# P1 ideas, lens D — the dexterous manipulator, done smartly

Round P1 (idea finding) for meal preparation. Lens: start from a cook's two hands, a few utensils and a
board, and find the cheapest mechanical equivalent that can be hosed down.

Tags: [S] from the research files, [E] my engineering estimate, [U] unverified recollection.
`research/02-meal-corpus.md` did not exist when this was written; coverage is judged against
requirements section 5.3 (UO list) and the meals named in the brief.

## 0. What the lens says before any concept

### 0.1 Why the imitation-of-a-human arm fails, and what that tells us

A human hand-arm has about 27 degrees of freedom, skin that senses force everywhere, and is washed in a sink.
Moley copied the 27 DOF and got the cost; nobody copied the sink. Four observations steer everything below.

1. **A cook's hands do very few distinct things.** Watching prep work, almost every action is one of:
   hold a utensil and move it top-down (knife, masher, whisk, rolling pin, scraper); hold food down while the
   other hand cuts ("claw grip"); pick up and put down; tip something over; turn something over. Only the
   last two need a wrist rotation about a *horizontal* axis. Finger dexterity is used mainly for
   workholding and for peeling/rolling — and both can be moved into the utensil or the board.
2. **So the minimal hand is "2.5D + yaw", twice.** X, Y, Z and rotation about the vertical axis, with
   50–200 N downward, covers knife, press, mash, knead, roll, scrape, pick and place. One of the two hands
   additionally needs one horizontal roll axis (flip, pour, ladle). That is 9 axes, not 2 × 27.
3. **Dexterity can be bought with passive geometry.** A horizontal-blade knife replaces a wrist tilt. A
   comb that pins the onion replaces five fingers. A hook on the pot rim replaces a pouring wrist. Passive
   stainless utensils cost 5–50 EUR and go in the ware washer.
4. **The cleaning problem is a topology problem.** A joint inside the wet cell is a crevice with a seal, a
   cable and grease. The only seal shapes that are cheap and proven are a *circle around a rotating part* and
   a *ring around a sliding round rod*. A kinematic that needs only those two seal types, all in one wall,
   is washable. A kinematic that needs a sliding slot, a linear bellows over 1 m, or joints in the cell is
   not (or is expensive).

### 0.2 Load case used in all concepts

| Task | Force / torque at the utensil | Source |
|------|-------------------------------|--------|
| Knife through potato, carrot, onion (push cut, 15–25° edge) | 44–71 N peak; with draw cut about half | [S] R4 §1.1 |
| Guillotine through half a cabbage | 200–500 N | [S] R4 §1.2 |
| Flatten cutlet between plates | 0.5–1.5 kN (plates); by roller line contact about 150–300 N [E] | [S]/[E] |
| Mash cooked potato through 5 mm grid, Ø80 mm disc | 100–200 N [E] (about 30 kPa on 50 cm²) | [E] |
| Knead 1.5 kg yeast dough with a hook | 10–20 Nm at 60–100 rpm | [S] R4 §14 |
| Roll out dough with a pin | 100–200 N down | [E] |
| Pin through a Roulade | 5–20 N | [S] R4 §4.1 |
| Carry a loaded basket / ladle | 1–1.5 kg at 0.25 m, 5 Nm | [S] R4 §12.1 |
| Scrape, spread, press breading | 20–50 N | [S] |

Design target for a "hand": **200 N down, 100 N sideways, 15 Nm about the vertical axis, ±0.5 mm**.

### 0.3 Utensil canon (shared by concepts A, C, D; partly B, E)

All passive, one-piece 1.4404 or moulded PP/silicone, no hollow closed sections, 80–400 g, washed in the
ware washer on a rack that is itself a transport item. Handle: a female bayonet socket Ø30 × 35 mm deep,
open at the bottom edge with two drain slots so it cannot hold water in any orientation [E].

| # | Utensil | Does | Replaces which human ability |
|---|---------|------|------------------------------|
| U1 | Chef's blade, 200 mm, vertical | slice, dice, halve, top-and-tail, carve | knife hand |
| U2 | Horizontal blade on a Z-shaped shank (blade parallel to the board, 5–60 mm above it) | horizontal cuts in onion, split cutlet, halve bread roll | wrist tilt |
| U3 | Rolling disc blade Ø100 (pizza-wheel type), single and a 5-disc gang at 3 mm pitch | cuts with pure translation: herbs, dough, pastry, cooked meat portions | rocking chop |
| U4 | Fakir hand: comb (tines Ø1.5 × 40 mm at 5 mm pitch) and needle-bed variant (10 × 10 needles) | pins produce to the board; the blade passes between the tines | claw grip |
| U5 | Swivel peeler blade on a sprung parallelogram (2–6 N preload) | peel rotating or lying produce | peeling |
| U6 | Gouge (Ø10 mm sharp-rimmed cup) | eyes, stalks, cores | paring knife tip |
| U7 | Fork, 3 tines, and wide 4-tine "Schnitzel fork" | impale, carry, hold, dredge | fingers |
| U8 | Spatula/turner 110 mm and pancake turner Ø200 | lift, flip (with roll axis), spread | turner |
| U9 | Bench scraper 150 mm, silicone-edged | gather, fold dough, scrape board into pot, clean bowl wall | palm edge |
| U10 | Press plate Ø120 and grid masher Ø80 (5 mm holes) | press, flatten, mash, press breading | palm, fist |
| U11 | Dough hook, paddle, balloon whisk | knead, mix, whip (driven by yaw) | — |
| U12 | Rolling pin (free sleeve on a fork shank), 250 mm | roll out | both hands |
| U13 | Rounding cup Ø60 / Ø90 (open dome) | rounds balls by orbiting on the board | cupped palm |
| U14 | Ring cutters Ø70, Ø90 | cut pucks from a pressed slab | — |
| U15 | Scoops 15 / 60 / 250 mL, ladle 100 mL | dose granular and powder, ladle | cupped hand, spoon |
| U16 | Spice wand (grooved pin, 0.1 mL per dip) | seasoning 0.1–5 g | pinch |
| U17 | Air-displacement pipette barrel 60 mL / 300 mL (wetted part only the barrel) | dose liquids | measuring jug |
| U18 | Silicone vacuum cup Ø20 (egg) / Ø40 (slices) | pick eggs, meat slices, bacon, cheese | fingertips |
| U19 | Silicone brush, squeegee | scrub roots, wipe the ceiling and walls | — |
| U20 | Pin setter (holds a Ø2 × 80 mm stainless Rouladen pin at 25°) and C-ring setter | secure Rouladen | toothpick fingers |
| U21 | Rotary spray head on a lance | the hand hoses the cell | — |

21 types; a meal uses 4–8 of them. PRP-003 asks that each be justified; U2, U6, U13, U14, U20 are the
candidates to drop if the corpus shows low use.

---

## 1. Concept A — TWIN TURRET ("two rods through a disc-in-disc ceiling")

### 1.1 Core idea

The ceiling of a welded stainless prep cell contains two flush turrets. Each turret is a large disc with a
smaller disc set eccentrically into it; a plain stainless rod passes through the small disc. Turning the two
discs moves the rod anywhere inside a circle (it is a SCARA whose two links are flush plates in the roof);
the rod slides for Z and turns for yaw. **Nothing but two smooth rods hangs into the wet cell**, all four seal
lines are circles, and every motor, bearing, belt and cable sits in the dry room above. The rods pick up
passive utensils by push-and-twist (the bayonet uses the existing Z and yaw axes, so there is no gripper
and no tool-changer actuator).

### 1.2 Sketch

```
 SIDE VIEW (section through one turret)            cabinet top 2000
 ┌──────────────────────────────────────────────┐
 │  DRY DRIVE ROOM (Zone N)      Z screw, yaw   │  550 high
 │   ┌─motor─┐   ┌─motor─┐        motor, rod    │
 │   │ disc1 │   │ disc2 │          ║ upper end │
 │ ══╧═══════╧═══╧═══╦═══╧══════════║═══════════│ ← slewing rings (igus PRT type)
 ├───────────────────╫──────────────║───────────┤  ceiling 1450, heated, flush
 │ outer disc Ø470   ║ inner Ø240   ║ rod Ø40   │
 │ (seal S1)         ║ (seal S2)    ║ (seal S3 + lantern drain + ring nozzle)
 │                                  ║           │
 │   camera window (heated)         ║  Z stroke 400
 │                                  ╩ bayonet spigot
 │                              ┌───┴───┐ utensil
 │          box dock            │ knife │                  vessel dock
 │   ┌────┐           ┌─────────┴───────┴────┐            ╔══════╗ tip bar
 │   │box │           │ board Ø360, turns,   │            ║ pot  ║
 │   └─┬──┘           │ tilts 0–75°, on 3    │            ╚══╤═══╝
 │  load cell         │ load cells           │           load cell / hob
 ├─────────────────── floor sloped 3° to drain ────────────────┤  work level 900
 └──────────────────────────────────────────────┘

 TOP VIEW of the cell interior 1000 wide × 520 deep
 ┌──────────────────────────────────────────────────────────┐ back wall (utensil
 │  U  U  U  U  U  U  U   ← utensils held on the wall by magnets behind it   │
 │      ╭────────────╮            ╭────────────╮            │
 │ box  │  turret 1  │   board    │  turret 2  │  vessel    │
 │ dock │  "blade"   │   Ø360     │  "carry"   │  docks ×2  │
 │      │  reach Ø470│  (centre)  │  reach Ø470│            │
 │      ╰────────────╯            ╰────────────╯            │
 │  waste chute ○                          sink/drain ○     │
 └──────────────────────────────────────────────────────────┘ front door (glass, service)
   turret centres 480 apart; utensils are 100–200 mm long, so both hands
   reach the whole board even though the rods themselves meet only at its centre line
```

