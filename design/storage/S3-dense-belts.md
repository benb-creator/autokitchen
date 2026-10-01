# S3 — Dense grid with belts: "docked belt levels"

Storage design round, design S3 (customer's variant (c), "with belts"). Inputs: `00-storage-brief.md`,
`DECISIONS.md`, `requirements/requirements.md` (BOX, STO, CLD, TRN, CAP 6.2, PHY-004), `research/03-storage.md`
sections 1–4 and 6–7, `design/prep/concepts/K9b-combined-simplest.md` section 2 (hand-over interface).
Tags: [C] calculated, [E] estimate, [U] unverified/must be measured.

**Result in one paragraph.** Every shelf level is a passive belt conveyor without a motor, two box rows deep. A lift
in a 200 mm front aisle carries a short belt (the "shuttle belt"). When the lift stops at a level, a blade on the lift
drops into a slotted hub on that level's front roller (the drive coupling of a laser-printer toner cartridge), so the
lift's single belt motor drives the shuttle belt and the docked level belt together. The machine therefore has
**2 motors** for the whole 650 mm column. Capacity is ≈ 110 nominal positions (≈ 90–95 in real mixed use). The
worst-case retrieval takes 18 s. The honest catch: in a 600 mm deep cabinet the lift aisle is unavoidable, so the
belt grid is **not denser than an aisle shuttle** (research A). It only saves one motor, and it pays for that with
13 belts.

---

## 1. Principle and geometry

### 1.1 Principle (3 sentences)

1. Boxes stand directly on 13 stacked, motor-less belt levels, each 2 rows deep. A row is the boxes standing side by
   side across the full width: any mix of GN 1/9, 1/6 and 1/3, all 176 mm deep, up to 11 units of 54 mm = 595 mm.
2. A lift in the front aisle stops at a level, and a blade on the lift engages that level's slotted roller hub. One
   motor then turns the shuttle belt and the level belt together, so the front row moves onto the shuttle belt (or
   the shuttle's row moves into the level and pushes the level's front row back).
3. The lift takes the row to the exit at the top, where the transport (K9b gallery, z 2000–2200) picks the wanted box
   from above through a port. The port's shutter is opened by the lift's last 30 mm of travel. A box in a back row
   costs one extra move: the front row is parked in any level that has a free row slot.

### 1.2 Belt schemes considered, and how many drives each needs

| # | Scheme | Drives (650 column, 13 levels) | Verdict |
|---|---|---|---|
| a | Literal sliding puzzle: every cell a cross-belt (X and Y), empty centre lane, front picker | 3 × 3 cells × 2 × 13 ≈ **234** (row/column belts instead: ≈ 80) | rejected: drive count, wiring in every cell, jams |
| b | Gravity flow lanes (tilted roller tracks, 3–4°), front escapement, re-feed lift at the back | lift front + lift back + 1 escapement per lane | rejected: two 200 mm shafts leave 170 mm of a 570 mm depth, i.e. one box per lane; the tilt costs 20–25 mm per level [C]; loose rollers trap crumbs. It works only for lanes ≥ 1.5 m long |
| c | Two-level loop lane (upper run to the front, lower run to the back, transfers at both ends) | 2 lifts or 2 transfers per loop | rejected: same depth problem as b. The end transfers must hold the longest box (325 mm) |
| d | Horizontal racetrack per level (row 1 runs left, row 2 runs right, cross transfers at both ends) | 4 motions per level (4 couplings) | rejected: it removes digging, but digging here costs only one row move. It needs a free hole of one L width (6 of 22 units) per level |
| e | Same geometry as chosen, but one motor per level belt | 13 + lift + shuttle = **15** | rejected: 13 motors and their cables inside the grid (and inside the cold, see 7) |
| **f** | **Chosen: passive level belts, docked drive on the lift** | **lift Z + shuttle/level belt = 2** | the shutter is driven by the lift's over-travel, so it needs no actuator |
| g | Option on f: the transport hoist (C4) acts as the lift if its stroke reaches 1.9 m | 1 (belt motor on the hoist head) | depends on C4, not assumed |

Why a front aisle at all. Under the customer's density rule ("only box height plus leeway per layer") a box can leave
a level only horizontally. Whatever receives it, lift or column, must therefore be free for a full box length in the
exit direction. If the box exits along the 176 mm side (the dimension that S, M and L share, `research/03` 2.4), that
free length is 176 mm plus gripper clearance, about 200 mm. Exiting along the long side would need 325 mm for an L
box. In 570 mm of inner depth this leaves exactly **two rows**, whether the 200 mm sit in front (this design) or
between two rack faces (aisle shuttle A). This is the main geometric finding of S3 (see 4 and 8).

### 1.3 Dimensioned views

Coordinates: x 0–650 from left to right seen from the front, y 0 at the front face and 600 at the back, z from the
floor. Inner width 614 (side walls 18 mm, hollow: lift guide channel, lift belt, slot hubs).

**Front view** (service door removed, lift parked below the exit):

```
  z     x: 0 18                                                        632 650
 2200   +----------------------------------------------------------------+
        |  transport gallery (C4; not part of S3)                        |
 2000   +=====[ exit port 600 x 196 over the aisle, sliding shutter ]====+
        |  exit position: shuttle belt top z 1828, box tops <= z 1990    |
 1920   +--+----------------------------------------------------------+--+
        |  | 13  L-150 (325)                 | M-150 (162) |S-100(108)|  |  pitch 195
 1725   |  |----------------------------------------------------------|  |
        |  | 12  L-150 (325)                 | M-150 (162) |S-100(108)|  |  pitch 195
 1530   |  |----------------------------------------------------------|  |
        |  | 11  M-100 (162) | M-100 | M-100 | S-100 (108)            |  |  pitch 145
        |  |  :              6 levels z 660-1530                      |  |
        |  |  6  M-100       | M-100 | M-100 | S-100                  |  |
  660   |  |----------------------------------------------------------|  |
        |  |  5  S-65 | S-65 | S-65 | S-65 | S-65   (or 3 M-65 + S)   |  |  pitch 110
        |  |  :              5 levels z 110-660                       |  |
        |  |  1  S-65 | S-65 | S-65 | S-65 | S-65                     |  |
  110   |  +----------------------------------------------------------+  |
        |  plinth: stainless drip tray + leak sensor, lift motor with    |
        |  brake on a cross shaft, hand-crank socket, 1 L crumb bin       |
    0   +----------------------------------------------------------------+
         left wall: guide channel + lift belt   right wall: guide channel + lift belt
                                                 + slot hubs of all 13 levels
```

**Side view** (section at x 325, front on the left):

```
  y:  0  15                          215 230               408               586 600
 z    +--+----------------------------+--+-------------------+-----------------+--+
 2000 |  |<== shutter (opens at lift over-travel z 1828-1858)  |                    |
      |D |  EXIT: lift + row          |  | lvl 13  row 1      |  row 2          |B |
 1920 |O |                            |  +-------------------------------------+A |
      |O |  aisle 200: lift guides    |  | lvl k   row 1      |  row 2          |C |
      |R |  in both side walls        |  | [box 176]          |  [box 176]      |K |
      |  |  +----------------------+  |  |o==================================o|  |
      |  |  |o=====shuttle belt===o|-blade->[slot hub on level front roller]  |  |
      |  |  |  motor, sensors      |  |  |  level belt loop, Ø 18 noses,      |  |
      |  |  +----------------------+  |  |  slider bed inside the loop        |  |
  110 |  |                            |  +-------------------------------------+  |
      |  |  plinth                    |                                          |  |
    0 +--+----------------------------+------------------------------------------+--+
         front door (service, no tools)   transfer gap ≈ 10 mm between noses
```

**Top view** (plan at one level):

```
  y   x: 0 18                                                    632 650
    0 +--+--------------------------------------------------------+--+
      |  |  service door 15                                       |  |
   15 |  |  front fence 10 high | 10 mm finger gap                |  |
      |  |  LIFT: shuttle belt 600 x 196  (one row fits)          |  |
      |  |  guide rollers in the side-wall channels at y 100-130  |  |
  215 |  |== shuttle rear nose ===== gap 10 ===== level front nose[O] slot hub Ø 30
  230 |  +--------------------------------------------------------+  |  (right wall)
      |  | row 1 (y 230-408): L 325 | M 162 | S 108  = 595        |  |
  408 |  |--------------------------------------------------------|  |
      |  | row 2 (y 408-586): M 162 | M 162 | M 162 | S 108 = 594 |  |
  586 |  +--------------------------------------------------------+  |
  600 +-----------------------------------------------------------+--+  back panel 14
```

Height budget [C]: plinth 0–110; 5 × 110 + 6 × 145 + 2 × 195 = 1810 → levels z 110–1920; top cover 1920–2000
(shutter linkage, port). Level pitch = box with lid + 21 mm belt deck + 8 mm clearance: 65 mm box (77 with lid)
→ 110; 100 mm box (112) → 145; 150 mm box (162) → 195. Level heights are set at assembly by hooking the level
brackets into the perforated side walls (`research/03` 2.4). A household with other needs re-pitches
levels during service. That is the only "hardware" change, and the box mix within a level is free (STO-006).

### 1.4 Mechanism details

* **Level** (13 identical modules, 600 × 380 × 21 mm): an endless food-grade homogeneous PU flat belt (1.4 mm, blue,
  EU 10/2011 and FDA, loop ≈ 820 mm) with a **V-guide on its underside** in a groove of the slider bed. The guide
  tracks the belt, because a belt wider than it is long cannot be tracked by crowned rollers. The slider bed is
  1.5 mm stainless with bent stiffening channels inside the belt loop. Front nose: a Ø 17.5 stainless drive roller,
  lagged. Its effective diameter with the belt (18.9 mm) makes **one row pitch (178 mm) = 6 half-turns** [C]. Rear
  nose: a Ø 17.5 idler with an eccentric quick-release tensioner. On the right end of the front roller shaft sits
  the **slot hub**: a Ø 30 disc with a diametral slot 7 mm wide, open at both ends and chamfered. A spring-ball
  detent holds the slot vertical every 180°. The detent also locks the level belt, so a level can move **only**
  while the lift is docked.
* **Lift**: an aluminium/stainless frame 614 × 200 × 50 with four plastic guide rollers (igus or similar,
  dry-running) in two vertical channels in the side walls. It hangs on two HTD-5M belts in the side-wall cavities.
  These are driven from the plinth by one cross shaft, a closed-loop NEMA 23 stepper, a 3 : 1 reduction and a
  spring-applied power-off brake. The lift has a hand-crank socket.
* **Shuttle belt on the lift**: the same belt and noses as a level, 600 × 196. A closed-loop NEMA 17 stepper with a
  gearbox drives the shuttle's rear-nose roller and, through a 1 : 1 GT2 loop, the **drive blade** (5 mm stainless
  tongue, 28 mm tall, on a shaft along x at the right end, y 222). Both surfaces therefore run at exactly the same
  speed. While the lift travels, the blade is held vertical (index Hall sensor) and slides through the open slots of
  all the levels it passes. When the lift stops at a level, the blade sits in that level's slot, so docking needs no
  extra motion. The blade is mounted on a sprung x-slide with a switch: if a hub is not vertical, the blade is pushed
  aside instead of jamming, and the lift stops on following error.
