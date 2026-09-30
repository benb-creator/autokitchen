# R6 - Hygiene and Automatic Cleaning

Research document R6 for the AutoKitchen project. Cleaning is the customer's major concern (BRIEF.md,
"Cleaning": *"The human will not clean anything"*). This document constrains every module. It ends with a
checklist of design rules (section 11), "Open issues" and "Risks".

## 0. How to read this document

Evidence tags used throughout:

| Tag | Meaning |
|-----|---------|
| **[S]** | Taken from a source that was retrieved during this research; URL in section 13 |
| **[K]** | General engineering / regulatory knowledge of the author, not re-verified in this session; verify before relying on it |
| **[E]** | Estimate or calculation by the author (assumptions stated); treat as design starting point, to be measured on a prototype |

Limits of this research (be aware): the primary EHEDG documents (Doc 8, 13, 44) and the EN/ISO/NSF/3-A
standards are paywalled or were unparseable PDFs, so the design criteria in section 1 come from secondary
summaries that quote them, plus author knowledge. The web-search budget was exhausted before the
commercial-dishwasher standards (NSF/ANSI 3, DIN 10510/SPEC 10534), cleaning-verification literature and
allergen-cleaning literature could be searched; those parts are mostly [K]/[E] and are listed in "Open issues".

---

## 1. Hygienic design principles and what they mean for the mechanical designer

### 1.1 The standards landscape

| Standard / guideline | What it is | Relevance to AutoKitchen |
|---|---|---|
| **EHEDG Doc 8** (Hygienic Design Principles; 2nd ed. 2004 "Hygienic equipment design criteria", 3rd ed. 2018, new edition 2025) | The base document. Prevent microbial contamination; influenced EN 1672-2 and EN ISO 14159 [S] | Primary source for all design rules below |
| **EHEDG Doc 13** (Hygienic design of equipment for open processing; 3rd ed. June 2024 retitled for *wet-cleaned open food-processing environments*) | Design criteria for open equipment: joints, drainability, covers, shafts/couplings, bearings, belts, cladding, installation [S] | Directly applicable: our prep/cook cell is open equipment that is wet-cleaned |
| **EHEDG Doc 44** | Per search results a *building/factory-level* hygienic design guideline ([S] secondary: "specific building design criteria"; author recollection: "Hygienic design principles for food factories") | Applies to the room/kitchen, not to the machine; useful for how the machine meets floor, wall and drain |
| EHEDG Doc 2, 32 | Cleanability test method; materials of construction [S] | A supplier's EHEDG test certificate is a shortcut for buying components |
| **EN 1672-2** (Food processing machinery - basic concepts - hygiene) and **EN ISO 14159** (Safety of machinery - hygiene requirements) | The EU machinery-directive route; define food area / splash area / non-food area [S] | Legal basis if the machine is placed on the EU market as machinery |
| **3-A Sanitary Standards** (US) | Same principles; Ra <= 0.8 um food contact [S] | Reference for components (US-sourced pumps, valves) |
| **NSF/ANSI 2** (Food equipment - design) and **NSF/ANSI 51** (Food equipment - materials) | US commercial foodservice equipment. NSF/ANSI 51 defines *food zone*, *splash zone*, *non-food zone*: material certified for food zone is fine everywhere, splash-zone material is not certified for food zone [S] | Source of the zoning vocabulary; NSF-listed parts can be bought for each zone |

Note on the zone names: EN 1672-2 uses *food area / splash area / non-food area*; NSF uses *food zone / splash
zone / non-food zone* [S]. This document uses **Zone F (food), Zone S (splash), Zone N (non-food)**.

### 1.2 Concrete criteria (numbers a designer can use)

| Topic | Criterion | Source |
|---|---|---|
| Surface roughness, food contact metal | **Ra <= 0.8 um** (3-A and EHEDG). Rougher is acceptable only if a cleanability test shows it works. Cold-rolled stainless sheet (2B) is typically Ra 0.2-0.5 um without polishing | [S] |
| Surface roughness, splash zone | No hard number in the standards found; author rule: Ra <= 1.6 um metal, and no coating that can flake | [E] |
| Surface roughness, plastics | As-moulded PP/PE/Tritan is typically Ra 0.1-0.6 um, meets 0.8 um. FDM printed parts are typically Ra 10-30 um and do not (section 4) | [K] |
| Internal corner radii | **>= 6 mm preferred, 3 mm absolute minimum**; corners <= 90 deg without radius are not allowed in food/splash area | [S] |
| Radius exception | Where a corner is a *sealing point* it must be sharp, with a small (~0.2 mm) break edge so the elastomer is not cut | [S] |
| Slope for self-draining | Horizontal surfaces must be avoided; surfaces slope to one side, **>= 3 deg** minimum | [S] |
| Drainability | All equipment interior and exterior must be *self-draining* (or drainable). A rim/ledge must not hold product; open-top rims rounded and sloped | [S] |
| Ledges, horizontal ribs | None in Zone F/S. Structural ribs go on the *outside* (non-food side) or run in the direction of flow | [S]/[K] |
| Gaps, crevices | No pockets or gaps between equipment and supports; clearance to walls/frame adequate for cleaning and inspection | [S] |
| Metal-to-metal contact (non-welded) in product area | Avoid. Use continuous welds or an elastomer seal on the product side | [S] |
| Welds | Continuous, smooth, flush (ground), on flat faces not in corners; TIG, pickled and passivated (finish to Ra <= 0.8 um) | [S]/[K] |
| Screw threads, bolt heads | Avoid in Zone F. If unavoidable, seal the crevice (hygienic fasteners with integral seal, domed/closed nuts, welded studs) | [S] |
| Holes | All blind holes/hollow tubes sealed by welding, gasket or cap; no open hollow sections | [S] |
| Seals, O-rings | Directly product-exposed O-rings only if compressed to a *flush static seal*; no crevices. Approved elastomers: EPDM, FKM, HNBR, NR, NBR, VMQ, FFKM | [S] |
| Dynamic seals | Reciprocating shafts: diaphragm or bellows. Rotating shafts: double seal with barrier liquid (industrial). For us: avoid shafts through the food wall (magnetic coupling or removable vessel with drive in base) | [S] |
| Dead legs (pipes) | Avoid stagnant branches. Industrial rule of thumb L <= 1.5 D for CIP pipe branches | [K] |
| Materials | Stainless AISI 304L / 316L (EN 1.4307/1.4404) for food contact; must be non-toxic, non-absorbent, corrosion-resistant, cleanable | [S] |
| Open vs closed equipment | *Closed* (CIP-able) equipment is cleaned without dismantling; *open* equipment is cleaned by wet-cleaning (spray/foam) or dismantled. EHEDG Doc 13 addresses the open, wet-cleaned case | [S] |

### 1.3 Zoning applied to AutoKitchen

| Zone | Definition (EN 1672-2 / NSF 51) | AutoKitchen items | Material rules | Cleaning method (must be stated per item) |
|---|---|---|---|---|
| **F - food** | Direct contact with food, or surfaces from which liquid/condensate can drip, drain or splash back onto food [S] | Interior of storage boxes and lids; dosers, funnels, chutes, ingestion funnel interior; pots, pans, bowls, blades, stirrers, scrapers, portion tools; plates and cutlery; cooking plate/vessel contact; gripper fingers if they touch food; **ceiling and hood underside above open food (condensate!)**; serving shelf | 1.4404 or food-contact polymers with EU 10/2011 / LFGB / FDA compliance; Ra <= 0.8 um; radii >= 3 (pref. 6) mm; no FDM | Removable and washed in the wash chamber at >= 70 deg C (section 2), or CIP with rinse and hot final rinse |
| **S - splash** | Routinely soiled by splashes, spills, steam, grease aerosol, but not intended food contact [S] | Prep/cook cell walls, floor, door; gantry/robot within ~1 m of food; carriage and gripper bodies; box exteriors; wash-chamber door and seal; hood; ingestion cutter housing; drip tray; waste chute; serving hatch | Stainless 1.4301 minimum (1.4404 near salt/steam/chlorine), NSF-51 splash-zone plastics, sealed printed parts only per section 4; IP65+ (IP69K near jets); no paint or powder-coat | In-place wash-down (nozzles, hot water, steam) each cooking session, deeper weekly; gripper and carriage on a wash station |
| **N - non-food** | Not exposed to food or splash, minor dust [S] | Frame, drive cabinets, electronics, fridge compressor, storage-grid rails (dry) | Any; powder-coat/paint ok; must be **pest-proof** (openings <= 5 mm) and dust-tight enclosures | Dust removal by service; no wet cleaning |

Rule: **a part's zone is decided by the worst thing that can reach it.** Steam and grease aerosol travel
(section 6.5); the cooking cell is Zone S for everything it contains and Zone F for the ceiling above open food.

### 1.4 Ten design rules distilled

1. Every wetted or food-exposed surface must be either **removable to the wash chamber** or **directly reachable by a spray/steam nozzle** (line of sight, no shadowing); a surface that neither can reach does not exist.
2. Smooth, continuous, crevice-free: welded stainless, formed with radius >= 6 mm (3 mm min.), Ra <= 0.8 um in Zone F.
3. Everything self-drains at >= 3 deg (5 deg recommended for viscous soils) to a defined drain point; no pockets, no flat ledges.
4. Fasteners, hinges, connectors leave no crevice in Zone F/S: welded, sealed or hygienic-design components.
5. Keep motors, electronics, cables, bearings and lubricants **outside** the wet zone; pass motion through a sealed wall (magnetic coupling, bellows, removable vessel with base drive).
6. Contact polymers only if certified (EU 10/2011, FDA) and only in shapes that are moulded/machined/cast smooth; no FDM in Zone F.
7. Unidirectional dirty -> clean flow: wash chamber is a **pass-through** with a dirty door and a clean door (section 9).
8. Nothing stays wet or damp for hours: pre-rinse within minutes, forced drying after wash (biofilm attaches in ~3 h, section 5.4).
9. Every seal and wear part is replaceable from the outside, visible, and listed as a service item with an interval.
10. Every cleaning step is sensed and logged (section 8) so a "cleaned" claim is backed by data.

---

## 2. Cleaning methods and parameters

### 2.1 Sinner's circle

Four factors that can compensate each other: **temperature, time, chemistry, mechanical action** (Herbert Sinner,
Henkel, 1959) [S]. Reduce one and the others must increase. Rules of thumb from the sources:

* Temperature accelerates chemical action (roughly a doubling of reaction rate per +10 K) and softens fat; but heat *hardens* protein soils (egg, milk), so the first rinse must be cool [S: Miele, Kaercher].
* Time: soak phases and longer programmes clearly improve results [S: Miele].
* In a dishwasher, low mechanical action is compensated by chemistry and time [S: Miele]; this is why a household dishwasher works with gentle spray arms and a 1-3 h programme. **We need to decide where we sit on that trade-off**: a robot kitchen with a 20-minute quick-wash requirement needs more mechanics (jets) and heat.

### 2.2 Water supply, heating and power: the hard physical limits

Constants: 1 L water needs **1.164 Wh per K** [E, physics]. Cold inlet assumed 12 deg C.

