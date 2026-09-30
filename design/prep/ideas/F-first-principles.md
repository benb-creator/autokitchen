# P1-F — Preparation ideas from first principles (and wild cards)

Round P1 (idea finding), lens F: forget how cooks and existing machines do it, ask what each operation
physically *is*, and take the simplest mechanism that does that. Written without reading the other P1 files.

Inputs used: `BRIEF.md`, `DECISIONS.md`, `PLAN.md`, `requirements/requirements.md` (sections 3.5, 5, 7),
`research/01`, `02`, `04`, `06` (and the box family of `03`).

Tags: **[E]** = my estimate or calculation (derivation shown so it can be redone); **[R4]**, **[R6]**, **[R2]** = taken
from that research file; **[K]** = general knowledge of existing industrial or household practice, not verified
in this session. Nothing here has been built or tested. Every force, time and yield below is a paper number.

Contents: 0 summary · 1 first-principles table · 2 assumptions common to all concepts · 3 four whole-system
concepts (A TUCH, B SÄULE, C TROMMEL, D ZUSTAND) · 4 check against the meal corpus · 5 recipe reordering ·
6 standalone sub-mechanisms (37) · 7 the bet · 8 open issues · 9 risks.

---

## 0. Summary

1. Three observations fall out of the physics and drive everything else:
   * **Cutting firm food is a solved, low-energy problem** (2–5 N per mm of edge, a few joules per cut [R4]). The
     unsolved operations are the ones on *limp, sticky or sheet-like* food: meat slices, mince, dough, breading,
     Rouladen. R2 confirms it: the shaping cluster blocks 15.3 % of meals and has no commodity purchase
     workaround; flipping 12.9 %, assembly 6.9 %, carving 4.8 %, unmoulding 4.4 %.
   * **A rigid tool cannot be pulled off sticky food, but a flexible one can be peeled off.** Peeling needs a
     force per unit *width*, not per unit *area*. This is why cooks use cling film, baking paper, cloths and
     sushi mats for exactly the operations that robots fail at.
   * **Stiffness is a process variable.** Two to four minutes on a −25 °C contact plate turns a meat slice or a
     mince patty into a rigid part (section 3.4, Plank calculation); 100 °C turns a bonded skin into a loose one.
     Change the state first and the mechanics become trivial.
2. Four concepts, each built on one physical principle:
   * **A TUCH** — a reversible reel-to-reel *mat* is conveyor, work surface, kneading cloth, rolling mat, tossing
     sling and mould. The mat is the only surface that sees sticky food, and a flat mat is the easiest object in
     the world to wash.
   * **B SÄULE** — one vertical ram pushes food through a revolver of fixed dies; the grid that makes cuts 1
     and 2 is the fixture for cut 3. Food only ever falls; the unused half of the revolver sits in a wash box.
   * **C TROMMEL** — one two-axis drum with liners and stators: washing machine, peeler, spinner, tumbler,
     kneader, centrifugal slicer. Centrifugal force is the workholding.
   * **D ZUSTAND** — a cold plate and a steam/blanch step placed *before* the mechanics; everything soft is
     handled frozen-firm as a rigid body, every bonded skin is removed after heat.
3. I would bet on **A, carrying B's die head as its dicer and D's cold plate as a booster** (section 7).
4. Best three sub-mechanisms: **S6 grid-as-fixture dicing**, **S14 loop roller for Rouladen**, **S17/S18
   cold-plate tempering and ice-cube-tray forming**. Cheapest big win: **S31 salt as brine**.

---

## 1. First-principles table

| Unit operation | What it physically is | Simplest physical ways to do it |
|---|---|---|
| Cut (slice, dice, strip) | Create new surface by fracture at an edge. Energy is tiny (2–10 kJ/m² [R4]); the problem is *holding the piece while the edge passes* | (1) Push through a fixed grid — the grid holds the piece (S6). (2) Draw-cut with a fast thin edge so that the normal force and therefore the holding force go to zero (band knife, S38). (3) Let inertia hold the piece: centrifugal slicer (S27) |
| Fine chop, mince herbs | Much new surface on thin, limp material that cannot be pushed | (1) Compress into a bundle, then slice the bundle 1–2 mm (column). (2) Blade against a soft anvil, many strokes (mezzaluna on the mat). (3) Make it brittle: freeze, then crush (S19) |
| Peel firm produce | Remove a 1–2 mm shell from an irregular body | (1) Shape-agnostic abrasion (drum, sling). (2) Make the body regular instead: broach a prism out of it and discard the rest (S9). (3) Weaken the bond first: cook, then slip or retain the skin (S12, S13) |
| Peel onion | Remove a dry shell that is attached only at the two poles | (1) Cut both poles, slit one meridian, then apply tangential shear: water or air jets, rollers (S11). (2) Blanch 60 s and tumble against rubber fingers (S12). (3) Do not: buy peeled [R2: level-1 purchase, 52 % of meals] |
| Trim ends, core, deseed | Remove a part defined by anatomy | (1) Orient, then first-and-last slice to waste. (2) Cut first, separate after by size or density (seeds through a 6 mm sieve, S37). (3) Axial punch after self-orientation (S26) |
| Wash | Transfer soil from a surface into water and carry it away | (1) Flotation: soil sinks, leaves float to a weir (S37). (2) Spray on a perforated carrier. (3) Wash in the cooking pot and suck the water out (S41) |
| Dry (salad) | Separate surface water from solid | (1) Centrifuge, 40–110 g [R4]. (2) Air knife. (3) Shake in a cloth |
| Mix | Reduce the scale of segregation | (1) Tumble: gravity does it, no tool (drum, loop). (2) Divide and recombine (fold, push through a perforated plate). (3) Shear with a moving boundary (stirrer) |
| Knead | Stretch and fold a gluten network; about 10–25 kJ/kg | (1) Roll flat and fold, repeatedly — the pasta-sheeter method [K]. (2) Rotating bowl against a fixed roller [R4]. (3) Squeeze in a closed pouch (lab "stomacher" paddle blender [K]) |
| Whip, emulsify | Create gas–liquid or liquid–liquid interface | (1) Wire moving at 2–3 m/s through the liquid. (2) Rotor–stator. (3) Force through an orifice repeatedly (two-syringe method) |
| Mash, purée | Rupture cooked tissue without shearing starch | (1) Push through 3 mm holes (ricer, retains skins). (2) Crush in a nip with a mesh belt (S13). (3) Slow roller in a rotating bowl |
| Form a paste (patty, ball, dumpling) | Give a shape to a yield-stress material and then get it off the tool | (1) Extrude and cut off. (2) Fill a mould, then *change the state* so it releases (S17), or peel the mould away (mat). (3) Core it out of the bulk with a tube (S4). (4) Portion, then round by tumbling |
| Flatten meat | Plastic flow of a thin slab | (1) Calender between rollers (what industry does [K]). (2) Platen press 0.5–1.5 kN [R4] |
| Coat, bread | Adhere particles to a wet surface; remove the excess | (1) Tumble item and particles together. (2) Lay on a bed, sprinkle, press, flip. (3) Dip a rigid (frozen-firm) item into each medium |
| Roll a Roulade | Wrap a limp sheet 1.5–2 turns round a filling and keep it shut | (1) Belt loop: pulling one side of a slack loop makes the content roll (cigarette and dolma rollers [K], S14). (2) Drape into a U-cradle, fold the flaps. Fixing: (a) pin (S15), (b) freeze the seam (S16), (c) sear seam-down first |
| Roll out dough | Reduce thickness by plastic flow | (1) Nip roller over a moving belt. (2) Platen press. (3) Spin: centrifugal stress ρω²R² (S47) |
| Flip | Expose the other face to the heat | (1) Sandwich between two pans and rotate the pair (S20). (2) Transfer over a nose bar onto a lower surface (S21). (3) Do not flip: heat both faces |
| Drain | Separate free liquid from solids | (1) Remove the liquid, not the solids: suck it out through a strainer tip (S41). (2) Lift a basket. (3) Pour through a perforated mat |
| Press out liquid | Squeeze a porous mass | (1) Mangle: mesh belt through a nip (S13). (2) Centrifuge |
| Crack an egg | Open a brittle shell and let gravity empty it, keeping fragments out | (1) Hold both ends by vacuum, score the equator, pull apart (S22). (2) Cut the cap off and invert (egg topper [K]) |
| Separate an egg | Yolk is a coherent membrane-bound sphere, white is a liquid | (1) Suck the yolk out with a soft wide tip (bottle trick). (2) Slotted cup |
| Dose granules | Meter a mass flow | (1) Hourglass: orifice flow is constant and independent of fill level (Beverloo; S1). (2) Tilt, vibrate and weigh [R4] |
| Dose cohesive powder | Same, but the powder arches | (1) Mesh that holds the static arch and passes powder only while vibrated (S2). (2) Dissolve it: dose as a liquid (S31) |
| Dose liquid | Displace a volume | (1) Air-displacement pipette, only the tip is wetted (S3). (2) Mains valve + flow meter for water |
| Dose paste, fat, mince | Displace a volume of a material that does not flow | (1) Core tube with ejector (S4). (2) Piston cartridge. (3) Squeeze a pouch through a nip |
| Transfer limp or sticky things | Move without relative sliding at the contact | (1) Conveyor nose: the surface is pulled out from under the item (S21). (2) Make the item rigid (S18). (3) Clamshell scoop (S5) |
| Pour | Move mass with gravity | (1) Let it fall straight down from where it was made (column). (2) Convey over a nose. (3) Reverse a helix (S28) |
| Unmould | Break adhesion between product and mould | (1) Peel a flexible mould off the product. (2) Melt a 50 µm film by a heat flash (S17). (3) Flex or blow |

