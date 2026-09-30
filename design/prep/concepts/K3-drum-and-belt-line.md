# K3 — Drum and belt line

Round P3 exploration of candidate K3 of [02-concept-catalogue.md](../02-concept-catalogue.md), following
[03-exploration-brief.md](../03-exploration-brief.md). Written without reading the other documents in
`design/prep/concepts/`.

Sources read: `BRIEF.md`, `DECISIONS.md`, the exploration brief, the catalogue, idea files B (complete),
F §3.3, C §3, A §1.4, D §3 (complete for the source concepts), the other idea files through the catalogue
only, `requirements/requirements.md` sections 3.5, 3.6, 5, 6, 7, corpus sections 0, 3 (benchmark rows), 4.5–4.9,
6.2–6.3, and research R4 §2, §3, §6.2, §8, §10, §11, R5 §5, R6 §2.2, §2.3, §6.

**Status of every number: paper estimate [E] unless a source is named. Nothing here has been built or tested.**
Confidence ratings: H = known practice at comparable scale, M = sound but needs a bench test, L = speculative.

Contents: 1 definition · 2 mechanism · 3 intake and dosing · 4 operation table · 5 benchmarks · 6 cleaning ·
7 numbers · 8 coverage · 9 failure modes · 10 risks · 11 improvements and changes · 12 open issues and requests.

---

## 1. Definition

K3 is a process line without a food manipulator. Food is worked by three machines that stand around one
vertical shaft:

* **The drum** (left): one tilting, self-washing, induction-heated cup Ø 300 × 350 mm. It washes, peels,
  spins, tumbles, kneads, chops, whips, mashes, tosses, boils, drains and sautés. It pours about its own
  lower lip, which stays at a fixed point at the edge of the shaft.
* **The belt** (right): a 300 mm wide homogeneous belt, 420 mm fixed bed plus a nose that extends 370 mm
  across the shaft to the drum lip. Two gates stand over it (a reciprocating guillotine at the nose, a
  three-face turret beam in the middle) and a roll pocket can be formed in it. It slices, carves, scores,
  sheets, rolls, forms, breads, arranges and lays down.
* **The tool arm** (rear wall, between the two): one spindle on a swing arm that reaches both into the drum
  mouth and over the shaft. It carries knives, whisk, roller, masher, stirrer, the cutter cartridges
  (slice, dice, grate, sticks) and the drum's loose floor discs and basket.

Food moves between them by gravity and by the belt: the drum pours onto the extended nose or straight down
the shaft; the belt drops or lays its product into whatever vessel stands in the shaft; the dock above the
shaft doses into the drum, onto the belt or into that vessel.

**Vessels are handled by a vessel shuttle in the shaft** (a weighing, heated lift deck and a handle gripper
with reach to both sides and a roll axis). It is not a food manipulator: it never touches food, only the
handle tang of a vessel. It serves three stacked hob shelves under the belt and a compact oven under the
drum, tips a vessel into the drum mouth, and inverts a pan pair. This is the largest change from the catalogue
definition, which left vessel handling open (section 11.2).

Heated positions: drum (3 kW), lift deck H0 (3 kW), shelf R1 (3 kW), shelf R2 (2 kW), shelf R3 (1.5 kW,
warm-hold and hand-over port), oven (bought compact combi-steam oven, 45 cm niche, ≥ 45 L, turned sideways
with a modified door). Four positions and the oven can heat together within 3 × 16 A (section 7).

### 1.1 Front view (looking at the machine, dimensions in mm)

```
 z
2000 +--------------------------+-------------------+--------------------------+
     | dry: electronics, fan,   | DOCK: box tipper  | dry: drives of the gates |
     | condenser                | on 3 load cells,  | (rods enter through the  |
1700 |  . . . . . . . . . . .   | swivel chute,     |  bridge ceiling), belt   |
     |  swing envelope of the   | paste ram, egg    |  wash pump               |
1550 |  drum (pour position)    | opener, weigh cup |==========================| bridge ceiling 1480
     |        __                |    \  |  /        |  G2 turret beam   G1     | (sloped, Zone S)
     |       /  \__             |  tool arm (swing  |  [roller|comb|   guillo- |
1330 |      / drum \__  mouth up|  about Y, rear    |   blade]          tine   |
     |     /  Ø300    \ +60 deg |  wall)            |     O               |    |
1180 |    / x 350    __(o)<-lip pivot, fixed        |     v               v    |
1150 |    \       __/   :  <===== extended nose ====+=====belt top 1150========| tail
     |     \   __/ pod  :  (stroke 370)             |  pocket      slider bed  | chute
1000 |      \_/         :      SHAFT 370 wide       |  (o)  return strand (o)  | to
     |                  :   +-----------------+     |  [ belt wash box ]       | waste
 990 |  drain gutter    :   | head: handle    |     +--------------------------+
     |  (swings under   :   | gripper, X +-440|     | R1  3 kW, turntable,     |
 785 |   the lip)       :   | roll 360 deg    |     |     lid arm   surface 700|
     +------------------+   +-----------------+     +--------------------------+
     | OVEN compact     |   | deck H0 3 kW,   |     | R2  2 kW, turntable,     |
     | combi-steam,     |<--| 3 load cells    |-->  |     lid arm   surface 380|
     | sideways, sliding|   +-----------------+     +--------------------------+
 330 | door to the shaft|   two mast tubes Ø 50     | R3  1.5 kW warm-hold =   |
     +------------------+   at the rear wall        |     HAND-OVER PORT   120 |
     | sump 8 L, pumps, |   shaft floor, drain      +--------------------------+
   0 | strainer, bio bin|                           | dry: induction generators|
     +------------------+---------------------------+--------------------------+
     0                 590                         960                      1450  x
```

