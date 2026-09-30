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

| Concept | Score (1–10) | Fatal | Major | Verdict in one line |
|---|---|---|---|---|
| K1 ceiling turret | **3** | 1 | 10 | 7.3 m of uncleanable-until-proven gap over the food, a rod bore that carries both drinking water and cooking water, and 2.5 × the water budget |
| K2 vessel stack | **5** | 0 | 8 | Excellent bare-metal ware on a wash lathe, but the "flash" is dry heat, a drive sits above the press pot and 12 m² of splash zone get 10 L a day |
| K3 drum and belt | **3.5** | 0 | 7 | The drum is a credible self-cleaning vessel; the TPU belt, the shared chute and 19 dynamic seals are not |
| K4 shuttle mat | **3** | 0 | 7 | 10 m² of textile-cored elastomer food surface stored wound and wet; the raw-meat disinfection of the cutting mat covers 5 % of its length |
| K5 ram and die | **5** | 0 | 8 | Best in-place cleaned food part (the pigged tube with a bore camera), spoiled by a shared die carousel, twin-lip pistons and a chip box in the wash loop |
| K6 loose ware, wash wells | **7** | 0 | 8 | No fixed food surface, commercial wash hardware, per-item verification; a large open splash zone washed only at night and a gripper that carries soil from tang to tang — all fixable |
| K7 state change | **5.5** | 0 | 4 | Loose ware and a steam-finished slot washer; the slot sprays raw-meat liquor beside the clean tray rack, and the sink is raw bench, produce wash and waste port at once |
| K8 sealed tub | **6** | 0 | 6 | Zero dynamic seals and full containment; but clean ware lives in the soiled tub, the rinse does not disinfect raw-meat ware, and the rinse water is under-counted by 12 L |

Major counts include the RES-005 miss that every concept shares; weight, not count, sets the score (section 5).

**The one fatal finding** is K1-1: the six annular seam gaps above the whole work deck, flushed only from one
side, invisible to every sensor, and — by the explorer's own statement — without a fallback inside the concept.
Two further findings become fatal if their concept's own kill test fails: K3-1 (belt) and K4-1 (mats).

**Findings that apply to all eight** (section 2) are as important as any single concept's defect:

1. **No concept meets RES-005 or RES-001** (re-based by DEC-18 to ≤ 35 L and ≤ 3.0 kWh for 2 persons, ≤ 55 L
   and ≤ 4.5 kWh for 6) once the machine-washed dishes (DEC-6), produce washing (DEC-8) and cooking water are
   booked and the arithmetic is redone: recomputed **54–118 L** and **4.0–8.9 kWh** for the 4-person benchmark
   meal, hardly less for 2 persons because cleaning does not scale with persons (C-2).
2. **Thermal-disinfection claims (HYG-021, A0 ≥ 60) have no margin in six concepts, and in two (K2, K3) the
   induction "flash" is dry heat, to which A0 does not apply** (C-1).
3. **DEC-8 turns every produce intake into a class R path** (unwashed soil-bearing produce is class R by
   definition 1.4) and brings sand into wash sumps whose pumps and 1–1.5 mm nozzles were not designed for it
   (C-4). DEC-6 makes the hatch a dirty return and a clean serving point at once (C-5).
4. **Splash zones of 5–12 m² are washed with 0.5–1 L of fresh water per m² once a day**, with no nozzle plan and
   no drying step after the meals in between; HYG-045 (not soiled and wet for more than 4 h) is not shown by any
   open-bay concept (C-3).
5. **Nobody cleans the oven cavity, the hood or the grease path** (C-6), and **no concept can verify allergen
   removal** online (C-7).

**Recommendation for round 2** (section 8): build on K6's rule "everything that touches food is ware, washed in a
fast tank washer, hung by one grip feature, verified per item", add K5's pigged tube as the press cassette, K8's
enclosure of the frying zone, K7's steam finish for flat ware, K3's drum as a closed produce-wash vessel, and
K2's wash lathe for round ware only if the flash is redone as moist heat. Drop K1 and K4 as whole-cell concepts;
keep K3's belt only if its riboflavin/swab test passes. Twelve hygiene rules for every round-2 concept are in
section 8.1.

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

Common additions to every concept's own cleaning figure [E]: **dishes 10 L / 0.9 kWh** (DEC-6; RES-005 and RES-001 now
include the meal's dishes), **cooking water 4 L**, **produce washing 5 L** (DEC-8; GP-W1 in
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

