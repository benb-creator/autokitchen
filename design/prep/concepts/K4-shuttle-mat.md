# K4 — Shuttle mat: the membrane cell (round P3 exploration)

Explorer document for candidate K4 of [02-concept-catalogue.md](../02-concept-catalogue.md), written to
[03-exploration-brief.md](../03-exploration-brief.md). Source: `ideas/F-first-principles.md` concept A (TUCH),
with mechanisms borrowed from the catalogue (SM numbers given where used).

Status of all statements: **nothing was built or tested.** Tags: **[E]** my estimate or calculation,
**[F]** taken from the idea document F, **[R2]/[R4]/[R6]** research files, **[K]** general knowledge of existing
practice, not verified in this session. Confidence: H / M / L as in the catalogue.

Coordinates: X along the wall (right positive), Y from the back wall to the front, Z up from the floor.
All mm.

Contents: 0 what changed from the catalogue · 1 definition · 2 mechanism · 3 intake and dosing ·
4 operation table · 5 benchmarks · 6 cleaning · 7 numbers · 8 coverage · 9 failure modes · 10 risks ·
11 improvements · 12 open issues and requests.

---

## 0. What I changed from the catalogue definition, and why

The catalogue definition (section 3.5) is a mat between two bars on cranks, a rail of fixed tools, a
magazine of loose mats, a ram-and-die head and "a bowl and pots" for the rest. Worked out to the level
of the exploration brief (hobs and oven in scope, six persons, all twelve benchmarks), five weaknesses
appeared that the definition does not answer. I changed the concept where an invention inside its own
spirit (flexible web, rotary shafts through one wall, everything extruded along Y) fixed them.

| # | Catalogue definition | This document | Reason |
|---|---|---|---|
| C1 | Reel B on a crank, R = 220; the nose reaches one vessel | Reel B on a **two-link arm** (shoulder, elbow, bar spin; three coaxial rotary drives through one wall cartridge). The nose can be put anywhere in a 850 mm radius in the X–Z plane | The mat must deliver into four heated positions, a bowl, a tin and the waste port. With a crank it serves one. The arm also gives the new primitive ENVELOPE (C3) |
| C2 | Magazine of ten loose mats, hem rods on magnets | **Roller-blind cassettes**: five mats stay wound on their own driven reels under the table; arm B fetches the hem of the wanted mat and draws it out through one wash gate. No loose mat is ever handled | Mat exchange was the least credible step of the original (threading a limp sheet onto two bars). A used mat is washed *while it is retracted*, so the exchange and the wash are one motion |
| C3 | Roller and blade touch the food | **ENVELOPE**: arm B carries the free end of the mat back over the food; roller and press work on the back of the mat (SM-091 with one sheet). The mat is then peeled off at 150–180° | Answers "sticky mass winds round the roller" (F risk 2) without scraper or flour |
| C4 | Ram-and-die head (3 drives, 8 kN) for dice | **Slab–strip–chop** dicing on the cutting mat: blade slices, a free-rolling disc-knife roller cuts strips, blade cross-cuts. The die head is kept only as a fallback module (section 11) | Removes the only high-force axis (X14), eight dies and their washing; also dices raw meat, which a grid does badly. **It is unproven** (risk R4) |
| C5 | "Liquids stay in a bowl and pots" (not designed) | **Station P1**: the first hob position is a universal liquid station — turntable 0–600 rpm, induction, a swing-in vertical spindle (whisk, beater, blender) and the loop zone directly above it. **All four hob positions are slow turntables**; stirring is a passive scraper hung on a wall peg | A two-dimensional cell cannot stir in Y. Rotating the vessel restores the missing axis with a motor under the deck |
| C6 | No vessel handling | **Vessel arm C**: a second arm of the same module as B, carrying an electro-permanent-magnet shoe for vessel tabs. Lifts, carries, pours, inverts pan pairs, loads the oven | Exploration-brief ruling 1 puts handling at the hob in scope. This is a rigid manipulator, which the catalogue excluded for K4; it handles vessels only, never food |
| C7 | Six mat types incl. cavity mat M6 and TPU anvil M2 | Five cassettes: **K** cutting (UHMW-PE film), **S** silicone for class R and sticky work, **D** silicone for dough and RTE, **P** PTFE-glass open mesh, **R** stainless rasp foil. Cavity mat dropped | TPU hydrolyses above 60 °C [R6], so it cannot take the steam pass. Patties are made by log-and-cut; nothing needed the cavity mat |
| C8 | Blade lands on the mat over the steel table | Blade lands on the mat over a **soft anvil strip** let into the table, under torque control | Limits contact stress on the mat (risk R3) |
| C9 | Air knife dries the mat | Squeegee lips and the mat's own heat after the steam slot; final drying extended in warm air | Noise (NOI-003) and power of an air knife |
| C10 | Salad dried by spinning the rolled-up mat | Lift-out basket spun on the P1 turntable (a salad spinner) | Known practice instead of an unbalanced roll on a cantilever |

What did **not** survive honest dimensioning: "lowest mechanical complexity, 13 actuators". With hobs,
vessel handling and the liquid station in scope the count is 26 (section 7). The mat line proper still has 11.

A finding that the definition hides and that shapes everything below: **a two-dimensional cell has no yaw.**
Nothing on the mat can be turned about the vertical axis. Consequences and the workarounds (pour direction
sets the orientation; two cutting directions; the P1 turntable as a turn plate) are in section 2.6.

---

## 1. Definition

The cell is an extrusion along Y: every moving part is a bar or beam cantilevered from the back wall
over a 400 mm wide working zone, and every drive is a rotary shaft through that wall (hob turntables: through
the deck from below). A roller-blind mat is drawn from a cassette under the table, across a 330 mm
table, and out to a bar on a two-link arm. Seven primitives do the food work:

| Primitive | Motion | Used for |
|---|---|---|
| SHUTTLE | cassette reel and bar B wind against each other; food passes under a fixed tool | dosing in rows, slicing, scoring, sheeting, flattening, conveying |
| NIP | roller arm presses on the mat over the table, gap 0–60 mm, ≤ 600 N | sheeting, flattening, levelling, pressing crumbs, mangle |
| CHOP | blade beam against the mat over the soft anvil, mat jogs between strokes | slices 1–30 mm, fine chop, trim, score, portion, carve |
| LOOP | arm B comes close to the table edge; the slack hangs between two cheeks as a trough with a moving wall | tumble, toss, fold, round, roll up, rub, rasp-peel |
| ENVELOPE (new) | arm B carries the mat back over the food on the table; tools act on the mat's back; then peel | pounding meat, pressing, sheeting sticky dough, breading press |
| NOSE | bar B is placed over any target and winds in; the mat is pulled from under the food | transfer into P1–P4, bowl, tin, tray, waste port; also turns the item over |
| SLING (new) | the mat spans freely from the table edge to bar B up to 1.1 m away and conveys | transport from the dock to any vessel; nothing else carries food in X |

Liquids never go on a mat. They are dosed into a cup or straight into the vessel, mixed, whipped and
blended at station P1, and cooked in vessels on four turntable hobs. Vessel arm C moves vessels.

**Envelope:** 1 560 mm of wall × 600 deep × 2 000 high, containing the mat cell, four heated positions,
the oven (45 L class, turned 90°, mouth to the left), wash gate, sump and drives. Free volume of about
1 100 × 450 × 300 under the hob deck is left to the architect (ware store or washer).

