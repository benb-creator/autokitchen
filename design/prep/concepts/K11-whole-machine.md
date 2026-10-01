# Meal preparation — Cost round 2: K11, the whole machine (cell, storage, appliances)

**K11** is round 2 of the cost / simplicity / space optimisation (#28). It follows the recommendations of critique
C6 (`../critique/C6-K10-review.md` §7.3): K9c's in-cell wash well and bench as the base, K10's thermo-cooker only
behind a controllability gate (fallback K9c's hub), K10's cost discipline, and one shared rail with two carriages
(K10-W2) reconciled with the storage round (`../../storage/10-storage-comparison.md`). Binding: DECISIONS #1–28.

Markers: **[D]** from an earlier document (named); **[W]** web price checked 2026-10-01 (URL in §3.1);
**[E]** engineering estimate; **[C]** calculated here; **[U]** unknown, a test decides. Prices: EU retail or
job-shop price for one unit incl. VAT, own assembly labour not counted (as K9c/K10).

**Result.** K11 keeps K9c's wet cell — donor-tub well under the deck with an 82 °C final rinse (A0 ≈ 95), Gastro
deck, printer-class gantry with the canned roll — and rearranges it so that a bought **thermo-cooker** (gated by
R1; fallback K9c's hub at net +€45) and a **60 cm 4-zone 7.4 kW hob** (four pans, COK-002 met in full) fit into
1,750 mm: the serving hatch moves onto the 0.25 m² well-lid bench. Cooker + three pans + K9c's hatch drawer would
need 2,040 mm. **One beam** carries the cell carriage and a **storage carriage** that replaces the gallery and every
hand-over; it cannot replace random access inside a store without failing STO-003 (ambient) or CLD-006 (cold),
while CLD-004 survives with one sub-lid per stack. **Option A (compliant**: S4 + C1-B exits with lean S1 robots):
machine part **€7.29 k**, out of pocket **≈ €14.4 k**. **Option B (cheap**: everything dug from the top through
sub-lids): **€5.60 k / ≈ €12.3 k**, needs waivers on STO-003, CLD-006 (unplanned boxes) and CAP-024. Household
appliances **€3.24 k** + shelving €1.27–1.67 k against Ben's ≈ €3–3.5 k; the machine part is **2.8–3.6 × his
€2 k** (cell €3.86 k, −10 % against K9c). Coverage 232 (93.5 %); B6 fails by ≈ 1 min without the push dicer, B3,
B5, B7 are marginal; all clean ≈ 72–80 min after serving. Ben's decisions are in §7.1, the €4.0–4.5 k test
programme in §7.2.

---

## 0. Decisions taken from the sources

One line each: what K11 adopts (or explicitly does not adopt) from each input.

**DECISIONS.md**
* #1 — the 400 V 3 × 16 A connection is used; a phase plan with load shedding stays mandatory.
* #4 — food contact only stainless, PE-HD and moulded food-grade parts; FDM only in the dry zone.
* #5 — every hob is driven through an interface board, not a consumer API; the same logic puts the thermo-cooker behind a gate.
* #6 — the machine takes back, washes, dries and dispenses its own dishes at the hatch.
* #8, #9, #25 — the machine washes, peels and cuts produce itself (spit + blade post); peeled onions are bought.
* #11 — height 2,200 mm, depth 600 mm.
* #16, #17 — storage holds cooking ingredients only; a separate ordinary fridge exists; CAP-020…023 apply as written (#17 is already inside CAP-021, C6 §5.1).
* #18, #19 — sized for 2 persons, every meal possible for 1–4.
* #20 — simplicity decides close calls (fewer actuators, fewer custom parts, fewer special cases).
* #21 — job-shop stainless parts allowed.
* #22, #23 — cost and water reported honestly; the €2 k target is a design target, not a gate.
* #24 — the bought oven may be turned and its door worked by a hook rod; its knobs bypassed by an SSR.
* #26 — coverage ≥ 231 of 248 meals (93 %).
* #27 — no texture change: browning in pans, the cooker's blade chop only where the cooked dish hides it.
* #28 — household appliances used largely as bought; the result is compared with ≈ €3–3.5 k appliances + ≈ €2 k machine part.

**C6 (the starting point)**
* §7.3-5 — K9c's donor-tub well under the deck (82 °C final rinse, turnaround load in the meal); no appliance door over the hot zone.
* §7.3-6 — a bench of ≥ 0.25 m² besides the board, and a hatch that presents two plates side by side.
* §7.3-7 — a third pan-capable hot position with its own generator.
* §7.3-1 — thermo-cooker only after R1 (network check → bus sniff and replay → stylus fallback); never bypass its power board; two units of one model bought at once; fallback = K9c hub.
* §7.3-2 — one rail pair with two carriages (W2); W1 (cell hand digs storage) rejected.
* §7.3-3 — 5 L boiler, Klipper single-board controls, folded riveted stubs, Gastro deck, countertop convection oven but not above the hob.
* §7.3-4 — bought gadgets only after a HYG-027 cleanability test: ricer first, unpeeled-garlic press second; dicer and mandoline only as fallback.
* §7.3-8 — storage shown to Ben as A compliant and B cheap with a named waiver.
* §6.2 — the missing items are budgeted: cooker splash cover and base sleeve, backflow preventer and leak tray, hatch watchdog, X-box partition, nest stack, realistic job-shop prices.
* §3.6 — class R boxes never above RTE; sleeve rinse after every R grip; dry storage gallery separated from the wet cell.
* §1.3, §2.1 — jug emptying and the cooker's lid type are test items; a removable clamped lid is preferred over a hinged one.
* §6.4 — the whole out-of-pocket figure is reported next to the machine-part figure.
* §7.4 — the cheapest-first test order (desk walk, R1, emptying, A0 loggers, gadget cleanability, mock-up, cut test).

**K9c (base layout and parts)**
* §5.1 G1–G12 — printer-class Cartesian gantry under Klipper; its X beam becomes the shared rail.
* §5.1 R1–R4 — canned roll coupling (no lip seal: 2 dynamic seals, not 3).
* §5.1 WL1–WL4 — donor slim dishwasher's own tub as the well; R2-10: the donor heats the final rinse to 82 °C, no 30 L store.
* §5.1 RC1–RC4 — rinse cup, spout, sleeve jets, chute with spring flap and blade post.
* §5.1 E1–E14 — Gastro table deck, stainless liners to z 1450, profile frame, sliding glazing with a household door lock, IKEA tool-cabinet carcass; R2-1 shared carcass with the ambient module.
* §5.1 H1–H8 — the hub (T, S, ring coil, €435) is the R1 fallback, not the base.
* §5.1 C1–C9 — Octopus Pro + Raspberry Pi 5, one wide camera, household safety chain, power manager.
* §5.1 WA4–WA6 — bought special tools, custom fixtures, carriers.
* §5.2 K1–K11 — ordinary kitchen content priced and shown outside the machine part.
* §1.3 P1–P27 — web prices reused.
* §7 — tests K1–K15 kept for the parts kept.

**K10 (cost discipline, appliances, shared rail)**
* Q1/Q2 — thermo-cooker as a household appliance (Monsieur Cuisine Smart €399 or Mambo 11090 €219), gated.
* Q3 — 25 L countertop convection oven (€70–126), turned, hook-rod door, SSR + thermocouple.
* Q5 — 5 L under-sink boiler 85 °C (€149–152) for spout, jets and nozzle rail.
* Q6/Q7 — unpeeled-garlic press and ricer/Spätzle press on a lever seat (gated by HYG-027).
* §4.1 C5–C9 — appliance interfaces counted in the machine part.
* §4.1 WA1 — laser-cut folded stubs, riveted, €4.50.
* §7.2–7.3 — the W2 shared rail and storage carriage (lines S1, S4, S6–S9), corrected per C6 §6.
* Not taken: dishwasher as bought (I3), no in-meal wash with duplicates (I4), W1, lip-sealed roll (I5 variant), serving without a hatch (I13), mandoline and dicer as primary routes.

**Storage round (10-storage-comparison)**
* §3 — S4 aisle shuttle in the 650 mm ambient column with the S5-B nest level (72 lidded + 9 cool + ≤ 37 nested).
* §4 — C1-B top-wall exits (throat 210 × 200, ≈ 3.4 s open) with S1 2 × 2 stacks inside a 178 cm built-in larder fridge (≈ 38–45) and NoFrost freezer (≈ 24, stacks capped at 9).
* §5.3 — box standard: bought GN 1/6 and 1/9 in PP copolymer or Tritan, no stub, flat seal lid, one passive toggle gripper on the long-side rims, two NFC tags.
* §5.3–5.4 — stub carriers on the box shelf (two green, one red, shelf-opened spring hooks) and a lid station.
* §6 — layout freezer 0–600, fridge 600–1200, ambient 1200–1850, cell 1850–3600; one pick line y ≈ 290.
* §4.4, Q1 — cool section (CAP-024) kept in option A as the Must, recommended for Ben's waiver.
* Q2 — menu-planned pre-digging of deep chilled boxes (default).
* §4.5 — storage cost basis (machine part ≈ €3,800, structure ≈ €1,250, access ≈ €635; ≈ 170 boxes at ≈ €12).
* §8 — experiments E1–E7.

**K9b (only for mechanism details)**
* §2.4–2.11 — kinematic limits, well loading and clearance rules, oven hook-rod loading, plating and dish return by carriers.
* §6 — B1–B12 times as the reference for the benchmark walk.

---

## 1. The whole machine

### 1.1 The width problem, and how K11 solves it

C6 asked for K9c's layout plus a thermo-cooker plus a third pan position. Put side by side in K9c's columns, that
does not fit [C]:

| Column (K9c order) | Needs | Why |
|---|---|---|
| S column: hatch drawer (front), rinse cup + chute + egg fixture (rear), box shelf and tool cabinet above | 580 | two plates side by side (2 × 270 + rim) |
| Domino 2 zones | 300 | |
| Thermo-cooker (≈ 340 × 340) + lever seat behind it | 360–390 | K10 used 400 |
| Third pan position: single 2 kW plate (glass ≈ 280 × 350) | 300 | C6 §7.3-7 "+300 mm" |
| Well (slim dishwasher 448) with lid-bench, oven above | 480 | |
| **Sum** | **≈ 2,040** | the storage round leaves **1,750** (freezer 600 + fridge 600 + ambient 650 = 1,850) |

A 3.9 m machine breaks PHY-004 (≤ 3.6 m, M). Shrinking storage by 290 mm is not possible without failing CAP-020
or CAP-021 (S4 needs its 650 mm for three lanes, the built-in shells need their 600 mm niches). K11 therefore
changes three things inside the cell:

1. **A 60 cm 4-zone induction hob with 7.4 kW (2 × 3.7 kW, one phase per side)** replaces "domino + cheap single
   plate". Same 600 mm, about the same money (€436 [W1] against €300 + €50 + a second interface), but **four** pan
   positions and two zones that boost to ≥ 3 kW at the same time: COK-002 is met in full and K9c's Q7 waiver
   disappears. This is also the appliance on Ben's own list (#28). The cheap single plate stays the fallback if
   the hob interface (COK-023) fails on this model (domino + plate, same width).
2. **The serving hatch moves onto the well-lid bench.** The bench (540 × 460 = 0.25 m²) sits at the front of the
   well column; a motorised sliding glass door in front of it opens for serving and dish return. This frees the
   front of the S column for the **thermo-cooker** (or, if R1 fails, for K9c's hub).
3. **The board lives on a passive turntable carrier** (ware, separable pivot), placed on a cold hob zone during
   prep or on the bench; nothing on the deck is reserved for it.

Result: S column 580 + hob 600 + well column 560 + end wall 10 = **1,750 mm**; whole machine **3,600 mm**. The
price of change 2 is that the bench is time-shared (prep, plating, hatch, dish return, well lid); the rules are in
§1.7, and SRV-014 becomes marginal (§4). Rejected alternatives: the cooker on a shelf above the bench or the
rinse cup (it blocks the hand's vertical access to the well or the rinse cup), and the hatch drawer at z ≈ 1,200
above the deck (it shadows whatever stands below it).

### 1.2 Widths and heights

| Module | Machine X | Width | Content |
|---|---|---|---|
| Freezer | 0–600 | 600 | Bosch GIN81ACE0 178 cm built-in NoFrost (559 wide), on a 120 mm plinth to z ≈ 1,892; top wall opened (A: C1-B window, B: four sub-lids) |
| Fridge | 600–1200 | 600 | Bosch KIR81AFE0 178 cm built-in larder fridge, same plinth and top |
| Ambient | 1200–1850 | 650 | A: S4 aisle shuttle (two rack faces × 3 lanes, nest level, cool section) z 80–2000; B: S1 3 × 3 top-dug stacks |
| Cell: S column | 1850–2430 | 580 | rinse cup, chute + blade post, thermo-cooker in a drained pocket; box shelf (3 carriers) z 1550, lid station z 1750–1950 |
| Cell: hob column | 2430–3030 | 600 | 60 cm 4-zone hob; tool cabinet above X 2440–2780; oven-door corridor X 2780–3030 |
| Cell: well column | 3030–3590 | 560 | donor slim dishwasher as the well (z 100–870), lid-bench = hatch (z 870), oven z 1550–1855 |
| End wall | 3590–3600 | 10 | stainless lower / HPL upper panel |
| **Total** | | **3,600** | PHY-004 (M) met with 0 mm spare; E1 must confirm every appliance and the hob cut-out [U] |

Heights: plinth 0–120 (cold) / 0–100 (cell); deck z 870; cell ceiling z 2000; **gallery z 2000–2200** over all
modules, with the shared beam on the rear wall at z 2080–2160. Depth 600: mast lane y 0–120, guard y 580–600.

### 1.3 Whole machine, front view (fronts and doors removed) and top view

Scale ≈ 40 mm per character. (A) = option A only.

```
z 2200 +==============+==============+===============+==============+==============+=============+
       | SHARED BEAM X 0-3600 on the rear wall (y 0-40, z 2080-2160): 2 x MGN15 + one static belt|
       | STORAGE CARRIAGE: hoist X 250-2350, fixed arm to pick line y 290 | CELL CARRIAGE: mast  |
       | (boxes carried at z 2000-2200 over the module tops)               | X 1880-3560 via slot|
  2000 +=[THROAT 300]=+=[THROAT 900]=+=[ROOF HATCH]==+=[PORT+FLAP]==+=ceiling+slot=+=ceiling=====+
       |exit plate,   |exit plate,   |S4 carriage    |LID STATION   |TOOL CABINET  |  OVEN 25 L  |
       |slide + motor,|slide + motor,|hand-over,     |z 1750-1950,  |X 2440-2780,  |  turned,    |
  1890 |CoreXY (A)    |CoreXY (A)    |lid z 1941     |vacuum cup    |z 1550-1950;  |  mouth -X,  |
       |------------- |------------- |FRONT FACE     |BOX SHELF     |X 2780-3030:  | z 1550-1855,|
       |robot zone    |robot zone    |3 lanes:       |z 1550:       |oven-door     | X 3080-3440,|
       |350 (A)       |350 (A)       | 7 x S (65)    |3 carriers    |corridor      |  y 120-570  |
  1550 |------------- |------------- | 4 x M (100)   |------------- |------------- |-------------|
       |FREEZER       |FRIDGE        | 5 x T (150)   |arm space     |arm space     |arm space    |
       |Bosch         |Bosch         |REAR FACE:     |roll axis     |roll axis     |roll axis    |
       |GIN81ACE0     |KIR81AFE0     | 5 M, 3 S,     |<= 1240       |<= 1240       |<= 1240      |
       |212 L NoFrost |319 L larder  | nest level    |              |              |HATCH DOOR   |
       |S1 2x2 stacks |S1 2x2 stacks | (<=37 empty)  |cooker top    |pots with     |z 880-1250   |
       |cap 9: ~24    |~38-45 [U]    | cool 3 x T    |~z 1050       |stub <= 1100  |2 plates out |
   870 |              |              |  (if kept)    |RC|CH|COOKER  |=4-ZONE HOB== |=BENCH=LID== |
       |              |              |               |bin |cooker   |hob body,     |WELL: donor  |
       |              |              |               |20 L|pocket   |5 L boiler,   |slim DW 448, |
       |              |              |               |    |200 deep |controls,     |tub cut open |
       |              |              |               |drains,       |power mgr,    |z 100-870    |
   120 |plinth, vent  |plinth, vent  |drip tray      |valves        |extract fan   |DW pumps     |
     0 +--------------+--------------+---------------+--------------+--------------+-------------+
      X 0            600           1200            1850           2430           3030          3600
          FREEZER 600    FRIDGE 600     AMBIENT 650     S COLUMN 580   HOB 600        WELL 560 (+10)
```

Top view: storage at the level of the module tops (z ≈ 1,950), cell at deck level (z 870).

```
 y 600 +OEM door======+OEM door======+human door=====+glass panel===+glass panel===+HATCH DOOR===+
   580 |              |              |FRONT FACE     |chute |       |FL210   FR180 |2 plates O270|
       |  2 x 2       |  2 x 2       |3 lanes x 16   |120 x | COOK  |(L1)    (L2)  |on the BENCH |
   420 | stacks of    | stacks of    |levels         |200   | -ER   |2 x 3.7 kW    |540 x 460    |
       | GN 1/6       | GN 1/6       |-------------  |flap  | 340   |boost         |= well lid   |
   290 |.[throat].... |.[throat].... |..[carriage]...|.carriers.....|..............|.............|
       |  (C1 middle  |              |AISLE 188      |RC    | spit  |RL145   RR180 |2 bench trays|
       |   band)      |              |-------------  |O 150 | rest  |              |oven above   |
   120 |              |              |REAR FACE      |      |       |fume slot     |(mast behind)|
       |  beam + carriages y 0-110 (gallery z 2000-2200) over all modules; cell mast lane y 0-120|
   y 0 +--------------+--------------+---------------+--------------+--------------+-------------+
      X 0            600           1200            1850           2430           3030          3600
        pick line y = 290 (dots): throats X ~300 / ~900, S4 roof hatch X ~1525, box shelf X 1860-2430
```

### 1.4 The cell in detail (≈ 20 mm per character)

Front view, guard removed (machine X):

```
z 2200 +===========+==================+=================+============+===========================+
       | gallery: storage carriage arm over the PORT; cell carriage on the same beam             |
  2000 +=[PORT+FLAP+=X 1860-2430======+==slot (y 50-120)+============+=ceiling===================+
  1950 |lid        |LID STATION:      |TOOL CABINET     |oven-door   |OVEN 25 L countertop       |
       |magazine   |vacuum cup on     |IKEA carcass +   |corridor    |convection, turned 90 deg, |
       |(26 lids)  |lead screw        |stainless liner, |(door drops |mouth -X, hook-rod door,   |
  1750 |---------- |----------------- |3 tool racks,    |to horiz.   |SSR + K thermocouple;      |
       |red        |BOX SHELF:        |spring flaps to  |at z 1560)  |GN 1/2 trays, plate        |
       |carrier    |2 green stub      |the mast lane,   |            |warming when free          |
  1550 |========== |carriers========= |soffit -> gutter |------------|===========================|
       |           |                  |                 |            |arm passes under the oven, |
       |sleeve     |COOKER: jug lift  |pots on the      |            |roll axis <= 1240          |
       |rinse,     |150 under shelf   |front zones,     |            |HATCH DOOR (NEMA 17 belt)  |
  1250 |pouring    |(roll <= 1240)    |pans on rear     |            |opening X 3040-3580,       |
       |           |                  |zones (height    |            |z 880-1250; slides left    |
       |           |lid top ~1050     |rule K9b 2.3)    |            |in front of the hob        |
   870 |[RC][CH]   |[COOKER in pocket]|[== 60 cm 4-zone |induction=] |[BENCH = WELL LID 540x460 ]|
       |bin 20 L   |cooker base on a  |hob body (55)    |power mgr,  |WELL = donor slim DW 448 x |
       |pull-out   |drained pocket    |5 L boiler 85 C, |relays, PSUs|550: tub cut to a 400 x 440|
       |drains,    |200 deep (z 670), |controls box     |extract fan |mouth, collar, fork combs, |
       |valves     |splash hood       |(Pi 5, Octopus)  |+ filter    |fan-nozzle rows; DW door = |
   100 |           |                  |                 |            |service door to the filter |
     0 +-----------+------------------+-----------------+------------+---------------------------+
     1850        2070               2430              2780         3030                        3600
```

Top view at deck level (z 870); the box shelf (z 1550) lies over the S column, the tool cabinet over the hob's left
half, the oven over the bench:

```
 y 600 +glass======+sliding glass=====+fixed glass======+============+HATCH DOOR slides left=====+
   580 |           |COOKER 340 x 340  |FL zone O 210    |FR O 180    |plate 1     plate 2        |
       |CHUTE      |MC Smart in a     |3.7 kW boost     |3.1 kW      |O 270       O 270          |
   500 |120 x 200  |drained pocket    |(phase L1)       |(L2)        |(served and returned here) |
       |spring flap|under a splash    |                 |            |BENCH 540 x 460 (0.25 m2)  |
   420 |to the bin |hood; lid clamped |board on a       |            |= well lid, front hinge,   |
       |           |by the base       |turntable (prep, |            |gas strut, 150 W heater    |
   330 |blade post |jug handle stub -y|hob cold)        |            |2 bench trays 265 x 420    |
       |---------- |                  |                 |            |(ware, exchanged)          |
   240 |RINSE CUP  |spit rest,        |RL zone O 145    |RR O 180    |well mouth 400 x 440       |
       |O 150,     |stab nest         |2.2 kW           |3.1 kW      |below the bench            |
   130 |4 jets 85C |                  |                 |            |oven above (z 1550)        |
   120 | mast lane y 0-120: mast X 1880-3560 | fume slot behind the hob | rear liner + gutter    |
   y 0 +-----------+------------------+-----------------+------------+---------------------------+
     1850        2070               2430              2780         3030                        3600
```

Hob zone sizes and powers are those of a typical 7.4 kW 60 cm hob [U: final model, E1]. Height rule as K9b §2.3:
rear zones take low vessels (pans, ≤ 80 mm), front zones take pots, so the hand reaches every stub from behind.

### 1.5 The shared rail and the two carriages

* **Beam**: one aluminium 40 × 80 profile on edge, X 0–3,600, on wall brackets every ≈ 600 mm (y 0–40,
  z 2080–2160); **two MGN15 rails** on its front face; **one static HTD 3M-15 steel-cord belt** clamped at both
  ends. Each carriage carries its own NEMA 23 with an omega pulley set (drive pulley between two idlers), so one
  belt serves two independent carriages. Butt joints of the rails at module boundaries are aligned on a jig [U: K1].
* **Cell carriage** (4 blocks): the mast (60 × 120) hangs through a labyrinth slot in the cell ceiling (y 50–120);
  the extraction keeps the cell below the gallery pressure, so air flows into the cell, never out (K9c M1.6). Mast
  X 1880–3560; Z SFU1610, arm z 1000–1900 (roll axis 700–1600); Y 450 (wrist y 130–580); canned roll unit on a
  300 mm drop link. Limits as K9c: lift ≤ 6 kg at ≤ 160 mm, roll 10 Nm, push 300 N within y ≤ 420 and 150 N at full
  reach, 0.8 m/s. The mast is ≈ 150 mm longer than in K9c because the beam sits in the gallery (K1 rig checks it).
* **Storage carriage** (4 blocks): a fixed arm reaching forward to the pick line y 290 at z 2120–2180; at its tip
  the **hoist** (NEMA 23 with 2 Nm brake, spool, Dyneema line, stroke ≥ 450 mm) and the storage round's **passive
  toggle gripper**; an NFC reader in the gripper frame. Hoist X 250–2350. **Option B** adds a short Y slide
  (MGN12 + NEMA 17, y 160–440) to reach all stacks, and a small servo with a hook that lifts the sub-lids.
* **Zoning**: the two carriages overlap only over the box shelf (X 1880–2350). The controller admits one carriage
  at a time; a limit switch on each carriage that stops both drives is the second channel. The box shelf's three
  carriers decouple them (TRN-008).
* **Gallery**: the ceiling of every module is the gallery floor; ports are the two cold exits, the S4 roof hatch
  and the cell's box-shaft port (spring flap pushed open by the descending gripper). Boxes up to T height plus
  gripper travel at z 2005–2200 (storage round K-8) [U: E1 height budget].

### 1.6 Actuators and dynamic seals

| # | Actuator | Part [source] | Where | Seal |
|---|---|---|---|---|
| 1 | Cell X | NEMA 23 3 Nm, omega drive on the static belt [P4] | beam | none (labyrinth slot) |
| 2 | Z | SFU1610 + NEMA 23 with 2 Nm brake [P5, P7] | mast | **band 1** (stainless strip) |
| 3 | Y | NEMA 17, MGN12, belt in the 60 × 60 arm tube [K9c G8] | arm | **band 2** |
| 4 | Roll | NEMA 23 + 20 : 1 planetary, canned magnet coupling [K9c R1–R4] | arm tip | none (canned) |
| 5 | Hatch door | NEMA 17 + GT2 belt, current-limited, soft edge [E] | guard | outside the food zone |
| 6 | Storage X | NEMA 23, omega drive on the same belt | beam | none |
| 7 | Hoist | NEMA 23 with brake, spool, Dyneema | storage carriage | none |
| 8 | Lid station | NEMA 17 lead screw lifting a vacuum cup | box shaft | none |
| **A** 9–11 | S4: Z, X, J-hook Y | NEMA 23 + brake on the cross shaft; 2 × NEMA 17 | ambient aisle | none |
| **A** 12–14 | Fridge robot: CoreXY × 2 (outside), hoist (inside) | NEMA 17 | fridge top / inside | **2 PTFE shaft bushings** in the exit plate |
| **A** 15–17 | Freezer robot: same, hoist cold-rated | NEMA 17, −40 °C grease | freezer | **2 PTFE shaft bushings** |
| **A** 18–19 | C1-B exit slides | 12 V gear motor each | fridge, freezer tops | static magnetic gaskets |
| **A** 20 | Cool-section roller shutter (only if CAP-024 is kept) | gear motor | S4 rear face | static |
| **B** 9 | Storage Y | NEMA 17 + MGN12 | storage carriage | none |
| **B** 10 | Sub-lid lifter | hobby servo with hook | storage carriage | none |

**Cell: 5 motion actuators, 2 dynamic seals** (K9c 6 and 2; the cooker's own motor, the hob, oven, dishwasher pumps,
boiler, 4 solenoid valves and the extraction fan are not counted). **Storage A: +15 motors, +4 bushings; storage B:
+5 motors, 0 seals.** If R1 fails, the hub adds T and S (7 in the cell, as K9c).

### 1.7 Stations

| Station | Where (machine X; y; z) | What it is | Food contact |
|---|---|---|---|
| Rinse cup | 1870–2020; y 140–290 | bar-sink bowl Ø 150 with 2 mm basket strainer; spout cold / 45 °C / 85 °C (boiler) with flow meter; 4 fan jets 85 °C for the sleeve (**20 s after a class-R grip**, 3–10 s otherwise); cooking water poured here | strainer (ware) |
| Chute + blade post | 1880–2000; y 330–530 | 120 × 200 opening with spring flap to a 20 L bin pull-out; blade post (shoes 1 / 2.5 / 5 mm, rasp edge) on its rear rim: peeling and slicing on the fork-spit (K9b N2) | blade post (ware) |
| Thermo-cooker | 2080–2420; y 240–580 | MC Smart in a drained 200 mm pocket (top ≈ z 1,050), splash hood over the base with only the jug exposed, silicone base sleeve; jug handle stub to −y; stainless funnel in the lid opening; two jugs alternate (§6) | jug, blade, lid (ware) |
| Spit rest | 2080–2420; y 130–230 | silicone-lined stab nest for the fork-spit, cooker cable duct | no |
| Hob | 2440–3030; y 58–580 | 60 cm 4-zone induction, 2 × 3.7 kW, UI board replaced by the interface; boards on turntable carriers on cold zones during prep | glass under ware |
| Bench = hatch = well lid | 3040–3580; y 120–580; z 870 | 540 × 460 insulated lid, front hinge, gas strut; 150 W heater mat (warm-hold, plates 40–60 °C); **two removable bench trays** 265 × 420 (ware); motorised sliding glass door in front (opening z 880–1250) | trays (ware) |
| Well | 3060–3540 under the bench | donor slim dishwasher, tub cut to a 400 × 440 mouth with collar; fork combs at z 700 / 800; fan-nozzle rows; final rinse ≥ 82 °C for 60 s heated by the donor's own heater; donor door = service door to its filter | — |
| Oven | 3080–3440; y 120–570; z 1550–1855 | 20–25 L countertop convection oven ≤ 450 mm along y, turned (mouth −X), door opened by the hook rod and dropped onto the corridor over the hob's right half; GN 1/2 trays | ware only |
| Box shelf | 1860–2430; y 200–525; z 1550 | three permanent stub carriers (green, green, red) with shelf-opened spring hooks (storage round §5.3) under the ceiling port | no |
| Lid station | 1860–2430; z 1750–1950 | vacuum cup on a lead screw takes the lid off a box held by the gripper; lid magazine for ≈ 26 lids | no |
| Tool cabinet | 2440–2780; y 120–580; z 1550–1950 | IKEA wall carcass with stainless tray liner, three tool racks, rear spring flaps to the mast lane, insulated soffit sloped to the rear gutter (it is over the hob: Zone S, rinsed by the nozzle rail) | no |
| Splash cleaning | back liner, sides, deck, soffits | fixed nozzle rail (85 °C from the boiler, detergent by venturi), deck sloped to the rinse cup; fume slot behind the hob to the extractor | — |
| Camera | ceiling, rear | one wide camera, heated window, white + UV-A LEDs (K9c C6) | — |

**Bench rules** (the price of 1.1-2):
* B-1: food never touches the bench top: raw items stand only in GN on a bench tray; a tray that carried raw GN goes
  to the well before plating.
* B-2: the well lid opens only with the bench cleared; while it is open (≤ 5 min per load change) the hatch shows
  "busy".
* B-3: serving: two plates at the bench front, door opens, the diner takes them; repeated for persons 3–4.
* B-4: return: before the door opens for return, the hand sets a plate carrier and the glass/cutlery basket on the
  bench; after the return the door closes; the carriers wait there until the running well load ends, then are
  parked on the cold hob while the lid opens and the well is loaded.
* B-5: the heater mat runs only for warm-holding and plate warming, never during prep.

### 1.8 Household appliances (models and prices)

| Appliance | Model (example) | € | Source | How it is used |
|---|---|---|---|---|
| Induction hob 60 cm, 4 zones, **7.4 kW** | Bosch Serie 4 PIE631BB5E | 436 | [W1] | as bought, UI board replaced by the interface board (COK-023, #5). The €256 PUE611BB5E has only 4.6 kW in total [W1] and loses the double boost |
| Thermo-cooker | Lidl Monsieur Cuisine Smart (removable, dishwasher-safe lid with seal and measuring cup [W2]) | 399 | Q1 [W] | gated by R1; alternative Cecotec Mambo 11090 €219 (Q2), whose lid is hinged to the base and never reaches the well (C6 §2.1) |
| Countertop convection oven 20–25 L, ≤ 450 mm along y | Severin / Stillstern class | 100 | Q3 [W] €70–126 | turned, hook-rod door, SSR + thermocouple, own thermostat as limiter (#24) |
| Slim 45 cm dishwasher (well donor) | Exquisit GSP9109-030E / Bomann GSP 7418 class | 300 | P13 [W] €269–349 | tub cut open; pumps, heater, softener, dosing re-used |
| Under-sink boiler 5 L, 85 °C | Stiebel Eltron SNU 5 SL | 150 | Q5 [W] | spout, sleeve jets, nozzle rail; off when idle |
| Hob extractor fan with baffle filter | — | 150 | K9b [D] | rear fume slot, cell under-pressure |
| Fridge 178 cm built-in, larder (no ice box) | Bosch Serie 6 KIR81AFE0, 319 L | 788 | [W3] | top wall opened (option A or B) |
| Freezer 178 cm built-in, NoFrost | Bosch Serie 6 GIN81ACE0, 212 L, 235 kWh/a | 920 | [W4] | same |
| **Appliances** | | **3,243** | | (Ben's list: hob 500 + oven 500 + fridge/freezer 1,000 + dishwasher 500 = 2,500, plus shelving) |

### 1.9 Phase plan (#1)

| Phase | Loads | ≤ kW |
|---|---|---|
| L1 | hob left pair (front boost 3.7); controls 0.2 | 3.9 |
| L2 | hob right pair 3.7; while the cooker heats (≈ 1 kW [U: model]) the right pair is limited to ≈ 2.7 | 3.7 |
| L3 | oven 2.0 **or** well heater 2.0 **or** boiler 2.0 (one at a time); extraction 0.1; gantry 0.3 | 2.4 |
| **Peak** | (fridge and freezer stay on their own household sockets) | **≈ 10.0** of 11 kW |

COK-002: 4 hob zones + cooker = 5 simultaneously heated positions, two of them ≥ 3 kW (one per phase), plus the
oven and the heated bench for warm-holding at the same time ✓. COK-004: 4 L from 15 to 95 °C on a 3.7 kW zone
≈ 1.34 MJ / (3.7 kW × 0.85) ≈ 7.1 min ≤ 11 ✓ [C], with the oven heating on L3; from the 85 °C boiler < 1 min.

### 1.10 Ware list

B = bought, B+ = bought with a folded riveted stub (K10 WA1), C = custom job-shop part. Changes against K9b §2.10 in
the last column.

| Group | Items | Pieces | Change against K9b |
|---|---|---|---|
| Pots, pans, lids | frying pans Ø 280 tri-ply ×2 (hook tab, flip partners) B+; pot 5 L with basket B+; pot 3 L B+; pot 1.5 L B+; braiser Ø 280 5.5 L B+; lids Ø 280 / 220 / 160 and strainer lid Ø 220 B+; lift-rack pair Ø 260 C; red wash pot Ø 220 with dunk basket B+ | 14 | kneading bowl and dog rings deleted |
| GN, oven, serving | GN 1/2-20 ×2 (pizza, sheets); GN 1/2-65 + lid (lasagne, gratin, roast); GN 1/3-65 ×3 with lids (breading line, mise en place, serving); loaf tin 25 cm; springform 24 | 10 | GN 2/3 → GN 1/2 (25 L oven) |
| Boards and cutting | PE-HD boards Ø 300 red / green on two turntable carriers C; chef's knife red / green; scalloped slicer; blade post C; fork-spit; corer shank with tubes Ø 14 / 22 / 42; plunger pitter | 11 | turntable instead of the T carrier |
| Cooker ware | jug with blade ×2 (one spare, used alternately), lid with seal, measuring cup + stainless funnel, steamer (2 levels), whisk insert, spatula; clamp-on stubs on jug handle and lid | 9 | replaces press cup, S ware, kneading roller, hung scraper |
| Gadgets (gated by HYG-027) | ricer / Spätzle press (WMF), unpeeled-garlic press (Rösle) on a press stand C (set on the bench); push dicer only if B6 needs it | 3 | replace press cup grids and ricer die |
| Stem tools | spatula-tongs red / green (pincer); turner red / green; ladle; silicone spatula red / green; balloon whisk; measuring spoons; disher; probe holder; rolling pin with gauge rings; Spätzle slider; plate cradle; hook rod; scraper-squeegee | 18 | + red turner and red spatula (raw → cooked without re-washing, CAP-030) |
| Fixtures | egg fixture (loose, set on the bench); Rouladen cradle + 2 raft forks; carving trough with gauge; ravioli plate GN 1/2; dumpling press; rinse-cup strainer; fat cup | 9 | egg fixture loose |
| **Food contact** | | **74** | K9b 77 |
| Carriers (no food contact) | plate carriers ×2; glass and cutlery baskets (from the donor); bench trays ×4; tool racks ×3; stub carriers ×3 (green, green, red); spinner basket for the roll axis | 15 | + bench trays, stub carriers |

A 4-person meal takes out ≈ 25–35 items, a 2-person meal ≈ 15–25 (K9b). Dishes: the household's own plates,
bowls, glasses and cutlery (CAP-031, §4).

---

## 2. Storage: what one manipulator can do, and the two options for Ben

### 2.1 Where the storage carriage can replace dedicated robots, and where it cannot

The storage round used five moving systems: the gallery (X + hoist), S4's carriage (3 motors), and one S1 robot
in each cold shell (3 motors each). K10-W2 replaced all of them by one carriage digging from the top. Job by job
[C/E; per-move times from the storage round and C6 §5.2]:

| Job | Storage round | One storage carriage on the shared beam? | Requirement that decides | K11 |
|---|---|---|---|---|
| Transport between modules, to the cell's box shelf, ingestion hand-over, drinks to the cell | gallery X axis + hoist (≈ €500, not costed there) | **Yes.** Freezer → box shelf ≈ 1.9 m ≈ 4–6 s at 0.8 m/s; no Y needed on the pick line | TRN-005 (≤ 20 s, mean ≤ 10 s) ✓; TRN-008 via 3 carriers and the port stacks ✓ | both options |
| Lid off / on | gallery at the lid station | **Yes** (the station holds the cup, the carriage moves the box) | — | both |
| Ambient random access: 30 retrievals a day, 5–8 seasonings per meal, spontaneous meals | S4's own XZ carriage in a 188 mm aisle | **No.** S4 pulls boxes sideways out of two rack faces down to z 80. A rope hoist cannot take the J-hook's side load, and a rigid 1.9 m Z does not fit under a 200 mm gallery. Digging from the top (S1) costs 72 s worst / ≈ 36 s random with S1's own robot, ≈ 60–120 s with the gallery carriage (slower hoist, longer stroke) | **STO-003** (≤ 30 s, mean ≤ 15 s) | A keeps S4; B digs (waiver) |
| Fridge: 25 retrievals a day, mostly menu boxes (#17) | S1 robot inside, C1-B window (3.4 s open) | **No.** From outside, the carriage can dig only through the top. With one full-top lid the lid stays open for the whole dig (≈ 1 min for 4 boxes): CLD-004 fails. With **four sub-lids** (one per stack, each open only while the hoist passes, ≈ 6–8 s) CLD-004 holds per passage, but every box moved aside costs ≈ 10–12 s: 4 boxes above ≈ 60 s, 10 above ≈ 2 min | **CLD-006** (≤ 45 s); CLD-004 ✓ only with sub-lids | A keeps the robot; B uses sub-lids (waiver on CLD-006) |
| Freezer: 5 retrievals a day | S1 robot inside (cold-rated hoist), stacks capped at 9 | Technically **no** (as the fridge). In practice frozen boxes are almost always taken out hours ahead for controlled thawing (CLD-013), so unplanned frozen retrievals are rare | CLD-006 | the best place for a waiver (hybrid, §2.4) |
| Night-time re-sorting by menu and use frequency | the robots, hatch closed | **Yes**: the storage carriage is idle most of the day | — | B relies on it |
| Storage duty on the **cell hand** (K10-W1) | — | **No**: 122–140 cm cold shells fail CAP-021, storage moves cost 15–20 min of hand time per meal, one carriage for everything (C6 §4.4) | CAP-021, PERF-002 | rejected |

**Rule for K11:** one manipulator (the second carriage on the cell's beam) replaces the gallery and every
hand-over. It cannot replace random access inside a store without failing STO-003 (ambient) or CLD-006 (cold).
CLD-004 can be kept without in-shell robots by giving every stack its own sub-lid.

### 2.2 Option A — compliant

* **Ambient**: S4 aisle shuttle with the S5-B nest level and the thermoelectric cool section (CAP-024), as the
  storage round, built with K9c's maker-market parts (NEMA 23 + brake on the Z cross shaft instead of a 200 W
  servo, open-loop NEMA 17 for X and the J-hook, an AS5600 encoder plus homing instead of a magnetic tape, the
  gripper's NFC reader instead of S4's own). 72 lidded (30 S, 27 M, 15 T) + 9 cool + ≤ 37 nested empties.
* **Fridge and freezer**: C1-B top-wall windows (throat 210 × 200, spring-closed slide, magnetic gasket, open
  ≈ 3.4 s per passage; freezer with skirt and heated seat) and lean S1 robots inside (CoreXY motors outside,
  shafts through PTFE bushings, NEMA 17 hoist inside, cold-rated in the freezer, passive toggle gripper).
  Fridge ≈ 38–45 usable [U: E1 interior], freezer ≈ 24 (stacks capped at 9).
* **Storage carriage**: X + hoist, no Y; lid station; three stub carriers.
* **Retrieval**: ambient worst 6 s, mean 4 s; cold planned ≈ 6 s, unplanned ≤ 45 s for the top 8 boxes of every
  stack and for every freezer box; gallery ≈ 10 s per box overlapped with cooking (storage round §6.3).
* **The one gap the storage round already put to Ben (Q2)**: an unplanned chilled box near the bottom of a full
  fridge stack takes ≈ 60–70 s (CLD-006 ≤ 45 s). Option A is compliant on the storage round's reading (chilled
  boxes are menu boxes, pre-dug overnight). A fix worth one rig test: a **sub-stack lift** (the gripper's hooks
  reach down the 12 mm stack gaps and lift the target's upper neighbours as one block of ≤ 3 boxes and ≤ 12 kg
  onto another stack at ≤ 0.2 m/s²), which would cut a 10-box dig to ≈ 4 moves ≈ 40 s [E/U].
* **Cost**: machine part **€3,430**, structure **€1,250** (§3.4). Motors in storage: 15.

### 2.3 Option B — cheap (needs Ben's waiver on retrieval times)

* **Ambient**: S1 3 × 3 stacks of lidded GN 1/6 / 1/9 in the 650 column, full height, dug from the top by the
  storage carriage through a spring-closed roof hatch (lifted by the carriage's servo hook); one stack of nested
  empties (CAP-023). No in-column robot zone is needed (the hoist comes from above): ≈ 120 usable positions [E]
  (S1 113 with its own 350 mm robot zone).
* **Fridge and freezer**: the top wall gets a stainless exit plate with **four windows ≈ 200 × 190, one over each
  stack**, each closed by an insulated 40 mm sub-lid on a magnetic gasket, spring-closed; the carriage's servo
  hook lifts one sub-lid at a time and only while the hoist passes (≈ 6–8 s, CLD-004 ✓); in the freezer each seat
  has a 100 mm skirt and a dew-point-controlled 3 W heater. Full-height stacks: fridge 14 levels × 4 − 8 dig
  reserve ≈ **48**, freezer 12 × 4 − 8 ≈ **40** [E on the storage round's interiors, U].
* **Storage carriage**: X, Y, hoist, sub-lid servo; it re-sorts all stores at night from the menu plan and the
  use frequency (frequent boxes on top, R boxes on their own stacks, never above RTE).
* **Retrieval** [E]: top box ≈ 15–18 s; each box above +10–12 s; random mean ≈ 50–70 s; deepest ≈ 2–2.5 min;
  menu-planned ≈ 15–20 s.
* **What is lost**: STO-003 and CLD-006 for unplanned boxes; the cool zone CAP-024 (no place for it: waiver, as the
  storage round recommended anyway); spontaneous 4-person meals start 5–15 min later (≈ 20 random digs before
  cooking); drink pouring from a deep carton waits ≈ 1–2 min (SRV-024, S); four windows make the top cut almost a
  full-top cut (CLD-007, S: hidden lines, R600a) — a cut test on a used unit is mandatory; the freezer seats add
  ≈ 0.05–0.1 kWh/day (RES-004 becomes marginal); one carriage serves all storage (a fault stops storage; the human
  still has every OEM door).
* **What is gained**: more positions (≈ 120 / 48 / 40), 10 motors and 4 bushings fewer, **machine part €1,735,
  structure €850** — ≈ €1.7 k machine part and ≈ €0.4 k structure less than A.

### 2.4 The options side by side

| | **A compliant** | **B cheap** | Hybrid A/B (for information) |
|---|---|---|---|
| Ambient | S4, 72 + 9 cool + ≤ 37 nested | S1 top-dug, ≈ 120 incl. a nest stack | S4 as A |
| Fridge / freezer positions | 38–45 [U] / 24 | ≈ 48 / ≈ 40 | ≈ 48 / ≈ 40 (as B) |
| Retrieval, unplanned | 4–6 s ambient; ≤ 45 s cold except deep chilled 60–70 s | 50–70 s mean, ≤ 2.5 min | ambient 4–6 s; cold as B |
| Retrieval, planned | 2–6 s | 15–20 s | 4–6 s / 15–20 s |
| Cold exit open per passage | 3.4 s | 6–8 s | 6–8 s |
| Motors in storage | 15 | 5 | 8 |
| Machine part / structure | **€3,430 / €1,250** | **€1,735 / €850** | ≈ €2,600 / €1,200 |
| Storage Musts needing a waiver | CLD-006 for deep chilled boxes, unplanned (storage round Q2); CAP-021 depends on E1 | STO-003, CLD-006 (unplanned), CAP-024 | CLD-006 (unplanned cold), CAP-024 if the cool section is dropped |

---

## 3. Bill of materials (one unit, EU retail / job shop incl. VAT, own labour not counted)

### 3.1 Prices checked for K11 (2026-10-01); all other prices are K9c P1–P27 and K10 Q1–Q11

| # | Item | Price found | Source |
|---|---|---|---|
| W1 | 60 cm induction hob, 4 zones, **7.4 kW**, Bosch Serie 4 PIE631BB5E; for comparison PUE611BB5E (4 zones, **4.6 kW total**: Ø 21 2.2/3.7, 2 × Ø 18 1.8/3.1, Ø 14.5 1.4/2.2 kW) | from €435.68; PUE611BB5E from €251.62–256.15 | Kaufland: <https://www.kaufland.de/product/503290521/>; Geizhals: <https://geizhals.de/bosch-serie-4-pue611bb5e-induktionskochfeld-autark-a2879087.html> |
| W2 | Monsieur Cuisine Smart lid for the jug with seal and measuring cup, sold as a spare part, dishwasher-safe | (spare part) | <https://shop.monsieur-cuisine.com/de/monsieur-cuisine-smart/315-deckel-fuer-den-mixbehaelter-inkl-dichtungsring-und-messbecher.html> |
| W3 | 178 cm built-in fridge without ice box, Bosch Serie 6 KIR81AFE0 (319 L) | from €787.50 | Geizhals: <https://geizhals.at/bosch-serie-6-kir81afe0-a2350942.html> |
| W4 | 178 cm built-in NoFrost freezer, Bosch Serie 6 GIN81ACE0 (212 L, 235 kWh/a) | from €919.99 | Geizhals: <https://geizhals.de/bosch-serie-6-gin81ace0-a3086208.html> |
| W5 | GN 1/6-100 container in PP; GN 1/6 PP lid with silicone seal | from €2.35 (€4.35 typical); lid €5.19 | <https://www.gastro-billig.com/kuechenbedarf/gn-behaelter-zubehoer/gn-behaelter/gn-behaelter-kunststoff/gn-behaelter-aus-polypropylen/gn-behaelter-polypropylen-gn-1/6-100-mm-1-5-liter-transparent-6350>; search summary of GastroHero / gastro-michel listings |

Findings: the two 178 cm built-in cold appliances cost **€1,708** together (Ben assumed ≈ €1,000; the storage
round €1,700–2,800); a 7.4 kW 4-zone hob costs €436, close to Ben's €500; a gasketed GN 1/6 box with tags costs
≈ €10.

### 3.2 Household appliances and shelving (Ben's "€3,000–3,500" list)

| # | Item | A € | B € | Source |
|---|---|---|---|---|
| AP1 | Induction hob 60 cm, 4 zones, 7.4 kW (Bosch PIE631BB5E) | 436 | 436 | W1 |
| AP2 | Thermo-cooker Monsieur Cuisine Smart (gated by R1) | 399 | 399 | K10 Q1 |
| AP3 | Countertop convection oven 20–25 L, ≤ 450 mm along y | 100 | 100 | K10 Q3 (€70–126) |
| AP4 | Slim 45 cm dishwasher as the well donor | 300 | 300 | K9c P13 (€269–349) |
| AP5 | Under-sink boiler 5 L, 85 °C (Stiebel Eltron SNU 5 SL) | 150 | 150 | K10 Q5 |
| AP6 | Hob extractor fan with baffle filter | 150 | 150 | K9b [D] |
| AP7 | Fridge 178 cm built-in larder (Bosch KIR81AFE0) | 788 | 788 | W3 |
| AP8 | Freezer 178 cm built-in NoFrost (Bosch GIN81ACE0) | 920 | 920 | W4 |
| | **Appliances** | **3,243** | **3,243** | |
| SH1 | Storage structure: A = S4 rack and enclosure 850 + cool-section insulation 100 + cold posts and grates 2 × 150; B = S1 ambient stack grid and carcass 600 + cold stack guides 2 × 125 | 1,250 | 850 | storage round §4.5 [D]; K10 S7 / C6 §6.1 |
| SH2 | Kitchen furniture equivalent in the cell: Gastro work table 1700 × 600 (190), tool-cabinet carcass (120), under-deck fronts (80), bin pull-out (30) | 420 | 420 | K9c e2 |
| | **Appliances and shelving** | **4,913** | **4,513** | |

### 3.3 Machine part — the cell (identical in A and B)

| # | Item | Qty | € | Cat. | Source |
|---|---|---|---|---|---|
| H1 | X beam 40 × 80, cell share 1.75 m | 1 | 35 | b | K9c P1 |
| H2 | MGN15 rails, cell share 2 × 1.75 m, 4 blocks | 1 | 140 | b | K9c G2 / P2 |
| H3 | Static HTD 3M-15 belt (cell share), omega pulley set, idlers, tensioner | 1 | 50 | b | K9c P3 |
| H4 | X motor NEMA 23 3 Nm | 1 | 25 | b | K9c P4 |
| H5 | Z ball screw SFU1610 set | 1 | 60 | b | K9c P7 |
| H6 | Z motor NEMA 23 with 2 Nm brake | 1 | 45 | b | K9c P5 |
| H7 | Mast 40 × 80 × 1.25 m, MGN15 1 m, bent stainless cover (+150 mm against K9c) | 1 | 80 | b, job | K9c G7 + [E] |
| H8 | Y: NEMA 17, MGN12 0.6 m, belt | 1 | 60 | b | K9c G8 |
| H9 | Arm tube stainless 60 × 60 × 620 | 1 | 40 | job | K9c G9 |
| H10 | Sealing bands (Z, Y) | 2 | 50 | b | K9c G10 |
| H11 | Labyrinth lips in the ceiling slot | 1 | 25 | job | K9c G11 |
| H12 | Carriage plates, printed brackets (dry zone) | 1 | 40 | b, c | K9c G12 |
| H13 | Roll motor NEMA 23 + 20 : 1 planetary | 1 | 50 | b | K9c R1 |
| H14 | Canned magnet coupling | 1 | 90 | b, job | K9c R2 |
| H15 | Sleeve with J-slots, reaction tab | 1 | 25 | job | K9c R3 |
| H16 | Roll housing, 300 mm drop link, 2 Hall sensors | 1 | 20 | job, b | K9c R4 |
| H17 | Arm-root load cell 30 kg + ADC (weighing, collision) | 1 | 25 | b | K9c P12 |
| | **Hand** | | **860** | | K9c 850 |
| T1 | Cooker pocket 360 × 360 × 200, drained, welded into the deck | 1 | 80 | job | [E] |
| T2 | Splash hood over the cooker base, silicone base sleeve | 1 | 45 | job, b | C6 §6.2 (€30–60) |
| T3 | Clamp-on stubs (jug handle, lid), stainless funnel | 1 | 25 | job | K10 WA10 |
| | **Cooker integration** (cooker on AP2) | | **150** | | K9c hub 435 |
| WL1 | Donor tub opened: cut, collar flange, gasket | 1 | 80 | job | K9c WL1 |
| WL2 | Fan-nozzle rows | 1 | 25 | b | K9c WL2 |
| WL3 | Fork combs with flats | 1 | 40 | job | K9c WL3 |
| WL4 | Lid-bench 540 × 460 + gas strut | 1 | 70 | job, b | K9c WL4 + [E] |
| WL5 | 150 W heater mat under the bench, thermostat | 1 | 25 | b | [E] |
| WL6 | Donor control: relays for pumps, heater, drain, dosing; rinse NTC | 1 | 25 | b | [E] |
| | **Well** (dishwasher on AP4) | | **265** | | K9c 205 |
| RC1–4 | Rinse cup and basket strainer (35), 4 jets (15), spout + flow meter (15), chute with spring flap (35) | 1 | 100 | a, b, job | K9c RC1–RC4 |
| E1 | Gastro work table 1700 × 600 (→ SH2) | — | — | e2 | K9c P15 |
| E2 | Job work: flush hob cut-out, rinse cup, chute, well collar seat | 1 | 130 | job | [E] (C6 §6.1) |
| E3 | Back liner 1.0 mm stainless to z 1450 with bent gutter, HPL above | 1 | 120 | job, b | K9c P18 + [E] |
| E4 | End panel; stainless face on the ambient wall in the splash zone (shared carcass, K9c R2-1) | 1 | 80 | job, b | [E] |
| E5 | Front frame 40 × 40 ≈ 4 m + brackets | 1 | 100 | b | K9c P1 |
| E6 | Ceiling panel with mast slot, box-shaft port and spring flap | 1 | 50 | b, job | [E] |
| E7 | One sliding and one fixed glazed service panel, top track | 1 | 90 | b | K9c E8, R2-7 |
| E8 | Hatch door: sliding glazed panel, NEMA 17 + belt drive, soft edge | 1 | 70 | b | [E] |
| E9 | Household door lock + reed contacts | 1 | 30 | a | K9c P21 |
| E10 | Tool cabinet: liner, sloped soffit, rear spring flaps (carcass → SH2) | 1 | 20 | job | K9c E10 + [E] |
| E11 | Oven shelf | 1 | 30 | b | K9c E11 |
| E12 | Box shelf with release pins, shaft liner | 1 | 50 | job | [E] |
| | **Enclosure** (furniture equivalent on SH2) | | **770** | | K9c 860 |
| V1 | Solenoid valves, hot-rated (jets, nozzle rail) | 2 | 90 | b | K9c P19 |
| V2 | Solenoid valves, cold (spout, mixer) | 2 | 30 | b | K9c P19 |
| V3 | Nozzle rail | 1 | 40 | b | K9c V3 |
| V4 | Piping, hoses, thermostatic mixer | 1 | 60 | b | K9c V4 |
| V5 | EN 1717 backflow preventer; leak tray + sensor under well and boiler | 1 | 60 | b | C6 §6.2 |
| | **Water** | | **280** | | K9c 220 |
| C1 | Klipper board BTT Octopus Pro (8 slots: cell 5 + storage carriage and lid station 3) | 1 | 75 | b | K9c P8 |
| C2 | Raspberry Pi 5 4 GB + eMMC/NVMe | 1 | 135 | b | K9c P10 |
| C3 | TMC5160 drivers (X, Z, roll) | 3 | 69 | b | K9c P9 |
| C4 | TMC2209 drivers (Y, hatch door) | 2 | 12 | b | [E] |
| C5 | PSUs 48 V 350 W + 24 V 150 W | 1 | 55 | b | K9c C5 |
| C6 | Camera Module 3 Wide, heated window, white + UV-A LEDs | 1 | 60 | b | K9c P11 |
| C7 | Power manager: 3 current sensors, 2 contactors | 1 | 45 | b | [E] (K9c 70, K10 35) |
| C8 | Safety chain: 2 force-guided relays | 1 | 40 | b | K9c C8 |
| C9 | Cable chains, cables, connectors | 1 | 90 | b, c | K9c C9 |
| C10 | Hob interface board replacing the UI board (COK-023) | 1 | 70 | b | K9b [D] €60 + [E] |
| C11 | Oven: 25 A SSR, K thermocouple, MAX31855 | 1 | 30 | b | K10 C7 |
| C12 | Cooker R1 interface: isolated UART tap + ESP32 (never bypasses the power board) | 1 | 25 | b | [E] |
| C13 | Relays: boiler, extraction | 1 | 15 | b | [E] |
| | **Controls and appliance interfaces** | | **721** | | K9c 633 + 160 on its appliance side |
| WA1 | Folded riveted stubs on ≈ 42 items | 42 | 190 | job | K10 WA1 (€4.50) |
| WA2 | Press stand for ricer and garlic press | 1 | 35 | job | K10 WA4 |
| WA3 | Bought special tools: corer tubes, pitter, ravioli mould, dumpling press, wireless probe, spoons, strainer basket, fat cup | 1 | 90 | a | K9c WA4 |
| WA4 | Custom fixtures: blade post, egg fixture, Rouladen cradle + 2 raft forks, carving trough, plate cradle, hook rod, fork-spit, lift-rack pair | 1 | 240 | job | K9c WA5 − scraper, kneading roller |
| WA5 | Carriers: 2 plate carriers, 3 tool racks (baskets from the donor) | 1 | 60 | a, job | K9c WA6 |
| WA6 | Board turntable carriers (separable pivot, push pegs) | 2 | 40 | job | [E] |
| WA7 | Bench trays 265 × 420, folded rim, stub | 4 | 60 | job | [E] |
| | **Machine ware** | | **715** | | K9c 1,010 |
| | **CELL MACHINE PART** | | **3,861** | | K9c 4,313 on the same basis |

Against K9c (€4,313 on the same basis), block by block: hand +10 (longer mast); hub → cooker integration −285;
well +60 (larger lid-bench, heater mat, donor relays); enclosure −90 (hatch drawer and cell X-box cover deleted,
one sliding service panel, shared carcass; hatch-door drive and box shelf added); water +60 (backflow preventer,
leak tray); controls +88 (hob, oven and cooker interfaces, +140, moved here from K9c's appliance side); ware −295
(no press cup and S ware, folded stubs, no dog rings; turntables, bench trays and press stand added) =
**−€452 (−10 %)**. Custom part types ≈ 24 (K9c ≈ 28). C6 projected ≈ €3.3–3.5 k without the interfaces, the
splash hood and the backflow/leak items; on that basis K11's cell is ≈ €3.6 k.

### 3.4 Machine part — storage handling

| # | Item | A € | B € | Source |
|---|---|---|---|---|
| S1 | Beam and rail extension 1.85 m: beam 40, 2 × MGN15 150, 4 blocks 30, belt + second omega set 35, gallery floor/cover over storage 60, cable chain 40, wall brackets 20 | 375 | 375 | K9c P1–P3 pro rata; C6 §6.1 (€290–390) |
| S2 | Storage carriage: plates + NEMA 23 omega drive 50, fixed arm 50, hoist NEMA 23 + brake 45, spool / Dyneema / guide / limit 25, passive toggle gripper 60, NFC reader 20; **B** + Y slide (MGN12, NEMA 17) 50 + sub-lid servo hook 20 | 250 | 320 | K9c P4/P5 + [E]; storage round §5.3 |
| S3 | Lid station: vacuum cup, mini pump, valve 35; NEMA 17 lead screw 35; lid magazine ≈ 30 lids 40; sensor 10 | 120 | 120 | [E] (K10 S8 €75) |
| S4 | Stub carriers (green, green, red), bent 1.4404, spring hooks, end pusher, riveted stub | 120 | 120 | storage round §5.3 [E] |
| S5 | Storage controls: **A** 2nd Octopus Pro 75 + SKR Mini 40 + drivers 106 + 3 H-bridges 15 + PSU 35 + 6 loggers 15 + hatch watchdog 15 + cabling 80; **B** SKR Mini 40 + drivers 52 + loggers 15 + watchdog 15 + cabling 40 | 380 | 160 | K10 Q10, K9c P8/P9 + [E] |
| S6 | **A** S4 mechanism, lean: Z NEMA 23 + brake, 3 : 1 belt, cross shaft, 2 HTD-5M belts and sealed idlers, 2 × MGN12 1.9 m, AS5600 (≈ 265); carriage frame with notched runners (120); X and J-hook NEMA 17 slides (85); roof hatch cam (40); drip tray, sump, slot-spray nozzle + valve (60); cabling (50) | 620 | — | storage round S4 (€1,470, lean €1,200) re-priced at K9c level [E] |
| S7 | **A** Cool section, machine part: roller shutter + motor, 40 W Peltier with fans, controls | 250 | — | storage round §4.4 [D] |
| S8 | **A** Fridge robot: CoreXY 2 × NEMA 17, GT2, MGN12 × 2, trolley, 2 shafts through PTFE bushings (170); NEMA 17 hoist inside (45); toggle gripper (60); load cell, reed switch (25); cabling (25) | 325 | — | storage round S1 (€1,000) re-priced [E] |
| S9 | **A** Freezer robot: as S8 with a cold-rated hoist (−40 °C grease, winding pre-warm) | 355 | — | storage round S1 (€1,100) re-priced [E] |
| S10 | **A** C1-B exits: window cut in the middle band, PP throat, exit plate, PU slide, constant-force spring, magnetic gasket, 12 V gear motor (fridge 300); + skirt and heated seat (freezer 335) | 635 | — | storage round §4.1 [D] |
| S11 | **B** Fridge top: stainless exit plate over the whole top, 4 windows ≈ 200 × 190, 4 insulated sub-lids on magnetic gaskets, springs, hold-open only by the carriage's servo | — | 260 | [E] (C6 §6.1: full-top lids €250–300 per shell) |
| S12 | **B** Freezer top: as S11 + 4 skirts and 4 dew-point-controlled 3 W seat heaters | — | 310 | [E] |
| S13 | **B** Ambient roof hatch (spring-closed, lifted by the servo hook) | — | 40 | [E] |
| S14 | **B** Nest stack for empties (CAP-023) | — | 30 | C6 §6.2 |
| | **STORAGE HANDLING MACHINE PART** | **3,430** | **1,735** | storage round 3,800 + 635 access + ≈ 500 gallery |

### 3.5 Boxes and kitchen content

| # | Item | € | Source |
|---|---|---|---|
| BX | ≈ 170 storage boxes GN 1/6 and 1/9 in PP copolymer, gasketed flat lid, 2 NFC tags, DataMatrix (≈ 96 ambient incl. 26 empties, 45 chilled, 24 frozen, 8 cool); Tritan ≈ +€500 | 1,700 | W5 (box €2.35–4.35 + lid €5.19 + tags ≈ €1) |
| KC | Kitchen content: K9c K1–K11 (375) − kneading bowl and spinner basket (25) + red turner and spatula (15) + second cooker jug with blade (90) | 455 | K9c §5.2 + [E] |
| GD | Gadgets: ricer / Spätzle press 28, unpeeled-garlic press 37 (push dicer +30 only if B6 needs it) | 65 | K10 Q6/Q7 |
| DS | Dish set for CAP-031 (plates, bowls, glasses, cutlery): the household's own | 0 | — |
| | **Boxes and kitchen content** | **2,220** | |

### 3.6 Totals, and Ben's expectation

| Block | **A compliant** | **B cheap** | Ben's expectation (#28) |
|---|---|---|---|
| Household appliances | 3,243 | 3,243 | ≈ 2,500 (hob 500, oven 500, fridge + freezer 1,000, dishwasher 500) |
| Shelving (storage structure + kitchen furniture equivalent) | 1,670 | 1,270 | 500–1,000 |
| **Appliances and shelving** | **4,913** | **4,513** | **≈ 3,000–3,500** |
| Machine part: cell | 3,861 | 3,861 | |
| Machine part: storage handling | 3,430 | 1,735 | |
| **Machine part** | **7,291** | **5,596** | **≈ 2,000** |
| Boxes and kitchen content | 2,220 | 2,220 | (not in his figure) |
| **Out of pocket** | **≈ 14.4 k** | **≈ 12.3 k** | ≈ 5.0–5.5 k + boxes |

* **Appliances**: +€0.2–0.7 k over Ben's figure, entirely from the two 178 cm built-in cold appliances (€1,708
  instead of €1,000) and the boiler and extractor he did not list; hob, oven and dishwasher together cost €836
  instead of €1,500. Shelving is over because the storage racks are machine-grade (welded stainless runners, cold
  posts) and the cell's deck is a Gastro table.
* **Machine part**: **3.6 × (A) or 2.8 × (B) Ben's €2 k.** The cell alone is €3.9 k: hand €0.86 k, controls and
  interfaces €0.72 k, enclosure €0.77 k, ware €0.72 k, water €0.28 k, well €0.27 k, rinse cup and chute €0.1 k,
  cooker integration €0.15 k. No single line is above €140; the €2 k target would need a different principle for
  the hand or the wet cell, as K9c §6.3 found.
* **In a series of ≥ 50** (job-shop and maker parts −25…−35 %, K9c R2-9): machine part A ≈ €5.0–5.5 k, B ≈
  €3.8–4.2 k [E].

### 3.7 If R1 fails: the hub instead of the cooker

K9c's hub with ring coil (H1–H8 €435) + press cup (€150) + S ware (€110) replaces the cooker integration (T1–T3 and
C12, €175): **machine part +€520**; appliances −€399 (no cooker); kitchen content −€75 (no spare jug, + kneading
bowl). **Net whole machine ≈ +€45.** With the cheaper Mambo (€219) the cooker saves ≈ €225. The thermo-cooker is
therefore **not a cost lever for the whole machine**; its value is food (closed stirred heating, emulsions,
weighing, steaming), two motors and two novel mechanisms less (N3 press cup, N4 ring coil), against the R1 risk and
a consumer LRU with yearly model churn.

### 3.8 Cost levers left for Ben (not taken in the totals)

| Lever | Saves | Costs |
|---|---|---|
| Hybrid storage (S4 ambient, top-dug cold, §2.4) instead of A | ≈ €0.85 k machine, €0.05 k structure | CLD-006 waiver for unplanned cold boxes |
| Drop the cool section (CAP-024, storage round Q1) | €350 | dark ambient storage at room temperature; +17 ambient positions |
| Cheaper 7.4 kW hob once the interface is proven on it | ≈ €200 | a second interface reverse-engineering |
| Mambo 11090 instead of MC Smart | €180 | hinged lid never reaches the well (C6 §3.3) |
| BTT CB1 instead of the Raspberry Pi 5 (K9c R2-2) | €95 | still-image vision only |
| Lip-sealed roll instead of the canned coupling (K10) | €75 | a third dynamic seal (test R6) |
| Kitchen content and boxes bought by the household anyway | — | accounting only |

---

## 4. Requirements check: every Must that fails or is marginal

✗ = fails as designed; **m** = marginal (met on paper with little margin, or met only after a named test); ✓ = met.
Musts not listed are met as in K9b/K9c and the storage round. "Fixed" at the end lists the Musts K10 failed that
K11 meets.

| Requirement (M) | A | B | Cause | Fix, or the waiver Ben must give |
|---|---|---|---|---|
| **PHY-003** module widths on the 150 mm grid, none > 1,200 | ✗ | ✗ | ambient 650 and the integrated cell 1,750 (inherited from K9b and the storage round) | waiver: the cell is one integrated module; 650 for S4's three lanes |
| PHY-004 ≤ 3,600 mm | m | m | 3,600 with 0 mm spare | E1 measures every appliance; fallback: fridge and freezer 20 mm apart (storage round: 1,140 mm) |
| PHY-002 height incl. boxes carried in the gallery | m | m | a T box + gripper must pass at z 2005–2200 | E1 height budget; fallback: T boxes never cross the cold tops |
| **STO-003** retrieval ≤ 30 s, mean ≤ 15 s | ✓ | ✗ | B digs from the top: random mean ≈ 50–70 s, worst ≈ 2.5 min | **waiver B**: planned ≈ 15–20 s after overnight re-sorting |
| STO-006 any box mix without hardware change | m | m | A: S4's height mix is set by its partition set; B: GN 1/9 needs its own stacks | accept a fixed default mix (storage round §3.5) |
| CLD-004 exit open ≤ 10 s per passage | ✓ | m | B: each sub-lid open ≈ 6–8 s, set by the servo hook and the hoist [U] | cut test with sub-lids (§7.2 T11) |
| **CLD-006** cold retrieval ≤ 45 s | m | ✗ | A: a deep unplanned chilled box ≈ 60–70 s (storage round Q2); B: random digs 1–2.5 min | A: sub-stack-lift rig test, else **waiver** (menu-planned chilled boxes); B: **waiver** |
| CLD-008 / CLD-014 no frost build-up, exit does not freeze shut | ✓ | m | B: four freezer seats instead of one | dew-point-controlled seat heaters, one-week freezer test |
| **CAP-021** ≥ 45 chilled positions | m | ✓ | A: 38–45 depending on the real interior [U] | E1; fallback GN 1/9 stacks in part of the grid, or Q2 (b) ≈ 36 with waiver |
| **CAP-024** cool zone 8–15 °C, ≥ 8 boxes | ✓ | ✗ | B has no place for the thermoelectric section | **waiver** (storage round Q1 recommends it for A too: −€350) |
| CAP-025 ≥ 143 food positions + reserve | m | ✓ | A: 72 + 9 + 38–45 + 24 = 143–150 | follows CAP-021 |
| **CAP-031** dish store 8 × flat, deep, small plates, glasses, cutlery | ✗ | ✗ | the 25 L oven no longer holds plate carriers; the well is also the big-ware store: 8 flat + 8 deep plates, glasses and cutlery fit (2 carriers + 2 baskets), the 8 small plates do not [E] | **waiver**: small plates stay in the household cupboard (breakfast is outside the machine, #16); or one tool rack in the cabinet becomes a plate rack |
| SRV-014 dish return at any time, careless placement | m | m | hatch "busy" ≤ 5 min while the well lid is open (≈ 3–4 windows per 4-person meal); return into carriers as K9b, not onto a pile | **waiver** of "any time" to "except ≤ 5 min busy windows"; carrier return as K9b Q8 |
| PERF-001/002 benchmarks | m | m / ✗ | B3 47 (44–51) of 50, B5 144 of ≈ 150, B7 54 of ≈ 54 marginal; **B6 51 of 50 fails** without the push dicer; in B an unplanned 4-person meal adds 5–15 min (B3, B6, B7 then fail) | push dicer after HYG-027 (B6 → 47); E0 simulation; in B plan meals ahead |
| PERF-005 clean in 90 min | m | m | ≈ 72–80 min for 4 persons (donor heats the rinse: +3 min per load); counted from serving only if dishes return within ≈ 45 min | fallback 10 L boiler pre-heating the rinse (+≈ €30) |
| HYG-006 no human cleaning | m | m | oven cavity after a spill (inherited K9b Q12); cooker base under its splash hood [U] | **waiver** for the oven cavity (as K9b); test R7 for the cooker |
| HYG-013 Zone F geometry | m | m | ricer and unpeeled-garlic press (and push dicer) are crevice parts | HYG-027 test after a real programme with 2 h dried soil; if they fail: mash in the cooker, garlic by the ricer, or bought peeled garlic (Ben, as #9) |
| HYG-021 A0 ≥ 60 on class-R ware | ✓ | ✓ | well A0 ≈ 95; sleeve after an R grip 20 s at 85 °C ≈ 63 (m) | logger validation (K5) |
| HYG-004 no drive above open food | m | m | the hoist spool and line are above the opened box at the box-shaft port | drip shield under the spool (≈ €10) |
| RES-001 ≤ 3.0 kWh per 2-person meal | m | m | ≈ 2.6–3.4 kWh [E] (K9b 2.6–3.5) | measure in K5/E0 |
| RES-002 ≤ 7 kWh/day | m | m | 2 meals 5.2–6.8 + cold ≈ 1.1–1.2 + idle 0.2 | as RES-001; dropping the cool section saves 0.2–0.35 kWh/day |
| RES-003 idle ≤ 15 W | m | m | Pi 5, two boards, PSUs, appliance standby | relays cut cooker, hob, oven and boiler when idle |
| RES-004 cold ≤ 1.2 kWh/day | ✓ | m | ≈ 116 [U] + 235 [W4] + 45 kWh/a exits = 1.08 kWh/day; B + seat heaters ≈ 1.15–1.2 | choose a fridge ≤ 110 kWh/a [U] |
| REL-004 life or declared LRU | m | m | cooker (≈ 5,500 h stirring in 10 years) and donor dishwasher (≈ 700–900 loads a year) exceed household duty | declare both as LRUs: cooker 2–4 years, donor 3–4 years (buy two cookers at once, model churn) |
| REL-005 MTBF ≥ 6 months | m | ✓ | A: 20 motors, 2 bands, 4 bushings → ≈ 1.1–1.3 exchanges a year, MTBF ≈ 9–11 months [C on C3 X10 rates: 3 % per axis, 25 % per band]; B: 10 motors → ≈ 0.8, ≈ 15 months | modular spares |
| TRN-003 L layouts | m | m | the straight shared beam does not turn a corner | corner transfer only in an L kitchen (storage round §6.4, ≈ +€500) |
| Coverage ≥ 93 % (#26, MEAL) | m | m | central 232 (93.5 %), range 229–234 | R8 desk walk |

**Fixed against K10 (C6 §7.1):** PERF-005 (K10: 3–5 h), HYG-021 (household 65–70 °C), COK-002 (now 4 pans and two
≥ 3 kW zones, also better than K9b/K9c), the work surface (0.25 m² bench + cold hob), two plates side by side,
pasta water (the 6 kg hand pours through the strainer lid), CAP-021 (no 122 cm shells), CLD-004 (in both options),
STO-007/008 (closed gallery, cell under-pressure), no appliance door over the hot zone.

---

## 5. Coverage and the twelve benchmarks

### 5.1 Coverage (C1 standard N, 248 meals, 8 excluded; target 231 = 93 %)

Start: K9b/K9c central 233 (K9b §7.2). K11's changes [E]:

| Change against K9b | Meals | Note |
|---|---|---|
| Heated hub with hung scraper → thermo-cooker (closed stirred heating ≤ 120–130 °C) **plus** 4 pans on 2 × 3.7 kW | 0 | risotto, polenta, béchamel, vanilla sauce, hollandaise, mayonnaise M → H (K10); stirred browning (Gulasch onions, curry paste, roux) stays in pans, stirred at intervals by the hand — C6's #27 objection to browning in the jug does not arise |
| Press-cup grids → knife dice; cooker chop only where the cooked dish hides it (soffritto, curry paste) | 0 | +3–5 min per kg diced; push dicer after HYG-027 as the time fallback (B6) |
| S slicing and grating discs → blade post on the spit (1 / 2.5 / 5 mm, rasp edge); Parmesan in the jug | 0 | semi-hard cheese grated on the rasp edge, slower |
| Board turned on T → passive turntable carrier | **−1** | MX06 guacamole: avocado halved round the stone needs a turning board while the knife holds (as K10) |
| Pfannkuchen: spin-spread on the heated hub → **gyrating spread**: the hand moves the lifted pan on a ±45 mm circle at ≈ 1 Hz, i.e. a rotating effective tilt of ≈ 10° [C: 0.045 m × (2π)² ≈ 1.8 m/s²], without yaw or a second tilt axis | 0 [U] | low end −2 (Pfannkuchen family) if the rig test fails |
| Gadgets gated by HYG-027: if the unpeeled-garlic press fails, the ricer presses garlic in its skin (K9b's ricer-die route); if both fail, 44 garlic meals need bought peeled garlic | 0 | Ben's ruling needed only in that case (as #9 for onions) |
| Kneading ≤ ≈ 500 g flour per batch [U]; 25 L oven with GN 1/2 trays | 0 | bread and pizza for 4 in 2–3 batches, +10–25 min |
| Jug emptying of sticky mass and dough [U] | 0 | +1–2 min per emptying; fallback knife, bowl and hand |
| **Central** | **232 = 93.5 %** | range **229–234**, reserve 1 (K9b 2); out as K9b: AS08, IN07, CK12; at risk: DM12, AS09, MX06; low end also CK16, IT17, DM33 |

### 5.2 Benchmarks B1–B12 (exploration brief; limits PERF-002 or 1.15 × T_ref + 10, the same for 2 and 4 persons)

Times from the order in minutes [E], K9b §6 as the reference, with K11's station effects: 4 pans (parallel batches),
the jug instead of the hub, knife dice instead of the press cup, the blade post instead of S discs, the 0.8 m/s
hand, the turntable (+1–2 min), the 25 L oven, turnaround well loads of 9–11 min. Storage as option A (or a
menu-planned meal in B).

| B | Dish | Limit | K9b 4 p | **K11 4 p** | **K11 2 p** | Verdict | Critical path in K11 |
|---|---|---|---|---|---|---|---|
| B1 | Rouladen, Rotkohl, Salzkartoffeln | 183 | 130 | 135 | 128 | ✓ | Rouladen seared in 2 pans at once, braised in the braiser; Rotkohl shredded on the blade post (2.5 mm), braised in the 5 L pot on a rear zone |
| B2 | Schnitzel, Bratkartoffeln, Gurkensalat | 68 | 50 | 50 | 44 | ✓ | breading line 3 × GN 1/3 on the bench (528 mm); 4 Schnitzel in 2 pans on the two front zones in one batch; Bratkartoffeln on a rear zone; cucumber on the blade post |
| B3 | Frikadellen, Püree, Erbsen-Möhren | **50** | 45 | **47 (44–51)** | 41 | **m** | mass mixed in jug 1 and emptied [U], jug 1 to the turnaround load; potatoes peeled on the spit and boiled in the 5 L pot from 85 °C water; mash in jug 2 with the whisk; 8 patties in 2 pans; carrots knife-diced + frozen peas |
| B4 | Spaghetti Bolognese | 96 | 88 | 82 | 76 | ✓ | soffritto chopped in the jug; mince seared in 2 pans; sauce simmers 60 min in the braiser (6 interval stirs) or in the jug ≤ 2 L; Parmesan in the jug |
| B5 | Pizza from flour, 2 trays | ≈ 150 | 120 | **144** | 112 | **m** | dough 500 g in the jug, proofing in the oven at 35 °C; GN 1/2 trays: 3 bakes instead of 2 |
| B6 | Gemüseeintopf | **50** | 46 | **51** (47 with the push dicer) | 44 | **✗ / ✓ with dicer** | 1.2 kg of roots and potatoes knife-diced (≈ 5 min/kg) instead of the press-cup grid; bean trimming as K9b; 5 L pot on the front-left zone |
| B7 | Steak, oven fries, salad | ≈ 54 | 48 | **54** | 42 | **m** | fries cut by knife (10 mm, ≈ 8 min/kg); two GN 1/2 levels in convection; 4 steaks in 2 pans at once (K9b 2 + 1 batch); lettuce spun in a basket on the roll axis [U] |
| B8 | Pfannkuchen, 8 | 50 | 36 | 32 [U] | 22 | ✓ if the spread works | batter in the jug; 2 pans in parallel, gyrating spread |
| B9 | Chicken curry with rice | ≈ 62 | 48 | 52 | 46 | ✓ | onion-garlic-ginger paste blended in the jug and fried in a pan; chicken in a second pan; simmer in the braiser; rice in the 3 L pot |
| B10 | Lasagne, béchamel from scratch | 148 | 125 | 125 | 118 | ✓ | béchamel in the jug; ragù in the braiser; layered in GN 1/2-65 on the bench |
| B11 | Rührkuchen in a loaf tin | ≈ 102 | 95 | 95 | — | ✓ | creaming and folding in the jug (whisk insert); 25 cm tin |
| B12 | Scrambled eggs, toast | ≈ 21 (1 p); 17 (4 p, PERF-002 i) | 9 | 13 | 9–10 | ✓ | eggs cracked on the loose egg fixture on the bench; pan on a front zone |

Other PERF-002 items: (c) steak + baked potato + salad ≈ 60 of 79 ✓; (h) mixed salad ≈ 20–24 of 27 ✓; (f) roast
pork ≈ 200 of 229 ✓ (carving trough).

**Result**: 8 of 12 ✓ with margin, three marginal (B3, B5, B7), one fails by about a minute without the push dicer
(B6). The four pans recover what the slower hand, the knife dice and the small oven cost; the bottleneck is still
the single hand in the 50-minute dishes (B3, B6), as in K9b. **In option B** an unplanned 4-person meal starts with
≈ 20 random digs (≈ 15–20 min of storage-carriage time, partly overlapped with prep): B3, B6 and B7 then fail;
planned meals are as above. The E0 discrete-event simulation (§7.2 T1) must confirm every number in this table.

---

## 6. Cleaning concept

### 6.1 Disinfection values (A0 = Σ 10^((T − 80)/10) · Δt at the surface [C])

| What | Process | A0 | HYG-021 (A0 ≥ 60) |
|---|---|---|---|
| All ware, dishes, bench trays, carriers, storage boxes, cooker jug and lid, gadgets | well programme: pre-rinse, wash 55–60 °C, **final rinse ≥ 82 °C held 60 s on the coldest item** (donor heater, rinse NTC; validated with loggers on a heavy pan and a PE board, C2 R-3), fan dry with the lid ajar to the extraction; 15–18 min | **≈ 95** | ✓ margin 1.6 × |
| Same, red → green during the meal | turnaround programme with the same final rinse, short wash; 9–11 min | ≈ 95 | ✓ |
| Sleeve and reaction tab after a **class-R** grip | 4 fan jets at 85 °C for **20 s** (K9b: 10 s) before any clean item is touched (software interlock) | ≈ 63 [C, surface at 85 °C, U] | m (logger) |
| Sleeve after other soiled grips | jets 3–10 s | cleaning only | — |
| Cooker jug between a raw-produce use and a ready-to-eat use, or after an allergen | boil-clean: water + detergent at ≈ 100 °C, high speed, 3 min, then a 2 min clear-water rinse (HYG-023) | ≈ 18,000 on wetted surfaces | ✓ where wetted |
| Cooker jug after **raw meat** (e.g. Frikadellen mass) | not boil-cleaned: jug 1 goes to the well's turnaround load, jug 2 continues on the base | ≈ 95 | ✓ |
| Deck, liners, soffits, hob glass, bench lid top, cooker splash hood | fixed nozzle rail: 85 °C rinse with detergent, then clear; deck drains to the rinse cup; hob glass also by the scraper-squeegee | Zone S cleaning | (no food contact by rule B-1) |
| Rinse cup, chute, pocket drains | jets and rail after every meal, daily hot rinse | Zone S | — |
| Household dishwasher, for comparison (C6 §3.1) | 65 °C 10 min / 70 °C 10 min | 19 / 60 | not used in K11 |

### 6.2 Raw / ready-to-eat separation

* **By item**: red board, chef's knife, spatula-tongs, turner, spatula, wash pot, stub carrier and cooker jug 1
  for class R; green twins for ready-to-eat. With these twins a 2-course meal for 4 runs without re-washing
  (CAP-030); the turnaround load is the reserve.
* **By sequence**: ready-to-eat produce first, raw items last in prep; raw meat leaves its GN only into a hot pan.
* **By place**: food never touches the bench top (rule B-1): raw only in GN on a bench tray, the tray goes to the
  well afterwards; class-R boxes arrive only in the red carrier; in the cold stacks R boxes have their own stack and
  never stand above RTE (CLD-011; in option B the night re-sort keeps it so).
* **By the hand**: 20 s hot sleeve rinse after any R grip; the storage gripper touches only box rims and never
  covers an open box.
* **By the clean store**: the well (closed, dried) holds big ware and dishes between meals; tools in the closed
  cabinet; GN 1/2 trays in the cold oven. Everything a menu needs is taken out **before any food is opened**
  (C2 R-6).

### 6.3 PERF-005 timeline, 4 persons (serving starts at t = 0) [E]

| t (min) | What | Well |
|---|---|---|
| −15…−5 | turnaround load with the prep ware (boards, knives, jug 1) | running |
| 0–5 | plating, two hatch cycles (SRV-009 ≤ 3 min if the first pair is taken) | idle |
| 5–8 | pans, pots and braiser into the well (bench cleared, hatch "busy") | loading |
| 8–24 | load 1: cooking ware | running |
| 24–27 | unload to the cold hob, cabinet and oven; load 2: remaining ware, serving GN, bench trays | loading |
| 27–43 | load 2 — the diners return dishes into the carriers on the bench meanwhile | running |
| 43–46 | dishes loaded | loading |
| 46–62 | load 3: dishes, glasses, cutlery | running |
| 62–80 | unload; clean ware back into the well as the clean store; nozzle-rail rinse of deck, hob, bench and liners; fan dry | drying |
| **≈ 25** | **ready for the next meal** (hob, jug 2, boards, knives clean) | ≤ 30 ✓ |
| **≈ 72–80** | **all clean, dry, idle** | ≤ 90 ✓ (10–18 min margin) |

2 persons: two loads after serving, ≈ 45–50 min (S target 45 marginal). The 90 min hold if the dishes come back
within ≈ 45 min of serving; later returns shift the end accordingly. Water per 2-person meal ≈ 30–33 L, energy
≈ 2.6–3.4 kWh incl. washing (reported, #23).

---

## 7. Decisions for Ben, and the test programme

### 7.1 Decisions (with the default used until Ben answers)

| # | Question | Default |
|---|---|---|
| D1 | **Storage**: A compliant (machine part €3.43 k + structure €1.25 k), B cheap (€1.74 k + €0.85 k; waivers STO-003, CLD-006 for unplanned boxes, CAP-024), or the hybrid (S4 ambient + top-dug cold, ≈ €2.6 k + €1.2 k; waiver CLD-006 for unplanned cold boxes only)? | **A** (no waiver assumed). Recommendation: the **hybrid** — chilled boxes are menu boxes (#17) and frozen boxes are thawed ahead (CLD-013), A already needs Q2 for deep chilled boxes, and the hybrid has the larger fridge (≈ 48) |
| D2 | Waivers needed in **every** option: PHY-003 (650 / 1,750 mm modules), CAP-031 (small plates in the household cupboard), SRV-014 ("busy" ≤ 5 min while the well lid is open; return into carriers), HYG-006 for a soiled oven cavity (as K9b Q12) | yes |
| D3 | A **bought thermo-cooker** (Monsieur Cuisine Smart, €399; two bought at once) as the stirred, blending, kneading and weighing position, only if R1 passes; fallback K9c's hub. It is cost-neutral for the whole machine (§3.7) and is chosen for food and simplicity | yes, gated |
| D4 | A **60 cm 4-zone hob with 7.4 kW** (€436) instead of C6's domino + cheap single plate: same width and money, 4 pans, COK-002 met without K9c's Q7 waiver | yes; domino + plate as fallback if the hob interface fails |
| D5 | **Hatch on the well-lid bench** (motorised sliding door; plating, serving and dish return on the bench) — the only arrangement found that fits cooker, 3+ pans, a 0.25 m² bench and two plates side by side into 1,750 mm | yes |
| D6 | **Cool zone** CAP-024: keep the thermoelectric section in S4 (€350, 60–130 kWh/a) or store potatoes, onions, garlic, tomatoes and citrus dark at room temperature? | keep in A; recommendation: drop (storage round Q1) |
| D7 | **Fridge retrieval** (A): deep chilled boxes pre-dug from the menu plan (storage round Q2 a) | yes |
| D8 | **Gadgets**: ricer and unpeeled-garlic press (push dicer only for B6) used only if they pass HYG-027; if both presses fail, accept bought **peeled garlic** like peeled onions (#9)? | decide after T6 |
| D9 | **Accounting**: thermo-cooker and furniture equivalent on the appliance/shelving side; boxes and kitchen content as their own block | yes |
| D10 | **Cost**: accept a machine part of ≈ €5.6 k (B) to €7.3 k (A) at one unit (≈ €3.8–5.5 k in a series) for the full function set, or name functions to give up (K9c §6.3)? Round 2 saved 10 % on the cell; a third round of the same kind would save less than its test cost | accept and go to the tests |
| D11 | Household-grade safety chain and hobby-grade electronics (K9c Q4, Q5) | yes, pending K4 |
| D12 | 20–25 L countertop oven with GN 1/2 trays (pizza for 4 in three bakes, no steam) | yes |

### 7.2 The cheapest test programme, in order

| # | Test | Decides | Cost | Time |
|---|---|---|---|---|
| T1 | **Desk**: R8 coverage walk with K11's routes; E0 discrete-event simulation of B1–B12 and four menus with K11 station times, well loads, hatch busy windows, jug emptying and boil-cleans, storage moves for A and B | coverage 232; B3, B5, B6, B7; PERF-005 | €0 | 4–5 days |
| T2 | **E1 measurements**: hob cut-out and UI board, oven ≤ 450 mm along y, cooker dimensions and lid lock, fridge and freezer interiors, top walls (thermal camera, service manuals), gallery height budget | 3.6 m, CAP-021, pick line | €0–100 | 2 days |
| T3 | **E2 GN box samples** from three makers (rims, lids, nesting, NFC, −18 °C, 50 washes) | box standard, nest stack | €230 | 3 days |
| T4 | **R1 cooker**: two MC Smart; network/app check (1 day) → open, log UI ↔ power board, replay (2–4 weeks) → fallback solenoid fingers + camera; with **jug emptying** (20 × chopped onion, Frikadellen mass, 500 g dough, risotto, residue by weight) and lid handling by a hand-held stub tool | cooker or hub | €820 (units re-used) | 3–5 weeks |
| T5 | **Hob interface** on the PIE631BB5E: UI ↔ power-board bus sniff and replay (in parallel with T4) | 4-zone hob or domino + plate | €436 (hob re-used) | 2–3 weeks |
| T6 | **HYG-027 gadgets**: ricer, unpeeled-garlic press, push dicer after 2 h dried garlic and potato starch, one 70 °C programme, riboflavin + ATP | gadget routes, D8 | €130 | 3 days |
| T7 | **Gyrating batter spread** and roll-spun salad basket on a hand-driven XY jig | B8, B7 salad | €30 | 1 day |
| T8 | **R10 1 : 1 mock-up** of the cell: cooker in its pocket under the box shelf (jug lift under roll axis 1,240), hob, bench-hatch with door, oven-door corridor, tool cabinet | layout of §1.4 | €80 | 2 days |
| T9 | **K1 gantry rig on the shared beam**: 3.6 m beam with jointed MGN15 rails, static belt, two omega carriages, the cell mast with Z and Y; tip deflection at 6 kg / 300 N, zoning, 10,000 moves | hand and rail | €700 (re-used) | 2 weeks |
| T10 | **K5 donor-tub well**: €300 dishwasher cut open, collar, combs, 82 °C rinse by the donor heater, loggers on the coldest item, turnaround time, sump plastics at 82 °C | HYG-021, PERF-005 | €400 (re-used) | 1 week |
| T11 | **Storage rigs**: E3 stub carrier (€150) in both; **A**: E4 S4 one-lane rig (€500) + E6 cold S1 rig with the passive gripper and the sub-stack lift (€750); **B**: cut test of four sub-lids in a used fridge and freezer with the servo hook, CO₂ tracer, energy and seat frost for a week (€400) + dig timing on a basic stack rig (€300) | storage option | A €1,400 / B €850 | 2–3 weeks |
| T12 | Soaks: hobby electronics at 40 °C / 80 % RH (K3, €100), load-cell drift (K10, €40), cooker base and boil-clean hygiene (R7, €60); riveted stubs ride along in T10 | REL, HYG | €200 | 2–3 weeks |
| | **Total** | | **≈ €4.5 k (A) / ≈ €4.0 k (B)**, of which ≈ €2.2 k are parts re-used in the prototype | **≈ 8–10 weeks** with T4/T5 and T9–T11 in parallel |

**Order**: T1–T3 cost almost nothing and can stop marginal benchmarks or the 3.6 m width; T4 and T5 can stop the
two new appliances (their fallbacks are known and costed: hub at net +€45, domino + plate at the same width);
T6–T8 are cheap and settle routes and layout; T9–T11 prove the hand, the well and the storage option chosen in D1.