**Against the limits.** The concepts' benchmarks are for 4 persons; while this critique was written the
requirements were re-based by DEC-18: RES-005 is now ≤ 35 L per reference meal of **2 persons** and ≤ 55 L per
sizing meal of 6; RES-001 ≤ 3.0 kWh (2 persons) and ≤ 4.5 kWh (6 persons), both including the washing of the
meal's dishes. Cleaning hardly scales with persons (the requirement says so itself): a 2-person meal soils the same
stations and nearly the same ware, only fewer dishes. So the 4-person figures above minus about 5 L of dishes and
produce are a fair estimate for 2 persons: **every concept misses the 35 L of the 2-person meal by 15–80 L**; for
the 6-person sizing meal only K6 (~54 L, ~4.5 kWh) and K2 (~57 L, ~4.0 kWh) come near the 55 L / 4.5 kWh, and
K2 only because its splash-zone wash is under-budgeted. DEC-19 (maximum 4 persons per meal, recorded as this
critique was finished) makes the 4-person benchmark meal the sizing meal; if the sizing limits are re-based below
55 L / 4.5 kWh, no concept is inside them. Round 2 needs water and heat recovery as a design
feature (final rinse kept as the next pre-rinse, drain heat recovery, washing only full loads, fewer soiled items
per meal), and the 2-person case must be walked through by every concept.

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
* RES-005 and RES-001 now include the dishes (DEC-18 wording). A household machine needs about 10 L per load;
  in-cell washers with 85 °C rinses and small loads use more water and energy per dish.

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
| K1-8 | **Water, energy, time.** Recomputed ~118 L, ~8.9 kWh for the 4-person meal (C-2): about 2 × even the 6-person limits of RES-005 (55 L) and RES-001 (4.5 kWh). Cell free 43–50 min after serving (relays 10–17 min + wash-down 33 min): PERF-005 (30 min) missed. Ware in three loads of 55–75 min in series: the third load starts about 2 h after the food left it (HYG-030: ≤ 60 min, M); everything clean after 3 h (90 min required) | §6.2, §6.3, §6.4 | major | partly (fast washer; half the ware) |
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

### K5 — Ram-and-die column with piston vessels

| # | Finding | Where [D] | Severity | Fixable |
|---|---|---|---|---|
| K5-1 | **The die carousel is a shared fixed Zone F plate.** Ø 400 × 12 mm plate (0.25 m²) with six windows whose 4 mm ledges are exposed only while lift pegs raise the inserts under the wash hood; the **shear-gate move deliberately smears mince and batter film** across it (documented as a smear path); dies are shared between class R and RTE by sequence, and after any class R shear the whole carousel must run the hood programme before the next RTE tube. The hood uses "an open labyrinth instead of lip seals". Explorer risk 7 | §2.1 carousel, §6.2, §6.4, risk 7 | major | partly (drop the shear gate; red die set for mince; closed hood) |
| K5-2 | **Twin-lip UHMW-PE pistons**: the 4 mm groove between the lips is "a known soil trap" (explorer); the snapped-on UHMW lip ring of every tube is a crevice, pushed off only weekly; all pistons and dashers are washed in a shared parts basket with the tubes' liquor; UHMW stays damp longest and is at its softening limit in an 85 °C rinse | §2.1 pistons, §6.2 rows 2–4, §6.6 #1–2 | major | yes (single-lip moulded piston or one-piece steel follower with a clearance gap flushed by the bore jet) |
| K5-3 | **Tube disinfection is marginal**: 1 L at 85 °C for 45 s on 1.6 kg of steel coming from the 55 °C wash; heat balance puts the wall near 80 °C, A0 ≈ 30–45 (C-1). The tube is the class R vessel for mince | §6.2 row 1 | major | yes (2 L or 90 s; logger) |
| K5-4 | **The chip box is the strainer of every drain** under bay A: peel slurry, raw trimmings, ricer skins, egg shells and wash solids sit wet, warmed by the sump, **in the recirculation path of the wash liquor** for the whole meal (B1: 140 min), then the transport system carries the dripping perforated box out. Under DEC-8, sand passes its 2 mm holes into the sump, the 30 L/min pump and the hood nozzles | §1.2, §6.1, §6.5 | major | partly (chip box upstream of a separate drain, emptied after each peeling job; settling trap before the pump) |
| K5-5 | **Frying book next to its own seals**: hinge trough with two rotary shaft seals 40 mm from frying fat ("the weakest seals of the concept"); leaf frames beside a 240 °C pan collect fat "that carbonises … not removed by a 55 °C spray" (explorer); silicone rim gaskets on the GN vessels at 230 °C take up fat and odour (HYG-025) | §2.3, §2.5 #7–8, §6.2 rows 17, 19, §6.6 #8–9 | major | partly |
| K5-6 | **Things above open food**: eight stem tools (tongs, turner, knife, ladle, probe…) parked on cone pegs on the rear wall of bay B "above the rear positions' splash line", including the red tongs after raw work; ram rod and mixer crank rod collars above open tubes ("HYG-004 is met only through the drip edge"); the extraction hood with a **condensing coil and drip tray** above the hob | §1.2, §2.4, §2.5, §6.6 #7 | major | yes (pegs beside, not above; hood condensate path proven) |
| K5-7 | **The shuttle slot** (1300 × 70 mm, band cover and labyrinth, facing down above food heights): "a surface that is cleaned by nobody" (explorer) | §2.5 #11, §6.2 row 23 | major | partly (a wash nozzle row and a gutter under the slot) |
| K5-8 | Hard-to-clean inserts: iris die (six sprung blades on a flexure; "weakest part against HYG-013"), duckbill valve (silicone slit), sickle sheath (a blind, wet, form-fitting holster that no camera sees), rolling-mat pull-bar hem | §2.1, §6.2, §6.6 #5–6, #13 | minor | yes (delete iris and duckbill; open sheath) |
| K5-9 | Dock chutes shared by raw mince, eggs and RTE doses; the tube chute is rinsed only after the last dry dose of the meal ("flour + water = paste"), so a mince residue can wait for the rest of the meal | §3, §6.2 row 11 | minor | yes (red chute insert) |
| K5-10 | Numbers: ~69 L, ~4.8 kWh (C-2). Column clean and dry 15 min after last use; cell wash 25 min after the meal; PERF-005 met | §6.3 | major (RES-005) | partly |