```
 FRONT VIEW (door removed). Heights above floor. Back-wall gallery (Y = 0..60) carries all arm links.

 2000 +--------------------------------------------+-----------------------------------------+
      | extraction hood over P1/P2, grease trap    |                                         |
 1955 |                     camera 2 (hob row)     |   OVEN 45 L, combi-steam, turned 90 deg |
      |  box port                                  |   mouth faces left (lift door)          |
 1650 +--[dock: tilt, lid, vibrate]--camera 1      |   X 610..1160, Z 1500..1955             |
      |      | pour edge X -280                    +--------<mouth X 610>--------------------+
 1500 |      v          (sB) shoulder arm B                       fume gap, condensate lip   |
      |   roller arm   blade arm   X 380, Z 1350      (sC) shoulder arm C  X 700, Z 1250     |
 1330 |     (o)          |                 \                        /                        |
      |   ___O___________|___   cheeks      \ link 430             / link 430               |
 1150 |(L)==========mat=====(E)~~~~~~~ SLING ~~~~~~(B)            [shoe]   wall pegs for     |
      | |   TABLE 330x420    | \  LOOP /  spindle crank            |      scrapers at each P |
      | G  soft anvil strip  |  \_____/   (swing-in, R 300)      lids, baskets               |
  880 | G  wash gate         |dump                                                           |
      | |                    |port   P1          P2          P3          P4 (36 cm / GN 2/3) |
  700 | cassettes K S D P R  +==[turntable]==[turntable]==[turntable]==[turntable]===========+ hob deck
      | 5 reels, dia 80-100  | 3.5 kW 0-600rpm  2.5 kW      2.5 kW       3.5 kW   | vessel   |
  380 +----------------------+  coils, turntable motors, load cells, inverters   | port to  |
      | sump 2 L, pump,      +---------------------------------------------------+ washer / |
  150 | heater, steam gen.   |   free volume 1100 x 450 x 300 (architect)        | plating  |
      +----------------------+----------------------------------------------------+---------+
     X -380   -330          0      150         440         730        1030      1180
       |<------ 380 ------->|<--------------------------- 1180 ---------------------------->|
                                 total inside 1560 incl. 2 x 20 side walls

 TOP VIEW at Z = 1150 (mat level)
   Y
  600 +== door (glass in a frame, 30) =========================================================+
  570 |  front cheek / lip guide                                                               |
  480 |  +---------------------+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -   |
      |  |                     |E  mat 400 wide (Y 70..470), SLING to bar B                    |
      |  |  TABLE, mat on top  |    ( P1 )      ( P2 )      ( P3 )      (  P4  )  below         |
      |  |  roller    blade    |    dia 300     dia 300     dia 300     380                    |
   70 |  +---------------------+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -   |
   60 |  gallery: links of arm B (Y 0..28) and arm C (Y 30..58), roller arm, blade arm, gutter |
    0 +== back wall, 3 mm 1.4301, all rotary seals ============================================+
  -90 |  dry drive room: motors and gearboxes lie flat against the wall                        |
      +----------------------------------------------------------------------------------------+
```

The Y budget is tight: 90 drive room + 3 wall + 60 gallery + 400 mat + 17 front cheek and clearance + 30
door = 600 [E]. The mat is therefore 400 wide, not 440 as in F; a 400 × 300 baking tray takes a sheet
300 wide, and a 36 cm pan is fed by moving the nose during the drop.

---

## 2. Mechanism

### 2.1 Mat line

**Table.** 1.4404 plate 330 × 420 × 6, top at Z 1150, with a 3° cross slope to the gallery gutter (the mat
lips keep food in). A 12 mm wide strip of 60 Shore A platinum silicone is bonded flush into a groove under
the blade line at X −60 (soft anvil, replaceable with the table plate as an LRU). Left edge roller L
(Ø 40, idle, flanged) at X −350; right edge roller E (Ø 30, idle, flanged) at X 0. Both on dry-running
iglidur bushes on fixed stub axles from the back wall and the front cheek.

**Cheeks.** Two 1.4404 plates, X 0…300, Z 880…1200, at Y 70 and Y 470, flanking the loop zone above P1.
The back cheek is the wall of the gallery; the front cheek hangs from the front frame.

**Cassettes.** Five reels on a plate under the table (X −370…−40, Z 380…860), each a Ø 40 stainless tube
on a splined stub shaft through the back wall with its own 20 Nm gearmotor. A cassette (reel, mat, hem
rod) is pulled off its spline to the front after opening the door and a quarter-turn latch: this is how
the human replaces a mat (section 6.7). Each mat runs from its reel over a fixed guide bar into the
bottom of the wash gate; its hem rod (Ø 8, 1.4016, 400 long) rests in a park fork at the gate mouth, X −350,
Z 1140.

| Mat | Build | Length | Wound Ø | Duty |
|---|---|---|---|---|
| **K** | Skived UHMW-PE film 1.0 mm, food grade, no reinforcement needed (0.7 N/mm tension is 0.1 % strain) [E] | 2.4 m | 70 | Cutting anvil: produce, RTE, cooked meat; raw meat last in the meal |
| **S** | Platinum-cured silicone 60 A on aramid or glass fabric, 0.8–1.0 mm, fabric fully encapsulated | 2.6 m | 72 | Class R and odorous sticky work: mince, Rouladen, Schnitzel, breading |
| **D** | As S | 2.6 m | 72 | Dough, pastry, RTE sticky food, dry goods in SLING, tossing |
| **P** | PTFE-coated glass open mesh, 4 × 4 mm aperture (dryer and dough-belt material [K]) with silicone-bound edges | 2.4 m | 65 | Wash, drain, mangle, steam |
| **R** | 1.4301 foil 0.15 mm with a punched low-profile rasp pattern (teeth 0.3 mm), edges bound in silicone | 1.6 m | 60 | Abrasive peeling in LOOP |

All mats carry **flap lips**: a 45° silicone flap, 8 mm high, vulcanised along both edges. Free, it stands
up and keeps rice, peas, flour and drips on the mat in SLING and seals against the cheeks in LOOP; under
winding it lies flat, so the reel stays cylindrical. The lip also encapsulates the cut edge of the fabric,
which would otherwise wick liquid into the core. The hem is a vulcanised closed pocket around the hem
rod. A sixth cassette position is provided empty (second K for raw meat, or a paper roll, section 6.6).

**Arm B (mat arm).** Shoulder at X 380, Z 1350; two links of 430 mm in the gallery plane Y 0…28; bar B is a
Ø 40 × 3 tube, 470 long, cantilevered into the working zone. Three coaxial shafts pass the wall in one
cartridge (shoulder 150 Nm, elbow 80 Nm through a belt in the sealed upper link, bar spin 20 Nm / 300 rpm
through two belts). The links are welded, sealed stainless boxes with a breather to the dry room through
the hollow shoulder. The bar has a key slot: the hem rod drops in, half a turn wraps the mat over it and
locks it (sail-keder principle); after 1.5 turns capstan friction carries the tension [F]. A UHMW-PE
doctor lip on the forearm touches the mat just after the nose and keeps anything sticky from being wound
in. Bar deflection under the full 300 N mat tension: 0.3 mm at the tip [E: tube I = 6.0·10⁴ mm⁴], which I
take as acceptable for tracking because the flanged rollers E and L and the reel flanges guide the lips.

**Roller arm.** Shaft at X −250, Z 1330, arm 150, 40 Nm (600 N at the roller). The arm ends in two open
PEEK forks; rollers are loose ware dropped in by arm C: smooth Ø 60 (1.4404), and disc-knife rollers
(section 2.4). A spring in the arm gives a soft hold-down mode.

