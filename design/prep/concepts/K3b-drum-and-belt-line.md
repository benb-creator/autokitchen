# K3b — Drum and belt line, improved (round P5a)

Improvement of `design/prep/concepts/K3-drum-and-belt-line.md` (K3) per
`design/prep/round2/00-improvement-brief.md`, against DECISIONS #1–#28 and the critiques C1–C5.
Nothing was built or tested. Numbers are estimates [E] unless tagged: [K] known practice, [C] calculated
here, [D] from a concept document, [C1]…[C5] from a critique.

**Core idea kept:** food is worked by two process machines — a self-washing drum that tilts about its own pouring
lip, and a flat belt with a nose — and moves between them and the vessels by pouring, conveying and laying down,
never by gripping. **What changed:** the two hidden manipulators of K3 (vessel shuttle and tool arm) become one
honestly counted hand; the belt becomes ware; everything that does not earn its place is gone.

---

## 0. Brainstorm

### 0.0 Charges to fix (working notes from C1–C5 and the decision matrix)

| Ref | Charge | Severity |
|---|---|---|
| C3 K3-1, C5 | "No manipulator" hid two: 5-axis vessel shuttle + 3-axis tool arm with 15 heads; 35 actuators (25 normalised), 19 dynamic seals, 7 novel mechanisms, 13 mechanism types, ~85 events | major, the main charge |
| C2 K3-1 | Fixed TPU belt is the food surface for raw meat and RTE; inner face and wash box never seen; TPU hydrolyses > 60 °C under 55 °C wash + steam; comb and press plate cut it. Fatal if the riboflavin test fails | major / fatal-if |
| C2 K3-2 | Drum "flash" is dry heat, A0 does not apply; silicone heads stay wet; knurled disc holds starch | major |
| C2 K3-3 | Dock chute shared by raw meat, RTE, powders and unwashed produce; raw mince tipped over the open shaft | major |
| C2 K3-4 | Arm heads parked wet above the open drum | major |
| C2 K3-6, C3 K3-6, C4 K3-7 | One drum for every wet job (produce wash, peel, boil, raw mince, mash): bottleneck (busy 27 of 34 min in B3), allergen carry-over after a 90 s rinse; drum, shuttle head and dock are single points of failure | major |
| C3 K3-2 | 35 kg spinning drum hard-mounted on a Ø 60 shaft into the building wall; 105 N at 8 Hz; coil-to-drum rub risk | major |
| C3 K3-3, K3-4 | Ø 16 nose bar cannot hold a 0.5 mm blade gap; 40 Hz single guillotine shakes rods and seals | major |
| C3 K3-5 | Tool arm: swing, plunge and 1 kW spindle through one concentric penetration, lubricated gearing above food | major |
| C3 K3-7 | R1 hob boils under the belt wash box and TPU return strand | major |
| C4 K3-1 | Oven does not fit under the drum (≈ 500 mm depth for a 595 body turned sideways) | major |
| C4 K3-2 | Ports at z 120 (vessels) and z 1750 (boxes) on different walls | major |
| C4 K3-3, K3-4, K3-6 | Power 11 kW excludes H0; water ≈ 60 L per 2-person meal; peel + chop + spin > 5 loud minutes | major |
| C1 K3-1 | Bratkartoffeln tumbled from raw slices: hash, not Bratkartoffeln | major (W3) |
| C1 K3-2 | Salad spun at 480 rpm together with tomato and cucumber | major (W3) |
| C1 K3-3, A-3 | Schnitzel in 25 mL fat (0.2 mm) because the pan-pair flip cannot hold more | major (W3) |
| C1 K3-4, A-5 | No core probe: Frikadellen, steak, roast "by time" | major |
| C1 K3-5 | No corer, garlic press, citrus press, zester, ricer; bought cored apples, peeled celeriac, pepper strips, juice: 83.1 % as documented (90.3 % with arm modules) | major |
| C1 K3-7, A-2 | Rouladen gravy without roasted onion and paste; no fastener fallback | major (brief) |
| C1 K3-6, K3-8, K3-9 | Pancake zigzag pour; red cabbage core shredded in; greasing with one roll axis | minor / major |
| C5 §5.2 | Suggested: delete belt + gates (−10 act, −9 seals, −4 novel), drop spin, dock → tip by hand, pastes as packs | — |
| 04 §6.2 | "K3: stop; borrow the lip-pivot pour geometry; drum wok only as a later option" | — |
| Strengths to keep | Drum = credible self-cleaning bulk vessel (wash, peel, knead, stir-fry, best Bolognese browning); pour about its own lip; belt for carving, sheeting dough, breading, Rouladen | — |

Hard limits to meet or argue (C5): ≤ 10 actuators, ≤ 5 dynamic seals, ≤ 2 novel mechanisms, ≤ 70 events.

### 0.1 From K1 (ceiling turret cell)

| # | Idea | Verdict for K3b |
|---|---|---|
| I1 | Passive tools driven by one core shaft; "a missing operation is one more passive part" | **take as a rule**: K3b's drum is its only power drive; tools are passive and the drum (or its tilt) moves the food against them |
| I2 | Slotted mandrel rolls a Roulade along a stationary slice | maybe: inverted on the belt (a free mandrel resting on the moving belt winds the slice); the pocket loop needs no part at all, test both |
| I3 | Hermaphroditic pan pair (half stub + hook tab) turned in the air | **take** if K3b keeps a roll axis: pancakes, Rösti, unmoulding |
| I4 | Jet gate: tool held in fixed fan nozzles and spun | **take**: the arm heads (if any remain) are rinsed in the drum mouth spray, never parked wet over the drum |
| I5 | Ram with die cassettes on wall pegs, cut-off by a hand-held blade; ricer plate passes skin-on potatoes | maybe: a die-in-ware press needs force K3b does not have; the ricer function is wanted (C1 K3-5) |
| I6 | Front door as serving hatch; air corer for patties; tool rails; three hands | reject: K3b serves through one port; corer needs a bore; more hands are the opposite of the fix |

### 0.2 From K2 (vessel stack and inversion)

| # | Idea | Verdict for K3b |
|---|---|---|
| I7 | Inverter on the lift ("Wender"): one carriage that lifts, reaches, rolls and grips; every pick-up can be an inversion | **take, reduced**: K3's deck and head merge into one carriage; no separate deck axis |
| I8 | Load pins in the jaws: every carry is weighed; partial inversion by weight portions sauces | **take**: replaces the deck load cells and the dock scale for most doses |
| I9 | Closed pair tumbled: toss, coat in flour, oil fries, shake-peel garlic and boiled eggs | **take, inverted**: the drum *is* K3b's tumbler: flour coating of pieces, oiling of fries, shake-peeling garlic against the wall (impact, not abrasion) |
| I10 | Grease by spin, flour by tumbling, release by a 3 s induction pulse | **take** for tins (C1 K3-9): a loose-floor tin greased by spin needs a turning position, which K3b's drum is not — use liners/loose floors instead (see K5) |
| I11 | Spin-spread batter on a turning pan (150 rpm, 2 s) | maybe: needs a turning hob; K3b has none unless the drum back is the pan |
| I12 | Rinse seat at the shaft foot: drain, cold flush, waste strainer, jaw rinse in one funnel | **take**: K3's drain gutter and shaft floor become one seat under the drum lip |
| I13 | Rim spool with neck, hourglass dock, cold sheet with release pulse | reject: custom spun ware; 5-actuator dock; cold sheet is out by #27 |

### 0.3 From K4 (shuttle mat)

| # | Idea | Verdict for K3b |
|---|---|---|
| I14 | ENVELOPE: a sheet folded back over sticky food, the roller works on its back (cling-film method) | **take**: the roller never touches dough or raw meat; the sheet goes to the washer |
| I15 | The mat is "an excellent flat-food station and a poor whole kitchen; its place is the flat half of a hybrid next to a bulk-and-liquid half" | **take as the thesis of K3b**: drum = bulk half, flat station = flat half, one small hand between them |
| I16 | Roller-blind cassettes washed on retraction; mats stored wound | reject: wound wet elastomer is C2's worst finding (K4-1); K3b's food surface must leave for the washer flat |
| I17 | Pour direction sets orientation: long goods tipped out along the line stay aligned | **take**: boxes are tipped along the belt axis, so leek, carrot, cucumber and meat slices arrive lengthwise |
| I18 | Dump port: funnel mouth beside the hob row, pot water and scraps never cross a vessel | **take**: merged with the rinse seat (I12) under the drum lip |
| I19 | Polar placement (turntable angle + nose position) reaches every point of a dish | maybe: needs a turntable under the dish; K3b's carriage has none |
| I20 | Turntables under every hob with wall-peg scrapers; slab–strip–chop dicing; LOOP kneading | reject for K3b: 4 drives and seals for stirring (the drum stirs); chop dicing unproven; the drum kneads |

### 0.4 From K5 (ram-and-die column)

| # | Idea | Verdict for K3b |
|---|---|---|
| I21 | Ricer plate passes skin-on potatoes and unpeeled garlic; skins stay behind (cook in skin = generic peeler for mash) | **take**: K3b needs a ricer and a garlic press (C1 K3-5); as passive ware worked by force K3b already has (see own ideas) |
| I22 | Frying book: two hinged GN pans flip everything at once, bread, flatten, press | maybe as **loose ware** (a hinged double pan, a bought household product class) turned by the carriage's roll; never with more than 30 mL fat (C1 A-3) |
| I23 | Loose-floor tins: the cake is pushed out, dome up; set desserts pushed out of a tube | **take**: fixes the greasing/unmoulding charge (C1 K3-9) without a second roll axis |
| I24 | Rotating round positions with a hung scraper (stir, spin, spin-spread batter, rasp can) | reject as extra drives; K3b's drum already is the one turning vessel; note that a hob turntable is what K9 dropped too |
| I25 | Paste storage as a capped syringe tube in cold storage; slot die lays a mustard ribbon that stops 35 mm short | **take** the slot die on K3's paste cartridge (it already exists); the ribbon length is set by belt travel |
| I26 | Microtome carving in a tube; die carousel; plunger kneading; 8 kN C-frame | reject: carving stays on the flat station; kneading stays in the drum |

### 0.5 From K6 (loose ware and fast washer)

| # | Idea | Verdict for K3b |
|---|---|---|
| I27 | One flat tang with two Ø 8 holes on every item; pins make the grip form-fit; two tangs back to back = a pair inverter in one grip | **take**: replaces K3's tang-and-latch socket; pairs (pan pair, tin and board, tray pair) need no second mechanism |
| I28 | Workpiece on a fork turned by the wrist, blade fixed on a post (spit peeling: apple, kohlrabi, cucumber, potato) | **take**: K3b's carriage has a roll axis anyway; a spit fork on the tang turns produce past a fixed sprung blade — the generic peeler of #25 for what the drum cannot rumble |
| I29 | Press tube with end plates (dice, slice, rice, corer-wedger, juicing cone, Spätzle) | maybe: K3b has no press; the force must come from something it already has (own ideas) |
| I30 | Everything that touches food is ware, washed in one washer and verified per item | **take for every part except the drum**: the drum stays the one cleaned-in-place vessel (C2 rates it credible) |
| I31 | Tongs as a one-piece sprung U closed by the chuck jaws; spatula-tongs with a turner blade | **take**: one tool for singling meat slices, laying cutlets, turning Frikadellen |
| I32 | Wash-as-you-go wells, hanging mast with 6 axes, wrist spin to 6000 rpm | reject: K3b uses one bought washer; the wrist spin adds two seals over food |

### 0.6 From K8 (sealed tub, magnetic puck)

| # | Idea | Verdict for K3b |
|---|---|---|
| I33 | Canned radial magnet coupling in a welded thimble: the driven bell runs on a PEEK bush over the thimble, no seal, 25–30 Nm (T) | **take for the drum spin**: the drum's hub becomes a bell over a thimble in the yoke face; the spin seal disappears and the drum lifts off its thimble like a food-processor bowl. Same physics as bottom-entry magnetic tank mixers in pharma [K] |
| I34 | Force from torque inside ware: a screw cassette (Rd 28 × 6) turns 12 Nm into 2.5 kN; the reaction stays in the cassette | **take**: K3b's one rotary hand axis (or the drum drive) turns the screw: dice, rice, garlic press, patty orifice, corer — the force K3b lacked without the tool arm |
| I35 | Slide heavy vessels on a flush floor (24 N for 12 kg) into an oven whose floor is level with the deck | **take**: braiser and full pots are pushed, not lifted; also answers C4 K3-1 (oven placement) |
| I36 | Rectangular ware with a full-width scraper swept in X; graded wash programmes; core probe as a wireless utensil | **take** the probe (C1 K3-4) and the graded programmes; the swept scraper is not needed (the drum stirs) |
| I37 | Lag sensing in a compliant coupling gives a free force/torque sensor | **take**: the drum's magnet coupling reports torque by lag (dough development, mash stiffness, jam) |
| I38 | Pucks through a flat wall, whole tub washed after every meal, door gantry | reject: unmeasured magnets; K3b keeps a conventional hand |

### 0.7 From the catalogue and the gap documents (G-produce, G-assembly-meat)