### 1.2 Top view at belt level (z = 1150)

```
 y (depth)
 600 +------------------------------------------------------------------------+ front door
     |  door, glazed, interlocked                                             |
 560 +------------------+-------------------+---------------------------------+
     |                  |                   |  belt edge guide                |
     |   drum Ø 300     |      shaft        |  ============================   |
     |   (axis in the   |   370 x 540       |  belt 300 wide, bed 970..1390   |
     |    x-z plane)    |   vessel up to    |  ============================   |
     |                  |   GN 2/3 or tray  |  gate rods (4) at the belt edges|
 140 |  trunnion yoke   |   400 x 300       |                                 |
     |  (from rear wall)| (o) (o) mast tubes|  belt drive shaft, pocket shafts|
  60 +------------------+---+-------+-------+---------------------------------+
     | dry spine 60 mm: tilt drive, arm drive, belt drive, shuttle, lid arms  |
   0 +------------------------------------------------------------------------+ wall
     0                 590                 960                             1450
```

Cell: **1450 mm wall width × 600 mm deep × 2000 mm high**, including the oven and five heated positions.
The wet zone is one welded stainless enclosure with a sloped floor in each column and one common drain.

---

## 2. Mechanism

### 2.1 Drum

| Item | Value [E] |
|---|---|
| Shape | Spun cup, inner Ø 300, length 350, full-width mouth with a rolled pouring lip r = 6; closed back. One welded helical fin, 15 mm high, 1.5 turns, fillet r = 6 both sides (forward rotation keeps the charge in and turns it over, reverse rotation screws it out: SM-116). No other internal feature |
| Material | Tri-ply: 1.4404 inside (0.8 mm), aluminium core, 1.4016 ferritic outside; total 3 mm; mass about 6 kg. Answers catalogue question 5: austenitic food side for HYG-011, ferritic outside for induction, no exposed aluminium edge (lip rolled and seal-welded) |
| Volumes | 24.7 L gross; 18 L of liquid at +60°; working charge 4 L of solids, 9 L of boiling water, 1.6 kg of dough |
| Spin | Direct-drive outer-rotor motor of washing-machine class in a sealed stainless pod behind the closed drum back; 2–500 rpm, 30 Nm. Critical speed 77 rpm; tumble 10–55 rpm; spin 450–500 rpm (34–42 g at the wall) |
| Tilt | **About the lower lip.** The trunnion axis (along y) passes through the lowest point of the mouth rim, so the pouring lip stays at x = 590, z = 1180 for every tilt angle. Range +60° (mouth up) to −35° (pour). Worm gearmotor behind the rear wall, 150 Nm, self-locking; load at horizontal about 75 Nm (25 kg at 0.3 m). Yoke cantilevered from the rear wall on a hollow shaft Ø 60 |
| Swing envelope | Radius 555 about the lip pivot: x 35…590 (plus the mouth reaching to x = 760 above the shaft when pouring), z 780…1700 |
| Heating | Curved induction coil segment fixed to the yoke under the lower third of the wall, 3 kW, with an IR sensor on the wall and a contact sensor in the pod. 6 kg from 20 to 110 °C: 270 kJ, 90 s |
| Weighing | Three load cells between yoke shaft bearing block and frame (dry side): ±5 g on 30 kg at standstill |
| Water | The lance of the tool arm (mains through a flow meter, and the recirculation pump) |
| Drain gutter | A stainless trough on a rotary shaft through the rear wall swings under the lip: wash liquor, cooking water and peel go to the strainer and the sump, never down the shaft |

Loose parts that ride in the drum (all are put in and taken out by the tool arm through the mouth, section 2.3):
basket liner (perforated shell Ø 292 × 260, 3 mm holes, three lugs that key into the helix), peel disc
(knurled stainless floor disc Ø 290, no bonded grit), stud disc (silicone-studded floor disc).

Wall penetrations: hollow tilt shaft (one rotary lip seal Ø 60 with drained lantern, above floor level, in
the splash zone but 250 mm behind the mouth); gutter shaft (rotary seal Ø 20). The spin shaft seal is between
pod and drum back, under an umbrella skirt, and sees splash only from the wash-down of the bay. **No seal or
shaft inside the food volume.**