| Target | Energy per litre from 12 deg C | Comment |
|---|---|---|
| 40 deg C (protein-safe pre-wash) | 33 Wh | |
| 55 deg C (enzymatic wash) | 50 Wh | |
| 70 deg C | 68 Wh | |
| 75-80 deg C (sanitising rinse) | 73-79 Wh | |
| 85 deg C (commercial rinse) | 85 Wh | |

**Instantaneous heaters are unusable for the spray circuit.** A 3.5 kW electric instantaneous heater raises
flow Q (L/min) by dT = P / (0.0698 x Q) K [S formula, 4.18 kJ/kgK]: at +50 K it delivers **only ~1.0 L/min**
[E]. A spray circuit needs 20-60 L/min. The dishwasher solution is the right one: **fill 4-8 L once from the
mains, heat that volume in a sump with a 1.5-2.4 kW heater, and recirculate it with a pump** [K/E].

| Item | Calculation | Result |
|---|---|---|
| Heat 6 L sump from 12 to 55 deg C with 2 kW | 6 x 1.164 x 43 = 300 Wh | ~9 min |
| Heat 4 L to 75 deg C with 2 kW | 4 x 1.164 x 63 = 293 Wh | ~9 min |
| Hot buffer tank 10 L at 70 deg C (12 -> 70) | 10 x 1.164 x 58 = 675 Wh | ~14 min at 3 kW; standby loss with 50 mm insulation ~15-30 W [E] |
| Power circuit | 230 V x 16 A = 3.68 kW per circuit (Germany) [K] | The whole machine has, unless an extra circuit is installed, **one ~3.6 kW budget**: cooking (induction 2-3.6 kW), wash heater (2 kW), steam generator (2-3 kW) and fridge cannot all run at once; a **power manager** is mandatory [E] |

**Mains pressure and flow.** The 2.2-5 bar mains (BRIEF) is enough to *fill* and to run a few fixed jets, but
not enough for high flow:

* Household dishwashers accept 0.5-10 bar supply and need >= ~10 L/min [S: Bosch documentation], so filling 6 L takes < 1 minute.
* Orifice flow Q = Cd A sqrt(2 dp / rho): a **2 mm nozzle at 2 bar gives ~2.4 L/min and ~20 m/s** exit velocity; a 1.5 mm nozzle at 5 bar gives ~2.2 L/min at ~30 m/s (Cd = 0.65) [E].
* A DN15 house branch with 2.2 bar static will deliver perhaps 8-12 L/min at the appliance, i.e. **at most 3-4 such jets simultaneously**, once-through (wasteful) [E].
* Therefore: **mains for filling and final fresh-water rinse only; mechanical action comes from a recirculation pump.**
* A small 12/24 V diaphragm pump (5-8 bar, ~4 L/min, ~70 W; RV/marine type) allows a few jets at 5 bar from a sump [K/E]. A 230 V pressure-washer pump (~1.4 kW, 6-8 L/min at 100-130 bar) allows a robot-carried spot-cleaning lance but is a heavy, loud, aerosol-generating option [K].

Impact comparison of a 1 mm jet: at 2 bar ~0.3 MPa stagnation-equivalent, at 40 bar ~4.5 MPa (roughly 15-20x)
[E]. High-pressure jets remove baked-on starch in seconds; low-pressure sprays need minutes plus chemistry.

### 2.3 Spray-ball, rotating-jet and spray-arm cleaning (what is achievable)

| Device | Typical data | Source |
|---|---|---|
| Static spray ball (CIP) | 1-2.5 bar; flows from ~15 L/min for small balls up to >1000 L/min; cleaning diameter 1-6 m; suited to tanks up to ~2 m diameter; relies on **sheeting flow** down the wall rather than impact | [S] |
| Rotary spray ball / rotary jet head | Rotary spray heads for tanks up to ~4.5 m; industrial rotary jet cleaners 3-14 bar, 90-250 L/min, effective radius 1.8-2.5 m; TankJet 9B: 64 L/min max, up to 3.6 m tank diameter | [S] |
| CIP pipe flow | Fluid velocity **>= 1.5 m/s** in pipes to give turbulent scouring | [S] |
| Household dishwasher spray arms | Low pressure (well below 1 bar at the arm), rotating by reaction; **mechanics is low but flow is high** and the programme is long; 9.5 L (Bosch average) to 15-22 L per cycle | [S]/[E] |
| Industrial CIP sequence | pre-rinse, caustic circulation, intermediate rinse, acid wash, final rinse, hot-water/disinfectant circulation, air blow | [S] |

Scaling to our sizes (author estimates, assumption: film-flow wetting of ~2 L/min per 100 mm of vessel
circumference at ~25-30 L/min per metre is the industrial rule of thumb; small vessels overshoot, so use
impact):

* **Closed vessel Ø200 mm x 250 mm (~8 L), one rotary nozzle in the lid:** 8-15 L/min at 2-3 bar, 10 L sump, 10-15 min wash. Water ~13-15 L per CIP cycle [E].
* **Wash chamber 480 x 480 x 400 mm (~92 L free volume) with two rotating spray arms and a sump of 6-8 L:** recirculation 40-80 L/min at 0.3-0.8 bar from a household-type circulation pump (~40-100 W) [E].
* **Wash-down cell 800 x 500 x 600 mm (2.4 m2 interior) with 12-16 nozzles:** ~30-40 L/min at 2 bar, sump 10 L [E].

### 2.4 Other methods

| Method | Parameters and facts | Use for AutoKitchen |
|---|---|---|
| **Dishwasher-style wash chamber** | Household: wash 45-75 deg C, rinse 50-83 deg C; 15-22 L and 1-2 kWh per cycle; cycle 3-4 h normal, 30 min quick [S]. Commercial: wash 65-71 deg C, final rinse 82 deg C via booster heater (or chemical); <0.4 gal (1.5 L) per rack in efficient models; no drying phase, ambient air dry [S] | **Backbone** (section 9) |
| **Hot-water wash-down of the cell** | Recirculating sump + nozzles; sanitising needs surface temperature >= ~70 deg C for tens of seconds [K] | Splash-zone rinse (section 9.2) |
| **Steam** | 2 kW steam generator ~3 kg/h [S]; author physics: 0.73 kWh per kg incl. heating from 12 deg C, so 2 kW ~ 2.5-2.7 kg/h real; 3.3 kW commercial units exist [S]. Wall heating: 28 kg of 1.5 mm stainless cell surfaces from 25 to 75 deg C needs ~0.2 kWh = ~0.3 kg steam, i.e. ~8-15 min with losses [E]. Condensate carries soil to the drain; steam does not by itself remove baked soil, and needs an enclosed, vented cell | Sanitising step for closed chambers, gripper station, ingestion funnel; **not** as the primary cleaner |
| **Ultrasonic bath** | 40 kHz general purpose; 20-30 kHz stronger; 30-400 W/L in studies [S]. Cavitation reaches crevices, effective on grease/carbon in small parts. Needs immersion (5-10 L bath, ~300-500 W), degassing, 50-60 deg C bath. Erodes soft plastics/aluminium foil; FDM parts damp it | **Optional** module for cutters, graters, grippers and filters that have cavities; not for the base concept |
| **Hot-air drying** | 60-70 deg C air, 100-200 m3/h, 1-1.5 kW heater, 15-20 min [E]. Stainless flash-dries from a 75+ deg C final rinse; **plastics (PP, PE) have low heat capacity and stay wet without forced air**. Alternatives in household machines: condensation, heat exchange, zeolite [S] | Mandatory (mould/biofilm control) |
| **UV-C (254-280 nm)** | 3-4 log on stainless at ~6-8 mJ/cm2 for *E. coli*, *Salmonella*, *Listeria* on **clean** surfaces [S]; needs ~400 mJ/cm2 for 5 log on soiled stainless in one study [S]; **shadowing and organic soil strongly reduce efficacy** [S]; degrades many plastics and silicone over time [K]; eye/skin hazard - needs interlock | Adjunct only: dry, empty compartments (fridge, storage), cutting-blade parking. Never a substitute for washing |
| **Ozone (gas)** | Effective on odours/mould but toxic (occupational limit ~0.1 ppm [K]), attacks elastomers | **Not recommended** in an occupied kitchen. Ozonated water only in closed chambers, unstable [S] |
| **Electrolysed water (on-site HOCl, from salt + water)** | Slightly acidic EW: pH 5-6.5, 10-80 ppm HOCl; ~80x more active than hypochlorite ion; at 5 ppm no better than tap water; sanitiser limits <= 200 ppm available chlorine per FDA; **organic matter neutralises it, so it works only on cleaned surfaces** [S] | Optional for non-heatable surfaces (fridge interior, housing). Watch chloride corrosion on 1.4301 |
| **Pyrolysis (ovens)** | 400-500 deg C, door locked ~3 h, opens at ~316 deg C; **3-7 kWh per cycle**; smoke/fumes; oven soil turns to ash [S] | Applies to a baking oven only (D5). Not for anything else |
| **Catalytic coatings** | Ce/Cu/Mn oxide enamel oxidises grease at cooking temperature [S] | Oven wall liner only |
| **Pressure-washer lance carried by robot** | 100+ bar, 6-8 L/min, ~1.4 kW | Spot cleaning of stubborn soil in the cell; aerosol and splash; optional |

### 2.5 Reference wash programmes (starting point for D7)

**Programme P1 - full wash (vessels, tools, boxes, plates)**, all volumes and temperatures [E] unless noted:

| Step | Water | Temp | Time | Notes |
|---|---|---|---|---|
| 1 Pre-rinse | 3 L, fresh, drain | **<= 35-40 deg C** | 2 min | Cool: heat denatures protein and gelatinises starch on the soil [S: Miele]. Turbidity measured -> sets soil class |
| 2 Main wash | 6 L | 50-55 deg C | 12-18 min | Alkaline **enzymatic** detergent (protease + amylase) 3-4 g/L; enzymes operate at 45-55 deg C and are inactivated above ~60 deg C [S: 45 deg C, 23 min, protease removes 40% more egg yolk] |
| 3 Intermediate rinse | 3.5 L, drain | 45-50 deg C | 2 min | Conductivity/pH watched to find when the detergent is rinsed out |
| 4 Final rinse / sanitise | 4 L, fresh + rinse aid 0.2-0.5 mL/L | **>= 75 deg C for >= 3 min** (A0 ~ 57-60 s) | 3-4 min | A0 = sum of 10^((T-80)/10) x dt(s). A0 60 equals 80 deg C for 1 min or 70 deg C for 10 min (the Bosch HygienePlus level, 70 deg C for up to 10 min [S]) [K] |
| 5 Hot-air dry | - | 60-70 deg C air | 15-20 min | Exhaust humidity sensor ends the step |
| **Total** | **~17-20 L** | | **55-75 min** | Energy ~1.3 kWh (heating 0.75 kWh, drying 0.4, mass and losses 0.2) [E], consistent with 1-2 kWh household [S] |