---

## 2. Assumptions common to all four concepts

So that the concepts can be compared, all of them use the same base. Items marked S.. are described in section 6.

* **Boxes**: GN 176 mm family in PP or Tritan (1/9, 1/6, 1/3) [research/03]. Boxes have draft, so they cannot be used
  as piston cartridges; where a concept needs a prismatic cartridge it is a separate *process sleeve*.
* **Dosing dock** at the storage hand-over, dry and away from steam [R4 9.3]: a 2-axis box tilter with a
  vibrator; lids S1 (hourglass) and S2 (mesh valve); pipette S3 for liquids; core tube S4 for pastes, fats and
  mince; two load-cell ranges [R4]. Salt is dosed as brine (S31).
* **Egg module** S22 (crack, inspect in a clear cup, commit or discard; yolk suction for separating).
* **At the hob** (cooking module, but in scope as "handling during cooking"): double-pan flip S20, venturi
  drain wand S41, spin-coat for thin batter S47, smash-forming in the pan.
* **Ware wash**: the pass-through wash chamber recommended by R6 (480 × 480 × 400 mm, programme P1 17–20 L,
  55–75 min). Each concept states what it sends there and what it cleans in place instead.
* **Vessel sizes from R2**: mixing 8–10 L working (salad 5 L, dough rising to 4–5 L, mince mass 1 kg), boil pot
  9 L, pans 280 and 360 mm, braiser 320 × 240 × 110 mm. Pieces up to Ø 130 mm (M) and Ø 220 mm (S) [PRP-020].
* **Hygiene rules taken as fixed**: no FDM in Zone F (DEC-4); no drives above open food unless under a
  drip-proof hood (HYG-004); rotary shaft seals are acceptable, linear slots through a wet wall are not (R6);
  thermal disinfection A0 ≥ 60 after class R food (HYG-021). A0 = Σ 10^((T−80)/10)·Δt: 80 °C for 60 s, or
  90 °C for 6 s, or 100 °C for 0.6 s. **Thin parts reach these temperatures in seconds; this is the hidden
  advantage of membranes and thin dies.**

---

## 3. Concepts

### 3.1 Concept A — TUCH: the shuttle mat (membrane lens)

**Core idea.** A reinforced food-grade mat (440 mm wide, about 1.4 m long) runs reel-to-reel between two smooth
bars, across a small fixed table and under a rail of fixed tools; it shuttles the food back and forth under the
tools like a reversible production line 0.9 m long. When the second bar swings towards the table the mat goes
slack and hangs as a *loop* between two fixed cheek plates: a trough with a moving wall, in which food is
tumbled, tossed, folded, kneaded and rolled up. The mat is the only surface that touches sticky food, it is
peeled off the food instead of the food being pulled off it, and it washes itself by running through a spray
and steam section on the way back.

```
 FRONT VIEW. X to the right, Z up. Everything is uniform over Y = 440 mm ("extruded" into the page),
 so every moving part is a bar cantilevered from the back wall and every drive is a rotary shaft
 through that wall. The dry drive room is 100 mm deep behind the wall.

  box dock        fixed tool rail (tools hang from back-wall shafts, under a drip hood)
  (tilt, dose)     D        P        R        K        H
      |         shaker   pipette   roller   blade   die head (S6): dice fall on the mat
      v            v        v        O        |
  (A)========================================(E)~~~~~~~~~~~~~(B)      z = 0, mat top, 900 above floor
  reel A        fixed table 360 x 440        edge   bridge    reel B on a crank, R = 220
  dia 30        = anvil under R and K        roller   \         \
  on a crank                                 dia 30    \_______/   LOOP mode: B swings in, the slack
                                                       loop zone    hangs between cheeks at Y = 0 / 440
  |<-- 120 -->|<----------- 360 ----------->|<----- 260 ----->|
                                            [ sink, strainer,   ]     [ pan / pot / tin ]
                                            [ spray + steam bar ]      NOSE mode: B swings out and
                                                                       down, winds in, food falls off
  bay: 900 wide x 600 deep x 650 high; mat magazine (10 mats hanging) on the left, 150 wide
```

**Primitives.** Everything A does is a combination of five moves:

| Primitive | How | Used for |
|---|---|---|
| SHUTTLE | Wind on A or B; food passes under a fixed tool | Dosing in rows, flattening, rolling out, slicing, scoring, spreading |
| LOOP | B swings in; winding circulates the slack loop, contents roll over themselves | Tossing salad, mixing mince mass, folding dough, breading, rounding, rolling Rouladen, washing under the spray |
| NIP | Roller presses on the mat over the table, gap 0–60 mm, up to 600 N | Rolling out, flattening meat, kneading (with LOOP), crushing, pressing crumbs on |
| NOSE | B swings out and down and winds in; the mat is pulled from under the food | Transfer of anything into pan, pot, tin or onto another surface without sliding; flips the item if wanted |
| CHOP | Blade against the mat on the table while the mat jogs | Slices 1–20 mm, trimming ends, scoring, chopping, portioning logs, carving |

**Kinematics and actuators.** Reel A: crank + spin. Reel B: crank + spin. Roller: press (free-rolling). Blade: one
stroke axis, guided by posts in both cheeks. That is **6 rotary drives** for the mat line, all through rotary
seals in the back wall. The die head (S6) adds 3 (ram, die slide, face blade). A whisk/blender spindle over a
separate rotating bowl handles liquids (2). Box tilter 2. **Total 13** [E]. Spin drives 20 Nm (pulling 1.6 kg of dough through
the nip needs about 300 N at a wound radius of 40 mm = 12 Nm [E]). Mat tension 300 N over 440 mm is
0.7 N/mm, which a plain silicone sheet would answer with about 30 % stretch, so the mat needs a fabric core.

**Mats (the vessel set).** Hem rods of ferritic steel at both ends snap onto magnets set in a flat of each bar;
after 1.5 turns capstan friction holds (e^(μθ) = e^(0.6·3π) ≈ 280 [E]), so the bars stay plain cylinders.

| Mat | Material | Use |
|---|---|---|
| M1 | Glass-fabric reinforced silicone, 1 mm, sealed edges (the material of baking mats [K]) | General: dough, mince, breading, tossing, Rouladen |
| M2 | Homogeneous TPU belt, 1.5 mm (positive-drive food belts of the meat and dairy industry [K]) | Cutting anvil, raw meat, carving |
| M3 | M1 perforated, 3 mm holes, 30 % open | Wash and drain produce, drain pasta poured through it, steam |
| M4 | Stainless or polyester mesh belt, 3 mm and 0.5 mm | Mangle ricer and wringer (S13), straining |
| M5 | Stainless rasp sheet on TPU (no loose grit) | Abrasive peeling in LOOP mode |
| M6 | M1 with moulded cavities (6 × Ø 70 × 25; hemispheres) | Patties, dumplings, unmoulding by peeling the mat away |

Rigid ware: the 8–10 L rotating bowl with small insert, pipette tips, core tubes, dies. A loop 250 mm across and
200 mm deep over 440 mm holds about 17 L [E], so the loop itself is the large mixing vessel for solids.

**Dosing and moving, by ingredient form.**

