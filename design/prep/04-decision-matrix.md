# Meal preparation — integrated decision matrix after round P4

Combines the five critiques of round P4 into one ranking:

* C1 coverage and food result (`critique/C1-coverage-food.md`)
* C2 hygiene and cleanability (`critique/C2-hygiene.md`)
* C3 mechanics and reliability (`critique/C3-mechanics-reliability.md`)
* C4 system fit and operations (`critique/C4-system-fit.md`)
* C5 simplicity, DECISIONS #20 (`critique/C5-simplicity.md`)

From these it derives the recommendation for round P5. Author: critic C5. Decision state: DECISIONS #1–26.

---

## 1. Result in brief

* **Ranking, base weights**: K6 5.7 ≈ K8 5.7 > K7 4.7 > K2 4.4 ≈ K5 4.4 > K1 3.9 ≈ K3 3.8 > K4 3.7.
* **K6 and K8 lead under every weight set tried**: 12 named sets, 20 000 random weightings, and ±1 point of noise
  on every critic score. Neither ever falls below second place. Between the two the order flips with the
  weights; the gap (0.06) is far smaller than the scores' own uncertainty.
* **By DECISIONS #20 the simpler one wins a tie, and that is K8** (C5 5.1 against 4.5). But K8's simplicity rests
  on eight untested principles. K6's lower simplicity comes from logistics that can be cut.
* **No concept is good enough to be developed as it stands.** The best total is 5.7 of 10. Every critic found
  fixable but major defects, and the simplest of the eight scores only 5.1 on simplicity, against 7.1 for a
  reference built from their best parts.
* **Recommendation for P5**: develop one **simplicity-first hybrid** in two variants that share one station
  list. **H-S1** uses a gantry and is the base. **H-S2** puts the same stations into a sealed tub with magnetic
  pucks, and is pursued only if the K8 magnet rig passes. The P5 brief gets hard simplicity limits (section 6).
  K1, K3, K4 and K7 stop as whole concepts. K2 and K5 survive as part donors.

---

## 2. Inputs and how decisions #21–26 change them

### 2.1 Scores as reported by the critics

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| C1 coverage and food | 7 | 3.5 | 4.5 | 4 | 3 | 7 | 6.5 | 6 |
| C2 hygiene | 3 | 5 | 3.5 | 3 | 5 | 7 | 5.5 | 6 |
| C3 mechanics and reliability | 3 | 4.5 | 3.5 | 3.5 | 5 | 6 | 4 | 6 |
| C4 system fit | 2 | 5 | 4.5 | 4.5 | 5 | 3.5 | 2.5 | 6 |
| C5 simplicity | 3.1 | 4.3 | 3.5 | 3.8 | 3.9 | 4.5 | 3.3 | 5.1 |

### 2.2 Adjustments for decisions made after the critiques

C1–C4 were written before decisions #21–26 (2026-10-01). Re-scoring them is the critics' job. Here, only the
parts of their justifications that the new decisions remove are taken out, and the change is stated. Section 5
shows that the ranking is the same with and without these adjustments.

| Decision | Effect on the critiques | Adjustment |
|---|---|---|
| #21 job-shop welded and polished stainless allowed | C3 X2 ("every concept fails BLD-002") no longer applies. Welding onto **clad** walls (K2 cans) stays a metallurgical problem; it is a design issue, not a permission issue | none to scores (X2 hit all eight equally); C5 S11 already counts only processes beyond job-shop welding |
| #22 cost is reported, not a gate | C3 X1 and C4 3.5 cost penalties lose weight. They counted most for K1 (40–45 k€), K7 (37–41 k€, "fatal on cost" in C4) and K5 (dies 3× the estimate). K8's advantage as the cheapest concept shrinks | C3: K1 +0.5, K5 +0.5, K7 +0.5. C4: K1 +0.5, K7 +1.0, K8 −0.5 |
| #23 water is reported, not a gate; hygiene first | C4's water verdicts (K1 152 L/day, K3 107, K5 101 against 75) lose weight; K8's lowest-water advantage shrinks. C2's RES-005 "major" was shared by all and weighted lightly | C4: K3 +0.5, K5 +0.5 (the K8 −0.5 above covers its lost cost and water lead). Hygiene weight raised (section 3) |
| #24 a bought oven may be modified | C3 X6 and C4 e ("the oven turned by 90° voids certification") weaken for all eight. The oven still does not fit 540–555 mm of inner depth sideways; that is geometry | none (it applies to all) |
| #25 generic peeling and stoning is a core function | The concepts must host a shared generic module. Those with a hand or a free axis (K1, K6, K7, K8, partly K3) can; K2, K4 and K5 cannot without a new station (C1 3, G-produce 0.3). It recovers MX06 and CK16 (avocado, banana) for the hosts | Coverage gate (2.3); C1 scores unchanged |
| #26 coverage target 93 % | C1's ceiling under #8 was 231 = 93.1 %; with #25 about 233–234. The target is now within reach, but the reserve is only 2–3 meals | Coverage gate (2.3) |

