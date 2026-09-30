# K1 — Ceiling turret cell

Round P3 exploration of candidate K1 of [02-concept-catalogue.md](../02-concept-catalogue.md), following
[03-exploration-brief.md](../03-exploration-brief.md). Sources: `ideas/A-machine-tool.md` (concept A2,
sub-mechanisms M1–M17) and `ideas/D-manipulator.md` (concept A, N1–N20), with mechanisms borrowed from the
other lenses by their SM numbers.

**Status of all statements.** Nothing here was built or tested. Tags: [S] taken from a research file or
requirement, [E] my engineering estimate or calculation, [U] unverified recollection of a catalogue value.
Coordinates: x along the wall from the left inner wall, y from the back inner wall towards the front,
z from the room floor. Dimensions in mm.

Contents: 1 definition · 2 mechanism · 3 intake and dosing · 4 operation table · 5 benchmark walk-throughs ·
6 cleaning · 7 numbers · 8 coverage · 9 failure modes · 10 risks · 11 improvements and changes ·
12 open issues and requests to the architect.

---

## 1. Definition

K1 is one welded stainless wash-down cell, 1650 wide × 550 deep × 550 high inside, whose flat ceiling
carries three identical **turrets**. A turret is a disc (Ø 500) with a second disc (Ø 270) set eccentrically
into it and a plain round rod (Ø 45) through the second disc. Two disc rotations place the rod in X-Y, the
rod slides for Z and turns for yaw; a thin second shaft inside the rod (the *core*) and a fluid bore make
every tool passive. Apart from the three rods and one fixed press ram, nothing hangs into the cell: no
gripper, no tool changer, no cable, no guide. All motors, bearings and valves sit in a dry room above the
ceiling.

Food never touches a fixed surface. It lies on a board disc, in vessels, trays and cups, or on tools — all
of them loose stainless or moulded parts ("ware") that leave the cell to be washed. The fixed cell is
splash zone only and is hosed down by the hands themselves with a jet lance on a programmed path.

The deck carries, from left to right: the box dock at the hand-over port; one turntable pedestal that
carries the board, a mixing bowl or a spin basket; a flat bench for trays; and a block of four induction
positions. A bought compact combi-steam oven stands at the right end, turned by 90° so that its mouth
opens into the cell.

```
 FRONT VIEW (front door removed). z in mm from the room floor, x in mm from the left inner wall.

 z=2000 ┌──────────────────────────────────────────────────────────────────┬──────────────────────┐
        │ DRIVE ROOM, dry (Zone N): ring drives, Z towers, ram, valves,    │ oven vapour          │
        │ filtered-air plenum. Turret cassettes slide out to the front.    │ condenser, fan       │
        │     ┃Z1          ┃ram R        ┃Z2                  ┃Z3          │                      │
 z=1400 ╞══[═════T1═════]══╪══════[═════T2═════]════════[═════T3═════]═════╡ z=1330 ┌──────────┐  │
        │       ║          ║             ║                     ║           │        │  combi   │  │
        │       ║rod Ø45   ╨ die        ╔╩╗ roll head          ║           │        │  steam   │  │
        │       ║        ▭▭▭ cassette   ╚═╧══ turner           ╩ whisk     │  rack  │  oven    │  │
        │ port  ▼        on 2 pegs                                       ◄─┼─ pulls │  45 L    │  │
        │┌────┐      ┌──board──┐                        ┌─────┐  ┌─────┐   │   out  │          │  │
        ││box │ cup  │ BT Ø400 │    bench 350 × 550     │ pot │  │ pan │   │        └──────────┘  │
 z=850  ╞╧════╧══════╧═══╤═════╧════════════════════════╧═════╧══╧═════╧═══╡ z=870                │
        │ chip box · sump 10 L · pumps · boiler 6 L · BT drive and load    │ oven electrics,      │
        │ cells · 4 induction modules · extraction fan, condenser · control│ service space        │
 z=0    └──────────────────────────────────────────────────────────────────┴──────────────────────┘
        x=0        275    550          825        1100        1375       1650               2220
        │◄── zone 1 ──►│◄────── zone 2 ──────►│◄────── zone 3 ─────►│◄──── oven niche 570 ────►│
        module outer width: 25 + 1650 + 25 + 570 = 2270 (cell alone: 1700)


 TOP VIEW of the deck (cell interior 1650 × 550). ( ) = limit of rod-axis reach, Ø 400 per turret.

 y=0   back wall ───── rear gutter 60 wide, falls to the chip drain at x=550 ────────────────────── 
       ┌─────────────────────────────────────────────────────────────────────────────────────────┐
       │   rail A ▪▪▪▪▪   G1      ◎ram      rail B ▪▪▪▪▪   G2        extraction slot (hob)       │
       │       .-"""""-.      ⊓pegs⊓          .-"""""-.                .-"""""-.                 │ ┌──
       │┌────┐(         )  .-------.         (         )           (  ◯H2   ◯H4  )               │ │
       ││dock│(   T1    ) /  BT     \        (   T2    )           (  Ø220  Ø220 )               │ │oven
 y=275 ││ D  │(  +275   )(   +550    )  bench(  +825   )           (     T3      )               │ │mouth
       ││    │(         ) \  Ø400   /  350×550(        )           (  ◯H1   ◯H3  )  ◄─ rack ─────│ │400
       │└────┘ `-.....-'   `-------'          `-.....-'            (  Ø280  Ø280 )               │ │×250
       │  ▫W ▫C1                                                     `-.....-'                   │ └──
       └─────────────────────────────────────────────────────────────────────────────────────────┘
 y=550 front: two-leaf glass door, interlocked, heated inner pane
       x=0    200  350      550      750     925      1100   1240      1510      1650

 D dock shelf 200 × 250 on load cells (boxes arrive through the port in the left wall)
 W seasoning weigh cup (300 g cell) · C1 cup position on a 3 kg cell
 BT board turntable, pedestal Ø 400, top at deck + 150, on three 10 kg cells
 rail A, rail B tool rails (5 tools each) hung on wall pegs · G1, G2 jet gates (fixed fan nozzles)
 ram R at (550, 110), fixed · pegs below it carry die cassettes
 H1…H4 induction positions at (1240 | 1510, 410 | 140): H1, H3 3.5 kW; H2, H4 2.0 kW
```

| Key figure | Value |
|---|---|
| Wall width | 1700 for the cell, 2270 including the oven niche [E] |
| Hands | 3 turrets × 5 axes (two discs, Z, yaw, core) |
| Other servo axes | press ram 1, board turntable 1 |
| Force per hand | 300 N down, 150 N sideways, 20 Nm yaw, 0.65 Nm / 6000 rpm core [E] |
| Press | 3 kN, 250 stroke, fixed position |
| Ceiling seams | 2.42 m per turret, 7.3 m in total; three rod collars, one ram collar |
| Rod-axis reach | Ø 400 per turret (see 2.2 — not Ø 470 as in the source documents) |
| Tool-point reach with the roll head | Ø 780 per turret (overlapping) |

---

## 2. Mechanism

### 2.1 Answers to the catalogue's six questions, in short

| # | Question | Answer | Where |
|---|---|---|---|
| 1 | One stiff 3 kN quill, or light hands plus a press? | Three light hands (300 N) and one fixed 3 kN ram between two turrets. Only dicing, forming and ricing need more than 300 N, and none of them needs X-Y travel under load. A 3 kN load 200 mm off-centre would put 600 Nm through both ceiling seams exactly while food is open below. | 2.3, 2.5 |
| 2 | Ceiling seam design and fallback | No contact seal faces the food. Each seam is an open, downward-draining annular gap behind a 45 mm coaming, swept by filtered air in operation and flushed from the top during the wash; the elastomer seal sits outside the coaming on the dry side. Fallback: there is none inside the concept. A gantry above a fixed ceiling needs slots, which the concept forbids; if the seams fail the riboflavin test, the hands have to be replaced by a gantry gripping above drip collars (K6), and K1 survives only as its tool and fixture set. | 2.4 |
| 3 | Turrets, width, hobs inside or outside | Three turrets, 1650 inside. The hobs are inside the cell under turret 3, because the rods are the only handling. Two turrets are possible (1100 inside) at a clear loss of time. | 2.2, 7 |
| 4 | Tool logistics | Prep tools on two removable rails (the rail with its tools is one item of ware); cooking tools ride with their vessel on a rim rest; between two foods a tool is spun in a fixed jet gate (8–10 s). No holsters. | 2.8 |
| 5 | Side-wall lathe spindle? | No. The roll head gives every hand a horizontal spindle; it peels potatoes, apples and kohlrabi as a hand-held spit. A lathe would save one hand during peeling and add a tailstock for slender carrots, at the price of two more wall penetrations. | 4 |
| 6 | Utensil count | 26 rod tools, 8 stub tools, the roll head, 11 fixtures: 46 types. | 2.7 |

### 2.2 Turret geometry — a correction to both source documents

Both inventors drew a rod that reaches almost the full disc diameter (D:A: discs Ø 470 / Ø 240, eccentricities
117 + 117, "reach Ø 468"; A:A2: Ø 500 / Ø 250, 120 + 120, "reach Ø 480"). That geometry does not close: with
e2 = 117 the Ø 40 rod would lie 17 mm outside a disc of radius 120.

The rod hole must lie inside the inner disc, and the inner disc inside the outer one:

```
 e2 ≤ R2 − c      c = rod radius + weld land round the rod hole        = 22.5 + 12.5 = 35
 e1 ≤ R1 − R2 − m  m = rim of inner disc + its coaming in the outer disc = 15
 rod-axis reach radius = e1 + e2 ≤ R1 − c − m            (independent of R2)
 the centre is reached only if e1 = e2