* **Exit port and shutter**: a 600 × 196 opening in the top cover over the aisle, closed by a spring-returned
  stainless slide (gaps < 1 mm, STO-008). A bell crank is struck by the lift above z 1828 and opens the slide during
  the last 30 mm of lift travel. The port is therefore open only while the lift is at the exit.
* **Front**: one full-height gasketed service door (or two, split at z 1100), opened without tools; a switch stops
  both motors when it opens (power-off is safe, see 5.4).

---

## 2. Box standard

| Feature | S3 requirement | Why |
|---|---|---|
| Family | GN 176 family (`research/03` 2.4): **S = GN 1/9** 108 × 176, **M = GN 1/6** 162 × 176, **L = GN 1/3** 325 × 176; depths 65 / 100 / 150 (no GN 1/9-150: S-100 is used in 150 levels) | rows tile in 54 mm units; the 176 mm side is the travel direction for every size |
| Orientation in the store | **176 mm side along y** (direction of travel), the 108/162/325 side along x | all rows have the same pitch, so the lift aisle is 200 mm deep instead of 340 |
| Material | PP or Tritan, flat-bottomed, −40 to +95 °C (BOX-009, −18 °C) | dishwasher and freezer |
| Bottom | flat and smooth, standing ≥ 120 mm long in y (GN tapered bottoms ≈ 150 × 135 for M [U]), no feet or ribs that catch in the 10 mm transfer gap | the box crosses the gap between the noses |
| Rim/flange | normal GN flange on all four sides. The **transport grips under the flange on the two y-faces** (front and back), with fingers ≤ 4 mm thick in the 10 mm gaps the shuttle leaves fore and aft | the x-neighbours touch flange to flange |
| Lid | flat press-on gasket lid without clips, sitting on top of the flange (Cambro seal-cover type) | a proud lid is detected by the height light barrier on the lift (5.2) |
| Friction box/belt | PP on PU, μ ≈ 0.4 [E] > the 0.1 g needed at 1 m/s² | no slip under acceleration |
| Tag (BOX-006) | **NFC tag** (NTAG 21x, −40…+85 °C) moulded or welded into a closed pocket under the **bottom centre**, outside zone F; plus a DataMatrix etched on both y-faces for the transport camera | read through the 1.4 mm shuttle belt by an antenna strip (5.2) |
| Bayonet stub (K9b 2.5) | **Conflict:** a stub Ø 22 × 40 protruding from a side wall breaks dense rows (every row would lose ≈ 40 mm). S3 needs the stub **inside the flange envelope**: either a clip-on stub collar that the lid station fits when it opens the box (the cell only handles opened boxes, K9b 2.12), or a stub recessed into a moulded pocket of a custom box (BOX-011 deviation) | interface issue for C4/K9b |
| Empty-box reserve (CAP-023) | stored **nested**: 3 empty S-65 in one S-100 slot, 3 empty M-100 in one M-150 slot [E] | reserve at a third of the positions |

