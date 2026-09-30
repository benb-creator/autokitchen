# C3 — Critique of the preparation concepts K1…K8: mechanics, robustness, reliability, buildability

Round P4, critic C3. View: machine designer and reliability engineer. Yardsticks: BRIEF (standard parts plus a
3D printer, robust for everyday use, easily accessible for repair), DECISIONS 8 and 11, requirements REL-001…009,
BLD-001…009, MNT-001…010, SAF-010…056, NOI-001…005, PHY-001…015, PRP-020…038, research R4 and R8.

All concept documents are paper estimates by their own advocates. So is this critique: nothing here was
built or measured. Where I recompute a number I show the method so that it can be checked.

Markers: **[D]** taken from the concept document (section given); **[C]** recomputed by me from the document's
own figures and textbook formulas (E = 193 GPa for austenitic stainless, 210 GPa for steel, 70 GPa for
aluminium); **[E]** my estimate. Severity: **fatal** = the design *as drawn* cannot work or cannot meet a
mandatory requirement; **major** = a load-bearing number is wrong by more than about 2× or a mandatory
requirement is missed, repair costs width, money or a defining element; **minor** = weakness with a known
remedy. **Fixable** = repairable while the concept stays the same concept. A "fatal, fixable" finding is a
drawing error that must be repaired before the concept can be compared honestly.

Scope: I read sections 1, 2, 7, 9, 10, 11 and 12 of all eight concept documents in full, the benchmark
summary tables, the two gap documents in their summary and mechanism sections, R8 (linear axes, arms,
grippers, house standard) and R4 (forces, torques, end-effectors). Hygiene is C2's dimension; I touch it only
where it becomes a mechanical or reliability problem (condensation, corrosion, seal wear). Coverage and food
result are another critic's dimension; I use the concepts' own coverage figures without judging them.

Requirements changed after the concepts were written and are still changing while this critique is written:
PHY-002 now allows 2 000–2 200 mm (DEC-11); PHY-004 allows **3 600 mm for the whole MVC and budgets 1.2 m for
the process cell plus 0.6 m for washing** (DEC-17); MEAL-012 no longer permits cut, cored or trimmed vegetables
(DEC-8); the reference household is 2 persons and a meal serves **at most 4** (DEC-18, DEC-19), so REL-003
falls to about 7 300 meal runs. The concepts were sized for 6 persons; where that matters below I say so. I
judge against the current text.

---

## 1. Summary

| | Score (1–10) | Fatal as drawn | Major | One-line verdict |
|---|---|---|---|---|
| K1 ceiling turret | **3** | 2 (fixable) | 6 | Three 5-axis hands that cannot meet each other; the geometry forces 175 moves per meal and the dearest cell |
| K2 vessel stack | **4.5** | 1 (fixable) | 6 | Strong sensing and inversion, but one carriage carries everything, a dropped pot needs a human, and hot tiers are stacked to 2 m |
| K3 drum and belt | **3.5** | 0 | 8 | "No manipulator" hides two (a 5-axis vessel shuttle and a tool-changing arm); 35 actuators and 19 dynamic seals |
| K4 shuttle mat | **3.5** | 1 (fixable) | 5 | A 470 mm cantilevered bar on a 28 mm thin arm cannot keep a mat tracking; zero margin in depth; mats are consumables |
| K5 ram and die | **5** | 3 (fixable) | 3 | The right principle for cutting, drawn with an open C-frame, a 4× force error in the frying book and dies that cost 3× more |
| K6 loose ware | **6** | 1 (fixable) | 6 | Fewest physical unknowns and the best interfaces, but the widest cell, 100–145 grips per meal and a mast that collides with its own press |
| K7 state change | **4** | 0 | 5 | Sound refrigeration physics; the most loose parts (132), the highest cost, and a 45 Hz knife on a loose coupling |
| K8 sealed tub | **6** | 1 (fixable) | 4 | Fewest actuators, no dynamic seal, all drives serviceable from the room, cheapest; everything hangs on unmeasured magnet and friction figures and on a 45 kg door that has no opening path |

No concept is robust enough as drawn. The two best (K6, K8) are best for opposite reasons: K6 because every
mechanism exists somewhere in catering, K8 because it has the fewest things that can wear. The worst (K1, K3,
K4) are those whose defining idea generated the most hidden actuators or the least stiffness per euro.

**Cross-cutting findings that are fatal against the requirements as written** (section 2):

* **X1 Cost.** Re-estimated with oven, ware-washing capacity, safety chain and realistic stainless work, every
  preparation cell costs **24–45 k€**, i.e. **96–180 % of the 25 k€ that BLD-004 allows for the whole MVC**
  (storage, cold storage, transport, washing, serving included). No concept can meet BLD-004; a customer ruling
  on the budget, or on an MVC without some modules, is needed before round P5.
* **X2 Welding.** BLD-002 lists printed parts, cut profiles, laser-cut and bent sheet and simple turned or
  milled parts as the only non-catalogue parts. **Every concept depends on welded stainless** (tangs, tabs, lugs,
  rims, stubs on bought pots; welded cells and tubs), several also on wire-EDM, deep drawing, metal spinning,
  tri-ply welding or refrigerant brazing. BLD-002 must be amended (ordered TIG and laser welding, EDM and
  electropolishing as services) or every concept fails it.
* **X3 Width.** PHY-004 (MVC ≤ 3.6 m) budgets 1.2 m for the process cell and 0.6 m for washing. Normalised
  to that scope (preparation, four heated positions, oven, clean-ware store and ware-washing capacity), the
  concepts need **1.75–3.1 m against 1.8 m**. Only K8 (1.75 m) fits, K2 (1.6–1.9 m) nearly; the rest do not.

---

## 2. Cross-cutting findings

### X1 — Cost: every cell alone exceeds the MVC budget

The concept estimates omit, to different degrees: the oven (K1, K3, K4, K5, K8), ware-washing capacity
(K1, K3, K4, K5 rely on a central washer that must grow for them), a safety chain with guard locking and
safe torque off (only K1 prices a safety relay), and realistic prices for one-off welded and finished
stainless parts (30–80 € per simple welded ware item, 150–400 € per custom tri-ply vessel, 600–2 000 € per
wire-eroded grid [E]). Adders used for the re-estimate in section 4: oven 3.0 k€ where missing; ware-washing
capacity 2.5 k€ where not included; safety chain 1.0 k€; custom ware × 1.4–2 depending on its difficulty;
15 % contingency for a first build. The re-estimates are in the comparison table (section 4); they range
from about 25 k€ (K8) to about 42 k€ (K1).

### X2 — BLD-002 and BLD-005 against what the concepts need

| Process the concept needs | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Welded and polished cell or tub (large weldment) | ● | ● | ● | ● | ● | ● | ● | ● |
| Features welded onto bought pots and trays | ● stubs, ears, tabs | ● rim spools | ● tangs | ● dovetail tabs | ● skirts, lugs | ● tangs, skirts | ● tabs | ● spigots, tangs |
| Welding onto clad (tri-ply) walls | ● pans | ● **all cans** | ● drum | — | ● skirts | ● pots | — | — |
| Wire-EDM or ground monobloc blades | ● dice grids | ● grids | — | — | ● **15 dies** | ● grids | ● grids | ● 2 grids |
| Metal spinning, deep drawing | — | ● cans | ● drum | — | — | — | ● pressed trays | ● **thimbles** |
| Moulded silicone on steel (custom tool) | ● | ● beads | — | ● mat lips | ● | ● | ● | ● |
| Refrigerant brazing and charging | — | — | — | — | — | — | ● | — |
| Welded bellows | — | ● | — | — | — | — | ● | — |

Two remarks. First, welding a turned ring or a skirt onto a **tri-ply wall** (stainless–aluminium–stainless)
is not a job for a normal fabrication service: the aluminium core melts at 660 °C, forms brittle Fe–Al
intermetallics and porosity in the weld root. K2 needs it on every can (rim spool on a tri-ply wall, because
the induction flash needs a heatable wall [D K2 6.2]); K1, K5 and K6 need it only for skirts and stubs, which
can be placed on the stainless-only base ring or on a clamp band. Second, **refrigerant brazing and charging
of R290** (K7) requires a certified technician (F-gas and hydrocarbon handling); it is outside BLD-005 for a
private builder. The fix is a bought, pre-charged unit (an anti-griddle or ice-roll machine), as K7 itself
lists for the prototype.

Custom stainless is the dominant cost and lead-time item in every concept. The number of distinct custom
types (section 4) is therefore a better buildability measure than the number of motors.

### X3 — Width and the new height

