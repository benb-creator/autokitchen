# P1 ideas E — Cleaning first: design the wash, then fit the cooking into it

Round P1 (idea finding) for meal preparation, written from one lens only: **start from what a machine
can wash trivially and verifiably, and allow only preparation mechanisms that fit that wash.**
Written independently; no other file in `design/prep/ideas/` was read.

Inputs used: `BRIEF.md`, `DECISIONS.md`, `PLAN.md`, `requirements/requirements.md` (3.5, 5, 7),
`research/06` (all), `research/04`, `research/01` (3–5), `research/05` (4–5).
`research/02-meal-corpus.md` did not exist yet; the operation list of requirements 5.3 was used instead.

All numbers are my own estimates or derivations unless a research document is cited. They are design
starting points, to be measured on a prototype.

---

## 0. The lens: twelve rules that come before any mechanism

A preparation mechanism is only admitted if it obeys these rules. They are stricter than the checklist in
`research/06` section 11, on purpose.

| # | Rule | Why (cleaning argument) |
|---|------|-------------------------|
| C1 | Food touches only (a) loose passive ware, (b) a tool that has its own form-fitting wash holster, or (c) a surface that is thrown away. **Never a fixed machine surface.** | A fixed food-contact station (HYG-033) is the thing nobody has cleaned automatically (`research/01` 4.3). |
| C2 | Allowed shapes for Zone F: body of revolution, straight open tube, flat plate, single-curvature bent sheet, solid rod. Each part is **one piece or fully welded**, internal radii ≥ 6 mm (tools ≥ 3 mm). No hinge, spring, thread, hollow closed volume, O-ring groove or press-fit in Zone F. | If a part can be described as "a lathe part, a bent sheet or a laser-cut plate", a spray or a pipe flow reaches all of it. |
| C3 | Relative motion between food-contact parts only as **loose-fit pairs that fall apart for washing** (piston in tube, blade past plate, bowl under scraper). Never an assembled joint. | Joints are where Thermomix, grinders and slicers keep their dirt. |
| C4 | Every Zone F part has **one named wash pose at one fixed place**. The wash load pattern is fixed, not random, and is validated once with riboflavin (HYG-019). | Household dishwashers fail by random loading; ours is never loaded randomly. |
| C5 | Steel first: ware is 1.4404/1.4301, thin-walled, smooth (2B or electropolished). Polymers only as one-piece pistons, lips, boards and mats, blue, listed as wear parts. | Steel survives 85 °C and pH 12, dries by its own stored heat, and is easy to inspect by camera. |
| C6 | Motion enters the food zone only by: gripping a clean stem **above a drip collar**; pushing a loose piston from its dry side; a magnetic coupling; or spinning/tilting the whole vessel. | No shaft seal in Zone F (HYG-016). |
| C7 | **Confine the soil at the source**: operations happen inside the ware (lidded tray, tube, bowl), so the bay itself only sees traces. State the soiled m² per meal (HYG-002). | What is not soiled need not be cleaned. |
| C8 | Cold pre-rinse ≤ 2 min after use ("wet parking" in the holster or the washer). Never a hot first rinse. | Dried egg and starch are the hard soils (`research/06` 3). |
| C9 | Sequence inside a meal: **dry before wet, RTE before raw, allergen-free before allergen, raw animal food last.** Two ware sets, marked green (RTE) and red (class R). | Removes most mid-meal washes (FSF-040, PRP-032). |
| C10 | No closed food lines except drinking water. Every other liquid is poured from its own box or bottle. | Nothing to CIP, no dead legs. |
| C11 | Geometry is chosen so that **one camera view sees the whole food-contact surface** (tube bore, open tray, flat blade), and wash loops are small (1–3 L) so that turbidity and conductivity of the last rinse are sensitive. | Verification (HYG-026) is designed in, not added. |
| C12 | Everything that touched class R food gets A0 ≥ 60 before its next use; everything is dry before it is stored (HYG-021, HYG-024). | — |

Four different answers to "what is trivially cleanable?" give the four concepts below:

| Concept | Answer | One-line description |
|---------|--------|----------------------|
| A Spülzelle | Do not move the dirt: **the prep cell is a dishwasher** | Preparation inside a dishwasher tub; tools hang in it and are washed in place |
| B Alles ist Geschirr | Make **everything a dish** and wash it in 3 minutes | All-steel loose ware, a commercial-type 3-minute washer as the heartbeat |
| C Kolbenrohr | Make **everything a pipe** | Open tube + loose piston as the universal vessel; extrude, slice, knead, dose; clean by pigging and pipe flow |
| D Zwei-Bahnen-Küche | **Throw the surface away** | Food sandwiched between two paper webs; tools never touch food |

Shared by all four (not repeated each time):

* **The box is the doser.** Nothing fixed touches stored food. The box docks at a port, is tilted about its pour
  edge with a vibrator, and the receiving vessel stands on a load cell (two ranges, 200 g and 10 kg, per
  `research/04` 9.2). Pieces are picked with tongs.
* **Pasta draining** is a cooking-side operation in all concepts: perforated steel insert basket, lifted by its
  rim handles, held 20 s over the pot, tipped. No hot water is ever poured.
* **Spike lathe** (sub-idea S3) is the common peeler for round produce.
* Cooking vessels and hob/oven belong to D5; I only state how stirring and flipping are done with each concept's tools.

---

## 1. Concept A — "Spülzelle": the preparation cell is a dishwasher

### 1.1 Core idea

Preparation takes place inside a real dishwasher tub (stainless, coved, sump, spray arms, heater, filter).
All tools hang inside on cone pegs at fixed places and are never taken out; after the work the door closes and
the tub washes itself and everything in it with a normal dishwasher programme. Motors stay outside: motion
enters through two "ball ports" (a polished rod through a sealed ball, as on hot-cell manipulators), a
magnetically driven floor turntable and one magnetically coupled high-speed spindle.

### 1.2 Sketch