| Form | From the box | Onward |
|---|---|---|
| Whole produce | Tilt-singulate over the box lip onto the mat; count by load-cell steps and camera | SHUTTLE to blade or die head |
| Leafy | Tilt and shake into the loop on M3 | LOOP under spray, then roll-up spin (below), NOSE into the bowl |
| Granular | Hourglass lid S1 straight into the pot; or onto the mat if it is to be mixed in | NOSE |
| Powder | Mesh-valve lid S2, as a row on the mat or into the bowl | LOOP folds it in |
| Liquid | Pipette S3 into bowl or pot; onto the mat only as a spread or drizzle | — (the mat is not a liquid vessel) |
| Paste, fat | Core tube S4; spread by the roller at a 2 mm gap | — |
| Raw meat | Block: SHUTTLE to the blade, slices are created one at a time. Bought slices: needle pad or S21 | NOSE into the pan |
| Egg | Egg module, then pipette or pour into the loop content or bowl | — |
| Frozen | IQF as granular; blocks crushed in the NIP inside a folded mat | — |

**The hard operations.**

| Operation | How A does it | Confidence |
|---|---|---|
| Peel potato, carrot | LOOP on rasp mat M5 under spray: a drum peeler without the drum. Relative speed 0.3–0.5 m/s, so slower than a drum: 4–6 min per 1.5 kg [E]. Or cook first and rice through M4 | Medium |
| Peel onion | CHOP the two ends (vision finds them), slit one meridian 3 mm deep, LOOP on M1 with the roller at light pressure (the garlic-tube principle) plus water jets (S11) | Medium-low |
| Dice onion | Halves through the die head, 6 or 8 mm grid, face cut every 6–8 mm (S6) | High |
| Mince herbs | CHOP: 60–80 strokes in 30 s while the mat jogs ±15 mm; or cryo-crumble (S19) | High |
| Crack egg | Egg module S22 | Medium-high |
| Frikadellen | Mince, soaked roll, egg, onion, brine onto M1; 30–40 LOOP/NIP cycles (90 s); roll to a Ø 60 log in the loop; CHOP into 30 mm pucks (100 g); NOSE into the pan; press to shape there. Or mat M6 | High |
| Rouladen | Slice on M1 (created by the blade from a tempered block, or laid by S21); NIP to 5 mm; mustard dots from the pipette, spread by the roller at 1 mm gap; bacon, gherkin spear, onion placed at the leading edge; LOOP sized to 160 mm circumference rolls it up (S14); pin (S15) pressed in by the blade axis carrying a pin driver, or seam-down NOSE into the hot pan | Medium-high for the roll, medium for the fix |
| Bread a Schnitzel | NIP to 6 mm (wet roller); flour row from S2; LOOP 3 turns; 40 g beaten egg from the pipette; LOOP; 50 g crumbs; LOOP; NIP at thickness + 1 mm presses the crumb on; NOSE into the pan. One cutlet per 60–90 s. All in one "bag", so flour must be dosed to what adheres (about 8 g) | Medium |
| Knead, roll out | LOOP folds, NIP flattens to 15 mm, repeat 40–60 times (3–5 min for 1 kg [E]); proof in the loop under a cover; roll out by SHUTTLE at falling gap to 2–10 mm ± 0.5; NOSE onto the tray | High: this is a sheeter |
| Mash | Boiled skin-on potatoes in folded M4 (3 mm mesh) through the NIP at 2 mm: flesh goes through into the pot, skins stay in the fold (S13) | Medium-high |
| Toss salad | LOOP, 5–10 slow circulations with the dressing added from the pipette | High |
| Dry salad | Roll the leaves up in M3 around bar B and spin the roll at 600 rpm (r = 60 mm gives 24 g) for 2 × 15 s | Medium (imbalance, compression of leaves) |
| Flip steak, pancake | Not in the bay: S20 at the hob. NOSE transfer can lay a pancake into a second pan face down | — |
| Drain pasta | S41 wand, or pour through M3 over the sink | High |
| Carve a roast | SHUTTLE on M2 with the roller as hold-down, CHOP at 2–15 mm; slices stay shingled on the mat; NOSE onto the plates | High |

**Cleaning and drying.** (1) *The mat*, after every use: it is reeled from B to A and back through the sink
section: cold pre-rinse bar, scraper blade on the edge roller, recirculated 55 °C detergent spray from both
sides (8 flat-fan nozzles at 40 mm, every square centimetre passes a nozzle, so there are no spray shadows by
construction), fresh-water rinse, then a steam bar. At 20 mm/s a point spends 5 s in a 100 mm steam slot and
reaches more than 90 °C because the mat is 1 mm thick: A0 > 60. Heating 0.6 kg of mat by 80 K costs about
60 kJ (17 Wh, 25 g of steam) [E]. An air knife and the mat's own heat dry it in one more pass. About 3–4 L
and 3–4 min per mat [E], against 17–20 L and an hour for a chamber load. (2) *The bars* are washed over their
whole length when the mat is unwound. (3) *Fixed Zone F parts* — table, two cheeks, roller, blade, edge roller,
about 0.45 m² [E], all flat plates or plain cylinders — are washed in place by fixed nozzles; the roller and
reels rotate under the spray. The bay drains through the sink strainer to the organic waste. (4) *Dies, tips,
bowl, core tubes* go to the wash chamber. (5) Silicone takes up onion, fish and curry odour (HYG-025): mats are
baked out at 150 °C in the oven cavity when a sniff-proxy or a use counter demands it, and M2 (TPU, which I expect to take
up less [K, to verify]) is used for the smelly jobs. Mats are wear parts: planned exchange by the human about once a
year, like the detergent.

**Off-the-shelf / custom.** Off-the-shelf: mat materials by the metre, gearmotors, rotary seals, spray nozzles,
steam generator, load cells. Custom: mats with hems (sewn/vulcanised, moulded cavities for M6), cheeks, table,
blade guide, the control of slack length.

**Novel.** A reversible mat as the *universal vessel and hand* of a kitchen; the loop as a drum with a flexible
wall; reel-through cleaning with steam disinfection of a thin film; a whole prep cell that is two-dimensional.

**Biggest weakness.** The mat itself. Nobody knows how a reinforced silicone or TPU mat behaves after 2 000
cycles of raw mince, 95 °C steam, a blade landing on it and onion oil; and wet yeast dough may stick more than
peeling can handle without flour. Second: A does not hold liquids, so batters and whipped things still need a
bowl and a whisk. Third: one mat line means one job at a time, and a meal with Schnitzel, salad and dessert
queues on it.

---

### 3.2 Concept B — SÄULE: ram, die revolver and gravity (extrusion lens)

**Core idea.** One vertical servo ram pushes food in a sleeve through whichever fixed die the revolver presents,
and a blade sweeping flush under the die sets the third dimension: choose the die and the advance per sweep and
you have chosen the cut. The same axis is ricer, Spätzle press, patty former, garlic press, citrus press, meat
flattener and coating press. Food only ever moves downward, straight into the vessel, and the half of the
revolver that is not under the ram sits permanently in a wash box, so dies are washed while the next one works.

```
 SIDE VIEW                                                     z, mm above floor
   [ servo ram 8 kN, 350 stroke ]  dry, above a drip hood      1500-1950
          |
       ---+---   wash collar: ring of nozzles round the        1150
          |      retracted pusher
      [pusher]   changeable face: flat / fingers / platen
    +----------+
    |  sleeve  | <--- loading chute from the box tilter        900-1120
    | dia 140  |      3 sleeves on a turret: raw veg / class R / cooked
    |  x 220   |
    +==========+  die revolver, dia 460 x 25, 8 windows   875-900   [ wash box: spray both ]
    ---rotor----  face rotor: sickle blade / shred disc   850       [ sides, 85 C, hot air ]
      \      /    funnel 60 deg, 120 high                 730-850     (back half of revolver)
       \____/
    [ rotating bowl 10 L or the pot itself, on a load cell ]   400-700
    footprint 450 x 600; a light X-Z handler (needle pad, clamshell, pipette) serves a
    300 x 200 platen table beside the column
```

**Dies.** Open (slices by the rotor alone); grids 6, 10, 20 mm with staggered blade heights (S7); 8-wedge with
centre tube (apples, tomatoes, potato wedges); fries 10 × 10; ricer 3 mm holes; Spätzle 8 mm holes; orifice
Ø 70 (patties) and Ø 40 (dumplings, stuffing nozzle); iris peeler (S10); citrus cone. Rotors: sickle blade,
coarse and fine shred disc.

**Forces.** Engaged edge on a 10 mm grid is about 2 × (food cross-section) / pitch. One potato 60 × 50: 490 mm,
1–2.5 kN. A Ø 130 celeriac: 2 650 mm, 5–13 kN — too much, so the blades are staggered over four heights
(÷ 3–4, S7) and large items go through the 8-wedge die first (edge 8 × 65 = 520 mm, 1–2.6 kN). Ram 8 kN peak,
force-limited, in a closed frame with two tie rods. Face cut of 36 sticks: 60–150 N. Time: 2 potatoes per
15 s stroke cycle, 1.5 kg in about 75 s [E].

