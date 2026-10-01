# C5 — Critique of the preparation concepts K1…K8: simplicity

Round P4, critic C5. View: the customer's new decision criterion (DECISIONS #20). Simple solutions
(a) work far more reliably, (b) are often easier to clean, (c) are normally cheaper, (d) are easier to build and
(e) are often smaller. When two solutions are close, the simpler one wins.

The question here is not whether a concept works (C3), cleans (C2), cooks (C1) or fits (C4). It is **how much
machine** each concept needs for what it does, and where that machine can be made smaller without losing meals.

**Decision state used.** DECISIONS #1–26. In particular #8/#9 (the machine washes, peels and cuts produce; peeled
onions are allowed), #19 (at most 4 persons), #20 (simplicity), #21 (job-shop welded stainless allowed), #22/#23
(cost and water are reported but are not gates now; hygiene first), #24 (a bought oven may be modified), #25
(generic peeling and stoning is a core function, preferably by generic mechanisms) and #26 (coverage target
93 %; filled pasta and pastry sheets still may not be bought).

**Sources.** All eight concept documents. Sections 1, 2, 6, 7, 9–12 of K1–K8 were extracted line by line into
count sheets: two helper extractions, checked against C3's tables. Also read: both gap documents (summaries,
host needs, parts lists), the catalogue (section 3, rules 4.1), C1–C4 in full or in their summary, comparison
and score sections, and requirements REL, BLD, PHY, MEAL-002…021 and 5.4–5.6.

Markers: **[D]** taken from the concept document; **[C]** recomputed here; **[E]** my estimate. Counts are paper
counts by the concepts' own advocates, normalised as described. Nothing was built.

---

## 1. Summary

| | Simplicity score (1–10) | Actuators (cell) | Dynamic seals | Novel mechanisms | Distinct mechanisms | Events per meal | One-line verdict |
|---|---|---|---|---|---|---|---|
| K1 ceiling turret | **3.1** | 17 | 13 | 7 | 10 | ~190 | Three 5-axis hands, 30–45 bayonet changes a meal and a 7.3 m seam: the most complex way to hold a tool |
| K2 vessel stack | **4.3** | 15 | 8 | 7 | 11 | ~90 | Few events and easy to repair, but five washing points and seven novel stack/inversion mechanisms |
| K3 drum and belt | **3.5** | 25 | 19 | 7 | 13 | ~85 | "No manipulator" became two manipulators plus two process lines: the most actuators and seals |
| K4 shuttle mat | **3.8** | 20 | 22 | 8 | 12 | ~95 (+300–900 strokes) | Few loose parts; but the whole concept is novel and has 22 rotary passages |
| K5 ram and die | **3.9** | 16 | 10 | 9 | 14 | ~90 | A simple column inside a complex cell: 14 mechanism types and the longest series chain |
| K6 loose ware | **4.5** | 12 | 7 | 4 | 12 | ~115 | Fewest unknowns and easiest to repair; its complexity is logistics (93 items, 45 skills) |
| K7 state change | **3.3** | 17 | 8 | 10 | 15 | ~145 | The booster adds a refrigeration circuit and the most novel mechanisms without removing any |
| K8 sealed tub | **5.1** | 13 | **0** | 8 | 13 | ~120 | The simplest hardware (no seal, one washing system); its simplicity rests on eight untested principles |
| *S-min (reference, section 7)* | *7.1 (target)* | *9* | *5* | *2* | *6* | *~65* | *The simplest machine that should reach the 93 % target, built from proven parts of K6, K7, K8* |

**Five headline findings.**

1. **No concept is simple.** On an absolute scale anchored to what a simple machine would need, all eight score
   **3.1–5.1**. The spread between them is smaller than the gap to a deliberately simple reference built from
   their own best parts (7.1, section 7). Round P5 should design for simplicity from the start, not select it.
2. **Novelty dominates.** Every concept carries **4–10 independent untested mechanisms**. Each one is a research
   project with a real chance of failure. Each one is also a hidden source of adjustments, wear and software.
   This is the single largest simplicity cost, and the one that is cheapest to remove: replace the novel
   mechanism by a proven or bought one, and accept a recipe adaptation.
3. **Complexity was moved, not removed** (as C3 §6 found for actuators). The same pattern applies to stations
   and washing: K1, K2, K3 and K5 each need **five or six cleaning points**. K6 needs three, K8 two. Only K8 is
   genuinely simpler in the machine, and it pays for that in ware, software and unproven magnetics.
4. **The common front end is the simplest place to cut.** The dosing dock (2–6 actuators) and the egg module
   (3 actuators) appear in every concept. C3's normalised counts leave them out, but they are real. A manipulator
   that tips the opened box over a weighing cup, plus a passive egg fixture, removes **5–9 actuators in every
   concept** at almost no coverage cost (section 5).
5. **The coverage slack is now tiny.** #26 sets 93 % (231 of 248 meals). C1's ceiling under #8 is 231, and #25
   adds about 2–3 meals (banana, avocado). That leaves a reserve of **2–3 meals**. Simplification must therefore
   turn meals into *adapted* meals (MEAL-019: class c ≤ 24, of which ≤ 5 weight-3 meals) rather than drop them.
   "Drop a station and lose its meals" works only for stations that carry no meal on their own (section 6.2).

---

## 2. Simplicity defined measurably

### 2.1 Metrics and weights

Each metric is a count that a round-P5 document can report. Weights follow the customer's five reasons. A metric
gets more weight the more of the reasons it drives, and the more strongly it drives them.

