# C2 — Critique of the preparation concepts K1…K8: hygiene, cleanability, food safety

Round P4, critic C2: the view of a hygienic-design auditor and a food microbiologist. Yardsticks: the brief
("the human will not clean anything"), DECISIONS 1–15 (in particular **6**: the machine now also washes the
dishes returned at the hatch, and **8**: it washes, peels and cuts all fresh produce itself), requirements
HYG-001…061, FSF-010…070, WSH-001…016, RES-001/-005, PERF-005, HUM-007/-012, and the design-rule checklist of
`research/06-hygiene-cleaning.md` section 11 (quoted as "R6 A1…H34").

This version replaces an earlier C2 draft that was written before decisions 6 and 8. It was written afresh from
the sources.

**Status.** All eight concept documents are paper estimates by their own advocates. So is this critique:
nothing was tested. Markers: **[D]** taken from the concept document (section given), **[C]** recomputed by me
from the document's own figures or from physics, **[E]** my estimate.

**Severity.** **fatal** = a mandatory (M) hygiene or food-safety requirement cannot be met without giving up a
defining element of the concept; **major** = a mandatory requirement is missed as designed, or a hygiene claim
does not hold as stated; **minor** = weakness with a known remedy that does not change the concept.
**Fixable** = fixable while the concept stays the same concept ("partly" = the remedy exists but costs a
defining advantage or an untested part).

**Scope of reading.** Read in full: BRIEF, DECISIONS, the exploration brief, R6, requirements sections 1.4,
3.5–3.8, 6.3–6.6, 7, and in every concept document the definition, mechanism, penetrations, ware list,
cleaning, numbers, failure, risk and open-issue sections. Benchmark walk-throughs, operation tables, the two gap
documents and the catalogue were read selectively (B1–B3 and B12 in most concepts; hygiene-relevant passages of
the gap documents; the catalogue's cleaning mechanisms SM-188…216 and its common findings).

---

## 1. Summary

(Scores and counts are completed in section 5; draft.)

---

## 2. Cross-cutting findings

### C-1 Thermal disinfection: claims without margin, and A0 applied to dry heat

HYG-021 asks ≥ 5 log on ware that touched class R food, by A0 ≥ 60 at the **surface** (80 °C for 60 s,
85 °C for 19 s, 90 °C for 6 s) or a validated equivalent. A0 is a **moist-heat** measure (EN ISO 15883 logic):
it counts only while the surface is wet or in saturated steam. Dry heat at 100–110 °C kills vegetative bacteria
orders of magnitude more slowly; dried *Salmonella* is notoriously dry-heat tolerant. Recomputed:

| Concept, step | Claim [D] | What the physics gives [C] | Verdict |
|---|---|---|---|
| K2 induction flash (§6.2 step 4) | "105 °C for 45 s, A0 ≥ 60 in the first second" | The part is **spun at 900 rpm before** the flash (step 3), so the flash heats a nearly dry surface; only the seconds in which a residual film boils count as moist heat. The rim spool heats by conduction only (explorer: M). Blades, whisks, grids, polymers get a 20 s 80 °C rinse: A0 ≤ 20 | claim not supported; **major** |
| K3 drum flash (§6.2 step 5) | "110 °C for 60 s, A0 far above 60" | Same: spin at 450 rpm, then dry heating of the empty drum | claim not supported; **major** |
| K6 wells (§6.1) | "20 s at 85 °C plus the time above 75 °C gives A0 ≥ 60 on every cycle" | Ware enters the rinse at ~60 °C from the tank; a surface at 85 °C for all 20 s is not reachable. Commercial undercounter washers (the hardware K6 borrows) are built to put ~71–74 °C on the ware surface, A0 rate 0.13–0.25 per s. Realistic A0 10–40 | margin negative; **major, fixable** (rinse hold 60–90 s, or a validated heat-unit equivalent, proven with loggers on the coldest item) |
| K8 full wash (§6.2 step 4) | "each vessel 6 s in the gate at 85–90 °C" | Even at 88 °C instantly: 6 s × 6.3 = A0 38. Only the red-to-green rinse (25 s at 88 °C) approaches 60, and only for the items it is applied to | **major** for class R ware |
| K5 tube (§6.2) | "1 L at 85 °C for 45 s, A0 ≥ 60 after 15 s" | 1.6 kg of tube from ~55 °C needs ~24 kJ to reach 85 °C; 1 L of 85 °C water cooling by 5 K delivers ~21 kJ. The wall peaks near 80 °C: A0 ≈ 30–45 | marginal; **major, fixable** (2 L or 90 s) |
| K4 steam slot (§6.2) | "1 mm mat reaches > 90 °C: A0 > 60" in 4 s | At 90 °C, 4 s = A0 40; 30 g of steam per pass (68 kJ) just heats 1.3 kg of mat by ~35 K from the rinse temperature: zero margin | marginal |
| K4 cutting mat K after raw meat (§5 B1, §6.2) | "held three times for 60 s in the rinse stage" | The rinse stage is 40 mm long: stopping the mat treats 3 × 40 mm of a 2.4 m mat (5 %) | **wrong**; see K4-2 |
| K1 rod tip (§6.2 step 4) | "60 s at 80 °C after class R" | A0 60 only if the tip is at 80 °C for all 60 s; hot water first on protein soil (R6 E19 forbids) | zero margin |
| K7 slot washer steam (§7.2) | "0.3 kg tray > 90 °C within 3 s" | Condensing steam can do this on a thin tray, the most credible disinfection claim of the eight; but 8–10 g in 6 s needs ~1.5 g/s, twice what a 2 kW generator makes (R6 §2.4: 0.7 g/s) unless it has a pressure buffer, and the slot is open at the top | plausible, under-powered |

Rule for round 2 (R-3, section 8): only moist heat counts; every A0 is to be shown with a data logger on the
coldest item of the worst load; a dry flash is a drying step.

### C-2 Water and energy per reference meal, recomputed

Common additions to every concept's own cleaning figure [E]: **dishes 10 L / 0.9 kWh** (DEC-6; the RES-005
rationale already assumes 10 L), **cooking water 4 L**, **produce washing 5 L** (DEC-8; GP-W1 in
`gaps/G-produce.md` needs 6–12 L per 200–300 g of gritty leaves, robust produce 2–4 L), **cooking energy
1.3 kWh** (RES-001 rationale).

