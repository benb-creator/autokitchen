# R7 - Ingestion and Packaging

Research for the AutoKitchen ingestion module (BRIEF: "Ingestion", "opening product packaging"; PLAN: R7 feeding D8).
Version A = user dumps supermarket packages in a container, machine picks, scans, looks up, opens, funnels into a storage box.
Version B = user scans the barcode and pours the contents into the funnel.

## 0. Summary of findings

1. **Only about one fifth of a typical weekly shop should be decanted at ingestion** (dry, ambient-stable, free-flowing goods in paper, film or box-plus-inner-bag packaging: roughly 22 % of items, 30 % of mass, estimate). Everything else is either shelf-life-critical (cans, UHT milk, jars, vacuum and MAP meat, dairy tubs), reclosable and rigid (jars, bottles, tubes) or not a "packaged ingredient" at all (loose produce, eggs, butter, bakery).
2. **The key architectural finding: decanting starts the "after opening" clock at ingestion, not at use.** UHT milk goes from months to 3-7 days, a can from years to about 2-4 days, vacuum meat from weeks to about 1-3 days. So the ingestion module must have two routes, not one: **DECANT** (into a storage box) and **STOW** (scan, register, wash outside, store the sealed original in a carrier). Stowed packs are opened **just in time (JIT)** by a shared "opening cell" on the preparation side. That cell (can opener, jar/bottle uncapper, carton and tray cutter) is the same hardware family as the ingestion cutter.
3. With STOW plus JIT opening, about **70 % of items and about 85 % of mass** can be opened automatically at some point; about 28 % of items (produce, bakery, snacks, ready meals, eggs, butter) need no package opening or need a human.
4. **Opening mechanics are tractable.** Bag slitting stations exist industrially (5-6 bags/min per robot, rotating blades cutting 3 sides, up to 600 bags/h for high-rate systems). Twist-off caps need about 1.6-3 N·m, design to 6 N·m nominal and 10 N·m peak; PET caps about 0.5-2.5 N·m; cans can be side-cut or opened by ring-pull. The hard part is not force, but **hygiene** (blade carries outer-surface contamination into the food) and **fragments** (never sever film strips; slit, do not cut off).
5. **Bin picking of arbitrary packages is the single biggest technical risk of version A.** State of the art for suction picking is 95 % on rigid novel objects (Dex-Net 4.0, more than 300 picks/h) but only 75-80 % on deformable items; groceries are dominated by deformable bags. Recommendation: **do not start with a jumbled bin.** Use a single-file lane or pocketed magazine (user places each item, 2-3 s per item) and keep bin picking as a later upgrade behind the same pose-station interface.
6. **Barcodes:** use imager-based (2D) scanners, not laser line scanners, because of GS1 "Sunrise 2027" (POS must read 2D GS1 Digital Link QR / GS1 DataMatrix by end of 2027, dual marking with EAN-13 expected). Variable-weight items (prefix 20-29) are retailer-specific and not in Open Food Facts; treat them as "identify by label OCR / user". The best-before date is normally not in EAN-13; OCR plus fallback question to the user. GS1 2D codes can carry the date (AI 15/17) and lot (AI 10): a future path to drop OCR.
7. **Product data:** Open Food Facts (ODbL, about 4.78 M products, about 283 k with Germany as a country) is the primary source; use a local mirror plus live lookup (their rule: 1 API call = 1 real scan; 15 req/min product reads, 10 req/min search). Do not rely on it alone: expect gaps for store brands' newer products, quantity typos, and a poorly filled `packaging` field. Fallbacks: EAN-Search (EUR 9-19/month tiers), LLM/vision on a photo of the label, ask the user in the app. Map to internal ingredient IDs via OFF category taxonomy, with BLS 4.0 (free, CC BY 4.0, about 7,140 foods, since Dec 2025) as the German nutrient/ingredient anchor.
8. **Weigh everything.** Weigh gross before and empty pack after opening: gives tare-independent content mass, verifies the database entry, measures residue, and feeds the inventory ledger.
9. **Funnel:** flour bridges and dusts. Design a docked, sealed funnel with steep polished walls (or an inverted-cone, mass-flow shape), a vibrator, and a small dust extraction; wash-down between products; allergen-driven wash rules; new box per pack by default, top-up only same GTIN and similar date.
10. **Packaging waste** of a 2-person household from ingested food is about 1.1 kg and about 20 L (uncompacted) per week (estimate). Use 3-4 sorted bins (LVP / paper / glass / residual), rinse in the machine, never cut or crush deposit (Pfand) containers, human carries bins out weekly.

Source-quality note: the web-search budget of the session was exhausted before all searches were done. Values are tagged **[S]** (found in a cited source, numbered in section 13) or **[E]** (engineering estimate or general knowledge, not verified against a source in this session). Anything tagged [E] should be verified before it drives a design number. Several peer-reviewed or industry PDFs (torque data, peel forces, hopper design, flour dust explosion data) could not be fetched; these are exactly the [E] items called out in "Open issues".

---

## 1. Taxonomy of supermarket packaging (Rewe, Edeka, Aldi, Lidl)

### 1.1 Model of a weekly shop

Basis: German EVS 2023: an average household spends about EUR 335/month on food; 2-person households EUR 477/month, i.e. about EUR 110/week; spending shares: meat/sausage/fish 22 %, cereal products (bread, rice, pasta) 17 %, milk/dairy/eggs 17 %, vegetables/potatoes/pulses 14 %, fruit/nuts 9 %, sugar/sweets/desserts 8 % [S22]. Beverages are excluded here (crates, Pfand bottles; not ingested).

Model shop (my construction, [E]): 2 persons, cooking most meals, about **40 food items**, about **14 kg** food mass excluding beverages. Item share is what matters for the number of handling cycles; mass share matters for storage and dosing. The shares below are estimates; a measurement task (photograph 5 real receipts from Rewe/Edeka/Aldi/Lidl and count) is in Open issues.

### 1.2 Table A - quantities, geometry, barcode

Dimensions and masses are typical German retail packs (approximate, [E]). Barcode = EAN-13 nearly always; position is the usual location, not a rule.

| # | Class | Examples | Items % | Mass % | Typical size mm, mass | Barcode location |
|---|-------|----------|--------:|-------:|-----------------------|------------------|
| 1 | Paper bag / sack | flour, sugar, semolina, salt | 3 | 5 | 90-110 x 60-75 x 200-260, 0.5-1 kg (bag 8-12 g) | back or side panel, sometimes on the glued fold; bottom |
| 2 | Plastic pillow / flow bag, dry or frozen | pasta, rice, pulses, oats, frozen veg, fries | 8 | 8 | 100-200 x 40-70 x 230-300, 0.25-1 kg | back panel near the bottom seal; wavy, not on the seal |
| 3 | Stand-up pouch (zip) | nuts, dried fruit, grated cheese, spice refills, rice pouches | 4 | 2 | 130-200 x 40-80 gusset x 200-280, 0.1-1 kg | back, low |
| 4 | Cardboard box with inner bag | cereals, couscous, instant potato, tea, sugar cubes | 4 | 2 | 150-200 x 60-90 x 230-300, 0.3-0.75 kg | back or side of box, sometimes bottom |
| 5 | Beverage carton (Tetra Pak Brik/gable-top) | UHT/fresh milk, passata, cream, plant milk, stock | 6 | 12 | 1 L: 65 x 95 x 195, about 1.03 kg; 500 g passata: about 95 x 65 x 100 | side panel, near bottom |
| 6 | Tin can (ring-pull or plain) | tomatoes, beans, corn, tuna, coconut milk | 5 | 6 | 425 ml: dia 74 x 110, 0.4 kg; 850 ml: dia 99 x 119, 0.85 kg; tuna: dia 84 x 35 | printed or on paper wrap, side |
| 7 | Glass jar, twist-off lid | gherkins, sauces, jam, honey, pesto, jarred veg | 7 | 7 | dia 53-82 x 80-170, 0.3-1 kg (glass 150-300 g) | paper label at back or on the base; curved |
| 8 | Bottle with screw cap (glass or PET) | oil, vinegar, soy, ketchup, PET milk | 4 | 5 | 500 ml-1 L: dia 65-80 x 200-290, 0.5-1 kg | label on curved surface |
| 9 | Plastic tub with peel foil | yoghurt, quark, cream cheese, sour cream, margarine | 8 | 8 | 150 g cup dia 75 x 70; 500 g tub dia 100-110 x 90 | side sleeve or lid |
| 10 | MAP tray with top film | minced meat, steaks, cheese slices, sausage, fish | 10 | 6 | 190 x 140 x 35-50, 0.25-0.5 kg; cheese/sausage 190 x 110 x 20 | label on top film or base; variable-weight label for counter goods |
| 11 | Vacuum pack | ham, smoked salmon, cheese block, some meat | 4 | 2 | 120-200 x 200 x 30-60, 0.1-1 kg | printed on film or label |
| 12 | Butter foil wrap | butter 250 g, some margarine | 2 | 1 | 110 x 70 x 40, 0.25 kg | side of wrap |
| 13 | Egg carton | 6 or 10 eggs | 3 | 3 | 250 x 100 x 70 (10), 0.6-0.7 kg | lid or end label |
| 14 | Net bag / paper bag produce | onions, potatoes, citrus, garlic | 3 | 6 | 200 x 300 x 100, 1-5 kg | paper label or clip tag |
| 15 | Loose produce | cucumber, peppers, apples, bananas | 7 | 12 | 50-250, 0.1-0.5 kg per piece | none (PLU sticker on some) |
| 16 | Flow-wrapped produce | cucumber, lettuce, herbs | 4 | 4 | 60 x 350, 0.3-0.4 kg | sticker or film |
| 17 | Clamshell punnet | berries, tomatoes, mushrooms | 4 | 2 | 120 x 90 x 50, 0.125-0.5 kg | label on lid |
| 18 | Tube | tomato paste, mustard, mayonnaise | 2 | 0.3 | dia 40-45 x 180-190, 0.2 kg | crimp or body |
| 19 | Spice jar / sachet | herbs, spices, baking powder, gelatine | 2 | 0.2 | jar dia 45-55 x 80-110; sachet 10-30 g | jar base, sachet back |
| 20 | Shrink-wrapped multi-pack | 4-6 yoghurts, 4 cans, 6 bottles | 2 | 3 | 100-300, 0.6-3 kg | on the outer film; inner units carry own EAN (mostly) |
| - | Not ingredients: bakery, snacks, ready meals, sweets | bread, chocolate, frozen pizza | 8 | 5.5 | various | various |
| | **Total** | | 100 | about 100 | | |