| | Stated width | What is inside | Missing for a like-for-like scope | Normalised width [E] |
|---|---|---|---|---|
| K1 | 2 270 | prep, 4 hobs, oven | ware washer (2 chambers asked, A7), store for 110 parts | 2.9–3.2 m |
| K2 | 1 600 | prep, 4 hobs, oven, wash lathe, rack for 60 % of the ware | rack for the rest (+300 mm, or +200 mm of height now allowed) | 1.6–1.9 m |
| K3 | 1 450 | prep, 5 heated positions, oven | ware washer for 12–16 items per meal | 2.0–2.1 m |
| K4 | 1 560 | prep, 4 hobs, oven (above P3/P4) | ware washer; store under the deck is "left to the architect" | 2.1–2.2 m |
| K5 | 1 770 | prep, 4 hobs, oven, clean-ware store | ware washer | 2.3–2.4 m |
| K6 | 2 595 | prep, 4 hobs, oven, store, twin washer | — | 2.6 m |
| K7 | 2 280 | prep, 4 hobs, oven, slot washer | chamber share for 12–15 bulky items | 2.4–2.6 m |
| K8 | 1 750 | prep, 4 hobs, oven, washing of all its own ware | — | 1.75 m |

PHY-004 now budgets 1.2 m for the process cell plus 0.6 m for washing, 1.8 m together. Only K8 fits, K2
nearly; K3 and K4 are 0.2–0.4 m over, K5, K7 and K6 0.5–0.8 m, K1 more than 1 m. K2, K3, K4 and K8 are narrow
because they stack (K2 hot tiers over the oven, K3 hob shelves under the belt, K4 the oven above the hobs, K8
the washer is the cell); stacking is what creates their thermal problems (X5). DEC-19 (at most 4 persons)
shrinks the vessel set (no 9 L pot, 28 cm pans at most) but does not shorten any of the width-setting bays.

DEC-11 (2 200 mm) helps exactly three concepts mechanically: K1 (the Z stroke had 5 mm of margin, [D K1 2.3]),
K2 (the ware rack that holds only 60 % of the ware, [D K2 12.1-1]) and K7 (quill retraction). It does not help
width anywhere, because no concept is limited by height in its width-determining bay.

### X4 — Reliability arithmetic: the move count is the wrong unit

REL-001 allows 2 % of meals to need a human. If half of that budget is given to handling and half to food
processes (a Roulade that opens, an egg with shell, a pancake that tears), the unrecovered failure rate per
handling event must be **p ≤ 0.01 / N**, N = events per meal.

The concepts count "moves" differently: K1 counts every hand motion including tool changes; K2, K3 and K5
count only carriage moves; K4 excludes 300–900 mat strokes; K7 and K8 add washing logistics separately. In the
comparison table I normalise to **handling events** = every pick, place, tool change, pour or tip, flip,
press load, mat transfer or dock dose that has its own discrete failure mode [E, from each document's
benchmark walk-throughs and operation tables].

What such mechanisms achieve:

| Event class | Raw success achievable after tuning [E, from industrial practice] | Unrecovered after detection and one retry |
|---|---|---|
| Form-fit grip of a rigid, fixtured part (pin-in-hole tang, neck jaw, lug fork) | 99.9–99.99 % | 10⁻⁵–10⁻⁴ |
| Bayonet or taper pick-up in food soil (K1 V and H interfaces, K8 spigot) | 99.5–99.9 % | 10⁻⁴–10⁻³ (soil in the socket is the failure the retry cannot cure) |
| Magnet shoe or magnet coupling hold (K4 EPM, K8 puck) | 99.9 % + (a function of the gap and the soil, unmeasured) | depends on the decoupling mode |
| Station cycle with force signature (press stroke, drum pour, turntable) | 99.9 % | 10⁻⁴ |
| Transfer of deformable food by a surface (nose pick-up of a wet cutlet, mat NOSE, slice singulation) | 90–99 % | 10⁻²–10⁻³ |
| Pan-pair flip of a whole-pan item | 70–80 % first time [D G-assembly-meat 7.1] | 10⁻¹–10⁻² |

Two conclusions follow, and they apply to every concept:

1. **The food-process events dominate the budget, not the handling.** A Pfannkuchen meal has eight flips at
   70–80 %; no amount of handling reliability rescues that. REL-001 can only be met if the recovery for every
   food-process failure is **degrade and continue** (a torn pancake is served or remade; an opened Roulade is
   braised open) rather than **stop and call**. REL-001 counts interventions, not quality; the software
   architecture must be built around that from the start.
2. For handling events the required 5 × 10⁻⁵ to 1.2 × 10⁻⁴ (section 4) is reachable only for **form-fit
   grips on fixtured parts with a weight check** (K2 neck jaws with load pins, K6 tang pins with jaw-position
   and motor-current check, K5 lugs, K7 tab and cone). Bayonets that must engage in soiled sockets (K1: 30–45
   tool changes per meal) and a magnetic friction drive whose failure is a fall (K8) are one to two orders of
   magnitude short until a rig proves otherwise.

The cycle counts of REL-003 add a wear dimension: 245 grips a day (K6's own figure for 4 persons [D K6 7.3],
perhaps 170 for the 2-person household of DEC-18 [E]) are 0.6–0.9 million in ten years; a bayonet or chuck at
that count is an LRU, as K6 states honestly.

### X5 — Heat, steam, condensation and corrosion

* **Stacked heated positions** (K2 hot column: oven → K/H → S1 → F1 → F2 up to 1 980 mm; K3 hob shelves
  R1–R3 under the belt and its wash box; K4 the oven at 1 500–1 955 mm above P3/P4). Each tier's steam and fat
  aerosol rises into the coils, load cells and drives of the tier above. OEM induction generators are typically
  rated for 40–60 °C ambient [E]; load cells drift with temperature gradients; TPU belts (K3) are rated 80–90 °C.
  None of the three documents has a thermal budget per tier.
* **Drives behind a hot wall** (K8 door cassette behind a skin that sees 85 °C in the wash and radiant heat
  from four hobs; K1 drive room directly above the cook hand's hobs). Electronics limits (60–70 °C), belt and
  stepper derating, magnet grade.
* **Open wash water in the manipulator space** (K6: 60 °C tank and 85 °C rinse wells with one well always open
  as wet parking; K7 sink well). Continuous steam condenses on the mast, arm and camera windows. A fogged
  camera window is a perception failure, and condensate on a mast above open food is a HYG-004 drip.
* **Corrosion.** Salt, pH 12–13 detergent and 85 °C together pit 1.4301 in crevices within months; 1.4404 is
  the minimum for Zone F and S crevices. Ferritic grades used for induction (K3 drum outer skin 1.4016, K7 trays
  1.4016/1.4509, K8 puck ring 1.4016 inside a welded can) must never see the liquor at a cut edge or a weld
  defect. Tri-ply cut edges expose aluminium, which dissolves in alkaline detergent (all concepts with tri-ply
  ware; worst in K2 with a welded rim on every can).

### X6 — The oven turned by 90° with a replaced door (all eight)

Every concept turns a bought built-in combi-steam oven by 90° and replaces or drives its door. That voids the
appliance's own door interlock and certification (SAF-056 requires them to remain effective), puts the oven's
steam release and its control panel into the cell's splash zone, and makes the oven an LRU that must be
exchanged from the front although its mouth faces sideways (MNT-001). This is one architecture decision, not
eight concept details: either a commercial combi oven with a factory automatic door and a side-opening
variant, or an oven served by the transport system from its normal front. The concepts that shrink most if
the oven leaves the cell are K5 (−600 mm), K8 (−600 mm) and K7 (−560 mm).

### X7 — Safety: forces behind a household door

| | Largest force or energy in the cell | Hot-fat inversion | Notes |
|---|---|---|---|
| K1 | ram 3 kN; three rods 300 N | pan pair turned in the air on a PEEK worm, 3.2 kg at 290 mm | all rods retract into the ceiling before the door unlocks: **best SAF-035 case of all eight** |
| K2 | quill 5 kN; turntable 900 rpm; 8 kg inverted at 1.5–2 m | pairs flipped in a vertical shaft; fat above 30 mL runs down the shaft [D K2 4] | flips at head height above four other tiers |
| K3 | gate 800 N; 35 kg drum at 500 rpm; 40 Hz blade | pan pair on the shuttle | stored tension in the dancer and the belt (SAF-034) |
| K4 | blade 1.5 kN; nip 600 N | pan pair on an EPM shoe | stored mat tension on five reels and the arm |
| K5 | ram 8 kN; book leaves (2 kN claimed); rings 600 rpm | **frying book: guided, gasketed, the safest flip of all eight** | the ram acts inside a closed tube: inherently guarded |
| K6 | press 3 kN; wrist 6 000 rpm | pan pair gripped from one side | pH 12–13 liquor in open wells next to the door |
| K7 | press 3 kN; bow knife 45 Hz; sink spin 900 rpm | pan pair on the wrist | R290 below induction generators and an oven grill element (X2, K7-2) |
| K8 | magnets 610 N clamp per puck; screw cassette 2.8 kN inside ware; spindle 6 000 rpm | pan pair on a magnetic puck; a decoupling drops puck and pair | finger pinch between puck and wall in work and travel mode |

All need interlocked doors with guard locking (SAF-033), safe torque off and a PL determined per EN ISO
13849-1 (SAF-002). Only K1 and K5 have made their hazard inherently smaller by design.

### X8 — Software: skills and perception

| | Distinct skills [D or E] | Perception on the hardest step | Free sensing built in |
|---|---|---|---|
| K1 | ~38 [D] | ceiling camera looking down on wet polished steel and food at 300–550 mm | Z motor current (tool weight) |
| K2 | ~25 [D] | shaft camera into carried ware | **load pins in every jaw** (weighs every transfer), squeeze position (mis-seat) |
| K3 | ~30 [E] | top camera on a TPU belt; seam of a roll in the pocket | load cells under drum, belt bed, deck |
| K4 | ~30 [E] | camera 1 over a flat, clean, uniform mat: **the best vision background of all** | reel encoders and torques |
| K5 | ~22 [E] | bore camera looking into a lit tube: **controlled scene** | ram force-travel signature per stroke |
| K6 | ~45 [D] | three fixed cameras, occupancy checks after every release | jaw position, Z current |
| K7 | ~35 [E] | camera over trays; frozen items are rigid and matte | slab lift force, plate temperatures |
| K8 | ~35 [E] | two ceiling cameras through a tub that fogs during cooking | **Hall lag: force ±5 N and torque ±0.3 Nm at every puck for nothing** |

The hard perception problems are the same everywhere: specular stainless, steam, deformable and translucent
food (onion flesh vs skin, egg shell fragments). Concepts that present food against a controlled background
(K4 mat, K5 bore) or that measure force instead of seeing (K2 load pins, K5 ram signature, K8 Hall lag) need
less vision. The skill count matters less than the number of skills that need **closed-loop vision on
deformable food**: K1 about 12, K6 about 10, K7 about 8, K8 about 10, K2 about 5, K3 about 6, K4 about 6, K5
about 4 [E].

### X9 — DEC-8 shifts load from purchase to mechanism

MEAL-012 now forbids bought cut, cored or trimmed vegetables. The gap mechanisms (G-produce GP-11 onion,
GP-61 pepper corer, GP-102 trimming) all require "a means to bring an item to a tool axis within ±15 mm and
±20°" [D G-produce 0.3]. Concepts with a hand (K1, K6, K7, K8) have that; concepts without one (K2, K3, K5,
and K4 except by arm C) need an orienting nest station for each, which adds actuators and events that are not
in their counts. The onion alone (52 % of meals) adds about 8 events per onion (find axis, chuck, two end
cuts, three slits, wipe, jet, check) in every concept, or a batch session at night [D G-produce 1.4].