| | Explorer, cleaning only [D] | Corrections [C] | Recomputed total water / energy |
|---|---|---|---|
| K1 | 90 L, 5.9 kWh | seam fresh flush 6 × 5 s × 15 L/min = 7.5 L, booked as 1 L; +0.5 kWh | **~118 L, ~8.9 kWh** |
| K2 | 38 L (26–45), 1.8 kWh | daily wash-down of 12 m² with 10 L (C-3) not corrected here | **~57 L, ~4.0 kWh** |
| K3 | 24 L in place + 6 L daily share + 18 L ware | — | **~64 L, ~5.1 kWh** |
| K4 | 15 L in cell + 18 L ware | gate pre-rinse and rinse 13–27 L instead of 4 L (K4-3); rinse heat +0.35–0.95 kWh | **62–76 L, 4.7–5.3 kWh** |
| K5 | 32 L in place + 18 L ware | — | **~69 L, ~4.8 kWh** |
| K6 | 35 L (33–42), 2.3 kWh | — | **~54 L (52–61), ~4.5 kWh** |
| K7 | 21–25 L + 17–20 L chamber | + cold side 0.2 kWh per meal | **57–64 L, 5.0–5.2 kWh** |
| K8 | 26 L full wash + 3–8 L | gate 12 L/min × 6 s = 1.2 L per vessel, not 0.6; puck rinse 2 × 20 s × 12 L/min = 8 L uncounted: full wash ≈ 38 L, ≈ 2.8 kWh | **60–65 L, ~5.3 kWh** |

RES-005 (M) is 45 L, RES-001 (M) 4.0 kWh. **Every concept misses water; only K2 reaches the energy limit, and
only because its splash-zone wash is under-budgeted.** Either the requirement is re-based (it was written before
DEC-6 and DEC-8), or round 2 needs water recovery as a design feature (final rinse kept as the next pre-rinse,
heat recovery from the drain, washing only full loads).