### 1.3 Kinematics and actuators

| Axis | Turret 1 "blade hand" | Turret 2 "carry hand" |
|------|----------------------|------------------------|
| Outer disc rotation | servo + belt on slewing ring | same |
| Inner disc rotation | same | same |
| Z (rod slide), 400 mm, 200 N | ball screw above the ceiling | same |
| Yaw (rod rotation), continuous, 15 Nm, 0–300 rpm | servo + 10:1 | same, 5 Nm |
| Roll (horizontal output at the rod end) | — | inner coaxial shaft, bevel in a welded elbow, one Ø20 shaft seal |
| **Total** | 4 | 5 |

Plus board turn (1) and board tilt (1), both driven from below the floor: **11 servo axes**, all
IP20 motors in dry rooms. No gripper actuator: large objects (pots, boxes, a cabbage, a roast) are pinched
*between the two rods* carrying paddles — the two hands together are a parallel gripper with 0–900 mm stroke
and 100 N.

Geometry: with eccentricities e1 = e2 = 117 mm the rod reaches every point of a Ø468 circle, including the
centre. Stiffness: the only cantilever is the rod; Ø40 × 3 mm tube at 450 mm extension deflects 0.13 mm under
50 N side load [E, calculated]. Disc torque for a 100 N side load: 12 Nm, trivial.

**The turret is also a planetary mixer.** Spin the inner disc continuously and the rod orbits; spin yaw and
the hook turns on its own axis. The orbit radius is set by the outer disc angle, 0–230 mm, so the same hand
kneads in a Ø160 bowl or a Ø300 bowl and scrapes the wall on the last turns. With a rounding cup on the
board, a 15 mm orbit is a baker's hand rounding a dough ball.

Force control without a force-torque sensor: the board and each dock sit on load cells **below** the floor
(posts through static diaphragm seals). They give weight to ±1 g and, from the three-cell distribution, the
magnitude and position of any press or cut force. The hand is position-controlled; the *board* feels.
Hardware about 60 EUR [E].

Perception: one fixed camera looks straight down through a heated window in each outer disc's fixed
surround, plus a line laser. Top-down 2.5D scenes on a known board are the easy case of food vision:
outline, height map, colour (peel left or not).

### 1.4 Vessels and holders

* Vessels are cylindrical stainless pots/bowls with a standard rim carrying a **pivot hook** on one side and
  a **bail pocket** on the other. Hung on a fixed *tip bar* at a dock, a rod lifting the bail pours to 120°
  with no tilt actuator (sub-idea N4).
* Shallow GN 1/6 trays for breading, marinating, mise en place.
* Lift-out perforated basket with bail for washing, draining, blanching.
* The board: Ø360 × 12 mm HDPE disc with a stainless core, located on three pins, removed by the two rods and
  sent to the ware washer after each meal; a second board (coloured, class R only) is kept in the clean store.

### 1.5 Dosing and moving each ingredient form

The box arrives through a hatch onto a weigh dock; the lid is lifted by a rod (bayonet knob on the lid).
All dosing is loss-in-weight at the box dock and gain-in-weight at the vessel dock, both logged (PRP-012).

| Form | Method | Accuracy / time [E] |
|------|--------|---------------------|
| Whole produce | camera picks a piece; fork U7 impales it (the hole does not matter, it is cut next), or two-rod pinch for cabbage | exact count; 5 s per piece |
| Leafy, bulky | two forks, one per rod, close on a bundle ("salad hands"); weigh; repeat | ±10 g; 8 s per grab |
| Granular | scoop U15 on the carry hand, dump by roll; last 5 % trickled by slow roll with 30 Hz yaw dither | ±2 g; 20–40 s |
| Powder | scoop as above for > 20 g; cohesive flour is cut out of the box with the scoop edge, no bridging problem because nothing has to flow | ±2.5 g |
| Seasoning | spice wand U16: dip through a wiper hole in the box lid insert, release over the pot by a 1500 rpm yaw spin | 0.1 g steps; 3 s per dip |
| Liquid | water, oil from fixed lines; everything else by pipette barrel U17 (air displacement from a dry-side pump through the hollow rod, the liquid never enters the rod) or tip-bar pour of the box for > 300 mL | ±2 % or ±2 mL |
| Paste | spoon on the carry hand, scraped clean into the pot by the bench scraper on the blade hand (two-handed, as a cook does); weigh | ±3 g |
| Solid fat | butter block on the board, blade cuts by length (250 g block = 2.5 g/mm) | ±3 g |
| Raw meat, wet pieces | Schnitzel fork slid under, or fork impale; slices by vacuum cup U18 | exact count |
| Egg | vacuum cup Ø20 on the blunt end | 4 s |
| Frozen loose | scoop; box returned to the freezer within 90 s | ±5 g |
| Long goods | two-rod pinch of a bundle (spaghetti), fork for leek/cucumber | ±10 g |

Transfer board → vessel: the board tilts to 75° over the vessel dock and the bench scraper sweeps it; the
recipe's water is then run over the board into the pot (residue goes into the food, R4 §10.2). Vessel →
vessel: tip bar plus scraper.

### 1.6 The hard operations

| Operation | How | Time [E] |
|-----------|-----|----------|
| **Peel potato** | Carry hand impales the potato on a fork on its *roll* axis (a horizontal spit), spins it at 120 rpm; blade hand holds the sprung peeler U5 and traverses 12 mm per turn. Camera then finds remaining brown patches (strong colour contrast), spit indexes, gouge U6 removes them. Peel drops straight into the waste chute under the spit. Loss 12–18 % | 25 s each, 1.5 kg in about 5 min |
| **Peel carrot, cucumber** | Lying in a V-groove of the board, held by the comb at one end; peeler strokes lengthwise, board-independent roll of the carrot by the comb (60° steps). Or scrub only (brush U19 under the mains jet) | 20 s |
| **Peel onion** | Spit pole to pole; blade tops and tails 8 mm; blade scores one meridian 2 mm deep (depth from first-contact force); onion turns slowly against a stiff silicone thumb held at the score while a 2 mm mains jet (20 m/s [S]) is aimed under the flap: the outer two layers unroll. Camera checks gloss and colour; on failure one more layer is taken (loss 10–20 %) | 20–30 s |
| **Dice onion** | Halve pole to pole on the spit, halves dropped cut-face down. Comb U4 pins a half. Horizontal blade U2 makes 2 cuts; vertical blade makes slices between the tines at 5 mm (or 2.5 mm with a half-pitch shift of the comb); board turns 90°, comb re-pinned, cross cuts. About 40 cuts at 0.5 s | 45 s per onion |
| **Mince herbs** | Bundle pinned by the comb, blade slices at 1.5 mm feed; then the 5-disc gang wheel U3 rolls over the pile at 60 N, 12 passes with 15° board turns | 40 s |
| **Crack egg** | Carry hand holds the egg by the cup over a fixed twin-blade anvil on the wall; lowering it 6 mm pierces the underside, a further 8 mm travel spreads the blades by a cam and the shell opens like a clam, still hanging from the cup by its upper side. Contents drop into a small cup (camera check for shell, yolk intact), shell is carried to the waste chute. Anvil is sprayed after each batch | 12 s per egg |
| **Form Frikadellen** | Mass kneaded by the planetary hook. Tipped onto the board, pressed to a 25 mm slab by the press plate inside a ring frame, pucks cut with ring cutter U14 and weighed on the board (100 g ± 8 g), trimmings re-pressed; edges rounded by the orbiting cup U13. For Klöße the cup rounds full spheres | 15 s per piece |
| **Rouladen** | Slice laid on a silicone mat on the board by vacuum cup; camera outline. Mustard by pipette barrel with a slot tip, spread by spatula. Bacon by vacuum cup, onion dice by scoop, gherkin spear by fork. Carry hand lifts the near edge of the mat by its bar and carries it over (sushi-mat roll) while the blade hand's press bar tucks. Securing: a saddle on the carry hand holds the roll; blade hand pushes a Ø2 × 80 mm stainless pin at 25° through flap and roll (10–20 N, guided by a slot in the saddle); or two snap C-rings are pushed on from above (N5) | 2.5 min each |
| **Bread Schnitzel** | Three GN 1/6 trays: flour 30 g, 1 egg whisked, crumbs 60 g. Schnitzel fork lays, flips (roll) and shakes the cutlet in flour; dips and drains 5 s over the egg; lays in crumbs, scoop covers, press plate presses with 20 N (board load cells), flip, repeat. Carried on the fork to the pan | 60 s each |
| **Knead and roll dough** | Hook, planetary, 1 kg in 6–8 min at 80 rpm. Rolled out directly on a silicone baking mat on the board: pin U12 at 100–200 N, passes with 30° board turns; thickness from the rod Z at contact and the laser line, to 3 mm ± 1. The mat goes onto the tray, so the sheet is never lifted | 3 min |
| **Mash potatoes** | Grid masher Ø80 driven to the pot floor at 150 N on a raster of 9 positions × 3 passes with yaw steps: every part passes the 5 mm grid at least once (deterministic, like a ricer, no gluey over-working). Milk and butter folded in by the paddle | 90 s |
| **Toss salad** | Two forks/spoons, one per hand, lift from the bottom and turn over, 8 cycles in a wide bowl; dressing by pipette | 30 s |
| **Flip steak / pancake** | Spatula on the roll axis slides under against a fork held by the blade hand as a backstop, lifts 120 mm, rolls 180°. Pancake Ø240: Ø200 turner, or two-pan clamshell (N13) | 5 s |
| **Drain pasta** | Pasta is cooked in the lift-out basket; carry hand hooks the bail, lifts (1.5 kg), holds 20 s over the pot, tips the basket into the sauce pan on the tip bar | 40 s |

