# K7 — State change and rigid handling (ZUSTAND cell)

Round P3 exploration of candidate K7 (catalogue section 3.8; source W25 = F:D "ZUSTAND").
Written without reading the other files in `design/prep/concepts/`.

Inputs read: `BRIEF.md`, `DECISIONS.md`, `design/prep/03-exploration-brief.md`,
`design/prep/02-concept-catalogue.md` (complete), `design/prep/ideas/F-first-principles.md` (complete),
the cold-related mechanisms of idea files A (M9, M10), B (N12), C (S-9, S-24), D (N1, N19) and concept B of
E (loose ware, drip collar, 3-minute washer), `requirements/requirements.md` sections 3.5, 3.6, 5, 6, 7,
`research/02` (key results, the 248 rows by script, section 6.3), `research/04` sections 2, 4, 7, 8,
`research/05` section 11, `research/06` sections 2.2–2.5 and 6, `research/08` sections 2.3, 3.1, 5.1.
Not read: `research/01`, `03` (only the cold-store paragraphs), `07`.

Tags: **[C]** = calculated in this round (method given, can be redone); **[E]** = my estimate;
**[F]**, **[R2]**, **[R4]**, **[R6]**, **[R8]** = taken from that document; **[K]** = general knowledge of
existing practice, not verified in this session. Nothing here has been built or tested. Confidence ratings:
high / medium / low.

Contents: 0 verdict in brief · 1 definition and layout · 2 mechanism · 3 thermodynamics and refrigeration ·
4 intake and dosing · 5 operation table · 6 benchmark walk-throughs · 7 cleaning · 8 numbers ·
9 coverage and the adapted-method count · 10 failure modes · 11 risks and kill experiments ·
12 improvements, changes from the catalogue definition, borrowings · 13 answers to the catalogue's
questions · 14 open issues and requests to the architect.

---

## 0. Verdict in brief

1. **The physics works.** A one-dimensional enthalpy calculation confirms F's Plank estimates within ±20 %:
   a 6 mm cutlet is a rigid plate after 55–115 s between two −25 °C plates, a 25 mm patty has a 3 mm crust on
   both faces after 110–150 s, a Roulade seam is frozen 6 mm deep after 4.4–5.7 min (section 3). The heat to
   be removed is small: 30 kJ per cutlet, 7 kJ per patty, 80–240 kJ per meal. A 21 kg aluminium plate stack
   absorbs a whole meal with a temperature rise of 4–12 K, so a 200–300 W freezer-class compressor is enough.
2. **The concept is a booster, not a kitchen.** Tempering is decisive for about 12 of the 248 corpus meals
   (breading, flat pockets, staged patties, croquettes), useful for about 40 more (cutting soft things, fast
   chilling, unmoulding, dosing pastes as pieces), and irrelevant for the rest. Everything a kitchen needs
   besides — a press with dies, a raw peeler, a kneading bowl, a whisk, a sink — must still be there. The
   cell described here therefore has 24 actuators and about 110 loose parts; "only a plain gantry, trays and
   a knife" is not true once the corpus is walked through.
3. **Three statements of the catalogue definition did not survive the calculation** and were changed
   (section 12): the "tacky thawed film after 30–60 s" does not exist (the surface stays below −2 °C for
   more than 5 minutes), so flour must go on *before* freezing; a double plate with a moving refrigerated
   upper plate is replaced by fixed evaporator plates with loose cold slabs; the band knife is replaced by a
   reciprocating bow knife that is one loose part.
4. **Benchmarks:** 11 of 12 "yes", 1 "adapted" (B7, oven fries, by requirement X-01). Coverage estimate
   **92–94 %** (229–233 of 248), below the 95 % target; what falls out is the wrapping of limp sheets
   (cabbage leaf, tortilla, strudel, sponge, wrappers), which this concept excludes by definition.
5. **Adapted-method budget:** the requirements themselves already spend 19 of the 24 permitted meals
   (section 9.3). K7 is inside the 10 % only if crust-freezing is ruled a handling aid and not an adapted
   method (then 8.5 %); counted strictly it is at 13.3 %.

---

## 1. Definition

### 1.1 What the cell is

A wash-down bay with one Cartesian gantry (X, Y, Z, one horizontal wrist axis, one clamping jaw) that moves
only loose ware: thin steel trays with a standard grip tab, lid sheets, cassettes and one-piece stem tools.
Food is never gripped by the machine itself and never worked on a fixed surface.

Before any handling that would need dexterity, the food is put into a state in which it behaves as a rigid
body:

* **Cold side.** A cold cabinet (CC) with five fixed aluminium evaporator plates at −25 °C and five loose
  aluminium cold slabs takes five GN 1/3 "sandwiches" (tray – food – lid sheet) at once. Cutlets, slices,
  extruded patties, rolled Rouladen, fillings and soft cheese come out rigid after 1–6 minutes and are then
  picked, dipped, stacked, slid and cut like parts.
* **Heat side.** Skins are loosened by boiling or steaming (potato, tomato, egg, onion as the upgrade path)
  and slipped in a rubber-finger basket in the sink well; frozen food is released from its tray by a 1.5 s
  induction flash; butter is softened on the same coil.
* **Storage side.** Pastes, fats, herbs, garlic, ginger, stock and roux are kept in the freezer as countable
  pieces (5 g and 20 g pucks, 10 g cubes, flakes) and dosed by count and weight.
* **Recipe side.** Steps are reordered where that removes an operation: flour before freezing, cook before
  peeling (mash, Bratkartoffeln, potato salad), chill steps done in minutes on the plate, fillings formed as
  frozen plugs and rods.

The rest of the cell is conventional and is there because the corpus demands it: a 3 kN press with a sleeve
and dies (dice, slices, wedges, patties by extrude-and-cut, ricer), a sink well with a turntable (wash,
spin, raw rasp peeling, skin slipping), a reciprocating bow knife, four rotating hob positions (the fourth is
also the kneading station), a magnet-coupled spin head for whisk and blade lids, a bought combi-steam oven,
and a slot washer that cleans flat ware in about 70 s.

### 1.2 Layout

Envelope 600 deep, 2000 high. **Wall width 2280 mm**: oven column 560 + preparation bay 1000 + hob bay 720.
Without the oven column the cell is 1720 mm. X runs to the right, Y to the rear, Z up; internal depth 550.

