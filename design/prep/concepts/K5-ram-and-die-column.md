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
| Dasher M (mesh), M1 | disc Ø 136 with a 1.5 mm (M) or 1 mm (M1) woven mesh welded in a ring, same stem | M: whipping egg white and cream; M1: puréeing as a reciprocating sieve |
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
| D1 | Blank cap, two forms | (a) carousel cap: flat disc with a moulded silicone face gasket, liquid-tight under the tube's own weight plus 200 N; (b) stopper cap: a silicone-rimmed plug pressed 15 mm into the bore (holding force about 50 N), which stays in the tube when the shuttle lifts it, so that a capped tube is a can that can stand at the drop position, be tipped, or go to cold storage | custom, simple |
| D2 | Open ring | Ø 140 opening, knife-edge exit | custom |
| D3 | Grid 10 mm, two-tier | X blades 9 mm above Y blades, neighbours staggered by 6 mm (SM-010) | custom (eroded); blade geometry copied from push dicers |
| D4 | Grid 6 mm, two-tier | onion, fine dice | custom |
| D5 | Grid 20 mm / fries 10 × 10 long | stews, fries, sticks | custom |
| D6 | Wedge die with centre tube Ø 22 | 8 radial blades; core goes up the centre tube (SM-041) | custom |
| D7 | Ricer plate, 3 mm holes, 30 % open | mash, passata, skin-on garlic | bought plate, custom rim |
| D8 | Spätzle plate, 8 mm holes | also gnocchi strands with the Ø 18 version | bought plate |
| D9 | Former Ø 80 (and Ø 45 insert) | 30 long land, polished | custom |
| D10 | Nozzle Ø 18 / Ø 25 with a 60 mm spout; the Ø 18 version with a bought silicone duckbill valve in the spout (opens above about 0.1 bar) | stuffing, piping; thin batters are mixed directly on the duckbill version and metered by the ram | custom, valve bought |
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

**Mixer crank.** At the SERVICE position a light reciprocating drive in the dry zone (slider crank with a
fixed 60 mm throw; the whole crank unit rides on a lead screw that sets the working height; rod Ø 20 through
its own collar; two actuators: crank motor and height screw)
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
welded stem), comb fence, sifter cup (mesh-bottom cup for flour and crumbs), oil mister (bought pump spray
head actuated by the jaw), ladle, core-temperature probe. Eight tools, parked on cone pegs on the rear
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
| Pistons, dashers | P140 ×4, P60 ×2, C10, C6, K110, D, M, M1, spray dasher | 13 | custom turned parts |
| Dies | D1 ×2, D2 ×2, D3–D15 | 17 | custom plate parts; D7, D8 bought plates |
| Cutting arms | sickle ×2 (green, red), wire bow, shred arm | 4 | blade bought, stem custom |
| GN ware | pan GN 1/2-40 tri-ply ×3, tray GN 1/2-20 ×3, GN 1/2-65 ×2, GN 1/2-100 braiser with lid ×1, griddle ×1, perforated GN 1/2-65 ×1, HDPE board GN 1/2 ×1, handle plates ×4 | 16 | bought; handle plates custom |
| Round ware | pot 9 L, 4 L ×2, 1.5 L ×2, pan 28 + flip lid, baskets ×2, rasp can, salad can + spin basket, lids ×4, scrapers ×3, whisk bar | 21 | bought pots with welded skirt and lugs; rasp can custom |
| Fixtures | Rouladen comb rack (GN 1/2), rolling mat with pull bar (silicone-glass, 300 × 250) ×2, springform 26 with loose floor, loaf tin with loose floor, muffin tray, baking tray GN 2/3 ×2, ring Ø 100 (burger and layered builds) | 9 | bought, mat bar custom |
| Stem tools | tongs ×2, turner, knife, comb fence, sifter cup ×2, oil mister, ladle, probe | 10 | custom stems, bought blades |
| **Total loose Zone F items** | | **about 96 pieces of 44 types** | |

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
Between the two chute mouths sits a small swing arm (one actuator) carrying the **weigh cup** (0.3 L, on a
300 g cell) and the egg inspection cup; it dumps into either chute. Seasoning is weighed into the cup in dry
air with the chute shutters closed, then dropped (SM-141).

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
| Egg | Egg module at the bypass chute (SM-164 baseline, SM-165 as the fallback): two cups take the egg from the tray insert of the box, score, pull apart over the clear inspection cup on the small load cell; camera check; the cup tips into the tube chute or the bypass chute, or, for a reject, into the bypass chute with the diverter set to waste. Separation by a slotted cup. 3 actuators | 10 s per egg; M (shared with all candidates) |
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
| MXW, WHK batters, dressings, egg mixtures; CRM butter and sugar | At SERVICE: perforated dasher D on the crank, 2–3 Hz, 60 mm stroke. Pourable batters are mixed directly on the nozzle die with duckbill (D10), so that no die change under a liquid is needed. EMU with a slow oil feed (mayonnaise, hollandaise) cannot be done at SERVICE, which has no chute: it is made in the 1.5 L pot on a rotating position with the whisk bar, oil dosed in steps at the drop position (M) | 30–60 s | M–H batters, M creaming (butter must be 18–20 °C: tempered 60 s on a leaf at 30 °C) |
| WHP egg white, cream, 30 mL to 1.5 L whipped | Mesh dasher M on the crank, 3 Hz, stroke through the whole liquid and 40 mm of air above it. 1 egg white in the small tube (bore 60: 30 mL is 11 mm deep, the dasher works it); 6 whites in the large tube (180 mL, 12 mm deep, foam rises to 100 mm) | 60–120 s | **M** for cream (a French press froths milk and whips cream; known household practice), **L–M** for stiff egg white. Tubes are steel and come out of an 85 °C rinse fat-free, which egg white needs |
| FLD fold | Dasher D, 3 slow strokes by the ram at 20 mm/s | 15 s | M; volume loss unknown |
| Fallback if the dasher does not whip or the plunger does not knead | Whipping: a top-driven whisk on a small spindle replaces the crank at SERVICE (same place, same actuator count; proven, SM-177). Kneading: roller and scraper hung in the 8 L can on a rotating position (SM-171, proven, 20 Nm is provided); the dough then leaves the can by the shuttle tipping it with the scraper, residue 2–4 % [E], and it is no longer enclosed and no longer metered by the ram | — | H. Cost to the concept: the tube stops being the mixing vessel for dough; formed dough products need a transfer can → tube (tip into the tube chute: M) |

### 4.4 Peeling, trimming, cutting, egg