### 1.7 Cleaning and drying

| What gets dirty | How it is cleaned | Where the water goes | Shadows / crevices |
|-----------------|-------------------|----------------------|--------------------|
| Utensils, board, vessels, trays, mat | Ware washer (R6 backbone), on racks that are transport items. Utensil sockets point down on rack pegs with a jet up each socket | washer sump | socket has two drain slots; no closed hollows |
| Rods | Each rod retracts through a **collar** in the inner disc: ring nozzle (hot water from the cell sump), then a scraper ring, then a drained lantern chamber, then the dry seal. The lower 450 mm passes the collar at every wash; the bayonet spigot is a plain cone with two pins | back into the cell | the rod is a smooth cylinder |
| Roll elbow on rod 2 | Smooth welded elbow, one Ø20 lip seal facing down, purged with dry air from inside (a leak blows outwards); seal is an LRU | cell | one small rotary seal is the only dynamic seal on a product-side surface |
| Ceiling discs and seams S1, S2 | The carry hand takes the spray lance U21 (hot water through the hollow rod bore) and hoses the ceiling, walls, docks and the other rod by a fixed coverage path; then the hands swap. Seam gaps are downward-facing labyrinths with a PTFE lip, kept at +50 Pa dry air so steam does not enter. Each hand then wipes the other's ceiling half with the squeegee | floor, 3° to a central drain with sieve, to the sump | the nozzle goes to the surface, not the other way round, so there is no fixed shadow; coverage is proven once with riboflavin and thereafter by logged path and flow |
| Walls, floor, docks | Same lance, plus 4 fixed floor-rim nozzles; hot rinse 70 °C; utensils are not on the wall during this (they are in the washer) | drain | coved corners R10, no ledges; dock posts are smooth cones |
| Hollow rod bore | Flushed top-down with hot water and blown out after every use as a vacuum or pipette line (straight Ø8 bore, no dead leg) | cell | straight, CIP at > 1.5 m/s |
| Drying | 70 °C rinse flash-dries the steel; ceiling trace heater (about 150 W [E]) keeps it 5 K above cell air, also during cooking, so condensate does not form above food; 15 min fan purge | — | — |

Cell Zone F + S area about 3.4 m² [E] (1000 × 520 × 550 box). Wash-down 25–40 L recirculated from a 10 L
sump [S, R6 scaling].

### 1.8 Off-the-shelf, custom, novel

* Off-the-shelf: slewing rings (igus PRT polymer slewing rings, Ø up to about 300 mm inner, 100–400 EUR
  [U]), closed-loop steppers or small servos, ball screws, load cells, PTFE lip seals, camera, induction
  module, all utensil blades (adapted from commercial knives, peelers, whisks).
* Custom: four laser-cut and turned 1.4404 discs, the rod assemblies, the elbow, bayonet sockets, board,
  tip-bar vessels. Drive-room brackets can be printed (Zone N).
* Parts cost for the two turrets about 6–8 kEUR [E].
* **Novel:** disc-in-disc flush ceiling SCARA; turret as variable-orbit planetary mixer; bayonet pick-up
  using Z and yaw only; the board as the force sensor; two rods as the gripper; the hand as the cell's spray
  lance.

### 1.9 Biggest weaknesses

* Two Ø470 rotating seams in a ceiling above open food. They can be flushed and purged, but this is the
  part a hygiene auditor will look at first; seal wear debris must fall nowhere (lip above a drip edge that
  leads to the gutter, not to the board).
* A wet rod sliding up into the dry room. The collar and lantern are standard practice for hygienic rod
  actuators [S, R6 §6.2], but it is a wear part.
* Software: about 30 utensil skills, each with vision and force thresholds. The scenes are top-down and the
  motions 4-DOF, which is far easier than 6-DOF manipulation, but onion skin removal, Rouladen rolling and
  pancake flipping will each need weeks of tuning and will not reach 98 % first-time success without
  retry logic.
* Slow: everything is serial. 1 kg of vegetables in 6 min (PRP-023) is met only with two hands working in
  parallel and about 0.5 s per cut.

---

## 2. Concept B — WALL PUCK ("the manipulator goes in the dishwasher")

### 2.1 Core idea

The cell has no penetrations at all. Its back wall is one flat 1.5 mm non-magnetic stainless sheet; behind
it, in the dry, an ordinary H-bot plotter carries a magnet head. Inside the cell a passive stainless
"puck" clings to the wall opposite the head and follows it; a second, rotating magnet ring in the head
turns a spindle in the puck through the wall. The puck is a dumb object with no wire and no seal to the
outside: after the meal it lets go, is carried off with the utensils, and is washed in the ware washer.

### 2.2 Sketch

```
 SIDE VIEW                                  FRONT VIEW of the wall (1000 × 700)
 dry room │wall│ wet cell 300 deep          ┌───────────────────────────────────────┐
          │1.5 │                            │ box dock ▽ chute                       │
  H-bot   │    │                            │    ╲                                   │
  XZ ─┐   │    │  puck Ø130                 │     ╲   ◎ puck 1 (knife, swings)       │
  ┌───┴─┐ │    │ ┌────┐ spindle Ø25         │  ┌───────────────┐                     │
  │magnet├┤    ├─┤    ├────●━━━━ utensil    │  │ board shelf    │  ◎ puck 2 (fork,   │
  │array │ │    │ │    │   (swings in the   │  │ turntable Ø300 │     spit, turner)  │
  │+ring │ │    │ └────┘    plane ∥ wall)   │  └──────┬────────┘                     │
  └──────┘ │    │  ▲ 3 PEEK rollers         │         ▽ tilts                        │
   rollers │    │                           │      ╔═══════╗   ╔═══════╗             │
   press on│    │  board shelf 300 deep     │      ║ pot 1 ║   ║ pot 2 ║  hob        │
   the wall│    │ ┌──────────┐              │      ╚═══════╝   ╚═══════╝             │
   (sheet is    │ │ turntable│              └───────────────────────────────────────┘
   clamped      │ └──────────┘               gravity cascade: box → board → pot
   between)     │    pots below
```

### 2.3 Kinematics and actuators

Per puck: X, Z (H-bot, 2 motors behind the wall), spindle rotation about the wall normal (1 motor turning an
8-pole magnet ring Ø90), optionally a second coaxial ring driving a screw for a jaw: **3–4 motors per puck,
two pucks, 6–8 in total**, plus the board turntable, itself magnet-driven through the floor (1) and its tilt
(1). All motors are IP20 behind a continuous sheet.