```
Front view, one tub (interior 560 W x 480 D x 560 H, ~150 L, = tub of a 60 cm dishwasher)

        box dock + tilter (dry)          drive deck (dry, Zone N): 2 gimbal drives
   ________[shutter]_______________________________________________
  |  \  port chute            (ball port R1)   (ball port R2)     |  <- 45 deg chamfer faces,
  |   \                          \O/               \O/            |     ports are NOT above the
  |  upper spray arm  ============\================/==========    |     work area
  |                                \  rod Ø28     /               |
  | tool pegs (left wall)           \            /   tool pegs    |
  |  knife  peeler  tongs            \          /    whisk roller |
  |  turner scraper egg-cup           \        /     hook  spike  |
  |                               [tool]    [tool]                |--> side hatch 330 x 200
  |          board (GN 1/2)        ___________         jet gate   |    (exchange tray GN 1/2
  |  _____________________________|  bowl 4 L |__   6 fan jets    |     in / out by transport)
  |  floor, 5 deg to sump  ((( turntable Ø260, magnetic )))       |
  |__________________ lower spray arm ____________________________|
        | sump 6 L, heater 2 kW, drum strainer -> bio bin |
        | circulation pump 60 L/min, drain pump, 5 bar jet pump |

Duplex option: two tubs stacked (upper "green" 950-1550 mm, lower "red" 250-850 mm), 600 W x 600 D column.
```

### 1.3 Kinematics and actuators

* **Ball port**: ball Ø100, 1.4404, polished, in a PEEK seat ring with EPDM energiser (seat is changed from the
  dry side). Rod Ø28 × 1.5 tube, closed end, slides and turns in a lip wiper in the ball. Tilt ±35° in two
  axes, stroke 450 mm, continuous spin; a coaxial push rod behind a diaphragm at the tip opens tongs.
  Reach at 450 mm depth: a circle of radius 315 mm, which covers the tub. Tip deflection at 50 N side load,
  500 mm out: about 0.5 mm. Tip resolution about 0.4 mm. 5 actuators per rod, all dry.
* Turntable: 0–300 rpm, 8 Nm through a 1 mm floor window with a Ø150 SmCo face coupling (about 10 Nm).
* High-speed spindle in the rear wall: 500 W, to 10,000 rpm, through a PEEK window Ø90 (no eddy-current
  heating), 1.5 Nm, for the chopper cup and the salad-spin basket.
* Count, single tub: 2 × 5 (rods) + turntable + spindle + hatch + shutter + box tilt and vibrator (2) +
  drum strainer = **17 motion actuators**, plus 3 pumps and a fan. Duplex: about 32.

### 1.4 Tools and vessels (all stay in the tub)

Rod tools with a taper-bayonet stem: chef's blade 200 mm (standard blade, welded stem), Y-peeler head (standard
blade), tongs, egg cup-tongs, turner, steel scraper, whisk, dough hook, free roller Ø50 × 250, spike chuck and
tailstock cup. Ware: 4 L bowl, perforated basket, chopper cup with blade lid, GN 1/2 HDPE board, silicone mat
with a steel pull bar, 2 exchange trays. About 18 items, about 0.6 m² of surface.

### 1.5 Dosing and moving, by ingredient form

| Form | How |
|------|-----|
| Whole produce | Box docks at the port; tongs on rod R1 pick pieces through the port (exact count), camera above the port |
| Leafy | Tongs pick by the handful into the basket on the turntable; weight by turntable load cell |
| Granular | Box tilted at the port, falls down the port chute into the bowl on the turntable (load cell under the turntable drive, outside) |
| Powder | As granular, **only while the tub is dry** (rule C9), shutter closed immediately; flour dust stays in the tub and is washed away |
| Liquid | Water by valve through a ceiling nozzle; other liquids poured from their bottle/box at the port |
| Paste | Piston box (S10) pushed at the port, strand cut by the scraper |
| Raw meat | Pack opened outside; piece slides down the port chute onto the board; tongs handle it |
| Egg | Tongs take the egg from the box insert at the port |
| Frozen | IQF as granular; blocks go directly to the pot, not into the tub |
| Out | Finished component is scraped or tipped into the exchange tray, which leaves through the side hatch to the hob |

### 1.6 The hard operations

| Operation | How it is done in A | Numbers | Confidence |
|-----------|--------------------|---------|------------|
| Peel potato / carrot | Spike lathe: piece between turntable spike and tailstock cup on R2; R1 holds a floating Y-peeler blade at 3–5 N, travels pole to pole under a water film; peel falls to the floor and is flushed to the strainer | 120 rpm, 8–12 s per potato, 1.5 kg in about 4 min | Medium–high (consumer lathe peelers do this) |
| Peel onion | On the lathe: knife tops and tails, scores one meridian 2 mm deep; tub spins the onion at 300 rpm against a tangential 5 bar fan jet that strips skin and first layer | 15 s per onion | Low–medium, must be tested |
| Dice onion | Lathe dicing (S3): 24 meridian cuts with the blade (index 15°), then slices across the axis; pieces drop into the bowl | ≤ 70 N per cut, about 60 s per onion | Medium |
| Mince herbs | Chopper cup on the high-speed spindle, 3 pulses | 5 s | High |
| Crack egg | Egg held in the two-half egg cup-tongs, tapped on a fixed steel edge over a saucer (0.1 J), halves opened by the push rod; camera checks the saucer before it is tipped into the bowl | 10 s per egg | Medium |
| Form Frikadellen | Mass mixed in the bowl by hook against turntable; R1 presses a ring (Ø80) into the mass spread on the board by the roller, turner lifts the pucks | ±10 % | Medium |
| Rouladen | Slice on the silicone mat on the board; mustard strand from a piston box, spread by the scraper; filling placed by tongs; R1 hooks the mat's pull bar and draws it over (sushi-mat roll); R2 pushes a steel Rouladen needle through with tongs | 15–20 N for the needle, about 90 s per roll | Low–medium |
| Bread a Schnitzel | Three shallow zones on a divided tray; tongs dip and turn; turner presses crumbs at 20–50 N | 40 s per cutlet | Medium |
| Knead, roll out | Hook on R1 (spin 20 Nm is too much for the rod: the **turntable turns the bowl**, the hook is only held, Ankarsrum principle); roll out on the mat with the free roller between two 4 mm rails | 1 kg dough, 8 Nm, 8 min | Medium |
| Mash | Not in the tub; ricer at the cooking side | — | — |
| Toss salad | Basket on the high-speed spindle washes and spins (600 rpm, 40 g); dressing and toss in the bowl on the turntable with a fixed scraper | 2 × 15 s spin | High |
| Flip steak / pancake | Cooking side; same rod idea can serve a "hot tub" with induction under a glass-ceramic floor, where frying splatter is simply washed away | — | Option |

### 1.7 Cleaning and drying

