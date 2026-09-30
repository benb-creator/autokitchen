# P1 ideas — lens B: food-industry process engineering, scaled down

Round P1 (idea finding) for meal preparation. Author's lens: how a food factory or a pharmaceutical
batch plant would do it, and what the smallest honest version of each machine is. Written without
reading the other files in `design/prep/ideas/`.

Inputs used: `BRIEF.md`, `DECISIONS.md`, `PLAN.md`, `requirements/requirements.md` (sections 3.1,
3.5, 5, 7), `research/01`, `03`, `04`, `06`. The concepts in section 2 were written before
`research/02-meal-corpus.md` existed, against the unit-operation list of requirements section 5.3.
They were then checked against the finished corpus (248 meals, 126 operations); the result is
section 3.1, and it changed the bet in section 5. Section 2 is left as first written, so where
section 2 and section 3.1 differ (vessel sizes, what counts as a satellite), section 3.1 applies.

All numbers are my own estimates unless a research document is cited. Nothing here is tested.
Box sizes assume the Gastronorm 176 mm family proposed in R3 (GN 1/6: 176 x 162 x 100 mm, 1.5 L).

Contents: 0 what factories teach us, 1 shared front end, 2 four concepts (A Fallturm,
B Trommelwerk, C Kolbenstrang, D Flachband), 3 cross-comparison and corpus check, 4 standalone
sub-mechanisms, 5 the bet, 6 open issues, 7 risks.

---

## 0. What the factory teaches (the principles I am scaling down)

| Factory principle | Why factories do it | Home-scale consequence |
|---|---|---|
| Gravity is the conveyor. Raw material enters at the top floor, product leaves at the bottom. | No transfer mechanism, no transfer residue, and the wash takes the same route. | Use the 2000 mm height: box dock at about 1700 mm, processing at 900-1600 mm, cooking vessel at 700-900 mm, sump and waste below. |
| The container carries its own discharge valve (IBC cone valve, tote with butterfly). | No shared dosing surface, so no cross-contamination and no dosing equipment to clean between products. | Each storage box keeps its own dosing lid. The machine only actuates it from outside (section 1.1). |
| Doorless, shaft-less vessels: drums on rollers, reversing-helix discharge, pigged tubes. | Doors, seals and shafts are where soil hides. | Drum as a cup on a rear shaft (seal outside the food zone), tubes open at both ends, discs that overhang their seals. |
| The product is given a shape the machine can handle: crust-frozen meat, slabs before dicing, plugs in tubes, sheets on belts. | Machines handle geometry, not "food". | Three canonical shapes: *bulk pieces* (tumble, fall), *plug* (push through a die), *sheet* (lie on a belt). Each concept below is built around one of them. |
| Batch identity and clean-in-place with recorded parameters. | Validation. | Every concept has one closed wet zone with a sump, a heated recirculating wash and logged temperature, time and conductivity (HYG-026). |
| The last of the product pushes itself out: pigging, product-to-product push, water chase. | Yield. | "Recipe water as chase": the water, stock or milk the recipe needs anyway is dosed through the soiled path last (idea N9). |

Honest limit of the lens: factories make one product per line. A home machine makes 300 products
on one line, so changeover (which is cleaning) dominates. Every concept is therefore judged first
on how many shared food-contact surfaces it has and how they are washed.

---

## 1. Shared front end (used by all four concepts)

These three elements are the same in every concept, so they are described once.

### 1.1 Own-lid dosing at a tipper dock

The storage box keeps a *dosing lid* for its whole filling cycle (fitted at ingestion, washed with
the box when it is empty). The preparation module has a **tipper dock**: a clamp frame on a
horizontal rotary axis (0-180 deg, 15 Nm, 5 kg box at 80 mm offset needs 4 Nm), standing on three
load cells, with a 150 Hz vibrator and one linear finger. Loss in weight is measured at the dock,
so nothing shared touches the food until it is in free fall.

| Lid type | For | How it doses | Accuracy (est.) |
|---|---|---|---|
| **M mesh lid** | flour, starch, sugar, salt, spices, breadcrumbs, grated cheese | Stainless mesh (2-5 mm by product) over the full opening. Cohesive powder arches on the mesh and holds when inverted. It flows only while the dock vibrates: 0.1-5 g/s by amplitude. No moving part in the food. A dust cap snaps over the mesh for storage. | +/-0.2 g (spice dock, 300 g cell), +/-2 g (bulk) |
| **I iris lid** | rice, lentils, pasta, frozen peas, nuts, small whole produce | Silicone sleeve iris (twist-to-close, as Mucon iris valves), 0-100 mm opening, turned by the dock finger. Closes gently on product without crushing. | +/-1 piece; +/-3 g for rice |
| **O open lid** (plain lid, removed) | potatoes, onions, carrots, apples, leaf heads, meat pieces, eggs in a tray | Pulse-tilt to 95-130 deg over a vibrating chute with a camera; stops on weight. Resolution is one piece. | one piece |
| **S spout lid** | oil, milk, vinegar, stock, cream, liquid egg | Duckbill silicone spout; doses by tilt angle with weight feedback; the duckbill closes drip-free when tilted back. | +/-2 g |
| **K piston box** (push-up floor, idea N5) | mince, quark, tomato paste, mustard, honey, butter, jam | Box floor is a free piston; the dock pushes it up and a wire cuts off the extruded slug. | +/-3 % |

Mains water is dosed by valve and flow meter directly into the vessel.

Weakness, stated once: four lid types and one box type add cost and 20-30 mm of height per box
in storage, and the mesh lid needs a tuned mesh per product class. Steam is kept away from
the lids by a downdraft (A) or by dosing away from the hob (B, C, D).

### 1.2 Egg opener "scribe and pull" (idea N6)

Used by all concepts. Two suction cups hold the egg at its poles, rotate it once against a carbide
scribe, then pull apart. Contents fall without touching the machine; the shell halves stay on the
cups and are carried to waste. 10 s per egg.

### 1.3 Thermal budget and wash kit

One wash kit per preparation module: 8 L sump with 2 kW heater, recirculation pump 30-40 L/min at
0.5-2 bar, detergent and rinse-aid dosing, fresh-water final rinse at 80-85 deg C, conductivity
and temperature sensors, drain pump, 70 deg C dry-air fan with filter (values from R6 section 2).

---

## 2. Concepts

### Concept A — "Fallturm": the vertical food tower

**Core idea.** One vertical process shaft of 180 mm bore runs from the tipper dock at 1700 mm down
to the cooking vessel at 800 mm; processing stages swing into the shaft like the plates of a
filter stack and the food falls through them. A stage has no floor that stores food: it is a tube,
a spinning disc under a lifting sleeve, or a cutting disc. After the meal a wash takes the
same path from the same dock, so whatever the food could reach, the water reaches too.

```
 front view, module 600 W x 600 D x 2000 H          side detail of stage L4

 2000 +------------------------------+              sleeve (lifts 100 mm)
      | fan + filter (downdraft)     |                |          |
 1950 |  +--------+                  |                |  o  o o  |  produce
      |  |box, lid|<- tipper dock    |                | o o  o   |
 1700 |  +---\/---+   on load cells  |             ===+==========+=== abrasive disc
      |      ||    shutter (iris)    |              \   |stalk |   /   dia 190, overhangs
 1600 |  +---||---+                  |               \  |motor |  /    its own seal
      |  | L4 wash/peel/spin stage   |<- swing-out    \ +------+ /     annular funnel
 1350 |  +---||---+   arm (rear post)|                 \        /      to shaft / waste
      |  | L3 cutter: hopper dia 130 |                  +--||--+
 1150 |  +---||---+  disc + grid     |                 diverter flap
      |      ||                      |
 1050 |  .---\/---.  vessel on Z-lift (400 stroke) + X-slide (250), load cell 10 kg
      |  | bowl / |  tool head from the side: scraper, roller, whisk, chopper spindle
  850 |  '--pot---'  induction hob 3 kW
  750 |------------------------------|  sloped floor 5 deg, central drain
      | sump 8 L, pump, heater, organic-waste screw press, waste bin      |
    0 +------------------------------+
```

