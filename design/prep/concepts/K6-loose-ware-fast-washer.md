# K6 — Loose ware and fast washer (round P3 exploration)

Candidate K6 of `design/prep/02-concept-catalogue.md` section 3.7, worked out per
`design/prep/03-exploration-brief.md`. Sources: W19 (E:B "Alles ist Geschirr") as the backbone, GN logistics
of W10 (C:B), W16 (D:D) as the alternative manipulator, W21 (E:D) in reserve. No other file in
`design/prep/concepts/` was read.

**Status of all statements.** Nothing here was built or tested. Every number is my estimate unless it carries a
source tag: [R4], [R5], [R6], [R8] = research documents, [C] = meal corpus, [E:B] etc. = idea documents.
Confidence words: high = known practice at comparable scale; medium = sound, needs a bench test; low =
speculative.

**One-paragraph verdict.** The concept works on paper for all twelve benchmarks (nine "yes", three "adapted"),
with proven cleaning and no fixed food-contact surface. It pays for that with wall width (2.6 m including hob
and oven), about 93 loose items, 45–100 gripper cycles before a meal is served, and a washer that sits at the
limits for water, energy and noise. It is the candidate with the fewest physical unknowns and the most
logistics.

---

## 1. Definition

### 1.1 What the cell is

A stainless bay in which **nothing that touches food is attached to the machine**. Food is worked in bought
Gastronorm trays and in round pots; every tool is a welded steel part on a stem with a drip collar; the few
mechanisms are passive cassettes that fall apart into plain shapes. One Cartesian manipulator (a hanging mast
with a height-adjustable cantilever arm, wrist tilt and spin, and a servo two-jaw chuck) does all handling.
Two small top-loading wash wells of commercial type (60 °C tank wash, 85 °C fresh rinse, 3.5 min) stand in the
deck, so ware is washed during the meal and dries by its own heat. The bay itself is Zone S only.

Five statements define the concept as explored:

1. **One grip feature on everything.** Every tray, pot, lid, tool and cassette part carries the same flat
   tang (6 × 32 × 60 mm, two Ø 8 holes). The chuck needs no tool changer and no tray fork.
2. **One ware grid.** Trays are GN 2/3 and GN 1/3 (the 176 mm family of the storage boxes), pots are
   Ø 240 mm. Two trays or two pots rim to rim are clamped by gripping both tangs at once: that is the
   inverter for flipping, unmoulding and closed transfer.
3. **Heavy forces do not go through the manipulator.** A pull-down swing press (3 kN) at one bench takes
   dicing, slicing, ricing and filling; two turning hob positions (20 Nm) take kneading and continuous
   stirring. The manipulator carries at most 5 kg and pushes at most 100 N.
4. **Wash as you go.** A soiled item is hung straight into the open well, which is its wet parking place.
   Wells alternate, so one is always open.
5. **Sequence instead of duplication where possible**: dry before wet, ready-to-eat before raw, raw animal
   food last; duplicate (red/green) instances only for the items that must overlap.

### 1.2 Layout

Inner dimensions in mm. X along the wall, Y from the front door (0) to the rear wall (555), Z from the floor.

```
FRONT VIEW (door removed)                                         outer width 2595, depth 600, height 2000
Z
2000 +-----------------------------------------------------------------------------------------------+
     | dry box: X rails, purge air, electronics      camera windows (3)      fume hood + grease trap |
1950 +====slot=(X 0..2000)====================================================+----------------------+
     |  tool wall      |<------- hanging mast travels X 150..1900 ---------->|                      |
1730 |  36 pigeon-     |        ||  mast 60 x 120, Z 1000..1950              |  TRAY STORE          |
     |  holes,         |        ||                                           |  6 rail levels       |
     |  tools lie      |   arm ====[Y carriage]    arm Z 1050..1880          |  Z 1345..1730        |
1345 |  horizontal     |            |  drop link 150                         +----------------------+
     |  Z 1150..1700   |          [wrist: tilt, spin]                        |  OVEN combi-steam    |
1150 |.................|           [chuck]        water spouts, anchor pins  |  GN 2/3 rails        |
     |  DOCK  box      |            |tang         on the rear wall           |  Z 870..1325         |
     |  tilter + lid   |          (tool)                                     |  door opens towards  |
 850 +--[S0 scale]-----+--[B1 sink]--+--[B2 press]--+--[ HOB 2 x 2 ]--+-WELLS-+  the bay (-X)        |
     | bio bin 12 L    | sink basin, | press drive  | induction x 4   | W1 W2 | tank 10 L, boiler    |
     | drum strainer   | strainer    | 3 kN, swing  | 2 ring drives   | 440   | 8 L, pumps, dosing,  |
     |                 | drain       | column       | load cells      | deep  | softener             |
 100 +-----------------+-------------+--------------+-----------------+-------+----------------------+
     X=0              300           645            990              1590    1985                  2545

TOP VIEW at deck level (Z 850)                                   rear wall Y 555
     +----------------+-------------+--------------+--------+--------+-------+----------------------+
 555 | fine scale     |  spout  o   | press column | T3     | T4     | W2    |                      |
     | (300 g)        |  rear strip | (o) Ø40      | turning| turning| rear  |   oven, 550 deep     |
 435 |................|.............|..two bars....| Ø240   | Ø240   | well  |   (its 595 width     |
     | S0: GN 1/3     | B1: GN 2/3  | B2: GN 2/3   +--------+--------+-------+    lies along Y)     |
     | frame on       | frame over  | solid plate  | H1     | H2     | W1    |                      |
     | 10 kg cell     | sink        | under bars   | plain  | plain  | front |                      |
 110 |                | 325 x 354   | 325 x 354    | Ø240   | Ø240   | well  |                      |
   0 +---- door ------+-------------+--------------+--------+--------+-------+----------------------+
     0               300           645            990    1290     1590    1985                   2545

Trays lie with their long side (354) along Y and their tang pointing along X. A thermoplate lies over the
front and the rear coil of one hob column (bridge mode); two thermoplates fill the hob.
```

Wall width by function: preparation proper (dock 300, two benches 690, wells 395) 1385 mm; four heated
positions 600 mm; oven and store tower 560 mm; casing 50 mm. **Total 2595 mm, say 2.6 m.**
the brief for this round puts them inside, so 2.6 m is the honest figure. Reasons it cannot be shorter are in
section 7.2. Without hob and oven the bay would be 1.4 m.

### 1.3 What I changed from the catalogue definition

| # | Catalogue / E:B | As explored | Why |
|---|---|---|---|
| 1 | GN 1/2 trays | GN 2/3 and GN 1/3 | GN 1/2 is outside the 176 mm box family [R3]; GN 2/3 equals a 36 cm pan, takes 8 Rouladen, fits compact combi ovens, and two GN 1/3 fill one frame |
| 2 | Knob above a drip collar on tools; tray gripping not stated | One flat tang on every item; servo two-jaw chuck with pins | Trays and pots need a grip too; a tool fork for trays would double the moves |
| 3 | Separate inverter not stated; wrist inverts pan and flip lid | Two tangs gripped together clamp a rim-to-rim pair | One grip inverts a pair; no clamp actuator, no equal-rim adapter |
| 4 | Gantry X–Z behind the wall, Y arm, tilt-and-spin wrist | Hanging mast in the bay, arm moves in Z, chuck works vertical or horizontal | A tube hanging from an overhead bridge cannot reach both the deck and a shelf above the oven (section 7.2); the arm that moves in Z can |
| 5 | Pass-through washer 500 × 500 rack, two doors, rack shuttle | Twin top-loading wells, ware hangs by its tang, no rack, no shuttle | 380 mm of wall instead of 600; the gantry never reaches into a wet chamber; one well is always open |
| 6 | Flat power wall: low-speed dog, high-speed magnet drive, 2 kN ram from above | No power wall. Turning hob positions are the low-speed drive; the wrist spin (to 6000 rpm) is the high-speed drive; the press pulls down from under the deck | No drive above food, no magnet window, two actuators fewer |
| 7 | Push dicer, ricer, separate slicing | One press tube Ø 110 with exchangeable end plates and a cut-off slide | One cassette for slices, sticks, dice, mash, juice, wedges, Spätzle |
| 8 | Spike-lathe cassette with tailstock | The potato is stabbed on a fork in the chuck and turned past a fixed sprung blade | No lathe, no tailstock, no horizontal drive (SM-002 instead of SM-001) |
| 9 | Three benches with load cells and vibrators | Two benches plus a small weigh station; no vibrators | Width; the gantry jiggles a tray where shaking is needed |
| 10 | About 45 items in two sets | 93 items, duplicates only where red and green overlap | Counted for six persons and four heated positions; E's count was too low |
| 11 | Magnet-driven chopper cup, egg cracker on the ram | Blade stem in a lidded saucepan; hook-hinged cracker closed by the chuck | No bearing inside ware |

---

## 2. Mechanism

### 2.1 Manipulator: hanging mast with a cantilever arm

| Axis | Travel | Drive | Force / torque, speed | Where the drive sits |
|---|---|---|---|---|
| X | 1780 (wrist X 120…1900) | toothed belt, closed-loop servo 400 W, two profile rails 140 apart | 300 N, 1.0 m/s, 3 m/s² | dry box above the bay ceiling, Z 1950–2000 and behind the top 170 mm of the rear wall |
| Z (arm on mast) | 830 (arm 1050…1880) | ball screw 16 × 10 with motor brake, servo 400 W | 600 N, 0.4 m/s | inside the mast, a closed stainless box 60 × 120 with a steel sealing band over the carriage slot |
| Y (carriage on arm) | 380 (wrist Y 60…440) | toothed belt, servo 200 W | 200 N, 0.8 m/s | inside the arm, closed box 80 × 80, slot on its side face with sealing band and a drip lip below |
| Tilt (pitch about an axis parallel to Y) | ±180° | servo 200 W with 50:1 gear | 25 Nm, 90°/s | wrist housing, sealed, static seals plus one shaft lip seal |
| Spin (about the chuck axis) | continuous | direct-drive servo 400 W with holding brake | 1.3 Nm continuous, 3.8 Nm peak, 0–6000 rpm | wrist housing, one shaft lip seal |
| Chuck | 2 × 22 mm | servo, screw, two parallel jaws | 20–400 N, force-controlled | chuck body Ø 70, jaw guides behind lip seals |

