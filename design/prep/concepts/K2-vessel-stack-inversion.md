# K2 — Vessel stack and inversion

Round P3 exploration of candidate K2 of [02-concept-catalogue.md](../02-concept-catalogue.md), written to
[03-exploration-brief.md](../03-exploration-brief.md). Sources: catalogue section 3.3 and the SM list,
`ideas/C-universal-vessel.md` (concepts A, B, C, D, S-1 … S-24), requirements section 5 and PRP/COK/HYG,
corpus `research/02`, research 04, 05, 06. Other concept documents of this round were not read.

**Status of every number: paper estimate [E] unless a source is named.** Nothing was built. Confidence
ratings: **H** known practice at similar scale, **M** sound but needs a bench test, **L** speculative.
All dimensions in mm.

## 0. Summary and what changed from the catalogue definition

K2 as catalogued: one round rim, cans / sleeves / discs stacked under a press-and-spin quill, a separate
rim-to-rim inverter, GN 2/3 clamshell pair, wash lathe with induction flash, an unspecified part gantry.

Working it out showed four structural problems. Each was answered inside the concept's spirit, and each
answer is a change to the catalogue definition:

| # | Problem found | Change | Effect |
|---|---|---|---|
| C1 | A separate inverter station costs two gantry moves per inversion, and the gantry was never designed. At 600 depth a front aisle for 290 mm ware does not exist. | **The inverter rides on the lift ("Wender").** One vertical shaft between two station columns; the lift carriage carries a roll axis, two independent neck-jaw pairs and a squeeze axis. Every pick-up can be an inversion. | No inverter station; an inversion costs 4 s inside a move that happens anyway; the carriage can stack, unstack, clamp a lid on, and weigh. |
| C2 | The cold press column plus two stirring hobs plus two flat hobs plus an oven plus washers plus rack do not fit two station columns. | **The press column stands on a heated position ("K/H")**: annular turntable round a fixed induction pedestal. Ricing, puréeing, whisking, kneading, spin-spreading happen in the cooking pot on its hob. | One station less; food leaves its pot less often; K/H becomes the bottleneck station (weakness W2). |
| C3 | Dosing by "box inverted onto a collar in the inverter" costs 5–6 gantry moves per ingredient (about 70 per meal). | **Hourglass dock at the hand-over port**: the transport system pushes the box into a rolling cradle under a ware collar; the cradle's roll angle and a shutter meter the flow into a beaker on a scale. | Zero Wender moves per dosed ingredient. |
| C4 | **Rim-to-rim inversion cannot merge.** It only moves the contents of a full lower vessel into an empty upper one. Adding anything to a vessel that already holds food (onion into fat, mince onto onion, wine onto the fond, milk into mash) is impossible by inversion. The source document does not notice this. | **Tip cradle at K/H** (and the dock as a second tipper): a hat beaker held by its neck is rolled about a fixed axis so that its lip ends inside the mouth of the vessel below. | The rule "no food is ever poured through open air" is broken for every staged addition: a 30–80 mm guided fall inside a closed tier. This is a deviation from the catalogue definition and is recorded as such. |

Further changes: the rim became a spool with a gripping neck (section 2.1), so gaskets live only on
interposers; draining uses a lift-out basket by default and three-layer inversion only for small pots;
one large wash lathe takes round ware and GN trays; stalk tools travel inside their lids as kits; the
round-to-GN transition plate was added (without it nothing gets from a pot onto a tray).

**Result in one paragraph.** A cabinet 1600 wide × 600 deep × 2000 high holds the whole cell including
four heated positions, a sideways built-in combi-steam oven, the washer and the ware rack. 21 motion
actuators, 76 loose ware pieces of 50 types, parts cost about EUR 24 000 [E, ±35 %]. Eleven of the
twelve benchmarks run as "yes" (three of them with a test pending on one step), one (Rouladen) as an
adapted method. Estimated corpus coverage is **89 % (220 of 248; range 86–92 %)**, below the 95 %
target: the
concept has no way to pick one piece up and put it down oriented, which costs the open-hand assemblies
and the stuffed vegetables. It is strongest exactly where the catalogue expected (flip, unmould, drain,
dice, mash, enclosed breading, no seal in any washed part) and weakest in traffic through one carriage
and one press station, in piece handling, and in singulating raw slices.

## 1. Definition

The cell is a closed stainless cabinet with three vertical zones. In the middle a **shaft**, 440 wide,
in which one carriage (the Wender) travels vertically, reaches sideways into both columns, and turns
what it holds about a horizontal axis. On the left the **ware column**: hand-over port with hourglass
dock, ware rack, wash lathe. On the right the **hot column**: oven at the bottom, above it the press
column on its hob (K/H), a stirring hob (S1) and two flat flex hobs (F1, F2). All food is in passive
ware with one round rim (R260) or in GN 2/3 trays; the machine touches ware only on the outside below
the rim. Food is processed inside closed stacks at K/H; it is transferred, flipped, tossed, coated and
unmoulded by the Wender's roll axis; it is merged by tip-in.

```
 FRONT VIEW (door removed)                 width 1600, height 2000
      20   520          15  440   15        560              20
  +----+---------------+--+------+--+----------------------+----+ 2000
  |    | PORT + DOCK   |  |camera|  | F2 flex hob 3 kW     |duct| 1980
  |    | cradle, scale |  |  o   |  |  (GN 2/3 / round)    | +  | 1730
  |    | collar store  |  |      |  +----------------------+ in-| 
  +    +---------------+  |      |  | F1 flex hob 3 kW     |duc-| 
  |    | RACK          |  | === <- Wender carriage:        |tion| 1480
  |    | flats magazine|  | jaws |  +----------------------+ el.|
  |    |  20 x 25 mm   |  | A, B |  | S1 stir hob 3.5 kW   |    |
  |    | GN tray stack |  | roll |  |  spindle from ceiling|    | 1180
  |    | pot / beaker  |  | about|  +----------------------+    |
  |    |  nest stack   |  |  Y   |  | K/H  quill 5 kN,     |C-  |
  |    |               |  |      |  |  spindle, fork,      |frame
  +    +---------------+  |      |  |  annular turntable,  |col-|
  |    | WASH LATHE W  |  |      |  |  hob 3.5 kW, tipper  |umns| 500
  |    | chamber d520  |  |      |  +----------------------+----+
  |    |  x 430, side  |  |      |  | OVEN, 45 cm compact       |
  |    | shutter, coil |  |drain |  | combi-steam, SIDEWAYS,    |
  |    | sump, pump    |  | seat |  | door faces the shaft      |  50
  +----+---------------+--+------+--+---------------------------+   0
   plinth: sump, pumps, drain, water valves, waste strainer drawer

 TOP VIEW at K/H level                       depth 600
  +--------------------+---------+---------------------------+
  | rear wall, Zone N: Z mast of the Wender behind a slot     |  45
  +--------------------+--||-----+---------------------------+
  |                    | roll    |   (o) guide columns of the |
  |   rack position    | head    |       C-frame, in the      |
  |   d290 ware or     |  |Y     |   160 mm side space        | 520
  |   GN 354 (Y) x     | [jaws]  |   +-------+                |
  |   325 (X)          |  ware   |   | d290  |  turntable     |
  |                    |         |   +-------+                |
  +--------------------+---------+---------------------------+
  | front door, double skin, interlocked                      |  35
  +-----------------------------------------------------------+
        X telescope of the Wender: +-450 from shaft centre
```

Levels in the hot column from the floor: plinth 50, oven 50–500, K/H 500–1180, S1 1180–1480, F1
1480–1730, F2 1730–1980. Left column: plinth and lathe 50–600, rack 600–1650, port and dock 1650–1980.
The shaft foot (50–450) carries the drain and rinse seat. A camera in the shaft ceiling looks down into
whatever the Wender carries.

The width is honest for what is inside, and it is not small: 1600 including oven, washer and rack. The
shaft (440 × 520 × 1900 of air) is the price of inverting anywhere; every attempt to put stations on
more than two sides of it, or a rack behind it, failed on the 600 depth (ware is 290 across).

## 2. Mechanism

### 2.1 The rim standard R260 and the three rules of the ware

```
   section through two mated rims                      jaw (top view, one of a pair)
        _____________  flange OD 290, 5 thick          ____________________________
  _____|  ___________| sealing land d252-266          |  straight slot  _  straight |
 | neck | <- OD 266, 14 high: the jaws grip here      |  for GN flange / \  slot    |
 |______|__ shoulder bead OD 278                      |________________/   \________|
    |  bore 250                                          arc pocket R133 over 100 deg
    |  wall, 4 deg taper per side (pots nest)            for the round neck
```

* **Rim spool.** Every round vessel, sleeve and lid carrier ends in the same turned or spun ring: bore
  250, flange OD 290 × 5, below it a neck OD 266 × 14 and a shoulder bead OD 278. The ring is
  laser-welded to the body with a ground fillet (R ≥ 3 inside). The neck is what the machine holds: a
  jaw in the neck holds the vessel positively in both axial directions, so a single vessel can be
  inverted, and the flange faces stay free. The profile is a large Tri-Clamp ferrule; that standard has
  done rim-to-rim sealing in dairies for a century.
* **Gaskets live on interposers only.** Vessels are bare metal. A joint that must be tight has a
  coupler ring (8 thick, moulded platinum-silicone bead on both faces at d 259) or a disc with the same
  rim between the flanges. Dry and frying joints are metal to metal. No vessel carries a seal, a
  bearing, a magnet or a loose part.
* **Interposer rim.** Every disc has the 290 × 8 rim, so a sandwich is always flange / 8 / flange and
  the squeeze travel is known. Mis-stacking shows as a wrong squeeze position (section 9).
* **Base skirt.** Round cans stand on a 6 mm skirt ring d 230 with three notches (drive, drain when
  inverted, angular index); tri-ply base inside the skirt for induction.
* **Flat family.** Bought GN 2/3 multi-layer induction trays ("thermoplates", 354 × 325, 20 / 65 /
  100 deep). Their flange is the GN standard. The jaws carry both geometries (arc pocket for the neck,
  straight slots for the GN long sides; closing stroke 80 per jaw). A GN pair is sealed, when needed,
  by a silicone gasket frame; a round vessel meets a tray through the **transition plate** (GN 2/3
  outline, d 250 hole with bead on both faces).

### 2.2 Wender (lift, reach, roll, two jaw pairs, squeeze)

| Axis | Type | Travel | Force / torque | Notes |
|---|---|---|---|---|
| Z | belt or screw axis behind the rear wall, brake, counterweight | 1750 | 22 kg moved (12 payload + 10 head), 0.8 m/s | mast is Zone N; the arm passes a vertical slot closed by a magnetically held stainless sealing band (rodless-cylinder practice) |
| X | two-stage telescopic slide, stainless, polymer plain bearings, rack drive | ±450 | 100 Nm moment at full reach | in the shaft, Zone S; open profile, washed with the shaft |
| Roll (about Y) | gearmotor in a sealed IP69K housing, hollow shaft, absolute encoder | continuous, 0–40 rpm, ±0.2° | 40 Nm, holding brake | swing circle of the largest inverted set: 400 (two pots, or a GN 65 pair) |
| Jaw pair A | two jaws, one screw with left/right thread | 80 per jaw | 250 N grip | load pins: weighs what it holds to ±5 g |
| Jaw pair B | as A | 80 | 250 N | as A |
| Squeeze | B moves along the stack axis relative to A | 220 | 600 N, force-controlled | sets gasket compression (300–450 N), separates and joins stacks, detects mis-seat by position |