Adjusted scores used in the matrix:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| C3' mechanics and reliability | 3.5 | 4.5 | 3.5 | 3.5 | 5.5 | 6 | 4.5 | 6 |
| C4' system fit | 2.5 | 5 | 5 | 4.5 | 5.5 | 3.5 | 3.5 | 5.5 |

### 2.3 Coverage gate (a base must be able to reach 93 %)

A concept that cannot reach the target even with every module it can host is not a candidate base, whatever its
total. Its good mechanisms can still be borrowed.

| | C1 with hostable modules | + #25 module (if hostable) [E] | Reaches 93 % (231)? | Base? |
|---|---|---|---|---|
| K1 | 230 (229–231) | ~232 | yes | yes |
| K2 | 209 (201–211) | not hostable | no (−20) | **no** — donor |
| K3 | 224 (218–224) | ~225 | no (−6), only with a hand added | marginal |
| K4 | 208 (204–217) | not hostable | no (−23) | **no** — donor |
| K5 | 194 (192–216) | not hostable | no (−37) | **no** — donor |
| K6 | 230 (229–231) | ~232 | yes | yes |
| K7 | 226 (224–228) | ~228 | no (−3); the limp-sheet rule must go | marginal |
| K8 | 227 (225–231) | ~229 | within range (−2) | yes, if the force limits hold |

---

## 3. Weights

| Criterion | Proposed in the P4 brief | **Used (base)** | Why |
|---|---|---|---|
| C5 simplicity | 30 % | **30 %** | #20: "high weight". It is the largest single weight, as the customer asked |
| C1 coverage and food | 20 % | **20 %** | The target is a requirement (MEAL-002), so it is also handled by the gate (2.3). The weight then only ranks the concepts that pass |
| C2 hygiene | 20 % | **25 %** | #23: "Hygiene comes first". The brief calls cleaning "a major consideration"; it is the one dimension a later optimisation step cannot fix |
| C3 mechanics and reliability | 15 % | **15 %** | Kept below its standalone importance because C5 already counts actuators, seals, events and the series chain: about half of C3's content |
| C4 system fit | 15 % | **10 %** | #22 and #23 take cost and water out of the gates, which were two of C4's five budgets. Width overlaps with C5 reason (e). Power, transport, turnaround and modularity remain |

**Double counting, stated openly.** C5 overlaps with C3 (actuators, seals, MTBF), with C2 (crevices, cleaning
stations) and with C4 (width follows actuators). The effective weight of "complexity" is therefore about 40–45 %.
That is consistent with the customer's ruling ("high weight; when close, the simpler one wins"). The sensitivity
check includes a set without C5 at all.

---

## 4. Integrated matrix (base weights, adjusted inputs)

