# Prep ideas C — The vessel is everything

Round P1 (idea finding), lens: **"the saucepan is the bucket"**. Start from the only mass-market success
(Thermomix / Cooking Chef / rotating wok: one vessel that weighs, chops, mixes, kneads and cooks) and push it
until the whole preparation module is nothing but **vessels + active lids + docks**.

Written independently of the other P1 documents. Sources used: `BRIEF.md`, `DECISIONS.md`, `PLAN.md`,
`requirements/requirements.md` (sections 3.5, 5, 7), `research/01`, `04`, `05`, `06`, and the GN box
recommendation of `research/03`. Sections 1-6 were written before `research/02-meal-corpus.md` existed and
argue against the unit operations UO-01 … UO-87 and the brief's named meals; **section 7 checks the concepts
against the finished corpus** (248 meals, 126 operations) and corrects sections 1-6 where the corpus disagrees
(vessel sizes, number of hobs, five additional mechanisms S-20 … S-24).

Tags: **[E]** my estimate or calculation, **[R4]**/**[R6]** number taken from that research document,
**[?]** must be verified by test. All dimensions in mm.

---

## 0. What the lens forces, and four rules I derived from it

Thermomix works because nothing has to be *handed over*: the food never leaves the vessel. It fails our brief in
three places: (1) the bottom blade needs a shaft seal that a human has to take apart (HYG-016), (2) it cannot do
anything flat or anything that needs a clean cut (dice, slices, Schnitzel, steak, Rouladen), (3) it has one
vessel, so a four-component meal is sequential.

Pushing the idea further gave me four rules that all concepts below obey:

1. **No shaft ever passes through a food-contact wall.** Motion enters a vessel only through its open mouth
   (a one-piece tool on a spindle above it), through the wall as a whole (the vessel itself rotates, tilts or
   shakes), or through a flexible wall (concept D). This removes every dynamic seal from Zone F.
2. **Every food transfer is a closed, rim-to-rim inversion** ("hourglass"). Two vessels with the same rim are
   clamped mouth to mouth and turned over. Nothing is poured through open air, nothing dribbles down an outside
   wall, powder cannot dust the cell (PRP-014), and the emptied vessel leaves upside down, already in its
   draining position.
3. **Work is done *between* two vessels.** A flat "interposer" (strainer, grid, ricer plate, cutting disc, rack)
   clamped between the two rims turns a transfer into an operation. The stack of vessel / interposer / vessel is
   its own splash enclosure, so the machine around it stays clean.
4. **The part that receives the food may be the rotor.** A cutting disc that clips onto the rim of a rotating
   receiving vessel, under a stationary feed tube, is a food processor without a shaft, a hub or a seal.

The four concepts differ in *what the vessel is* and *how it is moved*:

| | Concept | Vessel | Motion that does the work |
|---|---|---|---|
| A | **STACK** | rigid round cans, open sleeves, discs | vertical column: quill above (press + spin), turntable below |
| B | **SANDWICH** | rectangular GN trays, off-the-shelf | tray rides a slide under a bridge of heads; clamshell flip; shaking hob |
| C | **TWIN-SPINDLE** | few drums chucked on a spindle, washed in place | a tilting two-headed "kitchen lathe" |
| D | **SKIN** | soft everting bags and folders | squeezing from outside; turning the vessel inside out |

---

## 1. Concept A — STACK: cans, sleeves and discs under a quill

### 1.1 Core idea

One rim standard (R260), three kinds of passive stainless parts: **cans** (closed bottom), **sleeves** (open
tubes) and **discs** (interposers). They are stacked in a vertical column that has a **quill** on top (a spindle
that can push with 8 kN and spin up to 6 000 rpm, like a drill press) and a **turntable** underneath; whatever
is clamped in the middle fork stands still. Food moves downward through the stack by gravity and piston, and
between cans by rim-to-rim inversion in a separate inverter.

### 1.2 Sketch

```
 COLD COLUMN "K" (front view)            VESSEL FAMILY, one rim R260 (flange OD 290, bore 250)

        ||  quill: Z 300 stroke, 8 kN          pot      B250 x H110   5.4 L  tri-ply
        ||  + spindle 0-6000 rpm               tall pot B250 x H180   8.8 L  tri-ply
      __||__                                   pan      B250 x H40    2.0 L  tri-ply, 2 per flip pair
     |piston|   P160 / P90 comb / platen       beaker   B160 x H130   2.6 L  "hat": 45 deg shoulder
   __|______|__                                                               up to the R260 rim
   \          /  feed sleeve S90 or S160       sleeve   S160 x 160, S90 x 160 with funnel collar
    |        |   (held by fork, stationary)    discs    15 thick, R260 rim, see 1.4
    |  food  |
  ==|========|== <- fork, Z-adjustable, with 3 load pins (weighs the stack)
    [# # # # ]   disc: grid / ricer / slicer / rasp ...
   |          |
   |  can     |  receiving can = rotor for cutting discs
   |__________|
   ====[TT]====  turntable 0-900 rpm, 20 Nm, umbrella labyrinth, drive below deck
   ~~~~~~~~~~~~  sloped stainless deck, drain

   column envelope approx. 380 W x 480 D x 1050 H [E]

 INVERTER "W"                         HOB "H" (x2)                     WASH LATHE "S" (x2)
   +--can B (upside down)--+            || light quill: Z + spin         closed pot, dia 360 x 380
   |=== interposer/gasket ==| 3 jaws    ||  20 Nm / 60 rpm               part upside down on turntable,
   +--can A ---------------+            =[rotating lid]=                 fixed jet mast along one meridian,
      rotates 360 deg about              |   can      |                  induction ring for flash dry
      a horizontal axis                  ~~ induction ~~
```

Module estimate [E]: 1 cold column, 1 inverter, 2 hobs with light quills, 2 wash lathes, 1 dosing dock, a rack
for about 45 parts; arranged on two levels, about 1 200 wide x 600 deep x 1 900 high, served by the transport
gantry (X-Z plus a short Y reach).

### 1.3 Kinematics and actuators

| Station | Axes | Count |
|---|---|---|
| Cold column K | quill Z (servo ball-screw cylinder, 8 kN, 250 mm/s); quill spindle (two ranges: 20 Nm at 0-300 rpm, 1.5 Nm at up to 6 000 rpm); turntable (servo, 20 Nm, 0-900 rpm); fork Z (positions the stationary part) | 4 |
| Inverter W | jaw clamp (3 V-jaws on a ring, closes on two flanges and an interposer, about 300 N); rotation (continuous, 0-30 rpm, 15 Nm) | 2 |
| Hob H1, H2 | light quill Z (lid down/up, 200 N); spindle (20 Nm at 60 rpm, 3 Nm at 1 000 rpm) | 4 |
| Wash lathe S1, S2 | turntable; door | 4 |
| Dosing dock | shutter; vibrator; water valve | 3 |
| **Total** | | **17** (plus pumps, heaters, the transport gantry and its gripper) |

Force loop of the press: quill → piston → food → disc → fork → column. 8 kN stays inside the column frame
(a 60 x 60 x 4 stainless tube pair is ample [E]); the turntable never sees press force.

Weighing: the fork's three load pins weigh whatever hangs in it; the dosing dock has a 10 kg platform (±1 g)
and a 200 g micro cell (±0.05 g) for seasoning [R4 9.2].

### 1.4 Tool and vessel set (first count, [E])

| Group | Parts | Qty |
|---|---|---|
| Cans | pot 5.4 L x3, tall pot 8.8 L x1, pan 2 L x4, beaker 2.6 L x4 | 12 |
| Sleeves | S160 x2, feed tube S90 x2 (funnel collar R260 → dia 90), S60 insert for long goods x1 | 5 |
| Discs (interposers) | coupler ring with moulded gasket x3; strainer 3 mm; ricer 2.5 mm; dicing grid 10 mm and 6 mm (dia 90 window) each with rotating sweep knife ring; 6-way wedge; slicing disc (2/4/8 mm by shims) and shredding disc (clip to can rim); rasp floor disc; scraper ring; rack (coarse grid); egg disc; spin basket (perforated inner can) x2 | 15 |
| Stalk tools (one piece, chucked in a quill) | blade stalk; whisk stalk; zig-zag stamp chopper; piston P160 (silicone lip); comb piston P90 (studs matching the grids); platen P250 (flat, for pans); French-press piston (perforated) | 7 |
| Lids | plain lid x4; splash lid with centre hole x2; rotating scraper lid x2; kneading lid (roller + scraper) x1; cone roller for dough x1 | 10 |
| **Total** | | **about 49 passive parts, no part contains a bearing, a seal or a motor** |

### 1.5 How each ingredient form is dosed and moved

Common principle: the storage box (GN 1/6, 176 x 162, diagonal 239, fits inside the R260 rim) is clamped in the
inverter onto a **box collar** (rectangular socket above, R260 below, with a shutter) and turned over. The box
becomes a hopper for a few seconds, then is turned back and re-lidded. Nothing is scooped.

| Form | Dosing | Transfer |
|---|---|---|
| Whole produce | Box inverted over a piece chute collar (dia 100 port); pieces roll out one at a time into the can on the scale; stop on mass, accept ±1 piece, and **scale the rest of the recipe to the measured mass** (idea S-14) | Hourglass into peeler sleeve / feed tube |
| Leafy, bulky | Whole box content inverted into a spin basket in a pot (leafy goods cannot be dosed by pouring); surplus is kept cold in a lidded beaker (PRP-036) | Basket is the carrier; lifted by its rim |
| Granular | Hourglass orifice collar: mass flow through an orifice is nearly independent of fill height (Beverloo). Rice through dia 20: about 43 g/s; dose by shutter time, trim on the scale, ±2 % [E] | Hourglass |
| Powder | Cohesive powders do not flow by themselves through a 1.5 mm mesh: a **vibrated sieve collar** is a valve with no moving part in the food. Vibration on = about 5-15 g/s flour, off = stop [?] | Closed stack, so no dust |
| Seasoning | Each spice box keeps its own sifter insert (no cross-contact, washed with the box); shaken into a beaker on the micro cell; salt through a dia 3 orifice: about 0.6 g/s, ±0.05 g [E] | Beaker is inverted onto the pot |
| Liquid | Water: valve + flow meter at column and hobs (through the hollow hub of the rotating lids). Other liquids: the opened package or box is tilted in the inverter through a spout collar onto the scale, closed loop, ±3 g [R4] | — |
| Paste, solid fat | Frozen pucks (idea S-9) counted as pieces; or squeeze pouch between two rollers (idea S-10); last resort a spoon-stalk on the quill | Scraper ring |
| Raw meat, fish | Pieces and mince: opened pack inverted onto the can (hourglass), scraper ring for the rest. Stacked slices: freeze-plate lid lifts one slice at a time (idea S-3) | Slice is laid into a pan |
| Egg | Egg disc over a beaker (1.6) | — |
| Frozen loose | As granular, through the dia 50 orifice; blocks (spinach) go as pieces and thaw in the pot | Hourglass |
| Long goods | Spaghetti: box tilted through a slot collar into the tall pot; cucumber, leek, carrot: dropped lengthwise into the S60 feed insert | — |

### 1.6 The hard operations

| Operation | How, with numbers |
|---|---|
| **Peel potato, carrot, celeriac** | Mini-Rumbler built from the kit: sleeve S160 with a dimple-rasp liner, held by the fork; **rasp floor disc** (wavy, etched stainless, not carborundum, so it washes) on the turntable at 250-300 rpm; 3 mm gap at its edge; water 1 L/min from the quill nozzle; slurry falls through the gap into a waste can below. 1.5 kg in 90-120 s, loss 15-25 % [R4 for the principle; E for the numbers]. Eyes remain (PRP-022 allows 5 %). Default remains skin-on + ricer [R4]. |
| **Peel onion** | Not solved by abrasion. Two routes: (a) wedge disc halves the onion pole to pole, a knife ring tops and tails it, then the half is pushed cut-face-down through an **undersized D-shaped die** chosen by camera from three sizes; the inner layers pass, the skin and the outermost fleshy layer stay behind (idea S-12). Loss 20-30 %. Success rate unknown, my guess 85 % [?]. (b) fallback: peeled or frozen diced onion. This is the weakest operation of the concept. |
| **Dice onion, potato, carrot** | Feed tube S90 on the dicing grid disc; comb piston pushes (staggered blade heights); under the grid a **sweep knife fixed to the rim of the rotating receiving can** cuts the emerging sticks: dice length = feed speed / rotation rate (10 mm/s at 60 rpm = 10 mm). Force for a dia 90 window at 10 mm pitch: edge length about 1 000 mm x 2-5 N/mm = 2-5 kN [R4 formula], hence the 8 kN quill. Onion halves through the 6 mm grid give true dice because the layers supply the third cut (Alligator-chopper principle). The comb piston pushes the last plugs through, so the grid leaves the stack almost clean. 1.5 kg potatoes in four loads, about 90 s. |
| **Slice, shred** | Slicing or shredding disc clipped to the rim of the receiving can, turntable 300-400 rpm, stationary feed tube above, piston as a gentle pusher (20-50 N). A food processor in which the bowl and disc rotate together: no shaft. |
| **Mince herbs, garlic, nuts** | Zig-zag stamp chopper on the quill (Zyliss principle): 2-3 strokes/s, the turntable indexes 37 deg per stroke, 30-40 strokes. Clean cuts, no mush. Floor insert of food-grade PE-HD takes the blade edge (a wear part, see weakness). Alternative: blade stalk pulses in the beaker. |
| **Crack egg** | Egg disc: cradle + blade mechanism (EZ-Cracker kinematics) operated by one quill stroke; contents fall into the beaker on the scale; camera checks yolk and fragments; shell halves tip outward into an annular **shell moat** on the disc (holds 12 eggs' shells), which is later inverted over the waste. 12-15 s per egg, 12 eggs in about 3 min (UO-05 limit). Pin hinges are open and washed on the lathe. |
| **Form Frikadellen** | Mass is kneaded in a sleeve clamped on a die disc with a closed slide gate (a "spring-form can"; fine for a stiff mass, not for liquids). Gate opens to a dia 70 hole, piston P160 extrudes a log, the sweep knife on the rotating can rim below cuts pucks: 25 mm = about 100 g, ±10 % by piston travel, checked by the fork load pins. Pucks drop 30 mm into a pan that the turntable indexes. Pressure about 20-50 kPa → 0.4-1 kN [E]. Alternative with zero handling: idea S-7 (form in the pan). |
| **Rouladen** | Needs the one non-vessel tool: an **apron roller** (idea S-6) standing on a pan. Slice placed by the freeze plate; mustard from the paste nozzle as a stripe; diced bacon, onion and gherkin dosed as pieces (diced instead of sliced bacon: marked as adapted); one stroke rolls it; the roll drops seam-down into a trough insert in a pan where four rolls lie packed against each other. No tying: sear seam-down first (the seam sets in about 60 s), then clamshell-flip into a second trough pan, then braise lidded. My honest estimate: 80 % first-time success, camera-checked, a failed roll is re-rolled. |
| **Bread a Schnitzel** | Flatten in a pan with platen P250 (0.5-1.5 kN [R4]; the cutlet becomes roughly round, dia 195 for 300 cm2, which fits the dia 250 bore). Then **breading by flipping** (idea S-5): pan F with 30 g flour, pan E with beaten egg, pan C with 60 g crumbs; the cutlet is moved from one to the next by clamshell inversion, each flip re-beds it, a rack disc lets loose flour and surplus egg fall back. About 8 flips, 60-90 s per cutlet, fully enclosed. One cutlet per pan is the throughput limit (see weakness). |
| **Knead, roll out dough** | Knead: kneading lid (roller + scraper, Ankarsrum geometry [R4]) held still while the turntable turns the pot at 60-100 rpm, 10-20 Nm for 1.5 kg. Roll out: dough ball in a pan on the turntable at 30 rpm, **cone roller** on the quill pressed down to a gap of 2-10 mm (potter's jigger; a cone with its apex on the axis rolls without slip). Gives a round sheet up to dia 250, ±0.5 mm. Rectangular tray-size sheets are not possible in A. |
| **Mash potatoes** | Steamed potatoes (skin on or peeled) hourglassed into S160 on the ricer disc over a warm pot holding butter and milk; piston P160, 1.2-4 kN (scaled from a hand ricer [R4]); skins stay on the disc; rotating scraper lid folds at 20 rpm. No blade, so no glue. |
| **Toss salad** | Wash: leaves in the spin basket in a pot, water in, turntable reverses ±90 deg for 30 s, drain by three-layer inversion, spin at 900 rpm (109 g at r = 120), water leaves through the basket. Toss: two pots rim to rim in the inverter with the dressing, 4 slow turns. |
| **Flip steak, pancake** | Clamshell: second pan preheated and oiled on H2, placed upside down on the first, inverter turns the pair in 2 s. Drop height = pan depth (40; use 25 for crêpe pans). Pancake batter is spread by spinning the pan (idea S-15). |
| **Drain pasta** | Three-layer inversion: pot / strainer disc / empty pot. Turn over: water is in the lower pot, pasta on the strainer under its own pot. The inverter then grips only pot + strainer and turns them back: the pasta is back in its own pot, drained, and returns to the hob for the sauce. The pasta water is kept in a pot (for the sauce) or poured to drain. No lifting of 5 kg of boiling water over an open cell. |
| Purée, whip, emulsify | Blade stalk or whisk stalk through a splash lid with a clearance hole; slinger collar on the stalk. Stalk dia 20, overhang 250: first critical speed about 13 000 rpm [E], run at up to 6 000 rpm, blade dia 90 = 28 m/s. Whisk runs off-centre in the pot to break the vortex. |
| Stir, sauté, deglaze | Rotating scraper lid on the hob quill: one welded piece (disc + two silicone-edged arms following floor, corner and wall), hovering 2 mm above the rim, hollow hub for water, liquids and the weigh-beaker contents. |

### 1.7 Cleaning and drying

* **What gets dirty.** Only passive, mostly axisymmetric parts: cans, sleeves, discs, stalks, lids. The
  processing volume is always a closed stack, so the column, the inverter jaws and the fork are Zone S with very
  little soil.
* **Wash lathe** (idea S-1). A part is placed upside down (or on a mandrel, for discs and stalks) on a turntable
  inside a closed round chamber. A fixed mast carries 5-6 nozzles along one meridian: floor centre, floor,
  corner radius, wall, rim, outside wall. The part turns at 60 rpm, so every point passes every jet: there is no
  spray shadow on an axisymmetric part by construction. Nozzles dia 1.5 at 5 bar, 2.2 L/min each [R6], about
  12 L/min from a 2 L sump.
  Sequence per part [E]: cold pre-rinse to drain 30 s (1.5 L) → 55 °C enzymatic wash, recirculated, 3 min →
  rinse 30 s (1 L) → spin at 900 rpm for 15 s → **induction flash**: a coil ring in the chamber heats the
  still-wet tri-ply can to 105 °C for 60 s (A0 far above 60; about 70 kJ = 0.02 kWh instead of 0.3 kWh for 4 L
  of 80 °C rinse water) → dry. About 6 min and 3-4 L per part; two lathes wash the ware of a reference meal
  (about 16 parts) in 50 min (PERF-005: 90 min).
* **Non-axisymmetric parts** (grids, egg disc, apron roller): grids are pushed clean by the comb piston first;
  then they are washed on the lathe on a mandrel with an extra fan jet normal to the disc. If that fails the
  riboflavin test [?], these six or so parts go to the conventional wash chamber of D7.
* **Where the water goes.** Chamber floor is a 10 deg cone to a central drain with a 1 mm strainer basket; the
  strainer is itself a disc that is inverted over the waste and washed as the last part.
* **The chamber cleans itself** in every cycle (it is a rotationally symmetric pot with its own jets) and is
  dried by the same induction-warmed air and a fan.
* **Stations.** Turntables have an umbrella labyrinth (the rotating plate overhangs a raised collar, no contact
  seal); decks slope 5 deg to a drain; quills sit behind a bellows; a low-pressure wash-down ring on each
  station runs daily (HYG-034).
* **Verification.** Because the part rotates, one fixed camera and one light see the whole inner surface
  (HYG-026).

### 1.8 Off-the-shelf, custom, novel

* **Off-the-shelf:** servo cylinders, servo motors, induction modules (DEC-5), load pins, pumps, nozzles,
  silicone profiles, slicing/shredding blades, zig-zag chopper blades, abrasive-free rasp sheet.
* **Custom:** all cans, sleeves and discs (deep-drawn or spun tri-ply and 1.4404, a few dozen simple turned and
  laser-cut parts, no FDM in Zone F); inverter; column frame; wash lathe.
* **Novel (as far as I know):** receiving vessel as the rotor of the cutting disc; sweep knife on the can rim
  for dicing; three-layer "drain in its own pot" inversion; breading by flipping; the hat-shaped beaker on a
  common rim; wash lathe with induction flash sanitising.

### 1.9 Biggest weakness

**Part count and traffic.** About 49 loose parts and, for a reference meal, 60-90 gantry moves to build and take
down stacks. Every stack-up is a chance for a mis-seat. Second: **round pans fry one Schnitzel at a time**, so
flat dishes for six need two hobs for 15-20 min. Third: the PE chopping insert is a consumable that cuts score,
and onion peeling is unproven.

---

## 2. Concept B — SANDWICH: GN trays on a slide, flipped as clamshells

### 2.1 Core idea

The storage box, the prep bucket, the pan, the roasting tin, the baking tray and the serving platter are all
**Gastronorm containers** on the 176 x 325 grid, mostly bought. A tray is never worked on by a moving arm;
instead **the tray rides a linear slide under a fixed bridge of heads** (roller, platen, spreader, sifter,
nozzles), and **the hob itself shakes** to toss and stir. Turning, coating and transferring are done by
clamping two trays rim to rim with an interposer plate between them and inverting the sandwich.

### 2.2 Sketch

```
 SIDE VIEW of the prep deck (one lane, running left-right along the cabinet front)

   bridge of fixed heads (each with at most one Z axis)
    [sifter] [paste slot] [platen 3 kN] [roller] [apron bar] [batter/water nozzles] [camera]
       |         |            |            |          |
  =====+=========+============+============+==========+=========  <- travel 700
     [ GN 1/3 tray on carriage ]  -->  X slide, 0.5 m/s, also shakes +-15 at 3 Hz
  ---------------------------------------------------------------  sloped deck, drain

 SANDWICH INVERTER                          SHAKING HOB (x2)
    +--- tray B (inverted) ---+               tray (Rieber thermoplate GN 1/3 or 2/3)
    |== interposer plate ====|  4 clamps      ~~~~ induction coil moves with the tray ~~~~
    +--- tray A -------------+               [carriage] asymmetric stroke: slow out, fast back
      rotates about the long axis,            fixed wiper-bar lid above = full-floor scraper
      swing dia about 380

 FAMILY (all bought): GN 1/9, 1/6 boxes (PP/Tritan, storage) - GN 1/3 x 20/40/65/100 stainless (prep) -
 thermoplates GN 1/3 and 2/3 x 20/40/65 (induction + oven) - GN 2/3 oven (compact combi steamer)
 GN 1/3 inner floor about 300 x 150: exactly one Schnitzel or Rouladen slice of 250 x 150 (UO-20 limit)
 GN 2/3 (354 x 325) = two GN 1/3 side by side: 2-4 Schnitzel, 4 steaks, 8 Frikadellen, 8 Rouladen
```

Envelope [E]: prep lane 1 000 x 250, inverter 450 x 450, two shaking hobs 450 x 400 each, oven 520 wide: about
1 400 wide x 600 deep on two levels.

### 2.3 Kinematics and actuators

Slide X (1), platen Z 3 kN (1), roller Z (1), apron bar Z (1), sifter vibrator (1), inverter clamp + rotation
(2), two hob carriages (2), two wiper lids Z (2): **11**, plus a bought cutter head and a bought kneading
machine (below), pumps and the oven.

The hob carriage moves coil, glass and tray together (about 8 kg): ±15 at 3 Hz needs 43 N; the fast return of
the slip-stick stroke at 1 g needs 80 N [E]. Trivial for a belt axis.

### 2.4 Tool and vessel set

Bought GN trays and lids; interposer plates in GN 1/3 and 2/3 outline: **rack**, **strainer**, **sifter plate**,
**mandoline plate** (blade + julienne comb), **grater plate**; bridge heads as listed; a silicone apron liner
for rolling; trough inserts. For round work B has no answer of its own and **buys it in**: a feed-through
vegetable cutter head (Robot Coupe CL class, discharging into a GN tray) and one rotating-bowl kneader/whisk
(Ankarsrum class [R4]) or a column from concept A.

### 2.5 Ingredient forms

| Form | Dosing and moving |
|---|---|
| Whole produce | Storage box and tray share the GN rim: box clamped onto a GN 1/3 tray through a gate plate, inverted; pieces by count via camera |
| Leafy | Whole box inverted into a deep GN 1/3-100 with a perforated GN insert (bought) |
| Granular, powder | Box inverted onto the **sifter or orifice plate** over the tray on a scale; vibration or shutter meters (as A) |
| Liquid | Nozzles on the bridge (water, pumped oils), tray on load cells in the carriage |
| Paste | Slot nozzle on the bridge lays a stripe while the tray moves (mustard on Rouladen, tomato sauce on pizza and lasagne layers) |
| Raw meat slices | Freeze-plate head on the bridge (idea S-3) lifts a slice from the opened pack and lays it flat in the tray; pieces and mince by inversion |
| Egg | Egg cracker head on the bridge (conventional [R4]) over a tray or cup |
| Frozen | As granular |

### 2.6 The hard operations

| Operation | How |
|---|---|
| Peel potato, carrot | Not native. Bought abrasive peeler insert or skin-on route. Onion: bought peeled. **B peels nothing itself.** |
| Dice onion, slice, shred | Bought cutter head into a tray. Own, simpler alternative for slices and julienne: mandoline plate between box and tray, produce under a 1 kg follower weight, the sandwich shaken ±60 at 2 Hz on the slide [?]; orientation is random, fine for potato slices, poor for cucumber coins. |
| Mince herbs | Bought chopper; or a multi-wheel roller head on the bridge (mezzaluna wheels at 3 mm pitch) rolling over the herbs in a PE-lined tray, 10 passes. |
| Crack egg | Conventional blade-and-jaw module on the bridge. |
| Form Frikadellen | **Formed in the pan** (idea S-7): mass inverted into a thermoplate, platen presses it to an even 22 mm layer, a divider lid with rounded cells parts it into 4 (GN 1/3) or 8 (GN 2/3) pieces of 110 g that are fried where they lie and flipped as a set by clamshell. Rounded-rectangle Frikadellen, no handling of sticky pieces at all. |
| Rouladen | Best of all four concepts. Slice laid on the apron liner in a GN 1/3; tray moves under the slot nozzle (mustard stripe), then under the piece dosers (bacon, onion, gherkin across the leading edge); the fixed apron bar hooks the liner hem and the tray drives back under it, so the liner is drawn over itself and the slice rolls up (sushi-mat kinematics, one axis that already exists); the roll drops into a trough thermoplate, four side by side, seam down; sear, clamshell-flip, braise lidded in the oven. |
| Bread a Schnitzel | Platen flattens to 5 mm on spacers (1.5 kN); flour from the sifter head while the tray passes; breading by flipping through flour, egg and crumb trays with the rack interposer; platen presses the crumb at 30-50 N. GN 2/3 takes two at once. |
| Knead | Bought rotating-bowl machine. Roll out: dough in a GN 2/3 tray passes 4-6 times under the roller head, which steps down 2 mm per pass (20-60 N [R4]); a tray-size rectangular sheet of 2-10 mm is B's speciality (pizza, tray bakes, quiche, biscuits). Flour from the sifter head against sticking. |
| Mash | Bought ricer principle under the platen: potatoes in a perforated GN insert (2.5 mm, custom), platen presses them through into the tray below; 3 kN platen over a 300 x 150 insert is marginal, done in two half-loads [E]. |
| Toss salad | Two deep GN 1/3 rim to rim, 4 slow turns. Washing and spinning leaves is not native (rectangular baskets do not spin): bought-in round spinner, or buy washed salad. |
| Flip steak, pancake | Clamshell between two thermoplates; rectangular pancakes 300 x 150 or GN 2/3. Alternatively a heated platen lid (contact grill) cooks both sides at once with no flip. |
| Drain pasta | Bought perforated GN insert in a GN 1/3-150 pot, lifted out by the transport gripper (R4's recommendation); or three-layer inversion with a strainer plate. |
| Stir, sauté | **Shaking hob** (idea S-4): asymmetric stroke conveys the pieces to the curved end wall, which rolls them over, like a cook's wrist; reverse to bring them back. Thick sauces: the tray shuttles ±140 under a fixed wiper-bar lid that spans the width: 100 % of a rectangular floor is scraped every 2 s. |
| Layer lasagne, gratin | Native: tray moves under sheet dropper, sauce slot nozzle and cheese sifter; bakes and is served in the same GN tray (UO-43, UO-85). |

### 2.7 Cleaning and drying

* All vessels are GN: they go through a rack wash chamber with GN guide rails, the documented industry case
  (Winterhalter-type pot washers take GN 1/1 and 2/1 racks). Trays stand on edge at 10 deg so they drain;
  GN corner radii are 10-20. Bought tri-ply trays flash-dry from the 80 °C rinse; PP boxes need hot air [R6].
* Interposer plates are flat and wash like trays. Mandoline and grater plates have blades with a gap underneath:
  fan jet along the blade.
* Bridge heads hang above open food, so they are Zone F (HYG-004). Each head parks over a **wash trough** at
  the end of the lane: the slide brings a "wash tray" with upward nozzles (a spray-bar lid turned upside down)
  under the whole bridge and drives back and forth; roller and platen are smooth cylinders and planes; the
  roller rotates in the jet. Water falls into the sloped deck and drain.
* Sticky problem: the apron liner and the platen after raw meat. Both are washed in the chamber (liner) or by
  the wash tray with 80 °C water (platen) after every class-R use. Better: cover the platen with a silicone
  folder from concept D so it never touches meat.
* The bought cutter head and kneader are the hygiene weak points: discs, chute and bowl are dishwasher parts, but
  the machine has to take them apart (several gripper moves, latches designed for humans).

### 2.8 Off-the-shelf, custom, novel

* **Off-the-shelf (the strength):** every vessel and lid, the oven, the wash chamber, cutter, kneader, slides.
* **Custom:** interposer plates, bridge heads, inverter, hob carriage, apron liner, trough and divider inserts.
* **Novel:** shaking hob with slip-stick conveying and a turning end wall; shuttle-wiper stirring; forming in the
  pan with a divider; apron rolling driven by the tray's own travel; breading by flipping.

### 2.9 Biggest weakness

B is excellent at everything flat and **has no native answer for round work**: chopping, kneading, whipping,
puréeing, peeling, spinning. It ends as "GN logistics plus three bought kitchen machines that a robot must
dismantle", which is exactly where prior art got stuck. The shaking hob also sloshes: a GN 1/3-65 can carry at
most about 1.2 L of liquid while shaking [E], so soups still need a quiet pot.

---

## 3. Concept C — TWIN-SPINDLE: the kitchen lathe

### 3.1 Core idea

Instead of many vessels that travel to a wash, **two or three drum vessels stay chucked on a spindle and are
cleaned in place in three minutes**, as Chinese wok robots do (90 s between dishes [R1]). Each drum faces a
second, coaxial spindle that holds "heads" by the same chuck (scraper, blade, feed tube, spray lance, or a second
vessel), and the whole pair sits in a frame that tilts through 360 deg. One machine is therefore pot, rotating
wok, tumbler, centrifuge, mixer, food processor, inverter and washing machine.

### 3.2 Sketch

```
  FRONT VIEW of one unit (frame tilts about the Y axis, which points into the cabinet)

              spindle 2 (head side): spin 0-6000 rpm, axial stroke 250, 3 kN
                    ||
                 ___||___  <- head, chucked by its hub: scraper / blade / feed tube+piston /
                |  head  |     spray lance / or a second drum or pan (mouth to mouth)
            . . |________| . .   steady rest (fork) can hold a stationary sleeve between the two
           /                  \
          |   drum dia 240     |   drum: wall 1.4404 / tri-ply, hemispherical floor r = 120,
          |   depth 200, 7 L   |   one welded helical fin 15 high, hub + bayonet chuck on the back
           \__________________/
          (((( induction cradle ))))   curved coil fixed to the frame, 3 kW
                    ||
              spindle 1 (vessel side): spin 0-900 rpm, 25 Nm

   tilt 0 deg: pot          tilt 45 deg: wok / tumbler / kneader     tilt 180 deg: drum on top = hourglass
   tilt 135 deg: discharge over a chute, pan, plate                  tilt 150 deg + lance: wash, drains out

   swing circle dia about 850; two units above one another fill 900 W x 600 D x 1 750 H [E]
   flat sibling: "face pan" dia 300 x 30 on the same chuck, with a flat coil behind it
```

### 3.3 Kinematics and actuators

Per unit: frame tilt (1), spindle 1 spin (1), spindle 2 spin (1), spindle 2 axial (1), steady rest (1),
chuck release x2 (2) = **7; two units = 14**, plus a drain funnel flap and pumps. The transport system brings
boxes and heads; vessels are changed only a few times a day.

### 3.4 Tool and vessel set

3 drums (one with a rasp liner for peeling), 1 perforated drum (basket, runs inside a drum), 2 face pans;
heads: scraper/baffle, kneading hook, masher grid, blade, whisk, feed tube with piston (takes the cutting discs
of concept A; the disc clips onto the drum mouth and rotates with the drum), strainer head, cone roller,
spray lance, plain lid. About 18 parts.

### 3.5 Ingredient forms

All dosing happens **into the drum mouth at 45 deg tilt** through a dosing head (a chute with shutter or
sieve) held by spindle 2, with the box tilted above it by the transport system; the frame's tilt bearing blocks
carry load cells (±3 g on a 10 kg range [E]; worse than A because the whole frame is weighed). Seasoning is
pre-weighed in a cup and tipped in. Whole produce, leafy goods, granules, frozen goods: tipped in. Liquids:
nozzle in the head. Pastes: pucks or pouch. Raw meat pieces: tipped in; slices: freeze plate onto a face pan.
Eggs: cracker head.

### 3.6 The hard operations

| Operation | How |
|---|---|
| Peel potato, carrot | Rasp-lined drum at 45 deg, 60-70 % of critical speed (about 55 rpm for dia 240), water from the lance, 2 min; tilt to 120 deg with the strainer head to pour off the slurry; rinse twice. A drum peeler in its native geometry [R4]. |
| Peel onion | Same open problem as A; C adds nothing. |
| Dice, slice, shred | Steady rest holds the feed tube, the cutting disc or sweep knife rides on the drum mouth, spindle 2 pushes the piston (3 kN limits the dicing window to about dia 70 [E]). |
| Mince herbs | Blade head at 3 000-6 000 rpm in the drum at 30 deg tilt (the tilt keeps a small quantity in the corner under the blade, which a flat-bottomed Thermomix cannot do). |
| Crack egg | Cracker head; or idea S-8, which uses the two spindles directly. |
| Form Frikadellen | Not native. Tumbling gives balls (Klöße, meatballs: 20 rpm, wet drum, 60 s, the mass pre-portioned by the feed-tube extruder); flat patties need the extruder and sweep knife onto a face pan. |
| Rouladen | Not native: needs the apron roller as a separate head over a face pan. |
| Bread a Schnitzel | Two face pans mouth to mouth = clamshell; breading by flipping as in A, the frame tilt does the flip. Small pieces (goulash in flour, nuggets) tumble-coat in the drum, which is the industrial method [R4 8]. |
| Knead, roll out | Hook head stationary, drum at 45 deg and 60-100 rpm: a tilted-bowl spiral kneader. Roll out: cone roller head on a face pan. |
| Mash | Masher-grid head stationary, drum at 20 rpm drags the cooked potatoes through the grid repeatedly: "Stampf" texture, lumps below 5 mm after about 40 passes [?]; a riced, fluffy mash is not possible. |
| Toss salad | The native strength: tumble at 15 rpm for 10 s. Wash and spin in the perforated drum inside a drum: 600 rpm with the axis vertical. |
| Flip steak, pancake | Face pan to face pan, frame turns 180 deg. Crêpe batter spread by spinning. |
| Drain pasta | Strainer head on the mouth, tilt to 120 deg over the drain funnel. Hot water leaves through a closed chute. |
| Stir, sauté | Rotation at 45 deg with the fin; nothing to insert; scraper head for sticky sauces. |
| Discharge, plating | Reverse rotation: the helical fin augers the food out over the lip in a controlled stream, so the drum can portion directly. |

### 3.7 Cleaning and drying

* **In place.** Spindle 2 takes the spray lance (three fixed fan jets on a bent tube reaching floor, wall and
  lip). Drum at 150 deg tilt (mouth down-ish), 60 rpm: cold rinse 20 s to drain, 300 mL detergent solution
  recirculated through the lance 90 s with the induction cradle holding the drum at 55 °C, rinse 20 s,
  **induction heats the wet drum to 105 °C for 30 s**, spin at 900 rpm. About 3 min, 2-3 L. The drum is its own
  wash chamber; the jet is fixed and the surface moves, so coverage is complete.
* **Outside of the drum, mouth lip, cradle, frame:** Zone S. Drips run off the lip only at tilt angles above
  90 deg, over the drain funnel. A fixed nozzle ring on the frame rinses lip and outside in the same cycle.
* **Heads** are washed by docking them into a dirty drum during its wash (the drum washes its own tools), then
  parked dry. The helical fin is a continuous fillet weld with r = 6 on both sides.
* **Weak points:** the chuck interface at the back of the drum is in the splash zone and must be an umbrella
  design; the perforated drum has 2 000 holes (hot alkaline wash, inspect by camera against back light).

### 3.8 Off-the-shelf, custom, novel

* **Off-the-shelf:** servo drives, slewing bearing for the tilt, induction generator; drum-wok technology is
  mature in commercial machines.
* **Custom:** drums with chuck, curved induction cradle (the hardest part to source), frame, heads.
* **Novel:** the coaxial second spindle that makes lid, tool, second vessel and wash lance one interface;
  mouth-to-mouth drums on a tilting frame as inverter; tools washed inside the dirty vessel; fin discharge for
  portioning; tilt as a parameter for small quantities.

### 3.9 Biggest weakness

**Flat food and formed food are foreign to a drum.** Schnitzel, Rouladen, Frikadellen, steak and pancakes all go
to the face pan, where C is merely a complicated inverter. Second: the 850 mm swing circle is a large, moving,
hot assembly (guarding, MECH safety, and a 7 kg unbalanced drum at 900 rpm). Third: with 2-3 fixed drums a
four-component meal queues, unless more units are built.

---

## 4. Concept D — SKIN: soft vessels that are squeezed and turned inside out

### 4.1 Core idea

For all cold preparation the vessel is a **silicone bag with a rigid rim** or a **flat silicone folder**. The
machine never touches food: paddles, rollers and platens work on the *outside* of the skin (as a cook pounds a
Schnitzel between two sheets of film, or a laboratory "stomacher" blends a sample through the bag wall). To empty
and to clean it, the bag is **turned inside out** over a mandrel: the wall peels away from sticky food, and the
former inside becomes an open convex surface with no corner and no shadow. Cooking stays in steel pots and pans
(from A or B).

### 4.2 Sketch

```
  BAG ("sock")                         FOLDER ("Mappe")                    EVERSION
   ___________  rim ring R200,          two sheets 330 x 180 x 1.5,          rim held in fork
  |           | stainless, fully        hinged on one long side,              ____
  |           | encapsulated            stiff spine with grip holes          /    \   mandrel dia 150,
  |  3 L      | wall 1.5 mm platinum    ______________________              |      |  r = 40 nose, pushes the
  |  dia 170  | silicone, Shore A 40   /_____________________/|             |  ^   |  floor up through the rim:
   \_________/  depth 180              |  slice / dough      ||            =|==|===|= bag is now inside out on
    r = 40                             |_____________________|/             the mandrel, food has dropped
                                                                            into the vessel below; 10-30 N
  WALKER (kneader)            SQUEEZER                     FLAT PRESS / ROLLER
   bag hangs by its rim        two rollers close on the     folder lies on a plate; platen 3 kN or a
   between two paddles         bag and travel down: the     roller works on the top sheet; a peel bar
   120 x 120, stroke 40,       content leaves through a     then lifts the top sheet at 150 deg
   4 Hz, 300 N each            die ring on the rim
```

### 4.3 Kinematics and actuators

Walker crank (1), squeezer close + travel (2), eversion mandrel (1), flat press (1), roller travel (1), peel bar
(1), bag turner for the wash (1): **8**, plus a cutting device (A's cold column, or a bought cutter) and the
cooking stations. Envelope of the soft-prep part about 700 x 600 x 900 [E].

### 4.4 Tool and vessel set

Bags 3 L x6, 1 L x4; folders x6; die rings for the bag rim (patty die dia 70 with wire, Spätzle die, ricer
plate, piping nozzle, plain spout); clip-on strainer ring. All mechanisms are outside the food zone.

### 4.5 Ingredient forms

Boxes are inverted into a bag held open by its rim on a scale (as A). Bags are forgiving receivers: the rim ring
is the funnel. Liquids up to 2 L (the bag hangs). Pastes: the squeezer treats a supermarket pouch, or a storage
bag of paste, exactly like a bag of dough: rollers travel a measured distance, ±5 % [E], residue below 2 %
because the rollers flatten the skin completely. Raw meat slices: inverted pack onto an open folder, or freeze
plate. Eggs: cracked by a separate module into a small bag (whisked by the walker in 10 s: no whisk to wash).

### 4.6 The hard operations

| Operation | How |
|---|---|
| Peel, dice, slice, mince | **Not possible in a skin** (blades cut it). Done in steel (A's column), discharging into a bag. |
| Crack egg | Separate module. |
| Knead | Walker: 1 kg dough, 4 Hz, 300 N paddles, 4-6 min [?]. Squeeze-and-fold is what hands do; gluten development by this route is proven for stomacher-type sample blenders and "bread in a bag", not yet for a machine at 1.5 kg. Frikadellen mass, dumpling mass, marinades, batters (2 min), crumble: the ideal cases. |
| Form Frikadellen | Patty die ring on the rim, squeezer advances the mass, wire cuts pucks of 100 g onto the pan; ±10 % by roller travel, checked by weight. Klöße: round die, pucks drop into simmering water. Spätzle: die ring with 8 mm holes over the pot. |
| Flatten, bread a Schnitzel | Slice in a folder; platen 1.5 kN to 5 mm: the platen stays clean. Open, add 30 g flour, close, shake, open; pour in beaten egg from a small bag, close, the roller passes once to spread it; tip out the surplus; add crumbs, close, press at 40 N. The cutlet is slid into the pan by tilting the open folder to 60 deg (silicone releases breadcrumbed surfaces well). |
| Rouladen | Folder opened flat: the lower sheet is the rolling apron. Mustard stripe, fillings, then the apron bar draws the sheet over itself (as B). |
| Roll out dough | Dough ball in a folder, roller passes 4-6 times stepping down; no flour needed, nothing sticks to the roller. The top sheet is peeled at 150 deg, the folder is inverted over the baking tray, and the second sheet is peeled: a 2 mm sheet is transferred without ever being lifted. This is how thin dough is handled by pastry cooks (between two sheets), and it removes the usual sticking problem completely. |
| Mash | Cooked potatoes in a bag with the ricer plate on the rim, squeezer rolls them through (force as a ricer, 1-4 kN line load is high for the rollers [?]); or walker for a rustic mash. |
| Toss salad | 3 L bag half full, closed with a plain lid, walker at 1 Hz and 10 mm stroke, or simply inverted three times. Gentle. |
| Marinate | Native: little marinade, air squeezed out, bag clipped and returned to the cold store (PRP-036). |
| Flip steak, pancake; drain pasta | Not D's business; done in steel as in A. |
| Empty sticky masses | Eversion: residue below 1 % for dough, mince, mash, batter [?], against 5-15 % for a tilted bowl [R4 10.2]. |

### 4.7 Cleaning and drying

* The bag goes to the wash **inside out on a mandrel**: a smooth convex dome, r at least 40 everywhere. Four fan
  jets, mandrel rotating, 60 s cold rinse, 2 min at 55 °C, 80 °C final rinse 60 s (silicone takes it).
  Then the bag is turned right side out by the mandrel retracting with the rim held, and the outside, which was
  touched only by clean paddles, gets a 20 s rinse. Drying: silicone stays wet [R6], so hot air at 70 °C for
  8 min on the mandrel, with air fed through the mandrel.
* Folders are washed open and hanging by the spine, jets both sides, like baking mats.
* Walker paddles, rollers, platen: Zone S, never touched by food unless a skin fails; daily wash-down.
* **Odour and pigment:** silicone takes up onion, garlic, curry and tomato [R6]. Counter-measures: platinum
  silicone post-cured; colour-coded bag sets (raw meat, allium/spice, neutral/sweet); a weekly bake-out at
  150 °C for 1 h in the oven; bags are a wear part, replaced every 6-12 months (a cheap moulding).
* **Leak check:** a bag is tested before each use by closing it on the mandrel and applying 50 mbar; a cut skin
  is discarded (PRP-035 equivalent).

### 4.8 Off-the-shelf, custom, novel

* **Off-the-shelf:** silicone baking mats as the first folders; stomacher kinematics; rollers, cylinders.
* **Custom:** the moulded bag with encapsulated rim ring (one mould), die rings, walker, mandrels.
* **Novel:** the everting vessel (emptying by peeling and washing as a convex surface); the machine working only
  through the skin so that its own mechanisms stay out of Zone F; die rings on a squeezed bag as the universal
  former; pastes dosed by roller travel.

### 4.9 Biggest weakness

D is **half a system**: it cannot cut, cannot cook, cannot whip cream stiff (no shear), and silicone's odour
uptake threatens HYG-025. Kneading 1.5 kg of bread dough through a skin is unproven and the skin's fatigue life
under 300 N paddles is unknown (my guess: fine for 2 000 cycles, to be tested). Its value is as the raw-meat and
sticky-mass half of another concept.

---

## 5. Standalone sub-mechanism ideas

Each can be used in any concept. Feasibility: **H** high (known physics, similar products exist), **M** medium
(sound but needs a test), **L** speculative.

**S-1 Wash lathe with induction flash.** Wash every axisymmetric part by rotating it past a fixed meridian of
jets instead of spraying a static rack; then sanitise and dry it by heating the wet steel itself with an
induction ring to 105 °C for 30-60 s. Coverage is geometric, not statistical; energy for the hot step falls from
about 300 Wh (4 L of 80 °C water) to about 20 Wh (1.6 kg of steel through 60 K plus 5 g of water film) [E].
Needs ferritic or tri-ply parts; one camera sees the whole surface. **H** for the jets, **M** for even wall
heating.

**S-2 The receiving vessel is the rotor.** Slicing, shredding and sweep-knife discs clip onto the rim of a
rotating receiving vessel under a stationary feed tube. A food processor with no shaft, hub or seal; the disc
lifts off as a flat plate. Drive torque 2-3 Nm at 300-400 rpm through three notches in the base skirt (skirt
notches also drain the skirt when inverted). **H**.

**S-3 Freeze-plate lid for wet flat food.** A smooth stainless plate cooled to about −10 °C by a Peltier stack
freezes the surface film of a raw meat or fish slice in 1-2 s, lifts it (ice adhesion on steel is of the order
of 0.1-1 MPa, thousands of times the need), separates it from the stack beneath, and releases it on a reversed
current pulse. It replaces needle and suction grippers with a flat plate that has no hole and no crevice.
Commercial freeze grippers exist for fish fillets and textiles. Open points: fat-covered surfaces freeze poorly,
condensate on the plate. **M**.

**S-4 Shaking hob with slip-stick conveying.** The hob module rides a short linear axis with an asymmetric
stroke (slow out, fast back), the principle of horizontal-motion conveyors for fragile snacks. Pieces walk to the
curved end wall and roll over; reversing the asymmetry walks them back. Sautéing without any tool in the pan.
Force below 100 N. Limit: liquids slosh; not for deep fills. **M**.

**S-5 Breading by flipping.** Three shallow vessels (flour, egg, crumb). The cutlet is moved by clamping the
next vessel upside down on the current one and inverting: the loose coating falls with it and re-beds it, a
rack interposer sifts surplus back. No gripper touches a wet cutlet, no crumb leaves the closed pair.
About 8 flips of 5 s. **H**.

**S-6 Apron roller for Rouladen and cabbage rolls, without tying.** A silicone apron whose free hem is drawn
over a fixed bar (the "dolma roller" gadget, the sushi mat, the cigarette roller) rolls a filled slice in one
stroke. The roll is dropped seam-down into a trough insert in which the rolls are packed against each other; the
seam is set by searing seam-down first, then the set is clamshell-flipped. Replaces twine, toothpicks and clips.
Alternative fastening if that fails: a reusable spring-steel C-clip pushed on radially while the roll is still in
the apron. **M** (rolling), **M** (tie-free braising; many cooks do it).

**S-7 Form in the cooking vessel.** Do not make a patty and then move it. Press the mass to an even layer in the
pan with a platen, then part it with a divider lid with rounded cells; fry in place; flip the whole set by
clamshell. Same for fish cakes, Reibekuchen (grated potato mass spread and divided), biscuits on the tray.
Rounded-rectangle Frikadellen are a cosmetic change (adapted method, MEAL-013). **H**.

**S-8 Glass-cutter egg opening.** Hold the egg between two silicone cups on coaxial spindles, rotate one turn
against a small toothed wheel that scores shell and membrane on the equator, then pull the cups apart. The shell
breaks along the score like cut glass: two clean cups, no crushed zone, few fragments; the yolk stays whole
(fried egg), and tilting the lower cup while holding the yolk back gives separation (UO-06). Half shells stay on
the cups and are dropped into the waste. Open points: suction lines need a trap and a rinse; variation in egg
size. **M/L**.

**S-9 Freeze to count.** Pastes and awkward small quantities (tomato paste, stock concentrate, mustard, butter,
lard, chopped herbs, garlic paste, cream) are frozen once, at ingestion or after opening, in a silicone tray of
5 g and 20 g cells and popped out by everting the tray. From then on a paste is a **discrete piece** that is
counted, not metered: no pump, no tube, no residue, and the opened jar's shelf-life problem is gone (DEC-3).
Accuracy is the cell size (±2.5 g, within PRP-011 for 5-50 g). Cost: freezer space for about 12 small boxes and
a filling step. **H**.

**S-10 Pouch squeezer.** Anything pasty that is not frozen is kept in a soft pouch (its own supermarket pouch or
tube, or a silicone storage bag) and dosed by two rollers travelling a measured distance; roller travel is
proportional to volume, the scale trims. The rollers touch only the outside. Residue below 2 %. **H**.

**S-11 Hourglass orifice and vibrated sieve as valves.** Free-flowing solids pass an orifice at a rate that is
almost independent of the head above it (Beverloo: about 43 g/s for rice through dia 20, 4.7 g/s for salt
through dia 6, 0.6 g/s through dia 3 [E]); dosing becomes shutter time plus a final trim. Cohesive powders do
the opposite: they bridge over a 1-2 mm mesh until it is vibrated, so the vibrator is the valve and nothing
moves in the food path. One collar with an orifice turret and one sieve collar dose all dry goods. **H**
(granules), **M** (flour in a humid kitchen).

**S-12 Undersized-die onion peeling.** Halve the onion pole to pole, cut off root and tip, push the half,
cut face first, through a D-shaped die 6-8 mm smaller all round than the onion (one of three dies, chosen by
camera). The loose inner layers slip through; skin and outermost fleshy layer are stripped off and stay behind as
waste. Trades 20-30 % of the onion for having no air blast and no fine manipulation. **M/L**, needs a test on 50
onions before anyone relies on it.

**S-13 Three-layer inversion: drain in its own pot.** Pot, strainer interposer, empty pot; invert; then invert
only pot + strainer back. The solids never leave their pot, the liquid is caught (pasta water, blanching water,
potato water for the sauce) instead of going down a sink, and no open stream of boiling water exists at any
moment. Also skims: invert slowly and stop when the fat layer has passed. **H**.

**S-14 The recipe follows the scale.** For goods that cannot be dosed finely (whole onions, potatoes, a head of
lettuce, a pack of mince) do not try: take what comes out, weigh it, and scale seasoning, liquid and time to the
measured mass. Dosing accuracy is then needed only for fine, cheap-to-dose goods. A control idea, but it removes
a whole class of singulating and portion-cutting mechanisms. **H**.

**S-15 Spin-spread and cone-roll on a rotating pan.** A pan on a turntable spreads crêpe batter by rotation
(150 rpm for 2 s, thickness set by batter mass) and rolls dough to a round sheet under a conical roller whose
apex lies on the axis (pure rolling, the potter's jigger). Pizza sauce as a spiral from a fixed nozzle. **H**.

**S-16 Eversion for sticky transfers.** Any sticky mass held in a soft vessel is released by turning the vessel
inside out: peeling needs a few newtons where scraping leaves 5-15 %. Works for dough, mince, mash, cooked rice,
and for frozen pucks. The everted vessel is then its own best wash geometry. **M** (durability, odour).

**S-17 Tools washed inside the dirty vessel.** Before a pot or drum goes to its wash, the soiled stalk tools and
lids of that dish are docked into it and the vessel's own wash cycle cleans them; the vessel is the wash
chamber, one chamber per allergen/raw group, no separate tool washer. Works best where the vessel rotates past a
fixed lance (concept C, wash lathe). **M** (tool surfaces facing away from the jet need a second lance angle).

**S-18 French-press piston.** A perforated piston in a straight-walled beaker presses solids down while the
liquid rises above it and is poured off by inversion with the piston held: drains tinned goods, presses grated
potato and thawed spinach (UO-36), strains stock. Spinning a basket at 900 rpm (109 g at r = 120) is the
alternative where pressing would crush. **H**.

**S-19 Comb piston.** Every grid (dicing, wedge, ricer) has a mating pusher with studs or slots that passes
through it to the far side. The last plug of food goes into the dish instead of staying in the grid, and the
grid arrives at the wash already free of fibres, which is where push-through cutters normally fail. **H**.

The following five were added after the corpus check of section 7.

**S-20 Shake-peel in a closed vessel pair.** Two cans clamped rim to rim and shaken hard by the inverter
(±60 deg at 3-4 Hz, 15 s) are the cook's "two bowls" trick: dry garlic cloves lose their skins, hard-boiled
eggs with 50 mL of water crackle and slip their shells (PLE), blanched almonds and tomatoes slip. Skins are
separated afterwards by a strainer disc or by floating them off. No extra part at all. Garlic that is going to be
minced does not even need this: unpeeled cloves go through the ricer disc with the comb piston and the skins stay
behind [R4]. **H** (garlic press route), **M** (shake-peel yield, my guess 70-90 %).

**S-21 Wedge-and-core disc with a concentric receiver.** An apple divider scaled up: 6-8 radial blades around a
central tube (dia 25 for apples and pears, dia 40 for peppers). The piston pushes the fruit through; wedges fall
into the pot, the core with seeds and stalk goes down the tube into a beaker standing inside the pot (the hat
beaker nests in the pot, so the split receiver costs nothing). Cores apples, pears, peppers, halves and de-stalks
tomatoes, quarters cabbage heads around the stalk. Needs the fruit placed with its stalk axis vertical (camera +
gripper); a tilted pepper loses 10-20 % to the core tube. Force about 1-2 kN. **M**.

**S-22 Ring-build and push-out (assemble and unmould).** A sleeve standing on a plate or base disc is the
chef's ring mould. Layers are dosed into it in order (burger: bun, patty, sauce, salad, bun; tiramisu, layered
salad, potato gratin tower, tartare-style starters), then the quill holds the stack down with a soft piston while
the fork lifts the sleeve off. The same sleeve on a base disc is a spring-form tin: bake in it, lift the sleeve,
the cake stands on its disc. Puddings and panna cotta set in silicone cups and are turned out by everting the
cup (S-16). Everything else is unmoulded by the rim-to-rim inversion onto a plate carrier. **H** for ring-build,
**M** for sticky cakes (needs greased or lined sleeve).

**S-23 Sickle carving in the stack.** A boneless roast stands on end in a wide sleeve (grain vertical, so slices
are across the grain), held down by a 1.5 kg follower; a long scalloped sickle blade on the rim of the slowly
rotating receiving pan (40-60 rpm, draw angle about 45 deg, blade speed 0.5 m/s at r = 100) takes one slice per
turn; the fork lowers the sleeve by the slice thickness (2-15 mm) per turn. Slices fall flat into the warm pan
with their juice. Also slices bread, sausage, cooked potatoes for Bratkartoffeln. Not for bone-in poultry.
Open point: hot, soft braised meat may tear instead of cutting at this blade speed [?]. **M**.

**S-24 Dice blocks once, then count.** Butter, lard, firm cheese, tofu and bacon are pushed through the dicing
stack once, when the pack is opened (10 g cubes for butter, 10 mm dice for the rest), and stored as loose pieces
in their box. "Cut a defined portion off a block", which the corpus finds in 51 % of meals, becomes piece dosing
by weight; cold butter cubes are also what Mürbeteig and Streusel want. The sibling of S-9. **H** (butter cubes
must stay below 8 °C or they fuse).

---

## 6. Which concept I would bet on

**Concept A (STACK), with three imports.**

Why A:

* It is the only one that is a **whole** preparation system from one kit: it peels, dices, slices, minces,
  presses, kneads, whips, forms, drains and flips with one column, one inverter and passive parts. B and D each
  need another machine for half the unit operations; C needs a face-pan sideline for every flat dish.
* It takes the hygiene requirement at its root: no shaft seal, no bearing, no motor in any washed part; food is
  processed only inside closed stacks; every part is a plain open stainless shape (HYG-013, HYG-016, HYG-019).
* Its risks are **logistics** (many parts, many moves), which engineering and software reduce, not unproven
  physics. The physics I am unsure about (onion peeling, tie-free Rouladen, PE chopping insert) is equally open
  in every concept.
* The quill column is cheap to prototype: a bench drill-press frame, a servo cylinder, a turntable and a dozen
  turned parts test the dicing, ricing, slicing and extrusion claims in weeks.

Imports:

1. From B: **a rectangular GN 2/3 flat pair** (thermoplates) for Schnitzel, Rouladen, steak, tray-size dough and
   everything that goes into the oven, with the platen, divider and apron roller. A's round pans stay for
   pancakes and single steaks. This fixes A's one-Schnitzel-at-a-time weakness. The inverter must then accept two
   rim standards (R260 and GN 2/3).
2. From D: **silicone folders** as the contact skin for all raw-meat flat work (flatten, bread, roll), so that
   platen and roller never become Zone F, and **freeze-to-count / pouch squeezing** for pastes.
3. From C: make A's column **tiltable by 180 deg** in a second design step. It then is its own inverter and
   tumbler, and the separate inverter station disappears. I would not start with it (swing space, guarding).

What I would drop: C as a whole (too much moving mass for what it adds) and B's shaking hob for anything liquid.

After the corpus check (section 7) the bet stands, but import 1 is no longer optional: the corpus asks for a
36 cm pan and a 6 L braiser for twelve Rouladen, which only the GN 2/3 flat family delivers. The honest name of
the bet is therefore **"STACK + SANDWICH": round cans under a quill for everything that flows or is cut,
GN 2/3 clamshell trays for everything that lies flat, one inverter for both.**

---

## 7. Check against the meal corpus (`research/02-meal-corpus.md`)

Added after the corpus was finished. Codes are the corpus's operation codes; percentages are shares of the 248
meals. Rating of my own answer: **ok** mechanism exists in the concept and rests on known practice; **test**
mechanism exists but its success rate is a guess; **buy** covered only by the purchase workaround; **no** not
covered.

### 7.1 Operations with no purchase workaround (union 29 % of meals): these decide the bet

| Op | Share | A | B | C | D | Mechanism |
|---|---|---|---|---|---|---|
| FLP flip / turn | 12.9 % | ok | ok | ok | no | Clamshell inversion into a second hot vessel. It is indifferent to what is flipped: pancake, omelette and tortilla (rated D5 for a spatula) are supported over their whole area during the turn and drop only the pan depth (25-40). This is where the vessel lens pays most. Limits: needs a second preheated pan and a free hob for it; fried egg "over easy" and omelette folding are not flips (fold by sliding half out onto the plate and turning the pan over it, a plating move). B alone can also avoid the flip with a heated platen lid. |
| ASM assemble / build | 6.9 % | test | ok | no | no | Layered builds in a vessel are native: lasagne, moussaka, pizza topping (rotating pan or tray under fixed dosers), and ring-build S-22 for burger and layered cold dishes. Open-hand assemblies (taco, filled sandwich, wrap) are **not** covered by any of my concepts beyond rolling a wrap with the apron roller; I would serve tacos and wraps as components. My estimate: 11-13 of the 17 meals. |
| CAR carve cooked meat | 4.8 % | test | no | no | no | S-23 sickle carving for boneless roasts. Bone-in birds: parts are roasted and served as parts (requirement X-04 already allows this). B, C, D have no answer and would leave it to the serving module. |
| UNM unmould | 4.4 % | ok | ok | test | ok | Rim-to-rim inversion is unmoulding by definition; spring-form by lifting a sleeve off a base disc (S-22); set desserts by everting a silicone cup (S-16). Risk: sticking of cakes, as for a human. |
| SCO score / slash | 2.8 % | ok | ok | no | no | A: a comb of parallel blades on the quill stamped to a depth stop (pork rind needs the force: 8 kN is there), turntable indexes 90 deg for the cross-hatch. B: the tray travels under a fixed blade, a true draw cut, better for slashing proved bread. |
| POA poach egg | 0.4 % | test | no | no | no | Egg cracked into a small silicone cup floated in the simmering pot, turned out by eversion. One meal; low priority. |

Result: A covers five of six (two of them subject to a test), B four, C two, D one. Flipping and unmoulding,
17 % of meals between them, fall out of the rim-to-rim rule without any extra mechanism.

### 7.2 The shaping cluster (15.3 %, avoidable only with semi-finished products)

| Op | Share | Answer (concept A + GN flat family) | Rating |
|---|---|---|---|
| STU stuff / fill | 6.5 % | Sleeve + piston is a filling gun: a nozzle disc on the sleeve, quantity by piston travel. Rigid cavities (peppers cored by S-21 and stood in a cup rack, tomatoes, cannelloni laid in a tray, apples) are fillable; soft pockets (cordon bleu, Maultaschen, dumpling centres) are not. | ok for about 10 of 16 meals, rest buy |
| WRP wrap / roll | 4.0 % | Apron roller S-6: Kohlrouladen (leaves blanched whole, which LSP makes hard), burrito, biscuit roll on its baking mat (roll the mat itself, folder of concept D). Spring rolls, sushi, strudel: no (requirement X-06, X-12). | test, about half |
| FRM shape small pieces | 2.8 % | Extrude a log through a die disc and cut with the sweep knife: gnocchi, croquettes, cookie blanks, falafel pucks. Schupfnudeln and balls: tumble the cut pieces in a slowly rotating floured can against a fixed baffle (a dough rounder). | test |
| SHD shape dough | 2.4 % | Loaf: prove and bake in a tin (the pot is the tin). Rolls: portion by extrusion, round in the rotating can. Pizza: cone roller S-15 or roller head. Lining a tin: press the dough into the pan with a stepped platen. Braids, pretzels: no (X-09). | ok / no |
| BRD bread / coat | 2.0 % | Breading by flipping S-5. | ok |
| RLT roll and tie | 1.6 % | Apron roller + seam-down trough pack, no tying; clip as fallback. Twelve Rouladen fit a GN 2/3-100 in two rows of six (55 x 150 each). Roast tying and trussing: bought tied. | test |
| SKW skewer | 0.4 % | No. Cubes cooked loose. | no |

The cluster is where my concepts are weakest in *proof*: three "test" entries hang on the apron roller and the
extrude-and-cut former. Both are single-axis mechanisms, so they are cheap to test early, and they should be.

### 7.3 Peeling and trimming (69.8 % of meals, all with a level-1 purchase workaround)

| Op | Share | Answer | Rating |
|---|---|---|---|
| PLA peel onion, garlic | 52.0 % | Garlic: unpeeled through the ricer disc, or shake-peel S-20: ok. **Onion is the single most valuable unsolved operation and my concepts do not solve it with confidence.** Candidates in order of my belief: (1) blanch 45-60 s in a pot that is boiling anyway, shock, then push through the undersized die S-12: the blanch loosens the skin so the die strips skin only and the loss falls from 20-30 % to about 5-10 % [?]; outer layer slightly softened, irrelevant for the cooked dishes that are most of the 52 %; (2) cold die S-12 with the loss accepted, for raw onion; (3) purchase of peeled or frozen diced onion, which the corpus recommends as the starting point. Build (3) first and keep a disc slot for (1). | buy, test |
| PLP peel potato, carrot | 24.2 % | Rasp-floor stack (A) or rasp drum (C). | ok |
| COR core / deseed | 20.2 % | S-21 wedge-and-core disc with concentric receiver: apple, pear, pepper, tomato stalk, cabbage stalk. Pumpkin, avocado, cucumber seeds: buy or leave. | test |
| TRE trim ends | 12.5 % | Long goods fed axially through the S60 tube: the first and last sweep-knife cut go to a waste beaker (leek root, cucumber and carrot ends, asparagus ends). Beans, sprouts, strawberries, mushrooms: buy trimmed or frozen. | partly, buy |
| PLS peel apple, pear, cucumber | 10.5 % | The rasp bruises soft fruit. Unpeeled where the recipe allows, otherwise buy. No concept of mine peels an apple properly. | buy |
| PLH peel celeriac, kohlrabi, beet | 7.3 % | Rasp stack with longer time, loss about 30 %; ginger as frozen pucks (S-9). White asparagus: no. | ok / no |
| SEP separate egg | 6.9 % | Slotted yolk cup under the egg disc, or S-8. Carton white whips worse, so this should be built. | test |
| STR, PLE, PIT | 3.6 / 2.8 / 1.2 % | STR buy; PLE shake-peel S-20; PIT buy. | buy / test / buy |

### 7.4 Dosing and the everyday operations

* **DUN** countable whole items (93 %) and **DME** raw meat (43 %) are the two D3 operations the corpus puts in
  the foundation tier. DUN: inversion through a piece chute plus "the recipe follows the scale" (S-14). DME:
  inversion for pieces and mince, freeze plate (S-3) for stacked slices; the corpus suggests one piece per tray
  with a peel-off liner, which is the silicone folder of concept D. Both remain "test".
* **DBL** portion block solids (51 %): I had missed this. Answer S-24 (dice once, then count) and S-9.
* **GRS** grind pepper and spices (43.5 %): not a vessel problem; a burr mill as the resident insert of the pepper
  box, or pre-ground.
* **DRN** drain (22.6 %): three-layer inversion S-13. **TOS** toss (14.5 %): closed pair in the inverter.
  **STC** stir continuously (6.5 %): rotating scraper lid. **SQZ** (1.6 %): French-press piston or spin basket.
  **FLD** fold (4.4 %): scraper lid at 10-20 rpm; quality is a test.
* **DFR** deep-fry (4.0 %) is excluded by requirement X-01 in all concepts.

### 7.5 Vessel sizes: corrections to section 1

| Corpus need (6 persons) | Section 1 had | Correction |
|---|---|---|
| Boil pot 9 L | tall pot B250 x H180 = 8.8 L | make it H190 = 9.3 L; it is heavy (about 9 kg full), so it is filled and drained on the hob and never inverted by the three-layer trick when full: for the 9 L pot use the spin basket as a lift-out pasta insert instead |
| Mixing bucket 8-10 L (dough rising to 4-5 L, 1.2 kg leaves) | pot 5.4 L | the tall pot doubles as the mixing bucket; two of them needed |
| Whip 1 egg white (30 mL) up to 6 (1.5 L) | beaker B160, 2.6 L | 30 mL is a 1.5 mm film in a 160 bore. Add a **small hat beaker B90 x H110, 0.7 L**, same R260 rim, with a small whisk stalk |
| Pan 28 cm, and 36 cm for 1.5 kg Bratkartoffeln | pan B250 (491 cm2) | the round pan is below both. **GN 2/3 thermoplate** (floor about 330 x 300 = 990 cm2) equals the 36 cm pan (1 018 cm2) and replaces it; the round B250 pan stays for pancakes (24-25 cm) and eggs |
| Braiser 6 L, 12 Rouladen | pot 5.4 L | GN 2/3-100, about 9 L, with its lid, hob to oven |
| Sauce pot 1.5 L, minimum 0.15 L | beaker B160 | ok; tri-ply beaker on the hob |
| Wok 36 cm | none | not covered; stir-fry (2.8 %) in the GN 2/3 on full power, marked as adapted |
| Concurrent heat: up to 4 hobs + oven; 6 food vessels at once | 2 hobs | **four heated positions**: two round (with light quills) and two GN 2/3, plus the oven. This raises the actuator count of A from 17 to about 19 and the module width by about 450 |

The cans list of section 1.4 becomes: pot 5.4 L x3, tall pot 9.3 L x2, pan 2 L x2, beaker 2.6 L x3, small beaker
0.7 L x3, plus GN 2/3 thermoplates x4 (two depths) and a wide sleeve S250 for roasts and cakes: about 55 parts.

### 7.6 What the corpus changes in my judgement

1. The rim-to-rim rule is worth more than I had claimed: it answers FLP and UNM (17 % of meals, no purchase
   workaround, FLP rated D4-D5 for a spatula robot) with a mechanism of two actuators.
2. The round kit alone is too small for frying and braising for six. "STACK + SANDWICH" is the concept, not an
   option.
3. Onion peeling (52 %) is not solved by the vessel lens. It should be handled as the corpus proposes: purchase
   first, peeler as an upgrade, and the blanch-and-die variant tested early because its value is so high.
4. Concepts C and D fall further behind: C answers two of the six no-workaround operations, D one.
5. My concepts do not assemble open-hand food (taco, sandwich) and do not carve bone-in birds. I would state
   these as known members of the 5 %.

---

## Open issues

0. Coverage has not been counted meal by meal. Section 7 rates operations, not the 248 recipes; the "test"
   entries (apron roller, extrude-and-cut former, wedge-and-core, sickle carving, freeze plate, onion die) decide
   whether the bet reaches 95 % without level-2 purchases, and none of them has been tried.
1. The R260 rim, the base skirt with drive notches and the GN 2/3 flat pair are vessel standards that the
   architecture (A1) must freeze; the storage box must fit inside the rim (GN 1/6 does, GN 1/3 does not: GN 1/3
   boxes need the rectangular collar of the flat family).
2. Rack logistics for about 50 parts and the number of gantry moves per meal need a simulation with real
   recipes once the meal corpus exists.
3. Tests needed before P3 can rely on them: onion die peeling (S-12), tie-free Rouladen (S-6), induction flash
   on can walls (S-1), vibrated-sieve flour dosing at 60-70 % RH (S-11), dicing force with staggered blades,
   residue of hourglass transfers per food type (PRP-013), walker kneading of 1.5 kg dough (D).
4. Which parts of the wash lathe's job the central warewasher of D7 takes over (grids, egg disc, folders).
5. Power: two hobs, wash-lathe sump heater and induction flash must be scheduled (DEC-1 helps).
6. Noise of the abrasive peeler, the stamp chopper and an 8 kN press stroke against the noise limits.
7. Whether rounded-rectangle Frikadellen, diced-bacon Rouladen and round-pressed Schnitzel count as "adapted
   methods" within the 10 % allowance of MEAL-013.

## Risks

| Risk | Concept | Consequence | Mitigation |
|---|---|---|---|
| A stack is mis-seated and 8 kN is applied | A | bent part, debris in food (PRP-035) | seat sensing by the fork load pins before pressing; force-travel signature monitored; press limited to 1 kN until the signature matches |
| Hot liquid escapes during an inversion | A, B, C | scald hazard inside the cell, large spill | gasket on every coupler, clamp-closed sensing, inversion only inside a closed splash hood, max fill 60 % |
| Part count grows beyond what the rack and the wash can turn over | A | meal time and PERF-005 missed | cut the kit after recipe walk-throughs (PRP-003); parts used by < 1 % of meals are dropped |
| PE chopping insert, silicone skins, apron liner wear or take up odour | A, D | hygiene failure (HYG-020, HYG-025) | treat as dated wear parts with automatic leak/scoring check; colour-coded sets |
| Freeze plate fails on fatty or dry-surfaced meat | all | slices cannot be singulated | fallback: invert the whole pack into a folder and separate by peeling the folder |
| Grids and perforated parts are not cleaned by the lathe | A, C | residue in holes | comb pistons; back-light camera inspection; route to the central warewasher |
| Unbalanced load at 900 rpm (wet leaves, one drum-side lump) | A, C | vibration, noise, bearing wear | ramp with imbalance detection from motor current, redistribute at low speed as washing machines do |
| Concept relies on several unproven food results at once | all | the 95 % goal is met on paper only | each **[?]** above is a bench test of days, to be done in P3 before selection |