### 2.2 Belt

| Item | Value [E] |
|---|---|
| Belt | Homogeneous TPU, 2 mm, 300 wide, endless welded, no fabric, no teeth on the food side; driven by a lagged drive roller Ø 60 with a tracking rib on the inner face. Bought material (Volta / Habasit class); contact 80–90 °C in the wash, short contact 110 °C [unverified for the chosen grade] |
| Bed | Fixed slider bed x = 970…1390 on three load cells (±2 g on 5 kg): stainless plate with longitudinal drain grooves; interrupted at the pocket |
| Nose | Retracting nose bar Ø 16 on a carriage, stroke 370 (tip at x = 970 retracted, 600 extended). The extended part is carried by two side rails cantilevered from the rear wall. Take-up of 740 mm of belt in a dancer loop on the return strand |
| Drive | Gearmotor behind the rear wall, shaft through a rotary seal; 0–300 mm/s, reversible, encoder ±0.5 mm |
| Pocket | At x = 1100 the bed has a 70 mm gap between two pocket rollers Ø 25. The dancer releases 170 mm of belt, the top strand sags into a loop, the rollers close to 12 mm, the belt runs: whatever lies in the loop rolls on itself, contained all round (SM-079). Loop inner diameter 45–65 |
| Tail | Right end at x = 1390: a scraper and a chute to the waste strainer (surplus flour, crumbs, trimmings, first and last slices leave here, away from the shaft) |
| Wash box | Under the bed, on the return strand: scraper, two spray bars (both faces), hot bar, air knife (section 6.2) |
| Tension release | The dancer retracts fully: the belt hangs slack so that its inner face, bed and rollers are sprayed |

Gates (the "bridge" of the catalogue, reduced to two):

| Gate | Build | Actuators | Function |
|---|---|---|---|
| **G1 guillotine** | Two vertical rods Ø 20 through the bridge ceiling, independent, 300 N each, stroke 240; between them a bow frame with one scalloped blade 320 mm, reciprocated 10 mm at 40 Hz by a rocking shaft in the crossbar (sealed oscillator pod on the dry end). The blade passes 0.5 mm in front of the retracted nose bar and never touches the belt | 2 + 1 | Overhang cut: belt advance = slice thickness (1 mm to any length); carving; scoring with a depth stop from the rod encoders; rocking cut by running the rods unequally; trimming first and last slice to the tail |
| **G2 turret beam** | Two coupled vertical rods, stroke 240, 800 N; between them a beam that indexes about its y axis in 120° steps (sealed gearmotor pod on the dry end of one rod). Face 1: sheeting and press roller Ø 70, a bought hygienic drum motor. Face 2: divider comb, nine blunt blades at 30 mm pitch. Face 3: silicone-edged doctor blade on a flat press plate 280 × 120 | 1 + 1 + 1 | Flatten, sheet, press crumbs, hold down, divide logs and slabs, strips, spread, level, press plate for burgers and dough |

Wall penetrations: four gate rods through the ceiling (rod seal, scraper and drained collar each, SM-191;
rods are above the belt edges, not above the 250 mm food lane); belt drive shaft, two pocket roller shafts,
dancer shaft, nose carriage rod (rear wall, rotary or rod seals). Six rotary or rod seals in the rear wall.

Answer to catalogue question 6: the shortest line that still does the no-workaround operations is a 420 mm
bed, a 370 mm nose, one blade gate, one turret beam and the pocket. Sifter, curtain, curl belt and dish
slide of the source concept are removed: dusting and pouring come from the dock and from a vessel held by
the shuttle above the extended nose, rolling is done by the pocket, and the dish stands on the lift deck.

### 2.3 Tool arm

An L-shaped closed tube on a rotary shaft through the rear wall at x = 640, z = 1420. Swing 270° about y
(gearmotor 40 Nm), quill plunge 90 mm along the tool axis (200 N), spindle 30–3000 rpm (1 kW; 20 Nm below
400 rpm, 3 Nm at 3000). All three motors are behind the rear wall; the drives run through the hollow swing
shaft and a bevel stage inside the arm. One penetration with concentric seals; the quill has a scraper and a
drained collar at the nose. Tools lock on the spindle nose by a taper with bayonet (plunge and turn, SM-234)
and park on pegs on the rear wall along the arm's arc, above the drum bay, where the bay wash reaches them.

The arm works in three places: **in the drum** (any tilt between +20° and +60°; the drum tilts to meet
the arc), **over the shaft** (tool axis vertical, above a vessel on the deck raised to it), and at the rack.