Separation: red and green tubes, pistons, sickle and tongs (dedicated); dies, carousel plate, drop position,
chutes and parts basket shared and separated in time. The tube itself — a smooth bore, pigged by its own piston,
jetted from inside and seen whole by one camera — is the best-cleaned in-place food part of all eight concepts.

### K6 — Loose ware and fast washer

| # | Finding | Where [D] | Severity | Fixable |
|---|---|---|---|---|
| K6-1 | **Largest open splash zone (10.7 m²), washed once a day at night** with the day's tank liquor (which has washed every class R load) sprayed over the whole bay, then 10 L of fresh water at 65 °C. The explorer: "a rinse of a large, cluttered splash zone and its coverage is not proven". After lunch the bay stays soiled and damp for ~10 h (HYG-045, C-3) | §6.3 Zone S table and wash-down, risk 12 | major | yes (per-meal dry-out; per-meal hob-zone wash with fresh water; nozzle plan) |
| K6-2 | **The manipulator is above food**: three sealing bands (X slot, Z mast slot, Y slot in the arm with a drip lip "above food"), wrist tilt and spin lip seals with food-grade grease behind them, chuck jaw rod lips. HYG-004 is met only by the closed boxes; band edges collect aerosol and meet grease | §2.1, §2.4 #1–6 | major | partly (sleeve over the wrist as the explorer suggests; drip tray under the arm) |
| K6-3 | **The gripper carries soil from item to item.** Tray and pot tangs have no drip collar ("a real weakening of the drip-collar rule"); the chuck grips the tang of every soiled tray and then the next clean one; the jet gate (85 °C, 4 s — a rinse, A0 negligible) runs only after class R contact; chuck pin sockets are 8 mm holes. R6 §6.4 names exactly this path | §2.2, §6.4, §6.6 #1–2, risk 4 | major | partly (jet gate after every soiled grip; collar on tray tangs; second chuck for clean side) |
| K6-4 | **"Every load is disinfected" is not shown**: 20 s of 85 °C rinse on ware coming from a 60 °C tank; realistic surface A0 10–40 (C-1) | §6.1 | major | yes (rinse hold; loggers on the coldest item) |
| K6-5 | **No pass-through: the wells are dirty entry, wet parking and clean store at once.** Soiled items are hung into the open well and wet-parked (cold mist every 2 min) until the well is full; "a clean well is a store until the other is full"; the lid underside drips rinse condensate onto clean ware when it opens. R6 E17/rule 7 asks for a one-way clean/dirty flow | §1.1 point 4, §2.5 parking table, §6.1, §6.6 #12 | major | partly (clean items leave to the store at once; lid drip lip) |
| K6-6 | **The sink bench does four jobs**: produce wash (class R under DEC-8), waste port for peel and trimmings, drain of the wells' pre-spray, and a work bench (GN 2/3 frame over the basin) for the next job | §2.3 B1, §6.5, §11.1 #10 | major | partly (a separate waste chute; the sink frame never used for RTE) |
| K6-7 | **Frying fat above 30 mL has no path**: poured onto the peelings, "it would run through the strainer into the drain" (WSH-016) | §6.5, §12.1 #5 | major | yes (fat cup as ware) |
| K6-8 | Crevice-bearing ware: egg cracker on open hook hinges ("dried egg white in a hook is the expected failure"), cut-off slide in open U-rails, whisk wire roots (must be a welded hub), rolled flanges of bought GN trays ("a crevice 354 + 325 mm long on every tray" unless flat-flange trays are specified), perforated items | §6.6 #3–11 | minor | yes |
| K6-9 | Human wear parts: two silicone spatulas, squeegee, apron, mat, HDPE boards (scored), pistons, peeler blade, knives; blades not resharpened (PRP-034 only by exchange). Noise of the wells 52–56 dB(A) against 48 | §7.1, §12.1 #12 | minor | yes |
| K6-10 | Numbers: ~54 L (52–61), ~4.5 kWh (C-2) — the lowest water of the eight and still over RES-005. Everything clean, dry and stored 15–20 min after hand-over: the best turnaround. Under DEC-6 the wells can also wash dishes (five plates a load, on a tanged carrier) | §6.1, §6.2 | major (RES-005) | partly |