### C-3 Splash-zone wash-down: budgets without nozzle plans, and HYG-045

| | Zone S [D] | Wash frequency [D] | Fresh water per wash [D] | Fresh L per m² [C] |
|---|---|---|---|---|
| K1 | 5.6 m² | after every warm meal | ~17 L (+7.5 L seams) | 3.0–4.4 |
| K2 | 12 m² | daily | ~10 L | 0.8 |
| K3 | 11.5 m² | daily (drum and belt per meal) | 12 L | 1.0 |
| K4 | 8.3 m² | daily | 6 L | 0.7 |
| K5 | 5.0 m² | daily | 13 L | 2.6 |
| K6 | 10.7 m² | daily, at night | 10 L + the day's tank liquor | 0.9 |
| K7 | 9.3 m² | daily | 5 L rinse + 10 L sump | 0.5 |
| K8 | 3.25 m² tub | every meal | 3 L spray-ball rinse + 8 L wash | 0.9 |

R6 §2.3/§9.4 estimates 25–40 L per wash and rinse of a 2.4 m² wash-down cell. About 1 L of fresh rinse per m²
is a dishwasher figure for a closed tub with recirculation; it is credible for K8, doubtful for an open,
cluttered bay with a gantry, hob tiers and stations. **No concept gives a nozzle plan (nozzles × flow × time) for
its splash zone**, and HYG-019 (spray-shadow-free, proven) is deferred to a weekly riboflavin self-test in all
of them.

**HYG-045** forbids any Zone F/S surface to stay soiled *and* wet for more than 4 h. A lunch cooked in an open
bay leaves condensate, fat aerosol and splashes of meat juice on walls, gantry and hob surround; if the wash is
"daily, at night" (K6) or "daily" (K2, K3, K4, K5, K7), those surfaces are soiled and damp for 6–12 h unless a
drying step runs after each meal. Only K1 (per warm meal) and K8 (per meal) wash their splash zone after every
cooked meal. Remedy for all: a fan dry-out after every meal (RH < 65 % in 60 min, HYG-053) plus a per-meal wash
of the hob surround.

### C-4 DECISION 8 (machine washes, peels and cuts all produce): what it does to hygiene

* **Class R grows.** Definition 1.4 makes "unwashed soil-bearing produce" class R. Every place that receives
  unwashed potatoes, carrots, leeks, herbs, lettuce becomes a red station: K1's jet gate G1 (which also rinses
  tools), K2's dock collar and feed sleeve, K3's chute and drum, K4's mats P and K, K5's tube chute and tube, K6's
  sink bench, K7's sink well, K8's basket on the turntable in the same tub. FSF-042 asks the wash **before** any
  shared tool touches the produce. In K3 B2 (§5) a cucumber is slid onto the belt and sliced without any wash;
  in K8 B1 potatoes are spike-peeled at t = 100 min with no wash step. Walk-throughs must be redone.
* **Sand.** Field soil carries quartz grains of 0.1–0.5 mm (G-produce §8.1). They pass every 2 mm strainer
  named in the concepts and reach recirculated sumps, circulation pumps and nozzles: K1's seam holes are Ø 1.0 mm
  (K1-2), K2's lathe nozzles Ø 1.5, K8's spray balls and gate recirculate 40 L/min from the sump, K5's chip box
  drains into its sump. A settling trap upstream of every recirculation pump is needed (rule R-8).
* **Waste.** Peel slurry (about 200 g per kg of potatoes, wet and starchy), onion skins (dry flakes that fly),
  pepper plugs, cabbage cores: 100–400 g per meal (G-produce open issue 9). Starch slurry dries into a glue within
  an hour (R6 §3); every concept must flush it within minutes, not "at the end of the meal" (K1 gutter, K5 chip
  box, K8 floor).
* **Wet time.** More produce work means the wettest stations stay wet for longer and are used more often: the
  drum in K3 (80 % busy in B3 already, §5.13), K6's sink, K7's sink well.
* **Washing does not make raw salad safe** (about 1 log, G-produce §8.2). Raw produce that is not cooked stays
  RTE-with-risk; no concept should promise more.