| # | Head | Bought / custom | Used for |
|---|---|---|---|
| T1 | Knife pair (two sickle blades Ø 160 on a stalk) | blades bought, stalk custom | bowl-chopper mode in the drum: onion, herbs, crumbs, purée; chopping in a pot on the deck |
| T2 | Balloon whisk | bought | whip, whisk, emulsify in the drum corner or in a beaker on the deck (1 egg white) |
| T3 | Roller and scraper (passive; spindle locked) | custom | knead against the turning wall (SM-171), cream, fold, scrape the wall while pouring (SM-115), hold back the charge over the peel disc |
| T4 | Masher grid (passive) | custom | mash in the turning drum |
| T5 | Stir paddle with silicone edge | custom | stir and scrape a pot on the deck |
| T6 | Lance with three fan jets | custom | water dosing, drum wash, rinse of the mouth |
| T7 | Mouth sieve | custom | drain the drum through the mouth when the basket is not in |
| C1–C5 | Cutter cartridges: cage with kidney hopper 180 × 110, top-driven disc, fixed grid below; nothing under the grid. C1 dice 10, C2 dice 20, C3 slice 4, C4 grate 3, C5 sticks 10 | discs and grids bought (vegetable-cutter class), cage custom | feed-through cutting over the shaft (SM-014): fed from the drum lip, the belt nose or the dock, product falls into the vessel on the deck |
| L1, P1, P2 | Basket liner, peel disc, stud disc | custom | carried to and from the drum by their hubs |

### 2.4 Vessel shuttle, shelves and oven access

Two polished stainless tubes Ø 50 stand at the rear of the shaft from floor to z = 1500. Two carriages
slide on them on polymer bushings, each driven by a magnet follower inside one tube (belt drive inside the
sealed tube; 400 N coupling force [E]; a decoupled carriage cannot fall because the inner follower is braked
and a pawl on the carriage catches on the second tube). No penetration.

| Carriage | Axes | Function |
|---|---|---|
| **Deck** (lower) | Z, 60…1100 | Flat glass-ceramic plate 340 × 340 over a 3 kW coil, on three load cells (±1 g to 2 kg, ±2 g to 12 kg). The receiving, weighing and frying position under drum lip, nose, cutter and dock |
| **Head** (upper) | Z 200…1350; X ±440 on a two-stage plain-bearing telescope at the rear wall; roll 360° about y, 25 Nm; grip | Handle gripper: a tapered socket with a latch that takes the tang (a flat tongue 40 × 10 × 70 at rim height on the rear of every vessel, lid, tray, scoop and board). Holds 10 kg at 200 mm. Grips two tangs lying on each other (pan pair). Carries, pours by rolling, shakes, rocks, inverts |

Shelves (right column): R1 and R2 each have a rotating hob plate (rim drive below the deck behind an
umbrella labyrinth) and a lid arm on a rotary shaft through the rear wall that swings the lid, with its
hanging scraper blade, up and down. The pot turns, the scraper stands still (SM-180). R3 is a plain
warm-hold plate and the hand-over port to serving and to the ware washer.

Oven: bought compact combi-steam oven, turned so that its opening faces the shaft; the hinged door is
replaced by a vertically sliding door (one actuator). The head pushes trays, tins and the braiser in along x.

### 2.5 Actuator list

| Group | Actuators | n |
|---|---|---|
| Drum | spin, tilt, drain gutter | 3 |
| Tool arm | swing, plunge, spindle | 3 |
| Belt | drive, nose, pocket close, dancer | 4 |
| Gates | G1 left, G1 right, blade oscillator, G2 lift, G2 index, roller drum motor | 6 |
| Dock | box clamp, tilt, lid finger, vibrator, swivel chute, paste ram | 6 |
| Egg opener | cup spin, cup pull, swing over target | 3 |
| Shuttle | deck Z; head Z, X, roll, grip | 5 |
| Shelves and oven | 2 turntables, 2 lid arms, oven door | 5 |
| **Total motion actuators** | | **35** |

Of these, 16 are the preparation machine proper (drum, arm, belt, gates), 9 are the common dosing front end
and 10 are vessel handling and cooking-side handling. Fluid and thermal: 12 solenoid valves, 3 pumps
(recirculation, drain, belt wash), 2 fans, 5 induction generators, 1 sump heater.

### 2.6 Ware list (loose, washed in the ware washer; all with the tang)

| Item | n | Bought / custom |
|---|---|---|
| Pot 1.5 L Ø 160, pot 4 L Ø 240, pot 6 L Ø 240, each with scraper lid | 2 / 2 / 1 | bought pots, tang welded on; lids custom |
| Pan Ø 280 tri-ply, as a pair (either may be the cover) | 2 | bought, tang added |
| GN 2/3 pan 354 × 325 × 40, as a pair | 2 | bought thermoplate, tang added |
| Braiser GN 2/3 × 100 with lid and seam-down rack (five channels) | 1 | bought GN, rack custom |
| Baking tray 400 × 300; lasagne dish 300 × 200 × 60; loaf tin, 26 cm ring tin (ferritic) | 2 / 1 / 1 / 1 | bought, tang added |
| Scoop (GN 1/4-like pan with a spout end) | 2 | custom |
| Peel tray (flat tray with one rimless ramped side), also the unmoulding board | 2 | custom |
| Beaker 0.8 L with weir spout; weigh cup 0.3 L for the dock | 2 / 2 | custom |
| Lift-out basket for the 6 L pot | 1 | bought |