**Kinematics and actuators (15 axes).** Tipper rotation, clamp, lid finger, vibrator (4). Shaft
shutter (1). Stage swing arms L4 and L3 on a rear post, 90 deg each (2). L4 disc drive 300 W
50-900 rpm, sleeve lift, waste diverter (3). L3 cutter drive 500 W 400 rpm, disc-stack lift for
changing among 5 discs (2). Vessel Z-lift and X-slide (2). Tool head swing with one 500 W spindle
(1 + spindle). Fluid: 6 valves, 2 pumps, 1 fan. No robot arm. A flat-item station (Buch-Wender,
idea N1) stands beside the vessel position for cutlets and Rouladen; it is not part of the shaft.

**Tool and vessel set.** L4 discs: abrasive (silicon carbide on stainless), rubber-stud, smooth
ribbed. L4 sleeves: solid, perforated (for spin drying the sleeve is coupled to the disc). L3
discs: slice 2/5/10 mm, grate 3 mm, dicing grid 10 mm and 20 mm. Tool-head tools: silicone
scraper, kneading roller, balloon whisk, chopper knife pair, masher plate. Vessels: rotating
mixing bowl 5 L (bowl rotates, tool fixed; no seal, R4 concept C), pots and pans of the cooking
module, all with the same base flange.

**Ingredient forms.**

| Form | Path |
|---|---|
| Whole produce | O lid, pulse-tilt, falls into L4 (wash, peel), sleeve lifts, falls through L3 (cut) into the raised vessel. |
| Leafy | O lid into L4 with perforated sleeve: flood 1.5 L, disc at 40 rpm, drain, spin 450 rpm 30 s (34 g at 150 mm radius), discharge by sleeve lift at 20 rpm. |
| Granular, powder | M or I lid, free fall through the open shaft (stages swung out) into the raised vessel; the stream (dia 100) does not touch the 180 mm shaft. |
| Liquid | S lid; falls through the shaft. Water by valve at vessel level. |
| Paste | K piston box; slug cut by wire, falls. |
| Raw meat | Bulk pieces (goulash, mince): O lid or K box, straight fall, stages out. Flat cuts go to the flat station by the transport gripper, never through the shaft. |
| Egg | Egg opener mounted at vessel level, outside the shaft. |
| Frozen | I lid (IQF) as granular; blocks fall into the pot and thaw there. |

**Hard operations.**

| Operation | How in A | Honest rating |
|---|---|---|
| Peel potato, carrot | L4 abrasive disc, 1.5 kg batch, 250 rpm, 1.5 L/min water, 90-120 s; peel slurry leaves under the sleeve (1.5 mm gap) to the waste diverter. Loss 12-20 %, eyes remain. | Works (commercial peeler principle). Carrots shorter than 150 mm only. |
| Peel onion | Top-and-tail at L3 with the 10 mm slicing disc (first and last slice diverted to waste by weight timing is not credible). Use idea N7 (slit and rub) in L4 with the rubber-stud disc. | Weak. Default: bought peeled or frozen diced onion. |
| Dice onion | L3 slicing disc over dicing grid, 10 mm. Finer than 5 mm: chopper spindle in the bowl, 3 pulses. | Works, irregular below 5 mm. |
| Mince herbs | Washed and spun in L4, dropped into the bowl, chopper knives at 3000 rpm in pulses. | Works; bruises soft herbs more than a knife. |
| Crack egg | Egg opener 1.2. | Works. |
| Frikadellen | Mass mixed in the rotating bowl with scraper and roller; bowl contents pushed into a K piston box; slugs of 150 g (dia 100 x 19 mm) cut off directly over the pan. | Works; patties are cylindrical discs. |
| Rouladen | Flat station: Buch-Wender N1 plus roll loop N2, seam-down braising cassette N3 instead of tying. | Outside the tower. |
| Bread a Schnitzel | Flat station N1: the tower doses flour and crumbs onto the mat by moving the mat under the shaft on the X-slide. | Works on paper. |
| Knead, roll out dough | Rotating bowl with roller and scraper, 10-20 Nm. Roll out: pressed flat in N1 (2 kN gives 0.5 bar on 200 x 200 mm: enough for shortcrust and rested yeast dough to 4 mm, not for stiff pasta dough). | Kneading good, sheeting moderate. |
| Mash | Boiled potatoes in the pot; masher plate on the tool head plunges while the pot turns; or ricer die on a K piston box. | Works. |
| Toss salad | Rotating bowl tilted 30 deg, 15 rpm, dressing from an S lid. | Works. |
| Flip steak, pancake | Not a tower function. Band spatula N4 or clamshell pan. | Outside the tower. |
| Drain pasta | Pot with a perforated insert basket lifted by the Z-lift hook; or the pot tilts against a sieve lid. | Works, standard. |

**Cleaning.** The tower interior from the shutter down to the floor (about 0.55 x 0.5 x 1.0 m,
2.3 m2 of Zone F and S) is one welded stainless wash cell. After the last drop a *wash cartridge*
(a box-format spray head) is docked where the food box was and the shutter opens. Sequence: cold
pre-rinse 3 L once-through; 6 L at 55 deg C with detergent recirculated at 35 L/min for 8 min
through (a) a rotary jet head at the dock pointing down the shaft, (b) one upward ring of 6
nozzles under each stage to hit undersides, (c) 4 wall nozzles; the L4 disc spins at 300 rpm and
the cutter disc at 400 rpm during the wash, which throws water outward over their own undersides
and the sleeve; rinse 3 L; final 3 L at 82 deg C; then 70 deg C air at 150 m3/h from the top fan
for 15 min. Water about 15 L, energy about 0.7 kWh. Water leaves through the sloped floor to the
sump; peel and solids are caught by a wedge-wire screen that a screw empties into the organic
bin. Crevice control: stages hang on arms that enter through the rear wall via rotary lip seals
*above* the stage (nothing drains onto a seal); discs sit on tapered shafts and overhang the
sealed stalk by 40 mm. Spray shadows that remain and need test: inside of the dicing grid (answer:
the disc-stack lift pushes a silicone comb through the grid, then sprays), the underside of the
shutter, the lid finger. Discs and grids not in use are stored inside the cell and are washed
with it. The flat station and the vessels go to the ware washer.

**Off-the-shelf vs custom.** Off-the-shelf: slicing and dicing discs and grids of a vegetable
cutter (Robot Coupe CL class), abrasive peeler discs (spare parts of 5 kg peelers can be cut
down), load cells, pumps, dishwasher heater and rotary jet heads, BLDC motors, induction module.
Custom: welded cell, swing arms, sleeve lift, tipper dock, lids.

**Genuinely novel.** The combination: own-lid dosing in free fall, floorless stages, a wash
cartridge docked where the food enters, and a permanent downdraft (30 m3/h, 0.3 m/s in the shaft)
that keeps steam out of the dry path and dust inside.

**Biggest weakness.** Food that must not fall or is flat (Schnitzel, Rouladen, steak, fish fillet,
pancakes) does not fit the tower at all; A is really a *bulk* machine with a separate flat
station bolted on. Second: the 2.3 m2 wash cell is wetted after every meal even if only rice was
dosed. Third: a 0.9 m fall into a pan of hot fat is not acceptable, hence the vessel lift, which
costs an axis and cycle time.

---

### Concept B — "Trommelwerk": one tilting drum, washing machine meets concrete mixer meets wok

**Core idea.** A stainless drum (dia 300 x 350 mm, a cup on a rear shaft) spins from 5 to 900 rpm
and tilts from mouth-up to mouth-down; with loose liners and one swing-in tool arm it is the
produce washer, salad spinner, abrasive peeler, tumble coater, mixer, kneader, bowl chopper and
rotating induction wok. Food enters by gravity through the mouth from the tipper dock above and
leaves by tilting the mouth down over the pot, pan or plate below. The drum washes itself like
a washing machine and then dries and disinfects itself with its own induction coil at 110 deg C.

```
 side view (depth 600)                         tilt positions (axis angle to horizontal)

 1750  [box on tipper dock]                     +60 deg  mouth up: receive, hold 5 L liquid,
          \  chute 150 wide                              chop, knead, boil
 1500      \      tool arm (swings in           +15 deg  tumble: wash, peel, coat, mix, fry
            \     through the mouth)            -10 deg  drain through mouth sieve
 1400   .----\-------/--.                       -35 deg  pour out / helix discharge
       /  drum dia 300   \==[rear bearing, seal, direct drive 30 Nm]   <- Zone N
      |   x 350 long      |   (behind the closed drum back)
       \   wall 1.5 mm   /    trunnion at the mouth-side third, tilt drive 50 Nm
 1100   '---------------'     induction coil segment under the lower third, 3 kW
            |  pour arc
  900   [pot / pan / baking dish on hob or shuttle]     drain gutter swings under the
  750   ------------------------------------------      mouth for wash water and peel
```