### C-5 DECISION 6 (used dishes returned at the hatch)

* Dishes come back with saliva, leftovers and sometimes raw-egg desserts, tartare or a sick household member's
  norovirus. The hatch becomes a **dirty return point and a clean serving point** at once: HYG-005 at the hatch
  needs its own design (separate return drawer or a wash of the hatch after every return).
* Which washer takes them: K6's wells (five plates per load; dishes need a tanged carrier), K7's slot washer (flat
  plates at 70 s each: 12–16 dishes = 15–20 min), K2's lathe (one plate per 4.5 min: not realistic), K8 (tub
  explicitly not; §6.3), K1/K3/K4/K5 a central washer. Cutlery and glasses fit none of the in-cell washers.
* The 10 L of the RES-005 rationale was meant for a human-loaded household machine; in-cell washers with 85 °C
  rinses use more energy per dish.

### C-6 The oven, the hood and the grease path — nobody cleans them

Every concept buys a combi-steam oven, turns it by 90° and replaces its door. None designs the cavity cleaning
(K2 open issue 4: "not washed by the machine"; K1 request A4 needs a front that tolerates jets). Burnt-on
spills in a household cavity need pyrolysis (3–7 kWh, R6 §2.4) or a self-cleaning commercial unit. Extraction
ducts, condensers and grease traps (HYG-039, weekly, "no grease filter washed by a human") are named by K1 (fixed
nozzles), K5 (hood mesh and condenser flushed weekly), K4 (grease trap), and not designed by anyone. K4 and K5
hang the oven or a condensing coil directly above open pots (K4-6, K5-6).

### C-7 Verification is by proxy, and allergens cannot be verified at all

All concepts log process parameters and use cameras (some with UV-A) and a weekly riboflavin self-test. That is
the R6 §8.2 stack, good for "visibly clean" (HYG-020). It cannot show HYG-021 (microbiologically clean) or
HYG-022 (allergen-free): ATP and protein swabs are manual and only at service. For a household with a declared
allergy the only safe answer is **dedicated ware** for that allergen, not a cleaning claim. A second weakness is
common to the concepts with fixed food surfaces (K1 cell, K3 drum and belt, K4 table and blade, K5 carousel, K8
tub): when a fixed surface fails verification twice, there is no spare, and the meal stops.

### C-8 Recirculated liquors held all day

K6 keeps a 10 L tank at 60 °C and dumps it once a day; K7 a 6 L tank, dumped daily; K2 reuses the lathe liquor
for three loads (RTE first); K5 one 2.5 L liquor for three tubes and the parts basket; K8 8 L per meal. Liquor that
has washed raw-meat ware and flour is re-sprayed onto the next load and, in K6, onto the whole bay. Detergent at
pH 11–12 and ≥ 60 °C is hostile to vegetative bacteria, but allergen proteins and starch redeposit, and between
meals a tank that cools into the 25–55 °C band is a culture medium. Rule R-7: dump after class R or allergen
loads, or hold at ≥ 60 °C; never let soiled liquor stand warm.

---

## 3. Findings per concept

### K1 — Ceiling turret cell

