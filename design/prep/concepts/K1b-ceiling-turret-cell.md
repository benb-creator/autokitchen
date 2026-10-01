# K1b — Ceiling turret cell, improved (round P5a)

Round P5a improvement of concept K1 (`design/prep/concepts/K1-ceiling-turret-cell.md`) after the critiques
C1–C5, following `00-improvement-brief.md`. Nothing here was built or tested. [E] estimate, [C] calculated
here, [K] known practice. Decision state: DECISIONS #1–28.

**In one sentence:** one ceiling turret whose rod ends in an elbow arm works *beside* itself instead of
*under* itself — so one hand reaches the whole cell, nothing is relayed, and neither the seam nor the rod
collar is ever above food.

## 0. Brainstorm

### 0.0 Charges to fix (working notes from C1–C5, decision matrix)

* C2 K1-1 FATAL: 6 seam gaps 7.3 m over deck, no fallback. K1-2 Ø1 holes from sump (sand). K1-3 rod tip core
  seal + hex + bore Zone F. K1-4 bore carries potable + drain water (EN 1717). K1-5 scraper rings/lanterns above
  food. K1-6 roll head open worm (PEEK), tongs fin-ray. K1-7 aerosol lance mid-meal; jet gate spins + produce.
  K1-8 118 L / 8.9 kWh, 3 h to clean. K1-9 HDPE board discs. K1-10 peel in gutter. K1-11 seams unseen. K1-12 hob
  joints, oven front in lance zone. R-2 "nothing above an open vessel".
* C3 K1-1 FATAL hob positions under T3 collide (4 in r=200 circle). K1-2 FATAL press on Ø16 pegs in 2 mm wall
  (400 MPa). K1-3 cut-off by hand-held blade via roll head. K1-4 175 moves/190 events, bayonet in soil. K1-5 15
  axes for 42 % coverage. K1-6 turret LRU 30–40 kg at 1.4–2 m. K1-8 roll head torque at limit. K1-9 cost 40–45 k€.
  K1-10 wash-down noise. K1-11 drive room above hobs. Rank 21/21 "disc-in-disc turret". Strengths: rods
  retract → safest jam clearing; plain rod simplest penetration; stiff rod.
* C4 K1-1 FATAL width 2270 (4.5–5 m machine). K1-2 FATAL every budget ~2× (103 L, 7.3 kWh per 2-p meal;
  clean after 3 h; next meal 43–50 min). K1-3 €32 k. K1-4 11 kW hob. K1-5 oven sideways. K1-6 95 transport
  moves. K1-7 110 loose parts, store undefined. K1-9 noise/quiet mode. Strength: can plate; partial limp-home.
  Budget sheet: ≤1200 incl. oven, 3 heated positions on 2 × 2.8 kW, ≤15 L in-cell water, ≤50 moves.
* C1 score 7 (best food). Fix: K1-1 Rouladen tongs → floured flap, sear seam-down untouched, raft/pins;
  K1-3 Schnitzel bread ≤10 min before, 200–250 mL fat; K1-4 cooled potatoes for Bratkartoffeln; K1-5 swirl
  pancake; K1-6 ricer not grid masher; K1-7 patty shape; K1-8 six persons (now max 4); K1-9 fresh herbs, garlic;
  K1-10 florets, cordon bleu pocket, poached egg.
* C5 3.1: 17 act, 13 seals, 7 novel, 10 types, 190 events, 86 custom, 110 loose, 38 skills (12 vision),
  6 cleaning stations. Opportunities: 2 turrets, deck hatch, drop <6 % tools. Limits: ≤10 act, ≤5 seals,
  ≤2 novel, ≤70 events.

### 0.1 Notes per source document

**K2 vessel stack / inversion.**
* Load pins in the jaws weigh every transfer → put a load cell in each rod's Z carriage (dry side): every
  pick is weighed for free; replaces 5 of 11 deck load cells. *take*
* Press column standing on a hob with a turning pot (rice/purée/knead in the cooking pot) → put K1's press
  over a turning hob position, so ricing and dicing land directly in the pot: no cup relay. *take (variant)*
* Rim-to-rim pair inversion with neck jaws → a pan pair flipped in a guided cradle instead of in the air on
  the open worm. *maybe* (guided flip needs a device; compare GA-36 lift rack).
* Drain stalk with its own pump (not the potable bore) → fixes C2 K1-4. *take* (own hose, or drain sink).
* Grease by spin, flour by tumbling, induction pulse frees the cake; spin-spread pancake batter on a
  turntable → fixes C1 K1-5 if one hob position turns. *take*

**K3 drum and belt.**
* Turning pot on a hob with a scraper hung from a lid arm (SM-180) → K1's cook hand stops stirring; with a
  K8 canned magnet drive no deck seal. *take* (it is C1 rank 2, C3 rank 1).
* "One shaft as the meeting point" → invert K1's relay problem: let all three zones meet at ONE shared
  station instead of relaying T1 → BT → T2 → bench → T3. Better still: fewer turrets, and the stations come
  to the rod (turntable, lift). *take as principle*
* Cutter cartridge (hopper + top-driven bought disc + grid, falls into the pot) driven by the rod's yaw
  (20 Nm, 150 rpm) → dice/slice/grate without the ram. *maybe* (C1 prefers press tube; disc cutters are
  household practice, but need a pusher).
* Boil and drain in one vessel tipped about its lip into a gutter; drain gutter swings under → drain at a
  sink position rather than a drain wand in the potable bore. *take (sink position)*
* Breading without flip (flour bed, rocked egg tray); order on the belt = order in the stack. *reject* (no
  belt; K1's tongs and turner place pieces anyway).

**K4 shuttle mat.**
* Turntable under every hob position + passive scraper hung on a wall peg; "polar placement" (turntable
  angle + one linear coordinate reaches every point of a dish) → a turret over a turntable needs only a
  radial reach, not a full circle: smaller turret, fewer axes. *take (key idea)*
* Water from a fixed spout at each position, never through the hand → the rod bore can stop carrying
  potable water (C2 K1-4). *take*
* Dump port (funnel in the partition to the strainer) for pot water and peel; waste never passes over a
  vessel → K1 drain wand replaced by a pour to a dump funnel. *take*
* Turn plate on a turntable to rotate a flat item 90° → K1 board turntable already does this. *have*
* Mat as sheeting/rolling station, slab–strip–chop dicing. *reject* (mat release unproven, C2 hygiene).

**K5 ram and die.**
* Loose press tube with loose piston standing on a die, product falls straight into the vessel below
  (C1 rank 1): replaces K1's die cassette on wall pegs (C3 fatal K1-2) and the hand-held cut-off (C3
  K1-3) — single-layer loading of slabs through a grid gives dice without any cut-off. *take*
