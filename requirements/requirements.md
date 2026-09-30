# AutoKitchen — Requirements Specification

Document: `requirements/requirements.md` (task Q1) · Status: baseline for architecture (A1) and module design (D1–D10)
Source of truth: [BRIEF.md](../BRIEF.md). Where this document and the brief disagree, the brief wins and the
conflict is to be raised as an open issue.

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
* **Trace** — B1…B13 refer to the brief sections in the table below; "drv" = derived requirement, needed to
  make a brief requirement achievable, safe or legal.
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

ID prefixes: GEN general · UC use case · STO ambient storage · CLD cold storage · TRN transport · PRP preparation ·
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

Out of scope: see non-goals (section 11.2).

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
| **Serving hatch** | The place with an automatic door where dishes are presented to the human and where the human puts clean dishes back (B8, B9). |
| **Ingestion** | Taking purchased food into the storage system (B10). **Version A**: the machine takes packages from a container, identifies and opens them. **Version B**: the human scans the bar code and pours the contents into a funnel. |
| **Meal** | What is served to the persons at one sitting: one or more courses, each of one or more components. |
| **Component** | A separately prepared part of a course (e.g. roast, potatoes, vegetable, sauce, salad). |
| **Portion** | The amount of a component served to one person. Reference portion sizes are in CAP-004. |
| **Unit operation** | An elementary preparation step (e.g. dice, simmer, turn), listed in section 5.3. |
| **Meal corpus** | The reference list of traditional meals in `research/02-meal-corpus.md`, used to measure the 95 % goal. |
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
| **Reference household** | 4 persons, 3 meals per day from the machine (1 cold/light, 1 light warm, 1 full warm meal). Basis for all per-day figures. |
| **Reference meal** | Full warm meal for 4 persons: 1 course, 4 components (protein, starch, vegetable, sauce), 2.2 kg plated food in total. |
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
  topping up, (7) opens the package and transfers the contents into the box through the funnel, without
  packaging fragments, (8) weighs the box, closes it, records it in the inventory, (9) sends the box to the
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
  courses), the number of persons (1–6), optionally the portion size per person and per-meal options (e.g.
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

### UC-07 Dishes: washing and return

* **Actor:** user (per brief B9).
* **Flow:** (1) After eating, the user puts the used dishes into the dish washer. (2) The dish washer runs
  (automatically when full or at a set time, or on command). (3) The user takes the clean, dry dishes out and
  puts them at the serving hatch ("the same spot as before"). (4) The machine takes each dish in, checks type
  and cleanliness, and stores it in the dish store.
* **Exceptions:** dish soiled, damaged or of unknown type → handed back at the hatch with a message.
  Dish stock too low for the next planned meal → reminder.
* **Note:** OQ-03 asks whether the machine should take used dishes directly at the hatch instead.

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
| BOX-007 | Every box shall have a closure that the machine opens and closes, that stays closed during transport, and that prevents spill of liquid contents in any transport motion and prevents entry of dust, insects and drips. | Liquids (milk), odour, cross-contamination. | M | T | B3, B6 |
| BOX-008 | Boxes used for food class R and for liquids shall be leak-tight: no leakage when filled with water to rated fill and tilted 30° for 60 s. | Raw-meat drip must not escape. | M | T | drv |
| BOX-009 | Box and closure shall withstand −25 °C to +85 °C, washing per HYG-021, and a drop of the filled box from 100 mm, without damage or deformation that impairs handling. | Freezer, thermal disinfection, mishandling. | M | T | B6 |
| BOX-010 | Box interior shall be fully cleanable and drainable: internal radii ≥ 6 mm (est.), no undercuts, crevices, hollow rims or threads in Zone F, and self-draining in the wash and dry orientation. | Hygienic design. | M | I, T | B6 |
| BOX-011 | Boxes shall be off-the-shelf food containers where a product meeting BOX-001 to BOX-010 exists; otherwise the deviation shall be justified. | Standard parts. | S | R | B13 |
| BOX-012 | The fill level or content mass of a box shall be determinable without opening it (e.g. by weighing), to ±5 g or ±2 %, whichever is larger. | Inventory, shopping list. | M | T | drv |
| BOX-013 | The machine shall be able to empty a box completely (residue ≤ 2 % of content mass for dry free-flowing goods, ≤ 5 % for sticky or wet goods) and to remove a partial, dosed quantity (PRP-010 ff.). | Use of contents. | M | T | B5 |

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
| TRN-004 | Payload: ≥ 5 kg for boxes and ≥ 8 kg for vessels including contents (est.), each with a safety factor ≥ 1.5 on holding force. | Heaviest box (BOX-004); 5 L pot with contents. | M | A, T | drv |
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
| PRP-023 | Throughput: wash, peel and cut 1.5 kg of potatoes in ≤ 10 min; cut 1 kg of mixed vegetables in ≤ 6 min; knead 1 kg of dough; mix 1.2 kg of minced-meat mass. | Time targets for 6 persons. | M | T | drv |
| PRP-024 | The module shall form the meat, dough and filled items required by the M unit operations (section 5.3, UO-40 ff.) with piece-mass variation ≤ ±10 %. | Frikadellen, Rouladen, Klöße named in or implied by the brief. | M | T | B5 |
| PRP-030 | Every tool and vessel shall be completely cleanable by the machine (HYG-030 ff.) and shall be sent to washing after use without human action. | Brief: "especially for these tools". | M | D, T | B6 |
| PRP-031 | The module shall hold enough clean tools and vessels to prepare the reference meal for 6 persons without waiting for a wash cycle (CAP-030). | Time target. | M | A | drv |
| PRP-032 | Food class R shall be prepared physically or temporally separated from RTE food as FSF-040 requires. | Cross-contamination. | M | R | B6 |
| PRP-033 | Trimmings, peel, shells and other preparation waste shall be removed to the organic waste without human action and without passing over open food. | No human cleaning. | M | D | B6 |
| PRP-034 | Cutting edges shall keep the performance of PRP-021 for ≥ 1 year of reference use without sharpening or exchange by a human, or be resharpened by the machine. | Human does not maintain weekly. | M | A, T | B13 |
| PRP-035 | The module shall detect tool breakage or loss of a tool part (e.g. blade fragment) and shall then discard the affected food. | Foreign bodies. | M | A, D | drv |
| PRP-036 | The module shall be able to hold prepared ingredients and intermediate products at ≤ 7 °C (marinating, dough resting, prepared salad, set desserts) for up to 24 h, e.g. by returning them in a closed vessel or box to cold storage. | Multi-stage recipes; FSF limits. | M | D | drv |
| PRP-037 | The module shall be able to hold dough at 25–35 °C for proofing. | Yeast dough. | S | D | B5 |

### 3.6 Cooking and baking (COK)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| COK-001 | The cooking module shall perform all thermal unit operations marked M in section 5.3, and should perform those marked S. | 95 % goal. | M | D | B7 |
| COK-002 | Number of simultaneously heated cooking positions: ≥ 3 (M), 4 (S), plus 1 baking/roasting cavity usable at the same time. | Reference meal: protein, starch, vegetable, sauce; roast in the oven with 2–3 positions for sides. | M | I | B7, B8 |
| COK-003 | Cooking positions: controlled vessel-base temperature 40–250 °C; content temperature control 40–100 °C within ±3 K (simmering, poaching, holding, melting). | Searing to gentle simmer. | M | T | B7 |
| COK-004 | Heating performance (single-phase baseline, UTL-010): bring 2 L of water from 15 °C to 95 °C in ≤ 8 min in one vessel while all other heaters are off. | Pasta/potato water is the time driver. | M | T | drv |
| COK-005 | Searing: a vessel base shall reach 220 °C in ≤ 5 min and recover to ≥ 180 °C within 60 s after 600 g of meat at 4 °C is added. | Browning instead of stewing (steak, Rouladen, roast). | M | T | B5, B7 |
| COK-006 | Baking/roasting cavity: 30–250 °C, ±10 K at the centre; top heat for gratinating/browning; usable space for at least a 2.5 kg roast, or a baking dish for 6 portions (≥ 3.5 L, e.g. 350 × 250 × 60 mm), or a tray of ≥ 0.10 m². | Roast beef, gratin, lasagne, cake, pizza. | M | T, I | B7 |
| COK-007 | The cavity should offer controlled humidity (steam injection or steam baking up to 100 °C). | Bread crust, gentle roasting, regeneration, steaming in bulk. | S | D | B7 |
| COK-008 | Every cooking position shall be able to stir or agitate the contents automatically, including scraping the bottom and wall so that thickened sauces, porridge, risotto and roux do not burn on; stirring speed and pattern selectable per recipe step. | Brief: "cooking, including stirring". | M | D, T | B2 |
| COK-009 | The module shall turn and flip individual pieces (steak, schnitzel, Frikadelle, fish fillet, pancake, fried egg) without breaking them: ≥ 95 % of pieces intact. | Pan-fried dishes are a large share of the corpus. | M | T | B5 |
| COK-010 | The module shall put on and take off lids, and add ingredients to a hot vessel at any time during cooking (deglazing, seasoning, staged addition). | Braising, sauces. | M | D | B5 |
| COK-011 | The module shall drain cooking water from solids (pasta, potatoes, vegetables) with ≤ 3 % of the water remaining, and shall be able to retain a measured part of the liquid. | Boiled sides. | M | T | B5 |
| COK-012 | The module shall separate fat, liquid and solids as the M unit operations require (pour off frying fat, strain a sauce). | Sauces, gravy. | S | D | B5 |
| COK-013 | The module shall measure the core temperature of pieces ≥ 20 mm thick to ±1 K and use it to end the cooking step. | Food safety (FSF-020); doneness of steak and roast. | M | T | drv |
| COK-014 | The module shall measure the mass of each vessel's contents during cooking to ±10 g. | Reduction, evaporation compensation, dosing check. | S | T | drv |
| COK-015 | The module shall detect boil-over, dry-boiling and burning (e.g. by temperature, mass, humidity, vision) and react before food is spoiled or a hazard arises. | Unattended cooking. | M | T | drv |
| COK-016 | Cooking vessels: working volumes covering 0.3 L (sauce for 1) to ≥ 5 L (soup, pasta water for 6); at least one frying surface with ≥ 600 cm² base (6 schnitzels in 2 batches, 6 Frikadellen in 1). | 1–6 persons. | M | A | B8 |
| COK-017 | The module shall keep finished components at ≥ 65 °C without further cooking them noticeably, for up to 30 min, and cold components at ≤ 7 °C. | All components ready together; late pick-up. | M | T | B8 |
| COK-018 | Steam, fumes and grease aerosol from cooking shall be captured inside the machine (ENV-010 ff.). | Home environment; casing cleaning. | M | T | B6, drv |
| COK-019 | All surfaces of the cooking positions and the cavity, including burnt-on residue, shall be cleaned by the machine (HYG-033). | Brief. | M | T | B6 |
| COK-020 | Off-the-shelf cooking and baking appliances or their heating modules should be used where they meet the requirements. | Standard parts. | S | R | B7, B13 |
| COK-021 | The quantity of free fat or oil in any vessel shall be limited to 250 mL (est.). | Fire load for unattended cooking; excludes deep frying (section 5.4). | M | R | drv |
| COK-022 | The module shall cool a cooked component from 65 °C to ≤ 10 °C within 120 min when the recipe needs it cold (potato salad, pudding, cooked components of salads). | Food safety; cold dishes. | S | T | drv |

### 3.7 Portioning and serving (SRV)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| SRV-001 | The module shall place cooked food on dishes for 1 to 6 persons per meal. | Brief. | M | D | B8 |
| SRV-002 | It shall portion each of these forms: (a) single pieces (steak, schnitzel, dumpling, roulade), (b) loose solids (potatoes, vegetables, rice, pasta, salad), (c) long pasta, (d) mash and purées, (e) soups and stews, (f) sauces and gravy, (g) slices carved from a cooked roast, (h) slices/pieces of baked goods (gratin, lasagne, cake), (i) garnish (chopped herbs, a lemon wedge). | Coverage of corpus meals. | M | D | B8 |
| SRV-003 | Portion equality: each person's portion of each component within ±10 % of its target mass (pieces: equal count, and the machine shall distribute unequal pieces so that totals are within ±15 %). | "Portion the food on the dishes for each person." | M | T | B8 |
| SRV-004 | Per-person portion sizes (at least S/M/L = 0.7/1.0/1.3 of the reference portion) shall be selectable. | Children and adults at one table. | S | D | B8 |
| SRV-005 | Presentation ("nicely presented") shall meet all of: (a) each component in its zone of the recipe's plating layout, position within ±15 mm; (b) components that the layout keeps apart do not touch or run into each other; (c) the outer 20 mm of the plate rim free of food, drips and smears > 3 mm; (d) sauce placed as specified (over, beside or under); (e) no component visibly broken up, burnt or dried out; (f) garnish placed where specified. | Makes the brief's requirement testable. | M | T (photo check against layout) | B8 |
| SRV-006 | In a blind rating by ≥ 5 persons of 10 different plated corpus meals, the mean score for appearance shall be ≥ 3.5 on a 5-point scale where 3 = "as a careful home cook would serve it". | Subjective acceptance. | S | T | B8 |
| SRV-007 | Hot food shall be ≥ 65 °C at the core when the dish arrives at the hatch; cold food ≤ 10 °C; hot and cold components that the recipe serves together shall be plated last-minute. | Eating quality, food safety. | M | T | B8, drv |
| SRV-008 | Dishes for hot food shall be pre-warmed to 40–60 °C. | Food stays warm; grip area not scalding (SAF-021). | S | T | B8 |
| SRV-009 | All dishes of one course for up to 6 persons shall be at the hatch within 4 min from the first to the last. | Family eats together. | M | T | B8 |
| SRV-010 | The serving hatch shall be at a fixed place, with an automatically operated door, and shall present the dishes so that an adult standing in front can take them with one hand each; presentation height 850–1 300 mm above the floor. | Brief; ergonomics. | M | I | B8 |
| SRV-011 | The hatch shall present ≥ 2 dishes at a time (M), 4 (S). | Carrying two plates at once; serving time. | M | I | B8 |
| SRV-012 | The hatch door shall be closed except while dishes are being presented or returned, and shall separate the room from the machine interior (heat, steam, noise, odour, access). | Safety, hygiene. | M | I | B8 |
| SRV-013 | The system shall announce "ready" at the machine (light and sound, mutable) and on the app, and shall detect removal of each dish. | UX. | M | D | B8 |
| SRV-014 | The module shall accept clean dishes placed by the human at the hatch, identify the dish type, inspect them (SRV-015) and store them in a closed dish store. | Brief. | M | D | B9 |
| SRV-015 | A returned dish that is visibly soiled, wet, chipped/cracked or not part of the dish set shall be detected with ≥ 95 % probability and handed back. | Human-washed dishes are an uncontrolled input into Zone F. | M | T | B9, drv |
| SRV-016 | The dish set shall consist of commercially available dishes: at least a flat plate (Ø 260–280 mm), a deep plate or bowl (≥ 0.5 L) and a small plate or bowl (dessert, salad, side). | Courses of traditional meals; standard parts. | M | I | B8, B13 |
| SRV-017 | The dish store capacity shall be as CAP-031. | — | M | A | drv |
| SRV-018 | Food in shared serving vessels ("family style": one bowl of potatoes, one of vegetables, to be passed at the table) shall be offered as an alternative to individual plating. | Common at family tables; large meals. | C | D | B8 |
| SRV-019 | All portioning tools and surfaces are Zone F and shall be cleaned as HYG-030 ff.; the hatch space is Zone S and shall be cleaned daily and after any spill. | Brief. | M | R, T | B6 |
| SRV-020 | Food not collected shall be handled as FSF-032. | Food safety. | M | D | drv |
| SRV-021 | Leftovers remaining in vessels after plating shall, by user setting, be (a) discarded, (b) offered as second helpings at the hatch for 30 min, or (c) cooled (COK-022) and stored in a box for a later meal within the FSF limits. | Waste vs. simplicity; default (b) then (a). | S | D | drv |

### 3.8 Washing and cleaning module (WSH)

Acceptance criteria and frequencies are in section 7; this table states the functions of the module.

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| WSH-001 | The system shall include a dish washer into which the human places used dishes and from which the human takes clean dishes. | Brief. | M | I | B2, B9 |
| WSH-002 | The human-loaded dish washer shall hold at least the used dishes of a 2-course meal for 6 persons including cutlery and glasses: ≥ 9 standard place settings (EN 60436) (est.). | One load per meal at most. | M | I | B9 |
| WSH-003 | The human-loaded dish washer shall be loadable at a height and position reachable without kneeling for the upper rack, with door or drawer not blocking the serving hatch. | Ergonomics. | S | I | B9 |
| WSH-004 | The system shall wash, disinfect (where HYG requires) and dry all internal ware — boxes, closures, vessels, lids, tools, funnels, removable Zone F parts — without human action, fed and emptied by the transport system. | Brief. | M | D, T | B6 |
| WSH-005 | Internal-ware washing capacity and cycle time shall be such that (a) the reference meal for 6 is never delayed by lack of clean ware, (b) all ware of a meal is clean and dry within 90 min after serving (M), 45 min (S), (c) empty boxes from ingestion and use are washed within 12 h. | Turn-round. | M | A, T | drv |
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
| ING-018 | The system should be able to store a sealed long-life package (tin, jar, UHT carton, vacuum pack) unopened and open it only when first needed. | Avoids turning a 2-year shelf life into 3 days (see OQ-05). | S | R | B10, drv |
| ING-019 | Ingestion shall be possible while no meal is in progress (M) and during cooking without delaying the meal by more than 2 min (S). | Shared transport and washing resources. | M | D | drv |

### 3.10 Ingestion version A — automatic (INA)

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| INA-001 | The user shall place packages as bought into a container, unsorted, in any orientation; the machine shall pick one package at a time. | Brief. | M | D | B10 |
| INA-002 | Container capacity: ≥ 40 L and ≥ 20 packages and ≥ 15 kg per load (est.). | About half of a weekly shop per load; chilled goods are not left waiting long. | M | I | B10 |
| INA-003 | Package envelope: from 40 × 30 × 10 mm to 350 × 250 × 150 mm; mass 20 g to 3 kg (est.). | Spice sachet to 2.5 kg potato bag, 1.5 L bottle, 500 g spaghetti. | M | T | B10 |
| INA-004 | The machine shall find and read the bar code on any face of the package, including curved, glossy, crumpled and frosted surfaces, with a first-pass read rate ≥ 95 % on the reference basket (INA-006). | Brief. | M | T | B10 |
| INA-005 | The machine shall open these package types and transfer their contents (M): folding carton; paper bag; plastic film bag and pouch (incl. frozen); tray with film lid; tub/cup with peel-off lid; beverage carton; net bag; vacuum pack; egg carton. (S): tin can; glass jar with twist-off lid; plastic bottle with screw cap; tube; foil-wrapped block (butter); carton with inner bag. | Brief: "cuts open the package". Coverage by frequency; S types have long shelf life and are candidates for ING-018. | M | T | B10 |
| INA-006 | On a reference basket of 100 packages representative of a weekly household shop (to be defined from `research/07-ingestion-packaging.md`), ≥ 90 % of packages shall be ingested fully automatically (M), ≥ 97 % (S); the remainder shall be rejected *unopened and undamaged*. | Measurable success rate; graceful fallback to version B. | M | T | B10 |
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
| CTL-002 | It shall hold a recipe library covering the meal corpus (section 5) in a machine-executable recipe format built from the unit operations of section 5.3, with quantities per person and scaling rules for 1–6 persons. | 95 % goal. | M | R, D | B1, B5 |
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
| UI-003 | An order shall specify: meal (1–3 courses), number of persons 1–6, serving time (now or date/time up to 7 days ahead), and optionally per-person portion size and recipe options. | UC-04. | M | D | B8 |
| UI-004 | Ordering a repeat of a previous or favourite meal for the default number of persons shall take ≤ 3 user inputs. | Daily use. | S | D | drv |
| UI-005 | The UI shall support weekly meal plans and recurring orders (e.g. breakfast every weekday at 07:00). | Scheduling. | S | D | drv |
| UI-006 | A household profile shall hold persons, default portion sizes, allergens and intolerances, excluded ingredients and diets; orders conflicting with the profile shall require explicit confirmation. | Allergen safety. | M | D | drv |
| UI-007 | The UI shall show the state of the machine: current activity, time to ready, inventory with use-by dates, consumable levels, waste fill level, due human tasks, faults with location and instructions. | Transparency. | M | D | drv |
| UI-008 | Notifications shall be issued for: meal ready; dish pick-up overdue; human task due (section 7.8); ingestion rejects; food discarded; faults; alarms (SAF). Alarms shall also sound at the machine. | UC-06 ff. | M | D | drv |
| UI-009 | The panel on the machine shall allow, without smartphone or network: order from favourites, stop/cancel, open hatch for dish return, start ingestion, confirm human tasks, present a box (UC-18), service mode, acknowledge alarms. | Works when the phone or network does not. | M | D | drv |
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

## 5. Meal coverage: "at least 95 % of all traditional meals"

### 5.1 Measure

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| MEAL-001 | The reference for "traditional meals" is the meal corpus in `research/02-meal-corpus.md`: Central European home cooking (the brief's examples are German) plus the internationally established everyday dishes cooked in such households, across breakfast dishes, soups, salads, mains with sides, one-pot dishes, egg and flour dishes, bakes and gratins, simple baked goods and desserts. Beverages are not meals. | Defines the population for the 95 %. | M | R | B5 |
| MEAL-002 | Coverage by count: ≥ 95 % of the meals in the corpus shall be *preparable* as defined in MEAL-010. | Brief. | M | A (V2 walk-through), later T on a sample | B5 |
| MEAL-003 | Coverage by frequency: if the corpus gives a frequency weight per meal, the weighted coverage shall be ≥ 97 %. | The meals eaten most often matter most. | S | A | B5 |
| MEAL-004 | Coverage by category: in every category of the corpus with ≥ 10 meals, ≥ 85 % shall be preparable. | The 5 % must not wipe out a whole category (e.g. all baking). | S | A | B5 |
| MEAL-005 | Regardless of percentages, the meals named in the brief shall be preparable: a mixed salad with dressing; mashed potatoes; roast beef; Frikadellen; Rouladen; soups (clear with garnish, puréed, stew-like); pan-fried steak; pasta with sauce. | Brief, literally. | M | A, D | B5 |
| MEAL-006 | Every meal that is not preparable shall be listed with the reason and the missing unit operation, so that the 5 % is known, not accidental. | Transparency; basis for customer decisions. | M | R | B5 |
| MEAL-007 | The corpus coverage shall be evaluated by walking each meal's recipe through the designed unit operations, tools, vessels and capacities, for 4 persons; and a sample of ≥ 20 meals spread over all categories for 1 and 6 persons. | Verification method for the paper phase (V2). | M | R | B5, B8 |
| MEAL-008 | If `research/02-meal-corpus.md` and section 5.3 disagree on the set or naming of unit operations, section 5.3 shall be updated to the corpus; until then the union of both applies. | Single source for designers. | M | R | drv |

### 5.2 What "preparable" means

| ID | Requirement | Rationale | Prio | Verif. | Trace |
|----|-------------|-----------|------|--------|-------|
| MEAL-010 | A meal is **preparable** when all of MEAL-011 to MEAL-017 hold. | Definition. | M | — | B5 |
| MEAL-011 | All steps from stored ingredients to plated dish are performed by the machine without human action. | B1. | M | D | B1 |
| MEAL-012 | Ingredients are in a form sold in ordinary supermarkets and ingestible under section 3.9. Basic processed forms are permitted: butchered and portioned cuts, minced meat, filleted fish, shelled nuts, dried pasta, flour, stock or stock concentrate, tinned tomatoes and pulses, frozen vegetables, ready-made puff/filo pastry sheets, breadcrumbs. Ready-made meal components that are the characteristic part of the dish are not permitted (ready sauce for a sauce dish, ready dumplings for a dumpling dish, pre-formed patties, pre-rolled Rouladen, instant mash). | Otherwise 95 % is trivially reached by buying convenience food. | M | R | B5 |
| MEAL-013 | The method may differ from the traditional one if the result is equivalent (*adapted method*, e.g. oven-crisped instead of deep-fried). Adapted meals shall be marked; they count as preparable only if rated per MEAL-015, and no more than 10 % of the corpus may be covered by adapted methods. | Leaves design freedom ("novel tools welcome") without hollowing out the goal. | M | R, T | B5 |
| MEAL-014 | The result is safe: FSF requirements met. | — | M | T | drv |
| MEAL-015 | The result is accepted: in a blind comparison with the same dish by a competent home cook, ≥ 5 raters give a mean ≥ 3.0 of 5 (3 = "as good as normal home cooking") for taste and texture, and none of the recipe's objective criteria (doneness, core temperature, consistency, browning) is missed. | "Cook … normal meals" means edible to home standard, not merely processed. | M | T (prototype), R (paper phase: objective criteria only) | B1 |
| MEAL-016 | It can be prepared for every number of persons from 1 to 6 (largest single pieces, e.g. a roast, may have a minimum size serving more than 1). | B8. | M | A | B8 |
| MEAL-017 | It meets the time target PERF-001 and is completed without human intervention in ≥ 98 % of attempts (REL-001). | — | M | A, T | drv |

### 5.3 Unit operations the machine shall support

Module: P preparation, C cooking/baking, S portioning/serving, X any (architect's choice). Priority M = needed
for the 95 %; S = raises coverage or quality, expected; C = optional. The "limits" are minimum capabilities.

**Handling and dosing**

| ID | Unit operation | Minimum capability | Prio | Mod. | Examples |
|----|----------------|--------------------|------|------|----------|
| UO-01 | Dose from box: all ingredient forms of PRP-010 | PRP-011 | M | P | everything |
| UO-02 | Dose water | PRP-015 | M | P/C | soups, pasta |
| UO-03 | Transfer vessel → vessel / cooking vessel / baking dish | PRP-013 | M | P/C | all |
| UO-04 | Weigh (ingredient, vessel contents, portion) | ±1 g below 500 g, ±0.5 % above | M | X | all |
| UO-05 | Crack eggs, shell-free (no fragment > 1 mm in 99 % of eggs) | 12 eggs in ≤ 3 min | M | P | cakes, Schnitzel, pancakes, fried egg (yolk intact ≥ 90 %) |
| UO-06 | Separate egg white and yolk | yolk in white ≤ 1 % of cases | S | P | meringue, mousse, hollandaise |
| UO-07 | Open/close lids of boxes and vessels | — | M | X | all |
| UO-08 | Thaw | CLD-013; or thaw as part of cooking | M | X | frozen meat, vegetables |
| UO-09 | Rest / marinate / soak / proof for a set time at a set temperature | 0.1–24 h; ≤ 7 °C, ambient, or 25–35 °C | M | P | Sauerbraten, yeast dough, dried pulses |

**Cleaning and cutting of raw food**

| ID | Unit operation | Minimum capability | Prio | Mod. | Examples |
|----|----------------|--------------------|------|------|----------|
| UO-10 | Wash produce (remove soil, sand) and spin/drain dry | leaf salad: ≤ 5 % adhering water; no grit | M | P | salad, potatoes, leeks, herbs |
| UO-11 | Peel round/oblong firm produce | potato, carrot, apple, cucumber, kohlrabi, celeriac; PRP-022 | M | P | most mains |
| UO-12 | Peel onion and garlic | ≥ 95 % skin-free | M | P | most savoury dishes |
| UO-13 | Trim/core/de-seed/remove stalk | pepper, apple, tomato stalk, cabbage stalk, lettuce heart, bean ends | S | P | stuffed peppers, salads |
| UO-14 | Slice | 1–20 mm, PRP-021 | M | P | cucumber, potato, onion rings, mushrooms |
| UO-15 | Dice / cut sticks and strips | 3–25 mm | M | P | soup vegetables, potatoes, bacon, goulash meat |
| UO-16 | Chop finely | < 3 mm | M | P | onion, herbs, garlic |
| UO-17 | Grate / shred | 1–6 mm | M | P | cheese, carrot, potato (Reibekuchen), cabbage (slaw) |
| UO-18 | Cut raw meat and fish: slices, cubes, strips | 5–50 mm; across the grain as the recipe states | M | P | goulash, Geschnetzeltes, schnitzel from a loin |
| UO-19 | Mince meat | 3–5 mm plate equivalent | C | P | (minced meat is bought, MEAL-012) |
| UO-20 | Flatten / tenderise | to 4–10 mm ±1 mm, area up to 250 × 150 mm | S | P | Schnitzel, Rouladen (may be bought pre-cut thin) |
| UO-21 | Juice / zest citrus | — | S | P | dressings, desserts |
| UO-22 | Halve, quarter, segment; cut bread | pieces up to PRP-020 | M | P | tomatoes, eggs, lemons, potatoes |

**Mixing and transforming**

| ID | Unit operation | Minimum capability | Prio | Mod. | Examples |
|----|----------------|--------------------|------|------|----------|
| UO-30 | Stir / mix / toss | 0.05–5 L; gentle (salad, without bruising) to vigorous | M | P/C | all |
| UO-31 | Whisk / whip / emulsify | cream and egg white to stiff peaks; dressings, mayonnaise | M | P | desserts, sauces, dressings |
| UO-32 | Knead | 0.2–1.5 kg; yeast dough, shortcrust, pasta/Spätzle dough, dumpling and minced-meat masses | M | P | bread, pizza, cake, Frikadellen |
| UO-33 | Mash | potatoes to lump-free (no lump > 5 mm) without becoming gluey | M | P/C | mashed potatoes |
| UO-34 | Purée / blend, hot or cold | to < 1 mm particle size, up to 3 L, up to 95 °C | M | P/C | cream soups, sauces |
| UO-35 | Strain / sieve / press through | 1–3 mm mesh | S | P/C | sauces, Spätzle, lump-free custard |
| UO-36 | Drain / press out liquid | — | M | P/C | grated potato, tinned goods, tofu, thawed spinach |
| UO-37 | Season to recipe and preference | UO-01 at seasoning accuracy; optional closed-loop salt check | M | P/C | all |

**Forming and assembling**

| ID | Unit operation | Minimum capability | Prio | Mod. | Examples |
|----|----------------|--------------------|------|------|----------|
| UO-40 | Form patties and balls from a mass | 20–250 g, ±10 % | M | P | Frikadellen, meatballs, Klöße/Knödel, fish cakes |
| UO-41 | Coat / bread (flour – egg – crumbs), dust with flour | full coverage ≥ 95 % of the surface | M | P | Schnitzel, fish, dusting meat before searing |
| UO-42 | Spread, fill, roll up and secure | meat slice up to 250 × 150 mm with spread + filling, stays closed during browning and braising | M | P | Rouladen (brief), cabbage rolls (S) |
| UO-43 | Layer in a baking dish | alternate solids and sauces, even layers ±20 % | M | P | lasagne, gratin, casseroles, moussaka |
| UO-44 | Stuff hollow vegetables or poultry | — | S | P | stuffed peppers |
| UO-45 | Roll out dough / press into a mould / line a tin | 2–10 mm ±1 mm, up to the tray size | S | P | pizza, tarts, quiche, biscuits |
| UO-46 | Shape small dough items | Spätzle, gnocchi, bread rolls, dumplings from dough | S | P | Spätzle, rolls |
| UO-47 | Pour batter in metered amounts into a pan or mould | ±10 % | M | P/C | pancakes, cakes, omelette |
| UO-48 | Skewer, tie, lard | — | C | P | roasts are bought ready-tied |
| UO-49 | Grease / line a baking vessel | — | M | P/C | cakes, gratins |

**Thermal**

| ID | Unit operation | Minimum capability | Prio | Mod. | Examples |
|----|----------------|--------------------|------|------|----------|
| UO-50 | Boil in water | up to 5 L, COK-004 | M | C | pasta, potatoes, eggs, vegetables |
| UO-51 | Simmer / poach with temperature control | 60–98 °C ±3 K | M | C | soups, dumplings, sausages, poached fish/eggs |
| UO-52 | Steam | up to 1.5 kg of food | M | C | vegetables, potatoes, fish |
| UO-53 | Blanch and shock-cool | — | S | C | green vegetables, tomato skinning |
| UO-54 | Sweat / sauté with stirring | 100–180 °C | M | C | onions, mirepoix, mushrooms |
| UO-55 | Sear / pan-fry pieces with turning | COK-005, COK-009 | M | C | steak, Schnitzel, Frikadellen, fish, fried potatoes |
| UO-56 | Shallow-fry in ≤ 250 mL fat | COK-021 | M | C | Schnitzel, Reibekuchen |
| UO-57 | Braise / stew, lidded, long duration | up to 4 h at 85–160 °C, hob or cavity | M | C | Rouladen, goulash, Sauerbraten |
| UO-58 | Roast in the cavity with core-temperature control | up to 2.5 kg; 80–250 °C | M | C | roast beef, roast pork, chicken parts |
| UO-59 | Bake | 30–250 °C; COK-006 | M | C | gratin, lasagne, cake, quiche, pizza, bread (S) |
| UO-60 | Gratinate / brown from above | — | M | C | gratins, toast dishes |
| UO-61 | Deglaze, reduce, thicken (roux, starch slurry, liaison, cold butter) | reduction to a target mass ±5 % | M | C | sauces, gravy |
| UO-62 | Make a sauce in the pan/roasting vessel from the fond | — | M | C | roast gravy, Rahmsoße |
| UO-63 | Fry thin batter items, flip | Ø up to 240 mm, ≥ 95 % intact | M | C | pancakes, omelette, crêpes |
| UO-64 | Fry / scramble / boil eggs to a set doneness | — | M | C | breakfast, egg dishes |
| UO-65 | Baste / glaze during roasting | — | S | C | roasts, poultry |
| UO-66 | Skim fat or foam | — | C | C | stocks |
| UO-67 | Toast / dry-roast | bread slices; nuts, crumbs with stirring | S | C | croutons, toast |
| UO-68 | Melt / temper gently | 30–60 °C ±2 K | S | C | chocolate, butter, gelatine |
| UO-69 | Deep-fry | — | excluded (X-01); C | C | chips, doughnuts |
| UO-70 | Hold hot / hold cold | COK-017 | M | C/S | all |
| UO-71 | Cool down quickly / set in the cold | COK-022; set desserts ≥ 2 h at ≤ 7 °C | S | C/P | pudding, potato salad, jelly |
| UO-72 | Rest cooked meat | 3–20 min at 50–60 °C ambient | M | C/S | steak, roast |
| UO-73 | Reheat stored leftovers or cooked components | core ≥ 72 °C | S | C | SRV-021 |

**Finishing and plating**

| ID | Unit operation | Minimum capability | Prio | Mod. | Examples |
|----|----------------|--------------------|------|------|----------|
| UO-80 | Carve / slice cooked meat | 2–15 mm slices, roast up to 2.5 kg; slices intact | M | S/P | roast beef (brief), roast pork |
| UO-81 | Portion by mass or count onto N dishes | SRV-002, SRV-003 | M | S | all |
| UO-82 | Ladle / pour liquids and sauces without drips on the rim | 30–400 mL ±10 % | M | S | soup, gravy |
| UO-83 | Place pieces in a defined position and orientation | SRV-005 | M | S | all mains |
| UO-84 | Garnish: sprinkle, dollop, place | 0.5–30 g | M | S | herbs, cream, lemon |
| UO-85 | Cut and lift portions from a baking dish or tin | pieces intact ≥ 90 % | M | S | lasagne, gratin, cake |
| UO-86 | Dress and toss salad immediately before serving | — | M | P/S | salads |
| UO-87 | Unmould | — | C | S | pudding, terrine |

### 5.4 Candidates for exclusion (the "5 %")

Designers may treat the following as outside the required capability. If a candidate can be included at little
cost, it should be. Meals that need an excluded operation, with no adapted method (MEAL-013), fall into the
5 %. V2 shall check that the exclusions together cost no more than 5 % of the corpus; if they cost more, the
cheapest candidates to re-include are (in this order) X-06, X-01, X-09.

| ID | Excluded capability | Justification | Adapted method / consequence |
|----|---------------------|---------------|------------------------------|
| X-01 | Deep-frying in an oil bath (> 250 mL oil) | Fire load incompatible with unattended operation; oil storage, filtering and disposal; hardest cleaning task. | Oven/hot-air crisping of chips, croquettes; shallow-frying of Schnitzel. Doughnuts, tempura fall out. |
| X-02 | Open-flame or charcoal grilling, smoking, flambéing | No flame in an enclosed unattended machine; smoke. | Pan-searing, top-heat browning. |
| X-03 | Butchery: gutting, scaling, filleting and skinning whole fish; boning and jointing; plucking; shellfish opening, prawn peeling | Rare in today's households; supermarket sells prepared cuts (MEAL-012); complex anatomy-dependent manipulation. | Buy fillets and cuts. |
| X-04 | Whole large roasts and birds > 2.5 kg (goose, turkey, suckling pig); carving whole birds | A few festive meals per year; sets oven and vessel size for everything else. | Poultry parts and breast/leg roasts up to 2.5 kg. Whole chicken ≤ 1.6 kg roasted and served in halves/quarters: S. |
| X-05 | Meals for more than 6 persons in one run | CAP-001. | Two runs, or family-style serving (SRV-018). |
| X-06 | Hand-shaped filled pasta and dumplings (ravioli, Maultaschen, tortellini, pierogi), hand-pulled strudel dough, laminated dough (croissant, puff pastry from scratch) | Delicate thin-dough manipulation; ready sheets and filled pasta are sold everywhere. | Bought pastry sheets; bought filled pasta with home-made sauce (counts as preparable only if the filling is not the characteristic part). |
| X-07 | Decorative patisserie: multi-layer tortes, piping, icing decoration, sugar work | Not "meals"; endless variety of manual finishing. | Plain cakes, tray bakes, tarts, muffins (S). |
| X-08 | Preserving, canning, jam-making, fermenting, curing, sausage-making | Not meal preparation. | — |
| X-09 | Sourdough and artisan bread with long multi-stage processes; shaped bakery items (pretzels, plaits) | Mostly bought; many hours of process time block the cavity. | Simple yeast bread, rolls, pizza base: S. |
| X-10 | Table-cooking formats: fondue, raclette, hot pot, table grill | The cooking *is* the human activity. | Machine prepares the raw components on platters (C). |
| X-11 | Techniques needing special single-purpose equipment: pressure-cooking, sous-vide in bags, wok cooking over a jet flame, ice-cream churning, waffle/sandwich irons, rotisserie | Each adds a device and a cleaning task for < 1 % of meals. | Longer braising; pan-frying; oven. |
| X-12 | Dishes whose assembly is fine manual craft: sushi, spring rolls, stuffed vine leaves, canapés, decorated open sandwiches | Low share of traditional corpus. | — |
| X-13 | Produce needing special handling: artichokes, whole pineapple, coconut, pomegranate seeds, fresh peas/beans from the pod, chestnut peeling, stoning cherries/plums, asparagus peeling | Shape-specific tools. | Frozen, tinned or prepared forms. White asparagus peeling: S (seasonal staple in Germany). |
| X-14 | Raw-egg, raw-meat and raw-fish dishes served uncooked (tartare, Mett, carpaccio, tiramisu with raw egg) | Food-safety risk without a human judging freshness; only on explicit user opt-in (FSF-024). | Pasteurised egg; cooked variants. |
| X-15 | Drinks: coffee, tea, juices, smoothies, cocktails | Non-goal NG-01. | — |