### X10 — Seal count drives the time between failures

REL-005 asks for ≥ 6 months between failures needing a part exchange. A crude series model [E]: 3 %/year per
servo axis in a dry zone; 25 %/year per lip or rod seal in the splash zone with food soil and daily wash-down;
70 %/year per sealing band on a slot (K2, K5, K6, K7 say "replaced yearly" themselves); 50 %/year per bellows
in reciprocation.

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Axes | 17 | 21 | 35 | 26 | 25 | 16 | 24 | 16 |
| Dynamic seals, bands, bellows in splash | 7 seals + 6 V-rings | 6 seals, 1 band, 1 bellows | 19 seals | 22 rotary passages | ~9 seals, 1 band | 4 seals, 3 bands | 5 seals, 1 band, 1 bellows at 45 Hz | **0** |
| Unplanned exchanges per year [E] | ~3.6 | ~2.9 | ~5.8 | ~4.6 | ~3.7 | ~3.7 | ~3.4 | ~0.6 |
| MTBF [E] | ~3 months | ~4 months | ~2 months | ~2.6 months | ~3 months | ~3 months | ~3.5 months | **~20 months** |

The absolute numbers are soft; the ranking is not. Only K8 meets REL-005 without declaring its seals as
preventive-exchange LRUs (REL-004 route), which then need a technician visit that HUM-007 does not cover.

---

## 3. Findings per concept

### K1 — Ceiling turret cell

K1's explorer already corrected the source documents' reach geometry honestly (Ø 400 instead of Ø 470 per
turret, [D K1 2.2]). The findings below go further.

| # | Finding | Severity | Fixable? |
|---|---|---|---|
| K1-1 | **The four hob positions under T3 collide.** H1 and H3 (front, Ø 280, 3.5 kW) sit at x = 1 240 and 1 510, a pitch of 270 mm [D K1 1, top view]: two Ø 280 frying pans overlap by 10 mm before their welded lift stubs, half stubs and hook tabs (40 mm each) are added; H3's pan touches the right inner wall (1 650) and the door (y = 550). Ø 260 pots with rim ears of 290 span collide either with each other (ears along x) or with the door and H2's pot (ears along y, 5–15 mm). The cause is geometric [C]: the J-lifter carries on the rod axis, so every vessel centre must lie within the rod-axis circle of radius 200; four positions in that circle have at most a 283 mm square pitch, which cannot hold two Ø 280 pans with 40 mm stubs. | fatal as drawn | yes: three positions under T3 and one under T2 (T2 already reaches the left column as "helper"), or +150 mm of width; the pan-pair flip then needs both pans in one zone |
| K1-2 | **The press station reacts 3 kN through two Ø 16 pegs welded to the 2 mm back wall.** The ram acts at y = 110 mm, beyond the 90 mm peg length; the pegs carry 330 Nm together [C]: σ ≈ 400 MPa per peg (W = 402 mm³), above the yield of annealed 1.4404; peg rotation ≈ 0.024 rad, i.e. ≈ 2.6 mm sag and 1.4° tilt at the chamber centre; the 2 mm sheet dents at the weld and the weld toe fatigues over ~10⁵ strokes. The ram foot is the grid's negative [D K1 2.5] and needs < 0.5 mm alignment; it will hit the grid wires. | fatal as drawn | yes: carry the cassette on a pedestal through the deck to the frame, or a closed yoke from the ram housing (one more penetration or a larger C-frame) |
| K1-3 | **Cut-off by a hand-held horizontal blade swept flush under the grid** after every 5–20 mm of ram travel. The ram is 320 mm from both turret centres, outside the 200 mm rod-axis reach, so the blade is carried through the roll head (190 mm offset, open PEEK worm with backlash) at the end of a rod extended ~380 mm. Holding a blade flush within 0.3 mm under a 62 mm grid through that chain is not credible [E]; the result is strings of joined dice, and each sweep is a hand motion (dozens per meal) | major | yes: a cut-off slide on the cassette (K6 has one), at one more part |
| K1-4 | **Reliability exposure is the highest of all eight.** 110–280 moves per 4-person meal (mean 175) including 30–45 bayonet tool changes in soiled sockets [D K1 7]; normalised about 190 events, so p ≤ 5 × 10⁻⁵ is needed. The reach geometry forces relays (every inter-zone transfer through the turntable, a prep cup or the roll head), so the count cannot be cut inside the concept. A tool that falls into a full pot needs a human [D K1 9] | major | no |
| K1-5 | **Five-axis turrets are an expensive way to buy 42 % coverage of the deck.** 15 servo axes, 7.3 m of rotating seam, 8.7 k€ [D K1 7] for three hands whose reach circles never overlap and whose payload off-axis is 4 kg (roll head) | major | no (it is the concept) |
| K1-6 | **Turret cassettes are LRUs at 1.4–2.0 m height** (rings Ø 560, discs, rod, Z tower, five drives: 30–40 kg [E]) that "slide out to the front" of the drive room. Overhead handling of that mass by one person conflicts with MNT-002 (≤ 30 min, hand tools) and reasonable manual handling; a turret fault stops the oven and half the hobs (T3) [D K1 9] | major | partly: a service slide and lift aid |
| K1-7 | **Z stroke had 5 mm of height margin** (595 of 600 mm) [D K1 2.3] | minor now | yes: DEC-11 gives 200 mm |
| K1-8 | **Roll head torque at the limit.** The open PEEK worm (20:1, self-locking, so efficiency ~30–40 % [C: lead angle ≈ 7°, µ 0.25–0.4]) turns 0.65 Nm of core torque into 4–5 Nm, against 2.8 Nm for the dough bowl inversion and 9 Nm on the bayonet for the pan pair [D K1 2.6]; worm wear under 150 000 tool uses a decade with dishwasher chemistry is unknown | minor | yes: it is ware, exchanged like a tool |
| K1-9 | **Cost.** 27.5 k€ without oven and washer; 110 loose parts with welded stubs, ears and tabs on bought (partly clad) pans. Re-estimate 40–45 k€ (section 4) | major | no |
| K1-10 | **Noise of the wash-down**: three 5 bar lances on 5 m² of stainless for 10 min; the explorer expects > 48 dB(A) (NOI-002) without damping [D K1 7] | major | yes: constrained-layer damping on the dry side |
| K1-11 | **Drive room above the hobs.** Steam and grease aerosol from four induction positions rise to the heated ceiling; the seams are air inlets, so the drive room is at over-pressure, good; but motors and belts sit 550 mm above boiling pots in a room without its own cooling | minor | yes: ventilate the drive room |