**Blade arm.** Shaft at X −230, Z 1260, arm 170; beam 420 × 60 × 1.2 mm blade on a 10 × 40 back, edge
inclined 8° in Y for a progressive cut; the front end of the beam rides in a slot of the front frame
(a passive guide in Zone S). Opening 150 mm. Drive 120 Nm (1.5 kN at the blade) [E: 300 mm engaged edge ×
2–5 N/mm × 1.5, R4 section 1.1]. Contact with the mat is detected by torque; penetration into mat and soft
anvil is limited to 0.2 mm.

**Gate.** Vertical slot X −372…−330, Z 880…1130, through which the active mat rises. From bottom to top:
detergent spray pair, fresh rinse pair, steam slot (100 mm), squeegee lip pair; a cold pre-rinse bar and a
scraper act on the mat as it enters from above during retraction. One small actuator closes the squeegee
and scraper lips (open when the mat only passes for work). Section 6.2.

**Mat exchange.** Bar B unwinds and lays the hem rod into its park fork (the reel retracts the mat through
the gate: this is the wash). B moves 40 mm to the next fork, takes the next hem, winds half a turn, and
draws the mat out over L and the table. 75–100 s with wash, 15 s without [E].

### 2.2 Station P1 and the hob row

Hob deck: one glass-ceramic sheet at Z 700 with four raised stainless collars. Under each collar an OEM
induction module (DEC-5; P1 and P4 3.5 kW, P2 and P3 2.5 kW) with a Ø 30 centre hole, a load cell frame
(±2 g to 10 kg) and a turntable shaft coming up through the collar. The vessel stands on a **spider**
(three non-magnetic 1.4301 arms, centring pins) 4 mm above the glass; the spider's hub cap overhangs the
collar by 15 mm, so the rotary seal sits in a labyrinth outside Zone F. Spiders lift off and are ware.
P2–P4: 0–60 rpm, 3 Nm. P1: servo, 0–600 rpm, 8 Nm.

**Spindle at P1.** A crank R 300 on a shaft at X 450, Z 1100, with a parallelogram belt that keeps the
head vertical; swinging ±30° about horizontal moves the head 300 mm up and down with 40 mm of X drift.
The spindle is driven by a belt inside the sealed crank from a 600 W motor in the dry room (0–3 000 rpm);
nothing electric is in the wet zone. Tools (ware, bayonet stem with drip collar): balloon whisk Ø 90,
flat beater, bell-guarded blender blade (SM-024), small whisk Ø 40 for the 0.4 L beaker (SM-176).
Because the vessel rotates under an off-centre tool, the motion is planetary (SM-172).

**Stirring (COK-008).** A passive scraper (bent 1.4404 rod, silicone-lipped paddle following floor, corner
and wall) is hung by arm C on a fixed fork at the back wall above each position; the vessel turns under
it at 5–40 rpm (SM-180). Four scrapers in two sizes. Risotto, béchamel and custard are whisked at P1.

**Water** is dosed by a fixed spout with valve and flow meter at each position (PRP-015); a spray bar
above the loop zone and one above the table serve washing of produce and cleaning.

**Dump port.** A stainless funnel mouth 300 × 80 in the partition at X 0, Z 700…780, leading to the
strainer basket over the drain under the table. Arm C pours pot water into it in the −X direction; bar B
drops peel and scraps into it by NOSE. Waste never passes over a vessel (R10).

### 2.3 Vessel arm C

Same module as arm B (shoulder X 700, Z 1250, links 430, layer Y 30…58; 150 / 80 / 40 Nm). Its bar is
80 mm long and ends in a **shoe**: a dovetail slot with two electro-permanent magnets (each 400 N, wires
in the sealed arm). Every vessel, lid, basket, roller, scraper and spindle tool has a ferritic dovetail
**tab** on the side that faces the back wall. The shoe slides onto the tab by a Z move; the magnet holds
it in any attitude; the bar spin tilts or inverts the vessel about Y. Payload 8 kg at 800 mm reach [E:
63 Nm + arm]. The full 9 L pot is never lifted (R7).

What C does: set and remove vessels, lids, baskets, scrapers, rollers, spindle tools; pour (metered by the
load cell of the receiving position); lift a basket and hold it to drain; pan-pair inversion (SM-127: the
tabs of the two pans lie back to back and the shoe takes both); push trays into the oven mouth and hook
them out; hand vessels through the vessel port in the right wall (to washer, ware store, plating).

Arms B and C cannot pass each other (each bar crosses the other's link layer). B works from the left and
above, C from the right and below; the controller keeps exclusion zones. C must be parked right and low
when B delivers to P3 or P4.

### 2.4 Tools, vessels and fixtures

| Item | Dimensions | Qty | Bought / custom |
|---|---|---|---|
| Smooth roller | Ø 60 × 410, 1.4404 | 2 | custom (turned tube) |
| Disc-knife roller, pitch 5 / 10 / 20 | discs Ø 110 × 0.8 on a Ø 30 arbor with spacers and a fixed stripper comb | 1 each | discs bought (slitter knives), arbor custom |
| Blade beam | 420 × 60 × 1.2 | 1 + spare edge | blade stock bought, beam custom |
| Scraper for wall peg | two sizes | 4 | custom (bent rod, moulded lip) |
| Spindle tools | whisk 90, whisk 40, beater, blender bell | 1 each | bought heads on custom stems |
| Pots with tab | 1.5 L, 2.5 L, 4 L (2), 6 L braiser GN-shaped 325 × 265 × 110, 9 L | 6 | bought induction pots, tab welded on |
| Pans with tab and common rim | 28 cm (2), GN 2/3 frying pan pair 354 × 325 × 40 (2) | 4 | bought, tab added; the GN pair needs a matched rim |
| Mixing bowl 8 L with lift-out basket; beaker 0.4 L | Ø 280 × 180; Ø 90 × 90 | 1 + 1, 1 | bought, tab added |
| Pasta basket for the 9 L pot | Ø 240 × 180 | 1 | bought |
| Lids | for each pot | 5 | bought, tab added |
| Dosing cups with tab | 50 mL, 250 mL, 1 L | 2 each | bought |
| Rouladen cradle insert for the braiser (SM-084) | comb rack, 8 channels | 1 | custom (bent sheet) |
| Tins and trays | tray 400 × 300, loaf tin 300, springform 26 cm with push-up base, gratin dish 300 × 200 × 60, turn plate Ø 280 | 1–2 each | bought, tab added |
| Spiders | Ø 280 | 5 | custom (laser cut, welded) |

36 loose ware items of 22 types [E], of which 8–14 are used in a meal.

### 2.5 Wall penetrations and seals

| Penetration | Seal | Zone on the wet side |
|---|---|---|
| 5 cassette reel shafts Ø 20 | PTFE-lip shaft seal in a flushed cartridge | S (below the table, spray zone) |
| Arm B cartridge Ø 90 (3 coaxial shafts; inner gaps are on the dry side) | one hygienic lip seal Ø 90, flushed by the gallery spray | S |
| Arm C cartridge Ø 90 | same | S |
| Arm B and C elbows (2), bar joints (2) | lip seals Ø 50 / Ø 40 on the arm, product side exposed and sprayed | S; the B bar joint is 40 mm from the mat edge — **closest dynamic seal to Zone F** |
| Roller arm Ø 25, blade arm Ø 30, gate actuator Ø 12, spindle crank Ø 60 (2 coaxial) | lip seals | S (gallery) |
| Spindle nose | lip seal under a drip collar, above the vessel | **F-adjacent**: the one seal directly over food; an LRU (HYG-016) |
| 4 turntable shafts through the deck | lip seal inside a raised collar under the spider hub cap | S, labyrinth |
| Dock tilt and lid shafts (2) through the left wall | lip seals | S, dry corner |

No linear slot, bellows or guide crosses a wall (SM-227). 17 rotary passages in walls and deck and 5 on
the arms [E]. HYG-004: nothing of Zone N is above open food except the two arm forearms when they reach
over a vessel; they are closed welded boxes and count as Zone S.

### 2.6 The missing yaw, and what replaces it

| Need | Replacement | Confidence |
|---|---|---|
| Long items lengthwise under the blade (trim ends, coins) | **Pour direction sets orientation**: the dock tilts the box about a Y axis, so carrots, leeks, cucumbers and meat slices stored lengthwise in a GN 1/3 box slide out along X and stay so as long as they are not tumbled | M |
| A cut across Y | **Disc-knife roller**: cuts planes perpendicular to Y at a fixed pitch (5, 10, 20 mm). After LOOP work, cylinders lie along Y, and the disc roller cross-cuts them | M |
| Turn a flat item by 90° (a meat slice that must be rolled from its narrow end) | **Turn plate on P1**: NOSE the item onto the plate, turntable 90°, arm C tilts the plate and slides the item back onto the SLING | M–L, 40 s per item |
| Distribute over a round pan or a rectangular dish | Turntable under the nose; nose travels in X | H |
| Stir | Turntable under a fixed scraper | H |

---

## 3. Ingredient intake and dosing

**Dock.** The storage box arrives at the box port in the left wall (X −380, Z 1400…1650), the driest corner
of the cell, 450 mm above the table and 800 mm from the nearest hob (R8). The dock grips the box, removes
the lid (one lid actuator), tilts it 0–135° about a Y axis at its pour edge (X −280) and vibrates it
(SM-133). Loss-in-weight on the dock's load cell (10 kg ± 1 g); seasoning on a second cell (300 g ±
0.05 g) under the cup position (R9).

