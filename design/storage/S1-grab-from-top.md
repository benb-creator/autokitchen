# Storage S1 — grab-from-top grid (AutoStore principle) for the 650 mm ambient column

Status: design proposal, storage round (brief `00-storage-brief.md`). Inputs: DECISIONS.md, requirements
(BOX, STO, CLD, CAP-020…026, PHY-001…004), `research/03-storage.md` §1–4, 6–7, K9b §2.
Marks: **[C]** calculated here, **[est]** estimate, **[U]** unverified, must be measured on a sample or a unit.
Machine coordinates as K9b: the ambient column is machine X 1200–1850; in this document local x 0–650 (left
to right seen from the front), y 0 (wall) – 600 (front), z 0 (floor) – 2000; the K9b transport gallery
occupies z 2000–2200 above every module and is **not** part of S1.

## 0. Summary

* **Principle:** 9 stacks of lidded GN 1/6 boxes (3 × 3) in open corner-post cells, up to 14 boxes high, no
  shelves. A CoreXY trolley in a 350 mm robot zone above the stacks lowers a **passive hook gripper on two steel
  tapes**, takes the top box of any stack and sets it on any other stack. A buried box is reached by digging:
  the boxes above it go onto neighbouring stacks. The exit is the top of the front-centre **port stack** under
  a roof hatch, where the gallery picks the box.
* **Density [C]:** 126 box positions (GN 1/6-100) in 650 × 600 × 2000 mm, of which 113 usable (13 slots kept
  free for digging). That is **194 positions per metre nominal, 174 usable**; box envelope 51 % of the enclosure
  (45 % usable). The Rowa-type aisle rack fits only 84 positions in the same 650 mm column.
  **The waste that comes from grabbing from the top is 23 % of the column** (robot zone 17.5 % + dig reserve 5 %),
  not ≈ 50 %. The biggest loss, 27 %, is the walls and gaps of a 3 × 3 GN grid in 650 × 600, which any design
  with these boxes pays too. The customer's ≈ 50 % is right for shallow stacks (3 tiers of 2-high stacks, §4.3).
* **Retrieval [C]:** about 4–5 s for a box on top. The worst case, the bottom box of a full stack (13 boxes
  above, 14 moves), takes **72 s** at the design point (hoist 1.5 m/s) and 106 s with a conservative 0.8 m/s
  hoist. Boxes are placed by expected use: move-to-front on every return, plus pre-digging overnight for the
  planned menu. With that, planned retrievals are one move and the **mean is ≈ 6 s** (STO-003 mean ≤ 15 s met).
  The STO-003 worst case (≤ 30 s for *any* box) is **not met** for boxes more than 5 deep that were not
  pre-dug.
* **Actuators:** 3 motors (2 for CoreXY, 1 hoist servo with brake), 0 in the gripper. **Cost [est]:** machine
  part ≈ €1,100–1,400, plus enclosure and grid ≈ €600 ("shelving"), plus boxes.
* **Biggest weakness:** digging time, and the many grip cycles it causes. Second: hand access to deep rear
  boxes and wet cleaning both need unstacking.
* **Cold:** works in the fridge with the robot inside the top of an upright fridge shell and the exit through
  a **top-wall hatch**. Cold air stays in a horizontal opening, so this is the thermally best exit of all.
  It fits the freezer only with the XY motors outside and a cold-rated hoist motor inside (risk).
  Capacity is about 40 positions per 178 cm shell [U].

## 1. Principle and views

**Principle (3 sentences).** Lidded GN 1/6 boxes stand directly on each other, lid to bottom, in nine open
stacks of up to 14 boxes between stainless corner posts, so each layer costs only the box height plus the lid
(75–210 mm), with no rail, fork or clearance per level. One CoreXY trolley in a single 350 mm robot zone above
all stacks lowers a passive hook gripper on two steel tapes, lifts the top box of any stack clear of the posts
and sets it on another stack; a buried box is dug out by moving the boxes above it onto neighbouring stacks,
where they stay. The exit is the top of the front-centre port stack under a roof hatch, where the K9b gallery
takes the box, and because placement follows expected use (move-to-front, pre-digging for the planned menu),
most retrievals are a single move.

### 1.1 Front view (door removed), x–z

```
 z (mm)                                                            x (mm)
 2200 +-----------------------------------------------------------+
      |   K9b transport gallery (not S1)        hatch over B-F    |
 2000 +====== roof 10 =========================[==== 200 ====]====+
 1990 |  CoreXY rails + belts (z 1970-1990), motors in rear corners|
 1970 |        +---------------+  trolley: hoist servo, drum,     |
 1910 |        |=gripper plate=|  2 tapes, load cell, ToF, camera,|
 1880 |        +---------------+  RFID; plate docked 1880-1910    |
      |        |  lifted box   |  <= 210 (GN 1/6-200 + lid)       |
 1670 |        +---------------+  >= 20 clearance                 |
 1650 +--v-------------v--------------v--------------v------------+ grid top (post lead-ins)
      |  |   A-F       |    B-F       |    C-F       |            |
      |  |   stack     |  PORT STACK  |   stack      |            |
      |  |   <= 14 x   |  (out-box on |              |            |
      |  |   GN 1/6-100|   its top)   |              |            |
      |  |   pitch 110 |              |              |            |
      |  |     ...     |     ...      |     ...      |            |
   80 +--+-------------+--------------+--------------+------------+ floor grate (stainless)
   60 |  drip tray 1.4301, slope 1 % to sump (front left), drain  |
    0 +==feet=====================================================+
      0 15 37 49     225 237        413 425        601 613  635 650
        |  |  |  box A  |  |  box B   |  |  box C   |  |   |
       wall post   176   post  176    post  176    post wall
       zones 12 mm (posts at corners, finger slots at mid-row)
```

