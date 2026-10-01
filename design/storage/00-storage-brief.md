# Storage round — brief for the storage and cold-storage designers

The customer asked for designs of (1) how the dense storage grid gets one specific box out, and (2) how the
machine gets boxes out of the fridge and freezer through a (modified) door. Research exists in
`research/03-storage.md` (box families, comparison of grid retrieval mechanisms, cold-storage options, hatch
heat leakage, motors at +4 °C / −18 °C) — but no design yet.

## Customer's framing (binding)

* Brief: boxes are stored **in a dense grid**, and a single specific box must be brought to the exit.
* **Grab from the top** (AutoStore style): needs empty height above each stack equal to a box plus the
  grabber plus leeway → wastes space (≈ 50 %+), **but is accessible for humans** (e.g. service, manual access).
* **Dense in all three directions**: only box height plus leeway per layer; boxes are moved by **pushers or
  belts** in X into an **empty centre column** (like a Rubik's cube / sliding puzzle), then moved in Y along that
  column to the front, where the grabber takes it from the front row only.
* At least three designs: **(a) grab from top, (b) with pushers, (c) with belts**, plus more from your own ideas,
  then compare and pick the best.
* Cold storage: an off-the-shelf fridge/freezer with as few modifications as possible (requirement CLD-007),
  exit thermally closed; show how the door/hatch works and how boxes move inside the cold space.

## Inputs

* `DECISIONS.md` (all; esp. #11 height ≤ 2200 mm, #17/#18/#19 capacity for a 2-person household, #20 simplicity,
  #21 job-shop metal allowed, #22 cost later but #28 target: household appliances + ≈ €2k machine part).
* `requirements/requirements.md` — sections on storage (STO-xxx), cold storage (CLD-xxx), transport (TRN-xxx),
  capacity table (section 6.2: ambient ≥ 70 positions, cool ≥ 8, chilled ≥ 45, frozen ≥ 20, plus empty-box
  reserve), PHY-004 width (machine ≤ 3.6 m; K9b allots ambient 650 mm and cold 1200 mm).
* `research/03-storage.md` sections 1–4 and 6–7.
* `design/prep/concepts/K9b-combined-simplest.md` section 2 only — the hand-over interface to the process cell.

Keep reading lean (usage limits). No helper agents. **Save your file as you go; commit only once, when it is
complete.**

## Each storage design document must contain

1. **Principle** in 3 sentences and a dimensioned ASCII front, side and top view, fitted to the allotted width
   (ambient ≤ 650 mm, or state what it needs), 600 mm depth, ≤ 2200 mm height.
2. **Box standard** it needs (size family, rim, features for pushing/gripping/belts, tag), compatible with
   dishwasher cleaning and −18 °C.
3. **Retrieval sequence** for the worst-case box (deepest, most blocked): every move, time; and the put-away.
4. **Density**: box positions and box volume as % of the enclosure volume; positions per metre of wall.
5. **Actuators, seals, sensors, parts** (bought vs custom), cost estimate (machine part), failure modes and
   recovery (jammed box, dropped box, power loss mid-move), how a human gets a box out by hand if it fails.
6. **Cleaning**: spills, crumbs, a broken box; how the grid itself is cleaned without a human.
7. **Cold variant**: does the same mechanism work inside a fridge (+4 °C) and freezer (−18 °C)? frost, motors
   outside the cold, condensation, door opening time.
8. Score against the criteria (simplicity 30 %, hygiene 25 %, coverage/fit 20 %, reliability 15 %, cost 10 %)
   and the honest biggest weakness. Cheapest experiment to prove it.