Six actuators. The wrist hangs 150 mm below the arm on a fixed drop link, so the arm passes over a 4 L pot on
the rear hob row. With the chuck vertical its tip works from Z 870 to 1700; tilted 90° it points along +X
(oven, tray store, wells side) or −X (tool wall) at any height from 900 to 1730.

Payload 5 kg gripped at the tang with the centre of mass 200 mm out (10 Nm static on the tilt axis). Push
force at the tool 100 N, enough for a draw cut (10–70 N [R4]), rolling (20–60 N [R4]) and pressing crumbs.
Repeatability ±0.3 mm from closed-loop axes [R8]; the jaw pins and the cones on every rest take up ±3 mm.

**What the wrist can and cannot do (gantry dexterity).**

| Needs | Provided by | Examples |
|---|---|---|
| No wrist axis (X, Y, Z only) | — | draw cuts along X or Y, pressing, stamping, placing trays, hanging ware in the wells |
| Spin only (yaw of a vertical tool) | spin | knife at any angle in plan, whisk, blade, peeling on the fork, orienting tongs to a piece |
| Tilt only | tilt | pouring from a pot or tray over its far rim, ladle, tossing, reaching into the oven and the store |
| Tilt and spin together | both | turner flip (blade pointing along Y, tilt = roll of the blade); inverting a rim-to-rim pair (tilt 90°, then spin 180° about the tang axis); rolling the apron |
| A third wrist axis — **not available** | — | pouring sideways while the tang points elsewhere; a spatula following a curved wall at a chosen angle; approaching a piece in the pan from any azimuth (approach is along X or Y only); basting by tilting the pan towards a spoon; plating with a wrist flourish |

Consequences of the missing axis: every vessel is poured over the rim opposite its tang; curved walls are
scraped by turning the vessel (turning hob) and not the tool; pieces in a pan are laid out in rows along Y by
the machine itself so that the turner can take them from the front. I found no benchmark step that fails for
lack of the third axis; bone-in carving and free-form assembly (tacos) would want it.

### 2.2 Chuck and tang

The tang is a flat bar 6 × 32 mm, 60 mm long, with two Ø 8 holes 30 mm apart and chamfered edges. One jaw
carries two conical pins, the other two sockets; closing drives the pins through the holes, so the grip is
form-fit in all directions and the clamp force only keeps it shut.

* **Stem tools**: tang – conical drip collar Ø 60 – stem Ø 12, 120 mm – tool. The jaws touch only the tang
  above the collar (SM-202).
* **Trays**: tang welded to the middle of one long side, in the plane of the flange, pointing outward.
  The tray is carried level with the chuck horizontal; it hangs on edge from the vertical chuck.
  A 5 mm dam is bent up between flange and tang. There is no collar, because trays nest in the store.
  **This is a real weakening of the drip-collar rule** (section 6.6).
* **Pots**: tang radial at the rim, on a 40 mm stand-off with a collar.
* **Tongs**: a one-piece sprung steel U; each arm has a tang plate with holes. The jaw pins enter from
  outside and stay engaged over the whole stroke, so the chuck servo sets opening and grip force
  (2–40 N at the tips). No spring joint, no second jaw drive.
* **Pairs**: two trays or a pan and its flip disc, laid rim to rim, present their two tangs back to back
  (12 mm pack). The chuck takes both on the same pins. The pair is held from one side only; the far side
  gapes by the flange flex (estimated ≤ 1 mm at 1.5 kg of food, to be measured).

### 2.3 Fixed stations

| Station | What it is | Actuators | Penetration and seal |
|---|---|---|---|
| Dock | Cradle for a GN 1/6 or GN 1/3 box delivered through a port in the left wall; tilts the box about its pour edge 0–135°; tapper; lid lifter. Cradle on a 6 kg load cell (loss in weight). | tilt, tapper, lid lifter (3) | shaft through the left wall above deck level, lip seal; port shutter belongs to transport |
| S0 | GN 1/3 frame on a 10 kg / ±1 g cell; beside it a cup rest on a 300 g / ±0.05 g cell under a draught hood | — | load-cell posts through raised bosses with umbrella caps (SM-236) |
| B1 sink bench | GN 2/3 frame over a basin 360 × 330 × 120 with outlet Ø 90; swivel-free fixed spout (cold and 45 °C mixed water) | drum strainer (1) | basin welded into the deck |
| B2 press bench | Solid plate for a GN 2/3 or GN 1/3 tray or a pot; two bars Ø 30, 300 apart, 230 above the plate, carried by the rear wall and a front post; swing column Ø 40 behind the bench with a 200 mm arm | press, 3 kN, stroke 200, first 25 mm swings the arm 90° by a helical cam (1) | column through a raised boss; scraper ring, drained lantern, dry seal (SM-191). Bars and arm are plain bars, Zone S |
| Hob | 2 × 2 induction positions (column pitch 300) under one glass-ceramic field 600 × 515: H1 3.5 kW and H2 2.2 kW (front, plain), T3 2.2 kW and T4 3.5 kW (rear, turning) [OEM modules, DEC-5] | ring drives T3, T4 (2), worm gear motor 0–120 rpm, 20 Nm at the pot | three roller posts per turning position through bosses with umbrella caps; each post set on a sub-frame with three load cells (10 kg, ±2 g) |
| Wells W1, W2 | Two wash wells 365 × 262 × 440 deep, front and back, sliding lids | lids (2) | lid runs in a channel outside the well coaming |
| Oven | Bought compact combi-steam oven with GN 2/3 rails (V-ZUG CombiSteam or a commercial XS class), front facing −X | door drive (1) | appliance seal |
| Tray store | Six rail levels above the oven, open towards −X, behind a roller shutter that the arm pushes up | — | — |
| Tool wall | 36 pigeonholes (two rods each) on the left end wall | — | — |

**Turning position.** A loose carrier ring (1.4301, Ø 250 / 205, 3 mm, pin teeth on the rim) lies on three
PEEK rollers; one is driven. The pot's base skirt drops into the ring and stands 2 mm above the glass. The
ring is ware. A loose scraper or roller arm hooks onto two anchor pins on the rear wall and stands in the
turning pot (Ankarsrum principle, SM-171/-180): no seal, no shaft, the manipulator is free. Confidence medium:
coil coupling through a 2 mm gap and ring heating need a test.

**Motion actuator count: 6 (manipulator) + 3 (dock) + 1 (strainer) + 1 (press) + 2 (rings) + 2 (lids) + 1
(oven door) = 16.** Not counted: 3 pumps (wash 60 L/min, rinse booster, drain), about 12 solenoid valves,
2 fans, heaters, induction.

### 2.4 Wall penetrations and dynamic seals (complete list)

| # | Penetration | Zone on the wet side | Seal |
|---|---|---|---|
| 1 | X slot, 1800 long, in the vertical face of the ceiling bulkhead (rear, Z 1900) | S, above the rear strip, not above a bench | steel band, labyrinth, gutter below, dry-air purge outward |
| 2 | Z slot in the mast | S, above rear hob row at times | steel sealing band (bought linear-module type) |
| 3 | Y slot in the side of the arm | S, above food | sealing band, drip lip, arm sloped 3° to the mast |
| 4–5 | Tilt and spin shafts | S, above food | one lip seal each, food-grade grease behind it |
| 6 | Chuck jaws | S | two rod lips |
| 7 | Press column | S, behind B2 | scraper, lantern, dry seal |
| 8–13 | Six roller posts, 3 load-cell bosses | S | contact-free umbrella caps |
| 14 | Dock shaft | S | lip seal in a vertical wall |
| 15–16 | Well lids | S/F side faces the well | none; coaming 30 mm and channel |

No penetration and no dynamic seal is in Zone F. Items 2–6 hang above open food and are the hygiene cost of
any manipulator (HYG-004: closed, drip-proof, Zone S).

### 2.5 Ware, tools and cassettes

B = bought as is, B+ = bought plus a welded tang, C = custom (laser-cut, bent, turned, welded, no FDM).

**Vessels and lids (37)**

| Item | Size | No. | Make | Use |
|---|---|---|---|---|
| GN 2/3-20 | 354 × 325 × 20 | 2 | B+ | baking sheet, bench, lid for a pair |
| GN 2/3-40 | 3 L | 3 | B+ | bench, roasting, breading set-up |
| GN 2/3-65 | 5.5 L | 2 | B+ | mixing, marinating, holding |
| GN 2/3-100 | 9 L | 1 | B+ | salad for six (5 L), dough proof, soak |
| GN 2/3-65 perforated | | 1 | B+ | wash, drain |
| GN 2/3 flat lid | | 2 | B+ | cover, toss |
| GN 2/3 thermoplate -40 | multilayer, induction (Rieber class) | 2 | B+ | frying surface 1000 cm² over two coils, pair for the flip |
| GN 2/3 thermoplate -65 | | 1 | B+ | braiser 5.5 L, hob and oven |
| GN 2/3 thermoplate -20 | | 1 | B+ | griddle, flip partner |
| GN 1/3-40 | 325 × 176 | 4 | B+ | breading, mise en place, weighing |
| GN 1/3-65 | | 2 | B+ | one solid (loaf tin, waste tray), one perforated (washing potatoes) |
| Pot Ø 240 × 160 | 6.5 L, tri-ply | 1 | C (bought body, welded tang and skirt) | pasta, potatoes, kneading bowl |
| Pot Ø 240 × 100 | 4 L | 2 | C | soup, vegetables, rice, mixing |
| Pan Ø 240 × 60 | 2.5 L | 2 | C | sauté, pancake |
| Saucepan Ø 160 × 80 | 1.5 L, with adapter lugs for the ring | 2 | C | sauce 0.15–0.8 L, small quantities, chopping |
| Lids Ø 240 (3), Ø 160 (1), splash lid with Ø 40 hole (1) | | 5 | C | |
| Flip disc Ø 240 | tri-ply disc, 10 mm rim | 1 | C | pancake, omelette, Rösti (SM-128) |
| Basket Ø 225 × 150 perforated | | 1 | B+ | pasta, potatoes (SM-155) |
| Carrier ring | | 2 | C | turning positions |

The 9 L pot of COK-016 (priority S) is not in the set: Ø 240 × 200 is too tall for the rear row under the
arm. Pasta for six is cooked in the 6.5 L pot at 0.7 L per 100 g [C 6.3].

**Stem tools (26)**