What K1 does well mechanically: plain round rods through collars are the simplest moving penetration; all
rods retract so that the open cell is free of motion (best jam-clearing safety); the rod stiffness is ample
(0.21 mm at 150 N and 450 mm, recomputed and confirmed [C]).

### K2 — Vessel stack and inversion

| # | Finding | Severity | Fixable? |
|---|---|---|---|
| K2-1 | **The 5 kN press rides on two Ø 30 guide columns in the 160 mm side space**, with the quill and the fork (which holds the grid) both cantilevered about 200 mm from the columns [D K2 2.3]. Moment 1 kNm [C]; 500 Nm per column: σ ≈ 190 MPa; relative tilt of crosshead and fork ≈ 0.015 rad (0.9°) over 250 mm; the fork's bushings see edge loads of ~8 kN. A comb piston entering a 10 mm grid with 1 mm blades needs < 0.5 mm alignment. The same frame is to sheet 1 kg of dough at 2–6 kN [D K2 4] | fatal as drawn | yes: four-column die set or a closed frame round K/H, at cost and some width |
| K2-2 | **One carriage, no recovery from a drop.** All 48 moves per meal, every inversion, every lid clamp and every basket lift go through the Wender; a Wender fault stops everything with hot pots on hobs; **a dropped vessel cannot be gripped again** by neck jaws and needs a human [D K2 9] | major | no (single shaft is the concept) |
| K2-3 | **Rim-to-rim sealing without a centring feature.** R260 flanges meet face to face with a coupler bead at d 259 [D K2 2.1]; concentricity comes only from the jaws, on a two-stage stainless telescope with polymer plain bearings carrying 22 kg at up to 450 mm (≈ 100 Nm) [D K2 2.2]. Sag and play of such a telescope are millimetres [E]; a gasketed hot pair squeezed 2–3 mm off-centre leaks during the roll | major | yes: add a centring cone or spigot to the rim standard (changes R260) |
| K2-4 | **Inverting a hot, closed pair can pressurise it.** A coupler squeezed at 300–450 N holds 0.06–0.09 bar over the d 259 area (0.053 m²) [C]. A pot that is still boiling, or a pair with a warm upper vessel, easily exceeds that; the gasket then opens during the roll and sprays into the shaft at head height | major | yes: a vent valve in the coupler, or no inversion of liquids above ~80 °C |
| K2-5 | **Hot tiers stacked to 1 980 mm.** Oven 50–500, K/H 500–1 180, S1, F1, F2 up to 1 980 [D K2 1]. K/H's load cells, turntable drive and press sit directly on top of a 250 °C oven; F1 and F2 frying pans are at 1.5–2.0 m, where hot-fat flips happen and "fat above 30 mL runs out of the joint into the shaft" [D K2 4] onto every tier below and onto the telescope | major | partly: tier insulation and extraction; the stacking is the concept's width saving |
| K2-6 | **Z mast in 45 mm of depth.** A 1 750 mm Z axis with counterweight for 22 kg, loaded by ~100 Nm about the arm and ~65 Nm forward, lives in a 45 mm zone behind the rear wall; the arm passes a 1.9 m vertical slot under a magnetically held band. PHY-001 counts rear installation space inside the 600 mm | major | yes: take 40–60 mm from the shaft (520 deep, ware is 290) |
| K2-7 | **Custom tri-ply cans with a laser-welded rim spool** (62 custom ware pieces, 43 types) at 90–150 € each [D K2 7]. Welding to a clad wall is metallurgically poor (X2); a spun one-piece rim needs tooling. Realistic 200–400 € per can [E] | major | yes: stainless-only walls with a tri-ply disc base, at the price of the wall flash |
| K2-8 | **The rack holds 60 % of the ware** [D K2 12.1] | minor now | yes: DEC-11 gives 200 mm of rack |
| K2-9 | Eight dynamic penetrations including a Z slot band and a quill bellows above food (conflict with HYG-004/-016 accepted by the explorer) | minor (mechanically) | LRUs |

What K2 does well: the best sensing of all eight (load pins in every jaw weigh every transfer; squeeze
position detects a mis-seat before force is applied); the fewest handling events of the manipulator
concepts; one grip feature (the neck) gives a positive lock in both axial directions.

### K3 — Drum and belt line

| # | Finding | Severity | Fixable? |
|---|---|---|---|
| K3-1 | **"No manipulator" moved the complexity; it did not remove it.** The cell has a 5-axis vessel shuttle (deck Z, head Z, X telescope ±440, roll, grip) that carries, pours, inverts pan pairs and loads the oven, plus a 3-axis tool arm with a bayonet tool change and 15 heads [D K3 2.3–2.5]. That is two manipulators. With the drum, belt, gates and stations the cell has **35 actuators and 19 dynamic seals**, the most of all eight | major | no |
| K3-2 | **Drum dynamics.** Drum 6 kg, outer-rotor motor and pod ~13 kg, coil and yoke ~7 kg, charge up to 9 kg: ~35 kg on a hollow Ø 60 shaft cantilevered from the rear wall, on load cells. Tilt torque at horizontal ≈ 90–100 Nm [C: motor pod 400 mm behind the lip], not 75 Nm [D K3 2.1]; the 150 Nm worm still suffices. Spinning at 480 rpm with 0.3 kg imbalance gives 105 N at 8 Hz [D K3 7], hard-mounted into the rear wall, i.e. **into the building wall** (NOI-005) and into the load cells; a washing machine needs springs and dampers for the same reason. The induction coil is fixed to the yoke with the drum spinning over it; runout of a 350 mm spun cup at 500 rpm against a coil gap of a few mm is a rub risk | major | yes: isolation mounts (then weighing moves to the dry side of the isolators), spin only at low charge |
| K3-3 | **The nose bar cannot hold the guillotine gap.** The Ø 16 nose bar is wrapped 180° by a 300 mm belt [D K3 2.2]: at belt tensions of 300–1 500 N it carries 600–3 000 N over ~320 mm [C]: bending stress 60–300 MPa, mid-span deflection 0.4–2 mm, varying with load. The blade "passes 0.5 mm in front of the retracted nose bar and never touches the belt" [D K3 2.2]; that gap cannot be held over 300 mm, so 1 mm slices and clean overhang cuts are not repeatable. The nose carriage must also hold 2T axially | major | partly: Ø 25–30 nose (worse for thin transfers) or a supported nose |
| K3-4 | **G1 guillotine at 40 Hz, ±5 mm, single blade and bow frame** on two Ø 20 rods through the ceiling [D K3 2.2]. Acceleration ≈ 32 g; a 0.4 kg blade and frame shake the rods and their seals with ~130 N at 40 Hz [C]; noise is tonal; 10 minutes a day is 10⁸ cycles in ten years | major | yes: counter-reciprocating twin blades (electric-knife principle), which is what G-assembly-meat GA-14 recommends |
| K3-5 | **Tool arm: the most complex single penetration of all eight.** Swing, plunge and a 1 kW spindle through one hollow shaft, three concentric shafts and a bevel stage inside a closed arm that dips into the drum [D K3 2.3]; the plunge through a rotating arm needs differential compensation; the gearing needs lubricant above food. Kneading 1.6 kg against the turning drum puts the roller reaction on a 400–500 mm arm against a 40 Nm swing gearmotor [E: 50–100 N → 20–50 Nm] | major | partly |
| K3-6 | **Three single points of failure stop every meal**: drum, shuttle head, dock [D K3 9]; a drum that fails its wash verification blocks the kitchen | major | no |
| K3-7 | **Stacked heat under the belt.** R1 (surface 700) boils under the belt wash box (990–1 100) and the TPU return strand, which is rated 80–90 °C [D K3 2.2] | major | yes: shield and extraction per shelf |
| K3-8 | **The shaft is 370 mm wide**; a GN 2/3 (354) rolls with 5 mm per side; the braiser with lid (diagonal ≈ 371 mm) cannot be rolled [C] | minor | constrains the ware |
| K3-9 | Cost 20 k€ without oven and washer; re-estimate 29–33 k€ | major | no |

What K3 does well: the tilt axis through the pouring lip is an elegant fixed-point geometry; the drum is a
known machine class (tilting kettle, vegetable peeler, washing machine); the shuttle's magnet-coupled
carriages in sealed tubes have no penetration.