**Kinematics and actuators.** Ram 1, sleeve turret 1, die revolver 1, face rotor 1, bowl spin and tilt 2,
handler 3, platen table slide 1, box tilter 2: **12** [E].

**Dosing and moving.**

| Form | How |
|---|---|
| Whole produce | Tilt-singulate down the chute into the sleeve; ends trimmed by sending the first and last slice to waste through a diverter flap |
| Leafy | Into the sleeve; the ram compresses the bundle at 50–100 N and the rotor slices it at 1.5–5 mm (chiffonade, slaw, herbs). Whole leaves for salad bypass the column into the bowl |
| Granular, powder, liquid | Dosing dock straight into the bowl or pot |
| Paste, fat, mince | Into a sleeve with a loose piston floor: the sleeve is a syringe. 1 mm of stroke on Ø 140 is 15 mL |
| Raw meat | Tempered block in the class R sleeve, open die: slices, then strips or cubes through a grid. Limited to the Ø 140 sleeve |
| Frozen | IQF as granular; spinach blocks pushed through the 20 mm grid |

**The hard operations.**

| Operation | How B does it | Confidence |
|---|---|---|
| Peel potato | Default skin-on or cook-then-rice. If peeled raw dice are demanded: broach-peel (S9), honest yield 55–70 % against PRP-022's 75 % | Medium; misses PRP-022 |
| Peel carrot, cucumber, asparagus | Pushed point-first through the iris die (S10) | Medium-high |
| Peel onion | Not native: S11 basket in the sink, or buy peeled | Low |
| Dice onion | Halves, 6 mm grid, 6 mm advance (S6) | High |
| Mince herbs | Compressed bundle, 1.5 mm slices, then a second pass turned by the bowl | Medium-high |
| Frikadellen | Mix in the rotating bowl with a fixed roller; mass into the piston sleeve; Ø 70 orifice, 6 mm of ram advance gives 25 mm of strand (96 mL), face cut: 100 g pucks fall into the pan | High |
| Rouladen | Off-column: handler lays the slice across a hinged U-cradle on the platen table, doses the filling, the cradle closes like a dumpling press, the ram drives a pin (S15) | Medium-low; this is an add-on, not the concept |
| Bread a Schnitzel | Platen table as coating tray: flour, flip by handler, egg, crumbs, ram presses at 30–50 N [R4] | Medium |
| Knead, roll out | Bowl with fixed roller [R4]; roll-out only as platen-pressing into the tin or a 320 mm disc (1–2 kN) | Medium: no free sheeting |
| Mash | Boiled skin-on potatoes through the ricer die, 0.3–1 kN [R4]; skins stay on the die and the pusher wipes them to waste | High |
| Toss salad | Rotating bowl at 10 rpm with a fixed silicone blade | High |
| Carve a roast | Only if it fits Ø 140; a 250 × 150 × 120 joint does not | Low |
| Flip, drain | S20, S41 | — |

**Cleaning and drying.** *Dies and rotors*: revolver wash. The back half of the revolver passes through lip seals
into a wash box of about 3 L sump: spray on both faces at 55 °C, rinse at 85 °C (a 25 mm die reaches A0 60 in
under a minute), then hot air; the rotor spins itself dry at 1 500 rpm. *Sleeve*: an open tube on the turret's
back position between a nozzle above and one below — straight-through flow, no shadows. *Pusher*: retracts
into the wash collar. *Heel in the grid*: pushed through by a follower (S8) before washing. *Funnel*: two
fixed nozzles. *Bowl, cradle, trays*: wash chamber. Zone F in the column is about 0.25 m² [E], all of it
reached by a fixed nozzle at under 150 mm.

**Off-the-shelf / custom.** Off-the-shelf: electric cylinder, blade assemblies of push dicers and the discs of
vegetable cutters as die and rotor inserts [R4], ricer plates, DD or gear motors. Custom: revolver, sleeves,
wash box, face-rotor timing.

**Novel.** Grid-first/face-cut-second with a force-controlled ram (S6); one press axis for ten operations; the
revolver that is washed on its other half; first-and-last-slice trimming; broach-peeling.

**Biggest weakness.** It only does things that fit in a Ø 140 tube and fall. Every sheet operation (Rouladen,
Schnitzel, dough sheets, carving a large roast, assembly) needs the handler and the platen table, i.e. a second
small machine beside the elegant one. And a 1.5 m column with an 8 kN ram is a lot of height and steel for a
dicer.

---

### 3.3 Concept C — TROMMEL: the two-axis drum (rotation lens)

**Core idea.** A washing machine is already a hygienic, sealed, direct-driven, self-draining drum that tumbles,
washes, spins dry and cleans itself, and it is built in very large numbers. Give such a drum a tilt axis, exchangeable
liners and a stator arm through the mouth, and it washes, peels, dries, tumbles, marinates, breads, rounds,
kneads, whips and slices. Tilting the mouth down, or reversing a helical liner, empties it.

```
 SIDE VIEW                 stator arm (through the mouth): scraper / roller /
                           spray lance / driven whisk or blender head
   box tilter doses             \
   into the mouth  ---->   ______\____________
                          /       \           \        drum dia 320 x 300, mouth dia 220
     tilt axis (Y) --->  |  liner  o--tool     |===[ direct-drive motor, 30 Nm, 0-1400 rpm ]
     +60 deg load / mix   \___________________/        (washing-machine class [K])
       0 deg slice, knead        |   shell with drain, sump 2 L, heater
     -30 deg discharge           v
                           [ pot / pan / tin ]       bay 700 wide x 600 deep x 700 high
```

**Liners** (thin stainless shells clipped to the hub; the liner is the soiled part): L1 smooth with two low
lifters; L2 perforated; L3 rasp (peeling); L4 rubber studs (skin slipping); L5 helix (mix one way, discharge
the other, S28); L6 slicing ring, held stationary by a brake while an impeller turns inside it (S27); L7 small
insert for 1 egg white or 100 g of dough.

**Numbers.** Spin dry at 800 rpm, r = 0.15 m: 107 g (salad needs 40–110 g [R4]). Tumble at 10–30 rpm (critical
speed for Ø 320 is 75 rpm). Kneading 1.5 kg needs 14–20 Nm at 100 rpm [R4]: inside the 30 Nm of the motor.
Whisk wire speed at the wall at 200 rpm: 3.3 m/s. Slicing impeller at 300 rpm: 16 g holds the piece on the
ring, the paddle supplies the cutting force.

**Kinematics and actuators.** Tilt 1, spin 1, liner brake 1, stator arm 2, driven head 1, handler 3 (liner and
stator change, meat slices), box tilter 2: **11** [E].

**Dosing and moving.** All forms are tilted or pipetted into the mouth at +60°. Discharge is by tilt to −30°
(loose pieces roll out; pastes need the scraper stator to follow the wall). Whole produce and leaves are
washed in the drum they are dosed into. Raw meat slices are a handler job; the drum only tumbles cubes and
strips (marinating, flouring goulash meat).

**The hard operations.**

| Operation | How C does it | Confidence |
|---|---|---|
| Peel potato, carrot, celeriac | L3 with water, 1.5 kg in 2–3 min [R4: household and industrial abrasive peelers]; peel flushes to the strainer | High |
| Peel onion | Blanch 60 s in the pot, then L4 with 4 bar jets (S11, S12); root plate stays on and is diced with the rest | Medium-low |
| Peel boiled egg, tomato, cooked potato | L4 with water | Medium |
| Slice, strips, shred | L6 (S27): thickness is uniform whatever the shape, no workholding | Medium |
| Dice | **Not native.** Strips plus chop only; true cubes need S6 | Gap |
| Chop onion, herbs | Two-blade rotor at 1 400 rpm in the braked liner (tip speed 15 m/s: chops, does not purée) | Medium-high |
| Frikadellen | Mix with the roller stator; portion with the core tube S4; round by tumbling in floured L1 for 10 s; discharge; smash flat in the pan | Medium-high |
| Rouladen | **Not possible in a drum.** Needs the cradle or loop roller as a separate device | Gap |
| Bread | Tumble in L1: fine for balls, strips, fish fingers; flat cutlets fold and tear [R4] unless tempered rigid first (S18) | Medium-low for Schnitzel |
| Knead | Rotating liner against the roller stator: the proven rotating-bowl kneader, 5 kg on 600 W [R4] | High |
| Roll out | Not native. Pizza: drum at +90°, dough on a flat liner bottom, spin (S47) | Low |
| Mash | Skins off in L4, then roller stator in L1 with butter and milk | Medium |
| Toss and dry salad | L2: wash, spin, then 5 turns at 10 rpm with the dressing. Best of all concepts | High |
| Whip | Driven whisk head in L7 | High |
| Drain pasta | Pour or S41 | — |