Separation: red and green knife, tongs, board, GN 1/3 trays and turner; everything else is washed and (claimed)
disinfected in a 3.5-min well cycle before reuse; the gripper is the shared path. No fixed food-contact surface.

### K7 — State change and rigid handling

| # | Finding | Where [D] | Severity | Fixable |
|---|---|---|---|---|
| K7-1 | **The slot washer sprays raw-meat liquor next to the clean tray rack.** An open-top slot 50 × 280 mm flush in the deck, 12 nozzles recirculating 40 L/min, a steam pulse and an **air knife on the upstroke** that blows the water off the rising part at the slot mouth; directly beside it the rack well stores 16 clean trays vertically (layout "S slot │ R rack"). Red trays go into the slot "straight after the red phase". Pre-rinse with tank overflow, not fresh water; the 6 L tank is dumped once a day. HYG-005, FSF-041 | §1.2 top view, §2.4, §7.2, §7.5 | major | partly (lid over the slot while spraying, air knife inside, rack behind a shutter, pre-rinse fresh) |
| K7-2 | **The sink well is the only fixed Zone F surface and does everything wet**: produce wash, rasp peeling (slurry), skin slipping, salad spin, waste catch, press table, and — with grate T2 — the red bench for raw meat. Rubber-finger basket with fingers pushed in ("a crevice at every finger"); hub umbrella; steamed at 85 °C for 1 min after the red phase. Under DEC-8 the well is busier and gritty | §2.4, §7.3 sink row, §7.6, §7.7 #2, #8 | major | partly (separate red bench; one-piece finger sheet) |
| K7-3 | **Aluminium in the splash zone**: five aluminium evaporator plates and five loose aluminium slabs (21.5 kg) in the cold cabinet, touched by tray undersides and lid tops, rinsed daily with 40 °C water only (R6 A7: no unanodised aluminium in Zone F/S; alkaline detergent attacks it, so it is never washed with detergent). Lid sheets float on raw meat and are then pressed by slabs that next press other trays; frost melt and flour dust in a cabinet whose defrost day passes through 0–10 °C, where *Listeria* grows | §2.4 CC, §3.4, §7.3 CC row, §7.7 #11 | major | yes (stainless-clad slabs; weekly detergent wash of the cabinet) |
| K7-4 | **The steam finish is under-powered**: 8–10 g of steam in 6 s needs ~1.5 g/s; a 2 kW generator gives ~0.7 g/s; the slot is open at the top (C-1) | §7.2 | minor | yes (accumulator; closed slot) |
| K7-5 | **One gantry, one air space, 120 moves per meal** (80 food moves + 40 washing moves); separation of red trays from open RTE food is procedural ("routed along the rear lane … open vessels on its way are lidded first") | §7.5, §8 | minor | — |
| K7-6 | The most loose parts of all concepts (~105 preparation items + 27 cookware): pin roots of the pin board, knock-out pin plates, filling-rod half-shell mould, bow knife blade clamps, rotor lids with PEEK bushes, grid and harp dies; tab welds and Ø 8 holes on every piece | §2.5, §7.7 | minor | — |
| K7-7 | Numbers: 57–64 L, 5.0–5.2 kWh (C-2); flat ware clean 25–30 min after use, bulky ware in the chamber 55–75 min: PERF-005 met | §7.4 | major (RES-005) | partly |

Separation: red tongs, bow knife, pin board and cold trays (dedicated); the sink and T1 are shared. A real
hygiene gain that no other concept has: **tempered meat drips and smears far less**, and its purge stays frozen on
the tray (§7.5).

### K8 — Sealed tub with magnetic pucks