Two targets exist under the pour edge: **the mat** on the table (solids, which then travel by SLING and
NOSE to any vessel) and **a cup** standing on a small bracket at X −200, Z 1260, which arm C fetches
(liquids, seasoning, pastes). The mat is thus the only conveyor for solids and the cup the only conveyor
for liquids. Water does not travel at all (spout at each position).

| Form | From the box | Onward | Confidence | Untested |
|---|---|---|---|---|
| Whole produce | Pulse-tilt over the pour edge onto mat K or P; count by load-cell steps and camera 1 (SM-150); long goods slide out lengthwise | SHUTTLE to tools, SLING to vessel | M | rolling of round items on the table slope; resolution is one piece |
| Leafy | Whole box emptied onto mat P or K (SM-153); a head of lettuce is cut on K first | NOSE into the basket at P1 | M | dosing part of a box (±10 g at best) |
| Granular (rice, lentils, sugar, IQF peas) | Tilt and vibrate onto mat D in a ribbon; the flap lips hold it | SLING + NOSE into the pot. 300 g of rice is a 300 × 200 mm patch | M–H | grains under the flap lip; residue on silicone (expected < 0.3 % [R4]) |
| Powder (flour, starch, cocoa) | Mesh-valve lid (SM-135), vibrated, onto mat D or into the cup | as granular; drop height at the nose ≤ 60 mm to limit dust | M | flour at 60–70 % RH; dust on the cheeks |
| Seasoning 0.2–5 g | Sifter lid into the 50 mL cup on the fine cell (SM-141); salt as brine (SM-143) into the cup | arm C tips the cup into the vessel; chase with 10 mL of recipe water where the recipe has water | H | — |
| Liquid (milk, oil, wine, vinegar, stock, cream) | Tilt-pour through a spout lid into a cup on the load cell, or from the opened carton held in a carrier box | arm C pours into the vessel | M–H | drip after pouring; oil film in the cup (1–3 % [R4], chased or accepted) |
| Viscous paste (mustard, tomato paste, honey, quark) | Stored in the box as delivered or as frozen pucks made at ingestion (SM-147, request X6). From a jar: tilt-and-scrape is **not solved here**; K4 has no piston. Default: puck or a spout-lid squeeze pouch in a nip | puck onto the mat or into the cup | **L–M** | the weakest dosing form of K4; see open issue 4 |
| Solid fat | Block pushed over the pour edge, cut by CHOP by length on mat K (SM-148) | NOSE into pan or bowl | H | — |
| Raw meat, pieces and mince | Tilt-slide out of the box or opened tray onto mat S (mince, cutlets) or K (pieces to cut) | SHUTTLE / NOSE | M | mince sticking in the tray corner (3–8 % [R4]) |
| Raw meat slices in a stack | Default: cut from a block on K (SM-100), one slice at a time. Bought stack: shingled by ENVELOPE shear (top layer moved against the bottom layer) | — | L for the bought stack | G9 of the catalogue remains open here |
| Egg | Egg module at the dock level (common front end: SM-164 with SM-168), contents into the inspection cup | arm C tips the cup into bowl or pan | M | as for all candidates |
| Frozen | IQF as granular. Blocks (spinach) into the pot as pieces | — | H | — |
| Long goods (spaghetti) | Box tilted with the strands along Y over the mat; by mass on the dock cell | NOSE into the basket of the 9 L pot | M | ±15 g; strands bridging the lips |
| Stowed sealed packs (can, jar, carton, tub, vacuum pack) | Opened by the package-opening mechanism of the ingestion/transport side (DEC-3); K4 receives them open in a carrier box that the dock tilts like a box. A vacuum pack cut open on three sides is emptied onto the mat | as liquid, paste or meat | M | viscous content of cans (tomato: 3–10 % residue without a rinse; the recipe water is poured through the can where the recipe has water) |

Requests resulting from this table are collected in section 12.

---

## 4. Operation table

Times for 4 persons unless stated. "Mat" names the cassette.

### 4.1 MEAL-018 operations (no purchase workaround, shaping cluster)