| Tool | No. | Make | Note |
|---|---|---|---|
| Chef's blade 200 mm | 2 | C (bought blade, welded stem) | red / green |
| Slicing blade 250 mm, scalloped | 1 | C | carving, bread, cake |
| Tongs, sprung U | 2 | C | red / green |
| Egg tongs (two cups Ø 38) | 1 | C | |
| Turner 0.6 mm, 110 × 90 | 2 | C | |
| Steel scraper / spreader 120 mm | 1 | C | also levels and cuts dough |
| Silicone-lipped spatula (one-piece moulded lip on a steel core) | 2 | C, wear part | emptying vessels, folding |
| Whisk | 1 | C (bought head) | 600–1200 rpm |
| Paddle | 1 | C | stirring on the plain positions |
| Blade stalk Ø 12, two-wing blade Ø 55 | 1 | C | chop, purée; 3000–6000 rpm |
| Roller Ø 50 × 250 on a fork | 1 | C | the only rotating joint in ware: plain pin in open hooks, falls apart |
| Fork (three prongs, 40 mm) | 1 | C | peeling spindle, pricking, carving fork |
| Ladle 250 mL | 2 | C | |
| Cup 50 mL | 2 | C | seasoning, weighing |
| Spoons 5 mL and 1 mL | 2 | C | |
| Ring cutter Ø 80 × 30 | 1 | C | patties, dumplings, biscuits |
| Presser plate 120 × 80 | 1 | C | crumbs, smash |
| Spin basket Ø 220 × 120 on a central stem | 1 | C | leaves |
| Squeegee | 1 | C, wear part | deck, hob glass |
| Core-temperature probe | 1 | B+ | wireless probe in a stem holder |

**Cassettes and inserts (30 parts)**

| Cassette | Parts | Driven by | Replaces |
|---|---|---|---|
| Press tube Ø 110 × 200 with flange | tube, plain piston, studded piston (R13), cut-off slide with blade, sleeve insert Ø 60 for long goods, end plates: open mouth, grid 6, grid 10, ricer 3 mm, Spätzle 8 mm, corer-wedger (8 wedges), citrus cone — 12 parts. The piston in use hangs in a fork on the press arm and is swung in and out by the press itself | press; slide stroked by the chuck | slicer, dicer, fries cutter, ricer, juicer |
| Small tube Ø 45 × 160 | tube, piston, nozzle Ø 18, plate 2 mm — 4 parts | press | garlic press, paste syringe, filler |
| Peeler post | one-piece flexure with a bought Y-peeler blade and a stripping slot | — (stands in a tray) | lathe |
| Kneading set | roller arm, scraper arm | turning position | planetary mixer |
| Egg cracker | two half cups on open hook hinges, blade bar; slotted saucer | chuck squeeze | — |
| Rouladen set | silicone apron with two hem bars, trough insert, channel insert for the braiser (8 channels) | chuck | string |
| Boards | HDPE board GN 2/3 (red, green), silicone mat, gauge bars 3/5/8/22 mm, comb fence, steel sling strip for the loaf tin | — | — |

**Total: 93 loose items of about 58 types.** A reference meal uses 40–55 of them. The catalogue's "about 45
items in two sets" does not survive a count for six persons, four heated positions and the whole corpus.

**Where everything is parked.**

| Place | Capacity | Holds | Access |
|---|---|---|---|
| Tray store above the oven | 6 rail levels, nested pairs | all GN 2/3 trays and lids, GN 1/3 trays in a carrier frame on one level, boards and inserts lying in their trays | chuck horizontal, +X |
| Oven, when cold | 3 rails | thermoplates | chuck horizontal, +X |
| Hob | 4 positions | pots with their lids, saucepans nested inside, kneading set inside the 6.5 L pot | chuck vertical |
| Tool wall | 36 pigeonholes | 26 tools, tubes, pistons, peeler post, cracker, a file of end plates | chuck horizontal, −X |
| Wells | 5 slots each | whatever was washed last; a clean well is a store until the other is full | chuck vertical |

The tool wall is full; there is no growth margin. Pots live on the hob and must be moved when another pot is
wanted there (counted in the walk-throughs).

### 2.6 A sleeved low-cost cobot instead of the mast gantry?

Considered against the same bay: a 6-axis arm of the FR5 / xArm 6 class (5 kg, 700–920 mm reach, 4.6–5.3 k€
net [R8]) on the X rail, inside the inflated sleeve of W16.

| Criterion | Mast gantry (this document) | Sleeved cobot on a rail | Better |
|---|---|---|---|
| Reach in a 555 mm deep, 2.5 m long bay | whole bay, straight-line paths | needs the X rail anyway; elbow sweeps 620–920 mm, more than the depth, so poses above the hob and inside the oven are constrained [R8] | gantry |
| Vertical reach (store above oven, tool wall) | 900–1730 | same or better, and can enter shelves from the front | cobot, slightly |
| Payload | 5 kg at 200 mm; stiff | 5 kg including the 1.2 kg chuck and the sleeve drag; a 4 L pot with 2 kg of food is at the limit | gantry |
| Force | 100 N everywhere | about 30–50 N continuous [D:D] | gantry |
| Dexterity | 5 axes; limits listed in 2.1 | 6 axes; pours in any direction, approaches from any azimuth, can baste and plate | cobot |
| Hygiene | closed boxes with three sealing bands and four lip seals above food | one seamless sleeve, pressure-tested before each meal; but it is a 0.5 m² flexing polymer above food, and a knife nick stops the kitchen [D:D] | open; gantry is conventional, sleeve is cleaner if it lasts |
| Cost of the manipulator | about 3.3 k€ | 4.6–5.3 k€ arm + 0.8 k€ rail + sleeve and wrist cap 1.0–1.5 k€ | gantry |
| Software | five-axis canned cycles on fixed stations | six-axis path planning with a sleeve that snags; but also collision detection and force sensing out of the box | gantry for effort, cobot for extensibility |
| Does K6 need its strengths? | — | K6 already moved force to the press and the turning hob, and orientation to the ware (tangs, fixed poses). What is left for a sixth axis is small | gantry |

**Verdict.** For K6 the cobot is not the better manipulator. The concept was built so that the manipulator
only picks, places, tilts and spins fixed-interface ware; that is gantry work, and the gantry does it stiffer,
cheaper and with straight paths in a shallow cabinet. The cobot would earn its place only if serving (plating)
were given to the same manipulator, or if free-form assembly and bone-in carving were required. What I would
take from it: a third wrist axis (roll) as an option on the gantry wrist, one more sealed actuator, if the
critique finds a step that needs it; and the sleeve idea for the wrist alone (a short bellows-free glove over
tilt and spin housings) if the lip seals prove hard to keep clean.

---

## 3. Ingredient intake and dosing

Assumptions: the box is a GN 1/6 or GN 1/3 PP box with a plain lid (exploration brief, ruling 5). The
transport system sets it into the dock cradle; the dock lifts the lid. **No dosing lid is required**; a
sifter lid for flour would help (see requests). Stowed sealed packs are assumed to arrive **already opened**,
standing in a carrier box; opening them is not designed here (request 4).

Two routes: **pour** (the dock tilts the box over a tray or cup standing on S0; closed loop on the dock's
loss of weight and S0's gain) and **take** (the box stays upright and the chuck reaches in with tongs, a spoon
or a ladle). Everything is dosed at the dry left end into a tray or cup and carried to the pot (R8, R9);
nothing is dosed from a box over a steaming vessel.

| Form | Route | Accuracy expected | Confidence; untested |
|---|---|---|---|
| Whole produce (potato, onion, apple, carrot) | Pour by pulse-tilt into the perforated tray on S0; camera counts; surplus pieces back with tongs. Pieces over Ø 100: take with tongs or the fork | ±1 piece; the recipe follows the scale (SM-151) | Medium; rolling and bouncing out of a 40 mm tray |
| Leafy (lettuce, spinach, herbs) | Take with tongs by the handful into the perforated tray on S0; weigh; repeat | ±15 g; part of a lettuce head is cut off on the board first | Medium–low; tongs on leaves tear and drop; ±10 g is not reached |
| Granular (rice, lentils, sugar, frozen peas) | Pour with tapper | ±3 g or ±2 % | High |
| Powder, cohesive (flour, starch, cocoa) | Above 100 g: pour with tapper into a GN 2/3-65 under a loose hood plate with a slot. Below 100 g: ladle or 50 mL cup dipped into the upright box, levelled on the box rim, weighed | ±5 g pour, ±2 g cup | Medium; dust at the dock, bridging in the box corner, caking near a steaming bay (flour at 60–70 % RH) |
| Seasoning 0.2–5 g | 1 mL or 5 mL spoon dipped into the box, tipped by wrist tilt onto the fine scale cup with a spin dither (SM-139); surplus returned to the box | ±0.1–0.2 g | Medium–high; 20–40 s per seasoning, 2–3 min per meal of manipulator time |
| Thin liquid (milk, oil, vinegar, wine, stock) | Pour from the box or the opened carton in its carrier into a cup or tray on S0. Water: four spouts with flow meters (S0, B1, hob rear and front) | ±3 mL from 30 mL up; below that the 5 mL spoon | High for water, medium for oil (film, dribble down the box wall) |
| Viscous paste (mustard, tomato paste, quark, honey) | Take with the 50 mL cup or a spoon from the opened jar or tub; scrape into the dish with the silicone spatula. For Rouladen and filling: loaded into the Ø 45 tube and pushed by stroke (1.6 mL per mm) | ±2.5 g | Medium; two tools and a scrape per dose; the last 15 % of a jar is not reached |
| Solid fat (butter, lard) | Block on the green board, cut by length with the knife against the scale (SM-148) | ±3 g | High |
| Raw meat and fish, pieces | Opened pack or box tipped at the dock onto the red GN 1/3 tray; tongs sort and count | exact count | Medium–high |
| Raw meat, slices that stick together (Rouladen slices, bacon, cold cuts) | Tongs take a corner found by the camera and peel the slice off against the tray rim | — | **Low–medium. Not solved for bacon** (G9). Fallback: diced bacon (adapted), butcher's interleaved slices |
| Mince | Box tipped by the dock onto the red tray; the silicone spatula clears the box | residue ≤ 5 % | Medium |
| Egg | Egg tongs take eggs from the box insert one by one | exact | Medium–high |
| Frozen loose (peas, herbs) | As granular; box is out of the freezer < 90 s | ±3 g | High |
| Frozen block (spinach) | Tongs or fork, straight into the pot | — | Medium |
| Long goods (spaghetti, leek, cucumber) | Spaghetti: pour by pulse-tilt with the box turned long side down into a GN 1/3 tray; leek, cucumber, carrot: tongs | ±10 g (one pulse) | Medium; spaghetti bridging across the box mouth is untested |
| Can, jar, carton, tub, vacuum pack (stowed) | Arrives opened in a carrier. Can and carton: poured at the dock, the can clamped in its carrier. Jar and tub: spoon or spatula. Vacuum pack: slit pack tipped onto the red tray, tongs pull the film away and drop it in the waste tray | — | Medium for can and carton; **low for film and vacuum packs** (limp film on tongs) |