| Operation | Mechanism | Time | Conf. | Untested |
|---|---|---|---|---|
| PLP potato, raw (UO-11) — the one raw peeler (catalogue question 5) | **Rasp can** on a rotating round position: Ø 260 × 200 can with a knurled, etched steel floor and lower wall (no bonded grit); a fixed deflector blade hung from the rear post keeps the charge from turning with the can; 250 rpm, water from the position's nozzle at 1 L/min; slurry leaves through a row of 3 mm slots at the floor edge into the drained ring around the position. 1 kg in 2.5–3 min, loss 15–25 %, eyes remain. The shuttle then tips the can onto a fixed slide in the wall between bay B and bay A, which leads into the tube standing at the SERVICE seat (the seat nearest to bay B) | 3 min + 20 s | M (commercial peelers have a rotating floor in a fixed wall; a rotating can with a fixed deflector is my variant) | Peel quality with a fixed deflector; slurry on the deck ring; loss against PRP-022 (25 %) |
| PLP default (SM-055, SM-056) | Mash: boiled skin-on, riced, skins stay on the ricer plate and are pigged to waste. Bratkartoffeln, potato salad: boiled skin-on, skin slipped in the rasp can run for 20 s (rubbing, not rasping: a rubber-stud liner ring is a further part; without it, skin-on slices, adapted) | — | H mash, M slip | Slipping hot potatoes in a can |
| Carrot, cucumber, asparagus, salsify | Iris die D12 under the small tube (bore 60), one piece at a time: the dock drops one carrot, the tube guides it, the P60 piston pushes it through the iris. Several pieces side by side cannot pass one iris, so this is slow. Peel and carrot fall together; they land in a perforated basket and the peel strips are rinsed out through 6 mm holes | 12 s per carrot | **L–M** | Almost everything: blade following, peel separation, pieces thicker than the bore. Fallbacks: rasp can after cutting to 80 mm lengths with the sickle; skin-on; bought peeled |
| PLA onion (UO-12, S) | Bought peeled (SM-242), as in all candidates. The concept offers one try: top and tail by first-and-last slice in the tube, then the onion pushed through a silicone squeeze ring die (SM-062) | — | L | Not counted |
| Garlic | Skin-on cloves through the ricer plate in the small tube; skins stay and are pigged to waste (SM-064) | 20 s | H | — |
| PLS, PLH | Apple: wedge die with centre tube cores and wedges it (skin on), or the rasp can for a rough peel (L). Kohlrabi, celeriac: rasp can, 30 % loss, or bought peeled. Tomato: blanched in the basket, skins retained by the ricer for sauces | — | M / L | — |
| PLE boiled egg | Eggs with 100 mL of water in the salad can with its lid, shuttle shakes it (roll ±90°, 10 s), shell rinsed out in the basket (SM-065) | 40 s | M | Yield |
| COR apple, pear | Wedge die D6; the fruit must sit stalk-up on the centre tube: it does not self-orient in a bore 140 tube. A centring cone insert (3 fingers) is one more part; expected 80 % centred [E], the rest gives wedges with core pieces | 6 s per fruit | M–L | Orientation |
| COR pepper, cabbage head, pumpkin | Pepper: quartered by the wedge die stalk-up, seeds rinsed out in the spin basket through 8 mm holes (SM-043); white ribs remain. Cabbage head, pumpkin: too large for the tube (section 8) | — | L–M / fail from whole | — |
| TRE ends | Long goods standing in the tube: the first slice goes to waste through the diverter; the second end is trimmed as the last slice: the ram stops 8 mm before the end, the diverter switches to waste and the comb piston pushes the heel out. Turning the load end for end is not possible. Beans, sprouts, radishes, mushrooms: not trimmed (bought trimmed or frozen) | +6 s | M for long goods; fail for small goods | Pieces of unequal length: the waste slice is set by the longest piece, the others keep their tip |
| STR strip, pluck, florets | Not done (G2). Bought as florets, frozen leaf spinach, chopped kale; tender herbs chopped with stems | — | fail from whole | — |
| DIC, JUL (UO-15) | Grid die + sickle, 2.2 | 1 kg mixed vegetables in 3–4 min incl. filling | H (M for the sickle under a full grid) | Onion layers splaying on the 6 mm grid; tomato (crushes: 20 mm grid with a sharp two-tier die only) |
| SLI (UO-14) | Open ring + sickle, thickness = advance per revolution, 1–20 mm. Cucumbers and carrots stand; potatoes lie at random, so gratin slices are not all cross-cuts (accepted) | 1.5 kg in 60 s | H | Tomato and mushroom slices (soft: piston force 5–10 N only, L–M) |
| WED | Wedge die | 5 s | H | — |
| MIN, CHH (UO-16) | Compressed-bundle chiffonade in the small tube: herbs or peeled onion pieces under 50–100 N, sickle at 1.5 mm steps. A second pass at 90° is not possible, because the slices are already in the pot. Result: 1.5 mm ribbons, not a fine mince. Onion and garlic: 6 mm grid with 3 mm advance; where the recipe demands < 3 mm the pieces are used as they are (slightly coarser) | 20 s | M; **PRP-021 "fine chopping < 3 mm" is met in one dimension only** | Bruising of basil; wet herbs smearing on the ring |
| GRC, GRF | Block in the small tube against the shred plate, shred arm at 200 rpm. Parmesan, nutmeg, zest: fine shred plate; zest: **not done** (a lemon cannot be pushed through a plate); bought or omitted | 100 g in 15 s | M–H / fail zest | — |
| JUI | Halves on the citrus cone: halving needs the wedge die in 2-blade form and the half must land cut-face down: L. Whole lemon pressed at 3 kN against the 1 mm slot die: juice with peel oil (bitter): L. Honest answer: bottled juice or a tongs-placed half (M–L) | — | L | — |
| SQZ | Grated potato, thawed spinach, salted cucumber pressed against the 1 mm slot die at 3–5 bar; liquid to the diverter, cake pushed out by changing to the open ring (shear gate) | 30 s | H | — |
| MSH, EXT | Ricer 3 mm, Spätzle plate over the simmering pot | 1 kg in 40 s | H | — |
| PUR | **Reciprocating sieve**: the cooked soup or sauce stands in a capped tube (2 L per load); a mesh dasher with 1 mm mesh (M1) is worked through it by the crank at 2–3 Hz for 60 s, so that every soft piece is forced through the mesh many times (a passe-vite with a moving sieve). Fibres and skins collect on the mesh. Stiff purées (hummus, 0.5 kg): the same dasher on the main ram at 1–2 kN, 20 strokes | 2 min for 2 L in one or two tube loads; +4 shuttle moves (soup in and out of the tube by tipping the pot into the tube chute: only for ≤ 4 kg pots) | M–L | Particle size against the < 1 mm requirement; hot soup splashing at 3 Hz (lid ring on the tube); tipping 2 L of hot soup into a chute |
| POU | Book, 1.5–2 kN between two trays with interleaf, gauge rails 5 mm | 10 s | H | — |
| CRK, SEP | Egg module (common) | 10 s per egg, 12 eggs in 2 min | M | — |
| WLF, DRY | Leaves in the spin basket inside the salad can on a rotating position: flood 1.5 L, 40 rpm with reversal 30 s, shuttle lifts the basket, can is tipped to the drain gutter, basket back in, spin 600 rpm (Ø 240: 48 g) 20 s | 2 min | H (salad spinner) | Imbalance at 600 rpm on a ring drive |
| TOS | Lid on the salad can, shuttle rolls it ±150° four times (SM-186) | 15 s | H | — |
| DRN | Lift-out basket by the shuttle, held 20 s over the pot, then set into the serving vessel or tipped. The pot stays (R7). Pot water is pumped out later by a suction lance on the nozzle bar (venturi, SM-158) or left to cool and tipped at 4 kg | — | H | — |
| Stir, scrape, sauté, deglaze, baste | Rotating positions with hung scraper; liquids from the position's valve or by the shuttle tipping a small pot. Basting (BST, 9 meals): the shuttle tilts the roasting vessel 15°, a ladle stem tool scoops at the low corner and pours over the roast (3 scoops) | 40 s per basting | H stir; M–L baste | Ladle path in a hot oven-side vessel; the oven door is open 60 s |
| LIN grease a tin | Oil mister tool | 5 s | M | — |
| GLZ | Mister for egg wash thinned with milk (M–L), otherwise not done | — | L | — |

---

## 5. Benchmark walk-throughs

Conventions: t = minutes from start. "Move" = one shuttle pick-carry-place, one book cycle, or one turret or
carousel index with a loaded tube (dock tilts and ram strokes are not moves). Vessel names as in 2.6.
G = green tube (RTE and produce), R = red tube (class R). Onions and garlic are bought peeled (SM-242).
Elapsed times are estimates built from the step times of section 4; T_ref and limits from PERF-001/-002.

### B1 Rinderrouladen, Rotkohl, Salzkartoffeln (4 persons) — limit 183 min

| t | Step | Where, vessel | Moves |
|---|---|---|---|
| 0 | Red cabbage: bought as a quartered, cored head piece ≤ Ø 135 (a whole head does not fit the tube: section 8). Quarters into tube G1, open ring, sickle 3 mm: 800 g of shreds fall into the 4 L pot. One apple through the wedge die (core to waste), 1 onion through grid 6 | column → 4 L pot at the drop position | 4 |
| 6 | Pot to rear position L, scraper hung, fat, vinegar, stock from valves and dock; braise 90 min, pot turning 2 rpm | rear L | 2 |
| 8 | 4 Rouladen slices tilt-slid from their pack onto tray 1 (with silicone interleaf) at the drop position; tongs spread them if they overlap | tray 1, tongs R | 3 |
| 11 | Tray 1 into leaf L, tray 2 (interleaf) into leaf R; book closes at 1.5 kN on 5 mm rails, opens: slices lie on tray 2, flattened | book | 3 |
| 13 | Filling prepared into a 1.5 L pot: 2 onions grid 6; 4 gherkins (from the jar, tilt) as sticks through grid 10 with 40 mm advance; bacon bought diced | column, tube G2, sauce pot | 3 |
| 17 | Mustard: small tube from cold storage onto the slot die. Shuttle holds tray 2 under the die and moves it in Y: one 120 × 2 ribbon per slice (12 g) | tray 2 | 3 |
| 19 | Filling: shuttle tips the sauce pot along the four slices in one pass (35 g per slice ± 30 %); salt, pepper from the weigh cup over the moving tray | tray 2 | 2 |
| 21 | Rolling: slices must lie on the rolling mat. The mat was the interleaf of tray 2, its pull bar at the hinge side. For each slice: shuttle (hook on the tongs stem) draws the bar over; the slice rolls up; the roll is dragged to the tray edge and tipped seam-down into a slot of the comb rack standing in the GN 1/2-65 braiser on leaf L, which is tilted 20° toward the book centre as a receiving ramp | tray 2, mat, comb rack, braiser | 4 × 3 = 12 |
| 27 | Sear: braiser on leaf L at 220 °C, rolls seam-down 3 min; book flips rolls with the rack into a second GN 1/2-65 (preheated), 3 min; onion and carrot dice from the column (braiser taken to the drop position), deglaze with wine and stock from the dock, lid on | book, 2 braisers | 6 |
| 38 | Braise 90 min at leaf L, 95 °C, or in the oven at 160 °C (shuttle carries it in; lift door) | oven | 1 |
| 95 | Potatoes: 1 kg into the rasp can on rear R, 3 min, tipped down the slide into tube G1; wedge die (halves and quarters) into the 4 L pot with basket at the drop position; water from the valve, salt as brine; to rear R, boil 22 min | rasp can, tube, pot 2 | 6 |
| 128 | Braiser out; rack with rolls lifted by tongs onto the warm GN tray (leaf R, 70 °C). Sauce: the braiser is tipped by the shuttle into the 1.5 L pot on rear R (unstrained), starch slurry dosed, thickened there with the scraper at 40 rpm | braiser, sauce pot | 4 |
| 135 | Potato basket lifted, drained 20 s, to the hand-over; cabbage pot, Rouladen tray, sauce (tipped into the 1.5 L pot) to the hand-over | — | 6 |

**Result: adapted, low–medium confidence.** Untied rolls held by a comb rack (pins as the fallback are
traditional, but untested here); thickening in a rectangular braiser without a scraper is weak (the sauce
is better finished in a round pot: +2 moves); sauce not strained. Elapsed **about 140 min** (limit 183).
**Moves: about 54.** Soiled: 2 large tubes + 1 small, 3 pistons, 4 dies, sickle, 3 trays, mat, 2 braisers,
rack, 2 pots + sauce pot, basket, rasp can, tongs, scraper: **about 24 items**.

### B2 Wiener Schnitzel, Bratkartoffeln, Gurkensalat (4 persons) — T_ref 50, limit 68 min