**Programme P2 - quick reuse wash (mid-recipe)**: pre-rinse + 45-50 deg C wash + rinse, 20-25 min, no dry,
~10 L. Permitted only when the next use includes a >= 72 deg C heat step (cooking) and no allergen change.
**Programme P3 - deep/sanitise**: weekly, 80-85 deg C, chlorine-free alkaline, includes the chamber
itself and all nozzles. **Programme P4 - descale**: citric acid (1-2%), monthly or by conductivity/hardness
(section 2.7).

**Water and energy per day** (2 people, 2 cooked meals plus dish loads): ~2-3 P1 cycles = 35-60 L water and
2.5-4 kWh, on top of cooking. This is similar to two household dishwasher loads a day [E].

### 2.6 Detergent, rinse aid, enzymes, dosing

* Enzymatic detergents (protease for egg/milk, amylase for starch) clearly outperform detergents relying only on alkalinity/bleach for **dried and burnt-on protein/starch soils**; even with bleach and high alkalinity, protein and starch soils are not completely removed [S].
* Chlorine bleach degrades enzymes; use oxygen bleach (percarbonate) or none in the enzymatic step [K].
* Dosing: household ~3-5 g/L (20 g tablet in ~5 L); commercial 2-4 g/L; rinse aid ~1-3 mL per cycle [K/E].
* **Consumables for a refill-rarely rule** (2-3 P1 cycles/day) [E]: liquid alkaline enzyme concentrate ~15-25 mL/cycle -> ~1.5-2 L/month -> a 10 L cartridge lasts ~5-6 months; rinse aid ~2 mL/cycle -> 200 mL/month; citric acid descaler ~50 mL/month. Use **peristaltic dosing pumps from cartridges** (three cartridges: detergent, rinse aid, acid). Tablets and powders are hard to dose robotically and clump in humid air.
* Ideal end state: a single service visit every 6 months refills cartridges; the machine warns 2 weeks in advance from dose counters.

### 2.7 Water hardness and scale

Scale (CaCO3) forms above ~60 deg C and blocks 1-2 mm spray holes, insulates the heater and roughens
surfaces (worse cleanability). At 14 deg dH (2.5 mmol/L; "hard" in Germany [K]) 15 L of water can precipitate
up to ~2-3 g CaCO3 per cycle; ~3 kg/year worst case [E]. Options:

| Option | Consumable | Comment |
|---|---|---|
| Built-in ion-exchange softener (as in dishwashers) | regeneration salt; ~1 kg per ~6-8 weeks at 14 deg dH with 1 L resin [E] | Proven; refill is *not* rare unless the resin volume is increased to ~3 L (~3 kg salt / 6 months) |
| Point-of-entry softener or RO for final rinse | membrane/filter yearly; RO wastes 2-3x rejected water | Spot-free finish |
| Periodic acid descale (P4) + rinse aid | citric acid cartridge | Acceptable for <= 14 deg dH; **design for 25 deg dH tolerance** |

### 2.8 Mains protection and Legionella

* Drinking-water backflow protection per **EN 1717** (air gap or listed backflow preventer, as dishwashers do with an air-gap inlet hose) [K]. No direct connection between the drinking-water line and a sump/vessel.
* Avoid warm stagnant water in the 25-55 deg C band (Legionella): hot buffer >= 60 deg C or none; flush inlet branches that have been idle > 72 h; no dead legs in supply plumbing; keep < 3 L in any stagnant branch [K].

---

## 3. Soil types, difficulty and strategy

| Soil | Behaviour | Best removal | Design consequence |
|---|---|---|---|
| **Sugars, salt, simple juices** | Water soluble; dried film re-dissolves; caramel (not char) dissolves in hot water | Warm water, minutes | Easy; also sticky attractant for pests |
| **Raw starch (flour, potato, rice)** | Cold: rinses off. **Hot: gelatinises into a glue that dries hard** | Cold pre-rinse first; amylase; alkaline | Never start with a hot rinse; pre-rinse <= 35-40 deg C |
| **Protein - egg, milk, meat juice** | **Denatures at >= 60-70 deg C** and bonds to steel; milk leaves "milkstone" | Cold/lukewarm rinse first; protease; alkaline | Same rule; egg soil the reference hard case [S: "protease effect clear for egg; alkalinity minor"] |
| **Fat and oil** | Melts > 40 deg C; polymerised (baked) oil films need strong alkali and time | 55-65 deg C, alkaline, surfactant | Fat in the drain resolidifies in cold pipes (section 7.4) |
| **Burnt-on / carbonised** | Carbon is insoluble; only soaking + chemistry + mechanical (scraper, jet, ultrasonic) | Soak 10-30 min at 50 deg C, alkaline enzyme, 40+ bar jet or silicone/PP scraper; last resort abrasive | Cook programmes must avoid burning (sensor); vessels needing scouring are retired to a "soak" slot |
| **Dried-on residue (any)** | Time dependent: thin film on a hot surface dries in tens of seconds, on a cold surface in an hour or two; wet-dry cycles bind soil | Keep wet | **Rinse < 2 min after emptying a hot vessel; < 30 min for anything else; hold dirty items wet ("wet parking")** |
| **Pigments and odours** (turmeric, tomato, curry, garlic) | Stain PP, silicone, printed parts; odours absorbed by silicone, PP, PE | Oxidising bleach; use non-porous stainless, glass, Tritan | Stainless/Tritan for vessels; PP for cold boxes only; accept stains as cosmetic if the surface is clean |
| **Fine powders (flour, sugar, spice dust)** | Airborne dust deposits everywhere, cakes with humidity | Dry: vacuum/air blast/brush; wet: cannot go into wet chamber without drying | Dry powder paths cleaned dry (section 7.2) |

**Strategy**: (1) *empty completely* (scrape with a tool that has a silicone/PEEK lip while emptying);
(2) *rinse cool within minutes*, (3) *soak with enzyme at ~45-50 deg C if the vessel will wait*, (4) *wash*,
(5) *hot rinse*, (6) *dry*. For cookware, the induction plate can do the soak: after serving, the robot adds
0.3-0.5 L of water + a dose of enzyme cleaner and holds it at 50 deg C for 5-15 min while the meal is eaten,
then carries the vessel to the wash chamber [E].

### 3.1 Which cookware surface cleans best (in a dishwasher)

| Surface | Cleanability | Dishwasher | Notes |
|---|---|---|---|
| **Stainless steel, polished, tri-ply (304/316 inside, 430 induction base)** | Good with soak + alkaline; burnt-on removable; no coating to wear | Excellent (any detergent, 85 deg C) | **Default** for pots, pans, bowls, tools |
| **PTFE non-stick** | Best release for egg/starch; easy | Manufacturers usually say hand wash; alkaline dishwasher detergents and scratches wear it; not above ~260 deg C; fluoropolymer/PFAS **regulatory risk** (EU restriction proposal under discussion) [K] | Only as a consumable pan (replace yearly) if egg/crepe quality demands it |
| **Ceramic sol-gel non-stick** | Excellent initially; non-stick property diminishes faster than PTFE; many "not dishwasher safe" [S] | Poor | Not recommended |
| **Enamel (glass-on-steel, up to ~450 HV)** | Very smooth; cleans well; chips if knocked [S] | Good, chip risk in robot handling | Possible for bakeware, not for robot-gripped pans |
| **Anodised aluminium** | Attacked by alkaline detergents (darkens) [K] | Poor | Avoid in the wash chamber |
| **Cast iron (seasoned)** | Seasoning stripped by detergents | Not allowed | Exclude |
| **Glass (borosilicate)** | Excellent, non-porous | Excellent | Breakage risk with robot handling |

---

## 4. Materials

### 4.1 Regulations in brief

| Regulation | Content | Consequence |
|---|---|---|
| **(EC) 1935/2004** | Framework: food-contact materials must not transfer constituents in quantities endangering health or causing unacceptable change in composition/taste (Art. 3) [S]; traceability and labelling | Applies to everything in Zone F |
| **(EC) 2023/2006** | Good manufacturing practice for FCM [S] | Applies to whoever *makes* the article |
| **(EU) 10/2011** | Plastics: Union list of authorised substances; **overall migration limit 10 mg/dm2 (~60 mg/kg food)**; specific migration limits (Annex I); declaration of compliance along the supply chain [S]. Repeated-use articles are tested on repeated migration runs (third result counts) [K] | Ask suppliers for the Declaration of Compliance for every polymer |
| Metals | No harmonised EU measure; Council of Europe Resolution CM/Res(2013)9 gives release limits for Ni, Cr, Mo etc. from stainless [K] | 1.4301/1.4404 are accepted food-contact steels |
| Silicone, rubber | Germany: LFGB with BfR recommendations XV (silicone) and XXI (rubber) [K]; FDA 21 CFR 177.2600 [K] | Buy food-grade, platinum-cured silicone |
| **FDA** (US) | 21 CFR 177 (plastics/elastomers), 21 CFR 175.300 (coatings; [S] for epoxy), 178.3570 (H1 lubricants incidental contact) [K] | Use where EU markets are not the only target |
| **NSF/ANSI 51 and 2** | Materials and design listings for commercial foodservice [S] | Buy NSF-listed parts for splash zone |
| **NSF H1 / ISO 21469** | Lubricants with incidental food contact allowed | Only lubricants in splash zone; none in Zone F |
| Drinking-water parts | DVGW / lead-free brass (4MS) [K] | Do not use plain brass in water paths (brass nozzle lead also mentioned by Prusa [S]) |

### 4.2 Material table

Dishwasher regime for design: **up to 85 deg C, pH 10-12 (alkaline), acid descale pH ~2, 1000-3000 cycles,
hot air 70 deg C**. Data on heat deflection are typical values [K] unless tagged.

