# Meal preparation — Round P5: the combined machine "EINHAND"

**EINHAND** ("one hand"): one serial gantry hand, one deck, one washer for ware and dishes, one bought oven.
This is the simplicity-first hybrid H-S1 of `04-decision-matrix.md` §6, worked out as one machine. It takes its
skeleton from K6 (loose ware, tang grip, washer as the only cleaning point), its seal-free drives from K8 (canned
magnetic couplings), its press from K8 and K6 (screw cassette with K6/K5 end plates), its stirring from K6/K7
(turning pot under a hung scraper), and the gap modules from G-produce and G-assembly-meat.

Decision state: DECISIONS #1–26. Markers: **[D]** taken from a concept, critique or gap document; **[C]**
calculated here; **[E]** engineering estimate; **[U]** unknown, a test or a supplier answer decides. Nothing has
been built. All times, masses and costs are estimates unless marked otherwise.

Document map: 1 principles and limits · 2 selection table · 3 the machine · 4 generic produce module ·
5 benchmarks · 6 cleaning · 7 numbers · 8 simplicity audit · 9 risks and kill experiments · 10 open questions.

---

## 1. Design principles and hard limits

### 1.1 Principles (binding for this concept)

| # | Principle | Source |
|---|---|---|
| P-1 | **Everything that touches food is loose ware** and leaves for the one washer after use. No fixed cutting, forming or plating surface. The only fixed food-contact surfaces are the hob glass (Zone F only under pans, which are ware) and the hatch drawer's frame (covered by a ware tray) | C2 R-1, K6 |
| P-2 | **Nothing above an open vessel**: all drives, rails and the three sealing bands are in the rear lane (y 0–120) or in closed boxes; the only part that passes over food is a closed arm tube and the wrist. Fume intake, oven mouth and stores are never in the vertical projection of an open food vessel during work | C2 R-2 |
| P-3 | **One hand, no dock, no tool changer**: the gantry tips opened boxes, carries ware, holds tools and works passive fixtures. A station is added only if it carries meals that no recipe route or passive part can carry | C5 §5.1 A1, §6.3 rule 2 |
| P-4 | **No new seal**: rotary work through the deck uses canned radial magnet couplings in welded thimbles (K8 R-can). Force is made inside ware (screw cassette) from the roll torque of the wrist, not by a press drive through the deck (K8 R-torque) | C3 §7 ranks 1–3, K8 |
| P-5 | **Stir by turning the vessel, not by holding a spoon**: two of three hob positions turn the pot under a hung scraper or kneading roller, so the single hand is free | C3 §7 rank 1, C1 §7 rank 2 |
| P-6 | **Recipe routes before mechanisms**: cook potatoes in the skin and rice or slip them; scrub carrots; leek cut before washing; sprigs in an infuser; Bratkartoffeln from cooled boiled potatoes; adapted methods inside the MEAL-019 budget | C1 §10.3, G-produce GP-P1, C5 §6.1 rank 1 |
| P-7 | **Food result rules from C1 §10.3** are part of every recipe: fond before deglazing; fried items finish last; 200–250 mL fat for Schnitzel; turned by lift rack, never by inverting fat; core probe for every steak, roast, mince and poultry item | C1 A-2…A-5 |
| P-8 | **Hygiene rules C2 R-1…R-12** apply as written; in particular moist-heat disinfection only (60 s rinse hold at ≥ 82 °C), one-way flow at the washer, red/green ware, unwashed produce is class R, grit to a strainer before anything recirculates | C2 §8.1 |
| P-9 | **Degrade and continue**: every food-process failure has an automatic path (redo, swap to the fallback method, or serve without the item and tell the user) | C3 §8 rec. 7 |
| P-10 | **One standard ware interface**: a flat tang at rim height on one side with two Ø 8 holes and a ferritic insert (K6 geometry, C4 R-2); equal rims for the pan pair; GN 2/3 and one round family (Ø 220, Ø 280) | C4 R-2, R-3 |
| P-11 | **Whole-machine budgets first** (C4 §9.1): wall width, the three-phase plan, water and energy reported honestly (not gates, #22/#23) | C4 |

### 1.2 Hard limits (C5) and where EINHAND stands

| Limit (C5 / matrix §6.1) | EINHAND | Verdict |
|---|---|---|
| ≤ 10 motion actuators in the cell | **8** normalised (X, Y, Z, roll, chuck, 2 turning drives, deck drive); 9 with the oven door; the hatch drawer (serving) is the 10th of the whole cell-plus-serving block | met |
| ≤ 5 dynamic seals | **4**: three stainless sealing bands (X, Z, Y) and one lip seal on the hygienic roll servo | met |
| ≤ 2 novel mechanisms | **3**: N1 EPM tang chuck with pins (and roll-driven tongs), N2 generic produce module (spit-and-shoe paring, grid skinning), N3 turning skirt pot on a canned roller drive with the pan 2–3 mm above the glass | **exception requested** for N3, see below |
| ≤ 70 handling events per meal | **~70 in the meal** for B3 at 4 persons [E, §5]; **~110 including dish handling and washer loading after the meal** | met for the meal; exceeded by the dish duty that DECISIONS #6 adds and that no K-concept counted |
| ≤ 6 mechanism types; chain ≤ 7; ≤ 50 loose items; ≤ 35 custom types | 7 types (gantry, turning position, deck drive, screw cassette, washer, oven, hatch drawer); chain 6 for B3; **~68 loose items** (+ 8 second-set items); ~38 custom types | items and custom types over; reasons in §3.6 and §8 |

**Exception for N3 (turning pot).** It is the only way a single serial hand can run three hot components with
continuous stirring (risotto, béchamel, red cabbage, porridge, kneading) and still cut, dose and plate. Without
it the hand stirs: COK-008 is still met ("able to stir"), but B1, B9, B10 lose 10–25 min [E] and four-component
menus exceed PERF-001. Its failure has a proven, zero-hardware fallback (the hand stirs with a paddle), so the
risk is time, not coverage. It costs no seal and no actuator beyond the two drives that a turning position needs
anyway. If its kill test (§9, E3) fails, the two drives are removed and the actuator count falls to 6.

**Event count.** C5's 70 was set before anyone counted the dish return of DECISIONS #6: about 25–40 extra
grips per 4-person meal (plates, bowls, glasses, cutlery basket, hatch tray). They happen after serving, at no time
pressure and with unlimited retries, so their effect on REL-001 is small. The in-meal count is the one that
decides whether a meal completes.

---

## 2. Selection table

Confidence H / M / L as in the catalogue. "Beat" names the alternatives and the criteria that decided:
**F** food and coverage, **Hy** hygiene, **S** simplicity, **R** robustness, **Fit** system fit.

| Function | Chosen mechanism | From | Why it beat the alternatives | Conf. |
|---|---|---|---|---|
| Receive box | Transport sets the GN box (lid already removed at a lid station outside the cell, C4 R-4) on a **box shelf** in the upper rear of the serving column; the hand grips the box's moulded tang (ferritic insert) | C4 R-4, R-9; C5 A1 | Beat K2 hourglass dock, K6 tipper dock (2–6 actuators, 1–2 seals): **S, R** — no dock at all | H |
| Receive sealed pack (STOW) | Opened just in time by the opening cell outside the cell (C4 R-5) and delivered upright in a GN 1/3 carrier; the hand pours, spoons or squeezes from the opened pack | C4 R-5 | Beat in-cell openers: **S, Hy** (no can-opener crevice in the cell) | M–H |
| Dose granular, powder, liquid | **Tip the opened box with the roll axis**, loss-in-weight on the wrist load cell (±5 g), pouring directly into the target vessel; lip-pivot pour path (box lip held on a fixed point while tilting, coordinated Y–Z–roll) | C5 A1, K3 lip pivot as geometry only, K2 load pins | Beat docks and dosing lids: **S** (0 actuators); powders by scoop-and-trim (GA-39 core tube as fallback) | M–H |
| Dose seasoning 0.2–5 g | Box tipped over the **0.05 g cup scale S0**, tapped by small roll oscillations; cup emptied into the vessel | K6 S0, GA | Beat vibrating mesh lids (humid air, G-assembly 7.4): **R** | M |
| Dose viscous, fats | Spoon tool or the screw cassette's filler nozzle (syringe principle) from the opened pack; butter cut from the block with the wire bow | K5 syringe as cassette, K8 U15 | Beat frozen pucks (K7): **S** (no freezing step, no puck plate) | M |
| Dose pieces, meat, frozen, long goods | Box tipped onto a GN tray, count and pose by camera; pieces picked by fork-spit, turner or roll-driven tongs; spaghetti by the log-roll weir in the box (GA-29) | K6, G-assembly GA-29 | Beat suction and grabs: **Hy, S** | M–H |
| Eggs | **Passive egg fixture**: bottom strike, hinge-open cradle, slotted saucer, per-egg camera check, beaten egg through a 2 mm strainer | G-assembly 7.2, 7.3; C5 A2 | Beat equator scoring and 3-actuator egg modules: **S, R** | H |
| Wash produce | **Dunk basket over a 40 mm sediment zone** in a red wash pot (ware), plunged by the hand; dump to the drain gully through a 2 mm strainer with a turbidity sensor; leek cut before washing; spin on the deck drive | G-produce GP-W1, GP-W4; K8 S | Beat drum wash (K3), spray-in-basket, bubble baths: **F** (grit physics), **S, Hy** (no fixed sink surface, R-5 red path) | H |
| Peel, core, stone (generic, #25) | **Generic produce module** (§4): spit on the roll axis against a fixed blade post with three depth shoes; grid skinning for soft fruit; blanch-and-slip; cook-in-skin route; knurled drum on the deck drive; tube corers and plunger pitter | G-produce GP-11, GP-Z4, GP-P1/P2, GP-61; K1/K6/K8 spit; new: grid skinning | Beat iris peeler, rasp can, single-fruit devices: **S** (3 mechanisms for the PRP-039 list), **F** | M |
| Cut, dice, slice, grate | Knife (stem tool, draw cut by Y) on a board; **screw press cassette** (tube Ø 100, Rd 28 × 6 screw driven by the roll axis, 2.5 kN) with bought push-dicer grids 6/10/15, slice and wedge plates; grating drum and chopper cup on the deck drive | K8 PZ (torchio principle), K6/K5 end plates, C1 §7 rank 1 | Beat K7 under-deck press (1 actuator, 2 rod seals), K5 8 kN column: **S** (0 actuators, 0 seals), **Hy** (all parts are ware) | M–H |
| Mix, knead, whip, purée | Kneading roller and scraper hung in the **turning 5 L pot** (Ankarsrum principle, up to 30 Nm at the pot); blender jug, chopper cup, whisk cup on the **canned deck drive D** (0–6000 rpm) | K6/K7 turning, K8 S | Beat wrist spin (2 lip seals over food, K6) and planetary mixers: **S, Hy** | M–H |
| Form, roll, stuff, bread | Patties extruded through the cassette's Ø 70 orifice, wire cut-off, smash-formed in the pan; rolling pin with gauge rings on rails (2–10 mm, pasta 1–1.5 mm); ravioli plate (square parcels, IT17/DM33); hinged dumpling press (half-moons: CK17, AS09); breading line in three GN 1/3 trays; Rouladen with side folds, dry floured flap and the **GA-20 raft**; GA-01 peel for stacks | K7 smash, G-assembly GA-01/-08/-20, known household tools | Beat mat line (K4), belt (K3), cold plate (K7), frying book (K5): **S** (all passive ware), **F** | M |
| Cook with stirring | **Turning positions H2, H3** under a hung scraper; H1 plain for frying | K6, K7 | see P-5 | M (N3) |
| Fry and flip | Pancakes, omelette, Rösti: **pan pair** (Ø 280 pan + shallow flip pan with drip skirt), ≤ 30 mL fat, release check; Schnitzel and fish in **220 mL fat (3.6 mm) on a lift-rack pair (GA-36)**; patties, steak: turner, singly | G-assembly 7.1, GA-36; C1 A-3 | Beat frying book (2 actuators, 2 seals near fat): **S**; beat thin-fat flips: **F** | M–H |
| Bake, roast | **Bought countertop-class combi-steam oven**, mouth turned towards the cell, door replaced by a driven side-hinged door; GN 2/3 trays and tins; core probe | C4 R-7, #24 | Beat custom cavities and oven-in-tub: **Fit, S**; geometry is risk 1 | M [U] |
| Drain | Perforated basket in the 5 L pot, lifted and held over the pot; pour-off through a strainer lid into the drain gully when the water is waste | K6, K8 | **S** | H |
| Transfer | Pour by roll about the vessel lip; empty with the silicone-lipped spatula; weigh in the wrist | K6, K2 | **S** | H |
| Carve | Boneless roasts in the **GA-14 V-trough with gauge plate**, single scalloped blade drawn by Y (no twin blade); braises chill-slice-reheat (GA-16); poultry as parts (R-06) | G-assembly 3.2 | Beat belt guillotine (K3), microtome (K5): **S, Hy** | M–H |
| Plate, portion | Heated plate dispensers, plate fork; ladle, turner, tongs, ring mould; plating on the **hatch drawer tray** inside the cell; plated items held at 70 °C under the oven's waste heat in the hatch zone for ≤ 5 min | C4 R-11 | Beat a separate serving manipulator: **S** (no second hand) | M |
| Wash ware | **One side-loading wash chamber** (commercial undercounter washer internals: tank 60 °C, boiler, 85 °C rinse with 60 s hold) in the oven column below the oven; items hung on edge by their tangs | C2 §6 rank 1 (K6 wells), C4 R-10 | Beat in-cell wells (two chambers), tub wash (K8), wash lathe (K2): **S** (one wash system), **Hy** (validated commercial cycle) | M–H |
| Wash dishes | **The same chamber** (assumption: customer accepts one washer, Q1) | C5 Q1 | Saves a 600 mm dish washer and its loader: **S, Fit** | M |
| Clean the cell | Fixed nozzle rail on the soffit's rear edge and in the X box face, a fan and the extraction for drying; hob glass scraped by a stem scraper and squeegeed to the gully; jet gate for the chuck | C5 A4, C2 R-7 | Beat lance wash-down (K1, K2, K5): **S** | M |
| Waste | Closed waste chute WC in the deck to a 20 L bin in a front drawer; peel strainer of the gully emptied into it; fat in a fat cup (ware) | C2 R-8, K6-7 fix | **Hy, S** | H |
| Core temperature | Wireless probe in a stem holder placed by the hand | C1 §7 rank 6 | **F** (FSF) | H |
| Hot-holding | Oven at 70 °C vented (crisp items ≤ 10 min), lidded pots on a hob at keep-warm, hatch zone 60–70 °C (plates) | C1 A-4 | **S** | M |