### K4 — Shuttle mat

| # | Finding | Severity | Fixable? |
|---|---|---|---|
| K4-1 | **Arm B cannot keep the mat tracking.** Bar B (Ø 40 × 3, 470 mm) is stiff enough (0.36 mm at 300 N, confirmed [C]). The problem is the arm it hangs on: two 430 mm links only 28 mm thick in Y [D K4 2.1]. The mat tension acts about 270 mm out on the bar, i.e. ≈ 81 Nm of out-of-plane moment on the links [C]. For a 28 × 70 × 1.5 box link: out-of-plane bending ≈ 4.4 × 10⁻³ rad and torsion ≈ 4.3 × 10⁻³ rad per link [C], i.e. **2–5 mm of bar skew over its length**, varying with pose and tension. A homogeneous or fabric belt needs roller parallelism of about 1 mm per metre; 0.3–0.7° makes the mat walk onto its flanges and climb its lips | fatal as drawn | only by thickening the arm, which costs mat width (see K4-2) |
| K4-2 | **The 600 mm depth has zero margin** (90 drive room + 3 wall + 60 gallery + 400 mat + 17 + 30 door [D K4 1]) and **omits the rear installation allowance** of PHY-001. The drive room must hold three coaxial-shaft cartridges with 150/80/20 Nm drives "lying flat" in 90 mm. Inside the 28 mm links the elbow drive is a belt carrying 80 Nm: with a Ø 60 pulley that is 2.7 kN of belt tension, against ~0.5 kN for a 15 mm HTD belt [C, R8]; it needs a reduction gear at the elbow (lubricant in a link above food) | major | yes: mat 300–340 mm wide, links 50 mm, drive room 120 mm; then 400 × 300 trays go |
| K4-3 | **The mat is a consumable.** The blade lands with 1.5 kN over 300 mm (5 N/mm of edge) on a 1 mm UHMW-PE film over a silicone strip, "limited to 0.2 mm penetration by torque" [D K4 2.1]. Torque control on a 170 mm lever cannot resolve 0.2 mm against food resistance that varies from 10 to 100 N; the film will be scored and cut. The explorer's own life estimate is 6–12 months for K, 1–2 years for the silicone mats; 570 € per set [D K4 6.7] against MNT-007's 300 € per year for all wear parts | major | partly |
| K4-4 | **The oven hangs at 1 500–1 955 mm above P3/P4** [D K4 1]: a 35–40 kg appliance at head height as an LRU (MNT-002), its electronics and fan inlet in the rising steam of two hobs; hot trays loaded at 1.5 m by an EPM shoe | major | yes: oven below the deck (then arm C must reach down) |
| K4-5 | **One line, strictly serial**; a hem rod that falls behind the table needs a human [D K4 9]; arms B and C cannot pass each other | major | no |
| K4-6 | **EPM shoe on ferritic dovetail tabs**, 8 kg at 800 mm [D K4 2.3]: the holding force of an electro-permanent magnet falls steeply with a water or fat film in the gap; a dropped pan pair is hot fat on the deck | minor | yes: the dovetail can be made a positive lock in the carrying attitudes |
| K4-7 | 300–900 mat strokes per meal on five reels, a dancerless tension control through two reel encoders and the arm pose, and a keder lock of the hem [D K4 2.1]: each stroke is individually reliable, the number is not small | minor | — |
| K4-8 | Cost 16 k€ without oven and washer; re-estimate 25–29 k€, plus 570–650 € a year of mats | major | no |

What K4 does well: rotary shafts only, no slot or linear seal through a wall; a flat, uniform mat under a
top camera is the best vision background of all eight; mats are changed by the householder in 2 minutes
without tools.

### K5 — Ram-and-die column