* Force loop closed inside a frame, never through a wall or the hands. *take* (as the rule for K1b's press)
* Ricer plate 3 mm (mash, C1 K1-6), Spätzle plate, former Ø 80, slot die for sheets; tube as paste
  cartridge. *take ricer, Spätzle, former; maybe slot die*
* Rotating round positions: pot skirt in a driven ring, scraper hung on the rim and held by a fixed post.
  *take* (same as K3/K4/K8; K8's canned drive preferred)
* Frying book (guided flip, the safest hot-fat flip). *reject* (2 actuators, 2 seals near fat); keep only
  the principle "flip hot fat in a guided pair" → GA-36 lift rack or a ware-only flip cradle.
* Diverter to a chip box: waste never crosses open food. *take as rule*

**K6 loose ware, fast washer.**
* Workpiece on the fork, blade fixed (peeler post: one-piece flexure with a bought Y-peeler blade) → ONE
  rod peels (fork on the rod, yaw spins the potato past the post); K1 needed two hands to meet. *take*
* Drip collar on every stem tool, grip feature above the collar (SM-202) → the bayonet socket of K1's
  tools stays out of food soil (C3's main doubt about K1's bayonet). *take*
* Pull-down press under the deck (no drive above food) with a loose press tube and end plates incl.
  cut-off slide, ricer, Spätzle, corer-wedger, citrus cone. *take the tube + plates; drive see K7/K8*
* Turning hob positions as carrier ring on rollers + loose scraper hooked on anchor pins. *take*
* Sprung U tongs worked by the jaws → K1 needs no core-driven tongs if the rod has… no jaws. Variant: tongs
  closed by pressing the U into a fixed V-slot? *maybe; see own ideas (canned core coupling)*
* Sink bench = produce wash + waste port; wash wells; tank liquor washes the bay. *take sink; wells → a
  bought fast washer outside the cell (C5 A5)*
* Batch by tool (all seasonings with one tool cycle, two Rouladen per stroke). *take as planning rule*

**K8 sealed tub, magnetic puck.**
* Canned radial magnet coupling through a welded thimble (no seal, torque-limited): (a) under a turning
  hob position and a deck speed spindle (blender, chopper, whisk); (b) **inverted onto K1's rod tip**: the
  core shaft drives a magnet rotor inside a closed, welded rod cap; the tool's bell sits outside → the
  three core lip seals, the hex and the Ø 4 bore at the rod tip disappear (C2 K1-3, K1-4). *take*
* R-torque: force made from torque inside the ware (screw cassette, 12 Nm → 2.5 kN), force loop closed in
  the cassette → K1's rod yaw (20 Nm) could drive it: no ram. *maybe* (thread in ware is novel). A lever
  press driven by the rod's Z push is the household/catering precedent (lever ricer, lever push-dicer). *see
  own ideas*
* R-lean: tools lean on a fixed bracket (lever knife 2.5 : 1 with fulcrum on the board bracket) → cabbage
  and celeriac with a 300 N rod. *take*
* Water from fixed outlets above each station; seasoning never dosed over the hob. *take*
* Whole tub washed after every cooked meal, jet gate through which the hand carries each item. *reject*
  for K1b's ware (bought washer is simpler) — but the per-meal closed-cell wash is exactly K1's model.

**G-produce (gap document).**
* GP-11 onion: three slits with a depth shoe on a spit, dry wipe, jet; K1's spit fork + peeler post host it
  (axis ±15 mm by the camera). GP-17 garlic: crack, press skin-on through a 3 mm plate. *take both* (onion
  as the upgrade path; DEC #9 baseline stays peeled onions).
* GP-61/62 pepper plug corer (Ø 42 tube with stalk cone, ejector) and four-cheek cuts; tube family
  Ø 14/22/42 on one shank → one V-tool family on the rod (Z push 30–50 N, yaw oscillation ±30° = exactly
  what a rod does). *take*
* GP-P1 route by recipe (cook in skin, slip or rice; scrub carrots) → removes most spit peeling; GP-P2
  knurled drum only for raw-peeled uses. *take GP-P1; GP-P2 maybe (a knurled liner in a turning pot)*
* GP-Z1 zest by spinning against a fine rasp at 2–4 N; GP-Z4 pare citrus to the flesh with the shoe blade.
  *take* (rod spins the fruit on a fork against a fixed rasp/peeler post).
* GP-W1 dunk basket over a 40 mm sediment trap, turbidity-terminated; GP-W4 cut leek before washing. *take*
  (the rod plunges the basket: Z stroke at 1–1.5 Hz is a rod's natural motion).

**G-assembly-meat (gap document).**
* GA-20 hairpin-skewer raft through the comb cradle; side folds, dry floured flap, sear seam-down 90 s →
  fixes C1 K1-1 (no tongs on unset rolls). The raft has a handle → the rod lifts and turns it. *take*
* GA-36 lift-rack turn for Schnitzel in 200–250 mL fat (two perforated racks turned in air above the pan;
  only drips move) → fixes C1 K1-3 and C3's "no free hot-fat flip". *take*
* Pan-pair flip rules (≤ 30 mL fat, drip skirt, release check, shallow pans) for whole-pan items. *take*
* Egg: blade-and-spread cracker (strike from below, halves swing apart), one egg per dark saucer, beaten egg
  strained through a 1.5–2 mm plate; slotted saucer for separation. *take* (worked by a rod's Z stroke).
* GA-01 peel with a fixed stripper bar over a collared build spot (burger, toast); GA-03 stand-and-fill
  rack; GA-14 carving trough with overhang cut; GA-39 core tube for powders from a plain box. *take GA-01,
  GA-03, GA-39; maybe GA-14 (K1's knife-and-comb is already good)*

**K6b / K8b (round-2 examples, read for depth).** Both converged on one hand, turning hob positions, a
canned deck spindle, wash after hand-over in one quiet well, the oven at or outside the end, plating in
the cell. K6b took four K1 ideas (hooked pan pair, rim rest, tool rack, deck hatch to the washer). Nothing
new to take beyond the per-concept notes; they confirm the station list and the water/energy method.

### 0.2 Own new ideas

The decisive observation: every charge against K1 has one root. A rod that comes straight down through
a disc can only work **under** its own seams, and a disc can never reach beyond itself — so three turrets
were needed, their circles could not meet, food had to be relayed, and the seams hung over the food.
If the rod carries a **horizontal elbow**, the tool works **beside** the turret, the reach grows beyond the
disc, and one turret is enough.

| # | Idea | Verdict |
|---|---|---|
| N1 | **One turret instead of three.** Parallel work comes from stations (turning hobs, spindle, press), not from hands; relays disappear | **take** |
| N2 | **Elbow rod**: the rod ends in a welded horizontal arm (L = 360 mm). Disc rotation + rod yaw = a two-link SCARA. The inner disc is deleted (−1 axis, −0.9 m of seam); the rod's yaw, which K1 already had, becomes the elbow | **take** |
| N3 | **Radial layout**: food stations stand in two lobes left and right of the turret, **outside the vertical projection of the seam and the rod collar** (C2 R-2 by geometry); under the turret only the wash well and nothing open | **take** (cures C2's fatal K1-1) |
| N4 | Disc-in-disc kept with the elbow (three planar DOF, independent tool yaw) | maybe: option K1b-2D if coupled yaw fails a bench test; +1 axis, +0.9 m seam |
| N5 | **Canned roll coupling at the arm tip**: the core shaft turns a magnet rotor inside a welded can; a removable sleeve rotor (ware) outside carries the tools. A seal-free horizontal roll axis: pour, flip, invert, spit, tongs | **take** |
| N6 | Core torque runs down the rod and along the arm on a belt **inside the closed, welded rod-and-arm body**; the only wet-zone seal of the hand is the rod collar | **take** |
| N7 | **Tongs as a pincer**: one jaw on the roll sleeve, the other hooked to a fixed tab of the arm tip (K8's rotor/spider principle) — no tongs mechanism in ware | **take** |
| N8 | **Load cell under the Z carriage** (dry): every grip weighed, doses as loss in weight from a held box or cup, dropped items detected | **take** (K2 load pins, transposed) |
| N9 | **Bought catering lever push-dicer** (pusher, grids 6/10/20 mm, wedger-corer, fry cutter; plus a ricer plate) on a swing post, worked by the arm pressing the lever: about 2 kN with no actuator, no seal; cuts straight into the pot | **take** (replaces the ram on pegs, C3 fatal K1-2, and the hand-held cut-off, K1-3) |
| N10 | **Two-wall seam flush**: jets on the fixed coaming *and* jets in the turning rim (fed through the disc's cable loop), softened, filtered fresh water at 80 °C, Ø 1.5 holes; air sweep with a pressure switch that parks the hand on loss | **take** |
| N11 | **Downdraft slot between the two hob positions**: aerosol leaves at pan height, so clean filtered air enters through the seams at the top and leaves at the deck | **take** |
| N12 | **Wash well under the turret**: the zone the hand must not use for food is where soiled ware goes down (K1's own deck-hatch idea, C5 opportunity 2) | **take** |
| N13 | Turret shifted 25 mm to the rear: a 75 mm front strip outside the seam projection carries the dump slot and the peeler post | **take** |
| N14 | **Parked arm folds over the turret**: idle, the elbow lies under the disc; nothing hangs over a lobe; door unlocks with a motion-free cell (K1's best safety case kept) | **take** |
| N15 | LRU split: rod and arm (6 kg) are lowered into the cell after unclamping the Z carriage; motors < 3 kg from the front of the drive room; disc ring on drawer rails | **take** (C3 K1-6) |
| N16 | Oven outside the cell, used as bought, served by the transport through the port (as K8b) | **take** |
| N17 | Two-hand cutting (comb + knife) replaced by fixtures: spiked white board on the turntable, comb fence on the board rim, lever-knife fulcrum eye | **take** |
| N18 | A rotating hanger carousel in the well so that the unreachable centre of the well is used | reject: one more actuator for storage only |
| N19 | Second turret as an option module for 4-person menus | reject: +4 axes, +1 seam, +550 mm |
| N20 | Front door as serving hatch (all motion retracts) | reject: the diner's hand in the cell (HYG-007); a port drawer instead |
| N21 | Vertical spit (fork hanging from the tip, spun by the core) | reject: the roll sleeve gives a horizontal spit, as K6b, with the post beside the dump slot |
| N22 | Measuring spoons checked by the Z load cell instead of the spice wand and the 300 g cell | **take** |
| N23 | Pasta and potato water never above 4 L; pots poured by roll into the dump slot; the basket is lifted first | **take** |
| N24 | Heated arm against condensate | reject: the arm sits in the downdraft air path and dries with the cell |
| N25 | Mandrel rolling of Rouladen on the roll sleeve (K1's H6) feeding the GA-20 raft cradle | **take** |

### 0.3 What is picked

From the concepts: K2 load pins (as N8), induction release pulse, spin-spread batter; K3 turning pot with
hung scraper, dump instead of drain wand; K4 polar placement on turntables, water from fixed spouts, dump
slot; K5 press principle (force loop closed in the cassette, product falls into the pot), ricer and
Spätzle plates, diverter rule; K6 peeler post with workpiece on the spit, drip collars, carrier-ring
turning positions, batch-by-tool; K8 canned couplings (turntables, spindle, roll), R-lean lever knife,
water outlets per station. From the gap documents: GP-11, GP-17, GP-61/62, GP-P1, GP-Z1/Z4, GP-W1/W4;
GA-20, GA-36, pan-pair rules, bottom-strike egg cracker with strained egg, GA-01, GA-03, GA-39.
Own: N1–N3, N5–N17, N22, N23, N25. Rejected: mats, belts, drums, frying book, hourglass dock, fluid bores
in the hand, the second and third turret.

---

## 1. What changed and why

Effect columns: S simplicity, H hygiene, C coverage and food, R reliability, F system fit; ++ strong gain,
+ gain, 0 no change, − loss. Critique references: C1…C5 finding numbers of the K1 sections.

| # | Problem (critique) | Change in K1b | S | H | C | R | F |
|---|---|---|---|---|---|---|---|
| 1 | **Reach circles never overlap; food relayed; 110–280 moves per meal** (C3 K1-4, C4 K1-8, C5 S5) | **One turret.** The rod ends in a welded elbow arm (360 mm); disc rotation and rod yaw form a two-link arm that reaches 185–535 mm from the turret axis, i.e. both lobes of the cell. Nothing is relayed; parallel work is done by stations (two turning positions, spindle, press) | ++ | 0 | − (one serial hand) | ++ | + |
| 2 | **7.3 m of rotating seam above open food, no fallback** (C2 K1-1, the only unconditional fatal) | One disc instead of six seams: **1.4 m**. **Radial layout**: every open-food position lies outside the vertical projection of the seam and of the rod collar (C2 R-2 met by geometry, not by a seal); under the turret is only the wash well with its lid. Fallback if the seam test fails: a fixed drip ring under the coaming (the seam then sheds onto the well lid, never onto food) | + | ++ | 0 | + | 0 |
| 3 | Seam jets Ø 1.0 fed from the sump; one wall unwetted; unseen (C2 K1-2, K1-11) | Jets in **both** walls (fixed coaming and turning rim), Ø 1.5, softened and 20 µm-filtered fresh water; air sweep in operation with a pressure switch; seam dry within 15 min after cooking; daily flush, logged per jet ring | 0 | + | 0 | + | 0 |
| 4 | Core lip seals, hex and Ø 4 bore at every rod tip; potable and drain water in one bore (C2 K1-3, K1-4) | **No bore, no tip seal.** The core drives through a **canned magnet coupling** in the closed, welded rod-and-arm body. Water comes from fixed spouts; pots are poured into the dump slot (no drain wand) | + | ++ | 0 | + | 0 |
| 5 | Open PEEK worm roll head as ware; fin-ray tongs (C2 K1-6, C3 K1-8) | The **roll axis is permanent** at the arm tip; the only part in ware is a welded magnet sleeve on a PEEK bush. Tongs are a pincer: one jaw on the sleeve, one on a fixed tab | + | + | 0 | + | 0 |
| 6 | **Four hob positions under T3 collide** (C3 K1-1, fatal as drawn) | Three heated positions in their own slots: H1 Ø 280 and H2 Ø 240 in the right lobe, T0 Ø 280 in the left lobe; centre distances ≥ 280 mm, nothing on a 270 mm pitch | + | 0 | 0 | ++ | + |
| 7 | **Press reacts 3 kN through two Ø 16 pegs in a 2 mm wall** (C3 K1-2, fatal); hand-held cut-off (C3 K1-3) | **No ram.** A bought catering lever push-dicer on a four-leg stand straddles T0; the arm presses its lever (300 N × 7 ≈ 2 kN); the force loop is closed inside the dicer frame. Halves and slabs are loaded single-layer, so no cut-off is needed; ricer plate in the same frame | ++ | + | + | ++ | 0 |
| 8 | **Widest cell, 2270 mm** (C4 K1-1, fatal; C3 X3: 2.9–3.2 m normalised) | **1250 mm** including the ware and dish washer; oven outside the cell as bought (as K8b); 1.85 m with an oven column, like-for-like | + | 0 | 0 | 0 | ++ |
| 9 | **Every budget ~2×; clean after 3 h** (C4 K1-2, fatal; C2 K1-8) | All ware washed in the cell's own well after hand-over; 4 m² of splash zone instead of 5.6, fixed nozzles instead of a held lance: **103 → ≈ 39 L, 7.3 → ≈ 3.2 kWh** per 2-person meal; all clean **20 min** (2 p) / **33 min** (4 p) after hand-over | + | + | 0 | 0 | ++ |
| 10 | 17 axes, 13 dynamic seals, 7 novel mechanisms (C5 S1, S2, S4; C3 X10) | **7 actuators, 2 dynamic seals (none above food), 2 novel mechanisms** | ++ | + | 0 | ++ | + |
| 11 | ~110 loose parts, 46 tool types, ~86 custom types, 38 skills (C5 S7, S8, S12; C3 X8) | **≈ 57 items, ≈ 45 custom types, ≈ 26 skills** (8 with vision): tools merged, fixtures from the gap documents, roll head and rails gone | ++ | + | 0 | + | + |
| 12 | Turret LRU 30–40 kg at 1.4–2 m (C3 K1-6) | Heaviest LRU 6 kg (rod with arm), lowered into the cell after unclamping; motors ≤ 3 kg from the drive-room front; slewing ring with disc on drawer rails | + | 0 | 0 | + | + |
| 13 | Drive room above the hobs (C3 K1-11) | The drive room sits above the turret and the well only; above the hob lobe is the extraction plenum | 0 | 0 | 0 | + | 0 |
| 14 | Lance wash-down 33 min, noise (C5 A4, C3 K1-10, C4 K1-9) | Fixed nozzles: hob zone after every cooked meal (6 L, 4 min), whole cell daily; damped sheet; no lance skill | + | + | 0 | + | + |
| 15 | HDPE board discs; peel in an open gutter; aerosol from a mid-meal lance and spinning jet gates (C2 K1-9, K1-10, K1-7) | White HDPE boards with camera roughness check and yearly exchange; dump slot flushed after every peeling job; no mid-meal lance; produce washed by dunking (GP-W1), never sprayed | 0 | + | 0 | 0 | 0 |
| 16 | Rouladen turned by tongs; Schnitzel in 1.3 mm fat, breaded 30 min early; warm Bratkartoffeln; pancakes thick; grid masher; cylinder patties; frozen herbs, peeled garlic; florets, cordon bleu, poached egg (C1 K1-1…K1-10) | Dry floured flap and GA-20 raft; 180 mL fat, lift-rack turn, breaded ≤ 10 min before frying; potatoes boiled in skin and cooled; spin-spread on H1; riced mash; scooped and smashed patties; GP-21/GP-17 fresh herbs and garlic; GP-25, GA-08, slotted saucer | 0 | 0 | ++ | + | 0 |
| 17 | Oven turned 90° into the wet cell (C4 K1-5, C3 X6) | Oven as bought in the machine's oven column, front-facing, fed by the transport through the port | + | + | 0 | + | + |
| 18 | 95 transport moves per meal (C4 K1-6) | Ware never leaves the cell; transport carries boxes, oven trays, plates and dishes only: ≈ 25 per meal | 0 | 0 | 0 | + | ++ |
| 19 | Z stroke without margin (C3 K1-7) | DEC-11 used: drive room 1500–2200, stroke 440, rod top ≤ 2100 | 0 | 0 | 0 | + | 0 |
| 20 | Plating outside the scope (C4 R-11) | Plating on T0 by polar placement (turntable angle + arm reach); plates leave through the port | 0 | 0 | + | 0 | + |

**What is kept from K1**, because the critics called it its strength: a plain round rod is the only moving
thing that enters the cell from the drive room; all drives are above, dry and outside the wash; all tools
are passive; every motion retracts to the ceiling before the door unlocks (C3: best SAF-035 case); the
widest tool set of all concepts (knife, tongs, spit, turner, mandrel, probe, corers) for the best food
result (C1: 7/10).

---

## 2. The improved concept

### 2.1 Definition in one page

K1b is a welded stainless cell **1250 mm wide, 600 deep, 2200 high** (inside 1200 × 550 × 650 above a deck at
z = 850). One **turret** in the middle of its ceiling carries one hand: a disc Ø 420 turns in the ceiling on
a slewing bearing; a round rod Ø 50 passes through the disc 175 mm off its centre, slides (Z) and turns
(yaw); at its lower end the rod carries a **welded elbow arm** of 360 mm whose tip is a closed can with a
**canned magnet roll coupling**. All tools hang on the roll sleeve. Disc angle and rod yaw place the tool
anywhere 185–535 mm from the turret axis, Z sets the height, the roll tilts, pours, flips and spins.
Four actuators, all in the dry drive room above the turret.

The ceiling seam and the rod collar lie inside a circle of 225 mm radius round the turret axis. **Food
never stands inside that circle.** The cell is therefore laid out radially:

* **Left lobe** — T0, a turning position (canned ring drive, 2.2 kW induction): board, bowl, plates, or a
  third pot; the lever press is set over it when needed. Behind it the canned **spindle** S (blender,
  chopper, whisk, salad spinner, slicing disc) and the **port** to the transport in the left end wall.
* **Right lobe** — H1, a turning position (3.5 kW, Ø 280 pan) and H2, a plain position (2.2 kW); tool
  cabinet in the right end wall; downdraft slots along both end walls.
* **Under the turret** — the **wash well** (380 × 300 opening, 450 deep) under two lids that form the deck.
  It washes all ware and the household's dishes after hand-over and is the closed clean store between meals.
* **Front band** (outside the circle) — the **dump slot** to the strainer and chip box, the **peeler post**
  on its rim, two nests (corer, twist, egg).

Seven rules define it:

1. **Beside, never under.** Open food stays outside the turret circle; the arm reaches it from the side.
   Idle, the arm folds back over the well.
2. **One hand, stations for force and time.** Stirring and kneading by turning vessels, cutting force by a
   lever press, speed by a canned spindle; the hand only places, pours, flips, cuts, peels.
3. **No seal where food can be below it.** The two dynamic seals of the cell (rod collar, disc V-ring) sit
   inside the turret circle; every drive into the food zone is canned (roll, rings, spindle).
4. **One interface on everything.** Every tool and vessel carries the H stub (Ø 22 × 40, two pins) above a
   drip collar; the roll sleeve locks it by 60° of roll; the Z load cell confirms and weighs every grip.
5. **Water in, water out at fixed places.** Spouts at T0, H1, H2; pouring into the dump slot only.
6. **Ware never leaves the cell.** Washed in the well, stored in the well, the tool cabinet or lidded on
   its position; the transport carries food, plates, dishes and oven trays.
7. **Retract before the door.** Rod up, arm over the well, rings and spindle stopped: the open cell has no
   moving part.

### 2.2 Layout

Coordinates in mm: x from the left inner wall (0) to the right (1200); y from the inside of the front door
(0) to the rear wall (550); z from the floor. Turret axis C at x = 600, y = 300 (25 mm behind the depth
centre, which frees a 75 mm front band at the centre). Seam circle: r = 225 round C.

```
FRONT VIEW (door removed)                                outer 1250 W x 600 D x 2200 H
 z
2200 +------------+--------------------------------------+-------------+
     | controls,  | DRIVE ROOM (dry, vented)             | extraction  |
     | power, IO  |  Z carriage + load cell, rod top     | plenum, fan,|
     |            |  (z <= 2100), 4 drives, ring on      | seam-air    |
     |            |  slewing bearing, cable-free core    | fan + H13   |
1500 +==cam=======+=======[ disc 420 ]=coaming 450=======+=====cam=====+  ceiling, heated
     |            |       |  ||rod 50, collar            |             |
     | dicer on   |       |  ||                          | tool        |
     | stand hung |       |  ++==== arm 360 ====[can]=() | cabinet     |
     | on the wall|       |    (parks folded over        |  (flap)     |
     |            |       |     the well)          | tool|             |
     | port, [T0] |       |                        v     |   [H1] pan  |
     | S behind T0|       |                              |  H2 behind  |
 850 +==slot=ring==+==lid==+====== WELL LIDS ======+==lid=+==[ring]=slot+  deck
     | 30 L hot   | coils | WASH WELL 380 x 300   | coils, ring drive, |
     | store,     | ring  | x 450 deep; comb at   | downdraft fan and  |
     | spindle    | drive | x 415 and x 785       | grease filter      |
 400 +------------+-------+-----------------------+--------------------+
     | 8 L tank, wash pump, softener, dosing, drain pump, bio-bin       |
     | drawer under the dump slot                                       |
   0 +------------------------------------------------------------------+
     0           ~300    410                     790                1200  x
```

```
TOP VIEW at deck level (z 850). (  ) seam circle r 225 round C. Reach of the tool: 185 <= r <= 535 from C.

 y=550 ---- rear wall --------------------------------------------------------------------------
       |port |        ( S )        .  '  '  '  '  .           ( H2 )          |tool  |
       |shelf|      jug 160,     '                 '         Ø 240, 2.2 kW   |cabi- |
       |drawer     (300,440)   '   +------WELL-----+ '       plain (945,425)  |net   |
       |y 200|                '    | comb    comb  |  '                       |x 1105|
       | -540|               '     | x415  C x785  |   '                      |-1200 |
       |     |               '     |     (600,300) |   '      downdraft slot  |y 150 |
       |     |                '    +---------------+  '       x 1115-1155    | -450 |
       |dicer|      ( T0 )     '                    '         ( H1 )          |      |
       |hung |   Ø 280, 2.2 kW   '  .    .    .   '           Ø 280, 3.5 kW   |      |
       |y20- |   turning           [nest] [==dump slot==] [nest] turning      |      |
       |190  |   (255,145)       peeler post  x 450-750       (945,145)       |      |
 y=0   ---- front door (glass, interlocked) ------------------------------------------------
       0     150   255            380  450      750  820    945          1105    1200   x
```

Clearances [C]: T0 inner edge 232 mm from C, H1 250, H2 262, S 251, all > 225; the far edges of T0 and H1
are 509 mm from C, H2 481, inside the 535 mm reach. The front band is outside the circle for y < 300 −
√(225² − (x − 600)²): at the dump slot's ends (x 450, 750) that is y < 132, so the slot (y 5–75) and the
nests (y < 110) are clear. The well's combs at x 415 and 785 lie 185–232 mm from C, inside the reach.

### 2.3 The turret and its hand

```
 SECTION THROUGH THE TURRET (drive room above the ceiling, cell below)

  z 2100  ── rod top in the Z carriage (load cell, yaw pulley, core pulley) on a linear rail
            │
  z 1560  ═══╪═══ rod collar cartridge in the disc: PEEK scraper, flush ring, drained lantern,
            │      two guide bushes 120 apart, dry lip seal at the top (LRU from below)
  z 1500  ══[█]══════════════ disc Ø 420 on a slewing bearing; coaming Ø 450 x 40 (seam, below)
            ║ rod Ø 50 x 5, 1.4404, ground and polished; core shaft Ø 16 inside
            ║
  z 1000-   ╚══════════════ arm 80 x 60 welded box, 360 long ══════════╦═══[ can Ø 70 ]=(sleeve)=> tools
  1440       belt from the core pulley to the tip pulley inside the     │   inner magnet rotor in a
             closed body; bolted top lid with a hygienic static gasket  │   welded 0.5 mm can; outer
                                                                        │   sleeve rotor = ware
```

| Axis | Drive (in the drive room) | Data [E] |
|---|---|---|
| D disc | slewing bearing Ø 400 (thin-section, four-point), HTD belt round the ring, closed-loop stepper 3 Nm, ratio 15 | ±200°, 45 Nm, 90°/s; 160 Nm tilting moment carried by the bearing |
| Z rod | ball screw 16 × 5 on a linear rail, servo 400 W with brake; **load cell between carriage and rod** | stroke 440 (arm z 1000–1440), 300 N continuous, 600 N peak, 250 mm/s; weighs ±10 g |
| Y yaw (= elbow) | servo 400 W, belt 1 : 8 to the rod | ±270°, 40 Nm (110 N tangential at the tool), 120°/s |
| K core (= roll) | servo 400 W, belt to the core shaft; in the arm a belt 1 : 2.5 to the tip | roll at the sleeve 0–150 rpm, rated 10 Nm, slips at 15 Nm (torque-limited by the coupling) |

**Kinematics.** Tool point TC = rod axis + 360 mm along the arm. The rod axis lies on a circle of 175 mm
round C (disc angle); the arm direction is the rod yaw. TC reaches every point with 185 ≤ r ≤ 535 from C,
each with two elbow solutions; the tool's heading is tied to its position (radial ± 0–30° in the lobes).
The second heading a knife or turner needs comes from turning the food on T0 or H1. Tools hang 150–250 mm
below the roll axis, so that they reach the deck at the lowest arm position (z 1000). Option **K1b-2D**:
keep K1's inner disc (+1 axis, +0.9 m of seam) for a free tool heading, if a bench test shows that the tied
heading costs meals (risk 6).

**Loads [C].** 300 N down at TC gives 108 Nm on the rod: bending stress 15 MPa (Ø 50 × 5, W = 7 245 mm³),
900 N on each collar bush; sag at TC 1.2 mm from the rod and 0.3 mm from the arm (80 × 60 × 3 box). A 6 kg
pot held at the sleeve with its centre 120 mm further out: 28 Nm on the rod, 7 Nm on the roll (rated 10).
The slewing bearing takes 160 Nm of tilt (300 N at 535 mm); thin-section bearings of this size are rated for
several kNm.

**Roll coupling [E, by comparison with catalogue magnetic couplings and K8's model].** Inner rotor Ø 56 × 45
with 12 encapsulated NdFeB magnets (dry, inside the can, ≤ 80 °C); can 0.5 mm 1.4404 welded into the arm
tip; outer sleeve rotor with 12 SmCo magnets in a welded 1.4404 can (wet, 85 °C wash), on two PEEK bushes,
held axially by a two-lug bayonet on the can. Gap 2.5 mm; rated 10 Nm, break-away about 15 Nm. The sleeve's
outer end is the **H socket**: Ø 22 bore with two J-slots. A tool stub is pushed in along the arm axis and
locked by 60° of roll against the flats of its rest; released the same way. On the arm tip, above the
sleeve, a fixed **reaction tab** (welded, no moving part) takes the second jaw of a pincer tool.

**Penetrations of the cell (complete).**

| Penetration | No. | Type | Above food? |
|---|---|---|---|
| Disc seam Ø 450 | 1 | open coaming gap 4 × 40 mm, air-swept outward; **V-ring on the dry side** (dynamic seal 1) | no: inside the turret circle |
| Rod collar | 1 | scraper, flush ring, drained lantern, **lip seal on the dry side** (dynamic seal 2), LRU | no: 175 mm from C |
| Ring drives T0, H1 | 2 | pinion post driven through a welded thimble (canned coupling) | no seal |
| Spindle S | 1 | welded thimble Ø 40 in a drained pocket | no seal |
| Hob glass (3 coils) | 3 | glass-ceramic bonded flush, static | under vessels (HYG-018 ruling, as all concepts) |
| Well lids | 2 | flaps on open lift-off pins, resting in a drained channel | no seal |
| Port (left wall) | 1 | transport gate, static gasket | — |
| Dump slot, downdraft slots, spouts, nozzles | — | welded | — |
| Cameras (3) and lights | 4 | bonded heated glass in the lobe ceilings | static |
| Front door | 1 | static gasket, drained sill | — |

**Dynamic seals: 2**, both on the dry side of their gap, both inside the turret circle. No slot, band,
bellows or lip faces food.

**The seam, improved (risk 1).** As K1 (open, downward-draining gap 4 mm behind a 40 mm coaming, V-ring
outside), with four changes: (a) **jets in both walls** — eight Ø 1.5 jets in the fixed coaming aim at the
turning rim, four in the rim (fed by a hose in the disc's own cable loop) aim at the coaming; one disc turn
of 400° sweeps every point of both walls; (b) **fresh, softened, 20 µm-filtered water** at 80 °C with inline
detergent, never sump liquor (C2 K1-2); (c) **air sweep** of filtered air 0.3 m/s outward through the gap
whenever the cell is not washing, with a pressure switch: on loss the hand parks and the hobs go to simmer
under lids; (d) **the seam is not above food**, so a drop that leaves it lands on the well lid. Fallback if
the riboflavin test fails anyway: a fixed annular drip ring Ø 470 under the coaming (bolted, washable) that
catches and drains to the well, at the cost of 15 mm of height.

### 2.4 Stations

| Station | What it is | Actuators | Seal |
|---|---|---|---|
| **T0** turning position (left front) | induction 2.2 kW under glass; loose carrier ring Ø 280 on three PEEK rollers, one roller driven by a pinion post through a thimble (K6 ring + K8 canning), 0–120 rpm, 20 Nm; takes the board, the bowl, a plate on its carrier, a pot; anchor pins on the left end wall for the scraper arm, kneading roller and whisk bar | 1 | canned |
| **H1** turning position (right front) | as T0, 3.5 kW, Ø 280 pan or Ø 240 pots; spin-spread, stirring, kneading of mince | 1 | canned |
| **H2** plain position (right rear) | 2.2 kW, Ø 240; dunk-wash vessel when cold | 0 | — |
| **S** spindle (left rear) | 750 W motor under the deck, 0–6000 rpm, 1.5 Nm, inner magnet rotor in a welded thimble Ø 40 in a drained pocket Ø 170 (K8 S, K6b); jug Ø 160 with blade, whisk, slicing-disc and grating-disc rotors (bought processor discs), spin basket Ø 220 in its catch bowl | 1 | canned |
| **Press** (set over T0) | bought catering lever push-dicer (Vollrath InstaCut / Nemco class): pusher sets and grids 6, 10, 20 mm, wedger-corer, fry cutter; a custom ricer plate 3 mm with its pusher. Mounted on a four-leg stand (ware, 320 × 320 span) that straddles T0's vessel; hung on the left end wall when idle. The arm presses a pad on the lever end: 300 N × 7 ≈ 2.1 kN at the pusher | 0 | — |
| **Wash well** (under the turret) | 1.4404, insulated, coved; 380 × 300 opening, 450 deep; two hang combs along x 415 and x 785 (6 slots each, radial); household-dishwasher wash parts (30 L/min pump, 2 kW heater, filter, softener, dosing), 8 L tank at 60 °C, 88 °C rinse water from a 30 L household store charged only while the oven and hobs are off; two lid flaps lifted by the arm by a lug | pumps only | — |
| **Dump slot** (front band) | funnel 300 × 70 over a 2 mm strainer basket and a turbidity sensor; solids to the closed bio-bin drawer; one socket-rinse fan nozzle (< 1 bar, 88 °C) beside it | — | — |
| **Peeler post** (on the slot's rear rim) | one-piece flexure carrying a sprung Y-blade, a paring blade with 2.5 / 5 mm depth shoe (GP-11, GP-Z4) and a fine rasp (GP-Z1); peel falls into the slot | 0 | — |
| **Nests** (front band, x 380 and 820) | silicone-lined V cups with end stops: stab nest for the spit, twist nest for stone fruit, pepper nest for GP-61, egg cradle position | 0 | — |
| **Port** (left end wall, y 200–540, z 870–1070) | transport-owned gate and a 160 mm drawer shelf; boxes in (lid removed outside, C4 R-4), plates out, oven trays out and in, dishes in | (transport) | static |
| **Downdraft** | two slots along the end walls at deck level, one bought hob-extractor fan (300–400 m³/h) with a washable baffle filter; make-up air enters through the seam and a filtered ceiling inlet | fan | — |
| **Spouts** | one at T0, H1, H2 (cold and 60 °C mixed, flow meter), outlet 30 mm inside the vessel rim | valves | — |

**Motion actuators: hand 4 (D, Z, Y, K) + T0, H1, S = 7.** Oven door and port gate belong to the oven
column and the transport. Not counted: 3 pumps, 2 dosing pumps, about 10 valves, 2 fans, 3 induction
modules, 2 heaters.

### 2.5 Ware (≈ 57 food-contact items) and where it lives

All carry the H stub above a drip collar (vessels: on a 40 mm stand-off at the rim; lids: at the centre).
B = bought, B+ = bought with welded stub, C = custom (laser-cut, bent, welded, turned).

| Group | Items | No. | Make | Home |
|---|---|---|---|---|
| Pots | 6.5 L Ø 240 × 160 with basket; 3 L Ø 220 × 90; saucepan 1.5 L Ø 160 (1-person braiser); rondeau 5 L Ø 280 × 90 (braiser, 8 Rouladen in two rafts) | 5 | B+ | nested, lidded, on H2 and H1 |
| Pans and racks | shallow pans Ø 240 × 40, hermaphroditic pair (stub, hook tab, catch — K1's pan pair); lift racks Ø 225, a hooked pair (GA-36) | 4 | B+ / C | closed pair on H1, racks inside |
| Lids | Ø 280, Ø 240, Ø 160 | 3 | B+ | on the pots |
| Bowl, boards | mixing bowl Ø 280; white HDPE boards Ø 270 red and green with a fulcrum eye and a comb-fence rim | 3 | B+ / C | bowl inverted over the boards on T0 |
| Spindle ware | jug Ø 160 with lid, blade, whisk, slicing-disc and grating-disc rotors, spin basket in its catch bowl | 7 | B+ / C | on S, lidded |
| Tools | knife 250 scalloped (also lever knife with the fulcrum eye), tongs jaws red and green (pincer), turner, ladle 100 mL, silicone spatula, measuring spoons 1/5 mL, disher 60 mL, presser, spit fork, mandrel Ø 12 slotted, corer shank with tubes Ø 14/22/42 and ejector, core probe holder, plate carrier, rolling pin with gauge bars | 18 | C (bought blades, probe) | tool cabinet |
| Fixtures | press stand with dicer, grids 6/10/20 mm, ricer plate; raft forks (2) and comb cradle (GA-20); scraper arm, kneading roller, whisk bar; egg cracker (bottom strike, halves on one loose pin) and dark slotted saucer; peeler post; 2 roll sleeves | 17 | B / C | dicer on the wall, rest in the cabinet and the well |
| **Total** | | **≈ 57** (K1: ≈ 110) | | |

Between meals the clean set is in the closed well, the cabinet, or lidded on its position. At the start
of a meal the hand takes out everything the meal needs **before any food is opened**; only then does the
well receive soiled items (one-way in time, C2 R-6). Items left in the well are washed again with the load.

### 2.6 Interfaces

| Interface | K1b offers | K1b asks |
|---|---|---|
| Boxes (transport) | port drawer at the left end wall, z 870–1070 | GN 1/6 and 1/3 PP boxes delivered **opened** (lid station outside, C4 R-4), with a moulded H stub on one short end (Ø 22, two pins); spice boxes GN 1/9 with a levelling edge; egg tray insert |
| Oven | none inside; trays GN 2/3 out and in through the port | an oven column with a front-facing household combi-steam oven fed by the transport (as K8b) |
| Serving | plated food on carriers through the port, 2 plates per 75 s | serving module with a heated hand-over shelf and the hatch (C4 R-11) |
| Dishes (DEC-6) | washed in the well after the meal's ware; plates on edge on the comb, cutlery in a basket | returned through the port in a carrier |
| Utilities | — | 400 V 3N~ (cell peak ≈ 6.8 kW with the hob managed to 5.6 kW on two phases, section 6); cold water, drain; extraction outlet or recirculation; the machine's shared condenser (C4 ENV-010) |
| Waste | closed bio-bin drawer under the dump slot | emptied by the human weekly or by transport |

---

## 3. How the hard operations work now

Times for 4 persons [E]. "Events" = handling events in C3's sense (pick, place, tool change, pour, flip,
press load, dose). Confidence H / M / L as in the concept documents. All tools hang on the roll sleeve;
"roll" is the sleeve's rotation about the arm axis; "radial" is a move of the tool along its own arm.

### 3.1 Generic peeling, coring and stoning (#25, PRP-039): three mechanisms

* **P1 Spit and post.** The spit fork (three prongs, coaxial with the roll axis) is pushed along the arm
  into the produce lying in the stab nest against its end stop (30–60 N, radial). The roll turns the piece at
  30–150 rpm; the arm carries it pole to pole past the **peeler post** on the dump slot's rim, which holds
  three edges on one flexure: a sprung Y-blade (thin skins, 3–6 N), a paring blade with a 2.5 or 5 mm depth
  shoe (thick, knobbly or pithy skins; GP-11, GP-Z4) and a fine rasp (zest, 2–4 N, GP-Z1). The post also
  carries a fixed straight edge for cutting round a stone. Peel falls into the slot; the knife parts off the
  fork-end cap; a stripping notch on the post pulls the piece off the prongs.
* **P2 Rice in the skin.** The lever press with the 3 mm ricer plate over the receiving pot: cooked or soft
  produce goes in with skin, seeds and cores; the flesh passes, the residue stays as a mat on the plate and
  is knocked into the dump slot (food-mill practice [K]).
* **P3 Tubes along the roll axis.** Corer tubes Ø 14, 22, 42 on one shank are pushed radially (≤ 100 N) into
  the produce lying on its side in a nest, while the roll oscillates ±30° (GP-61's rotating-tube cut). The
  plug stays in the tube and is pushed out by the ejector pin when the shank is pressed against the ejector
  post at the slot. Stone fruit: the fruit on the spit is pushed against the post's straight edge until the
  edge stops on the stone (force rise in the disc and yaw currents), turned once; the free half is pushed into
  the **twist nest** and the roll turns 90°: the halves part; the stone is lifted by the disher.

| Produce | Use | Route | Loss, time | Conf. |
|---|---|---|---|---|
| Potato | mash, Klöße | boiled in the skin as halves, P2 | 3–6 %, 60 s per kg | H |
| Potato | Bratkartoffeln, salad | boiled in the skin, cooled, P1 paring at 1 mm | 6–10 %, 12 s each | M |
| Potato | Salzkartoffeln, raw dishes | P1 Y-blade, 150 rpm | 15–20 %, 15 s each | M–H |
| Carrot, parsnip, kohlrabi, apple, kiwi | | P1 Y-blade (carrots > 150 mm halved first); apple cored by the Ø 22 tube or the wedger-corer grid | 10–20 % | M–H |
| Celeriac, ginger, raw pumpkin | | halved by the lever knife on the board; P1 paring 5 mm in facets | 25–30 % | M |
| Cucumber, courgette | | P1 Y-blade, full or striped | 10 % | M |
| Citrus | zest; rounds; juice | P1 rasp; P1 paring 5 mm (à vif, rounds); halves on the bought citrus cone on S, pressed by the presser | — | H / M / H |
| Bell pepper | strips, stuffed | Ø 42 tube from the stalk end in the pepper nest, inverted rinse at the spout (GP-61); recovery four cheeks by knife on the board (GP-62) | 12 %, 15 s | M–H |
| Tomato | core, passata, peel | Ø 14 tube on the scar; P2; blanch 30 s in the basket, P1 paring 1 mm | — | H / H / M |
| Avocado, peach, plum, apricot | | cut round the stone (post edge), twist nest, stone by disher; guacamole: halves through P2 | 25 % | M (pulp), M–L (slices) |
| Mango | cubes, purée | camera finds the stone plane on the spit; two cheeks cut at ±7 mm on the post edge; purée through P2 | 30–35 % | M |
| Banana | bread; slices | ends cut on the board; 40 mm sections through P2 (bread) or stood on the Ø 30 knife ring in the nest and pushed through by the presser (slices; the skin stays outside the ring) | 20–35 % | M |
| Strawberry, cherry (S) | | Ø 14 tube in the nest | 4 s each | M–L |
| Onion (upgrade; #9 baseline peeled) | | GP-11 on the spit: top and tail on the board, three slits by the 2.5 mm shoe, dry wipe, jet at the spout | 10–15 %, 30 s | M |
| Garlic | | cloves in the skin through the ricer plate (GP-17) | — | H |

Three mechanisms, no single-purpose device (PRP-039 asks ≤ 3). Citrus segments are not offered (rounds,
class b).

### 3.2 Dice an onion

Bought peeled onion (#9) from the box by the tongs into the V nest; the knife on the sleeve halves it through
the root with one Z stroke (30–60 N). The press stand is set over the receiving pot (on T0, H1 or H2, cold
or hot; the grid sits 30 mm above the rim). Tongs lay two halves flat side down into the dicer chamber; the
arm presses the lever pad 200 mm down (300 N → ≈ 2 kN at the pusher, staggered 6 mm grid): 6 mm dice drop
into the pot; the root plate stays on the grid and is pushed out by the next load. Two onions: 2 loads, 6
events, 50 s. Confidence H for halves (C1 §5: push dicers do exactly this).

### 3.3 Rouladen: fill, roll, secure, sear, braise (8 rolls)

1. **Slices.** Interleaved butcher's slices (request A6 of K1, kept) are lifted by the tongs' lower jaw slid
   under a corner and laid on the red board on T0. Without interleaf: the corner found by the camera is
   peeled (M–L, the shared G9 gap).
2. **Fill.** Salt and pepper by spoon; mustard by spoon, spread by the spatula drawn along the slice, **stopping
   35 mm before the flap**; the flap salted and dusted with flour (seam glue, G-assembly 4.2); bacon strip,
   onion strip and gherkin spear laid on the first third by the tongs. The turner slides 15 mm under each
   long edge and rolls 180°: the edges are folded in (G-assembly 4.2, measure 1).
3. **Roll.** T0 turns the slice so that its leading edge lies along the arm. The slotted **mandrel** (Ø 12,
   coaxial with the roll) is pushed over the edge; the arm moves sideways at the rolling speed while the roll
   turns, pressing 10 N: 2.5 turns along the stationary slice (K1's H6). The roll is drawn through the U-notch
   of the comb cradle, which strips it off the mandrel, flap at 5 o'clock.
4. **Secure.** With four rolls in the cradle a two-tine raft fork is pushed radially through the cradle's
   guide slots and through all four rolls (30–60 N, GA-20). Two rafts.
5. **Sear.** The rondeau Ø 280 on H1 at 220 °C with 20 mL oil; each raft is laid in seam face down for 90 s
   untouched, then turned about its tines by the roll (the handle is an H stub): two broad faces browned,
   about 60 % of the surface. Searing in two batches avoids crowding (C1 K1-2).
6. **Fond.** Rafts onto the bowl's lid on T0; onion and tomato paste roasted in the fat for 4 min, H1 turning
   under the hung scraper; deglazed with wine, stock and water added from the spout.
7. **Braise.** Rafts back, lid on, 95 °C for 100 min on H1 (simmer; no hand needed).
8. **Finish.** Rafts lifted by their handles and lowered into the cradle; the cradle's comb holds the rolls
   while the fork is drawn out: rolls seam down on the plate carrier. Gravy thickened with a slurry whisked
   in the jug on S, seasoned.

About 60 events for the component; confidence H for holding (raft), M for rolling (the mandrel's grip on a
wet slice is risk 5).

### 3.4 Breaded Wiener Schnitzel in 3–4 mm of fat

Cutlets bought thin (butcher cut, #8) or flattened under the presser between a folded silicone mat (1 kN by
the press stand with a flat plate, ENVELOPE of K4). Breading by tumbling, not by gripping: two cutlets with
flour in the bowl on T0 under its hooked lid, the pair rolled ±60° three times; egg dip in the 3 L pot on H2
(cold): the tongs pinch the edge, the roll turns the cutlet through the egg, 5 s drain; crumbs in the rondeau
under its lid, tumbled twice, pressed at 20 N by the presser. **Breaded ≤ 10 min before frying** (C1 K1-3).

Frying: pan A Ø 240 on H1 with **180 mL of oil = 4.0 mm** [C: 180 cm³ / 452 cm²] at 170 °C (COK-021 ≤ 250 mL).
The two cutlets lie on the lower lift rack, which is lowered into the fat by its stub; fat ladled over the
tops twice; after 3 min the upper rack is hooked on, the pair lifted, drained 5 s, rolled 180° over the pan
and lowered (GA-36: only drips move); 3 min; lifted, drained, set on pan B on T0 at 80 °C (warm-hold, rack
keeps the crust off the base). Two batches for 4 persons; fried items finish last; the first batch waits
≤ 7 min (C1 A-4). Confidence M–H; untested: rack marks in the crumb.

### 3.5 Frikadellen (8 × 110 g)

Bread soaked in milk (box poured by roll, milk weighed by loss on the Z load cell), mince tipped from the
opened pack, egg from the bottom-strike cracker via the dark saucer (camera), 6 mm onion dice (3.2), mustard,
salt, pepper, chopped fresh parsley (GP-21, blade rotor on S): all in the bowl on T0; kneading roller on its
pins, T0 at 40 rpm for 90 s. Portions by the 60 mL disher, each weighed on the Z load cell (110 ±10 g), dropped
as balls into pan A on H1 and into the rondeau on H2 with 25 mL fat each; the presser flattens each to 22 mm
(**smash-forming**, the most traditional shape per C1 §5; no cylinders, C1 K1-7). Turned once by the turner
(slide under against the pan wall, lift 30 mm, roll 180°, 6 s each). Core probe 72 °C. About 30 events.

### 3.6 Mash

1 kg potatoes dunk-washed in the 6.5 L pot's basket on H2 (GP-W1: the arm plunges the basket 20 × 50 mm at
1.2 Hz, water to the dump slot, two baths, turbidity-terminated), halved in the nest, boiled 18 min in the
basket. Basket lifted, drained 20 s. The 3 L pot with 250 mL hot milk and 50 g butter stands on T0 under
the press stand with the ricer plate; potatoes tipped in from the basket in two loads, pressed at 1–2 kN
**with their skins**, which stay on the plate and go to the slot. Scraper on its pins, T0 at 30 rpm for 60 s,
nutmeg and salt by spoon. Riced texture (C1 K1-6). Confidence H.

### 3.7 Kneading and shaping dough

The box of flour comes through the port with its H stub; the sleeve takes it and pours by roll into the bowl
on T0, **weighed as loss on the Z load cell** (500 g ±10 g); water from the spout by flow meter; yeast, salt
by spoon; oil by ladle. Kneading roller and scraper on their pins, T0 at 80 rpm for 8 min (Ankarsrum
principle; 1.6 kg at 20 Nm). Proofing in the lidded bowl on T0 at 30 °C. Shaping: **pizza** — the dough
tipped onto the board, halved by the knife, each half weighed on the load cell by the tongs, laid into an
oiled GN 2/3 tray lying across T0 (stopped) and rolled with the rolling pin (coaxial with the roll, driven at
surface speed, 100–200 N) between 5 mm gauge bars, 5 min rest, rolled again (H); the tray leaves through the
port to the oven. **Rolls** — 60 g disher portions on a floured tray, rounded by shaking the tray (the
sleeve holds its stub and oscillates 3 Hz) (M). **Loaf** — into the loose-floor tin (K5). Sticky dough is
rolled under a folded silicone mat.

### 3.8 Pancake flip

Batter whisked in the jug on S (60 s). Pan A on H1 at 190 °C with 5 g fat; the ladle pours 100 mL at the
centre while **H1 spins at 120 rpm for 3 s**: the batter spreads evenly to Ø 220 (spin-spread, K2/K5; C1
K1-5). After 80 s a release check (5 mm jerk on the stub, camera). Pan B, preheated on H2 with 3 g fat, is
taken by its stub, rolled upside down, laid on A 8 mm off-centre and slid to engage the hook tab; the pair
is taken by its twin stub, lifted 40 mm, rolled 180° in 0.8 s over H1 and set down; pan A (now on top) is
lifted off and goes to H2 for the next round. 2.2 min and 3 events per pancake; ≤ 30 mL free fat (G-assembly
7.1 rules). Pancakes slide off onto a plate carrier on T0 at 70 °C. Confidence M (shared pan-pair result).

### 3.9 Draining pasta

Pasta boils in the basket of the 6.5 L pot on H1 (4 L water for 400 g, 3.5 kW; never more than 4 L, rule
N23). A ladle of pasta water is taken first. The basket is lifted by its stub, held 20 s, and tipped about
its lip into the sauce in the rondeau on H2 by the roll. The water stays in the pot and is poured into the
dump slot later: the pot's far rim rests on the slot edge while the roll lifts the near side (pour about the
lip, K3), so the roll carries < 5 Nm instead of the 9 Nm of a free pour. No hot water is carried over food.
Confidence H.

### 3.10 Carving a boneless roast

Roast rested 15 min, on the green board on T0; the comb fence (slots at 10 mm pitch) is set over its end by
the sleeve and locked on the board rim; the scalloped knife draw-cuts in each slot along the arm (radial
strokes of ±60 mm, 2 mm descent per stroke, 50–150 N); T0 turns the roast to present the grain at 90° to the
blade. Slices are lifted by the turner onto the plates. Firm roast H, braised meat M. Bone-in poultry as
parts (R-06, class b).

### 3.11 Plating 2–4 portions nicely

Warm plates (Ø ≤ 270) come through the port on carriers; one lies on T0, the next waits on the port drawer.
The recipe gives a layout (meat at 7 o'clock, starch at 12, vegetables at 3, sauce beside the meat, garnish
on top). **Polar placement**: T0 turns the plate so that each target lies on the arm's reach, the tool
always works on one line. Batch by tool, each tool fetched once for all plates: tongs for pieces and
vegetables; a Ø 80 ring set down, mash or rice from the disher pressed by the presser, ring lifted; the
ladle pours 50 mL of sauce as an arc while T0 turns; the spoon sprinkles herbs with a small radial dither.
The camera compares the plate with the layout; the spatula's edge wipes a rim splash. About 45 s per
plate, 2 plates in 1.5 min, 4 in 3 min (SRV-009: 3 min, met without margin). Components wait hot and
lidded on their positions; fried items are plated last. Confidence M (layout ±10 mm).

---

## 4. Benchmark check B1–B12

Events as in section 3, now including box doses by the hand, plating and the moves into the well, which
K1 did not count. "Before" is K1's own figure (§5). Times [E]; limits from PERF-001 as in K1 §5.
2p = the regular household (#18); 4p = the brief's size, B6 now at 4 persons (#19).

| # | Benchmark | Result K1 → K1b | Time 4p / limit (min) | Events 4p, K1 → K1b | Time 2p | Events 2p | What changed |
|---|---|---|---|---|---|---|---|
| B1 | Rouladen, Rotkohl, Salzkartoffeln | yes → yes | 148 / 183 | 280 → 105 | 135 | 78 | raft-secured rolls, flap rule, seared in two batches; cabbage quartered by the lever knife and shredded by the slicing disc on S; potatoes peeled on the spit (P1); plated |
| B2 | Schnitzel, Bratkartoffeln, Gurkensalat | yes → yes | 64 / 67.5 | 210 → 92 | 55 | 74 | potatoes boiled in the skin at t = 0, cooled in a cold bath in their basket, pared at 1 mm, sliced by the slicing disc; 180 mL fat, lift-rack turn, breaded ≤ 10 min before; cucumber striped on the spit. Tight at 4p: one retry costs the margin |
| B3 | Frikadellen, Püree, Erbsen-Möhren | yes → yes | 46 / 50 | 190 → 88 | 40 | 70 | mash riced in the skin; patties by disher and smash in two pans; carrots peeled (P1), diced through the 10 mm grid straight into the pot on H2 |
| B4 | Spaghetti Bolognese | yes → yes | 76 / 96 | 150 → 68 | 72 | 58 | mince seared first in the rondeau; celeriac pared in facets; garlic in the skin through the ricer; basket drain; pot poured about its lip |
| B5 | Pizza, 2 trays | yes → yes | 96 / 113 | 170 → 58 | 96 | 56 | flour by loss in weight on the Z load cell; kneading on T0; trays rolled across T0 and sent to the oven through the port |
| B6 | Gemüseeintopf (now 4 persons) | yes, no margin → yes | 50 / 60 | 170 → 66 | 44 | 57 | beans trimmed by one camera-indexed cut each (GP-102); leek cut, then dunk-washed (GP-W4); diced straight into the pot on H1; fresh parsley chopped on S |
| B7 | Steak, oven fries, mixed salad (2p brief) | yes → yes, basting adapted | 50 / 55 [E] | 150 (2p) → 95 | 42 / 44.5 | 80 | fries through the fry-cutter grid, tray to the oven via the port; pepper cored (GP-61); lettuce butt cut, dunk wash, spin basket on S; steak turned by the turner, core probe; butter ladled over (no pan tilt: class b) |
| B8 | Pfannkuchen, 8 | yes → yes | 44 / 50 | 190 → 50 | 30 (4 pcs) | 36 | spin-spread on H1, hooked pan pair, 3 events per pancake; batter on S |
| B9 | Chicken curry, rice | yes → yes | 38 / 56 | 140 → 60 | 34 | 52 | fresh pepper cored; ginger pared on the spit; lime on the citrus cone; rice rinsed in the spin basket |
| B10 | Lasagne, béchamel from scratch | yes → yes | 128 / 148 | 230 → 88 | 120 | 80 | béchamel on T0 under the whisk bar while the ragù turns on H1 under the scraper (no stirring visits); layers in the dish on H2 (cold); dish to the oven via the port; portions cut and plated |
| B11 | Rührkuchen, unmoulded | yes (if unmoulding) → yes | 98 / 125 | 110 → 55 | 98 | 55 | creamed by the whisk rotor in the jug; loose-floor loaf tin; release pulse on H2 after the oven; pushed off its floor on the nest: dome up |
| B12 | Scrambled eggs, toast (1 person) | yes → yes | 10 / 17 | 60 → 32 | — | — | eggs cracked over the dark saucer, beaten in the jug on S, scrambled in the saucepan on H1 under the scraper; toast in pan A on H2; 6 items, one well load |

**Twelve yes**, B7 with basting as a class (b) adaptation (K1 had it; the elbow arm cannot hold the pan
tilted and spoon at once). Mean events at the brief's person counts **175 → ≈ 71**, for the regular
2-person household **≈ 61**; full 4-person menus (B1, B2, B10) 88–105. Elapsed times rise by 0 to +4 min
against K1 (one hand instead of three), stay inside every limit; B2 at 4 persons is the tightest
(64 / 67.5).

---

## 5. Cleaning

### 5.1 Food-contact surfaces: all ware, washed in the well under the turret

Nothing fixed touches food. T0's and H1's carrier rings, the boards, the peeler post, the nests, the press
grids and pusher, and the roll sleeves are loose ware like the vessels and tools.

**Well programmes** (household-dishwasher wash parts, 30 L/min, 16 flat-fan nozzles in the long walls and
one rotary head in the floor; items hang on the two combs in validated patterns; 8 L tank at 60 °C; rinse
water from the 30 L store at 88 °C):

| Programme | When | Steps | Time | Water | Heat |
|---|---|---|---|---|---|
| Cold rinse | within 2 min of emptying a vessel (C2 R-7); the item then waits in the closed well | 10 s cold fan | — | 0.3 L | — |
| Standard load | after hand-over: ware, then dishes | cold pre-rinse 20 s; wash 60 °C alkaline 180 s; drain to tank; **rinse 3 L at 88 °C recirculated 60 s, coldest surface ≥ 82 °C for ≥ 40 s: A0 ≥ 90** (logger-validated, C2 R-3); dry 90 s with the lids lifted 30 mm into the downdraft | 6.5 min | 3.5 L | 0.27 kWh from the store |
| Turnaround | a class R item needed again for RTE work | as standard, 1–3 items | 6.5 min | 3.5 L | 0.27 kWh |
| Intensive | burnt-on soil, failed check, weekly | own 6 L fill, enzymatic, 50 °C, 15 min, then the standard rinse | 20 min | 9 L | 0.5 kWh |

Tank liquor is dumped daily and after any class R or allergen load (C2 R-7). The store is charged at 2 kW
only while hob and oven are off; during cooking the well draws only its pump.

**Throughput.** 2-person meal: two ware loads and one dish load, **20 min** after hand-over. 4-person menu:
three ware loads and two dish loads, **33 min** (PERF-005, everything clean within 90 min: met; K1: 3 h).
The cell itself is free for the next meal as soon as the clean set for it has been taken from the well.

**Verification (C2 R-11).** When the hand lifts an item out of the well it rolls it once in front of the
left-lobe camera (white, oblique and UV-A light) and an IR spot sensor (≥ 65 °C = dry steel); a failed
item goes to the intensive programme, then to a quarantine slot in the cabinet, and the human is told.
Weekly riboflavin self-test of one load and of the cell.

**Clean side.** Between meals the well is the closed clean store; at the start of a meal the hand takes out
everything the meal needs before any food is opened, so no clean item is taken out of a well that already
holds soiled ware (R-6 one-way in time). Items not needed stay and are washed again (no harm, no extra cycle).

### 5.2 The hand

| Part | Zone | Cleaned |
|---|---|---|
| Roll sleeve (H socket, PEEK bushes) | F-adjacent: it holds the tool stubs | two sleeves; swapped after class R work; both washed in the well after the meal; socket rinse at the dump slot (88 °C, 10 s, < 1 bar) after every soiled tool |
| Arm, tip can, reaction tab | S, above food during work | parks over the well; two fixed nozzles on the rear wall wash it after every cooked meal; welded, sloped 2° to the rod so that water runs back, not off the tip |
| Rod (wetted length) | S, inside the turret circle | scraper and flush ring of the collar at every retraction; lantern drained and watched |
| Seam (both walls) | S, inside the turret circle | air-swept outward whenever the cell is not washing; daily flush from both walls with softened 80 °C water and detergent while the disc turns 400°, then 5 s rinse and 15 min warm air; flow per jet ring logged |

### 5.3 Splash zone (Zone S)

| Surface | m² | Soiled by | Cleaned | Dries by |
|---|---|---|---|---|
| Deck: hob glass, well lids, dump slot surround, port drawer | 0.66 | drips, flour, boil-over | **after every cooked meal**: fixed nozzles, detergent, rinse; scraper-blade tool on the glass on camera alarm (burnt sugar, milk; C2 K1-12) | 2° fall to the dump slot; fan |
| End walls, rear wall and door, lower 300 mm | 1.0 | aerosol, splashes (low thanks to the downdraft) | after every cooked meal | fan |
| Upper walls, door, ceiling, cabinet face, dicer frame | 1.6 | steam | daily | heated ceiling, fan |
| Arm, rod, seam, collar | 0.3 | steam, splashes | 5.2 | air sweep |
| Dump slot, strainer, spindle pocket | 0.15 | waste, water | flushed after each use (0.5 L), daily | drains |
| **Total** | **≈ 3.7** (K1: 5.6) | | 1.8 m² per meal | |

**Nozzle plan.** Per meal: 8 flat-fan nozzles (5 along the rear wall at z 1150 aiming down and across the
lobes, 3 inside the door), 0.05 L/s each, 8 s detergent (60 °C, 2 g/L), 2 min dwell, 8 s fresh rinse at
65 °C: **6.4 L**; plus the arm nozzles 0.4 L. Daily in addition: two rotary heads in the lobe ceilings and the
upper rows 12 L, the seam flush 4.5 L (12 jets × 0.025 L/s × 15 s): **≈ 17 L**. After every meal the
downdraft fan dries the cell to RH < 65 % within 60 min (HYG-045, HYG-053); the ceiling is held 5 K above
the cell air. No manipulator-held lance (C5 A4). Riboflavin proof on a mock-up before selection: risk 1 and 8.

**Fat aerosol at the source.** Two downdraft slots along the end walls draw 300–400 m³/h at pan height; the
make-up air enters at the top centre through the seam (30 m³/h, H13-filtered) and a filtered ceiling
inlet. The airflow therefore runs from the turret outwards and downwards: the seam and the rod collar are
upstream of every pan.

### 5.4 Raw and ready-to-eat within one meal

* Order: dry, ready-to-eat, raw vegetable, raw animal food last (SM-208); where a recipe forbids it (B1
  starts with meat), RTE work follows a turnaround load.
* Unwashed produce is class R (C2 R-5): it is dunk-washed in the 6.5 L pot's basket (red use) before any
  tool touches it.
* Red instances: board, tongs jaws, one roll sleeve; everything else that touched class R goes to a
  turnaround load (A0 ≥ 60) before RTE use. The socket rinse after every soiled stub; the sleeve is swapped
  after the last raw step.
* Plates and dishes share the port drawer only in time: the drawer is rinsed by the per-meal nozzles after
  the dishes came back (R-6 in time).

### 5.5 Peelings, scraps, fat

Peel falls from the post into the dump slot; ricer mats and trimmings are knocked into it; the slot is
flushed after each job; solids stay on the 2 mm strainer and drop into the closed bio-bin drawer when the
strainer is tipped by the hand (C2 K1-10). Fat above 30 mL is poured into the saucepan, cooled on T0 and
tipped onto the peel in the bio bin; it never reaches the drain.

### 5.6 Crevices, seals and spray shadows, named

1. **Seam** (4 × 40 mm, 1.4 m): open, both walls jetted, air-swept; not above food; residual risk medium
   until the riboflavin rig (risk 1) passes; fallback drip ring.
2. **Rod collar**: scraper ring and lantern; LRU cartridge, yearly (R-12).
3. **Roll sleeve**: PEEK bushes on the can; the sleeve slides off (bayonet) and is washed as ware.
4. **Carrier rings and roller posts** of T0 and H1: rings are ware; posts stand in umbrella bosses, pinion
   in a thimble, no seal.
5. **Dicer grids and pusher, ricer plate**: blade roots and hole edges; ware, jets against the cutting
   direction, back-lit camera check after every use (PRP-035).
6. **Dicer frame pivots** on the stand: open pins, splash zone, washed daily in place and weekly in the well.
7. **Egg cracker pin, raft tines, mandrel slot, spin-basket mesh, peeler-post flexure**: one-piece or
   falling apart; ware.
8. **Well combs and lid pins**: two-point contact; lids lift off.
9. **Hob glass joints** (HYG-018 ruling, as all concepts), door gasket, port gasket, spout tips (rinsed by
   their own flow at the end of each fill).
10. **Arm tip** above food: welded, no seam, no seal; the reaction tab is a plate with R 3 edges.

### 5.7 Water and energy (2-person reference meal, including dishes)

| Item | Water | Energy |
|---|---|---|
| Well: 2 ware loads + 1 dish load × 3.5 L, 0.27 kWh | 10.5 L | 0.8 kWh |
| Tank: daily fill share, kept ≥ 60 °C | 4 L | 0.3 kWh |
| Per-meal hob-zone and arm wash | 7 L | 0.25 kWh |
| Daily cell and seam wash, share of two cooked meals | 8.5 L | 0.3 kWh |
| Produce washing (GP-W1 two baths), cooking water, socket rinses | 9 L | — |
| Cooking (hob; oven where used) | — | 1.3 kWh |
| Drives, fans, seam air, heated ceiling | — | 0.25 kWh |
| **Total** | **≈ 39 L** | **≈ 3.2 kWh** |

Against RES-005 (≤ 35 L, reported only, #23) and RES-001 (≤ 3.0 kWh): over by about 10 % and 7 %. K1 as
recomputed by C4: ≈ 103 L and ≈ 7.3 kWh. 4-person menu: ≈ 50 L, ≈ 3.9 kWh. Levers: final rinse kept as the
next pre-rinse (−3 L), per-meal wash only after frying or boil-over (−5 L on two meals in three).

---

## 6. Numbers before → after

### 6.1 Summary

| Quantity | K1 | K1b | Note |
|---|---|---|---|
| Wall width of the cell | 2270 mm with oven niche (1700 cell) | **1250 mm** | K1b includes the ware and dish washer; oven outside (oven column, as K8b) |
| Like-for-like (cell + washer + oven) | 2.9–3.2 m (C3 X3) | **≈ 1.85 m** (1250 + 600 oven column) | K6b 1.86 m, K8b 1.78 m |
| Height use | 0–850 services, 850–1400 cell, 1400–2000 drives | 0–400 tank and pumps, 400–850 well, 850–1500 cell, 1500–2200 drives | DEC-11 used; rod top ≤ 2100 |
| Hands | 3 turrets × 5 axes | **1 turret × 4 axes** (disc, Z, yaw, core) | |
| Motion actuators, stated | 17 (20 with dock, vibrator, oven door) | **7** | hand 4, T0, H1, spindle |
| C5-normalised | 17 | **7** | C5 limit ≤ 10: met |
| Dynamic seals in the splash zone | 13 (3 core seals, 4 collars, 6 V-rings) | **2** (rod collar, disc V-ring), both on the dry side of their gap, **none above food** | C5 limit ≤ 5: met |
| Rotating seam | 7.3 m over the whole deck | **1.4 m**, outside the projection of every open vessel | C2 R-2 met by geometry |
| Independent novel mechanisms (C5 S4) | 7 | **2**: the air-swept two-wall seam; the elbow rod with a canned roll coupling as the hand | C5 limit ≤ 2: met (6.2) |
| Distinct mechanism types (S3) | 10 | 7 | hand, turning position, spindle, lever press, well, dump slot with post, port drawer |
| Custom part types | ≈ 86 | **≈ 45** | |
| Loose food-contact items | ≈ 110 | **≈ 57** | |
| Tool changes per meal | 20–40 at 6–8 s, bayonet in soil | 12–20, stubs above drip collars, weighed by the Z load cell | |
| Handling events per meal | 110–280, mean 175 (C3: ≈ 190) | **mean ≈ 71; 2 persons ≈ 61; full menus 88–105** | includes box doses, plating, well loading |
| Skills (with vision on food) | ≈ 38 (12) | ≈ 26 (8) | |
| Cleaning stations (S10) | 6 (lance, gates, collars, seams, gutter, chamber) | **2** (well; fixed cell nozzles incl. seam and socket rinse) | |
| Zone S | 5.6 m², lance after every warm meal | 3.7 m², 1.8 m² per meal by fixed nozzles | |
| Coverage, C1 standard N, central | 225 as documented; 230 = 92.7 % with modules | **232 = 93.5 %** (range 230–233) | 6.3 |
| Benchmarks | 12 yes (none shown to work) | 12 yes, B7 basting class (b) | section 4 |
| Water, energy per 2-person meal incl. dishes | ≈ 103 L, ≈ 7.3 kWh (C4) | **≈ 39 L, ≈ 3.2 kWh** | 5.7 |
| All clean after hand-over | ≈ 3 h | **20 min (2 p), 33 min (4 p)** | |
| Transport moves per meal | ≈ 95 (C4) | ≈ 25 (boxes, oven trays, plates, dishes) | ware stays in the cell |
| Cell peak power | 11.8 kW (C4) | ≈ 6.8 kW: hob managed to 5.6 kW on two phases (H1 3.5 + T0/H2 2.1), drives 0.5, spindle 0.75; well heating 0 W during cooking | C4 R-8 |
| Heaviest LRU | turret cassette 30–40 kg at 1.4–2 m | rod with arm 6 kg, lowered into the cell; motors ≤ 3 kg | |
| Unplanned part exchanges per year (C3 X10 model) | ≈ 3.6 (MTBF ≈ 3 months) | ≈ 0.7: 7 axes × 3 % + 2 seals × 25 % (MTBF ≈ 17 months) [E] | |
| Parts cost, single unit | 27.5 k€ stated; 40–45 k€ (C3), 32 k€ comparable (C4) | **≈ 12.3 k€ ± 30 %**, machine part ≈ 10.3 k€ | 6.4 |

### 6.2 The C5 hard limits

* **Actuators ≤ 10:** 7. **Dynamic seals ≤ 5:** 2.
* **Novel mechanisms ≤ 2:** two. (1) The open seam with two-wall flush and air sweep — inherited from K1 and
  still unproven, but now outside the food projection, so a failure costs cleaning effort, not food
  safety; rig risk 1. (2) The elbow rod as a hand with a canned roll coupling — the parts are known (four-
  point slewing ring, rod collar, magnetic couplings of mixers and mag-drive pumps), their combination as a
  robot wrist is new; rigs risks 2 and 3. Not counted, by C5's own S-min convention: the turning carrier
  ring and the canned spindle (shared with K6b, K8b), the pan pair, the raft, the egg cracker (shared
  modules), and the lever press (a catering product used with the force a cook uses; rig risk 4).
* **Events ≤ 70:** met for the regular 2-person household (mean 61) and for eight of twelve benchmarks; not
  for full 4-person menus (88–105). Argument as K6b: every event is a form-fit stub-and-bayonet grip above a
  drip collar with a weight check by the Z load cell and a camera after release, the case C3 X4 rates at
  10⁻⁵–10⁻⁴ unrecovered after one retry; at 100 events that is inside REL-001's handling half. 4-person
  meals are occasional (#18). Rig risk 7 decides it.

C5 simplicity score recomputed with C5's formula and anchors [C]: S1 10, S2 7.0, S3 7.8, S4 6.1, S5 6.8,
S6 7.4 (B3 chain: hand, T0, H1, press, spindle, well), S7 5.5, S8 5.9, S9 5.5 (10 crevice types), S10 7.0,
S11 5.2, S12 5.2, S13 6 → **≈ 6.8** (K1 3.1; C5's reference S-min 7.1).

### 6.3 Coverage (C1 standard N)

Start: C1's 230 meals for K1 with the hostable modules (C1 §2.3). K1b keeps every K1 tool that carried a
meal (knife, tongs, spit, turner, mandrel, probe, corers) and adds the stations C1 ranks highest (press with
ricer, turning positions, spindle, G-produce set, GA-20, GA-36). With #25's generic peeling it recovers
**CK16 banana bread** (banana riced in the skin) and **MX06 guacamole** (cut round the stone, twist, rice):
**232 = 93.5 %**. Low end 230 if these two fail their bench test; high end 233 if DM12 Kohlrouladen works
(GP-71 freeze–thaw head, leaves lifted by the tongs). Still out: the 8 exclusions of 5.4; IT17, DM33,
CK12, CK17 (no ready dough, no pastry line); AS08, AS09, IN07 (folded wrappers). Designer class (c) about 9
(basting by ladle, citrus as rounds, Spätzle as pressed strands, round cakes in a loose-floor tin), inside
MEAL-019's 24. Nothing is lost by going from three hands to one: no K1 benchmark step needed two hands
on one workpiece that a fixture (stab nest, peeler post, comb fence, fulcrum eye, cradle) cannot replace.

### 6.4 Cost, honestly (#22 report, #28 target)

| Block | k€ | Of which household appliance or bought module |
|---|---|---|
| Hob: three OEM induction modules under glass (DEC-5) | 0.6 | yes |
| Downdraft extractor fan with baffle filter | 0.4 | yes |
| Hot-water store 30 L | 0.2 | yes |
| Wash parts of a household dishwasher (pump, heater, filter, softener, dosing) | 0.3 | yes, replaces the €500 dishwasher of #28 |
| Catering lever push-dicer with blade sets | 0.45 | yes |
| **Appliances and bought modules** | **1.95** | |
| Turret: slewing ring 0.35, disc, coaming and seam jets 0.35, rod-and-arm body with belt and two canned couplings 0.7, Z axis with load cell 0.35, four drives 0.9, collar cartridge 0.15, frame and drawer rails 0.2 | 3.0 | |
| Turning drives T0, H1 (canned pinions, carrier rings, rollers); spindle with thimble | 0.7 | |
| Stainless cell, door, well, drive room, dump slot, cabinet, port frame (job shop, #21) | 2.6 | |
| Nozzles, valves, pumps, filters, seam-air fan, ceiling heater | 0.5 | |
| Controls (7 drives, controller, safety chain, 3 cameras, lights, IR sensor) | 1.1 | |
| Ware ≈ 57 items (bought pots and pans 0.5; welded stubs and collars 0.5; custom tools, fixtures, sleeves 1.4) | 2.4 | |
| **Machine part** | **10.3** | #28 target ≈ 2 k€: missed by about 5 × |
| **Total** (oven excluded: appliance in the oven column, #28 €500) | **≈ 12.3** | K1: 27.5 stated, 32–45 re-estimated |

The machine part is dominated by stainless work, the turret and the ware. Design-to-cost levers for the
rounds after K9b: a bought deep-drawn sink or dishwasher tub as the well (−0.4 k€), steppers instead of
servos for Z and yaw (−0.3 k€), bought cookware with clamp-on stubs instead of welded ones (−0.4 k€), series
prices (−30 %). A loose-ware cell with one hand and about 55 items will not reach €2 k.

---

## 7. Self-assessment

Before: the critics' scores (C3 and C4 as adjusted in 04-decision-matrix §2.2). After: my estimate, to be
re-scored by the critics.

| Criterion (weight) | K1 | K1b [E] | Why |
|---|---|---|---|
| Simplicity (30 %) | 3.1 | **6.8** | 7 actuators, 2 seals, 2 novel, ≈ 71 events, ≈ 57 items, 2 cleaning stations (6.2) |
| Hygiene (25 %) | 3 | **6.5** | the fatal finding removed by geometry (nothing above food but the closed arm and the tool); no bore, no tip seal; every drive into the food zone canned; all ware washed with logged A0 ≥ 90; hob zone washed and dried per meal; still: an open seam to prove, an arm above the pans, glass joints |
| Coverage and food (20 %) | 7 | **7.5** | 232 meals; the C1 food defects of K1 fixed (raft, fat, cooled potatoes, ricer, smash patties, spin-spread); one serial hand makes B2 at 4 persons tight; basting adapted |
| Mechanics and reliability (15 %) | 3.5 | **6** | one 4-axis hand with torque-limited couplings; force jobs in closed loops (lever press, turning rings); light LRUs; MTBF ≈ 17 months; still: two novel parts, tied tool heading, 88–105 events in 4-person menus |
| System fit (10 %) | 2.5 | **6** | 1250 mm with washer; 39 L, 3.2 kWh; clean in 20–33 min; 25 transport moves; 6.8 kW peak; still: needs an oven column fed by the transport, and a port that carries boxes, plates, trays and dishes |
| **Weighted** | **3.85** | **≈ 6.6** | P4 leaders before round 2: K6 5.74, K8 5.68 |

**Remaining weaknesses, in order.**

1. **The seam is still a gap** that must pass a riboflavin test; it is no longer above food, but a failed
   flush means the well lid and the arm collect what the seam sheds (risk 1; fallback drip ring).
2. **One serial hand.** Four-component menus for four persons run within 4–30 min of their limits; a retry
   in B2 at 4 persons uses the margin.
3. **Tied tool heading.** The elbow arm cannot turn a tool about its own vertical axis at a fixed point;
   the turntables, the fixtures and the two elbow solutions cover every benchmark step, but untested
   corners may need K1b-2D (risk 6).
4. **Reach is a ring, not a disc**: nothing within 185 mm of the turret axis is reachable, which is why the
   well's combs sit at its edges and the well's centre holds only hanging bodies.
5. **The arm sweeps above open pans** (closed, welded, Zone S): condensate and splashes on its underside are
   washed per meal; whether they drip during long simmering is risk 9.
6. **Oven outside**: oven meals add 4–6 transport moves and depend on an oven column that other modules
   own (shared with K8b).
7. Cost ≈ 5 × the #28 target.

---

## 8. Best ideas for the combined machine (K9b)

1. **The elbow turret as the hand.** One rotating ceiling disc (Ø 420) and one plain rod with a welded
   elbow arm give a 4-axis SCARA whose drives all sit in a dry room above, with one round rod collar and one
   seam as the only moving penetrations — no slot, no sealing band, no bellows. Placed in the middle of a
   1.2 m cell it reaches two station lobes; idle, it folds over the wash well, and the open cell has no
   moving part (K1's best safety case kept). An alternative carrier for K9b's station list next to K6b's
   gantry: 4 instead of 5 axes, 2 instead of 5 seals.
2. **Canned magnet roll coupling at the arm tip.** A torque-limited, seal-free horizontal roll axis (10 Nm
   rated) for pour, flip, pan pair, lift rack, raft, spit and pincer tongs; the only ware part is a welded
   magnet sleeve on PEEK bushes. It would also remove the roll lip seal of a gantry wrist.
3. **"Beside, never under" as a layout rule**: the part of a cell that lies under a manipulator's own
   penetrations (seam, collar, band) is the wash well or the waste slot, never a food position. It turns
   C2 R-2 from a sealing problem into a drawing rule.
4. **A bought catering lever push-dicer worked by the hand**: about 2 kN from 300 N of Z force, grids,
   wedger, fry cutter and a custom ricer plate in one frame, force loop closed in the frame, cutting straight
   into the pot; no actuator, no seal, a product precedent.
5. **Load cell under the Z carriage**: every grip weighed, doses as loss in weight from a held box or cup,
   dropped or missed tools detected — the K2 load pin moved into the dry drive room.

---

## 9. Risks, cheapest kill experiments, open questions

### 9.1 Risks

| # | Risk | Consequence | Cheapest experiment | Kill criterion |
|---|---|---|---|---|
| 1 | The two-wall seam flush leaves soil or drips late | daily cleaning effort; drips onto the well lid and the parked arm | Ø 450 laser-cut disc on a lazy-Susan bearing in an acrylic coaming, 8 + 4 jets, garden pump with a softener cartridge, fan; flour paste and oil aerosol, dried 2 h; flush; riboflavin under UV. 3 days, < €500 | fluorescence on either wall after the standard flush, or a drop later than 10 min → fit the drip ring |
| 2 | The canned roll coupling slips under real loads, or its sleeve bush holds soil | pour, flip and tongs unreliable; hygiene of the sleeve | bought magnetic coupling of the 10 Nm class with a turned sleeve on PEEK bushes; 10 000 roll cycles under 6 Nm with starch water; then dishwasher and ATP swab. 1 week, ≈ €600 | rated torque < 8 Nm at 2.5 mm gap, bush seizing, or ATP fail |
| 3 | Elbow rod too soft for cutting and pressing | ragged cuts, press lever missed | Ø 50 × 5 tube with a welded 80 × 60 box arm clamped in a drill-press stand: sag and chatter under 300 N; draw cuts through potatoes and a roast. 1 day, ≈ €200 | sag > 2.5 mm or visible chatter marks |
| 4 | The lever push-dicer needs more than 300 N at the pad | dicing falls back to knife work (slow) | buy one catering lever dicer; load the lever pad with a force gauge; potato halves, onion halves, carrot, mozzarella cold; ricer plate with boiled potatoes. 1 day, ≈ €450 | > 300 N for 10 mm potato halves or > 10 % broken dice |
| 5 | Mandrel slips on a wet slice; rolls open (shared) | Rouladen (brief meal) | by hand: slotted Ø 12 rod, 8 slices with flap rule, raft, sear, 100 min braise (G-assembly 4.2 A/B/C). 1 day, €40 | > 1 of 8 slips or opens with the raft |
| 6 | The tied tool heading blocks steps | slower meals or option K1b-2D (+1 axis, +0.9 m seam) | kinematic script of the 2-link arm with the real station positions; run the B1–B3, B7, B10 step lists; count steps that need a heading the arm cannot give. 3 days | > 5 % of steps need a third planar axis |
| 7 | H-stub bayonet fails in soil | stops at 70–105 events per meal | sleeve socket and stub on a pick-and-place rig, drip collar fitted, stub smeared with flour paste, mince, dried starch; 10 000 cycles with Z load-cell check. 3 days, ≈ €300 | > 1 unrecovered failure per 10 000 |
| 8 | Well capacity and A0 for the K1b load patterns | slower turnaround; disinfection claim | mock well 380 × 300 × 450 with a household-dishwasher pump set; hang B1 4p ware; loggers on the coldest item. 2 days, ≈ €300 | > 5 loads for a 4-person menu, or A0 < 60 |
| 9 | Condensate drips from the arm into simmering pots | quality, hygiene | sear 4 steaks and simmer a stew under a steel box held 300 mm above, with and without downdraft; collect drops. 1 day | any drop from the arm with the downdraft running |
| 10 | Layout does not close (port drawer, press stand, tray across T0, cabinet reach) | width grows by 100–200 mm | CAD of the cell with real appliance and dicer dimensions. 2 days | any station outside the 185–535 mm reach or under the turret circle |

### 9.2 Open questions

1. **Oven column fed by the transport** (as K8b) or an oven at the cell's end with its own loader:
   architecture decision for K9b (C4 R-7).
2. **Ruling on C2 R-2**: two dynamic seals and a seam that are inside the turret circle and never above an
   open vessel — compliant, as argued here?
3. **Box standard**: a moulded H stub on one short end of the GN 1/6 and 1/3 boxes, delivered opened.
4. **One washer for ware and dishes** (C5 Q1) in the cell's well, with dishes returned through the port.
5. **One serial hand** for 4-person menus at the PERF limit (C5 Q2).
6. The well as the **closed clean store** between meals (C2 R-6, one-way in time).
7. HYG-018 ruling for the glass-ceramic hob in Zone S (all concepts).
8. Whether basting by ladle (B7) is accepted as class (b).