Categories 10-13, 15-17 are perishable; 2 and 10-11 also appear as frozen variants.

Reference points: plastics make up the main component of about 57 % of German food and beverage packaging (2024) [S23]; PET (about 55 %) and PP (about 39 %) dominate food/beverage plastics [S23].

### 1.3 Table B - opening, outflow, residue, difficulty

Difficulty: 1 = trivial for a machine, 5 = research-grade. "Route" is explained in section 2 (D = decant at ingestion, S = stow sealed and open JIT, M = manual / human, P = keep the pack as is; open by unwrapping or cracking JIT).

| # | Class | Best automated opening | How contents come out | Residue left in pack [E] | Difficulty | Route |
|---|-------|------------------------|-----------------------|---------------------------|:----------:|:-----:|
| 1 | Paper bag | hook or straight blade slit across the front near the top; hold the bag, invert, shake 10-20 Hz | free-flowing; flour clings and dusts | 0.5-2 % (5-20 g per kg) | 2 | D |
| 2 | Pillow bag | slit just below the fin seal (no offcut), invert, shake; hot knife works on PE/PP | free-flowing; frozen veg clumps (needs shaking, brittle film) | 0.2-1 % | 2 | D (frozen: D or S) |
| 3 | Stand-up pouch | slit above the zip or straight across the top; keep the zip attached | free-flowing (sticky if dried fruit) | 0.5-3 % | 3 | D |
| 4 | Box with inner bag | open box flap by tuck-flap lifter or cut the box top; then slit the inner bag; or slit box and bag together in one pass | free-flowing | 0.5-2 % | 3 | D |
| 5 | Carton | unscrew cap and pierce the membrane (cap with cutter ring), or cut a top corner/gable; hold upright | liquid | 1-2 % | 2-3 | S |
| 6 | Tin can | ring-pull: hook finger and 15-40 N pull; plain: side-cut wheel (safe edge, lid stays on a magnet) | pours; chunky or thick contents need scraping (tomato, beans in brine) | 2-5 % (up to 10 % for paste) | 3 | S |
| 7 | Glass jar | grip lid, break vacuum by piercing or button/lever, rotate 1/4 turn (lug cap), re-close if leftovers | pours (pickles) or sticks (jam, honey, pesto: needs scraping) | 3-8 % for sticky | 3 | S |
| 8 | Bottle | unscrew cap (tamper ring breaks), tilt over scale, re-cap; oils: drip catcher | liquid | 1-3 % | 2 | S |
| 9 | Tub with peel foil | pierce or circle-cut the foil (no tab needed), or pinch tab and peel at 5-15 N; then squeeze/scrape | viscous, sticks, needs scraping or squeezing | 5-10 % | 4 | S |
| 10 | MAP tray | hot wire or blade cutting the top film inside the flange; or peel at pull tab (cheese) | meat: falls as a lump with juice; slices: stack sticks, needs spatula | 1-3 % (juice) | 4 | S (raw lane) |
| 11 | Vacuum pack | cut a corner or one side (vacuum releases), then pour | meat lump, greasy | 1-3 % | 3-4 | S (raw lane) |
| 12 | Butter foil | unwrap: fold/tuck geometry, no reliable slit option; hot knife through foil is possible but leaves foil on butter | solid block | 1-2 % butter stays on the foil | 5 | P (unwrap JIT or manual) |
| 13 | Egg carton | no opening: lift carton lid; eggs stay in original carton, cracking is a prep task (R4) | solid eggs | none | 2 | P |
| 14 | Net bag | slit with a blade; nets snag and stretch, needs a clamp; pour into a produce box | free-flowing (potatoes, onions) | 0 % | 3 | D (later) or M |
| 15 | Loose produce | not applicable; vision ID and weigh | n/a | n/a | 3 (ID) | M or P |
| 16 | Flow-wrapped produce | slit along the fin | solid | 0 % | 2 | S or M |
| 17 | Clamshell | pop the lid catch or lift; fragile contents | solid, fragile | 0 % | 3 | S or M |
| 18 | Tube | uncap; roller squeeze; re-cap | paste, needs squeezing | 3-8 % | 3 | S |
| 19 | Spice jar / sachet | jar: shaker cap opened by rotating; sachet: tear/slit | powder, dust | 1-3 % | 2-3 | jar: S; sachet: D |
| 20 | Multi-pack | slit outer film, discard, then treat units separately | n/a | n/a | 2 | pre-step |

### 1.4 What fraction of a shop can realistically be opened automatically

Three tiers (item shares of section 1.2 summed, [E]):

| Tier | Classes | Items | Mass | Comment |
|------|---------|------:|-----:|---------|
| T1: decant-ready (dry, ambient-stable, free-flowing, cheap to slit) | 1, 2 (dry), 3, 4, 19-sachet | about 20-22 % | about 27-30 % | the ingestion cutter and funnel's proper job |
| T2: automatable but better kept sealed and opened JIT | 5, 6, 7, 8, 9, 10, 11, 16, 17, 18, 19-jar, frozen bags | about 48-52 % | about 55 % | needs the opening cell on the preparation side |
| T3: no package opening, or human only | 12, 13, 14-15 loose, bakery/snacks/ready meals | about 28 % | about 15 % | eggs, butter and produce are stowed as is (P) or put in by hand |

- Opened automatically at ingestion (T1): about **22 % of items, about 30 % of mass**.
- Opened automatically at some point in its life (T1 + T2): about **70 % of items, about 85 % of mass**.
- Reliability caveat: the "automatable" ratings assume opening success of 90-98 % per class after tuning. Mass share is more relevant for cooking; item share is more relevant for handling cycles and jams.

### 1.5 What is better left in the original container

| Product | Keep original because | Machine interaction |
|---------|-----------------------|---------------------|
| Eggs | shelf life about 28 days from laying, carton is a perfect protective tray, no decant option; cracking is in prep | store carton in a carrier; robot lifts carton lid and picks eggs for the cracker |
| UHT milk carton or PET bottle | sealed months, opened 3-7 days [S20] | chuck unscrews cap, pours to scale, re-caps, back to the fridge; empty PET milk bottles are deposit items (Pfand 25 ct since 2024) [S19] |
| Cans | sealed years; opened, VZ advises transferring to a lidded container (lacquer damage, tin) and consuming quickly [S20] | JIT: side-cut or ring-pull at the opening cell; leftover to a lidded box with a timer, or planner uses whole cans |
| Jars, bottles (oil, vinegar) with screw or twist-off caps | reclosable rigid containers are already good storage boxes; sauce/jam jars keep for weeks when closed | uncap, dose, re-cap; pack becomes its own box in a carrier |
| Vacuum meat, MAP meat/fish, cheese blocks | sealed vacuum beef 3-5 weeks chilled, pork 20-28 days, poultry 6-9 days [S20]; opened, days | keep sealed in a carrier with leak-tight tray; open JIT in the "raw lane" |
| Yoghurt, quark, cream tubs | date is weeks; opened 3-5 days [E]; planner can pick whole tubs | JIT cut/peel and squeeze |
| Butter, hard cheese, sausage | own barrier wrap; needs slicing, not pouring | P, opened at prep |
| Produce | needs airflow and cooling, no decant | P, own produce bin |
| Tubes, spice jars | reclosable | S, dose from original |

---

## 2. Shelf life and the architecture of ingestion (the central question)

### 2.1 Facts

| Product | Sealed (chilled/ambient) | After opening | Source |
|---------|--------------------------|---------------|--------|
| UHT (H-Milch) | several months without cooling | must be cooled; 3-7 days (VZ: "a few days"; other sources 3, 7, and 6-7 days in a secondary-shelf-life study) | [S20] |
| Fresh milk / ESL | about 1-3 weeks | "within a few days" | [S20] |
| Tin cans | many years beyond the printed date if undamaged and stored below 19 °C | transfer to a lidded glass/steel/food-grade container; then as fresh food, about 2-4 days for cooked-type contents [E] | [S20] |
| Vacuum-packed beef | 3-5 weeks chilled (30-40 days), pork 20-28 days, poultry 6-9 days | roughly as fresh meat: 1-3 days [E] | [S20] |
| Low-O2 MAP beef | 25-35 days (bulk); retail high-O2 packs much shorter (Verbrauchsdatum in 3-7 days for mince) [E] | 1-2 days [E] | [S20] |
| Yoghurt, quark | 2-4 weeks | 3-5 days [E] | [E] |
| Jars: pickles, jam | months to years | jam weeks, sauces 1-2 weeks, pickles months [E] | [E] |
| Dry staples: flour, rice, pasta, sugar, salt, lentils, oats | 6-24 months | same (barrier: humidity, pests, oxidation of wholegrain and nut products) | [E] |
| Frozen veg | 12 months | same at -18 °C; freezer burn if the bag is open and air can reach | [E] |

Regulation note [E, EU 1169/2011 art. 24, not fetched]: "Verbrauchsdatum" (use-by, "zu verbrauchen bis") on raw meat/fish is a safety limit and must be a hard stop; "Mindesthaltbarkeitsdatum" (MHD, best before) is a quality date. The machine must read and store which of the two it is.

### 2.2 The mechanism

Decanting does not change the physics of "after opening" shelf life; it moves the moment the clock starts from first use to ingestion. If the interval ingestion-to-use of the last unit (T_hold) exceeds the opened shelf life T_open, decanting destroys food. Example: 6 x 1 L UHT bought for a 2-person household: sealed 120 days, use rate about 1 L per 3 days; decanting all 6 L into one box at ingestion gives 6 L that must last T_open = 3-7 days while the demand is about 2 L in that time: about **two thirds wasted, and the effective shelf life falls by a factor of about 20**. The same arithmetic applies to cans (years to days), vacuum meat, tubs.

