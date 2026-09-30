# C2 — Critique of the preparation concepts K1…K8: hygiene, cleanability, food safety

Round P4, critic C2. View: hygienic-design auditor and microbiologist. Yardsticks: BRIEF ("the human will not
clean anything"), requirements HYG-001…061, FSF-010…070, WSH-xxx, RES-001/-005, PERF-005, HUM-007/-012, and
the checklist of `research/06-hygiene-cleaning.md` (R6) section 11.

All concept documents are paper estimates. So is this critique: nothing here was tested.

Markers: **[D]** taken from the concept document (section given); **[C]** recomputed by me from the
document's own figures; **[E]** my estimate. Severity: **fatal** = a mandatory hygiene requirement cannot be
met without giving up a defining element of the concept; **major** = a mandatory requirement is missed as
designed; **minor** = weakness with a known remedy. "Fixable" = fixable while the concept stays the same
concept.

Scope limit: I read every cleaning, penetration, ware and failure section of K1…K8 in full, and R6 and the
requirements sections in full. I read the benchmark walk-throughs, operation tables and the two gap
documents only selectively (by search for cleaning-relevant passages). A finding that depends on a
benchmark step is marked where that matters.

---

## 1. Summary

| | Score (1–10) | Fatal | Major | One-line verdict |
|---|---|---|---|---|
| K1 ceiling turret | **3** | 1 | 7 | 7.3 m of gap above open food, and twice the water and energy budget |
| K2 vessel stack | **5** | 0 | 8 | Sound ware principle, but 12 m² of splash zone and a 2-minute wash for cookware |
| K3 drum and belt | **3.5** | 0 | 8 | The two main food surfaces are fixed; the belt contradicts R6 directly |
| K4 shuttle mat | **3** | 1 | 7 | 10 m² of elastomer and textile food surface, stored wound and wet |
| K5 ram and die | **5** | 0 | 7 | Best closed-cavity cleaning (tube), spoiled by a shared chute, carousel and a frying hinge |
| K6 loose ware, wash wells | **7** | 0 | 5 | No fixed food surface, fast validated-type washer, best verification; large open splash zone |
| K7 state change | **5.5** | 0 | 6 | Rigid cold food smears less; most loose parts; aluminium cold cabinet and a shared sink bench |
| K8 sealed tub | **6.5** | 0 | 6 | No dynamic seal, smallest soiled area; but separation is only temporal and the rinse budget does not close |

No concept meets RES-005 (45 L) once the human's dish load (10 L) and cooking water (4 L) are added and the
arithmetic is checked (section 4). Only K8 claims to, and its rinse volumes do not add up (K8-3).

Three findings apply to all eight and are as important as any single concept's defect (section 3):
thermal-disinfection claims with no margin, daily wash-down volumes that are 5 to 10 times below R6, and an
oven that nobody cleans.

---

## 2. Findings per concept

### K1 — Ceiling turret cell

| # | Finding | Where | Severity | Fixable? |
|---|---|---|---|---|
| K1-1 | **Seam gaps above open food.** Six annular gaps, 4 mm wide × 45 mm high, 7.3 m long, 0.65 m² of wall, directly over the work area. They are cleaned by 40 holes of Ø 1.0 mm in a groove on the *fixed* wall aimed at the turning wall; the explorer does not know whether the wall that carries the jets is wetted. The flush uses recirculated (soiled) liquor, then 5 s of fresh water. The ceiling is flat (R6 rule 4 asks ≥ 5°). Verification is indirect: flow per seam, no view into the gap. The explorer states that the concept "has no fallback inside itself" if this fails. | §2.4; §6.7 #1; §10 risk 1 | **fatal** until the riboflavin test passes | no (the gap is the turret) |
| K1-2 | Holes of Ø 1.0 mm fed with recirculated liquor at 0.5 bar. R6 2.7: scale and particles block 1–2 mm holes. A blocked arc leaves a dry sector of gap that no sensor sees (only total flow per seam is logged). 240 such holes. | §2.4 | major | partly (fresh softened water only, per-seam pressure signature) |
| K1-3 | Grease aerosol on a ceiling heated to air + 5 K. Heating stops steam condensing; it does not stop fat droplets depositing, and a warm surface hardens the film. The 0.3 m/s outflow keeps the gap clean only while extraction balance holds. | §2.4; §10 risk 11 | major | partly (hobs out of the cell) |
| K1-4 | **Rod tips are Zone F and get no detergent.** Rod tip with a PTFE lip seal Ø 14, a hex and a Ø 4 bore sits inside the tool socket over food. After class R it gets a 60 s flush at 80 °C in the collar: a hot first rinse on protein (R6 rule 19 forbids it), no detergent, and A0 = 60 only if the Ø 45 × 4 tube reaches 80 °C at once — zero margin. | §2.4; §6.2 step 4 | major | yes (cold, detergent, hot sequence in the collar) |
| K1-5 | The Ø 4 core bore carries water, air and **vacuum** through nine valves. Vacuum draws food liquid upward into a 600 mm bore and its valve block: a dead leg above food. | §2.3, §2.4 | major | yes (no vacuum through the bore, or a trap at the tip that is ware) |
| K1-6 | Four collar scraper rings (PEEK) and lantern chambers above food; soil collects under the lip; wettest part for 30 min. | §6.7 #2; §6.3 | major | partly |
| K1-7 | **Water and energy.** Explorer: 90 L and 5.9 kWh cleaning per full meal. With dishes and cooking water: about 104 L and 8.1 kWh [C], 2.3 × RES-005 and 2 × RES-001. The cell wash is also undercounted: six seams × 5 s × 15 L/min of fresh 80 °C water is 7.5 L, the document books 1 L [C]. | §6.3, §6.4 | major | only with a different washer and half the ware |
| K1-8 | **Time.** Cell free 43–50 min after serving (relay 10–17 min + wash-down 33 min): PERF-005 (30 min) missed. Everything clean after 3 h (90 min required). Third ware load starts about 2 h after use: HYG-030 (≤ 60 min) missed. | §6.4 | major | as K1-7 |
| K1-9 | Mid-meal bench rinse with an 80 °C lance at 5 bar after raw meat, with pots open on the hobs in the same air space (B1: potatoes after Rouladen). Aerosol and splash of class R wash water: FSF-041. | §6.5 | major | partly (lids on, low pressure) |
| K1-10 | Roll head as ware: open stainless worm with a PEEK wheel and bushes — a gear mesh in the food zone. | §6.7 #13; §10 risk 6 | major | yes (closed wrist outside Zone F) |
| K1-11 | Squeegee wipes the ceiling after the wash: a silicone lip dragged over 0.9 m² above food spreads what it did not remove; the squeegee itself is then ware. | §6.3 | minor | yes |
| K1-12 | No scraper for burnt-on spill on the hob glass; five camera windows and the extraction duct (weekly nozzles only) above or beside food. | §6.7 #8, #10, #11 | minor | yes |

Good: no fixed food-contact surface by intent; the seams face food with a plain gap, not a seal; the explorer
names the seam as the killer and gives a 3-day test. Separation: red ware instances plus sequence; spatial
only in that raw work stays on the bench.

**Score 3.** The defining element is the unresolved hygiene risk, and the concept is the most expensive to
clean by a wide margin.

### K2 — Vessel stack and inversion

| # | Finding | Where | Severity | Fixable? |
|---|---|---|---|---|
| K2-1 | **Zone S is 12 m²**, the largest of all (shaft 3.7, hob tiers 5.2, dock 0.8, lathe 1.1, oven 1.3). The daily wash-down is booked at 10 L per day: 0.8 L/m². R6 9.4 gives 25–40 L for 2.4 m². See X-2. | §6.1, §6.4 | major | partly |
| K2-2 | **Wash lathe for cookware: 120 s at 55 °C.** Pots and pans with fond, burnt milk or dried starch (WSH-006) get two minutes of enzyme liquor; enzymes need minutes (R6 2.5: 12–18 min). No soak step exists; the escalation is "one longer cycle, then the central washer". | §6.2 | major | yes (soak on the hob, R6 section 3) |
| K2-3 | **Verification comes after the flash.** Step 4 heats the part to 105 °C, step 5 inspects. Any residue the 120 s wash left is baked on before anyone looks, and the next wash is harder. | §6.2 | major | yes (inspect, then flash) |
| K2-4 | Flash evenness. The rim spool — the sealing land where food crosses at every inversion — is monolithic stainless and heats by conduction only (explorer: confidence M). Austenitic discs, lids, ricer and platen are listed for the flash; an induction ring does not heat them well. | §6.2 table | major | partly |
| K2-5 | **Blade loads are not disinfected as written.** Grid, slicer, grater, whisk and kneading lid get "80 °C rinse instead": 0.8 L in 20 s. A0 ≤ 20 [C], against 60. These are the single-instance parts shared by raw and RTE food. | §6.2, §6.5 | major | yes (longer hot rinse, second instances) |
| K2-6 | Quill nose: bayonet, bellows and spindle lip seal above open food, fixed, washed **daily** by tier nozzles. The explorer states the conflict with HYG-004 and HYG-016. It also carries the drinking-water outlet, the only fixed Zone F item. HYG-033 asks for cleaning after each meal. | §2.3; §6.3 | major | partly |
| K2-7 | Annular turntable labyrinth at K/H: boil-over runs in; "a real harbourage risk", inspected by endoscope at service. | §6.3 | major | partly |
| K2-8 | Metal-to-metal rim joints for frying flips leak fat into the shaft, where the telescopic slide with open profile, rack drive and plain bearings travels beside the vessel (R6 6.2: racks behind a wall). | §6.1, §6.3 | major | partly (gasketed flips only) |
| K2-9 | Jaws are the one shared contact path between raw and RTE ware; they are rinsed for 3 s with cold mains water. That is not disinfection (FSF-040). | §6.3, §6.5 | major | yes (hot rinse, or two jaw pairs — it has A and B) |
| K2-10 | Rinse seat with an upward fan nozzle at the shaft foot; open vessels travel in the same shaft above it. | §2.4 | minor | yes (shutter) |
| K2-11 | Dock is a dry flour zone washed weekly with water: paste. Coupler-ring silicone beads take up odour ("not solved"). Fourteen part types have no second instance: a failed verification blocks operations until a human replaces the part. | §6.3; §9 | minor | yes |
| K2-12 | Water: explorer 38 L preparation, about 50 L with dishes. With cooking water and a wash-down at even 3 L/m² it is 70–80 L [C/E]. The "quarter load" of the central washer (5 L) assumes someone else fills the rest. | §6.4 | major | partly |

Good: no vessel carries a seal, bearing or magnet; gaskets only on interposers; rotation past fixed jets is
a sound coverage argument for bodies of revolution; lathe camera with stripe light is a good inspection
geometry.

**Score 5.**

### K3 — Drum and belt line

| # | Finding | Where | Severity | Fixable? |
|---|---|---|---|---|
| K3-1 | **The drum is a fixed food surface that cannot leave.** 0.42 m², it boils, sears at 220 °C, kneads and mixes mince. Wash: 1.5 L of liquor for 3 min at 55 °C, 6 L in all. Then it is heated to 110 °C, which bakes on whatever remained. If it fails verification: "no meal possible" — and nothing but a human can scrub it (HYG-006). | §6.2; §9 | major | yes (long soak programme in the drum itself; inspect before the flash) |
| K3-2 | The drum is the one vessel for raw and RTE food. Heat kills bacteria; it does not remove allergens (R6 5.3). Allergen separation rests on the 3-minute wash. | §6.4 | major | partly |
| K3-3 | **TPU belt in the wet zone under raw meat.** R6 6.2: belts "only in a dry tunnel; do not use in splash zone"; TPU hydrolyses above 60 °C. The belt is washed at 55 °C and steamed at 90–95 °C every meal; the grade is "unverified". | §2.2; §6.3 | major | no (the belt is the concept; a loose sheet is a different concept) |
| K3-4 | Hidden wet surfaces under the food: belt inner face, slider bed with drain grooves, nose bar and rails, pocket rollers, dancer: 0.75 m². Meat juice creeps round the edge. Cleaned per meal only when raw food was used, otherwise daily. | §6.1 row 7; §6.3 | major | partly |
| K3-5 | Steam bar energy: 1.5 kW of steam against about 1.6 kW needed to raise the full belt section (300 × 2 mm at 20 mm/s) by 60 K [C]. The claim rests on heating the surface only; no margin, and the belt is wet. | §6.3 step 5 | major | yes (slower, more steam) |
| K3-6 | **Contradiction on raw meat.** §6.4 says raw mince never touches the belt; the failure table has "mince log sticks in the pocket", and flat raw cuts slide onto the belt by design. The belt is a class R surface. | §6.4 vs §9, §3.2 | major | — (must be restated) |
| K3-7 | The dock chute is shared by raw packs and RTE doses; the answer is "raw last" and a narrowing sleeve. No disinfection between. | §6.4 | major | yes (second chute as ware) |
| K3-8 | The belt has no per-cycle surface inspection: drum has a camera, belt has conductivity and a weekly riboflavin test. | §9 | major | yes (top camera exists) |
| K3-9 | Gates above the belt: G2 beam with a drum motor and a gearmotor pod, four rod collars, G1 blade clamps, nine comb-blade roots. Their wash water drains onto the belt. | §6.1 rows 8–10; §6.3 | minor | partly |
| K3-10 | Tools washed inside the dirty drum, one after another in 3 min (15 heads and inserts exist); silicone parts leave wet; knurled peel disc "most likely to fail a swab". | §6.2 | minor | yes |
| K3-11 | Water: 24 L in place + 6 L share of wash-down + 17–20 L ware + dishes + cooking = about 63 L [C]; the document says 50–55. Zone S 11.5 m² washed with 12 L per day. | §6.6 | major | partly |
| K3-12 | Endless welded belt: exchange means threading it through bed, nose, dancer and wash box. Not a 15-minute task for a user (HUM-007). Life not stated in the cleaning section. | §2.2 | minor | yes |

Good: no seal or shaft inside the drum; the blade never touches the belt; waste leaves at the tail away from
the shaft; shuttle has no wall penetration.

**Score 3.5.**

### K4 — Shuttle mat

| # | Finding | Where | Severity | Fixable? |
|---|---|---|---|---|
| K4-1 | **The primary food surface is 10 m² of elastomer and textile, stored wound and wet.** The explorer: "a wound roll cannot dry." The remedy is 3 min in 40 °C air. Flap-lip roots lie folded flat in the roll; the hem is a closed pocket. Rarely used mats (rasp, mesh) sit damp for days: HYG-024, HYG-051, R6 rule 8. | §6.2 Drying; §6.5 #1, #2 | **fatal** as designed | only by leaving the reel (mats as loose sheets to a washer, or stored drawn out and dried) |
| K4-2 | **Mat K is not disinfected after raw meat.** At 25 mm/s a point spends 1.6 s in the 40 mm rinse zone: A0 about 5 [C]. "Held three times for 60 s" treats 120 mm of a 2.4 m mat. Doing the whole soiled length takes about 20 min, not the 4 min in §6.6 [C]. K takes no steam. | §6.2; §6.6 | major | yes (second K for raw, longer hot zone) |
| K4-3 | Mat K is cut on: 60 000 blade landings a year, 0.2 mm into a 1 mm film. Scored polyethylene under raw meat; the explorer gives 6–12 months until it fails HYG-020. | §6.7 | major | partly (it is a consumable: two human exchanges a year for K alone) |
| K4-4 | Steam slot: 4 s. A0 is 40 at 90 °C and 126 at 95 °C [C]; the claim needs ≥ 92 °C from the first second. Detergent contact is 5 s. For mince and dough on silicone this is rinse-grade action, not a wash. | §6.2 | major | yes (slower pass, at a time cost) |
| K4-5 | Mesh mat P: PTFE-coated woven glass. Every crossing is a crevice; the explorer expects it to fail first. A fraying glass-fibre mesh is also a foreign-body source (FSF-070), and PTFE is on R6's regulatory watch list. | §2.1; §6.5 #3 | major | yes (delete P; use a perforated steel basket as ware) |
| K4-6 | Fixed Zone F of 0.69 m² shared by raw and RTE: table, cheeks, blade, bar B. A wet film is trapped between mat and table during work. The soft anvil is a bonded joint in the wettest place. | §6.3; §6.5 #5, #10; §6.6 | major | partly |
| K4-7 | 22 rotary passages; five are on the arms and move over food; the bar-joint lip seal is 40 mm from the mat edge. | §2.5; §6.5 #8 | major | partly |
| K4-8 | One 2 L gate sump serves all mats, renewed twice a meal. The liquor that washed mince, egg and mustard off S then washes the dough mat D; 0.5 L of rinse for 2 m² follows. Allergen carry-over is untested. | §6.2 | major | yes (fresh liquor per mat class) |
| K4-9 | Fixed fan nozzles rinse table and cheeks after every retraction while vessels stand open at P1 below the loop zone. | §6.1 | minor | yes |
| K4-10 | Water: the "40–48 L, at the limit" total omits the human's dish load. With it: 48–59 L [C]. | §6.4 | major | partly |
| K4-11 | Disc-knife roller: discs, spacers and comb stacked at 5 mm pitch; "doubtful" in a chamber washer. Wet plain bearings on rollers E and L. | §6.5 #7, #9 | minor | yes |

Good: a flat mat under a top camera is the best inspection geometry of any food surface here; washing within
minutes of soiling; S and D are separate instances; the explorer's list of crevices is complete and frank.

**Score 3.** The concept asks more of elastomers and textiles than R6 allows anywhere.

### K5 — Ram and die column

| # | Finding | Where | Severity | Fixable? |
|---|---|---|---|---|
| K5-1 | **Tube final rinse does not reach A0 60.** 1 L at 85 °C meets 1.6 kg of steel at about 50 °C: equilibrium about 79 °C [C]; 45 s there is A0 about 36. The document claims 60 after 15 s. | §6.2 row 1 | major | yes (2–3 L or recirculate the hot litre) |
| K5-2 | **Chutes carry mince and egg, then RTE doses.** They are flushed cold after class R, washed hot daily, and go to the washer weekly. No disinfection before the next RTE dose (FSF-040). | §6.2 chute row | major | yes (red chute as ware, per meal) |
| K5-3 | Carousel plate is shared and gets a mince film at every shear-gate move; window ledges are exposed only while pegs lift the inserts; the hood is an open labyrinth inside the bay. | §6.2; §6.4; §6.6 #3 | major | partly (no shear-gate with class R) |
| K5-4 | UHMW lip ring snapped on every tube: a crevice behind the snap, taken off weekly. HYG-030 asks for cleaning after each use. Same for the double-lip groove of every piston ("a known soil trap"). | §6.2; §6.6 #1, #2 | major | yes (one-piece rim, single-lip piston) |
| K5-5 | **Frying book.** Leaf frames and hinge trough next to a 240 °C pan; two rotary seals 40 mm from the fat; carbonised fat "not removed by a 55 °C spray"; a silicone rim gasket in frying fat at 200 °C. | §2.3; §6.2; §6.6 #8, #9 | major | partly (frames as ware) |
| K5-6 | **Shuttle slot** 1300 × 70 mm with band cover: "a surface that is cleaned by nobody", above all food. R6 checklist item 1 calls that a defect. | §6.2 last row | major | partly (rotary shuttle instead of a slot) |
| K5-7 | Ram and crank rod collars above open tubes; pistons washed in a box under the deck with the used tube liquor; mesh dasher, duckbill slit, iris die. | §6.2; §6.6 #5–7 | minor | yes (delete iris and duckbill) |
| K5-8 | Water: explorer 50 L before dishes; with dishes and cooking water about 64 L and 4.7 kWh [C]. Fourteen cookware items as "one load" is tight for a 9 L pot plus GN pans. | §6.3 | major | partly |
| K5-9 | 96 loose pieces of 44 types. | §2.6 | minor | partly |

Good: the tube is the best-cleanable working cavity in the set — a plain electropolished bore, pigged,
jetted by a travelling head, seen whole by one bore camera; red and green tubes, pistons and sickles; tubes
clean and dry 15 min after use; waste through a diverter into a chip box.

**Score 5.**

### K6 — Loose ware and fast washer

| # | Finding | Where | Severity | Fixable? |
|---|---|---|---|---|
| K6-1 | **Zone S is 10.7 m², open, cluttered, washed once a night.** The wash liquor is the day's used tank water, sprayed over walls and ceiling above the benches, followed by 10 L at 65 °C. Frying grease stays up to 24 h. The explorer: "coverage is not proven". | §6.3 | major | partly (partition the hob; fresh liquor) |
| K6-2 | **Manipulator above open food**: Y slot with sealing band, tilt and spin lip seals with grease behind them, jaw guides. Closed boxes breathe; condensate inside finds the band edge. | §2.4 items 2–6 | major | partly |
| K6-3 | Final rinse: 2.2 L at 85 °C for 20 s on about 5 kg of steel at 60 °C gives about 80 °C at the surface [C]; A0 is 20–60 with cool-down. The explorer says "to be proven". | §6.1 | major | yes (3 L, 30 s) |
| K6-4 | One 10 L tank for the whole day, all loads, raw and RTE. Normal commercial practice, but allergen removal then rests on the 2.2 L rinse alone, and the 100 s wash needs pH 12–13 (HYG-011 allows 12.5; WSH-010 asks household products). | §6.1 | major | yes (tank change after class R or allergen loads) |
| K6-5 | Water and energy over the limit by the explorer's own count: 47–56 L, 4.4–5.0 kWh. 40–50 items and 7–9 loads per meal. | §6.2 | major | partly (fewer items) |
| K6-6 | Tray and pot tangs have no drip collar; the chuck carries a splash to the next item. Jet gate and dam reduce it. | §6.6 #1 | minor | yes |
| K6-7 | Frying fat above 30 mL has no path (WSH-016). | §6.5 | minor | yes (fat cup) |
| K6-8 | Burnt-on cookware needs the 15 min programme; "once in three warm meals" is optimistic for a machine that sears. Egg cracker hooks, cut-off slide rails, grid crossings. | §6.1; §6.6 #4–6 | minor | yes |
| K6-9 | Well lid drips condensate on clean ware; the lid channel is outside the coaming. | §6.6 #12 | minor | yes |

Good: fixed Zone F is zero; every item is washed in a closed well in a fixed, validated pose; soiled ware is
wet-parked under a lid; every load gets the hot rinse; each item is turned before a camera with white, oblique
and UV-A light and an IR check at lift-out; all clean 15–20 min after hand-over; two wells give partial
redundancy; spraying happens behind a lid, not in the food air space.

**Score 7.** The ware side is the best of the eight; the bay around it is ordinary.

### K7 — State change and rigid handling

| # | Finding | Where | Severity | Fixable? |
|---|---|---|---|---|
| K7-1 | **The sink well is the red bench.** Raw meat is worked on a grate over the same 0.45 m² well in which salad is washed. Between the two: 2 L at 60 °C and 60 g of steam, "well at 85 °C for 1 min". 60 g of steam delivers about 135 kJ; 5.4 kg of well wall needs about 160 kJ for 60 K before losses into the deck [C]. The well does not get there. | §7.3 sink row; §7.5 | major | yes (3–4 × the steam, or red work on a tray bench) |
| K7-2 | **Aluminium cold plates and slabs** in a splash zone that raw-meat trays enter. R6 4.2 excludes aluminium from Zone F/S. They are cleaned by 2–3 L of 40 °C water daily, no detergent. Lid sheets float on the raw food and touch the slab above. | §1.1; §7.3 CC row; §3.4 | major | yes (stainless-clad plates; detergent in the defrost) |
| K7-3 | Slot washer pre-rinse is "overflow from the tank, ≤ 40 °C"; the tank is at 55–60 °C. Either the pre-rinse is hot soiled liquor on egg and flour (R6 rule 19), or there is an unlisted cold supply. | §7.2 | major | yes (mains pre-rinse) |
| K7-4 | Steam finish: 6 s, of which about 3 s at temperature. A0 is 30 at 90 °C, 95 at 95 °C [C]. Tab weld and rim corners are in shadow. | §7.2 | major | yes (10–15 s) |
| K7-5 | **Most loose parts: about 132** (105 preparation + 27 cookware); up to 35 flat items per meal, washed one at a time, about 40 extra gantry moves, last item clean 25–30 min after use with no wet parking described. | §2.5; §7.4 | major | partly |
| K7-6 | Gantry above food: X slot with cover strip, quill collar, wrist seal; a metal bellows on the knife rod; rubber fingers pushed into a basket (a crevice per finger); sink hub umbrella in produce wash water. | §2.3; §7.7 #2, #8, #10 | major | partly |
| K7-7 | Cold ware frosts over in the cell within seconds and then drips melt water as it is carried. Frost also collects flour dust and aerosol. | §3.4; §7.3 T1 row | minor | partly |
| K7-8 | Water 52–59 L with dishes and cooking water (explorer's own admission). | §7.4 | major | partly |

Good: tempered and crust-frozen meat smears and drips far less — a real and rare hygiene gain; food never
touches a manipulator; thin flat steel is the easiest thing to wash, disinfect and dry; the slot is an
enclosed spray space; red instances for tongs, knife, board and trays.

**Score 5.5.**

### K8 — Sealed tub with magnetic pucks

| # | Finding | Where | Severity | Fixable? |
|---|---|---|---|---|
| K8-1 | **Separation is temporal only, in one air space.** The red-to-green rinse runs 4 bar fan jets over a raw-meat board with RTE food elsewhere in the same tub. The explorer states that raw splashes on the drive wall "are not removed by the rinse". The pucks then slide across that wall. | §6.4 raw/RTE paragraph | major | partly (lids on everything; rinse only in a shrouded gate) |
| K8-2 | **The manipulator is a bearing in the food zone.** Puck = rotor + spider + PEEK thrust washer + loose bush + four pressed-in PTFE-filled skids (joint ≤ 0.1 mm), sliding on a wetted wall beside the food. A polymer transfer film on the wall is intended; its debris and the wall run-off go down to the work area. | §2.5; §6.4 puck row; line 141 ff. | major | partly (unfilled skids; drip gutter below the puck zone) |
| K8-3 | **Rinse budget does not close.** At the gate's 12 L/min, 6 s per vessel is 1.2 L, not 0.6; two pucks at 20 s are 8 L and are not in the 11 L; 3 L through spray balls rated 40 L/min is 4.5 s for 3.25 m². Realistic fresh rinse 25–30 L; full wash about 40–45 L and 2.5–3 kWh [C], against 26 L and 1.5 kWh. The 8 L boiler cannot supply it. | §6.2 | major | partly |
| K8-4 | Vessel disinfection: 6 s at 85–90 °C is A0 19–60 [C]. | §6.2 step 4 | major | yes (longer; costs water, see K8-3) |
| K8-5 | **Frying inside the washer.** Every dinner soils all 3.25 m² and every parked utensil, used or not; the cell is closed 25–35 min; ware from the first preparation step waits soiled in a warm tub for the whole meal (B1: over two hours) unless the 5 s cold tool rinse is extended to vessels. | §6.3 | major | partly |
| K8-6 | Wash with the tub full of its own ware: vessels on the drain rack over the hob shadow the hob glass (a fixed Zone F station); static spray balls rely on sheeting flow. 20 s of gate wash per vessel is short for GN pans that fried. | §6.2; §6.4 | major | yes (path and order) |
| K8-7 | Round thread Rd 28 on the press screw, in mince. Opened fully for washing; still a thread in Zone F (HYG-013). PE boards are cut on (two a year). Door gasket 3.6 m, the usual dishwasher mould site. | §6.4 cassette row | minor | yes |
| K8-8 | A fallen puck or utensil ends with "human opens the door" — into a tub with raw food and hot fat. | §9 | minor | partly |

Good: **no dynamic seal and no moving penetration at all**; Zone N is behind a welded skin; the soiled area is
the smallest (3.25 m² of tub) and all of it is washed after every meal, not nightly; each item is presented
to a camera; small sump loop makes turbidity sensitive; the explorer states plainly that the soil is not
confined.

**Score 6.5.**

---

## 3. Findings that apply to every concept

| # | Finding | Severity |
|---|---|---|
| X-1 | **Thermal disinfection has no margin anywhere.** Recomputed A0 (HYG-021 asks ≥ 60 at the surface): K1 rod 60 at best; K2 blade loads ≤ 20; K4 mat K about 5, silicone mats 40–126; K5 tube about 36; K6 wells 20–60; K7 trays 30–95, sink not reached; K8 vessels 19–60. Only the induction flash (K2, K3 drum) has margin, where it heats evenly. Every figure assumes the surface is at water or steam temperature from the first second. R6 8.2 says the sump probe does not measure the load. | major |
| X-2 | **Daily wash-down volumes are not credible.** R6: 25–40 L for a 2.4 m² cell (10–17 L/m²). Booked: K2 0.8 L/m², K3 1.0, K6 1.9, K7 about 2, K4 about 0.7. K1's 33 L for 5.6 m² is the only figure near R6. Each in-place water total is low by 10–30 L per day. | major |
| X-3 | **Nobody cleans the oven.** All eight open a bought combi-steam oven into the cell and replace its door. K2 says so ("burnt-on spills are not removed"); the others pass it to the cooking module. HYG-033 lists the baking cavity. | major |
| X-4 | **Hobs inside the preparation cell** make 5–12 m² of grease-aerosol splash zone in seven concepts. Only K8 bounds it (3.25 m²). The fume path (slot, duct, condenser, hood mesh) gets a weekly flush at most and no verification. | major |
| X-5 | **Rinse volume against HYG-023.** 0.4 L per item (K7), 0.5 L per mat pass (K4), 0.8 L per lathe load (K2), 0.6 L per vessel (K8). Nobody shows that 3 g/L of alkaline detergent is brought within 50 µS/cm of mains water. | major |
| X-6 | **Verification sees soil, not films or allergens.** Cameras find visible residue; weekly riboflavin tests coverage, not removal. No concept checks protein residue. For fixed surfaces there is no quarantine: K1 seam, K3 drum and belt, K4 table and cheeks, K8 tub end at "flagged", "no meal possible" or "service". | major |
| X-7 | **Spraying in the food air space**: K1 lance, K2 rinse seat, K4 table nozzles, K8 gate. K5 (in the tube), K6 (lidded well) and K7 (slot) spray in enclosed spaces. | major |
| X-8 | **Scale.** Nozzles of 1.0–1.5 mm, 85 °C boilers and three steam generators (K3, K4, K7) at up to 25 °dH (HYG-052). No concept sizes a softener or its salt (HUM-004). | major |
| X-9 | **Dicing grids** appear in all eight; blade crossings hold fibre and sinew; most concepts have one instance per pitch, shared by raw and RTE. | major |
| X-10 | **Silicone** lips, gaskets, aprons and mats everywhere: slowest to dry, takes up onion, curry and fat (HYG-025). | minor |
| X-11 | **One chamber load** for the cookware (K3, K4, K5, K7) assumes 12–16 items including a 9 L pot fit a 480 × 480 × 400 chamber. K1 counted honestly: 45 items, three loads. | minor |

What the human would end up doing (HUM-007 allows two visits a year, 15 min):

| Concept | Parts a human must eventually exchange or clean [D/E] |
|---|---|
| K1 | V-rings, four collar cartridges, three rod-tip cartridges; scrubbing the seams if they fail |
| K2 | coupler beads and gasket frame yearly, Z-slot band yearly, quill bellows; labyrinth by endoscope |
| K3 | endless belt (threading job), rod collars, drum by hand if it fails |
| K4 | five mat cassettes a year, K twice; table plate with anvil |
| K5 | lip rings, pistons, rim gaskets, hinge seals; carbon on the book frames |
| K6 | sealing bands, two wrist seals, boards, silicone tools |
| K7 | rubber fingers yearly, bow-knife blades, boards, cover strip |
| K8 | skids and washers, PE boards twice a year, door gasket |

---

## 4. Comparison

Water and energy: explorer's cleaning figure for preparation and cooking ware plus cell; then my total per
reference meal with the human's dish load (10 L, 0.9 kWh) and cooking (4 L, 1.3 kWh) added, and corrected
where section 2 found an error. Limits: 45 L, 4.0 kWh. Wash-down volumes are left as booked (X-2), so every
total is still a lower bound.

| | Fixed Zone F m² | Zone S m² | Soiled per meal | Loose parts | Moving seals, slots, gaps | Water L: explorer → total [C] | Energy kWh: explorer → total [C] | Cell free / all clean after serving | Raw–RTE separation | Verification |
|---|---|---|---|---|---|---|---|---|---|---|
| K1 | 0.04 (+0.17 rods above food) | 5.6 | 25–45 items, 3.5 m² | not totalled; 45 per menu | 6 seams, 4 collars, 3 core seals; all above food | 90 → **110** | 5.9 → **8.1** | 45 min / 3 h | red ware + sequence; bench vs turntable | cameras on deck and walls; none into the seams |
| K2 | ≈ 0 (water outlet) | **12** | 24 pieces, 3 m² | 76 | 8; quill above food | 38 → **52** (70+ with X-2) | 1.8 → **4.0** | 10 min / 55 min | by instance and time; shared jaws | lathe camera, pyrometer, turbidity |
| K3 | **1.5** | 11.5 | 12–16 ware + heads | 46 | about 14; 4 rods above belt | 24 (+18 ware) → **63** | 1.3 (+1.3) → **5.1** | 12 min wet, 35 dry / 75 | temporal for drum, belt, chute | drum camera; belt none per cycle |
| K4 | 0.69 + **mats 10** | 8.3 | 3–5 mats, 8–14 ware | 36 + 5 mats | 22 rotary; 5 on moving arms | 15 (+18) → **48–59** | 0.85 (+1.3) → **4.4** | 12–15 min / 75 | S vs D by instance; K, blade, table temporal | top camera on the flat mat |
| K5 | ≈ 0.45 (carousel, chutes) | 5.0 | 14 ware + column parts, 2.6 m² | 96 | 14 + one open slot | 50 → **64** | 2.5 → **4.7** | 15 min column, 25 cell / 75 | red tubes, pistons, sickle; dies, carousel, chute temporal | bore camera (UV), back light |
| K6 | **0** | 10.7 | 40–50 items, 1.5 m² | 93 | 16; 5 above food | 35 → **49** (47–56) | 2.3 → **4.5** | 0 / **15–20 min** | red and green duplicates, wash between, chuck gate | **per item**: camera white + UV, IR |
| K7 | 0.45 (sink) | 9.3 | 18–35 flat + bulky load | **132** | about 13; 3 above food | 38–45 → **52–59** | 2.6–2.8 → **4.8–5.0** | slot 25–30 min / 75 | red instances; sink bench temporal | grazing-light camera, records |
| K8 | 0.31 (hob glass) | **3.25** | whole tub + 1–1.5 m² vessels | about 85 | **0 dynamic** | 26 → 40 claimed; **54–59** corrected | 1.5 → 3.7 claimed; **4.7–5.2** corrected | 25–35 min / 35 | **temporal only** | per item camera white + UV; sump loop; coupon |

Cleaning budget that follows from the requirements [C]: 45 − 10 − 4 = **31 L** and 4.0 − 1.3 − 0.9 =
**1.8 kWh** per reference meal for everything the preparation and cooking cell soils. No concept is inside
it.

---

## 5. Cleaning sub-mechanisms, ranked by credibility

| Rank | Mechanism | Used in | Why here |
|---|---|---|---|
| 1 | **Tang-hung wash wells**, tank wash + 85 °C rinse | K6 | Commercial tank-washer practice in a closed chamber; fixed pose per item type, validated once; every load disinfected; manipulator stays outside. Open points: rinse margin (X-1), shared tank, burnt-on needs the long programme |
| 2 | **Drip-collar stems** | K1, K4, K5, K6, K7 | Passive, no part, no failure mode; it prevents soiling rather than removing it. Fails exactly where it is left out (K6 trays) |
| 3 | **Pigging + travelling jet head in a plain bore** | K5 | R6 rates CIP of a simple cavity high; the pig removes the bulk, one camera sees the whole bore. Open: hot rinse volume, lip ring |
| 4 | **Wash lathe** | K2 | Rotation past fixed jets gives coverage by geometry for round ware, in a closed chamber, with a good camera view. Open: 120 s is short; GN corners; one load at a time |
| 5 | **Tub wash** | K8 | Dishwasher pedigree, whole cell washed every meal. Open: tub full of ware shadows itself; blocks the cell; rinse budget |
| 6 | **Jet gate** | K8, K1, K6 (chuck) | Credible as a cold pre-rinse within minutes and for the chuck. Not a validated wash: seconds of contact, no soak, and in K1 and K8 it sprays in the food air space |
| 7 | **Induction flash-dry** | K2, K3 | Real margin on A0 and saves hot water, but only on ferritic, even-walled parts; bakes residue if it runs before inspection |
| 8 | **Form-fitting wash holster** | K5 sickle sheath | Pipe flow at 1.5 m/s works for a plain blade; the sheath itself is a 3 mm gap nobody can inspect; one fibre turns it into a dead zone; not a disinfecting step |
| 9 | **Self-washing drum** | K3 | 1.5 L of liquor in a 25 L drum for 3 min, on a vessel that sears; cannot be removed when it fails |
| 10 | **Mat wash on retraction** | K4 | 5 s of detergent, 1.6–4 s of heat, on elastomer and mesh, then stored wet. Coverage of the flat faces is by construction; everything else is unproven |

Not on the list but worth keeping: K7's slot washer (an enclosed jet gate with detergent and steam; rank about
5) and K6's wet parking under a lid.

---

## 6. Hygiene rules for round 2

1. **No fixed food-contact surface**, except a closed cavity of simple shape with its own CIP and a camera
   that sees all of it (K5 tube). Whatever food touches leaves the cell to a closed washer.
2. **No elastomer or textile as a working surface cleaned in place.** Silicone only as a moulded lip on
   removable ware. No woven mesh, no belts, no reels in Zone F or S (R6 6.2).
3. **Nothing that moves crosses the ceiling above open food**: no gap, slot, sealing band, collar or lip
   seal. Manipulators enter through a vertical wall or work through it (K8). Ceiling monolithic, ≥ 5°.
4. **No open jet above 1 bar in an air space that holds open food.** Rinsing of class R items happens behind
   a lid or shutter.
5. **Red instances for everything raw animal food touches**, including grids, dies, chutes and boards.
   Temporal separation is allowed only for removable ware, with a full disinfecting cycle between; never for
   a fixed surface. "Raw last" is a help, not a control: B1 breaks it in most concepts.
6. **Thermal disinfection is designed to A0 ≥ 120 by calculation** at the coldest point, with the heat
   balance shown (mass of the part, its start temperature, water or steam quantity). Steam pulses under 10 s
   count only after a logger test.
7. **Inspect before any heat step.** No flash, steam or 85 °C rinse on a part that has not passed the
   camera.
8. **Cold pre-rinse within 2 min of emptying a hot vessel, within 30 min otherwise; then wet parking under
   a lid; wash starts within 20 min.**
9. **Budget per reference meal for all cleaning caused by preparation and cooking: 31 L, 1.8 kWh, at most
   25 soiled items and two wash loads.** Every concept reports in one common table. Wash-down is booked at
   ≥ 5 L/m² per event until a test shows less.
10. **Frying and boiling are contained**: a hot bay or hood with its own extraction, separated from the
    preparation bay; target total Zone S ≤ 4 m². The fume path is removable to the washer or has a hot
    alkaline cycle, and is inspected.
11. **Every item is verified individually** at lift-out (white, oblique and UV-A light, IR temperature), and
    every fixed splash surface has a camera line of sight. Escalation: repeat, intensive programme,
    quarantine with a duplicate in stock. No single-instance Zone F part. A fixed surface that fails twice
    locks the cell and runs the intensive programme; it does not call the human to clean.
12. **The oven must clean itself** (pyrolysis, or a steam-clean programme with a drain) and oven ware is
    deep or lidded. Request to the architect and the cooking module.
13. **Softened water** for every nozzle ≤ 1.5 mm, every boiler and every steam generator; flow or pressure
    monitored per nozzle circuit; no recirculated liquor through holes under 2 mm.
14. **Waste**: perforated chip box that leaves as a box; fat cup for anything above 30 mL; peel slurry
    flushed within 2 min; no open gutter longer than needed.
15. **Dicing grids**: monobloc, cleared by a comb piston before washing, checked against a back light, two
    instances per pitch (red and green).
16. **Wear parts**: each concept lists every part a human exchanges, with interval; the sum must fit HUM-007.

### Recommendation

* **Carry forward K6's ware principle as the hygiene baseline**: zero fixed food surface, tang-hung closed
  wells, per-item verification, wet parking. Fix its bay: separate the hobs, shrink Zone S, take the
  sealing bands out from above food, give the rinse a margin, cut the item count.
* **Graft onto it**: the K5 tube with pig and bore camera for pressing, dicing and forming (without the
  shared carousel, shear gate and frying book); K8's zero-penetration idea for whatever wall the
  manipulator works through, and its habit of washing the whole enclosure after every meal; K7's tempering
  of raw meat, with stainless-clad plates.
* **K8 deserves a second round in its own right** if the rinse budget is redone honestly and raw work gets a
  physical barrier (a lidded or shrouded red zone); it is the only concept with no dynamic seal.
* **On hygiene grounds, do not carry forward**: the K4 mat reel, the K3 belt and fixed cooking drum, and
  the K1 ceiling seams — K1 only if the one-seam riboflavin test (its own risk 1, 3 days) is run first and
  passes. K2's lathe is a reasonable option for round ware but does not justify 12 m² of shaft and tiers.
* **Three cheap tests before round 3**: (a) riboflavin coverage of a K6 well with its load pattern;
  (b) data loggers on the coldest item for each claimed hot rinse or steam pulse; (c) protein swab after the
  short cycles, with egg, mince and flour paste dried for 30 min.

---

## 7. Open issues

1. All recomputations use the documents' own flows, masses and times with textbook heat capacities; none was
   measured. Where a document's figure was ambiguous (K8 gate flow during rinse, K7 pre-rinse source) I took
   the reading that follows from its stated hardware and said so.
2. The benchmark walk-throughs were not audited step by step; soiled-item counts are the explorers'.
3. K1's total loose-part count was not found in the sections read.
4. The gap modules (G-produce, G-assembly-meat) declare all their tools to be loose ware for the washer. They
   add about 30 passive parts and two hygiene items of their own: the twin carving blade joined by a rivet,
   and a conventional egg-cracker cassette with pivots. Both need the "falls apart in the washer" treatment.
5. A0 ≥ 60 itself is a design choice in R6, not a validated regulatory value (R6 open issue 2).

## 8. Risks

| Risk | Consequence | Mitigation |
|---|---|---|
| Round 2 selects on coverage and speed and treats cleaning numbers as equal | A concept with a fixed or elastomer food surface is carried into detailed design | Apply rules 1–5 as entry conditions, not as scores |
| The common budget (rule 9) cannot be met by any concept | RES-005 and RES-001 have to be renegotiated with the customer | Report early; the ware count is the lever, not the washer |
| My recomputed A0 values are too pessimistic (parts hotter than assumed) | Some "major" findings shrink to "minor" | Logger test (b) settles it in a day |
| Separating the hobs from the preparation bay conflicts with handling during cooking | Containment rule 10 costs a second manipulator or a pass-through | Let round 2 price it explicitly |