The jaws reach forward (in Y) from the roll head, which sits behind the ware; nothing of the carriage
is above an open vessel. Payload: 12 kg carried upright (the 9.3 L pot is carried only empty or with
its basket, never full), 8 kg inverted.

What the Wender does with these six axes:

* **Carry** any vessel, tray, disc or kit stack between all stations (a move: 7–11 s).
* **Invert a pair**: lower vessel in A, empty vessel upside down in B, squeeze, retract into the shaft,
  roll 180° in 2–4 s, place. Used for transfer, flip, drain, unmould, coat, empty into waste.
* **Tumble** a closed pair (toss salad, coat in flour, oil fries, shake-peel garlic and boiled eggs):
  continuous roll or ±60° at 3 Hz.
* **Partial inversion by weight**: roll to 95–130° and back while the jaw load pins show how much has
  crossed (layering a sauce in thirds, portioning).
* **Stack and unstack** at a station, **clamp a lid** on a vessel for a hot carry, **lift a basket**
  out of its pot and hold it while it drains.
* **X table under the fork**: hold a tray under the K/H fork and travel in X while the quill extrudes
  (paste stripes, rows of dice or filling); pull a tray under a fixed bar (apron rolling).
* **Present** a soiled part to the rinse seat, the shaft camera or the lathe.

### 2.3 K/H: the press column on a hob

```
      ||  quill: Z 300, 5 kN; spindle 20 Nm @ 0-300 rpm, 1.5 Nm @ 6000 rpm;
      ||  hollow (drinking water); bayonet nose with bellows and drip collar
   ___||___   crosshead on two d30 guide columns in the side space (C-frame)
      []      stalk tool, arrives hanging in its lid
  ====[]====  fork: holds the stationary part (sleeve, grid, lid), Z 250 on the
   |  food |  same columns, self-locking screw, 3 load pins (+-2 g, 10 kg)
   |_______|  
  [# # # # ]  disc (grid, ricer, slicer ...)          tip cradle: fork for one
  |         | receiving vessel = rotor                 hat beaker on a roll
  |_________| stands on the turntable ring             actuator at the tier wall
 ==[ring]=====[ring]==  annular turntable: slewing ring ID 270, 20 Nm, 0-900 rpm,
     | glass d260 |     three lugs for the skirt notches, umbrella skirt
     |  coil 3.5kW|     fixed pedestal, pot base rides 1 mm above the glass
  ~~~~~~~~~~~~~~~~~~~~  deck sloped 5 deg to a drain; three load cells under the
                        turntable frame weigh the vessel (+-5 g), outside the press loop
```

Force loop of the press: quill → tool → food → disc → fork → columns → crosshead. The turntable, the
hob and the load cells never see it. 5 kN replaces the 8 kN of the source: staggered grid blades and a
d 90 window need 1–2.5 kN, the ricer 1.2–4 kN [R4]; pork-rind scoring is done by a draw cut, not by
stamping.

Penetrations at K/H: quill (linear plus rotary through the tier ceiling, bellows on the linear stroke,
lip seal with leak-off on the spindle; both above food, so the nose carries a drip collar and the
bellows is an LRU); two guide columns through the ceiling and deck of the side space (outside the food
tier); tip-cradle shaft through the side wall (rotary lip seal, Zone S); turntable ring (labyrinth, no
contact seal, drive below the deck).

### 2.4 Other stations

| Station | Content | Actuators |
|---|---|---|
| **S1** stir hob | glass hob 3.5 kW; light spindle from the tier ceiling (20 Nm, 0–120 rpm) with 60 mm Z to lower and lift the rotating scraper lid; content probe through the lid hub | 2 |
| **F1, F2** flex hobs | 360 × 330 glass field, two oval coils 2 × 1.5 kW, takes a GN 2/3 tray or any round vessel; no moving part; IR and NTC base temperature | 0 |
| **Oven** | bought 45 cm compact combi-steam oven (30–250 °C, steam, grill), mounted sideways so that its mouth faces the shaft; the door is replaced by a motor-driven lift door; one fixed shelf, ware is set down on it | 1 |
| **Dock** at the port | rolling cradle (servo roll, ±185°) into which the transport system pushes a box, a carton or a can carrier; clamp that lifts the box against the collar; shutter finger and vibrator acting on the collar from outside; driven rubber cone for screw caps (6 Nm); 10 kg scale (±1 g) and 300 g cell (±0.05 g) under the receiving beaker; dry, under slight overpressure from filtered room air | 5 |
| **Wash lathe W** | round chamber d 520 × 430, side shutter to the shaft, turntable 0–900 rpm with the skirt lugs and a GN cradle, two fixed jet masts (inside and outside meridian), induction ring 2.5 kW, 3 L sump with 2 kW heater, 5 bar pump | 2 |
| **Drain and rinse seat** (shaft foot) | gasketed funnel seat for R260 and a GN frame; upward fan nozzle on mains cold water; two jaw-rinse nozzles; tempering valve to the drain; 1 mm strainer drawer for solids | valves only |
| **Camera** | shaft ceiling, looks into carried ware; second camera in the lathe | — |

Total motion actuators: Wender 6, K/H 5 (quill Z, spindle, fork Z, turntable, tip cradle), S1 2, dock
5, lathe 2, oven door 1 = **21**. In addition 3 pumps (lathe, drain stalk, detergent), about 10
valves, 5 induction generators, 2 fans.

### 2.5 Ware list (bought / custom)

| Group | Piece | Dimensions | Qty | Make | Used by (share of corpus meals, [E]) |
|---|---|---|---|---|---|
| Cans | pot P, tri-ply | B250 × H110, 5.0 L | 3 | custom (spun, welded rim) | nearly all |
| | tall pot TP | B250 × H190, 9.0 L | 2 | custom | boil, soup, dough, leaves: 45 % |
| | pan PN | B250 × H40 | 3 | custom | pancake, egg, patties: 20 % |
| | hat beaker BK, tri-ply base | B160 × H130, 2.6 L, 45° shoulder to R260 | 3 | custom | dosing, whisking, sauce: 90 % |
| | small hat beaker SB | B90 × H110, 0.7 L | 2 | custom | seasoning, 1 egg white: 60 % |
| | basket BS (perforated 3 mm) | fits P and TP, H100 | 2 | custom | drain, leaf wash, steam: 35 % |
| Sleeves | S160, S90 (with funnel collar), S60 insert | × 160 | 2, 2, 1 | custom | dice, slice, rice, extrude: 60 % |
| | S250 with rasp liner; plain S250 | × 160 | 1, 1 | custom | peel 24 %; springform, roast, ring-build 8 % |
| Discs | coupler ring CR | | 3 | custom, moulded bead | all |
| | grid 10 mm two-tier + comb piston CP90 | window d 90 | 1 + 1 | custom | dice 43 % |
| | ricer / strainer RIC 2.5 mm; coarse die 8 mm | | 1, 1 | custom | mash, garlic, Spätzle, egg strain |
| | slicer SLC (1–8 mm by shim), grater GRT, sickle SKL | clip to the rotor rim | 1, 1, 1 | custom, bought blades | slice 28 %, grate 20 %, carve 5 % |
| | sweep-knife bridge SWK | clips to a vessel rim | 1 | custom | dice, extrude |
| | wedge-and-core WDG | 8 blades, tube d 25 | 1 | custom | apple, tomato, cabbage quarters |
| | rasp floor RSP | etched stainless | 1 | custom | peel |
| | die disc with slide gate DIE (d 70 / d 20 inserts) | | 1 | custom | patties, dumplings, gnocchi 5 % |
| | egg cassette EGG | 6-pocket carousel over one cracker | 1 | custom, goes to D7 washer | eggs 14.5 % |
| | platter disc PLD (flat, R260 rim) | | 2 | custom | unmould, hand-over |
| | dosing collars: orifice turret, vibrated sieve, spout / piece chute | | 3 | custom | all |
| Lids | plain lid | | 4 | custom | |
| | scraper lid SCR250, SCR160 | welded arms, silicone edge | 2, 1 | custom | stir 45 % |
| | kneading lid KNL (roller + scraper) | | 1 | custom | knead 12 % |
| | splash lid with whisk WSK; with blade BLD; small whisk | kits | 3 | custom, bought whisk wires | whip 20 %, purée 6 % |
| Stalks | piston P160 (silicone lip), platen PLG (GN, 300 × 280), can cutter, jar cone | | 4 | custom | |
| GN | tray T65 | 354 × 325 × 65 | 4 | bought (Rieber thermoplate class) | flat food 30 % |
| | sheet T20; braiser T100 with lid | | 2, 1 | bought | bake, flip lid, cold sheet; braise |
| | transition plate TRP; gasket frame; rack; divider lid; trough insert (4 channels) ×2; apron; silicone folders ×3 | | 10 | custom / bought mats | |

**76 pieces of 50 types** (counting the drain stalk of section 4). Cut from the source list: 6 mm grid, zig-zag stamp chopper and its PE
insert, French-press piston, separate strainer disc, cone roller, scraper ring, shredding disc as a
separate part. First candidates for a further cut (each serves under 2 % of meals): sickle, wedge disc,
S60 insert, coarse die. No piece contains a bearing, a seal or a motor. Pieces with hinges or pins:
egg cassette, die gate, dosing collars; these go to the central washer (section 6).

## 3. Ingredient intake and dosing

**The hourglass dock.** The transport system pushes a box (lid already off, see requests) on rails into
the cradle at the port. Above the box position the cradle holds a ware collar; below the collar's
outlet, 5 mm inside its mouth, stands a hat beaker on the scale. The clamp lifts the box rim against
the collar's silicone face (GN 1/9 and 1/6 directly; GN 1/3 through a rectangular funnel collar). The
cradle rolls; box and collar turn over together; the box is now a hopper. Flow is metered by the roll
angle (liquids, pieces), by the shutter (granules) or by the vibrator (powders), closed-loop on the
gain in weight. The cradle rolls back, what did not leave falls back into the box, the transport system
takes the box away. The collar stays for the next box of the same class; the Wender changes it between
classes (dry → wet → allergen change). The Wender moves only the beaker.