Secondary arguments for keeping the sealed original:
- **Hygiene barrier:** a sealed pack is the best barrier there is; no food-contact surface of the machine ever touches raw meat, milk, etc. That removes the largest allergen and raw-meat cleaning burden from the funnel and the boxes.
- **Traceability:** label, lot, allergens and recall information remain on the pack (photographed and stored at ingestion in any case).
- **Reclosable rigid packs are already storage boxes** (jars, bottles, tubes).

Arguments for decanting:
- Standard boxes and dosing: the machine's preparation stage assumes pourable material in standard boxes (BRIEF, "Preparation"); decanted dry goods can be dosed by weight with one interface.
- Storage density: a box filled to the brim with rice is denser than the same mass of bags.
- No package-opening hardware on the preparation side for dry goods.
- Protection from pantry pests, humidity (box with a gasket lid beats an opened bag).

### 2.3 Decision rule

```
                        product ingested
                              |
          T_sealed >> T_open ?  (opened life drops by more than ~5x
                              |   or opened life < 30 days)
                 no ----------+---------- yes
                 |                          |
        free-flowing, dry,           reclosable rigid pack? (jar, bottle,
        cheap to slit?                tube, PET/carton with cap)
          |            |                |               |
         yes           no              yes              no
          |            |                |               |
        DECANT     STOW (keep        STOW; pack is    STOW sealed in
       (route D)   pack; route P     its own box;     leak-tight carrier;
                   or S)             uncap/dose/      open JIT; leftover to
                                     re-cap           timer box or plan
                                                      uses whole pack
```

Additional exceptions:
- **Same-day use (direct-to-vessel):** if the meal plan uses the entire pack today, the opening cell can pour directly into the preparation vessel without a storage box.
- **Planner awareness:** if the meal plan can guarantee use within T_open (e.g. planned cooking tonight), decanting is allowed; default rules by class avoid needing this.
- **Pack-size-aware planning:** plan whole packs where possible (a 400 g can for a recipe needing 400 g); leftover management is a scheduling, not a mechanical, problem.

### 2.4 Assignment per class

| Class | Route | Why |
|-------|:-----:|-----|
| Paper bags, pillow bags (dry), stand-up pouches (dry), box+inner bag, spice sachets | D | dry, stable, free-flowing |
| Frozen bags | D (freezer box with lid) or S | opened frozen veg is fine at -18 °C when boxed; decanting needs the bag cut while brittle and clumped |
| Cartons (milk, passata, cream) | S | opened life days |
| Tin cans | S | sealed years, opened days |
| Jars | S | reclosable |
| Bottles | S | reclosable |
| Tubs | S | opened life days |
| MAP trays, vacuum packs | S (raw lane) | sealed weeks, opened days |
| Butter, eggs, cheese blocks, sausage | P | not pourable; own wrap or carton |
| Net bags (onions, potatoes) | D (later) or P | free-flowing, but nets snag; produce needs airflow anyway |
| Loose produce, punnets, flow-wrap | M or P | no meaningful package opening |
| Spice jars | S | reclosable, small amounts used slowly |
| Multi-packs | pre-step | remove outer film, treat units |

### 2.5 Consequences for the architecture

1. **Ingestion has two output lanes: DECANT and STOW.** STOW = scan, weigh, register, surface rinse (see below), put into a carrier, hand to the transport system. This lane is the same in versions A and B.
2. **A JIT opening cell exists on the preparation side.** It must handle can, jar, bottle, carton, tray/vacuum pack, tube, tub. The ingestion cutter and the JIT cell share design (blade cell, uncapper chuck, can opener); the alternative of having the ingestion station also serve as the JIT opening cell by taking the pack back out of storage is attractive for footprint (the brief asks for no wasted footprint) but adds a round trip through the transport system for each use. Recommendation: **one physical opening cell, reachable from both ingestion and preparation via the transport system** (decision for A1).
3. **Storage must hold sealed packs.** New item type in the inventory: "pack instance" with GTIN, serial number, weight ledger (current gross weight minus tare), best-before/use-by, opened timestamp, state (sealed/open/empty). Carriers: standard box with a shaped insert, or "pucks" that give cylindrical packs a common outer footprint.
4. **Leftover handling:** after JIT opening, remaining content stays in the original if it is reclosable (jar, bottle, tube), else is transferred to a lidded box in the fridge with a timer ("opened at, use by").
5. **Cold chain during ingestion.** EU practice is a 2-hour rule for chilled goods out of refrigeration [E]. Version A's "dump into a container" input bin should be either chilled (Peltier or a fridge segment) or, more simply, the user is told to put chilled and frozen items into a separate cooled input drawer at once. Items in the bin need a timer: alarm at 30 min if chilled goods have not been ingested.
6. **Surface rinse.** Outer surfaces of retail packs are dirty (cardboard dust, pallets, shelves). Before anything enters a food area, rinse (hot water shower plus air knife) cans, jars, bottles, cartons; not paper bags, boxes (they would soak), or deposit packs' labels (rinse quickly, do not scrub).
7. **Box slot budget:** with about 40 items/week, decant ≈ 9 boxes, stow ≈ 20 packs (about 8 boxes if 2-3 per carrier), total about 17 box movements in and out per week. R3/D1 must confirm capacity.

---

## 3. Opening mechanisms

### 3.1 Industrial state of the art

- **Bag slitting / emptying stations** (25 or 50 kg sacks): rotating blades slit along 3 sides while gravity empties the bag and rotating nylon wheels push the empty bag down to a separate auger outlet; a vibrating screen filters oversize impurities after emptying [S11 Tinsley]. Palamatic SackBot 100: robot-mounted, 5-6 bags/min, four cutting variants: fixed cross-cut blades (granular), single fixed blades (free-flowing, sensitive), rotary disc blades (tough bag materials), mobile blades on guide units (maximise opening, reduce retention zones); accepts kraft paper, plastic, jute, woven bags with inner sachets; dust extraction and a confined hopper are optional [S11 Palamatic]. LaborSave claims 99.99 % emptying rate and more than 1,800 installations for sugar, flour, rice, frozen vegetables and more [S11 Laborsave]. High-rate systems reach up to 600 bags/h [S11 Powder Bulk Solids]. Relevance: the principle (slit three sides, pull the bag free, screen the product) scales down to 0.25-1 kg packs; the residue claims do not transfer to 500 g pouches with sticky content.
- **Can opening machines:** Morrison Model 20 opens up to 20 #10 cans/min, Model 60 up to 60/min, using a crown punch and a magnetic de-lidder that drops the lid into a chute; safety guarding [S12]. D.C. Norris AutoCAN 1000: 1,000 A10 cans/h (opener plus crusher) [S12]. Domestic "side-cut" (safe-cut) openers cut the seam below the rim and leave a smooth edge; the lid stays on a magnet.
- **Depackaging machines** for out-of-date packaged food exist (they shred and separate), but they destroy the food and are not relevant.
- **Films on trays:** peelable lidding, laser scoring, hot wire and ultrasonic sealing/cutting are well established in packaging production; they show that film can be cut without a contacting blade.

### 3.2 Mechanism catalogue

Forces are estimates unless marked [S]; measure before design freeze.

| Mechanism | Suits | Force / power [E unless noted] | Pros | Cons | Cleaning of the tool | Fragment risk |
|-----------|-------|-------------------------------|------|------|----------------------|---------------|
| Straight blade on linear axis (slit) | paper bags, film bags, boxes, nets, multi-pack film | 2-10 N for 30-100 um film, 5-30 N paper/cardboard | simple, cheap | contaminates blade; needs film tension and support | wash cabinet: 60-80 °C hot water jets plus hot air; or single-use blade cartridge | low if slit not sever |
| Hook blade ("ripper"), pulled through film from inside outward | film bags, pouches, vacuum packs | 2-5 N | cuts away from the contents, no offcut, guards easy | needs a puncture start | as above | very low |
| Rotary disc / rolling cutter | paper, cardboard, cartons, tough film | 5-30 N | continuous cut, long blade life | fibres from paper; shear-type slivers | as above; disc can rotate in a cleaning bath | medium (slivers, paper fibres) |
| Hot wire / hot knife | thermoplastic films (PE, PP, PET), vacuum bags, shrink film, nets (PE) | 250-400 °C, 20-50 W, below 1 N | no fragments (melts and forms a bead), tool at 250 °C is self-sanitising | not for paper or aluminium foil, smoke and melt drops, fire and burn hazard, energy | wipe off, burn off | very low (melt beads) |
| Ultrasonic knife (20-40 kHz sonotrode, titanium) | foods (cheese, sausage, cake), film, some laminates | low cutting force vs steel [S13]; system EUR 2-5 k [E] | very low force, self-cleaning effect for sticky food, clean cuts [S13] | cost, generator and horn tuning | horn self-cleans, wipe or spray | very low |
| CO2 laser (30-100 W) | thin films (below 100 um), lidding film scoring | 30-100 W typical for below 100 um multilayer, 300-450 W for scoring lidding laminate [S14] | no blade at all, no contact contamination | smoke and burnt edge residues, Class 1 enclosure, not for aluminium foil and tinplate, cost EUR 3-10 k [E] | none needed for the beam | none if partial-depth scoring leaves a hinge |
| Pierce needle or punch | foil lids (yoghurt, tubs), Tetra Pak membranes, jar-lid vacuum break | foil 5-15 N, tinplate lid 100-300 N [E] | trivial | bare puncture, cuts food surface | rinse and hot air | metal shards from lid piercing (avoid on jars: use lever or button) |
| Can cutter: side-cut wheel, crown punch | plain cans | wheel force 30-100 N, rotation torque 0.3-0.6 N·m [E] | industrial precedent [S12] | tinplate lid edge is sharp, lid handling, brine spray | wash after each can; hot water plus air | metal filings: use side-cut, magnet lid removal |
| Ring-pull hook | stay-on tab cans | pull 15-40 N [E] | simple | tab detection, lid edge | hook washed | low |
| Clamp and tear / peel | tabbed foils (yoghurt, cheese pack peel corners), easy-open notches | peel 5-15 N (tub foil) [E]; notch tear 3-10 N [E] | no blade, no cleaning | needs the tab or notch; vision problem; unreliable on some tubs | gripper fingers washed | very low |
| Unscrewing chuck | jars, bottles, tubes, cartons with caps | see 3.3 | standard | glass breakage, caps that tear | chuck washed | low; plastic bridges can shed |
| Squeeze / roller | tubes, soft tubs | 20-80 N [E] | simple | residues | roller washed | none |

