# Prep ideas A — Machine-tool lens ("the food machining centre")

Round P1 (idea finding), meal preparation. Author's lens: treat food preparation as CNC machining — a
rigid kinematic, a spindle with quick-change tooling, workholding for irregular workpieces, a tool
magazine, chip evacuation, coolant flood and an enclosure that is washed down.

Status of numbers: forces and energies for cutting, kneading and pressing are taken from
`research/04-food-prep-mechanisms.md` (R4). Everything else is my own estimate, marked **[E]**, and
nothing here has been built or tested. The concepts were drawn up against
`requirements/requirements.md` section 5.3 (UO list) and the meals named in the brief, and then
checked against `research/02-meal-corpus.md` (R2: 248 meals, 126 unit operations) once it was
available; section 1.5 is that check, and it changed vessel sizes, module widths and the ranking of
weaknesses.

Contents: 0 shared conventions — 1 four whole-system concepts and the corpus check — 2 seventeen
standalone sub-mechanisms — 3 the bet — 4 open issues — 5 risks.

---

## 0. What the machine-tool lens brings, and conventions shared by all four concepts

### 0.1 Seven transfers from machine-tool practice

| Machine-tool practice | Food translation used below |
|---|---|
| The machine is generic; **fixtures and tooling carry the job knowledge** | A strong, dumb, clean spindle or ram; all food-specific geometry sits in passive tools, dies and pallets that go through the wash chamber |
| **Only round things go through the enclosure wall** (spindles, quills, rotary tables); slideways live outside behind covers | Every penetration into the wet cell is a round rod or shaft through a rod seal or rotary seal. No slots, no bellows, no drag chains, no linear guides inside the cell |
| **Spring clamps, actuator releases** (tool drawbar) | A tool or vessel can never drop on power loss |
| **Through-spindle coolant and air blast** | Water, air and vacuum through the spindle: doses water, flushes the tool interface, blows the socket clean before every tool change, drives a wash head |
| **Workpiece in the spindle, tools fixed** (turning on a mill) as well as the reverse | A potato on a fork in the spindle, pushed past a fixed blade ring, is easier than a blade chasing a clamped potato |
| **Parts catcher and chip conveyor** | A flap under the cut diverts "part" to the vessel and "chip" (peel, shell, trimmings) to the waste sieve; waste never passes over open food (PRP-033) |
| **Probing, tool setting, broken-tool detection, canned cycles** | Measure each workpiece before cutting, check every blade after each operation (PRP-035), program recipes as canned cycles |

### 0.2 Shared conventions

* **Wet cell.** A fully welded 1.4404 tub, coved corners R ≥ 10 mm, floor sloped 3° and ceiling 5° to
  one drain, as R6 recommends for a "wash-down-lite" cell. Below the drain sits the **chip box**: a
  perforated standard storage box (2 mm holes) that catches peel, shells and trimmings, is carried
  away by the transport system like any other box, emptied into the organic waste and washed with
  the boxes. No macerator. Below that: sump 10 L, 2 kW heater, recirculation pump, 5 bar diaphragm
  pump for jets.
* **Removable ware goes to the pass-through wash chamber** (R6 backbone, 480 × 480 × 400 mm
  envelope). Every tool, die, pallet and vessel below fits that envelope and is a one- or two-piece
  part without threads, hollow sections or blind pockets.
* **Vessels are pallets.** Every vessel has the same base ring with three tapered lugs (a bayonet
  "zero-point clamp", engaged by 30° rotation). The same ring sits on the spin chuck, on the hob, in
  the wash rack and in the transport gripper. The sketches were first drawn for a Ø 240 × 160 mm
  (5 L) pot; R2 section 6.3 asks for more at 6 persons, so the family is: mixing bucket Ø 270 × 200
  (10 L nominal) with a 2 L insert and a 0.3 L cup on the same ring (one bucket cannot whip one egg
  white and knead 1 kg of dough), boil pots 9 L and 4 L, sauce pot 1.5 L, pans 28 and 36 cm, oval
  braiser 320 × 240 × 110 on an adapter ring (it cannot spin), flat platen Ø 270, perforated baskets
  for the pots. All fit the 480 × 480 × 400 wash envelope. Where a dimension in a sketch still shows
  the Ø 240 pot, section 1.5 states the consequence.
* **Box dock.** The transport system presents an opened storage box at a dock in the cell wall. A
  dock tilter turns it 0–135° about its pouring edge with a 100–200 Hz vibrator (R4 9.3/10.1), so
  free-flowing goods are tilt-poured with weight feedback. For everything that does not pour, a
  spindle tool reaches into the open box instead.
* **Weighing.** Bulk: three 10 kg load cells under the vessel station (±2 g). Seasoning: a 200 g
  cell under a small weigh cup at a dry corner, away from steam (R4 9.3).
* **Cooking position.** I assume the induction zones are inside or directly beside the cell, within
  reach of the same spindle, because stirring and flipping during cooking are in scope. Where a
  concept needs something from the cooking module (a second pan, a contact plate) it says so.

### 0.3 "G-code for food"

Recipes compile to canned cycles, each with a probe step, a process step and a verify step, e.g.
`PEEL(item, allowance 1.5)`, `DICE(p=10)`, `KNEAD(mass, energy 12 kJ/kg)`, `FORM(puck, 100 g, n=8)`,
`POUR(from, to, scrape=1)`, `WASH(tool)`. Three things are taken over from CNC directly:

* **Workpiece probing.** A camera plus the spindle's own force signal measure length, diameter and
  axis of every potato or onion before the cut; toolpaths are scaled per piece.
* **Tool setting / broken-tool check.** After every cutting cycle the blade is passed through a light
  curtain or touched on a setter; a missing tooth or blade aborts and discards the batch (PRP-035).
* **Adaptive feed.** Spindle torque and ram force are the process signals: kneading stops on an
  energy target, dicing feed slows when ram force rises, a stalled blade is a jam, not a mystery.

---

## 1. Whole-system concepts

Overview:

| | A1 TURN-MILL | A2 CEILING-QUILL FMC | A3 TURRET PRESS | A4 BELT & BLADE |
|---|---|---|---|---|
| Machine-tool ancestor | Turn-mill centre with trunnion and tailstock | Vertical machining centre with pick-up magazine and pallets | Turret punch press / rotary transfer machine | Conveyor-bed cutter, frame saw, dough sheeter |
| What moves | The workpiece and the vessel rotate; tools nearly fixed | One universal spindle moves; everything else stands | Dies and vessels index under one fixed ram; food falls | Food rides a belt past fixed powered blades |
| Force level | 3 kN press quill, 20 Nm spindle | 3 kN quill, 20 Nm spindle | 3 kN ram | < 300 N everywhere (powered blades) |
| Servo axes (excl. valves) | 12 | 8 per quill; 15 for the two-quill cell that R2's vessel sizes require | 10 (+3 for a pick arm) | 12 |
| Module width (600 deep) | 900 mm | 600 mm per quill; 1200 mm for two | 600 mm | 900 mm |
| Best at | Peeling, onions, eggs, kneading, spin-drying, pouring | Breadth: handles, presses, mixes, doses, flips, washes itself | Dicing, forming, mashing, throughput, few parts | Meat slices, Rouladen, breading, dough, carving, slicing |
| Worst at | Flat limp items | One seal concept carries everything | Anything that must be placed or turned | Bowl work is an add-on; dicing needs two passes |

---

### 1.1 Concept A1 — TURN-MILL ("everything spins")

**Core idea.** One powerful main spindle on a tilting trunnion holds either a workpiece between centres
(lathe mode: peel, slit, part off) or a vessel by its base ring (bowl mode: the vessel rotates and the
tools stand still, as in the Ankarsrum mixer, so no shaft ever passes through a vessel). Tilting the
spindle turns the same vessel from mixing bowl (axis up) to tumbling drum (axis 30°) to pouring and
dump-flipping (axis down), and high-speed spin dries produce, pasta, salad and the vessel itself. All
other axes are plain round rods through the walls.

```
 FRONT VIEW, wet cell 800 W x 520 D x 1000 H (module 900 W)
      box dock + tilter        Q: press/tool quill, Z 350 mm, 3 kN, C 20 Nm / 9000 rpm
  ________|__|____________||____________________________________  ceiling 5 deg
 |         \ chute        ||                                     |
 |          \           [tool]   <- tools stand in the vessel    |
 |  brush-roller           .        (the vessel is the magazine) |
 |  loader (rear,       ___.___  bowl at B=+90                   |
 |  swings in)         |       |                                 |
 |                     |_______|     TB: tool bar, X 300, phi    |
 |                        | |      ===[peel|part|slit]===========| -> right wall
 |   trunnion pivot  (O)--S1]=>  <potato>  <=[S2 tailstock rod]==| -> right wall
 |   z = 450, B +-95 deg  spur              cup, X 300, 300 N    |
 |                                                               |
 |               \___ parts-catcher flap ___/                    |
 |        chip chute |            | part chute                   |
 |                   v            v   [vessel pallet on weigh pad]|
 |___________________o____________________________________________| floor 3 deg
        chip box  |  sump 10 L, heater, pumps  (dry side: all motors behind L, R, top)
 <------------------------------ 800 ----------------------------->
```