| t | Step | Moves |
|---|---|---|
| 0 | Potatoes (boiled the day before or now: 1 kg skin-on in the basket, 4 L pot, rear L, 22 min). Meanwhile cucumber salad: 2 cucumbers stand in tube G1, open ring, sickle 2 mm, slices fall into the salad can; dressing (vinegar, oil, brine, sugar, dill frozen-chopped) dosed from the dock into the can; lid, shuttle tosses; to the hand-over cold | 6 |
| 8 | Cutlets: 4 bought thin cutlets slid onto tray 1; flattened in the book to 5 mm (as B1) | 5 |
| 12 | 2 eggs by the egg module into the small tube on a blank cap, dasher 10 s at SERVICE; poured: the small tube is lifted by the shuttle and tipped over egg tray 2 | 4 |
| 15 | Breading as 4.2, two batches of two cutlets: flour tray → egg tray → egg again → crumb tray → press → pan. Pan GN 1/2-40 on leaf R with 60 mL clarified butter at 170 °C | 2 × 9 |
| 22 | Potatoes drained, skins slipped in the rasp can 20 s (or left on), tipped into tube G2, sickle 5 mm, slices fall into the second GN pan with fat; onion through grid 6 on top | 6 |
| 25 | Frying. The book has two leaves and both are wanted: Schnitzel (2 batches × 2 × 2.5 min with one flip each) and Bratkartoffeln (15 min, turned every 3 min). Schedule: Schnitzel batch 1 on R, flip into a third pan on L, out to the warm tray in the oven at 70 °C; batch 2 the same; then potatoes on L, flipped L↔R five times. The potatoes therefore start at t = 33 | 4 + 4 + 8 |
| 50 | Potatoes done; all to the hand-over; lemon wedges: wedge die, a lemon stands any way up: accepted | 5 |

**Result: yes, medium confidence** (breading coverage and the fat at the book rim are the open points).
With a pan of 60 mL fat the pre-flip tilt is mandatory. Elapsed **about 55 min** (limit 68). **Moves: about
60.** Soiled: 2 tubes + small tube, 3 pistons, dasher, 3 dies, sickle, 3 trays, 3 pans, pot, basket, rasp
can, salad can, tongs, sifter cup: **about 23 items**. Breading trays and crumbs that touched raw meat are
discarded and washed at once (class R).

### B3 Frikadellen, Kartoffelpüree, Erbsen-Möhren (4 persons) — T_ref 35, limit 50 min

| t | Step | Moves |
|---|---|---|
| 0 | Potatoes 1 kg skin-on, halved by the wedge die into the 4 L pot with basket, water, rear L, boil 20 min | 3 |
| 3 | Carrots 300 g: stand in tube G1, grid 10 with 10 mm advance (skin on, washed in the basket first: +1 move; or bought peeled), into the 1.5 L pot; frozen peas 300 g by the bypass chute; water, butter dose; rear R, simmer 10 min with scraper | 4 |
| 7 | Mince mass in tube R1. The onion is diced first: tube R1 on a stopper cap stands at the drop position as the receiving vessel (shuttle, 2 moves) while tube G1 dices 1 onion on grid 6 into it. R1 back to the turret, FILL: stale roll (bought as cubes) with 80 mL milk, 500 g mince down the tube chute, 1 egg, mustard dose, salt, pepper. PRESS: knead plunger, 30 strokes, 2 min | 5 |
| 13 | Tube R1 slid from the cap window onto the former Ø 80 (shear gate: a film of mince on 60° of the carousel); 8 pucks of 95 g fall onto the oiled pan held by the shuttle, which then sets the pan into leaf L at 170 °C | 3 |
| 15 | Fry 4 min, book flip into the preheated pan on leaf R, fry 4 min; bread pig not needed (the roll went in first); piston pigs the tube, the last 15 g go onto the pan as a small ninth puck | 2 |
| 22 | Potatoes: basket lifted and drained, tipped down the slide into tube G2 on the ricer plate; ram 3 kN; mash falls into the emptied, still hot 4 L pot brought to the drop position (water was pumped out by the lance); skins stay and are pigged to waste. Hot milk 150 mL (from the carton at the dock, warmed in the pot first) and butter dose, scraper folds it in at 30 rpm, 40 s | 7 |
| 28 | Vegetables drained through the lid gap by tipping over the gutter (1.5 L pot, 1 kg: allowed), butter, parsley (frozen) | 2 |
| 30 | All to the hand-over | 4 |

**Result: yes, high–medium confidence.** This is the concept's home ground; only the plunger mixing of the
mass is new (M–H). Elapsed **about 32 min** (limit 50). **Moves: about 30.** PRP-023 (12 patties in 5 min):
met, 12 pucks in 75 s. Soiled: 3 tubes, 3 pistons + plunger, 5 dies, wire bow, sickle, 2 pans, 3 pots,
basket, scrapers 2: **about 20 items**; mince film on the carousel plate.

### B4 Spaghetti Bolognese with grated cheese (4 persons) — limit 96 min

| t | Step | Moves |
|---|---|---|
| 0 | Soffritto: 2 onions grid 6, 2 carrots and 1 celery stalk grid 6 (upright in tube G1), garlic through the ricer in the small tube: all into the 4 L pot at the drop position with oil | 5 |
| 5 | Pot to rear L, scraper, sauté 6 min at 140 °C, 20 rpm | 1 |
| 11 | 400 g mince: pot back to the drop position, mince down the bypass chute (slide insert), back; sear at 200 °C, scraper breaks it up poorly: clumps of 20–30 mm remain unless the mince is first pushed through the Spätzle plate as 8 mm strands from tube R1 (then it crumbles well): +3 moves | 5 |
| 18 | Tomato paste dose (small tube), wine and stock (dock), tinned tomatoes (can tilted), simmer 45 min, lid on | 4 |
| 50 | 9 L pot filled with 4.5 L from the hot-water valve on rear R (never carried full), boil. 400 g spaghetti are dosed dry, endwise, down the bypass chute into the lift-out basket standing at the drop position; the shuttle lowers the basket into the boiling pot | 4 |
| 62 | Basket lifted, drained 20 s, set into the warm serving vessel; sauce pot to the hand-over | 4 |
| 64 | Parmesan block in the small tube against the fine shred plate: 40 g into a small bowl | 3 |

**Result: yes, medium–high.** Elapsed **about 68 min** (limit 96). **Moves: about 26.** Spaghetti 250 mm
long in a Ø 240 basket lean out until they soften: the 9 L pot is 200 deep, so 50 mm stand proud for the
first minute (a cook has the same). Soiled: 2 tubes + 2 small, 4 pistons, 4 dies, sickle, shred arm, 2 pots,
basket, scraper: about 17 items.

### B5 Pizza with yeast dough from flour (2 trays)

| t | Step | Moves |
|---|---|---|
| 0 | Tube G1 on the blank cap at FILL: 500 g flour (mesh lid), 7 g dry yeast and 8 g salt from the weigh cup (its swing arm reaches both chutes), 325 mL water at 30 °C | 1 |
| 3 | PRESS: knead plunger, 200 strokes, 12 min (untested) | 1 |
| 15 | Proof 45 min in the tube at 30 °C: the tube is carried to a leaf at 32 °C with a lid; 825 g of dough (0.75 L) rises to 1.6 L = 105 mm in the tube, inside the 300 | 2 |
| 60 | Back to PRESS, press piston, open ring: two portions of 410 g (each 24.4 mm of stroke) wire-cut onto two baking trays GN 1/2 lined with a baking mat, oiled by the mister | 4 |
| 63 | Each tray into the book under a second tray with mat and 4 mm rails, pressed at 2 kN for 10 s, twice with 30 s rest (spring-back). Result: a rectangular base about 300 × 240 × 4–5 mm with a thicker irregular edge | 6 |
| 68 | Tomato sauce from the slot die in three lanes per tray (tray moved by the shuttle under the column); mozzarella block through the 20 mm grid with 5 mm advance (slabs) or the coarse shred plate, falling on the moving tray; salami bought sliced: dropped from the pack by tilting, lands in a heap: spread by tongs (8 placements) or accepted as a heap per quarter | 10 |
| 76 | Oven 250 °C (preheated from t = 55), trays in one after the other (the cavity takes two GN 1/2 on two levels if the combi has fan heat: one load), 10–12 min | 4 |
| 90 | Out to the hand-over; slicing belongs to serving | 2 |

**Result: adapted, low–medium.** Pressed rectangular bases of GN 1/2 size instead of rolled round or
tray-size ones (two GN 1/2 trays are 0.17 m², one 400 × 300 tray is 0.12 m²: quantity is met, format is
not); kneading by plunger is unproven; salami placement is poor. With the fallback kneader (rotating can)
the dough step becomes high confidence and the verdict stays "adapted" for the pressing. Elapsed **about
92 min** (T_ref 90, limit 114). **Moves: about 30.**

### B6 Gemüseeintopf from whole vegetables (6 persons) — T_ref 35, limit 60 min

| t | Step | Moves |
|---|---|---|
| 0 | 1 kg potatoes in the rasp can, 3 min; meanwhile carrots (400 g) washed in the basket under the valve, then upright in tube G1, grid 10, into the 9 L pot standing at the drop position (empty it weighs 2.2 kg) | 5 |
| 4 | Leek (2): stands in the tube, first slice to waste (root), sickle 8 mm on the open ring; the green top 60 mm is the last slice region, to waste. **Sand between the leek layers is not washed out** (WLF for leek needs the rings washed afterwards: rings fall into the basket, flooded and spun on rear R, then tipped into the pot: +4 moves) | 6 |
| 9 | Celeriac 300 g: bought as a peeled half ≤ Ø 135 or peeled in the rasp can with 30 % loss; wedge die, then grid 10 | 3 |
| 12 | Kohlrabi 1, green beans 200 g (frozen, trimmed: bypass chute), potatoes from the rasp can down the slide into the tube, grid 20 | 5 |
| 16 | Pot (now 2.6 kg of vegetables) carried to rear L: 4.8 kg, within payload. Butter, sauté 3 min with scraper, 2 L stock from the valve and a stock dose, simmer 20 min | 2 |
| 40 | Parsley (frozen) and seasoning; the pot is not carried full (5 kg of soup + 2.2 kg = 7.2 kg, inside the 9 kg payload but it sloshes): it goes to the hand-over at 0.1 m/s with the lid on | 2 |

