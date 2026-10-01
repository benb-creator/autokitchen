# Critique C6 — adversarial review of K10 "KÜCHENGERÄT" (the €2 k machine)

Reviewed: `design/prep/concepts/K10-two-thousand.md` (all), against DECISIONS #1–28, the summary parts of
`K9b-combined-simplest.md`, `K9c-design-to-cost.md` and `design/storage/10-storage-comparison.md`, the benchmark list
in `design/prep/03-exploration-brief.md` and the requirements MEAL, HYG, PERF-005, CAP, STO, CLD, REL, COK-002/-004.
Reviewer did not write K10. Markers: **[W]** web-checked 2026-10-01 (source given); **[C]** calculated here;
**[E]** reviewer's engineering estimate; **[K10 §n]** claim as stated in K10. Severity: **fatal** (kills the
concept or the claim it rests on, no fallback inside the concept), **major** (a claim does not hold as written;
fixable at a real cost), **minor**.

**Summary.** K10's cost direction is real: a bought thermo-cooker, appliances used as bought and cost discipline cut
the cell by ≈ 25–32 % against K9c (corrected cell ≈ €2.75–3.0 k, not €2.52 k). Its headline "whole machine ≈ €3.0–3.3 k"
does not hold: W1 fails CAP-021 (fridge ≈ 28–30 of 45) and CLD-004, and the compliant W2 with the missing items is
≈ €4.3–5.0 k. The named cooker (Mambo 11090) has a touchscreen and a hinged lid, no thermo-cooker has a published
control protocol, and IEC 60335-2-14 Ed. 7 restricts remote start — R1 can wipe out the cooker saving. The raised
front-door dishwasher as the only washer and clean store causes most Must failures: PERF-005, HYG-021 margin, no
bench, impossible P0 staging, PERF-002 (b) and (d). **K10 is the better source of principles, not the better base**;
round 2 should combine K9c's layout and washer with K10's cooker, cost discipline and shared rail (§7.3).

---

## 0. Claims to be checked

| # | K10 claim | Where | Check |
|---|---|---|---|
| A1 | A Cecotec Mambo-class thermo-cooker (2.3 L usable, ≤ 120 °C) replaces K9b's heated hub, S, press cup and kneading roller with **0 meals lost** | §1.1 I2, §5 | capacity per batch for 4 persons; temperature; 12 benchmarks |
| A2 | Searing/browning (Rouladen, Schnitzel, steak, Frikadellen, Bratkartoffeln) all happen on the **2-zone domino**, under splatter lids | §3.5, §6 | positions, batches, timing; splatter lid vs browning |
| A3 | Coverage **232 = 93.5 %**, reserve 1; only MX06 lost | §5 | at-risk list, capacity-limited meals, B1–B12 walk-through missing |
| A4 | Spaghetti Bolognese for 4 in ≈ 80 min; meals only +10–20 min longer than K9b | §3.6, §5 | PERF-002 limits; simultaneous components |
| A5 | COK-002 met: domino 2 zones + cooker + oven + warm-hold | §1.1 I2 | ≥ 2 positions ≥ 3 kW; 4 simultaneous positions |
| B1 | The cooker can be **driven by K10's controller through its own power board** (€40, R1) | §4.1 C6, §10 R1 | web: Mambo app/API, firmware, board; what if not |
| B2 | The hand can twist the cooker lid by an XY arc, lift the 3.5 kg jug, feed through a funnel | §3.4, R2 | lid lock, safety interlock, mass |
| C1 | Household dishwasher hygiene/intensive programme, **A0 ≥ 60 at 65–70 °C** is enough; fallback a longer-rinse model | §6 | HYG-021, C2 R-3, cheap €255–350 models |
| C2 | Raw/RTE separation by **duplicate items**, no in-meal wash | §1.1 I4, §6 | count of duplicates, cooker jug reuse |
| C3 | Cooker jug, blade and lid **boil-clean in place** (A0 ≫ 600) between raw and RTE | §6 | blade underside, seal, lid gasket, steamer |
| C4 | Gadgets (garlic press, ricer, dicer, mandoline) are **dishwasher-safe** and get clean | §4.2, §6 | crevices, mandoline [U], garlic skins |
| C5 | Clean store = the closed dishwasher; dishes clean **3–5 h** after the meal; PERF-005 dropped | §9 W1, Q2 | PERF-005 M, next-meal readiness, REL life |
| C6 | Kitchen furniture as enclosure; splash at the source; nozzle rail cleans | §1.1 I1/I11, §6 | HYG-006/-013/-019; fat in carcasses, lazy susan, lever seat |
| C7 | Open storage tops and shelves under a shared rail are hygienic | §7 | HYG-004, STO-008 |
| D1 | K9c's printer-class gantry carries the duty: lift ≤ 4 kg at ≤ 150 mm, push 300/150 N, 0.8 m/s | §3.4 | jug 3.5 kg off-axis; garlic press forces; dicer forces |
| D2 | Gadgets worked by the gantry with ≤ 150 N at 4 : 1 | §3.5 | real press forces; mandoline safety and jamming |
| D3 | Dishwasher turned 90°, raised to z 1000, door and racks by a hook rod; 3,000-cycle runners | §3.3, R3 | door spring, ergonomics, rack loads, cycle count vs REL-003 |
| D4 | One X rail over 3.6 m serves storage and cell (W1) or two carriages (W2) | §7 | belt length, deflection, timing, single point of failure |
| E1 | Dig-from-top retrieval ≈ 15–20 s for a top box | §7.4 | STO-003, CLD-006 with digging |
| E2 | 122–140 cm cold shells give fridge ≈ 30–32, freezer ≈ 24, ambient 80–90 | §7.2 | CAP-020/-021/-022/-023 |
| E3 | Cold hatches: whole top wall as a lid, €10 solenoid, 15–20 s open per move | §7.2, §7.3 | CLD-004, CLD-005, CLD-007, CLD-008 |
| E4 | Storage moves cost **+≈ 8 min** hand time per 4-person meal (W1) | §7.4 | 20–25 boxes × 20 s, lids, returns |
| F1 | Cell machine part **€2,520**; like-for-like **€2,739 (−37 %)** | §4 | line-by-line plausibility |
| F2 | Whole machine **≈ €3.0–3.3 k** (W1/W2); storage add-on €820/€1,100 | §7.3, §7.4 | missing items, box count, appliances |
| F3 | Appliances total inside Ben's €3,000–3,500 | §4.3 | 122–140 cm fridge + freezer price, built-in vs freestanding |
| G1 | K10 is the better base than K9b/K9c | — | verdict |

---

## 1. Coverage and food result

### 1.1 Hot positions and browning (A2, A5) — **major**

| | K9b / K9c | K10 |
|---|---|---|
| Pan-capable positions (can brown) | 3: domino front, domino rear, heated hub (own 2.0 kW generator, pan on the dog ring) | **2**: domino front and rear |
| Stirred position | hub with hung scraper, induction-heated pot or pan: can brown while stirring | jug, **37–120 °C** [W: pccomponentes.de / testsieger.de spec sheets, 1600 W] — no Maillard, no pan |
| Power for all pans | domino 3.7 kW + hub 2.0 kW = 5.7 kW | **3.7 kW** for both pans together |