### 3.3 Torque values

- Twist-off (lug) caps on glass jars: removal torque of vacuum-release aluminium lids averaged 1.6 N·m, and 20-51 % lower than standard lids [S9 Food Protection Trends]. So standard lug lids average about 2-3 N·m [derived, E]. Usability guidance: opening torque for a 66 mm jar lid should be limited to 2 N·m for seniors [S9]. Lug caps need only a partial turn (about 1/4 turn) [S9].
- PET screw caps 28 mm (PCO 1881 for carbonated drinks): datasheets found do not give torque; typical removal torque 0.5-2.5 N·m plus the tamper band bridges [E].
- ROPP aluminium caps (oil, vinegar, spirits in glass): 3-5 N·m [E].
- Beverage-carton screw caps: 0.5-1.5 N·m [E].
- **Design values for the chuck:** nominal 6 N·m, peak 10 N·m with a slip clutch or motor torque limit; jar body held against reaction torque by a rubber V-clamp or 3-finger holder, clamp force limited (about 100-200 N) to avoid glass damage; rotation of 90-120° for lug caps, 3-4 turns for screw caps. Vacuum: hot-filled jars carry a partial vacuum of about 0.3-0.6 bar [E]; break the vacuum with a small lever on the lid skirt, a thin needle through the lid, or by observing the "pop" (safety button deflection). The safety button is also a **spoilage check**: a domed button means the jar has lost vacuum or is swollen: reject.
- Cans: bulging or heavily dented cans must be rejected (VZ) [S20]; detect by shape/weight.

### 3.4 Blade contamination and cleaning

Problem: a blade that first passes the (dirty, possibly Listeria-carrying) outer package surface then enters the food carries contamination inward; on the way out, food residue stays on the blade (allergens, raw meat).

Measures:
1. **Cut from the inside out** (hook blade after a small clean puncture; or piercing tip plus outward pull), or use non-contact cutting (hot wire, laser, ultrasonic).
2. **Rinse the pack exterior first** (section 2.5) for rigid packs; dry with an air knife.
3. **Clean the tool after every pack:** retract into a wash cabinet: spray with 70-80 °C water with detergent, then steam or hot air at 100 °C or above; measurable effect: hot-wire at 250 °C or more self-sanitises. UV-C is not sufficient for shadowed geometry [E].
4. **Single-use blades:** a magazine of 20-50 utility blades (about EUR 0.03 each, EUR 1/week for 30 cuts) removes cleaning validation for the blade edge. Cost and metal waste are small; the mechanics of loading and dropping blades are a design issue [E].
5. **Blade material:** hardened stainless (1.4034 / 440C), ceramic (zirconia, brittle), or titanium sonotrode. Track blade wear by cut count, replace by a schedule.
6. **Separate cutter for raw:** the raw lane has its own cutter or a mandatory hot-wash cycle. Meat trays are never routed via the dry funnel.

### 3.5 Preventing packaging fragments in the food

- **Geometry:** slit, never sever: the opening is a slit or a flap that stays attached; no offcut strip. Avoid cutting the fin-seal off a pillow bag (creates a 5-10 mm strip). Hold the pack by the gripper during emptying; the pack leaves as one piece.
- **Choose cutters that do not shred:** hook blade, hot wire, laser, ultrasonic. Paper bags shed fibres: sieve flour after emptying (1-2 mm).
- **Screening:** a vibrating screen after the pack (as in the industrial station [S11 Tinsley]) works for powders (1-2 mm sieve) and for granules larger than sieve mesh; for pasta and rice a coarser grid (12-15 mm) catches large film pieces only.
- **Vision check of the funnel outlet:** a camera above the outlet flags foreign material of contrasting colour; clear film is hard [E].
- **Metal check:** blades can chip; a small inductive coil around the funnel outlet could flag ferrous fragments; industrial units are expensive, custom coil is an open issue [E].
- **Empty-pack inspection:** after emptying, weigh the empty pack and inspect with a camera for missing pieces (compare mass to the declared tare from the first ingest of that GTIN).
- **Fallback on any uncertainty:** the box is flagged "possible foreign object" and the user is asked to inspect.

### 3.6 Recommended opening cell per class

| Class | Cell |
|-------|------|
| Paper bag, pillow bag, pouch, box+inner bag | **Slit-and-shake station:** V-cradle, hook blade or hot knife (film) or straight blade (paper), clamp on the closed end, wrist rotation to invert, vibration 10-20 Hz, sieve, wash cabinet |
| Carton with cap | uncapper chuck, membrane pierce; cartons without cap: hook blade at the gable corner |
| Tin can | side-cut wheel with magnet; ring-pull hook; both optional |
| Jar, bottle, tube | chuck plus clamp, lever or needle for vacuum break, re-cap |
| Tub | foil pierce plus circular cutter (side-cut principle) or tab peel; squeeze or scraper |
| MAP tray, vacuum pack | hot wire (film) plus tilting tray holder; raw lane |

---

## 4. Singulating and picking packages

### 4.1 State of the art

- E-commerce piece picking runs at 600-1,200 picks/h [S16 claru], RightHand Robotics RightPick 800-1,000 units/h with a combined suction and finger gripper [S16], Berkshire Grey claims over 99 % accuracy and quick-change suction cups for polybags, rigid boxes and porous cloth [S16]. Dex-Net 4.0 (open research code) clears bins of up to 25 novel objects with above 95 % reliability at more than 300 picks/h with suction plus parallel-jaw [S16]. Reported success drops to 75-80 % on deformable items vs 95 % on rigid parts [S16].
- Our throughput need is low: 40 items in about 30-60 min means 1-2 picks/min. Reliability matters, not speed: a failed pick needs a retry (re-pose, retry from another side) and finally a fallback to the user.
- Grocery packs are a hard mix: rigid cylinders (cans, jars, bottles), rigid boxes (cartons, cereal), deformable (pillow bags, pouches), nets, trays, slippery wet packs (yoghurt cups with condensation), heavy (2.5 kg potatoes).

### 4.2 Cameras

| Camera | Price | Notes |
|--------|------:|-------|
| Intel RealSense D405 | USD 272 [S17] | 7-50 cm ideal range, depth error below 2 % at 50 cm, up to 1280 x 800 at 90 fps: the standard for close-range grasping; RealSense is now an independent company (spin-off completed July 2025) with the same SKUs [S17] |
| Intel RealSense D435 | USD 314 [S17] | wider range, global shutter |
| Luxonis OAK-D Lite / OAK-D / OAK-D Pro | USD 269 / 329 / 429 [S17] | on-device AI (4 TOPS in OAK-D), DepthAI; good for classification at the edge |
| Orbbec Gemini 335, Zivid, Photoneo | EUR 300 / several k / several k [E] | Orbbec is a common RealSense alternative; structured light gives better detail |

### 4.3 Software

- Suction grasp planning: Dex-Net 2.0/3.0/4.0 (Berkeley, open code; older but widely reused) [S16]; simple heuristic (depth-flatness heat map, highest item first) works decently for boxes and cylinders [E].
- Parallel-jaw and 6-DoF: Contact-GraspNet (NVIDIA, open code) [S16]; GraspNet-1Billion, AnyGrasp mentioned in the literature [S16]; MoveIt with MoveIt Grasps for motion planning [E].
- Segmentation: Segment Anything or Mask R-CNN to isolate items in the bin [E].
- Grocery items, deformable bags and nets are the weak point of all of these [S16].

### 4.4 Grippers

- Suction cups with bellows (30-50 mm), high-flow ejector for porous paper bags; FDA-conformant silicone cups (Schmalz, Piab) [E].
- Soft or Fin-Ray fingers for nets, tomatoes; 3D-printable in TPU [E].
- A rigid parallel gripper with rubber pads for jars and cans (handles and re-orientation during scanning) [E].
- One arm with quick-change tools or two arms/pick stations; a hybrid suction plus finger gripper as RightHand's [S16].

### 4.5 Simpler alternatives (recommended over a jumbled bin)

| Option | How | Pros | Cons |
|--------|-----|------|------|
| **Single-file lane / belt** | user places one item at a time on a belt or slide (like a supermarket checkout), sensor detects an item, belt stops at the pose station | user effort 2-3 s per item; pose within +-20 mm; no bin picking | user must singulate; belt is a cleaning surface |
| **Pocketed magazine / carousel** | 12-16 pockets (about 150 x 150 x 300 mm), user drops one item per pocket (light curtain or load cell), carousel indexes | pose constrained, weighs each item, buffer for pack flow; cold pockets possible | footprint; only rigid-ish and small packs; large 1 L cartons and 1 kg bags need slot size 100 x 100 x 300; more mechanics |
| **Drawer with compartments** | fixed compartments for chilled, frozen, dry, glass | segregates by handling route at loading, solves cold chain | user has to pre-sort |
| **Tilted vibratory hopper** | tumbles items to a pick lane | cheap | bags jam, cans roll and break, jars clink |
| **Bin picking (user dumps)** | as in the brief | best user experience | highest risk; deformable, entangled nets, stacking; recovery needed |

**Recommendation:** baseline = single-file lane with 10-15 slot buffer; bin picking is a stretch goal behind the same interface ("item presented at the pose station in a known 2D pose"). A hybrid, where the user drops into a shallow tray and the arm picks only the top item with a cheap depth camera, can be evaluated in a prototype cycle.

---

## 5. Barcode scanning and identification

### 5.1 Symbologies