Transfers inside the cell: tray to pot by tilt over the far rim with the silicone spatula following on a
second grip (residue ≤ 1 % for pieces, 1–3 % for dough and mince [R4 10.2]); recipe liquid is used as chase
(SM-119); sticky masses leave the tube by its piston; a pair inversion moves powders and doughs without a
pouring arc (SM-111).

---

## 4. Operation table

Time is manipulator or station time for four persons. "G" = gripper cycles (one grip and one release of a
tool or vessel, whatever happens in between).

### 4.1 Operations of MEAL-018 (no workaround, and the shaping cluster)

| Operation | Mechanism | Sequence | Time, G | Confidence | Untested |
|---|---|---|---|---|---|
| Flip pieces: patty, steak, cutlet (FLP) | Turner with the blade along Y; tilt is the roll (SM-129). For a full thermoplate: pair flip with the second, preheated thermoplate (SM-127) | slide under from the front, lift 30 mm, move 40 mm aside, tilt 180°, withdraw | 6 s per piece, 1 G per pan visit; pair flip 12 s, 2 G | Medium–high for patties and steak; medium for cutlets (crust) | Sticking on bare steel; crumb loss |
| Flip whole-pan items: pancake, omelette, Rösti, fish (FLP) | Flip disc on the pan, both tangs gripped, tilt 90°, spin 180°, set down on the second position; the disc is now the pan (SM-128) | preheat the disc on H2, drain fat to ≤ 30 mL, cover, grip pair, lift, invert, set down, remove the upper pan | 15 s, 2 G | Medium | Hot fat running to the rim during inversion; the pair gaping at the far side; pancake Ø 220, not 280 |
| Assemble layers in a vessel (LAY, TOP, SPR) | Ladle and scraper for sauces, tongs for sheets, cup with dither for cheese | per layer: 2 ladles sauce, level with the scraper, 3–4 sheets with tongs | 40 s and 3 G per layer | High | Picking dry lasagne sheets one at a time from the box |
| Assemble open-hand food (ASM) | Tongs and turner, top-down camera | burger: bun base, patty by turner, toppings by tongs, lid | 60 s per burger | Medium for burger, toasted sandwich, bowl; **low for taco and filled wrap** | Stability on the way to the hatch |
| Carve a boneless roast (CAR) | Roast on the green board, held by the comb fence; slicing blade drawn along Y with 2 mm/stroke descent (SM-032) | set fence, 8–12 draw cuts at the fence pitch (10 mm), turner lifts the slices | 6 s per slice | Medium–high; medium for soft braised meat | Roast creeping along the fence; one hand only |
| Carve bone-in poultry (S) | — | — | — | **Not provided** | — |
| Unmould (UNM) | Tin and receiving tray rim to rim, pair inversion (SM-111); greased and floured tin, steel sling strip under the loaf | grease and flour before filling; after baking and cooling: cover, grip pair, invert, tap, lift the tin | 20 s, 2 G | Medium | Sticking on bare steel; round cakes are baked in the Ø 240 pan on a loose base disc (not in the set yet) |
| Score (SCO) | Knife with depth from Z, force limit | 2–5 s per cut | High | — |
| Stuff rigid cavities (STU) | Small tube with nozzle on the press bars; the item stands in a tray below and is moved by tongs between strokes | 10 s per item | Medium–high | Cannelloni upright in a rack; pepper prepared by hand-like cuts (4.2) |
| Stuff flat pockets, dumpling cores, poultry cavity | Poultry cavity: nozzle; dumpling core: crouton pressed into a ring-cut disc before rounding; flat pockets: none | — | — | **Low; flat pockets not provided (S)** | — |
| Wrap (WRP): cabbage roll, wrap, bacon wrap | Apron and trough as for Rouladen | 45 s per pair | Medium | Leaf tearing; bacon singulation |
| Separate whole cabbage leaves (LSP) | Head blanched whole, outer leaves peeled with tongs | — | — | **Low**; counted as not preparable | — |
| Hand-form small pieces (FRM) | Strand from the small tube (Ø 18 nozzle), cut by the scraper every 25 mm onto a floured tray; balls: tray jiggled; Schupfnudeln: cylinders (adapted) | 4 s per piece | Medium | Gnocchi dough sticking at the nozzle |
| Form patties (FRB) | Mass spread in a GN 2/3-40 between two 22 mm gauge bars with the roller, ring cutter Ø 80 stamps, turner lifts, rest re-rolled once (SM-068) | spread, roll, 8 stamps, lift, re-roll, 4 stamps | 12 patties in about 4 min, 4 G | Medium–high | Mince sticking in the ring; piece mass ±8 %; PRP-023 (5 min) is met with little margin |
| Form dumplings (FRK) | Plugs Ø 45 from the small tube or Ø 80 ring cuts, rounded by jiggling on a wet tray | 5 s each | Medium | Roundness; holding together in simmering water |
| Roll Rouladen (RLT) | Apron in a GN 2/3-20 with a trough insert Ø 55 at the start line; two slices side by side; the filled leading edge sags into the trough; the chuck carries the near hem bar over the far one (SM-079/-080); the rolls drop off the apron end into the channel insert | lay 2 slices, spread, fill, roll: 110 s and 4 G per pair | Medium | Start of the first turn; filling squeezed out at the ends; slices torn at pick-up |
| Secure Rouladen | Seam-down channel insert in the braiser, seam seared first (SM-084); fallback steel pins set with the tongs and counted back (SM-085) | — | Medium; **unproven over a 100 min braise** (shared risk of all candidates) | Browning on three of four sides only |
| Bread (BRD) | Flour, egg and crumbs in three GN 1/3 trays on S0, B1, B2; red tongs carry the cutlet; crumbs pushed over with the presser and pressed at 30 N; two tongs (flour–egg, crumbs) against clubbing (SM-094) | 60 s per cutlet, 3 G per cutlet | Medium | Coverage ≥ 95 % at the tong marks; crumb waste about 30 % |
| Roll out dough (ROL) | Dough on the silicone mat with flour; roller between 3, 5 or 8 mm gauge bars in a GN 2/3-20; 6–8 passes, rest, 4 passes (SM-106) | 90 s, 2 G | Medium–high | Spring-back of yeast dough; sheet 330 × 300, not 400 × 300 |
| Shape dough (SHD) | Loaf: dough dumped in the greased GN 1/3-65; rolls: ring cuts, jiggled round; pizza: rolled in the baking tray itself | — | Medium | — |
| Line a tin with dough (LIN) | Sheet rolled on the mat, mat and sheet inverted onto the tin as a pair, mat peeled by one hem bar, presser tucks the corners | 60 s | Low–medium | Tearing at the corners |
| Knead (KND, KNM) | 6.5 L pot on T4 at 60–100 rpm against the roller and scraper arms; 1.6 kg of dough needs 14–20 Nm [R4] | load, hang the arms, turn, lift the arms out | 6–8 min, 4 G, manipulator free meanwhile; 1.6 kg dough and 1.2 kg mince: yes | High (Ankarsrum) | 100 g of dough in the 1.5 L saucepan on its adapter |

### 4.2 Peeling, trimming, cutting, egg

| Operation | Mechanism | Time | Confidence | Untested |
|---|---|---|---|---|
| Wash produce (WSH) | Perforated tray in the B1 sink under the spout, jiggled, 20–30 s | 1.5 L per kg | High | Soil in potato eyes |
| Wash and dry leaves (WLF, DRY) | Perforated tray dunked in the GN 2/3-100 of water in the sink, lifted, leaves tipped into the spin basket standing in the 6.5 L pot, wrist spins at 500–600 rpm for 20 s (35–45 g) | 2 min per 300 g | Medium | Imbalance on a cantilever arm; tipping leaves into the basket |
| Peel potato, apple, kohlrabi (PLP, PLS, PLH) | Fork stabs the piece through its long axis (top-down camera), spins it at 150 rpm past the sprung blade of the peeler post, pole to pole; knife parts off the fork-end cap; stripping slot pulls the piece off into the tray | 15–18 s per piece; 1.5 kg (12 pieces) in 3.5 min | Medium–high for regular tubers | Stab alignment on lumpy pieces (5–10 % retry); eyes remain; loss 18–22 % with caps |
| Peel carrot, cucumber | Same, stabbed at the thick end; long pieces whip | 12 s | Medium–low; cucumber unpeeled by default | Carrots longer than 150 mm |
| Peel onion and garlic (PLA) | **Bought peeled** (MEAL-012). Reserve: top, tail and slit on the fork, 45 s of steam in the oven, push through a silicone ring end plate on the press (SM-063). Garlic skin-on through the 2 mm plate (SM-064) | — | Reserve: low–medium; garlic press high | Everything |
| Core and wedge apple, pear (COR) | Corer-wedger end plate, fruit centred by the tube | 3 s | High | — |
| Deseed pepper (COR) | Fork holds it stalk-up; knife cuts the cap off in a circle (spin); tongs pull the cap; halves rinsed in the perforated tray | 40 s | Low–medium; frozen strips bought by default | Ribs remain |
| Trim ends (TRE) | Long goods aligned against the tray wall by tongs, one knife cut per end | 10 s per bundle | Medium for leek, carrot, asparagus; **low for beans and sprouts** (bought trimmed) | — |
| Strip, florets (STR) | — | — | **Not provided**; frozen florets, chopped herbs with tender stems | — |
| Slice 1–20 mm (SLI) | Press tube, open mouth, slide cuts once per advance (SM-015) | 1.5 kg potatoes in 90 s | High | Last 10 mm (studded piston pushes it through) |
| Dice 6 or 10 mm, sticks (DIC, JUL) | Press tube with grid and slide (SM-009); staggered blades; column of 60 mm per load needs 1–2.5 kN | 1 kg in 2 min including 4–5 loads | High for potato, carrot, onion halves; medium for soft tomato | Onion layers slipping; tomato squashing; grid pitch fixed at 6 and 10 |
| Wedges, quarters (WED) | Knife on the board, piece held by the fork | 5 s per cut | Medium–high | — |
| Mince, chop herbs < 3 mm (MIN, CHH) | Blade stalk in the 1.5 L saucepan under the splash lid, 3–6 pulses at 3000 rpm; saucepan tilted 20° by its adapter for small amounts | 10 s | Medium–high; herbs are bruised | One garlic clove (goes through the press instead) |
| Grate (GRC, GRF), zest | Bought grated cheese by default; block pushed over a grater end plate is a possible 12th plate | — | Medium; **zest not provided** (bottled zest or omitted) | — |
| Juice citrus (JUI) | Knife halves the fruit on the board; half set on the cone plate; press at 300 N | 10 s per half | High | — |
| Purée (PUR) | Blade stalk in the pot at 6000 rpm under the splash lid, 60–90 s | — | Medium; coarser than a blender (tip speed 17 m/s) | < 1 mm particle size |
| Mash (MSH) | Potatoes boiled skin-on or peeled, basket tipped into the press tube over the pot, ricer plate, 1–2 kN, two loads for 1 kg | 60 s | High | — |
| Crack eggs (CRK) | Egg tongs set the egg in the cracker over the slotted saucer on S0; chuck squeezes the cracker arms: blade scores, cups spread; camera checks the saucer; saucer tipped into the bowl | 12 s per egg; **12 eggs in 2.5 min** | Medium | Shell fragments; the hook hinges; yolk intact ≥ 90 % |
| Separate (SEP) | Saucer slot: white runs off on a 15° tilt, yolk stays | +5 s | Medium | 1 % yolk in white |
| Whip, whisk, emulsify (WHP, WHK, EMU) | Whisk at 600–1200 rpm in the saucepan (1–3 whites) or the 4 L pot (4–6) | 3–4 min | Medium–high | One egg white in a Ø 160 pan: whisk must be tilted |
| Toss salad (TOS) | GN 2/3-100 with lid, pair grip, four slow inversions | 15 s | High | — |
| Drain (DRN) | Basket lifted from the pot, held 20 s, tipped into the serving vessel; small pots tipped through the perforated tray over the sink | — | High | Retaining a measured part of the water (ladle first) |
| Flatten (POU) | Slice on the red board on B2 under the press arm, with the presser plate as platen, at 1 kN | 10 s | Medium–high | — |
| Stir while cooking (STC) | Turning positions with the scraper arm (continuous); plain positions: paddle visits every 2–4 min | — | High / medium | Two continuous stirs at once is the limit |
| Baste, glaze, grease (BST, GLZ, LIN) | Ladle; silicone spatula as brush substitute | — | Medium | — |

