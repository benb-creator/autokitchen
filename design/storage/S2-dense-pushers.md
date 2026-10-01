# Storage S2 — dense grid with pushers: "one shaft, one car"

Status: design proposal, storage round (brief `00-storage-brief.md`). Inputs: DECISIONS #11, #17–#22, #28;
requirements STO, CLD, TRN, BOX, CAP-020…025, PHY-001…004; `research/03-storage.md` sections 1–4, 6, 7;
K9b section 2 (hand-over interface). [E] = estimate, [U] = unverified, must be measured.

Coordinates: module-local **x 0–650** from the left side (machine X 1200–1850, K9b 2.1), **y 0 at the wall,
y 600 at the front** (as K9b), **z** from the floor.

## 0. Summary

* The customer's concept: boxes on shelves packed in X, Y and Z with only leeway. Pushers move a box in X into
  an empty centre column, then in Y along it to the front. **In the 650 mm column only three box columns of
  176 mm fit** (3 × 182 = 546 of 610 mm inside). The centre one stays empty, so every stored box stands
  directly next to the empty column. **No box ever blocks another**, so there is no sliding-puzzle shuffling.
* **The empty column is the same at every level, so it is made one vertical shaft without floors.** A single
  **car** runs up and down the shaft. Its deck serves as the floor of the empty column at whatever level it
  stops. Its **toe** pulls a box in X from the left or right lane onto the deck, slides it in Y, and pushes it
  into a hand-over cell at the top. **3 motors for the whole column (Z, Y, X), none per shelf**, no solenoids.
  The pin engages the box when the car itself drops 10 mm.
* **89 box positions** (32 S, 53 M, 4 L) plus 2 hand-over/buffer cells in 650 × 600 × 1900 mm (z 100–2000).
  CAP-020 is met: ≥ 70, ≥ 30 S, 124 L ≥ 45 L. **Box volume = 31 % of the enclosure** (slot volume 38 %),
  **137 positions per metre of wall**. That misses STO-005's 55 % and is not denser than an aisle shuttle. In
  X, one column in three is always the shaft.
* **Worst-case retrieval ≈ 11.5 s** (bottom level, rear box, to the top hand-over), mean ≈ 7 s. Put-away is the
  same; if the lane must first be compacted, ≤ 17 s. STO-003 is met (≤ 30 s, mean ≤ 15 s).
* **Cost [E]:** ≈ €1,050 bought (motion, sensors, controls) + ≈ €1,000 job-shop stainless (shelves, carcass,
  car, door) per ambient column. The structure takes the place of the customer's "shelving €500–1,000" line.
  The boxes need a custom mould for the pull rib. K9b already needs one for its stub.
* **Interface finding for K9b:** a 40–50 mm bayonet stub on the box side cannot be packed densely in any
  direction (section 2.3). S2 uses stubless boxes and a permanent **stub carrier** on the cell's box shelf.
* **Cold:** the same car is mounted on the **replacement door**, so the cabinet is not drilled (CLD-007).
  There is one lane behind a front shaft, ≈ 33–38 positions per 178 cm shell. The Z motor sits outside the
  cold; the small X/Y motors are on the car inside.
* **Biggest weakness:** at 650 mm the concept's purpose, density, is lost. A real multi-column puzzle needs
  ≥ 1,050 mm of width and then brings shuffling back (section 4.3).

## 1. Principle and layout

### 1.1 Principle (3 sentences)

Lidded boxes stand flat on plain sloped stainless shelves in two lanes left and right of an empty centre
column, packed front to back with 4 mm leeway, with levels only box height + 22 mm apart. The empty centre
column is a vertical shaft without floors in which one car travels; at the wanted level the car's deck lies
flush with the shelves and its toe pin drops into a slotted rib at the base of the box. The toe pulls the box
sideways (X) onto the car and slides it along the car (Y), and the car lifts it to a hand-over cell under the
transport gallery's ceiling port (K9b 2.1/2.12); put-away is the reverse.

### 1.2 From "pushers into an empty column" to "one car in a shaft": how many actuators?

The brief asks for pushers in X into the empty column and a pusher in Y along it. The question is how many
actuators that really takes. Options for a 15-level column (14 storage levels + hand-over level):

| # | Who moves the boxes | Motors | Other moving parts | Verdict |
|---|---|---|---|---|
| O1 | Literal: per level, one X pusher per Y position per side (3 × 2), one Y pusher in the centre column, plus a front lift with a puller | 15 × 7 + 2 = **107** | — | rejected (research 3.1 F: too many drives, a stuck one freezes a level) |
| O2 | One full-length push plate per lane and level | 30 + lift | — | **not selective**: pushes the whole lane into the column |
| O3 | Passive pushers (spring-return slides, push rods) at every position, worked by one travelling driver on a front lift | 3–4 | ≈ 105 slides, springs, couplings | rejected: 105 crevices and wear points, each a jam case |
| O4 | The K9b gallery hand: its hoist goes 1.9 m down a floorless centre shaft and carries a side toe | 0 in storage (+1 toe, +1.9 m hoist stroke in the transport) | — | possible fallback; blocks the transport ≈ 10 s per box (TRN-008) |
| **O5** | **One car in the floorless centre column; its toe pulls in X and slides in Y; the car changes levels** | **3 (Z, Y, X)** | **0** | **chosen** |

Why O5 needs no per-level parts:

* In a 650 column there are only two lanes, both next to the empty column. The puller never has to reach past
  a box, so it can sit in the empty column, not at the walls.