| Operation | Mechanism and sequence | Time [E] | Conf. | Untested |
|---|---|---|---|---|
| Flip pieces (FLP) | Pan-pair inversion by arm C (SM-127): second pan preheated on the neighbouring position, set on, both tabs in the shoe, 180°, upper pan off | 25 s | M–H | hot fat > 30 mL; 5 kg pair on the magnet |
| Flip whole-pan items | Same. Thin pancakes: "ping-pong" between two pans, each flip changes pan | 20 s | M | pancake sticking to the first pan |
| Assemble layered dishes (LAY, TOP, SPR) | Dish on P1. Sheets and solid layers by NOSE with the nose travelling in X; sauces poured by arm C from the pot in a ribbon while the dish oscillates ±10°; cheese and crumbs as a ribbon from mat D by NOSE | 5–8 min for lasagne | M | evenness ±20 % of poured sauce; tiling of dry sheets |
| Assemble open-hand food (burger, sandwich, wrap) | Bread or bun halves in a row on mat D, toppings by NOSE row on row from a second pass of the same mat is impossible (one mat at a time) — toppings are sliced on K first, parked in cups or on a tray, and laid by pouring. Patty slid from the pan by arm C | — | **L** | G3 stays a gap; K4 builds wraps and rolled items well, stacks badly |
| Carve a boneless roast (CAR) | Roast by NOSE-in-reverse is impossible (nothing picks up a roast): arm C tilts the braiser/tray and slides the roast onto mat K at the table. Roller as hold-down, CHOP 2–15 mm, slices stay shingled; NOSE onto a warm tray | 2 min | M–H | sliding a 2 kg roast out of a vessel onto the SLING; soft braised meat under the blade |
| Carve bone-in poultry | Not solved. Served as parts (SM-244) | — | — | G5 |
| Unmould (UNM) | Arm C inverts the tin onto a tray (tabs back to back as for pans); springform with push-up base; puddings in beakers inverted onto the plate carrier | 30 s | M | sticking (as for a human); greasing quality |
| Score (SCO) | CHOP to a depth stop on K or D, mat jogs; only cuts parallel to Y. Diamond pattern is not possible; parallel slashes are | 20 s | H (parallel) | — |
| Stuff rigid cavities (STU) | No nozzle, no piston. Peppers and tomatoes are halved by CHOP into "boats", filling dropped in by NOSE from a log cut into portions | 3 min | M, **adapted** | whole-pepper-with-lid form is lost; cannelloni become rolled sheets |
| Stuff flat pockets, dumpling cores | Flat pocket = fold in ENVELOPE (mat folds the cutlet over the filling). Dumpling core: dough disc, core placed by NOSE, closed by rolling in a small LOOP | — | L | G4 |
| Wrap (WRP): cabbage roll, burrito, bacon wrap, biscuit roll, strudel | Small LOOP as roll loop (SM-079): item and filling sag into the loop between E and bar B, B closes to the loop circumference, both reels run the same way. Biscuit roll and strudel are rolled in the mat they were spread on (the cloth method) | 30–40 s each | M–H | start of the first turn; filling squeezed out at the ends (the cheeks limit it) |
| Separate cabbage leaves (LSP) | Not solved | — | — | G7 |
| Hand-form small pieces (FRM) | Strand rolled in the LOOP or under ENVELOPE with the roller moving to and fro (a palm), cut by CHOP; tapered Schupfnudeln by a short palm stroke per piece row | 3–4 min | M–H | taper |
| Form patties and dumplings (FRB, FRK) | Mass rolled to a Ø 60 log in the LOOP on S, CHOP into 30 mm pucks (100 g ± 8 %), NOSE into the pan one row at a time, pressed flat by the first pan-pair contact. Balls: pucks tumbled 10 s in the LOOP | 12 patties 3 min | M–H | log diameter control by loop length; ends of the log |
| Roll Rouladen (RLT) | Section 5, B1 | 6 rolls 7 min | M | see B1 |
| Secure Rouladen | Seam-down in the cradle insert (SM-084), seared seam first. Pins (SM-085) are not available: no press axis with a pin magazine | — | M | the two-hour braise test that every candidate needs |
| Bread (BRD) | On S: cutlet flattened in ENVELOPE; flour ribbon (8 g), ENVELOPE press both sides; egg from the cup poured by C in a ribbon over the row, LOOP two turns; crumbs 50 g, LOOP three turns, ENVELOPE press at thickness + 1 mm; NOSE into the pan (SM-095) | 70–90 s per cutlet, 2 at a time | M | coverage ≥ 95 %; egg running under the lips; crumb film left on the mat |
| Roll out dough (ROL) | On D: SHUTTLE under the smooth roller at falling gap, 6–10 passes; sticky dough in ENVELOPE; thickness ±0.5 mm; NOSE onto tray | 2 min | H | — |
| Shape dough (SHD) | Pizza: sheet, NOSE on tray. Loaf: roll up in LOOP, NOSE into tin. Rolls: log, CHOP, round in LOOP | 2–4 min | H / M (rounding) | — |
| Line a tin with a dough sheet | NOSE lays the sheet over the tin; it sags in; rim trimmed only along Y. No presser | — | L | tart and quiche cases; press-in crumb crusts work (ENVELOPE is not available in a tin) |
| Knead dough, mix mince mass (KND, KNM) | LOOP fold and NIP (SM-174) on D or S: the lump is folded in the loop, drawn back onto the table under the roller at 15 mm (in ENVELOPE if sticky), 40–60 cycles | 1.6 kg dough 5 min; 1 kg mince 2 min | M | the central unknown after mat release |

### 4.2 Peeling, trimming, cutting, egg

| Operation | Mechanism | Time | Conf. | Untested |
|---|---|---|---|---|
| Wash produce | On P in the LOOP under the spray bar, water falls through to the dump side (P1 must hold the waste bowl or be empty); or in the basket at P1 | 60 s | H | — |
| Wash and dry leaves | Basket in the bowl on P1: fill from the spout, slow reversing turns, arm C lifts the basket, dumps the water, spin 40 s at 500 rpm (SM-213) | 3 min | H | — |
| Peel potato, smooth roots (PLP) | LOOP on rasp mat R under spray, 0.4 m/s relative speed; default for mash and fried potatoes is skin-on cooking and slipping the skin in the LOOP on P (SM-055) | 1.5 kg in 5–6 min | M | loss (PRP-022: 25 %), eyes, wear of the cheeks by the rasp |
| Peel carrot, cucumber | As potato on R, after cutting to ≤ 120 mm lengths. Cucumber: not peeled (or striped by R, short) | 3 min | M–L | soft cucumber on a rasp |
| Peel onion | Bought peeled (SM-242). Own attempt: top, tail, slit by CHOP; rub in LOOP on R at low speed with spray (SM-061) | — | L | G1 |
| Core, deseed | Pepper: halved by CHOP, seeds flushed out in the LOOP on P under the spray (4 mm mesh passes seeds). Apple: bought cored or cut in eighths and the core strip accepted: not solved | 2 min | M / — | G6 |
| Trim ends (TRE) | Long goods as poured (X-aligned), camera 1 finds the ends, CHOP | 5 s per item row | M–H | beans and sprouts in quantity: only if they arrive lengthwise; otherwise bought trimmed |
| Dice 5 / 10 / 20 mm (DIC) | **Slab–strip–chop** on K: (1) CHOP slabs of thickness p with the roller as hold-down; (2) level to one layer under the smooth roller at gap 1.3 p; (3) roller swapped by C for the disc roller of pitch p, one SHUTTLE pass cuts strips along X; (4) CHOP at pitch p. Other sizes in X and Z are free; the Y pitch is 5, 10 or 20 | 1 kg in 2–3 min | M | step 2 (slabs lying flat in one layer); ≥ 90 % within tolerance (PRP-021) |
| Slice (SLI) | X-aligned items: CHOP at 1–30 mm. Y-aligned cylinders: disc roller (5, 10 mm) | 1 kg in 1 min | H / M | thin slices of soft tomato |
| Sticks, fries (JUL) | Potatoes rolled to lie along Y, CHOP 10 mm planks, planks fall flat, CHOP again at 10 mm: sticks of the potato's full length | 1.2 kg in 2 min | M–H | planks falling flat |
| Mince fine, chop herbs (MIN, CHH) | CHOP 3 strokes/s with ±12 mm mat jog, LOOP regather once, repeat | 40 s | H | blade landing life (R3) |
| Grate (GRC, GRF), zest | Block held under the smooth roller on rasp mat R in SHUTTLE; gratings stay on R and are carried by NOSE. Hard cheese bought grated by default (MEAL-012) | 1 min | M–L | block slipping under the roller; zest not solved |
| Juice citrus | Halved by CHOP, pressed in a fold of mat P through the NIP over a cup (mangle, SM-161) | 40 s | M | pips pass a 4 mm mesh: strained at the cup |
| Crack, separate eggs | Common egg module | 12 in 3 min | M | — |

