# Storage S5 — new storage ideas for the 650 mm ambient column

Status: design proposal, storage round (brief `00-storage-brief.md`). Inputs: DECISIONS.md, requirements
(BOX, STO, CLD, CAP-020…026), `research/03-storage.md` §1–3, K9b §2.1–2.4, and the summaries of S1–S4.
Marks: **[C]** calculated here, **[est]** estimate, **[U]** unverified, must be measured.
Coordinates and accounting as in S1/S4: ambient column = machine X 1200–1850; local x 0–650 (left to right
from the front), y 0 (wall) – 600 (front), z 0 (floor) – 2000. The K9b gallery (z 2000–2200) is not part of
the store. Enclosure 650 × 600 × 2000 = 780 L; box envelope GN 1/6-100 = 176 × 162 × 110 mm (lid included).

**Reference (same accounting):** S1 grab-from-top 126 nominal / **113 usable**, worst case **72 s**;
S2 pushers with a shaft column **89**, **11.5 s**; S3 belts with a lift aisle **≈ 92**, **18 s**;
S4 aisle shuttle **96**, **6–9 s**.

**The geometric fact behind all four.** 553 mm of usable depth hold exactly three rows of 162 mm boxes, and
610 mm of inside width exactly three lanes of 176 mm: **9 boxes per level**. Any design that needs a box-sized
access space next to every box (aisle, shaft) keeps only **6 per level** (S2, S3, S4). Only top access (S1)
keeps 9, and pays with a robot zone, a dig reserve and digging. A new idea is only worth working out if it
either keeps 9 per level without digging, or makes the 6-per-level designs hold more food per position.

## 1. Candidate principles (quick verdicts)