27 loose ware items, plus the 15 arm heads and drum inserts of 2.3. The 9 L pot is not needed: six portions
of pasta are boiled and drained in the drum.

---

## 3. Ingredient intake and dosing

### 3.1 The dock

One tipper dock above the shaft (x = 775, z = 1600–1900): clamp frame on a horizontal axis (0–180°, 15 Nm),
on three load cells (loss in weight, ±1 g to 3 kg), 150 Hz vibrator, one lid finger. Under it a **swivel
chute**, a stainless spout 140 × 100 on a vertical axis with three positions: into the drum mouth (drum at
+60°), straight down the shaft (onto the extended nose at 1150 or, with the nose retracted, into the cutter
cartridge or the vessel on the raised deck), and to the fixed part of the belt. The chute ends 120 mm above
the belt, so powders fall through a closed sleeve and not as a cloud (PRP-014).

A second, small dry position beside the tipper holds the **weigh cup** (0.3 L on a 300 g cell, ±0.05 g) for
seasoning: all seasonings of a step are weighed into it in dry air and the cup is tipped through the chute
(SM-141, rule R8). The dock stands beside, not above, the steam path: steam from the deck and the drum
rises at x < 760 into the extraction slot at the rear wall; the dock sits behind a downward air curtain of
30 m³/h (SM-142).

Boxes: GN 176 family with lid. K3 works with **plain boxes** (lid removed by the finger, tilt-pour with
vibration and weight feedback, SM-133). It works better with two own-lid types (SM-134), which I request
from the architect but do not depend on: a mesh lid for powders and crumbs (SM-135) and a spout lid for
liquids. The fallback for powders from a plain box is a vibrated mesh insert in the chute; it is then a
shared surface and must be dry.

### 3.2 By ingredient form

| Form (PRP-010) | Path | Accuracy [E] | Conf. |
|---|---|---|---|
| (g) Whole produce | Box tilted at the dock, pulse-tilt with vibration, pieces roll down the chute into the drum; count and mass from dock and drum load cells; "the recipe follows the scale" (SM-151) | one piece | H |
| (h) Leafy, bulky | Whole box tipped into the drum with the basket liner; surplus is washed and spun with the rest and returned cold in a box, or the recipe is scaled. Herbs: whole bunch into the drum, chopped with tender stems | ±1 box or ±15 g | M |
| (a) Granular | Dock tilt-pour into drum, pot on the deck, or onto the belt | ±2 g | H |
| (b) Powder | Mesh lid or mesh insert, vibrated; through the closed chute | ±2 g; ±0.2 g into the weigh cup | M (humid air) |
| (c) Seasoning | Weigh cup, then tipped; salt in cooking water as brine from a spout box (SM-143) | ±0.05–0.2 g | H |
| (d) Liquid | Water: valve and flow meter at the lance and at a spout over the shaft. Others: spout lid or plain box tilted, stream through the chute, stop on weight | ±2 g | H (spout lid), M (plain box, dribble) |
| (e) Viscous paste | **Paste cartridge** at the dock: a straight tube Ø 60 × 150 with a loose piston, filled at ingestion or first opening from jar or tube (request X6 of the catalogue). The paste ram (1.5 kN) pushes; a slot nozzle 100 × 4 lays a ribbon on the belt passing below, or a round nozzle drops slugs cut by a wire into the vessel | ±3 % | M |
| (f) Solid fat | Butter as a bar on the belt: G1 cuts by length and the pieces fall from the nose into the vessel (SM-148). Cold butter cuts cleanly | ±3 g | H |
| (i) Raw meat, pieces and mince | Pack or box tipped at the dock: mince and cubes into the drum or a pan; chute rinsed afterwards | one piece | H |
| (i) Raw meat, flat cuts | Slide from the tilted box down the chute onto the moving belt (chute exit tangential, belt speed = slide speed, so the cut lies flat). One cut per box compartment works; **a stuck stack of slices does not** (section 12, open issue 2). Alternative: the block is tempered in the freezer airlock and sliced by G1 (SM-100, SM-240) | — | M single cut, L stack |
| Egg | Egg opener at the dock (SM-164: two cups, scribe, pull), over an inspection saucer on the weigh position; camera; then tipped through the chute (SM-168). Eggs arrive in a tray insert; the cups take one at a time | 10 s per egg | M |
| (j) Frozen loose | As granular. Blocks fall into the hot drum and are tumbled free | ±3 g | H |
| (k) Long goods | Spaghetti: box tilted, strands slide down the chute into the drum (boiled there); dose by weight loss, ±15 g. Leek, cucumber, carrot: slid onto the belt lengthwise; the chute aligns them | ±15 g | M |
| Stowed sealed packs | Opened just in time by the package-opening mechanism (not part of K3), which delivers the contents in a box, or the opened can, carton or tub in a carrier that the dock clamps and tilts like a box. Jars of paste go into paste cartridges once. Vacuum-packed meat arrives unpacked in a box | — | depends on the opener |