### 1.2 Side view (from the right, lane C cut), y–z

```
 z      y=0 wall                                                  y=600 front
 2200 +-------------------------------------------------------------+
      |  gallery                                                    |
 2000 +================== roof ====================[ hatch B-F ]====+
      |  rails, belts                                               |
      |  trolley parks over A-R (rear left) when the door opens     |
 1650 +---+----------------+---+----------------+---+---------------+-+
      |   |  row R         |   |  row M         |   |  row F        | |
      |   |  162           |   |  162           |   |  162          | |door
      |   |  (stacks of    |   |                |   |               | |25 mm,
      |   |   lidded boxes)|   |                |   |               | |gasket,
      |   |                |   |                |   |               | |interlock
   80 +---+----------------+---+----------------+---+---------------+-+
    0 +=========== drip tray, sump at front ===========================+
      0 20 30 42          204 216              378 390             552 564 575 600
        rear service gap 0-20 (PHY-001), rear liner at 20, door y 575-600
```

### 1.3 Top view, x–y (posts `+`, finger slots `:`)

```
 y 600 +----------------------------------------------------------+ front, door
   564 |  +------------+------------+------------+                |
       |  |  A-F       |  B-F PORT  |  C-F       |                |
   470 |  :  176x162   :  roof hatch:            :  <- hooks enter |
       |  |            |  above     |            |    the lane gap |
   390 |  +------------+------------+------------+    at mid-row   |
       |  |  A-M       |  B-M       |  C-M       |                |
   216 |  +------------+------------+------------+                |
       |  |  A-R       |  B-R       |  C-R       |                |
    30 |  +------------+------------+------------+                |
     0 +----------------------------------------------------------+ wall
       0 15 37        225 237      413 425      613 635 650
 cell pitch: x 188 (176 + 12), y 174 (162 + 12); grid 576 x 534 inside 620 x 555
 16 posts: 4 corner L-, 8 edge T-, 4 inner +-profiles, folded 1.5 mm 1.4301, 8 mm wide in the 12 mm gaps
 (2 mm guide clearance per side), flared lead-ins at z 1635-1650; mid-row of every lane gap is free for the hooks
```

### 1.4 Gripper on a box (section through the hooks, x–z)

```
            tape   tape            (yoke slides 15 mm in the plate; slack -> cam indexes 90 deg)
              |     |
   +----------o-----o----------+   gripper plate 172 x 158 x 30, 1.4301, toggle cam inside
 h |  ======= lid (10, clamped) ======= | h      plate rests on the lid; hooks pull the flange
 o |_|=flange                  flange=|_| o    up against it -> lid cannot open in transport
 o   \                                 /  k
 k    \   box body (GN taper)        /       hook tips 7 mm under the flange at mid-span of the
       \____________________________/        +-x short sides; hooks run in the 12 mm lane gap
```

The robot zone is the only height that the grab-from-top principle itself costs:

| z (mm) | Content | Height |
|---|---|---|
| 0–80 | levelling feet, drip tray with sump, floor grate | 80 |
| 80–1650 | stack zone (14 × GN 1/6-100 at 110 pitch = 1540 used) | 1570 |
| 1650–1670 | clearance under a lifted XL box | 20 |
| 1670–1880 | lifted box, at most GN 1/6-200 + lid | 210 |
| 1880–1910 | gripper plate (docked against cones) | 30 |
| 1910–1970 | trolley: hoist drum, servo, load cell, sensors | 60 |
| 1970–1990 | CoreXY rails and belts | 20 |
| 1990–2000 | roof with the port hatch | 10 |
| **1650–2000** | **robot zone ("box + grabber + leeway")** | **350 = 17.5 % of 2000** |

## 2. Box standard