```
 TOP VIEW (plan at bench level, z = 900; front = service door at the bottom)            all dimensions mm

 y=550 rear wall ===================================================================================
       |  (above the  | tool pegs     | approach lane for | CC cold cabinet   | P1 Ø260    P2 Ø260   |
       |   oven: dock | z 1170-1390   | CC trays (clear   | 395 x 240 x 430   | 3.5 kW     3.5 kW    |
       |   and box    | x 570-810     | at z 930-1330)    | flap faces -X     | turntable  turntable |
 y=300 |   port)      |...............|........o press rods o.........(bow)...|                      |
       |              | T1            | S  | R       | W sink well            | P3 Ø300    P4 Ø300   |
       |  OVEN        | weigh bench   | l  | rack    | 335 x 270, 250 deep    | 2.2 kW     2.2 kW    |-> plating
       |  mouth -> +X | + flash coil  | o  | well    | turntable, grate T2    | turntable  25 Nm     |   port
       |  (door drops)| 335 x 270     | t  | 16 trays| press P above          | (pans)     knead +   |
 y=20  |              |               |    |         |                        |            spin head |
 front ===================================================================================
     x=0            560 570         905 915 965 975 1203 1213              1548 1560                2280
       |<--- O 560 --->|<----------------------- P 1000 ---------------------->|<------- H 720 ------>|


 FRONT VIEW (section through the front row; rear-strip items shown in brackets)

 z=2000 __ceiling = extraction plenum, sloped 5 deg to a rear gutter______________________________________
        |                 free height for the retracted quill (450)                                      |
 1550   |              .-----. Y carriage                                                                |
 1400   |  ============|=====|=========== bridge beam (Y), cantilevered from the X module on the rear wall
        |  [dock]      |quill|  Ø60, stroke 450; wrist band z 950-1400                 [spin head MS]    |
 1330   |  [box port]  '--+--'          [press crosshead, parked]   [CC top]            z 1180 over P4   |
        |  pour lip     wrist: pitch axis (Y), jaw                  [bow knife, when mounted]            |
 1150   |  z 1160                                                                                        |
        |  OVEN  mouth                                                                                   |
  900   |  cavity floor__T1_____slot_rack____W (grate T2)___________hob glass, 4 rotating positions______|
  820   |  oven body    load cell  | tray |  | sink 250 deep |          induction modules,               |
        |  820-1275     + coil     | lift |  | turntable hub |          turntable drives                 |
  650   |---------------------------------------------------------------------------------------------- |
        |  base: R290 condensing unit | wash tank 6 L, steam generator | press drive | strainer, waste bin |
  100   |______________________________________________________________________________________________|
        x=0          560                                                  1560                       2280
```

Where the heated positions are: the four induction positions are inside the cell (hob bay, right); the oven
is a bought 60 cm compact combi-steam oven turned by 90° so that its mouth opens into the cell at bench
level (oven column, left); warm-holding is done in the oven at 70–80 °C, on a hob position at low power, or
on a heated shelf on the rear wall of the hob bay (300 × 270, 80 °C, 250 W).

Hand-over ports: boxes and stowed packs arrive at the dock above the oven (left, z 1300–1600); cooked food
leaves in its vessel through a port in the right wall at bench level.

---

## 2. Mechanism

### 2.1 Kinematics: the gantry

| Axis | Type | Travel | Force / torque, speed | Drive location, sealing |
|---|---|---|---|---|
| X | Bought belt-driven linear module with stainless cover strip, mounted on the rear wall at z 1400–1550 under a drip hood with a downward-facing opening | 1620 | 300 N, 1.0 m/s | Dry side of the rear wall; the bridge passes through the strip-sealed slot. The hood and strip are Zone S |
| Y | Same type, 120 wide, forms the cantilevered bridge beam | 440 | 300 N, 0.8 m/s | Inside a closed stainless shroud with drip edges (HYG-004: drive above food under a drip-proof cover) |
| Z | Stainless quill Ø 60 × 650 long through a wiper collar with drained lantern chamber (SM-191) in the Y carriage; ball screw in the carriage | 450 (wrist axis z 950–1400) | 400 N up and down, 0.4 m/s | One rod seal, vertical, not above the food path of the rod itself |
| Pitch | Wrist head at the quill end, axis parallel to Y, continuous rotation; gearmotor inside the quill, worm stage in the head | continuous | 25 Nm, 60 rpm | One rotary lip seal, IP69K, H1 grease, LRU |
| Jaw | Fork-slot jaw: the tab of the ware enters a 3.2 mm slot 45 mm deep, a cone pin locks it and centres it (±3 mm capture). Actuated by a push rod through the hollow pitch shaft | 12 | 300 N | Bellows inside the head |

Moving mass at the wrist 8 kg payload (largest: GN 2/3 braiser pair with twelve Rouladen halves, 5.6 kg;
4 L pot drained, 4.4 kg). The full 9 L pot is never lifted (catalogue rule R7). Bending moment at the tab up
to 13 Nm, carried by the form fit of the slot, not by friction [C].

The single wrist axis does five jobs: (1) it faces the jaw to −X (oven, plating) or +X (cold cabinet) or
downwards (slot washer, rack well: a tray hangs vertically and is lowered); (2) it tips a tray or vessel
over its far edge to pour; (3) it turns a pan pair or a tray pair through 180° (the flip of catalogue
rule R2); (4) it winds a Roulade on a fork (section 5); (5) it spins an apple or a lemon on a fork at
60 rpm against a peeler or zester.

There is **no yaw axis**. Consequence: every station presents its ware with the long side along X and the
tab on a short side; round vessels are turned by their hob turntable.

### 2.2 All actuators