Forces [E]: six N52 magnet pairs across a 3.5 mm total gap give about 400 N normal force. With fine-pitch
alternating poles (10 mm) the lateral restoring force peaks near 0.4 × normal, about 150 N, with a stiffness
of roughly 60–80 N/mm, so a 60 N cut sags the puck under 1 mm. The puck rides on three PEEK rollers, the dry
carrier on three rollers directly opposite, so the sheet is only squeezed, not bent. Tilting moment: a
60 N load 150 mm out from the wall is 9 Nm; the 400 N preload on a 100 mm roller base resists 20 Nm. Spindle
torque through the wall about 4–8 Nm for an Ø90 face coupling: enough to swing a 150 mm knife with 30–50 N
at its middle, to turn a whisk, flip a turner, tip a ladle, or spin a potato. **Not enough for kneading or
200 N pressing**; those are done by a vessel with a magnet-driven base tool (Thermomix-type station).

The spindle points out from the wall, so its rotation is the *horizontal* wrist axis a vertical-rod
manipulator lacks. A knife on it chops like a paper cutter (pivot cut, which needs about half the force of a
push cut); a fork on it is a spit; a turner on it flips; a scoop on it dumps. What is missing is motion
towards the front (Y): the work is a slice of space 60–250 mm from the wall. The turntable brings every
point of the board under that slice.

### 2.4 Vessels, tools

Pucks come in three kinds (spindle puck ×2, jaw puck ×1); utensils clip to the spindle by bayonet using X/Z
and spindle rotation. Vessels as in concept A, on a shelf row under the board; the board shelf tilts to pour
into them. Utensils and idle pucks park on the wall, held by fixed magnets behind it.

### 2.5 Ingredient forms

