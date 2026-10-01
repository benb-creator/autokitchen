# Storage 10 — comparison and selection (ambient, fridge, freezer, box standard, layout)

Status: system-engineering decision of the storage round. Inputs: `00-storage-brief.md`, DECISIONS #11, #17–#21,
#28 (and #20 simplicity, #22 cost later), the six designs S1–S5 and C1, K9b §2 (hand-over interface, bayonet stub),
K9c §4.2 (width), requirements STO/CLD/CAP. Tags: **[C]** calculated here, **[E]** estimate, **[U]** unverified, must
be measured; **[D]** taken from the design document named.

## 0. Decisions in brief

* **Ambient (650 mm column): S4 aisle shuttle**, with the S5-B nest level for empty boxes. Lidded GN boxes hang by
  their rims in two rack faces; one XZ carriage with a passive J-hook; 3 motors; worst retrieval 6 s, mean 4 s;
  72 lidded ambient places + 9 cool + ≤ 37 nested empties; ≈ €1,470 machine part + €850 rack. It scores highest
  (3.74 against S2 3.60, S1 3.31) and is the only simple design that meets every Must. **We lose against S1**
  ≈ 14 usable positions and the free height mix; **we gain** 6 s instead of 72 s, no digging, hanging boxes that never
  touch each other, and every box within one box of a human hand.
* **The customer's framing:** grab-from-top wastes 23 %, not 50 %, and in a 2.2 m machine it is **not** the
  human-accessible design (S4 is). Pushers and belts lose on geometry: at 650 × 600 one level holds 3 × 3 boxes, and
  the empty column leaves 6, as an aisle does; sliding density needs ≥ 1,050 mm width or ≥ 900 mm depth.
* **Cold: C1 concept B** (one window in the top wall, a spring-closed lift-and-slide hatch on a magnetic gasket,
  OEM door kept) **with S1 stacks inside**, in a 178 cm built-in larder fridge (≈ 38–45 usable [U]) and a 178 cm
  NoFrost freezer (≈ 24 usable). One cold robot design, built twice. Exit open 3.4 s; +7 / +38 kWh a year.
  No mechanism meets CAP-021 and CLD-006 together in one fridge shell; the default relies on menu planning (Q2).
* **Box standard:** bought GN 1/6 (and 1/9 for spices) in PP copolymer or Tritan, **no stub**, flat seal-cover lid,
  free rim underside at mid-span of the two long sides, J-hook seat on the ends, two NFC tags. One passive hook
  gripper on the gallery and both cold robots. The cell gets each box in a **permanent stub carrier** on the box
  shelf (spring hooks opened by the shelf, 0 actuators). K9b changes K-1…K-9 (§5.4).
* **Layout:** freezer 600 | fridge 600 | ambient 650 | cell 1,750 = **3,600 mm**; one gallery X axis, one pick line
  (y ≈ 290). The L-corner helps only in an L kitchen, and then for storage.
* **First experiments:** measure the appliances (E1) and GN box samples (E2), then the stub carrier (E3).

## 1. Comparison table

### 1.1 Accounting used here (normalisation)

The designers counted slightly differently. This document uses one basis for all of them:

* **Enclosure** = the ambient column 650 × 600 × 2000 mm = **780 L**. The gallery (z 2000–2200) belongs to the
  transport and is not counted (S1, S4, S5 did this; S2 used 741 L without plinth, S3 780 L).
* **Box envelope** = rim footprint × (box depth + 10 mm lid). GN 1/6-100 (M) = 176 × 162 × 110 = **3.136 L**;
  GN 1/6-65 = 2.14 L; GN 1/6-150 (T) = 4.56 L; GN 1/9-65 = 1.43 L; GN 1/9-100 = 2.09 L; GN 1/3-150 = 9.15 L.
  **M-equivalent** = envelope ÷ 3.136 L. Box volume % = envelope ÷ 780 L.
* **Positions** = box places the hardware offers. **Usable** = positions minus places that must stay free for the
  mechanism to work (S1 dig reserve, S3 free row slot and real row fill), i.e. what the inventory can fill.
* **Reference stock** (2-person household, CAP-020 + CAP-023, as S1/S4/S5 used it): **70 food boxes + 26 empties =
  96 boxes** in the ambient column. The cool zone (CAP-024, ≥ 8) is placed in §4.4.
* **Retrieval** = from the command until the box waits at the gallery hand-over, at each designer's design-point
  axis data; brackets = conservative axis data where the designer gave it. "Random" = mean over all positions with no
  prediction; "planned" = mean with menu-based pre-positioning.
* **Cost** = machine part (motion, sensors, controls, mechanism) **+ structure** (rack/posts/shelves/enclosure, the
  "shelving" line of #28). Boxes are excluded (≈ €10–14 each, the same for all, except S2's custom mould). All net;
  S2's figures were incl. VAT and are converted (÷ 1.19).
* **Cold** = positions per 178 cm built-in shell on C1's interior estimates (larder fridge ≈ 470 W × 410 D × 1620 H,
  NoFrost freezer ≈ 430 × 370 × 1450 [U]), with the exit through the top wall (C1 concept B).

### 1.2 The table