| # | Actuator | Type | Force / torque, travel | Where, how sealed |
|---|---|---|---|---|
| 1–5 | Gantry X, Y, Z, pitch, jaw | see 2.1 | | |
| 6 | CC slab lift | Lead-screw actuator lifting a comb frame that raises all five slabs and, lowered, presses them down through springs | 600 N, 80 mm | Outside the insulation, two rods through PTFE bushes in the cabinet roof |
| 7 | CC flap | Small gearmotor on an insulated flap 200 × 400 with a heated gasket (3 W) | 2 Nm | Hinge outside the cold space |
| 8 | Press P | Ball screw and gearmotor under the deck pulling a crosshead down on two Ø 20 rods | 3 kN, 220 mm, 50 mm/s | Two rod wiper collars in the deck at the rear edge of the sink well |
| 9 | Bow knife drive | Eccentric, 80 W, reciprocating rod | ±6 mm at 45 Hz | Rod through a welded bellows in the deck (no sliding seal) |
| 10 | Sink turntable | BLDC with belt stage | 8 Nm, 5–900 rpm | Hub through the sink floor under an umbrella labyrinth (SM-236), above the water line of the drain weir |
| 11 | Sink drain valve | Motorised pinch or ball valve DN 40 | | Below the sink |
| 12 | Slot washer tray lift | Belt lift carrying a two-prong hanger | 50 N, 340 mm | Drive outside the wash slot; hanger through a labyrinth |
| 13–16 | Hob turntables P1–P4 | Ring drives under the deck; P1–P3 5 Nm at 5–40 rpm, P4 25 Nm at 5–300 rpm | | Rotating ring with raised boss and drained trough (SM-236) |
| 17 | Spin head MS | 500 W BLDC, 200–10 000 rpm, magnet coupling Ø 70 through a closed cap | 2 Nm at low speed | Fully closed housing on a bracket over P4; no seal |
| 18–20 | Dock: tilt, vibrator, lid lifter | Common front end of all candidates | tilt 0–180°, 10 Nm | Dry corner above the oven |
| 21 | T1 vibrator | Eccentric under the weigh frame (levels flour and crumbs, settles batter) | 20 W | Under the deck |
| 22–24 | Egg module | Common (SM-164 or SM-165 with SM-168): cup gripper, score or blade, tilt of the inspection cup | | On the left side wall of the preparation bay above T1 |
| 25 | Oven door | Door sliding down below bench level | 50 N, 300 mm | Replaces the bought door; drive under the deck |

**24 motion actuators in the preparation and cooking-side handling (1–10, 12–25), plus one valve actuator.**
Not counted as axes: compressor, condenser fan, circulation pump, steam generator, solenoid valves (8),
four induction modules, flash coil.

### 2.3 Wall penetrations

| Penetration | Count | Seal | Zone faced |
|---|---|---|---|
| X-module slot in the rear wall (bridge root) | 1, 1620 long | Stainless cover strip, downward-facing, under a hood; slight over-pressure of dry air from the base | S, above the rear strip only |
| Quill through the Y carriage | 1 | Wiper collar, lantern chamber, dry seal | S |
| Wrist pitch shaft | 1 | Rotary lip seal | S |
| Press rods through the deck | 2 | Wiper collars | S (the rods never touch food; dies are loose ware) |
| Bow knife rod | 1 | Welded bellows | S |
| Sink turntable hub | 1 | Umbrella labyrinth above the weir level | F (wash water of produce) |
| Hob turntable rings | 4 | Raised boss, drained trough | S |
| CC slab-lift rods | 2 | Bushes, inside the cold space | S (cold, dry) |
| Refrigerant lines into the CC | 2 | Brazed, foamed in | — |
| Water, steam and drain | nozzles 9, drains 3 | Welded sockets | F/S |
| Camera windows | 3 | Heated glass with containment, flush | S |

No shaft passes through a food-contact vessel wall (catalogue rule R3). No dynamic seal faces Zone F
except the sink hub, which is contact-free.

### 2.4 Stations

| Station | Function | Key dimensions |
|---|---|---|
| **CC** cold cabinet | Temper, crust-freeze, ice-weld, quick-chill, set | Outer 395 × 240 × 430, five levels for GN 1/3 (325 × 176); four daylights of 45 mm, one of 70 mm; section 3 |
| **T1** weigh and flash bench | Gain-in-weight dosing (10 kg ±1 g, hard stops for overload), flash release, butter softening, general dry work | Top 335 × 270, glass-ceramic; induction coil 1.5 kW underneath |
| **W** sink well with grate **T2** | Wash, spin, rasp-peel, slip skins, shock, drain, catch scraps; with the grate in place it is the red bench and the press table | 335 × 270 × 250 deep, 1.4404, floor 3° to a Ø 50 drain with lift-out strainer; grate rated 4 kN |
| **P** press | Dice, slice, wedge, core, extrude and cut, rice, flatten, squeeze, crush, knock out | 3 kN, daylight 330 under the parked crosshead; force and travel recorded per stroke (PRP-035) |
| **K** bow knife | Slice tempered meat and sausage, carve, shred cabbage, trim, halve, slice bread and cake | Blade 0.6 × 12 × 200 free length, scalloped; C-bow throat 270; hangs on a peg when idle |
| **S** slot washer, **R** rack well | Wash flat ware; store 16 trays vertically | Slot 50 × 280 × 340 deep; rack 228 × 280 × 340 |
| **P1–P4** hob | Cook; P4 also kneads and carries the bowl under the spin head | 2 × 2 on 720 × 550 |
| **MS** spin head | Whisk, whip, emulsify, purée, chop, juice (with P4) | Nose at z 1180 |
| **Dock** | Box tilt-pour with vibration; seasoning cup on a 300 g cell | Above the oven |
| **Oven** | Bake, roast, steam (skin-on potatoes), hot-air crisping, warm-hold | Bought, ≥ 45 L, trays 400 × 300 and GN 2/3 |

Operational constraints that follow from the geometry: T1 must be empty of anything taller than 40 mm when
a tray enters or leaves the oven; the bow knife is dismounted before anything crosses from the sink to the
hob at low height; P4 cannot knead and whisk at the same time; the GN 2/3 braiser on P3 overlaps P1, which
then takes only a Ø 200 pot.

### 2.5 Ware, tools and fixtures

All ware carries the same tab (tongue 40 × 45 × 3 with a Ø 8 hole). "Bought+" = bought standard part with a
welded tab; "custom" = made to drawing. Food-contact material: stainless steel throughout (trays in
ferritic 1.4016 or 1.4509 so that induction heats them), no FDM, no coatings.