| | Weight | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|---|
| C5 simplicity | 30 % | 3.1 | 4.3 | 3.5 | 3.8 | 3.9 | 4.5 | 3.3 | **5.1** |
| C1 coverage and food | 20 % | **7** | 3.5 | 4.5 | 4 | 3 | **7** | 6.5 | 6 |
| C2 hygiene | 25 % | 3 | 5 | 3.5 | 3 | 5 | **7** | 5.5 | 6 |
| C3' mechanics and reliability | 15 % | 3.5 | 4.5 | 3.5 | 3.5 | 5.5 | **6** | 4.5 | **6** |
| C4' system fit | 10 % | 2.5 | 5 | 5 | 4.5 | **5.5** | 3.5 | 3.5 | **5.5** |
| **Weighted total** | 100 % | 3.85 | 4.41 | 3.84 | 3.66 | 4.39 | **5.74** | 4.70 | **5.68** |
| **Rank** | | 6 | 4 | 7 | 8 | 5 | **1** | 3 | **2** |
| Coverage gate (2.3) | | pass | fail | marginal | fail | fail | pass | marginal | pass (if force holds) |

Reading the matrix:

* **K6 and K8 are a tie.** K6 wins on food, hygiene and repairability. K8 wins on simplicity, seals and system
  fit. Their weaknesses are different in kind. K6's are *logistics*: 93 items, 115 events, 45 skills and 2.6 m,
  and they shrink when stations are simplified (C5 §5.2). K8's are *unknowns*: magnetic force and friction, the
  door path, drives behind a hot skin, and they are decided by experiment, not by design.
* **K7 is third only because of C1 and C2.** Its simplicity (3.3) and system fit are near the bottom. With its
  cold cabinet removed it becomes K6 with a better press (C3 §5, C5 §5.2).
* **K2 and K5 score in the middle but fail the coverage gate.** They are donors: K2's load pins in the jaws and
  rim-to-rim pairs; K5's press tube, ricer, loose-floor moulds and syringes.
* **K1, K3 and K4 are last on simplicity and last overall.** Keep only rules and parts: K1's passive tools and
  "everything retracts before the door opens"; K3's lip-pivot pour geometry; K4's white mat as a vision
  background.

---

## 5. Sensitivity

### 5.1 Named weight sets

Order: C5 simplicity / C1 coverage / C2 hygiene / C3 reliability / C4 system fit.