Off-the-shelf GN boxes work unchanged, apart from the tag pocket and the stub question. No rail-specific flange
tolerance is needed: boxes are conveyed by their bottoms, not hung by their rims. This is an advantage over hanging
designs, because research/03 open issue 1 (real flange width and stiffness) does not gate S3.

---

## 3. Retrieval and put-away

Motion parameters [E]: lift 0.6 m/s, 1.5 m/s² → full stroke 1.72 m in 3.3 s, neighbouring level in 1.0 s
including settling. Row transfer: 178 mm at 0.3 m/s, 1 m/s² → 0.9 s, plus indexing to the next half-turn and a
sensor check → **1.3 s**. NFC read of a row: 0.5 s. Shutter: included in the over-travel (0.3 s).

### 3.1 Worst-case retrieval

The worst case is the target in **row 2 of level 1** (bottom, back), with the store full: 25 of the 26 row slots
are used, and the only free slot is at **level 13** (top, far end).

| # | Move | Time [C/E] |
|---|---|---|
| 0 | Lift parked empty at the exit (the shutter closes as soon as the lift drops 30 mm). The controller picks the plan: row 1 of level 1 is the blocker | — |
| 1 | Lift travels z 1828 → level 1 (the blade slides through 12 slots) | 3.3 s |
| 2 | Docked. Motor turns −6 half-turns: row 1 moves onto the shuttle belt, row 2 moves forward to the front of level 1, and level 1's back slot is now free. NFC read of the row | 1.3 + 0.5 s |
| 3 | Lift travels to level 13 (the free slot) | 3.3 s |
| 4 | Motor turns +6: the shuttle pushes row 1 into level 13. Level 13's own row moves to its back slot | 1.3 s |
| 5 | Lift travels back to level 1 | 3.3 s |
| 6 | Motor turns −6: row 2 (with the target) moves onto the shuttle. NFC read confirms the target (STO-009) | 1.3 + 0.5 s |
| 7 | Lift travels to the exit; the over-travel opens the shutter | 3.3 + 0.3 s |
| | **Box ready for the transport** | **≈ 18.4 s** |
| 8 | Transport picks the target from above (its hand-over ≤ 5 s, TRN-005) | (TRN) |
| 9 | Lift returns the riders (rest of row 2) to level 1: travel + push in. This overlaps with the transport's transfer | 3.3 + 1.3 s |