| Item | Dimensions | Qty | Source |
|---|---|---|---|
| Cold tray GN 1/3, 0.6 mm, rim 20 mm, tabs on both short sides | 325 × 176 × 20 | 8 | custom (pressed) |
| Lid sheet for the cold tray, 0.4 mm, rim down 8 mm, floats on the food | 300 × 152 | 8 | custom |
| Work tray GN 1/2, 0.6 mm, corner spout | 325 × 265 × 20 | 8 | bought+ |
| Coating trays GN 1/3, 40 deep (flour, crumbs) and one narrow deep egg bath | 325 × 176 × 40; 300 × 60 × 160 | 3 | bought+ / custom |
| Roulade cassette: tray with five troughs 56 × 150 × 50 and a lid sheet | GN 1/3 footprint, 60 high | 2 | custom |
| Pin board (rimmed board with 12 welded pins Ø 3 × 12, radiused roots) | 300 × 150 | 2 | custom |
| Puck plates (through-hole plates for 5 g and 20 g pucks, gnocchi, croquettes) with knock-out pin plates | GN 1/3, 10 and 18 thick | 3 + 3 | custom |
| Filling-rod mould (two half shells, 8 rods Ø 18 × 100) | GN 1/3 | 1 | custom |
| Press sleeve Ø 110 × 130 with hopper rim; follower piston with stud faces | | 1 + 3 faces | custom |
| Dies: grid 8, grid 12 (staggered blades), harp 3, wedge-corer, orifice Ø 65 / Ø 55, ricer 3 mm, garlic plate | Ø 110 seat | 8 | custom (blades bought) |
| Platen with gauge rails 5 / 8 / 22 | 300 × 150 | 1 + 3 pairs | custom |
| Sink inserts: spin basket; rasp basket with wavy disc; rubber-finger basket with finger disc; grate T2; strainer; clip-on rim peeler and rim rasp | Ø 260 × 180 | 9 | custom (rubber fingers, peeler blade bought) |
| Optional moulds: hemispherical pair (dumplings, Germknödel), tapered cavity pair (Schupfnudeln) | GN 1/3 | 2 pairs | custom |
| Bowls: 8 L (ferritic base) with roller-and-scraper bridge; 1.5 L; 0.5 L | Ø 260, Ø 160, Ø 110 | 3 + 1 | bought+ / custom |
| Spin-head lids: whisk lid, small whisk lid, blade lid, blender stalk lid, reamer | | 5 | custom (two parts each: lid with PEEK bush, rotor) |
| Bow knife | 270 throat | 2 (red, green) | custom bow, bought blade |
| Stem tools, one piece each, with drip collar: tweezer tongs (4), turner (2), scraper (2), knife (2), roller (1, two parts), ladle 100 mL, spoon 15 mL, silicone brush, sifter cup, cut-off wire, winding fork, pin setter, cold pick plate, Spätzle sieve lid with scraper, probe | | 20 | custom / bought+ |
| Cooking ware (common to all candidates, listed for the count): pots 9 L with basket, 4 L (2) with basket (2), 1.5 L, 0.5 L; pans Ø 28 (2, a pair), Ø 20; GN 2/3 braiser with griddle lid (a pair); lids (4); rim scrapers (3); baking trays 400 × 300 (2), GN 2/3 (2); loaf tin, springform, gratin dish GN 1/2-65 | | 28 | bought+ |

Totals: about **110 loose items of 62 types**, of which 28 are cookware that any candidate needs; custom
part types in ware and tools: about 40.

---

## 3. Thermodynamics and refrigeration

### 3.1 Freezing times, recalculated

Method [C]: one-dimensional explicit enthalpy model of a slab, 30 nodes. Lean meat or mince: density
1050 kg/m³, initial freezing point −1.5 °C, freezable water 66 % of the mass, ice fraction
1 − (−1.5 / T), latent heat 334 kJ/kg of ice, specific heat 3.5 (unfrozen) and 2.0 kJ/kg·K (frozen),
conductivity 0.48 W/m·K rising linearly with the ice fraction to 1.5. Start at 4 °C. Boundary: contact
coefficient h between plate and food (through the 0.6 mm tray or 0.4 mm lid), plate at constant
temperature. "Crust" = ice fraction ≥ 50 % (−3 °C or colder). Unlike Plank's equation the model includes
the cooling of the unfrozen core and the sub-cooling of the crust.

| Case | h = 500 | h = 300 (design value) | h = 150 (frost, poor contact) | Heat removed |
|---|---|---|---|---|
| Cutlet 6 mm, both faces, 2 mm crust each side (rigid) | 55 s | 81 s | 147 s | 0.9 MJ/m² |
| Cutlet 6 mm, both faces, frozen through | 83 s | 114 s | 184 s | 1.26 MJ/m² = 30 kJ per 200 × 120 cutlet |
| Cutlet 6 mm, one face only, 3.5 mm crust | 126 s | 174 s | 295 s | 0.87 MJ/m² |
| Patty 25 mm, both faces, 3 mm crust | 110 s | 153 s | 264 s | 1.53 MJ/m² = 6.7 kJ per Ø 75 patty |
| Roulade seam, one face, frozen 6 mm deep | 261 s | 341 s | 544 s | 1.42 MJ/m² = 13 kJ per roll |
| Paste puck 10 mm, both faces, core below −12 °C | 231 s | 313 s | 516 s | 2.7 MJ/m² |

Plate at −25 °C. With the plate at −21 °C all times are about 20 % longer. F's Plank figures (3 mm crust
100 s, 10 mm slice 205 s at h = 500) are confirmed. **The sensitive quantity is h, not the plate
temperature**: halving h doubles the time. h = 500 assumes a wet, pressed contact; a 0.1 mm air gap alone
is 240 W/m²·K, and a 0.3 mm frost layer about 500 W/m²·K [C]. Hence three design rules: the sandwich is
pressed flat by the platen before it goes into the cabinet; the slabs are pressed down with 100 N each
(2 kPa on the tray, about 5 kPa on a cutlet), which makes a 0.6 mm tray follow 0.2 mm of waviness [C]; the
plates are kept frost-free (3.4). I use h = 300 as the design value and treat it as unproven (risk 1).

**Handling window** [C]: after removal into 22 °C air (15 W/m²·K on both faces) the ice fraction of the
outer 1.5 mm and the surface temperature develop as follows.

| Item | 30 s | 60 s | 120 s | 300 s | 600 s |
|---|---|---|---|---|---|
| Cutlet 6 mm after 90 s clamp | 0.80 / −7.2 °C | 0.78 / −6.7 | 0.75 / −5.9 | 0.66 / −4.2 | 0.49 / −2.8 |
| Cutlet 6 mm after 60 s clamp | 0.64 / −4.3 | 0.57 / −3.4 | 0.52 / −2.9 | 0.41 / −2.4 | 0.24 / −1.7 |
| Patty 25 mm after 110 s clamp | 0.73 / −5.6 | 0.66 / −4.4 | 0.55 / −3.4 | 0.35 / −2.3 | 0.09 / −1.6 |
| Patty 25 mm after 180 s clamp | 0.79 / −7.2 | 0.73 / −5.6 | 0.65 / −4.2 | 0.47 / −2.8 | 0.26 / −2.0 |

Two consequences. (a) A thin item frozen through stays rigid for 5–10 minutes: enough for breading and
staging. A thick item with a crust is rigid for 2–3 minutes and soft again after 5: it must be moved
promptly or clamped for 180 s. (b) **The surface does not thaw to a tacky film in 30–60 s as F assumed.**
A thin slab is thermally lumped (Biot number 0.04): its surface follows its mean temperature and stays
below −2 °C for more than five minutes. Condensation adds only about 3 g/m² per minute [C]. Flour does not
stick to such a surface; the breading sequence had to be changed (section 5, BRD).

