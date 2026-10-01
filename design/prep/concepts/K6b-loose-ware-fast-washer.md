# K6b — Loose ware and fast washer, improved (round P5a)

Improvement of `design/prep/concepts/K6-loose-ware-fast-washer.md` (K6) per
`design/prep/round2/00-improvement-brief.md`, against DECISIONS #1–#28 and the critiques C1–C5.
Nothing was built or tested. Numbers are estimates [E] unless tagged: [K] known practice, [C] calculated
here, [D] from a concept document, [C1]…[C5] from a critique.

**Core idea kept:** nothing that touches food is fixed to the machine. Food is worked in plain loose ware
(GN trays, round pots, plain steel tools) that all carry one grip feature; one Cartesian manipulator
handles everything; force and speed come from a few fixed stations; soiled ware is washed in a fast
washer inside the machine and verified item by item.

---

## 0. Brainstorm

Notes per concept document, written while reading (ideas for K6b, each with a quick verdict).

### 0.1 From K1 (ceiling turret cell)

| # | Idea | Verdict |
|---|---|---|
| I1 | Hermaphroditic pan pair: half stubs plus a hook tab, the upper pan set 8 mm off-centre and slid sideways so the far side is hooked; the pair is held on its own axis | **take**: cures K6's one-sided pair grip (C3 K6-2) with a passive far-side hook |
| I2 | Cooking tools ride on a V-saddle on the rim of their own pot between uses | **take**: no tool returns to a store during cooking, fewer long moves |
| I3 | Tool rail as one item of ware (5 tools in, 5 tools out, one grip) | **take** as tool racks: cuts the return moves R by about 3 × |
| I4 | One turntable pedestal: board, mixing bowl, spin basket, carousel under the ram | **take, modified**: one canned deck spindle that turns slowly (board, bowl) and fast (blender, spin); a turning board gives a fixed knife every cutting direction |
| I5 | Deck hatch above an under-deck wash chamber, soiled ware leaves straight down | **take**: basis of the "bench over the washer" layout |
| I6 | Front door as serving hatch, because all moving parts retract | maybe: saves a hatch drawer, costs a wash-down of the door zone after serving |
| I7 | Air corer, pipette barrels, drain wand through a rod bore | reject: fluid paths in the gripper (C2 R-10), seals |
| I8 | Spice wand through a wiper insert of the spice box (0.1 mL steps) | maybe: better small doses than a spoon; needs a box insert |

### 0.2 From K2 (vessel stack and inversion)

| # | Idea | Verdict |
|---|---|---|
| I9 | Load pins in the jaws: every transfer is weighed (±5 g), a mis-seat or a drop is seen at once | **take**: the cheapest reliability gain for 100 grips; also gives "pour by weight" without carrying to a scale |
| I10 | Partial inversion by weight: roll to 95–130° and back while the jaws show how much has crossed | **take**: portioning sauce, layering, dosing from a carried vessel |
| I11 | Closed pair tumbled (toss salad, coat in flour or crumbs, oil fries, shake-peel garlic) | **take**: one roll axis does it with any lidded GN pair; breading without tongs marks |
| I12 | Press column standing over a hob position: rice, purée, knead in the cooking pot | maybe: saves a transfer, but puts the tube over steam; keep the press on the cold bench, let the cooking pot stand under the tube cold |
| I13 | Grease by spin, flour by tumbling, release by a 3 s induction pulse | **take**: the tin stands on a hob for the pulse, no extra part |
| I14 | Rinse seat: one funnel for drain, cold flush, waste strainer and jaw rinse | **take**: becomes the K6b drain hopper with the chuck rinse |
| I15 | Spin-spread batter: pan turned at 150 rpm for 2 s | **take** on the turning hob positions: even crêpes without a two-axis swirl |
| I16 | Rim spool with neck jaws; hourglass dock (5 actuators); drain stalk with pump | reject: custom spun ware, actuators, fluid path |
| I17 | Sweep knife clipped to the rim of a turning receiving vessel sets the dice length | maybe: removes the cut-off slide in open U-rails (a C2 crevice), needs a turning vessel under the tube |

### 0.3 From K3 (drum and belt line)

| # | Idea | Verdict |
|---|---|---|
| I18 | Pour about the lip: the tilt axis passes through the pouring lip, so the pour point is fixed | **take as a motion rule**: X/Y/Z compensate the wrist roll so every vessel pours about its own lip (no new axis) |
| I19 | Rumbler mode: knurled floor disc, the charge held back by a still scraper, water spray; 1.5 kg in 3 min | **take**: a knurled disc insert in the 6.5 L pot on a turning hob position with the hung scraper arm is a raw-potato peeler with no new drive (GP-P2) |
| I20 | Carriages driven by a magnet follower inside a sealed stainless tube (400 N), no penetration | maybe: would remove the Z sealing band of the mast; needs the magnet rig that decides K8 |
| I21 | Bought vegetable-cutter discs (slice, grate, dice, sticks) driven from one spindle | **take, as bought household food-processor discs** on the deck spindle: grating and fine slicing that a press does badly; #28 prefers bought parts |
| I22 | Tool caddy that carries all arm heads to the washer at once | **take** (same as I3) |
| I23 | Belt, gates, pocket former, drum wok | reject: fixed food surfaces and 25 actuators; not loose ware |

### 0.4 From K4 (shuttle mat)

| # | Idea | Verdict |
|---|---|---|
| I24 | Polar placement: turntable angle plus a linear position reaches every point of a dish | **take**: plates on the deck spindle turning slowly; tongs or ladle stay on one line; also gives a fixed knife any cutting direction (with I4) |
| I25 | Dump port: a narrow funnel mouth in the deck, pot water poured into it, waste never passes over a vessel | **take**: the K6b drain hopper replaces the sink |
| I26 | ENVELOPE: a sheet folded back over sticky food, the roller works on its back (cling-film method) | **take, with a loose silicone mat**: rolling sticky dough and flattening meat without the roller touching food |
| I27 | Passive scrapers hung on fixed forks above each turning position | **take** (K6 had anchor pins; keep) |
| I28 | White mat under a top camera as an inspection background | **take**: white HDPE board as the vision background for cutting and checking |
| I29 | Electro-permanent magnet shoe on a ferritic dovetail tab | reject: a hold that fails by falling, magnetic soil (C3 X4) |
| I30 | Mat cassettes, slab–strip–chop dicing, 22 rotary passages | reject: wound wet elastomer surfaces (C2 K4-1) and seals |

### 0.5 From K5 (ram-and-die column)

| # | Idea | Verdict |
|---|---|---|
| I31 | Former die Ø 80 / Ø 45 with a cut-off: patties and dumpling portions by stroke, ±5 % mass | **take** as two end plates of the K6 press tube (−6 grips in B3) |
| I32 | Slot die 120 × 2: mustard, sauce or tomato as an even ribbon | **take** as an end plate of the small tube: the Rouladen mustard stripe that stops 35 mm before the flap edge |
| I33 | Whisk bar hung on the pot rim, pot turns under it (béchamel, custard, scrambled egg) | **take**: continuous whisking on a turning position without the deck spindle; second scraper-type part |
| I34 | Loose-floor springform and loaf tin for unmoulding by push-up | **take** (C1 rank 12): unmoulding without a second inversion, cake dome-up |
| I35 | Rasp can on a rotating position for potatoes | **take** (same as I19) |
| I36 | Frying book: two hinged GN pans flip everything in hot fat, guided | maybe: the safest hot-fat flip (C3), but two actuators and seals beside fat; K6b uses the passive hooked pair plus a lift rack instead |
| I37 | Ram foot that picks the piston by a magnet; the ram never touches food | **take in spirit**: the press arm carries the piston in an open fork (K6 had this) |
| I38 | Tubes pigged and washed in place with a bore camera; die carousel; 8 kN C-frame; plunger kneading | reject: fixed food surfaces and unproven kneading; K6 kneads in a turning pot |

### 0.6 From K8 (sealed tub, magnetic puck)

| # | Idea | Verdict |
|---|---|---|
| I39 | Canned radial coupling in a deep-drawn thimble welded into the floor: no seal, no axial force (S: 1.5 Nm, 6000 rpm) | **take** for the K6b deck spindle; the thimble is also the central column that bought food-processor bowls already have, so bowls and rotors slide over it |
| I40 | Slide heavy vessels on a flush floor instead of lifting them (24 N for a 12 kg pot); oven floor level with the floor | **take**: braiser, roasting tray and full pots are pushed and pulled by their tang along a flush deck into the oven; cures the overloaded tang (C3 K6-2) for the heaviest loads |
| I41 | Lever knife with a fulcrum eye on the board bracket (2.5 : 1) | **take**: halves cabbage, celeriac and pumpkin with the 100 N gantry (C1 K6-9) |
| I42 | Graded wash programmes: tool rinse, red-to-green rinse with A0 ≈ 60, short wash, full wash, intensive | **take** for the K6b well |
| I43 | The manipulators carry every item through a fixed jet plane (no racks, programmed path) | reject as the main washer: 40 wash moves per meal on the one gripper; keep the jet gate for the chuck and quick tool rinses |
| I44 | Everything retracts and the whole chamber is washed after a frying meal | **take in part**: per-meal wash of the hob zone with fixed nozzles and a dry-out fan (C2 K6-1) instead of daily only |
| I45 | Magnetic pucks through the wall, swept GN scraper, Y-slide, planar motor | reject: eight unproven principles; K6 stays with proven axes |

### 0.7 Own new ideas

