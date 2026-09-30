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
actuators, 76 loose ware pieces of 50 types, parts cost about EUR 24 000 [E, ±35 %]. Ten of the
twelve benchmarks run (two of them as adapted methods), two are marked "yes, test pending" on one
untested step each. Estimated corpus coverage is **91 % (range 88–93 %)**, below the 95 % target: the
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