| # | Finding | Where [D] | Severity | Fixable |
|---|---|---|---|---|
| K1-1 | **Six annular seam gaps above the whole deck.** 4 mm × 45 mm, 7.3 m long, 0.65 m² of gap wall over open food. In the wash, 40 holes of Ø 1.0 mm per seam spray recirculated liquor at 0.5 bar at the *rotating* rim wall; whether the fixed coaming wall is wetted at all "is not known". The liquor runs down both walls and drips into the cell. The gap interior is invisible to the ceiling cameras; the only signal is total flow per seam. In operation the 0.3 m/s outflow keeps aerosol out only while the plenum pressure holds; grease and flour carried in during a fan fault or door opening stay there. The ceiling is flat (R6 A4: ≥ 5°). The explorer: "Fallback: there is none inside the concept" | §2.1 q2, §2.4, §6.7 #1, risk 1 | **fatal** (until the full-size soil and riboflavin test of risk 1 passes) | no |
| K1-2 | **Seam holes of Ø 1.0 mm fed from the recirculated sump.** R6 §2.7: scale and particles block 1–2 mm holes. Under DEC-8 the jet gate washes soil-bearing produce into the gutter, whose chip box has 2 mm holes: sand of 0.1–0.5 mm reaches the sump and the 240 seam holes. A blocked arc leaves a dry sector that per-seam flow cannot see | §2.4, §6.6; C-4 | major | partly (seams on filtered, softened fresh water; pressure per arc) |
| K1-3 | **Rod tips are Zone F with a PTFE lip seal Ø 14, a ball-hex and a Ø 4 bore** inside every tool socket above food. After class R: a 60 s 80 °C flush in the collar — hot water first on protein (R6 E19), no detergent, A0 60 with zero margin (C-1) | §2.4, §6.2 step 4, §6.7 #3 | major | yes (cold → detergent → hot sequence; A0 logged at the tip) |
| K1-4 | **Soiled and potable water share one bore.** The same Ø 4 × 600 mm bore doses drinking water into food, carries vacuum and air, and — through drain wand V17 — sucks cooking water and salad wash water at 1.7 L/min to the drain pump (B7 salad, §4.4 WLF and DRN). A potable path that alternately carries starch water is a cross-connection (EN 1717 fluid category 5) and a 600 mm dead leg above food; the explorer flags it as open issue 4 | §2.3, §2.7 V17, §4.4, §12.1 #4 | major | yes (drain wand with its own hose through the collar, or drain by basket only) |
| K1-5 | Four PEEK scraper rings and drained lantern chambers above food; the wettest items after the wash (about 30 min); plus V-ring leak-off troughs above the ceiling that collect jet water | §2.4, §6.3, §6.7 #2, #14 | major | partly (LRU cartridges; hot air through lanterns) |
| K1-6 | **Mechanisms as ware:** the roll head is an open stainless worm with a PEEK wheel and plain bushes (wear debris of PEEK into food, soil in the mesh — explorer risk 6); pinch tongs V21 have a core-driven face cam and silicone fin-ray fingers (every fin a crevice) | §2.6, §2.7, §6.7 #13 | major | partly (closed wrist outside Zone F; one-piece tongs as in K6) |
| K1-7 | **Aerosol of class R water in an open cell.** Mid-meal bench rinse after raw meat with an 80 °C, 5 bar lance while pots stand open on the hobs (B1: potatoes after Rouladen). The jet gates spin tools at 300–600 rpm to dry them and, under DEC-8, wash soil-bearing produce in the same fans | §2.8, §4.3, §6.5 | major | partly (lids on; flood rinse at < 1 bar; enclosed gate) |
| K1-8 | **Water, energy, time.** Recomputed ~118 L, ~8.9 kWh per reference meal (C-2): 2.6 × RES-005, 2.2 × RES-001. Cell free 43–50 min after serving (relays 10–17 min + wash-down 33 min): PERF-005 (30 min) missed. Ware in three loads of 55–75 min in series: the third load starts about 2 h after the food left it (HYG-030: ≤ 60 min, M); everything clean after 3 h (90 min required) | §6.2, §6.3, §6.4 | major | partly (fast washer; half the ware) |
| K1-9 | **HDPE board discs** carry every knife job (2 cuts/s, 240 cuts for a cabbage). Scored HDPE holds soil; no roughness check, no replacement interval, and the steel core bond line is a crevice. Red and green discs share the one BT pedestal and its umbrella skirt | §2.7 fixtures, §6.7 #6 | major | yes (interval, camera roughness check, human exchange under HUM-007) |
| K1-10 | Peel and trimmings wait in the open rear gutter under the rails and jet gates until the wash (B1: potato peel from t = 105 min); with DEC-8 the peel load rises to 100–400 g per meal | §6.6 | minor | yes (flush after each peeling job) |
| K1-11 | **Verification and failure.** Seam interiors, rod bores and collar lanterns are never seen; a cell that fails its check has no spare (§9: "local lance path repeated once, then flagged") | §6.3, §9 | major | partly |
| K1-12 | Hob silicone joints and burnt-on sugar or milk with "a scraper tool not provided"; oven front inside the lance zone (A4) | §6.7 #8, #9, §12.1 #13 | major | yes (scraper tool; jet-proof oven front) |