### 3.2 Thawing and the effect on cooking

* **Pan load** [C]: 600 g of cutlets entering the pan at −4 °C (60 % ice) need about 97 kJ more than the
  same cutlets at 4 °C; the normal heating from 4 to 60 °C is 118 kJ. At a contact heat flux of 20–40 kW/m²
  per face the extra is 15–25 s of frying time. COK-005 (recover to 180 °C within 60 s) becomes harder: the
  load in the first minute is about 80 % higher. Counter-measures: preheat to 200 °C, two cutlets instead of
  three per 28 cm pan, 3.5 kW position. If the pan drops below 140 °C the crumb soaks fat instead of
  browning — to be tested (risk 3).
* **Juice loss.** The freezing front moves at about 10 cm/h (3 mm in 100 s), which is "quick freezing"
  (> 5 cm/h [K]); ice crystals stay small, and the item is cooked from the frozen state, which loses less
  drip than thawing first [K]. Crust-freezing before slicing and portioning is routine in meat plants
  [F, B:N12, K]. I expect no measurable difference for breaded, minced and braised items (medium-high),
  and I do not temper steak, roasts or fish fillets that are fried plain.
* **Browning.** A frozen surface delays the Maillard reaction by the time it takes to thaw and dry the
  surface, 20–40 s [E]. Irrelevant under a crumb coat and for braises; for Frikadellen it lengthens the
  first side from 5 to about 5.5 min. Frozen surfaces spit in hot fat; the 250 mL fat limit and the hood
  cope, the hob deck is soiled more.
* **Crumb adhesion.** Unknown; the changed sequence (flour pressed on while the surface is wet, egg on the
  frozen floured surface, crumbs on the wet egg) is my answer, not a tested one (risk 4).
* **Ice-weld.** Two wet meat faces frozen together hold with 0.1–0.5 MPa [D:N1, unverified]; on a 90 cm²
  seam that is at least 900 N. In the pan the weld melts within seconds while the protein of the seam
  coagulates within 60–90 s under the weight of the roll. Whether the seam then survives turning and
  90 minutes of braising nobody knows (risk 5); the pin is the default until it is tested.

### 3.3 Scheduling cost of the waiting times

| Event | Duration | Hidden behind other work? |
|---|---|---|
| Boost of the stack from idle (−12 °C) to −25 °C | 14 min at 300 W [C] | Yes whenever a meal has 14 min of other preparation before the meat (catalogue rule R11 puts raw animal food last anyway). Not for a Schnitzel-only order "now": +10 min, still inside PERF-001 (44 min allowed, 36 needed) |
| Pull-down from warm (after defrost) | 38 min [C] | Scheduled directly after the daily defrost |
| Cutlets, slices, fillings | 1.5–2 min per batch of up to 5 trays | The gantry prepares the coating trays meanwhile; net cost 0–1 min |
| Patties, dumplings, croquettes | 2.5–3 min per batch | Net cost 1–2 min |
| Roulade seam | 5.7 min | Net cost 2–3 min (pan preheats, sauce vegetables are cut) |
| Recovery of the stack after a batch | 4–9 min at 300 W [C] | Matters only for back-to-back batches: the second batch of a 6-person meal is 20–30 % slower |

Because all five daylights are loaded at once there is **no plate queue** for the largest case asked for
(six Rouladen in two cassettes plus twelve patties on three trays: five levels, 236 kJ, stack rise 12 K
without the compressor [C]). Elapsed-time cost per benchmark meal: 0 to 4 minutes (section 6). The real
cost is gantry moves, not waiting: each tempered batch costs 6–10 moves (in, out, flash, lid off).

### 3.4 Refrigeration hardware

**Plate stack.** Five aluminium plates 335 × 190 × 10 mm with a pressed-in refrigerant tube (the
construction of shelf evaporators in static freezers [K]), fixed, tilted 3° to a rear drain channel. On
each lies a loose aluminium slab 335 × 190 × 15 mm (2.6 kg). Resting on its plate, a slab is recharged by
conduction within about a minute; lifted by the comb it opens the daylight; lowered onto the lid sheet it
cools the top face of the food from its own heat capacity (2.3 kJ/K: one cutlet warms it by 6.5 K [C],
which costs 5–10 % in time). **No refrigerant line moves.** Total aluminium 21.5 kg, 19.3 kJ/K.

**Loads** [C]: B1 for four 76 kJ, for six 117 kJ; B2 159 kJ; B3 83 kJ; the 6-person worst case 236 kJ.
Without the compressor the stack warms by 4–12 K; with 300 W it recovers in 4–13 min. The thermal mass
shaves the peak; the compressor sees an average, not the 2–3 kW that the food draws from the plates in the
first seconds.

**Compressor.** A hermetic low-back-pressure compressor of 12–15 cm³ on R290 or R600a (the class used in
commercial freezers and ice makers): about 350 W cooling at −25 °C evaporation and 200–250 W at −35 °C,
250–300 W electrical, below 150 g charge, about 40 dB(A) [K, to be verified on a data sheet]. Fan-cooled
condenser in the base of the oven column; it rejects 500 W for a few minutes per meal.

**Can it share the freezer's circuit?**

| Option | Verdict |
|---|---|
| Tap the sealed circuit of a bought built-in freezer (the preferred cold store of research/03) | No. 40–80 g of R600a, a compressor sized for 0.26 kWh/day, no spare capacity, approval and warranty void |
| Second evaporator branch on a custom cold cell with its own compressor (research/03 path B) | Yes: solenoid valve and own capillary for the plate stack, priority control; the compressor must be the 300 W class. Saves one compressor, couples two modules |
| Own bought condensing unit plus custom plate stack, brazed and charged by a refrigeration technician | **Recommended.** About 450 € for the unit [E] |
| Bought appliance as it is | None exists with two-sided contact and several levels. For the prototype a single-plate "ice-roll" or anti-griddle machine (−30 °C, one plate about 300 × 400, 600–1100 W) gives the refrigeration set and one cold plate in one purchase [K] |
| Charge the loose slabs in the storage freezer | No. −18 °C air gives 16 K instead of 23 K of driving difference and hours of recharge |

**Energy** [C, E]: cabinet surface 0.74 m²; with 20 mm vacuum panel plus 5 mm foam the loss is 10 W at
−25 °C and 7.5 W at the idle set-point of −12 °C, that is 0.18 kWh/day thermal, about 0.15 kWh/day
electrical. Daily defrost and pull-down 0.25–0.3 kWh. Per meal 0.03–0.07 kWh. **About 0.6 kWh per day**,
6 % of RES-002. With plain 25 mm foam the idle loss would be 25 W; the vacuum panel is needed.