Critical speed of a 300 mm drum is 42.3 / sqrt(0.3) = 77 rpm. Below it the charge tumbles
(mix and coat at 20-30 rpm, wash and peel at 45-55 rpm); above it the charge sticks to the wall
(spin-dry at 450 rpm = 34 g). Usable charge: 4 L of solids, 5 L of liquid mouth-up. Drum mass
about 4.7 kg; heating it from 20 to 110 deg C takes 212 kJ, 70 s at 3 kW.

**Kinematics and actuators (9 axes).** Drum spin (washing-machine direct drive, off-the-shelf),
drum tilt, tool-arm swing, tool-arm plunge, tool spindle 500 W 300-6000 rpm, drain-gutter swing,
plus the tipper dock (3). Tools and liners are fetched from a rack by the arm itself (taper
coupling with bayonet) or by the transport gripper. Fluid: 3 valves, 1 drain pump.

**Tool and liner set.**

| Item | Form | Function |
|---|---|---|
| Bare drum | Smooth, three 15 mm lifters rolled into the wall (radius 10 mm, no add-on parts) | Mix, toss, tumble-coat, stir-fry, sweat onions, brown mince, boil, reduce |
| Helix liner | Loose stainless spiral strip, 40 mm high, 1.5 turns | Forward rotation keeps food at the back; reverse rotation screws it out of the mouth (concrete-mixer discharge, idea N8). Portioned discharge without full tilt. |
| Abrasive liner | Loose shell with silicon-carbide coat | Peeling |
| Basket liner | Perforated shell, 3 mm holes | Wash and spin; boil-in basket for pasta and potatoes |
| Mouth sieve | Perforated disc held in the mouth by the arm | Draining |
| Arm: scraper + roller | Passive, fixed against the rotating wall | Kneading (Ankarsrum principle: 600 W kneads 5 kg, R4), folding, scraping the wall clean while pouring |
| Arm: chopper knives | Two sickle blades on the spindle, entering from above the liquid line | Bowl chopper (butcher's Kutter): onions, herbs, breadcrumbs, mince from cubes, purée, emulsions |
| Arm: slicing disc head | Disc and grid on the spindle, closing the mouth, with a feed chute | Feed-through slices and dice that fall into the drum |
| Arm: whisk, masher, spray lance | | Whipping, mash, washing |

Liners are loose ware (no permanent gap between liner and drum); after use they are tipped out
like food and go to the ware washer, or stay in for the drum wash and are removed before drying.

**Ingredient forms.** All forms enter through the mouth from the tipper dock chute (M, I, O, S, K
lids as in 1.1). The drum is mouth-up and not over the hob while dosing, so lids see no steam.
Frozen blocks are tumbled at 60 deg C wall temperature until free. Raw meat in pieces is
tumbled (browning, dusting with flour, marinating: tumble marination is factory practice). Flat
raw meat does not go into the drum. Out-transfer is always tilt-pour with the scraper on the
wall: a rotating wall under a fixed scraper is wiped completely every revolution, so residue
should be below 2 % even for mince mass and dough (to be measured).

**Hard operations.**

| Operation | How in B | Honest rating |
|---|---|---|
| Peel potato, carrot | Abrasive liner, +15 deg, 50 rpm, 1 L/min spray from the lance, 2-3 min for 1.5 kg; slurry pours into the gutter continuously. Option: thermal-shock peel N10 to cut the loss. | Works. Drum peelers are slower but gentler than disc peelers and take long carrots (up to 300 mm lengthwise). |
| Peel onion | Idea N7: the slicing head tops and tails, a depth-stopped blade slits the skin, then 60 s tumble with wet rubber-stud liner. | Medium; one outer layer is lost. Fallback: bought peeled. |
| Dice onion | Slicing head with 10 mm grid into the drum; fine chop with the Kutter knives, drum turning at 10 rpm so that the knives see all of the charge. | Works. The bowl chopper is the one factory machine that chops 200 g of onion evenly because the bowl brings the food to the knife. |
| Mince herbs | Wash and spin in the basket liner, then Kutter knives, 5 s. | Works. |
| Crack egg | Egg opener over the mouth. | Works. |
| Frikadellen | Mix the mass with scraper and roller at 40 rpm (2 min). Forming: reverse-helix discharge pushes a rope out of the mouth, a wire on the arm cuts 150 g portions by weight loss of the drum (drum on load cells), portions drop into the pan; the pan-side press plate flattens them. Alternative: rounder cup N11. | Medium. Portion accuracy +/-10 % is plausible, shape is rustic. |
| Rouladen | Not in the drum. Flat station N1 + N2 + N3. | Outside. |
| Bread a Schnitzel | Flat station N1. The drum only makes the crumbs and whisks the egg. Tumble-breading works for nuggets, cubes and fish pieces, not for cutlets of 250 x 150 mm in a 300 mm drum. | Outside for cutlets. |
| Knead, roll out dough | Knead as above, 1.5 kg at 20 Nm. Proof in the drum at 30 deg C (coil at low power, drum turned 1 rev/min for even heat). Sheet: flat station press, or roller arm against the drum wall to form a band 300 wide x 940 long x 4 mm on the wall, peeled off by the scraper (as a drum sheeter; needs flour dusting; speculative). | Kneading good; sheeting speculative. |
| Mash | Boil potatoes in the basket liner, drain through the mouth sieve, masher tool with the drum at 20 rpm, add hot milk and butter. | Works; no blade, so not gluey. |
| Toss salad | Bare drum, +15 deg, 12 rpm, 6 turns, dressing misted through the lance. | Excellent; this is how bagged salad is dressed industrially. |
| Flip steak, pancake | Not in the drum. N4 band spatula or clamshell pan. Small items (diced potato, Geschnetzeltes, meatballs) are turned by tumbling. | Outside for flat items. |
| Drain pasta | Mouth sieve, tilt to -10 deg, water runs into the gutter; 30 s. | Works, simplest of all concepts. |

**Cleaning.** Wetted: drum inside, mouth rim, arm and tool, chute, gutter. Sequence: scraper wipes
the wall during the last pour; 1.5 L cold water from the lance, tumble with reversal 30 s,
pour to the gutter; 1.5 L with detergent, heated by the drum's own coil to 55 deg C in about
2 min, tumble and lance jet (3 bar, 2.4 L/min through a 2 mm nozzle, R6) for 3 min, the arm tool
spinning in the liquor; pour; two rinses of 1 L; pour at -35 deg and spin at 450 rpm for
10 s to throw off the film; then heat the empty drum to 110 deg C for 60 s. Total about 6 L of
water and 0.25 kWh, 9 min. Thermal disinfection and drying come from the wall itself, so there is
no wet plastic and no hot-air dryer for the drum. Spray shadows: none inside a smooth rotating
cup; the rolled-in lifters have 10 mm radii. Critical places: the outer mouth rim and the first
30 mm of the outside wall (pouring dribble) get a fixed fan nozzle and pass through the gutter
spray; the chute is a loose stainless part changed per meal and sent to the ware washer; the arm
is washed up to a drip collar and its spindle seal sits above the collar, outside the drum. The
rear shaft seal never sees food because the drum back is closed. The enclosure around the drum is
Zone S and gets a weekly spray-down.

**Off-the-shelf vs custom.** Off-the-shelf: washing-machine direct-drive motor and bearing unit,
induction generator with a custom coil, cutter discs, Kutter blades, load cells. Custom: the drum
(spun or deep-drawn ferritic-clad stainless), trunnion, arm, liners.

**Genuinely novel.** A food drum that spans the full speed range from tumble to centrifuge,
combined with a bowl-chopper spindle entering through the mouth and with induction self-drying.
I know of rotating woks (Botinkit, Spyce), peeling drums and salad spinners, but not of one
vessel that is all three and its own disinfector.

**Biggest weakness.** One drum is a serial bottleneck: a meal with four components needs the drum
four to eight times, with at least a rinse in between (2-3 min each). A second, smaller drum
(dia 200) on the same trunnion design relieves this at the cost of width. And, as in A, flat items
need the separate flat station. The drum spinning at 450 rpm with an unbalanced 1.5 kg charge
needs washing-machine style balancing (ramp with redistribution) or the cabinet shakes.

---

### Concept C — "Kolbenstrang": food as a plug in a pigged tube

**Core idea.** Food is loaded into a straight stainless cartridge tube (110 mm bore x 250 mm,
2.3 L) that contains a free piston, and a press pushes the plug through an exchangeable die
clamped to the end. Every shape-giving operation becomes "push through a die and cut off":
slices, sticks, dice, mash, Spätzle, patties, dumplings, dough ribbons, piped fillings, metered
paste. The piston wipes the bore on every stroke (pigging), so transfer residue is close to zero,
and the soiled parts are an open tube, a disc and a plate: the three easiest shapes to wash.

```
 front view, 450 W x 600 D, press frame closed yoke for 10 kN

 1800  [box on tipper dock] -> funnel -> open cartridge at the loading position
 1600  +==== yoke ====+
       |  electric cylinder 10 kN, 300 stroke, 25-50 mm/s (250-500 W)
 1500  |      |ram|   |
       |   +--+---+--+                 cartridge carousel (4 places):
       |   | piston  |  <- free piston, two wiper lips     load - press - mate - park
       |   | plug    |  cartridge 110 bore x 250
 1200  |   | (food)  |
       |   +=========+  die turret (6 dies dia 110): open ring, slicing frame, 12 mm grid,
 1150  |   ---wire---   ricer 3 mm, Spaetzle 8 mm, slot 100 x 4, nozzle dia 15
       +==============+ cut-off: rotating wire / blade under the die, timed to ram travel
 1000       |  falls
  900  [pot / pan / Buch-Wender mat / baking dish]
```

**Kinematics and actuators (8 axes).** Press ram, cartridge carousel, die turret, cut-off drive,
die clamp, plus the tipper dock (3). For kneading, two cartridges are clamped mouth to mouth
through an orifice plate and the ram works against a second, smaller counter-cylinder (1 more).

**Forces.** Die pressure at 10 kN on 95 cm2 is 10.5 bar. Dicing grid: engaged edge length of a
12 mm grid over a 70 mm potato is about 2 x 3850 / 12 = 640 mm; at 2-5 N/mm times 1.5 for
friction (R4 1.1) that is 1.9-4.8 kN. A full 110 mm plug of raw carrot sticks on the same grid
would need up to 12 kN, so hard produce is loaded in a single layer of items and cut one item per
stroke section, or pre-sliced to 12 mm slabs by the cut-off blade on an open ring first (slab,
then grid: the factory dicer sequence). Ricer: about 1 kN. Patty: 150 g is a 15.3 mm stroke; a
stroke error of 0.3 mm is 2 %.

**Tool and vessel set.** 4 cartridges, 4 pistons, 7 dies, 2 cut-off tools (wire, blade), one
orifice plate, one whisk lid (a top-driven whisk that sits on a cartridge used as a beaker,
because a piston cannot whip). The cartridge is the "bucket" of the brief: it stores, meters,
transports and empties.

**Ingredient forms.**

| Form | Path |
|---|---|
| Whole produce | O lid, into the cartridge through the funnel (one to four items), pressed through slicing frame or grid. Washing and peeling are *not* solved by this concept: it needs a wash/peel stage from A or B, or skin-on cooking and the ricer, which retains skins (R4 2.2). |
| Leafy | Cut to ribbons by the blade cut-off at the open ring (chiffonade); washing elsewhere. |
| Granular, powder, liquid | Do not need the piston; dosed from their lids directly into the vessel. The cartridge with a closed die is used as a weigh beaker. |
| Paste, sticky | The natural domain: cartridge as metering syringe, +/-2 %. K piston boxes dock to the press directly. |
| Raw meat | Mince: dosed, mixed and formed as plugs. Cubes: crust-frozen at -3 deg C (idea N12), then grid. Flat cuts: flat station. |
| Egg | Egg opener into a cartridge used as beaker. |
| Frozen | Spinach blocks and similar are pushed through a coarse grid while frozen: 5 kN, feasible. |

**Hard operations.**

| Operation | How in C | Honest rating |
|---|---|---|
| Peel potato, carrot, onion | Not solved. Skin-on plus ricer for mash; otherwise borrow the L4 stage of A. | Gap. |
| Dice onion | Peeled onion, root end down, through the 12 mm grid with the cut-off blade timed every 6 mm of travel: true dice of 12 x 12 x 6. About 1.5 kN. | Good; the most regular dice of the four concepts. |
| Mince herbs | Pack the herbs, extrude through the open ring 1 mm per step with the blade cutting at each step: a guillotine chiffonade, 1-2 mm. | Good and gentle (a cut, not a bash). |
| Crack egg | Egg opener. | Works. |
| Frikadellen | Mince mass in the cartridge, open ring, wire cut every 15-20 mm: discs of 150-200 g +/-3 % drop flat into the pan. The mass is mixed by ten push-pull passes through a 40 mm orifice. | Very good: this is a factory former. |
| Rouladen | The nozzle die pipes a metered stripe of mustard and filling onto the meat slice lying on the flat station; rolling by N2. | Filling good; rolling outside. |
| Bread a Schnitzel | Outside (N1). | Outside. |
| Knead, roll out dough | Reciprocating extrusion between two cartridges through a 30 mm orifice: 8 kN gives 8.4 bar, 840 J per litre pass; 30 kJ/kg (about 100 W for 5 min, R4 6.2) needs about 36 passes of 5 s = 3 min. Sheet: extrude through the 100 x 4 mm slot onto a moving mat, ribbons laid side by side and pressed. | Kneading plausible but unproven for gluten development (extrusion aligns rather than folds); sheet from ribbons is second-rate. |
| Mash | Boiled potatoes, skins on, into the cartridge, ricer die, straight into the pot with butter and milk. Skins stay on the die and are pushed out backwards by reversing the piston. | Excellent: the ricer is the right tool and skins are retained. |
| Toss salad | Not a piston task; rotating bowl. | Outside. |
| Flip, drain | Outside (N4; sieve basket). | Outside. |

Additional things it does uniquely well: Spätzle directly into simmering water; Klöße and gnocchi
portions; piped mashed potato and duchesse; cake batter and pancake batter metered to +/-2 %;
butter and quark metering; pressing thawed spinach or grated potato dry (UO-36) against a fine
die at 5 bar; citrus pressing against a cone die.

**Cleaning.** After the stroke the piston stands flush with the tube end and has wiped the bore;
the wire wipes the die face. Cartridge, piston and die are then released into the ware washer
as three separate open parts (tube: water runs straight through; piston: a disc with two lips and
no cavity; die: a plate). Grids are the known problem of every dicer: a silicone *push-out block*
with the grid's negative is pressed through on the last stroke (factory practice), then the grid
is sprayed from both sides. The ram never touches food (it pushes the dry side of the piston).
Frame and yoke are Zone S, reached by two fixed nozzles. The only path that needs in-place
cleaning is the loading funnel (loose part, to the ware washer).

**Off-the-shelf vs custom.** Off-the-shelf: electric cylinder 10 kN (several makers), stainless
tube 114.3 x 2 (dairy tube, electropolished), dicing grids and ricer plates from push dicers and
commercial ricers, load cells. Custom: pistons (moulded silicone lip on a stainless disc), die
turret, clamp.

**Genuinely novel.** Pigging as the general transfer principle of a kitchen; kneading by
reciprocating extrusion without any rotating tool or seal; one press replacing dicer, ricer,
former, depositor, Spätzle press, juicer and metering pump.

**Biggest weakness.** It is half a kitchen. It does not wash, peel, toss, whip, coat or handle
flat items, and hard produce needs up to 10 kN, which means a heavy closed frame and a safety
case. It is best seen as the *forming and metering station* inside another concept.

---

### Concept D — "Flachband": a washable belt as the universal work surface

**Core idea.** A 300 mm wide, 800 mm long monolithic food-grade belt (homogeneous TPU,
tooth-driven, no fabric) is the machine's cutting board: items lie flat on it and are carried back
and forth under a row of fixed stations, so that a process line is folded in time instead of
space. Flat and formed food (Schnitzel, Rouladen, steak, fish, dough, patties, slabs of vegetable)
is handled the way factories handle it: dust, curtain-coat, press, slit, cross-cut, roll up,
and lay down gently into the pan with a retracting nose. The belt is washed continuously on its
return strand in a closed wash box, as in a factory.

```
 front view, 900 W x 600 D x 550 H, belt top at 1150 mm

  box dock      sifter     curtain     press/sheeting    gang     guillotine   curl belt
  + chute       (flour,    nozzle      roller dia 80     knives   cross-cut    (runs
     |          crumbs)    (egg, oil)  gap 2-25 mm       10 mm    wire/blade   backwards)
     v            v           v            O             ||||        |          ___
 ==========================================================================  <- belt 300 wide
 (o) slider bed, stainless rails, belt lifts off for washing              (o)--> retracting
  |________________ return strand ________________________________________|      nose, 150
        [ wash box 300 x 150 x 120: scraper, 2 spray bars, air knife ]           stroke
                                                                         pan / pot / dish
  drip tray, 5 deg slope, to sump                                        at 900-1000 mm
```

Every station can be lifted clear (20 mm) so that an item can pass under it untouched. The belt
reverses; position is known from the drive encoder and a top camera.

**Kinematics and actuators (12 axes).** Belt drive (60 W, 0.01-0.3 m/s), nose retract, roller
gap, roller drive, gang-knife lift, guillotine, curl-belt drive and lift (2), sifter vibrator,
station lifts grouped on one camshaft (1), plus tipper dock (3). A rotary turntable segment to
turn items by 90 deg is avoided: strips come from the gang knives (along the belt) and dice from
the guillotine (across), which is the factory belt-dicer sequence.

**Tool and vessel set.** The belt; sifter cassette (takes flour or crumbs from an M lid above);
curtain trough with slot nozzle (egg wash, oil, marinade; fed from an S lid through a 200 mm
gravity drop, no pump); press roller with scraper; gang of 14 circular knives at 20 mm pitch,
shifted by 10 mm for a second pass; guillotine blade 300 mm; curl belt; nose. Vessels are the
cooking module's pots and pans and a rotating mixing bowl for wet mixing (belts do not mix).

**Ingredient forms.**

| Form | Path |
|---|---|
| Whole produce | Round items roll on a belt. They are first cut to slabs by a feed-through slicing disc at the dock chute (one extra drive), then the belt makes strips and dice. Washing and peeling: a roller bed (idea N13) in place of the first 300 mm of belt, or borrowed from A/B. |
| Leafy | Spread on the belt, guillotine at 2-5 mm steps: chiffonade and chopped herbs with a true knife cut. |
| Granular, powder | Bypass chute at the nose end, straight into the vessel; or through the sifter onto items. |
| Liquid, paste | Curtain trough or nozzle onto items; bulk liquid bypasses. Paste: K piston box extrudes a stripe across the belt (mustard on Rouladen, tomato sauce on pizza). |
| Raw meat | Home ground: slices and cutlets lie flat, are flattened, coated, filled, rolled, strip-cut (Geschnetzeltes) and cubed (goulash), then laid into the pan. |
| Egg | Egg opener over the mixing bowl (egg wash) or directly over the pan. |
| Frozen | Frozen fish fillets and cutlets ride the belt; IQF goods bypass. |

**Hard operations.**

| Operation | How in D | Honest rating |
|---|---|---|
| Peel potato, carrot | Roller bed N13: six abrasive rollers dia 40, 300 long, in a trough form, counter-rotating with water spray; carrots and potatoes roll and travel along it. 1 kg in 2-3 min. | Works in factories (roller peelers); good on carrots, which drums and discs break. Adds a module. |
| Peel onion | N7 on the roller bed with rubber rollers. | Medium. |
| Dice onion | Peeled onion sliced to 5 mm slabs at the chute disc, slabs pass gang knives and guillotine: 5 x 10 x 5 mm. Slabs of onion fall apart into rings, so dice are irregular. | Medium. |
| Mince herbs | Guillotine in 1 mm steps, belt reversed and second pass after the curl belt has turned the pile. | Good cut quality, slow (60 s). |
| Crack egg | Egg opener. | Works. |
| Frikadellen | K piston box deposits 150 g slugs on the belt; the press roller at 18 mm gap flattens them; the nose lays them into the pan. | Good. |
| Rouladen | Slice on belt; press roller at 5 mm flattens it (1.5 kN line force); piston box lays a mustard stripe, the curtain/chute drops bacon, onion and gherkin strips (cut on the same belt beforehand and parked in a cup); the curl belt lowers onto the leading edge and runs backwards at belt speed: the slice rolls up like a croissant on a curling mat. The roll is pushed seam-down into the braising cassette N3. No tying. | The most credible Rouladen method I can find. The filling must not be pushed ahead of the roll: needs a 20 mm bare leading edge and test. |
| Bread a Schnitzel | Factory flatbed line in three passes: sifter dusts flour, belt reverses, curl belt flips the cutlet, dust again; egg curtain (25 g), flip, curtain; crumb bed laid by the sifter (40 g), cutlet driven onto it, crumbs sifted on top, press roller at 30 N. Excess flour and crumb fall off the nose into a waste tray, egg drips through a slotted section into the drip tray. | Good coverage expected (>95 %); wasteful in crumbs (about 30 % to waste because it touched raw meat). |
| Knead, roll out dough | Knead in the rotating bowl. Sheet on the belt: roller gap from 20 to 3 mm in 5 reversing passes, flour from the sifter; 300 mm wide sheet of any length; guillotine and gang knives cut noodles, squares for Maultaschen, biscuits strips; curl belt rolls Strudel and cinnamon rolls. | Excellent: a dough sheeter is a belt machine. |
| Mash | Not a belt task (pot and masher). | Outside. |
| Toss salad | Not a belt task (rotating bowl). | Outside. |
| Flip steak, pancake | The nose is an 8 mm nose bar: it crawls under the item in the pan as the belt runs (band spatula N4), lifts it, and lays it back after the curl belt has turned it over. Pancake dia 240 mm on a 300 mm belt: marginal but possible with a non-stick belt rated 120 deg C contact for seconds; the pancake surface is below 100 deg C on the raw side. | Medium. Hot fat on the belt is the concern: the wash box has to cope with it. |
| Drain pasta | Not a belt task. | Outside. |

**Cleaning.** Wetted: belt both sides, stations above, slider rails, drip tray. The scraper at
the nose removes solids into the waste tray after each item. During and after use the return
strand runs through the wash box: upper and lower spray bars (6 flat-fan nozzles each, together
8 L/min at 2 bar, recirculated from the sump at 55 deg C), a silicone scraper, then an air knife;
one belt revolution is 1.9 m, 19 s at 0.1 m/s, so a 3 min wash is 9 passes; final pass with
82 deg C fresh water, then warm air. Between a raw-meat step and the next item the belt gets a
full wash including the hot pass (4 min). Homogeneous tooth-driven belts are made for this
(no fabric edge, no hinge pins). The stations are the problem: roller, gang knives, guillotine,
sifter and curl belt hang above food and are soiled from below. Answer: all stations sit on one
lift-out bridge with two spray bars aimed upward from between the strands (the belt is slackened
and pushed aside by lifters), the knives rotate during the wash, and the sifter cassette and
curtain trough are loose ware. This is the largest wetted area of the four concepts (about
1.4 m2) and the least certain to pass a riboflavin test.

**Off-the-shelf vs custom.** Off-the-shelf: belt and sprockets (Volta, Habasit Cleandrive,
Intralox ThermoDrive class), drum motor, circular knives, flat-fan nozzles. Custom: station
bridge, curl belt, nose.

**Genuinely novel.** Folding a breading line, a sheeter, a belt dicer and a croissant curler into
one reversible 800 mm belt; rolling Rouladen with a curling belt; the nose as powered spatula.

**Biggest weakness.** A belt cannot contain liquids or mix, cannot wash leaves and cannot hold
round produce; it covers the flat and formed third of cooking superbly and the rest not at all.
It also puts many mechanisms above food (HYG-004), each needing its own drip-proof design.

---

## 3. Cross-comparison

| | A Fallturm | B Trommelwerk | C Kolbenstrang | D Flachband |
|---|---|---|---|---|
| Canonical food shape | falling bulk | tumbling bulk, liquid | plug | sheet |
| Footprint W x D x H (mm) | 600 x 600 x 2000 | 600 x 600 x 900 (+ dock) | 450 x 600 x 900 | 900 x 600 x 550 |
| Motion axes incl. dock | 15 | 9 | 8-9 | 12 |
| Shared Zone F + S wetted per meal (m2) | 2.3 | 0.5 | 0.15 + ware | 1.4 |
| Wash water / energy per cycle | 15 L / 0.7 kWh | 6 L / 0.25 kWh | via ware washer | 10 L / 0.5 kWh |
| Wash, spin, peel | yes | yes | no | roller bed add-on |
| Regular slices and dice | yes | yes (disc head) | best | slabs only |
| Fine chop | bowl chopper | bowl chopper, best | guillotine steps | guillotine steps |
| Mix, knead, whip | rotating bowl | yes, in the drum | knead only, unproven | no |
| Form, meter pastes | via piston box | rustic | best | good |
| Flat items, coating, rolling | no | no | no | best |
| Cooks as well | no | yes (tumble dishes) | no | no |
| Needs a robot arm | no | no | no | no |

No single concept covers 95 % of the unit operations alone. B covers the most (my count against
requirements section 5.3, preparation operations UO-01 to UO-49: about 30 of 38 alone, A about
27, D about 16, C about 14). The missing ones are complementary: B lacks exactly what D and C
do best.

### 3.1 Check against the meal corpus (`research/02-meal-corpus.md`)

The corpus ranks the hard operations by the share of the 248 meals they block. Rating per
concept: ++ native strength, + credible, o weak or adapted method, - not done by this concept.
"Buy" = a level-1 purchase removes the operation (corpus 4.7). The ratings are my judgement from
section 2, not measurements.

| Code | Operation | Meals | Buy? | A | B | C | D | Best mechanism in this document |
|---|---|---|---|---|---|---|---|---|
| PLA | peel onion, garlic | 52.0 % | yes | o | o | - | o | N7 slit and rub; every concept is weak here. Corpus advice (buy peeled or frozen first, peeler as upgrade) is right. |
| COR | core, deseed, hull | 20.2 % | yes | - | o | + | - | Not covered in section 2. Added: N20 corer-wedger die (apple, pear) on the press; N21 halve and tumble-rinse (pepper). |
| FLP | flip, turn | 12.9 % | **no** | - | - | - | + | N1 clamshell flip (two-sided contact, which the corpus names as the alternative) and N4 band spatula. Pieces (diced potato, strips, meatballs) turn by tumbling in B. |
| TRE | trim ends, stems, roots | 12.5 % | yes | - | - | o | + | D: items lie lengthwise, camera finds the ends, guillotine cuts. Added: N22 snipper drum for beans. |
| PLS / PLH | peel soft / hard produce | 10.5 / 7.3 % | yes | + | + | - | + | Abrasive disc, drum or roller bed; N10 thermal shock for tomato and peach. Knobbly celeriac and ginger: high loss (30 %). |
| ASM | assemble, build, layer | 6.9 % | **no** | o | o | + | ++ | Not covered in section 2. Added: N23 miniature lasagne line (dish moves under fixed depositors). |
| SEP | separate egg | 6.9 % | yes | + | + | + | + | N6 with a slotted cup under it. |
| STU | stuff, fill | 6.5 % | level 2 | - | o | ++ | + | Nozzle die on the piston (rigid cavities: peppers, cannelloni). Flat pockets not solved. |
| CAR | carve cooked meat | 4.8 % | **no** | - | - | o | ++ | D: roast rides the belt in steps, guillotine with draw cut, 120 mm clearance needed (roast 250 x 150 x 120). C fits only roasts under 110 mm. Bone-in poultry: not solved by anything here. |
| UNM | unmould, turn out | 4.4 % | **no** | - | - | ++ | o | N5 push-up floor in every mould; added N24 induction release pulse; N1 inverts the mould onto the dish. |
| WRP / RLT | wrap, roll (and tie) | 4.0 / 1.6 % | level 2 | - | - | - | ++ | Curl belt or N2 roll loop, N3 cassette instead of tying. |
| STR | strip, pluck | 3.6 % | yes | - | - | - | - | Not solved. Buy. |
| FRM / SHD | hand-form, shape dough | 2.8 / 2.4 % | level 2 | o | o | ++ | + | Piston former, N11 rounder cup, sheeter and curl belt. Braids and pretzels: not solved. |
| PLE | peel boiled egg | 2.8 % | yes | o | + | - | - | B: crack by tumbling at 60 rpm, then rubber-stud liner with water, 30 s (factory egg peelers work this way). |
| SCO | score, slash | 2.8 % | **no** | - | - | - | ++ | D: gang knives or guillotine with a depth stop of 3-5 mm. |
| BRD | bread, coat | 2.0 % | level 2 | - | o | - | ++ | Flatbed passes on the belt, or N1. |

Conclusions from the check:

1. **The flat, formed and finished-item domain is larger than I assumed.** Flipping, carving,
   scoring, assembling and unmoulding have no purchase workaround and their union blocks 29 % of
   the meals; the shaping cluster adds 15 %. Section 5 set a threshold of "about a quarter of the
   meals" for promoting D from an option to a fixed part. The corpus is above it.
2. **Concept B alone is weaker than I rated it.** Of the six no-workaround operations the drum
   does none. Its strength is the foundation tier (dose, wash, cut, mix, knead, heat), which is
   the precondition for any coverage claim (61 % with level-1 purchase), and peeling, which the
   corpus says to buy away first. B remains the best *bulk* machine, not the best machine.
3. **Coring and deseeding (20 %)** was missing entirely. It is mainly apple, pepper and tomato.
   The press with a corer-wedger die is the factory answer for apple and pear; peppers are
   unsolved beyond N21; frozen pepper strips and canned tomato are the corpus workaround.
4. **Vessel sizes for six persons.** The corpus asks for a 9 L boil pot, 8-10 L mixing volume and
   28 and 36 cm pans. The B drum (24.7 L gross) holds 18 L when tilted mouth-up at 60 deg
   (volume = pi r2 (L - D tan 30 deg / 2)), so 9 L of boiling water or 10 L of mixing volume fit;
   the "5 L" in section 2 was conservative. The A mixing bowl must grow from 5 L to 10 L (dia 280 x
   200), which still fits the vessel position. The C cartridge (2.3 L) takes 1.6 kg of dough or
   1 kg of mince mass but not a salad. The D belt (300 mm) and the band spatula (200 mm) reach
   into a 36 cm pan; a 28 cm pan takes one pancake of 240 mm, so six persons means many flip
   cycles (about 12 pancakes at 40 s handling each).
5. **Minimum quantities.** None of the large vessels can whip one egg white (30 mL) or make
   100 g of dough. A small top-driven whisk beaker (the C whisk lid on a 110 mm cartridge) is
   needed in every concept.
6. **Still unsolved by everything in this document:** stripping and plucking (kale, thyme
   leaves), carving bone-in poultry, flat pocket stuffing (cordon bleu), braiding, skewering,
   meat trimming. All but poultry carving have a purchase workaround in the corpus.

---

## 4. Standalone sub-mechanism ideas

Feasibility: H = standard engineering, M = plausible but needs a test, L = speculative.

**N1 Buch-Wender (book flipper).** Two flat leaves of 300 x 220 mm, each a stainless plate with a
clipped-on silicone-coated sheet, joined by a hinge like a book, each leaf driven 0-180 deg, with
a 2 kN closing force. Closing the book and re-opening the other side turns whatever lay on
leaf 1 onto leaf 2, upside down. One mechanism does: flip a cutlet; bread both sides at once
(crumbs on both leaves, close, press at 50 N); flatten (close at 2 kN); press dough to a sheet;
press patties; and with two pans instead of leaves, flip a pancake or a steak (clamshell flip).
Leaves tilt to 90 deg to slide the item into the pan and to drain in the washer. Feasibility H.

**N2 Roll loop (cigarette-roller principle).** A slack loop of thin belt or silicone sheet hangs
between two rollers 60 mm apart. The filled meat slice is fed into the loop; the rollers close to
10 mm and turn the same way, so the loop rolls the slice on itself into a tight cylinder of
45-60 mm. This rolls with containment all round, so the filling cannot escape forward as it can
on a flat mat. Also for cabbage rolls, Strudel, sushi. Feasibility M (slice thickness and
stickiness vary).

**N3 Seam-down braising cassette instead of tying.** Rouladen are not tied, pinned or netted. They
are pushed seam-down into a stainless rack with dividers at 60 mm pitch (or into stainless
sleeves of 55 mm bore), browned in the rack under a top grill or in the oven at 230 deg C and
braised in it. Home cooks do this in a tight casserole. The rack is plain sheet metal, washed as
ware. Removes UO-48 entirely. Feasibility H; browning is less even than in a pan (adapted method).

**N4 Band spatula (powered nose).** A spatula whose blade is a thin belt running around an 8 mm
nose bar, 200 mm wide. Pushed under a steak while the belt runs at the advance speed, it crawls
under the item without pushing it, so nothing is shoved across the pan and no crust tears. Turning
the spatula 180 deg about its long axis 40 mm above the pan flips the item. Laying down works in
reverse (retracting-nose conveyor, standard in bakeries). Belt: PTFE-glass, rated 260 deg C.
Feasibility M-H; the belt and nose must be washed after every use (loose cassette to the washer).

**N5 Push-up floor ("the vessel floor is a pig").** Any straight-walled vessel or box gets a
loose floor disc with a wiper lip, as in a push-pop or a springform tin. Pushing the floor up
empties sticky contents (mince, dough, mash, quark) to below 1 % residue and meters them by
stroke; in the washer the floor drops out and both parts are simple shapes. Works for round tubes
and, with a moulded silicone lip, for GN boxes with their 10-15 mm corner radii. Feasibility H for
round, M for rectangular (lip sealing in corners, wall draft angle of GN boxes must be zero).

**N6 Egg opener "scribe and pull".** Two silicone suction cups (dia 25) grip the egg at both
poles, rotate it one turn against a spring-loaded carbide scribe (as a glass-tube cutter, 1-2 N),
then pull apart with a slight twist. The crack follows the scribed equator, so few fragments form;
contents drop straight into the vessel or a slotted separator cup; the shell halves remain on the
cups and are dropped into the waste. Only the cups touch the (dirty) shell outside, nothing
touches the contents. 10 s per egg. Feasibility M: shell thickness varies from 0.3 to 0.4 mm and
brown eggs are tougher; needs the scribe force tuned, and a camera check for fragments remains.

**N7 Onion skinning by slit and rub.** Top and tail by two cuts (6 mm each), one meridian slit
2 mm deep by a depth-stopped blade while the onion is held at the cut faces, then 40-60 s in a
wet tumbler with rubber studs or under two tangential water jets at 3 bar: the slit dry skins and
the first fleshy layer unwrap and leave with the water. Loss 10-15 %. Factories do this with
compressed air; water replaces the compressor and the dust. Feasibility M.

**N8 Reversing-helix discharge.** A drum with a low internal spiral keeps its charge in when
turning one way and screws it out of the mouth when turning the other way, without a door and
without full tilting, and in controlled portions (about 80 mL per revolution for a 40 mm
flight). Used for portioned discharge onto plates (four equal portions by weight) as well as
for emptying. Feasibility H (concrete mixer, continuous blancher).

**N9 Recipe water as chase.** Almost every cooked dish needs water, stock, milk or wine. Dose that
liquid *last and through the soiled path* (cutter, chute, mixing bowl, piston tube): it carries
the remaining 1-3 % of food into the pot, which improves yield and dosing accuracy and turns a
dried-on soil into a pre-rinsed surface. The control software orders the dosing sequence
accordingly. Costs nothing. Feasibility H.

**N10 Thermal-shock peel in the induction drum.** Before abrasion, heat the dry drum wall to
180 deg C, drop in the wet potatoes or tomatoes and tumble 30-45 s, then quench with 0.3 L of cold
water: the outer 0.5 mm is cooked and loosened, as in a factory steam peeler but without a
pressure vessel. Then 30 s with rubber studs instead of 120 s with carborundum. Expected peel loss
6-10 % instead of 12-20 %, smoother surface. Tomatoes and peaches skin the same way. Feasibility
M; scorching of the skin must not taint the flesh.

**N11 Orbiting rounder cup.** Bakeries round dough pieces under a cup that orbits on a plate
(20 mm orbit, 3 s). A stainless cup of 70 mm bore with a wet or oiled inner wall, orbiting over a
wetted plate, rounds a 60-150 g portion of dumpling dough or mince mass into a ball; a 40 %
squash afterwards makes a Frikadelle with closed, rounded edges that do not crack in the pan.
Feasibility H for dough and Klöße, M for mince (sticks unless the surfaces are wet and cold).

**N12 Crust-freeze before cutting meat.** The machine owns a freezer. Temper raw meat to -3 deg C
at the surface (20-40 min in the freezer airlock) before slicing, cubing or strip-cutting. It then
behaves like a firm solid: clean cuts, no smearing, 3-5 times higher force (no issue for a press
or disc), far less residue on blades and surfaces. Standard in meat plants before dicing and
bacon slicing. Feasibility H; adds planning time, the scheduler has to start early.

**N13 Roller-bed peeler and washer.** Six to eight parallel rollers of 40 mm diameter in a
shallow trough, all turning the same way at 300 rpm, with water spray. Produce lies in the
valleys, spins, and migrates along the bed if it is tilted 3 deg. Abrasive rollers peel, brush
rollers wash, rubber rollers skin onions. Long carrots, cucumbers and asparagus are peeled along
their whole length, which a disc peeler cannot do. The rollers clean each other. Feasibility H;
eight shaft seals on one side are the price (cantilevered rollers, seals behind a splash wall).

**N14 Mains-water hydraulics.** The brief guarantees 2.2-5 bar. A rolling-diaphragm cylinder of
160 mm bore gives 4.4 kN at 2.2 bar (10 kN at 5 bar) with a solenoid valve as the only moving
electrical part, is silent and is inherently wash-down proof. A 200 mm stroke uses 4 L, which is
then used as the pre-rinse water. Uses: press for dicing grids, ricer, Buch-Wender closing force,
cartridge ram. Feasibility M: force depends on the house pressure (a regulator set to 2 bar makes
it constant), and EN 1717 requires backflow protection (the cylinder water is on the non-potable
side of an air gap or a type BA device only if it never returns to food use; here it goes to
rinse and drain).

**N15 Induction flash-dry and self-disinfection of steel ware.** Instead of 15-20 min of hot air,
pass magnetic stainless ware (pots, drums, tubes, plates, discs) through or over an induction
coil after the final rinse: a 300 g part needs 13.5 kJ to reach 110 deg C plus 11 kJ to evaporate
5 g of water, 12 s at 2 kW. The surface is dry and thermally disinfected far beyond A0 = 60
(HYG-021, HYG-024) without any detergent-side uncertainty. Feasibility H for simple rotational
shapes of ferritic or clad steel; uneven for thin edges and complex parts (knife edges must stay
below tempering temperature, so not for blades above 150 deg C).

**N16 Downdraft shaft and steam lock.** Wherever dry goods are dosed above a vessel, run a
filtered downward air flow of 0.3 m/s through the dosing opening and extract at vessel level
(30 m3/h for a 180 mm shaft against 1.5 L/s of steam from a 2 kW boil, R4 9.3). Steam cannot rise
into lids, powder dust is drawn down into the extraction and its grease/steam condenser. This
lifts R4's rule "never dose spices above the pot". Feasibility H; the extracted air must be
condensed and filtered anyway.

**N17 Vibration-gated mesh (the valve with no moving part).** Cohesive powders bridge over holes
a few millimetres wide; the bridge collapses only under vibration. A mesh therefore is a valve:
closed at rest, open and metering while vibrated, and with nothing sliding in the powder. Mesh by
product: 2 mm for flour and ground spice, 3 mm for sugar and salt (these free-flowing goods need
a shallower cone and a slower ramp, or the I lid), 5 mm for breadcrumbs. Used in pharmaceutical
micro-dosing. Feasibility H for flour and spices, M for free-flowing crystals, which dribble.

**N18 Ice pig for paste lines.** If any pipe or pump for pastes and sauces exists, clean it by
pumping a slurry of crushed ice from the machine's own freezer: the ice plug scours the wall
like a solid pig but passes bends and valves, then melts to drain. Ice pigging is used in food
and water industries and recovers product as well. Feasibility L-M at this scale (needs an ice
maker and a slurry pump); listed because it removes the usual objection to piston fillers.

**N19 Weigh-and-drop carrier cup.** The bucket of a multihead weigher, scaled down: a stainless
cup of 0.3 L hanging on a 300 g load cell at the dry dosing dock, with a clamshell bottom opened
by pushing the cup down onto the rim of the target vessel. All seasonings of one recipe step are
weighed into it together (±0.1 g each) in dry air and dropped in one go. One cup per meal, washed
as ware. Feasibility H.

**N20 Corer-wedger die.** A tube punch of 22 mm in the centre of a slicing frame with 6 or 8
radial blades, as a die under a press (C, or the N14 cylinder): apple or pear pushed through at
200-400 N comes out as cored wedges, the core stays in the tube and is ejected to waste by the
next stroke. The fruit must be centred stalk-up: a three-finger self-centring cone above the die.
Also halves peppers around the seed core if they are pushed stalk-first (seed core goes up the
tube; about 70 % success expected because pepper cores are off-centre). Feasibility H for apple,
L-M for pepper.

**N21 Pepper deseeding by halve and tumble-rinse.** Cut the cap off (first slice of the slicing
disc, diverted to waste by the chute flap), halve, then tumble 30 s in the basket liner with 8 mm
holes under a water spray: seeds and loose ribs leave through the holes. White ribs remain.
Feasibility M.

**N22 Snipper drum for bean ends.** Factory bean snippers tumble the beans in a drum whose wall
has tapered slots; bean ends poke through and a knife outside the rotating wall cuts them off.
At home: a slotted basket of 200 mm diameter rotating inside a fixed shell with one blade bar,
40 rpm, 2-3 min for 500 g. Also tops radishes and tails gooseberries. Feasibility M; the gap
between basket and blade is a cleaning concern, so basket and shell must separate for the washer.

**N23 Miniature lasagne line (assembly by moving the dish, not the food).** Assembly is 6.9 % of
the corpus and has no workaround. Factories never pick and place sauce or layers: the tray
travels under fixed depositors. Put the baking dish (or the plate, or a burger bun on the belt) on
an X-slide with 400 mm travel under three fixed outlets: a slot die on a piston box (sauce ribbon
100 mm wide, 3 passes cover 300 mm; layer mass by stroke, +/-5 %), the sifter (cheese, crumbs)
and a suction plate that takes one pasta sheet, slice or patty from its box and sets it down.
Layer evenness comes from dish speed times piston speed. Covers lasagne, gratins, casseroles,
moussaka, pizza topping, open sandwiches, burgers, trifle. Feasibility H for sauce and sprinkle
layers, M for the suction pick of wet or perforated items.

**N24 Release by induction pulse.** Unmoulding (4.4 %, no workaround) fails when the contact
layer sticks. For steel moulds: invert the mould over the dish (N1 book flip), then heat the mould
wall by a 1-2 s induction pulse (2 kW: a 400 g mould rises by about 15 K). The fat or gel film
at the wall melts, the content drops, the core stays cold. It is what a cook does by dipping a
pudding mould in hot water. With N5 (loose floor pushed by a pin) as the positive ejector.
Feasibility M-H; aluminium and silicone moulds do not couple, so moulds must be ferritic steel.

---

## 5. The concept I would bet on

**A two-machine cell: B (Trommelwerk) for everything that is bulk or liquid, and a shortened D
(Flachband, 500 mm belt) for everything that is flat, formed, layered or carved, with the piston
box N5 as the forming and paste-metering device between them.**

Before the corpus check I would have bet on B alone with a small book-flipper as a satellite. The
corpus moved me: the operations without any purchase workaround (flip 12.9 %, assemble 6.9 %,
carve 4.8 %, unmould 4.4 %, score 2.8 %) and the shaping cluster (15.3 %) are all "item on a
surface" operations. A drum does none of them, and a belt with a guillotine, a roller, a curl
belt, a nose and a dish slide does nearly all of them with one drive concept. So the flat machine
is not a satellite; it is the second half.

Why B for the bulk half:

1. Cleaning decides this machine, and the drum is the only concept whose cleaning is already a
   mass-produced appliance: a rotating smooth cup with a liquor, a spin and a drain. It has
   the smallest shared wetted area (0.5 m2), the least water (6 L), no shaft seal in the food
   zone, and it dries and disinfects itself by induction in about a minute, which removes the
   usual bottleneck of "wait for the washer" between components of one meal.
2. It has the fewest axes (9 with the dock) and all of them are rotary; there is no robot arm and
   no precision positioning. The main drive is a washing-machine part made in millions.
3. It covers the foundation tier and the produce operations that prior art never solved (R1 4.3)
   with proven factory principles: drum peeler, drum washer and spinner, bowl chopper,
   rotating-bowl kneader, tumble coater, rotating wok. It holds the corpus maxima (9 L boil,
   10 L mixing).
4. Rotation brings the food to the tool and wipes the wall under a fixed scraper, which answers
   the transfer-residue requirement (PRP-013) without a manipulator.

Why D, shortened, for the flat half:

1. It is the only concept here that flips, carves, scores, rolls, breads, sheets and layers, and
   it does them with factory principles rather than with a dexterous arm.
2. Shortened to a 500 mm belt with four stations (roller, guillotine with depth stop, curl belt,
   nose) plus the sifter and the dish slide of N23, its wetted area drops to about 0.9 m2.
3. It is used in perhaps a third of the meals, so its weak point (the station bridge above the
   belt, the hardest thing to wash in this document) is loaded less often than the drum.

What I am least sure of: whether the station bridge passes a riboflavin test; whether a belt nose
can flip a 240 mm pancake; and whether one drum can be scheduled through a four-component meal.
If the bridge cannot be cleaned, fall back to N1 (book flipper, loose silicone sheets washed as
ware) plus a separate slicer: less capable, far easier to wash. If the drum is the bottleneck,
add a second drum of 200 mm.

From A (Fallturm) I would keep the own-lid free-fall dosing, the downdraft and the wash cartridge,
which fit on top of B. A is the most elegant on paper and has the largest wash area. From C I
would keep the press only if the corpus walk-through shows regular dice, coring and formed items
justify a 5-10 kN axis; the piston box alone gives most of its forming value.

---

## 6. Open issues

1. The corpus check in section 3.1 is a judgement per operation, not a meal-by-meal walk-through; the counts in section 3 are against the requirements' unit-operation list.
2. Own-lid dosing changes the box standard and the storage height pitch; this needs the storage
   and architecture designers' agreement. Mesh sizes per product class need tests.
3. Drum scheduling for a four-component meal for six persons has not been simulated.
4. Drum residue under a fixed scraper, peel loss at 1.5 kg batch size, and chop uniformity of the
   mouth-entering Kutter knives are unmeasured.
5. Rouladen: neither the roll loop nor the curl belt has been tried with real filled slices; the
   seam-down cassette changes the browning method (adapted method under MEAL-013).
6. Onion skinning (N7) and the egg opener (N6) are the two single mechanisms with the highest
   uncertainty and the highest frequency of use.
7. Kneading by reciprocating extrusion (C) may not develop gluten adequately.
8. Flat pan work (flip steak, pancake) sits on the border to the cooking module; ownership
   between preparation and cooking has to be decided by the architecture.
9. Assembly of soft items by suction plate (N23), carving of bone-in poultry, stripping and
   plucking are open; the last two are unsolved in this document.
10. Induction self-drying needs a drum material that is both induction-capable and meets HYG-011
   (ferritic 1.4016 or clad 1.4301/ferritic); corrosion under detergents to be checked.

## 7. Risks

| Risk | Concept | Consequence | Mitigation |
|---|---|---|---|
| Spin with unbalanced wet charge shakes the cabinet | B, A | Noise, fatigue | Washing-machine balancing ramp; limit spin to 450 rpm; mass of the module |
| Spray shadows in stage undersides and station bridge | A, D | Fails HYG-019 | Parts rotate during wash; upward nozzles; riboflavin test early |
| Powder cakes on the mesh lid in humid kitchens | all | Dosing fails | Dust cap, downdraft, desiccant in lid, mesh lid washed with box |
| Abrasive liner sheds grit | A, B, N13 | Foreign body | Stainless knurled or brazed-carbide abrasive instead of bonded grit; PRP-035 check by weight of liner |
| 10 kN press and cutting grids | C | Safety case, frame mass | Closed yoke, interlocked door, slab-then-grid to stay below 5 kN |
| Hot fat on belts | D, N4 | Belt damage, wash load | PTFE-glass belt at the pan; separate cassette |
| Too many lid and tool types | all | Cost, PRP-003 | Rank by corpus frequency; drop lid type I if M and O cover it |
| One drum as single point of failure | B | No meal | Drum is a vessel on a standard flange; spare drum; pots can still cook dosed ingredients |