---

## 5. Benchmark walk-throughs

Conventions. **G** = gripper cycles until the food is handed over (fetching ware and tools, working, hanging
soiled items in a well). **R** = cycles afterwards to carry washed ware back to its store; they fall in idle
time. A cycle takes 9 s on average (1 m of travel at 1 m/s, grip, release); steps in which the manipulator
works longer are timed separately. Onion and garlic arrive peeled (MEAL-012). Boxes are brought and opened
by transport and dock; that costs no G. All times are estimates for four persons unless stated; elapsed time
runs from the order. "Loads" = wash-well loads of five slots.

### B1 Rinderrouladen, Rotkohl, Salzkartoffeln (4 persons, 8 Rouladen)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–2 | Set-up: apron tray with trough to B1; red GN 1/3 on S0, meat pack tipped onto it; braiser thermoplate with channel insert to hob column 1; mustard jar at the dock | apron set, red tray, braiser | 5 |
| 2–10 | Roll four pairs. Per pair: tongs lay two slices; spatula takes mustard from the jar and spreads; tongs place bacon, pickle spear, onion; chuck takes the hem bar and rolls both; tongs carry the two rolls seam-down into the channels and fetch the next slices | red tongs, spatula, apron | 17 |
| 10–20 | Sear the seam side 3 min, turn twice with the tongs; dose wine, stock, tomato paste, sliced onion, salt, pepper into one GN 1/3 at the dock; tip in, scrape, lid on; braiser into the oven at 160 °C | braiser, lid, GN 1/3, ladle for oil, spoon | 9 |
| 20–34 | Red cabbage: fork carries the head to the green board; knife halves, cores, cuts 8 wedges; press tube with open mouth on B2; four loads (tongs load, chuck strokes the slide, 3 mm); apple peeled on the fork, quartered and cored by knife, sliced; onion sliced | board tray, press tube (4 parts), GN 2/3-65, peeler post, fork, knife, green tongs | 23 |
| 34–38 | Fat, onion, cabbage and apple into the 4 L pot on T4 (column 2, so that column 1 stays free for the braiser); vinegar, wine, sugar, salt, cloves dosed and tipped; scraper arm in, slotted lid on; turns at 10 rpm, 85 min | 4 L pot, scraper arm, lid, GN 1/3, spoon | 8 |
| 90–100 | Potatoes: 1 kg poured into the perforated GN 1/3, washed in the sink, peeled on the fork (9 pieces, 2.5 min), stripped into the basket in the 6.5 L pot on H2; water from the spout, salt, lid | perforated GN 1/3, post, fork, 6.5 L pot, basket, spoon | 8 |
| 100–126 | Boil 25 min; basket lifted, held 20 s, tipped into a GN 2/3-40 with lid | GN 2/3-40, lid | 3 |
| 120–130 | Braiser to the hob; rolls lifted into a warm GN 2/3-40; insert out; flour slurry whisked in; 5 min | tongs, whisk, cup, tray | 6 |
| 130–132 | Hand-over of four vessels | | 4 |
| during | Vessels and cassette parts hung in the wells (tools are released there at the end of their own cycle) | | 15 |

**Result: adapted** (Rouladen untied and seam-down; potatoes whole instead of quartered; diced bacon if the
slices cannot be singulated; sauce not strained). Elapsed **132 min** (limit 183). **G = 98, R = 45, 9 loads.**
Soiled: 4 cooking vessels, 7 trays, 3 lids, 14 tools, press tube, apron set, insert, board.
Weak steps: slice pick-up, first turn of the roll, halving a hard cabbage head at ≤ 100 N (rocking draw cut,
medium), seam staying shut for 100 min.

### B2 Wiener Schnitzel, Bratkartoffeln, Gurkensalat (4 persons)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–2 | Set-up: water on in the 6.5 L pot (H2, 2 L); press tube with open mouth on B2 | pot, basket, tube | 8 |
| 2–9 | Potatoes 1.2 kg washed, peeled raw (3 min), sliced 5 mm through the tube into the basket | perforated GN 1/3, post, fork, tongs | 9 |
| 9–16 | Parboil 6 min, basket lifted and drained over the pot | | 2 |
| 16–40 | Thermoplate on hob column 1 with 30 mL fat; slices tipped in; diced onion and bacon after 10 min; turned five times with the turner | thermoplate -40, turner, ladle | 9 |
| 10–14 | Cucumber through the tube with the sleeve insert, 2 mm; sour cream, vinegar, oil, sugar, salt, frozen dill dosed into a cup tray; both into a GN 2/3-65, lid, pair inversion ×4; stands 15 min | GN 2/3-65, lid, GN 1/3, spoon, spatula | 8 |
| 14–20 | Breading set-up: flour, crumbs poured into GN 1/3 trays; 2 eggs cracked, tipped into the third tray, whisked; trays on S0, B1, B1 | 3 × GN 1/3, cracker, saucer, egg tongs, whisk | 11 |
| 20–25 | Four cutlets: salt, flour (tongs 1), egg, crumbs pushed over and pressed (presser), tongs 2 to a holding tray | red tongs ×2, presser, GN 2/3-20, spoon | 13 |
| 26–36 | Second thermoplate on column 2, 150 mL fat at 165 °C; four cutlets laid in from the front, 3 min, turned one by one with the turner, 3 min, lifted onto the perforated tray | thermoplate -40, turner, perforated GN 2/3 | 7 |
| 40–42 | Hand-over of three vessels | | 3 |
| during | To the wells | | 20 |

**Result: yes**, with two changes of order: potatoes are peeled raw, sliced and parboiled (not boiled whole
the day before), and cucumber stays unpeeled. Elapsed **42 min** (limit 67). **G = 90, R = 44, 9 loads.**
Both hob columns are taken by the thermoplates from minute 26, so the potato pot must be gone by then.
Weak steps: crumb coverage at the tong marks, crumb crust at the turner flip, used flour–egg–crumb trays
(raw-meat contact) are waste: about 30 % of the crumbs.

### B3 Frikadellen, Kartoffelpüree, Erbsen-Möhren-Gemüse (4 persons, 8 patties)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–2 | Set-up: 2 L water on in the 6.5 L pot (H2); tube with grid 10 on B2; bread and milk into the 4 L pot on T4 | pots, tube | 8 |
| 2–8 | Potatoes 1 kg washed, peeled (2.5 min), pushed through grid 10 as sticks into the basket | perforated GN 1/3, post, fork, tongs | 8 |
| 8–19 | Boil 10 min (sticks); basket lifted out and parked in a GN 2/3-65; the pot (2 L, 3.5 kg gross, inside the 5 kg limit) is carried to the sink and emptied; milk and butter warm in the same pot | GN 2/3-65 | 4 |
| 6–9 | Carrots (3, short) peeled on the fork, diced 10 mm with the slide into a GN 1/3 | fork, tongs, GN 1/3 | 4 |
| 9–14 | Mince 600 g tipped into the 4 L pot; egg cracked in; frozen diced onion, mustard, salt, pepper, parsley dosed and tipped; kneading arms in; T4 turns 2 min | cracker, saucer, egg tongs, spoon, cup, arms | 12 |
| 14–19 | Mass tipped into a GN 2/3-40, rolled between the 22 mm bars, 5 stamps, turner to the thermoplate, re-roll, 3 stamps | GN 2/3-40, spatula, roller, ring, turner, bars | 9 |
| 19–32 | Eight patties fry in one thermoplate on column 1, 6 min a side; turned one by one with the turner from the front (50 s); probe reads 72 °C | thermoplate, turner, ladle, probe | 4 |
| 19–22 | Grid plate exchanged for the ricer plate; pot with hot milk set under the tube on B2; potatoes tipped into the tube; two strokes; paddle folds | ricer plate, paddle | 9 |
| 20–32 | Carrots 8 min and frozen peas 4 min in the second 4 L pot on T4 (free since minute 14) with butter, sugar, salt; drained through the perforated tray over the sink; back into the pot | 4 L pot, perforated GN 2/3, spoon | 7 |
| 33–35 | Hand-over of three vessels | | 3 |
| during | To the wells | | 22 |