| Design | Positions in the 650 column | Usable positions (M-eq) | Box volume % | Worst retrieval s | Mean retrieval s (random / planned) | Actuators (motors + passive moving parts) | Seals | Machine part + structure € | Cold suitability (per 178 cm shell) | Human access (power off, door open) | Biggest weakness |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **S1** grab from top | 126 (9 stacks × 14 M) | **113** (113) | 50.7 (usable 45.4) | **72** (106) | ≈ 36 / ≈ 6 | 3 motors; passive toggle gripper | 0 dynamic; freezer: 2 shaft bushings, hoist motor inside | 1,370 + 600 | **good**: port stack under a top hatch; fridge ≈ 45–50 raw, ≈ 38–45 usable [U]; freezer ≈ 32 raw / ≈ 24 usable | front stack tops direct; a deep rear box needs up to ≈ 40 boxes unstacked (3–4 min) | digging: STO-003 (≤ 30 s) missed for 72 of 126 positions; works by prediction |
| **S2** pushers, one car in a shaft | 89 (32 S, 53 M, 4 L) | 89 (81) | 32.6 | 11.5 | 7 / – (frequent boxes already placed high) | 3 motors; none (pin engaged by the car's Z drop) | 0; cold: 1 bushing in the door, X/Y motors inside | ≈ 1,030 + 660 (+ box mould €30–50 k) | medium: car on a replacement door (C1 D2), 1 lane: fridge 38–42, freezer ≈ 30 | **best**: every lane front open, ≤ 3 boxes slide forward | at 650 mm the shaft takes one column in three: 89 < 96 reference boxes; custom-moulded rib box |
| **S3** belts, docked levels | 110 (50 S-65, 48 at 100, 12 at 150) | ≈ 92 real mix (89) | 35.6 | 18.4 (15.6) | ≈ 12 / 8 | 2 motors; 13 belt levels (26 rollers, 13 hub detents), shutter bell crank | 0; cold: belts through slots, hex-shaft bushing, motors outside | ≈ 1,800 + 460 | poor: 1 row per level; fridge 27–33; **freezer does not fit** (370 < 386 mm) | front rows direct; back rows by turning the level hub | 13 hidden belt loops (hygiene, half the cost); not denser than an aisle |
| **S4** aisle shuttle, hanging boxes | 96 all-M; 99 with S/M/T | **96–99** (96) | 38.6 | **6.1** (9.3) | **4** / 2–3 | 3 motors; passive J-hook | 0; cold: 1 bushing, X/Y motors inside | 1,470 + 850 | poor in the fridge: one face, 24 (CAP-021 fails); freezer 24 if depth ≥ 375 [U] | **very good**: front face direct (48), rear face through one emptied front slot (≈ 15 s) | density: 3 spare places with the reference stock; no GN 1/3; hook seat on the rim [U] |
| **S5-A** ring rack | 168 (84 M + 84 S); 148 with a T lane | 168 (140) | **56.3** | 20 (28) | 10 (14) / 2–5 | 2 motors; ≈ 110 passive parts (74 cradles, 24 pawls, 6 platforms, 5 cams) | 0; cold: 2 bushings, no motor inside | 1,550 + 1,850 | medium: M-only rings ≈ 40 fridge, ≈ 32–36 freezer [E here]; no motor inside | front column direct, the rest by hand crank ≤ 2 min | the whole store moves for every box; one jam stops all three lanes |
| **S5-B** S4 + nest level | 87 lidded + 3 nests (≤ 37 empties) = 124 boxes | 87 + 37 nested (96) | 38 | 6.1 (empty: 5.8 per nest) | 4 / 2–3 | as S4 | as S4 | as S4 | as S4 (no gain in the cold) | as S4 | rests on GN nesting (pitch, sticking) and on the lid station keeping lids [U] |
| **C1** cold access (concept B) | – (cold only) | – | – | exit part ≈ 3.4 s | – | +1 small gear motor per shell (hatch) | 0 dynamic; magnetic compression gasket; freezer seat heated 3 W | ≈ 300 fridge, ≈ 335 freezer per shell | the access for all of the above: one window in the top wall, OEM door kept; +7 kWh/a fridge, +38 kWh/a freezer | OEM door opens normally | what lies in the top wall and how deep the interior really is are unpublished [U] |

### 1.3 Corrections made while normalising

* **S1 random mean** is not in S1: from its depth table (3.7 s at k = 0 … 70.6 s at k = 13), the mean over a full
  stack is ≈ 36 s [C]. S1's 6 s holds only with move-to-front plus overnight pre-digging.
* **S2**: 31 % was on 741 L and without lids; on the common basis 254 L = 32.6 %, 81 M-eq. Costs were incl. VAT.
* **S3**: 110 nominal, ≈ 106 after the free row slot, ≈ 92 with the designer's 85 % real row fill; envelope 278 L
  already included lids.
* **S4**: its §4.3 says a 4th lane needs 800 mm; its own x budget (15 + 38 + 4 × 180.5 + 1.5 + 39 + 15) gives
  **≈ 830 mm**. At 740 mm (K9c's spare 90 mm) S4 gains nothing.
* **C1's fridge capacity** (52–58 usable with S1) assumes a third, narrow GN 1/9 stack per row with almost no gaps.
  That stack turns the box 90° against the others, so one gripper (and the gallery's hook spacing) cannot serve it.
  With one footprint (GN 1/6, all heights) a 470 mm interior takes 2 × 2 stacks: **≈ 45–50 raw, ≈ 38–45 usable**
  with a dig reserve and a stack cap for CLD-006 [C on U interior]. This makes the interior measurement the first
  gate (§8).
* **S5-A cold** figures are mine: larder fridge 2 lanes × 11 levels above the compressor step → 20 cradles × 2 =
  40 M; freezer ≈ 9–10 levels → 32–36 [E].

## 2. Scores against the brief's criteria, and sensitivity

### 2.1 How "coverage / fit" is scored

Coverage was the criterion the designers read most differently, so it is split into five equal sub-scores (1–5):
(a) holds the reference stock of 96 boxes in 650 mm, with margin; (b) STO-003, ≤ 30 s for every box (M);
(c) STO-011, any box by hand, power off (M); (d) size flexibility: STO-006 mix without hardware change, L and XL
boxes; (e) the same mechanism works in a 178 cm cold shell.

| Design | (a) stock | (b) time | (c) hand | (d) sizes | (e) cold | Coverage |
|---|---|---|---|---|---|---|
| S1 | 4.5 (113, 17 spare) | 1 (72 s) | 2 | 4 (any height on any stack, no L) | 5 | **3.3** |
| S2 | 1.5 (89 < 96) | 5 | 5 | 4 (L, mixed lengths) | 2.5 | **3.6** |
| S3 | 3 (≈ 92 real) | 4 | 3.5 | 4.5 | 1.5 | **3.3** |
| S4 | 2.5 (99, 3 spare) | 5 | 5 | 2 (fixed partition set, no L) | 1.5 | **3.2** |
| S5-A | 5 (148–168) | 3 (20–28 s) | 2.5 | 2 (S : M = 1 : 1, no L) | 3 | **3.1** |
| S5-B | 3.5 (124 held, 17 spare) | 5 | 5 | 2 | 1.5 | **3.4** |

### 2.2 Weighted scores (1–5)

| Design | Simplicity 30 % | Hygiene 25 % | Coverage 20 % | Reliability 15 % | Cost 10 % | **Weighted** | Designer's own |
|---|---|---|---|---|---|---|---|
| **S4** aisle shuttle | 4 | 4 | 3.2 | 4 | 3 | **3.74** | 3.6 |
| **S5-B** S4 + nest level | 4 | 4 | 3.4 | 3.5 | 3 | **3.71** | 3.6 |
| S2 pushers | 3.5 | 3.5 | 3.6 | 4 | 3.5 | 3.60 | 3.6 |
| S1 grab from top | 3.5 | 3 | 3.3 | 3 | 4 | 3.31 | 3.4 |
| S3 belts | 3 | 2 | 3.3 | 3 | 2.5 | 2.76 | 3.0 |
| S5-A ring rack | 2.5 | 3 | 3.1 | 2.5 | 2 | 2.70 | 3.3 |

Reasons for the scores that differ from the designers':

* **S1 simplicity 3.5 (not 4), reliability 3 (not 3.5):** three motors and posts are simple, but the digging logic,
  the move journal, the re-scan after a human touched the grid, and a novel passive toggle gripper doing 100–200
  grip cycles a day are not. **Cost 4:** the cheapest per usable position (≈ €17).
* **S5-A simplicity and reliability 2.5 (not 3):** two motors drive ≈ 110 moving parts in lockstep; one jam stops
  every lane, ≈ 600 index steps a day.
* **S2 cost 3.5:** on net prices it is the cheapest hardware (≈ €1,690), but every box needs a moulded rib
  (≈ €30–50 k tooling, or a welded-on rib per box in small series).
* **S3 hygiene 2:** 13 closed belt loops that are only cleaned by taking the belts out.

### 2.3 Must-requirement gate (ambient column)

| Requirement | S1 | S2 | S3 | S4 | S5-A | S5-B |
|---|---|---|---|---|---|---|
| CAP-020 + CAP-023, 96 boxes (M) | ✓ 113 | **✗ 89** | ≈ 92 (borderline) | ✓ 99 (3 spare) | ✓ 148 | ✓ 124 boxes held |
| STO-003 ≤ 30 s for any box (M) | **✗ 72 s** (54 of 126 within) | ✓ 11.5 | ✓ 18 | ✓ 6 | ✓ 20 (28 conservative) | ✓ 6 |
| STO-011 any box by hand, power off (M) | ✓ but 3–4 min, up to 40 boxes moved | ✓ | ✓ | ✓ ≤ 1 box moved | ✓ ≤ 2 min crank | ✓ |
| STO-005 ≥ 55 % box volume (S) | ✗ 51 | ✗ 33 | ✗ 36 | ✗ 39 | **✓ 56** | ✗ 38 |

Only S4, S5-B and S5-A pass every Must. S1 fails STO-003 by design: a software stack cap fixes the time only by
cutting capacity below CAP-020 (S1 §3.2: cap 6 → 54 positions).

### 2.4 Sensitivity

| Case | S4 | S5-B | S2 | S1 | S5-A | Leader |
|---|---|---|---|---|---|---|
| Brief weights (base) | **3.74** | 3.71 | 3.60 | 3.31 | 2.70 | S4 |
| Equal weights, 20 % each | **3.64** | 3.58 | 3.62 | 3.36 | 2.62 | S4 (S2 close) |
| Coverage 40 %, others scaled down | 3.61 | **3.63** | 3.60 | 3.31 | 2.80 | S5-B |
| Cost 30 %, others scaled down | **3.58** | 3.55 | 3.57 | 3.46 | 2.54 | S4 |
| Coverage = capacity (a) only, 20 % | 3.60 | **3.73** | 3.18 | 3.55 | 3.08 | S5-B |
| Coverage = capacity (a) only, 40 % | 3.33 | 3.67 | 2.76 | **3.79** | 3.56 | **S1** |
| Designers' own scores, brief weights | 3.6 | 3.6 | 3.6 | 3.4 | 3.3 | tie S4 / S5-B / S2 |
| S4's rim seat fails: punched slot (S4 simplicity 3.5, cost 2.5) | 3.54 | 3.50 | **3.60** | 3.31 | 2.70 | S2 by 0.06 |

**Break-even.** S1 overtakes S4 only if coverage is read as capacity alone **and** weighted above ≈ 22 % (above
≈ 32 % against S5-B). Then S1 still fails STO-003 (M), so it would win the matrix and lose the gate. S2 comes within
0.06 only if S4's hook seat must be punched, and S2 still fails the reference stock (89 < 96). **The S4 family leads
in every case that keeps the brief's ranking of simplicity and hygiene first.** When S4 and S2 are close, #20
decides for S4: bought boxes, no moulded rib, no shelves under the boxes.

## 3. Ambient selection: S4 aisle shuttle with the S5-B nest level

### 3.1 Decision

**Ambient storage = S4** (two single-deep rack faces of 3 lanes, lidded GN 1/6 boxes hanging by their rims on welded
stainless runners, one XZ carriage in a 188 mm aisle, passive J-hook engaged by a 5 mm Z lift, the carriage itself is
the exit under the roof hatch), **built with the S5-B nest level as its default rack set** (empty boxes nested
without lids in one tall level). If the €80 nesting test fails (§8), the same machine gets the plain S4 rack set.

| Item | Value |
|---|---|
| Positions | 99 lidded (S/M/T mix) plain; with nest level and cool section see 3.5 |
| Retrieval | worst 6.1 s (9.3 s conservative), mean ≈ 4 s, ≈ 2–3 s pre-fetched; put-away ≤ 3.5 s |
| Actuators | 3 motors: Z 200 W servo with brake (the same part as the cold robots' hoist), X and Y NEMA 17 closed loop; hook passive |
| Seals | 0 dynamic; door gasket, hatch brush, drain trap |
| Cost | machine part ≈ €1,470 (lean ≈ €1,200) + rack and enclosure ≈ €850 |
| Human access | front face direct; rear face through one emptied front slot; re-scan after a door opening ≈ 1 min |
| Cleaning | slot-by-slot spray from the carriage, open lanes to the drip tray and sump; no box ever touches another |

### 3.2 Why S4

* It is the **only family that passes every Must** in the ambient column with few moving parts: one transfer per
  retrieval, no other box ever moves, no prediction needed (pre-fetch is a bonus, 6 → 2 s, not a precondition).
* **Hygiene**: nothing lies under a box, box bottoms never touch anything, a drip stays in its lane, any slot is
  emptied with one move and washed.
* **Commonality** with the cold robots (§4): same 200 W servo, closed-loop steppers, NFC reader, load cell,
  controller, passive-hook philosophy, same box.
* It scores highest under the brief's weights and stays first or within 0.06 in every sensitivity case except
  "capacity alone at ≥ 22 %" (§2.4).

### 3.3 What we lose against the runner-up

* **Against S1 (the density alternative):** 14 usable positions (99 vs 113; 27 nominal), i.e. 3 spare instead of 17
  with the reference stock; the free height mix (S1 takes any height on any stack; S4's mix is set by the partition
  set); ≈ €350 of hardware (≈ €2,320 vs ≈ €1,970). **We gain** 6 s instead of 72 s worst case, no digging and no
  dependence on the menu, no box-on-box contact, every box within one box of a human hand, a 1 min re-scan instead
  of up to 25 min, ≈ 60 transfers a day instead of 100–200 grip cycles.
* **Against S2 (score runner-up):** S2's 4 GN 1/3 positions and its continuous lanes that pack mixed box lengths.
  **We gain** bought GN boxes (no moulded rib, no €30–50 k tool), 10 more positions, half the worst-case time, no
  shelves under the boxes.
* **Common gap of S1, S4 and the cold throat:** no GN 1/3 in storage. Long pasta (≥ 25 cm) fits no GN 1/6 box, even
  diagonally (239 mm). Open question Q3.

### 3.4 The customer's framing, answered honestly

**Grab from the top (S1).** The customer expected ≈ 50 % waste but human access. In this column both turn around:

* The space the top grab costs is **23 %** (a 350 mm robot zone = 17.5 % plus a 5 % dig reserve), not 50 %. The
  50 % holds only for shallow stacks (3 tiers of 2 boxes, S1 §4.3). S1 is in fact the **densest** of the classic
  mechanisms (126 positions). The largest loss in every design (≈ 27 %) is that 176 × 162 boxes tile 610 × 553 only
  3 × 3.
* **Human access does not survive in a 2.2 m machine:** the top of the grid is under the gallery at 1.65–2.0 m, so
  a person reaches it from the front, and a buried rear box means unstacking up to 40 boxes. The human-accessible
  design is S4: every box is at most one box away from the door.
* What really costs S1 is **digging**: 14 moves and 72 s for a bottom box; it meets STO-003 only by predicting the
  menu. That is why it lost, not the waste.

**Dense with pushers (S2) or belts (S3).** The idea is right for wide, deep blocks; at 650 × 600 it has nothing to
work with:

* One level holds a 3 × 3 grid of boxes. The empty centre column takes one of the three columns, leaving **6 boxes
  per level — exactly what an aisle shuttle keeps**. Every stored box already touches the empty column, so there is
  never a box to slide aside: the sliding puzzle collapses into "one car in a shaft" (S2) or "a lift aisle in front
  of two rows" (S3).
* Real sliding density starts at **≥ 5 columns (≥ 1,050 mm wide: +23 %, but 25 s shuffles, S2 §4.3)** or with lanes
  **≥ 4 rows deep (≈ 900 mm deep, S3 §4)**. K9b's 650 mm allotment and #11's 600 mm depth exclude both.
* The pusher and belt designs did not lose on mechanism quality. S2's car that engages a base rib by its own Z drop
  and S3's passive slot coupling (one motor drives any level it docks at) are good ideas. They lost on geometry and
  remain the candidates for a ≥ 1,050 mm extension module (CAP-026).

**The densest idea found (S5-A, ring rack, 56 %)** is the only one that meets STO-005. It moves the whole store for
every box, so it is kept as the answer if capacity per metre ever becomes the gate.

### 3.5 Default rack set of the ambient column

Level budget per face Σ pitch ≤ 1,860 mm (S4 §4.2); S = GN 1/6-65 (pitch 80), M = 1/6-100 (115), T = 1/6-150 (165);
nest level 379 (S5-B §4.4); cool section = §4.4.

| Face (bottom → top) | Levels | Lidded positions |
|---|---|---|
| Rear | cool section 3 × T + insulation and shutter drum (645) · nest level (379) · 3 × S (240) · 5 × M (575) = 1,839 | 9 S, 15 M, + 9 cool T, + 3 nests (≤ 37 empties) |
| Front | 5 × T (825) · 4 × M (460) · 7 × S (560) = 1,845 | 21 S, 12 M, 15 T |
| **Total** | | **72 ambient lidded (30 S, 27 M, 15 T) + 9 cool + ≤ 37 nested empties** |

Allocation: 30 seasonings (S, 0 spare), 30 M food (27 M + 3 in T), 10 T food (cans, jars) → 2 T spare; 26 empties
in the nests (11 spare); 9 cool places (CAP-024 ≥ 8). **The column is full.** Relief, in order of preference:
Ben drops the separate cool zone (Q1: +17 positions), the L-corner column (§6.4), the 4.2 m configuration. Without
nests **and** with the cool section, the column is ≈ 15 positions short: then the cool zone cannot stay here.

## 4. Cold selection: top-wall exit (C1-B) with S1 stacks inside, in both shells

### 4.1 Decision

| Item | Fridge | Freezer |
|---|---|---|
| Wall position | machine X 600–1200 (next to the ambient column: ≈ 55 passes a day) | X 0–600 (machine end: ≈ 10 passes a day) |
| Appliance | 178 cm built-in **static larder fridge without ice box** (Liebherr IRBd/IRBe 51**20** class, ≈ 300 L, 559 × 1770 × 546) [U: model] | 178 cm built-in **NoFrost freezer** (Liebherr IFN/SIFN 51xx, Siemens GI81NA… class, ≈ 210 L) [U: model] |
| Price [U] | ≈ €800–1,300 | ≈ €900–1,500 |
| Exit (C1 concept B) | window 260 × 260 cut in the verified middle band of the top wall; double-walled PP throat **210 × 200** (S and M boxes, upright 1 L cartons in XL height); stainless exit plate 1.4016; 40 mm PU slide that lifts off and parks along −x; constant-force spring closes it on power loss; **magnetic compression gasket**; 1 small 12 V gear motor | same, plus a **100 mm skirt** below the NoFrost ceiling jet and a **3 W dew-point-controlled heated seat** |
| Open time per passage | ≈ 3.4 s (CLD-004 ≤ 10 s) | same |
| Inside | **S1 stacks**, 2 × 2 GN 1/6 stacks on posts that hook into the liner's shelf ribs; port stack under the throat; robot zone 350 mm at the top inside | same |
| Motors in the cold | CoreXY motors on the cabinet top, shafts through PTFE bushings in the exit plate; **hoist servo on the trolley inside** at +4 °C (no issue) | CoreXY outside as in the fridge; **hoist servo inside at −18 °C**: cold-rated IP67, −40 °C grease, warmed by winding current ≈ 60 s before a move instead of 3–5 W standby [U] |
| Positions | ≈ 45–50 raw, ≈ 38–45 usable with the dig reserve [C on U interior; C1's 52–58 needs a second footprint, §1.3] | ≈ 32 raw, ≈ 24 usable with stacks capped at 9 [C on U] — CAP-022 ≥ 20 ✓ |
| Retrieval | planned (pre-dug overnight with the hatch closed) ≈ 6 s; top ≈ 8 of each stack ≤ 45 s; an **unplanned bottom box ≈ 60–70 s** (CLD-006 ≤ 45 s missed for those, Q2) | cap 9 per stack → worst ≈ 40 s, CLD-006 ✓ |
| Added energy [D: C1] | exit ≈ 7 kWh/a (+6 %); trolley parked < 1 W | exit + seat heater ≈ 38 kWh/a (+13–17 %); hoist pre-warm ≈ 2 kWh/a [E] |
| Access cost [D: C1] | ≈ €300 | ≈ €335 |
| Mechanism + grid [E] | ≈ €1,000 (S1 without spray kit, RFID and own controller; NEMA 17) + ≈ €150 posts and grate | ≈ €1,100 (cold-rated hoist) + ≈ €150 |
| Manual access | OEM door kept as the service door: front stacks direct, rear stacks after moving the front boxes aside; reed switch on the door stops the robot | same, with gloves |
| Raw meat (CLD-011, CLD-003) | R boxes leak-tight (BOX-008) in the rear-left stack (coldest, over the compressor step); digging may set an R box on an RTE stack for ≈ 10 s (logged). No 0–2 °C sub-zone (S requirement, Q6) | – |

**Both shells together:** 1,200 mm of wall (or 1,140 mm if the two 559 mm appliances can stand 20 mm apart [U]).
Cold energy ≈ 115–125 + 7 + 220–300 + 40 ≈ 385–470 kWh/a = **1.05–1.3 kWh/day** against RES-004 ≤ 1.2 (M): choose
models whose labels sum to ≤ ≈ 340 kWh/a (class D or better) [U].

### 4.2 Why this combination

* **Top exit (C1-B)** is the only access that costs no wall width in K9b (the gallery picks from above, and there is
  no front lane in 600 mm depth). Cold air does not climb, so a horizontal hatch exchanges about the box's own
  volume (5–10 L), and a vestibule adds nothing (C1 §8). One actuator, one static gasket, OEM door kept. C1 scored it
  4.40 against 3.35 for the next concept.
* **S1 inside**, in both shells, because:
  * it is the only mechanism that comes near CAP-021's 45 in one fridge shell (S4: 24, S3: 27–33, S5-A: ≈ 40,
    S2 on a door: 38–42);
  * its port stack sits naturally under a top throat;
  * the freezer's low traffic (≈ 5 retrievals a day) makes digging harmless there, and its stacks can be capped to
    meet CLD-006;
  * **one cold robot design, built twice**, sharing the passive hook gripper with the gallery (§5) and the 200 W
    servo with S4. Using S4 in the freezer (24, zero depth margin) would add a third mechanism variant and put
    two motors in the cold instead of one.

### 4.3 What we lose against the runner-up

* **Fridge, against S5-A M-only rings (≈ 40) or S2 on the door (38–42):** we lose retrieval without digging, and
  CLD-006 for unplanned deep boxes (≈ 60–70 s instead of ≤ 20 s). We keep ≈ 5–10 more positions, bought boxes,
  one mechanism for both shells, ≈ 3 moving assemblies instead of ≈ 50 cradle parts (S5-A) or a custom door (S2).
* **Freezer, against S4 with one face (24):** we lose the 6 s retrieval and accept stacked boxes (freeze-bonding
  risk, mitigated by lid stand-off pads and drying returns; freezer returns are rare). We gain one motor in the
  cold instead of two, a depth margin (S4 needs ≥ 375 mm of the ≈ 370 expected) and the same robot as the fridge.
* **The honest limit:** no mechanism meets CAP-021 (45 positions) **and** CLD-006 (45 s for every box) in one
  178 cm shell. We keep CAP-021 and the 3.6 m wall, and rely on menu planning for chilled boxes, as S1 does in the
  ambient design we rejected. The difference is the traffic: chilled boxes are almost all menu boxes, because #17
  moved breakfast dairy and table drinks to the separate fridge. Q2 asks Ben.

### 4.4 The cool zone (CAP-024: 8–15 °C, ≥ 8 boxes)

| Option | Positions | Energy | Width | Verdict |
|---|---|---|---|---|
| Cellar sleeve inside the fridge (C1 ii) | −15–20 fridge positions | ≈ 46 kWh/a, counted in RES-004 | 0 | **rejected**: the fridge has no spare positions (§4.1) |
| Wine cooler / compressor cabinet (C1 iii) | 8+ | 100–150 kWh/a | ≥ 300 mm | rejected: breaks 3.6 m |
| **Thermoelectric section at the bottom of S4's rear face** | **9 T places**, costs ≈ 17 ambient positions | ≈ 60–130 kWh/a [E: 1 W/K at ΔT 8–10 K, Peltier COP ≈ 0.6] | 0 | **default**, space reserved in §3.5 |
| Dark ambient storage instead (no separate zone) | 0 | 0 | 0 | **recommended to Ben (Q1)**: it is how most kitchens keep potatoes, garlic, tomatoes and citrus; with weekly shopping the shelf life is sufficient |

The default section: the bottom three T levels of S4's rear face, all three lanes (≈ 55 L), 30 mm PIR on the wall,
sides, top and bottom, closed towards the aisle by a **motorised insulated roller shutter** whose drum takes one
level height (+1 small gear motor, compression seal at the bottom edge); a 40 W Peltier unit with fans in the rear
service zone; ethylene emitters (tomatoes, apples) in their own gasketed boxes. Cost ≈ €350 [E]. It is the
ugliest part of the whole storage design, which is why Q1 recommends dropping it.

### 4.5 Storage cost, reported honestly (#22)

| Module | Machine part | Structure | Access | Sum |
|---|---|---|---|---|
| Ambient S4 (+ cool section) | ≈ 1,470 (+ ≈ 250) | ≈ 850 (+ ≈ 100) | – | ≈ 2,670 |
| Fridge S1 | ≈ 1,000 | ≈ 150 | ≈ 300 | ≈ 1,450 |
| Freezer S1 | ≈ 1,100 | ≈ 150 | ≈ 335 | ≈ 1,585 |
| **Storage total** | **≈ 3,800** | **≈ 1,250** | **≈ 635** | **≈ €5,700** |

Plus appliances ≈ €1,700–2,800 and ≈ 170 boxes at ≈ €12 ≈ €2,000. The storage machine part alone is ≈ 1.9 × the
€2,000 that #28 expected for the whole machine part. The levers for the cost round: lean robots (no camera, open-loop
X/Y: ≈ −€250 each), one shared controller for all three robots, the chest freezer F (≈ −€1,000, but manual defrost,
fails CLD-008), and dropping the cool section (−€350).

## 5. Box standard and the bayonet-stub conflict

### 5.1 The conflict

K9b (§2.5, §2.12) moulds a Ø 22 × 40 mm bayonet stub with collar, ≈ 45 mm proud, on the rear short side of every
storage box. Every storage design measured what that costs: S1 9 → 6 cells (−33 %), S2 one lane short in every
direction (−33 %), S3 ≈ 40 mm per row, S4 one rack face instead of two (−50 %), S5 the same. Pointing the stub up
costs 45 mm per level. **No dense store can carry it.** The stub is only needed in the cell, for the ≈ 20–25 box
moves of a meal, while the box spends the rest of its life in storage.

### 5.2 Options

| Option | Storage loss | Cell change | Actuators | Verdict |
|---|---|---|---|---|
| Stub moulded on every box (K9b) | −33 to −50 % | none | 0 | rejected |
| Stub recessed in a moulded pocket inside the flange outline | 0 | custom box mould (€30–50 k), pocket eats box volume, crevice | 0 | rejected (#20, BOX-011) |
| Clip-on stub collar fitted by the lid station (S3) | 0 | a loose part that clamps every box rim, one more station step, its own cleaning | 0–1 | rejected: one more handling step per box and a part in the splash zone |
| Cell hand grips the rim (K9b fallback, K6b pin jaws) | 0 | +1 actuator, +2 dynamic seals | +1 | fallback only |
| **Stubless boxes + a permanent stub carrier on the box shelf** (S2 §2.3; the same idea as K9b's STOW-pack carrier, C4 R-5) | **0** | 3 carriers, 2 shelf pins per place | **0** | **chosen** |

### 5.3 Decision: the box standard

| Item | Standard (all modules: ambient, fridge, freezer, cell) |
|---|---|
| Family | **Bought GN 176 family** in PP impact copolymer or Tritan (−40…+95 °C, commercial dishwasher, translucent; no PC, no homopolymer PP). **GN 1/6 (176 × 162)** in depths 65 (S), 100 (M), 150 (T), 200 (XL, fridge only: two 1 L cartons upright). **GN 1/9 (176 × 108)**, depth 65 or 100, ambient only (spices; it hangs in an S slot of S4). **No GN 1/3 storage boxes** (S4 and the 210 × 200 cold throat cannot carry them). |
| The common dimension | Every box is **176 mm across its "long sides"**: the two rims that are 176 mm apart (the 162, 108 or 325 mm long sides). All grippers, runners and carriers use this one spacing. |
| Rim | Continuous flange, ≥ 2.5 mm thick; overhang ≥ 9 mm on the two long sides (S4 runners), ≥ 7 mm on the ends; **free underside ≥ 30 mm at mid-span of both long sides** (gripper hooks); on **both 176 mm ends** a J-hook seat: an inner vertical face ≥ 4 mm high, 25–45 mm from the left corner, ≥ 5 mm clear of the body (normally the downturned rim skirt; otherwise a 4 × 20 mm slot punched outside the lid's seal line) [U: E2]. |
| Lid | Flat gasketed seal-cover lid on top of the flange, flush with its outer edge, ≤ 8 mm, no clips; four 1 mm stand-off pads on top (stacking in the cold, freeze-bonding); flat centre for the lid station's vacuum cup. Removed at the lid station before the cell, refitted after. |
| Bottom | Flat with a perimeter foot ring; stands on a lid without rocking; drains when washed upside down. |
| Protrusions | **None outside the rim outline. No stub, no tang, no rib.** |
| Identity | Two HF NFC inlays (ISO 15693), one in each 176 mm end rim, rated for washing and −40 °C [U]; DataMatrix laser-marked on both ends. |
| Mass | ≤ 5 kg gross (BOX-004). |
| Empties | Lid-less empties of one size nest at ≤ 25 mm pitch without sticking [U: E2]; their lids wait at the lid station. |

**How every gripper holds a box — one design everywhere.** A passive toggle gripper (S1's "ballpoint pen" cam,
no motor, no wire): an **open frame that rests on the rim** (it never covers the opening of an opened box) and two
hooks that close under the two long-side rims at mid-span. The same gripper hangs on the gallery hoist and on both
cold S1 trolleys. Where boxes are picked:

* S4 carriage: its two runners get a **30 mm notch at mid-span** so that the hooks reach under the long-side rims
  (S4 had planned to grip the ends; changed so that one gripper serves everything);
* cold S1 grids: the hooks run in the 12 mm gaps between the stacks, as S1 drew it;
* cell box shelf: the carriers' long walls have the same 30 mm mid-span notches.

**How the cell holds a box: the stub carrier.** A stainless carrier (laser-cut and bent 1.4404, ≤ 0.7 kg) with a GN
1/3 opening (325 × 176), the K9b bayonet stub on its rear short side (riveted, K9c), and:

* two **spring hooks** over the box's long-side rims, **opened by two pins in the shelf** while the carrier sits on
  the shelf and closed by their springs as soon as the hand lifts the carrier — so the gallery sets the box in and
  takes it out freely, and the box cannot fall out when the hand pours or inverts it. No actuator.
* a **sprung end pusher** that presses a GN 1/6 or 1/9 against the stub end, so the centre of mass stays ≈ 100–120 mm
  from the sleeve: carrier + 5 kg box ≈ 5.7 kg and ≈ 7 Nm, inside the hand's 6 kg / 9.4 Nm (K9b §2.4).
* the same carrier holds an opened STOW pack (can, jar, carton) upright, replacing C4 R-5's separate carrier.

### 5.4 What K9b must change

| # | K9b section | Change |
|---|---|---|
| K-1 | §2.5, §2.12; C4 R-2 | **Storage boxes carry no stub.** Stubs stay on ware, tools and carriers. The cell receives opened GN 1/9 and 1/6 boxes (not 1/3), always in a carrier. |
| K-2 | §2.6 box shelf | Two places = **two permanent stub carriers** (§5.3) plus **one red carrier** for class R boxes; two release pins per place. One carrier design also serves STOW packs (C4 R-5). |
| K-3 | §2.6, §2.1 | Two carriers side by side in X need ≈ 380 mm; K9b's shelf is 290 mm (X 1870–2160). **Use the 90 mm K9c saved** (cell 1660 → 1750 again, machine stays 3,600) to widen the shelf; or one carrier on the pick line and a plain buffer place. |
| K-4 | §2.6, transport | **One pick line for the whole machine, y ≈ 290 ± 10**, fixed in the layout round. Limits: S4's aisle centre is y 298 (its racks can move ≈ 10 mm towards the wall); the cold window (260 × 250, throat 200 along y) must end ≥ 80–90 mm behind the cabinet front, i.e. at y ≤ ≈ 410–420 (C1 §1.2) [U: E1]. The carriers then sit at y ≈ 200–525, the stub end at y ≈ 200 and the wrist at y ≈ 150 (≥ 130 ✓). A gallery Y axis is not needed. |
| K-5 | §2.4 | Hand load case: carrier + box ≤ 5.7 kg, centre of mass ≤ 120 mm, pouring and 180° inversion with the hooks closed (to be shown in E3). |
| K-6 | §2.12, spice dosing | The "levelling edge on spice boxes" moves to the box's own straight GN rim, or to a bar on the carrier's far end; K9b to confirm with its spoon geometry. |
| K-7 | §2.8, §2.10 | Carriers are ware: +3 items, washed in the well daily and after every class R box. |
| K-8 | transport (C4) | Gallery: passive toggle gripper on the long-side rims (§5.3); hoist stroke ≥ 450 mm (box shelf z 1550; cold throats ≈ 250–300 mm; S4 hand-over ≈ 60 mm, nest hand-over ≈ 285 mm). **Lid station** (C4 R-4, not yet placed): proposed in the box shaft above the shelf (X 1870–2250, z ≈ 1750–1950); it keeps the lid on a vacuum cup while the box is in the cell, and stores the ≈ 26 lids of the nested empties. |
| K-9 | §2.12 | Storage runs **pre-fetch / pre-dig** from the menu plan (UC-04) ≥ 30 min before cooking; storage time per box ≈ 2–6 s, gallery ≈ 10 s, ≈ 6 min of transport per 4-person meal, overlapped with cooking [E]. |

## 6. Layout of the 3.6 m machine

### 6.1 Widths

| Module | Machine X | Width | Content |
|---|---|---|---|
| Freezer | 0–600 | 600 | 178 cm built-in NoFrost freezer, S1 2 × 2 stacks, C1-B exit with skirt and heated seat |
| Fridge | 600–1200 | 600 | 178 cm built-in larder fridge, S1 2 × 2 stacks, C1-B exit |
| Ambient (+ cool) | 1200–1850 | 650 | S4: 2 faces × 3 lanes, nest level, cool section at the bottom of the rear face; 20 mm PIR on the wall towards the cell (STO-007) |
| Cell | 1850–3600 | 1750 | K9b; K9c's 1660 plus the 90 mm it saved, given to the box shelf for two carriers (K-3) |
| **Total** | | **3,600** | PHY-004 (M) met. 3,510 is possible only if the box shelf keeps one carrier on the pick line |

Order: the fridge sits next to the ambient column because it has five times the freezer's traffic; the ambient
column sits between the cold module and the cell's cool end (box shelf and tool cabinet; the oven and the well are
at X 3070–3550). Heights: appliances on a plinth at z ≈ 120–1890, the 110 mm gap above them holds the exit plates,
the slide motors, the CoreXY shafts and a front vent grille ≥ 200 cm² per shell (the built-in appliances vent
through the top); S4 occupies z 80–2000; the gallery z 2000–2200 runs over everything.

### 6.2 Front view (fronts removed) and the pick line

The ambient column is drawn as seen through its door: the front face hides the aisle and the rear face, whose
contents are listed in brackets.

```
 X  0               600              1200            1850         2250                          3600
 2200 +----------------+----------------+---------------+------------+------------------------------+
      |  TRANSPORT GALLERY z 2000-2200: one X axis, hoist >= 450 mm, passive hook gripper,           |
      |  every pick and drop on the pick line y = 290 +- 10                                         |
 2000 +====[THROAT]====+====[THROAT]====+===[HATCH]=====+=[SHAFT]====+==============================+
      | exit plate,    | exit plate,    | carriage at   | lid station|                              |
      | slide, XY motors, vent grille   | hand-over     | z 1750-1950| K9b cell                     |
 1890 +----------------+----------------+ (lid z 1941)  +------------+ (tool cabinet X 2250-2450,   |
      | robot zone     | robot zone     |               | BOX SHELF  |  hob, hub, oven, well:       |
      | CoreXY + hoist | CoreXY + hoist | FRONT FACE    | 2 carriers |  K9b 2.2)                    |
      |----------------|----------------| 3 lanes:      | z 1550     |                              |
      | S1: 2 x 2      | S1: 2 x 2      |  7 x S        +------------+                              |
      | GN 1/6 stacks, | GN 1/6 stacks, |  4 x M        |                                           |
      | port stack     | port stack     |  5 x T        |                                           |
      | under the      | under the      |               |                                           |
      | throat         | throat         |               |                                           |
  120 +----------------+----------------+---------------+                                           |
      | plinth, vent intake             | drip tray     |                                           |
    0 +----------------+----------------+---------------+-------------------------------------------+
        FREEZER ≈ 24      FRIDGE ≈ 38-45   AMBIENT 72 lidded + 9 cool + <= 37 nested
        (behind the ambient aisle, the rear face: 5 x M, 3 x S, the nest level, the cool section 3 x T at the bottom)
```

```
 top view at z ≈ 1950 (y 0 = wall, y 600 = front)
 y 600 +----------------+----------------+---------------+--------------------------------------+
       |  OEM door      |  OEM door      | human door    |  cell front, hatch drawer            |
 ~420  |  - - - - - - - - - - - - - - - -|  front face   |                                      |
       |    [window]    |    [window]    |---------------|   [carrier 1][carrier 2]             |
 ~290  | . . .[throat]. . . . [throat]. . . .[carriage]. . . .[ box  ][ box  ] . . . pick line |
       |    (C1 middle  |                |  aisle        |   stub end at y ≈ 200                |
       |     band)      |                |---------------|                                      |
       |                |                |  rear face    |  X box / mast lane y 0-120 (K9b)     |
 y 0   +----------------+----------------+---------------+--------------------------------------+
       X 0  port ≈ 300      port ≈ 900     port ≈ 1525    shelf ≈ 1870-2250
```

### 6.3 How the gallery connects the modules

* **One X axis, one hoist, one passive gripper**, no Y axis: every module presents its out-box, and takes its in-box,
  on the pick line. The ports are the two cold throats (X ≈ 300 and ≈ 900), the S4 roof hatch over lane B
  (X ≈ 1525) and the box shaft over the shelf (X ≈ 1870–2250). The longest travel, freezer to shelf, is ≈ 1.8 m.
* **Hand-over depths below the gallery floor (z 2000):** S4 carriage ≈ 60 mm (nest hand-over ≈ 285 mm); cold port
  stack top ≈ 250–300 mm through the throat; box shelf 450 mm. All within K9b's 450 mm hoist stroke.
* **A typical retrieval** [E]: storage 2–6 s (planned) while the gallery is elsewhere; gallery pick ≈ 2 s, travel
  ≈ 2 s, lid off at the lid station ≈ 3 s, lower into a carrier and release ≈ 3 s → ≈ 10 s of gallery time per box,
  ≈ 6 min for the 20–25 box moves of a 4-person meal, overlapped with cooking.
* **Decoupling (TRN-008):** S4's carriage holds one out-box; each cold port stack holds a second box under the
  out-box; the shelf has two carriers. The gallery never waits for a dig.
* **Thermal:** a cold throat opens only while the gallery hook is in it (≈ 3.4 s); digging and in-cell travel run
  with the hatch closed.

### 6.4 Does the L-corner help?

* **In the straight 3.6 m baseline: no.** There is no corner.
* **If Ben's kitchen is an L** (OQ-11, PHY-004 allows it, TRN-003 requires the transport to follow it): the natural
  split is leg A = cold + ambient (1,850 mm) and leg B = the cell (1,750 mm). The corner square (≈ 600 × 600) is
  useless for the cell (no front for the hatch drawer, no reach for the mast) and for an appliance (its door cannot
  open), but it suits **storage served from above**: a second ambient column there (≈ 100 positions, S1-type top
  grid, because hand access to a corner is poor whatever is inside) would end the capacity squeeze of §3.5 and could
  take the cool section and the empties.
* **The price:** the gallery must turn the corner. That means a second X axis on leg B and a transfer place in the
  corner (≈ +€500, +1–2 actuators, ≈ +4 s per box), and a second mechanism type in storage.
* **Verdict:** the corner helps only where the kitchen is an L anyway; then it should hold storage, not the cell.
  It is not part of the baseline.

## 7. Open questions for Ben (with the default used until he answers)

| # | Question | Default |
|---|---|---|
| Q1 | **Cool zone (CAP-024, 8–15 °C, ≥ 8 boxes):** do potatoes, garlic, tomatoes, citrus and squash need a separate cool zone, or is dark storage at room temperature (≈ 20 °C) acceptable, as in most kitchens, with weekly shopping? | Keep the requirement: thermoelectric section in S4's rear face (§4.4). **Recommendation: drop it**: +17 ambient positions, −1 actuator, −€350, −60–130 kWh/a. |
| Q2 | **Fridge capacity against speed:** one 178 cm shell gives ≈ 38–45 usable positions with S1 stacks; an unplanned deep chilled box then takes ≈ 60–70 s (CLD-006 asks ≤ 45 s). Accept (a) ≈ 45 positions with menu-planned retrieval, (b) ≈ 36 positions with every box ≤ 45 s, or (c) a second fridge shell (+600 mm, only in the 4.2 m configuration)? | (a): chilled boxes are menu boxes, because table drinks and breakfast dairy live in the separate fridge (#17). |
| Q3 | **Long pasta (≥ 25 cm)** fits no GN 1/6 box, and no design stores GN 1/3. Break it in half at decanting, buy short shapes only, or keep long pasta outside the machine? | Decanting snaps long pasta in half into a T box. |
| Q4 | **Appliances:** built-in larder fridge + built-in NoFrost freezer cost ≈ €1,700–2,800 (#28 assumed ≈ €1,000), and cutting the top wall voids their warranty. Accept? | Accept. Cost-down fallback: chest freezer (C1 F, ≈ −€1,000) only if a manual defrost every 1–2 years is acceptable. |
| Q5 | **Kitchen geometry (OQ-11):** straight wall of ≥ 3.6 m, or an L? | Straight 3.6 m; the L-corner is a variant (§6.4). |
| Q6 | **Raw meat sub-zone at 0–2 °C (CLD-003, S):** needed, or is raw meat at the fridge's coldest stack (+2–4 °C), used within 2 days or frozen at ingestion, enough? | Drop the sub-zone for the MVC. |
| Q7 | **Human access:** the customer valued grab-from-top for access. In this machine S4 is the accessible one (open the door, any box, at most one other box moved). Is that what he meant? | Yes. |
| Q8 | **Cost:** storage hardware ≈ €5,700 (machine part ≈ €3,800), plus appliances and ≈ 170 boxes — far above #28's €2,000 for the whole machine part. Accept for now (#22) and cut in the cost round? | Accept now; levers listed in §4.5. |
| Q9 | **Empty boxes nested without lids**, lids kept at the lid station (needed for the S5-B nest level)? | Yes, if E2 passes. |

## 8. Cheapest experiments, in order

| # | Experiment | Cost, time | Decides |
|---|---|---|---|
| E1 | **Measure the shortlisted appliances:** interior W × D × H, compressor step, top-wall thickness, thermal camera on the top after 2 h (frame heater, ducts, cables), service manuals (C1 §11 #1) | €0–100, 1 day | fridge positions (Q2), window position and pick line (K-4), freezer stack heights |
| E2 | **GN box samples** from 3 makers (GN 1/6-65/100/150/200, GN 1/9): rim overhang, J-hook seat, free underside at mid-span, lid fit and pads; nesting pitch, sticking, rim gap; 50 dishwasher cycles and one night at −18 °C; NFC tag fixing | ≈ €230, 2–3 days | box standard (bought as is / punched slot), nest level (Q9) |
| E3 | **Stub carrier mock-up:** bent stainless carrier with shelf-opened spring hooks and end pusher; 500 insert/remove cycles; inverted pour and shake with 0.2–5 kg; release on the shelf pins; riboflavin test after dishwasher washing | ≈ €150, 1 week | the K9b change (K-1…K-5) |
| E4 | **S4 one-lane rig** (S4 §8): 6 levels, J-hook on a Y belt, runner step ±0.5–2 mm, friction dry, wet and frosted, transfer time, lifting the box off the carriage through the 30 mm runner notch with the passive gripper | ≈ €500, 2 weeks | ambient mechanism |
| E5 | **Cut test in a used fridge** (C1 §11 #2): 260 × 250 window, slide on a magnetic gasket, CO₂ tracer per pass, energy and seat temperature for a week; plus the NoFrost fan-jet smoke test (C1 #3, €50) | ≈ €300, 2 weeks | C1-B exit, skirt length, energy |
| E6 | **S1 cold stack rig with the passive toggle gripper** (S1 §8), 1,000 cycles at +20 °C, then in a chest freezer at −18 °C: gripper toggling, tapes, hoist-motor cold start after pre-warming, freeze-bonding of stacked lids. It is also the gallery gripper prototype | ≈ €750, 2–3 weeks | cold mechanism, gallery gripper |
| E7 | Only if Q1 keeps the cool zone: heat-load mock-up of the cool section (PIR box, roller shutter, Peltier, logger) | ≈ €150, 1 week | cool-section energy |

E1 and E2 cost almost nothing and gate most later decisions, so they run first. E3 is next because K9b's design depends
on it. E4–E6 prove the mechanisms.