| # | Finding | Where [D] | Severity | Fixable |
|---|---|---|---|---|
| K8-1 | **Clean ware is stored in the soiled workspace.** 24 utensils on the top strip and three pucks live inside the tub, in its steam and fat aerosol, and in the air in which raw meat is open; the top strip is above the front edge of the hob rows. After a *short wash* unused utensils are not washed at all (explorer open issue 10). HYG-005 by construction; separation temporal only; "splashes from raw meat on the drive wall … are not removed by the rinse" | §1 front view, §6.3, §6.4 R/RTE paragraph, §12 open issue 10, request A-6 | major | partly (shuttered utensil garage in the door top; red-to-green rinse of every utensil used for RTE after raw work) |
| K8-2 | **Rinse water under-counted**: the gate delivers 12 L/min, so 6 s is 1.2 L per vessel, not 0.6 L; the pucks' 2 × 20 s rinse (8 L) is not in the 26 L. Full wash ≈ 38 L and ≈ 2.8 kWh; per meal 60–65 L with dishes, cooking and produce (C-2) | §6.1, §6.2 full wash steps 4–5, §7 | major | yes (the budget), partly (the water) |
| K8-3 | **The full wash does not disinfect class R ware**: 6 s at 85–90 °C gives A0 ≤ 38 even for a surface already at 88 °C (C-1). Only the red-to-green programme (25 s at 88 °C) approaches A0 60, and it runs only when RTE work follows raw work | §6.2 | major | yes (25–60 s gate time for every red item) |
| K8-4 | **Soiled ware waits for the end of the meal.** Apart from 5 s cold tool rinses and the red-to-green rinse, nothing is washed until the full wash: in B1 the braiser, boards, mat and cradle soiled at t = 0–33 min wait until t ≥ 140 min. HYG-030 (washing starts ≤ 60 min after use, M) is missed in every meal longer than about an hour; the tub cannot run a wash while food is open in it without spraying liquor into that food | §5 B1, §6.2, §6.3 | major | partly (gate washes of idle ware while all vessels are lidded) |
| K8-5 | **A 3.6 m EPDM door gasket** around the drive wall — the classic mould and biofilm site of every dishwasher — here in a food-preparation chamber, on its wettest wall, with its lower sill just above the sump; plus the pressed expansion bead round the skin and the polymer skid tracks on the wall | §2.4, §6.4 drive-wall row | major | partly (hygienic flush gasket profile as LRU; hot drying cycle through the gasket groove) |
| K8-6 | **The pucks are Zone F and skid across the soiled wall**: PEEK skids ride through raw-meat splashes on the drive wall and then carry RTE tools; rotor–spider thrust washer and bush (open 5 mm only when hung off); bayonet lugs; the press cassette's Rd thread and PEEK nut (explorer risk 4: residue in the thread; PEEK wear debris near food) | §2.1, §2.5, §6.4 pucks and cassettes rows | major | partly |
| K8-7 | Glass-ceramic plate as the tub floor with a silicone joint (a fixed food-contact station in the explorer's own table); burnt-on sugar or milk needs the intensive soak; a falling 1.1 kg puck carries 4.3 J onto it (explorer risk 8) | §2.1, §6.4 | minor | partly |
| K8-8 | Dosing port in the ceiling above column A and the egg module and piston box outside the tub are "not washed by it" (open issue 9); flour at the port needs a dry tub and the exhaust off | §3, §12 open issue 9 | minor | yes |

Separation: two boards, two press tubes, two tongs; otherwise **temporal** inside one chamber, with a disinfecting
rinse of the used red items. The concept's strength is real: no dynamic seal, no fixed mechanism, a closed
all-steel chamber in which every surface is washed after every cooked meal; frying aerosol never reaches the
kitchen or any other module.

---

## 4. Comparison

Areas per 4-person reference meal. "Fixed F" = food-contact surface cleaned in place. Water and energy: section
C-2 (recomputed, including dishes, cooking water and produce washing). "Next meal" = earliest start of the next
meal; "all clean" = everything clean, dry and stored.

| | Fixed F cleaned in place | Ware F soiled per meal | Zone S | Loose parts | Dynamic seals / penetrations above open food | Water, energy | Next meal / all clean | R ↔ RTE separation | Verification |
|---|---|---|---|---|---|---|---|---|---|
| K1 | 0.04 m² rod tips + 0.65 m² seam gap over food | ~3.5 m², ~45 items | 5.6 m² | ~110 | 3 core seals, 4 collars, 6 seams (7.3 m) — all above food | ~118 L, ~8.9 kWh | 43–50 min / ~3 h | dedicated red set + sequence; rods, bench, gates, deck shared | lance path, flow per seam, conductivity, ceiling camera; seams and bores unseen |
| K2 | quill nose (~0.01 m²) | ~3 m², ~24 pieces | 12 m² | 76 | 8 moving seals; quill bellows and lip seal above the K/H pot | ~57 L, ~4.0 kWh | 10 min / ~55 min | instance + time; single-instance discs and jaws shared | lathe camera per part, pyrometer, turbidity; shaft and tiers unseen |
| K3 | 1.5 m² (drum, belt, gates, chute, gutter) | ~1 m², 12–16 items | 11.5 m² | 31 + 15 heads | 19; 4 gate rods above the belt, arm quill above the drum | ~64 L, ~5.1 kWh | ~15 min / 55–75 min | temporal: one belt, one drum, one chute | drum camera with stripe light; belt inner face unseen |
| K4 | 0.69 m² + 6–8 m² of mats | 1.5–2.5 m² | 8.3 m² | 36 + 5 mats | 22 rotary passages; spindle nose over P1; oven above P3/P4 | 62–76 L, 4.7–5.3 kWh | 12–15 min / 55–75 min | mat S dedicated; K by sequence; blade, table, cheeks shared | camera on the drawn-out mat (top face only) |
| K5 | ~0.9 m² column parts (tubes, carousel, dies) | ~1.7 m² | 5.0 m² | ~96 | ~10; ram and crank rod collars above tubes; shuttle slot | ~69 L, ~4.8 kWh | 15 min / 55–75 min | red tubes, pistons, sickle, tongs; dies and carousel shared | bore camera (whole bore), back-light of dies; pistons by coupon only |
| K6 | 0 | 1.3–1.6 m², 40–55 items | 10.7 m² | 93 | 3 sealing bands, 2 wrist seals, chuck lips — above food | ~54 L, ~4.5 kWh | ~15 min / 15–20 min | red/green for overlapping items; everything else washed per use; chuck shared | every item turned before a camera (white, oblique, UV-A) + IR ≥ 65 °C |
| K7 | 0.45 m² (sink) | 2–3 m², 25–40 items | 9.3 m² | ~132 | X cover strip, quill wiper, wrist seal (rear lane); spin head closed | 57–64 L, 5.0–5.2 kWh | 25–30 min / 55–75 min | red tongs, knife, board, trays; sink and T1 shared | process record + grazing-light camera for flat ware |
| K8 | tub 3.25 m² + hob glass 0.31 m² (all S/F) | 1–1.5 m² + 2.8 m² resident parts, all washed | (whole tub) | ~70 resident | **0** | 60–65 L, ~5.3 kWh | 25 min (cannot cook while washing) / 35 min | temporal in one chamber; 2 boards, 2 tubes, 2 tongs | every item presented to a camera (white, UV-A); 8 L loop turbidity |

---

## 5. Scores

Scale: 10 = would pass a hygienic-design audit as drawn; 5 = passes only after several major fixes that keep the
concept; 1 = cannot pass without abandoning the concept.

| Concept | Score | Justification |
|---|---|---|
| K1 | **3** | The only fatal finding (seam gaps over the deck, no fallback), a cross-connected fluid bore at every rod tip, the most loose parts after K7 and the worst water, energy and turnaround (3 h). Its ware principle ("food only on ware") is sound; its cell is not |
| K2 | **5** | Bare-metal, seal-free, one-rim ware on a lathe is the best ware-cleaning idea of the eight; against it: disinfection claimed from a dry flash, a quill over the press pot, one shaft for clean, dirty and raw, and 12 m² of splash zone with a 10 L budget. All fixable, none small |
| K3 | **3.5** | The drum is a credible self-cleaning vessel. The belt is a fixed flexible food surface that R6 advises against, with an unseen inner face and wash box; plus a shared chute, tools parked over the drum and 19 dynamic seals. Separation is temporal for everything |
| K4 | **3** | Excellent wash timing (mats washed within minutes) cannot make up for 10 m² of textile-cored elastomer stored wound and wet, a cutting mat that scores, a raw-meat disinfection that covers 5 % of it, a ten-fold water under-count and the oven hanging over the pots |
| K5 | **5** | The pigged, jetted, camera-checked tube is the best in-place food part of all; the shared carousel with its smear path, twin-lip pistons, the chip box in the wash loop and tools parked over the pots pull it back to the middle |
| K6 | **7** | No fixed food surface, commercial wash hardware, per-item camera verification, 15–20 min to fully clean, the least water. Deductions: a 10.7 m² open splash zone washed once at night, a gripper that carries soil from tang to tang, grease-lubricated seals over food, and a disinfection claim without margin |
| K7 | **5.5** | Mostly loose steel ware, one small fixed food surface, the most credible disinfection step (steam); rigid, tempered meat drips less. Against: the open slot washer sprays raw-meat liquor beside the clean rack, the sink is raw bench and produce wash at once, aluminium in the cold cabinet, and the most loose parts and moves |
| K8 | **6** | No dynamic seal, no fixed mechanism, full containment of splashes and aerosol, whole chamber washed after every cooked meal. Against: clean ware stored in the soiled chamber, temporal separation only, a final rinse that does not disinfect raw-meat ware, soiled ware waiting up to two hours, a dishwasher door gasket in a kitchen, and 12 L of uncounted rinse |

---

## 6. Ranking of the cleaning sub-mechanisms

Credibility = how likely the mechanism meets HYG-019/-020/-021/-024 reliably for the parts it is meant for,
without a human.

| Rank | Mechanism (concept) | Credibility | Why | What must be proven |
|---|---|---|---|---|
| 1 | **Tang-hung wash wells** (K6; SM-201) | High | Commercial undercounter-washer hardware; fixed hanging pose per item type; steel self-dries from an 85 °C rinse; one well always free; per-item camera on the way out | Surface A0 with loggers (it is short, C-1); shadows when a slot is mis-loaded; drying of silicone and HDPE items; noise |
| 2 | **Pigging plus in-bore rotary jet** (K5 tube; SM-206) | High for the tube | A smooth cylinder emptied by its own piston, jetted from inside, seen whole by one camera | The piston and its lips are not covered by this claim; the rinse heat (C-1) |
| 3 | **Drip-collar stems** (K6, K5, K7; SM-202) | High, as a design rule | Keeps the gripper out of the food; cheap; verifiable | It is a separation rule, not a cleaner; K6 drops it for trays and pots (K6-3) |
| 4 | **Wash lathe** (K2; SM-192) **+ induction flash-dry** (SM-212) | Lathe high for bodies of revolution; flash medium as a dryer, **low as a disinfection** | Every point of a rotating part passes every jet; the camera sees the whole part in one turn | GN corners and blade roots on the lathe; the flash must act on a *wet* surface to count as A0 (C-1); evenness on the thick rim spool |
| 5 | **Self-washing drum** (K3; SM-193) | Medium–high | Smooth spun cup, closed back, own heater, lance, pour to a gutter; camera on a mirror finish | Helix-fin root and lip welds; dry-flash claim; allergen carry-over after a 90 s rinse |
| 6 | **Tub wash** (K8; SM-200 as re-designed) | Medium | A closed all-steel chamber washed like a dishwasher, with the pucks presenting each item to a jet gate on a programmed path | Coverage of the parked utensil strip, gasket and puck bush; gate time for disinfection; the water recount |
| 7 | **Jet gate** (K1 G1/G2, K8, K6 chuck; SM-198) | High as a cold rinse between foods of the same class; **low as a wash or disinfection** | A plane of fans that the tool is turned through; simple | K1 uses it also for soil-bearing produce and for spin-drying (aerosol); K8 uses it as its main wash with 6 s per vessel |
| 8 | **Form-fitting wash holster** (K5 sickle sheath; SM-190) | Medium–low | Pipe flow at 1.5 m/s in a 3 mm gap cleans a flat blade | The sheath itself is a blind, permanently wet niche that no camera sees; drying inside it; the catalogue already says a holster rinse is not the validated disinfecting cycle |
| 9 | **Mat wash on retraction** (K4; SM-195) | Medium for the two faces, **low for lip roots, hem, mesh, rasp and drying of the wound roll** | Every cm² passes every nozzle row — by construction, for flat faces only | Lip roots and hem with riboflavin and ATP; weight of the mat after the airing run; the real nozzle flows (K4-3) |

Other mechanisms met on the way: the **slot washer with a steam finish** (K7) would rank between 4 and 5 (steam is
the most credible thermal step; the open slot and its aerosol are the problem); the **belt wash on the return run**
(K3; SM-195) between 8 and 9; the **rod car-wash collar** (K1, K3, K5; SM-191) medium as established hygienic-seal
practice, but a wear part above food; the **seam flush** (K1) and the **manipulator-held lance** (K1; SM-188) low.

---

## 7. What the human would eventually clean or replace

HUM-007 allows ≤ 2 part exchanges a year of ≤ 15 min; HUM-012 forbids touching soiled internals except for that.
All numbers [D] unless marked.

| | Wear and hygiene parts the human changes | Likely frequency [E] | Hidden surfaces that will eventually need a service clean |
|---|---|---|---|
| K1 | rod-tip cartridges (core seal), collar cartridges (PEEK scrapers), V-rings (2–3 years), HDPE board discs, silicone mats, blades | yearly | seam gaps and coamings, leak-off troughs, rod bores, extraction duct |
| K2 | coupler-ring and gasket-frame beads (yearly), Z-slot sealing band (yearly), quill bellows (LRU), blades | yearly | K/H labyrinth (endoscope), oven cavity, dock |
| K3 | TPU belt (yearly, sooner if steam hydrolyses it), silicone heads, gate rod collars, blades | yearly | belt wash box, dancer loop, pocket rollers, bridge ceiling |
| K4 | all five mat cassettes (yearly), cutting mat K twice a year, blade | 2 × a year, ~€570 | cassette bay, gallery gutter, soft-anvil bond line |
| K5 | UHMW pistons and lip rings, GN rim gaskets, duckbill, book shaft seals, grids | yearly | shuttle slot, hinge trough, window ledges |
| K6 | two silicone spatulas, squeegee, apron, mat, HDPE boards, pistons, peeler and knife blades | twice a year (the explorer's own list is already at the HUM-007 limit) | sealing-band edges, tool-wall and store rails (30-day clean), well comb rods |
| K7 | rubber-finger sheet (yearly), bow-knife blades, blade clamps, PEEK bushes | yearly | cold-cabinet plates and drain channel, slot-washer tank, sink hub |
| K8 | door gasket (EPDM, 3.6 m), PEEK skids and puck bushes, PE boards (twice a year), silicone lips | yearly | gasket groove, expansion bead, press-cassette thread |

---

## 8. Hygiene rules and recommendations for round 2

### 8.1 Rules (binding proposals for every round-2 concept)

| # | Rule | Reason (finding) |
|---|---|---|
| R-1 | **Everything that touches food is ware** that leaves for a washer, or a smooth closed cavity (tube, drum) cleaned in place by a validated cycle **and seen whole by a camera after every cycle**. No flexible or textile food surface cleaned in place; no fixed cutting surface | K3-1, K4-1, K4-5, K5-1 |
| R-2 | **Nothing above an open vessel**: no gap, seal, sealing band, rod collar, parked tool, oven mouth or condensing coil in the vertical projection of an open food vessel during work. Manipulators approach from the side or park their drives outside that column | K1-1, K2-2, K3-4, K4-6, K5-6, K6-2 |
| R-3 | **Only moist heat counts for A0.** Every disinfection claim is shown with a data logger on the coldest item of the worst load; a rinse hold of ≥ 60 s at ≥ 82 °C (or saturated steam) is the default; an induction or hot-air flash is a drying step | C-1 |
| R-4 | **Water and energy are budgeted from nozzle flow × time**, including machine-washed dishes (DEC-6), produce washing (DEC-8) and cooking water; the re-based RES-005/-001 (DEC-18) are to be met by recovery (final rinse → next pre-rinse, drain heat recovery) | C-2, K4-3, K8-2 |
| R-5 | **Unwashed produce is class R**: the first wash station is a red station with its own basket and drain; no shared tool or surface touches produce before it is washed (FSF-042) | C-4 |
| R-6 | **One-way flow**: soiled ware leaves by a path that clean ware does not use, or at least clean ware is stored behind a closed shutter outside the air space in which class R food is open; dishes returned at the hatch never share it with plated food at the same time | K2-3, K6-5, K7-1, K8-1, C-5 |
| R-7 | **Time limits**: cold rinse within 2 min of emptying a hot vessel, wash start ≤ 60 min (HYG-030); splash zone dried within 60 min after every cooked meal (HYG-045, HYG-053); no soiled wash liquor held in the 25–55 °C band — dump after class R or allergen loads, or keep ≥ 60 °C | C-3, C-8, K1-8, K8-4 |
| R-8 | **Grit and waste**: a settling trap upstream of every recirculation pump; peel slurry flushed within minutes; chip boxes and strainers outside the recirculation loop; waste leaves the cell closed | C-4, K1-2, K5-4 |
| R-9 | **Polymers and elastomers**: one-piece moulded only; no woven mesh, no twin-lip grooves, no pushed-in fingers; every polymer part dried by forced air before storage; nothing stored wound or nested while wet | K4-1, K5-2, K7-2 |
| R-10 | **Separate fluid paths**: no bore, hose or nozzle that carries soiled water or food ever carries potable water or air into food (EN 1717) | K1-4, K2-2 |
| R-11 | **Verification**: per-item camera (white, oblique, UV-A) on the clean side for all ware; a per-meal camera check of every fixed surface; riboflavin and dried worst-case soils (WSH-006) run **before** a concept is selected, not weekly after; for declared household allergens, **dedicated ware** instead of a cleaning claim | C-7 |
| R-12 | **Every seal, gasket, band and wear part** listed with its interval and who changes it; the total must fit HUM-007 | section 7 |

### 8.2 Recommendation

1. **Backbone: K6's rule set** — all food-contact parts are loose ware with one grip feature, washed as they go
   in a fast tank washer with an 85 °C rinse and dried by their own heat, verified per item. It is the only
   concept with no fixed food surface and a turnaround inside PERF-005 (M and S). Fix before round 2: rinse hold
   and loggers (K6-4), collars on tray tangs and a jet gate after every soiled grip (K6-3), a pass-through or at
   least an immediate move of clean ware to a closed store (K6-5), per-meal drying and a hob-zone wash (K6-1),
   a fat path (K6-7), and a sleeve or drip tray under the arm (K6-2).
2. **Borrow**: K5's pigged tube with its bore camera as the press cassette (with a single-lip or steel follower,
   K5-2); K8's containment of frying — a closed, washable hood or sub-chamber over the hob so that fat aerosol does
   not reach a 10 m² bay; K7's steam finish for flat ware (in a closed slot); K2's wash lathe for round ware only if
   the flash is done wet; K3's drum as a closed produce-wash and peel vessel (it also answers DEC-8), without the
   belt; K7's crust-tempering of raw meat where it reduces drip.
3. **Do not carry forward** K1 (seam gaps, bore cross-connection, water) or K4 (wound wet mats) as whole-cell
   concepts. K3's belt returns only if its riboflavin and ATP test (K3 risk R2) passes on edges, inner face and
   pocket rollers after dried soils.
4. **Experiments that decide the hygiene case** (cheapest first):
   * Surface A0 with data loggers on the coldest item in an undercounter washer with a 20 s and a 60 s rinse
     (K6-4, K8-3, K2-1); the same logger on a spun tri-ply pot under an induction coil (flash dry vs. wet).
   * Riboflavin and dried egg, starch and mince soil (2 h) on: a tang-hung load with deliberate mis-loads; a
     GN tray on a lathe; a tube, piston and die set; a belt loop (only if K3 stays).
   * Aerosol mapping: a fluorescent or *E. coli* surrogate on raw meat, then the planned rinse (K1 lance, K6
     jet gate, K7 open slot with air knife, K8 red-to-green rinse); settle plates on the clean store and on open
     RTE vessels.
   * Splash-zone wash-down on a plywood-and-sheet mock-up with the real nozzle plan and a manipulator parked in
     it: riboflavin coverage and fresh water per m².
   * Grit: 1 g of sand per 200 g of field vegetables through the planned produce wash; where the sand ends up
     (strainer, sump, pump, nozzles).