* **What gets wet:** the whole tub interior (1.7 m²) and all tools in it (0.6 m²), every time.
* **Quick rinse between steps** (green to red): the rod carries each used tool through the **jet gate**
  (S5), a plane of 6 fan nozzles at 5 bar, 12 L/min from the sump, turning the tool as it passes. 20 s per
  tool, 3 L of cold water in total, to drain. The manipulator is its own dish rack, so there is no shadow.
* **Full wash after the meal:** programme P1 of `research/06` with the two spray arms plus the jet gate; the
  rods are stroked fully in and out through their wipers and the balls tilted to their limits so that the
  whole rod and ball surface is presented; the turntable lifts 40 mm on its pivot and spins. 17 L, about
  1.3 kWh, 45–55 min including drying.
* **Drying:** final rinse at 80 °C; 25 kg of tub steel stores about 560 kJ, enough to evaporate 230 g; the
  film is about 70 g. A 100 m³/h vent fan for 10 min, then the door is parked ajar.
* **Waste:** peel, shell and trimmings go to the floor, are flushed to a drum strainer (2 mm) that rotates
  180° and is back-flushed into the bio-waste bin. No macerator.
* **Verification:** L1 process data; turbidity and conductivity of the last fresh rinse; a camera behind a
  heated window with white and UV-A light compares the parked tools with reference images; the fixed load
  pattern is riboflavin-validated once and re-checked by the vitamin-B2 self-test (S13).

### 1.8 Off-the-shelf / custom / novel

Off-the-shelf: tub, sump, pumps, heater, filter, spray arms, door seal from a 60 cm dishwasher; 5 bar
diaphragm pump; blades; SmCo magnets. Custom: ball ports and gimbal drives, tool set with stems, turntable,
drum strainer. **Novel:** preparation inside a dishwasher tub with a fixed, validated load; ball-port rod
manipulator with all drives dry; manipulator-as-rack jet gate.

### 1.9 Biggest weakness

The whole 2.3 m² gets dirty and wet for every meal, even for one chopped onion, and then the cell is blocked
for 50 minutes; mid-meal raw/RTE separation needs either the duplex (32 actuators) or strict sequencing.
The ball seat and rod wiper are dynamic seals in the food zone, which rule C6 only tolerates because they are
washed in place and replaceable. Dexterity through a polar rod is poor for flat work (Rouladen, breading).

---

## 2. Concept B — "Alles ist Geschirr": every food-contact part is a dish, washed in 3 minutes

### 2.1 Core idea