| Material | Hygiene use | Key data | Verdict for wash chamber |
|---|---|---|---|
| **Stainless 1.4301 (AISI 304)** | Splash surfaces, non-salt contact | 18Cr-8Ni; weak against chloride pitting (salt, brine, hypochlorite) | Yes; splash zone default |
| **Stainless 1.4404 (AISI 316L)** | Food contact, salt, sanitiser | 2-2.5% Mo; much better chloride resistance; recommended by EHEDG summaries as "304L/316L" [S] | Yes; Zone F default |
| **PP (polypropylene)** | Boxes, lids, chutes, scoops; living hinges | Tm ~160 deg C, HDT ~100 deg C; stain and odour absorbing; wide FDA/EU grades | **Yes** |
| **PE-HD** | Boxes, cutting boards, chutes | Tm ~130 deg C, HDT ~70-80 deg C; flexible | Yes up to ~65 deg C; marginal at 75-85 deg C |
| **Tritan (copolyester)** | Transparent vessels, see-through bowls | Tg ~110 deg C, BPA-free; dishwasher-proof | Yes; camera-inspectable |
| **PC (polycarbonate)** | Was common for boxes | BPA; crazes in alkaline hot detergent | Avoid |
| **PETG** | Cold boxes, hand-wash items | Tg ~80 deg C; alkaline/hot cycles cause crazing/haze; FDA-listed as *material* [S], but printed parts are different (section 4.3) | Only <= 60 deg C; not for the hot programme |
| **PET, PLA** | - | PLA softens above 55-60 deg C [S] | **No** |
| **POM-C (acetal copolymer)** | Gears, sliders, valve bodies, dosing wheels | Wear-resistant; POM-H and hypochlorite/chlorine attack | Yes, avoid chlorine sanitiser; natural grade food-approved |
| **PA6/PA66 (nylon)** | Bushings, gears in dry zones | Absorbs water (2-9%): dimensional change [K]; SLS PA12 HDT 82-86 deg C [S] | Splash/dry zone only |
| **PEEK** | Food-contact tools, wear parts, brackets in hot zones | > 250 deg C use, excellent chemical resistance, dishwasher-safe [S] | Yes; expensive (stock ~100-150 EUR/kg [K]) |
| **PTFE** | Seals, slide strips, coatings | Inert; PFAS regulatory outlook [K] | Yes technically; regulatory risk |
| **Silicone (VMQ, LSR, platinum cured)** | Seals, gaskets, scrapers, mats | -50..200 deg C; retains odour/oil, swells with oil | Yes, food-grade only |
| **EPDM** | Hot water/steam seals | Excellent hot water; swells in fats and oils | Yes for wash chamber seals |
| **FKM** | Seals in fat/oil contact | Good at 200 deg C in oils | Yes |
| **TPU (white FDA)** | Belts (avoid), grippers | Hydrolysis > 60 deg C; wear | Limited |
| **Aluminium, copper, brass** | - | Alkaline darkening; Cu, Pb leaching; acid foods leach Al | Avoid in Zone F/wash |
| **Wood, cast iron, zinc, galvanised, nickel plating** | - | Not cleanable/corrosion | **Excluded** |
| **Coatings: paint, powder coat** | - | Chip and flake (foreign body) | **Excluded from Zone F/S** |

Rules: colour polymer parts in a colour contrasting with food (blue is standard in food plants because it is
rare in food) so fragments are visible/detectable [K]. Use lubricants only NSF H1 and only outside Zone F.

### 4.3 Food-safe 3D printing

**Position: FDM printing is not acceptable for cleanable food-contact surfaces. It is acceptable for
non-food-zone parts and for sealed splash-zone parts with restrictions.**

Findings:

1. **Layer lines are crevices.** Each layer creates a V-groove; groove depth is typically 20-100 um and bacteria are 1-5 um, so they fit [S]. Prusa: *"No print is food-safe without surface coating"*; chemical (vapour) smoothing is ineffective because it leaves tiny bubbles that harbour bacteria; untreated prints accumulated the most bacterial colonies [S].
2. **Raw material certification does not carry over to the printed part.** PETG resin may be FDA-listed, but *"the FDM process itself is not a certified food-grade manufacturing method"* [S]; SLS powder certification "usually applies to the raw powder, not automatically to the printed part" [S]. Pigments and additives also matter (Prusa recommends only inorganic non-migratory pigments, natural grades) [S].
3. **Cleaning by normal washing is not enough.** A Utah Valley University study found warm water (~49 deg C) and dish soap removed >= 90% of pathogens from PLA/PETG prints [S] - that is about **1 log reduction**, far from the 5-log reduction that FDA defines for sanitisation [S]. Autoclaving destroys PLA/PETG parts [S].
4. **Brass nozzles contain lead**; use a stainless (or hardened steel) nozzle; PTFE liners are acceptable below their temperature limit [S: Prusa].
5. **Coatings help but do not survive the dishwasher.** Food-grade two-part epoxy (e.g. compliant to 21 CFR 175.300 [S]) seals pores and gives a smooth washable surface [S], but Prusa explicitly says resin-coated prints are unsuitable for dishwashers, hot soups and microwaves [S], and Formlabs warns that coatings degrade and can expose the substrate [S].
6. **SLA resins are not food-safe by default**; no Formlabs resin is, unless the user takes additional steps [S]. SLS PA12 has smooth-ish but slightly porous surface with unfused particles; recommend a food-safe coating [S].
7. **A plasma-deposited SiOxCyHz thin film on PA12 was shown to give roughly 4-log reductions in 4 h vs foodborne pathogens** [S: PMC12196969, abstract only]; an industrial process, not a workshop one.

Material limits for dishwashing of printed parts [S/K]:

| Material | Approx. HDT/Tg | Dishwasher 65-75 deg C | Comment |
|---|---|---|---|
| PLA | Tg 55-60 deg C | No | Never near hot water |
| PETG | Tg ~80 deg C | Marginal, haze/creep | Cold or hand-wash only |
| ABS/ASA | Tg ~100 deg C | Mechanically ok | ABS not a food-contact grade; ASA not certified; splash/non-food only |
| PP filament | Tm ~160 deg C | Yes | Hard to print (warping); certified filaments rare |
| PA12 (SLS/MJF) | HDT 82-86 deg C [S] | Yes mechanically | Certified powders exist (raw powder) [S]; porous |
| PA-CF, PA-GF | higher | Yes mechanically | Fibres shed; not for Zone F |
| PEEK, PEKK (industrial FDM) | Tg ~143 deg C | Yes | Needs 400 deg C heated-chamber printer |
| Photopolymer resin | - | No | Not food safe |

**Permitted use of printed parts (binding rule for D1-D10):**

| Zone | FDM (PLA, PETG, ASA, PA-CF) | SLS/MJF PA12 | Industrial PEEK/PP print |
|---|---|---|---|
| **N** non-food | **Allowed** (brackets, housings, guides, jigs). Use PETG/ASA/PA where above 50 deg C | Allowed | Allowed |
| **S** splash | Allowed only if: material stable at >= 85 deg C (ASA, PA, PETG at <= 60 deg C only), **epoxy or paint sealed and free of crevices, no wet-retaining pockets, replaceable (consumable) with a stated interval**, radii >= 3 mm, printed with the smooth face out; *not* in the wash chamber where it sees > 60 deg C | Allowed, sealed, preferred over FDM | Allowed |
| **F** food | **Not allowed** for wetted, cleaned, reused contact. Exception: *dry, single-purpose parts with certified natural filament, coated, cleaned by dry method or hand-off* - not recommended | Allowed for **dry** goods only (scoop, chute for flour, spices) with certified powder + sealing (food-grade coating or dyeing/vapour smoothing) + documented migration test; **not** for wet/hot/fatty or dishwasher-cycled parts | Allowed (PEEK) if the printer and material are certified and a DoC exists |

Recommended routes for food-contact parts that must have complex shapes (in order): (1) machine from
stainless/POM-C/PEEK stock (CNC, turned, laser + bent + welded sheet); (2) injection-moulded standard parts;
(3) **cast silicone or PU from a printed master mould** (print the *mould*, not the part); (4) SLS/MJF PA12
with certified powder and a sealing finish for dry goods; (5) FDM only for tooling and prototypes, which then
are replaced by (1)-(4) in series parts.

---

## 5. Microbiology and food-safety basics for the design

### 5.1 Temperature and time

| Item | Value | Source |
|---|---|---|
| Danger zone | US: **4-60 deg C (40-140 deg F)**; UK: 8-63 deg C. Fastest growth 21-47 deg C | [S] |
| Time limit in danger zone | **2 h cumulative** (discard beyond); 1 h if ambient > 32 deg C | [S]/[K] |
| Refrigeration | Design value <= 5 deg C, alarm > 7 deg C (Germany DIN 10508: refrigerated foods generally <= 7 deg C, minced meat <= 2 deg C, fresh poultry <= 4 deg C [K]); *Listeria* still grows near 0 deg C, so time also counts [K] | [K] |
| Freezer | <= -18 deg C | [K] |
| Hot holding | **>= 63 deg C** (EU), **>= 65 deg C** serving temperature per German guidance (DIN 10508) | [S] |
| Cooling of cooked food | FDA Food Code: 57 -> 21 deg C within 2 h, then to <= 5 deg C within a further 4 h; FSIS Appendix B (beef/poultry): 54.4 -> 26.7 deg C in 1.5 h, then to 4.4 deg C within a further 5 h; prevents *C. perfringens* and *C. botulinum* spore outgrowth | [K]; principle [S] |
| Cooling design | Portions in layers <= 5 cm; a dedicated **blast-chill** step or shallow vessel in the fridge; cool-down curve logged | [E] |

### 5.2 Required core temperatures (safe minimum)

| Food | Core temperature | Source |
|---|---|---|
| Poultry (whole, parts, ground) | **74 deg C (165 deg F)** instantaneous | [S] |
| Ground/minced beef, pork, lamb, veal | 71 deg C (160 deg F) | [S] |
| Eggs and egg dishes (sauces, custard) | 71 deg C (160 deg F), or yolk and white firm | [S] |
| Whole cuts of beef, pork, lamb, veal; fish | 63 deg C (145 deg F), with a 3 min rest | [S] (rest [K]) |
| Reheated leftovers, reheated poultry | 74 deg C (165 deg F) | [S] |
| German BfR recommendation for poultry/minced meat/eggs | core >= 70 deg C for >= 2 min | [K] |
| Time-temperature equivalence | Lower temperature is safe if held long enough (lethality integral) | [S] |

**Design default:** critical limit **>= 72 deg C core for >= 2 min** for poultry, minced meat and egg dishes;
**>= 63-65 deg C core for >= 3 min** for whole-muscle red meat and fish; liquids and sauces **>= 85 deg C
bulk** (simmer). Core temperature must be *measured* (spike probe on a tool that is washed each time, or
thermocouple in the vessel/stirrer for stirred foods) - section 8; open issue if a robot cannot probe reliably.

### 5.3 Cross-contamination and allergens

* **Raw meat/poultry/fish/eggs** carry *Salmonella*, *Campylobacter*, *Listeria*, STEC. Hazard: transfer to ready-to-eat (RTE) foods via vessel, tool, gripper, board, surface, or air/splash [K]. **Rules:** raw and RTE never share a vessel or tool between washes; sequence RTE before raw or use a wash between; raw-flagged items get the P1 programme with the sanitising hold; the gripper that handled raw-contact items is washed before it touches clean items.
* **Packaging is a contamination source** (supermarket packaging is not clean, raw meat trays leak): the ingestion cutter passes from the outer to the inner side of a package. **Treat the ingestion cutter and funnel as raw-meat contact surfaces**; wash/steam them after each package, or at minimum after each raw item [E]. (R7 details the packaging.)
* **Allergens (EU list of 14)**: allergenic proteins are heat-stable; **sanitising does not remove them, only physical removal does** [K]. Design: no shared unwashable paths (dosers for flour, nut, sesame, mustard are dedicated per ingredient or removable-washable); a household "allergen profile" triggers double wash + fresh-water rinse + protein test at service; log each ingredient with its allergen tags per vessel/tool use.
* **Cold storage**: sealed boxes only; no open food in the fridge; drip tray with drain.

### 5.4 Biofilm

*Listeria monocytogenes* attaches to stainless steel within ~3 h; 10^6-10^8 CFU/cm2 after 24 h; mature biofilm
between 24 h and ~7 days depending on nutrients and temperature [S]. Mature biofilm resists normal
cleaning and sanitisers [S]. **Design consequence:** (a) no surface that can stay wet and soiled > ~4 h (section 3);
(b) every food-contact or splash surface gets a mechanical clean at least every 24 h of use, and a
sanitising hot step at least daily; (c) hidden moist niches (seals, hollow tubes, gasket grooves, threads, dead
legs) are the real risk and must be designed out (section 1); (d) a weekly deep/sanitise programme
P3 [E]. A proposed anti-biofilm chemistry is electrolysed alkaline water 30 deg C/10 min followed by
electrolysed oxidising water [S], useful as an option, not a base.