| Form | Path | Accuracy, rate [E] | Conf. | Untested |
|---|---|---|---|---|
| Whole produce (potato, onion, apple, carrot) | piece-chute collar, roll to 100–120°, pieces roll out one at a time into the feed sleeve or pot standing on the scale; stop on mass, accept ±1 piece, **scale the recipe to the measured mass** (SM-151) | ±1 piece (±80 g) | M | bridging of large pieces in the d 110 chute; onions with loose skin |
| Long goods (leek, cucumber, carrot, spaghetti) | spout collar with slot; spaghetti slide out lengthwise into the basket in TP; cucumber and leek into S60, which self-aligns them | spaghetti ±15 g | M–L | spaghetti bundles jam; part of a pack of leek |
| Leafy, bulky | whole box turned over into the basket (no metering); surplus returned in a lidded beaker to cold storage (PRP-036) | — | M | part of a head of lettuce is not possible: the head is quartered by the wedge disc and one or more quarters are used |
| Granular (rice, lentils, sugar, salt, frozen peas) | orifice turret (d 3 / 6 / 20 / 50), shutter timed, trim on the scale; Beverloo flow is independent of fill | ±2 % above 50 g; salt d 3: 0.6 g/s, ±0.1 g | H | frozen goods clumped by a thaw cycle |
| Powder (flour, starch, cocoa, breadcrumbs) | vibrated 1.5 mm sieve collar: arch holds, vibration flows (SM-135), 5–15 g/s | ±2 g | M | flour at 60–70 % RH; the dock is kept dry and away from the hot column |
| Seasoning 0.2–5 g | spice boxes are GN 1/9 with their own sifter insert (request X1); tapped by the vibrator into the small beaker on the 300 g cell; several seasonings of one dish into the same beaker | ±0.1 g or 10 % | M | oily or caking spice mixes; pepper is bought ground |
| Liquid: water | valve and flow meter through the hollow quill at K/H (10 mL–5 L, ±3 %); second outlet at the dock | ±3 % | H | — |
| Liquid: oil, vinegar, milk, cream, stock, wine | the opened carton or bottle stands in a box-size carrier; cap off by the driven cone (clamp presses the cap into the cone, 6 Nm); spout collar seals on the neck; pour by roll angle on the scale | ±3 g | M | glugging; tethered caps; cartons without a screw cap need the can cutter |
| Viscous paste (mustard, tomato paste, honey, quark, jam) | from a **paste cartridge**: S60 barrel with free piston and nozzle disc, kept cold like a box; at K/H the quill pushes the piston (2.8 mL per mm, ±1.5 g); stripes onto a tray while the Wender moves it in X | ±2 g | M | the cartridge must be filled: requested from ingestion (tube or jar decanted once); fallback in the cell: tube crushed nozzle-down in S90 by the quill (about 10 % left), jar turned over a funnel for minutes (L) |
| Solid fat (butter, lard), firm cheese, tofu, bacon | diced once when the pack is opened (grid stack), then stored and dosed as pieces by mass (SM-147) | ±1 cube (10 g) | H | cubes fuse above 8 °C |
| Raw meat: mince, cubes, strips | the opened tray or box is turned over in the dock onto a tray or pot through the piece chute; mince falls as a block; residue chased by the first recipe liquid | residue 3–8 % on the pack | M | absorbent pad falling with the meat (camera check; request: pad-free packs) |
| Raw meat: slices lying together | **cold sheet**: a T20 sheet kept at −18 °C is pressed on the pack by the squeeze axis for 3 s, lifts the top slice frozen to its underside, is rolled over and set on F1; a 1 s induction pulse (about 2 kJ) melts the film; the slice lies loose and flat on the sheet and is passed on by a clamshell flip | 40 s per slice | **L–M** | fatty and dry surfaces; whether exactly one slice comes up; this is the weakest dosing path (W3) |
| Egg | box with a 2 × 3 egg tray insert; the egg cassette is put on the box as its collar; one roll moves six eggs into the cassette pockets (5 mm drop); unused eggs go back the same way | count exact | M | eggs of mixed size; a cracked egg in the box |
| Frozen loose | as granular, d 50 orifice; blocks (spinach) as pieces | ±10 % | H | — |
| Stowed can | not through the dock: carried by the Wender in a **can cup** (R260 disc with rubber cone) to K/H; the turntable turns the can under the cutter stalk (three wheels at three radii, the lowest engages), quill force 300 N, lid held by a magnet; cup + coupler + pot are inverted; chase with recipe liquid | 60 s | M | dented cans, ring-pull lids (cut the same way), beans packed solid |
| Stowed jar (twist-off) | jar in the can cup on the turntable, quill presses the jar cone on the lid (300 N), turntable unscrews (3–6 Nm); pourable contents as for the can; pickles through the basket | 40 s | M | vacuum-tight lids above 6 Nm; pasty contents (see paste) |
| Carton, tub | carton as liquid above; tub (quark, yoghurt) with peel lid: lid cut out by the can cutter, contents as paste fallback | | L–M | foil lids; tubs are better decanted at ingestion |
| Vacuum pack, MAP tray | **not opened by this cell.** Request: the package-opening mechanism of ingestion delivers the opened pack in a carrier to the port just in time (DEC-3). | — | — | shared with all candidates |

Moves: a dosed dry or liquid ingredient costs no Wender move; the beaker costs one move to its
destination and one tip-in. A reference meal has 12–20 dosed ingredients in 5–8 beaker loads.

## 4. Operation table

Time is for the 4-person quantity. "Moves" are Wender pick-and-place cycles.

| Operation | Mechanism and sequence | Time | Moves | Conf. | Untested |
|---|---|---|---|---|---|
| **Transfer** vessel to vessel (UO-03) | empty vessel upside down in B over the full one in A, coupler between if wet, squeeze, roll, place; drip 5 s | 12 s | 1–2 | H | residue of sticky masses: taper and a knock with the squeeze axis; batter and mince estimated 4–8 %, at the PRP-013 limit |
| **Merge / staged addition** (C4) | beaker into the tip cradle at K/H, rolled by gain in weight on the turntable load cells; from trays: tray brought to K/H | 15 s | 2 | M | splash of a 60 mm fall into hot fat; steam on the beaker |
| **Flip pieces and whole-pan items** (FLP, 12.9 %) | second pan or tray preheated on a free hob, picked up upside down, squeezed metal to metal onto the first, rolled 180° in 2 s, set on a hob; drop 25–65 | 20 s | 2 | M–H | fat above 30 mL runs out of the joint into the shaft (drain first or use the gasket frame); pancake sticking to the first pan; mass of a T65 pair (7 kg) |
| **Assemble layered dishes** (LAY, TOP, SPR) | tray on F1 or held under the K/H fork; sauces by partial inversion by weight, pastes as stripes from the cartridge, cheese through a coarse sprinkle collar during a shaken partial inversion | 30–60 s per layer | 2 per layer | M | evenness ±20 %; dry lasagne sheets land shingled (L–M) |
| **Assemble open-hand food** (ASM) | burger and layered cold dishes by ring-build in S160 on a platter disc (bun, patty by flip, sauce stripe, sliced items by tip-in), sleeve lifted by the fork; **taco, filled sandwich, wrap, hot dog: not possible**, served as components | 3 min | 8 | L–M / no | the concept cannot place a single piece in a given orientation |
| **Carve boneless roast** (CAR) | roast on end in S250 under a 1.5 kg follower in the fork; sickle on the rim of the pan turning at 40–60 rpm; fork lowers 2–15 mm per turn; slices fall flat into the warm pan | 2 min | 4 | M | hot braised meat may tear; getting the roast into the sleeve on end (inversion from its roasting pot, axis uncontrolled) |
| Carve bone-in poultry | not possible; parts are cooked and served as parts | — | — | no | — |
| **Unmould** (UNM, 4.4 %) | pot greased by spin (melted butter, 200 rpm) and floured by tumbling; after baking and cooling a 3 s induction pulse frees the wall; platter disc on top, roll; the 4° taper releases | 30 s | 2 | M–H | sticking, as for a cook |
| **Score** (SCO) | roast or loaf in its tray held by the Wender, drawn in X under a depth-stopped blade comb held in the fork | 20 s | 2 | M | rind toughness; proved dough dragging |
| **Stuff rigid cavities** (STU) | filling from S90 with a nozzle disc by quill stroke into cavities standing in a cup rack | | | L | **loading the cavities into the rack upright is not possible without a pick-up**; halves lying in a tray land cut face up or down at random |
| **Wrap, roll Rouladen** (WRP, RLT) | slice on the apron in a T65 (from the cold sheet by flip); mustard stripe and a row of diced bacon, onion and gherkin laid while the Wender moves the tray in X under the fork; the Wender then engages the apron hem on a fixed bar in the shaft wall and travels 250 in X: the apron is drawn over itself, the roll runs off its end into a channel of the trough insert in the same tray; two lanes at once | 3 min per pair | 12 per pair | **M–L** | every step: slice flat, roll tight, roll drops into the channel |
| **Secure Rouladen** | no tying: the four-channel trough insert holds the rolls shut; seared in the insert, the set is flipped into a second trough tray, braised lidded in the oven | — | 2 | M | two-hour braise of an untied roll (catalogue: highest-priority test) |
| **Bread** (BRD) | cutlets flattened between folders under the GN platen (1.5 kN); three trays: flour, egg, crumbs; the set is moved by clamshell flips over the GN rack, each flip re-beds both faces; two cutlets per tray | 90 s per pair | 8 | M | coverage at the edges; crumbs mixed with egg are discarded after each meal |
| **Form patties** (FRB) | mass kneaded in a pot; inverted into S160 on the die disc; piston extrudes a d 70 log; sweep knife on the rim of the pan turning below cuts pucks of 25 mm (100 g ±10 %); the pan indexes 90°; four per pan | 12 in 4 min | 6 | M–H | smear on the die; sticking to the knife |
| **Form dumplings, gnocchi** (FRK, FRM) | as patties with the d 20–50 insert, pieces drop into simmering water or onto a floured tray; rounding by tumbling in a floured pair | 3 min | 4 | M | shape is a rough cylinder; Schupfnudeln not tapered |
| **Roll out dough** (ROL, SHD) | ball on a T20 between oiled folders, GN platen presses in three steps with 30 s rests to 3–6 mm | 3 min | 4 | M | 1 kg of yeast dough needs 2–6 kN over 0.1 m²: at the limit of the quill; springback; thickness ±1 |
| Line a tin | dough pressed into the pot or tray by the platen; edge not raised | | | L–M | raised rim for quiche |
| **Knead** (KND, KNM) | pot on the turntable at 60–100 rpm against the kneading lid held by the fork (Ankarsrum principle) | 8 min | 2 | H | 1.6 kg in a 9 L tall pot: torque 20 Nm at the limit |
| **Peel potato, carrot, celeriac** (PLP, PLH) | S250 rasp sleeve in the fork, rasp floor on the turntable at 250 rpm, water from the quill, slurry through the 3 mm gap into a pot below, which is emptied at the seat through the strainer | 1.5 kg in 2 min | 5 | M | loss 15–25 % against the 25 % limit; eyes; long carrots |
| Peel onion, garlic (PLA) | **onion bought peeled** (SM-242); the undersized-die idea of the source is not carried (no evidence). Garlic: unpeeled through the ricer with the comb piston, or shake-peel in a tumbled pair | | | buy / H | MEAL-009 is not met |
| Core, trim (COR, TRE) | apple, pear, tomato, cabbage quarters through the wedge-and-core disc; long goods through S60, first and last cut to a waste beaker; beans, sprouts, peppers bought trimmed or frozen | | | M / buy | orientation of the fruit on the disc (funnel cup only) |
| **Dice, sticks** (DIC, JUL) | S90 on the two-tier 10 mm grid, comb piston; sweep knife on the rim of the turning receiving pot sets the length (10 mm/s at 60 rpm); without the knife: sticks | 1.5 kg in 90 s | 4 | H | one pitch only; fine dice by the blade stalk (bruises) |
| **Slice, grate** (SLI, GRC, GRF) | disc clipped to the rim of the turning receiving vessel, stationary feed sleeve, piston as pusher | 1 kg in 60 s | 4 | H | disc balance at 400 rpm |
| Mince, chop herbs, purée (MIN, CHH, PUR) | blade stalk through the splash lid at up to 6000 rpm in the beaker, or in the soup pot on its hob | 20–60 s | 2 | H | herbs bruise; small quantities climb the wall |
| **Crack eggs** (CRK), separate (SEP) | egg cassette on a beaker in the fork: quill indexes the carousel 60° and one stroke works the cracker; shells to the moat; slotted cup retains the yolk. Mixtures are whisked and then inverted through the ricer disc, which holds shell back | 12 s per egg | 5 | M | shell fragments; yolk intact for fried egg; 12 eggs in 3 min is just met |
| **Mash** (MSH) | potatoes boiled in the basket; basket inverted into S160 on the ricer over the warm pot with butter and milk on K/H; piston; scraper lid folds at 20 rpm | 2 min | 5 | H | skins on the ricer when boiled skin-on |
| **Whip, emulsify, cream** (WHP, EMU, CRM) | whisk kit in a beaker, off-centre, up to 1000 rpm; one egg white in the small beaker; hollandaise at 65 °C on the K/H hob | 2–5 min | 2 | H | — |
| Fold (FLD) | scraper lid at 10–20 rpm | 1 min | 2 | M | volume loss |
| **Toss, coat, marinate** (TOS) | closed pair tumbled 4 turns | 15 s | 2 | H | — |
| **Wash and dry leaves** (WLF) | leaves in the basket in a tall pot on K/H, water in, turntable reverses ±90° for 30 s, basket lifted, water out by the drain stalk, spin at 600–900 rpm | 3 min | 4 | M–H | imbalance |
| **Drain** (DRN, 22.6 %) | default: the food is boiled in the basket; the Wender lifts the basket and holds it 20 s over its pot. The water stays on the hob and is pumped out later through the **drain stalk** (dip tube on the quill, hot-rated pump in Zone N, 4 L/min) or, for pots up to 3.5 L of water, carried with a clamped lid to the seat and inverted. Three-layer inversion (SM-157) only below 3 L | 40 s | 2 | H | the 9 L pot stands only on K/H |
| Squeeze (SQZ) | grated potato, spinach: piston P160 on the ricer disc, 2 kN | 30 s | 3 | H | — |
| **Stir, scrape, sauté** (STC, SAU) | rotating scraper lid on S1; on K/H the pot turns against a scraper lid held by the fork. F1 and F2 do not stir: food there is turned by clamshell flip or tumbled | — | 0 | H / deviation | COK-008 is met at two of four positions only |
| Deglaze, baste, glaze (DGL, BST, GLZ) | deglaze by tip-in; baste by flipping the piece in its own fat; glaze as a paste stripe | | 2 | M | true basting is not possible |
| Spin-spread batter (PTH) | pan on the K/H turntable, batter tipped in by weight, 150 rpm for 2 s | 10 s | 0 | M–H | — |
| Proof (PRF) | dough in its lidded pot on F2 held at 32 °C | | 1 | H | — |

