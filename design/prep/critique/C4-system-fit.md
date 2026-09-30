# C4 — Critique of the preparation concepts K1…K8: system fit and operations

Round P4, critic C4. View: system architect and operations planner. The question is not "does the cell
work" but "does the whole machine still fit, pay and run a household's day with this cell in it".

**Decision state used.** DECISIONS #1–19 as of commit 6f78ec3, in particular: #6 used dishes, glasses and
cutlery come back at the hatch and the machine washes them; #8 and the purchase list (requirements 5.6) — the
machine washes, peels and cuts produce, stock is made in house (UO-96), frozen peas and grated cheese remain
permitted; #11 height up to 2200 mm; #13/#16/#17 the machine stores cooking ingredients incl. chilled cooking
liquids and pours drinks it stores, a separate household fridge is allowed, the MVC must fit **≤ 3600 mm**;
#18 the **regular household is 2 persons** (2 warm meals a day); #19 **at most 4 persons per meal**. The
requirements were aligned to #18 (PHY-004 ≤ 3600 M / ≤ 3300 S with an allocation of 1.2 m for the process cell;
CAP-020…025: 143 box positions; RES-001 ≤ 3.0 kWh and RES-005 ≤ 35 L per 2-person meal; RES-002 ≤ 7 kWh and
RES-006 ≤ 75 L per day; SRV-022/-024 drinks; WSH-001/-002 dish washing) but not yet to #19 (CAP-001, -004, -006,
-030, -031, COK-016 and SRV-009 still say 6 persons). Where they disagree, the decision is used.

The concepts were written earlier, against 3.6 m for the whole household's storage, 2000 mm, a human-loaded
dish washer, pre-cut and frozen produce, a 4-person reference household and 6-person sizing. They are judged
against the current state; where the change helps a concept, that is said too.

Other yardsticks: PHY, UTL, CAP, PERF, RES, NOI, ENV, MOD, TRN, SRV, HUM, BLD, MNT, REL; research R3 (storage),
R5 (cooking, plating, washing), R7 (ingestion); the exploration brief; the catalogue's rules and conflicts
X1–X16.

Markers: **[D]** taken from the concept document; **[C]** recomputed by me from the document's own figures or
from physics; **[E]** my estimate. Severity: **fatal** = a mandatory requirement cannot be met without giving
up a defining element of the concept; **major** = a mandatory requirement or a whole-machine budget is missed
as designed; **minor** = weakness with a known remedy. "Fixable" = fixable while the concept stays the same
concept.

Scope: for every concept I read the definition and layout, the numbers, the cleaning totals, the benchmark
summary, the requests to the architect and the verdict in full, and the B1–B3 walk-throughs of K1, K3, K5 and
K8 step by step; the rest by search. Nothing here was tested; the budget figures are estimates with stated
inputs, meant to be recomputed by the architect.

---

## 1. Summary

| | Score (1–10) | Fatal | Major | Cell width as drawn [D] | Cell cost, comparable [C] | One-line verdict |
|---|---|---|---|---|---|---|
| K1 ceiling turret | **2** | 2 | 8 | 2270 | ≈ 32 k€ | Widest, dearest, wettest and slowest to turn round; every whole-machine budget blown by about 2× |
| K2 vessel stack | **5** | 0 | 8 | 1600 (+300 rack) | ≈ 25 k€ | Most self-contained cell (washer, rack, oven inside; transport only at the port), but the sideways oven does not fit and nothing can plate |
| K3 drum and belt | **4.5** | 0 | 8 | 1450 | ≈ 23.5 k€ | Narrowest all-inclusive cell and few moves; oven does not fit, ports at 120 and 1750 mm, 35 actuators, 19 dynamic seals, water over |
| K4 shuttle mat | **4.5** | 0 | 8 | 1560 | ≈ 19.5 k€ | Cheap and compact on paper; mats cost twice the whole yearly wear budget, oven above the hob at head height with no human access |
| K5 ram and die | **5** | 0 | 7 | 1770 (1170 without oven) | ≈ 21 k€ | Best build path (column separable from the hob), few moves; highest in-place water, 6 kW boiler, ware store lives in the oven bay |
| K6 loose ware, wells | **3.5** | 1 | 7 | 2595 | ≈ 23 k€ | Best turnaround and proven parts, but 2.6 m is 72 % of the machine, and wash-as-you-go gets no power while the oven heats |
| K7 state change | **2.5** | 1 | 7 | 2280 | ≈ 32 k€ | A booster bolted onto a full kitchen: dearest cell, a second refrigeration circuit, 120 moves per meal |
| K8 sealed tub | **6** | 0 | 7 | 1750 (1150 without oven) | ≈ 18.5 k€ | Best system fit: smallest cell, cheapest, washes its own ware, lowest water and energy; blocked 25–35 min after a meal, power claim internally inconsistent |

**Budget verdict.** No concept fits the machine. The modules other than preparation and cooking need **2.25 m
of wall at the floor and ≈ 2.7 m realistically** (storage for CAP-020…025, dish washing, hatch, drinks,
ingestion B), **€17–23 k of parts** and **≈ 25 L of water a day**. PHY-004 (≤ 3600 mm) therefore leaves the
process cell **0.9–1.35 m including the oven** — PHY-004's own allocation is 1.2 m. The cells as drawn take
1.45–2.6 m (1.2–2.2 × the allocation), €18.5–32 k (3–15 × the €2–7 k the M cost target leaves) and
43–127 L of in-cell water a day. The machines that result are **3.7–5.3 m wide, €36–55 k and 68–152 L per
day** against 3.6 m, €25 k (S €15 k) and 75 L. **Per 2-person meal no concept meets RES-005 (35 L) or RES-001
(3.0 kWh)**; K8 comes closest (42 L, 3.1 kWh). Every cell claims the whole 3 × 16 A connection for itself,
and every cell turns a 595 mm wide oven across a depth of at most 555 mm. The honest allocation to
preparation plus cooking is **≤ 1200 mm including the oven, ≤ 5.6 kW for all four hob positions together
(oven on its own phase, no water heating while it heats), ≤ 15 L of in-cell water per meal and ≤ €9 k of
parts without the oven** — and BLD-004 still needs a customer ruling (section 9).

**Round-2 recommendation in one line.** Carry K8 (tub, washer and cell in one) and K5 (separable press column)
forward as the system-fit base, with K2's inverter-on-a-lift as the hybrid candidate for pan work; drop K1 and
K7 as whole systems; keep K6 only as the reference for proven ware and washing; re-run the survivors against
fixed budgets, one ware, port and oven standard, 4-person maximum vessels, and in-cell plating (sections 8, 9).

---

## 2. Cross-cutting findings: the orchestrator's list verified, and what it missed

The previous attempt's summary (a)–(h) was checked against the documents. **C** confirmed, **M** confirmed
with a correction, **R** rejected.