Nothing that touches food is attached to the machine: work surfaces are GN 1/2 steel trays, tools are plain
steel parts on a stem, mechanisms are passive cassettes. A small commercial-type washer (tank at 60 °C, fresh
rinse at 85 °C, 2–3 minute cycle, possible because 11 kW is available, DECISIONS #1) sits at the end of the
bay, so the machine washes as it goes, like a cook, instead of stockpiling dirty ware for an hour-long
programme. All ware is steel, so it leaves the washer at 75 °C and dries by its own heat in about a minute.

### 2.2 Sketch

```
Front view, bay 900 W x 600 D x 750 H (at 850-1600 mm above floor)

  dry slot, rear wall: X-Z rails behind a labyrinth; arm = closed steel tube (Zone S)
  ======================= X 800 ==================================
        | Z 450          wrist: tilt + spin, stem chuck
        |  ___
        | (___)  <- clean knob, gripped
        | /_____\ <- drip collar Ø70 (S1)
        |    |
        |  [tool]                            power wall (flat, IP69K):
   box  |                                     (o) low-speed dog 20 Nm
   dock |   bench 1      bench 2     bench 3  (o) high-speed magnet 500 W      washer
  [tilt]|   GREEN        RED         WEIGH     |  ram 2 kN from above          380x380x350
        |  [GN1/2-65]  [GN1/2-65]  [GN1/2-65]  v                             | dirty | clean |
  ______|__on frames with load cells and vibrators________________________   | door  | door  |
   floor 5 deg to drain, nozzle bar for the daily bay rinse                  tank 12 L 60 C
                                                                             boiler 6 kW, 85 C rinse
  clean-ware store (dry, behind the clean door): second set of everything
```

### 2.3 Kinematics and actuators

Gantry X 800, Y 350, Z 450 plus wrist tilt (±180°, 3 kg at 150 mm, 5 Nm) and wrist spin (0–300 rpm, 10 Nm)
and one stem chuck: 6 axes. Low-speed dog drive, high-speed drive, press ram (2 kN, 150 mm), two bench
vibrators, box tilt and vibrator, two washer doors and a rack shuttle. **About 17 actuators.** Heavy work
(knead 20 Nm, press 2 kN) is taken by the wall drives and the ram, not by the gantry.

### 2.4 Tools and vessels

* **Benches:** GN 1/2-65 steel trays (325 × 265 mm), 6 off; perforated GN 1/2-65, 2 off; flat GN 1/2 lids, 4;
  GN 1/2 HDPE cutting board; GN 1/2 silicone mat. The tray is work surface, splash guard and transfer vessel in one.
  Loose steel rail bars (3, 5, 8, 22 mm) laid in a tray turn it into a **thickness gauge** for the roller.
* **Stem tools** (S1), each a welded steel part with drip collar and knob: chef's blade, Y-peeler, tongs
  (spring-free: two leaf blades closed by the chuck's second jaw), turner 0.6 mm, scraper, roller, whisk, ring
  cutter Ø80, brush-free steel squeegee, spike. 14 off, in duplicate (green/red).
* **Cassettes** (passive, fall apart into C2 shapes): rotating bowl 4 L with a hang-in roller and scraper
  (Ankarsrum principle, no seal); chopper cup with magnet-driven blade lid; ricer cylinder with plate; push-through
  grid on the ram; egg cracker (one ram stroke via a cam: score, spread); apron roller for Rouladen (S11).
* About 45 items in total, two sets.

### 2.5 Dosing and moving, by ingredient form

| Form | How |
|------|-----|
| Whole produce | Box tilted at the dock onto the perforated tray on bench 3 (counts by camera, mass by load cell); surplus pieces picked back with tongs |
| Leafy | Tongs from the box into the perforated tray; washed under the water nozzle, tray spun on the low-speed dog with a lid (S14) |
| Granular | Tilt-pour with vibration into a tray or bowl on bench 3, closed loop on weight |
| Powder | Same, through the box's sifter lid, into a **lidded** tray through a slot in the lid (dust stays in the tray) |
| Liquid | Water valve over bench 3; other liquids poured from the box/bottle |
| Paste | Piston box (S10) on the ram, strand cut by a wire bar |
| Raw meat | Pack emptied onto the red tray; handled by red tongs or the freeze plate (S6) |
| Egg | Tongs place the egg in the cracker cassette |
| Frozen | IQF as granular |
| Vessel to vessel and to the pot | Tray tipped by the wrist over its corner spout with the squeegee following (residue ≤ 1 %); or **hourglass** (S4): the pot's rim adapter is set on the tray, both inverted together |

### 2.6 The hard operations

| Operation | How it is done in B | Numbers | Confidence |
|-----------|--------------------|---------|------------|
| Peel potato / carrot | Spike lathe cassette on the low-speed dog over bench 1; Y-peeler stem held by the gantry with a 4 N spring compliance; carrots through the flexure-iris peeler (S9) on the ram | 10 s per potato | Medium–high |
| Peel onion | Top, tail and slit on the lathe; 45 s in a steamed lidded tray; skin slips when the onion is pushed through a silicone ring by the ram (S16) | 20 s per onion | Medium |
| Dice onion | Halves on the push-through grid cassette, staggered blades, 6 mm | 1–2 kN, 3 s | High (hand dicers work this way) |
| Mince herbs | Chopper cup | 5 s | High |
| Crack egg | Cracker cassette, one ram stroke; saucer checked by camera | 10 s per egg | Medium |
| Form Frikadellen | **Roll and cut:** mass spread in the tray between two 22 mm rails by the roller, ring cutter Ø80 stamps pucks, turner lifts them, rest is re-rolled | ±5 % | High |
| Rouladen | Apron roller cassette (S11) rolls the filled slice; rolls are laid seam-down in a channel insert in the braising pan, seam side seared first, so no tying | 60 s per roll | Medium |
| Bread a Schnitzel | Three GN 1/2-20 trays (flour, egg, crumbs) on the benches; tongs move the cutlet, bench vibrator shakes the tray, turner presses at 30 N | 40 s | Medium–high |
| Knead, roll out | Rotating-bowl cassette, 20 Nm; roll out in a tray between rails, between two silicone mats (no flour) | 1 kg, 6–8 min | High / medium |
| Mash | Ricer cassette under the ram; skins stay in the cylinder | 1–2 kN | High |
| Toss salad | Lid on the tray, wrist inverts it 4 times | 10 s | High |
| Flip steak / pancake | Turner stem with a counter-holder; for pancakes and fragile items the hourglass flip with a second hot pan | 3 kg on the wrist | Medium |
| Stir while cooking | Pot turns on its hob drive against a loose scraper hung on the rim; or a paddle stem on the wrist spin | 5–10 Nm | High |

### 2.7 Cleaning and drying

* **What gets wet:** only ware. Per 4-person meal about 1.0 m² of Zone F in 6–8 racks. The bay (2.7 m², Zone S)
  sees only traces because every operation is inside a tray (rule C7); it gets a 5-minute rinse from a fixed
  nozzle bar once a day (8 L, 60 °C) and is otherwise dry.
* **The gripper never gets dirty:** it grips the knob above the drip collar; the collar is washed with the tool.
  Used tools are dropped straight into the wash rack, which is their parking place (wet parking, C8).
* **Cycle per rack:** 15 s cold mains pre-spray to drain (1 L, carries scraps to a 2 mm strainer), 90–120 s
  tank wash at 60 °C with 40 L/min, 15 s fresh rinse 2.5 L at 85 °C (A0 ≈ 60 after about 20 s at 85 °C), 60–90 s
  air knife. **3.5 L and about 0.3 kWh per rack, 3–4 min.** Per meal about 25 L and 2.2 kWh; the tank is
  dumped and the chamber self-washed daily.
* **Drying by physics:** a 1 kg tray leaving at 80 °C stores about 25 kJ above 30 °C, enough to evaporate 10 g;
  the air knife leaves less than 5 g. Thin tools (150 g knife: 3.7 kJ, 1.5 g) depend on the air knife. The
  HDPE board and silicone mat are the only items that need 5 min of warm air.
* **Shadows and crevices:** each rack is a comb that holds its items in one validated pose; every item is a C2
  shape; cassettes fall apart when the gantry lifts them by the designated part.
* **Verification:** the clean gripper carries each item past a camera (white, oblique and UV-A light) before it
  is stored; plain brushed steel makes residue stand out; a witness coupon (S12) rides in each red rack.

### 2.8 Off-the-shelf / custom / novel

Off-the-shelf: GN trays, lids, boards, mats; knife and peeler blades; an undercounter commercial warewasher as
the wash engine (or its pump, boiler and dosing unit in a custom chamber); gantry axes. Custom: stems and
collars, cassettes, racks. **Novel:** drip-collar stem; tray as bench and gauge; "wash as you go" with an
all-steel, self-drying ware set; seam-down channel instead of tying.

### 2.9 Biggest weakness

Handling count: about 80–120 pick, place and rack moves per meal and about 45 loose items in two sets. At
99.9 % per move that is a 90 % success rate per meal, below the 98 % target, so every move needs self-locating
cones and a retry. The commercial wash chemistry is aggressive (pH 12–13) and the washer is loud.

---

## 3. Concept C — "Kolbenrohr": everything is a pipe

### 3.1 Core idea

The universal preparation vessel is a straight, open-ended dairy tube with a loose piston as its floor. A ram
pushing the piston turns the tube into a slicer with any slice thickness, a dicer, a ricer, a patty and
dumpling former, a paste doser, a variable-volume chopper and (two tubes nose to nose) a kneader and mixer.
A tube with a piston is the most cleanable vessel there is: the piston scrapes it empty (a "pig"), it has no
bottom corner, it is washed as a pipe with full-velocity flow, and one camera looking down the bore sees all of it.

### 3.2 Sketch

```
Tube: DIN 11850 DN100 dairy tube Ø104 x 2 (bore 100), L 250 (1.96 L) or 400 (3.1 L), clamp ferrules both ends.
Piston: one-piece blue UHMW-PE puck, two integral lips, 40 long. Small tube DN40 (bore 38) for pastes.

 S1 fill/weigh      S2 cut/extrude (vertical)        S3 knead/mix (horizontal)        S4 holster
   box dock            ram 5 kN, 300 stroke            ram L          ram R            (torpedo CIP)
     \\                     ||                          ||  orifice   ||
      \\                 ___||___  yoke               __||____|_|_____||__             ___________
   ____\\___            |  [pis] |                   | [pis] dough | [pis] |          |  _______  |
  |         |           |  food  |                   |_____________|_______|          | | core  | |
  |  food   |           |  food  |                     tube 1   plate  tube 2         | | Ø94   | |  tube slides
  |_[pis]___|           |__grid__|  <- end plate                                      | |_______| |  over the core:
   load cell         (sickle blade) <- stem tool,          S5 chop/whip               |  3 mm gap  |  pipe flow
                     180 rpm, one slice per rev          blade cap on tube,           |___________|  at 1.5 m/s
                     [receiver: pot / tray / tube]       magnet drive 500 W            sump 2 L

 Bay 700 W x 600 D x 700 H. Gantry X-Z with flip wrist carries tubes (max 3.5 kg filled).
 One flat bench (GN 1/2 tray, from concept B) for whole meat, salad, eggs, breading.
```

### 3.3 Kinematics and actuators

Gantry X, Z, flip wrist, gripper (4); vertical ram (1); sickle spindle (1, 8 Nm); two horizontal rams (2);
high-speed magnet drive (1); box tilt and vibrator (2); two holster pumps are not counted. **About 11
actuators** plus the flat bench's share of tools. End plates are loose and are held only by the axial clamping
force of the station yoke, so there is no fastener anywhere.

### 3.4 Tools and vessels

6 tubes DN100 (4 short, 2 long), 3 tubes DN40, 10 pistons; end plates: staggered dicing grids 10 and 20 mm,
grid 5 mm, ricer plate Ø3, Spätzle plate Ø8, orifice plates for kneading (7 × Ø16 and 19 × Ø8), mesh plate for
foaming, Ø80 forming sleeve, slot die 100 × 1.5 mm, blade cap, blank cap. Sickle blade on a drip-collar stem.
Flat adjunct: 3 trays, tongs, turner, apron roller. About 35 items. All tube parts are standard dairy
tube, ferrules and laser-cut plate.

### 3.5 Dosing and moving, by ingredient form

| Form | How |
|------|-----|
| Whole produce | Dropped from the box into the upright tube (piston low); pieces up to Ø95 fit, larger ones are first halved by the sickle on the bench |
| Leafy | Not in tubes, except herbs for chopping; salad goes to the flat bench (perforated tray) |
| Granular, powder | Tilt-poured into the tube on the load cell, then capped: **flour dust is enclosed** from that moment (PRP-014) |
| Liquid | Water directly into the pot; small liquid amounts for doughs into the upright tube on top of the dry goods |
| Paste, solid fat, mince | **The tube is a syringe:** 7.85 mL per mm of stroke (DN100), 1.13 mL per mm (DN40); strand cut by the sickle or a wire. Tomato paste, mustard, quark, butter, mince are dosed to ±2–3 % with no scoop and no residue |
| Raw meat, whole | Flat bench (red tray, tongs); cubes and strips: semi-frozen block in the tube, sliced and gridded |
| Egg | Flat bench cracker; whisked eggs are poured into the tube for batters |
| Frozen | IQF poured in; frozen herb or spinach blocks sliced by the sickle |
| Tube to tube, tube to pot | **Hourglass** (S4): mouths clamped, flip, or simply push the piston over the pot. Residue after pigging ≤ 0.5 % even for dough and mince (rule of thumb: a lip-wiped wall keeps a film of about 50 µm, about 4 g per tube) |

### 3.6 The hard operations

| Operation | How it is done in C | Numbers | Confidence |
|-----------|--------------------|---------|------------|
| Slice (any thickness) | "Microtome": ram advances continuously, sickle sweeps the mouth once per revolution; thickness = ram speed / 3 Hz | 3 mm at 9 mm/s; 1.5 kg of potatoes in under 1 min; blade force 50–70 N | High |
| Dice | Staggered two-level grid as end plate, sickle below it cuts to length | 10 mm grid on a full Ø100 column: 2–5 kN (hence the 5 kN ram); 5 mm on onion about 2–3 kN | Medium–high |
| Peel potato / carrot | Spike lathe (shared); carrots, cucumber, asparagus through the flexure-iris peeler as an end plate, pushed by the piston | 5 s per carrot | Medium |
| Peel onion | As concept B (steam and push through a silicone ring end plate) | | Medium |
| Mince herbs / fine chop | Blade cap on the tube; the **piston sets the chamber volume to the batch**, so one garlic clove chops as well as 300 g of onion; then the piston ejects everything | 5 s | Medium–high |
| Crack egg | Flat bench | | Medium |
| Form Frikadellen | Mass pushed through the Ø80 forming sleeve, 24 mm per piece, cut by the sickle: a 125 g puck | ±3 % by stroke | High |
| Klöße, meatballs | Ø40 plugs, then rounded under an orbiting cup on a wet tray | 5 s each | Medium |
| Rouladen | Mustard laid as a 100 × 1.5 mm ribbon from the slot die (no spreading tool); rest as concept B on the flat bench | | Medium |
| Bread a Schnitzel | Flat bench, as B | | Medium |
| Knead | Two tubes nose to nose with an orifice plate, rams push the dough back and forth. At 4 bar (3.1 kN) one pass of 0.9 L does 360 J; 12 kJ/kg needs about 33 passes of 4 s | 2–3 min per kg, closed, no dust | Medium: gluten development by repeated extrusion is plausible (dough brake, pasta press) but the crumb must be tested; 15 % head space is left for air |
| Mix mince mass | Same, 6–8 passes through the 7 × Ø16 plate | 30 s | Medium–high |
| Whip cream / egg white, emulsify | Same through the mesh plate with 3 parts air (two-syringe foam method); mayonnaise through the 19 × Ø8 plate with oil added in 4 steps | | Low–medium for foams, high for emulsions |
| Roll out dough | Extrude through the slot die as a 100 mm band of the wanted thickness, laid side by side on the tray; or flat bench with roller | | Low–medium |
| Mash | Boiled potatoes, skin on, through the ricer plate; skins stay on the plate and are pigged into the waste | 1–1.5 kN | High |
| Spätzle | Batter through the Ø8 plate over the pot, sickle cuts | | High |
| Toss salad, flip | Flat bench, as B | | — |

### 3.7 Cleaning and drying

* **Step 0, pig:** the piston is pushed right through and out. What remains is a film.
* **Step 1, torpedo holster (S2):** the tube is slid over a fixed Ø94 core inside a jacket, so inner and outer
  walls each face a 3 mm annular gap. At 1.5 m/s the inner gap carries 82 L/min (pressure drop about 15 mbar),
  which a dishwasher circulation pump delivers; flow must pass every square millimetre, so a spray shadow is
  impossible by construction. Programme: 1 L cold to drain (10 s), 2 L enzyme at 50 °C for 3 min, 1 L rinse,
  1.5 L at 85 °C for 60 s, hot air through the gap for 60 s. **5.5 L, about 0.3 kWh, 6–7 min per tube.**
  Three tubes per meal: about 17 L.
* **Small parts** (pistons, plates, blade, stems): a comb rack in a small chamber as in concept B, or their own holsters.
  Grids are the one geometry that traps fibres; they get jets against the cutting direction and are the first
  candidates for flash pyrolysis (S7).
* **Drying:** tube steel (1.6 kg at 80 °C) flash-dries; UHMW pistons need the air.
* **Verification:** turbidity and conductivity in a 1.5 L last rinse (10 mg of residue is about 7 mg/L, easily
  seen); pump pressure signature proves the gap was not blocked; a camera with a ring light looks down the
  bore and sees 100 % of the inner surface in one image.
* **Zone F per meal** about 0.5 m², the smallest of the four; the bay stays nearly clean because food is
  enclosed from box to pot.

### 3.8 Off-the-shelf / custom / novel

Off-the-shelf: dairy tube, ferrules, caps, sieve plates; 5 kN ball-screw actuators; dishwasher pumps.
Custom: pistons (turned), grids and plates (laser-cut and sharpened from one piece), holsters, yoke.
**Novel:** the tube-and-piston as universal vessel; ram-fed microtome slicing with one blade for all
thicknesses; variable-volume chopper; reciprocating-extrusion kneading; syringe dosing of every paste;
torpedo CIP for an open vessel.

### 3.9 Biggest weakness

It is a concept for everything that can be pushed. Whole meat pieces, leaves, eggs and anything flat need the
flat bench from concept B, so C is never alone. The two new processes (kneading and foaming by reciprocating
extrusion) are unproven for quality. The piston lip is a wear part, and thin liquids seep past it, so tubes do
not hold liquids.

---

## 4. Concept D — "Zwei-Bahnen-Küche": the work surface is thrown away

### 4.1 Core idea

Raw meat, dough and coatings, the soils that are hardest to wash, are handled between two webs of baking
paper drawn from rolls: a lower web that is work surface and conveyor, and an upper web through which every
tool (roller, press plate, scraper) acts. No tool and no table ever touches food, so nothing in this
station is washed; the used paper wraps the leftovers and goes to the waste. This is what a cook does with
cling film and baking paper, made into a machine.

### 4.2 Sketch

```
Side view, module 600 W x 600 D x 450 H

   upper roll (400 wide)                      tool gantry X-Z (dry): roller Ø60, press plate 250x150 (1.5 kN),
      (O)___________________                  squeegee bar; tools touch only the back of the upper web
           upper web        \___  peel bar Ø6 (web pulled back 180 deg -> releases from food)
   ..........food............
   ========lower web=====================\  nose bar Ø8: food slides off the web edge,
  | vacuum table 400 x 500, two halves,   \ drop <= 30 mm into pan / tray / baking sheet
  | hinged in the middle ("book flip")     \
  | trough slot 60 wide for rolling         (O) take-up: used web + scraps -> waste
   lower roll (O)   table on 3 load cells (portions by weight)
```

### 4.3 Kinematics and actuators

Lower web drive, upper web drive, peel bar, book-flip hinge, tool gantry X and Z, press, web cutter:
**8 actuators.** The roller and squeegee are passive.

### 4.4 Tools and vessels

None that touch food. Rolls of wet-strength, compostable baking paper 400 mm × 200 m. The module is fed by and
feeds into whatever vessels the host concept uses (trays of B or tubes of C); alone it cannot cut, mix or dose
liquids, so as a whole system it is always "D plus closed vessels".

### 4.5 Dosing and moving, by ingredient form

| Form | How |
|------|-----|
| Raw meat, fish | Dropped from the opened pack onto the lower web; moved by advancing the web; leaves over the nose bar |
| Dough, mince mass | Deposited in weighed portions (table on load cells) from a bowl or tube |
| Powder (flour, crumbs) | Sifted from the box onto the web; surplus is wrapped up and discarded |
| Liquid (egg wash) | Into a paper trough: the web is sucked into a shallow table depression and holds 50 mL for the 30 s needed |
| Whole produce, leafy, granular, frozen, paste | Not handled here (host concept) |

### 4.6 The hard operations

| Operation | How it is done in D | Numbers | Confidence |
|-----------|--------------------|---------|------------|
| Flatten Schnitzel, Rouladen slices | Between the webs, press plate or roller passes | 0.5–1.5 kN, to 5 mm ±1 | High (the cook's method) |
| Bread a Schnitzel | Flour on the web, cutlet on it, **book flip** turns it; paper trough with egg, flip; crumbs, press through the upper web at 30 N, flip, press | 45 s, all three "stations" are thrown away | Medium |
| Form Frikadellen | Weighed blobs, upper web down, press to 22 mm, peel, advance over the nose bar into the pan | ±5 % by weight | Medium–high (patty paper is standard) |
| Rouladen | The lower web dips into the trough slot and acts as the rolling apron (S11); a bar drags it over and the roll forms; seam-down channel or a wooden pick | 45 s per roll | Medium |
| Knead | No | | — |
| Roll out dough | Between the webs with the roller on gauge rails, 2–10 mm, no flour, no sticking; the lower paper then serves as the baking paper in the oven, so it is used twice | 20–60 N | High |
| Flip pancake / steak | Not here | | — |
| Cut raw meat | **Not possible on paper** (paper fragments in food); must be done on a washable board | | — |
| Peel, dice, herbs, egg, mash, salad, drain | Host concept | | — |

### 4.7 Cleaning, waste and honest accounting

* Nothing is washed per use. Table and tools are Zone S, touched only by paper; they get the daily bay rinse.
* **Waste:** about 0.6 m of lower and 0.5 m of upper web per use, 0.44 m², about 18 g of paper. If 40 % of
  meals use the station: about 2.6 kg of paper a year, about 25 EUR, one roll change per year and web.
  The washing it replaces is roughly 5 L and 0.4 kWh per use, so cost and footprint are about equal; the gain
  is certainty, not economy.
* **Disposal:** siliconised baking paper is not accepted in the organic bin in many German municipalities; use an
  EN 13432 compostable grade or send it to residual waste. It carries raw-meat juice, so it must go into the
  sealed bin at once.
* **Verification** is trivial: a fresh web is clean by definition; a camera checks that the web is whole
  (no tear, no missing piece) before the food is released.

### 4.8 Off-the-shelf / custom / novel

Off-the-shelf: paper rolls, web-handling rollers, vacuum blower. Custom: table, nose and peel bars, book hinge.
**Novel:** two-web sandwich so that tools never touch food; book flip; nose-bar transfer into the pan;
the web as Rouladen apron; paper trough for egg wash.

### 4.9 Biggest weakness

It covers only flat, sticky work, perhaps a fifth of all operations, and it adds a consumable and a web path
that can tear or wrinkle. It contradicts "refill rarely" only mildly (one roll a year), but it is a second
architecture inside the machine that has to earn its place against simply washing three trays.

---

## 5. Standalone sub-mechanism ideas

Each can be used in any concept. Feasibility: H high, M medium, L low/wild.

**S1 Drip-collar stem (Tropfkragen).** Every tool has a steel stem with a conical umbrella Ø70 and a knob
above it. The gripper holds only the knob, which soil cannot reach from below; the collar is washed with the
tool. This removes the gripper cross-contamination path (`research/06` 6.4) without a gripper wash station.
Feasibility H; the collar limits how deep a tool can reach into a narrow vessel.

**S2 Form-fitting wash holster ("Köcher-CIP").** Turn an open tool into a closed pipe for washing: it is
parked in a sheath that leaves a 3 mm gap all round, and wash water is pumped through the gap at 1.5 m/s.
For a 200 mm knife the gap is about 360 mm², so 32 L/min from a 1 L sump; 2.5 L, 0.1 kWh, 3 min per tool.
Flow has to pass every surface, so there is no shadow, and the 1 L loop makes turbidity very sensitive.
Feasibility H for simple tools, M for whisks (needs a basket-shaped sheath).

**S3 Spike lathe and lathe dicing (Spießdrehbank).** Round produce is held between a driven three-prong
spike and a free tailstock cup. One floating Y-peeler blade peels potato, apple, kohlrabi, celeriac; a knife
tops and tails; for dicing, the knife makes 24 meridian cuts (index 15°) and then slices across the axis, which
is exactly the cook's onion technique. Forces below 70 N. Feasibility H for peeling (consumer products exist), M for dicing;
deep potato eyes stay (within the 5 % of PRP-022).

**S4 Hourglass transfer.** Two vessels with equal rims are clamped mouth to mouth and inverted. No pouring
arc, no spill, no dust, works for powder, pieces and pastes (with a tap). With two hot pans it is a pancake,
omelette, fish and Rösti flip that needs no spatula under a fragile item. Needs equal rim diameters as an
architecture rule. Feasibility H; wrist must carry both vessels (3–4 kg).

**S5 Jet gate: the manipulator is the rack.** A fixed plane of 6 fan nozzles at 5 bar (12 L/min from a small
sump). The manipulator passes each used tool through it while turning it, so every face meets a jet at 50 mm
distance. 20 s and about 0.5 L net per tool. Good as cold pre-rinse (C8) everywhere. Feasibility H.

**S6 Freeze-plate gripper.** A flat steel plate chilled to −10 °C by a Peltier element freezes the moisture
film of a meat slice, fish fillet or dough sheet in 1–2 s and holds it (order of 1 N/cm²); a short heat
pulse releases it. The gripper is a flat plate, the easiest shape to clean, instead of fingers. Freeze
grippers exist in food handling. Feasibility M; fails on dry or floured surfaces.

**S7 Flash pyrolysis by induction.** Plain steel parts without a hardened edge or polymer (dicing grids,
ricer and orifice plates, needles, channel inserts, grill grates) are laid on an induction coil in a small
vented box and heated to 450 °C: 300 g needs about 65 kJ, under a minute at 2 kW, against 1.3 kWh for a wash.
Residue turns to ash and is blown or rinsed off; allergens are destroyed. Limits: knives soften (martensitic
blades are tempered at 200–300 °C; only HSS or cobalt alloys would survive), ferritic 1.4016/1.4521 couples
well but austenitic does not, repeated heat tint lowers pitting resistance, smoke needs a catalyst.
Feasibility M as a weekly "reset" for grids, L as the only cleaning.

**S8 Bread pig.** The butcher's trick: after mince or paste, push a slice of stale bread through the tube,
grinder or grid. It wipes the wall and the blades, soaks up the residue and goes into the Frikadellen mass,
which needs soaked bread anyway. Yield up, wash load down. Feasibility H where the recipe contains bread;
otherwise a potato slice.

**S9 Flexure-iris peeler.** Six standard peeler blades on the fingers of a one-piece laser-cut spring-steel
spider form a ring that opens from Ø15 to Ø60. A carrot, cucumber, salsify or asparagus spear is pushed
through, turned 30° and pushed back. No hinge, no spring, one part. 5 s per carrot. Feasibility M; blade
attachment without a crevice (laser weld) is the detail to solve.

**S10 Piston box (Schubboden-Box).** A member of the box family for sticky goods (mince, quark, butter,
tomato paste, cooked rice): prismatic, no draft, with a loose follower plate as floor. A ram pushes the
follower; the contents leave as a strand that a wire cuts, dosed by stroke and checked by weight. The box is
scraped empty by its own floor (BOX-013) and both parts are plain shapes for the washer. Feasibility M–H;
needs a lip seal that is tight at −25 °C and a hole pattern in the storage grid for the ram.

**S11 Apron roller for Rouladen (dolma-roller principle).** A loose band of silicone sheet (or the paper web of
concept D) hangs as a pocket between two bars. The slice with its filling lies on the band; pulling one bar
over the other rolls it into a tight cylinder Ø45–55, as cigarette rollers and vine-leaf rollers do. The band
is a flat sheet when removed. Securing without string: lay the rolls seam-down in a **channel insert** in the
braising pan and sear the seam first; optionally press the seam for 5 s on a 200 °C bar with a pinch of salt
so that the proteins bond. Feasibility M; works also for cabbage rolls.

**S12 Witness coupon.** A small steel coupon is dipped at the start of each meal into that meal's worst soil
(egg, mince, batter) and left to dry the longest, then rides through the wash with the ware. If the camera
finds the coupon clean, everything that was soiled later and dried less is clean too. This gives a
per-cycle worst-case proof instead of process parameters only (HYG-026). Feasibility H.

**S13 Vitamin-B2 self-test.** Riboflavin is the standard tracer for spray-coverage tests and is a food
vitamin. Once a week the machine mists a riboflavin solution over the clean ware or the cell, runs a rinse,
and looks under UV-A: any remaining glow is a spray shadow or a blocked nozzle. HYG-019 becomes a recurring
automatic test instead of a one-time validation. Feasibility H; 50 mL of solution a month.

**S14 Spin-rinse-dry for round ware.** Borrowed from semiconductor wafer cleaning: a vessel that is a body
of revolution is set upside down on a spindle at 600–1200 rpm over one radial line of nozzles. Rotation
gives full coverage with a single jet line, and at 100 g the film is thrown off, so the vessel is nearly dry in
20 s without hot air. 1–2 L per vessel. The same spindle is the salad spinner. Feasibility H for bowls and pots;
argues for making all vessels round with one rim diameter.

**S15 Water-jet peeling and the jet as a tool.** A 100 bar pressure-washer pump (1.4 kW, 6 L/min) with a
rotating nozzle strips thin skins (carrot, new potato, ginger) without any tool to clean, inside a closed tub,
water recirculated through a strainer; the same lance spot-cleans burnt soil. About 1.5 L and 15 s per piece.
Feasibility L–M: loud, makes aerosol, skin thickness of old potatoes may be too much; worth a one-day test.

**S16 Steam-slip onion peeling.** Top and tail, slit the skin once, 45 s in steam (cook's trick for pearl
onions), then push the onion through a silicone ring slightly smaller than itself: skin and first layer stay
behind. Steam comes from the cooking module. Feasibility M; the outer layer is slightly cooked, which does not
matter for onions that are going to be sweated.

**S17 Decap, do not crack.** A spring-ball egg topper (standard German tool) scores a circle on the blunt
end, a suction cup lifts the cap, the egg is inverted and emptied. The shell stays in two whole pieces, so
fragments are far less likely than with an equator crack. Feasibility M; the yolk must pass a Ø32 opening
intact, to be tested against the 90 % requirement.

**S18 Flume transfer.** Cut vegetables are carried from the cutter to the pot's insert basket in a stream of
water through a closed pipe; the pipe is its own CIP line and the water is the washing water of UO-10.
Contact time is seconds. Feasibility M for vegetables that are washed anyway; not for anything that must stay dry.

**S19 Mirror ware and stripe inspection.** Electropolished ware reflects a projected stripe pattern; any
film or particle dulls or bends the stripes and is found by a plain camera at far higher sensitivity than
looking for colour. Chooses the ware finish for inspectability (rule C11). Feasibility M–H.

**S20 Steam gate.** A slot nozzle with 2 kW of steam (0.8 g/s) through which a blade passes for 3 s between
two ingredients: melts fat, sanitises, condensate carries juice away. Not a cleaner for dried soil, but it
removes most mid-meal washes of the knife. Feasibility H.

Considered and rejected from this lens: hydrophobic and ceramic coatings (wear off in alkaline washing),
ultrasonic baths (only as an option for grids), UV-C or ozone as a substitute for washing, dry-ice blasting
(needs a gas supply), bag liners for all vessels ("stomacher" kneading in a bag works, but costs 20–30 g of
plastic per meal).

---

## 6. Which concept I would bet on

**B as the logistics, with the Kolbenrohr of C as its main cassette; D kept in reserve.**

* B is the only concept whose cleaning is both already proven (rack washer, fixed poses, steel ware) and fast
  enough to wash within a meal, and it handles the flat and whole items that no clever vessel can: steak,
  Schnitzel, salad, eggs, Rouladen.
* C removes most of B's weakness. One tube with a ram replaces B's dicer, slicer discs, ricer, patty ring,
  paste scoops and mixing bowls, cuts the item count from about 45 to about 30 and the handling moves by
  roughly half, and it encloses flour and mince from box to pot. Its cleaning proof (pig, pipe flow, one
  camera view down the bore) is the strongest of all.
* A is the most elegant statement of the lens but soils and blocks a whole tub for every onion. I would keep
  two things from it: the spike lathe and the jet gate.
* D is the fallback if washing of raw-meat and dough ware fails validation (HYG-021/022). It should not be
  built first.

First tests, in this order: reciprocating-extrusion kneading (bread crumb quality), dicing-grid force on a full
Ø100 column, torpedo-holster cleaning of dried egg and dough with riboflavin, flash-dry of steel ware.

---

## Open issues

1. Meal corpus not yet available; coverage of the four concepts was judged against requirements 5.3 only.
2. Kneading and foaming by reciprocating extrusion (C) have no quality data.
3. Dicing-grid force on a full tube cross-section is estimated at 2–5 kN; hand-dicer experience suggests the
   lower end, the research figure of 2–5 N/mm the upper.
4. Onion peeling is uncertain in every concept (jet, steam-slip); frozen or peeled onions remain the fallback.
5. Rouladen: rolling is solved on paper by the apron; securing relies on the seam-down channel, to be proven
   over a 2-hour braise. Bacon slices that stick together in the pack are not solved (diced bacon as adapted method).
6. Equal rim diameters (hourglass, spin-rinse-dry) and a piston member of the box family are requests to the
   architecture (A1).
7. A commercial-type washer (B) needs a check against the noise and consumable requirements.
8. Blade sharpness over a year (PRP-034) and blade-break detection (PRP-035) are only addressed by using
   standard replaceable blades and a camera check in the holster.

## Risks

| # | Risk | Concept | Mitigation |
|---|------|---------|------------|
| 1 | Handling reliability with many loose parts falls below 98 % per meal | B | Tube cassette reduces part count; self-locating cones; retry logic |
| 2 | Dynamic seals in the food zone become biofilm sites | A | Washed in place, stroked through the wiper, replaceable from the dry side; or drop A |
| 3 | New processes do not give home-cooking quality | C | Keep the rotating-bowl kneader of B as a fallback cassette |
| 4 | Fibres and sinew lodge in dicing grids | B, C | Reverse jets, bread pig, weekly flash pyrolysis, camera check |
| 5 | Paper web tears or is rejected as waste | D | Wet-strength compostable grade; D only as reserve |
| 6 | Piston lip wear leaves an uncleaned film | C | Lip is a listed wear part; bore camera detects streaks |
| 7 | Hot tank wash bakes protein on | B | Cold pre-spray in every cycle (rule C8) |