## 5. Benchmark walk-throughs

Conventions: t in minutes from the order; "→" a Wender move; "flip" a rim-to-rim inversion; "tip" a
tip-in at K/H; onions and garlic arrive peeled (section 4.2 of the catalogue, assumption 1); opened
vacuum or MAP packs arrive from ingestion (request R3). Moves are counted per step in brackets. A move
averages 9 s, so 60 moves are 9 min of carriage time. Limits are PERF-001: 1.15 × T_ref + 10 min.

### B1 Rinderrouladen, Rotkohl, Salzkartoffeln (4 persons) — **adapted**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | Red cabbage head (1 kg) tipped from its box into S250 over the slicer disc clipped on a tall pot; follower; 300 rpm; shredded whole, **core included** | K/H; TP1, S250, SLC | 5 |
| 3 | Apple through the wedge-and-core disc, then with one onion through the 10 mm grid into a beaker | K/H; WDG, S90, grid, CP90, SWK, BK1 | 8 |
| 6 | Lard cubes, vinegar, wine, sugar, salt, spices dosed at the dock; TP1 to S1, scraper lid; all tipped in cold (no separate sweating: reordered) ; simmer 90 min, lid turning at 10 rpm | dock, S1; BK2, SB1, SCR250 | 6 |
| 8 | Four slices lifted one by one with the cold sheet, freed by the induction pulse on F1, flipped onto the apron in the rolling tray (two lanes) | F1; T20c, T65a + apron | 4 × 4 |
| 12 | Mustard stripe, then a row of bacon cubes, onion dice and gherkin dice (gherkins from the jar through the basket and the grid) laid while the tray travels under the fork | K/H; cartridge, S90, BK3 | 8 |
| 16 | Apron hem hooked on the bar, 250 mm X stroke, two rolls drop into channels 1–2 of the trough insert; repeat for slices 3–4; camera check, a loose roll is rolled again | shaft; T65a, trough A | 6 |
| 22 | Rolling tray with trough on F1, 15 mL oil, 220 °C, 3 min; second trough tray preheated on F2; flip; 3 min | F1, F2; T65b, trough B | 4 |
| 30 | Tray to K/H: tomato paste, wine, stock tipped in (fork load pins); braiser lid on; oven 160 °C, 100 min | K/H, oven; BK4 | 5 |
| 95 | 1 kg potatoes tipped into the rasp sleeve, peeled 2 min, slurry pot emptied at the seat; potatoes through the wedge disc (quarters) into the basket | K/H; S250r, RSP, P1, WDG, BS1 | 9 |
| 105 | Basket into P2 with 1.5 L salted water on K/H; boil 20 min | K/H; P2 | 2 |
| 130 | Tray out of the oven; braising liquid poured off by partial inversion through the GN rack into a beaker; beaker on S1 after the cabbage pot moved to F2; flour slurry tipped in; SCR160 stirs 5 min | S1, F2; BK5, SCR160 | 7 |
| 128 | Basket lifted, 20 s drip, set into a warm lidded pot on F1; potato water out by the drain stalk | K/H; P3 | 3 |
| 140 | Hand-over: trough tray, cabbage pot, potato basket, sauce beaker to the serving port | | 4 |

Elapsed **about 145 min** plus serving (limit for the corpus menu with dumplings 183). Moves **about
83**. Soiled: 31 pieces (2 trough trays and inserts, apron, cold sheet, braiser lid, TP, 3 P, 5 BK, SB,
BS, S250, S250r, RSP, SLC, WDG, grid set, S90, 2 scraper lids, cartridge nozzle, 2 collars, 2 couplers).
Adapted because: untied rolls held by channels, diced instead of sliced bacon, cabbage core shredded in,
onions of the cabbage not sweated first. Three steps are L–M and chained (slice pick-up, rolling, untied
braise); first-time success of the whole chain is guessed at 60–70 %.

### B2 Wiener Schnitzel, Bratkartoffeln, Gurkensalat (4) — **yes, tests pending**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | 1 kg small potatoes rasp-peeled, into the basket, boiled 18 min in P1 | K/H; S250r, RSP, P1, BS1, P2 (slurry) | 9 |
| 3 | Cucumber through S60 over the slicer (2 mm) into BK1; vinegar, oil, sugar, salt, frozen dill, sour cream dosed into BK2; tipped onto the slices at the dock; pair tumbled 4 turns; rests | K/H (2 min, potatoes moved to S1 meanwhile), dock; BK1, BK2, S60, SLC, SB1 | 8 |
| 8 | Onion through the grid; bacon cubes dosed | K/H; grid set, BK3 | 5 |
| 12 | Flour on T20a (sieve collar), two eggs cracked, whisked, strained, poured on T20b; crumbs on T65c | dock, K/H; EGG, SB2, WSKs, RIC | 9 |
| 22 | Potatoes: basket lifted, cold flush at the seat 60 s, sliced 5 mm on the slicer into P3 (crumbling expected: 10–15 % broken, M) | K/H; SLC, S160 | 5 |
| 25 | Slices and bacon into T65a on F1, 170 °C, 20 min; flipped into T100 (preheated on S1) at 30, 35, 40 min, onion added at 35 (tip at K/H) | F1, S1; T65a, T100 | 8 |
| 28 | Cutlets (bought thin; otherwise platen 1.5 kN between folders) tipped from the opened pack onto the flour tray, shaken flat, camera | dock; T20a | 3 |
| 30 | Breading by flipping: flour → rack → egg → rack → crumb, platen press 40 N; two cutlets per pass, two passes | shaft, K/H; rack, T20b, T65c, PLG | 2 × 9 |
| 36 | T65b on F2 with 100 mL clarified butter at 165 °C; cutlets flipped in from the crumb tray (gasket frame in the joint); 3 min; flipped onto the hot rack-tray T65d (fat drains through the rack), 3 min in T65d; second pair | F2; T65b, T65d, gasket frame | 2 × 4 |
| 50 | Hand-over | | 4 |

Elapsed **about 52 min** (limit 67). Moves **about 77**. Soiled: 33 pieces; **all seven GN trays are
in use**, so this meal defines the tray stock. Untested: cutlets landing flat from the pack, crumb
coverage at the edges, slicing warm boiled potatoes, 100 mL of hot fat in a flipped pair (the gasket
frame is silicone, 230 °C rated; the fat is poured through the rack into a pot before the second flip).

### B3 Frikadellen, Kartoffelpüree, Erbsen-Möhren (4) — **yes**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | 800 g potatoes rasp-peeled, basket, boil 22 min in P1 on S1 | K/H then S1; S250r, RSP, BS1, P1, P2 | 9 |
| 4 | Carrots rasp-peeled with the potatoes' second load, through the grid (10 mm) into BS2 | K/H; grid set, S90 | 5 |
| 7 | Stale roll soaked in a beaker, pressed on the ricer disc by P160; onion through the grid; egg cracked; mustard from the cartridge; mince tipped from its pack into P3; all tipped in; kneading lid, 80 rpm, 3 min | dock, K/H; BK1, BK2, EGG, P3, KNL, RIC, P160 | 14 |
| 14 | P3 inverted into S160 on the die disc; pan PN1 on the turntable; 8 pucks of 100 g cut by the sweep knife, four per pan (PN1, PN2), the pan indexing 90° | K/H; S160, DIE, SWK, PN1, PN2 | 8 |
| 18 | PN1 on K/H, PN2 on F1, 160 °C, 5 min; PN3 preheated on F2; flip PN1 → PN3, then PN2 → PN1 (rinsed at the seat, reheated 60 s); 5 min; core 72 °C by probe through the lid | K/H, F1, F2; PN3 | 8 |
| 22 | Carrots in BS2 in P4 with 0.4 L water, butter, sugar on F2 (after PN3 left), 8 min; frozen peas added through the dock into the basket at 27 | F2, dock; P4, BS2 | 4 |
| 24 | Potatoes: basket lifted; P1 water out (lidded carry to the seat); butter and milk warmed in P1 on K/H; basket inverted into S160 on the ricer over P1; P160; SCR250 folds 1 min | K/H; S160b, RIC, SCR250 | 9 |
| 33 | Hand-over | | 4 |

