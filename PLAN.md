# AutoKitchen — Project Plan

How this project is run. The customer's brief is in [BRIEF.md](BRIEF.md).

## Approach

The work is done by agents; the orchestrator only plans, briefs, sequences and checks hand-overs.
Research is done by Sonnet agents, requirements/design/engineering by Opus agents. Each agent owns
its own files and commits each significant result.

The hard parts of this machine are not the individual mechanisms but the *interfaces* between them
(what is a box, how is it gripped, where is it handed over) and *hygiene* (everything that touches
food must be washable by the machine). So the order is: facts first, then one architecture that
freezes the interfaces, then independent module designs against those interfaces, then an
adversarial integration review.

## Phases

### Phase 1 — Research and requirements (parallel)

| ID | Task | Model | Output |
|----|------|-------|--------|
| R1 | Prior art: cooking robots and automated kitchens, why they succeeded or failed | Sonnet | `research/01-prior-art.md` |
| R2 | Meal corpus: traditional meals decomposed into unit operations, to measure the 95% goal | Sonnet | `research/02-meal-corpus.md` |
| R3 | Storage: standard food containers, grid storage/retrieval mechanisms, off-the-shelf fridges and freezers | Sonnet | `research/03-storage.md` |
| R4 | Food preparation mechanisms: cutting, peeling, mixing, kneading, dosing of solids, powders and liquids | Sonnet | `research/04-food-prep-mechanisms.md` |
| R5 | Cooking, baking, portioning and plating technology | Sonnet | `research/05-cooking-plating.md` |
| R6 | Hygiene and automatic cleaning: hygienic design, CIP, materials, food-safe 3D printing, regulations | Sonnet | `research/06-hygiene-cleaning.md` |
| R7 | Ingestion: packaging types, opening methods, barcode and product databases | Sonnet | `research/07-ingestion-packaging.md` |
| R8 | Standard parts: motion, frames, actuators, grippers, sensors, controllers, with prices | Sonnet | `research/08-standard-parts.md` |
| Q1 | Requirements specification | Opus | `requirements/requirements.md` |

### Phase 2 — System architecture (one agent)

| ID | Task | Model | Output |
|----|------|-------|--------|
| A1 | Module split, kitchen layout (straight and L), the box and vessel standards, transport interface, utility bus, hygiene concept, control concept | Opus | `design/00-architecture.md` |

This document freezes the interfaces. Module designers may not change them; they raise conflicts
in an "Open issues" section instead.

### Phase 3 — Module design (parallel)

| ID | Module | Model | Output |
|----|--------|-------|--------|
| D1 | Ambient storage and the storage box | Opus | `design/01-storage.md` |
| D2 | Cold storage (fridge and freezer) | Opus | `design/02-cold-storage.md` |
| D3 | Transport system | Opus | `design/03-transport.md` |
| D4 | Preparation: tools, vessels, holders, dosing and pouring | Opus | `design/04-preparation.md` |
| D5 | Cooking and baking | Opus | `design/05-cooking-baking.md` |
| D6 | Portioning, plating, serving hatch and dish handling | Opus | `design/06-portioning-serving.md` |
| D7 | Cleaning: dish washer, tool and vessel washing, box washing, machine self-cleaning, water and waste | Opus | `design/07-cleaning.md` |
| D8 | Ingestion, versions A (automatic) and B (manual), package opening | Opus | `design/08-ingestion.md` |
| D9 | Frame, casing, service access, utilities, electrical and safety | Opus | `design/09-frame-utilities-safety.md` |
| D10 | Control system, sensing, software, recipe format, inventory | Opus | `design/10-control-software.md` |

### Phase 4 — Integration and review

| ID | Task | Model | Output |
|----|------|-------|--------|
| V1 | Interface and consistency review across all modules | Opus | `review/01-integration-review.md` |
| V2 | Recipe walk-throughs: run real meals from the corpus through the design step by step, measure coverage | Opus | `review/02-recipe-walkthroughs.md` |
| V3 | Hygiene and cleanability audit of every food-contact and splash surface | Opus | `review/03-hygiene-audit.md` |
| F1 | Fix the findings in the module documents | Opus | updated `design/*` |
| B1 | Bill of materials, cost and build order | Opus | `design/11-bom-build.md` |
| S1 | Overview document for the reader | Opus | `README.md` |

## Rules for all agents

* Read `BRIEF.md` first. It overrides everything else.
* Write Markdown. Diagrams as ASCII or Mermaid. Dimensions in mm, metric units.
* Give real numbers: dimensions, masses, forces, torques, temperatures, times, part numbers, prices.
  State where a number is an estimate.
* Prefer off-the-shelf parts; 3D-printed or custom parts only where nothing standard fits.
* Every surface that food, steam or splashes can reach needs a stated cleaning method.
* Each document ends with "Open issues" and "Risks".
* Commit each significant result, only your own files, no attribution lines in commit messages.