Transfers inside the cell (PRP-013):

| From → to | How | Residue [E] |
|---|---|---|
| Drum → vessel on the deck | Pour about the lip, roller-scraper on the turning wall, recipe liquid as chase (SM-115, SM-119) | liquids < 1 %, dough and mince 2–4 % |
| Drum → belt | Pour onto the extended nose 30 mm below the lip while the belt runs away from the lip | same |
| Drum → cutter | Reverse helix screws out a few pieces per turn into the cartridge hopper under the lip | — |
| Belt → vessel | Overhang cut and drop, or nose lay-down: deck raised to 15 mm under the nose, nose retracts at belt speed (SM-101) | < 1 %, scraper at the nose |
| Belt → drum | Product falls into a scoop on the head; the head rises and rolls the scoop into the drum mouth | < 1 % loose pieces |
| Vessel → belt | Flat items: the nose crawls under them on a peel tray held by the head (belt speed = advance speed, SM-102). Masses and roasts: the head rolls the vessel and the content slides onto the extended nose | M; untested for wet cutlets |
| Vessel → vessel, vessel → drum | Head rolls the vessel over the target; scraping only by chase liquid | pastes 5–10 % (weak: no scraper) |

---

## 4. Operation table

Time is for the quantity of 4 persons unless stated. "Untested" names what a bench test must show.

### 4.1 MEAL-018 (a): no purchase workaround

| Operation | Mechanism and sequence | Time | Conf. | Untested |
|---|---|---|---|---|
| Flip pieces (FLP: patty, steak, cutlet) | Pan-pair inversion by the head (SM-127): cover pan, preheated on R1, is rolled and set rim to rim on the pan; the gripper takes both tangs; out to the shaft, roll 180°, back, upper pan lifted off. Small loose pieces (fried potato, strips, meatballs) are browned in the drum by tumbling | 25 s per pan | M | hot fat > 30 mL runs out at the rim; breading that sticks to the upper pan |
| Flip whole-pan items (pancake, omelette, Rösti, Puffer) | Same pan pair | 25 s | M | thin pancake folding during the turn |
| Assemble layered dishes (LAY, TOP, SPR) | Dish on the deck under the retracted nose. Sheets and slices are arranged on the belt and laid in by the nose; sauces are poured from their pot by the head moving in x, levelled by lowering the dish and a short shake; cheese from the dock chute | 6–8 min for a lasagne | M | evenness of a stiff ragù layer (no spreader reaches into a dish on the deck) |
| Assemble open-hand food (ASM) | **The order on the belt is the order in the stack.** Bun base, patty, cheese, tomato slices, top are lined up on the belt and laid on each other by the nose on a plate on the deck, the deck stepping down. Burger and open sandwich: yes. Taco, wrap, filled sandwich closed by hand: components only | 60 s per burger | M (stack), not done (taco, closed sandwich) | lateral accuracy ±10 mm; cold cuts that stick together |
| Carve a boneless roast (CAR) | Roast slid from its tray onto the extended nose, carried under G2 (press plate as hold-down 30 mm behind the cut), sliced by the reciprocating blade at the nose; slices fall 40 mm onto a tray on the head that steps 8 mm per slice (shingled) | 2 s per slice | H cold, M hot braised | tearing of hot soft meat |
| Carve bone-in poultry | Not done. Parts are bought or cooked whole and served whole | — | — | — |
| Unmould (UNM) | Ferritic tin. Short induction pulse on the deck (SM-241), the head lays the peel board on the tin, grips both tangs, rolls 180°, sets down, lifts the tin off | 40 s | M | sticking; tin geometry with a centre tube |
| Score (SCO) | G1 with depth stop from the rod encoders, item on the belt under the G2 hold-down; parallel cuts by belt steps. Diamond pattern is not possible (no rotation of the item) | 1 s per cut | H parallel, not done: crossed | proofed bread deflating under a vertical blade |

### 4.2 MEAL-018 (b): the shaping cluster