* The empty column is empty at every level. Its floors only make it impossible for a single drive to change
  level, so they are left out. The car's deck becomes "the floor of the empty column" only where and when it
  is needed.
* The toe engages a feature at the box base, so the box height (65/100/150) does not matter. The engagement
  stroke is the car's own Z: it arrives 10 mm high and drops onto the box. Pushing out works the same way in
  reverse (section 3).

### 1.3 Dimension budget

| Direction | Budget (mm) |
|---|---|
| **X 650** | wall 20 (left, toward the cold module) · gutter margin 32 · **left lane 182** (box 176 + 6 leeway) · **shaft 182** (car 176 + 2 × 3 gap) · **right lane 182** · gutter margin 32 · wall 20 (right, 20 mm PIR insulated toward the hot cell, STO-007) |
| **Y 600** | rear panel 15 (incl. wall allowance, PHY-001) · rear zone 35: Z rails and cable chain behind the shaft, drain ducts behind the lanes · **lanes and car deck 510** (y 50–560) · front frame 20 (posts at the shaft edges, gasket face) · door 20 |
| **Z 2200** | plinth 0–100 (sump, drain pump, valves, controller) · shaft bottom pan 100–140 · **14 storage levels 140–1808** · **hand-over level H 1808** (car beam top at 1988) · gallery floor 2000 · transport gallery 2000–2200 (K9b) |

Level table (shelf top z, pitch = box nominal height + 6 lid + 14 clearance + 2 shelf):

| Levels | z (shelf top) | Class | Pitch | Per lane (510 mm) | Per level |
|---|---|---|---|---|---|
| L1–L2 | 140, 312 | 150 mm | 172 | 1 L (GN 1/3, 325) + 1 M (162) = 495 | 2 L + 2 M-150 |
| L3–L10 | 484 … 1338 | 100 mm | 122 | 3 M (3 × 166 = 498) or L + M | 6 M-100 |
| L11–L14 | 1460 … 1721 | 65 mm | 87 | 4 S (4 × 112 = 448) or M + 3 S (502) | 8 S-65 |
| H | 1808 | hand-over | to 2000 | front: hand-over cell 214 × 344, open to the port; rear: 1 M (left) or the Z motor (right) | 2 cells + 1 M |

Heavy L boxes sit at the bottom. Spices (S) are used in almost every meal, so they sit at the top next to the
hand-over, which shortens the mean Z travel.

### 1.4 Front view (door removed)

```
  x  0 20 52           234            416           598 630 650
 2200 +--+--+-------------+--------------+-------------+--+--+
      |        transport gallery (K9b), 2 ceiling ports with spring flaps     |
 2000 +--+--+===[port L]==+==============+==[port R]===+--+--+
      |  |  | H cell L    | car parked:  | H cell R    |Zm|  |  H 1808: hand-over cells open to the ports
 1808 |  |g |=============| beam 1973-88 |=============|  |  |
      |  |u | S  (4/lane) |              | S           |u |  |  L14 1721 \
      |  |t |-------------|              |-------------|t |  |  L13 1634  | 65-class, pitch 87
      |  |t |-------------|    SHAFT     |-------------|t |  |  L12 1547  |
      |  |e |-------------|   182 wide   |-------------|e |  |  L11 1460 /
 1460 |  |r | M  (3/lane) |  no floors   | M           |r |  |  L10 1338 \
      |  |  |-------------|              |-------------|  |  |   ...       | 100-class, pitch 122
      |  |  |-------------|  +--------+  |-------------|  |  |   ...       | 8 levels
      |  |  |-------------|  |  car   |  |-------------|  |  |   ...       |
  484 |  |  |-------------|  | 176 w  |  |-------------|  |  |  L3   484  /
      |  |  | L + M-150   |  +--------+  | L + M-150   |  |  |  L2   312 \ 150-class, pitch 172
  140 |  |  |=============|______________|=============|  |  |  L1   140 /
  100 |  |  |  shaft bottom pan 100-140, removable, drained   |  |
      +--+--+-----------------------------------------------+--+--+
      |  plinth: sump + drain pump, rinse valves, controller, 24 V  |
    0 +-------------------------------------------------------------+
   g = gutter (outer edge of every shelf, 1 deg shelf slope toward it); Zm = Z gearmotor (top rear)
```

### 1.5 Side view (section through the left lane)

```
  y   0  15    50                                            560 580 600
 2000 +---+-----+---------------------------------------------+---+---+
      |   |     |  rear M  |  H cell (open up to port L)       |   |   |
 1808 |   |  d  |==========|==================================|   |   |
      |   |  r  |  S  |  S  |  S  |  S  |   (4 x 112 = 448)   | F |   |
      |   |  a  |=============================================|   | D |
      | r |  i  |   ... 65-class levels                       | r | o |
 1460 | e |  n  |=============================================| o | o |
      | a |     |     M      |     M      |     M      |      | n | r |
      | r |  d  |=============================================| t |   |
      |   |  u  |   ... 100-class levels                      |   |   |
  484 | p |  c  |=============================================| f |   |
      | a |  t  |          L  325            |    M  162      | r |   |
      | n |     |=============================================| a |   |
      | e |  -> |          L                 |    M           | m |   |
  140 | l |  sump============================================  | e |   |
  100 +---+-----+---------------------------------------------+---+---+
      plinth: sump, drain pump
   Every gutter (outer lane edge) falls 2 deg to the rear into the vertical duct (y 15-50), then to the sump.
   Boxes stand anywhere along y 50-560 (no slots); front and rear 8 mm up-stops.
```

### 1.6 Top view at a 100-class level