### 4.3 Everyday operations

| Operation | Mechanism | Conf. | Untested |
|---|---|---|---|
| Mash (MSH) | Potatoes are rasp-peeled (R) before boiling or slipped in the LOOP on P after it, returned to the pot on P1 and mashed by the flat beater with the pot turning; milk and butter from cups. The mangle ricer of F (SM-161) is **not used**: it needs the mesh and a receiving mat at the same time, and only one mat can be threaded | M | lumps > 5 mm; gluey if over-beaten |
| Whip, emulsify, cream | Spindle at P1, bowl or 0.4 L beaker turning slowly | H | one egg white in the beaker |
| Fold gently (FLD) | Flat beater at 30 rpm with the bowl at 10 rpm | M | volume loss |
| Purée hot (PUR) | Blender bell in the pot at P1 | H | splash guard lid with a slot |
| Toss salad (TOS) | In the bowl at P1 turning under the wall-peg scraper, dressing poured by C; or LOOP on D | H | — |
| Drain pasta, potatoes (DRN) | Lift-out basket by arm C (SM-155), 20 s drip; water dumped later through the dump port when cooled or in a pot ≤ 4 L | H | — |
| Squeeze (SQZ) | Fold of mat P through the NIP over the table, liquid runs off the table slope to the gutter; the pressed cake stays in the fold | M | grated-potato mass |
| Transfer mat → vessel | NOSE; residue on silicone expected ≤ 2 % for dough and mince [E, unmeasured], doctor lip returns film | M | R1 |
| Transfer vessel → vessel | Arm C pours; pastes need a scraper: the wall-peg scraper held in the tilted, turning vessel is not possible (turntable is not under a tilted vessel). Thick masses are therefore made in the vessel they are cooked or baked in, or on the mat | M | cake batter from bowl to tin: 5–15 % residue without scraping [R4] — **misses PRP-013 (8 %) unless the bowl is chased** |
| Stir and scrape while cooking | Turntable under wall-peg scraper, all four positions at once | H | scraper following a 36 cm pan edge |
| Flatten meat (POU) | ENVELOPE on S, smooth roller in passes to 4–10 mm | H | — |
| Thin batter poured and spread (PTH) | Arm C pours from the bowl by weight on the receiving load cell; turntable spin-coat at 90 rpm (SM-097) | M | ±10 % by pouring from an 8 L bowl; a 1 L jug with a lip is used instead |
| Grease a tin (LIN) | Release spray from one fixed mist nozzle at P1 while the tin turns on the turntable. (Melting butter in the tin and rolling it with arm C coats only the four faces around Y, not the two end faces: rejected) | M | coverage of corners and of a Gugelhupf tube |
| Baste, glaze | Arm C tilts the roasting tray so the juices run over the roast; glaze poured from a cup | L–M | no brush |
| Proof (PRP-037) | Dough in the bowl or on the tray in the oven at 32 °C with steam | H | — |
| Hold cold (PRP-036) | In a lidded vessel handed out through the vessel port to cold storage | — | request to the architect |

---

## 5. Benchmark walk-throughs

Conventions: t = minutes from order. "Moves" = handling moves of arm C plus mat exchanges plus box
dockings (the things that can fail), not mat strokes. "Soiled" lists what must be cleaned afterwards;
the fixed parts of the mat line (table, cheeks, blade, E, L, bar B) are soiled in every meal and not
repeated. All times [E]. T_lim is the PERF-001 limit (1.15 × T_ref + 10).

### B1 Rinderrouladen, Rotkohl, Salzkartoffeln (4 persons) — **yes**, 170 min (T_lim 183)

| t | Step | Where |
|---|---|---|
| 0 | C sets braiser with cradle on P4, 4 L pot on P3, 2.5 L pot on P2. Red cabbage half docked onto K: CHOP out the core wedge (two oblique-free cuts: the stalk end is cut off as a 40 mm slab, accepted loss 10 %), CHOP 2 mm shreds, SLING + NOSE into P3 with fat; apple eighths and peeled onion diced (slab–strip–chop, 10 mm), into P3; vinegar, wine, sugar, spices by cups | K; P3 |
| 12 | Onion for the filling diced 5 mm, gherkins CHOP into spears (as poured, lengthwise: CHOP cannot cut along X; spears are quartered gherkins bought, or slices are used: **adapted detail**), bacon block CHOP 3 mm slices; all parked in three cups by NOSE | K; 3 cups |
| 18 | K retracted (washed). Beef block (tempered 30 min in the freezer airlock, request X7) on K?? K is in the wash: the block was sliced **before** the vegetables would breach "raw last". Resolution: Rouladen slices are bought cut (MEAL-012 a) and stored lengthwise; stack of 4 docked onto S, shingled by ENVELOPE shear; camera checks four separate slices | S |
| 22 | Each slice: ENVELOPE flatten to 5 mm; mustard ribbon from the cup (C pours along Y while the mat jogs), spread by the smooth roller at 1 mm gap through a fold of the mat; bacon, gherkin, onion poured from the cups as a ribbon at the leading edge; small LOOP of 160 mm rolls it; loop opened, camera finds the seam, roll turned seam-leading; NOSE drops it seam-down into a cradle channel in the hot braiser | S; P4 |
| 34 | Four (or eight) rolls seared seam-down 3 min; C sets the second GN pan on, inverts, cradle keeps the rolls; 3 min; back. Deglaze with wine and stock from cups, tomato paste puck, lid on. P4 at 95 °C for 100 min, turntable 2 rpm | P4 |
| 40 | S retracted with steam. Potatoes docked onto R: LOOP rasp peel 5 min under spray; R retracted; potatoes on K: CHOP halves; NOSE into P2 with basket; water at t 125, boil 22 min | R, K; P2 |
| 150 | C lifts the potato basket, drains, sets it in the warm 4 L pot. C lifts the cradle with the rolls onto a warm tray; sauce at P4 thickened with a starch slurry from a cup under the scraper; C moves the braiser to P1 only if blending is wanted | — |
| 165 | Hand-over of tray, P3 pot, potato pot and sauce (poured by C into a jug) through the vessel port | — |

Vessels: braiser + cradle + GN pan, two pots, basket, lids, 5 cups, tray, jug (13). Mats: K, S, R, K.
Moves: 46. Soiled: K, S, R, smooth roller, disc roller 10 and 5, blade, all listed vessels.
Weak points: the seam (SM-084), shingling a bought stack (L), gherkin spears (no lengthwise cut).
Without shingling, the fallback is own slicing from a block at the very start of the meal on K, with K
steam-disinfected... K cannot be steamed (UHMW-PE softens): it is disinfected by an 85 °C rinse hold of
60 s, which the gate can do with the mat stopped in three steps. This costs 4 min.

### B2 Wiener Schnitzel, Bratkartoffeln, Gurkensalat (4 persons) — **yes** (Bratkartoffeln from potatoes boiled the same hour: slightly adapted), 62 min (T_lim 45 for the Schnitzel row alone; the menu T_ref is driven by the potatoes, 50 min + cooling) 