**Cleaning and drying.** The drum cleans itself the way a washing machine does: lance in, 2 L at 55 °C with
detergent, 3 min at 50 rpm with reversals, drain, 85 °C rinse, spin at 800 rpm, hot air through the lance. Liner
and stators are inside during this. The known weak point is inherited: the gap between liner and shell is the
"outer tub", where washing machines grow biofilm. It is answered by the 85 °C rinse, the spin and the hot air
after every use, and by liners that come out for the chamber once a day. About 6 L and 8 min per clean [E].

**Off-the-shelf / custom.** Off-the-shelf: direct-drive motor, bearing and seal unit, drain pump, heater, door
gasket technology. Custom: tilt frame, liners, slicing ring, stator arm.

**Novel.** One drum as wash-peel-dry-tumble-knead-slice cell; the liner/shell split; centrifugal slicing at
household scale; rounding and breading by tumbling; the prep tool that is its own dishwasher.

**Biggest weakness.** A drum cannot do anything that needs a flat surface or a defined orientation: no cubes, no
Rouladen, no Schnitzel worth the name, no sheets, no assembly. R2 says exactly those operations (shaping
15.3 %, assembly 6.9 %) decide the 95 %. C is a superb *produce* machine and half a kitchen.

---

### 3.4 Concept D — ZUSTAND: change the state, then handle rigid bodies (thermal lens)

**Core idea.** Put a thermal conditioning step in front of the mechanics. A double-sided contact plate at −25 °C
makes raw meat, bacon, mince, fish, butter and soft dough rigid in 2–4 minutes; steam or a 60 s blanch loosens
skins. After that the machine needs only what a pick-and-place cell needs: a plain two-finger gripper, trays,
moulds and one low-force blade. Sticky pastes are formed like ice cubes and come out of the mould as solid
parts.