**Result: yes, high** for the cutting (the concept's best case: 2.6 kg of vegetables diced in about 12 min
with one tube and two dies), **adapted in detail** for celeriac and beans bought prepared. PRP-023 (1 kg
mixed vegetables in ≤ 6 min): met for carrots, potatoes, kohlrabi; leek with its wash is slower. Elapsed
**about 45 min**. **Moves: about 23.** Soiled: 1–2 tubes, 2 pistons, 4 dies, sickle, rasp can, basket,
9 L pot, scraper: about 12 items.

### B7 Steak, oven fries, mixed salad with vinaigrette (2 persons) — limit 79 min (with baked potato)

| t | Step | Moves |
|---|---|---|
| 0 | Oven to 220 °C fan. 600 g potatoes in the rasp can (3 min), down the slide into tube G1, fries die 10 × 10 with the ram running through without a face cut (sticks as long as the potato), into the salad can; 15 mL oil, salt; lid, toss; tipped onto the baking tray GN 2/3, spread by shaking the tray (shuttle Y dither); into the oven, 25 min, tray shaken once at 12 min | 10 |
| 8 | Salad: a lettuce head does not come apart by tilting. A small head (romaine heart, little gem, ≤ Ø 135) is pushed through the 8-wedge die and the wedges fall into the basket in the salad can; an iceberg or butterhead of Ø 180 does not fit and is bought as washed leaves. Wash, spin. Cucumber 3 mm and carrot through the coarse shred plate, tomato wedges (wedge die; soft, they squash somewhat), all into the dried can | 9 |
| 16 | Vinaigrette in the small tube on a blank cap: oil, vinegar, mustard dose, brine; dasher 10 s; kept until serving, then tipped over the salad and tossed | 4 |
| 20 | Steaks: 2 × 200 g slid onto a cold tray, salted (brine mist) at t = 5 so that they temper; pan on leaf L to 240 °C, oil mist; tray tipped by the shuttle so that the steaks slide into the pan (placement ±30 mm; tongs correct) | 3 |
| 27 | Sear 2 min, book flip into the 240 °C pan on leaf R, 2 min; core temperature by the probe stem tool (its signal path is an open issue, 12.1); until that exists, doneness by time and by thickness measured by the camera on the tray | 2 |
| 31 | Rest 5 min on the warm tray; fries out; salad dressed | 6 |

**Result: yes for steak and salad from small heads, adapted for fries (oven, permitted by X-01); medium.**
Elapsed **about 38 min**. **Moves: about 34.** Basting the steak with butter (BST in the corpus row) is not
done. Soiled: tube + small tube, dies 3, rasp can, salad can + basket, 2 pans, 2 trays, tongs: about 15.

### B8 Pfannkuchen (8 pieces) — T_ref 35, limit 50 min

| t | Step | Moves |
|---|---|---|
| 0 | Tube G1 on the nozzle die D10 (duckbill) at FILL: 250 g flour, 500 mL milk, 3 eggs (egg module, inspection cup tipped into the tube chute), salt as brine. SERVICE: perforated dasher 40 s. Rest 20 min in the tube | 2 |
| 22 | Tube with its nozzle die (duckbill closed under 70 mm of batter) co-rotates to PRESS; press piston set on the batter | 1 |
| 23 | Pan 28 on rear L at 190 °C, oil mist. Shuttle carries the pan to the drop position (cools 10 K), press piston doses 95 mL (6.2 mm of stroke) in 2 s, shuttle returns the pan, ring drive spins 90 rpm for 3 s: the batter spreads | 2 |
| 24 | 50 s; flip with the flip lid (12 s), second side 40 s on the lid at rear R; the lid is tipped over the warm stack tray (pancake slides off); meanwhile the pan is already refilled. Cycle 1 pancake per 95 s with two positions | 4 per piece |
| 37 | Eighth pancake done | — |

**Result: yes, medium–low.** Three untested mechanisms in series (duckbill metering of a thin batter, spin
spreading, flip lid). Simpler variant with higher confidence: rectangular pancakes 300 × 240 in the book
(batter dosed from the nozzle onto the leaf pan held under the column, spread by tilting the leaf, book flip):
adapted shape.
Elapsed **about 38 min** (limit 50). **Moves: about 40.** Soiled: tube, piston, dasher, 2 dies, pan, lid,
tray: 8 items, the fewest of all benchmarks.

### B9 Chicken curry with rice (4 persons)

| t | Step | Moves |
|---|---|---|
| 0 | Rice 280 g by the bypass chute into the basket, rinsed under the valve, tipped into a 4 L pot (cooked volume 1.1 L; the 1.5 L pot is too small with the lid and scraper); 560 mL water, brine; rear R, absorption 15 min with lid, rest 10 | 5 |
| 4 | Onion grid 6, garlic and ginger (unpeeled ginger through the ricer in the small tube: fibres and skin stay) into the second 4 L pot; pepper: bought as frozen strips (coring from whole: L–M) | 5 |
| 9 | Sauté on rear L with scraper 5 min; curry paste dose from a small tube | 2 |
| 14 | Chicken breast 500 g: tempered 25 min in the freezer beforehand (scheduler; request X7), two fillets into tube R1 (they fit lengthwise), grid 20 with 20 mm advance: cubes fall into the pot brought to the drop position. Untempered chicken does not dice (it extrudes through the grid as ragged strips): then bought cut | 4 |
| 18 | Sear 4 min, coconut milk (can tilted), simmer 15 min | 2 |
| 35 | Coriander (frozen), lime juice (bottled); both pots to the hand-over | 3 |

**Result: yes, medium** (tempered-meat dicing M; without it, bought diced chicken: still "yes" under
MEAL-012 a). Elapsed **about 38 min** (T_ref 40). **Moves: about 21.** Soiled: 2 tubes + 2 small, 3 dies,
sickle, 2 pots, basket, scraper: about 14; the red tube and grid get the disinfecting wash.

### B10 Lasagne, béchamel from scratch (GN 1/2-65 dish) — limit 148 min with salad

| t | Step | Moves |
|---|---|---|
| 0 | Bolognese as B4 (steps 0–18), simmer 40 min | 15 |
| 25 | Béchamel in the 1.5 L pot on rear R with the whisk bar: 50 g butter (small tube, 19 mm), melt; 50 g flour by the bypass chute (the pot comes to the drop position; steam is low at this stage), 2 min roux at 60 rpm; 600 mL milk in four portions from the carton at the dock (pot at the drop position each time: 8 moves; milk is not plumbed); whisk 6 min to 90 °C; nutmeg, brine | 10 |
| 45 | Oven to 180 °C. Assembly, dish GN 1/2-65 oiled. The shuttle has one fork, so it cannot hold the dish under the column and pour from a pot at the same time: poured layers are laid with the dish standing on leaf L, deposited layers with the dish at the drop position. (1) Bolognese: pot tipped along the dish on leaf L in two lanes, levelled by dithering the leaf. (2) Dish to the drop position: 3 sheets dropped from the dock one at a time down the slide insert, dish indexed 85 mm between drops. (3) Back to leaf L, béchamel poured in lanes. Four rounds. (4) Cheese from the shred plate over the moving dish | 4 × 6 + 3 |
| 62 | Dish (3.2 kg) into the oven, 40 min; rest 15 min | 2 |
| 120 | To the hand-over | 1 |

**Result: yes, medium–low** (sheet dropping is the weak step; layer evenness ±30 % by pouring from a
rolled pot is plausible, the requirement is ±20 %). Elapsed **about 120 min** (limit 148). **Moves: about
55**, the dish shuttling between leaf L and the drop position is the cost of having one fork and one fixed
depositor. Soiled: about 16 items plus the dish.

### B11 Rührkuchen in a tin, unmoulded — T_ref 100

| t | Step | Moves |
|---|---|---|
| 0 | Butter 250 g: small tube, pushed out into tube G1 standing on a stopper cap at the drop position; tempered there 3 min with the tube on a 35 °C leaf | 4 |
| 5 | Sugar 250 g, vanilla sugar into the tube (tube chute); PRESS: knead plunger 40 strokes (creaming by back-extrusion: mixes, but beats in little air: the cake rises on baking powder; a creamed-by-whisk crumb is lighter) | 2 |
| 9 | 4 eggs (egg module into the tube chute), plunger 15 strokes; 500 g flour (mesh lid) and 15 g baking powder (weigh cup), 125 mL milk; plunger 20 strokes: a stiff, dropping batter of 1.4 L | 3 |
| 16 | Loaf tin (loose floor, oil mist, flour dusted with the sifter cup) at the drop position. The tube is slid from its cap onto the 120 × 5 slot die over the tin (shear gate; the batter is stiff, so it smears but does not run), and the ram pushes 1.4 L out in 20 s while the shuttle moves the tin in X; levelled by shaking | 4 |
| 19 | Oven 175 °C, 60 min; out; cool 10 min in the tin | 2 |
| 90 | Unmould: shuttle grips the tin, rolls it 180° over the board on leaf L and sets it down; lifts the tin wall (the cake rests on the loose floor, now on top); tongs lift the floor. The cake lies upside down, which is the usual presentation of a loaf cake turned out; to turn it upright the book flips it onto a second board (one cycle, at 20 N) | 5 |

**Result: yes, medium.** Adapted in detail: creaming without aeration. Elapsed **about 95 min**. **Moves:
about 24.** Soiled: tube, small tube, plunger, pistons 2, 3 dies, tin + floor, 2 boards, tongs: 12 items.