Boxes dock at the top and are tipped by a puck hooking the box's tip-bar bail. Granular and powder: scoop
on the spindle, dumped by spindle rotation, weighed at the vessel dock. Liquids: fixed lines, or a ladle.
Pieces: fork impale (spindle turns the fork to strip it against a fixed comb). Leafy: two pucks with forks
close on a bundle. Meat slices: wide fork. Eggs: cup-shaped cradle on the spindle carries the egg to the
wall anvil (A's method with the cradle instead of a vacuum cup). Frozen: scoop. Paste: spoon plus scraper on
the second puck.

### 2.6 Hard operations

| Operation | How in B | Verdict |
|-----------|----------|---------|
| Peel potato/carrot | Puck 2's spindle is the spit; puck 1 drags the sprung peeler along. Natural fit | good |
| Peel onion | As A (score, thumb, jet) | fair |
| Dice onion | Pivot-cut knife on puck 1, comb on puck 2, turntable for the cross cuts. Horizontal cuts by a blade mounted parallel to the board | good, ±1 mm |
| Mince herbs | Pivot chop at 3 Hz while the turntable creeps | good |
| Crack egg | Cradle plus wall anvil | fair |
| Frikadellen | Mass mixed in a magnet-driven bowl; slab pressed by a roller on the spindle (line contact 50 N), cut with a ring, rounded against the board by an orbiting cup (X/Z circle does not orbit in the board plane: use the turntable plus an X oscillation) | fair |
| Rouladen | Mat roll by puck 2 lifting the mat bar in an arc (the X/Z plane is exactly the rolling plane if the slice lies with its long axis along the wall); pin pushed along X by puck 1 | good geometry, weak force margin |
| Bread Schnitzel | Trays on the shelf row; fork on spindle flips naturally | good |
| Knead / roll dough | Kneading in a driven bowl. Rolling: pin on puck, 60 N only, many passes; 3 mm pizza base achievable for soft yeast dough, not for stiff shortcrust | weak |
| Mash | 60 N on an Ø50 masher, many strokes; or blade in the driven bowl | weak |
| Toss salad | Two forks; or the lidded bowl is turned on the spindle | good |
| Flip steak/pancake | Turner on the spindle | very good |
| Drain pasta | Basket 1.5 kg at 150 mm from the wall is 2.2 Nm and 15 N: fine | good |

### 2.7 Cleaning

* Pucks, utensils, board: ware washer. The puck is a welded shell around potted magnets, rollers on plain
  PEEK bushes open on both sides, spindle on a dry-running iglidur A-grade bush [S] with open ends: no
  lubricant, all gaps ≥ 2 mm and flushable, no closed cavity.
* Cell: five flat sheets, coved, with **nothing** on them: no rod, rail, arm, cable or seal. Fixed rotating
  nozzle in the ceiling plus floor-rim nozzles reach everything in line of sight; this is the rare case
  where a wash-down cell has high coverage confidence. 2.0 m² [E]. Water to a floor drain and sump.
* Drying: hot rinse, fan, and a squeegee utensil dragged over the wall by a puck before it leaves.

### 2.8 Off-the-shelf, custom, novel

Off-the-shelf: H-bot (3D-printer mechanics), magnets, PEEK, bushes. Custom: pucks, magnet head. Parts
about 2–3 kEUR [E] — the cheapest concept. **Novel:** zero-penetration cell; a manipulator that is itself
ware; through-wall magnetic wrist.

### 2.9 Weaknesses

* Force ceiling of 60–100 N and 4–8 Nm; heavy work must go to driven vessels, which brings back a base-drive
  station.
* A decoupled puck falls, possibly into food. It must be designed as a safe fuse (tether hook on a rail at
  the wall top, or acceptance that the batch is discarded).
* Anything trapped between roller and wall (a salt grain, a bone chip) scratches the wall; NdFeB collects
  ferrous swarf and must stay below 80 °C, so the hob needs distance or SmCo magnets.
* No Y axis: it is a 2.5D kitchen and some reach problems will only show in a mock-up.
* Perception is the same as A but from the front at a grazing angle, which is worse; a ceiling camera helps.

---

## 3. Concept C — ROLLO ("the board is a conveyor, the knife is a gate")

### 3.1 Core idea

Give the dexterity to the work surface. The board is a 320 mm wide cantilevered homogeneous-TPU belt; above
it stands a gate of two vertical rods carrying a crossbar that accepts a guillotine blade, a slitter bar, a
sheeting roller, a press plate or a doctor bar. Belt feed plus gate stroke slices, dices, sheets dough,
flattens meat, rolls Rouladen against a stop, runs a Schnitzel through a breading pass, carries product
off its front nose into a pot and waste off its rear nose into the bin — and the belt washes itself by
running past a spray bar and scraper. One simple turret hand (concept A, turret 1 only) does the picking,
placing and pinning.

### 3.2 Sketch

```
 SIDE VIEW (looking from the front; belt runs left ↔ right)
                 ceiling ─────────────╥───────╥────────╥──────────────
                                 gate rod  gate rod   turret rod
                                      ║  (behind)     ║ (disc-in-disc, 4 axes)
                                 ┌────╨───────┐       ║
        box dock                 │ crossbar   │       ╩ utensil
        ┌─────┐                  │ + cassette │
        │ box │  hold roller ○   └─────▼──────┘ blade
        └──┬──┘            ▼           │
   rear    │      ╭────────────────────┴──────────────────╮   front nose Ø20
   nose ◄──┴──────┤  TPU belt 320 × 560, platen on 3 load │──► overhang cut:
   (waste)        ╰───────────────○────────────○──────────╯    slice falls into
      │             spray bar ↑ scraper ↑  drive Ø50 (shaft          the pot
      ▼                                   through back wall)      ╔══════╗
   waste chute                                                    ║ pot  ║
                                                                  ╚══════╝
 Cell 1000 × 520 × 550; belt frame is fixed to the back wall only (open front, no legs).
```

### 3.3 Kinematics and actuators

Belt (1, positive-drive, ±0.5 mm); gate left and right rod Z, independent (2; 300 N each, so 600 N and a
tilting blade for a rocking cut); turret hand X-Y by two discs, Z, yaw (4); belt tension release (1).
**8 axes.** The gate rods only slide: two ring seals. The turret hand changes the gate's cassette, so the
gate needs no changer either.

### 3.4 Tool and vessel set

Gate cassettes: G1 guillotine blade 300 mm; G2 slitter bar with free-running disc blades at 10 mm pitch
(second bar at 5 mm); G3 sheeting roller Ø60; G4 press plate; G5 doctor bar; G6 flour/crumb sifter trough.
Hand utensils: fork, vacuum cup, comb, scoops, spice wand, pipette, scraper, pin setter, brush, spray lance
(about 10 of the canon). Vessels as in A, docked under the front nose on a weigh dock.

### 3.5 Ingredient forms

Whole produce and pieces: tipped or placed on the belt by the hand; the belt is the singulator (run,
stop, camera). Leafy: forked on; spread by the doctor bar. Granular, powder, seasoning, liquids, paste: by
the hand exactly as in A (scoops, wand, pipette) directly into the vessel; they do not touch the belt.
Meat slices: vacuum cup onto the belt. Eggs: by cup to a wall anvil. Frozen loose: scoop. Long goods: laid
along the belt, cut to length by the guillotine, carried off the nose.

### 3.6 Hard operations

| Operation | How in C |
|-----------|----------|
| Slice anything (1–20 mm) | **Overhang cut**: the belt advances the item one slice thickness past the front nose, the hold roller presses it 30 mm upstream, the guillotine passes 0.5 mm in front of the nose bar. The slice drops straight into the pot. No board contact, no transfer step, thickness set by the belt encoder. 2 cuts/s |
| Dice (potato, carrot, pepper) | Slices are cut onto the belt instead (belt reverses after each cut so they land flat), levelled to one layer by the doctor bar, run under the slitter bar (strips), then overhang-cut crosswise at the same pitch (dice). Pieces are within pitch in two directions and slice thickness in the third. 1 kg in about 3 min [E] |
| Dice onion finely | Halves face down; horizontal cuts are not needed when the onion is sliced to 3 mm half-rings and then crosscut through the slitter at 5 mm and guillotined at 3 mm: pieces < 3 × 5 mm; layers separate by themselves |
| Mince herbs | Bundle under the hold roller, overhang cut at 1.5 mm feed, then one pass under the 5 mm slitter |
| Peel potato/carrot | Not the belt's strength. Hand holds the sprung peeler; the potato is rolled by the belt against a fixed fence bar (belt moves under it, fence holds it in place, so it spins about its long axis) while the peeler traverses. Carrots likewise. About 30 s per potato, coverage 85–90 %, camera-guided touch-up with the gouge [E] |
| Peel onion | Top-and-tail by guillotine; score by the hand; rolled by the belt against a silicone-finger fence with a mains water fan jet: the rubbing strips the scored skin (this is how small industrial onion peelers work without air). Skins leave over the rear nose |
| Crack egg | Hand + wall anvil as in A |
| Frikadellen | Mass (mixed in a driven bowl or by the hand's hook) is dropped on the belt, sheeted to 25 mm by G3 in two passes, guillotined into 60 × 60 mm blocks by weight from the platen load cells (belt feed adjusted so each block is 100 g ± 5 g), corners rounded by the hand's cup |
| Rouladen | Slice on the belt; the hand spreads mustard and places filling. The doctor bar is lowered to 3 mm above the belt in front of the slice and the belt is run *towards* it: the leading edge climbs the bar's curved face, folds back and the slice rolls up on itself (bakery curling principle). Hold roller presses the finished roll, hand pushes the pin or snaps C-rings. 60 s per Roulade |
| Flatten cutlet | Between two sheets of the silicone mat, three passes under G3 with the gap stepped 12 → 8 → 5 mm; line force about 200 N |
| Bread Schnitzel | One pass each: under the sifter trough G6 with flour (belt carries surplus to the rear nose and waste), hand dips the cutlet in the egg tray, belt pass under G6 with crumbs onto a crumb bed, press plate G4 at 20 N, hand flips it, second pass |
| Knead / roll dough | Kneading by the hand's hook in a bowl (planetary). Rolling out is the belt's best trick: a reversing sheeter. 8–10 passes under G3 with the gap stepping 20 → 3 mm, the hand turning the sheet 90° halfway; ±0.5 mm. The sheet leaves over the nose directly onto the baking tray |
| Mash | Hand with grid masher in the pot, as A |
| Toss salad | Leaves fall off the nose into a wide bowl; tossing by a lidded-bowl tumble station or by the hand's fork with a scraper, slower than A (one hand) |
| Flip steak / pancake | **Weak point.** One vertical rod has no roll axis. Steak: fork lifts one edge over a fixed bar on the pan rim and lets it fall over. Pancake: two-pan clamshell (N13). Or add the roll elbow of A's turret 2 (+1 axis) |
| Drain pasta | Basket lifted by the hand |

### 3.7 Cleaning

* Belt: homogeneous extruded TPU, no fabric, no hinge, welded endless, positive-drive teeth on the inside
  (Volta-type hygienic belt [U]). After the meal it runs 10 revolutions past a spray bar (hot detergent
  water from the cell sump) and a scraper on the return side; then the tension roller retracts 30 mm, the
  belt hangs slack and lances above and inside spray the platen, rollers and the belt's inner face while
  it is inched round. The frame is cantilevered from the back wall so the belt has an open side: no spray
  shadow behind a leg, and the belt can be slid off by service without tools.
* Raw meat on the belt: a silicone mat (ware) is laid under class R food wherever possible; when not, the
  belt wash runs with a 75 °C sanitising pass before RTE food (HYG-030 allows this between uses). TPU
  tolerates 80–90 °C [U].
* Gate rods: collars as in A. Gate cassettes and hand utensils: ware washer. Drive shaft: one hygienic lip
  seal through the back wall, shaft horizontal, seal above floor level.
* Cell: fixed nozzles plus the hand's lance. About 3.6 m² [E] including belt (0.45 m² both faces).
* Drying: hot rinse, belt run against an air knife fed by a side-channel blower, fan purge. TPU stays wet
  longer than steel; 20 min [E].

### 3.8 Off-the-shelf, custom, novel

Off-the-shelf: belt material and sprockets, drum motor or external gearmotor, blades (deli and pizza-wheel
blades), sifter mesh. Custom: cantilever frame, gate, cassettes. Parts about 5–7 kEUR [E]. **Novel:**
overhang cut into the pot; one belt as slicer, dicer, sheeter, flattener, Roulade curler, breading line,
transfer and waste conveyor; belt platen as force sensor; self-washing work surface.

### 3.9 Weaknesses

* A belt is the classic hygiene trouble spot: inner face, rollers, edges. Homogeneous belts and tension
  release are the industry answer, but this needs a real riboflavin test.
* Cutting on TPU (slitter discs roll on it) wears it; the overhang cut avoids most knife contact, the
  slitter does not. Belt is a yearly service part [E].
* Only one dexterous hand: flipping, tossing and two-handed jobs are clumsy.
* Disordered pieces after slicing mean dice are "statistical" (±20 % allowed by PRP-021, probably met, to
  be tested).
* Software is easier than A for cutting (open-loop feeds) but the Roulade curl and onion rub are
  process-tuning problems with a wide range of raw material.

---

## 4. Concept D — SOCK ARM ("a cheap cobot in an inflated, leak-tested sleeve")

### 4.1 Core idea

Take the full dexterity argument seriously: buy a 4.6 kEUR six-axis collaborative arm with built-in
force-torque sensing, hang it from the cell ceiling, and put all of it inside one seamless silicone sleeve
that is clamped to a ceiling flange at the top and to a stainless wrist cap at the bottom. The sleeve is
kept at +5 mbar with dry air: folds are blown smooth so they can be sprayed, a leak blows outwards, and the
pressure-decay rate is a continuous integrity test. The wet cell then contains one smooth object with no
seam, which is as cleanable as a rubber glove.

### 4.2 Sketch

```
 FRONT VIEW, cell 900 wide × 520 deep × 650 high
 ─────────────── ceiling flange Ø160, clamp ring, dry-air feed ───────────────
                        ╔═╗
                        ║ ║ base (in the dry room or just below the ceiling)
                       ╭╨─╨╮
                      ╱ sleeve ╲         fixed nozzles ◦  ◦  ◦  (arm does a
                     ╱  J2      ╲                                "shower dance")
                    ╱  ╱ ╲       │
                   │  ╱   ╲ J3   │    FR3-class arm: 622 mm reach, 3 kg payload
                   ╰─╱─────╲─────╯
                    ╱       ╲
                  wrist cap (stainless, bayonet spigot, magnet-coupled jaw drive)
                    │
                 utensil ────► lever knife hooked in the board's fulcrum eye
   ┌──────────────────────────────┐            ╔══════╗
   │ board 400 × 300 on a trunnion│            ║ pot  ║  box dock on the left
   │ tilts to pour, flips 180° to │            ╚══════╝
   │ a spray bar under it         │
   └──────────────────────────────┘
```

### 4.3 Kinematics and actuators

Six arm joints plus one jaw drive through the wrist cap (a small magnetic coupling across a stainless
membrane, 20 N grip), plus board trunnion (1): **8 axes**, of which 6 come in a bought, tested unit with
controller, collision detection and a software stack. Payload 3 kg means about 30 N continuous at the
tool, so the knife force is obtained by leverage, not by the arm: the blade tip hooks into a fulcrum eye at
the back edge of the board and the arm presses the handle (lever 3:1; 30 N at the handle gives about 90 N
at mid-blade, N9). Pressing above 100 N (flattening, mashing a full pot) goes to a fixed press beam or to
driven vessels.

### 4.4 Tools, vessels

The full utensil canon; tilt and roll come from the arm, so U2 and the tip-bar vessels are not needed —
ordinary pots with a handle block. The board is a "third hand": it has a V-groove, a fulcrum eye, a
spike row and an ice-chuck patch (N1).

### 4.5 Ingredient forms

As in A, but simpler because the arm can pour: boxes and vessels up to 2.5 kg gross are tipped in the hand
(heavier ones on a tip dock); scoops and ladles are emptied by wrist roll; liquids are poured from the box
against the vessel's load cell. Pieces, leaves, meat and eggs with a two-finger jaw carrying silicone
fin-ray fingers (ware, swapped per food class) or the vacuum cup.

### 4.6 Hard operations

The arm does what concept A does with the same utensils, with these differences:

* Peel potato: potato on a fixed spit station on the wall (1 motor through the wall) or held on the board's
  spikes and peeled in strips with the peeler following the surface under force control — the one place
  where 6 DOF plus F/T is really better: the blade stays normal to an irregular surface and eyes are gouged
  at any angle.
* Dice onion: lever knife plus comb held by a board-mounted swing clamp (one hand only, so the second hand
  is a fixture).
* Crack egg: the human way — tap on a fixed edge with 0.1 J, then the jaw's two fingers plus a fixed
  thumb hook pull it apart; about 90 % clean [E], camera and strainer spoon for shell.
* Frikadellen: scoop with a sweeper, round in the cup; arm force is ample.
* Rouladen: single-handed mat roll with the far edge of the mat clipped to the board; pin setter at any
  angle.
* Knead: 15 Nm is beyond the wrist; use a driven bowl. Roll out: pin at 30 N, many passes; soft doughs only,
  or a fixed press beam.
* Flip, pour, toss, ladle, baste, plate: natural, and the same arm can plate nicely (SRV), which no other
  concept here offers.

### 4.7 Cleaning

* The sleeve is the only Zone S/F surface of the manipulator: 0.8 mm platinum-cured silicone, about 0.5 m².
  Wash: fixed nozzles plus the "shower dance" — a programmed sequence of poses that opens each joint's folds
  towards a nozzle, at +15 mbar so the folds are taut. 70 °C rinse. Drying by the same dance in the fan
  stream. The wrist cap is a smooth cone with static seals only.
* Arm heat (50–100 W) is removed by the purge air, exhausted to the dry room.
* Integrity: pressure decay test before every meal (10 s). A pinhole is detected before water gets in, and
  until then the leak blows out. Sleeve is an LRU, changed from above with the arm, yearly [E].
* Board: flips face-down over a spray bar after every ingredient change (10 s rinse) and goes to the ware
  washer after the meal. Cell: as A, 3.2 m² [E].

### 4.8 Off-the-shelf, custom, novel

Off-the-shelf: arm (Fairino FR3 4.6 kEUR, or xArm 6 5.3 kEUR [S, R8]), its controller and motion planning;
robot jackets exist as a product class [S, R6]. Custom: sleeve with ceiling and wrist clamps, wrist cap,
board. About 7–9 kEUR [E]. **Novel:** ceiling-sealed, inflated, continuously leak-tested sleeve; shower
dance; lever knife to let a 3 kg arm cut carrots.

### 4.9 Weaknesses

* Sleeve fatigue at the joints (elbow folds see 10⁵–10⁶ flex cycles per year) and knife nicks. One cut in
  the sleeve stops the kitchen until service.
* R8's verdict stands: a 622 mm arm sweeps more than the 520 mm depth allows, so the usable workspace is a
  lens shape and the door must be interlocked.
* Arm above open food: whatever drips from the sleeve drips into the pot, so the sleeve is Zone F.
* Hardest software of all five: 6-DOF planning in a cramped cell with a sleeve that snags, one hand only,
  deformable food. It is also the most *extensible*: a new skill is a software update.
* Low force: three operations need extra fixed mechanisms anyway.

---

## 5. Concept E — SPIT AND STATIONS ("hold the food, not the tool")

### 5.1 Core idea

Invert the cook: the manipulator grips the *food* on a standard two-prong spit and presents it to simple
tools. The heart is a kitchen lathe — a spindle through the left wall, a tail rod through the right wall, and
one tool rod parallel to them that slides and swings. Round produce is peeled, scrubbed, scored, sliced,
diced, grated, zested and cored between centres with four motors and four circular seals; eggs are opened by
scoring the equator; Rouladen are wound on a slotted mandrel. A single ceiling rod (concept A, one turret)
loads the lathe and does the flat work on a small press table.

### 5.2 Sketch

```
 FRONT VIEW, cell 1000 × 520 × 550
 ───────────────────────────── ceiling ──────╥──────────────────────────
                                         turret rod (load, flat work)
   left wall                                 ║                    right wall
   ║                 tool rod Ø30 (slides 320, swings ±60°)            ║
   ║  ════════════════╤══════╤══════╤═════════════════════════════════╬══ motor
   ║               peeler  knife  comb-scorer   (tools on short arms   ║  (X + swing)
   ║                  ▼      ▼      ▼            around the rod)       ║
 ══╬══[spindle]══▶▶ (  potato / onion / apple )  ◀══ tail cup ═════════╬══ tail rod
 motor  fork Ø25      capacity Ø220 × 300                              ║  (push 20–150 N)
   ║                         │ slices, dice, peel fall                 ║
   ║        diverter flap ───┴──► pot (product)   or ──► waste chute   ║
   ║   ┌───────────────┐                  ╔══════╗                     ║
   ║   │ press table   │                  ║ pot  ║ on weigh dock       ║
   ║   │ 300 × 250     │                  ╚══════╝                     ║
   ╚═══╧═══════════════╧══════════ floor 3° ═══════════════════════════╝
```

### 5.3 Kinematics and actuators

Spindle (0–600 rpm, 10 Nm), tail rod push (1), tool rod slide (1) and swing (1, 15 Nm, so 125 N at a
120 mm arm, torque-controlled — the swing motor current *is* the force sensor), diverter flap (1), turret
hand (4), press table beam (1, 1 kN): **10 axes**. Seals: one rotary (spindle), two rod seals in the right
wall, turret seals as in A.

### 5.4 Tools

On the tool rod, fixed on arms at different angles so the swing selects the tool: T1 sprung peeler;
T2 parting knife (thin, 120 mm); T3 scoring comb (6 blades at 8 mm pitch, plus a 4 mm one); T4 brush;
T5 grater plate (coarse/fine faces); T6 gouge/corer point. The tool rod with its arms slides out through a
wash port as one piece of ware, or is cleaned in place (5.7). Spindle noses (ware): two-prong fork, slotted
mandrel, vacuum cup, reamer. Hand utensils: about 10 of the canon.

### 5.5 Ingredient forms

Round and long produce: hand impales it on the fork or sets it between fork and tail cup. Everything else
(granular, powder, liquid, paste, leaves, meat, frozen) is dosed by the hand as in A; the lathe does not
touch it.

### 5.6 Hard operations

| Operation | How in E |
|-----------|----------|
| Wash roots | Spin at 200 rpm against brush T4 under a mains fan jet; 6 s |
| **Peel potato, apple, kohlrabi, celeriac, cucumber** | The lathe's home game: 120 rpm, peeler feed 12 mm/rev, blade follows the contour on its spring. 6–8 s per potato plus 8 s loading; 1.5 kg in about 3.5 min. Eyes in hollows: camera, spindle indexes, gouge T6. The two pole caps under fork and cup (each Ø25) are parted off as waste or gouged; loss 15–20 % |
| Peel carrot | Between centres with the tool rod's brush arm as a steady rest opposite the peeler; slender carrots (< Ø20) are only scrubbed |
| **Peel onion** | Fork pole to pole; parting knife tops and tails; comb scores the two outer layers along the axis at 2 mm depth (swing torque limit); spin to 600 rpm with a fan jet: centrifugal force (Ø70 at 600 rpm is about 14 g at the skin) and the jet throw the scored skin segments off. Camera check |
| **Dice onion, potato, apple** | Meridian scoring with the comb to the core while the spindle indexes (every 8–10°, or parallel chordal cuts with the spindle stopped at 0° and 90° for square sections), then the parting knife slices at the dice pitch with the spindle turning slowly: each slice falls apart into dice into the pot. Onion 3 mm dice: 4 mm comb, 3 mm parting feed, 25 s. The Ø25 stub on the fork is pushed off as an offcut |
| Slice | Parting knife, any thickness, slices drop via the diverter into the pot. Spiral cuts and ribbons for free |
| Grate, zest | Spinning potato, carrot, cheese block or lemon pressed at 20–50 N against T5; zest depth limited by torque. Juice: halved citrus against a reamer on the spindle |
| Core | T6 driven in along the axis from the tail end (tail cup swapped for a hollow cup) |
| Mince herbs | Not lathe work: hand with the gang wheel on the press table |
| **Crack egg** | Egg held between two Ø20 vacuum cups on spindle and tail rod (vacuum through both hollow shafts). Turn at 60 rpm, a carbide scribe on the tool rod scores the equator through the 0.35 mm shell at 3 N; the tail rod retracts 30 mm: two clean half-shells, contents drop intact. No impact, so very few fragments; separation of yolk by a slotted cup below. 10 s per egg |
| Frikadellen | Hand: planetary hook, then slab and ring cutter on the press table (beam presses the slab with a plate) |
| **Rouladen** | Filled slice lies on a mat on the press table with one short edge overhanging towards the lathe. The slotted mandrel (Ø12, slot 3 × 120 mm) is advanced over that edge, the spindle turns 2.5 turns at 20 rpm while the hand's press bar keeps tension: a tight, even roll. Pin pushed through axially-offset by the tail rod's pin nose, or C-rings by the hand; then the tail cup strips the Roulade off the mandrel onto a fork. 40 s each |
| Flatten, bread | Press table: beam with plate, 1 kN; breading trays with the hand's fork (no roll axis: the cutlet is turned by the fork against a tray edge) |
| Knead, roll dough | Hand hook (planetary); rolling with the pin on the press table, or the beam presses a pizza base to thickness in one stroke between two mats |
| Mash | Hand with grid masher |
| Toss salad | **Lathe trick:** a lidded salad drum is chucked between spindle and tail cup and turned at 20 rpm — tumble toss, also for marinating and for flouring goulash meat |
| Flip | The pan is not reachable by the lathe; hand with clamshell pan (N13) or edge-over-bar flip. Same weakness as C |
| Drain pasta | Basket by the hand. The spun salad drum with a perforated shell is also the salad spinner (600 rpm) |

### 5.7 Cleaning

* Spindle nose, tail nose: short, smooth, swappable ware; shafts behind them have hygienic lip seals with
  a drip edge, flushed by a ring nozzle in the wall at each wash.
* Tool rod: withdrawn fully through its collar into a closed tube on the dry side that is itself a small CIP
  chamber (ring nozzles, hot water, air), so the blades are washed and dried where they park, away from
  the cell — or pulled out as ware by the hand. Blade edges are open, arms are solid bar.
* Hand: as A. Press table top and mats: ware. Cell: fixed nozzles and the hand's lance; about 3.5 m² [E].
  The lathe zone throws peel and juice radially, so a removable splash hood (ware) surrounds it and takes
  most of the soil to the washer.

### 5.8 Off-the-shelf, custom, novel

Off-the-shelf: gearmotors, seals, peeler and grater blades, vacuum cups. Custom: everything on the lathe
axis, small and simple turned parts. About 5–6 kEUR [E] with the single turret. **Novel:** kitchen lathe
with torque-controlled swing tools; score-then-part dicing; centrifugal onion skinning; equator-scored
egg opening; mandrel-wound Rouladen; chucked tumble drum as salad tosser and spinner.

### 5.9 Weaknesses

* Only bodies of revolution (roughly) are covered by the star mechanism. Leaves, meat, mushrooms, peppers,
  tomatoes and herbs all fall back on one simple hand, which is then the bottleneck.
* Fork stubs and pole caps cost 5–10 % extra waste; small items (garlic cloves, shallots, radishes) are too
  small to chuck: bought peeled, or crushed.
* Irregular potatoes leave peel in hollows; without the camera-gouge step PRP-022 (≤ 5 % residual peel) is
  not met.
* Loading on centres needs the hand to find the long axis of a lumpy object: simple vision, but a 5–10 %
  retry rate is likely [E].

---

## 6. Comparison at a glance

| | A Twin turret | B Wall puck | C Rollo | D Sock arm | E Spit & stations |
|---|---|---|---|---|---|
| Servo axes | 11 | 8–10 | 8 | 8 (6 bought) | 10 |
| Tool force | 200 N, 15 Nm | 60–100 N, 4–8 Nm | 600 N gate, 200 N hand | 30 N (90 N by lever) | 125 N tool, 1 kN table |
| Dynamic seals at the cell | 6 (4 large circles, 2 rods) + 1 elbow | **0** | 5 | **0** (one static sleeve) | 6 |
| Objects left in the wet cell | 2 smooth rods | nothing | belt, gate, 1 rod | 1 sleeved arm | 3 rods |
| Two-handed work | yes | yes | no | no (fixtures) | partly |
| Peeling | good | good | fair | good | **best** |
| Dicing speed | medium | medium | **best** | slow | good |
| Flat work (meat, dough) | good | weak | **best** | fair | fair |
| Flip / pour / plate | good (roll axis) | very good | weak | **best** | weak |
| Software difficulty | medium | medium | low–medium | high | medium |
| Parts cost [E] | 6–8 kEUR | 2–3 kEUR | 5–7 kEUR | 7–9 kEUR | 5–6 kEUR |
| Main risk | ceiling seams | force limit, puck drop | belt hygiene | sleeve life | narrow scope of the lathe |

---

## 7. Standalone sub-mechanism ideas

**N1 — Ice chuck (freeze workholding).** A Ø120 patch of the board is a thin stainless plate over a Peltier
stack whose hot side is cooled by mains water. A wet cut face placed on it at −15 °C freezes on in 5–10 s.
Ice adhesion of 0.1–0.5 MPa [U] on a 20 cm² onion half gives 200–1000 N of holding force on a perfectly
flat, crevice-free surface; a reversed-current pulse releases it in 2 s. Freezing 0.5 mm of tissue costs
about 0.3 kJ and is invisible in cooked food. Also firms raw meat locally for clean slicing. Feasibility:
medium-high; open points are frost in a humid cell and RTE produce whose cut face must not be frozen
(tomato for salad).

**N2 — Fakir hand.** A comb or needle bed pressed into the produce from above replaces the cook's claw
grip; the blade runs in the lanes between the tines, so holding and cutting do not compete for space and
the blade position is mechanically referenced to the holder. 100 needles at 2–4 N each need at most 300 N.
Stripping by lifting against the flat of the blade. Dishwasher: needles are open pins 5 mm apart.
Feasibility: high (the comb exists as a consumer onion holder).

**N3 — The board feels.** Three load cells under the board (outside the cell, through diaphragm-sealed
posts) give ingredient weight to ±1 g, press force, blade touchdown, "cut-through" (force collapses) and the
position of the force. The manipulator can then be a plain position-controlled axis set. 60 EUR.
Feasibility: high; needs taring against cell air pressure and wash water.

**N4 — Tip-bar pour.** Every vessel and box has a small hook lip on one rim side and a bail pocket on the
other. Hung on a fixed bar, anything that can lift the bail vertically pours it to 120° about the bar, with
the lip 20 mm from the target. Removes the tilt actuator and the pouring wrist. Feasibility: high.

**N5 — Snap C-ring for Rouladen.** A 12 mm wide spring-steel (1.4310) band bent to an open ring Ø38 with a
25 mm mouth and flared lips. Pushed onto the roll from above with 15–25 N it snaps closed around it; two per
Roulade. No piercing, no aiming of a pin, reusable, dishwasher-safe, removed at plating by a hook. Seared
surface under the band stays pale (12 mm stripes). Feasibility: high.

**N6 — Equator-scored egg opening.** Two vacuum cups hold the egg at its poles, it turns once against a
scribe, the cups pull apart. Replaces the impact (which makes fragments) by a controlled crack path, and the
shell halves stay on the cups for disposal. Also works as a hand-held utensil pair in the two-rod concept.
Feasibility: medium-high; shell thickness varies 0.3–0.45 mm, so scribe force control is needed.

**N7 — Hollow rod as service line.** A straight Ø8 bore through the manipulator rod carries vacuum (cups,
pipette), mains water (spray lance, rinsing a pot the hand is scraping) and air (blow-off), switched on the
dry side. It is CIP-flushed top-down after every use; straight, no dead leg. One feature removes the
gripper actuator, the pipette mechanism and half the fixed spray nozzles. Feasibility: high.

**N8 — Rod car-wash collar.** At the penetration: ring nozzle, scraper ring, drained lantern chamber, dry
seal, dry-air purge. Every retraction washes and wipes the rod; a leak shows as water at the lantern drain
sensor long before it reaches the drive room. Feasibility: high (standard hygienic rod-seal practice made
active).

**N9 — Lever knife.** The blade tip carries a hook that drops into a fulcrum eye at the board edge; the
manipulator presses the handle. 3:1 leverage at mid-blade lets a 3 kg-payload arm or a magnet puck cut
carrots and swede, and the pivot fixes the cut line mechanically. Feasibility: high; the eye is an open
slot, washable.

**N10 — Rolling-disc knife.** A free-running Ø100 disc cuts by translation only, with no draw stroke and no
tip to steer; a gang of five minces herbs. Ideal for a Cartesian hand. Needs a board or belt it may touch.
Feasibility: high.

**N11 — Spice wand.** A pin with a ring groove of 0.1 mL is pushed through a silicone wiper hole in the
spice box's lid insert into the powder and pulled back: the wiper strikes it off level. Over the pot a
1500 rpm spin throws the dose out. Dose = number of dips, 0.05–0.1 g resolution depending on bulk density
(calibrated per spice on the weigh dock). The box never travels over the steaming pot, which avoids the
caking that kills shaker dosers [S, R4 §9.3]. Feasibility: medium-high; damp or oily spices (paprika paste,
ground cloves) may pack in the groove.

**N12 — Magnet-parked utensils.** Utensil handles contain a ferritic (1.4016) slug; permanent magnets behind
the flat cell wall hold them. The wet side has no peg, hook or rack: the wall and the hanging utensil are
both fully exposed to spray, and a utensil can be parked anywhere. Feasibility: high.

**N13 — Clamshell pan flip.** Two identical pans with the tip-bar rim: the second is set upside down on the
first, the pair is rotated 180° about the bar, the top one lifted off. Flips pancakes, omelettes, Rösti,
fish fillets and a whole pan of Frikadellen with ≥ 95 % intact and no spatula skill. Costs a second pan in
the wash. Feasibility: high.

**N14 — Rinse the board with the recipe's water.** The measured cooking water is delivered as a sheet over
the tilted board into the pot (a flume), so cut pieces, starch and juice are transferred with 0 % residue
and the board arrives at the washer pre-rinsed. For dry-pan recipes use the oil or skip. Feasibility: high.

**N15 — Score before boiling, shrug after.** Potatoes are scored once around the equator (lathe or knife),
boiled in their skins, shocked in cold water 10 s; two silicone cups then pull the skin off each half in one
motion. Moves potato peeling to a state where it needs 5 N and no contour following, and saves 10 % of the
potato. Works for waxy boiling potatoes and tomatoes; not for raw-potato dishes. Feasibility: medium-high.

**N16 — Laser-line portion knife.** A line laser in the blade plane and the top camera measure the
cross-section profile of meat, a mince slab or a dough strand as it is fed; the feed per cut is computed so
each piece has the target mass (as industrial portion cutters do). Frikadellen, goulash cubes, Schnitzel
from a loin, rolls, all ±5 % without weighing each piece. Feasibility: high on a belt or turntable.

**N17 — Planetary by kinematics.** Any manipulator that can make the tool orbit while the yaw axis spins is
a planetary mixer with programmable orbit radius and an integrated wall scraper pass. No separate mixer
drive, no bowl-bottom shaft seal (HYG-016). Needs 15 Nm on yaw. Feasibility: high in concept A, not in B/D.

**N18 — Levitating vessel carriers (wild).** Replace docks and part of the transport by planar-motor tiles
(Beckhoff XPlanar class [U]: passive magnetic movers float over flat stainless-covered tiles, about 4 kg
payload, can tilt a few degrees, rotate and wobble). The vessel floats to the hand, shakes itself to mix,
weighs by levitation current. Floor is a flat sheet, movers are ware. Feasibility: technically proven,
economically poor (about 3–4 kEUR per 240 mm tile [U]); keep for a later generation.

**N19 — Cold finger pick-up (wild).** A stainless pad chilled to −10 °C picks wet, floppy, slippery things
(raw fish, liver, a sheet of bacon, a lettuce leaf) by freezing a contact film in about 1 s and releases with
a warm pulse; no squeezing, no suction marks, no clogging. Cryo-grippers are used industrially for fish
and textiles [U]. Needs coolant lines in the hand; pairs with N7's hollow rod only if a second bore exists.
Feasibility: medium.

**N20 — Sacrificial interleaf (pragmatic).** A roll of baking paper in a dry cassette feeds a sheet onto
the board for class R work (Rouladen, breading, mince). The paper is the sushi mat, the breading tray liner
and the baking-tray liner, and leaves with the waste. Removes the worst soils from the wash entirely.
A consumable the human refills twice a year; to be checked against GEN-003/HUM list. Feasibility: high.

---

## 8. Which concept I would bet on

**Concept A, Twin Turret**, with three transplants: the ice chuck and fakir hand (N1, N2) on its board, the
clamshell pan (N13), and — if walk-throughs show that dicing time or dough and meat sheeting are the
bottleneck — concept C's gate over a short belt section in place of the turntable board in round 2.

Reasons:

1. **It is the only concept with two real hands**, and the hard operations named in the brief (Rouladen,
   breading, flipping, tossing, scooping paste, peeling on a hand-held spit) are all hold-and-act jobs. C, D
   and E each stumble on exactly those and patch them with fixtures.
2. **Force and stiffness are free.** 200 N and 15 Nm from a rod in a bushing cost nothing; B and D are
   force-limited and need extra stations that eat the saving.
3. **The cleaning topology is honest.** Only circles and rods cross the wall; the cell contains two smooth
   cylinders; the hand itself carries the nozzle to every surface, which answers R6's main objection to
   wash-down cells (unpredictable spray shadows). The residual risk is concentrated in one place, the
   ceiling seams, where it can be tested early on a single-turret mock-up.
4. **Software is 2.5D.** Top-down camera, vertical tools, force from the board. That is a tractable
   perception and control problem for a small team; D's is not.
5. **Standard parts.** Slewing rings, steppers, ball screws, load cells; the custom parts are flat discs and
   round rods that any sheet-metal and turning shop makes.

B deserves a P3 exploration anyway because a zero-penetration cell whose manipulator is ware is the most
radical answer to "clean everything", and because it is cheap enough to build as an experiment. E's lathe
is the best peeling and egg answer found here and could be grafted onto A as one spindle through the side
wall if A's hand-held spit proves too weak.

---

## 9. Open issues

1. No meal corpus yet: utensil count and the value of U2, U6, U13, U14, U20 cannot be weighed against
   frequencies.
2. Ceiling seam design of concept A (lip material, purge flow, drip edge, how it is proven with
   riboflavin) is the first thing to detail and test.
3. Magnetic shear stiffness and torque through a 1.5 mm wall (concept B) are estimates; a bench test with
   off-the-shelf magnets costs a day.
4. Ice adhesion on stainless for real produce (N1) and frost management are unmeasured.
5. Onion skin removal has three proposed methods (thumb and jet, belt rub, centrifugal); none is proven at
   ≥ 95 %. The fallback is losing one fleshy layer, or buying peeled.
6. Whether the prep cell and the cooking positions share one wash-down cell (as assumed for stirring and
   flipping by the same hands) is an architecture decision; it puts grease and steam on the manipulator.
7. Cycle-time totals for a reference meal have not been summed; serial hand work may exceed PERF targets
   for 6 persons.
8. Class R / RTE separation is by time and ware change (second board, second utensil set) in all concepts;
   whether a rod or sleeve needs a sanitising pass between raw meat and salad within one meal must be set.
9. N20 (paper interleaf) and N15 (peel after boiling) change recipes or add a consumable; customer view
   needed.

## 10. Risks

| Risk | Concepts | Consequence | Mitigation |
|------|----------|-------------|------------|
| Large rotary ceiling seals leak or shed wear debris | A, C, E | hygiene audit fails; drive room gets wet | purge air, lantern drains with sensors, seals as LRU, single-turret test rig early |
| Skill software takes far longer than the mechanics | all, worst D | coverage on paper, not in practice | 2.5D top-down kinematics, passive utensils that make the motion simple, deterministic processes (C, E) for the high-volume operations |
| Force estimates for cutting are from slow universal-tester data | all | knife stalls or food squashes | 200 N margin in A/C/E; lever knife in B/D; keep blades sharp (PRP-034: blades are ware and can be exchanged at service) |
| Passive utensil drops off the bayonet | A, C, E | utensil in the food, jam | bayonet with over-centre pin seat, pick-up confirmed by weight on the rod's Z motor current and by camera |
| Puck decouples | B | puck falls into the pot | tether rail, force budget with factor 2, SmCo near heat |
| Belt cannot be validated clean | C | concept falls back to a plain board | silicone mat under class R food; belt removable as ware in one piece if made as a short cassette |
| Sleeve puncture | D | downtime until service | pressure-decay monitoring, knife paths kept away from the sleeve by software limits, spare sleeve |
| Serial manipulation too slow for 6 persons | A, D | PERF-001 missed | two hands in parallel, prep started earlier by the scheduler, gate-and-belt cutting from C |
| Vision fails on wet, glossy, steaming scenes | all | retries, waste | heated windows, polarised lighting, scenes on a known board colour, weight as the second sensor |