| # | Metric (what is counted) | Drives reason | Weight | Why this weight |
|---|---|---|---|---|
| S1 | **Motion actuators** in the cell, without dock, egg module and oven door (C3's normalisation) | a, c, d, e | 10 | Each actuator is a motor, a driver, a cable, a homing routine and a failure mode. Size follows the number of axes |
| S2 | **Dynamic seals, sealing bands and bellows** in the splash zone; each is also a moving wall penetration | a, b, c | 12 | C3 X10: a seal is 10–25 × as likely to need exchange as a dry servo axis. Each seal is a crevice above food (C2 R-2). It drives MTBF more than any other count |
| S3 | **Distinct mechanism types**: powered or passive machines and stations, not plain ware | a, c, d, e | 10 | Every type is its own design, spare-part list, failure analysis and calibration. It also measures how much there is to understand |
| S4 | **Independent novel mechanisms**: no product or catering precedent; a rig must prove them. Mechanisms common to all eight are left out (pan-pair flip, Rouladen seam, egg module, dock tilt) | a, d | 15 | Each is a research project that can fail, and each brings unknown wear and tuning. Highest weight, because one failed rig can sink a concept, and because it is the cheapest complexity to remove |
| S5 | **Handling events per 4-person meal** (C3 X4 normalisation) | a | 10 | REL-001 counts interventions; at 10⁻⁴ per event, 100 events use half the budget |
| S6 | **Series chain**: distinct mechanisms that must all work for a typical dinner (B3); single points of failure are listed with it | a | 7 | Reliability of a chain is the product of its links (2.3) |
| S7 | **Custom part types**: machine assemblies plus ware and tools made to drawing | c, d | 8 | C3: custom stainless is the dominant cost and lead-time item. #21 allows it, but each type is still a drawing, a supplier and a spare |
| S8 | **Loose ware items** picked up by the machine, including cookware | b, c, e | 5 | Each item is washed, stored, tracked and inspected. Storage takes room |
| S9 | **Food-contact part types with crevices, hinges, threads, elastomers or joints**; a fixed flexible food surface counts +3 (belt) or +6 (mats and anvil) | b | 6 | C2's main source of hygiene risk that cannot be verified by eye |
| S10 | **Cleaning stations**: distinct wash systems or points inside the cell, plus an external chamber if the cell needs one for its ware (the dish washer is common to all and not counted) | b, a, c | 6 | Each is pumps, valves, nozzles, heaters and a validation |
| S11 | **Special fabrication processes** beyond job-shop laser cutting, bending, welding and polishing (#21): welding on clad walls, wire-EDM, spinning, deep drawing, moulded silicone on steel, bellows, refrigerant brazing | c, d | 3 | Few suppliers, long lead times, metallurgical risk. Low weight now that #21 allows welding |
| S12 | **Software skills**, counting skills that need closed-loop vision on deformable food twice (C3 X8) | a, d | 4 | Software is the part that is never finished; vision on wet food is its hardest part |
| S13 | **Repair in an hour**: can a trained technician understand the fault, find it and fix it in one hour? Judgement 1–10 | a, d | 4 | Conceptual simplicity; MNT-002 |
| | | | **100** | |

Reason (a), reliability, appears in 10 of 13 metrics and carries about 70 % of the weight. That is deliberate: it
is the customer's first reason, and REL-001 (98 % of meals without help) is the requirement the concepts are
furthest from. Size (e) is not scored here: it is an outcome that C4 measures (width), and scoring it twice would
double-count it.

### 2.2 Normalisation

Every count is scored on an **absolute** scale between two anchors: 10 = what a deliberately simple machine needs,
1 = the level at which the metric alone makes the machine unmanageable. Between the anchors the score is
logarithmic, `s = 10 − 9 · ln(x/x₁₀) / ln(x₁/x₁₀)`, clamped to 1…10. Counts that can be zero are shifted by +1. A
logarithmic scale is used because the step from 5 to 10 seals matters as much as the step from 10 to 20.
Absolute anchors (instead of best-in-class) let round-P5 hybrids be scored on the same scale.

| Metric | Anchor 10 | Anchor 1 |
|---|---|---|
| S1 actuators | 8 | 40 |
| S2 seals (+1) | 0 | 25 |
| S3 mechanism types | 5 | 20 |
| S4 novel mechanisms (+1) | 0 | 12 |
| S5 events | 40 | 200 |
| S6 series chain | 4 | 16 |
| S7 custom types | 20 | 100 |
| S8 loose items | 25 | 150 |
| S9 crevice types | 4 | 25 |
| S10 cleaning stations | 1 | 8 |
| S11 special processes (+1) | 0 | 7 |
| S12 skills + vision skills | 15 | 70 |

### 2.3 Why series reliability is a simplicity measure

Suppose each mechanism in the chain fails unrecoverably once in about 700 meals (p = 0.15 % per meal [E]). Suppose
also that each handling event fails unrecoverably at 10⁻⁴ (C3 X4, form-fit grips after a retry). Then the
fraction of meals that finish without help is:

| | Chain N | Events E | (1 − 0.0015)^N | (1 − 10⁻⁴)^E | Together [C] |
|---|---|---|---|---|---|
| K1 | 12 | 190 | 98.2 % | 98.1 % | 96.4 % |
| K2 | 9 | 90 | 98.7 % | 99.1 % | 97.8 % |
| K3 | 12 | 85 | 98.2 % | 99.2 % | 97.4 % |
| K4 | 11 | 95 | 98.4 % | 99.1 % | 97.4 % |
| K5 | 13.5 | 90 | 98.0 % | 99.1 % | 97.1 % |
| K6 | 10 | 115 | 98.5 % | 98.9 % | 97.4 % |
| K7 | 10 | 145 | 98.5 % | 98.6 % | 97.1 % |
| K8 | 10 | 120 | 98.5 % | 98.8 % | 97.3 % |
| S-min | 6 | 65 | 99.1 % | 99.4 % | **98.5 %** |

None of the eight reaches REL-001's 98 % with these modest assumptions. Food-process failures (torn pancakes,
opened rolls) are not even counted yet. The simple reference reaches it with a small margin. The absolute
figures are soft; the conclusion is not: **at this reliability level, every mechanism and every 50 events
removed is worth about half a percentage point of REL-001.**

---

## 3. Raw counts

Corrections to C3's normalised table (C3 §4) are marked ✱.

| Count | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 | Source |
|---|---|---|---|---|---|---|---|---|---|
| Motion actuators stated | 17 (20 with dock tilter, vibrator, oven door) | 21 | 35 | 26 | 25 | 16 | 24 | 16 ✱ (19 with the egg module, which K5 and K7 count) | [D §7] |
| S1 Actuators, cell-normalised | 17 | 15 | 25 | 20 | 16 | 12 | 17 | 13 | C3 §4 |
| Of which in manipulators | 15 | 6 | 8 | 6 | 5 | 6 | 5 | 8 | C3 §4 |
| Moving wall penetrations | 11 | 8 | 19 | 22 | 12 | 12 (+ manipulator seals) | 14 | **0** | [D §2] |
| S2 Dynamic seals, bands, bellows | 13 | 8 | 19 | 22 | 10 | 7 | 8 | **0** | C3 §4 |
| S3 Distinct mechanism types [E] | 10 | 11 | 13 | 12 | 14 | 12 | 15 | 13 | extraction |
| S4 Independent novel mechanisms [E] | 7 | 7 | 7 | 8 | 9 | **4** | 10 | 8 (3 decided by one magnet rig) | risk lists [D §10] |
| S5 Handling events per meal | ~190 | ~90 | ~85 | ~95 + 300–900 mat strokes | ~90 | ~115 | ~145 | ~120 | C3 §4 |
| S6 Series chain, B3 | 12 | 9 | 12 | 11 | 13–14 | 10 | 10 | 10 | [D §5 B3] |
| Single points of failure | 4 (T3, BT, dock, wash-down) | 3 (Wender, K/H, dock) + 14 single-instance ware types | 3 (drum, shuttle head, dock) + 4 partial | 5 (arm B, arm C, dock, blade, gate) | ~7 (shuttle, ram, turret, carousel, face rotor, dock, wash kit) | ~5 (manipulator, wash pump, press, sink drain, dock) | ~6 (gantry, press, sink, slot washer, dock, P4) | ~6 (door gantry, wash system, T, glass plate, hatch, dock) | [D §9] |
| S7 Custom part types | ~86 | ~67 | ~65 | ~48 | ~39 ✱ (dies included: 30 loose types + 9 assemblies [D §7]; C3 counted the dies twice) | ~85 | ~52 | ~45 | C3, [D] |
| S8 Loose ware items | ~110 | 76 | 46 | 41 ✱ (36 items + 5 mats [D §2.4]) | ~96 | 93 | **132** | ~70 | C3, [D] |
| S9 Crevice/elastomer types (+ flexible surfaces) | 18 | 14 | 16 + 3 belt = 19 | 14 + 6 mats = 20 | 14 | 14 | 14 | 15 | [D §6] |
| S10 Cleaning stations | 5 + chamber = 6 | 5 + D7 = 6 | 5 + chamber = 6 | 4 + chamber = 5 | 5 points + chamber = 6 | 3 (2 wells, jet gate, bay wash on one pump) | 4 + chamber = 5 | **2** (jet gate + spray system, one pump set) | [D §6] |
| Materials and processes, all | ~14 | ~12 | ~13 | ~13 | ~15 | ~12 | ~15 | ~14 | extraction |
| S11 Special processes (after #21) | 3 (weld on clad, EDM grids, silicone on steel) | 5 (clad cans, EDM, spinning, silicone, bellows) | 3 (clad spun drum, TPU belt splice, silicone) | 2 (silicone on aramid mats, skived film) | 3 (clad skirts, EDM dies, silicone) | 3 (clad pot skirts, EDM grids, silicone) | 5 (EDM, pressed trays, silicone, bellows, R290 brazing) | 4 (EDM grids, deep-drawn thimbles, silicone, potted magnets) | C3 X2 |
| S12 Skills (vision on deformable food) | 38 (12) | 25 (5) | 30 (6) | 30 (6) | 22 (4) | 45 (10) | 35 (8) | 35 (10) | C3 X8 |
| S13 Repair in an hour [E] | 2: 15 coordinated axes in a ceiling room, about 25 valves | 6: discrete stations, passive ware; the Wender is the hard unit | 3: each module is familiar, the interactions are not | 4: drives easy, process faults (tracking, release) not | 3: 8 kN ram behind guard locking, coaxial under-deck shafts | 8: standard axes, swappable chuck, commercial washer parts, front access | 3: refrigeration needs a certified technician | 6: drive swaps the easiest of all; gap and friction faults hard to diagnose | extraction |

Notes on the counts.

* **S4 counts research projects, not risks.** Examples: K8's puck drive, skid friction and heat at the pucks are
  three findings that one €300–1 000 rig decides, so the 8 is soft at the low end. K7's 10 includes four food
  results (frying from crust-frozen, flour before freezing, ice-weld seam, frozen-puck dosing) that need cooking
  trials, not rigs. K6's 4 are: the one-sided pair grip, the 100 s hanging-ware wash, the spinning-fork peeler and
  the turning ring through a 2 mm gap. Its tang grip in soil needs a reliability rig, but nothing new in physics.
* **S3 counts types.** K1's three turrets are one type. K2's press-on-hob counts as three: quill press, annular
  turntable, tip cradle.
* The counts were made **before #25**. Every concept will host the shared generic peeling module that is being
  designed. A concept that can host it on an existing axis (K1, K6, K7, K8, partly K3) adds no actuator. One that
  cannot (K2, K4, K5, per C1) must add a nest or a station.

---

## 4. Scores

### 4.1 Normalised scores per metric

| Metric | w | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 | S-min |
|---|---|---|---|---|---|---|---|---|---|---|
| S1 actuators | 10 | 5.8 | 6.5 | 3.6 | 4.9 | 6.1 | 7.7 | 5.8 | 7.3 | 9.3 |
| S2 dynamic seals | 12 | 2.7 | 3.9 | 1.7 | 1.3 | 3.4 | 4.3 | 3.9 | **10.0** | 5.1 |
| S3 mechanism types | 10 | 5.5 | 4.9 | 3.8 | 4.3 | 3.3 | 4.3 | 2.9 | 3.8 | 8.8 |
| S4 novel mechanisms | 15 | 2.7 | 2.7 | 2.7 | 2.3 | 1.9 | **4.4** | 1.6 | 2.3 | 6.1 |
| S5 events per meal | 10 | 1.3 | 5.5 | 5.8 | 5.2 | 5.5 | 4.1 | 2.8 | 3.9 | 7.3 |
| S6 series chain | 7 | 2.9 | 4.7 | 2.9 | 3.4 | 2.1 | 4.1 | 4.1 | 4.1 | 7.4 |
| S7 custom types | 8 | 1.8 | 3.2 | 3.4 | 5.1 | 6.3 | 1.9 | 4.7 | 5.5 | 7.7 |
| S8 loose items | 5 | 2.6 | 4.4 | 6.9 | 7.5 | 3.2 | 3.4 | 1.6 | 4.8 | 7.0 |
| S9 crevice types | 6 | 2.6 | 3.8 | 2.3 | 2.1 | 3.8 | 3.8 | 3.8 | 3.5 | 6.6 |
| S10 cleaning stations | 6 | 2.2 | 2.2 | 2.2 | 3.0 | 2.2 | 5.2 | 3.0 | 7.0 | 7.0 |
| S11 special processes | 3 | 3.6 | 1.9 | 3.6 | 4.9 | 3.6 | 3.6 | 1.9 | 2.7 | 7.6 |
| S12 skills | 4 | 3.0 | 6.0 | 4.9 | 4.9 | 6.8 | 2.4 | 3.8 | 3.6 | 6.0 |
| S13 repair in an hour | 4 | 2.0 | 6.0 | 3.0 | 4.0 | 3.0 | 8.0 | 3.0 | 6.0 | 8.0 |
| **Simplicity score** | 100 | **3.1** | **4.3** | **3.5** | **3.8** | **3.9** | **4.5** | **3.3** | **5.1** | *7.1* |

### 4.2 Robustness of the simplicity ranking

| Method | Ranking |
|---|---|
| As above (weighted, absolute log anchors) | K8 5.1 > K6 4.5 > K2 4.3 > K5 3.9 > K4 3.8 > K3 3.5 > K7 3.3 > K1 3.1 |
| Equal weights for all 13 metrics | K8 5.0 > K6 4.4 > K2 4.3 > K4 4.0 > K5 3.9 > K3 3.6 > K7 3.3 > K1 2.9 |
| Relative min–max scale among the eight (linear) | K6 7.3 > K8 7.2 > K2 6.9 > K5 5.5 > K4 5.3 > K3 4.6 > K7 4.5 > K1 4.4 |
| Hardware only (S1, S2, S3, S7, S9, S10, S11) | K8 6.3 > K6 4.6 > K5 4.2 > K2 4.1 > K7 3.9 > K1 3.6 > K4 3.5 > K3 2.9 |
| Novelty weighted twice (S4 = 30) | K8 4.7 > K6 4.4 > K2 4.1 > K5 3.6 > K4 3.6 > K3 3.3 > K7 3.1 > K1 3.0 |

The top three (K8, K6, K2) and the bottom two (K7, K1) are the same under every method. Only the relative scale
puts K6 a hair ahead of K8. K5, K4 and K3 swap places in the middle within 0.4 points.

### 4.3 Justification per concept

| | Score | Justification |
|---|---|---|
| K8 | **5.1** | Simplest hardware by far. Zero dynamic seals, the fewest manipulator-independent stations, one integrated washing system, all drives dry and reachable from the room. Pulled down by 8 independent unknowns (puck drive, skid tribology, screw cassette, swept paddle in GN, jet-gate wash, skin flatness, wall-leaning kneading, pincer), 120 events and 35 skills: the simplicity is real in the machine and borrowed in the software and the ware |
| K6 | **4.5** | Fewest novel mechanisms (4), fewest actuators (12), best repairability, only three cleaning points. Pulled down by logistics: 85 custom types, 93 loose items, 115 events and 45 skills. "Simple parts, many of them" |
| K2 | **4.3** | Few events (90), discrete stations, passive ware, a fair repair case. Pulled down by 7 novel mechanisms (inverter on the lift, hot rim-to-rim flip, cold sheet, apron Rouladen, wash lathe with flash, hourglass dock, press on a hob), 5 washing points and 5 special processes (clad cans with welded rim spools) |
| K5 | **3.9** | The column itself is simple (7 actuators). The cell around it is not: 14 mechanism types, the longest chain (13–14 for B3), ~7 single points of failure, 9 novel mechanisms (plunger kneading, dashers, iris peeler, frying book with fat, microtome carving …) |
| K4 | **3.8** | Few loose parts and custom types. But all of its defining mechanisms are novel (8), it has 22 rotary passages (the most) and 10 m² of elastomer food surface |
| K3 | **3.5** | The most actuators (25 normalised, 35 stated) and 19 seals; 13 mechanism types; two process lines and two hidden manipulators in one shaft |
| K7 | **3.3** | The most novel mechanisms (10), the most mechanism types (15), the most loose items (132) and a refrigeration circuit that needs a certified technician. Its defining station is not used in B3 or B4 |
| K1 | **3.1** | 190 events, 30–45 bayonet tool changes, 15 servo axes in three hands, a 7.3 m seam that is a research project of its own, and the hardest repair case |

---

## 5. Simplicity opportunities per concept (the three largest)

Savings are counted against section 3. "Coverage cost" is in corpus meals, using C1's standard and C1's
mechanism-to-meal mapping [E]. Under #26 a lost meal is worth far more than an adapted one (finding 5).

### 5.1 Across all concepts first

| # | Simplification | Saves | Coverage cost |
|---|---|---|---|
| A1 | **The manipulator tips the opened box over a weighing cup in a dry corner**, instead of a dedicated tipper dock. Lid off and on at a lid station outside the cell (C4 R-4). Powders by scoop-trim (G-assembly GA-39) | 2–6 actuators, 1–2 seals per concept | none; some time per dose |
| A2 | **Passive egg fixture** (bottom strike and hinge-open in a cup, slotted saucer, per-egg camera check; G-assembly 7.2/7.3), worked by the manipulator or the press | 3 actuators per concept | none; ≤ 3 meals move to whole-egg recipes (R-11, class b) |
| A3 | **Three heated positions, not four** (COK-002 M, possible since #19); two of them turning | 1 position, 1 turntable, 250–300 mm | none for ≤ 4 persons (COK-002 rationale) |
| A4 | **No wash-down by a manipulator-held lance**; fixed nozzles and a drying fan in the splash zone | one skill set and many moves (K1, K2, K5) | none |
| A5 | **One bought commercial washer** (2–4 min cycle, 85 °C rinse, robot-loaded) for all ware the cell does not keep, instead of a concept-specific wash device (lathe, slot washer, wells, kit) | 1–4 cleaning stations, 1–3 actuators | none; needs the hygiene ruling on one washer for ware and dishes (C4 9.2c) |

A1 + A2 alone remove 5–9 actuators from **every** concept. Together they are larger than any single
concept-specific simplification below.

### 5.2 Per concept

| | 1st | 2nd | 3rd | After all three [E] |
|---|---|---|---|---|
| K1 | **Two turrets instead of three** (the explorer's own variant, [D §7]): −5 axes, −4 seals, ~−10 custom types; B2 and B6 run over time, B1 +15 min. Cost: 0 meals | **A deck hatch to the washer** instead of relays [D A3]: −70 relay moves | **Delete tools used in under 6 % of meals** (cone roller, mandrel, rounding cups, air corer, Spätzle slider): ~−8 types, −15 items, −2 novel mechanisms. Patties are formed by the press tube, Rouladen by the GA-20 raft | 12 axes, 9 seals, 5 novel, ~105 events: still the weakest base; K1 survives only as its passive-tool rule and its "everything retracts before the door opens" rule |
| K2 | **Replace the wash lathe and flash with the bought washer** (A5): −2 actuators, −1 seal, −1 induction coil, −1 novel mechanism; ware stock about ×1.5. Cost: 0 meals | **Drop the cold sheet and the apron/trough Rouladen chain**; use the GA-20 raft and slicing from the block: −4 types, −2 novel. Cost: 0 meals | **A1 instead of the hourglass dock** (5 actuators for dosing alone): −4 actuators, −2 seals | 9–10 actuators, 5 seals, 4 novel: a simple cooking side, but it still cannot place a piece or host the peeling module (C1 K2-1) |
| K3 | **Delete the belt, G1 and G2** (the explorer's own fallback [D §11.2]): −10 actuators, ~−9 seals, ~−12 types, −4 novel mechanisms and C2's worst hygiene surface. Rouladen, breading, sheeting and carving then need a manipulator: ~20–25 meals are adapted or lost unless a bench is added | **Spin only at low charge, or drop the spin function**: removes the 35 kg imbalance case, isolation mounts and the spin noise. Salad spin moves to a basket on a spindle. Cost: 0 meals | **A1 and pastes as pucks**: −3 actuators, −1 seal | ~12 actuators, ~9 seals: a drum on a shuttle, which needs a hand next to it, i.e. a different concept |
| K4 | **Reduce K4 to its own 11-drive flat module** [D §11.3]. It cannot reach 93 % alone (C1: 84 %) and needs another concept's hand and hob anyway | **Drop mats P and R** (mesh and rasp, the first to fail hygiene, [D §6.5]): −2 reels, −2 seals | **Replace the three disc-knife rollers by the press tube**: −3 crevice types, −1 novel mechanism | Not a base. The mat remains only as an optional sheeting station, if test R1 passes |
| K5 | **Knead and whisk in the can on the existing ring drive** (the explorer's fallback [D §4.3]): −2 actuators, −1 rod seal, −5 dasher types, −3 novel mechanisms (plunger kneading, dasher whip, mesh purée), and a better cake (C1 K5-4). Cost: 0 meals | **Fix the carousel to the turret** (no shear gate; the shuttle swaps dies): −1 actuator, −1 seal, −1 novel; +2–4 moves | **Drop the frying book; pan-pair flip under the G-assembly rules, plus a turner and lift rack**: −2 actuators, −2 seals near fat, −1 novel. Also drop the iris peeler, duckbill and microtome carving; move the oven out [D §1.3]: −600 mm | ~18 actuators (cell ~11), 5–6 seals, 4 novel. The column becomes a module (the press in section 7), not a base: whole heads and peeling still need a hand |
| K6 | **Let the manipulator push the well lids; passive sink strainer**: −3 actuators. Cost: 0 meals | **Take K5's Ø 80 former into the press tube**: 93 → ~84 items, 90 → 72 B3 cycles [D §11.3]; and **drop bench B2**: −345 mm | **Drop the wrist spin** (the 6 000 rpm axis and its two lip seals over food) and put one canned high-speed spindle in the deck (K8 S principle) for blender, chopper, whisk, spinner and zester: −2 seals over food, 0 actuators net. Also **replace the hook-hinged egg cracker** by A2 (C2's worst cassette) | ~10 actuators, ~3–4 seals, 3 novel, ~80 items: the basis of S-min (section 7) |
| K7 | **Drop the cold cabinet and refrigeration**, or keep one bought anti-griddle as an option: −2 actuators, −2 rod passages, −1 certified-technician process, ~−20 cold-ware parts, −5 novel. Cost: 3–5 meals lose their best method; about 0–2 lost (cordon bleu, croquettes, flat pockets become adapted) | **Replace the slot washer** with A5: −1 actuator, −1 tank and steam, −1 novel | **Two turning hob positions instead of four; the bow knife becomes a passive draw-knife or twin-blade tool**: −3 actuators, −2 rings, −1 bellows at 45 Hz | ~11 actuators, ~5 seals: it becomes K6 with K7's under-deck press, which is what C3 recommends |
| K8 | **Oven out of the tub** (transport-served column, or beside it; #24 allows modification): −1 actuator, −600 mm. Cost: 0 meals | **Drop the Y-slide, the sheet dispenser and the grater** (few-meal parts): −4 custom types, −1 novel. Carving quality falls in ~12 meals, none lost | **Drop the speed spindle S only if the press cassette PZ takes purée and mince**: −1 actuator, −1 thimble. Quality falls in 20–35 meals, none lost. *Not recommended*: S is the cheapest high-coverage drive (section 6.1) | ~14 actuators, 0 seals, 7 novel. The magnets cannot be simplified, only decided by the rig |

---

## 6. Coverage per unit of complexity

### 6.1 Sub-mechanisms ranked

C1 §7 ranks mechanisms by meals carried. C3 §7 ranks them by robustness per cost. Here both are combined with the
complexity each mechanism adds, measured in **complexity units (CU)**: actuators + dynamic seals + 3 × novel
mechanisms + 0.1 × custom part types. It is assumed that the host already has a manipulator with a roll axis
(every surviving base has one). "Meals" means C1's operation counts (overlapping, [C1 §7]). The "unique" column
says whether the meals depend on this mechanism or merely use it.

| Rank | Mechanism | Meals carried | + Act. | + Seals | Novel | + Types | CU | Meals/CU | Unique? | Verdict |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Recipe routes that remove operations**: cook in skin, slip or rice (GP-P1, R-09); "do not trim" rules (GP-101); sprigs in an infuser (GP-22); leek sliced before washing | ~50 PLP + ~15 | 0 | 0 | 0 | 0–1 | ~0 | very high | yes | **take all**: free simplicity |
| 2 | **Core probe** placed by the manipulator | ~30 (steak, roasts, mince, poultry) | 0 | 0 | 0 | 1 | 0.1 | ~300 | yes (MEAL-015, FSF) | keep |
| 3 | **Fork-spit, sprung peeler, knife and comb fence on the manipulator's roll axis**; this is where the generic peeling and stoning module of #25 belongs | ~90 (PLP 60, PLS 26, COR 18, CAR 12) | 0 | 0 | 1 | 6 | 3.6 | ~25 | yes | keep, as the generic module |
| 4 | **Two turning hob positions** with hung scraper and kneading roller, **canned magnet drive** (K8 principle, no seal) | ~110 (STC/SAU 100, KND 29) | 2 | 0 | 0 | 4 | 2.4 | ~45 | partly (frees the manipulator) | keep |
| 5 | **One canned high-speed spindle** in the deck: blender cup, chopper cup, whisk, salad-spinner basket, zester drum | ~45 (purée soups, pesto, hummus, mayonnaise, cream, egg white, herbs, salad) | 1 | 0 | 0 | 5 | 1.5 | ~30 | yes for emulsions and whipping | keep |
| 6 | **Press tube with end plates under a pull-down press** (K7 structure, two rods in tension, 3 kN): bought push-dicer grids, slicer, ricer, Spätzle, garlic, patty orifice, corers, **and a slot die for pasta sheets** | ~120 distinct (DIC 106, SLI 70, MSH 9, FRB, garlic, EXT) | 1 | 2 | 0 | 10 | 4.0 | ~30 | partly (a knife can dice, slowly) | keep |
| 7 | **Loose-floor moulds and lined tins** (K5, paper liners SM-204) | UNM 11 | 0 | 0 | 0 | 3 | 0.3 | ~37 | yes | keep |
| 8 | **G-produce small set** (plug corer and four cheeks, snipper basket, cone cut, dunk basket, zester) | ~60 (pepper 27, citrus 35, florets, beans, gritty leaves) | 0 | 0 | 0.5 | 9 | 2.4 | ~25 | yes | keep, fold into the #25 module where possible |
| 9 | **GA-20 raft** for Rouladen, **GA-36 lift rack** for Schnitzel in 200–250 mL fat, matched pans for the pan-pair flip | DM02 (brief), FLP 32, BRD | 0 | 0 | 1 | 6 | 3.6 | ~12 | yes (brief meals, staples) | keep |
| 10 | Form-fit tang with pins plus load pins in the jaws | every handling event | 0 | 0 | 0 | 1 | 0.1 | n/a | — | keep: it makes events cheap |
| 11 | Frying book (K5) | 0 beyond rank 9 | 2 | 2 | 1 | 2 | 7.2 | 0 | no | drop |
| 12 | Drum with spin and tilt (K3) | 7 stir-fries already mandated (b); mince browning | 3 | 2 | 1 | 6 | 8.6 | < 1 | no | drop; agitated pan on a turning position |
| 13 | Cold plate stack with refrigeration (K7) | ~12 better, ~0 more meals (C1 10.2) | 2 | 2 | 3 | 20 | 15 | < 1 | no | drop; option: bought anti-griddle |
| 14 | Wash lathe with induction flash (K2) | 0 (cleaning) | 2 | 1 | 1 | 2 | 6.2 | — | no | replace by bought washer |
| 15 | Hourglass or tipper dock with 5–6 actuators | 0 if the manipulator tips | 5 | 2 | 1 | 4 | 10.4 | — | no | replace by A1 |
| 16 | Belt with nose and guillotine (K3) | +0–2 | 10 | 9 | 4 | 12 | 32 | < 0.1 | no | drop |
| 17 | Mat line (K4) | +1–3 if sheets are needed (C1 10.2) | 11 | 9 | 8 | 15 | 45 | < 0.1 | no | drop; sheeting by the press slot die or a passive pin on a tray |
| 18 | Additional manipulator (K1's third turret, K3's tool arm, K4's arm C) | 0 (time only) | 3–5 | 2–4 | 0–1 | 5 | 6–12 | 0 | no | drop; accept serial work and longer meals |

Two remarks.

* **The press tube is the one place where a little complexity buys a lot.** With a slot die it also makes sheets
  for filled pasta. IT17 tortellini (weight 3) and DM33 Maultaschen are mandated class (c) in "simple square
  shape", and #26 still forbids buying them. A pasta extruder is household and catering practice; a pressed
  pizza base is not (C1 K2-5, K5-3). So the slot die is for pasta and wrappers, not for pizza.
* **Generic before specific (#25).** One spit with a sprung blade and a depth shoe, a knurled drum on a turning
  position, and a stone-coring tube in the press cover most of the peeling and stoning family (potato, carrot,
  apple, cucumber, kiwi, mango cheeks, avocado halves and pit, citrus, banana slit-and-pull). Single-purpose
  devices for one fruit (iris peeler, rasp can, vertical poultry stand) should not return.

### 6.2 Costly mechanisms that serve few meals — candidates for the 5 %

Under #26 only 2–3 meals may be *lost*. So the right move for these mechanisms is "replace by an adaptation". Only
the last column may be lost.

| Mechanism (concept) | Complexity | Meals that need it | Replacement and class | Meals lost |
|---|---|---|---|---|
| Cold plate and refrigeration (K7) | 2 act., 2 passages, R290, ~20 parts | ~12 for best method; none uniquely (C1) | chill on a tray in cold storage (R-02, a); breading limp | 0–1 (cordon bleu if crimping fails) |
| Mat sheeting and wrapping (K4) | 11 act., 9 seals | ROL/SHD 16, WRP 10 | rolling pin on a tray, press slot die, served as components (MEAL-020) | 0–1 (burrito fold) |
| Belt carving and guillotine (K3) | 10 act., 9 seals | CAR 12 | knife and comb in a V-trough with a twin blade (GA-14) | 0 |
| Frying book (K5) | 2 act., 2 seals | flip subset | pan pair ≤ 30 mL fat (R-03, a), turner, lift rack | 0 |
| Drum spin (K3) | isolation, noise | salad spin, peel | spinner basket on the deck spindle; GP-P1/P2 | 0 |
| Iris peeler, microtome carving, duckbill (K5) | dies, 1 novel each | carrots, hot roast, piping | spit peeler; chill-slice-reheat (R-02); squeeze tube | 0 |
| Vertical poultry split stand (G-assembly) | stand set | DM20, ME10 | poultry as parts (R-06, b) | 0 |
| Dedicated egg separation cassette | cassette | SEP 17 | slotted saucer (passive); whole-egg method (R-11, b) | 0 |
| Whole cabbage leaves GP-71 | freeze–thaw route | DM12 | keep: passive, uses cold storage | 0 |
| Folded or pleated wrappers (samosa, gyoza, spring roll) | sheeting + folding, novel | IN07, AS08, AS09 | square parcels (R-10, c) if sheets come from the slot die | 1–3 |
| Banana, avocado (now #25) | the shared generic module | MX06, CK16, DS10 | generic slit-and-pull, halve-and-pit | 0–1 |

The honest 7 % (#26) is therefore dominated by the meals already excluded (requirements 5.4) plus the
folded-wrapper family. No costly station has to be built to save it.

---

## 7. The simplest machine that should reach 93 % (reference "S-min")

This is a sketch for round P5, not a concept: it shows what the simplicity score rewards and gives P5 a target to
beat. It is built only from parts that C1, C2 and C3 rank highest. It is a K6 skeleton with K8's seal-free drives,
K7's press structure and a bought washer.

| Element | Choice | Source | Actuators | Seals |
|---|---|---|---|---|
| Manipulator | Cartesian gantry in dry boxes, X-Y-Z, **one roll axis**, gripper with form-fit tang and pins, load pins in the jaws. No wrist spin, no tilt | K6, K2, K8 (roll only) | 5 | 3 (bands) |
| Heat | 3 induction positions (COK-002 M); 2 of them with a **canned magnet turntable**, hung scraper and kneading roller | K8 T, C3 rank 1 | 2 | 0 |
| Force | **Pull-down press** under the deck, 3 kN, two rods in tension; loose Ø 110 tube; bought push-dicer grids; ricer, Spätzle, garlic, corer, patty and slot-die plates | K7, K5, K6 | 1 | 2 |
| Speed | **One canned high-speed spindle** in the deck: blender, chopper, whisk, spinner, zester, generic-peeler drum | K8 S | 1 | 0 |
| Produce | the shared generic peeling and stoning module (#25) on the roll axis and the spindle; G-produce set | #25, G-produce | 0 (target) | 0 |
| Dosing, egg | A1 (gantry tips the opened box over a weighed cup in a dry corner), A2 (passive egg fixture) | section 5.1 | 0 | 0 |
| Oven | bought combi-steam oven, modified for an automatic door (#24), loaded by the gantry | #24 | (1, not counted) | 0 |
| Washing | **one bought commercial washer** for all ware (and dishes, if ruled); fixed spray nozzles and a fan for the splash zone | C4 R-10, A5 | 0 | 0 |
| Ware | ~45 items: bought GN thermoplates and round pans with a welded tang, matched pair, lift rack, raft, turner, knife, comb fence, spit, tongs, ladle, probe, ~10 press plates, red duplicates | K6, G-assembly | — | — |
| **Total** | 6 mechanism types, ~30 custom types, ~25 skills (5 with vision), 2 novel (one-sided tang grip in soil; spit peeling of the generic module) | | **9** | **5** |

Expected properties [E]: about 65 handling events per meal; a series chain of 6 for B3; repair in an hour (8).
Simplicity score **7.1**. Coverage: C1's hybrid H1 (230–231 meals) is the same kit minus K6's wrist spin
(replaced by the deck spindle). With #25's generic module it should reach **231–233 = 93–94 %**, within the
MEAL-019 adaptation budget. This needs a meal-by-meal check in P5, because the reserve is 2–3 meals.

What it gives up, honestly: speed (one serial hand: four-component menus for four persons will run at the PERF
limit; C1 K1-8, C4 4.1), the K8 enclosure (the frying aerosol is in an open bay that C2 wants washed per meal), and
three sealing bands that a K8-type wall would avoid. If the K8 magnet rig succeeds, the **same station list on a
K8 tub** (pucks instead of the gantry, seal-free) is the simpler variant in hardware: 0 seals and one washing
system, but 4–6 more novel mechanisms. This is the one comparison P5 must settle with evidence.

---

## 8. Customer decisions that most affect simplicity

Ordered by how much machine each answer can remove.

| # | Question | If "yes" | Saves [E] |
|---|---|---|---|
| Q1 | May **one bought commercial washer** clean the cell's ware *and* the household's dishes, glasses and boxes, given an 85 °C disinfecting rinse and raw-meat ware washed in its own cycle? | one washing system for the whole machine | 1 washer (600 mm), 1–4 cleaning stations |
| Q2 | Is a **single serial manipulator** acceptable if menus with four hot components for four persons take up to the PERF-001 limit (or 10–15 min more), and if some preparation is done ahead in idle hours (potatoes boiled in the morning, stock at night)? | no second hand, no relays | 3–6 actuators, 2–4 seals |
| Q3 | Are **adapted methods within the MEAL-019 budget** acceptable as the default way to simplify (oven-finished Frikadellen, untied Rouladen on a raft, poultry as parts, whole-egg sponges, square pasta parcels), so that P5 removes a station whenever a class (a)/(b) route exists? | stations removed instead of built | 1–3 stations |
| Q4 | **IT17 tortellini (weight 3) and DM33 Maultaschen**: since they may not be bought (#26), may they be machine-made as square parcels from slot-die sheets (mandated c), or may IT17 be exempted from MEAL-003? | no sheeting or folding station | 0 if made by the press, otherwise one novel station |
| Q5 | **Oven position** (#24): inside the cell, loaded by the gantry, or a front-facing column served by the transport? | one less oven-door axis, ~600 mm shorter cell | 1 actuator, width |
| Q6 | May the **transport serve the cell's washer and oven**, while the cell keeps its internal handler (C4 R-1)? | fewer cell-internal moves | ~20–40 events per meal |
| Q7 | **Lid handling outside the cell**: may ingestion or a lid station deliver boxes open and pastes in an opened pack, so that the cell needs no dock mechanism (A1)? | no dock | 2–6 actuators, 1–2 seals |
| Q8 | Is a **closed tub with temporal raw/RTE separation** (K8) acceptable as a hygiene principle, if the rig confirms the magnets? It decides whether the zero-seal variant can be pursued | the K8 variant of S-min | 3–5 seals |

---

## 9. Open issues and limits of this critique

1. The counts S3, S4, S9 and S13 are judgements made with a defined rule. Another critic would land within ±1–2
   per concept. The ranking test in 4.2 shows that the ranking survives such changes.
2. S-min's counts are targets, not results. It is scored only to show the scale; it must be explored and
   critiqued like K1–K8 before its 7.1 means anything.
3. All counts predate #25. The shared generic peeling module will add the same few parts to every concept; it
   changes the ranking only for concepts that cannot host it (K2, K4, K5).
4. Requirements 5.6 permits peeled garlic cloves; C1's standard N counted them as forbidden. If 5.6 stands, C1's
   garlic penalty on K3, K4 and K8 shrinks. This does not change any simplicity count.
5. Simplicity is scored here for the cell. The common modules (storage, transport, dish handling, drinks) are out
   of scope, but they are where Q1, Q6 and Q7 would save the most.