### B12 Scrambled eggs from shell eggs, toast, 1 person — T_ref 6, limit 17 min

| t | Step | Moves |
|---|---|---|
| 0 | 1.5 L pot with whisk bar to the drop position; 2 eggs by the egg module (inspect cup, tip), 20 mL milk, brine, 8 g butter (small tube, 3 mm) | 2 |
| 1.5 | Pot to rear R (adapter ring), 60 rpm cold for 15 s (whisk), then 95 °C base, whisk bar replaced by the scraper (1 move), 40 rpm, 2.5 min until 72 °C and set in curds. Minimum quantity: 120 mL is a 6 mm layer in a Ø 160 pot; the scraper sweeps the whole floor | 2 |
| 1.5 | 2 toast slices: tilt-slid from the bag (bread bag opened by the opening mechanism; slices stand in a box) onto the griddle leaf L at 200 °C; 60 s; book flip onto leaf R; 45 s | 3 |
| 5 | Pot and toast tray (leaf R vessel lifted out) to the hand-over | 2 |

**Result: yes, high–medium.** Elapsed **about 7 min** (limit 17). **Moves: 9.** Soiled: pot, whisk bar,
scraper, 2 griddle plates, egg module cups and inspection cup: 7 items. The column is not used at all
except for the butter dose: for the minimum-quantity breakfast the concept is a pot, a book and a shuttle.

### Summary

| # | Meal | Result | Elapsed, min | Moves | Weakest step |
|---|---|---|---|---|---|
| B1 | Rouladen, red cabbage, potatoes | adapted (L–M) | 140 | 54 | rolling and securing; cabbage head does not fit |
| B2 | Schnitzel, Bratkartoffeln, Gurkensalat | yes (M) | 55 | 60 | breading by book; two dishes compete for the book |
| B3 | Frikadellen, mash, peas and carrots | yes (H–M) | 32 | 30 | — |
| B4 | Spaghetti Bolognese | yes (M–H) | 68 | 26 | mince crumbling |
| B5 | Pizza | adapted (L–M) | 92 | 30 | plunger kneading; pressed GN 1/2 bases |
| B6 | Vegetable soup | yes (H) | 45 | 23 | leek wash |
| B7 | Steak, oven fries, salad | yes / fries adapted (M) | 38 | 34 | no core probe; large lettuce heads |
| B8 | Pfannkuchen | yes (M–L) | 38 | 40 | batter at the shear gate; flip lid |
| B9 | Chicken curry, rice | yes (M) | 38 | 21 | dicing raw chicken |
| B10 | Lasagne | yes (M–L) | 120 | 55 | sheet placement |
| B11 | Rührkuchen | yes (M) | 95 | 24 | creaming |
| B12 | Scrambled eggs, toast | yes (H–M) | 7 | 9 | — |

Ten "yes", two "adapted", none "no"; but only B3, B6 and B12 stand on mechanisms that I rate high.

---

## 6. Cleaning

### 6.1 Principle

Three cleaning routes, by surface:

1. **Column parts are cleaned where they stand**, within minutes of use: tube by pig and jet, dies and
   carousel under the wash hood, pistons and dashers in the parts basket of the wash box under the deck.
2. **Cooking ware, GN ware and stem tools are loose ware** for the central ware washer (D7); the shuttle sets
   them on the hand-over. K5 does not contain a ware washer of its own.
3. **The cell** (bay A above the deck, bay B above the deck) is a welded wash-down enclosure with fixed
   nozzles, washed once a day and after a spill.

Wash kit (bay C, below the oven): boiler 6 L at 85 °C (6 kW, DEC-1), sump 6 L under bay A with a 2 kW
heater, circulation pump 30 L/min at 1.5 bar, enzyme detergent and rinse-aid dosing, turbidity and
conductivity cell in the sump return, 70 °C dry-air fan 100 m³/h. All drains of bays A and B run through the
perforated chip box before the sump, so the chip box is also the strainer (2 mm).

### 6.2 Surface inventory (HYG-010)

| Surface | Zone, area [E] | Soiled by | Cleaning | Dries | Verified by |
|---|---|---|---|---|---|
| Tube bore and rims (per tube) | F, 0.14 m² | everything | (0) Pig: the press piston ends flush with the bottom rim; film about 50 µm, 5–7 g [E:C]. (1) At SERVICE over an empty carousel window: the crank takes the spray dasher, its first stroke pushes the piston out downwards through the window into the parts chute; then the rotary jet head travels the bore 6 times per program step: 1 L cold to drain (20 s), 2.5 L at 55 °C with enzyme recirculated 2.5 min, 1 L rinse, 1 L at 85 °C from the boiler for 45 s (A0 ≥ 60 on a 3 mm wall: reached after about 15 s [E]). The outside of the tube and the fork are hit by two fixed fan nozzles in the same steps | own heat from the 85 °C rinse (1.6 kg steel: film 8 g evaporates with 18 kJ of the 45 kJ stored) plus 60 s of air through the spray dasher | bore camera (whole bore in one image, white and UV-A light); turbidity of the last litre; pump pressure trace |
| Tube lip ring (UHMW, snapped on) | F, crevice behind the snap | pastes | jets from below through the window; the ring is pushed off weekly by the shuttle against a fixed hook and both parts go to the ware washer | air | camera from below (mirror in the window) — weak |
| Pistons, comb pistons, dashers, plunger | F, 0.02–0.06 m² each | everything | fall or are set into the parts basket (wire comb, fixed poses) in the wash box under the deck; washed there by four fixed nozzles with the liquor of the tube wash, final 85 °C rinse; lifted back by the shuttle through the drop-position opening | 5 min warm air; UHMW stays damp longest | witness coupon in the basket after class R; camera at the store |
| Piston lips (two per piston) | F, groove between the lips 4 mm wide, R 2 | paste, mince | as above; the groove is open and faces a nozzle in the basket pose | — | not individually; **a known soil trap** |
| Dies on the carousel, carousel plate both faces | F, 0.04 m² per die, plate 0.25 m² | everything; mince and batter film from shear-gate moves | the heel is pushed through by the comb piston first. Carousel turns at 2 rpm through the wash hood: three fixed pegs lift each insert 10 mm out of its window as it passes (so the ledge and the insert edge are exposed), 8 fan nozzles above and below, recirculated 55 °C 3 min, fresh 85 °C 1 min, air knife | plate 12 mm thick holds heat; air knife | camera above the carousel at FILL; blade check of grids by back-light through the window (PRP-035) |
| Grid blade roots, ricer and Spätzle holes, mesh | F | fibres, sinew, starch | jets against the cutting direction under the hood; daily trip to the ware washer; grids are monobloc so there is no joint, but fibres wedge at blade crossings | — | back-light image; **second known soil trap** |
| Iris die (flexure spider with six blades) | F, many edges | peel | ware washer only, after each use | — | **weakest part against HYG-013**; candidate for deletion |
| Duckbill valve in the nozzle die | F, silicone, slit | batter | everted by a peg under the hood; ware washer daily | air | none |
| Sickle, wire bow, shred arm | F, 0.02 m² | everything | parked in the sheath: 3 mm gap, pipe flow 1.5 m/s (SM-190), 1.5 L per wash | air | light barrier, camera |
| Tube chute, bypass chute, slide insert, weigh cup, inspection cup | F, 0.2 m² | powders, mince, egg | flushed from a ring nozzle at the top of each chute: cold after mince or egg at once, hot in the daily cell wash; chutes are loose and go to the ware washer weekly | air, downdraft | camera at the chute mouth; **flour film + water = paste: the tube chute is rinsed only after the last dry dosing of the meal** |
| Diverter flap, drop sleeve, waste chute | F / S, 0.1 m² | trimmings, juice | fixed nozzles, with the hood program | air | — |
| Egg cups and scribe | S (shell only) | shell, white | rinse nozzle at the park position | air | — |
| Ram foot, rod ends, collars | S | splashes, flour dust | daily cell wash; rods stroked through their collars during it | warm air | — |
| Bay A walls, ceiling, deck above the carousel | S, 1.5 m² | dust, splashes, steam from pots at the drop position | 6 fixed nozzles, 5 L at 55 °C recirculated 3 min + 2 L rinse, daily | fan, 20 min | riboflavin self-test weekly (SM-207) |
| GN pans, trays, braisers, boards, mats, racks | F, 0.2–0.3 m² each | frying fat, raw meat, egg, crumbs | ware washer (P1); burnt-on fat in pans is the ware washer's problem | there | there |
| GN rim gaskets (silicone, on the receiving vessels) | F | fat | ware washer; wear part | — | — |
| Pots, pan 28, lid, baskets, cans, scrapers, whisk bar | F | everything | ware washer | there | there |
| Book leaf frames and hinge trough | S, 0.3 m², **next to frying fat** | fat spatter, drips at the flip | two fixed fan nozzles along the trough, hot alkaline from the sump, with the daily wash; leaves open to 90° so both faces are reached | warm air | camera; **fat that carbonises on the frames next to a 240 °C pan is not removed by a 55 °C spray: risk** |
| Hob deck (glass-ceramic), ring-gear rims, gutter | S, 0.45 m² | boil-over, fat, peel slurry | deck slopes 3° to a front gutter; nozzle bar on the rear wall; ring-drive umbrellas lifted 5 mm by their drives' reverse jog to flush under them | fan | camera; boil-over that burns on under a pot needs a scraper the concept does not have |
| Bay B walls, hood, tool pegs | S, 2.6 m² | steam, grease aerosol | hood mesh and condenser flushed weekly (HYG-039); walls with the daily wash, 6 L | fan | — |
| Shuttle arm, fork jaws | S, 0.15 m²; jaws touch ware rims, not food | drips | the arm holds itself in the bay A hood spray daily | air | — |
| Shuttle slot and band cover | S | steam | not washed (faces down, above all food heights); band wiped by its own felt-free scraper lips | — | inspection at service: **a surface that is cleaned by nobody** |