- **EAN-13** (13 digits, 95 modules) and **EAN-8** for small packs [S8]. Nominal X-dimension 0.33 mm, magnification 80-200 % (X 0.264-0.66 mm), symbol including quiet zones about 37.3 x 25.9 mm at 100 % [E, consistent with the 95-module structure in S8]. Check digit is modulo 10 with alternating weights 3 and 1 [S8].
- **GS1 DataBar** appears on loose produce stickers and coupons; DataBar Expanded can carry weight and date [E]. Imager-based scanners read it; some old laser scanners cannot.
- **GS1 QR (Digital Link) and GS1 DataMatrix:** **Sunrise 2027**: by 31 December 2027 retail point-of-sale systems must be capable of reading and processing a GTIN in a QR Code with a GS1 Digital Link URI or a GS1 DataMatrix; the 1D barcode is not banned, and dual marking (1D and 2D side by side) is expected for years [S6]. Consequence: the AutoKitchen scanner must be an **imager (camera) with 2D decoding**. A laser scanner is a dead end. The GS1 Digital Link URI has the form `https://.../01/{GTIN}[/10/{lot}][?17={expiry}]`; GS1 element strings include AI 01 (GTIN), 10 (lot), 15/17 (best before/expiry), 310n (net weight kg) [E].
- Not all QR codes on packs are GS1: many are marketing links (recipes, recycling). The parser must pick the GS1 pattern and ignore the rest.

### 5.2 Finding the barcode on an arbitrary pack

Approaches:
1. **Presentation scanning with rotation.** The gripper holds the item in front of 2 fixed imagers on opposite sides and rotates 4 x 90 degrees about its long axis, then re-grasps or flips to see the ends: about 5-15 s per item [E].
2. **Bioptic (checkout) approach.** A glass plate plus mirrors: imagers below and to the side see 5 of 6 faces at once as the item is placed; the same idea as supermarket bioptic scanners. NCR Voyix Halo Checkout and Toshiba MxP Vision Kiosk are camera-based multi-item "bulk scanning" checkouts (2024-25 pilots) using vision AI (Everseen); they identify items partly without the barcode [S24].
3. **Tunnel (self-checkout portal).** Items pass through a frame of 4-6 cameras on a belt; the pack tumbles or is held; best coverage, but expensive and needs space [S24].

Camera geometry: at the worst case (magnification 80 %, X = 0.264 mm) and 3 px per module, pixel pitch on the item must be at most 0.088 mm; a 5 MP sensor (2592 x 1944) then covers about 228 x 171 mm: one camera per side of a typical pack, 2 cameras for a pack held in a gripper [E]. Use a global-shutter sensor with a ring light (avoid glare on film and cans; polarised light helps) and decode with ZXing-C++ or zbar, both open source and handling EAN-13 and GS1 codes [E]; commercial decoders (Scandit, Dynamsoft) do better on curved and blurred codes [E].

Difficulties: cans (curved and shiny), pouches (wrinkled, reflective), pillow bags (barcode in a fold), packs with the barcode on the flap or hidden under a tuck.

Failure cascade: (1) 2 imagers x 4 rotations (10 s); (2) tumble or flip once; (3) ask the vision model (photograph front and back, LLM reads product name and brand and matches OFF text search); (4) show "hold the pack up to the camera" on the machine display (user assist); (5) route to the manual lane.

### 5.3 Off-the-shelf scanner options

| Option | Price | Comment |
|--------|------:|---------|
| Camera modules plus software decode (Arducam or Raspberry Pi global shutter, ZXing) | EUR 30-80 per camera [E] | flexible, needs an SBC or PC; my default for a prototype |
| Embedded 2D scan engine (Newland, Honeywell N6603, Zebra SE4710, GM65-type low-end) | EUR 15-25 (GM65 class, small DoF) to EUR 100-300 (Newland or Honeywell industrial) [E] | reads 1D and 2D, decodes on-chip, delivers over UART/USB |
| Handheld 2D imagers (for version B) | EUR 80-150 basic [E]; industrial Zebra DS3678 EUR 481, Honeywell Granit 1991i EUR 383 [S: logiscenter listing] | plug and play |
| Fixed-mount industrial (Cognex DataMan, Datalogic Matrix) | EUR 1,500-3,000 [E] | overkill but the reliability reference |
| Phone camera in the app | free (ML Kit, ZXing) | for version B or fallback |

### 5.4 Variable-weight items

- EAN-13 numbers starting with **02 and 20-29** are for restricted circulation numbers, i.e. store-internal, variable measure (weight or price) [S7]. Each GS1 member organisation and, in practice, each retailer decides the layout: typically prefix, item number, a check digit, then 4-5 digits of price or weight [S7, E]. In Germany the counter (Bedientheke) label and the pre-packed "SB-Frischfleisch" label follow the retailer's own scale system.
- These numbers are **not resolvable in Open Food Facts or GS1 registries**; the item reference maps only inside that retailer's master data (and Rewe's and Edeka's schemes differ). Handling: parse the embedded price or weight (validates the mass), OCR the label text (product name, "Verbrauchsdatum", "Bruttogewicht"), match text to a generic ingredient by LLM, ask the user to confirm; remember the mapping by (retailer prefix + item number) after the first time.
- GS1 Belgium and Luxembourg guidance documents the move from national numbers to GS1 DataMatrix / GTIN for variable measure at POS [S7]: possibly the future path.

### 5.5 Best-before date

- **Not in the EAN-13.** Only GS1 2D (DataMatrix, QR Digital Link) can carry it (AI 15 or 17) [E, consistent with S6]; adoption is optional and slow.
- **OCR:** a camera with a ring light reads the date printed by inkjet or laser code (can lid, jar cap, carton fold, bag seal) after the robot rotates the pack until the "MHD" or "zu verbrauchen bis" text is found. Dot-matrix inkjet on curved or shiny surfaces gives maybe 70-90 % read rate with standard OCR (PaddleOCR, Tesseract) [E]; a vision LLM on a 3-4 view photo set is better at the layout problem (find "MHD:") and comparable at digits.
- **Fallbacks:** OFF's `expiration_date` field is rarely filled [E]; use a class default (e.g. 5 days from ingestion for MAP mince; 1 year for cans) flagged as "estimated", and ask the user for the date in the app if the product class is perishable. Never allow an unknown date for raw meat or fish to be silently defaulted: require confirmation.
- Distinguish Verbrauchsdatum (hard stop) from MHD (quality).

### 5.6 Loose produce (no barcode)

- Some fruits carry PLU stickers (4-5 digits; 4xxx conventional, 9xxxx organic per IFPS) [E] or small EAN-13 stickers; OCR of the digits or the sticker's own barcode works when visible.
- Vision classification (fine-tuned ViT or ConvNeXt on ~100 common produce classes) gives high accuracy on clean backgrounds (about 95 % [E]); real kitchens fall in the low 90s. Add weight (0.1 g load cell) to derive count. Fallback: ask the user via the app with a photo.
- Recommendation: produce is not routed through package opening at all (M or P): user places produce into produce bins at a manual station; the machine identifies it by a photo plus weight.

### 5.7 Identification pipeline

```
 pack at pose station
   -> weigh (gross)
   -> scan (2 imagers x rotations)  --fail--> vision/LLM label read --> user
   -> code type?
        EAN-13/EAN-8 (GTIN)  -> local OFF mirror -> live OFF -> EAN-Search -> LLM/user
        GS1 2D               -> GTIN + date + lot directly
        prefix 02/20-29      -> retailer parse + label OCR + user
        none                 -> vision
   -> date OCR (MHD / Verbrauchsdatum)
   -> product record: name, net quantity, categories, allergens, ingredients, packaging
   -> map to generic ingredient ID (section 6.3)
   -> plausibility: gross - declared tare ~ declared net?  (else flag)
   -> route: DECANT | STOW | MANUAL
```

---

## 6. Product databases

### 6.1 Open Food Facts (OFF)

- Coverage: about **4.78 M products worldwide**, about **283 k with Germany as a country** [S1]; 25,000+ contributors [S1]. German coverage is boosted by active local contributors (a German pantry app, Smantry, is the second-biggest German contributor [S5]). Gaps are likely for new or seasonal store-brand items and for very regional products; the percentage for a real German weekly shop is unmeasured (Open issue: test 200 EANs from a real shop).
- API: `GET /api/v2/product/{barcode}.json`, `fields` parameter to reduce payload, search at `/api/v2/search`, taxonomy suggestion and taxonomy endpoints [S3]. Returned fields include `product_name`, `brands`, `quantity`, `categories_tags`, `ingredients`, `allergens`, `nutriments`, `packaging`, `expiration_date`, `code` [S3]; also Nutri-Score, NOVA, Eco-Score, labels, countries [S1]. The `packaging` field is backed by taxonomies for packaging (shape, material, recycling), e.g. `packaging_materials`, `shape=box` [S3, S16]; my expectation is that it is empty for a large share of products [E].
- Rate limits: 15 req/min per IP for product reads, 10 req/min for searches; bans possible; usage rule "1 API call = 1 real scan by a user"; scraping via the API is blocked, bulk data available as dumps instead [S2, S4].
- Dumps: MongoDB nightly with 14 delta exports; JSONL (about 7 GB gz, 43 GB unpacked); Parquet (about 8 GB, on Hugging Face); CSV about 0.9 GB gz / 9 GB unpacked; product images CC-BY-SA and via AWS Open Data [S2, S4].
- Licence: database ODbL (attribution, share-alike for the database), contents DbCL, images CC-BY-SA [S2]. For AutoKitchen: attribute; share-alike applies to derived databases, not to the machine software as such; if we improve records (photos, corrections) we push them back to OFF via the API with the user's consent, which also improves our own coverage.
- **Architecture:** ship a **local mirror** of German (and adjacent EU country) products, reduced to the needed fields (about 300 k rows, order of 100-300 MB in SQLite [E]), refreshed weekly from the delta exports; on a miss, do a live call (which is compliant: it is one call per real scan; a household scans 40 items/week); on a second miss go to the next source.

### 6.2 Other sources