### 5.5 HACCP for an autonomous kitchen

Regulation (EC) 852/2004 Art. 5 requires HACCP-based procedures [S]; CCPs typically include goods receipt,
storage, cooling, heating and hot-holding [S]. Author's mapping (oPRP = operational prerequisite programme):

| # | Step | Hazard | Critical limit / target | Monitoring by machine | Corrective action |
|---|---|---|---|---|---|
| 1 | Ingestion (receiving) | Spoiled/damaged/unknown product, pests, wrong allergen data | Package intact, use-by not passed, barcode resolved; frozen goods not thawed | Barcode + date OCR, camera, weight; temperature for chilled goods if probe available | Reject to a "quarantine" bin, tell the user |
| 2 | Cold storage | Growth | Fridge <= 5 deg C (alarm 7 deg C after 30 min), freezer <= -18 deg C | Continuous sensors with 1 min logging | Alarm, mark boxes "review", block use of high-risk items after limit exceeded > 2 h cumulative |
| 3 | Thawing | Growth in danger zone | In fridge <= 5 deg C, or during cooking; never on the counter | Time and temperature | Discard beyond 2 h in zone |
| 4 | **Cooking (CCP)** | Survival of pathogens | Section 5.2 | Core/bulk probe + time | Continue heating; reject the portion if not reached |
| 5 | **Cooling (CCP)** | Spore outgrowth | 57->21 deg C <= 2 h, -> <= 5 deg C <= 4 h | Probe in vessel | Discard if failed |
| 6 | Hot holding / serving | Growth | >= 63-65 deg C (or serve within 2 h) | Vessel/plate warm-holding sensor | Discard after 2 h |
| 7 | **Cleaning (oPRP; CCP if user is immunocompromised)** | Residue, biofilm, cross-contact, detergent residue | Section 2.5 (T, t, dose) and 8 (turbidity/conductivity) | Full cycle log | Repeat cycle; retire item |
| 8 | Water quality | Legionella, contamination | Drinking-water; no warm stagnation | Flush counter, hot buffer temperature | Flush/heat |
| 9 | Pest control | Contamination | Sealed boxes, no openings > 5 mm | Sensors, glue traps at service | Service |
| 10 | Waste | Odour, flies, cross-contamination | Sealed bins | Fill/timer | Alert to empty |
| 11 | Foreign bodies | Plastic/metal/glass fragments | Zero | Camera check of vessels; detectable (blue) polymers; magnet trap in filters | Stop and inspect |

### 5.6 What must be logged (per event, time-stamped, tamper-evident, retained >= 1 year [E])

* Every box: ID, ingest date, product, EAN, allergens, use-by, storage temperature history summary, wash count.
* Fridge/freezer temperature continuously (1-min), door/exit events, alarms.
* Every cooking: recipe ID, vessels/tools used and their raw/RTE flags, time-temperature curve, core/bulk temperature, hold time, cooling curve, serve time.
* Every wash cycle: item IDs, programme, temperatures per step, A0 value, water volume, detergent dose counts, turbidity and conductivity curves, drying humidity, pass/fail, retries.
* Sensor calibration and self-tests; service actions; consumable levels and refill dates; door/hatch opening; pest alarms.
* Allergen profile of household and each allergen-relevant cleaning decision.

The German/EU legal obligation is on food *businesses* (852/2004); private households have none, but the same
data gives the user trust and the customer a liability defence [E].

---

## 6. Cleaning the hard parts: rails, belts, grippers, robot, cables in the splash zone

### 6.1 Strategy

**Keep the drive train out of the wet zone; move only passive, washable objects inside it.** Where motion must
cross into a wet zone, use one of: (1) magnetic coupling through a non-magnetic stainless wall; (2) bellows/diaphragm
(reciprocating motion); (3) IP69K stainless/hygienic actuators; (4) accept IP65+ and rounded surfaces on a
robot arm (last resort, expensive).

### 6.2 Component options and ratings

| Component | Fit | Notes / data |
|---|---|---|
| **Stainless hygienic electric rod actuators** (Tolomatic ERD/IMA, BJ-Gear, LinMot stainless motors) | IP67-IP69K; stainless housings, 316 rod and fasteners, rounded body, water-shedding, food-grade lubricants, Viton seals; *rod style* only needs the rod opening sealed and is better than rodless in washdown [S] | Use where a rod push/pull inside the wet zone is needed |
| **Magnetically coupled rodless carriers** | Carriage inside a sealed tube or behind a 0.8-1.5 mm non-magnetic stainless wall; drive outside [K] | Force limited (~100-500 N typical, [E]); ideal for light gripper carriages; decouple risk on overload (acts as a fuse) |
| **igus food-contact bearings (iglidur)** | Dry-running, self-lubricating, maintenance-free; grades **A160 (to +90 deg C, FDA + EU 10/2011), A180 (wet areas), A181 (FDA + EU), A200, A500 (-100..+250 deg C)**; PTFE-free options A160/A500; wear predicted by online calculator [S] | Use as slide bushings on stainless shafts/rails inside splash zone; verify per part number whether a rail/carriage variant with these liners is offered; wear debris must be captured (blue/visible?) |
| **Stainless linear guides** | Open profile rails with 316/440C rails and NSF-H1 grease inside the block [K] | Suitable for dry/splash edge; ball recirculation cavities trap soil; prefer plain sliders in splash |
| **Belts** | White FDA PU/TPU belts with stainless cords; open teeth trap soil [K] | Only in a dry tunnel; do not use in splash zone |
| **Rack and pinion, lead/ball screws** | Grease in the mesh; need bellows | Behind a wall |
| **Industrial hygienic robots** | **Stäubli HE (TX2-60 HE etc.)**: fully enclosed *pressurised* 316L body, no paint, smooth rounded/tilted surfaces, open below to drain, connectors integrated, NSF-H1-compatible, EHEDG-conform exterior, IP65-IP67 (some sources IP69K) [S]. **FANUC M-20iD/25 food**: IP65 body, IP67 wrist and J3, white epoxy paint, stainless flange, NSF-H1 grease, anti-rust bolts [S]. Other IP69K FANUC models exist (DR-3iB/6) [S] | Heavy (tens of kg to > 100 kg), expensive (order 30-60 kEUR [E]); far too large for a 600 mm-deep cabinet; a lesson, not a solution |
| **Robot covers/jackets** | Washable or single-use suits over standard arms for washdown [K] | Adds heat/seal issues; not needed if arm stays in dry zone |
| **Cameras and sensors** | IP69K stainless proximity sensors; camera behind a **heated window with air purge**; condensation is the practical enemy [E] | |
| **Cables and connectors** | M12/M8 IP68/IP69K stainless connectors, PUR/TPE halogen-free jackets, no drag chains in wet zone, or hygienic drag chains; smooth sheath, rise and drain path; connectors placed **below** cable entry (drip loop) [K/E] | |
| **Hoses** | FDA silicone/PTFE, no spiral coverings; smooth-bore, pitched to drain | |

### 6.3 Where things sit in the machine (recommended)

```
 Zone N (dry, sealed, IP54, pest-proof)          Zone S (wet, sloped, stainless)
+------------------------------------+   sealed penetrations   +--------------------------+
| motors, drives, PLC, camera        |=== magnetic coupling ===| carriage / gripper (dry- |
| electronics, cable chains          |=== bellows / lip seal ==| running bushings, SS)    |
| gantry rails (dry), belts          |                         | washable via wash station |
+------------------------------------+                         +--------------------------+
```

### 6.4 The gripper problem (cross-contamination path)

The gripper touches dirty items, then clean items. **Rules:** (1) grip only defined *handle zones* on
vessels/boxes (Zone S), never food-contact surfaces; (2) gripper fingers are stainless/PEEK/food-grade
silicone, radii >= 3 mm, removable in tool-free way; (3) use **two grippers** (dirty side, clean side) *or* a
**gripper wash/steam station** between dirty and clean handling; (4) the pass-through wash chamber (section 9) hands
the vessel over on the clean side to the clean gripper.

### 6.5 Steam and grease aerosol travel

Cooking vapour condenses on the coolest surfaces (ceiling, hood, the transport rails next to the cell) and
drips back. **Rules:** enclosed cook cell with door; extraction hood with removable stainless baffle filter
(a wash-chamber-sized item); ceiling sloped >= 5 deg to a gutter that drains outside the food area; negative pressure
5-10 Pa in the cook cell relative to the adjacent transport/storage area [E]; the transport corridor is separated from the cook
cell by a hatch that closes during cooking.

---

## 7. Storage boxes, dispensers, pests, waste

### 7.1 Boxes (cleaning)

* **Boxes are only opened where product is added (ingestion) or removed (dispensing cell), never in the storage grid.** Lids with a gasket keep dust, moths and moisture out.
* **Empty -> wash -> dry -> refill.** No topping-up of a box with a new package on top of old contents (the old residue becomes a permanent reservoir); refill only into a clean, empty box; a box that has been in use > ~8-12 weeks is emptied to a spare box and washed (FIFO) [E].
* Boxes are wash-chamber-sized and rack-compatible; drying must reach "dry to the touch" before return to dry storage (exhaust humidity/weight check).
* PP boxes with gasketed lids; smooth interior (radii >= 3 mm, no ribs on the inside), draft angle for drainage, no living hinge inside the food area.

### 7.2 Dispensers and dry-powder paths

* Liquid dispensers: peristaltic tubes/food-grade silicone; **CIP loop** with hot water + detergent, flow >= 1.5 m/s in tubing [S]; oil, sugar syrup, soy sauce leave films - flush after each use [E].
* Solid/powder dosers (auger, rotary valve): removable and washable in the wash chamber, or **dry-cleaned** (air blast + vacuum into a filter/bin, no water) in place; flour and sugar that get damp cake and mould. Dedicated dosers per allergen [K].
* **Storage grid crumbs and spills**: a **cleaning shuttle** in box format (vacuum, brush, steam/wet-wipe pad), stored in the grid, run by the transport system, returned to the wash chamber [E]. A spill tray under the grid with a slope to a drain point.

### 7.3 Pests, mould, odours