| t | Step |
|---|---|
| 0 | Potatoes (skin-on) docked onto P, washed in LOOP, NOSE into P3 pot with basket, boil 22 min |
| 4 | P retracted. Cucumbers docked lengthwise onto K: CHOP 2 mm slices (2 cucumbers, 70 s), dill CHOP fine; NOSE into the bowl on P1; dressing (vinegar, oil, sugar, brine, sour cream) from cups, tossed under the scraper; C moves the bowl out through the vessel port to cold storage |
| 12 | Onion dice on K for the potatoes; parked in a cup. K retracted |
| 28 | Potatoes: C lifts basket, NOSE is not possible from a basket: C tips the basket onto mat P at the table; LOOP on P rubs the skins off (SM-055/S12), skins through the mesh to the waste bowl on P1; P retracted; potatoes on K, CHOP 5 mm slices; NOSE into the 36 cm GN pan on P4 with fat and onion; turntable + scraper as a plough, 15 min |
| 36 | Cutlets docked onto S; ENVELOPE to 5 mm; breaded two at a time (4.1); NOSE into the 28 cm pan on P2 (80 mL fat); 3 min; C pours the fat into the second pan through the rim gap, pan-pair flip; 3 min; C slides them onto a tray in the oven at 70 °C. Second pair likewise |
| 58 | Lemon CHOP wedges on K (K drawn out again, RTE after the potatoes — allowed; K never saw raw meat in this meal) |

Vessels 9. Mats P, K, P, K, S, K. Moves 52. Weak points: six mat exchanges (8 min of gate time, mostly
parallel to cooking); crust loss in the pan-pair flip with 80 mL of fat (catalogue TEST); egg wash
running under the flap lips; Schnitzel larger than 200 × 150 do not fit a 28 cm pan two at a time.

### B3 Frikadellen, Kartoffelpüree, Erbsen-Möhren (4 persons) — **yes**, 48 min (T_lim 50)

| t | Step |
|---|---|
| 0 | Potatoes on R, rasp peel 5 min; on K: CHOP halves; NOSE into P3 pot; boil 20 min |
| 9 | Carrots docked lengthwise on K: CHOP ends, CHOP 100 mm lengths; (not peeled: scrubbed on R for 60 s before, same session) dice 10 mm; NOSE into P2 pot; onion dice 5 mm into a cup; parsley CHOP into a cup. K retracted |
| 16 | Roll soaked in milk in the beaker at P1 (beater, 30 s); egg into it from the egg cup. Mince docked onto S; onion, parsley, mustard puck, brine, and the soaked-roll mix poured by C over the mince; ENVELOPE closes it (liquid is held in the fold); LOOP fold and NIP, 30 cycles, 90 s; log Ø 60 in LOOP; CHOP 8 pucks; NOSE, two rows of four, into the GN pan on P4 (170 °C) |
| 24 | Pan-pair flip after 5 min (presses the pucks to shape); 5 min; S retracted with steam |
| 30 | Peas (IQF) on D by SLING into P2; butter. Potatoes: C drains (basket), tips them back into the pot on P1; flat beater 60 s with hot milk and butter from cups; nutmeg from the seasoning cup |
| 44 | Hand-over |

Vessels 8, mats R, K, S, D; moves 38. PRP-023 (12 patties in ≤ 5 min): met on paper (3–4 min).
Weak point: the wet mince mass in ENVELOPE and LOOP is exactly the release experiment R1.

### B4 Spaghetti Bolognese with grated cheese (4 persons) — **yes**, 78 min (T_lim 96)

t 0: 9 L pot with basket on P4, 4.5 L water from the spout, heat (16 min). Onion, carrot, celeriac
(bought peeled or rasped on R) diced 5 mm on K; garlic CHOP fine; SLING + NOSE into the 4 L pot on P3
with oil, sweat under the scraper. t 10: K retracted; mince docked onto S and NOSEd straight into P3
(S is used as a conveyor only, 40 s), seared with the scraper breaking it up; wine from a cup; canned
tomatoes poured by C from the opened can in its carrier, chased with the stock; paste puck; simmer 50 min
at 2 rpm. t 58: spaghetti docked onto D (strands along Y), NOSE into the basket; 10 min. t 70: C lifts the
basket, drips 20 s, tips the pasta into a warm bowl... tipping a basket of long pasta is a known weak
step for every candidate; here it is a pour about Y into the GN braiser. Grated cheese (bought grated)
into a cup. Vessels 6, mats K, S, D; moves 30. Weak point: none specific to K4; mat S soiled for one
transfer — a disposable paper leaf would do (section 6.6).

### B5 Pizza with yeast dough from flour (2 trays) — **yes**, 95 min incl. 60 min proof (T_ref 90, T_lim 113)

t 0: bowl on P1; 320 mL water at 30 °C, yeast, brine, oil from cups; flour (500 g) from the dock onto D,
NOSE into the bowl in three portions while the beater turns (shaggy mass, 90 s). C tips the bowl onto D at
the table (the mass leaves the bowl as a lump; 3–5 % stays, flushed later: **PRP-013 for dough is
borderline here**). LOOP fold and NIP in ENVELOPE, 50 cycles, 5 min. NOSE back into the oiled bowl; C
carries it to the oven (32 °C, steam), 60 min. t 70: C tips the dough onto D; CHOP in two; each half sheeted
by SHUTTLE to 4 mm, 380 × 290, 8 passes; NOSE onto the tray held by C at the table edge height. Tomato
sauce (canned, seasoned in a 1.5 L pot at P2) poured by C in three ribbons, spread by the tray's own
tilt?? — no: spread with the smooth roller? no, the tray is not on the table. **Spread by the wall-peg
scraper held still while C moves the tray under it in X** (the tray is the moving part). Mozzarella CHOP
10 mm dice on K, salami CHOP 2 mm, NOSE as a ribbon while C moves the tray in X under the nose; C pushes
the tray into the oven (250 °C, 10 min). Second tray likewise. Vessels 5, mats D, K; moves 34.
This is the concept's home ground: kneading, sheeting and transfer of a tray-size sheet are all H if the
mat releases the dough.

### B6 Gemüseeintopf from whole vegetables (6 persons) — **yes** (green beans bought trimmed: permitted purchase), 50 min (T_lim 60 for 6)

t 0: 6 L pot on P4. Potatoes and celeriac half on R: rasp peel 6 min (the celeriac is cut into 40 mm slabs
first so the knobbly skin is reachable: loss 25–30 %). Carrots, parsnip scrubbed on R in the same run.
Leek docked lengthwise on K: CHOP root and dark green, CHOP 5 mm rings, washed in the basket at P1
(grit between layers, FSF-042), spun. t 9: all on K in three batches: slab–strip–chop 10 mm, 2.4 kg in
7 min (PRP-023: 1 kg in ≤ 6 min — met with margin on paper); each batch by SLING + NOSE into P4 with
oil; stock 2.5 L from the spout and a stock cup; tomato CHOP eighths; beans and frozen peas by D at t 30.
Simmer 25 min, scraper 3 rpm. Parsley CHOP. Vessels 3 + basket, mats R, K, D; moves 22. Weak point: three
roller swaps per batch (smooth ↔ disc 10), 20 s each.

### B7 Steak, oven fries, mixed salad with vinaigrette (2 persons) — **yes** (fries are the X-01 adapted method for every candidate), 45 min (T_lim 79 with baked potato)