| Source | Content | Access, price | Comment |
|--------|---------|---------------|---------|
| GS1 GEPIR | maps a GTIN prefix to the company owning it; no product attributes | free, rate-limited queries [E] | only useful to obtain a brand hint |
| Verified by GS1 | GS1's registry of basic product attributes for GTINs (brand, description, net content, image) | API for subscribers [E] | coverage depends on brand-owner registration |
| GDSN / GS1 Germany data pool | detailed trade data (dimensions, weights, packaging) | for trade partners only [E] | not accessible to a consumer product without a partnership; a business-deal item |
| EAN-Search.org | very large EAN database (German operator) | trial EUR 1 for 100 queries, then EUR 9/month; 5,000 queries/month EUR 19/month [S21] | name, category, issuing country; good German coverage of names, weak on ingredients [E] |
| Barcode Lookup | product names, images, US-centred | USD 99/month for 5,000 calls up to USD 949/month for 500k [S21] | expensive for our volume; US-centred |
| Edamam Food Database | nutrition, UPC, NLP | USD 14/month basic 100k calls, USD 69, USD 299 plans [S21] | US/EN focus |
| Spoonacular | recipes, ingredient DB, products | free 50 points/day; USD 29, 79, 149/month [S21] | recipe-oriented; product coverage US |
| FoodRepo | Swiss open product DB | open [E] | Swiss items mostly |
| USDA FoodData Central | nutrient data, US branded foods | free, CC0, 1,000 requests/h with a key [S21] | good for generic ingredient nutrition, weak for German brands |
| Retailer data | Rewe, Edeka, Aldi, Lidl webshops | no public API [E] | scraping is fragile and contractually risky; but a retailer partnership or an e-receipt feed would improve coverage |

### 6.3 From product to generic ingredient

Recipes need "ingredient" IDs (e.g. `flour_wheat_405`, `tomato_chopped_canned`), not GTINs.

- **BLS 4.0** (Bundeslebensmittelschlüssel, Max Rubner-Institut): free since 16 December 2025, CC BY 4.0, about 7,140 foods, 138 nutrients [S21]. Use as the German ingredient and nutrition anchor: each internal ingredient carries a BLS code where possible.
- **FoodOn**: open food ontology with raw ingredient, process (packaging, cooking, preservation) and product-type facets; `has ingredient` and `has defining ingredient` properties [S21]. Useful as an interlingua and for cross-mapping (OFF taxonomy, USDA FDC, BLS), not as the run-time key.
- **OFF categories taxonomy** (`en:wheat-flours`, `en:canned-tomatoes`): multi-parent hierarchy per product; walk up from the most specific tag until a mapped internal ingredient is found.
- **Internal ingredient table** (about 800-1,500 entries suffice for 95 % of German home cooking [E, check against R2 corpus]) with: id, German and English name, BLS code, FoodOn ID, OFF category tags mapped, typical bulk density (flour 0.55-0.60 kg/L, sugar 0.85, rice 0.85, short pasta 0.40-0.45, oats 0.35, salt 1.2, lentils 0.8 [E]), decant policy (D/S/P), open shelf life, allergen tags, dosing class.
- Mapping pipeline: (1) direct GTIN cache; (2) OFF categories to internal ID; (3) LLM with a closed list: input name, brands, categories, ingredients text; output ID plus confidence; (4) if confidence is below a threshold or the class is high-risk (allergens), ask in the app; save the confirmed mapping keyed by GTIN.
- Composite products (ready sauces, spice mixes) map to "prepared product" IDs with the ingredient list attached (allergens).

### 6.4 Fallback when unknown

1. Second DB (EAN-Search). 2. Photo of front and back label, LLM extracts name, quantity, ingredients, allergens. 3. Ask the user in the app (photo already attached, three options). 4. Store "unknown, treat conservatively": route STOW, no decant, allergens "unknown: warn".
The quantity is the essential field: if unknown, take the measured gross minus estimated tare and confirm.

### 6.5 Verification by weighing

Weigh gross before and empty pack after opening: content = gross - empty; compare with declared net (`quantity`, `product_quantity`) and flag deviations above 5 %. This detects wrong DB entries, size changes ("shrinkflation"), and lets the ledger deduct residue. Weigh the storage box on a load cell (box under the funnel) to cross-check.

---

## 7. Funnel and filling

### 7.1 Bridging and flow

- Cohesive powders (flour, cocoa, powdered sugar, brown sugar) arch and rat-hole in funnels; free-flowing granules (rice, sugar, lentils, pasta) do not. Hopper theory (Jenike): mass flow requires steep, smooth walls and an outlet larger than the arching diameter; for flour the outlet should be at least 100-150 mm and the wall half-angle from vertical 15-20° in polished stainless [E; not verified in this session].
- **Design:** funnel as a steep inverted cone (wall angle at least 65° from horizontal for powders), 316L electropolished (Ra below 0.8 um), outlet 120-150 mm or a slot, interchangeable insert; a low-amplitude vibrator (eccentric motor or piezo, 50-100 Hz) on the funnel, an air knock or a tapping solenoid; compressed-air purge for stubborn residue.
- **Fill height:** the box is docked against the funnel with a silicone gasket, so material does not fall into an open space (dust).

### 7.2 Dust

- A 1 kg flour bag dumped from 30 cm produces a cloud; house-scale quantities are not an ATEX zone, but flour dust is combustible (St 1 class: Kst around 50-100 bar·m/s, minimum ignition energy tens of mJ) [E; verify]. Use grounded stainless parts and no exposed brushed motors or heaters in the dust zone; avoid static build-up on plastic (PP funnels) by not using them in the powder path.
- **Measures:** sealed docking of funnel and box, an air outlet with a HEPA or bag filter at a low flow (about 20-50 m³/h) so the box displaces air through the filter, slow pack tilting so material pours rather than drops, and a fine spray-free wipe (air knife) before undocking.

### 7.3 Cleaning between products

- **Allergen cross-contact:** the 14 EU allergens (gluten, egg, milk, nuts, peanut, soy, sesame, celery, mustard, lupin, fish, crustaceans, molluscs, sulphites) are read from the DB record and the machine knows the previous product's allergens; wash the funnel after any product that contains an allergen before the next product that does not. Practical rule: **wash after every product** (rotary spray nozzle, 60-70 °C water plus detergent, 60-90 s), then hot air dry until dry (wet flour paste is the worst case; never load a dry powder into a wet funnel). A dry pre-blow, then wet, then dry cycle costs about 2-3 minutes per pack; acceptable for 10 packs a week. Validation: ATP swab and allergen ELISA tests at the prototype stage (R6).
- **Raw meat:** never via the dry funnel: STOW route, opened at the JIT cell in the "raw lane" with its own tools and hot wash (section 3.4). A separate funnel for wet/liquid products is also worth having: dry funnel A, wet funnel B (liquids need a spout, not a wide funnel).
- **Fresh produce:** never through the funnel.

### 7.4 Weighing what was filled

Load cell under the box (0.1 g resolution, capacity 5 kg per box [E]); weigh box before and after; also weigh the pack before and empty after (section 6.5). Two independent weights give a per-fill residual check, feed the inventory ledger, and drive the "pack not fully emptied: shake again" loop.

### 7.5 FIFO, new box vs top-up

Rules:
- **Default: a new box per pack.** Simple and traceable; small boxes make this economical.
- **Top-up allowed only if:** same GTIN or same ingredient ID and the same allergen profile; the box is at most 60 % full; the older stock's MHD is within 60 days of the new one's [E]; ambient staple (flour, rice, sugar, salt, pasta), never perishables, never after 30+ days in the box (risk of stale stock at the bottom and pantry-pest carry-over).
- **Box carries the earliest MHD** of its contents and a "mixed" flag; the box's date is used for planning.
- **Dispensing physics:** boxes are emptied by tilting/pouring from the top by the preparation stage; new material poured on top would then be used first (LIFO). If FIFO matters, top-up is disallowed, or the boxes have bottom outlets (mass flow, first in first out). Given the box standard is open, default no top-up; the app suggests consolidation when two half-empty boxes hold the same GTIN.
- **Pests:** a new pack can carry grain moths; a sealed new box protects older stock.

---

## 8. Packaging waste

### 8.1 Amounts

- German households produced about 68 kg packaging waste per capita per year in 2018 (light packaging 30 kg, glass 22 kg, paper/cardboard 16 kg) [S18]; total packaging waste (all sectors) was 215 kg/capita in 2023, 227 kg in 2022, private end consumers about 47 % of the total [S18]. Recycling quotas 2023: glass 80.6 %, plastic 52.2 %, paper 86.6 % [S18].
- Machine-ingested food only: my estimate for the model shop of section 1.1 is **about 1.1 kg and 20 L per week** uncompacted [E]:

| Stream | Content | Mass/week | Volume/week (uncompacted) |
|--------|---------|----------:|--------------------------:|
| LVP (light packaging: plastics, composites, cartons, tinplate, aluminium, metal lids) | bags, tubs, tray and film, cartons, cans, lids | about 0.4 kg | about 14 L |
| Paper/cardboard | paper bags, cereal boxes, egg cartons | about 0.1 kg | about 3 L |
| Glass | 3 jars and bottles | about 0.6 kg | about 2 L |
| Residual waste | greasy meat trays and film, soiled foil, butter wrap | about 0.1 kg | about 1-2 L |

### 8.2 Sorting

- In Germany (Gelber Sack / Wertstofftonne for LVP, blue Papiertonne, glass containers by colour, residual bin), **empty is enough: "spoon-clean"**, no rinsing needed [E, UBA guidance not fetched]. Cartons (Getränkekartons) go into LVP, not paper. Jar lids go into LVP; the jar into glass.
- **Deposit (Pfand)** on single-use PET bottles and cans is EUR 0.25, since 2024 including milk and milk drinks in single-use plastic bottles; return rate almost 99 % [S19]. Deposit containers must not be cut or crushed by the machine (the reverse vending machine needs the barcode and shape intact): route them to a "Pfand return" bin or leave them with the user; PET milk bottles thus prefer the STOW route (uncap, dose, re-cap).
- Returnable (Mehrweg) jars and bottles are washed and returned; treat like Pfand: do not damage.
- **Automatic sorting** in the machine by class (section 1.2) plus a camera check is sufficient: class "paper bag" goes to paper, "can" to LVP, "jar" to glass, "meat tray" to residual. A glass colour sort into white / coloured is possible with a colour camera; simplest is a single glass bin and the user sorts at the bottle bank [E].

### 8.3 Compaction, rinsing, storage and odour

