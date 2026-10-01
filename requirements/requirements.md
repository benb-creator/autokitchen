# AutoKitchen — Requirements Specification

Document: `requirements/requirements.md` (task Q1) · Status: baseline for architecture (A1) and module design (D1–D10)
Source of truth: [BRIEF.md](../BRIEF.md), then [DECISIONS.md](../DECISIONS.md) (customer decisions and project
rulings 1–26 of 2026-09-30/10-01 are incorporated, see section 12.4). Where this document disagrees with either, they
win and the conflict is to be raised as an open issue.

## 0. How to read this document

* **"shall"** = binding requirement. Every requirement has a unique ID, a priority, a verification method and a
  trace to the brief.
* **Priority** — **M** (must: the design is not acceptable without it), **S** (should: expected, may be dropped
  only with a written justification in the module's "Open issues"), **C** (could: desirable, do not compromise
  an M or S for it).
* **Verification** — **T** test (measured on hardware), **D** demonstration (functional show, no measurement),
  **A** analysis/calculation/simulation, **I** inspection of the built item, **R** review of design documents.
  During the paper design phases (A1, D1–D10, V1–V3) every T/D is to be substituted by A/R with the numbers
  shown; the T/D definition states what a later prototype must pass.
* **Trace** — B1…B13 refer to the brief sections in the table below; "DEC-n" refers to decision n in DECISIONS.md;
  "drv" = derived requirement, needed to make a brief requirement achievable, safe or legal.
* Numbers marked **(est.)** are the requirements engineer's estimates, to be confirmed by research R1–R8;
  they are nevertheless binding until changed in this document.
* Requirements state *what*, not *how*. Examples in parentheses ("e.g.") are illustrations, not prescriptions.

| Code | Brief section | Code | Brief section |
|------|---------------|------|---------------|
| B1 | Goal | B8 | Portioning and serving |
| B2 | Parts | B9 | Dishes |
| B3 | Storage | B10 | Ingestion |
| B4 | Cold storage | B11 | Modularity |
| B5 | Meal preparation | B12 | Physical constraints |
| B6 | Cleaning | B13 | Build constraints |
| B7 | Cooking and baking | | |

ID prefixes: GEN general · UC use case · BOX storage box · MODE operating mode · X exclusion candidate · STO ambient storage · CLD cold storage · TRN transport · PRP preparation ·
COK cooking and baking · SRV portioning and serving · WSH washing and cleaning module · ING ingestion (common) ·
INA ingestion version A · INB ingestion version B · CTL control · UI user interface · MEAL meal coverage ·
UO unit operation · CAP capacity · PERF performance · NOI noise · RES resources (energy, water) · HYG hygiene ·
FSF food safety · HUM human tasks · PHY physical · UTL utilities · ENV environment · MOD modularity · BLD build ·
MNT maintainability · REL reliability · SAF safety · REG regulatory · SEC security and privacy · AS assumption ·
NG non-goal · OQ open question.

---

## 1. Purpose, scope, stakeholders, definitions

### 1.1 Purpose

AutoKitchen is a built-in home kitchen machine that replaces the cook *and* the person who cleans the kitchen.
It stores food, takes in supermarket purchases, prepares, cooks, bakes, plates and serves meals, and cleans
every part of itself, with no human cooking and no human cleaning (B1, B6).

This specification defines what the system and each of its modules must achieve, in measurable terms, so that
the architect and ten module designers can work independently and reviewers can verify the result.

### 1.2 Scope

In scope: everything listed under "Parts" in the brief — ambient storage, cold storage (fridge and freezer),
preparation, cooking and baking, portioning and serving, dish washing, transport, package opening/ingestion
(versions A and B) — plus what is needed to make them work: frame and casing, utilities, control system,
user interface, recipe library, inventory management, safety.

Out of scope: see non-goals (section 12.2).

### 1.3 Stakeholders

| Stakeholder | Interest |
|-------------|----------|
| Customer (author of the brief) | Owns the requirements; decides open questions. |
| User / household members (adults) | Order meals, load groceries, take plates, handle used dishes, empty waste, refill consumables. No cooking, no cleaning. |
| Children, guests, pets | Present near the machine; must be protected; do not operate it. |
| Builder | Builds the machine from off-the-shelf parts and 3D prints with ordinary tools. |
| Maintainer (technically skilled user or technician) | Diagnoses and replaces parts from the front. |
| System architect, module designers | Design against this document. |
| Reviewers (V1–V3) | Verify designs against this document. |
| Installer (plumber/electrician) | Connects water, drain, power. |
| Authorities / insurers (indirect) | Electrical, water, fire and food-contact safety. |

### 1.4 Definitions

| Term | Definition |
|------|------------|
| **System** | The complete AutoKitchen installation in one kitchen. |
| **Module** | An independently designed, built, tested and replaceable part of the system with defined interfaces (B11). |
| **Transport system** | The module that moves transport items between all other modules and binds them together physically (B11). |
| **Transport item** | Anything the transport system carries: box, vessel, tool, dish. |
| **Box** | A rectangular, lidded, reusable plastic container in which food is stored (B3). Belongs to the *box family*: a small set of sizes on a common footprint grid. |
| **Vessel** | A container in which food is processed, mixed, cooked, baked or held between steps (the brief's "bucket", "sauce pan", "frying pan"). |
| **Tool** | A part that acts on food: cutting, peeling, mixing, stirring, turning, scooping, dosing, plating, etc. |
| **Ware** | Collective term for everything that is washed: *internal ware* (boxes, lids, vessels, tools, funnels — handled only by the machine) and *dishes* (plates and bowls the human eats from). |
| **Dish / dish set** | Plate or bowl on which food is served. The dish set is a defined set of dish types the machine can handle. |
| **Station** | A place inside a module where a transport item is handed over, held or worked on. |
| **Hand-over point** | A station at a module boundary where the transport system delivers or collects a transport item. |
| **Serving hatch** | The place with an automatic door where food, drinks and dishes are presented to the human and where the human returns used dishes (B8, DEC-6). |
| **Ingestion** | Taking purchased food into the storage system (B10). **Version A**: the machine takes packages from a container, identifies and opens them. **Version B**: the human scans the bar code and pours the contents into a funnel. |
| **Meal** | What is served to the persons at one sitting: one or more courses, each of one or more components. |
| **Component** | A separately prepared part of a course (e.g. roast, potatoes, vegetable, sauce, salad). |
| **Portion** | The amount of a component served to one person. Reference portion sizes are in CAP-004. |
| **Unit operation** | An elementary preparation step (e.g. dice, simmer, turn), listed in section 5.3. |
| **Meal corpus** | The reference list of traditional meals in `research/02-meal-corpus.md`, used to measure the coverage goal (brief: 95 %; DEC-26: 93 %). |
| **Zone F** (food contact) | Surfaces that touch food, or from which anything can drip, drain or fall into food. |
| **Zone S** (splash) | Surfaces that food, splashes, steam, condensate or dust from food can reach during normal operation or a foreseeable spill, but that are not Zone F. |
| **Zone N** (non-food) | Internal surfaces that food, splashes and steam cannot reach in normal operation (drives, electronics, utilities). |
| **Zone X** (exterior) | Outer surfaces facing the room and touched by humans. |
| **Food class R** | Raw food of animal origin that needs cooking: raw meat, poultry, fish, raw egg. Also unwashed soil-bearing produce until washed. |
| **Food class RTE** | Ready-to-eat: food that will not be heated to a safe core temperature before serving (salad, bread, cooked food, dairy). |
| **TCS food** | Food needing temperature control for safety (chilled or frozen perishables, cooked food). |
| **Danger zone** | Food temperature between 5 °C and 60 °C. |
| **Clean** | Meets the acceptance criteria of HYG-020 to HYG-025. |
| **Soiled** | A Zone F or Zone S surface that has had food contact or contamination since its last cleaning. |
| **Reference household** | 2 persons, 2 warm meals per day from the machine (1 full, 1 light); guest meals for 3–4 persons occasionally (≤ 2 per week). Basis for storage, autonomy, per-day, energy, water and lifetime figures (DEC-18). |
| **Reference meal** | Full warm meal for 2 persons: 1 course, 4 components (protein, starch, vegetable, sauce), 1.1 kg plated food. The **sizing meal** is the same for 4 persons (2.2 kg); vessels, batches, heat sources, ware and dish stock are sized for it. |
| **T_ref** | Reference time of a recipe: start to ready-to-serve for a skilled home cook in a normal kitchen, as given in the meal corpus. |
| **Human intervention** | Any unplanned action a human must take for the machine to continue (clearing a jam, removing an object, restart). Routine tasks of section 7.8 are not interventions. |
| **LRU** | Line-replaceable unit: the smallest sub-assembly exchanged in a repair. |
| **MVC** | Minimum viable configuration (MOD-030). |

### 1.5 General requirements

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| GEN-001 | The system shall produce a complete meal, from stored ingredients to plated dishes at the serving hatch, without any human action between order and pick-up. | Core goal. | M | D | B1 |
| GEN-002 | The system shall clean all of its Zone F and Zone S surfaces, all internal ware and all boxes without any human action. | "The human will not clean anything." | M | D, T | B6, B13 |
| GEN-003 | The only recurring human actions shall be those listed in section 7.8 (HUM-001 to HUM-012), at no more than the stated frequency and duration. | Makes "fully automatic" measurable. | M | D, A | B1, B6 |
| GEN-004 | The system shall consist of modules as defined in section 9, joined by the transport system. | Modularity. | M | R | B11 |
| GEN-005 | The system shall fit a domestic kitchen as defined in section 8. | Physical constraints. | M | I | B12 |
| GEN-006 | The system shall be buildable as defined in section 10. | Build constraints. | M | R | B13 |
| GEN-007 | No requirement of this document shall be met by a recurring manual step other than those in section 7.8. | Closes the loophole "the user just does X". | M | R | B1, B6 |
| GEN-008 | Every design document shall list, for each requirement allocated to it, how the requirement is met or why it is not. | Verifiability in paper phases. | M | R | drv |
| GEN-009 | Among solutions that meet the requirements comparably, the simpler one shall be chosen: fewer parts, mechanisms, actuators and interfaces, fewer food-contact surfaces. Every concept and design shall report its part and actuator count per module. | Customer decision DEC-20: simple solutions are more reliable, easier to clean, cheaper, easier to build and smaller. | M | R | B13, DEC-20 |

---

## 2. Use cases

Each use case gives actor, trigger, normal flow, result and exceptions. The requirements that follow from them
are in sections 3–10; the use cases are the end-to-end scenarios that reviewers (V2) shall walk through.

### UC-01 First installation and commissioning

* **Actors:** installer, builder/maintainer, user.
* **Flow:** (1) Modules are carried in, placed, levelled, joined, fixed to the wall. (2) Water, drain, power and
  network are connected. (3) The control system discovers all modules and runs a self-test of every axis,
  sensor, valve and heater. (4) The system calibrates hand-over points. (5) The system flushes the water paths
  and runs a full cleaning cycle of all Zone F surfaces, vessels, tools and all empty boxes. (6) The user
  creates the household profile (persons, portion sizes, allergens, dislikes), connects the app, and places the
  dish set at the serving hatch. (7) The user loads the first groceries (UC-02 or UC-03).
* **Result:** system reports "ready", inventory known.
* **Exceptions:** self-test failure → the failed module and LRU are named; other modules stay testable.

### UC-02 Grocery ingestion, version A (automatic)

* **Actor:** user. **Trigger:** user comes home with shopping.
* **Flow:** (1) User opens the ingestion container, puts in the packages as bought, in any order and
  orientation, closes it and confirms. No sorting, no unpacking. (2) The machine singulates one package,
  (3) reads the bar code, (4) looks up the product (local cache, then Internet), obtaining at least: name,
  category, net quantity, storage class (ambient/chilled/frozen), food class, allergens, package type,
  (5) determines the use-by date (read from the package, or category default), (6) selects and fetches a clean,
  dry, empty box of suitable size, or an existing box of the *same product and lot* only if HYG/FSF rules allow
  topping up, (7) DECANT lane: opens the package and transfers the contents into the box through the funnel, without
  packaging fragments; STOW lane (ING-018): places the sealed package in a box or carrier, to be opened just in
  time before its first use, (8) weighs the box, closes it, records it in the inventory, (9) sends the box to the
  right storage, chilled and frozen goods first, (10) discards the packaging into the packaging waste,
  (11) cleans funnel and opener as required by the hygiene rules before the next product, (12) repeats until
  the container is empty, then reports a summary to the user.
* **Result:** all food in boxes, inventory updated, container empty and clean.
* **Exceptions:** bar code unreadable or product unknown → package set aside in a reject area, user asked via
  the UI (identify by photo/name, or use version B). Package type not openable → reject area, untouched.
  No free box of suitable size / storage full → user informed *before* opening. Damaged or leaking package →
  reject or discard, clean. Product already expired → user informed, not stored. Glass breakage → contents
  discarded, affected path cleaned, user informed.

### UC-03 Grocery ingestion, version B (manual)

* **Actor:** user.
* **Flow:** (1) User holds the package's bar code to the scanner (or selects a product without bar code, e.g.
  loose produce, from the UI). (2) The machine looks up the product, shows what it understood, and brings a
  suitable box under the funnel. (3) The machine signals "pour". (4) The user opens the package and pours or
  places the contents into the funnel. (5) The user confirms "done" (or the machine detects the end).
  (6) The machine weighs, closes, records and stores the box; cleans the funnel as required.
* **Result/exceptions:** as UC-02. The user disposes of the packaging.

### UC-04 Meal ordering and scheduling

* **Actor:** user (smartphone app, web page, or panel on the machine).
* **Flow:** (1) The user opens the menu. The system shows the meals it can cook from current stock ("cookable
  now"), and meals that need shopping, each with time-to-ready. (2) The user chooses a meal (one or more
  courses), the number of persons (1–4), optionally the portion size per person and per-meal options (e.g.
  doneness of steak), and "as soon as possible" or a serving time (up to 7 days ahead; repeating weekly plans
  possible). (3) The system checks stock, allergens against the household profile, use-by dates and the dish
  stock, reserves the ingredients and confirms the serving time. (4) The system starts on its own at the
  right time so that the meal is ready at the serving time, including thawing ahead if needed.
  (5) The user can change or cancel without food loss until the system starts irreversible steps; the UI shows
  that deadline.
* **Extensions:** meal plan for a week → the system produces a shopping list of what is missing. The system
  proposes meals that use up food near its use-by date.
* **Exceptions:** ingredient missing/expired → alternatives or substitution offered. Not enough clean dishes →
  user asked to return dishes before the start time.

### UC-05 Cooking a meal for 1..N persons

* **Actor:** system.
* **Flow:** (1) Plan the schedule of all components backwards from the serving time, within the power budget.
  (2) Retrieve boxes; dose ingredients by mass or count into vessels; return boxes to storage within the
  cold-chain limits. (3) Wash, peel, cut, mix, form etc. (4) Cook/bake all components with stirring, turning,
  lid handling, temperature control; verify the safe core temperature where required. (5) Send each soiled
  tool, vessel and emptied box to washing as soon as it is free. (6) Hold finished components hot (or cold)
  until all are ready.
* **Result:** all components of a course are ready within a window of 5 minutes, scaled for N persons.
* **Exceptions:** see UC-12 to UC-15. Deviation detected (e.g. core temperature not reached) → extend;
  unrecoverable → discard, clean, inform user, offer alternative.

### UC-06 Portioning and serving

* **Flow:** (1) Take N clean dishes from the dish store (pre-warmed for hot food). (2) Place each component on
  each dish according to the recipe's plating layout, equal portions (or per-person sizes). (3) Check the
  result (completeness, clean rim). (4) Notify the user "meal ready". (5) Present the dishes at the serving
  hatch; open the door; the user takes them; the door closes when the hatch is empty or on timeout.
  (6) Further dishes and courses follow; the next course is released by the user ("next course") or by schedule.
* **Exceptions:** not collected → keep hot within the food-safety limits, remind; after the limit, discard and
  wash. Dish dropped/broken inside → contain, stop affected area, discard exposed food, clean, inform.

### UC-07 Dishes: return and washing