**Frost and condensation.** The cabinet is closed except for 8 s per tray exchange. One opening exchanges
about 12 L of air: 0.1 g of water in normal room air, 0.4 g in steamy cell air [C]; ten openings per meal
give 1–4 g of frost, a layer of at most 0.02 mm on 0.6 m² of plate and slab. Rules: trays go in dry
underneath (they come dry from the slot washer); the flap opens away from the hob; the cell's extraction
runs during cooking. **Defrost is a rinse**: once a day (or after 3 meals) 2–3 L of 40 °C water are sprayed
over the tilted stack, which melts the frost in a minute, washes the plates and slabs (Zone S, touched only
by tray undersides and lid tops) and runs off through the heated drain; a fan dries the stack for 10 min
before pull-down. Cold ware brought out into the cell frosts over within seconds (a few g/m² per minute);
this melts on the flash coil and leaves a wet bench top that drains to the sink. The flap gasket is heated.
Nothing in the cabinet is above open food.

**Noise.** Compressor and fan run during preparation (covered by NOI-003) and for 2–3 minutes per hour at
idle; at night the set-point is released and the stack is boosted with the first scheduled meal.

---

## 4. Ingredient intake and dosing

Front end as common to all candidates (catalogue 3.1): the box is opened at the dock, tilted about its pour
edge with vibration, and the dose is weighed as gain in weight on T1 (10 kg ±1 g) or in the seasoning cup
(300 g ±0.05 g) at the dock, in dry air above the oven and 1.3 m from the hob (rule R8). What K7 changes is
the *form* in which many ingredients are stored.

| Form | From box to vessel | K7-specific | Confidence |
|---|---|---|---|
| Whole produce | Pulse-tilt at the dock onto a GN 1/2 tray on T1, count by weight steps and camera; surplus pieces picked back with tongs | — | medium (SM-150) |
| Leafy | Whole head or bag content tilted into the spin basket in the sink; surplus returned in the basket to a box | No mass dosing better than "what came out" (SM-151) | medium |
| Granular | Dock tilt-pour, weight loop, into pot or bowl on T1 | Frozen peas, diced onion, diced vegetables are dosed the same way | high |
| Powder | Dock with mesh-valve lid into a bowl or the sifter cup on T1; never above a hot vessel | Flour for breading goes onto the tray through the sifter cup carried by the gantry | medium (humidity) |
| Seasoning 0.2–5 g | Weighed into the cup at the dock, carried to the pot; salt as brine through a metering valve at the hob (SM-143) | — | high |
| Liquid | Water: valve with flow meter at T1, at the sink and at the hob. Milk, oil, vinegar, wine, stock: dock pour into a cup on T1, the cup is carried | Small acidic or aromatic liquids (lemon juice, wine for deglazing) optionally as 20 mL frozen cubes | high |
| Viscous paste | **Frozen pucks** of 5 g and 20 g (tomato paste, stock concentrate, garlic, ginger, chilli and curry paste, pesto, roux), counted out by pulse-tilt and checked by weight; they drop straight into the hot pot. Mustard, jam, quark, honey (not frozen hard or needed cold-spreadable): spoon or ladle tool from the opened jar or tub, weighed on T1 | The pucks are made by the cell itself when a jar or tube is first opened: content pressed into a puck plate, frozen 5 min in the CC, knocked out into a freezer box | medium: clumping of pucks over weeks untested; ±2.5 g resolution meets PRP-011 for 5–50 g only with the 5 g puck |
| Solid fat | **10 g cubes** cut once from the block with the grid die while cold, stored frozen; counted | Softened on the flash coil (30–60 s at 300 W) when the recipe creams butter | high |
| Herbs | Bought frozen chopped, or fresh herbs frozen at ingestion and crushed frozen under the platen (SM-027); dosed as granular | Fresh-looking garnish of soft herbs is not possible; frozen chives and parsley on hot food are home practice | high for cooked dishes |
| Raw meat, pieces and mince | Pack (opened by the opening mechanism) tilted over a red tray or over the pot by the gantry; mince scraped out with the scraper | Cubes and strips: piece tempered 2–3 min, then through the 20 mm grid or past the bow knife | high / medium |
| Raw meat, slices and cutlets | **The one limp pick of the concept:** tweezer tongs take the top slice by an edge found by the camera, lift it so that it peels off the stack, and lay it down by dragging onto a floured cold tray. Alternative: the cold pick plate (SM-098) freezes on to the top slice in 5–10 s and the slice is tempered against the plate | After this step the slice is never handled limp again | **medium-low**; risk 6 |
| Bacon, sausage, soft cheese | Bought as a piece; tempered 2–3 min; slices, sticks and dice are created one at a time by the bow knife or the grid (SM-100) and slide off the tray as rigid pieces | Avoids singulating stuck slices (catalogue gap G9) | medium-high |
| Egg | Egg module: tongs take the egg from the tray insert, crack, inspect in the clear cup, tip into the bowl | — | medium (common) |
| Frozen | Native state; loose goods as granular, blocks (spinach) dropped into the pot | — | high |
| Long goods | Spaghetti: tongs take a bundle of about 100 g from the upright box, weighed on T1; leek, cucumber: tongs | Rigid, therefore easy | medium |
| Can, carton, tub (arrive opened in a carrier box with a tab) | Carrier gripped by the tab and tipped by the wrist over the vessel; rinsed with the recipe liquid (SM-119); tubs scraped with the scraper tool | — | medium |
| Jar | Pickles taken with tongs; pastes converted to pucks at first opening | — | medium |
| Vacuum or tray pack of meat | Tipped onto a red tray. A vacuum-skin pack can be tempered for 2 min before it is opened so that the content leaves as one rigid slab and the purge stays in the pack as ice | The tempering of closed packs works only with film in tight contact, not with tray packs on an absorbent pad | medium-low |

Requests that follow for other modules are collected in section 14.

---

## 5. Operation table

"CC n s" = n seconds in the cold cabinet at the design value h = 300. Times are for the quantity named and
include gantry moves at 7 s per pick-or-place [E]. "N" marks operations where the state change is the
mechanism (native to K7); all others use conventional mechanisms that K7 merely hosts.

### 5.1 Operations the machine must do itself (MEAL-018)

