# R4 - Food preparation mechanisms

Research input for design task D4 (Preparation: tools, vessels, holders, dosing and pouring).
Scope: how to perform every preparation step for at least 95 % of traditional meals with tools that
the machine can wash by itself. Numbers are in SI/mm. Sources are listed in section 17.

## 0. How to read this document

**Evidence tags.** Every number carries one of these tags, because the web-search quota ran out
part-way through this research and several items could not be verified.

| Tag | Meaning |
|-----|---------|
| [S] | Seen in a source fetched or returned by search during this research (URL in section 17) |
| [M] | From general engineering or product knowledge, not verified in this session. Treat as plausible, check before relying on it (prices +-30 %) |
| [E] | Engineering estimate or derivation made here; the derivation is shown so it can be redone |

**Key findings (short).**

1. Cutting energy is tiny. A whole carrot cross-cut costs about 4.5 J, a potato 2.4 J [S]. Slicing
   half a kilo of vegetables is a few hundred joules. Motor size is set by friction, inertia and
   dough or meat, not by cutting. The hard problems are workholding, blade geometry and cleanability.
2. Force scales with the blade length engaged in the food, roughly 2-5 N per mm of edge for raw
   root vegetables [E from S]. A push-through dicer on a 50 x 50 mm potato block therefore needs
   0.8-2 kN; limiting the block cross-section to about 30 x 30 mm cuts that to 0.25-0.6 kN.
3. The best-proven, cleanable cutting mechanisms are the ones commercial kitchens already use in
   dishwashers: food-processor discs and dicing grids (Robot Coupe class), bottom-blade bowls
   (Thermomix class) and push-through grids (Vollrath Redco class).
4. Several "hard" operations disappear with ingredient choice: skin-on potatoes and carrots,
   ricer or food mill that retains skins (mash, tomato sauce), pre-portioned meat (goulash cubes,
   Rouladen slices, cutlets, mince), liquid egg, frozen peeled garlic and onion, dried or
   chilled fresh pasta, frozen dumplings.
5. Dosing: tilt-pour with vibration and a load cell is the easiest to clean; it needs no
   mechanism that touches food. Use two weighing ranges (a 200 g cell for spices, a 5-10 kg cell
   for bulk), because load-cell accuracy is about 0.1 % of full scale [S]. Keep steam away from
   powders: a 2 kW boil releases about 0.9 g/s of vapour [E].
6. Prefer a station-centric architecture: fixed motors at fixed stations, vessels travel on the
   transport. Only light tools (below 1 kg) need a tool changer on the manipulator.
7. Ankarsrum-style "rotating bowl, fixed tool" needs no shaft seal through the bowl floor, drives
   5 kg of dough on 600 W [S], and doubles as a stirrer for cooking. A Thermomix-style bottom
   blade (500 W, 40-10,700 rpm, 2.2 L [S]) covers chopping, puree, emulsifying and whipping.
8. Recommended minimal set: (1) bottom-blade prep bowl, (2) rotating-bowl kneader/stirrer,
   (3) feed-through cutter head with discs and a dicing grid, (4) press station with
   interchangeable plates (flatten, patty, coating press), (5) ricer/food mill, (6) egg cracker,
   (7) weigh-and-dose station, (8) a manipulator with a small changer for 4-6 light tools.

---

## 1. Cutting

### 1.1 Physics and force data

A knife cuts by concentrating stress at an edge until the material fractures. The work is
fracture energy per new surface plus friction on the blade flanks plus deformation of the bulk.
Sharp thin edges, slicing (draw) motion and high speed lower the force.

**Measured data.**

| Food | Value | Conditions | Tag / source |
|------|-------|-----------|--------------|
| Potato | peak force 43.7-61.5 N | universal tester, edge angle 15-25 deg, 20-40 mm/min | [S] R1 |
| Carrot | 47.9-67.6 N | same | [S] R1 |
| Radish | 36.8-58.4 N | same | [S] R1 |
| Onion | 46.4-70.9 N (layered, force rises slowly with speed and angle) | same | [S] R1 |
| Cucumber | 11.6-21.4 N | same | [S] R1 |
| Energy per cut (review) | potato 2.36 J, carrot 4.55 J, radish 1.23 J, cucumber 1.19 J, bell pepper 1.83 J, onion 2.36 J, aubergine 7.72 J; carrot up to 10.1 J with other rigs | 20-50 mm/min, edge 0-45 deg | [S] R2 |
| Cheddar, wire cut | peak load 846 g (8.3 N), work 185 mJ | texture analyser with wire | [S] R31 |
| Cooked beef, Warner-Bratzler shear of a 12.7 mm core | 3.2 kg (31 N) "tender" loin; 5.3 kg (52 N) top round | 1.016 mm blade, 60 deg V | [S] R10 |
| Raw beef, sharp slicing knife | 10-40 N for a steak of 60 x 25 mm | draw cut | [E] |
| Raw meat, semi-frozen (-2 to -4 C) | 3-5x the chilled value | | [E] |
| Bread, serrated blade | 10-30 N through crust, less through crumb | | [E] |
| Tomato | skin puncture 3-6 N; squashes under a dull blade | | [E] |
| Bone, frozen meat with bone | needs saw-type blade, 100s of N | not recommended | [E] |

**Derived design rules ([E], derived from R1 and R2).**

* Specific cutting energy, root vegetables: about 2-10 kJ/m2 (potato 2.36 J over an assumed
  25 mm diameter section = 4.8 kJ/m2; the review does not state the diameter).
* Force per unit engaged edge length: 2 N/mm (peak-force data) to 5 N/mm (energy data). Use
  2-5 N/mm, then multiply by 1.5-2 for friction and a slightly dull edge.
* Push-through dicer, block cross-section a x b, grid pitch p: engaged edge length is
  L = (a/p - 1) * b + (b/p - 1) * a. For 50 x 50 mm, p = 10 mm: L = 400 mm, force 0.8-2 kN.
  For 30 x 30 mm, p = 10 mm: L = 120 mm, force 0.24-0.6 kN. The Vollrath push dicer is hand
  driven through a lever, which fits these numbers.
* Whole meal: 500 g of vegetable sliced to 3 mm is about 100 slices x 2-5 J = 0.2-0.5 kJ. At
  one minute that is under 10 W of cutting power.
* Measured throughput of a commercial cutter: Robot Coupe CL50, 1.5 HP (1.1 kW), 425 rpm disc,
  1,100 lb/h (500 kg/h) [S] R3. That is about 8 kJ/kg including losses [E]. A home unit needs
  300-500 W for 10-30 kg/h.
* Speed and slicing angle: forces fall with faster edge speed and with a draw angle of
  15-45 deg. Ultrasonic excitation reduces cutting work with amplitude, mostly on fatty or sticky
  foods (cheese, cake) [S] R11.

### 1.2 Cutting principles compared

| Principle | How it works | Works on | Fails on | Force / power | Size | Cleanability | Fit |
|-----------|--------------|----------|----------|---------------|------|--------------|-----|
| **Feed-through disc** (Robot Coupe, Magimix, Kenwood, KitchenAid slicer/shredder discs) | Food pushed down a chute against a rotating disc with a fixed blade; slice thickness set by the disc; shredders and julienne discs have teeth | Firm veg, cheese, cabbage, potatoes for gratin/Rösti, carrots, cucumbers, mushrooms | Very soft tomato and ripe fruit, leafy herbs, raw meat, bread; long pieces jam | 300-1,100 W at 400-1,500 rpm [S R3, M] | Disc 190-215 mm, chute 50-100 mm | Discs are dishwasher-safe; chute and bowl are plain; crevices at the disc hub and the pusher | High |
| **Dicing grid + disc** (Robot Coupe dicing kit 5-25 mm) | The disc slices, the grid at the exit cuts sticks and cubes in the same stroke | Potato, carrot, onion (fair), peppers, cheese | Soft tomato; long products must be cut to length | as above, needs more torque | Kit adds about 50 mm height | Kit is "dishwasher resistant" [S R3] | High |
| **Push-through grid** (Vollrath Redco InstaCut, Nemco Easy Chopper, Nicer Dicer) | Linear ram pushes the block through fixed knives | Onion, potato, pepper, tomato (Vollrath), cucumber, soft cheese | Very long or curved products; hard carrots need large force | 0.25-2 kN [E] | 300 x 150 x 100 mm | Removable blade assembly; whole unit is rinsable; blade assembly USD 107 [S R24] | High as a fixed station |
| **Bottom-blade bowl** (Thermomix, Robot Coupe cutter-mixer R-series) | Blade rotates at 40-10,700 rpm at the bowl floor and throws food in a torus; chops randomly | Onion, garlic, herbs, nuts, minced meat, ice, puree, breadcrumbs, cheese grate | Uniform slices, uniform cubes, whole-muscle meat | 500 W [S R4] | Bowl 2.2 L | Bowl and blade unit dishwasher-safe; seal ring is the weak point | High (multi-use) |
| **Deli slicer** (rotary circular blade on a carriage) | Product on a carriage or gravity feed pushes past a 190-300 mm blade; thickness gauge | Cooked meat, cold cuts, cheese, sausage, bread with serrated blade, tomato, cucumber | Bone, very small pieces, soft fresh cheese | 150-370 W [M] | 400 x 350 x 350 mm | Blade removal is needed; classic hygiene trouble spot | Medium (carving) |
| **Guillotine or reciprocating knife** | Straight knife driven by a linear actuator or crank through a held product | Cabbage, melon, bread loaves, cooked roast, halving of onions | Round products slip without a holder | 200-500 N for a 200 mm cabbage [E] | 200-400 mm stroke | Simple flat blade, easy to spray-clean; the guide slot needs care | Medium (pre-cut) |
| **Wire or harp** | Tensioned wires push through the product | Cooked egg, mozzarella, soft cheese, mushroom, strawberry, banana, Cheddar [S R31] | Hard carrot, raw potato, meat | under 20 N [E] | Small | Wires are easy to spray; wire fatigue | Niche |
| **Ultrasonic blade** (20-40 kHz sonotrode) | Blade vibrates axially; adhesion and friction drop | Cakes, cheesecake, soft brie, bread, ice-cream bars [S R11] | Hard root vegetables gain little; generator is costly | 100-500 W generator [M] | Blade 100-300 mm | Titanium blade wipes clean; can be run in a water bath to shed residue [E] | Low (specialty) |
| **Water jet** (3,000 bar, 0.1 mm nozzle, up to 300 mm/s [S R12]) | Abrasive-free water jet cuts through food | All fresh and frozen foods, shapes | Needs an intensifier pump of several kW, noise, water on the food | 3,000 bar system, EUR 20k+ [M] | Large | No contact; nozzle sealed | Not viable |
| **Robot-held knife** | Arm moves a chef's knife (rock chop, slice) with force control | Anything, in principle | Needs accurate workholding, sharpening, safety; academic stage [S R32] | 10-40 N, arm payload 2-3 kg | Arm | Knife is easy to wash, but sharpness drifts | Not recommended |