* **Actor:** user, then system (DEC-6, replacing the brief's "human loads the dish washer").
* **Flow:** (1) After eating, the user brings the used dishes, glasses and cutlery to the serving hatch as
  they are — with leftovers, not scraped, not sorted — and confirms (or the hatch detects them). (2) The
  machine takes them in, identifies each item, removes leftovers and napkins to the organic waste, washes,
  disinfects, dries and inspects them, and stores them in the dish store. (3) The hatch space is cleaned
  before food or clean dishes are presented there again. (4) The dishes are dispensed again for the next
  meal or drink.
* **Exceptions:** items that are not part of the dish set (a pan, a phone, a toy) → handed back with a
  message; broken dish → fragments contained and discarded, user informed; hatch occupied by food not yet
  collected → the user is asked to take the food first. Dish stock too low for the next planned meal →
  reminder to return dishes.

### UC-08 Consumables refill

* **Flow:** the system tracks detergent, rinse aid, softener salt, descaler, filter life, waste bags. It
  announces a refill at least 7 days before run-out. The user refills from the front without tools; the system
  confirms the new level.

### UC-09 Waste removal

* **Flow:** the system collects organic waste (peelings, trimmings, leftovers, spoiled food) and, in version A,
  packaging waste, in closed containers. It announces "empty within 24 h" at 80 % fill. The user removes the
  container or liner from the front and inserts an empty one. The waste container area is cleaned by the
  machine.

### UC-10 Maintenance and repair

* **Actors:** maintainer.
* **Flow:** (1) The system reports a fault or a due maintenance item, naming module and LRU. (2) The maintainer
  selects "service mode" for the module: the system parks mechanisms, removes or covers blades, cools hot
  parts, depressurises and drains, and disconnects power from the module. (3) The maintainer opens the front,
  exchanges the LRU with ordinary hand tools, closes. (4) The module self-tests, recalibrates, cleans the
  surfaces the human touched (Zone F/S), and rejoins.
* **Result:** system ready; no food lost in unaffected modules; cold storage kept cold throughout.

### UC-11 Self-cleaning (routine)

* **Flow:** after every use each tool, vessel, box and Zone F station is washed, disinfected as required,
  dried and returned to its clean store. Daily, all Zone S surfaces are cleaned. Weekly/monthly, deep-cleaning
  tasks run (section 7.3). The system verifies the result (HYG-026) and keeps a record.

### UC-12 Fault: power loss during cooking

* **Flow:** (1) On loss of mains, all heaters are off by nature; moving mechanisms stop and hold their load
  (no hot vessel is dropped or tipped); the state is stored. (2) On return of power, the system knows the
  outage duration, re-homes, inspects the state of each vessel, (3) resumes each component if the food-safety
  rules (FSF-030) and the recipe's tolerance allow, else discards it, (4) cleans, (5) informs the user of the
  new serving time or the loss, and of any stored food to be discarded because cold storage limits were
  exceeded.
* **Result:** no unsafe food is served; no human action needed to restart.

### UC-13 Fault: mechanical jam, dropped or mis-gripped item

* **Flow:** (1) Detection by force/position/time-out/vision. (2) Automatic recovery attempts (back off, retry,
  at most 3 times). (3) If not recovered: safe stop of the affected module; heaters to a safe state; other
  modules continue what is safe (e.g. keep food hot, keep cold storage cold); user informed with location,
  picture and instructions. (4) The user clears it from the front without tools, confirms; the system re-homes,
  cleans what was exposed, resumes or discards per FSF rules.

### UC-14 Fault: water supply or drain failure

* **Flow:** water pressure low/absent or drain blocked is detected before or during a cycle. Cooking steps
  that need no fresh water continue; steps needing water wait; washing is postponed; soiled ware is parked
  where it cannot contaminate. No overflow. If the fault outlasts the food-safety limits, affected food is
  discarded. The user is informed. After restoration the system flushes and catches up on all postponed
  cleaning before the next meal.

### UC-15 Fault: leak, fire, smoke, overheating

* **Flow:** leak → water supply shut, pumps off, user alarmed. Smoke/flame/over-temperature → all heating
  off, the cooking space closed, ventilation set to the safe state, suppression as designed, audible alarm
  and notification. Human decides on restart after inspection.

### UC-16 Long absence (holiday)

* **Flow:** (1) The user announces absence from/to (or the system detects 72 h without orders and asks).
  (2) Before departure the system proposes meals that use up perishables, lists what will expire, and on
  confirmation discards it on the last day; asks the user to empty the waste. (3) During absence: cold storage
  runs; everything else is clean, dry and idle; water paths are flushed automatically at the stagnation
  interval; expired food is discarded and its box washed as long as waste capacity allows. (4) Before return
  the system flushes water paths and runs a cleaning cycle; it offers a shopping list and meals from
  long-life stock.
* **Result:** no odour, no mould, no stagnant water, up to 90 days without a human.

### UC-17 Spoiled or expired food

* **Flow:** (1) Detection: use-by date passed; cold-chain limit exceeded; or spoilage signs found when the box
  is opened or inspected. (2) The box is never used for a meal. (3) The contents are discarded into the organic
  waste, the box goes to an intensified wash with disinfection, any station the contents touched is cleaned.
  (4) The user is informed (what, how much, why); the shopping list is updated.
* **Exceptions:** waste container full → box quarantined, closed, in storage; user asked to empty the waste.

### UC-18 Human needs food or the machine is down

* **Flow:** the user can request any box to be presented (e.g. at the serving hatch or ingestion point) to take
  food out manually. With the machine unpowered or faulty, a human can reach all stored food manually from the
  front without tools, so that food is not lost and the household is not locked out of its food.

### UC-19 Drink on request

* **Actor:** any household member (child role limited, SRV-025). **Trigger:** request on the panel or app,
  e.g. "a glass of apple juice", "a glass of milk".
* **Flow:** (1) The system checks stock and profile. (2) It fetches a clean glass and the drink's box or
  carrier; pours (SRV-022); re-closes and returns the carton or bottle. (3) It presents the glass at the hatch
  within SRV-024 and notifies. (4) The glass comes back with the next dish return (UC-07).
* **Exceptions:** out of stock → alternatives offered, shopping list updated; hatch occupied → queued.
* **Not a function (DEC-16):** snacks, bread, muesli and other breakfast goods are kept by the household outside
  the machine and are not served by it.

---

## 3. Functional requirements per module

Column "Trace": brief section or "drv". Capacity numbers referenced here are defined once, in section 6.

### 3.1 Box (common to storage, cold storage, transport, ingestion, preparation, washing)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| BOX-001 | Food shall be stored in rectangular plastic boxes. | Brief. | M | I | B3 |
| BOX-002 | The box family shall comprise at most 4 sizes, whose footprints are integer multiples or integer fractions of one base footprint, so that any mix of sizes tiles the storage grid. | Small to medium sizes, one grid, one gripper. | M | R | B3 |
| BOX-003 | The box family shall cover usable volumes from ≤ 0.3 L (spices, herbs) to ≥ 5 L (2.5 kg potatoes, a 1 kg flour bag with headroom) (est.). | Range of supermarket quantities. | M | A | B3 |
| BOX-004 | No box shall exceed a gross mass of 5 kg when filled to its rated fill. | Bounds transport payload and gripping forces. | M | A | drv |
| BOX-005 | All boxes shall present the same gripping/handling interface and the same identification feature to the transport system, regardless of size. | One transport interface. | M | R | B3, B11 |
| BOX-006 | Every box shall carry a unique machine-readable identity that survives ≥ 11 000 wash cycles and is readable at −25 °C and when wet or frosted. | Inventory integrity. | M | T | drv |
| BOX-007 | Every box shall have a closure that the machine opens and closes, that stays closed during transport, and that prevents spill of liquid contents in any transport motion and prevents entry of dust, insects and drips. A vented closure state or variant shall exist for fresh produce. | Liquids (milk), odour, cross-contamination; sealed wet produce rots. | M | T | B3, B6 |
| BOX-008 | Boxes used for food class R and for liquids shall be leak-tight: no leakage when filled with water to rated fill and tilted 30° for 60 s. | Raw-meat drip must not escape. | M | T | drv |
| BOX-009 | Box and closure shall withstand −25 °C to +85 °C, washing per HYG-021, and a drop of the filled box from 100 mm, without damage or deformation that impairs handling. | Freezer, thermal disinfection, mishandling. | M | T | B6 |
| BOX-010 | Box interior shall be fully cleanable and drainable: internal radii ≥ 6 mm (est.), no undercuts, crevices, hollow rims or threads in Zone F, and self-draining in the wash and dry orientation. | Hygienic design. | M | I, T | B6 |
| BOX-011 | Boxes shall be off-the-shelf food containers where a product meeting BOX-001 to BOX-010 exists; otherwise the deviation shall be justified. | Standard parts. | S | R | B13 |
| BOX-012 | The fill level or content mass of a box shall be determinable without opening it (e.g. by weighing), to ±5 g or ±2 %, whichever is larger. | Inventory, shopping list. | M | T | drv |
| BOX-013 | The machine shall be able to empty a box completely (residue ≤ 2 % of content mass for dry free-flowing goods, ≤ 5 % for sticky or wet goods) and to remove a partial, dosed quantity (PRP-010 ff.). | Use of contents. | M | T | B5 |
| BOX-014 | The box material shall not take up colour or odour from food so that HYG-025 is met, and shall allow the contents to be inspected by camera with the closure removed; transparent material is preferred. | Tomato and curry stain polypropylene; spoilage check. | S | T | B6 |

### 3.2 Ambient storage (STO)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| STO-001 | The storage module shall store boxes in a grid. | Brief. | M | I | B3 |
| STO-002 | The storage module shall deliver any specific single box to its exit and accept any box from its exit into a free position, under control-system command. | Brief. | M | D | B3 |
| STO-003 | Retrieval of any box to the exit shall take ≤ 30 s (mean ≤ 15 s); return likewise. | 10–20 boxes per meal must not dominate cooking time. | M | T, A | drv |
| STO-004 | Capacity shall be as CAP-020. | — | M | A | B3 |
| STO-005 | At least 55 % of the module's enclosed volume shall be box volume (gross box envelope) (est.). | "Does not waste footprint space." | S | A | B13 |
| STO-006 | The storage module shall accept every size of the box family, in a mix that can be changed without hardware modification. | Households differ. | M | D | B3 |
| STO-007 | Storage conditions: air temperature ≤ 25 °C and ≤ 5 K above room temperature, relative humidity ≤ 65 %, dark, with all other modules operating at full load. | Shelf life of dry goods; protection from cooking heat and steam. | M | T | drv |
| STO-008 | The storage module shall be closed against insects and rodents: no opening > 1 mm to the room or to wet modules, except the exit, which is closed when not in use. | Pest-proof food storage. | M | I | B6 |
| STO-009 | The module shall verify the identity of each box at the exit against the inventory and report mismatches. | Wrong ingredient = wrong or unsafe meal. | M | D | drv |
| STO-010 | The module shall keep track of box positions such that, after power loss or manual intervention, the inventory is re-established automatically (re-scan) within 10 min. | Fault recovery. | M | D | drv |
| STO-011 | A human shall be able to remove and insert any box by hand from the front, without tools, with the machine powered off. | UC-18; repair. | M | D | B13 |
| STO-012 | All surfaces inside the module that boxes touch or that a spill can reach shall be cleanable by the machine (HYG-010 ff.); a spill shall be detected and drained or contained. | "Including storage boxes and transport system." | M | R, D | B6 |
| STO-013 | The module shall detect a box that is missing, displaced, open or jammed, and shall not damage a box or mechanism on such a fault. | Robustness. | M | T | B13 |
| STO-014 | Further storage modules shall be addable to increase capacity (MOD-032). | Extension. | S | R | B11 |
| STO-015 | The module shall hold a reserve of clean, dry, empty boxes as CAP-023 and store them with the same mechanism. | Ingestion needs empty boxes. | M | A | B10 |

### 3.3 Cold storage (CLD)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| CLD-001 | Cold storage shall work like ambient storage (STO-001, -002, -006, -009 to -013, -015 apply) inside a refrigerated and a frozen compartment. | Brief. | M | R, D | B4 |
| CLD-002 | The chilled compartment shall keep all box contents at 0 °C to +4 °C, the frozen compartment at ≤ −18 °C, at 32 °C room temperature and the reference household's retrieval pattern (CAP-012). | Food safety; legal frozen-food temperature. | M | T | B4, drv |
| CLD-003 | The chilled compartment shall provide a sub-zone at 0 °C to +2 °C for raw meat and fish, with capacity as CAP-021. | Shelf life of raw meat/fish. | S | T | drv |
| CLD-004 | The exit shall be thermally closed whenever no box is passing; the open time per box passage shall be ≤ 10 s. | Brief: "exit is closed thermally". | M | T | B4 |
| CLD-005 | With the reference retrieval pattern, energy consumption of the cold storage shall not exceed that of the unmodified appliance (or an equivalent appliance of energy class D or better) by more than 25 %. | Bounds heat leak through the exit. | S | T, A | B4, drv |
| CLD-006 | Retrieval of any box to the exit shall take ≤ 45 s; return likewise. | As STO-003, allowing for the thermal closure. | M | T, A | drv |
| CLD-007 | The cold storage should be built from an off-the-shelf fridge/freezer with modifications limited to the door or exit and to internal fittings; the refrigerant circuit and cabinet insulation other than at the exit shall not be altered. | Brief ("ideally"); safety of flammable refrigerant. | S | R | B4, B13 |
| CLD-008 | No frost or ice shall build up that requires manual defrosting or impairs mechanisms; condensate and defrost water shall be drained automatically. | No human cleaning/maintenance. | M | T, R | B6 |
| CLD-009 | Mechanisms, sensors and box identification inside the compartments shall be rated for continuous operation at −25 °C (frozen) and 0 °C with condensation (chilled). | Robustness. | M | R | B13 |
| CLD-010 | Air temperature in each compartment shall be measured independently of the appliance's own thermostat at ≥ 2 points, logged at ≤ 5 min intervals, and alarmed per FSF-012. | Cold-chain evidence. | M | I, T | drv |
| CLD-011 | Food class R shall be stored so that no liquid from it can reach any other box or its handling surfaces: leak-tight boxes (BOX-008) and position below or separate from RTE food. | Cross-contamination. | M | R | B6, drv |
| CLD-012 | After loss of power with exits closed, chilled contents shall stay ≤ 7 °C for ≥ 6 h and frozen contents ≤ −9 °C for ≥ 12 h at 25 °C room temperature. | UC-12. | S | T | drv |
| CLD-013 | The cold storage shall be able to thaw frozen food under control: in the chilled compartment, scheduled so that it is thawed at the time of use. | Thawing at room temperature is unsafe; planning ahead. | M | D | drv |
| CLD-014 | The thermal exit shall not freeze shut, and shall not drip condensate onto boxes or into Zone F. | Robustness, hygiene. | M | T | B4, B6 |

### 3.4 Transport system (TRN)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| TRN-001 | The transport system shall move every type of transport item (box, vessel, tool, dish) between the hand-over points of all modules. | Brief: binds modules together. | M | D | B2, B11 |
| TRN-002 | All material flow between modules shall go through the transport system; modules shall not hand items to each other directly. | Independent module design; one interface. | M | R | B11 |
| TRN-003 | The transport system shall physically join the modules: it shall span straight layouts of 1 800 mm to 6 000 mm length and L-shaped layouts, with a length adaptable in steps of the module width grid (PHY-003) without redesign. | Brief; extension. | M | R | B11, B12 |
| TRN-004 | Payload: ≥ 5 kg for boxes and ≥ 6 kg for vessels including contents (est.), each with a safety factor ≥ 1.5 on holding force. | Heaviest box (BOX-004); 5 L pot with 4 L of contents. | M | A, T | drv, DEC-19 |
| TRN-005 | A transfer between any two hand-over points of a 3 600 mm system shall take ≤ 20 s (mean ≤ 10 s), excluding the hand-over itself of ≤ 5 s at each end. | ~100 moves per meal (est.) must fit in the time targets. | M | A, T | drv |
| TRN-006 | Open vessels filled to their rated level with water shall be transported without spilling; hot contents (> 60 °C) shall be transported either closed or inside the enclosed machine volume with no human access (SAF-020). | Scalding, soiling. | M | T | drv |
| TRN-007 | The transport system shall not drop or tip its load on power loss, emergency stop, or a single component failure. | Safety, UC-12. | M | T, A | drv |
| TRN-008 | The transport system shall serve ≥ 2 independent transfer requests in overlapping time (e.g. two carriers, or buffer positions at hand-over points that decouple modules), such that a module is not blocked for > 30 s waiting for transport during the reference meal. | One carrier must not become the bottleneck of parallel cooking. | S | A | drv |
| TRN-009 | Placement repeatability at each hand-over point shall be within the tolerance the architecture assigns to the transport side of the interface, maintained over the lifetime and re-established by automatic calibration without human measurement. | Interface robustness. | M | T | B11, B13 |
| TRN-010 | The transport system shall verify, for every move, that the item was picked (presence/mass) and placed (position), and identify it. | Fault detection. | M | D | drv |
| TRN-011 | No part of the transport system shall be Zone F. Parts of it that can be reached by spills, drips or steam are Zone S and shall be cleanable by the machine; drives and guides shall not shed lubricant or wear particles into or above open food, open vessels or open boxes. | Brief: transport must be cleanable; hygiene. | M | R, I | B6 |
| TRN-012 | Parts of the transport system that touch both class-R-soiled items and clean items (grippers) shall touch only surfaces that are outside Zone F of those items, and shall be cleaned at least daily and after any detected soiling. | Cross-contamination via gripper. | M | R | B6 |
| TRN-013 | The transport path shall pass module boundaries through openings that can be closed where the architecture requires separation (thermal, steam, wash water, pests). | Zoning. | M | R | drv |
| TRN-014 | The transport system shall continue to serve the remaining modules when one module is removed, switched off or in service mode. | Maintainability. | M | D | B11 |
| TRN-015 | A human shall be able to move the transport mechanism by hand, power off, to free a jammed item. | UC-13. | M | D | B13 |
| TRN-016 | The transport system shall not reduce the usable interior of the modules by more than 20 % of the system's enclosed volume (est.). | Footprint. | S | A | B13 |

### 3.5 Preparation (PRP)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| PRP-001 | The preparation module shall perform all unit operations marked M in section 5.3 that are allocated to preparation, and should perform those marked S. | 95 % goal. | M | D | B5 |
| PRP-002 | Tools shall be one multi-tool or several tools, exchanged automatically; no human tool change. | Brief. | M | D | B5 |
| PRP-003 | The number of distinct tool types shall be minimised and stated; every tool type shall be justified by the unit operations and the share of corpus meals it enables. | Complexity, cleaning load, cost. | M | R | B5, B13 |
| PRP-010 | The module shall transfer ingredients from a box into a vessel in a dosed quantity, for each of these ingredient forms: (a) free-flowing granular (rice, lentils, sugar, salt), (b) powders, incl. cohesive (flour, starch, cocoa), (c) small seasoning quantities (spices, dried herbs), (d) liquids (water, milk, oil, vinegar, stock), (e) viscous and pasty (mustard, tomato paste, honey, quark, jam), (f) solid fats (butter, lard), (g) discrete pieces by count or mass (potatoes, onions, eggs, meat cuts, sausages), (h) leafy and bulky (lettuce, spinach, fresh herbs), (i) sticky or wet pieces (raw meat, fish fillet, tinned fruit, pickles), (j) frozen loose goods (peas, frozen herbs), (k) long goods (spaghetti, leek, cucumber). | Brief: "how to pour the various ingredients". | M | D, T | B5 |
| PRP-011 | Dosing accuracy: quantities ≥ 50 g or mL: ±5 %; 5–50 g or mL: ±2.5 g or mL; 0.2–5 g (seasoning): ±0.2 g or ±15 %, whichever is larger. Pieces by count: exact. | Taste reproducibility; baking ratios. | M | T | drv |
| PRP-012 | The dosed mass of every ingredient shall be measured and recorded, and the inventory updated. | Inventory, recipe scaling, allergens. | M | D | drv |
| PRP-013 | The module shall transfer the contents of one vessel into another vessel, and into the cooking or baking vessel, with residue ≤ 3 % of mass for liquids and free solids and ≤ 8 % for doughs, batters and pastes. | Brief: "from one bucket to another, and from the bucket to the sauce pan". | M | T | B5 |
| PRP-014 | Transfers shall cause no spill outside Zone F/S surfaces designed to receive it, and airborne powder shall be contained within the preparation enclosure. | Cleaning load; allergen dust. | M | T | B6 |
| PRP-015 | Fresh drinking water shall be dosable into any vessel: 10 mL to 5 L, ±5 % or ±5 mL. | Most common ingredient. | M | T | drv |
| PRP-020 | Accepted raw pieces: up to 130 mm diameter and 300 mm length (potato, onion, apple, carrot, cucumber, courgette, celeriac half) (M); up to 220 mm diameter (cabbage, cauliflower, whole lettuce) (S). Meat and fish pieces up to 2.5 kg and 300 × 200 × 120 mm. | Bounds tool envelopes. | M | D | B5 |
| PRP-021 | Cutting results: slices 1–20 mm thick, dice and sticks 3–25 mm, within ±1 mm or ±20 % (whichever is larger) for ≥ 90 % of pieces by mass; fine chopping to < 3 mm (onion, herbs, garlic). | Even cooking, appearance. | M | T | B5 |
| PRP-022 | Peeling: ≤ 5 % of the surface with residual peel; peel loss ≤ 25 % of the mass for potatoes and carrots (est.). | Quality; waste. | M | T | B5 |
| PRP-023 | Throughput: wash, peel and cut 1.0 kg of potatoes in ≤ 7 min; cut 0.7 kg of mixed vegetables in ≤ 4 min; knead 1.2 kg of dough; mix 0.8 kg of minced-meat mass; form 8 patties in ≤ 4 min. | Time targets for 4 persons. | M | T | drv, DEC-19 |
| PRP-024 | The module shall perform the forming and assembling operations of MEAL-018 (section 5.3, UO-40 to UO-49, UO-90 to UO-94) with piece-mass variation ≤ ±10 %. | Frikadellen and Rouladen are named in the brief; the shaping cluster is 15 % of the corpus. | M | T | B5 |
| PRP-030 | Every tool and vessel shall be completely cleanable by the machine (HYG-030 ff.) and shall be sent to washing after use without human action. | Brief: "especially for these tools". | M | D, T | B6 |
| PRP-031 | The module shall hold enough clean tools and vessels to prepare the sizing meal for 4 persons without waiting for a wash cycle (CAP-030). | Time target. | M | A | drv |
| PRP-032 | Food class R shall be prepared physically or temporally separated from RTE food as FSF-040 requires. | Cross-contamination. | M | R | B6 |
| PRP-033 | Trimmings, peel, shells and other preparation waste shall be removed to the organic waste without human action and without passing over open food. | No human cleaning. | M | D | B6 |
| PRP-034 | Cutting edges shall keep the performance of PRP-021 for ≥ 1 year of reference use without sharpening or exchange by a human, or be resharpened by the machine. | Human does not maintain weekly. | M | A, T | B13 |
| PRP-035 | The module shall detect tool breakage or loss of a tool part (e.g. blade fragment) and shall then discard the affected food. | Foreign bodies. | M | A, D | drv |
| PRP-036 | The module shall be able to hold prepared ingredients and intermediate products at ≤ 7 °C (marinating, dough resting, prepared salad, set desserts) for up to 24 h, e.g. by returning them in a closed vessel or box to cold storage. | Multi-stage recipes; FSF limits. | M | D | drv |
| PRP-037 | The module shall be able to hold dough at 28–35 °C for proofing. | Yeast dough: 11 corpus meals, no workaround. | M | D | B5 |
| PRP-038 | Mixing, whipping and kneading shall work over the full quantity range of 1–4 persons and of one cake or loaf: from 1 egg white (30 mL) or 100 g of dough up to 6 egg whites, 1.2 kg of dough (rising to about 3.5 L), 0.8 kg of salad leaves (≈ 3.5 L) and 0.8 kg of mince mass; working volume of the largest mixing vessel ≥ 5 L (nominal ≥ 6 L). | Corpus 6.3 scaled to 4; a 26 cm cake or a 750 g-flour loaf does not scale down. | M | T | B5, B8, DEC-19 |
| PRP-039 | **Generic peeling, stoning, deseeding and coring** is a core function (DEC-25): the machine shall remove skin, stones, seeds and cores from at least potato, carrot, celeriac, kohlrabi, beetroot, pumpkin/squash, ginger, white asparagus, cucumber, courgette, apple, pear, banana, avocado, mango, kiwi, orange, lemon (peel and segments), bell pepper, chili, tomato (core), peach, plum, apricot; cherries and pineapple: S. Generic mechanisms shall be preferred: the design shall state how many distinct peeling/coring mechanisms it needs for this list (target ≤ 3) and justify every single-purpose device. Results: residual skin ≤ 5 % of the surface; no stone or seed fragment > 2 mm left; flesh loss ≤ 25 % for smooth produce, ≤ 30 % for knobbly produce (est.). | Customer decision: this is the same task for all produce; dishes such as guacamole, banana bread, fruit salad, apple cake, mango and avocado salads are preparable targets. | M | T, R | B5, DEC-25 |

### 3.6 Cooking and baking (COK)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| COK-001 | The cooking module shall perform all thermal unit operations marked M in section 5.3, and should perform those marked S. | 95 % goal. | M | D | B7 |
| COK-002 | Number of simultaneously heated cooking positions: ≥ 3 (M), 4 (S), of which ≥ 2 with ≥ 3 kW, plus 1 baking/roasting cavity and warm-holding usable at the same time (within UTL-011). | Corpus 4.9: single dishes need up to 3 heat sources; the 5 of 15 menus that need 4 (e.g. roast + dumplings + red cabbage + gravy) can be run with 3 positions for ≤ 4 persons by holding one finished component warm (COK-017) — pan batches are shorter at 4 persons. | M | I, A | B7, B8, DEC-19 |
| COK-003 | Cooking positions: controlled vessel-base temperature 40–260 °C; content temperature control 40–100 °C within ±3 K (simmering, poaching, holding, melting, water-bath-like heat at 65–80 °C). | Searing to hollandaise (corpus 4.9). | M | T | B7 |
| COK-004 | Heating performance: bring 2 L of water from 15 °C to 95 °C in ≤ 6 min, and 4 L in ≤ 11 min, in one vessel, while one further cooking position and the baking cavity are heating. | Pasta for 4 (400 g in 4 L) and potato water are the time drivers; one phase (≈ 3.4 kW) per fast position. | M | T | drv, DEC-1, DEC-19 |
| COK-005 | Searing: a vessel base shall reach 220 °C in ≤ 5 min and recover to ≥ 180 °C within 60 s after 600 g of meat at 4 °C is added. | Browning instead of stewing (steak, Rouladen, roast). | M | T | B5, B7 |
| COK-006 | Baking/roasting cavity: 30–250 °C (M), to 280 °C (S), ±10 K at the centre; top heat for gratinating; usable volume ≥ 35 L with space for a tray of ≥ 0.09 m² (e.g. 370 × 250 mm, 400 × 300 mm or Gastronorm 2/3), a 26 cm springform, a roast or bird of 2.5 kg (duck), or a 4 L lidded braising vessel (≈ 290 × 220 × 100 mm). | Corpus 4.9 and 6.3 scaled to 4 persons: 57 meals bake or roast; a 26 cm cake and a whole chicken or duck do not scale down; only pizza and Flammkuchen want more than 250 °C. | M | T, I | B7, DEC-19 |
| COK-007 | The cavity should offer controlled humidity (steam injection or steam baking up to 100 °C). | Bread crust, gentle roasting, regeneration, steaming in bulk. | S | D | B7 |
| COK-008 | Every cooking position shall be able to stir or agitate the contents automatically, including scraping the bottom and wall so that thickened sauces, porridge, risotto and roux do not burn on; stirring speed and pattern selectable per recipe step. | Brief: "cooking, including stirring". | M | D, T | B2 |
| COK-009 | The module shall cook individual pieces (steak, schnitzel, Frikadelle, fish fillet, pancake, fried egg) with browning on both sides as the recipe demands — by turning them or by heating from both sides — without breaking them: ≥ 95 % of pieces intact. | Pan-fried dishes are a large share of the corpus; the method is left open. | M | T | B5 |
| COK-010 | The module shall put on and take off lids, and add ingredients to a hot vessel at any time during cooking (deglazing, seasoning, staged addition). | Braising, sauces. | M | D | B5 |
| COK-011 | The module shall drain cooking water from solids (pasta, potatoes, vegetables) with ≤ 3 % of the water remaining, and shall be able to retain a measured part of the liquid. | Boiled sides. | M | T | B5 |
| COK-012 | The module shall separate fat, liquid and solids as the M unit operations require (pour off frying fat, strain a sauce). | Sauces, gravy. | S | D | B5 |
| COK-013 | The module shall measure the core temperature of pieces ≥ 20 mm thick to ±1 K and use it to end the cooking step. | Food safety (FSF-020); doneness of steak and roast. | M | T | drv |
| COK-014 | The module shall measure the mass of each vessel's contents during cooking to ±10 g. | Reduction, evaporation compensation, dosing check. | S | T | drv |
| COK-015 | The module shall detect boil-over, dry-boiling and burning (e.g. by temperature, mass, humidity, vision) and react before food is spoiled or a hazard arises. | Unattended cooking. | M | T | drv |
| COK-016 | Cooking vessels (corpus 6.3 scaled to 4 persons), each also working at its 1-person minimum fill: sauce 0.15 L to 0.5 L content (1 L nominal); rice 0.2–1.1 L (1.5 L nominal); potatoes/vegetables up to 1.0 kg + 1 L water (3 L nominal); soups and stews up to 2 L content (3 L nominal; hot blending needs 40 % headspace); pasta for 4 in ≥ 3 L of water (5 L nominal; 6 L: S); a lidded braising vessel of ≥ 4 L usable on a cooking position and in the cavity (8 Rouladen, 1.2 kg + 0.8 L liquid); a frying surface of ≥ 600 cm² (28 cm: 4 patties or 2 cutlets per batch) (M), ≥ 800 cm² (32 cm, fried potatoes for 4 in one batch) (S). Pan-fried components for 4 may be cooked in ≤ 2 batches with warm-holding (COK-017). Asparagus and long pasta need ≥ 250 mm inner length. | DEC-19. | M | A | B8, DEC-19 |
| COK-017 | The module shall keep finished components at ≥ 65 °C without further cooking them noticeably, for up to 30 min, and cold components at ≤ 7 °C. | All components ready together; late pick-up. | M | T | B8 |
| COK-018 | Steam, fumes and grease aerosol from cooking shall be captured inside the machine (ENV-010 ff.). | Home environment; casing cleaning. | M | T | B6, drv |
| COK-019 | All surfaces of the cooking positions and the cavity, including burnt-on residue, shall be cleaned by the machine (HYG-033). | Brief. | M | T | B6 |
| COK-020 | Off-the-shelf cooking and baking equipment should be used where it meets the requirements. A bought oven may be modified — door, mounting orientation, controls, access openings — where the machine's access requires it; the design shall list every modification and prefer the solution with fewer modifications. The cooking positions shall be built from controllable OEM or commercial induction modules, not from a finished consumer hob. | Standard parts; DEC-24; consumer hobs cannot be started remotely (DEC-5). | M | R | B7, B13, DEC-5, DEC-24 |
| COK-021 | The quantity of free fat or oil in any vessel shall be limited to 250 mL (est.). | Fire load for unattended cooking; excludes deep frying (section 5.4). | M | R | drv |
| COK-022 | The module shall cool a cooked component from 65 °C to ≤ 10 °C within 120 min when the recipe needs it cold (potato salad, pudding, cooked components of salads). | Food safety; cold dishes. | S | T | drv |
| COK-023 | Any off-the-shelf appliance integrated into the machine (oven, dish washer, fridge, induction module) shall be started, controlled and monitored by the control system without a human action at the appliance (no "remote start" button to be pressed), and without dependence on a manufacturer cloud service — if necessary by modifying its controls (COK-020, DEC-24). | Consumer appliances often require a manual remote-start confirmation and a cloud API (`research/05`); both defeat autonomy and CTL-012. | M | D | B1, drv |

### 3.7 Portioning and serving (SRV)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SRV-001 | The module shall place cooked food on dishes for 1 to 4 persons per meal. | Brief; DEC-19. | M | D | B8, DEC-19 |
| SRV-002 | It shall portion each of these forms: (a) single pieces (steak, schnitzel, dumpling, roulade), (b) loose solids (potatoes, vegetables, rice, pasta, salad), (c) long pasta, (d) mash and purées, (e) soups and stews, (f) sauces and gravy, (g) slices carved from a cooked roast, (h) slices/pieces of baked goods (gratin, lasagne, cake), (i) garnish (chopped herbs, a lemon wedge). | Coverage of corpus meals. | M | D | B8 |
| SRV-003 | Portion equality: each person's portion of each component within ±10 % of its target mass (pieces: equal count, and the machine shall distribute unequal pieces so that totals are within ±15 %). | "Portion the food on the dishes for each person." | M | T | B8 |
| SRV-004 | Per-person portion sizes (at least S/M/L = 0.7/1.0/1.3 of the reference portion) shall be selectable. | Children and adults at one table. | S | D | B8 |
| SRV-005 | Presentation ("nicely presented") shall meet all of: (a) each component in its zone of the recipe's plating layout, position within ±15 mm; (b) components that the layout keeps apart do not touch or run into each other; (c) the outer 20 mm of the plate rim free of food, drips and smears > 3 mm; (d) sauce placed as specified (over, beside or under); (e) no component visibly broken up, burnt or dried out; (f) garnish placed where specified. | Makes the brief's requirement testable. | M | T (photo check against layout) | B8 |
| SRV-006 | In a blind rating by ≥ 5 persons of 10 different plated corpus meals, the mean score for appearance shall be ≥ 3.5 on a 5-point scale where 3 = "as a careful home cook would serve it". | Subjective acceptance. | S | T | B8 |
| SRV-007 | Hot food shall be ≥ 65 °C at the core when the dish arrives at the hatch; cold food ≤ 10 °C; hot and cold components that the recipe serves together shall be plated last-minute. | Eating quality, food safety. | M | T | B8, drv |
| SRV-008 | Dishes for hot food shall be pre-warmed to 40–60 °C. | Food stays warm; grip area not scalding (SAF-021). | S | T | B8 |
| SRV-009 | All dishes of one course for up to 4 persons shall be at the hatch within 3 min from the first to the last. | Family eats together. | M | T | B8 |
| SRV-010 | The serving hatch shall be at a fixed place, with an automatically operated door, and shall present the dishes so that an adult standing in front can take them with one hand each; presentation height 850–1 300 mm above the floor. | Brief; ergonomics. | M | I | B8 |
| SRV-011 | The hatch shall present ≥ 2 dishes at a time (M), 4 (S). | Carrying two plates at once; serving time. | M | I | B8 |
| SRV-012 | The hatch door shall be closed except while dishes are being presented or returned, and shall separate the room from the machine interior (heat, steam, noise, odour, access). | Safety, hygiene. | M | I | B8 |
| SRV-013 | The system shall announce "ready" at the machine (light and sound, mutable) and on the app, and shall detect removal of each dish. | UX. | M | D | B8 |
| SRV-014 | The serving hatch shall accept used dishes from the human at any time when no food is presented in it: a whole 2-course meal for 4 (SRV-016 items) in ≤ 2 loads, placed in any order and orientation that a careless adult would use (stacked plates, cutlery on the plates, glasses standing), with leftovers on them. | DEC-6. | M | D | B9, DEC-6 |
| SRV-015 | The system shall identify every returned item; items that are not part of the dish set shall be detected with ≥ 99 % probability and handed back without damage; chipped or cracked dishes shall be detected with ≥ 95 % probability and withdrawn from use with a notification. | Returns are an uncontrolled input; broken dishes are a foreign-body hazard. | M | T | B9, DEC-6 |
| SRV-016 | The dish set shall consist of commercially available items: flat plates (Ø 260–280 mm), deep plates or bowls (≥ 0.5 L), small plates or bowls, drinking glasses (200–400 mL), and cutlery sets (knife, fork, spoon, dessert spoon). The machine dispenses a cutlery set with each plated main course (S) or on request (M). | Courses of traditional meals; drinks (SRV-022); DEC-6. | M | I | B8, B13, DEC-6 |
| SRV-027 | Returned used dishes shall not contaminate food or clean dishes presented later: the hatch surfaces touched by returned items shall be cleaned (HYG-035) before the next presentation, or return and presentation shall use separate surfaces. | Dirty and clean flows meet at the hatch (HYG-005). | M | R, T | B6, DEC-6 |
| SRV-022 | On request (app, panel, voice optional) the system shall pour a drink that it stores — juice, milk, water from the tap, other still drinks; carbonated drinks (C) — from its carton, bottle or the water supply into a glass of the dish set and present it at the hatch: 100–400 mL ±10 %, chilled drinks ≤ 8 °C at the hatch, no drips on the outside of the glass, and the carton or bottle exterior not touching the glass rim. Opened cartons and bottles are re-closed and returned to storage. | DEC-13, kept by DEC-17 for drinks the machine stores; optional because table drinks may live in a separate fridge. | S | D, T | DEC-13, DEC-17 |
| SRV-024 | Response time of SRV-022: the glass at the hatch ≤ 60 s after the request when the machine is idle, ≤ 3 min while a meal is in progress; a running meal shall not be delayed by more than 2 min. | A drink that takes ten minutes is not requested twice. | S | T, A | DEC-13 |
| SRV-025 | Drink requests shall respect the household profile (allergens) and the user role (UI-012: e.g. a daily limit of juice for children). | Allergen safety; parents' control. | S | D | DEC-13 |
| SRV-026 | Drinks are recorded in the inventory like any other retrieval; the time outside the cold chain of the box follows FSF-013. | Inventory and food safety. | M | D | DEC-13 |
| SRV-017 | The dish store capacity shall be as CAP-031. | — | M | A | drv |
| SRV-018 | Food in shared serving vessels ("family style": one bowl of potatoes, one of vegetables, to be passed at the table) shall be offered as an alternative to individual plating. | Common at family tables; large meals. | C | D | B8 |
| SRV-019 | All portioning tools and surfaces are Zone F and shall be cleaned as HYG-030 ff.; the hatch space is Zone S and shall be cleaned daily and after any spill. | Brief. | M | R, T | B6 |
| SRV-020 | Food not collected shall be handled as FSF-032. | Food safety. | M | D | drv |
| SRV-021 | Leftovers remaining in vessels after serving shall be discarded to the organic waste by default (M). Optionally they shall be cooled (COK-022) and stored in a box for a later meal within the FSF limits, offered in the menu as "leftovers" (S). | Customer decision: discard; store if easy. | M | D | DEC-12 |

### 3.8 Washing and cleaning module (WSH)

Acceptance criteria and frequencies are in section 7; this table states the functions of the module.

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| WSH-001 | The system shall take back used dishes, glasses and cutlery of the dish set at the serving hatch, remove leftovers and disposable items (napkins, bones) to the organic waste, wash, disinfect, dry and inspect them, and store them in the dish store, without human action. | Customer decision: the human only brings used dishes back to the hatch. | M | D, T | B9, DEC-6 |
| WSH-002 | Dish washing capacity: the used dish set of a 2-course meal for 4 persons (8 plates or bowls, 4 small plates, 4 glasses, 4 cutlery sets) shall be clean, dry and back in the dish store within 90 min of its return (M), 60 min (S), without delaying the next meal. | Dishes are needed again at the next meal. | M | A, T | B9, DEC-6, DEC-19 |
| WSH-003 | Dishes, glasses and cutlery are Zone F and shall meet HYG-020 to HYG-024, with thermal disinfection (HYG-021) at every wash. | They come back from the table with saliva and leftovers and go out again with food. | M | T | B6, DEC-6 |
| WSH-004 | The system shall wash, disinfect (where HYG requires) and dry all internal ware — boxes, closures, vessels, lids, tools, funnels, removable Zone F parts — without human action, fed and emptied by the transport system. | Brief. | M | D, T | B6 |
| WSH-005 | Internal-ware washing capacity and cycle time shall be such that (a) the sizing meal for 4 is never delayed by lack of clean ware, (b) all ware of a meal is clean and dry within 90 min after serving (M), 45 min (S), (c) empty boxes from ingestion and use are washed within 12 h. | Turn-round. | M | A, T | drv |
| WSH-006 | The washing shall remove burnt-on and dried-on residue from cooking vessels (test soil: milk burnt on at 200 °C; egg; starch dried for 2 h; minced-meat fond) to the criteria of HYG-020. | Pots are the hardest item. | M | T | B6 |
| WSH-007 | Washed ware shall be dry (HYG-024) before it is stored or used for dry ingredients. | Mould, clumping, microbial growth. | M | T | B6 |
| WSH-008 | The module shall clean in place those Zone F and Zone S surfaces of all modules that cannot be carried to the washer, or each module shall do so itself by the means defined in the architecture (one system-wide cleaning concept). | Casing, stations, funnels, hatch. | M | R, D | B6 |
| WSH-009 | The module shall supply the wash media (heated water, detergent solution, rinse water, drying air) that other modules need for cleaning in place, through the utility interface (MOD-013). | One detergent store, one heater. | S | R | B6, B11 |
| WSH-010 | Detergents and rinse aids shall be commercially available household or food-service products; dosing shall be automatic from store containers as CAP-040. | Standard parts; no per-cycle human dosing. | M | I | B13 |
| WSH-011 | The final rinse of all Zone F surfaces shall be with water of drinking quality, and leave no detergent residue above HYG-023. | Chemical food safety. | M | T | drv |
| WSH-012 | Food residue shall be separated from wash water so that the drain is not blocked: solids > 1 mm (est.) retained and moved to the organic waste automatically; the filter shall be self-cleaning. | Household dish washers need manual filter cleaning — not allowed here. | M | D, T | B6 |
| WSH-013 | The module shall clean itself (wash chamber, spray system, sump, filters, door seals) and shall not develop odour, biofilm or scale within the lifetime (HYG-050 ff.). | Self-cleaning of all parts. | M | T, A | B6, B13 |
| WSH-014 | Off-the-shelf dish washer(s) should be used where they meet the requirements. | Standard parts. | S | R | B13 |
| WSH-015 | The system shall collect organic waste and (version A) packaging waste in closed, odour-tight containers as CAP-041 and HUM-003. | Waste removal. | M | I | drv |
| WSH-016 | Used frying fat and oil > 30 mL shall be collected with the organic waste or separately, not discharged into the drain. | Drain blockage; waste-water rules. | M | R | drv |

### 3.9 Ingestion — common to versions A and B (ING)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| ING-001 | Two versions of the ingestion module shall be designed: A (automatic, INA) and B (manual, INB). They shall be interchangeable at the same module interface, and B shall also be usable alongside A as its fallback. | Brief: "Make those 2 versions". | M | R | B10 |
| ING-002 | The module shall read EAN-13, EAN-8, UPC-A and UPC-E bar codes (M) and GS1 DataBar, GS1 DataMatrix and GS1 QR codes (S). | Brief; retail is moving to 2D codes that also carry the expiry date. | M | T | B10 |
| ING-003 | The module shall look up the product by its number on the Internet and obtain at least: product name, category, net quantity, and, where available, ingredients, allergens, nutrition, storage instructions and package type. | Brief: "what is inside". | M | D | B10 |
| ING-004 | Looked-up products shall be cached locally; a product ingested once shall be recognised without Internet. | Robustness, privacy. | M | D | drv |
| ING-005 | Where the look-up gives no or incomplete data, the user shall be asked once through the UI (name/category or photo-based proposal), and the answer stored for that product number. | Databases are incomplete. | M | D | B10 |
| ING-006 | The module shall map each product to: an ingredient of the recipe library, a storage class (ambient / chilled / frozen), a food class (R / RTE / other), allergens, a shelf life after opening, and a box size. | The inventory must be usable by recipes and by the hygiene rules. | M | D | drv |
| ING-007 | The use-by or best-before date shall be recorded for every ingested product: read automatically from a 2D code or the printed date (S), or entered/confirmed by the user, or else set to a conservative default for the category. | Spoiled-food handling. | M | D | drv |
| ING-008 | Because the package is opened at ingestion, the inventory shall apply the *shelf life after opening* from the moment of ingestion (FSF-050). | Opening ends the shelf life printed on the package. | M | R | B10, drv |
| ING-009 | Contents shall fall or be guided into a storage box through a funnel. | Brief. | M | I | B10 |
| ING-010 | The net mass transferred into the box shall be measured to ±5 g or ±2 % and compared with the declared net quantity; deviations > 10 % shall be flagged. | Detects incomplete emptying and wrong identification. | M | T | drv |
| ING-011 | One product per box. Topping up a box that still holds older contents of the same product is permitted only for ambient dry goods and only if the older remainder stays identifiable for FIFO use or is used first; never for chilled, frozen or class R goods. | Traceability, shelf life. | M | R | drv |
| ING-012 | A product whose quantity exceeds one box shall be split over several boxes automatically. | 2.5 kg potatoes, 1.5 kg flour. | M | D | B10 |
| ING-013 | Funnel and all Zone F parts shall be cleaned and dried by the machine: before a product with a different allergen profile, after every class R product, after every wet or sticky product, and at the end of every ingestion session (HYG-031). | Cross-contact; dry goods must not meet a wet funnel. | M | D, T | B6 |
| ING-014 | Fragile products (eggs, soft fruit, tomatoes, biscuits) shall arrive in the box with ≤ 2 % damaged by count or mass. | A funnel drop breaks eggs. | M | T | B10 |
| ING-015 | The module shall accept food without a bar code (loose produce, bakery, butcher's counter) by selection in the UI (M) and by camera-based proposal (S). | A large share of fresh food. | M | D | B10 |
| ING-016 | Chilled and frozen products shall be in cold storage within the limits of FSF-011 after being handed to the machine. | Cold chain. | M | T, A | drv |
| ING-017 | Before accepting a product, the module shall check that a clean, dry box of suitable size and a storage position of the right class are available, and otherwise refuse the product unopened. | No opened food without a place to go. | M | D | drv |
| ING-018 | The ingestion shall have two lanes, chosen per product by the control system. **DECANT** (open now, contents through the funnel into a box — the brief's process) for dry, ambient-stable, free-flowing goods and for other products whose shelf life is not shortened by opening (produce, frozen loose goods). **STOW** for products whose shelf life collapses on opening (tins, jars, bottles, beverage cartons, tubs, vacuum and modified-atmosphere packs): scanned, weighed, registered and stored sealed inside a box or carrier of the box family, and opened by the machine's package-opening mechanism just in time before preparation, with the same requirements on residue, fragments and hygiene (INA-007, INA-008, INA-014). In version B the user places the sealed package into the presented box instead of pouring. | Opening at ingestion turns a shelf life of months or years into days (UHT milk 3–7 days, tins 2–4 days, vacuum meat 1–3 days; `research/07`); without STOW, CAP-010 cannot be met. Project ruling, pending customer objection (OQ-05). | M | R, D | B10, DEC-3 |
| ING-019 | Ingestion shall be possible while no meal is in progress (M) and during cooking without delaying the meal by more than 2 min (S). | Shared transport and washing resources. | M | D | drv |
| ING-020 | The outside of packages stored sealed (STOW) shall not contaminate Zone F: either it is cleaned before storage, or the carrier/box that held it is treated as soiled and the opening mechanism as class R contact (HYG-031). | Supermarket packaging is not clean. | M | R | B6, DEC-3 |
| ING-021 | Just-in-time opening of stowed packages shall be available in every configuration, including the MVC with ingestion version B; the opening mechanism may be shared between ingestion and preparation. | STOW is useless without opening at use. | M | R | B10, DEC-3 |
| ING-022 | A guest shop of 20 items (CAP-013) shall be ingested with version A in ≤ 20 min machine time (user ≤ 2 min), with version B in ≤ 10 min user time, chilled items within FSF-011. | Shopping shortly before a guest meal. | M | T, A | B10, DEC-18 |

### 3.10 Ingestion version A — automatic (INA)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| INA-001 | The user shall place packages as bought into a container; the machine shall pick one package at a time. Minimum (M): the user puts the items in one by one, in any orientation, ≤ 3 s per item, without sorting. Target (S): a jumbled pile tipped in from the shopping bag. | Brief. Picking deformable packages from a jumbled pile is the largest technical risk of version A (`research/07`), hence the staged requirement (OQ-06). | M | D | B10 |
| INA-002 | Container capacity: ≥ 40 L and ≥ 20 packages and ≥ 15 kg per load (est.). | About half of a weekly shop per load; chilled goods are not left waiting long. | M | I | B10 |
| INA-003 | Package envelope: from 40 × 30 × 10 mm to 350 × 250 × 150 mm; mass 20 g to 3 kg (est.). | Spice sachet to 2.5 kg potato bag, 1.5 L bottle, 500 g spaghetti. | M | T | B10 |
| INA-004 | The machine shall find and read the bar code on any face of the package, including curved, glossy, crumpled and frosted surfaces, with a first-pass read rate ≥ 95 % on the reference basket (INA-006). | Brief. | M | T | B10 |
| INA-005 | The machine shall open these package types and transfer their contents, at ingestion or at first use as ING-018 decides. (M): paper bag; plastic film bag and pouch, dry and frozen; folding carton with or without inner bag; net bag; beverage carton; tin can; tray with film lid; tub/cup with peel-off lid; vacuum pack. (S): glass jar with twist-off lid; bottle with screw cap; tube; foil-wrapped block (butter); egg carton; clamshell punnet; flow-wrapped produce; shrink-wrapped multi-pack. | Brief: "cuts open the package". M types cover about 60 % of items and 55 % of mass of a weekly shop, M + S about 85 % (`research/07`, est.); the rest is loose produce needing no opening. | M | T | B10 |
| INA-006 | On a reference basket of 100 items representative of a weekly household shop (defined from `research/07-ingestion-packaging.md`, table 1.2, excluding drinks and non-ingredients), ≥ 75 % of items shall be ingested without human help (M), ≥ 90 % (S). A package shall be accepted only if the machine can also open it later; all others shall be rejected *unopened and undamaged*. | Measurable success rate; graceful fallback to version B. | M | T | B10 |
| INA-007 | Residue left in the package: ≤ 2 % of net mass for dry free-flowing goods, ≤ 5 % for pieces and frozen goods, ≤ 10 % for viscous goods (est.). | Food waste; inventory accuracy. | M | T | B10 |
| INA-008 | No packaging material shall enter the box: no fragment > 2 mm in 100 packages of each M type; absorbent pads, desiccant sachets, clips, labels and inner wrappers shall be detected and kept out. | Foreign bodies. | M | T | drv |
| INA-009 | Throughput: mean ≤ 60 s per package including storage and required cleaning (M), ≤ 40 s (S); a full container load in ≤ 25 min. | 40–60 packages per weekly shop. | M | T, A | B10 |
| INA-010 | Within a load, packages identified as frozen shall be processed first, then chilled, then ambient, as far as they can be reached; the user shall be told to load frozen and chilled goods in a separate first load. | Cold chain (FSF-011). | M | D | drv |
| INA-011 | Rejected packages shall be placed in a reject area of ≥ 10 L reachable by the user, and listed in the UI with the reason. | Fallback. | M | D | B10 |
| INA-012 | Emptied packaging shall be moved to the packaging waste without dripping onto Zone F or clean boxes; the packaging waste shall hold ≥ 1 load (compacting permitted). | Waste handling. | M | D | drv |
| INA-013 | The container interior and the package handling and opening mechanisms are Zone S (outside of packages is dirty) and Zone F (opening tools, funnel) and shall be cleaned by the machine (HYG-031). | Package exteriors carry dirt and germs; a leaking package soils the container. | M | D | B6 |
| INA-014 | Opening tools shall not contaminate the food with the package's outside: the cut shall be made so that contents do not run over the outer surface where avoidable, and cutting tools shall be cleaned per ING-013. | Hygiene. | M | R | B6 |
| INA-015 | The container shall be closed by an interlocked lid or door while the machine operates in it (SAF-030). | Cutting mechanism next to human hands. | M | T | drv |

### 3.11 Ingestion version B — manual (INB)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| INB-001 | The user shall scan the bar code at a scanner on the machine (M) or with the smartphone app (S). | Brief. | M | D | B10 |
| INB-002 | The machine shall confirm the recognised product and the expected quantity on a display visible from the pouring position within 3 s of the scan. | Avoids wrong assignments. | M | T | B10 |
| INB-003 | A suitable box shall be under the funnel and "pour now" signalled within 15 s of the scan (mean ≤ 8 s). | The user stands waiting with the package in hand. | M | T | B10 |
| INB-004 | The funnel inlet shall be 900–1 200 mm above the floor, with a free opening of ≥ 200 × 200 mm, and accept single items up to Ø 220 mm and up to 350 mm length. | Pouring ergonomics; cauliflower, cucumber. | M | I | B10 |
| INB-005 | The funnel shall accept all ingredient forms of PRP-010 without bridging or sticking such that the user has to push by hand: ≥ 98 % of the mass shall reach the box on its own. | Human does not poke in the funnel. | M | T | B10 |
| INB-006 | The end of pouring shall be confirmed by the user (M) or detected automatically (S); the box shall then be stored and the next scan be possible within 10 s (without funnel cleaning) or 60 s (with). | Throughput ≥ 3 products/min for dry goods. | M | T | B10 |
| INB-007 | Overfill shall be prevented: the machine shall signal "stop" before the box is full and change to a further box within 10 s. | No spill. | M | D | B10 |
| INB-008 | The funnel shall be closed by a cover when not in use; no moving part shall be reachable through the funnel (SAF-031). | Safety, pests, dust. | M | T | drv |
| INB-009 | The funnel area shall contain spills and powder dust; the inlet surround that the user can soil is Zone S and cleaned by the machine. | No human cleaning. | M | D | B6 |
| INB-010 | Version B shall fit in a module width of ≤ 300 mm or be integrated into another module's front without adding width. | Footprint; B is the minimum configuration. | S | I | B13 |

### 3.12 Control system (CTL)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| CTL-001 | The control system shall keep an inventory per box: identity, size, position, product, ingredient mapping, net mass, ingestion date, use-by date, storage class, food class, allergens, lot/purchase, cleaning state, and cumulative time outside the cold chain. | Basis of ordering, food safety, shopping list. | M | D | drv |
| CTL-002 | It shall hold a recipe library covering the meal corpus (section 5) in a machine-executable recipe format built from the unit operations of section 5.3, with quantities per person and scaling rules for 1–4 persons. | 95 % goal. | M | R, D | B1, B5 |
| CTL-003 | Recipes shall be data, not program code: adding or changing a recipe shall need no software change. | Extensibility. | M | R | drv |
| CTL-004 | Users should be able to add their own recipes from the supported unit operations; the system shall check them against the safety and capability limits before accepting. | Family recipes. | S | D | B1 |
| CTL-005 | The control system shall schedule all steps of a meal backwards from the serving time across all modules, respecting: resource availability, the electrical power budget (UTL-011), food-safety time limits, noise mode, and readiness of all components of a course within 5 min of each other. | UC-05. | M | A, D | B8 |
| CTL-006 | It shall predict the ready time when the order is placed with an error ≤ ±5 min or ±10 %, whichever is larger, and update it during cooking. | UX. | M | T | drv |
| CTL-007 | It shall close the loop on the process with sensors (mass, temperature, core temperature, state detection) rather than executing timed steps blindly, and adapt times to measured quantities and temperatures. | Ingredient variability; robustness. | M | R | drv |
| CTL-008 | It shall enforce the hygiene and food-safety rules of section 7 automatically (cleaning state of every ware item and station, cold-chain timers, separation rules, use-by dates) and refuse any step that would violate them. | No human supervision. | M | D, R | B6 |
| CTL-009 | It shall record for every meal: ingredients and boxes used, temperatures reached, holding times, cleaning cycles with their verification result; records kept ≥ 12 months, readable and exportable by the user. | Traceability, fault finding. | M | I | drv |
| CTL-010 | It shall detect faults, attempt automatic recovery, and otherwise bring the affected module into a safe state while other modules continue safe activities (UC-12 to UC-15). | Fault recovery. | M | D | B13 |
| CTL-011 | The state needed for recovery shall be stored non-volatile such that after power loss at any moment the system restarts without human action and knows the outage duration. | UC-12. | M | T | drv |
| CTL-012 | The system shall cook, clean and keep its inventory without an Internet connection; only product look-up of unknown products, remote UI access from outside the home, and updates need the Internet. | Internet outages must not stop dinner. | M | D | B12, drv |
| CTL-013 | Each module shall have its own controller function that can be operated and tested without the other modules, against a simulated system (MOD-020). | Independent design and test. | M | D | B11 |
| CTL-014 | The control system shall discover the installed modules and layout and adapt capacity, routes and schedules without programming. | Modularity. | M | D | B11 |
| CTL-015 | Safety functions (SAF section) shall not depend on the application software, the network or the UI. | Safety integrity. | M | R | drv |
| CTL-016 | The control system shall derive a shopping list from the meal plan and the inventory (incl. minimum stock levels of staples), exportable to the app. | Autonomy is only as good as replenishment. | M | D | drv |
| CTL-017 | It shall use food in first-expired-first-out order and propose meals that use food within 2 days of its use-by date. | Food waste. | M | D | drv |
| CTL-018 | It shall count cycles and operating hours per LRU, predict wear, and announce maintenance ≥ 14 days ahead. | Maintainability. | S | D | B13 |
| CTL-019 | Control hardware shall be commercially available controllers, single-board computers and fieldbus components. | Standard parts. | M | R | B13 |
| CTL-020 | Software updates shall be installable without losing inventory, recipes or settings, and be reversible to the previous version. | Robustness. | M | D | drv |
| CTL-021 | The system shall support the operating modes of section 4. | — | M | D | drv |
| CTL-022 | A simulation mode shall execute recipes against a model of the machine (timing, resources, power, ware usage) without hardware. | Verifies coverage and performance during the paper phase (V2). | S | D | drv |

### 3.13 User interface (UI)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| UI-001 | Meals shall be ordered through (a) a smartphone/web application on the home network (M), (b) a panel on the machine (M), (c) the same application from outside the home (S), (d) voice or third-party home automation (C). | How the human chooses a meal. | M | D | B1 |
| UI-002 | The ordering UI shall show, per meal: picture, components, time to ready, whether it is cookable from stock, allergens, and what is missing. It shall filter by cookable-now, time, diet, course and favourites. | Choice. | M | D | drv |
| UI-003 | An order shall specify: meal (1–3 courses), number of persons 1–4, serving time (now or date/time up to 7 days ahead), and optionally per-person portion size and recipe options. | UC-04. | M | D | B8 |
| UI-004 | Ordering a repeat of a previous or favourite meal for the default number of persons shall take ≤ 3 user inputs. | Daily use. | S | D | drv |
| UI-005 | The UI shall support weekly meal plans and recurring orders (e.g. breakfast every weekday at 07:00). | Scheduling. | S | D | drv |
| UI-006 | A household profile shall hold persons, default portion sizes, allergens and intolerances, excluded ingredients and diets; orders conflicting with the profile shall require explicit confirmation. | Allergen safety. | M | D | drv |
| UI-007 | The UI shall show the state of the machine: current activity, time to ready, inventory with use-by dates, consumable levels, waste fill level, due human tasks, faults with location and instructions. | Transparency. | M | D | drv |
| UI-008 | Notifications shall be issued for: meal ready; dish pick-up overdue; human task due (section 7.8); ingestion rejects; food discarded; faults; alarms (SAF). Alarms shall also sound at the machine. | UC-06 ff. | M | D | drv |
| UI-009 | The panel on the machine shall allow, without smartphone or network: order from favourites, request a drink from a favourites list (SRV-022), stop/cancel, open the hatch for returning dishes, start ingestion, confirm human tasks, present a box (UC-18), service mode, acknowledge alarms. | Works when the phone or network does not. | M | D | drv, DEC-13 |
| UI-010 | A stop control shall be on the front of the machine that brings all motion and heating to a safe state within 1 s (SAF-050). | Safety. | M | T | drv |
| UI-011 | UI languages: German and English (M); further languages addable as data (S). | Users. | M | I | drv |
| UI-012 | Access shall be by user accounts with roles: adult (all functions), child (view, order from an approved list), maintainer (service mode). | Child safety; misuse. | S | D | drv |
| UI-013 | The user shall be able to rate a meal and adjust persistent preferences (salt level, doneness, spiciness, portion size) that the recipes then apply. | "Normal meals" differ by household. | S | D | drv |

---

## 4. Operating modes

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| MODE-001 | **Normal:** all functions available; schedule driven by orders. | — | M | D | B1 |
| MODE-002 | **Quiet** (default 22:00–06:00, configurable): only operations within NOI-004 run; others are deferred unless an order explicitly requires them. | Home at night. | M | D | drv |
| MODE-003 | **Holiday:** as UC-16; entered by the user or proposed after 72 h without order; maintained for up to 90 days. | Long absence. | M | D | drv |
| MODE-004 | **Service** (per module): as UC-10; hazards removed, module isolated, other modules keep cold storage and safe activities running. | Repair. | M | D | B13 |
| MODE-005 | **Safe state** (per module and system): no motion, heaters off, water supply valves closed, loads held, cold storage running, alarms active. Entered on stop, on faults that cannot be recovered, and on safety triggers. | Fault recovery. | M | T | drv |
| MODE-006 | **Degraded:** with a module failed, every function not depending on it shall stay available (e.g. cooking from stock with ingestion failed; ingestion and storage with cooking failed; manual access to stored food always). | Robustness. | M | A, D | B11, B13 |
| MODE-007 | **Commissioning/self-test:** as UC-01; repeatable on demand per module. | Build, repair. | M | D | B13 |
| MODE-008 | **Eco:** the system should shift deferrable, energy-intensive activity (washing, box disinfection) to user-defined low-tariff hours. | Energy cost. | C | D | drv |

---

## 5. Meal coverage: "at least 95 % of all traditional meals" (DEC-26: 93 %)

### 5.1 Measure

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| MEAL-001 | The reference for "traditional meals" is the meal corpus in `research/02-meal-corpus.md`: 248 meals and meal components in 19 categories (56 % German/Austrian/Swiss home cooking, the rest the internationally established everyday dishes cooked in such households), each decomposed into unit operations and weighted 1–3 by how often it is cooked. Beverages are not meals. | Defines the population for the 95 %. | M | R | B5 |
| MEAL-002 | Coverage: ≥ 93 % of the corpus meals by count (≥ 231 of 248) **and** ≥ 93 % by weight shall be *preparable* as defined in MEAL-010, with ingredients bought in the forms permitted by MEAL-012 and no others. | Brief (95 %), lowered by the customer to 93 % (DEC-26). Bought filled pasta and pastry or wrapper sheets remain not permitted. | M | A (V2 walk-through and recomputation per corpus appendix A), later T on a sample | B5, DEC-26 |
| MEAL-003 | Every corpus meal of weight 3 (staple) shall be preparable, except those listed as falling out in section 5.4. | The meals eaten most often matter most. | M | A | B5 |
| MEAL-004 | Coverage by category: in every corpus category with ≥ 10 meals, ≥ 85 % shall be preparable. | The 5 % must not wipe out a whole category (e.g. all baking). | S | A | B5 |
| MEAL-005 | Regardless of percentages, the meals named in the brief shall be preparable: mixed salad with dressing (SA01); mashed potatoes (SD02); roast beef and other boneless roasts with gravy (DM08 and equivalents); Frikadellen (DM01); Rouladen (DM02), rolled and secured by the machine; soups (clear with garnish, puréed, stew-like: SP01–SP19); pan-fried steak (DM23); pasta with sauce (IT01 and equivalents). | Brief, literally. | M | A, D | B5 |
| MEAL-006 | Every meal that is not preparable shall be listed with the reason and the missing unit operation, so that the 5 % is known, not accidental. | Transparency; basis for customer decisions. | M | R | B5 |
| MEAL-007 | Coverage shall be evaluated by walking each corpus row's ordered unit operations through the designed tools, vessels and capacities, for 2 persons; the 15 reference menus of corpus section 4.9 (Annex A) and ≥ 20 further meals spread over all categories also for 1 and 4 persons. | Verification method for the paper phase (V2). | M | R | B5, B8 |
| MEAL-008 | The corpus taxonomy (codes, definitions, difficulty and avoidability ratings) is the common vocabulary of all design documents and of the recipe format (CTL-002); section 5.3 allocates every corpus code. If the corpus is revised, section 5.3 shall be updated to it. | Single source for designers. | M | R | drv |
| MEAL-009 | **Fresh produce.** Every meal counted in MEAL-002 shall be made from whole fruit and vegetables that the machine washes, peels, trims, cores and cuts itself; the only exceptions are those of section 5.6 (peeled onions, shallots, garlic; frozen peas, corn kernels and whole berries; tinned whole tomatoes, passata, tomato paste, pulses, corn). Therefore all produce operations of section 5.3 are M, except the S operations listed there (onion peeling, whole cabbage leaves, whole pineapple, thin wrapper sheets); meals depending on an S operation count against MEAL-019 or the 5 % until it is built. Target (S): MEAL-002 also met with unpeeled onions and garlic (the onion peeler upgrade, DEC-9). | Customer decision: the machine washes, peels and cuts fruit and vegetables itself. | M | A | B5, DEC-8, DEC-9 |

### 5.2 What "preparable" means

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| MEAL-010 | A meal is **preparable** when all of MEAL-011 to MEAL-017 hold, within the limits of MEAL-019 and MEAL-020. | Definition. | M | — | B5 |
| MEAL-011 | All steps from stored ingredients to plated dish are performed by the machine without human action. | B1. | M | D | B1 |
| MEAL-012 | **Permitted purchases** (DEC-8, DEC-9: "fresh, healthy meals from natural ingredients, without industrial food"). Only the products listed in section 5.6 as permitted may be used for a meal counted in MEAL-002. In short: animal products pre-processed only by cutting and portioning; peeled whole onions, shallots and garlic; basic foods and staples that a traditional home cook buys and does not make; bread and bakery; drinks. Not permitted: fruit and vegetables that are cut, peeled (except onions/garlic), cored, trimmed, pre-washed or frozen after cutting; egg products; ready doughs, pastry sheets, wrappers, fresh and filled pasta; stock concentrates; ready sauces, dressings, mayonnaise, pesto, dessert powders; formed, breaded, stuffed or rolled meat and fish products; ready meals. The storage holds whatever the household buys (DEC-13); the rule restricts only what counts towards coverage. | Otherwise 95 % is reached by buying convenience food, which the customer explicitly rejects. | M | R | B5, DEC-8, DEC-9 |
| MEAL-013 | **Deviations from the traditional method are classified in three classes.** **(a) Process aid:** a change in how the machine gets there that the diner cannot detect in the finished dish — other tool, fixture, order of steps, batch size, vessel, tempering or chilling for handling, fasteners. Free: not marked, not counted, no panel. **(b) Equivalent method:** a different cooking or forming method that aims at the same traditional result (e.g. hot-air instead of oil bath, two-sided heat instead of turning, parts instead of whole). Marked in the design documents; to be confirmed once per method family by the panel of MEAL-015: equivalent if the mean is ≥ 3.0 *and* not more than 0.5 points below the traditionally made reference. If confirmed it is not counted; if the panel notices (more than 0.5 below, but still ≥ 3.0) it is treated as class (c); below 3.0 the meal is not preparable. **(c) Visibly different result:** the diner sees or tastes, without a comparison, that the dish is not the traditional one (other shape, other cut where the cut is the dish, a part left out, another form of serving). Must reach ≥ 3.0, is marked as such to the user on the menu, and is counted against MEAL-019. "Adapted" in this document means class (b) or (c). | Leaves design freedom ("novel tools welcome") without hollowing out the goal; ends the explorers' disagreement on what counts. | M | R, T | B5 |
| MEAL-014 | The result is safe: FSF requirements met. | — | M | T | drv |
| MEAL-015 | The result is accepted: in a blind comparison with the same dish by a competent home cook, ≥ 5 raters give a mean ≥ 3.0 of 5 (3 = "as good as normal home cooking") for taste and texture, and none of the recipe's objective criteria (doneness, core temperature, consistency, browning) is missed. | "Cook … normal meals" means edible to home standard, not merely processed. | M | T (prototype), R (paper phase: objective criteria only) | B1 |
| MEAL-016 | It can be prepared for every number of persons from 1 to 4 (largest single pieces, e.g. a roast, may have a minimum size serving more than 1). | B8. | M | A | B8 |
| MEAL-017 | It meets the time target PERF-001 and is completed without human intervention in ≥ 98 % of attempts (REL-001). | — | M | A, T | drv |
| MEAL-018 | **Operations the machine shall perform itself.** (a) Those with no purchase workaround at all — browning on both sides (FLP, 12.9 % of meals), assembling (ASM, 6.9 %), carving (CAR, 4.8 %), unmoulding (UNM, 4.4 %), scoring (SCO, 2.8 %); together 29 % of the corpus. (b) The shaping cluster, avoidable only with products that MEAL-012 forbids — stuff/fill (STU), wrap (WRP), hand-form small pieces (FRM), dough rolling and shaping (ROL, SHD), breading (BRD), roll-and-secure (RLT), and forming patties and dumplings (FRB, FRK); the cluster alone blocks 38 meals = 15.3 %. These operations are priority M in section 5.3, within the limits stated there; the coverage target cannot be met without them. A design that omits one of them shall show, meal by meal, that MEAL-002 and MEAL-003 still hold. | Makes explicit where the difficulty of the 95 % goal lies (corpus sections 4.5–4.7, 7). | M | R, A | B5 |
| MEAL-019 | **Budget for adaptations.** (1) *Mandated adaptations* — those this specification itself prescribes by its exclusions (section 5.4: X-01, X-06, X-11, X-13, and the purchase rule MEAL-012; at present 24 meals = 9.7 %, listed in 5.5) — are kept in a separate list and do not consume the designers' budget, whatever class the panel assigns them. (2) *Designer-chosen class (c)*: ≤ 24 meals (10 % of the corpus), and ≤ 5 of the weight-3 meals. (3) *Designer-chosen class (b)* pending panel confirmation: ≤ 50 meals (20 %); in the paper phase they count as zero against (2) but each shall name its fallback if the panel notices. (4) Ceiling for everything the user can notice — mandated meals that turn out class (c), plus (2): ≤ 40 meals (16 %). | The former single 10 % limit was almost used up by the specification's own substitutions. | M | A, T | B5 |
| MEAL-020 | **Served as components for assembly at the table.** Counts as preparable, as class (a), for meals the customer accepts being assembled by the diner (DEC-14): tacos, fajitas, wraps and burritos, raclette-like and cold platters, garnishes served alongside. It does not count as preparable for meals whose identity is the assembly made in the kitchen: burger, sandwich and toast, hot dog, pizza, enchiladas, layered and filled dishes and cakes. | Customer decision. | M | R | B5, B8, DEC-14 |
| MEAL-021 | One register of adaptations shall be kept for the whole project (owner: architecture/V2): per corpus meal its class, the method, whether mandated, the panel status and the fallback. Every design document shall use the class letters of MEAL-013 and the rulings of section 5.5. | "Not yet counted by anyone" (explorers). | M | R | drv |

### 5.3 Unit operations the machine shall support

The taxonomy of `research/02-meal-corpus.md` section 2 (126 operations, three-letter codes) is authoritative
for naming and definitions; the table below allocates every corpus code to a requirement, with priority and
minimum capability. Module: P preparation, C cooking/baking, S portioning/serving, X any. Priority M = needed
for MEAL-002; S = needed for MEAL-009 or raises quality; C = optional. "n" = number of corpus meals using
the operation(s).

**Handling and dosing**

| ID | Unit operation (corpus codes) | n | Minimum capability | Prio | Mod. |
|----|-------------------------------|---|--------------------|------|------|
| UO-01 | Dose from box: free-flowing solids DSO, powders and spice pinches DPO, viscous/sticky DVI, countable whole items DUN, block solids DBL (cut a portion off butter, cheese), raw meat/fish pieces DME | 238 | PRP-010, PRP-011 | M | P |
| UO-02 | Dose thin liquids DLI, incl. water | 218 | PRP-015 | M | P/C |
| UO-03 | Transfer vessel → vessel / cooking vessel / baking dish | all | PRP-013 | M | P/C |
| UO-04 | Weigh (ingredient, vessel contents, portion) | all | ±1 g below 500 g, ±0.5 % above | M | X |
| UO-05 | Crack eggs CRK, shell-free (no fragment > 1 mm in 99 % of eggs), yolk intact ≥ 90 % for fried egg | 36 | 12 eggs in ≤ 3 min | M | P |
| UO-06 | Separate egg SEP | 17 | yolk in white in ≤ 1 % of eggs (no egg products may be bought) | M | P |
| UO-07 | Open/close lids of boxes and vessels | all | — | M | X |
| UO-08 | Thaw | — | CLD-013; or as part of cooking | M | X |
| UO-09 | Soak SOK, marinate MAR, rest RES (dough, batter, meat) for a set time at a set temperature | 55 | 0.1–72 h; ≤ 7 °C or ambient | M | P |
| UO-23 | Rinse grains, pulses, cooked pasta RNS | 16 | — | M | P/C |

**Cleaning, peeling, trimming and cutting**

| ID | Unit operation (corpus codes) | n | Minimum capability | Prio | Mod. |
|----|-------------------------------|---|--------------------|------|------|
| UO-10 | Wash robust produce WSH; wash leafy/delicate produce WLF; spin or pat dry DRY | 146 / 86 | leaf salad ≤ 5 % adhering water; no grit | M | P |
| UO-11 | Peel potato and smooth roots PLP | 60 | PRP-022 | M | P |
| UO-12 | Peel onion, shallot and garlic PLA | 129 | ≥ 95 % skin-free; cutting away some flesh is acceptable (DEC-9) | S (upgrade; peeled onions and garlic are the baseline purchase, DEC-9). Dicing and slicing onions is always M (UO-14 to UO-16). | P |
| UO-24 | Peel soft fruit and vegetables PLS (cucumber, apple, pear, mango, kiwi, banana, citrus); hard/knobbly PLH (celeriac, kohlrabi, carrot, beetroot, pumpkin, ginger, white asparagus); tomato and peach by blanching PLM; boiled egg PLE | 26 / 18 / 2 / 7 | peel loss ≤ 30 % for knobbly roots; PRP-039 | M (core function, DEC-25) | P |
| UO-13 | Trim ends TRE (beans, leek, spring onion, sprouts, mushrooms, strawberries); core/deseed/hull COR (pepper, apple, pear, cabbage, tomato, chili, pumpkin, melon); stone PIT (avocado, mango, peach, plum, apricot, cherry, olive); strip/pluck/break into florets STR (herbs, kale, cauliflower, broccoli); separate whole cabbage leaves LSP; peel and core whole pineapple | 31 / 50 / 3 / 9 / 1 / 2 | TRE, COR, PIT, STR: M (PIT for cherries and olives: S); LSP, pineapple: S | M | P |
| UO-14 | Slice SLI | 70 | 1–20 mm, PRP-021 | M | P |
| UO-15 | Dice DIC; sticks and strips JUL | 106 / 13 | 3–25 mm | M | P |
| UO-16 | Mince fine MIN; chop herbs CHH | 35 / 26 | < 3 mm | M | P |
| UO-17 | Grate coarse GRC; grate fine and zest GRF | 22 / 29 | 1–6 mm; zest without pith | M | P |
| UO-18 | Slice raw meat and fish SLM; butterfly/pocket-cut BFL | 15 / 1 | 5–50 mm | S (bought cut by default) | P |
| UO-19 | Grind meat GRM; grind spices GRS | 1 / 108 | — | C (mince and ground spices are bought) | P |
| UO-20 | Pound / flatten POU | 5 | to 4–10 mm ±1 mm, up to 250 × 150 mm | S (thin cutlets bought by default) | P |
| UO-21 | Juice citrus JUI | 8 | — | M | P |
| UO-22 | Halve, quarter, wedge WED | 14 | pieces up to PRP-020 | M | P |
| UO-25 | Crush/chop coarse hard items CRH (nuts, chocolate); make crumbs BCR | 5 / 1 | — | M / C | P |
| UO-26 | Cut dough and pasta CUD | 10 | strips, pieces, cutter shapes | M | P |

**Mixing and transforming**

| ID | Unit operation (corpus codes) | n | Minimum capability | Prio | Mod. |
|----|-------------------------------|---|--------------------|------|------|
| UO-30 | Mix dry MXD; mix/stir cold or batter MXW; toss/coat TOS | 25 / 39 / 36 | 0.05–5 L; gentle (salad, no bruising) to vigorous | M | P/C |
| UO-31 | Whisk WHK; whip to volume WHP; cream fat with sugar CRM; emulsify EMU | 32 / 10 / 7 / 10 | from 1 egg white to 6; mayonnaise, vinaigrette, hollandaise | M | P |
| UO-38 | Fold gently FLD; sift SFT | 11 / 9 | volume loss ≤ 20 % | M / S | P |
| UO-32 | Knead dough KND; mix/knead mince mass KNM; rub in fat RUB | 17 / 12 / 5 | 0.1–1.2 kg dough (750 g flour); 0.8 kg mince mass | M | P |
| UO-33 | Mash MSH | 9 | no lump > 5 mm, not gluey | M | P/C |
| UO-34 | Purée / blend PUR, hot or cold | 15 | < 1 mm particles, up to 3 L, up to 95 °C | M | P/C |
| UO-35 | Extrude / press through EXT (Spätzle, ricer) | 3 | — | S | P/C |
| UO-36 | Drain / strain DRN; squeeze out liquid SQZ | 56 / 4 | COK-011 | M | P/C |
| UO-37 | Season surface SEA; season to recipe and household preference | 29 | UO-01 at seasoning accuracy; user factor 0.8–1.2 (UI-013) | M | P/C |

**Forming and assembling — no purchase workaround at the permitted level (MEAL-018)**

| ID | Unit operation (corpus codes) | n | Minimum capability | Prio | Mod. |
|----|-------------------------------|---|--------------------|------|------|
| UO-40 | Form patties and balls from mince FRB; form dumplings FRK | 6 / 3 | 20–250 g, ±10 %; dumplings hold together in simmering water | M | P |
| UO-41 | Bread (flour – egg – crumbs) BRD; dust with flour; batter-dip BAT | 5 / 1 | coverage ≥ 95 % of the surface | M (BAT: S) | P |
| UO-42 | Roll and secure RLT; wrap a flat item around a filling WRP | 4 / 10 | Rouladen: meat slice up to 250 × 150 mm with spread and filling, stays closed through browning and braising (M, brief). Cabbage rolls, bacon wrap, burrito/wrap, enchilada (M). Strudel, biscuit roll, trussing poultry (S). Sushi excluded (X-12). | M | P |
| UO-43 | Layer LAY | 23 | alternate solids, sheets and sauces, even layers ±20 % | M | P |
| UO-44 | Stuff / fill STU | 16 | rigid cavities and tubes: peppers, tomatoes, apples, cannelloni, dumpling cores, poultry cavity (M); pockets of rolled pasta dough for filled pasta (Maultaschen, tortellini-type) in simple shapes (M, since filled pasta may not be bought); flat meat pockets such as cordon bleu (S) | M | P |
| UO-45 | Roll out dough ROL; shape dough SHD | 10 / 6 | 2–10 mm ±1 mm up to tray size; pasta sheets 1–2 mm; line a tin, form loaf and rolls, pizza base (M); thin wrapper sheets ≤ 1 mm for spring rolls and gyoza (S); braids and pretzels excluded (X-09) | M | P |
| UO-46 | Shape small pieces FRM | 7 | gnocchi, Schupfnudeln, croquettes, falafel, cookie balls; ±15 % mass | M | P |
| UO-47 | Pour and spread thin batter PTH; fill moulds (part of LIN) | 3 / 22 | ±10 % | M | P/C |
| UO-48 | Skewer SKW | 1 | — | C | P |
| UO-49 | Grease / line a baking vessel LIN | 22 | — | M | P/C |
| UO-90 | Spread evenly SPR (mustard on Roulade, sauce on pizza, cream on cake) | 11 | layer ±30 % | M | P |
| UO-91 | Sprinkle / top TOP | 24 | even over the area ±30 % | M | P |
| UO-92 | Score / slash SCO (pork rind, bread, tomato) | 7 | depth 2–10 mm ±2 mm | M | P |
| UO-93 | Pipe / deposit shaped portions PIP | 3 | — | S | P/S |
| UO-94 | Glaze / brush GLZ | 7 | — | M | P/C |

**Thermal**

| ID | Unit operation (corpus codes) | n | Minimum capability | Prio | Mod. |
|----|-------------------------------|---|--------------------|------|------|
| UO-50 | Boil BOL | 47 | up to 4 L of water, COK-004 | M | C |
| UO-51 | Simmer / poach gently SIM; poach egg POA | 79 / 1 | 60–98 °C ±3 K (POA: S) | M | C |
| UO-52 | Steam STM | 3 | up to 1.0 kg of food | M | C |
| UO-53 | Blanch and shock BLA | 3 | — | S | C |
| UO-54 | Sauté / sweat SAU, incl. slow caramelising of onions | 84 | 100–180 °C, with stirring | M | C |
| UO-55 | Sear SER; pan-fry PFR; browned on both sides FLP | 25 / 43 / 32 | COK-005, COK-009; surface up to 260 °C | M | C |
| UO-56 | Shallow-fry in ≤ 250 mL fat (PFR) | — | COK-021 | M | C |
| UO-57 | Braise BRS | 9 | lidded, up to 4 h, 85–170 °C, hob or cavity | M | C |
| UO-58 | Roast RST with core-temperature control | 13 | up to 2.5 kg; 80–250 °C | M | C |
| UO-59 | Bake BKE | 44 | 30–250 °C (280 °C: S); COK-006 | M | C |
| UO-60 | Grill / gratinate GRL | 8 | top heat | M | C |
| UO-61 | Deglaze DGL; reduce RED; thicken THK | 24 / 14 / 29 | reduction to a target mass ±5 %; lump-free | M | C |
| UO-62 | Make a sauce from the fond in the pan or roasting vessel | — | — | M | C |
| UO-63 | Thin batter items cooked on both sides (PTH + FLP) | — | Ø up to 280 mm, ≥ 95 % intact | M | C |
| UO-64 | Fry / scramble / boil eggs to a set doneness | — | — | M | C |
| UO-65 | Baste BST | 9 | every 20–30 min | M | C |
| UO-66 | Skim foam or fat SKM | 2 | — | C | C |
| UO-67 | Toast dry TST | 13 | bread, nuts, crumbs | M | C |
| UO-68 | Melt MLT; gentle water-bath heat BMA; caramelise sugar CRL | 24 / 5 / 4 | 30–80 °C ±2 K; sugar to 180 °C | M | C |
| UO-69 | Deep-fry DFR | 10 | excluded (X-01): adapted methods | — | C |
| UO-70 | Keep warm KWM / hold cold | 8 | COK-017 | M | C/S |
| UO-71 | Chill / set CHL; cool down COL | 15 / 27 | COK-022; set ≥ 2 h at ≤ 7 °C | M | C/P |
| UO-72 | Rest cooked meat (RES) | — | 3–20 min at 50–60 °C | M | C/S |
| UO-73 | Reheat stored leftovers or cooked components | — | core ≥ 72 °C | S | C |
| UO-74 | Cook by absorption ABS (rice, couscous) | 23 | measured water, lid, boil-dry detection | M | C |
| UO-75 | Stir continuously on heat STC (risotto, custard, béchamel, porridge, scrambled egg) | 16 | COK-008; no scorching | M | C |
| UO-76 | Stir-fry STW | 7 | adapted method permitted: agitated pan at 230–260 °C | M (adapted) | C |
| UO-77 | Proof dough PRF | 11 | 28–35 °C; or 12–16 h cold | M | P/C |
| UO-78 | Contact bake CNT (toasted sandwich; waffle) | 2 | sandwich by pan or double-sided heat (M, adapted); waffles excluded (X-11) | S | C |
| UO-79 | Freeze / churn FRZ | 1 | excluded (X-11) | — | — |

**Finishing and plating — no purchase workaround (MEAL-018)**

| ID | Unit operation (corpus codes) | n | Minimum capability | Prio | Mod. |
|----|-------------------------------|---|--------------------|------|------|
| UO-80 | Carve / slice cooked meat CAR | 12 | 2–15 mm slices, boneless roast up to 2.5 kg, slices intact (M); bone-in poultry into portions (S) | M | S/P |
| UO-81 | Portion into servings PRT | 28 | SRV-002, SRV-003 | M | S |
| UO-82 | Sauce / ladle onto plate SCE | 18 | 30–450 mL ±10 %, no drips on the rim | M | S |
| UO-83 | Plate / arrange PLT | 231 | SRV-005 | M | S |
| UO-84 | Garnish / dust / drizzle GAR | 37 | 0.5–30 g | M | S |
| UO-85 | Slice baked goods, portion cake, pizza, casserole SLB | 33 | pieces intact ≥ 90 % | M | S |
| UO-86 | Dress and toss salad immediately before serving (TOS) | — | — | M | P/S |
| UO-87 | Unmould / turn out UNM | 11 | cake from tin, pudding, panna cotta; ≥ 95 % undamaged | M | S/C |
| UO-88 | Assemble / build ASM (burger, taco, sandwich, wrap, bowl, pizza toppings, layered cake) | 17 | components placed in order, stack stable on the way to the hatch | M | S/P |
| UO-95 | Shred cooked meat SHR | 3 | — | S | S/P |
| UO-96 | Make stock ahead: simmer bones and/or vegetables 1–4 h, strain, portion and freeze; keep ≥ 3 L of frozen stock in stock | 49 (use stock) | stock concentrates may not be bought (MEAL-012) | M | P/C |
| UO-97 | Make from scratch what the corpus row buys ready: pesto (PUR), mayonnaise and dressings (EMU), custard/pudding from milk, starch, egg (STC), fish fingers from fillet (BRD) | — | as the operations named | M | P/C |

### 5.4 Candidates for exclusion (the "7 %")

The corpus has 248 meals, so at most 17 may be not preparable (MEAL-002, DEC-26). With the exclusions below and the purchase
rule of MEAL-012, the meals known to fall out are 11 (4.4 %): CK11 yeast doughnuts, DM21 roast goose (duck
≤ 2.5 kg remains), DS13 ice cream, BF08 waffles, AS05 sushi, BK06 pretzels, CK08 Black Forest cake, BK02
sourdough bread, CK12 apple strudel (hand-pulled dough), and AS08 spring rolls and AS09 gyoza (no wrappers may
be bought). The reserve is 6 meals. The thin-sheet capability of UO-45 (S) brings AS08 and AS09 back (reserve 8);
V2 shall recompute the list. If the reserve is exceeded, the cheapest candidates to re-include are, in this
order, thin wrapper sheets (UO-45), X-11 (waffle plates, possibly shared with two-sided heating), X-09, X-01.

| ID | Excluded capability | Justification | Corpus meals affected; adapted method or consequence |
|----|---------------------|---------------|------------------------------------------------------|
| X-01 | Deep-frying DFR in an oil bath (> 250 mL oil). The corpus proposes a 3 L fryer; this specification does not require one. | Fire load incompatible with unattended operation (SAF-014); oil storage, filtering, ageing and disposal; hardest cleaning task; 4 % of meals. | 10 meals. **Adapted methods permitted (MEAL-013):** SD04 French fries, SD21 croquettes, IN07 samosa, AS08 spring rolls → hot-air/oven crisping at 200–230 °C with ≤ 15 mL oil per 500 g. ME05 falafel, FI02 Backfisch, US05 fried chicken, AS07 sweet-and-sour chicken → shallow-frying in ≤ 250 mL fat with turning (UO-56), or hot-air. IN05 biryani (fried onions) → shallow-fried. CK11 Krapfen/Berliner → no acceptable substitute, falls into the 5 %. SD04 has weight 3: its result shall pass MEAL-015 explicitly. These are mandated adaptations (MEAL-019 (1), section 5.5). |
| X-02 | Open-flame or charcoal grilling, smoking, flambéing, torching | No flame in an enclosed unattended machine. | Pan-searing, top-heat browning (UO-60). |
| X-03 | Butchery: debone DBN, trim sinew and silverskin TRM, fillet/gut/scale fish FLT, shell seafood PLQ | Difficulty 5, no household-scale solution; supermarkets sell the prepared form (MEAL-012 a). | 11 meals, all preparable with bought boneless, trimmed, filleted or shelled goods. Whole gutted fish (FI07) is baked whole and carved by the guest. |
| X-04 | Whole roasts and birds > 2.5 kg; carving whole large birds | A few festive meals per year would set oven and vessel size for everything. | DM21 goose falls out; duck, chicken ≤ 2.5 kg and poultry parts remain (bone-in carving: S). |
| X-05 | Meals for more than 4 persons in one run | CAP-001, DEC-19. | Two runs, or family-style serving (SRV-018). |
| X-06 | Laminated dough from scratch (puff pastry, croissant); hand-pulled strudel dough | Thin-dough manipulation of difficulty 5; pastry sheets may not be bought (MEAL-012). | CK12 falls out. CK17 apple turnovers with quark-oil dough instead of puff pastry: mandated class (c) (5.5). Filled pasta is **not** excluded: made by the machine (UO-44). |
| X-07 | Decorative patisserie: multi-layer cream tortes, piped decoration, icing work | Endless variety of manual finishing. | CK08 Black Forest cake falls out; plain cakes, tray bakes, tarts, muffins (with simple topping) remain. |
| X-08 | Preserving, canning, jam-making, fermenting, curing, sausage-making | Not meal preparation; not in the corpus. | — |
| X-09 | Sourdough with a living starter; braided and knotted shapes | Starter culture needs weekly feeding; shaping of difficulty 5. | BK02, BK06 fall out. Yeast bread, rolls, pizza and Flammkuchen bases remain (UO-45). |
| X-10 | Table-cooking formats: fondue, raclette, hot pot, table grill | The cooking is the human activity; not in the corpus. | — |
| X-11 | Single-purpose equipment: waffle iron, ice-cream churn, pressure cooker, sous-vide, rotisserie, jet-flame wok | Each adds a device and a cleaning task for < 1 % of meals. | BF08 waffles, DS13 ice cream fall out. US07 toasted sandwich → pan or double-sided heat. The 7 stir-fry meals → agitated hot pan (UO-76, adapted). |
| X-12 | Fine manual assembly: sushi rolling, canapés | Difficulty 5. | AS05 sushi falls out. |
| X-13 | Skewering SKW, skimming SKM | Alternatives exist. | ME04 souvlaki as loose cubes; SP05, DM29 without skimming — mandated adaptations (5.5). |
| X-14 | Raw-egg, raw-meat and raw-fish dishes served uncooked | Food-safety risk without a human judging freshness. | Only on explicit opt-in (FSF-024); DS06 tiramisu with pasteurised egg by default. |
| X-15 | Preparing drinks | Non-goal NG-01; not in the corpus. Pouring stored drinks is required (SRV-022). | — |

### 5.5 Adaptation rulings

Binding examples for MEAL-013 (class a = process aid, free; b = equivalent method, panel; c = visibly
different, counted). New cases are decided by analogy and added here.

**Mandated adaptations (MEAL-019 (1)) — 24 meals, outside the designers' budget**

| Meals | Mandated by | Method | Class to assume until the panel |
|-------|-------------|--------|--------------------------------|
| SD04 fries, SD21 croquettes, IN07 samosa, AS08 spring rolls | X-01 | hot-air/oven crisping | b (SD04, weight 3, shall be panel-tested first) |
| ME05 falafel, FI02 Backfisch, US05 fried chicken, AS07 sweet-and-sour chicken, IN05 biryani onions | X-01 | shallow-fry ≤ 250 mL or hot-air | b |
| AS01, AS02, AS04, AS11, MX05, VG01 stir-fry dishes (AS07 counted above) | X-11 | agitated pan at 230–260 °C | b |
| US07 toasted sandwich | X-11 | pan or two-sided heat | a (the home method) |
| ME04 souvlaki | X-13 | grilled as loose cubes | c |
| SP05 chicken soup, DM29 boiled beef | X-13 | not skimmed | b |
| IT17 tortellini, DM33 Maultaschen | MEAL-012 (no filled pasta) | filled pasta made by the machine in simple square or rectangular shape | c |
| FI01 fish fingers | MEAL-012 (no formed or breaded products) | breaded fish pieces made from fillet | b |
| DS03 pudding from powder | MEAL-012 (no dessert powders) | cooked from milk, starch, egg, vanilla | b |
| CK17 apple turnovers | X-06 | quark-oil dough instead of puff pastry | c |

**Rulings on cases raised in the concept phase**

| # | Case | Ruling |
|---|------|--------|
| R-01 | Rouladen not tied with twine but held by skewers, pins or clips, or braised seam-down without fastener | **a**. Pins and skewers are themselves traditional; the fastener is removed before plating or is removable by the diner without tools. Condition: ≥ 90 % of rolls closed at plating (UO-42). One large Roulade sliced into portions: **c**. |
| R-02 | Tempering, chilling or surface-freezing an ingredient as a handling aid (meat before slicing or breading, bacon to 12–15 °C, butter to 18–22 °C, chill-slice-reheat of a braised roast) | **a**, provided the food is served in the traditional state, FSF-013/-014/-030 are met and thawed raw food is not refrozen. |
| R-03 | Flip by a pair of pans (turning one over onto the other) with ≤ 30 mL free fat | **a**: it is turning. With more fat another turning method is required (COK-021 is unaffected). |
| R-04 | Browning both sides by two-sided contact heat or top heat instead of turning | **b**. |
| R-05 | Pizza, Flammkuchen or tray cake baked on a rectangular tray (e.g. Gastronorm 2/3) instead of 400 × 300 mm or a round 320 mm stone | **a**: tray pizza is a traditional home form; COK-006 asks only for ≥ 0.10 m². Portions per run shall still serve the ordered persons (several trays in sequence allowed within PERF-001). |
| R-06 | Poultry roasted as parts instead of whole and carved | **b** (plated portions are the same pieces; skin and juiciness go to the panel). Whole goose remains excluded (X-04). Aromatics injected or added as liquid instead of a cavity stuffing: **b**. Where the stuffing is served as a component: **c**. |
| R-07 | Diced bacon instead of slices | **a** where the bacon is cooked into the dish (Bratkartoffeln, carbonara, beans, quiche); **c** where the rasher is the item on the plate or wraps something (breakfast bacon, bacon-wrapped dishes). |
| R-08 | Onion: bought peeled whole onions, shallots, garlic cloves (DEC-9) | Permitted, no adaptation; dicing, slicing and rings are always cut by the machine. Frozen diced onion and garlic paste are **not** permitted (DEC-8). |
| R-09 | Potatoes boiled in the skin and slipped afterwards, for mash, potato salad, fried potatoes, dumplings | **a** (traditional). For plain boiled potatoes (Salzkartoffeln): **b**. |
| R-10 | Other cut than the recipe's: cauliflower in slabs instead of florets, square instead of pleated gyoza/samosa, strawberries with calyx | **c**. Dice instead of slices inside a stew or sauce: **a**. |
| R-11 | Other batter or mixing method with the same product: whole-egg sponge instead of separated eggs, oil or melted-butter method instead of creaming, carton egg white | **b**. |
| R-12 | More batches, other vessel, other order of steps, warm-holding between batches | **a**. |
| R-13 | A component or garnish of the corpus row left out | **c**; if it is the characteristic component, the meal is not preparable. |
| R-14 | Served as components | MEAL-020. |
| R-15 | Stock | Stock made by the machine and frozen in portions (UO-96): **a**. Water with extra aromatics where the recipe wants stock: **b**. Bought stock, cubes or bouillon powder: not permitted (5.6). |
| R-16 | A product that the corpus row buys ready is made from scratch | **a** where the home-made version is the traditional one (pesto, mayonnaise, dressing, washed whole lamb's lettuce instead of a bag, raw beetroot boiled and peeled instead of vacuum-cooked, fresh vegetables instead of a frozen mix, custard starch instead of pudding powder as a minor ingredient of a cake); **b** or **c** where the bought product defines the dish (5.5 mandated list). |

### 5.6 Purchase list (DEC-8, DEC-9)

Decided case by case against the customer's aim "fresh, healthy meals from natural ingredients, without
industrial food": cutting and portioning are allowed, industrial or semi-finished products are not; fruit and
vegetables are washed, peeled and cut by the machine. Corpus ingredient keys in brackets.

| Group | Permitted for meals counted in MEAL-002 | Not permitted (the machine makes it, or the meal is adapted or falls out) |
|-------|------------------------------------------|---------------------------------------------------------------------------|
| Fruit and vegetables | Whole, unwashed, unpeeled fresh produce; **peeled whole onions, shallots and garlic cloves** (DEC-9); frozen peas and corn kernels (podding and shelling are excluded, fresh pods are rarely sold); frozen whole berries; dried fruit; tinned whole peeled tomatoes, passata, tomato paste, tinned pulses and corn (only cooked, not cut). | Anything cut, peeled, cored, trimmed, grated or shredded; pre-washed and bagged salad (saladmix); frozen cut vegetables and mixes (veg_fz, asianveg), frozen chopped spinach and herbs (spinach_fz); frozen diced onion, garlic paste; vacuum-cooked beetroot; tinned or jarred cut fruit (pineapple_can); bottled lemon juice. |
| Meat and fish | Cuts and portions from the butcher or fish counter: fillets, steaks, cutlets, thin Rouladen slices, strips, cubes, minced meat, boneless and trimmed joints, bones, whole birds ≤ 2.5 kg, shelled seafood; traditional cured, smoked or cooked products: bacon (sliced or diced), ham, sausages, Kassler, herring, tinned tuna. | Formed, breaded, marinated, stuffed or rolled products: patties, meatballs, fish fingers (fishsticks), breaded cutlets, ready Rouladen, ready-stuffed vegetables, kebab meat. |
| Eggs and dairy | Eggs in shell; milk, cream, butter, yoghurt, quark, sour cream, crème fraîche, cream cheese, cheese (also sliced or grated), mozzarella, feta, paneer. | Liquid, pasteurised or dried egg products; peeled boiled eggs. |
| Grains, staples, baking | Flour, semolina, oats, rice, couscous, bulgur, dried pasta and noodles incl. dried lasagne sheets, dried pulses, starch, sugar, honey, salt, yeast, baking powder, gelatine, cocoa, chocolate, vanilla, marzipan, nuts and seeds (whole or ground), tahini, oils, vinegar, wine and spirits for cooking, soy sauce, miso, coconut milk, nori, tofu. | Ready doughs and pastry sheets (pastry_dough, pizza, shortcrust, puff, filo, strudel), spring roll and dumpling wrappers (wrapper), fresh and filled pasta (pasta_fresh), cake and dessert mixes, pudding powder (pudding_powder). |
| Seasonings and condiments | Dried herbs, whole and ground spices and spice blends without additives, fresh herbs, mustard, ketchup, horseradish, jam, pickles, sauerkraut, chili paste. | Stock, stock cubes and bouillon powder (stock: made by the machine, UO-96); ready sauces, dressings, mayonnaise (mayo), pesto; flavour enhancers. |
| Bread and bakery | Bread, rolls, buns, toast bread, tortillas, sponge fingers, breadcrumbs as cooking ingredients (bought as bakery, like any household; bread for eating is kept outside, DEC-16). Baking bread is a machine function (corpus BK rows). | Par-baked or frozen dough products counted as "home-made" bread. |
| Drinks and household chilled goods | Any chilled or frozen product the household buys, and drinks, are stored (DEC-13); drinks are poured on request (SRV-022). Ambient breakfast goods and snacks are kept outside (DEC-16). | Not counted towards meal coverage. |

The corpus ingredients hit by this list and the consequences: stock (49 meals) → UO-96; pesto, mayonnaise,
pudding powder, saladmix, veg_fz, asianveg, spinach_fz, beet → made from scratch or fresh (R-16, class a or b);
pasta_fresh (DM33, IT17) → filled pasta by the machine (mandated c); fishsticks (FI01) → from fillet (mandated
b); pastry_dough (CK17) → quark-oil dough (mandated c); wrapper (AS08, AS09) → thin sheets (UO-45, S) or fall
out; pineapple_can (AS07, US07) → fresh pineapple (S) or class c without it.

---

## 6. Capacity and performance

### 6.1 Persons, meals, portions

**1–4 persons per meal (DEC-19).** The regular household is 2 persons; with guests a meal serves at most
4 (DEC-18, DEC-19). All batch and vessel sizes, cooking positions, ware and dish stock and time targets are
dimensioned for 1–4 persons (the *sizing meal*), while storage, running costs and lifetime are sized for the
reference household of 2. Vessel sizes are re-derived from the corpus portion and vessel tables
(`research/02`, 6.1 and 6.3) scaled from 6 to 4 persons; baked goods do not scale below one tin or tray.

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| CAP-001 | One meal run shall serve 1 to 4 persons. | DEC-19. | M | D | B8, DEC-19 |
| CAP-002 | The system shall sustain the reference household (2 persons, 2 warm meals per day) indefinitely, guest meals for up to 4 persons up to twice a week, and 4 persons with 2 full warm meals per day for ≥ 3 consecutive days when the ingredients are ingested beforehand. | DEC-18, DEC-19. | M | A | B13, DEC-18, DEC-19 |
| CAP-003 | A meal shall comprise up to 3 courses. One course shall comprise up to 4 separately prepared hot components plus 2 cold components, all served together. | Starter/soup – main – dessert; main = protein + starch + vegetable + sauce, + salad. | M | A | B8 |
| CAP-004 | Reference portions per person (corpus 6.1, 6.2): boneless meat 150 g raw (120–200), bone-in 300 g; starch side 200 g cooked; pasta as a main 100–150 g dry; vegetable 150–200 g; sauce 80 mL; soup as a main 450 mL; salad 100–150 g; dessert 120–250 g. Plated mass per person: typically 550–650 g, maximum 900 g. Maximum batch for 4 persons: one component 1.2 kg or 2 L (plus cooking water); whole meal 3.6 kg. | Sizing of vessels, tools, dishes. | M | A | B8, DEC-19 |
| CAP-005 | Within one meal, one alternative variant of one course for a subset of the persons (e.g. vegetarian, allergen-free, child's version) shall be possible. | Mixed households. | S | A, D | B8 |
| CAP-006 | The system shall serve a second full warm meal for 4 with a serving time ≥ 2 h after the first (M), ≥ 1 h (S). | Lunch and dinner with guests. | M | A | drv |
| CAP-007 | Several independent orders shall be queued and executed in serving-time order; two light meals (≤ 2 components each) with serving times ≥ 15 min apart shall both be met. | Staggered breakfasts. | S | A | drv |

### 6.2 Storage capacity and autonomy

**Scope (DEC-13, DEC-16, DEC-17).** The machine stores the household's *cooking* ingredients: ambient staples
and seasonings, cooking produce, chilled cooking goods (milk, cream, butter, eggs, cheese for cooking, raw meat
and fish, fresh produce, opened jars) and frozen ingredients and stock. Breakfast dairy, cold cuts for bread,
table drinks and other non-cooking chilled goods may live in a separate ordinary fridge; ambient breakfast
goods and snacks stay outside. A larger-storage configuration (CAP-026) can take over the separate fridge.

**Derivation** (reference household: 2 persons, 2 warm meals/day = 14 meals/week; autonomy CAP-010; DEC-18).
*Types — independent of the number of persons:* the corpus Monte-Carlo (`research/02`, 5.4) gives about 38
ingredient types for 7 dinners and 58 for 14; primary storage classes are 54 % fridge, 4 % freezer, 41 %
ambient by type. For one week of 14 meals: ≈ 30 chilled types, ≈ 5 frozen types, plus a standing ambient stock
of ≈ 55–65 staples and seasonings. *Boxes per type:* × 1.15 for split and partly used boxes (smaller
quantities for 2 persons need fewer splits); plus raw meat and fish portions (≈ 5 per week), intermediate
products (≈ 4), frozen meat portions (FSF-052: ≈ 5) and frozen stock portions (UO-96: ≈ 4). *Mass:* ≈ 0.5 kg
of raw ingredients per person per warm meal → ≈ 2 kg/day, 14 kg/week; ≈ 50 % chilled, 30 % ambient, 20 %
frozen by mass; the average box is smaller (more S and M sizes). **Consequence:** halving the household
halves the mass and volume but reduces the number of box positions by only about 10–20 %, because positions
are set by the variety of ingredients, not by the number of eaters.

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| CAP-010 | Autonomy without grocery loading, reference household (2 persons): ≥ 7 days for meals depending on fresh chilled food (M), ≥ 14 days for meals from frozen and ambient stock (M), ≥ 21 days for ambient staples and seasonings (S). Guest meals may depend on a shopping trip shortly before (CAP-013). | Weekly shopping. | M | A | B3, B4, DEC-18 |
| CAP-011 | The MVC shall hold the stock for CAP-010 *plus* the variety needed to offer, at any time after a weekly shop, ≥ 30 different corpus meals as "cookable now". | Choice is the point of a stocked kitchen. | S | A | B1 |
| CAP-012 | Reference retrieval pattern for sizing and for thermal tests: per day 30 box retrieve-and-return cycles from ambient, 25 from chilled, 5 from frozen; peaks of 15 retrievals in 10 min (est.). | Retrievals follow the number of ingredients per meal, not the number of persons. | M | — | drv, DEC-18 |
| CAP-013 | Guest shop: on top of the reference stock, the storage shall accept the ingredients for a guest meal for 4 persons bought ≤ 24 h before — ≥ 15 products, ≥ 4 kg, of which ≥ 2 kg chilled — using the empty-box reserve (CAP-023) and free positions, and ingest them per ING-022. | DEC-18: storage is sized for 2, guests are supplied by a shopping trip. | M | A | DEC-18, DEC-19 |
| CAP-020 | Ambient storage (MVC), cooking ingredients only: ≥ 70 box positions, of which ≥ 30 of the smallest size for seasonings; usable box volume ≥ 45 L; ≥ 18 kg of food, including sealed long-life packs of the STOW lane and bread used as a cooking ingredient. | 55–65 standing staples and seasonings × 1.15; 3 weeks of ambient mass for 2 persons. | M | A | B3, DEC-16, DEC-18 |
| CAP-021 | Chilled storage (MVC): ≥ 45 box positions; usable box volume ≥ 35 L; ≥ 10 kg; of which a raw meat/fish sub-zone of ≥ 5 boxes, and room for chilled cooking liquids in their original cartons (≥ 2 L, 1 L cartons upright). | ≈ 30 chilled types × 1.15 + 5 raw portions + 4 intermediates ≈ 45; 7 days × 1 kg/day chilled + intermediates. | M | A | B4, DEC-17, DEC-18 |
| CAP-022 | Frozen storage (MVC): ≥ 20 box positions; usable box volume ≥ 20 L; ≥ 8 kg; including portions of machine-made stock (UO-96) and raw meat frozen at ingestion (FSF-052). | ≈ 5 frozen types × 1.15 + 5 meat portions + 4 stock portions + reserve ≈ 20; 14 days × 0.4 kg/day + stock. | M | A | B4, DEC-17, DEC-18 |
| CAP-023 | In addition to CAP-020 to -022, the system shall hold a reserve of clean, dry, empty boxes: ≥ 15 % of all box positions, in a size mix matching the stored mix, and ≥ 25 boxes before a planned weekly ingestion. | One new box per ingested product; emptied boxes come back only after washing. | M | A | B10 |
| CAP-024 | A cool ambient zone of 8–15 °C shall hold ≥ 8 boxes for cooking produce that must not be chilled (potatoes, whole onions, garlic, tomatoes, citrus, squash), with ethylene-emitting produce kept apart from sensitive produce. | Storage quality. | M | A | B3 |
| CAP-025 | Total box positions of the MVC: ≥ 143 for food (ambient 70, cool 8, chilled 45, frozen 20) plus the empty-box reserve of CAP-023 (which also receives the guest shop, CAP-013); the architect shall confirm the resulting length against PHY-004 and may use the extra height of PHY-002. | Summary for the layout. | M | A | DEC-17, DEC-18 |
| CAP-026 | **Larger-storage configuration** (optional, ≤ 4 200 mm, PHY-004): chilled ≥ 90 positions / ≥ 140 L / ≥ 45 kg incl. ≥ 12 L of table drinks, and frozen ≥ 35 positions / ≥ 60 L / ≥ 20 kg, so that the machine can replace the separate household fridge (DEC-13); added by extension modules (MOD-032) without redesign. Ambient +50 % likewise. | Households without a separate fridge. | S | R | B11, DEC-13, DEC-17 |

### 6.3 Ware, consumables, waste

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| CAP-030 | The clean stock of vessels and tools shall cover a 2-course meal with a 4+2-component main course for 4 persons without re-washing during the run; at least 6 food vessels shall be usable at the same time. The designers shall state the resulting ware list; its total shall be minimised. | PRP-031; corpus 4.9: the peak of 6 concurrent food vessels depends on the menu, not on the number of persons. | M | A | drv, DEC-19 |
| CAP-031 | Dish store: ≥ 8 flat plates, ≥ 8 deep plates/bowls, ≥ 8 small plates/bowls, ≥ 8 glasses, ≥ 8 cutlery sets. | Two consecutive 2-course meals (or a 3-course meal) for 4 while the first dishes are being washed. | M | I | B9, DEC-6, DEC-19 |
| CAP-040 | Consumable stores (detergent, rinse aid, softener salt, descaler, disinfectant if used) shall last ≥ 30 days of reference use (M), ≥ 180 days (S). | HUM-004. | M | A | B6 |
| CAP-041 | Organic waste: ≥ 10 L and ≥ 3.5 days of reference use (est. 0.5–0.8 kg/day incl. peel, trimmings, plate leftovers), and one guest meal for 4 on top. Packaging waste, where the machine opens packages: ≥ 20 L and ≥ 3.5 days of reference use (est. 20 L/week uncompacted for 2 persons, `research/07`; compaction permitted); deposit containers shall not be damaged. | HUM-003. | M | A | drv, DEC-18 |
| CAP-042 | The organic waste shall be kept so that no odour is noticeable in the room (no detection by 4 of 5 persons at 1 m with all doors closed) until 4 days after the first waste entered. | Home. | M | T | drv |
| CAP-043 | Packaging waste should be kept in ≥ 2 separate fractions (recyclable light packaging / other), rinsed where it held perishable food. | Local recycling rules; odour. | S | I | drv |

### 6.4 Time

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| PERF-001 | Order-to-ready time, for 1–4 persons, from stock at storage temperature: ≤ 1.15 × T_ref + 10 min (M); ≤ 1.0 × T_ref + 5 min (S). T_ref of a meal is the corpus column "min"; T_ref of a menu is the longest T_ref of its components. Scheduled waiting (marinating, proofing, chilling) is part of T_ref. | The machine has no mise-en-place head start but parallelises, and has about the power of a domestic cooker (UTL-010). | M | A, T | drv |
| PERF-002 | Benchmarks for 4 persons, from PERF-001 (M level) and the corpus times: (a) spaghetti bolognese IT01, T_ref 75 → ≤ 96 min; (b) Frikadellen DM01 with mashed potatoes SD02 and peas, 35 → ≤ 50 min; (c) steak DM23 + baked potato + mixed salad, 60 → ≤ 79 min; (d) vegetable soup SP06, 35 → ≤ 50 min; (e) Rouladen DM02 + red cabbage SD11 + potato dumplings SD07, 150 → ≤ 183 min; (f) roast pork DM06 + dumplings + red cabbage + gravy, 190 → ≤ 229 min; (g) lasagne IT05 + salad, 120 → ≤ 148 min; (h) mixed salad SA01, 15 → ≤ 27 min; (i) scrambled eggs BF03, 6 → ≤ 17 min. | Concrete yardsticks for V2. | M | A, T | B5 |
| PERF-003 | From order "now" with the machine idle, the first process step shall start within 60 s. | No warm-up waiting. | M | T | drv |
| PERF-004 | For scheduled meals, the first dish shall be at the hatch within −0/+5 min of the serving time in ≥ 90 % of meals. | Punctuality. | M | T | drv |
| PERF-005 | After serving, the system shall be ready to start the next meal within 30 min (needed stations clean), and completely clean, dry and idle within 90 min (M), 45 min (S). | CAP-006; drying of soil makes cleaning harder. | M | A, T | B6 |
| PERF-006 | Ingestion throughput: as INA-009 and INB-006. | — | M | — | B10 |

### 6.5 Noise

Sound pressure level L_pA at 1 m in front of the machine, 1.5 m above the floor, in a furnished room; all
doors closed.

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| NOI-001 | Idle/standby including refrigeration: ≤ 35 dB(A) (M), ≤ 30 dB(A) (S). | Open-plan living; comparable to a quiet fridge. | M | T | drv |
| NOI-002 | Storage and transport movements, washing, drying, ventilation at normal level: L_Aeq ≤ 48 dB(A) (M), ≤ 44 dB(A) (S). | Comparable to a quiet dish washer; runs for hours per day. | M | T | drv |
| NOI-003 | Cooking including fume extraction at the level needed for searing: L_Aeq ≤ 58 dB(A). Short loud operations (chopping, blending, package opening, spin-drying): L_Aeq ≤ 68 dB(A), for ≤ 5 min in total per meal, L_AFmax ≤ 75 dB(A). | Comparable to a cooker hood at medium level; far quieter than a hand blender in the open. | M | T | drv |
| NOI-004 | Quiet mode (MODE-002): L_Aeq ≤ 40 dB(A), L_AFmax ≤ 50 dB(A); no impacts or tonal alarms except safety alarms. | Night; neighbours. | M | T | drv |
| NOI-005 | The machine shall not transmit structure-borne noise causing > 30 dB(A) in an adjacent room through a solid wall to which it is fixed (est.). | Flats. | S | T, A | drv |

### 6.6 Energy and water

All values est.; for the reference household / reference meal; energy as electrical energy at the mains.

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| RES-001 | Energy per reference meal (2 persons) including cleaning of everything it soiled and washing its dishes, excluding cold storage: ≤ 3.0 kWh (M), ≤ 2.0 kWh (S); per sizing meal (4 persons) ≤ 4.0 kWh. | Cleaning dominates and hardly scales with persons; a ware wash ≈ 1.3 kWh (`research/06`). | M | T, A | drv, DEC-18 |
| RES-002 | Energy per day, reference household, everything included: ≤ 7 kWh (M), ≤ 5 kWh (S). | ≤ 2 550 kWh/year; running cost. | M | A, T | drv, DEC-18 |
| RES-003 | Idle power, excluding refrigeration compressors: ≤ 15 W (M), ≤ 8 W (S). | 8 760 h/year. | M | T | drv |
| RES-004 | Cold storage energy for the capacity of CAP-021 and CAP-022: ≤ 1.2 kWh/day at 25 °C room temperature with the reference retrieval pattern (M); ≤ 0.8 kWh/day (S). | Two cold cells of class D/E plus exit losses. | M | T | B4, DEC-18 |
| RES-005 | Water per reference meal (2 persons) including all cleaning and washing its dishes shall be estimated and reported. Targets: ≤ 35 L, stretch ≤ 22 L; per sizing meal (4 persons) ≤ 45 L. Not a pass/fail criterion for concept selection now (DEC-23); hygiene requirements (section 7) take precedence over any water saving. | A ware wash ≈ 17–20 L (`research/06`); water optimisation is a later step. | S | T, A | drv, DEC-18, DEC-23 |
| RES-006 | Water per day, reference household, shall be estimated and reported. Targets: ≤ 75 L, stretch ≤ 50 L. Not a selection gate (DEC-23). | ≤ 27 m³/year. | S | A, T | drv, DEC-18, DEC-23 |
| RES-007 | Holiday mode: ≤ 1.5 kWh/day and ≤ 3 L/day averaged. | Only cold storage, control and stagnation flushing. | S | A | drv |
| RES-008 | Detergent consumption: ≤ 45 g (or mL) per day at reference use (est.). | Running cost; CAP-040 store size ≤ 2 L. | S | A | drv, DEC-18 |
| RES-009 | Food loss caused by the machine (residues in packages, boxes, vessels, tools, on the way; excluding peel/trimmings and plate leftovers): ≤ 5 % of ingested mass. | Yield. | S | A, T | drv |

---

## 7. Hygiene, cleaning and food safety

The brief makes cleaning "a major consideration": the machine handles raw food daily, runs unattended, and no
human cleans it. Prior art (`research/01-prior-art.md`, section 4.3) shows that no existing kitchen robot cleans
more than its vessels and tools; this section therefore is where the design must go beyond the state of the
art. Every module design shall contain a *surface inventory* (HYG-010).

### 7.1 Zones and principles

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| HYG-001 | Every surface of the system shall be assigned to Zone F, S, N or X (definitions in 1.4). In doubt, the more demanding zone applies. | Basis of all cleaning requirements. | M | R | B6 |
| HYG-002 | The design shall minimise Zone F and Zone S: each module design shall state its total Zone F and Zone S area in m² and the measures taken to reduce it (containment of splashes, steam and dust at the source). | What is not soiled need not be cleaned. | M | R | B6 |
| HYG-003 | Zone F and Zone S shall be separated from Zone N by closed surfaces or seals that withstand the cleaning process (water jets, 85 °C, detergent, steam). | Electronics and drives survive cleaning; dirt cannot hide. | M | R, T | B6 |
| HYG-004 | No Zone N part (drive, guide, cable, bearing) shall be located above open food, open vessels, open boxes or clean ware unless enclosed with a drip-proof cover that is itself Zone S. | Lubricant, wear debris, condensate. | M | I | B6 |
| HYG-005 | Material flow shall run from clean to dirty without crossing: clean ware, RTE food and plated dishes shall not pass through spaces where soiled ware, waste or class R food is open at the same time. | Cross-contamination. | M | R | B6 |
| HYG-006 | No cleaning of any Zone F or Zone S surface shall require a human, and none shall require dismantling by a human. | Brief. | M | R, D | B6 |
| HYG-007 | The system shall clean itself after a human has reached into Zone F or S (service, jam clearing) before food contact resumes. | Hands are a contamination source. | M | D | drv |

### 7.2 Hygienic design

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| HYG-010 | Each module design shall include a surface inventory: every Zone F and Zone S surface with material, finish, how it becomes soiled, cleaning method, frequency, how the cleaning medium reaches and leaves it, and how it dries. | Project rule; makes the hygiene audit (V3) possible. | M | R | B6 |
| HYG-011 | Zone F materials shall be food-contact compliant (REG-010), non-absorbent, corrosion-resistant to the detergents used (pH 2–12.5) and stable at −25 °C (where applicable) to +85 °C (wash) or to their process temperature. | Durability under daily cleaning. | M | R | B6 |
| HYG-012 | Surface finish: Zone F Ra ≤ 0.8 µm; Zone S Ra ≤ 1.6 µm (est.), closed, non-porous, no paint or coating that can flake. | Cleanability (EN 1672-2 / EHEDG practice). | M | I | B6 |
| HYG-013 | Zone F geometry: internal radii ≥ 3 mm (≥ 6 mm preferred); no crevices, gaps, blind holes, exposed threads, screw heads, hollow sections open to soil, horizontal ledges or overlapping joints; permanent joints continuous and smooth. | No soil traps. | M | I | B6 |
| HYG-014 | All Zone F and Zone S surfaces shall be self-draining (slope ≥ 3° towards a drain or edge) in their cleaning position; no standing liquid 10 min after the end of cleaning. | Standing water breeds biofilm. | M | T | B6 |
| HYG-015 | Parts made by layer-wise (FDM) 3D printing shall not form Zone F surfaces. Zone F parts shall be stainless steel or moulded or machined food-grade standard parts. In Zone S, printed parts are permitted only if sealed to HYG-012, replaceable as an LRU, and kept below 60 °C in operation and cleaning. In Zone N they are unrestricted (subject to BLD-003). | Layer grooves and porosity harbour bacteria; print materials soften at wash temperatures. Project ruling confirmed by the customer. | M | I, R | B6, B13, DEC-4 |
| HYG-016 | Dynamic seals and shaft passages through Zone F shall be avoided; where unavoidable they shall be cleanable in place on the product side and be an LRU. | Known weak point of kitchen machines (mixing-bowl seals). | M | R | B6 |
| HYG-017 | Lubricants in Zone F/S or above them shall be food-grade (NSF H1) or the mechanism shall run dry. | Incidental food contact. | M | R | drv |
| HYG-018 | No glass, ceramic or other brittle material shall be used in or above Zone F, except the dishes and viewing windows of safety glass with containment. | Foreign bodies. | M | I | drv |
| HYG-019 | Every Zone F and S surface shall be reached by the cleaning medium: spray-shadow-free, proven by a fluorescent-tracer (riboflavin) coverage test or equivalent analysis. | Coverage is the usual failure of cleaning-in-place. | M | T, A | B6 |

### 7.3 Acceptance criteria for "clean"

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| HYG-020 | **Visually clean:** after cleaning, 100 % of the Zone F and S surface shows no visible food residue, film, grease, scale or discolouration from soil, at ≥ 500 lx from 300 mm. Tested with the worst-case soils of WSH-006 and the dried-on soils of each module. | First criterion of every hygiene standard. | M | T | B6 |
| HYG-021 | **Microbiologically clean (Zone F):** the cleaning process achieves a ≥ 5 log10 reduction of test organisms on ware and surfaces that had contact with class R food, by thermal disinfection (A0 ≥ 60, e.g. 80 °C for 1 min or 70 °C for 10 min at the surface) or a validated equivalent. Surface counts after cleaning: aerobic colony count ≤ 10 cfu/cm², Enterobacteriaceae < 1 cfu/cm². | Raw meat, unattended, no human check. | M | T | B6 |
| HYG-022 | **Residue-free (Zone F):** ATP swab within the instrument maker's pass limit for food-contact surfaces, and allergen-specific rapid tests negative after soiling with milk, egg, wheat flour and mustard. | Allergen cross-contact; objective cleanliness. | M | T | B6 |
| HYG-023 | **Chemically clean (Zone F):** after the final rinse, water draining from the surface differs from the supply water by ≤ 0.5 pH and ≤ 50 µS/cm (est.); no detergent taste or odour transferred to food. | Detergent residue. | M | T | drv |
| HYG-024 | **Dry:** ware is stored and used only when dry: no visible droplets; adhering water ≤ 0.5 g per item up to 1 L size and ≤ 1.0 g per larger item (by weighing); boxes for dry goods ≤ 0.2 g. Cleaned-in-place surfaces dry within 60 min after cleaning. | Mould, clumping of powders, bacterial growth. | M | T | B6 |
| HYG-025 | **Odour-neutral:** a box that held onion, fish or curry and was washed shall transfer no taint detectable in a triangle test to butter stored in it for 48 h at 4 °C. | Plastic boxes absorb odour. | S | T | B6 |
| HYG-026 | **Verified in operation:** every cleaning cycle shall be verified by recorded process parameters (temperature, time, flow or pressure, detergent dose, final-rinse quality) and cooking vessels additionally by inspection of the result (e.g. camera). A failed cycle is repeated once with an intensified programme; after a second failure the item is quarantined and the user informed. | No human looks at the ware. | M | D, R | B6 |
| HYG-027 | The cleaning process for every type of ware and every cleaned-in-place surface shall be validated once against HYG-020 to HYG-024 with worst-case soils and soil drying times, before the design is released. | Parameters are only proxies. | M | T (paper phase: A) | B6 |

### 7.4 What is cleaned when

| ID | Item | Zone | Trigger and latest time | Criteria | Prio | Trace |
|----|------|------|--------------------------|----------|------|-------|
| HYG-030 | Vessels, lids, tools, dosing and transfer parts, portioning tools | F | After each use; before contact with a different food, other than consecutive steps of the same component. Washing starts ≤ 60 min after use (M), ≤ 20 min (S). After class R: with disinfection. A shortened programme without disinfection and drying is permitted only for immediate re-use within the same meal, when the next use is heated to FSF-020 and the allergen profile does not change. | 020–024 | M | B6 |
| HYG-031 | Ingestion funnel, opening tools, package grippers at the cut | F | Per ING-013; at the latest at the end of each ingestion session. | 020–024 | M | B6, B10 |
| HYG-032 | Boxes and closures | F | Whenever emptied or their contents discarded, before any re-use; and at the latest after 14 days of continuous use for chilled goods, 12 months for frozen and ambient dry goods. Box exterior when soiled. | 020–025 | M | B6 |
| HYG-033 | Fixed food-contact stations (cutting, forming, cooking positions, baking cavity, plating station) | F | After each meal in which they were used; burnt-on residue removed at each cleaning, not accumulated. | 020–023 | M | B6, B7 |
| HYG-034 | Inner casing and splash surfaces of preparation, cooking, serving, washing and ingestion modules | S | Every day with use, ≤ 24 h after soiling; immediately (≤ 1 h) after a detected spill or boil-over. | 020, 024 | M | B6 |
| HYG-035 | Serving hatch space and door inner side, funnel surround (B), container interior (A) | S | Hatch: after every return of used dishes before the next presentation, daily, and after every spill; container (A) after every session. | 020, 024 | M | B6, DEC-6 |
| HYG-036 | Transport system parts in Zone S, grippers | S | Grippers daily; all other parts ≤ every 7 days; after any detected spill ≤ 1 h. | 020, 024 | M | B6 |
| HYG-037 | Storage interiors (ambient), dish store | S | After any detected spill or box leak (≤ 1 h for class R, ≤ 24 h otherwise); routinely ≤ every 30 days. | 020, 024 | M | B6 |
| HYG-038 | Cold storage interiors | S | As HYG-037, routinely ≤ every 90 days, without warming stored food above FSF limits. | 020 | M | B6 |
| HYG-039 | Fume, steam and condensate path; grease separator | S | ≤ every 7 days and when its sensor indicates loading; no grease filter to be washed by a human. | 020 | M | B6 |
| HYG-040 | Washing system itself: chambers, spray system, sump, filters, drains, hoses with standing water | S/F | Self-cleaning hot cycle (≥ 70 °C) ≤ every 7 days; descaling automatically as water hardness demands. | 020; no odour | M | B6 |
| HYG-041 | Waste container bay | S | At every container change, and ≤ every 7 days. | 020 | M | B6 |
| HYG-042 | All Zone F and S: intensified cleaning with disinfection | F, S | ≤ every 30 days; after holiday mode; after a spoilage, mould or pest event; after service access. | 020–024 | M | B6 |
| HYG-043 | Zone N | N | Stays clean by design for ≥ 12 months; inspected at the annual service. | no food soil | M | B6 |
| HYG-044 | Zone X (exterior fronts, handles, panel) | X | Smooth, closed, wipeable; hatch sill and funnel surround count as Zone S. Wiping the exterior like any furniture is the only cleaning left to the human (AS-08, OQ-08). | — | M | B6 |
| HYG-045 | Any Zone F or S surface | F, S | No surface shall remain both soiled and wet for > 4 h, and none soiled for > 24 h; in faults (UC-14) exceeding this, the intensified programme HYG-042 applies to the affected items. | — | M | B6 |

### 7.5 Hygiene of the machine's own systems

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| HYG-050 | Water for food and for final rinses shall be of drinking quality at the point of use: materials in contact with it approved for drinking water; no internal storage of fresh water for > 24 h; pipe sections without flow for > 72 h shall be flushed automatically before use. | Stagnation, Legionella, biofilm. | M | R, D | B12 |
| HYG-051 | Wet areas (wash chambers, sumps, drains, condensate paths) shall be dried or ventilated after use so that no mould or biofilm develops: no visible growth and no odour after 12 months of reference use. | The usual fate of dish washers and drip trays. | M | T (accelerated), A | B6 |
| HYG-052 | Scale shall not build up on Zone F/S surfaces, heaters, nozzles or sensors at water hardness up to 25 °dH (4.5 mmol/L); softening and descaling shall be automatic. | Hard water is common. | M | A, T | B12 |
| HYG-053 | Relative humidity inside the machine shall return below 65 % within 60 min after the end of cooking and cleaning; no condensation shall form in ambient storage, on electronics or in Zone N at any time. | Mould; dry goods; corrosion. | M | T | drv |
| HYG-054 | The machine shall offer no access or harbourage to insects and rodents: openings to the room > 1 mm screened or closed; no food residue left accessible; waste closed. | Pests. | M | I | drv |
| HYG-055 | Waste shall be contained so that liquids cannot leak into the machine and the container can be removed without the user touching waste. | HUM-012. | M | D | drv |

### 7.6 Food safety rules (time and temperature)

Default limits; national guidance may set stricter values (`research/06-hygiene-cleaning.md` takes precedence
where it cites a legal or normative value stricter than the one given here).

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| FSF-010 | Storage temperatures as CLD-002/003; ambient as STO-007. | — | M | T | B4 |
| FSF-011 | Ingestion cold chain: from the moment the user hands products to the machine until the box is inside cold storage: frozen ≤ 20 min, chilled ≤ 45 min (at 25 °C room temperature). | Thaw onset of thin frozen packs; chilled goods have already travelled home. | M | A, T | B10 |
| FSF-012 | Cold-storage excursion: if chilled air exceeds 7 °C for > 2 h, or frozen air exceeds −15 °C for > 2 h, the system shall alarm; boxes whose contents are calculated or measured to have exceeded 7 °C for > 4 h (chilled TCS) or 0 °C (frozen) shall be blocked, and discarded unless the user releases them knowingly. Thawed food shall never be refrozen raw. | Power loss, door fault. | M | D | drv |
| FSF-013 | Retrieval excursion: a chilled box shall be outside cold storage ≤ 10 min per retrieval and a frozen box ≤ 5 min; the cumulative time outside is recorded per box; chilled TCS contents reaching 120 min cumulative shall be used in the current meal or discarded. | Partial use of a box over days. | M | A, D | drv |
| FSF-014 | During preparation, class R food shall be above 7 °C for ≤ 30 min before its heating starts, other TCS food ≤ 60 min; longer waits only at ≤ 7 °C. | Danger zone. | M | A | drv |
| FSF-020 | Core temperature at the end of cooking: ≥ 72 °C for ≥ 2 min (or equivalent lethality) for poultry, minced meat, rolled or stuffed meat, sausages, egg dishes and all reheated food; ≥ 63 °C for ≥ 3 min for whole-muscle pork and fish; soups and sauces ≥ 85 °C in bulk. Whole-muscle beef, veal and lamb may be cooked to the ordered doneness (core ≥ 48 °C) provided all outer surfaces were seared to ≥ 70 °C. | Pathogen kill; a rare steak is "normal". Values per `research/06`, section 5.2. | M | T | drv |
| FSF-021 | FSF-020 shall be verified per batch by measurement (COK-013) for pieces ≥ 20 mm; for smaller pieces and liquids by a validated time–temperature profile of the vessel contents. | Evidence. | M | D, R | drv |
| FSF-022 | Low-temperature cooking: food shall pass from 10 °C to 60 °C core within ≤ 4 h. | Slow roasting. | M | A | drv |
| FSF-023 | Cooked food kept for later (SRV-021) shall be cooled per COK-022, stored at ≤ 4 °C for ≤ 48 h, reheated once to FSF-020, never stored again. | Leftovers are the highest-risk food. | M | D | drv |
| FSF-024 | Dishes with raw or undercooked animal products (X-14, soft-boiled egg, rare minced meat) shall be offered only after explicit opt-in per household and never for persons marked as vulnerable in the profile. | Informed choice. | M | D | drv |
| FSF-030 | Danger-zone rule: any food whose cumulative time between 7 °C and 60 °C — not counting continuous heating-up or cooling-down within the limits above — exceeds 2 h shall be discarded. This rule decides resume-or-discard after power loss, water failure, jam and stop. | One rule for all faults. | M | D, A | drv |
| FSF-031 | Hot holding: ≥ 65 °C, for ≤ 2 h (quality limit 30 min, COK-017). | — | M | T | drv |
| FSF-032 | Plated food not collected: reminders at 3 and 10 min; kept closed in the hatch or returned to holding; discarded 90 min after plating at the latest (cold RTE dishes: 120 min at ≤ 10 °C), dishes washed. | UC-06. | M | D | drv |
| FSF-040 | Any surface that touched class R food shall be cleaned with disinfection (HYG-021) before it touches RTE food or food that will not be heated to FSF-020 afterwards. Within one meal, separate vessel and tool instances shall be used for class R and RTE components. | Cross-contamination. | M | R, D | B6 |
| FSF-041 | Open class R food shall not be moved above open RTE food, clean ware or dishes, and its wash water shall not splash onto them. | Drip. | M | R | B6 |
| FSF-042 | Soil-bearing produce shall be washed (UO-10) before cutting or peeling on shared tools; wash water goes to drain. | Soil bacteria, grit. | M | R | drv |
| FSF-050 | Shelf life: every box has a use-by time = the earlier of (a) the date on the package and (b) ingestion time + shelf life after opening for its category and storage class. Defaults (conservative, editable table): raw minced meat and raw fish 1 day; raw poultry 2 days; other raw meat 3 days; cooked leftovers 2 days; opened dairy, tinned goods after opening, cut produce 3–5 days; hard cheese, eggs, whole produce per category; frozen 3–12 months; dry goods 6–12 months. | ING-008. | M | R, D | drv |
| FSF-051 | Food past its use-by time shall be blocked and handled per UC-17 within 24 h. For "best before" dates of ambient dry goods the user may extend once per box, up to the category limit. | Spoiled-food handling. | M | D | drv |
| FSF-052 | At ingestion, class R food not planned for a meal within its chilled shelf life shall be frozen (in portion-suitable amounts) unless the user objects. | Opening at ingestion shortens shelf life; avoids waste. | S | D | drv |
| FSF-053 | At each opening of a box of perishable food the contents shall be checked for signs of spoilage (at least camera: mould, discolouration, liquid; S: gas/odour sensing), with UC-17 on suspicion. | Dates do not catch everything. | S | D | drv |
| FSF-060 | The 14 allergens of Regulation (EU) 1169/2011 Annex II shall be tracked per product, per box and per meal, and shown with every meal. | Allergen information. | M | D | drv |
| FSF-061 | Cleaning between allergen-containing and other food shall meet HYG-022. Airborne allergenic powders (flour) shall be contained (PRP-014). | Cross-contact. | M | T | B6 |
| FSF-062 | The system shall not declare a meal "free from" an allergen that is present anywhere in the inventory unless the customer accepts the residual risk in the profile; a household setting "ban allergen" shall make ingestion refuse products containing it. | Honest limits of a shared machine. | M | D | drv |
| FSF-070 | Foreign bodies: besides INA-008, PRP-035 and HYG-018, a dish, box or vessel broken or chipped inside the machine shall be detected; exposed food discarded; fragments removed by the cleaning process or the user called. | Safety. | M | D, A | drv |

### 7.7 Hygiene records

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| HYG-060 | The system shall keep, per Zone F item and station, its cleaning state (clean / soiled with what, since when / quarantined) and refuse to use any item not "clean". | Enforcement. | M | D | B6 |
| HYG-061 | Cleaning, temperature and discard records shall be kept per CTL-009 and summarised for the user monthly (cycles run, failures, food discarded and why). | Trust; fault finding. | S | I | drv |

### 7.8 What the human still does

This list is exhaustive (GEN-003). Times are the user's own time per occurrence.

| ID | Human task | Frequency (reference household) | Time | Prio | Trace |
|----|------------|----------------------------------|------|------|-------|
| HUM-001 | Order meals; take dishes from the hatch. | Per meal | — | M | B8 |
| HUM-002 | Bring used dishes, glasses and cutlery back to the serving hatch, as they are (no scraping, sorting or rinsing). | Per meal | ≤ 1 min | M | B9, DEC-6 |
| HUM-003 | Exchange the organic waste container/liner; version A: also the packaging waste. | ≤ 2 × per week; packaging: ≤ once per ingestion session | ≤ 2 min | M | drv |
| HUM-004 | Refill consumables (detergent, rinse aid, salt, descaler), all from the front, without tools, without spilling into the machine. | ≤ once per 30 days (M), per 180 days (S), all at the same visit | ≤ 5 min | M | B6 |
| HUM-005 | Load groceries: version A — put packages into the container (INA-001); version B — scan and pour. | ≈ weekly | A: ≤ 3 s per item; B: ≤ 20 s per product | M | B10 |
| HUM-006 | Deal with ingestion rejects (identify in the UI or ingest via B). | ≤ 25 % of items (M), ≤ 10 % (S) | ≤ 30 s each | M | B10 |
| HUM-007 | Replace wear and filter parts (odour filter, water filter if any, blades, seals) as announced. | ≤ 2 × per year | ≤ 15 min | M | B13 |
| HUM-008 | Wipe exterior fronts (Zone X). | As any kitchen furniture | — | M | AS-08 |
| HUM-009 | Clear an unplanned stoppage following on-screen instructions. | ≤ 1 per 50 meals (REL-001) | ≤ 5 min | M | B13 |
| HUM-010 | Annual inspection and service. | 1 × per year | ≤ 2 h | S | B13 |
| HUM-011 | Sum of HUM-003, -004, -007, -009, -010: ≤ 10 min per week on average. | — | — | M | B1 |
| HUM-012 | No human task shall require touching food residue, wash water, soiled internal surfaces, blades or detergent concentrate, nor the use of tools, except HUM-007 (announced part exchange) and HUM-010. | "The human will not clean anything." | — | M | B6 |

---

## 8. Physical and interface constraints

### 8.1 Dimensions and layout

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| PHY-001 | Depth: no part of the closed machine shall extend more than 600 mm from the wall, including fronts, rear service space for pipes and cables, and wall unevenness allowance; handles and the hatch sill may add ≤ 30 mm. | Brief: 60 cm deep. | M | I | B12 |
| PHY-002 | Height: 2 000–2 200 mm from the floor, including feet, plinth and any top ventilation parts; the design shall state its height and the minimum room height needed for installation. | Customer decision (was 2 000 mm in the brief). | M | I | B12, DEC-11 |
| PHY-003 | Module widths shall be multiples of 150 mm, preferably 300, 450, 600, 900 or 1 200 mm; no module wider than 1 200 mm. | Kitchen grid; handling; fits between walls with standard fillers. | M | I | B12 |
| PHY-004 | Total wall length of the MVC: ≤ 3 600 mm (M), ≤ 3 300 mm (S), ≤ 3 000 mm (C), straight or L-shaped. The larger-storage configuration (CAP-026) may use ≤ 4 200 mm. | Estimate: ambient and cool storage ≈ 0.45 m (78 positions + reserve at ≈ 168 positions per metre, `research/03`); cold storage 1.2 m (chilled 45 and frozen 20 positions still need two cells of 33–45 positions each); process cell 0.9–1.2 m (for 4 persons: 3 cooking positions, a ≥ 35 L cavity and 5 L vessels instead of 4 positions, 45 L and 9 L); washing 0.6 m → ≈ 3.15–3.45 m. 3.3 m is therefore a realistic target; 3.0 m needs in addition chilled and frozen in one 600 mm cell (≥ 65 positions, 2 200 mm height) or ambient storage inside another module. | M | I | B12, B13, DEC-17, DEC-18, DEC-19 |
| PHY-005 | The system shall be installable in a straight line and, optionally, around one inside corner of 90° ("L"), left- or right-handed, with leg lengths free on the 150 mm grid (each leg ≥ 1 200 mm). | Brief. | M | R | B12 |
| PHY-006 | Straight and L layouts shall use the same modules; only a corner element and transport parts may differ. | Modularity. | M | R | B11, B12 |
| PHY-007 | In an L layout, ≥ 50 % of the corner cell (600 × 600 mm × height) shall be functionally used, and the transport system shall pass the corner. | Corners are the classic dead space. | S | A | B13 |
| PHY-008 | Volume budget: each module shall state the split of its enclosed volume into storage/process/ware, transport, mechanisms, utilities and unused; unused voids > 10 L shall be justified; ≥ 85 % of the system's enclosed volume shall be functional. | "Does not waste footprint space." | M | A | B13 |
| PHY-009 | After installation, no access from the rear, the sides or the top shall be needed for operation, human tasks, service or module exchange. | Built in between walls and under ceilings. | M | R | B13 |
| PHY-010 | Open doors, drawers, the hatch door and removable containers shall project ≤ 600 mm into the room; all human tasks shall be possible with 1 000 mm free floor depth in front. | Kitchen aisle. | M | I | B12 |
| PHY-011 | Operating mass including a full stock of food and water: ≤ 200 kg per 600 mm of width (est.), load per foot ≤ 1.0 kN, on feet with ≥ 20 cm² contact area each. | Domestic floors (2 kN/m² design imposed load) and floor coverings; comparable to a loaded fridge-freezer. | M | A | B12 |
| PHY-012 | Delivery: every module (or its delivered sub-units) shall pass a door opening of 780 × 1 950 mm and a 900 mm wide stair with a 180° landing, tilted if necessary; no sub-unit heavier than 80 kg (M), 50 kg (S). | Getting it into a flat; modules up to 2 200 mm tall must tilt or split. | M | A | B11, DEC-11 |
| PHY-013 | Levelling: adjustable for floor unevenness of ± 15 mm over the system length; the system shall be fixed to the wall against tipping. | Installation. | M | I | B12 |
| PHY-014 | The fronts shall form a closed, flat, easily wiped surface in a regular grid. | It is a kitchen in a home. | S | I | B12 |
| PHY-015 | Connection points of the house installation (water valve, drain, sockets) may lie anywhere behind the lower 600 mm of the system; isolating valve and mains isolator shall be reachable from the front without tools after installation. | Installation reality; service. | M | I | B12 |

### 8.2 Utilities

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| UTL-001 | Water supply: one connection to cold drinking water, 2.2–5 bar static (functional over the full range; pressure-proof to 10 bar), 5–25 °C; the machine shall need ≤ 10 L/min. | Brief. | M | T | B12 |
| UTL-002 | No hot-water supply is available; the machine heats all water it needs. | Brief: cold only. | M | R | B12 |
| UTL-003 | Drain: one connection to the house waste pipe (DN 40/50, with odour trap); discharge ≤ 20 L/min, ≤ 75 °C, solids ≤ 1 mm; the machine shall lift waste water to a connection up to 900 mm above the floor. | Brief; domestic drain practice. | M | T | B12 |
| UTL-004 | One connection point per utility for the whole system; distribution to modules through the module interfaces (MOD-012, MOD-013). | Installation; modularity. | M | I | B11 |
| UTL-010 | Electrical supply: three-phase cooker connection 400 V 3N~ (3 × 230 V ± 10 % to neutral), 50 Hz, protected at 3 × 16 A: about 11 kW. The machine shall draw ≤ 15 A on each phase at any time (inrush averaged over 1 s), and ≤ 10.3 kW in total. | Brief: "220 V power"; customer decision: the cooker connection is available and designs may rely on it. | M | T | B12, DEC-1 |
| UTL-011 | A power manager shall keep every phase within UTL-010 by distributing loads over the phases and scheduling them, in this priority: safety functions, cold storage, control, food being cooked, hot holding, washing, everything else. It shall be part of the scheduling (CTL-005). | Power management remains required (DEC-1). **Consequence of 3 × 16 A:** each phase carries about 3.4 kW, so e.g. two cooking positions at full power and the baking cavity can heat together, but a third full-power position, wash-water heating and drying must be interleaved. No single load may exceed one phase (3.4 kW) unless it is a three-phase device. | M | A, T | B12, DEC-1 |
| UTL-012 | The machine should remain usable, with longer cooking and cleaning times, on a single 230 V / 16 A circuit (≤ 3.5 kW), by configuration of the supply module and the power manager only. | Kitchens without a cooker connection; time targets do not apply in this mode. | C | A | B12 |
| UTL-013 | Earth leakage of the whole system shall stay ≤ 10 mA in normal operation. | Must not trip the 30 mA residual-current device of the house. | M | T | drv |
| UTL-014 | Network: wired Ethernet (M) and Wi-Fi (S) to the home router; functions without Internet as CTL-012. | Brief: Internet. | M | I | B12 |

### 8.3 Environment: room conditions, heat, steam, odour

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| ENV-001 | Operating room conditions: 10–32 °C, 20–80 % relative humidity non-condensing, altitude up to 2 000 m (boiling point accounted for in recipes). | Domestic rooms; climate class of household fridges. | M | T, A | B12 |
| ENV-010 | No ducted exhaust to the outside is assumed (OQ-02). Moisture released into the room: ≤ 0.3 kg per reference meal including its cleaning; steam shall be condensed and drained. | Cooking and washing release 1–2 kg of vapour per meal; without a duct this would go into the room and the machine. | M | T, A | B12, drv |
| ENV-011 | Air returned to the room shall be free of visible fumes; grease aerosol shall be separated to ≥ 90 % by mass (est.); cooking odour in the room after pan-frying shall be no stronger than with a good recirculating cooker hood (panel comparison). | Home. | M | T | drv |
| ENV-012 | Each module design shall state its heat release to the room (average and peak); the system shall work at 32 °C room temperature in a closed 12 m² kitchen without exceeding any internal temperature limit (STO-007, CLD-002, electronics). | All 7–10 kWh/day end up as heat, partly in the drain. | M | A | B12 |
| ENV-013 | Walls, floor and adjacent furniture shall not exceed 60 °C, and no condensation shall form on them or on the machine's exterior. | Building fabric; mould. | M | T | drv |
| ENV-014 | Optional connection to a ducted extraction. | Where available, better odour removal. | C | R | B12 |

---

## 9. Modularity

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| MOD-001 | The system shall be divided into these modules: ambient storage; cold storage; transport; preparation; cooking and baking; portioning and serving; washing and cleaning; ingestion (A or B); frame, utilities and safety infrastructure; control. Preparation, cooking and portioning may share one enclosure ("process cell") but remain separately designed sub-modules with defined internal interfaces. | Brief. | M | R | B11 |
| MOD-002 | **Designed independently:** a module shall depend on other modules only through the interfaces frozen in the architecture document (mechanical, transport hand-over, electrical, data, water/utilities, air). No module design shall assume internals of another. | Brief. | M | R | B11 |
| MOD-003 | **Built and tested independently:** each module shall have its own supporting structure, stand on its own, and be fully testable on its own with an interface simulator (power, data, utilities) and test items at its hand-over points. | Parallel build; acceptance per module. | M | D | B11 |
| MOD-004 | **Replaced independently:** one module shall be removable and re-installable from the front in ≤ 2 h by 2 persons, without removing neighbouring modules and without emptying other modules. Cold storage shall stay in operation. | Repair, upgrade. | M | D, A | B11, B13 |
| MOD-010 | Mechanical interface: defined datum faces, fixing points and tolerances between neighbouring modules and to the transport system; modules shall be joinable without shimming or machining; residual misalignment shall be absorbed by automatic calibration (TRN-009). | Buildability. | M | R | B11 |
| MOD-011 | Transport hand-over interface: one standard definition of a hand-over point (pose, approach envelope, item types, supporting features, presence sensing, handshake) used by all modules; each module has ≥ 1 such point. | The transport system is the binding element. | M | R | B11 |
| MOD-012 | Electrical interface: one standard power connection per module, individually switchable and protected, with a declared maximum and average power; protective-earth continuity through the connector. | Independent operation and replacement. | M | R, I | B11 |
| MOD-013 | Utility interface: standard couplings for fresh water, wash media (if centralised), drain and exhaust air, self-sealing on disconnection (≤ 5 mL loss), mechanically coded against wrong connection. | Replacement without a plumber. | M | R, D | B11 |
| MOD-014 | Data interface: one standard bus and protocol for all modules; each module reports type, version, capabilities and hand-over points (self-description); a separate hard-wired or safety-rated channel carries the stop and safe-state signals. | Discovery; safety independent of software. | M | R, D | B11 |
| MOD-015 | Interfaces shall be versioned and frozen in the architecture; module designers raise conflicts as open issues rather than deviate. | Project rule. | M | R | B11 |
| MOD-016 | The order of modules along the transport system should be free, subject only to stated zoning rules (e.g. ambient storage not next to an unshielded heat source). | Fits different kitchens. | S | R | B11, B12 |
| MOD-020 | For each module an interface simulator/test specification shall be defined so that the module can be accepted before integration. | MOD-003. | M | R | B11 |
| MOD-030 | **Minimum viable configuration (MVC):** one ambient storage, one cold storage (chilled + frozen), transport, preparation, cooking and baking, portioning and serving with hatch, washing and cleaning including the dish washer, ingestion version B, frame/utilities, control. The MVC shall meet all M requirements for the reference household. | Smallest buildable system. | M | R | B11 |
| MOD-031 | **Standard configuration:** MVC with ingestion version A added; version B's function remains available as fallback. | Brief: both versions. | M | R | B10 |
| MOD-032 | **Extensions** without redesign of existing modules: up to 3 further ambient storage modules; a second cold storage; L corner; a second ingestion module. The control system adapts automatically (CTL-014). | Growing households, stock-keeping. | S | R | B11 |
| MOD-033 | The transport system, as the one shared element, shall have the highest reliability target of all modules (REL-005) and a manual fallback (TRN-015); its failure shall not cause loss of stored food. | Single point of failure. | M | A | B11 |

---

## 10. Build, maintainability and robustness

### 10.1 Build

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| BLD-001 | ≥ 85 % of BOM line items and ≥ 80 % of BOM value shall be catalogue parts purchasable in single quantities by a private buyer in the EU; every part with manufacturer part number, supplier and price. | Brief: standard parts; off-the-shelf remains preferred, but custom stainless parts are allowed where necessary (DEC-21). | S | R | B13, DEC-21 |
| BLD-002 | Non-catalogue parts shall be limited to: (a) parts printable on a desktop FDM printer with a build volume of 250 × 210 × 210 mm in PETG, ASA, PA or TPU (within HYG-015 and BLD-003); (b) cut-to-length profiles, laser-cut and bent sheet metal, and simple turned or milled parts ordered from fabrication services from the supplied drawings; (c) where necessary, stainless steel parts laser-cut, bent, welded and polished by a job shop to the hygienic requirements of section 7 (welds continuous, ground and polished to HYG-012). Each custom part shall be justified against an off-the-shelf alternative. No injection moulding or casting; no welding by the builder. | Brief: "off-the-shelf parts and a 3D printer"; customer decision DEC-21. | M | R | B13, DEC-21 |
| BLD-003 | Printed parts shall not be used where HYG-015 forbids, where they would exceed their material's heat-deflection temperature minus 20 K, or as the sole load path for holding hot or heavy (> 2 kg) items above humans' reach zones without a safety factor ≥ 4. | Printed plastic creeps, softens and is anisotropic. | M | R | B13 |
| BLD-004 | Cost (parts, single unit, retail prices incl. VAT, without labour, tools and the printer) shall be estimated honestly per module and reported for every concept and design. Targets: MVC ≤ EUR 25 000, stretch ≤ EUR 15 000; ingestion version A ≤ EUR 4 000 extra; each additional storage module ≤ EUR 2 500 (all est.). Cost is **not** a pass/fail criterion for concept selection at this stage; cost optimisation is a later step (DEC-22). | Customer decision; prior art places an automated kitchen in the fitted-kitchen class (EUR 20–60 k, `research/01`). | S | A (BOM) | B13, DEC-22 |
| BLD-005 | Tools needed to build: hand tools (hex keys, screwdrivers, spanners, torque wrench, pliers), cordless drill, deburring and tapping tools, crimping and soldering tools, multimeter, desktop FDM printer, PC. No machine tools, welding equipment or special calibration equipment. | Buildable by a skilled amateur. | M | R | B13 |
| BLD-006 | Build documentation per module: BOM, drawings and print files, wiring and plumbing diagrams, assembly sequence, commissioning and test procedure. | Reproducibility. | M | R | B13 |
| BLD-007 | Variety shall be limited across modules: one profile system, one fastener family (≤ 15 fastener types), ≤ 3 motor/driver families, one controller family, one connector family per function. | Spare parts, learning effort. | S | R | B13 |
| BLD-008 | Mains-voltage functions shall be realised with finished, certified components and appliances (power supplies, relays, heaters, appliances with their own protection), so that builder-made mains wiring is limited to connecting them; this wiring shall be inspected by a qualified electrician. | Electrical safety of a self-built machine. | M | R | B13 |
| BLD-009 | Assembly effort of the MVC: ≤ 400 person-hours after parts are available (est.). | Feasible as a project. | S | A | B13 |

### 10.2 Maintainability

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| MNT-001 | Every LRU shall be reachable and exchangeable from the front, without moving the machine or a module. | Brief: easily accessible. | M | R, D | B13 |
| MNT-002 | Exchange time per LRU, one person, hand tools of BLD-005 only: ≤ 30 min for 90 % of LRU types, ≤ 60 min for all. | MTTR. | M | A, D | B13 |
| MNT-003 | Mean time to repair including diagnosis: ≤ 45 min, given the spare part. | Availability. | M | A | B13 |
| MNT-004 | The system shall identify the faulty LRU correctly in ≥ 90 % of failures, and guide the exchange step by step on the UI. | Diagnosis is usually the longest part. | S | A, D | B13 |
| MNT-005 | Every place where an item can jam or fall shall be reachable by an adult's hand from the front after the safe state is established, without tools; clearing time ≤ 5 min. | UC-13. | M | D | B13 |
| MNT-006 | After an LRU exchange the module shall recalibrate and self-test automatically; no manual adjustment with measuring instruments. | No special skills. | M | D | B13 |
| MNT-007 | A wear-parts list shall state life, exchange time and price per part; yearly cost of wear parts and consumables at reference use ≤ EUR 300 (est.). | Running cost. | S | A | B13 |
| MNT-008 | All LRUs shall be catalogue parts or reproducible from the build documentation; a recommended spares kit shall cost ≤ EUR 500 (est.); parts with a delivery time > 4 weeks shall be in the kit. | Spare parts. | M | R | B13 |
| MNT-009 | Cables, hoses and connectors shall be labelled and keyed against wrong connection. | Repair errors. | M | I | B13 |
| MNT-010 | Service on any other module shall not interrupt cold storage, and cold storage service shall be possible with the food transferred or kept cold for ≥ 2 h. | Food loss. | M | A | B13 |

### 10.3 Robustness and lifetime

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| REL-001 | ≥ 98 % of ordered meals shall be completed without human intervention (M), ≥ 99.5 % (S), measured over ≥ 300 meals of the corpus mix. | "Fully automatic"; one intervention per 50 meals ≈ one every 2–3 weeks. | M | T (later), A (failure-mode analysis) | B1, B13 |
| REL-002 | No fault or combination of a single fault with power loss shall lead to unsafe food being served; in doubt the food is discarded. | Food safety over availability. | M | A | drv |
| REL-003 | Design life: 10 years at reference use = about 7 300 meal runs, of which 3 650 full warm meals. | Brief: robust for everyday use. | M | A | B13 |
| REL-004 | Every mechanism shall be designed for the life-cycle counts of the table below × 1.5, or be an LRU with a declared exchange interval of ≥ 2 years. | Translates lifetime into design loads. | M | A | B13 |
| REL-005 | Mean time between failures needing a part exchange: system ≥ 6 months (M), ≥ 12 months (S); transport system alone ≥ 5 years. | Everyday use. | M | A | B13 |
| REL-006 | Availability for cooking: ≥ 98 % of days. | — | M | A | B13 |
| REL-007 | Tolerance of input variation: natural variation of produce (size, shape, ripeness within PRP-020), fill levels, package variation, and foreseeable misuse (foreign object in the ingestion container or funnel, overfilled container, wrong dish at the hatch, hatch blocked, door left open) shall not damage the machine. | Real households. | M | A, T | B13 |
| REL-008 | Cold storage shall keep its temperature when any other module or the central control fails. | No loss of stored food. | M | A, T | B4 |
| REL-009 | The system shall withstand supply disturbances without damage and resume automatically: voltage dips and interruptions, water pressure surges up to 10 bar, water interruptions. | Fault recovery. | M | A, T | B12 |

**Life-cycle counts for 10 years of reference use (est.; REL-004).**

| Mechanism / function | Per day | In 10 years |
|----------------------|---------|-------------|
| Ambient storage retrieve-and-return cycles | 30 | 110 000 |
| Chilled storage retrieve-and-return cycles; thermal exit openings | 25; 50 | 91 000; 183 000 |
| Frozen storage retrieve-and-return cycles; thermal exit openings | 5; 10 | 18 000; 37 000 |
| Transport moves (boxes, vessels, tools, dishes, glasses) | 200 | 730 000 |
| Box closure open/close (all boxes; per box ≤ 5 000) | 170 | 620 000 |
| Dosing operations | 50 | 183 000 |
| Tool changes | 25 | 91 000 |
| Cutting and peeling operating time | 8 min | 490 h |
| Mixing, kneading, stirring operating time | 1.5 h | 5 500 h |
| Cooking positions on-time (sum); baking cavity on-time | 2 h; 0.5 h | 7 300 h; 1 800 h |
| Internal ware wash cycles | 2.5 | 9 100 |
| Dish-set wash cycles | 1.5 | 5 500 |
| In-place cleaning cycles; valve operations | 1.5; 40 | 5 500; 146 000 |
| Serving hatch door cycles (meals, drinks, dish returns) | 10 | 37 000 |
| Dish handling (store → plate → hatch, hatch → store) | 12 | 44 000 |
| Wash cycles per vessel or tool | up to 2 | 7 300 |
| Wash cycles per box | — | ≤ 1 000 |
| Ingestion: items | 6 (40 per week incl. guest shops) | 22 000 |

Note: household dish washers are typically designed for about 280 cycles per year; an off-the-shelf unit
used for internal ware at 2–3 cycles per day is a declared LRU under REL-004 or needs a commercial-grade unit.

---

## 11. Safety, regulatory, security

These are requirements, not designs. A risk assessment decides the measures.

### 11.1 General

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SAF-001 | A risk assessment following EN ISO 12100 shall be made for each module and for the system, covering operation, human tasks, faults, service, building and foreseeable misuse including children. | Method. | M | R | drv |
| SAF-002 | Safety functions shall be implemented independently of the application software (CTL-015), with a performance level determined per EN ISO 13849-1 from the risk assessment. | Integrity. | M | R | drv |
| SAF-003 | Loss of power, of the network, of water or of the control system shall lead to a safe state without human action. | Fail-safe. | M | T, A | drv |

### 11.2 Fire and unattended cooking

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SAF-010 | No open flame; no heating surface accessible to room air outside the closed cooking space. | Unattended. | M | I | B7, drv |
| SAF-011 | Every heater shall have a temperature limiter independent of the control system that cuts power before fat can ignite: vessel base and cavity walls ≤ 300 °C under any single fault; normal control limit ≤ 260 °C. | Oil self-ignites at about 350–370 °C. | M | T | drv |
| SAF-012 | Heat shall be applied only when a vessel is present and its contents and their mass are known; heating of an empty or unexpectedly dry vessel shall stop within 60 s. | Dry-boiling is the classic cause of kitchen fires. | M | T | drv |
| SAF-013 | Smoke, flame and abnormal temperature shall be detected in the cooking space and the exhaust path; on detection all heaters shall be de-energised within 2 s, the space closed, ventilation put into the safe state, and an alarm raised (UI-008). | Detection. | M | T | drv |
| SAF-014 | The cooking space shall contain a fire of the largest permitted quantity of fat (COK-021) without flame or burning material leaving the space and without igniting adjacent modules, walls or furniture; materials in and around the cooking space shall be non-combustible; printed plastic parts are not permitted there. | Containment. | M | T, A | drv |
| SAF-015 | An automatic means to extinguish a fire in the cooking space shall be provided. | Containment alone may be slow; nobody may be at home. | S | T | drv |
| SAF-016 | Grease shall not accumulate in the exhaust path (HYG-039). | Secondary fire load. | M | R | drv |
| SAF-017 | Alarms shall be audible in the home (≥ 75 dB(A) at 1 m) and sent to the app; an output for a home alarm system should be provided (C). | Unattended operation. | M | T | drv |

### 11.3 Burns and scalding

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SAF-020 | Parts hotter than 60 °C, liquids hotter than 55 °C and steam shall not be accessible to a human: enclosures and doors to such spaces shall be locked until the temperature has fallen, including after power loss. | Scalding. | M | T | drv |
| SAF-021 | Accessible external surfaces: ≤ 50 °C. The areas by which a dish is grasped at the hatch: ≤ 55 °C. Hot food is indicated as such at the hatch. | Burn thresholds for brief contact; children. | M | T | drv |
| SAF-022 | Opening the hatch or any door shall not release steam, hot air above 50 °C or spray towards the human. | Scalding. | M | T | drv |
| SAF-023 | A spill of the largest vessel's hot contents shall be retained inside the machine and drained; it shall not reach the room, the floor or electrical parts. | 4 L of boiling liquid. | M | A, T | drv |

### 11.4 Mechanical hazards

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SAF-030 | Ingestion container (A): picking, cutting and moving parts shall be inaccessible while the container is open to the human (interlocked cover with guard locking, or a separating barrier); motion shall stop before access is possible. | Hands next to a cutting machine. | M | T | B10, drv |
| SAF-031 | Funnel (B) and all other openings to the room: no hazardous part shall be reachable with the jointed test finger and the child-finger probes of EN 61032 (probes B, 18, 19), with covers in any position. | Children. | M | T | B10, drv |
| SAF-032 | Serving hatch: door closing force ≤ 50 N (M), ≤ 25 N (S), reversing on contact within 0.5 s; no shearing or drawing-in points at door edges; no moving mechanism within reach through the open hatch while the door is open. | Pinch and crush. | M | T | B8, drv |
| SAF-033 | All other moving, cutting, hot or pressurised parts shall be behind fixed guards (removable only with a tool) or interlocked movable guards. | Basic machinery safety. | M | I | drv |
| SAF-034 | Service mode (MODE-004): energy isolated and lockable; stored energy (springs, pressure, raised loads, capacitors) released or blocked; hot parts cooled or indicated; blades covered or parked in guards; blades and other sharp tools exchangeable without touching the edge. | Maintenance is when people get hurt. | M | D, R | B13 |
| SAF-035 | Forces and energy of mechanisms that a human can reach during jam clearing in the safe state shall be zero (de-energised, no gravity-driven motion). | UC-13. | M | T | drv |
| SAF-036 | Stability: the installed system shall not tip with all doors open and 25 kg applied to any open door, drawer or sill. | Child climbing. | M | T | drv |
| SAF-037 | No space accessible from the room shall be able to trap a child or pet; any accessible space > 40 L shall be openable from inside or not closable with an occupant detected. | Entrapment. | M | R, T | drv |

### 11.5 Child safety

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SAF-040 | A child lock shall prevent ordering, opening of the ingestion container, the consumables and waste compartments, and service mode. | Unsupervised children. | M | D | drv |
| SAF-041 | Detergent and other chemical stores shall be inaccessible to children, and refilled from closed containers without open handling of concentrate. | Poisoning, eye injury. | M | I | drv |
| SAF-042 | Small parts, blades and hot items shall never be presented at the hatch; only dishes with food (or a requested box, UC-18). | Foreseeable reach of a child. | M | R | drv |

### 11.6 Electrical safety near water; leaks

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SAF-050 | The stop control (UI-010) and the mains isolator shall bring the system into the safe state within 1 s; the isolator shall be lockable. | Emergency and service. | M | T | drv |
| SAF-051 | Protection class I throughout, with all touchable conductive parts bonded to protective earth; supply via a 30 mA residual-current device (house installation, assumed). | Shock protection. | M | T, I | drv |
| SAF-052 | Electrical parts inside Zone F/S shall be rated for the cleaning process there (at least IP65; IPX9 where exposed to hot jets). Actuators and sensors in Zone F/S should run on safety extra-low voltage (≤ 24 V DC). | Water and electricity in one enclosure. | M | I, T | drv |
| SAF-053 | Water from any single leak, hose failure or overflow shall not reach live parts: electrical compartments above or sealed from water paths; every wet module has a base tray with leak detection. | Shock, fire. | M | A, T | drv |
| SAF-054 | On a detected leak the supply shall be shut at the inlet within 2 s; water released into the room ≤ 1 L; the supply valve is closed whenever no water is being drawn and on loss of power. | Water damage in an unattended home. | M | T | drv |
| SAF-055 | No single valve or sensor failure shall cause overflow of a vessel, sump or tray. | Flooding. | M | A | drv |
| SAF-056 | Where an off-the-shelf appliance is modified (e.g. oven door, orientation or controls, DEC-24), its safety functions (door interlocks, thermal cut-outs, leak protection) shall remain effective or be replaced by equivalent ones, its refrigerant circuit untouched, and nothing added inside a compartment cooled with flammable refrigerant shall be a potential ignition source. | Modifying appliances voids their certification. | M | R | B4, B13, DEC-24 |

### 11.7 Water and drain protection

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SAF-060 | The drinking-water supply shall be protected against backflow from the machine according to EN 1717 for the highest fluid category present (wash water, food, detergent: category 5 → air gap or equivalent), as also required by EN 61770. | Protection of the house and public water supply. | M | R, T | B12 |
| SAF-061 | Waste water shall not flow or siphon back from the drain into the machine. | Sewage into a food machine. | M | T | B12 |

### 11.8 Regulatory awareness

The machine is first built as a prototype for private use (AS-13); formal conformity assessment is a non-goal
(NG-07). It shall nevertheless be designed so that nothing precludes later conformity. Classification is to
be confirmed by a regulatory expert (OQ-15).

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| REG-001 | Designers shall apply, as design guidance, the essential safety requirements of the Low Voltage Directive 2014/35/EU with EN 60335-1 and the relevant parts (-2-5 dish washers, -2-6 hobs and ovens, -2-14 kitchen machines, -2-24 refrigerating appliances, -2-31 range hoods), and those of the Machinery Directive 2006/42/EC / Machinery Regulation (EU) 2023/1230 (applicable from 20 January 2027) for the mechanical hazards, whichever is stricter per hazard. | Household appliances fall under the LVD and are excluded from machinery legislation, but this machine has hazards (autonomous motion, cutting, unattended remote operation) that the appliance standards do not fully cover. | M | R | drv |
| REG-002 | EMC Directive 2014/30/EU; Radio Equipment Directive 2014/53/EU if radio is used; RoHS 2011/65/EU; General Product Safety Regulation (EU) 2023/988; Cyber Resilience Act (EU) 2024/2847 — to be observed as design guidance. | Awareness. | S | R | drv |
| REG-010 | Every Zone F material shall comply with Regulation (EC) 1935/2004, plastics with Regulation (EU) 10/2011, and be produced under Regulation (EC) 2023/2006; a supplier declaration of compliance for the intended use (temperature, fatty/acidic food, repeated use) shall be on file for every Zone F part in the BOM. | Food-contact materials. | M | R | B6 |
| REG-011 | Fluorinated non-stick coatings (PTFE/PFAS) should be avoided. | Pending restrictions; coating wear under machine cleaning. | S | R | drv |
| REG-012 | Hygienic design shall follow EN 1672-2 and EN ISO 14159 (and EHEDG guidelines 8 and 13 as practice). | Basis of section 7. | M | R | B6 |
| REG-013 | Materials in contact with drinking water shall be approved for it in the country of installation. | Water quality. | M | R | B12 |
| REG-014 | No food waste shall be macerated into the drain; waste-water discharge shall respect UTL-003 and WSH-016. | Municipal waste-water rules. | M | R | B12 |

### 11.9 Security and data privacy

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SEC-001 | The online product look-up shall transmit only the product number and what the protocol technically requires; no user identity, location, inventory, consumption or household data. Look-ups are cached (ING-004) and the database's terms of use and licence observed. | Shopping data reveals health, religion and habits. | M | I (traffic inspection) | B10 |
| SEC-002 | Household data (inventory, meals, profiles, allergy information, records) shall be stored locally and leave the home only after explicit opt-in per purpose; the user can export and delete all of it. | GDPR principles; allergy data is health data. | M | I, D | drv |
| SEC-003 | Cameras shall view only the machine interior and items; images stay local; no microphone is active without opt-in. | Privacy at home. | M | I | drv |
| SEC-004 | The system shall be fully usable without any cloud account. Remote access shall be authenticated and encrypted; no default passwords; no service reachable from the Internet unless the user enables it. | Lifetime of 10 years outlasts cloud services. | M | I, T | drv |
| SEC-005 | No command from the network shall be able to override a safety function; remote start of heating requires the local safety conditions to be met and verified by the machine. | A hacked cooker is a fire hazard. | M | A, T | drv |
| SEC-006 | Software updates shall be authenticated and installed only with user consent (CTL-020). | Integrity. | M | D | drv |

---

## 12. Assumptions, non-goals, open questions

### 12.1 Assumptions

| ID | Assumption |
|----|------------|
| AS-01 | The machine occupies its own stretch of kitchen wall and replaces the conventional kitchen there; it contains no worktop, hob or sink for human use. |
| AS-02 | Installation in the EU (first: Germany): 230/400 V, 50 Hz, protective earth, 30 mA residual-current device, metric threads and EN standards. "220 V" in the brief means the nominal 230 V mains. |
| AS-03 | The three-phase cooker connection (UTL-010) is available for the machine alone (DEC-1). |
| AS-04 | Cold-water valve and drain are within or directly beside the machine's length, as for a sink or dish washer. |
| AS-05 | No ducted exhaust to the outside (ENV-010). |
| AS-06 | Internet through the home router, not guaranteed to be always on. |
| AS-07 | Users are cooperative adults who follow loading instructions; children may be near the machine unsupervised. |
| AS-08 | Wiping the exterior fronts is acceptable as ordinary housekeeping, not as "cleaning the machine" (HUM-008). |
| AS-09 | Food is bought in European supermarkets, packaged as described in `research/07-ingestion-packaging.md`. |
| AS-10 | "Traditional meals" as defined in MEAL-001. |
| AS-11 | The machine owns a defined dish set including glasses and cutlery (SRV-016); it washes, stores and dispenses it (DEC-6). Household crockery outside the set is not handled. |
| AS-12 | Reference household: 2 persons, 2 warm meals per day; guests occasionally, at most 4 persons per meal (DEC-18, DEC-19). |
| AS-13 | One-off prototype for private use; designed to the standards named, not formally certified. |
| AS-14 | Heated indoor room, domestic floor, water hardness up to 25 °dH. |
| AS-15 | The human carries waste from the machine's containers to the household bins. |
| AS-16 | The machine may choose where and how each product is stored; users do not need to find food in it except through UC-18. |

### 12.2 Non-goals

| ID | Non-goal |
|----|----------|
| NG-01 | Preparing beverages (coffee, tea, smoothies, cocktails, carbonating); storing bulk beverage crates (water, beer). Pouring stored drinks is a function (SRV-022). |
| NG-02 | Laying and clearing the table; carrying dishes between hatch and table. |
| NG-03 | Handling crockery, cookware or cutlery that is not part of the machine's dish set; hot drinks cups and serving of coffee or tea. |
| NG-04 | Buying food: the system produces a shopping list (CTL-016) but does not order or receive deliveries. |
| NG-05 | Manual cooking by humans in or on the machine. |
| NG-06 | Commercial throughput, restaurant or canteen use, meals for more than 4 persons in one run. |
| NG-07 | Formal certification or CE marking in this project. |
| NG-08 | Cleaning the room, the exterior fronts, or anything outside the machine. |
| NG-09 | The capabilities excluded in section 5.4. |
| NG-10 | Guaranteed allergen-free or medically prescribed diets; infant food preparation and sterilisation. |
| NG-11 | Pet food; non-food items; medicines. |
| NG-12 | Operation outdoors, in vehicles, or in unheated rooms. |
| NG-13 | Storing or serving ambient breakfast goods (bread, muesli, cereals) and snacks (DEC-16); in the MVC, storing non-cooking chilled goods (breakfast dairy, cold cuts for bread, table drinks), which may live in a separate fridge (DEC-17). |

### 12.3 Open questions for the customer

Designers shall use the **default** until the customer decides; the design shall not preclude the alternative
where the last column says so.

| ID | Question | Default assumption for the design | Keep alternative open? |
|----|----------|-----------------------------------|------------------------|
| OQ-01 | *Closed by DEC-1:* a three-phase cooker connection (400 V 3N~, 3 × 16 A) is available. | UTL-010; power management still required (UTL-011). | Single-circuit fallback: UTL-012 (C). |
| OQ-02 | Is a ducted exhaust to the outside available? | No: recirculation with grease separation, odour filter and steam condensation (ENV-010, -011). | Yes: ENV-014. |
| OQ-03 | *Closed by DEC-6:* used dishes are returned at the serving hatch; the machine washes, dries, stores and dispenses its own dishes. | WSH-001 to -003, SRV-014 to -016, -027, HUM-002. | — |
| OQ-04 | *Closed by DEC-19 (superseding DEC-10):* 1–4 persons per meal. | CAP-001; reference household 2 persons × 2 warm meals/day (DEC-18). | — |
| OQ-05 | The brief says every package is cut open at ingestion. The project ruling DEC-3 (pending customer objection) adds the STOW lane: tins, jars, cartons, tubs, vacuum packs are stored sealed and opened just in time. Does the customer object? | Two lanes, DECANT and STOW (ING-018). | If decant-only were required: CAP-010's 14- and 21-day autonomy would no longer apply to those products. |
| OQ-06 | *Closed by DEC-7:* ingestion A minimum one by one, jumbled pile as target. | INA-001. | — |
| OQ-07 | *Closed by DEC-8 and DEC-9:* only products pre-processed by cutting and portioning, peeled onions as baseline, no industrial or semi-finished ingredients. | MEAL-009, MEAL-012, section 5.6. | Onion peeler as upgrade (UO-12). |
| OQ-08 | Is wiping the exterior fronts by the human acceptable? | Yes (AS-08). | — |
| OQ-09 | Is it acceptable that the human empties waste containers about twice a week and refills consumables about monthly (section 7.8)? | Yes. | — |
| OQ-10 | Cost target for the parts. | ≤ EUR 25 000 for the MVC (BLD-004). | — |
| OQ-11 | Available wall length and corner geometry in the target kitchen. | Straight ≤ 3 600 mm for the MVC (target ≤ 3 300 mm; ≤ 4 200 mm with larger storage), or L with legs ≥ 1 200 mm (PHY-004, PHY-005). | — |
| OQ-12 | Which cuisine defines "traditional meals"? | Central European home cooking plus established international everyday dishes (MEAL-001). | — |
| OQ-13 | *Closed by DEC-6:* the machine uses its own dish set. | SRV-016, AS-11. | — |
| OQ-14 | *Closed by DEC-12:* leftovers are discarded; stored if that is easy. | SRV-021. | — |
| OQ-15 | Is the machine ever to be sold or installed for third parties (certification, liability)? | No: private prototype, designed to the standards (section 11.8). | Yes, by design to standards. |
| OQ-16 | *Closed by DEC-16:* bread, muesli, cereals and snacks are kept outside the machine and not served. Warm breakfast dishes of the corpus (eggs, pancakes, porridge) are ordinary meals; baking bread remains a meal function (corpus BK rows). | CAP-020, UC-19, NG-13. | — |
| OQ-17 | Items larger than a box (leek, whole cabbage, melon, a 3 kg roast): cut by the human before ingestion, or out of scope? | Accepted up to Ø 220 mm × 350 mm (INB-004) and cut by the machine on the way into boxes (S); larger items rejected. | — |
| OQ-18 | Are the noise limits and quiet hours of section 6.5 acceptable (open-plan living)? | As NOI-001 to -005. | — |
| OQ-19 | Is remote ordering from outside the home and any cloud service wanted? | Local operation; remote access optional and opt-in (UI-001 c, SEC-004). | Yes. |
| OQ-20 | *Closed by DEC-13, DEC-16 and DEC-17:* the machine stores all cooking ingredients (chilled, frozen, ambient); a separate ordinary fridge may hold breakfast dairy, cold cuts and table drinks; ambient breakfast goods and snacks stay outside. The larger-storage configuration (CAP-026) can make the machine the only fridge. | CAP-020 to -026, SRV-022, UC-19. | Yes: CAP-026. |
| OQ-21 | Raw and rare dishes (tartare, soft eggs, rare minced meat): offer at all? | Only after explicit opt-in (FSF-024). | — |
| OQ-22 | *Closed by DEC-14:* tacos and wraps may be served as components. | MEAL-020. | — |

### 12.4 Decisions incorporated (DECISIONS.md)

| Decision | Content | Reflected in |
|----------|---------|--------------|
| DEC-1 (customer) | Three-phase cooker connection 400 V 3N~, 3 × 16 A, ≈ 11 kW is available; power management still required. | UTL-010, UTL-011, UTL-012, COK-004, PERF-001, AS-03, OQ-01 closed |
| DEC-2 (customer) | Meal preparation is the most novel part and is developed in several rounds of idea finding, exploration, critique and iteration. | Section 3.5 and 5.3 are deliberately solution-neutral (capabilities and limits, no mechanisms); PRP-003 asks for a justification of every tool type. |
| DEC-3 (ruling, pending customer objection) | Two ingestion lanes: DECANT and STOW with just-in-time opening. | ING-018, ING-020, ING-021, INA-005, INA-006, UC-02, FSF-050, OQ-05 |
| DEC-4 (ruling, confirmed by customer) | No FDM-printed parts on food-contact surfaces; splash zone only if sealed, replaceable and below about 60 °C. | HYG-015, BLD-002, BLD-003, SAF-014 |
| DEC-5 (ruling) | The hob is built from a controllable OEM/commercial induction module, not from a consumer hob. | COK-020, COK-023 |
| DEC-6 (customer) | Used dishes are returned at the hatch; the machine washes, dries, stores and dispenses its own dishes. | UC-07, WSH-001 to -003, SRV-014 to -016, SRV-027, CAP-031, HUM-002, HYG-035, AS-11, OQ-03, OQ-13 |
| DEC-7 (customer) | Ingestion A: one by one minimum, jumbled pile as target. | INA-001, OQ-06 |
| DEC-8 (customer) | Only cut and portioned products may be bought; no industrial or semi-finished ingredients; the machine washes, peels and cuts fruit and vegetables. | MEAL-009, MEAL-012, section 5.6, UO-06, UO-13, UO-24, UO-44, UO-45, UO-96, UO-97, 5.4, 5.5, OQ-07 |
| DEC-9 (customer) | Peeled onions are the baseline purchase; dicing onions is always done by the machine; onion peeler as upgrade. | UO-12, R-08, MEAL-009 |
| DEC-10 (customer) | 1–6 persons per meal — superseded by DEC-19. | — |
| DEC-11 (customer) | Height 2 000–2 200 mm; depth 600 mm. | PHY-002, PHY-012 |
| DEC-12 (customer) | Leftovers discarded; stored if easy. | SRV-021, OQ-14 |
| DEC-13 (customer) | The machine is the only fridge and pantry; it serves simple drinks and snacks. | CAP-012, CAP-021, CAP-022, CAP-025, CAP-026, SRV-022, SRV-024 to -026, UC-19, UI-009, PHY-004, REL-004 table, NG-01, OQ-20 |
| DEC-20 (customer) | Simplicity is a high-weight decision criterion. | GEN-009, PRP-003, PRP-039 |
| DEC-21 (customer) | Job-shop laser-cut, bent, welded, polished stainless parts allowed where necessary; off-the-shelf preferred. | BLD-001, BLD-002 |
| DEC-22 (customer) | Cost optimisation later; cost reported, not a gate. | BLD-004 |
| DEC-23 (customer) | Water optimisation later; reported, not a gate; hygiene first. | RES-005, RES-006 |
| DEC-24 (customer) | A bought oven may be modified; fewer modifications better. | COK-020, COK-023, SAF-056 |
| DEC-25 (customer) | Generic peeling and stoning/deseeding/coring of most produce is a core function; generic solutions preferred. | PRP-039, UO-13, UO-24, MEAL-009 |
| DEC-26 (customer) | Coverage target 93 %; bought filled pasta and pastry/wrapper sheets still not allowed. | MEAL-002, section 5.4 (17 meals may fall out, reserve 6), MEAL-018 |
| DEC-19 (customer) | Maximum 4 persons per meal; batches, vessels, cooking positions, dish stock and time limits for 1–4. | 1.4 sizing meal, 6.1, CAP-001, -002, -004, -006, -013, -030, -031, -041, ING-022, PRP-023, -031, -038, COK-002, -004, -006, -016, TRN-004, SAF-023, SRV-001, -009, -014, WSH-002, -005, CTL-002, UI-003, MEAL-007, -016, PERF-001, RES-001, -005, X-05, NG-06, AS-12, OQ-04, PHY-004, Annex A |
| DEC-18 (customer) | Regular household 2 persons; up to 6 occasionally with guests; storage, autonomy, daily and lifetime figures sized for 2; guest meals supplied by a shop shortly before. | Reference household and reference meal (1.4), CAP-002, CAP-010, CAP-012, CAP-013, CAP-020 to -025, CAP-041, ING-022, PERF-001, RES-001 to -008, REL-004 table, PHY-004, AS-12, OQ-11 |
| DEC-17 (customer + ruling) | A separate ordinary fridge is allowed; the machine's cold storage is sized for cooking ingredients; MVC ≤ 3.6 m, larger storage ≤ 4.2 m as option; drink pouring kept for drinks the machine stores. | Section 6.2 derivation, CAP-002, CAP-012, CAP-020 to -026, PHY-004, SRV-022, SRV-024, REL-003, REL-004 table, NG-13, OQ-11, OQ-20 |
| DEC-16 (customer) | Clarifies DEC-13: breakfast goods and snacks are stored outside and not served; chilled items stay in the machine. | CAP-012, CAP-020, CAP-024, CAP-025, PHY-004, UC-19 (drinks only), SRV-023 deleted, NG-13, OQ-11, OQ-16, OQ-20 |
| DEC-14 (customer) | Tacos and wraps may be served as components. | MEAL-020, OQ-22 |
| DEC-15 (customer) | Commits are pushed to GitHub by a hook. | (process only) |

---

## 13. Traceability: brief → requirements

| Brief statement | Covered by |
|-----------------|-----------|
| B1 Fully automatic; cooks most normal meals autonomously | GEN-001 to -003, -007; MEAL-001 to -021; REL-001; section 7.8 |
| B2 Parts list | MOD-001; sections 3.1–3.13 |
| B3 Rectangular plastic boxes, small to medium, in a grid; a specific box to the exit; "design this transport system" | BOX-001 to -014; STO-001 to -015; TRN-001 to -016; CAP-020, -023 |
| B4 Cold storage works the same; exit thermally closed; ideally off-the-shelf fridge/freezer with modified door | CLD-001 to -014; CAP-021, -022; RES-004; SAF-056 |
| B5 Multi-tool or tools; all steps for most meals; ≥ 95 % (DEC-26: 93 %); named meals; pouring from box to bucket, bucket to bucket, bucket to pan; novel tools welcome | PRP-001 to -037; MEAL-002, -005; MEAL-018; section 5.3 (UO-01 to UO-95); section 5.4 |
| B6 Everything cleaned automatically; hygienic; human cleans nothing; including boxes and transport | GEN-002; section 7 (HYG, FSF, HUM); WSH-004 to -013; PRP-030; TRN-011, -012; STO-012; COK-019; SRV-019; ING-013; INA-013 |
| B7 Cooking (e.g. induction) and baking, designer free | COK-001 to -023 |
| B8 Portion on a dish, nicely presented; several persons at once; specific place with automatic door | SRV-001 to -013; CAP-001 to -007; SAF-032 |
| B9 Dishes (superseded by DEC-6: used dishes returned at the hatch, machine washes) | WSH-001 to -003; SRV-014 to -017, -027; HUM-002; CAP-031 |
| B10 Ingestion: container, one package at a time, bar code, Internet look-up, cut open, funnel into box; alternative: user scans and pours; two versions | ING-001 to -021; INA-001 to -015; INB-001 to -010; SEC-001; SAF-030, -031 |
| B11 Modular; transport binds the parts; each part designed independently | MOD-001 to -033; TRN-002, -003, -014; CTL-013, -014 |
| B12 600 mm deep, 2 000 mm high; L form optional; cold water 2.2–5 bar, waste water, 220 V, Internet | PHY-001 to -015; UTL-001 to -014; ENV-001 to -014; SAF-060, -061 |
| B13 Standard parts and 3D printer; self-cleaning; accessible for repair; robust; no wasted footprint | BLD-001 to -009; MNT-001 to -010; REL-001 to -009; PHY-007, -008; STO-005 |

---

## 14. Open issues

1. **Meal corpus: resolved.** Section 5, PERF-001/-002, COK-002/-003/-004/-006/-016, CAP-004/-030, PRP-023/
   -024/-037/-038 and Annex A are aligned with `research/02-meal-corpus.md`. Remaining: the corpus' difficulty,
   avoidability and weight values are its author's estimates, and the list of meals falling out (5.4) was
   compiled by keyword, not by a full recomputation; V2 shall recompute coverage with the corpus' appendix A
   method. One deliberate deviation from the corpus: it proposes a deep fryer, this specification does not
   (X-01). The corpus has no plain "roast beef" row; MEAL-005 uses DM08 and equivalents.
2. **Estimated numbers.** Everything marked (est.) is to be confirmed by research and by the architecture's
   budgets, in particular: storage box counts (CAP-020 to -022), energy and water (RES), cost (BLD-004),
   life-cycle counts (REL-004), mass per width (PHY-011), noise limits (NOI).
3. **Microbiological and allergen criteria** (HYG-021, HYG-022) are taken from general hygiene practice;
   `research/06` could not verify the dish-washer standards (DIN 10510/10534, NSF/ANSI 184). To be validated
   with a laboratory on the prototype.
4. **Cooling of cooked food** (COK-022: 65 → 10 °C in 120 min) is stricter than the FDA two-stage rule quoted
   in `research/06`; kept as S until the leftover question (OQ-14) is decided.
5. **Regulatory classification** (household appliance under the LVD vs. machinery) is unresolved (REG-001,
   OQ-15).
6. **Cleaning inside cold storage** (HYG-038) and **in-place cleaning of the transport system** (HYG-036) are
   required but no proven method exists in prior art; the architecture must assign an owner.
7. **Automatic verification of cleanliness** (HYG-026) by sensors and camera has no proven prior art;
   thresholds must be found by prototyping.
8. **Measuring core temperature** automatically and cleanably (COK-013) is unresolved in the research.
9. **Off-the-shelf appliances without manual remote-start** (COK-023): the choice of oven and dish washer
   depends on finding models that can be controlled locally.
10. **Dish-washer duty** (REL-004 note): 4 ware-wash cycles per day exceed household appliance design life.
11. The **reference basket** for INA-006 and the **test soils** for HYG-027 need to be fixed as test
    specifications.
12. The acceptance panel methods (MEAL-015, SRV-006, CAP-042, ENV-011) need a test protocol.

## 15. Risks

| # | Risk | Effect | Mitigation in this specification |
|---|------|--------|----------------------------------|
| 1 | The scope exceeds any existing product: no prior system combines storage, raw preparation, cooking, plating, self-cleaning and ingestion. | Unbuildable or unaffordable machine. | Priorities M/S/C; explicit exclusions (5.4); MVC (MOD-030); cost budget per module (BLD-004). |
| 2 | "No human cleaning" fails at the casing, transport and storage interiors. | Hygiene hazard or hidden manual work. | Zones, surface inventory, schedule and acceptance criteria (section 7); exhaustive human task list (7.8); hygiene audit V3. |
| 3 | 93 % coverage is claimed but not achieved in quality. | Meals processed but not good. | MEAL-010 to -021 define "preparable", the classes of adaptation and their budgets. |
| 4 | Raw-ingredient preparation (peeling, meat handling, forming, Rouladen) has no prior art. | Largest development effort; coverage gap. | Solution-neutral unit operations with measurable limits; permitted ingredient forms (MEAL-012, OQ-07); multi-round preparation design (DEC-2). |
| 5 | Version A ingestion of arbitrary packages from a pile. | Low automatic rate, many rejects. | Staged requirement (INA-001, INA-006), reject path, version B as fallback (ING-001). |
| 6 | Opening everything at ingestion destroys shelf life. | Food waste, autonomy lost. | Two lanes (ING-018), FSF-050 to -052. |
| 7 | Power and heat: cooking, washing and drying compete even on 11 kW; all heat and steam stay in the room. | Slow meals; damp, hot kitchen; mould in dry storage. | UTL-011; ENV-010 to -013; STO-007; HYG-053. |
| 8 | Unattended heating of fat. | Fire with nobody at home. | COK-021, SAF-010 to -017, exclusion X-01. |
| 9 | Reliability of a machine with many mechanisms: 98 % meal completion needs very high reliability per step (≈ 300 steps per meal → ≥ 99.993 % per step). | Frequent interventions. | REL-001 to -009; closed-loop control (CTL-007); automatic recovery (CTL-010); few tool types (PRP-003). |
| 10 | Modified consumer appliances (fridge, dish washer, oven) lose certification, have short duty life, or cannot be controlled locally. | Safety, lifetime, integration risk. | SAF-056, COK-023, REL-004 note. |
| 11 | Standard parts and 3D printing conflict with hygienic design in Zones F and S. | Custom stainless parts raise cost. | HYG-015, BLD-002 (online fabrication services allowed), BLD-004. |
| 12 | Requirements based on estimates prove too tight or too loose. | Over- or under-design. | (est.) marking; open issue 2; architect to confirm budgets and raise conflicts. |
| 13 | Used dishes returned at the hatch are an uncontrolled input (foreign objects, breakage, leftovers) and meet clean food at the same place. | Contamination, jams, foreign bodies. | SRV-014, SRV-015, SRV-027, WSH-001, HYG-035. |
| 14 | Water damage or scalding in an unattended home. | Property damage, injury. | SAF-020 to -023, SAF-053 to -055. |

---

## Annex A — Reference menus (from the corpus, section 4.9)

The meal list itself is the corpus (`research/02-meal-corpus.md`, section 3). These 15 menus are the
reference for scheduling, heat-source, vessel and time walk-throughs (MEAL-007); H = peak concurrent heat
sources, B = peak concurrent food vessels.

| # | Menu | H | B | Note for this specification |
|---|------|---|---|-----------------------------|
| 1 | Spaghetti bolognese | 2 | 3 | PERF-002 a |
| 2 | Schnitzel + French fries + mixed salad | 2 | 5 | fries by adapted method (X-01); breading by the machine |
| 3 | Steak + baked potato + salad | 2 | 3 | PERF-002 c |
| 4 | Frikadellen + potato salad + cucumber salad | 2 | 4 | pan in batches, warm-hold |
| 5 | Pizza + salad | 1 | 3 | one pizza at a time; 250 °C (280 °C: S) |
| 6 | Käsespätzle + salad | 3 | 4 | EXT is S: Spätzle by press or cut |
| 7 | Fish fingers + mash + creamed spinach | 3 | 4 | breading by the machine |
| 8 | Rouladen + red cabbage + potato dumplings | 3 | 5 | PERF-002 e |
| 9 | Roast pork + dumplings + red cabbage + gravy | 4 | 6 | PERF-002 f; sizes COK-002 and CAP-030 |
| 10 | Goose + red cabbage + dumplings + gravy | 4 | 6 | goose excluded (X-04); run with duck ≤ 2.5 kg |
| 11 | White asparagus + hollandaise + potatoes + schnitzel | 4 | 6 | asparagus peeling by the machine (PRP-039, DEC-25) |
| 12 | Butter chicken + rice + naan + raita | 4 | 5 | naan in the pan, in batches |
| 13 | Burger + fries + coleslaw | 3 | 4 | assembly ASM; fries adapted |
| 14 | Lasagne + salad | 3 | 4 | PERF-002 g |
| 15 | Breakfast for 4: scrambled eggs, pancakes, bacon, porridge | 4 | 5 | pancakes are the bottleneck (8 in sequence); run with 3 positions plus warm-holding (COK-002) |