Totals per reference meal [E]: Zone F soiled about 2.6 m² (column parts 0.9, ware 1.7); Zone S 5.0 m², of
which about 1 m² is actually hit by soil.

### 6.3 Water, energy, time per reference meal (4 persons, 4 components) [E]

| Item | Water | Energy | Time |
|---|---|---|---|
| 3 tubes in place (wash liquor of 2.5 L reused for all three; per tube 1 L pre-rinse, 1 L rinse, 1 L final) | 11.5 L | 0.45 kWh | 3 × 5 min, during cooking |
| Carousel, 6 dies, diverter, sickle sheath | 5 L | 0.2 kWh | 5 min |
| Parts basket (pistons, dashers) | 2 L extra rinse | 0.1 kWh | with the tubes |
| Chutes, cold flush | 1 L | — | 20 s |
| Share of the daily cell wash (bays A and B: 13 L, 0.5 kWh, 25 min; one warm meal per day) | 13 L | 0.5 kWh | 25 min after the meal |
| **In-place total (preparation cell)** | **about 32 L** | **about 1.25 kWh** | 15 min during the meal + 25 min after |
| Loose ware to the central washer: about 14 items (2 pans, 2 trays, 3 pots, basket, can, scrapers, tools) = one P1 load [R6] | 18 L | 1.3 kWh | 55–75 min |
| **Total caused by preparation and cooking** | **about 50 L** | **about 2.5 kWh** | |

Against RES-005 (≤ 45 L per reference meal including the dish load) this is **over the limit** once the
plates are added. The in-place cleaning does not replace a ware-washer load, it comes on top, because the
cooking ware needs the washer anyway. Savings available: daily cell wash only on days with frying or mince
(−6 L average); tube final rinse reused as the next tube's pre-rinse (−2 L).
PERF-005 (ready for the next meal within 30 min): met for the column (tubes and dies are clean and dry
15 min after their last use); the ware set must be double for that (it is: 2.6).

### 6.4 Raw meat and ready-to-eat

* Separate instances: red tubes, red pistons, red sickle, red tongs, and trays that touched raw meat never
  return to use in the same meal (FSF-040). Dies are shared: a die used for class R goes through the hood
  program with the 85 °C step before any other use, and the scheduler orders cuts RTE first, raw animal
  food last (SM-208), so that in most meals no die is used for RTE after class R.
* The carousel plate itself is shared and gets a mince film at every shear-gate move. After any class R
  shear-gate move the whole carousel runs the hood program before the next RTE tube is seated.
* The drop position is shared: a splash guard ring stands on it; raw meat never crosses open RTE food
  because only one vessel is at the drop position at a time (FSF-041).
* Breading trays, crumbs and egg that touched raw meat are discarded to the chip box and the trays washed.

### 6.5 Waste

Peel, cores, first and last slices, ricer skins, egg shells, heel plugs and wash solids all end in the chip
box (perforated GN 1/3, 4 L) under bay A: by the diverter chute, by the deck gutter, or with the wash water.
Peel slurry from the rasp can (about 200 g per kg of potatoes, wet) runs through the deck ring drain and
the gutter to the same box. The box drains into the sump, is taken away by the transport system after each
meal, emptied into the organic bin and washed as a box. No macerator. Frying fat: the pan is tipped by the
shuttle into a fat can (a 1.5 L pot with lid), which solidifies and goes out with the chip box.

### 6.6 Honest list of crevices, seals and spray shadows

1. Groove between the two lips of every UHMW piston.
2. Snap seat of the tube lip ring.
3. Window ledge under each die insert (exposed only while the lift pegs raise the insert under the hood).
4. Blade crossings of the grid dies; holes of ricer and Spätzle plates; the welded mesh rim of dasher M.
5. Iris die: six blades on flexures.
6. Duckbill slit.
7. Ram and crank rod collars above open tubes (drained lantern, but a dynamic seal above food: HYG-004 is
   met only through the drip edge and the closed shutter logic, HYG-016 only by "cleanable in place").
8. Book hinge trough and its two shaft seals, 40 mm from frying fat.
9. Rim gaskets of the GN vessels (silicone at 200 °C, odour and fat uptake, HYG-025).
10. Umbrella gaps of the ring drives and of the turret, carousel and spindle bosses.
11. The shuttle slot.
12. The underside of the ceiling of bay A around the chute mouths (flour dust + steam).
13. Pull-bar hem of the rolling mat.

---

## 7. Numbers

| Item | Value [E] |
|---|---|
| Wall width | **1 770 mm** including the oven bay (450 column + 720 hob + 600 oven); 1 170 mm without the oven. Depth 600, height 2 000 |
| Motion actuators | **25**: column 7 (ram, turret, carousel, face rotor, diverter, mixer crank, crank height); dock 5 (tilt, clamp and lid finger, vibrator, weigh-cup and egg-cup swing, shutters); egg module 3; shuttle 5 (X, Y, Z, roll, jaw); frying book 2; ring drives 2; oven door 1. Not counted: 3 pumps, 2 fans, about 14 valves, 4 induction modules |
| Loose Zone F parts | about 96 pieces of 44 types (2.6) |
| Custom part types | about 30 loose part types + 9 custom assemblies (frame, turret, carousel with hood, dock, ram foot, book, ring drive, shuttle arm, wash box) |
| Peak electrical power | 11 kW connection, load-managed: 4 zones (11 kW nameplate) + oven 3.5 + boiler 6 + drives < 1.2 kW. The ram needs 480 W at 8 kN and 60 mm/s |
| Handling moves per meal | 9 (B12) to 60 (B2); reference meal (B3-like) about 30–35; mean of the twelve benchmarks 34 |
| Noise sources | produce cracking through a grid and pieces falling into an empty pot (short, about 65–70 dB(A) at 1 m behind the door), spin basket at 600 rpm (imbalance), rasp can (3 min, about 60 dB(A)), mixer crank at 3 Hz (knocking if the dasher hits the cap: soft stops), circulation pump. No blade above 300 rpm anywhere: no blender noise |
| Zone F / S area | 2.6 m² / 5.0 m² (6.2) |

**Parts cost estimate** (one machine, prototype prices, ±40 %; [M] = from `research/04` 16 and `research/08`,
otherwise [E]):

| Group | EUR |
|---|---|
| Servo cylinder 8 kN, 340 mm, with drive | 1 200 |
| Frame, deck, ceiling, tie columns (welded 1.4301) | 900 |
| Turret, carousel, bosses, seals, 2 drives with gearboxes | 900 |
| Face rotor, diverter, mixer crank | 600 |
| Tubes (6), pistons and dashers (12) | 1 100 |
| Dies (17, wire-eroded grids are the expensive ones: 250–400 each) | 2 600 |
| Dock, chutes, weigh cup, load cells, egg module | 1 100 |
| Shuttle (X, Y, Z, roll, jaw; closed-loop steppers [M], rails, arm) | 1 800 |
| Frying book (frames, shafts, 2 worm drives) | 900 |
| Ring drives (2) | 500 |
| Induction modules (4, OEM) and glass-ceramic deck | 900 |
| GN and round ware, tools, fixtures (mostly bought) | 1 300 |
| Wash kit (boiler, sump, pumps, dosing, hood, nozzles, sensors) | 900 |
| Enclosure sheet metal, doors, hood, condenser, fans | 1 800 |
| Cameras (4), sensors, control boards, power supplies, wiring | 1 200 |
| **Preparation and hob, without oven** | **about 17 700** |
| Built-in combi-steam oven with custom lift door | 2 500–4 500 |
| **Total** | **about 20 000–22 000** |

The column itself (first six rows) is about 7 300: a third of the cell. The rest is what any concept needs
around a hob.

---

## 8. Coverage estimate against the 248-meal corpus

Method: I went through the ordered operations of all 248 rows (compact extract of corpus section 3) against
the operation table of section 4, for 4 persons, with purchases as MEAL-012 permits. This is a judgement per
row from its operation codes, not a recipe-level walk-through; V2 must redo it. "Adapted" = the plated result
differs in a way a rater could notice (MEAL-013).

**Size limits that decide many rows.** Anything processed by the column must pass a bore of 140 mm; anything
worked in the book must lie on 325 × 265 mm. PRP-020 asks for Ø 130 × 300 (met: long goods stand in the
300 mm tube; **nothing in the cell can shorten a longer piece: a 320 mm cucumber stands proud of the tube
and is pushed down by the ram, a 350 mm leek is refused**) and for Ø 220 heads as priority S
(**not met**: cabbage, cauliflower, large lettuce, pumpkin and whole celeriac must be bought quartered or cut).

### 8.1 Meals that fall out

| Group | Meals | Count |
|---|---|---|
| Already excluded by requirements 5.4 | CK11, DM21, DS13, BF08, AS05, BK06, CK08, BK02 | 8 |
| Wrap a sheet round a filling, sheet larger than the book or too limp for the mat roll; leaf separation | DM12 Kohlrouladen, CK12 Apfelstrudel, CK13 Biskuitrolle, AS08 spring rolls, IN07 samosa | 5 |
| Flat pockets, filled dough pieces, filled dumplings | DM05 cordon bleu, AS09 gyoza, CK17 Apfeltaschen, DS11 Germknödel | 4 |
| Poached egg with hollandaise build | BF14 | 1 |
| **Not preparable, firm** | | **18 (7.3 %)** |
| Folded or rolled hand food, preparable only as "served as components" (SM-244): counted as **not preparable unless the customer rules otherwise** | MX02 tacos, MX03 burritos, MX05 fajitas, MX07 enchiladas, ME03 gyros in pita, US08 sandwich or wrap, US02 hot dog | 7 |