### 1.3 Existing machines worth copying

* **Robot Coupe CL50**: continuous feed, belt drive, 1.5 HP, 425 rpm, accepts 39 discs [S R3].
  Dicing kit 10 x 10 x 10 mm, dishwasher resistant [S R3]. Price of the CL50 about USD
  2,500-3,500 [M]; dicing kit USD 250-400 [M].
* **Thermomix TM6**: 500 W reluctance motor, 40-10,700 rpm, alternating-direction kneading mode,
  2.2 L working capacity [S R4]. TM5 launched at EUR 1,139 [S R4b]; TM6 is around EUR
  1,300-1,500 [M]. Also includes a weighing scale and heating [S R4b]. Removable blade unit with
  seal ring is the wear and hygiene point [M].
* **Vollrath Redco InstaCut 3.5**: hand-lever push-through dicer, 1/4", 3/8" or 1/2" cubes,
  USD 285; replacement blade assembly USD 107 [S R24].
* **KitchenAid / Kenwood attachment ecosystems** (see section 12) give cheap slicer, shredder,
  grinder and pasta parts with dishwasher-safe parts for a fraction of the professional price.
* **YORI** research kitchen uses removable dicing chambers and blade assemblies in a
  linear-actuator-lidded food-processor module [S R13].

### 1.4 Workholding of irregular produce

| Method | Principle | Suits | Comment |
|--------|-----------|-------|---------|
| **Confinement** | Feed tube or chute of fixed cross-section; pusher with soft face | Carrot, cucumber, potato halves, sausage, cheese blocks | The dominant industrial solution; no sensing; pre-halving needed for large items |
| **Halve first** | Guillotine or wedger reduces to chute size | Large potatoes, cabbage, onions, melons | Wedgers (push-through "apple corer-wedger" grids) work on round items |
| **V-jaw clamp with compliant pads** | Two jaws close on the item; spring-loaded | Roasts, cabbage, onions | Needs force limit so as not to crush tomatoes |
| **Spike or fork** | 3-prong spike through the item, as on spiralisers and deli slicers | Onions, cabbage cores, roasts | Leaves holes; the spike must be cleaned |
| **Vacuum cup** | Piab-type suction | Flat, dry, smooth surfaces (meat slices) | Fails on wet or textured skin |
| **Freeze-firm** | -2 to -4 C raises stiffness so meat slices cleanly | Raw meat, fat, bacon | Adds a chilling step and a fridge zone [E] |
| **Shape-then-cut** | Press an irregular piece into a prismatic mould (tray), chill, slice | Meat, mince blocks, cooked roasts | Turns an irregular into a regular part [E] |

**Onion.** Layered structure, slippery skin. Most robust: top and tail with a guillotine, halve
pole-to-pole, feed the halves flat side down through a slicing disc (half rings) or into the bowl
blade (chopped). Cutting force is 46-71 N per cut [S R1], so no special holder is needed if the
half is clamped in a tube.

### 1.5 Recommendation (cutting)

1. **Bottom-blade bowl** as the universal chop / mince / puree tool.
2. **One feed-through cutter head** with a small disc rack: slice 2, 4 and 6 mm, shred coarse and
   fine, stick/julienne, dicing grid 10 mm and optionally 15-20 mm. Max chute cross-section
   about 40 x 40 mm (keeps dicer force below about 1 kN); robot pre-halves larger items.
3. **Carving slicer** (rotary) only if roast beef, ham and bread slicing must be done on
   the machine; otherwise buy pre-sliced.
4. No water jet, no robot-held knife, no ultrasonic blade in v1.

---

## 2. Peeling and trimming

### 2.1 Mechanisms

| Mechanism | Principle | Suits | Fails / cost | Cleanability |
|-----------|-----------|-------|-------------|--------------|
| **Abrasive drum (carborundum)** | Food tumbles against a silicon-carbide (or brush) lined drum or rollers while water sprays and carries peel away; industrial units peel 2,500-5,000 kg/h [S R8] | Potato, carrot, beet, celeriac, ginger | Loss about 5 % for potato-chip lines [S R8], higher for small, eyed or irregular tubers (up to 60 % reported in bad cases [S R8]); soft skins (tomato, onion) fail | Wash by spray and flush; SiC surface holds starch; needs drain screen |
| **Knife peeler on a lathe** (apple peeler-corer, Victorio style) | Item is spun on a spike; a spring-loaded blade follows the contour | Apples, pears, firm round fruit, kohlrabi | Irregular potatoes, soft produce | Spike and blade rinse well; gears must be outside splash |
| **Y or swivel peeler on a robot** | Force-controlled arm pulls a blade along the skin | Straight carrot, cucumber, asparagus | Complex sensing; slow (10-30 s per item) [E] | Simple blade |
| **Steam pressure** | Vessel with 150-200 C steam at up to 15 bar (8 bar delicate fruit) for a few seconds up to 60 s, then flash depressurisation blows the skin off [S R8] | Potato, tomato, carrot, beet | PED pressure vessel, steam raising, waste; industrial only | Closed vessel, CIP; not home-scale |
| **Blanch and shock** | 30-60 s in 95 C water, then cold water; skin slips off | Tomato, peach, almond, broad beans | Two water baths, skin remains in the drain | Uses the existing pot |
| **Cook then slip skin** | Boiled whole potatoes (Pellkartoffeln) skin slips or is retained by a ricer | Potato for mash, salad, Bratkartoffeln | Cooking before cutting | Uses existing pot |
| **Lye peeling** | Hot NaOH dissolves skin | Industrial peach, tomato | Hazardous chemical | Rejected |
| **Air-blast (garlic, onion)** | Drum with multi-point air jets makes cyclone that strips dry skins; up to 95 % peeling rate of dry garlic [S R9]; onion versions slit the skin with 4 blades then blow air [S R9] | Garlic cloves, onions | Compressor (6-8 bar), noise, dust | Dry process, closed drum, blow out |
| **Top-and-tail plus squeeze** | Cut both ends, push through a tube or between two silicone rollers, skin slides off | Onion, shallot | Roller gap needs adjusting [E] | Rollers rinse |
| **Garlic press with skin on** | Hinged press retains the skin | Garlic for cooking | Skin remnants left in the press | Hinged basket must be flushable |
| **Coring / destemming** | Tube corer through a wedger grid; punch-through | Apple, pepper (halve, strip seeds with a scraper), pineapple, strawberry (hollow knife) | Each fruit needs its own head | Simple metal parts |

### 2.2 Strategy: reduce or remove peeling

| Strategy | Effect |
|----------|--------|
| **Skin-on** for waxy potatoes, carrots, courgette, aubergine, Hokkaido pumpkin, apples, pears, cucumber, tomatoes in sauce | Removes most peeling; needs a scrubbing wash (brush in the wash basket) |
| **Ricer or food mill retains skins** (mash from steamed unpeeled potatoes, tomato sauce, apple sauce) | No peeling at all for these dishes; skins collect in the hopper |
| **Buy pre-peeled** | Vacuum-packed peeled potatoes (about 2-3 weeks chilled) [M], peeled garlic cloves, peeled frozen onion, baby carrots, frozen diced onion, canned pineapple |
| **Frozen** | Frozen peeled vegetables, peas, spinach, diced onion, garlic cubes remove peeling, trimming, destemming, stoning |
| **Small abrasive drum** as an optional tool | 1-2 kg batch, 60-120 s [E]; only needed for old potatoes and root vegetables in traditional recipes that require peeled |

### 2.3 Recommendation (peeling)

Use skin-on plus ricer/food mill as the default; add a small abrasive drum (silicon-carbide
coated PP drum, 2-3 L, spray nozzles, drain screen) for potatoes and roots if peeled is needed.
Buy peeled garlic, onions or frozen alternatives. Do not build steam or air-blast peelers
for a home machine.

---

## 3. Washing produce and spinning it dry

**Goal.** Remove soil, pesticide residue and some microbes. Water alone reduces background
microflora on lettuce by about 1 log; 100 ppm chlorine gives 0.7-1.5 log [S R25]. A
peracetic acid two-step wash achieved 1.45-1.47 log CFU/g [S R25]. Ozone batch washing reached
2.7-2.9 log reduction of E. coli and Salmonella in 2 minutes [S R25]. Contact time correlates
with reduction [S R25].

| Step | Mechanism | Numbers |
|------|-----------|---------|
| Soak and agitate | Perforated basket in the vessel, water filled from the mains pipe (2.2-5 bar), air-bubble or pulsating flow, or bottom-drive stirring | 1-2 min; 3-5 L water per kg [E] |
| Scrub | Silicone brush on the drum or the robot; needed for skin-on roots | 30 s [E] |
| Rinse | Fresh water spray | 10-20 s |
| Optional sanitising | Electrolytic ozone or a peracetic acid dose; regulation to be checked | Ozone 2-3 log in 2 min [S R25] |
| Spin dry | Bottom drive spins the perforated basket inside the bowl | see below |

