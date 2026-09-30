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
and oven), about 92 loose items, 45–100 gripper cycles before a meal is served, and a washer that sits at the
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
FRONT VIEW (door removed)                                         outer width 2590, depth 600, height 2000
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
     X=0              300           680           1060              1600    1980                  2540

TOP VIEW at deck level (Z 850)                                   rear wall Y 555
     +----------------+-------------+--------------+--------+--------+-------+----------------------+
 555 | fine scale     |  spout  o   | press column | T3     | T4     | W2    |                      |
     | (300 g)        |  rear strip | (o) Ø40      | turning| turning| rear  |   oven, 550 deep     |
 435 |................|.............|..two bars....| Ø240   | Ø240   | well  |   (its 595 width     |
     | S0: GN 1/3     | B1: GN 2/3  | B2: GN 2/3   +--------+--------+-------+    lies along Y)     |
     | frame on       | frame over  | solid plate  | H1     | H2     | W1    |                      |
     | 10 kg cell     | sink        | under bars   | plain  | plain  | front |                      |
 110 |                | 354 x 325   | 354 x 325    | Ø240   | Ø240   | well  |                      |
   0 +---- door ------+-------------+--------------+--------+--------+-------+----------------------+
     0               300           680           1060    1330     1600    1980                   2540
```

Wall width by function: preparation proper (dock, two benches, wells) 1440 mm; four heated positions 540 mm;
oven and store tower 560 mm; casing 50 mm. **Total 2590 mm.** Without hob and oven the bay would be 1.5 m;
the brief for this round puts them inside, so 2.6 m is the honest figure. Reasons it cannot be shorter are in
section 7.2.

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
| 10 | About 45 items in two sets | 92 items, duplicates only where red and green overlap | Counted for six persons and four heated positions; E's count was too low |
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
* **Trays**: tang welded to the middle of one short side, in the plane of the flange, pointing outward.
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
| Hob | 2 × 2 induction positions under one glass-ceramic field 540 × 515: H1 3.5 kW and H2 2.2 kW (front, plain), T3 2.2 kW and T4 3.5 kW (rear, turning) [OEM modules, DEC-5] | ring drives T3, T4 (2), worm gear motor 0–120 rpm, 20 Nm at the pot | three roller posts per turning position through bosses with umbrella caps; each post set on a sub-frame with three load cells (10 kg, ±2 g) |
| Wells W1, W2 | Two wash wells 345 × 262 × 440 deep, front and back, sliding lids | lids (2) | lid runs in a channel outside the well coaming |
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
| GN 2/3 thermoplate -40 | multilayer, induction (Rieber class) | 2 | B+ | frying surface 1000 cm², pair for the flip |
| GN 2/3 thermoplate -65 | | 1 | B+ | braiser 5.5 L, hob and oven |
| GN 2/3 thermoplate -20 | | 1 | B+ | griddle, flip partner |
| GN 1/3-40 | 325 × 176 | 4 | B+ | breading, mise en place, weighing |
| GN 1/3-65 | | 2 | B+ | loaf tin, crumb bed, waste tray |
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

**Cassettes and inserts (29 parts)**

| Cassette | Parts | Driven by | Replaces |
|---|---|---|---|
| Press tube Ø 110 × 200 with flange | tube, plain piston, studded piston (R13), cut-off slide with blade, end plates: open mouth, grid 6, grid 10, ricer 3 mm, Spätzle 8 mm, corer-wedger (8 wedges), citrus cone — 11 parts | press; slide stroked by the chuck | slicer, dicer, fries cutter, ricer, juicer |
| Small tube Ø 45 × 160 | tube, piston, nozzle Ø 18, plate 2 mm — 4 parts | press | garlic press, paste syringe, filler |
| Peeler post | one-piece flexure with a bought Y-peeler blade and a stripping slot | — (stands in a tray) | lathe |
| Kneading set | roller arm, scraper arm | turning position | planetary mixer |
| Egg cracker | two half cups on open hook hinges, blade bar; slotted saucer | chuck squeeze | — |
| Rouladen set | silicone apron with two hem bars, trough insert, channel insert for the braiser (8 channels) | chuck | string |
| Boards | HDPE board GN 2/3 (red, green), silicone mat, gauge bars 3/5/8/22 mm, comb fence, steel sling strip for the loaf tin | — | — |

**Total: 92 loose items of about 58 types.** A reference meal uses 40–55 of them. The catalogue's "about 45
items in two sets" does not survive a count for six persons, four heated positions and the whole corpus.

**Where everything is parked.**

| Place | Capacity | Holds | Access |
|---|---|---|---|
| Tray store above the oven | 6 rail levels, nested pairs | all GN 2/3 trays and lids, GN 1/3 trays (two deep), boards and inserts lying in their trays | chuck horizontal, +X |
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
| Mince | Box inverted onto the red tray (pair grip with the box? no: the dock tips it); silicone spatula clears the box | residue ≤ 5 % | Medium |
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
| Carve a boneless roast (CAR) | Roast on the green board behind the comb fence, fork holds? no: the fence holds; slicing blade drawn along Y with 2 mm/stroke descent (SM-032) | set fence, 8–12 draw cuts at the fence pitch (10 mm), turner lifts the slices | 6 s per slice | Medium–high; medium for soft braised meat | Roast creeping along the fence; one hand only |
| Carve bone-in poultry (S) | — | — | — | **Not provided** | — |
| Unmould (UNM) | Tin and receiving tray or plate carrier rim to rim, pair inversion, tap, lift the tin; greased and floured tin, sling strip under the loaf | 20 s, 2 G | Medium | Sticking on bare steel; springform cakes stay on their base instead |
| Score (SCO) | Knife with depth from Z, force limit | 2–5 s per cut | High | — |
| Stuff rigid cavities (STU) | Small tube with nozzle on the press bars; the item stands in a tray below and is moved by tongs between strokes | 10 s per item | Medium–high | Cannelloni upright in a rack; pepper prepared by hand-like cuts (4.2) |
| Stuff flat pockets, dumpling cores, poultry cavity | Poultry cavity: nozzle; dumpling core: crouton pressed into a ring-cut disc before rounding; flat pockets: none | — | **Low; flat pockets not provided (S)** | — |
| Wrap (WRP): cabbage roll, wrap, bacon wrap | Apron and trough as for Rouladen | 45 s per pair | Medium | Leaf tearing; bacon singulation |
| Separate whole cabbage leaves (LSP) | Head blanched whole, outer leaves peeled with tongs | — | **Low**; counted as not preparable | — |
| Hand-form small pieces (FRM) | Strand from the small tube (Ø 18 nozzle), cut by the scraper every 25 mm onto a floured tray; balls: tray jiggled; Schupfnudeln: cylinders (adapted) | 4 s per piece | Medium | Gnocchi dough sticking at the nozzle |
| Form patties (FRB) | Mass spread in a GN 2/3-40 between two 22 mm gauge bars with the roller, ring cutter Ø 80 stamps, turner lifts, rest re-rolled once (SM-068); or 120 g plugs from the Ø 110 tube cut by the slide (SM-066) | tube route: load 1 kg, 8 strokes of 24 mm, 8 cuts: 60 s, 3 G | **12 patties in about 2.5 min** | High for the tube route (factory former), medium for mince smear on the slide | Piece mass ±5 % by stroke |
| Form dumplings (FRK) | Plugs Ø 45 from the small tube or Ø 80 ring cuts, rounded by jiggling on a wet tray | 5 s each | Medium | Roundness; holding together in simmering water |
| Roll Rouladen (RLT) | Apron in a GN 2/3-20 with a trough insert Ø 55 at the start line; two slices side by side; the filled leading edge sags into the trough; the chuck carries the near hem bar over the far one (SM-079/-080); the rolls drop off the apron end into the channel insert | lay 2 slices, spread, fill, roll: 110 s and 4 G per pair | Medium | Start of the first turn; filling squeezed out at the ends; slices torn at pick-up |
| Secure Rouladen | Seam-down channel insert in the braiser, seam seared first (SM-084); fallback steel pins set with the tongs and counted back (SM-085) | — | Medium; **unproven over a 100 min braise** (shared risk of all candidates) | Browning on three of four sides only |
| Bread (BRD) | Flour, egg and crumbs in three GN 1/3 trays on S0, B1, B2; red tongs carry the cutlet; crumbs pushed over with the presser and pressed at 30 N; two tongs (flour–egg, crumbs) against clubbing (SM-094) | 60 s per cutlet, 3 G per cutlet | Medium | Coverage ≥ 95 % at the tong marks; crumb waste about 30 % |
| Roll out dough (ROL) | Dough between two silicone mats? one mat and flour; roller between 3, 5 or 8 mm gauge bars in a GN 2/3-20; 6–8 passes, rest, 4 passes (SM-106) | 90 s, 2 G | Medium–high | Spring-back of yeast dough; sheet 330 × 300, not 400 × 300 |
| Shape dough (SHD) | Loaf: dough dumped in the greased GN 1/3-65; rolls: ring cuts, jiggled round; pizza: rolled in the baking tray itself | — | Medium | — |
| Line a tin with dough (LIN) | Sheet rolled on the mat, mat and sheet inverted onto the tin as a pair, mat peeled by one hem bar, presser tucks the corners | 60 s | Low–medium | Tearing at the corners |
| Knead (KND, KNM) | 6.5 L pot on T4 at 60–100 rpm against the roller and scraper arms; 1.6 kg of dough needs 14–20 Nm [R4] | load, 6–8 min, no manipulator | **1.6 kg dough, 1.2 kg mince: yes** | High (Ankarsrum) | 100 g of dough in the 1.5 L saucepan on its adapter |

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
| Flatten (POU) | Slice between the mat and the board under the presser? no: on B2 under the press arm with a GN 1/3 lid as platen at 1 kN | 10 s | Medium–high | — |
| Stir while cooking (STC) | Turning positions with the scraper arm (continuous); plain positions: paddle visits every 2–4 min | — | High / medium | Two continuous stirs at once is the limit |
| Baste, glaze, grease (BST, GLZ, LIN) | Ladle; silicone spatula as brush substitute | — | Medium | — |