Elapsed **about 37 min** plus serving: **at the 50 min limit with little margin**; K/H is occupied
without pause from minute 0 to 28. Moves **about 61**. Soiled: 28 pieces. The die disc and the mince
pot are class R and are rinsed at the seat before the ricer job; the ricer disc is used first for the
bread (RTE), and a second instance is not in the kit: the mash uses the same disc after a seat rinse and
a lathe cycle of 4 min, or the order is reversed (mash first, kept warm). This is a real scheduling
constraint of the single-instance discs.

### B4 Spaghetti Bolognese with grated cheese (4) — **yes**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | Carrot and celeriac rasp-peeled; with onion through the grid into BK1; garlic unpeeled through the ricer | K/H; S250r, RSP, grid set, RIC, BK1 | 10 |
| 6 | P1 on K/H: oil, mince tipped from the pack, seared 4 min, pot turning against the scraper lid; vegetables tipped in, 5 min | K/H; P1, SCR250 | 4 |
| 16 | Tomato paste (cartridge), wine and stock tipped in. P1 moves to S1. The tin of tomatoes is opened on the now free turntable; it cannot be inverted onto the full pot (C4), so it is inverted into a beaker and that is tipped in at S1's neighbour K/H: P1 returns for 20 s | K/H, S1; can cup, BK2 | 9 |
| 22 | Simmer 50 min on S1, scraper lid 10 rpm | S1 | 0 |
| 25 | Parmesan block through S90 on the grater disc into the small beaker | K/H; GRT, S90, SB | 4 |
| 45 | TP1 with 4 L water on K/H, boils at 55; 400 g spaghetti slid into the basket at the dock, basket lowered in; 10 min | K/H, dock; TP1, BS1 | 3 |
| 66 | Basket lifted, 20 s drip; basket inverted into an empty warm pot P2; 100 mL pasta water kept in the tall pot for the sauce (drain stalk stops by weight) | shaft, K/H; P2 | 4 |
| 70 | Hand-over; pasta water out by the drain stalk | | 4 |

Elapsed **about 72 min** (limit 96). Moves **about 38**. Soiled: 19 pieces. The walk-through exposes
C4 plainly: every one of the five additions to the sauce pot is a tip-in, and the tinned tomatoes need
a beaker in between.

### B5 Pizza from flour, two trays — **yes, tests pending**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | 500 g flour, salt, sugar, dry yeast dosed into TP1 on the dock scale; water 320 mL and oil at K/H; kneading lid, 80 rpm, 8 min | dock, K/H; TP1, KNL, BK1 | 5 |
| 10 | Lid on, F2 at 32 °C, 60 min | F2 | 2 |
| 15 | Tinned tomatoes opened, blade stalk 10 s with salt and oregano in BK2; mozzarella diced through the grid into BK3; salami sliced on the slicer into BK4 | K/H; can cup, BLD, grid set, SLC, S90 | 12 |
| 70 | Dough inverted into S160 on the die disc (gate open d 70), extruded, cut in two by weight (fork load pins) onto two oiled folders on T20a and T20b | K/H; S160, DIE | 6 |
| 74 | Each sheet: folder closed, GN platen in three steps to 5 mm; top folder peeled by the Wender gripping its spine clip against the fork | K/H; PLG, folders | 6 |
| 80 | Sauce as six stripes (beaker in the tip cradle, tray travelling in X), spread by one light platen stroke through a folder; cheese and salami from a coarse sprinkle collar in a shaken partial inversion through the transition plate | K/H, shaft; TRP, collar | 8 |
| 86 | Oven 250 °C, both sheets on two levels (second shelf) or in sequence, 10 min each | oven | 4 |
| 100 | Hand-over on the sheets (the pizza bakes on the lower folder or directly on the oiled sheet) | | 2 |

Elapsed **about 100–110 min** (T_ref 90, limit 113). Moves **about 45**. Soiled: 20 pieces. Untested:
sheeting 500 g of proved dough to 5 mm with 5 kN (springback; expected 5–7 mm and a rounded rectangle
of about 280 × 300), peeling the folder, evenness of toppings (±30 % allowed). The base is rectangular
and tray-baked, not a round stone-baked pizza; the corpus counts tray pizza as the home form.

### B6 Gemüseeintopf from whole vegetables (6 persons) — **yes**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | Carrots, parsnip, potatoes, celeriac half (1.6 kg together) rasp-peeled in two loads of 2 min | K/H; S250r, RSP, P1 | 8 |
| 6 | Leek through S60 on the slicer (first and last cut to the waste beaker); tomatoes through the wedge disc; frozen cut beans and peas dosed (whole beans are not trimmed: bought cut) | K/H, dock; S60, SLC, WDG, BK1, BK2 | 8 |
| 10 | Peeled roots through the grid in four loads into TP1 (it is the rotor and the soup pot) | K/H; grid set, S90, TP1 | 4 |
| 15 | Oil; 5 min sauté with the pot turning against the scraper lid; 2.5 L stock from the quill and the dock; remaining vegetables tipped in; simmer 25 min | K/H; SCR250 | 4 |
| 35 | Frozen parsley tipped in at 40; seasoning beaker | | 2 |
| 42 | Hand-over in TP1 (8 kg: carried upright with a clamped lid) | | 2 |

Elapsed **about 45 min** (limit 60 for six). Moves **about 28**. Soiled: 15 pieces. The best case of
the concept: the receiving vessel of the dicer is the cooking pot, the food is never transferred.

### B7 Steak, oven fries, mixed salad with vinaigrette (2 persons) — **yes**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | 500 g potatoes rasp-peeled; pushed whole through the grid without the sweep knife: 10 mm sticks; rinsed and spun in the basket (600 rpm, 20 s); 10 mL oil and salt; pair tumbled; emptied through the transition plate onto T20a | K/H, shaft; S250r, RSP, grid set, BS1, P1, P2, TRP | 14 |
| 10 | Oven (preheated from t = 0) 220 °C hot air, 25 min; at 22 min the sheet is flipped onto T20b and returned | oven | 5 |
| 12 | Lettuce quarter (wedge disc in S250) into BS2 in TP1: water, ±90° agitation 30 s, basket lifted, spun at 700 rpm | K/H; WDG, S250, TP1, BS2 | 7 |
| 18 | Cucumber and radish on the slicer, carrot on the grater, tomato through the wedge disc, all into P3; raw pepper: bought as cored strips or left out (W4) | K/H; SLC, GRT, S60, S90, P3 | 8 |
| 24 | Vinaigrette: oil, vinegar, mustard, salt, pepper in the small beaker, small whisk 20 s | dock, K/H; SB, WSKs | 3 |
| 27 | Steaks tipped from the opened pack onto T65a preheated to 250 °C on F1 (15 mL oil); 2.5 min; T65b preheated on F2; flip; butter cube and thyme tipped in; 2 min; flipped once more to coat; probe 54 °C; rests 5 min lidded on F2 at 55 °C | F1, F2; T65a, T65b | 7 |
| 36 | Leaves into P3, dressing tipped in, pair P3 + P1 tumbled 4 turns | shaft | 4 |
| 38 | Hand-over; the steaks are not carved | | 4 |

Elapsed **about 40 min** (corpus menu with baked potato: limit 79). Moves **about 52**. Soiled: 26
pieces for two persons. Basting is replaced by flipping in butter (adapted in a small way, not counted).

### B8 Pfannkuchen, 8 pieces — **yes**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | 250 g flour (sieve collar), salt, sugar into BK1; 3 eggs cracked into BK2, whisked, inverted through the ricer disc onto the flour; 500 mL milk from the dock; whisk kit 40 s | dock, K/H; BK1, BK2, EGG, RIC, WSK | 9 |
| 5 | Batter rests 20 min in the tip cradle; pans PN1–PN3 preheat on K/H, S1, F1 | | 3 |
| 25 | Cycle per pancake: butter cube into PN on K/H; 100 mL batter tipped by weight; 150 rpm for 2 s; 80 s at 190 °C; hot empty pan brought upside down from S1, squeezed on, roll, the pair's lower pan set on S1 for side two (60 s); the freed pan returns to K/H. A finished pancake is flipped onto the stack on a platter disc held warm on F1 | K/H, S1, F1; PLD | 8 × 5 |
| 47 | Hand-over of the stack | | 1 |

Elapsed **about 48 min** (limit 50). About 2.7 min per pancake with two pans in rotation and the third
as the turning partner. Moves **about 53**. Soiled: 10 pieces. Untested: release from the first pan (bare tri-ply sticks; a seasoned carbon-steel or
ceramic-coated pan is needed, which the lathe and the induction flash tolerate but which adds a ware
material), and batter running into the rim joint.

### B9 Chicken curry with rice (4) — **yes**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | 300 g rice rinsed in the basket under the quill, inverted into P1 with 600 mL water and salt; lid; F1: boil, then 90 °C, 15 min, boil-dry watched by base temperature | K/H, F1; BS1, P1 | 5 |
| 4 | Onion through the grid; garlic through the ricer; ginger as a frozen puck; pepper as bought frozen strips | K/H; grid set, RIC, BK1 | 6 |
| 9 | P2 on K/H: oil, onion tipped, 4 min turning against the scraper lid; curry paste (cartridge) 1 min; chicken cubes (bought cut) tipped from the pack, 4 min | K/H; P2, SCR250 | 5 |
| 19 | Coconut milk: can opened after P2 has moved to S1; inverted into BK2; P2 back for the tip-in with stock, pepper strips, sugar, salt; simmer 15 min on S1, scraper lid | K/H, S1; can cup, BK2, SB | 9 |
| 36 | Lime juice omitted or bottled; hand-over of P1 and P2 | | 3 |

Elapsed **about 38 min** (corpus 40–50; limit 56–67). Moves **about 28**. Soiled: 14 pieces. Again two
pot shuttles between S1 and K/H only because the can opener and the tip cradle live at K/H.

### B10 Lasagne, béchamel from scratch — **yes, one test pending (sheets)**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | Bolognese as B4 without pasta, 45 min simmer on S1 | K/H, S1; P1 … | 24 |
| 25 | Béchamel by the cold-start method: 50 g butter cubes, 50 g flour, 700 mL cold milk, nutmeg, salt in P2; whisk kit 20 s; then on K/H at 95 °C with the pot turning against the scraper lid, 8 min | dock, K/H; P2, WSK, SCR250b | 6 |
| 35 | Cheese: block on the grater into BK; mozzarella through the grid | K/H (béchamel to F1 to hold); GRT, grid set | 8 |
| 50 | Layering in T65a, held by the Wender: sauce by partial inversion of P1 through the transition plate, a third by weight each time; béchamel likewise; **dry sheets**: the sheet box in the dock with the slot collar over the tray on the dock scale, four sheets slid out by angle and vibration, landing shingled; the tray is jogged in X; camera checks coverage; three rounds; cheese from the sprinkle collar | shaft, dock; T65a, TRP | 18 |
| 62 | Oven 190 °C, 40 min; rest 15 min | oven | 2 |
| 118 | Hand-over in the tray (cut by the serving module) | | 1 |