| Problem | Facts | Design rule |
|---|---|---|
| **Pantry moths, weevils, flour beetles** | Larvae **chew through thin plastic and cardboard**; hard plastic, glass, metal with tight lids stop them; freeze new grains for 72 h to 1 week to kill eggs; higher humidity breeds pests [S] | Hard PP boxes with gasketed lids only; **quarantine/freeze incoming grain, flour, nuts, dried fruit in the freezer module 72 h - 7 days** before the ambient store [S]; ingestion pours from the package into the box, package itself never enters the storage |
| Flies | Fruit flies are attracted to ripe fruit and waste | Sealed waste bin; any air inlet with mesh <= 1 mm |
| Mice | Pass gaps >= ~6 mm [K] | All housing openings <= 5 mm, brush or mesh seals at plinth; sealed cable/pipe penetrations |
| Cockroaches | Use warm dark cavities and gaps ~1.5 mm [K] | Seal enclosures (IP54), no open hollow tubes, fill voids with closed-cell foam/sealant |
| Mould | Supported at > ~65-70% RH [K]; dry-goods store **<= 60% RH** | Vent through a filtered breather; no wet parts enter the dry store; drying verification; fridge condensate drained not standing |
| Odour | Fat, fish, waste, moist plastics | Activated-carbon filter in exhaust and waste bin; cool or sealed bin; UV-C adjunct on empty, dry compartments only; no ozone in occupied space [S/K] |

### 7.4 Waste: peelings, food waste, packaging, grease

