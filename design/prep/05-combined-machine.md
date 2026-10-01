# Meal preparation — Round P5: combined machine K9 "EINHAND"

**K9 EINHAND** ("one hand"): one serial gantry hand, one deck, one washer for ware and dishes, household
appliances used largely as bought. It is the simplicity-first hybrid H-S1 of `04-decision-matrix.md` §6, worked
out as one machine. Skeleton from K6 (loose ware, tang grip, the washer as the only cleaning point); seal-free
drives from K8 (canned magnet couplings T and S); press from K8 (screw cassette driven by torque) with K6/K5 end
plates; gap modules from G-produce and G-assembly-meat. K7 is not used (DECISIONS #27): no cold plate, no
surface-freezing, no tempering, no chill-slice-reheat — no step that changes the food against traditional
preparation.

Decision state: DECISIONS #1–28. Markers: **[D]** from a concept, critique or gap document; **[C]** calculated
here; **[E]** engineering estimate; **[U]** unknown, a test or supplier answer decides. Nothing has been built.

---

## 1. Design principles and hard limits

### 1.1 Principles (binding for K9)

| # | Principle | Source |
|---|---|---|
| P-1 | **Everything that touches food is loose ware** and goes to the one washer. No fixed cutting, forming or plating surface; the hob glass is touched only by ware, the hatch drawer is covered by a ware tray | C2 R-1, K6 |
| P-2 | **Nothing above an open vessel**: the three sealing bands and all drives sit in the rear lane (y 0–120) or in closed boxes; only the closed arm tube and the wrist pass over food; fume intake, oven mouth and stores are never in the projection of an open food vessel | C2 R-2 |
| P-3 | **One hand, no dock, no tool changer**: the gantry tips opened boxes, carries ware, holds tools and works passive fixtures. A station is added only if it carries meals that no recipe route or passive part can carry | C5 A1, §6.3 rule 2 |
| P-4 | **No new seal**: rotation through the deck by canned radial magnet couplings in welded thimbles; press force made inside ware from the wrist's roll torque | K8 R-can, R-torque; C3 §7 ranks 2, 10 |
| P-5 | **Recipe routes before mechanisms**: potatoes cooked in the skin and riced or slipped; carrots scrubbed; leek cut before washing; sprigs in an infuser; stirring in intervals where the traditional cook also stirs in intervals | C1 §10.3, GP-P1, C5 §6.1 rank 1 |
| P-6 | **Authentic result (#27)**: no texture-changing aid. Every adapted method is the one a home cook uses (pins or raft for Rouladen, lift rack for Schnitzel, pan pair for pancakes) | DECISIONS #27, MEAL-013 |
| P-7 | **Food rules C1 §10.3** in every recipe: fond before deglazing; fried items finish last; 200–250 mL fat for Schnitzel; never invert a pan with fat > 30 mL; core probe for steak, roast, mince, poultry | C1 A-2…A-5 |
| P-8 | **Hygiene rules C2 R-1…R-12** as written: moist-heat disinfection only (A0 ≥ 60, logged on the coldest item), one-way flow at the washer, red/green ware, unwashed produce is class R, grit to a strainer before any pump | C2 §8.1 |
| P-9 | **Degrade and continue**: every food-process failure has an automatic path (redo, fallback method, or serve without the item and tell the user) | C3 §8 rec. 7 |
| P-10 | **One ware interface**: flat tang at rim height on one side, 6 × 32 × 60 mm, two Ø 8 holes, ferritic stainless (1.4521) insert; equal rims for pan pairs; GN 2/3 plus round Ø 220 / Ø 280 | C4 R-2, R-3, K6 |
| P-11 | **Household appliances largely as bought (#28)**; cost split into "appliances" and "machine part" and reported honestly | DECISIONS #28 |

### 1.2 Hard limits (C5) and where K9 stands

| Limit | K9 | Verdict |
|---|---|---|
| ≤ 10 motion actuators | **7** in the cell (X, Y, Z, roll, chuck, T, S); 8 with the oven door; 9 with the hatch drawer of the serving column | met |
| ≤ 5 dynamic seals | **4**: sealing bands X, Z, Y; one lip seal of the sealed roll unit | met |
| ≤ 2 novel mechanisms | **2**: N1 electro-permanent-magnet (EPM) tang chuck with form-fit pins, including roll-driven tongs; N2 generic produce module (spit-and-shoe paring, grid skinning). The screw cassette is the Italian *torchio* press driven by a motor instead of a crank [K]; it needs a cleaning test, not new physics | met |
| ≤ 70 handling events per meal | **~70 during the meal** (B3, 4 persons, §5); **~105 including dish return and washer loading after serving** | met for the meal; the dish duty of #6 (≈ 35 events) was counted by no K-concept |
| ≤ 6 mechanism types, chain ≤ 7, ≤ 50 loose items, ≤ 35 custom types | 7 types (gantry, canned drives, screw cassette, hob, oven, washer, hatch drawer); chain 6 for B3; **~66 loose items** (+ 8 second-set items); ~36 custom types | items over (§3.6, §8) |

What the limits cost: without the turning hob positions that H-S1 proposed (they need a custom hob with thimbles
through the glass, against #28, and were a third novel mechanism), the hand stirs. Long stirring steps are run as
interval stirring, 20–30 s every 1–3 min, which is how a home cook stirs red cabbage, béchamel and risotto
anyway. Continuous stirring for 20 min is not offered; the hand's time is the price (§5, B1, B9, B10).

---

## 2. Selection table

Criteria: **F** food and coverage, **Hy** hygiene, **S** simplicity, **R** robustness, **Fit** system fit and cost.

| Function | Chosen mechanism | From | Why it beat the alternatives | Conf. |
|---|---|---|---|---|
| Receive box | Transport sets the GN box (lid removed at a lid station outside the cell, C4 R-4) on the **box shelf** (serving column, upper rear); the hand grips the box's moulded tang with a ferritic insert | C4 R-4, R-9; C5 A1 | Beat tipper and hourglass docks (2–6 actuators, 1–2 seals): **S, R** | H |
| Receive sealed pack | Opened just in time outside the cell (C4 R-5), delivered upright in a GN 1/3 carrier; the hand pours, spoons or squeezes | C4 R-5 | Beat in-cell openers: **S, Hy** | M–H |
| Dose granular, powder, liquid | **Tip the opened box by the roll axis**, loss-in-weight on the wrist load cell (±3 g), straight into the target vessel; the box lip is held on a fixed point while tilting (lip-pivot path, coordinated Y–Z–roll) | C5 A1; K3 lip-pivot geometry; K2 load pins | Beat docks and dosing lids: **S** (0 actuators). Cohesive powders by scoop-and-trim (GA-39) | M–H |
| Dose 0.2–5 g | Box tipped over the **0.05 g cup scale S0**, small roll taps; cup emptied into the vessel | K6 S0 | Beat vibrated mesh lids (humid air, G-assembly 7.4): **R** | M |
| Dose viscous, fats | Spoon tool or the cassette's filler nozzle from the opened pack; butter cut from the block by the wire bow | K5 syringe, K8 U15 | Beat frozen pucks (K7, out by #27): **S, F** | M |
| Dose pieces, meat, frozen, long goods | Box tipped onto a GN tray, count and pose by camera; picked by fork, turner or roll-driven tongs; spaghetti by the log-roll weir (GA-29) | K6, GA-29 | Beat suction and grabs: **Hy, S** | M–H |
| Eggs | **Passive egg fixture**: bottom strike, hinge-open cradle, slotted saucer, per-egg camera, beaten egg through a 2 mm strainer | G-assembly 7.2/7.3; C5 A2 | Beat equator scoring, 3-actuator egg modules: **S, R** | H |
| Wash produce | **Dunk basket over a 40 mm sediment zone** in a red wash pot, plunged by the hand; dump into the drain gully through a 2 mm strainer with turbidity sensor; leek cut first; spin on S | GP-W1, GP-W4; K8 S | Beat drum wash, spray-in-basket, bubble bath: **F** (grit physics), **S, Hy** (R-5 red path, no fixed sink) | H |
| Peel, core, stone (#25) | **Generic produce module, §4**: spit on the roll axis against a fixed blade post with three depth shoes; grid skinning of soft fruit; blanch-and-slip; cook-in-skin; knurled drum on T; tube corers, plunger pitter | GP-11, GP-Z4, GP-P1/P2, GP-61; K1/K6/K8 spit; grid skinning new | Beat iris peeler, rasp can, single-fruit devices: **S** (3 mechanisms for the PRP-039 list), **F** | M |
| Cut, dice, slice, grate | Knife on a board (draw cut by Y); **screw cassette** (tube Ø 100 × 160, Rd 28 × 6 screw turned by the roll axis, 2.5 kN) with bought push-dicer grids 6/10/15, slice and wedge plates; grater drum and chopper cup on S | K8 PZ, K6/K5 plates, C1 §7 rank 1 | Beat K7's under-deck press (1 actuator, 2 rod seals, a fixed press table) and K5's 8 kN column: **S** (0 actuators, 0 seals), **Hy** (all ware) | M–H |
| Mix, knead, whip, purée | Kneading bowl Ø 280 on the canned **turntable T** (25 Nm, 0–500 rpm) under a hung roller and scraper (Ankarsrum principle); blender jug, chopper cup, whisk cup on the canned **speed spindle S** (6000 rpm) | K8 T and S, C3 §7 ranks 1–2 | Beat wrist spin (2 lip seals over food, K6), planetary heads above the bowl: **S, Hy** | M–H |
| Form, roll, stuff, bread | Patties extruded through the cassette's Ø 70 orifice and wire cut-off, then pressed flat in the pan with the turner; rolling pin with gauge rings on rails (2–10 mm; pasta 1–1.5 mm); ravioli plate for square parcels (IT17, DM33); hinged dumpling press for half-moons (CK17, AS09); breading line in three GN 1/3 trays; Rouladen with side folds, dry floured flap and the **GA-20 raft**; GA-01 peel for stacks | GA-01/-08/-20, household tools [K] | Beat mat line (K4), belt (K3), cold plate (K7, out), frying book (K5): **S** (passive ware), **F** | M |
| Cook with stirring | Household 4-zone hob; the hand stirs in intervals with paddle or whisk; lidded braising where tradition does it | #28; C5 §7 | Beat turning hob positions: **S, Fit** (no custom hob, no third novel mechanism); costs hand time | M–H |
| Fry and flip | Pancakes, omelette, Rösti: **pan pair** (Ø 280 pan + shallow flip pan with drip skirt), ≤ 30 mL fat, release check; Schnitzel, fish: **220 mL fat (3.6 mm) on a lift-rack pair (GA-36)**; steak, patties: turner, singly | G-assembly 7.1, GA-36; C1 A-3 | Beat frying book (2 actuators, 2 seals near fat), thin-fat flips: **S, F** | M–H |
| Bake, roast | **Bought countertop-class combi-steam oven** (~€500–700), turned with its mouth into the cell, door replaced by a driven side-hinged door | #24, #28, C4 R-7 | Beat built-in 595 mm ovens (do not fit the depth turned), custom cavities: **Fit** | M [U] |
| Drain | Perforated basket in the 5 L pot lifted and held above the pot; pour-off through a strainer lid into the gully when the water is waste | K6, K8 | **S** | H |
| Transfer | Pour by roll about the vessel lip; empty with a silicone-lipped spatula; weigh in the wrist | K6, K2 | **S** | H |
| Carve | Boneless roast in the **GA-14 V-trough with gauge plate**, scalloped blade drawn by Y; braises cut hot at 8–10 mm (thicker, traditional); poultry roasted as parts (R-06 b) | GA-14 | Beat belt guillotine (K3), microtome (K5); chill-slice-reheat dropped (#27): **S, F** | M–H |
| Plate, portion | Spring plate dispensers, plate fork; ladle, turner, tongs, ring mould; plating on the **hatch drawer tray** inside the cell; finished plates held ≤ 5 min in the warm hatch zone | C4 R-11 | Beat a serving manipulator: **S** | M |
| Wash ware and dishes | **One side-loading wash chamber** using the wash system of a bought household slim dishwasher (pump, heater, spray arms) in a stainless tub; hygiene programme with 10 min hold at 70 °C (A0 ≈ 60); items hung on edge by their tangs; dishes in the same chamber (assumption Q1) | C2 §6 rank 1, C4 R-10, #28 | Beat in-cell wells (two chambers), tub wash (K8), wash lathe (K2), a separate dish washer: **S, Fit** | M |
| Clean the cell | Fixed nozzle rail at the soffit rear edge and in the X-box face; fan and extraction to dry; hob glass scraped by a stem scraper and squeegeed to the gully; jet gate for the chuck | C5 A4, C2 R-7 | Beat lance wash-down (K1, K2, K5): **S** | M |
| Waste | Closed chute in the deck to a 20 L bin in a front drawer; gully strainer emptied into it; fat into a fat cup (ware) | C2 R-8, K6-7 fix | **Hy, S** | H |
| Core temperature | Wireless probe in a stem holder, placed by the hand | C1 §7 rank 6 | **F** (FSF) | H |
| Hot-holding | Oven 70 °C vented for crisp items ≤ 10 min; lidded pots on keep-warm; warm hatch zone for plates | C1 A-4 | **S** | M |

---

## 3. The machine

### 3.1 Whole-machine width (PHY-004 minimum configuration)

| Module | Width | Contents |
|---|---|---|
| Cold storage | 1200 | fridge + freezer shells (#28: ~€1,000 household class), box positions per C4 3.1 |
| Ambient storage | 450 | shelving and box racks (C4 floor value; marginal, see Q4) |
| Serving and dish column "W/S" | 600 | hatch drawer, plate dispensers, glass and cutlery store, box shelf, waste bins |
| Process module "P" | 900 | hob, fixture socket with T, the gantry's main work area |
| Oven-and-wash column "O" | 450 | wash chamber (z 870–1400) under the oven (z 1400–1850) |
| **Total** | **3600** | ≤ 3600 M met; the cell's share (P + O) is **1350 mm = 37.5 %**; with W/S, which the same hand serves, 1950 mm |

The gantry spans W/S, P and O (machine X 1650–3150 for the mast; O is reached by pushing ware in +X). The
transport gallery runs at z 2000–2200 over the whole length (C4 R-9). Height 2200 (PHY-002), depth 600.

### 3.2 Front view (fronts removed) and top view

```
 z (mm)                         machine X (mm)
      1650              2250                      2850     3150             3600
 2200 +-----------------+------------------------------------+----------------+  transport gallery
 2000 +=== X-axis dry box along the rear wall, mast travel X 1680-3120 ==========+
 1950 | plate dispenser |  clean-ware cabinet  |  oven-load    |  OVEN          |
      | flat | deep     |  (rear spring flaps, |  corridor     |  countertop    |
      | glasses, cutlery|   insulated soffit)  |  (kept free)  |  combi-steam   |
 1450 | box shelf (rear)|______________________|               |  mouth -X      |
 1400 |-----------------+   fume slot at rear  |               +----------------+ 1400
      |  free arm space |                      |               |  WASH CHAMBER  |
      |                 |   arm space over the hob and socket   |  side door -X  |
  900 | hatch drawer    |  HR1  HR2 / HF1  HF2 | PS socket + T |  z 870-1400    |
  870 +=================+======================+===============+================+ deck
      | waste bins,     | hob body, T motor,   | electronics,  | sump, pump,    |
      | S motor, gully  | front drawer bin     | power manager | heater, chem.  |
  100 +-----------------+----------------------+---------------+----------------+ plinth
```

```
 y 580 +------------------------------+----------------------+-------------+---------------+
 front | hatch drawer tray, 2 plates  | HF1 Ø210   HF2 Ø180  | PS fixture  | wash chamber  |
       | (slides 300 out to present)  | front zones          | socket      | (O column,    |
 y 300 |------------------------------|----------------------| 300 x 280   |  430 x 440,   |
       | S | S0 | E | DG + spout|WC| J| HR1 Ø145   HR2 Ø210  | T thimble   |  z 870-1400)  |
 y 120 +------------------------------+ rear zones           | centre      |               |
       |=============== mast lane y 0-120: mast hangs from the X carriage ==|               |
 y 0   +-------------------------------------------------------------------+---------------+
      1650                          2250                   2850         3150            3600
 S speed spindle  S0 cup scale  E egg fixture  DG drain gully with tap spout  WC waste chute  J jet gate
```

The household hob (590 × 520) is set flush at y 60–580; its rear 60 mm lie under the mast lane, where no pot
stands. At most three of its four zones carry 4-person vessels at once (Ø 280 pan front left, Ø 220 pots on two
other zones), which meets COK-002 M (3 positions); the fourth zone takes a small pot (S level).

### 3.3 Kinematics, actuators and seals

| # | Actuator | Type and rating [E] | Travel | Seal / penetration |
|---|---|---|---|---|
| 1 | **X** | toothed-belt linear module in the rear dry box, stepper-servo, 1.5 m/s | 1440 mm (X 1680–3120) | stainless sealing band in the box's lower front face, drip lip and gutter; behind the mast lane, not above food |
| 2 | **Z** | covered ball-screw module on the fixed hanging mast (80 × 120, foot at z 900), 400 N, brake | 1000 mm | sealing band on the mast's front face, in the rear lane |
| 3 | **Y** | closed arm tube 70 × 70, length 520, internal belt drive, cantilevered from the Z carriage | 440 mm (reach y 140–580) | sealing band on the arm's **side** face under a drip lip, arm sloped 3° to the mast; the one sealed slot that passes over food (C2 K6-2, accepted and listed) |
| 4 | **Roll** | sealed roll unit at the arm tip (stepper + planetary in a stainless housing), continuous rotation, 30 Nm peak, 0–150 rpm, slip ring inside | ∞ | one PTFE lip seal on the output shaft (LRU, yearly) |
| 5 | **Chuck** | dual EPM (electro-permanent magnet) face on the roll output: centre EPM turns with the roll; ring EPM fixed to the housing; two fixed conical pins Ø 8 in each face; 6-axis load cell inside the housing | 0 (switched, no moving part) | none |
| 6 | **T** turntable | NEMA 34 stepper + 10:1 planetary under the deck, inner magnet rotor in a deep-drawn thimble Ø 90 × 50 welded into the socket plate | 25 Nm, 0–500 rpm | none (canned) |
| 7 | **S** speed spindle | 600 W BLDC under the deck, thimble Ø 40 × 20 | 1.5 Nm, 0–6000 rpm | none (canned) |
| 8 | Oven door | gearmotor at the replaced door's vertical hinge (front edge) | 0–95° | appliance |
| 9 | Hatch drawer (serving) | belt drive, the front flap opened by the drawer's own cam | 300 mm | in the serving front |

Not counted: valves (8), pumps (wash, drain, gully), fans (2), the wash chamber's door (passive, side-hinged,
opened by the hand at its tang, spring- and magnet-closed), the cabinet flaps (passive).

**The chuck (N1).** A tang presses onto the two pins; the centre EPM is switched on and holds it with ≈ 400 N
pull-off on a 6 mm ferritic plate [E, commercial EPM grippers]; the pins take shear and torque. A 4 kg pot at
160 mm puts 6.4 Nm on the face [C]; the pull-off moment about the face edge is ≈ 400 N × 30 mm = 12 Nm [C],
margin ×1.9. **Tongs and pincers are worked by the roll**: such tools have a second tang ring that the fixed
ring EPM holds, so turning the roll turns a cam inside the tool that closes the jaws (K8's "torque in the ware").
Every grip is checked by the load cell (mass and moment expected for that item) and by an EPM flux sensor.

**What the hand can do**: lift ≤ 6 kg at 160 mm; pour by roll about y; push or pull 100 N at y ≤ 250 (rear),
40 N at the front; turn 30 Nm (cassette, spit, tongs); no tilt about x — every item is designed to be used from
one side (tangs face the rear), which is the price of a 5-axis hand.

### 3.4 Stations

| Station | Where (X, y) | What it is | Fixed food contact? |
|---|---|---|---|
| Hob HF1, HF2, HR1, HR2 | P, X 2255–2845 | household 4-zone induction hob (€500), touch electronics replaced by an interface board (COK-023); power limit set to 2 × 2.8 kW | glass only under ware |
| PS fixture socket | P, X 2855–3145, y 300–580 | stainless plate with two locating pins, a torque anchor socket and the T thimble in its centre. Takes: screw cassette, blade post, corer nest, carving trough, Rouladen cradle, kneading bowl on T, knurled peeling drum on T | no (fixtures are ware) |
| S, S0, E, DG, WC, J | W/S rear row, y 120–290 | speed spindle; 600 g / 0.05 g cup scale; egg fixture seat; drain gully Ø 130 with 2 mm strainer basket, tap spout (cold / 45 °C) and turbidity sensor; waste chute with flap; jet gate (four 85 °C fan jets in a drained box, for the chuck face) | gully strainer (ware) |
| Hatch drawer | W/S front, y 300–580, z 900 | drawer carrying a removable stainless tray (ware) for two plates; warmed from below (150 W) and by the oven column's waste heat | tray is ware |
| Plate dispensers | W/S, z 1450–1950 front | two spring-lift dispensers (flat Ø 280, deep), top plate always at z 1900 | no |
| Glass and cutlery store, box shelf | W/S rear | 8 glasses, 8 small plates, cutlery caddy; box shelf for 2 GN 1/3 boxes under the transport port | no |
| Clean-ware cabinet | P, X 2250–2850, z 1450–1950 | closed stainless cabinet over the hob with a 50 mm insulated, 3° sloped soffit draining to the rear gutter; opened only from the rear lane by spring flaps; filtered air at slight overpressure | no |
| Oven | O, z 1400–1850 | see 3.7 | ware only |
| Wash chamber | O, z 870–1400 | see 3.8 | — |

### 3.5 Hob positions and the phase plan

Zones (typical household 2 × 2) [E]: HF1 Ø 210, 2.3 kW (boost 3.0); HR2 Ø 210, 2.3 kW; HF2 Ø 180, 1.8 kW;
HR1 Ø 145, 1.4 kW. The hob's own power limiter is set to 2.8 kW per side (left pair on L1, right pair on L2).

| Phase | Loads | ≤ kW |
|---|---|---|
| L1 | hob left pair (HF1 + HR1) 2.8; fridge 0.15; control 0.15; transport 0.2 | 3.3 |
| L2 | hob right pair (HF2 + HR2) 2.8; freezer 0.15; T, S, gantry 0.4 average (S peak 0.6 for ≤ 60 s) | 3.35 |
| L3 | oven ≤ 2.2 (countertop class) **or** washer heater 2.0; when the oven only holds (≈ 0.8 average) the washer may heat at 1.5 | 3.0 |

COK-004 (4 L to 95 °C in ≤ 11 min) is met on HF1 boost only while HR1 is off [C: 1.34 MJ / 2.4 kW ≈ 9.3 min].

### 3.6 Ware list

B = bought, B+ = bought with a welded tang (1.4521 insert), C = custom. Red items are for class R.

| Group | Items | No. |
|---|---|---|
| Pans and pots | frying pan Ø 280 × 50 tri-ply B+ ×2 (red/green use within a meal); shallow flip pan Ø 280 with drip skirt C ×1; pot Ø 220 × 150 (5 L) B+ ×2; pot Ø 220 × 90 (3 L) B+ ×1; pot Ø 160 (1.5 L) B+ ×2; braiser Ø 280 × 100 (5.5 L, oven-safe) with lid B+ ×1; small braiser Ø 200 (1.8 L, A-8) B+ ×1; lids Ø 280 ×1, Ø 220 ×2, Ø 160 ×1, strainer lid Ø 220 ×1; pasta/potato basket Ø 205 ×1 | 17 |
| GN and oven ware | GN 2/3-20 ×3 (tray pizza, sheet, bench); GN 2/3-40 ×2; GN 2/3-65 ×2 (lasagne, gratin, mixing); GN 2/3 lid ×2; GN 1/3-40 ×4 (breading line, mise en place); lift-rack pair GA-36 ×1; loaf tin 30 cm with paper liner and loose floor (K5) ×1; springform 26 ×1 | 16 |
| Prep ware | PE-HD board GN 2/3 on a tanged steel carrier, red and green ×2; red wash pot Ø 220 with dunk basket and 40 mm sediment zone ×1; kneading bowl Ø 280 (10 L) for T ×1; T-ware: knurled peeling drum ×1, spinner basket ×1; S-ware: blender jug 2 L, chopper cup 0.6 L, whisk cup 1 L ×3; reamer ×1; grater drum ×1; fat cup ×1 | 13 |
| Screw cassette | tube Ø 100 × 160 with screw head and piston ×2 (raw / RTE); plates: grids 6, 10, 15 (bought push-dicer grids in a welded rim), slice 5 mm, wedge 8, ricer 3 mm, Spätzle 6 mm, orifice Ø 70 with wire cut-off, garlic 3 mm, filler nozzle Ø 18 | 12 (2 tubes + 10 plates) |
| Stem tools (tang, drip collar, stem) | chef's knife ×2 (red/green); scalloped slicing blade ×1; turner ×2; roll-driven tongs ×2 (red/green; also glasses); ladle ×1; silicone-lipped spatula ×2; paddle ×1; balloon whisk ×1; fork-spit ×2; seed spoon ×1; corer tubes Ø 14/22/42 ×1 set; plunger pitter ×1; probe holder + wireless probe ×1; cups 50/250 mL ×2; spoon 5 mL ×1; plate fork ×1; glass-ceramic scraper ×1; squeegee ×1; hung kneading roller + scraper (for T) ×1; rolling pin with gauge rings ×1 | 30 |
| Fixtures (on PS or deck) | blade post with three depth shoes; corer nest; GA-14 carving trough; Rouladen comb cradle + GA-20 raft fork; ravioli plate GN 2/3; hinged dumpling press; egg cradle + slotted saucer + 2 mm strainer; cutlery basket; hatch trays ×2 | 11 |
| **Total** | | **≈ 99 pieces counting plates and pairs; ≈ 66 handled items** (sets counted as one) |

**Second set for the next meal within 30 min (PERF-005):** one frying pan, one 5 L pot, one board, one chef's
knife, one tongs, one GN 2/3-40, one turner, one ladle — 8 items in the cabinet, because the washer needs
≈ 60–90 min for the first meal's ware and dishes (3.8). C5's "≤ 50 loose items" is not met; the list is K6's
93 items cut by the dock, egg cracker, wells, wrist tools and cold-ware.

### 3.7 Oven integration (#24, #28)

* **Appliance**: a countertop-class combi-steam oven, ~30–36 L, external ≈ 490 W × 400 H × 450 D [U], ~€500–700,
  tray ≥ 0.09 m² (COK-006 asks ≥ 35 L: Q5). It stands in the O column with its mouth facing −X into the oven-load
  corridor (P, X 2850–3150, z 1400–1850). Its width (≈ 490) lies along the depth (fits 560 inner), its depth
  (≈ 450) along X (fits the 450 column). The 595 mm built-in ovens do not fit turned (C4 3.1) and are not used.
* **Modifications (as few as possible)**: (1) the door is replaced by a side-hinged door with a gearmotor at the
  front hinge and the oven's own door switch kept; (2) the control panel is bypassed by an interface on its
  control board (start, mode, temperature, probe) — COK-023; (3) none else; water tank refilled by the hand from
  the tap spout, or plumbed (S).
* **Loading**: the hand carries the GN 2/3 tray by its short-side tang and pushes it in +X along the oven's own
  rails; the mast stops at X 3120 and the tray (354 long) reaches X 3480 [C].
* **Door path**: the door swings into the corridor along the front wall (y 560–580) — not over an open vessel; its
  lower edge has a drip gutter. Rule: the door opens only when the corridor is free and the pot under its swing
  (HF2 front zone) is lidded.
* **Cleaning**: food is always in ware; the cavity sees spatter and steam only. The oven's own steam-clean and
  descaling programmes run after roasts; a weekly wipe is not possible, so burnt-on soil must be prevented by
  lidded roasting and liners. Honest gap (C2 C-6): if the cavity soils anyway, the human wipes it (HUM budget).

### 3.8 The washer (one for ware and dishes — assumption Q1)

* **Build**: tub 430 (X) × 440 (y) × 500 (z) welded stainless, side door facing −X; inside it the wash system of a
  bought household slim dishwasher (pump, heater, upper and lower spray arms, softener, dosing, control board):
  the "appliance used largely as bought" of #28, ~€450, re-housed. Sump and pumps under the deck in O.
* **Loading**: items are rolled to stand on edge (the plane perpendicular to X) and pushed in +X onto two
  tang rails (ware, pots, trays) or a comb rack (plates, at 25 mm pitch); glasses in a basket; cutlery in the
  cutlery basket. Capacity per load [E]: 14 plates + 6 glasses + cutlery, **or** 8–10 ware items.
* **Programme**: pre-rinse, 55 °C wash, **hold at 70 °C for 10 min (A0 ≈ 60 [C])**, rinse, hot-air dry with the
  door ajar to the extraction: ≈ 30 min per load [E]. Raw-meat ware always in a load that runs the hold; the tank
  water is not reused between loads (household principle, C2 R-7 met).
* **Per meal (4 persons, 2 courses)**: 3 loads (ware during the meal when the oven is off; dishes after) →
  everything clean ≈ 70–90 min after serving [E] (PERF-005 M 90 min: marginal).
* **One-way flow**: soiled items go in at the door; clean items come out the same door after the cycle, never while
  soiled items stand outside waiting — the hand first empties the chamber to the cabinet, then loads. Dirty
  dishes wait on the hatch tray, not in the cell.

### 3.9 Serving and plating path

Plate from dispenser (W/S, z 1900) → plate fork → hatch tray (z 900) → components placed from the hob by ladle,
turner, tongs, ring mould → finished plates wait ≤ 5 min in the warm hatch zone (60–70 °C) → drawer slides
300 mm out, flap opens, two plates presented (SRV-011 M); the other two follow within ≤ 60 s. Plating time for
4 plates × 4 components ≈ 16 placements × 12 s ≈ 3.5 min [E]; SRV-009 (3 min first to last) is met because the
plates are released together. Returns: the human puts dishes on the drawer (any order); the drawer retracts; the
hand tips scraps through the cutlery basket held over WC, loads the washer, swaps the hatch tray (SRV-027).

### 3.10 Interfaces

| To | Interface |
|---|---|
| Storage and transport | box port above the W/S box shelf; plain GN 1/9–1/3 PP boxes with a moulded tang (ferritic insert), lid removed outside; opened STOW packs in a GN 1/3 carrier; ≈ 25 box moves per full meal at 20 s; a buffer place on the shelf (TRN-008) |
| Cold store | prepared intermediates in lidded boxes returned via the box shelf (PRP-036); frozen stock portions (UO-96) |
| Ingestion | none directly; garlic peeled at ingestion is not needed (5.6 permits peeled cloves; Q11) |
| Utilities | 3 × 16 A phase plan (3.5); cold water to the spout, the oven tank and the washer; one drain (washer, gully); one extraction to the shared condenser-dehumidifier (C4 R-12) |
| Human | waste drawer (organic 20 L, emptied 2 × a week), detergent and salt for the washer, the oven cavity if soiled, service through removable fronts |

---

## 4. Generic produce module (#25, PRP-039)

The customer's rule — "take the skin off and remove the seeds" — is turned into **four generic principles**,
chosen per item by its firmness and shape, not by its name. All tools are ware; all steps run over a red catch
tray or the gully; the camera checks every piece (residue ≤ 5 % of surface, no stone fragment > 2 mm).

| Principle | How | Items (PRP-039 list and more) | Conf. |
|---|---|---|---|
| **G1 Pare on the spit** (firm, roughly convex) | Item impaled pole to pole on the fork-spit held by the chuck; the roll turns it at 30–120 rpm while Y traverses it past the **blade post** on PS. The post carries one blade with three sprung depth shoes on three faces: 1 mm (thin skin), 2.5 mm (tough skin, onion tunics, GP-11), 5–6 mm (pith and rind, "à vif", GP-Z4). Top and tail by knife first; camera checks, second pass offset 60° | apple, pear, cucumber, courgette, kohlrabi, celeriac (halved), beetroot (cooked: slips), mango (whole, stone left in the core), kiwi, orange, lemon, pineapple (S), melon halves, ginger (thin shoe), white asparagus (spit along the spear, 1 mm shoe, L–M), onion (S upgrade, #9) | M |
| **G2 Grid skinning** (soft) | Item halved (avocado, kiwi, mango cheek, banana lengthwise), laid **skin up** on a dicing grid of the screw cassette or a perforated plate; the piston (or turner) presses the flesh through; the skin stays on the grid and is lifted to waste. Gives dice or mash | avocado (guacamole, MX06), banana (mash, CK16), ripe mango, kiwi, papaya, cooked pumpkin and squash | M [U]: new |
| **G3 Blanch and slip** (thin skin over soft flesh) | Score a cross, dip in boiling water 20–40 s in the basket, cold bath, rub in the spinner basket on T at 60 rpm with water | tomato, peach, apricot, plum (where peeled), almonds | H [K] |
| **G4 Cook in the skin** (tubers) | Boil in the skin, then rice (skins stay in the ricer plate) or slip; raw-peeled uses on the **knurled drum on T** with camera stop (GP-P2) | potato, beetroot, celeriac for mash, sweet potato; carrot scrubbed in the drum | H / M–H |

**Seeds, cores, stones** — three tool families, one motion each (push by Z near the rear, ≤ 100 N, or the screw):

| Family | How | Items |
|---|---|---|
| **C1 Tube corers** Ø 14 / 22 / 42 with ejector pin | item in the corer nest on PS, stalk up (camera), push through | apple, pear (Ø 22), tomato scar, strawberry hull (Ø 14), pepper plug (Ø 42, GP-61), pineapple core; apple wedges + core in one stroke with the cassette's wedge plate |
| **C2 Halve and scrape / cheek cut** | knife cuts parallel to the seed plane; seed spoon (a stem tool with a sharpened spoon edge) is drawn along the cavity by Y | cucumber, courgette, melon, pumpkin, papaya; pepper four-cheek cut (GP-62); mango cheeks; avocado cheeks around the stone (± 8 % yield loss [E]) |
| **C3 Plunger pitter** | fruit in a ring seat, plunger by Z pushes the stone out | cherry (S), plum, olive, apricot (freestone); clingstone peach → cheek cut |

**Mechanism count for PRP-039 (target ≤ 3):** blade post (G1), tube corer / pitter family (C1, C3), knurled drum
(G4 raw). Grid skinning, scraping and blanching use ware that exists anyway. No single-purpose device.

**Throughput [E]:** 4 apples pared and cored 2.5 min; 1 cucumber peeled 40 s; 1 kg potatoes boiled in skin and
riced 0 min of hand time; 2 avocados halved, stoned and grid-skinned 1.5 min; 4 oranges à vif 2 min.

**Questions for the produce research round:**

1. Blade-post paring on irregular items: success rate on knobbly celeriac, kohlrabi with leaf scars, bent
   cucumbers; how much does a sprung shoe follow the contour at 1 mm? (bench: apple-peeler mechanism on a drill)
2. Grid skinning: does avocado and banana flesh pass a 10 mm grid leaving the skin intact and clean? Which ripeness
   window? Slices (fruit salad) instead of mash: can a banana piece be pushed out of its slit skin through a ring?
3. Stone handling: a generic way to find the stone plane of mango and avocado by camera (or by a probing knife
   that stops on force) so that cheek cuts lose ≤ 10 % flesh.
4. Can the spit grip soft or slippery items (mango, kiwi) without tearing? Prong geometry, depth, a cup-backed
   prong.
5. Citrus segments (DS10): any generic route, or accept rounds?
6. Onion peeling (the S upgrade) on the same blade post: GP-11 slit-and-wipe without the extra finger comb?
7. Batch mode: peel the week's onions, garlic and hard vegetables at night (keeps 10–14 days at 2–4 °C), so that
   produce time leaves the meal's critical path.

---

## 5. Benchmark walk-throughs

Conventions: t in minutes from the order; **ev** = handling events (one grasp to release of an item, incl. box
grips); persons as stated (2 or 4, DEC-19); PERF limits from PERF-002 or 1.15 × T_ref + 10. One retry of
≈ 1 min is inserted in the tightest step of each meal. Food-result fixes of C1 are marked **(fix)**. Times
are [E], checked against K6/K8 walk-throughs and the 2.8 kW channel limit.

**B1 Rinderrouladen, Rotkohl, Salzkartoffeln — 4 persons (6 rolls). Yes.**

| t | Step | ev |
|---|---|---|
| 0–14 | Red cabbage (800 g): outer leaves off by knife, quartered, cored (cheek cut), sliced 3 mm with the cassette slice plate; apple pared and cored on the spit; onion diced (grid 6). Into 3 L pot on HR2 with fat, sugar, vinegar, lidded | 14 |
| 14–24 | Rouladen: slices laid on the board, mustard spread up to 35 mm before the flap edge, flap salted and floured (fix), bacon and gherkin laid, side folds 15 mm, rolled with the fork-and-turner roll (GA-04 plough on the board), laid into the comb cradle on PS; **GA-20 raft** pushed through all six | 10 |
| 24–36 | Raft seared in the braiser on HF1 (3.0 kW boost): seam side first 90 s untouched, then two faces; raft lifted out to a tray; **onion and tomato paste roasted in the fond 4 min (fix)**, deglazed with wine and stock (frozen portion), raft back, lidded; braiser into the oven 160 °C for 90 min | 9 |
| 36–100 | Red cabbage stirred every 10 min (6 × 30 s); potatoes (1 kg) washed, peeled on the knurled drum (Salzkartoffeln want raw-peeled, GP-P2), halved, into 5 L pot at t 100 | 12 |
| 100–125 | Potatoes boiled on HF1; braiser out at t 125; raft drained, rolls pushed off by the stripper comb into a GN 2/3-40 in the oven at 70 °C; gravy strained, reduced, thickened (whisk, interval stirring) on HF1 | 8 |
| 125–135 | Potatoes drained; plating: 4 plates × (1.5 rolls, gravy, cabbage, potatoes) | 18 |
| | **Total ≈ 135 min (limit 183); ≈ 71 ev; core temperature probe in one roll (≥ 85 °C for tender)** | |

**B2 Wiener Schnitzel, Bratkartoffeln, Gurkensalat — 4 persons. Yes.**

| t | Step | ev |
|---|---|---|
| (−) | Potatoes boiled in the skin earlier the same day, cooled in the cold store (C1 rule 3); otherwise +35 min | — |
| 0–8 | Cucumber peeled on the spit (1 mm), sliced 2 mm by the cassette, salted; dressing whisked in the chopper cup; dill chopped; into a lidded green GN 1/3 | 10 |
| 8–14 | Cooled potatoes slipped, sliced 5 mm (cassette); onion diced | 6 |
| 14–22 | Breading line in three GN 1/3 trays (flour, egg from the egg fixture, crumbs); 4 cutlets coated by tongs and turner; laid on the lower rack of the GA-36 pair | 14 |
| 22–34 | Bratkartoffeln in the 2nd Ø 280 pan on HR2 (2.3 kW), turned with the turner every 3 min; onion added at t 30 | 6 |
| 34–46 | **Schnitzel in 220 mL clarified butter/oil = 3.6 mm in the Ø 280 pan (fix)** on HF1, 2 per batch; rack pair turned in air after 2.5 min, 2 batches; first batch held ≤ 8 min in the oven at 80 °C vented (fix: fried last) | 8 |
| 46–50 | Salad dressed; plating 4 × (Schnitzel, lemon wedge, potatoes, salad) | 14 |
| | **Total ≈ 50 min (limit ≈ 68); ≈ 58 ev; fat poured off into the fat cup** | |

**B3 Frikadellen, Kartoffelpüree, Erbsen-Möhren — 4 persons (8 patties). Yes.**

| t | Step | ev |
|---|---|---|
| 0–6 | Potatoes (1 kg) washed in the dunk basket, boiled **in the skin** in 5 L pot on HF1 (GP-P1) | 6 |
| 6–14 | Onion diced (grid 6, RTE tube); stale roll soaked; mince 600 g, egg, onion, roll, spices into the kneading bowl on T, roller 90 s | 12 |
| 14–20 | Mass into the red cassette tube, extruded through Ø 70, wire cut every 20 mm (±10 % by wrist mass); patties onto the Ø 280 pan on HR2, pressed flat with the turner | 6 |
| 20–34 | Carrots scrubbed in the drum, diced 10 mm, cooked in 1.5 L pot on HF2 with frozen peas added at t 28; Frikadellen turned singly (turner) every 3 min; **probe to 72 °C core (fix)** | 14 |
| 34–42 | Potatoes riced through the 3 mm plate (skins stay behind), milk and butter, folded in the bowl on T | 10 |
| 42–47 | Plating 4 × (2 patties, mash, vegetables) | 14 |
| | **Total ≈ 47 min (limit 50, tight: one retry consumed); ≈ 70 ev in the meal; series chain 6 (gantry, chuck, T, cassette, hob, washer)** | |

**B4 Spaghetti Bolognese with grated cheese — 4 persons. Yes.** Onion, carrot, celery diced (cassette, 6 ev,
8 min); **mince seared first in the wide hot Ø 280 pan (fix)**, then vegetables, tomato paste roasted, tinned
tomatoes, wine; transferred to 3 L pot, simmer 60 min with stirring every 5 min (12 × 20 s); pasta 400 g in
the 5 L pot (4 L water, HF1 boost) from t 75, drained by the basket; cheese grated on the drum (S). **≈ 90 min
(limit 96); ≈ 48 ev.**

**B5 Pizza from flour, 2 trays (GN 2/3-20). Yes (tray pizza, R-05 a).** Dough 500 g flour kneaded 8 min in the
bowl on T; proofed 60 min in the bowl, lidded, in the oven at 30 °C; tomatoes and toppings cut meanwhile;
divided by wrist mass, rolled with gauge-ring pin to 5 mm on oiled trays, topped; baked one tray at a time
230 °C, 12 min each (countertop oven: one level). **≈ 120 min (limit ≈ 150 at T_ref 120); ≈ 40 ev.**
Weakness: two trays in sequence; the second pizza waits 12 min under 70 °C or is served as a second round.

**B6 Gemüseeintopf from whole vegetables — 4 persons (2 L). Yes.** Potato, carrot, leek (cut before washing,
GP-W4), celeriac (spit, 2.5 mm shoe), beans trimmed by GP-102 (camera-indexed cut, 40 pieces, 3 min), onion;
all diced by the cassette; sweated in the 5 L pot, stock from frozen portion; simmer 25 min; herbs chopped
(cup on S). **≈ 48 min (limit 50, tight because of bean trimming); ≈ 45 ev.**

**B7 Steak, oven fries, mixed salad with vinaigrette — 2 persons. Yes.** Potatoes scrubbed, cut to 10 mm sticks
(cassette grid 10), oiled 15 mL, oven 220 °C 25 min on a GN 2/3-20 (X-01 adapted, b); lettuce butt cut, washed in
the dunk basket (2 baths), spun on S; tomato and cucumber cut; vinaigrette emulsified in the chopper cup; steaks
seared on HF1 (3.0 kW, Ø 280 pan), **probe to 54 °C (fix)**, rested 4 min; fries finish last, served at once.
**≈ 40 min (limit ≈ 44); ≈ 38 ev.**

**B8 Pfannkuchen, 8 pieces. Adapted (pan-pair flip, R-03 a).** Batter in the whisk cup on S (eggs from the
fixture, flour, milk); Ø 280 pan with 3 g fat; 70 mL ladled, pan rolled to spread (roll axis); after 90 s release
check (5 mm jerk, camera), flip pan set on, pair rolled 180° in 0.8 s over the hob, the emptied pan returned;
8 pieces × 3.5 min, stacked in the oven at 80 °C, served in two rounds of four. **≈ 38 min (limit 50); ≈ 44 ev.**

**B9 Chicken curry with rice — 4 persons. Yes.** Onion, garlic (peeled cloves, GP-17 plate), ginger (spit, thin
shoe, grated on S), chicken thighs (red board, knife, 25 mm cubes); onion browned, spices, chicken seared,
tomatoes and coconut milk, simmer 25 min stirring every 5 min; rice 300 g in 3 L pot, absorption method, lidded
(no stirring needed). **≈ 50 min (limit ≈ 62); ≈ 46 ev; probe on the largest cube 75 °C.**

**B10 Lasagne, béchamel from scratch, GN 2/3-65 — 4 persons. Yes.** Bolognese as B4 (45 min simmer);
béchamel: roux in 1.5 L pot, milk added in 4 portions while whisking (4 × 40 s), then stirred every 60 s for 8 min
— the hand's busiest phase; layering with dry sheets (GA-dispensed from the box, laid by the plate fork) in the
GN 2/3-65, cheese on top; oven 180 °C 40 min; rest 10 min; cut into 4 portions in the dish by knife, served by
turner. **≈ 130 min (limit 148); ≈ 52 ev.**

**B11 Rührkuchen in a loaf tin, unmoulded. Yes.** Butter at room temperature from the morning (scheduled
retrieval, not tempering), creamed with sugar in the whisk cup on S (flat beater), eggs one by one, flour
folded with the spatula on T at 20 rpm; tin lined with paper liner and loose floor (K5); baked 175 °C 55 min with
probe (98 °C); cooled 15 min; inverted by the hand onto a tray, floor and liner lifted. **≈ 95 min (limit ≈ 102);
≈ 26 ev.** Unmoulding H (liner).

**B12 Scrambled eggs from shell eggs, toast — 1 person. Yes.** 3 eggs in the fixture, per-egg check, through the
strainer into the 1.5 L pot, butter, gentle heat on HR1 with spatula strokes every 15 s (the hand stays at the
pot, 4 min); toast from bread delivered by transport (if the household stores it in the machine; DEC-16 keeps
bread outside — then toast in the dry pan, top heat). **≈ 9 min (limit ≈ 21); ≈ 12 ev; 1 wash load shared with
the next meal's dishes, or a 15-min quick hygiene load: 4 items.**

**Summary.** All twelve are possible (B8 adapted, B5 tray pizza). The tightest are B3 (47/50) and B6 (48/50),
both bounded by the single hand; B2 needs potatoes cooked ahead (a scheduling rule, not a texture change).
Events in the meal: 12–71, mean ≈ 46 per meal; 4-person meals 45–71.