**Kinematics and actuators (12).**

| Axis | Function | Data [E] |
|---|---|---|
| S1 | Main spindle, faceplate Ø 160 with three-lug vessel bayonet and a centre socket for a spur drive | 600 W, two ranges: 0–300 rpm at 20 Nm; 0–1500 rpm at 3 Nm |
| B | Trunnion tilt of S1 about a horizontal axis through the left wall | ±95°, 60 Nm (5 kg vessel at 280 mm plus margin), worm gear, self-locking |
| S2 | Tailstock rod through the right wall, coaxial with S1 at B = 0, free-running cup centre | stroke 300 mm, 300 N |
| TB-X, TB-φ | Tool bar: a round rod through the right wall, parallel to and above the lathe axis; slides (X) and rocks (φ). A gang head on it carries peel blade, parting knife, slitting blade, jet nozzle; φ selects the tool and sets the depth, like the rocker of a Swiss lathe | X 300 mm, 100 N; φ 10 Nm |
| Q-Z, Q-C, Q-W | Vertical quill through the ceiling above S1 at B = +90°, 55 mm off the bowl axis: press ram, tool spindle, tool clamp/actuation rod | Z 350 mm, 3 kN; C as S1 ranges up to 9000 rpm at 1 Nm; W 20 mm |
| Flap | Parts catcher under the lathe axis: left = chip chute, right = part chute | 1 rotary actuator |
| Loader (2) | Twin helical brush rollers (sub-mechanism M4): spin, and lift to centre height | 40 W; lift 120 mm |
| Dock | Box tilter | 0–135° |

Every penetration is a rotary seal (S1 via the hollow trunnion pivot, flap, loader shafts) or a rod
seal with wiper and flush ring (S2, TB, Q).

**Tools and vessels.** Tools are passive one-piece parts on the quill interface (M1): roller +
scraper pair, dough hook, whisk, bell-guarded blade, flat ram foot Ø 110, ricer plunger Ø 110 with
3 mm holes, puck nozzle plunger, conical face roller, platen, shaker cup, spray nozzle, tongs.
Tools do not live in a magazine: **they arrive standing in a ring holder on the rim of the clean
vessel** at r = 55 mm; S1 indexes the vessel so the wanted tool is under the quill, and they leave
for the washer in the vessel they soiled (M12). Gang-head blades on the tool bar are a removable
cassette. Vessels: pot/bowl Ø 240 × 160, pan, platen Ø 240, spin basket, press pot (Ø 120 cylinder
set eccentrically on a pallet so that it is coaxial with the quill), drum lid with centre port.

**Dosing and moving, by ingredient form.**

| Form | How |
|---|---|
| Whole produce | Box tilted onto the helical brush rollers, which wash, singulate, align the long axis and lift each piece onto the lathe axis; S2 closes |
| Leafy | Tilt-pour (with shaking) into the spin basket on S1 at B = +90°; flood from the quill nozzle, slow reversing rotation, tilt to pour off, spin 600 rpm for 20 s |
| Granular, powder | Dock tilt-pour with vibration into the vessel on S1; S1 stands on the weigh frame (whole trunnion subframe on three 30 kg cells, ±3 g [E]); seasoning via the 200 g weigh cup |
| Liquid | Water through the quill (flow meter); other liquids tilt-poured from a pour-lip box with weight feedback |
| Paste, solid fat | Frozen or chilled block dosed by milling (M10); jar contents by a spoon/syringe tool on the quill (W-actuated) |
| Raw meat | Tongs or freeze gripper (M9) on the quill lift pieces from the box onto the platen or into the pot. The quill has no XY travel, so **the box dock must be placed so the tilted box delivers directly onto the platen** — a real limitation |
| Egg | Tongs place the egg between the S1 and S2 cups (M6) |
| Frozen | IQF goods tilt-poured; blocks dropped whole into the pot |
| Vessel to vessel | Trunnion pours at B = −45…−95° over a pallet on the floor, S1 turning slowly against a fixed scraper held by the quill; residue ≤ 2 % even for dough [E] |

**The hard operations.**

| Operation | How it is done | Numbers [E] |
|---|---|---|
| Peel potato | Between spur centre and cup; floating blade with depth shoe on the tool bar, 3–5 N preload, follows the out-of-round profile; then the parting knife faces both ends | 200 rpm, feed 8 mm/rev: 80 mm in 3 s; 20 s per potato incl. loading, 1.5 kg in 3.5 min; loss ≈ 15 % skin + 5 % end caps |
| Peel carrot | Same; the brush rollers stay up as a steady rest so the slender "shaft" cannot whip | 200 mm in 5 s |
| Peel onion | Held between two concave cups with three 8 mm prongs each (the prongs sit in the root and top, which become waste); slitting blade draws one 2 mm deep meridian cut; tangential fan jet at 4 bar strips the slit skin at 300 rpm (M5) | 8 s, 0.2 L water |
| Dice onion | The cook's method, by lathe: draw-knife strokes along the axis (the cut force goes axially into the headstock cup), indexing S1 by 15° — 24 radial cuts that stop short of both ends; then the parting knife plunges every 5 mm. Dice fall on the flap to the part chute; the two end caps stay on the prongs and are dropped to the chip chute | 24 × 1.5 s + 10 × 2 s ≈ 55 s per onion; blade force 20–60 N |
| Dice potato, carrot | Not on the lathe: the peeled piece falls via the part chute into the press pot; the quill pushes it through a two-tier grid die into the vessel below; a blade bridge on the rotating vessel rim cuts cubes (as A2) | 60 × 60 mm chamber, 0.9–2.3 kN |
| Mince herbs | Rotating platen (S1 at B = +90°) with a rolling gang cutter on the quill, five free-running discs at 30 N, traversing radially like a facing cut; a scraper tool sweeps the result over the rim into a cup | 10–30 g in 30 s; platen wear is an open point |
| Crack egg | Lathe pipe-cutter method (M6): egg held between two vacuum cups, a carbide point scores the equator over 360°, the cups pull 10 mm apart with a 20° twist; the contents fall on the flap into a cup, the shells go to the chip chute | 8 s per egg; 12 eggs in 96 s |
| Frikadellen | Mass mixed in the rotating bowl with roller and scraper; bowl dumped into the press pot; the quill drives a nozzle plunger into it (backward extrusion through a Ø 60 mm nozzle), a wire on the tool bar parts off 25 mm pucks that slide down the part chute into the pan | 100 g ± 5 %; 0.5 kN |
| Rouladen | **Mandrel winding.** A slotted mandrel in S1 (B = 0) grips the leading 15 mm of the slice; the slice with mustard, bacon, gherkin and onion lies on a feed platen tangent to the mandrel; S1 turns 2.5 rev while the brush-free steady roller keeps the coil tight; S2 strips the roll axially into a slot of the Rouladen cradle (M8), seam down. No tying | 25 s per roll; mandrel Ø 12 mm |
| Bread a Schnitzel | On the platen at B = +90°: flour from a shaker cup while turning; egg wash poured at the centre and **spin-coated** at 60 rpm; crumbs shaken on and pressed by a platen tool at 50 N; then **dump-flip**: B = −90° over a second platen on a raised pallet 20 mm below, and the second side is coated the same way | 60 s per cutlet |
| Knead and roll out dough | Knead in the rotating bowl against roller and scraper; roll out on the platen with a conical roller whose apex lies on the platen axis (rolls without slip), thickness set by quill Z | 1.5 kg at 20 Nm, 60–100 rpm; disc Ø 240 × 2–10 mm ± 0.5 |
| Mash | Boiled potatoes in the pot; ricer plunger (3 mm holes, wiper lip) driven to the floor like a French press; mash rises through it, skins stay below; the plunger rod is released and the plate stays in the pot while butter and milk are folded in | 3 kN on Ø 110 mm = 3.2 bar (need 1–2 bar) |
| Toss salad | Drum mode: bowl with lid at B = 25°, 15 rpm, 30 s, dressing injected through the lid port | gentle tumbling, no tool |
| Flip steak / pancake | Dump-flip pan to pan with the trunnion (needs a second hot pan from the cooking module) | 3 s |
| Drain pasta | Pot with basket chucked on S1, tilted to −100° through a clip-on strainer lid into the cell's own drain; or the basket is spun at 300 rpm for 10 s | 4.5 kg of boiling water stays inside the tub |

**Cleaning and drying.**

* *Removable, to the wash chamber after each use:* vessels, platens, baskets, lids, all quill tools
  (riding in their vessel), gang-head cassette, centre cups and spur, flap tray, chip box.
* *Fixed Zone F/S, cleaned in place after each meal:* faceplate and trunnion pod, S2 nose, tool-bar
  rod, quill nose, brush rollers, chutes, walls, ceiling, floor.