Elapsed **about 120 min** (limit 148). Moves **about 59**. Soiled: 24 pieces. Untested and rated L–M:
laying dry sheets as a closed layer. If it fails, the fallback is fresh sheet pasta bought in tray
size, turned out of its pack by a flip with the paper interleaf staying on top (not solved).

### B11 Rührkuchen in a tin, unmoulded — **yes**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | Tin = pot P1: 10 g butter melted on K/H, spun at 200 rpm; 20 g flour, lid clamped, tumbled, surplus inverted into the waste at the seat | K/H, shaft; P1, lid | 5 |
| 3 | 250 g butter cubes and 200 g sugar in TP1 on K/H at 28 °C, whisk kit (flat beater wires) 4 min; 4 eggs cracked into BK1, tipped in one by one; flour and baking powder through the sieve collar into BK2, tipped in in three parts with milk, 60 rpm | K/H, dock; TP1, WSK, EGG, BK1, BK2 | 12 |
| 14 | TP1 inverted onto P1, 20 s drip, two knocks with the squeeze axis (residue guessed 6 %, limit 8 %) | shaft; coupler | 2 |
| 15 | Oven 175 °C, 60 min; doneness by core probe 96 °C | oven | 2 |
| 76 | Cools 20 min on the rack position; 3 s induction pulse on F1; platter disc on top, flip, pot lifted off; camera checks the surface | F1, shaft; PLD | 5 |
| 100 | Hand-over on the platter disc | | 1 |

Elapsed **about 100 min** (limit 125). Moves **about 27**. Soiled: 9 pieces. The cake is a round of
d 245 × 55 with a 4° taper, not a loaf or a Gugelhupf.

### B12 Scrambled eggs from shell eggs and toast, 1 person — **yes, at a high cleaning price**

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | Egg box into the dock with the egg cassette as collar; one roll; cassette to a beaker in the K/H fork; two eggs cracked (carousel indexes twice); cassette back on the box, roll, four eggs return | dock, K/H; EGG, BK1 | 6 |
| 2 | Milk 20 mL, salt; small whisk 10 s in BK1; the shaft camera looks for shell (the 110 mL film is 5 mm deep in the beaker) | K/H; WSKs | 3 |
| 3 | Two slices of toast slid from their pack onto T20a on F1 at 200 °C; 90 s; flip onto T20b; 60 s | dock, F1; T20a, T20b | 5 |
| 4 | BK1 (tri-ply base) on S1 with a butter cube, 110 °C, SCR160 at 40 rpm, 2.5 min, ended by base temperature and the torque of the scraper | S1; SCR160 | 3 |
| 8 | Chives (frozen chopped) into the beaker; hand-over | | 3 |

Elapsed **about 9 min** (limit 17). Moves **about 20**. Soiled: 8 pieces including the egg cassette,
which goes to the central washer. About 6 L of water and 12 min of lathe time for 110 mL of egg: the
minimum-quantity case works but is expensive.

### Summary of the benchmarks

| | Result | Elapsed min | Limit | Moves | Pieces soiled |
|---|---|---|---|---|---|
| B1 | adapted | 145 | 183 | 83 | 31 |
| B2 | yes (tests) | 52 | 67 | 77 | 33 |
| B3 | yes | 37 | 50 | 61 | 28 |
| B4 | yes | 72 | 96 | 38 | 19 |
| B5 | yes (tests) | 105 | 113 | 45 | 20 |
| B6 | yes | 45 | 60 | 28 | 15 |
| B7 | yes | 40 | 79 | 52 | 26 |
| B8 | yes | 48 | 50 | 53 | 10 |
| B9 | yes | 38 | 56 | 28 | 14 |
| B10 | yes (test) | 120 | 148 | 59 | 24 |
| B11 | yes | 100 | 125 | 27 | 9 |
| B12 | yes | 9 | 17 | 20 | 8 |

Mean 48 moves per meal (range 20–83). The source's estimate for the same concept was 60–90; the
difference comes from C1 and C3. Elapsed times assume no retry; B3 and B8 have no margin.

## 6. Cleaning

### 6.1 Principle and zones

No fixed surface of the cell is meant to touch food. Zone F is the ware (76 pieces, about 9 m² in
total, about 3 m² soiled per reference meal). The only fixed Zone F item is the drinking-water outlet
in the quill nose. Everything else inside the cabinet is Zone S, and there is much of it: **about
12 m²** (shaft 3.7, four hob tiers 5.2, dock 0.8, lathe chamber 1.1, oven cavity 1.3). The catalogue's
claim "the machine around the stacks stays clean" holds for the press work (closed stacks) and for
inversions with a gasket; it does not hold for hot frying flips (fat at the metal joint), for tip-ins,
for open pots under a scraper lid, or for the shaft under any leaking joint.

### 6.2 Ware: rinse seat, wash lathe, induction flash

1. **Cold rinse within minutes** (catalogue rule R11). On its way from use every class R or sticky piece
   is held upside down on the rinse seat: mains cold water, fan nozzle, 6 s, 0.4 L. Solids stay on the
   1 mm strainer drawer (see 6.5).
2. **Lathe.** The piece stands upside down on the turntable (pots, beakers, sleeves on the skirt lugs;
   discs and lids on a three-tier spindle fixture, up to three per load, or one pot with its lid and one
   disc above it; a GN tray on the cradle, tilted 10°). 60 rpm past two fixed masts: inside meridian
   (floor centre, floor, corner, wall, rim) and outside meridian (rim, neck, wall, skirt), 10 nozzles
   d 1.5 at 5 bar, 12 L/min recirculated from a 3 L sump at 55 °C with enzymatic detergent, 120 s.
   Because the part turns, every point of a body of revolution passes every jet; a GN tray's corners
   pass the same jets at a changing distance (coverage there is a claim, to be shown by riboflavin).
3. **Rinse** 0.8 L fresh through the same masts, 20 s. **Spin** 900 rpm, 15 s (GN tray 300 rpm).
4. **Induction flash**: the 2.5 kW ring heats the wet tri-ply part to 105 °C for 45 s. A0 at 105 °C
   accumulates at 316 per second, so the A0 ≥ 60 of HYG-021 is reached in the first second at
   temperature; the limit is evenness, not dose (a wall pyrometer on the outside mast checks the coldest
   band, the rim spool, which is monolithic stainless and heats by conduction only: **M**). About 25 Wh
   per kg of ware instead of 300 Wh of 80 °C rinse water.
5. **Verify**: lathe camera while the part turns once under a stripe light; recorded liquor temperature,
   pump pressure, flash temperature, turbidity of the rinse (HYG-026). A failed part gets one longer
   cycle, then goes to the central washer, then to quarantine.

One load: **4.5 min**. The liquor is reused for up to three loads, RTE loads first, class R loads last.

| Goes to | Pieces | Why |
|---|---|---|
| Lathe, flash | all cans, sleeves, baskets, plain and scraper lids, platter discs, coupler rings (flash limited to 95 °C: silicone bead), GN trays and sheets, ricer, rasp floor, platen | bodies of revolution or flat; monolithic |
| Lathe, no flash (80 °C rinse instead, +0.3 kWh) | whisk and blade kits, grater, slicer, sickle, sweep knife, wedge disc, grid and comb piston (the comb has pushed the grid clean first), kneading lid, folders, apron, gasket frame | blades and polymers must not be flashed; blade roots and wire ends face the jets only partly |
| Central washer D7 | egg cassette, die disc with gate, dosing collars, paste-cartridge parts, trough inserts, GN rack, divider | hinges, slides, channels: not provable on a lathe |

### 6.3 Honest list of crevices, seals and shadows

| Place | Problem | Answer, and how good it is |
|---|---|---|
| Rim spool weld and neck | fillet outside, under the flange | outside mast aims at it; visible to the camera; good |
| Coupler bead, gasket frame | moulded silicone on steel: the bond line | moulded, not glued; dated wear part, yearly; odour uptake (onion, curry) not solved |
| Perforated baskets, ricer, rasp floor | 1 500 holes; starch and fibre in holes | comb or piston first; back-light check in the lathe; M |
| Grid blades, slicer and sickle blade roots | blade clamped or welded to a frame | welded and ground only, no clamped blades; still a shadow on the downstream side: fan jet from the outside mast; M |
| Whisk wire ends, scraper-lid silicone edges | sockets, bond | wires welded flush; silicone edge moulded on; M |
| Egg cassette, die gate, collar shutters | pins, slides | central washer; the weakest pieces of the kit |
| Quill nose above food | bayonet, bellows, spindle lip seal with leak-off | drip collar on every stalk; the nose is fixed and cannot go to the lathe; it is washed only by the K/H tier nozzles, daily, and is an LRU. **A Zone N drive above open food behind a bellows is a conflict with HYG-004 and HYG-016** |
| K/H annular turntable | labyrinth gap between ring and pedestal; boil-over runs in | flushed by two dedicated nozzles into the deck drain; inspected by endoscope at service; a real harbourage risk |
| Wender telescopic slide and jaws | open profile, rack, plain bearings, in the shaft beside the carried vessel, in the splash of any leaking joint | jaws rinsed at the seat after every class R grip (2 nozzles, 3 s); slide washed by the shaft ring daily; grease-free polymer bearings; M |
| Sealing band of the Z slot | full-height dynamic seal in Zone S | band is wiped by the carriage; replaced yearly; M |
| Dock cradle and clamp | flour dust, drips of oil | a dry zone with no dust removal; washed weekly by two nozzles, then dried by the dock's air; wetting flour dust makes paste. **L–M** |
| Oven cavity | a bought household oven has no wash | all oven ware is lidded or deep; steam-soak programme weekly; **burnt-on spills are not removed: open issue, request R6** |
| Shaft, hob tiers | fat aerosol from flips and frying, steam | fixed nozzles per tier (5 each) and a spray ring on the Wender carriage for the shaft: daily wash-down with 55 °C liquor from the lathe sump, rinse, fan dry 30 min; glass hobs are flat; tier ceilings slope 3° |

### 6.4 Water, energy and time per reference meal

Reference meal: 24 pieces soiled (mean of B1–B12: 20; B2: 33), of which 16 round, 5 GN, 3 to D7.

| Item | Count | Water | Energy | Time |
|---|---|---|---|---|
| Cold rinse at the seat | 15 pieces | 6 L | — | in passing |
| Lathe loads | 12 (7 round trees, 5 trays) | liquor 4 × 3 L = 12 L; rinse 12 × 0.8 = 10 L | liquor heat 0.6 kWh, flash 0.4, 80 °C rinse for blade loads 0.2, pump 0.1 | 54 min |
| Central washer share | 3 pieces, quarter load | 5 L | 0.3 kWh | within its cycle |
| Daily wash-down, half a day's share | tiers, shaft, dock | 5 L | 0.2 kWh | 12 min + 30 min drying |
| **Total for preparation** | | **about 38 L** (range 26–45) | **about 1.8 kWh** | **about 55 min after serving**, first stations free after 10 min |

This does **not** meet RES-005 (45 L per meal including the dish washer and the cooking water): with
10 L for the dishes the meal is at about 50 L. The lathe's water is dominated by the rinse and by the
number of loads, not by soil; fewer loads (nesting four pieces per tree) is the lever. PERF-005 (next
meal possible after 30 min, all clean after 90 min) is met, since the ware stock covers two meals
except for the single-instance discs.

