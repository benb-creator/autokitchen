# C4 — Critique of the preparation concepts K1…K8: system fit and operations

Round P4, critic C4. View: system architect and operations planner. The question is not "does the cell
work" but "does the whole machine still work, fit, pay and run a household's day with this cell in it".

Yardsticks: BRIEF, DECISIONS 1–16 (especially #6 dishes returned at the hatch and washed by the machine,
#8 the machine washes, peels and cuts produce itself, #11 height 2000–2200 mm, #13 the machine is the
household's only fridge and pantry and pours drinks, #16 ambient breakfast goods and snacks stay outside),
requirements as aligned to these decisions on 2026-09-30 (PHY-004 now ≤ 4200 mm M / ≤ 3600 mm S with a
1.2 m allocation for the process cell; CAP-020…025 237 box positions; SRV-022/-024 drinks; WSH-001/-002 dish
washing; section 5.6 purchase list; UO-96 stock made by the machine), and PHY, UTL, CAP, PERF, RES, NOI, ENV,
MOD, TRN, SRV, HUM, BLD, MNT, REL; research R3 (storage), R5 (cooking, plating, washing), R7 (ingestion); the
exploration brief and the catalogue's common rules and conflicts X1–X16. The concepts were written against
the older requirements (3600 mm, 2000 mm, human-loaded dish washer, frozen and pre-cut produce allowed); where
that matters it is said.

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

**Budget verdict.** No concept fits the machine. With storage sized for CAP-020…025 (237 box positions,
DEC-13/16), the modules other than preparation and cooking need **3.0 m of wall at the floor and ≈ 3.6 m
realistically**, **€20–26 k of parts** and about **45 L of water per day** on their own. PHY-004 (now ≤ 4200 mm
M) therefore leaves the process cell **1.2 m at best, 0.6 m realistically — including the oven**. The cells as
drawn take 1.45–2.6 m, €18.5–32 k and 55–150 L per day; the machine that results is **4.45–6.2 m wide,
€38–58 k and 95–190 L per day** against 4.2 m, €25 k (€15 k S) and 110 L. Every cell also claims the whole
3 × 16 A connection for itself, and every cell turns a 595 mm wide oven across a depth that is at most
555 mm inside. Section 3 gives the arithmetic. The honest allocation to preparation plus cooking is
**≤ 1200 mm of wall including the oven (or ≤ 600 mm plus a shared oven column), ≤ 5.6 kW for all four hob
positions together, ≤ 20 L of in-cell water per full meal and ≤ €9 k of parts without the oven** — and BLD-004
still needs a customer ruling (section 9).

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
| c | Cells take 1450–2600 mm of the ≤ 3600 mm wall and €16–32 k of the €25 k | **C** (limit now 4200 mm, allocation 1200 mm) | Widths [D]: 2270, 1600, 1450, 1560, 1770, 2595, 2280, 1750, i.e. 1.2–2.2 × PHY-004's own allocation of 1.2 m for the process cell. Costs as stated [D] 14–32 k€, but on different bases (with or without oven, dock, washer). Made comparable (section 3.5): **€18.5–32 k**. All cells also break PHY-003 (no module wider than 1200 mm) |
| d | Water per day exceeds 110 L in most concepts at three meals a day | **M** | Four clearly over (K1 ≈ 190 L, K3 ≈ 140, K5 ≈ 120, K7 ≈ 115), four at the limit with no margin (K2 ≈ 107, K4 ≈ 108, K6 ≈ 99, K8 ≈ 100–110) [C/E, section 3.3]. Per meal, **none** meets RES-005 (45 L) once dishes, cooking water and produce washing are counted. No concept counts box washing, produce washing (except K4), glasses (DEC-13) or unscraped dishes (DEC-6) |
| e | Sideways 60 cm ovens (≈ 595 wide) do not fit 540–555 mm internal depth | **C, all eight** | K1, K2, K3, K4, K5, K7, K8 turn a built-in oven 90°; K6 states "its 595 width lies along Y" in a bay of 555 inner depth. Inner depth available at the oven: K2 520, K3 ≈ 500, K4 ≈ 510, K5 540, K6 555, K7 550, K1 and K8 at best the full 600 outer with zero skin. Plus: the oven's cooling-air inlet and outlet sit in its front, which now faces the wet, greasy cell; the oven's service side faces sideways, so it cannot be exchanged from the front (MNT-001); four concepts replace the door of a certified appliance (BLD-008) |
| f | Most concepts have single-instance ware, so a second meal waits 55–75 min for a washer | **M** | True for the concepts that send ware to an R6-type chamber (55–75 min): K1 (3 loads, 3 h to all clean), K3, K4, K7 (bulky ware), and K2's 14 single-instance types. Not true for K5 (double set, 2.6), K6 (3.5 min wells) and K8 (tub washes itself in 25–35 min, but is then blocked). CAP-006 (second meal 2 h later) is met by all but K1; **PERF-005** (next meal possible within 30 min) is missed by K1 and at risk for K3, K4, K7 and K8 |
| g | Plating is pushed to "serving" everywhere and hot-holding is undefined | **C** | K1 open issue 12, K2 R8, K3 port R3, K4 A7, K5 request 7, K6 request 5, K7 transport request, K8 A-4: all hand over the cooking vessel (up to 8 kg). K2 even hands over "the final merge of pasta and sauce". Nobody checks SRV-009 (all six dishes within 4 min = one placement every 6–7 s, section 4.5). Hot-holding is "a free hob at low power" or "the oven at 70–80 °C", i.e. it occupies the cooking positions the next course needs |
| h | Noise has almost no numbers | **M** | K4, K5, K6, K7, K8 give dB(A) estimates for short loud operations; only K6 gives a number for washing (52–56 dB(A) for 25–30 min per meal, over NOI-002's 48). K1 gives none. Nobody addresses quiet mode (NOI-004, MODE-002 22:00–06:00), although dinner clean-up runs until 22:00–23:00 in K1 and in the chamber concepts |

Findings the list missed (each applies to all eight unless stated):

| # | Finding | Severity | Why it matters |
|---|---|---|---|
| i | **No concept pours a drink** (DEC-13, SRV-022: glass at the hatch ≤ 60 s when idle, **≤ 3 min during a meal, and the meal delayed ≤ 2 min**, SRV-024). A glass of juice needs an opened carton kept upright in the chilled store, a pour, a glass from the dish store, the hatch, and the carton back: ≈ 4 transport moves [E]. Through the cell it would wait for K8's 25–35 min wash, K1's 45 min wash-down, or a manipulator busy with a meal; it must therefore be a pour station at the serving side that no concept (and no module yet) owns | major | Daily use case of the customer; transport load during meals (TRN-008) |
| j | **Section 5.6 (DEC-8) invalidates some benchmark shortcuts.** Frozen peas and grated cheese remain permitted, but bought-trimmed or frozen cut beans (B6 in K2, K3, K4, K6, K8; K5 "bought prepared"), frozen chopped herbs (K1, K2, K5, K7 dill/parsley/chives), stock paste or cubes (K3 "stock paste slug", K4 "stock cup") are not. Trimming 60–80 beans for B6 (6 persons) exceeds G10's GP-102 (≤ 40 pieces); stock must be made ahead (UO-96: 1–4 h of simmering, ≥ 3 L frozen). B6 has 0–16 min of margin (K6 54/60, K4 50/60, K7 50/60) | major | Time claims of B6 and of all stock-based menus are not valid under the current purchase list |
| j2 | **UO-96 stock-making is a standing load nobody schedules**: one hob position for 1–4 h, ≈ 1.5–3 kWh [E] and a strain-and-portion step per batch, ≈ 1–2 batches per week for 49 corpus meals; it fits only into idle hours (quiet mode is fine: simmering is silent) and competes with the oven on the phase plan of section 3.2 | minor | Hob occupancy, energy per day, freezer positions (CAP-022 includes them) |
| k | **Stowed packs "arrive opened"** (K1 A6, K2 R3, K4 A5, K6 4, K8 A-3) or are converted at ingestion (K3 cartridges, K5 small tubes, K7 pucks, K4 pucks): the JIT opening cell of DEC-3 and R7 §2.5 is assumed by everyone and budgeted by no one (width 300–600 mm, €0.8–1.5 k, a transport round trip per pack) | major | Width, cost, transport load |
| l | **Ports everywhere**: box ports at z 1300–1980 in left side walls or ceilings (K1, K2, K4, K5, K6, K7, K8), K3's dock at 1750 and its vessel port at **z 120–290**, K4's vessel port at 700–950, K7's at bench height in the right wall. A side-wall port is reachable only at the joint with the neighbouring module, which must then leave a transfer zone; a transport along the machine at one height cannot reach them all | major | TRN-003, MOD-011: one hand-over definition for all modules |
| m | **ENV-010 (≤ 0.3 kg of moisture into the room per meal) is unaddressed.** Extraction of 60–150 m³/h [D] through an air-cooled condenser releases up to 2 kg/h [C: saturated 25 °C exhaust 23 g/m³ against room 9.7 g/m³, × 150 m³/h]. Meeting 0.3 kg needs the exhaust dried to a dew point of ≈ 13 °C: a refrigerant dehumidifier (0.2 kWh/kg, 0.3–0.5 kW, €300–600, 20–30 L) or 27 L of mains water per kg of steam (R5 §2.3) | major | Power, water, noise and a shared module nobody owns |
| n | **PHY-003** (modules ≤ 1200 mm, on a 150 mm grid): all cells as drawn are 1450–2600 mm single enclosures; K8's tub (1150) and K5's column-and-hob (1170) are the only parts that could become 1200 mm modules | major | Modularity, delivery (PHY-012) |
| o | **Unscraped dishes, glasses and cutlery** come back through the hatch (UC-07 after DEC-6); the concepts' "10 L for the dish load" assumes a household dishwasher loaded by a human. A machine-loaded washer with scraping and cutlery handling is a module of its own (≈ 600 mm, €1.5–7 k) | major | Width, cost; every concept's water ledger |
| p | **CAP-003/SRV courses**: hot-holding on the hob positions blocks the dessert or second course that CAP-003 allows (up to 3 courses) | minor | Scheduling |

---

## 3. Whole-machine budgets

### 3.1 Width (PHY-004: ≤ 4200 mm M, ≤ 3600 mm S; PHY-003; DEC-11 height 2200; CAP-020…025)

The requirements now allocate 0.6–0.9 m to ambient and cool storage, 1.8 m to cold storage, **1.2 m to the
process cell**, 0.6 m to washing, and ingestion B "within a front" (PHY-004 rationale). Checked against
R3 [E, from R3 §3.2, §4.1, §6 and R5 §10]:

| Module | Floor | Realistic | Basis |
|---|---|---|---|
| Ambient + cool storage (aisle shuttle, 2 × 176 racks), CAP-020 ≥ 100 + CAP-024 ≥ 12 | 600 (≈ 90–100 GN 1/6 at 2200 high: fails by a few) | 900 (≈ 140; STOW packs, tins and UHT cartons need taller slots; ethylene separation) | R3: 130–168 boxes per metre at 2000 |
| Chilled storage, CAP-021 ≥ 90 positions incl. 12 L of upright drinks | 1200 (two 178 cm shells, 66–90 positions: marginal) | 1200 | R3: 33–45 positions per shell |
| Frozen storage, CAP-022 ≥ 35 | 600 | 600 | one shell 33–45 |
| Dish washer (machine-loaded, scraping, cutlery; WSH-001/-002), hatch, dish and glass store (CAP-031) | 600, stacked: washer 0–820, hatch 850–1300, store 1300–2200 | 600 | SRV-010, UC-07 |
| Ingestion B, JIT opening cell, drink pour station, waste bins | 0 (in fronts and the top gallery) | 300 | R7 §2.5, §10; SRV-022; CAP-041 |
| Transport | 0 (overhead gallery in the 200 mm of DEC-11) | 0–150 | TRN-003 |
| Ware/box washer, if the cell has none | 0 if the dish washer is a shared commercial under-counter unit | 0–600 | R5 §10.4 option 2 |
| **Total without the cell** | **3000** | **3600** | |

So the process cell's share of a 4200 mm machine is **1200 mm at the floor and 600 mm realistically,
including the oven**; at the S limit (3600) it is 600 mm or nothing. Whole-machine widths with each cell as
drawn [C]:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Cell as drawn [D] | 2270 | 1600 | 1450 | 1560 | 1770 | 2595 | 2280 | 1750 |
| Hidden extras [C] | clean store for ≈ 110 parts not designed | rack holds 60 % → +300 (explorer) | — | — | ware store sits in the oven bay | — | chamber for bulky ware | — |
| Machine, floor (+3000) | 5270 | 4600–4900 | **4450** | 4560 | 4770 | 5595 | 5280 | 4750 |
| Machine, realistic (+3600) | 5870 | 5200–5500 | 5050 | 5160 | 5370 | 6195 | 5880 | 5350 |
| Cell ÷ PHY-004 allocation (1200) | 1.9 × | 1.3–1.6 × | 1.2 × | 1.3 × | 1.5 × | 2.2 × | 1.9 × | 1.5 × (1.0 × without oven) |

Height does not rescue it: DEC-11's extra 200 mm is best spent on an overhead transport gallery, and the
178 cm cold shells cannot grow. An L layout does not add wall length under PHY-004. **No concept fits the
4200 mm limit even at the storage floor; K3 comes closest (4450), K8 and K5 reach the allocation only
without their oven.**

Where the oven goes decides 560–600 mm. All eight put it inside the cell and all eight turn it 90° (finding e),
which does not fit. Three honest options: (1) a front-facing oven in a transport-served "hot column"
(oven 900–1355, with a freezer below it or ware storage above), loaded by the transport or by a small loader
of the cooking module; (2) a narrower oven (countertop combi-steam units of ≈ 490–500 mm width exist [E,
unverified], but none checked for 45 L, GN 2/3, plumbing and a start without a button press, COK-023); (3) a
custom cavity (loses the certified appliance, BLD-008). Option 1 shrinks cells (K1 → 1700, K5 → 1170,
K8 → 1150, K7 → 1720, K6 → 2035) but the oven column still costs ≈ 600 mm of the 1200 mm allocation, unless
it can share a column with the dish store or the ware store above 1400 mm. K2, K3 and K4 stack the oven
inside the cell and gain no width; they must redesign the stack instead. In short: **the 1200 mm allocation
holds a 600 mm cell and a 600 mm oven column, or a 1200 mm cell with the oven stacked inside and loaded by
the cell's own handler.** No explored cell is 600 mm; K8's tub (1150) and K5's column-and-hob (1170) are the
only ones that are 1200 mm without their oven, and K3 (1450) the only one near 1200 with it.

### 3.2 Power: a phase plan for the whole machine (UTL-010, UTL-011)

UTL-010 allows ≤ 15 A per phase (3.45 kW at 230 V) and ≤ 10.3 kW in total. Loads that the rest of the machine
draws while a meal is cooked [E]: two fridge and one freezer compressor 3 × 0.15 kW (CAP-021/022 need three
cold shells), control and cameras 0.15, transport and storage drives 0.2 average, cell drives 0.3–0.8,
extraction plus dehumidifier (finding m) 0.1–0.4. Total **≈ 1.2–2.0 kW**, and cold storage ranks above
cooking. A household combi-steam oven heats with 3.0–3.5 kW single-phase [R5 §2.2] and cannot be throttled
from outside without aborting its programme.

The only phase plan that closes [C]:

| Phase | Load | kW |
|---|---|---|
| L1 | hob channel A (coils 1 + 2 share one generator budget) ≤ 2.7; fridge 1 0.15; control 0.15; transport 0.2; extraction 0.1 | ≤ 3.3 |
| L2 | hob channel B (coils 3 + 4) ≤ 2.7; fridge 2 and freezer 0.3; cell drives 0.3–0.45 | ≤ 3.45 |
| L3 | oven ≤ 3.3 (heating) **or**, when the oven is off, washer/boiler heaters ≤ 3.3 | ≤ 3.4 |
| **Total** | | **≤ 10.15** |

Consequences for every concept:

1. **Four hob positions share ≈ 5.4 kW**, not 11–13 kW. COK-004 (6 L to 95 °C in 16 min: 2.0 MJ at 75 %
   efficiency = 2.8 kW [C]) is met only while the paired coil is off and a compressor is not starting. 3.5 kW
   zones are neither needed nor allowed; 3.0 kW coils on 13 A, managed per pair, are the right size.
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
| Ambient and cool storage with ≈ 120 boxes and lids | 3.0 | 4.5 | carriage, racks, enclosure, hatch, lid station |
| Cold storage: two fridge shells and one freezer shell (CAP-021/022), hatches or vestibules, cold-rated racks and carriages, ≈ 125 boxes | 7.1 | 9.8 | shells 3.2–4.4, three hatch-rack-carriage sets 2.7–4.2 |
| Transport, 4.2 m, 8 kg payload | 2.4 | 3.5 | |
| Hatch, dish and glass store, dish handling (no plating manipulator) | 1.5 | 3.0 | + 2–4 if serving must plate with its own manipulator |
| Machine-loaded dish washer with scraping and cutlery (DEC-6, WSH-001) | 1.5 | 7.0 | household with door drive and rack loader, or commercial under-counter |
| Ingestion B, JIT opening cell, drink pour station | 1.5 | 2.5 | |
| Frame, utilities (softener, break tank, drain lift, leak sensing), electrical, safety, extraction and dehumidifier | 2.5 | 4.0 | |
| Control hardware, UI | 0.8 | 1.5 | |
| **Total without the cell** | **≈ 20** | **≈ 36** | mid ≈ 26 |

Cell costs made comparable (explorer's figure [D] + realistic controllable combi-steam oven €3.5 k where
excluded or under-priced [R5: €2.3–5.5 k] + dosing front end ≈ €1.0–1.2 k where excluded) [C]:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| As stated [D] | 27.5 without oven, dock | 24 incl. oven 2.6, lathe | 20 without oven | 16 without oven | 17.7 without oven | 21.9 incl. oven 2.5, washer | 32 incl. oven | 14 without oven, dock |
| Comparable [C] | **≈ 32** | **≈ 25** | **≈ 23.5** | **≈ 19.5** | **≈ 21** | **≈ 23** | **≈ 32** | **≈ 18.5** |
| Machine total, low / mid [C] | 52 / 58 | 45 / 51 | 43.5 / 49.5 | 39.5 / 45.5 | 41 / 47 | 43 / 49 | 52 / 58 | 38.5 / 44.5 |

**How much can preparation plus cooking honestly take?** At the M target (€25 k) the rest of the machine
leaves **€0–5 k** for the cell including hob and oven; at the S target (€15 k) nothing — the S target is
unreachable with any concept and any storage that meets CAP-020…025. No concept is within a factor of 3.5
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

## 4. Operations

### 4.1 Benchmark times, re-checked

The explorers' times [D] assume full power on every position, no retry, the old purchase rules, and a box
at the dock whenever it is wanted. Spot checks of the arithmetic held up (e.g. K1 B3: 1 kg potatoes with
1 L water on a 2.0 kW position boil after 0.65 MJ / 1.5 kW = 7.3 min [C], ready at t ≈ 31–33 as written).
What does not hold is the frame:

| | B2 Schnitzel (limit 67–68) | B3 Frikadellen (limit 50) | B6 soup for 6 (limit 60) | B8 Pfannkuchen (limit 50) | Effect of the phase plan (3.2) and the purchase list (5.6) [E] |
|---|---|---|---|---|---|
| K1 | 62 | 40–42 | 47 | 42 | B2 fries two pans at once: under 2 × 2.7 kW channels with boiling on one, COK-005 recovery is lost → serialise, **≈ 72 > 67.5** |
| K2 | 52 | 37 | 45 | **48** | B8 has 2 min; K/H busy 28 min without pause in B3 |
| K3 | 32 | 34 | 37 | 42 | drum flash-wash (3 kW) at t 14–23 of B3 collides with frying and boiling; stock paste and bought beans (B6) not permitted |
| K4 | **62** | **48** | 50 | 42 | B3 has 2 min, B2 ≈ 6 min: both break once serialised; B6 needs bean trimming (+5–10 min) |
| K5 | 55 | 32 | 45 | 38 | the frying book is shared by the two pan dishes of B2 |
| K6 | 42 | 35–40 | **54** | 44 | B6 has 6 min and bought-trimmed beans; wells stall under oven meals |
| K7 | 55 | 43 | 50 | **47** | B7 has 4 min, B8 3 min; cold-cabinet boost adds 10 min to an order "now" |
| K8 | 48 | 34 | 44 | 38 | tank and boiler heating during cooking is not available (3.2) |

Two explorers applied the wrong limit: PERF-001 adds 10 min for 6 persons, so K1's B6 (47/60) and its B3 for
six (54/60) are inside, not "without margin". Conversely, B7's limit is taken as 44 (K7), 44.5 (K1) or 79
(K3, K4, K5) depending on whether steak with oven fries or with baked potato is meant; PERF-002 c needs one
reading.

### 4.2 Transport and dock load per full meal

TRN-005 allows a mean of 10 s per transfer plus ≤ 5 s at each end, i.e. ≈ 20 s per move. Moves per full
meal [E]: ≈ 15 boxes in and out (30 moves), ware between cell and washer, and 3–4 vessels to serving and
back.

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Ware moves through transport [D/E] | ≈ 57 (12 in, 45 out) | ≈ 6 | ≈ 28 | ≈ 30 | ≈ 28 | 0 | ≈ 27 | ≈ 2 (chip box) |
| Transport moves per full meal [E] | ≈ 95 | ≈ 44 | ≈ 66 | ≈ 68 | ≈ 66 | ≈ 38 | ≈ 65 | ≈ 40 |
| Transport time per meal at 20 s [C] | ≈ 32 min | 15 | 22 | 23 | 22 | 13 | 22 | 13 |
| Ports (height, wall) [D] | left wall, deck level | top left 1650–1980; shaft serving side | dock z 1750; vessel port z **120–290** right | left z 1400–1650; right z 700–950 | left or ceiling z 1500–1750; side wall | left z 900–1200; front-left or "from the hob" | above oven left z 1300–1600; right at bench | left wall z 1150–1400; ceiling dosing port |

K1 is the only concept whose transport load approaches saturation inside a 40-min meal (B3), because its 12
vessels, rails and cups must arrive through one port at the start while the first boxes are also needed; the
"ware in, 0–4 min" rows of its walk-throughs require one item every 20 s with nothing else moving. For the
others the transport is not the bottleneck; **the single dock is**. Every concept has one dock position; a box
cycle (arrive, lid off, tilt or reach, weigh, lid on, leave) takes 40–90 s [E], and B3 needs ≈ 12 boxes in its
first 15 minutes: 50–100 % dock occupancy before a retry. A buffer position at the dock (TRN-008) belongs in
every concept. A drink requested during a meal (SRV-024) adds ≈ 4 transport moves and must not use the dock.

### 4.3 Consecutive meals, the full day and the night

| | Next meal can start (PERF-005: 30 min) | All clean (PERF-005: 90 min) | Second full meal for 6 after 2 h (CAP-006) | Two light meals 15 min apart (CAP-007) | Dinner served 19:00: clean by [C] |
|---|---|---|---|---|---|
| K1 | **43–50 min** (relays + 33 min wash-down) | **≈ 3 h** (three chamber loads) | needs a second ware set of ≈ 45 items: store not designed | yes (three hands) | **≈ 22:00**, into quiet mode for later dinners |
| K2 | 10 min (first stations) | 55 min | yes, except 14 single-instance types (4.5 min lathe cycle each in the critical path) | yes; K/H is the bottleneck | 19:55 |
| K3 | drum 3 min rinse; belt 12 min wet, 35 dry | 55–75 min (chamber) | yes (31 ware items ≈ two sets) | only if one drum job each | ≈ 20:15 |
| K4 | 12–15 min | 55–75 min (chamber) | yes | one mat line: second meal queues | ≈ 20:15 |
| K5 | 15 min for the column | 55–75 min (chamber) | yes (ware set ×2.6) | yes | ≈ 20:15 |
| K6 | 0 (wash as you go) | 15–20 min | yes | yes | 19:20 (if the wells had power, 3.2) |
| K7 | flat ware 25–30 min; cold stack recovery 4–13 min | 55–75 min (bulky ware) | yes | one gantry | ≈ 20:15 |
| K8 | **25–35 min** (full wash, tub closed) | 35 min | yes | only if both are prepared before the wash; otherwise +10 min short wash | 19:35 |

A full reference day (breakfast cold/light ≈ 07:00, light warm lunch ≈ 12:30, full dinner ≈ 19:00) fits
every concept on time, **except the night rule for K1** and, for dinners after ≈ 20:30, the chamber
concepts (K3, K4, K5, K7) whose last load runs past 22:00. The binding day-level limits are not time but
water (3.3), stoppages (4.6) and, for K6 and K8, power for hot water (3.2).

### 4.4 One and six persons

| | 1 person (B12, scrambled eggs and toast) [D] | 6 persons: bottleneck [D] |
|---|---|---|
| K1 | 9 min, **60 moves, 23 L, 1.5 kWh** of cleaning | the hands: every per-piece operation scales linearly; B3 for 6: 54/60 min |
| K2 | 9 min, 20 moves, 8 pieces, 6 L, 12 min of washing | K/H: dicing and forming grow by half |
| K3 | 8 min, 14 moves; belt used, belt wash follows | drum busy 80 %; any retry breaks B3 |
| K4 | 9 min, 12 moves | one mat line for all flat work |
| K5 | 7 min, 9 moves | frying book shared; tube 140 limits roast size |
| K6 | 9 min, 34 + 13 moves, 2 wash loads | Rouladen for 6 split over two vessels; breakfast for 6 marginal (12 pancakes 27 min) |
| K7 | 9 min, 25 moves | second tempered batch 20–30 % slower |
| K8 | 9 min, 22 moves, **12 L short wash**: "a 6-minute dish occupies a 1.75 m machine and one wash" | three griddle batches for B2 and B3 |

The 1-person case is where the all-ware and wash-down concepts are least efficient per plate: K1 spends
23 L and K8 12 L on one person's eggs, against 6 L for K2 and ≈ 7 L for K6.

### 4.5 Plating and hot-holding

SRV-009: all dishes of one course for six at the hatch within 4 min. A main course of four components for six
is 24 placements plus 6 sauce and 6 garnish actions: **one action every 6–7 s** [C] — beyond one manipulator
with ring moulds and ladles (≈ 15–30 s per component per plate, R5 §9.2); it needs either two heads or plates
moving under fixed dispensers. No concept plans for it, and all hand the problem to the serving module in
their cooking vessels:

| | Hands over [D] | Could the cell plate itself? | Hot-holding [D] |
|---|---|---|---|
| K1 | lidded vessels through the port | **yes**, if plates reach the bench (A10); three hands, ladle, tongs, turner | oven at 70–80 °C or a hob at low power |
| K2 | R260 vessels, baskets, GN trays, platter discs; plus "the final merge of pasta and sauce" | **no**: cannot pick and place a piece | any free hob |
| K3 | vessels at R3 (z 120–290, 1.5 kW warm-hold) | partly: the belt nose lays flat items onto a dish ("dish slide") | **R3 is the only defined hot hand-over position of all eight** |
| K4 | tabbed vessels through the right-wall port | partly: NOSE lays flat items; no ladle yaw | not defined |
| K5 | vessels by the shuttle; fried pieces sit on fixed book leaves and must first go to a tray | no (shuttle pours and carries) | not defined |
| K6 | tanged GN trays and pots, "or directly from the hob" | yes, serially (≈ 24 × 10 s = 4 min for a main for six) | hob positions |
| K7 | vessels through the right wall at bench height | partly (gripper and trays) | oven, hob, or the T1 coil (55–70 °C) |
| K8 | GN vessels up to 8 kg at the left hatch | in principle (scoop, turner), but a clean plate entering the soiled tub is an HYG-005 problem | hob positions |

Holding on the hob blocks the positions the next course needs (CAP-003) and, with the phase plan, the power.
The serving module as the requirements now stand (hatch, dish store, washer, drinks) would have to add a
manipulator as capable as the cell's, a utensil set, a heated holding shelf and a wash route for its
utensils: that is a second process cell. **Plating belongs in the process cell**, with warmed plates brought
in by the transport, and a defined heated hand-over shelf like K3's R3.

### 4.6 Handling reliability and the human's ten minutes a week

HUM-011 allows 10 min per week for waste, consumables, wear parts, stoppages and the annual service. The
fixed items already take ≈ 8 min [C]: waste 2 × 2 min, consumables 5 min per 30 days (1.2), wear parts 2 × 15
min per year (0.6), annual service 2 h (2.3). **That leaves ≈ 2 min per week for stoppages (HUM-009, 5 min
each), i.e. ≤ 0.4 stoppages per week** — the same as REL-001's 2 % of 21 meals. Moves per week at 1 full,
1 light (½) and 1 cold (¼) meal per day = 12.25 × moves per full meal [C]:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Moves per full meal [D] | 175 | 48 | 36 | 35 (+ 300–900 mat strokes) | 34 | 100 | 120 | 105 (incl. 40 wash moves) |
| Moves per week [C] | 2140 | 590 | 440 | 430 | 420 | 1225 | 1470 | 1290 |
| Stoppage minutes per week at 10⁻³ unrecovered failures per move [C] | **10.7** | 3.0 | 2.2 | 2.1 | 2.1 | **6.1** | **7.4** | **6.4** |
| Unrecovered failure rate per move that fits the budget [C] | 2 × 10⁻⁴ | 7 × 10⁻⁴ | 1 × 10⁻³ | 1 × 10⁻³ (mat strokes not counted) | 1 × 10⁻³ | 3.4 × 10⁻⁴ | 2.9 × 10⁻⁴ | 3.3 × 10⁻⁴ |

Process failures (an egg shell, a roll that opens) need their own share, so the real limits are about half.
The low-move concepts (K2–K5) sit near what closed-loop handling with a camera check and one retry can
plausibly reach; K1, K6, K7 and K8 need three to five times better. Wear and consumables: K4's mats cost
€570 per set and year [D] against MNT-007's €300 per year for **all** wear parts and consumables; K6 lists
eight human-changed wear items and 75 g of detergent a day (RES-008: 60 g); K2, K6 and K7 run a second wash
chemistry in the cell next to the dish washer, which HUM-004 turns into two refill points unless WSH-009's
common supply is imposed.

### 4.7 Incremental build path and graceful degradation

| | First useful increment | Single points of failure | Degraded mode (MODE-006) |
|---|---|---|---|
| K1 | not before the welded cell, ceiling seams and three turrets exist (the two-turret variant misses B2, B6) | seams (no fallback, explorer) | T1/T2 down: most meals slower; T3 down: no oven, left hob column only (≈ half the menus) |
| K2 | Wender + hob + dock: a cooking machine; stack tools added later | the single carriage; K/H press station | carriage down: nothing moves |
| K3 | drum + shuttle + shelves (a stirring and boiling machine); belt later | vessel shuttle (explorer: "decides whether K3 exists"); drum | belt down: no flat work; drum down: boiling in pots on R1 |
| K4 | mat line alone is testable, but the hob row needs arm C | arm C; the mat line | mat torn: next cassette; arm C down: nothing reaches the hob |
| K5 | **hob + shuttle + oven = a cooking module; the column is a separate addition** | shuttle | column down: no dicing, cooking continues from whole ingredients the shuttle can handle |
| K6 | **mast + hob + wells; cassettes added one by one; all bought ware** | the one manipulator | manipulator down: nothing moves |
| K7 | a K6-like gantry cell; the cold cabinet is an add-on booster | gantry | cabinet down: meals without tempering (explorer: 5 of 12 benchmarks use it) |
| K8 | rig first (a week); then the whole tub at once | door gantry; tub wash pump (the tub is also the washer) | one head down: one puck; wash failure: cell unusable (hygiene) |

K5 and K6 have the best build paths; K1 and K8 the worst (monolithic weldments that must work as a whole).

---