```
 y 600 +-----------------------------------------------------------------+
       |                           door (20)                             |
 y 580 +--+----------------+-+------------------+-+----------------+--+--+
       |  |  front stop    |P|  car front post  |P|  front stop    |  |  |  P = front-frame posts
 y 560 |  |----------------| |..................| |----------------|  |  |
       |g |  M 162         | :                  : |  L 325         |g |  |
       |u |----------------| :    CAR DECK      : |                |u |  |
       |t |  M 162         | :  176 x 510, UHMW : |                |t |  |
       |t |----------------| :  Y beam above,   : |----------------|t |  |
       |e |  M 162         | :  toe on cross    : |  M 162         |e |  |
       |r |                | :  slide (+-91)    : |                |r |  |
 y 50  |  |----------------| :..................: |----------------|  |  |
       | drain duct        | | rear post, 2 Z    | | drain duct      |  |
 y 15  |                   | | rails, cable chain| |                 |  |
 y 0   +--+----------------+-+------------------+-+----------------+--+--+
      x 0 20 52          234                   416               598 630 650
```

### 1.7 The car and the toe

* **Car**: an O-frame in the y–z plane of laser-cut, bent 1.5 mm stainless: rear post, deck, overhead beam
  and front post, 176 wide. It is guided only at the rear by two vertical rails (y 15–35) and hangs on the
  Z belt. The **deck** is 176 × 510 with a 6 mm UHMW-PE (PE-1000) top and chamfered long edges, mounted on a
  single-point load cell (10 kg, ±2 g). The **overhead beam** sits at deck + 165…180, above a lidded 150 box.
  It carries the Y rail, Y belt and Y carriage. The X **cross slide** hangs below the carriage with ±91 mm
  stroke, and from it hangs the toe arm.
* **Toe**: a 4 mm stainless strip hanging from the cross slide, with a horizontal toe at deck + 18…28 mm and a
  Ø 4 × 8 mm conical pin pointing down. It reaches ≤ 13 mm into a lane, under the box's top flange and above
  its base rib. It carries the NFC reader, an IR edge sensor and a small inspection camera.
* **Engagement by Z, no solenoid**: the car stops 10 mm above the shelf. X moves the toe over the rib slot,
  Y centres it on the slot. The car drops 10 mm to flush, so the pin goes through the slot. If the pin
  lands on the rib instead of the slot, Z stops 6 mm early; that is detected as following error and
  retried with a ±3 mm Y search. Release is the same: the car rises 10 mm.

```
   left lane                         | shaft
                    flange  ___      |  6 mm leeway at the lane edge
   box wall (draft) \       |  |     |
                     \      |  |   hanging toe arm (inside the shaft above deck + 30)
                      \   __|__|_____|___
                       \ |pin|  toe       deck +18..28: under the flange, above the rib
            base rib ===|v|==             rib at base +12..16, slot 10 (y) x 5 (x), through
   ====================== shelf ====|3|===== car deck (UHMW, flush +-1) =====
                         1 deg slope       gap 3, both edges chamfered
                         toward the gutter
```

## 2. Box standard

### 2.1 Size family

GN 176 family as in research 2.4. In every lane the **176 mm side runs across the lane (X)**, so all boxes
fit the 182 mm lanes and shaft. The variable side runs along the lane (Y), so mixed lengths pack without
fixed slots:

| Size | Footprint (Y × X) | Heights used | Volume [U] | Where |
|---|---|---|---|---|
| S | GN 1/9: 108 × 176 | 65 | ≈ 0.5 L | L11–L14 (spices, herbs, salt) |
| M | GN 1/6: 162 × 176 | 65, 100, 150 | 1.0 / 1.5 / 2.1 L | everywhere |
| L | GN 1/3: 325 × 176 | 100, 150 | 4 / 6 L | L1–L2 (flour, sugar, pasta, rice, bread for cooking) |

Height classes are 65, 100 and 150. A level takes one class, which keeps the level pitch at box + 22 mm.

### 2.2 Features S2 needs (custom-moulded GN-footprint box)

* **Material**: PP impact copolymer or Tritan. Homopolymer PP is brittle below 0 °C, so it is excluded
  (−25 °C, BOX-009). Transparent or translucent (BOX-014). PC is excluded (BPA, research 2.2).
* **Top**: the standard GN flange, ≥ 6 mm wide, so GN lids and bain-marie use still work. Flat gasketed
  press-on lid **sitting on top of the flange and not overhanging it**, ≤ 6 mm above the flange, with a flat
  centre for the lid station's vacuum cup (research 2.3).
* **Pull rib** (the only new feature): on **both sides parallel to the lane**, i.e. the 108/162/325 mm sides,
  at the centre, a solid rib 40 mm long at base + 12…16 mm, protruding 5 mm. It stays inside the flange
  outline, because the base is inset ≥ 7 mm by the draft. It has a **through-slot** 10 (along the side) × 5 mm.
  The slot is open at the top and bottom, so it drains upright and inverted in the washer. There are no
  undercuts and no hollow rims; outer radii are ≥ 1 mm. The rib is outside Zone F. It is pulled and pushed at
  14 mm above the shelf, which is too low to tip any box. It also makes a box from either lane usable in
  either lane.
* **Base**: flat, with 4 moulded pads Ø 15 × 1.5 mm near the corners. They give a defined sliding contact,
  ride over the 3 mm deck gap and keep the base out of thin spill films.