**Result: yes.** Elapsed **35–40 min** (limit 50). **G = 90, R = 42, 8 loads.** The manipulator is busy for
about 26 of these minutes (13.5 min of cycles, 12 min of peeling, stamping, stroking, dosing): this is the
benchmark with the least slack, and one retry-heavy step (a potato that will not centre, a patty stuck in the
ring) eats the margin. 12 patties for six: 4 min of forming, inside PRP-023.
Weak steps: mince in the ring cutter; the hob is full (one thermoplate on column 1, two pots on column 2),
so the pair flip is not available here and the patties are turned singly.

### B4 Spaghetti Bolognese with grated cheese (4 persons)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–2 | Set-up: tube with grid 6 on B2, 4 L pot on T4 | | 6 |
| 2–9 | Onion (2) and carrot (1, peeled on the fork) diced 6 mm; garlic skin-on through the small tube; celeriac bought as peeled cubes and pushed through the same grid | fork, post, tongs, small tube (3 parts), GN 1/3 | 12 |
| 9–20 | Oil; mince 500 g seared in the pot, paddle breaks it up (3 visits); vegetables in; tomato paste | paddle, ladle, cup, spatula | 8 |
| 20–25 | Wine, stock, tinned tomatoes poured at the dock into a GN 2/3-65, tipped in; herbs, sugar, salt; scraper arm in; slotted lid | GN 2/3-65, spoon, arm, lid | 7 |
| 25–70 | Simmer 45 min on T4, turning; no manipulator | | 0 |
| 50–62 | 3 L of water in the 6.5 L pot on H1 (11 min at 3.5 kW); salt | pot, basket | 2 |
| 62–72 | Spaghetti 400 g pulse-poured into a GN 1/3, tipped into the basket, pushed under with the paddle; 9 min; basket lifted and tipped into a GN 2/3-65 | GN 1/3, GN 2/3-65, paddle | 6 |
| 72–74 | Cheese, bought grated, 60 g into a cup; hand-over of three items | cup | 4 |
| during | To the wells | | 14 |

**Result: yes** (cheese bought grated; a grater end plate would be a 13th plate for 22 + 29 corpus meals and
is the first candidate to add). Elapsed **74 min** (limit 96). **G = 59, R = 30, 6 loads.**
Weak step: 250 mm spaghetti into a Ø 225 basket.

### B5 Pizza with yeast dough from flour (2 trays)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–4 | Flour 500 g poured into a GN 2/3-65 under the hood plate and tipped into the 6.5 L pot on T4; water 320 mL at 30 °C from the spout; yeast, salt, oil by spoon and cup; kneading arms in | GN 2/3-65, spoon, cup, arms | 9 |
| 4–12 | Knead 8 min at 80 rpm | | 0 |
| 12–72 | Arms out, lid on; proof 60 min at 30 °C (T4 coil at low power, controlled by the pot-base sensor) | lid | 3 |
| 60–70 | Oven to 250 °C; sauce: tinned tomatoes, salt, oregano, oil in a GN 1/3; mozzarella block diced 10 mm through the tube | tube, tongs, 2 × GN 1/3, spoon | 10 |
| 72–80 | Dough tipped onto the floured mat on B1, halved with the scraper (S0 checks the halves), each half laid in an oiled GN 2/3-20, rolled out with the roller and pushed to the edge with the presser; 5 min rest; rolled again | mat tray, 2 × GN 2/3-20, scraper, roller, presser, spatula | 12 |
| 80–84 | Per tray: two ladles of sauce spread in a spiral with the spatula, mozzarella scattered from the cup, salami and basil with the tongs | ladle, spatula, cup, tongs | 8 |
| 84–96 | Both trays into the oven, 10–12 min; out; hand-over | | 4 |
| during | To the wells | | 10 |

**Result: yes** (rounded rectangles 330 × 300, the home "Blechpizza"). Elapsed **96 min** (limit 113).
**G = 56, R = 24, 5 loads.** Weak steps: salami slices stuck together; yeast dough springing back.

### B6 Gemüseeintopf from whole vegetables (6 persons, 3 L)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–2 | Set-up: tube with grid 10 on B2; 6.5 L pot on T4; GN 2/3-65 under the tube | | 6 |
| 2–9 | Carrots 300 g, parsnip 150 g, potatoes 500 g: washed, peeled on the fork (11 pieces, 3.5 min) | perforated GN 1/3, post, fork | 5 |
| 9–14 | Diced 10 mm in four loads | tongs, slide | 8 |
| 14–19 | Leek: ends cut on the board, halved lengthwise, cut into 10 mm pieces with 30 knife strokes, washed in the perforated tray (grit) | board tray, knife, tongs, perforated GN 2/3 | 6 |
| 19–23 | Celeriac 200 g: held on the fork, skin cut away in six facets against the fixed blade of the post (loss about 30 %), then diced; tomatoes (2) cut into eight wedges on the board | fork, knife | 5 |
| 12–24 | Oil into the pot; leek and roots in as they are ready; scraper arm in; sweated 5 min | ladle, spatula, arm | 6 |
| 24–28 | 1.8 L stock and water; frozen cut green beans and peas poured and tipped; salt, pepper; slotted lid | GN 1/3, spoon, lid | 5 |
| 28–52 | Simmer 22 min; parsley (frozen chopped) in at the end | cup | 1 |
| 52–54 | Hand-over of the pot | | 1 |
| during | To the wells | | 13 |

**Result: adapted.** Carrot, parsnip, potato, leek, celeriac and tomato are taken whole; **green beans are
bought trimmed** (no mechanism for topping and tailing, G10), and fresh parsley would need washing, spinning
and the blade (+6 G, feasible). Celeriac facet-peeling is medium–low. Elapsed **54 min** (limit 60 for six).
**G = 56, R = 28, 6 loads.**

### B7 Steak, oven fries, mixed salad with vinaigrette (2 persons)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–2 | Set-up; oven to 220 °C with fan; tube with grid 10 on B2 | | 5 |
| 2–7 | Potatoes 500 g washed, peeled (5 pieces), pushed through the grid without the slide: sticks 10 × 10 | perforated GN 1/3, post, fork, tongs | 7 |
| 7–11 | Sticks rinsed in the perforated tray, spun in the basket (20 s), tossed with 10 mL oil and salt in a lidded GN 2/3-65 (pair inversion), spread on a GN 2/3-20 | perforated GN 2/3, spin basket, 6.5 L pot, GN 2/3-65, lid, GN 2/3-20, spatula | 11 |
| 11–38 | Bake 25 min; after 15 min the tray is taken out, shaken and returned | | 3 |
| 12–22 | Salad: lettuce cut in quarters on the board, leaves loosened with the tongs into the perforated tray, dunked, spun in two loads; tomato wedges by knife; cucumber and radish through the tube (open mouth, sleeve); carrot through grid 6 as fine sticks instead of grated; pepper bought as strips | board tray, knife, tongs, spin basket, GN 2/3-100, tube parts | 19 |
| 22–25 | Vinaigrette: oil, vinegar, mustard, salt, pepper into the saucepan, whisk 20 s | saucepan, whisk, spoon, cup | 5 |
| 28–36 | Pan Ø 240 on H1 to 250 °C, oil; two steaks laid in with the red tongs; 2.5 min; turner flip; butter, thyme, garlic; 2 min; probe 54 °C; steaks to a warm GN 1/3, rest 5 min | pan, red tongs, turner, probe, ladle, GN 1/3 | 9 |
| 36–38 | Dressing over the leaves, lid, four inversions; hand-over of three items | lid, spatula | 5 |
| during | To the wells | | 16 |

**Result: yes** (basting is reduced to butter melted over the steak: the wrist cannot tilt the pan towards a
spoon; carrot as fine sticks, not grated). Elapsed **38 min** (limit 79). **G = 80, R = 36, 7 loads.** Twice
the ware of a cook for two plates: the salad alone costs 24 G.

### B8 Pfannkuchen (8 pieces)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–5 | Flour 250 g, salt, sugar into the 4 L pot; 3 eggs cracked (saucer checked each time); milk 500 mL; whisk at 800 rpm for 60 s; 30 mL oil into the batter | pot, GN 1/3, cracker, saucer, egg tongs, whisk, spoon | 17 |
| 5–25 | Batter rests 20 min; pan on H1 and flip disc on H2 heat to 190 °C from minute 20 | pan, flip disc | 2 |
| 25–43 | Per pancake (2.2 min, 5 G): ladle 100 mL into the pan; chuck takes the pan by its tang and swirls it (tilt and spin give pitch and roll); 80 s; the hot disc is laid on; both tangs gripped, inverted, set down on H2; the pan goes back to H1 and takes the next ladle; after 50 s the disc is tilted and the pancake slides onto the holding tray in the oven at 70 °C; the disc returns to H2 | ladle, GN 2/3-20 | 40 |
| 43–44 | Hand-over | | 1 |
| during | To the wells | | 8 |

**Result: yes**, Ø 220 instead of 250–280 (pan family Ø 240), no sifting. Elapsed **44 min** (limit 50).
**G = 68, R = 16, 3 loads.** The flip itself is the step every candidate shares (SM-127/-128); specific to K6:
the pair is clamped at one side only, and the pan is lifted off the hob 16 times.

### B9 Chicken curry with rice (4 persons)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–2 | Set-up: tube with grid 6 on B2; 4 L pot on T4, second 4 L pot on H2 | | 6 |
| 2–8 | Onion diced 6 mm; garlic and ginger through the small tube; zucchini through the tube with the slide, 10 mm half slices; pepper bought as frozen strips | tongs, small tube, GN 1/3 ×2 | 10 |
| 8–12 | Rice 300 g poured into the pot on H2, 600 mL water, salt, lid; 15 min absorption, 5 min rest (rice is not rinsed: no fine sieve in the set) | pot, lid, spoon | 3 |
| 8–14 | Chicken, bought cubed, tipped onto the red tray; oil in the pot; onion, garlic, ginger, curry paste sweated with the scraper arm turning; chicken in | red GN 1/3, ladle, cup, arm, spatula | 9 |
| 14–32 | Coconut milk (opened tin, poured at the dock), vegetables, sugar, salt; simmer 15 min, turning; lime juiced on the cone plate | GN 2/3-65, knife, cone plate, spoon | 9 |
| 32–34 | Hand-over of two pots | | 2 |
| during | To the wells | | 13 |

