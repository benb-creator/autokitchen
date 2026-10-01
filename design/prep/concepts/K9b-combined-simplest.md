# Meal preparation — Round P5b: combined machine K9b "SCHLICHT" (simplest)

**K9b SCHLICHT** ("plain"): one 4-axis hand whose gripper *is* its roll axis, one turning hub that brings all
force and speed, a 2-zone household domino, a countertop combi-steam oven mounted high, one top-loading well
that washes ware and dishes and stores the big ware between meals. **6 motion actuators, 2 dynamic seals.**
It combines K9 EINHAND (`../concepts/K9-einhand.md`) with the round-2 improvements K1b … K8b and removes
whatever a passive part, a recipe route or the human's normal table habits can replace.

Decision state: DECISIONS #1–28. Markers: **[D]** from a concept, critique or round-2 document; **[C]**
calculated here; **[E]** engineering estimate; **[U]** unknown, a test or supplier answer decides. Nothing
has been built. Coordinates: machine X from the left end of the machine, y from the rear inner wall (0) to
the inside of the front (580), z from the floor; mm.

---

## 0. Idea pool

Every improvement idea of K9 and of the seven round-2 documents (their sections 1, 2, 6, 8), one line each.
Verdict for K9b: **T** take, **M** maybe (kept as option or fallback), **R** reject. "Why" names the
deciding criterion: simplicity first (#20), then hygiene, coverage, reliability, fit.

### 0.1 Manipulator and grip

| # | Idea | Source | V | Why |
|---|---|---|---|---|
| 1 | One serial gantry hand, no dock, no tool changer | K9 P-3, C5 S-min | T | fewest drives; every round-2 concept ended with one hand |
| 2 | EPM tang chuck, roll-driven tongs by a second EPM ring | K9 N1 | M | 0 moving parts, but needs power at a rotating face → slip ring → roll lip seal; fallback 2 for ideas 5–6 |
| 3 | Pin jaws with load pins (servo screw) | K3b, K5b, K6b | M | proven, but +1 actuator, +1 rod seal, +1 roll lip seal; fallback 1 for ideas 5–6 |
| 4 | V-groove (Tri-Clamp) jaws with tool notch, stroke closes U-tongs | K2b | R | +1 actuator, +1 lip seal; centring of rim pairs not needed with hooked pan pairs |
| 5 | **Canned magnet roll coupling at the arm tip** (torque-limited, no seal) | K1b | **T** | removes the only seal that sits right above food; overload slips instead of breaking |
| 6 | **Bayonet stub Ø 22 locked by 60° of roll; fixed reaction tab works pincer tools** | K1b | **T** | the gripper costs 0 actuators and 0 seals; novel N1, kill test E2 |
| 7 | Elbow turret (ceiling disc + rod + yaw) as the hand | K1b | R | custom slewing ring and an open seam (novel); a gantry is bought modules |
| 8 | Two magnetic pucks behind a sealed drive wall (0 seals) | K8b | R | 6 novel mechanisms, magnet forces unmeasured; stays the H-S2 research track |
| 9 | Wall-mounted SCARA arm with EPM dovetail shoe | K4b | R | needs the mat line to pay off; reach is one line |
| 10 | **No Y axis**: ware line plus polar work on the turntable | K2b, K8b | M | −1 actuator, −1 band, but forces a one-line layout (+width, linear hob) and loses the Y traverse of spit peeling; kept as cost-round option |
| 11 | **X axis behind a contact-free labyrinth with purge air** | K3b, K6b | **T** | no seal on the longest axis |
| 12 | **Y band on the arm's top face inside a sloped gutter** | K3b, K6b | **T** | the one band over food cannot drip |
| 13 | Z band on the mast face towards the wall | K6b | T | band faces away from food |
| 14 | Y as a closed arm sliding through a wiper collar | new | M | would move the Y seal into the rear lane; untested; cost-round option |
| 15 | **Single-point load cell under the arm root** (every grip weighed, loss-in-weight doses) | K1b (Z carriage), K2b (load pins) | **T** | moment-insensitive bought cell in the dry zone; replaces wrist 6-axis cell |
| 16 | Coupling lag (two Hall sensors) as torque signal | K3b | T | free torque sensing for stirring, kneading, spit, press |
| 17 | Tang family: spine bar on trays, far-side hook locking pairs | K6b, K1b | T | hook and catch make hermaphroditic pan and rack pairs; stub at the tray's rear corner instead of a spine |
| 18 | Tool racks: one grip moves five tools | K6b | T | −8–10 events at meal start and end |
| 19 | Passive tool carousel indexed by the hand | K2b | R | a rack on rails in the cabinet is simpler |
| 20 | Pour about a virtual lip pivot; never invert hot liquid | K2b, K3b, K9 | T | coordinated X/Z/roll; no cradle |
| 21 | Slide, don't lift (deck, glass, lids flush) | K6b | T | heavy braisers slid; payload stays 6 kg |

### 0.2 Force, speed, turning, heat

| # | Idea | Source | V | Why |
|---|---|---|---|---|
| 22 | **Recessed coaxial canned hub: slow T (25–30 Nm) and fast S (6000 rpm) in one drained pocket** | K8b, K2b | **T** | two drives, one pocket, zero seals |
| 23 | **Ring induction coil around the hub = one heated turning position** | K2b (KH); heated turning in K1b, K4b, K5b, K6b | **T** | continuous stirring, −6–12 stirring events per stirred meal, hand freed; one OEM module, no actuator |
| 24 | Two turning carrier rings on PEEK rollers on the hob | K1b, K6b | R | 2 drives and a custom hob for what one hub does |
| 25 | **Anchor post takes reaction torque of hung scraper, kneading roller, press cup** | K2b, K5b (crosshead), K6b (anchor pins) | **T** | the hand is free while T works |
| 26 | Kneading bowl under a hung roller and scraper (Ankarsrum principle) | all seven, K9 | T | proven home appliance principle |
| 27 | Interval stirring by the hand | K9 | M | kept for a second stirred dish on the domino |
| 28 | Drum tilting about its lip on a canned bell (wash, rumble, wok, stir, drain, mash) | K3b | R | +2 actuators, +1 seal, spun custom drum; heated hub covers stirring |
| 29 | **Press cup on T**: screw in the base turned by T, piston rises, product through a die on top, swept into a spout | K8b | **T** | 0 actuators, 0 seals, force loop inside the cup; 3 kN at 13 Nm |
| 30 | Screw cassette turned by the roll axis | K9 | R | canned roll is limited to ≈ 10 Nm |
| 31 | Pull-down press column over the heated turning position (gravity into the pot) | K5b, K4b (swing press), K6b | M | best output path, but +1 actuator, +1–2 seals; fallback for E3 |
| 32 | Bought catering lever push-dicer worked by Z | K1b | M | 0 actuators but 8–10 kg and a 300 × 300 footprint; fallback for E3 |
| 33 | **Bought push-dicer grids as press dies** | K1b, K5b, K8b, K9 | **T** | cheap, proven blades |
| 34 | Food mill on T; processor dicing kit through a chimney bowl | K2b | R | press cup and cutter cup cover ricing and dicing |
| 35 | **Cutter cup on S with bought food-processor discs (slicer 1–6 mm, grater)** | K3b, K6b, K2b | **T** | slicing and grating with bought parts, no new cutting physics |
| 36 | Knife cage on the turning ring (one revolution = one cut) | K5b | R | needs a press column; slicing disc does it |
| 37 | Head splitter with centre corer | K5b | R | heads quartered by knife and cored by cheek cut |
| 38 | Bought cordless stick blender held by the hand | K5b | M | cost-round option if S is cut |
| 39 | Ramp-supported roller driven by the roll axis | K3b | R | needs 30 Nm; gauge-ring pin pushed by Z does sheeting |
| 40 | Vertical T-lathe: produce on T against a held blade; trepanning, parting, cabbage shredding | K8b, K2b, K4b | M | spit on the roll does the same jobs with a fixed post; T is busy cooking; kept as option for celeriac and cabbage |
| 41 | Spiral rounding guide on T | K5b | R | disher plus pan press gives a traditional shape |

### 0.3 Cooking, oven, cleaning, serving

| # | Idea | Source | V | Why |
|---|---|---|---|---|
| 42 | Household 60 cm 4-zone hob, touch board interfaced | K9 | M | €500, 4 zones, but 300 mm wider than needed; option if storage width allows |
| 43 | **Household 2-zone domino hob** | K3b | **T** | with the heated hub = 3 positions (COK-002 M) in 600 mm |
| 44 | Bought flex hob under-mounted, GN ware on oval coils | K8b, K2b | M | flex domino as a variant |
| 45 | Countertop combi-steam oven turned into the cell | K9, K3b, K5b | T | appliance largely as bought (#24, #28) |
| 46 | Driven door (gearmotor) on the oven | K9, K3b | R | the hand opens it with the hook rod |
| 47 | **Oven door opened and closed by the hand's hook** | K5b | **T** | −1 actuator |
| 48 | Oven outside the cell, front-facing, loaded by the transport | K1b, K2b, K4b, K8b | R | moves complexity into the transport (Z reach, oven access, door) |
| 49 | **Stack by heat and wetness: oven high, washer low** | K3b, K9 | **T** | oven over the well in one 500 mm column |
| 50 | Compact oven with its floor flush with the deck, drop door into the plinth | K6b | R | heavier modification of the appliance |
| 51 | Side-loading wash chamber under the oven, items pushed in +X | K9 | R | the mast cannot enter the column; loading and unloading need pushing and hooking |
| 52 | **Top-loading well under a lid that is the bench** | K6b | **T** | natural for a Z axis; uses the space under the deck |
| 53 | **One washer for ware and dishes** | K6b, K1b, K9 | **T** | one wash system for the machine |
| 54 | **Well = closed clean store between meals** | K1b | **T** | no large ware cabinet |
| 55 | **30 L under-sink heater charged while the oven is off; 88 °C rinse; 0 W wash heating during cooking** | K6b, K1b | **T** | bought appliance; fast cycles; power plan |
| 56 | **Class R hold ≥ 82 °C for 60 s (A0 ≥ 90), logged** | K2b, K6b, K8b | **T** | short, validated moist-heat disinfection |
| 57 | In-meal open downdraft well; clean-air tool nook | K8b | R | open well needs extraction through its floor; nook is one more station |
| 58 | Wash lift with a rack lowered by the manipulator | K2b | R | rack is one more item and a lid mechanism |
| 59 | All ware to the machine's separate dishwasher through a port | K5b | R | needs transport traffic and a dish loader |
| 60 | Wash well under the turret | K1b | R | needs the turret |
| 61 | **Drain, tap spout, gripper jet gate and strainer merged in one funnel** | K6b (hopper), K2b, K8b (well mouth jets) | **T** | three K9 stations (DG, J, spout) become one "rinse cup" |
| 62 | **Peeler/blade post on the waste opening's rim** | K1b, K3b, K9 | **T** | peel falls straight to waste |
| 63 | Closed chute to a 20 L bin in a front drawer | K9, C2 R-8 | T | |
| 64 | Cup scale S0 0.05 g | K9 | R | levelled measuring spoons (cook's method) and T load cells suffice |
| 65 | **Levelled spoons; spice boxes with a levelling edge** | K1b, K2b | **T** | 0 parts |
| 66 | Fixed nozzle rail, fan dry; per-meal hob-zone rinse | K9, K6b, K1b | T | no lance |
| 67 | Rear fume slot / downdraft with a bought hob-extractor fan | K6b, K9, K1b | T | bought |
| 68 | Clean-ware cabinet over the hob behind an insulated soffit | K9, K2b, K3b | R | nothing static above the hob; cabinet only over the serving column |
| 69 | **Hatch drawer pulled out by the diner, solenoid-locked** | K6b | **T** | −1 actuator vs K9 |
| 70 | Spring plate dispensers | K9 | R | plates live on carriers (wash, store, set the table) |
| 71 | Plating on a turntable in polar coordinates | K1b, K2b, K4b, K5b, K8b | R | the heated hub is cooking at plating time; Y axis places directly |
| 72 | Fall lane; drop-down pocket door | K8b | R | belong to the tub concept |
| 73 | Second set of 8 items for the next meal within 30 min | K9 | M | 5 items kept |

### 0.4 Food routes and produce

| # | Idea | Source | V | Why |
|---|---|---|---|---|
| 74 | Box tipped by the roll, lip-pivot path, loss-in-weight | K9, C5 A1, K2b, K3b | T | 0 actuators |
| 75 | Passive box cradle tilted by a lever; dock tilter | K4b, K8b | R | the hand tips |
| 76 | Passive egg fixture (bottom strike, hinge-open cradle, slotted saucer, 2 mm strainer) | K9, G-assembly; all | T | |
| 77 | Dunk basket over a 40 mm sediment zone in a red wash pot | K9 GP-W1, K1b, K6b | T | |
| 78 | **Spit on the roll against a blade post with depth shoes 1 / 2.5 / 5 mm** | K9, K1b, K3b, K5b, K6b | **T** | household apple-peeler principle; generic (#25) |
| 79 | **Press-peel / grid skinning / rice-in-skin: skin and stone stay, flesh passes** | K5b, K6b, K9, K2b (mill), K1b | **T** | banana, avocado, mango, potato, pumpkin with zero extra hardware |
| 80 | Blanch-and-slip; cook in the skin | K9, all | T | recipe routes |
| 81 | Knurled peeling drum on T | K9 | R | T is the heated position; spit peels raw potatoes (4–5 min per kg) |
| 82 | Tube corers Ø 14/22/42, plunger pitter, seed spoon, cheek cuts | K9, K1b, K5b, K6b | T | |
| 83 | Small tube with knife ring pushing banana out of its skin | K6b | M | slices for fruit salad (DS10, BF01) if the test passes |
| 84 | GA-20 raft, dry floured flap, mustard stopping 35 mm short, fond first | all | T | |
| 85 | Curl hood (bread-moulder) for Rouladen and logs | K3b | R | needs the belt |
| 86 | Silicone apron roll for Rouladen | K6b, K2b | M | fallback to the fork-and-turner roll |
| 87 | **Rack breading: cutlet stays on the wire rack from flour to pan** | K5b | **T** | no grip on the crust |
| 88 | Lift-rack pair GA-36 in 200–250 mL fat | all | T | |
| 89 | Hermaphroditic pan pair (either pan is the flip partner) | K1b, K3b, K6b | T | removes K9's separate flip pan |
| 90 | **Spin-spread pancake batter on the turning position** | K1b | **T** | pan on heated T spins once |
| 91 | **Disher portions for Frikadellen, pressed flat in the pan** | K1b, K4b, K8b | **T** | traditional shape, no extrusion |
| 92 | Extrusion through Ø 70 orifice with wire cut-off | K9 | R | cylinders (C1 R-10) |
| 93 | Rolling pin with gauge rings | K9, K2b, K4b, K5b | T | thickness from rings, not stiffness |
| 94 | Belt cassette, mats, capstan nose, blade column, lay-down, order-on-band stacks | K3b, K4b | R | carry few meals for 2–3 actuators each |
| 95 | Ravioli plate (square parcels), hinged dumpling press | K9, K3b | T | IT17, DM33, CK17 (mandated c) |
| 96 | GA-14 V-trough with gauge plate for carving | K9 | T | |
| 97 | Carving by parting a roast standing on end on T | K2b | R | T is cooking at carving time |
| 98 | Garlic cracked and pressed in the skin (GP-17) | K8b | T | press cup garlic die; peeled garlic no longer needed |

### 0.5 New ideas in K9b

| # | Idea | V | Why |
|---|---|---|---|
| 99 | **Narrow oven mounted high (z 1550–1950, ≤ 460 mm in y) so that the mast passes behind it** and the well under it is reached from above | T [U] | oven and washer share one column without a side-loading chamber |
| 100 | **Carrier inversion over the chute**: plates on edge in a carrier with retaining bars, roll 180°, scraps fall | T | dish scraping in one event |
| 101 | **Diner slots returned plates into the carrier in the hatch drawer** (as into a dish rack) | T (Q8) | dish return ≈ 5 events instead of ≈ 35 |
| 102 | **Family-style serving** in lidded serving dishes plus clean warm plates on the carrier | T as mode (Q9) | the simplest serving; plated mode kept |
| 103 | Passive **plate cradle** (slotted L-plate): lifts a plate on edge, roll 90° lays it flat, ribs of the hatch tray strip it | T | plating without a plate dispenser |
| 104 | Bought **Spätzle slider** (Spätzlehobel) moved by the hand over the pot | T | traditional, 0 parts beyond a stub |
| 105 | Rouladen braised lidded on the domino, not in the oven | T | traditional; no 5 kg braiser at 1.6 m |
| 106 | Plates warmed on their carrier in the oven at 60 °C | T | no heated dispenser |
| 107 | Height rule on the domino: pans in the rear zone, pots in front, so every bayonet stub is reachable from behind | T | 2-row access with a gripper that approaches along +y |

### 0.6 Convergences (ideas several improvers reached independently)

| Idea | Reached by | Count |
|---|---|---|
| A turning station with tools hung against a fixed reaction point (Ankarsrum) | K1b, K2b, K3b (drum post), K4b, K5b, K6b, K8b | 7 / 7 |
| Turn the produce against a held, shoe-guided blade (spit or T-lathe) | K1b, K2b, K3b, K4b, K5b, K6b, K8b | 7 / 7 |
| Lift-rack pair in 3.5–4 mm fat; GA-20 raft with floured flap and fond first | all seven | 7 / 7 |
| Potatoes cooked in the skin and riced or slipped | all seven | 7 / 7 |
| Canned magnet drives instead of shaft seals | all seven | 7 / 7 |
| One serial manipulator | all but K8b | 6 / 7 |
| Manipulator tips the opened box; no dock | K1b, K2b, K3b, K5b, K6b (K4b cradle, K8b tilter) | 5 / 7 |
| **Heated turning position** | K1b, K2b, K4b, K5b, K6b (K3b drum) | 5–6 / 7 |
| Plating by turning the plate (polar) | K1b, K2b, K4b, K5b, K8b | 5 / 7 |
| Press-peel / rice in the skin for banana and avocado | K1b, K2b, K5b, K6b (+K9) | 4 / 7 |
| Bought push-dicer grids in a press | K1b, K5b, K8b (+K9) | 3 / 7 |
| Washer for ware inside the cell; ware and dishes in one washer | 6 / 7; K1b, K6b (+K9) | — |
| Household hob as bought with interface board | K2b, K3b, K8b (+K9) | 3 / 7 |
| Oven outside the cell, served by the transport | K1b, K2b, K4b, K8b | 4 / 7 (rejected here) |
| Contact-free X labyrinth; Y band facing up in a gutter | K3b, K6b | 2 / 7 |
| Wash with ≥ 82 °C for 60 s for class R | K2b, K6b, K8b | 3 / 7 |
| Disher for patties; gauge-ring rolling pin | K1b, K4b, K8b; K2b, K4b, K5b | 3 / 7 each |

---

## 1. Design principles

### 1.1 Principles (binding for K9b)

| # | Principle | Source |
|---|---|---|
| P-1 | **Six motion actuators, no more**: one hand (X, Y, Z, roll) and one turning hub (T, S). Doors, drawer, lids, flaps, egg fixture, press, pincers are passive or worked by the hand or by the diner | C5 S-min, K2b, K5b, K6b |
| P-2 | **The gripper is the roll axis**: every item carries one bayonet stub; the hand pushes the canned roll sleeve onto it and turns 60° | K1b |
| P-3 | **No seal at the wrist, none above food**: X contact-free labyrinth, Z band facing the wall, Y band facing up into a gutter, roll and hub canned | K1b, K3b, K6b, K8b |
| P-4 | **All force and speed at one hub**: stirring, kneading, pressing, blending, slicing, spin-spreading, salad spinning on T or S; the hand supplies position, ≤ 400 N push and ≤ 10 Nm roll | K2b, K8b |
| P-5 | **Everything that touches food is loose ware**, washed in the one well; the well is also the closed clean store for big ware between meals | K6b, K1b, K9 P-1 |
| P-6 | **Household appliances as bought** (#28): domino hob, countertop combi-steam oven, dishwasher wash parts, 30 L water heater, hob-extractor fan; only their control boards are interfaced | #24, #28 |
| P-7 | **Merge stations**: one wet point (rinse cup: drain, tap, jet gate), one waste point (chute with blade post), one washer (well) | K6b, K1b |
| P-8 | **Beside, never under**: nothing static above the hob; the oven door opens over the hub only when the hub vessel is lidded or empty; bands never face an open vessel | K1b, K9 P-2 |
| P-9 | **Slide, don't lift**: deck, domino glass, hub glass and well lid flush; heavy vessels slide | K6b |
| P-10 | **Recipe routes before mechanisms**: cook in the skin and rice; spit paring; blanch and slip; disher; raft; rack pair; pan pair; braise on the hob | C1 §10.3, K9 P-5 |
| P-11 | **Authentic result (#27)**: no texture-changing aid; every method is one a home cook uses | #27 |
| P-12 | **Hygiene C2 R-1…R-12**: moist-heat disinfection logged (class R hold ≥ 82 °C / 60 s), red/green ware, one-way flow at the well, grit to a strainer, fat to the fat cup | K9 P-8, K6b |
| P-13 | **The human does what people do at a table anyway**: pull the hatch drawer, slot used plates into a rack, plate from serving dishes if the family-style mode is chosen | DEC-6, Q8, Q9 |
| P-14 | **Degrade and continue**: every food-process failure has a redo, a fallback route or "serve without, tell the user" | K9 P-9 |

### 1.2 What is deliberately left out, and what it costs

| Left out | Saves | Costs (meals / quality / time) |
|---|---|---|
| Wrist actuator (chuck, jaws, EPM) and the roll lip seal | 1 actuator, 2 seals, slip ring | roll torque limited to ≈ 10 Nm: no screw cassette on the roll; novel grip (N1) |
| Oven-door motor, hatch-drawer motor | 2 actuators | ≈ 20 s of hand time per oven use; the diner pulls the drawer |
| Third and fourth hob zones (domino instead of 4-zone hob) | 300 mm width | 3 hot positions + oven; menus with 4 hot pots run the 4th in the oven or serialise (+5–10 min [E]); no meal lost |
| Second turning position | 1 actuator, 1 coil | a second stirred dish is stirred by the hand in intervals (K9 method) |
| Drum (K3b), belt and mats (K3b, K4b), press column (K4b, K5b, K6b) | 2–4 actuators, 1–3 seals each | no bulk rumble-peeling, no lay-down; pressing output is swept by the hand; thin wrappers (AS08, IN07) stay out as everywhere |
| Cup scale S0, dock, egg module | 1 station, 2–6 actuators | small doses by levelled spoon (±10 % [E]), as a cook doses |
| Knurled peeling drum | 1 ware item | raw-peeled potatoes on the spit: ≈ 4–5 min hand time per kg |
| Plate dispensers, separate clean-ware cabinet over the hob | 2 bought units, 0.15 m³ | plates on carriers; plates warmed in the oven |
| Separate drain gully, jet gate, produce sink | 2 stations | none: merged in the rinse cup |
| T-lathe trepanning and parting (K8b) | — | apples cored by tube, cabbage quartered and sliced on the disc |
| Thin-wrapper sheeting, strudel stretching, orange segments | a sheeting station | AS08, IN07, CK12 out (as K9); DS10 in rounds (c) |
| Kohlrouladen whole leaves | — | DM12 at risk (as K9) |

---

## 2. The machine

### 2.1 Whole-machine width (PHY-004 minimum configuration)

| Module | Machine X | Width | Contents |
|---|---|---|---|
| Cold storage | 0–1200 | 1200 | household fridge + freezer shells (#28, ≈ €1,000), box positions per C4 3.1 |
| Ambient storage | 1200–1850 | **650** | shelving and box racks (K9 had 450; C4's realistic figure wanted ≈ 900) |
| **Cell** (S column 600, domino 300, hub 300, oven-and-well column 550) | 1850–3600 | **1750** | everything of meal preparation, cooking, serving, dish return and washing |
| **Total** | | **3600** | ≤ 3600 met; the cell is **200 mm narrower than K9's like-for-like 1950**; the 200 mm go to ambient storage. Option: 4-zone hob instead of the domino (+300 mm, ambient back to 350) |

Height 2200 (#11): plinth 0–100, services and well 100–870, deck 870, work space 870–1950, X box in the
rear lane at z 1900–2000, transport gallery z 2000–2200 over the whole length (C4 R-9). Depth 600 (inner
580; mast lane y 0–120).

### 2.2 Front views

Whole machine, fronts on:

```
 X  0                       1200          1850                                            3600
 2200 +-------------------------+-------------+---------------------------------------------+
      |                transport gallery z 2000-2200, ceiling ports into each module      |
 2000 +-------------------------+-------------+---------------------------------------------+
      |                         |             | box shelf | (glazed cell door, interlocked) |
      |  COLD STORAGE           |  AMBIENT    | + tool    |              |  OVEN behind    |
      |  fridge + freezer       |  STORAGE    | cabinet   |              |  the door       |
      |  shells, box positions  |  shelving,  |-----------+              +-----------------+
      |                         |  box racks  | cell work space (no human access in use)  |
  870 |                         |             |[HATCH DRAWER]  pulled by the diner        |
      |                         |             |[bin drawer]       service fronts          |
  100 |                         |             |                                           |
    0 +-------------------------+-------------+---------------------------------------------+
```

Cell, front door removed (machine X):

```
 z (mm)
       1850            2450      2750      3050                     3600
 2000 +===== X box (rear lane y 0-120): belt axis, labyrinth slot, mast travel X 1890-3530 ====+
 1950 | S column       |  free    | oven-load| OVEN  countertop combi-steam,    |
      | box shaft and  |  air,    | corridor | ~25-32 L, turned: mouth faces -X, |
      | shelf z 1550   |  extrac- | (kept    | width <= 460 along y [U]          |
      | + TOOL CABINET |  tion    |  free)   | z 1550-1950; door opened by hook  |
 1450 | (rear flaps)   |  plenum  |          +-----------------------------------+ 1550
      |----------------|  at the  |          |  free arm space (roll axis<=1240); |
      | free arm space |  rear    |          |  the mast passes behind the oven   |
      |                |          | anchor   |                                    |
      |                |          | post  o  |  well lid = bench (front hinge,    |
  870 |[hatch drawer]  |[ DOMINO ]|[HUB coil]|   swings up against the front)     | deck
      |=rinse cup, chute+blade post (rear)===|====================================|
      | bin drawer 20 L| hob body | T + S    | WELL 420 x 440 x 450 (z 420-870)   |
      | drains, valves | interface| motors,  | DW wash parts, softener, dosing,   |
      |                | power    | ring-coil| 30 L hot-water store 88 C, pumps   |
  100 |                | manager  | generator|                                    |
      +----------------+----------+----------+------------------------------------+
     1850             2450       2750       3050                                3600
```

### 2.3 Top view of the cell at deck level (z 870)

```
 y 580 +--------------------------------+-----------+o------------+----------------------------+
 front | HATCH DRAWER 560 x 280         | HF  Ø 210 |^ anchor post| WELL mouth 420 x 440       |
       | heated tray, 2 plates or the   | 3.4 kW    | (2770,560)  | lid = bench 460 x 460,     |
       | plate carrier; pulls out 300   | (pots)    |  HUB  T/S,  | flush, hinged at front edge|
 y 300 |--------------------------------|           |  ring coil  |                            |
       | RC Ø150 | CHUTE 120x200 | EGG  | HR  Ø 180 |  Ø 280,     |   (oven above, z 1550-1950,|
       | rinse   | flap, blade   | fix- | 2.0 kW    |  pocket at  |    y 120-580)              |
       | cup     | post on rim   | ture | (pans)    |  (2900,440) |                            |
 y 120 +--------------------------------+-----------+-------------+----------------------------+
       |===== mast lane y 0-120 (mast 60 x 120 hangs from the X carriage); rear fume slot y 70-110 ======|
 y 0   +-----------------------------------------------------------------------------------------+
      1850                            2450        2750          3050                         3600
 RC rinse cup: funnel with 2 mm strainer basket, tap spout (cold / 45 C), 4 jet nozzles (85 C) for the
 sleeve, turbidity sensor, drain.  Chute: dry waste to the bin; blade post on its rear rim.
```

The domino (288 × 520) sits flush at y 60–580; its rear 60 mm lie under the mast lane where no vessel
stands. **Height rule (idea 107):** the rear zone takes low vessels (pans, rack pair; ≤ 80 mm with contents),
the front zone takes pots whose stub stands ≥ 100 mm above the deck; so the hand always reaches a stub from
behind, passing over a low pan at ≥ 60 mm clearance.

### 2.4 Kinematics, actuators and dynamic seals

| # | Actuator | Type and rating [E] | Travel | Seal / penetration |
|---|---|---|---|---|
| 1 | **X** | toothed-belt linear module with two profile rails in the dry X box, closed-loop stepper 400 W, 1.2 m/s | 1640 (mast X 1890–3530) | **none**: carriage passes a vertical labyrinth slot (interleaved lips, purge air outward, gutter below) (K3b, K6b) |
| 2 | **Z** | ball screw 16 × 10 with brake on a hanging mast 60 × 120 (inner torsion tube), foot at z 950, 400 N | 900 (arm z 1000–1900, roll axis z 700–1600; under the oven arm ≤ 1540, roll axis ≤ 1240) | **sealing band 1** on the mast's rear face, towards the wall; drip lip into a cup at the foot |
| 3 | **Y** | belt drive inside a closed arm tube 70 × 70 × 620 cantilevered from the Z carriage on a **single-point load cell** (30 kg, ±5 g) | 450 (wrist y 130–580) | **sealing band 2** on the arm's top face inside a 15 mm gutter sloped 3° to the mast |
| 4 | **Roll** | closed-loop stepper + 20 : 1 planetary in a sealed static housing at the arm tip, hanging on a **300 mm drop link** (the arm stays ≥ 300 mm above the work); **canned magnet coupling** (inner NdFeB rotor in a welded 0.5 mm 1.4404 can, outer SmCo sleeve rotor on two PEEK bushes); two Hall sensors measure coupling lag = torque | continuous, 0–150 rpm, 10 Nm rated, slips at ≈ 15 Nm | **none** (canned, static can) |
| 5 | **T** | NEMA 34 stepper + 10 : 1 planetary under the deck; driver magnet ring outside a drawn pocket Ø 120 × 60; **T plug** (magnets in a welded can, PEEK bush, four lug slots) flush with the glass | 25 Nm (30 peak), 0–500 rpm | **none** |
| 6 | **S** | 600 W BLDC coaxial through the hollow T shaft; inner rotor in a thimble Ø 40 rising from the pocket centre | 1.5 Nm, 0–6000 rpm | **none** |

**6 motion actuators** (C5 ≤ 10; K9 had 7 in the cell, 9 with oven door and hatch drawer). **2 dynamic seals**
(C5 ≤ 5; K9 4). Not counted: well circulation and drain pumps, 2 dosing pumps, ≈ 8 solenoid valves,
extraction fan, purge fan, 3 induction generators (2 inside the domino, 1 for the hub coil), the hatch
solenoid lock, the cell-door guard lock.

**What the hand can do**: lift ≤ 6 kg with the centre of mass ≤ 160 mm in front of the sleeve (9.4 Nm of
bending on the PEEK bushes, carried by the arm tip); roll ≤ 10 Nm (pour, flip pan pair and rack pair, turn
the spit, close pincers); push 400 N down (Z), 150 N in Y, 200 N in X; weigh any held item ±5 g by loss in
weight. It cannot yaw: knives cut with the blade in the y–z plane, and the board turns on T for cross cuts
(polar work, K2b/K8b). Heavy full vessels (braiser ≈ 5 kg) are slid on the flush deck rather than lifted.

### 2.5 The grip: bayonet stub on the canned roll sleeve (N1)

* **Stub** (on every item, ware side): round bar Ø 22 × 40 along −y with two radial pins Ø 5 and a moulded
  PEEK detent collar, on a stand-off above a **drip collar**; welded (TIG or laser) to bought vessels at the
  rear rim, to GN trays at the rear long side near the −X corner, to tools at the top of their stem; moulded
  into the storage boxes (C4 R-2 as amended: stub instead of flat tang).
* **Sleeve** (on the roll output, permanent, LRU): Ø 34 rotor can with a Ø 22.5 bore and two J-slots.
  **Grip**: approach along +y, push the stub in 35 mm, roll +60° while the item resists by its rest (tool
  rails and well combs have flats; vessels resist by weight on a flat surface ≥ 2 Nm), the detent clicks
  [E: 1.5 Nm]. **Release**: set the item down, roll −60° against the rest, withdraw −y. In the air the item
  turns with the sleeve, so no relative torque arises; the spit is always driven in the locking direction.
* **Check**: the arm-root load cell must show the item's expected mass and moment (±10 %), the roll encoder
  the 60° lock angle, the camera the item; a failed check means set down and retry (C3 X4 case).
* **Pincer tools** (spatula-tongs, disher sweep, egg-fixture lever): the body locks in the sleeve; the moving
  jaw's lever rests against a **fixed reaction tab** on the roll housing; turning the roll 15–40° closes the
  jaw (K1b). A pincer tool is never rolled for pouring.
* **Rinse**: after every soiled grip the sleeve and tab are sprayed for 3–10 s at 85 °C in the rinse cup
  (10 s after class R), before any clean item is touched (software interlock, K6b).
* **Fallback** (if E2 fails): K6b pin jaws on a lip-sealed roll unit (+1 actuator, +2 seals → 7 and 4,
  still inside C5's limits).

### 2.6 Stations

| Station | Where (machine X; y) | What it is | Actuators | Fixed food contact? |
|---|---|---|---|---|
| **Hatch drawer** | 1870–2430; y 300–580; deck level | drawer with a removable stainless tray (ware), heated 150 W; holds 2 plates, the plate carrier or 2–3 serving dishes; the diner pulls it 300 mm out through a flap when the green lamp is on; solenoid-locked while the hand works in the S column (K6b) | 0 | no (tray is ware) |
| **Rinse cup (RC)** | 1880–2030; y 130–290 | funnel Ø 150 × 120 with a tanged 2 mm strainer basket and turbidity sensor; tap spout above it (cold / 45 °C, flow meter ±3 %); four fan jets 85 °C in its rim for the sleeve; plate pre-rinse; cooking water and produce wash water are poured here | 0 | strainer (ware) |
| **Chute + blade post** | 2040–2240; y 130–290 | opening 120 × 200 (long along y) with a spring flap, straight into a 20 L bio bin in a plinth drawer (C2 R-8); the **blade post** (ware) stands on its rear rim: one blade with sprung depth shoes 1 / 2.5 / 5 mm and a fine rasp edge (K1b, K6b) | 0 | blade post (ware) |
| **Egg fixture** | 2250–2430; y 130–290 | passive cradle: bottom strike, hinge-open halves on one loose pin, slotted saucer, 2 mm strainer; per-egg camera check (G-assembly 7.2/7.3, K9) | 0 | no (all parts are ware) |
| **Domino hob** | 2450–2750 | household 30 cm induction domino, front Ø 210 (3.4 kW with boost), rear Ø 180 (2.0 kW); touch board replaced by an interface board (COK-023, K9 Q6), own power limiter set to 3.4 kW | 0 | glass under ware only |
| **Hub (T/S) with ring coil** | 2750–3050; T at (2900, 440) | glass-ceramic disc Ø 330 with a Ø 130 hole, the drawn pocket gasketed into it (downdraft-hob nozzle practice, K2b); OEM **ring induction coil** Ø 135/280, 2.5 kW, own generator, IR and NTC base sensors; **3 load cells** under the station frame (10 kg ±2 g); pocket drained to the rinse line | 2 (T, S) | glass under ware; pocket under the T plug |
| **Anchor post** | (2770, 560) | stainless post Ø 25, z 870–1200, fork at z 1000–1180; takes the reaction arms of the hung scraper, kneading roller and press cup (K2b) | 0 | no |
| **Well (washer and clean store)** | 3090–3510; y 130–570 | see 2.8 | 0 (pumps) | — |
| **Oven** | 3070–3550; y 120–580; z 1550–1950 | see 2.7 | 0 | ware only |
| **Box shelf** | 1870–2160; y 300–580; z 1550, in a shaft under the ceiling port | the transport lowers an **opened** box (lid removed at the lid station outside, C4 R-4) or a GN 1/3 carrier with an opened STOW pack (C4 R-5) through the ceiling port; two places (one buffer, TRN-008) | 0 (port belongs to transport) | no |
| **Tool cabinet** | 2160–2450; y 120–580; z 1450–1950 (0.07 m³) | closed stainless cabinet entered from the rear lane through spring flaps; filtered air at slight overpressure; insulated soffit sloped to the rear gutter; holds 3 tool racks, press-cup kit, S kits, small fixtures (plate carriers live in the cold oven, glass and cutlery baskets in the well) | 0 | no |
| **Splash-zone cleaning** | X box face, cabinet soffit | fixed fan-nozzle rail (45–60 °C, detergent), fan dry; rear fume slot y 70–110 behind the domino and hub with a bought hob-extractor fan and baffle filter (ware) to the shared condenser (C4 R-12) | fans only | — |
| **Cameras** | X box face | two heated windows with white and UV-A light: one over S column and hub, one over domino and well | — | — |

### 2.7 Oven integration (#24, #28)

* **Appliance**: countertop combi-steam oven, 25–32 L, external ≈ 460 (along y) × ≤ 480 (along X) × ≤ 400
  (z) [U], ≈ €500–700. Mounted at z 1550–1950 in the O column, **turned with its mouth facing −X**, in front of
  the X box: because it is ≤ 460 mm deep in y, **the mast passes behind it**, so the space under it (the well)
  is reached from above. Fallback if no model fits (E1): the oven sits y 20–580, the mast stops at X 3040,
  and the well becomes K9's side-loading chamber under the oven (+0 actuators, slower loading).
* **Modifications** (as few as possible): (1) an interface on the control board (start, mode, temperature,
  probe input) — COK-023; (2) the water tank fed by a float valve from the cold line, or the tank refilled by
  the hand at the rinse-cup spout if it is reachable from −X. **No door motor.**
* **Door**: the hand opens it with the **hook rod** (a stem tool with a hook): a drop-down door is pulled down
  to the horizontal and then serves as the loading shelf at z ≈ 1560 over the hub; a side-hinged door is swung
  95° along the front wall. Closing by pushing with the rod. Rule (P-8): the door opens only when the hub
  vessel below is lidded or the hub is empty; the door's lower edge has a drip gutter.
* **Loading**: GN 2/3 trays carry their stub at the rear long side near the −X corner; the hand slides the
  tray in +X over the open door onto the oven's rails until the wrist reaches the mouth, releases, and pushes
  the last 60 mm with the hook rod. Unloading the reverse; a hot tray is set on the well lid (bench).
* **Cleaning**: food is always in ware; the cavity sees spatter and steam; the oven's own steam-clean runs
  after roasts; a burnt-on spill is wiped by the human (Q12, as K9).

### 2.8 The well: one washer for ware and dishes, and the clean store (K6b + K1b)

* **Build**: welded 1.4404 tub, inner 420 (X) × 440 (y) × 450 deep (z 420–870), double wall with 20 mm
  insulation, coved corners, floor sloped to a sump with a 2 mm strainer and the donor's micro-filter. Wash
  parts of a **bought slim household dishwasher** (€400 donor: circulation pump, 2 kW heater, filter,
  softener, two dosing pumps, control board re-used): two fan-nozzle rows on the long walls and one bottom
  spray arm. Rinse water from a **bought 30 L under-sink heater at 88 °C**, charged only while the oven is
  off (0 W of wash heating during cooking, K6b).
* **Lid = bench**: 460 × 460 insulated sandwich, flush with the deck, carries GN trays and the breading
  line; hinged at its **front** edge on open lift-off pins; the hand lifts the rear edge by its stub (15 N)
  and swings it to the vertical against the front wall, where a gas strut holds it as a splash screen
  towards the cell door. A left or rear hinge was rejected: the raised lid would close the 210 mm window
  (z 1330–1540) through which the arm passes under the oven. It rests in a drained channel; no seal.
* **Clearance rules** [C]: with the mast behind the oven (X > 3030) the arm stays at z ≤ 1540 (roll axis
  ≤ 1240 on the 300 mm drop link); an item on edge hangs ≤ 360 mm below the axis, so its bottom clears the
  deck (≥ 880) before it is lowered. In the well the stubs sit in combs at z 700 (round ware: ± 140 mm about
  the axis, top ≤ 840 < lid 870) and z 800 (GN, carriers: hanging below the axis, bottom ≥ 446 > floor 420);
  the arm is then at z 1000–1100, above the deck. To load the oven the mast stays at X ≤ 3030, so the 70 mm
  arm clears the oven body at X 3070; roll axis ≤ 1600 reaches the oven rails at z ≈ 1620 [U: model].
* **Loading**: items are rolled 90° so they stand on edge in y–z planes and lowered in; their stubs drop
  into **fork combs with flats** on the rear wall (round ware at z 700, GN, carriers and racks at z 800), the
  far edge into a front comb. 10 slots at 40 mm; a pot takes 4. Typical load: 2 pots + 2 pans + 2 racks of
  tools, or 2 plate carriers (8 plates) + glass basket + cutlery basket + 2 GN trays.
* **Programmes** [E]: (a) **ware/dish** 12–15 min: pre-rinse, 55–60 °C wash, **final rinse ≥ 82 °C held
  60 s (A0 ≥ 90, logged on the coldest item during validation)**, fan dry with the lid ajar to the
  extraction; (b) **turnaround** 6–8 min for a red → green swap during the meal; (c) daily hot self-clean,
  weekly ≥ 70 °C self-clean (HYG-040). Tank water is never reused between loads.
* **One-way flow**: the hand empties clean items first (to the cabinet, the cold oven, the domino), then
  loads soiled ones; no clean item waits outside while soiled items stand in the well. Dirty dishes wait in
  the hatch drawer, not in the cell.
* **Clean store** (K1b): after the last load of the day the well keeps the big ware (pots, pans, braiser,
  bowl, boards, glass and cutlery baskets) closed and dry until the next meal; GN trays and the plate
  carriers live in the cold oven (where the plates are also warmed); tools, S kits and press cup in the tool
  cabinet. At the start of a meal the hand takes out everything the menu needs
  **before any food is opened** (C2 R-6).
* **Per meal** (4 persons, plated): 4 loads (3 ware, 1 dishes) → all clean ≈ 50–60 min after hand-over [E]
  (PERF-005 M 90 min met; K9 70–90 min). 2 persons: 2–3 loads, ≈ 35 min.

### 2.9 Hob, hub and the phase plan

| Phase | Loads | ≤ kW |
|---|---|---|
| L1 | domino (own limiter 3.4 kW); controls 0.15 | 3.55 |
| L2 | hub ring coil ≤ 2.5 (≤ 1.9 while S runs); T, S, gantry 0.3 average (S 0.6 for ≤ 60 s); fridge, freezer 0.3 | 3.6 |
| L3 | oven ≤ 2.2 **or** well heater 2.0 **or** 30 L store 2.0 (one at a time); extraction 0.1; transport 0.2 | 2.5 |
| **Peak** | | **≈ 9.7** (K9 10.0) |

Three hot positions (COK-002 M): domino front, domino rear, hub; the oven is the fourth. COK-004 (4 L to
95 °C ≤ 11 min) on the domino front at 3.4 kW with the rear off: 1.34 MJ / (3.4 kW × 0.85) ≈ 7.7 min [C].
The ring coil is switched on only when a T-vessel (dog ring under its clad base) is detected on the plug;
the press cup, board carrier and spinner are never heated (software interlock and pan detection).

### 2.10 Ware list

B = bought, B+ = bought with a welded stub and drip collar, T = also a dog ring for the hub, C = custom
(laser-cut, bent, welded, turned; no FDM in food contact, #4). Red items are for class R.

| Group | Items | Pieces |
|---|---|---|
| Pots, pans, lids | frying pans Ø 280 × 50 tri-ply, hermaphroditic (hook tab + catch), B+ T ×2 (one red within a meal; either is the flip partner); pot Ø 220 × 150 (5 L) with basket B+; pot Ø 220 × 90 (3 L) B+ T; pot Ø 160 (1.5 L, also the 1-person braiser) B+; braiser Ø 280 × 100 (5.5 L) B+ T; lids Ø 280, Ø 220, Ø 160 and strainer lid Ø 220; lift-rack pair Ø 260 (GA-36) C ×2; kneading bowl Ø 280 (10 L) B+ T; red wash pot Ø 220 with dunk basket and 40 mm sediment zone | 16 |
| GN, oven, serving | GN 2/3-20 ×2 (tray pizza, sheets, bench); GN 2/3-65 + lid (lasagne, gratin, roast); GN 1/3-65 ×3 with lids (breading line, mise en place, hot-holding, **serving dishes**); loaf tin 30 cm with loose floor and paper liner; springform 26 with loose floor | 12 |
| Hub ware | boards PE-HD Ø 300 on a T carrier, red and green ×2; **press cup** kit (tube Ø 110 × 200 with Rd 28 × 6 screw base and PE piston; reaction arm; swivel spout collar); dies: push-dicer grids 6 and 10 (bought, welded rim), ricer 3 mm (also garlic in skin, press-peel, citrus); salad spinner basket; hung stirring scraper on a rim bridge; kneading roller with scraper | 11 |
| S ware | blender jug 2 L with fixed blade; cutter cup 2 L with feed-tube lid; rotors: chopping blade, whisk, adjustable slicing disc 1–6 mm and grating disc (bought food-processor discs on an adapted hub) | 6 |
| Stem tools (stub, drip collar) | chef's knife red / green; scalloped slicing knife; spatula-tongs red / green (pincer, one jaw a 0.6 mm turner blade, K6b); turner; ladle 100 mL; silicone spatula; balloon whisk; fork-spit; corer shank with tubes Ø 14 / 22 / 42 and ejector; plunger pitter; measuring spoon 1 / 5 / 15 mL with a sharpened edge (also the seed spoon); disher 60 mL (pincer sweep); wireless probe in a holder; rolling pin with gauge rings 1–10 mm; Spätzle slider (bought Spätzlehobel); plate cradle; hook rod 450; scraper-squeegee (glass blade one edge, rubber the other) | 20 |
| Fixtures | blade post with shoes; egg fixture (cradle, saucer, strainer); Rouladen comb cradle + 2 GA-20 raft forks; GA-14 carving trough with gauge plate; ravioli plate GN 2/3; hinged dumpling press; rinse-cup strainer basket; fat cup | 12 |
| **Food contact** | | **77 pieces** (K9 ≈ 99); **≈ 61 handled items** with lids, baskets, pairs and kits counted with their parent (K9 ≈ 66) |
| Second set (next meal within 30 min, PERF-005) | frying pan, 5 L pot, board, chef's knife, spatula-tongs | 5 (K9 8) |
| Carriers (no food contact) | plate carriers ×2 (4 plates on edge each, retaining bars), glass basket, cutlery basket, hatch trays ×2, tool racks ×3 (5 tools each) | 9 |

A 4-person meal takes out 25–35 items; a 2-person meal 15–25.

### 2.11 Serving and dish path

* **Plated mode** (default for 1–2 persons, option for 3–4): the plate carrier comes warm from the oven
  (60 °C, 5 min) to the bench; the **plate cradle** lifts one plate out of its slot, roll 90° lays it
  flat on the hatch tray, whose four ribs strip it; two plates side by side; components by ladle, turner,
  spatula-tongs; the green lamp lights, the diner pulls the drawer, takes two plates, pushes it back;
  the next two follow ≈ 1.5 min later [E] (SRV-009 3 min first to last: met if the first pair is taken).
* **Family-style mode** (default for 3–4 persons, Q9): food in 2–3 lidded GN 1/3-65 serving dishes plus the
  warm plate carrier in the drawer, in two drawer cycles; the household plates at the table. 4–6 events
  instead of ≈ 24.
* **Dish return** (DEC-6, Q8): the diner slots plates into the carrier standing in the drawer (as into a
  dish rack), puts cutlery into the basket and glasses into the glass basket, pushes the drawer in. The hand
  lifts the carrier over the chute and **rolls it 180°** (retaining bars hold the plates; scraps fall); the
  camera checks; carrier, baskets and the hatch tray go into the well; a clean tray is set in (SRV-027):
  ≈ 5 events (K9 ≈ 35).

### 2.12 Interfaces

| To | Interface |
|---|---|
| Storage and transport | ceiling port above the box shelf (shaft in the S column, shelf at z 1550, two places); opened GN 1/9–1/3 PP boxes with a **moulded bayonet stub** on the rear short side and a levelling edge on spice boxes; opened STOW packs upright in a GN 1/3 carrier with a stub; ≈ 20–25 box moves per 4-person meal; prepared intermediates and leftovers returned lidded in GN 1/3-65 via the shelf (#12, PRP-036) |
| Ingestion | none directly; peeled onions bought (#9) |
| Utilities | 3 × 16 A phase plan (2.9); cold water to the rinse-cup spout, the 30 L heater, the well and the oven float valve (EN 1717 break); one drain rated 95 °C (well, rinse cup); one extraction to the shared condenser |
| Human | hatch drawer (food out, dishes back); bin drawer (20 L, emptied about twice a week); detergent and salt for the well; oven cavity if soiled; service through removable fronts with the cell locked out |

---

## 3. Selection table

Criteria in the order of #20: **S** simplicity, **Hy** hygiene, **Co** coverage and food result, **R**
reliability, **Fit** system fit and cost. Conf. = confidence that it works as described (H / M / L).

| Function | Chosen mechanism | Source | Why it beat the alternatives | Conf. |
|---|---|---|---|---|
| Manipulator | Gantry X (labyrinth), Z (band to the wall), Y (band up in a gutter); bought linear modules | K9, K3b, K6b | **S**: bought modules, 3 axes; beat turret (K1b, custom slewing ring, open seam), pucks (K8b, 6 novel), SCARA (K4b), no-Y Wender (K2b: one-line layout, +width, no spit traverse) | H |
| Grip | **Bayonet stub on the canned roll sleeve**, locked by 60° roll | K1b | **S**: 0 actuators, 0 seals; **Hy**: no lip seal and no slip ring above food; beat EPM chuck (K9: power at a rotating face), pin jaws (K3b/K5b/K6b: +1 act, +2 seals), V-groove jaws (K2b) | M [U] |
| Tongs, disher, egg lever | Pincer tools closed by roll against a fixed reaction tab | K1b, K9 (roll-driven tongs) | **S**: no tool drive | M |
| Receive box | Opened box set on the box shelf by the transport; hand grips its moulded stub | K9, C4 R-4 | **S**: no dock (2–6 act.) | H |
| Receive sealed pack | Opened just in time outside the cell, upright in a GN 1/3 carrier | C4 R-5, K9 | **S, Hy**: no in-cell opener | M–H |
| Dose granular, powder, liquid | Tip the opened box by roll about a lip pivot; loss in weight at the arm-root load cell (±5 g); gain on the hub cells (±2 g) when the target is on T | K9, K2b, K3b | **S**: 0 act.; beat dock tilter (K8b), passive cradle (K4b) | M–H |
| Dose 0.2–5 g | **Levelled measuring spoon** (1 / 5 / 15 mL) against the levelling edge of the spice box | K1b, K2b | **S**: −1 station (S0); cook's own method; ±10 % [E] acceptable for salt and spices | M–H |
| Dose viscous, fats | Spoon or spatula from the opened pack; butter cut by the knife from the block | K9 | **S** | M |
| Dose pieces, meat, long goods | Box tipped onto a GN tray; picked by spatula-tongs or turner; spaghetti by the log-roll weir (GA-29) | K9 | **S, Hy** | M–H |
| Eggs | Passive egg fixture, per-egg camera, 2 mm strainer | K9, G-assembly | **S, R**: beat egg modules (3 act.) and press-struck crackers (K4b, K5b: need a press) | H |
| Wash produce | Red wash pot with dunk basket over a 40 mm sediment zone, filled at the rinse-cup spout, dumped into the rinse cup; leek cut first; leaves spun on T | K9 GP-W1, K6b | **Co** (grit physics), **Hy** (class R in ware), **S**; beat drum wash (K3b, +2 act.), well as sink (K8b) | H |
| Peel, core, stone (#25) | **Generic module §4**: spit on the roll against the blade post; press-peel through the ricer die; blanch-and-slip; cook in the skin; corers, pitter, cheek cuts | K9, K1b, K5b, K6b | **S**: 3 tool families, no single-purpose device; beat knurled drum (K9), T-lathe (K8b: T is busy cooking), rumbler (K3b) | M |
| Knife cuts | Knife held in the sleeve, draw cut by Y, chop by Z; board on T turned for cross cuts | K9, K8b (polar) | **S**: one blade direction, no yaw axis | M–H |
| Dice, rice, press | **Press cup on T**: T turns the screw, the piston rises, product passes the die on top and is swept into the swivel spout; bought push-dicer grids 6/10, ricer 3 mm; reaction arm on the anchor post | K8b, K5b (grids), K1b | **S**: 0 act., 0 seals, force loop in the cup; beat pull-down press (K5b: +1 act., +2 seals), swing press (K4b, K6b), lever dicer (K1b: 10 kg, big), roll-driven cassette (K9: needs 30 Nm roll) | M [U] |
| Slice, grate, shred | **Cutter cup on S** with bought food-processor discs (slicer 1–6 mm, grater); cabbage quartered and cored by knife first | K3b, K6b | **S, Co**: bought parts, household results; beat knife cage (K5b), belt guillotine (K3b), blade column (K4b) | M–H |
| Mix, knead | Bowl on T under the hung kneading roller and scraper, reaction on the anchor post (Ankarsrum) | all seven | **S, R**: one known principle for dough, mince mass, creaming | M–H |
| Blend, whip, purée, chop | Jug and cutter cup on S (canned, 6000 rpm) | K8b, K2b, K9 | **S, Hy**: no seal; beat stick blender held by the hand (K5b: battery, handling) | M–H |
| Cook with stirring | **Heated hub**: T-vessel on the ring coil turns slowly under the hung scraper; second stirred dish on the domino stirred by the hand in intervals | K2b, K5b, K6b, K1b; K9 | **Co, R**: continuous stirring for risotto, polenta, béchamel, Rotkohl; −6–12 events per stirred meal; beat turning carrier rings on a custom hob (K6b, K1b), drum (K3b) | M [U coil evenness] |
| Hob work | Bought household 2-zone domino (3.4 + 2.0 kW), height rule front / rear | K3b | **S, Fit**: −300 mm against a 4-zone hob; 3 hot positions with the hub | M–H |
| Fry and flip (pancakes, Rösti, omelette) | **Hermaphroditic pan pair**, ≤ 30 mL fat; batter **spin-spread** on the heated hub | K1b, K6b, K3b; G-assembly 7.1 | **S**: no separate flip pan, no frying book (K5) | M–H |
| Breaded cutlets | **Rack breading** (cutlet stays on the wire rack from flour to pan) + lift-rack pair in 220 mL fat (3.6 mm) | K5b, GA-36 | **Co, S**: no grip on the crust, real shallow-frying | M–H |
| Patties | **Disher** portions (pincer sweep) dropped into the pan and pressed flat by the turner | K1b, K4b, K8b | **Co** (traditional shape), **S**; beat orifice extrusion (K9: cylinders) | M–H |
| Roll dough, sheets | Rolling pin with gauge rings pushed by Z (≤ 400 N) and moved in Y on a floured GN tray | K9, K2b, K4b, K5b | **S**: thickness from rings; beat ramp roller (K3b: needs 30 Nm roll), mats (K4b) | M |
| Stuff, fold | Ravioli plate (square parcels), hinged dumpling press closed by Z | K9 | **S**: passive ware for IT17, DM33, CK17 (mandated c) | M |
| Spätzle | Bought **Spätzle slider** moved in Y over the boiling pot | new | **S, Co**: the household tool; beat Spätzle die in a press | M–H |
| Rouladen | Board on T; mustard by spatula stopping 35 mm short; dry floured flap; side folds; fork-and-turner roll; comb cradle; GA-20 raft; braised lidded on the domino | K9, all seven | **Co** (fond first, secured rolls), **S** | M |
| Bake, roast, steam | Bought countertop combi-steam oven, turned, high, door opened by the hook rod | K9, K3b, K5b | **S**: −1 act. (no door motor); **Fit**: no oven column served by the transport | M [U fit] |
| Drain | Basket lifted out of the 5 L pot and held to drip; waste water poured through the strainer lid into the rinse cup | K9, K6b | **S** | H |
| Transfer | Pour by roll about the lip (X, Z follow); empty with the silicone spatula; weigh by loss in weight | K9, K2b | **S** | H |
| Carve | GA-14 V-trough with gauge plate on T, scalloped knife drawn by Y; braises cut hot at 8–10 mm; poultry as parts | K9 | **S, Co**; beat parting on T (K2b), knife cage (K5b) | M–H |
| Core temperature | Wireless probe in a stem holder | K9, all | **Co** | H |
| Hot-holding | Oven 60–80 °C vented; lidded pots on keep-warm; heated hatch tray | K9 | **S** | M |
| Plate, portion | Plate cradle lays plates flat on the heated hatch tray; ladle, turner, tongs, ring; **or family style** in lidded serving dishes | new, K9 | **S**: no plate dispenser, no plate fork; family style removes plating | M |
| Hand-over | Hatch drawer pulled by the diner, solenoid lock | K6b | **S**: −1 act. vs K9 | H |
| Dish return | Diner slots plates into the carrier; carrier rolled 180° over the chute; carrier into the well | new | **S**: ≈ 5 events instead of ≈ 35 | M |
| Wash ware and dishes | **Top-loading well** with bought dishwasher wash parts and a 30 L 88 °C store; 82 °C / 60 s final rinse | K6b, K1b, K2b, K8b | **S**: 0 act., top-loading suits a Z axis; **Hy**: A0 ≥ 90 logged; beat K9's side-loading chamber, wash lift (K2b), separate dishwasher via port (K5b) | M |
| Clean store | Big ware closed in the well between meals; GN in the cold oven; small items in the tool cabinet | K1b, K3b, K6b | **S, Fit**: no ware tower, no cabinet over the hob | M–H |
| Gripper rinse | Four 85 °C jets in the rinse-cup rim | K6b, K2b, K9 (jet gate) | **S**: merged with the drain | H |
| Waste | Chute with flap to a 20 L bin; strainer baskets tipped into it; fat to the fat cup | K9, C2 R-8 | **Hy, S** | H |
| Weighing | Single-point load cell at the arm root; 3 load cells under the hub | K1b, K2b | **S**: two cells weigh everything; no wrist cell, no S0 | M–H |
| Cell cleaning | Fixed nozzle rail, per-meal hob and deck rinse with the scraper-squeegee, fan dry ≤ 60 min | K9, K6b, C5 A4 | **S, Hy**: no lance | M |
| Fumes | Rear slot behind domino and hub, bought hob-extractor fan, baffle filter (ware) | K6b, K9 | **S, Hy** | M |

---

## 4. Generic produce module (DECISIONS #25, PRP-039)

"Take the skin off and remove the stones, seeds and cores" is done with **three mechanisms**, chosen per
item by firmness and shape, not by its name: **(1) the spit on the roll against the blade post**, **(2) the
press cup with the ricer die ("press-peel": skin and stone stay, flesh passes)**, **(3) one family of tube
tools** (corers Ø 14/22/42, plunger pitter). Everything else (knife, spoon edge, pot, basket, spinner) is
ware that exists anyway. No single-purpose device. All work runs over the chute or the rinse cup, so peel
and cores go straight to waste. The camera checks every piece: skin residue ≤ 5 % of the surface, no stone
or core fragment > 2 mm (else a second pass or the knife).

### 4.1 The mechanisms

| # | Mechanism | How it works | Parts |
|---|---|---|---|
| G1 | **Pare on the spit** (firm, roughly convex or long) | The item lies in the **stab nest** (silicone-lined V cup with an end stop, part of the blade-post fixture); the hand pushes the 3-tine fork-spit in pole to pole along +y (top and tail cut first by knife). The roll turns it at 30–120 rpm, always in the bayonet's locking direction; Y traverses it past the **blade post** on the chute rim; Z presses it on with 5–20 N (coupling lag = cut torque). The post has one blade with three sprung depth shoes: **1 mm** (thin skin), **2.5 mm** (tough skin, onion tunics GP-11), **5 mm** (pith and rind à vif GP-Z4), and a fine rasp edge for zest (GP-Z1). Second pass offset 60° where the camera sees skin | fork-spit, blade post with stab nest |
| G2 | **Press-peel** (soft flesh, or cooked) | Item halved (avocado round its stone, banana in its skin cut in 3, mango cheeks, kiwi halves) or cooked whole (potato in skin, pumpkin roasted in skin), laid in the press cup **skin side down on the piston**; T drives the piston up; the flesh passes the ricer die (3 mm) or a dicer grid (10 mm for cubes) and is swept off into the spout; the skin (and the avocado stone, if left) stays as a cake on the piston and is tipped into the chute | press cup, ricer die, grids |
| G3 | **Blanch and slip** (thin skin over soft flesh) | cross scored by the knife point, 20–40 s in boiling water in the pot basket, cold bath at the spout, skins rubbed off in the spinner basket on T at 60 rpm with water (K9) | pot basket, spinner |
| G4 | **Cook in the skin** (tubers, beets) | boiled in the skin; then riced (G2, skins stay) or slipped by the spatula-tongs after a cold bath | pot, press cup |
| C1 | **Tube corers** Ø 14 / 22 / 42 with ejector | item stalk-up in the stab nest turned upright (or on the board on T), corer pushed down by Z (≤ 300 N); T oscillates ±30° under a pepper plug (GP-61); core ejected over the chute | corer set |
| C2 | **Halve and scrape, cheek cuts** | knife cuts parallel to the seed plane on the board on T; the 15 mL spoon's sharpened edge is drawn along the cavity by Y; pepper four-cheek cut (GP-62) with T turning 90° between cuts; cheeks round mango and clingstone stones | knife, spoon |
| C3 | **Plunger pitter** | fruit in the ring seat of the stab nest, plunger pushed by Z | pitter |

### 4.2 Produce routes (generic; most of the PRP-039 list and the corpus)

| Produce | Route | Time [E] | Conf. |
|---|---|---|---|
| Potato, raw-peeled (Salzkartoffeln, gratin, Rösti) | G1, 1 mm shoe, pole to pole; eyes ≤ 5 % left (GP-P2) | 25–30 s each; 1 kg ≈ 4–5 min | M–H |
| Potato for mash, Bratkartoffeln, salad | G4 then G2 (riced, skins stay) or slipped | 0 hand time while boiling | H |
| Carrot, parsnip, cucumber, courgette | G1, 1 mm shoe, spit in the thick end; seeds of cucumber and courgette by C2 | 20–40 s | M |
| Kohlrabi, celeriac (halved), beetroot (raw), butternut | G1, 2.5 then 5 mm shoe, two passes; loss 20–30 % | 60–90 s | M |
| Beetroot, celeriac for mash | G4 slip or G2 | — | H |
| Apple, pear | G1 1 mm, then C1 Ø 22 (or wedges and core by knife on the board) | 30 s | M–H |
| Orange, lemon | zest: rasp edge; peeled à vif: G1 5 mm; juice: pared halves through the ricer die (G2) | 15–30 s | M–H |
| Kiwi | G1 1 mm (whole) or halves through G2 | 15 s | M |
| Mango | cheeks cut beside the stone (C2), cheeks skin-down through grid 10 (G2 cubes) or ricer (pulp) | 60 s | M [U] |
| Avocado | halved round the stone by knife with T turning 360°, twisted apart by the tongs (K8b); halves with or without stone skin-down through ricer (guacamole, MX06) or grid 10 (cubes) | 60 s | M [U] |
| Banana | cut in 3 pieces in the skin, slit lengthwise by the knife point, pieces skin-down through the ricer (CK16 banana bread); slices for fruit salad (DS10, BF01) only by the knife-ring option (idea 83) | 30 s | M [U] |
| Pineapple, melon | top and tail, G1 5 mm (pineapple), melon halves on the board: C2 scrape, skin cut by knife round the turning half on T; pineapple core by C1 Ø 42 | 2–3 min | L–M |
| Pumpkin (Hokkaido) | halved by knife on T, seeds by C2, roasted in skin, flesh by G2 (soups) or eaten with skin | 2 min | M |
| Tomato, peach, apricot, plum | G3; stones by C3 (freestone) or C2 cheeks; tomato scar by C1 Ø 14 | 1–2 min per batch | H |
| Cherry, olive | C3 | 3 s each | M |
| Pepper | C1 Ø 42 plug (stuffing) or C2 four cheeks | 10–15 s | H |
| Onion | bought peeled (#9) baseline; upgrade: top and tail by knife, G1 2.5 mm shoe slit and tunic wiped on the spit, camera | 40 s | M (upgrade) |
| Garlic | cloves pressed **in the skin** through the ricer die (GP-17); skin cake to the chute | 30 s per 4 cloves | H |
| Ginger | G1 with the blunt rasp edge as a scraper, then grated on the S disc | 30 s | M |
| White asparagus | G1 along the spear, 1 mm shoe, from below the tip | 20 s each | L–M (SD19, SP09 class c) |
| Cabbage (red, white) | outer leaves off by knife, quartered on T, core cut out (C2 cheek cut), quarters sliced 3 mm on the S slicing disc | 5–6 min per head | M–H |
| Lettuce, herbs | butt cut, dunk-washed, spun on T; herbs chopped on S | 2 min | H |
| Leek | cut before washing (GP-W4) | 1 min | H |

### 4.3 Cutting most produce

After peeling, every item goes one of four ways: **dice** in the press cup (grids 6 and 10 mm; onion,
carrot, potato, celery, apple, mango, avocado), **slice, shred, grate** in the cutter cup on S (1–6 mm,
grater; cucumber, potato, cabbage, cheese, carrot), **knife on the board on T** (halves, wedges, strips,
segments of meat, herbs coarse; T turns the board for cross cuts), **chop** fine in the cutter cup with the
blade rotor (herbs, garlic paste, pesto). Two mechanisms (press cup, S) plus a knife cover the cutting part
of PRP-039 and the corpus.

**Throughput [E]:** 4 apples pared and cored 2.5 min; 1 cucumber peeled and sliced 1 min; 1 kg potatoes
boiled in the skin and riced: 2 min of hand time; 2 avocados halved, stoned and riced 2 min; 4 oranges à vif
2 min; 1 kg raw potatoes peeled 4–5 min. Batch mode (K9 Q7): firm produce for two days can be peeled at night
and stored lidded at 2–4 °C, so produce time leaves the meal's critical path.

**Questions for the produce bench (E5):** sprung-shoe tracking at 1 mm on knobbly celeriac and bent
cucumbers; press-peel of avocado, banana and mango at three ripeness levels (does the skin stay intact on the
piston; is the stone a problem in the cup?); spit grip on soft or slippery items (cup-backed prongs); stone
plane finding for avocado and mango by camera or by a knife that stops on force.

---

## 5. How the hard operations work

Food rules C1 §10.3 apply throughout: fond before deglazing, fried items finish last, 200–250 mL fat for
breaded cutlets, never invert a pan with > 30 mL fat, core probe for steak, roast, mince, poultry. Times [E].

### 5.1 Rinderrouladen (6 rolls, 4 persons)

1. **Lay out**: the red board on T (raw meat); slices (from a box, tipped onto a GN tray) laid one by one with the
   spatula-tongs; T turns each slice so its long side lies along y. Salt and pepper by spoon.
2. **Fill**: mustard spread by the silicone spatula drawn in y, **stopping 35 mm before the flap edge**; the
   flap salted and floured dry (C1 fix); bacon strip and gherkin quarter laid by the tongs; onion strips.
3. **Fold and roll**: the two side folds (15 mm) pressed down by the turner edge; the roll started by the
   fork lifting the near edge and the turner pushing it over (GA-04 plough on the board), 2.5 turns; seam
   down. The roll is set into the **comb cradle**; when six are in, the **GA-20 raft** (two two-tine forks)
   is pushed through all six by Z (≤ 150 N).
4. **Sear**: braiser on the domino front at 3.4 kW, 30 mL fat; the raft laid seam side down, 90 s untouched,
   then turned by roll to two more faces; raft lifted to a GN 1/3. **Onion and tomato paste roasted in the
   fond 4 min** (C1 fix), deglazed with wine and stock; raft back; lid on.
5. **Braise** lidded on the domino front at simmer for 90 min (traditional stove-top method; no 5 kg
   braiser lifted into the oven at 1.6 m). Probe in one roll (≥ 85 °C for tender).
6. **Finish**: raft out, rolls pushed off the raft by the stripper comb into a GN 1/3-65 (hot-hold in the
   oven at 70 °C); gravy reduced and thickened on the domino front, stirred by the whisk in intervals.
   ≈ 25 events for the Rouladen part; the raft makes six rolls one item. Untested: the fork-and-turner roll
   on a dry floured flap (bench E5); fallback silicone apron roll (K6b).

### 5.2 Breaded Wiener Schnitzel (4 cutlets)

1. **Breading line** on the well lid (bench): three GN 1/3-65 with flour, beaten egg (egg fixture, 2 mm
   strainer) and crumbs, side by side along y.
2. **Rack breading** (K5b): each cutlet is laid by the tongs onto the lower **lift rack** (Ø 260 wire rack)
   in the flour tray (its rim stands on the tray rim); the hand dusts flour over it with the spoon; the
   rack is lifted, tapped, lowered into the egg tray, then into the crumb bed, where crumbs are spooned
   over and pressed with the turner. The crust is never gripped; the underside is coated by the bed. Two
   cutlets per rack; breaded ≤ 10 min before frying.
3. **Fry** in the red Ø 280 pan on the domino front with **220 mL** clarified butter and oil (3.6 mm), 170 °C
   (IR): the rack with two cutlets lowered into the fat; after 2.5 min the upper rack is hooked on, the
   **pair is turned by roll 180° in the fat plane** (the roll axis lies in the joint plane, K6b), the empty
   rack lifted off; 2.5 min more. Batch two the same. First batch hot-held ≤ 8 min in the oven at 80 °C
   vented; fried last in the menu (C1 A-4). Fat cooled and poured into the fat cup → bin.
4. ≈ 14 events for breading, 8 for frying. Untested: crumb adhesion on the rack's underside (E5).

### 5.3 Frikadellen (8 patties, 600 g mince)

Stale roll soaked in a GN 1/3 at the spout; onion diced in the press cup (grid 6, green); mince (tipped
from its box), egg, onion, roll, mustard, spices into the kneading bowl on T; the **hung kneading roller**
works 90 s at 40 rpm while the hand does other work; reaction on the anchor post. **Disher** (60 mL,
pincer sweep) drops 8 portions into the red Ø 280 pan on the domino rear (low vessel, rule 2.3) with 20 mL
fat; each pressed to 25 mm by the turner (smash-forming, round flat traditional shape). Turned singly by
the turner every 3 min; probe in the largest to **72 °C core**. ≈ 18 events. No extrusion, no cylinder.

### 5.4 Kartoffelpüree (1 kg potatoes)

Potatoes dunk-washed and boiled **in the skin** in the 5 L pot on the domino front (25 min). Drained by
lifting the basket. The press cup with the ricer die stands on T (coil off); halves go in skin side down
(tongs, three batches of ≈ 350 g); T drives the piston up at 13 Nm (≈ 3 kN, 15 mm/s); the riced flesh is
swept by the spatula into the swivel spout, which drops it into the 3 L pot standing on the domino front
with 200 mL hot milk and 50 g butter; skins stay as a cake on the piston and go to the chute. Folded by the
spatula in four strokes; or, when T is free, the pot goes on T and the hung scraper folds at 20 rpm. Riced,
not beaten: no glue (C1 K4-7). ≈ 12 events. Untested: sweep rate of riced flesh off the die top (E3).

### 5.5 Kneading and shaping yeast dough (pizza, 500 g flour)

Flour, salt, yeast tipped by weight into the bowl on T (hub cells ±2 g); water dosed at the spout by the
flow meter; **kneading roller and scraper** hung from the bowl rim with the reaction arm on the post; T at
60–100 rpm for 8 min; coupling lag at T shows dough development. Proof 60 min in the bowl, lidded, in the
oven at 30 °C with steam. Divided by loss in weight (scraper cuts, wrist cell); each piece laid on an oiled
GN 2/3-20 on the bench and rolled with the **gauge-ring pin** to 5 mm: the hand pushes 150–300 N in Z and
draws in y, then turns the tray by 90° on T for the cross passes. Topped (spoon, tongs, grated cheese from
the S disc); baked one tray at a time at 230 °C. Pasta sheets the same way at 1–1.5 mm with flour. ≈ 30
events. Untested: 1 mm sheets at ≤ 400 N (risk shared with K9).

### 5.6 Pfannkuchen (8 pieces)

Batter in the jug on S (eggs from the fixture, flour, milk, salt), rested 15 min. The Ø 280 pan sits on
the **heated hub** (dog ring): 3 g fat; 70 mL ladled into the centre; **T spins the pan once at ≈ 200 rpm
for 1 s** — the batter spreads as on a crêpe spreader (spin-spread, K1b); ring coil 1.8 kW. After 90 s:
release check (5 mm jerk by T, camera). Flip: the second pan (its hermaphroditic partner) is set rim to rim
by the hand, the far-side hook engages, the hand grips the bottom pan's stub, lifts the pair 50 mm and
**rolls it 180° in 0.8 s**; the pair is set down, the hook released against the release pin on the post,
the emptied pan lifted off. 60 s more; pancake slid onto a GN 2/3 in the oven at 80 °C. 8 × 3.5 min ≈ 30 min.
≈ 40 events (adapted, R-03 a, as K9). Untested: spin-spread evenness on a heated, slightly domed pan.

### 5.7 Draining pasta

400 g pasta in 4 L in the 5 L pot with its basket, on the domino front (boost 3.4 kW: 7.7 min to boil).
Drained by **lifting the basket** by its stub and holding it 20 s over the pot (water stays in the pot for
the sauce if wanted), then the pasta is poured from the basket by roll into the sauce pan or a serving dish;
the water is poured off later through the strainer lid into the rinse cup (or kept for the next batch). 4
events. Nothing hot is inverted with liquid except the pour, which is a lip pour at ≤ z 1200 over the rinse
cup (K2b rule).

### 5.8 Carving

Boneless roast (or braised meat) rested 10 min, laid by the spatula-tongs into the **GA-14 V-trough** on
the board carrier on T; the gauge plate set by the hand to 8 mm (hot) or 5 mm (rested); the scalloped
knife is drawn in y and lowered in Z through the slot; each slice falls onto the tray; T turns the trough
180° for the second half. 1 kg in ≈ 4 min. Braises (pot roast, Sauerbraten) cut hot at 8–10 mm, as
traditional; poultry roasted as parts (R-06 b, as K9). ≈ 6 events.

### 5.9 Plating 2–4 portions

* **Plated mode** (2.11): plates warmed on their carrier in the oven; the carrier set on the bench; the
  **plate cradle** (a slotted L-plate on a stem) is pushed against a plate's face, its lip under the plate's
  lower rim, lifted 30 mm, rolled 90° (the plate now lies on the cradle), lowered onto the heated hatch tray,
  whose four ribs pass the cradle's slots and take the plate; the cradle is withdrawn in y. Two plates side
  by side. Components: mash by ladle as a mound, vegetables by ladle with the strainer edge, two patties by
  the turner, gravy by ladle; rice as a ladle mound (no ring mould is carried). 2 plates × 4
  components ≈ 8 placements × 12 s ≈ 1.6 min; drawer cycle; then the next 2. The camera checks rim
  cleanliness; a smear is wiped by the spatula edge. ≈ 6 events per pair (tools held for both plates).
* **Family-style mode**: components into 2–3 lidded GN 1/3-65 serving dishes (≈ 1 event each) plus the warm
  plate carrier: 2 drawer cycles, 4–6 events, ≈ 1 min.
* Untested: the plate cradle on deep plates (rim angle) — bench E10; fallback plated mode only for flat
  plates, deep plates served with the carrier.

### 5.10 Dish return and washing

1. The diner slots plates into the carrier in the drawer, cutlery into the basket, glasses into the glass
   basket, pushes the drawer in (≈ 30 s for 4 persons).
2. The hand lifts the carrier over the chute, **rolls it 180°**: scraps fall; retaining bars hold the
   plates; the camera checks for foreign items (SRV-014, SRV-015) and chips.
3. Well cycle order (4 persons): during the meal at most one **turnaround** load for red items (red pan,
   red tongs, red board, breading trays) if the menu needs them again; after hand-over: ware load 1 (pots,
   pans), ware load 2 (bowl, braiser, boards, press cup kit, S kits), ware load 3 (two tool racks, GN), dish
   load (two plate carriers, glass and cutlery baskets, hatch tray). Each 12–15 min with 88 °C stored water,
   final rinse ≥ 82 °C for 60 s (A0 ≥ 90), fan dry with the lid ajar to the extraction.
4. Unloading: tools and kits to the cabinet; GN trays and plate carriers into the cold oven; the last load stays in
   the well as the clean store. Every item passes the camera (white and UV-A) when it comes out; a dirty item
   goes back into the next load.
5. Events: dish return ≈ 5; well loading and unloading ≈ 30 for a 4-person meal (K9 ≈ 35 for dishes alone).

---

## 6. Benchmark check (B1–B12, `../03-exploration-brief.md`)

Times [E] from the order, one retry of ≈ 1 min included in the tightest step; limits as in K9 §5 (PERF-002
or 1.15 × T_ref + 10). **ev** = handling events as K9 (one grasp to release of an item, box grips
included; a tool that serves both plates of one drawer cycle in one grasp counts once), plated mode, in the
meal; **+after** = dish return and well loading after hand-over (put-away later is not counted, as in K9).
B6 is cooked for 4, not 6 (#19). Notes only where K9b differs from K9.

| B | Dish | 4 persons: result, time (limit), ev / +after | 2 persons: time, ev / +after | What changed against K9 |
|---|---|---|---|---|
| B1 | Rouladen, Rotkohl, Salzkartoffeln | yes, 130 min (183), 62 / 84 | 125, 52 / 66 | Rotkohl on the heated hub under the scraper (no interval stirring); Rouladen braised lidded on the domino front; raw potatoes peeled on the spit (4–5 min) instead of the drum |
| B2 | Schnitzel, Bratkartoffeln, Gurkensalat | yes, 50 min (68), 56 / 76 | 45, 44 / 58 | rack breading; Bratkartoffeln in the pan on the hub (turned by the turner), Schnitzel pan on the domino front; potatoes boiled in the skin earlier (scheduling rule, as K9); cucumber sliced on the S disc |
| B3 | Frikadellen, Püree, Erbsen-Möhren | yes, 45 min (50), 60 / 80 | 40, 50 / 64 | disher and smash-forming instead of extrusion; carrots and peas on the heated hub; riced mash into the pot on the domino; tightest benchmark, still one retry of reserve |
| B4 | Spaghetti Bolognese, grated cheese | yes, 88 min (96), 38 / 56 | 85, 34 / 48 | sauce simmers 60 min on the heated hub under the scraper: −10 stirring events; cheese on the S grating disc |
| B5 | Pizza from flour, 2 trays | yes (tray pizza, R-05 a), 120 min (≈ 150), 38 / 50 | 1 tray: 100, 30 / 40 | dough kneaded on T as K9; one tray at a time in the countertop oven; the second tray served 12 min later or held at 70 °C |
| B6 | Gemüseeintopf from whole vegetables | yes, 46 min (50), 44 / 62 | 42, 38 / 52 | Eintopf in the braiser on the heated hub; celeriac and carrots on the spit; bean trimming (GP-102) still the long step |
| B7 | Steak, oven fries, salad | yes, 2 steaks + 1 extra batch at 4 p: 48 min (≈ 54 [E]), 46 / 64 | 40 (44), 36 / 48 | fries cut in the press cup (grid 10); lettuce spun on T; steak on the domino front, probe 54 °C |
| B8 | Pfannkuchen, 8 pieces | adapted (pan-pair flip, R-03 a), 36 min (50), 40 / 52 | 4 pieces: 20, 24 / 34 | **spin-spread** on the heated hub instead of tilting the pan; no separate flip pan |
| B9 | Chicken curry with rice | yes, 48 min (≈ 62), 40 / 58 | 44, 34 / 48 | curry on the heated hub under the scraper; rice by absorption in the 3 L pot on the domino; garlic pressed in the skin |
| B10 | Lasagne, béchamel from scratch | yes, 125 min (148), 44 / 62 | 120, 40 / 54 | béchamel on the heated hub (milk in four portions, scraper turning): the hand is free in K9's busiest phase |
| B11 | Rührkuchen in a loaf tin, unmoulded | yes, 95 min (≈ 102), 26 / 34 (no persons) | — | creaming in the cutter cup with the whisk rotor; folding on T at 20 rpm |
| B12 | Scrambled eggs, toast, 1 person | yes, 9 min (≈ 21), 12 / 16 | 2 persons: 10, 14 / 18 | one quick well load or shared with the next meal |

**Summary.** All twelve are possible (B8 adapted, B5 tray pizza), as in K9. Events in the meal: 12–62 (K9
12–71), mean ≈ 41 at 4 persons (K9 ≈ 46); with dish return and well loading at most ≈ 84 (K9 ≈ 105). The
**family-style mode** saves ≈ 6–8 events and ≈ 3 min per 4-person meal. The tightest remain B3 (45/50) and
B6 (46/50), bound by the single hand; the heated hub moved B3 from 47 to 45 and freed the hand in B4 and B10.
Menus with four hot components for four persons use the oven as the fourth hot position or run 5–10 min
longer (domino has 2 zones).

---

## 7. Numbers

Comparison with K9 (`../concepts/K9-einhand.md` §7) and with **K6b**, the best round-2 concept by its own
weighted self-assessment (7.0; K1b 6.6, K8b 6.5, K3b 6.4, K5b 6.4, K2b 6.2, K4b 6.0). Like-for-like scope:
preparation, cooking, oven, serving hatch, dish return and washing of ware and dishes.

### 7.1 Summary

| Quantity | K9 | K6b | **K9b** |
|---|---|---|---|
| Cell width, like for like | 1950 (P 900 + O 450 + W/S 600) | 1855 | **1750** |
| Whole machine | 3600 with ambient 450 | 3505–3955 | **3600 with ambient 650** |
| Motion actuators (cell, incl. oven door and hatch) | 9 (7 normalised) | 10 (9 normalised) | **6** |
| Dynamic seals | 4 | 5 | **2** (Z band, Y band); X labyrinth contact-free |
| Novel mechanisms, C5 S-min convention / strict | 2 / 2 | 2 / 3 | **2 / 4**: N1 roll-bayonet grip; N2 generic produce module (spit on blade post, press-peel); strictly also N3 press cup on T (upward, swept) and N4 ring coil round a canned hub — each with a rig (§9) and a fallback |
| Mechanism types | 7 | 9 | **6** (gantry, hub, press cup, domino, oven, well) |
| Series chain B3 | 6 | — | **5** (gantry, hub, press cup, domino, well) |
| Custom part types (K9's counting) | ≈ 36 | ≈ 60 | **≈ 35** (enclosure and cabinet, X box, mast and arm, roll can and sleeve, hub pocket, plug and glass, anchor post, well and lid, rinse cup, chute, hatch drawer, stub with drip collar and dog ring, press cup, blade post, corers and pitter, egg fixture, raft and cradle, trough, lift racks, plate cradle and carriers, hung tools, ravioli plate, dumpling press, ≈ 12 stem types) |
| Loose food-contact ware | ≈ 99 pieces, ≈ 66 handled + 8 second set | 78 items + 11 carriers | **77 pieces, ≈ 61 handled + 5 second set**; 9 carriers |
| Handling events, B3 4 persons, in the meal / with dish return and loading | ≈ 70 / ≈ 105 | ≈ 72 mean, 92–102 full menus | **≈ 60 / ≈ 80**; mean B1–B12 ≈ 41 (K9 ≈ 46) |
| Cleaning stations | 3 (washer, jet gate, nozzle rail) | 2 | **3** (well, rinse-cup jets, nozzle rail) |
| Peak power | 10.0 kW | — | **≈ 9.7 kW** |
| Unplanned exchanges a year (C3 X10 model: 3 % per axis, 25 % per seal) [C] | 1.2 | 1.6 | **0.7** |
| All clean after hand-over, 4 persons | 70–90 min | 39 min | **50–60 min** |
| Simplicity score (C5 method) [E] | 6.5–7 | 6.3 | **≈ 7.3** (S-min reference 7.1) |

### 7.2 Coverage (C1 standard N, 248 meals, 8 excluded by requirements 5.4)

| Step | Meals | Note |
|---|---|---|
| K9 central (C1 kit with hostable modules, #25 module, ravioli plate, dumpling press, DM12 at risk) | 233 | K9 §7.1 |
| Continuous stirring restored by the heated hub (risotto, polenta: K9's "0 to −2") | 233; low end 231 instead of 230 | M; the second stirred dish of a menu is stirred in intervals |
| Domino with 2 zones + hub (3 positions + oven) instead of 4 zones | 0 | COK-002 M met; 4-pot menus take longer, no meal lost [E] |
| Garlic pressed in the skin (GP-17) instead of bought peeled cloves | 0 | covers garlic dishes even if Q11 of K9 is answered "no" |
| Knurled drum and S0 removed | 0 | spit and spoons |
| **Central** | **233 = 94.0 %** (range 231–236) | target 231 (93 %): reserve 2. At risk: DM12, AS09; M-confidence: MX06, CK16 (press-peel), IT17, DM33, CK17 (passive parcels). Out: AS08, IN07, CK12 |

### 7.3 Water and energy per 2-person meal (reported, not a gate, #23)

| Item | Water | Energy |
|---|---|---|
| Well: 2 loads (ware; dishes with some ware) | 18 L | 1.2–1.5 kWh (88 °C store + wash heater) |
| Produce dunk baths | 6–8 L | — |
| Cooking water | 3 L | in cooking |
| Rinse-cup jets, hob and deck rinse | 4 L | 0.1 kWh |
| Cooking (domino, hub, oven) | — | 1.2–1.8 kWh |
| 30 L store standby share | — | 0.1 kWh |
| **Total** | **≈ 31–33 L** (K9 33–37, K6b ≈ 50) | **≈ 2.6–3.5 kWh** (K9 2.5–3.1, K6b ≈ 3.5) |

### 7.4 Cost (#22 reported, #28 split)

**Appliances** (household, largely as bought) [E]:

| Appliance | € |
|---|---|
| Induction domino, 2 zones + interface board | 300 + 60 |
| Countertop combi-steam oven + control interface + float valve | 550 + 100 |
| Slim household dishwasher as wash-parts donor | 400 |
| 30 L under-sink water heater | 200 |
| Hob-extractor fan with baffle filter | 150 |
| Fridge + freezer (cold storage) | 1,000 |
| Shelving (ambient storage) | 500–1,000 |
| **Appliances** | **≈ 3,260–3,760** (customer's figure ≈ 3,000–3,500) |

**Machine part** (design-to-cost at small-series prices, ±30 %) [E]:

| # | Line item | € |
|---|---|---|
| M1 | Gantry: X belt module 1.7 m in the dry box with labyrinth and purge fan; Z ball screw with brake on the mast; Y belt module in the closed arm; 3 closed-loop steppers and drivers; 2 sealing bands; mast and arm tubes | 1,000 |
| M2 | Roll unit: stepper + planetary in a sealed housing, canned magnet coupling (can, inner and sleeve rotors, PEEK bushes), bayonet bore, reaction tab, Hall sensors | 300 |
| M3 | Arm-root single-point load cell and amplifier | 60 |
| M4 | Hub: drawn pocket and S thimble, T plug, NEMA 34 + 10 : 1 planetary, 600 W BLDC and driver, coaxial shaft, 3 load cells, anchor post | 450 |
| M5 | Ring induction coil with generator (OEM), glass disc with hole and gasket | 300 |
| M6 | Well: welded insulated tub with combs, lid-bench with gas strut (wash parts in the appliances) | 500 |
| M7 | Rinse cup with strainer, tap spout, 4 jets, turbidity sensor; chute with flap; bin drawer | 180 |
| M8 | Enclosure: deck, X box, walls, rear gutter, glazed door with guard lock, tool cabinet with flaps and box shelf, oven mount, hatch drawer (runners, solenoid lock, 150 W heater, 2 trays) | 1,500 |
| M9 | ≈ 8 valves, nozzle rail, fan dry, piping | 300 |
| M10 | Controller (single board), 3-phase power manager, 2 cameras with lights, safety relay, wiring | 600 |
| M11 | Ware: bought pots, pans, GN, tins, processor discs 500; stubs, drip collars, dog rings welded on ≈ 40 items 400; press-cup kit with bought grids 200; custom tools, fixtures and carriers 500 | 1,600 |
| | **Machine part** | **≈ 6,800** (range 5,000–9,000) |
| | **Total** | **≈ 10,100–10,600** |

Against K9 (machine part €7.8–13.8 k, mid 10.8 k): **−€4 k at the midpoint**, from 3 fewer actuators,
2 fewer seals and the roll unit without a chuck (−€0.8 k), no side-loading chamber and no plate dispensers
(−€0.6 k), a smaller enclosure without a cabinet over the hob (−€1–2 k) and ≈ 20 fewer ware pieces
(−€0.5 k). Against K6b (€11.4 k): −€4.6 k. K8b (€5.9 k) is cheaper only because its oven and dishwashing are
outside its module.

---

## 8. Cost gap analysis

### 8.1 Why the machine part is not at €2 k

The machine part (≈ €6.8 k) is ≈ 3.4 × the target. Three blocks make 61 % of it:

| Block | € | Share | Why it is there |
|---|---|---|---|
| Ware (M11) | 1,600 | 24 % | ≈ 80 pieces with a grip feature; ≈ €500 of it are pots, pans, tins and knives a household buys anyway |
| Enclosure, cabinet, hatch (M8) | 1,500 | 22 % | the wet zone needs a closed, washable stainless box with a door; it also replaces the household's worktop, sink cabinet and utensil drawer |
| Gantry (M1) | 1,000 | 15 % | three bought linear axes with closed-loop steppers in dry boxes |
| Controls and cameras (M10) | 600 | 9 % | |
| Well, hub, coil, roll (M2, M4–M6) | 1,550 | 23 % | the stations that replace a dishwasher's racks, a mixer, a blender, a processor, a stirring cook |

€2 k is about the price of the gantry plus its controller alone. The customer's €2 k assumed the appliances
carry most of the machine; in K9b they carry heat, washing water and cold, but the hand, the hub, the wet
enclosure and the ware are machine. No explored concept reached €2 k at 93 % coverage; the cheapest round-2
cell (K8b, €5.9 k) leaves the oven and the dishes outside its module.

### 8.2 Candidate cuts for the cost round (ordered by € saved per loss)

| # | Cut | Saves [E] | Costs |
|---|---|---|---|
| CC1 | Enclosure from standard kitchen carcasses (from the shelving budget) with stainless only in the wet zone (deck, back wall to z 1450, well, cabinet liner); bent sheet, no polished welds in Zone N; bought glazed cabinet door | 500–700 | more joints in Zone S that the nozzle plan must reach; hygiene validation of the joints |
| CC2 | Series price for 50–100 units | 25–35 % of M1, M2, M4, M8, M11 (≈ 1,500) | none technically; needs a series |
| CC3 | Gantry from printer-class parts (aluminium V-slot, GT3 belts, NEMA 23 open-loop with stall detection) in the dry box; Z by belt with brake and counterweight | 400–500 | repeatability ±0.5 mm (stubs and combs take ±3 mm), belt life (yearly check), payload 6 → 4 kg: full braiser slid, never lifted |
| CC4 | Stubs as clamp-on rings on bought ware instead of welded; dog rings on 4 items only | 250–350 | crevice under the clamp: must pass the riboflavin test of E2; ring loosening checked by the camera |
| CC5 | Well from a bought deep-drawn sink body or the donor's own tub cut down | 200–300 | dimensions follow the bought part (capacity ±20 %) |
| CC6 | Controller on a single-board computer with bought stepper drivers; one wide-angle camera instead of two | 250–350 | well-mouth and plate-rim checks from an oblique view; less vision redundancy |
| CC7 | Unheated hub (drop the ring coil, M5) | 300 | +6–12 events and 5–10 min hand time per stirred meal; risotto and polenta back "at risk" (coverage reserve 2 → 0–2); B3 back to 47/50 |
| CC8 | Hatch drawer replaced by a fixed tray behind a manual flap | 150 | the diner reaches 250 mm into the machine (SRV-010) |
| CC9 | No second set | 150 | PERF-005's 30 min between two meals fails; fine for the 2-person household's normal day |
| CC10 | Drop S; bought cordless stick blender held by the hand (K5b); slicing and grating by knife and rasp | 200 | +3–5 min per meal; slicing quality by knife; one more battery item; not recommended |
| CC11 | Tool cabinet replaced by an open tool rail | 200–250 | tools in the splash zone during cooking (C2 R-6): not recommended |
| CC12 | Drop ravioli plate and dumpling press | 150 | −3 meals → 230 = 92.7 %, below #26: not allowed |

**Path**: CC1 + CC3 + CC4 + CC5 + CC6 save ≈ €1.6–2.2 k (machine part ≈ €4.6–5.2 k at small-series
prices); with CC2 ≈ €3.3–3.8 k. CC7 and CC8 bring it to ≈ €2.9–3.3 k at a cost in time and ergonomics.
Below that only two levers remain, and both are the customer's call: count the ≈ €1 k of ordinary kitchen
content (pots, pans, knives ≈ €0.5 k; worktop-and-cabinet function ≈ €0.5 k) as household equipment, or
accept a machine without a gantry, which no concept has shown at 93 %.

---

## 9. Risks and open questions

### 9.1 Risks and the cheapest kill experiments (run in this order)

| # | Risk | Experiment | Cost, time | Kills / decides |
|---|---|---|---|---|
| E0 | **One hand, 2-zone domino and the height rule are too slow or block each other** | discrete-event simulation of B1–B12 and 4 reference menus with retries, the domino front/rear rule, hub occupancy, well schedule and the phase plan | €0, 2 days | domino vs 4-zone hob (+300 mm); second set; menu limits |
| E1 | **No countertop combi-steam oven fits ≤ 460 mm in y** (≥ 25 L, hook-openable door, start via the control board, tank plumbable) | CAD and supplier survey of 6–8 models; buy and measure one | €0–600, 2 days | the high-oven layout; fallback K9's O column with a side-loading chamber, or a narrower mast lane (80 mm → oven ≤ 480) |
| E5 | Food results of the passive methods | home bench: rack breading + rack-pair turn in 220 mL; Rouladen fork-and-turner roll with raft; spin-spread and pan-pair flip; disher smash patties; spit paring of 10 produce with three shoes; Spätzle slider | €150, 2 days | routes of §5; fallbacks apron roll, tongs breading |
| E9 | Dish return and plating | diners slot plates into a carrier; 180° carrier roll over a bin with typical scraps; plate cradle on flat and deep plates with a manual mock-up | €100, 1 day | Q8, plated mode for deep plates |
| E3 | **Press cup on T** (N3): force, upward dice quality, sweep rate, press-peel, thread cleaning | stainless tube with Rd 28 × 6 screw and PE piston on a torque-limited drill at 13 Nm; onion, potato, carrot through bought grids; potatoes in skin, avocado, banana, mango through the ricer; dried mince and starch on the thread through a dishwasher programme, riboflavin | €400, 1 week | dicing and ricing chain; fallback K5b pull-down press (+1 actuator, +2 seals) or K1b lever dicer |
| E4 | **Ring coil around the hub** (N4): evenness at the pot centre, power through the 6 mm dog-ring gap | OEM ring coil under a glass disc with a Ø 130 hole; crêpe and béchamel tests; IR map | €300, 3 days | heated hub; fallback unheated hub and interval stirring (CC7) |
| E10 | Canned T/S torque and heating | K8 rig subset: Ø 120 pocket at 25 Nm, Ø 40 thimble at 6000 rpm, coil heat on the pocket | €300, 3 days | hub |
| E2 | **Roll-bayonet grip in soil** (N1): lock and unlock torque, detent life, pour and pan-pair moments, cleaning of the J-slots | bought magnetic coupling (10 Nm) with a sleeve and two J-slots on a stepper; stubs with PEEK detent; 5 000 cycles dry, floured, greasy, wet; vessels on glass resisting unlock; jet-rinse and riboflavin | €800, 2 weeks | the hand's grip; fallback K6b pin jaws on a lip-sealed roll (+1 actuator, +2 seals; still 7 / 4) |
| E6 | Well: on-edge loading, spray coverage, A0, cycle time | donor wash parts in a plywood-and-sheet well 420 × 440 × 450 with combs; pots, pans, GN, carriers; riboflavin; loggers at the 82 °C / 60 s rinse; 30 L store recovery | €700, 1 week | one washer (Q1); PERF-005 |
| E7 | Household domino and oven control | interface on the touch board of one domino and the oven's control board; power limit; pan detection of stubbed and dog-ringed pans | €400, 1 week | #5 vs #28; fallback OEM modules |
| E8 | Fumes and heat: bands, cabinet soffit, the high oven near the X box | smoke and grease-aerosol test over the domino and hub with the rear slot; thermocouples on the X box beside a running countertop oven | €200, 2 days | P-8; oven insulation |

**Other risks named**: the hub is the busiest station (prep, pressing, cooking, spinning) — the planner
must sequence it (E0); the bench is unavailable while the well lid is up; the Y band still passes over open
food (gutter, daily wash; C2 K6-2 accepted as in K9); deck congestion with three hot positions on 600 mm;
the 30 L store's standby loss (≈ 0.3 kWh a day); cost (§8).

### 9.2 Open questions for Ben (with the default assumed in K9b)

| # | Question | Default |
|---|---|---|
| Q1 | May **one washer** clean the cooking ware and the dishes, glasses and cutlery, with raw-meat ware only in loads with the ≥ 82 °C / 60 s rinse? | yes |
| Q2 | Is **one serial hand** acceptable: B3 and B6 near their time limits, potatoes for Bratkartoffeln boiled ahead, 4-pot menus 5–10 min longer? | yes |
| Q3 | **Temporal raw/RTE separation** on one open deck (raw work first, sleeve rinse, red/green ware, disinfecting well)? | yes |
| Q4 | A **2-zone household domino plus one heated turning position** (3 hot positions + oven) instead of a 4-zone hob, so that ambient storage gets 650 mm instead of 350? | yes, domino |
| Q5 | A **countertop combi-steam oven of 25–32 L**, mounted high, its door opened by the machine's hook, its tank fed by a float valve? | yes |
| Q6 | Household domino and oven with their **control boards interfaced** (instead of OEM modules, #5)? | yes; OEM fallback |
| Q7 | The diner **pulls the hatch drawer** out by hand (no motor)? | yes |
| Q8 | Dish return: the diner **slots plates into a rack** in the hatch drawer and drops cutlery into a basket, instead of setting dishes down anywhere? | yes |
| Q9 | Serving: **plated for 1–2 persons, family style** (lidded serving dishes + warm plates) **for 3–4**? | yes; "always plated" also works (+≈ 8 events, +3 min) |
| Q10 | **Interval stirring** (20–30 s every 1–3 min) for the second stirred dish of a menu counts as traditional? | yes |
| Q11 | Spices and salt dosed by **levelled measuring spoon** (±10 %) instead of a 0.05 g scale? | yes |
| Q12 | Tortellini and Maultaschen as **square parcels**, apple turnovers and gyoza as **crimped half-moons**? | yes (c) |
| Q13 | The human wipes the **oven cavity** in the rare case a spill burns on? | yes |
| Q14 | Kohlrouladen leaves by blanching the whole head: accept "at risk"? | yes |
| Q15 | **Cost**: machine part ≈ €6.8 k against €2 k; continue with the cost round of §8? And may ordinary kitchen content (pots, knives, worktop-cabinet function, ≈ €1 k) be counted as household equipment rather than machine part? | yes; counted as machine part until Ben decides |
