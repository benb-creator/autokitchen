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
   (breading, flat pockets, small formed pieces, rigid fillings), useful for about 40 more (cutting soft
   things, fast chilling, unmoulding), a simplification of fat and paste dosing in about half of all meals,
   and irrelevant for the rest. Everything a kitchen needs besides — a press with dies, a raw peeler, a
   kneading bowl, a whisk, a sink — must still be there. The cell described here therefore has 24 actuators,
   about 105 loose preparation parts and 27 pieces of cookware; "only a plain gantry, trays and a knife" is
   not true once the corpus is walked through.
3. **Three statements of the catalogue definition did not survive the calculation** and were changed
   (section 12): the "tacky thawed film after 30–60 s" does not exist (the surface stays below −2 °C for
   more than 5 minutes), so flour must go on *before* freezing; a double plate with a moving refrigerated
   upper plate is replaced by fixed evaporator plates with loose cold slabs; the band knife is replaced by a
   reciprocating bow knife that is one loose part.
4. **Benchmarks:** 11 of 12 "yes", 1 "adapted" (B7, oven fries, by requirement X-01). Coverage estimate
   **92–93 %** by count (227–230 of 248; certain upper bound 232), below the 95 % target; what falls out is
   the wrapping of limp sheets (cabbage leaf, tortilla, strudel, sponge, wrappers), which this concept
   excludes by definition.
5. **Adapted-method budget:** the requirements themselves already spend 19 of the 24 permitted meals
   (section 9.3). K7 is inside the 10 % only if crust-freezing is ruled a handling aid and not an adapted
   method (then 8.5–9.3 %); counted strictly it is at 13.7 %.

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

 y=550 +-----------------------+---------+-------------+----------------+--------------+--------------+
 rear  | above the oven:       | tool    | lane for CC | CC cold cabinet| P1  dia 260  | P2  dia 260  |
       | dock, box port,       | pegs    | trays: keep | 395 x 240 x 450| 3.5 kW       | 3.5 kW       |
       | seasoning cup,        |         | clear       | flap faces -X  | turntable    | turntable    |
 y=300 | egg module            +---------+-------------+--o----------o--+              |              |
       |                       | T1 weigh bench|S | R       | W sink well  [K]+--------------+--------------+
       | OVEN (turned 90 deg)  | + flash coil  |l | rack    | + grate T2     | P3  dia 300  | P4  dia 300  |
       | mouth opens to +X     | 335 x 270     |o | well    | 335 x 270,     | 2.2 kW       | 2.2 kW,25 Nm | => plating
       | at bench level; door  |               |t | 16 trays| 250 deep;      | pans, GN 2/3 | bowl: knead; |    port
       | drops below the bench |               |  |         | press P above  | braiser      | spin head MS |
 y=20  |                       |               |  |         | (rods: o)      |              | above        |
 front +-----------------------+---------------+--+---------+----------------+--------------+--------------+
      x=0                     560             905 965     1203             1548 1560        1920          2280
       |<------ O 560 -------->|<------------------- P 1000 ------------------>|<--------- H 720 ---------->|
       [K] = bow knife, mounted at the right edge of the sink when in use; o = press rods (x 1225, 1535)


 FRONT VIEW (section through the front row; rear-strip items shown in brackets)

 z=2000 __ceiling = extraction plenum, sloped 5 deg to a rear gutter______________________________________
        |                 free height for the retracted quill (450)                                      |
 1550   |              .-----. Y carriage                                                                |
 1400   |  ============|=====|=========== bridge beam (Y), cantilevered from the X module on the rear wall
        |  [dock]      |quill|  Ø60, stroke 450; wrist band z 950-1400                 [spin head MS]    |
 1350   |  [box port]  '--+--'          [press crosshead, parked]   [CC top]            z 1180 over P4   |
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
on the weigh bench T1 with its coil at low power (one GN 1/2 tray at 55–70 °C).

Hand-over ports: boxes and stowed packs arrive at the dock above the oven (left, z 1300–1600); cooked food
leaves in its vessel through a port in the right wall at bench level.

---

## 2. Mechanism

### 2.1 Kinematics: the gantry

| Axis | Type | Travel | Force / torque, speed | Drive location, sealing |
|---|---|---|---|---|
| X | Bought belt-driven linear module with stainless cover strip, mounted on the rear wall at z 1400–1550 under a drip hood with a downward-facing opening | 1620 | 300 N, 1.0 m/s | Dry side of the rear wall; the bridge passes through the strip-sealed slot. The hood and strip are Zone S |
| Y | Same type, 120 wide, forms the cantilevered bridge beam | 440 | 300 N, 0.8 m/s | Inside a closed stainless shroud with drip edges (HYG-004: drive above food under a drip-proof cover) |
| Z | Stainless quill Ø 60 × 650 long through a wiper collar with drained lantern chamber (SM-191) in the Y carriage; ball screw in the carriage | 450 (wrist axis z 950–1400) | 400 N up and down, 0.4 m/s | One wiper seal on a vertical rod; the quill is a closed tube and counts as Zone S |
| Pitch | Wrist head at the quill end, axis parallel to Y, continuous rotation; gearmotor inside the quill, worm stage in the head | continuous | 25 Nm, 60 rpm | One rotary lip seal, IP69K, H1 grease, LRU |
| Jaw | Fork-slot jaw: the tab of the ware enters a 3.2 mm slot 45 mm deep, a cone pin locks it and centres it (±3 mm capture). Actuated by a push rod through the hollow pitch shaft | 12 | 300 N | Bellows inside the head |