* STO-003 (≤ 30 s) is met with margin. In practice the controller keeps the free row slot near mid-height,
  which shortens moves 3 and 5 to ≈ 1.9 s each, so the worst case drops to **≈ 15.6 s**.
* A front-row box from a mid level takes ≈ 1.7 + 1.8 + 1.9 + 0.3 = **5.7 s**. With "last used goes to the front"
  (every returned box enters a front row, see 3.2), ≈ 70 % of picks are front-row picks [E], so the **mean is ≈ 8 s**
  (STO-003 mean ≤ 15 s met).
* Peak CAP-012 (15 retrievals in 10 min) needs 15 × (≤ 18 + 5) s ≈ 6 min [C] for retrieval plus return of the
  riders. This is feasible, but the single lift is busy ≈ 60 % of the peak window. TRN-008 buffering happens at the
  transport side.
* Nothing is restored after a dig. The blocker row stays where it was parked; the inventory only records the new
  slot. The free slot wanders like the hole in a sliding puzzle.

### 3.2 Put-away (a box returns from the cell)

| # | Move | Time |
|---|---|---|
| 1 | The lift waits empty at the exit, shutter open | — |
| 2 | Transport sets the box onto the shuttle belt at x = 18 + 2 mm (left-justified). The NFC strip confirms identity and position | (TRN) |
| 3 | Lift travels to the target level: the nearest level that has a free row slot **and** a front row with a gap ≥ the box width | ≤ 3.3 s |
| 4a | If the level's front row has a gap: motor −6 brings that front row onto the shuttle. This needs the shuttle to be empty, so in this case step 2 happens **after** step 4a (the lift collects the partial row, goes to the exit, the transport places the box into the gap, then the row returns: + 3.3 + 3.3 + 1.3 s) | + 8 s |
| 4b | Otherwise: motor +6 pushes the single box in as a new front row; the level's front row moves back | 1.3 s |
| | **Simple put-away (4b)** | **≈ 4.6 s** after the box is placed |

Rule: **every returned box enters a front row**. Frequently used boxes therefore collect in front rows, and rarely
used ones drift to row 2 (an LRU order). Fragmentation from 4b (rows with one box) is removed by a night-time
**consolidation run**. The lift brings partial rows to the exit one by one, and the transport moves boxes between
them, holding one box in its hand while the lift exchanges the rows. This takes ≈ 25 s per moved box [E]. The same
run tests every level coupling (5.4).

Ingestion (a full row of new boxes) uses 4b repeatedly: the transport fills the shuttle row with up to 5 boxes,
then the lift pushes it into a level. That is ≈ 6 s per row plus the transport's placing time.

---

## 4. Density