| Weight set | 1st | 2nd | 3rd | 4th | Rest |
|---|---|---|---|---|---|
| **Base 30/20/25/15/10** | **K6 5.74** | **K8 5.68** | K7 4.70 | K2 4.41 | K5 K1 K3 K4 |
| Brief's proposal 30/20/20/15/15 | K8 5.66 | K6 5.57 | K7 4.61 | K5 4.41 | K2 K3 K1 K4 |
| Equal 20 each | K8 5.72 | K6 5.59 | K7 4.67 | K5 4.57 | K2 K3 K1 K4 |
| Simplicity 40/15/20/15/10 | K8 5.59 | K6 5.49 | K7 4.44 | K2 4.41 | K5 K3 K4 K1 |
| Simplicity 20/25/25/20/10 | K6 5.94 | K8 5.77 | K7 4.92 | K5 4.42 | K2 K1 K3 K4 |
| Coverage 25/35/20/10/10 | K6 5.92 | K8 5.72 | K7 5.01 | K1 4.42 | K2 K5 K3 K4 |
| Hygiene 25/15/35/15/10 | K6 5.87 | K8 5.72 | K7 4.76 | K5 4.54 | K2 K3 K1 K4 |
| Reliability 25/15/20/25/15 | K8 5.70 | K6 5.59 | K5 4.62 | K7 4.56 | K2 K3 K4 K1 |
| System fit 25/15/20/15/25 | K8 5.65 | K6 5.34 | K5 4.62 | K2 4.52 | K7 K3 K4 K1 |
| Without simplicity (before #20) | K6 6.29 | K8 5.93 | K7 5.29 | K5 4.61 | K2 K1 K3 K4 |
| Base weights, **unadjusted** C3/C4 | K6 5.74 | K8 5.73 | K7 4.53 | K2 4.41 | K5 K3 K1 K4 |
| Base weights, C5 stretched to the same 2–7 spread as C1–C4 | K8 6.25 | K6 6.03 | K2 4.62 | K7 4.51 | K5 K3 K4 K1 |

### 5.2 Random tests

| Test | Result |
|---|---|
| 20 000 random weightings (Dirichlet around the base, every weight free to vary roughly ±50 %) | 1st: K6 62 %, K8 38 %. **Top two: K6 and K8 in 100 %** of cases |
| 20 000 runs with uniform ±1 point noise on every critic score, base weights | 1st: K6 56 %, K8 44 %. 3rd: K7 65 %, K2 18 %, K5 16 % |

### 5.3 What the sensitivity says

1. **The pair at the top is robust; the order inside it is not.** Weighting simplicity, reliability or system
   fit more puts K8 first. Weighting coverage, hygiene or C1–C4 alone puts K6 first. A 0.1-point change in any
   single score swaps them.
2. **Simplicity changes the decision only at the top.** Without C5, K6 leads by 0.36. With it, the two are level.
   #20's tie-break rule then points to K8, *provided its simplicity is real*. That is exactly what K8's
   €300–1 000 magnet-and-friction rig decides.
3. **Positions 3–8 change but never reach the top**: no plausible weighting lifts K1, K2, K3, K4, K5 or K7 into
   the top two. That justifies stopping them as whole concepts.
4. The stretched-C5 variant matters: C5's absolute scale compresses the eight into 3.1–5.1, which shrinks
   simplicity's effective influence below its nominal 30 %. Stretched to the critics' usual spread, K8 leads by
   0.2. The recommendation below does not depend on which of the two is first.

---

## 6. Recommendation for round P5

### 6.1 What to develop

Neither K6 nor K8 should simply be developed further. Both carry complexity that their best parts do not need,
and the critics' fixes add more. P5 should develop **one simplicity-first hybrid with a fixed station list, in two
carrier variants**. It is designed from the start for C5's metrics, and it is the "simplest possible machine that
reaches 93 %" asked for (C5 §7, reference S-min).

| | **H-S1 "simple gantry bench"** (base) | **H-S2 "simple tub"** (conditional) |
|---|---|---|
| Carrier | Cartesian gantry in dry boxes, X-Y-Z + one roll axis, form-fit tang grip with pins and load pins (K6, K2) | K8 sealed tub; door gantry with two magnet heads and pucks with roll spindle (K8) |
| Stations (identical in both) | 3 induction positions (COK-002 M), 2 with a canned magnet turntable, hung scraper and kneading roller; one pull-down press, 3 kN, two rods in tension, loose tube with bought push-dicer grids, ricer, Spätzle, garlic, corer, patty and slot-die plates (K7, K5); one canned high-speed spindle (K8 S); the shared generic peeling and stoning module (#25) on the roll axis and the spindle; G-produce set; GA-20 raft, GA-36 lift rack, matched pans, core probe; passive egg fixture; the manipulator tips the opened box over a weighed cup (no dock mechanism) | same; the press acts on a closed cassette through the tub ceiling (C4 H-A) or as K8's screw cassette |
| Washing | one bought commercial washer for ware (and dishes, if ruled); fixed spray nozzles and a fan in the bay | the tub is the ware washer (K8); dishes in the household washer |
| Oven | bought combi-steam oven, modified for an automatic door (#24), outside the bay or at its end | outside the tub (K8 A-1) |
| Target counts (C5 metrics) | ≤ 10 actuators, ≤ 5 seals, ≤ 2 novel, ≤ 6 mechanism types, ≤ 70 events, chain ≤ 7, ≤ 50 loose items, ≤ 35 custom types; C5 ≥ 7 | ≤ 14 actuators, 0 seals, ≤ 6 novel, ≤ 7 mechanism types; C5 ≥ 6.5 |
| Go / no-go | always developed | only if the K8 rig shows ≥ 200 N holding shear, ≥ 12 Nm and acceptable wall wear (C3 rec. 6), and the door has a legal opening path (C3 K8-1) |

Why this pair: H-S1 removes K6's logistics (wells, wrist spin, dock, egg cracker, second bench) and K8's
unknowns, and keeps the parts the critics rank highest (C1 §7 ranks 1–6; C2 R-1 "everything that touches food is
ware"; C3 §7 ranks 1–6). H-S2 is the one variant that could be simpler still in hardware (zero seals). The
customer's tie-break rule obliges P5 to test it rather than drop it.

### 6.2 What stops, and what is borrowed

| Concept | Status after P4 | Borrow |
|---|---|---|
| K1 | stop | passive-tool rule; "all motion retracts before the door unlocks"; knife-and-comb carving |
| K2 | stop as a base | load pins in the jaws; rim-to-rim pairs for flip and unmould; ricer |
| K3 | stop | lip-pivot pour geometry; drum wok only as a later option |
| K4 | stop | white mat as a vision background; mat as a sheeting station only if its release test passes |
| K5 | stop as a base | press tube, ricer, loose-floor moulds, syringes, force-signature sensing |
| K6 | absorbed into H-S1 | tang with pins, GN logistics, per-item camera verification, wash rules |
| K7 | stop as a base | under-deck press in tension; cold plate only as an optional bought anti-griddle |
| K8 | H-S2, conditional | canned couplings (turntables, spindle) in H-S1 as well; enclosure of the frying zone |

### 6.3 Rules for the P5 brief

1. **Simplicity budget sheet** (C5 §2 metrics) next to C4's budget sheet; every P5 document reports all 13 counts
   and its C5 score.
2. **Every station must carry meals no cheaper route can carry.** A station is added only with its list of meals
   and the meals lost without it. Recipe routes (C5 §6.1 rank 1) and adaptations within MEAL-019 come first.
3. **No new novel mechanism without a named rig, its cost and a fallback** that is itself proven.
4. **Meal-by-meal coverage check against 231 meals** (93 %), with the adaptation register (MEAL-021). The reserve
   is 2–3 meals.
5. Carry C1 §10.3 (recipe rules), C2 §8.1 (hygiene rules R-1…R-12) and C3 §8 rec. 7 (degrade and continue) as
   binding.

### 6.4 Experiments before or during P5, cheapest first

| Experiment | Decides | Cost |
|---|---|---|
| K8 magnet, friction and wall-wear rig | whether H-S2 exists | €300–1 000 |
| Tang-and-pin grip, 10 000 cycles wet and floured | the main handling event of H-S1 | ~€2 k |
| Bought push-dicer grid in a Ø 110 tube on a workshop press; slot die for pasta sheet | the press station; IT17/DM33 | ~€500 |
| Canned magnet turntable under a hob with scraper and dough (1.6 kg) | stirring and kneading without a seal | ~€300 |
| Pan-pair flip vs. lift rack vs. turner; Rouladen raft (C1 10.4) | flipping and DM02 | ~€100 |
| Generic peeling module bench tests (#25, by its inventors) | ~90 meals and banana/avocado | per its document |

---

## 7. Customer decisions that most affect simplicity

From C5 §8, ordered by the machine they can remove. Items already ruled by #21–26 are left out.

1. **One washer for ware and dishes** (and boxes), with an 85 °C disinfecting rinse and raw-meat ware in its own
   cycle? Saves a whole washing system.
2. **One serial manipulator**, accepting four-component menus for four persons at the PERF-001 limit and some
   preparation done ahead in idle hours? Saves a second hand (3–6 actuators, 2–4 seals).
3. **Adaptation first**: may P5 remove a station wherever a class (a)/(b) route exists, using the MEAL-019
   budget (c ≤ 24) as the simplification budget?
4. **Filled pasta (IT17, weight 3; DM33)**: machine-made square parcels from press-extruded sheets (mandated c),
   or exempt IT17 from MEAL-003?
5. **Oven position**: inside the bay and loaded by the gantry, or a front-facing column served by the transport
   (#24 allows the modification)?
6. **Transport serves the cell's washer and oven** while the cell keeps its own handler (C4 R-1)?
7. **Lids handled outside the cell** (ingestion or a lid station), so that the cell needs no dock mechanism?
8. **Closed tub with temporal raw/RTE separation** (K8) acceptable as a hygiene principle? Decides whether H-S2
   may proceed.

Still open from C1–C4 and relevant to simplicity: the R-10 ruling on extruded patties and cylinder dumplings
(C1 10.1-4), the module-boundary ruling for an internal handler (C4 R-1), and the garlic question (requirements
5.6 permits peeled cloves, C1's standard N did not).