Moving mass at the wrist 8 kg payload (largest: GN 2/3 braiser pair with six Rouladen, 5.6 kg;
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
| 7 | CC flap | Small gearmotor on an insulated flap 190 × 400 with a heated gasket (3 W) | 2 Nm | Hinge outside the cold space |
| 8 | Press P | Ball screw and gearmotor under the deck pulling a crosshead down on two Ø 20 rods | 3 kN, 220 mm, 50 mm/s | Two rod wiper collars in the deck at the rear edge of the sink well |
| 9 | Bow knife drive | Eccentric, 80 W, reciprocating rod | ±6 mm at 45 Hz | Rod through a welded bellows in the deck (no sliding seal) |
| 10 | Sink turntable | BLDC with belt stage | 8 Nm, 5–900 rpm | Hub through the sink floor under an umbrella labyrinth (SM-236), above the water line of the drain weir |
| 11 | Sink drain valve | Motorised pinch or ball valve DN 40 | | Below the sink |
| 12 | Slot washer tray lift | Belt lift carrying a two-prong hanger | 50 N, 340 mm | Drive outside the wash slot; hanger through a labyrinth |
| 13–16 | Hob turntables P1–P4 | Ring drives under the deck; P1–P3 5 Nm at 5–40 rpm, P4 25 Nm at 5–300 rpm | | Rotating ring with raised boss and drained trough (SM-236) |
| 17 | Spin head MS | 500 W BLDC, 200–10 000 rpm, magnet coupling Ø 70 through a closed cap | 2 Nm at low speed | Fully closed housing on a bracket over P4; no seal |
| 18–20 | Dock: tilt, vibrator, lid lifter | Common front end of all candidates | tilt 0–180°, 10 Nm | Dry corner above the oven |
| 21 | T1 vibrator | Eccentric under the weigh frame (levels flour and crumbs, settles batter) | 20 W | Under the deck |
| 22–24 | Egg module | Common (SM-164 or SM-165 with SM-168): cup gripper, score or blade, tilt of the inspection cup | | Beside the dock above the oven; the inspection cup tips towards T1 |
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
| **CC** cold cabinet | Temper, crust-freeze, ice-weld, quick-chill, set | Outer 395 × 240 × 450, five levels for GN 1/3 (325 × 176); three daylights of 45 mm, two of 70 mm; section 3 |
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
| Coating trays GN 1/3, 40 deep (flour, crumbs) and one narrow deep egg bath | 325 × 176 × 40; 300 × 45 × 160 | 3 | bought+ / custom |
| Roulade cassette: tray with five troughs 56 × 150 × 50, each with a flat bottom 40 wide that lies on the plate, and a lid sheet | GN 1/3 footprint, 60 high | 2 | custom |
| Pin board (board with a rim on three sides, open at the cutting edge, 12 welded pins Ø 3 × 12, radiused roots) | 300 × 150 | 2 | custom |
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
| Stem tools, one piece each, with drip collar: tweezer tongs (4), turner (2), scraper (2), knife (2), roller (1, two parts), ladle 100 mL, spoon 15 mL, silicone brush, sifter cup, cut-off wire, winding fork, pin setter, cold pick plate, Spätzle sieve lid with scraper, probe | | 23 | custom / bought+ |
| Cooking ware (common to all candidates, listed for the count): pots 9 L with basket, 4 L (2) with basket (2), 1.5 L, 0.5 L; pans Ø 28 (2, a pair), Ø 20; GN 2/3 braiser with griddle lid (a pair); lids (4); rim scrapers (3); baking trays 400 × 300 (2), GN 2/3 (2); loaf tin, springform, gratin dish GN 1/2-65 | | 27 | bought+ |

Totals: about **105 loose preparation items of about 50 types plus 27 pieces of cookware** that any
candidate needs; custom part types in ware and tools: about 40.

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
(six Rouladen in two cassettes plus twelve extruded patties on two trays, eight to a tray: four of the five
levels, 236 kJ, stack rise 12 K without the compressor [C]). Elapsed-time cost per benchmark meal: 0 to
4 minutes (section 6). The real cost is gantry moves, not waiting: each tempered batch costs 6–10 moves
(in, out, flash, lid off).

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

**Energy** [C, E]: cabinet surface 0.76 m²; with 20 mm vacuum panel plus 5 mm foam the loss is 10 W at
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
| **RLT** Rouladen (N for the seam) | 1 slice drag-laid on a Roulade board (cold tray with a cross groove at the leading end) on the grate. 2 brine and pepper; mustard from the spoon, spread with the scraper. 3 onion dice sprinkled; a bacon stick and a gherkin spear (both rigid) laid on the leading edge with tongs. 4 winding fork (two prongs 22 mm apart, on the wrist axis): lower prong in the groove under the meat edge, upper prong over the filling; the wrist turns 1.7 turns while X follows; the roll ends seam down. 5 the fork is drawn out in Y against the trough end of the cassette, the roll stays in its trough. 6 cassette with lid sheet into the 70 mm daylight, CC 340 s: seam and underside frozen 6 mm. 7 pin setter pushes a Ø 2 × 90 pin through each rigid roll, guided by a hole in the trough wall (default until the weld is proven). 8 rigid rolls taken with tongs and set seam-down in the hot braiser; turned twice by tongs after 3 min; braised | 4 rolls: 13 min incl. 5.7 min CC | medium (roll), medium-low (weld alone) | Start of winding on a limp slice; stripping; pin force in frozen meat; weld through 90 min of braising; pins counted out at plating |
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
| **PLP** potato, carrot, raw | Rasp basket with wavy disc in the sink well, water spray, 150 rpm; peel slurry to the strainer. Carrots cut in halves first. K7 cannot avoid this peeler: 46 corpus meals peel raw (section 9.3) | 1.5 kg: 150 s | high; eyes and hollows remain (PRP-022 at its limit) | Loss 15–25 % |
| **PLP** potato, cooked first (N) | Steam or boil skin-on, shock 60 s in the sink, rubber-finger basket 45 s. Used where the recipe cooks first anyway (14 meals) and for mash | 1.5 kg: 2 min after cooking | medium | Slip yield on hot potatoes of mixed size |
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

---

## 6. Benchmark walk-throughs

Conventions. t in minutes from the order. "Moves" = pick-or-place cycles of the gantry including tool
pick-up and parking (7 s each [E]); dock, press, turntables and the cold cabinet work in parallel to the
gantry. Limits from PERF-001: 1.15 × T_ref + 10 min for 4 persons, T_ref = longest corpus time of the menu.
Onions are bought peeled (the common assumption); "slot" = washed in the slot washer, "chamber" = sent to
the ware-wash chamber. All times and move counts are paper estimates [E].

### B1 Rinderrouladen, Rotkohl, Salzkartoffeln — 4 persons (T_ref 150, limit 182 min)

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | CC boost starts (−12 → −25 °C, ready at t = 14). Red cabbage 900 g tipped by the dock onto a work tray, speared with the fork, set on the pin board | dock, T1, pin board | 5 |
| 2 | Bow knife mounted. Cabbage halved, each half laid cut face down (fork), core cut out by two oblique cuts, shredded at 3 mm: 2 × 50 cuts; shreds fall on a work tray on the grate | K over W, 2 work trays | 12 |
| 8 | Apple peeled on the fork against the rim peeler, cored and wedged by the press die, wedges through the 12 mm grid; one onion through the 8 mm grid; two more onions diced for the Rouladen and the sauce | W, P, sleeve, 3 dies, cup | 14 |
| 12 | 4 L pot on P1: lard cube, onion 3 min, cabbage and apple tipped in, vinegar, wine, sugar, brine, spice cup; lid; simmer 75 min, pot turned against the rim scraper every 5 min | P1, pot, lid, scraper | 12 |
| 16 | Red phase. Four Roulade slices drag-laid on two Roulade boards (two per session), seasoned, mustard spooned and spread, onion sprinkled, bacon stick (cut from a tempered piece) and gherkin spear laid on; wound on the fork, stripped into the cassette troughs seam down | T2 grate, 2 boards, cassette, tongs, spoon, scraper, fork | 34 |
| 27 | Cassette into the 70 mm daylight; CC 340 s. Meanwhile braiser preheats on P3 (220 °C, 15 mL oil) | CC, braiser | 3 |
| 33 | Cassette out, flash on T1, pins set, rigid rolls placed seam-down in the braiser; seared 3 min; turned twice with tongs at 3 min intervals | T1, pin setter, tongs | 18 |
| 42 | Rolls lifted to a warm tray; onion dice and one tomato paste puck fried 2 min; wine cup, stock; rolls back; lid; braise at 95 °C, 90 min | P3, tongs, cup, lid | 12 |
| 45–110 | Flat ware through the slot; bulky ware to the chamber; idle | S | (20) |
| 112 | Potatoes 800 g tipped into the rasp basket, 150 s with spray; tipped onto a tray; large ones halved past the knife; into the basket of the second 4 L pot on P2 with 1.2 L water and brine; boil 22 min | W, rasp basket, K, P2 | 14 |
| 132 | Rolls out on a tray into the oven at 70 °C; sauce strained through the strainer lid into the 1.5 L pot on P4, two roux pucks, simmer 5 min on the turntable | P4, 1.5 L pot | 8 |
| 140 | Potato basket lifted, drained 20 s, steamed dry in the emptied pot; pins pulled by the pin setter magnet and counted | P2 | 6 |
| 145 | Hand-over: braiser tray with rolls, sauce pot, cabbage pot, potato pot to the plating port | | 4 |

**Verdict: yes.** Elapsed 145–150 min. About 140 moves plus 20 for washing. Cold cabinet used once
(5.7 min, hidden). Soiled: 2 boards, cassette and lid, pin board, 3 work trays, sleeve and 3 dies with
follower, bow knife, tongs (2), spoon, scraper, fork, pin setter, sifter cup, 3 cups, rasp basket and disc,
pots 4 L (2), 1.5 L, braiser, lids (3), rim scrapers (2), basket — 38 items. The weld is not relied on; if
the pins are dropped after the test the step at t = 33 loses 6 moves.

### B2 Wiener Schnitzel, Bratkartoffeln, Gurkensalat — 4 persons (T_ref 50, limit 67 min)

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | CC boost starts. 800 g small waxy potatoes, skin on, into the basket of the 4 L pot on P1, 1 L water; boiling from t = 7, done at t = 27 | dock, P1 | 5 |
| 3 | Green phase. Two cucumbers rinsed in the sink, cut into 110 mm lengths past the knife, sliced by the 3 mm harp on the press into the 8 L bowl; dill (frozen), vinegar, oil, sugar, brine, sour cream dosed at the dock into the 0.5 L bowl, whisked under the spin head, poured over; bowl turned over four times with its lid; rests | W, K, P, bowls, MS | 22 |
| 14 | Red phase. Four cold trays dusted with flour; four cutlets (150 g) drag-laid; flour on top; lid sheets; platen to the 5 mm rails, 1 kN | T2, P, sifter cup, tongs | 24 |
| 20 | Four sandwiches into the CC; 115 s. Meanwhile two eggs cracked, whisked in the egg bath with brine; crumbs dosed into the crumb tray; 28 cm pan on P4 preheats with 120 mL clarified butter | CC, egg module, P4 | 14 |
| 23 | Sandwiches out one by one: flash, lid off, cutlet taken by a corner with the red tongs, egg bath, crumb tray (shake, turn, press), onto a staging tray | T1, 3 coating trays | 28 |
| 28 | Potato basket lifted, shocked 60 s in the sink, slipped 45 s in the rubber-finger basket, sliced 5 mm past the knife onto two cold trays; trays 90 s in the CC to firm the slices | W, K, CC | 16 |
| 31 | Schnitzel batch 1 (two) into the pan, 3.5 min per side, turned with the turner; batch 2 follows; finished ones on the rack tray in the oven at 80 °C | P4, oven | 12 |
| 34 | Potato slices slide from the trays into the GN 2/3 braiser on P3 with bacon dice, onion after 8 min; turned with the turner every 4 min for 18 min | P3 | 12 |
| 52 | Lemon cut into wedges; hand-over of pan tray, braiser, salad bowl | K | 5 |

**Verdict: yes.** Elapsed about 55 min. About 140 moves. Cold cabinet twice (cutlets 115 s, potato slices
90 s). Soiled: 6 cold trays, 4 lid sheets, 3 coating trays, staging tray, platen, harp die and sleeve,
bow knife, tongs (2), turner (2), sifter cup, bowls (2), whisk lid, rubber-finger basket and disc, pot,
basket, pan, braiser — 32 items; flour, egg and crumb residues that touched raw meat are discarded into the
sink strainer. The Bratkartoffeln follow the traditional order (boiled, cooled, sliced, fried); the
cooling that a household does overnight takes 90 s.

### B3 Frikadellen, Kartoffelpüree, Erbsen-Möhren-Gemüse — 4 persons (T_ref 35, limit 50 min)

| t | Step | Station, ware | Moves |
|---|---|---|---|
| 0 | 800 g potatoes, skin on, halved past the knife if larger than 60 mm, into the pot basket on P1; boiling from t = 7, done at t = 27 | dock, K, P1 | 8 |
| 3 | 300 g carrots rasped 60 s, cut to 100 mm, diced through the 8 mm grid into the 1.5 L pot; 250 g frozen peas dosed on top; 100 mL water, butter cube, brine; on P2 from t = 25, 10 min | W, P, P2 | 14 |
| 9 | Stale roll soaked in 80 mL water in the 0.5 L bowl, squeezed under the platen in the perforated insert; onion through the 8 mm grid; egg cracked | P, egg module | 10 |
| 14 | Red phase. 500 g mince tipped from its pack into the 8 L bowl on P4 with roll, onion, egg, a spoon of mustard, brine, pepper cup, frozen parsley; roller 90 s at 80 rpm | P4, bowl, roller bridge | 8 |
| 18 | Bowl tipped into the press sleeve (scraper follows); Ø 65 orifice; eight strokes of 25 mm, cut-off wire after each. Fast path: the pucks drop into the GN 2/3 griddle standing on the grate, four per row | P, sleeve, orifice, wire | 12 |
| 21 | Griddle to P3 (170 °C, 20 mL oil); pucks pressed flat to 22 mm with the turner; 5.5 min per side; turned with the turner | P3 | 12 |
| 28 | Potato basket lifted, drained; potatoes slipped 45 s in the rubber-finger basket, tipped into the sleeve (ricer plate), pressed back into the emptied pot with 150 mL hot milk and 40 g butter cubes; folded on the turntable with the scraper; nutmeg | W, P, P1 | 14 |
| 35 | Vegetables drained through the strainer lid, butter cube, parsley | P2 | 4 |
| 38 | Hand-over | | 4 |

**Verdict: yes.** Elapsed 40–43 min. About 85 moves. **The cold cabinet is not used** on the fast path;
for six persons the second batch of six patties is extruded on a cold tray, crust-frozen 150 s and slid
into the pan when the first batch leaves (adds 8 moves, no elapsed time). PRP-023 "12 patties in
≤ 5 min": 2 min on the fast path, about 6 min when all twelve are staged. Soiled: bowl, roller bridge,
sleeve, orifice, ricer plate, grid, follower, wire, scraper, turner, spoon, 0.5 L bowl, insert, baskets
(2), rasp and rubber-finger baskets, pots (2), griddle — 24 items.

### B4 Spaghetti Bolognese with grated cheese — 4 persons (T_ref 75, limit 96 min)

| t | Step | Moves |
|---|---|---|
| 0 | 9 L pot with basket on P2, 4.5 L water from the hob valve, lid, held at 90 °C | 3 |
| 1 | Carrot and a piece of celeriac: carrot rasped, celeriac faceted past the knife; both and one onion through the 8 mm grid; two garlic pucks counted at the dock | 16 |
| 9 | 4 L pot on P1: oil, vegetables 5 min on the turntable; 500 g mince tipped in from the pack, broken up by the rim scraper at 30 rpm, 6 min; tomato paste puck; wine cup; tinned tomatoes tipped from the carrier, tin rinsed with the stock; brine, sugar, herbs; simmer 50 min, turned every 3 min | 18 |
| 58 | Water to the boil (3.5 kW, 3 min); 450 g spaghetti in five tong bundles weighed on T1, into the basket; 10 min; pushed under once with the turner | 12 |
| 69 | Basket lifted, drained 20 s, tipped into the sauce pot; turned over on the turntable | 4 |
| 72 | Cheese: bought grated, dosed into a cup | 3 |
| 74 | Hand-over | 3 |

**Verdict: yes.** Elapsed 75–80 min. About 60 moves. Cold cabinet not used; K7 contributes only the pucks.
Soiled: 2 pots, basket, sleeve, grid, follower, bow knife, 3 cups, tray, rasp basket — 14 items.

### B5 Pizza, yeast dough from flour, two trays (T_ref 90, limit 113 min)

| t | Step | Moves |
|---|---|---|
| 0 | 500 g flour (mesh lid), 10 g yeast, brine, 20 mL oil dosed into the 8 L bowl on T1; bowl to P4; 310 mL water at 30 °C; roller 8 min | 8 |
| 10 | Proof in the bowl on P4, coil at 30 °C, lid on, 45 min. Meanwhile: tinned tomatoes with oregano and brine under the blender stalk; oven preheats to 250 °C from t = 35 | 8 |
| 12 | Mozzarella (2 balls) and a salami piece 120 s in the CC; mozzarella through the 12 mm grid, salami sliced 2 mm past the knife onto a cold tray (40 slices) | 14 |
| 55 | Dough tipped onto a floured work tray, divided with the scraper by weight; each half on an oiled GN 2/3 baking tray, rolled to 5 mm in two passes with 5 min rest | 22 |
| 68 | Sauce ladled and spread with the scraper; salami slid on from the tilted cold tray with vibration, mozzarella likewise | 12 |
| 72 | Both trays into the oven (two levels); 11 min; out; cut with the knife tool | 10 |
| 86 | Hand-over | 2 |

**Verdict: yes.** Elapsed about 88 min. About 76 moves. The cold cabinet makes the mozzarella cuttable and
creates the salami slices singly (no stuck stack). Open points: evenness of the rolled base in the tray
corners; topping distribution by sliding is ±30 % at best.

### B6 Gemüseeintopf from whole vegetables — 6 persons (T_ref 35, limit 60 min)

| t | Step | Moves |
|---|---|---|
| 0 | 450 g potatoes, 300 g carrots, 1 parsnip into the rasp basket, 150 s; tipped onto a work tray | 8 |
| 4 | 150 g celeriac faceted past the knife; leek halved lengthwise past the knife, rinsed in the spin basket, sliced 5 mm past the knife; 200 g green beans: bundle pushed against the tray rim, both ends trimmed past the knife (medium-low: 10–15 % of ends missed), cut to 30 mm | 20 |
| 10 | Roots cut to sleeve length and diced through the 12 mm grid, ten loads, into the 9 L pot standing on the grate; two tomatoes cored with the knife, 60 s in the CC, diced | 30 |
| 18 | Pot to P2 (2.3 kg of vegetables): oil, 5 min on the turntable; 1.8 L water and stock pucks; boil, simmer 22 min; peas after 15 min | 8 |
| 46 | Frozen parsley, seasoning; hand-over (the pot is carried with 4.5 kg content) | 3 |

**Verdict: yes**, with the bean trimming as the weak step (bought trimmed beans remove it). Elapsed
48–50 min. About 70 moves. PRP-023 "1 kg mixed vegetables in ≤ 6 min": 10 loads × 35 s = 6 min, at the
limit. "Cook before cutting" does not help here: soup dice must be cut raw.

### B7 Steak, oven fries, mixed salad with vinaigrette — 2 persons (T_ref 30, limit 44 min)

| t | Step | Moves |
|---|---|---|
| 0 | Oven to 220 °C hot air. 500 g potatoes rasped 120 s, pushed lengthwise through the 12 mm grid (sticks), rinsed and spun in the basket, turned over in the bowl with 8 mL oil, spread on the perforated tray | 18 |
| 8 | Tray into the oven, 25 min, shaken by the gantry at half time. Option (N): sticks steamed 4 min and crust-frozen 3 min before the oven, as the industry does for oven fries | 4 |
| 9 | Lettuce head quartered past the knife, core cut out, cut in strips, washed and spun (2 × 15 s); tomato through the wedge die; half a cucumber through the harp; carrot rasped and cut to julienne by two harp passes; radishes through the harp; all into the 8 L bowl | 26 |
| 20 | Vinaigrette: oil, vinegar, mustard, brine in the 0.5 L bowl under the whisk lid, 20 s | 5 |
| 22 | Steaks (2 × 200 g) from the pack onto a red tray with tongs; brine spray, pepper. 28 cm pan on P3 at 240 °C, 15 mL oil | 5 |
| 25 | Sear 2.5 min per side, turned with tongs; butter cube, thyme, a garlic puck after the turn; probe set by the gantry; out at 54 °C core; rest 5 min on a tray on T1 (coil at 55 °C) | 10 |
| 33 | Dressing poured, bowl turned over four times; fries out, salted | 8 |
| 36 | Steaks sliced past the knife if ordered; hand-over | 4 |

**Verdict: adapted** (oven fries instead of deep-fried, as X-01 prescribes for every candidate; nothing
K7-specific is adapted). Elapsed 37–40 min. About 80 moves. The steak is deliberately not tempered.
Basting with a spoon is not done; the butter melts over the steak when the pan is tilted 10° by the wrist.

### B8 Pfannkuchen, 8 pieces (T_ref 35, limit 50 min)

| t | Step | Moves |
|---|---|---|
| 0 | 250 g flour sifted into the 8 L bowl on T1, 500 mL milk, 3 eggs (egg module), brine, sugar; whisk lid under the spin head 60 s; rest 20 min | 12 |
| 20 | Pans A and B on P3 and P4 at 190 °C. Cycle per pancake: butter cube in A; 100 mL ladled in while A turns at 90 rpm for 3 s; 90 s; B set mouth-down on A, both tabs gripped, pair turned over and set on P4; A lifted off and returned to P3; 60 s; B tipped, the pancake slides onto the stack tray in the oven at 70 °C. A and B swap roles every cycle | 8 × 7 = 56 |
| 44 | Hand-over | 2 |

**Verdict: yes**, conditional on the pan-pair flip (shared test of all candidates). Elapsed 45–48 min,
close to the limit because one gantry does every flip. About 70 moves.

### B9 Chicken curry with rice — 4 persons (T_ref 40–50, limit 56 min)

| t | Step | Moves |
|---|---|---|
| 0 | CC boost. 300 g rice rinsed in the fine basket in the sink, into the 4 L pot on P2 with 600 mL water and brine; lid; from t = 22: boil, then 15 min at low power | 8 |
| 3 | Two onions through the 8 mm grid; pepper (bought as strips, frozen) dosed; garlic and ginger pucks, curry paste puck counted | 10 |
| 14 | Red phase. 500 g chicken breast laid on two cold trays with tongs, lid sheets; CC 150 s; flash; tipped into the sleeve; 20 mm grid at 1.5 kN; cubes fall on a red tray; rest 3 min so that the crust softens | 18 |
| 22 | 4 L pot on P1 at 220 °C: cubes seared in two batches of 2 min; onion, pucks; tinned coconut milk tipped from the carrier, rinsed with 100 mL water; simmer 15 min | 14 |
| 40 | Seasoning; rice loosened with the turner; hand-over | 4 |

**Verdict: yes.** Elapsed 42 min. About 55 moves. Native K7 case: tempered chicken is diced by the grid in
one stroke without smearing.

### B10 Lasagne, béchamel from scratch — 4 to 6 persons (T_ref 120, limit 148 min)

| t | Step | Moves |
|---|---|---|
| 0–60 | Ragù as in B4, 45 min simmer | 40 |
| 45 | Béchamel: 50 g butter cubes melted in the 1.5 L pot on P4 (turntable 30 rpm, rim scraper); 50 g flour sifted in, 2 min; 600 mL milk in four portions from a cup at 1 min intervals; 8 min at 90 °C, turning continuously; nutmeg, brine | 12 |
| 60 | Oven to 190 °C. Gratin dish GN 1/2-65 on T1, greased with the brush. Layers: béchamel ladle and scraper; three dry sheets placed with tongs from the upright box (rigid, one at a time); ragù ladled and spread; repeat four times; béchamel; grated cheese tipped from a tray | 46 |
| 72 | Dish into the oven, 40 min; out; rests 12 min on T1; cut into portions with the knife tool | 6 |
| 126 | Hand-over | 2 |

**Verdict: yes.** Elapsed about 128 min. About 105 moves. Cold cabinet not used. Risk: lumps in the
béchamel with turntable and scraper only (a whisk lid on P4 for 20 s cures it).

### B11 Rührkuchen in a tin, unmoulded (T_ref 100, limit 125 min)

| t | Step | Moves |
|---|---|---|
| 0 | Oven to 175 °C. Loaf tin (tinplate, 300 × 110) greased with the brush (a butter cube softened 40 s on the coil), floured with the sifter cup, turned over and tapped | 8 |
| 3 | 250 g butter cubes in the 8 L bowl on T1: coil 300 W for 60 s; bowl to P4; 200 g sugar; roller at 120 rpm 4 min; four eggs one at a time from the egg module; 350 g flour with baking powder sifted in, 100 mL milk; 10 rpm 60 s | 22 |
| 14 | Half of the batter tipped into the tin (scraper follows); cocoa and a little milk into the rest, 30 s; tipped in; swirled with the knife tool | 8 |
| 17 | Tin into the oven, 60 min; out; cools 20 min on the grate over the sink | 4 |
| 98 | Tin 5 s on the coil at low power; work tray placed on top, both tabs gripped, turned over; tin lifted | 5 |
| 100 | Hand-over; slicing past the bow knife at serving | 3 |

**Verdict: yes.** Elapsed 100–105 min. About 50 moves. The state change works here in the warm direction
(softening butter, releasing the tin).

### B12 Scrambled eggs from shell eggs, toast — 1 person (limit 17 min)

| t | Step | Moves |
|---|---|---|
| 0 | Three eggs through the egg module into the 0.5 L bowl; 20 mL milk, brine; small whisk lid 15 s | 7 |
| 2 | Two slices of toast bread taken with tongs into the dry 28 cm pan on P3 at 180 °C, 80 s per side, turned with tongs | 6 |
| 3 | Ø 20 pan on P4 at 110 °C, butter cube; eggs poured; turntable 10 rpm against the rim scraper, 2.5 min; frozen chives from the cup | 8 |
| 7 | Hand-over | 3 |

**Verdict: yes.** Elapsed 8–9 min. About 25 moves. Seven soiled items; the smallest vessels work at their
minimum quantity. Cold cabinet not used.

### Summary

| | Verdict | Elapsed / limit (min) | Moves | Cold cabinet | Weakest step |
|---|---|---|---|---|---|
| B1 | yes | 150 / 182 | 140 | seam 5.7 min | winding and stripping the roll; weld |
| B2 | yes | 55 / 67 | 140 | 2 × | flour-then-freeze breading; limp lay-down |
| B3 | yes | 43 / 50 | 85 | not needed | mince residue in bowl and sleeve |
| B4 | yes | 78 / 96 | 60 | no | — |
| B5 | yes | 88 / 113 | 76 | cheese, salami | rolling into the tray corners |
| B6 | yes | 50 / 60 | 70 | tomato only | bean trimming; dicing rate |
| B7 | adapted (X-01) | 40 / 44 | 80 | optional | time margin 4 min |
| B8 | yes | 47 / 50 | 70 | no | pan-pair flip; time margin 3 min |
| B9 | yes | 42 / 56 | 55 | chicken | — |
| B10 | yes | 128 / 148 | 105 | no | béchamel lumps |
| B11 | yes | 103 / 125 | 50 | no (coil) | unmoulding |
| B12 | yes | 9 / 17 | 25 | no | egg module |

The state change is used in 5 of 12 benchmarks and is indispensable in one (B2). Mean 80 moves per meal.

---

## 7. Cleaning

### 7.1 Principle

Food touches only loose ware and the sink well. Loose ware is of two kinds:

* **Flat ware** — trays, lid sheets, coating trays, boards, plates, dies, platen, grate, pot lids, stem
  tools, bow knife: everything thinner than 45 mm. It is washed in the **slot washer** inside the cell
  within minutes of use and returns dry to the rack well or to its peg.
* **Bulky ware** — bowls, pots, pans, baskets, sleeve, cassette, rotor lids: goes to the ware-wash chamber
  of the washing module (research/06 programme P1), as the cookware of every candidate does.

The slot washer exists because K7 produces many flat parts per meal and because thin steel is the easiest
object to wash, disinfect and dry (F's observation about membranes applies to a 0.6 mm tray as well).

### 7.2 Slot washer

A vertical slot 50 × 280 mm, 340 deep, flush in the deck. The gantry turns the item to the vertical and
hangs it by its tab on a two-prong hanger; a belt lift (actuator 12) moves it up and down between two
facing spray bars (six flat-fan nozzles each, 45 mm stand-off, inclined ±20° so that the inside of rims is
hit), so every square centimetre passes a nozzle. The gantry is free during the cycle.

| Phase | Medium | Time | Water |
|---|---|---|---|
| Pre-rinse to drain (strainer) | Overflow from the tank, ≤ 40 °C | 5 s | none fresh |
| Wash, two strokes | Tank 6 L at 55–60 °C, enzymatic detergent, 40 L/min recirculated | 25 s | — |
| Rinse | Fresh water 0.4 L at 60 °C with rinse aid; runs into the tank and displaces the overflow | 8 s | 0.4 L |
| Steam | 8–10 g from a 2 kW steam generator: a 0.3 kg tray reaches more than 90 °C within 3 s, A0 ≥ 60 (HYG-021) | 6 s | 0.01 L |
| Air knife on the upstroke | The part leaves at about 80 °C and dries by its own heat | 15 s | — |

About 70 s and 0.4 L per item; about 40 Wh per item (rinse water 22 Wh, steam 7 Wh, tank upkeep and pump
11 Wh) [C, E]. The tank is dumped and the slot washes itself once a day (6 L, 0.35 kWh).

Honest points: the tab weld, the inside corners of the tray rim and the cells of the grid dies are the spray
shadows to prove with riboflavin; the hanger prongs shade two spots on the tab (the tab is not
food-contact); parts with dried egg or starch may need two cycles; a 3 s steam pulse disinfects a smooth
clean surface, not a soiled one, so steam comes after the wash, never instead of it.

### 7.3 Surface inventory

| Surface | Zone, area [E] | Soiled by | Cleaning | Frequency | Drying | Verification |
|---|---|---|---|---|---|---|
| Trays, lid sheets, coating trays, boards, puck plates (up to 35 per meal) | F, 0.10–0.17 m² each (both faces) | Meat, flour, egg, mince, vegetables | Slot washer | After each use | Own heat, air knife | Process record; camera with grazing light on the way to the rack |
| Dies, follower faces, platen, cut-off wire | F | Vegetable fibres, mince | Follower with studs clears the grid (rule R13); slot washer; chamber weekly | After each use | as above | Camera through the grid against a light |
| Stem tools | F below the collar | All | Slot washer | After each use; red tools after the red phase | as above | Process record |
| Bow knife | F (blade), S (bow) | Meat, cabbage, bread | Slot washer; blade clamps are the crevice | After each session | as above | Blade tension and drive current (PRP-035) |
| Bowls, pots, pans, baskets, sleeve, cassette, rotor lids, inserts | F | All | Ware-wash chamber P1 (75 °C final rinse) | After the meal; cold pre-rinse in the sink within minutes | Chamber hot air | Chamber record, camera |
| Sink well, hub umbrella, drain, strainer | F, 0.45 m² | Soil, peel slurry, raw meat juice under the red bench | Mains rinse 1.5 L after each use; after the red phase and at the end of the meal 2 L from the wash tank at 60 °C through three nozzles plus 60 g steam under a tray as cover (well at 85 °C for 1 min) | Per use, per meal | Drains (3°), residual heat | Temperature sensor in the wall |
| T1 top | S, 0.09 m² | Tray undersides, flour dust, melt water | Wiped by the scraper tool into the sink; daily wash-down | Per meal | Coil at 60 °C for 1 min | Camera |
| CC plates, slabs, liner, flap | S, 0.9 m² | Frost, tray undersides, flour dust; drips if a tray leaks | Defrost rinse with slabs lifted (3.4), fan | Daily or after 3 meals | Fan 10 min, then pull-down | Plate temperature curve shows frost; camera at the flap |
| Hob deck, rings and troughs | S, 0.4 m² | Fat spatter, boil-over | Scraper tool, then daily wash-down; troughs flushed | Daily; after a spill at once | Residual heat | Camera |
| Gantry: shroud, quill, wrist head, jaw | S, 0.6 m² | Steam, grease aerosol, splashes; the jaw touches tabs only | Jaw and wrist: three nozzles and steam over the sink after every red phase; all: daily wash-down | Daily | Warm air | — |
| Press crosshead and rods, knife rod bellows, spin head, dock pour chute | S | Splashes | Daily wash-down; pour chute is loose ware | Daily | Warm air | — |
| Cell walls, door, deck, ceiling | S, about 6.9 m² | Steam, aerosol, flour dust | Fixed nozzle rails, 10 L sump at 60 °C recirculated 5 min, 5 L rinse; ceiling sloped to a gutter | Daily | Extraction fan and 40 °C air, below 65 % r.h. in 60 min | Humidity sensor |
| Rack well | S, clean side | Drips of clean ware | Rinse weekly | Weekly | Warm air | — |
| Slot washer tank, nozzles, hanger | S/F | Wash liquor | Self-wash at the daily dump | Daily | Drains | Turbidity of the tank |

Fixed Zone F: **0.45 m²** (the sink). Zone S: about **9.3 m²** [E], large because one gantry serves an
open bay of 1.72 m including the hob. The fixed Zone F would be zero if produce were washed only inside a
basket that never touches the well; I count the well because its water does touch the produce.

### 7.4 Water, energy and time per meal (4 persons, mean of the benchmarks) [E]

| Item | Water | Energy | Time |
|---|---|---|---|
| Slot washer, 18–25 flat items | 7–10 L | 0.7–1.0 kWh | 21–30 min in the background; about 40 extra gantry moves |
| Sink well rinses and steam | 6–7 L | 0.15 kWh | 3 min |
| Share of the daily cell wash, CC defrost, tank dump (24 L, 1.2 kWh per day, three meals) | 8 L | 0.4 kWh | 12 min per day |
| **K7-specific cleaning** | **21–25 L** | **1.3–1.5 kWh** | flat ware clean 25–30 min after its last use |
| Ware-wash chamber, one load of bulky preparation ware and cookware (not K7-specific) | 17–20 L | 1.3 kWh | 55–75 min |
| **Total for preparation and cooking ware** | **38–45 L** | **2.6–2.8 kWh** | |

With the dish washer load (about 10 L) and cooking water this exceeds RES-005 (45 L per reference meal) by
10–15 L and takes two thirds of RES-001 (4.0 kWh) before cooking. The chamber load is the largest single
item; if the chamber could be loaded only every second meal (second set of pots) the total falls to about
32 L.

### 7.5 Raw meat and ready-to-eat food

* Sequence (rule R11): dry and green work first, red work last; the scheduler enforces it.
* Separate instances: red tongs, red bow knife, red pin board, red cold trays (marked by a notch that the
  camera reads). The sink with its grate is the red bench; the dry bench T1 sees only the undersides of
  trays. After the red phase: red ware straight into the slot (cold pre-rinse within minutes, steam finish),
  sink steamed, jaw and wrist rinsed and steamed.
* Coating media that touched raw meat (flour, egg, crumbs) are discarded.
* One gantry means one air space: a red tray is not carried over open ready-to-eat food (FSF-041); the path
  planner routes it along the rear lane, and open vessels on its way are lidded first. This is procedural,
  not physical, separation.
* Tempered meat drips and smears far less than chilled meat [B:N12]; frozen purge stays on the tray and is
  washed off there. This is a real hygiene benefit of the concept.

### 7.6 Peelings and scraps

Everything cut, peeled or slipped falls into the sink or is tipped into it: peel slurry, skins, cores, egg
bath, crumbs. The 2 mm lift-out strainer holds the solids; the gantry carries the strainer to the waste port
beside the sink (a lidded chute to the organic bin in the base) and tips it. Egg shells go down the egg
module's own chute. Nothing passes over open food (PRP-033); no macerator.

### 7.7 Crevices, seals and spray shadows, named

1. Grid and harp dies: blade roots in the frame. The weakest loose part against HYG-013.
2. Rubber fingers pushed into the basket and disc (the way plucker fingers are mounted): a crevice at every
   finger. Needs a one-piece moulded finger sheet or yearly replacement.
3. Rasp basket teeth hold starch; knurled steel, no bonded grit.
4. Bow knife blade clamps and the scallops of the blade.
5. Pin roots on the pin board; tab welds on all ware; the Ø 8 locating holes.
6. Rotor lids: shaft in a PEEK bush; taken apart by the gantry for the chamber (two parts each).
7. Roller tool: journals in open forks, no bore.
8. Sink: underside of the hub umbrella (flush nozzle inside), drain valve seat, strainer seat.
9. Jaw: the 3.2 mm slot and the cone pin. The slot is open on both sides so that jets pass; it touches tabs,
   not food.
10. Quill wiper collar, wrist shaft seal, cover-strip lips of the X module, press rod collars, knife bellows.
11. CC: the contact faces between slab and plate (rinsed with the slabs lifted), comb ledges, flap gasket,
    rear drain channel (heated so that it cannot freeze shut).
12. Hob ring troughs.
13. The dock: a powder place that must stay dry; only its loose pour chute is washed.

---

## 8. Numbers

All values are estimates [E] unless a calculation is referenced.

| Quantity | Value |
|---|---|
| Wall width | **2280 mm**: oven column 560, preparation bay 1000, hob bay 720. Cell without the oven column: 1720 mm. Depth 600, height 2000 used completely (the quill retracts into the top 450 mm) |
| Motion actuators | **24** (gantry 5, cold cabinet 2, press 1, knife 1, sink 1, slot lift 1, hob turntables 4, spin head 1, dock 3, bench vibrator 1, egg module 3, oven door 1), plus 1 drain valve actuator, 8 solenoid valves, compressor, condenser fan, circulation pump, steam generator, extraction fan |
| Of these, caused by the state-change idea itself | 2 (slab lift, flap) and the refrigeration set |
| Loose items | about 105 preparation ware and tools of about 50 types, plus 27 pieces of cookware; per 4-person meal 25–40 items are soiled, 18–25 of them flat |
| Custom part types | about 40 in ware and tools; 12 custom machine assemblies (quill and wrist, jaw, plate stack with comb, press, knife drive, sink with hub, slot washer, rack, turntable rings, spin head, dock, egg module) |
| Parts cost, one-off | about **32 000 €** ±30 %: gantry 5 500; cold cabinet with refrigeration 2 550; press 1 200; knife 450; sink and inserts 1 600; slot washer and rack 1 600; weigh bench and coil 450; dock and egg module 1 600; spin head and lids 700; hob with turntables 2 500; oven and door 3 300; ware, dies and tools 3 800; cookware 900; cell, lining, extraction, wash-down 3 600; sensors 750; control and power 1 500. Preparation proper (without oven, hob, cookware, cell): about 22 000 € |
| Peak power | Installed: hob 11.4 kW, oven 3.3, steam 2, wash tank 2, flash coil 1.5, compressor 0.3, drives 0.8. Load-managed to **10.5 kW** on 3 × 16 A; typical during a meal 5–7 kW |
| Energy of the cold side | 0.6 kWh per day (3.4) |
| Noise sources | Bow knife 65–70 dB(A) for 1–4 min per meal; blender stalk and blade lid 70 dB(A), seconds; press strokes through a grid (impact of the cut-off); sink spin 600 rpm and rasp peeling (rumble, 2–3 min); slot washer pump and air knife, 25 min per meal inside a closed slot; compressor and fan about 40 dB(A); extraction 55 dB(A). The knife and the rasp together are near the 5 min budget of NOI-003 |
| Handling moves per meal | Preparation and cooking 25–140, mean 80 (section 6); plus about 40 for washing logistics; about **120** in total. REL-001 (98 % of meals without intervention) then needs 99.98 % per move; tabs with cone capture, a camera check after each pick and one automatic retry are assumed |
| Zone F fixed / Zone S | 0.45 m² / 9.3 m² |
| Cleaning per meal, K7-specific | 21–25 L, 1.3–1.5 kWh, flat ware ready again 25–30 min after use (7.4) |
| Throughput against PRP-023 | 1.5 kg potatoes washed, rasped and halved: 8 min (limit 10); 1 kg mixed vegetables diced: 6 min (limit 6); 1.6 kg dough, 1.2 kg mince: yes; 12 patties: 2 min direct, 6 min staged (limit 5) |

---

## 9. Coverage estimate against the 248-meal corpus

Method: the hard operations of every row were looked up by script (WRP, STU, ASM, FRM, SHD, LSP, RLT, CAR,
UNM, FRK, BRD, STR, PLE, PLP and others) and each affected row was judged against section 5. This is a
judgement per row on paper, not a full walk-through of 248 meals.

### 9.1 Meals that fall out

| Group | Meals | Reason |
|---|---|---|
| Excluded by the requirements (5.4) | CK11, DM21, DS13, BF08, AS05, BK06, CK08, BK02 (8) | X-01, X-04, X-07, X-09, X-11, X-12 |
| Wrapping a limp sheet round a filling | DM12 Kohlrouladen (also leaf separation), AS08 spring rolls, IN07 samosa, MX03 burritos, CK12 strudel, CK13 sponge roll (6) | No flexible work surface, no dexterous hand: excluded by the definition of K7. A frozen-rigid filling does not help, because the difficulty is the sheet |
| Pleating and braiding | AS09 gyoza, BK04 Hefezopf (2) | Difficulty 5; no mechanism |

**Certain: 16 out, 232 of 248 = 93.5 % by count, 95.8 % by weight.**

Doubtful (medium-low confidence; I expect three to five of the ten to fail): MX07 enchiladas (fork winding
of a tortilla), ME03 gyros in pita, US06 pulled pork (shredding), DS11 Germknödel (closing the dough),
SD22 Schupfnudeln (tapered shape), BK03 rolls (rounding), BF14 poached egg, DM20 roast chicken (bone-in
carving; weight 3), VG04 stuffed zucchini (hollowing), DM13 stuffed peppers (coring).

**Estimate: 92–93 % by count (227–230 of 248), about 94–95 % by weight. MEAL-002 (95 % by count) is
missed by six to nine meals.** MEAL-003 holds except for DM20, which every candidate shares. MEAL-004
(≥ 85 % in every category with ten or more meals) is missed for Asian dishes (9 of 12) and cakes (13 of 17).
MEAL-005 (the meals named in the brief) holds.

What would close the gap: one loose rolling mat used with the winding fork (apron roll, SM-080) would
bring back up to six wrap meals and lift the estimate to about 95 %. That is a borrowing from K4 and breaks
K7's exclusion of flexible surfaces; I record it as the most valuable import (section 12.3).

### 9.2 Where the state change actually matters

| Role of the cold or heat step | Meals [R2 codes] | Count |
|---|---|---|
| Decisive: no equally simple route in this cell | Breading (DM03, DM05, SD21, FI02, US05), flat pockets and attachments (DM05, IT12), small formed pieces (SD21, ME05, IT08, SD22), rigid filling rods and cores (IT18, DS11) | about 12 |
| Useful: faster, cleaner or more reliable | Raw meat strips and cubes (15), staged patties and dumplings (9), Rouladen seam (1), soft cheese, sausage, tomato, bacon cut tempered, set desserts and quick chilling (CHL 15, COL 27, partly overlapping), cooked-first potatoes (14) | about 60, of which about 40 not already counted |
| Dosing as frozen pieces | Fats (DBL, 51 % of meals), pastes, herbs, garlic | about half of the corpus, as a simplification of dosing, not as an enabler |
| No role | everything else | about 120 |

### 9.3 Adapted methods (MEAL-013, limit 10 % = 24 meals)

Finding for all candidates: **the requirements themselves already make 19 meals "adapted"** — nine
deep-fried dishes baked or shallow-fried (X-01), seven stir-fries in an agitated pan (UO-76), the toasted
sandwich (X-11), and three meals without skewer or skimming (X-13). That is 7.7 % of the corpus before any
concept adds its own; five meals are left.

K7's own account (17 of the 19 are among its covered meals = 6.9 %):

| Counting rule | Additional K7 meals | Total | Share |
|---|---|---|---|
| Strict: every meal whose method includes crust-freezing counts as adapted | DM03, DM05, IT12, DM01, DM10, DM11, DM35, ME09, US01, SD07, SD08, DS11, SD22, IT08, BK03, DM02, IT18 (17) | 34 | **13.7 % — outside** |
| Lenient: tempering is a handling aid like chilling dough; only a changed result counts | DM05 (two cutlets instead of a pocket), BK03 (rolls not rounded), IT08 and SD22 (moulded shapes), and SD07, SD08 if dumplings are cylinders | 21–23 | **8.5–9.3 % — inside** |

Reorderings that I class as traditional and do not count: mash from potatoes boiled in their skins;
Bratkartoffeln and potato salad from cooked, cooled potatoes; pins in Rouladen; garlic, herbs and pastes
from the freezer; frozen diced onion (a permitted purchase); cauliflower divided after cooking; patties
smashed in the pan.

Reorderings that K7 must **not** use because the budget cannot pay for them: Salzkartoffeln as peeled
Pellkartoffeln (SD01, VG02, DM31 and similar), blanched onions in raw salads, one large Roulade, a
flour-and-egg batter instead of three coating steps, two-sided contact instead of flipping a steak. This is
why the cell carries a raw peeler: **46 corpus meals peel potato or carrot raw** and only 14 cook first;
without the rasp basket K7 would be at 25 % adapted or would lose the soups.

So the answer to the catalogue's question 3 is: inside the 10 % only under the lenient rule, with the raw
peeler, and with at most four or five genuine shape adaptations. A ruling is needed (section 14).

### 9.4 MEAL-009 (whole fresh produce, ≥ 90 %)

Not met, as for every candidate at this stage. K7's contribution is the blanch-and-slip route for onions
(SM-063, medium-low, part-cooked outer layer) and skins slipped after cooking. Peppers, beans, mushrooms,
herbs on the stalk, banana and avocado have no K7 mechanism. My estimate is 60–70 %.

---

## 10. Failure modes and recovery

| Failure | Detection | Recovery |
|---|---|---|
| Tab missed or tray dropped | Jaw travel and camera after every pick | Retry from a new camera fix. A dropped rigid item is picked up again with tongs and, if it fell on Zone S, discarded into the sink; a dropped tray is washed |
| Food frozen to the tray does not release | Tray does not empty when tipped (weight on the receiving tray) | Second flash of 2 s; then 60 s wait; then the turner |
| Lid sheet or tray frozen to a slab or plate (water on the outside) | Lift force on the jaw | Slab lifted, 30 s wait; defrost rinse of that level; rule: trays dry underneath |
| Item not rigid after the clamp time (frost, warm stack) | Plate temperature curve; deflection seen by the camera when the tray is tilted | Back for 60 s; schedule a defrost |
| Cutlet folded or wrinkled at lay-down | Camera outline against the expected area | Tongs drag it flat once; else it is flattened as it is (a smaller, thicker Schnitzel) and flagged |
| Roll unwinds when stripped or in the pan | Camera | Re-wound once; pin set; in the pan: tongs turn it seam-down and hold 20 s |
| Pin left in the food | Count of pins out against pins in (magnet at the pin setter) | Plate is held back, user informed |
| Patty or dumpling breaks at transfer | Weight and camera | Pieces pressed together with the turner in the pan; dumpling pieces discarded |
| Grid die jams (hard carrot, stone) | Press force above the limit before the stroke ends | Retract, second stroke at half feed, then the load is tipped out and the die inspected by camera (PRP-035); blade fragment: food discarded |
| Bow knife blade breaks or dulls | Drive current, tension | Second bow; blade exchange is an announced human task (HUM-007) |
| Rasp peeling leaves eyes and skin patches | Camera on the tray: dark area fraction | 30 s more; accepted up to 5 % (PRP-022); worst pieces diverted to a mash or soup use |
| Flat part fails the visual check after the slot | Camera | Second cycle; then the chamber; then quarantine (HYG-026) |
| Cold cabinet fails or is frosted up | Plate temperature | Degraded menu: patties direct to the pan, Rouladen pinned without weld, cutlets breaded limp with tongs (medium-low), cordon bleu and croquettes not offered |
| Refrigerant leak | Pressure and temperature; the base is ventilated, charge below 150 g | Unit locked out, service |
| Power loss | — | Food in the cabinet stays cold for hours; the FSF-030 rule decides the rest |
| Gantry fault with a pan on the hob | Drive fault | Hob power off through the independent safety chain; the single gantry is a single point of failure for the whole cell |
| Spill on the hob or deck | Camera, humidity | Scraper tool, local rinse, daily wash brought forward |

---

## 11. Top risks and the cheapest experiment for each

| # | Risk | Consequence if true | Cheapest experiment |
|---|---|---|---|
| 1 | Real contact coefficient is 150 instead of 300–500 W/m²·K (thin trays, frost, uneven food) | All clamp times double; patties staged for six take 9 min; the concept's time argument weakens | Two 10 mm aluminium plates cooled in a chest freezer to −25 °C, a 0.6 mm steel tray and lid, pork cutlets and mince with two thermocouples each, a 2 kg weight: time to rigid. One day, under 100 € |
| 2 | Frozen food does not release by a 1.5 s induction flash, or the lid sheet does not peel | Every tempered batch needs minutes more; handling count rises | Same trays on a household induction hob; 20 releases |
| 3 | Crust-frozen cutlets, patties and cubes fry worse (pan recovery, fat uptake, juice) | Customer rejects; K7 loses its reason | Blind comparison of 12 Schnitzel and 12 Frikadellen, half tempered, by five eaters (MEAL-015); a weekend in a kitchen |
| 4 | Flour-before-freezing breading does not reach 95 % coverage or the crumb lifts | BRD falls back to limp handling with tongs | Part of experiment 3: coverage by photograph before and after frying |
| 5 | Ice-welded seam opens during searing or braising | Pins stay the method; the weld is dropped and 5.7 min with it (no loss of coverage) | 12 Rouladen, 6 welded and 6 pinned, seared and braised 90 min. One day |
| 6 | The one limp pick fails: slices stick, fold or tear when taken from a retail pack with tweezer tongs | Cutlets and Roulade slices cannot enter the process; meat must be bought as a piece and sliced by the machine, which needs deep tempering or a super-chilled store | 50 slices from 10 retail packs, taken with a pair of long tweezers guided by a straight-line jig (no wrist); count clean lay-downs |
| 7 | Winding on the fork does not start or the roll deforms when stripped | Rouladen only as folded parcels (adapted) or not at all — a meal named in the brief | Hand jig: two prongs on a crank, 20 slices with filling |
| 8 | Frost builds faster than estimated in a steamy cell; trays freeze to the plates | Defrost after every meal, 0.3 kWh and 40 min each | Chest-freezer mock-up with a flap beside a boiling kettle, 30 tray exchanges, weigh the frost |
| 9 | Slot washer leaves shadows in rim corners, at tab welds and in grid cells | Flat ware goes to the chamber; 20 more chamber items per meal, the ware stock doubles | Two spray bars, a pump and a tray on a string; riboflavin test. Two days |
| 10 | Frozen pucks and cubes sinter into lumps in the freezer box over weeks | Dosing by count fails; pastes need a conventional doser | 200 tomato-paste pucks and butter cubes in a box, taken out for 60 s daily for four weeks |
| 11 | 120 moves per meal at one gantry: reliability and time | REL-001 missed; B7, B8 already have only 3–4 min of margin | Move-time study on any XYZ rig with the real tab and jaw: 1 000 picks |
| 12 | Customer does not accept that fresh meat is frozen at the surface | Tempering limited to mince, cheese, fillings; breading falls back as in 4 | A question to the customer (section 14) |
| 13 | Wall width of 2.28 m, with a poorly used rear strip in the preparation bay | The cell does not fit a kitchen run together with storage and washing | Layout review with the architect; the cold "toaster" well (12.2) saves nothing in width by itself |

Experiments 1 to 5 need one chest freezer, two aluminium plates, an induction hob and a week.

---

## 12. Improvements found, changes from the catalogue definition, borrowings

### 12.1 What I changed from the catalogue definition of K7, and why

| Catalogue definition | This document | Reason |
|---|---|---|
| Double-sided −25 °C contact plate, upper plate lowers | Five fixed evaporator plates with five loose cold slabs lifted by one comb; two 70 mm and three 45 mm daylights | No moving refrigerant line; five trays at once removes the plate queue; the slabs' heat capacity does the top face |
| 250 W "ice-cream roll" unit | 21.5 kg of aluminium as thermal store plus a 200–300 W low-temperature compressor; idle at −12 °C | The food draws kilowatts for seconds; the mass shaves the peak [C] |
| Cutlet breaded as a rigid plate after "30–60 s in air gives a tacky film" | Flour is pressed on before freezing, in the same sandwich in which the cutlet is flattened | The tacky film does not form for more than 5 min [C] |
| Band knife | Reciprocating bow knife, one loose part | A band knife has two wheels, guides and a wiper box in the food zone; the bow goes through the slot washer |
| Rouladen closed in a U-cradle (SM-083), seam frozen | Wound on a fork on the wrist axis (SM-082), stripped into a trough, seam frozen, pinned until the weld is proven | A folded parcel is not a rolled Roulade (MEAL-005); the wrist axis is there anyway |
| Rubber-finger skin slipper drum Ø 250 | Rubber-finger basket and disc in the sink well; the same turntable spins salad and drives the rasp peeler | One drive, one wet place |
| Raw abrasive peeling "only if the adapted budget is exceeded" | Kept as standard equipment | The budget is exceeded (9.3) |
| Mince "formed like ice cubes" in mould trays | Extrude and cut on the press; crust-freezing only to stage and to slide; through-hole plates only for small pieces | Screeding sticky mince into cavities by a gantry is the weak step; the direct route is faster (B3) |
| SM-014 or SM-009 for produce | SM-009 on a 3 kN press under the deck | The press is also platen, ricer, extruder and knock-out |
| Loose ware to the wash chamber (8–12 parts per meal) | Slot washer for flat ware inside the cell | The honest count is 25–40 parts per meal; the chamber cannot take them |
| 14 actuators, 1000 mm bay | 24 actuators, 1720 mm cell plus oven column | Hob, stirring, dock, egg module, washer and oven door are included |
| Ice chuck (SM-004), freeze gripper (SM-098) | Not in the baseline; the cold pick plate is the fallback for the limp pick | A thin tray holds too little cold: 3 kJ, gone in 45 s in air [C] |

### 12.2 Improvements worth keeping, whatever becomes of K7

1. **Fixed plates plus loose cold slabs, with the aluminium as a thermal store.** It turns a process that
   needs kilowatts for seconds into a job for a freezer compressor, takes five trays at once, and has no
   moving refrigerant part. This is the most valuable improvement of this round, because it removes the
   concept's named main weakness (the plate queue) with one actuator.
2. **Flour before freezing, in the flattening sandwich.** One press stroke flattens, flours both faces and
   prepares the contact for the plate.
3. **Ice-weld as a joining method for flat pockets**: cordon bleu from two cutlets with a welded rim,
   ham and sage frozen on for saltimbocca, a frozen jam core for Germknödel, rigid filling rods for
   cannelloni and plugs for peppers. It is the only proposal so far for catalogue gap G4 besides
   fold-and-pin; unproven.
4. **Rigid things pour.** Crust-frozen patties, cutlets, slices and dice slide off a tilted tray; six
   patties enter the pan in one move.
5. **Chill steps in minutes**: cooked potatoes for Bratkartoffeln and potato salad, shortcrust rest,
   puddings and panna cotta set in 20–30 min, COK-022 without a separate chiller.
6. **Temper before cutting for everything soft**, not only meat: mozzarella, tomato, sausage, bacon,
   chicken, fish, pork rind before scoring.
7. **Frozen roux and stock pucks**: thickening becomes counting.
8. **The flash coil under the weigh bench** serves both directions: release of frozen food and tins,
   softening butter, drying the bench.
9. **Slot washer with steam finish** for thin flat ware: about 0.4 L and 70 s per item.
10. **Oven fries steamed and crust-frozen before the oven**, as the industry does: a way to make the
    adapted SD04 (weight 3) pass MEAL-015.
11. **Pre-forming at ingestion** (option, customer decision): when meat is frozen at ingestion anyway
    (FSF-052), the cell lays cutlets flat, flours and freezes them as plates, and forms and freezes patties,
    so that later meals start with rigid countable parts and the limp pick happens once, without time
    pressure.
12. **Super-chilled raw-meat zone** (−2 to −3 °C) in cold storage: meat would arrive firm, a piece could be
    sliced by the bow knife without a tempering wait, and chilled shelf life grows [K]. A request, not part
    of the cell.
13. **Cold "toaster" well** (alternative not adopted): vertical plates in a top-opening well below the
    bench, loaded like the slot washer. Keeps the cold in, has no flap and frees the rear strip; but limp
    food in a vertical sandwich may slump, and liquids cannot be frozen. Worth a test if the horizontal
    cabinet's lane proves awkward.

### 12.3 What I would borrow from other candidates

* From K4 (mat): **one loose silicone-glass rolling mat** for wraps, strudel, sponge roll and cabbage
  rolls, used with the winding fork. Closes most of the coverage gap (9.1).
* From K5 (ram and die column): the comb piston and staggered grids are already here; a piston box for
  mustard and quark would replace the spoon.
* From K2 (vessel stack): a grating or slicing disc on the rim of the rotating bowl (SM-013) to close the
  grating gap and to speed up slicing.
* From K6 (loose ware, fast washer): if its 3-minute rack washer exists, the slot washer and the chamber
  load could both go to it.
* From K1 or K8: a second hand. One gantry doing 120 moves is the throughput limit of this cell.

---

## 13. Answers to the catalogue's questions for K7

1. **Plank times; plate area for six Rouladen plus six Frikadellen.** Confirmed within ±20 % by an
   enthalpy model (3.1). Six Rouladen need two cassettes (the two 70 mm levels), six patties one tray:
   three of five levels, 0.19 m² of plate, all at once; stack load about 170 kJ, rise 9 K, no queue.
   Schedule in 3.3.
2. **Does crust-freezing change the result?** On paper: +15–25 s frying time, harder pan recovery, more
   spatter, no expected difference in juice for breaded, minced and braised food; crumb adhesion needs the
   changed order. Not tested (risks 3, 4).
3. **Class-A reorderings against the 10 %.** 9.3: inside only under the lenient rule (8.5–9.3 %), strict
   13.7 %. The raw peeler needed for the staples is the rasp basket in the sink.
4. **Ice-weld through a two-hour braise; pin fallback.** Unknown; the pin is the default and is easy to set
   in a rigid roll (risk 5).
5. **Frost, defrost, interfaces.** 1–4 g of frost per meal; daily rinse-defrost; cold side 0.6 kWh per day
   (3.4). Freezer: 12–15 extra small boxes for pucks, cubes and herbs. Ingestion: fresh herbs straight to
   the freezer; jars and tubes of paste converted to pucks by the preparation cell at first opening
   (20 min of cell time per jar, off-peak). FSF-013: frozen boxes are at the dock for under 60 s per dose.
   FSF-012 needs a clarification: tempering thawed meat minutes before cooking is not refreezing for
   storage (section 14).
6. **Customer decision.** See section 14.

Standard questions of catalogue 3.1 in short: (2) MEAL-018 operations solved: FLP, ASM (layers and simple
stacks), CAR (boneless), UNM, SCO, STU, FRM, ROL, SHD, BRD, RLT, FRB, FRK; failed: WRP of limp sheets, LSP,
pleating, braiding, bone-in carving, trussing, strip and pluck, trimming small items. (3) Surfaces: 7.3.
(4) Counts: section 8. (5) Width for the 6-person vessel set and four positions: 2280 mm with the oven.
(6) Class R and RTE: 7.5. (7) Requests: section 14. (8) Adapted share: 9.3.

---

## 14. Open issues and requests to the architect

### 14.1 Open issues

1. Every food result in this document is untested (section 11). The concept stands or falls with
   experiments 1 to 6, which cost a week.
2. The limp pick from the retail pack is outside the concept's own logic and only medium-low.
3. No grater; no solution for wraps, leaf separation, pleating, braiding, trimming of small produce.
4. The rear strip of the preparation bay is poorly used (oven corridor and cabinet lane must stay clear).
5. The hob with four rotating positions is assumed, not designed; the rim scraper for stirring is a
   cooking-module item.
6. Water: the cell plus the chamber load exceed RES-005 (7.4).
7. Hemispherical and tapered moulds, the rod mould and the rubber-finger basket are sketches without
   release tests.
8. Gantry path planning with keep-clear zones (oven corridor, cabinet lane, bow knife, press crosshead) has
   not been simulated; the move times of section 6 assume no waiting for clearance.
9. Whole spices, bay leaves and pins that travel with the food to the plate must be removed by serving.

### 14.2 Requests to the architect and to other modules

| To | Request |
|---|---|
| Customer | Is it acceptable that fresh meat, fish and mince are frozen at the surface for 2–6 minutes before cooking? Is batch pre-forming at ingestion (floured frozen cutlets, frozen raw patties made by the machine) acceptable? |
| Requirements | Ruling on MEAL-013: does an intermediate tempering step make a meal "adapted"? Note that 19 meals are already adapted by sections 5.3 and 5.4, leaving five. Clarify FSF-012 for tempering before cooking |
| Box standard | None beyond the common dock assumption. Carrier boxes for cans, cartons and tubs need the K7 tab (or any grip feature for a side-gripping jaw). Frozen goods in the smallest box size, lids that open in under 5 s |
| Cold storage | +12–15 small freezer positions (pucks, cubes, herbs, diced onion). Optional third zone at −2 to −3 °C for six boxes of raw meat. If the cold store gets its own compressor, a second evaporator branch for the plate stack can be considered |
| Ingestion | Fresh herbs frozen at ingestion; meat planned for later frozen flat (FSF-052) — ideally laid out by the preparation cell; jars and tubes of paste routed once through the preparation cell for puck making |
| Transport | Box hand-over port on the left above the oven column at z 1300–1600; cooked-food hand-over through the right wall at bench level; waste bin and strainer port below the sink |
| Cooking module | Four induction positions under rotating rings (P4 with 25 Nm and 300 rpm); bought combi-steam oven mounted sideways with a door that drops below bench level, started without human action (COK-023); all cookware with the K7 tab; matching pan pair and GN 2/3 pair |
| Washing module | Chamber capacity for 12–15 bulky items per meal within 60 min of use; shared detergent and softened-water supply for the slot washer |
| Serving | Pins and whole spices removed and counted; slicing of bread and cake can use the bow knife |
| Safety | R290 charge below 150 g in a ventilated base; guarding of the bow knife and the press behind the interlocked door; 3 kN press and 600 rpm spin inside a household cabinet |