* *Method.* The main spindle is the washer: the quill nozzle feeds 4 L/min onto the bare faceplate
  spinning at 1500 rpm (rim speed 12.5 m/s), which throws a flat sheet; sweeping B through ±95°
  rotates that sheet across ceiling, right wall and floor while front and back walls are always in
  its plane. Two fixed nozzles cover the shadow behind the trunnion pod. The brush rollers spin in
  the sheet. Rods are retracted through their flush rings. Sequence: cold pre-rinse to drain, 55 °C
  detergent recirculated from the sump (6 min), fresh rinse at 80 °C (3 min). About 15 L per wash.
* *Where water goes.* Floor → chip box sieve → sump. The chip chute and part chute are open
  half-pipes, not tubes.
* *Drying.* Everything that can spin is spun (vessel at 800 rpm: 86 g at the rim); 60 °C air for
  10 min through the cell; rods are wiped by their seals.
* *Spray shadows and crevices.* The trunnion pod is one welded, domed body. The known crevice lines
  are five seals: trunnion pivot, spindle nose, three rods. Each seal is doubled, with a drained
  leak-off groove between the lips, and is an LRU from the dry side.

**Off-the-shelf vs custom.** Standard: BLDC/servo motors, worm and planetary gearboxes, ball-screw
electric cylinders, load cells, dishwasher pump and heater, nozzles, apple-peeler-type floating blade,
Ankarsrum-type roller/scraper geometry. Custom: trunnion pod, faceplate bayonet, quill interface,
gang head, cups, brush rollers, all vessels' base rings.

**Genuinely novel.** Lathe dicing of an onion with the ends as sacrificial chucking stock; pipe-cutter
egg cracking; mandrel-wound Rouladen; the vessel as tool magazine; the faceplate as the wash
impeller; one trunnion giving bowl, drum, pour and flip.

**Biggest weakness.** The quill has no XY travel and the lathe has no gripper, so every flat, limp
or placed item (meat slices, filling, layering a lasagne, plating) depends on chutes and on the
trunnion — A1 is a brilliant vegetable and dough machine and a poor pick-and-place machine. It is
also 900 mm wide and 1000 mm high inside, and onion dicing at 55 s per onion is slow.

---

### 1.2 Concept A2 — CEILING-QUILL FMC (food machining centre with a sealed ceiling and pallets)

**Core idea.** One vertical universal spindle hangs from a completely flat, sealed ceiling made of
two nested eccentric discs (M3), so it reaches any point of the deck while only rotary seals face
the food. The spindle nose carries torque, a push rod and a fluid channel (M2), which makes every
tool a passive stainless part; the quill is also a 3 kN press ram, a crane for vessels and the
carrier of the wash head. The food-specific knowledge sits in pallets and die cassettes on the
deck — fixtures — and each tool is washed in its own holster in the magazine.

```
 FRONT VIEW, wet cell 540 W x 520 D x 750 H (module 600 W)
   dry: D1/D2 worm drives, Z ball screw, C motor (2 ranges), W actuator, rotary union
  =====[================ D1 disc O 500 ================]=====  ceiling, 5 deg, flat
               [====== D2 disc O 250 ======]   inflatable seals, leak-off groove
                          ||
                          ||  quill O 50, Z 380 mm, 3 kN
                          ||
                        [M1]  expansion mandrel + W rod + fluid
  back wall:  |T1|T2|T3|T4|T5|T6|T7|T8|   tool holsters = CIP pockets (drain, 3 jets, warm air)
              |T9|..                 |
  dock ->  \ chute                         press bracket (3 pegs on back wall, z = 230)
            \                                [die cassette 60x60 chamber]
             \                                    |  blade bridge on vessel rim
   [weigh cup]   [vessel on weigh pad]      [vessel on SPIN CHUCK]    [pan on induction zone]
  ____o_______________o__________________________(O)______________________#######_____  deck 3 deg
   200 g cell     3 x 10 kg cells         rotary seal on raised boss    (cooking module)
  <------------------------------------ 540 ------------------------------------------->
   below: chip box, sump, pumps      reach of quill: circle O 480 (corners by tool offset)
```

**Kinematics and actuators (8).**

| Axis | Function | Data [E] |
|---|---|---|
| D1 | Large ceiling disc Ø 500, slewing ring, worm drive (self-locking) | ±180°, 40 Nm |
| D2 | Eccentric disc Ø 250, centre 120 mm off D1's centre; quill 120 mm off D2's centre → reach radius 0–240 mm | ±180°, 25 Nm |
| Z | Quill Ø 50 through a rod seal in D2 | stroke 380 mm, 3 kN, 150 mm/s |
| C | Spindle inside the quill, two ranges | 0–300 rpm at 20 Nm; 0–9000 rpm at 1 Nm |
| W | Push rod through the spindle: actuates tools, over-travel releases the clamp | stroke 20 mm, 300 N, 5 Hz |
| Spin chuck | In the deck, three-lug bayonet, on a raised boss | 0–800 rpm, 5 Nm; also 20 Nm at 60 rpm for kneading with a fixed tool |
| Dock tilter | Box tilt-pour | 0–135° |
| Range shift | Spindle gear range | — |

Plus valves for water, air and vacuum into the spindle. Kneading torque (20 Nm) is reacted by the
two worm drives: 20 Nm / 0.12 m = 170 N tangential, well within a self-locking worm.

**Tools (about 16, all passive, one or two pieces).**

| # | Tool | Driven by | Used for |
|---|---|---|---|
| T1 | Tongs with silicone fin-ray fingers | W | produce, meat, eggs, packs |
| T2 | Vessel hook (grips the base ring or a bail) | W | crane for vessels, lids, pallets, dies up to 6 kg |
| T3 | Fork with stripper ring (three 12 mm prongs) | C, W | workpiece in the spindle: peeling, jet-skinning |
| T4 | Dough hook / roller | C | knead (with or against the spin chuck) |
| T5 | Whisk | C | whip, emulsify |
| T6 | Silicone-edged paddle / scraper | C | stir, fold, scrape out, stir in the pan |
| T7 | Bell-guarded blade | C high | chop, purée, blend hot soups in the pot |
| T8 | Ram foot 58 × 58 with cross slots; ram foot Ø 110; ricer plunger; puck nozzle plunger | Z | dice, flatten, form, mash |
| T9 | Rocking mezzaluna (W rocks a double blade) | W, XY | herbs, garlic, fine onion on a board pallet |
| T10 | Syringe 60 mL / 250 mL | W | pastes, oil, egg wash, yolk pick-up, batter metering |
| T11 | Angle-head turner (open bevel pair, torque-arm pin on the quill) | C | flip steak, Schnitzel, Frikadellen, pancake |
| T12 | Conical face roller | Z, spin chuck | roll out dough |
| T13 | Freeze platen (M9) or vacuum cup | fluid | pick one meat slice |
| T14 | Shaker / sifter cup | C dither | flour dusting, crumbs, spices from the weigh cup |
| T15 | Rotary jet wash head | fluid | wash the cell (M11) |
| T16 | Squeegee | XY, C | dry the flat walls |

**Pallets and fixtures.** Pot/bowl, pan, platen, spin basket (as 0.2); press pot Ø 120; **dice
cassette** (60 × 60 × 120 mm chamber over a two-tier grid, hung on three pegs on the back wall so the
3 kN goes into the frame, not into the spin chuck); **peel ring** (M5, fixed over the chip drain);
**orienting cone** (a Ø 90 → 30 mm funnel cup in which an elongated potato stands on end for the
fork); **pocket-band pallet** for Rouladen (M7) driven by the spin chuck; Rouladen cradle (M8);
board pallet; breading tray.

**Dosing and moving, by ingredient form.**

| Form | How |
|---|---|
| Whole produce | Box tilted onto a short brush-roller singulator (M4) at the dock; pieces roll one at a time into the orienting cone; the fork stabs at 50 N and carries the piece |
| Leafy | Tongs take handfuls from the open box into the spin basket on the chuck; water from the spindle; spin |
| Granular, powder | Dock tilt-pour into the vessel on the weigh pad, weight feedback |
| Seasoning | Shaker-lid spice box tapped over the weigh cup; the quill carries the cup to the vessel (never dosed above steam) |
| Liquid | Water through the spindle with a flow meter; other liquids tilt-poured or drawn with the 250 mL syringe tool |
| Paste | Syringe tool dips into the opened jar or tube-box; frozen blocks milled (M10) |
| Raw meat | Tongs for pieces; freeze platen for single slices; mince lifted with a scoop tool with W-driven ejector |
| Egg | Tongs from an egg-tray box to the cracking fixture (M6, a small two-cup fixture with its own rotation from the spin chuck) or whole into the pot |
| Frozen | IQF tilt-poured; blocks by tongs |
| Vessel to vessel | The hook lifts the vessel to a **pour bracket** on the side wall (a passive pivot the base ring hangs in); the quill then pushes the far rim up, so Z motion becomes tilt; the paddle scrapes while the quill's C turns it. Sticky masses go through the press pot instead (M13) |

**The hard operations.**