* **Identity** (BOX-006): an HF NFC tag (ISO 15693, rated for washing) moulded into each pull rib. The toe
  reads it at every pick, and in the freezer through frost. A laser-marked 2D code on both 176 mm end faces
  is for cameras at the lid station and cell.
* **Mass** ≤ 5 kg (BOX-004). Highest pull force: 5 kg × μ 0.3 = 15 N. The pin and rib are sized for 80 N.
* **Dishwasher**: monomaterial, no inserts other than the tag, self-draining both ways (BOX-010).
* **Prototype**: bought Araven/Hendi GN 1/6 and 1/3 PP boxes with a PP rib hot-plate-welded on. The final
  mould is ≈ €30–50 k for three footprints with height inserts [U]. K9b's stub already needs a custom mould,
  so the step is not new.

### 2.3 Interface conflict: the K9b bayonet stub cannot be stored densely

K9b (2.5, 2.12) moulds a Ø 22 × 40 mm bayonet stub plus collar, ≈ 45 mm proud, on the box's rear short side.
In any dense store that costs 45 mm in whichever direction it points:

* On the end face (Y), boxes are packed end to end, so a lane would hold 2 M instead of 3 (−33 %).
* On the side face (X), box + stub needs a lane and shaft of 227 mm, and 3 × 227 = 681 mm > 610 mm.
* Pointing up costs 45 mm per level × 14 levels = 630 mm.

**S2 proposal**: storage boxes carry no stub. The cell's box shelf (K9b 2.6, two places) keeps two
permanent **stub carriers**. Each is a stainless GN 1/3 cradle with the bayonet stub and two spring hooks over
the GN flange, with a drop-in spacer for 1/6 and 1/9. The transport lowers the opened box into a carrier,
which is what C4 R-5 already does for STOW packs. There is no extra move. The hand pours with the carrier,
and the flange hooks hold the box. **This needs agreement from the K9b/C4 owners**. It affects every dense
storage design, not only S2.

## 3. Retrieval, put-away, empty column, shuffling

Axis data [E]: Z 0.5 m/s, 2 m/s² (closed-loop stepper, self-locking worm, belt); Y 0.5 m/s; X 0.25 m/s
(pulling/pushing a box), 0.5 m/s empty. The car parks empty at H + 10 mm with the toe inside the shaft.
The toe stays inside the shaft whenever Z moves (software interlock). X motion with a box is only allowed
when the car sits on a level flag within ±1 mm.

### 3.1 Worst-case retrieval: L1 (bottom), rear box, right lane, to hand-over cell R

| # | Move | Axes | Time (s) |
|---|---|---|---|
| 1 | Command; car empty (load cell 0 ± 5 g); look up level, lane, y of the slot | — | 0.2 |
| 2 | Car down 1,678 mm to L1 + 10 mm; **in parallel** Y carriage to the box's slot (y ≈ 131), cross slide to the right shaft edge | Z ∥ Y, X | 3.6 |
| 3 | Toe extends 13 mm into the lane; IR edge sensor finds the rib within ±3 mm | X | 0.3 |
| 4 | Car drops 10 mm to flush: pin through the slot (Z following check); NFC tag read = identity check (STO-009) | Z | 0.4 |
| 5 | Pull 182 mm: box crosses the 3 mm gap onto the deck, centred; load cell checks mass ±10 % | X | 1.2 |
| 6 | Car up 1,668 mm to H flush; **in parallel** Y slides the box to the hand-over cell's y range | Z ∥ Y | 3.6 |
| 7 | Push 182 mm into hand-over cell R against its outer stop | X | 1.2 |
| 8 | Car rises 10 mm (pin out), toe back into the shaft | Z, X | 0.4 |
| 9 | Cell presence sensor; "box n in cell R" to the transport, which lifts it through the port | — | 0.2 |
| | **Total** | 2 X moves, 2 long Z, 2 short Z, 1 Y (parallel) | **≈ 11.1 (11.5 with settling)** |

No box is moved except the wanted one. **Mean ≈ 7 s**: S boxes sit 0.1–0.4 m below H, the M levels on
average ≈ 0.9 m. **Peak (CAP-012)**: 15 retrievals + 15 returns in 10 min ≈ 30 × 10 s = 5 min of car time
(50 %). The two hand-over cells, one in and one out, let the car and the transport work without waiting for
each other (TRN-008).

### 3.2 Put-away

The transport sets a lidded box into a free hand-over cell. The car, at H + 10, engages it (toe and 10 mm
drop, 0.7 s) and pulls it onto the deck (1.2 s), reading the tag and mass. The mass is the inventory fill
level (BOX-012, ±5 g at standstill [E]). The car travels to the target level (≤ 3.6 s, Y to the target gap in
parallel), pushes the box to the outer stop (1.2 s) and rises 10 mm (0.4 s). That is **≤ 7.5 s, or ≤ 11 s
including the return to park**.

Target choice: the height class from the box ID; heavy boxes low, frequent ones high; the smallest gap ≥ box
length + 4 mm. **Compaction**: if no gap is long enough, the toe engages a neighbour *in its lane* and slides
it along the lane in Y (pin in rib, 2–2.5 s per box, ≤ 2 boxes). **Worst-case put-away ≈ 17 s.** In idle time
the car compacts each lane toward its rear so that every L level keeps a ≥ 329 mm gap and every M level a
≥ 166 mm gap.

### 3.3 How the empty column is kept empty

* **Structurally**: the shaft has no shelves, so nothing can be parked in it except on the car.
* The car always parks empty. It only waits loaded while both hand-over cells are occupied.
* **Admission control**: the inventory admits a box only if a free gap of its height class exists. Empty
  reserve boxes (CAP-023) use ordinary positions. The 89 − 70 = 19 spare positions here hold the ambient
  share of the reserve.

