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
| Potato ricer / food mill | Piston or paddle pushes cooked food through a 2.5-3 mm perforated plate | Piston force 100-300 N for 500 g hot potato [E]; motorised 500-1,000 N electric cylinder | Skins stay in the hopper | [E] |

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