| Operation | How it is done | Numbers [E] |
|---|---|---|
| Peel potato / carrot | Workpiece in the spindle: fork stabs the piece in the orienting cone, the quill spins it at 200 rpm and pushes it down through the **peel ring** — three gimballed floating blades and three rollers that self-centre on any Ø 20–85 mm. The cap under the fork and the entry spot are faced off on a fixed blade; peel drops straight into the chip drain | 80 mm in 4 s; 20 s per potato; loss ≈ 20 % |
| Peel onion | Fork in the root end; a fixed blade draws one meridian slit during a Z stroke; the onion spins at 300 rpm in a fixed tangential fan jet (M5) | 8 s |
| Dice onion / potato | Piece dropped into the dice cassette; ram foot pushes it through the two-tier 10 mm grid at 5 mm/s; the blade bridge on the vessel rim, turning at 30 rpm underneath, cuts a cube every half turn; cubes fall into the same vessel. Other pitches = other cassettes (5, 10, 20 mm, slicer, wedger) | 0.9–2.3 kN; 15 s per piece; 1.5 kg potatoes in 3 min |
| Mince herbs | Rocking mezzaluna at 4 Hz walking across a board pallet in a CNC raster, turning 90° between passes; or the blade in a small Ø 80 cup for garlic | 20 g parsley in 40 s |
| Crack egg | Pipe-cutter fixture (M6); or, simpler, a W-actuated cracker tool: two blades score and spread over a cup | 8–10 s per egg |
| Frikadellen | Knead the mass in the bowl on the spin chuck; dump via the pour bracket into the press pot; nozzle plunger extrudes through Ø 60 mm; a wire on the turning vessel rim parts off pucks that drop onto a platen, from where the turner sets them in the pan | 100 g ± 5 % |
| Rouladen | Freeze platen lifts one slice onto the pocket-band pallet; syringe spreads mustard in a raster; tongs place bacon, gherkin, onion; the band rolls it (M7); the roll is tipped into the cradle (M8) | 40 s per roll |
| Bread a Schnitzel | Flatten under the Ø 110 foot in overlapping presses (1 kN). In one breading tray: sifter dusts flour; syringe lays egg wash, paddle spreads; crumbs shaken on; platen foot presses at 50 N; angle-head turner flips; repeat (R4 section 8 sequence) | 70 s per cutlet |
| Knead and roll out | Hook in the spindle, bowl counter-rotating on the chuck; roll out with the conical roller on the platen turning on the chuck | 1.5 kg, 20 Nm |
| Mash | Ricer plunger as a French press in the pot | 3.2 bar available |
| Toss salad | Basket spun dry; dressing from the syringe; two slow paddle turns with the bowl counter-rotating at 10 rpm | — |
| Flip steak / pancake | Pieces (steak, Schnitzel, patties): angle-head turner — slide under along the pan's low side, lift 40 mm, C turns the blade 180°. Whole-pan items (pancake, omelette, Rösti, tortilla, fish): **pan-to-pan flip on the flip bracket (M17)** — the hook sets a second, preheated pan rim-to-rim on the first, and the quill leads the pair through a half circle about the bracket pivot | turner 6 s per piece; pan pair 28 cm ≈ 4 kg, 5 s |
| Drain pasta | Hook lifts the basket out of the pot, holds it 20 s, sets it on the chuck for a 5 s spin if wanted | 1.5 kg basket load |

**Cleaning and drying.**

* *Tools: washed in the magazine.* Each holster is a small stainless pocket with a drain and three
  fixed jets aimed at that tool's geometry, fed from the sump loop (40 °C pre-rinse, 55 °C wash,
  80 °C rinse, warm air). A tool is rinsed within 2 min of use and is dry and ready again in about
  6 min [E]. The tool's socket bore is flushed from inside by the spindle before release. Once a day,
  and after raw meat, tools are carried to the wash chamber for the validated disinfecting
  programme.
* *Pallets, vessels, dies, fixtures:* hook → hand-over to the wash chamber.
* *The cell washes itself with a tool.* The quill picks up the rotary jet head (two 1.2 mm nozzles,
  5 bar, 4 L/min, ≈ 28 m/s) and runs a fixed CNC path 100 mm from every surface (M11). Deck, walls,
  ceiling discs and holster fronts total ≈ 2.6 m²; at a 150 mm swath and 50 mm/s one pass takes
  ≈ 6 min. Three passes (recirculated pre-rinse, recirculated detergent, fresh 80 °C rinse at
  2 L/min) ≈ 18 min and ≈ 16 L fresh water. Then the squeegee tool wipes the flat walls and deck in
  2 min, and 60 °C air finishes the corners. Because the path is a program, coverage is identical
  every day and can be validated once with riboflavin (HYG-019).
* *The quill itself* is a polished rod: it retracts through a flush ring and wiper in D2 after
  every job, and is jetted by one fixed nozzle while it rotates.
* *Ceiling discs.* Flat, flush, sloped 5°. The two seals are inflated for the wash and relaxed for
  motion; a drained leak-off groove behind each seal leads any seepage to the sump, never to food
  and never to the drives.
* *Deck.* One sheet; the spin chuck and the weigh pads rise through raised bosses (20 mm) so no
  seal stands in water.
* *Spray shadows.* The cell contains no mechanism at all apart from the quill; fixtures are
  removed before the wash. The holster row is the one structured surface and has its own jets.

**Off-the-shelf vs custom.** Standard: slewing rings, worm gear motors, ball-screw cylinder, servo
spindle motor, rotary union, inflatable seals, diaphragm pump, rotary jet nozzle, load cells, fin-ray
fingers, Vollrath/Nemco-type blade grids. Custom: the two discs, quill and interface, holsters, tools'
sockets (turned parts with an H7 bore), pallets.

**Genuinely novel.** The twin-eccentric sealed ceiling; the three-media spindle nose and the
resulting all-passive tool set; holsters as wash pockets; the machine washing and squeegeeing its own
enclosure by program; the vessel rim as the dicer's cut-off knife; "workpiece in the spindle" peeling
through a passive blade ring.

**Biggest weakness.** Everything hangs on one quill and two large seals: a seal failure or a jam
stops the whole kitchen, and the single spindle makes the concept strictly serial — a four-component
meal is a long queue of tool changes (I estimate 60–90 tool changes per reference meal at 8–10 s
each, i.e. 10–15 min of pure changing [E]). The 380 mm quill cantilever under 3 kN and 20 Nm also
needs a stiff, heavy ceiling.

---

### 1.3 Concept A3 — TURRET PRESS (dies index, one ram strikes, food falls)

**Core idea.** A turret punch press for food: one fixed 3 kN ram, an upper turret of feed tubes, a
lower turret of dies, and a carousel of vessels underneath, so that any tube can be brought over any
die over any vessel by rotation alone. Food moves by gravity from box to tube to die to vessel; every
cutting and forming operation is "push through a die", and patties are made exactly as an industrial
mould-plate former or a tablet press makes them. There is no manipulator in the basic machine.

```
 SIDE VIEW (section through the ram axis), column 600 x 600, working height 1150
        box dock + tilter        brush-roller singulator (wash, align, one by one)
   _________|__|________________________\\\\\\____________
  |          \ chute to tube at LOAD station  |           |
  |   RAM (3 kN, 300 stroke)                  v           |
  |      ||        stir quill (Z 250, C)    [tube]        |   upper turret: 6 feed tubes
  |  ====||=============||===================| |=======   |   O 480, tubes O 120 x 220 and
  |      ||   [tube]    ||                   | |          |   60 x 60 x 200, lip seals below
  |  ====[]=============[]===================[_]=======   |   die turret: 8 dies in a plate
  |   die: grid|ricer|nozzle|mould cavity|peel ring|blank |   O 480 x 15, anvil plate below
  |      --------- cut-off blade (1 axis) ---------       |
  |                                                       |
  |    [vessel]        [vessel]        [vessel]   [Wender]|   vessel carousel, 4 places,
  |  =====o===============o===============o===========    |   on load cells; tilt/flip station
  |__________________________________________________o____|   deck 3 deg, chip box, sump
  <------------------------- 600 ------------------------->
   central column carries three coaxial rotary drives (upper turret, die turret, carousel)
```

**Kinematics and actuators (10).** Ram (Z, 3 kN); upper turret rotation; die turret rotation; vessel
carousel rotation (three coaxial shafts up one central column — three rotary seals); cut-off blade
under the die plane; knock-out punch at the patty eject position; stir quill (Z and C: whisk, hook,
paddle and blade on a four-station star, no tool changer); "Wender" — a horizontal rotary axis that
grips a vessel by its ring and turns it over (pour, dump, flip); brush-roller singulator; dock
tilter.

**Tools, dies and vessels.** Feed tubes: 2 × Ø 120 (mass, dough, potatoes), 2 × 60 × 60 (produce),
2 × spare. A tube is an open cylinder whose silicone bottom lip slides on the die plate; **the die
plate is its floor** (M14). Dies in the plate: blank (floor for mixing in the tube), two-tier grids
5/10/20 mm, slicing harp, wedger, ricer plate 3 mm, Spätzle plate, puck nozzle Ø 60, mould cavities
Ø 90 × 15 and Ø 50 × 35, slot 120 × 4 (dough ribbon), rotating peel ring. Ram feet: flat with cross
slots, flat follower pistons with wiper lip. Vessels as 0.2.

**Dosing and moving, by ingredient form.**