**Result: yes** (chicken bought cut; cutting raw breast into cubes with one hand against the comb fence is
medium–low). Elapsed **34 min** (limit 56). **G = 52, R = 28, 6 loads.**

### B10 Lasagne, layered, béchamel from scratch (4 persons, one GN 2/3-65)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–25 | Ragù as B4 up to the simmer (onion, carrot, mince, tomato, wine), in the 4 L pot on T4 | as B4 | 33 |
| 25–65 | Simmer 40 min, turning | | 0 |
| 45–60 | Béchamel in the second 4 L pot on T3. The only scraper arm is in the ragù, so the paddle visits every 40 s for 10 min; butter 50 g cut on the board, flour 50 g by cup, roux 2 min, milk 600 mL in four ladle additions from a GN 2/3-65, nutmeg, salt | pot, paddle, knife, cup, ladle, GN 2/3-65, spoon | 22 |
| 55–60 | Oven to 190 °C; GN 2/3-65 greased with the spatula, set on B1 | GN 2/3-65, spatula | 2 |
| 65–74 | Four layers: two ladles of ragù levelled with the scraper; one ladle of béchamel; three sheets taken on edge from the box at the dock with the tongs. Top: béchamel, grated cheese from the cup with dither | 2 ladles, scraper, tongs, cup | 14 |
| 74–114 | Bake 40 min; rest 15 min in the open oven | | 2 |
| 129 | Hand-over in its tray | | 1 |
| during | To the wells | | 18 |

**Result: yes.** Elapsed **129 min** (limit 148). **G = 92, R = 38, 8 loads.**
Weak steps: the béchamel ties the manipulator for ten minutes of short visits, because only one scraper arm
exists and the ragù has it (a second arm is the obvious addition); single dry sheets out of the box.

### B11 Rührkuchen in a tin, unmoulded

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–6 | Butter 250 g cut on the board into the 4 L pot, softened at 30 °C on T4; sugar 200 g poured and tipped; whisk at 300–600 rpm, 3 min | pot, board tray, knife, GN 1/3, whisk | 8 |
| 6–12 | Four eggs cracked one at a time, whisked in; flour 500 g and baking powder mixed dry in a GN 2/3-65, tipped in three parts alternating with 125 mL milk; T4 turns at 30 rpm against the scraper arm (fold) | cracker, saucer, egg tongs, GN 2/3-65, spoon, cup, arm | 19 |
| 3–8 | Loaf tin (GN 1/3-65, 2 L) greased with the spatula, dusted with a spoon of flour, tilted four ways, tapped out over the sink; sling strip laid in | tin, spatula, spoon, sling | 5 |
| 12–14 | Batter tipped into the tin with the spatula following; levelled; into the oven at 175 °C | spatula | 4 |
| 14–74 | Bake 60 min; probe at 55 min | probe | 1 |
| 74–94 | Cool 20 min on B1 | | 1 |
| 94–96 | GN 1/3-40 laid on the tin, both tangs gripped, inverted, tapped twice on the bench, tin lifted off; hand-over on the tray | GN 1/3-40 | 4 |
| during | To the wells | | 10 |

**Result: adapted.** The cake leaves the machine base-up on a tray; turning it back dome-up needs a second
inversion between two trays of unequal gap and is low–medium. Creaming with a whisk at ≤ 3.8 Nm works only
with softened butter. Release from a bare steel tin is medium (grease, flour, sling); the reserve is a sheet
of baking paper (W21), which is a consumable. Elapsed **96 min** (limit 125). **G = 52, R = 22, 4 loads.**

### B12 Scrambled eggs from shell eggs, toast (1 person)

| t (min) | Block | Vessels and tools | G |
|---|---|---|---|
| 0–1 | Pan Ø 240 on T4 with its ring at 110 °C; griddle (thermoplate -20) on column 1 at 180 °C; butter 10 g into the pan by spoon | pan, griddle, spoon | 3 |
| 1–3 | Cracker and saucer on S0; three eggs: tongs place, chuck squeezes, camera checks, saucer tipped into the saucepan (3 G per egg) | cracker, saucer, egg tongs, saucepan | 12 |
| 3–4 | 30 mL milk, salt; whisk tilted 20°, 15 s; tipped into the pan, spatula follows; scraper arm in | whisk, spoon, spatula, arm | 5 |
| 4–7 | T4 turns at 20 rpm for 2.5 min; two slices of toast laid on the griddle, turned after 70 s | tongs, turner | 2 |
| 7–8 | Chives (frozen) over; pan and toast handed over | spoon | 3 |
| during | To the wells | | 9 |

**Result: yes.** Elapsed **8–9 min** (limit 17). **G = 34, R = 13, 2 loads.** Thirteen items and 6.5 L of
wash water for one plate of scrambled eggs: the minimum-quantity case is where loose ware is least efficient.
Scrambled egg on bare steel sticks; the pan goes to the well within 2 min (cold pre-spray).

### 5.13 Summary

| # | Benchmark | Result | Elapsed / limit (min) | G | R | Loads | Main reservation |
|---|---|---|---|---|---|---|---|
| B1 | Rouladen, Rotkohl, Salzkartoffeln | adapted | 132 / 183 | 98 | 45 | 9 | untied seam; slice pick-up |
| B2 | Schnitzel, Bratkartoffeln, Gurkensalat | yes | 42 / 67 | 90 | 44 | 9 | crumb coverage |
| B3 | Frikadellen, Püree, Erbsen-Möhren | yes | 35–40 / 50 | 90 | 42 | 8 | manipulator has no slack |
| B4 | Spaghetti Bolognese | yes | 74 / 96 | 59 | 30 | 6 | cheese bought grated |
| B5 | Pizza, 2 trays | yes | 96 / 113 | 56 | 24 | 5 | topping slices |
| B6 | Gemüseeintopf, 6 persons | adapted | 54 / 60 | 56 | 28 | 6 | beans bought trimmed; celeriac |
| B7 | Steak, oven fries, salad | yes | 38 / 79 | 80 | 36 | 7 | no basting |
| B8 | Pfannkuchen, 8 | yes | 44 / 50 | 68 | 16 | 3 | pair flip, Ø 220 |
| B9 | Chicken curry, rice | yes | 34 / 56 | 52 | 28 | 6 | rice not rinsed |
| B10 | Lasagne | yes | 129 / 148 | 92 | 38 | 8 | béchamel ties the manipulator |
| B11 | Rührkuchen, unmoulded | adapted | 96 / 125 | 52 | 22 | 4 | base-up; release |
| B12 | Scrambled eggs, toast, 1 person | yes | 9 / 17 | 34 | 13 | 2 | 13 items for one plate |

Nine yes, three adapted, none no. Mean G = 69, mean G + R = 100. The catalogue's estimate of 80–120 moves
per meal is confirmed for full menus (B1, B2, B3, B10: 132–143 with returns).

**Other persons counts.** One person: the pot and tray family is sized for six, so small amounts go to the
Ø 160 saucepans (0.15 L sauce, one egg white, 100 g dough); G falls by 15–25 %, loads by half. Six persons:
B2 needs two frying batches of cutlets (+10 min, +8 G), B3 twelve patties in one thermoplate and a re-roll
(+2 min), B1 twelve Rouladen in two layers of channels is not possible: a second braiser is not in the set,
so **Rouladen for six need 8 + 4 in the thermoplate -65 and the -40** (+6 G). Pasta for six in 6.5 L.

**Reference menus of corpus 4.9** not covered above, in one line each: Käsespätzle (Spätzle plate over the
pot, three loads; yes); fish fingers from fillet (breading as B2; yes); roast pork with dumplings (roast in
the thermoplate -65 in the oven, scored with the knife, carved against the comb fence; dumplings by ring cut
and jiggle, medium); duck ≤ 2.5 kg (roasted whole, **not carved**: served in parts only if bought in parts);
asparagus with hollandaise (asparagus bought peeled; hollandaise whisked in the saucepan at 65 °C on T3 with
the wrist whisk for 6 min, medium); butter chicken with naan (naan rolled and cooked on the griddle, six
singly; yes, slow); burger (patties as B3, buns toasted on the griddle, stacked with turner and tongs;
medium); breakfast for six (12 pancakes take 27 min alone: over the limit unless two pans and the second
thermoplate run in parallel; **marginal**).

---

## 6. Cleaning

### 6.1 The wash wells

Two wells, front and back, each 365 × 262 × 440 mm deep, welded 1.4404, coved, floor sloped to a Ø 40 outlet.
A comb of knife-edge rods at the top carries five slots at 45 mm pitch. Every item hangs by its own geometry
with the tang up: trays on edge (a -65 tray takes two slots), a pot on its side with the mouth towards an
end wall (three slots), four stem tools side by side in one slot, plates and pistons in a file slot. The
load pattern per item type is fixed and validated once (rule C4 of E). The chuck releases the tang above the
coaming and never enters the chamber.

Spray: 28 fixed flat-fan nozzles in the two end walls shoot along X into the gaps between the hanging items;
two turbine-driven rotary heads in the floor shoot up; four nozzles at the top are aimed at the tangs. One
pump (60 L/min, 0.9 bar, 250 W) is switched between the wells. Tank 10 L at 60 °C with a 2 kW heater; boiler
8 L at 85 °C with 3 kW; dosing pumps for detergent and rinse aid; softener. All of this is commercial
undercounter-washer hardware [R5 10.1] in a custom chamber.

| Step | Medium | Time | Water |
|---|---|---|---|
| Wet parking while the well fills | 3 s cold mist every 2 min, lid closed | — | 0.2 L |
| 1 Pre-spray | cold mains, to drain through the strainer (protein and starch leave before heat, R11) | 12 s | 0.8 L |
| 2 Wash | tank water 60 °C, alkaline detergent 2 g/L | 100 s | recirculated |
| 3 Drain back | | 10 s | — |
| 4 Rinse | fresh water 85 °C with rinse aid, runs into the tank and regenerates it | 20 s | 2.2 L |
| 5 Dry | lid opens 40 mm, fan 60 m³/h | 45–60 s | — |
| **Total** | | **3.3–3.5 min** | **3.2 L, 0.24 kWh** |

Thermal disinfection: 20 s at 85 °C plus the time the steel stays above 75 °C gives A0 ≥ 60 on every cycle
(to be proven with loggers on the coldest item, HYG-021). Every load is disinfected, so class R ware needs no
special programme. Steel leaves at about 75 °C and dries by its own heat (a 1 kg tray stores 25 kJ above
30 °C, enough for 10 g of water [E:B]); the two silicone spatulas, apron, mat, squeegee and HDPE boards need
4 min of fan and are the only items that can fail HYG-024.