| # | Claim | Verdict | Evidence and correction |
|---|---|---|---|
| a | Almost every concept claims 10.3–11 kW for the cell alone; single 3.5 kW zones exceed 3.4 kW per phase; no phase plan anywhere | **C**, and worse | Managed peaks [D]: K1 7 kW hob + 3.3 oven + 1.5 drives = **11.8 kW** [C]; K2 11 (22 installed); K3 11 plus a fifth heated position H0 of 3 kW not in the sum; K4 11; K5 11 (its oven, 3.5 kW, is itself > 3.4); K6 ≤ 10.3 (11.4 kW hob installed); K7 10.5; K8 claims ≤ 10.3 but its own terms give 7 + 3 + 0.8 = **10.8** [C], and its §6.2 heats tank and boiler "during the cooking phase" while §7 puts them "outside the cooking peak". Single-phase zones of 3.5 kW: K1, K2, K4, K7, K8. No document assigns a load to a phase. UTL-010 allows ≤ 10.3 kW and ≤ 15 A per phase **for the whole machine**, and UTL-011 ranks cold storage above cooking. Section 3.2 |
| b | Every concept merges preparation, cooking and part of washing into one cell with its own manipulator, bypassing transport (TRN-002) | **C** | Internal handlers: K1 three turrets, K2 Wender, K3 vessel shuttle, K4 arm C, K5 shuttle (its request 11 asks TRN-002 to allow it), K6 mast, K7 gantry, K8 pucks. Washing inside: K2 lathe, K6 wells, K7 slot washer, K8 the tub; K1, K3, K4, K5 clean fixed surfaces in place. MOD-001 allows a shared "process cell" for preparation, cooking and portioning but not washing, and no concept keeps its cooking part separately designable. The requirement is the problem: routing 30–175 moves per meal through the shared transport would break TRN-005/-008. Ruling needed (R-1, section 8) |
| c | Cells take 1450–2600 mm of the ≤ 3600 mm wall and €16–32 k of the €25 k | **C** | Widths [D] 2270, 1600, 1450, 1560, 1770, 2595, 2280, 1750 = 1.2–2.2 × PHY-004's allocation of 1.2 m. Costs as stated [D] 14–32 k€ on different bases (with or without oven, dock, washer); comparable (3.5): **€18.5–32 k**. All cells also break PHY-003 (no module wider than 1200 mm) |
| d | Water per day exceeds 110 L in most concepts at three meals a day | **M** (limit now 75 L at two meals) | For the 2-person household: six of eight over RES-006 (K1 ≈ 152 L, K3 ≈ 107, K5 ≈ 101, K7 ≈ 92, K2 ≈ 80, K4 ≈ 76), K6 ≈ 73 and K8 ≈ 68 just under [C/E, 3.3]. Per meal **none** meets RES-005 (35 L). Cleaning hardly shrinks with persons (the requirement's own rationale), so the 2-person household pays the 4-person cleaning bill. No concept counts box washing, produce washing (except K4), glasses (SRV-022) or unscraped dishes (DEC-6) |
| e | Sideways 60 cm ovens (≈ 595 wide) do not fit 540–555 mm internal depth | **C, all eight** | K1, K2, K3, K4, K5, K7, K8 turn a built-in oven 90°; K6 states "its 595 width lies along Y" in a bay of 555 inner depth. Inner depth at the oven: K2 520, K3 ≈ 500, K4 ≈ 510, K5 540, K6 555, K7 550; K1 and K8 at best the full 600 outer with zero skin. Also: the oven's cooling-air slots sit in its front, which now faces the wet, greasy cell; its service side faces sideways, so it cannot be exchanged from the front (MNT-001); four concepts replace the door of a certified appliance (BLD-008) |
| f | Most concepts have single-instance ware, so a second meal waits 55–75 min for a washer | **M** | True where ware goes to an R6-type chamber (55–75 min): K1 (three loads, ≈ 3 h to all clean), K3, K4, K7 (bulky ware), and K2's 14 single-instance types. Not true for K5 (ware set ×2.6), K6 (3.5 min wells) or K8 (the tub washes itself in 25–35 min but is blocked meanwhile). CAP-006 (second meal 2 h later) is met by all but K1; **PERF-005 (next meal possible within 30 min)** is missed by K1 and marginal for K8 |
| g | Plating is pushed to "serving" everywhere and hot-holding is undefined | **C** | K1 open issue 12, K2 R8, K3 port R3, K4 A7, K5 request 7, K6 request 5, K7 transport request, K8 A-4: all hand over the cooking vessel (up to 8 kg). K2 also hands over "the final merge of pasta and sauce". Nobody checks SRV-009 (a course at the hatch within 4 min: for 4 persons one plating action every 10 s, 4.5). Hot-holding is "a free hob at low power" or "the oven at 70–80 °C", i.e. on the positions the next course needs; only K3 defines a heated hand-over shelf |
| h | Noise has almost no numbers | **M** | K4, K5, K6, K7, K8 give dB(A) estimates for short loud operations; only K6 gives one for washing (52–56 dB(A) for 25–30 min per meal, above NOI-002's 48). K1 gives none. Nobody addresses quiet mode (NOI-004, MODE-002 from 22:00), although K1's dinner clean-up runs to ≈ 22:00 |

Findings the list missed (all eight unless stated):

| # | Finding | Severity | Why it matters |
|---|---|---|---|
| i | **No concept pours a drink** (SRV-022; SRV-024: glass at the hatch ≤ 60 s when idle, **≤ 3 min during a meal, meal delayed ≤ 2 min**). A glass of milk or juice needs an opened carton kept upright in the chilled store, a pour, a glass from the dish store, the hatch, and the carton back: ≈ 4 transport moves [E]. Through the cell it would wait for K8's 25–35 min wash, K1's 45 min wash-down or a busy manipulator; it must be a pour station on the serving side, which nobody owns yet | major | Daily use; transport load during meals (TRN-008) |
| j | **The purchase list (5.6) invalidates some benchmark shortcuts.** Frozen peas and grated cheese stay permitted, but bought-trimmed or frozen cut beans (B6 in K2, K3, K4, K6, K8; K5 "bought prepared"), frozen chopped herbs (K1, K2, K5, K7) and stock paste or cubes (K3 "stock paste slug", K4 "stock cup") are not. B6 margins were 0–16 min | major | Time claims of B6 and of every stock-based menu |
| k | **UO-96 stock-making is a standing load nobody schedules**: a hob position for 1–4 h, ≈ 1.5–3 kWh and a strain-and-portion step per batch, roughly weekly; it fits only into idle hours (it is silent, so night is fine) and competes with the oven for the third phase (3.2) | minor | Hob occupancy, RES-002, freezer positions |
| l | **Stowed packs "arrive opened"** (K1 A6, K2 R3, K4 A5, K6 4, K8 A-3) or are converted at ingestion (K3 paste cartridges, K5 small tubes, K7 and K4 pucks): the JIT opening cell of DEC-3 and R7 §2.5 is assumed by all and budgeted by none (300–600 mm, €0.8–1.5 k, a transport round trip per pack), and the four conversion formats conflict | major | Width, cost, transport, ingestion scope |
| m | **Ports are everywhere**: box ports at z 1300–1980 in left side walls or ceilings (K1, K2, K4, K5, K6, K7, K8), K3's dock at 1750 and its vessel port at **z 120–290**, K4's vessel port at 700–950, K7's at bench height in the right wall. A side-wall port can be reached only at the joint with the neighbouring module, which must leave a transfer zone; a transport running along the machine at one height cannot reach them all | major | TRN-003, MOD-011 (one hand-over definition) |
| n | **ENV-010 (≤ 0.3 kg of moisture into the room per meal) is unaddressed.** Extraction of 60–150 m³/h [D] through an air-cooled condenser releases up to 2 kg/h [C: saturated 25 °C exhaust 23 g/m³ against room air 9.7 g/m³, × 150 m³/h]. Meeting 0.3 kg needs the exhaust dried to a dew point of ≈ 13 °C: a refrigerant dehumidifier (0.2 kWh/kg, 0.3–0.5 kW, €300–600, 20–30 L of volume) or 27 L of mains water per kg of steam (R5 §2.3) | major | Power, water, noise, and a shared unit nobody owns |
| o | **PHY-003** (modules ≤ 1200 mm on a 150 mm grid): every cell as drawn is one enclosure of 1450–2600 mm; only K8's tub (1150) and K5's column-and-hob (1170) could become 1200 mm modules | major | Modularity, delivery (PHY-012) |
| p | **Unscraped dishes, glasses and cutlery** come back at the hatch (DEC-6, WSH-001/-002: a 2-course meal's set clean within 90 min). The concepts' "10 L for the dish load" assumes a household machine loaded by a human; a machine-loaded washer with scraping and cutlery handling is a module of its own (600 mm, €1.5–7 k) | major | Width, cost, every water ledger |
| q | **DEC-19 (max 4 persons) is a gift nobody has used yet**: the 9 L pot, 8–10 L mixing, 36 cm pan, 12 Rouladen and 12 pancakes that set several cells' sizes and bottlenecks are gone. Worth an estimated 0–150 mm of width, not the 300–1400 mm needed (3.1), but it removes K6's rear-row pot problem, K1's and K2's 6-person time overruns and part of K5's tube-size limit | — (opportunity) | Round-2 dimensioning |
| r | **CAP-003 courses**: hot-holding on the hob positions blocks the dessert or second course (up to 3 courses) | minor | Scheduling |

---

## 3. Whole-machine budgets

### 3.1 Width (PHY-004 ≤ 3600 mm M, ≤ 3300 mm S; PHY-003; height ≤ 2200 mm)

PHY-004's rationale allocates ≈ 0.45 m to ambient and cool storage, 1.2 m to cold storage, **1.2 m to the
process cell**, 0.6 m to washing, ingestion B "within a front": 3.45 m. Checked against R3 [E, from R3 §3.2,
§4.1, §6 and R5 §10]:

| Module | Floor | Realistic | Basis |
|---|---|---|---|
| Ambient + cool storage: CAP-020 ≥ 70, CAP-024 ≥ 8, reserve CAP-023 ≥ 15 % → ≈ 90 positions | 450 (≈ 75–85 at 2200 mm high: marginal) | 600 (≈ 100; STOW packs need taller slots; ethylene separation) | R3: 130–168 per metre at 2000 mm |
| Chilled CAP-021 ≥ 45 and frozen CAP-022 ≥ 20 | 1200 (two 178 cm shells, 33–45 positions each: chilled marginal) | 1200 | R3 §4.1 |
| Machine-loaded dish washer with scraping and cutlery (WSH-001), hatch, dish and glass store (CAP-031) | 600, stacked: washer 0–820, hatch 850–1300, store 1300–2200 | 600 | SRV-010, UC-07 |
| Ingestion B, JIT opening cell, drink pour station, waste bins | 0 (in fronts and the top gallery) | 300 | R7 §2.5, §10; SRV-022; CAP-041 |
| Transport | 0 (overhead gallery in the 200 mm of DEC-11) | 0–150 | TRN-003 |
| Ware/box washer, if the cell has none | 0 if the dish washer is a shared commercial under-counter unit | 0–600 | R5 §10.4 option 2 |
| **Total without the cell** | **2250** | **2700** | |

The process cell's share of a 3600 mm machine is therefore **1350 mm at the floor and 900 mm realistically,
oven included** (S, 3300 mm: 1050 / 600). Whole-machine widths with each cell as drawn [C]:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Cell as drawn [D] | 2270 | 1600 | 1450 | 1560 | 1770 | 2595 | 2280 | 1750 |
| Hidden extras [C] | clean store for ≈ 110 parts not designed | rack holds 60 % → +300 (explorer) | — | — | ware store sits in the oven bay | — | chamber for bulky ware | — |
| Machine, floor (+2250) | 4520 | 3850–4150 | **3700** | 3810 | 4020 | 4845 | 4530 | 4000 |
| Machine, realistic (+2700) | 4970 | 4300–4600 | 4150 | 4260 | 4470 | 5295 | 4980 | 4450 |
| Cell ÷ allocation (1200) | 1.9 × | 1.3–1.6 × | 1.2 × | 1.3 × | 1.5 × | 2.2 × | 1.9 × | 1.5 × (1.0 × without oven) |

Height does not rescue it: the 200 mm of DEC-11 is best spent on an overhead transport gallery, and the
178 cm cold shells cannot grow. An L layout adds no wall length under PHY-004. DEC-19 is worth 0–150 mm
(finding q). **No concept fits 3600 mm even at the storage floor; K3 comes closest (3700), K8 and K5 reach
the allocation only without their oven.**

Where the oven goes decides 560–600 mm. All eight put it in the cell and turn it 90° (finding e), which does
not fit. Three honest options: (1) a front-facing oven in a transport-served column (oven 900–1355, ware or
dish store above), loaded by the transport or a small loader of the cooking module; (2) a narrower oven
(countertop combi-steam units of ≈ 490–500 mm width exist [E, unverified], none checked for 45 L, GN 2/3,
plumbing and a start without a button press, COK-023); (3) a custom cavity (loses the certified appliance,
BLD-008). Option 1 shrinks cells (K1 → 1700, K5 → 1170, K8 → 1150, K7 → 1720, K6 → 2035), but the oven column
still costs ≈ 600 mm of the allocation unless it shares a column with the dish or ware store. K2, K3 and K4
stack the oven inside and gain no width; they must re-plan the stack. In short, **the 1200 mm allocation holds
a 600 mm cell plus a 600 mm oven column, or a 1200 mm cell with the oven stacked inside and loaded by the
cell's own handler.** No explored cell is 600 mm; K8's tub and K5's column-and-hob are 1200 mm without their
oven, K3 is the only one near 1200 mm with it.

### 3.2 Power: a phase plan for the whole machine (UTL-010, UTL-011)

UTL-010 allows ≤ 15 A per phase (3.45 kW at 230 V) and ≤ 10.3 kW in total. What the rest of the machine draws
while a meal is cooked [E]: fridge and freezer compressors 2 × 0.15 kW, control and cameras 0.15, transport
and storage drives 0.2 average, cell drives 0.3–0.8, extraction and dehumidifier (finding n) 0.1–0.4: **≈ 1.0–1.8
kW**, and cold storage ranks above cooking. A household combi-steam oven heats with 3.0–3.5 kW single-phase
[R5 §2.2] and cannot be throttled from outside without aborting its programme.

The only phase plan that closes [C]:

| Phase | Loads | kW |
|---|---|---|
| L1 | hob channel A (coils 1 + 2 share one generator budget) ≤ 2.8; fridge 0.15; control 0.15; transport 0.2; extraction 0.1 | ≤ 3.4 |
| L2 | hob channel B (coils 3 + 4) ≤ 2.8; freezer 0.15; cell drives 0.3–0.5 | ≤ 3.45 |
| L3 | oven ≤ 3.3 while heating **or**, when the oven is off, water heaters (washer, boiler, tank) ≤ 3.3 | ≤ 3.4 |
| **Total** | | **≤ 10.25** |

Consequences for every concept:

1. **Four hob positions share ≈ 5.6 kW**, not 11–13 kW. COK-004 (6 L to 95 °C in 16 min: 2.0 MJ at 75 %
   efficiency = 2.8 kW [C]) is met only while the paired coil is off. 3.5 kW zones are neither needed nor
   allowed; 3.0 kW coils on 13 A, managed per pair, are the right size.
2. **No water heating while the oven heats.** K6's wash-as-you-go needs ≈ 0.26 kWh per load for the 85 °C
   rinse [C: 3.2 L × 4.19 kJ/kgK × 70 K], 7 loads per meal: ≈ 2.7 kW on average over a 40-min meal. It gets
   0 kW during oven meals and stalls once its 8 L boiler is drawn down. K8's tank and boiler (8 kW), K5's 6 kW
   boiler, K1's 2 kW sump heater and K4's 3 kW wash heater plus 2 kW steam wait likewise, and so does the
   dish washer.
3. **Time claims were made at full power.** Menus with two pans frying at once (B2 everywhere) lose COK-005
   recovery when the pans share a channel with boiling water (4.1).
4. The rest of the machine is not free: if the cell takes its claimed 10.3–11.8 kW, the cold store is shed in
   every meal, contrary to UTL-011.

### 3.3 Water (RES-005 ≤ 35 L per 2-person meal; RES-006 ≤ 75 L per day)

Reference day for 2 persons: one full warm meal and one light warm meal (CAP-002; breakfast goods stay
outside, DEC-16). Cell and ware figures are the concepts' own for a full meal [D] — sized for 4, but
cleaning hardly scales with persons; light meals are scaled by me [E]. Added to every concept [E]: dishes,
glasses and cutlery 8–10 L a day (5 per meal), cooking water 4 (2), box washing 3–8 (2), produce washing 4 (2;
only K4 counts it), hatch, transport and waste wash-down 3: **≈ 25 L per day, ≈ 11 L per meal**.

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Full meal, cell + ware [D] | 92 | 38 | 42.5 + 6 (half the daily wash) | 33.5 | 50 | 35 | 41.5 | 31 |
| **Per reference meal (+11) [C]** | **103** | 49 | 59.5 | 44.5 | 61 | 46 | 52.5 | **42** |
| RES-005 (35 L) | 2.9 × | 1.4 × | 1.7 × | 1.3 × | 1.7 × | 1.3 × | 1.5 × | 1.2 × |
| Light warm meal, cell + ware [E] | 35 | 17 | 27 + 6 | 17 | 26 | 13 | 25 | 12 |
| **Machine per day [C]** | **≈ 152** | ≈ 80 | ≈ 107 | ≈ 76 | ≈ 101 | ≈ 73 | ≈ 92 | **≈ 68** |
| RES-006 (75 L) | 2.0 × | 1.07 × | 1.4 × | 1.0 × | 1.35 × | 0.97 × | 1.2 × | 0.9 × |

The largest single item in K1, K3, K4, K5 and K7 is the external chamber load (17–20 L, R6). The lever is one
shared commercial under-counter washer with 2.4 L of rinse per rack (R5 §10.1) for dishes, boxes and ware,
which brings a load to ≈ 5 L plus a share of the tank, and fewer items per meal.

### 3.4 Energy (RES-001 ≤ 3.0 kWh per 2-person meal; RES-002 ≤ 7 kWh per day)

Cleaning energy per meal [D] plus cooking for 2 (≈ 0.9 kWh), a share of the dish wash (≈ 0.45) and
dehumidification (0.05–0.2) [C]; per day: full meal + 0.6 × full meal for the light one + cold storage 1.2 +
idle 0.3 [E]:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Cleaning per meal [D] | 5.9 | 1.8 | 2.85 | 2.15 | 2.5 | 2.3 | 2.9 (incl. cold cabinet) | 1.7 |
| Per reference meal [C] | **7.3–7.5** | 3.2–3.35 | 4.25–4.4 | 3.55–3.7 | 3.9–4.05 | 3.7–3.85 | 4.3–4.45 | **3.1–3.25** |
| Per day [C] | ≈ 13 | ≈ 6.8 | ≈ 8.4 | ≈ 7.3 | ≈ 7.9 | ≈ 7.6 | ≈ 9.0 | ≈ 6.6 |

All miss RES-001; K8 and K2 by 5–10 %, K1 by 2.5 ×. Only K2 and K8 stay inside RES-002.

### 3.5 Cost (BLD-004: MVC ≤ €25 k M, ≤ €15 k S)

The rest of the MVC in parts [E, from R3 §2.2, §4.1, R5 §6.1, §9, §10.1, §11, R7 §10]:

| Module | Low | High | Note |
|---|---|---|---|
| Ambient and cool storage with ≈ 90 boxes and lids | 2.5 | 3.5 | carriage, racks, enclosure, hatch, lid station |
| Cold storage: fridge and freezer shells, hatches or vestibules, cold-rated racks and carriages, ≈ 75 boxes | 4.7 | 6.6 | shells 2.2–3.1 |
| Transport, 3.6 m, 8 kg payload | 2.4 | 3.5 | |
| Hatch, dish and glass store, dish handling (no plating manipulator) | 1.5 | 3.0 | + 2–4 if serving must plate with its own manipulator |
| Machine-loaded dish washer with scraping and cutlery (WSH-001) | 1.5 | 7.0 | household with door drive and rack loader, or commercial under-counter |
| Ingestion B, JIT opening cell, drink pour station | 1.5 | 2.5 | |
| Frame, utilities (softener, break tank, drain lift, leak sensing), electrical, safety, extraction and dehumidifier | 2.5 | 4.0 | |
| Control hardware, UI | 0.8 | 1.5 | |
| **Total without the cell** | **≈ 17.5** | **≈ 31.5** | mid ≈ 23 |

Cell costs made comparable: the explorer's figure [D] + a controllable combi-steam oven at €3.5 k where
excluded or under-priced (R5: €2.3–5.5 k) + the dosing front end (≈ €1.0–1.2 k) where excluded [C]:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| As stated [D] | 27.5 without oven, dock | 24 incl. oven 2.6, lathe | 20 without oven | 16 without oven | 17.7 without oven | 21.9 incl. oven 2.5, washer | 32 incl. oven | 14 without oven, dock |
| **Comparable [C]** | **≈ 32** | **≈ 25** | **≈ 23.5** | **≈ 19.5** | **≈ 21** | **≈ 23** | **≈ 32** | **≈ 18.5** |
| Machine total, low / mid [C] | 49.5 / 55 | 42.5 / 48 | 41 / 46.5 | 37 / 42.5 | 38.5 / 44 | 40.5 / 46 | 49.5 / 55 | 36 / 41.5 |

**How much can preparation plus cooking honestly take?** At the M target (€25 k) the rest of the machine
leaves **€2–7 k** for the cell including hob and oven; at the S target (€15 k) nothing — the S target is
unreachable with any concept and any storage that meets CAP-020…025. No concept is within a factor of 2.5 of
the M share. A defensible design-to-cost target for round 2 is **≤ €9 k for preparation and hob without the
oven** (roughly a quarter of a €36–40 k machine), with the oven (€2.5–4 k) budgeted in the cooking part;
BLD-004 itself needs re-baselining by the customer.

### 3.6 Noise, heat and steam

| | Loud operations [D] | Washing [D] | Quiet mode (NOI-004, MODE-002 from 22:00) [C] |
|---|---|---|---|
| K1 | not estimated; blender 6000 rpm, ram strokes, 600 rpm basket | three 5 bar lances on 5 m² of steel for 10 min, "will probably exceed 48"; three chamber loads after dinner | dinner at 19:00 → not clean before ≈ 22:00 |
| K2 | rasp peeling 70–75 at source, 2 min | lathe 54 min after the meal, needs an insulated chamber | fine |
| K3 | rumbler 3–4 min, knives 3000 rpm, spin 480 rpm; B3 and B6 exceed NOI-003's 5-min budget | drum and belt 12 min wet, 35 min dry | fine |
| K4 | blade landings 62–66 through the door, ≤ 2 min | steam gate, pump | fine |
| K5 | produce cracking through grids 65–70, rasp can 60 for 3 min, mixer knocking at 3 Hz | tubes during the meal | fine |
| K6 | blade 65–70, < 2 min | **52–56 dB(A) for 25–30 min per meal** (NOI-002: 48) | fine |
| K7 | bow knife 65–70 for 1–4 min, blender 70, extraction 55, compressor 40 | slot washer 25 min per meal | compressor cycles at night |
| K8 | chopper 65–70 for seconds | jets on the 1.5 mm door skin, **which faces the room**; 48 "not assured" | full wash 25–35 min after every dinner |

Night is a scheduling problem: a yeast-dough dish for an early meal kneads inside the quiet window, and a
dinner after ≈ 20:30 pushes the chamber concepts' last load (K3, K4, K5, K7) past 22:00, where MODE-002 defers
it and HYG-030 (wash within 60 min) is broken; for K1 this happens after every dinner.

**Heat and steam.** Only K1 states a heat release (0.3–0.5 kW during cooking); ENV-012 asks it of every module.
Nobody sizes the condenser (finding n). Whole machine: 6–9 kWh a day end up as heat, ≈ 1–1.5 kW during a
meal, plus 0.3–1.5 kg of steam per meal for 2–4 persons that must be condensed to meet ENV-010.

---

## 4. Operations

### 4.1 Benchmark times, re-checked

The explorers' times [D] assume full power on every position, no retry, the old purchase rules, and a box at
the dock whenever wanted. Spot checks of the arithmetic held (e.g. K1 B3: 1 kg potatoes with 1 L of water on
a 2.0 kW position boil after 0.65 MJ / 1.5 kW = 7.3 min [C], ready at t ≈ 31–33 as written). The frame does
not:

| | B2 Schnitzel (limit 67–68) | B3 Frikadellen (limit 50) | B8 Pfannkuchen (limit 50) | Effect of the phase plan (3.2) and the purchase list (5.6) [E] |
|---|---|---|---|---|
| K1 | 62 | 40–42 | 42 | B2 fries two pans at once while potatoes boil: on 2 × 2.8 kW channels COK-005 recovery is lost → serialise, **≈ 72 > 67.5** |
| K2 | 52 | 37 | **48** | B8 has 2 min; K/H busy 28 min without pause in B3 |
| K3 | 32 | 34 | 42 | the drum's 3 kW flash wash at t 14–23 of B3 collides with frying and boiling; stock paste and bought beans (B6) not permitted |
| K4 | **62** | **48** | 42 | B3 has 2 min, B2 ≈ 6 min: both break once serialised; B6 needs bean trimming |
| K5 | 55 | 32 | 38 | the frying book is shared by the two pan dishes of B2 |
| K6 | 42 | 35–40 | 44 | B6 (6 persons) had 6 min with bought-trimmed beans; wells stall in oven meals |
| K7 | 55 | 43 | **47** | B7 has 4 min, B8 3 min; the cold-cabinet boost adds 10 min to an order "now" |
| K8 | 48 | 34 | 38 | tank and boiler heating during cooking is not available |

With DEC-19, B6 (soup for 6) becomes a 4-person benchmark and loses its tightness; bean trimming for 4
(≈ 40–50 beans) is at the edge of G10's GP-102 (≤ 40 pieces). PERF-001's limits were misapplied twice: K1
counted B6 and its B3 for six against the 4-person limit, and B7's limit is taken as 44 (K7), 44.5 (K1) or 79
(K3, K4, K5) depending on whether steak comes with oven fries or baked potato; PERF-002 c needs one reading.

### 4.2 Transport and dock load per full meal

TRN-005 allows a mean of 10 s per transfer plus ≤ 5 s at each end: ≈ 20 s per move. Moves per full meal [E]:
≈ 15 boxes in and out (30 moves), ware between cell and washer, 3–4 vessels to serving and back.

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Ware moves through transport [D/E] | ≈ 57 (12 in, 45 out) | ≈ 6 | ≈ 28 | ≈ 30 | ≈ 28 | 0 | ≈ 27 | ≈ 2 (chip box) |
| Transport moves per full meal [E] | ≈ 95 | ≈ 44 | ≈ 66 | ≈ 68 | ≈ 66 | ≈ 38 | ≈ 65 | ≈ 40 |
| Transport time per meal at 20 s [C] | ≈ 32 min | 15 | 22 | 23 | 22 | 13 | 22 | 13 |
| Ports (height, wall) [D] | left wall, deck level | top left 1650–1980; serving side of the shaft | dock z 1750; vessel port z **120–290** right | left z 1400–1650; right z 700–950 | left wall or ceiling z 1500–1750; side wall | left z 900–1200; front-left or "from the hob" | above the oven, left z 1300–1600; right at bench height | left wall z 1150–1400; ceiling dosing port |

K1 is the only concept whose transport load approaches saturation inside a 40-min meal: its vessels, rails
and cups arrive through one port at the start while the first boxes are wanted; its "ware in, 0–4 min" rows
need one item every 20 s with nothing else moving. For the others **the single dock is the bottleneck**. A
box cycle (arrive, lid off, tilt or reach in, weigh, lid on, leave) takes 40–90 s [E], and B3 needs ≈ 12 boxes
in its first 15 minutes: 50–100 % dock occupancy before any retry. A buffer position at the dock (TRN-008)
belongs in every concept. A drink during a meal (SRV-024) adds ≈ 4 transport moves and must not use the dock.

### 4.3 Consecutive meals, the full day and the night

| | Next meal can start (PERF-005: 30 min) | All clean (PERF-005: 90 min) | Second full meal 2 h later (CAP-006) | Two light meals 15 min apart (CAP-007) | Dinner served 19:00, clean by [C] |
|---|---|---|---|---|---|
| K1 | **43–50 min** (relays + 33 min wash-down) | **≈ 3 h** (three chamber loads) | needs a second ware set of ≈ 45 items: store not designed | yes (three hands) | **≈ 22:00** |
| K2 | 10 min (first stations) | 55 min | yes, except 14 single-instance types (4.5 min lathe cycle each, in the critical path) | yes; K/H is the bottleneck | 19:55 |
| K3 | drum 3 min rinse; belt 12 min wet, 35 dry | 55–75 min (chamber) | yes (31 ware items ≈ two sets) | only if one drum job each | ≈ 20:15 |
| K4 | 12–15 min | 55–75 min (chamber) | yes | one mat line: the second meal queues | ≈ 20:15 |
| K5 | 15 min for the column | 55–75 min (chamber) | yes (ware set × 2.6) | yes | ≈ 20:15 |
| K6 | 0 (wash as you go) | 15–20 min | yes | yes | 19:20, if the wells get power (3.2) |
| K7 | flat ware 25–30 min; cold stack recovery 4–13 min | 55–75 min (bulky ware) | yes | one gantry | ≈ 20:15 |
| K8 | **25–35 min** (full wash, tub closed) | 35 min | yes | only if both are prepared before the wash, else + 10 min short wash | 19:35 |

The 2-person day (light warm lunch ≈ 12:30, full dinner ≈ 19:00, drinks on request) fits every concept on
time except K1 against the night rule. The binding day-level limits are water (3.3), stoppages (4.6) and, for
K6 and K8, power for hot water (3.2).

### 4.4 One, two and four persons

| | 1 person (B12: scrambled eggs, toast) [D] | 4 persons (the new maximum): what the old 6-person bottleneck becomes |
|---|---|---|
| K1 | 9 min, **60 moves, 23 L, 1.5 kWh** of cleaning | the hands scale linearly per piece; at 4 persons within the limits |
| K2 | 9 min, 20 moves, 8 pieces, 6 L, 12 min of washing | K/H still the one press station; fine at 4 |
| K3 | 8 min, 14 moves; the belt is used and washed | drum busy 80 % of B3 for 4: a retry breaks the limit |
| K4 | 9 min, 12 moves | one mat line for all flat work |
| K5 | 7 min, 9 moves | frying book shared between pan dishes |
| K6 | 9 min, 34 + 13 moves, 2 wash loads | Rouladen and breakfast problems were 6-person problems and vanish |
| K7 | 9 min, 25 moves | second tempered batch rarely needed at 4 |
| K8 | 9 min, 22 moves, **12 L short wash** ("a 6-minute dish occupies a 1.75 m machine and one wash") | two griddle batches at 4 |

The 2-person reference meal is the hard case for resources, not for time: cleaning per meal is almost the
same as for 4 persons, so every concept's water and energy per portion doubles against its own 4-person
figures. The all-ware and wash-down concepts suffer most (K1 spends 23 L on one person's eggs, K8 12 L; K2
6 L, K6 ≈ 7 L).

### 4.5 Plating and hot-holding

SRV-009: all dishes of one course at the hatch within 4 min. A main course of four hot components for four
persons is 16 placements plus 4 sauce and 4 garnish actions: **one action every 10 s** [C] (for 2 persons
every 20 s). That is at or beyond one plating head with ring moulds and ladles (≈ 15–30 s per component and
plate, R5 §9.2). No concept plans for it; all hand the problem to serving in their cooking vessels:

| | Hands over [D] | Could the cell plate? | Hot-holding [D] |
|---|---|---|---|
| K1 | lidded vessels through the port | **yes**, if plates reach the bench (A10): three hands, ladle, tongs, turner | oven at 70–80 °C or a hob at low power |
| K2 | R260 vessels, baskets, GN trays, platter discs; and "the final merge of pasta and sauce" | **no**: cannot pick and place a piece | any free hob |
| K3 | vessels at R3 (z 120–290, 1.5 kW warm-hold) | partly: the belt nose lays flat items onto a dish | **R3 is the only defined hot hand-over position of all eight** |
| K4 | tabbed vessels through the right-wall port | partly: NOSE lays flat items; no yaw for a ladle | not defined |
| K5 | vessels by the shuttle; fried pieces sit on the fixed book leaves and must first go to a tray | no (the shuttle pours and carries) | not defined |
| K6 | tanged GN trays and pots, "or directly from the hob" | yes, serially (≈ 24 × 10 s = 4 min) | hob positions |
| K7 | vessels through the right wall at bench height | partly (gripper and trays) | oven, hob, or the T1 coil (55–70 °C) |
| K8 | GN vessels up to 8 kg at the left hatch | in principle (scoop, turner), but a clean plate entering the soiled tub is an HYG-005 problem | hob positions |

Holding on the hob blocks the positions the next course needs and, under the phase plan, the power. A
serving module that plates would need a manipulator as capable as the cell's, a utensil set, a heated shelf
and a wash route for its utensils: a second process cell. **Plating belongs in the process cell**, with warmed
plates brought in by the transport, and a defined heated hand-over shelf like K3's R3.

### 4.6 Handling reliability and the human's ten minutes a week

HUM-011 allows 10 min a week for waste, consumables, wear parts, stoppages and the annual service. The fixed
items take ≈ 8 min [C]: waste 2 × 2 min, consumables 5 min per 30 days (1.2), wear parts 2 × 15 min a year
(0.6), annual service 2 h (2.3). **That leaves ≈ 2 min a week for stoppages (HUM-009, 5 min each): ≤ 0.4
stoppages a week**, about REL-001's 2 % of 14 meals. Moves per week for 2 persons, 2 warm meals a day ≈ 8.4 ×
moves per full meal [C: 7 × (1 + 0.5) × 0.8 for smaller batches]:

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Moves per full meal [D] | 175 | 48 | 36 | 35 (+ 300–900 mat strokes) | 34 | 100 | 120 | 105 (incl. 40 wash moves) |
| Moves per week [C] | 1470 | 400 | 300 | 295 | 285 | 840 | 1010 | 880 |
| Stoppage minutes a week at 10⁻³ unrecovered failures per move [C] | **7.4** | 2.0 | 1.5 | 1.5 | 1.4 | **4.2** | **5.0** | **4.4** |
| Unrecovered failure rate per move that fits the budget [C] | 2.6 × 10⁻⁴ | 9.5 × 10⁻⁴ | 1.3 × 10⁻³ | 1.3 × 10⁻³ (mat strokes not counted) | 1.3 × 10⁻³ | 4.5 × 10⁻⁴ | 3.8 × 10⁻⁴ | 4.3 × 10⁻⁴ |

Process failures (an egg shell, a roll that opens) need their own share, so the real limits are about half.
The low-move concepts (K2–K5) sit near what closed-loop handling with a camera check and one retry can
plausibly reach; K1, K6, K7 and K8 need three to five times better. Wear and consumables: K4's mats cost
€570 per set and year [D] against MNT-007's €300 a year for **all** wear parts and consumables; K6 lists
eight human-changed wear items and 75 g of detergent a day for 4 persons (RES-008: 60 g); K2, K6 and K7 run a
second wash chemistry in the cell next to the dish washer, i.e. two refill points under HUM-004 unless
WSH-009's common supply is imposed.

### 4.7 Incremental build path and graceful degradation

| | First useful increment | Single points of failure | Degraded mode (MODE-006) |
|---|---|---|---|
| K1 | not before the welded cell, the ceiling seams and three turrets exist (the two-turret variant missed B2, B6) | the seams ("no fallback inside itself", explorer) | T1/T2 down: slower; T3 down: no oven, left hob column only (≈ half the menus) |
| K2 | Wender + hob + dock = a cooking machine; stack tools later | the single carriage; K/H | carriage down: nothing moves |
| K3 | drum + shuttle + shelves (stirring and boiling); belt later | vessel shuttle ("decides whether K3 exists"); drum | belt down: no flat work; drum down: boiling in pots |
| K4 | the mat line alone is testable; the hob row needs arm C | arm C; the mat line | mat torn: next cassette; arm C down: nothing reaches the hob |
| K5 | **hob + shuttle + oven = a cooking module; the column is a separate addition** | shuttle | column down: no dicing, cooking continues |
| K6 | **mast + hob + wells; cassettes added one by one; bought ware** | the one manipulator | manipulator down: nothing moves |
| K7 | a K6-like gantry cell; the cold cabinet is an add-on | gantry | cabinet down: meals without tempering (5 of 12 benchmarks use it) |
| K8 | rig first (a week), then the whole tub at once | door gantry; tub wash pump (the tub is also the washer) | one head down: one puck; wash failure: cell unusable |

K5 and K6 have the best build paths; K1 and K8 the worst (monolithic weldments that must work as a whole).

---

## 5. Findings per concept

Findings that are shared by all eight and listed in section 2 (power, oven, ports, plating, drinks, moisture,
PHY-003, JIT opening) are repeated below only where the concept makes them worse or better.

### K1 — Ceiling turret cell

| # | Finding | Where [D] | Severity | Fixable? |
|---|---|---|---|---|
| K1-1 | **Width 2270 mm (1.9 × the allocation), 1700 for the cell alone**, set by three Ø 500 turrets whose rods reach only Ø 400 and never meet; the two-turret variant (1150/1720) misses B2 and B6. With the rest of the machine: 4.5–5.0 m against 3.6 | §1, §7 | **fatal** | no (the turret geometry is the concept) |
| K1-2 | **Every resource budget at about 2×**: 92 L and 5.9 kWh of cleaning per full meal; ≈ 103 L and 7.3 kWh per 2-person reference meal (RES-005 2.9 ×, RES-001 2.4 ×); ≈ 152 L and 13 kWh per day; everything clean after ≈ 3 h (PERF-005: 90 min); next meal after 43–50 min (30). The explorer: "misses … by about a factor of two" | §6.4, §7 | **fatal** | no (all-ware plus a 5.6 m² wash-down cell) |
| K1-3 | **Cost ≈ €32 k comparable** (27.5 k without oven, dock and washer; the hands alone 8.7 k): the cell costs more than the whole M target | §7 | major | no |
| K1-4 | Hob block 11 kW nameplate with two 3.5 kW zones; peak 11.8 kW with drives; boiler and sump heater only "not during searing" | §7 | major | yes (3.0 kW coils in pairs, 3.2) |
| K1-5 | Oven turned 90° with its mouth in the cell wall: 595 mm across the depth with zero margin, front must take wash jets (IPX5), door must not swing into the hob block, not exchangeable from the front | A4 | major | at +0–600 mm (oven column) |
| K1-6 | **Transport load ≈ 95 moves per full meal (≈ 32 min)**: vessels, rails and cups come and go through one port; "ware in" at t 0–4 needs one item every 20 s while the first boxes are also needed. The proposed deck hatch to the washer (§11.2) is a direct module-to-module hand-over (TRN-002) | A3, §5 | major | partly |
| K1-7 | ≈ 110 loose parts plus "a second set of the frequent ones": the clean store and wash racks are not designed (open issue 11); A7 pushes the store to the wash module: ≈ 0.3–0.4 m³ [E] of width nobody has | §12.1, A7 | major | only with width |
| K1-8 | 110–280 moves per meal (mean 175): needs ≤ 2.6 × 10⁻⁴ unrecovered failures per move (explorer: 1.1 × 10⁻⁴ for 4 persons) or the stoppages alone take 7 min a week (HUM-011) | §7, 4.6 | major | no (follows from the reach) |
| K1-9 | Noise not estimated; wash-down with three 5 bar lances in a steel drum; after a 19:00 dinner the machine washes until ≈ 22:00 (quiet mode) | §7 | major | partly (damping; one wash-down per day, open issue 7) |
| K1-10 | Strength: the three hands could plate (A10) and give a partial limp-home (T1 or T2 down) | A10, §9 | — | — |
| K1-11 | Z stroke has no margin at 2000 mm; DEC-11's 2200 mm removes the problem | §2.3 | minor | yes |

### K2 — Vessel stack and inversion

| # | Finding | Where [D] | Severity | Fixable? |
|---|---|---|---|---|
| K2-1 | **The sideways oven does not fit**: the hot column is 600 deep with a 45 mm rear slot and a 35 mm door, i.e. ≈ 520 mm for a 595 mm oven body; "not checked against a real model", 5 mm clearance for the roll head at its mouth. Fixing it (front-facing oven or a narrower one) breaks the claim "1600 including oven" | §1, §12 open issue 4, risk 9 | major | at +300–600 mm, or a custom oven |
| K2-2 | Rack holds 60 % of the ware; the explorer: "the cabinet grows by about 300 mm" or ware parks on idle hobs and in the lathe (4–6 extra moves). True width ≈ 1900 | open issue 1 | major | only with width |
| K2-3 | **Hobs stacked to 1980 mm** (F2 1730–1980, F1 1480–1730, S1 1180–1480): hot fat and boiling pots above head height; jam clearing by hand (MNT-005) and service at 2 m; heat and steam of the lower tiers rise into the upper ones; extraction per tier | §1 | major | partly |
| K2-4 | Installed 22 kW, "managed to 11 kW": two 3.5 kW positions; the lathe (2.5 kW) runs after cooking only | §7 | major | yes |
| K2-5 | **A second washer in the machine** (wash lathe) beside the dish washer: second chemistry, softener, dosing, a 54-min pump run after every meal that needs an insulated chamber | §6.2, §7, R7 | major | no (the lathe is the ware concept) |
| K2-6 | **Cannot place a piece**: plating, including "the final merge of pasta and sauce" and component assembly, is handed to serving, which then needs its own manipulator (+€2–4 k, + width) | §0, R8 | major | no |
| K2-7 | One carriage and one press station: K/H busy 28 min without pause in B3; carriage down = nothing moves | §5, open issue 3 | major | no |
| K2-8 | Water 38 L per full meal in the cell; ≈ 49 L per 2-person reference meal (RES-005 1.4 ×); ≈ 80 L a day (RES-006 1.07 ×); 6 L and 12 min of washing for one person's eggs | §6.4 | major | partly (four pieces per lathe tree) |
| K2-9 | Strength: the best TRN-002 fit of all eight — the transport serves only the port (≈ 20 boxes) and the serving side (≈ 44 moves per meal); washer, rack and oven are inside | R5 | — | — |
| K2-10 | 62 custom ware pieces (tri-ply cans at €90–150 each): cost and spares (MNT-008 kit ≤ €500) | §7 | minor | partly |

### K3 — Drum and belt line

| # | Finding | Where [D] | Severity | Fixable? |
|---|---|---|---|---|
| K3-1 | **The oven under the drum does not fit** (≈ 500 mm between the dry spine and the door line for a 595 mm body, turned sideways with a sliding door); the drum's swing radius (555) fixes the bay at 590, so moving the oven out adds ≈ 600 mm | §1.1, open issue 9 | major | at + 600 mm |
| K3-2 | **Vessel port R3 at z 120–290** and the dock at z 1750 on different walls: the transport must reach the floor and the top of the machine. R3 is also the warm-hold, so moving it up costs the shelf stack | §1.1, request 6 | major | partly |
| K3-3 | 11 kW "with everything on" excludes the fifth heated position H0 (3 kW deck); the drum's 3 kW flash wash runs mid-meal (B3 t 14–23) | §7, B3 | major | yes (schedule, 3.2) |
| K3-4 | Water: 24 L in place + 17–20 L chamber load + 12 L daily wash-down → ≈ 60 L per 2-person meal (1.7 ×), ≈ 107 L a day (1.4 ×) | §6.6 | major | partly (shared washer) |
| K3-5 | **35 motion actuators, 19 dynamic seals, ≈ 65 custom part types**: the highest maintenance and spares load (MNT-002, MNT-008; HUM-007 belt yearly, X13) | §7 | major | no |
| K3-6 | Peeling, chopping and spinning exceed NOI-003's 5 loud minutes in B3 and B6 | §7 | major | partly |
| K3-7 | One drum and one shuttle in series: the drum is busy 27 of 34 min in B3; the explorer rates the shuttle as the item that "decides whether K3 exists" | §5.13, risk R8 | major | no (a second drum costs width) |
| K3-8 | The dock above the shaft doses over steaming vessels (catalogue rule R8) | §1.1 | minor | yes (downdraft) |
| K3-9 | Stock paste and bought-trimmed beans are no longer permitted (finding j) | B6 | minor | yes |
| K3-10 | Strengths: narrowest all-inclusive cell (1450), 36 moves per meal, the only defined heated hand-over (R3) | §5.13 | — | — |

### K4 — Shuttle mat

| # | Finding | Where [D] | Severity | Fixable? |
|---|---|---|---|---|
| K4-1 | **Oven turned 90° above P3/P4 at z 1500–1955**, lift door, "the human has no access to it" (A9): the 600 mm Y budget is used up by the drive room, gallery, mat and door, so the 595 mm body does not fit; a hot oven above the hob at head height; not exchangeable from the front | §1, A9 | major | at + 600 mm |
| K4-2 | **Mats cost €570 per set and year** (all five once, K twice) against MNT-007's ≤ €300 a year for all wear parts and consumables together | §6.7 | major | no (the mat is the concept) |
| K4-3 | 11 kW managed (hobs ≤ 7.4, oven 3, wash heater 3, steam 2); two 3.5 kW turntable positions | §7 | major | yes |
| K4-4 | B3 48/50 and B2 62/68 have 2–6 min of margin at full power; B2 needs two pans at once and breaks when serialised (4.1) | §5 | major | partly |
| K4-5 | 300–900 mat strokes per meal are not counted as handling; their failure rate (tracking, winding, tearing, sticking) is unknown, so REL-001 cannot be estimated | §7 | major | by test |
| K4-6 | Water ≈ 44.5 L per 2-person meal (1.3 ×), ≈ 76 L a day (at the limit); 36 tabbed items through the vessel port (≈ 68 transport moves per meal) | §6.4 | major | partly |
| K4-7 | Ferritic dovetail tab for the electro-permanent magnet on all ware: a ware interface no other concept uses (X15) | A7 | minor | yes |
| K4-8 | Strength: 1100 × 450 × 300 mm of free volume under the hob deck for the ware store or a washer; replacing a mat cassette takes the human 2 min without tools (HUM-007 met) | §1, §6.7 | — | — |

### K5 — Ram-and-die column

| # | Finding | Where [D] | Severity | Fixable? |
|---|---|---|---|---|
| K5-1 | **Oven bay turned 90° with 540 mm clear depth** for a 595 mm oven: does not fit. The offered fix (oven loaded by the cooking module, cell 1170 mm) also removes the clean-ware store below the oven (tubes, dies, pistons, trays, pans, tools), which then needs a new home | §1.2–1.3, request 7 | major | yes, but the store must move |
| K5-2 | **In-place cleaning comes on top of the ware wash**: 32 L in place + 18 L chamber → ≈ 61 L per 2-person meal (1.7 ×), ≈ 101 L a day (1.35 ×) | §6.3 | major | partly |
| K5-3 | Four zones of 11 kW nameplate, oven 3.5 kW (> 3.4 kW single load), 6 kW boiler | §7 | major | yes |
| K5-4 | ≈ 96 loose Zone F parts of 44 types, including 17 dies (wire-eroded grids €250–400 each): the spares kit (MNT-008, ≤ €500) cannot hold them | §2.6, §7 | major | partly (fewer dies for 4 persons) |
| K5-5 | **Cannot plate**: the shuttle pours and carries; fried pieces sit on fixed book leaves and must be moved to a tray before hand-over | §1.1 | major | no |
| K5-6 | 8 kN ram and 600 rpm positions behind a household door: the safety case is cost and noise, not only interlocks | §2.2 | minor | yes |
| K5-7 | The frying book is shared by the pan dishes of a menu (B2) | §5 | minor | yes (schedule) |
| K5-8 | Strengths: 34 moves per meal; column and hob are separable modules (1170 mm without oven); the best incremental build path | §7, 4.7 | — | — |

### K6 — Loose ware and wash wells

| # | Finding | Where [D] | Severity | Fixable? |
|---|---|---|---|---|
| K6-1 | **Width 2595 mm = 72 % of the machine, 2.2 × the allocation**, because every station needs top access and nothing can be stacked (§7.2). Dropping a bench (−345) and the oven (−560) leaves ≈ 1.7 m, still 1.4 × | §1.2, §7.2 | **fatal** | only partly |
| K6-2 | **Wash as you go has no power while the oven heats**: 7 loads × 0.26 kWh of 85 °C rinse ≈ 2.7 kW average over a meal on the phase the oven occupies; "washer heating yields to cooking" means the wells stall after the 8 L boiler — and wet ware parks in an open well meanwhile | §6.1, §7, 3.2 | major | partly (larger pre-heated boiler: volume, standby loss) |
| K6-3 | Wells 52–56 dB(A) for 25–30 min per meal (NOI-002: 48) | §7 | major | yes, at slower cycles |
| K6-4 | 35 L per full meal (≈ 46 L per 2-person meal, 1.3 ×); 75 g of detergent a day (RES-008: 60 g) | §6.2 | major | partly |
| K6-5 | 100 gripper cycles per meal (130–145 in full menus) with one manipulator: needs ≤ 4.5 × 10⁻⁴ unrecovered failures per move (explorer: 99.993 % per cycle for 4 persons) | §7.3 | major | no |
| K6-6 | **Two washers in one machine**: dishes, glasses and cutlery have no tang and cannot hang in the wells, so DEC-6's dish washing needs its own washer; two chemistries, two softeners | §6, request 8 | major | no |
| K6-7 | Oven with its 595 width along the 555 mm bay; its door swings over the wells (interlock) | §1.2, open issue 10 | major | with width |
| K6-8 | Tool wall full, no growth margin; the 9 L pot excluded (irrelevant now, DEC-19) | §2.5 | minor | — |
| K6-9 | Strengths: 15–20 min to everything clean, the best PERF-005; bought GN ware; no fixed Zone F; the best build path | §6.2, 4.7 | — | — |

### K7 — State change and rigid handling

| # | Finding | Where [D] | Severity | Fixable? |
|---|---|---|---|---|
| K7-1 | **Cost ≈ €32 k** (preparation proper ≈ 22 k): the state change adds a refrigeration set, cold cabinet and slot washer to a full conventional kit ("a booster, not a kitchen", explorer) — alone more than the MVC's M target | §0, §8 | **fatal** | no |
| K7-2 | Width 2280 (1.9 ×); 1720 without the oven column | §1.2 | major | partly |
| K7-3 | **A second refrigeration circuit** (R290 condensing unit, brazed and charged by a refrigeration technician — BLD-005/BLD-008), 0.6 kWh a day, 14 min boost from idle and 38 min pull-down after the daily defrost; its condenser rejects 500 W into the base beside the oven | §3.4 | major | only by dropping the booster |
| K7-4 | 60 cm oven turned 90° in 550 mm inner depth; the door drops below bench level | §1.2 | major | with width |
| K7-5 | 80 moves for cooking + ≈ 40 for washing logistics = 120 per meal: needs ≤ 3.8 × 10⁻⁴ per move | §8 | major | no |
| K7-6 | Three wash systems in one machine (slot washer, chamber for bulky ware, dish washer); ≈ 52 L per 2-person meal (1.5 ×), ≈ 92 L a day (1.2 ×) | §7.4 | major | partly |
| K7-7 | 11.4 kW hob installed with two 3.5 kW positions, flash coil 1.5, steam 2, tank 2, compressor; 10.5 kW managed for the cell alone | §8 | major | yes |
| K7-8 | ≈ 105 preparation items and 27 cookware pieces; gantry keep-clear zones (oven corridor, cabinet lane, knife, press) not simulated | §8, §14.1 | minor | — |
| K7-9 | Strength: fast chilling (COK-022) and tempering as an optional module that can be added later | §3 | — | — |

### K8 — Sealed tub with magnetic pucks

| # | Finding | Where [D] | Severity | Fixable? |
|---|---|---|---|---|
| K8-1 | **The tub is also the washer: closed 25–35 min after every meal with frying**, 10 min after a short wash. Two light meals 15 min apart must be prepared before the wash; a cake after a roast waits 35 min; drinks must not go through the tub (SRV-024). PERF-005 is met narrowly | §6.1–6.3 | major | no (the defining element), but tolerable |
| K8-2 | **Power claim internally inconsistent**: §6.2 heats tank and boiler "during the cooking phase", §7 "outside the cooking peak"; 7 + 3 + 0.8 = 10.8 kW > 10.3; two 3.5 kW positions; a full wash needs 1.4 kWh of heat in ≈ 25 min (3.4 kW, one whole phase) after every dinner | §6.2, §7 | major | yes |
| K8-3 | Oven turned 90° in a 600 mm bay with its door replaced by the hatch shutter (a modified certified appliance) and its cavity floor at tub-floor level: 595 in 600 with zero skin. The offered alternative (transport serves the oven) gives 1150 mm | A-1 | major | yes |
| K8-4 | Jets drum on a 1.5 mm door skin **facing the room** for 25–35 min after every dinner; the drive gantry lives in that door beside a hot skin (thermal design not done) | §7, open issues 3, 8 | major | yes (double skin, damping) |
| K8-5 | 65 moves + 40 wash moves per meal, each through a bayonet and a magnet coupling: needs ≤ 4.3 × 10⁻⁴ per move; a decoupled puck falls into the food | §7, open issue 6 | major | by test |
| K8-6 | The transport tray enters the tub (A-3), a chamber where raw food was open: TRN-012 (gripper parts touching R-soiled zones) | A-3 | major | yes (a cell-owned tray handed across) |
| K8-7 | All magnetic and friction figures are calculated; the explorer's week of rig time (A-9, < €1000) decides the concept and should precede any architecture commitment | A-9 | major (risk) | by test |
| K8-8 | Strengths: smallest cell (1150 without oven), cheapest (≈ €18.5 k comparable), 0 dynamic seals, washes all preparation and cooking ware itself so the machine's washer handles only dishes and boxes; lowest water (≈ 42 L per 2-person meal, ≈ 68 L a day) and energy (≈ 3.1 kWh per meal); ≈ 40 transport moves per meal | §7, 3.3–3.5 | — | — |

---

## 6. Comparison table

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Cell width as drawn [D] | 2270 | 1600 (+300) | 1450 | 1560 | 1770 | 2595 | 2280 | 1750 |
| Without the oven [D/C] | 1700 | (oven stacked) | (oven stacked) | (oven stacked) | 1170 | 2035 | 1720 | **1150** |
| Machine width, floor [C] (limit 3600) | 4520 | 3850–4150 | **3700** | 3810 | 4020 | 4845 | 4530 | 4000 |
| Oven fits the depth? | zero margin | no (520) | no (≈ 500) | no (≈ 510) | no (540) | no (555) | no (550) | zero margin |
| Cell peak claimed [D] | 11.8 [C] | 11 | 11 (+3) | 11 | 11 | 10.3 | 10.5 | 10.8 [C] |
| Largest single load | 3.5 | 3.5 | 3.0 | 3.5 | 3.5 (oven) | 3.3–3.5 | 3.5 | 3.5 |
| Water per 2-person meal [C] (35) | 103 | 49 | 59.5 | 44.5 | 61 | 46 | 52.5 | **42** |
| Water per day [C] (75) | 152 | 80 | 107 | 76 | 101 | 73 | 92 | **68** |
| Energy per 2-person meal [C] (3.0) | 7.3 | 3.2 | 4.25 | 3.55 | 3.9 | 3.7 | 4.3 | **3.1** |
| Cost comparable [C] | 32 | 25 | 23.5 | 19.5 | 21 | 23 | 32 | **18.5** |
| Moves per full meal [D] | 175 | 48 | 36 | 35 (+ mat) | **34** | 100 | 120 | 105 |
| Transport moves per meal [E] | 95 | 44 | 66 | 68 | 66 | **38** | 65 | 40 |
| Next meal possible after [D] | 43–50 min | 10 | 3–35 | 12–15 | 15 | **0** | 25–30 | 25–35 |
| Everything clean after [D] | 3 h | 55 min | 55–75 | 55–75 | 55–75 | **15–20** | 55–75 | 35 |
| Washers in the machine | chamber + dish | lathe + dish | chamber + dish | chamber + dish | chamber + dish | wells + dish | slot + chamber + dish | **tub + dish** |
| Can plate in the cell | yes | no | partly | partly | no | yes (serial) | partly | in principle |
| Loose ware items [D] | ≈ 110 | 76 | 46 | 36 | 96 | 93 | 132 | ≈ 70 |
| Motion actuators [D] | 17–20 | 21 | 35 | 26 | 25 | 16 | 24 | 16 |
| Dynamic seals and slots at the cell [D] | 7 + 6 V-rings | 8 | 19 | 17 + 5 | ≈ 11 (one band slot) | ≈ 9 (three band slots) | ≈ 8 + 4 contact-free rings | **0** |
| Washing noise [D] | not given, likely > 48 | needs insulation | — | — | — | 52–56 | — | drumming risk |
| Build path | poor | fair | fair | fair | **good** | **good** | fair | poor |

---

## 7. Scores and justification

The score is for system fit and operations only: 10 = fits the width, power, water, cost and transport
budgets and runs a household's day without help; 1 = cannot be made to fit without abandoning the concept.

| | Score | Justification |
|---|---|---|
| K1 | **2** | Two fatal findings (width inherent to the turret reach; resource budgets at 2 × inherent to all-ware in a wash-down cell), the highest cost, the highest transport load, the slowest turnaround and a clean-up that runs into the night. Its only system strengths — three hands that could plate, partial limp-home — do not offset any of that |
| K2 | **5** | The most self-contained cell: rack, washer and oven inside, transport only at one port, 48 moves, energy near the limit. Against it: the oven does not fit the stack, the true width is ≈ 1900, hobs are stacked to 2 m, a second washer in the machine, and it cannot plate, so serving needs a second manipulator |
| K3 | **4.5** | Narrowest all-inclusive cell (the only machine within 100 mm of 3.6 m at the storage floor), few moves, the only defined heated hand-over. Against it: the oven does not fit, a floor-level port, 35 actuators and 19 dynamic seals, water 1.4–1.7 × over, a single drum and a single shuttle in series |
| K4 | **4.5** | Cheap and compact, few moves, water near the limit. Against it: consumables above the whole yearly wear budget, an inaccessible oven over the hob that does not fit, uncounted mat strokes that make reliability unknowable, and B2/B3 without margin |
| K5 | **5** | The best build path and a clean split into column and cooking module, few moves, double ware set for turnaround. Against it: the highest in-place water on top of the ware wash, a 6 kW boiler, 17 costly dies, no plating, and an oven bay that also holds the ware store |
| K6 | **3.5** | Operationally the best (turnaround 15–20 min, proven parts, fine build path), but 2.6 m makes the machine 4.8 m at best — fatal against PHY-004 — and its signature, wash as you go, cannot get power during oven meals and is too loud. It also needs a second washer for the dishes |
| K7 | **2.5** | A booster that adds a refrigeration circuit, a slot washer and ≈ €10 k to a full conventional cell: fatal on cost, 1.9 × on width, 120 moves per meal. Keep the cold cabinet as an optional module idea, not as a system |
| K8 | **6** | Best system fit: 1150 mm without the oven, cheapest, zero dynamic seals, washes its own ware so the machine needs only a dish washer, lowest water and energy (still over RES-005/-001 by 10–20 %), light transport. Against it: the cell is blocked 25–35 min after meals, its power claim is inconsistent, jets on a door facing the room, 105 moves per meal, and the whole concept rests on untested magnetic figures |

---

## 8. Interface requests to the architect: conflicts and the common denominator

| # | Topic | What the concepts ask [D] | Conflict | Common denominator (proposed) |
|---|---|---|---|---|
| R-1 | **Module boundary** | all: an internal handler moving vessels between preparation, hob, oven and (K2, K6, K7, K8) washing (X8) | TRN-002, MOD-001 | The **process cell is one module** (preparation, cooking, portioning **and plating**) with its own internal handler; TRN-002 applies at its boundary. Washing inside the cell only if the cell's washer also replaces the ware washer of the washing module (K8, K2), never as a third wash system |
| R-2 | **Grip feature on ware** | K1 lift stub Ø 22 × 40 + rim ears; K2 R260 spool with neck + notched skirt; K3 tang 40 × 10 × 70; K4 ferritic dovetail tab; K5 two rim lugs + notched skirt; K6 tang 6 × 32 × 60 with two Ø 8 holes; K7 "K7 tab"; K8 bayonet/pucks on GN | seven incompatible features; the transport, washer racks, hob and oven must all clear them | **One flat tang at rim height on one side** (K6 geometry, which K3, K4, K7 approximate; a ferritic insert allowed), plus equal rims for pair inversion (catalogue R1). Transport grips the same tang |
| R-3 | **Vessel families** | GN 2/3 (K1, K3, K6, K7, K2 flat); GN 1/2 and 1/4 (K5, K8); round Ø 220–300 (K1, K2 R260, K4, K5, K6 Ø 240) | the oven rails, hob bridge mode, washer and serving must take all | **GN 2/3 as the flat, oven and braising family** (fits compact ovens, 8 Rouladen, matches the 176 mm box family) and **one round pot family Ø 240** sized for **4 persons** (DEC-19: 6 L maximum, 28 cm pan) |
| R-4 | **Box** | plain GN 176 family accepted by all; wishes: pour edge (K3, K5, K8), sifter/mesh lids (K2, K3, K4, K5, K6, K8), egg insert (K1, K2, K3, K6), plane top rim sealing under 60 N (K2), lid removed before the dock (K2) or knob for a stub (K1), lengthwise storage (K4) | X1, X4, X5; BOX-005/-007 | **Plain GN 1/9, 1/6, 1/3 with a flat lid; the lid is removed and replaced by a lid station outside the cell; the box tolerates a 135–180° tilt; inner radius ≥ 10 mm; egg insert.** Mesh lids only for flour and starch, as an option |
| R-5 | **Stowed packs and conversions** | "arrive opened, upright, in a carrier" (K1, K2, K4, K6, K8); paste cartridges (K3), small tubes (K5), frozen pucks (K4, K7), piston cartridges (K2), dicing butter and bacon at first opening (K2) | four formats; DEC-3 (open just in time); ingestion scope | **One JIT opening cell served by the transport**, delivering opened packs upright in a GN 1/3 carrier; pastes spooned or squeezed from the opened pack. No ingestion-time conversion in the MVC |
| R-6 | **Cold store** | freezer-airlock tempering 20–40 min (K3, K4, K5); 12–15 extra freezer positions for pucks (K7); cold sheet position (K2); chilled boxes up to 3 min at the dock (K2, K6) | CLD-004, FSF-013, CAP-022 | Not in the MVC; dock dwell ≤ 3 min accepted |
| R-7 | **Oven** | all: a bought oven turned 90° with its mouth into the cell, machine-driven door, start without a button | does not fit the depth; MNT-001, BLD-008, COK-023 | **Front-facing oven in a transport-served column, or stacked in a 1200 mm cell and loaded by its handler — decided on a CAD model of a real appliance** before round 2 draws any cell |
| R-8 | **Hob** | four OEM induction positions, two or four with turntables or ring drives (K4, K5, K6, K7), load cells, bridge mode for GN 2/3, 3.5 kW front zones | UTL-010/-011 | **Four 3.0 kW coils as two pairs of ≈ 2.8 kW each, on L1 and L2**; two positions with a slow turntable; bridge mode for GN 2/3 |
| R-9 | **Ports** | side-wall and ceiling ports at z 120–1980 (finding m) | TRN-003, MOD-011 | **One box port in the cell ceiling or upper wall reached from an overhead transport gallery (z 2000–2200), and one ware/vessel port at deck height at the module joint**, both to the MOD-011 standard; a buffer position at the dock |
| R-10 | **Washing** | K1: 3 loads per meal in 90 min; K3: 12–16 items per meal; K4: 36 tabbed items; K5: class R load back in 30 min; K7: 12–15 bulky items in 60 min; K2, K6, K8: own washers | D7 scope, RES-005, WSH-002 | **One commercial under-counter washer (500 × 500 rack, 2–4 min cycles, 85 °C rinse, robot-loaded) for dishes, glasses, cutlery, boxes and whatever ware the cell does not wash itself**; a ware set that needs at most one load per meal |
| R-11 | **Serving, plating, hot-holding, drinks** | all hand over cooking vessels; K3 defines a heated hand-over shelf | SRV-005/-009, COK-017, SRV-022/-024 | **Plating in the process cell** with warmed plates brought in; **a heated hand-over shelf** at the cell's port; the serving module is dish store, dish washer, hatch and a **drink pour station** that never uses the cell |
| R-12 | **Utilities** | 6–8 L boilers at the cell (K1, K5, K6, K8), 95 °C drain (K2), 100–150 m³/h extraction with "a condenser" (all), EN 1717 (K1) | UTL-011, ENV-010 | **A machine-wide phase plan (3.2); one shared dehumidifier-condenser sized for ENV-010**; water heating only on L3 when the oven is off; one softened-water and detergent supply (WSH-009) |
| R-13 | **Waste** | chip boxes, strainer drawers, fat cups collected by transport (K1, K2, K4, K5) or through hatches | CAP-041, PRP-033 | One GN 1/3 chip-box format exchanged by the transport |
| R-14 | **Rulings** | adapted methods (all), glass-ceramic in Zone F/S (K1, K8), fixed belts and drums (K3), temporal red/green separation in one chamber (K8), module-internal handler (K5) | MEAL-013/-019, HYG-018, HYG-005, TRN-002 | To the requirements owner before round 2 |

---

## 9. Recommendations for round 2

1. **Fix the budgets before anyone draws.** Every round-2 cell receives the same sheet: wall width **≤ 1200 mm
   including the oven** (or ≤ 600 mm plus a shared oven column), height ≤ 2200 mm with the top 200 mm left to
   the transport; hob **two channels of ≤ 2.8 kW**, oven alone on the third phase, no water heating while it
   heats; in-cell water **≤ 15 L per 2-person meal** and ≤ 1.0 kWh of cleaning; **≤ €9 k of parts** without
   the oven; **≤ 50 handling moves per full meal**; washing noise ≤ 48 dB(A); vessels for **1–4 persons**.
   A concept that cannot meet a line says by how much, with the arithmetic.
2. **Ask the customer three questions now** (through the orchestrator): (a) BLD-004 — with storage, dish
   washing and transport at €17–23 k, is €25 k still the target, or is €35–40 k acceptable? The S target of
   €15 k is unreachable; (b) is the MVC allowed to exceed 3.6 m if the cell cannot reach 1.2 m, or does storage
   give way (ambient 450, one fridge shell)? (c) may the machine's own washer take the household's dishes if
   the cell is a K8-type tub, i.e. is a plate that was in a chamber where raw meat was open acceptable after a
   disinfecting wash (the answer decides whether K8 can also be the dish washer)?
3. **Settle the oven on a real appliance first.** One day of CAD with the dimensions and service clearances of
   two candidate combi-steam ovens (a 45 cm compact built-in and a countertop unit) against the 600 mm depth,
   door, cooling air, COK-023 start and front exchange (MNT-001). All eight layouts depend on it.
4. **Carry forward as system bases**: **K8** (smallest, cheapest, washes its own ware) and **K5** (separable
   column; cooking module and column can be built and tested apart). Explore two hybrids against the budget
   sheet: **H-A "K8 + K5"** — the tub with four GN hob positions, and the force operations (dice, rice,
   press, knead) done by a K5-type tube cassette driven from above through the tub's ceiling port, keeping the
   tub free of dynamic seals; **H-B "K5 + K2"** — the press column and a K2 inverter-on-a-lift serving a
   two-by-two hob and a stacked oven in 1200 mm, washing in the shared commercial washer. K3 continues only if
   the hygiene critique clears its belt and drum; K6 continues as the reference for ware, wells and
   verification, at ≤ 1.7 m and without wash-as-you-go during oven meals; **K1 and K7 stop as systems** (keep
   K1's passive-tool interface and K7's cold cabinet as optional module ideas).
5. **Put plating into the cell** and give it a number: a course for 4 at the hatch within 4 min, i.e. one
   placement every 10 s, or plates moving under fixed dispensers. Define the heated hand-over shelf and where
   finished components are held without blocking the hob.
6. **Make each round-2 document carry a whole-day ledger** for the 2-person household and for a 4-person
   guest meal: water, energy, peak power per phase on a timeline for reference menus 2, 8, 9 and 15, noise by
   hour including quiet mode, transport moves and port positions, dock occupancy, ware parking volume, human
   minutes per week, and a drink requested in the middle of a meal.
7. **Walk the benchmarks again under the current purchase list** (5.6: beans trimmed, herbs fresh, stock made
   ahead by UO-96) and at 1, 2 and 4 persons, with one retry inserted in the tightest step.
8. **Test before choosing**, in this order: the oven CAD (one day); a phase-level power simulation of menus 2,
   8, 9, 15 (one day); K8's magnet and friction rig (one week, < €1000); a handling-reliability rig that
   counts unrecovered failures per move for the chosen grip and tang (two weeks).
9. **Rule on the requirements that fight the concepts** (R-1, R-14): a process cell with an internal handler
   as one module; washing inside it only as a replacement of, never an addition to, the ware washer; and align
   CAP-001/-004/-006/-030/-031, COK-016 and SRV-009 with DEC-19.

---

## 10. Open issues and risks of this critique

**Open issues.**

1. The non-cell budgets (3.1, 3.5) are my estimates from R3, R5 and R7; the architect's module allocation
   (BLD-004 asks for it) will replace them. The verdict "no concept fits" survives any plausible correction:
   the smallest cell is 1450 mm against an allocation of 1200 mm.
2. Light-meal water and energy (3.3, 3.4) are scaled by me; the concepts only give full meals and B12.
3. The phase plan (3.2) assumes a household oven that cannot be throttled and two compressors; a three-phase
   commercial oven or a custom cavity would change it.
4. Stoppage arithmetic (4.6) assumes 10⁻³ unrecovered failures per move as a reference, not as a prediction.
5. The requirements are being aligned to DEC-19 while this is written; limits quoted for 6 persons (CAP-006,
   SRV-009 etc.) were read as 4.
6. I read benchmark walk-throughs step by step only for B1–B3 of K1, K3, K5 and K8; other time claims were
   checked for margin and consistency, not recomputed.

**Risks.**

| # | Risk | Consequence | Mitigation |
|---|---|---|---|
| 1 | The width and cost verdicts are read as "the project cannot work" | Discouragement, or silently raised limits | State them as budgets for round 2 and as questions to the customer (recommendation 2) |
| 2 | Round 2 optimises the cell and leaves plating, drinks and dish washing to modules nobody designs | The same system gaps reappear at integration (V1) | R-11 and recommendation 5 put plating into the cell; serving gets a defined, smaller scope |
| 3 | The oven question is answered late | Every cell layout is redrawn after selection | Recommendation 3 first |
| 4 | Scores are compared with other critics' scores as if they measured the same thing | A concept that is clean but does not fit (K6) or fits but is untested (K8) is chosen for the wrong reason | Selection (P6) weighs the critiques explicitly; this one is about fit and operations only |