| Form | How |
|---|---|
| Whole produce | Box tilted onto the helical brush rollers (wash, singulate, align); each piece drops end-on down a chute into the 60 × 60 tube at the load station |
| Leafy | Tilt-pour with shaking into the spin basket on the carousel (one carousel place has a spin drive) |
| Granular, powder, seasoning | Tilt-pour through a by-pass chute straight into the vessel on its load cells, or into a Ø 120 tube standing on the blank die when the mass will be formed |
| Liquid | Water valve over the vessel; other liquids tilt-poured; thin liquids never go into tubes (the lip seal is not liquid-tight) |
| Paste, fat | Frozen/chilled block in a 60 × 60 tube pushed against a grater die — dosing by stroke and weight (M10) |
| Raw meat | Pieces tilt-slid from the box into a tube or vessel; mince tipped into a Ø 120 tube |
| Egg | **Not solved without a handler**: needs the optional pick arm and the cracking fixture |
| Frozen | IQF by-pass chute; blocks dropped into the vessel |
| Vessel to vessel | Wender turns the vessel over the next one on the carousel; a fixed scraper bar wipes the wall as it turns |

**The hard operations.**

| Operation | How it is done | Numbers [E] |
|---|---|---|
| Peel potato / carrot | Ram foot with three spikes pushes the piece out of the tube through a **rotating** peel ring in the die turret (the bar-peeling machine: the cutter head turns round a non-rotating bar); the gimballed blades follow slopes to about 60° | unpeeled polar caps ≈ 13 % of area, faced off by the cut-off blade (≈ 4 % mass); 12 s per piece |
| Peel onion | Weak: top-and-tail with the cut-off blade, then push through a squeeze ring of silicone rollers that strips the outer layer (R4 2.1); expect 85–90 % success | below the 95 % target (UO-12) |
| Dice onion / potato | Ram pushes through the grid, cut-off blade swings every 5–20 mm of stroke: the Dynacube principle, motorised | 0.9–2.3 kN; 8 s per piece; 1.5 kg in under 2 min |
| Mince herbs | Bunch pushed down a tube against a fast cut-off blade taking 1 mm steps (a chiffonade), then the blade in a cup | coarse; fine mince marginal |
| Crack egg | Optional pick arm + M6 fixture | — |
| Frikadellen | Mince, egg, soaked bread, onion dosed into a Ø 120 tube on the blank die and mixed there by the stir quill's hook; turret moves the tube over the mould cavity, the ram fills it at 0.5 bar, the die turret indexes 45° (shearing the patty flat), the knock-out punch drops it into the pan below | mould-plate accuracy ± 1–2 % mass; 4 s per patty |
| Rouladen | A cassette whose band is fixed to the die turret and whose carriage to the upper turret: relative rotation of the two turrets by 40° gives a 150 mm stroke that rolls the band (M7). Loading the slice and filling needs the pick arm | awkward |
| Bread a Schnitzel | Flatten under the ram on a platen (1–1.5 kN). Cutlet in a shallow tray on the carousel: flour and crumbs from shaker boxes, egg poured, Wender flips tray-to-tray, ram presses at 50 N | coverage depends on spreading the egg by tilting only — doubtful |
| Knead and roll out | Knead in the Ø 120 tube or in a bowl with the hook (1 kg limit in the tube); sheet by extrusion through the slot die onto a tray, or press a dough ball to a disc between platens | 1–2 kN for a Ø 240 disc; thickness ± 1 mm doubtful |
| Mash | Potatoes in the Ø 120 tube over the ricer die, follower piston, ram: mash falls into the pot, skins stay in the tube | 3 kN / 113 cm² = 2.6 bar |
| Toss salad | Spin basket; dressing poured; Wender rocks the lidded bowl ± 120° three times | — |
| Flip steak / pancake | Not in the press; pan-to-pan flip at the Wender or double-sided contact heat in the cooking module (adapted method) | — |
| Drain pasta | Wender tilts the pot through a strainer lid into the drain | — |

**Cleaning and drying.**

* *To the wash chamber:* tubes (open cylinders — the easiest possible shape), follower pistons, ram
  feet, vessels. The transport system collects them at a port; they are lifted out of the turret
  by the Wender gripper.
* *Cleaned in place:* the die turret plate with its dies, the anvil plate, cut-off blade, stir star,
  ram rod, chutes, walls. The die plate is the critical part: it is a flat disc with through
  holes — no blind cavities — and it **rotates through a fixed wash sector** at the back of the
  column (a hood with jets above and below and a squeegee lip at its exit), like a turntable under
  a fixed nozzle bar. One revolution at 2 rpm washes every die from both sides; the anvil plate is
  washed by the same sector from above once the die plate is lifted 10 mm. The stir star is washed
  in a vessel of hot detergent solution that it stirs itself, then rinsed by jets.
* *Water* runs down the central column and the deck to the chip box and sump.
* *Drying:* warm air; the turrets spin at 120 rpm to shed water.
* *Crevices:* grid dies are blades in a frame — blade roots are the soil trap; they must be
  monobloc (wire-eroded or laser-welded and polished) and are the first candidates for a daily trip
  to the wash chamber instead of in-place washing, which needs a die exchanger and weakens the "no
  manipulator" idea.

**Off-the-shelf vs custom.** Standard: electric press cylinder, three hollow-shaft rotary tables or
worm drives, blade grids, ricer plates, Formax-type geometry (well documented), load cells. Custom:
both turret plates, tubes with lips, Wender, peel ring.

**Genuinely novel.** The two-turret "any tube over any die" arrangement for food; mixing in the feed
tube with the die plate as floor; using relative turret rotation as a free linear stroke; the die
plate washing itself by rotating through a wash sector.

**Biggest weakness.** Gravity only runs downhill and a press only pushes: everything that must be
picked, placed, turned or spread (eggs, meat slices, fillings, breading, layering, stirring in a pan)
is outside the principle and needs an added pick arm, after which the concept loses its simplicity.
My estimate is 80–85 % of the UO list without the arm. The lip-sealed tube on a rotating plate also
smears raw meat mass over the die plate at every index.

---

### 1.4 Concept A4 — BELT & BLADE (conveyor bed, powered blades, no force)

**Core idea.** Food rides a washable homogeneous belt past fixed, powered reciprocating blades, so
cutting forces are a few newtons and no knife ever needs an anvil or a board. The belt is the
universal handler: it feeds, meters slice thickness, carries items under sifters and rollers
(breading, sheeting), flips them at its nose, forms a pocket that rolls Rouladen and rounds
dumplings, and "pours" by simply running. It is the opposite of A2 and A3: light, fast, low-force,
and at its best with exactly the flat and limp items the press concepts cannot handle.

```
 SIDE VIEW, wet cell 800 W x 520 D x 600 H (module 900 W), belt 380 wide
  dock/tilter   rocker rod R (through back wall): Y 350, phi; stations: sheeter roller,
     \          platen, sifter, return tray, freeze platen, syringe
      \ chute          ___(R)___            G2 frame blade (12 blades, pitch 10, lifts out)
       v              /  roller \           | G1 cross blade (guillotine, reciprocating)
  tail ram ->[press pot]=============================|  |
  1.5 kN     ( o )  belt, PU homogeneous, 3 mm   ( o )|  |   nose bar R 8, gap 4 mm
             drive  \________      ________/          |  v
                  pocket rollers  (close 50 -> 12)     [vessel on weigh pad] / pan
                         \  dancer  /  <- drops 60 mm to form the rolling pocket
                          \__( o )_/
             scraper + spray bar + air knife on the return run
  _______________________________________________________o________  deck 3 deg, chip box
  <--------------- belt working length 480 -------------->|<- 200 ->
   bowl station with top spindle (Z, C) at the far right for mixing, kneading, puree
```

**Kinematics and actuators (12).** Belt drive (reversible, 0–200 mm/s, encoder); dancer (belt
pocket depth); pocket rollers (closing); rocker rod Y (across the belt) and φ (selects one of six
stations on the rod and lowers it — the rod is the whole "gantry" and is a round rod through the
back wall); cross blade G1 stroke and its oscillation drive (rocking shaft through a rotary seal,
10 mm at 40 Hz, 60 W); frame blade G2 lift (shares the oscillation drive); tail ram (1.5 kN,
extrudes masses onto the belt); bowl-station spindle Z and C; dock tilter.

**Tools and vessels.** On the rocker rod: sheeter/press roller Ø 60 (gap to belt set by φ,
0–40 mm), flat platen, sifter for flour and crumbs, return tray, freeze platen (M9), syringe head.
Blades: G1 one scalloped blade 400 mm in a bow frame; G2 a monobloc frame of 12 blades. Press pot
with nozzles at the tail. Bowl station: hook, whisk, paddle, blade (exchanged by the transport
system with the bowl, as in A1). Vessels as 0.2, plus the Rouladen cradle.

**Dosing and moving, by ingredient form.**