**Centrifugal drying.** Acceleration a = w^2 r. At 600 rpm, r = 0.10 m: 395 m/s2 = 40 g. At
900 rpm, r = 0.125 m: 1,110 m/s2 = 113 g [S R26 for the 900 rpm case; formula]. Commercial
salad spinners run around 900 rpm for 1-3 minutes [S R26]. Leaves bruise at higher speed; two
short spins (15 s) dry better than one long spin [S R26, low-confidence source]. Spin-up torque
is small: basket plus 0.3 kg greens, inertia about 0.005-0.01 kg m2, 0 to 600 rpm in 5 s needs
about 0.1 Nm [E]. A 1-3 Nm coupling is ample. Unbalance limits speed, so use a compliant mount
and a bowl with a drain.

**Recommendation.** Use one perforated inner basket in the standard prep bowl. The same bottom
drive that spins the blade spins the basket (wash by agitation, then drain, then spin). No
separate washer is needed. Drain goes to the waste pipe through a screen.

---

## 4. Meat handling

### 4.1 Operations and mechanisms

| Operation | Mechanisms | Numbers | Comment |
|-----------|-----------|---------|---------|
| **Mincing / grinding** | (a) Auger grinder (#12 class); (b) bowl blade on cubed, semi-frozen meat; (c) buy mince | #12 grinder 750 W (1 HP), 170-200 rpm, 4 lb/min (about 30 kg/h) [S R23], Vollrath 1 HP 264 lb/h [S R23]. Energy about 25 kJ/kg [E]; torque about 27 Nm at 170 rpm assuming 70 % efficiency [E]. 500 g takes about 1 min | Grinder has knife, plate and auger with crevices; the blade bowl is already cleaned as part of the cycle, so (b) avoids one more device. Fat smears if meat is warm; use -2 C cubes [E] |
| **Pounding / tenderising** | Flat press plate, roller, blade tenderiser (Jaccard type) | Flatten 150 g cutlet from 15 to 6 mm: 0.5-1.5 kN with plates [E]; hand mallet about 5-10 J per blow [E] | Blade tenderisers push surface bacteria inside, so cook to core temperature |
| **Slicing raw meat** | Deli slicer with partially frozen meat; guillotine; buy pre-sliced | Raw beef 10-40 N; semi-frozen 3-5x [E] | Frozen meat above -4 C is cut by industrial slicers [S R32]; for a home machine buy sliced |
| **Forming patties** | Ring mould plus plunger and ejector (the Formax mould-plate principle); lever presses | Formax plates give weight within +/-0.5 % [S R22]. Household ring 100 mm, 120 g patty: press 80-240 N [E] | Weigh portion first on the load cell; the ring, plunger and ejector are stainless and washable |
| **Forming meatballs / Frikadellen** | Two hemispherical cavities that close, or a scoop with a sweeper; flattened pucks | 30-50 g each [E] | Pucks (flattened Frikadellen) are easier than spheres |
| **Rolling (Rouladen)** | Flexible silicone mat rolled like a sushi mat, reusable stainless Rouladen clip or pin, or twine; buy pre-sliced 5 mm slices | Filling weight 30-50 g [E] | Least automatable; strongly consider fixed, pre-formed alternative such as a stuffed cutlet shape |
| **Skewering** | Pointed skewer pressed through gripped cubes | Force 5-20 N per cube [E] | Rare; avoid or serve unskewered |
| **Trimming, deboning** | Not feasible in v1 | | Buy boneless, trimmed, portioned |

### 4.2 Raw-meat hygiene (design rules)

* Separate zones: a "raw" zone with dedicated tools and vessels, and a "ready-to-eat" zone. Raw
  tools are washed at 70 C or above with detergent, then dried, before touching anything else
  [M; confirm in R6].
* Cook whole cuts to a core temperature of at least 70 C for 2 minutes, poultry at least 75 C
  [M, BfR/USDA style guidance; confirm].
* Minimise splashes: closed lids, low drop heights.
* Tag every tool as raw or clean in the software so a tool that touched raw meat cannot be
  used on salad until washed.
* Prefer vacuum packs sealed until the machine opens them (R7).

### 4.3 Recommendation (meat)

Buy portioned cuts. Provide one **press station** (flat plate, ring mould, sphere-pair inserts)
that flattens, forms patties and presses coating; mince in the bottom-blade bowl from
semi-frozen cubes or buy frozen mince. No dedicated grinder, no blade tenderiser, no skewering
in v1. Rouladen: buy sliced, roll on a silicone mat with a clip, or treat as an optional recipe
set.

---

## 5. Eggs

| Method | Principle | Data | Comment |
|--------|-----------|------|---------|
| **Commercial breakers** (Sanovo OptiBreaker, Moba Pelbo) | Curve-controlled breakers hit and pull the shell apart over a cup; separators hold the yolk in a slotted cup | OptiBreaker Basic 2: 30 cracking units, 21,600 eggs/h, separation time 5 s, optional CIP [S R7]; larger models 90,000-216,000 eggs/h [S R7]; only 1-3 % of egg stays in shell on good machines [S R7] | Industrial scale, far too large, but the principle miniaturises |
| **Small crackers** (30-100 eggs/h) | Knife or blade scores the shell, jaws pull it apart | USD 20-30 manual, USD 120-150 electric [S R7b] | Cheap, plastic, suitable as reference |
| **Robot egg cracking cell** | Arm picks an egg and taps it on an edge | igus gantry demo with threaded spindles and 3D-printed parts [S R7b] | Success needs impact energy 0.05-0.2 J [E] |
| **Liquid egg** (carton pasteurised whole, yolk, white) | Dose as a liquid | Whole liquid egg is not an equal replacement in fried, poached or soft-boiled uses | Removes shells, spills and yolk handling for scrambles, batters and baking |
| **Whole in shell** | Place in the boiling water | | Soft or hard boiled eggs need no cracking |

**Egg cracker module (design sketch, [E]).**

1. The gripper drops an egg on a nest above a slotted separator cup and a receiving vessel.
2. A spring-loaded blade strikes the equator with about 0.1 J and scores the shell.
3. Two silicone-tipped jaws rotate 60 deg and pull the shell halves apart; contents fall.
4. A camera checks for shell fragments; a small strainer spoon retrieves them.
5. Shell halves fall into a shell bin (waste) via a chute; spray wash follows every raw egg
   because of Salmonella.

**Recommendation.** Whole eggs in shell for boiled eggs; egg cracker module for fried eggs and
scrambles; liquid egg in cartons as the default for batters and baking.

---

## 6. Mixing, kneading, whipping, folding, emulsifying, pureeing, mashing

### 6.1 Existing machines and their numbers

| Machine | Principle | Power / size | Load | Tag |
|---------|-----------|--------------|------|-----|
| Thermomix TM6 | Bottom blade with knife; kneading mode in alternating direction | 500 W, 40-10,700 rpm, 2.2 L | approx. 500 g flour [M] | [S R4] |
| KitchenAid (tilt-head / bowl-lift) | Planetary hook, whisk, paddle; power hub for attachments | 325-500 W DC motor, hub top speed about 280 rpm | approx. 1-1.5 kg dough for home models [M] | [S R5, M] |
| Ankarsrum Assistent | **Bowl rotates, tools are fixed**; roller and scraper knead like hands; whisk | 600 W, 7 L steel bowl and 3.5 L plastic bowl, 5 kg dough or 1.5 L liquid; dough roller, knife and steel bowl are dishwasher safe | 5 kg dough | [S R29] |
| Spiral mixer (small pro) | Spiral hook plus rotating bowl | 750 W for 5-10 kg dough; 1.5 kW for 8 kg (Amazon listing); 1.8 kW for 25 kg (Spiralmac) | | [S R30] |
| Kenwood Chef | Planetary bowl tools plus three outlets | 1,000 W class [M] | | [S R6, M] |
| Immersion blender | Bell-guarded blade | 200-800 W, 10,000-15,000 rpm [M] | | [M] |
| Potato ricer / food mill | Piston or paddle pushes cooked food through a 2.5-3 mm perforated plate | Piston force about 300-1,000 N for 500 g hot potato through 3 mm holes (hand ricers use a lever) [E]; use a 1-2 kN electric cylinder | Skins stay in the hopper | [E] |

### 6.2 Torque and power per batch (derived)

From the three dough machines above, motor rating per kg of dough is about 72-150 W/kg:
Ankarsrum 600 W / 5 kg = 120 W/kg; 750 W / 5-10 kg = 75-150 W/kg; Spiralmac 1,800 W / 25 kg
= 72 W/kg [S R29, R30]. [E] planning numbers:

| Batch | Motor rating | Torque at 100 rpm (eta 0.7) | Comment |
|-------|--------------|-----------------------------|---------|
| 0.5 kg dough | 60-75 W | 4-5 Nm | One person's pizza |
| 1 kg dough | 100-150 W | 7-10 Nm | Family bread |
| 1.5 kg dough | 150-225 W; choose 300 W | 14-20 Nm | Upper limit for the standard bowl |
| Whipping cream, egg white (0.5 L) | 100-200 W at 500-1,500 rpm | 1-2 Nm | Bowl must be fat-free for egg whites; dishwasher residue kills foam |
| Emulsify mayonnaise (0.3 L) | 100-300 W at 3,000-6,000 rpm | 0.3-1 Nm | Oil dribbled at 1-2 g/s from the pump |
| Chop / puree in bottom-blade bowl | 300-500 W at 3,000-10,000 rpm | 0.5-1.5 Nm | Blade tip speed 30-60 m/s [E] |
| Minced meat from semi-frozen cubes (0.5 kg) | 300-500 W at 1,500-3,000 rpm | 2-5 Nm start [E] | Motor stall risk at -4 C |
| Stirring viscous stew, ragu | 30-60 W | 5-10 Nm at 20-40 rpm [E] | Stirring is low power, but torque is high near the bowl wall |

Formula: T = P * eta / (2 pi n / 60). Example: 300 W * 0.7 / 10.5 rad/s = 20 Nm at 100 rpm.

**Folding** (whipped whites into batter) uses a slow reversing paddle or a robot-held
silicone spatula in a figure-of-eight path; the Thermomix reverse low speed does the same
[M]. **Mashing:** a spinning blade ruptures starch cells and makes potato gluey. Use a ricer,
food mill or slow paddle plus warm butter and milk, never a blade [M].

### 6.3 How to drive the tools (seal problem)

| Concept | Principle | Torque | Pros | Cons |
|---------|-----------|--------|------|------|
| **A. Bottom drive through a shaft seal** (Thermomix, cutter mixers) | Removable blade unit with lip seal or mechanical seal | any (10+ Nm ok) | Proven; strong for kneading | Seal ring is a biofilm and leak point; needs replacement every 1-2 years [M] |
| **B. Magnetic coupling through the bowl floor** (YORI uses magnetic coupling of pot and mixer [S R13]) | Ring of SmCo or NdFeB magnets on either side of a non-magnetic window | 60-80 mm ring: about 2-4 Nm [E] | No floor penetration; bowl is smooth | Slips when kneading; NdFeB demagnetises above about 80 C (use SmCo); induction heating interacts with metal; window must be plastic or ceramic |
| **C. Bowl rotates, tools fixed** (Ankarsrum) | Bowl bottom engages a dog coupling; tools on a fixed arm | 600 W handles 5 kg dough [S R29] | No seal; bowl is a plain steel bowl; the fixed tool scrapes the wall while stirring; suits stirring in a pot | Needs a tool holder at the top; not for chopping |
| **D. Top drive through the lid** | Blade or whisk on a shaft in a tool lid | any | Bowl is unpierced | Splash and steam on the shaft; poor chopping of small batches |
| **E. Robot-held tool** | Immersion blender or spatula on the arm | 20-50 N | Flexible | Reaction torque on the arm; long dwell times; splash |

**Recommendation.** Two vessel drives: (A or B) for a *chopping bowl* that also spins the wash
basket, and (C) for a *kneading / stirring bowl* that also works as the cooking pot with a fixed
silicone scraper. Concept B with SmCo magnets is worth prototyping for the chopping bowl,
because it removes the seal; keep A as the fallback.

---

## 7. Dough handling

| Operation | Mechanisms | Numbers | Comment |
|-----------|-----------|---------|---------|
| **Kneading** | Concept C bowl, or planetary hook | see 6.2 | Same for bread, pizza, noodles |
| **Proofing** | Heated cabinet at 25-35 C | 30-90 min [M] | Belongs to R5 |
| **Rolling out** | Robot-held rolling pin; twin motorised rollers; flat press | Rolling pin about 20-60 N over 200 mm width [E]; pizza press 1-2 kN [E] | Flour dusting and sticking are the risks |
| **Sheeting (pasta)** | Marcato Atlas-type twin steel rollers, gap 0.6-4.8 mm [M] | | Rollers must not be wet-washed (manufacturer advice [M]); needs scrapers and dry cleaning |
| **Extrusion (pasta)** | Philips-type mixer chamber plus screw and die | 150-200 W, about 500 g in 15 min [S R21]; dies are dishwasher-safe, with poke tools for the holes [S R21] | Dough residue in the chamber; dies clog |
| **Shaping** (bread rolls, pretzels, dumplings) | Moulds, tins, cutters | | Avoid: use tins, cutters or buy frozen |
| **Bread-machine approach** | Kneading paddle at the bottom of the baking tin: knead, prove and bake in the same tin | Loaf tin 1-1.5 kg | Removes transfer and shaping; the paddle leaves a hole |

**Recommendation.** Knead in the concept C bowl; bread and cakes are baked in the tin they are
proved in (bread-machine approach). Pasta: buy dried, or chilled fresh; optionally add a
Philips-class extruder as a wash-in-dishwasher accessory later. Pizza: pressed to a plate-sized
disc between two plates in the press station, or bought as a base.

---

## 8. Breading and coating (Schnitzel)

**Industrial practice.** A predust of flour, a wet batter or egg bath, then breadcrumbs, in a
continuous line. Applicators are drum breaders (products tumble in the crumb) and flatbed breaders
(product falls on a crumb bed, crumb is sprinkled on top, pressure rollers press it on) [S R20].
Machines are made for Schnitzel and Milanese as well [S R20].

**Home-scale mechanism (design sketch, [E]).** One shallow tray with a tilt and drain, a flat
press plate and a silicone brush on the manipulator:

1. Dust flour (10 g/portion) through a sifter shaker onto the cutlet in the tray.
2. Pour the whisked egg (beaten in the bowl) over it; brush it out to cover; drain the excess.
3. Flip the cutlet with the spatula.
4. Dose breadcrumbs (30-60 g/portion) onto the tray, lay the cutlet in it, press with the plate
   at 20-50 N, flip and press again.
5. Shake off loose crumb over the tray, move the cutlet to the pan.

This avoids three separate dipping trays. Crumb and flour that touched raw egg and meat are
discarded and the tray is washed at 70 C or above every batch. Alternatively, the classical
three-tray "Panierstrasse" with the manipulator dipping the cutlet works with off-the-shelf
trays.

**Tumbling drums** suit nuggets, wings, fish fingers and croquettes; they break flat cutlets
[S R20]. Use only if such items are required.

**Recommendation.** Press station plus coating tray; alternatively buy frozen breaded products
for rarely used recipes.

---

## 9. Dosing and dispensing from a storage box into a vessel

### 9.1 Principles by ingredient form

| Form | Mechanism options | Accuracy | Difficulty | Easy to self-clean? |
|------|-------------------|----------|-----------|--------------------|
| **Thin liquids** (water, milk, stock, wine) | Water: mains valve plus flow meter; other liquids: peristaltic pump, gear pump, or tilt-pour with a load cell | Peristaltic +/-0.5-2 % of set point [S R16]; load-cell feedback tilt-pour 1-3 g | Drips, foam | Peristaltic: flush the tube; tilt-pour: box is washed with the boxes |
| **Oils** | Peristaltic pump (silicone or TPU tube), tilt-pour | 1-2 g | Film on walls (1-3 % residue [E]) | Pump tube needs periodic replacement [S R16] |
| **Viscous pastes** (tomato paste, mustard, honey, jam) | Squeeze-tube rollers, piston or progressive-cavity pump, spoon or scoop on the manipulator | +/-3-5 % volumetric [E] | Residue 3-10 % without a scraper [E] | Pouch cartridges are disposable; piston needs CIP |
| **Powders** (salt, sugar, flour, spices) | Tilt-pour plus vibration; rotary volumetric cup (Solbern-type); auger module (YORI); shaker lid | Volumetric cups +/-0.3-1 % industrial [S R17]; screw feeder +/-3-5 % volumetric, under 2 % gravimetric, batch 3 g [S R15]; load-cell C3 +/-0.1-0.5 % of set point [S R15] | Bridging, static, humidity | Tilt-pour: yes; rotary cup: cup lid washes with the box; auger: motor coupling and screw are difficult |
| **Granular** (rice, pasta, lentils, oats) | Tilt-pour with a gate and a vibrating tray (electromagnetic vibratory feeder [S R18]); volumetric cup; screw | 1-2 % with a load cell [E] | Easiest class | Yes |
| **Whole produce** (potato, onion, tomato, egg) | Tilt-pour to a ramp then singulate by vision; gripper pick; tongs | Count-based | Bruising | Gripper is washable |
| **Leafy** (spinach, lettuce, herbs) | Gripper or tongs; tilt-pour with shaking; weigh | 5 % [E] | Bridging, fluffy | Gripper washable |
| **Sticky** (mince, cheese shreds, cooked rice, dough) | Scoop or portion scoop with a sweeper; box with a push-out plate; robot scraper | 5-10 % by weight per grab [E] | Residue | Robot-held tools wash in the tool washer |
| **Frozen** (peas, spinach block, berries, diced onion) | Tilt-pour (IQF); stir or blade for blocks | Same as granular | Clumping after freeze-thaw; frost | Condensate on the box needs drying |

### 9.2 Gravimetric accuracy and load cells

* Practical accuracy of a strain-gauge scale is about 0.1 % of capacity: a 5 kg cell gives about
  +/-5 g; a 1 kg cell +/-0.5 g with good calibration and stable temperature [S R19]. C3-class cells
  with calibration reach +/-0.1-0.5 % of set point in powder batching [S R15].
* Cheap cells drift with temperature; warm up 15-30 minutes and compensate in software [S R19].
  Never mount cells under the induction plate; keep them thermally isolated.
* The HX711 amplifier is 24-bit, gain 128, 10 or 80 sample/s [S R19]; for better noise use an
  ADS1256 or NAU7802 [M].
* **Two ranges.** Spices (0.1-10 g, e.g. 2 g salt for 500 mL pasta water is a typical weigh-in
  [E]) need a 100-200 g cell with 0.05-0.1 g resolution; bulk (10 g-3 kg) uses a 5-10 kg cell
  with +/-1-5 g.
* Loss-in-weight from the box: the manipulator holds the box static and a wrist force sensor
  reads the loss [E], as a redundancy check only (arm motion adds noise).
* Feedback loop: tilt in pulses, observe the weight rise, stop early by the measured in-flight
  amount (about 1-3 g for granular material) [E].
* Chef Robotics: deposit within 1 % of target for corn and olives; 12 % more depositions
  within range overall [S R14].

### 9.3 Bridging, clumping, humidity and steam

* **Bridging.** Fine cohesive powders form arches over narrow outlets, and compressibility makes
  volumetric dosing error grow [S R15]. Use a wide slot opening, a sloping wall, vibration
  (100-200 Hz eccentric motor or piezo) and tilt angles of 110-135 deg for flour.
* **Oily and sticky powders** (paprika with oil, ground nuts, cocoa butter mixes) are often
  unsuitable for automated weighing [S R15]; use a shaker or a spoon on the manipulator.
* **Humidity and steam.** Boiling at 2 kW evaporates 2 kW / 2.257 MJ/kg = 0.89 g/s (about 53 g/min),
  which is 1.5 L/s of steam at 100 C [E]. Any open dispenser above or beside a pot will take
  up moisture. Salt, sugar and spice mixes cake. Design rules:
  1. Do not dispense spices above the cooking vessel. Dose into a **weigh cup** at a dry
     dosing station in the storage exit zone and carry the cup to the vessel.
  2. Boxes are closed except while dosing; use a shutter, not a hole.
  3. Extraction hood or a small air curtain over the cooking vessels.
  4. Silica-gel desiccant cartridges in spice boxes [M].
* **Static** makes fine powders cling to plastic; use stainless or antistatic-coated cups [M].

### 9.4 Which method is easiest to self-clean (ranking)

1. Tilt-pour with gate and vibration: no mechanism in the food path; the box (and its lid) is
   washed in the box washer.
2. Shaker lid with a perforated plate (sifter): a cheap 3D-printed lid; washes with the box.
3. Rotary volumetric cup in a lid module: cup and vane washed with the box; motor coupling stays
   dry.
4. Peristaltic pump: the fluid contact is the tube only; flush water clears it; replace the tube
   annually [S R16].
5. Auger module (YORI: eight modular screw units with geared DC motors and magnetic power and
   I2C coupling [S R13]): fine, but the screw has to be removed to wash.
6. Piston or progressive-cavity pump: needs a CIP loop.

### 9.5 Recommendation

Standardise **three box lid types** on the standard box: (a) **pour lid** with a sliding or flap
gate for granulates and pieces; (b) **shaker lid** with a sifter plate and vibration for powders
and spices; (c) **liquid bottle** with a pump port, for oils and sauces. A dosing station with a
load cell on the vessel platform and a small spice cell on a second platform. Mains water by
valve plus flow meter.

---

## 10. Transfer between vessels

### 10.1 Tilt-pour geometry

* A rectangular container tilts about its bottom edge or a pivot at the spout. For thin flows
  and granulates tilt to 90-120 deg; for powders 110-135 deg with vibration.
* The pour stream lands within about +/-5 mm if the lip is 10-30 mm from the target and the
  tilt is slow [E]; a pouring lip with a V-notch narrows the stream.
* Pour heights above 100 mm splash hot liquids; use a low pour or a slide into the vessel.
* **Chute or funnel:** angle at least 60 deg for sticky material, 35-45 deg for granules; 3D
  printed and removable for the washer.
* **Curved ramp with squeegee** transfers from pan to pan (YORI) [S R13].
* **Robot scraper.** A silicone spatula on a manipulator, or a fixed silicone wiper on the vessel
  edge, collects the residue.
* For sticky mass (dough, mince, mash), turn the vessel over a target and scrape the wall with a
  fixed wiper mounted at the rim (a "bowl scraper" ring) while tilting [E].

### 10.2 Residue by food type (estimates, [E]; to be measured by D4)

| Food | Residue after tilt to 120 deg and 2 s tap | With one scraper stroke |
|------|-----------------------------------------|--------------------------|
| Dry free-flowing (rice, lentils, pasta, salt) | 0.05-0.3 % | less than 0.1 % |
| Powders (flour, cocoa, spices) | 0.3-2 % | 0.1-0.5 % |
| Cut vegetables, wet | 0.5-2 % (pieces stuck) | less than 0.5 % |
| Thin liquids (water, stock, milk) | 0.5-1 % film | rinse if needed |
| Oil | 1-3 % film | 0.5-1 % |
| Viscous paste, sauce | 3-10 % | less than 1 % |
| Dough and batter | 5-15 % | 1-3 % |
| Minced meat, fat-rich | 3-8 % | 1-2 % |
| Cooked rice, mash | 2-5 % | about 1 % |

**Residue is not lost if the rinse goes into the food.** Rinse the empty vessel with the cooking
liquid or the recipe's water (deglazing rinse) before it goes to the washer. This raises yield
and cuts washer load.

---

## 11. Straining, draining, skimming, deglazing

| Operation | Mechanisms | Comment |
|-----------|-----------|---------|
| **Pasta and vegetable draining, blanching** | (a) Lift-out perforated basket (as in commercial pasta cookers and fryers, and the Thermomix simmering basket) raised by the arm or a lift; (b) bottom drain valve plus sieve plate in the vessel; (c) pour through a colander | 4 L water at 100 C is about 4.5 kg; pouring is risky. (a) is recommended: basket 1-1.5 kg loaded, drain 20-30 s, tilt, tip into the next vessel. Reserve pasta water by taking a measured cup or draining partially |
| **Blanching and shock** | Same basket moved into a cold-water sink | Use mains water 2.2-5 bar |
| **Skimming** | Skimmer ladle on the manipulator, or overflow weir; fine-mesh skimmer | Foam from stock; can be replaced by overflow of a wide bowl |
| **Deglazing** | Dose liquid (wine, stock, water) into the hot pan; scrape with a fixed silicone or steel scraper | Needs a splash lid and steam extraction; the liquid comes from the same dosing lines |
| **Straining sauce** | Food mill, or fine sieve basket in a bowl | The food mill also removes skins and seeds |
| **Draining oil from fried food** | Basket lift with pause; paper, or a rack | |

---

## 12. End-effectors and tool changing

### 12.1 Load case for the manipulator tools ([E])

Tool 0.2-0.5 kg, food load up to 1-1.5 kg (basket, ladle), lever arm 0.25 m: static moment
about 5 Nm, design for 10-15 Nm with dynamics. Scraping and pressing: 20-50 N. Heavy work
(chopping, kneading, pressing 1-2 kN) is done at fixed stations, not by the arm. So the changer
handles light tools only.

### 12.2 Grippers

| Gripper | Data | Fit | Tag |
|---------|------|-----|-----|
| **Festo HPSX** universal adaptive gripper | Silicone fingers, 0.5 kg payload, 15 g acceleration, sizes 40, 70, 100 mm, IP69K washdown, food-grade and metal-detectable, tool-free finger replacement, about 5 million cycles per finger, ISO 50 interface, 2-, 3- and 4-finger versions, direct contact with raw proteins allowed | Eggs, tomatoes, potatoes, meat slices; price on quote (estimate EUR 1,500-3,000) | [S R28], price [M] |
| **Festo DHAS** adaptive fin-ray fingers | Sizes 60, 80, 120 mm; fin-ray effect; used on fruit and vegetables | Cheap way to add compliance to a parallel gripper | [S R28] |
| **Soft Robotics mGrip** | Pneumatic soft fingers, food-grade, washdown | Produce and meat pieces | [M] |
| **OnRobot soft gripper / Piab piSOFTGRIP** | Silicone bellows or vacuum-driven soft gripper | Fragile produce | [M] |
| **Chef Robotics utensils** | "Food safe, IP67 pneumatic parallel actuator" with proprietary utensils; a limited set per class of food (sauces vs diced vs long); under 10 minutes to disassemble, clean and reassemble modules | Shows that a small set of utensils per food class works in production | [S R14] |
| **Hygienic parallel grippers** (Schunk, Zimmer, Festo, stainless IP69K) | Stainless, sealed bearings | Rigid jaws for handled tools | [M] |

Hygienic design rules for grippers and tools ([M], EHEDG-style): no hollow tubes, no exposed
threads, smooth surface (Ra of about 0.8 um or better), radii of at least 3 mm, self-draining
slopes, food-grade silicone/PEEK/316L, sealed IP69K joints, no electronics in the wet zone.

### 12.3 Ways to change tools

| Option | Principle | Data | Pros | Cons |
|--------|-----------|------|------|------|
| **A. Grasp-the-tool (no changer)** | One good two-finger gripper picks handled tools (spatula, ladle, tongs, scraper, brush) by a standard handle with a V-groove and a flange | Utensils are passive, 100-300 g [E] | No electrics or air in the tool; every tool is a plain stainless or PP part that goes in the washer; Chef Robotics does this with utensils [S R14] | Limited torque transfer; tools are passive; handle must self-locate (cone plus flange) |
| **B. Kinematic coupling with a lock hook** (Prusa XL, E3D ToolChanger, Jubilee) | Three balls seated in three pairs of cylindrical pins; a rotary hook draws the tool tight | Prusa XL holds up to 5 toolheads with a Kelvin coupling and a motor-driven hook; repeatability +/-0.015 mm when clean, over 0.08 mm with dust [S R27]; XL+ single-tool price EUR 2,299 [S R27b] | Repeatable, mechanically simple, 3D-printable [E]; kitchens need only 0.5 mm | Balls and pin pockets are crevices; must sit in a dry, shielded zone; pogo pins for electrics are not washable |
| **C. Magnetic plus kinematic** | Magnets pull the tool onto a 3-ball seat; a small bayonet twist locks it | Hold force 10-30 N per magnet pair [E] | Flat, wipeable faces (seal the magnets in PEEK or steel) | Magnets attract swarf; hold force marginal for scraping; NdFeB temperature limit |
| **D. Pneumatic industrial** (ATI QC-11, Schunk SWS, Zimmer) | Locking piston and balls, compressed air | QC-11: payload 35 lb (16 kg), static moment 180 lbf-in (20 Nm) X/Y and 110 lbf-in (12 Nm) Z, lock force 240 lb (about 1.07 kN) at 80 psi, repeatability 0.0004 in (10 um), coupled mass about 0.25 kg, six air passes [S R27d]; Schunk SWS has 14 sizes [S R27e] | Robust, tested, vendor support | Not hygienic; needs a compressed-air line (compressor 6 bar); overkill for 0.5 kg tools; price not published, estimated USD 700-1,200 per pair [M] |
| **E. Manual flange** (ISO 9409-1-50, Festo HPSX has an ISO 50 interface [S R28]) | Bolted | | Cheapest | Human in the loop; rejected |

**Rack and washer.** All changing options need a tool rack. The tool rack should be part of a
spray cabinet: the manipulator returns each used tool to a washing slot; the next clean one is
taken from a dry slot. This removes the "dirty tool touches clean tool" problem.

**Recommendation.** Use option A for passive tools (spatula, scraper, ladle, tongs, skimmer,
brush). Use option B or C only where a tool needs a different actuator (e.g., a soft gripper
versus the rigid tool-gripper). Avoid pneumatics unless a compressor is already present for air
peeling.

### 12.4 Reusing commercial mixer attachments

| Ecosystem | Interface | Data | Attachments of interest | Tag |
|-----------|-----------|------|-------------------------|-----|
| **KitchenAid** | Power hub with square socket and thumbscrew; any attachment from any era fits any mixer since 1937 | Motor about 325-500 W; hub tops out near 280 rpm | Slicer/shredder, food processor, grinder, pasta roller and cutters, pasta extruder, fruit and vegetable strainer (food mill), spiraliser, sausage stuffer. Many parts are dishwasher-safe [M]; price USD 50-200 each [M] | [S R5], [M] |
| **Kenwood Chef / Major** | Three outlets: high-speed (blender, processor), slow-speed "Twist Connection" (product codes KAX; pasta, mincer, etc.; adapter for old bar type), and a bowl-tool outlet on top | | Mincer, slicer, food processor, pasta | [S R6] |
| **Bosch MUM** | Side power take-off plus bowl tools | | Cutters, mincer, juicer | [M] |
| **Ankarsrum** | Bowl-rotating base; side hub for attachments | 600 W | Grain mill, meat grinder, roller-and-knife | [S R29] |

**Reuse strategy.** Build a small **power-hub module** with the KitchenAid hub geometry
(brushless motor 200-300 W, 10:1 planetary, 20-300 rpm, thumbscrew replaced by a cam or a
bayonet). The hub stays dry; the attachments (grinder, slicer-shredder, food mill, pasta
extruder) are washed in the washer. Only use it if D4 chooses those devices; otherwise a custom
cutter head is simpler. The cost of attachments is far below the cost of a professional unit.

---

## 13. Synthesis: unit operation to mechanism

Column "Rec." is the recommended mechanism. "Avoid" means solve by ingredient choice.

| # | Unit operation | Candidate mechanisms (best first) | Rec. | Avoid by ingredient choice |
|---|----------------|-----------------------------------|------|-----------------------------|
| 1 | Wash produce | Basket in the prep bowl with agitation; spray; ozone/PAA dose | Basket in bowl | Pre-washed leaves |
| 2 | Spin dry | Bottom-drive basket at 600-900 rpm | Bottom drive | |
| 3 | Scrub roots | Silicone brush on arm; drum | Brush on the arm | |
| 4 | Peel potato, root | Skin-on; ricer/food mill retains skin; abrasive drum | Skin-on and ricer; drum optional | Vacuum-peeled potatoes |
| 5 | Peel onion, garlic | Top-and-tail plus rollers; air blast; buy peeled | Buy peeled or frozen; garlic press with skin | Peeled garlic, frozen diced onion |
| 6 | Peel tomato | Blanch and shock; food mill | Food mill for sauce | Canned tomato |
| 7 | Core, destem, stone | Push-through corer; halve and scrape | Avoid | Frozen, canned, pitted |
| 8 | Slice vegetable | Feed-through slicing disc; push-through grid; harp | Disc | |
| 9 | Dice vegetable | Disc plus grid; push-through dicer; bowl blade (rough) | Disc plus grid; bowl blade for sauces | |
| 10 | Julienne, sticks | Julienne disc; slice then cross-cut | Julienne disc | |
| 11 | Grate, shred | Shredding disc; bowl blade | Disc | |
| 12 | Chop onion, herbs | Bowl blade pulses; dicing grid | Bowl blade | Frozen herbs |
| 13 | Mince garlic | Press; bowl blade | Press | Paste, frozen cubes |
| 14 | Slice bread, sausage, cooked roast | Deli slicer; guillotine; buy pre-sliced | Slicer optional | Pre-sliced bread and cold cuts |
| 15 | Portion raw meat (cubes, strips) | Buy cut; semi-frozen slicer plus grid | Buy cut | Goulash, Geschnetzeltes packs |
| 16 | Mince meat | Bowl blade with semi-frozen cubes; grinder; buy mince | Bowl blade, or buy | Frozen mince |
| 17 | Pound, flatten | Press plate 0.5-1.5 kN; roller | Press station | Pre-flattened cutlets |
| 18 | Form patty, Frikadelle | Ring mould with plunger; sphere pair | Press station | |
| 19 | Roll, stuff (Rouladen) | Silicone mat with clip; buy pre-rolled | Optional recipe set | Ready Rouladen |
| 20 | Skewer | Skewer press | Avoid | Serve loose |
| 21 | Crack egg | Blade and jaws module; liquid egg | Module | Liquid egg |
| 22 | Separate egg | Slotted cup on the module | Module | Liquid yolk and white |
| 23 | Whisk, whip | Bottom-drive whisk; concept C whisk | Concept C bowl | |
| 24 | Knead | Concept C roller and scraper; planetary hook | Concept C | Bought dough |
| 25 | Mix, stir | Fixed scraper plus rotating vessel; robot spatula | Concept C | |
| 26 | Fold | Slow reversing paddle; robot spatula | Slow paddle | |
| 27 | Emulsify | Bottom blade plus pump dribble | Bottom blade | Bought mayonnaise |
| 28 | Puree, blend | Bottom blade; immersion blender; food mill | Bottom blade | |
| 29 | Mash | Ricer / food mill; slow paddle | Ricer in press station | |
| 30 | Roll out dough | Robot pin; plate press; twin rollers | Plate press | Bought dough sheets |
| 31 | Pasta | Buy dried or chilled; extruder attachment | Buy | Dried pasta |
| 32 | Shape bread, cake | Tins; bread-machine approach | Tins | Bought pastry |
| 33 | Coat, bread (Schnitzel) | Tray plus press and brush; three trays | Tray plus press | Frozen breaded |
| 34 | Dose thin liquid | Peristaltic; mains valve; tilt-pour | Pump / valve | |
| 35 | Dose viscous paste | Pouch and rollers; scoop; piston | Scoop or pouch | Bottled sauces |
| 36 | Dose powder, spice | Shaker lid with vibration; rotary cup; auger | Shaker lid, weigh cup | |
| 37 | Dose granulate | Tilt-pour with gate and vibration | Tilt-pour | |
| 38 | Dose whole produce | Tilt onto a ramp and pick by vision; gripper | Ramp and gripper | |
| 39 | Dose leafy | Gripper with weigh check | Gripper | Frozen spinach |
| 40 | Dose sticky | Scoop with sweeper; push-out box; robot scraper | Scoop | |
| 41 | Vessel to vessel | Tilt-pour; ramp and scraper; rinse | Tilt plus scraper plus rinse | |
| 42 | Drain, blanch | Lift-out basket; drain valve | Basket | |
| 43 | Skim | Skimmer on the arm; overflow | Skimmer | |
| 44 | Deglaze | Liquid dose plus scraper | Dose plus scraper | |
| 45 | Citrus juice | Reamer press in the press station | Press station | Bottled juice |
| 46 | Zest | Shredding disc or grater plate | Avoid | Dried zest |

---

## 14. Minimal tool set

| # | Tool / station | Function | Key specification ([E]) | Operations covered (numbers from section 13) |
|---|----------------|----------|-------------------------|-----------------------------------------------|
| 1 | **Chopping bowl** with bottom drive (concept A or B) and perforated basket | Chop, mince, puree, emulsify, whip, wash and spin | 2.5 L, 500 W, 40-10,000 rpm, basket 600-900 rpm, blade unit and basket dishwasher-safe | 1, 2, 12, 13, 16, 27, 28 |
| 2 | **Rotating-bowl kneader / stirrer** (concept C), which is also the cooking pot with a fixed silicone scraper | Knead, whisk, fold, stir; dough up to 1.5 kg | 4-7 L, 300 W, 10-20 Nm at 100 rpm | 23-26, 32 |
| 3 | **Feed-through cutter head** | Slice, shred, stick, dice | 300-500 W, 400 rpm, chute at most 40 x 40 mm, 5-8 discs and a 10 mm grid, jam detection by motor current | 8-11 |
| 4 | **Press station**: 2 kN electric cylinder, 150 mm stroke, tool plates | Flatten cutlets, patty ring, ricer chamber, citrus reamer, garlic press, pizza plate, coating press | 2 kN, 20-50 mm/s | 5, 17, 18, 29, 30, 33, 45 |
| 5 | **Egg module** | Crack, separate | 1 egg per 10 s; blade 0.1 J | 21, 22 |
| 6 | **Weigh and dose station** | Dose all forms from boxes | Two load cells (200 g and 10 kg), tilt gantry with vibration, pumps, mains valve and flow meter | 34-41 |
| 7 | **Manipulator with passive utensil set** | Scrape, flip, skim, lift baskets, pick, brush | 3 kg payload, soft or fin-ray gripper, 6 utensils | 3, 41-44 |
| 8 | **Tool rack in a spray cabinet** | Wash and store utensils and discs | | all |
| 9 | Optional: **deli slicer**, **pasta extruder**, **abrasive drum**, **grinder attachment** | Carving; fresh pasta; peeled potatoes; mincing | | 4, 14, 31 |

**Fit against the 95 % goal (qualitative).** Items 1-8 do every operation in section 13 except
skewering, coring of many fruits, Rouladen rolling, hand-shaped pastry and bone work. Those are
either avoided by ingredient choice (frozen, canned, pre-cut, pre-sliced) or listed as optional
recipes. The measured coverage must be computed against the meal corpus of R2.

**Count of moving mechanisms:** 2 bowl drives, 1 cutter drive, 1 press cylinder, 1 egg module,
1 tilt gantry with vibration, pumps, 1 manipulator, 2 load cells. This is a small set for the
range covered.

---

## 15. Operations better avoided by ingredient choice

| Operation | Why it is hard | Substitute |
|-----------|----------------|-----------|
| Peeling potatoes, carrots | Irregular, water, waste; abrasive drum is bulky | Skin-on, ricer or food mill, vacuum-peeled potatoes |
| Peeling onions and garlic | Delicate skins; air or blades | Peeled cloves, frozen diced onion, garlic paste |
| Coring, stoning (avocado, cherries, mango) | Each fruit needs its own head | Frozen or canned pitted; avocado pulp |
| Butchering, deboning, trimming fat | Force and safety | Boneless, trimmed and portioned packs |
| Cutting raw meat to cubes or strips | Workholding and hygiene | Goulash, Geschnetzeltes and stir-fry packs |
| Slicing Rouladen | Thin slices from a muscle | Pre-sliced Rouladen meat |
| Skewering | Needs pointed skewers and force | Serve loose; cook cubes on the plate |
| Cracking many eggs | Shell, spill | Liquid egg in cartons |
| Fresh pasta, dumplings | Rolling, cutting, filling | Dried or chilled pasta; frozen dumplings, Maultaschen |
| Fish (gutting, filleting) | Bones | Fillets |
| Shaping bread and pastry | Skill | Tin loaves, bought puff pastry |
| Shelling peas, beans, nuts | Small parts | Frozen or shelled |
| Segmenting citrus, carving fruit | Skill | Canned or juice |
| Decorative plating cuts | Aesthetic | Standard shapes |

Trade-offs: pre-cut and vacuum-packed items cost more and last days to weeks [M]. The ingestion
module (R7) must record the pack type and shelf life, and the meal planner (D10) must prefer
recipes that match the available forms.

---

## 16. Candidate components with prices

Prices marked [S] were seen in a listing; the rest are approximate street or list prices from
memory [M], +-30 %, to be verified in D4 or the BOM (B1).

| Component | Model or class | Price | Tag |
|-----------|----------------|-------|-----|
| Prototype chopping bowl | Vorwerk Thermomix TM6 (500 W, 40-10,700 rpm, 2.2 L) | EUR 1,300-1,500 (TM5 launch EUR 1,139) | [S R4b], [M] |
| Prototype chopping bowl | Robot Coupe R2 or R301 cutter-mixer | USD 1,500-2,500 | [M] |
| Custom bowl drive | BLDC 500 W plus controller, SmCo ring coupling | USD 150-350 | [E] |
| Prototype rotating-bowl mixer | Ankarsrum Original (600 W, 7 L bowl) | USD 650-800 | [M] |
| Custom kneader drive | 300 W BLDC plus 10:1 planetary | USD 150-300 | [E] |
| Prototype cutter head | Robot Coupe CL50 (1.5 HP, 425 rpm) | USD 2,500-3,500 | [M] |
| Dicing kit | Robot Coupe 10 x 10 mm, CL50 | USD 250-400 | [M] |
| Push-through dicer | Vollrath Redco InstaCut 3.5, 3/8 inch | USD 285; blade assembly USD 107 | [S R24] |
| Kitchen attachments | KitchenAid slicer/shredder, grinder, strainer | USD 50-200 each | [M] |
| Meat grinder (if used) | #12, 750 W, 170-200 rpm | USD 250-500 | [M] |
| Press | 2 kN electric cylinder, 150 mm stroke | USD 150-400 | [M] |
| Load cells | 200 g and 10 kg strain-gauge, HX711 or NAU7802 amplifier | USD 3-15 each; amplifier USD 1-10 | [M] |
| Peristaltic pump | Small food-grade (about 100-500 mL/min) | USD 30-60; large USD 200-500 | [M] |
| Vibration motor | Eccentric 12-24 V | USD 5-20 | [M] |
| Egg cracker reference | Electric small-scale, about 100 eggs/h | USD 120-150 | [S R7b] |
| Tool changer (printed) | Kinematic coupling, servo-driven hook | USD 30-80 | [E] |
| Tool changer (industrial) | ATI QC-11 or Schunk SWS | USD 700-3,000 per pair | [M] |
| Reference multi-tool platform | Prusa XL+ single tool | EUR 2,299 | [S R27b] |
| Gripper | Festo HPSX (0.5 kg, IP69K) | quote; estimate EUR 1,500-3,000 | [S R28], [M] |
| Fin-ray fingers | Festo DHAS | EUR 50-150 per pair | [M] |
| Compressor (only if needed) | Diaphragm, 6 bar | USD 60-150 | [M] |
| Ultrasonic blade | 20 kHz kit | USD 600-2,000; industrial five figures | [M], [S R11] |
| Pasta extruder | Philips 7000 series (150-200 W) | EUR 200-350 | [S R21] for power, [M] for price |
| Pasta sheeter | Marcato Atlas 150 | EUR 80-120 | [M] |
| Deli slicer | 250 mm | USD 500-1,500 | [M] |

---

## 17. Sources

R1. Effects of knife edge angle and speed on peak force and specific energy when cutting vegetables of diverse texture. https://www.researchgate.net/publication/305488455_Effects_of_knife_edge_angle_and_speed_on_peak_force_and_specific_energy_when_cutting_vegetables_of_diverse_texture_Cutting_force_and_specific_energy_for_vegetables_23 ; https://pdfs.semanticscholar.org/c0fd/d64045bf6337bad1130543b93fc3a54121b1.pdf (Int. J. Food Studies, 2016; only the abstract-level numbers were readable)
R2. Energy requirements for cutting of selected vegetables: a review (CIGR Journal 2018). https://cigrjournal.org/index.php/Ejounral/article/download/4949/2892/22924
R3. Robot Coupe CL50: https://webstaurantstore.com/robot-coupe-cl50-continuous-feed-food-processor-1-1-2-hp/649CL50ND.html ; dicing kit https://www.amazon.com/Robot-Coupe-Dicing-Kit-CL50/dp/B0017S4J92 ; https://www.robot-coupe.com/export/en/p/discs-dicing-equipment-10x10x10-mm/18324
R4. Vorwerk Thermomix TM6 manual and specification. https://www.vorwerk.com/gb/en/c/dam-home/service/instruction-manuals/TM6_digital_manual_MGB-en-GB_prefill_20190207.pdf ; https://thespoon.tech/here-they-are-the-full-thermomix-tm6-specs/
R4b. https://en.wikipedia.org/wiki/Thermomix
R5. KitchenAid attachment hub. https://medium.com/@MrProduct/kitchenaid-mixer-attachments-all-83-attachments-add-ons-and-accessories-explained-45e49e71ef64 ; https://www.kitchenaid.com/content/dam/global/documents/201904/spec-sheet-ksm8990.pdf
R6. Kenwood outlets. https://www.kenwoodworld.com/en/products/attachments/high-speed-outlet-attachments/c/high_speed_outlet ; https://thekenwoodguys.com/collections/slow-speed-outlet
R7. Sanovo egg breakers. https://www.sanovogroup.com/en/egg/solutions/egg-processing/optibreaker-plus-12/ ; https://www.thepoultrysite.com/articles/easing-the-pains-of-egg-and-chick-processing
R7b. Small-scale egg breaking. https://making.com/equipment/small-scale-egg-breaking-and-separation ; https://rbtx.com/en-US/solutions/jsl-solution-egg-cracking-machine-room-linear-robot-xyz-gantry
R8. Abrasive and steam peeling. https://www.potatopro.com/about/carborundum-peelers ; https://www.potatopro.com/news/2025/abrasive-peeling-%E2%80%93-gentle-yet-effective-delicate-produce ; https://www.potatopro.com/about/steampeeler ; https://www.tomra.com/food/machines/peeling-line
R9. Air-blast garlic and onion peeling. https://www.verfoodsolutions.com/products/vegetable-process/garlic-peeling-machine/automatic-garlic-peeling-machine/ ; https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/4602559
R10. Warner-Bratzler shear force. https://www.ars.usda.gov/ARSUserFiles/30400510/protocols/shearforceprocedures.pdf ; https://agrilife.org/animalscience/files/2012/04/ASWeb072-warnerbratzler.pdf
R11. Ultrasonic cutting. https://hackaday.com/2025/03/21/high-frequency-food-better-cutting-with-ultrasonics/ ; https://www.sciencedirect.com/science/article/abs/pii/S0958694608002276 ; https://www.sciencedirect.com/science/article/abs/pii/S1466856406000439 ; https://www.sciencedirect.com/science/article/abs/pii/S0260877410005467 (abstracts only)
R12. Water-jet food cutting. https://www.hydroprocess.fr/en/special-water-jet-cutting-machine-for-the-catering-trade-chefcut/ ; https://www.techniwaterjet.com/cutting-food-with-a-waterjet-cutter/
R13. YORI modular robotic kitchen. https://arxiv.org/html/2405.11094v3
R14. Chef Robotics. https://www.automationworld.com/process/robotics/article/55131189/amys-kitchen-boosts-yields-and-production-with-chef-robotics
R15. Dosing selection, load cell batching, spice screw dosing. https://www.palamaticprocess.com/blog/how-select-your-dosing-system ; https://industrialmonitordirect.com/blogs/knowledgebase/designing-load-cell-based-powder-batching-system ; https://www.ddw-online.com/automation-of-solid-powder-dispensing-much-needed-but-cautiously-used-917-200908/ ; https://www.palamaticprocess.com/en-us/case-studies/food-feed/spice-dosing
R16. Peristaltic pumps. https://www.axflow.com/en-gb/applications/technical-support/pump-technologies/hygienic-pump-articles/food-grade-peristaltic-pumps/ ; https://www.coleparmer.com/tech-article/how-to-achieve-accurate-dispensing-with-peristaltic-pumps (page returned 403; figures from the search summary)
R17. Volumetric cup dosers. https://www.vtops.com/product/dry-solids-volumetric-cup-rotary-filling-dispenser/ ; https://heritageequipment.com/product-detail/243/8671/
R18. Vibratory feeders for food. https://www.processingmagazine.com/material-handling-dry-wet/powder-bulk-solids/article/21293774/selecting-electromagnetic-vibratory-feeders-for-food-applications ; https://www.foodengineeringmag.com/articles/99711-vibratory-feeder-dosing-system
R19. Load cell and HX711 accuracy. https://zbotic.in/hx711-load-cell-interface-weight-scale-project-step-by-step/ ; https://forum.arduino.cc/t/how-to-get-more-accurate-reading-out-of-load-cells-with-hx711/500770
R20. Breading machines. https://jbtmarel.com/en/prepared-foods/battered-and-breaded-products/coating/ ; https://nothum.com/equipment/predust-breading/superflex/ ; https://www.ayrking.com/food-prep-equipment/breading-equipment/drumroll-automated-breader/ ; https://www.anko.com.tw/en/food/Batter-Crumb-Breading.html
R21. Philips pasta maker. https://www.documents.philips.com/assets/20221015/1fa0b6cdd833474e9540af2f00cb40a5.pdf ; https://www.home-appliances.philips/gb/en/p/HR2665_93
R22. Patty forming. https://www.provisur.com/en/equipment/forming/f6/ ; https://waltons.com/categories/patty-makers
R23. Meat grinders. https://www.vollrathfoodservice.com/products/countertop-equipment/food-preparation-equipment/grinders/grinders/40743 ; https://www.walmart.com/ip/Weston-12-Heavy-Duty-Electric-Grinder-1-HP/208140460 ; https://www.hubert.com/product/PAF.MC-12/ALFA-12-MEAT-GRINDER-SS-1-HP--110V60HZ---ETL-170-RPM
R24. Vollrath Redco InstaCut. https://www.webstaurantstore.com/vollrath-15001-redco-instacut-3-5-3-8-fruit-and-vegetable-dicer-tabletop-mount/92215001.html ; https://www.webstaurantstore.com/vollrath-15063-redco-3-8-dicing-blade-assembly-for-vollrath-redco-instacut-3-5/92215063.html
R25. Produce washing. https://www.osti.gov/pages/servlets/purl/1981610 ; https://www.foodprotection.org/files/food-protection-trends/Aug-12-Fishburn.pdf ; https://pmc.ncbi.nlm.nih.gov/articles/PMC8000956/ ; https://www.sciencedirect.com/science/article/pii/S0362028X22054588
R26. Salad spinners. https://sammic.com/en/products/salad-spinner ; https://lifetips.alibaba.com/kitchen-hacks/equipment-the-best-salad-spinner (low-confidence; the a = w^2 r arithmetic was re-derived, its "4-6 g" claim is inconsistent and is not used)
R27. Prusa XL tool changer. https://www.theindustrialmaker.com/machines/fdm-3d-printers/prusa-xl-toolchanger-problems-fixes ; https://3dprintingindustry.com/news/prusa-debuts-its-large-format-toolchanger-system-the-xl-3d-printer-technical-specifications-and-pricing-199965/ ; E3D: https://e3d-online.com/blogs/news/research-and-development-motion-system-and-tool-changer (returned HTTP 429, search summary only)
R27b. https://www.prusa3d.com/product/original-prusa-xl-2/
R27d. ATI QC-11. https://www.ati-ia.com/products/toolchanger/QC.aspx?ID=QC-11
R27e. Schunk tool changers. https://schunk.com/de/en/automation-technology/tool-changer/c/PUB_11563
R28. Festo grippers. https://www.therobotreport.com/festo-hpsx-compliant-gripper-designed-meet-industry-requirements/ ; https://www.festo.com/media/catalog/202802_documentation.pdf ; https://press.festo.com/en/node/5135
R29. Ankarsrum. https://www.tasteofhome.com/article/ankarsrum-mixer-review/ ; https://www.ankarsrum.com/us/product/assistent-original-red-r/ ; https://en.wikipedia.org/wiki/Electrolux_Ankarsrum_Assistent
R30. Spiral mixers. https://www.agrieuro.co.uk/dough-mixers/spiral-mixers-c-2322_105.html ; https://pleasanthillgrain.com/spiralmac-25kg-spiral-dough-mixer
R31. Cheddar cutting force and wire cutting. https://texturetechnologies.com/application-studies/cheddar-cheese-cut ; https://labomat.eu/gb/texture-faq/861-case-study-cheddar-cutting-force-measurement.html ; https://www.sciencedirect.com/science/article/abs/pii/S0013794404001997
R32. Robotic meat cutting and knife control. https://pmc.ncbi.nlm.nih.gov/articles/PMC9056033/ (search summary only; page blocked) ; https://arxiv.org/pdf/2508.02604
R33. Other cooking robots for context. https://www.livingetc.com/news/nymble-kitchen-robot ; https://newatlas.com/robotics/moley-robotic-kitchen-launch/ ; https://newatlas.com/cooki-robotic-chef/35510/

Verification limits: the web-search quota was exhausted mid-task, and several pages (E3D blog,
Cole-Parmer, ScienceDirect, PMC, Kenwood guide, arXiv PDFs) could not be read in full.

---

## 18. Open issues

1. **Coverage is not yet measured.** The meal corpus (R2) was not available. The tool set in
   section 14 must be checked against unit-operation counts; particularly how many meals need
   peeled potatoes, chopped onion, diced meat, Rouladen, skewers.
2. **Box lid interface.** Section 9.5 proposes three lid types (pour, shaker, liquid) on the
   standard storage box. This touches the box standard frozen by A1. D4 must raise this with A1
   and D1 if the box has no room for a gate or a shaker plate.
3. **Vessel standard.** Chopping bowl (bottom drive), kneading bowl (rotating) and cooking pots
   are proposed as different vessel classes. The number and sizes of vessels, and who moves them
   (transport or manipulator), belong to A1 and D4.
4. **Magnetic coupling.** Torque (2-4 Nm), slip, heat, and the interaction with induction
   heating are estimates. A bench test is needed before choosing between concepts A and B.
5. **Shaft seal hygiene** in concept A: cleaning validation (R6/V3), seal lifetime.
6. **Feed-through cutter quality** on tomatoes, onions and leafy herbs; jams on long items;
   need for a pre-halving step.
7. **Press station tooling.** One 2 kN press with seven tool plates (flatten, patty ring, ricer,
   citrus, garlic, pizza, coating) needs tool-change logistics and washing of each plate.
8. **Egg module reliability**, shell fragments, raw-egg cleaning cycle.
9. **Residue table** in 10.2 is an estimate; measure with real food.
10. **Peeling.** Decide whether the optional abrasive drum is built, and how starch and peel
    waste is kept out of the drain (screen, settling trap).
11. **Sanitising wash.** Ozone or peracetic acid: legal status, materials compatibility and
    residue limits are open (R6).
12. **Number of manipulators** (one or two) and their payload, especially for lifting a 4-5 kg
    hot pot for draining or pouring.
13. **Noise and vibration** of blades at 10,000 rpm and the dryer at 900 rpm in a home kitchen.
14. **Prices** in section 16 marked [M] are unverified.

## 19. Risks

| Risk | Effect | Mitigation |
|------|--------|------------|
| Cutting quality is worse than a human's (bruised tomato, ragged onion) | Users reject the meals | Use slicing and dicing discs with sharp blades, keep onion for bowl blade, allow cut-form substitutes |
| Feed-through jams and blade wear | Stalls, service calls | Motor-current detection, reversing, standard discs and easy replacement |
| Biofilm in seal crevices, disc hubs, tool-changer pockets | Food safety | Seal-free designs (concepts B and C), smooth radii, flush ports, hot wash at 70 C or above (R6) |
| Raw meat and egg cross-contamination | Salmonella, Campylobacter | Raw and clean zones, tool tags, hot wash between raw and clean use, core-temperature cooking |
| Allergen carry-over (nuts, gluten, milk) | Health | Validate cleaning cycles per allergen; label boxes (R6) |
| Powder caking from steam and humidity | Dosing errors, blockages | Weigh-cup dosing away from the pot, shutters, desiccant, extraction |
| Load-cell drift with temperature and vibration | Wrong recipe amounts | Thermal isolation, two ranges, tare before each dose, redundant check by box weight |
| Magnetic coupling slips or overheats | Blade stops, product left raw | SmCo magnets, torque sensing, fallback concept A |
| Tool-changer contamination or wear | Missed pick, tool drop | Use passive grasp-the-tool option, keep changers in dry zones, teach re-calibration |
| Blade injury during service | Injury | Interlocks, guarded stations, blades removable only when powered off |
| Reliance on ingredient choice | Shorter shelf life, higher cost, region-dependent supply | Make recipe planner aware of pack forms (D10), provide optional attachments (drum, slicer, grinder) |
| Mechanism count grows with each recipe | Cost, failure rate, maintenance | Stick to the minimal set; every additional device needs a cleaning method (R6) |
| Unverified numbers | Design errors | Tags [S], [M], [E] in every table; verify [M] and [E] items in the prototype phase |