### 6.5 Raw and ready-to-eat, waste

* **Class R / RTE**: separation is by instance and by time. Trays T65a/b and the cold sheet are the
  raw set for a meal; salad and dessert use pots and beakers that raw food has not touched. The
  single-instance parts (grid, ricer, slicer, die disc, egg cassette) are the weak point: RTE jobs are
  scheduled first ("dry before wet, raw last"), otherwise a rinse and a 4.5 min lathe cycle sit in the
  critical path (B3). The Wender's jaws grip only necks and flanges, below the pouring edge, and are
  rinsed after every class R grip; they are the one shared contact path between raw and RTE ware (M).
* **Peel slurry, trimmings, shells, can lids, surplus flour and crumbs**: collected in a pot or beaker
  under the stack, carried upright and inverted on the seat; water passes, solids stay on the strainer
  drawer (10 L), which drains and is pushed to the organic-waste container of the waste module. Waste
  is never carried over open food: open vessels travel only in the shaft, and the seat is at its foot.
* Breading leftovers (flour, egg, crumbs after raw meat) are discarded each time: about 60 g per meal.

## 7. Numbers

| Item | Value [E] |
|---|---|
| Wall width | **1600** (left column 520, shaft 440, hot column 560, walls 80); depth 600; height 2000 |
| Heated positions | K/H 3.5 kW with turntable, quill and tipper; S1 3.5 kW with stirring spindle; F1, F2 flex 3 kW each; oven 45 L class, sideways; warm-hold on any free hob at low power |
| Motion actuators | **21** (Wender 6, K/H 5, S1 2, dock 5, lathe 2, oven door 1) |
| Other driven items | 3 pumps, about 10 valves, 5 induction generators, 2 fans, 1 vibrator (counted in the dock) |
| Wall penetrations with a moving seal | Z slot band; quill (bellows + lip seal); tip-cradle shaft; S1 spindle; dock roll shaft and clamp rod; lathe turntable shaft (from below, umbrella); K/H ring labyrinth: **8** |
| Ware | 76 pieces, 50 types; 62 custom pieces of 43 custom types, the rest bought GN trays and mats |
| Custom machine assemblies | about 24 (Wender head, jaws, telescope, C-frame, crosshead, fork, turntable ring, pedestal, tip cradle, S1 spindle unit, dock cradle, clamp, cone, lathe chamber, masts, fixtures, seat, oven door, tier liners, shaft liner, frame) |
| Parts cost | **about EUR 24 000 ±35 %**: Wender 3 500; K/H 3 300; S1 and flex hobs 1 500; oven and door 2 600; dock 1 000; lathe, seat, pumps 1 900; ware 5 000 (custom tri-ply cans at EUR 90–150 are the largest item); frame, liners, extraction 3 200; controls, drives, sensors 2 300 |
| Peak power | installed 3.5 + 3.5 + 3 + 3 + 3.3 (oven) + 2 + 2.5 (lathe) + 1.5 (drives) = 22 kW; managed to 11 kW (DEC-1): two hobs at full power plus oven, the rest pulsed; the lathe runs after cooking |
| Noise sources | rasp peeling (2 min, est. 70–75 dB(A) at source), blade stalk at 6000 rpm (20–60 s), spin at 900 rpm, press strokes and the sweep knife, lathe pump and jets for 54 min after the meal (NOI-002 limit 48 dB(A): needs an insulated chamber), Wender moves |
| Handling moves per meal | mean 48, range 20–83 (section 5); 7–11 s each |
| Reliability arithmetic | at 48 moves, 99.9 % per move gives 95 % per meal; REL-001 (98 %) needs 99.96 % per move or recovery from most faults without a human (section 9) |

## 8. Coverage estimate against the 248-meal corpus

Method: the 57 corpus rows that contain a no-workaround or shaping operation (FLP excluded, which K2
does natively) were judged one by one against section 4; the remaining rows were judged by operation.
Purchases as MEAL-012 allows (peeled onions, trimmed beans, cut meat, grated or block cheese). This is
an estimate by reading, not the recomputation of corpus appendix A.

| Group | Meals | Verdict |
|---|---|---|
| Excluded by requirements 5.4 | CK11, DM21, DS13, BF08, AS05, BK06, CK08, BK02 (8) | out for every candidate |
| **Needs one piece picked up and placed in a given orientation, or a single thin slice or sheet laid** | DM13 stuffed peppers, VG04 stuffed zucchini, IT18 cannelloni, IT12 saltimbocca, FR06 croque monsieur, MX04 quesadilla, US08 sandwich or wrap, MX03 burrito, MX07 enchiladas (9) | **no** |
| Folding, pleating, pocketing, braiding | DM05 cordon bleu, AS08 spring rolls, AS09 gyoza, IN07 samosa, CK17 Apfeltaschen, CK12 strudel, CK13 sponge roll, DS11 filled yeast dumplings, BK04 braided loaf (9) | **no** |
| Others | DM12 cabbage rolls (leaf separation), BF14 poached egg (2) | **no** |
| Covered only if an M or L–M mechanism passes its test | 9 roasts carved by the sickle (DM06, 07, 08, 11, 16, 29, ME10 and two more); DM02 Rouladen; IT05 lasagne (sheets); 8 unmoulded cakes and desserts; DS15 baked apple (cored and filled in the feed sleeve); US01 burger (ring-build); 5 breaded dishes | yes, test pending: **about 26 meals hang on five tests** |
| Adapted methods | 9 oven or shallow-fried instead of deep-fried, 7 stir-fries in a tumbled tray, 3 of X-13, and K2's own: DM02, BF11 and ME03 and MX02 and US02 and US06 served as components, DM20 and US04 served uncarved, US07 with diced ham and grated cheese, SD25, DS16, SA15, SD22, BF10, AS06, CK05 (16) | **about 35 meals = 14 %**, above the 10 % of MEAL-013 |

Count: 248 − 8 − 20 = **220 preparable = 88.7 %**; by weight about 90 % (none of the 20 K2-specific
losses has weight 3; BF11 and US07, both weight 3, are kept only as adapted). Range: 86 % if sickle
carving of hot braised meat fails for half of the roasts and the Rouladen chain fails; 92 % if a
minimal pick-and-place aid is added (section 11). MEAL-002 (95 %) is **not met**, MEAL-003 is met only
through adapted methods, MEAL-004 fails for Mexican (3 of 7) and is marginal for cakes, MEAL-005 is met
on paper (Rouladen at L–M). MEAL-009 is not met (onions, peppers, beans, soft fruit are bought
prepared). Of MEAL-018 the concept solves FLP, UNM, SCO, BRD, FRB, FRK, KND natively, ROL, SHD, FRM,
RLT and layered ASM with tests, CAR for boneless roasts with a test, and fails open-hand ASM, most STU
and most WRP. Of the catalogue's gap list it solves none of G1–G10; it sidesteps G9 for thick pieces
and offers the cold sheet for slices.

## 9. Failure modes and recovery

| Failure | Detection | Recovery | Human needed? |
|---|---|---|---|
| Mis-seated stack before a press stroke | squeeze position outside ±0.5 of the expected sandwich height; fork load pins show tilt; press limited to 300 N for the first 5 mm and the force-travel curve compared with the recipe's signature | restack once; then abort the step | no |
| Food jams in the grid or die (stringy celeriac, bone chip) | force above 4.5 kN or no travel | retract, comb piston again at low speed; then the stack goes to the seat, is inverted and flushed; the load is lost; PRP-035 camera check of the grid | no |
| Joint leaks during an inversion | jaw load pins lose mass; shaft camera; conductivity strip in the seat gutter | the roll stops at the nearest upright; shaft wash-down; the dish continues if the loss is under 5 % | no, unless hot fat on the telescope (then a wash cycle before the next move) |
| Food sticks in the upper vessel after an inversion | jaw B still heavy | two knocks with the squeeze axis, 3 Hz shake; then chase with the recipe liquid at K/H; then accept the residue and scale the recipe | no |
| Dropped vessel or tray | jaw load pin goes to zero in a move | **no recovery**: a pot on its side at the shaft foot cannot be gripped by neck jaws. The shaft foot slopes to the seat and is washed; the meal is aborted | **yes** |
| Piece falls beside the vessel at a tip-in or in the dock | tier camera or missing mass | stays on the deck, washed down daily; recipe scaled | no |
| Boil-over at K/H into the turntable labyrinth | base temperature and load cells | flush nozzles; turntable dried at 300 rpm | no |
| Pancake, cutlet or patty torn at a flip | shaft camera | served as it is, or repeated if ingredients allow | no |
| Roulade opens | camera on the trough tray | rolled again once; then served as a braised slice with its filling (the dish is degraded, not lost) | no |
| Part fails wash verification twice | lathe camera, turbidity | central washer, then quarantine shelf; the kit has no second instance of 14 part types, so the affected operations are blocked until a human replaces the part | later |
| Wender fails (any of 6 axes) | drive faults | **everything stops**: no food moves, hot pots stay on hobs, which switch to hold and then off; no redundancy | **yes** |
| K/H fails | drive faults | cooking continues on S1, F1, F2; no cutting, kneading, whisking, tip-ins, can opening | yes for most meals |
| Power loss with a stack clamped inverted | — | roll brake and jaw screws are self-locking; on return the pair is finished or set down | no |

## 10. Top risks and the cheapest experiment for each

| # | Risk | Kills the concept? | Cheapest experiment |
|---|---|---|---|
| 1 | **Traffic and single points**: 48 moves per meal through one carriage, all press work and all merges through one station; REL-001 needs 99.96 % per move | degrades, does not kill | discrete-event simulation of B1, B2, B3 and reference menus 9 and 15 with the move times of section 2.2 (one week, no hardware); a plywood shaft with a manual roll head to time real moves |
| 2 | **Hot inversion**: fat or sauce leaves a metal joint or a gasket at 100–200 °C | yes for FLP, the concept's main claim | two bought 24 cm steel pans, a turned coupler ring and a lathe chuck as roll axis: flip 50 steaks, pancakes, fried potatoes with 5 / 15 / 30 / 60 mL of fat; weigh what escapes; measure drop damage |
| 3 | **Slices and single pieces**: cold sheet picks one slice, releases it flat; cutlets land flat from the pack | kills Rouladen as a machine-made dish (brief) | a 3 mm steel sheet from the freezer on supermarket Rouladen, cutlets, bacon, 30 trials each; induction hob pulse for release |
| 4 | **Rouladen chain**: apron roll by tray travel, drop into the channel, untied braise for 100 min | as 3 | silicone mat on a baking tray pulled under a fixed rod by hand; trough insert bent from sheet; 12 rolls braised (shared test of the catalogue) |
| 5 | **Residue of inversions** for dough, batter, mince, mash against PRP-013 (3 % / 8 %) | no, but adds chase steps and moves | weigh residue in a tapered pot after inversion and two knocks, ten foods, greased and bare |
| 6 | **Wash lathe and flash**: coverage on GN corners, blade roots, holes; evenness of induction heating on walls and the solid rim | yes for "all ware on a lathe" (falls back to the central washer and 60 min cycles, doubling the ware stock) | a pot on a turntable in a bin with four nozzles and a 5 bar pump, riboflavin under UV; a 2.5 kW hob coil wound as a ring round a wet tri-ply pot with thermocouples at rim, wall, floor |
| 7 | **Press work at 5 kN on a hot, wet station**: dicing force with two-tier blades, ricing skin-on potatoes, dough sheeting by platen; bellows and nose above food | partly | bench drill frame with a 5 kN servo cylinder, bought push-dicer grid and ricer plate; measure force curves for potato, carrot, celeriac, onion halves; press 500 g of dough between mats |
| 8 | **Dock**: flour through the vibrated sieve at 60–70 % RH; pouring by angle from cartons; dust and drips in a zone that is hard to wash | no | a box on a hand-rolled cradle over a kitchen scale |
| 9 | **Width and depth**: sideways oven in 560, roll head passing the oven mouth, 440 shaft | no, costs width | CAD of the three columns with a real compact oven and the largest inverted sets |
| 10 | **Part count** (76 pieces, 50 types) against PRP-003, and 14 single-instance types in the critical path | no | walk the 15 reference menus with the ware list and count conflicts |