| Form | How |
|---|---|
| Whole produce | Tilted onto the belt between two converging guide rails that align the long axis with the belt; pre-peeled by a small brush/abrasive roller pair above the belt, or skin-on |
| Leafy | Tilted onto the belt, spray bar above, belt carries it to the spin basket at the nose; lettuce heads are cut into ribbons by G1 on the way |
| Granular, powder | Dock tilt-pour past the belt directly into the vessel at the nose (by-pass chute); flour for dusting via the sifter |
| Liquid | Water valve; others tilt-poured into the vessel; egg wash from the syringe head |
| Paste | Syringe head lays tracks on the belt or on the slice (mustard on a Roulade in a raster: belt gives X, rod gives Y) |
| Raw meat | Pack emptied onto the belt; the freeze platen separates slices; the belt carries everything else |
| Egg | Cracking fixture (M6) at the bowl station; not a belt operation |
| Frozen | By-pass chute |
| Belt to vessel | The belt runs; the nose scraper leaves < 1 % even of sticky masses. Bowl to belt: masses come through the tail press pot |

**The hard operations.**

| Operation | How it is done | Numbers [E] |
|---|---|---|
| Peel potato / carrot | Weakest point: no lathe. Twin abrasive-roller bed over the belt tail (roller peeler), 60–90 s per 1.5 kg batch with spray; or skin-on plus ricer | loss 15–25 %, eyes remain |
| Peel onion | G1 tops and tails it; slit by a fixed blade in the guide rail; roller bed with air/water jet strips the skin | 90 % [E] |
| Dice onion / potato | Two passes. Pass 1: G1 cuts slabs of thickness p, which fall onto the return tray; the rocker swings the tray over and lays them flat on the belt. Pass 2: the belt feeds them through the frame blade G2 (strips) and G1 cuts every p mm (cubes) | feed 20 mm/s; 1.5 kg potatoes ≈ 42 s + 10 s + 15 s; pitch 10 mm from G2, any length |
| Mince herbs | Belt feeds the bunch into G1 at 1 mm steps at 8 cuts/s; a second pass turned 90° by the return tray | 20 g in 20 s |
| Crack egg | M6 fixture at the bowl station | — |
| Frikadellen | Tail ram extrudes the mass as a Ø 60 "bar" onto the belt; G1 parts off 25 mm pucks; the roller flattens and rounds the edges; the belt lays them in the pan | 100 g ± 5 %; 3 s per piece |
| Rouladen | Freeze platen lays one slice on the belt; syringe rasters mustard; filling pieces arrive on the belt (G1-cut gherkin, onion, bacon) and are laid on by the platen; the dancer drops, the slice sags into the pocket, the pocket rollers close to 12 mm, the belt runs 250 mm and the slice rolls up tight (M7); the pocket opens and the roll is carried to the cradle (M8) at the nose | 20 s per roll |
| Bread a Schnitzel | The industrial flat-bed breader in miniature. Roller flattens the cutlet in three passes (belt + roller = sheeter, 300 N); sifter dusts flour; syringe lays egg, roller spreads at zero load; belt carries a crumb bed under the cutlet, sifter crumbs on top, roller presses at 50 N; **nose flip** onto the return tray and back for the second side | 45 s per cutlet |
| Knead and roll out | Knead at the bowl station; dough through the tail press pot onto the belt; reversing sheeter passes with the roller gap stepping down | 2–10 mm ± 0.5, sheets up to 380 × 450 — tray size |
| Mash | At the bowl station with a ricer plunger (needs a 3 kN spindle there) or by the tail ram through a ricer nozzle | — |
| Toss salad | Bowl station, paddle | — |
| Flip steak / pancake | Not a belt job; turner on the bowl-station spindle or contact heat | — |
| Carve roast, slice bread, tomato, cucumber | The cross blade in the gap: belt advance = slice thickness, any value from 1 mm | the best slicer of the four concepts |
| Drain pasta | Basket lifted by the bowl-station spindle | — |

**Cleaning and drying.**

* *The belt cleans itself continuously,* as food-industry belts do: a homogeneous PU belt (no fabric,
  no hinges, sealed edges) on a cantilevered frame; on the return run a scraper, a spray bar at
  40–80 °C and an air knife. Washing the belt is "run three turns": 1.2 m of belt in 20 s per turn.
  Drive drum and rollers are smooth and cantilevered from the back wall (rotary seals), so both
  faces of the belt and all rollers are open to the jets.
* *Blades* reciprocate in a spray curtain (G1 and G2 are open frames; G2 is monobloc). G2 and the
  rocker stations are removable cassettes that go to the wash chamber daily.
* *Rocker rod* retracts through its flush ring; its stations are jetted by fixed nozzles while φ
  rotates them past.
* *Cell:* fixed rotary nozzle in the ceiling plus the usual wash-down-lite; water → deck → chip box
  → sump.
* *Drying:* air knife on the belt, warm air in the cell.
* *Weak spots:* belt edges and the underside of the belt over the slider bed (the bed is replaced
  by three open rollers to avoid a lapped joint); belt tracking; a knife mark on the belt is a
  hygiene defect, which is why no blade ever cuts against it — both blades cut in the 4 mm gap
  beyond the nose.

**Off-the-shelf vs custom.** Standard: homogeneous PU belting and drums (Volta/Habasit class), bread
slicer frame blades, electric-knife blade geometry, sheeter roller, electric cylinders. Custom:
pocket-roller/dancer unit, rocker stations, blade frames, tail press.

**Genuinely novel.** The pocket belt as Roulade roller; the single rocker rod as a sealed "gantry";
powered blades in the nose gap so that the belt meters every cut; the return tray that turns a
one-direction slicer into a dicer; breading, flattening and sheeting with one roller.

**Biggest weakness.** A belt is 1 m² of flexing food-contact polymer that must be validated as
clean after raw meat every time, and it wears; and the concept needs a complete second station for
everything that happens in a bowl, plus a weak answer for peeling. It is a superb second machine, a
doubtful only machine.

---

### 1.5 Check against the meal corpus (R2)

R2 changes the picture in four ways.

**(a) Vessel sizes.** A 10 L bucket, a 9 L boil pot and a 36 cm pan are needed at 6 persons.

| Concept | Consequence |
|---|---|
| A1 | The trunnion must swing a Ø 270 × 200 bucket and a 36 cm pan: pivot height 520 mm, cell height 1100 mm, tilt drive 100 Nm (9 kg strainer-lidded pot at 320 mm = 28 Nm static). The 9 L pot is better never chucked: drain by basket |
| A2 | The reach circle of one quill (Ø 480, limited by the 520 mm depth) holds one large vessel plus small stations, not a bucket and a pan side by side. For a 6-person meal it becomes **one 1200 mm cell with two twin-disc quills** — a preparation quill over the spin chuck, press bracket and dock, and a pan quill over two induction zones with the flip bracket — sharing a hand-over pad. 15 axes instead of 8; it also removes the serial bottleneck and gives limp-home redundancy |
| A3 | Carousel places for Ø 270 vessels need a Ø 640 pitch circle: the column grows to about 750 × 600, or the carousel drops to three places |
| A4 | Unaffected: the belt discharges into whatever stands at the nose; the bowl station needs the 10 L bucket |

**(b) Operations that cannot be bought away** (R2 4.5: flip 12.9 %, assemble 6.9 %, carve 4.8 %,
unmould 4.4 %, score 2.8 %, poach 0.4 %; union 29 % of meals). These are all pick, place, turn and
draw-cut operations — exactly what A1 and A3 lack.

| Operation (share of meals) | A1 | A2 | A3 | A4 |
|---|---|---|---|---|
| FLP flip (12.9 %) | Pan-to-pan dump-flip on the trunnion: good, including pancakes; needs the pan on the trunnion, away from the heat, for 5 s | Turner for pieces, M17 pan pair for pancakes: good | Wender pan-to-pan: fair | None; relies on two-sided contact heat |
| ASM assemble / layer (6.9 %) | No placing ability: **fails** | Tongs, freeze platen, vacuum cup, syringe, sifter over a dish on the deck: good, slow | Only pourable layers: **fails** | Layers ride the belt and are laid into a dish moving under the nose, as on a lasagne line: good |
| CAR carve cooked meat (4.8 %) | **Fails** (no draw knife, no hold for a hot roast) | W-driven reciprocating carving knife (20 mm stroke, 5 Hz), C-oriented, roast on a spiked board pallet; or M15 as a wall fixture: fair | Roast in a tube, pushed past the cut-off blade: fair, slices 2–15 mm | Cross blade in the gap: the best, any thickness |
| UNM unmould (4.4 %) | Trunnion inverts the mould over a plate with a jolt: good | Flip bracket inverts mould onto plate, air through the syringe tool along the wall: good | Wender: good | Bowl station only: weak |
| SCO score (2.8 %) | Slitting blade on the platen, polar paths only: fair | Knife tool on any CNC path: good | **Fails** | Rocker knife wheel on the dough sheet (never through to the belt): fair |
| POA poach (0.4 %) | Cup vessel | Cup vessel, egg lowered by tongs | Cup vessel | Cup vessel |

**(c) The big avoidable blockers** (R2 treats them as "buy first, build later"; my concepts build
them):