| Operation | Mechanism and sequence | Time | Conf. | Untested |
|---|---|---|---|---|
| Form patties (FRB) | Mass kneaded in the drum (T3). Poured onto the belt in two heaps, carried into the pocket: rolled to a log Ø 60 × 280 lying across the belt. Pocket opens, the comb (G2 face 2, pitch 30) divides the log into nine pucks of about 85 g; two pucks pressed together for large patties, or the press plate flattens each to 20 mm. The nose lays them in the pan | 12 patties 3 min | M | log diameter ±; mince sticking in the pocket; ±10 % mass (belt load cells verify each log) |
| Form dumplings (FRK), small pieces (FRM) | As above with logs Ø 35–60; pucks tumbled in the wetted or floured drum for 20 s to round them (SM-074); gnocchi as cut log pieces; Schupfnudeln: log pieces rolled under the press plate by belt to-and-fro | 4–5 min | M | rounding of sticky dumpling mass in the drum; tapered ends |
| Bread (BRD) | 1 flour bed from the dock on the belt; cutlet laid on it; flour on top. 2 Nose lays the cutlet on a peel tray with 60 g of whisked egg, held by the head; the head rocks ±10°: egg washes over. 3 The nose crawls under the cutlet and takes it back onto a crumb bed; crumbs on top; roller presses at 30 N. 4 Nose lays it in the pan. No flip, no gripper | 50 s per cutlet | M | nose pick-up of a wet cutlet; coverage of the underside edge; crumbs in the egg |
| Roll and secure (RLT), wrap (WRP) | Slice on the belt, long side along x, two slices side by side. Paste ribbon from the cartridge, spread by the doctor blade; filling from a scoop or the chute as a stripe across the first third. Belt carries the slice over the pocket, dancer releases, the filled part sags in, rollers close, belt runs 300 mm: two tight rolls. Belt position sets the seam down. Pocket opens; the nose lays the rolls seam-down into the rack in the braiser on the deck (SM-084). No tying | 30 s per pair | M roll, **M–L secure** | start of the first turn; filling squeezed out at the ends; rolls staying shut through a two-hour braise |
| Roll out dough (ROL), shape (SHD) | Dough poured on the belt, reversing passes under the roller, gap 20 → 3 mm, flour from the dock between passes. The last pass elongates the sheet over the nose directly onto the baking tray, which the head moves away at belt speed. Sheet up to 300 × 400. Rolls: log and comb, rounded in the drum. Loaf: log into the tin. Lining a tin: sheet laid over the tin by the nose, pressed in by the press plate only for a rectangular tin 280 wide | 2–3 min | H sheet, M rolls, L lining a round tin | sticking to belt and roller; a round base for a 26 cm tin is pressed in as crumbs (adapted) |
| Stuff rigid cavities (STU) | No nozzle is fed by the drum, so the filling is made a solid first: mass from the drum rolled to a log Ø 45 in the pocket, divided by the comb, and each plug dropped by the nose into the cavity (pepper, tomato, apple standing in a rack on the deck; the deck has no x axis, so the rack is held by the head and stepped in x). Soft fillings (quark, cream) only from a paste cartridge filled beforehand. Cannelloni: not filled; made as rolled sheets in the pocket instead (adapted) | 20 s per item | **L–M** | plug hitting a 60 mm opening from the nose (±10 mm); dumpling cores and poultry cavity not done |
| Flatten meat (POU) | Roller passes at 12 → 8 → 5 mm, 800 N line force, on the belt | 20 s | H | — |
| Spread (SPR) | Ribbon from the cartridge or poured line, doctor blade at 1–3 mm | 10 s | H | — |
| Sprinkle (TOP) | Dock chute over the item carried to and fro on the extended nose | 15 s | H | — |
| Grease and line a tin (LIN) | 8 g of melted butter poured in; the head rolls and rocks the tin through ±70° in two planes is not possible (one roll axis): wall coverage on two sides only. Completed by flour dust. Alternative: butter ribbon and crumbs | 30 s | L–M | coverage; sticking cakes |

### 4.3 Peeling, trimming, cutting, egg