## 11. Improvements found, answers to the catalogue's questions, and what to borrow

### 11.1 Improvements found while exploring (all are changes to the catalogue definition)

| # | Improvement | Value |
|---|---|---|
| I1 | **Inverter on the lift** (C1): roll axis, two neck-jaw pairs and a squeeze axis on the carriage in a shaft | the most valuable one: removes a station and about a third of the moves, makes flip, toss, drain, unmould, lid-clamped carry and weighing one device; answers catalogue rule R2 ("one horizontal roll axis somewhere") once for preparation and cooking |
| I2 | **Rim spool with a gripping neck**, gaskets only on interposers | a single vessel can be held inverted; vessels stay bare metal; the joint is a known hygienic standard |
| I3 | **Hourglass dock** at the port with roll-angle metering | dosing costs no carriage move; boxes are never handled by the cell |
| I4 | **Press column on a hob** with an annular turntable | purée, mash, knead, whisk, spin-spread in the cooking pot; one station less |
| I5 | **Weighing jaws and partial inversion** | layering and portioning by weight without a ladle; residue and leaks are measured at every transfer |
| I6 | **Finding C4: inversion cannot merge**, answered by the tip cradle | not an improvement but a correction; without it the concept cannot cook a sauce |
| I7 | **Rinse seat** at the shaft foot: drain, cold flush, waste strainer and jaw rinse in one fixed funnel | rule R11 for 0.4 L per piece; hot water is never poured in the open |
| I8 | **Cold sheet with induction release**: a frozen flat GN sheet lifts one slice, a 1 s pulse frees it | a freeze gripper with no power on the tool (L–M) |
| I9 | **Kits**: stalk tools hang in their lids, discs ride on their sleeves, vessels nest | fewer moves, one rack footprint per family |
| I10 | **Wender as X table** under the fork and against a fixed bar | stripes, rows and apron rolling without a new axis |
| I11 | **Grease by spin, flour by tumbling, release by an induction pulse** | LIN and UNM (22 and 11 meals) without a brush |
| I12 | Eggs moved from the box tray into the cassette by one inversion; beaten egg strained through the ricer by inversion | no egg gripper; shell insurance for mixtures |

### 11.2 The catalogue's questions for the K2 explorer

1. *Moves, elapsed time, who moves the parts, mis-seat detection.* Mean 48 moves, 20–83; times in
   section 5. The cell's own Wender moves all ware; the transport system only pushes boxes into the
   dock and takes finished vessels at the serving side of the shaft (TRN-002 is respected at the module
   border, conflict X8 remains inside). Mis-seat: squeeze position and force, fork load pins, 300 N
   probing stroke (section 9).
2. *Hot inversion.* Gasketed coupler or frame for anything wet (silicone, 230 °C); metal to metal only
   for frying flips with under 30 mL of free fat; fill limit 60 % of the receiving vessel; more than
   3.5 L of hot liquid is never inverted (basket and drain stalk instead); inversions happen only in the
   closed shaft above the seat; clamp force is measured, the roll has a brake and the jaws are
   self-locking. Untested (risk 2).
3. *One inverter for R260 and GN 2/3.* Yes: neck-and-flange jaws with an arc pocket and straight slots,
   roll about the tray's long axis, largest swing 400, shaft 440 × 520.
4. *Cut the kit.* From about 55 to 76 pieces: the kit **grew**, because the source list lacked the GN
   inserts, the transition plate, the dosing collars, platter discs and package tools. Seven source
   parts were cut (section 2.5). A cut to about 60 is possible by dropping sickle, wedge disc, S60,
   coarse die, one folder, one platter disc, the divider and the second trough insert, at the price of
   about 14 more meals.
5. *Lathe against the central washer.* Section 6.2: about 60 pieces on the lathe, 14 without flash,
   about 12 to D7. Flash on tri-ply walls is plausible, on the monolithic rim spool it relies on
   conduction (M).
6. *Rim against the box standard.* No box is inverted onto the round rim any more. The dock takes
   GN 1/9 and 1/6 directly and GN 1/3 through a funnel collar; the collar, not the vessel, adapts.
7. *Tilting column.* Not worth it; the roll axis on the carriage gives the same inverter and tumbler
   with a 400 swing instead of 850 and leaves the press frame stiff.

### 11.3 What I would borrow from other candidates

* **A small pick-and-place hand** (K1's rod hand or K6's stem tools) for one piece in a given pose:
  it would recover the 9 meals of the second row of section 8 and replace the cold sheet, the dock's
  piece chute for cutlets and the egg transfer. This is the single largest gain in coverage (+3–4 %).
* **The belt-metered guillotine or a knife with a comb fence** (SM-017, SM-032) for carving and for
  slicing cooked potatoes, if the sickle fails.
* **Pins counted by a magnet** (SM-085) as the fallback for Rouladen.
* **K6's three-minute washer** instead of the lathe if the riboflavin test on GN corners and blade
  roots fails: the ware is already all loose.
* **K5's piston box or tube** as the paste cartridge, filled at ingestion.
* **The venturi wand** is not needed; the drain stalk with a pump uses no motive water.

## 12. Open issues and requests to the architect

### Open issues

1. **The rack holds only about 60 % of the ware.** 1050 mm of column height takes the flats magazine
   (19 slots), the GN stack and one nest of pots and beakers. Tall pots, pans, the S250 sleeves and
   about twelve flats park on S1, F2 and in the lathe while these are idle and are moved when the
   station is needed (4–6 extra moves in large menus), or the cabinet grows by about 300 mm. The width
   of 1600 is therefore a lower bound.
2. **COK-008** (every cooking position stirs) is met at two of four positions; **COK-010** (add at any
   time) only by taking the vessel to K/H. Menus with three stirred pots at once (reference menu 9:
   red cabbage, dumplings, gravy plus the roast) need a third scraper drive or accept unstirred
   simmering of one pot.
3. K/H occupancy: in B3 it is busy for 28 minutes without pause; for six persons the dicing and
   forming loads grow by half and the 50-minute target is lost.
4. The oven is a bought household unit mounted sideways with a changed door; its cavity is not washed
   by the machine, and the roll head has about 5 mm of clearance in its mouth. Not checked against a
   real model.
5. Adapted methods are at about 14 % of the corpus against the 10 % of MEAL-013.
6. HYG-004 and HYG-016 at the quill (drive above food behind a bellows and a lip seal) and the slot
   band of the Z axis are accepted conflicts, not solved ones.
7. Safety: a 5 kN press, a 900 rpm turntable, a blade at 6000 rpm and a roll axis with 8 kg behind a
   household door (catalogue X14); only interlocks are assumed here.
8. Onion peeling, stripping herbs, trimming small items, bone-in carving, trussing (G1, G2, G5, G8,
   G10) are untouched.
9. The 1-person case soils 8 pieces and costs about 6 L and 12 min of washing for 110 mL of egg.
10. Software: about 25 skills (stack recipes with force signatures, flips, tip-ins by weight, dock
    metering per product class); fewer than a manipulator concept needs, but every one is safety- or
    hygiene-relevant.

### Requests to the architect

| # | Request | Collides with |
|---|---|---|
| R1 | **Vessel standard**: R260 rim spool with neck, base skirt with three notches, tri-ply bases; GN 2/3 thermoplates as the flat family; both frozen as the interface of preparation, cooking, serving and washing | X15 (ware material fixed by the induction flash) |
| R2 | **Box**: GN 1/9, 1/6, 1/3 with a plane top rim that seals against a silicone face when lifted by 60 N; delivered to the port with the lid removed and pushed 200 mm on rails into the cradle; box walls stiff enough to be rolled over full. Spice boxes keep a sifter insert; egg boxes a 2 × 3 tray insert | X1, X3, X5; BOX-005, BOX-007 |
| R3 | **Ingestion / package opening**: vacuum packs and MAP trays arrive opened, just in time, in a box-size carrier, without absorbent pad where possible; pastes (mustard, tomato paste, honey, quark) are decanted once into piston cartridges; butter, cheese and bacon blocks may be diced by this cell at first opening and returned to cold storage as pieces | X6, DEC-3 |
| R4 | **Cold storage**: one freezer position for the cold sheet (GN 2/3 × 20) and the ginger and herb pucks; chilled boxes may stay at the dock up to 3 min per dosing | X7, FSF-013 |
| R5 | **Transport**: serves only the port (boxes in and out, about 20 per meal) and the serving side of the shaft (finished vessels and platter discs out, soiled ones back); never enters the cell | TRN-002, X8 |
| R6 | **Cooking module**: the four induction positions, the oven with a motor door facing the shaft, extraction per tier and the cavity cleaning are inside this cabinet; the architect decides whether they are owned by D5 with this geometry, and whether a self-washing compact combi oven replaces the household unit | open issue 1 of the catalogue |
| R7 | **Washing module**: accepts about 12 awkward pieces per meal (egg cassette, die gate, collars, trough inserts, rack) through the transport system; supplies detergent and softened water to the lathe; takes the strainer drawer's solids | X12, D7 scope |
| R8 | **Serving**: takes food in R260 vessels, baskets, GN trays and on platter discs; owns slicing of baked goods, plate-side assembly of component meals (tacos, Abendbrot, hot dog, burger as fallback) and the final merge of pasta and sauce | UO-81 to UO-88 |
| R9 | **Utilities**: 400 V 3N~ with load management to 11 kW; cold water at 2.2–5 bar to quill, dock, seat and lathe; a drain rated for 95 °C with a tempering valve; extraction of about 150 m³/h from the hot column | UTL |

## Verdict of the explorer

K2 is a good cooking-side mechanism and an incomplete preparation system. Rim-to-rim inversion on the
lift answers flipping, unmoulding, draining, tossing and enclosed breading with one device and no seal
in any washed part, and the closed stack dices, rices, forms and kneads well. It cannot merge, cannot
place a piece, and handles slices badly; its width, its part count and its dependence on one carriage
and one press station are real. As a whole system it reaches about 89 % of the corpus. Its parts worth
keeping for any hybrid in round P5 are I1 (inverter on the lift), I2 (rim spool), I3 (hourglass dock)
and the grid-over-rotor dicer in the cooking pot.