- Compaction: a small platen press at 3-4:1 for LVP and paper (flattened cartons), not for glass or deposit packs [E]. Cans are crushed only by a magnet-free press; a can crusher is not needed at 2-3 cans/week.
- Rinsing: after emptying, a 2-3 s hot-water jet inside the pack (cans, jars, tubs, cartons) prevents odour and fly attraction; at 0.2 L per pack and 25 packs/week that is 5 L/week of water to waste [E]. Packs with a wet or fatty residue (meat trays, film) go to a small sealed residual bin, not into the recycling stream.
- Storage: 4 lidded bins, 30 L (LVP), 15 L (paper), 10 L (glass), 5 L (residual) at the front-bottom of the ingestion module (about 400 x 300 x 400 mm), with a carbon filter in the lid, fill-level sensor (ToF), a flap that closes after each drop, and a bag-in-bin system so that the human lifts out the bag. Weekly emptying is realistic (20 L uncompacted plus 60 % free volume).
- **The human removes it:** the display shows "bin full" and the bins pull out at knee height; the bag is closed and carried to the outdoor bins. This is the one manual step that the brief allows because it cannot be eliminated.

---

## 9. Alternative supply models

- **Grocery delivery** (Rewe Lieferservice, Picnic, Flink, Edeka24, Amazon Fresh) [E]: retailers publish no public APIs to consumers. An order confirmation or e-receipt (Rewe eBon, Lidl Plus) contains item names but not EANs [E]. Value: the order list gives an "expected items" set to pre-match scans and to pre-plan meals; Picnic's reusable totes cut multi-pack waste. It does not remove packaging. Recommendation: design an inventory import interface (`expected_items` with name, quantity, optional GTIN) but not depend on it.
- **Standardised refill containers**: retailers with refill or Pfand-jar systems (Loop, "Unverpackt" shops, some Pfand-jars on supermarket shelves) [E]: if the packaging is a machine-standard box, ingestion disappears (scan the QR on the box; the transport system stores it). This is the endgame for the dry-goods class but needs a supplier ecosystem. Recommendation: make the storage box the reference container and offer an optional "box exchange" concept (delivery of pre-filled, RFID-tagged standard boxes) as a future business model rather than a design constraint.
- **Meal kits** (HelloFresh, Marley Spoon) [E]: pre-portioned ingredients in tiny bags for a single recipe. For AutoKitchen this multiplies packaging count per kg by about 10 (10-50 g sachets) and defeats stock-keeping; not recommended as a primary model, but a "meal-kit mode" (open the whole kit bag by hand, cook immediately) is a cheap add-on: no ingestion required.

---

## 10. Recommendation

### 10.1 Common architecture

```
  [input: lane / magazine (A)  |  scanner window + funnel (B)]
        |
  scan + weigh + identify + date OCR (5.7)     <- shared by A and B
        |
  route:  DECANT lane  ---- dry goods ---->  slit-and-shake (A) / user pours (B)
                                             -> docked funnel -> box on load cell
          STOW lane    ---- rigid, wet, perishable ---> surface rinse (rigid) ->
                                             carrier -> transport -> storage (ambient/cold)
          MANUAL lane  ---- produce, butter, eggs, bakery ---> user places in bin/drawer;
                                             machine records by photo + weight
        |
  JIT opening cell (shared with preparation): can/jar/bottle/carton/tray/tube/tub
        |
  packaging streams: LVP / paper / glass / residual bins; deposit items to return bin
```

### 10.2 Version A (automatic) scope

| Phase | Classes handled | Notes |
|-------|-----------------|-------|
| A-1 (MVP) | **D:** 1, 2 (dry), 3, 4, 19-sachet (about 22 % of items, 30 % of mass). **S:** 5, 6, 7, 8 handled by scan, weigh, rinse and stow only (no opening at ingestion). | single-file lane or pocketed magazine; scanner cell; slit-and-shake station; docked funnel; wash cabinet; JIT opening cell for cans, jars, bottles, cartons delivered with the preparation module |
| A-2 | **S:** 9 (tubs), 10-11 (MAP and vacuum, raw lane), 18 (tubes), frozen bags, 16-17; D: 14 (net bags) | hot-wire cutter; raw-lane hygiene concept; cold input bin |
| A-3 (stretch) | bin picking from a jumbled container; ring-pull automation for plain cans; GS1 2D date read; ultrasonic cutter | |
| Out of scope | butter unwrapping (12), egg cartons (13, P only), loose produce (15), bakery, snacks, ready meals, multi-pack film (user removes) | user places into the manual lane |

Interfaces to freeze with A1: pose station geometry and pose tolerance; carrier and "puck" definition for sealed packs; the JIT opening cell location and the transport handover for pack instances; funnel-to-box docking (box lid, gasket, mouth diameter); weight station resolution; the four packaging bins.

### 10.3 Version B (manual) scope

| Component | Content |
|-----------|---------|
| Scanner | fixed 2D imager window or handheld; display prompts product and expected mass |
| Decant lane | docked funnel with vibrator, dust extraction, load cell; user opens the pack and pours (dry goods, liquids into a wet funnel, frozen veg into a freezer box path) |
| Stow lane | user places the sealed pack into a carrier (rigid, wet, perishable items) after scanning; the machine stows it, opens JIT |
| Manual lane | produce, eggs, butter: photograph plus weigh, user places into the bin |
| Waste | user keeps the packaging; optional 4-bin sorter under the counter |
| Not needed | picking, cutting, blade wash, bin-picking vision |

Version B is A minus the picker and cutter: the same three lanes, the same database, the same funnel. This is the recommended first build (lowest risk, gives real data on packs, dates, DB coverage and weight verification). Version A adds a single-file lane, arm/gantry, slit-and-shake and wash cabinet on top.

### 10.4 Which package classes each handles

| Class | A-1 | A-2 | B |
|-------|:---:|:---:|:-:|
| 1 Paper bag | D | D | D (user pours) |
| 2 Pillow bag dry | D | D | D |
| 2 Frozen bag | stow | D/S | D or stow |
| 3 Stand-up pouch | D | D | D |
| 4 Box + inner bag | D | D | D |
| 5 Carton | stow | stow | stow (JIT open) |
| 6 Can | stow | stow | stow |
| 7 Jar | stow | stow | stow |
| 8 Bottle | stow | stow | stow |
| 9 Tub | manual | stow | stow |
| 10 MAP tray | manual | stow (raw lane) | stow |
| 11 Vacuum pack | manual | stow (raw lane) | stow |
| 12 Butter | manual | manual | manual |
| 13 Eggs | manual | stow as P | stow as P |
| 14 Net bag | manual | D | user pours |
| 15-17 produce | manual | manual (17: stow) | manual |
| 18 Tube | manual | stow | stow |
| 19 Spice jar | stow | stow | stow |
| 20 Multi-pack | user removes | user removes | user removes |

---

## 11. Open issues

1. **Real weekly-shop composition** (item and mass shares in section 1.2 are estimates): photograph and count 5-10 real receipts and baskets from Rewe, Edeka, Aldi and Lidl; recompute the automatable fractions.
2. **OFF German coverage and field quality**: test 200-300 EANs from real shops for hit rate, quantity, ingredients, allergens, packaging. Decide whether the EAN-Search subscription (EUR 9-19/month) is needed.
3. **Torque, peel and cut forces** in section 3 marked [E]: build a test rig (load cell plus torque sensor) and measure 30 jars, 20 bottles, 20 cartons, 20 foils, 20 bags from real packs. The Food Protection Trends article on removal torque could not be parsed in this session (PDF), nor could a ResearchGate torque paper.
4. **Funnel design numbers** (outlet diameter, wall angle for flour, vibrator specification, dust extraction flow) need a Jenike-style flow test with flour, cocoa, powdered sugar; and a dust explosion check (Kst, MIE) with a safety engineer.
5. **Decision A1: one opening cell or two?** Shared cell reachable from ingestion and preparation via the transport system, or one at each place. Needs the transport module's interface (D3) and the storage carrier definition (R3, D1).
6. **Carrier / puck standard for sealed packs** in the storage grid: box dimensions unknown at this stage (R3); slot budget in section 2.5 item 7 must be confirmed.
7. **Cold-chain in Version A input:** chilled input drawer vs user-sorts-at-loading; maximum unrefrigerated time (2 h rule [E]).
8. **Verbrauchsdatum enforcement:** legal and UX wording; what the machine does when the date cannot be read.
9. **Ring-pull and plain can opening** by a machine (side-cut vs hooked tab): which subset of German cans has a ring-pull? Estimate: majority [E].
10. **Metal and film fragment detection** at the funnel: whether a low-cost inductive coil and camera are sufficient.
11. **Deposit items:** policy when the user drops a Pfand bottle or can into the input; label reading for the deposit logo.
12. **GS1 2D rollout in Germany:** track dual marking and the data content (does it carry the best-before date?); choose a scanner that supports GS1 Digital Link parsing now.
13. **LLM/vision privacy and cost**: labels photographed and sent to a cloud LLM; local fallback model; cost per unknown item.
14. **Bulk density table** for the box-size selection and mass-to-volume conversion (values in 6.3 are estimates).
15. **Regulatory:** EU 1935/2004 and 10/2011 (food contact) for funnel, blades and grippers; R6 to confirm materials and cleaning validation (allergen ELISA/ATP).

## 12. Risks

| # | Risk | Likelihood | Impact | Mitigation |
|---|------|:----------:|:------:|------------|
| 1 | Bin picking of deformable bags, nets and slippery cups fails too often (75-80 % on deformable items [S16]) | high | high | single-file lane / magazine baseline; fallback to the manual lane; pick retries; bin picking only as A-3 |
| 2 | Packaging fragments (film, paper fibres, blade chips) in food | medium | high | slit-not-sever geometry, hook or hot-wire cutters, sieve, camera, empty-pack weigh, user prompt |
| 3 | Cross-contamination from blade or funnel (raw meat, allergens, Listeria on outer surfaces) | medium | high | STOW route for raw items, raw lane, wash after every pack, surface rinse, single-use blade option, ATP/ELISA validation |
| 4 | Decanting shelf-life-critical foods causes waste or unsafe food | medium (if rules are ignored) | high | route rules by class; planner aware of opened-clock; Verbrauchsdatum hard stop |
| 5 | Wrong or missing product data (wrong quantity, missing allergens) leads to a wrong recipe or an allergen incident | medium | high | weight cross-check, multiple sources, user confirmation for allergen-relevant or unknown items, conservative default |
| 6 | Barcode not found on wrinkled, curved or shiny packs; date OCR unreliable | high | medium | multi-camera rotation, LLM label read, user assist, class defaults with confirmation |
| 7 | Flour and other cohesive powders bridge in the funnel or dust and contaminate the machine | high | medium | steep polished funnel, vibrator, docked box, extraction, wash and dry cycle |
| 8 | Glass jars break in the gripper or from vacuum lid piercing (glass shards in food) | medium | high | force-limited clamp, lever vacuum break instead of piercing the lid, camera check of jar, discard-and-alert routine |
| 9 | Complexity and cost of the STOW / JIT concept (carriers, JIT opening cell, ledger) | high | medium | stage: build B first, then A-1; make the JIT cell a separate deliverable with clear interfaces |
| 10 | Cold chain broken by dwell in the input container | medium | medium | cooled input drawer, timer and alarm, user sorts chilled items first |
| 11 | Packaging change (new formats, GS1 2D, plastic-to-paper switches, DPP) breaks assumptions | medium | medium | keep the class table data-driven; log unknown pack shapes; update via OTA |
| 12 | OFF terms change or rate limits (15/10 req/min) block the machine | low | medium | local mirror plus rare live calls; alternative source |
| 13 | Odour, flies or mould in waste bins | medium | low | rinse, closed bins, carbon filter, weekly removal |
| 14 | Poor search coverage in this research (search budget exhausted, many [E] values) | certain | medium | treat all [E] numbers as hypotheses; test-rig measurements before design freeze |