| # | Idea | Verdict for K3b |
|---|---|---|
| I39 | GP-P1/GP-P2: cook in skin and slip for Bratkartoffeln and salads; knurled drum stopped by camera for raw-peeled uses | **take**: the drum is GP-P2 by birth; the stud disc slips boiled skins (SM-055) |
| I40 | GP-W1 dunk basket over a 40 mm sediment zone; never pour the water off through the leaves | **take, adapted**: the basket liner stands 40 mm off the drum back; water leaves through the annulus outside the basket, never through the leaves |
| I41 | GA-20 hairpin-skewer raft; dry floured flap; mustard stops 35 mm short; side folds by plough rails (GA-04) | **take** all four; the plough rails become wings of the curl frame on the belt |
| I42 | GA-36 lift-rack pair for Schnitzel in 200–250 mL fat; pan pair only ≤ 30 mL (G-assembly 7.1 rules) | **take**: the belt nose lays the cutlets onto the rimless rack, the hand lowers it into the fat |
| I43 | GA-14 overhang cut with a gauge plate ("drawbridge") supporting the slice; braises cut at 8–10 mm hot | **take**: the gauge hooks onto the cassette nose; the belt pushes the roast against it |
| I44 | Egg: bottom strike and hinge-open cradle, one egg per saucer, beaten egg strained (7.2/7.3) | **take** as a passive fixture (C5 A2) |
| I45 | SM-081 curl on a belt (bakery curling) and SM-130 belt-nose flip | **take** the curl (bread-moulder principle) for Rouladen and logs; nose flip only as a fallback |
| I46 | GP-61 plug corer, GP-62 four cheeks, GP-Z1 zest on a spit, GP-Z4 paring à vif | **take**: all are worked by the hand's Z and roll on the blade post and corer nest |
| I47 | SM-108 assembly by moving the dish under fixed depositors | **take, inverted**: the plate moves under the belt nose (plating, burger stacks, lasagne sheets) |

### 0.8 Own new ideas