**Coverage by count: 223 of 248 = 89.9 %** if served-as-components does not count; **230 of 248 = 92.7 %**
if it does. By weight the picture is slightly better (most fall-outs have weight 1–2; BF11 Abendbrot, US07
and US01 with weight 3 are flat builds and stay in, at low–medium confidence): about 91–94 %.
**K5 misses MEAL-002 (95 %) in both readings**, by 6 to 13 meals. The reserve of 4 meals is used up four
times over. Every one of the missing meals is a limp-sheet or open-hand operation.

Further rows that are in the count above but hang on a low-confidence mechanism (each could fall out after a
bench test): DM02 Rouladen (named in the brief, MEAL-005), US01 hamburger, IT12 saltimbocca, IT18 cannelloni,
IT05 lasagne and ME02 moussaka (sheet and slice placement), IT10 pizza and FR05 Flammkuchen (pressed bases;
2 mm Flammkuchen base is not reached), DS15 Bratapfel (coring a whole apple on centre). If all nine failed,
coverage would be 86–89 %.

### 8.2 Adapted methods (MEAL-013 limit: 10 % = 24 meals)

| Adaptation | Meals [my count] |
|---|---|
| Deep-frying replaced (already ruled by X-01) | 9 |
| Pressed instead of rolled dough, GN 1/2 format, flat base without a raised rim | IT10, FR05, FR01, CK02, CK04, CK09, IN06: 7 |
| Cylindrical or tumble-rounded instead of hand-rounded dumplings, balls, rolls, Schupfnudeln | SD07, SD08, DM10, SD22, BK03, DM35, ME05 (in 9 above): 6 |
| Untied Rouladen in a rack; untrussed chicken served whole; unbraided Hefezopf | DM02, DM20, BK04: 3 |
| Halved instead of hollowed vegetables for stuffing | DM13, VG04: 2 |
| Pressed through a coarse grid instead of pulled or torn | US06, DS05: 2 |
| Creaming without aeration (plunger) | CK01, CK03, CK14, CK15, CK16: 5 (none if the whisk fallback is fitted) |
| Skewerless, unskimmed (already ruled) | ME04, SP05, DM29: 3 |
| Herbs and onion as 1.5 mm ribbons and 3–6 mm dice instead of a fine mince where the recipe says MIN | not counted as adapted (35 rows); a rater may disagree |
| **Total** | **about 37 = 15 %**; 32 with the whisk fallback |

**K5 exceeds the 10 % budget of MEAL-013.** The pressed-dough and cylinder-dumpling rows are the ones that a
sheeter and a rounder would remove.

### 8.3 Other coverage requirements

* MEAL-003 (all staples): DM02 (W 3) is in only as adapted and at low–medium confidence.
* MEAL-004 (≥ 85 % in categories with ≥ 10 meals): **cakes 12 of 17 = 71 %, Asian 9 of 12 = 75 %: missed.**
  All other categories ≥ 86 %.
* MEAL-005 (brief meals): salad yes (small heads or bought leaves), mash yes, roasts yes (carving M), Frikadellen
  yes, Rouladen adapted and uncertain, soups yes (puréed soups by the reciprocating sieve: mesh dasher with
  1 mm mesh worked through the cooked soup in a capped tube, 2 L per load, 60 s, confidence M–L), steak yes,
  pasta yes.
* MEAL-009 (≥ 90 % from whole produce, S): **far from met**, about 40–45 % [E]: onions (52 % of meals),
  whole heads, small-item trimming, stripping, peppers from whole, carrots by iris (L–M) all rely on purchase.
* MEAL-016 (1–6 persons): 1 person works through the small tube and the 1.5 L pot. 6 persons: frying
  is batch work on two leaves (12 Frikadellen = 2 leaf loads, fine; 6 Schnitzel = 3–6 batches with the potatoes
  waiting for the book: about +15 min over the 4-person time, outside PERF for B2); dough 1.6 kg fits one tube;
  1.5 kg potatoes = 2 rasp-can loads; salad 1.2 kg = 3 basket loads.

---

## 9. Failure modes and recovery

| Failure | Detection | Recovery | Human needed? |
|---|---|---|---|
| Ram overload on a grid (too full, dull blades, a stone) | force > 7 kN before the expected travel | back off, turret shakes the tube at FILL, retry once; then shear-gate the tube to the open ring, push the load out into a spare pot and re-dose it in smaller layers. Blade life counter (PRP-034) | no |
| Piece bridged in the tube above the die (long carrot lying across) | piston height at contact does not match the dosed volume | ram taps at 300 N three times; else as above | no |
| Piston tilts and jams in the bore (paste under one lip) | force rise with no travel | retract; the magnet foot holds the piston centred on the next try; a jammed piston is pulled out upward by the foot (60 N) or pushed out by the spray dasher | rarely |
| Piston not picked up or dropped by the magnet foot | foot load pin reads no piston weight | re-approach; spare piston from the store | no |
| Food stuck in a die (heel, fibres, sinew) | back-light image of the die after use | comb piston stroke; hood wash; die quarantined and exchanged from the store | no |
| Blade fragment missing (grid or sickle) | back-light image compared with the reference; light barrier on the arm | the vessel's contents are discarded to the chip box by the shuttle, die quarantined, user informed (PRP-035) | replaces the die later |
| Mass rides up with the knead plunger | ram force falls to < 200 N over the stroke | stripper ring fitted by the shuttle; if still riding: fallback kneader in the can | no |
| Shear-gate move smears or leaks more than expected | camera on the carousel at FILL | hood wash before the next seat; recipe marked for the fallback path | no |
| Cutlet, patty or pancake sticks to the first pan at a book flip | leaf load cells (strain gauges on the leaf shafts) show the mass did not change sides; camera | re-close, tap (leaf dither 5°), reopen; then the turner tool loosens it | no |
| Hot fat runs out at a book flip | drip sensor in the hinge trough; temperature spike on the deck | flip cycles with fat > 30 mL are blocked unless the pre-tilt has run; trough is flushed | no |
| Roulade opens or misses the rack slot | camera over leaf L | tongs re-roll attempt once; else pin; else the slice is cooked flat in the braise ("deconstructed") and the meal is flagged | no, but the dish is changed |
| Food dropped on the deck or beside the vessel | camera, load cells (mass missing) | class R or unknown: flushed to the chip box; recipe re-doses if stock allows | no |
| Shuttle drops or mis-seats a vessel | jaw current, lug switches, load in Z | re-grip from the known seat; a vessel lying on its side is not recoverable | **yes** for a toppled pot |
| Boil-over at a rear position | deck temperature, ring-drive torque | power cut, deck flush after cooling | no |
| Spin-basket imbalance | ring-drive current ripple | stop, 40 rpm redistribution, retry at 450 rpm | no |
| Tube or die fails verification after washing | bore camera, turbidity | repeat once with the intensified program (HYG-026); then the shuttle takes the part to the central washer; then quarantine | after the second failure |
| Power loss with the ram under load | — | screw drive is self-holding; on return the ram retracts under force control; food handled by FSF-030 | no |
| Dock: powder cakes in the mesh lid, pieces jam in the chute | dock weight not falling | vibrate, tilt back and forth; jam in the chute: piston P140 is dropped through the chute as a pig | sometimes |

---

## 10. Top risks and the cheapest experiment for each

| # | Risk | Why it matters | Cheapest confirming or killing experiment |
|---|---|---|---|
| 1 | **Plunger kneading does not develop gluten**, or the dough rides with the plunger | Without it the tube is not the dough vessel; pizza, bread, rolls go to the fallback can and lose enclosure and metering | A 140 mm tube (acrylic or steel) with a bottom plate, a turned Ø 110 plunger, on a 1 t arbor press or a drill-press quill; 500 g flour at 65 % hydration, 200 strokes; windowpane test and a baked loaf against a hand-kneaded one. Half a day, < 150 EUR |
| 2 | **Book flip with hot fat**: fat leaves at the rim, crust stays in the first pan, breading is torn | The book is the whole flat bench; FLP is 12.9 % of meals, BRD, POU and the steak depend on it | Two bought GN 1/2 pans joined by a door hinge on a plank, hand-operated over two portable induction plates: 10 Frikadellen, 6 cutlets breaded by the flip sequence of 4.2, 4 steaks, fried potatoes; count intact pieces, weigh fat lost, weigh crumb coverage. One day, < 200 EUR |
| 3 | **Rouladen by mat and rack** (rolling, landing, staying closed for 90 min) | Named in the brief; no tested mechanism in any lens | By hand with a baking mat in a GN tray, pulling only the bar; braise 12 untied rolls in a comb rack (bent wire) for 90 min; count closed rolls. One afternoon |
| 4 | **Dicing force and quality on a bore-140 staggered grid**; sickle torque under a full grid | Sets the ram, the frame and the throughput; decides whether 8 kN and the 50 % fill rule hold | A wire-eroded two-tier 10 mm grid (one part, about 400 EUR) in a tube on a workshop press with a load cell: potatoes, carrots, onions at three fill levels; face cut with a hand-swung blade on a pivot with a torque wrench |
| 5 | **Coverage: limp sheets and open-hand assembly** cannot be added within the concept | 89.9–92.7 % against 95 %; MEAL-004 missed for cakes and Asian | No experiment; a decision: accept, or add a sheeter-and-roll station (which is K3 or K4 next to K5) |
| 6 | **Dasher whipping of egg white and cream** | PRP-038 (1–6 egg whites); 10 + 32 meals | A French press and a stand mixer side by side: 1, 3, 6 egg whites with a 1.5 mm mesh at 3 Hz by hand; overrun and stability. One hour |
| 7 | **Carousel hygiene**: window ledges, shear-gate film, shared plate between class R and RTE | The strongest cleaning claim of the source concepts (pig, pipe, one camera) holds for the tube only; the carousel is a fixed Zone F station (X9) | Riboflavin test on a mock carousel with lift pegs under a hood of 8 nozzles; mince smear dried 30 min |
| 8 | **Tilt-dosing of pieces, slices, tubs and pastes from boxes into a Ø 150 chute** | Front end of everything; shared with all candidates but K5 has no hand to correct it except tongs | A GN 1/6 box on a hand tilter with a vibrator over a Ø 150 tube: potatoes, onions, mince, cutlets, quark; count mis-doses |
| 9 | **Rasp can with a fixed deflector** peels unevenly or loses > 25 % | The only raw peeler | Knurled sheet ring in a pot on a drill; 1 kg potatoes; weigh loss, photograph coverage |
| 10 | **Microtome carving of a hot roast** tears the slices | CAR 4.8 %, brief meal roast beef | A cooked rolled roast in the test tube of experiment 4, slices by a sharp hand-swung sickle; against knife carving |
| 11 | Width 1 770 mm and about 20 k EUR are not competitive | Footprint and cost constraints of the brief | Compare in P4 with the same hob and oven assumptions |
| 12 | Handling reliability: 30–60 moves per meal at 98 % per meal needs 99.95 % per move | REL-001 | Self-locating lugs and seats; shuttle endurance rig later |