| # | Idea | Verdict |
|---|---|---|
| I46 | **Bench over the washer**: the single wash well lies under the work bench; its insulated lid is the bench plate and slides away under the hatch strip when the bench is empty | **take**: saves the 395 mm well slot; washing happens mostly when the bench is free (after hand-over) |
| I47 | **The well also washes the dishes** on tanged carriers (plates on edge, glasses, cutlery basket) | **take**: removes the second washer (C4 K6-6); the machine's only washer, as C4 9.9 demands |
| I48 | **Hot water from a bought 30 L under-sink heater**, charged only while the oven is off; the well itself heats nothing during cooking | **take**: wash without power while the oven heats (C4 K6-2); household part (#28) |
| I49 | **Wash after hand-over, not during the meal**: the clean stock covers the meal (CAP-030); only red-to-green turnarounds are washed during cooking | **take**: fewer hot open lids in the bay, quieter dinner preparation, slower and quieter cycle allowed |
| I50 | **Spine tang**: the tang is the end of a 200 mm flat bar welded under the flange of a GN tray, sealed all round | **take**: spreads the 6.4 Nm over 200 mm of rim (C3 K6-2) |
| I51 | **One wrist axis**: roll about the chuck axis, chuck pointing along +X; the roll axis is also the tang axis, so pairs invert about their own joint plane, vessels pour sideways, the spit turns | **take**: −1 axis, −1 lip seal, −1 sealed housing above food |
| I52 | **Remote-centre tool moves**: X/Y/Z follow the roll so that a ladle, spoon or knife turns about its own head (≤ 70°) | **take**: replaces the second wrist axis for tools |
| I53 | **Rice in the skin as a generic peeler**: cooked potato, banana, avocado, cooked squash, tomato (passata), cooked apple pass the 3 mm plate, skin, seeds and cores stay in the tube (food-mill practice) | **take**: one press plate peels and stones a dozen produce types for all purée and mash uses (#25) |
| I54 | **Press column at the front corner, tube standing on its own legs**: no bars across the bench | **take**: the mast passes behind it (C3 K6-1, fatal as drawn) |
| I55 | **Downdraft extraction slot between the two hob columns** (bought hob-extractor class) | **take**: fat aerosol is caught at pan level, so the bay walls and the manipulator stay cleaner (C2 K6-1) |
| I56 | **Twist nest**: a fixed silicone-lined cup holds one half of a stone fruit or avocado while the roll turns the other half on the fork | **take**: halve, twist, stone out with one hand |
| I57 | **Push-off stand for loose-floor tins**: the tin is lowered over a pedestal, the cake stays on the floor plate, dome up | **take**: no second inversion (C1 K6-6) |
| I58 | X axis behind a non-contact labyrinth with purge air instead of a sealing band | **take**: −1 band; the slot is at the rear top, never above an open vessel |
| I59 | Manual hatch drawer for 2 plates, pulled by the diner, interlocked | **take**: plating inside the cell (C4 4.5) without a serving actuator |
| I60 | Fine seasoning by levelled measuring spoons (1 / 5 mL) instead of a 300 g scale | **take**: recipes are written in spoons anyway; one load cell and its window less |

### 0.8 What is picked

Taken into K6b: I1–I3, I5, I9–I11, I13–I15, I18, I21 (bought Ø 140 slicing and grating discs in a
cutter cup on the spindle), I22, I25–I28, I31–I35, I37, I39–I42, I44, I46–I60. I4 and I24 are not taken:
a turning board needs deck room that the layout does not have; two knives (one per cutting direction)
are simpler. Kept as options with a rig: I19 (knurled rasp disc for raw roots), I20 (magnet-follower Z
carriage), I8 (spice wand). Rejected: the fluid paths, magnets as holders, mats, belts, drums, dies on
carousels and the frying book (actuators, seals, fixed food surfaces).

---

## 1. What changed and why

Effect columns: S simplicity, H hygiene, C coverage and food, R reliability, F system fit; ++ strong
gain, + gain, 0 no change, − loss.

| # | Problem (critique) | Change in K6b | S | H | C | R | F |
|---|---|---|---|---|---|---|---|
| 1 | **Width 2595 mm, 72 % of the machine** (C4 K6-1 fatal; C3 X3) | Dock removed (A1 of C5), one bench instead of two, the sink replaced by a drain hopper, the wash well moved **under the bench**; the cell now also holds the machine's only washer, the hatch and plating: **1855 mm** | + | 0 | 0 | 0 | ++ |
| 2 | **100–145 grips per meal** through one gripper (C3 K6-4, C4 K6-5, C5 S5) | Tool racks (one grip for five tools), tools resting on their pot rim, release straight into the well, Ø 80 former plate, hooked pairs, cutting straight into the cooking pot, load pins in the jaws that verify every grip: **mean 100 → 72 (2 persons: 64)**, full menus 130–145 → 92–102 | + | 0 | 0 | ++ | + |
| 3 | **10.7 m² open splash zone washed once a day** (C2 K6-1, C-3; HYG-045) | Bay 10.7 → 8.5 m²; downdraft slot between the hob columns; the 2.8 m² hob zone rinsed by fixed nozzles **after every cooked meal**, fan dry-out after every meal; daily full wash with a nozzle plan | 0 | ++ | 0 | 0 | 0 |
| 4 | **Gripper carries soil from tang to tang** (C2 K6-3) | Drip collar on every tang, trays included (spine tang); the chuck passes the jet gate on its way out of the well after every soiled grip (3 s, no detour), 10 s at 90 °C after class R; a "soiled chuck" may not touch clean ware (software interlock) | 0 | ++ | 0 | 0 | 0 |
| 5 | **Loud wells, no power while the oven heats** (C4 K6-2, K6-3; C3 K6-5, K6-6) | Rinse water from a 30 L under-sink heater charged only while the oven is off; washing mainly after hand-over; one insulated well under the bench, lid closed except while hanging; household-class pump, longer gentler cycle: **52–56 → 44–48 dB(A)**, 0 W of wash heating during cooking | + | + | 0 | + | ++ |
| 6 | **A second washer still needed for the dishes** (C4 K6-6) | Plates, glasses and cutlery go into the same well on tanged carriers; the hatch drawer is the return point | ++ | 0 | 0 | 0 | ++ |
| 7 | **Mast collides with its own press bars** (C3 K6-1, fatal as drawn) | No bars: the press column stands at the bench's front corner and parks low, the tube stands on its own legs; the mast passes behind | + | 0 | 0 | ++ | 0 |
| 8 | **Tang on a thin GN rim overloaded, pair gapes at the far side** (C3 K6-2) | Spine tang (200 mm bar under the flange); heavy vessels are slid on a flush deck, not lifted; pairs are locked at the far side by a passive hook (K1's hook tab) | 0 | 0 | + | ++ | 0 |
| 9 | "Every load disinfected" not shown (C2 K6-4, C-1) | Recirculated final rinse held ≥ 60 s at ≥ 82 °C, A0 ≥ 90 at the surface, proven with a logger on the coldest item | 0 | ++ | 0 | 0 | 0 |
| 10 | Well is dirty entry, wet parking and clean store at once (C2 K6-5) | Clean items leave the well straight into the closed tower store; lid with a drip lip; nothing clean waits in the well | 0 | + | 0 | 0 | 0 |
| 11 | Sink does four jobs (C2 K6-6) | No sink. Produce is washed in its own red pot basket (dunk wash, GP-W1); the drain hopper takes only waste and dumped water | + | + | 0 | 0 | + |
| 12 | Frying fat above 30 mL has no path (C2 K6-7) | Fat cup (ware): cooled fat goes to the bio bin onto the peelings, never to the drain | 0 | + | 0 | 0 | 0 |
| 13 | Manipulator above food: 3 bands, 4 lip seals (C2 K6-2, C3 X10) | X axis behind a contact-free labyrinth with purge air; wrist with one roll axis; Y band faces up into a gutter: **7 → 5 dynamic seals**, none dripping into a vessel | + | + | 0 | + | 0 |
| 14 | Coverage claim overstated; peppers, beans, celeriac, diced onion bought (C1 K6-1, K6-2, K6-9) | Generic peeling and stoning (#25) with three passive mechanisms; G-produce corer, trimming, dunk-wash and zest modules hosted; lever knife: **central 230 → 232 meals = 93.5 %** (C1 standard N) | 0 | 0 | + | 0 | 0 |
| 15 | Rouladen untied and turned with tongs; gravy without roasted onion and paste (C1 K6-3, A-2, A-6) | Dry floured flap, mustard as a ribbon that stops 35 mm short, GA-20 skewer raft, sear, roast onion and paste in the fond, deglaze | 0 | 0 | ++ | + | 0 |
| 16 | Bratkartoffeln from parboiled slices, wet mash, Schnitzel in 1.3 mm of fat (C1 K6-4, K6-5, K6-7, A-3) | Potatoes boiled in the skin and cooled before slicing; mash from halves riced in the skin; Schnitzel in 180 mL in Ø 240 pans (4 mm), turned by a lift-rack pair | 0 | 0 | ++ | 0 | 0 |
| 17 | Cake leaves base-up (C1 K6-6) | Loose-floor tins and a push-off stand: dome up, no second inversion | 0 | 0 | + | + | 0 |
| 18 | Mast twists, settles slowly (C3 K6-3) | X travel 1.78 → 1.23 m, closed torsion tube inside the mast, 2 m/s² | 0 | 0 | 0 | + | 0 |
| 19 | Oven turned 90°, door swings over the wells (C4 K6-7, C3 X6) | Household compact oven at the deck end, cavity floor flush with the deck, its door replaced by a drop-down door into the plinth (#24): trays slide in, nothing swings | + | 0 | 0 | + | + |
| 20 | 16 actuators (C5: 12 normalised) | Dock, strainer drive, two lid drives and the wrist spin removed: **10 stated, 9 normalised** | ++ | 0 | 0 | + | + |
| 21 | 93 loose items, about 85 custom types (C5 S7, S8) | Sized for 4 persons (#19), duplicates cut, tools merged (spatula-tongs, knife and lever knife): **78 items**, about 60 custom types | + | + | 0 | + | + |
| 22 | Hook-hinged egg cracker, worst cassette (C2 K6-8, C5) | Bottom-strike cracker whose two halves lie loose on one pin (G-assembly 7.2); beaten egg strained through the 2 mm plate | + | + | 0 | + | 0 |
| 23 | Cost 22 k€, re-estimated 28–31 k€ (C3 K6-7); #28 target about €2 k for the machine part | Household appliances where they exist (oven, water heater, extractor, dishwasher wash parts), cheaper axes (closed-loop steppers), fewer custom parts; the €2 k target is still missed by about 5 × (section 6.4) | + | 0 | 0 | 0 | + |

---

## 2. The improved concept

### 2.1 Definition in one page

K6b is a stainless bay **1855 mm wide, 600 deep, 2200 high** that contains the whole cooking side of the
machine: preparation, four heated positions, the oven, plating, the hatch, and the machine's **only washer**
(ware and dishes). Nothing that touches food is fixed: food is worked in bought GN trays and round pots and
with plain steel tools, all carrying one grip feature (the tang). One hanging-mast gantry with a single
roll axis does all handling. Four fixed drives give force and speed where the gantry has none: a 3 kN
press, two turning hob positions, one seal-free spindle in the deck.

Seven rules define it:

1. **One tang, one chuck.** Every item carries the same flat tang 6 × 32 × 60 with two Ø 8 holes and a drip
   collar or dam; trays carry it on a 200 mm spine bar. The chuck's pins pass the holes (form fit) and two
   load pins weigh every grip. Pairs are locked at their far side by a passive hook.
2. **One wrist axis.** The chuck points along +X; the wrist rolls about that axis. Pairs therefore invert
   about their own joint plane, vessels pour sideways about their lip (X, Y, Z follow the roll), the spit
   turns produce, tools tip ≤ 70° about their own head.
3. **Heavy goes along the deck, not through the tang.** Deck, bench lid, hob glass and oven floor are flush;
   braiser, roasting tray and full pots are slid.
4. **Force and speed are stations**: press (dice, slice, rice-in-skin, form, juice, Spätzle), turning hob
   positions (stir, knead, fold, whisk, spin-spread, rasp-peel), deck spindle (blend, whip, spin, grate).
5. **Wash after hand-over** in one quiet well under the bench, with hot water stored before cooking; only
   red-to-green turnarounds are washed during the meal. Dishes use the same well.
6. **Soil stays low**: downdraft at the hob, the hob zone rinsed after every cooked meal, the bay dried
   after every meal, the chuck rinsed after every soiled grip.
7. **Sequence before duplication**: dry, ready-to-eat, raw vegetable, raw animal food last; red duplicates
   only for the spatula-tongs and one GN 1/3; raw meat never lies on the board.

### 2.2 Layout

Coordinates in mm: X along the wall from the inner left wall, Y from the inside of the front door (0) to
the rear wall (555), Z from the floor. Deck top Z 880.

```
FRONT VIEW (front door removed)                         outer 1855 W x 600 D x 2200 H, inner 1805
 Z
2200 +-------------------------------------------------------------------------------------------+
     | transport gallery (not K6b); box drop hatch above zone A                                  |
2100 +==== dry box: X rails and belt, purge fan, controls, 3 cameras =========================== +
1950 |  X labyrinth slot in the vertical rear face, Z 1900-1950, X 60..1290, gutter below |TOWER   |
     |DISH CABINET  |   mast 60x120, hangs at Y 485-555, travels X 60..1290           | store  |
1900 |Z 1560-1900,  |     ||  Z band on the mast's rear face                          | 5 rail |
     |flap          |     ||                                                          | levels,|
1560 |--------------|     ||   arm 80x80, Z 1110..1940 ===[Y carriage]                | roller |
     |BOX SHELF     |     ||                                  | drop link 150         | shutter|
1350 |Z 1350-1500   |     ||                            [roll wrist]=[chuck] -> +X    |Z 1295- |
     |(front only)  |  press column, parks low         T1, T3 pots (column 1)         | 1930   |
     |              |  |  tube on legs                                                |--------|
     |              |  |  [|||]                                                       | OVEN   |
 880 +=HATCH DRAWER=+==BENCH = WELL LID===+==== HOB 600 x 520, flush glass ====+ floor 880       |
     |press drive   | WASH WELL 300 x 320 | 4 induction modules, 2 ring drives,| household      |
     |bio bin 12 L  | x 420 deep (Z 440-  | downdraft fan + grease filter,     | compact oven,  |
     |(plinth       | 860); tank 8 L,     | electronics                        | drop door      |
     | drawer)      | pump, softener      |                                    | 30 L store     |
 100 +--------------+---------------------+------------------------------------+ 88 C, drain pump|
     0             280                   625                                1225              1805

TOP VIEW at deck level (Z 880)                                                rear wall Y 555
     +-------------+-----------+--------+---------------+---+---------------+-------------------+
 555 |             | HOPPER    |SPINDLE | T3  2.2 kW    | D | H4  2.2 kW    |                   |
     |  HATCH      | 150 x 170 |pocket  | turning ring  | O | plain         |                   |
     |  DRAWER     | + chuck   |Ø 170,  | Ø 240 pot     | W |   } bridge:   |   OVEN cavity     |
 370 |  280 x 520  | jet gate  |thimble +-------------- | N |   } one GN 2/3|   (floor flush    |
     |  2 plates   +-----------+--------+ T1  3.5 kW    | D |   } over both |    with the deck),|
     |  Ø <= 270,  | BENCH: well lid    | turning ring  | R | H2  3.5 kW    |    door on the    |
     |  heated     | hinged at X 290,   | Ø 240 pot     | A | plain         |    -X face        |
     |  60 C;      | GN 2/3 cones; press|               | F |               |                   |
  30 |  pulls out  | column o (X 295,   |               | T |               |                   |
     |  to -Y      | Y 30)              |               |   |               |                   |
   0 +-- front door (glazed, interlocked); hatch flap in it at X 0-280 ---------------------------+
     0            280       430        625     775    900 950    1075    1225                  1805
```

Width by function: hatch and plating 280, bench with well, press, hopper and spindle 345, hob 600, oven
and clean store 580, casing 50: **1855 mm**. The 280 mm of hatch, the washer and the dish store would
otherwise sit in a separate dish module (C4 3.1 budgets 600 mm for it).

### 2.3 Manipulator

| Axis | Travel | Drive | Force, speed | Seal |
|---|---|---|---|---|
| X | 1230 (wrist X 60…1290) | closed-loop servo-stepper 400 W, toothed belt, two profile rails in the ceiling dry box | 300 N, 0.8 m/s, 2 m/s² | **none**: the carriage passes a vertical labyrinth slot (four interleaved lips, 2 mm gaps, purge air outward, gutter below); contact-free |
| Z (arm on the mast) | 830 (arm Z 1110…1940) | stepper with brake, ball screw 16 × 10, inside the closed mast 60 × 120 with an inner torsion tube | 600 N, 0.3 m/s | steel sealing band on the mast's rear face (towards the wall), drip lip into a cup at the mast foot |
| Y (carriage on the arm) | 380 (wrist Y 60…440) | stepper, belt, inside the closed arm 80 × 80 | 200 N, 0.6 m/s | sealing band on the **top** face, inside a 15 mm gutter sloped 3° to the mast: nothing can drip off the band into a vessel |
| Roll (about the chuck axis, along +X) | ±200° (cable wrap) | servo 200 W, 20 : 1 gear, brake | 20 Nm, 0–150 rpm | one lip seal under an umbrella collar |
| Chuck | 2 × 22 mm | servo, screw, two parallel jaws, conical pins and through-drilled sockets; **two load pins** (±5 g to 6 kg) | 20–400 N, force-controlled | one rod lip seal (central drive rod) |

Payload 6 kg at the tang with the centre of mass 160 mm out (9.4 Nm on the roll axis, 50 % margin). Push
force at a tool 100 N. Repeatability ±0.3 mm; the pins and the cones on every rest take ±3 mm. The wrist
hangs 150 below the arm, so the arm passes over a lidded 4 L pot on the rear row (top Z 1010) with the
mast foot at Z 1060.

What the single roll axis does, with X, Y, Z following it ("remote centre"):

| Motion | How |
|---|---|
| Pour any vessel | roll about the tang axis tips it towards ±Y; Y and Z keep the lip still (pour about the lip, K3) |
| Invert a pair (pan pair, tray pair, rack pair, tin and stand) | the pair's tangs lie back to back on the pins; the roll axis lies in the joint plane, so the pair turns over in place |
| Spit | the fork is straight and coaxial with the chuck: roll at 30–150 rpm turns the produce past the peeler post |
| Tip a tool (ladle, spoon, knife bevel, spatula) | ≤ 70° about the tool head; the chuck stays above the head |
| Hang ware on edge in the well | roll 90° |
| Not possible | yaw of a tool in plan: knives come in two blade directions (X-cut and Y-cut); free-form plating flourishes |

### 2.4 Stations and drives

| Station | What it is | Actuators | Penetration and seal |
|---|---|---|---|
| Hatch drawer (zone A) | Drawer 280 × 520 at deck level, heated base 60 °C, two plate places; the diner pulls it out through the front flap when the machine has locked the gantry out; dirty dishes come back the same way on the carriers. Zone A is also where the wrist stands when the chuck grips a tang on the bench, so the drawer holds plates only during plating | none (manual pull, solenoid interlock) | flap gasket (static) |
| Box shelf (zone A, front, Z 1350) | The transport lowers an opened box (lid taken off outside, C4 R-4) through a ceiling hatch; the chuck takes it by its lug and tips it sideways over a tray on the bench; spoons and tongs reach into it on the shelf | none | ceiling hatch belongs to transport |
| Dish cabinet (zone A, Z 1560–1900) | Clean dish carriers behind a lift-up flap opened by the chuck | none | — |
| Bench (zone B) | Flush, insulated lid (25 mm sandwich, ribbed for the press load, 3 kg) over the wash well, with GN 2/3 locating cones. It hangs on two open lift-off pins at its left edge; the chuck lifts it by its lug (15 N) to vertical, where it stands as a splash screen between zones A and B. No scale: doses are weighed by the chuck's load pins as loss in weight of the held box or vessel (K2's partial inversion by weight) | none | none (open pins, washed in place) |
| Press | Column Ø 40 at the bench's front-left corner, arm 200, pulls down 3 kN, stroke 250; the first 25 mm swing the arm over the tube by a helical cam; **parked low and swung to the front edge** when idle, below the arm's path; the tube Ø 110 stands on its own three legs over the receiving vessel | 1 (servo screw under zone A) | scraper, drained lantern, dry seal |
| Drain hopper (zone B rear) | Funnel 150 × 170 with a tanged 2 mm strainer basket; two fan nozzles above it are the **chuck jet gate** (85–90 °C, 3–10 s) and the plate pre-rinse; outlet to drain, solids to the bio bin | none | — |
| Deck spindle (zone B rear) | Thimble Ø 40 × 60 deep-drawn and welded into a drained pocket Ø 170 × 120; inner magnet rotor on a 750 W motor, 0–6000 rpm, 1.5 Nm (K8's S). Bowl Ø 160 × 200 with a central column fits over it; rotors: blade, whisk, spin basket, disc cutter with bought Ø 140 slicing and grating discs | 1 | **none** (canned coupling) |
| Hob (zone C) | One glass field 600 × 520, four OEM induction modules (DEC-5). Column 1 (beside the bench): **T1** 3.5 kW front and **T3** 2.2 kW rear, each with a loose carrier ring on three PEEK rollers, one driven, 0–120 rpm, 20 Nm; scraper arms, kneading roller and whisk bar hook onto anchor pins on the rear wall (Ankarsrum principle). Column 2 (beside the oven): **H2** 3.5 kW front and **H4** 2.2 kW rear, plain, bridged for one GN 2/3 thermoplate, from where trays slide straight into the oven | 2 | roller posts in umbrella bosses, contact-free |
| Downdraft (zone C) | Slot 50 × 480 between the hob columns, bought hob-extractor fan, washable stainless baffle filter (ware) | fan only | — |
| Oven (zone D) | Household compact oven (45 cm class, 35–45 L, GN 2/3 shelf), cavity floor flush with the deck, its door replaced by a drop door that slides into the plinth (#24); trays and the braiser are slid in | 1 (door) | oven's own gasket |
| Clean store (zone D, above the oven) | Five rail levels behind a roller shutter that the chuck pushes up: GN nest, tool racks, press cassette, spindle ware, small fixtures | none | — |
| Wash well (under the bench) | Welded 1.4404 well 300 × 320 × 420, double wall with 20 mm insulation, comb of slots at the top (7 slots at 45 mm); wash parts of a household dishwasher (circulation pump 30 L/min, heater 2 kW, sump filter, softener, two dosing pumps) plus 8 L tank; hot rinse water from a bought 30 L under-sink heater at 88 °C | pumps only | — |

**Motion actuators: X, Z, Y, roll, chuck (5) + T3, T4 (2) + press (1) + spindle (1) + oven door (1) = 10.**
C5-normalised (without dock, egg module and oven door): **9**. Not counted: 3 pumps (wash, drain,
booster), 2 dosing pumps, about 10 solenoid valves, 2 fans, 4 induction modules, the two heaters.

**Dynamic seals in the splash zone: 5** — Z band, Y band, roll lip seal, chuck rod seal, press column.
Contact-free: X labyrinth, six roller posts, the spindle (canned), the well lid (rests in a drained
channel). No band drips into a vessel: the Y band faces up into its gutter, the Z band faces the wall, the press
column stands at the front edge and is parked low. The two wrist seals sit 100–150 mm in X beside the
tool head (the chuck points along X and the tools are L-shaped), so in most moves they are beside, not
above, the vessel; umbrella collars catch the rest (R-2 met in most, not all, moves).

### 2.5 Ware (78 food-contact items) and carriers

B = bought, B+ = bought with a welded tang or spine tang, C = custom (laser-cut, bent, welded, turned).

| Group | Items | No. | Make |
|---|---|---|---|
| Flat vessels | GN 2/3-20 (1), GN 2/3-65 (2), GN 2/3 lid (1), thermoplate GN 2/3-40 (2, a pair), thermoplate GN 2/3-65 braiser (1), GN 1/3-40 (3, one red), loaf tin GN 1/3-65 with loose floor (2 parts) | 12 | B+ |
| Round vessels | pot Ø 240 × 160 6.5 L with perforated basket (2), pots Ø 240 × 100 4 L (2), shallow pans Ø 240 × 40, identical and hermaphroditic (tang, hook tab and catch: either is the flip partner) (2), saucepan Ø 160 × 80 (1, also the 1-person braiser), lids Ø 240 (2, one with a splash hole), Ø 160 (1), lift racks Ø 225 perforated, a pair with hook (2) | 12 | B+ / C |
| Spindle ware | bowl Ø 160 × 200 with central column, blade rotor, whisk rotor, spin basket, disc cutter cup, slicing disc, grating disc | 7 | B+ (bought processor discs), C |
| Tools (tang, collar, L-stem) | spatula-tongs (one-piece sprung U, one jaw a 0.6 mm turner blade) red and green (2), knife-X 250 scalloped (slices, carves), knife-Y 200 with hook tip for the board's fulcrum eye (lever knife), ladle 100 mL with pour lip, measuring spoon 1/5 mL, silicone spatula, spit fork (straight, coaxial), ring Ø 80, presser plate, roller with gauge bars, peeler post (sprung Y-blade, depth-shoe paring blade 2.5/5 mm, fine rasp), core probe | 14 | C (bought blades, probe) |
| Press cassette | tube Ø 110 on legs, piston, cut-off slide, plates: open, grid 6, grid 10, ricer 3 mm, Spätzle 8, wedger-corer, former Ø 55 | 10 | C (plates partly bought) |
| Small tube | tube Ø 45, piston, plate 2 mm (garlic in skin, egg strainer), slot plate 40 × 2 (mustard ribbon), knife ring Ø 30 (pushes banana sections out of their skin) | 5 | C |
| Produce | corer tubes Ø 14, Ø 22 and Ø 42 with ejector (GP-61 family), stab-and-twist nest (silicone-lined V cup with end stop) | 4 | C |
| Turning-position set | scraper arm (2), kneading roller arm, whisk bar | 4 | C |
| Egg | bottom-strike cracker (two halves loose on one pin), slotted saucer | 2 | C |
| Rouladen | silicone apron with hem bars, comb cradle with tine guides, two two-tine raft forks (GA-20; one raft = 4 rolls) | 4 | C |
| Boards and fixtures | white HDPE board GN 2/3 with fulcrum eye, silicone mat, comb fence, push-off stand for loose-floor tins | 4 | B+ / C |
| **Food-contact total** | | **78** (K6: 93) | |
| Service ware | hopper strainer basket, downdraft baffle filter, fat cup | 3 | C |
| Carriers | tool racks (3, five tools each); dish carriers: plates on edge (3 × 4), glasses (4), cutlery basket | 3 + 5 | C |

Where everything lives: round vessels on the hob (6.5 L with basket on T1, 4 L on T3, 4 L with the
saucepan inside on H4, pan stack on H2); thermoplates in the cold oven; everything else in the tower
store; dishes in the dish cabinet. A reference meal uses 30–45 items.

### 2.6 Interfaces

| Interface | K6b offers | K6b asks |
|---|---|---|
| Box port | passive shelf at the front of zone A, Z 1350–1500, under a ceiling hatch | transport lowers an **opened** box (lid removed at a lid station); GN 1/6 and 1/3 PP boxes with a moulded **lug with two Ø 8 holes** on one short end; inner corner radius ≥ 10 for spoons |
| Transport | nothing else: ware never leaves the bay | — |
| Serving | plated food in the hatch drawer, 2 plates per drawer cycle (4 persons: two cycles within SRV-009's 3 min); whole vessels are not handed over | diner pulls the drawer |
| Dish return | the same drawer: diner slots plates into the carrier in the drawer and puts cutlery into the basket; the machine scrapes, pre-rinses over the hopper, washes, dries, stores | DEC-6 unchanged: the human only brings the dishes to the hatch |
| Utilities | — | 400 V 3N~; cold water 2.2–5 bar; drain; extraction outlet or recirculation filter; the 30 L heater on its own phase while the oven is off |
| Waste | closed 12 L bio bin under zone A, opened through a plinth drawer | emptied weekly by the human or by transport |

---

## 3. How the hard operations work now

Times for 4 persons [E]. G = gripper cycles (grip and release of one item). Confidence H / M / L as in
the concept documents.

### 3.1 Generic peeling, coring and stoning (#25, PRP-039)

Three passive mechanisms, all worked by the gantry, cover the PRP-039 list:

* **P1 Spit and post.** The straight spit fork sits coaxially in the chuck; the produce is stabbed by
  pushing it along +X into the stab nest's end stop (30–60 N), then turned by the roll axis at 30–150 rpm
  and drawn pole to pole past the **peeler post**, which carries three edges on one flexure: a sprung
  Y-blade (thin skins), a paring blade with a depth shoe of 2.5 or 5 mm (GP-11 / GP-Z4 geometry: thick or
  knobbly skins, pith), and a fine rasp (zest, GP-Z1). The knife cuts off the fork-end cap; a stripping
  slot pulls the piece off. Peel falls into the hopper.
* **P2 Rice in the skin.** The press tube with the 3 mm ricer plate stands over the receiving pot; cooked
  or soft produce goes in with skin, seeds and cores; the flesh passes, skins, seeds and cores stay as a mat
  on the plate and are tipped into the hopper. This is food-mill and potato-ricer practice [K].
* **P3 Tube cutters.** Corer tubes Ø 14 / 22 / 42 with ejector pushed by the gantry Z (≤ 100 N) or the
  press; the wedger-corer plate; the knife ring Ø 30 on the small tube pushes banana sections out of their
  skin. Halving round a stone is a knife plunge to the stone while the roll turns the fruit on a shallow
  fork, then a **twist** with the other half held in the twist nest.

| Produce | Use | Route | Loss, time | Conf. |
|---|---|---|---|---|
| Potato | Salzkartoffeln, raw dishes | P1 Y-blade, 150 rpm | 15–20 %, 15 s each | M–H |
| Potato | mash, Klöße, purée | boiled as halves in the skin, P2 | 3–6 %, 60 s per kg | H |
| Potato | Bratkartoffeln, salad | boiled in the skin, cooled, P1 paring blade at 1 mm (cooked skin is 0.5 mm) | 6–10 %, 12 s each | M |
| Carrot, parsnip, kohlrabi, raw beetroot | | P1 Y-blade; carrots over 150 mm halved first | 10–20 % | M–H |
| Celeriac, ginger, pumpkin (raw) | | halved or quartered by the lever knife; P1 paring blade 5 mm in facets | 25–30 % | M |
| Pumpkin, squash (cooked) | soup, purée | roasted in wedges, P2 | 10 % | H |
| White asparagus | | spit with a thin 2-prong fork in the cut end, tip resting in the post's V-guide, 30 rpm, Y-blade drawn from 30 mm below the head | 20 %, 20 s each | M–L |
| Cucumber, courgette | | P1 Y-blade, full or striped; V-guide against whip | 10 % | M |
| Apple, pear | | P1 Y-blade; core by the Ø 22 tube (whole) or the wedger-corer plate (wedges) | 15–20 % | H |
| Kiwi | | top and tail by knife, P1 Y-blade | 15 % | M |
| Mango | | stands stalk up in the twist nest; camera finds the flat stone; knife-Y takes two cheeks 7 mm off the centre plane; purée: cheeks through P2; cubes: grid scored to the skin (Z depth), paring blade slides under the skin (fish-skinning geometry) | 30–35 % | M (purée), M–L (cubes) |
| Avocado | guacamole, salad | shallow fork in the stalk end, knife plunged to the stone while the roll turns 360°, twist in the nest, stone levered out by the spoon; guacamole: halves through P2 (skin stays); slices: spoon scoop along the skin (camera-guided) | 25 % | M (guacamole), M–L (slices) |
| Banana | bread, smoothie | ends cut, 40 mm sections through P2 | 35 % (skin) | M |
| Banana | slices | ends cut, 40 mm sections stood on the Ø 30 knife ring, piston pushes the flesh out | 20–25 % | M |
| Orange, lemon | zest; peeled rounds; juice | P1 rasp at 2–4 N (zest); P1 paring blade 5 mm (à vif, rounds); halves through P2 (juice, skin stays) | — | H / M / H |
| Bell pepper | strips, stuffed | Ø 42 corer pushed from the stalk end in the nest, inverted rinse (GP-61); recovery: four cheeks by knife (GP-62) | 12 % | M–H |
| Chili | | cut with seeds (rule), or halved and scraped by the spoon | — | M |
| Tomato | core; passata; peel | Ø 14 corer; P2; blanch 30 s in the pot basket, cold dip, P1 paring blade at 1 mm | — | H / H / M |
| Peach, plum, apricot | | halve round the stone and twist (as avocado), stone out by spoon or Ø 22 tube; peach skin: blanch, P1 at 1 mm | 10–15 % | M |
| Cherries (S) | | Ø 14 tube pushes the stone out in the nest | 4 s each | M–L |
| Pineapple (S) | | top and tail, P1 paring blade 5 mm at 30 rpm (eyes stay), Ø 42 core | 40 % | L–M |
| Onion (upgrade, #9 baseline is bought peeled) | | GP-11 on the spit: top and tail cut, three slits by the 2.5 mm shoe, dry wipe, jet over the hopper | 10–15 % | M |
| Garlic | | cloves in the skin through the small tube's 2 mm plate (GP-17) | — | H |

**Distinct peeling and coring mechanisms: 3** (P1, P2, P3) plus the knife and the nest, which every
dish uses anyway. PRP-039 asks ≤ 3. Single-purpose parts: none. Segments of citrus are not offered
(rounds instead, class b).

### 3.2 Dice an onion

Peeled onion (bought, #9) in the V of the nest, root along X; knife-Y halves it through the root
(30–60 N). The halves go flat side down into the press tube (two per load) on the 6 mm grid; the piston
advances 6 mm per stroke of the cut-off slide (stroked by the chuck): brunoise of 6 mm, the root plate
stays on the grid and is pushed out at the end. The tube stands on its legs over the cooking pot itself
(cold, on the bench), so the dice need no intermediate tray. Two onions: 50 s, 4 G. Confidence H for
halves (C1 §5).

### 3.3 Rouladen: fill, roll, secure, sear, braise (8 rolls)

1. **Slices.** Butcher's slices arrive interleaved (request to ingestion) and are lifted by the
   spatula-tongs' blade slid under a corner; without interleaf, the top slice is peeled from a corner found
   by the camera (M–L, the shared G9 gap). Two slices lie side by side on the silicone apron in a GN 2/3-20
   with the trough insert at the start line.
2. **Fill.** Salt and pepper by spoon; mustard from the small tube's 40 × 2 slot plate as a ribbon drawn
   by an X move, stopping **35 mm before the flap edge**; the flap is salted and dusted with flour (seam
   glue, G-assembly 4.2); bacon strip (or diced bacon), pickle spear, onion strip laid on the first third by
   the spatula-tongs; the long edges folded in 15 mm by the tongs' blade.
3. **Roll.** The chuck takes the near hem bar and carries it over the far one: both slices roll at once
   (SM-079/-080) and drop off the apron end into the comb cradle, flap at 5 o'clock.
4. **Secure.** With four rolls in the cradle (in a GN 2/3-65), a two-tine raft fork is pushed through the
   cradle's guide slots and through all four rolls (30–60 N, GA-20). Two rafts for eight rolls.
5. **Sear.** The braiser (thermoplate GN 2/3-65) heats bridged on H2/H4 with 20 mL of oil; each raft is
   laid in seam-face down for 90 s, then turned once by the roll axis about the tines (the raft handle is a
   tang), browning two broad faces (about 60 % of the surface).
6. **Fond.** Rafts out onto the GN 2/3-65; sliced onion and tomato paste roasted in the fat 4 min with the
   silicone spatula; deglazed with red wine, scraped; stock and water.
7. **Braise.** Rafts back, lid on, the braiser is **slid** from H2 along the flush deck into the oven,
   160 °C, 90 min.
8. **Finish.** Braiser slid back to H2; rafts lifted by their handles, lowered into the cradle comb and
   drawn out: the rolls stay, seam down. Sauce strained through the spin basket (1 mm), thickened with a
   flour slurry whisked in the spindle bowl, seasoned.

Grips: 40 for the whole Rouladen component; confidence H for holding (raft), M for rolling.

### 3.4 Breaded Wiener Schnitzel in 3–4 mm of fat

Cutlets bought thin (butcher cut) or flattened between the folded silicone mat by the press's presser
plate (1 kN, ENVELOPE of K4). Breading by tumbling, not by tongs: two cutlets with flour in a GN 2/3-65
under the GN lid, the pair hooked and rolled ±60° three times; egg dip from a GN 1/3 with the spatula-tongs
(pinch at the edge, roll 180° in the dip, 5 s drain); crumbs in the second GN 2/3-65 under the GN 2/3-20
as lid, tumbled twice, light pressure by the presser. The cutlets go straight onto the lower lift rack.

Frying: Ø 240 pan on H2 with **180 mL of oil (4 mm)** at 170 °C (COK-021: ≤ 250 mL). The rack with two
cutlets is lowered in; a ladle of fat is poured over the top twice (the swirl a cook does); after 3 min
the upper rack is set on and hooked, the rack pair is lifted, drained 5 s over the pan, rolled 180° and
lowered (GA-36); 3 min; lifted, drained, laid on the GN 2/3-20 in the oven at 80 °C with the vent open. Two
batches for four cutlets, fried last; the first batch waits ≤ 7 min. Confidence M–H; untested: rack marks
in the crumb.

### 3.5 Frikadellen (8 × 110 g)

Bread soaked in milk, mince, egg (cracked in the bottom-strike cracker over the saucer, checked by the
camera), 6 mm onion dice, mustard, salt, pepper and chopped parsley in the 4 L pot on T1 with the kneading
roller, 2 min. The mass is scooped into the press tube with the silicone spatula; the **Ø 55 former plate**
and the cut-off slide make 46 mm plugs (110 g ±5 %) onto a wetted GN 2/3-20; the gantry jiggles the tray
(X oscillation, 3 Hz, 20 s) to round them; the spatula-tongs set them on the thermoplate on H2/H4 with
25 mL of fat, the presser flattens each to 22 mm (smash-forming, the most traditional shape per C1). Turned
once by the hooked thermoplate pair (≤ 30 mL free fat). Core probe 72 °C. 18 G.

### 3.6 Mash

1 kg potatoes washed in the 6.5 L pot's basket (dunk wash, two baths), halved by knife-Y, boiled 18 min
in the basket on T1. Basket lifted and drained 20 s. The 4 L pot with 250 mL hot milk and 50 g butter
stands on the bench; the tube on its legs over it; potatoes tipped in twice, pressed through the 3 mm
plate at 1–2 kN **with their skins**, which stay in the tube. The pot goes to T3 with the scraper arm,
30 rpm for 60 s, nutmeg and salt by spoon. Riced texture, not gluey (C1). Confidence H.

### 3.7 Kneading and shaping dough

The chuck pours flour from the box held in the jaws into the 6.5 L pot standing on the bench, weighed by
the load pins as loss in weight (±5 g); water from the spout through the flow meter; yeast, salt and oil
by spoon and ladle. The pot is slid onto T1, the roller and scraper arms hooked onto their pins, 8 min at
80 rpm (Ankarsrum principle, 1.6 kg with 20 Nm). Proofing in the same pot, lidded, T1 at 30 °C.
Shaping: **pizza** — dough halved by knife (halves checked by the load pins), each half rolled in its oiled
tray between 5 mm gauge bars, 5 min rest, rolled again (H). **Rolls** — 60 g plugs from the Ø 55 former,
rounded by jiggling on a floured tray (M). **Loaf** — into the loose-floor tin. Sticky dough is rolled
under the folded silicone mat (ENVELOPE).

### 3.8 Pancake flip

Batter whisked in the spindle bowl (whisk rotor, 60 s). Pan A on T1 at 190 °C with 5 g of fat; the ladle
pours 100 mL at the centre while T1 spins at 120 rpm for 3 s: the batter spreads evenly to Ø 220
(spin-spread, K2/K5). After 80 s a release check (5 mm jerk at the tang, camera). Pan B, preheated on H2
with 3 g of fat, is laid on upside down, slid 8 mm to engage the far-side hook (K1); the pair is lifted
40 mm, rolled 180° in 0.8 s over the hob and set on H2; pan A is unhooked and goes back to T1 for the next
pancake. After 50 s the finished pancake is slid off pan B onto the warm GN 2/3-20 in the oven. 2.2 min and
3 G per pancake. Confidence M (the shared pan-pair flip result, G-assembly 7.1 rules applied).

### 3.9 Draining pasta

Pasta boils in the basket in the 6.5 L pot on T1 (3 L water, 3.5 kW). A ladle of pasta water is taken
first. The basket is lifted by its tang, held 20 s over the pot, and tipped about its lip into the sauce
pot or a GN 2/3-65. The water stays in the pot and is poured into the hopper later (pot 4.5 kg at 160 mm:
7 Nm on the pot's stand-off tang, inside the 9.4 Nm limit). No hot water is carried over food. H.

### 3.10 Carving a boneless roast

Roast on the white HDPE board on the bench, the comb fence (slots at 10 mm pitch) set over its end;
knife-X (250 mm, scalloped) draw-cuts in each slot with 2 mm descent per stroke; slices are lifted by the
spatula-tongs straight onto the plates. Firm roast H; hot braised meat M (rest 15 min first). Bone-in
poultry: cooked and served as parts (R-06, class b).

### 3.11 Plating 2–4 portions nicely

Plates (Ø ≤ 270) come from the dish cabinet: the spatula-tongs pinch the rim and lay two plates into the
heated hatch drawer. For each plate a layout from the recipe (meat at 7 o'clock, starch at 12, vegetables
at 3, sauce beside the meat, garnish on top). **Batch by tool**: each tool is fetched once and serves both
plates — spatula-tongs for pieces and vegetables, the Ø 80 ring as a mould (set down, mash or rice ladled
in and pressed by the presser, ring lifted: a clean cylinder), the ladle pouring 50 mL of sauce about its
lip, the spoon sprinkling herbs with a small X/Y dither. The camera compares the plate with the layout and
the silicone spatula's edge wipes a splash off the rim. Two plates take about 75 s and 5 G; the gantry
withdraws, the drawer unlocks, the diner takes the plates; for 3–4 persons the second pair follows about
90 s later (SRV-009: within 3 min). Components wait hot in their vessels on the hob or in the oven, fried
items are plated last. Confidence M (layout repeatability ±10 mm).

---

## 4. Benchmark check

Moves = handling events G + R as in K6 §5 (grips before hand-over plus return grips afterwards), now
including box doses by the chuck (C5 A1) and plating, which K6 did not have. "Before" is K6's own figure.
Persons as in the exploration brief for 4p (B6 now at 4 persons, DEC-19); 2p = the regular household.

| # | Benchmark | Result (K6 → K6b) | Time 4p / limit (min) | Moves 4p, before → after | Time 2p | Moves 2p | What changed |
|---|---|---|---|---|---|---|---|
| B1 | Rouladen, Rotkohl, Salzkartoffeln | adapted → **yes** | 138 / 183 | 143 → 102 | 128 | 82 | raft-secured rolls, onion and paste roasted in the fond, red cabbage halved by the lever knife, plated |
| B2 | Schnitzel, Bratkartoffeln, Gurkensalat | yes | 55 / 67 | 134 → 94 | 49 | 76 | potatoes boiled in the skin at t = 0, cooled in cold water, peeled at 1 mm, sliced in the tube; Schnitzel in 4 mm of fat, lift-rack turn, two batches; cucumber striped on the spit |
| B3 | Frikadellen, Püree, Erbsen-Möhren | yes | 42 / 50 | 132 → 85 | 38 | 69 | mash from halves riced in the skin (no peeling); patties by former and smash; thermoplate pair flip; one retry adds 1 min |
| B4 | Spaghetti Bolognese | yes | 76 / 96 | 89 → 70 | 72 | 60 | mince seared first in the bridged braiser; celeriac from a whole bulb (P1 facets); garlic in the skin; cheese bought grated |
| B5 | Pizza, 2 trays | yes | 96 / 113 | 80 → 60 | 96 | 58 | dough poured and weighed by the load pins; mozzarella diced in the tube |
| B6 | Gemüseeintopf (now 4 persons) | adapted → **yes** | 48 / 60 | 84 → 67 | 42 | 58 | beans trimmed by one camera-guided cut each (GP-102); leek cut, then dunk-washed (GP-W4); fresh parsley washed, spun, chopped by the blade rotor |
| B7 | Steak, oven fries, mixed salad | yes (basting adapted) | 45 / 79 | 116 (2p) → 98 | 40 | 86 | pepper cored (GP-61); lettuce butt cut, dunk wash, spin basket; steak turned by the pan pair, core probe; butter ladled over instead of pan-tilt basting |
| B8 | Pfannkuchen, 8 | yes | 44 / 50 | 84 → 55 | 30 (4) | 40 | spin-spread on T1, hooked pan pair, 3 G per pancake |
| B9 | Chicken curry, rice | yes | 36 / 56 | 80 → 63 | 32 | 54 | fresh pepper cored; ginger pared on the spit; lime juiced through the ricer; rice rinsed in the 1 mm spin basket |
| B10 | Lasagne, béchamel from scratch | yes | 129 / 148 | 130 → 92 | 120 | 83 | béchamel on T3 under the whisk bar while the ragù turns on T1 under the scraper (no paddle visits); portions cut and plated |
| B11 | Rührkuchen, unmoulded | adapted → **yes** | 98 / 125 | 74 → 58 | 98 | 58 | loose-floor loaf tin with flour and fat; induction release pulse on H2; push-off stand: dome up |
| B12 | Scrambled eggs, toast (1 person) | yes | 9 / 17 | 47 → 35 | 11 | 40 | eggs beaten in the spindle bowl, scrambled on T3 under the scraper; toast turned by the griddle pair |

**Twelve yes** (K6: nine yes, three adapted). Mean moves at the brief's person counts **100 → 72**; for
the regular 2-person household **64**; full 4-person menus (B1, B2, B10) **92–102**, against C5's limit
of 70 (see 6.2). Elapsed times change by −2 to +13 min; the largest rise (B2) is the correct
cooked-and-cooled Bratkartoffeln sequence, still inside the limit.

---

## 5. Cleaning

### 5.1 Food-contact surfaces: everything is ware, washed in one well

**Well.** Under the bench, 1.4404, coved, double wall with 20 mm insulation, floor sloped to a Ø 40 outlet
over the household-dishwasher sump filter. A comb of seven slots (45 mm pitch) at the top; every item
hangs tang-up in a validated pattern (tray on edge: 2 slots, pot on its side: 3 slots, tool rack: 1,
plate carrier: 1, press plates in a file slot); the chuck releases above the rim and never enters. Spray:
16 flat-fan nozzles in the two end walls between the slots, one rotary head in the floor, two nozzles on
the tangs; household circulation pump 30 L/min. Tank 8 L at 60 °C below the well; hot rinse water from
the 30 L store at 88 °C.

| Programme | When | Steps | Time | Water | Heat |
|---|---|---|---|---|---|
| Cold rinse | within 2 min of emptying any vessel (R-7); the item then waits in the closed well | 10 s cold fan | — | 0.3 L | — |
| Standard load | after hand-over, ware and dishes | pre-rinse cold 20 s to drain; wash 60 °C alkaline 180 s recirculated; drain to tank 15 s; **rinse 3 L at 88 °C recirculated 60 s, surface ≥ 82 °C for ≥ 40 s: A0 ≥ 90**; rinse water runs into the tank and regenerates it; dry 90 s (lid lifted 30 mm, well fan to the downdraft duct), polymers 4 min | 6.5 min | 3.5 L | 0.27 kWh from the store |
| Turnaround | during the meal, a class R item needed again for RTE work | as standard, one to three items | 6.5 min | 3.5 L | 0.27 kWh |
| Intensive | burnt-on soil (WSH-006), failed verification, weekly | own 6 L fill, enzymatic, 50 °C, 15 min soak-spray, then standard rinse | 20 min | 9 L | 0.5 kWh |

The tank liquor is dumped every day and whenever it falls below 60 °C (R-7). The store is recharged at
2 kW only while the oven is off; during cooking the well draws only its pump (120 W) and stays at 44–48 dB(A)
behind its insulated lid [E, risk 4].

**Throughput.** Full 4-person menu: about four ware loads and two dish loads, 6 × 6.5 = 39 min after
hand-over (PERF-005: 45 min S met). 2-person meal: three ware loads and one dish load, 26 min. Ware needed
twice in one meal is covered by the clean stock (CAP-030); the turnaround is used about once per meal
with raw meat.

**Verification (R-11).** On lift-out the chuck turns every item once in front of the rear-wall camera
(white, oblique and UV-A light) and an IR sensor (≥ 65 °C stands for dry steel); the image is compared
with the item's reference. A failed item goes to the intensive programme, then to a quarantine slot in the
store, and the human is told. Logger validation of A0 on the coldest item of each load pattern before
release; weekly riboflavin self-test of one load and of the bay.

**Clean side.** Clean items go from the well straight to the closed tower store or the dish cabinet; no
clean item waits in the well (C2 K6-5). The lid has a drip lip that leads condensate back into the well.

### 5.2 The chuck and the tangs

Every tang has a drip collar (pots, tools) or a 5 mm dam and a spine bar (trays); the jaws touch only the
tang. The jet gate (two fan nozzles over the hopper, 88 °C from the store) rinses the jaws and sockets
(through-drilled) **after every grip of a soiled item**, on the way out of the well, 3 s and 0.1 L; after
any class R item 10 s (A0 ≈ 60 on the 0.2 kg jaws). The controller tracks the chuck as "clean" or
"soiled" and refuses a clean item with a soiled chuck.

### 5.3 Splash zone (Zone S)

| Surface | m² | Soiled by | Cleaned | Dries by |
|---|---|---|---|---|
| Deck: hob glass, bench lid, hatch drawer, oven sill | 1.0 | drips, flour, splashes, boil-over | **after every cooked meal**: fixed nozzles, detergent, rinse; hob glass also by a scraper-blade tool after burnt sugar or milk (weekly or on camera alarm) | 3° slope to the hopper; fan |
| Hopper, spindle pocket | 0.1 | waste, water, peel | flushed after each use; daily | drains |
| Rear wall and door inside, lower part (Z 880–1300) | 1.5 | aerosol, splashes near the hob | **after every cooked meal** | fan |
| Rear wall and door inside, upper part | 2.5 | steam, little aerosol (downdraft) | daily | fan |
| End walls, tower face (oven door, store shutter), ceiling | 2.2 | steam | daily, shutter closed | fan |
| Mast, arm, wrist, chuck, press column, anchor pins, spouts | 0.7 | steam, splashes; chuck: tangs | chuck: jet gate per grip; lower mast and arm: per meal; all: daily with a fixed pose sequence | closed boxes, slopes |
| Inside the well, lid | 0.5 | everything | every cycle | fan |
| **Total** | **8.5** (K6: 10.7) | | 2.8 m² per meal, all daily | |

**Nozzle plan.** Per meal: 14 flat-fan nozzles (8 along the rear wall at Z 1300 aiming down and across the
deck, 6 on the inside of the door), 0.05 L/s each: 8 s of detergent solution (2 g/L, 60 °C, 5.6 L),
2 min dwell, 8 s of fresh rinse at 65 °C (5.6 L): **11 L**, 0.6 L/m²·pass over 2.8 m²·2 passes; the
gantry parks at the left end and is sprayed by two nozzles of its own. Daily: in addition 2 rotary heads in
the ceiling corners and the upper rows, 12 L detergent and 10 L rinse while the gantry runs its pose
sequence: **22 L**. After every meal the downdraft fan dries the bay to RH < 65 % within 60 min
(HYG-045, HYG-053). The riboflavin proof on a mock-up is risk 6.

**Fat aerosol at the source.** The downdraft slot between the hob columns draws 300–400 m³/h at pan level
(bought hob-extractor class, washable baffle filter as ware, washed daily in the well). It is why the
upper bay can be washed daily and the lower part per meal.

### 5.4 Raw and ready-to-eat within one meal

* Order: dry, ready-to-eat, raw vegetable, raw animal food last (SM-208); the scheduler keeps it except
  where the recipe forbids (B1 starts with meat; then the RTE work comes after a turnaround).
* Unwashed produce is class R (R-5): it is washed in the 6.5 L pot's basket (dunk wash, GP-W1) before any
  tool touches it; the basket counts as red for that use.
* Red duplicates only for spatula-tongs and one GN 1/3; raw meat lies on the red GN 1/3 or in its own
  vessel, never on the board. Everything else that touched class R goes to a turnaround load (A0 ≥ 60)
  before an RTE use.
* The chuck rule of 5.2; a witness coupon rides in the first red load (SM-207).
* Dishes return through the hatch drawer after the meal; the drawer is rinsed by the per-meal nozzles and
  dried before it next carries plated food (R-6 in time).

### 5.5 Peelings, scraps, fat

Peel falls from the post into the hopper; trimmings and the skin mats from the ricer are tipped into it;
the 2 mm strainer basket is emptied by the chuck into the closed bio bin chute and goes to the well. Water
goes to the drain. Fat above 30 mL is poured into the fat cup, cooled on the store's lowest level and
tipped into the bio bin onto the peelings; it never reaches the drain (WSH-016).

### 5.6 Crevices, seals and spray shadows, named

1. Sealing bands of Z (rear face of the mast) and Y (top of the arm, in its gutter): band edges collect
   aerosol; washed per meal (lower part) and daily; exchanged yearly (R-12).
2. Roll lip seal and chuck rod seal above the work: under umbrella collars; inspected weekly by the camera.
3. Press column seal: scraper, drained lantern, dry seal; the column is at the front edge, outside the
   projection of the tube.
4. Spine tangs: continuous seal weld, ground; a weld pore is the expected defect (inspected at purchase).
5. Bought GN trays: **flat-flange** trays only, or the roll welded shut.
6. Dicing grids, ricer and Spätzle plates, perforated basket, spin basket, lift racks: blade roots and hole
   edges; jets against the cutting direction; camera against back light.
7. Cut-off slide in open U-rails on the tube flange; egg cracker on one loose pin; lid hinge on two open
   pins: all fall apart or open fully for washing.
8. Spindle rotors: magnet rings fully welded in 1.4404 cans; the PEEK bush lifts off.
9. Silicone apron, mat, spatula lip: one-piece moulded; dried by fan 4 min (R-9).
10. Well: comb rods touch each tang at two points; mis-loading is prevented by the load pattern and checked
    by the camera; the lid's drip lip.
11. Bay: the X labyrinth (purged outward, gutter below), the door gasket, the glass-to-deck silicone joint
    (HYG-018 ruling needed), the hatch-flap gasket, the oven door slot in the plinth.

### 5.7 Water and energy (2-person reference meal, incl. dishes)

| Item | Water | Energy |
|---|---|---|
| Well: 3 ware loads + 1 dish load × 3.5 L, 0.27 kWh | 14 L | 1.1 kWh |
| Tank: daily fill share, kept ≥ 60 °C | 5 L | 0.3 kWh |
| Per-meal hob-zone wash | 11 L | 0.3 kWh |
| Daily bay wash, share | 11 L | 0.3 kWh |
| Produce washing, cooking water, jet gate | 9 L | — |
| Cooking (hob, oven) | — | 1.3 kWh |
| Store standby loss, fans, pumps, drives | — | 0.2 kWh |
| **Total** | **≈ 50 L** | **≈ 3.5 kWh** |

Against RES-005 (≤ 35 L, reported only, #23) and RES-001 (≤ 3.0 kWh): over by about 40 % and 15 %. K6 as
recomputed was ≈ 46 L and ≈ 3.6 kWh per 2-person meal **without** its dishes and with a splash zone washed
only daily; K6b includes the dishes and a per-meal wash. Levers: final rinse kept as the next pre-rinse
(−3 L), per-meal wash only after frying or boil-over (−8 L on two meals in three), drain heat recovery.

---

## 6. Numbers before → after

### 6.1 Summary

| Quantity | K6 | K6b | Note |
|---|---|---|---|
| Wall width of the cell | 2595 mm | **1855 mm** | both include the oven; K6b also the hatch, plating and the dish washing |
| Whole machine (C4 3.1: + 2250 floor / + 2700 realistic; K6b minus the 600 mm dish module it replaces) | 4845 / 5295 mm | **3505 / 3955 mm** | PHY-004 ≤ 3600: met at C4's storage floor, missed by 0.36 m at its realistic storage |
| Motion actuators, stated | 16 | **10** | X, Z, Y, roll, chuck, T1, T3, press, spindle, oven door |
| C5-normalised (no dock, egg, oven door) | 12 | **9** | C5 limit ≤ 10: met |
| Dynamic seals and bands in the splash zone | 7 | **5** | Z band, Y band, roll, chuck rod, press column; C5 limit ≤ 5: met |
| Independent novel mechanisms (C5 S4) | 4 | **2** by C5's own S-min convention, **3** strictly | 6.2 |
| Distinct mechanism types (S3) | 12 | 9 | gantry, press, turning ring, spindle, well, jet gate and hopper, peeler post, hatch drawer, oven door |
| Custom part types | ≈ 85 | ≈ 60 | |
| Loose food-contact items | 93 | **78** | plus 3 service items, 3 tool racks, 5 dish carriers |
| Handling events per meal (G + R) | mean 100; full menus 130–145 | **mean 72; 2 persons 64; full menus 92–102** | includes box doses and plating, which K6 did not count |
| Cleaning stations (S10) | 3, plus a separate dish washer | **2** (well, jet gate), dishes included | |
| Zone S | 10.7 m², washed daily | 8.5 m², 2.8 m² of it per meal, dried per meal | |
| Coverage, C1 standard N, central | 218 as documented; 230 = 92.7 % with modules | **232 = 93.5 %** (range 230–233) | 6.3 |
| Benchmarks | 9 yes, 3 adapted | 12 yes | section 4 |
| Water, energy per 2-person meal incl. dishes | ≈ 49 L, ≈ 4.0 kWh (C2/C4 recomputed) | ≈ 50 L, ≈ 3.5 kWh | per-meal bay wash added, wash heat moved out of cooking |
| Wash heating during cooking | up to 5 kW | **0 W** | thermal store |
| Washer noise | 52–56 dB(A) | 44–48 dB(A) [E] | |
| All clean after hand-over | 15–20 min (two wells) | 26 min (2p), 39 min (4p) | worse: one quiet well; PERF-005 S (45 min) still met |
| Parts cost, single unit | 21.9 k€ (C3: 28–31 k€) | **≈ 13.5 k€ ± 30 %**, machine part ≈ 11 k€ | 6.4 |

### 6.2 The C5 hard limits

* **Actuators ≤ 10, seals ≤ 5:** met (9 normalised, 5 seals).
* **Novel mechanisms ≤ 2:** by the convention C5 used for its own S-min (canned couplings and the shared
  modules not counted) K6b has two: the tang-and-hook ware family gripped in soil, and the spit-and-post
  peeling. Strictly there is a third, the turning carrier ring 2 mm above the induction glass; its rig is
  two days and 300 €, its fallback is a plain position with a hung paddle visited by the gantry. Exception
  argued: removing the ring would cost continuous stirring and kneading, which carry about 130 meals (C1
  rank 2).
* **Events ≤ 70:** met for the regular 2-person household (mean 64) and for eight of twelve benchmarks at
  their brief size; not met for full 4-person menus (92–102). Argument: REL-001 gives handling half of 2 %;
  at 100 events that is 1 × 10⁻⁴ unrecovered failures per event, which C3 X4 rates reachable for
  form-fit grips on fixtured parts with a weight check (10⁻⁵–10⁻⁴ after one retry). K6b's tang with pins,
  load pins in the jaws and a camera after every release is that case; guests' menus (4 persons) are
  occasional (#18). The 10 000-cycle rig (risk 1) decides it.

### 6.3 Coverage (C1 standard N)

Starting point C1's 230 meals for K6 with the hostable modules. K6b adds the two meals that C1 lists as
lost for every concept for want of a banana and an avocado method: **CK16 banana bread** (banana riced in
the skin) and **MX06 guacamole** (halve, twist, rice in the skin): **232 = 93.5 %**. Low end 230 if these
two fail their bench test; high end 233 if Kohlrouladen (DM12, whole leaves from a blanched head peeled by
the spatula-tongs) works. Still out: the 8 exclusions of 5.4; IT17, DM33, CK12, CK17 (no ready dough under
#8/#26 and no pastry line); AS08, AS09, IN07 (folded wrappers). Designer class (c) about 9 (basting by
ladle, citrus as rounds, Spätzle as pressed strands, round cakes in the pan with a loose floor among them),
inside MEAL-019's 24.

### 6.4 Cost, honestly (#22 report, #28 target)

| Block | k€ | Of which household appliance or bought module |
|---|---|---|
| Hob: four OEM induction modules, glass, two ring drives | 0.7 | yes (DEC-5) |
| Oven: household compact oven, door replaced by a drop door | 0.7 | yes, modified (#24) |
| Downdraft extractor with baffle filter | 0.5 | yes |
| Hot-water store 30 L (under-sink heater) | 0.2 | yes |
| Wash parts of a household dishwasher (pump, heater, filter, softener, dosing) | 0.3 | yes, replaces the €500 dishwasher of #28 |
| **Appliances subtotal** | **2.4** | |
| Gantry X, Z, Y with mast and arm boxes, bands, labyrinth | 2.0 | |
| Wrist roll, chuck, two load pins | 0.5 | |
| Press, deck spindle | 0.75 | |
| Controls, drives, 3 cameras, lights, IR sensor, safety chain | 0.9 | |
| Stainless bay, deck, well, tower store, hatch drawer, nozzles and valves (job shop, #21) | 3.0 | |
| Ware: 78 items (bought GN, thermoplates and pots 0.9; tangs, spines, hooks welded 0.9; custom tools, cassettes, racks and carriers 2.5) | 4.3 | |
| **Machine part subtotal** | **11.4** | #28 target ≈ 2 k€: missed by about 5 × |
| **Total** | **≈ 13.8** | K6: 21.9 (C3 28–31) without dish washing and hatch |

The machine part is dominated by stainless work and ware, not by motion. Design-to-cost levers for the
convergence rounds after K9b: ware with bought standard GN handles and a handle gripper instead of welded
tangs (−1.5 k€, but loses the drip-collar rule), a bay of bent sheet with a bought dishwasher tub as the
well (−1 k€), series prices (−30–40 %). Even so a loose-ware concept with about 80 items will not reach
€2 k; that is the price of having no fixed food surface.

---

## 7. Self-assessment

Scores 1–10. "Before" is the critic's score of K6; "after" is my estimate for K6b on the same scale, to be
checked by the next critique. Weights from `04-decision-matrix.md`.

| Criterion (weight) | Before | After | Why |
|---|---|---|---|
| Simplicity (30 %) | 4.5 (C5) | 6.3 | 9 actuators, 5 seals, 2–3 novel, 78 items, two cleaning stations including dishes; still about 60 custom types and about 40 software skills |
| Hygiene (25 %) | 7 (C2) | 8 | rinse hold with A0 ≥ 90, chuck rinse per soiled grip, per-meal hob-zone wash and dry-out, downdraft, no sink, fat path; the bay is still an open splash zone with two bands |
| Coverage and food (20 %) | 7 (C1) | 7.5 | 232 meals, correct gravy, Schnitzel in 4 mm of fat, riced mash, dome-up cake, generic peeling; banana and avocado methods are new and untested |
| Reliability (15 %) | 6 (C3) | 7 | no collision, spine tangs, hooked pairs, load pins on every grip, slides instead of lifts, fewer events; one gripper and one well remain single points |
| System fit (10 %) | 3.5 (C4) | 6 | 1.86 m with oven, washer, hatch and plating; no wash heating during cooking; quiet; one washer for the machine. Still 0.36 m over at realistic storage, still 5 × the cost target |
| **Weighted** | **5.75** | **7.0** | |

**Remaining weaknesses, in order of weight.**

1. **Handling count for guests' menus** (92–102 events) rests on a grip reliability nobody has measured.
2. **Cost**: the machine part is about 11 k€ against #28's €2 k; ware and stainless work dominate.
3. **One gripper, one well**: either failing stops cooking after the running meal; the well is also slower
   than K6's two (39 min to all clean for four persons).
4. **Width**: fits 3.6 m only with C4's minimum storage.
5. **The open bay**: 8.5 m² of splash zone and two sealing bands above the work area; per-meal washing
   costs 11 L.
6. **New food methods** that only a bench can confirm: banana and avocado through the ricer, spin-spread
   Pfannkuchen, smash-formed Frikadellen from plugs, raft-secured Rouladen.
7. **No yaw**: two knives, no free-form plating flourishes, approach only along X.

---

## 8. Best ideas for the combined machine (K9b)

1. **Bench over the washer, and one washer for ware and dishes.** One insulated top-loading well under the
   work bench, its lid the bench; ware hangs by its tang, dishes on tanged carriers; washing after
   hand-over from hot water stored while the oven was off. Saves a 400 mm slot and the separate dish
   washer, removes wash heating from the cooking power budget.
2. **Tang family with spine, hook and load pins.** One flat tang with two holes on every item (spine bar on
   trays), a passive far-side hook that locks any pair (pans, trays, racks, tin and stand), two load pins in
   the jaws that weigh every grip: form-fit handling with free weighing, pairs that invert about their own
   joint plane on a single roll axis.
3. **Three passive peelers for the whole PRP-039 list**: spit with a three-edge post (Y-blade, depth-shoe
   paring blade, rasp) on the wrist roll; **rice in the skin** through the press's 3 mm plate (potato,
   banana, avocado, squash, tomato, citrus juice); tube cutters (corers, wedger, banana ring). No
   single-purpose device.
4. **Slide, don't lift.** Deck, bench, hob glass and oven floor flush; heavy vessels are pushed by their
   tang into the oven and between positions, so the gripper's moment limit stops deciding the vessel size.
5. **Keep the dirt low**: downdraft slot between the hob columns, the 2.8 m² hob zone washed by fixed nozzles
   after every cooked meal, fan dry-out after every meal, chuck rinsed over the waste hopper after every
   soiled grip.

---

## 9. Risks, cheapest kill experiments, open questions

### 9.1 Risks

| # | Risk | Cheapest experiment | Kill criterion |
|---|---|---|---|
| 1 | Tang grip with pins and load pins misses or drops in wet, floury, greasy soil; spine tang yields | Hobby 3-axis gantry with the chuck, five tanged items (one spine-tang GN 2/3 with 3 kg), four rest types; 10 000 automatic cycles with soiled tangs; static load test of the spine tang to 15 Nm. 2 weeks, 2 k€ | raw success < 99.5 % after tuning, or rim yield below 10 Nm |
| 2 | Hooked pan pair leaks or fails to engage; lift-rack turn breaks the crumb | Two Ø 240 pans with welded tang, hook tab and catch, turned by hand: 20 pancakes, 10 Rösti, 8 Schnitzel with the rack pair in 180 mL; weigh leaked fat, photograph crumbs. 1 day, 150 € | > 2 mL fat per flip, or > 1 in 10 crusts damaged |
| 3 | Rice in the skin does not hold back banana, avocado or citrus skin | Workshop press or lever ricer with a 3 mm plate: 1 kg each of boiled potato halves, ripe banana sections, avocado halves, lemon halves, cooked squash, tomato; weigh flesh yield, look for skin in the output. Half a day, 50 € | skin fragments in the purée, or yield < 65 % |
| 4 | Quiet well does not clean or disinfect: 3 min wash at 30 L/min on hanging ware, 60 s rinse at 88 °C; noise above 48 dB(A) | Household dishwasher pump and heater on a welded test well with the comb, dried egg, starch and mince soils at 2 h, riboflavin, a surface logger on the coldest tray; sound level through a 20 mm insulated lid. 1 week, 800 € | visible soil after 2 h drying, A0 < 60, or > 50 dB(A) |
| 5 | Spit-and-post peeling: stabbing, whip of long goods, asparagus, kiwi, mango | Cordless drill with the straight spit fork, a home-made three-edge post on a spring; 5 kg of mixed produce from the PRP-039 list; time, loss, retries. 1 day, 50 € | loss > 30 % or > 10 % retries on potatoes and apples |
| 6 | Per-meal hob-zone wash leaves shadows; downdraft does not keep the upper bay clean | Plywood-and-sheet mock-up of the bay with the real nozzle plan and a parked dummy mast; fluorescent oil mist from a frying pan on a bought downdraft hob; riboflavin and UV. 3 days, 1.5 k€ | coverage < 95 % of the hob zone, or visible fat on the upper rear wall after 10 fryings |
| 7 | Turning carrier ring: induction coupling through 2 mm, ring heating, boil-over on the rollers | Laser-cut ring on three rollers over a bought induction plate; power, ring temperature, boil-over test. 2 days, 300 € | > 15 % power loss or ring > 120 °C |
| 8 | Canned spindle: 1.5 Nm through a welded thimble at 6000 rpm, eddy heating | Bought magnetic coupling in a 0.8 mm 1.4404 cup on a 750 W motor; blend 1 L of soup, whip 400 mL cream; measure cup temperature. 2 days, 300 € | < 1 Nm transmitted or cup > 70 °C |
| 9 | Rouladen raft, mustard ribbon and flour seam | G-assembly 4.2 experiment A/B/C with the 40 × 2 slot ribbon. 1 day, 40 € | any open roll in group C |
| 10 | Bench over the well: the lid deflects under 3 kN, aerosol from an open well reaches RTE food | Sandwich lid on the test well under a press; settle plates on the bench while the lid is lifted after a red load. With risk 4 | lid deflection > 1 mm or positive settle plates |

### 9.2 Open questions

1. **Ruling on one washer for ware and dishes** (C4 9.2c): is a plate acceptable after a disinfecting
   cycle in the well that also washed raw-meat ware? K6b assumes yes, as in catering.
2. **Box lug**: the storage box standard must carry a tang lug (two Ø 8 holes) on one short end; the lid
   station outside the cell removes the lid.
3. **Hatch**: is a drawer that the diner pulls (two plates at a time) acceptable for DEC-6 and SRV-009, or
   must serving be motorised (+1 actuator)?
4. **Oven**: a household compact oven with its door replaced by a drop door into the plinth (#24) — the
   appliance's certification and interlock (SAF-056) must be re-established by the machine.
5. **Glass-ceramic hob flush in the deck** (HYG-018) and the slide path across it.
6. **CAP-030** is met by stock, not by re-washing; whether one quiet well gives enough turnaround for
   two-course guest menus has not been simulated.
7. **Cost**: if #28's €2 k is a firm direction, K9b must decide whether "everything that touches food is
   loose ware" survives; K6b's ware alone costs twice the target.
8. **Width**: K6b fits 3.6 m only with C4's minimum storage (2250 mm); with realistic storage the machine
   is 3.96 m.