| Operation | Mechanism and sequence | Time | Conf. | Untested |
|---|---|---|---|---|
| Wash robust produce (WSH) | Bare drum, 1.5 L, tumble 45 rpm with reversal, pour to the gutter, rinse | 60 s | H | — |
| Wash and dry leaves (WLF, DRY) | Basket liner, 2 L flood, 20 rpm, drain, 480 rpm for 2 × 15 s | 2 min | H | bruising, balance |
| Peel potato, carrot, roots (PLP, PLH) | **Rumbler mode**: drum at +60°, peel disc on the floor, 120 rpm, the roller-scraper arm held still in the charge so that the potatoes do not ride round with the wall but roll over the knurled disc; lance sprays 1 L/min; slurry poured to the gutter twice | 1.5 kg in 3 min | M | loss (target ≤ 20 %), eyes remain, long carrots cut to 120 mm first |
| Skin-on and rice (SM-056) | Not available: K3 has no ricer. Mash is made from peeled potatoes with the masher grid | — | — | — |
| Peel onion, garlic (PLA) | Bought peeled (SM-242). Upgrade path inside the concept: blanch 45 s in the drum, stud disc and jets (SM-063) | — | L–M | everything |
| Peel cucumber, apple (PLS) | Rumbler with reduced time for cucumber halves; apples are used unpeeled or bought prepared | — | L | — |
| Tomato, boiled egg skin (PLM, PLE) | Blanch in the drum basket, quench, stud disc with water 30 s | 3 min | M | yield of eggs 70–90 % |
| Core, deseed (COR) | Not done (no press, no corer). Bought cored or as frozen strips; pepper: cap cut by G1, halves tumbled in the basket under the lance (SM-043) | — | L | — |
| Trim ends (TRE) | Long goods lie along the belt: first and last slice to the tail chute (SM-037). Beans, sprouts: bought trimmed | 5 s | H long goods | — |
| Strip, pluck (STR) | Not done | — | — | — |
| Slice (SLI) | Long and flat goods, bread, cheese, sausage, tomato: overhang cut at the nose, hold-down by G2. Round produce in quantity: cartridge C3 | 2 cuts/s; 1 kg in 60 s | H | tomato without squashing (blade speed) |
| Dice (DIC) | **Cartridge C1 or C2**: slicing disc pushes each slice through the grid; regular dice of 10 or 20 mm fall into the vessel on the deck. Fed by the drum helix, the nose (carrots cut to 60 mm lengths by G1 first) or the dock. Other pitches: slab by G1, strips by the comb, cross-cut by G1 ("belt dicing", irregular) | 1.5 kg in 90 s | H 10 and 20 mm, M others | last pieces in the hopper; onion dice (rings fall apart: acceptable) |
| Sticks, strips (JUL) | Cartridge C5; dough and meat strips by G1 across the belt | — | H | — |
| Fine chop, mince (MIN, CHH) | T1 knives in the drum at +30° (small quantity collects in the corner), drum at 10 rpm, 3–6 pulses. Herbs for garnish: bundle under the G2 roller, overhang cut at 1.5 mm feed | 20 s | H (bruises), M clean cut | — |
| Grate (GRC, GRF) | Cartridge C4. Hard cheese and nutmeg bought grated; zest not done | 30 s | H coarse, not done: zest | — |
| Juice citrus (JUI) | Not done natively; bought juice, or halves (G1) pressed under the press plate on the grooved bed end: low yield | — | L | — |
| Wedge, halve (WED) | G1 on the belt; tomato and apple wedges as thick slices | — | M | shape differs |
| Crack eggs (CRK) | Egg opener at the dock, saucer, camera | 10 s/egg, 12 in 3 min with two saucers | M | scribe force; fragments |
| Separate (SEP) | Slotted saucer: white drains into the beaker on the weigh position | 20 s | M | — |

### 4.4 Everyday operations

| Operation | Mechanism | Time | Conf. |
|---|---|---|---|
| Knead dough 0.15–1.6 kg (KND) | Drum at +35°, 80 rpm, roller-scraper held against the wall, 20 Nm | 6 min | H (M below 250 g) |
| Mix mince mass (KNM) | Same at 40 rpm | 2 min | H |
| Proof (PRF) | In the drum at 30 °C wall, 1 rev/min; or in the oven at 32 °C with steam, which frees the drum | 45 min | H |
| Whip, whisk, emulsify (WHP, WHK, EMU) | T2 in the drum corner at +30° for ≥ 3 whites or 0.3 L; T2 in a beaker on the raised deck for 1 egg white; oil from the dock at 1–2 g/s | 2–4 min | H |
| Cream, rub in, fold (CRM, RUB, FLD) | T3 and T1 pulses; folding by six slow turns of the drum at +15° over the helix | 1–3 min | M |
| Mash (MSH) | Boiled, drained potatoes in the drum at +40°, masher grid held still, drum 20 rpm, 40 passes, hot milk and butter from pot and dock | 2 min | M ("Stampf" texture, not riced) |
| Purée (PUR) | T1 at 3000 rpm in the drum, or in the pot on the deck | 1–2 min | M (top-entering blade is coarser than a blender) |
| Toss salad (TOS) | Drum at +15°, 12 rpm, 6 turns, dressing from a beaker or the dock | 30 s | H |
| Drain (DRN) | Pasta, potatoes boiled in the drum with the basket or mouth sieve: tilt to −10°, water to the gutter, no vessel lifted. Pots on shelves: lift-out basket taken by the head | 30 s | H |
| Squeeze (SQZ) | Spin in the basket at 480 rpm; pressing under the press plate on the belt | 30 s | M |
| Stir and scrape while cooking | Drum: rotation over the helix. R1, R2: turning pot against the lid scraper. Deck: T5 on the arm | continuous | H |
| Sauté, sear mince, stir-fry | Drum as rotating wok at +15°, wall 160–250 °C | — | H |
| Deglaze, add to a hot vessel | Vessel brought under the chute by the head; or into the drum directly | 20 s | H |
| Baste, glaze | Pour from a beaker by the head; no brush | — | M |
| Thin batter poured (PTH) | Beaker held by the head poured in a zigzag over the pan on the deck; batter levels itself | 10 s | M |

<!--NEXT-->