Reference volumes: module enclosure 650 × 600 × 2000 = **780 L** (the gallery z 2000–2200 belongs to the
transport); the whole column to 2200 = 858 L.

| Level group | Levels × rows | Boxes per row | Positions | Envelope incl. lid (L) [C] | Slot volume, footprint × pitch (L) [C] | Usable food volume (L) [E] |
|---|---|---|---|---|---|---|
| 65 mm boxes, pitch 110 | 5 × 2 | 5 S-65 | 50 | 73 | 105 | 25 (0.5 L each) |
| 100 mm boxes, pitch 145 | 6 × 2 | 3 M-100 + 1 S-100 | 48 | 141 | 182 | 66 |
| 150 mm boxes, pitch 195 | 2 × 2 | L-150 + M-150 + S-100 | 12 | 64 | 82 | 36 |
| **Total** | 13 levels, 26 row slots | | **110** | **278 = 36 % of 780 L** (32 % of 858) | **368 = 47 %** (`research/03` convention) | **127 L** (16 %) |

* **Effective positions:** 110 − one free row slot for digging (≈ 4) = **106**. Rows are not always fully tiled
  (≈ 85 % [E]), so real mixed use gives **≈ 90–95 positions**. The empty reserve is nested (2), which counts as
  ≈ 3 boxes per slot.
* **Positions per metre of wall:** 169/m nominal, ≈ 140/m in real use.
* **Requirements:** CAP-020 (≥ 70 positions, ≥ 30 S, ≥ 45 L of usable volume) is met with ≈ 20 positions spare for
  the ambient share of CAP-023 (with nesting, ≈ 25–35 empty boxes). STO-005 (≥ 55 % envelope, S) is **not met**
  (36 % strict). The cool zone of CAP-024 (8–15 °C) is not provided here: it belongs in the cold module.
* **Comparison with the aisle shuttle A in the same 650 × 600 column** [C]: two faces × (3 M + 1 S) per level ×
  13 levels at a 135 mm pitch (hanging lidded GN-100 plus fork clearance) = 104 positions of 100 mm boxes. S3 with
  all-100 mm levels: 12 levels × 2 rows × 4 = 96. So **S3 is not denser**. Its belt deck (21 mm) costs a little more
  height than rails, and both designs lose the same 200 mm of depth to the aisle. S3's real gains are elsewhere: any
  box mix including L without per-box fork clearance, no flange-hanging tolerance, and 2 motors instead of 3–4.