| Operation (share) | Answer from this lens |
|---|---|
| PLA peel onion/garlic (52 %) | M5 slit-and-jet on the lathe (A1) or on the fork (A2): a real mechanism in both; A3 and A4 only reach about 85–90 % skin-free and would buy peeled onions |
| COR core / deseed / hull (20 %) | A punch is the natural die: tube corer with ejector through apple, pear, tomato stalk, strawberry hull (A1 hollow tailstock; A2 W-ejector corer tool, 100–200 N; A3 corer die under the ram). Pepper: part off the cap, then spin the open pepper mouth-down over a jet — seeds leave by coolant flush (A1, A2). A4 has no answer |
| TRE trim ends (12.5 %) | Probe length, part off both ends: lathe parting knife (A1), workpiece in tongs past a fixed blade (A2 with M15), cut-off blade (A3), belt and cross blade (A4). All good; this is what probing is for |
| PLS / PLH peel soft and knobbly (10.5 % / 7.3 %) | Floating blade follows an apple or a kohlrabi as well as a potato (A1, A2). Celeriac, ginger, pumpkin: cut-away peeling on the fork against M15 in flat facets, loss ≈ 30 % as R2 expects. Tomato and peach: blanch and jet |
| SEP separate egg (6.9 %) | M6 with the lower cup tilted; or suck the yolk off the cracked egg with the syringe tool |
| STU stuff (6.5 %) | Rigid cavities (pepper, tomato) stand in a cone pallet; filling extruded from the syringe tool or the press-pot nozzle by weight. Flat pockets are not solved |
| WRP / RLT wrap, roll and tie (4.0 % / 1.6 %) | Pocket band M7 and cradle M8; in A1 mandrel winding. R2 calls roll-and-tie "no solution known" — M7 + M8 is my answer and the first thing I would prototype |
| FRM / SHD shape by hand, shape dough (2.8 % / 2.4 %) | Extrude-and-part-off (M13, M14) for pucks, dumplings, gnocchi, Spätzle; pocket band for rounding rolls and Klöße; braids and pretzels stay excluded (X-09) |
| BRD bread (2.0 %) | Flat-bed breading: A4 best, A2 and A1 workable, A3 doubtful |
| PLE peel boiled egg (2.8 %) | Tumble 10 s in the spin basket to craze the shell, then jet while rolling on the brush rollers (M4); unproven |
| STR strip / pluck (3.6 %), PIT (1.2 %), SKW (0.4 %) | Not solved in any concept beyond a punch for stones; buy prepared |

**(d) Rough coverage per concept under R2 scenario S0** (nothing bought pre-processed), my own
judgement from the tables above, not a walk-through: A2 ≈ 93–96 %; A4 with its bowl station ≈ 85 %;
A1 ≈ 80 % (loses assemble and carve outright); A3 ≈ 65–70 % without a pick arm. Under S1 (peeled,
trimmed, boneless bought) A2 and A4 reach the mid-90s, A1 stays below 90 %, A3 below 80 %.

---

## 2. Standalone sub-mechanisms (usable in any concept)

**M1 — Expansion-mandrel spindle nose ("HydroDorn").** The spindle ends in a closed, smooth, polished
mandrel Ø 25 × 40 mm that expands 0.03–0.06 mm hydraulically (the hydraulic expansion chuck turned
inside out). Every tool is a plain part with an H7 bore. A disc-spring stack holds the pressure;
pulling the central rod releases it, so tools stay clamped on power loss. Grip ≈ 80–150 Nm and
several kN axial [E from 20–40 MPa contact pressure, µ 0.1]; compressive loads go into a shoulder. No
balls, keys, threads or tapers facing the food; air blast through the spindle clears the bore before
each change. *Feasibility: medium–high; the principle is standard in tool holding, the thin sleeve
(17-4PH) is a wear part, and a rice grain in the bore stops a change — hence the air blast.*

**M2 — Three-media coaxial interface.** Through the mandrel run (a) torque, (b) a push rod with
20 mm stroke and 300 N, (c) a fluid channel for water, air or vacuum. The push rod makes passive
tools active: tongs, syringe, scoop with ejector, stripper, rocking mezzaluna, cracker. The fluid
channel doses water, flushes the tool from inside, feeds the wash head and holds a vacuum cup. No
tool contains a motor, cable or air hose. *Feasibility: high; this is a machine-tool drawbar plus
through-spindle coolant. The rod seal at the mandrel tip is the delicate part.*

**M3 — Twin-eccentric disc penetration.** Two nested rotating discs in a flat ceiling or wall, the
quill through the inner one: two rotations position the quill anywhere in a circle of radius
e1 + e2 (240 mm with 120 + 120). Only rotary seals face the food; the surface stays flat and
flush. Inflatable seals are relaxed to move and inflated to wash; a drained groove behind each seal
catches seepage. *Feasibility: medium; seal length is 2.4 m, friction ≈ 15 Nm on the large disc [E],
and the flatness of a Ø 500 disc under a 3 kN quill load needs a proper slewing ring.*

**M4 — Helical twin brush rollers.** Two parallel brush rollers Ø 60 × 300 with a helical bristle
pattern, counter-rotating under a spray: they scrub potatoes and carrots, align the long axis with
the rollers, convey and hand out one piece at a time at the end (screw action), and then serve as
V-block and steady rest for the lathe. Four jobs, one motor. *Feasibility: high; roller brush
washers and roller singulators are industry standard. Brushes are a hygiene item and must be
removable to the wash chamber.*

**M5 — Slit-and-jet onion skinning.** One shallow meridian slit (2 mm), then the spinning onion
(300 rpm) meets a flat fan jet of mains water (4 bar, 2 L/min) aimed tangentially against the
rotation at the slit: the jet gets under the dry skin and the first fleshy layer and unwinds them in
3–5 s. Garlic cloves the same in a small cup. *Feasibility: medium; industrial onion peelers do
slit-plus-air-blast, water is my substitute to avoid a compressor. Wet skins stick to walls — the
chip drain must be directly below.*

**M6 — Pipe-cutter egg cracking.** The egg is held on its long axis between two soft vacuum cups and
rotated once against a carbide point at 1–2 N, scoring the shell all round (0.3 mm); the cups then
pull apart with a slight twist. The shell parts along the score like a cut glass tube, the membrane
tears, the contents drop with the yolk untouched, and each cup still holds its half shell for
disposal. Scoring dust falls before the egg opens (the catcher flap is on "chip"). The same fixture
separates: the lower cup tilted to 45° holds the yolk in the half shell while the white runs off.
*Feasibility: medium; scoring raw shells cleanly needs testing on thin and thick shells; fallback is
the classic blade-and-spread cracker.*

**M7 — Pocket band ("cigarette roller") for Rouladen, dumplings and rolls.** A flexible food-grade
band hangs as a slack pocket between two rollers 50 mm apart. The slice with its filling is laid
over the pocket, sags in, the rollers close to 12 mm, and the band is driven: the contents turn in
the pocket and wind up tightly; opening the rollers ejects the roll. With a lump of dough or dumpling
mass it rounds instead of winding. *Feasibility: medium–high; hand cigarette rollers, sushi and
vine-leaf rollers work exactly so. Open points: starting the first turn of a limp meat slice
(a 10 mm fold made by the closing roller), filling squeezed out at the ends.*

**M8 — Rouladen cradle: the fixture stays with the workpiece.** A stainless comb rack with 4–8
U-shaped slots (40 × 45 × 130 mm) into which each Roulade is put seam down. The cradle goes into the
braising pan with the rolls in it, holds them closed through searing and two hours of braising, and
is lifted out with them for plating. No twine, no picks, no clips, nothing for the eater to remove.
The same thinking works for stuffed peppers and cabbage rolls. *Feasibility: high; open point is
browning on the sides shadowed by the comb (use wire, not sheet).*

**M9 — Freeze fixture and freeze gripper ("ice vice").** Machine shops clamp thin or irregular
parts by freezing them to a plate. A Peltier platen at −10 °C touched onto a wet meat slice freezes
to it in 5–15 s [E] and lifts exactly one slice off a sticky stack; reversing the current releases
it in 2 s. As a fixture it holds fish fillet, liver or a cutlet flat and immobile for clean strips
and cubes, with the contact layer stiffened. The platen face is a flat stainless sheet. *Feasibility:
medium; cryo-grippers exist for textiles and food. Needs ≈ 60 W of Peltier and a heat path — the
only tool that would need electrical contacts, unless cold is "charged" in the holster and the
platen is a passive thermal mass (200 g aluminium core in a stainless skin holds for one pick).*

**M10 — Dosing by machining: keep sticky things as bar stock.** Butter, tomato paste, stock
concentrate, fresh herbs, ginger, garlic paste and cheese are stored as frozen or chilled blocks in
their box. The box is the vice; a grater disc or face cutter on the spindle (or a ram pushing the
block over a fixed grater die) removes shavings until the weigh pad says stop. 20 g of butter ± 1 g
without any pump, spoon or smeared spout; the dose is already finely divided and melts at once.
Grating cheese, carrot and potato is the same cycle. *Feasibility: high for butter, cheese, frozen
herbs, frozen paste; pastes that do not freeze firm (mustard, honey) stay with the syringe.*