| # | Idea | Verdict |
|---|---|---|
| O1 | **Drum spins on a canned bell**: the drum's hub is a magnet bell running on two PEEK bushes over a welded thimble in the yoke pod; the motor's rotor turns inside the thimble, dry. No spin seal; the drum lifts off for service; magnet lag gives the torque | **take** (−1 seal; torque sensing for dough and mash) |
| O2 | **Fixed gully under the lip** instead of K3's swinging gutter: the lip is a fixed point, so the drain can be fixed too | **take** (−1 actuator, −1 seal) |
| O3 | **S spindle in the centre of the gully**: the drum pours straight into the blender jug, the helix screws produce straight into the cutter-cup hopper standing on S | **take**: K3's "drum feeds the cutter" without a cartridge drive |
| O4 | **Tool post on the yoke**: the hand hangs roller-scraper, masher grid or hold-back on a stub at the mouth; the post tilts with the drum, so the tool keeps its pose (a passive Ankarsrum arm) | **take** (replaces the 3-axis tool arm) |
| O5 | **Belt as ware**: a cassette that the seat tensions; lifted out it hangs slack and goes to the washer on edge; one red, one green cassette | **take** (C2 R-1 met; answers the fatal-if finding) |
| O6 | **Canned face coupling** in the seat's rear wall drives the cassette's tail roller | **take** (0 seals) |
| O7 | **Gauge ramps** on the cassette side plates; the sheeting roller rests on them, the hand sets the gap by the roller's x-position and drives it by the roll axis; the reaction stays in the cassette frame | **take** (no gate, no lift actuator) |
| O8 | **Curl frame** (bread-moulder principle): a floating half-pipe hood with plough wings; the belt rolls Rouladen and mince logs under it | **take** (M; apron roll as the known fallback) |
| O9 | **Doctor blade on the ramps** spreads mustard while the belt moves the slice; lifted 35 mm before the flap edge | **take** |
| O10 | **Zigzag lay-down**: the hand moves the pan at belt speed in x and steps it in y between pieces, so one log gives two rows | **take** |
| O11 | **Shingling by speed ratio**: the plate moves slower than the belt, slices overlap by a set amount | **take** (plating nicely without tongs) |
| O12 | **Oven above the drum bay**: the drum's swing envelope ends at z 1560; a countertop combi-steam oven fits above it with its mouth into the shaft | **take** (answers C4 K3-1) |
| O13 | **Washer under the belt seat**: the seat plate is the lid of a top-loading chamber (K6b's bench-over-washer) | **take** |
| O14 | **The drum is the turning hob position**: béchamel, risotto, red cabbage, polenta are stirred continuously by drum rotation against the hung scraper | **take**: K9 had to accept interval stirring; K3b does not |
| O15 | **Moist-heat final rinse** in the drum: 1 L at 90 °C tumbled for 2 min (A0 ≫ 60), the coil flash only dries | **take** (C2 K3-2) |
| O16 | Two drums side by side for parallel jobs | reject: +2 actuators, +500 mm; the hob now takes the second wet job |
| O17 | Drive the belt by the hand's roll axis (no belt motor) | reject: the hand must move the receiving vessel during every lay-down |
| O18 | Tilt the drum by the hand via a lever and passive detents | reject: 25 kg with hot fat on a pawl; the hand would be tied to every pour |
| O19 | Centrifugal ricer: cooked potatoes pressed through the spinning basket against a fixed wiper | reject for now: novel, purée trapped in a 4 mm annulus; the masher grid gives "Stampf" |
| O20 | Tumble breading of small pieces (nuggets, fish pieces, Cordon-bleu strips) in the drum | **take** (SM-096, H) |
| O21 | Shake-peeling garlic in the drum | reject: 3–4 cloves in a 16 L drum; peeled garlic is allowed (MEAL-009, 5.6), a lever press takes skin-on cloves |
| O22 | Household domino 2-zone induction hob instead of stacked shelves with turntables and lid arms | **take** (#28; −4 actuators, −4 seals) |

### 0.9 The pick

K3b keeps K3's two process machines and gives them **one honest hand** instead of two hidden ones:

* **Drum** (kept, smaller, seal-free spin): O1, O2, O3, O4, O14, O15, O20, I9, I39, I40. The 3-axis tool arm,
  the swinging gutter, the cutter cartridges and the 15 heads are gone.
* **Belt** (kept, made ware): O5–O11, I14, I17, I41–I43, I45, I47. Nose carriage, dancer, pocket rollers, both gates,
  the wash box and the steam bar are gone.
* **Hand** (K6b/K9 class, 5 axes, replaces the 5-axis shuttle and the dock): I7, I8, I27, I28, I31, I33 (the
  probe), I35, I36. Tangs face the rear; everything is poured about its own lip.
* **Around them**: S spindle (I33/O3), domino hob (O22), oven above the drum (O12), washer under the belt (O13),
  passive egg fixture (I44), lift rack and pan pair (I42, I3), raft (I41), loose-floor tins (I23).
* Rejected for good: dock and chute, egg opener, stacked hob shelves with turntables and lid arms, oven under
  the drum, tool arm, belt gates, nose carriage, pocket rollers, steam bar, wash box.

---

## 1. What changed and why

Effect columns: S simplicity, H hygiene, C coverage and food, R reliability, F system fit; ++ strong gain,
+ gain, 0 no change, − loss.

| # | Problem (critique) | Change in K3b | S | H | C | R | F |
|---|---|---|---|---|---|---|---|
| 1 | **"No manipulator" hid two**: 5-axis shuttle + 3-axis tool arm with 15 heads; 35 actuators, 19 seals (C3 K3-1, K3-5; C5) | One gantry hand (X, Y, Z, roll, chuck) does all vessel and tool handling; the tool arm and its heads are replaced by a passive tool post on the drum yoke; the dock, chute and egg opener are replaced by tipping boxes with the hand and a passive egg fixture: **35 → 10 actuators (9 normalised), 19 → 5 dynamic seals** | ++ | + | 0 | ++ | + |
| 2 | **Fixed TPU belt** shared by raw and RTE, unseen inner face and wash box; hydrolysis under steam (C2 K3-1, fatal-if) | The belt is a **cassette (ware)**: the seat tensions it, lifted out it hangs slack and is washed on edge in the washer at 70 °C; one red and one green cassette; no wash box, no steam bar, no fixed food-contact belt | + | ++ | 0 | + | 0 |
| 3 | Gates over the belt: 6 actuators, 4 rod seals; Ø 16 nose cannot hold a 0.5 mm blade gap; 40 Hz guillotine (C3 K3-3, K3-4) | No gates. Passive tools that rest on the cassette: driven roller on gauge ramps, doctor blade, curl frame, comb divider, gauge plate. The knife is drawn by the hand's Y axis 2 mm in front of a Ø 22 nose; no blade gap to hold | ++ | + | 0 | ++ | 0 |
| 4 | Nose carriage, dancer, pocket rollers (3 actuators, 3 seals) | Fixed nose; the hand moves the receiving vessel at belt speed (lay-down); Rouladen and logs are rolled under a floating curl hood (bread-moulder principle) | ++ | + | 0 | + | 0 |
| 5 | **One drum, three single points of failure** (drum, shuttle head, dock); drum busy 80 % in B3 (C3 K3-6, C4 K3-7, C2 K3-6) | Dock gone; a 2-zone hob takes boiling and sauces, so the drum is a booster, not the only wet vessel; a drum failure costs only dough and wok meals (degrade and continue, 9.1) | + | + | 0 | ++ | + |
| 6 | **35 kg spinning drum hard-mounted into the house wall**, coil rub risk (C3 K3-2) | Drum Ø 260 × 300 for 4 persons (#19), module ≈ 22 kg loaded; spin ≤ 400 rpm only with the basket and ≤ 0.5 kg; rotating force ≤ 25 N; module on elastomer pads in a free-standing frame | + | 0 | 0 | ++ | + |
| 7 | Spin shaft seal behind the drum; arm heads parked wet over the drum (C2 K3-4, K3-5) | Spin through a **canned magnet bell** on a thimble (no seal); tools park in the closed cabinet, ride on the post only while working | + | + | 0 | + | 0 |
| 8 | Drum "flash" is dry heat (C2 K3-2) | Final rinse: 1 L at 90 °C tumbled 2 min (moist heat, A0 ≈ 380), then the coil only dries | 0 | ++ | 0 | 0 | 0 |
| 9 | Dock chute shared by raw, RTE, powders and unwashed produce; raw mince tipped over open vessels (C2 K3-3, C4 K3-8) | No chute: the hand tips each opened box straight into its target; raw packs last; unwashed produce only into the drum (the red first-wash station) | ++ | ++ | 0 | + | + |
| 10 | **Oven does not fit under the drum** (C4 K3-1) | Countertop combi-steam oven **above** the drum bay (z 1600–2000), mouth into the shaft; drum envelope ends at z 1560 | + | 0 | 0 | 0 | ++ |
| 11 | Ports at z 120 and z 1750 on different walls (C4 K3-2) | Box shelf under a ceiling port; plates and vessels to serving through one side hatch at z 1450–1650 | 0 | 0 | 0 | 0 | + |
| 12 | Stacked hobs under the belt (heat), loose glass hob discs to the washer, 2 turntables + 2 lid arms (C3 K3-7, C2 K3-8) | Household domino induction hob (2 zones) flush in the deck beside the belt, nothing stacked above it; the drum is the turning, scraped position | ++ | + | 0 | + | + |
| 13 | **Schnitzel in 25 mL** (C1 K3-3, A-3) | 220 mL in a Ø 280 pan (3.6 mm), cutlets laid by the nose onto a rimless lift rack, turned as a rack pair (GA-36) | 0 | 0 | ++ | 0 | 0 |
| 14 | **Bratkartoffeln tumbled from raw** (C1 K3-1) | Boiled in skin in the drum, skins slipped over the stud disc, cooled, sliced on S, fried in the pan, turned by the turner | 0 | 0 | ++ | 0 | 0 |
| 15 | **Salad spun with tomato** (C1 K3-2) | Leaves alone in the basket, spun ≤ 400 rpm; cut vegetables and dressing added after | 0 | 0 | + | 0 | 0 |
| 16 | **No core probe** (C1 K3-4, A-5) | Wireless probe placed by the hand for steak, roasts, Frikadellen, poultry | 0 | 0 | + | 0 | 0 |
| 17 | **No corer, garlic press, citrus press, zester, ricer** (C1 K3-5) | Spit and blade post with depth shoes, tube corers and pitter in a nest, lever garlic press, reamer and grater drum on S: generic peel/core/stone with 3 mechanisms (PRP-039) | 0 | 0 | ++ | 0 | 0 |
| 18 | Rouladen: onion and paste not roasted, no fastener (C1 K3-7, A-2, A-6) | Mustard ribbon stops 35 mm short (doctor blade), floured flap, plough side folds, GA-20 raft, fond roasted before deglazing | 0 | 0 | ++ | + | 0 |
| 19 | Greasing with one roll axis; pancake zigzag (C1 K3-6, K3-9) | Loose-floor tins with paper liner (pushed out, dome up); pan-pair flip under the G-assembly rules; batter poured on a pan rolled ±15° | 0 | 0 | + | + | 0 |
| 20 | Cut cabbage core in, cored apples and peeled celeriac bought (C1 K3-8, standard N) | Cabbage quartered and cored with the knife and cone cut on the belt; apples cored in the nest; celeriac rumbled | 0 | 0 | + | 0 | 0 |
| 21 | Peel + chop + spin > 5 loud minutes (C4 K3-6) | Rumbling 2–3 min, spin 30 s, no 3000 rpm knives in a steel drum; S chops in a lidded cup | 0 | 0 | 0 | 0 | + |
| 22 | Water ≈ 60 L per 2-person meal (C4 K3-4) | No belt wash box (11 L), no steam bar; one washer load; drum wash 4.5 L: ≈ 31 L per 2-person meal with dishes (5.8) | 0 | 0 | 0 | 0 | + |
| 23 | Cost 20 k€ (re-estimated 29–33 k€); #28 target ≈ €2 k (C3 K3-9) | Household oven, hob and dishwasher parts; 25 fewer actuators, 14 fewer seals: ≈ €9.5–15 k machine part (6.4) — still 5–7 × the target | + | 0 | 0 | 0 | + |
| 24 | K3's strengths | Kept: drum wash, rumble-peel, knead, sear (best Bolognese), stir-fry, boil and drain pasta, toss, mash; pour about the lip; belt carving, sheeting, breading without gripping, Rouladen, logs, lay-down | 0 | 0 | 0 | 0 | 0 |

---

## 2. The improved concept

### 2.1 Definition in one page

K3b is a stainless cell **1420 mm wide, 600 deep, 2200 high** that holds the whole cooking side: two process
machines (drum and belt), one hand, a speed spindle, a 2-zone hob, the oven and the ware washer. Read from left
to right it is still a line: **oven over drum → wet column (gully with the speed spindle) → hob → belt over
the washer**. The drum and the belt work the food; the hand moves vessels and passive tools and never needs
to grip a piece of food (tongs exist, but every benchmark runs without them).

Eight rules define it:

1. **The drum is the turning vessel.** A Ø 260 × 300 induction-heated tri-ply cup tilts about its own lower lip
   (+60° … −35°) and spins on a canned magnet bell (0–400 rpm). It washes, rumble-peels, slips skins, boils,
   drains, kneads, mixes mince, sears, stir-fries, stews, stirs sauces continuously, mashes, tosses, spins leaves
   and proofs. Tools are passive and hang on a post on its yoke.
2. **The lip is a fixed point, so everything under it is fixed too**: a drain gully, and in the gully's centre
   the thimble of the speed spindle S. The drum pours waste into the gully, food into the S jug or cutter cup
   standing on S, or into whatever the hand holds there.
3. **The belt is ware.** A 300 mm belt runs in a cassette that the seat tensions and drives through a canned
   face coupling; lifted out, it hangs slack and goes to the washer. One red cassette for raw meat, one green
   for everything else. Tools rest on the cassette (driven roller on gauge ramps, doctor blade, curl frame,
   comb, gauge plate), so their forces stay in the cassette frame.
4. **Lay-down instead of gripping.** The belt nose is fixed; the hand moves the receiving vessel under it at belt
   speed. Rack, tray, cradle, tin, pan or plate: the item arrives flat and in its place.
5. **One hand, honestly counted.** Gantry X (labyrinth, no seal), Z, Y, roll about y, two-jaw chuck with pins
   and load pins (K6b/K9 class). Every item has one flat tang facing the rear. Vessels pour about their own lip.
6. **Nothing stacked over food**: the hob has free air above it; the oven sits over the drum, the clean cabinet
   over the belt; the only part above an open vessel is the hand's closed arm.
7. **Every food-contact part except the drum is loose ware** washed in the one washer under the belt; the drum is
   the one cleaned-in-place vessel, finished with a moist-heat rinse and checked by camera every time.
8. **Sequence before duplication**: produce first (unwashed produce only into the drum, which is the red
   first-wash station), ready-to-eat, raw animal food last; red duplicates only for the belt cassette, one knife
   and the tongs.

### 2.2 Layout

Coordinates in mm: x along the wall from the inner left wall, y from the rear wall (0) to the inside of the front
door (580), z from the floor. Deck z 900; belt top z 1340.

```
FRONT VIEW (door removed)                          outer 1420 W x 600 D x 2200 H, inner 1380
 z
2200 +------------------------------------------------------------------------------------+
     | transport gallery (machine level, not K3b); ceiling port above the box shelf        |
2000 +=====================+===== X box (rear lane y 0-120), contact-free labyrinth slot ===+
     | OVEN countertop     |  free arm space; fume intake    | CLEAN CABINET (rear flaps) |
     | combi-steam ~35 L,  |  in the rear wall               |  z 1720-1990               |
     | mouth +x, drop door |                                 +- BOX SHELF z 1700, front --+
1600 |=====================|<- open door = shelf z 1600, x 460-740                        |
1560 | drum swing envelope |                                 |  serving hatch in the      |
     |      ___            |  hand: mast in the rear lane,   |  right wall, z 1400-1650 ->|
     | pod /   \  mouth up |  Z 950-1950, Y arm, roll, chuck |                            |
     |    / drum\ +60 deg  |                                 |                            |
1340 |   | Ø260  |         |          receiving zone  <== nose (x 920) == BELT z 1340 ===|
1150 |    \x 300/__(o) lip pivot x 460                       |  cassette 470 x 350        |
     | [pedestal: tilt     |  :  stream                      |  seat plate = washer lid   |
 900 |  bearing, rear]     |GULLY + S | HOB domino, 2 zones   +----------------------------+ 1260
 830 |---------------------| funnel   | flush glass, zones    | WASH CHAMBER, top-loading  |
     | plinth: tilt drive, | Ø150 with| front/rear            | 450 x 350 x 780, tang rail |
     | load cells on pads, | S thimble| hob electronics,      | (ware, belt cassettes,     |
     | drain pump, valves, | S motor, | power manager,        |  dishes)                   |
     | coil generator,     | strainer,| controller            +----------------------------+ 450
     | bio-bin drawer      | waste    |                       | wash pump, heater, softener|
   0 +---------------------+----------+-----------------------+----------------------------+
     0                    460        620                     910                         1380

TOP VIEW at deck and belt level
 y
 580 +-- front door (glazed, interlocked) ---------------------------------------------------+
     |                        | jet gate | HOB front zone      | BELT CASSETTE (green or    |
     |   drum Ø 260           | tap spout| Ø 210, 3.0 kW       |  red), belt 300 wide;      |
 460 |   (y 200-460),         | waste    |                     |  nose x 920 (Ø 22) <--     |
     |   mouth toward +x      | chute    |                     |  tail x 1370 (Ø 50,        |
 330 |   axis y 330 .......(o)|  GULLY   |---------------------|  face coupling in the      |
     |                    lip | (o) S    | HOB rear zone       |  seat's rear wall)         |
 200 |   yoke and pod behind  | blade    | Ø 180, 2.0 kW       +----------------------------+ 230
     | [pedestal y 120-200]   | post,    |                     | STATION STRIP: egg cradle, |
 120 |                        | corer    |                     | cup scale S0, tool rests   |
     |== mast lane y 0-120: mast travels x 60-1340; arm reaches y 140-580 ====================|
   0 +--------------------------------------------------------------------------------------+ rear wall
     0                       460        620                   910                        1380
```

Width by function: drum and oven column 460, wet column 160, hob 290, belt and washer column 470, walls 40:
**1420 mm**. The cell contains preparation, three heated positions (drum 3 kW, hob 3.0 + 2.0 kW), the oven, the
ware washer and the plating position. K3 needed 1450 mm without a fitting oven and without a washer.

### 2.3 The drum

| Item | Value [E] |
|---|---|
| Cup | Spun tri-ply (1.4404 inside 0.6 mm, aluminium core, 1.4016 outside; total 2.5 mm), inner Ø 260 × 300, 15.9 L gross, about 11 L of liquid at +60°. Rolled and seal-welded lip r = 6. One welded helix fin, 12 mm high, 1.5 turns, fillets r = 6. Mass with hub ≈ 4.5 kg |
| Working charge (4 persons, #19) | 1.2 kg produce + 2 L water; 400 g pasta in 4 L; 1 kg dough (600 g flour); Bolognese for 4; 3 L soup; 0.3 kg leaves in the basket. Below 250 g the drum is not used (pots on the hob) |
| Spin | **Canned magnet bell**: a 1.4404 bell with an encapsulated 12-pole SmCo ring is welded to the drum's closed back; it runs on two PEEK sleeve bushes (60 mm apart) over a deep-drawn thimble Ø 110 × 90 welded into the front face of the sealed pod; a 400 W BLDC with a planetary stage turns the inner magnet rotor inside the thimble, dry. 40 Nm rated, 0–400 rpm (critical speed for Ø 260: 83 rpm). Magnet lag measured by two Hall sensors = torque (dough development, mash stiffness, jam) [K: bottom-entry magnetic tank mixers; K8's T] |
| Tilt | About the lower lip (x 460, z 1150, y 330). Self-locking worm gearmotor, 100 Nm, in a sealed column (the **pedestal**) that rises from the plinth behind the drum's rear face (y 120–200), so the hand's rear lane stays free over the whole width. Static torque at horizontal ≈ 56 Nm [C: 11 kg at 0.2 m, pod 5 kg at 0.4 m, yoke 6 kg at 0.25 m]. Range +60° (mouth up) to −35° (pour) |
| Swing envelope [C] | x 80–460 (the upper rim reaches x 630 at −35°), z 830–1560; nothing is stacked closer than 40 mm |
| Heating | Curved induction segment on the yoke under the lower third of the wall, 3.0 kW; IR sensor on the wall, contact sensor in the pod. Coil gap 4 mm; bell runout ≤ 0.3 mm on the PEEK bushes |
| Weighing | Three load cells under the pedestal foot, on elastomer pads (dry plinth): ±10 g at standstill |
| Vibration | Spin only with the basket liner and ≤ 0.5 kg; ramp through 83 rpm with redistribution; 0.1 kg imbalance at 0.12 m and 400 rpm = 21 N [C] (K3: 105 N). The cabinet stands on its feet; the wall bracket is an anti-tip bush, not a load path |
| Water | Two fan nozzles on the yoke aim into the mouth and tilt with it: mains water through a flow meter (dosing, ±10 mL), hot water, detergent |
| Tool post | A Ø 20 stub on the yoke ring at the mouth's front edge, non-rotating, tilting with the drum. The hand hangs one passive tool on it: **roller-scraper** (knead, cream, scrape during the pour, hold-back in rumbler mode, scrape sauces while stirring), **masher grid** (mash). The tool keeps its pose relative to the drum at every tilt (Ankarsrum principle, C3 rank 1) |
| Inserts (ware) | **Basket liner** Ø 250 × 220, 3 mm holes, floor 40 mm above the drum back (sediment zone, GP-W1), bail with tang; **knurled peel disc** Ø 250 with a central stem and tang (GP-P2); **stud disc** (one-piece moulded platinum silicone, Ø 250) for slipping cooked skins |
| No seal in or near the food volume | Spin canned; tilt seal at the pedestal top, 150 mm behind the drum's rear face, below the yoke, never above an open vessel |

What the drum does, by tilt and speed:

| Mode | Tilt | Speed | Tool | Jobs |
|---|---|---|---|---|
| Tumble wash | +20° … +45° | 30–45 rpm reversing | — / basket | wash robust produce; wash leaves in the basket |
| Rumbler | +60° | 120 rpm | peel disc + roller hold-back | raw-peel potato, carrot, celeriac chunks, beetroot, ginger; camera stop (GP-P2) |
| Slip | +45° | 40 rpm | stud disc | skins of cooked potatoes, beetroot; blanched tomatoes, peaches, plums |
| Knead, mix, cream | +35° | 40–100 rpm | roller-scraper | yeast dough to 1 kg flour, mince mass, Rührteig (all-in method) |
| Stir-cook | +40° … +60° | 2–10 rpm | roller-scraper | béchamel, risotto, polenta, red cabbage, curries, stews, sauces: continuous stirring without the hand |
| Wok | +10° … +20° | 10–30 rpm | — | sear mince (best Bolognese browning, C1), stir-fry, sauté, glaze |
| Boil and drain | +60°, then −10° | 0–5 rpm | basket | pasta, potatoes, dumplings; water through the annulus to the gully |
| Mash | +40° | 20 rpm | masher grid | Kartoffelpüree ("Stampf" texture), with milk and butter at 80 °C wall |
| Toss, coat | +15° | 8–15 rpm | — | salad with dressing; flour or crumb coat for small pieces (SM-096) |
| Spin | +60° | ≤ 400 rpm | basket | leaves dry (18–23 g); wash-water fling-off |
| Discharge | −35° … +0° | 3–10 rpm reverse | — | pour about the lip; reverse helix screws pieces out one by one (feeds the S cutter cup) |
| Proof | +45° | 1 rev/min | — | dough at 30 °C wall |

### 2.4 The belt cassette

| Item | Value [E] |
|---|---|
| Belt | Endless homogeneous polyether-TPU 2 mm, 85 Shore A, white, 300 wide, no fabric, no teeth (bought bakery/food belt class; hydrolysis-resistant grade, continuous ≤ 70 °C wet [U: supplier]). Wear part, yearly (≈ €60) |
| Frame | Two 1.4404 side plates 3 mm, 470 × 70, three tie rods; the top edges of the side plates outside the belt are the **gauge ramps** (rise 1 : 10 from the nose towards the tail, 2–24 mm above the belt). Tang at the rear side plate, centre. Mass 4.5 kg |
| Rollers | Tail roller Ø 50 (crowned, the drive), nose roller Ø 22 (crowned), one support roller Ø 40 under the sheeting zone; all turn on fixed stainless axles in open PEEK sleeves (1 mm axial gap both ends, no blind bore) |
| Tension | **The seat tensions, the cassette does not**: two spring wedges in the seat push the nose axle outwards by 12 mm when the cassette is set down (300 N belt tension); lifted out, the belt hangs slack for washing and drying. Flanged rollers keep a slack belt on |
| Nose deflection | 600 N on a Ø 22 tube over 300 mm: 0.1 mm [C: 5wL⁴/384EI]; no blade passes near it, so it needs no tighter tolerance |
| Drive | Canned **face coupling**: the tail roller's rear end carries a disc with 8 encapsulated magnets 4 mm from the seat's rear wall, behind which a gearmotor turns the mating disc. 3 Nm (≈ 120 N belt pull), 0–0.3 m/s, reversible, encoder ±0.5 mm. Axial pull taken by a PEEK thrust washer. No seal |
| Seat | Stainless tray frame on three load cells (±2 g to 5 kg), locating cones, the two tension wedges and the coupling. Its plate is the lid of the wash chamber below |
| Two cassettes | Green (produce, dough, cooked food, plating) and red (raw meat and fish). Stored on edge in the clean cabinet |

Passive tools that rest on the cassette (ware):

| Tool | Build | Work |
|---|---|---|
| **Driven roller** | Ø 70 × 300 stainless tube, axle ends Ø 12 resting on the gauge ramps, tang on the rear axle end coaxial with the hand's roll axis | Sheet dough 20 → 2 mm, flatten meat in the envelope, press crumbs, flatten patties. The hand sets the gap by the roller's x-position on the ramp (10 mm of x per 1 mm of gap) and drives it at belt speed by the roll axis (30 Nm = 850 N at the surface); the vertical reaction goes into the side plates, not into the hand |
| **Doctor blade** | 280 mm stainless blade with silicone edge on the same axle ends | Spread mustard, sauces, tomato on pizza at 1–3 mm while the belt moves the item under it; lifted to stop a spread (35 mm before a Roulade flap) |
| **Curl frame** | Floating half-pipe hood Ø 60 × 140 guided by two pins on the side plates, with two plough wings upstream | Rouladen (side folds 15 mm, then curl), mince and dough logs, wraps: the belt carries the leading edge under the hood, the edge curls back, the roll forms between the moving belt and the still hood (bread-moulder principle [K]); the hood floats up as the roll grows |
| **Comb divider** | 7 blunt blades at 32 mm pitch on a bar, pressed down by the hand (Z, 150 N) | Divides a log into 8 pucks or dough strips into pieces |
| **Gauge plate and nose shelf** | L-plate hooked onto the nose end at t = 4, 6, 8, 10, 12 or 15 mm; below it a hook rest for a GN 1/3 tray | Overhang cut: the belt pushes the item against the gauge, the knife (drawn by Y) cuts in the slot, the slice drops into the tray |
| **Envelope sheet** | Moulded platinum-silicone sheet 300 × 500, 1 mm, with a stiff end bar | Cling-film method (K4 ENVELOPE): laid over meat or sticky dough before the roller passes, peeled off at 170° |

### 2.5 The hand

| Axis | Travel | Drive | Force, speed | Seal |
|---|---|---|---|---|
| X | 1280 (mast x 60–1340) | servo-stepper 400 W, toothed belt, profile rails in the X box (z 2000–2100, y 0–120) | 300 N, 1.0 m/s | **none**: carriage passes a contact-free labyrinth slot with purge air and a gutter (K6b) |
| Z | 1000 (chuck z 950–1950) | ball screw with brake on the hanging mast 80 × 100 in the rear lane | 400 N, 0.3 m/s | sealing band on the mast's front face, in the rear lane |
| Y | 440 (chuck y 140–580) | belt drive inside the closed arm 70 × 70 | 200 N, 0.6 m/s | sealing band on the arm's **top** face inside a 15 mm gutter sloped to the mast (nothing drips off it) |
| Roll (about y) | continuous | sealed roll unit at the arm tip, stepper + planetary, slip ring | 30 Nm peak, 0–200 rpm | one lip seal under an umbrella collar |
| Chuck | 2 × 22 mm | servo screw, two parallel jaws with conical pins through the tang's two Ø 8 holes (form fit), **two load pins** | 20–400 N | one rod seal |

Payload 6 kg at 160 mm. Everything carries **one flat tang 6 × 32 × 60 mm with two Ø 8 holes, facing the rear**
(C4 R-2, K6); pan pairs and rack pairs present their two tangs back to back and are held as one. What the roll
axis does: pour about the vessel's lip (X and Z follow the roll), invert pairs, turn the spit for peeling, drive the
sheeting roller, swing tools into the drum mouth. The hand reaches over the drum only when it is mouth-up (≥ +35°,
its highest point then at z ≤ 1370 [C]) and the arm is below the oven (z ≤ 1580): interlocked.

### 2.6 Other stations

| Station | Where | What it is | Actuators |
|---|---|---|---|
| **Gully** | wet column, under the lip | Welded 1.4404 funnel 150 × 290 (rim z 900, cone to z 960 on the lip side), rear part under the blade post and corer nest; 2 mm strainer basket (ware, tang) and turbidity sensor in the outlet; two 85 °C rinse jets; drain to the house drain via a pump | none (pump) |
| **Speed spindle S** | thimble Ø 40 × 25 in the gully centre (x 540, y 330) | 600 W BLDC below the gully, inner magnet rotor (K8's S); 1.5 Nm, 0–6000 rpm. Ware stands on a 3-point ring around the thimble: blender jug 2 L, chopper cup 0.6 L, whisk cup 1 L, **cutter cup** (bowl 3 L with bought food-processor discs: adjustable slicer 1–6 mm, grater, dicing kit 10 mm; wide hopper lid) and reamer cone. The drum lip pours straight into the jug; the reverse helix feeds the cutter hopper | 1 |
| **Blade post and corer nest** | rear of the wet column, over the gully | Socketed post with a sprung peeler blade and three depth shoes (GP-11 geometry: 1 mm zest/peel, 2.5 mm, 5 mm paring); silicone-lined V-nest with an end stop for coring, pitting and avocado twisting; peel and cores fall into the gully strainer | none |
| **Jet gate, tap, waste chute** | front of the wet column | Four 85 °C fan jets for the chuck after every soiled grip (3–10 s); tap spout cold/45 °C for filling pots held by the hand; flap-covered chute to a 20 L bio bin in a front drawer | none |
| **Hob** | x 620–910 | Household domino induction hob 288 × 520 flush in the deck (#28), touch control replaced by an interface board (DEC-5, COK-023): front zone Ø 210 3.0 kW, rear zone Ø 180 2.0 kW, bridge mode for one GN 2/3 | none |
| **Oven** | over the drum bay, z 1600–2000, y 125–575 | Countertop combi-steam oven ≈ 35 L (external ≈ 490 W × 400 H × 450 D), turned so its mouth faces +x; its door replaced by a motorised drop door that opens to a horizontal shelf at z 1600 (#24). Trays are slid in and out by the hook rod; outside, the hand grips them | 1 (door) |
| **Wash chamber** | under the belt seat, z 450–1260 | Welded 1.4404 tub 450 × 350 × 780, insulated; wash system of a bought slim dishwasher (pump, 2 kW heater, spray arms on both long walls, softener, dosing); tang rail at the top; hygiene programme with 10 min at 70 °C (A0 ≈ 60). Top-loading: the hand lifts the cassette, then the seat plate (lid, on open lift-off hinges) | none (pumps) |
| **Station strip** | y 120–230 behind the cassette | Passive egg cradle (bottom strike and hinge-open, G-assembly 7.2), slotted saucer on the **cup scale S0** (600 g / 0.05 g), 2 mm egg strainer; rests for the belt tools | none |
| **Clean cabinet, box shelf** | over the belt column | Closed cabinet z 1720–1990 with rear spring flaps the arm pushes open; box shelf at z 1700 in front of it under the ceiling port (C4 R-9) | none |
| **Cameras** | three | over the drum mouth (mirror-finish check, rumbler stop, pour), over the belt (white belt as the vision background, K4), over the hob and gully | — |

### 2.7 Actuators and seals (complete)

| # | Actuator | Seal or penetration |
|---|---|---|
| 1 | Drum spin | none (canned bell on a thimble) |
| 2 | Drum tilt | **1 lip seal** with drained lantern at the pedestal top (behind the drum, not above food) |
| 3 | Belt drive | none (canned face coupling) |
| 4 | Hand X | none (contact-free labyrinth) |
| 5 | Hand Z | **sealing band** on the mast (rear lane) |
| 6 | Hand Y | **sealing band** on the arm's top face in a gutter |
| 7 | Hand roll | **1 lip seal** under an umbrella collar |
| 8 | Chuck | **1 rod seal** |
| 9 | S spindle | none (canned thimble) |
| 10 | Oven door | appliance gasket (static) |

**10 motion actuators stated, 9 normalised** (C5: without dock, egg module and oven door). **5 dynamic seals.**
Not counted: about 10 solenoid valves, drain pump, washer circulation and drain pumps, two dosing pumps, extraction
fan, washer drying fan, induction generators (drum, two hob zones, oven's own), three cameras.

### 2.8 Ware list

B = bought, B+ = bought with a welded tang (ferritic insert), C = custom (laser-cut, bent, welded, spun).

| Group | Items | No. | Make |
|---|---|---|---|
| Drum inserts and tools | basket liner, knurled peel disc, stud disc (silicone), roller-scraper, masher grid, transfer scoop (GN 1/3 with spout) | 6 | C |
| Belt | cassettes green and red, driven roller, doctor blade, curl frame, comb divider, gauge plate with nose shelf, envelope sheet, wire V-saddle for roasts | 9 | C (belt B) |
| S ware | blender jug 2 L, chopper cup 0.6 L, whisk cup 1 L, cutter cup with hopper lid, adjustable slicing disc, grating disc, dicing kit 10 mm, 10 mm stick disc, reamer cone | 9 | B / B+ (bought processor parts, base adapted to the thimble ring) |
| Pans and pots | frying pans Ø 280 × 2 (identical, hermaphroditic hook tabs: either is the flip partner, K1/K6b), lift-rack pair Ø 260 (GA-36) × 2, pot Ø 220 5 L with basket, pot Ø 220 3 L, pot Ø 160 1.5 L, braiser Ø 280 × 100 with lid, small braiser Ø 200 (1 person, C1 A-8), lids Ø 220 and Ø 160, strainer lid Ø 220, GN 2/3-40 thermoplate | 15 | B+ / C (racks) |
| Oven ware | GN 2/3-20 trays × 2, GN 2/3-65, loaf tin 30 cm with loose floor, springform 26 (loose floor) | 5 | B+ |
| Tools (tang, drip collar, stem) | chef's knife green and red, scalloped carving knife, turner, spatula-tongs green and red (one-piece sprung U, one jaw a 0.6 mm turner blade, K6), ladle, silicone spatula, balloon whisk, fork-spit, corer tubes Ø 14/22/42 (one set), plunger pitter, seed spoon, sifter cup, cup 250 mL, ring mould Ø 90, hook rod 450, probe holder with wireless probe, lever garlic press, Spätzle hopper with plate, piston syringe with nozzles | 22 | C (bought blades, probe, press, hopper) |
| Fixtures | Rouladen comb cradle and GA-20 raft fork, egg cradle and slotted saucer, egg strainer, gully strainer basket, fat cup, ravioli stamp GN 2/3, hinged dumpling press | 9 | C / B+ |
| **Food-contact total** | | **75** (K3: 31 + 15 = 46) | |
| Carriers | plate carrier trays from serving (2), dish racks of the washer (3) | 5 | C |

The count rises against K3 because K3b now does what K3 bought or skipped (coring, garlic, zest, probe, lift rack,
raft). A 4-person meal uses 25–35 items. Where things live: pots and pans on their hob zones and in the cabinet;
GN trays in the cold oven; drum inserts and belt tools in the cabinet; S ware on a rack beside the box shelf.

### 2.9 Interfaces

| Interface | K3b offers | K3b asks |
|---|---|---|
| Box port | box shelf z 1700 under a ceiling port; the hand takes boxes by their tang and tips them straight into drum, belt, S jug or pot; lids are removed outside the cell (C4 R-4) | GN 1/9, 1/6, 1/3 PP boxes with a moulded tang (ferritic insert) on one short end; raw flat cuts one per compartment or interleaved (G9); opened packs delivered upright in a GN 1/3 carrier (C4 R-5) |
| Transport | ceiling port only (boxes in and out); waste bin and strainer solids leave through the front drawer | — |
| Serving | side hatch in the right wall, z 1400–1650: the hand passes plated food on carrier trays to the serving column and takes empty carriers and warm plates back | a serving column with plate warmer, hatch and dish return (K9's W/S, not part of K3b); dishes may come back into K3b's washer if Q1 of C5 is answered yes |
| Utilities | — | 400 V 3N~ 3 × 16 A; cold water 2.2–5 bar; drain; extraction to the machine's shared condenser |

---

## 3. How the hard operations work now

Times for 4 persons unless stated. Confidence H / M / L as in the catalogue. "Events" = handling events of the
hand (one grip-and-release of an item, or one box tip) — the unit of C3 X4 and C5 S5.

### 3.1 Generic peeling, coring and stoning (#25, PRP-039): three mechanisms

| Mechanism | How | Produce | Loss, time [E] | Conf. |
|---|---|---|---|---|
| **M1 Drum rumbler** (GP-P2) | Drum at +60°, knurled disc keyed to the back, roller-scraper on the post held in the charge so the pieces roll over the knurl instead of riding with the wall; 120 rpm, yoke nozzles spray 1 L/min; camera over the mouth stops when < 5 % of the visible surface is brown or the drum's load cells show 20 % loss; slurry poured to the gully twice | potato, carrot (cut to ≤ 120 mm on the belt first), celeriac (halved on the belt), beetroot, ginger, kohlrabi chunks, Jerusalem artichoke | 10–18 %; 1.2 kg in 2.5–3 min; eyes remain (≈ 1.3 % of the surface, inside PRP-022) | M |
| **M2 Spit and blade post, corer nest** (household apple-peeler principle [K]; GP-11, GP-61, GP-Z1, GP-Z4) | The hand stabs the piece on the fork-spit (camera finds the axis), turns it by the roll axis at 60–150 rpm and traverses it in y past the sprung blade of the post; the depth shoe sets the cut: 1 mm (zest, cucumber stripes), 2.5 mm (apple, pear, kiwi, mango, courgette, cucumber), 5 mm (citrus à vif, pumpkin slices, kohlrabi). Coring and stoning in the nest by the hand's Z (60–150 N): tube corer along the stalk axis (apple, pear, quince), plug corer from the stalk (pepper: plug out, then four cheeks cut on the belt, seeds rinsed out in the basket), scar corer (tomato), stone fruit cut round the stone on the spit against the fixed knife shoe, twisted apart in the nest, stone out with the pitter (peach, apricot, plum, avocado); mango cheeks cut along the stone on the belt, flesh scored and scooped | apple, pear, cucumber, courgette, kohlrabi, kiwi, mango, citrus, pumpkin, pepper, tomato, peach, apricot, plum, avocado, chilli (halved, seeds scraped) | 15–25 % (apple 18 %, citrus à vif 30–35 %); 15–25 s per piece | M (H apple, citrus zest) |
| **M3 Heat, then slip, in the drum** (SM-055, GP-P1) | Blanch in the basket 30–60 s in boiling water in the drum, quench with cold mains water, tumble 30 s over the stud disc with water: the skins come off and leave through the annulus to the gully strainer. Cooked in skin: potatoes for Bratkartoffeln, salad and mash; beetroot | tomato, peach, apricot, plum (whole, before stoning); boiled potatoes, beetroot | 3–6 %; 3–5 min | M–H |
| Banana | Ends cut on the belt; the banana rides on the belt under the 1 mm depth shoe of a slit blade held by the hand; skin opened by the tongs, fruit pushed out by the seed spoon | banana | 1 min per banana | L–M |
| Onion, garlic | Bought peeled (#9; MEAL-009 and 5.6 allow peeled garlic); in-concept upgrade: garlic cloves skin-on through the lever press; onion upgrade slot GP-11 on the spit (not counted) | — | — | H (bought), H (press) |

PRP-039 counts three peeling and coring mechanisms (M1, M2, M3); the banana slit uses M2's shoe and the belt.
White asparagus (SD19, SP09) stays unsolved (as in all concepts): spears whip on the spit.

### 3.2 Dice an onion

Bought peeled onions (#9). The hand puts them on the green belt; the belt carries each under the knife, which halves
it by a push cut through the root axis (the camera aligns the onion against the gauge plate; 3 s each). The halves
go by scoop into the **cutter cup on S** with the 10 mm dicing kit: slicing disc above a fixed grid, pusher plate on
the hand at 20–40 N; 4 onions in 45 s. For Frikadellen and fine sauces the halves go into the **chopper cup**
instead: 3–4 pulses of 1 s at 3000 rpm give 3–5 mm. Ring separation of onion dice is accepted as for any household
dicer. Events: box tip, 4 halving cuts (the knife is held throughout: 1 grip), scoop, pusher, cup to pot: 6. Conf.: H.

### 3.3 Rouladen: fill, roll, secure, sear, braise (B1: 8 rolls for 4)

1. **Lay** (red cassette): the hand tips the meat box (one slice per compartment) over the belt while the belt runs
   at the slide speed; two slices land side by side, long side along x. 8 slices in 4 passes.
2. **Flatten**: envelope sheet laid over, driven roller at 5 mm, sheet peeled back (60 s per pair). Optional when
   the butcher's slices are even.
3. **Season and spread**: salt and pepper by the cup tipped by roll; a 12 g spoon of mustard per slice; the doctor
   blade on the ramps at 1 mm spreads it while the belt moves the slice; the hand lifts the blade **35 mm before the
   flap edge** (camera measures the slice length). The flap is salted and dusted with flour from the sifter cup.
4. **Fill**: the filling tray (bacon dice, onion slices from S, gherkin sticks from the S julienne cut) is tipped by the
   hand as a 40 mm stripe across the leading edge, by belt position; the seat's load cells stop the pour at 35 g.
5. **Side folds and roll**: the curl frame stands on the side plates at the nose. The belt carries the slice into the
   plough wings (both long edges fold in 15 mm), then under the floating hood: the filled edge curls up the hood and
   back over itself, and the Roulade forms between moving belt and still hood (Ø 45–50). The belt stops when the
   camera sees the flap at about 5 o'clock.
6. **Into the cradle**: the hand lifts the curl frame onto its rest, takes the comb cradle (rimless, six slots) and
   holds it 15 mm under the nose, moving it at belt speed: the Roulade rolls off seam-down into its slot.
   45 s per roll, 6 min for 8.
7. **Secure**: the hand pushes the GA-20 raft fork through the cradle's guide slots and through all rolls (40–60 N);
   one raft carries four rolls; two rafts for eight. The cradle is lifted away.
8. **Sear**: braiser on the front zone, 25 mL lard at 200 °C; raft in seam-side down, 90 s untouched, then the hand
   turns the raft by roll (2.2 Nm) to brown the top and sides (≈ 60 % browned, G-assembly 4.2); rafts out onto a tray.
9. **Fond** (C1 A-2): onion dice and tomato paste roasted in the fat for 4 min, deglazed with red wine, stock added.
10. **Braise**: rafts back in, lid on; the hand carries the braiser (4.5 kg) to the oven: 160 °C, 100 min, probe in one
    roll; or on the rear zone at a simmer.
11. **Gravy**: rafts out onto a warm tray (oven 70 °C); braising liquid poured into the drum at +45°, reduced with the
    roller-scraper turning, thickened with flour slurry (S jug), seasoned; poured into a pot for serving.
12. **Plate**: the stripper comb pushes the rolls off the raft onto a warm GN tray seam-down; plated by the
    spatula-tongs (lifting from below).

Conf.: M for rolling (curl hood on meat untested; fallback apron roll on a GN tray with the hand, K6b/K9), H for
holding (raft). Events: ≈ 34 for 8 rolls (box 4, envelope 4, tools 8, cradle 2, rafts 4, braiser 6, sauce 6).

### 3.4 Breaded Wiener Schnitzel in 3–4 mm of fat (B2: 4 cutlets)

1. **Flour** (red cassette): the hand tips flour from the box into a 200 mm bed on the belt near the tail; the meat
   box is tipped and the cutlet slides onto the bed (belt speed = slide speed); flour on top; the driven roller at
   5 mm in the envelope flattens it if needed.
2. **Egg**: two eggs beaten in the whisk cup on S, poured through the 2 mm strainer into a GN 1/3-20 tray. The hand
   holds the tray under the nose; the belt lays the cutlet into the egg; the hand rocks the tray ±10° twice: egg
   washes over the top face.
3. **Crumbs**: while the cutlet lies in the egg, the belt runs a crumb bed (80 g, tipped from the box) to the nose.
   **Pick-up**: the hand tilts the tray 5° towards the nose and moves it towards the nose while the belt runs
   backwards at the same speed: the nose crawls under the cutlet (SM-101) and takes it onto the crumbs. Crumbs on
   top from the box; the driven roller presses at cutlet thickness + 1 mm (≈ 30 N). Breaded ≤ 10 min before frying
   (C1 10.3 rule 2).
4. **Fry**: Ø 280 pan on the front zone with **220 mL clarified butter (3.6 mm)** at 170 °C. Lower rack of the GA-36
   pair held by the hand under the nose: two cutlets laid flat, side by side. The hand lowers the rack into the fat
   (cutlets swim, the crust can puff), 2.5–3 min.
5. **Turn**: upper rack set on, the two tangs gripped back to back; the pair is lifted 40 mm, drained 5 s over the
   pan, rolled 180°, lowered; the now upper rack is lifted off. 2.5 min.
6. **Out**: the rack is lifted, drained, the cutlets slid onto a warm GN tray in the oven at 70 °C, vented, ≤ 10 min
   (C1 A-4); second pair fried meanwhile. Fried items finish last.

Conf.: M (nose pick-up of the egg-wet cutlet is the untested step, K3's R4; fallback: spatula-tongs lift it from the
egg tray onto the crumbs). The rack pair is the shared GA-36 method (M–H). Events: ≈ 22 for 4 cutlets.

### 3.5 Frikadellen (B3: 8 × 95 g)

1. **Mass in the drum** (first drum job of the meal, raw): soaked roll, onion from the chopper cup, 2 eggs from the
   egg cradle, mustard, salt, pepper, marjoram from the cup scale, 500 g mince tipped from the box last. Roller-scraper
   on the post, drum +35°, 40 rpm, 2 min (lag torque shows when the mass binds).
2. **To the belt**: the drum pours the mass about its lip into the transfer scoop held by the hand (the roller scrapes
   the wall during the pour, residue 2–4 %); the hand tips the scoop onto the red belt as a heap along x.
3. **Log**: the belt carries the heap under the curl frame's hood (no plough wings): it rolls into a log Ø 65 × 270
   along x; the belt load cells weigh it (750 g).
4. **Divide and shape**: comb divider pressed down (Z 150 N): 8 pucks; the driven roller at 22 mm passes over them:
   patties Ø 85 × 22. Comb and roller are wetted under the tap spout first, against sticking.
5. **Into the pan**: GN 2/3-40 thermoplate bridged over both zones, 30 mL oil at 170 °C. The hand lifts it, holds it
   under the nose and moves it at belt speed in x, stepping 90 mm in y after every puck (**zigzag lay-down**): two rows
   of four; back onto the hob.
6. **Fry and turn**: 4–5 min per side; each patty turned singly by the turner (8 × 6 s); **core 72 °C by the probe**
   (C1 K3-4). Hold ≤ 10 min in the oven at 70 °C if the mash is not ready.

Conf.: M–H (log rolling under a hood is moulder practice for dough, M for a mince mass; fallback: heap pressed flat on
the belt by the roller at 22 mm and stamped by the ring mould, K6 method). Shape: round, pressed edges (C1: R-10
acceptable for patties). Events: ≈ 16.

### 3.6 Mash

Potatoes rumble-peeled in the drum (3.1 M1), disc out (no cutting: medium potatoes boil whole in 22 min). Boiled in
the drum in 2 L salted water at +60°, drained to the gully at −10° through the basket, steamed dry for 60 s at +45° with the coil on. The
hand hangs the masher grid on the post; drum +40°, 20 rpm, 40 passes; milk (warmed in the 1.5 L pot) and butter
added; the roller-scraper replaces the grid for 30 s of stirring. Wall held at 80 °C; served by pouring about the lip
into a warm pot, or straight onto plates through the ring mould (3.12).

Result: "Stampf" texture (C1: yes for SD02). For a riced Püree the potatoes are boiled in skin and pressed through
the lever ricer (optional ware, not in the base set). Conf.: H. Events: 6.

### 3.7 Kneading and shaping dough

* **Knead** (B5 pizza, 600 g flour): flour tipped from the box (dust stays in the drum mouth, the oven above is shut),
  water from the yoke nozzles by flow meter, yeast, salt, oil; roller-scraper on the post; drum +35°, 80 rpm, 6 min; the
  magnet lag gives the torque curve (gluten development end point). 0.15–1 kg flour (M below 250 g).
* **Proof**: in the drum at 30 °C wall, 1 rev/min, 45 min; or in the oven at 32 °C with steam (frees the drum).
* **Divide**: poured about the lip into the transfer scoop, tipped onto the green belt; the comb divider cuts the heap
  into three pieces by the seat's load cells (re-cut if > 5 % off).
* **Sheet**: per piece, 6–8 reversing passes under the driven roller, gap 20 → 4 mm set by the roller's x on the
  ramps, flour from the sifter cup between passes; sheet 290 × 340 (R-05 tray pizza, 0.099 m²). Envelope sheet for
  sticky dough. Pasta (IT17, DM33): 1.2 mm in 10 passes.
* **Top**: tomato by the doctor blade at 2 mm; cheese and toppings tipped from boxes and scoops while the belt moves.
* **Lay on the tray**: the hand moves a GN 2/3-20 tray under the nose at belt speed; the sheet is laid flat.
* **Rolls**: log in the curl frame, comb divides; pieces rounded by 20 s of tumbling in the floured drum at +45°, 30 rpm
  (SM-074, M). Loaf: log laid into the loose-floor tin by the nose. Tin lining (quiche, CK02): sheet laid over the tin,
  pressed in by the ring mould and the spatula, rim trimmed by the knife on a circular X–Y path (L–M).

Conf.: H knead, H sheet, M rolls. Events (pizza, 3 trays): ≈ 24.

### 3.8 Pancake flip (B8)

Batter (250 g flour, 500 mL milk, 3 eggs) in the blender jug on S, 30 s; rest 20 min. Two identical Ø 280 pans with
hook tabs (K1/K6b): pan A on the front zone at 190 °C with 3 g butter; the hand pours 100 mL from the jug by weight
(load pins) into the centre while rolling the pan ±15° about y and moving it ±40 mm in y (a two-direction swirl by
roll and Y); 80 s. Pan B, preheated on the rear zone, is turned onto A rim to rim, slid 8 mm so the hooks engage; the
two tangs are gripped back to back; release check (5 mm jerk, camera sees the pancake move); the pair is rolled 180°
over the hob; A lifted off and returned to the rear zone. ≤ 30 mL free fat (G-assembly 7.1). 140 s per pancake with
two pans overlapping; finished pancakes stacked in the oven at 70 °C.

Conf.: M (shared mechanism; thin pancakes may fold). Fallback: second side by top heat under the oven grill (b).
Events: ≈ 6 per pancake.

### 3.9 Draining pasta (B4)

400 g spaghetti in 4 L of salted water in the drum with the basket liner (the strands slide from the box into the
mouth at +60°; the drum rocks ±20° while they soften). Done: drum to −10°, the water runs through the basket's holes
and the annulus over the lip into the gully (strainer basket, 4 L in 15 s); the basket keeps the pasta. 100 mL of
pasta water is kept by stopping the pour at +5° (load cells). The sauce pot is poured into the drum mouth by the hand;
four turns at +15°; poured about the lip into the warm serving pot. No hot pot is lifted, no water is carried.
Conf.: H. Events: 4.

### 3.10 Carving a boneless roast

Roast rested 10 min, slid by the hand from its tray onto the green belt (tray tilted at the tail, belt running
backwards), long axis along x, in a wire **V-saddle** (ware, rests on the belt) that keeps it from rolling. Gauge plate
hooked at the nose at 8 mm (braised) or 4–6 mm (pork, Kassler, pink beef); a GN 1/3 tray in the nose shelf. Each slice:
the belt pushes the roast gently against the gauge (stall on 5 N), the hand draws the scalloped knife ±50 mm in y at
0.3 m/s while descending 3 mm per stroke in the slot between nose and gauge (2 mm in front of the nose); the slice
drops into the tray. 6–8 s per slice; juice runs down the belt to the nose and drips into the tray (for the gravy).
Plating from the tray (3.12) shingles them. Conf.: H firm roasts, M braised (8–10 mm, as K9). Bone-in poultry: parts
(R-06 b). Events: knife 1 grip for the whole roast, saddle, gauge, tray: 6.

### 3.11 Other operations that changed

| Operation | K3b | Conf. |
|---|---|---|
| Bratkartoffeln (C1 K3-1) | potatoes boiled in skin in the drum (day before or morning, cooled in the cold store), skins slipped over the stud disc, sliced 4 mm through the S cutter cup; Ø 280 pan with 30 g lard, 12 min, turned 4 times in portions by the turner; onion and bacon added at the end | M–H |
| Mixed salad (C1 K3-2) | leaves washed in the basket in the drum (water out through the annulus, sand settles 40 mm below the basket floor), spun 2 × 15 s at 400 rpm, poured into the bowl; tomato, cucumber, radish sliced on S into the bowl after; vinaigrette in the whisk cup; tossed in the drum at +15° or with two spoons | H |
| Stir continuously (risotto, polenta, béchamel, red cabbage) | in the drum with the roller-scraper on the post at 2–10 rpm, wall temperature controlled; the hand is free | H |
| Stir-fry (7 mandated meals) | drum wok at +15°, 230 °C wall | H |
| Purée soup | the drum pours 1.5 L into the blender jug on S, 60 s, the hand pours it into the serving pot; two batches for 3 L | H |
| Whip, emulsify | whisk cup on S (1 egg white to 6, 400 mL cream); mayonnaise and hollandaise in the jug with oil from the cup | H |
| Grate, zest, juice | grating disc in the cutter cup (cheese, carrot, potato for Puffer); zest by the 1 mm shoe on the spit; reamer cone on S | H |
| Unmould | loose-floor tins with a paper liner: the hand sets the tin over the ring mould standing on a tray, pushes the floor up 60 mm with the turner stem, lifts the ring; cake dome up (K5) | M–H |
| Burger, open sandwich (ASM) | the order on the belt is the order in the stack (K3): bun base, patty, cheese, tomato and leaf slices, top; the plate moves under the nose and stops at each piece | M |
| Spätzle | batter from the drum into the scoop; the hand slides a Spätzle hopper over a perforated plate on the 5 L pot (household Spätzlehobel principle) | M–H |
| Garlic | peeled cloves into the chopper cup, or skin-on cloves through the lever garlic press (hand Z 150 N on a 3 : 1 lever) | H |

### 3.12 Plating 2–4 portions nicely

Plates come warm from the serving column on a carrier tray through the side hatch (two plates per carrier). The hand
brings a carrier under the belt nose:

* **Slices** (roast, Rouladen halves): the belt carries the portion from the tray onto the nose; the plate moves at
  70 % of belt speed, so each slice overlaps the previous by 30 % (**shingling by speed ratio**); 3 slices per plate.
* **Flat items** (Schnitzel, patties, pancakes, pizza slices): laid flat by the nose at full belt speed, lemon wedge
  from the knife on the belt.
* **Mash, rice**: the ring mould Ø 90 is set on the plate; the drum pours by weight about its lip into the ring held
  under the lip (or the ladle from the pot); ring lifted.
* **Vegetables**: spooned from the pot by the ladle with a slotted insert; **sauce** by ladle beside, not over, crisp
  items; **garnish** (chopped parsley from the chopper cup) by the sifter cup tipped by roll.
* Back through the hatch: 2 plates per carrier, ≈ 70 s per plate, 4 plates in ≈ 5 min (SRV-009 asks 3 min for a
  course; plating starts while the last batch fries, with plates held in the serving column's warm hatch ≤ 5 min).

Conf.: M (shingling and ring mould H; free-form garnish not offered). Events: ≈ 5 per plate.

---

## 4. Benchmark check B1–B12

Limits from PERF-001/-002 as in K3 §5. Time = order to plated food, minutes [E]. Events = handling events of the
hand during the meal, plating included, dish return excluded (C3 X4 unit; K3 counted "moves" differently, C3
normalised K3 to ≈ 85 for a reference meal). Rule in every menu: produce first, raw animal food last; fried items
finish last; core probe on every meat item.

| # | Meal | Result | 4 persons: time / limit, events | 2 persons: time / limit, events | What changed against K3 |
|---|---|---|---|---|---|
| B1 | Rouladen, Rotkohl, Salzkartoffeln | yes | 157 / 183, 62 | 150 / 183, 50 | Cabbage quartered and cored on the belt, shredded on S, braised **in the drum** with continuous stirring (t 5–85), then held in a pot; Rouladen by 3.3 (raft, floured flap, fond roasted); potatoes rumbled and boiled in the drum from t 115; gravy in a pot. Weakest step: curl rolling (M, apron fallback) |
| B2 | Schnitzel, Bratkartoffeln, Gurkensalat | yes | 62 / 67, 56 | 54 / 67, 44 | Potatoes boiled in skin in the drum, quenched in three cold baths (core ≈ 25 °C), skins slipped, sliced on S, fried on the rear zone; cucumber striped on the spit, sliced on S; Schnitzel in 220 mL on the rack pair (3.4). Tight at 4 persons; with potatoes boiled in the morning 50 min |
| B3 | Frikadellen, Püree, Erbsen-Möhren | yes | 46 / 50, 66 | 40 / 50, 50 | Drum: mince mass (t 0–4), full wash with moist-heat rinse (t 5–11), rumble and boil potatoes (t 11–36), mash (t 37–41): 3 uses instead of 4; carrots on the spit and the cutter cup; patties formed on the red belt and laid zigzag; probe 72 °C |
| B4 | Spaghetti Bolognese | yes | 84 / 96, 24 | 80 / 96, 20 | Unchanged in principle (drum sear, simmer with the roller-scraper turning, boil and drain in the drum, toss); vegetables chopped on S; cheese grated on S. Pasta water heated in the 5 L pot in parallel saves 9 min |
| B5 | Pizza, yeast dough | yes (R-05 tray pizza, class a) | 95 / 113, 36 | 85 / 113, 28 | Sheets 290 × 340 on 300 mm belt; two trays per oven run (two levels), third tray after; salami, mushrooms, mozzarella sliced on S |
| B6 | Gemüseeintopf (4 persons, #19) | yes | 42 / 50, 40 | 36 / 50, 32 | Leek cut into rings on the belt before washing (GP-W4), washed in the drum basket; roots rumbled together and screwed by the helix into the cutter cup (10 mm dice); green beans whole, ends cut by camera-indexed knife cuts on the belt (GP-102), not bought trimmed; stock from the freezer (UO-96), not paste |
| B7 | Steak, oven fries, salad (2 persons) | yes (fries: mandated X-01) | 52 / 79, 42 | 45 / 79, 32 | Fries cut by the 10 mm stick disc on S; leaves washed and spun alone, tomato and cucumber added after (C1 K3-2); steaks tipped from the box into the pan, turned by the turner, **probe** to 52 °C |
| B8 | Pfannkuchen, 8 | yes (flip M) | 44 / 50, 54 | 32 / 50, 30 | Batter in the S jug; pour with a two-direction swirl (roll + Y); hooked pan pair under the G-assembly rules |
| B9 | Chicken curry, rice | yes | 36 / 67, 26 | 32 / 67, 22 | Rice in the 3 L pot on the rear zone, rinsed through the strainer lid; curry in the drum as in K3; onion, ginger and garlic in the chopper cup |
| B10 | Lasagne, béchamel | yes | 118 / 148, 44 | 112 / 148, 36 | Ragù in the drum; béchamel in the 1.5 L pot with interval whisking; **the drum pours each ragù layer by weight into the dish that the hand moves under the lip**; sheets laid by the nose in two lanes; cheese grated on S |
| B11 | Rührkuchen, unmoulded | yes (all-in method M) | 98 / 125, 24 | same cake | Batter mixed all-in in the drum with the roller-scraper (creaming by roller is M–L, C1); poured about the lip into a loose-floor loaf tin with a pre-formed paper liner; pushed out dome up |
| B12 | Scrambled eggs, toast (1 person) | yes | 8 / 17, 14 (1 person) | 9 / 17, 18 | Eggs from the cradle into the 1.5 L pot, whisked and stirred by the hand on the front zone; toast in a dry pan, turned by the turner; the drum is not used |

**Summary.** 12 of 12 preparable (B5 and B7 with the adaptations the requirements themselves prescribe; B8, B11 and
the rolling in B1 at medium confidence). All inside PERF-001 at 2 and 4 persons; B2 and B3 at 4 persons have
4–5 min of margin, so one retry of a fried batch breaks the limit (as in K9). Events per 4-person meal: 24–66,
mean ≈ 43; the reference meal B3 has **≈ 66** (C3's normalised K3: ≈ 85; K9: ≈ 70). The drum saves the hand
every stirring, kneading, mixing, draining and mashing event; the belt saves every patty, cutlet and roll grip.

---

## 5. Cleaning

### 5.1 Principle

* **One cleaned-in-place food vessel: the drum** (C2 rates it "credible", rank 5). Everything else that touches food
  is loose ware, the two belt cassettes included, and goes to the one washer under the belt (C2 R-1).
* **Moist heat only** counts for disinfection (C2 R-3): the drum ends with a 90 °C water rinse, the washer with a
  10 min hold at 70 °C (A0 ≈ 60); induction and fans only dry.
* **Nothing above an open vessel** except the hand's closed arm (C2 R-2): the hob has free air above it; the oven
  door opens to the side of the wet column; tools park in the closed cabinet, not over the drum.
* **Fixed Zone F cleaned in place: 0.33 m²** (the drum) instead of 1.5 m² (drum, belt, gates, chute, gutter).

### 5.2 The drum

| Step | What | Water, time |
|---|---|---|
| Quick rinse (between two jobs of the same class, HYG-030) | 1 L cold from the yoke nozzles, tumble with reversal 30 s, pour to the gully | 1 L, 60 s |
| 1 Pre-rinse | last pour with the roller-scraper on the wall; 1 L cold, tumble, pour | 1 L, 60 s |
| 2 Wash | 1.5 L with detergent heated by the coil to 60 °C, tumble with reversal 3 min at all tilts from +60° to 0°; yoke nozzles spray the lip, the outer 30 mm of the wall, the tool post and the bell; pour | 1.5 L, 4 min |
| 3 Rinse | 1 L, tumble, pour | 1 L, 60 s |
| 4 **Hot rinse** | 1 L heated in the drum to 90 °C (314 kJ, 2 min at 2.7 kW), tumbled 2 min so that every wall element is wetted at ≥ 85 °C: A0 ≈ 380 at the wall [C: 10^(0.5) × 120 s]; the water is then sprayed over lip and post on the pour | 1 L, 4 min |
| 5 Dry | spin 400 rpm 10 s, coil to 105 °C for 30 s (drying, not disinfection) | — |
| 6 Verify | camera over the mouth sees the mirror finish against a stripe light at 0° and +45° while the drum turns; last-rinse conductivity at the gully; coil and IR temperature log | — |

Full wash **4.5 L, 0.35 kWh, 10 min**, run during the meal whenever the drum changes from class R to RTE. The
roller-scraper and masher grid go to the washer, not into the drum wash (silicone edge, C2 K3-2).

Honest weak points: the helix root (continuous fillet weld r = 6, ground) and the seal-welded rolled lip are
welding-quality items; the knurled peel disc holds starch (washer after every use, alkaline programme); the PEEK
bushes and the thimble behind the closed back see splash only (yoke nozzles flush them, the drum lifts off its
thimble for a weekly look and a yearly bush change).

### 5.3 Belt cassettes and loose ware: the washer

* Cassettes are lifted out by the hand after their last use in the meal and hung by their tang on edge; out of the
  seat the belt hangs 12 mm slack, so both faces, the rollers, the open PEEK sleeves and the side plates are reached
  by the spray arms on both long walls. Hot air drying with the tub's fan; the belt is never stored wound or wet
  (C2 R-9).
* Programmes: **short** (red-to-green turnaround inside a meal: 12 min, 70 °C hold 3 min), **hygiene** (after the
  meal: wash 55 °C, rinse, **10 min at 70 °C**, dry; 28 min, 9 L, 0.7 kWh), **intensive** weekly (75 °C, starch and
  protein enzyme detergent). Temperatures logged with a reference probe in the tub.
* Load: a 4-person meal soils 25–35 items = two hygiene loads after hand-over (≈ 60 min); a 2-person meal one load.
  The clean green cassette and a second pan, pot and knife set cover a next meal within 30 min (PERF-005).
* Verification: every item is held by the hand under the overview camera (white light and UV-A) on its way from
  the washer to the cabinet; a reseated cassette runs one revolution under the belt camera (white belt as the
  background, K4) before food touches it.

### 5.4 Fixed surfaces cleaned in place

| # | Surface | Zone, m² [E] | Soiled by | Cleaning | When | Drying |
|---|---|---|---|---|---|---|
| 1 | Drum inside, helix, lip | F 0.33 | everything | 5.2 | per job / per meal | spin, coil |
| 2 | Drum outer 30 mm, yoke ring, tool post, nozzles, bell | S 0.25 | pour dribble, splash | yoke nozzles in steps 2 and 4 | per meal | coil heat |
| 3 | Gully funnel, S thimble and seat ring | S (receives F pours) 0.08 | wash and cooking water, peel slurry, class R | two 85 °C fan jets after every class R pour and before any S bowl is set down; strainer basket to the washer | per pour / per meal | air |
| 4 | Wet column: blade-post and corer sockets, jet-gate box, tap spout | S 0.10 | peel, juice | rinse jets | per meal | air |
| 5 | Hob glass | S 0.15 | fat aerosol, boil-over | glass scraper and squeegee (ware) push to the gully side, rinse nozzle | per meal | air |
| 6 | Belt seat plate (washer lid top), station strip | S 0.25 | drips from the cassette edges, crumbs, egg | nozzle rail at the column's rear edge; the lid's underside is washed by the washer itself | per meal | fan |
| 7 | Drum bay walls, drip floor (z 830, sloped to the gully), pedestal | S 1.2 | peel splash, steam, frying aerosol | four fixed nozzles | per meal with frying or peeling, else daily | fan |
| 8 | Hand: arm, roll unit, chuck jaws and pins | S 0.15 | tangs, steam | jet gate after every soiled grip (3 s cold, 10 s at 85 °C after class R); arm passes the rear nozzle rail daily | per grip / daily | air |
| 9 | Mast band, X labyrinth, rear lane | S 0.6 | steam, splash | rear nozzle rail, purge air outward | daily | air |
| 10 | Walls, soffit under cabinet and oven, door inside | S 3.5 | aerosol, condensate | two rotary nozzles, insulated sloped soffits (no condensate over food) | daily | fan, 60 min after the meal (HYG-045) |
| 11 | Oven cavity | S/F | roasting splatter | the appliance's own steam-cleaning programme after roasting meals; its drip tray is ware (C2 C-6) | per roast | appliance |
| 12 | Box shelf | S 0.1 | box bottoms | nozzle rail | daily | air |
| 13 | Clean cabinet | clean | — | closed, filtered over-pressure air; wiped by nozzle mist weekly | weekly | fan |

Fixed in-place surface: **Zone F 0.33 m², Zone S ≈ 6.9 m²** (K3: 1.5 m² and 11.5 m²; the three hob shelves and the
shuttle shaft are gone).

### 5.5 Raw and ready-to-eat within one meal

* **Belt**: the red cassette carries only class R work (raw meat and fish, and leek cut before washing, GP-W4); the
  green cassette everything else. Each is washed after its use, so a red cassette never meets RTE food.
* **Drum**: it is the red first-wash station for soil-bearing produce and the mixer for raw mince. After any class R
  job the full wash with the hot rinse runs before an RTE or cooked job; within a class only the quick rinse. Order
  in every menu: produce wash and peel → RTE work → raw animal food last (SM-208).
* **Gully**: flushed at 85 °C after every class R pour, before any S bowl stands in it; S ware never touches raw meat.
* **Tools**: red knife and red tongs for raw meat; the lift racks and the turner touch raw surfaces and are class R
  ware; plating uses the green belt, the green tongs and the ladle.
* **Hand**: touches tangs only; the jet gate after every grip of a class R item; a "soiled chuck" may not grip clean
  ware (software interlock, K6b).
* **Boxes**: raw packs are tipped last and only over the red cassette, the drum or a pan; no box is tipped over an
  open RTE vessel.

### 5.6 Crevices, seals and spray shadows, named

| Item | Why it is a risk | Answer |
|---|---|---|
| Helix root, rolled lip of the drum | weld quality | continuous TIG fillet, ground and electropolished; camera check per wash |
| Bell bushes on the thimble | wet sliding fit behind the drum | not food zone; flushed every wash; lift-off for inspection weekly, bushes yearly (HUM-007 part 1) |
| Belt edges, open PEEK sleeves, roller flanges | soil creeps round edges | belt slack in the washer, 1 mm open gaps both ends; riboflavin rig before selection (risk R2) |
| Tension wedges in the seat | spring crevice in Zone S | one-piece bent spring-steel tongues, no coil springs, sprayed by the rail |
| Tilt shaft lip seal at the pedestal top | dynamic seal in Zone S | drained lantern, 150 mm behind the drum, not above food; yearly (HUM-007 part 2) |
| Z and Y bands, roll lip seal, chuck rod seal | dynamic seals over the work area | Z band in the rear lane; Y band faces up into a gutter; roll seal under an umbrella collar; the chuck seal is the only one that can pass over an open vessel |
| Silicone parts (stud disc, envelope, doctor edge, spatula) | stay wet, take odour | one-piece moulded, dried by the washer fan; replaced yearly |
| S seat ring in the gully | bowl bases stand in a drain | flushed hot before every placement; bowl outside is not food contact |
| Egg cradle pivots | hinge in egg | open pins, the halves fall apart in the washer (G-assembly 7.2) |
| Oven door gasket, motorised hinge | grease | appliance cleaning programme; hinge outside the cavity |

### 5.7 Waste

Wash water, peel slurry and cooking water go through the gully's 2 mm strainer basket and a turbidity sensor to the
drain; strainer solids, belt trimmings (dropped off the nose into a GN 1/3 tray in the nose shelf), egg shells and
cooled frying fat (fat cup) go through the flap-covered waste chute into a closed 20 L bio bin in the front drawer.
No waste crosses an open vessel; no macerator; no recirculated liquor is held (the drum uses fresh water every step).

### 5.8 Water, energy and time per meal (reported, #23)

| | 2 persons | 4 persons |
|---|---|---|
| Drum: one full wash, two quick rinses | 6.5 L, 0.35 kWh | 7.5 L, 0.4 kWh |
| Produce washing in the drum | 3 L | 5 L |
| Gully flushes, hob, wet column, seat | 3 L, 0.05 kWh | 4 L, 0.05 kWh |
| Washer: ware and cassettes | 1 load: 9 L, 0.7 kWh | 2 loads: 18 L, 1.4 kWh |
| Drying fans | 0.1 kWh | 0.1 kWh |
| **In-cell total** | **≈ 22 L, 1.2 kWh** | **≈ 35 L, 2.0 kWh** |
| Dishes, if they share the washer (Q1) | + 9 L, 0.7 kWh | + 9 L, 0.7 kWh |
| Daily wash-down (once a day) | 8 L, 0.3 kWh | — |

K3 (C4 K3-4): ≈ 60 L per 2-person meal with dishes; K3b ≈ 31 L with dishes, the daily wash-down excluded. Next
meal possible at once (drum clean in 10 min, second set and second cassette); everything clean and dry ≈ 60 min
after hand-over at 4 persons, ≈ 35 min at 2.

---

## 6. Numbers before → after

### 6.1 Summary

| Quantity | K3 | K3b |
|---|---|---|
| Wall width | 1450 mm, oven did not fit (C4 K3-1), no washer | **1420 mm** with oven, washer and plating position |
| Heated positions | drum, deck H0, R1, R2, R3 (5) + oven | drum 3.0 kW, hob 3.0 + 2.0 kW (3, COK-002 M) + oven |
| Motion actuators stated | 35 | **10** |
| Actuators, C5-normalised | 25 | **9** |
| Dynamic seals | 19 | **5** (tilt shaft, Z band, Y band, roll, chuck) |
| Novel mechanisms (C5 S4) | 7 | **2**: N1 belt cassette as ware with seat-driven face coupling and resting tools (ramp roller, curl hood); N2 drum on a canned bell with rumbler mode |
| Mechanism types (S3) | 13 | 7: drum, belt cassette, hand, S, hob, oven, washer |
| Series chain B3 (S6) | 12 | 6: drum, S, belt, hand, hob, oven (hold) |
| Single points of failure | drum, shuttle head, dock | hand (every meal, as in K9); drum (dough, wok and continuous-stir meals only) |
| Custom part types | ≈ 65 | ≈ 42 (drum cup and bell, pod, pedestal, yoke and post, three drum inserts, two drum tools, scoop; cassette frame and rollers, seat, six belt tools; gully, blade post, corer nest and tubes, pitter, egg cradle, raft and cradle, lift racks, hook tabs; X box, mast, arm, roll housing, chuck; enclosure, decks, soffits, cabinet, wash tub; stem family ≈ 8) |
| Loose ware (food contact) | 46 | 75 (incl. ravioli stamp, dumpling press and syringe, 6.3) |
| Handling events, B3 4 persons | ≈ 85 (C3 normalised) | **≈ 66**; mean B1–B12 ≈ 43 |
| Cleaning stations (S10) | 6 | 4: drum self-wash, washer, jet gate, nozzle rail |
| Fixed Zone F / Zone S in place | 1.5 / 11.5 m² | **0.33 / 6.9 m²** |
| Crevice and elastomer types (S9) | 16 + 3 (fixed belt) | ≈ 14 (the belt is ware) |
| Special processes (S11) | 3 | 3 (spun clad drum, deep-drawn thimbles with potted magnets, silicone on steel) |
| Skills (vision on deformable food) | 30 (6) | ≈ 30 (7: rumbler stop, spit axis, coring, curl stop, breading pick-up, carving, plating) |
| Water per 2-person meal with dishes | ≈ 60 L | ≈ 31 L |
| Peak power | 11 kW + H0 3 kW | ≤ 9.2 kW by the phase plan: L1 drum 3.0 + motors 0.3; L2 hob limited to 2.8 + S 0.6 for ≤ 60 s; L3 oven 2.2 **or** washer heater 2.0 |
| Loud minutes (NOI-003) | > 5 in B3 and B6 | ≤ 4.5: rumbling 2–3 min (≈ 68 dB(A) at 1 m, door shut [E]), spin 30 s, S bursts ≤ 60 s |
| Coverage, C1 standard N, central | 206 = 83.1 % (224 = 90.3 % with modules) | **≈ 232 = 93.5 %** (range 229–235), 6.3 |
| Machine-part cost | 20 k€ stated, 29–33 k€ re-estimated (C3) | **≈ €9.5–15 k** + appliances ≈ €1.65 k (6.4) |
| C5 simplicity score [E, C5 formulas] | 3.5 | **≈ 6.2** |

### 6.2 The C5 hard limits

| Limit | K3b | Verdict |
|---|---|---|
| ≤ 10 actuators | 10 stated, 9 normalised | met |
| ≤ 5 dynamic seals | 5 | met, at the limit; the tilt seal is the price of a safe self-locking tilt (a 100 Nm canned coupling would slip and drop 22 kg) |
| ≤ 2 novel mechanisms | 2 | met. Argued: curl rolling, nose pick-up of a wet cutlet and all-in creaming are process skills of N1 and N2, each with a proven fallback in the same cell (apron roll, spatula-tongs, whisk cup); the spit is the household apple-peeler principle [K]; the canned bell is the bottom-entry magnetic mixer [K] |
| ≤ 70 events per meal | ≈ 66 (B3) | met |
| ≤ 6 mechanism types | 7 | **exception**: drum and belt are the concept; K9 has 7 as well |
| ≤ 50 loose items | 75 | **missed**: produce tools (spit, corers, pitter, press) and the safe frying set (rack pair, raft) that K3 lacked; K9 has 66 + 8 |
| ≤ 35 custom types | ≈ 42 | **missed by 7**: the drum and belt inserts |
| Chain ≤ 7 | 6 | met |

Score by C5's formulas [E]: S1 9.3, S2 5.1, S3 7.8, S4 6.1, S5 7.2, S6 7.4, S7 5.9, S8 4.7, S9 3.9, S10 4.0, S11 4.0,
S12 4.7, S13 6 (standard axes, the drum lifts off its thimble, the cassette lifts out, appliances as bought): weighted
**6.2** (K3 3.5; S-min 7.1; K9 claims 6.5–7).

### 6.3 Coverage (C1 standard N, 248 meals, 8 excluded by 5.4)

| Step | Meals | Note |
|---|---|---|
| C1's K3 with the modules it can host | 224 | C1 2.3: corer, press, reamer, plug corer, snipper on the arm |
| Modules move to the hand; nothing of the 224 is lost | 224 | the S chopper and cutter cup replace the drum knives and cartridges; the rack pair replaces the 25 mL frying (DM03, FI01 back to class a/b) |
| + DM05 cordon bleu: half-curl fold on the belt (GA-08), crimp by the comb's blunt edge, breaded as 3.4 | +1 | M |
| + DS11 Germknödel: core injected after cooking (GA-11) by a piston syringe pushed by the hand | +1 | M |
| + CK13 Biskuitrolle: apron roll on the tray (Ø 90 is too large for the curl hood) | +1 | M |
| + VG04 stuffed zucchini: halved lengthwise on the belt, seeds out by the seed spoon, filled by the scoop | +1 | M–H |
| + BF14 poached egg: slotted saucer lowered by the hand into 85 °C water in the 1.5 L pot | +1 at risk | L–M |
| + #25: MX06 guacamole (avocado on M2), CK16 banana bread (belt slit) | +2 | M / L–M |
| + IT17, DM33 as square parcels (mandated c): pasta sheeted to 1.2 mm on the belt, filling dots by spoon, second sheet laid by the nose, cut and sealed by a ravioli stamp pressed by the hand | +2 | M; IT17 is W3 |
| + CK17 half-moons by a hinged dumpling press (mandated c) | +1 | M |
| DM12 Kohlrouladen: whole head blanched in the drum, leaves peeled by the tongs (freeze–thaw is out by #27) | 0 (at risk) | L–M |
| Continuous stirring (risotto, polenta) | 0 | the drum stirs; K9's possible −2 does not apply |
| **Central** | **≈ 232–233 = 93.5–94 %** | range 229–235; target 231 met with a reserve of 1–2 |

Designer class (c) ≈ 12 (banana-based BF01, BK04 unbraided loaf, CK02 lined tin, DS10 orange rounds, SD19 and SP09
asparagus, MX02 components, US06, SD22, AS09 crimped half-moons, FR01, CK07 muffins by beaker) ≤ 24, weight-3 ≤ 2.
Still out: AS08, IN07 (thin wrappers), CK12 (strudel). By weight ≈ 95 % [E].

### 6.4 Cost (#22 reported, #28 target)

| Appliances, household, largely as bought | € [E] |
|---|---|
| Domino induction hob (2 zones) + interface board | 300 + 100 |
| Countertop combi-steam oven + motorised drop door and interface | 600 + 200 |
| Slim dishwasher as donor of the wash system | 450 |
| **Appliances in the cell** | **≈ 1,650** (cold storage and shelving lie outside the cell) |

| Machine part | € [E] |
|---|---|
| Drum module: spun tri-ply cup with helix and bell, pod with thimble and 400 W BLDC, pedestal with worm gearmotor and seal, yoke with post and nozzles, 3 kW coil segment and generator, load cells | 1,400–2,200 |
| Belt: two cassettes with belts, seat with face coupling, gearmotor and load cells, six belt tools | 800–1,300 |
| Hand: X/Z/Y linear modules, steppers with encoders, bands, mast and arm, roll unit, chuck with load pins | 2,100–3,700 |
| S: BLDC, thimble, magnet rotor; bought processor cups and discs adapted | 350–650 |
| Custom stainless: enclosure, decks, gully, wash tub, cabinet, soffits, X box (job shop, #21) | 2,500–4,000 |
| Ware (≈ 75 items; bought GN and pots with welded tangs; racks, raft, cradle, blade post, egg cradle) | 1,200–2,000 |
| Controller, power manager, 3 cameras, sensors, wiring | 600–1,000 |
| Valves, nozzles, drain pump, fans, extraction connection | 500–900 |
| **Machine part** | **≈ 9,450–15,750**, say €9.5–15 k |

**Honest reading.** K3b costs about €1.5–2 k more than K9 (€7.8–13.8 k): that is the drum module and the belt.
The €2 k target is missed by 5–7 ×, for the same reasons as in K9: welded stainless enclosure (≈ 30 %), the gantry
(≈ 20 %), ware with welded tangs (≈ 12 %). Cheapest cuts: clip-on tang rings on bought ware (−€800–1,200),
bent-sheet enclosure in Zone N (−€1,000–1,500), printer-class belt modules for X and Y (−€500–1,000), one camera
instead of three (−€200). A realistic floor is ≈ €6.5–7.5 k.

---

## 7. Self-assessment

Scores 1–10 as the critics define them; "before" = the critics' scores of K3 (C3', C4' as adjusted in
`04-decision-matrix.md`); "after" = my estimate for K3b, which no critic has checked yet.

| Criterion (weight) | Before | After | Why |
|---|---|---|---|
| Simplicity (30 %) | 3.5 | **6.2** | 35 → 10 actuators, 19 → 5 seals, 7 → 2 novel, 13 → 7 mechanism types, chain 12 → 6, events 85 → 66; against it 75 loose items and 42 custom types |
| Coverage and food (20 %) | 4.5 | **7** | ≈ 232 meals (93.5 %); Schnitzel in 3.6 mm of fat, Bratkartoffeln from boiled potatoes, probe, leaves spun alone, fond before deglazing, raft; kept: best Bolognese browning, drum wok, continuous stirring; at risk: curl rolling, nose pick-up, all-in cake, banana |
| Hygiene (25 %) | 3.5 | **6.5** | The belt is ware (fatal-if gone); drum ends with moist heat; no chute, no tools over the drum, no wash box; Zone F in place 1.5 → 0.33 m², Zone S 11.5 → 6.9 m². Left: the drum is shared by class R and RTE in time; S bowls stand in the gully; the chuck seal can pass over food |
| Reliability (15 %) | 3.5 | **6** | Fewer parts, torque-limited canned drives (a jammed drum slips, nothing breaks), 22 kg instead of 35 kg, 21 N instead of 105 N, three SPOFs → one (the hand) plus a degradable drum; left: five seals, belt life, the hand's 66 events |
| System fit (10 %) | 5 | **6.5** | 1420 mm with oven, washer and plating; peak 9.2 kW by phases; 31 L per 2-person meal with dishes; one box port, one serving hatch; left: cost 5–7 × €2 k, oven at 1.6–2.0 m, washer needs two loads for 4 persons |
| **Weighted** | **3.85** | **≈ 6.4** | (K6 5.74 and K8 5.68 before their own improvement) |

Remaining weaknesses, in order of consequence:

1. **K3b is K9's hand plus two process machines.** It needs 2 more actuators, 1 more seal, ≈ 9 more loose items and
   ≈ €1.5–2 k more than K9. The drum and the belt earn that only if the customer values continuous stirring, the wok,
   hand-free kneading, washing and peeling in bulk, and laying food down without gripping it.
2. **Four food results are untested**: curl rolling under a hood (Rouladen, logs), nose pick-up of an egg-wet cutlet,
   rumbling against a hold-back roller, all-in Rührkuchen. Each has a fallback inside the cell.
3. **The belt cassette's cleanability** (edges, open sleeves) in a dishwasher at 70 °C is a claim until R1 is run.
4. **The drum is one vessel for raw and RTE work**, separated in time by a 10 min wash; allergen carry-over after a
   quick rinse is still untested (C2 K3-6).
5. **The hand is the single point of failure** for every meal; a drum failure costs dough, wok and continuous-stir
   meals (≈ 25 meals) until service.
6. **Packaging is tight**: the hand works over the drum only when the drum is mouth-up and the arm stays below the
   oven; the oven is a 35 L countertop unit; a 4-person meal needs two washer loads.
7. Loose items (75) and custom types (≈ 42) exceed C5's targets; cost exceeds #28's target 5–7 ×.

---

## 8. Best ideas for the combined machine (K9b)

1. **Lift-off canned drum tilting about its lip, as K9's turning position.** A Ø 260 tri-ply cup on a magnet bell
   over a welded thimble (no seal, torque by lag), tilted by one self-locking worm about its pouring lip, heated by its
   own coil, tools hung on a yoke post. It brings back what K9 gave up (continuous stirring, T kneading) and adds the
   wok, bulk wash, rumble-peel, slip, boil-and-drain and mash — for 2 actuators and 1 seal, in a 460 mm bay with the
   oven stacked above it.
2. **Fixed gully under the fixed lip, with the S thimble in its centre.** Because the lip never moves, the drain and
   the speed spindle can be fixed under it: the drum pours waste into the gully and food straight into the blender
   jug or cutter cup; the reverse helix screws peeled produce one by one into the cutter hopper. Zero actuators;
   replaces K3's swinging gutter and K9's separate drain gully.
3. **Belt cassette as ware.** A 300 mm homogeneous belt in a frame that the seat tensions (spring tongues) and drives
   through a canned face coupling; out of the seat it hangs slack and is washed on edge in the ware washer; red and
   green cassettes. With the hand moving the receiving vessel at belt speed it lays cutlets onto the lift rack,
   Rouladen into the cradle, sheets onto trays and shingled slices onto plates — 1 actuator, 0 seals, no gate.
4. **Ramp-supported, roll-driven roller.** A Ø 70 roller resting on 1 : 10 gauge ramps of its frame, positioned in x
   and turned by the hand's roll axis: the gap is set by position, the press reaction stays in the frame, and a hand
   that can only push 40–100 N sheets pasta to 1.2 mm and flattens meat with 850 N at the surface. Works on the belt
   cassette or on a tray with ramp rails, so K9 can take it without the belt.
5. **Stack by heat and wetness**: oven above the drum bay (the drum's swing envelope ends at z 1560), washer under the
   flat station (its seat plate is the washer's lid), clean cabinet above the belt, nothing above the hob. This is
   how K3b holds drum, hob, belt, oven and washer in 1420 mm.

---

## 9. Risks, cheapest kill experiments, open questions

### 9.1 Failure modes that changed

| Failure | Detection | Recovery (degrade and continue, C3 rec. 7) |
|---|---|---|
| Drum jams or overloads | magnet lag (torque), tilt motor current | the canned bell slips, nothing breaks; reverse, retry; then the job moves to a pot on the hob (stir by the hand at intervals) or the meal is re-planned without dough and wok steps |
| Drum fails its wash check | stripe-light camera, conductivity | intensified wash once; then the drum is locked out and the meal runs on hob, belt and S |
| Belt slips or tracks off | encoder against seat load cells, belt camera | cassette lifted and reseated (tension re-applied); then the second cassette; then tray methods (rolling pin on ramp rails, tongs) |
| Roll does not form in the curl hood | camera: diameter, flap position | belt reverses, slice flattened by the roller, second try; then apron roll on a tray |
| Cutlet not picked up by the nose | seat load cells | spatula-tongs lift it onto the crumbs |
| Hand misses a tang or drops an item | load pins, camera | re-approach twice; dropped items in the gully or on the hob are discarded and the recipe follows the scale (SM-151); otherwise user call |
| Washer late | cycle monitor | second set and second cassette cover one more meal (PERF-005) |

### 9.2 Risks and the cheapest experiment for each

| # | Risk | Why it matters | Cheapest experiment that confirms or kills it |
|---|---|---|---|
| R1 | Belt cassette does not come clean in a dishwasher (edges, open sleeves, inner face) | Decides whether the belt survives at all (C2 K3-1) | €150, 2 days: a bought 300 mm homogeneous TPU belt on two rollers in a bent stainless frame, soiled with dried egg, raw mince fat and flour paste for 60 min, three cycles in a household dishwasher with a 70 °C programme; riboflavin under UV and ATP swabs at edges and sleeves. Kill if any site fails after the hygiene programme |
| R2 | Curl hood does not roll Rouladen or mince logs | B1 (brief, W3) rolling, patties | €80, 1 day: a benchtop conveyor or a 300 mm belt cranked by hand, a Ø 60 half-pipe cut from tube on two guide pins; 12 slices with side folds and floured flap, 3 mince logs. Kill if < 10 of 12 roll tight or the log tears; fallback apron roll |
| R3 | Canned bell cannot carry 40 Nm kneading torque, wears its PEEK bushes or rubs the coil | Every drum job | €400, 1 week: a Ø 110 mag-drive pump or stirrer coupling, a 5 kg cup cantilevered on two PEEK bushes over a thimble, roller-scraper with 1 kg dough; slip torque, bush temperature beside a 3 kW coil, runout at 400 rpm with 0.1 kg imbalance |
| R4 | Rumbling against a hold-back roller in a turning drum peels badly or loses > 20 % | 60 PLP meals, the drum's peeler claim (K3 R6) | €60, 2 hours: knurled disc in a 260 mm pot on a pottery wheel with a fixed paddle, camera stop; 1.2 kg old and new potatoes; weigh loss, count eyes |
| R5 | Nose pick-up of an egg-wet cutlet fails | Breading without tongs (K3 R4) | €50, half a day: 300 mm belt on a Ø 22 nose on a drawer slide, tray tilted 5°; 20 cutlets. Kill if < 18 come up unfolded (fallback tongs costs ≈ 4 events per meal) |
| R6 | Packaging: arm between mouth-up drum and oven, hook-rod oven loading, hob receiving zone | The 1420 mm claim | 1 day CAD with a real countertop combi-steam oven and household domino hob; check every pose of 3.3–3.12 |
| R7 | Allergen carry-over in the drum after a quick rinse | C2 K3-6; mustard, egg, gluten | €100: mustard and egg mass in the drum, 60 s quick rinse vs full wash; lateral-flow allergen swabs |
| R8 | S bowl seat in the gully gets contaminated | Hygiene of the gully-S idea | €50: E. coli surrogate (fluorescent) poured as "class R water", 85 °C flush, swab the seat ring and the bowl base |
| R9 | Hot rinse does not reach A0 ≥ 60 on the coldest wall element (helix root, lip) | C2 R-3 | €100: thermocouple loggers at helix root and lip during the 2 min hot tumble |
| R10 | TPU belt ages at 70 °C twice a day | Belt as a yearly part (HUM-007) | supplier data; 300 dishwasher cycles on a belt strip, tensile and surface check |
| Shared | Pan-pair flip, rack-pair Schnitzel, GA-20 raft, egg cradle | as in K9 | G-assembly bench tests (€40–100 each), run once for all concepts |

### 9.3 Open questions

1. **Q1 (C5)**: may the one washer take dishes too? If not, the serving module needs its own dishwasher.
2. Is a ≈ 35 L countertop combi-steam oven enough (COK-006 asks ≥ 35 L; B5 bakes two trays per run)?
3. Is "Stampf" texture accepted for Kartoffelpüree (C1: yes), or is the lever ricer added (+1 item, +3 events)?
4. Is all-in mixing accepted for Rührkuchen and other creamed cakes, or must S get a larger beater bowl?
5. Ruling: leek cut before washing on the red (class R) cassette — acceptable as "soil-bearing produce is class R"?
6. Belt material: polyether-TPU (cut and wear resistance) or platinum silicone (dough release, heat) — R1 and R10 decide.
7. Pre-formed paper liners for loaf tins as a consumable (HUM-004)?
8. For K9b: is continuous stirring plus the wok worth a drum bay (2 actuators, 1 seal, ≈ €1.5 k), or does the customer
   accept interval stirring and pan stir-fry (K9's default)?