### 3.4 Blocking boxes and shuffling

**None in the 650 module.** Each lane touches the shaft along its whole length, and the toe reaches every
box's rib from the shaft. Y neighbours do not block, because the box leaves sideways. The Rubik's cube /
sliding-puzzle moves of the brief only appear with **more than one lane per side**; section 4.3 counts them
for a 1,050 mm module. "Restoring" is therefore only lane compaction (3.2), done in idle time.

## 4. Density

### 4.1 The 650 column (chosen layout)

Enclosure (z 100–2000, without plinth and gallery): 650 × 600 × 1900 = **741 L**. The full 2,200 column is 858 L.

| Box | Count | Nominal envelope (footprint × height) | Slot (footprint × pitch) | Usable content [U] |
|---|---|---|---|---|
| L-150 (GN 1/3) | 4 | 4 × 8.58 = 34.3 L | 39.4 L | 24 L |
| M-150 | 4 | 17.1 L | 19.6 L | 8.4 L |
| M-100 | 49 | 139.7 L | 170.4 L | 76 L |
| S-65 (GN 1/9) | 32 | 39.5 L | 52.9 L | 16 L |
| **Total** | **89** (+ 2 hand-over cells) | **231 L = 31 %** (27 % of 858 L) | **282 L = 38 %** | **124 L = 17 %** |

* **Positions per metre of wall: 137** (140 with the hand-over cells). For comparison, research A has
  168/m (1 m module, all M, slot basis).
* **Where the volume goes**: X 54 % (2 × 176 of 650; the shaft takes 28 %, walls and gutters 18 %) ×
  Y 82 % (lanes 510 of 600, fill 97 %) × Z 72 % (levels 1,668 of 1,900; box / pitch ≈ 0.82) ≈ 32 %.
* STO-005 (≥ 55 %) is **not met**. No S2 layout in 650 mm meets it. With 176 mm boxes, one column in three is
  the shaft.
* **Against an aisle shuttle in the same 650 column** (two racks front and back plus a 192 mm aisle along X,
  pitch 125): ≈ 13 levels × ≈ 7 M-equivalents ≈ 90 positions [E]. **S2 is about equal to it, not denser.** S2
  saves the fork's lift clearance (pitch +22 instead of +25 mm), rails and flange hanging, but it loses
  104 mm of X to the 3-column rule.

### 4.2 Variant S2-B: lanes along X, shaft as the middle row

If the lanes run along the 610 mm width (rear lane, shaft row, front lane, each 182 in Y), each lane is
570 mm long: 2 M + 2 S, 5 S, or L + 2 S. That gives **≈ 97–113 positions (+10…25 %)**, depending on how many
small boxes the mix has. The front lane faces the door, which is best for human access. Costs:

* The car spans 570 mm between rails on both side walls, so it needs two synchronised Z belts.
* Y has only 19 mm left for gutters (3 × 182 = 546 of 565), so drainage would go to the shaft bottom instead
  of side gutters.
* It no longer follows the customer's "X into the column, Y to the front".

It is kept as the option if positions count more than drainage. **The cold variant (section 7) must use this
orientation.**

### 4.3 Where the dense puzzle really appears: a 1,050 mm module with 5 columns

X: walls 40 + gutters 64 + 5 × 182 = 1,014 ≤ 1,050, which is on the PHY-003 grid. Lanes L2 L1 | shaft | R1 R2:

* **≈ 176 positions = 168/m (+23 %)**, nominal box volume ≈ 38 %.
* The toe must reach through an inner lane: **telescopic 2-stage toe, 377 mm per side** (still one motor).
* An outer-lane box is blocked by the 1–2 inner-lane boxes that overlap its y range. Placing outer boxes
  behind inner boxes of the same length keeps that at 1 in most cases.

Worst case: wanted L in L2, two M blockers in L1.