**M11 — The wash tool and the programmed wash path.** The enclosure is washed by a spindle-held
rotary jet head that follows a fixed CNC path at constant stand-off, then by a spindle-held squeegee
that wipes flat walls dry — the machine-tool "chip fan" idea. Coverage is a program, identical every
day, validated once with riboflavin and re-checked by the cell camera under UV. Stubborn spots found
by the camera get a local repeat instead of a full cycle. *Feasibility: high wherever a positioning
axis reaches all walls (A2); needs flat walls and nothing fixed in the cell.*

**M12 — Tools ride with their vessel.** A ring holder on the vessel rim carries the two or three
tools that vessel will need. The clean kit is assembled in the clean-ware store, the spindle picks
tools from the vessel in front of it (the vessel indexes), and when the job is done the tools are
dropped back into the soiled vessel and both go to the washer together. No tool magazine in the wet
cell, no dirty tool ever parked next to a clean one, no separate tool transport. *Feasibility: high;
costs spare tools (one hook per bowl instead of one per machine).*

**M13 — Syringe pot ("Kolbentopf").** A vessel made of a plain tube and a loose piston floor with a
moulded wiper lip. Mix or knead in it; then a ram pushes the floor and the contents leave through
whatever die closes the top: wide open (dough, mince, mash transferred with < 1 % residue instead of
5–15 %), nozzle (pucks, dumplings), ricer plate, Spätzle plate, slot. For washing it falls apart
into a tube and a disc. The storage-box version — a box with a push-out floor — turns a box of mince
or quark into a cartridge. *Feasibility: high; open point is the lip seal on thin liquids.*

**M14 — Feed shoe on a die plate (mould-plate former).** An open tube slides on a plate that is its
floor; move it over a cavity, press, slide away, knock out. This is how patty formers and tablet
presses reach ± 0.5–2 % by mass. With a blank plate position the same tube is a mixing vessel.
*Feasibility: high for stiff masses; smear on the plate must be washed off after each batch.*

**M15 — Fixed powered blade, workpiece under CNC ("wire EDM for food").** A tensioned scalloped
blade (or a plain wire for cheese, butter, eggs) reciprocates 10 mm at 40 Hz in a bow frame fixed in
the cell; the workpiece is moved through it on a fork, in tongs or on a belt. Feed force is a few
newtons for bread, roast, tomato and raw meat alike, so the axes can be light; no anvil or board is
ever cut into; partial-depth cuts are trivial, which gives the cook's onion method (two sets of
cuts stopping short of the root, then slices) on any produce. Cut pieces fall straight down.
*Feasibility: high (electric carving knives, bread frame slicers); blade fatigue and the root stub
(10–15 % of an onion) are the costs.*

**M16 — Vessel rim as cut-off knife, and spin as a universal process.** A blade bridge clipped
across the rim of a vessel rotating on the spin chuck cuts off whatever a die above extrudes, and
the pieces fall into that same vessel — a dicer with no cut-off actuator. The same chuck spin-dries
salad, drains pasta, spin-coats egg wash on a cutlet, flings wash water, and dries the vessel to
below the 0.5 g limit of HYG-024 (800 rpm, 86 g at the rim [E]) before it is stored. *Feasibility:
high; balance of unevenly loaded baskets limits the speed.*

**M17 — Flip bracket: pan-to-pan, mould-to-plate, with no flip actuator.** A passive pivot on the
wall in which a vessel's base ring hangs. A second vessel (preheated pan, plate, platen) is set
rim-to-rim on the first and held by a spring clip ring; the spindle, holding the far rim with the
hook tool, leads the pair through a half circle about the pivot — the CNC axes trace the arc, the
bracket carries the weight. One motion flips a whole pancake, omelette, Rösti or fish fillet, and
unmoulds a cake or pudding onto a plate; stopped at 100–130° it is the pour bracket. *Feasibility:
high; this is the Spanish-tortilla plate flip. Needs a second hot pan (cooking module) and hot oil
must be poured off first.*

Further small ideas, one line each: a cutting board that the machine re-faces itself with a planing
cut once a month (plastic swarf in a food cell — doubtful); a pin roller meshing with a blade grid
like rack and pinion, so a slice is rolled through the grid at 200–500 N instead of pressed at
2 kN; a passive pour bracket that turns the quill's Z stroke into vessel tilt; weighing with the
Z axis (a load cell in the quill makes every lifted vessel or cup a weighing).

---

## 3. Which concept I would bet on

**A2, the ceiling-quill machining centre — with A1's spin chuck in the deck (already included), A3's
dies as cassettes, and A4's pocket band as a pallet.**

Reasons:

1. **Coverage.** It is the only one of the four with a real answer for every row of the hard-operation
   table and every ingredient form, because it can pick and place as well as press and spin. A1 and
   A3 fail on flat and limp items; A4 fails on peeling and needs a second station. The meal corpus
   sharpens this: the operations that cannot be bought away (flip, assemble, carve, unmould, score —
   29 % of meals) are all pick, place, turn and draw-cut operations, and A2 is the only concept
   that does all five (section 1.5).
2. **Cleanability is structural, not added.** The wet cell contains one polished rod and flat
   stainless sheet; everything food-specific is a removable passive part. The wash is a program with
   reproducible coverage. That matches the brief's strongest requirement better than any design with
   turrets, belts or trunnions inside the cell.
3. **The machine-tool division of labour is right for a product that must reach 95 %.** A missing
   operation is solved by designing one more tool or pallet — a stainless part — not by changing
   the machine. The long tail of the meal corpus becomes a tooling catalogue.
4. **Actuator count is the lowest** per spindle (8), and they are standard industrial parts. The
   corpus vessel sizes push it to a 1200 mm cell with two quills (15 axes), which I would accept:
   two identical units, twice the throughput, and a kitchen that still cooks with one quill down.

What I would check first, because the bet fails if they fail: (a) the twin-disc seals in a washed
and steamed cell over 10 000 cycles, with a plain XY gantry behind a roll-up stainless cover as
fallback; (b) the expansion mandrel with wet, starchy, greasy tool bores; (c) total tool-change time
per meal with two quills; (d) peel-ring quality on ugly potatoes; (e) the pocket band and cradle
for Rouladen, since the brief names them and R2 knows no solution.

If the customer wanted the most *original* machine rather than the safest bet, it would be A1: the
lathe treatment of onion, egg and Roulade is where this lens produced things I have not seen
elsewhere, and its mechanisms (M5, M6, mandrel winding) should be carried into P3 as fixtures for A2
whatever concept wins.

---

## 4. Open issues

1. The coverage figures in section 1.5 are judgements per operation, not recipe walk-throughs; P3
   must walk real corpus meals through each explored concept. The sketches of A1–A3 still show the
   Ø 240 pot and must be redrawn for the R2 vessel family.
2. Peeling is solved on paper three ways (lathe blade, peel ring, rotating ring) and proven in none;
   eyes, green spots and kidney-shaped tubers need a test rig. The skin-on/ricer strategy of R4 stays
   the fallback.
3. Onion: the jet-skinning rate, and whether radially cut layers hold together until the cross cut.
4. Where the hob is relative to the spindle, and whether flipping is a preparation tool (turner) or a
   cooking-module feature (two-sided contact heat); both assumed possible here.
5. Holster washing (A2) is a quick rinse, not the validated disinfecting cycle; the rule for when a
   tool must go to the wash chamber (after every class R contact) drives the number of spare tools.
6. Dice pitch is set by the die (5/10/20 mm), not freely programmable, in A1–A3; only M15 gives
   free pitch.
7. Rouladen without fastening (M8) changes how they are seared; needs a cooking trial.
8. Noise of spin-drying, of the 40 Hz blades and of a 3 kN press stroke has not been estimated.
9. Vessel base ring (three-lug bayonet) must be agreed with storage, transport, hob and wash rack in
   the architecture (A1 task) before any of this is detailed.

## 5. Risks

| Risk | Concept | Consequence | Mitigation |
|---|---|---|---|
| Large rotary seals leak or wear | A2 | Water or condensate into the drive space; hygiene failure above food | Double seal with drained groove, inflated only for washing, LRU from above; fallback gantry |
| Single spindle is a single point of failure and a serial bottleneck | A2 | Kitchen down; PERF time targets missed | Second light quill; tools ride with vessels (M12) to cut changes |
| Expansion mandrel jams on soil | A1, A2 | Tool change fails | Air blast, flushed bore, polygon-taper fallback |
| Blade grids hold soil at blade roots | A1–A3 | Fails HYG-020 after onion or potato starch dries | Monobloc grids, rinse within 2 min, wash chamber after each use |
| 3 kN ram and 800 rpm spin behind a household door | A1–A3 | Mechanical hazard | Interlocked door, force and speed limits with the door open (section 11.4 of the requirements) |
| Belt hygiene after raw meat | A4 | Cross-contamination to RTE food | Separate class R session followed by a hot belt wash; or a second belt |
| Lathe needs a well-centred, firm workpiece | A1 | Soft, sprouting or very irregular produce is dropped or torn | Probe first, reject to skin-on route |
| Too many custom stainless parts | all | Cost and lead time against the "standard parts" constraint | Freeze one tool socket, one base ring and one die frame, and make everything else from turned, laser-cut and welded parts |