| Item | S1 requirement |
|---|---|
| Footprint | **One stacking footprint: GN 1/6, 176 × 162 mm outer flange** (research/03 family 1, M size). Placed 176 along x, 162 along y. Any height can stand on any other, so the height mix changes without hardware changes (STO-006 for this family). |
| Heights (GN standard depths) | S = 1/6-65 (≈ 1.0 L, pitch 75), M = 1/6-100 (1.5–1.6 L, pitch 110), T = 1/6-150 (2.0–2.2 L, pitch 160), XL = 1/6-200 (≈ 2.5 L, pitch 210; upright 1 L cartons). Oil and vinegar bottles (≈ 300 mm) fit no GN 1/6 height and are assumed decanted into leak-tight XL boxes. Pitch = depth + 10 mm lid; a stack needs **no** per-level leeway. |
| L size (GN 1/3, 325 × 176) | **Not in the baseline.** An L box can only stand in a double cell, and a single L cell cannot be dug because the L boxes above the target have nowhere to go. Option S1-L: the rear two rows of lanes B and C become 2 L cells (each is the other's dig buffer) for long pasta and boxes ≥ 4 L. This turns 4 of the 9 M cells into L cells (§4.3). Otherwise long items (spaghetti 26 cm, BOX-003 ≥ 5 L) must live in another module. |
| Material, temperature, washing | PP or Tritan GN (Araven/Hendi/Cambro PP; PC only if the BPA rule allows), −40…+95 °C, commercial-dishwasher proof (BOX-009). |
| Lid | Flat gasketed press-on lid that sits **on top of** the flange and ends flush with its outer edge (Cambro seal-cover type, no clips), thickness ≤ 10 mm, splash-tight (needed for wet cleaning, §6). Four 1 mm stand-off pads on the top face carry the box above. They give point contact against freeze-bonding (§7) and against smearing. |
| Rim / gripping | Continuous flange, ≥ 7 mm overhang over the body, ≥ 2.5 mm thick, **free underside at mid-span of both 162 mm short sides over ≥ 25 mm** (hook seats; a moulded 22 mm notch would centre the hook — optional). Both the S1 gripper and the gallery's port gripper use these hook seats. **[U: flange overhang and stiffness under 2 × 30 N must be measured on PP samples.]** |
| No protrusions | **Nothing may stick out beyond the 176 × 162 flange outline.** K9b's moulded bayonet stub (Ø 22 × 40 + stand-off on the rear short side) would need a ≥ 60 mm stub lane per row and cuts the column from 9 to 6 cells (−33 %). Proposed interface: the lid station puts the opened box into a GN 1/3 stub carrier (as K9b already does for STOW packs), or the cell hand grips the flange. **To be settled with the cell designer.** |
| Bottom | Flat, with a perimeter foot ring. It stands on the lid below without rocking and drains when washed upside down. |
| Identity | UHF RFID inlay, encapsulated and rated for washing and −40 °C [U: 11,000 cycles], welded into a flange corner and read by the trolley at every pick. A DataMatrix is laser-marked on the flange side for the cameras at the lid station and port (BOX-006, STO-009). |
| Mass | ≤ 5 kg gross (BOX-004); every lift is weighed by the trolley load cell (BOX-012, ±5 g with 0.5 s settling [est]). |

Bought GN 1/6 boxes satisfy everything except the optional hook notch and the RFID inlay, so BOX-011 is
met with one added part (the tag).

## 3. Retrieval sequence

### 3.1 Motion data (design point)

| Axis | Data [est] |
|---|---|
| Hoist | 1.5 m/s, 5 m/s²; 200 W 48 V servo, 5 : 1 planetary, spring-applied brake, Ø 60 drum, 2 stainless tapes 0.1 × 15 mm |
| X/Y (CoreXY) | 0.5 m/s, 2.5 m/s² with a 5 kg box; moves of 0.17–0.40 m |
| Grip or release | 0.5 s each: touch-down (load cell sees the load drop), 12 mm over-travel indexes the cam, 10 mm check lift with weighing |
| Dig move | the box is lifted only until its bottom clears the post tops (z 1660), not to the dock |
| Final move | full dock (z 1880), weigh, read RFID, then travel to the port |

### 3.2 Worst case: bottom box of a full stack, retrieved unplanned

Situation (all-M grid): target T is the 14th (bottom) M box in rear-left cell A-R. The stack top is z 1620 and 13 boxes
lie above T. Neighbouring stacks with room: A-M (9 boxes, top 1070), B-R (10, top 1180), B-M (10, top 1180),
C-R (11, top 1290); 16 free slots in total. The trolley starts parked over A-R. Times are from the motion
model in 3.1 **[C]**.

| # | Move | Source top z | Destination (top z before) | Time s |
|---|---|---|---|---|
| 1 | box 1 (top) A-R → A-M | 1620 | A-M (1070) | 4.3 |
| 2 | box 2 → A-M | 1510 | A-M (1180) | 4.3 |
| 3 | box 3 → B-R | 1400 | B-R (1180) | 4.6 |
| 4 | box 4 → A-M | 1290 | A-M (1290) | 4.5 |
| 5 | box 5 → B-R | 1180 | B-R (1290) | 4.7 |
| 6 | box 6 → A-M | 1070 | A-M (1400) | 4.6 |
| 7 | box 7 → B-R | 960 | B-R (1400) | 4.8 |
| 8 | box 8 → A-M (A-M now full, 14) | 850 | A-M (1510) | 4.7 |
| 9 | box 9 → B-R (B-R now full) | 740 | B-R (1510) | 4.9 |
| 10 | box 10 → B-M (diagonal neighbour) | 630 | B-M (1180) | 5.9 |
| 11 | box 11 → C-R | 520 | C-R (1290) | 6.4 |
| 12 | box 12 → B-M | 410 | B-M (1290) | 6.0 |
| 13 | box 13 → C-R | 300 | C-R (1400) | 6.5 |
| 14 | **T**: plate down 1.58 m, grip, up 1.69 m to dock, weigh and RFID check (0.3 s), XY 0.40 m to B-F, down 0.26 m onto the port stack, release, up | 190 | port stack B-F (1510) | 5.9 |
| | **Total: T sits on the port, gallery may take it** | | | **≈ 72 s** |

Each dig move breaks down as: plate down (0.1–1.4 m), grip 0.5 s, lift until clear of the posts, XY 0.19 m,
down onto the destination, release 0.5 s, plate up, XY back. Hoist travel dominates: about 60 % of the time.
With a conservative 0.8 m/s, 3 m/s² hoist and 0.7 s grip cycles, the same case takes **≈ 106 s**.
The dug boxes are **not** put back. They stay where they were set, because random storage needs no restore
moves. As they were above T, they were used more recently than T, so leaving them on top of other stacks is
the right outcome.

**Retrieval time against depth** (k = number of boxes above the target, full stack, design point) **[C]**:

| k | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 8 | 10 | 13 |
|---|---|---|---|---|---|---|---|---|---|---|
| s | 3.7 | 8.3 | 12.9 | 17.6 | 22.5 | 27.4 | 32.4 | 42.9 | 53.6 | 70.6 |

STO-003 (≤ 30 s for any box) holds only for k ≤ 5, i.e. the top 6 boxes of every stack (54 of 126
positions). A software cap on stack height trades capacity for the worst case. The same hardware gives:

| Stack cap | Positions (usable after dig reserve) | Worst case |
|---|---|---|
| 14 (baseline) | 126 (113) | 72 s |
| 11 | 99 (89) | 54 s |
| 9 | 81 (73) | 43 s |
| 6 | 54 (49) | 27 s — STO-003 met, but CAP-020 (70 + empties) not |

**So in 650 mm, S1 cannot meet both CAP-020 and the STO-003 worst case.** It relies on prediction instead.

### 3.3 What normally happens: placement by expected use

1. **Move-to-front on every put-away.** A returned box always goes on top of a stack, so recently used boxes
   gather in the top layers by themselves (as in AutoStore). For a single list, move-to-front is provably
   within a factor 2 of the best static order (Sleator–Tarjan); 9 stacks behave similarly [est].
2. **Pre-digging in idle time.** The menu is planned (UC-04), and the robot is idle about 20 h a day. Every
   night, and again ≥ 30 min before each planned meal, it puts the boxes the next meals need on top of stacks
   near the port: 9 stacks × 2 top layers = 18 positions at k ≤ 1, more than the 10–15 ambient boxes of a
   4-person meal. Night moves run in a quiet mode (hoist at 0.5 m/s, ≈ 40 dB(A) [est]).
3. **Slow stock goes deep.** Empty boxes, long-term reserves and the guest-shop space sit low, preferably in
   the port stack, which keeps its top high (§3.4).
4. Expected mix: ≥ 85 % of retrievals at k = 0, 10 % at k ≤ 2, 5 % unplanned and deep (k ≈ 6) →
   **mean ≈ 0.85 × 3.7 + 0.10 × 10.6 + 0.05 × 32 ≈ 6 s [est]**, and a 4-person meal costs ≈ 2–3 min of storage
   time (retrievals and returns), spread over the cooking.

### 3.4 Port and put-away

* **Port stack B-F.** It holds 13 slow boxes (the empty reserve), so its base stays at z 1480–1540. The
  out-box is set on top, and the gallery hoist reaches it from z 2000 through the roof hatch (≤ 450 mm
  reach, as K9b already lowers boxes 450 mm into the cell). One more box may wait under the out-box as a
  decoupling buffer (TRN-008). A tall out-box sticks up into the robot zone, so the trolley routes around
  B-F while the port is occupied.
* **Handshake:** S1 reports the port as free / out-box ready / locked. While the gallery is in the hatch,
  the trolley stays out of cell B-F (software interlock plus the gallery's position signal).
* **Put-away (≈ 5 s):** the gallery sets the returned box on the port. The trolley lowers onto it (0.2 m),
  grips, docks, weighs (the mass difference updates the inventory, BOX-012), reads the RFID, travels to the
  stack chosen by expected next use, sets the box down, releases and docks empty. No digging is ever needed
  for put-away.
* **Port stack dig:** if a slow box under the port is needed (e.g. empties for ingestion), the robot digs it
  in idle time like any other.

## 4. Density

### 4.1 Positions and volume [C]

Enclosure: 650 × 600 × 2000 mm = 780 L. The gallery above (z 2000–2200) belongs to transport. Figures with
the full 2200 mm are given in brackets.

| Quantity | Value |
|---|---|
| Cells | 9 (3 × 3) GN 1/6 |
| Positions, all GN 1/6-100 (pitch 110, 14 per stack) | **126** nominal; **113** usable with 13 slots kept free for the worst dig |
| Positions with S boxes (pitch 75) | 20 per stack; T (160): 9; XL (210): 7 |
| Positions per metre of wall | **194 /m** nominal, **174 /m** usable |
| Box envelope (176 × 162 × pitch) | 126 × 3.14 L = 395 L = **50.7 %** (46 %); usable 354 L = **45 %** (41 %) |
| Box content (GN 1/6-100 ≈ 1.55 L) | 195 L = 25 %; usable 175 L = 22 % |
| STO-005 (≥ 55 % envelope) | **not met (51 %)**, close to the research figure for the aisle rack (50 %) |
| Same column with the Rowa-type aisle rack (research A: 3 boxes per face and level × 14 levels × 2 faces) | 84 positions, 38 % envelope. **S1 holds 50 % more boxes in 650 mm** |

**Where the 780 L go (all-M, full grid):**

| Share | Volume | What |
|---|---|---|
| 45.4 % | 354 L | usable box positions (113) |
| 5.2 % | 41 L | **digging reserve** (13 positions kept free) |
| 17.5 % | 137 L | **robot zone** (box + grabber + leeway + gantry, z 1650–2000) |
| 26.8 % | 209 L | walls, posts, 12 mm gaps, margins: the 3 × 3 GN 1/6 grid covers only 65.8 % of 650 × 600 |
| 4.0 % | 31 L | feet, drip tray, grate (z 0–80) |
| 1.0 % | 8 L | unused 30 mm at the top of the stack zone |

The waste caused by **grabbing from the top** is the robot zone plus the dig reserve: **≈ 23 %**. The single
largest loss (27 %) is the footprint: 176 × 162 boxes do not tile 620 × 555. A denser box footprint would
need custom boxes (BOX-011).

### 4.2 Reference allocation (2-person household, CAP-020, CAP-023)

| Cell | Height class | Holds | Free |
|---|---|---|---|
| A-F, A-M | S (20 each) | 30 seasonings + 8 empty S | 2 |
| A-R, B-R, C-R | M (14 each) | 30 M food | 12 |
| C-F, C-M | T (9 each) | 10 T food (cans, jars, cartons) + 5 empty T | 3 |
| B-F (port) | M | 13 empty M (slow; keeps the port high) | 1 = the out-box place |
| B-M | free | dig buffer, guest shop (CAP-013) | 14 |
| **Total** | | **70 food + 26 empty = 96 boxes** | **31 slot-equivalents** + the port place (≥ 13 needed) |

Food volume 30 × 1.0 + 30 × 1.55 + 10 × 2.1 ≈ 97 L ≥ 45 L; mass capacity far above 18 kg; ≥ 30 smallest
boxes. CAP-020 is met, and S1 alone also holds the machine's whole empty-box reserve (CAP-023 ≥ 25).
Height classes per stack are a preference only. Any stack takes any height.

### 4.3 Variations that reduce the waste or the digging

| Variation | Waste from top-grab | Positions | Worst case | Motors | Verdict |
|---|---|---|---|---|---|
| **Baseline**: one robot zone over 14-deep stacks | 23 % | 126 (113) | 72 s | 3 | **chosen** |
| Software stack cap (3.2) | same hardware; free cells | 81–126 | 43–72 s | 3 | **kept as a setting** |
| Placement by expected use: move-to-front, pre-dig, slow stock deep (3.3) | 0 | – | planned: 1 move | 0 | **in baseline**; mean ≈ 6 s |
| Shallow stacks, 2 tiers × 5 deep (each tier has its own robot zone; one upper cell is the lower tier's port shaft) | 36 % | ≈ 85 | 23 s | 6 | rejected: holds CAP-020's 70 food boxes but not the empties, and doubles the robot |
| Shallow stacks, 3 tiers × 2 deep, i.e. the customer's ≈ 50 % case | 55 % | ≈ 50 | ≈ 8 s | 9 | rejected: CAP-020 not met |
| "Grabber only in the top layer": each stack on a lead-screw lift that raises it one pitch, so the hoist stroke is ≈ 120 mm | 23 % | 126 | ≈ 40 s | 3 + 9 lifts | rejected: 9 extra drives under the food |
| The AutoStore form proper (robot rides on the grid and lifts the box into its body) | ≈ same 350 mm | – | – | 4–5 | the baseline is this, with a CoreXY instead of wheels |
| **Borrowed headroom ("hinged lid") S1-G**: no own robot zone; the gallery carriage (+Y axis, 1.9 m hoist) digs through hinged roof flaps, using its own height for the lifted box | ≈ 5 % (dig reserve) | ≈ 153 (17 per stack) | ≈ 75 s, and the gallery is blocked meanwhile | −3 in S1, +1 in the gallery | **idea for the system round**: only worth it if the gallery must be ≈ 330 mm high anyway to carry an XL box; it costs TRN-008 decoupling and idle-time pre-digging becomes gallery time |
| Pair lift: a second, 110 mm longer hook pair lifts the top 2 boxes of a homogeneous stack | 23 % | 126 | ≈ 40 s | +1 small selector | possible upgrade if the worst case matters |
| Max box height T 150 instead of XL 200 | 20 % | +2 | – | – | rejected: XL needed for upright cartons |
| Nested empties: 25 empties without lids nested, ≈ 0.55 m instead of ≈ 2.9 m of stack; lids kept at the lid station | – | +≈ 20 | – | – | option, if the lid station can keep 25 lids [U: nest pitch] |
| S1-L: rear two cells of lanes B and C become 2 GN 1/3 cells | – | 70 M + 18 L | – | – | option for long pasta; empties then must go elsewhere |

## 5. Actuators, seals, sensors, parts, cost, failures, manual access

### 5.1 Actuators and the passive gripper

| # | Actuator | Type [est] | Travel |
|---|---|---|---|
| 1, 2 | CoreXY X/Y | 2 × NEMA 23 closed-loop steppers fixed in the rear top corners, GT3 9 mm belts, 3 MGN12 stainless or igus drylin N dry-running rails | x 376, y 348 |
| 3 | Hoist | 200 W 48 V integrated servo with multi-turn absolute encoder, 5 : 1 planetary, spring-applied brake, Ø 60 drum, 2 stainless tapes 0.1 × 15 mm (each ≈ 2.2 kN; bending stress on Ø 60 ≈ 330 MPa) | z 1880 → 190 (1.69 m) |
| – | Gripper | **passive, 0 motors, 0 wires** | – |
| – | Roof hatch | spring flap with brush seal, opened by the gallery (transport side) | – |

**Passive toggle gripper ("ballpoint-pen" principle).** The two tapes end on a yoke that slides 15 mm inside
the gripper plate. When the tapes are taut, the yoke is pulled up against a stop. When the plate rests on a
lid and the hoist pays out ≥ 12 mm more, the yoke drops, and its pin advances a heart-shaped indexing cam by
90°. The cam alternates the two hooks between *open* (tips 4 mm outside the flange) and *closed* (tips 7 mm
under the flange). A pick and the following set-down are always two successive slack events, so the cycle
alternates by itself: close on the box, open after setting it down. Under load the cam cannot index, because
the tapes are taut and the hook seats are angled 5° inward, so a loaded gripper cannot open. A snag is
detected by the load cell within < 3 mm of payout, the hoist stops before the 12 mm needed to index, and the
gripper does not toggle. A magnet on the cam is read by a Hall sensor in the trolley when docked. Nothing on
the moving plate needs power, which matters in the freezer (§7). The principle is that of push-push latches and
of the self-releasing hooks used on cranes. **[U: reliability over 10⁵ cycles is the first experiment, §8.]**
Fallback: an electric hook drive with a micro gear motor and a flat cable reeled beside the tapes
(+1 actuator, a moving cable).

**Seals:** none dynamic; the module is a dry zone. Static: door gasket (STO-008), brush seal at the roof
hatch, cable glands, drain trap.

**Sensors:** load cell 10 kg in the trolley (weighing, touch-down, slack and snag detection); Hall sensors
for home X, home Y, dock and cam state; ToF distance sensor looking down (stack-top height per cell:
missing, displaced or open box, STO-013); camera with LED looking down (lids, spills, broken box); UHF RFID
reader in the trolley (identity at every pick); door interlock; leak electrodes in the sump; T/RH sensor
(STO-007).

### 5.2 Parts and cost (machine part, small series, net) [est]

| Part | Bought / custom | € |
|---|---|---|
| 2 closed-loop NEMA 23 + drivers | bought | 140 |
| Hoist servo 200 W, planetary, brake | bought | 220 |
| Rails, carriages, belts, pulleys, idlers | bought | 150 |
| Stainless tapes; turned drum | bought / custom | 30 |
| Load cell + amplifier; ToF; camera + LED | bought | 70 |
| UHF RFID reader + antenna | bought | 120 |
| Controller, 48 V 400 W PSU, energy chain, cabling | bought | 230 |
| Hall sensors, door interlock, leak and T/RH sensors | bought | 50 |
| Spray valve, trolley nozzle, hose, drying fan, drain trap | bought | 90 |
| CoreXY plates, trolley, docking cones | custom (laser, bent) | 120 |
| Passive toggle gripper | custom (laser, turned, springs) | 150 |
| **Machine part** | | **≈ 1,370** (lean: no RFID on the trolley, NEMA 17, no camera ≈ 1,180) |
| Enclosure: sides, roof with hatch, liner, gasketed door | custom | 350 |
| Grid: 16 posts with lead-ins, top frame, floor grate, drip tray with sump | custom | 250 |
| **Enclosure and grid (the "shelving")** | | **≈ 600** |
| Boxes: 96 × (GN 1/6 PP + lid + RFID tag) ≈ €13 (the same for every storage design) | bought | ≈ 1,250 |

Against #28 (≈ €2,000 for the whole machine part), one ambient column costs ≈ 60–70 % of that budget. Per
position it is cheap: ≈ €10–12 of machine part per usable position.

### 5.3 Failure modes and recovery

| Failure | Detection | Automatic recovery | Human |
|---|---|---|---|
| Box snags on a post (tilted, flange catches) | load-cell deviation > 15 % or stall within 2 mm | stop; lower 20 mm; re-seat; retry at 0.2 m/s with ±1 mm XY dither; after 3 tries the cell is marked *blocked* and the rest of the grid carries on | clear the cell |
| Gripper does not engage (cam out of phase, damaged flange) | check lift weighs only the plate | set down again (the cam indexes), retry; on a second failure the box is marked *ungrippable* | lift it out |
| Box dropped | weight loss; ToF/camera | the hooks are load-locked, so this is unlikely. Inside a cell the box falls along the posts onto its stack and stays contained; if it is upright, it is re-gripped | if tilted: remove |
| Tape breaks | load step | the second tape alone has a safety factor ≈ 35; the plate tilts and wedges between the posts and cannot fall | replace the tape (service) |
| **Power loss mid-move** | – | brake and passive gripper hold; inside a cell the posts hold the box sideways. On restore: absolute hoist encoder (z), write-ahead move journal, load cell (box present?) and RFID → finish or undo the move, re-home XY only when docked: **< 1 min, STO-010 met** | – |
| Door opened by a human | interlock | on closing: ToF height scan of 9 stacks + RFID of the 9 top boxes (≈ 30 s); every stack whose height or top identity changed is re-read by unstacking and restacking (≈ 2.5 min per stack). Typically < 3 min | the worst case (everything reshuffled) is ≈ 25 min, **STO-010 not met**; the UI asks the human to put dug boxes back on any stack top |
| Lid ajar, box displaced | ToF +5 mm, camera | re-seat by pressing with the plate (8 N); else out to the lid station | – |
| Gallery and trolley meet at the port | handshake, hatch switch | S1 never enters cell B-F while the gallery holds the port lock | – |

### 5.4 Getting a box out by hand (STO-011)

* **Power on, service mode:** on request S1 brings the box to the top of a front-row stack, parks and
  unlocks the door.
* **Power off:** open the door and push the unpowered CoreXY trolley aside by hand (it is back-drivable; the
  hoist brake holds the docked plate). All stack tops are at ≤ 1620 mm and can be reached from the front.
  The boxes are transparent, the UI or a label says which cell and level, and nothing holds a box but
  gravity. A front-row box takes ≈ 5 s per box above it, ≈ 1 min for the bottom one. **A deep rear-row box
  is behind the front stacks of its lane**, so those must be unstacked first: up to ≈ 40 boxes, ≈ 3–4 min.
  STO-011 is met to the letter (from the front, no tools, power off) but is not convenient.
* **Option S1+P, pull-out lanes:** each lane is a self-contained 3-cell rack on a full-extension larder
  pull-out (bottom runner + top guide, ≥ 100 kg [U]). Pulled out, its three stacks stand in the room, and
  any box is dug by hand from the top in ≤ 1 min. It also opens the grid for inspection and jam clearing.
  Lane pitch 196 instead of 188 still fits (3 × 196 + 12 = 600 ≤ 620); +€300–450, +3 lane-home switches.
  **Recommended if STO-011 shall be convenient.**
* What remains of "accessible from the top" in a 2.2 m machine: the true top is under the gallery and above
  head height, so access is from the front to the top of every stack at ≤ 1.6 m.

## 6. Cleaning

**Design for cleanability.** There are no shelves, no rails under boxes and no mechanism in the stack zone.
The only surfaces in the grid that a box touches are the post edges (flange sliding contact), the floor
grate (bottom box), the lid of the box below (box bottom) and the gripper plate and hooks (lid top, flange
underside). All of these are stainless or PP and outside Zone F. The robot zone above is dry: dry-running
polymer guides and PU belts, no grease above the boxes (TRN-011).

| Event | Detection | Machine response |
|---|---|---|
| **Crumbs, dust** (from box outsides) | camera on lids; schedule | they fall through the open cells to the grate and tray; a weekly flush nozzle at the high end of the tray rinses them to the sump and drain (drain connection shared with the machine, air break) |
| **Spill from a leaking box** | sump leak electrodes; weight loss of the box at its next lift (±5 g); wet lid in the camera image | the box is found by elimination: the leaking stack is the one above the wet tray zone. The robot unstacks that stack onto free space (the dig reserve suffices) and sends the leaking box via the port to the cell, where its contents are decanted into a fresh box and the box is washed. Boxes below it with wet outsides go out one by one for an exterior rinse and dry **[assumes the cell or lid station can rinse a lidded box outside — to be agreed]**. Then a cell wash (below) |
| **Broken box** | camera; ungrippable | **human task**: open the door, remove the pieces; then an automatic cell wash. PP GN boxes rarely break (BOX-009 drop test), and contents are lidded |
| **Box bottom soiled** (it stood in the cell) | camera at the lid station | rinse before it returns. Otherwise the stack carries soil from bottom to lid. **Stacking creates this contact path, which racks do not have** |
| **Routine cell wash** (monthly, at night) | schedule | the robot empties one cell onto free space (≈ 14 moves, ≈ 1.5 min). The trolley's full-cone nozzle (60 °C water with detergent, then a clear rinse, from the machine's supply; the valve sits at the inlet, so the hose is dry the rest of the time) sprays down the empty cell for 60–90 s while circling. Water runs to the tray, sump and drain. The fan and dehumidifier dry the module to RH ≤ 65 % (≈ 1–3 h [est]). About 3 cells per night, the grid in 3 nights |

**Honest limits.** Spraying an empty cell also wets the outsides of the neighbouring stacks, because the
cells have no walls, only posts. Their boxes are lidded and gasketed, so this only rinses them, but every
ambient box must be splash-tight (BOX-007 already requires that drips cannot get in). The robot zone
(gantry, belts) cannot be washed automatically; it is dry and wiped at the yearly service (UC-10). The
deep wet clean is gentle and slow compared with a rack, where each shelf is reachable. In S1 a surface can
be cleaned only after the robot has emptied the cell next to it.

## 7. Cold variant

### 7.1 Fit in the K9b cold allotment (1200 mm = two 600 mm, 178 cm built-in shells)

```
 front view, one shell (fridge or freezer), interior figures [U: research/03 4.1 estimate]
 z 2200 +----------------------------------------------+
        |  gallery                                     |
   2000 +==========================[ gallery port ]====+
        |  128 mm gap: hatch drive, XY motors (freezer)|
 ~1872  +=== cabinet top wall ======[TOP HATCH 200x190]=+   <- the only cabinet modification
        |  robot zone 350 (CoreXY, trolley, hoist)     |      (CLD-007 "at the exit")
        |----------------------------------------------|
        |  2 x 2 stacks GN 1/6, stack zone ~1120       |
        |  [ R / empties ]  [ port stack ]  (front row) |   interior ~480 W x 380 D x 1500 H
        |  [ M ]            [ S ]           (rear row)  |   cells x 2 x 188 + 12 = 388 <= 480
        |                                              |         y 2 x 174 + 12 = 360 <= 380
  ~320  +----------------------------------------------+
        |  compressor, plinth                          |
      0 +----------------------------------------------+
        OEM front door kept unmodified, used as the service door
```

| Item | Fridge (+4 °C) | Freezer (−18 °C) |
|---|---|---|
| Positions [C on U interior] | 4 stacks × 10 M = 40; with one S stack (15) ≈ 45 | ≈ 40 |
| Against the requirement | CAP-021 ≥ 45: **borderline** | CAP-022 ≥ 20: comfortable |
| Exit | **hatch in the cabinet's top wall** above the port stack: insulated flap 40 mm PU, heated gasket frame (≈ 5 W, CLD-014), small gear motor on the cabinet top (+1 actuator) | same |
| Open time per passage (CLD-004 ≤ 10 s) | ≈ 3–4 s: only while the gallery hoist passes. **Digging is done with the hatch closed**, so dig time costs no cold | same |
| Air exchange | **horizontal opening, cold air below: stable layering**, the exchange is mostly the displaced box volume plus mixing, ≤ 10 L per opening [est], compared with 28 L for a vertical 206 × 150 hatch (research 4.4). Cold air does not pour out of a top opening | ≈ 0.7 kJ per passage [est]; at 5 per day (CAP-012) negligible |
| Motors | all three inside at +4 °C: IP65 steppers and servo, conformal-coated electronics outside; ≈ 10–20 W while moving, < 1 W parked | **XY motors outside** on the cabinet top, shafts through 2 bushings in a machine-made "exit plate" that replaces a 450 × 350 section of the top wall around the hatch. **The hoist motor rides on the trolley inside at −18 °C**: cold-rated IP67 servo with −40 °C H1 grease, kept warm by ≈ 3–5 W of idle current (CLD-009). The alternative is a fixed winch outside with crane-style reeving to the trolley (more pulleys and rope) |
| Gripper and sensors inside | passive gripper, no electrics | passive gripper (an advantage); the trolley load cell drifts at −18 °C [research 4.5], so it is used only for relative slack and snag detection, and **weighing moves to the lid station** |
| Frost and condensation | condensation little, since humid air enters only through the top hatch; stainless and dry-running polymer guides | the NoFrost evaporator collects most frost; PU belts flexible to ≈ −30 °C [U]; carriage wipers. **Freeze-bonding of stacked boxes**: a box returned with a wet outside freezes to the lid below. Freezer returns are rare (thawing goes freezer → fridge, CLD-013; nothing is refrozen); returned boxes are blown dry; the lid stand-off pads keep ice bridges small enough for the hoist (≥ 100 N) to break |
| Raw meat (CLD-011, CLD-003) | R boxes are leak-tight (BOX-008) and live in the bottom layers of one stack. **Digging can put an R box above RTE boxes for ≈ 10 s** (logged), which conflicts with a strict reading of "below". The 0–2 °C sub-zone needs a separate compartment, since S1 has one air volume | – |
| Human access | open the OEM door: the 2 front stacks are directly reachable, the rear ones only after unstacking | same, with gloves |

**CLD-007 risk.** The top hatch leaves the door untouched, but it cuts the cabinet top. This is allowed "at
the exit" only if no refrigerant line (skin condenser loop), sensor or cable runs there **[U: check the
chosen model by thermography or a service manual before cutting]**. The freezer additionally needs the exit
plate with two shaft bushings. If the top wall cannot be cut, the exit must go through the upper door. A
top-grab grid then loses its thermal advantage and needs a front nest inside the cabinet, costing one stack.

**Chest freezers** are the natural form of S1: top access, robot fully outside, and only the passive gripper
on its tapes enters the cold. But a chest (≈ 850 mm high) wastes the 2 m column, so it is not proposed for
this machine.

**Verdict, cold:** S1 works in the fridge, giving ≈ 40–45 positions (about what the research expects for the
aisle rack in a shell), with the best exit thermally. In the freezer it works only with a cold-rated moving
hoist motor; that risk is shared with any carriage-based design.

## 8. Score, biggest weakness, cheapest experiment

Scores 1 (poor) – 5 (excellent), weights from the brief.

| Criterion | Weight | Score | Reason |
|---|---|---|---|
| Simplicity | 30 % | 4 | 3 motors, a passive gripper, no mechanism in the stack zone, 3D-printer-class bought parts, bought GN boxes. Against: digging and inventory logic (journal, re-scan) carry the complexity in software |
| Hygiene | 25 % | 3 | open posts, no shelves, lidded boxes, dry robot zone above. Against: box bottom on the lid below is a contact path; a spill runs down a whole stack; wet cleaning needs unstacking and wets neighbours; a broken box needs a human |
| Coverage / fit | 20 % | 3 | **highest density of the classic mechanisms in 650 mm** (126/113 positions, CAP-020 plus all empties). Against: STO-003 worst case missed (72 s), single footprint (no L without losing 4 cells), STO-005 51 % < 55 %, the K9b stub must leave the box, STO-011 only tediously by hand |
| Reliability | 15 % | 3.5 | few parts, brake and load-locked hooks, contained falls, < 1 min recovery after power loss. Against: digging multiplies grip cycles (≈ 100–200 per day [est]), and a reshuffled grid needs a long re-scan |
| Cost | 10 % | 3.5 | machine part ≈ €1,100–1,400 + enclosure ≈ €600; ≈ €10–12 per usable position |
| **Weighted** | | **3.4 / 5** | |

**Honest biggest weakness: digging time, and its knock-on effects.** A box at the bottom of a full stack
needs 14 moves and ≈ 72 s (106 s with a conservative hoist), 2–3 times the STO-003 limit. Every dig also
multiplies wear and the chances of a misgrip. S1 works only because the machine knows its menu and can
pre-dig in idle time. For an unplanned request (a recipe changed at short notice, a human asking for a deep
box) the wait is ≈ 1 min. The same unstacking also makes hand access to deep rear boxes and wet cleaning
laborious.

**Cheapest experiment (≈ €750, 2 weeks).** Build one lane of 2 cells, 1.6 m high: 6 bent stainless posts, a
floor plate, 28 real GN 1/6-100 PP boxes with seal-cover lids (≈ €360). Over it, a fixed gantry with one
manual X stroke (a 3D-printer CoreXY kit is enough), the tape hoist with the 200 W servo, and the passive
toggle gripper as an FDM prototype (non-food zone, allowed by #4). Measure:

1. gripper engagement and release on real GN flanges: 1,000 cycles with 0.2–5 kg, a 2 mm tilted box and a
   lid ajar → target < 1 failure in 10³, and no unintended toggle on deliberate snags;
2. flange overhang and stiffness under the hooks at 5 kg, with the box first at +20 °C, then after a night
   at −18 °C;
3. time per dig move against hoist speed, compared with the model in §3 (4.3–6.5 s);
4. snags on the post lead-ins and stack-height drift after 200 restacks (ToF).

If (1) or (2) fail, S1 falls back to the electric gripper. If (3) is far off the model, the worst case and
the stack cap in §3.2 must be recalculated before S1 is compared with the pusher and belt designs.