| Step | Time (s) |
|---|---|
| Z to level | 3.6 |
| Pull blocker 1 onto the car, slide it to the deck end | 2.7 |
| Pull blocker 2; the deck is full (166 + 166 + 329 > 510), so push it into a gap in R1 | 4.5 |
| Reach through the gap with the telescope, pull the L 364 mm | 2.5 |
| Push blocker 1 back into L1 (car holds L + blocker 1 = 495 ≤ 510) | 2.0 |
| Fetch blocker 2 from R1, push it into L1 | 4.0 |
| Z to H, push into the hand-over cell, release | 5.2 |
| **Total** | **≈ 25 s (within STO-003's 30 s)** |

Mean ≈ 12 s. Bought with: 6 extra moves in the worst case, a telescope, and a dependence on free gaps.
**This module does not fit K9b's 650 allotment**: it would take 400 mm from the cell or the cold store.

## 5. Actuators, sensors, parts, cost, failures

### 5.1 Actuators and seals

| # | Actuator | Type [E] | Stroke | Where |
|---|---|---|---|---|
| 1 | **Z** (car) | NEMA 23 closed-loop stepper + 10 : 1 **self-locking worm** gearbox, AT5 PU/steel-cord belt loop, 2 stainless profile rails (MGN12 or igus drylin T) with 4 carriages; **hand-crank hex socket** at the top front | 1,700 | motor top rear right (in place of one H-level M position); idler in the bottom pan |
| 2 | **Y** (along the car) | NEMA 17 closed-loop stepper, GT2 PU belt, drylin N polymer slide on the overhead beam | 470 | on the car |
| 3 | **X** (toe) | NEMA 17 closed-loop stepper, drylin high-helix lead screw (dry-running) | ±91 (182) | on the Y carriage |
| — | Pin engagement | **none**: done by the Z drop of 10 mm | — | — |
| — | Port flaps (2) | passive spring flaps pushed open by the transport gripper | — | gallery floor |
| — | Gutter rinse | 2 solenoid valves (left and right riser) + plinth drain pump (bought dishwasher drain pump) | — | plinth |

**3 motion motors for 89 boxes.** No dynamic seals: the whole mechanism is inside the closed store. Static
seals: door gasket, port flap brushes, drain trap (STO-008, pest-proof).

### 5.2 Sensors

* **Z position**: closed-loop encoder, plus 15 stainless **level flags** on the rail frame read by an
  inductive sensor on the car (±0.5 mm). Every stop is verified, which gives the ±1 mm flush rule.
* **X and Y**: closed-loop encoders and home switches. Following error or current rise = jam (STO-013).
* **Toe**: IR edge/rib sensor, **NFC reader** (identity at every pick and put, STO-009), inspection camera
  with LED (lanes, spills, lids; it scans the store as the car travels).
* **Car deck load cell** (10 kg): box present, mass for inventory (BOX-012), broken or emptied box.
* **Lid line**: a light barrier on the beam at lid height + 4 mm detects a lifted lid or bulging box
  before the box is pulled (STO-013, open box).
* **Store**: hand-over cell presence (2 × IR); **sump conductivity** (a spill reached a gutter); door switch
  (interlock); air temperature/RH (STO-007).
* **Re-inventory after power loss or manual access** (STO-010): the car drives every lane with the toe at the
  lane edge. It reads the tags on the fly (HF, ≈ 30 mm) and measures box edges, ≈ 5 s per level, **≈ 2 min
  for the column**.

### 5.3 Parts and cost (ambient column, machine part, prices incl. VAT [E])

| Group | Bought | € | Custom (job shop, #21) | € |
|---|---|---|---|---|
| Z drive | stepper + worm + brake-free crank, belt, pulleys, 2 rails, 4 carriages | 360 | rail frame with level flags | 60 |
| Car | Y and X steppers, belt, drylin slide and screw | 140 | O-frame (laser-cut/bent 1.5 mm 1.4301), UHMW deck, toe and pin (turned) | 160 |
| Cabling, control | cable chain 1.9 m with chainflex cables; MCU board, 24 V share | 140 | — | — |
| Sensors | NFC reader, ToF/IR, camera, load cell + ADC, light barriers, inductive, IR, sump, door, T/RH | 150 | — | — |
| Cleaning, drain | 2 valves, 30 fan nozzles, drain pump, trap | 100 | 2 riser pipes, sump tray, bottom pan | 90 |
| Structure | door hinges, gasket, lock; 2 port flaps | 90 | **30 shelves** (1.5 mm, 4 folds, gutter) ≈ €13 each; side/rear panels, front frame, top cover, door skin, PIR right wall | 690 |
| Wiper box (6) | — | — | GN 1/6 body with microfibre/silicone base | 20 |
| **Sum** | | **≈ 980** | | **≈ 1,020** |

**≈ €2,000 per ambient column.** About half of it (structure ≈ €700) replaces the customer's "shelving
€500–1,000" (#28). The motion, sensing and control part is ≈ €1,050–1,300. Boxes (90 + reserve) at ≈ €4–6 each
from a custom mould are not included; tooling is ≈ €30–50 k [U].

### 5.4 Failure modes and recovery

| Failure | Detection | Recovery |
|---|---|---|
| **Box tilts** while pulled | The pull acts 14 mm above the shelf, so it cannot tip; 1 m/s² on the car is far below the tipping limit (≈ 10 m/s² for an L-150) | — |
| Box catches the 3 mm gap or a shelf edge | X following error / current > 30 N | Stop, back off 5 mm, re-level Z to the flag, retry once. Then push the box back, mark the position, alarm |
| **Box jams** (deformed box, lid lifted, sticky spill under it) | lid-line barrier before the pull; X current; camera | Box is not pulled if the lid is lifted. A sticky box gets a ±3 mm Y wiggle, then retry. Else the position is locked and the human is asked (UC-13). The rest of the store keeps working |
| Pin misses the slot | Z stops 6 mm early (following error) | Y search ±3 mm, retry; then IR rescan of the box edge |
| Wrong box at the toe | NFC ≠ inventory | Put back, re-inventory the level |
| **Dropped box** into the shaft (only possible if X moved while the car was not flush) | Interlock prevents it; load cell, camera | If it happens: the box lands on the car or in the bottom pan. Human removes it through the door |
| Box dropped by the transport into a hand-over cell | Cell sensor, camera, load cell at the next pull | Transport's case; a spill in the cell drains to the gutter |
| **Spill under a box** (leaking lid, cracked box) | Sump conductivity (liquid); camera on the car (dry or wet); load-cell mass loss | Section 6 |
| **Power loss mid-move** | — | Z: worm is self-locking, the car stays. The box stays engaged: the pin hangs in the slot by gravity. A box half across the gap rests flush on both. Every move is journalled before it starts. On restart: Z flag check, X/Y homing toward the shaft centre (this completes a pull), then the journalled move is finished or reversed, then a re-scan of that level |
| Car, motor or driver dead | Self-test | Store out of service; the human retrieves by hand (5.5); the cell can still cook from what has been handed over |
| Belt break | Z encoder vs motor, flag missing | Worm and belt clamp: the car is caught by a fall stop (2 spring pawls on the rail frame rack) [E]; service |

### 5.5 Manual access (STO-011, TRN-015)

Power off, open the full-height front door:

* **Lane boxes**: every lane's front box is in reach. The ones behind slide forward on the smooth shelf, over
  the 8 mm front stop: at most 3 per lane, ≤ 510 mm deep. Most of the S-levels are at eye height.
* **Car**: turn the hex socket at the top front with a crank. The worm drives the car up or down slowly. It
  holds by itself, so it cannot drop.
* **Inserting by hand** is allowed anywhere. After the door closes, the car re-scans (≈ 2 min) and rebuilds the
  inventory.

## 6. Cleaning

**Normal state.** Boxes are lidded. Shelves touch only box exteriors, which are washed with the box. The
shelves are Zone S (spills can reach them). Nothing in the store is greased: the rails are dry polymer and
the belts PU. There is no mechanism under or beside a lane, only the car in the shaft.

**Spill paths.**

* Liquid follows the 1° shelf slope **away from the shaft**. It reaches the outer gutter (folded into the
  shelf, 2° to the rear), then the vertical duct in the rear zone, then the plinth sump. The sump has a
  conductivity sensor, a strainer, a drain pump and a trap.
* Dry spills stay where they land.

**Detection.**

* Sump sensor (liquid).
* Load-cell mass loss of a box against its last weighing.
* **Camera pass**: the car runs the shaft once a day (≈ 2 min) and compares each shelf image with the last
  one: stains, crumbs, displaced or lid-open boxes.

**Automatic response (no human).**

1. Find the source by camera and mass. Take the leaking box out and hand it to the transport (to the cell:
   decant or discard, then washing).
2. Compact the lane's boxes to its other end (3.2), or into other lanes for the time being.
3. **Wiper box.** This is a GN 1/6 body with a microfibre pad base and a one-way silicone lip on its outer
   lower edge. The transport wets it with warm water and detergent at the cell's rinse-cup spout (K9b 2.6). The
   car pushes it **from the shaft edge to the outer stop** in 162 mm strips, so the lip pushes crumbs and
   liquid into the gutter; when the wiper is pulled back, the lip folds. About 3 strips per half lane; then the
   boxes move over and the other half is wiped. A dry wiper box follows. After use, the wiper goes to the
   well (K9b 2.8). **The store needs no water plumbing for its shelves.** The same wiper, slid along the car
   deck in Y, wipes the deck.
4. **Gutter rinse.** One fan nozzle per gutter on the two riser pipes; 10 s of warm water with detergent,
   then the sump pump. The bottom pan has its own nozzle.
5. Dry with the module's filtered vent fan until RH < 60 % (STO-007), then camera check.

About 5 min per lane. A **monthly full pass** over all 30 shelves takes ≈ 40 min at night.

**Broken box.**

* Cracked but movable: pulled out and handed over as above.
* A large dry spill, e.g. > 100 g of flour or rice spread across a lane: water would make paste in the
  gutter. The machine locks the lane, keeps working with the rest, and asks the human to vacuum it through
  the door (UC-13). **This is the cleaning case S2 cannot do alone.**

**Shaft and mechanism.** The shaft has no walls of its own and no shelf drains into it. The rails and
belt see dust only. Anything that falls lands in the removable bottom pan, which has a rinse nozzle and a
yearly visual check by the human.

## 7. Cold variant

**Same mechanism, turned (S2-B), mounted on the door.**

* **Shell**: 178 cm integrated fridge (static, Liebherr IRBe 5121 class) and 178 cm NoFrost freezer
  (research 4.6). The door is replaced by a custom panel: 60 mm PU between stainless skins, the OEM gasket
  profile, the OEM hinges. **The cabinet, liner and refrigerant circuit are not touched** (CLD-007).
* **Interior** [U, must be measured first]: ≈ 490 W × 440 D with a flat door × ≈ 1,450 H.
* **Layout** (Y from the door): shaft row 182 (car), **one storage lane 182**, 60–75 mm free at the rear for
  the evaporator air. Two lanes and a shaft (546 mm) fit neither the width nor the depth, so the cold store has
  one lane per level (50 % of plan area).
* **Car on the door**: the two Z rails are bolted to the **inside of the new door**. Two cone pins register
  the closed door to the shelf frame (±0.5 mm). The car spans ≈ 450 mm in X.
  * **Z motor on the door's outer face** (warm), its shaft through the door in a PTFE bush: thermal bridge
    ≈ 0.05 W/K.
  * **X and Y motors are on the car, inside the cold**: NEMA 17 rated −30 °C [U], low-temperature bearing
    grease, IP65, conformal-coated encoders, no standby heating (each watt costs ≈ 0.6 W of compressor power).
  * Belts PU, slides drylin, cables PUR −40 °C (research 4.5).
* **Service**: opening the door swings the whole mechanism out, and every lane is open to the human.
* **Shelves**: custom 1.5 mm stainless on the liner's moulded shelf ribs (no drilling), 1° slope to a rear
  gutter. A corner duct runs down to a bottom tray, which drains through a fitting in the door's lower edge
  into the plinth sump.
* **Capacity**: lane ≈ 450 mm, i.e. 2 M + S, L + S or 4 S. About 8 levels at 122 and 5 at 87, minus the
  hatch level, gives **≈ 33–38 positions per shell**.
  * Frozen (≥ 20, CAP-022): **met** with reserve.
  * Chilled (≥ 45, CAP-021): **≈ 10 short**. Upright 1 L cartons (195 mm) also need one 220 mm level. The same
    gap appears in research 4.6, so it is a shell-size limit, not an S2 one.
* **Hatch**: the hatch and vestibule belong to the cold-door design. S2's interface:
  * The car brings the box to the top level.
  * The toe moves round the box end (X, Y, X; 2 s), engages the rear rib, and pushes the box ≤ 80 mm into the
    hatch tunnel.
  * The outer handler pulls it out.
  * The hatch is open ≈ 3–4 s per box (CLD-004 ≤ 10 s). **No extra actuator inside the cold.**
* **Time**: ≈ 13 s inside + ≈ 4 s hatch ≈ **17 s** (CLD-006 ≤ 45 s).
* **Fridge (+4 °C)**: condensation only right after a hatch cycle. The car motors are never warm-cycled, so
  no moisture is pumped into them.
* **Freezer (−18 °C)**: NoFrost keeps the air dry, and frost goes to the evaporator.
  * **Risk: a box returned with a wet base freezes to the shelf.** PP/PE–ice adhesion on 4 pads (7 cm²)
    could need > 80 N. Mitigations: boxes enter only after a dry-air blow in the vestibule (requirement on the
    hatch design); PE pads; a ±3 mm shear wiggle before every pull; force-limited retries, then alarm.
  * **Frost in a rib slot**: the pin stops early, which is detected; retry.
* **Cost per shell** [E]: car + door rails + motors ≈ €450, shelves ≈ €170, door panel ≈ €200, without the
  hatch: **≈ €800**.

## 8. Assessment

### 8.1 Score (1 = poor … 5 = excellent)

| Criterion (weight) | Score | Why |
|---|---|---|
| Simplicity (30 %) | **4** | 3 motors and 1 moving assembly for 89 boxes; flat folded shelves; engagement by Z, no solenoid; no shuffling. Against: custom box mould, ±1 mm flush rule, a car with an overhead beam |
| Hygiene (25 %) | **3.5** | Closed lidded boxes on sloped stainless with gutters; no mechanism beside or under a lane; no grease; the wiper box needs no plumbing. Against: shelves under boxes are reached only by moving boxes; big dry spills need the human; 30 gutters |
| Coverage / fit (20 %) | **3** | Fits 650 × 600 × 2000 with 89 positions (CAP-020 met, all sizes, mixed lengths). Against: 31 % volume (STO-005 55 % missed), equal to an aisle shuttle; cold shell ≈ 10 chilled positions short; K9b stub conflict (needs carriers) |
| Reliability (15 %) | **4** | No blocking boxes, short moves, pull at the base (no tipping); positive pin engagement held by gravity at power loss; tag check at every pick; full manual access. Against: a single car is a single point of failure; freezer ice-bonding |
| Cost (10 %) | **3** | ≈ €2,000 per ambient column incl. the structure that replaces shelving, ≈ €800 per cold shell; box mould ≈ €30–50 k |
| **Weighted** | **3.6 / 5 (72 %)** | |

### 8.2 Honest biggest weakness

**The concept's reason for existing, density, does not survive the 650 mm allotment.** With 176 mm boxes
only three columns fit, and one of them must stay empty. The "dense 3D grid" becomes two lanes and a shaft:
31 % box volume, 137 positions/m, no better than an aisle shuttle in the same column. The real sliding
puzzle (+23 % positions) needs ≥ 1,050 mm and brings 25 s shuffles back (4.3). The cold shells allow only one
lane. What S2 really contributes is a mechanism: **one car in a floorless empty column, engaging a base rib
by its own Z drop**. That is simple and reliable, but it is not a density win.

Second weakness: the box needs a custom mould (pull rib). Third: S2 is incompatible with K9b's stub on the
box, though every dense store is.

### 8.3 Cheapest experiment (≈ €150, 2 days)

A bench rig with **one lane shelf** (1.5 mm stainless, 1°) and a **car deck stub** (UHMW) 3 mm apart:

* **Toe** on a 3D-printer linear axis (X). The 10 mm drop is a printer Z axis or a hand lever.
* **Boxes**: bought GN 1/6-100 and 1/3-150 PP boxes with a hot-plate-welded slotted rib.

Measure:

1. Engagement success over 1,000 drop/pull/push cycles, at flush offsets of 0, ±1, ±2 mm and box position
   errors of ±3 mm (target ≥ 99.9 %).
2. Pull force dry, wet, with an oil film, with sugar crumbs, and full at 5 kg (target ≤ 20 N).
3. **Freezer**: a wet-based box on the shelf in a chest freezer at −18 °C for 12 h; break-loose force with and
   without the wiggle.
4. Rib wear after 1,000 cycles, and rib and tag after 200 dishwasher cycles.

If 1 and 3 pass, S2's mechanism is proven. The rest is ordinary linear-axis engineering.

### 8.4 Open issues and interface requests

* K9b/C4: stubless storage boxes plus permanent stub carriers on the box shelf (2.3).
* Transport gallery: gripper picks the lidded box from above, out of a 214 × 344 open cell at z 1808, with
  ≥ 15 mm free beside the flange on the long sides. Port flaps are opened by the gripper.
* Measure the real interior of the chosen fridge and freezer before the cold variant is detailed.
* Cool zone (CAP-024, 8–15 °C, ≥ 8 boxes) is **not** in this column: the shaft mixes the air of all levels.
  Candidates are a warmer bottom section of the fridge shell or a separate cool drawer.
* Confirm the PP/Tritan rib slot's wash life and the NFC tag's wash rating.