| Operation | Mechanism and step sequence | Time | Conf. | Untested |
|---|---|---|---|---|
| **BRD** bread a cutlet (N) | 1 sifter cup dusts a cold tray with flour. 2 tongs drag-lay the cutlet on it. 3 flour on top. 4 lid sheet on; platen presses to the 5 or 8 mm gauge rails at 1 kN (this is also POU). 5 CC 115 s. 6 flash 1.5 s on T1, lid peeled off, tray tipped: the rigid floured cutlet slides into the egg bath tray or is taken by tongs at one corner. 7 dipped upright into the narrow egg bath, drained 3 s. 8 laid in the crumb tray, tray shaken by the T1 vibrator, turned with the tongs, pressed with the turner at 30 N. 9 into the pan or onto a staging tray | 4 cutlets: 9 min, of which 2 min waiting | medium-high | Flour adhesion after freezing; egg film on a −5 °C surface; coverage ≥ 95 % at the grip corner; pan recovery |
| **FRB** patties (N for staging) | Mass kneaded in the 8 L bowl on P4 (roller, 90 s), tipped into the press sleeve (hopper rim, scraper). Press extrudes through the Ø 65 orifice, 25 mm per portion; the cut-off wire swipes; the puck drops 30 mm. Fast path: pucks drop directly into the cold pan standing on the grate, pan to the hob, pressed flat with the turner (smash-forming, no CC). Staged path for batches 2 and 3: pucks drop on cold trays, CC 150 s, flash, the rigid pucks **slide** off the tilted tray into the pan | 12 patties: 2 min fast path, 6 min staged | high / medium | Residue of mince in bowl and sleeve; mass ±10 % by stroke |
| **FRK** dumplings (N) | As FRB with the Ø 55 orifice, 45 mm per portion; CC 180 s so that the crust holds the shape; rigid cylinders slide into simmering water. Round shape: two-part hemispherical mould, filled by the press, CC 240 s, released by flash — optional | 8 dumplings: 7 min | medium | Whether a crust-frozen dumpling keeps together when the crust thaws in 90 °C water (the crust delays the setting of the surface starch) |
| **FRM** small pieces (N) | Croquettes, falafel, gnocchi blanks: mass pressed into a through-hole plate on a cold tray by the platen, struck off with the scraper, CC 120–180 s, knocked out by the pin plate on the press, slid into pan, pot or crumb tray. Schupfnudeln: two-part tapered cavity mould. Cookie balls: extrude and cut, no CC | 24 pieces: 6 min | medium | Knock-out of mash-based masses; gnocchi as pucks without ridges |
| **RLT** Rouladen (N for the seam) | 1 slice drag-laid on a Roulade board (cold tray with a cross groove at the leading end) on the grate. 2 brine and pepper; mustard from the spoon, spread with the scraper. 3 onion dice sprinkled; a bacon stick and a gherkin spear (both rigid) laid on the leading edge with tongs. 4 winding fork (two prongs 22 mm apart, on the wrist axis): lower prong in the groove under the meat edge, upper prong over the filling; the wrist turns 1.7 turns while X follows; the roll ends seam down. 5 the fork is drawn out in Y against the trough end of the cassette, the roll stays in its trough. 6 cassette with lid sheet into the 70 mm daylight, CC 340 s: seam and underside frozen 6 mm. 7 pin setter pushes a Ø 2 × 90 pin through each rigid roll (default until the weld is proven). 8 rigid rolls taken with tongs and set seam-down in the hot braiser; turned twice by tongs after 3 min; braised | 4 rolls: 13 min incl. 5.7 min CC | medium (roll), medium-low (weld alone) | Start of winding on a limp slice; stripping; weld through 90 min of braising; pins counted out at plating |
| **STU** rigid cavities | Peppers, tomatoes, apples, cannelloni, baked potato: filling by spoon or ladle; or (N) the filling is pressed as plugs Ø 55 or rods Ø 18 in a mould, CC 180 s, and the rigid plug is dropped or pushed into the cavity with tongs | cannelloni, 16 tubes: 8 min | medium-high | Rod mould release |
| **STU** flat pockets (N) | Cordon bleu: two thin cutlets with ham and cheese between, pressed by the platen, CC 115 s: the rim is ice-welded, the parcel is breaded as one rigid plate. Saltimbocca: ham and sage frozen on to the cutlet. Germknödel: a frozen jam puck between two dough discs pressed together in the hemispherical mould | 4 pieces: 10 min | medium | Whether the welded rim stays closed when the crumb coat sets; this answers catalogue gap G4 only if it does |
| **WRP** wrap | Rigid or semi-rigid sheets only: pancake folded over with the turner; enchilada and burrito attempted on the winding fork (tortilla warmed to make it pliable). Cabbage leaves, spring-roll and samosa wrappers, strudel, sponge roll: **not solved** | — | low | Everything |
| **ROL / SHD** dough | Kneaded and proofed in the bowl on P4 (coil at low power, 30 °C). Tipped onto the floured or oiled baking tray, rolled by the roller tool (100 N, X strokes, Y steps of 100 mm) between gauge rails, rested 5 min, rolled again. Loaf: baked in the tin. Shortcrust: dough slab chilled 3 min in the CC instead of 30 min in the fridge (N), rolled, tin lined by pressing with the platen foot | pizza base: 4 min + rest | medium-high | Sticking to the roller; corners of the tray; lining a round tin |
| **ASM / LAY** assemble | Layered dishes: ladle and scraper for sauces, tongs for rigid sheets (dry lasagne sheets, potato slices chilled firm, cheese slices cut tempered), sprinkle by tipping a tray. Open-hand food: tongs and turner on a work tray under the camera; burger, toast, open sandwich, taco in a rack, bowl | lasagne, 4 layers: 8 min | high (layers), medium (stacks) | Stability of stacks to the hatch |
| **FLP** flip | Pieces (steak, cutlet, patty, fish, toast): tweezer tongs or turner. Whole-pan items: pan-pair inversion on the wrist axis (both tabs in the jaw, 180° about Y, the pair lands on the neighbouring position) | 10 s per piece; 25 s per pan | high / medium | Pan pair with fat (shared test of all candidates) |
| **CAR** carve | Boneless roast rested 10 min, set on the pin board held by the gantry and fed past the bow knife with the board edge 3–15 mm from the blade; slices fall shingled on a warm tray | 10 slices: 90 s | medium-high | Hot braised meat; bone-in: not solved, served as parts |
| **UNM** unmould (N) | Tin plus inverted tray, both tabs in the jaw, turned 180°. Release: puddings and panna cotta set in ferritic cups are flashed 1–2 s on the coil (SM-241); cakes from greased and floured tinplate tins, 5 s on the coil at low power. Setting time in the CC 20–30 min instead of 2 h | 30 s | medium-high (set desserts), medium (cakes) | ≥ 95 % undamaged |
| **SCO** score | Knife tool with a depth shoe drawn by the gantry; pork rind is crust-frozen first (5 min, rind down on the plate) so that it cuts cleanly (N) | 20 cuts: 60 s | high | — |
| **SPR / TOP / GLZ / LIN** | Scraper zigzag; tray tipped with vibration, or sifter cup; silicone brush dipped in a cup of melted butter or egg wash; tin greased with the brush and floured with the sifter cup | 20–60 s | high; medium for fluted tins | — |