Separation (FSF-040): red board, mat, breading trays, knife, comb, fork, tongs as dedicated ware; RTE on BT
(zone 1), raw work on the bench (zone 2) travelling right; but the rods, rod tips, the bench, the jet gates and
the deck are shared and separated only in time, in one air space.

### K2 — Vessel stack and inversion

| # | Finding | Where [D] | Severity | Fixable |
|---|---|---|---|---|
| K2-1 | **The induction flash is dry heat.** Rinse 20 s, **spin 900 rpm 15 s, then** flash 105 °C 45 s: A0 is claimed for a surface that has just been spun dry (C-1). The rim spool heats by conduction only. The 14 items that are not flashed (blade and whisk kits, grids, slicer, grater, sweep knife, wedge disc, kneading lid, folders, apron, gasket frame) get an 80 °C rinse "instead", 0.8 L over 20 s: A0 ≤ 20. Class R ware is not shown to be disinfected | §6.2 steps 3–4 and table | major | yes (flash wet in a steam hood before the spin; or a 60–90 s hold at ≥ 82 °C; loggers) |
| K2-2 | **Drive above open food at K/H.** The quill enters the tier ceiling with a bellows (linear) and a spindle lip seal with leak-off, directly above the pot where ricing, whisking, kneading and cooking happen. Its nose is a fixed Zone F item (drinking-water outlet, bayonet for stalk tools) and is washed "only by the K/H tier nozzles, daily" — HYG-033 wants fixed food-contact stations cleaned after each meal. The explorer calls HYG-004/-016 "accepted conflicts, not solved ones". If the drain stalk (dip tube on the quill) returns cooking water through the quill bore, K1-4 applies; the document does not say | §2.3, §4 DRN, §6.3, §12 open issue 6 | major | partly (nose wash cycle after each use; separate drain path) |
| K2-3 | **One shaft for all traffic.** Clean ware from the rack, soiled ware to the seat and lathe, raw meat trays, RTE salad, waste beakers all move through the same 440 mm shaft past the same jaws; the rinse seat at its foot sprays upward into inverted class R ware; a leaking hot joint drips into the shaft. HYG-005 (no crossing of clean and dirty) is met only by time. The jaws are rinsed with cold mains water for 3 s after a class R grip: the one shared contact path, not disinfected | §1, §2.4 seat, §6.3, §6.5 | major | partly (hot jaw rinse after every soiled grip; lids on RTE vessels in transit) |
| K2-4 | **12 m² of Zone S washed daily with about 10 L** (§6.4: 5 L as half a day's share): shaft, four stacked hob tiers with scraper spindles, tip cradle, turntable ring, dock, lathe chamber, oven. Tier ceilings slope 3° (R6 A4: 5° for ceilings). No nozzle plan (C-3) | §6.1, §6.3 last row, §6.4 | major | partly |
| K2-5 | **K/H annular turntable labyrinth**: boil-over runs into it; flushed by two nozzles, "inspected by endoscope at service; a real harbourage risk" (explorer) | §2.3, §6.3, §9 | major | partly (drained trough the washer can see; umbrella the camera can check) |
| K2-6 | **Full-height Z slot with a magnetically held sealing band** and an **open telescopic X slide with rack and polymer plain bearings** beside every carried vessel, in the splash of any leaking hot joint (fat at 100–200 °C, explorer risk 2) | §2.2, §6.3 | major | partly |
| K2-7 | **The oven cavity is not cleaned** by the machine; burnt-on spills stay (C-6) | §6.3 last rows, §12 open issue 4, R6 | major | yes (self-cleaning oven) |
| K2-8 | **Numbers.** ~57 L and ~4.0 kWh recomputed (C-2); only the splash-zone budget keeps energy at the limit. Time is good: first stations free 10 min after serving, all ware clean after ~55 min (PERF-005 met) | §6.4 | major (RES-005) | partly |
| K2-9 | Single-instance discs (grid, ricer, slicer, die disc, egg cassette: 14 types without a second instance) shared between class R and RTE by sequence or a lathe cycle that does not disinfect blades (K2-1) | §6.5, §9 | minor | yes (red set of the two raw-used discs) |
| K2-10 | Dock: a dry place with flour dust and oil drips, washed weekly by two nozzles, "wetting flour dust makes paste" (explorer L–M); coupler-ring silicone beads take up onion and curry odour (HYG-025); egg cassette, die gate and collar shutters have pins and slides | §6.3 | minor | yes |

Separation: instance and time. The bare-metal, seal-free, one-rim ware is the best ware concept of the eight for
cleaning; the cell around it is not.

### K3 — Drum and belt line

| # | Finding | Where [D] | Severity | Fixable |
|---|---|---|---|---|
| K3-1 | **A fixed TPU belt is the food surface for raw meat and RTE.** R6 §6.2 rates belts "only in a dry tunnel; do not use in splash zone", and its material table gives TPU "hydrolysis > 60 °C" — the belt gets 55 °C detergent and a 90–95 °C steam pass every wash (grade "unverified"). Soil traps named by the explorer: belt edges and the first 10 mm of the inner face, pocket rollers and bed gap, nose bar and its cantilevered rails, the G1 blade clamps, the comb blade roots, the rod collars. Not named: the **wash box itself** (closed, wet, under the bed, never inspected), the longitudinal drain grooves of the slider bed, the dancer loop. The inner face is never seen by a camera; comb and press plate press onto the belt and will cut it | §2.2, §6.1 rows 6–10, §6.3, §12.2 #8 | major (**fatal if risk R2 fails**: the belt is half the concept) | partly |
| K3-2 | **The drum flash is dry heat** (spin 450 rpm, then 110 °C for 60 s; C-1). Silicone-edged heads do not take it and "leave wet"; the knurled peel disc holds starch; the helix-fin root and the rolled lip depend on weld quality | §6.2 | major | yes (hot rinse hold or wet flash) |
| K3-3 | **The dock chute is shared** by raw meat packs, RTE doses and powders ("must be dry before powder" after a wet rinse), and raw mince is tipped through it over the open shaft in which vessels wait on the deck. Under DEC-8 unwashed produce also comes down it onto the belt or into the drum; in B2 a cucumber goes from the chute onto the belt and is sliced unwashed (FSF-042) | §3.1, §5 B2, §6.1 row 12, §6.4 | major | partly (washed-produce route through the drum only; separate raw chute) |
| K3-4 | **Tools parked above the drum.** Arm heads park on pegs on the rear wall along the arm's arc "above the drum bay, where the bay wash reaches them" — washed in the drum after use, then hung wet over an open drum; the bay wash is daily | §2.3, §6.1 row 5 | major | yes (park outside the food column, drip tray) |
| K3-5 | **19 dynamic seals**, the most of any concept: four gate rods through the bridge ceiling above the belt edges, the tool arm's concentric seal and quill collar above the drum mouth, tilt and gutter shafts, five rear-wall seals of the belt, two lid arms, dock, chute swivel, egg opener | §2.1–2.3, §7 | major | partly |
| K3-6 | **One drum for everything wet**: washing soil-bearing produce, rasp peeling, boiling, raw mince mass, mash; separated by a 90 s cold rinse within a component chain and a full wash after raw use. Allergen carry-over (mustard, egg) after the 90 s rinse is untested (explorer risk R5); DEC-8 adds produce-wash jobs to a drum that is 80 % busy in B3 | §5.13, §6.2, §6.4 | major | partly |
| K3-7 | Numbers: ~64 L, ~5.1 kWh (C-2); daily wash-down 12 L for 11.5 m² (C-3). In place dry after 35 min: PERF-005 met | §6.6 | major (RES-005) | partly |
| K3-8 | Hob plates are **loose glass-ceramic discs** that the shuttle sends to the ware washer: brittle material handled by a gripper and racked in a washer (HYG-018, FSF-070) | §6.1 row 17 | minor | yes (fixed plates, scraper tool) |

Separation: temporal only — one belt, one drum, one chute, sequenced "RTE first, raw last", washed in between.
The drum as such is a credible self-cleaning vessel (smooth spun cup, own coil, closed back, lance): it would be
worth keeping as a module.

### K4 — Shuttle mat (membrane cell)

| # | Finding | Where [D] | Severity | Fixable |
|---|---|---|---|---|
| K4-1 | **About 10 m² of flexible food surface, stored wound and wet.** Silicone on aramid or glass fabric, UHMW-PE film, PTFE-coated glass mesh, rasp foil; 6–8 m² pass per meal. The explorer: "a wound roll cannot dry"; one 3-minute airing at ~40 °C per meal, then rewound. Soil traps: 45° flap-lip roots (reached only when a plough lifts them), hem pockets, every mesh crossing, rasp burr undersides, the fabric edge if the encapsulation cracks under 50 000–150 000 flex cycles. The cassette bay under the gate collects gate drips. Between meals (up to 24 h) a wound, damp elastomer roll is the textbook mould and biofilm site (HYG-024, HYG-051) | §2.1, §6.2 drying, §6.5 #1–3, §6.7, risk R2 | major (**fatal if R2 fails**; the paper-web fallback is a consumable) | partly (dry each mat full length in warm air before winding; drop mesh P) |
| K4-2 | **The raw-meat disinfection of cutting mat K covers 5 % of the mat.** K cannot take steam; "after raw meat it is disinfected by stopping it three times for 60 s under the 85 °C rinse": the rinse stage is 40 mm long, so 3 × 40 mm of 2.4 m are treated. Full length at 60 s per 40 mm would take an hour. UHMW-PE at 80–85 °C is at its softening limit (explorer: "UHMW-PE softens") | §5 B1, §6.2 | major | yes (raw meat never cut on K: sixth cassette as a red K, or paper) |
| K4-3 | **Gate water under-counted about ten-fold.** Pre-rinse 0.3 L and rinse 0.5 L per 100 s pass through two fan nozzles per face imply 0.05–0.08 L/min per nozzle — a mist, not a rinse. The smallest practical flat-fan tips give 0.2–0.4 L/min at 3 bar: 1.3–2.7 L each per pass, 13–27 L per meal instead of 4 L, and 0.55–1.15 kWh of 85 °C rinse instead of 0.2 | §6.2 table, §6.4 | major | yes (budget), partly (the water) |
| K4-4 | **Single fixed instances shared by class R and RTE**: blade beam, table with a bonded soft-anvil strip under the blade line ("in the wettest place"), cheeks, rollers E and L on wet iglidur bushes, bar B with its key slot that clamps the soiled mat hem; a wet film trapped under the mat on the table during work. Separation by an 85 °C wash in between | §2.1, §6.3, §6.5 #2, #5, #9, #10, §6.6 | major | partly |
| K4-5 | **Wear makes the cutting surface uncleanable.** About 60 000 blade landings a year into UHMW-PE over silicone; the scored band holds soil (explorer risk R3; life 6–12 months). The disc-knife roller is "a stack of crevices" washed assembled; mesh P is expected to fail HYG-020 first; produce washing on P in the loop (class R under DEC-8) puts soil and grit into the mesh | §2.4, §4.2, §6.5 #3, #7, §6.7 | major | partly (steel anvil band; one-piece roller; wash produce in the basket, delete P) |
| K4-6 | **The oven hangs above P3 and P4**; its underside, lift door and "fume gap, condensate lip" are above open cooking vessels; arm forearms and the bar-B joint seal (40 mm from the mat edge, "closest dynamic seal to Zone F") sweep over them | §1 front view, §2.5, §6.3, §7 | major | partly (oven beside, not above) |
| K4-7 | Numbers: 62–76 L, 4.7–5.3 kWh recomputed (C-2); Zone S 8.3 m² with 6 L a day (C-3). Cell clean 12–15 min after use: PERF-005 met | §6.4 | major (RES-005) | partly |
| K4-8 | Human replaces five cassettes a year and K a second time (€570 per set a year); a mat that fails verification twice is quarantined until the human exchanges it | §6.7, §9 | minor | — |

Separation: instance for sticky raw work (mat S, steamed at every retraction), sequence for cutting on K, and
shared blade, table and cheeks. The mat is washed within 1–10 min of soiling, which is excellent; what it is
stored as between meals is not.
