# Meal preparation — targeted invention: assembly, stuffing, carving, securing, singulating, finishing

Second idea round for the gaps G3, G4, G5, G8 and G9 of `design/prep/02-concept-catalogue.md` section 2.4,
for the priority-M operations that no inventor addressed, and for four shared mechanisms that rest on an
untested food result.

All mechanisms here are **concept-independent modules**: a passive tool held by whatever manipulator the
cell has, a loose fixture, a cassette or a station. None needs a particular cell architecture. They assume
only what section 4.1 of the catalogue found in every lens: a flat work surface or tray (GN family), a
top-down camera, a load cell under the work position, one roll axis, a slow turntable, a press or Z axis
with 0.5–1.5 kN, and a wash chamber for loose ware.

## 0. Conventions and status

**Nothing here was built or tested.** Provenance tags:
[K] known practice (a consumer or industrial product works this way),
[C] calculated in this document from stated inputs,
[E] my estimate.
Confidence: **H** = I expect ≥ 90 % success after normal engineering; **M** = sound, 60–90 %, a bench test
decides; **L** = speculative, < 60 %.

New mechanisms are numbered **GA-01 … GA-40** (own series, so that parallel gap documents cannot collide
with the SM numbering of the catalogue). SM, UO, MEAL, K and corpus codes are those of the catalogue,
the requirements and the corpus.

"Cost in coverage" counts corpus meals (of 248; the reserve of requirements 5.4 is 4 meals) that fall out,
and separately the meals that stay preparable but must be marked *adapted* (MEAL-013 budget: 10 % = 24
meals, not yet counted by anyone).