**Why it is fast (Plank's equation).** Time for a frozen layer of depth x:
t = (ρL/ΔT)·(x²/2k + x/h), with ρ = 1 050 kg/m³, L = 250 kJ/kg, k = 1.5 W/m·K (frozen), ΔT = 23.5 K (plate
−25 °C, freezing point −1.5 °C). Contact through a 0.5 mm stainless tray, h ≈ 500 W/m²K [E]:

| Case | x | t |
|---|---|---|
| 3 mm crust on each face of a cutlet or patty | 3 mm | 100 s |
| 10 mm slice fully tempered from both faces | 5 mm | 205 s |
| Same 3 mm crust in freezer *air* (−18 °C, h ≈ 12) | 3 mm | 67 min |
| 3 mm crust through a 0.8 mm silicone mould | 3 mm | 235 s |

So the plate, not the freezer, is the tool. Load: a 180 g slice with 40 % of its mass frozen is 25 kJ in 120 s,
about 200 W [E] — the class of the −30 °C "ice-cream roll" plates sold with a 250 W compressor [K].

```
 PLAN VIEW (bay 1000 wide x 600 deep), X-Y-Z gantry above under a drip hood

  +---------+-----------+------------+-------------+-----------+
  | dosing  | COLD CLAMP| band knife | tray / mould| veg cutter|
  | dock    | 300 x 200 | (S38) with | table 300 x | disc+grid |
  | (boxes) | -25 C,    | ram feed,  | 400: moulds,| off-the-  |
  |         | upper     | slices fall| cradles,    | shelf, or |
  |         | plate     | on a tray  | 3 coating   | S6 head   |
  |         | lowers    |            | trays       |           |
  +---------+-----------+------------+-------------+-----------+
  | skin slipper (rubber-finger drum, dia 250)  | rotating bowl 10 L + stators |
  +---------------------------------------------+------------------------------+
  steam / blanch / shock happen in the cooking module's pot with a basket
```

**Kinematics and actuators.** Gantry 3 + gripper 1, cold clamp 1, band knife 1 + feed 1, skin slipper 1, bowl 1 +
stator 1, veg cutter 2, box tilter 2: **14** [E]. The highest count of the four; most are standard axes.

**Tool and vessel set.** Stainless trays 300 × 200 × 0.5 mm; silicone or thin stainless mould trays (pucks,
hemispheres, logs); silicone Roulade cradles; three coating trays; gripper fingers, clamshell S5, needle pad;
the bowl. The cold plate never touches food.

**Dosing and moving.**

| Form | How |
|---|---|
| Whole produce | Tilt-singulate into the veg cutter chute or the pot basket |
| Leafy | Tilt into the bowl with a perforated insert (wash, spin), clamshell S5 |
| Granular, powder, liquid | Dosing dock |
| Paste, mince | Core tube S4, or screeded into a mould tray by a doctor blade |
| Raw meat, bacon, fish | Tempered on a tray, then gripped as a plate or sliced by the band knife; each slice is created singly and lands on its own tray |
| Egg | Egg module |
| Frozen | Used as it comes: frozen is this concept's native state |

**The hard operations.**

| Operation | How D does it | Confidence |
|---|---|---|
| Peel potato | Steam skin-on 20 min, slip in the rubber-finger drum with water (S12), then slice or dice the *cooked* potato at under 20 N; or rice for mash. Raw peeled potatoes: not native | Medium; adapted method for some dishes |
| Peel onion | Blanch 60 s, shock, rubber-finger drum; ends cut by the band knife | Medium-low |
| Peel tomato, boiled egg, almond | Blanch or boil, shock, drum | Medium-high |
| Dice onion | Veg cutter or S6 | High |
| Mince herbs | Herbs are frozen at ingestion (also solves their 3–5 day shelf life [R2]); crushed frozen in a folded sheet under the cold clamp (S19) | High for cooked dishes, low for garnish |
| Frikadellen | Mix in the bowl; screed into a 6-cavity mould; 2–4 min on the cold clamp; pop out; rigid pucks pushed into the pan (S17) | High |
| Rouladen | Band knife cuts 5 mm slices from a tempered block onto a flat silicone cradle; 2–3 min in air makes them pliable; mustard, tempered bacon slice, gherkin, onion placed by the gripper (all rigid); gripper closes the cradle to a roll; 3–4 min on the cold clamp welds the seam with ice (S16); rigid roll goes seam-down into the hot pan; pin (S15) as fallback | Medium; the seam is the unknown |
| Bread a Schnitzel | Tempered cutlet is a rigid plate: 30–60 s in air gives a tacky thawed film; classical three trays, laid, pressed at 30 N, turned over by rotating the gripper 180°. Industry coats frozen-formed products this way [K] | High |
| Knead, roll out | Bowl with roller stator; shortcrust chilled on the clamp before pressing into the tin | Medium |
| Mash, toss, whip | Ricer die or bowl | High |
| Carve a roast | Band knife with ram feed, the roast rested first | High |
| Unmould | Flash the metal mould on the induction zone for 2 s, or flex the silicone one | Medium-high |

**Cleaning and drying.** Everything that touches food is a loose, open part (tray, mould, cradle, finger, blade
guide) and goes to the wash chamber; this concept loads the chamber most (8–12 parts per meal [E]). The band
runs through a wiper and spray box continuously and gets an 85 °C pass at the end. The cold clamp is Zone S:
defrosted by hot gas or a heater once a day, its melt water to the drain; condensation on it is the price.
The skin-slipper drum is flushed like concept C.

**Off-the-shelf / custom.** Off-the-shelf: cold plate unit, gantry, gripper, vegetable cutter, rotating-bowl
mixer, trays, band-knife blades. Custom: cold clamp with upper plate, moulds and cradles, mini band knife,
rubber-finger drum.

**Novel.** Stiffness as a controlled process variable; ice as the fixing agent instead of twine; ice-cube-tray
forming of pastes; singulation of meat slices by creating them one at a time; freezing fresh herbs at ingestion.

**Biggest weakness.** Time and orchestration: every soft item waits 2–4 minutes on one plate, so a meal with
six Rouladen and six Frikadellen queues unless the plate is large or doubled, and the scheduler carries the
burden. And a customer may dislike the idea that fresh meat was surface-frozen, although the crust is 3 mm and
thaws in the pan.

---

### 3.5 Side by side

| | A TUCH | B SÄULE | C TROMMEL | D ZUSTAND |
|---|---|---|---|---|
| Principle | Peel, don't pull | Push through, fall down | Tumble and spin | Change the state first |
| Actuators in prep [E] | 13 | 12 | 11 | 14 |
| Bay width [E] | 900 (+150 magazine) | 450 + 350 table | 700 + handler | 1 000 |
| Strongest at | Dough, mince, Rouladen, breading, carving, transfer | Dice, slices, mash, extrusion | Wash, peel, dry, toss, knead | Meat, forming, breading, unmoulding |
| Cannot do alone | Liquids, cubes of raw roots (uses S6) | Sheets, large roasts | Cubes, sheets, Rouladen, assembly | Raw peeling; is slow |
| Ware to the chamber per meal [E] | 3–5 | 4–6 | 2–4 | 8–12 |
| Cleaned in place | Mat, bars, table | Dies, sleeve, pusher | Drum, liner, stators | Band, drum |
| Water per prep clean [E] | 4 L per mat | 3–4 L | 6 L | chamber load |
| Technical risk | Mat life and stickiness | Low | Low for what it does | Seam weld; scheduling |

---

## 4. Check against the meal corpus (R2)

R2 lists the hard operations by blocked meals. N = native to the concept, A = needs an add-on from section 6
(named), – = not covered. "Common" means the shared base of section 2 covers it for every concept.

| R2 code, share of meals | A | B | C | D | Note |
|---|---|---|---|---|---|
| PLA peel onion/garlic, 52.0 % | A (S11) | A (S11) | N (S11+S12) | N (S12) | Nobody has this at better than medium-low confidence. R2's advice stands: buy peeled first. Garlic: press skin-on through the ricer die, skin retained [R4] |
| COR core/deseed, 20.2 % | A | N (wedge die + S26) | A | A | Peppers: cut first, wash the seeds out through 6 mm holes (S37). Apples: S26 then tube die |
| FLP flip, 12.9 % | Common (S20); A also by NOSE | Common | Common | Common; rigid items by gripper | S20 covers pancakes, omelette, Rösti, fish, patties in one motion |
| TRE trim ends, 12.5 % | N (CHOP, vision) | N (first/last slice) | – | N (band knife) | Needs the item lying along the feed axis |
| PLS / PLH peel soft, peel hard, 10.5 / 7.3 % | N (M5), blanch | A (S9, S10) | N | N for blanchable | Apples for cake: S10 iris or skin-on |
| ASM assemble, 6.9 % | N (rows on the mat, NOSE placement) | A (handler) | – | N (gantry, rigid parts) | Lasagne: sheets by S21, sauces by S3 wide tip |
| SEP separate egg, 6.9 % | Common (S22) | Common | Common | Common | |
| STU stuff, 6.5 % | A (S4 / piston sleeve) | N (Ø 40 orifice) | – | A (S4) | Peppers held cap-up in a ring |
| CAR carve, 4.8 % | N | – (size) | – | N | |
| UNM unmould, 4.4 % | N (M6: peel the mould off) | – | – | N (S17 flash) | |
| WRP + RLT wrap, roll and tie, 4.0 + 1.6 % | N (S14 + S15) | A (cradle) | – | N (cradle + S16) | Kohlrouladen: blanched leaves are limp sheets, same path |
| STR strip/pluck, 3.6 % | – | – | N (tumble florets) | – | Herbs: chop with the tender stems; woody herbs bought rubbed |
| FRM / SHD shape pieces, shape dough, 2.8 / 2.4 % | N (log and cut, M6, sheeter) | N (extrude and cut) | N (rounding) | N (moulds) | Braids and pretzels stay excluded (X-09) |
| PLE peel boiled egg, 2.8 % | A (S12) | A | N (L4) | N | |
| SCO score, 2.8 % | N (blade to a set depth) | – | – | N | |
| BRD bread, 2.0 % | N | A | – (cutlets) | N | |
| Mixing vessel 8–10 L | loop 17 L + bowl | bowl | drum, 8–10 L at 40 % fill | bowl | 1 egg white needs the small insert everywhere |

Reading the table by columns: **A and D cover the no-workaround and shaping operations natively; B and C do not.**
B and C are the better produce machines. That is the reasoning behind section 7.

---

## 5. Recipe reordering: making hard operations vanish

The same plated result can often be reached by a different order of operations. **MEAL-013 limits adapted
methods to 10 % of the corpus**, so each reordering is classed: T = itself a traditional method (free),
A = adapted (counts against the 10 %, needs the MEAL-015 rating).

| Dish or step | Usual order | Reordered | Operation that vanishes | Class |
|---|---|---|---|---|
| Mashed potatoes | Peel, cut, boil, mash | Boil skin-on, rice | Peeling | T |
| Potato salad, Bratkartoffeln | — | Boil skin-on, slip the skin, slice cooked at under 20 N | Raw peeling, high-force cutting | T (Pellkartoffeln) |
| Salzkartoffeln | Peel, boil | Boil skin-on, slip | Raw peeling | A (slightly different surface) |
| Tomato sauce, apple sauce | Skin, core, chop | Cook whole, pass through the ricer or mill | Peeling, coring | T (passata) |
| Beetroot, celeriac for purée | Peel raw | Cook whole, slip or rice | Hard peeling (PLH) | T |
| Cream soups | Peel, dice, cook, blend | Wash, cut to pot size, cook, blend, strain | Dicing, often peeling | T |
| Frikadellen | Form by hand, fry | Portion with the core tube, drop in the pan, press flat (smash) | Forming station | T (a Frikadelle is a flattened ball) |
| Schnitzel | Flour, egg, crumbs | Flour and egg as one thin batter, then crumbs | One coating step, one tray | A |
| Rouladen | Roll each, tie | Roll each, pin or seam-sear | Tying | T (pins are traditional) |
| Rouladen, deconstructed | Six rolls | One large roll from overlapped slices, braised, carved into portions | Five of six rolling cycles | A (different shape on the plate) |
| Pancake | Flip with a turner | Sandwich-flip (S20) | Getting a turner under it | T |
| Thick omelette, frittata, Kaiserschmarrn | Flip | Set the top under top heat | Flipping | T |
| Steak | Flip several times | Both faces at once between two hot surfaces | Flipping | A (no basting) |
| Pasta | Boil, pour off | Boil, suck the water out (S41) | Pouring 4.5 kg of boiling water | T |
| Salting | Pinch of dry salt | Brine by volume (S31) | Powder dosing near steam | T |
| Onions for a braise | Peel, dice raw, sweat | Blanch, slip, dice soft, sweat | Peeling at medium instead of low confidence | A (softer start, browns later) |
| Garlic | Peel, mince | Press skin-on, skin retained | Peeling | T |
| Fresh herbs in cooked dishes | Chop fresh | Freeze at ingestion, crumble | Chopping; and the shelf life | T (frozen herbs are level-1) |
| Pizza, tray cake | Roll out, lift onto the tray | Press or sheet directly on the tray | Transfer of a dough sheet | T |
| Spätzle | Scrape from a board | Press through the die over the pot | Shaping | T (Spätzlepresse) |
| Meat cubes and strips | Cut limp meat | Temper, then cut (S18) | Workholding | T |

I have not counted the class-A rows against R2's 248 meals; that count is an open issue. Peeled boiled
potatoes and raw peeled vegetables are staples, so I expect that relying on class-A reordering for them would
use up the 10 % budget quickly. **Reordering removes much of the peeling problem but not all of it: one raw
peeling mechanism (drum, rasp mat or iris) is still needed.**

---

## 6. Standalone sub-mechanisms

Usable in any concept. Feasibility: H high, M medium, L low.

**Dosing**

* **S1 Hourglass lid.** A lid with one orifice and no moving part; dosing = invert the box for t seconds. Flow of
  free-flowing granules through an orifice is constant and independent of fill level (Beverloo:
  W = 0.58·ρ_b·√g·(D − 1.5d)^2.5). Rice, D = 15 mm: 17 g/s. Salt, D = 4 mm: 1.5 g/s, so ±0.1 s is ±0.15 g [E].
  Three orifice sizes cover 0.5 g to 1 kg. Scale closes the loop. The lid washes with the box. **H** for
  free-flowing goods; fails on anything cohesive.
* **S2 Mesh-valve lid.** For flour, cocoa, starch, ground spices: a 1–2 mm mesh across the opening. The static
  powder arches over the mesh and holds; it flows only while the box is vibrated (50–100 Hz) — the vibration
  *is* the valve, and it closes by itself. About 2–5 g/s for flour [E]. **H** (this is a flour sifter).
* **S3 Kitchen pipette.** Laboratory liquid handling at kitchen scale: a stainless or PP dip tip (10, 50,
  250 mL) on an air-displacement piston that stays on the dry side behind a hydrophobic filter. Only the tip is
  wetted; tips wash in the chamber. Works from any open container including an opened carton (STOW lane).
  ±1 % on thin liquids; oil and cream leave a film, so a blow-out stroke and a touch-off are needed.
  500 mL of milk is two strokes. A wide-bore tip doses sauces for layering. **H**.
* **S4 Core tube.** A thin-walled tube (Ø 20, 40, 60 mm) pushed to a set depth into butter, mustard, tomato
  paste, quark, mince, mash or dough takes a core of known volume; an ejector piston pushes it out. Ø 60 × 35 mm
  of mince is a 100 g Frikadelle, already formed. Residue is a wall film only. The box content ends up
  honeycombed, so the last 15 % needs a scraper or a tilt-and-tap. **M-H**.
* **S31 Salt as brine.** Keep a box of saturated brine (26 % w/w, 0.31 g salt per mL) and dose salt with the
  pipette: 2 g of salt is 6.4 mL, and ±0.1 mL is ±0.03 g. No caking, no powder near steam, no small load cell
  for the most frequent seasoning. Sugar syrup and a stirred starch slurry work the same way. Dry-surface
  salting (steak) is a fine brine spray. **H**; changes nothing on the plate.
* **S32 Box-in-box colander.** Produce is stored in a perforated liner basket inside its box (which also gives
  the vented storage that BOX-007 asks for). The liner lifts out as a wash basket, colander and pouring aid;
  the outer box stays clean and dry. **H**; costs one more ware type.

**Cutting and peeling**

* **S6 Grid-as-fixture dicing.** Push the food through a fixed blade grid with a force-controlled ram and cut
  flush under the grid after every p mm of advance. The grid that makes cuts 1 and 2 holds the sticks for cut
  3, so no workholding exists at all. Open die + blade = slices of any thickness. Against the vegetable
  cutter's slice-then-grid order this needs no feed-tube skill and cuts to a commanded size. **H**.
* **S7 Staggered grid.** Blades at four heights (X blades above Y blades, neighbours offset by 6 mm) so that
  only a quarter of the edge length engages at once: peak ram force ÷ 3–4 for 18 mm more die height. **H**
  (some fry cutters do this [K]).
* **S8 Heel pig.** The last 5–10 mm of food stays in the grid. Push it through with a follower: a sacrificial
  slice of raw potato, a 20 mm block of Shore 20A silicone that bulges 5 mm into the cells, or an ice puck
  that scours the blades on its way (ice pigging is an industrial pipe-cleaning method [K]); the vessel is
  swapped for the waste chute first if the follower is not food. **M**.
* **S9 Broach-peeling.** A grid whose outer ring of cells leads to waste: the potato is pushed through and only
  the inner, skin-free sticks are kept; first and last slices are diverted. Peeling and dicing in one stroke
  with no peeler. Honest yield 55–70 % with three die sizes chosen by camera [E], so it fails PRP-022 (75 %).
  Worth having as a zero-hardware fallback; the customer may accept the loss for the simplicity. **H** to
  build, **L** on yield.
* **S10 Iris peeler.** Six spring-loaded floating blades round an orifice; carrot, cucumber, asparagus,
  parsnip and salsify are pushed or pulled through point first. 5–10 N per blade. Industrial carrot and
  asparagus peelers work this way [K]. Six pivots to keep clean. **M-H**.
* **S11 Hydro-peel for onions.** Cut both poles, slit one meridian 3 mm deep, then tumble in a perforated basket
  under tangential water jets. Mains water at 4 bar through a 2 mm nozzle leaves at about 25 m/s [R6]; its
  impact pressure (½ρv² ≈ 300 kPa) is of the same order as that of a 6 bar air jet close to the nozzle, a
  water jet stays coherent over a longer distance, and no compressor is needed [E]. Skins
  flush to the strainer. The onion gets wet, which does not matter when it is used within minutes. **M-L**:
  plausible, unproven; industrial onion peelers use air because they store the product.
* **S12 Rubber-finger skin slipper.** A drum or roller bed of soft rubber fingers with water spray (the
  principle of a poultry plucker) removes any skin whose bond has been broken by heat: steamed potatoes,
  blanched tomatoes, onions and almonds, boiled eggs. 30–60 s per batch [E]. **M**.
* **S13 Mangle ricer.** A mesh belt folded round the food and pulled through a roller nip: cooked flesh goes
  through the mesh, skins stay in the fold (mash, tomato, apple). With a fine mesh the same nip wrings grated
  potato or thawed spinach (UO-36). Nip line load 1–2 N/mm. **M-H**.
* **S19 Cryo-crumble.** Fresh herbs go straight to the freezer at ingestion (their shelf life is otherwise 3–5
  days [R2]). Frozen leaves are brittle: squeezed in a folded sheet or pushed through a 6 mm grid they shatter
  into flakes under 3 mm. No blade, no bruised green smear on a knife. **H** for cooked dishes; fresh-looking
  garnish still needs a cut.
* **S26 Wheel orienter.** A round fruit spun on a small off-centre wheel in a cup settles with its stem cavity
  on the wheel (apple-processing practice [K]); then an axial tube punch cores it and the wedge die segments
  it. **M**.
* **S27 Centrifugal slicer.** An impeller carries the pieces round the inside of a stationary ring with a
  knife gap; the pieces are held against the ring by 10–20 g and slices leave through the gap, equally thick
  whatever the shape went in (industrial chip slicers [K]). Ø 200 at 300 rpm. Strip and shred rings exist.
  **M**: several knife holders to clean.
* **S38 Mini band knife.** An endless thin blade running at 10–20 m/s cuts by drawing, so the normal force on
  the food is nearly zero: bread, tomatoes, cooked roast, tempered meat, cake. Industry's universal slicer [K].
  The band passes a wiper and spray box on every turn; the wheels sit outside the food zone. Horizontal, with
  a hold-down belt, it splits slices off a meat block. Guarding is mandatory. **H** technically, **M** on
  hygiene of guides.

**Forming, meat, eggs**

* **S14 Loop roller.** A slack belt loop in a trough: lay the slice and filling in the loop, pull one side, and
  the content rolls up on itself — the mechanism of cigarette and stuffed-vine-leaf rollers [K]. Loop
  circumference sets the roll diameter (160 mm for Ø 50). Rolls Rouladen, cabbage rolls, mince logs, dough
  logs, Swiss rolls. **H** for the rolling, **M** for where the seam ends up.
* **S15 Magnetic pins.** Ferritic stainless Rouladen pins (Ø 2 × 90 mm, ring head) are pressed through the seam
  by any press axis from a magazine. At plating a magnet pulls each pin out by its ring, and the machine counts
  pins out against pins in, so none stays in the food (PRP-035). **H**.
* **S16 Ice-weld seam.** Wet meat surfaces pressed together and frozen stick firmly — the reason frozen slices
  cannot be separated. Freeze the closed roll for 3–4 min on the cold plate, put it seam-down in the hot pan:
  the seam sears before it thaws and coagulated protein takes over. No tie, no pin, nothing to remove.
  **M-L**: the physics is sound, whether the seam survives a two-hour braise is an experiment.
* **S17 Ice-cube-tray forming.** Screed mince, dumpling or fish-cake mass into a mould tray with a doctor blade,
  crust-freeze 2–4 min, pop out. The sticky paste leaves as rigid, equal parts (±3 % by volume) that a pusher
  can move. Metal moulds release after a 2 s induction flash that melts a 50 µm film; silicone moulds by
  flexing. **H**.
* **S18 Cold-plate tempering.** Double-sided −25 °C contact makes a cutlet, bacon slice or fish fillet rigid in
  100–200 s (section 3.4). Rigid items can be gripped by the edge, turned, dipped, stacked and sliced to
  ±0.5 mm. One 250 W plate. **H**.
* **S22 Egg by vacuum.** Two bellows cups hold the egg by its ends (40 kPa on 5 cm² is 20 N for a 60 g egg), a
  blade scores the equator from below with about 0.1 J [R4], the cups move 15 mm apart and tilt 30°, the
  content drops into a clear inspection cup on a scale, a camera looks for shell specks and blood, and only
  then is the egg committed to the batch (one bad egg costs one egg, not the dough). The shells never leave the
  cups until they are over the waste chute. Separation: a soft Ø 25 mm pipette tip lifts the yolk out of the
  cup. **M-H**.
* **S29 Mini flat-bed breader.** A vibrating tray recirculates 100 g of crumbs as a bed and a curtain; the item
  passes through on a wire grid. A true fluidised bed needs 1.5 L of crumbs for a cutlet-sized item and the
  bed is contaminated by raw meat after one batch, so it is rejected for the home scale. **M**.

**Transfer and handling**

* **S5 Clamshell.** Two stainless half-shells on a scissor whose hinge is 150 mm up the shaft, out of the
  food: open it is tongs, half closed a scoop for leaves, pieces and cooked pasta, closed a ladle and a ball
  mould (press 60 g of dumpling mass between the shells). One tool replaces tongs, scoop, ladle and former.
  **H**.
* **S21 Nose transfer.** A thin belt (or the concept A mat) round a Ø 20–30 mm nose bar: advance the nose
  under or withdraw it from under a limp item while the belt runs at the same speed, and the item is picked up
  or laid down with no sliding at all — the baker's conveyor peel and every belt-to-belt transfer in the food
  industry [K]. Dropped over the nose onto a lower surface moving the other way, the item lands turned over.
  For meat slices, dough sheets, fish, pancakes, lasagne sheets. **H**.
* **S28 Helix vessel.** A drum or bowl with a fixed internal helix, like a concrete mixer: one direction mixes,
  the other discharges through the mouth, with no tilt actuator and no scraper. **H** for loose pieces, useless
  for pastes.
* **S37 Flotation wash and hydro-transfer.** Tip soiled produce into a water column with a gentle upflow: sand
  and stones sink to a trap, leaves float to a weir and arrive washed; cut pepper seeds pass a 6 mm screen.
  Cut vegetables destined for a soup are flushed into the pot by the recipe's own measured water, which leaves
  the chute clean. **M-H**.
* **S30 Vacuum wand for granules.** A suction wand lifts rice, lentils or frozen peas out of an upright box
  into a small cyclone over the pot, as plastics plants convey pellets [K]. No box tilting. But every metre of
  hose is a Zone F surface that flour dust and damp turn into paste. **L**; listed so that it can be rejected
  knowingly.

**At the hob**

* **S20 Double-pan flip.** Two identical pans. The empty one is preheated and oiled, placed face down on the
  full one, the pair is clamped and turned 180° about a horizontal axis, the upper pan is lifted off. Everything
  in the pan is turned at once and nothing has to get under the food: pancakes, omelette, Rösti, fish fillets,
  six Frikadellen, a Schnitzel. One rotary axis. R2: flipping is 12.9 % of meals with no workaround. **H**;
  hot fat must be little (under 30 mL) or drained first.
* **S41 Venturi drain wand.** Drain by removing the water, not the food: a stainless wand with a slotted tip
  goes to the bottom of the pot; a water-jet ejector driven by mains water sucks the cooking water out and
  sends it, diluted and cooled, to the drain (drain pipes dislike 95 °C water). No moving part, and the motive
  water flushes the ejector. About 6 L/min of motive flow lifts 3–4 L/min [E]: a 4 L pasta pot in 70 s for 7 L
  of water. Pasta water can be reserved by stopping early. The same wand empties blanching water, potato water
  (then steam-dry on residual heat) and wash water when vegetables are washed in their pot. **H**.
* **S47 Spin-coat.** A pan on a rotating mount spreads thin batter by itself: film thickness
  h ≈ √(3μ / 4ρω²t); with μ = 0.3 Pa·s, 95 rpm, 3 s: 0.9 mm [E], a crêpe, with no spreader to wash. At 500 rpm
  the centrifugal stress ρω²R² in a Ø 200 dough disc is about 30 kPa, which I expect to exceed what a rested
  pizza dough resists [E, unverified], so a dough ball on a non-stick disc should open up the way a thrown
  pizza does. **M** for batter, **L** for dough
  (the centre thins first).

**Cleaning**

* **S23 Reel-through wash.** Any belt or mat is washed by running it through a fixed spray, scraper and steam
  section: full coverage by construction, thermal disinfection in seconds because the part is 1 mm thick
  (section 3.1). **H**.
* **S24 Revolver wash.** A tool turret whose idle half sits in a small wash box behind lip seals: tools are
  washed and dried while their neighbours work, and never travel to the chamber. **M-H** (the lip seals are
  the development item).
* **S25 Spin-dry everything.** Plastic boxes stay wet after a hot rinse because they hold no heat [R6]. Spin the
  rack instead: 600 rpm at r = 0.15 m is 60 g, which strips the film in 10–15 s and leaves a minute of warm
  air to do. Every rotary tool dries itself the same way. Replaces most of the 15–20 min hot-air step. **H**.
* **S42 Deglaze-rinse.** Rinse the emptied vessel or the mat with the recipe's own liquid and send that to the
  pot: it raises the yield and lowers the soil load [R4]. **H**.

---

## 7. The bet

**Concept A (TUCH) as the backbone, with concept B reduced to a die head (S6, S7) at the head of the mat, and
concept D reduced to one cold clamp (S17, S18) beside it.**

Reasons:

1. *It aims at the right problem.* R2 shows that the operations which decide the 95 % and cannot be bought away
   are limp-and-sticky operations: shaping 15.3 %, flipping 12.9 %, assembly 6.9 %, carving 4.8 %, unmoulding
   4.4 %. A does all of them with five primitives on one surface. B and C are elegant at what every vegetable
   cutter and washing machine already does.
2. *Cleaning is decided by geometry, and a flat film is the best geometry there is.* Full spray coverage by
   construction, A0 60 in seconds, dry in one pass, 4 L instead of 20 L. No other concept cleans its main
   food-contact surface in under five minutes without a chamber.
3. *It is two-dimensional.* Six rotary shafts through one wall, no robot arm, no linear guide in the wet zone,
   no tool changer for the core operations.
4. *The additions are small.* The die head is a 140 mm tube and a ram, discharging onto the mat, which then
   carries the dice away — it needs no vessel handling of its own. The cold clamp is a bought unit; with it
   the mat handles meat as a rigid part when that is easier (breading, slicing a block) and as a limp sheet
   when that is needed (rolling).
5. *The risk is concentrated and cheap to test.* Everything stands or falls with the mat: stickiness of wet
   dough and mince, life under the blade, odour. A bench rig with two geared motors, a rolling pin and a
   baking mat answers this in a week. B and C carry less risk only because they attempt less.

What I would not bet on: C as the whole kitchen (it has no answer to sheets), D alone (too slow and too many
loose parts), and onion peeling in any concept before it is tested — buy peeled until then.

---

## 8. Open issues

1. Does a reinforced silicone or TPU mat release 65 % hydration yeast dough and raw mince by peeling alone, or
   does it need flour or oil each time? What is its life in cycles under blade contact and 95 °C steam?
2. Slack control in LOOP mode: is open-loop geometry enough, or is a loop-depth sensor needed?
3. Seam of a Roulade: pin, ice-weld or seam-sear — three candidates, none tested through a two-hour braise.
4. Onion peeling (S11, S12): both medium-low. A test on 50 onions of mixed size would settle it.
5. Hydro-peel and rasp peeling wet the produce and use water; consumption per kg is not estimated.
6. Cold clamp: frost and condensate management, defrost schedule, and whether surface freezing is acceptable to
   the customer for fresh meat (a customer decision).
7. MEAL-013 budget: the class-A reorderings of section 5 have not been counted against the corpus, and it is
   open which of them raters accept as equivalent.
8. S20 needs two pans per flip and a hob mount that rotates; this belongs to D5 and is not designed here.
9. S41 motive-water consumption and the drain temperature limit need the real mains pressure.
10. All actuator counts exclude the dosing dock's pipette axis and the egg module (about 5 more, the same for
    every concept).