* How it could become dense: the aisle would have to serve deeper rows. With the same 200 mm aisle, a store with
  lanes 4 rows deep (≈ 900 mm, e.g. a module turned so that its lanes run along the wall) would reach ≈ 55 % envelope
  [E], but that does not fit the 600 mm depth (#11).

---

## 5. Actuators, sensors, parts, cost, failures

### 5.1 Actuators and seals

| # | Actuator | Type [E] | Notes |
|---|---|---|---|
| 1 | Lift Z | closed-loop NEMA 23 stepper, 3 : 1 belt reduction, spring-applied brake, cross shaft, 2 HTD-5M belts; 23 kg moving (lift 8 + row ≤ 15 kg) | in the plinth; hand-crank socket; brake holds on power loss (TRN-007 by analogy) |
| 2 | Shuttle belt + docked level belt | closed-loop NEMA 17 + gearbox on the lift; drives shuttle roller and blade 1 : 1 | flat PUR cable in a hanging loop in the left wall cavity |
| — | Exit shutter | **no actuator**: bell crank driven by the lift over-travel, return spring | |
| — | 13 levels | **no actuator**: slot hub + detent | |

Seals: **none dynamic** (ambient and dry). The lift's guide/belt connections pass through 8 mm vertical slots in
the inner skins of the side walls; dust can enter the cavities and falls to the plinth tray.

### 5.2 Sensors

* Lift: home switch (bottom), motor encoder, a **docking flag** on every level read by a slot sensor (± 0.5 mm
  alignment of blade and hub), index Hall sensor on the blade.
* Shuttle: through-beam light barriers along x at (a) the rear nose / transfer gap ("nothing straddles", the lift
  may move only when this beam is clear), (b) the front fence (overrun), (c) box-top height + 5 mm (proud lid,
  open box, STO-013); a **12-antenna NFC strip** under the shuttle belt with a multiplexed reader (identity and
  x position of every box in the row, STO-009); optional small camera looking along the level fronts.
* Module: shutter-closed switch, door switch, leak strip in the plinth tray, temperature/RH sensor (STO-007).
* No sensor or wire in any level.

### 5.3 Parts and cost (machine part, ambient module) [E, ±30 %]

| Group | Content | Bought / custom | € |
|---|---|---|---|
| 13 levels + spare belt | endless PU food belts 600 × 820 with V-guide (14 × 35), Ø 17.5 rollers with PEEK bushes (28 × 8), laser-cut bent slider beds 1.4301 (14 × 25), slot hubs, detents, brackets (13 × 6) | belts B (conveyor shop), rest C (job shop, #21) | 1,140 |
| Lift | NEMA 23 CL + driver, brake, reduction, belts, pulleys, cross shaft, guide rollers, frame | B + C | 310 |
| Shuttle | NEMA 17 CL + gearbox + driver, GT2 loop, blade on sprung slide, belt (counted above) | B + C | 95 |
| Sensors | 3 light barriers, NFC strip + reader, flags, switches, leak strip, T/RH, camera | B | 150 |
| Enclosure | hollow side walls with hook-in strips, back, top cover with port, plinth tray, door with gasket, shutter + bell crank | C | 460 |
| Controls share, cables | MCU, PSU share, PUR flat cable | B | 60 |
| Cleaning kit | scraper on the lift, mini pump, 0.5 L sanitiser tank, nozzle, crumb gutter | B + C | 45 |
| **Total** | | | **≈ 2,260** |

Not included: ≈ 110 boxes with lids (≈ €10 each, €1,100, the same for every design). The enclosure (€460) stands
in for bought shelving in #28, so the machine-part share is ≈ **€1,800**. The level belts are half of it. An aisle
shuttle in the same column would cost ≈ €400–600 less (rails instead of belts, even with an extra X axis) [E].

### 5.4 Failure modes and recovery

| Failure | Detection | Recovery |
|---|---|---|
| Box catches or tips at the transfer gap | following error of motor 2; gap beam blocked too long | reverse 20 mm, retry at half speed; second failure → level quarantined, service message |
| Belt slips (row does not arrive) | gap/front beam timing | up to 2 extra half-turns, then error; cause is belt tension → eccentric tensioner at service |
| Belt mistracks | V-guide prevents it; edge rub shows as rising motor current | service |
| Hub not vertical (detent broken, turned by hand) | blade pushed aside → x-slide switch, lift stops on following error | human turns the hub's knurled rim to its mark; the lift never travels unless the blade is vertical |
| Proud lid / open box | height beam when the row enters the shuttle | row goes back; or the lift brings it to the exit and the transport re-seats the lid |
| Wrong or missing box | NFC strip vs inventory | inventory update, re-scan of that level |
| **Dropped box** | — | boxes are never lifted inside the store. A box can leave a belt only at a front nose, and a level belt can move **only while the lift is docked**, i.e. with the shuttle in front of it, which has a front fence. A box that falls during service lands in the plinth tray; inventory/camera notice it; the human removes it |
| **Power loss mid-move** | — | both motors stop, the brake and detents hold, a row straddling the gap stays put and the blade stays engaged (the lift has not moved). On restart: beams read, the commanded transfer is completed, then the lift re-indexes. The move log is non-volatile; if in doubt, **re-scan** (STO-010): every row is pulled onto the shuttle, read and pushed back (back rows via the free slot), ≈ 4–5 min [C] |
| Jammed box (cannot move either way) | both directions fail | quarantine the level; human via door |
| Lift motor or brake fails | encoder, brake fail-safe | hand crank in the plinth |
| Shutter jammed | shutter switch | spring-closed; jammed open → pest alarm (STO-008) |

**By hand, power off (STO-011):** open the door (the switch cuts both motors). The front row of every level is in
reach: pull a box forward, it slides on the belt with ≈ 15 N. To reach a back row, turn the level's knurled hub rim
by hand: 6 half-turns move the whole level forward by one row, and the front boxes come out onto your hand. If the
lift hides the level you need, wind it up or down with the crank, which is clipped to the inside of the door.
No tools are needed.

---

## 6. Cleaning

**What gets dirty.** Boxes leave the washer clean and stay lidded in the store. The soil that reaches the store is
crumbs and flour dust carried on box bottoms and flanges from the lid station and the cell. Rare events: a leaking
box (ambient liquids are sealed STOW packs inside leak-tight boxes, BOX-008, so a leak is a double fault) and a
broken box.

| Surface | How it is cleaned without a human | Interval |
|---|---|---|
| Level belt top (the box-contact surface) | **Scraped at every docked move.** A soft symmetric PU lip on the lift's rear edge touches the level belt where it wraps the front nose; debris falls into a **crumb gutter** along the lift's rear edge. **Sanitising loop:** during the weekly consolidation (before the shop, when the store is emptiest), each level is emptied into free row slots, and the lift runs its belt through one full loop (820 mm, ≈ 6 s) while a nozzle mists ≈ 5 mL of 70 % ethanol (food-contact surface sanitiser, no rinse, dries in < 1 min, no water in a dry store). 5 mL in 0.78 m³ is ≈ 5 g/m³, far below the lower explosive limit [C] | every move / weekly |
| Shuttle belt | fixed lip and nozzle in the plinth act on the shuttle's front nose when the lift parks at the bottom | daily |
| Crumb gutter | emptied at the bottom park position by a small plinth fan through a docking nozzle into a sealed 1 L crumb bin | daily; bin emptied at the yearly service (dry, ≈ 10–50 g/year [E]) |
| Belt loop inside, slider beds | closed by the belt itself; **not machine-cleaned**. Belts release with the eccentric tensioner and slide out to the front | yearly service (human or technician): belts washed in a sink, beds wiped |
| Side walls, cavities, plinth tray | dry; dust falls to the removable stainless plinth tray | yearly service |
| **Liquid spill** | detected by the box's mass loss at the next weighing, the plinth leak strip, or the camera. Liquid on a belt runs to a nose and drips into the aisle or down the back wall to the plinth tray. It can wet the lids of boxes in the levels below. Response: affected levels quarantined, their boxes sent through the washer (exteriors), sanitising loop with detergent-sanitiser on those levels. **Oily or sticky spills need a human wipe** (service call) | event |
| **Broken box** | NFC missing, height-beam or transfer anomalies, mass | level quarantined; human removes the pieces through the door |

Verdict: the box-contact surfaces are smooth, closed and wiped at every move, which is good. But 13 hidden belt-loop
interiors, spills that drip down through the stack, and a yearly belt removal make S3 clearly **less hygienic than
open stainless rails** (aisle shuttle), where a spray reaches every surface. STO-012 is met for contact surfaces
only.

---

## 7. Cold variant

**Does the same mechanism work at +4 °C and −18 °C?** Yes, and it suits the cold better than the ambient. The levels
are passive, so **no motor, no wire and no grease** is in the grid. Both motors can sit outside the insulation.

**Arrangement** (per 178 cm integrated fridge or NoFrost freezer shell, `research/03` 4.1/4.6):

```
 side view of one cold shell (z from the machine floor; appliance at z 100-1880)
      y: 0    ~60                    ~260 ~272          ~450         550
 2000  +------+-- gallery port -------+-----------------------------+
       |      | [motors: lift drive, hex-shaft drive]  (outside cold) |
 1880  |OEM   +==== HATCH: cut-out in the cabinet top over the aisle, |
       |door  |     insulated slide 60 mm, heated frame              |
       |(kept,|  LIFT + shuttle  |gap| level n: 1 row (178)          |
       |closed|  (aisle 196)     |   | level n-1                      |
       |in    |  hex shaft and   |   |  :      8-9 levels @ 145       |
       |use)  |  lift belts from |   |  :      (1 row each: no dig)  |
       |      |  the top         |   |                                |
  ~350 |      |  lift bottom     |   +-- compressor step: no levels --+
  100  +------+------------------+---+--------------------------------+
```

* **One row per level.** Interior depth with the door bins removed ≈ 400 mm [U] = aisle 196 + gap 12 + one row 178.
  So there is **no digging** at all. Interior width ≈ 490 [U], minus a free-standing stainless insert frame (internal
  fitting; it hooks onto the liner's shelf ribs and needs no drilling) → rows of 8 units (432 mm): M + M + S, or
  L + S, or 4 S. With 8–9 levels at 145 mm above the compressor step: **≈ 27–33 positions per shell** [E]. That is
  the same range as `research/03` (33–45), and it means: chilled ≥ 45 (CAP-021) needs **two fridge shells**, while
  frozen ≥ 20 fits in one freezer shell. This shortfall is the same for every mechanism in these shells; it is set
  by the shell, not by S3.
* **Exit at the top.** A box can leave only horizontally into the aisle, then up. The 600 mm depth leaves no room for
  a vestibule in front of the door. So the exit is a **cut-out in the cabinet top above the aisle** (≈ 460 × 200),
  closed by an insulated 60 mm slide. The slide is opened by the lift's over-travel, as in the ambient module, with
  no extra actuator, and has a 5–8 W heated frame (CLD-014: does not freeze shut, no drip). This is a modification
  "at the exit" in the sense of CLD-007. The OEM door, refrigerant circuit and controller stay untouched, and **the
  door stays closed** in use and serves as the service door. [U, gating:] the top front strip must be free of the
  hot-gas anti-sweat loop and wiring; check on a real unit. A top opening is thermally favourable: cold air does
  not spill upward (chest-freezer principle), so losses are well below the front-hatch figures of `research/03` 4.4
  [E].
* **Motors outside.** Both motors sit on the cabinet top in the z 1880–2000 zone. The lift hangs on two belts that
  pass through 20 × 6 mm brush-sealed slots in the hatch frame, with idlers at the bottom inside. The shuttle and
  level belts are driven by a vertical **stainless hex shaft** (10 mm A/F) through a PTFE bushing, along which a
  bevel-gear block on the lift slides (replacing the ambient version's motor on the lift). Inside the cold: only the
  passive levels, the lift frame, dry-running PEEK/igus rollers and bushes, and the lift's sensors (light barriers,
  NFC strip, self-heated 1–2 W, potted) on a PUR cable rated −40 °C.
* **Belts at −18/−25 °C.** Ordinary PU belts are rated to about −20/−30 °C [U]. CLD-009 asks for −25 °C, so the
  freezer uses a **low-temperature PU or silicone-faced belt rated −40 °C** [U]. Bushes are PEEK, springs
  stainless. Slot hubs get 1 mm extra clearance and long chamfers to tolerate rime, and the closed-loop motor
  detects stiff docking.
* **Frost.** Humid air enters only through the top hatch for ≈ 5 s per pick. In a NoFrost freezer the frost
  collects on the evaporator, which defrosts itself. Main risk: a box with a **wet bottom freezes onto a level
  belt**. Rules: only washer-dried boxes enter the freezer (frozen food is not refrozen after use, `research/03` 4.4,
  so returns to the freezer are rare: new stock at ingestion and machine-made portions), and the transport's
  exit check rejects wet bottoms. A frozen-on box is released by flexing: the belt wraps the Ø 18 nose and peels the
  ice off, as ice trays do [E, to test].
* **Condensation (fridge).** Boxes and belts are wet at times. Wet PP on PU still gives μ ≈ 0.25 [E] > 0.1 needed.
  Fridge belts get the sanitising loop twice a week (ethanol works at +4 °C). Condensate drips to the shell's own
  drain channel. CLD-008 is met by the appliance's own defrost and drain.
* **Door opening time.** The OEM door is never opened in operation. The top hatch opens ≈ 5 s per pick: the transport
  hoist reaches 150 mm down, grips, lifts (CLD-004 ≤ 10 s). Retrieval: travel ≤ 2.6 s + transfer 1.8 s + travel
  2.6 s + hatch 0.3 s ≈ **8 s worst case** (CLD-006 ≤ 45 s). The riders of the row are exposed at the hatch for the
  same ≈ 5 s.

---

## 8. Score, weakness, experiment

| Criterion (weight) | Score 1–5 | Reason |
|---|---|---|
| Simplicity (30 %) | 3.5 | **2 motors** for 13 levels, no actuator in the grid, docking without extra motion, shutter on the lift's over-travel. But 13 belt modules (26 rollers, 13 detents and hubs), and row riders plus free-slot management add control logic |
| Hygiene (25 %) | 2.5 | closed, smooth contact surfaces scraped at every move and sanitised weekly; but 13 hidden belt-loop interiors, spills drip down the stack, belts are removed yearly by hand |
| Coverage / fit (20 %) | 3.5 | fits 650 × 600 × 2000; ≈ 90–95 real positions (CAP-020 + reserve met); any box mix incl. L; worst case 18 s / mean 8 s. But STO-005 is missed (36 %), the bayonet stub conflicts with dense rows, and the cold shell takes 1 row per level |
| Reliability (15 %) | 3 | no drives in the grid, power-off safe, a box cannot fall from a level; but 13 wide-short belts (tracking, slip), tall narrow boxes crossing the gap, freeze-on in the freezer |
| Cost (10 %) | 2 | ≈ €2,260 module (≈ €1,800 machine share), belts ≈ €1,150; ≈ €400–600 more than an aisle shuttle |
| **Weighted** | **3.0** | |

**Biggest weakness (honest).** In a 600 mm deep cabinet a belt grid cannot be truly dense. A box leaves a level only
horizontally, so a 200 mm lift aisle is unavoidable, and only two rows fit behind it. S3 therefore ends up exactly
as dense as an aisle shuttle. It pays for that with 13 belt loops (half the cost, the hidden hygiene surfaces, the
downward spill path) and saves only one motor. The "dense with belts" idea needs lanes ≥ 4 rows deep, which the 600
mm depth (#11) rules out.

**What is worth keeping regardless of the winner.** The **passive slot coupling** (the toner-cartridge drive): one
motor on the lift drives any passive mechanism at the level where it stops, with no extra motion. It lets a
pusher design (S2) or a cold store keep all motors on one carriage, or outside the cold.

**Cheapest experiment** (≈ €300, 3–4 days). Build one level module (belt with V-guide, slider bed, rollers, slot hub
with detent) and a lift mock-up: a board on a hand-moved vertical slide carrying the NEMA 17, the shuttle belt and
the blade. Test:
1. 500 row transfers of mixed rows (S-65 … L-150, empty to 5 kg, dry and wet bottoms) across the 10 mm gap;
2. 1,000 blade passes through hubs at 0.6 m/s, and docking accuracy;
3. belt tracking and slip over 2,000 cycles;
4. the module for a week in a chest freezer at −18/−25 °C with wet-bottomed boxes (freeze-on release, belt
   stiffness, rime in the slots).

If 1 and 4 pass, S3 is buildable. Its density verdict does not change.