Shape rule used for every new food-contact part (from E's rule C2, research R6 rule 1–4): one piece or
fully welded; bent sheet, laser-cut plate, tube, rod or body of revolution; radii ≥ 3 mm; no hinge, spring,
thread or closed hollow in the food zone. Where a part breaks the rule, it is said.

### Summary

| Gap | Recommended | Conf. | Fallback and its cost |
|---|---|---|---|
| G3 open-hand assembly | GA-01 peel with fixed stripper bar over a weighed, collared build spot; GA-03 stand-and-fill rack (taco, hot dog, pita); GA-04 plough-and-loop fold roller (burrito); GA-02 butter laid as a ribbon | H burger, sandwich, toast; M–H taco; M burrito | served as components (SM-244): 0 meals lost if the customer accepts, else up to 9; realistic residual risk 1 meal (burrito) |
| G4 stuffing | flat pocket: GA-08 fold, crimp and bread with ham-wrapped cheese; sheet pockets: GA-09 ridge tray; cores: GA-11 inject after cooking; cavity: GA-13 liquid aromatics by lance | M–H / H / H / H (adapted) | two thin cutlets crimped; 0 meals lost, 2–3 adapted |
| G5 carving | boneless: GA-14 trough with overhang cut, twin counter-reciprocating blade and drawbridge catcher; poultry: GA-17 vertical split stand with offset blade (upgrade), parts as baseline; fish: served whole | H (firm roasts), M (braised) / M–L / — | chill-slice-reheat for braises; bird roasted as parts (1 meal adapted, weight 3); 0 lost |
| G8 tie, truss; Rouladen | Rouladen: GA-20 hairpin-skewer raft set through the comb cradle as a jig, on top of side-fold, flour-dusted salted flap and seam-down sear; bird: vertical stand; roast: GA-23 sprung trough cage | H (raft), M (cradle alone) | single pins with inductive count-out; 0 lost |
| G9 singulate, leafy, long | slices: GA-24 shear dealer (top roller and retard lip) with mass check; bacon: peel roll at 12–15 °C or diced; leafy: GA-28 loss-in-weight grabs with a trim grab; spaghetti: GA-29 log-roll weir box; leek: slice until the scale says stop | M / M / H / M–H / H | slice from the block (SM-100); whole-box emptying; 0 lost |
| Priority operations | see the table in section 6 (15 operations) | mostly H | — |
| Pan-pair flip with fat | keep, with five rules (≤ 30 mL free fat, ground rim land or drip skirt, release check, full-floor items only, never for shallow-frying); GA-36 lift-rack turn for fat > 30 mL | M–H | two-sided heat or top heat (adapted) |
| Equator-scored egg | **replace**: pull-apart physics does not work with a scribe; use bottom strike and hinge-open (SM-165 kinematics) plus per-egg inspection and straining of beaten egg | H | liquid egg for mixtures (permitted) |
| Egg separation | one-piece slotted saucer, one egg per cup, inspect, commit | M–H | carton egg white; whole-egg recipes (≤ 3 meals adapted) |
| Mesh powder dosing, humid | keep only inside a dry dock purged with cold-store air and with warm boxes; GA-39 core tube as the plain-box fallback | M–H (dry dock), L–M (cell air) | tilt-pour plus scoop trim |

---

## 1. G3 — Open-hand assembly

### 1.1 What the meals actually need

The 17 ASM meals of the corpus, sorted by what is physically required:

| Need | Meals (weight) | Hard part |
|---|---|---|
| Flat stack on bread or bun | BF11 Abendbrot (3), US08 sandwich or wrap (2), US07 toasted sandwich (3), FR06 croque monsieur (1), US01 burger (3), US06 pulled pork bun (1), BF14 eggs Benedict (1) | laying limp slices exactly; spreading on soft bread; closing; keeping the stack together to the hatch |
| Filled fold or trough | MX02 tacos (2), US02 hot dog (2), ME03 gyros in pita (2) | holding an open shell while filling; serving it without it tipping |
| Fold-and-roll | MX03 burrito (2), AS05 sushi (excluded X-12) | side folds, tight roll, seam |
| Flat item on flat item | IT12 saltimbocca (1), MX04 quesadilla (2) | laying a slice and fixing it; fold in half |
| Arrangement in a bowl or on a plate | AS06 ramen (1), SA15 niçoise (1) | plating (SRV-005), not assembly in the strict sense |
| Wrapped at the table | MX05 fajitas (2) | none: the corpus row itself says "wrapping at table" |

Also asked for: layered cake (CK05, weight 3), canapé (excluded X-12), layered casserole (OK in the
catalogue, SM-108), pizza topping (IT10, weight 3).

Two observations shape the inventions. First, nearly everything is "deposit from above onto a known base";
the only really hard actions are **releasing a limp slice in the right place** and **keeping a loose
stack contained**. Second, pick-and-place with a gripper (SM-109) is slow and soft slices stick to the
gripper; a gripper-free lay-down is wanted.

### 1.2 Candidates

**GA-01 Peel with a fixed stripper bar, over a collared and weighed build spot** (recommended core)

```
   side view                                   top view of the build spot
   manipulator ──┐                              ┌───────────────┐
      peel 0.8 mm│ slice ~~~~~~                 │   collar       │  round Ø 115 × 70 (burger)
   ══════════════╧════════════  → retract       │   ┌───────┐   │  square 125 × 125 × 60 (bread)
                  ┃ stripper bar Ø 8, hung      │   │ stack │   │  open at top and bottom
                  ┃ in two hooks, fixed         │   └───────┘   │
              ┌───┸───┐                         └───────────────┘
              │ stack │ in collar; top of stack 5–10 mm below the bar
              └───────┘
        plate on Z-lift and load cell
```

Every limp item is created or singulated **onto a thin polished peel** (stainless 0.8 mm, 140 × 200 mm,
front edge chamfered to 0.3 mm): slices come off the slicer or the dealer (GA-24) directly onto it, a row
of tomato or cucumber slices arrives shingled as the slicer made it. The manipulator carries the peel
over the build spot, under a fixed bar; then it retracts the peel at 100–200 mm/s. The bar holds the
item back and it lays down on the stack from a height of 5–10 mm without sliding sideways (the bakery
peel and the retracting-belt placer of sandwich lines [K], here without a belt).

* Physics: the bar must overcome friction and film adhesion between slice and peel. Friction of a 20 g
  wet slice at µ ≈ 0.5 is 0.1 N; the viscous film adds τ = ηv/h ≈ 0.01 Pa·s × 0.15 m/s / 20 µm = 75 Pa,
  that is 0.75 N on 100 cm² [C]. A ham slice carries this in compression over its 100 mm edge only if it
  does not buckle: it lies flat on the peel, so buckling is suppressed by the film itself. For very limp
  leaves the bar is lowered to 1 mm above the peel.
* Position error: the item is released where the bar is, ±3 mm [E]; SRV-005 allows ±15 mm.
* The **collar** (a tube section, lifted in by the manipulator) centres each layer and catches what
  slides. It stays on during transport and is lifted off at the hatch while a ring finger holds the top
  (SM-078 extended). For plates without a collar the transport limit is a ≤ 2 m/s² and tilt ≤ 10°
  (tomato on lettuce, µ ≈ 0.2 [E]).
* The **load cell** under the build spot checks every layer (a missed or double slice is ±20 g against a
  resolution of 1 g); the camera checks position. No force sensing in the tool.
* Cleaning: peel, bar, collars are plate, rod and tube; all loose, all go to the washer. The bar hangs in
  two open hooks, so no fixed food-contact surface is created (HYG-033 not triggered).
* Confidence H for bread, cheese, ham, patty, tomato rows; M for single lettuce leaves (curl, spring
  back): use torn or cut leaf pieces of about 80 mm, or shredded lettuce dropped through the collar.

**GA-02 Butter ribbon: lay, do not spread.** Spreading cold butter tears soft bread: butter at 5 °C has a
yield stress of 50–100 kPa, fresh crumb fails at about 5–10 kPa [E]. A wire plane (a 0.4 mm wire
tensioned 1.0–1.2 mm above a sliding shoe) draws a ribbon 1 mm thick from the cold block (SM-148 family);
10 g is 100 × 100 × 1.1 mm. The ribbon lands on the peel and is laid like any slice. Soft spreads
(mayonnaise, mustard, quark) are laid as a zigzag by a nozzle (SM-110) and need no spreading because the
next layer presses them flat. Cleaning: shoe and wire frame are a bent sheet and a rod; the wire is a
wear part. Confidence H. No sensing.

**GA-03 Stand-and-fill rack: the fixture goes to the table.**

```
   end view            W-rack of 1 mm bent stainless sheet, 3 troughs, 45 mm wide, 60 deep, 160 long
   \    /\    /\    /  the rack stands on the plate and is served (restaurant taco holders [K])
    \  /  \  /  \  /
     \/    \/    \/    inverted (M position) it is a bake form for crisp shells
```

A warm soft tortilla laid over a trough by the peel sags in under its own weight. Filling is dosed along
the trough by the depositors moving above (meat by scoop or piston, cheese and lettuce sprinkled, sauce by
nozzle). The same rack holds a hot-dog bun (a V-plough pushed into the slit opens it), a folded pita for
gyros and a finished wrap seam-up. Crisp shells are made instead of bought: the tortilla is draped over
the inverted rack and baked 8 min at 180 °C (home method [K]); a second rack clamped on and the pair
inverted puts the shells mouth-up (rule R1 of the catalogue, no new hardware). Bought hard shells come
nested and fragile (they break at 5–10 N [E]); de-nesting them is not attempted.
Cleaning: bent sheet, washed with the dishes. Sensing: camera for the fill line, load cell for the
quantity. Confidence H for soft tortilla and hot dog, M for shells baked on the rack (does the tortilla
slide off the ridge in convection air? a rod across the top holds it).

**GA-04 Plough-and-loop fold roller** (burrito, enchilada, cabbage roll, Rouladen — one module)

```
   top view, feed →                       section through the loop
   plough rail  ___________               bar A ○─────╮       ╭─────○ bar B
               /   flap folded in          slack loop  ╲ roll ╱   bars close, band driven:
   ═══[ tortilla with filling line ]═══▶                ╲_◎_╱    content rolls 1.5–2.5 turns
               \___________                end flaps were folded in by the ploughs first
   plough rail
```

The slack-loop roller (SM-079, 4/6) is kept, and two fixed **plough rails** are added in front of it:
as the item is drawn towards the loop, the rails lift both side margins (40–60 mm each for a Ø 250–300
tortilla, 15 mm for a Roulade slice) and lay them over the filling, the way a plough turns a furrow.
Burrito machines fold sides with paddles before rolling [K]; ploughs do it with no actuator. The roll is
released seam-down. A burrito seam is set by 30 s seam-down at 180 °C in the pan (the corpus row MX03
already contains TST); starch and cheese glue it.
Physics: tortilla must be at 40–50 °C to fold without cracking; filling line ≤ 140 mm long and ≤ 250 g;
loop circumference set to 1.1 × the final roll circumference. Cleaning: loop band as in SM-079 (the band
is a loose homogeneous belt, washed and dried flat), ploughs are two bent rods. Sensing: camera for slice
outline and end of roll; motor current of the loop as a jam signal. Confidence M (side folds springing
back before the loop closes is the open point).

**GA-05 Inverse build in a cup** (alternative to GA-01 for the burger). The crown goes crown-down into a
cup Ø 115 × 70; everything is dropped in reverse order with loose tolerances; the heel goes on last; a
plate is set on top and the pair is inverted. No stripper, no collar handling, the cup contains
everything. Drawback: sauce and patty juice run towards the crown for some seconds, the hot patty sits on
lettuce. Confidence H mechanically, M on result. Kept as fallback for GA-01.

**GA-06 Side fork for buns and crowns.** A three-tine fork (tines Ø 2.5 × 60 mm, 25 mm apart) enters the
crown horizontally 10 mm below its top and carries it; the fixed bar strips it. Bread crumb hides the
holes (needle grippers are the bakery standard for this reason [K]). Pre-sliced buns that still hang
together at a hinge are separated by the same fork lifting the crown while the heel is held down by the
collar. Confidence H.

**GA-07 Wire-edged peel for cake layers.** A peel Ø 260 with a tensioned 0.5 mm wire 2 mm ahead of its
front edge, guided at a set height over the turntable: the wire splits the sponge (2–5 N [E]) and the
peel follows in the cut and carries the upper layer off in the same stroke. Cream or jam is spread on the
lower layer on the rotating turntable (SM-097, SM-110), the upper layer is stripped back by the fixed
bar, all inside an adjustable cake ring. Confidence M–H. For CK05 (strawberry sponge cake) no split is
needed: fruit is laid inside the ring and the glaze poured in a spiral (section 6, glaze).

**Build big, cut small** (canapés, excluded by X-12 but cheap to regain): assemble one open sandwich of
100 × 100 mm with GA-01, then press a 3 × 3 grid with its pusher through it (SM-009, SM-011). Nine
canapés per stroke. Confidence M (smearing of soft toppings on the blades).

**Layered casserole and pizza topping** are rated OK in the catalogue (SM-108). Numbers to make it real:

* Lasagne in a GN 1/2 dish: dried sheets are rigid plates (1 mm, 17 g) and are taken from the top of the
  stack by one Ø 30 suction cup or dealt by GA-24; they must arrive **stacked flat** in the box (request
  to ingestion). Sauce as three parallel ribbons from a piston or ladle, levelled by one pass of a blade
  at a set height. Layer tolerance ±20 % is met by mass per layer on the load cell.
* Pizza: base on the turntable at 20–30 rpm; sauce as a spiral from the nozzle moving outwards at constant
  surface speed; cheese from a vibrated chute whose radial dwell is proportional to r, so that mass per
  area is constant [C]; 150 g at 5 g/s takes 30 s. Slices of salami or mushroom fall at random from the
  same chute; "even ±30 %" (UO-91) is met, a regular pattern is not attempted. Tray pizza: raster instead
  of spiral. Grated cheese that has clumped in the box is the main risk: a rake across the chute breaks
  clumps.

### 1.3 Recommendation, experiment, fallback

**Recommended set:** GA-01 (peel, bar, collars) as the general assembler; GA-02 butter ribbon; GA-06 bun
fork; GA-03 rack for taco, hot dog, pita; GA-04 for burritos (shared with Rouladen and cabbage rolls).
Seven small passive parts, no actuator, no vacuum.

Sensing: top-down camera (outline of base, position of each layer) and the build-spot load cell. No
force sensing.

**Cheapest experiment** (about 40 EUR): a cake lifter or wide fish slice as the peel; a ruler clamped
between two books as the bar; a Ø 110–120 pastry ring and a square ring; a stainless taco holder; a
cheese plane with wire for the butter. Build 20 burgers and 20 sandwiches by moving only the peel; record
lay-down error (> 10 mm = fail) and layers that fold or stick. Then put each plate on a drawer slide and
jerk it (2 m/s² is 50 mm in 0.22 s) and tilt it 10°, with and without the collar. For GA-04: two broom
handles, a strip of silicone baking mat as the loop and two bent wire rails; 20 burritos.

**Fallback:** serve as components (SM-244). If the customer accepts, nothing falls out. If not, up to 9
meals are at stake (MX02, MX03, US01, US02, US06, US08, BF11, ME03, MX04), more than the reserve of 4.
With the per-dish confidences above, the realistic residual is the burrito (1 meal; fallback
enchilada-style: rolled, laid seam-down in a dish and baked, marked adapted).

---

## 2. G4 — Stuffing

### 2.1 What the meals need

| Case | Meals | Remark |
|---|---|---|
| Flat meat pocket | DM05 cordon bleu (2) | corpus chain BFL, POU, STU, BRD |
| Sheet pockets | CK17 apple turnovers (2), IN07 samosa (1), AS09 gyoza (1); ravioli and Maultaschen are excluded (X-06) but fall out of the same tool | fold or cover, seal, cut |
| Core in a dumpling | DS11 Germknödel (1); plum dumplings and filled potato dumplings are not in the corpus but are the same case | close dough round a core |
| Cavity of a bird or fish | DM20 roast chicken (3), DM21 duck (1), FI07 whole fish (1) | find and fill an opening in a limp body |
| Rigid cavities, open boats, tubes | DM13, VG04, SD25, IT18, DS15 | OK in the catalogue (SM-076) |
| Leaf or sheet round a filling | DM12, MX07, CK12 | wrapping: GA-04; leaf separation is gap G7 |

### 2.2 Flat meat pocket (cordon bleu)

**GA-08 Fold, crimp and bread; cheese wrapped in ham** (recommended). No pocket is cut. The cutlet is
flattened to 4–5 mm and about 250 × 150 mm (SM-089). A cheese slab 60 × 40 × 6 mm is rolled into one ham
slice in the loop of GA-04, so that the ham encloses the cheese (the cook's trick against leaking). The
parcel is laid on one half of the cutlet, 15 mm from the edges; the other half is folded over by the mat
or book flipper (SM-091, SM-103); a **crimp frame** (a U-shaped ridge 3 mm wide on the platen) presses
the three open margins.

* Physics: salted, pounded meat surfaces bond by extracted myosin; the crimp needs about 0.4 MPa on the
  ridge [E]. Ridge area 3 mm × 500 mm = 15 cm², force 600 N [C], inside the 0.5–1.5 kN of the platen.
  The flour–egg–crumb coat applied next is the real seal, as at home; frying sets it within a minute.
* Leak criterion: cheese flows above about 65 °C. With ham wrap, crimp and coat I expect fewer than 10 %
  of pieces to show a leak [E]; a leak is a blemish, not a failure of the meal.
* Cleaning: crimp frame is a bent rod welded on a plate. Sensing: camera checks that the parcel lies
  inside the margin before folding. Confidence M–H.

**Two thin cutlets as base and lid**, crimped all round with a closed frame (800 N). Simpler to automate
(no fold), two seams more. Confidence M–H. This is the fallback.

**Fold and pin** (SM-077): works, but brings pins into a breaded, fried item where they are hard to find
again. Not recommended.

Experiment (15 EUR): 10 cutlets, rolling pin, ham, cheese, a pastry ring or a bent 3 mm rod as crimp
frame pressed with a bathroom scale under the board to read the force; bread and fry; count leakers and
open seams.

### 2.3 Sheet pockets

**GA-09 Ridge tray** (recommended): the ravioli board [K], enlarged. A one-piece plate with cavities
(80 × 80 × 15 mm for turnovers, 45 × 45 × 10 for ravioli and gyoza) separated by raised ridges 1 mm wide.
Sheet 1 is laid over the tray by the peel and sags or is pressed into the cavities by a soft-stud platen;
filling is deposited by nozzle or scoop by mass; the margins are wetted (water or egg wash from the
roller of section 6); sheet 2 is laid on; a roller passes over the ridges and seals and cuts in one pass.
The tray is inverted onto the baking tray (rule R1) and the pockets drop out.

* Physics: cutting two 1 mm dough layers on a 1 mm ridge needs 1–2 N per mm of ridge in contact [E];
  when the roller crosses a transverse ridge of 300 mm this is 300–600 N, within the press range, or the
  roller is set at 5° so that it crosses ridges progressively (force ÷ 4).
* Shapes are square, not pleated half-moons or pyramids: gyoza and samosa are marked adapted in shape.
* Cleaning: tray is one machined or pressed plate with radii ≥ 3 mm, floured before use, washed.
  Sensing: load cell for the filling per cavity; camera for sheet position. Confidence H for bought puff
  pastry and wrappers (the consumer tool works by hand), M for release of wet fillings.

**Fold-over with a crimp frame** on the flat tray: a square of pastry, filling on one half, folded by the
peel lifting one edge, crimped with a U-frame like GA-08. One pocket at a time; no special tray.
Confidence M–H.

**Hinged dumpling press** [K]: works, but hinge and teeth are hard to clean. Rejected.

Experiment (20 EUR): a ravioli board and a rolling pin; bought puff pastry and gyoza wrappers; 3 boards
each; count unsealed and stuck pockets after inverting.

### 2.4 Cores in dumplings

**GA-11 Inject after cooking** (recommended for jam, Powidl, custard cores). The dumpling is formed and
steamed unfilled; a Ø 5 mm side-hole needle on the syringe tool (SM-144) injects 20 g into the centre,
as bakeries fill Berliner [K]. Nothing has to be closed, no core can leak during cooking. Cleaning: the
needle is a straight tube, flushed and washed. Sensing: none (depth from the known dumpling diameter,
mass from the stroke). Confidence H. Arguably not even an adapted method; the result is the same.

**GA-10 Sphere pair with a rigid core** (for solid cores: plum, crouton, a frozen jam puck per SM-147).
Two hemispherical cups Ø 60. Half the dough is pressed into the lower cup with a Ø 25 dimple punch
(back-extrusion forms a bowl), the core is dropped in, the second half is laid on as a lid and the upper
cup closes at 20–50 kPa (60–140 N). Potato dough is plastic and welds; yeast dough springs back and needs
moist, unfloured seam faces. Cleaning: two cups and a punch, bodies of revolution. Confidence H for
potato dough, M for yeast dough.

**GA-12 Poke and round**: portion in the orbiting rounder cup (SM-073), core pushed in with a punch,
rounding continued opening-down so that the neck closes (bakery rounding seals a seam at the bottom [K]).
No extra part where a rounder exists. Confidence M.

Experiment: one batch of Germknödel dough; 6 by sphere pair (two ladles), 6 poked and rounded by hand in
a cup, 6 injected after steaming with a 20 mL syringe and a wide needle; cut open, judge centring and
leaks.

### 2.5 Cavity of a bird or a fish

The obstacle is not the filling but **orienting a raw, slippery 1.5 kg body** so that a Ø 50–70 mm
opening points at the tool.

**GA-13 Liquid and paste aromatics by lance** (recommended; adapted method). The corpus stuffings are
aromatics, not bread stuffing: lemon, thyme, butter (DM20); apple, onion (DM21); lemon, dill, garlic
(FI07). Lemon juice, herb butter and crushed garlic are injected into the cavity as 30–50 g of paste
through a Ø 12 lance; the opening only has to be found within ±15 mm, which the camera can do on a bird
lying in its tray. Apple and onion wedges roast beside the duck in the tin. For the fish, lemon slices
and dill are laid under and on it. Cleaning: lance is a tube. Confidence H as a mechanism; taste
difference small [E], to be confirmed by MEAL-015 rating.

**GA-17 cone stand** (see 3.3): when the bird is put on a vertical stand for roasting, the cavity is
first presented upwards in a funnel and can be filled by gravity through a Ø 45 tube with a tamper
(SM-117) before the stand is pushed in. Confidence M–L (depends on the orientation step).

**Buy parts**: no cavity. See 3.3.

Fallback cost: none lost; DM20, DM21, FI07 marked adapted if GA-13 is used (DM21 falls out anyway, X-04).

---

## 3. G5 — Carving

### 3.1 The meals

CAR appears in 12 rows. DM23 steak is sliced like a small roast (tagliata; optional). DM16 Kassler, DM11
meat loaf, DM06 pork roast, DM07 Sauerbraten, DM08 pot roast, DM29 Tafelspitz are **boneless** (DM06
bought boneless). DM17 knuckle is traditionally served whole, one per person: no carving. ME10 leg of
lamb is bought boneless in a net (the net must come off, see 4.3). US04 ribs are cut between bones. DM20
and DM21 are bone-in birds. FI07 is a whole fish.

### 3.2 Boneless roast: do the easy case well

Physics. A hot roast is soft and wet. A pressing cut squeezes juice out and tears a braise along its
fibres; a slicing cut with a slice-to-push ratio above about 3 lowers the normal force by a factor of 3–5
[K, Atkins]. Forces with a sharp blade in slicing motion: 2–10 N [E]. Slices of braised beef at 85–90 °C
core do not survive below about 6–8 mm; firm roasts (pork, Kassler, meat loaf, pink beef) can be cut to
4 mm hot. The 2 mm of UO-80 is reachable only on chilled meat. After 10–15 min rest a 1 kg roast loses
10–30 mL of juice on carving [E]; it belongs in the gravy.

**GA-14 Trough, overhang cut, twin blade, drawbridge** (recommended)

```
  side view                              drawbridge = gauge plate, hinged at the bottom
                  twin blade ║            
   follower →┌──────────────║┐  gap t    1. pusher advances roast by t against the drawbridge
   5–10 N    │    roast     ║│◄──►│      2. blade descends along the trough end face (1 mm clear)
   ══════════╧══════════════╩╛    │      3. drawbridge lowers 90°: slice lies on the plate
      V-trough with juice groove   ╲     4. plate (or peel) retreats by pitch p: slices fan
      → juice well on the scale     ╲___ plate receding
```

* The roast lies in a **V-trough** (90° V of bent sheet, 300 mm long, juice groove to a well). Gravity
  centres it, including after 20–30 % shrinkage. No spikes. A follower pushes axially with 5–10 N.
* The blade is the **counter-reciprocating twin blade of an electric carving knife** [K]: two serrated
  blades, stroke about 10 mm at 50 Hz, moving against each other. The friction forces of the two blades
  on the meat cancel, so the roast is not dragged and needs almost no holding; feed force 2–5 N. The
  blade pair is driven through the tool interface; outside the food zone.
* **Overhang cut**: the roast is advanced beyond the trough end by the slice thickness t and the blade
  passes 1 mm in front of the end face, never touching steel. Thickness is free from 4 to 20 mm and is
  set by the **drawbridge**, a plate standing at distance t in front of the end face: it is the gauge, it
  supports the slice during the cut (a braised slice would otherwise fold away and tear at the bottom),
  and it lays the slice down by swinging 90° about its lower edge.
* **Fanning** follows from the kinematics: the plate or peel under the drawbridge retreats by a pitch p
  after each slice; overlap = slice height − p. With 80 mm high slices and p = 25 mm, three slices per
  portion make a fan 130 mm long. Portion by count and by mass on the load cell.
* Crackling roast (DM06): the rind was scored by the machine at a known pitch in the same trough datum;
  slice pitch is set to a multiple of the score pitch so that the blade runs in the score lines.
* Accuracy: thickness ±1 mm (gauge plate; soft meat bulges). Time: 3 s per slice.
* Cleaning: trough, follower, drawbridge are bent sheet. The twin blade is the critical part: two blades
  joined by a keyhole rivet [K]; they must be separated before washing (slide to the keyhole, a jig at
  the wash rack does it) or replaced by a single reciprocating blade plus a serrated counter-edge. This
  is the one hygiene question of the module.
* Sensing: load cell (slice mass, juice mass); camera for the end of the roast; motor current as a bone
  or string alarm. Confidence H for firm roasts, M for braises.

**GA-15 Comb cradle as mitre box.** The roast lies in a cradle of Ø 4 mm rods at 8 mm pitch; a draw
knife or the twin blade descends between the rods. After cutting, the slices still stand in the comb as a
whole roast, which keeps them hot and lets the cradle be carried to the plating position; the row is then
pushed out over the end and the slices topple one by one onto the receding plate. Thickness only in
multiples of 8 mm. The same cradle can be the roasting rack and the scoring jig (section 4.3).
Confidence M–H. Better than GA-14 where the roast should stay assembled (family-style serving, SRV-018).

**GA-16 Chill, slice, reheat** (catering method [K]). The braise is cooled to ≤ 10 °C core (2–3 h for
1 kg in the cold store), sliced cold and firm at any thickness on the normal slicer, fanned in a GN tray,
covered with gravy and reheated to 75 °C. Equal or better slices; costs 3 h or cooking the day before.
Fallback for braises if GA-14 tears them.

Draw knife with a carving fork on the manipulator (SM-032) remains the zero-hardware option for firm
roasts; band knife and ultrasonic blade are rejected (guarding and cleaning; cost).

Experiment (35 EUR plus the meat): an electric carving knife; a piece of angle profile or a loaf tin
with one end cut off as trough; a bench scraper held at distance t as the drawbridge. Cook one pork
roast and one pot roast (core 90 °C); carve at 6, 8, 12 mm after 10 min rest; count intact slices, weigh
the juice; repeat the pot roast after chilling.

### 3.3 Bone-in poultry

Honest position: jointing a roast bird as a cook does (legs through the hip joint, breast off the keel)
needs joint-finding by touch and is **not** solved here. Three candidates reduce the problem.

**Baseline: roast the bird as parts** (legs and breasts on the bone, a year-round commodity). No
carving, no trussing, no cavity, shorter roast. DM20 is then an adapted method and must be rated
(MEAL-015). Confidence H.

**GA-17 Vertical split stand and offset halving blade** (the upgrade path; bone-in carving is priority S)

```
   front view                       the stand is two half-mandrels on one base with a 6 mm gap
        ╱╲  bird sits legs down     a. bird roasts on it: browns all round, bastes itself,
       ╱  ╲ on the stand               needs no trussing (section 4.2) and no turning
      │ ┃┃ │                        b. its pose is known from raw to carving (rule R12)
      │ ┃┃ │◄─ gap plane, offset    c. a guillotine blade 250 mm descends through the gap:
      └─┸┸─┘   8 mm from the spine     two halves ("halbes Hähnchen", the German serving)
       base in the roasting tin     d. optional shear cut at mid height gives quarters
```

* The cut runs **8–10 mm beside the spine and keel**, through rib heads and breast meat, not through
  vertebrae. Cooked bones of a 35-day broiler are soft; I estimate 300–800 N peak on a 20° wedge blade
  [E], inside the press range.
* The azimuth of the bird on the stand must be known: side camera (breast against back), then the
  turntable turns the stand.
* Loading the raw bird: it is dropped into a funnel; an elongated body aligns with the funnel axis, tail
  or neck first at random; the camera decides and a rim-to-rim inversion with a second funnel corrects
  it; the stand is pushed into the vent opening from above (cone tip self-centres within ±10 mm); the set
  is inverted. Supermarket birds arrive with the legs held by an elastic loop [K], which keeps the body
  compact for this.
* Oven: stand 150 mm plus bird needs about 280 mm clear height for a bird ≤ 2 kg.
* Cleaning: stand and funnels are bent sheet and cones; blade is a plate. Sensing: camera twice, press
  force. Confidence M for halving once the bird is on the stand, **L–M for loading**; M–L overall.

**GA-18 Pull-apart**: at a thigh core of 82–85 °C the hip joint lets go when the drumstick knob is pulled
outwards with tongs (20–50 N [E]); the breast stays on the carcass. Gives leg portions only. L–M.

Experiment (15 EUR plus 3 chickens): a vertical roaster stand; roast; split with a long knife pressed
through a slot beside the spine on a bathroom scale to read the force; repeat on the midline to see the
difference. Separately: drop a raw bird 10 times into a large funnel or bucket with a Ø 120 hole and
record how it comes to rest.

**Ribs (US04):** served as half racks. One cut between two bones by a blade with ±5 mm lateral compliance
that slides off the bone into the gap; the bone ends are exposed after cooking and visible to the camera.
Confidence M–H.

### 3.4 Whole fish

**Serve whole** (recommended). A whole baked trout or bream on the plate is the traditional form;
requirements X-03 already rules "carved by the guest". A long peel (300 × 100 mm) slides under the fish
on its oiled tray and the fixed bar strips it onto the plate. Confidence H; cost 0 meals.

**GA-19 Top fillet lift** (optional): a blunt blade cuts along the back and behind the head with a force
limit of 2–3 N (it stops on bone because cooked flesh yields at 5–10 kPa and bone does not); a flexible
peel enters from the back, rides on the rib cage and lifts the upper fillet; the skeleton is lifted by
the tail; the lower fillet stays. Pin bones remain. Needs force sensing and a camera. Confidence L–M.
Not recommended for the first build.

---

## 4. G8 — Trussing, tying, and Rouladen without string

### 4.1 Rouladen: critical assessment of the tie-free claim

The claim (SM-084, 5/6): roll in a slack loop, lay the rolls seam-down in a comb cradle or channel,
sear the seam first, braise and lift out in the cradle; no string. Two inventors add pins.

What actually acts on the roll, for a 5 mm slice of 150–200 g rolled 2–2.5 turns to Ø 45–55 × 120 mm:

1. **Raw**: meat is plastic, elastic recovery is small; the roll stays shut while it lies seam-down.
   It opens when it is gripped or turned with the seam sideways or up.
2. **Searing seam-down, 60–90 s at 200 °C**: the flap is pressed on by 2 N of weight. Where meat touches
   meat, extracted myosin sets to a gel above 60 °C and bonds the flap. **Mustard on the flap prevents
   this bond** (acid and oil); every inventor spreads mustard over the whole slice. A bond of 2–10 kPa
   [E] over 120 × 30 mm would carry 7–36 N in shear [C]; the forces that open a flap are below 1 N. So a
   set seam is plausible, but only on a mustard-free, salted flap.
3. **Turning for browning**: in a comb cradle the sides are shadowed (the authors say so). Browning
   falls to the bottom strip; the fond and the gravy suffer. If the rolls are taken out to brown the
   other sides, the unset part of the seam opens.
4. **Braising 90 min at 90–95 °C**: the slice shrinks 10–15 % in its plane and the roll loses 25–30 % of
   its mass; Ø 50 becomes about Ø 40 [E]. The roll tightens on its filling (filling is squeezed out of
   open ends) and becomes loose in a 40 mm slot. The collagen part of the seam bond melts; the myosin gel
   stays. Simmer bubbles move loose rolls.
5. **Plating**: the cooked roll is heat-set in its shape and no longer wants to unroll, but it is so
   tender that tongs tear it. It must be lifted from below.

Verdict: many home cooks do braise untied Rouladen seam-down and it mostly works, when the rolls are
tight and packed [K]. My estimate for the cradle alone is **75–85 % of rolls fully closed** [E], with
poor browning. That is not enough for a meal the brief names (REL-001 asks 98 % per meal, and a meal has
4–6 rolls). The cradle is a good **jig**, but it is not a fastener.

### 4.2 Improved Rouladen chain

Five measures, the first four free, the fifth a positive fastener.

1. **Fold the long edges in 15 mm before rolling** (the plough rails of GA-04): closed ends, the filling
   stays in when the roll shrinks.
2. **Keep the last 35 mm of the slice free of mustard, salt it, dust it with flour** (section 6, dust).
   The flour is in the recipe already (gravy). Myosin plus gelatinised starch is the seam glue.
3. **Control the seam angle**: the loop stops when the camera-measured slice length is wound, and lays
   the roll into the cradle with the flap end at about 5 o'clock, 10 mm past the point where the skewer
   will pass.
4. **Sear seam-down first**, 90 s, before anything else moves.
5. **GA-20 Hairpin-skewer raft** (recommended fastener)

```
   top view                                     section through one roll in the cradle slot
   handle ┌────────────────────────────         ╭──────╮
   (out   │ ═══◎═════◎═════◎═════◎═══ tine 1    │ roll │   tines 6 × 1.5 mm on edge, 60 mm apart,
   of the │    roll  roll  roll  roll           │ ═══  │←  pass 12 mm above the floor through
   food)  │ ═══◎═════◎═════◎═════◎═══ tine 2    ╰─flap─╯   guide slots in the cradle walls
          └────────────────────────────         seam at 5 o'clock, pinned 10 mm behind its edge
```

   One stainless part: a two-tine fork with 300 mm tines, like a long carving fork. With the rolls lying
   in the comb cradle, the fork is pushed through guide slots in the cradle walls and through all rolls
   at once. Piercing raw beef with a pointed 6 × 1.5 blade takes 5–10 N per roll [E], 30–60 N for six.
   The cradle is then lifted away. Result: **a rigid raft of 4–6 rolls with a handle outside the food**.

   * Flat tines on edge prevent each roll from rotating; two tines prevent the raft from folding.
   * The raft is seared on its two broad faces by turning it with the handle on the roll axis (1.5 kg at
     150 mm: 2.2 Nm [C]); with 10 mm spacing between rolls about 60 % of the surface browns, against one
     strip in a cradle. Tine sag under the full load is 5 mm, stress 125 MPa [C].
   * It is braised as a raft, lifted out by the handle, drained, and the rolls are pushed off one by one
     by a stripper comb onto the peel, seam-down (1–3 N per roll). Nothing grips a roll at any time.
   * **Nothing small goes to the plate**: one fork instead of 6–12 pins, its handle visible, its return
     to the holster sensed. Catalogue conflict X16 (ferritic pins travelling to the plate) disappears.
   * Cleaning: fork and cradle are rod and sheet parts. Sensing: camera for seam angle; presence switch
     for the fork. Confidence H for holding through sear, braise and plating; M for the seam-angle
     control (if it fails, the free flap tail is at most 40 mm and lies under the roll).

Other fasteners considered:

| Candidate | Finding | Conf. |
|---|---|---|
| Single pins (SM-085) | traditional and sure; 6–12 small parts to set, find in sauce, pull and count; must add an inductive check of each plate for metal | H, handling M |
| Spring C-ring (SM-086) | to follow the shrinkage from Ø 50 to Ø 40 a 0.4 × 12 mm band of 1.4310 must open 44 mm at the gap: 7 N, 900 MPa bending stress, 24 kPa on the meat [C]; works, leaves dents and pale stripes, removal from a tender roll is awkward | M |
| GA-21 silicone bands from a loading tube | bands pre-stretched on a Ø 55 tube, roll pushed through, bands stripped onto it; 8 × 1 mm band gives about 40 kPa [C]; silicone in a 220 °C pan is at its limit, takes up odour, is a wear part (X13) and must be rolled off a tender roll | M–L |
| GA-22 egg-white glue on the flap | sets at 62–65 °C, stronger than flour; adds an allergen to a dish that has none | M, not recommended |
| Ice weld, hot bar (SM-087, SM-088) | replaced by measure 2 above | L–M |

Experiment, **the most important one in this document** (about 40 EUR): 12 Rouladen slices. Roll all
with side folds. Group A (4): mustard everywhere, seam-down in a loaf tin with dividers (the published
claim). Group B (4): dry, salted, floured flap, same tin. Group C (4): as B, then threaded on two flat
metal kebab skewers 60 mm apart. Sear seam-down 90 s, brown the rest as each method allows, braise
90 min at 95 °C, lift out (A, B with a fish slice; C by the skewers and pushed off with a fork). Record
per roll: closed, partly open, open; filling lost; browned area; whether it survives being slid onto a
plate. Decides between "cradle is enough", "glue is enough" and "raft needed".

Fallback: single pins with inductive count-out. Cost 0 meals. Rolling itself stays a TEST item of the
catalogue (SM-079); one large Roulade (SM-243) is the recipe fallback, marked adapted.

### 4.3 Trussing a bird, tying a roast

**Bird.** Three answers, in this order:

1. Whole chickens and ducks are sold with the legs held by an elastic loop or tucked [K]. "Buy trussed"
   is the normal supply form, checked by the camera at first opening.
2. On the **vertical stand** (GA-17) trussing has no function: the legs hang beside the body and cook
   evenly. Confidence H once the bird is on the stand.
3. Roasted as parts: nothing to truss.

A machine-set wire hock clip was considered and dropped (finding two drumstick knobs on a limp bird:
L–M). Cost: 0 meals.

**Roast.** Single-muscle roasts (DM06, DM07, DM08) need no tying. Rolled or boned joints are bought in a
net or string [K] — and this hides a task nobody listed: **the net must come off before carving**, when
it is baked into the crust.

**GA-23 Sprung trough cage** (recommended): the V-trough of GA-14 or the rod cradle of GA-15 with a
top bar of two rods, held down by its own weight (0.5–1 kg) on two guide posts, keeps a boned joint
compact while it shrinks. The bought net is cut **raw** along the top by a guarded hook blade (a seam
ripper: the guard slides under the strands, the blade cannot enter the meat) and pulled off while the
trough holds the joint; raw, it does not stick. The joint then roasts and is carved in the same fixture,
in the same datum as the scoring. Cleaning: rods and bent sheet. Sensing: camera to find the net.
Confidence M–H for the cage, M for net removal.

Alternatives: net applied from a loading tube (butcher's method [K]; a consumable, and it must come off
again: L); silicone bands as in GA-21 (M–L).

Experiment: a boned, netted pork shoulder; cut the net raw with a seam ripper, roast it in a loaf-tin
trough under a weighted rack; compare shape and carving with a netted control.

Fallback: buy only single-muscle roasts. ME10 (leg of lamb, weight 1) is then made from a boneless
single-muscle cut, adapted. Cost 0 meals.

---

## 5. G9 — Singulating stuck slices; dosing leafy and long goods by mass

### 5.1 Why flat lifting fails and what works instead

Two wet slices are joined by a liquid film. Pulling them apart **normal** to the film must draw liquid
into a widening gap (Stefan adhesion): the force is high and grows with speed, so a suction plate or a
freeze plate that lifts flat takes two or three slices, and the lower ones drop off later at random.
Two other modes are cheap:

* **Shear**: τ = ηv/h. With η = 0.01–0.1 Pa·s (brine with protein), v = 20 mm/s, h = 20 µm: 10–100 Pa,
  that is 0.1–1 N for a 100 cm² slice [C]. Sliding slices apart is what a person does with cheese.
* **Peel**: a line front needs F/b = G/(1 − cos θ); with G = 1–10 J/m² and b = 100 mm at 90°, 0.1–1 N
  [C].

Bacon is the exception: at 4 °C the slices are bonded by solid fat, the rasher itself tears at 4–7 N [E],
so it cannot be sheared off; it must be peeled at a low angle, warm enough for the fat to be soft.

### 5.2 Candidates for slices

**GA-24 Shear dealer** (recommended for cold cuts, cheese, fresh pasta sheets, tortillas)

```
   side view        knurled roller Ø 30 on the spindle, 1–2 N down, turns 1/3 turn
                        ◎→
   back fence ┃ ═══════════════  top slice moves 30 mm forward over the lip
              ┃ ═══════════════┃ retard lip: a 1 mm sheet edge at (stack height − 1 slice)
              ┃ ═══════════════┃
              └────────────────┘ stack in its tray on a lift or probed by the roller
                                → the peel comes under the overhang, roller and peel draw the slice off
```

The paper-feeder principle [K]: a friction roller drives the top slice, a retard lip holds the second.
The roller touches the top slice with knurled steel (µ ≈ 0.5–0.8 wet), while slice on slice is
lubricated; the top slice moves at under 1 N. Once it overhangs 30 mm the peel takes it; the slice is
delivered flat on the peel, ready for GA-01. Doubles are found by mass on the peel (one slice 20 ± 3 g)
and are either accepted (the recipe follows the scale, SM-151) or returned. Stack height is probed by
the roller. Tortillas are warmed to 40 °C first (they are tacky and brittle cold).
Cleaning: roller is a body of revolution on the spindle; lip and fence are one bent sheet; the tray is
the storage tray. Sensing: load cell, camera. Confidence M (cheese at > 15 °C smears; very thin ham
wrinkles instead of sliding).

**GA-25 Peel roll** (recommended for bacon, also for puff pastry). A drum Ø 70 with a row of short
needles or a pinch bar takes the leading edge of the top rasher and rolls back over the stack; the rasher
winds on at constant radius, that is, it is peeled at a low angle, and is unrolled onto the peel. Bacon
is tempered to 12–15 °C first. Bought packs are shingled, which exposes every leading edge. Needles or a
pinch bar break the shape rule; the drum is loose ware. Confidence M.
Puff pastry arrives rolled in its paper: the paper edge is clamped and pulled, dough and paper unroll
together onto the tray, and the paper is then the baking paper (section 6, lining). Confidence H at
≤ 10 °C.

**GA-26 Fan by bending**: the stack is pressed over a ridge; slices slip by t·θ each, so a stack bent
through 1 rad shows edges stepped by one slice thickness, and a wedge can enter under exactly one. A
helper for GA-24 and GA-25 when the pack is not shingled. M.

**Do not singulate** (recipe side): bacon for frying starts as the whole block in the cold pan; the
rashers part by themselves when the fat renders and are spread with the turner [K]. Diced bacon in
Rouladen is a common family variant. **Create the slice** (SM-100) from a block remains the certain
fallback for cheese and ham at ≥ 1.5 mm.

Dried lasagne sheets are not stuck; they are lifted by a suction cup or dealt by GA-24 without the retard
problem. Filo and strudel sheets are fragile and dry out in minutes: L–M; CK12 falls back on puff pastry
(adapted).

Experiment (20 EUR): a rubber-covered or knurled roller (paint roller core, wallpaper seam roller), a
steel rule as the lip. Packs of ham, salami, sliced cheese, fresh lasagne, tortillas, bacon. 30 deals
each at 5 °C and at 15 °C; count singles, doubles, tears. For GA-25 a rolling pin with a strip of
hook tape as the needle row.

### 5.3 Leafy goods by mass

A salad portion tolerates ±15 %; the seasoning follows the scale. The task is therefore easier than the
catalogue's "±10 g at best" suggests.

**GA-28 Loss-in-weight grabs with a trim grab** (recommended). The box or the spin basket stands on the
load cell. Wide tongs (90 mm opening) take 25–40 g per grab; when the remainder to target is below one
grab, narrow tongs (30 mm) take 5–10 g. If the last grab overshoots by more than 15 %, it is dropped
back. Expected error ±8 g on 60–360 g [E]. Cleaning: two tongs (each is one bent spring-steel strip, no
hinge). Sensing: load cell only. Confidence H.

**GA-27 Picker drum**: a slow pin drum at the mouth of the tilted box pulls tufts over the edge onto a
weigh pan (the feeder of salad multihead weighers [K]). Finer resolution, one more part with pins. M.

**Dose by subtraction**: tip the whole box on the weigh pan and take away the surplus. H, but handles
everything twice.

Part of a head of lettuce: the whole head is processed (quartered on the board, core cut out as a V,
cut into 40 mm pieces, washed and spun, which also separates the leaves) and the surplus is kept spun-dry
in a vented box for 3–4 days; the scheduler plans salads accordingly. No partial head goes back.

### 5.4 Long goods by mass

**GA-29 Log-roll weir box for spaghetti** (recommended). Spaghetti (250 mm) lies lengthwise in a GN 1/3
box. At the dock the box is tilted about its long axis until the rods roll over the long edge, one layer
deep, into a V-tray on the load cell; tilting back stops them. One rod weighs about 1 g, a portion of
100–125 g is a bundle of Ø 24 mm. Rods roll at a tilt a little above their friction angle (17–25° [E]);
a flow of 20–40 rods per second gives ±5 g. The V-tray slides the bundle end-first into the pot and the
stirrer pushes it under after 60 s. Requires the rods to be loaded **aligned** at ingestion (slide the
pack contents in lengthwise). Cleaning: nothing but the V-tray. Sensing: load cell. Confidence M–H
(crossed rods at the weir are the risk; a tap clears them).

**Gauge grab**: V-jaws closing to a stop take what fits (the Ø-hole spaghetti measure [K]); ±10 %. M–H.

**Leek, cucumber, carrot, celery**: these are sliced anyway. One piece is fed to the slicer and cut
**until the scale under the receiving vessel reaches the target**; the rest goes back into the box
(dosing from bar stock, SM-148). Confidence H.

Fallback for the whole of G9: slice from the block; empty whole boxes; short pasta instead of spaghetti
is not acceptable (IT01 is named in the brief), so GA-29 or the gauge grab must work. Cost 0 meals.

---

## 6. Priority operations nobody addressed

For each: candidates (a), (b), (c); the recommended one in bold; numbers; cleaning; sensing; confidence;
cheapest experiment; fallback and cost.

### 6.1 Grease a tin or pan (LIN, 22 meals)

* (a) **GA-30 Swirl-coat**: 5 g of oil or clarified butter dosed into the tin, the tin rotated at
  10–20 rpm on the turntable tilted 60–80°, so that the liquid runs over floor, corner and wall, then the
  excess drained by inversion. For flouring: 15 g of flour, same motion, excess dumped. Reaches fluted
  tins (Gugelhupf) where a brush fails. Film 30–50 µm on 1100 cm² is 3–5 g [C]; butter on a cold tin
  freezes on contact to 0.3 mm (33 g), so the tin is warmed to 40 °C or oil is used.
* (b) Silicone brush on the manipulator with a fat cup: M; slow raster, brush to wash.
* (c) Release spray: aerosol of fat in the cell; rejected.
* Cleaning: nothing but the tin. Sensing: camera under oblique light sees matt dry spots (optional).
  Confidence H. Multi-cavity trays (muffins) do not swirl: 0.5 g oil per cavity from the pipette, spread
  by a Ø 50 silicone dabber, M.
* Experiment: cake tin, 5 g oil, swirl by hand 20 s, flour, bake a pound cake, unmould; against a
  brushed control.
* Fallback: lining (6.2). Cost 0.

### 6.2 Line with baking paper

* (a) **Reusable liner that stays with its tray**: a PTFE-glass baking sheet [K] or the carrier mat of
  SM-091, cut to the GN tray, leaves its tray only in the washer. The baked product is drawn off with
  the liner over a nose (SM-101). No consumable.
* (b) The paper that comes with bought pastry (GA-25).
* (c) Pre-cut paper blanks picked by a suction cup with an edge flick, fixed with three dots of fat: M;
  a consumable the human refills (X13).
* (d) No liner: greased and floured tray (6.1).
* Cleaning: liner hangs by two eyelets in the wash rack. Sensing none. Confidence M–H (liner life and
  odour uptake to be measured). Fallback (d), cost 0.

### 6.3 Glaze, brush, egg wash (GLZ, 7 meals)

* (a) **GA-31 Driven soft roller**: a silicone sleeve Ø 40 × 80 on the spindle, wetted by rolling in a
  shallow tray, driven at surface speed equal to travel speed so that it does not drag on proofed dough;
  contact ≤ 0.3 N. Film 20–40 g/m², about 5–8 g of egg wash on a 20 × 30 cm braid.
* (b) **Nozzle raster or spiral** for viscous glazes (BBQ glaze, icing) and for cake glaze poured at
  60–70 °C inside the cake ring.
* (c) Silicone brush with compliance: M–H.
* (d) Spray of egg wash: raw-egg aerosol in the cell; rejected.
* Cleaning: sleeve and tray, class R ware when egg is used. Sensing: none; camera gloss check optional.
  Confidence H–M. Experiment: a silicone pastry roller or a smooth paint roller on proofed rolls against
  a brush; judge collapse and coverage after baking.
* Fallback: milk from a mister, or no glaze (matt crust). Cost 0.

### 6.4 Baste (BST, 9 meals)

* (a) **Spoon or ladle on the manipulator**, the roasting tin pulled out on the oven rail and tilted 5°
  by a wedge foot so that the jus collects in a known corner; 3–4 spoonfuls every 20–30 min, 20 s door
  time.
* (b) Steel syringe (SM-144) as a bulb baster; also removes fat. H–M.
* (c) **Self-basting by design**: vertical stand for birds (GA-17); lid or humidity (combi-steam) for
  roasts; rind of a crackling roast is *not* basted.
* Steak butter-basting: the pan is tilted 15° by lifting one side, foaming butter is spooned over at 1 Hz
  for 60 s.
* Cleaning: spoon. Sensing: none (pool position known from the tilt). Confidence H. Fallback: (c) alone,
  cost 0.

### 6.5 Fold (FLD, 11 meals; volume loss ≤ 20 %)

* (a) **GA-32 Fixed oblique blade in the slowly rotating bowl**: a spatula blade held at 45° rake from
  wall to centre floor while the bowl turns at 10–20 rpm lifts the bottom layer and turns it over; this
  is the hand fold with the motion moved into the bowl (hardware of SM-171). Shear rates below 5 s⁻¹.
  One third of the foam is stirred in first to lighten the base [K]. 15–25 turns.
* (b) Balloon whisk drawn through in 3–5 slow lifting strokes (chefs fold this way): M–H.
* (c) End-over-end tumbling in a closed vessel pair: heavy batter stays at one end; M–L.
* Cleaning: blade. Sensing: level before and after (camera or probe) with the mass gives density;
  streaks by camera. Confidence H–M.
* Experiment: bowl on a turntable ("lazy Susan"), spatula clamped to a stand; sponge batter; density by
  weighing a filled cup, against a hand fold.
* Fallback: whole-egg sponge with baking powder (adapted). Mousse (DS07) has no fallback: 1 meal at risk.

### 6.6 Rub fat into flour (RUB, 5 meals)

* (a) **Pulse the top-entering blade** (SM-024), 8–10 pulses of 1 s on fridge-cold diced butter in the
  flour: the food-processor method [K]. H.
* (b) **Grate cold butter into the flour** (SM-148, SM-035; 3–4 mm shreds are coated at once), then 20 s
  of slow mixing. H; needs no blade.
* (c) Wire pastry blender stamped repeatedly: M.
* Streusel: the rubbed mass is pressed through a 10 mm grid with its pusher (SM-009, SM-011) onto the
  cake.
* Fat must stay ≤ 15 °C. Cleaning: as the tool used. Sensing none. Confidence H. Fallback: melted-butter
  streusel (adapted), cost 0.

### 6.7 Cream fat with sugar (CRM, 7 meals)

* (a) **Top-driven beater or whisk** (SM-177) at 150–250 rpm for 3–5 min, butter diced 10 mm (SM-147) and
  tempered to 18–22 °C by 20 min at room temperature; a fixed scraper against the turning bowl wall.
  Above 30 °C the butter no longer holds air.
* (b) Roller and scraper in the rotating bowl (SM-171): H–M.
* Sensing: drive torque falls as the butter softens; an IR thermometer guards the temperature.
  Confidence H. Fallback: oil or melted-butter cake method (adapted; up to 7 meals against the 10 %
  budget, none lost).

### 6.8 Sift (SFT, 9 meals)

* (a) **Whisk the dry ingredients 20 s** (accepted modern substitute for sifting flour with leavening).
* (b) Flour dosed through a vibrated sifter lid is sifted by that act (SM-135, see 7.4).
* (c) Sieve disc on the bowl rim as an interposer, swept by the scraper: for icing sugar and cocoa.
* Confidence H. No fallback needed.

### 6.9 Dust with flour or icing sugar

* (a) **GA-33 Perforated dredger**: a cup with a laser-perforated sheet floor (holes Ø 0.8–1.0 mm, 30 %
  open; 0.5 mm for icing sugar), not woven mesh (wire crossings are crevices). Loaded and weighed in the
  dry corner, shaken by the manipulator at 5–8 Hz × 10 mm at 100–150 mm height in a raster: 20–60 g/m²
  ±30 %.
* (b) Dredging meat or fish: press both faces into a flour tray, shake off (first station of breading).
* Rule: a powder tool must be **bone dry**; it is stored in a warm holster and never used straight from
  the washer.
* Cleaning: dredger is cup plus welded perforated sheet. Sensing: mass before and after. Confidence H.
* Experiment: a flour dredger or tea strainer over a tray of weighed paper squares.

### 6.10 Skim (SKM, 2 meals; excluded by X-13 as adapted)

* (a) **Blanch and rinse the meat first** (start cold, boil 2 min, discard, rinse, restart): removes most
  of the scum at its source [K]. H.
* (b) **Weir ladle**: a ladle held level with its rim 2–3 mm below the surface; the top layer runs in.
  The surface is found by lowering until the camera sees inflow. Three dips take 70–80 % of a 3–5 mm
  fat layer [E]. M–H.
* (c) GA-34 Cold cup: a steel cup filled with ice water touched to the surface; fat freezes on, 5–10 g
  per dip on Ø 100, wiped off on a scraper. M.
* Fallback: none needed; unskimmed broth is already accepted (X-13).

### 6.11 Deglaze (DGL, 24 meals)

* Physics: a 1.5 kg pan at 200 °C holds 75 kJ above 100 °C and flashes up to 33 g of water into 56 L of
  steam in a few seconds [C]; water under hot fat spatters violently. 100 mL of wine carries 9.5 g of
  ethanol, 4.6 L of vapour [C]: harmless with the extraction running, and there is no flame in the cell.
* Rules: pan ≤ 160 °C; free fat ≤ 15 mL (pour or pipette the rest off); 20 mL first, slowly, at the wall;
  then 20–30 mL/s; lid or splash ring on; scrape the floor with a steel or PEEK edge at 10–20 N for 30 s.
* (a) **Liquid through the hub of a scraper lid** (SM-179) where the concept has one; (b) cup poured by
  the manipulator through a splash ring, then a flat spatula; (c) remove the meat, let the pan fall to
  130 °C, add liquid and simmer 1 min with stirring (gentlest, same result).
* Confidence H. Experiment: a pan on paper sheets; deglaze at 140, 180, 220 °C with 0, 15, 50 mL of fat;
  measure the spatter radius.

### 6.12 Rest dough, proof (RES, PRF, 11 meals)

* (a) **In the lidded working bowl at 30 °C** (oven proof mode or warm-hold drawer); end point by
  level: a time-of-flight or camera reading of the dome height in a straight-walled vessel gives volume
  ±5 %. Shaped pieces proof on their baking tray under an inverted GN tray as a hood (rule R1), which
  prevents a skin.
* (b) Cold proof 12–16 h in the cold store in a lidded box: H; a scheduler task.
* (c) Low induction power under a steel bowl: wall hot spots above 45 °C kill yeast; M, not recommended.
* If the oven is the proofer, the bake starts cold or the tray waits 8 min in the warm drawer.
* Confidence H. No fallback needed.

### 6.13 Score bread and meat (SCO, 7 meals; OK in the catalogue, details added)

* Proofed loaf: a thin blade (0.4 mm, serrated) at 30° to the surface, 5–8 mm deep, drawn at
  0.3–0.5 m/s, wetted; slow cuts drag and deflate the loaf. M–H.
* **GA-35 Water-jet scoring** (novel, worth the test): a Ø 0.3–0.5 mm jet of mains water at 4–5 bar has
  a stagnation pressure of 400 kPa against a dough yield stress near 1 kPa [C]; at 0.3 m/s traverse it
  uses about 1 mL per 150 mm of cut. No blade, no drag, nothing to wash, and the cut is wet, which helps
  it open. M (untested).
* Rolls: a stamp pressed in before the final proof [K]. H.
* Pork rind: steam or simmer the joint rind-down for 15–20 min first [K]; the softened rind then cuts at
  under 10 N with a blade in a depth shoe riding on the surface (SM-033), in a 10 mm diamond that becomes
  the carving pitch (GA-14). Raw rind needs 20–50 N and a very sharp edge. H.
* Experiment: a garden-sprayer pin nozzle or a syringe with a 0.4 mm needle on the tap against a razor
  blade, on two loaves.

### 6.14 Pipe, squeeze, extrude (EXT 3 meals, all Spätzle, two of weight 3; PIP 3)

* Spätzle, (a) **piston tube with a hole plate** (the ricer of SM-184 with a Spätzle die, holes
  Ø 2.5–3 mm) held 50–100 mm over the simmering pot; about 50 kPa, 250 N on Ø 80 [E]; 1.2 kg of batter in
  3–4 charges; the strands cook inside a lift-out basket and leave the pot in one lift. Steam cooks
  batter onto the plate: cold rinse within 2 min (rule R11).
* (b) **Perforated disc on the pot rim with a rotating wiper** (Knöpfle plane [K]; holes Ø 8–10): no
  pressure, uses the rotating lid where a concept has one. H–M.
* Cream and meringue: star nozzle ≥ 8 mm on the piston tube or a pouch squeezer (SM-149); cream is
  whipped in the tube it is piped from, so it is not transferred. H–M.
* Muffin batter: 60 g shots from the piston tube with 2 mm suck-back against drips. H.
* Cleaning: tube, piston, plate. Sensing: stroke and load cell. Experiment: a Spätzle press on a drill
  stand over a kitchen scale.
* Fallback for Spätzle: none acceptable (8 weight points); either (a) or (b) must exist.

### 6.15 Sprinkle garnish (GAR 37, TOP 24)

* (a) **Tap-dredger family** (GA-33 with holes of 1, 2.5 and 5 mm): weighed in the dry corner, emptied
  completely over the plate by taps of 5–10 g, inside the collar of GA-01 as a **rim mask** (SRV-005 c).
  Dose accuracy is the weighing accuracy; evenness is the raster.
* (b) Vibrated V-chute for seeds, croutons, fried onions. H.
* (c) Frozen crumbled herbs (SM-027) flow freely and thaw on hot food: H for hot dishes, not for cold.
* Fresh chopped herbs cling by water films: they must be spun to ≤ 5 % water before chopping; then M.
* Experiment: chopped parsley through a 5 mm perforated spoon tapped over black paper; photograph;
  variance of coverage.
* Fallback: one sprig placed with tongs. Cost 0.

---

## 7. Shared mechanisms that rest on an untested food result

### 7.1 Pan-pair flip with fat (SM-127, 6/6)

**What can go wrong.**

1. *Leak at the rim.* During the turn the free fat runs to the rim joint. For a gap h, wetted width
   150 mm, land 5 mm, head 20 mm of oil at 180 °C (µ ≈ 0.003 Pa·s): Q = wh³Δp/(12µL) gives 0.15 mL/s at
   h = 0.1 mm and 4 mL/s at h = 0.3 mm [C]. Flat rims lose drops; warped rims lose a spoonful of 180 °C
   fat onto the hob. Not an ignition risk on induction (auto-ignition is above 350 °C), but smoke, soil
   and a dry second pan.
2. *The item slides before it falls.* On a fat film µ is 0.05–0.2: the item starts to slide at 3–11° of
   tilt, reaches the wall, and tumbles over the joint. A pancake folds; a fish fillet breaks. Items that
   **fill the pan floor** cannot slide; small items can.
3. *The item sticks* to the first pan and tears when half of it falls.
4. *Large fat quantities.* Shallow-frying uses up to 250 mL (COK-021). Inverting that is the same class
   of hazard as inverting a full pot (rule R7).
5. *Mass.* A 36 cm pair with food is about 6 kg; held by one side handle that is 15 Nm on the wrist.

A trapeze swing (axis 250 mm above the pans, so that centripetal acceleration ≥ g holds food and fat on
the floor all the way) was examined and rejected: the content arrives at the top with 1.6 m/s tangential
speed and hits the wall when the swing stops [C].

**Improved rules** (the mechanism is kept):

| # | Rule |
|---|---|
| 1 | Pair-flip only with **free fat ≤ 30 mL**. More is taken off first with the steel syringe and given back afterwards. |
| 2 | Rim: a ground flat land ≥ 6 mm, flatness ≤ 0.1 mm, clamped with 50–100 N: leak below 1 mL per flip [C]. Better: the flip pan has a **drip skirt** that overlaps the frying pan's rim by 8–10 mm on the outside; after the turn the skirt points up and is a gutter that drains into the flip pan. The pair is then not symmetric: frying pan and flip pan are two parts. |
| 3 | Turn in 0.6–1.0 s about the diameter, the last 20° fast against a stop, over the hob position's own spill tray, never over open food. |
| 4 | **Release check before the turn**: a 5 mm horizontal jerk; the camera must see the item move freely. If not: wait 20 s, add 3 g of fat at the edge, or run a thin blade round the edge. |
| 5 | Second pan within 20 K of the first, with a 3 g fat film. |
| 6 | Whole-pan items (pancake, omelette, Rösti, tortilla, quesadilla) in **shallow** pans (wall 12–15 mm), so the fall is ≤ 25 mm. Small loose items (patties, steaks, cutlets) are turned singly (SM-129) or accept a tumble. |
| 7 | Trunnion support on both sides for the 36 cm pair. |

**GA-36 Lift-rack turn for fat above 30 mL** (Schnitzel, Backfisch, fried chicken, falafel): the items
lie on a flat perforated rack in the fat; a second rack is set on top; the pair of racks is lifted,
drained 5 s over the pan, turned 180° in air and lowered again (fish-grill basket principle [K], without
the hinge). Only drips move, and they fall back into the pan. Cost: rack marks in the crumb coat.
Confidence M–H.

Alternatives: two-sided contact heat or top heat (SM-132; adapted); a wide turner with pan tilt for
pancakes (D rates it doubtful).

Confidence: M–H for whole-pan items under the rules above; the 70–80 % first-time figure is a guess
until tested.

Experiment (30 EUR): two identical crêpe pans, oven gloves, a sheet of baking paper under the work as a
leak catcher, weighed before and after. 20 pancakes, 5 Rösti, 5 tortillas; repeat the Rösti with 10, 30,
60 and 100 mL of oil; slow-motion video of the fall. Records: leaked fat in grams, folded or torn items,
stuck items.

Fallback: top heat for thick items, two-sided contact for pancakes; adapted, 0 meals lost.

### 7.2 Equator-scored egg opening (SM-164, 5/6) — replace

**Assessment.** The idea copies glass cutting: scribe, then pull. It does not transfer.

* Shell is 0.35–0.40 mm of porous calcite on a tough 70 µm membrane. Tensile strength about 15–20 MPa;
  the section at the equator is π × 44 × 0.37 = 51 mm²; pulling the halves apart axially needs
  **770–1000 N** [C]. A Ø 25 suction cup at −0.6 bar holds 29 N [C]. A scratch 0.05–0.1 mm deep does not
  close that gap; the cups let go first.
* It works only if the score is a **through-cut or a perforation** all round, which makes chips and dust
  at every tooth — on the outside of the shell, the contaminated side.
* With the axis vertical the lower half-shell is a full cup and does not empty; with the axis horizontal
  the halves must also be tilted.
* Vacuum cups on cold, wet or soiled shells leak; a broken egg is sucked into the line.
* What opens an egg with little force is **bending it open about a local crack**, with the membrane on
  the far side as the hinge. That is the conventional cracker and the human hand.

**Recommended:** the blade-and-spread kinematics (SM-165; consumer crackers and industrial breakers
[K]): egg lying in a two-part cradle, one upward strike of a blade with 0.05–0.1 J through the bottom
third, the two cradle halves swing apart about an axis above the egg, contents fall, shells stay in the
cradle and are tipped to waste. Built as a loose cassette; its two pivots are open pins that fall apart
for washing (the one deliberate breach of the shape rule). Then:

* Every egg goes into its own **dark saucer on the small scale** (SM-168): the camera sees white shell
  fragments ≥ 1 mm and a broken yolk.
* **Beaten-egg uses** (batters, scrambled, baking: the majority): the beaten egg is poured through a
  1.5–2 mm perforated plate, which holds fragments and chalazae. This meets "no fragment > 1 mm"
  independently of the cracker.
* **Fried egg**: an egg with a fragment or broken yolk is diverted to the mixture stream; expect 2–5 %
  [E].
* Cleaning: cassette and saucer are class R ware, cold rinse at once. Sensing: camera. Confidence H.

Experiment (30 EUR): 60 eggs, white and brown, cold and at room temperature. (1) a hand cracker of the
blade-and-spread type; (2) equator scored with a glass cutter or rotary tool, pulled with two suction
cups; (3) the same score, opened by bending. Each into a black plate: fragments ≥ 1 mm, yolk intact,
seconds, mass of white left in the shell.

Fallback: liquid pasteurised egg for mixtures (permitted, MEAL-012 a); shell eggs only for boiled and
fried. Cost 0.

### 7.3 Egg separation (SEP, 17 meals, priority S)

* (a) **One-piece slotted saucer** under the cracker (industrial principle [K]): the yolk (Ø 32–36) sits
  in a Ø 40 dish with an annular slot of 4–5 mm; 15° tilt, 3 s, two small shakes to cut the thick white.
  **One egg per cup**: the white of each egg is inspected in a clear cup (a yellow streak is visible)
  before it joins the others, because one trace of yolk spoils a whole foam. White yield 85–90 %; the
  recipe takes whites by grams (SM-151).
* (b) Slotted ladle lifting the yolk out of a shallow dish, guided by the camera (the hand method): M–H.
* (c) Suction tip (bottle trick): raw egg inside a tube; 5–10 % broken yolks with older eggs. M.
* (d) Tilted half-shell: L–M.
* Cleaning: saucer is a pressed dish with a slot (shape rule kept). Sensing: camera. Confidence M–H.
* Experiment (10 EUR): 30 eggs, a slotted separator, clear cups; count yolk breaks and yolk traces; weigh
  the whites; whip the pooled white and measure volume.
* Fallback: carton egg white for foams; whole egg instead of yolk in carbonara and mayonnaise (adapted);
  hollandaise and crème brûlée then at risk: up to 3 meals adapted, none lost if carton yolk is
  unavailable only for these.

### 7.4 Powder through a vibrated mesh in humid air (SM-135, 3/6)

**Assessment.** The principle is sound: flour has an unconfined yield strength of 0.2–1 kPa, which
bridges openings of about 100 mm [C: 2f/(ρg) with ρ = 500 kg/m³], so it sits firmly on a 1–2 mm mesh and
runs only while vibration breaks the arches. The threat is less the relative humidity than **dew**:

* A box at 18 °C brought into cell air at 30 °C and 70 % RH (dew point 24 °C) condenses water on its
  mesh [C]. Flour plus water is paste; the mesh blinds in a few cycles.
* Without dew, flour at 75–80 % RH gains moisture within minutes at the exposed layer; cohesion doubles
  or triples [E]; flow per second falls, the principle survives.
* Salt deliquesces at 75 % RH, sugar at 84 %: crusts on the mesh. Free-flowing crystals dribble through
  any mesh wide enough for flour; they need another lid (conflict X1).

**Improvements.**

1. **Dry dock purged with cold-store air.** Air from the refrigerator has a dew point of 2–5 °C; warmed
   to cell temperature it is at 20–25 % RH [C]. 1–2 L/s into a dosing dock of about 5 L keeps the mesh
   dry at no energy cost beyond a small fan. (Interface to the cold store: a Ø 20 air duct.)
2. **Dry-goods boxes stored at or above cell temperature**, never colder.
3. Mesh uncovered only for the 10–30 s of dosing (shutter, BOX-007).
4. **Perforated sheet, holes Ø 2–3 mm**, instead of woven 1 mm mesh: tolerant of small lumps, no wire
   crossings, still far below the bridging span.
5. A closing tap (one 20 g knock) sheds the hanging layer.

**GA-39 Core tube** (plain-box alternative). A thin-walled tube Ø 40 is pushed 80 mm into the powder;
cohesive powder stays in it by wall friction; a piston ejects it over the cup. One core of flour is about
55 g; the trim is a partial core or the dredger. The more cohesive the powder, the better it works, so
humidity helps rather than hurts. It needs **no dosing lid** and so avoids conflict X1. Not for
free-flowing crystals (they pour). Cleaning: tube and piston, dry-brushed, washed weekly and dried warm.
Confidence M–H.

Dock tilt-pour with vibration (SM-133) stays the coarse method: avalanches of 5–10 g, trimmed by scoop.

**Recommended:** sifter lid (perforated sheet) only together with the dry dock and warm boxes; the core
tube as the baseline if the box standard does not allow special lids. Confidence M–H in the dry dock,
L–M in unconditioned cell air.

Experiment (20 EUR): a flour dredger with a 1.5 mm mesh and one drilled with Ø 2.5 holes, an electric
toothbrush or a phone vibration motor, a 0.1 g scale. Matrix: room air; 30 s held 0.3 m above a simmering
pot, 20 cycles; jar pre-chilled to 8 °C (the dew case). Measure g/s, dribble after stop, blinded area.
Repeat with icing sugar, cocoa, paprika, salt, sugar. For GA-39: a piece of Ø 40 tube and a dowel.

Fallback: tilt-pour and scoop. Cost 0 meals; accuracy ±5 g on flour, which the recipes tolerate.

---

## 8. Parts added and what they share

| Part | Used by |
|---|---|
| Peel 140 × 200 and long peel 300 × 100; fixed stripper bar | GA-01, GA-07, GA-24, carving fan, whole fish, Rouladen plating |
| Collars (round, square), cake ring | assembly, garnish rim mask, glaze |
| W-rack | taco, hot dog, pita, shell baking |
| Plough rails on the loop roller | burrito, Rouladen side fold, cabbage roll, ham-wrapped cheese |
| Crimp frames (U and closed), ridge tray | cordon bleu, turnovers, gyoza, samosa |
| V-trough with follower and drawbridge; twin blade | carving, scoring datum, roast cage |
| Comb cradle with guide slots; hairpin fork; stripper comb | Rouladen |
| Vertical split stand, two funnels, halving blade | roast bird (optional upgrade) |
| Knurled roller and retard lip; peel drum | slices |
| Wide and narrow tongs; V-tray | leafy goods, spaghetti |
| Perforated dredgers (3 hole sizes); silicone roller sleeve; slotted saucer; egg cassette; weir ladle; core tube | finishing, egg, powders |

About 30 small passive parts. Rule 11 of the catalogue's risks applies (part count); the parts used by
under 1 % of meals are the vertical stand set, the wire-edged peel and the peel drum.

## 9. Open issues

1. **Rouladen test first.** The three-group braise of 4.2 decides whether the hairpin raft is needed or
   whether the dry, floured flap is enough. It costs one afternoon and should run before round P3 ends.
2. **"Served as components"** (SM-244) needs a customer ruling for tacos and burritos; this document
   assumes the machine assembles them.
3. **Adapted-method count.** This document adds candidates for the 10 % budget: DM20 as parts or with
   liquid aromatics, FI07, gyoza and samosa shapes, creamed cakes by the oil method if creaming fails,
   whole-egg recipes if separation fails, top-heat flips. Someone must keep the single count the
   catalogue asked for (its issue 7).
4. **Ownership.** The carving trough, basting, deglazing, skimming and the flip rules sit on the border
   between preparation, cooking and serving; the build spot with its load cell is a plating station.
5. **Requests to ingestion and the box standard:** spaghetti and lasagne sheets loaded aligned and flat;
   sliced goods kept as the pack's stack in a tray; a whole bird checked for its leg loop; an air duct
   from the cold store to the dosing dock.
6. **Twin blade hygiene**: separating the two blades for washing, or a single blade with equal cutting
   quality, is unresolved.
7. **Loading a raw bird onto the vertical stand** is the weakest step in the document; without it GA-17
   and cavity filling by gravity do not exist and the bird is roasted as parts.
8. **Net and string removal** from bought tied roasts was not on anyone's list; it is needed wherever
   "buy tied" is the answer.
9. **Filo and strudel sheets**, de-nesting of paper muffin cups and bought taco shells remain unsolved
   and are avoided by substitution.
10. Numbers marked [E] are mine and unmeasured; the [C] figures follow from them. Forces for cutting
    cooked poultry bone, seam bond strength and slice adhesion are the least certain.
11. Not read for this document: the P3 concept files in `design/prep/concepts/`; requirements outside
    section 5 only where cited.

## 10. Risks

| # | Risk | Consequence | Mitigation |
|---|---|---|---|
| 1 | The hairpin raft tears tender rolls when they are pushed off after braising | the brief's named meal is served damaged | push off onto the peel while still in the sauce-wet state; tines polished; fallback single pins with inductive count-out |
| 2 | Seam-angle control fails and the skewer misses the flap | a free flap tail, cosmetic | flap is under the roll; two tines give two chances; test group C |
| 3 | Limp slices fold or stick on the peel at the stripper bar | assembly of sandwiches and burgers fails at the most frequent step | bar lowered to 1 mm; peel surface finish; inverse build (GA-05) as fallback |
| 4 | Side folds spring back before the loop closes | burritos and Rouladen with open ends | warm tortilla; hold-down roller between plough and loop; enchilada-style fallback |
| 5 | Braised meat tears in the overhang cut despite the drawbridge | DM07, DM08, DM29 served as broken slices | thicker slices (10–12 mm); chill-slice-reheat |
| 6 | Crimped cordon bleu leaks cheese in more than 10 % of pieces | blemished result, soiled pan | colder cheese core, wider margin, two-cutlet variant |
| 7 | Shear dealer delivers doubles or tears with thin ham and warm cheese | slow assembly, waste | mass check and return; slice from the block |
| 8 | Hot fat leaks at the pan-pair rim in spite of the rules | smoke, soiled hob, dry second pan | drip skirt; syringe the fat off first; lift-rack turn |
| 9 | The conventional egg cassette cannot be cleaned to class R standard at its pivots | raw-egg residue | pivots as open loose pins; cassette fully dismantled in the washer; verify by riboflavin test |
| 10 | Cold-store air purge is refused by the cold-storage module (door, energy, odour transfer) | sifter lids blind in humid cell air | core tube and scoop as the plain-box method |
| 11 | Part count grows by about 30 passive parts | wash capacity and tool store exceeded (PRP-003, CAP-030) | drop the parts used by < 1 % of meals; share fixtures as in section 8 |
| 12 | Several recommendations are recipe adaptations and spend the 10 % budget unnoticed | MEAL-013 exceeded | single count (open issue 3) |
| 13 | All figures are paper estimates | confidence ratings wrong in either direction | the ten bench experiments listed per section cost about 300 EUR together and two to three days |
