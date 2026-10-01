# Round P5a — improve each concept (K1b … K8b, without K7)

The customer asked for real iteration: each round-1 concept is now improved by its own agent, using
everything learned from all concepts and the critiques. Afterwards K9b combines all improvements into
one machine that is as simple as possible.

## Your job

Take ONE concept Kn and make it **better**: more practical, simpler, more reliable, more hygienic, better
food result, better fit into the whole machine. Keep its core idea (that is what makes it Kn), but you
may replace any sub-mechanism, borrow from the other concepts and gap documents, and remove whatever
the critics showed to be weak. Fix every fatal and major finding of C1–C5 that is fixable. Invent where
needed — new ideas are welcome — but every new idea must be physically argued.

## Binding inputs

* `DECISIONS.md` — all of it. Note especially: #8/#25 machine washes, peels, stones and cuts produce
  itself, generically; #9 peeled onions may be bought; #11 height ≤ 2200 mm; #18/#19 2-person household,
  max 4 per meal; #20 simplicity has high weight; #21 job-shop welded stainless allowed; #22/#23 cost and
  water are reported, not gates; #24 the oven may be modified; #26 coverage ≥ 93 %; **#27 K7 is out and
  no step may change the food's texture or result compared with traditional preparation.**
* Criteria and weights: `design/prep/04-decision-matrix.md` (simplicity 30 %, hygiene 25 %, coverage
  20 %, reliability 15 %, system fit 10 %) and the hard limits proposed in `critique/C5-simplicity.md`
  (≤ 10 actuators, ≤ 5 dynamic seals, ≤ 2 novel untested mechanisms, ≤ 70 handling events per meal) —
  meet them or argue an exception explicitly.

## Reading (keep it lean — usage limits matter)

1. Your own concept document `design/prep/concepts/Kn-*.md` — fully.
2. All critique findings about your concept: grep `Kn` in `design/prep/critique/C1…C5` and read those
   sections plus each critique's round-2 recommendations.
3. **All other concept documents** in `design/prep/concepts/` (except K7) — read each one fully enough to
   know every mechanism and idea in it (at least sections 1 Definition, 2 Mechanism, 4 Operation table,
   11 Improvements, 12 Open issues), plus the concept catalogue `design/prep/02-concept-catalogue.md`
   (sub-mechanism inventory). The point of this round is to improve your concept **with the knowledge of
   all the other ideas**.
4. Gap documents `design/prep/gaps/G-produce.md` and `G-assembly-meat.md` — summaries and the
   mechanisms you use.
5. Requirements only where needed (section 5 MEAL/UO, PRP-039 generic peeling, PHY-004 width).

Do not spawn helper agents. Commit a partial version early.

## Deliverable: `design/prep/round2/Knb-<slug>.md`

0. **Brainstorm** — before deciding anything: for each other concept, list what its ideas could do for
   yours (borrow, combine, invert, simplify), and add your own new ideas. At least 20 ideas in total, each
   in one line with a quick verdict (take / maybe / reject and why). Then pick.
1. **What changed and why** — a table: problem (with critique reference) → change → effect on each
   criterion.
2. **The improved concept** — one page definition, dimensioned front and top ASCII views, every actuator
   and seal, stations, ware list, where hob/oven/washer sit, interfaces (box port, transport, serving).
3. **How the hard operations work now** — at least: generic peel/core/stone (several produce types),
   dice onion, Rouladen (fill, roll, secure, sear, braise), breaded Schnitzel in 3–4 mm fat, Frikadellen,
   mash, kneading and shaping dough, pancake flip, draining pasta, carving, plating 2–4 portions nicely.
4. **Benchmark check** B1–B12 (`design/prep/03-exploration-brief.md`) at 2 and 4 persons: yes / adapted
   / no, time, moves — short table, with notes only where something changed.
5. **Cleaning** of every food-contact and splash surface; separation raw / ready-to-eat.
6. **Numbers before → after**: width, actuators, dynamic seals, novel mechanisms, custom parts, loose
   ware, moves per meal, coverage (one consistent standard as in C1), honest cost estimate.
7. **Self-assessment** against the five criteria, before → after, and the remaining weaknesses.
8. **Best ideas for the combined machine** — the 3–5 mechanisms from this concept that K9b should
   consider, each in 2–3 lines.
9. Risks with cheapest kill experiments; open questions.

Commit only your file: `git add design/prep/round2/Knb-*.md && git commit -m "Prep P5a: Knb improved"`
(no attribution lines; a hook pushes).