K10 (as K9b) writes "front Ø 210 3.4 kW boost, rear Ø 180 2.0 kW". A real 30 cm household domino has **one 3.7 kW
connection for both zones**: e.g. Bosch PIB375FB1E front Ø 210 2.2 kW (boost 3.7), rear **Ø 145** 1.4 kW (boost
2.2), total 3.7 kW with power management [W: Bosch spec sheet PIB375FB1E]. When the front boosts to sear, the
rear gets ≈ 0–0.3 kW. K9b got away with this because the hub had its own generator; K10 put every browning and
every pan job on these 3.7 kW.

Where browning happens in K10: Rouladen sear, Schnitzel (2 batches), steak, Frikadellen, Bratkartoffeln, mince
for Bolognese, chicken for curry — all on the two domino zones. **Stirred browning** (Gulasch onions 20–30 min,
curry paste, roux, the onion and tomato paste "roasted in the fond" for Rouladen) was done on K9b's hub with the
hung scraper while the hand did other work; K10 must either stir it on the domino in intervals with the hand
(hand time) or move it into the jug at ≤ 120 °C, where onions sweat but do not brown — a result change under #27
for curries and Gulasch. K10's coverage table does not mention this. "Pans with splatter lids" (§3.5, §6) must
be **mesh screens**: a closed lid steams the crust off a Schnitzel (#27); a mesh screen is itself a fat trap (§3).

**COK-002 (M)**: ≥ 3 simultaneous positions ✓ (2 domino zones + jug), but "≥ 2 with ≥ 3 kW" ✗ — one zone reaches
3.7 kW only while the other is nearly off (inherited from K9b, K9c Q7; worse in K10 because the third position is a
1600 W jug, not a pan). "Warm-holding usable at the same time as the baking cavity" ✗ — the 25 L oven is cavity,
warm-hold, plate warmer and clean GN/plate store at once: during oven fries at 220 °C (B7) or a roast, neither
Schnitzel batch 1 nor plates can be held in it.

### 1.2 Capacity of a 2.3 L jug for 4 persons (A1)

| Component for 4 | Volume [E] | In the jug? |
|---|---|---|
| Bolognese sauce (500 g mince, soffritto, 800 g tomatoes, wine) | 1.8–2.0 L | yes, tight; little reduction under the lid |
| Risotto (320 g rice, 1 L stock) | ≈ 1.5 L | yes (better than K9b) |
| Béchamel for lasagne (1 L milk) | ≈ 1.1 L | yes |
| Curry with 600 g chicken / Gulasch with 800 g beef and 600 g onion | 1.8–2.3 L | at the limit |
| Rotkohl, 1 kg **shredded** (mandoline) | 2.5–3 L loose at the start | **no** — only chopped by the blade (#27: shreds vs crumbs) or in a pot on the domino |
| Puréed soup as a main, 4 × 0.5 L | 2.0 L + blending head-space | marginal; Eintopf (2.5–3 L) goes to the 5 L pot, as K10 says |
| Yeast dough | 500 g flour | yes [U]; bread with 1 kg flour in 2 batches |

The jug is big enough for most **single** components, but it is **one** vessel: every raw → ready-to-eat change
costs a boil-clean (fill with 85 °C water, 3 min at ≈ 100 °C, drain: ≈ 4–6 min [C]), and only one jug dish per
menu can run at a time. A spare jug (€60, W3) does not help without a second base.

### 1.3 Getting food **out** of the jug — **major, not in K10's risk list**

K10's R2 tests the lid, the funnel, lifting the 3.5 kg jug and ladling. It does not test **emptying**. In a
Thermomix-class jug the blade sits fixed at the bottom; in household use sticky contents are scraped out with a
spatula, and dough is released by unlocking the blade from below. The K10 hand has no yaw, cannot unlock the
blade, and can only invert the jug (≤ 4 kg at ≤ 150 mm: the full jug with its CoM ≈ 100–130 mm from the handle is
**at the limit** [C]). Chopped onion and soffritto cling to the walls, Frikadellen mince mass and dough wrap round
the blade, risotto and mash pour badly. Every cooker route that replaced K9b's press cup and hub (onion chop,
soffritto, garlic paste, crumbs, nuts, cheese, kneading, mince mixing) depends on emptying. Expected residue
5–15 % of the batch and +1–2 min per emptying [E]; dough [U]. Needed test (add to R2): 20 emptyings each of
chopped onion, Frikadellen mass, 500 g pizza dough and risotto by inversion plus a stem spatula, weighing the
residue.

### 1.4 Work surface — **major, not in K10**

The only free deck in the K10 cell is the bay: 520 × 450 mm = 0.234 m² minus the sink Ø 260 (0.053 m²), the chute
120 × 200 (0.024 m²) and the peeler post, i.e. **≈ 0.15 m²** [C], about one Ø 320 board (0.080 m²) plus a margin.
The domino is a hot zone, the cooker sits in a pocket behind the lever seat, and under the raised dishwasher
(X 1225–1795) the deck has only 130 mm clearance. K9b had the well lid as a bench and the hub top. Consequences
[C]:

* **Breading line** (3 × GN 1/3 = 0.17 m²) does not fit beside anything; three GN 1/6 in a row need 486 mm.
* **Plating**: two Ø 270 plates need 540 × 270 mm; the serve zone is ≈ 480 × 250 mm. K10's "2 plates or 2 GN 1/3"
  does not fit (§3.3's own y 330 line is "schematic"; the Ø 320 board already overhangs it by 70 mm). 4 persons =
  3–4 serving cycles through the panel instead of 2 drawer cycles.
* **Dish return** of 4 settings (plates, glasses, cutlery) onto ≈ 0.15 m², then each plate carried singly.
* Rouladen lay-out (6 slices), pizza rolling on a tray, lasagne layering in a GN 1/2 (0.086 m²): only with the
  board removed, one at a time.

### 1.5 The twelve benchmarks (A4) — K10 has no walk-through; reviewer's estimate

K10 states "+10–20 min per 4-person meal against K9b" (§5) but never compares that with PERF-002. Applied to
K9b's B1–B12 times [K9b §6] with the K10-specific effects above [E]:

| B | Dish (4 p unless noted) | Limit (PERF-002 / K9b) | K9b | **K10 [E]** | Verdict | Where it browns / note |
|---|---|---|---|---|---|---|
| B1 | Rouladen, Rotkohl, Salzkartoffeln | 183 | 130 | 140–150 | ✓ | sear front; front blocked 90 min by the braise; Rotkohl in the jug (chopped, #27) or pot rear + potatoes in the steamer |
| B2 | Schnitzel, Bratkartoffeln, Gurkensalat | 68 | 50 | 60–70 | marginal | Schnitzel front + Bratkartoffeln rear share 3.7 kW; breading line has no room (1.4) |
| B3 | Frikadellen, Püree, Erbsen-Möhren | **50** | 45 | **55–62** | **✗ PERF-002(b)** | mince mass mixed in the jug, emptied (1.3), boil-clean before the vegetables; 1 kg riced in a household ricer: ≈ 200 g per fill → 5–6 fills × ≈ 60 s incl. removing the skins |
| B4 | Spaghetti Bolognese | 96 | 88 | 85–100 | marginal | K10 §3.6 says ≈ 80 min "≈ 15 min longer than K9b" — but K9b is 88 min; one of the two figures is wrong |
| B5 | Pizza, 2 trays | ≈ 150 | 120 | 135–150 | marginal | 25 L tray ≈ 0.07–0.08 m² vs GN 2/3 0.115 m²: 3 bakes, not 2 |
| B6 | Gemüseeintopf | **50** | 46 | **55–60** | **✗ PERF-002(d)** | no hub; all cutting by knife, dicer, mandoline; 5 L pot on the domino |
| B7 | Steak, oven fries, salad (2 p) | ≈ 54 | 40 | ≈ 45 | ✓ | at 4 p the fries need 2 tray loads (1 kg single layer ≈ 0.12 m²); PERF-002(c) 79 min probably ✓ |
| B8 | Pfannkuchen, 8 | 50 | 36 | **[U]** | **route missing** | K9b spread the batter by spinning the pan on the heated hub; K10 deleted the hub and states no spreading route; one roll axis tilts about one axis only, so no swirl |
| B9 | Chicken curry, rice | ≈ 62 | 48 | 55–60 | ✓ tight | chicken seared front; onion/spice paste in the jug at 120 °C is paler (#27) or stirred on the domino by hand |
| B10 | Lasagne | 148 | 125 | ≈ 130 | ✓ | béchamel in the jug is a gain |
| B11 | Rührkuchen | ≈ 102 | 95 | ≈ 95 | ✓ | creaming in the jug with the stirring tool [U] |
| B12 | Scrambled eggs, 1 p | ≈ 21 | 9 | 10–12 | ✓ | but the next meal needs a dishwasher cycle of 1.5–2.5 h (§3) |

**Result:** two PERF-002 Must benchmarks fail on K10's own time penalty (B3, B6), three are marginal (B2, B4,
B5), one has no route (B8). K10's mitigation, "produce prep can move hours ahead", does not apply to PERF-001
(order-to-ready from stock), and the prepped items have nowhere hygienic to wait: GN 1/3 does not fit the chosen
storage box standard (storage 10 §7 Q3: "no design stores GN 1/3"), and the "cold oven" is at room temperature
(cut produce and filled Rouladen > 2 h unchilled: FSF practice).

### 1.6 Coverage (A3) — **major: the claim is not robust**

K10 claims 232 (93.5 %), range 229–235, reserve 1 — so its own range straddles the 231 target. Not counted:
B8's spreading route (Pfannkuchen family, −0…−2 at risk), stirred browning moved to a 120 °C jug or to hand
interval stirring (Gulasch, curries: result or time), jug emptying [U] (if it fails, chop and knead routes fall
back to knife and dicer: no meals lost, but more time on B3/B6), grated cheese for pizza and gratin made in the
blade jug (crumbs, #27) unless the mandoline gets a grater insert. Reviewer's central estimate **229–232**, i.e.
**at or just below 231 about as often as above** [E]. K10-L with L8 (231, reserve 0) is not a valid design point.
The desk walk R8 must come before any further cost work, and it must include the B1–B12 table that the
exploration brief (§"Required content" #5) asks for.

## 2. Controllability of the thermo-cooker (B1, B2)

### 2.1 What the named model is — **major: K10 describes a different machine**

Web check of the Mambo 11090 [W: storececotec.de product page; codigodeerror.com review; pccomponentes.de]:
1600 W, 37–120 °C, 3.3 L jug / 2.3 L usable, scale, **touchscreen**, Wi-Fi app, and a **hinged lid attached to
the base** that locks automatically during cooking. K10 assumes a removable twist-lock lid turned "by an XY-arc
push on a pin of a clamped lever" (§3.4), "jug and lid to the rack" (§3.6 P5), and a fallback of
"opto-couplers on its keys" (R1). With the 11090:

* the lid cannot go into the dishwasher; its underside, gasket and hinge are cleaned only by the boil-clean
  (§3.3 below);
* opening is a lift on the hinge arc (Y–Z), not an XY arc — and the open lid stands ≈ 250–300 mm high over the
  lever seat behind it [E; R10 must check];
* **capacitive touch keys cannot be bridged by opto-couplers**; the only non-invasive fallback is the gantry
  pressing the screen with a conductive stylus and the camera reading the display — slow, but cheap and it keeps
  the appliance as bought.

### 2.2 The three ways to drive it

| Route | What is known [W] | Assessment |
|---|---|---|
| **Vendor app / cloud** | The Mambo app offers guided recipes and "in some cases" remote control with alerts; pairing problems reported in reviews. Cecotec's other connected products (Conga vacuums, heaters) run on Tuya and can be driven locally with tuya-local / tinytuya; **no evidence found that the Mambo is Tuya-based or that anyone has mapped its data points**. | Unproven. **IEC 60335-2-14 Ed. 7 (2025)** makes kitchen machines with accessible moving parts or that need further user interaction ineligible for remote control or delayed start; where remote control is allowed, the run time is set before the start and remote mode must be entered on the product [W: zrlklab.com summary of IEC 60335-2-14:2025]. A guided-cooking app that adds ingredients step by step is exactly the case the standard excludes, so a vendor API that starts the motor and heater on command is unlikely to exist and may be removed by a firmware update. Cloud dependence also breaks REL-006. |
| **Tap the internal bus** | Comparable machines are a UI SoC talking over a serial line to a power board: Monsieur Cuisine Connect (MT6580, Android 6) has a serial device `/dev/ttyMT0` "controlled with some commands"; firmware dumpable by SP-Flash, ADB can be enabled [W: github.com/EliasKotlyar/Monsieur-Cuisine-Connect-Hack]. Monsieur Cuisine Smart (MT8167, Android 8.1) has a DS28C36 security chip signing cloud calls; TWRP port only partly working; **no published protocol**, no working Home Assistant integration since 2022 [W: 1101011.xyz; community.home-assistant.io thread 418522]. | The **best** route, and better than K10's plan: sniff and replay the UI → power-board messages, so the power board's own lid interlock, over-temperature and motor protection stay in place. Weeks of reverse engineering per model; any model change or silent board revision restarts it. |
| **Bypass the UI board** (K10's C6, €40) | Drive the motor (1600 W class, speed loop with tacho), heater, NTC, scale load cells and lid lock from K10's own controller | **Worst** route: K10 rebuilds the appliance's control and safety loop for a mains-powered blender with a heater, the appliance loses its EN 60335 basis (CE then rests on K10), and it is no longer "used largely as bought" (#28). €40 of parts is plausible; the work and the safety case are not costed. |

### 2.3 What if it cannot be driven

K10's R1 fallbacks: (a) opto-couplers — fail on a touchscreen; (b) Monsieur Cuisine Smart (€399) — same closed
architecture, signed cloud, no protocol; (c) "a clone with knob controls" — knob-controlled thermo-cookers (e.g.
cheap soup makers) mostly lack scale and controllable speed. The honest fallback is **K9b/K9c's own hub** (hub
€435 + coil/press cup in K9c's blocks), i.e. K10's single biggest saving (≈ €0.5–0.7 k, §0 I2) disappears and
the concept becomes "K9c with a dishwasher as bought". A cheaper honest fallback exists: **the gantry presses the
touchscreen** (stylus stem tool, €10) and the camera reads speed/temperature/time — slow (≈ 5–10 s per setting),
but keeps the appliance unmodified; it should be R1's first fallback.

**Severity:** R1 is rightly first in K10's test order, but it is **fatal to the cost claim** if it fails and
there is no cheap fallback in K10 as written. The test should be: (1) check whether the 11090 app is Tuya
(network capture, €0, 1 day); (2) open the unit and log the UI ↔ power-board line while running each function;
(3) replay. Budget 2–4 weeks, not 1.

## 3. Hygiene

### 3.1 Household dishwasher as the only disinfection (C1) — **major**

HYG-021 asks ≥ 5 log on class-R ware by A0 ≥ 60 **at the surface** (moist heat; C2 R-3: show it with a logger on
the coldest item). A0 = Σ 10^((T − 80)/10) · Δt [C]:

| Final rinse at the ware surface | A0 |
|---|---|
| 65 °C for 10 min | **19** |
| 68 °C for 10 min | **38** |
| 70 °C for 5 min | **30** |
| 70 °C for 10 min | **60** (exactly the requirement, no margin) |
| C2 R-3 default, 82 °C for 60 s | 95 |

K10's own range "65–70 °C, A0 ≈ 60" therefore contains mostly **failing** values. A branded hygiene option is
specified as "up to 70 °C for ≈ 10 min" in the **water** [W: Bosch HygienePlus description, kliq.de; Bosch Serie 4
45 cm spec sheets list "Intensiv 70 °C"]; the surface of a PE-HD board, a heavy pan or a GN in a slim, full load
lags by several K, so expect A0 ≈ 35–50 [E]. The €255–303 slim models K10 prices (Midea, Bomann, Amica) state an
"intensive 65–70 °C" programme with no hold time: expect A0 ≈ 15–40 [E]. K10's fallback, "a longer 70 °C hygiene
rinse", needs control of the dishwasher's programme, but K10 only presses its keys through opto-couplers. Framing
it as "A0 ≥ 60 instead of K9b's 90 — a C2 decision" (§6, W2) understates it: **60 is the Must**, and a cheap
household dishwasher does not demonstrably reach it on class-R ware. Fix: a model with a validated hygiene
programme (+€150–250, Bosch/Siemens/Miele slim with hygiene option) **and** R3's loggers as a gate; if A0 < 60,
raw-meat ware needs a second pass or a different washer.

### 3.2 Bought gadgets are crevices (C4) — **major**

HYG-013 (Zone F: no crevices, gaps, blind holes, hinges, overlapping joints) is violated by construction by every
gadget K10 adds:

| Gadget | Crevices [E] | Typical household cleaning |
|---|---|---|
| Unpeeled-garlic press | 2 mm holes packed with skin and fibre, hinge pin, scraper pivot | brush / cleaning comb |
| Ricer / Spätzle press | perforated basket (skins pressed into the holes when press-peeling), hinge, plunger | rinse immediately, brush |
| Push dicer 6/10 mm | blade grid riveted into a plastic frame, matching pusher prongs; onion fibre wedges | brush; many makers say top-rack only |
| V-mandoline + julienne | riveted V-blade, comb of julienne blades, fruit-holder spikes; maker's dishwasher statement inconsistent [K10 Q8] | hand wash recommended for blade life [U] |
| Pump salad spinner | pump mechanism with spring inside the lid | lid often "hand wash" [U] |
| Mesh splatter screens | fine mesh with fat | soak |

K9b's ware was designed to HYG-013 (welded hubs, smooth stubs); K10 trades it for household gadgets whose normal
care is a brush. The soil has also **dried** before it is washed: prep ware is loaded in P2 and, for 2 persons, the
programme runs only after the meal (§3.6 P2: "for 4 persons this first load may run during cooking"), i.e.
1.5–2 h after use (PERF-005's rationale: drying makes cleaning harder). Expect the garlic press and the dicer to fail
HYG-020 (visually clean) after a household programme without brushing [E]; the camera cannot see into 2 mm holes.
R4 tests forces and food, not cleanability; add a riboflavin/ATP test after a real dishwasher cycle with 2 h dried
garlic and potato starch (HYG-027).

### 3.3 Who cleans the cooker (C3) — **major**

The boil-clean (water + detergent, ≈ 100 °C, high speed, 3 min) gives a huge A0 on surfaces it **wets**: jug wall,
blade top. It does not reach, or reaches only by splash:

* the **blade shaft seal** at the jug bottom — HYG-016 names "mixing-bowl seals" as the known weak point of
  kitchen machines; raw mince is mixed directly over it;
* the **hinged lid** (§2.1): its gasket lip, hinge, lock hooks and the measuring-cup opening — the lid never goes to
  the dishwasher;
* the jug's outside, handle and **drive coupling underneath**, the base top, the touchscreen and the vent slots,
  which get every drip from feeding, pouring and ladling;
* the "drained GN pocket" round the base: K10 has the nozzle rail rinse "bay, walls and pocket" (§3.6 P5), but a
  kitchen machine base is not water-jet proof [E: household kitchen machines are typically IPX0–IPX1]; rinsing the
  pocket floods the base, not rinsing it leaves a Zone S surface uncleaned (HYG-006).

And after detergent, a second clear fill is needed for HYG-023 (+≈ 2 min per boil-clean). In household use all of
these are wiped by hand. **No human cleaning (HYG-006) is not met for the cooker as installed**; K10's §6 does not
list these surfaces. Mitigation: cooker in a splash cover with only the jug opening exposed; jug removed and
emptied over the sink, never poured in place; a clip-on silicone sleeve over the base top that goes to the
dishwasher. All [U], none in the BOM.

### 3.4 No washing during the meal; the clean store (C2, C5) — **major**

* **PERF-005 (M)**: ready for the next meal within 30 min, completely clean, dry and idle within 90 min. K10: all
  clean 3–5 h after a 4-person meal (W1). This is a **Must failed**, not a "medium" weakness; it needs a requirement
  change by Ben, stated as such. With a household dishwasher's design life of ≈ 280 cycles a year (requirements, note to
  the REL life-cycle table), K10's 2–3 hygiene cycles a day (prep load, 1–2 after-meal loads, breakfast dishes) are 2.5–4 × the
  design duty [C]: the dishwasher becomes an LRU with a ≈ 3–4-year life (≈ €400–500 per exchange with the hygiene
  model), which REL-004 allows only if declared.
* **The clean store does not fit.** A 45 cm, 9-place dishwasher holds ≈ 9 × 11 small items or a few pots plus some
  plates. K10 must store: ≈ 40 stubbed items (pots, pans, lids, GN, tools), 8 gadgets, the jug, the two-level
  steamer, 2 boards, knives, mesh screens and the dish set for 4–6. K10 itself needs **2 loads per 4-person meal**
  [K10 W1]; between meals one load's worth has no closed store except the small tool caddy (GN 1/1-150) and the cold
  oven. The rest stands on the open deck: **C2 R-6** (clean ware behind a closed shutter) fails. And a Ø 280 pan
  with its handle (≈ 480 mm) does not lie flat in a slim rack [E].
* **Duplicates.** I4 counts a second board, knife, tongs and 2 GN 1/3. Without an in-meal wash every tool that
  touches raw food and then cooked or plated food needs a twin: turner (Frikadellen placed raw, served cooked),
  tongs, spatula, fork-spit, ladle, the egg fixture, the pan used for raw meat and then for a sauce. Realistic
  6–10 extra stubbed items (+€80–150 incl. stubs) [E], and more clean-store volume.

### 3.5 Splash, fat and vapour (C6) — **major for the oven and the X box**

* The 25 L mini oven hangs **directly above the domino** (oven X 520–860, z 1550; domino X 520–820): searing,
  Schnitzel in 220 mL fat at 170 °C and boiling rise into its painted housing, vents and knob panel — a Zone S
  surface the nozzle rail must not soak (mains appliance) and cannot clean. The rear fume slot helps (K9b P-8 / E8
  test) but does not stop rising aerosol under a mesh screen.
* The **dishwasher top is at z 1850, the X box at z 1900–2000**: when the hand opens the door after a 70 °C
  programme, the vapour plume rises 50 mm into the X box with the belt, the MGN15 rails (carbon steel unless
  stainless), cable chain and printed brackets. Neither K9c's labyrinth purge (needs the extraction running) nor
  K10 addresses it. Fix: open the door only with the extraction on and a drying pause (+10–20 min per load), or a
  hood between the dishwasher top and the X box.
* Furniture as enclosure is in practice K9c's Gastro table and stainless liners (§4.1 E1–E2); the "kitchen
  carcass" saving is accounting. New fixed crevices in the splash zone: the **lazy-susan bearing ring** under the
  raw-meat board (stays on the deck, only rinsed: HYG-013/-016), the lever-seat clamps, the peeler bracket.

### 3.6 Shared rail over open storage (C7) — **major for K10-W1**

* K10-W1 draws the ambient column with an **open top** under the X box (§7.2 figure: "[OPEN TOP]"). The X box is one
  air channel along 3.6 m from the wet cell (steam, fat aerosol, dishwasher vapour) to the storage: **STO-007**
  (≤ 25 °C, ≤ 65 % RH, ≤ 5 K above room) and **STO-008** (closed against insects, no opening > 1 mm to the room or a
  wet module except a closed exit) both fail as drawn. The storage round kept a dry gallery and a closed hatch on each
  module for this reason. Needed: a roof hatch on the ambient column and a partition (brush seal) in the X box at the
  cell boundary (≈ €150–200, not in K10's BOM).
* The same sleeve and hoist that just dug a raw-meat box (R) handle RTE boxes and then work in the cell; digging may
  set an R box on an RTE stack (storage 10 §4.1). CLD-011 needs a rule: R boxes on their own stack, never on top of
  RTE, sleeve jet-rinsed after an R grip.

## 4. Reliability and mechanics

### 4.1 Loads on the printer-class hand (D1)

K10 derates K9c's hand to **≤ 4 kg at ≤ 150 mm** and says nothing heavier than the full jug (≈ 3.5 kg) or "a pot of
pasta water (≈ 3 kg)" is lifted. Masses [C]:

| Item | Mass | Within 4 kg / 150 mm? |
|---|---|---|
| Full jug (empty ≈ 1.2–1.3 kg + 2.3 L) | ≈ 3.5–3.6 kg, CoM ≈ 100–130 mm from the handle | at the limit; inverting it to empty (§1.3) adds the roll moment ≈ 4–5 Nm (≤ 12 Nm ✓) |
| 5 L pot with 4 L pasta water | 1.2–1.5 kg + 4 kg = **5.2–5.5 kg** | **no** — K10's "≈ 3 kg" is the basket, not the pot |
| 3 L pot, 2 L water after the potatoes are lifted out | ≈ 3.0–3.3 kg | marginal |
| Eintopf for 4 in the 5 L pot | ≈ 4.5 kg | no (ladled, K10 says) |
| Rouladen braiser with gravy | 5–6 kg | no |

**Major:** the cooking water of every pasta and potato meal has **no way out** of the pot. K9b poured it through
the strainer lid at ≤ z 1200; K9c (payload 6 → 4 kg) said "slid, never lifted", but the K10 deck between the domino
and the sink is the lazy-susan board and the chute flap — no sliding path. Options: a pot with a bottom drain valve
over a deck drain (not household ware), siphon/pump-out by a hose stem tool (+€40, [U]), or ladling 4 L (≈ 30 moves,
≈ 5 min). None is in K10.

Push forces are inside K9c's limits for the presses (lever seat at y 130–240, 300 N there) [E: unpeeled garlic
≈ 100–200 N at the handle end, ricer 150–250 N, raw potato through a 10 mm lever dicer 300 N × 3 : 1]. The lever
handles move on an arc, so the tool tip must slide along the handle (roller tip); fine. Two open points: the
**garlic bulb must first be broken into cloves** (no route in K9b or K10), and **unloading** each gadget (skins out of
the ricer basket and press chamber, dice out of the dicer's container) means unclamping, inverting over the chute
and knocking — 5–6 cycles per kg of potatoes [C].

### 4.2 Mandoline on the fork-spit (D2)

* **End waste**: the spit stops 12 mm above the blade and its prongs hold ≈ 20 mm of the piece: per piece ≈ 30 mm is
  lost [E]. A whole cucumber (300 mm) on the spit levers the prongs by its length under a 10–30 N stroke force and
  breaks or spins, so it must be cut into ≈ 100 mm pieces first: 3 × 30 = 90 of 300 mm, **≈ 30 % waste** [C]. Potato for 1.5 mm slices (≈ 80 mm): **30–40 % waste** [C]; shallots,
  radishes, garlic: not usable. The waste goes to the bin — food cost and a texture-neutral but real loss; K10 counts
  only SD05 at risk.
* **Fixing the mandoline**: it stands on a GN 1/3 on the **lazy-susan board**, which turns freely; stroke forces of
  10–30 N need a lock (detent pin, [E]). Not in K10.
* **Safety**: in a closed cell the mandoline endangers only the machine (spit 12 mm over the blade needs Z ±1 mm
  under 10–30 N side load: fine for the ball-screw Z). It sits at the bay front, which is also the serving/return
  zone behind the panel the diner opens: an interlock rule "no blade in the bay when the panel unlocks" is needed.

### 4.3 Dishwasher turned 90° and raised (D3) — **major for the meal phases**

* **The open door covers the domino and the cooker** (X 570–1220 at z ≈ 1000–1060; the hand comes from above with
  a 300 mm drop link). K10's P0 ("door open, racks out; … pans and pots onto the domino or deck") is not possible:
  nothing can be set on the domino or taken from the cooker while the door is open, and the only other surface is
  the ≈ 0.15 m² bay (§1.4). P0, P2 and P5 therefore need **several door cycles** (open, rack out, take 1–3 items,
  rack in, close, place, repeat): ≈ 6–10 door cycles and 12–20 rack cycles per 4-person meal [E], 30–60 s each.
  That is +5–10 min per meal and **≈ 2,000–3,700 door and 4,000–7,000 rack cycles a year** [C]. R3's 3,000 rack
  cycles is ≈ 5–9 months; REL-004 needs 10 years × 1.5 or a declared LRU.
* **Door underside vs cooker top**: the tub floor of a household dishwasher sits ≈ 80–100 mm above its base (sump,
  pump) [E], so with the body at z 1000 the door hinge is at ≈ z 1080–1100 and the open door's outer face ≈ z
  1010–1040 — against the cooker top at ≈ z 1030 [K10 U]. Zero clearance as drawn; any pot lid knob on the domino
  (≈ z 1070–1090) collides. R10 is the right test; it may move the cooker (+150 mm width, K10's own fallback).
* **Upper rack**: pulled out at z ≈ 1400–1500, its far end reaches X ≈ 675 — under the oven (z ≥ 1550), where the
  arm is limited to z ≤ 1540. Loading tall items there is doubtful [K10 R3 lists "upper-rack reach"].
* **Drain**: the pump is now 600 mm above the sink trap; household installation rules require an anti-siphon loop
  [E]. Minor.

### 4.4 One rail over 3.6 m (D4, E4) — **major for W1**

* **Stiffness**: the X belt (HTD 3M-15) grows from ≈ 3 m to ≈ 7.2 m loop; belt axial stiffness at the far end falls by
  ≈ 2.5 × and the first axis resonance by ≈ √2.5 = 1.6 × [C]. K9c's K1 rig (1 m) does not cover it. MGN15 rails over
  3.5 m are butt-jointed segments that must be aligned across module boundaries; the 40 × 80 beam needs supports at
  each carcass. All feasible, none tested.
* **Hoist sway**: in W1 the hoist line hangs ≈ 1.2–1.4 m from the arm at z ≈ 1900–2000 into a fridge whose stacks end
  at z ≈ 120. A 1.3 m pendulum has a 2.3 s period [C]; placing a box in a 2 × 2 stack guide (±10 mm) after an X move
  needs damping or waiting, ≈ 2–5 s per pick [E].
* **Timing (W1)**: K10 books 20–25 boxes × 20 s = +8 min per 4-person meal. Missing: every box goes **back** after
  use (another 20–25 moves), each lid is taken off and put back at the bay with the suction-cup stem tool (tool change
  plus ≈ 10–15 s per lid), and deep boxes need digging (≤ 7 boxes moved per deep pick, ≈ 15 s each) unless pre-dug.
  Realistic: **≈ 15–20 min before and ≈ 10–15 min after the meal** on the cooking hand [E]. Added to §1.5, every
  4-person benchmark loses another 10–15 min of pre-cooking time unless the menu is planned the day before.
* **Cold hatch open time**: K10 §7.4 states "each move ≈ 15–20 s open". **CLD-004 (M) allows ≤ 10 s** per box
  passage. The storage round reached 3.4 s with a throat and a closing slide; K10's whole-top lid is open for the
  whole dig. Fails as written.
* **Single point of failure**: in W1 the same carriage, belt and roll unit do storage, cooking, dishwashing and
  serving. With the solenoid-latched hatch, a controller hang with power on leaves a **cold shell open**; a watchdog
  that drops the latch is required (REL-008: cold storage must keep its temperature when another module or the
  control fails). K9b's 0.7 unplanned exchanges a year rises with the doubled duty; REL-005 (≥ 6 months MTBF) is not
  assessed in K10.

### 4.5 Life of the bought appliances (REL-003/-004)

| Appliance | K10 duty [C] | Household design duty [E] | Consequence |
|---|---|---|---|
| Thermo-cooker (€219) | REL table: mixing/stirring 1.5 h/day → 5,500 h in 10 y | a few hundred to ≈ 1,000–2,000 h | LRU every 2–4 years; **Cecotec changes models yearly** (Mambo 9090 → 9590 → 10090 → 11090): the reverse-engineered interface (§2) must be redone for each successor — the biggest series and service risk in K10 |
| Slim dishwasher | 2–3 hygiene cycles/day ≈ 700–1,100 a year | ≈ 280 a year (requirements note) | LRU every 3–4 years |
| Mini oven (€70–130) | 0.5 h/day cavity + warm-hold + proofing | light household use | LRU; cheapest-tier knob thermostats drift |

## 5. Storage via open-top stacks and one hoist (E1–E4)

### 5.1 Capacity — **major (W1 fails CAP-021, a Must)**

| Store | Requirement | K10-W1 claim | Reviewer [C on storage round interiors, U] | Verdict |
|---|---|---|---|---|
| Fridge | CAP-021 ≥ 45 positions (M) | 30–32 | 122 cm built-in: interior ≈ 1,000–1,050 mm → 9 levels of GN 1/6-100 (110 mm) × 2 × 2 = 36 raw, compressor step −3…−4, dig reserve −4 → **≈ 28–30 usable** | **fails by 15–17 (−33…−38 %)** |
| Freezer | CAP-022 ≥ 20 (M) | ≈ 24 | 122 cm: ≈ 8 levels × 4 − step − reserve ≈ 22–24 | ✓ (the storage round's 178 cm freezer was capped at 9 levels anyway) |
| Ambient | CAP-020 ≥ 70 (M) + CAP-023 empties ≥ 25 before ingestion | 80–90 | 600 × 600 column z 120–1350: 11 levels × 9 stacks = 99 raw, ≈ 88 usable; the storage round's reference stock is 96 boxes | ✓ **only** with one stack of nested empties (S5-B idea, ≈ 40 nested in one position); not in K10 |

Two errors in K10's reasoning:

* "#17 lets non-cooking chilled goods move to an ordinary fridge" is **already inside CAP-021** — its source column
  cites DEC-17, and its 45 is "≈ 30 chilled types × 1.15 + 5 raw portions + 4 intermediates", i.e. cooking
  ingredients only. K10 counts #17 twice.
* "122–140 cm" appliances: W1 needs the storage tops at z ≤ 1350 (§7.2). On the 120 mm plinth a 140 cm appliance ends
  at z ≈ 1520. **Only 122 cm fits W1**, so the fridge is at the low end (≈ 28–30).

To reach 45 chilled in W1 needs a second fridge shell (+600 mm, breaks 3.6 m) or W2. Seasonings: CAP-020 asks
≥ 30 of the smallest size (GN 1/9 in the storage round's standard); a GN 1/9 does not stack on GN 1/6 guides, so
the ambient grid needs a second stack pitch (STO-006: any mix without hardware change) — not addressed.

### 5.2 Retrieval time — **major (STO-003 and CLD-006 fail without planning)**

Per pick on the K10 hand [C/E]: hook rod to the hatch, lift and latch (4–6 s), X travel ≤ 3 m at 0.8 m/s (2–5 s),
hoist ≈ 0.8 m down and up at ≈ 0.3 m/s (5–6 s), gripper toggle (2 s), sway settle (2–5 s), close hatch, travel to
the box shelf → **≈ 18–25 s for a top box** (K10: 15–20 s). Every box above the target costs ≈ 12–15 s to move
aside. In a 9-high stack:

| Case | Time | STO-003 (≤ 30 s, mean ≤ 15 s) / CLD-006 (≤ 45 s) |
|---|---|---|
| Top box | 18–25 s | ✓ / ✓, mean ✗ |
| Random box, mean 4 boxes above | ≈ 70–85 s | ✗ |
| Bottom box, 8 above | ≈ 120–145 s | ✗ (4–5 × the limit) |

The storage round accepted dig-from-top only **inside the cold shells**, with their own robots pre-digging while the
gallery is elsewhere, and kept random 6 s access for ambient (S4), where unplanned requests happen. K10-W puts
digging into **all three stores** and onto the **cooking hand** (W1): spontaneous meals, drink pouring (#13/#17) and
the 5–8 seasonings each meal uses wait for digs. Menu pre-digging works only if the plan is known the evening before
and runs with the hatch open (§5.3).

### 5.3 Cold hatches — **major (CLD-004 fails as written, CLD-007 at risk)**

* **CLD-004 (M): open ≤ 10 s per box passage.** K10 §7.4: "each move ≈ 15–20 s open"; a dig of 4 boxes keeps the lid
  open ≈ 1 min. The storage round's C1-B (throat + closing slide) took 3.4 s. Energy is not the problem (cold air does
  not climb; a full-top opening exchanges a few litres per move, frost ≈ 0.1 g per opening [C]) — the Must is.
* **CLD-007 (S): no change to the refrigerant circuit and insulation other than at the exit.** C1-B cut a 260 × 260
  window in a **verified middle band** of the top wall. K10 cuts **the whole top wall to a lid** "so that the hoist
  reaches all four stacks" — because without the in-shell XY robot the hoist must reach every stack from above. The
  top wall of built-in appliances carries hinge and fixing brackets, cables and control boards, and in freezers often
  the frame-heater loop (hot gas) and duct parts [E]; with R600a refrigerant a cut into a hidden line is a safety
  incident. This is the hidden price of deleting the cold robots; E1/E5 of the storage round (measure, thermal
  camera, cut a used unit) must be re-run for a **full-top** cut before W1 or W2 is credible.
* **REL-008**: the hatch is "latched open by a solenoid that releases on power loss" — a controller hang **with** power
  leaves it open. Needs a hardware watchdog/timer that drops the latch after ≤ 10 s (+€10).

### 5.4 W2 (two carriages on one rail)

W2 keeps 178 cm shells and the storage round's capacity, and moves storage time off the cooking hand: it fixes 5.1
and most of 4.4. It does **not** fix 5.2 (digging still from the top in all three stores; random access ≈ 70–85 s) or
5.3 (full-top cold lids). Two carriages on one rail pair need anti-collision zoning (the storage carriage parks over
storage; hand-over at the box shelf), and the storage carriage's own X belt loop runs the same 3.5 m.

## 6. Cost (F1–F3)

### 6.1 Arithmetic and line prices

The cell BOM adds up: gantry 600, hand 735, controls 560, enclosure 465, water 250, ware 510 = **€2,520** [C ✓]; the
appliance line €1,299 [C ✓]. The web-checked prices (Q1–Q11) are plausible; the Mambo at €219 is confirmed [W:
storececotec.de]. Lines that look low [E]: H6 brake NEMA 23 €45 (€50–80 usual), E6 deck job work €110 for three
cut-outs **and** a welded-in GN pocket with drain (€150–300 at one-unit job-shop prices), S1 X extension €260 for
2.1 m of profile, two MGN15 segments, belt, 3.5 m cable chain and a cover (€290–390), S6 €130 per **full-top** cold
lid (the storage round costed a 260 × 260 window at €300–335 per shell incl. motor; a 0.2 m² insulated lid with a
larger gasket costs more, not less), S7 stack guides €50 per shell (storage round €150).

### 6.2 What is missing

| Item | Why (section) | € [E] |
|---|---|---|
| **Cell** | | |
| Cooker splash cover and base sleeve | HYG-006 (3.3) | 30–60 |
| Pot draining: siphon/pump stem tool or drain-valve pot + deck drain | 4 kg limit (4.1) | 40–100 |
| Stubs on 6–10 duplicate tools (items themselves: kitchen content, +€50–100) | no in-meal wash (3.4) | 30–45 |
| Lazy-susan lock | mandoline, cutting (4.2) | 5–15 |
| Deck job work understated | 6.1 | 50–150 |
| Backflow preventer (EN 1717) on the machine's mains valves; leak tray and sensor under the raised dishwasher | REL-009, water damage | 50–100 |
| Stylus stem tool (R1 fallback) | 2.3 | 10 |
| **Cell subtotal** | | **≈ 215–480** |
| **Storage add-on** | | |
| X extension, stack guides understated | 6.1 | 130–330 |
| Full-top cold lids understated (2 shells) | 6.1, 5.3 | 240–340 |
| Ambient roof hatch (W1 "open top") and X-box partition at the cell boundary | STO-007/-008 (3.6) | 100–190 |
| Hatch watchdog | REL-008 (5.3) | 10–20 |
| Nest stack for empties | CAP-023 (5.1) | 20–40 |
| **Storage subtotal** | | **≈ 500–920** |
| **Appliance side** | | |
| Dishwasher with a validated hygiene programme instead of a €255–303 model | HYG-021 (3.1) | +150–250 |

### 6.3 Corrected totals (one unit, machine part)

| | K10 | Reviewer [E] |
|---|---|---|
| Cell (cooker as household appliance) | 2,520 | **≈ 2,750–3,000** |
| Cell like-for-like with K9c's €4,313 (cooker inside) | 2,739 (−37 %) | ≈ 2,950–3,200 (**−25…−32 %**) |
| Cell if R1 fails (K9c hub €435 + press cup €150 + S ware €110 back; cooker interface and funnel −€65) | — | ≈ 3,350–3,650 |
| K10-W1 whole machine (but fails CAP-021, 5.1) | 3,305 | ≈ 4,000–4,700 |
| **K10-W2 whole machine** (the only W variant that meets CAP-021) | 3,585 | **≈ 4,300–5,000** |
| Storage round + K10 cell | 7,450 | ≈ 7,700–7,900 |

The direction of K10's result holds: **bought thermo-cooker, dishwasher as bought and fewer custom parts cut the cell
by roughly a quarter to a third against K9c**, and one rail with top-dug storage cuts the storage handling by
≈ €3 k against the storage round. The size of the claim does not: the whole machine part is **≈ €4.3–5.0 k**, not
€3.0–3.3 k, at one-unit prices, before the requirement deviations of §5 are paid for.

### 6.4 What Ben actually pays (honest framing)

K10's accounting moves a lot outside "machine part": thermo-cooker €219, gadgets €295, kitchen content ≈ €400,
furniture ≈ €380, storage structure €700–900 (on "shelving"), **boxes ≈ €2,000** (on no line at all), and the cold
appliances at #28's €1,000 although the storage round found **€1,700–2,800** for built-in 178 cm units (W2). Out of
pocket for K10-W2 [E]: machine part ≈ €4.3–5.0 k + appliances ≈ €3.9–5.3 k (cell €1.45–1.55 k incl. hygiene
dishwasher, cold €1.7–2.8 k, shelving/structure €0.7–0.9 k) + boxes €2.0 k + gadgets, content, furniture ≈ €1.1 k →
**≈ €11–13.5 k**, against the ≈ €5–5.5 k Ben's #28 implies. Plus lifetime LRUs (4.5): 2–4 thermo-cookers and 2–3
dishwashers in 10 years ≈ €1.3–2.2 k. The report to Ben should state this whole number once, next to the
machine-part number.

## 7. Verdict and recommendations for round 2

### 7.1 Findings by severity

| Severity | Finding | § |
|---|---|---|
| **Fatal to a claim** | "Whole machine ≈ €3.0–3.3 k": W1 fails CAP-021 (fridge ≈ 28–30 vs 45) and CLD-004; the only compliant variant (W2) with the missing items is **≈ €4.3–5.0 k** | 5.1, 5.3, 6.3 |
| **Potentially fatal to the cost advantage** | R1: the named cooker has a touchscreen and a hinged lid; no published protocol for any thermo-cooker; IEC 60335-2-14 Ed. 7 restricts remote start; K10's fallbacks do not work on a touchscreen. If R1 fails, the cell returns to ≈ €3.35–3.65 k | 2 |
| Major | PERF-002 (b) Frikadellen and (d) soup fail on K10's own +10–20 min; B2, B4, B5 marginal; B8 has no route; W1 storage adds 15–20 min more | 1.5, 4.4 |
| Major | Coverage 232 has a range (229–232 reviewer) that straddles 231; no B1–B12 walk-through | 1.6 |
| Major | Only 2 pan positions on one 3.7 kW domino (not 3.4 + 2.0 kW); stirred browning lost with the hub | 1.1 |
| Major | Emptying sticky contents from a fixed-blade jug is untested; every chop/knead route depends on it | 1.3 |
| Major | Free deck ≈ 0.15 m²: no breading line, one plate at a time | 1.4 |
| Major | Dishwasher door covers the domino and cooker: P0/P2/P5 as written are impossible; 6–10 door cycles per meal | 4.3 |
| Major | HYG-021: household 65–70 °C gives A0 19–60; cheap models fail; K10 cannot extend the programme | 3.1 |
| Major | HYG-013: every bought gadget is a crevice part; HYG-006: cooker base, hinged lid, blade seal, pocket not cleaned | 3.2, 3.3 |
| Major | PERF-005 (M) fails (3–5 h); the clean store does not fit in a 9-place dishwasher; C2 R-6 fails | 3.4 |
| Major | Pasta and potato water (5.2–5.5 kg pot) cannot be emptied by the 4 kg hand | 4.1 |
| Major | Dig-from-top in all three stores: STO-003 / CLD-006 miss by 2–5 × without menu pre-digging; full-top cold lids risk CLD-007 (R600a) | 5.2, 5.3 |
| Major | W1 open-top ambient under a shared X box fails STO-007/-008; dishwasher vapour rises into the X box | 3.5, 3.6 |
| Minor | Factual slips: "≈ 3 kg" pasta pot; 140 cm appliances do not fit W1; #17 counted twice; B4 80 min vs "+15 min on K9b's 88"; mandoline waste 30–40 %; dishwasher drain siphon; upper-rack reach | various |

### 7.2 Is K10 a better base than K9b/K9c?

| Criterion | K9b | K9c | K10 (reviewed) |
|---|---|---|---|
| Coverage / food | 233, reserve 2; 3 pan positions; stirred browning | as K9b | 229–232; 2 pan positions; better sauces, risotto, emulsions |
| Time (PERF-002) | B3 45/50, B6 46/50 | slower hand | B3, B6 fail |
| Hygiene | 82 °C well, turnaround load, ware designed to HYG-013 | as K9b, riveted stubs, donor tub | A0 marginal, gadget crevices, cooker body uncleaned, PERF-005 fails |
| Mechanics / reliability | 6 actuators, canned hub | 6, printer class | 4 actuators, but appliance-door cycles, consumer cooker as LRU with yearly model churn, R1 |
| Simplicity (#20, high weight) | ≈ 7.3 | better | **best**: ≈ 18 custom part types, 4 actuators, appliances as bought |
| Cell machine part | 6.8 k (series) | 4.3 k | **≈ 2.75–3.0 k** (corrected) |
| System fit | 1,750 mm, bench, hatch drawer | 1,660 mm | 1,800 mm; dishwasher over the hot zone; tiny deck |

**Verdict: K10 is the better source of principles, not the better base.** Its genuine gains — a bought
thermo-cooker instead of the custom hub, appliances used as bought, the Klipper/Gastro/folded-stub cost discipline,
and one shared rail for storage and cell — are each separable. Almost all of its Must failures come from one layout
decision: **the front-door dishwasher raised over the hot zone as the only washer and the only clean store**, which
takes the bench, forbids in-meal washing, phases every meal around a door and caps disinfection at household level.
The second source is W1's single carriage. Neither is needed for the cost gain: of K10's −€1,574 against K9c (like-for-like,
K10 §4.4), the dishwasher-as-bought accounts for €240, the cooker for ≈ €480 (hub −216, press cup and S ware −260),
and ≈ €850 is enclosure, hand, controls and ware discipline that any base can adopt.

### 7.3 What round 2 should take from each

**From K10:**
1. The **bought thermo-cooker** as the stirred, blending, kneading and weighing position (replaces hub, S, press
   cup, kneading roller) — **conditional on R1** run as: Tuya/network check (1 day) → UI ↔ power-board bus sniff and
   replay on a Monsieur Cuisine or Mambo (2–4 weeks) → stylus-on-touchscreen as the fallback. Never bypass the power
   board. Buy two units of one model at once (model churn).
2. **One rail pair, two carriages (W2)** as the storage gallery: saves the separate gallery axis (≈ €500) and the
   in-cell box transport. Not W1.
3. The 5 L 85 °C boiler, Klipper single-board controls, folded riveted stubs, Gastro-table deck with liners, the
   countertop convection oven (but not directly above the domino without a fume hood path).
4. Bought gadgets **only where they pass HYG-027 after a real dishwasher cycle with 2 h dried soil**: ricer first,
   unpeeled-garlic press second; dicer and mandoline only as fallback to knife and a processor disc.

**From K9b/K9c:**
5. A washer that meets **PERF-005 and HYG-021 with margin**: K9c's donor-tub well under the deck (top-loaded, 82 °C
   rinse from the boiler, turnaround load possible), or — to be explored [U] — a bought single **dish drawer**
   (top-loaded by nature, no door swing) turned 90° under the deck. No appliance door that opens over the hot zone.
6. A **bench of ≥ 0.25 m²** besides the board (K9b's well lid) and K9b's hatch drawer or an equivalent that presents
   two plates side by side.
7. A **third pan-capable hot position with its own generator**: K9c's €50–70 single induction plate, used as bought
   on its own phase, restores 3 pans and ≈ 5.7 kW of pan power at ≈ +€60 and ≈ +300 mm, or under the cooker's
   place if the cooker moves.
8. Storage is a decision for Ben, shown as two honest options:
   * **A — compliant**: the storage round's cold access (C1-B throats, ≤ 10 s) with its lean in-shell stack robots
     and S4 ambient, the shared rail (7.3-2) as the gallery: storage handling **≈ €3.7–3.8 k** (K10 §7.4 "lean"
     row ≈ €3.8 k, gallery replaced by the second carriage).
   * **B — cheap**: K10-W2 top-digging in all stores, **≈ €1.6–2.0 k** (corrected, 6.2), only with Ben's explicit
     waiver of STO-003/CLD-006 for unplanned boxes and after a full-top-lid cut test with per-stack sub-lids
     (CLD-004, CLD-007).

Expected cell from 1–7 [E]: **≈ €3.3–3.5 k** (K9c €4,313 − hub/press cup/S €695 + cooker interface €65 + induction
plate €60 − K10's ware, controls and enclosure discipline ≈ €350–450), coverage back to K9b's 233 plus the cooker's
sauce gains, PERF-005 and HYG-021 met. That is **≈ €0.3–0.7 k more** than the corrected K10 cell for six Must
requirements kept — the trade Ben should be shown.

### 7.4 Tests, in order, before any further cost round

1. **R8 + B1–B12 table** (desk, 2 days) with K10/K11 station times; **E0 simulation** including dishwasher door
   cycles, jug emptying, boil-cleans and storage moves (1–2 days).
2. **R1** as in 7.3-1 (2–4 weeks, €219–400).
3. **Jug emptying** (§1.3): 20 × chopped onion, Frikadellen mass, 500 g dough, risotto; residue by weight (€0 on the
   R1 unit, 2 days).
4. **Dishwasher A0** with loggers on a PE board and a heavy pan in a full load: one €280 model, one hygiene-option
   model (€0 if R3's unit is used, 1 week).
5. **Gadget cleanability** (HYG-027): garlic press, ricer, dicer, mandoline after 2 h dried soil, one household
   programme, riboflavin + ATP (€50, 3 days).
6. **R10 1 : 1 mock-up** with the real cooker height and dishwasher door geometry (€50, 2 days).
7. **Full-top cold lid** cut test only if W-type storage is pursued (storage round E1/E5, €300, 2 weeks).

### 7.5 Questions for Ben that K10 should have asked as requirement deviations

* PERF-005 (M): accept "all clean 3–5 h after the meal" — or pay ≈ €0.25–0.3 k (K9c's donor well instead of the
  dishwasher as bought, K10 §4.4) for a washer that does it in ≤ 90 min?
* CAP-021 (M): 45 chilled positions are already cooking-only (#17 is inside). Keep 45 (W2 / 178 cm shells), or accept
  ≈ 30?
* STO-003 / CLD-006 (M): accept 1–2 min for unplanned boxes, with menu-based pre-digging?
* The **whole** out-of-pocket figure (≈ €11–13.5 k for K10-W2 incl. appliances, boxes and household items) next to
  the machine-part figure, so the €2 k target is judged against the right number.