| # | Finding | Severity | Fixable? |
|---|---|---|---|
| K5-1 | **The "closed frame" is an open C-frame.** Deck and ceiling plates are joined by two Ø 40 tie columns at the *rear* corners of bay A [D K5 2.1]; PRESS is the *front* seat of the turret (Ø 230 pitch circle about an axis near the bay centre), about 300 mm in front of the columns [C, from the top view]. At 8 kN: 2.4 kNm, 1.2 kNm per column, **σ ≈ 190 MPa** (W = 6 283 mm³), rotation ≈ 0.03 rad (1.7°) over 600 mm, **≈ 9 mm of opening** at the ram [C]; plate bending comes on top. Welded column-to-plate joints fail in fatigue at this stress range within 10⁵ strokes. The ≈ 35 J stored in the frame is released when produce breaks through the grid: a snap, an impact noise (NOI-003 L_AFmax 75) and a comb piston thrown into the grid | fatal as drawn | yes: two columns flanking PRESS left and right at ≥ 205 mm from the turret axis (clear of the tubes), which also frees the rear for the shuttle (K5-3) |
| K5-2 | **Grid dies are overstressed and under-priced.** At 8 kN a two-tier Ø 140 grid with 1 mm × 9 mm blades spanning 140 mm loads each of ~28 blades with ~290 N: σ ≈ 370 MPa and lateral buckling [C]; blades must be ~20 mm tall or 1.5 mm thick (which raises the cutting force). A monobloc grid wire-eroded from 20–25 mm plate is 8–30 h of EDM with tapered cuts for the edges [E]: 800–2 000 € per grid, not 250–400 € [D K5 7]. Seventeen dies then cost 6–12 k€, not 2.6 k€. Monobloc grids cannot be resharpened (PRP-034 only by exchange) | major | partly: lower the force rule (single layer, smaller bore), buy commercial push-dicer grids and adapt the rim |
| K5-3 | **The shuttle arm collides with the frame.** The shuttle's Ø 60 arm hangs vertically through a downward-facing slot and travels X 1 250 mm "from the drop position to 250 mm inside the oven mouth" along the rear [D K5 2.4]. To reach the drop position under the carousel in bay A it must pass the tie column at the rear right corner of bay A, which spans z 880–1 480 exactly in its path | fatal as drawn | yes: the column move of K5-1 cures both |
| K5-4 | **Frying book force is 4.4× too small.** "60 Nm, which is 2 kN at the centre of the leaf" [D K5 2.3]: the leaf centre is 132 mm from the hinge (GN 1/2, 265 mm), so 60 Nm gives **450 N** [C]. Flattening cutlets and pressing dough (the book is the concept's flat bench) need 1–6 kN; 2 kN needs 265 Nm per leaf, i.e. larger worm drives on the two lip seals that the explorer already calls the weakest of the concept (in the hinge trough beside frying fat) | fatal as drawn | yes: bigger drives, or move pressing to the ram |
| K5-5 | **Shear-gate moves and the loose die carousel.** A loaded tube slid from one window to the next over a flat plate [D K5 2.1] is a knife-edge wiping a plate: it wears the UHMW lip ring and smears. Loose dies on 4 mm ledges under 8 kN fret | minor | yes: restrict to stiff masses, as the explorer does |
| K5-6 | **Width 1 770 mm, 25 actuators, 96 loose parts**: the column's own simplicity (7 actuators) does not survive the cell [D K5 12.1-13] | major | no |
| K5-7 | Cost 20–22 k€; with realistic dies, safety chain and ware washing 33–38 k€ | major | partly |

What K5 does well: force goes where it can be measured (ram force-travel signature per stroke detects a
jam, a dull blade and a mis-seat before damage); the ram acts inside a closed tube, which is inherently
guarded; the bore camera looks into a controlled scene; the frying book is the safest hot-fat flip of the
eight (guided, gasketed, fixed hinge) once its drives are right.

### K6 — Loose ware and fast washer

| # | Finding | Severity | Fixable? |
|---|---|---|---|
| K6-1 | **The hanging mast cannot cross its own press bench.** The mast (60 × 120, fixed length, foot at z 1 000) hangs from the rear and passes "above the rear hob row" [D K6 1.2, 2.4]; the B2 press has two Ø 30 bars 230 mm above the plate, i.e. at z ≈ 1 080, "carried by the rear wall and a front post" [D K6 2.3]. Bars that run from the rear wall to the front cross every Y position the mast can occupy, 80 mm above its foot. The mast can therefore never travel from the dock and sink side (x < 645) to the hob and wells side (x > 990). Lowering the bars is impossible (tube Ø 110 × 200 plus piston); raising the mast foot loses the deck | fatal as drawn | yes: put the press at one end of the travel (beyond the wells), or make the bars a cassette that the chuck sets in place |
| K6-2 | **The tang on a thin GN flange carries too much moment.** A GN 2/3 tray is held by one 6 × 32 mm tang at the middle of a long side [D K6 2.2]; a 3 L tray with 3 kg of food is 4 kg at 162 mm: **6.4 Nm into a 0.8–1.0 mm flange** [C]. The plastic moment of a 60 mm effective strip of 1 mm 1.4301 is about 3–4 Nm [C]: the rim yields at the tang. A rim-to-rim pair held only at one side gapes more than the "≤ 1 mm" assumed [D K6 2.2] | major | yes: tang on a welded spine along the rim (more weld, more crevice) or carry trays level on a fork |
| K6-3 | **Mast stiffness and settling.** A 950 mm hanging cantilever with a slot for its sealing band is an open section; a 70 N draw cut at the end of the 440 mm Y arm is ≈ 31 Nm of torsion on it [C]. A bought covered linear module used as a free cantilever will twist; with a closed inner tube the first bending mode is ~20–30 Hz [C], acceptable, but every X move at 3 m/s² has a settling time | major | yes: closed torsion tube inside the mast, lower acceleration |
| K6-4 | **Handling count**: 100 grips per meal with returns, 130–145 for full menus [D K6 5.13]; normalised with dosing ≈ 115 events: p ≤ 9 × 10⁻⁵. The explorer states this honestly and makes the tang a form-fit grip with jaw-position and motor-current checks, which is the right answer; it still has to be proven on the proposed 10 000-cycle rig | major | partly (rig) |
| K6-5 | **Open hot wells in the manipulator bay.** One well is always open as wet parking; 60 °C tank liquor at pH 12–13 and 85 °C rinse steam condense on the mast, arm and camera windows (X5) | major | yes: lids closed except during a hang, extraction over the wells |
| K6-6 | **Washer noise** 52–56 dB(A) for 25–30 min against 48 [D K6 7.1]; **width 2.6 m**, the widest | major | noise yes (double wall); width no |
| K6-7 | Cost 21.9 k€ incl. oven and washer; 93 welded items; re-estimate 28–31 k€ | major | no |

What K6 does well: the best interfaces of all eight (one tang with pins through holes: form fit, no latch,
no bayonet, detected by jaw position); nothing novel in physics; redundancy where it is cheap (two wash
wells); every jam point reachable through the front door; a Cartesian gantry, the most robust manipulator per
euro that R8 lists.

### K7 — State change and rigid handling

| # | Finding | Severity | Fixable? |
|---|---|---|---|
| K7-1 | **A 45 Hz knife on a loose coupling.** The bow knife is a loose C-bow mounted by the gantry onto a rod that reciprocates ±6 mm at 45 Hz through a welded bellows [D K7 2.2]. Acceleration ≈ 48 g [C]; a 0.3–0.5 kg bow needs 150–240 N of alternating force through a joint that must also be releasable: it hammers, wears, rattles and is loud. The bellows sees 45 Hz × a few minutes a day = 10⁷–10⁸ cycles over the design life; welded metal bellows at ±6 mm are rated far lower [E] | major | yes: fixed counter-balanced twin blades (as K3-4) with a drive that stays in place; blade exchange as an LRU |
| K7-2 | **R290 in the base under an oven and induction generators.** A 150 g charge in a ventilated base is standard in a fridge; here the base also holds 11 kW of induction electronics and contactors, and the oven above has a grill element whose surface exceeds the 470 °C auto-ignition of propane [E]. Brazing and charging need a certified technician (X2) | major | yes: bought pre-charged unit, R600a or a sealed unit with its own ventilated compartment, no ignition sources in the leak path |
| K7-3 | **The rigid-body idea did not simplify the machine.** 24 actuators, 105 loose preparation items plus 27 cookware (132, the most), 120 moves per meal, 2.28 m, 32 k€ [D K7 8]. The state change itself costs only 2 actuators and the refrigeration set; everything else is a conventional kitchen that K7 still needs | major | no |
| K7-4 | **Contact coefficient depends on flat thin trays.** h = 300 W/m²K needs the 0.6 mm trays to follow 0.2 mm of waviness under 2 kPa [D K7 3.1]. Trays of 0.6 mm ferritic steel that are induction-flashed (1.5 s), washed at 85 °C and carried by a welded 40 × 45 × 3 tab distort; halving h doubles every clamp time [D K7 3.1] | major | partly: thicker trays (less rigid-state benefit per kJ), flatness check in the slot washer |
| K7-5 | **Keep-clear rules make the gantry a scheduling problem**: T1 must be empty of anything above 40 mm when a tray enters the oven, the bow knife must be dismounted before anything crosses from sink to hob, the braiser on P3 overlaps P1 [D K7 2.4]. Each rule is a collision if the software gets it wrong | minor | yes: layout |
| K7-6 | Gantry: a cantilevered Y module 550 mm from a belt module on the rear wall carries ~16 kg at the quill: ~90 Nm on the X carriage [C]. Plain igus ZLW modules are rated for 300 N radial and low moments [R8 2.3]; a profile-rail module is needed | minor | yes: cost |
| K7-7 | Cost 32 k€ incl. oven; re-estimate 37–41 k€ | major | no |

What K7 does well: the thermal physics is checked properly (enthalpy model, handling windows [D K7 3]); fixed
evaporator plates with loose aluminium slabs as a thermal store remove every moving refrigerant line — a
genuinely good mechanism; the under-deck pull-down press on two rods in pure tension (σ ≈ 5 MPa per Ø 20 rod
[C]) with a symmetric crosshead is **the soundest press structure of all eight**; rigid items make grasping
more reliable.

### K8 — Sealed tub with magnetic pucks

The explorer's magnetic model is careful; my rough magnetic-circuit estimate gives about 500 N of clamp at the
4 mm gap [C: B ≈ 0.55–0.6 T in the gap after leakage, 20 poles of 196 mm²], close to the design value of
610 N. The force numbers are therefore plausible; they are also the concept's single point of truth and are
unmeasured.

| # | Finding | Severity | Fixable? |
|---|---|---|---|
| K8-1 | **The drive door has no opening path inside the envelope.** The front door (1 100 × 700 × 115 mm) carries the skin, two X bridges, two Z carriages, two heads with 20 magnets each and their drives: 40–50 kg [E]. Its hinge is not specified. Side-hinged it sweeps 1 100 mm into the room, bottom-hinged about 815 mm at 900 mm height, both against PHY-010 (≤ 600 mm); top-hinged it would reach about 2 400 mm, above PHY-002's 2 200. MNT-005 needs the door opened for every jam | fatal as drawn | yes, by a ruling on PHY-010 for a service-only door, or a tub no taller than about 480 mm, or a lift-and-slide door with counterbalance |
| K8-2 | **Drives in a hot, closed door.** Steppers, BLDC servos, belts, Hall sensors and electronics sit in a 115 mm cassette behind a 1.5 mm skin that reaches 85 °C in the wash and faces four induction positions; the décor panel must stay ≤ 50 °C (SAF-021), so the cassette must be insulated from the room and ventilated from somewhere (noise). The explorer lists it as risk 12 | major | yes: forced ventilation of the door cassette, electronics outside the door |
| K8-3 | **Tribology of the wall.** 610 N per puck is squeezed through the skin between four PEEK skids and three ball transfer units [D K8 2.3]. A 15–25 mm steel ball at ~200 N on 1.5 mm austenitic sheet gives Hertz stresses of 1–1.5 GPa [C], far above yield: the dry face will be tracked and dented over 10⁵ passes, and the gap budget (± 0.5 mm) drifts. PEEK skids at PV ≈ 1–2.5 MPa·m/s wear 1–5 mm over the design life [C, k ≈ 10⁻⁶ mm³/Nm] against a wet clearance of 1.2 mm; grit (salt, sugar, bone chips) scores the wet face | major | yes: PTFE or UHMW glide pads instead of balls on the dry side; skids as dated wear parts on the puck (they are ware anyway) |
| K8-4 | **Every force path sits at its limit.** 110 N moving, 20 Nm tilt, 12 Nm rotor [D K8 2.1]; a 100 N push cut at 200 mm is "at the limit"; a decoupling during a hot-fat flip drops puck and pan pair; a falling 1.1 kg puck delivers 4.3 J to the glass-ceramic [D K8 2.1]. The concept's margins are those of a magnetic sensor-actuator, not of a machine | major | partly: the Hall lag loop yields before breakaway, which is the right design; the margin itself cannot be bought without clamp force |
| K8-5 | **Jets drumming on the room-facing skin.** The 1.5 mm skin is the front wall; the wash jets and the spray balls hit it for 25 min after every warm meal [D K8 7], against NOI-002 (48 dB(A)) | major | yes: constrained-layer damping on the dry side of the skin (without changing the magnet gap) |
| K8-6 | **Cell blocked 25–35 min after a meal**; two pucks and two bridges cannot pass each other [D K8 9] | minor | scheduling |
| K8-7 | **Tub weldment under-priced.** A 1 100 × 475 × 700 coved, polished tub with a flush glass-ceramic plate, two deep-drawn welded thimbles and a door skin flat to ± 0.5 mm over 150 mm for 3.0 k€ [D K8 7] is optimistic; 5–6 k€ one-off [E] | minor | — |

What K8 does well: **zero dynamic seals** and no drive, cable or bearing inside the food space; every actuator
is serviceable from the room behind a décor panel (the best MNT-001 case of all eight); the magnet coupling is
a torque limiter (a pole slip is harmless) and a free force and torque sensor (Hall lag); canned radial
couplings through welded thimbles are known practice in magnetic-drive pumps and mixers; torque-to-thrust
screw cassettes put 2.5 kN inside ware without a penetration; the cheapest cell, and the decisive experiments
cost under 1 000 € [D K8 12].

---

## 4. Normalised comparison

Definitions. **Width** as stated, and normalised to the same scope (X3). **Actuators**: motion actuators as
stated; normalised = without the common front end (dock and egg module) and without the oven door, so that
the cells are compared on their own mechanics. **Custom part types**: machine assemblies plus ware and tool
types made to drawing. **Loose parts**: everything that is picked up, including cookware. **Events per
meal**: handling events of X4 for a 4-person reference meal [E]. **p required**: unrecovered failures per
event allowed if handling gets half of the REL-001 budget (0.01 / events). **Cost**: stated scope, and
re-estimated with oven, ware-washing capacity, safety chain, realistic custom stainless and 15 % contingency
(X1). **Skills**: distinct canned skills; in brackets those that need closed-loop vision on deformable food
(X8).

| | K1 | K2 | K3 | K4 | K5 | K6 | K7 | K8 |
|---|---|---|---|---|---|---|---|---|
| Width stated, mm | 2 270 | 1 600 | 1 450 | 1 560 | 1 770 | 2 595 | 2 280 | 1 750 |
| Width normalised, m (budget 1.8) | 2.9–3.2 | 1.6–1.9 | 2.0–2.1 | 2.1–2.2 | 2.3–2.4 | 2.6 | 2.4–2.6 | **1.75** |
| Motion actuators stated | 17 (+3) | 21 | 35 | 26 | 25 | 16 | 24 | 16 |
| Actuators normalised (cell only) | 17 | 15 | 25 | 20 | 16 | 12 | 17 | **13** |
| Of which in hidden manipulators | 15 (3 turrets) | 6 (Wender) | 8 (shuttle 5, arm 3) | 6 (arms B, C) | 5 (shuttle) | 6 (gantry) | 5 (gantry) | 8 (2 heads) |
| Dynamic seals and bands in the splash zone | 13 | 8 | 19 | 22 | ~10 | 7 | 7 + bellows | **0** |
| Custom part types | ~86 | ~67 | ~65 | ~48 | ~39 (+ dies) | ~85 | ~52 | ~45 |
| Loose parts | ~110 | 76 | 46 | ~41 (+5 mats) | ~96 | 93 | **132** | ~70 |
| Moves per meal as stated | 175 | 48 | 36 | 35 (+300–900 strokes) | 34 | 69 (100 with returns) | 80 (120 with washing) | 65 (+40 washing) |
| Handling events per meal, normalised [E] | ~190 | ~90 | ~85 | ~95 | ~90 | ~115 | ~145 | ~120 |
| p required per event | 5 × 10⁻⁵ | 1.1 × 10⁻⁴ | 1.2 × 10⁻⁴ | 1.1 × 10⁻⁴ | 1.1 × 10⁻⁴ | 9 × 10⁻⁵ | 7 × 10⁻⁵ | 8 × 10⁻⁵ |
| Grip interface in soil | bayonet, stub (weak) | neck jaws + load pins (strong) | tang socket + latch | EPM dovetail | lug fork | tang pins (strong) | tab + cone pin (strong) | bayonet on puck + magnet |
| Recovery from a dropped vessel | tongs, often human | **none: human** | human | human (hot fat) | human for a toppled pot | from above if tang reachable | tongs | other puck lifts it |
| Cost stated, k€ (scope) | 27.5 (no oven, no washer) | 24 (all) | 20 (no oven, no washer) | 16 (no oven, no washer) | 20–22 (no washer) | 21.9 (all) | 32 (no chamber share) | 14 (no oven, no dock) |
| Cost re-estimated, k€ [E] | **40–45** | 32–37 | 29–33 | 25–29 | 33–38 | 28–31 | 37–41 | **24–28** |
| Skills (vision on deformable food) | ~38 (12) | ~25 (5) | ~30 (6) | ~30 (6) | ~22 (4) | ~45 (10) | ~35 (8) | ~35 (10) |
| MTBF, unplanned part exchanges (X10) [E] | ~3 months | ~4 months | ~2 months | ~2.6 months | ~3 months | ~3 months | ~3.5 months | **~20 months** |
| Loudest source vs NOI | wash-down on 5 m² steel > 48 | rasp 70–75 at source; lathe 54 min | rumbler + chop + spin > 5 min loud | blade landings 3/s | grid crack, frame snap (L_AFmax) | washer 52–56 for 25–30 min | 45 Hz knife + rasp near 5 min | jets drumming on the room-facing skin |

Two readings of the table:

* **Per actuator and per seal, K8 and K6 are the simplest cells; K3 and K4 the most complex.** K5 and K2 are in
  between, and their complexity is concentrated in one heavily loaded station (press, Wender), which is good
  for maintenance and bad for single-point failure.
* **Per event, all concepts need 5 × 10⁻⁵ to 1.2 × 10⁻⁴.** The spread is only a factor of 2.4; the grip
  interface and the recovery path matter more than the count. K2, K5, K6 and K7 have form-fit grips on
  fixtured parts; K1's bayonets and K4's magnet shoe are the weakest interfaces.

---

## 5. Scores and justification

| | Score | Justification |
|---|---|---|
| **K6** | **6** | Every mechanism exists in catering or in a hardware store; the tang with pins is the best grip interface; a Cartesian gantry is the most robust manipulator per euro; failures are recoverable from the front door. Against it: 2.6 m, a mast that collides with its press (fixable), a tang that overloads thin GN rims, the highest grip count per meal of the robust concepts, washer noise. It is the concept with the fewest unknowns and the most logistics. |
| **K8** | **6** | Fewest actuators, zero dynamic seals, all drives in the room-side door (best serviceability), torque limiting and force sensing built into the coupling, cheapest and the only concept inside the 1.8 m budget. Against it: all margins are magnetic and unmeasured, the drive door has no legal opening path as drawn, its drives live in a hot box, the wall is a wear surface, and a decoupling is a fall. It is the best cost–robustness bet if a 1 000 € rig confirms the magnet and friction figures. |
| **K5** | **5** | The right principle for cutting, ricing and forming, with the best process sensing (ram signature) and the safest flipper (book). Three drawing errors are fatal as drawn and all fixable: C-frame instead of a closed frame, shuttle through a tie column, book torque 4.4× too low. Dies cost 3× the estimate. |
| **K2** | **4.5** | Excellent sensing (load pins in the jaws), few events, one strong grip feature. But everything goes through one carriage with no recovery from a drop, the press frame is two cantilevered Ø 30 columns, hot tiers are stacked to 2 m with hot-fat flips at head height, the rim has no centring, and its custom tri-ply cans are metallurgically hard to make. |
| **K7** | **4** | Honest thermodynamics and two excellent mechanisms (plate stack with loose slabs; under-deck press in pure tension). But the state change adds cost and 132 loose parts without removing any conventional mechanism; the bow knife is a 45 Hz hammer on a loose coupling; R290 sits under an oven; the dearest after K1. |
| **K3** | **3.5** | Elegant fixed-point drum pour, but two hidden manipulators, 35 actuators, 19 dynamic seals (MTBF ~2 months), a hard-mounted 35 kg spinning drum on the building wall, a nose that cannot hold a 0.5 mm blade gap, a 40 Hz guillotine, three single points of failure. |
| **K4** | **3.5** | Rotary-only penetrations and the best vision background, but the defining 400 mm mat on a 470 mm cantilever hangs from links 28 mm thick and will not track; the depth stack has zero margin and ignores the installation allowance; the mat is a consumable over budget; the oven hangs at head height. |
| **K1** | **3** | Clean retraction safety and stiff rods, but 15 servo axes buy three hands that cannot meet; 175 moves per meal with bayonet tool changes in soil; the four hobs under T3 collide; the press hangs on two pegs in a 2 mm sheet; 30–40 kg turret LRUs at 1.4–2 m height; the dearest cell (40–45 k€) and the widest after normalisation. |

---

## 6. Which concepts are simpler, and which only moved the complexity

| | Claim in the catalogue | What exploration added | Verdict |
|---|---|---|---|
| K1 | "nothing hangs in the cell but three rods; all tools passive" | 17 axes, roll head (a gearbox as ware), turntable relay, prep cups as carriers, 110 loose parts | The passive-tool idea is sound; the turret multiplies axes (5 per hand) and moves, it does not reduce them |
| K2 | "no shaft through a food wall; inversion does everything" | Wender with 6 axes and a 1.9 m slot, tip cradle (inversion cannot merge), hourglass dock with 5 actuators, 76 ware pieces | Simpler in the food path, not in the machine; complexity concentrated in one carriage |
| K3 | "two process machines and **no manipulator**" | vessel shuttle (5 axes) and tool-changing arm (3 axes, 15 heads) | **Complexity moved, not removed.** The most actuators of all eight |
| K4 | "lowest mechanical complexity, 13 actuators" | 26 actuators, arm C (a rigid vessel manipulator), turntables at every hob, liquid station | **Complexity moved.** The mat line proper is still 11 actuators, but it needs a hand-equivalent beside it |
| K5 | "push and fall; very few surfaces" | vessel shuttle (5 axes), book (2), rings (2), 96 loose parts | The column is genuinely simple (7 actuators); the cell around it is not. Honestly stated by the explorer |
| K6 | "conservative: gantry plus loose ware" | 93 items, twin washer inside | What it says it is. Complexity is in logistics (grips), not in mechanisms |
| K7 | "only a plain gantry, trays and a knife" | 24 actuators, press, sink turntable, spin head, slot washer, refrigeration | **Complexity added.** The state change is a booster on top of a full kitchen, as the explorer says |
| K8 | "the manipulator is a dish; zero penetrations" | 16 actuators, 20 utensils, screw cassettes, Y-slide utensil, 70 resident parts | **Genuinely simpler in the machine** (13 cell actuators, 0 seals); complexity moved into ware and software (two pucks, lag control) |

Hidden manipulators and actuators worth naming: K3's shuttle and tool arm; K4's arm C and the five driven
cassette reels; K5's shuttle; K2's hourglass dock (5 actuators for dosing alone); K8's Y-slide utensil (a
depth axis bought back by giving up the roll axis) and the screw cassettes (a press in ware); K1's roll head
(a gearbox carried as ware).