t 0: potatoes on R (peel 3 min), onto K so that they lie along Y, CHOP 10 mm planks, planks fall flat,
CHOP 10 mm sticks (70 s); NOSE into the bowl with 10 mL oil and brine, tossed under the scraper 20 s; C
tips them onto the tray, shakes it level in X, into the oven at 220 °C, 25 min; C pulls the tray at 12 min
and shakes it. t 8: lettuce head on K, CHOP 40 mm strips both… only across X; the head is cut into 40 mm
slices, which fall apart into strips: accepted. Tomato wedges, cucumber slices, carrot (disc roller 5 mm
after rasp), pepper halves deseeded on P. Leaves washed and spun at P1 (3 min). Vinaigrette in the beaker
with the small whisk (oil, vinegar, mustard puck, brine). Toss in the bowl at serving. t 30: steaks docked
onto S, NOSE into the 28 cm pan at 240 °C on P2 (seasoned by brine mist from the cup? — salt from the
seasoning cup tipped by C, uneven: M); 2.5 min; pan-pair flip; 2.5 min; core probe is **not available to
K4** (no tool that can insert a probe; doneness by time, thickness from camera and pan temperature:
COK-013 not met for steak — open issue 6). Rest on the warm tray 5 min. Vessels 7, mats R, K, P, S;
moves 40.

### B8 Pfannkuchen (8 pieces) — **yes**, 42 min incl. 20 min rest (T_lim 50)

Bowl on P1: milk 500 mL from a 1 L cup, 3 eggs from the egg cup, brine; whisk 150 rpm; flour 250 g from D
by NOSE in a slow ribbon while whisking (lumps: M); rest 20 min. C pours the batter into the 1 L jug.
Pans 28 cm on P2 and P3 at 190 °C, 3 g butter each (CHOP pat, carried on D). Per pancake: C pours 100 mL by
the P2 load cell (±10 mL), turntable 90 rpm for 3 s (spin-coat), 90 s; C sets pan 2 on, inverts, lifts the
first pan off; 70 s in pan 2 on P3; C slides the pancake onto the plate stack tray; meanwhile pan 1 has
batter again. Cycle 2 min, 8 pieces in 17 min. Vessels 5, mat D once; moves 8 + 8 × 5 = 48. Weak point:
the thin pancake sticking to pan 1 at inversion; jug drip.

### B9 Chicken curry with rice (4 persons) — **yes**, 40 min without marinating (T_ref 50 with; T_lim 68)

Rice 280 g docked onto D, SLING into the 2.5 L pot on P2, rinsed in the pot (fill, turn, C pours off
through the lid gap into the dump port), 560 mL water, brine, lid, absorption 15 min. Onion dice, garlic
and ginger fine CHOP on K (ginger peeled on R or bought as paste puck); into the 4 L pot on P3 with oil
under the scraper. K stays out: chicken thigh fillets docked onto K **last** (raw last, R11): ENVELOPE is
not needed; slab 20 mm, disc roller 20, CHOP 20: cubes in 60 s — the step a push grid does badly.
NOSE into P3; K retracted with the 85 °C hold. Curry spice from the seasoning cup, canned tomatoes,
coconut milk or cream from cups; simmer 15 min. Optional blending of the sauce before the chicken goes
in: C moves the pot to P1, blender bell 40 s. Vessels 5, mats D, K; moves 26.

### B10 Lasagne with béchamel from scratch (4–6 persons) — **yes, quality M**, 125 min (T_lim 148)

Bolognese as B4 on P3 (45 min). Béchamel: 1.5 L pot on P1; butter pat, flour 50 g from the cup, whisked
2 min at 110 °C; milk 600 mL from the jug in three pours under the whisk at 300 rpm with the pot at 20 rpm;
nutmeg; 8 min (this is the operation the turntable-plus-spindle station was designed for: H). C moves
the béchamel pot to P2 (hold 70 °C), sets the gratin dish on P1. Layers, four times: C pours Bolognese
(220 g by the P1 load cell) in a ribbon along X, dish oscillates; dry sheets docked onto D (they slide
out lengthwise, three abreast is not controllable — camera 1 counts and measures the row), NOSE lays a row
of sheets while the nose travels; C pours béchamel; grated cheese ribbon from D on top. 8 min. C carries
the dish into the oven: 190 °C, 40 min, rest 15. Vessels 6, mats K, S, D; moves 44. Weak points: sheets
overlapping or lying skew (broken sheets and gaps are filled by the sauce; a cook would tile them);
sauce layer evenness ±20 % is a claim.

### B11 Rührkuchen in a tin, unmoulded — **yes** (unmoulding is the catalogue TEST), 105 min (T_ref 100, T_lim 125)

Loaf tin on P1, release spray while turning; C sets it aside. Bowl on P1: butter 250 g (CHOP slices from
the block on K, softened 60 s at 30 °C on the hob), sugar 200 g from D, flat beater 400 rpm 4 min (CRM);
4 eggs one at a time from the egg cup; flour 300 g with baking powder (both onto D as one ribbon: that is
the sifting and dry mixing, LOOP two turns) NOSEd in at 60 rpm; milk from a cup. C pours the batter into
the tin: about 10 % stays in the bowl; C holds the bowl inverted over the tin for 20 s and taps it against
the wall peg (residue then about 5 % [E]) — **this is where a scraper hand is missed**. Oven 175 °C,
60 min; doneness by time and oven core probe if the oven has one that a machine can place (it cannot).
Cool 15 min; C sets a tray on the tin, inverts, lifts the tin. Vessels 4, mats K, D; moves 22.

### B12 Scrambled eggs from shell eggs, toast, 1 person — **yes**, 9 min (T_lim 17)

t 0: 28 cm pan on P2 at 110 °C is too large for 2 eggs: the 1.5 L pot is used as a small pan (Ø 160).
Butter pat from the block (K drawn out: 15 s; CHOP one slice; NOSE). Two eggs cracked into the
inspection cup, milk 20 mL and brine added to the cup from the dock, C swirls the cup (no whisking
station needed for two eggs; streaky scramble) or tips it into the beaker at P1 for 10 s of whisk. C pours
into the pot; turntable 20 rpm under the small scraper, 2.5 min. Two slices of bought sliced bread
docked onto K, NOSE onto the tray, oven top heat 3 min (oven preheat decides the 9 min; a dry pan with a
pan-pair flip is the alternative). Chives CHOP on K. Vessels 3 + cups, mat K; moves 12. The minimum
quantity is not a problem for the mat (it has no minimum fill); it is one for the 28 cm pan.

### Summary

| | Result | Elapsed / limit (min) | Moves | Mats used |
|---|---|---|---|---|
| B1 Rouladen menu | yes (M: seam, shingling) | 170 / 183 | 46 | K S R K |
| B2 Schnitzel menu | yes | 62 / — | 52 | P K P K S K |
| B3 Frikadellen menu | yes | 48 / 50 | 38 | R K S D |
| B4 Bolognese | yes | 78 / 96 | 30 | K S D |
| B5 Pizza | yes | 95 / 113 | 34 | D K |
| B6 Eintopf (6) | yes | 50 / 60 | 22 | R K D |
| B7 Steak menu | yes; no core probe | 45 / 79 | 40 | R K P S |
| B8 Pfannkuchen | yes | 42 / 50 | 48 | D |
| B9 Curry, rice | yes | 40 / 68 | 26 | D K |
| B10 Lasagne | yes, tiling quality M | 125 / 148 | 44 | K S D |
| B11 Rührkuchen | yes (bowl residue, unmould TEST) | 105 / 125 | 22 | K D |
| B12 Scrambled egg | yes | 9 / 17 | 12 | K |

Mean 35 moves per benchmark. B3 has 2 min of margin: any repeat of a mat wash breaks PERF-002 b.