* **Waste disposer (macerator) into the drain: not to be used.** Germany has no national ban, but most municipalities forbid discharge of kitchen waste even shredded in their wastewater bylaws; **DIN 1986-100** says grinders for kitchen waste may not be connected to the sewer; Austria explicitly bans, Switzerland bans; EN 12056-1 leaves it to member states; allowed in Denmark, UK, Ireland, Italy, Norway, Spain [S]. Additional 3 L water/person/day, fat build-up, sludge [S]. **AutoKitchen: no macerator.**
* Solids go to a **removable waste tray/bin** behind a strainer/sieve (>= 2 mm, ideally 1 mm) at every drain (wash chamber sump, cell floor, waste chute). Fine particles that pass a 1-2 mm sieve go to the drain exactly as with any household dishwasher (legal) [K].
* **Food-waste bin**: sealed, gasketed lid, removable 10 L liner/bin (2 persons ~ 0.1-0.3 kg/day, so 3-5 days [E]), compostable bag; carbon filter; optional Peltier cooling to ~10 deg C to stop odours and larvae [E]. Germany has mandatory separate bio-waste collection (KrWG) [K]; plastics contamination of bio-waste is restricted, so **packaging film must never enter the bio bin**.
* **Packaging waste** (film, cartons, cans cut by the ingestion machine): separate sealed bin (20-30 L); compaction optional (mould/odour/contamination risk, so v1 without compaction) [E].
* **Grease in wastewater**: private households have no grease trap obligation; commercial kitchens must have a separator to **EN 1825 / DIN 4040**, emptied and cleaned **every 4 weeks** [S]. Design: wash water with fat is at 50+ deg C and emulsified by detergent, same as a household dishwasher [K]; **no deep-fat frying with disposal to drain**: used frying oil collected in a sealed can; a **fat-scraper step** removes gross fat from pans into the waste tray before washing [E]. If the machine is sold to a commercial user, an EN 1825 separator is the legal minimum.
* **Drain**: DN40 trap with anti-siphon, air gap to the mains line (section 2.8), sump and drain pump with **automatic flush of the sieve basket** after every wash (a household dishwasher's filter clog problem must be automated).

---

## 8. Verification of cleanliness by machine

### 8.1 What commercial dishwashers do

* **Optical turbidity sensor**: LED and photodetector measure light scattering/absorption of the wash water; soil raises turbidity; used at cycle start to classify soil load and set cycle duration, temperature and detergent dose [S].
* **Conductivity sensor** for dissolved ionic soil and to **detect detergent being rinsed out** [S].
* **Temperature sensor**; multi-sensor microprocessor decision logic rather than one sensor [S].
* **Known failure: "false clean"** - foam and dissolved detergents scatter light like soil, so a turbidity-only cycle can end early with food still present; state-dependent sensitivity [S].
* Pressure/flow and spray-arm rotation (Hall sensor), water level, pump current for clogged filters [K].

### 8.2 Proposed verification stack for AutoKitchen

| Layer | What | Pass criterion (start value, to be tuned) | Type |
|---|---|---|---|
| L1 | Process parameters (T, time, dose, volume) met per step; A0 >= 60 in final rinse | Hard interlock; failed step is repeated | Automatic [E] |
| L2 | **Turbidity in the *final fresh-water rinse* (no detergent)** | <= 2x inlet-water baseline NTU (~<= 2 NTU); use only fresh-water rinses to avoid detergent foam artefact [S] | Automatic [E] |
| L3 | **Conductivity and pH of the final rinse** | Within +20 uS/cm and +0.5 pH of inlet water: confirms detergent removal (chemical safety) [S principle] | Automatic [E] |
| L4 | **Camera inspection** of each item on the clean side under diffuse white + oblique + UV-A (365 nm) light, compared to a reference image of the same item ID; residues (protein, fat) often fluoresce | Residue area < threshold; fluorescence < threshold | Automatic, needs prototyping [E] |
| L5 | Exhaust humidity/dew point falls to dry level; weight of item | Dry | Automatic |
| L6 | **ATP bioluminescence swab** (manual): at commissioning, after service, quarterly by a technician; **protein-residue swabs** for allergen zones; typical pass criterion is device-specific RLU limit for food contact [K] | Below device limit | Manual |
| L7 | Initial soil turbidity trend per item type; **drift detection** (rising residual turbidity over weeks signals nozzle scaling or filter clogging) | Trend | Automatic [E] |

Decision logic: soil class from pre-rinse turbidity -> programme. If L2/L3/L4 fails: repeat wash once with
more time and stronger dose; if it fails again: **quarantine the item** (spare vessel in use), alert the user
once, log. Surface temperature of the load is not measured by the sump probe; commissioning uses
wireless data loggers on load items to validate that A0 is reached at the coldest spot.

---

## 9. Concept comparison for AutoKitchen

Three concepts requested plus their combination.

### 9.1 (a) Everything removable goes through a wash chamber

Vessels, tools, boxes, plates are dishwasher-sized and carried by the transport system to a dishwasher-like
chamber; the chamber is a standard wash process (P1).

### 9.2 (b) Wash-down cell

The preparation/cooking cell is itself a sealed stainless chamber with spray nozzles that washes itself.

### 9.3 (c) CIP of closed vessels

Closed vessels with a spray head (in the lid) and closed liquid lines are cleaned in place; blender-style
self-clean (fill water + detergent, run tool) for mixer vessels.

### 9.4 Comparison

| Criterion | (a) Wash chamber for all removables | (b) Wash-down cell | (c) CIP closed vessels/lines | (d) Recommended combination |
|---|---|---|---|---|
| What it cleans | Everything that can be moved and fits: pots, pans, tools, boxes, plates, grippers, filters | Fixed surfaces: walls, floor, ceiling, hood, gantry underside | Enclosed cavities: mixing bowls with drive, liquid lines, dispensers | Removable items in (a), fixed housing in (b'), lines and closed bowls in (c) |
| Coverage confidence | **High**: each item has a defined rack position, nozzles aimed per item type; shadowing controlled by fixtures | **Low-medium**: robot, tools, cables and holders create spray shadows; unpredictable geometry; soil in gaps | High for simple cavity (ball/rotary nozzle), low for baffles and shafts | High where it matters |
| Mechanics | Low (recirculation spray arms), compensated by time and chemistry [S] | Fixed jets at 2 bar (2.4 L/min each); limited impact | Sheeting flow + tool action | |
| Water per cycle | 17-20 L (P1); 10 L quick [E]; household 9.5-22 L [S] | 25-40 L per wash + rinse of a 2.4 m2 cell [E] | 13-15 L per vessel [E] | ~45-60 L/day typical |
| Energy per cycle | ~1.3 kWh incl. drying [E] | 0.7-1.2 kWh (sump heating, steam optional) [E] | 0.5-0.8 kWh [E] | 3-5 kWh/day |
| Time | 55-75 min full, 20-25 min quick | 15-30 min incl. dry | 10-20 min | Parallel: chamber running while cell is washed |
| **Cross-contamination control** | **Best**: pass-through, dirty side and clean side | Poor: soil moved around the cell | Good | |
| Robot exposure to water | None (chamber is closed, robot only loads through the door) | **High**: every actuator, cable, sensor must be washdown-rated (IP69K) or hidden | None if CIP is inside the vessel | Robot stays in dry zone or in a dry-cleanable shelter |
| Reliability / maturity | High: uses mature dishwasher parts (pump, heater, filter, spray arms, level sensor) [K]; risk is the automated door/rack handling | Medium-low: novel; seals and cables in wet zone fail | High for simple geometry | |
| Failure mode | Chamber down -> **no clean vessels** unless buffer or manual fallback | Cell stays dirty -> visible failure; but subtle spots persist unseen | Blocked nozzle leaves a dirty spot | Redundancy through spares and manual fallback |
| Footprint (depth 600 mm) | Chamber 480 x 480 x 400 mm interior fits in a 600 mm-deep cabinet (walls + insulation ~2 x 50 mm) | Fixed part of the cell; no extra | Nozzles in lids; small | ~0.6 m width + 0.6 m for a wash module |
| Cost | Off-the-shelf components: circulation pump, drain pump, heater, sensors ~200-400 EUR [E] + housing | Nozzles, pump, sump, wash-down rated everything: high | Low per vessel | |

### 9.5 Recommendation (d)

**Backbone (a): a dedicated pass-through machine-ware wash chamber** built from dishwasher parts, fed by the transport
system, plus the user's own dish washer as separate off-the-shelf unit (or the same chamber if the user racks
are compatible). It is the only concept that gives *verified, repeatable* cleanliness at reasonable cost and lets us
keep the robot dry.

1. **Pass-through wash module.** Interior ~480 x 480 x 400 mm (~92 L), two sliding doors (dirty side toward prep/cook, clean side toward the clean-vessel store), interlocked so never both open. Sump 6-8 L, 2 kW heater, circulation pump, two rotating arms + fixed nozzles matching the racks, hot-air dryer, triple-stage filter with auto-flushed sieve, dosing pumps, turbidity/conductivity/pH/temperature/humidity sensors, camera on the clean side. Programmes P1-P4 (section 2.5). Envelope of machine-ware **must be compatible with a standard household dishwasher rack** so a user can wash items manually in a fault (degraded mode).
2. **(b') Wash-down-lite in the prep/cook cell.** The cell is a splash-zone box with: monolithic stainless welded interior (coved radius >= 10 mm, sloped floor >= 3 deg to one central drain with sieve, ceiling sloped >= 5 deg to a side gutter), no exposed electronics, actuators and cameras outside; gantry parked in a sealed dry garage/behind a shutter during the wash; **rotating spray head in the ceiling + fixed nozzles**, mains-fed 2-3 jets or 5 bar diaphragm pump from a 10 L sump; hot rinse at 60-70 deg C; steam optional; dry-out fan. This is a *rinse and sanitise* of the fixed cell, not a scrubbing wash. Frequency: after each cooking session (10-15 min) and weekly deep. Cross-contamination risks are mitigated because **food touches only removable vessels**, not cell surfaces.
3. **(c) CIP for closed liquid paths** (oil, vinegar, stock, syrup dispensers; blender/mixer vessels with lid nozzle): hot-water+detergent loop, >= 1.5 m/s in lines.
4. **Cleaning shuttle** (box-format) for storage grid, rails and hatches.
5. **Robot arm out of the wet zone** (dry drive room with magnetic/bellows penetration); gripper on a wash station; two grippers or a gripper wash between dirty and clean.
6. **Fallbacks**: a spare set of vessels (>= 2 x the count needed for one meal) so a 60-min wash does not stall cooking; manual fallback via the user's dishwasher.

The pass-through chamber is the only part of the machine that moves water at scale; concentrate reliability effort
there (scale management, filter self-cleaning, sensors redundancy).

---

## 10. Integration constraints for each module (feeds D1-D10)

| Module | Hygiene constraints derived |
|---|---|
| D1 Storage/boxes | PP boxes with gasket lids, smooth interior; empty-wash-refill; sealed against pests; grid is Zone N; spill tray; quarantine/freeze slot for incoming dry goods; box compatible with wash rack |
| D2 Cold storage | Sealed boxes only; condensate drained; airlock design to avoid mould; interior wiped by cleaning shuttle; temperature logging; UV-C optional on empty compartments |
| D3 Transport | Drives in dry zone; wet-side parts passive, stainless/igus; two grippers or a gripper wash; grip handle zones only; cleaning shuttle; rails self-draining |
| D4 Preparation | Stainless/POM-C/PEEK/Tritan tools and vessels; quick-release blades; no FDM in food contact; scraper lips; all items wash-chamber-sized; raw/RTE flags; detectable blue polymers |
| D5 Cooking | Ceiling/hood slope + condensate gutter; extraction with baffle filter (removable); induction plate flush glass-ceramic, sealed edge; vessel soak on plate; no burning; oven pyrolysis only if oven present (3-7 kWh) |
| D6 Portioning/serving | Serving hatch interior sloped, smooth, self-wash; plate handling by clean gripper; plates from clean side; door seal wipeable |
| D7 Cleaning | Implements section 9.5; power manager; softening/descale; dosing cartridges; verification stack (section 8); logging |
| D8 Ingestion | Dirty zone: cutter/funnel treated as raw-meat contact, steam/wash after each package; package never enters storage; frozen quarantine step; waste (packaging) bin; dust extraction |
| D9 Frame/casing | Zones and sealing; pest-proof plinth; drains; IP ratings; service access to seals; electrical safety in wet areas (RCD) |
| D10 Control | Logs (section 5.6), power manager, sensors, HACCP alarms, traceability |

---

## 11. Checklist of design rules (every module designer)

Mark each item "met / not met / n.a. (with reason)" in your design document.

**A. Zoning and surfaces**
1. State the hygiene **zone (F/S/N)** of every surface and its **cleaning method and frequency**. A surface with no stated cleaning method is a defect.
2. Zone F metal Ra <= 0.8 um (2B sheet is typically 0.2-0.5 um); Zone S metal Ra <= 1.6 um.
3. Internal radii >= 6 mm preferred, >= 3 mm minimum; sealing corners sharp with 0.2 mm break edge.
4. All surfaces self-drain: slope >= 3 deg (5 deg for ceilings and viscous soils) to a defined drain point; no horizontal ledges, no ribs on the food side, no pockets.
5. No hollow sections open to soil; close by welding, gasket or cap. No crevices at joints; continuous smooth welds ground flush, on flats not corners.
6. No exposed threads or bolt heads in Zone F; in Zone S use hygienic (domed/sealed/welded) fasteners.
7. No paint, powder coat, wood, aluminium (unanodised), brass/copper or galvanising in Zone F/S. Zone F metal 1.4404 (1.4301 only if no salt/chlorine contact); Zone S 1.4301 minimum.

**B. Materials**
8. Food-contact polymers only with EU 10/2011 (and FDA where relevant) declaration of compliance for the exact grade; no PC, no PLA, and no filament without a manufacturer declaration for the natural (unpigmented) grade in Zone F.
9. Dishwasher regime for every removable item: **85 deg C, pH 10-12, 3000 cycles, acid descale, hot air 70 deg C**; no material in the chamber with Tg/HDT < 85 deg C unless the programme is limited to lower temperature and the item flagged.
10. Elastomers: EPDM (hot water/steam), FKM (fat), platinum-cured silicone (food); no O-rings exposed in a groove open to food.
11. Lubricants NSF H1 only, only outside Zone F; prefer dry-running polymer bearings (igus A160/A180/A181/A500).
12. Polymer parts in Zone F are a contrasting colour (blue) or detectable.

**C. 3D printing**
13. **FDM: Zone N always; Zone S only sealed, replaceable, < 60 deg C in wash chamber, radii >= 3 mm; never Zone F cleaned-and-reused.** Stainless nozzle. SLS/MJF PA12 for dry-goods food contact only with certified powder + sealing + migration test. Prefer machined, moulded, cast-from-printed-mould or PEEK for food-contact.

**D. Mechanics, drives and wet-zone components**
14. Drives, motors, gearboxes, PLC, electronics and camera electronics are in Zone N; motion enters Zone S through a magnetic coupling, bellows, or IP69K hygienic actuator.
15. Wet-zone components rated IP65 minimum, IP69K where directly jetted; cables PUR/TPE with sealed M12 stainless connectors; no drag chains in the wet zone; drip loops at every cable entry.
16. Grippers grip only designated handle zones; provide two grippers or a gripper wash/steam station between dirty and clean; fingers removable without tools.
17. Dirty -> clean flow is one-way: pass-through wash chamber with interlocked doors; clean items never travel back through the dirty zone.

**E. Cleaning process**
18. Everything removable fits the wash chamber (480 x 480 x 400 mm envelope, standard dishwasher rack compatible) and survives P1.
19. Rinse **< 2 min** after emptying a hot vessel; < 30 min for other soiled items; wet-park dirty items; never a hot first rinse for starch/protein (pre-rinse <= 35-40 deg C).
20. Final rinse >= 75 deg C for >= 3 min (A0 >= 60) on the load; forced drying to dry; nothing stored damp.
21. Every wash cycle is sensed (T, time, dose, turbidity, conductivity, pH, humidity), logged, and pass/fail with a defined retry and quarantine path.
22. Water: mains only for fill and fresh rinse; recirculation pump for mechanics; EN 1717 backflow protection; no warm stagnation (Legionella), flush idle lines; tolerate 25 deg dH with automatic descale.
23. Power: wash heater and cooking budgeted within one ~3.6 kW circuit; power manager interlock; heater <= 2 kW.
24. Consumables: cartridges with counters, warning 2 weeks ahead, target refill interval >= 6 months.

**F. Food safety**
25. Cooking critical limits: >= 72 deg C core 2 min for poultry/minced meat/egg dishes; >= 63-65 deg C for whole-muscle red meat/fish; bulk 85 deg C for sauces; measured and logged.
26. Cooling: 57 -> 21 deg C <= 2 h and -> <= 5 deg C within 4 more h; layers <= 5 cm; logged. Hold hot >= 63-65 deg C or serve within 2 h.
27. Cold chain: fridge <= 5 deg C (alarm 7), freezer <= -18 deg C, logged.
28. Raw and RTE items use separate flagged vessels/tools or a wash between; allergen-tagged items with dedicated or washed paths.
29. Ingestion cutter/funnel and any package contact surface treated as raw-meat contact.

**G. Pests, waste, odours**
30. No opening in the housing > 5 mm (mice); mesh <= 1 mm for air inlets (flies); seal all plinth and penetrations.
31. Storage boxes hard PP with gasket lids; boxes opened only in ingestion/dispensing cells; incoming grain/flour/nuts frozen 72 h - 7 days before ambient store.
32. **No macerator into the drain.** Solids collect in sieves (<= 2 mm) and a removable bin; sealed bio-waste and packaging bins; grease not to drain in bulk (fat scraper; oil can). Municipal by-laws checked.
33. Dry-store RH <= 60%; condensate drained.

**H. Service**
34. Every seal, filter, nozzle, wear bearing is accessible from outside without tools or with one common tool, has an inspection interval, and is logged.

---

## 12. Open issues

1. **Primary standard texts were not read** (EHEDG Doc 8/13/44, EN 1672-2, EN ISO 14159, NSF 2/51, 3-A). Numbers in section 1 rely on secondary quotations; a designer should buy or download EHEDG GL 8 and GL 13 (both free for EHEDG members / small fee) and confirm radii, slopes and zone requirements. EHEDG Doc 44's scope is only inferred.
2. **Wash-chamber and dishwasher standards** (NSF/ANSI 3, DIN 10510, DIN SPEC 10534, EN 17735 (unverified number)) were not researched; the 75 deg C x 3 min (A0 60) sanitising target is a design choice derived from the Bosch HygienePlus level and A0 concept, not a validated regulatory value. Needs validation with a microbiology lab.
3. **Cleaning verification by machine** (camera/fluorescence residue detection) has no cited prior art here; feasibility must be prototyped. Thresholds in section 8 are starting values.
4. **Core-temperature measurement by robot**: how to probe reliably, and cleanably, in irregular food is unresolved (needs R4/R5/D4 input).
5. **Allergen validation**: no data on residual protein after machine wash; need protein-swab tests (ELISA/lateral flow) on the prototype.
6. **Cooking-fat aerosol and vapour management**: hood and exhaust need a duct out; conflicts with "no wasted footprint" and with recirculating carbon-filter household hoods. Decision for D5/D9.
7. **Power**: a single 16 A circuit limits parallel cooking and washing; is a second circuit or a 32 A supply acceptable to the customer?
8. **Pass-through wash module size vs cabinet depth**: 480 x 480 x 400 interior fits by calculation only; needs CAD check with racks and door mechanism.
9. **Fridge interior cleaning**: only the cleaning-shuttle idea; needs a design owner (D2/D3).
10. **PFAS restrictions** may remove PTFE cookware and PTFE seals from the market; decide early whether to design without PTFE.
11. Whether **EU 10/2011 repeated-use migration tests** are required for the finished machine (placing on the market) or only for supplier components; legal clarification needed if the machine will be sold.
12. **Human tasks** the design still leaves: emptying bio/packaging bins every 3-5 days, refilling cartridges every ~6 months, occasional service (ATP swabs, seal replacement). Customer must confirm this is acceptable.
13. Steam/ultrasonic modules are options without a decision; they need a cost-benefit after the wash-chamber prototype.
14. The **1.4404 vs 1.4301** split rests on chloride exposure (salt, brine, hypochlorite); a corrosion test with real salty/acidic foods is needed.

## 13. Risks

| # | Risk | Impact | Likelihood | Mitigation |
|---|---|---|---|---|
| R1 | Wash chamber is the single point of failure | No clean vessels, cooking stops | Medium | Spare vessel sets, manual fallback into the user's dishwasher, redundant sensors and self-test |
| R2 | Hidden biofilm in seals, gaskets, hollow parts | Food-safety incident (Listeria) | Medium | Design out crevices; weekly P3; seals as service items; ATP swab at service |
| R3 | Spray shadowing in the wash chamber or the cell leaves soil | Persistent contamination, odour | High for the cell, medium for chamber | Item-specific racks and nozzle placement, camera verification, no reliance on the cell for food-contact hygiene |
| R4 | Burnt-on soil resists automatic cleaning | Retired vessels, waste, user dissatisfaction | Medium | Soak on plate, enzymatic detergent, jets, avoid burning; consumable pans; scraper tools |
| R5 | Hard water scale blocks nozzles and coats heaters | Reduced cleaning, failures | High without softening | Softener + descale programme, drift detection |
| R6 | Turbidity "false clean" from detergent | Undetected soil | Medium | Measure only fresh-water rinse; multi-sensor logic; camera |
| R7 | Cross-contamination via gripper or transport surfaces | Pathogen or allergen transfer | Medium | Two grippers or gripper wash, handle zones, pass-through chamber, raw/RTE flags |
| R8 | 3D-printed parts used in food contact "because it is convenient" | Bacteria reservoirs, migration | Medium | Rule 13; design review V3 enforces; catalogue of allowed printed parts |
| R9 | Pests enter through incoming packages (moths, weevils) | Storage infestation | Medium | Freeze quarantine, hard sealed boxes, dry-store RH |
| R10 | Power budget of 3.6 kW cannot sustain parallel wash + cook + steam | Long cycles, delays | Medium | Power manager, schedule wash off-peak, hot buffer |
| R11 | Legionella in warm stagnant lines | Health risk | Low-Medium | Hot buffer >= 60 deg C or none, flush, no dead legs |
| R12 | Municipal wastewater by-laws vs sieve discharge | Legal | Low | Sieve to bin, no macerator; check local rule |
| R13 | Chemical residue (alkaline detergent) left on items | Chemical hazard | Low-Medium | Conductivity/pH checks in final rinse; full fresh rinse |
| R14 | Consumable refill frequency exceeds "rare" | User dissatisfaction | Medium | Cartridge sizing, low dosing, counters, service plan |
| R15 | Standards and certification burden if sold as machinery/food-equipment (CE, EN 1672-2, LFGB, NSF) | Time and cost | High if commercialised | Plan third-party testing (EHEDG cleanability test, migration tests) early |

---

## 14. Sources (retrieved during this research)

Hygienic design and standards
* EHEDG Doc 8 2nd edition (2004) - https://www.goudsmitmagnetics.com/uploads/pdf/ehedg-doc-eng.pdf (PDF not parseable; content via summaries)
* EHEDG Doc 8 3rd edition (2018) - https://thefoodtech.com/wp-content/uploads/2020/08/Principios-diseno-higienico.pdf (403; via search summary)
* EHEDG Doc 8 summary on Food-Info - https://www.food-info.net/uk/eng/docs/doc8.htm
* EHEDG guideline list - https://www.food-info.net/uk/eng/ehedgdocs.htm
* EHEDG GL 13 description - https://www.ehedg.org/guidelines-working-groups/guidelines/guidelines/guidelines/guidelines/detail/hygienic-design-of-equipment-for-open-processing
* Hygienic design of equipment (Food Safety Magazine) - https://www.food-safety.com/articles/4350-hygienic-design-of-equipment-in-food-processing
* EN 1672-2 - https://nhkmachineryparts.com/en-1672-2-hygiene-requirements/ ; EN ISO 14159 - https://webstore.ansi.org/standards/iso/iso141592002
* NSF/ANSI 51 zones - https://webstore.ansi.org/standards/nsf/nsfansi512025 ; https://blog.ansi.org/ansi/nsf-ansi-51-2025-food-equipment-materials/ ; https://www.nsf.org/nsf-standards/standards-portfolio/food-equipment-standards
* 3-A hygienic design presentation - https://my.3-a.org/Portals/93/Documents/Annual%20Meetings%20Presentations/May1_Basics_02_Hygienic%20Design%20Considerations%20and%20Techniques.pdf (image PDF, not readable)

Cleaning methods
* Sinner's circle (Miele) - https://m.miele.com/en/com/sinners-circle-5149.htm ; (Kaercher) https://www.kaercher.com/int/home-garden/know-how/the-sinner-s-circle.html ; https://en.wikipedia.org/wiki/Sinner%27s_circle
* Spray balls/rotary heads - https://www.gea.com/en/products/cleaners-sterilizers/tank-cleaning/static-cleaners/spray-balls-tank-cleaner/ ; https://portal.spray.com/en-us/products/tj9b-b ; https://nozzle-pro.com/pages/tank-vessel-cleaning-spray-nozzles
* Clean-in-place - https://en.wikipedia.org/wiki/Clean-in-place
* Dishwasher - https://en.wikipedia.org/wiki/Dishwasher ; Bosch brochure https://media3.bosch-home.com/Documents/MCDOC02945851_BOS-Dishwasher-Brochure-Lores-20181123-v2.pdf ; Bosch HygienePlus https://www.bosch-home.com/qa/en/experience-bosch/innovations/dishwasher-hygiene-plus
* Steam generators - https://www.mieleusa.com/product/8538193/-steam-generator-3-3kw-230v ; https://www.globalspec.com/industrial-directory/2_kw_steam_generators
* Instantaneous heater formula - https://showerpowerbooster.co.uk/blog/flow-rate-calculations-water-heater-boosting/
* Ultrasonic cleaning - https://en.wikipedia.org/wiki/Ultrasonic_cleaning ; https://crest-ultrasonics.com/choosing-the-right-ultrasonic-frequency-for-effective-industrial-cleaning/
* UV-C on food-contact surfaces - https://www.frontiersin.org/journals/food-science-and-technology/articles/10.3389/frfst.2023.1182765/full ; https://www.mdpi.com/2304-8158/10/7/1459 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC12841400/
* Electrolysed water - https://www.frontiersin.org/journals/sustainable-food-systems/articles/10.3389/fsufs.2023.1007967/full ; http://dx.doi.org/10.3390/foods5020042
* Self-cleaning/pyrolytic ovens - https://en.wikipedia.org/wiki/Self-cleaning_oven ; https://www.miele.co.uk/cs/kitchen/inspiration-advice/discover-miele-self-cleaning-ovens-1383
* Enzymatic dishwashing - https://www.novonesis.com/en/biosolutions/household-care/dish/automatic-dish-wash ; https://www.ikw.org/fileadmin/IKW_Dateien/downloads/Haushaltspflege/HP_Dishwasher-Part_A_e.pdf
* Cookware coatings - https://www.ppg.com/en-US/industrialcoatings/industrial-blog/testing-standard-for-sol-gel-non-stick ; https://prudentreviews.com/ceramic-cookware-pros-and-cons/ ; https://gemixx.com/feeds/blog/ceramic-enamel-cookware

Materials and 3D printing
* Regulation (EU) 10/2011 - https://eur-lex.europa.eu/eli/reg/2011/10/oj/eng ; https://www.intertek.com/housewares-home-decor/food-contact-articles-testing/eu-food-contact-materials/ ; https://measurlabs.com/blog/plastic-food-contact-material-regulation-and-testing-eu/
* Prusa food-grade printing - https://blog.prusa3d.com/how-to-make-food-grade-3d-printed-models_40666/
* Formlabs - https://formlabs.com/blog/guide-to-food-safe-3d-printing/
* Utah Valley University study - https://www.researchgate.net/publication/373174194_Sanitation_Effectiveness_of_3D-printed_Parts_for_Food_and_Medical_Applications ; https://www.uvu.edu/cet/printlab/
* PA12 SiOxCyHz coating - https://pmc.ncbi.nlm.nih.gov/articles/PMC12196969/
* Food-safe SLS/MJF PA12 - https://craftcloud3d.com/en/material-guide/food-safe-sls-mjf-nylon-pa12 ; https://store.sinterit.com/blogs/sls-3d-printing/is-3d-printing-material-food-safe-what-you-need-to-know-before-using-printed-parts
* Food-safe PETG - https://us.qidi3d.com/blogs/print-lab/is-petg-food-safe-cookie-cutters ; https://spoolhound.com/food-safety-guide

Food safety
* FSIS temperatures - https://www.fsis.usda.gov/food-safety/safe-food-handling-and-preparation/food-safety-basics/how-temperatures-affect-food ; https://www.fsis.usda.gov/food-safety/safe-food-handling-and-preparation/food-safety-basics/doneness-versus-safety ; https://www.fsis.usda.gov/food-safety/safe-food-handling-and-preparation/poultry/chicken-farm-table
* Minnesota Dept. of Health - https://www.health.state.mn.us/people/foodsafety/cook/cooktemp.html
* Danger zone - https://en.wikipedia.org/wiki/Danger_zone_(food_safety)
* Cooling of cooked meat - https://meathaccp.wisc.edu/validation/cooling.html
* Regulation (EC) 852/2004 - https://eur-lex.europa.eu/eli/reg/2004/852/oj/eng ; German ship-hygiene guidance with CCP 65 deg C - https://www.deutsche-flagge.de/de/redaktion/dokumente/dokumente-dienststelle/leitfaden-hygiene-engl.pdf (search summary)
* Biofilm on stainless - https://pmc.ncbi.nlm.nih.gov/articles/PMC5498454/ ; https://www.sciencedirect.com/science/article/pii/S0168160522003609 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC7825347/

Robots, actuators, bearings
* Staubli HE - https://www.staubli.com/global/en/robotics/products/industrial-robots/hygienic-humid.html ; https://www.provisioneronline.com/articles/116085-staubli-showcases-humid-environment-robots-for-processing-operations-at-ippe ; https://www.automate.org/robotics/news/staubli-drives-food-processing-and-packaging-solutions-with-their-hygienic-robot-series
* FANUC food robots - https://www.fanuc.eu/eu-en/product/robot/m-20id25-food ; https://www.fanucamerica.com/products/robot/m-20id-25-food
* Hygienic actuators - https://www.tolomatic.com/blog/keeping-it-clean-hygienic-linear-actuators-for-food-safety/ ; https://www.tolomatic.com/blog/electric-linear-actuator-is-clean-in-place-washdown-ready/ ; https://linmot.com/products/stainless-steel-motors/
* igus food-contact bearings - https://www.igus.eu/plain-bearing/materials/food-contact ; https://www.igus.com/industry/food-and-packaging/fda-and-eu-compliant-products

Pests, waste
* Pantry moths/weevils - https://extension.umd.edu/resource/indian-meal-moth ; https://extension.umd.edu/resource/rice-and-granary-weevils ; https://www.thekitchn.com/how-to-get-rid-of-weevils-140955 ; https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5614616/
* Waste disposers in DE/EU - https://de.wikipedia.org/wiki/K%C3%BCchenabfallzerkleinerer ; https://www.myhomebook.de/service/abfallzerkleinerer-haecksler-spuele
* Grease separators (EN 1825, DIN 4040) - https://stadt.muenchen.de/infos/umgang-mit-fetthaltigem-abwasser.html ; https://www.aco-haustechnik.de/loesungen/abscheidetechnik/fettabscheider/ ; https://fettcheck.de/wissensdatenbank/ratgeber/fettabscheider-pflicht-wer-braucht

Verification
* Dishwasher turbidity/conductivity - https://eureka.patsnap.com/blog/scout-report/soil-sensing-dishwashers-turbidity-detection-cycle-optimization-and-false-clean-risk/ ; https://patents.google.com/patent/US6544344B2/en ; https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/8578951