## 9. Risks

| Risk | Concept | Consequence | Mitigation |
|---|---|---|---|
| Mat wears, stains or smells within months | A | Human exchange more often than yearly; HYG-025 missed | TPU for class R and odorous food; bake-out; mats as a cheap consumable; early life test |
| Sticky mass winds round the roller | A | Jam, human intervention | Scraper on the roller; wet or floured roller; M1 cover pass |
| One mat line is a bottleneck | A | PERF time targets missed at 6 persons | Second reel pair on the same cheeks; scheduler |
| Ram force underestimated (dull blades, fibrous food) | A, B | Stall, crushed food | Force control, staggered grid, wedge die first, blade life counter (PRP-034) |
| Blade fragment in food | all cutters | Foreign body | Ram force signature and camera check of the die after each use (PRP-035) |
| Biofilm between liner and shell | C | Odour, hygiene failure | 85 °C rinse, spin and hot air after each use; liners to the chamber daily |
| Plate queue makes meals late | D | PERF missed | Larger or second plate; temper during other steps |
| Ice-weld seam opens in the braise | D | Rouladen unroll | Pin as the default, ice-weld only after proof |
| Broach-peel loss rejected | B | No raw peeled potato | Drum or rasp mat as the raw peeler |
| Reordered recipes rated below 3.0 | all | Fall into the 5 % | Keep one raw peeler and the traditional order as an option |