**Long programme.** One well can be run with its own fresh 6 L fill at 50 °C with enzymatic detergent for
15 min, then rinsed as above. It is for burnt-on cookware (WSH-006), used perhaps once in three warm meals.
The 100 s cycle will not remove burnt milk or a baked fond; that is known from commercial practice, where pots
are soaked.

**Throughput.** One load per 3.5 min per well while the boiler keeps up. The boiler reheats one rinse in
3.7 min at 3 kW, and holds three rinses in reserve. While two hob positions and the oven are at full power
(9 kW of the 10.3 kW allowed, UTL-010) the boiler gets about 1 kW, and the sustained rate falls to **one load
per 8–10 min**. The benchmark with the most ware before serving (B2) sends 5 loads in 40 min, which still
fits; the rest is washed after hand-over. All ware of a full menu is clean, dry and stored **15–20 min after
hand-over** (PERF-005: 30 min required, 45 min "should" for complete cleanliness).

**Can it be the central washer of D7?** For internal ware, yes: a PP box hangs in a slot on an adapter hook
(GN 1/3 box: two slots) and lids in a file slot, 40 boxes a day would be 10–12 loads; plastics need the
4-minute fan step and probably a lower rinse temperature to protect the box. For the human's dishes, no: a
well takes five plates, and the human cannot hang ware into it. A household dishwasher remains (WSH-001).

### 6.2 Water, energy and time per meal (cleaning only)

| Item | Water | Energy | Basis |
|---|---|---|---|
| Wash loads of a reference meal (7 of them; full menus 8–9) | 22–29 L | 1.7–2.2 kWh | 3.2 L and 0.24 kWh per load |
| Share of the daily tank fill and heat-up (10 L, 0.56 kWh, three meals a day) | 5 L | 0.3 kWh | half booked to the full warm meal |
| Share of the daily bay wash-down (10 L fresh rinse; the wash liquor is the old tank water) | 5 L | 0.2 kWh | same |
| Chuck jet gate, mist, strainer back-flush | 1 L | — | |
| Long programme, one meal in three | 2 L | 0.1 kWh | |
| **Reference meal** | **35 L (33–42)** | **2.3 kWh (2.2–2.8)** | |
| Time during which cleaning delays cooking | 0 min | | wash runs in parallel |
| Time from hand-over to everything clean, dry, stored | 15–20 min | | |

Against the requirements: RES-005 allows 45 L per reference meal including the human's dish washer (about
10 L) and cooking water (about 4 L): **K6 lands at 47–56 L, over the limit**. RES-001 allows 4.0 kWh including
cooking (1.3) and dish washer (0.9): **K6 lands at 4.4–5.0 kWh, over the limit**. Detergent about 75 g per day
against 60 g (RES-008, priority S). These are the prices of washing 40–50 items per meal at 85 °C. Levers:
fuller loads (a sixth slot), rinse at 2.0 L, heat recovery from the drain, fewer items.

### 6.3 Surface inventory

**Zone F: the ware, and nothing else.**

| Group | Items | Food-side area (m²) | Material, finish | Wash pose | Dries by | Verified by |
|---|---|---|---|---|---|---|
| GN trays and lids | 21 | 2.5 | 1.4301, 2B or polished; **flat flange, not rolled** | on edge, tang up | own heat | camera on lift-out |
| Pots, pans, lids, disc, basket, rings | 16 | 1.2 | tri-ply, polished inside | on the side, mouth to the end wall | own heat | camera |
| Stem tools | 26 | 0.5 | 1.4404 / blade steel 1.4116; two silicone lips | hanging, four per slot | own heat; silicone by fan | camera, spun once in the chuck |
| Cassettes and inserts | 30 | 0.8 | 1.4404, UHMW-PE pistons, HDPE boards, silicone apron and mat | fallen apart; plates in file slots | heat; polymers by fan | camera; grids against a back light |
| **Total** | **93** | **5.0** (about 9 m² counting both faces) | | | | |

Soiled per reference meal: 1.3–1.6 m² food-side. Fixed Zone F area: **0 m²**.

**Zone S.**

| Surface | m² | Soiled by | Cleaned | How it drains and dries |
|---|---|---|---|---|
| Deck with bench frames, S0, hob glass | 1.1 | drips from carried ware, flour, splashes, boil-over | after each meal: squeegee tool and spout water on the hob glass and frames (2 min); daily wash-down | 3° to the sink basin; fan, door vent |
| Sink basin and strainer | 0.4 | produce soil, peel, shell, drained water | flushed after each use; daily wash-down; strainer back-flushed into the bin | outlet Ø 90 |
| Rear wall, door inside, left wall, ceiling | 5.9 | aerosol, steam, grease near the hob | daily wash-down | vertical or 5° slope |
| Mast, arm, wrist, chuck | 0.7 | steam, grease, splashes; **chuck: tang contact** | chuck: jet gate after each class R ware contact; all: daily wash-down with a fixed sequence of poses | closed boxes, 3° slopes |
| Press arm, bars, column, anchor pins, spouts, dock cradle | 0.3 | juice, splashes, dust | daily wash-down | round bars |
| Tower faces, store shutter | 0.6 | aerosol | daily wash-down with the shutter closed | vertical |
| Tray store rails, tool wall rods (behind shutter and screen) | 0.4 | only clean dry ware touches them | every 30 days, emptied (HYG-037) | rods |
| Wash wells inside, lids | 1.3 | everything | every cycle; hot self-clean with the daily tank dump | floor slope, fan |
| **Total** | **10.7** | | | |

Daily wash-down: before the tank is dumped, its 10 L of hot liquor is pumped through 14 fixed nozzles and
two rotary heads in the ceiling corners while the manipulator runs a fixed sequence of poses; the liquor
returns over the deck to the sink and is recirculated for 4 min; then 10 L of fresh water at 65 °C, the
squeegee tool, 30 min of fan. Twenty minutes in all, in the night. **This wash-down is a rinse of a large,
cluttered splash zone and its coverage is not proven**: 10.7 m² is the largest Zone S of what I would expect
from any candidate, because the bay is long and everything in it is open.

### 6.4 Raw and ready-to-eat within one meal

* Sequence rule: dry, then ready-to-eat, then raw vegetable, then raw animal food (SM-208). The scheduler
  orders the blocks of section 5 that way where the timing allows (B1 does not: meat first).
* Red and green instances exist for the items that overlap in time: knife, tongs, board, GN 1/3 trays, turner.
  Anything else that touched class R goes to the well before its next use; a well cycle is 3.5 min and every
  cycle disinfects.
* The chuck touches only tangs. After it has carried a class R tray or pot it passes a **jet gate** at the
  wells (two fan nozzles, 85 °C rinse water, 4 s, 0.15 L) before it takes a green item.
* A witness coupon (SM-207) rides in the first red load of each meal.
* Benches are frames; a spill of meat juice on the deck is squeegeed and flushed at once and the bay is
  washed down that night.

### 6.5 Peelings and scraps

Peel falls into the GN 1/3 waste tray under the peeler post; trimmings, cores, shells and used breading are
pushed or tipped into it. The tray is tipped into the sink, which is the waste port: outlet Ø 90, a rotating
drum strainer (2 mm) below it, back-flushed into a 12 L bio bin under the left zone; water goes to the drain.
The pre-spray of the wells drains through the same strainer. The route from the benches to the sink does not
cross the hob. No macerator. **Frying fat above 30 mL** (WSH-016) has no good path yet: it is poured from the
tilted thermoplate into the waste tray onto the peelings and crumbs; with no solids to take it up it would
run through the strainer into the drain (open issue 5).

### 6.6 Crevices, seals and spray shadows, named

1. **Tray and pot tangs have no drip collar.** A splash of mince or egg on a tray tang is carried by the
   chuck to the next item. The dam, the programming rule "no tool traffic over the tang side" and the jet
   gate reduce this; they do not remove it.
2. **Chuck**: two jaw rod seals, two pins, two sockets. The sockets are 8 mm deep holes on a Zone S part that
   touches every item; they are through-drilled so that the jet gate flushes them.
3. **Bought GN trays** usually have a rolled or folded flange edge, open underneath: a crevice 354 + 325 mm
   long on every tray. Flat-flange trays must be specified, or the roll welded shut.
4. **Dicing grids**: blade roots and crossings hold fibres (onion skin, sinew). Jets shoot against the
   cutting direction; the studded piston clears the cells before washing (R13); camera against a back light.
5. **Egg cracker**: two open hook hinges and a blade bar. It is the weakest cassette against HYG-013; the
   wash pose is fully opened, where the hooks fall apart. Dried egg white in a hook is the expected failure.
6. **Cut-off slide** runs in two open U-rails on the tube flange; mince and starch smear there.
7. **Roller**: pin in two open hooks; falls apart when lifted by the pin.
8. **Whisk**: wire roots in the hub; a welded, filled hub is required, not a bought crimped one.
9. **Silicone apron**: the hem bars are moulded in, no pocket; silicone takes up odour and colour (HYG-025).
10. **Perforated tray, basket, spin basket, ricer and Spätzle plates**: hole edges; several hundred holes each.
11. **Tongs**: inside of the U bend, radius 8 mm.
12. **Wells**: the comb rods touch each flange at two points; the items shadow each other if a slot is loaded
    with the wrong item, so the load pattern is enforced by software and checked by the camera; the lid
    underside drips rinse condensate on clean ware when it opens (clean water, but water).
13. **Bay**: edges of the three sealing bands; door seal; silicone joint round the hob glass; underside of the
    umbrella caps; pigeonhole rods; store rails; the dock cradle.

### 6.7 Verification

Per load: rinse temperature and time, pump pressure, detergent dose, turbidity and conductivity in the rinse
line (HYG-026 L1–L3). Per item: on lift-out the chuck turns the item once in front of a camera with white,
oblique and UV-A light in the rear wall above the wells (3 s, part of R) and compares it with the reference
image of that item; an infrared sensor confirms ≥ 65 °C, which stands in for "dry" on steel. A failed item is
rehung for the long programme, then quarantined in the last pigeonhole. Weekly: riboflavin mist on a clean
load and on the bay, rinse, UV check (SM-207). Tang grip zones of soiled trays are looked at by the bay camera
before the grip; a soiled tang forces the jet gate afterwards.

