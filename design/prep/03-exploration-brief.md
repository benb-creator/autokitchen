# Meal preparation — Round P3 exploration brief

Common rules for all explorers of candidate concepts K1…K8 (defined in
[02-concept-catalogue.md](02-concept-catalogue.md)), so that the results can be compared.

## Working assumptions (orchestrator rulings)

1. **Scope of the preparation cell.** Everything between "a storage box (or a stowed sealed pack) arrives at
   the cell's hand-over port" and "cooked food is handed over for plating", including handling during
   cooking (stir, scrape, flip, baste, drain). The heated positions (4 cooking positions, oven cavity ≥ 45 L,
   warm-hold — see requirements COK-xxx) sit directly beside or inside the cell and are served by the
   concept's own handling. State clearly where you put them; the oven itself may be a bought built-in
   combi-steam oven.
2. **Envelope.** 600 mm deep, 2000 mm high; use as little wall width as you honestly can and state it.
   Three-phase 400 V / 3 × 16 A is available. Cold mains water 2.2–5 bar, drain.
3. **Purchases.** Commodity pre-processed food is allowed per MEAL-012 (peeled onions are the starting
   assumption); shaping, coating and assembly must be done by the machine (MEAL-018).
4. **Materials.** No FDM prints in food contact (DECISIONS 4). Food-contact parts are stainless or
   moulded/machined standard items, preferably bought.
5. **Storage box.** Assume a Gastronorm-family PP box with lid (GN 1/9, 1/6, 1/3 footprint family, see
   research/03) arriving by the transport system. If your concept needs something else from the box
   (dosing lid, rim, tag), say so explicitly as a request to the architect.
6. All eight candidates are explored; none is merged away. No pure bought-robot-arm candidate is added
   (prior art and research/08 rule it out as a backbone; K6 may evaluate a sleeved cobot as its manipulator).

## Required content of each concept document

1. **Definition** — what the cell is, in one page, with a dimensioned ASCII layout (front view and top view).
2. **Mechanism** — kinematics, every actuator (type, force/torque, travel), every wall penetration and how
   it is sealed, the full list of tools / vessels / fixtures with dimensions and whether bought or custom.
3. **Ingredient intake and dosing** — for each form: whole produce, leafy, granular, powder, liquid, viscous
   paste, raw meat, egg, frozen, stowed sealed packs (can, jar, carton, tub, vacuum pack).
4. **Operation table** — every mandatory operation of MEAL-018 and every corpus blocker: mechanism, step
   sequence, time, confidence (high / medium / low), and what is untested.
5. **Benchmark walk-throughs**, step by step with times, vessels used and what is soiled:
   - B1 Rinderrouladen, Rotkohl, Salzkartoffeln (4 persons)
   - B2 Wiener Schnitzel (breaded), Bratkartoffeln, Gurkensalat (4 persons)
   - B3 Frikadellen, Kartoffelpüree, Erbsen-Möhren-Gemüse (4 persons)
   - B4 Spaghetti Bolognese with grated cheese (4 persons)
   - B5 Pizza with yeast dough made from flour (2 trays)
   - B6 Gemüseeintopf / vegetable soup from whole vegetables (6 persons)
   - B7 Steak, oven fries, mixed salad with vinaigrette (2 persons)
   - B8 Pfannkuchen (8 pieces)
   - B9 Chicken curry with rice (4 persons)
   - B10 Lasagne (assembled in layers, béchamel from scratch)
   - B11 Rührkuchen in a tin, unmoulded
   - B12 Scrambled eggs from shell eggs, toast, for 1 person (minimum quantity case)
   For each: can it be done (yes / adapted / no), total elapsed time, number of handling moves.
6. **Cleaning** — every food-contact and splash surface: how it is cleaned, dried and verified; water, energy
   and time per meal; what is cleaned between raw meat and ready-to-eat; what happens to peelings and scraps.
   Name every crevice, seal and spray shadow honestly.
7. **Numbers** — wall width, actuator count, custom-part count, parts cost estimate, peak power, noise
   sources, expected handling moves per meal.
8. **Coverage estimate** against the 248-meal corpus with the reasoning (which meals fall out).
9. **Failure modes and recovery** — jams, dropped food, stuck food, a dirty part that fails verification.
10. **Top risks**, each with the cheapest experiment that would confirm or kill it.
11. **Improvements** you found while exploring, and what you would borrow from other candidates.
12. **Open issues** and **Requests to the architect**.

Be honest: the next round is an adversarial critique. A stated weakness costs nothing; a hidden one does.
All numbers are estimates unless sourced — mark them.