```

With the largest outer disc that fits a 550 deep cell (R1 = 250, coaming outer Ø 530):
**R2 = 135, e1 = e2 = 100, reach radius 200.** The rod axis covers a circle of Ø 400 in a zone of 550 × 550,
i.e. 42 % of the deck, and the circles of neighbouring turrets stay 150 mm apart. They can never overlap,
whatever the disc sizes, because a turret cannot reach beyond its own outer disc.

Consequences, which shaped the rest of the design:

1. Two rods cannot pinch a pot between them and carry it (D:A's "two rods as a parallel gripper", SM-235):
   both would have to leave their circles. Vessels are carried by one hand.
2. Everything that must be picked with the vertical bayonet (tools, pressing, spinning) has to stand inside a
   circle. Everything that must pass from one zone to the next needs an offset.
3. The offset is supplied by the **roll head** (2.6): a passive wrist whose horizontal output lies 190 mm
   from the rod axis. With it the tool point reaches Ø 780 per turret, so neighbouring hands overlap by
   230 mm and the whole deck is covered. Every item that is carried between zones therefore has a horizontal
   **stub** for the roll head (2.7).
4. The turntable BT stands on the boundary between zones 1 and 2, so that either hand reaches the half of
   the board facing it and a half turn passes an item from one hand to the other.

| Turret | Centre (x, y) | Role | Rod-axis reach |
|---|---|---|---|
| T1 | (275, 275) | cold preparation: dock, dosing, knife work on the left half of the board, spit | x 75–475 |
| T2 | (825, 275) | bench: flat work, breading, rolling, assembly; second hand at the board; helper at the left hob column | x 625–1025 |
| T3 | (1375, 275) | cook hand: all four hob positions, oven rack | x 1175–1575 |

### 2.3 Axes and actuators

Per turret (three identical cassettes):

| Axis | Drive | Data [E] |
|---|---|---|
| D1 outer disc | ring Ø 560 on four V-rollers, HTD-5 belt round the ring, closed-loop stepper 3 Nm, ratio 18.7 | ±190°, 60 Nm, 60°/s; rod position ±0.3 mm |
| D2 inner disc | ring Ø 320 on three V-rollers, belt, stepper 2 Nm, ratio 10.7 | ±190°, 45 Nm (150 N at the roll-head tool point) |
| Z rod slide | ball screw 16 × 5 beside the tower, servo 200 W with holding brake | stroke 380, 300 N continuous, 250 mm/s |
| C yaw (rod tube) | servo 400 W, belt, two ranges by a second pulley pair | 20 Nm at 0–150 rpm; 2 Nm to 1200 rpm |
| K core shaft | servo 400 W, belt 1 : 2 up | 0.65 Nm, 0–6000 rpm; position-controlled |

The discs never turn continuously. Every cable and hose to the inner disc and the Z carriage runs in a loop
with ±190° of travel; there is no slip ring and no rotary water joint except the small one on top of the
core shaft. D:A's "turret as planetary mixer" (inner disc spinning) is therefore dropped: the bowl turns on
BT instead and the hook stands 60–75 mm off the bowl axis (SM-171/-172).

Other axes:

| Axis | Drive | Data [E] |
|---|---|---|
| R press ram | electric cylinder through the fixed ceiling at (550, 110), rod Ø 40 | 3 kN, stroke 250, 40 mm/s; force from motor current |
| BT turntable | direct-drive gear motor under the deck, hollow shaft on a raised boss | 20 Nm at 0–60 rpm; 3 Nm to 800 rpm; index ±0.2° |

**Total: 17 servo axes** in the concept proper. Shared or neighbouring equipment that the concept uses but
does not own: dock tilter and vibrator (2, the common dosing front end), oven door drive (1, unless the oven
is bought with one). Valves: water, air and vacuum to each rod bore (9), two jet gates, seam-flush diverter
(7 ways), lance feed, drain-wand pump, mains inlet.

Stiffness [E, calculated]. Rod tube Ø 45 × 4, 1.4404, I = 1.09 × 10⁵ mm⁴: 150 N sideways at 450 mm extension
bends it 0.21 mm; bushing clearance adds about 0.1 mm. A 4 kg vessel on the roll head (190 mm offset) puts
7.5 Nm on the bayonet and 12 N on each ring roller pair. The ring on four rollers at Ø 560 takes the 68 Nm
tilting moment of the worst side load with 120 N per roller. The ceiling sheet carries nothing: the rings
stand on the frame of the drive room.

Height budget [E]: deck 850, ceiling 1400, top 2000. Rod length 380 stroke + 170 guide length + 45 coaming
= 595 of the 600 available. There is no margin; a taller cell is not possible without telescoping the rod.
The rod tip travels from 170 to 550 above the deck. Tools are 80–250 long.

### 2.4 Ceiling seams, rod collar, penetrations

HYG-004 forbids drives above open food unless under a drip-proof cover that is itself splash zone; HYG-016
asks that dynamic seals do not face food. The discs are that cover. The seam is designed so that what faces
the food is a plain gap, not a seal.

```
 SECTION THROUGH ONE SEAM (outer disc in the fixed ceiling; the inner seam is the same, one size smaller)

   dry room                       ring Ø 560 on V-rollers (frame-mounted)
                                        │
        disc rim, folded outwards ══════╧═══╗   ╔══ fixed coaming, 45 high, welded to the ceiling sheet
                         skirt ───►║        ║   ║       flush groove + 40 holes Ø 1.0 (water in wash,
             V-ring (elastomer) ─►(◄        ║   ║◄────── filtered dry air in operation)
             leak-off trough ══════╝   ╔════╝   ║
             with drain and sensor     ║  gap   ║
                                       ║  4 mm  ║
   ════════════════════════════════════╝        ╚══════════════════════════  ceiling sheet 2 mm
        rotating disc, flat underside, 3 mm         fixed ceiling, heated to cell air + 5 K
   cell (wet)                          ▼ air 0.3 m/s in operation; wash water drains here
```

* **What the food sees:** an annular gap 4 mm wide and 45 mm high between two smooth vertical stainless walls,
  open at the bottom, edges rounded R 2. It cannot hold liquid. Nothing above it can drip: over the top of
  the coaming the path turns downwards again on the dry side.
* **In operation** filtered room air (H13 cartridge in the drive room plenum) is blown into the flush groove
  at the top of every coaming and leaves downwards through the gap at about 0.3 m/s. Gap area of all seams:
  7.3 m × 4 mm = 0.029 m², so 31 m³/h [E]. This air is the make-up air for the cell's fume extraction
  (100–150 m³/h [S, R5] drawn off through a slot in the back wall behind the hobs). Steam, grease aerosol and
  flour dust are therefore carried away from the gaps, and the air flow runs from the clean preparation end
  to the hob end.
* **In the wash** the same groove is fed with recirculated wash liquor: 40 jets of Ø 1.0 at 0.5 bar,
  15 L/min per seam, aimed at the rotating rim wall while the disc turns ±190° twice (30 s per seam, one
  seam at a time through a dishwasher-type diverter). The liquor runs down both walls and drips into the
  cell. Then 5 s of fresh 80 °C water, then air. Whether the fixed coaming wall, which carries the jets, is
  wetted completely is not known (risk 1).
* **The seal** is a standard V-ring at the foot of the skirt, outside the coaming. It keeps room air out of
  the plenum and steam out of the drive room. It never sees food soil; water that is shot over the coaming
  by a jet collects in the leak-off trough and returns to the sump through a drain with a conductivity
  sensor. Wear debris of the V-ring falls into the trough, 45 mm below the coaming top. The V-ring is
  changed from the drive room without opening the cell (LRU, est. every 2–3 years).
* **Condensate.** The ceiling sheet and the discs carry a 200 W trace heater and stay 5 K above cell air
  (SM-216). After the wash each hand wipes the ceiling half of its neighbour with the squeegee.
* **Flatness, not slope.** A rotating disc cannot be sloped to a gutter, so the ceiling is horizontal. This
  deviates from R6's "ceiling sloped ≥ 5°" and rests on heating and wiping instead. HYG-014 is met in the
  sense that nothing can pool; hanging drops after the wash are removed by the squeegee and the dry-out.

**Rod collar** (one per turret, in the inner disc; SM-191). From the cell upwards: PEEK scraper ring, ring
nozzle (8 jets, hot water), drained lantern chamber 30 mm with sensor, dry lip seal, guide bushings. The
rod is a ground and polished tube; its whole wetted length passes the collar every time it retracts. The
collar cartridge is an LRU changed from above.

**Rod tip.** Male taper Ø 30 → 26 × 35 with two radial pins Ø 5 (the bayonet, 2.6); in its centre the core
shaft ends as an 8 mm ball-hex with a Ø 4 bore. Between core shaft and rod tube sits one PTFE lip seal
Ø 14: **the only dynamic seal on a food-side surface**, 3 per cell. It is inside the tool socket whenever a
tool is mounted, is flushed by the collar on every retraction, is purged with dry air from inside (a leak
blows outwards), and is changed with the rod-tip cartridge. HYG-016 is met only in its second clause
("cleanable in place and an LRU").

**All penetrations of the cell:**

| Penetration | Number | Type | Faces food? |
|---|---|---|---|
| Turret seams (Ø 500, Ø 270) | 6 | open coaming gap, V-ring outside | gap above food, no seal |
| Rod collars | 3 | scraper + flush + lantern + lip seal | yes, above food; rod is wiped |
| Core shaft seal at the rod tip | 3 | PTFE lip Ø 14, air-purged | yes |
| Ram collar | 1 | as rod collar, in the fixed ceiling | above the press station only |
| BT shaft | 1 | raised boss 25 mm with umbrella skirt, no contact seal (SM-236) | below the board |
| Load-cell posts (dock 3, C1 1, W 1) | 5 | static diaphragm | no |
| Hob plates | 4 | glass-ceramic Ø 300 bonded flush into the deck, static | below vessels |
| Camera and light windows | 5 | bonded, heated glass in the free ceiling corners | above food, static |
| Nozzles, extraction slot, drain, gutter | — | welded | no |
| Port to the transport system | 1 | lift-gate in the left wall, inflatable static seal when closed | no |
| Oven mouth | 1 | welded collar round the oven front, static gasket | no |
| Front door | 2 leaves | static gasket, drained sill | no |

### 2.5 The press station

The ram comes down at (550, 110) through the triangle of fixed ceiling that is left between two turrets at
the back wall. Below it two round pegs (Ø 16 × 90, welded to the back wall at z = deck + 380) carry a **die
cassette**; the reaction goes through the pegs into the back frame and from there to the ram housing, a
closed C-frame of 130 throat. The deck and the turntable carry no press load.

What receives the product is a cup standing on the rim of BT at radius 165, directly under the cassette.
BT turns the full cup to either hand and brings the next empty one: a two-station carousel without any
further part. The cut-off under a dicing grid is made by a hand that sweeps the horizontal blade V2 flush
along the underside of the grid after every 5, 10 or 20 mm of ram travel (SM-009 with a hand-held knife
instead of a cut-off actuator or the rim knife SM-012). The ram foot is the grid's negative (SM-011).

| Cassette (ware, custom) | Chamber | Use | Ram force [S/E] |
|---|---|---|---|
| Dice 10 mm, two-tier staggered grid | 62 × 62 × 120 | potato, carrot, celeriac, apple, onion; sticks without cross-cut | 0.9–2.3 kN [S, R4] ÷ 3 by staggering |
| Dice 5 mm | 62 × 62 × 120 | fine onion, soup vegetables | 1–2.5 kN |
| Dice 20 mm / wedger | 62 × 62 × 120 | stew vegetables, potato wedges | 0.5–1 kN |
| Former: tube Ø 60 with nozzle plates | Ø 60 × 150 | dumpling and croquette portions, gnocchi strand, butter log | 0.3–0.6 kN |
| Ricer / mill plate 2.5 mm | Ø 100 × 120 | passing, tomato passata, squeezing grated potato (SQZ) | 1–3 kN |

### 2.6 Tool interfaces and the roll head

**V interface (vertical bayonet).** Tool socket: a female taper with two J-slots, open at the bottom edge with
two drain slots; it holds no water in any position. Pick-up: rod down onto the socket, yaw 30°, lift 1.5 mm
into the seat. Release is the reverse and needs the tool to be held against rotation, which the flats on
the tool neck do in the rail slot or rim rest. Carries 300 N push, 100 N pull, 20 Nm, 12 Nm bending.
Tools with a drive (blender, tongs, roll head) have a hex socket that the core enters; tools with a fluid
function (lance, vacuum cup, pipette, air corer, drain wand) seal on the taper with a moulded silicone lip
that is part of the tool. No spring, ball or thread on either side. Pick-up is confirmed by the Z motor
current (tool weight) and by the ceiling camera.

**Roll head RH (ware, custom; 3 in use + 1 spare).** A rigid stainless frame on a V socket, 190 mm from the
rod axis to the front of its horizontal output. The core turns a stainless worm; a PEEK worm wheel (20 : 1,
dry-running, open teeth of module 2) turns the output socket: 5 Nm, 0–300 rpm, self-locking, so a vessel
held at an angle stays there without power. Mass 0.9 kg. It is a gearbox in the food zone, but an open one:
two plain bushes with open ends, no housing, no lubricant, and it goes to the washer after every meal.

**H interface (stub).** A short horizontal stub Ø 22 × 40 with two pins, welded to every item that is
carried by the roll head. The output socket is pushed over the stub (disc motion) and locked by 60° of
roll, which the resting weight of the item resists. Payload 4 kg; roll torque 5 Nm.

What the roll head is used for:

| Function | How |
|---|---|
| Reach | offset 190 mm: relays between zones, reaching into the box on the dock, serving the left hob column from T2 |
| Flip pieces (SM-129) | turner or fork on the stub, 180° roll |
| Pour, dump, ladle | cups, jug bowl, basket, scoops and ladles carry a stub; roll to pour; weight at the source or target cell |
| Spit (SM-001) | two-prong fork on the output: potato, apple, kohlrabi turn at 120 rpm against the peeler held by the other hand |
| Mandrel (SM-082) | slotted rod Ø 12 on the output rolls a Roulade along the slice |
| Whole-pan flip, unmould (SM-127) | locked pan pair turned in the air (below) |
| Invert a bowl | 8 L bowl with 1.6 kg of dough (2.9 kg, 2.8 Nm) turned out over a tray |

**Pan pair without a flip bracket.** A:M17 and D:N13 turn a pan pair about a fixed pivot on the wall. With
the reach limits of 2.2 a fixed bracket would sit in the wrong zone for the cook hand. Instead the pair is
turned in the air:

* Each frying pan (Ø 280, 1.3 kg) and each turn-out plate has three welded features on its rim: a **lift
  stub** at 12 o'clock, a **half stub** (D-section) at 3 o'clock whose flat lies in the rim plane, and a
  **hook tab** at 9 o'clock.
* Pan B is picked by its lift stub, rolled upside down, set on pan A 8 mm off-centre and slid sideways:
  the two hook tabs engage, and the two half stubs meet to form one round stub on the pair's axis of
  symmetry.
* The roll head takes the pair by that twin stub (which also stops the pans from sliding apart), lifts it
  160 mm, rolls 180° and sets it down. The pair is balanced about the stub; the food adds about 0.2 Nm.
* The head then takes the upper pan by its lift stub (now at 6 o'clock), slides it free, lifts it, rolls it
  upright and returns it to its hob.

Three grips, about 40 s [E]. Load on the bayonet: 3.2 kg at 290 mm = 9 Nm. The same sequence unmoulds a
cake (tin in a carrier ring, turn-out plate on top). Untested; the pans are bought pans with custom welded
features.

### 2.7 Tools, fixtures and vessels

"Use" is the share of the 248 corpus meals in which the operations the part serves occur [S, R2 4.2/4.5;
rounded]. All parts are 1.4404 unless noted, one or two pieces, no closed hollow.

**Rod tools (V interface)**

| # | Tool | Dimensions | Operations | Use | Source |
|---|---|---|---|---|---|
| V1 | Chef's blade, vertical | blade 200 × 45 | slice, halve, trim, carve, cut dough, portion | > 60 % | bought blade, custom shank |
| V2 | Horizontal blade on a Z-shank | 150, 5–60 above the surface | cut-off under the die, split roll or cutlet, horizontal onion cuts | 45 % | custom |
| V3 | Comb ("fakir hand"), cranked 90 | tines Ø 1.5 × 40 at 5 pitch | hold produce, slice pitch fence for carving (SM-003) | 40 % | custom |
| V4 | Sprung peeler | swivel blade on a flexure, 3–6 N | peel on the spit (SM-046) | 35 % | bought blade, custom |
| V5 | Gouge Ø 10 and tube corer Ø 22 with air ejection | — | eyes, stalks, apple core (SM-040, -044) | 20 % | custom |
| V6 | Press plate Ø 120 and grid masher Ø 90, 5 mm holes | — | press crumbs, smash patties, mash (SM-185) | 12 % | custom |
| V7 | Dough hook | for the 8 L bowl | knead, mince mass (SM-172) | 12 % | bought (mixer hook), custom socket |
| V8 | Balloon whisk Ø 90 and Ø 40 | — | whisk, whip, emulsify (SM-177) | 21 % | bought, custom socket |
| V9 | Flat beater with silicone edge | for jug bowl and 8 L bowl | cream, fold, mix batter, scrape bowl | 20 % | bought |
| V10 | Stick-blender head, core-driven | bell Ø 65 | purée, blend hot soup (SM-024) | 6 % | bought foot, custom socket |
| V11 | Rolling pin, free sleeve on a fork shank | 250 × Ø 50 | roll dough in the tray, flatten cutlets (SM-106, -090) | 6 % | custom |
| V12 | Cone roller | Ø 20 → 70 × 180 | round sheets on the turning board (SM-105) | 3 % | custom |
| V13 | Air corer Ø 60 and Ø 35 | tube 140 long | form patties and dumplings, portion butter, paste, dough (SM-075), ejected by an air pulse through the bore | 8 % | custom |
| V14 | Vacuum cups Ø 20 / Ø 40 (silicone) | — | eggs, slices, pasta sheets (SM-099) | 25 % | bought cup, custom stem |
| V15 | Pipette barrels 60 / 300 mL | air displacement through the bore; only the barrel is wetted | liquids, egg wash, batter metering, basting (SM-144) | 50 % | custom |
| V16 | Spice wand | grooved pin, 0.1 mL | seasoning from the box (SM-140) | 40 % | custom |
| V17 | Drain wand | tube Ø 12 with slotted tip | empties cooking water through the bore to the drain pump (SM-158) | 20 % | custom |
| V18 | Rotary jet lance | two 1.2 nozzles | cell wash (SM-188) | every day | bought nozzle |
| V19 | Squeegee 200 | silicone lip | dry ceiling, walls, deck (SM-214) | every day | custom |
| V20 | J-lifter | two hooks, span 290 | carries pots, braiser, basket, dishes by two rim ears, on the rod axis, up to 8 kg | 70 % | custom |
| V21 | Pinch tongs, core-driven face cam | jaws 0–80, 20 N, silicone fin-ray fingers | pieces, leaves, bundles, sheets (SM-152, -153) | 60 % | custom |
| V22 | Rounding cups Ø 60 / Ø 90 | — | round balls, rolls, dumplings on the board (SM-073) | 5 % | custom |
| V23 | Sifter cup | mesh 1 mm, yaw dither | sift, dust, sprinkle crumbs and cheese (SM-135) | 15 % | custom |
| V24 | Reamer and grater cone | — | citrus juice, zest (SM-036) | 8 % | bought |
| V25 | Silicone brush | — | grease tins, glaze, baste, scrub roots | 15 % | bought head |
| V26 | Core-temperature probe carrier | sets and removes a wireless probe | COK-013 | 15 % | bought probe |

**Roll head and stub tools (H interface)**

| # | Tool | Operations | Use |
|---|---|---|---|
| RH | Roll head | see 2.6 | every hot meal |
| H1 | Turner 110 and wide turner 200 | flip and lift pieces, plate | 25 % |
| H2 | Wide four-tine fork | breading, lifting cutlets and fillets (SM-094) | 8 % |
| H3 | Two-prong spit fork | peeling, zesting, jet-skinning | 35 % |
| H4 | Ladle 100 mL, scoops 60 / 250 mL | batter, sauces, granular and powder dosing, plating | 80 % |
| H5 | Spoon-scraper with silicone edge | stir, scrape, fold; rides in its pot | 60 % |
| H6 | Slotted mandrel Ø 12 × 160 | Rouladen, wraps | 5 % |
| H7 | Shell cradle | egg station top (below) | 15 % |
| H8 | Cup holder ring | carries stub-less small cups and the inspection saucer | 40 % |

**Fixtures (ware)**

Die cassettes (5 types, 2.5) · egg station: cradle with two blades and a spreading cam over an inspection
saucer, worked by one Z stroke (SM-165, SM-168), with a slotted saucer for separating (SM-169) · grater
plate on a cup (coarse / fine faces) · Spätzle slider (hopper on a perforated plate that lies on the pot
rim) · Rouladen spacer comb · taco and cannelloni rack · spiked carving insert for the board · two board
discs Ø 400 (HDPE on a steel core: green for ready-to-eat, red for raw animal food) · silicone mats
400 × 300 · three breading trays GN 1/4 × 40 · sieve insert for the jug bowl.

**Vessels** (6-person set; all with two rim ears for V20; those ≤ 4 kg gross also with a lift stub)

| Vessel | Size | Number | Notes |
|---|---|---|---|
| Boil pot with lift-out basket | 9 L, Ø 260 × 170 | 1 | never lifted full (rule R7); emptied by the drain wand |
| Rondeau / braiser with lid | 5 L, Ø 260 × 100 | 2 | stews, soups, 8 Rouladen; hob and oven |
| Pot with basket and lid | 4 L, Ø 220 × 110 | 2 | potatoes, vegetables |
| Sauce pots with lid | 2.5 L Ø 180; 1.5 L Ø 160 | 1 + 1 | 0.15 L minimum in the small one |
| Frying pans with half stub and tab | Ø 280 | 2 | pair flip |
| Large pan | Ø 360 | 1 | bridges one hob column; not flipped, not poured |
| Small pan | Ø 200 | 1 | 1-person dishes |
| Roaster with lid | GN 2/3 × 100 | 1 | 12 Rouladen, roast up to 2.5 kg; oven, or seared on a bridged column |
| Mixing bowl with base ring for BT | 8.5 L, Ø 260 × 160 | 2 | dough, mince, salad; carries the spin basket |
| Jug bowl, induction base | 3 L, Ø 180 × 120 | 2 | batters, whipping, creaming; poured by the roll head |
| Beakers | 0.5 L | 3 | one egg white, vinaigrette, slurry (PRP-038) |
| Prep cups | 1.5 L, Ø 150 × 90 | 6 | everything that travels between zones |
| Seasoning cups, inspection saucer | 0.15 L | 3 | — |
| Trays, tins, dishes | 2 trays 400 × 300; gratin dish 300 × 200 × 60; loaf tin 300; springform Ø 260 in a carrier ring; muffin tray | 7 | bought, with welded ears or carrier |
| Turn-out plates | Ø 280 round, 320 × 140 | 2 | half stub and tab |

About 35 vessels and lids, 46 tool and fixture types in roughly 75 pieces (two sets of the frequent ones):
**about 110 loose parts** [E]. CAP-030 (six food vessels in use at once) is met.

### 2.8 Tool logistics

* **Rails.** Rail A (at T1) and rail B (at T2) are stainless bars with five open slots each, hung on two
  wall pegs over the rear gutter, tools hanging socket-up. A rail with its tools is loaded in the clean
  store, comes in as one item and leaves as one item (SM-122 applied to a rail). Its slots lie on a chord of
  the reach circle at y = 120, which is why a rail holds only five tools.
* **Rim rests.** Cooking tools (spoon-scraper, turner, ladle) arrive hanging on a V-saddle on the rim of their
  pot or pan and go back there between uses, as a cook's spoon does. There is no room for a rail above the
  hobs, and none is wanted there.
* **Jet gates G1, G2.** Three fixed fan nozzles on the back wall above the gutter. A tool is held in the
  fan and spun by yaw (300–600 rpm) or by the roll head: 6 s cold rinse, 3 s spin-dry, 0.2 L. This is the
  rinse between two foods of the same class (HYG-030), not a disinfection.
* **Class R.** Tools for raw animal food hang on rail B's red half or come on a third rail; they are used
  last (SM-208) and go to the washer's disinfecting programme.
* A reference meal uses 12–18 tools and makes 30–45 tool changes of 6–8 s each: 4–6 min of hand time [E].

---

## 3. Ingredient intake and dosing

**The port and the dock.** The transport system pushes one box at a time through the lift-gate in the left
wall onto the dock shelf D (200 × 250, three 6 kg load cells, ±1 g). The box stands inside the cell with its
long side along y; T1 reaches its right half with the rod axis and the rest with offset tools. All dosing
out of a box is measured as loss in weight at the dock (PRP-012) and checked as gain in weight at C1, W,
BT or the hob block (the block stands on three 30 kg cells, ±5 g, which also gives COK-014). The common
dock tilter (0–135° about the pour edge, with vibrator; SM-133) pours over the shelf's right edge into a
cup on C1 or W. The lid is taken off by T1 by its knob (a stub; request A2) unless the transport system
delivers the box open. Seasoning is weighed at W, 250 mm from the nearest heat source and upwind of it in
the air stream, and carried to the pot (rule R8).

Every dose that goes to the hobs travels in a **prep cup** (1.5 L, with stub): T1 → BT (half turn) → T2 →
left hob column directly, or → bench edge → T3. That is 2–3 hand-overs per cup and the main cost of the
reach geometry.

| Form | Method | Accuracy, time [E] | Confidence |
|---|---|---|---|
| Whole produce | Camera picks a piece in the open box; tongs V21 or spit fork H3 takes it. Soil-bearing produce is first held in jet gate G1 and turned (FSF-042). | exact count; 6 s per piece | high for firm pieces |
| Leafy, bulky | Tongs take handfuls into the spin basket until the dock shows the target; a whole lettuce is taken whole, the stem cut out on the board, the rest returned in its box. | ±15 g; 8 s per grab | medium |
| Free-flowing granular | Dock tilt-pour with vibration into a cup on C1; fine trim with the 60 mL scoop. | ±2 g or ±2 %; 15–30 s | high |
| Powder, cohesive | Scoop H4 cuts the powder out of the box (nothing has to flow), dumps by roll into the cup on C1, trickles the last 5 % with a slow roll; or sifter cup V23 for dusting. | ±2.5 g; 20–40 s | high; dust is contained by the downward air flow |
| Seasoning 0.2–5 g | Spice wand V16 through the wiper insert of the spice box into the cup on W (0.1 g steps); salt optionally as 25 % brine from a fixed line (SM-143). | ±0.1 g; 3 s per dip | medium-high; oily spices pack |
| Water | Through the bore of any rod, flow meter on the dry side, cold or mixed from the boiler. | ±5 mL or 3 %; 3 L/min | high |
| Other liquids | Pipette barrel V15 (300 mL) from the opened box or carton; above 0.5 L dock pour into a cup. | ±2 %; 10 s per stroke | high for thin liquids, medium for oil and cream (film) |
| Viscous paste | Scoop or spoon on the roll head dips into the jar or box, the dock shows the dose, the pot's own scraper wipes the spoon (two tools). Stiff pastes and butter by air corer V13 (10 / 38 mL per stab at 10 mm depth steps). | ±3 g; 20 s | medium |
| Solid fat | Butter block on the board, knife cuts by length (2.5 g/mm); or air corer. | ±3 g | high |
| Raw meat pieces, mince | Pieces by wide fork H2 or tongs onto the red board; mince tipped from its pack by the dock tilter into a bowl, or cored from the pack with V13. | exact count; ±8 g for mince portions | medium |
| Raw meat slices | Vacuum cup Ø 40 lifts one slice if the slices are interleaved (request A6); otherwise the turner is worked under the top slice with the fork as hold-down. Slices that stick together in a vacuum pack are not solved (catalogue gap G9). | 8 s per slice | medium / low without interleaf |
| Egg | Vacuum cup Ø 20 on the blunt end, from an egg-tray insert in the box, to the egg station. | 5 s | medium-high |
| Frozen loose | Dock pour into a cup; the box is back in the freezer within 90 s. | ±5 g | high |
| Frozen blocks | Tongs; or grated on the grater plate while held on the spit fork (SM-148). | — | medium |
| Long goods (spaghetti) | Tongs take bundles into a tall cup on W until the mass is reached; the cup travels. | ±15 g | medium |
| Stowed sealed packs (DEC-3) | The pack-opening mechanism of the ingestion lane is assumed to deliver the opened can, jar, carton or tub in a carrier box at the dock. Can and carton: dock pour, then 50 mL of the recipe's water as chase (SM-119). Jar and tub: spoon, pipette or air corer. Vacuum pack of meat: opened outside; contents tipped or picked. K1 adds nothing to pack opening. | — | as above |

---

## 4. Operation table

Times are per piece or per batch for 4 persons [E]. Confidence: H = known practice at this scale and force,
M = sound but needs a bench test, L = speculative. "Hands" = number of hands busy.

### 4.1 MEAL-018 (a): operations without a purchase workaround

| Operation | Mechanism and steps | Time | Hands | Conf. | Untested |
|---|---|---|---|---|---|
| Flip pieces: steak, patty, cutlet, fish fillet (FLP) | Turner H1 on the roll head slides under the piece against the pan wall, lifts 40 mm, rolls 180°, lowers. Fragile pieces: wide turner, and the second hand's fork as backstop at the left hob column. | 6 s per piece | 1 | H | breading loss on cutlets; whole fish |
| Flip whole-pan items: pancake, omelette, Rösti, tortilla (FLP) | Locked pan pair turned in the air by the roll head (2.6); second pan preheated and greased. | 40 s | 1 | M | fat running out at the rim; sticking to the first pan; hook-tab engagement with warped pans |
| Assemble layered dishes (LAY, TOP, SPR) | Dish on a cold hob position beside the sauce pots; ladle H4 deposits, spoon-scraper spreads in a raster, vacuum cup lays sheets, sifter cup or scoop sprinkles. Pizza: pipette raster and spatula, toppings by cup, scoop and sifter. | 75 s per layer | 1–2 | H | evenness ±20 % |
| Assemble open-hand food (ASM): burger, sandwich, toast, bowl | Pick and place on a plate or board on the bench under the ceiling camera: tongs (bun, leaf), turner (patty), vacuum cup (cheese, cold cuts), pipette (sauce). | 8–10 s per item; 70 s per burger | 1 | M | stack stability on the way to the hatch; leaf handling |
| — taco, filled wrap | Taco shells stand in a rack and are filled by small scoop. Wraps are rolled with the mandrel (below) or served open. | 40 s each | 1 | M–L | shells breaking; burrito fold with tucked ends is not covered |
| Carve a boneless roast (CAR) | Roast on the spiked board insert on BT; comb V3 (second hand) sets the pitch; knife V1 draw-cuts at 100–200 N along its edge while descending. | 6 s per slice | 2 | H | hot braised meat tearing |
| Carve bone-in poultry (CAR, S) | Not covered. Poultry is cooked as parts, or a small bird is served whole (SM-244). | — | — | — | gap G5 |
| Unmould (UNM) | Knife runs round the edge (round tins: yaw; loaf tins: four strokes); turn-out plate hooked on; pair flipped by the roll head; tin lifted off. Silicone moulds: pressed out with the press plate. | 60 s | 1 | M | sticking, as for a human cook; ≥ 95 % undamaged |
| Score (SCO) | Knife on a programmed path to a Z depth referenced by first contact (BT load cells). | 1 s per cut | 1 | H | rind of a hot roast is not reachable in the oven: scored before roasting |

### 4.2 MEAL-018 (b): the shaping cluster

| Operation | Mechanism and steps | Time | Hands | Conf. | Untested |
|---|---|---|---|---|---|
| Stuff rigid cavities (STU) | Item stands in a rack on the bench; filling by small scoop, air corer or pipette, by weight. | 15 s each | 1 | H | — |
| Stuff flat pockets, dumpling cores, poultry cavity | Flat pocket: fold with the turner and pin — not worked out. Dumpling core: crouton pressed into the portion before rounding (M). Cavity of a bird: scoop (M). | — | — | L | gap G4 remains |
| Roll Rouladen (RLT) | Slice on the red mat on the bench with its leading edge over a 10 mm step at the mat's edge. Pipette rasters mustard, spatula spreads; cup, scoop and tongs place bacon, onion and gherkin. The slotted mandrel H6 slides over the leading edge and rolls **along the stationary slice** (the head translates at the rolling speed and presses with 10 N), 2.5 turns. The roll is drawn through a U-notch that strips it off the mandrel into the braiser, seam down. | 80 s per Roulade with filling | 1 (2 to halve the time) | M | grip of the slot on a wet slice; filling pushed ahead of the roll |
| Secure Rouladen | Eight rolls packed seam-down against each other in the Ø 260 braiser; for fewer, the spacer comb fills the row (SM-084). Seam seared first, then the rolls are turned twice by tongs. Fallback: steel pin through the seam, set with tongs through a guide notch in the comb (SM-085). | 3 min searing | 1 | M–L | **whether an untied roll stays closed through a 100 min braise** — the shared highest-priority test |
| Wrap (WRP): cabbage roll, bacon wrap, enchilada, strudel from bought sheets, sponge roll | Mandrel for small wraps; mat roll (SM-080) for strudel and sponge roll: the roll head takes the bar at the mat's edge and carries it over while the second hand's pin tucks. | 40–90 s | 1–2 | M | hot sponge cracking; whole cabbage leaves are not separated (G7) |
| Form patties and dumplings (FRB, FRK) | Mass stands in its bowl on a cold hob position. Air corer V13 stabs 35 mm deep (Ø 60 × 35 = 100 mL), lifts, moves over the pan or tray, an air pulse of 0.3 bar ejects the portion; the press plate flattens patties to 20 mm; the rounding cup rounds dumplings on a wet board. | 8 s per portion + 3 s; 12 patties in 2.5 min | 1 | M | release of sticky mince from the tube; smear at the bore mouth |
| Form small pieces (FRM): gnocchi, Schupfnudeln, croquettes, falafel, cookies | Portions by the small air corer or a strand from the former cassette cut by the knife; rounding cup; tapered ends by the press plate rolled to and fro. | 5 s per piece | 1 | M | tapered shapes |
| Bread (BRD) | Three GN 1/4 trays on the bench. Wide fork H2 on the roll head lays the cutlet in flour, flips it by roll, shakes; dips in egg, drains 5 s; lays in crumbs; the scoop covers, the press plate presses at 20 N; flip, press; carry to the pan. | 70 s per cutlet | 1 (2 with T3 helping) | M–H | ≥ 95 % coverage at the fork's contact lines; crumb waste |
| Roll out dough (ROL) | Tray-size: dough on a mat in the tray on the bench, rolling pin V11 on the rod axis, 150–200 N, linear passes in two directions, thickness from Z at contact. Round: cone roller V12 on the turning board. The mat or tray goes to the oven; the sheet is never lifted. | 3 min | 1 | H | spring-back of yeast dough; corners |
| Shape dough (SHD) | Loaf in its tin; rolls: knife portions by weight, rounding cup; pizza: as ROL. | 10 s per roll | 1 | M–H | — |
| Line a tin with a sheet (LIN) | Sheet rolled on a mat; tin set upside down on it; pair turned with the turn-out plate sequence; press plate presses the sheet into the corner. | 2 min | 1 | L–M | sheet tearing at the edge |
| Knead (KND, KNM) | 8.5 L bowl on BT turning at 8 rpm; hook V7 on T1's yaw at 60–100 rpm and 15–20 Nm, 75 mm off the bowl axis. Energy target from the yaw torque. 100 g of dough: jug bowl. | 8 min dough; 90 s mince | 1 | H | side load on the rod from stiff dough (est. 100 N) |

### 4.3 Peeling, trimming, cutting, egg

| Operation | Mechanism and steps | Time | Hands | Conf. | Untested |
|---|---|---|---|---|---|
| Wash roots | Held in jet gate G1 on the spit or in tongs and turned; brush V25 if needed. | 6 s | 1 | H | — |
| Peel potato, apple, kohlrabi (PLP, PLS) | Spit fork H3 stabs the piece along its long axis (camera; the other hand's tool is the backstop), spins it at 120 rpm; peeler V4 on the second hand traverses at 12 mm per turn above the board's right half. Camera finds remaining patches; gouge V5. Peel falls on the board and is swept into the gutter. | 25 s per piece; 1.5 kg in 5 min | 2 | M–H | loading lumpy tubers; loss 15–20 % |
| Peel carrot, cucumber | As above; slender carrots (< Ø 20) are scrubbed instead. | 25 s | 2 | M | whip of a long carrot on the fork |
| Peel onion (PLA) | Baseline: bought peeled (MEAL-012). Upgrade slot: top and tail, one meridian slit, then the onion spins on the spit in the fan of jet gate G1; skins fall into the gutter (SM-060). | 20 s | 1–2 | L–M | everything; the hardware for the test exists in the cell |
| Garlic | Pressed unpeeled through the ricer cassette, or bought. | 10 s | 1 | M | — |
| Knobbly produce, tomato, boiled egg (PLH, PLM, PLE) | Celeriac, swede: cut-away in facets with the knife, piece held by the comb (loss 30 %). Tomato: blanch in the basket, skin pulled by tongs. Boiled egg: crazed under the press plate at 15 N, shaken with water in a closed cup on the roll head. | 60 s; 30 s | 1–2 | M; L for egg | egg yield |
| Core apple, pear (COR) | Tube corer along the stalk axis, 100–150 N, air ejection. | 8 s | 1 | H | finding the axis |
| Deseed pepper | Knife takes the cap off, tongs pull cap and core, inside flushed in the jet gate. | 30 s | 1–2 | M | white ribs; vision |
| Trim ends (TRE) | Long goods: knife at both ends after the camera measured the piece. Beans: bundle pushed against the comb as a fence, one cut per end. Sprouts, mushrooms, strawberries: one camera-guided cut each. | 3–4 s per item | 1–2 | M | slow for 500 g of sprouts (2 min) |
| Strip, pluck, florets (STR) | Florets: vertical cuts round the stalk with board turns. Herb leaves from stems: not solved (soft herbs chopped with stems, woody herbs cooked whole and removed). | — | — | L | gap G2 |
| Dice (DIC), sticks (JUL) | Die cassette under the ram, cup on BT, hand-held cut-off (2.5). Free pitches and soft items (tomato, mushroom): cook's method with comb and knives on the board. | 12 s per piece; 1.5 kg potatoes in 3 min | 1 + ram | H | onion layers jamming in the 5 mm grid; blade roots as soil trap |
| Slice (SLI) | Knife on the board, comb as hold and pitch fence, 2 cuts/s. | 0.5 s per cut | 2 | H | throughput for 1 kg of cabbage (2 min) |
| Mince, chop herbs (MIN, CHH) | Bundle under the comb, knife at 1.5 mm feed, then cross passes with the board turned 90°; or bought frozen-chopped. | 40 s | 2 | M | bruising; herbs sticking to the blade |
| Grate, zest, juice (GRC, GRF, JUI) | Piece on the spit fork stroked over the grater plate on a cup at 30 N; citrus half pressed on the reamer turning on yaw. | 60 s per 100 g | 1 | H | last 15 % of the piece |
| Crack eggs (CRK) | Vacuum cup sets the egg in the station's cradle; one Z stroke of 14 mm pierces and spreads; contents fall into the inspection saucer on W; camera checks shell fragments and the yolk; roll head tips the saucer into the vessel and dumps the cradle's shells into the gutter. | 12–14 s per egg; 12 eggs in 2.8 min | 1 | M | fragments; the 3 min of UO-05 is met with no margin |
| Separate (SEP) | Slotted saucer under the cradle keeps the yolk. | + 5 s | 1 | M | yolk breakage |

### 4.4 Everyday operations and those nobody had addressed

| Operation | Mechanism and steps | Time | Hands | Conf. | Untested |
|---|---|---|---|---|---|
| Transfer vessel to vessel (PRP-013) | Up to 4 kg gross: roll head pours or inverts, the second tool scrapes; chase with recipe liquid. Heavier: ladle or scoop; nothing above 4 kg is ever tilted. Board to cup: spoon-scraper sweeps over the board edge into a cup standing under the overhang. | 10–30 s | 1–2 | H liquids, M dough | residue of dough and mince in the bowl (target ≤ 8 %) |
| Stir and scrape while cooking (STC, SAU; COK-008) | Spoon-scraper H5 on the roll head moved in circles by the two discs, blade kept tangential by yaw; rests on the pot rim in between. Continuous stirring binds one hand. | — | 1 | H | see weakness 1 |
| Mash (MSH) | Grid masher V6 driven to the pot floor at 150–300 N on a raster of 9 positions × 3 passes; milk and butter folded in with the scraper. | 90 s | 1 | H | texture against a ricer |
| Purée (PUR) | Stick-blender head V10 in the pot, 6000 rpm, moved in a slow circle. | 40 s per litre | 1 | H | splashing at low fill |
| Whip, whisk, emulsify, cream (WHP, WHK, EMU, CRM) | Whisk or flat beater on yaw (to 1200 rpm) in the jug bowl or a beaker, the rod moving on a small circle. Butter for creaming is warmed to 20 °C in the jug bowl on a hob at low power. | 1–4 min | 1 | H | one egg white in the 0.5 L beaker |
| Fold, rub in, sift (FLD, RUB, SFT) | Flat beater at 20 rpm with the bowl turning; rub in: flat beater at 60 rpm with cold butter cubes; sift: sifter cup. | 30–120 s | 1 | M | volume loss when folding |
| Toss salad (TOS) | Bowl on BT turning at 6 rpm, spoon-scraper lifts from the bottom and turns over, 8 cycles; dressing by pipette. | 30 s | 1 | H | — |
| Wash and dry leaves (WLF, DRY) | Spin basket in the 8.5 L bowl on BT; 3 L of water through the rod; reversing rotation 30 s; drain wand empties the bowl; spin at 600 rpm for 20 s inside the bowl, which catches the water. | 3 min | 1 | H | imbalance; grit |
| Drain (DRN) | Lift-out basket by J-lifter or roll head, held 20 s over the pot; the water stays in the pot until the drain wand empties it (1.7 L/min). | 40 s | 1 | H | drain wand clogging with starch |
| Squeeze (SQZ), press through (EXT) | Ricer cassette under the ram; Spätzle slider on the pot rim moved to and fro by the hand at 20 N. | 1–2 min | 1 | M | — |
| Flatten meat (POU) | Between two mats on the bench: rolling pin in passes, 200–300 N line load, or bought thin. | 30 s | 1 | M | evenness ±1 mm |
| Thin batter (PTH) | Ladle pours in a spiral over the hot pan. | 8 s | 1 | M | evenness without swirling the pan |
| Grease, glaze, baste (LIN, GLZ, BST) | Brush V25 with melted butter from a beaker, on programmed strokes; baste with the 60 mL pipette from the pan's low side or with the spoon. | 40 s | 1 | M | corners of a Gugelhupf tin |
| Shred cooked meat (SHR) | Two forks: not possible with one hand per zone; comb holds, fork on the roll head pulls. | 2 min | 2 | L–M | — |
| Oven handling | T3 pulls the telescopic rack out over the hob block with a hook on the J-lifter, sets the vessel or tray on it, pushes it in; the door is driven. | 30 s | 1 | M | rack travel against reach (x 1250–1575 on the rod axis) |

---

## 5. Benchmark walk-throughs

Conventions. Quantities for the number of persons given in the brief. t = minutes from the order. Time
limit = PERF-001 (M): 1.15 × T_ref + 10 min, T_ref from the corpus row of the slowest component.
A **handling move** is one pick-and-place, hand-over, pour, dump or tool change by a hand; cuts, strokes and
stirring are not counted. Hob positions: H1 front-left and H3 front-right (3.5 kW, vessel up to Ø 280),
H2 rear-left and H4 rear-right (2.0 kW, up to Ø 220); the Ø 360 pan or the GN 2/3 roaster takes a whole
column. T2 reaches the left column (H1, H2) with roll-head tools. Vessels come in from the port and are
relayed T1 → BT → T2 → bench edge → T3: about 5 moves and 50 s per vessel for zone 3.
Onions are bought peeled; all times and counts are estimates [E].

### B1 Rinderrouladen, Rotkohl, Salzkartoffeln (4 persons: 8 Rouladen, 1 kg cabbage, 1 kg potatoes)

| t | Step | Hands |
|---|---|---|
| 0–4 | Ware in: rondeau → H1 (cabbage), braiser → H3, 4 L pot with basket → H2, rails A and B, red mat on the bench | T1, T2, T3 |
| 4–12 | Red cabbage: quartered (knife, 300 N), stalk cut out with the quarter on its side, shredded at 3 mm (T1 knife, T2 comb, 240 cuts); four cup loads to H1 | T1, T2 |
| 12–15 | Apple peeled on the spit, cored, diced 10 mm under the ram; three onions diced 5 mm; gherkins cut into spears | T1, T2, ram |
| 15–18 | H1: lard, onion, 3 min; cabbage, apple, vinegar, wine, sugar, salt, cloves; lid; simmers until t = 150, stirred every 5 min by T2 | T2 |
| 17–31 | Rouladen on the red mat: slice laid (vacuum cup), salt, pepper, mustard rastered and spread, bacon, onion, gherkin; mandrel roll; roll set seam-down in the braiser at 220 °C with 20 mL oil. T2 fills, T3 rolls and places | T2, T3 |
| 31–38 | Seam side seared 3 min; rolls turned twice with tongs | T3 |
| 38–45 | Rolls out to a tray; onion and tomato paste 2 min; wine 150 mL, stock 400 mL; rolls back, packed seam-down; lid | T3, T2 |
| 45–145 | Braise on H3 at 95 °C. Meanwhile red mat, red tools and cassettes leave for the washer | — |
| 105–113 | Potatoes washed, peeled on the spit (8 × 25 s), quartered; cups to the basket in H2; 1.2 L water through T3's rod, salt | T1, T2, T3 |
| 113–140 | Boil (6 min to the boil at 2 kW, 21 min cooking) | — |
| 140–143 | Basket lifted and drained; drain wand empties the pot; basket back, lid | T3 |
| 145–152 | Rolls out to the warm tray; sauce blended 30 s; flour slurry from a beaker stirred in, 3 min; rolls back | T3, T2 |
| 153 | Three lidded vessels ready at ≥ 65 °C | |

Result: **yes**, provided the untied, packed rolls stay closed (otherwise pins, + 2 min). Elapsed 153 min
(limit 183). About 280 handling moves, of which 38 tool changes and about 70 are relays. Soiled: 3 cooking
vessels with lids and basket, tray, 7 cups, 2 beakers, 2 cassettes, red mat, board disc, 2 rails with 10
tools, 3 roll heads with 8 stub tools — about 45 items, 3 washer loads.

### B2 Wiener Schnitzel, Bratkartoffeln, Gurkensalat (4 persons)

| t | Step | Hands |
|---|---|---|
| 0–3 | Ware in: 4 L pot with basket → H4, Ø 360 pan → left column, Ø 280 pan → H3, jug bowl, three breading trays | all |
| 3–9 | Salad first (ready-to-eat): 2 cucumbers peeled on the spit, sliced 2 mm; sour cream, vinegar, sugar, salt, frozen dill whisked in a beaker; tossed in the jug bowl; bowl with lid back to cold storage through the port | T1, T2 |
| 9–14 | 900 g potatoes peeled on the spit (7 × 25 s), halved, into the basket in H4 with 1 L water | T1, T2, T3 |
| 14–37 | Boil. Meanwhile: onion diced 5 mm (ram); breading set up on the bench: flour 40 g, two eggs cracked and whisked, crumbs 120 g | T1, T2 |
| 20–27 | Four cutlets (bought thin) salted and breaded with the wide fork, 70 s each; laid on a tray | T2 |
| 37–42 | Basket out, potatoes cooled under rod water, relayed to the board, sliced 5 mm (84 cuts); two cup loads into the Ø 360 pan, 30 mL oil, 180 °C | T3, T2, T1 |
| 42–62 | Potatoes fried 20 min, turned every 3 min with the wide turner; bacon and onion at t = 50 | T2 |
| 46–60 | Ø 280 pan, 80 mL fat, 170 °C: two batches of two cutlets, 3 min per side, flipped with the turner; first batch held on a tray in the oven at 80 °C; lemon cut in wedges | T3 |
| 62 | Ready | |

Result: **yes**. Elapsed 62 min (limit 67.5). About 210 moves. Open: crumb coverage where the fork
carries the cutlet; potatoes are sliced warm, not cold from the day before (they break more). Two Ø 280
pans do not fit one column, hence two batches. Soiled: about 35 items, 3 loads (the breading trays are
class R).

### B3 Frikadellen, Kartoffelpüree, Erbsen-Möhren-Gemüse (4 persons) — PERF-002 (b): ≤ 50 min

| t | Step | Hands |
|---|---|---|
| 0–3 | Ware in: 4 L pot with basket → H2, 2.5 L pot → H4, two Ø 280 pans → H1, H3, mixing bowl → BT | all |
| 3–9 | 1 kg potatoes washed, peeled, quartered; to H2 with 1 L water and salt | T1, T2, T3 |
| 9–33 | Potatoes boil | — |
| 9–13 | 300 g carrots peeled and diced 10 mm under the ram; to H4 with 150 mL water, butter, sugar, salt; simmer from t = 16; 300 g frozen peas at t = 24 | T1, T2, ram |
| 13–19 | Mass: 40 g crumbs soaked in 80 mL milk, onion diced 5 mm, one egg, mustard, salt, pepper, 600 g mince tipped from its pack; kneaded 90 s with the hook on BT | T1 |
| 19–22 | Bowl to the bench; air corer forms eight portions of 95 g onto a tray (8 × 8 s); turners set four in each pan; press plate flattens them to 20 mm | T2, T3 |
| 22–34 | Fried at 160 °C, flipped at t = 28 (8 × 6 s); core probe 72 °C | T3, T2 |
| 33–38 | Basket drained, drain wand, potatoes tipped back; masher 90 s; 150 mL milk and 40 g butter folded in on low heat; nutmeg | T3 |
| 40 | Parsley (frozen chopped) on the vegetables; ready | |

Result: **yes**. Elapsed 40–42 min (limit 50). About 190 moves. The patties are cylinders pressed flat, with
a sharper edge than hand-formed ones. For 6 persons (12 patties, 1.5 kg potatoes) the pans hold 4 + 4, so a
second batch adds 12 min: 54 min, over the 4-person limit.

### B4 Spaghetti Bolognese with grated cheese (4 persons) — limit 96 min

| t | Step | Hands |
|---|---|---|
| 0–3 | Ware in: rondeau → H1, 9 L pot with basket → H3 | all |
| 3–10 | Onion, carrot (peeled), celeriac (cut-away in facets), garlic diced 5 mm under the ram | T1, T2, ram |
| 10–18 | H1: oil, 500 g mince seared and crumbled with the scraper, vegetables, 30 g tomato paste (spoon, wiped by the scraper), wine, 800 g tinned tomatoes (dock pour, two cups), stock, herbs, sugar, salt | T2, T1 |
| 18–68 | Simmer, stirred every 3 min | T2 |
| 50–59 | 4 L water through T3's rod (80 s), 40 g salt; to the boil at 3.5 kW | T3 |
| 59–69 | 400 g spaghetti (tall cup, weighed at W) tipped in, pushed under after 1 min, stirred twice | T3 |
| 69–71 | Basket lifted, drained 20 s, tipped into the rondeau by the roll head (1.8 kg); folded with the sauce | T3, T2 |
| 72 | Ready; grated cheese (bought grated, or 40 g grated from the block in 60 s) goes with it in a cup | |

Result: **yes**. Elapsed 72 min. About 150 moves. After the meal the drain wand needs 2.5 min for the 4 L.
For 6 persons: 6 L of water, 11 min to the boil, same sequence.

### B5 Pizza from flour, 2 trays — limit 113 min

| t | Step | Hands |
|---|---|---|
| 0–3 | Ware in: mixing bowl → BT, jug bowl → C1, tray with mat → bench, second tray on the cold hob block | all |
| 3–7 | 500 g flour (scoop into the jug bowl on C1, dumped into the bowl), 300 mL water at 30 °C through the rod, 7 g dry yeast and 10 g salt from W, 30 mL oil by pipette | T1 |
| 7–15 | Kneaded 8 min, hook on T1, bowl turning | T1 |
| 15–60 | Bowl covered, on the bench at cell temperature (or in the oven at 30 °C); oven then heats to 250 °C | — |
| 16–26 | Sauce: tinned tomatoes, salt, oregano, oil, blended 20 s; 250 g mozzarella diced; salami slices laid out | T1, T2 |
| 60–62 | Bowl inverted over the board by the roll head, scraper frees the dough; knife halves it by weight on BT; halves to the trays | T1, T2 |
| 62–69 | Tray 1: rolled to 400 × 300 × 4 with the pin (3 min with one rest), sauce ladled in a spiral and spread, cheese scattered by scoop, 10 salami slices by vacuum cup; T3 carries the tray to the rack | T2, T3 |
| 69–76 | Tray 2 the same, second rack level | T2, T3 |
| 69–88 | Baked 12 min each, fan, 250 °C | — |
| 90 | Both trays out onto the hob block; ready (cutting is serving) | T3 |

Result: **yes**. Elapsed 90 min. About 170 moves. The base is rolled in the tray, as for a home tray pizza;
a round base is made with the cone roller on the board and moved on its mat.

### B6 Vegetable soup from whole vegetables (6 persons, 3 L) — limit 50 min

| t | Step | Hands |
|---|---|---|
| 0–3 | Ware in: rondeau → H1 | all |
| 3–5 | 12 pieces washed in the jet gate | T1 |
| 5–10 | Four potatoes, three carrots, one parsnip peeled on the spit; celeriac cut away in facets | T1, T2 |
| 10–14 | 14 pieces diced 10 mm under the ram into three cups | T1, ram |
| 10–17 | Leek trimmed, halved lengthwise, rinsed in G2, sliced; 200 g beans aligned against the comb, both ends cut, cut to 30 mm; two tomatoes: stalk gouged out, diced | T2 |
| 12–18 | H1: oil, leek, carrot, celeriac sautéed; the rest as it arrives; 2 L water through the rod, stock paste, salt | T2, T3 |
| 18–45 | To the boil (5 min), simmer 22 min; frozen peas at t = 40; frozen chopped parsley | — |
| 47 | Ready | |

Result: **yes, without time margin** (47 of 50 min). About 170 moves. 1.3 kg of whole vegetables take
14 min of two hands, against 6 min for 1 kg in PRP-023, which counts cutting only.

### B7 Steak, oven fries, mixed salad with vinaigrette (2 persons) — limit 44.5 min

| t | Step | Hands |
|---|---|---|
| 0–2 | Ware in; oven heats to 220 °C | all |
| 2–9 | 500 g potatoes washed, peeled, pushed through the 10 mm grid without cut-off (sticks), rinsed and spun in the basket, tossed with 8 mL oil and salt in the jug bowl, spread in one layer on the tray; T3 sets the tray on the rack | T1, T2, T3 |
| 9–35 | Fries bake 25 min; turned at t = 22 with the turner on the pulled-out rack | T3 |
| 9–20 | Salad: lettuce stem cut out, leaves cut, washed and spun on BT (drain wand 100 s); tomato wedges, cucumber slices, carrot grated on the spit, radishes sliced, pepper capped, cored, cut in strips; vinaigrette whisked in a beaker | T1, T2 |
| 22–31 | Ø 280 pan on H3 to 250 °C; two steaks salted, seared 2.5 min per side, flipped with the turner; butter, thyme and garlic, basted three times with the spoon; wireless probe 55 °C | T3 |
| 31–36 | Steaks rest on a warm plate; salad dressed and tossed at t = 33 | T2 |
| 36 | Ready | |

Result: **yes** (the brief's own benchmark already uses oven fries in place of deep-frying). Elapsed 36 min.
About 150 moves. Deseeding the pepper is the least certain step.

### B8 Pfannkuchen, 8 pieces — limit 50 min

| t | Step | Hands |
|---|---|---|
| 0–2 | Ware in: jug bowl, two twin-stub pans → H1, H3, turn-out plate | all |
| 2–7 | 250 g flour, 500 mL milk (dock pour by weight), three eggs through the egg station, salt, sugar; whisked 60 s | T1, T2 |
| 7–27 | Batter rests; pans heat from t = 24 | — |
| 27–41 | Per pancake (cycle 105 s): butter in pan A, 100 mL batter ladled in a spiral (T2); 90 s; pan B set inverted on A, locked, pair flipped, A lifted off and returned (T3, 40 s); 60 s in B; B tilted by the roll head, pancake slides onto the stack plate | T2, T3 |
| 42 | Ready | |

Result: **yes, if the pair flip works**; it is untested and carries all whole-pan items of the corpus.
Elapsed 42 min. About 190 moves (20 per pancake). T3 is busy 85 % of the frying time.

### B9 Chicken curry with rice (4 persons) — limit 56 min

| t | Step | Hands |
|---|---|---|
| 0–3 | Ware in: rondeau → H1, 2.5 L pot with lid → H4 | all |
| 3–12 | Green board: onion diced (ram), pepper deseeded and cut in strips, courgette sliced, garlic and ginger paste by spoon, lime on the reamer | T1, T2 |
| 12–16 | Red board: 500 g chicken breast cut in strips (30 cuts, comb hold), to a cup. 300 g rice (dock pour) rinsed in the sieve insert under rod water, to H4 with 450 mL water and salt, lid | T1, T2, T3 |
| 16–34 | Rice: to the boil, then 15 min covered at low power | — |
| 16–36 | H1: oil, chicken seared 4 min; onion, curry paste 1 min; vegetables 3 min; 400 mL coconut milk (can, dock pour); simmer 12 min, stirred every 2 min; lime, salt | T2 |
| 38 | Ready | |

Result: **yes**. Elapsed 38 min. About 140 moves. Red board, knife and comb go to the disinfecting programme.

### B10 Lasagne, béchamel from scratch (4–6 persons) — limit 148 min

| t | Step | Hands |
|---|---|---|
| 0–18 | Bolognese as B4, on H1 | T1, T2 |
| 18–63 | Simmer, stirred every 3 min by T2 | T2 |
| 50–62 | Béchamel on H2: 50 g butter melted, 50 g flour stirred 2 min, 600 mL milk added from four beakers by T2 while T3 stirs without pause for 8 min; nutmeg, salt | T3, T2 |
| 55–60 | Gratin dish 300 × 200 × 60 to the cold position H3; 12 dry sheets on a small tray to H4; oven to 180 °C | T2, T3 |
| 63–70 | Four layers, 75 s each: two ladles of Bolognese spread, one ladle of béchamel spread, three sheets by vacuum cup; top layer béchamel and 150 g cheese by scoop | T3, T2 |
| 70–110 | Dish (3.2 kg) by J-lifter onto the rack; baked 40 min | T3 |
| 110–125 | Rests on the cold hob block | — |
| 125 | Ready (portioning is serving) | |

Result: **yes**. Elapsed 125 min. About 230 moves.

### B11 Rührkuchen in a tin, unmoulded — T_ref 100 min, limit 125 min

| t | Step | Hands |
|---|---|---|
| 0–2 | Ware in: jug bowl → H1, loaf tin in its carrier → H2; oven to 175 °C | all |
| 2–5 | 250 g butter cut in eight pieces into the jug bowl, warmed to 20 °C at low power; 200 g sugar, vanilla | T1, T3 |
| 5–11 | Creamed 3 min with the flat beater; four eggs cracked into one beaker at the station, relayed once, added in four pours with 20 s beating each | T3, T1, T2 |
| 11–13 | 400 g flour with baking powder sifted in three portions, alternating with 100 mL milk; folded 90 s | T3, T2 |
| 13–15 | Tin brushed with melted butter, dusted with flour, tapped out over the gutter; batter poured by the roll head, bowl scraped by T2 | T2, T3 |
| 15–75 | Baked 60 min; probe 96 °C | T3 |
| 75–95 | Cools in the tin on a cold hob position | — |
| 96–98 | Knife along the four walls; turn-out plate hooked on; pair flipped; tin lifted off | T3 |
| 98 | Ready | |

Result: **yes, if unmoulding succeeds** at the rate a greased tin gives a human. Elapsed 98 min. About 110 moves.

### B12 Scrambled eggs from shell eggs, toast, 1 person — limit 17 min

| t | Step | Hands |
|---|---|---|
| 0–1 | Ware in: Ø 200 pan → H2, Ø 280 pan → H1, beaker | all |
| 1–3 | Three eggs through the station (14 s each, each inspected), 20 mL milk, 1 g salt; small whisk 10 s in the 0.5 L beaker | T1 |
| 3–4 | Beaker relayed; 8 g butter melted at 110 °C in the small pan; eggs poured in | T1, T2 |
| 4–7 | Stirred without pause with the spoon-scraper | T3 |
| 4–7.5 | Two slices of bread toasted dry in the Ø 280 pan at 180 °C, 90 s per side, flipped with the turner | T2 |
| 8 | Eggs on the toast or handed over in the pan; frozen chopped chives | |

Result: **yes**. Elapsed 9 min. About 60 moves. It soils 16 items (two pans, beaker, saucer, cradle, cup,
six tools, three roll heads and a rail) for one portion: one full washer load.

### Summary and scaling

| # | Meal | Result | Elapsed / limit (min) | Moves | Depends on untested |
|---|---|---|---|---|---|
| B1 | Rouladen, Rotkohl, Salzkartoffeln | yes | 153 / 183 | 280 | mandrel roll; untied braise |
| B2 | Schnitzel, Bratkartoffeln, Gurkensalat | yes | 62 / 67.5 | 210 | breading coverage |
| B3 | Frikadellen, Püree, Erbsen-Möhren | yes | 41 / 50 | 190 | air corer release |
| B4 | Spaghetti Bolognese | yes | 72 / 96 | 150 | — |
| B5 | Pizza, 2 trays | yes | 90 / 113 | 170 | dough release from the bowl |
| B6 | Vegetable soup for 6 | yes, no margin | 47 / 50 | 170 | bean trimming |
| B7 | Steak, oven fries, salad | yes | 36 / 44.5 | 150 | pepper deseeding |
| B8 | Pfannkuchen × 8 | yes | 42 / 50 | 190 | pan-pair flip |
| B9 | Chicken curry, rice | yes | 38 / 56 | 140 | — |
| B10 | Lasagne | yes | 125 / 148 | 230 | — |
| B11 | Rührkuchen, unmoulded | yes | 98 / 125 | 110 | unmoulding |
| B12 | Scrambled eggs, toast, 1 person | yes | 9 / 17 | 60 | egg station fragments |

No benchmark needs an adapted method beyond the oven fries that the brief's B7 already names. None has
been shown to work.

1 and 6 persons. B12 is the 1-person case. B3 for 1 person: 150 g of mince mass in the jug bowl, one pan,
the 1.5 L pot for 250 g of potatoes; nothing changes but the ware. B3 for 6: 54 min (second pan batch).
B1 for 6: 12 Rouladen in the GN 2/3 roaster, seared on the bridged left column and braised in the oven;
the cabbage moves to H3; rolling takes 6 min longer. B4 for 6: above. The hands are the limit for 6
persons, not the vessels: every per-piece operation (peel, roll, bread, form, flip) scales linearly and only
two hands reach any one workpiece.

The 15 reference menus of corpus 4.9, read against sections 4 and 5:

| Menu | Result | Note |
|---|---|---|
| Spaghetti Bolognese | yes | B4 |
| Schnitzel, Pommes, salad | adapted | oven fries (X-01); two cutlet batches |
| Steak, baked potato, salad | yes | as B7 |
| Frikadellen, potato salad, cucumber salad | yes | potato salad cooled in cold storage (COK-022) |
| Pizza, salad | yes | B5 |
| Käsespätzle, salad | yes | Spätzle slider on the pot rim; 3 positions and the oven |
| Fish fingers, mash, creamed spinach | yes | 3 positions |
| Rouladen, red cabbage, potato dumplings | yes | B1; dumplings by air corer and rounding cup (medium) |
| Roast pork, dumplings, red cabbage, gravy | yes | rind scored before roasting; carving on BT; 3 positions and the oven |
| Goose, red cabbage, dumplings, gravy | no | X-04 |
| Asparagus, hollandaise, potatoes, Schnitzel | yes with bought peeled asparagus | all 4 positions; hollandaise binds T3 for 8 min |
| Butter chicken, rice, naan, raita | yes | naan rolled and pan-baked one at a time: slow |
| Burger, fries, coleslaw | adapted | oven fries; burger assembly medium |
| Lasagne, salad | yes | B10 |
| Breakfast for 6: scrambled eggs, 12 pancakes, bacon, porridge | yes, about 45 min | pancakes first (21 min), eggs last; the cook hand is the bottleneck |

---

## 6. Cleaning

### 6.1 Principle and zones

By intent the cell has **no fixed food-contact surface**: food touches only ware. The fixed cell is Zone S.
The exceptions are the three rod tips (they sit inside tool sockets directly above food) — treated as
Zone F and washed in the collar after every use.

| Group | Zone | Area [E] | Cleaned |
|---|---|---|---|
| Ware: vessels, lids, trays, cups, tools, roll heads, fixtures, board discs, mats, rails | F | about 3.5 m² per 4-person meal | wash chamber (the R6 backbone, programme P1), after each meal |
| Rod tips and the lowest 100 mm of the rods | F | 0.04 m² | collar, after each use |
| Rods above that, ram | S, above food | 0.17 m² | collar, at every retraction |
| Ceiling sheet and discs | S, above food | 0.91 m² | lance, squeegee |
| Seam gaps (both walls of 7.3 m × 45 mm) | S, above food | 0.65 m² | top-fed flush |
| Walls, door inner pane, port gate, oven collar | S | 2.4 m² | lance, squeegee |
| Deck with hob plates, bench, gutter, dock shelf, BT pedestal, pegs | S | 1.2 m² | lance, fixed gutter nozzles, squeegee |
| Extraction slot and duct to the condenser | S | 0.3 m² | fixed nozzles weekly (HYG-039) |
| **Fixed Zone S total** | | **about 5.6 m²** | |

Measures that keep the area down (HYG-002): food only on ware; lids on simmering vessels; the air flow
from the seams to the extraction slot behind the hobs; searing only under turret 3. The fixed area is
nevertheless large for a preparation cell, because the hobs are inside it and the ceiling cannot be
shielded.

### 6.2 After every meal

| Step | What | Time | Water |
|---|---|---|---|
| 1 | Leftovers scraped into the gutter (spoon-scraper), pans' fat poured into a fat cup, cooking water removed by the drain wand | 2–4 min | — |
| 2 | Cold rinse of the worst ware in the jet gate (starch, egg, dough) so that nothing dries on (rule R11) | 1–2 min | 2–3 L |
| 3 | Ware out: tools back on their rails or rim rests; 25–45 items relayed to the port | 5–8 min | — |
| 4 | Rods through their collars with 80 °C flush, 60 s after class R work (A0 60), otherwise 10 s | 1–3 min | 1–2 L |
| 5 | Wash-down of the cell (6.3) after every warm meal; after a cold or 1-person meal only the deck round the used stations | 33 min / 5 min | 33 L / 4 L |
| 6 | Ware in the wash chamber: 3 loads for a full menu, 1 for a light meal, 55–75 min each [S, R6] | in parallel | 17–20 L each |

### 6.3 Wash-down of the cell

All ware and all fixtures are out; the cell contains three rods, the pedestal, six pegs and the dock shelf.

1. Squeegees sweep crumbs and peel to the gutter; gutter nozzles flush them to the chip drain (1 min).
2. Each hand takes a rotary jet lance (two Ø 1.2 nozzles, 5 bar, 4 L/min, plus a ring of back nozzles that
   spray up along its own shank). Pass 1: recirculated pre-rinse at ≤ 35 °C, 8 L from the sump, then
   drained. Pass 2: 8 L with alkaline enzymatic detergent at 55 °C, recirculated. Pass 3: fresh water at
   80 °C, 1.5 L/min per lance. Each pass follows a fixed path at 100 mm stand-off, 150 mm swath, 60 mm/s:
   1.9 m² per hand in 3.5 min. The path is a program; coverage is the same every day and is validated once
   with riboflavin (HYG-019, HYG-027).
3. During pass 2 the six seams are flushed one after the other (30 s each, discs turning), during pass 3
   each with 5 s of fresh hot water.
4. Squeegees wipe ceiling, walls and deck (3 min). Each hand wipes the ceiling round its neighbour's rod.
5. Dry-out: ceiling heater on, 60 °C air through the seam inlets for 15 min, extraction running.

Totals [E]: **33 min, 33 L** (8 + 8 recirculated, 16 + 1 fresh), **1.8 kWh** (heating 1.4, pumps 0.1, air
0.3). The final rinse could be kept as the next pre-rinse (−8 L).

**Drying.** Steel at 80 °C flashes dry; the squeegee takes the sheet water; the heated ceiling stays above
the dew point during cooking and drying. The seam gaps are dried by their own air flow. The PEEK scraper
rings and the door gasket stay wet longest (est. 30 min).

**Verification (HYG-026).** Logged per cycle: lance path completed, flow and pressure per lance, liquor
and rinse temperature, flush flow per seam, conductivity of the last rinse water at the drain, lantern and
trough sensors dry. The ceiling cameras compare deck and walls with the clean reference image at 500 lx.
Weekly: a riboflavin solution is sprayed by one lance, the normal pass 3 follows, and the cameras look
for fluorescence under UV LEDs (SM-207). A part of the cell that fails is washed again by a local path
(section 9). Ware is verified in the wash module.

### 6.4 Per meal: water, energy, time

| | Full warm meal for 4 (B1–B3 class) | Light meal (B12) |
|---|---|---|
| Ware loads | 3 × 18 L, 3 × 1.3 kWh | 1 × 18 L, 1.3 kWh |
| Cell | 33 L, 1.8 kWh | 4 L, 0.2 kWh |
| Jet gates, collars, pre-rinse | 5 L, 0.2 kWh | 1 L |
| **Total cleaning** | **about 90 L, 5.9 kWh** | about 23 L, 1.5 kWh |
| Hand time after the meal | 10–17 min of relays and rinsing, then 33 min wash-down | 4 min + 5 min |
| Until everything is clean and dry | 3 h with one wash chamber (three loads in sequence) | 75 min |

These figures miss RES-005 (45 L per reference meal) by a factor of two and RES-001 (4.0 kWh including
cooking) clearly, and PERF-005 (completely clean within 90 min) unless the wash module has two chambers or
is a fast tank washer. Three fifths of the water is the ware, which is the price of "everything is a
passive loose part": a B1 menu soils about 45 items.

### 6.5 Raw meat and ready-to-eat food in one meal (FSF-040, PRP-032)

* Separate instances: red board disc, red mat, red breading trays, red knife, comb, fork and tongs.
* Order: ready-to-eat components first, raw animal food last (SM-208). When the order cannot be kept
  (B1: potatoes after the Rouladen) the red ware leaves the cell first, the bench is rinsed with the lance
  at 80 °C (1 min), and the rods that carried red tools pass the 60 s hot collar flush.
* Raw meat is never carried over open ready-to-eat food (FSF-041): raw work is on the bench and travels
  right to zone 3 only; salads are made on BT and leave to the left.
* The deck is never a food surface. Food that falls on it is discarded.

### 6.6 Peelings, scraps, liquids

Peel, shells and trimmings are swept off the board's rear edge or dumped from the shell cradle into the
**rear gutter**, which runs along the back wall under the rails and jet gates and falls to the chip drain
at x = 550. They never pass over a vessel (PRP-033). Below the drain a perforated **chip box** in
storage-box format (2 mm holes) keeps the solids; wash water runs through it to the sump, a self-flushing
fine filter and the drain pump. The transport system takes the chip box away to the organic waste and the
box washer (request A8). No macerator. Frying fat goes into a fat cup and leaves as ware. Cooking water is
drawn off by the drain wand and mixed with cold water to below 75 °C.

### 6.7 Every crevice, seal and spray shadow

| # | Place | Why it is a concern | What is done | Residual risk |
|---|---|---|---|---|
| 1 | Seam gaps, 4 × 45 mm, 7.3 m | above food; the fixed coaming wall carries the jets and may stay partly dry | jets on the turning rim wall, film and splash on the other; air sweep in operation | **high until a riboflavin test passes** |
| 2 | Collar scraper rings (4) | soil collects under the lip | flush ring directly above, LRU cartridge | medium |
| 3 | Core-shaft seal, hex and bore at each rod tip | dynamic seal and a Ø 4 bore on a food-side surface | collar flush, bore flushed top-down after every fluid use, air purge, LRU tip | medium |
| 4 | Bayonet taper and pins of the rod | contact faces under a tool | exposed and flushed whenever the tool is off | low |
| 5 | Ring of disc surface Ø 45–120 round each rod | shadowed by the lance's own body | back nozzles of the lance; neighbour's squeegee | medium |
| 6 | Underside of the BT umbrella skirt and the boss | upward-facing shadow | four fixed nozzles inside the annulus, drains to the deck | low–medium |
| 7 | Six wall pegs, dock shelf posts | fillets, undersides | lance path goes round each; round bar only | low |
| 8 | Hob plates: silicone joint between glass and deck | joint can lift; burnt-on spill on the glass | flush bonded, no step; detergent pass; a scraper tool is **not** provided | medium for burnt sugar or milk |
| 9 | Door gaskets and sill, port gate seal, oven collar gasket, oven door outer face | static seals with a fold; the oven front must tolerate jets | drained sill; lance angle limited at the gaskets | medium; depends on the oven (request A4) |
| 10 | Camera and light windows | bond line; fogging | heated, flush | low |
| 11 | Extraction slot and duct | grease condensate out of lance reach | fixed nozzles, weekly hot cycle, removable condenser cassette | medium |
| 12 | Gutter, chip drain, chip box, sump, filter | wet, soiled, warm | flushed at every wash, sump emptied and dried, chip box exchanged | low |
| 13 | Ware: roll head worm and bushes, die-grid blade roots, J-slots of the sockets, hook tabs of the pans, tong hinges | the only real mechanisms in the food zone | open construction; wash chamber; grids monobloc; cold rinse within minutes | medium for the grids and the worm |
| 14 | Dry side of the coamings: V-rings, leak-off troughs | water shot over a coaming | trough drain with sensor | low |

---

## 7. Numbers

| Item | Value [E] |
|---|---|
| Wall width | cell 1700 outside (1650 inside); with the oven niche 2270. Two-turret variant: 1150 / 1720 |
| Height use | sump and services 0–850, cell 850–1400, drive room 1400–2000 |
| Servo axes | 17 (3 × 5 hands, ram, turntable); with dock tilter, vibrator and oven door 20 |
| Valves | about 25 (9 rod media, 7 seam diverter, 2 jet gates, gutter, lance feed, boiler, drains, inlet) |
| Load cells | 11 (dock 3, C1 1, W 1, BT 3, hob block 3) |
| Cameras | 3 in the free ceiling corners, plus 2 light windows |
| Dynamic seals at the cell | 3 core seals and 4 collar lip seals behind scrapers; 6 V-rings outside the coamings; 0 in the deck |
| Custom machine part types | about 25 (cell tub, ceiling with coamings, 9 per turret cassette, ram, pedestal, collar and tip cartridges, dock shelf, gate) |
| Tool and fixture types | 46, in about 75 pieces |
| Vessel types with welded features | 15, in about 35 pieces |
| Loose parts in total | about 110 |
| Skills to program (canned cycles with probe, process, verify) | about 38 |
| Handling moves per meal | 110–280 for the 4-person benchmarks, mean 175; 60 for B12 |
| Tool changes per meal | 20–40 at 6–8 s |
| Reliability needed per move | for 98 % of meals (REL-001) at 175 moves: ≤ 1.1 × 10⁻⁴ unrecovered failures per move |
| Peak power | hob block 11 kW nameplate, held to 7 kW by the power manager; oven 3.3 kW; boiler and sump heater 2 kW (not during searing); drives 0.4 kW average, 1.5 kW peak |
| Heat to the room | 0.3–0.5 kW average during cooking after condensation [E, rough] |

**Parts cost estimate** (EUR, ±30 %, without the oven, the wash module, assembly and development):

| Group | Cost |
|---|---|
| Three turret cassettes (each: rings and rollers 250, discs and coamings 600, rod with core shaft 500, Z axis 250, five drives 1000, collar and tip 200, cabling 100) | 8 700 |
| Press ram with C-frame | 700 |
| Turntable with load cells | 600 |
| Cell tub, ceiling, door, port gate (welded 1.4404, polished inside) | 3 500 |
| Frame, drive room, panels | 800 |
| Wash and water system (sump, two pumps, heaters, boiler, 25 valves, nozzles, filter, chip box) | 1 300 |
| Air (filter plenum and fan, extraction, condenser, ceiling heater) | 700 |
| Cameras, lights, load cells, flow meters, leak sensors | 900 |
| Hob block (four OEM induction modules, glass plates) | 1 200 |
| Tools and fixtures (75 pieces; roll heads 350, cassettes 250, others 30–80) | 4 500 |
| Vessels (35 pieces, bought and modified) | 2 400 |
| Control (17 axes, I/O, computer, safety relay) | 2 200 |
| **Total** | **about 27 500** |

The hands alone cost 8 700, in line with D:A's 9 000–11 000 for three turrets.

**Noise sources.** Stick blender at 6000 rpm (short); knife on the board at 2 cuts per second; ram strokes
and the cut-off sweep; turntable spinning a basket at 600 rpm (imbalance); belts of six disc drives; air
(130–180 m³/h in total); and the wash-down, where three 5 bar lances play on 5 m² of stainless sheet for
10 min. The cell is a steel drum: without damping mats on the dry side the wash will probably exceed the
48 dB(A) of NOI-002. Not estimated in numbers.

**Two-turret variant.** T1 with dock and BT, T2 over the hob block, no bench (tray work on cold hob
positions, flat work on BT): 12 axes, 1150 inside, about 23 000 EUR. It loses the parallel hand during
cooking: B2 and B6 exceed their limits, B1 grows by about 15 min [E]. It is a fallback for narrow kitchens,
not the proposal.

---

## 8. Coverage estimate

Method: the requirement's own list of eight meals that fall out (5.4), plus every corpus meal whose hard
operation has no mechanism in section 4, under purchase scenario S1 (MEAL-012). This is a reading of the
corpus rows against the operation table, not a walk-through of 248 meals.

**Meals that fall out**

| Meal | Reason |
|---|---|
| CK11 doughnuts, DM21 goose, DS13 ice cream, BF08 waffles, AS05 sushi, BK06 pretzels, CK08 Black Forest cake, BK02 sourdough | excluded by the requirements (X-01, X-04, X-07, X-09, X-11, X-12) |
| DM12 Kohlrouladen | whole cabbage leaves cannot be separated (LSP); rolling itself would work |
| AS08 spring rolls, AS09 gyoza, IN07 samosa | folding, pleating and sealing thin wrappers round a filling: no mechanism (part of gap G4) |

12 of 248 fall out: **95.2 % on paper**, exactly at the limit, with no reserve.

**Meals that depend on a medium-confidence mechanism**

| Mechanism | Meals at stake | Examples |
|---|---|---|
| Pan-pair flip | about 5 | BF06, SP11, DS05, thick omelette, Rösti |
| Mandrel or mat rolling; untied braise | about 12 | DM02, MX03, CK12, CK13, bacon wraps, enchiladas |
| Unmoulding | 11 | CK01–CK07, CK16, DS03, DS08 |
| Open-hand assembly | about 10 | US01, US02, US08, MX02, BF11, BF14, AS06 |
| Egg station (where liquid egg cannot replace it) | 5 | BF03–BF05, BF12, BF14 |
| Air-corer forming, rounding | about 12 | DM01, DM10, ME09, SD07, SD21, CK14 |

If every one of these mechanisms works, coverage is 95 %. If each fails in a quarter of its meals, 10 to
14 more fall out: about **90 %**. My estimate is **90–95 %, most likely 92 %**, below the requirement
until the medium items are proven. The source documents claimed 93–96 % (A:A2) and 90–96 % (D:A); the reach
correction of 2.2 does not remove any operation, it costs time.

**Other coverage requirements**

* MEAL-004 (every category ≥ 85 %): missed in the Asian category (3 of 12 out: 75 %).
* MEAL-005 (the brief's meals): all have a mechanism; Rouladen depend on the untested securing.
* MEAL-009 (≥ 90 % from whole produce): not met. Onion peeling (52 % of meals) has only an upgrade slot;
  herb stripping, bean and sprout trimming in quantity and pepper deseeding are slow or uncertain.
* MEAL-013 (adapted methods ≤ 10 %): the requirements themselves adapt 20 meals (deep-frying 10, stir-fry 7,
  skewer and skimming 3 = 8.1 %). K1 adds roast chicken without trussing and carved as parts (DM20), whole
  fish carved by the guest (FI07), and, if packing is judged not to be "securing", the Rouladen family
  (up to 4). Total 22–26 meals, **8.9–10.5 %**: at the limit.
* PERF for 6 persons: not shown. Per-piece operations scale linearly; B3 and B6 are already at their
  4-person limits.

---

## 9. Failure modes and recovery

| Failure | Detection | Recovery | Human needed? |
|---|---|---|---|
| Tool not picked up, or dropped | Z motor current shows no tool weight; ceiling camera | retry twice with a 0.5 mm search spiral; a tool lying on the deck is taken by another hand's tongs and sent to the washer; a spare is used | no, unless it fell into a full pot: then tongs, else the batch is discarded |
| Tool does not release (soil in the socket) | yaw torque at release | flush the socket from inside through the bore, retry; park the hand with the tool on and continue with two hands; washer at the end of the meal | no |
| Stub does not lock, vessel slips from the roll head | roll torque and weight signal | worm is self-locking, so nothing swings; lower, re-seat, retry; a dropped vessel of ≤ 4 kg falls ≤ 250 mm onto the deck: contents discarded, deck rinsed | no; the meal may be lost |
| Jam in a die cassette | ram force above limit, or no stroke | retract; push-out foot cycles twice; cassette changed for a spare and sent to the washer; piece diced by knife instead | no |
| Blade or grid wire broken (PRP-035) | camera check of blade and grid after every cutting cycle; cut force signature | batch discarded, tool quarantined | blade exchange at the next service (HUM-007) |
| Food dropped on the deck | camera | discarded, swept to the gutter; dosing repeated by weight | no |
| Food stuck: patty in the air corer, dough in the bowl, pancake in the pan, cake in the tin | weight not transferred; camera | second air pulse or tap; scraper by the second hand; pancake loosened with the wide turner before the flip; a cake that tears is served as it is or discarded by rule | no |
| Egg with shell fragments or broken yolk | camera on the inspection saucer | saucer emptied to the gutter, next egg | no |
| Roulade opens while searing | camera | re-rolled with tongs and pinned | no |
| Pan pair does not hook, or separates | weight and roll torque during the first 10° of lift | set down, re-seat once, otherwise turn the item with the wide turner (may break) | no |
| Rod collar leaks | lantern sensor | finish the meal; collar cartridge exchange | service, 15 min |
| Seam: water over the coaming | trough sensor | wash continues with reduced lance pressure near that seam; if repeated, V-ring or flush check | service |
| Turret axis fault | following error | the other two turrets take over within their reach. With T1 or T2 down most meals run slower; **with T3 down only the left hob column (H1, H2) can be served, by T2, and the oven not at all** | service; limp-home covers roughly half of the menus [E] |
| Part fails cleaning verification | camera or tracer check | cell: local lance path repeated once, then flagged; ware: rewashed by the wash module, spare used | only after a repeated failure |
| Power loss | — | Z brakes hold the rods, the worm holds tilted vessels, hobs off; on return each hand sets its load down, state is rebuilt from the cameras and the weights; open food beyond its time limit is discarded (UC-12) | no |
| Human reached into the cell (jam clearing, service) | door interlock | all rods retract fully into the ceiling and the ram rises before the door unlocks, so the open cell contains no moving part (SAF-033, SAF-035); wash-down before food contact resumes (HYG-007) | — |

---

## 10. Top risks, each with the cheapest experiment that confirms or kills it

| # | Risk | Consequence if true | Cheapest experiment | Kill criterion |
|---|---|---|---|---|
| 1 | The coaming gap cannot be flushed clean, or drips after the wash | 7.3 m of uncleanable gap above food: the concept fails HYG-004/-019 and has no fallback inside itself | One seam at full size: a laser-cut Ø 500 disc on a lazy-Susan bearing in a transparent acrylic coaming with the flush groove, a garden pump, a fan. Soil with flour paste and sprayed oil, dry 2 h, flush, inspect with riboflavin under UV. 3 days, < 500 EUR | any fluorescence on either wall after the standard flush, or any drop leaving the gap later than 10 min after it |
| 2 | With rod-axis reach of Ø 400 and no overlap, relays and tool changes make meals too slow and too many moves fail | PERF-001 and REL-001 missed; for 6 persons certainly | (a) Half a day: a full-size plywood deck with the real vessels; three people, each holding one stick through a Ø 400 hole in a board at ceiling height, play B3 and B1 against a clock. (b) One week: a kinematic script that runs the B1–B3 step lists with real axis speeds and collision checks | B3 for 4 persons above 50 min, or more than 250 moves, with no obvious re-layout |
| 3 | The pan pair turned in the air leaks fat, does not hook with slightly warped pans, or tears pancakes | every whole-pan item falls back on a turner (corpus difficulty 5); about 5 meals | Two identical Ø 280 pans with tack-welded tabs and half stubs on a hand crank: 8 pancakes, 2 omelettes, 1 Rösti with 10 g of fat. 1 day | fewer than 9 of 11 intact, or fat leaving the pair |
| 4 | An untied Roulade opens during the braise; the mandrel does not grip a wet slice | the brief's named dish needs pins, or fails | By hand: slotted Ø 12 rod, 8 Rouladen rolled along the slice, packed in a Ø 260 pot, seared, braised 100 min. 1 day | more than 1 of 8 open, or the mandrel slips on more than 1 of 8 |
| 5 | Bayonet or stub pick-up fails on soiled sockets | a stopped meal every few days at 30–45 changes per meal | Socket and spigot in a CNC mill or drill press, 1000 cycles, socket smeared with flour paste, then mince, then dried starch. 3 days | more than 1 failure in 1000 without cleaning in between |
| 6 | The roll head's open worm gear holds soil or wears into the food | the wrist, on which reach, flipping and pouring rest, is not acceptable as ware | One head (printed frame for the test, real worm and PEEK wheel), soiled with egg and mince, dried 1 h, household dishwasher, ATP swab and inspection; then 20 000 roll cycles under 4 kg and a particle check. 1 week | ATP above the pass limit in the mesh, or visible wear debris |
| 7 | Rod collar and core seal do not survive wet, starchy, greasy strokes | leaks into the drive room; the only dynamic seals on the food side fail early | One rod rig: 10 000 strokes and 100 h of core rotation with starch water and oil on the rod. 2 weeks unattended | lantern wet before 10 000 strokes; core seal leaking outwards |
| 8 | The lance leaves shadows on the ceiling round its own rod and behind the pedestal | HYG-019 failed after selection | Same mock-up as risk 1 plus a lance on a stick through the rod hole, following the planned path by hand; riboflavin | any shadow that a path change does not remove |
| 9 | 38 skills with vision and force thresholds take years, not months | coverage on paper only (the weakness both inventors named) | Implement the three hardest on a single-turret rig: spit peeling with patch detection, Roulade rolling, egg station with inspection. 6–8 weeks | none reaches 95 % first-time success |
| 10 | Water, energy and wash capacity: 45 soiled items and 5.6 m² of cell per menu | RES-001, RES-005 and PERF-005 missed by a factor of about two | Desk study with the wash-module explorer: racks for the K1 ware set in a 480 × 480 × 400 chamber; count loads for B1–B3 | more than two loads per full menu with no faster washer in the architecture |
| 11 | Grease aerosol and steam deposit on the heated ceiling and inside the gaps in spite of the air sweep | daily wash becomes a scrubbing task; smell | Sear 4 steaks under a heated steel plate with a 4 mm gap and 0.3 m/s outflow, 400 mm above the pan; weigh and inspect the deposit. 1 day | visible film inside the gap after one session |
| 12 | The air corer does not release sticky mince | forming falls back on slab and ring cutter (slower) | A Ø 60 tube and a bicycle pump, 600 g of Frikadellen mass. 1 hour | fewer than 9 of 10 portions released by one pulse |

## 11. Improvements found, and what changed from the catalogue definition

### 11.1 Changes (each is a deviation from K1 as defined in the catalogue)

| # | Catalogue or source said | This document | Why |
|---|---|---|---|
| 1 | Reach Ø 470–480 for Ø 470–500 discs; two rods pinch large objects | Reach Ø 400 for Ø 500; circles never overlap; one-hand carrying; layout built round that | the drawn geometry puts the rod outside the inner disc (2.2) |
| 2 | Flush ceiling with PTFE-lip labyrinth or inflatable seals in the seam | Open coaming gap, air-swept in operation, flushed from the top in the wash; V-ring on the dry side; the seams are the cell's air inlets | takes the dynamic seal and its debris out of the food zone; gives the gap a defined cleaning flow |
| 3 | One rod with a welded roll elbow and a Ø 20 seal in the cell | Every rod is plain and has a coaxial core shaft; the wrist (roll head) is a passive part of ware | rods retract completely through their collars; all three hands are identical and can flip, pour and relay; the offset of the wrist repairs the reach |
| 4 | Push rod through the rod (three-media interface) | Core rotation instead of a push rod, plus the fluid bore | one rotary lip seal instead of a sliding seal at the tip; also drives the blender |
| 5 | Turret spins as a planetary mixer | Discs limited to ±190°; the bowl turns on the turntable | no slip rings or rotary water joints on the discs |
| 6 | Turning and tilting board; separate spin chuck | One turntable pedestal on the zone boundary that does not tilt: board, relay between two hands, carousel under the ram, mixing and spin chuck | a tilt axis through the deck is not a round penetration; one axis instead of three |
| 7 | 3 kN quill, or a press bracket | Fixed ram in the ceiling triangle between two turrets; die cassette on wall pegs; cut-off by a hand-held blade | keeps press load out of the seams; no cut-off actuator |
| 8 | Flip bracket or tip bar on the wall | Hermaphroditic pan pair with half stubs, turned in the air by the roll head | a fixed bracket would be in the wrong zone for the cook hand; no vessel position is lost |
| 9 | Holsters with local wash, or magnet-parked utensils | Two tool rails that are ware; cooking tools ride on the rim of their vessel; spin-rinse in a jet gate | holsters are fixed structured surfaces in the cell; there is no room above the hobs |
| 10 | Pocket band or mat roll for Rouladen | Slotted mandrel rolling along the stationary slice | one hand, one trivial part; no band to drive or wash |
| 11 | Slab and ring cutter, or press-pot extrusion for patties | Air corer: a plain tube, ejected by an air pulse through the rod bore | no mass transfer, no trimmings, 8 s per patty |
| 12 | Board tilts and is scraped into the pot; hands carry vessels | Everything travels between zones in 1.5 L prep cups with a stub | follows from change 1 |
| 13 | Side-wall lathe spindle as an option | Not included | the roll head is a hand-held horizontal spindle |
| 14 | Ceiling sloped 5° (A:A2) | Horizontal, heated, wiped | discs cannot be sloped to a gutter |

The most valuable of these is change 2 together with change 3: the concept's acknowledged weak point, a
large dynamic seal above open food, is replaced by an open gap that can be given air and water on purpose,
and the rod becomes a plain cylinder that leaves the cell completely.

### 11.2 Improvements not yet taken, and what I would borrow

* **Breading by flipping a locked tray pair** (SM-093, from the vessel lens): two GN 1/4 trays with the same
  half stubs as the pans, turned and shaken by the roll head; the cutlet is never gripped. Probably better
  than the fork method; one more pair of welded trays.
* **Pots that turn on their hob against a hung scraper** (SM-180, SM-225): four more axes and four large
  deck seals, but continuous stirring would no longer bind the cook hand. The single most useful addition
  for 6 persons.
* **A fast tank washer** in place of the 60-minute chamber (K6, SM-201): K1 soils more ware than any
  concept with fixed stations, so it gains most from a 3–4 min cycle.
* **Crust-freezing of meat slices** (K7, SM-240) or interleaving at ingestion, for the unsolved
  singulation of slices that stick together.
* **A belt and cross blade** (K3, SM-017) would slice and carve better than knife and comb. Excluded by the
  concept; a die cassette with a slicing harp under the ram is the in-concept substitute for firm produce.
* **A piston tube** (K5, SM-117) as the former cassette, filled by the air corer, for masses that must not
  be smeared through a bowl transfer.
* **A ware hatch in the deck** above an under-deck wash chamber with a rising rack (top-loading), so that
  soiled ware leaves zone 2 straight down and not by three relays to the left port.
* **The front door as serving hatch**: because all rods retract into the ceiling, the open cell is free of
  moving parts. Plates filled on the bench could be taken from there. It costs a wash-down after each
  serving (HYG-007) and is an architecture decision.

## 12. Open issues and requests to the architect

### 12.1 Open issues

1. The layout was fitted by hand to a rod-axis coverage of 42 % of the deck. It has not been checked for
   collisions between two rods with tools over the turntable, nor for the reach of the oven rack. The Z
   stroke has no margin against the 2000 mm height.
2. Six-person times were not walked through; B3 and B6 are at the 4-person limit already.
3. The bench has no scale. Weighing is at the dock, C1, W, the turntable and the hob block; the hob block
   weighs its four positions as one sum.
4. The drain wand sucks cooking water through a rod bore that also doses drinking water into food. A hot
   flush after each use is planned; whether this is acceptable, or the wand needs its own path, is open.
5. Warm-holding (COK-017) uses the oven at 70–80 °C when it is free, otherwise a lidded vessel on a hob at
   low power. There is no warming drawer in reach of the hands.
6. Chilling, resting and proofing in cold storage go out and in through the single port.
7. I assumed a full wash-down after every warm meal because of grease on the ceiling; HYG-034 asks only
   for daily. With one wash-down per day the cell's share falls from 33 L per warm meal to about 17 L.
8. Gaps of the catalogue that K1 does not close: onion peeling (G1, only a test slot), herb stripping (G2),
   flat pockets and folded wrappers (G4), bone-in carving (G5), whole cabbage leaves (G7), trussing (G8),
   slices stuck together (G9). G3 (open-hand assembly) and G10 (trimming small items) are covered at
   medium confidence and slowly.
9. Programming effort for about 38 skills is not estimated.
10. Noise of the wash-down and of chopping is not estimated.
11. Storage volume for about 110 loose parts plus a second set of the frequent ones, and the racks that hold
    them in the washer, are not designed.
12. Plating is outside the scope; the hands could do it (ladle, tongs, turner, pipette under a ceiling
    camera) if plates reach the bench.
13. The burnt-on spill on a hob plate has no mechanical remover.

### 12.2 Requests to the architect

| # | Request | Collides with |
|---|---|---|
| A1 | **Vessel standard**: two rim ears (span 290) on every vessel; a horizontal lift stub Ø 22 × 40 on every vessel up to 4 kg gross, on cups, lids, baskets, rails and roll heads; half stub and hook tab on frying pans, turn-out plates and tin carriers; a V-saddle tool rest on pot rims. Hob, oven rack, wash racks and store must clear these features. | one vessel interface for all modules |
| A2 | **Box**: lid with a knob that a stub socket can take, or boxes delivered open; wiper insert for spice boxes; egg-tray insert; a perforated chip box in box format. No other change: K1 reaches into a plain open box and also uses the common dock tilter. | BOX-005, BOX-007 (catalogue X1, X4, X5) |
| A3 | **Port**: one lift-gate 380 × 300 in the left end wall, with the dock shelf inside the cell. The transport system must bring and take not only boxes but ware: rails 450 long, trays 400 × 300, vessels to Ø 360. A second way out for soiled ware (deck hatch to the wash module, 11.2) would remove about 70 relay moves per full menu. | TRN-002; catalogue X8 |
| A4 | **Oven**: compact combi-steam oven turned by 90° at the right end, its mouth in the cell wall. Needed: a front that tolerates wash jets (IPX5) or controls behind a sealed cover, a driven door that does not swing into the hob block (side-hinged or sliding), telescopic rack with a front bar at deck + 250, local control without a button press (COK-023). This adds 570 mm of wall width. | standard built-in installation; COK-020, COK-023 |
| A5 | **Hob block**: four OEM induction modules under glass-ceramic plates bonded flush into the deck, on three load cells; front positions Ø 280 at 3.5 kW, rear Ø 220 at 2.0 kW, columns bridgeable. Glass-ceramic below vessels in Zone S needs a ruling under HYG-018. | HYG-018 |
| A6 | **Ingestion**: meat slices interleaved or laid singly; onions and garlic peeled; herbs frozen chopped; stowed packs delivered opened in a carrier box at the dock. | DEC-3, catalogue X6 |
| A7 | **Wash module**: envelope 480 × 480 × 400 must take the rails, the Ø 360 pan and the trays; a disinfecting programme for class R ware; capacity of three loads per full menu within 90 min (two chambers or a fast washer); clean store for the full ware set. | scope of D7; RES-001, RES-005 |
| A8 | **Waste**: the transport system exchanges the chip box; a fat cup is emptied by the wash or waste module. | — |
| A9 | **Utilities at the module**: cold water with EN 1717 separation (the rod bores dose drinking water), 6 L boiler at 80 °C, 5 bar pump, drain with lift; three-phase supply; filtered supply air 30 m³/h at +50 Pa for the seams and 100–150 m³/h extraction with a condenser. | UTL-001, ENV-010 |
| A10 | **Plating and serving**: a decision on whether plates come to the bench and the hands plate, and whether the front door may serve as the hatch (11.2). | SRV, HYG-007 |
| A11 | **Adapted-method ruling**: whether Rouladen packed seam-down without pins count as "secured by the machine" (MEAL-005, UO-42), and whether patties formed as pressed cylinders are accepted. | MEAL-013 |

### 12.3 Verdict of the explorer

K1 can do on paper what its inventors claimed for it — it is the generalist, every benchmark has a path,
and a missing operation is one more passive part — but it is weaker than both source documents said, for a
reason neither of them saw: a rod in a disc-in-disc turret reaches 42 % of its zone and never meets its
neighbour. The design above repairs that with a wrist that is ware, a turntable on the zone boundary and
cups that travel; the repair works at the price of 110–280 handling moves per meal, about 110 loose parts,
17 axes, and a wall width of 2.27 m with the oven. Its three largest weaknesses are, in this order: the
handling count and serial hands that follow from the reach geometry; 7.3 m of rotating seam above open
food, improved but unproven; and the cleaning bill of an all-ware concept inside a 5.6 m² wash-down cell,
which misses the water, energy and turnaround requirements by about a factor of two.
