# C4 — Critique of the preparation concepts K1…K8: system fit and operations

Round P4, critic C4. View: system architect and operations planner. The question is not "does the cell
work" but "does the whole machine still work, fit, pay and run a household's day with this cell in it".

Yardsticks: BRIEF, DECISIONS 1–15 (especially #6 dishes returned at the hatch and washed by the machine,
#8 the machine washes, peels and cuts produce itself, #11 height 2000–2200 mm, #13 the machine is the
household's only fridge and pantry and serves drinks), requirements PHY, UTL, CAP, PERF, RES, NOI, ENV, MOD,
TRN, SRV, HUM, BLD, MNT, REL; research R3 (storage), R5 (cooking, plating, washing), R7 (ingestion); the
exploration brief and the catalogue's common rules and conflicts X1–X16.

Markers: **[D]** taken from the concept document (section given); **[C]** recomputed by me from the
document's own figures or from physics; **[E]** my estimate. Severity: **fatal** = a mandatory requirement
cannot be met without giving up a defining element of the concept; **major** = a mandatory requirement is
missed as designed, or a whole-machine budget is consumed; **minor** = weakness with a known remedy.
"Fixable" = fixable while the concept stays the same concept.

Scope limit: I read for every concept the definition and layout, the numbers section, the cleaning totals,
the benchmark summary, the requests to the architect and the verdict in full, and the B1–B3 walk-throughs of
K1, K3, K5 and K8 step by step; the rest by search. Nothing in this critique was tested either; its budget
figures are estimates with stated inputs, and they are meant to be recomputed by the architect.

---

## 1. Summary

| | Score (1–10) | Fatal | Major | Cell width as drawn [D] | Cell cost, comparable [C] | One-line verdict |
|---|---|---|---|---|---|---|
| K1 ceiling turret | **2** | 2 | 8 | 2270 | ≈ 32 k€ | Widest, dearest, wettest and slowest to turn round; every whole-machine budget is blown by about 2× |
| K2 vessel stack | **5** | 0 | 7 | 1600 (+300 rack) | ≈ 25 k€ | Most self-contained cell (washer, rack, oven inside, transport only at the port), but the sideways oven does not fit and nothing can plate |
| K3 drum and belt | **4.5** | 0 | 8 | 1450 | ≈ 23.5 k€ | Narrowest all-inclusive cell, few moves; oven does not fit, ports at 120 and 1750 mm, 19 dynamic seals, water over |
| K4 shuttle mat | **4.5** | 0 | 8 | 1560 | ≈ 19.5 k€ | Cheap and compact on paper; mats cost more per year than the whole wear budget, oven at head height with no human access |
| K5 ram and die | **5** | 0 | 7 | 1770 (1170 without oven) | ≈ 21 k€ | Best build path (column separable from the hob), few moves; highest water, 6 kW boiler, ware store lives in the oven bay |
| K6 loose ware, wells | **3.5** | 1 | 7 | 2595 | ≈ 23 k€ | Best turnaround and proven parts, but 2.6 m leaves 1 m for the rest of the machine, and wash-as-you-go cannot get power while cooking |
| K7 state change | **2.5** | 1 | 7 | 2280 | ≈ 32 k€ | A booster bolted onto a full kitchen: dearest cell, second refrigeration circuit, 120 moves |
| K8 sealed tub | **6** | 0 | 7 | 1750 (1150 without oven) | ≈ 18.5 k€ | Best system fit: smallest cell, cheapest, washes its own ware; blocked 25–35 min after each meal, power claim internally inconsistent |

**Budget verdict.** No concept fits the machine. With storage sized for DECISIONS #13, the modules other
than preparation and cooking need about **3.6 m of wall on their own** (floor: 2.7 m, which already misses
CAP-021/022), about **€18–24 k of parts on their own**, and about **45 L of water per day on their own**. The
cells as drawn add 1.45–2.6 m, €18.5–32 k and 55–150 L per day. The machine that results is about **4.2–6.2 m
wide, €37–56 k and 95–190 L per day** against 3.6 m, €25 k (€15 k S) and 110 L. Every cell also claims the whole
3 × 16 A connection for itself, and every cell turns a 595 mm wide oven across a depth that is at most
555 mm inside. Section 3 gives the arithmetic. The honest allocation to preparation plus cooking is
**≤ 1200 mm of wall (oven outside), ≤ 6.5 kW peak including the hob, ≤ 20 L of in-cell water per full meal
and ≤ €9 k of parts without the oven** — and even then the machine needs a customer ruling on width and cost
(section 9).

**Round-2 recommendation in one line.** Carry K8 (tub, washer and cell in one) and K5 (separable press
column) forward as the system-fit base, with K2's inverter-on-a-lift as the hybrid candidate for pan work;
drop K1 and K7 as whole systems; shrink K6 only if it gives up the deck-top oven and a bench; re-run all
survivors against fixed budgets and one ware, port and oven standard (sections 8, 9).

---

## 2. Cross-cutting findings: the orchestrator's list verified, and what it missed

The previous attempt's summary (a)–(h) was checked against the documents. Verdicts: **C** confirmed,
**M** confirmed with a correction, **R** rejected.

| # | Claim | Verdict | Evidence and correction |
|---|---|---|---|
| a | Almost every concept claims 10.3–11 kW for the cell alone; single 3.5 kW zones exceed 3.4 kW per phase; no phase plan anywhere | **C**, and worse | Managed peaks [D]: K1 7 kW hob + 3.3 oven + 1.5 drives = **11.8 kW** [C]; K2 11; K3 11 (plus a fifth heated position H0 of 3 kW not in the sum); K4 11; K5 11 (oven 3.5 kW is itself > 3.4); K6 ≤ 10.3; K7 10.5; K8 claims ≤ 10.3 but its own terms give 7 + 3 + 0.8 = **10.8** [C], and §6.2 says tank and boiler "are heated during the cooking phase" while §7 says "outside the cooking peak". Zones of 3.5 kW single-phase: K1, K2, K4, K7, K8 (and K6's 11.4 kW hob). No document assigns loads to phases. UTL-010 allows ≤ 10.3 kW and ≤ 15 A per phase **for the whole machine**, and UTL-011 puts cold storage above cooking in priority. Section 3.2 |
| b | Every concept merges preparation, cooking and part of washing into one cell with its own manipulator, bypassing transport (TRN-002) | **C** | Internal handlers: K1 three turrets, K2 Wender, K3 vessel shuttle, K4 arm C, K5 shuttle (request 11 asks TRN-002 to allow it), K6 mast, K7 gantry, K8 pucks. In-cell washing: K2 lathe, K6 wells, K7 slot washer, K8 the tub; K1, K3, K4, K5 wash fixed surfaces in place. MOD-001 allows a shared "process cell" for preparation, cooking and portioning; it does not allow washing inside, and none of the concepts keeps its cooking part designable separately. The requirement is wrong, not the concepts: routing 30–175 moves per meal through the shared transport would violate TRN-005/-008. Ruling needed (section 8, R-1) |
| c | Cells take 1450–2600 mm of the ≤ 3600 mm wall and €16–32 k of the €25 k | **C** | Widths [D]: 2270, 1600, 1450, 1560, 1770, 2595, 2280, 1750. Costs as stated [D] 14–32 k€, but on different bases (with or without oven, dock, washer). Made comparable (section 3.5): **€18.5–32 k**. All cells also break PHY-003 (no module wider than 1200 mm) |
| d | Water per day exceeds 110 L in most concepts at three meals a day | **M** | Four clearly over (K1 ≈ 190 L, K3 ≈ 140, K5 ≈ 120, K7 ≈ 115), four at the limit with no margin (K2 ≈ 107, K4 ≈ 108, K6 ≈ 99, K8 ≈ 100–110) [C/E, section 3.3]. Per meal, **none** meets RES-005 (45 L) once dishes, cooking water and produce washing are counted. No concept counts box washing, produce washing (except K4), glasses (DEC-13) or unscraped dishes (DEC-6) |
| e | Sideways 60 cm ovens (≈ 595 wide) do not fit 540–555 mm internal depth | **C, all eight** | K1, K2, K3, K4, K5, K7, K8 turn a built-in oven 90°; K6 states "its 595 width lies along Y" in a bay of 555 inner depth. Inner depth available at the oven: K2 520, K3 ≈ 500, K4 ≈ 510, K5 540, K6 555, K7 550, K1 and K8 at best the full 600 outer with zero skin. Plus: the oven's cooling-air inlet and outlet sit in its front, which now faces the wet, greasy cell; the oven's service side faces sideways, so it cannot be exchanged from the front (MNT-001); four concepts replace the door of a certified appliance (BLD-008) |
| f | Most concepts have single-instance ware, so a second meal waits 55–75 min for a washer | **M** | True for the concepts that send ware to an R6-type chamber (55–75 min): K1 (3 loads, 3 h to all clean), K3, K4, K7 (bulky ware), and K2's 14 single-instance types. Not true for K5 (double set, 2.6), K6 (3.5 min wells) and K8 (tub washes itself in 25–35 min, but is then blocked). CAP-006 (second meal 2 h later) is met by all but K1; **PERF-005** (next meal possible within 30 min) is missed by K1 and at risk for K3, K4, K7 and K8 |
| g | Plating is pushed to "serving" everywhere and hot-holding is undefined | **C** | K1 open issue 12, K2 R8, K3 port R3, K4 A7, K5 request 7, K6 request 5, K7 transport request, K8 A-4: all hand over the cooking vessel (up to 8 kg). K2 even hands over "the final merge of pasta and sauce". Nobody checks SRV-009 (all six dishes within 4 min = one placement every 6–7 s, section 4.5). Hot-holding is "a free hob at low power" or "the oven at 70–80 °C", i.e. it occupies the cooking positions the next course needs |
| h | Noise has almost no numbers | **M** | K4, K5, K6, K7, K8 give dB(A) estimates for short loud operations; only K6 gives a number for washing (52–56 dB(A) for 25–30 min per meal, over NOI-002's 48). K1 gives none. Nobody addresses quiet mode (NOI-004, MODE-002 22:00–06:00), although dinner clean-up runs until 22:00–23:00 in K1 and in the chamber concepts |

Findings the list missed (each applies to all eight unless stated):

| # | Finding | Severity | Why it matters |
|---|---|---|---|
| i | **No concept serves a drink** (DEC-13). A glass of juice needs an opened carton kept upright in the cold store, a pour, a glass from the dish store, and the hatch. If it runs through the cell, it waits for K8's 25–35 min wash or K1's 45 min wash-down; if not, the serving module needs a pour station nobody has budgeted | major | Daily use case of the customer |
| j | **DEC-8 invalidates benchmark shortcuts**: frozen peas (B3 in K1, K2, K3, K5, K8), bought-trimmed or frozen beans (B6 in K2, K3, K4, K6, K8), frozen chopped herbs (K1, K2), bought grated cheese (K1, K3, K4, K6). Shelling peas has no mechanism anywhere (no G-document); trimming 60–80 beans exceeds GP-102's ≤ 40 pieces. B3 and B6 have 2–16 min of margin in several concepts | major | Time claims of B3, B4, B6 are not valid under the current decisions |
| k | **Stowed packs "arrive opened"** (K1 A6, K2 R3, K4 A5, K6 4, K8 A-3) or are converted at ingestion (K3 cartridges, K5 small tubes, K7 pucks, K4 pucks): the JIT opening cell of DEC-3 and R7 §2.5 is assumed by everyone and budgeted by no one (width 300–600 mm, €0.8–1.5 k, a transport round trip per pack) | major | Width, cost, transport load |
| l | **Ports everywhere**: box ports at z 1300–1980 in left side walls or ceilings (K1, K2, K4, K5, K6, K7, K8), K3's dock at 1750 and its vessel port at **z 120–290**, K4's vessel port at 700–950, K7's at bench height in the right wall. A side-wall port is reachable only at the joint with the neighbouring module, which must then leave a transfer zone; a transport along the machine at one height cannot reach them all | major | TRN-003, MOD-011: one hand-over definition for all modules |
| m | **ENV-010 (≤ 0.3 kg of moisture into the room per meal) is unaddressed.** Extraction of 60–150 m³/h [D] through an air-cooled condenser releases up to 2 kg/h [C: saturated 25 °C exhaust 23 g/m³ against room 9.7 g/m³, × 150 m³/h]. Meeting 0.3 kg needs the exhaust dried to a dew point of ≈ 13 °C: a refrigerant dehumidifier (0.2 kWh/kg, 0.3–0.5 kW, €300–600, 20–30 L) or 27 L of mains water per kg of steam (R5 §2.3) | major | Power, water, noise and a shared module nobody owns |
| n | **PHY-003** (modules ≤ 1200 mm, on a 150 mm grid): all cells as drawn are 1450–2600 mm single enclosures; K8's tub (1150) and K5's column-and-hob (1170) are the only parts that could become 1200 mm modules | major | Modularity, delivery (PHY-012) |
| o | **Unscraped dishes, glasses and cutlery** come back through the hatch (UC-07 after DEC-6); the concepts' "10 L for the dish load" assumes a household dishwasher loaded by a human. A machine-loaded washer with scraping and cutlery handling is a module of its own (≈ 600 mm, €1.5–7 k) | major | Width, cost; every concept's water ledger |
| p | **CAP-003/SRV courses**: hot-holding on the hob positions blocks the dessert or second course that CAP-003 allows (up to 3 courses) | minor | Scheduling |

---

## 3. Whole-machine budgets

### 3.1 Width (PHY-004: ≤ 3600 mm M, ≤ 3000 mm S; PHY-003; DEC-11 height 2200; DEC-13 all household food)

What the rest of the machine needs, before any preparation cell [E, from R3 §3.2, §4.1, §6 and R5 §10]:

| Module | Floor | Realistic with DEC-13 | Basis |
|---|---|---|---|
| Ambient storage (aisle shuttle, 2 × 176 racks) | 600 (≈ 90 GN 1/6 at 2200 high) | 900 (≈ 130–150 positions; bread, fruit, cereals, ambient drinks need taller boxes) | R3: 130–168 boxes per metre; CAP-020 ≥ 80; DEC-13 adds non-cooking food |
| Chilled storage (178 cm built-in shell + rack + hatch) | 600 (33–45 positions) | 1200 (two shells) | CAP-021 ≥ 45 positions; R3: "1.3 cells for 4, tight, or 2"; DEC-13 adds milk, yoghurt, cheese, cold cuts, juice, leftovers |
| Frozen storage | 600 (178 cm shell) or under a counter (≈ 12–15 positions, fails CAP-022) | 600 | CAP-022 ≥ 20 positions |
| Dish washer (machine-loaded, DEC-6), hatch, dish and glass store (CAP-031: 36 dishes + glasses) | 600, stacked: washer 0–820, hatch 850–1300, store 1300–2200 | 600 | SRV-010, CAP-031, UC-07 |
| Ingestion B, JIT opening cell, waste bins | 300 (funnel in the top gallery, opener beside the hatch) | 300–600 | R7 §2.5, §10; CAP-041 |
| Transport | 0 (overhead gallery in the 200 mm of DEC-11) | 0–150 | TRN-003; end stations |
| Ware/box washer, if the cell has none | 0 if shared with the dish washer (commercial under-counter) | 0–600 | R5 §10.4 option 2 |
| **Total without the cell** | **2700** | **3600–3900** | |

So the cell's share of a 3600 mm machine is **≤ 900 mm at the floor and nothing at all with DEC-13
storage**. The floor itself already misses CAP-021 and is marginal for CAP-022. Whole-machine widths with
each cell as drawn [C]:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Cell as drawn [D] | 2270 | 1600 | 1450 | 1560 | 1770 | 2595 | 2280 | 1750 |
| Hidden extras [C] | clean store for ≈ 110 parts not designed | rack holds 60 % → +300 (explorer) | — | — | — | — | chamber for bulky ware | — |
| Machine, floor (+2700) | 4970 | 4600 | 4150 | 4260 | 4470 | 5295 | 4980 | 4450 |
| Machine, realistic (+3600) | 5870 | 5500 | 5050 | 5160 | 5370 | 6195 | 5880 | 5350 |
| Share of a 3600 run | 63 % | 53 % | 40 % | 43 % | 49 % | 72 % | 63 % | 49 % |

Height does not rescue it: DEC-11's extra 200 mm is best spent on an overhead transport gallery, and the
178 cm cold shells cannot grow. An L layout does not add wall length under PHY-004. **No concept fits;
the architect needs a customer ruling** (section 9, rec. 1).

Where the oven goes decides 560–600 mm. All eight put it inside the cell and all eight turn it 90° (finding e),
which does not fit. Three honest options: (1) a front-facing oven in a transport-served "hot column"
(oven 900–1355, with a freezer below it or ware storage above), loaded by the transport or by a small loader
of the cooking module; (2) a narrower oven (countertop combi-steam units of ≈ 490–500 mm width exist [E,
unverified], but none checked for 45 L, GN 2/3, plumbing and a start without a button press, COK-023); (3) a
custom cavity (loses the certified appliance, BLD-008). Option 1 is the only one that shrinks cells:
K1 → 1700, K5 → 1170, K8 → 1150, K7 → 1720, K6 → 2035. K2, K3 and K4 stack the oven inside the cell and gain
no width; they must redesign the stack instead.

### 3.2 Power: a phase plan for the whole machine (UTL-010, UTL-011)

UTL-010 allows ≤ 15 A per phase (3.45 kW at 230 V) and ≤ 10.3 kW in total. Loads that the rest of the machine
draws while a meal is cooked [E]: fridge and freezer compressors 0.15 + 0.15 kW, control and cameras 0.15,
transport and storage drives 0.2 average, cell drives 0.3–0.8, extraction plus dehumidifier (finding m)
0.1–0.4. Total **≈ 1.0–1.7 kW**, and cold storage ranks above cooking. A household combi-steam oven heats with
3.0–3.5 kW single-phase [R5 §2.2] and cannot be throttled from outside without aborting its programme.

The only phase plan that closes [C]:

| Phase | Load | kW |
|---|---|---|
| L1 | hob channel A (coils 1 + 2 share one generator budget) ≤ 2.8; fridge 0.15; control 0.15; transport 0.2; extraction 0.1 | ≤ 3.4 |
| L2 | hob channel B (coils 3 + 4) ≤ 2.8; freezer 0.15; cell drives 0.3–0.5 | ≤ 3.45 |
| L3 | oven ≤ 3.3 (heating) **or**, when the oven is off, washer/boiler heaters ≤ 3.3 | ≤ 3.4 |
| **Total** | | **≤ 10.25** |

Consequences for every concept:

1. **Four hob positions share ≈ 5.6 kW**, not 11–13 kW. COK-004 (6 L to 95 °C in 16 min: 2.0 MJ at 75 %
   efficiency = 2.8 kW [C]) is met only while the paired coil is off. 3.5 kW zones are neither needed nor
   allowed; 3.0 kW coils on 13 A are the right size.
2. **No water heating while the oven heats.** K6's wash-as-you-go needs ≈ 0.26 kWh per load for the 85 °C
   rinse [C: 3.2 L × 4.19 × 70 K], 7 loads per meal, i.e. ≈ 2.7 kW average over a 40-min meal — it gets 0 kW
   during oven meals and stalls after the 8 L boiler is drawn down. K8's tank and boiler (8 kW), K5's 6 kW
   boiler, K1's 2 kW sump heater and K4's 3 kW wash heater plus 2 kW steam likewise wait. The dish washer
   (≈ 2 kW) waits too.
3. **Time claims were made at full power.** Benchmarks with ≤ 3 min of margin (K4 B3 48/50, K2 B8 48/50,
   K7 B8 47/50 and B7 40/44) are not safe until re-timed under the plan.
4. The rest of the machine is not "free": if the cell takes its claimed 10.3–11.8 kW, the cold store is shed
   during every meal, contrary to UTL-011.

### 3.3 Water (RES-005 ≤ 45 L per reference meal; RES-006 ≤ 110 L per day)

Per reference day (1 full warm, 1 light warm, 1 cold/light meal, CAP-002). Cell and ware figures are the
concepts' own [D] for the full meal; light and cold meals are scaled by me [E] with ware loads pooled where the
concept allows. The same machine-wide items are added to every concept [E]: dishes, glasses and cutlery
(DEC-6/13) 15 L, cooking water 6.5 L, box washing 5–15 L (≈ 6 boxes emptied per day, R7 §2.5), produce
washing 8 L (DEC-8; only K4 counts it), hatch/transport/waste wash-down 4 L: **≈ 45 L per day**.

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Full meal, cell + ware [D] | 92 | 38 | 42.5 (+12 daily) | 33.5 | 50 | 35 | 41.5 | 31 |
| Per reference meal incl. dishes 10, cooking 4, produce 6 [C] | **112** | 58 | 62.5 | 53.5 | 70 | 55 | 61.5 | 51 |
| Light warm meal [E] | 35 | 17 | 27 | 12 (ware pooled) | 26 | 13 | 25 | 12 |
| Cold meal [E] | 22 | 8 | 15 | 18.5 pooled load | 3 | 7 | 5 | 12 |
| Cell per day [C] | 149 | 63 | 97 | 64 | 79 | 55 | 72 | 55 (explorer: 65) |
| **Machine per day [C]** | **≈ 190** | **≈ 107** | **≈ 140** | **≈ 108** | **≈ 122** | **≈ 99** | **≈ 115** | **≈ 100–110** |
| RES-006 (110) | 1.7 × | at limit | 1.3 × | at limit | 1.1 × | 0.9 × | 1.05 × | at limit |

No concept meets RES-005 per meal. The single largest item in K1, K3, K4, K5 and K7 is the external chamber
load (17–20 L, R6); the lever is one shared commercial under-counter washer with 2.4 L of rinse per rack
(R5 §10.1) for dishes, boxes and ware, which brings a chamber load to ≈ 5 L plus a tank share.

### 3.4 Energy (RES-001 ≤ 4.0 kWh per reference meal; RES-002 ≤ 10 kWh per day)

Cleaning energy per full meal [D] plus cooking 1.3 kWh and the dish load 0.9 kWh (the requirement's own
basis), plus dehumidification 0.1–0.4 kWh (finding m) [C]:

| K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|
| 5.9 + 2.2 = **8.1–8.5** | 1.8 + 2.2 = **4.0–4.4** | 2.85 + 2.2 = **5.05–5.45** | 2.15 + 2.2 = **4.35–4.75** | 2.5 + 2.2 = **4.7–5.1** | 2.3 + 2.2 = **4.5–4.9** | 2.9 + 2.2 = **5.1–5.5** (with the cold cabinet) | 1.7 + 2.2 = **3.9–4.3** |

Only K8 and K2 are at the limit; K1 is at twice the limit. With cold storage (1.2 kWh/day) and the light and
cold meals, K1 lands at ≈ 14 kWh/day against RES-002's 10 [C].

### 3.5 Cost (BLD-004: MVC ≤ €25 k M, ≤ €15 k S)

What the rest of the MVC costs in parts [E, from R3 §2.2, §4.1, R5 §6.1, §9, §10.1, §11, R7 §10]:

| Module | Low | High | Note |
|---|---|---|---|
| Ambient storage with ≈ 140 boxes and lids | 3.0 | 4.5 | carriage, racks, enclosure, hatch, lid station |
| Cold storage: fridge + freezer shells, hatches or vestibules, cold-rated racks and carriages, boxes | 5.0 | 7.0 | + 2.0–2.5 for a second fridge (DEC-13) |
| Transport, 3.6 m, 8 kg payload | 2.4 | 3.5 | |
| Hatch, dish and glass store, dish handling (no plating manipulator) | 1.5 | 3.0 | + 2–4 if serving must plate with its own manipulator |
| Machine-loaded dish washer (DEC-6) | 1.5 | 7.0 | household with door drive and rack loader, or commercial under-counter |
| Ingestion B and JIT opening cell | 1.3 | 2.2 | |
| Frame, utilities (softener, break tank, drain lift, leak sensing), electrical, safety, extraction and dehumidifier | 2.5 | 4.0 | |
| Control hardware, UI | 0.8 | 1.5 | |
| **Total without the cell** | **≈ 18** | **≈ 33** (+ 2.5) | mid ≈ 24 |

Cell costs made comparable (explorer's figure [D] + realistic controllable combi-steam oven €3.5 k where
excluded or under-priced [R5: €2.3–5.5 k] + dosing front end ≈ €1.0–1.2 k where excluded) [C]:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| As stated [D] | 27.5 without oven, dock | 24 incl. oven 2.6, lathe | 20 without oven | 16 without oven | 17.7 without oven | 21.9 incl. oven 2.5, washer | 32 incl. oven | 14 without oven, dock |
| Comparable [C] | **≈ 32** | **≈ 25** | **≈ 23.5** | **≈ 19.5** | **≈ 21** | **≈ 23** | **≈ 32** | **≈ 18.5** |
| Machine total, low / mid [C] | 50 / 56 | 43 / 49 | 41.5 / 47.5 | 37.5 / 43.5 | 39 / 45 | 41 / 47 | 50 / 56 | 36.5 / 42.5 |

**How much can preparation plus cooking honestly take?** At the M target (€25 k) the rest of the machine
leaves **€1–7 k** for the cell including hob and oven; at the S target (€15 k) nothing — the S target is
unreachable with any concept and any storage that meets CAP-020…022. No concept is within a factor of 2.5
of the M share. A defensible design-to-cost target for round 2 is **≤ €9 k for preparation and hob without the
oven** (roughly a quarter of a €36–40 k machine), with the oven (€2.5–4 k) budgeted in the cooking column;
BLD-004 itself needs re-baselining by the customer.

### 3.6 Noise, heat and steam

| | Loud operations [D] | Washing [D] | Quiet mode (NOI-004, 22:00–06:00) [C] |
|---|---|---|---|
| K1 | not estimated; blender 6000 rpm, ram strokes, 600 rpm basket | wash-down with three 5 bar lances on 5 m² of steel for 10 min, "will probably exceed 48"; 3 ware loads after dinner | dinner at 19:00 → cell and ware not clean before ≈ 22:00–23:00 |
| K2 | rasp peeling 70–75 at source, 2 min | lathe 54 min after the meal, needs an insulated chamber | lathe runs into the quiet window after late dinners |
| K3 | rumbler 3–4 min, knives 3000 rpm, spin 480 rpm; B3 and B6 exceed the 5-min budget of NOI-003 | drum and belt 12 min wet, 35 min dry | ok |
| K4 | blade landings 62–66 through the door, ≤ 2 min | steam gate, pump | ok |
| K5 | cracking through grids 65–70, rasp can 60 for 3 min, mixer knocking at 3 Hz | tubes during the meal | ok |
| K6 | blade 65–70 < 2 min | **52–56 dB(A) for 25–30 min per meal** (NOI-002: 48) | wells run during the meal |
| K7 | bow knife 65–70 for 1–4 min, blender 70, extraction 55, compressor 40 | slot washer 25 min per meal | compressor cycles at night (released set-point) |
| K8 | chopper 65–70 for seconds | jets on the 1.5 mm door skin, **which faces the room**; 48 "not assured" | full wash 25–35 min after every dinner |

Night is a scheduling problem for everyone: a yeast-dough breakfast (B5-class, 90–113 min) served at 07:00
must knead inside the quiet window; a dinner after 20:30 pushes K1's and the chamber concepts' washing past
22:00, where MODE-002 defers it and HYG-030 (wash within 60 min) is broken.

**Heat and steam.** Only K1 states a heat release (0.3–0.5 kW during cooking). ENV-012 asks it of every
module. Nobody sizes the condenser (finding m). Whole-machine: 7–10 kWh/day end up as heat, ≈ 1–1.5 kW during
a meal, plus ≈ 0.5–2 kg of steam per meal that must be condensed to meet ENV-010.

---