| # | Principle | One-line verdict |
|---|---|---|
| C1 | **Vertical carousel / paternoster** (trays of 3 boxes on a chain loop in y–z, the gallery picks from the carrier at the top apex) | 1 motor, but rigid carriers collide in the turns unless the chain pitch ≥ √(depth² + height²) ≈ 210–230 mm for a 120 mm tray [C, §2] → **≈ 51 positions**. Rejected: below CAP-020. |
| C2 | **Rotating column racks (lazy-susan towers)** about a vertical axis | A circle in a 610 × 553 square holds only 4 GN 1/6 per level around a dead hub, ≈ 64 positions, and still needs a lift in a corner that has no box-sized room. Rejected. |
| C3 | **Spiral / helical rack** (gravity helix, or a rotating radial car in a cylindrical tower like a tape silo) | Gravity helix is FIFO (blocking). Radial car: the diagonal slots collide with the side slots (checked [C]), so ≤ 6 per level = S2. Rejected. |
| C4 | **Boxes hanging from a rail like a garment conveyor** (columns of boxes circulating in plan = horizontal carousel) | A loop in plan needs ≥ 2 × 2 columns plus turn room; 650 × 600 is one turn. Fits only a long module (cold 1200 or a 4.2 m option). Rejected for the column. |
| C5 | **Rotating drum / Ferris wheel** (gondolas round a horizontal x-axis) | A paternoster with a worse fill (Ø ≤ 550, so 3 wheels stacked, each needing its own exit). Rejected. |
| C6 | **Ring stacks: two columns of stacked cradles that circulate as a closed ring** (ascending column, top transfer, descending column, bottom transfer; the paternoster with its turns replaced by sideways pushes) | Keeps the cradles touching (no turn clearance), no aisle, no robot zone, no digging; exit = top of the front column, gallery picks from above. **Worked out, §3.** |
| C7 | **Gravity chutes / flow lanes with escapements** | FIFO only: one blocked box per lane unless all boxes in a lane are interchangeable. That is true for **empty boxes** and for repeat stock (6 tins of tomatoes). Adopted as a part of C9, not as a store. |
| C8 | **Drawers the hand pulls** (each level a full 3 × 3 drawer pulled forward, picked from above) | A drawer needs its own length of free space in front: the kitchen. Nothing in the machine can reach it, and the gallery cannot pick outside the cabinet. Rejected (it is the STO-011 manual path, not a machine path). |
| C9 | **Box-in-box: nested empties magazine + spice cassettes** (more food per position instead of more positions) | The reference stock spends 26 of 96 positions on empty boxes. Nests of empties hanging in one tall level take ≈ 10 positions instead of 26 and need no new actuator in S4. Spice cassettes (several tubs in one box) would free more, but move the problem to the cell [U]. **Worked out on S4, §4.** |
| C10 | **Sliding puzzle with a vertical lift** (car in a front-centre shaft, 8 boxes per level around it, 15-puzzle moves) | The 8 cells around a front-centre shaft have no Hamiltonian cycle (checkerboard 5 : 3), so boxes cannot circulate; the car would need an XY reach arm inside the level. Rejected (S2 covers the useful form). |
| C11 | **Mobile racking** (compact shelving: rack rows move, one aisle opens where needed) | 3 rows + 1 aisle = 3 × 182 + 188 = 734 > 553 in y, and 3 × 186 + 188 = 746 > 610 in x. With 2 rows it is S4 plus a drive. Rejected in 650; valid in a ≥ 900 module. |
| C12 | **Moving gap in z** (levels are trays; lift all trays above level k to open a working gap there) | Lifts up to ≈ 200 kg for every pick, and a picker in the gap still needs an exit path. Rejected. |
| C13 | **Using the 2200 mm height** (storage above the gallery, or the gallery as the store's lift) | ≤ 2200 total is used by the gallery z 2000–2200. The "gallery as a full-height lift" idea (S4 §4.3) belongs to the system round. Rejected here. |
| C14 | **L-corner tower** (a 900 × 900 corner cabinet with a rotating 4-face rack) | Gains wall length (PHY-004), but the K9b gallery is a straight run, so the corner needs a second transport. System option for STO-014, not for the 650 column. |

**Selected for full work-out:** **C6 ring stacks** as **S5-A "ring rack"** (the only principle found here that
beats 9 boxes per level without digging: with an M and an S box per cradle it holds 12 per level, §3) and
**C9 box-in-box on S4** as **S5-B "nest lane"** (the cheapest way to raise free capacity, no new actuator, §4).
C1 is documented with its numbers in §2 because the research expected ≈ 100 boxes from it.

## 2. Why the paternoster (C1) fails in 600 mm depth [C]

Research (03, mechanism D) expected ≈ 100 boxes from a vertical carousel. The turn geometry says otherwise.
Carriers hang level from pivots on the chain (or are kept level by a second, offset chain; the result is the
same, because the carrier bodies translate along the chain path). Carrier = 3 boxes across x, depth
c = 176 (box 162 + tray lips), height h = 120 (envelope 110 + tray floor 10). The loop runs in y–z, so
2R + c ≤ 553 → R ≤ 188 mm.

Two neighbouring pivots in a turn are one chord k = 2R sin(p / 2R) apart, at a mean angle m from the
horizontal: Δy = k sin m, Δz = k cos m. The carriers collide when Δy < c **and** Δz < h. Because m sweeps
0…90° through every turn, a collision-free loop needs **k ≥ √(c² + h²) = 213 mm** → sin(p / 376) ≥ 0.567 →
**chain pitch p ≥ 226 mm** for a 120 mm tray, i.e. 47 % of every metre of chain is air.

| Item | y–z loop (carriers 3 across x) | x–z loop (carriers 1 lane wide, 3 deep in y) |
|---|---|---|
| Turn radius R | 188 | 212 (2R + 186 ≤ 610) |
| Minimum pitch | 226 | 232 |
| Loop length (pivot apexes z 210 / 1985) | 2 × 1399 + 2π·188 = 3979 | 2 × 1351 + 2π·212 = 4034 |
| Carriers × boxes | 17 × 3 = **51** | 17 × 3 = **52**, and the gallery must pick at 3 y positions |

Two-tier carriers (6 boxes, h = 240) need k ≥ 297 → p = 346 → 11 carriers = 66, and the lower tier is not
reachable from above. **Verdict: 1 motor, ≈ 51 positions, below CAP-020.** The research figure assumed
1.1 × 0.55 m trays in a wider module and no turn clearance. The fix for the turn, keeping the carriers
touching and moving them across at the top and bottom by a push, is C6 (§3).

## 3. S5-A — Ring rack ("paternoster without turns")

### 3.1 Principle and views

**Principle (3 sentences).** Each of the three lanes is a closed ring of 28 open stainless **cradles** stacked
directly on each other in two columns (front F, rear M), 15 levels high, with one gap at the bottom of F and one
at the top of M; every cradle holds **one GN 1/6-100 (M) and one GN 1/9-100 (S) box side by side**, hanging by
their rims, so a cradle is 270 mm deep and two columns fill the full 553 mm depth with no aisle. One **index
step** pushes the top cradle of F across onto M and the bottom cradle of M across into F, then lifts column F
and lowers column M by one level (cam-driven lifts and pawls), so all 28 cradles move one place round the ring;
running the camshaft backwards runs the ring backwards. The exit is the top of column F under the roof hatch,
where the gallery lifts the wanted box out of its cradle; the cradles never leave the ring.

The turn problem of the paternoster (§2) disappears because cradles change column only by a straight push
while they touch their neighbours, so the pitch is the cradle height (120 mm) and not 226 mm.

**Front view** (door removed, F column; x–z):

```
 z (mm)                                                                        x (mm)
 2200 +----------------------------------------------------------------------+
      |  K9b gallery (not S5)   picks through the hatch over each lane's F14  |
 2000 +====== roof 10 ==[ hatch A ]========[ hatch B ]========[ hatch C ]=====+
 1990 |  top pusher: Y belt + fork bar over all 3 lanes (zone 1950-1990)      |
 1950 +--+==================+--+==================+--+==================+--+-+
      |g | F14  [S][  M  ]  |g | F14  cradle      |g | F14  cradle      |g | |  level 14 = EXIT
 1830 |u |------------------|u |------------------|u |------------------|u | |
      |i | F13              |i |                  |i |                  |i | |
      |d |      ...         |d |      ...         |d |      ...         |d | |  15 levels x 120
      |e |  cradles stand   |e |                  |e |                  |e | |  (cradle = box 108
      |  |  on each other   |  |                  |  |                  |  | |   + 7 clear + 5)
  270 |  |------------------|  |------------------|  |------------------|  | |  F1, held by pawls
  150 |  | F0 = gap (platform low, waits for the cradle from M0)         |  | |  level 0
  145 |==|== platform F-A ===|==|== platform F-B ==|==|== platform F-C ==|==| |
   50 |   camshaft (x), lift rocker, pawl shafts, bottom pusher bar         | |
    0 +=====drip tray, sump front left===========================================+
      0 14 24              218 228             422 432             626 636 650
        wall guide  lane A 194     guide  lane B 194     guide  lane C 194   wall
           (cradle 182 + hems 2 x 6)  guides 10: pawls, platform guides
```

**Side view** (section through lane B; y–z):

```
 z     y=0 wall                                                         y=600 front
 2000 +=====roof=================[ hatch y 270-436 ]==========================+
 1990 |  top pusher fork moves in y 15...573 (pushes F14 -> M14, or shifts F14) |
 1950 |  M14 = GAP (top)          |      F14  [ S 108 ][    M 162     ]  <- exit|
 1830 |  M13 [ S ][    M    ]     |      F13  [ S ][    M    ]                 |
      |   ...                     |       ...                                 |d
      |   column M goes DOWN      |       column F goes UP                    |o
      |   one level per step      |       one level per step                  |o
      |                           |                                            |r
  270 |  M1  ---- M pawls         |      F1  ---- F pawls                     | 20
  150 |  M0  [ S ][    M    ] on  |      F0 = GAP, platform F                 |
      |      platform M  --bottom pusher-->  (M0 slides +y onto platform F)   |
   50 |=== camshaft, rocker (F up = M down) =====================================|
    0 +=====tray================================================================+
      0 12 15                    291 297                                 573 580 600
          M column cradles 276     gap 6       F column cradles 276
          (S box at the rear of every cradle, M box at the front)
```

**Top view** (level 7; x–y):

```
 y 600 +------------------------------------------------------------------+ door 580-600
   573 |  +----------------+  +----------------+  +----------------+      |
       |  | F-A  M box 162 |  | F-B  M box     |  | F-C  M box     |      |  F row: hand
       |  |----------------|  |----------------|  |----------------|      |  reaches the
       |  | S box 108      |  | S box          |  | S box          |      |  M boxes
   297 |  +----------------+  +----------------+  +----------------+      |
       |  6 mm gap between the columns (push path at levels 0 and 14 only) |
   291 |  +----------------+  +----------------+  +----------------+      |
       |  | M-A  M box     |  | M-B            |  | M-C            |      |  M row
       |  |----------------|  |----------------|  |----------------|      |
       |  | S box          |  |                |  |                |      |
    15 |  +----------------+  +----------------+  +----------------+      |
     0 +------------------------------------------------------------------+ wall
       0 14 24           218 228            422 432            626 636   650
```

The views use all-M/S cradles (pitch 120). A T-lane variant (lane C at pitch 170 for GN 1/6-150) is in §3.4.

### 3.2 Box standard

| Item | S5-A requirement |
|---|---|
| Sizes | **M = GN 1/6-100** (176 × 162, 1.5–1.6 L) and **S = GN 1/9-100** (176 × 108, ≈ 1.0 L [U]; 1/9-65 ≈ 0.5 L also fits). Both have the 176 side along x, so one cradle carries an S behind an M on one pair of runners (162 + 108 = 270). Optional T lane: GN 1/6-150 (§3.4). **GN 1/3 (L) and GN 1/6-150 outside the T lane are not supported**, as in S4. |
| Hanging | The box hangs by its two **x-end rims** (the 162 and 108 mm sides) on the cradle runners; rim overhang ≥ 9 mm [U, as S4]. The box never slides in the store: only cradles move. **No hook seat is needed** (S4 needs one on both ends). |
| Gallery grip | The gallery's passive hooks (S1 type) go under the x-end rims at mid-span. The runners have a 30 mm notch there, so the rim underside is free (the same "free underside at mid-span" rule as S1). One gripper serves M and S because both are 176 mm long in x. |
| Lid | Flat seal-cover lid ≤ 8 mm, on top of the rim (as S1/S4). Box + lid = 108 mm; the cradle pitch 120 leaves 7 mm above the lid and 5 mm under the body. |
| Protrusions | None outside the rim outline. The K9b bayonet stub is not stored (stub carrier at the cell, as S1, S2, S4). |
| Identity | One UHF or NFC inlay per box, read at the exit (F14) only; a DataMatrix on the lid for the cameras. Each cradle carries a fixed NFC tag too, so the ring position is checked at every step (STO-009, STO-010). |
| Mass | ≤ 5 kg per box (BOX-004); a loaded cradle ≤ 10.8 kg. Weighing (BOX-012) is done by the gallery or the lid station, as in S1. |
| Material, cold | PP or Tritan, −40…+95 °C, dishwasher-proof (BOX-009). |

So S5-A uses the **same bought boxes as S1** plus the GN 1/9 size, which research/03 already lists as the S
size of the 176 family.

### 3.3 Retrieval sequence

**One index step** (camshaft one turn; design point 1.3 s, conservative 1.8 s) [est]:

| Phase | t (s) | Motion |
|---|---|---|
| a | 0.00–0.55 | **Pushes.** Top fork pushes F14 → M14 (278 mm, harmonic, ≤ 4.5 m/s²); bottom bar pushes M0 → F0 at the same time. Cradle hems slide on the hems below (PE-UHMW skid strips). |
| b | 0.55–0.85 | Platform F rises 125 mm and lifts the new F0 with the whole F column; the F pawls retract while the column is lifted 5 mm off them and re-enter the web windows of the new F1. Platform M rises 125 mm empty to M1 and takes the M column off its pawls; the M pawls retract. |
| c | 0.85–1.30 | Platform F returns down empty. Platform M lowers 125 mm with the M column; the M pawls enter the windows of the cradle now at level 1, the platform drops 5 mm, and the old M1 stands alone at level 0, ready for the next push. |

All three lanes do this together (one camshaft). Reversing the camshaft runs the same phases backwards and turns
the rings the other way, so the store always takes the shorter direction.

**Worst case:** a box in the cradle at **M0** (opposite the exit on a 30-place ring), M box wanted.

| # | Move | Time s [C on est step] |
|---|---|---|
| 1 | Read the ring position (camshaft absolute encoder + cradle tag); choose direction (both are 15 steps) | 0.1 |
| 2 | 15 index steps (M0 → F0 → … → F14) | 15 × 1.3 = 19.5 |
| 3 | Top fork shifts the cradle 137 mm toward M14 so that the M box is under the hatch line; the reader confirms the box tag | 0.4 |
| 4 | "Out-box ready" to the gallery | 0.1 |
| | **Total** | **≈ 20 s** (conservative 1.8 s per step: **≈ 28 s**) |

Mean over all 56 places of a ring: 7.5 steps ≈ **10 s** (conservative 14 s). STO-003 (≤ 30 s, mean ≤ 15 s) is
met, but with far less margin than S4 (6 s) and only just at the conservative step time. An S box needs no shift
(the hatch line is over the S position), so it is 0.3 s faster.

**What normally happens.** Every put-away goes to the free place closest to the exit in ring order, and in idle
time the store turns the next meal's boxes to within 1–3 steps of F14 (UC-04 menu). Because the three rings turn
together, the store can bring one planned box per lane at the same time. A 4-person meal with 12 ambient boxes
then needs ≈ 30 steps (≈ 40 s) of store time in total, overlapped with cooking.

**Put-away** (≈ 2–4 s): the ring turns the nearest free place of the right size (M or S) to F14 (mean ≈ 1–2
steps), the fork shifts the cradle so that the place is under the hatch, the gallery lowers the box until the
rims sit on the runners, moves its hooks out of the notches and rises; the fork shifts back. No box ever slides.

**Hand-over.** Hatch per lane, 194 (x) × 166 (y) in the roof, spring flap opened by the gallery, brush seal
(STO-008). Handshake as S1/S4: the ring does not index while the gallery's gripper is below the roof.

### 3.4 Density [C]

| Quantity | S5-A baseline (all lanes M+S, pitch 120) | S5-A with T lane (lane C pitch 170) | S4 | S1 |
|---|---|---|---|---|
| Rings × cradles | 3 × 28 = 84 | 2 × 28 + 1 × 18 = 74 | – | – |
| Positions | **168** (84 M + 84 S) | **148** (56 M + 74 S + 18 T) | 96 (M) | 126 / 113 usable (M) |
| Positions per metre of wall | 258 /m | 228 /m | 148 /m | 194 / 174 /m |
| Box envelope (M 3.136 L, S 2.091 L, T 4.562 L) | 439 L = **56.3 %** | 412 L = 52.9 % | 38.6 % | 50.7 % / 45 % |
| In M-equivalents (envelope ÷ 3.136 L) | **140** | 131 | 96 | 113 usable |
| Box content (M 1.55, S 1.0, T 2.1 L) | 214 L = 27 % | 205 L = 26 % | 19 % | 22 % usable |
| STO-005 (≥ 55 % envelope) | **met** (the only design so far) | not met | not met | not met |
| Worst case / mean | 20 s / 10 s | 20 s / 10 s (lane C 13 s) | 6 s / 4 s | 72 s / 6 s planned |

**Where the 780 L go (baseline):**

| Share | Volume | What |
|---|---|---|
| 56.3 % | 439 L | box envelopes (84 cradles × M + S) |
| 4.0 % | 31 L | the two ring gaps per lane (F0, M14) |
| 13.8 % | 108 L | cradle overhead: webs and hems (194 vs 176 in x), end lips (276 vs 270 in y), pitch 120 vs 110 |
| 9.4 % | 73 L | x: 4 guide strips with pawls (10 mm) and walls (14 mm) |
| 6.4 % | 50 L | y: rear 15, column gap 6, front clearance 7, door 20 |
| 7.5 % | 59 L | z 0–150: tray, camshaft, platforms, bottom pusher |
| 2.5 % | 20 L | z 1950–2000: top fork zone and roof |

**Why it is denser than S1 and S4.** S4 pays 28.5 % for its aisle, S1 23 % for its robot zone and dig reserve.
S5-A pays 4 % for two ring gaps and 10 % for the bottom and top mechanism zones. The second gain is the
cradle: an M box and an S box together are exactly 270 mm, so two columns tile the 553 mm depth with 13 mm to
spare, where three rows of 162 leave 67 mm. The price is in the mix: **S and M places come 1 : 1**.

**Reference allocation (T-lane variant, CAP-020, CAP-023):**

| Size | Places | Holds | Free |
|---|---|---|---|
| S | 74 | 30 seasonings + 8 empty S | 36 (small food: nuts, cheese, herbs, leftovers) |
| M | 56 | 30 M food + 13 empty M | 13 |
| T | 18 | 10 T food (cans, jars) + 5 empty T | 3 |
| **Total** | **148** | **70 food + 26 empty = 96** | **52** (S4: 3, S1: 31) |

**Variations tried:**

| Variation | Result | Verdict |
|---|---|---|
| Boxes stacked directly as the ring (no cradles) | pitch 110 (+9 % levels), but the bottom box carries the column, mixed heights break the top alignment, box-on-box contact | rejected |
| One-box cradles (182 deep), third row as a fixed stack | 84 M in rings + an unreachable third row | rejected: worse than S4 |
| "Figure eight" per lane: F up, M down, R up, M shared | 3 × 182 deep, ≈ 129 M; with a 14-cradle M column F and R form two separate rings unless the steps alternate F, F, R, R; worst ≈ 21 steps ≈ 27 s | rejected: slower, cradle with M+S gives more |
| Rings across x (lane pairs) | 3 lanes = odd; exits off the gallery's pick line | rejected |
| One camshaft per lane | independent rings, 2 more motors, same worst case | rejected (#20) |
| 900 mm column | 4 lanes → 224 positions (all M+S) | scales linearly |

### 3.5 Actuators, seals, sensors, parts, cost, failures, manual access

**Actuators (2 motors for the whole store):**

| # | Actuator | Type [est] | Drives |
|---|---|---|---|
| 1 | **Index drive** | 400 W 48 V servo with spring-applied brake + 1 : 10 single-start worm gear (self-locking [U]) on a camshaft along x at z ≈ 90 | 5 cams: lift beam F (3 platforms), lift beam M (3 platforms), pawl set F, pawl set M (push rods up the 4 guide strips to 24 pawls), bottom pusher (lever, arms in the guide strips hooking pins on the cradle webs, stroke 278 mm). 4 gas springs carry the mean column weight; the cams take the difference. In the T-lane variant lane C's lift lever has a 1.4 : 1 ratio (175 mm stroke). |
| 2 | **Top fork** | NEMA 23 closed-loop stepper, GT2 belt, rail in the roof zone (z 1950–1990) | A bar over all three lanes with fingers on the top cradles' web pins: push F14 → M14 (278 mm) in phase a, shift the exit cradle by 0 or 137 mm for picking. Electronically geared to the camshaft encoder. Lane C finger stepped 100 mm lower in the T variant. |
| – | Roof flaps | passive spring flaps, opened by the gallery (as S4) | – |

No dynamic seal: the store is dry and closed (STO-008: brush seals at the 3 roof flaps, door gasket).

**Sensors:** absolute encoder on the camshaft (phase and step count); top-fork encoder; motor current on both
drives (jam); one inductive sensor per column that confirms "pawls engaged" before a platform leaves (6); UHF/NFC
reader at F14 for box tags and cradle tags; ToF over the hatch line (box present, lid seated, rim on runners);
leak sensor in the tray sump; door interlock.

**Parts and cost** (T-lane variant, small series, net) [est]:

| Item | Bought / custom | € |
|---|---|---|
| 74 cradles: 2 laser-cut and bent 1.4301 webs with hems and pawl windows, 2 runner angles with grip notches, end lips, PE-UHMW skid strips, NFC tag | custom (job shop) | 1,200 |
| 4 guide strips with 24 pawls (1.4404), push rods, bellcranks | custom | 300 |
| 6 platforms, 2 lift beams, levers, 4 gas springs | custom + bought | 250 |
| Camshaft with 5 cams, bearings, worm gear | custom + bought | 350 |
| Index servo 400 W + driver; top-fork stepper, belt, rail | bought | 400 |
| Reader, ToF, inductive sensors, I/O | bought | 250 |
| Frame, panels, door, roof with 3 flaps, drip tray | custom | 600 |
| Crank, cables, brush seals | bought | 50 |
| **Machine part** (motion, cams, pawls, platforms, sensors, controls) | | **≈ 1,550** |
| **Cradles and enclosure** | | **≈ 1,850** |
| **Total** | | **≈ 3,400** = €23 per position, €26 per M-equivalent (S4 ≈ €24, S1 ≈ €17) |

**Failure modes and recovery:**

| Failure | Detection | Recovery |
|---|---|---|
| Cradle jams in a push (proud rim, foreign object in the 6 mm gap) | motor current over the phase profile | stop, run the phase back, retry once; then alarm. **All three rings stop**, the store is blocked until it is cleared (single point of failure) |
| Pawl does not engage | "pawls engaged" sensor | the cam stops before the platform leaves; the worm holds the column |
| Box not seated after a put-away | ToF at the hatch line | gallery re-seats the box before any index step |
| Power loss mid-step | – | worm gear holds every position; the absolute encoder knows the phase, the step finishes on restart; full re-scan = one ring turn, 30 steps ≈ 40 s (STO-010) |
| Dropped box at the exit | ToF, tag missing | it falls back into its own cradle (the cradle is under it) |
| Broken cradle | tag read fails, current rises | the ring turns it to F0, where it stands alone on platform F behind the door; service slides it out forward and fits a spare |

**Manual access (STO-011).** Open the door: the M boxes of all 14 F-column cradles hang directly behind it and are
lifted over the 10 mm end lip and slid out forward; the S box of the same cradle comes next. The M column (rear)
is reached by turning the ring with a **hand crank** stored in the door on the worm shaft: 10 turns per step,
≤ 15 steps to bring any cradle to the front column (≈ 2 min worst). Met, but slowly; S4 reaches every box with
at most one box removed.

### 3.6 Cleaning

* **Boxes** never touch each other and never slide; only their rims touch the runners. Every box is washed in
  the K9b well whenever it is emptied (as S1/S4).
* **Spills.** A leaking lidded box drips through its open cradle onto the lid of the box below and down the
  column to the tray. Unlike S4, **the source moves**: as the ring turns, the drip reaches lids in both
  columns of that lane. Detection: leak sensor in the tray sump; the store then turns the ring past F14, where
  the ToF/camera and the weight trend at the hand-over find the wet box, and the gallery takes it out. The lids
  of that lane's boxes are wiped by washing them at their next use. **Option [est]:** a 0.5 mm drip pan in every
  cradle (pitch 125, 14 levels, −7 % positions) keeps a leak inside its own cradle.
* **Crumbs, a broken box:** fall through the open cradles to the tray (1 % slope to the sump, two rinse
  nozzles, drain, fan dry), as in S4. Shards stay on the runners of their own cradle or the lid below; the ring
  brings that cradle to F14 for inspection and the gallery removes the pieces it can grip; the rest is a
  service call (as S1/S4).
* **Cleaning the ring itself without a human:** a monthly night programme indexes every cradle through **F0**,
  where it stands alone on platform F with a 5 mm gap above. A spray bar on the bottom-pusher arms sweeps it
  in y with 40 °C detergent water and a rinse, the tray drains, and an extraction fan dries it before the next
  step (≈ 74 × 80 s ≈ 1.7 h) [U: humidity rise in the store, STO-007]. Boxes stay in their cradles with lids
  closed; their outsides are dishwasher-proof.
* Hygiene limit: 74 cradles with hems, windows and skids are more surface than S1's 9 open stacks or S4's
  runners, and every one of them moves.

### 3.7 Cold variant

Shell interior as S1/S4: ≈ 480 W × 380 D × 1500 H [U, research/03 §4.1].

| Item | Fridge (+4 °C) | Freezer (−18 °C) |
|---|---|---|
| Fit | M+S cradles need 552 mm depth: **do not fit** 380. Use **M-only cradles** (168 deep): 2 × 168 + 6 = 342 ≤ 380. 2 lanes × 194 + 3 strips = 418 ≤ 480. Height 1500 − 100 bottom zone − 40 top = 11 levels → ring of 22 places, 20 cradles | same |
| Positions [C on U] | **40 M** per shell (S1 ≈ 40–45, S4 24). CAP-021 ≥ 45 **not met with one shell**; met by M+S cradles if the shell is ≥ 560 deep inside (free-standing model: 2 × 20 × 2 = 80) | **40** ≥ CAP-022's 20: met |
| Exit | hatch in the cabinet's top wall above the F tops (as S1/S4): insulated 40 mm flap, heated frame ≈ 5 W (CLD-014); open ≈ 3–4 s per passage (CLD-004) | same |
| Motors | **none inside the cold.** Index servo on the cabinet top, a Ø 12 shaft down the 62 mm side space through one bushing in the exit plate to a bevel gear on the camshaft; top-fork stepper on top, fork driven through a second bushing | same; cams, pawls, levers in 1.4404 and PEEK with −40 °C H1 grease (CLD-009) |
| Frost | NoFrost shell; humid air enters only through the top hatch | **risk:** stacked cradle hems may freeze together. They move at every step and the lift breaks them free, but the push force may rise [U: §3.8 test]. No box-on-box freezing (boxes hang). |
| Raw meat (CLD-011) | In a ring every box is sometimes above others, so "R below RTE" cannot be kept by position. **One lane is R-only** (20 places ≥ 5 R boxes); the other lane is RTE. The 0–2 °C sub-zone (CLD-003) still needs its own compartment, as in S4 | – |
| Human access | OEM door kept as the service door: F-column boxes directly, the rest by crank | same, with gloves |

**CLD-007 risk** as S1/S4: the top wall is cut for the exit plate and two bushings [U: no refrigerant line there].

### 3.8 Score, biggest weakness, cheapest experiment

| Criterion | Weight | Score | Reason |
|---|---|---|---|
| Simplicity | 30 % | 3 | 2 motors and one camshaft for the whole store, no placement logic beyond "nearest free place", no box ever slides. Against: 74 cradles, 24 pawls, 6 platforms, pushes at two levels, a timed cam set; every retrieval moves every cradle |
| Hygiene | 25 % | 3 | no box-on-box contact, open cradles drain to a tray, rinse station at F0. Against: a leak travels with its box round the ring; much moving stainless surface |
| Coverage / fit | 20 % | 4.5 | **148–168 positions** (131–140 M-equivalent: +36–46 % on S4, +16–24 % on S1 usable), **STO-005 met** (baseline), 52 free places in the reference stock, STO-003 met (20 s, mean 10 s). Against: S : M fixed 1 : 1 per cradle (STO-006 partly), no GN 1/3, 40 per cold shell |
| Reliability | 15 % | 3 | cam indexers are proven for 10⁸ cycles; worm holds on power loss; 40 s re-scan. Against: ≈ 600 steps a day with 6 cradle slides and 24 pawl actions each; **one jam stops all three lanes** |
| Cost | 10 % | 2.5 | ≈ €3,400 total, machine part ≈ €1,550; €23 per position |
| **Weighted** | | **3.3 / 5** | (S4 3.6, S1 3.4) |

**Honest biggest weakness: the whole store moves for every box.** A retrieval is 7.5 index steps on average,
each step moves all 74 cradles, and the worst case (20 s, 28 s with conservative cams) is three times S4's and
close to the STO-003 limit. Lockstep makes it a single point of failure, and a leaking box carries its drip
round the ring. S5-A buys **density** (the first design to reach STO-005) with **motion**.

**Cheapest experiment (≈ €400, 2 weeks).** One lane, short ring: 2 columns × 5 levels, 8 laser-cut cradles
(≈ €130) with M and S boxes from two makers; two platforms on 3D-printer lead-screw axes; pawls of bent sheet
on a hand lever; top and bottom pushes by two belt axes (non-food zone, allowed by #4). Measure:

1. Push force and tolerance: cradle onto cradle across the 6 mm gap at height steps of 0, ±0.5, ±1, ±2 mm,
   with 1–11 kg cradles, 10,000 steps; target < 1 jam in 10⁴.
2. Pawl catch in the web windows over 10,000 cycles, with the column loaded to 150 kg.
3. Step time reachable without boxes sliding against the end lips (3–5 m/s²), against the 1.3 s design point.
4. Gallery-type hook pick from a cradle with notched runners, M and S.
5. One night in a chest freezer at −18 °C: push force and hem freeze-bonding after 24 h.

If (1) needs better than ±0.5 mm or (3) gives more than 1.8 s per step, S5-A falls behind S4 and stays a
cold-shell option.

## 4. S5-B — Nest lane: S4 with hanging nests of empty boxes

S5-B is S4 unchanged (racks, carriage, J-hook, hand-over, see `S4-aisle-shuttle.md`) except for one tall
**nest level**. Only what differs is described; where nothing is said, S4 applies.

### 4.1 Principle and views

**Principle (3 sentences).** A clean empty GN box without its lid nests into another one at a pitch of ≈ 22 mm
[U] instead of standing in its own 115 mm level, and **the lowest box of a nest hangs on the S4 runners like any
other box**, with the same rim and hook seat. The S4 carriage therefore pulls a whole nest (≤ 13 boxes,
≤ 2.6 kg) out of its slot with the normal J-hook move and brings it to a lower hand-over height, where the
gallery lifts the top box out of the nest or lowers a washed box into it. The lids of nested empties stay at
the lid station (S1 §4.3, K9b box shelf), so the store holds 26 empties in one level of three lanes instead of
26 slots, with no new actuator.

**Side view of the rear face, lanes A–C share the nest level** (y–z, as S4 §1.2):

```
 z (mm)       rear face (y 22-204)                 aisle (y 204-392)
 2000 +=====roof=====[ hatch y 214-382 ]========================================+
 1979 |                                    top rim of a full M nest at the        |
      |                                    NEST HAND-OVER: carriage runners at    |
 1715 |                                    R = 1715, gallery reaches 285 mm down  |
      |  7 M levels (pitch 115)            ...                                   |
      |  8 S levels (pitch 80)                                                   |
  467 +- - - - - - - - - - - - - - - - -                                          |
      |  NEST LEVEL (pitch 379)    lane A: 13 M empties  (rim pitch 22 [U])        |
      |    ][  ][  ][  ][ ...          lane B:  8 S empties                       |
      |    nested boxes rise           lane C:  5 T empties                       |
      |    264 mm above the rim                                                  |
  188 |==runner R_n = 188========  lowest box of each nest hangs here (hook seat)  |
   88 |  body bottom of the lowest box                                             |
   80 +--drip tray--------------------------------------------------------------- +
```

**Section through one nest** (x–z, lane A):

```
      | partition |                                   | partition |
  452 |           |   +=========================+     |           |  <- 13th (top) rim
      |           |    \   ...  11 more rims   /      |           |     22 mm apart [U]
  210 |           |   +=========================+     |           |  <- 2nd rim
  188 |===runner==|=+=============================+=|==|==runner==|  <- 1st rim on the runners
      |           |  \                           /    |           |     hook seat on its ends
      |           |   \_________________________/     |           |
   88 |           |      body of the lowest box       |           |
```

Front face and carriage are as S4. The carriage is open above the box between its two beams (S4 §1.4), so a
nest up to 264 mm above the rim passes; the only new carriage stop is the **nest hand-over**, set from the nest
height so that the top rim is ≤ 1980: R = 1715 for a full M nest, 1700 for a full S nest, and never below the
gallery's reach (R ≥ 1550).

### 4.2 Box standard

As S4 (GN 1/6 S/M/T with the S4 rim and hook seat, seal-cover lid, two NFC tags), plus:

| Item | Requirement |
|---|---|
| Nesting | lid-less empties of one size must nest at ≤ 25 mm pitch without sticking (no vacuum, no wedging; a drain rib or stand-off lugs on the wall help) [U: measure, §4.8] |
| Rim gap in the nest | ≥ 15 mm free between two nested rims at the x-end mid-span, for the gallery's hooks (hook tip ≤ 5 mm) [U] |
| Hook seat | the lowest box carries the nest on its own rim and hook seat: the S4 seat must take ≤ 2.6 kg (S4 rates it for 5 kg) |
| Tags | each nested box keeps its two tags; inside a nest the reader sees several tags, so the nest content is counted by the store's inventory, not by reading |
| Lids | stored at the **lid station** (interface request to the transport/cell designer, as S1 §4.3). Option inside the store: one lidded M box with up to 25 lids stacked on it in a 315 mm level, if the gallery can pick a lid [U] |

### 4.3 Retrieval and put-away

Food boxes: exactly S4 (worst case 6.1 s, mean ≈ 4 s, put-away ≤ 3.5 s).

**Empty box, worst case** (M nest, rear lane A, nest level R_n = 188; carriage parked at the top):

| # | Move | Time s [C, S4 axis data] |
|---|---|---|
| 1 | Z down 1.74 m to R_n − 5, X to lane A at the same time | 2.45 |
| 2 | Settle; ToF measures the nest height (count check), NFC reads the lowest box | 0.15 |
| 3 | Z +5: J-tip into the lowest box's seat | 0.20 |
| 4 | Y pull 167 mm (nest ≤ 2.6 kg, pull force < 15 N) | 0.62 |
| 5 | Z up to the **nest hand-over R = 1715**, X to lane B; the load cell weighs the nest (count = mass ÷ box mass) | 2.20 |
| 6 | Settle, "nest ready" to the gallery | 0.20 |
| | **Nest ready** | **≈ 5.8 s** |
| 7 | Gallery: hooks down 285–21 mm (depending on the count) into the top rim gap, lifts the top box ≈ 90 mm out of the nest | gallery time ≈ 3 s [est] |
| 8 | Carriage returns the nest (moves 1–5 reversed) | ≈ 5.5 |

For an ingestion batch the nest stays on the carriage while the gallery takes all the empties it needs (e.g. 6
for a shopping trip), so the store pays steps 1–6 and 8 once per batch (≈ 11 s). Food retrievals wait during
that time; ingestion does not overlap with cooking in the daily plan (TRN-008 not affected) [est].

**Put-away of a washed empty:** the same nest presentation; the gallery lowers the box into the nest until its
rim sits 22 mm above the previous one [U], releases and rises. Washed empties are collected in the cell's clean
store and put away in batches.

### 4.4 Density [C]

Level heights per face, budget Σ pitch ≤ 1860 (S4 §4.2). Nest level pitch = 100 (body below the runner) +
12 × 22 (nest above the rim) + 15 = **379**.

| Face | Levels from the bottom | Holds |
|---|---|---|
| Rear | nest level (379) + 8 × S (80) + 7 × M (115) = 1824 | 3 nests (M ≤ 13, S ≤ 15, T ≤ 9 empties [U pitch]) + 24 S + 21 M |
| Front | 2 × S + 7 × M + 5 × T (165) = 1790 | 6 S + 21 M + 15 T |

| Quantity | S5-B | S4 (same S/M/T mix) |
|---|---|---|
| Lidded positions | 87 (30 S, 42 M, 15 T) | 99 (39 S, 45 M, 15 T) |
| Empties held | up to 37 in 3 nests | in lidded positions |
| **Boxes held in total** | **124** (+25 %) | 99 |
| Reference stock: 70 food + 26 empties | food 70 of 87 (**17 free**), empties 26 of 37 | 96 of 99 (**3 free**) |
| Box envelope, lidded positions + nest slots | 264 + 32 = 297 L = 38 % | 293 L = 37.6 % |
| Positions per metre of wall (boxes held) | 191 /m | 152 /m |
| CAP-023 (≥ 25 empties, ≥ 15 % of positions) | met (37 ≥ 25 and ≥ 19) | met |

The enclosure is not used more densely (STO-005 is still missed); the gain is that **26 empty boxes take
one level instead of 26 slots**. Spice cassettes would add more but are not counted (they need the cell to
dose from a tub inside a box, [U]).

### 4.5 Actuators, sensors, parts, cost, failures, manual access

**No new actuator, sensor or part.** The rear partitions get a different runner set (one runner pair at
R_n = 188 with 379 mm free above it). The software adds the nest hand-over stop, a nest model (count, height)
and batch handling. The carriage's load cell and ToF give the nest count twice. **Cost as S4: machine part ≈
€1,450, rack and enclosure ≈ €850**; 26 lids fewer in the store, but not fewer lids in the system.

| Failure | Detection | Recovery |
|---|---|---|
| Nested boxes stick (wet, static, wedged) | gallery hoist current, two boxes lifted (ToF height, weight) | gallery shakes and retries; else the gallery takes the pair to the cell, where the hand separates them; repeated sticking means a different box make |
| Gallery hook misses the rim gap | ToF height check before the hooks go down | re-measure, retry |
| Nest count wrong after manual intervention | load cell (mass ÷ box mass) | corrected at the next presentation (STO-010) |
| Power loss, jams | as S4 | as S4 |

**Manual access (STO-011):** as S4's rear face; a nest is lifted out as one piece (≤ 2.6 kg).

### 4.6 Cleaning

As S4 (hanging boxes, open lanes, tray and sump). Nested empties are clean and dry; the inner boxes are covered
by the box above, and only the top box of each nest is open to the closed, dark store air (STO-008). Nested
boxes touch each other inside and outside, which is acceptable only because all of them come from the same wash
(this is how clean GN pans are kept in every kitchen); a box that has been in the cell is never nested before
it is washed. Option: the top box of each nest keeps a dust lid, moved by the gallery to the new top box [U].

### 4.7 Cold variant

No change from S4: empties are filled at ambient ingestion and enter the cold store already full, so the cold
store keeps no empties and nests bring no gain there. S4's cold capacity (24 per 178 cm shell) remains its weak
point.

### 4.8 Score, biggest weakness, cheapest experiment

| Criterion | Weight | Score | Reason (difference from S4) |
|---|---|---|---|
| Simplicity | 30 % | 4 | no new part; one more hand-over stop and a nest model in software |
| Hygiene | 25 % | 4 | as S4; nested boxes touch, but only freshly washed ones |
| Coverage / fit | 20 % | 3 | 124 boxes held instead of 99, 17 free food positions instead of 3. Still 38 % envelope (STO-005 missed), no GN 1/3, cold 24 per shell |
| Reliability | 15 % | 3.5 | nest separation and the hooks in a ≈ 15–19 mm rim gap are new risks [U] |
| Cost | 10 % | 3 | as S4 |
| **Weighted** | | **3.6 / 5** | (S4 3.6) |

**Honest biggest weakness:** the gain is modest (+25 % boxes held, +14 free food positions) and rests on two
things outside the mechanism: how real GN boxes nest (pitch, sticking, rim gap) and a lid station that keeps
the lids of nested empties. The cold store does not gain at all.

**Cheapest experiment (≈ €80, 1 day):** 15 GN 1/6-100 PP boxes from two makers, 8 GN 1/6-65 and 5 GN 1/6-150.
Measure the nesting pitch, the free rim gap at the x-end mid-span, the separation force of the top box (dry,
straight from a dishwasher, after a week nested), and hang a 13-box nest on two flat bars and pull it by one
rim with a hook (the S4 hook rig, if built). Pass: pitch ≤ 25 mm, gap ≥ 15 mm, separation < 5 N.

## 5. Comparison and recommendation

Same column, same accounting (650 × 600 × 2000 = 780 L; M-equivalent = box envelope ÷ 3.136 L).

| Design | Positions | M-equivalent | Envelope | Worst / mean retrieval | Motors | Cold, per 178 cm shell | Score (own doc) |
|---|---|---|---|---|---|---|---|
| S1 grab from top | 126 (113 usable) | 113 usable | 51 % (45 % usable) | 72 s / ≈ 6 s planned | 3 | ≈ 40, hoist inside | 3.4 |
| S2 pushers, shaft | 89 | – | 31 % | 11.5 s / 7 s | 3 | 33–38 | 3.6 |
| S3 belts, lift aisle | ≈ 92 | – | – | 18 s | 2 | – | 3.0 |
| S4 aisle shuttle | 96 | 96 | 38.6 % | 6 s / 4 s | 3 | 24, 2 motors inside (freezer) | 3.6 |
| **S5-A ring rack** | **168** (M+S) / 148 with T lane | **140** / 131 | **56 %** / 53 % | 20 s / 10 s (28 / 14 s conservative) | **2** | **40 M, no motor inside** | 3.3 |
| **S5-B nest lane (S4 + nests)** | 87 lidded + 37 nested = 124 boxes | 96 | 38 % | 6 s / 4 s (empty: 5.8 s per nest) | 3 | 24 (as S4) | 3.6 |

**Findings.**

1. **The paternoster is not a dense store in 600 mm depth.** Its turns need a chain pitch ≥ √(depth² + height²);
   with GN 1/6 trays that is 226 mm for a 120 mm tray, and the column holds ≈ 51 boxes (§2).
2. **Replacing the turns by sideways pushes gives the densest store found in this round** (S5-A): 12 boxes per
   level (6 M + 6 S in 270 mm cradles), no aisle, no robot zone, no digging, 2 motors, and the first design to
   meet STO-005 (56 %). Its price is motion: every retrieval moves the whole store (mean 7.5 steps), the worst
   case is 20 s, and one jam stops all three lanes. It scores below S4 for the 650 ambient column.
3. **The cheapest capacity is not a better mechanism but fewer positions per empty box** (S5-B): nests of
   empties in one tall S4 level hold 26 empties in ≈ 10 slots and leave 17 free food positions instead of 3,
   with no new part. It ties S4 on score and carries two outside risks (nesting behaviour, lid station).
4. **S5-A's real value is in the cold.** A 380 mm-deep fridge shell is too shallow for an aisle (S4: 24 per
   shell) but takes two M-cradle columns: 40 positions per shell, freezer met with margin, and all motors
   outside the cold (S1 keeps its hoist inside). CAP-021 (45) is still missed by one shell unless the shell is
   ≥ 560 mm deep inside, where M+S cradles give 80.

**Recommendation.**

* **Ambient 650 column: S4 with the S5-B nest level.** Same machine, same score, 14 more free positions; adopt
  the nest level as soon as the €80 nesting test passes and the lid station confirms it keeps the lids.
* **Cold shells: carry S5-A (M-only rings) into the cold-storage comparison** against S1 (top hatch, ≈ 40) and
  S4 (24). Its two advantages there are decisive: no aisle in a 380 mm interior and no motor in the cold.
* **If capacity becomes the gate** (CAP-026 larger storage, or ambient narrower than 650), S5-A is the only
  design here that holds ≥ 130 M-equivalents in 650 mm; then run its €400 ring experiment first, because the
  step time decides whether it meets STO-003.

**Open items.** [U] GN nesting pitch and rim gap; [U] GN 1/9-100 volume and rim; [U] interior of the chosen
fridge shell (380 vs ≥ 560 mm); interface requests: the gallery must pick at a fixed y line with S1-type hooks
under the x-end rims (S5-A) and at a lower nest hand-over (S5-B, ≤ 285 mm below the roof); the lid station must
store the lids of nested empties.