---

## 7. Mechanisms ranked by robustness per unit cost

Across all eight concepts and the two gap documents. "Robustness" = physical margin, precedent in products or
catering, tolerance of soil and wear, recoverability; "cost" = parts plus the actuators and seals it brings.

| Rank | Mechanism | Where | Why |
|---|---|---|---|
| 1 | **Turning vessel under a fixed or hung scraper** (stirring, kneading on the Ankarsrum principle) | K3, K4, K5, K6, K7, K8 (T) | Product precedent, one small drive under the deck, no shaft in food, no tool change, frees the manipulator |
| 2 | **Canned radial magnet coupling through a welded thimble** | K8 T and S | Magnetic-drive pumps and mixers; no seal at all; torque limiting built in |
| 3 | **Pull-down press under the deck on two rods in tension, symmetric crosshead, loose tube and end plates** | K7 (best), K6 (swing variant) | Closed force loop through the frame, drive below food, 3 kN is enough with single-layer loading |
| 4 | **Rasp can or knurled disc on a turning position** (raw peeling) | K5, K7, K3 (rumbler) | Commercial peeler principle, no extra actuator; noise is its cost |
| 5 | **Form-fit tang with pins, or neck jaws with load pins** | K6, K2 (also K7's tab and cone) | Positive lock in every direction, self-checking by jaw position or weight |
| 6 | **Cartesian gantry in a dry box with a 2-axis wrist** | K6, K7 | Cheapest stiffness per euro [R8]; straight paths in a shallow cabinet |
| 7 | **Twin top-loading wash wells** | K6 | Commercial glass- and utensil-washer practice; redundancy for one extra well |
| 8 | **Fixed evaporator plates with loose aluminium slabs** | K7 | No moving refrigerant line; thermal store shaves the peak — robust but only worth its cost where the corpus needs it |
| 9 | **Frying book** (two hinged pans, gasketed) | K5 | Guided, safest hot-fat flip; costs two worm drives and two seals near fat |
| 10 | **Torque-to-thrust screw cassette in ware** | K8 | 2.5 kN from 12 Nm without penetration; thread wear and cleaning to be proven |
| 11 | **Ram and die in a closed tube** | K5 | Excellent process control; expensive in frame and dies at 8 kN; right at 3 kN (see 3) |
| 12 | **Drum tilting about its pouring lip** | K3 | Robust geometry; the spin function is what costs (dynamics, noise) |
| 13 | **Jet gate with the manipulator as the conveyor** | K8 | Programmed wash path; cheap; coverage unproven |
| 14 | **Rim-to-rim inversion on a lift carriage** | K2 | Strong function, one carriage; sealing needs a centring feature |
| 15 | **Wash lathe with induction flash** | K2 | Rotating part past fixed jets is sound; flash on welded rims and tri-ply is doubtful |
| 16 | **Magnetic puck through a flat wall** | K8 | Cheap and seal-free; margins small and unmeasured |
| 17 | **Pan pair turned by a manipulator** (one-side grip, roll head, EPM shoe, puck) | K1, K3, K4, K6, K7, K8 | Food result 70–80 % first time; hot fat in free motion |
| 18 | **Belt with a retracting nose and a guillotine** | K3 | Belt life, nose stiffness and blade gap all marginal |
| 19 | **Roller-blind mat cassettes and the cantilevered mat arm** | K4 | Consumable mats; the arm lacks out-of-plane stiffness |
| 20 | **Reciprocating blades at 40–45 Hz on single blades or loose couplings** | K3 G1, K7 bow knife | Vibration, noise, fatigue; replace by counter-reciprocating twin blades |
| 21 | **Disc-in-disc ceiling turret with rod hand** | K1 | 5 axes and 2.4 m of seam per hand for a Ø 400 reach |

---

## 8. Recommendations for round 2 (P5)

1. **Get three customer or orchestrator rulings before any concept is merged**: (a) BLD-004 cost for the whole
   MVC is not reachable; set a budget for the process cell (my estimate: 25–30 k€ for the best hybrid);
   (b) amend BLD-002 to allow ordered TIG and laser welding, wire-EDM and electropolishing as services;
   (c) decide the oven question once (X6): factory automatic door and side opening, or served by transport.
2. **Build the hybrid on a Cartesian gantry with form-fit grips** (K6's tang with pins, or K7's tab and cone;
   add K2's load pins in the jaws), not on turrets (K1), cantilevered mat arms (K4) or a single shaft carriage
   without drop recovery (K2). Give the gantry a telescoping or retractable mast so that it can clear stations
   (K6-1).
3. **Take force out of the manipulator with K7's under-deck press** (two rods in tension, 3 kN, loose tube and
   end plates from K5 and K6); do not build K5's 8 kN C-frame. Use bought push-dicer grids with an adapted rim
   instead of wire-eroded monobloc dies.
4. **Stir and knead by turning the vessel** (rank 1), preferably with K8's canned couplings where a seal would
   otherwise be needed.
5. **Flip hot fat only in a guided device**: K5's frying book with corrected torque (≈ 265 Nm per leaf for
   2 kN, or pressing moved to the press), or G-assembly-meat's lift-rack turn; not in free manipulator motion.