---

## 11. Improvements found, changes from the catalogue definition, and what I would borrow

### 11.1 What I changed, and why

| # | Catalogue definition (3.6) | This document | Reason |
|---|---|---|---|
| 1 | "Two tubes nose to nose knead and mix" (SM-173), needing a second ram | **One tube on a liquid-tight cap, one ram, a family of loose dashers**: undersized plunger (back-extrusion kneading), perforated dasher (batters), mesh dasher (whipping, puréeing as a reciprocating sieve) | Removes one 3–8 kN axis and the tube-pair handling; makes the tube liquid-tight (the piston is always above the food, so no liquid stands on a lip); gives the column the mixing, whipping and puréeing it lacked. Precedents: plunger churn, French-press frother, passe-vite. Still untested for dough (risk 1) |
| 2 | Tube "filled at the dock, weighed, capped"; piston as the floor | **Piston on top, die or cap below**, piston carried by a magnet foot on the ram | Food only falls without ever turning a tube over; the ram never touches food; no tube inverter |
| 3 | Tubes as loose ware on a gantry, *or* fixed sleeves on a turret (question 1) | **Both**: loose tubes standing in a 3-seat turret, washed in place at the SERVICE seat, lifted out only for the store and the weekly deep wash | No tube carrying during a meal (the turret does it: 1 actuator), but no fixed food-contact sleeve either |
| 4 | Dies in a turret washed on its idle half behind lip seals (SM-196) | Loose inserts in a carousel, lifted by pegs under an **open** wash hood | No lip seal on a soiled plate; the window ledge is exposed for washing |
| 5 | Flat bench "taken from W19 in its smallest form" (trays, tongs, turner, apron roller, gantry) | **Frying book**: the flat bench is merged with two hob positions (SM-103 made into the hob) | One mechanism flips in the pan, breads, flattens and presses dough; removes the turner-under-the-food skill and the pan-pair handling by a manipulator; the bench costs 2 actuators and no width |
| 6 | Stirring and whole-pan flip left to "the hob" | **Rotating round positions** (SM-225, -180, -097, -159) used for stirring, batter spreading, salad spinning and the rasp-can peeler | One drive type covers four jobs and needs no tool drive in the food |
| 7 | One raw peeler: iris, broach or borrowed lathe or rumbler (question 5) | Rasp can on a rotating position for potatoes; iris die kept for long goods at low confidence; broach-peeling (SM-057) rejected (yield 55–70 % misses PRP-022) | The rasp can costs no actuator and no width |
| 8 | SM-025 variable-volume chopper (blade cap on the tube) | **Dropped** | It needs a high-speed drive and a blade in a cap; chiffonade and fine grid replace it, at the price of a coarser mince |
| 9 | SM-237 mains-water press, SM-205 flash pyrolysis, SM-146 piston box at the press | Not used | Electric ram is cheaper to control than backflow-protected hydraulics; pyrolysis needs ferritic dies and a vent; the small tube replaces the piston box without asking anything of the box standard |
| 10 | Dies as "slicer, dicer, ricer, former, filling gun, paste syringe" | Added: the tube as **depositor for assembly** (dish moved under the slot die and the sickle), as **carving microtome**, as **unmoulding piston mould**, as **paste storage cartridge** in cold storage, and the nozzle die with a **duckbill** for thin batters | Extends the principle into ASM, CAR, UNM and DVI without new hardware |

### 11.2 The most valuable improvement

Number 1 with number 2: the capped tube with dashers on a single ram. It converts the source concepts'
"half a kitchen" (no liquids, no whipping, a doubtful two-ram kneader) into a closed mixing-and-forming
vessel whose contents go from flour to formed pieces without a transfer, with one force axis. Its weak point
is that the kneading is as unproven as before; its strong point is that the fallback (whisk spindle, kneading
can) costs little. Second in value is the frying book.

### 11.3 What I would borrow from other candidates

| From | What | Would remove |
|---|---|---|
| K3 / K4 (belt or mat with roller and nose) | a 300 mm sheeting roller with a nose transfer and a loop roller | pressed-dough adaptations (7 meals), Rouladen and wrap risk, tray-size sheets, most of the 5 wrap fall-outs |
| K1 (hands with passive utensils) | a second, lighter arm with a wrist | open-hand assembly (7 meals), sheet and slice placement, cannelloni, basting, carving with a knife |
| K7 (cold plate) | one −25 °C clamp | sticking slices (G9), raw-meat dicing without the freezer airlock, rigid cutlets for breading |
| K2 (rim standard, interposers) | strainer and rack interposers between two GN vessels in the book | draining and rack transfer of Rouladen in one flip |
| K6 (3-minute washer) | the washer | the 55–75 min ware-wash bottleneck for the double GN set |
| Common | an immersion-type blade on a stem | true purée and fine mince (35 + 15 rows at better quality) |

---

## 12. Open issues and requests to the architect

### 12.1 Open issues

1. The column covers 89.9–92.7 % of the corpus, not 95 %; the gap is limp sheets and hand food (8.1).
2. Adapted methods are about 15 % against a 10 % limit (8.2).
3. Every mixing process in the tube (plunger, dashers) is untested; so are the book flip with fat, the mat
   roll, the rasp can with a deflector, the flip lid and the duckbill die. Only slicing, dicing, ricing,
   forming and paste dosing rest on existing practice.
4. Whole heads above Ø 135 and goods longer than 330 mm are refused; MEAL-009 is far from met.
5. Fine mince (< 3 mm in all dimensions), zest, citrus juice from whole fruit, basting with confidence,
   stripping and small-item trimming have no mechanism here.
6. Two dishes that both need the book (B2) queue; a 6-person pan-fried menu misses the time target.
7. The shear-gate move of a loaded tube smears the carousel plate; its hygiene between class R and RTE
   rests on a hood wash that has no riboflavin result.
8. Thin liquids at a die change are handled only by the duckbill nozzle; any other thin mixture must be
   tipped out of the tube by the shuttle on its stopper cap (D1 b), whose holding force of about 50 N under
   a tipped litre is unverified.
9. Water per reference meal about 50 L with the ware washer, above RES-005.
10. The shuttle slot is the one non-round wall penetration and is not washed.
11. Book rim gaskets at 200–240 °C: silicone is at its limit; a metal-to-metal rim with a drip lip may be
    needed, with more fat loss.
12. No core-temperature probe was designed; it is listed as a stem tool but its cable or wireless path
    through the fork is open (COK-013).
13. Actuator count 25 and width 1 770 mm: the concept's promised simplicity survives in the column
    (7 actuators, 0.9 m² of Zone F) but not in the cell.

### 12.2 Requests to the architect

| # | Request | Why |
|---|---|---|
| 1 | Hand-over port for boxes at z 1 500–1 750 in the left wall or ceiling of bay A; the dock takes GN 1/9, 1/6 and 1/3 boxes and needs a defined pour edge on each (X4) | gravity column |
| 2 | Mesh lid for the flour, starch, sugar, crumb and spice boxes (X1); fallback is plain tilt-pouring at ±5 g | powder dosing |
| 3 | A carrier box (GN 1/6-150 or taller: the tube is 300 long, so **lying**, in a GN 1/3-100) for a capped small tube as the storage form of pastes and butter; filling it at first opening (X6) | paste dosing without a piston box |
| 4 | Produce that must pass the bore is stored and bought accordingly: heads quartered, celeriac halved; slices of raw meat interleaved or singly (G9) | bore 140, no slice singulation |
| 5 | Freezer airlock time of 20–30 min for meat that is to be diced (X7) | tempered dicing |
| 6 | Cooking module interface: two rectangular GN 1/2 induction positions with leaf clearance, two round positions with ring drives; vessel standard = GN 1/2 family plus round pots with a notched skirt and two rim lugs (SM-218) | book and ring drives |
| 7 | An oven that the shuttle can load: mouth toward the hob bay, machine-operated door, GN 2/3 or 2 × GN 1/2; or an oven loader owned by the cooking module, which would reduce this cell to 1 170 mm | width |
| 8 | Central ware washer (D7) takes GN 1/2 ware, pots to Ø 260 × 200, tubes 300 long and die inserts, with an 85 °C final rinse, and returns a load within 30 min for the class R set | PRP-031, PERF-005 |
| 9 | Chip box (perforated GN 1/3) collected after each meal by the transport system; fat can with it | waste |
| 10 | Customer ruling: is hand food "served as components" preparable (7 meals)? Are pressed rectangular dough bases and cylindrical dumplings acceptable adapted results? | coverage 89.9 % or 92.7 %; MEAL-013 |
| 11 | The shuttle moves vessels inside the cell 30–60 times per meal; TRN-002 (all flow through the transport system) must allow a module-internal handler (X8) | — |