## 13. Sources

Numbers refer to tags used above. All URLs were returned by search or fetched in this research; items not opened in full are noted.

- S1 Open Food Facts, Germany page (282,974 DE products) and homepage (4.78 M products): https://world.openfoodfacts.org/country/en:germany , https://world.openfoodfacts.org/
- S2 Open Food Facts data and licence page (ODbL, DbCL, CC-BY-SA images, dump formats): https://world.openfoodfacts.org/data (fetched)
- S3 Open Food Facts API cheat sheet and API introduction: https://openfoodfacts.github.io/openfoodfacts-server/api/ref-cheatsheet/ (fetched) , https://openfoodfacts.github.io/openfoodfacts-server/api/ , https://openfoodfacts.github.io/openfoodfacts-server/api/tutorial-off-api/
- S4 Open Food Facts terms of use and rate-limit issue: https://world.openfoodfacts.org/terms-of-use , https://github.com/openfoodfacts/openfoodfacts-server/issues/8818 (limits quoted from search summaries)
- S5 Open Food Facts blog, Smantry in Germany: https://blog.openfoodfacts.org/en/news/using-open-food-facts-as-a-stock-tracking-app-in-germany (fetched)
- S6 GS1 Sunrise 2027: https://www.barcode.graphics/gs1-digital-link-sunrise-2027-explained/ , https://www.resourcelabel.com/blog/2025/08/08/future-proofing-your-packaging/ , https://ref.gs1.org/sme-guidance/solution-provider-2d-readiness/ , https://www.videojet.com/us/homepage/resources/learn/gs1-sunrise-2027.html (search summaries)
- S7 GS1 variable measure prefixes: https://www.gs1.org/docs/barcodes/SummaryOfGS1MOPrefixes20-29.pdf , https://www.gs1uk.org/knowledge-hub/barcodes/how-to-barcode-variable-measure-items , https://gs1.se/en/guides/how-to-guides/barcode-label-items-of-varying-weight/ , https://www.gs1belu.org/en/variable-weight-items (search summaries; two pages returned HTTP 403 on fetch)
- S8 EAN-13 structure: https://en.wikipedia.org/wiki/International_Article_Number (fetched)
- S9 Jar torque: https://www.foodprotection.org/members/fpt-archive-articles/2024-07-new-aluminum-lug-closure-reduces-removal-torque-while-ensuring-hermetic-seals-in-glass-jars/ (numbers from search summary; PDF not parsed) , https://www.researchgate.net/publication/11529907_The_Twisting_Force_of_Aged_Consumers_When_Opening_a_Jar (HTTP 403)
- S10 PET 28 mm caps (no torque data): https://www.pelliconi.com/product/plastic-caps-28mm-1881/ , https://bericap.com/product/hc-ev-28-27-pco-1881/
- S11 Bag opening and emptying: https://www.palamaticprocess.com/en-us/bulk-handling-equipment/robotize/sackbot-sb-100 (fetched) , https://www.tinsleycompany.com/automatic-bag-opener-and-emptying-system/ (fetched) , https://www.laborsave.com/ , https://www.powderbulksolids.com/packaging-systems/automated-sack-emptying-systems-an-alternative-to-bulk-supply
- S12 Can opening machines: https://morrison-chs.com/solutions/can-openers/ , https://www.profoodworld.com/processing-equipment/processing-instrumentation/product/22933370/morrison-container-handling-solutions-automated-industrial-can-opener-line , https://www.dcnorris.com/systems/industrial-can-opening-crushing/autocan-1000-automatic-can-opener-crusher-system/
- S13 Ultrasonic cutting: https://www.telsonic.com/en/cutting-with-ultrasonics/portioning-foodcutting-ultrasonics/ , https://www.herrmannultraschall.com/en/branch-solutions/food/food-cutting-with-ultrasonics , https://www.dukane.com/products/ultrasonic-welding-products/ultrasonic-cutting-solutions/ultrasonic-food-cutting-products , https://hackaday.com/2025/03/21/high-frequency-food-better-cutting-with-ultrasonics/ (search summaries; fetches returned 403)
- S14 Laser scoring and cutting of packaging film: https://www.pffc-online.com/die-cut/2736-lasers-digital-converting , https://luxinar.com/en/laser-cutting-packaging-industry/ , https://www.parksideflex.com/technology/laser-scribing-with-parkscribe/
- S15 Tetra Pak structure and opening: https://www.diva-portal.org/smash/get/diva2:542841/fulltext02 (fetch failed) , https://www.tetrapak.com/en-us/solutions/packaging/packages/aseptic-packages/tetra-brik-aseptic
- S16 Picking: https://www.berkshiregrey.com/solutions/robotic-pick/ , https://www.therobotreport.com/robot-grippers-advance/ , https://claru.ai/training-data/warehouse-automation , https://www.science.org/doi/10.1126/scirobotics.aau4984 , https://arxiv.org/pdf/2103.14127 (Contact-GraspNet) , https://arxiv.org/pdf/1703.09312 (Dex-Net 2.0) , https://www.mordorintelligence.com/industry-reports/piece-picking-robots-market
- S17 Cameras: https://store.realsenseai.com/buy-intel-realsense-depth-camera-d405.html , https://store.intelrealsense.com/buy-intel-realsense-depth-camera-d435.html , https://www.therobotreport.com/intel-spins-out-realsense-as-standalone-company/ , https://shop.luxonis.com/collections/oak-cameras-col
- S18 Packaging waste Germany: https://www.destatis.de/DE/Presse/Pressemitteilungen/2020/03/PD20_103_321.html , https://www.bvse.de/recycling/recycling-nachrichten/12283-215-kilogramm-verpackungs-muell-pro-kopf-fielen-2023-in-deutschland-an.html , https://www.umweltbundesamt.de/daten/ressourcen-abfall/verwertung-entsorgung-ausgewaehlter-abfallarten/verpackungsabfaelle
- S19 Pfand: https://www.verbraucherzentrale-brandenburg.de/pressemeldungen/lebensmittel/keine-25-cent-in-den-gelben-sack-werfen-milchgetraenke-ab-2024-pfandpflichtig-90899 , https://www.verbraucherzentrale-bawue.de/wissen/lebensmittel/lebensmittelproduktion/pfand-welche-regeln-gibts-bei-einweg-und-mehrweg-92183 , https://www.ing.de/wissen/pfandpflicht/ , https://www.bvse.de/recycling/recycling-nachrichten/10373-ab-2024-gilt-pfandpflicht-auch-fuer-milch-und-milcherzeugnisse-in-flaschen-aus-einwegplastik.html
- S20 Shelf life: https://www.verbraucherzentrale.de/wissen/lebensmittel/auswaehlen-zubereiten-aufbewahren/konserven-alles-zu-haltbarkeit-und-lagerung-58933 (fetched) , https://www.verbraucherzentrale.de/wissen/lebensmittel/auswaehlen-zubereiten-aufbewahren/milch-alles-wichtige-zu-haltbarkeit-und-lagerung-58934 (fetched) , https://www.verbraucherzentrale.bayern/faq/kann-man-reste-in-konservendosen-aufbewahren-46597 , https://www.dairy.com.au/you-ask-we-answer/how-long-does-uht-long-life-milk-last-once-opened , https://www.sciencedirect.com/science/article/abs/pii/S2214289422000722 , https://la-va.com/en/magazin/what-is-the-shelf-life-of-vacuum-packed-meat/ , https://www.beefresearch.org/resources/product-quality/fact-sheets/beef-shelf-life , https://meatupdate.csiro.au/Storage-Life-of-Meat.pdf (not parsed)
- S21 Product data and ontologies: https://www.ean-search.org/ean-api-intro.html , https://www.barcodelookup.com/api , https://developer.edamam.com/food-database-api , https://spoonacular.com/food-api/pricing , https://fdc.nal.usda.gov/api-spec/fdc_api.html , https://blsdb.de/download , https://www.openagrar.de/receive/openagrar_mods_00112643 , https://agrolab.com/en/news/food-news/6105-bls-datenbank-radar-01-26-en.html , https://www.nature.com/articles/s41538-018-0032-6 (FoodOn) , https://foodon.org/design/foodon-relations/
- S22 German food spending: https://www.bzfe.de/presse/pressemeldungen-archiv/zahlen-zum-deutschen-einkaufskorb , https://www.ernaehrungsindustrie.de/335-euro-pro-monat-so-sieht-der-deutsche-einkaufskorb-aus/
- S23 Packaging materials: https://de.statista.com/statistik/daten/studie/1535614/umfrage/haeufigste-hauptbestandteile-von-lebensmittelgetraenkeverpackungen-deutschland/
- S24 Camera-based multi-item checkout: https://retail-optimiser.de/en/ncr-and-toshiba-present-scanless-self-checkouts-for-small-baskets/ , https://research.aimultiple.com/self-checkout/
- Barcode handheld prices (Logiscenter listing): https://www.logiscenter.eu/readers