6. **Run K8's 1 000 € magnet-and-friction rig now** (risks 1, 2, 7, 8 of K8). If it confirms ≥ 200 N holding
   shear and ≥ 12 Nm, K8 is the cheapest, narrowest and most maintainable base and deserves a full P5 design
   with a solved door (K8-1) and a ventilated drive cassette (K8-2). If it fails, drop K8 entirely.
7. **Design recovery as "degrade and continue"** from the start (X4): every food-process failure must have an
   automatic path that serves or remakes, because REL-001 cannot be met by handling reliability alone.
8. **Count seals as a design currency** (X10): no concept with more than about 8 dynamic seals in the splash
   zone meets REL-005 without planned technician exchanges. K3's and K4's seal counts disqualify them as bases.
9. **Keep heat below electronics**: no stacking of hot tiers above drives or load cells (K2, K3, K4) without a
   thermal budget per tier; ventilate every drive box that shares a wall with the cooking space (K1, K8).
10. **Borrow, do not adopt**: from K3 the lip-pivot pour geometry; from K4 the white mat as a vision background
    for flat work and the householder-changeable cassette; from K7 the plate stack only if the coverage critic
    confirms the meals it rescues; from K1 the rule "all moving parts retract before the door unlocks".
11. **Rigs that decide the most per euro**, in this order: K8 magnet and friction (1 000 €); tang and pin grip,
    10 000 cycles wet and floured (K6 risk 1, 2 k€); pan-pair flip against frying book (hand rigs, 200 €);
    press force and dice quality with a bought push-dicer grid in a Ø 110 tube on a workshop press (500 €);
    thermal survey of a drive box behind an 85 °C skin (K8 risk 12, 300 €).
