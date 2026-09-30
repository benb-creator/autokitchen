# AutoKitchen — Customer decisions and project-level rulings

Additions to [BRIEF.md](BRIEF.md), made by the customer or by the orchestrator during the project.
They rank directly below the brief and above all research, requirements and design documents.

| # | Date | Source | Decision |
|---|------|--------|----------|
| 1 | 2026-09-30 | Customer | A three-phase cooker connection (400 V 3N~, 3 × 16 A, approx. 11 kW, German "Herdanschluss") is available if needed. Designs may rely on it. Power management is still required, but the machine is not limited to one 230 V / 16 A circuit. |
| 2 | 2026-09-30 | Customer | Meal preparation is the most novel part and needs new ideas. It is developed in multiple rounds by multiple agents: idea finding, exploration of each idea, critique, iteration and improvement (see PLAN.md, Phase 2P). |
| 3 | 2026-09-30 | Orchestrator, from research R7 (no customer objection) | Ingestion has two lanes. DECANT: dry, ambient-stable, free-flowing goods are opened and funnelled into a storage box at ingestion, as in the brief. STOW: products whose shelf life collapses once opened (cans, jars, bottles, cartons, tubs, vacuum/MAP meat etc.) are scanned, weighed and stored sealed inside a storage box or carrier, and opened just in time before preparation by the package-opening mechanism. |
| 4 | 2026-09-30 | Orchestrator, from research R6; confirmed by customer | FDM 3D-printed parts are not used for food-contact surfaces that are washed and reused. Printed parts are allowed in the non-food zone, and in the splash zone only if sealed, replaceable and below approx. 60 °C. Food-contact parts are stainless steel or moulded/machined food-grade standard parts. |
| 5 | 2026-09-30 | Orchestrator, from research R5/R8 | Consumer induction hobs cannot be started remotely through their APIs. The hob is built from a controllable OEM/commercial induction module, not from a finished consumer hob. |
| 6 | 2026-09-30 | Customer | **Used dishes are returned at the serving hatch** and the machine washes them itself ("that would be perfect and ideal"). This replaces the brief's "human loads the dish washer and puts clean dishes back": the human's only dish task is to bring used dishes back to the hatch. The machine stores, washes, dries and dispenses its own dishes. |
| 7 | 2026-09-30 | Customer | Ingestion version A: the minimum is packages placed one by one; a jumbled pile is the target. |
| 8 | 2026-09-30 | Customer | **Pre-processed food.** Allowed to buy: products pre-processed only by cutting and portioning, e.g. fish fillet, minced meat, butcher cuts. Not allowed: industrial ingredients / semi-finished products, e.g. ready-made dough. The purpose is fresh, healthy meals from natural ingredients, without industrial food. **The machine must wash, peel and cut fruit and vegetables itself** — e.g. cutting onions, cucumbers, tomatoes. Supersedes requirements MEAL-012 where it permits cut or frozen vegetables, liquid egg etc.; the requirements must be aligned. |
| 9 | 2026-09-30 | Customer | **Onions:** buying peeled onions is accepted and is the baseline. (Customer's suggestion for a later upgrade: peel onions like cucumbers, with a peeler; cutting away a bit too much is acceptable.) Cutting/dicing onions is always done by the machine. |
| 10 | 2026-09-30 | Customer | Persons per meal: 1–6 (confirmed). |
| 11 | 2026-09-30 | Customer | Height: 2000 mm to 2200 mm is allowed (was 2000 mm). Depth stays 600 mm. |
| 12 | 2026-09-30 | Customer | Leftovers: discard; store them if that is easy. |
| 13 | 2026-09-30 | Customer | **The machine is the household's only fridge and pantry.** Storage capacity must cover all household food, not only cooking ingredients. The machine also serves simple drinks and snacks from storage, e.g. pours a glass of juice from a juice carton on request. |
| 14 | 2026-09-30 | Customer | Tacos and wraps may be served as components for simple assembly by the human at the table. |
| 15 | 2026-09-30 | Customer | Every commit is pushed to the GitHub repo benb-creator/autokitchen. (A post-commit hook in the local repo does this; agents need not push manually.) |