### 5.2 Peeling, trimming, cutting, egg

| Operation | Mechanism | Time | Conf. | Untested |
|---|---|---|---|---|
| **PLP** potato, carrot, raw | Rasp basket with wavy disc in the sink well, water spray, 150 rpm; peel slurry to the strainer. Carrots cut in halves first. K7 cannot avoid this peeler: 48 corpus meals peel raw (section 9.3) | 1.5 kg: 150 s | high; eyes and hollows remain (PRP-022 at its limit) | Loss 15–25 % |
| **PLP** potato, cooked first (N) | Steam or boil skin-on, shock 60 s in the sink, rubber-finger basket 45 s. Used where the recipe cooks first anyway (12 meals) and for mash | 1.5 kg: 2 min after cooking | medium | Slip yield on hot potatoes of mixed size |
| **PLA** onion | Default: bought peeled or frozen diced (permitted). Upgrade (N): ends cut by the knife, blanch 60 s in the pot basket, shock, rubber-finger basket | 45 s per batch | high / medium-low | Blanch-slip: ≥ 95 % skin-free; outer layer part-cooked (adapted for raw use) |
| **PLA** garlic | Frozen pucks; or cloves pressed skin-on through the garlic plate | 10 s | high | — |
| **PLS / PLH** | Apple, pear, kohlrabi: impaled on the winding fork and turned on the wrist axis against a sprung peeler fixed on the sink rim (SM-046). Celeriac, pumpkin: facets cut away past the bow knife. Tomato: blanch and slip (N). Cucumber, carrot in salads: skin on or rasp. Banana, avocado, mango: not solved, bought prepared | 30 s per apple | medium | Loading an apple on the fork on its core axis |
| **PLE** boiled egg | Shock in the sink, tumble with water in the rubber-finger basket | 6 eggs: 60 s | medium-low | Yield |
| **COR** core | Apple, pear: wedge-corer die on the press after centring in the sleeve cone. Cabbage: quartered past the bow knife, core removed by one oblique cut per quarter. Pepper: bought cut, or cap cut off and halves rinsed in the sink | 5 s per apple | high / medium / low | Pepper |
| **TRE / STR** | Long goods: ends cut by the knife. Beans, sprouts, mushrooms, herbs from the stalk: not solved, bought trimmed or frozen. Cauliflower: cooked whole, divided afterwards (N, cook before cutting) | — | low | — |
| **DIC / JUL** | Press: piece in the sleeve, follower with stud face, 8 or 12 mm staggered grid, cut-off wire every 8–12 mm (SM-009). Soft items (tomato, mozzarella, chicken, bacon) tempered 1–2 min first (N) | 1 kg: 5–6 min | high | Force on old carrots; onion layers |
| **SLI** | Harp die 3 mm on the press for cucumber, carrot, potato, mushroom; bow knife for everything long, large or soft (cabbage, leek, bread, sausage, tempered meat) | cucumber: 20 s | high | Harp force (staggered) |
| **MIN / CHH** | Herbs frozen and crushed (N); garlic, ginger as pucks (N); otherwise blade lid on the 0.5 L bowl under the spin head | 10 s | high | — |
| **GRC / GRF / zest** | Coarse: 3 mm harp twice (julienne) or bought grated. Hard cheese: bought grated, or the frozen block crushed under the platen (N, low). Zest: lemon on the fork turned against a fixed rasp | — | medium; the missing grater is a gap | A grating disc on the rim of the rotating bowl (SM-013) would close it |
| **JUI** | Halved fruit pressed by tongs on a reamer standing in the bowl on P4 (turntable turns the reamer) | 15 s per half | medium-high | — |
| **SLM** raw meat strips and cubes (N) | Piece tempered 150 s, 20 mm grid on the press or bow knife | 500 g: 5 min | high | — |
| **POU** | Platen on gauge rails, in the sandwich | 8 s | high | — |
| **CRK / SEP** | Egg module (common); slotted cup | 12 eggs: 3 min | medium | common |

### 5.3 Mixing, transfer, cooking-side handling

| Operation | Mechanism | Conf. |
|---|---|---|
| **KND / KNM** | 8 L bowl on P4, 60–100 rpm, fixed roller and scraper bridge hung on the bowl rim and held by a wall lug (SM-171) | high |
| **CRM / RUB** | Butter cubes softened on the coil, creamed with the roller at 120 rpm; rubbing in: frozen butter cubes and flour under the blade lid in pulses (N: the cubes are already cold) | medium-high |
| **WHK / WHP / EMU** | Whisk lids on the 0.5 L and 1.5 L bowls (one egg white) or the 8 L bowl under the spin head | high; magnet torque limits stiff masses |
| **FLD** | Bowl at 10 rpm against the scraper | medium |
| **MSH** | Ricer plate in the press sleeve, potatoes slipped first; milk and butter folded in the pot | high |
| **PUR** | Blender stalk lid on the pot, pot carried to P4 | high |
| **EXT** Spätzle | Sieve lid on the pot, batter ladled on, scraper strokes by the gantry | medium |
| **TOS** | Bowl with lid turned over four times on the wrist axis | high |
| **WLF / DRY** | Spin basket in the sink: spray with reversing rotation, spin 600 rpm (54 g) 2 × 15 s | high |
| **DRN** | Lift-out baskets; pots up to 4 L tipped through the strainer lid into the sink | high |
| **SQZ** | Platen in a perforated GN insert on the press | high |
| **Transfer** | Trays tipped over the corner spout with the scraper following; bowls tipped by the wrist; rigid items slide; the recipe liquid rinses the emptied vessel (SM-119) | medium for mince and dough (PRP-013: ≤ 8 %) |
| **STC / SAU** stir | The pot turns on its position against a loose scraper hung on the rim (SM-180); continuous for risotto and béchamel without occupying the gantry | high |
| **BST** | Ladle tool, roast pulled half out of the oven | medium |
| **PTH** | Ladle into the pan turning at 90 rpm for 3 s (SM-097) | medium |
| **SLB** slice bread, cake | Bow knife | high |
| **SHR** shred | Two knife tools — not developed | low |

<!-- END -->
