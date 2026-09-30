# K5 — Ram-and-die column with piston vessels

Round P3 exploration of candidate K5 (definition: `design/prep/02-concept-catalogue.md` section 3.6; rules:
`design/prep/03-exploration-brief.md`). Written without reading the other files in `design/prep/concepts/`.

Inputs read: `BRIEF.md`, `DECISIONS.md`, the exploration brief, the catalogue (complete), idea files B and E
(complete), A and F (shared conventions, the press concepts A3 and F:B, corpus checks, sub-mechanisms, bets),
`requirements/requirements.md` (3.5, 3.6, 5, 6, 7, 11.4), `research/02` (taxonomy, all 248 rows in compact form,
4.9, 6), `research/04` (1, 2, 6–8, 16), `research/05` (5, 6, 11), `research/06` (2).
Not read: idea files C and D (used only through the catalogue's SM list), `research/01`, `03` (box sizes only),
`07`, `08` (prices only).

**Status of every statement.** Nothing here was built or tested. All forces, times, masses, prices and success
rates are my paper estimates, marked [E], unless a source is named ([R4], [R6] = research files, [cat] = catalogue).
Confidence: H = a product or factory machine does this at a comparable scale; M = sound, needs a bench test;
L = speculative.

---

## 1. Definition

### 1.1 The cell in one page

K5 is a **press column beside a hob**, served by **one vessel shuttle**.

* **The column (bay A).** A storage box docks at the top. Its contents fall into an upright stainless tube
  (bore 140 × 300 mm, 4.6 L) that stands on a die. A loose piston is set on top of the food and an 8 kN ram
  pushes on the dry side of the piston. Whatever leaves the die is cut off by a sickle blade and falls
  straight into the pot, pan or tray standing below. Die and advance per cut choose the result: slices of any
  thickness, dice, sticks, wedges, riced potato, Spätzle, patties, dumpling portions, a paste dose, a filling
  strand, a mustard ribbon. Three tubes stand on a turret (fill, press, service), six dies lie in a
  carousel under them.
* **The tube is also the mixing vessel.** With a gasketed blank cap under it the tube is liquid-tight at the
  bottom; the ram then works a loose *dasher* up and down inside it: an undersized plunger kneads dough and
  mince by back-extrusion through the annular gap, a perforated dasher mixes batter, a mesh dasher whips
  (the plunger churn and the French-press milk frother). One ram, one tube, no second cylinder (change from
  the catalogue, section 11).
* **The hob (bay B)** has four heated positions. The two front positions are the two leaves of a **frying
  book** ("Bratbuch"): two rectangular GN 1/2 pans or trays, hinged like a book, each leaf driven through 180°
  with up to 2 kN of closing force. Closing the book and opening the other side turns everything over. The
  book is the flat bench of the concept: it flips steaks, cutlets, patties and fried potatoes, breads
  cutlets, flattens meat and presses dough. The two rear positions are **rotating round positions** (0–600 rpm,
  20 Nm) for pots and round pans: the pot turns against a scraper hung on its rim (stirring), a pan spins
  batter into a pancake, a perforated basket spins salad dry, a rasp can peels potatoes.
* **The shuttle** is a fork on X-Y-Z rails behind the rear wall with one roll axis. It grips every vessel,
  tray, basket, lid and stem tool by the same rim lugs or stem, carries vessels between the drop position
  under the column, the hob, the oven and the hand-over, pours by rolling, lifts baskets out of pots, turns a
  round pan over with its flip lid, and holds the four stem tools that remain (tongs, turner, carving knife,
  comb fence).
* **The oven (bay C)** is a bought built-in combi-steam oven turned 90° so that its mouth faces the hob bay.

Honest summary of what this is: the column does all shape-giving and metering with very few surfaces; the
book and the shuttle do everything that must be turned, placed or carried. The column does not remove the
need for a manipulator. It reduces what the manipulator must be able to do to "carry a vessel, roll it, and
hold four tools".

### 1.2 Front view (dimensions in mm, heights above floor)

```
        bay A  COLUMN  450        bay B  HOB  720                       bay C  OVEN  600
      |<---------------->|<-------------------------------->|<----------------------->|
2000  +------------------+----------------------------------+-------------------------+
      | ram cylinder 8kN |  extraction hood, grease mesh,   | condenser, fan, filters |
      | (dry, Zone N)    |  condensing coil, drip tray      | (dry)                   |
      |   ||   box dock  |                                  |                         |
1700  |   ||  [box]tilt  |  shuttle rail X 1250 (dry slot   |-------------------------|
      |   ||   \ chute   |  behind rear wall, labyrinth)    |                         |
1480  +===||====\========+ =======[carriage]================|   combi-steam oven      |
      | rod Ø40  \  egg  |        | Z 500                   |   (bought, turned 90°,  |
1440  | [piston] \ mod.  |        |                         |    mouth to the left,   |
      |  +----+  +----+  |      [fork, roll axis]           |    lift door, 1 drive)  |
      |  |tube|  |tube|  |        |                         |    cavity GN 2/3,       |
      |  |PRESS  |FILL|  |                                  |    mouth 900-1350       |
1135  |  +----+  +----+  |                                  |                         |
1110  | ==die carousel== |          rear: 2 rotating round positions (pot, pan)       |
1090  | --sickle plane-- |   (o) 9 L pot      (o) pan 28    |                         |
      |  diverter flap   |  front: frying book, 2 leaves GN 1/2, hinge in the middle  |
 900  |  [drop position] |  [ leaf L 265x325 ]^[ leaf R ]   |-------------------------|
 880  +--3 load cells----+----------induction deck----------| clean-ware store:       |
      | die/tube wash    | 4 induction modules, 2 pot       | tubes, dies, pistons,   |
      | sump 6 L, heater | drives, book drives (dry)        | trays, pans, tools      |
      | chip box (GN1/3) | pan / pot / basket store         | (dry, behind a door)    |
      | pumps, valves    | under-deck drawer to the washer  | wash kit, boiler 6 L    |
   0  +------------------+----------------------------------+-------------------------+
```

### 1.3 Top view at the level of the deck (z = 900) and of the turret (z = 1300)

```
  rear wall (dry slot for the shuttle rails behind it)                       depth 600 (540 clear)
  +------------------+----------------------------------+-------------------------+
  |   turret axis    |   (o) rear L         (o) rear R  |                         |
  |       +          |   round pos. Ø300    Ø300        |    oven, 560 x 595      |
  |  FILL   SERVICE  |   pot drive          pot drive   |    mouth  <---          |
  |    o     o       |                                  |    (lift door)          |
  |     PRESS        |  +-----------+ +-----------+     |                         |
  |       o          |  | leaf L    | | leaf R    |     |                         |
  |  = drop position |  | 325 x 265 |^| 325 x 265 |     |                         |
  |    (front, z 900)|  +-----------+ +-----------+     |                         |
  +------------------+----------------------------------+-------------------------+
  front (service doors, Zone X)          ^ hinge axis runs front to rear
  turret: 3 tube seats on a Ø 230 pitch circle, outer swing Ø 400; die carousel Ø 400 coaxial below it.
  Hand-over port for boxes: upper left side wall or ceiling of bay A (z 1500-1750), chosen by the architect.
  Hand-over of cooked food to plating: the shuttle sets the vessel on a port in the right or left side wall.
```

**Wall width: 1770 mm** with the oven (450 + 720 + 600), all of preparation and cooking included; 600 deep,
2000 high. Without the oven bay (if the architecture supplies an oven with its own loader) it is 1170 mm.
I found no honest way to stack the oven into the 1170 mm: an oven under the hob deck cannot be loaded by a
handler that lives above the deck, and the space above the column is taken by the ram and the dock.

---

## 2. Mechanism

### 2.1 The column

**Frame and ram.** Closed frame: deck plate (z 880), ceiling plate (z 1480), two tie columns Ø 40 at the rear
corners of bay A, sized for 10 kN. The ram is an electric servo cylinder (8 kN peak, 5 kN continuous, 340 mm
stroke, 60 mm/s, folded motor, bought) standing on the ceiling plate in the dry zone. Its rod (Ø 40, hard
chromed stainless) passes the ceiling through a hygienic rod collar (scraper, lantern chamber drained to the
cell, dry seal above, SM-191). The rod end carries the **ram foot**: a flat Ø 120 steel disc with a permanent
magnet ring and a central stripper pin (spring-applied, released by the last 5 mm of retraction against a stop).
The foot picks up any piston or dasher by the ferritic disc welded into its dry side, holds it (60 N), and
strips it off by retracting fully. The ram foot never touches food; it is Zone S and is washed with the cell.
Force is measured by the cylinder's load pin, position by its encoder (±0.05 mm).

**Tubes.** Electropolished 1.4404 tube, bore 140.0 (H8), wall 3, length 300, both ends with a turned rim
(R 3) and three lugs at mid-height for the turret fork and the shuttle fork. The bottom rim carries a snapped-on
UHMW-PE lip ring (wear part) that seals on the flat carousel plate or die. Small tube: bore 60 × 300 (0.85 L)
in a carrier ring with the same lugs, for pastes, one egg white, 100 g of dough and fillings. Set: 4 large
(2 marked green for RTE and produce, 2 red for class R) and 2 small. Tubes are loose: they stand in the turret
forks by gravity and are lifted out by the shuttle.

Why bore 140: the largest bore that a 3-seat turret allows inside 450 mm; takes potatoes, onions, apples,
halved celeriac (PRP-020 asks for Ø 130), a cylindrical boneless roast up to about 2.5 kg (Ø 135 × 170), and
1.6 kg of dough (1.45 L = 94 mm of height). Bore 100–110 would halve the dicing force but would not take a
roast or an apple with clearance. The price is force: see 2.2.

**Pistons and dashers** (all loose, one piece or welded, with a ferritic disc on the dry side):

| Part | Geometry | Use |
|---|---|---|
| Press piston P140 (4 off), P60 (2) | blue UHMW-PE puck, 45 long, two integral lips, flat face | slicing, dicing, ricing, forming, dosing, pigging |
| Comb piston C10, C6 | PE puck with studs matching the 10 and 6 mm grids, 8 high | pushes the heel through the grid (SM-011) |
| Knead plunger K110 | stainless Ø 110 × 40, edges R 8, on a Ø 25 stem 200 long with the magnet disc on top | back-extrusion kneading and mixing of stiff masses |
| Dasher D (perforated) | disc Ø 136, 12 holes Ø 16, on the same stem | batters, emulsions, creaming, folding |
| Dasher M (mesh) | disc Ø 136 with a 1.5 mm woven mesh welded in a ring, same stem | whipping egg white and cream |
| Spray dasher | rotary jet head on a hollow stem, quick water coupling in the ram foot | washing the tube in place |

**Turret.** A three-armed fork on a vertical shaft (rotary seal under a raised boss in the deck, drive below
the deck). Seats at 120°: FILL (under the dock chute), PRESS (under the ram), SERVICE (under the mixer crank,
the bore camera and the wash supply). Each fork holds its tube with 8 mm of vertical float, so that the ram
force goes through the tube wall into the die and the deck, never into the turret. One rotary actuator.

**Die carousel.** A flat 1.4404 disc Ø 400 × 12 on a second, coaxial shaft, 25 mm below the turret forks, with
six windows Ø 152 on the same Ø 230 pitch circle. Dies are loose inserts that drop into a window onto a 4 mm
ledge, flush with the top of the disc. The disc rests on three hardened pads on the deck at the PRESS position
(the press load path). Turret and carousel can turn together (a filled tube travels with its own die or
cap under it, nothing smears) or relative to each other (a tube is slid from one window to the next: a shear
gate, used only for stiff masses and documented as a smear path). One rotary actuator.
The rear third of the carousel runs under a fixed **wash hood** (upper and lower fan nozzles, air knife at
the exit, open labyrinth instead of lip seals because the whole upper bay A is a wash-down cell anyway).

**Dies** (loose inserts Ø 152 × 12–40, all monobloc: wire-eroded or laser-cut from plate and ground; no
assembled blade, no fastener):

| # | Die | Detail | Bought / custom |
|---|---|---|---|
| D1 | Blank cap | flat disc with a moulded silicone face gasket; liquid-tight under the tube's own weight plus 200 N | custom, simple |
| D2 | Open ring | Ø 140 opening, knife-edge exit | custom |
| D3 | Grid 10 mm, two-tier | X blades 9 mm above Y blades, neighbours staggered by 6 mm (SM-010) | custom (eroded); blade geometry copied from push dicers |
| D4 | Grid 6 mm, two-tier | onion, fine dice | custom |
| D5 | Grid 20 mm / fries 10 × 10 long | stews, fries, sticks | custom |
| D6 | Wedge die with centre tube Ø 22 | 8 radial blades; core goes up the centre tube (SM-041) | custom |
| D7 | Ricer plate, 3 mm holes, 30 % open | mash, passata, skin-on garlic | bought plate, custom rim |
| D8 | Spätzle plate, 8 mm holes | also gnocchi strands with the Ø 18 version | bought plate |
| D9 | Former Ø 80 (and Ø 45 insert) | 30 long land, polished | custom |
| D10 | Nozzle Ø 18 / Ø 25 with a 60 mm spout | stuffing, piping, batter pouring | custom |
| D11 | Slot die 120 × 2 (and 120 × 5) | mustard, sauce and tomato ribbons, dough band | custom |
| D12 | Iris peeler | six sprung blades on a one-piece flexure spider, Ø 15–60 (SM-048) | custom, development item |
| D13 | Fine press die, 1 mm slots | squeezing grated potato, spinach (SQZ) | custom |
| D14 | Citrus cone | juice runs through slots, halves stay | custom |
| D15 | Shred plate 3 mm / 1.5 mm (raised teeth) | grate carrot, cheese, potato by pushing the block past the rotating shred arm | custom |

Six are on the carousel per meal; the shuttle exchanges inserts from the store before the meal (2–6 moves).
A small tube uses the same dies through a reducing insert.

**Face rotor.** A vertical spindle beside the PRESS position (shaft through a raised boss in the deck, 200 W,
0–300 rpm, 8 Nm, absolute encoder) carries one cutting arm on a stem with drip collar 2 mm under the die
plane. Arms: sickle blade (draw angle 35°, bought slicer-blade steel, welded stem), tensioned wire bow (for
mince, dough, butter, cheese), shred arm. One slice per revolution; thickness = ram advance per revolution.
The arm parks in a sheath at the rear (form-fitting holster with pipe flow, SM-190) and is checked by a
light barrier after every cutting cycle (PRP-035).

**Diverter.** Under the sickle plane a hinged stainless flap (shaft through the side wall, one actuator)
sends what falls either into the vessel at the drop position or down a 150 mm chute into the **chip box**
(a perforated GN 1/3 box under the deck, taken away by the transport system): first and last slice
(end trimming, SM-037), cores, peel from the iris, skins pigged off the ricer, rejected eggs. Waste never
crosses open food (PRP-033).

**Mixer crank.** At the SERVICE position a light reciprocating drive (slider crank in the dry zone, rod Ø 20
through its own collar, stroke adjustable 40–120 mm by the turret-independent crank radius being fixed at
60 mm and the start height set by a lead screw: I count this as two actuators, crank motor and height)
moves dashers D and M at up to 3 Hz, 250 N. It also reciprocates the spray dasher during tube washing.
The slow, strong strokes of kneading are done by the main ram at PRESS.

**Bore camera and light** above the SERVICE position behind a heated window: one image shows the whole bore.

### 2.2 Ram force (catalogue question 2)

Engaged edge on a grid of pitch p for a cross-section A is about 2A/p [cat, F:B]; force 2–5 N/mm × 1.5 for
friction [R4 1.1]; a two-tier staggered grid engages about a third at once [E].

| Load | Edge, mm | Force, flat grid | Force, two-tier staggered |
|---|---|---|---|
| One potato 65 × 55 on 10 mm | 570 | 1.7–4.3 kN | 0.6–1.4 kN |
| Full bore Ø 140 of potato on 10 mm (layer of 4–5 pieces) | 3 080 | 9–23 kN | 3–7.7 kN |
| Full bore on 6 mm (onion halves) | 5 130 | 15–38 kN | 5–13 kN |
| Full bore on 20 mm | 1 540 | 4.6–11.5 kN | 1.5–3.8 kN |
| Wedge die, Ø 130 celeriac half | 8 × 65 = 520 | 1.6–3.9 kN | — |
| Ricer, 1 kg boiled potato, Ø 140 | — | 0.3–1 kN at the 60 mm bore scaled to 154 cm²: 2–4 kN [E from R4 6.1] | — |
| Sickle face cut of a full bore of sticks | — | 100–200 N at the blade, 8 Nm at 60 mm arm: marginal, see below | — |

Consequences:

1. **A full bore of hard produce on a fine grid exceeds 8 kN.** The rule is single-layer loading with a bore
   fill of at most 50 % of the cross-section for the 10 mm grid and 30 % for the 6 mm grid (two to three
   onion halves side by side). The dock pulse-tilts pieces one by one and the camera above FILL counts them;
   the ram is force-limited and backs off at 7 kN, the turret returns the tube to FILL to shake the load
   (one retry), then the load is diverted to the 20 mm grid and the pot gets coarser dice (recorded). This
   costs throughput: 1.5 kg of potatoes on the 10 mm grid is about 8 layers of 190 g, 12 s each = 1.6 min
   plus 1.5 min of filling [E]. Inside PRP-023.
2. **Carrots and other long hard goods** stand upright in the tube (they fall in point-first from the chute
   and lean); 6–8 carrots Ø 25 on the 10 mm grid are 780 mm of edge, 0.8–2 kN staggered. Good.
3. The face rotor's 8 Nm is enough for slices of a full bore of potato (one blade, draw cut, 50–70 N [E:C])
   but marginal for cutting 100 sticks at once under a grid; the arm is therefore at 45 mm from the spindle to
   the near edge of the bore and the spindle geared to 20 Nm at 120 rpm for dicing. Untested.
4. **Noise and safety.** The ram is quiet (servo screw, < 55 dB(A) [E]); the loud events are the crack of
   produce passing the grid and pieces falling into an empty pot (first 2 s; a silicone drop sleeve hangs
   from the deck edge). 8 kN behind a household door needs: closed frame, interlocked service door with guard
   locking, force limit in the drive (STO on door open), and a die-seat check (carousel index switch plus a
   5 mm ram approach at 200 N that must find the piston at the expected height) before force is released.

### 2.3 The hob bay

**Frying book (front positions 1 and 2).** Two leaf frames of welded stainless tube, each carrying a bought
GN 1/2 vessel (325 × 265) by its rim in a spring clamp: a tri-ply GN 1/2-40 pan with ferritic base for frying,
a GN 1/2-20 tray for breading, a GN 1/2-65 for braising six Rouladen (a second one for twelve), a flat
GN 1/2 griddle plate. The two leaf shafts are concentric on one hinge line running front to rear between the
leaves, 45 mm above the deck, and leave the cell through two rotary seals in the front and rear end walls of
the hinge trough; each leaf has its own worm-gear drive (0–185°, 60 Nm, which is 2 kN at the centre of the
leaf; self-locking) in the dry zone. Under each leaf, in the glass-ceramic deck, lies a rectangular induction
coil of 3 kW (OEM module, DEC-5); the leaf lies flat on the deck when frying and the pan base is 3 mm above the
glass. Rims of the GN vessels meet all round when the book is closed; a moulded silicone rim gasket on the
receiving vessel (rated 230 °C) keeps fat in. Book cycle: receiving leaf (preheated and oiled, or cold for
breading) swings over onto the loaded leaf (2 s), both swing back together through 180° (2 s), the now empty
leaf returns (2 s). 6 s, nothing goes under the food, everything in the pan turns at once.
Surface per leaf 860 cm² gross, about 700 cm² flat: COK-016 M (≥ 600 cm²) is met by one leaf, S (≥ 1 000 cm²)
by both leaves frying in parallel (then the flip goes through a third, cold pan held by the shuttle: slower).

**Rotating round positions (rear positions 3 and 4).** Each is a Ø 300 induction zone (3 kW and 2 kW) with a
driven ring around the coil: a PEEK-and-steel ring gear on four rollers under a raised, umbrella-sealed rim
(SM-236), driven from below the deck (0–600 rpm, 20 Nm up to 100 rpm, 150 W at speed). Round vessels have a
base skirt with three drive notches (SM-218) and sit in the ring. Vessel family (bought pots with a welded-on
skirt and rim lugs): 9 L pot Ø 260 × 200, 4 L pot Ø 220, 1.5 L sauce pot Ø 160 on an adapter ring, pan 28 cm
with flip lid, perforated lift-out basket for the 9 L and the 4 L pot, rasp can Ø 260 for peeling, 8 L mixing
and salad can Ø 260 × 180 with a perforated spin basket. Stirring: a one-piece scraper (floor, corner and
wall blade, silicone-edged steel) hangs on the pot rim and is held against rotation by a fixed post at the
rear wall; the pot turns under it (SM-180). No stirrer drive, no shaft in food. A whisk bar (three wire loops
on the same hanger) replaces the scraper for béchamel, custard and scrambled egg.

**Power.** Four zones 3 + 3 + 3 + 2 kW and the oven 3.5 kW under a load manager on 3 × 16 A (11 kW).

### 2.4 The shuttle

Rails X (1 250 mm travel, from the drop position to 250 mm inside the oven mouth) and Z (500 mm) are belt
and screw axes in a dry slot behind the rear wall; only a closed stainless arm Ø 60 comes through a
horizontal labyrinth slot with a roll-up steel band cover (the one slot in the concept; it is above all
food-contact heights, faces downward and is Zone S). The arm telescopes in Y (280 mm, rod in a collar) and
ends in the roll axis (continuous, 25 Nm, worm drive inside the closed arm) with a two-jaw fork (one actuator,
spring-closed, power to open). Payload 9 kg at 200 mm (the 9 L pot is never carried full, R7; the heaviest
loads are the 6 L braiser in a GN 1/2-100 with 4 kg of food and the 4 L pot with 3.5 kg). Five actuators.

The fork grips (a) the two rim lugs of any round vessel, can, basket or tube, (b) the short side rim of any
GN 1/2 vessel through a clip-on handle plate, (c) the knob above the drip collar of a stem tool (SM-202).
Stem tools: tongs (two leaf blades closed by the jaw stroke), turner 0.6 mm, carving knife (bought blade,
welded stem), comb fence, sifter cup (mesh-bottom cup for flour and crumbs), oil mister (a spray nozzle on
the water-free line: bought pump spray head actuated by the jaw). Six tools, parked on cone pegs on the rear
wall of bay B above the rear positions' splash line.

### 2.5 Wall penetrations and seals

| # | Penetration | Type | Sealing | Zone facing it |
|---|---|---|---|---|
| 1 | Ram rod Ø 40 through the ceiling of bay A | linear rod | scraper + drained lantern + dry seal (SM-191); washed by stroking during the cell wash | S (above open food: drip edge and lantern drain lead behind the tube seats) |
| 2 | Mixer crank rod Ø 20, ceiling | linear rod | same | S |
| 3, 4 | Turret shaft, carousel shaft (coaxial), deck | rotary | raised boss 40 mm with umbrella, lip seal below the boss | S |
| 5 | Face-rotor spindle, deck | rotary | same | S; the arm is F |
| 6 | Diverter flap shaft, side wall | rotary | lip seal, horizontal | S / F (flap) |
| 7, 8 | Book leaf shafts, hinge trough end walls | rotary, ±185° | lip seals outside the trough end walls; the trough drains to the front gutter | S, close to frying fat: the weakest seals of the concept |
| 9, 10 | Ring-gear drives of the round positions | rotary, under an umbrella rim | contact-free labyrinth, drained | S |
| 11 | Shuttle arm, rear wall | slot 1 300 × 70 with steel band cover and inner labyrinth | not tight: drip-proof and splash-proof only, slightly over-pressured with filtered air | S; the only slot, a known violation of "only round things cross the wall" |
| 12 | Dock chute and bypass chute, ceiling | openings with shutters | shutters closed except while dosing; downdraft 30 m³/h | F |
| 13 | Egg module arm, ceiling | rotary | lip seal under a boss | S |
| 14 | Oven lift door | — | oven's own gasket | S |
| 15 | Three load-cell posts under the drop position | static, diaphragm-sealed posts | SM-236 | S |

### 2.6 Parts list: tools, vessels, fixtures

| Group | Items | Count (one working set + class R duplicates) | Bought / custom |
|---|---|---|---|
| Tubes | bore 140 (4), bore 60 in carrier (2) | 6 | custom from standard tube |
| Pistons, dashers | P140 ×4, P60 ×2, C10, C6, K110, D, M, spray dasher | 12 | custom turned parts |
| Dies | D1 ×2, D2 ×2, D3–D15 | 17 | custom plate parts; D7, D8 bought plates |
| Cutting arms | sickle ×2 (green, red), wire bow, shred arm | 4 | blade bought, stem custom |
| GN ware | pan GN 1/2-40 tri-ply ×3, tray GN 1/2-20 ×3, GN 1/2-65 ×2, GN 1/2-100 braiser with lid ×1, griddle ×1, perforated GN 1/2-65 ×1, HDPE board GN 1/2 ×1, handle plates ×4 | 16 | bought; handle plates custom |
| Round ware | pot 9 L, 4 L ×2, 1.5 L ×2, pan 28 + flip lid, baskets ×2, rasp can, salad can + spin basket, lids ×4, scrapers ×3, whisk bar | 21 | bought pots with welded skirt and lugs; rasp can custom |
| Fixtures | Rouladen comb rack (GN 1/2), rolling mat with pull bar (silicone-glass, 300 × 250) ×2, springform 26 with loose floor, loaf tin with loose floor, muffin tray, baking tray GN 2/3 ×2, ring Ø 100 (burger and layered builds) | 9 | bought, mat bar custom |
| Stem tools | tongs ×2, turner, knife, comb fence, sifter cup ×2, oil mister | 8 | custom stems, bought blades |
| **Total loose Zone F items** | | **about 93 pieces of 41 types** | |

This is more than the "about 35 items" of the source concept E:C. The difference is the honest cooking ware
(pots, pans, lids, baskets: 37 pieces) and the class R duplicates. Custom part types: about 30.

---

## 3. Ingredient intake and dosing

**Dock.** The box arrives lidded at the hand-over port. A clamp frame on a horizontal axis takes it, a finger
lifts the lid, and the frame tilts it 0–135° about its pour edge with a 150 Hz vibrator; the frame stands on
three load cells (loss in weight, ±1 g). Two chutes lead down from the dock, selected by which way the
frame faces: the **tube chute** (Ø 150, polished, 35° off vertical, ends 20 mm above the tube at FILL) and
the **bypass chute** (Ø 110, straight down beside the turret to the drop position). Both chutes are loose
stainless parts washed with the cell and sent to the ware washer daily. A shutter closes each chute when not
dosing; a downdraft of 30 m³/h through the open chute keeps steam out of the dock (SM-142).
At the mouth of the bypass chute hangs the **weigh cup** (0.3 L, on a 300 g cell, dumped by one actuator):
seasoning is weighed into it in dry air with the shutter below it closed, then dropped (SM-141).

| Form | Path | Accuracy, confidence |
|---|---|---|
| Whole produce (potato, onion, carrot, apple) | Pulse-tilt from the open box down the tube chute into the tube at FILL; a camera above the chute counts pieces and the dock weighs. A piece too many stays in the tube and is processed or, if the recipe forbids it, the recipe follows the scale (SM-151). Pieces > Ø 135 (celeriac, cabbage head, large kohlrabi) do not enter: see section 8 | one piece; M (A2 of catalogue 4.2: tilt-pouring from a box is itself untested) |
| Leafy (lettuce, spinach, herbs) | Whole box tilted down the bypass chute into the spin basket at the drop position; surplus stays in the basket and returns to cold storage in a box (SM-153). Herbs for chopping: tube chute into the small tube | ±15 g or whole box; M–L. A part of a lettuce head is not solved |
| Granular (rice, lentils, sugar, frozen peas) | Tilt and vibrate down the bypass chute into the vessel on the drop-position load cells; or down the tube chute when the goods will be mixed in the tube | ±2 g; H |
| Powder (flour, starch, cocoa) | Box with a mesh lid (request X1, section 12) inverted over the tube chute, vibrated; falls 250 mm into the tube at FILL, which is then closed by its piston: dust is enclosed from there on (PRP-014). Fallback for a plain box: tilt-pour with vibration, ±5 g | ±2 g with mesh lid; M (humidity) |
| Seasoning 0.2–5 g | Weigh cup, as above. Salt as brine from a spout box through the bypass chute (SM-143) | ±0.1 g; H |
| Liquid (milk, oil, stock, wine) | Water: valve and flow meter at the drop position and at each hob position (four solenoid valves, one nozzle bar). Others: spout box or opened carton tilted over the bypass chute into the vessel, or over the tube chute into a tube standing on the blank cap | ±3 g; M (dribble on the carton lip) |
| Viscous paste (mustard, tomato paste, quark, honey, jam) | Emptied once, at first opening, from the jar or tube into a small tube (bore 60, 0.85 L) standing on a blank cap; the small tube with piston and cap **is** the storage container and goes back to cold storage in a carrier box. Dosing: 2.83 mL per mm of stroke through the nozzle or slot die, wire cut. Request to the architect: a carrier box that holds a capped small tube (section 12) | ±2 % or ±1 mL; H for the syringe, M for getting the product out of the jar (the jar is scraped by nobody: residue 5–10 % in the jar, or the product is bought in pouches and squeezed in by the ram against a flat anvil, SM-149) |
| Solid fat (butter, lard) | Block in the small tube (a 250 g pack is 60 × 60 × 75: request a bore 60 tube to take it cut in two, or buy rolls); pushed out and wire-cut by length: 2.6 g per mm | ±2 g; H |
| Raw meat, pieces and mince | Mince: tilted from its tub or box down the tube chute into a red tube (slides as a lump; residue on the chute 2–4 g, chased by the bread and egg that follow). Cubes and strips: same, or bypass chute into the pan. Slices, cutlets, steaks: tilt-slid from the box down a flat slide insert in the bypass chute onto the leaf tray standing at the drop position; spread by the shuttle tongs if they overlap | pieces; M. **Slices that stick together (bacon, stacked Rouladen slices) are not solved**; request interleaved packs or one slice per tray (G9) |
| Egg | Egg module at the bypass chute (SM-164 baseline, SM-165 as the fallback): two cups take the egg from the tray insert of the box, score, pull apart over a clear inspection cup on the small load cell; camera check; the cup tips into the chute (to the vessel) or to the diverter (reject). Separation by a slotted cup. 3 actuators | 10 s per egg; M (shared with all candidates) |
| Frozen | IQF goods as granular. Blocks (spinach, stock) down the tube chute into a tube, sliced or pushed through the 20 mm grid at up to 6 kN | H / M |
| Long goods (spaghetti, leek, cucumber) | Spaghetti: tilted endwise down the bypass chute into the 9 L pot (they stand, then sink); dose by dock weight, ±20 g. Leek, cucumber, carrot: endwise down the tube chute, they stand in the tube | M–L for spaghetti by mass |
| Stowed can | Opened by the package-opening mechanism (not part of this concept); the open can is clamped in the dock like a box and tilted over the bypass chute; chase with recipe water through the can (SM-119) | M |
| Stowed jar | As a can for pourable contents (gherkins, red cabbage, passata); pastes as above | M |
| Carton (milk, cream, passata) | Opened carton tilted in the dock; partial use: returns upright in its carrier box | M |
| Tub (quark, yoghurt, crème fraîche) | Tub tilted over the tube chute with vibration: about 80 % leaves; the rest is left, or the tub is pressed flat against the chute mouth by the dock clamp. Residue 10–20 % is a real loss (RES-009) | L–M |
| Vacuum pack (meat) | Cut open by the opening mechanism over the slide insert; the piece slides out | M |

What the column adds to dosing: every paste and fat is a syringe with ≤ 1 % residue, and flour and mince are
enclosed from the chute to the pot. What it does not improve at all: getting food out of boxes, tubs and
packs in the first place. That front end is common to all candidates and is as untested here as anywhere.

---

## 4. Operation table

Times are for the 4-person quantity unless stated. "Tube cycle" = turret to FILL, dose, turret to PRESS,
ram picks the piston, press, strip the piston: fixed overhead about 25 s [E].

### 4.1 MEAL-018 (a): no purchase workaround

| Operation | Mechanism and sequence | Time | Conf. | Untested |
|---|---|---|---|---|
| FLP pieces: patty, steak, cutlet, fish, fried potatoes (UO-55) | Frying book. Receiving pan preheated 180–220 °C and oiled by the mister; close, turn, open (6 s). For more than about 30 mL of free fat the loaded leaf is first tilted 25° for 3 s so that fat collects at the hinge-side corner and stays behind | 6–10 s per flip, all pieces at once | M–H | Fat at the rim gasket and the hinge trough; whether a crust sticks to the first pan; fish skin |
| FLP whole-pan items: pancake, omelette, Rösti, tortilla (UO-63) | Round pan 28 on a rotating position; batter from the nozzle die or from a small pot, spread by spinning the pan at 90 rpm for 3 s (SM-097). Flip: shuttle sets the preheated flip lid on the pan, grips the pan lugs, lifts 120 mm, rolls 180°, sets the lid (now below, on its own skirt) on the other round position, rolls the pan back; the item finishes on the lid, which is a flat pan. Or, for omelette and Rösti, rectangular in the book | 12 s per flip | M | SM-128 is a 1/6 idea; pan pair 2.6 kg at 180 mm is 4.6 Nm, fine; pancake centring on the lid |
| ASM layered dishes (LAY, TOP, SPR; UO-43, -90, -91) | The dish (GN 1/2-65 or the braiser) stands at the drop position; the shuttle moves it in X and Y under the fixed outlet while the column deposits: sauce ribbons from the slot die (tube as a depositor, 120 mm wide, three passes), slices straight from the sickle (gratin potatoes fall in rows), cheese from the shred plate or the dock, béchamel poured by the shuttle from its pot along the dish. Lasagne sheets: dropped one at a time from the dock down the slide insert onto the dish, which is moved so that they land side by side | 4–6 min for a four-layer lasagne | M (sauces, slices H; sheets L–M) | Dry lasagne sheets singulating from a tilted box; landing position ±20 mm |
| ASM open-hand: burger, sandwich, toast, taco, wrap (UO-88) | Burger: bun halves laid by tongs on a tray, patty and sliced toppings placed by tongs and by dropping slices from the sickle onto the bun moved under the column, sauce from the nozzle, lid placed by tongs; a ring Ø 100 keeps the stack. Toast Hawaii, croque, bruschetta: same, flat builds. Taco, burrito, fajita, filled wrap, gyros in pita: **not assembled**; served as components (SM-244) | 40–60 s per burger | L–M burger and flat builds; fail for folded and rolled hand food | Tongs skill on soft buns; stack stability to the hatch |
| CAR boneless roast (UO-80) | (a) Roughly cylindrical roasts up to Ø 135: rested roast dropped by the shuttle tongs into a green tube on the open ring, piston on top at 30–50 N, sickle takes one slice per revolution at 30 rpm, ram advance 3–15 mm per revolution; slices fall overlapping into the serving dish moved in X (microtome, SM-015). (b) Slab roasts (crackling roast 250 × 150 × 120, meat loaf): on the HDPE board in a leaf, comb fence held down by the closed second leaf frame, knife stem drawn by the shuttle between the comb teeth (SM-032) | (a) 60 s per kg, (b) 8 s per slice | (a) M, (b) M–L | Hot braised meat tearing at the sickle; juice loss in the tube; shuttle stiffness for a draw cut |
| CAR bone-in poultry (S) | Not done. Birds are cooked whole and served whole, or cooked as parts | — | fail | — |
| UNM (UO-87) | Every tin and mould has a loose floor (SM-117): springform and loaf tin with loose floor, pudding and panna cotta set in a small tube or in ring moulds on a tray. Shuttle inverts the tin onto the board or plate carrier (roll 180°), tin wall lifted off, floor lifted by tongs; or the set dessert is pushed out of its tube by the ram onto the plate, which is the cleanest unmoulding there is | 20–40 s | M–H for piston moulds, M for cakes | Sticking of cakes (as for a human); plate carrier interface to serving |
| SCO (UO-92) | Knife stem on the shuttle, depth by Z with the force signal of the Z drive as touch-off; pork rind: tempered 20 min in the freezer first; proved bread: draw cut at 200 mm/s | 3 s per cut | M | Shuttle as a knife guide: stiffness 0.5 mm at 40 N needed |

### 4.2 MEAL-018 (b): shaping cluster

| Operation | Mechanism and sequence | Time | Conf. | Untested |
|---|---|---|---|---|
| FRB patties (UO-40) | Mass mixed in a red tube (4.3). Tube over former Ø 80; ram advances 7.0 mm per piece for 125 g (each mm of bore 140 feeds 15.4 mL; the Ø 80 strand grows 3.06 mm per mm of ram), wire cut; pucks Ø 80 × 21 drop 60 mm onto the oiled leaf pan held under the die by the shuttle, which indexes between drops | 8 patties in 50 s | H (factory former) | Mass sticking in the former land; drop deformation |
| FRK dumplings, balls (UO-40) | Former insert Ø 45, 40 mm strand = 64 mL, wire cut; pieces fall into simmering water in the 4 L pot brought under the die (steam: the shutter above is closed, downdraft on). Rounding: not done; Klöße are short cylinders with rounded ends after simmering (adapted appearance), or they roll for 5 s in the wet spin basket turning at 60 rpm (tumble rounding, SM-074) | 12 pieces in 60 s | M | Whether a cylinder is accepted as a Kloß; tumble rounding of sticky potato mass |
| FRM gnocchi, Schupfnudeln, croquettes, falafel, cookie blobs (UO-46) | Small tube over the Ø 18 plate (3 strands) or nozzle, wire cut every 20–25 mm, pieces fall on a floured tray or into the pot. Schupfnudel taper: not made, straight cylinders (adapted) | 60 pieces per min | M–H | Dough stiffness window |
| STU rigid cavities (UO-44) | Peppers, tomatoes, apples, baked potatoes, courgette boats stand in the comb rack or a ring tray at the drop position; small tube with nozzle Ø 25 and 60 mm spout; shuttle lifts each cavity to the spout, ram meters by stroke. Cannelloni: tubes stood upright in a rack, filled from above | 6 s per item | H | Standing the cannelloni upright (tongs, 10 s each: L–M) |
| STU flat pockets, dumpling cores, poultry cavity | Dumpling core: co-extrusion is not attempted. Cordon bleu: not done. Poultry: nozzle into the cavity of a bird held in the braiser (M) | — | fail / M | — |
| RLT Rouladen: flatten, spread, fill, roll, secure (UO-42) | See walk-through B1. Flatten in the book between two trays with a silicone interleaf (1.5 kN, SM-089); mustard as a 120 × 2 ribbon from the slot die; onion dice, gherkin sticks and bacon dice fall from the column onto the slice while the tray is indexed; roll by the mat-and-bar method (SM-080): slice lies on a silicone-glass mat in the tray, the shuttle hooks the mat's pull bar and draws the mat over itself against the tray wall; the roll ends seam-down against the comb rack, the mat edge tips it into a rack slot. Secured by the comb rack (SM-084); fallback ferritic pins pressed by the shuttle (SM-085) | 70 s per roll | **L–M** | Everything: first turn, filling squeezed out, roll landing in the slot, seam through 90 min of braising |
| WRP cabbage roll, bacon wrap, biscuit roll, strudel | Bacon wrap and biscuit roll (rolled in its baking mat): same mat roll, L–M. Cabbage rolls: no leaf separation (G7): fail. Strudel with a 400 mm sheet: too large for the GN 1/2 mat: fail | — | L–M / fail | — |
| BRD (UO-41) | In the book, three GN 1/2-20 trays. Flour tray on leaf L (flour sifted in by the sifter cup, 15 g), cutlets laid on it; flour sifted on top; book flips them onto the egg tray (60 g whisked egg spread over the tray by tilting the leaf ±10°); shuttle swaps the flour tray for a second pass of egg: book flips back onto a tray wetted with the remaining egg; shuttle swaps in the crumb tray (bed 40 g), book flips the cutlets onto it, crumbs sifted on top, book closes with an empty tray at 50 N, opens; book flips the cutlets into the hot pan that replaced the egg tray | 3 min per batch of 2 large or 3 small cutlets, 9 shuttle moves | M | Egg coverage on the second face (≥ 95 %); crumbs lost at each flip; two large cutlets (250 × 150) do not fit one leaf side by side: batches of one large or two medium |
| ROL roll out (UO-45) | No roller. Dough is **pressed** in the book between two trays with silicone-glass mats and gauge rails (2, 4, 8 mm) at 2 kN: on a 325 × 265 leaf that is 0.23 bar, enough for rested yeast dough and shortcrust to 3–4 mm, not for 2 mm Flammkuchen or pasta dough [B:A makes the same estimate]. Alternative: extruded as a 120 × 5 band from the slot die laid in three lanes and pressed once to weld the seams | 40 s per sheet | M for 4 mm, L for 2 mm | Spring-back of yeast dough; seam visibility; sheet size is GN 1/2, not tray size: **UO-45 "up to tray size" is missed** |
| SHD loaf, rolls, pizza base, lining a tin | Loaf: dough pushed from the tube into the tin, proofs and bakes there. Rolls: Ø 45 former, 80 g portions, tumble-rounded or left as cut cylinders. Pizza: pressed in the baking tray GN 1/2 (see B5). Lining a tin: dough pressed in the tin by a stepped punch on the ram (springform floor Ø 260 does not fit under a Ø 140 ram: the sheet is pressed flat in the book and the tin ring set on it; a raised rim is not formed: quiche and cheesecake get a flat base only, adapted) | — | M / L for lined rims | — |
| KND, KNM (UO-32) | 4.3 | — | — | — |

### 4.3 Mixing, kneading, whipping in the tube (catalogue question 3)

All in a tube standing on the blank cap D1 (liquid-tight at the bottom; the lip problem of the source
concepts disappears because no liquid ever stands on a piston lip).

| Operation | Sequence | Numbers [E] | Conf. |
|---|---|---|---|
| KND bread and pizza dough, 0.1–1.6 kg | Flour, salt, yeast, water dosed into the tube at FILL. At PRESS the ram takes the knead plunger K110 and strokes it through the mass: going down, the dough must flow up through the 15 mm annular gap (back-extrusion: it is drawn into a tube-shaped sheet, stretch ratio 2.6); the plunger then lifts clear and the dough sheet collapses and folds on itself under its weight and the next stroke. Every 10 strokes the turret swings the tube 5° and back (shake) so that the pattern does not repeat | Annulus 59 cm²; 1–2.5 bar on the plunger face (95 cm²) = 1–2.4 kN; stroke 80 mm at 60 mm/s, 3.5 s per cycle; 100–190 J per stroke; 12–25 kJ/kg × 1.6 kg = 19–40 kJ = 130–300 strokes = **8–17 min**. Small tube for 100–300 g | **L–M**. Not proven: gluten development by back-extrusion; dough riding up with the plunger instead of flowing past it (the plunger is wet or oiled; if it rides, a loose stripper ring rests on the tube rim) |
| KNM mince mass, dumpling mass, Spätzle batter, cookie and shortcrust dough (RUB, MXW stiff) | Same, 25–40 strokes | 1.5–2.5 min | M–H (mixing a paste by forcing it through a gap is reliable; over-working is controlled by stroke count) |
| MXW, WHK batters, dressings, egg mixtures; EMU mayonnaise, vinaigrette; CRM butter and sugar | At SERVICE: perforated dasher D on the crank, 2–3 Hz, 60 mm stroke; oil for mayonnaise trickled from the dock down the tube chute... not possible at SERVICE (the chute is at FILL): mayonnaise is made in the small pot on a rotating position with the whisk bar instead | 30–60 s | M–H batters, M creaming (butter must be 18–20 °C: tempered 60 s on a leaf at 30 °C) |
| WHP egg white, cream, 30 mL to 1.5 L whipped | Mesh dasher M on the crank, 3 Hz, stroke through the whole liquid and 40 mm of air above it. 1 egg white in the small tube (bore 60: 30 mL is 11 mm deep, the dasher works it); 6 whites in the large tube (180 mL, 12 mm deep, foam rises to 100 mm) | 60–120 s | **M** for cream (a French press froths milk and whips cream; known household practice), **L–M** for stiff egg white. Tubes are steel and come out of an 85 °C rinse fat-free, which egg white needs |
| FLD fold | Dasher D, 3 slow strokes by the ram at 20 mm/s | 15 s | M; volume loss unknown |
| Fallback if the dasher does not whip or the plunger does not knead | Whipping: a top-driven whisk on a small spindle replaces the crank at SERVICE (same place, same actuator count; proven, SM-177). Kneading: roller and scraper hung in the 8 L can on a rotating position (SM-171, proven, 20 Nm is provided); the dough then leaves the can by the shuttle tipping it with the scraper, residue 2–4 % [E], and it is no longer enclosed and no longer metered by the ram | — | H. Cost to the concept: the tube stops being the mixing vessel for dough; formed dough products need a transfer can → tube (tip into the tube chute: M) |

### 4.4 Peeling, trimming, cutting, egg

| Operation | Mechanism | Time | Conf. | Untested |
|---|---|---|---|---|
| PLP potato, raw (UO-11) — the one raw peeler (catalogue question 5) | **Rasp can** on a rotating round position: Ø 260 × 200 can with a knurled, etched steel floor and lower wall (no bonded grit), a fixed deflector blade hung from the rear post keeps the charge from turning with the can; 250 rpm, water from the position's nozzle at 1 L/min; slurry leaves through a row of 3 mm slots at the floor edge into the drained ring around the position. 1 kg in 2.5–3 min, loss 15–25 %, eyes remain. Then shuttle tips the can over the tube chute... no: over the drop position into the basket, from where they are re-dosed? **No: peeled potatoes are tipped by the shuttle directly down a short fixed slide on the left wall of bay B into the tube at the SERVICE seat**, which is nearest to bay B | 3 min + 20 s | M (principle proven in commercial peelers with a rotating floor; a rotating can with a fixed deflector is my variant) | Peel quality with a fixed deflector; slurry on the deck ring; loss against PRP-022 (25 %) |
| PLP default (SM-055, SM-056) | Mash: boiled skin-on, riced, skins stay on the ricer plate and are pigged to waste. Bratkartoffeln, potato salad: boiled skin-on, skin slipped in the rasp can run for 20 s (rubbing, not rasping: a rubber-stud liner ring is a further part; without it, skin-on slices, adapted) | — | H mash, M slip | Slipping hot potatoes in a can |
| Carrot, cucumber, asparagus, salsify | Iris die D12: pieces stand in the tube, the piston with a soft face pushes them through one by one? **No: several pieces side by side do not pass one iris.** One piece at a time: the dock drops one carrot, the small tube (bore 60) guides it, the P60 piston pushes it through the iris; peel falls with the carrot and is separated by the diverter timing only poorly. Honest result: peel and carrot land together in a perforated basket and the peel strips are rinsed out through 6 mm holes (M–L) | 12 s per carrot | **L–M** | Almost everything. Fallback: carrots in the rasp can (they break if long: cut to 80 mm first by the sickle), or skin-on, or bought peeled |
| PLA onion (UO-12, S) | Bought peeled (SM-242), as in all candidates. The concept offers one try: top and tail by first-and-last slice in the tube, then the onion pushed through a silicone squeeze ring die (SM-062) | — | L | Not counted |
| Garlic | Skin-on cloves through the ricer plate in the small tube; skins stay and are pigged to waste (SM-064) | 20 s | H | — |
| PLS, PLH | Apple: wedge die with centre tube cores and wedges it (skin on), or the rasp can for a rough peel (L). Kohlrabi, celeriac: rasp can, 30 % loss, or bought peeled. Tomato: blanched in the basket, skins retained by the ricer for sauces | — | M / L | — |
| PLE boiled egg | Eggs with 100 mL of water in the salad can with its lid, shuttle shakes it (roll ±90°, 10 s), shell rinsed out in the basket (SM-065) | 40 s | M | Yield |
| COR apple, pear | Wedge die D6; the fruit must sit stalk-up on the centre tube: it does not self-orient in a bore 140 tube. A centring cone insert (3 fingers) is one more part; expected 80 % centred [E], the rest gives wedges with core pieces | 6 s per fruit | M–L | Orientation |
| COR pepper, cabbage head, pumpkin | Pepper: quartered by the wedge die stalk-up, seeds rinsed out in the spin basket through 8 mm holes (SM-043); white ribs remain. Cabbage head, pumpkin: too large for the tube (section 8) | — | L–M / fail from whole | — |
| TRE ends | Long goods standing in the tube: first slice to waste through the diverter, then the tube is lifted out, turned end for end by the shuttle (roll 180° with the piston holding the load: piston and produce are held by a cap die on top... ) **not credible**; instead the second end is trimmed as the *last* slice: the ram stops 8 mm before the end, the diverter switches to waste, the comb piston pushes the heel out. Beans, sprouts, radishes, mushrooms: not trimmed (bought trimmed or frozen) | +6 s | M for long goods; fail for small goods | Height of the last slice varies by piece: the waste slice is set by the longest piece |
| STR strip, pluck, florets | Not done (G2). Bought as florets, frozen leaf spinach, chopped kale; tender herbs chopped with stems | — | fail from whole | — |
| DIC, JUL (UO-15) | Grid die + sickle, 2.2 | 1 kg mixed vegetables in 3–4 min incl. filling | H (M for the sickle under a full grid) | Onion layers splaying on the 6 mm grid; tomato (crushes: 20 mm grid with a sharp two-tier die only) |
| SLI (UO-14) | Open ring + sickle, thickness = advance per revolution, 1–20 mm. Cucumbers and carrots stand; potatoes lie at random, so gratin slices are not all cross-cuts (accepted) | 1.5 kg in 60 s | H | Tomato and mushroom slices (soft: piston force 5–10 N only, L–M) |
| WED | Wedge die | 5 s | H | — |
| MIN, CHH (UO-16) | Compressed-bundle chiffonade in the small tube: herbs or peeled onion pieces under 50–100 N, sickle at 1.5 mm steps; the pile is pushed back... a second pass is not possible (the slices are in the pot). Result: 1.5 mm ribbons, not a fine mince. Fine mince of onion and garlic: 6 mm grid with 3 mm advance, then, if the recipe demands < 3 mm, the pieces are sweated as they are (adapted: slightly coarser) | 20 s | M; **PRP-021 "fine chopping < 3 mm" is met in one dimension only** | Bruising of basil; wet herbs smearing on the ring |
| GRC, GRF | Block in the small tube against the shred plate, shred arm at 200 rpm. Parmesan, nutmeg, zest: fine shred plate; zest: **not done** (a lemon cannot be pushed through a plate); bought or omitted | 100 g in 15 s | M–H / fail zest | — |
| JUI | Halves on the citrus cone: halving needs the wedge die in 2-blade form and the half must land cut-face down: L. Whole lemon pressed at 3 kN against the 1 mm slot die: juice with peel oil (bitter): L. Honest answer: bottled juice or a tongs-placed half (M–L) | — | L | — |
| SQZ | Grated potato, thawed spinach, salted cucumber pressed against the 1 mm slot die at 3–5 bar; liquid to the diverter, cake pushed out by changing to the open ring (shear gate) | 30 s | H | — |
| MSH, EXT | Ricer 3 mm, Spätzle plate over the simmering pot | 1 kg in 40 s | H | — |
| PUR | **Not a column operation** (pushing a hot soup through a die is not puréeing). An immersion-type blade is missing from this concept; soups are passed through the ricer and then the 1 mm die (cooked vegetables pass, fibres stay): a passed soup, not a blended one (adapted, 15 corpus meals) | 2 min for 2 L in two tube loads | M–L | Texture; hot liquid on the piston lips (it stands on the die, not the lips: fine) |
| POU | Book, 1.5–2 kN between two trays with interleaf, gauge rails 5 mm | 10 s | H | — |
| CRK, SEP | Egg module (common) | 10 s per egg, 12 eggs in 2 min | M | — |
| WLF, DRY | Leaves in the spin basket inside the salad can on a rotating position: flood 1.5 L, 40 rpm with reversal 30 s, shuttle lifts the basket, can is tipped to the drain gutter, basket back in, spin 600 rpm (Ø 240: 48 g) 20 s | 2 min | H (salad spinner) | Imbalance at 600 rpm on a ring drive |
| TOS | Lid on the salad can, shuttle rolls it ±150° four times (SM-186) | 15 s | H | — |
| DRN | Lift-out basket by the shuttle, held 20 s over the pot, then set into the serving vessel or tipped. The pot stays (R7). Pot water is pumped out later by a suction lance on the nozzle bar (venturi, SM-158) or left to cool and tipped at 4 kg | — | H | — |
| Stir, scrape, sauté, deglaze, baste | Rotating positions with hung scraper; liquids from the position's valve or by the shuttle tipping a small pot; basting: shuttle tilts the braiser 15° and the oil mister... **basting is not solved**; roasts are cooked covered or in the combi-steam mode | — | H stir / fail baste | — |
| LIN grease a tin | Oil mister tool | 5 s | M | — |
| GLZ | Mister for egg wash thinned with milk (M–L), otherwise not done | — | L | — |
