# K8 — Sealed tub with magnetic pucks

Round P3 exploration of candidate K8 (catalogue `02-concept-catalogue.md` §3.9). Written independently; no
other file in `design/prep/concepts/` was read.

Inputs: `BRIEF.md`, `DECISIONS.md`, `03-exploration-brief.md`, the catalogue, idea files D (concept B,
WALL PUCK) and E (concept A, SPÜLZELLE) in full, the others skimmed; `requirements/requirements.md`
(3.5, 3.6, 5, 7); `research/02` (4.2–4.9, 6.3, benchmark rows), `research/04` (forces, torques),
`research/05`, `research/06` (wash programmes).

**Status of the numbers.** Nothing was built. Tags: **[C]** calculated by me (method in Appendix A),
**[E]** my engineering estimate, **[S]** taken from a research document, **[U]** from memory, unverified.
Magnetic figures are given twice where it matters: the model value and a *design value* = 0.8 × model
(allowance for real back iron, magnet tolerance, temperature and gap tolerance). All of them must be
measured on the rig of risk 1 before anything else is decided.

**Result in one paragraph.** The catalogue's force ceiling (about 100 N, 8 Nm) is roughly confirmed for
in-plane force and is pessimistic for torque: a Ø 150 magnet ring through a 1.5 mm wall gives about
110–130 N while moving, 220–250 N while holding still, and 12 Nm of spindle torque (design values). The
in-plane force is limited by skid friction as much as by magnetism. The concept therefore works only if
force is made *from torque inside the ware* (a screw cassette gives 2.5 kN from 12 Nm), *by leaning on the
wall* (compression is unlimited), and by *canned* radial couplings for the turntable (25 Nm). With these
three rules no sealed through-wall spindle, ball port or bellows press is needed for the benchmark meals.
What the concept cannot buy back is the missing depth axis and the long list of loose parts; and all of it
hangs on magnet and friction figures that are calculated, not measured.

---

## 1. Definition

The preparation **and cooking** cell is one stainless tub, 1100 × 475 × 700 mm inside, built like a
dishwasher tub: closed coved sheets, floor sloped to a sump, a gasketed door. Nothing moves through any wall.
There is no shaft, rod, rail, arm, cable, spray arm or bearing fixed inside.

* **Drive wall = the front door.** The door is a 115 mm thick cassette. Its inner skin is a flat 1.5 mm
  sheet of 1.4404. Behind the skin, in the dry, runs a dual-bridge X–Z gantry with two *heads*. Each head
  carries one rotating ring of 20 magnets. Removing the outer décor panel exposes every motor from the room.
* **Pucks.** Inside, opposite each head, a passive *puck* (Ø 190 × 40, 1.1 kg) clings to the door skin. It
  consists of two loose parts: a welded *rotor* disc with 20 encapsulated SmCo magnets and a bayonet spigot,
  and a *spider* with four skids. The one magnet ring does three jobs: it clamps the puck to the wall, it
  drags it in X and Z, and it turns the rotor (the horizontal wrist axis, normal to the wall).
* **Two canned drives in the floor.** A turntable *T* (25 Nm, 0–500 rpm) and a speed spindle *S* (1.5 Nm,
  0–6000 rpm) work through deep-drawn, welded thimbles: magnet couplings with a radial gap, no seal.
* **Four induction positions** under one glass-ceramic plate set flush into the floor, two at the wall
  (GN 1/2) and two in front of them (GN 1/4). All cooking ware is rectangular (GN, induction-capable).
* **Everything else is ware**: pucks, utensils, cassettes, vessels, boards. After the meal the tub washes
  itself and its contents; the pucks carry each vessel through a fixed jet gate and finally hang themselves
  up to be washed.
* **Openings** (static seals, closed during work and wash): a dosing port in the ceiling, a hand-over hatch
  in the left wall, an oven hatch in the right wall. The combi-steam oven stands beside the tub, turned 90°,
  its cavity floor level with the tub floor, so vessels are slid in, not lifted.

```
FRONT VIEW (seen from the room, décor panel and gantry removed; dimensions in mm, interior)

      dosing dock + box tilter + scale (dry)          exhaust fan, condenser (dry)
   ______[port Ø160]_________________________________________________________________
 700|  u  u  u  u  u  u  u  u  u  u  u  u   <- clean utensils parked on the top strip     |
 650|u ....................................................................................|
    |u :                         travel field of the two heads                            :|
    |u :      (P1)                                        (P2)                            :|      OVEN BAY
    |u :      puck 1, "prep hand"                         puck 2, "cook hand"             :|   (combi-steam oven,
 450|u :   jet                                                                            :|    turned 90°)
    |  :   gate     board on carrier (when used)                                          :|
    |  :   |||    _______________                                                         :|___________
 250|  :   |||   | bowl Ø280     |      __________________      __________________       hatch  cavity
    |[hatch to   |  on carrier   |     |  GN 1/2 pot/pan  |    |  GN 1/2 pot/pan  |      440 x   480 W
    | transport] |_______________|     |__________________|    |__________________|      300     x 400 D
   0|__sump______(( T thimble ))_______[ hob 1  3.5 kW    ]____[ hob 2  3.5 kW    ]_______|______x 350 H
    0           180            360    395               720   740              1065    1100
     <-- column A: prep, wash -->      <-------- columns B, C: hob (glass-ceramic) -------->

    | services below the floor: induction generators, T and S drives, sump, 3 pumps, tank 8 L, boiler 8 L |


TOP VIEW (interior 1100 x 475)

  Y=475 ___________________________________________________________________________ fixed rear wall
       | sump    ( S )jug Ø150 |  [ hob 3  GN 1/4 ]      |  [ hob 4  GN 1/4 ]      |
       | well                  |   265 x 162, 2.3 kW     |   265 x 162, 2.3 kW     |
  308  | 110x140               |                         |                         |==> oven hatch
       |       ____            |   ___________________   |   ___________________   |    (both rows can
       |      /    \  T        |  | hob 1  GN 1/2     |  |  | hob 2  GN 1/2     |  |     slide through)
       |     | bowl |  Ø280    |  | 325 x 265, 3.5 kW |  |  | 325 x 265, 3.5 kW |  |
       |      \____/           |  |___________________|  |  |___________________|  |
   35  |- - - - - - - - - - - - gutter strip 35 mm, water and drips run to the sump - - - - - - - |
   Y=0 |====(P1)=====================================(P2)=======================================|  drive wall
       |  door cassette 115 mm: 1.5 skin | heads, ring Ø150 | Z screws | X beams | décor panel     |
       X=0                   360                       730                       1100
       hatch to transport in the left wall; jet gate = plane X = 60 (nozzles in wall, ceiling, floor)
```

Module: 1150 mm wide (tub) + 600 mm (oven bay) = **1750 mm of wall** at 600 depth; tub floor 900 mm above
the room floor, tub top at 1600, dock above to 2000. Without the oven bay (oven elsewhere, served by the
transport system) the cell is 1150 mm.

---

## 2. Mechanism

### 2.1 The magnetic coupling: what goes through the wall

**Arrangement.** Head: 20 blocks 14 × 14 × 6 mm NdFeB N45SH (Br 1.33 T, 150 °C grade) on a 6 mm mild-steel
ring, centres on R = 68 mm, alternating polarity (pole pitch 21 mm). Puck rotor: 20 blocks 14 × 14 × 5 mm
Sm₂Co₁₇ (Br 1.08 T, usable to 300 °C, does not corrode) on a 4 mm ring of ferritic 1.4016, laser-welded
into a 1.4404 can with a 0.5 mm skin. Spider: four 15 × 15 × 5 SmCo magnets at R = 95 mm in its feet,
facing four fixed NdFeB magnets on the non-rotating head frame (orientation and extra hold).

**Gap.** Wall 1.5 + puck skin 0.5 + wet clearance 1.2 (set by the skids) + dry clearance 0.8 = **4.0 mm**
magnet to magnet. Austenitic 1.4404 is used because its austenite is stable (µr < 1.01 also after forming);
1.4301 becomes slightly magnetic when cold-worked.

**Calculated forces** (surface-charge model, Appendix A; the check case reproduces a supplier's pull force
for a Ø 20 × 10 magnet pair within 10 %).

| Quantity | Model [C] | Design value (× 0.8) |
|---|---|---|
| Normal clamp force N, ring + spider, work gap 4.0 mm | 638 + 130 = 768 N | **610 N** |
| N with the head retracted 6 mm (travel mode) | 200 + ~30 N | 185 N |
| N with the head retracted 16 mm (release) | 34 N | 27 N |
| Lateral stiffness at the centre | 66 + 11 = 77 N/mm | 62 N/mm |
| Lateral (shear) force at 4 mm lag | 229 + 44 = 273 N | **220 N** |
| Lateral force at 7 mm lag (N has dropped to 55 %) | 317 N + spider | ~280 N, breakaway |
| Peak torque of the ring (at 9° mechanical lag) | 33.9 Nm | 27 Nm |
| Torque at 3.7° lag (41 % of the pole angle) | 20.2 Nm | 16 Nm short-time; **12 Nm rated** |
| N remaining at rated torque and 4 mm lag together | 421 N + spider | ~420 N |
| Shear at 4 mm lag while at 60 % torque | 180 N + spider | 180 N |
| Spider yaw holding torque at 2° / 4° | 3.7 / 5.5 Nm | 3 / 4.4 Nm |
| Sensitivity to the gap: N at 3.5 / 4.5 / 5.0 mm (ring only) | 709 / 575 / 520 N | ±10 % per 0.5 mm |

Physics worth stating, because it sets the limits:

* For alternating poles the shear stiffness is tied to the clamp force: k ≈ N·π/τ (τ = pole pitch). You
  cannot have shear without clamp force. Peak shear equals about half of N₀ and is reached where N has
  fallen to half; the usable shear with N still above 80 % is about 0.35 N₀.
* Torque and clamp force are tied the same way: T_peak/N₀ ≈ 0.053 m for this ring (≈ 0.78 R). A large ring
  radius buys torque without buying clamp force; that is why the ring is Ø 150 and not D's Ø 90.
* D's figure "six N52 pairs give 400 N" is optimistic by about a factor of 1.6 for Ø 20 magnets at this gap
  [C]; D's torque "4–8 Nm for a Ø 90 face coupling" is about right for that size. The larger ring gives more.

**Friction of the puck on the wall.** The clamp force rests on four skids of blue PTFE-filled food-grade
PEEK (Ø 20, crowned) on the spider, at the corners of a 125 mm square. Rollers were rejected: the puck moves
in two directions, so a roller would scrub in one of them, and a roller on an axle is a crevice. Friction
µ ≈ 0.15 on clean 2B steel, dry or wet [E, range 0.10–0.25]:

| Mode | N | Friction µN | Net in-plane force available |
|---|---|---|---|
| Work, moving against a load | 610 N | ~90 N | 220 − 90 = **~130 N** (rated 110 N) |
| Work, holding still | 610 N | adds | 220 + 90 → rated **250 N** |
| Travel (head retracted 6 mm) | 185 N | ~28 N | ~40 N, enough to carry 3 kg at 0.5 m/s |

So the in-plane limit is **110 N moving / 250 N holding**, and one third of the magnetic shear is eaten by
friction. Sticky soil on the wall (dough smear, syrup) can double µ; this is risk 2. An option that stays in
the spirit of the concept is a *wet wall*: a drip bar along the top edge wets the drive wall on demand
(0.3 L/min, runs down into the 35 mm gutter strip and to the sump). A water film lowers µ to about 0.05–0.1
[E], flushes grit from under the skids and keeps splashes from drying. It is not used above the dry dosing
column.

**Tilting moment (the cantilevered utensil).** A force F at distance d from the wall tilts the puck about a
line through two skids, 62 mm from the centre. Tipping starts at N × 0.062 m = 38 Nm (design value); rated
**20 Nm**. Consequences:

| Load case | Shear | Tilt moment | Rotor torque | Verdict |
|---|---|---|---|---|
| Chop with a 200 mm blade, 70 N at d = 150 mm | 70 N moving | 10.5 Nm | — | fits |
| 100 N at d = 200 mm (limit of the push cut) | 100 N | 20 Nm | — | at the limit |
| Stir 30 N in a front-row pot, d = 390 mm | 30 N | 11.7 Nm | — | fits |
| Carry a GN 1/3 pot with 3 L (4.5 kg) at d = 190, pour | 44 N | 8.4 Nm | 3.1 Nm | fits |
| Carry 7 kg (full braiser) at d = 165 | 69 N | 11.3 Nm | — | fits, slow; slid instead |
| Pan pair for flipping, 3.8 kg at d = 200, roll 180° | 37 N | 7.5 Nm | < 1 Nm | fits |
| Full 9 L pot, 12 kg | 118 N | 23 Nm | — | **no**: slid on the floor (24 N) |
| Pull-off (force away from the wall) | — | — | — | rated 250 N |
| Push towards the wall | — | — | — | unlimited (skids) |

**Stiffness.** A 60 N cut deflects the puck 1 mm against the head (62 N/mm) plus about 0.3 mm of tilt at
the blade. The head measures this lag (below) and the path is corrected; cutting accuracy is about ±0.5 mm.

**The coupling as a sensor.** Three 3-axis Hall sensors in each head read the puck's field and give its
lag in X and Z (± 0.05 mm) and the rotor's angular lag (± 0.1°). With the known stiffness this is a force
reading of about ± 5 N (plus friction hysteresis) and a torque reading of about ± 0.3 Nm, for nothing. It
is used for: cut and tamp force, stirring torque (thickening end point), collision detection, and above all
to **keep the puck**: if the lag exceeds 5 mm the gantry yields and follows the puck instead of tearing
away. The coupling is thus a series-elastic drive with a stiff position loop around it.

**Eddy currents in the wall** (1.4404, σ = 1.33 MS/m, 1.5 mm; P ≈ σ v² B² /2 × volume under the poles ×
0.5 end factor) [C, rough]:

| Motion | Loss in the wall | Drag |
|---|---|---|
| Puck travel at 0.5 m/s | ~0.3 W | ~0.6 N, negligible; it damps the puck |
| Rotor at 120 rpm (press, pour, flip) | ~1 W | 0.08 Nm |
| Rotor at 375 rpm (whisk wheel, grater) | ~10 W | 0.25 Nm |
| Rotor at 1000 rpm | ~70 W local | **not allowed**: the travelling rotor is limited to 375 rpm |
| Turntable thimble Ø 90 × 50 at 500 rpm (salad spin) | ~15 W | — |
| Speed thimble Ø 40 × 20 × 0.8 at 6000 rpm | ~20–35 W | acceptable for 60 s bursts; the can is cooled by the wet side |

High speed therefore needs the small thimble S; it cannot come through the flat wall.

**Interaction with induction heating.**

* *Hob field on the pucks.* A coil only runs with a pan on it; the stray field 100 mm above a pan rim is of
  the order of tens of µT [U]. It cannot demagnetise SmCo (H_cJ > 1500 kA/m) and heats the puck's steel by
  less than a watt. A puck is never parked over an empty powered coil (pan detection is standard).
* *Puck field on the ware.* The 20-pole ring field decays as e^(−π·d/21 mm): 0.25 % at 40 mm. Ferritic pans
  are kept ≥ 40 mm from the ring (vessels start at Y = 35 mm, the ring sits at Y < 12 mm). Utensils are
  1.4404; only their parking slugs are ferritic.
* *Through the floor.* Induction does not work through a stainless floor: at 25 kHz the skin depth of 1.4404
  is 2.8 mm, a 1 mm floor sheet would absorb a large share of the power and glow. The four coils therefore
  sit under a glass-ceramic plate bonded flush into the floor with a silicone joint (ordinary hob practice,
  a static seal; brittle material, see request A-5).
* *Magnets and heat.* Puck magnets are SmCo because the wash reaches 85 °C and a puck above a pan sits in
  steam and radiant heat; NdFeB of the normal grade is limited to 80 °C. The head magnets are 0.8 mm behind
  a wall that reaches 85 °C, hence grade SH. T and S magnets are under the floor, 150 mm from the nearest coil.
* *Magnet turntable under a hot pan* was rejected; there is no rotating pan. Stirring is done differently (2.6).

**Decoupling and recovery.**

1. It cannot happen by loss of power: the magnets are permanent, the retract drive is a self-locking screw,
   the Z axes have brakes.
2. It is prevented by the lag limit (yield at 5 mm, stop and back off at 7 mm; breakaway is at about 8 mm).
3. If it happens (an impact, a jammed utensil, grit under a skid while at full torque), the puck drops with
   its utensil, at most 600 mm. It is clean ware, so the food is not contaminated; the food is discarded
   only if the camera sees damage or loose parts. The danger is the glass-ceramic plate: 1.1 kg from 400 mm
   is 4.3 J, above what hob glass is tested for [U]. The spider therefore has a TPE-free, one-piece
   stainless bumper ring, and the puck's working height over the glass is limited to 250 mm where the task
   allows. This remains risk 8.
4. Recovery: the other puck picks the fallen one up by its bail with the carrier fork and holds it to the
   wall; the head approaches and the ring snaps in (20 poles, self-centring; the spider magnets set the
   orientation). A third puck is parked as a spare. If that fails: the human opens the door and puts the
   puck back (one minute), and the tub runs a wash (HYG-007).

### 2.2 Force and torque budget: which operations fit, which need a complement

Three rules replace the missing force:

* **R-torque: make force from torque inside the ware.** The rotor turns a screw in a closed cassette; the
  press force stays inside the cassette frame and never reaches the puck or the wall. Rd 28 × 6 round-thread
  screw, stainless in a PEEK nut, ball tip on a loose piston: T = F × (13 mm × tan(4.2° + 11.7°) + 0.2 × 3 mm)
  = F × 4.3 mm, so 12 Nm gives **2.8 kN**, rated 2.5 kN, at 15 mm/s (150 rpm, 190 W) [C]. The reaction
  torque is taken by a 250 mm arm resting on the floor (48 N).
* **R-lean: lean on the wall or stand on the floor.** Utensils and cassettes may have feet that touch a wall
  or the floor. Compression is unlimited; the puck then only positions. Used for kneading (roller frame
  leans on the drive wall), the lever knife (fulcrum in the board bracket), all cassettes.
* **R-can: canned radial couplings where torque must be high or speed must be high.** A thimble is a
  deep-drawn cup welded into the floor, convex towards the tub, with the driving rotor inside it in the dry
  and the driven bell outside it in the wet. No axial force, torque grows with length. T: Ø 90 × 50 mm, 12
  poles, about 25–30 Nm [E, by comparison with catalogue couplings of this size, U]. S: Ø 40 × 20 mm,
  1.5 Nm, 6000 rpm.

| Operation | Demand [S: research/04 unless marked] | Path in K8 | Fits? |
|---|---|---|---|
| Slice, chop potato, onion, cucumber, leek, mushrooms | 12–71 N per cut | push cut, blade along Y, puck moves in Z | yes, direct |
| Cut carrot bundles, celeriac, cabbage quarters | 100–250 N | lever knife, 2.5 : 1, fulcrum on the board bracket | yes, R-lean |
| Halve a whole cabbage, pumpkin | 200–500 N | lever knife at its limit; several bites | marginal |
| Dice through a grid | 0.25–2 kN | press cassette PZ | yes, R-torque |
| Rice or mash potato | 0.3–1 kN | PZ with 3 mm plate | yes, R-torque |
| Form patties | 80–240 N | PZ, Ø 75 orifice, wire cut-off | yes, R-torque |
| Spätzle, gnocchi, croquette blanks | < 1 kN | PZ with plate or nozzle | yes |
| Knead 1 kg / 1.6 kg dough | 7–10 / 14–20 Nm | bowl on T (25 Nm), roller frame leaning on the wall | yes, R-can + R-lean |
| Mix 1.2 kg mince mass | ~5–8 Nm | as kneading | yes |
| Stir stew, risotto | 5–10 Nm on a round stirrer = 20–40 N on a paddle | paddle swept in X, 30 N | yes, direct |
| Whip, whisk | 1–2 Nm | whisk wheel on the rotor, 375 rpm, bowl turning on T | yes (medium) |
| Chop fine, purée, emulsify | 0.5–1.5 Nm at 3000–6000 rpm | jug on S | yes, R-can |
| Roll out soft yeast dough | 20–60 N per 200 mm | pin on the rotor, ≤ 100 N | yes |
| Roll out stiff shortcrust to 3 mm | > 150 N | pin at 100 N, many passes, dough kept at 18 °C | weak |
| Flatten a cutlet (POU, priority S) | 1–2 kN static or blows | PZ with a flat platen only for ≤ Ø 100; otherwise bought thin | no (bought, MEAL-012) |
| Juice citrus | 50–100 N, 2 Nm | reamer on rotor 1, half pressed on by puck 2 | yes |
| Grate cheese, carrot | 20–50 N | drum grater on the rotor, pusher on puck 2 | yes |
| Peel on the spike | 3–5 N | floating blade | yes |
| Flip, pour, ladle, baste, drain basket | < 50 N, < 6 Nm | rotor roll | yes, the natural strength |
| Lift and tilt > 6 kg | > 60 N, > 12 Nm | not done: slide on the floor, ladle, lift-out basket | avoided |
| Open a can, jar | 0.3–6 Nm, 30–100 N | outside (opening module); the puck only pours and scrapes | outside |

**Answer to catalogue question 6.** A ball port or sealed spindle is not needed for any of the twelve
benchmarks. The fallback, if the screw cassette fails on wear or hygiene (risk 4), is a *hydroformed bellows
ram* in the ceiling above column A (2 kN, 100 mm stroke): still no dynamic seal, but wide convolutions to
wash and about 500 € [U]. It is not part of the baseline.

### 2.3 Kinematics and actuators

| # | Actuator | Type | Force / torque | Travel | Where |
|---|---|---|---|---|---|
| 1, 2 | Bridge X1, X2 (two vertical bridges on common rails; they cannot pass each other) | closed-loop stepper NEMA 23, HTD 5M-15 belt | 400 N, 0.5 m/s | 1000 mm, shared | door cassette |
| 3, 4 | Carriage Z1, Z2 | stepper, ball screw 16 × 10, brake | 600 N, 0.3 m/s | 590 mm | door cassette |
| 5, 6 | Ring spin 1, 2 | 200 W BLDC servo, 8 : 1 belt + planetary, ring on a thin-section bearing | 5 Nm continuous, 12 Nm for 60 s, 0–375 rpm | continuous | head |
| 7, 8 | Head retract 1, 2 (gap modulation) | geared DC motor + self-locking screw | 800 N | 16 mm: work / travel / release | head |
| 9 | Turntable T | stepper NEMA 34 + 10 : 1 planetary, inner magnet rotor in the thimble | 25 Nm, 0–500 rpm | continuous | under the floor |
| 10 | Speed spindle S | 600 W BLDC, direct | 1.5 Nm, 0–6000 rpm | continuous | under the floor |
| 11 | Ceiling port shutter | sliding plate on a gasket, geared motor outside | — | 170 mm | ceiling, dry side |
| 12 | Hand-over hatch (left) | guillotine shutter, outside | — | 260 mm | left wall |
| 13 | Oven hatch (right), also the oven door | insulated guillotine shutter, outside | — | 310 mm | right wall |
| 14 | Door lock (service) | solenoid bolt with safety switch | — | — | door |
| 15, 16 | Box tilter and vibrator at the dock (common front end of all candidates) | geared motor, vibrator | — | 0–180° | dock, dry |

**14 motion actuators in the cell, 16 with the dock.** None is in the wet zone; all are IP20 parts. Not
counted: circulation pump, jet pump, drain pump, two dosing pumps, exhaust fan, 12 solenoid valves, 4
induction generators, tank heater and boiler.

The head floats ± 5 mm normal to the wall on a flexure and rides on the dry face of the door skin on three
ball transfer units placed opposite the puck's skids, so the skin is only squeezed, never bent, and the gap
is set by the skin itself, not by the gantry.

Sensors: 6 Hall sensors; 2 ceiling cameras behind heated windows (top-down over column A and over the hob)
with white and UV-A light; turbidity, conductivity and temperature in the sump; hob temperature sensors;
core-temperature probe as a utensil (wireless probe, bought [U]); dock load cells 10 kg ± 1 g and 300 g ±
0.05 g (loss in weight, dry side); three load cells under the glass-ceramic plate (optional, COK-014).

### 2.4 Wall penetrations and seals

There is **no dynamic seal**. Static openings and joints, all listed again in §6:

| Opening / joint | Seal | Remark |
|---|---|---|
| Door (1100 × 700) | one-piece EPDM profile gasket, as on a dishwasher; sill above the sump level | large perimeter, 3.6 m |
| Drive-wall skin to door frame | welded, with a pressed expansion bead all round | lets the skin grow 1 mm at 85 °C without buckling; bead is convex and drains |
| Ceiling port Ø 160 | shutter plate on a face gasket, closed except when dosing | powder and steam barrier |
| Hand-over hatch 300 × 250 | guillotine shutter, face gasket | transport tray enters 150 mm |
| Oven hatch 440 × 300 | insulated shutter with oven-grade gasket | sill strip between tub floor and oven |
| Glass-ceramic hob plate 700 × 440 | silicone joint, flush | standard; plate may rest on 3 load cells |
| T and S thimbles | deep-drawn, welded in, ground | no seal at all |
| 2 camera windows, 2 lamps | bonded glass | — |
| 2 static spray balls, 12 jet nozzles, drip bar, 6 water outlets, exhaust duct with baffle | welded or threaded from outside with gasket | no moving part inside |
| Sump outlet with lift-out strainer | — | strainer is ware |

### 2.5 The puck

```
 section (wall on the left)                    face seen from the wall
 wall 1.5                                          skid o           o skid     spider: 4 arms, 4 skids Ø20,
  |  1.2 wet gap                                        \   ___   /            4 magnets 15x15 in the feet,
  | |== rotor disc Ø160, magnets, 12 thick ==|           \ /   \ /             bail handle on top
  | |        hub Ø40, thrust washer r = 12   |            | ring |  ring of 20 magnets R68 (in the rotor)
  | |__ spigot Ø25 x 30 with 3-lug bayonet __|==> utensil  / \___/ \
  | spider arm behind the rotor, skids reach the wall    /         \
  |                                                 skid o           o skid
```

* Rotor: welded 1.4404 can around the 1.4016 ring and the magnets, no closed air volume (potted), Ra ≤ 0.8,
  0.8 kg. Spigot with a three-lug bayonet and a face taper.
* Spider: laser-cut and welded 1.4404, 0.3 kg. It carries the clamp force of the rotor through one PEEK
  thrust washer at r = 12 mm (friction torque 0.15 × 510 N × 12 mm = 0.9 Nm, 8 % of rated torque) and a
  loose PEEK radial bush. Rotor and spider are held together only by the magnet force; off the wall they
  hang apart by 5 mm, so the wash reaches between them.
* The spider gives a second member that does not turn: a tool with one jaw on the spider and one on the
  rotor is a pincer (tongs, shears, egg cracker) worked by up to 3 Nm.
* Three pucks (two working, one spare). One head can release its puck on the parking strip and take another.

### 2.6 What follows from having no depth axis

The puck moves in X and Z and rolls about Y. It cannot move towards the rear wall. The concept lives with
that through five devices:

1. **Blade along Y.** The main knife points away from the wall; slices are set by X steps, cuts by Z. Rolling
   the rotor tilts the blade (V-cuts for cores, horizontal cuts).
2. **Turntable T** under the board for the second cut direction and for round work (peeling spike, bowl).
3. **Rectangular cooking ware and a full-width scraper.** In a round pot a tool that can only move in X
   leaves two unscraped segments. In a GN vessel a scraper as wide as the vessel, swept in X, scrapes 100 %
   of the bottom and both end walls; a roll of the rotor folds the heap over (the cook's push-and-turn). Front
   and rear walls are wiped by the scraper's ends.
4. **The Y-slide** (utensil U20): the rotor turns a screw, the spider holds a guide rod, a carriage travels
   150 mm in Y at up to 15 mm/s and several hundred newtons. It trades the roll axis for a depth axis when
   one is needed: draw-cut slicing (carving, bread, tomato), feeding food to a blade parallel to the wall,
   setting a Rouladen pin, spreading along Y.
5. **Sliding vessels on the floor** in X (24 N for a 12 kg pot) instead of lifting them; the hob, the oven
   sill and the hatch sill are flush.

### 2.7 Tools, vessels, fixtures

All food-contact parts are 1.4404 (blades 1.4116), one piece or fully welded, except where a polymer is
named. "B" = bought standard part, "M" = bought and modified (spigot or handle welded on), "C" = custom.

**Utensils** (each has the bayonet socket and a ferritic parking foot with three dome contacts):

| # | Utensil | Dimensions | Used for | B/M/C |
|---|---|---|---|---|
| U1 | Chop knife, blade along Y | blade 200 × 45 × 2 | slice, chop, score, portion | M |
| U2 | Lever knife with tip hook | blade 250 | hard vegetables, cabbage | M |
| U3 | Floating peeler (blade on a one-piece flexure) | blade 50 | potato, carrot, apple, cucumber | M |
| U4 | Comb / fakir fork | 12 tines, pitch 10 | hold for cutting, carve fence, impale | C |
| U5 | Tongs (pincer: spider jaw + rotor jaw) | opening 0–110 | pieces, slices, sheets, eggs, cans | C |
| U6 | Turner, low | 240 × 130, shaft at blade level | flip in the 20 mm griddle, lift | C |
| U7 | Scraper paddle 150 (GN 1/4) and U8 paddle 250 (GN 1/2), silicone lip moulded on | — | stir, scrape, fold, empty vessels | C (4 pieces) |
| U9 | Carry cups 0.15 L, 0.5 L, 2 L with spigot | — | carry doses, roll-dump, ladle, baste | M |
| U10 | Whisk wheel Ø 150 and Ø 50 | — | whisk, whip | C |
| U11 | Rolling pin Ø 60 × 280 (rigid on the rotor, driven at surface speed; no bearing) | — | roll dough, press slabs | C |
| U12 | Vessel fork for GN handles; pan-pair clamp | — | carry, pour, invert | C |
| U13 | Squeegee 300, silicone | — | floor, walls, board; pushes scraps to the chip box | C |
| U14 | Hook rod 450 | — | push and pull vessels, lids, oven trays | C |
| U15 | Wire bow | span 120 | cut off extrudate, butter, soft cheese | C |
| U16 | Drum grater Ø 80 with pusher | — | cheese, carrot, zest (fine drum) | M |
| U17 | Kneading frame: roller Ø 60 + scraper, two wall feet | — | knead, cream, mix mince | C |
| U18 | Reamer cone | Ø 70 | citrus | B/M |
| U19 | Core-temperature probe holder | — | COK-013 | M |
| U20 | Y-slide, 150 mm, with draw knife, pusher and pin setter heads | — | §2.6 | C |

**Cassettes and fixtures:**

| Part | Description | B/M/C |
|---|---|---|
| PZ press cylinder | tube Ø 100 × 160, axis along Y, top loading window 60 × 120, rear cap with PEEK Rd nut (bayonet), screw Rd 28 × 6 × 200 with ball tip, loose PE piston, floor arm. Dies on a bayonet: grid 10, grid 15 with comb pusher, ricer plate 3 mm, Spätzle plate, orifice Ø 75, nozzle Ø 22 | C |
| Peeling spike | 3 tines 25 mm on a T carrier | C |
| T carrier bell | ring with 12 encapsulated SmCo magnets, runs on the thimble on a PEEK bush, dogs for bowl, board plate, spike, basket | C |
| S rotors | S-blade rotor Ø 120 and whisk rotor, each a welded ring with magnets, PEEK bush, sit over the dome in the jug | C |
| Board plates | 2 × PE-HD 325 × 265 × 15, green (RTE) and red (raw), on a steel carrier with fulcrum eye and comb rail | B/C |
| Silicone mat with steel hem bars | 300 × 250 | M |
| Rouladen cradle insert, egg-cup rack, breading trays 3 × GN 1/4-20, lasagne sheet dispenser, drain rack | — | C / B |
| Egg cracker cassette (blade-and-spread, SM-165, worked as a pincer) | fallback to the common egg module | C |
| Chip box GN 1/6 (scraps), sump strainer basket | — | B / C |

**Vessels:**

| Vessel | Size | Use | B/M/C |
|---|---|---|---|
| GN 1/2-150 induction (multi-layer GN, Rieber "thermoplates" type [U]) with lift-out perforated basket | 9.5 L | pasta, potatoes for 6, stock | B + M |
| GN 1/2-100 with lid | 6.5 L | braiser, stew, oven dish | B |
| GN 1/2-65 × 2 | 4 L | sauté, sauce, Bratkartoffeln, 700 cm² frying surface each | B |
| GN 1/2-20 × 2 (griddle) | — | steak, schnitzel, Frikadellen, flip pair | B |
| Round crêpe pan 28 cm × 2 with flat tangs | — | pancakes, fried eggs | M |
| GN 1/4-150 × 2, GN 1/4-65 × 1, GN 1/6-100 × 1, lids | 4 L, 1.8 L, 1.4 L | rice, vegetables, sauce, one-person quantities | B |
| Bowl Ø 280 × 180 (10 L), bowl Ø 180 (1.5 L), beaker 0.3 L | — | knead, mix, salad; PRP-038 small end | B + M |
| Salad basket Ø 260 | — | wash, spin | B |
| Jug 2.5 L with re-entrant bottom dome; chopper cup 0.6 L with dome and lid | — | purée, chop, emulsify, whip small | C |
| Baking tray 400 × 300 × 2, two-level tray rack, springform 26, loaf tin 300, gratin dish GN 1/2-65 | — | oven | B |

Count: 20 utensil types (24 pieces), about 12 cassette and fixture types, about 30 vessels and lids. About 45
custom part types (§7).

---

## 3. Ingredient intake and dosing

Boxes arrive from the transport system at the **dosing dock** above the ceiling port (column A). The dock
tilts and vibrates the box; two load cells under the dock weigh the *loss* (R9), in the dry. This is the
common front end of all candidates; K8 adds nothing to it and needs no load cell through a wet wall.
Everything falls through the port into a vessel on T or into a carry cup held by puck 1. Seasoning is never
dosed over the hob (R8): the cup is carried.

| Form | Path | Accuracy, remark |
|---|---|---|
| Whole produce | box tilted slowly with vibration; pieces fall one at a time through the port into the basket on T; counted by the port camera and the loss in weight | ± 1 piece; single pieces are then taken by tongs under the ceiling camera |
| Leafy | whole box emptied into the basket on T (G9 of the catalogue is not solved); head lettuce as a piece | mass by loss in weight, no fine dosing |
| Granular | tilt with a gate lid, fine feed by vibration | ± 2 % [S] |
| Powder | as granular with a mesh lid; the tub must be dry at the port and the exhaust off; shutter closes at once | ± 2.5 g; seasoning by the 300 g cell ± 0.2 g into the 0.15 L cup |
| Liquid | water from six fixed outlets in the ceiling, one above each station, flow meter ± 5 mL. Oil, vinegar, milk, stock: poured from their own box or bottle at the dock into a carry cup | ± 5 % |
| Viscous paste | piston box or squeeze pouch worked at the dock (request A-2), strand cut by the closing shutter; or, as the plain-box fallback, the opened tub or jar comes in through the hatch and puck 1 spoons it with the 0.15 L cup while puck 2 scrapes the cup | ± 2.5 g / ± 5 g with the spoon |
| Solid fat | bought in 10 g portions or cut at first opening (X6); counted pieces through the port; or a block on the board, cut with the wire bow | exact count |
| Raw meat | the opened pack or a tray comes through the hatch; tongs or turner move the piece to the red board; mince is tipped into the bowl | loss in weight at the hatch tray (transport scale) |
| Egg | common egg module at the dock (SM-164): the contents drop through the port into the 0.3 L beaker on T, the ceiling camera checks for shell, then the beaker is poured. Fallback in the tub: cracker cassette on the pincer | 12 eggs in 3 min with the module [E]; 20 s per egg with the cassette |
| Frozen | IQF goods as granular; blocks straight into the pot through the port if the pot is carried under it, else by tongs | — |
| Stowed sealed packs | opened just in time by the opening module (DEC-3). Cartons and bottles are poured at the dock. **Cans, jars, tubs** come in through the hatch already open; puck 1 grips them with the tongs and pours by rolling, puck 2 scrapes with a narrow paddle; the empty pack leaves through the hatch. Vacuum packs: slit outside, contents slide onto the board | residue ≤ 5 % for chunky cans with scraping [E] |

The roll axis makes pouring and scraping of cans and jars a natural operation here; it is one of the few
intake tasks where K8 is better placed than a vertical-rod machine.

---

## 4. Operation table

Confidence: H = known practice at this scale and within the calculated limits; M = sound, needs a bench
test; L = speculative. "Untested" is everything; the column names what is most in doubt.

| Operation (UO / code) | Mechanism and sequence | Time | Conf. | Most in doubt |
|---|---|---|---|---|
| Wash produce (WSH, WLF), spin dry | basket on T under the water outlet, T reverses at 60 rpm, then 500 rpm (36 g) | 60 s + 20 s | H | leaf damage |
| Peel potato, carrot, apple (PLP, PLS) | tongs press the piece on the spike on T; T turns 120 rpm; puck 2 runs the floating peeler pole to pole; top cap cut off, piece pulled, bottom cap stays as waste | 25 s per potato | M | loading on the spike; eyes remain; 1.5 kg takes 5–6 min, PRP-023 met only just |
| Peel onion (PLA) | bought peeled (SM-242). Slot kept: slit on the spike, tangential jet from the jet gate | — | L | as for all candidates |
| Peel hard items (PLH) | spike + peeler with 2 passes; celeriac and pumpkin: slab cuts with the lever knife, loss 30 % | 60 s | M–L | — |
| Core, trim (COR, TRE) | apple: punch tube pressed by the puck on the spike axis (80 N); pepper: cap cut, seeds flushed; cabbage: V-cuts by tilting the blade; beans bought trimmed | 15–30 s | M | pepper |
| Slice (SLI), sticks (JUL), wedge (WED) | U1, comb on puck 2, X steps 1–20 mm, 2–3 cuts/s | 1 kg in 3 min | H | round items rolling: comb |
| Dice (DIC) | bulk: PZ with grid 10 or 15, flush cut by the wire bow every 10 or 15 mm. Small counts: cook's method on the board, T turns it 90° | 1 kg in 3 min; 50 s per onion | H (grid) / M (knife) | grid needs pieces ≤ Ø 95 |
| Mince, chop herbs (MIN, CHH) | chopper cup on S, 3 pulses; or U1 chopping on the PE board with T creeping | 10 s | H | bruising of soft herbs |
| Grate (GRC, GRF) | drum on rotor 1 at 300 rpm, pusher on puck 2 | 100 g cheese in 30 s | M | end piece |
| Juice (JUI) | reamer on rotor 1, half held by tongs on puck 2 | 20 s per half | M | — |
| Slice raw meat, carve roast (SLM, CAR) | Y-slide draw knife on puck 1 (stroke 60 mm, 2 Hz) descending at 10 mm/s, comb fence on puck 2, X steps | 8 s per slice | M | draw-cut quality; bone-in: no |
| Crack egg (CRK), separate (SEP) | dock module; separation by a yolk cup under the port | 15 s | M | shared mechanism |
| Mix, toss (MXD, MXW, TOS) | bowl on T, paddle or kneading frame held still; salad: bowl turning at 20 rpm against a paddle, or two forks | 30–60 s | H | — |
| Whisk, whip (WHK, WHP), cream (CRM) | whisk wheel 375 rpm in the bowl turning on T; 1 egg white: whisk rotor in the chopper cup on S | 3–5 min | M | volume with a horizontal wheel |
| Emulsify (EMU) | jug on S, oil trickled from a carry cup | 60 s | M–H | — |
| Knead (KND), mince mass (KNM), rub in (RUB) | bowl on T 60–100 rpm, frame U17 leaning on the drive wall, roller driven by the rotor | 8 min for 1 kg flour | M | reaction path; 1.6 kg at 20 Nm |
| Fold (FLD) | paddle, bowl indexing on T | 40 s | M | — |
| Mash (MSH), extrude (EXT) | PZ with ricer or Spätzle plate, over the pot | 1.5 kg potato in 4 strokes, 2 min | H | loading hot potatoes through the window |
| Purée (PUR) | jug on S, 3000–6000 rpm, 1.5 L per batch; hot soup in two batches | 60 s per batch | M | hot transfer of 3 L in a 2.5 L jug; seal-free lid |
| Drain (DRN) | lift-out basket, 20 s over the pot, roll-dump | 40 s | H | — |
| Form patties, dumplings (FRB, FRK), small shapes (FRM) | PZ, orifice Ø 75 / nozzle Ø 22, stroke by weight, wire cut; pieces fall 40 mm onto the griddle or a tray | 12 patties in 3 min | M–H | disc shape; sticking at the orifice |
| Bread (BRD) | three GN 1/4-20 trays in a row; tongs dip and turn, turner presses the crumbs (40 N) | 40 s per cutlet | M | coverage at the tong marks |
| Roll and secure (RLT), wrap (WRP) | slice on the mat along X; paddle spreads; tongs place the filling; puck 2 lifts the hem bar and carries it over in an X–Z arc (the roll axis is Y, which is the natural plane); roll is tipped seam-down into the cradle; optional pin by the Y-slide | 90 s per roll | L–M | tightness; shared untested cradle |
| Layer (LAY), spread (SPR), top (TOP) | cup pours, paddle spreads in X, sheets from the dispenser by tongs; toppings sprinkled by a vibrated roll-dump of the cup while moving in X | 20 s per layer | M | even sprinkling across Y |
| Stuff (STU) | rigid cavities: carry cup dumps, tamp with the beaker base; cannelloni: PZ nozzle along Y into tubes lying along Y | 15 s per piece | M | flat pockets: no |
| Roll dough (ROL), shape (SHD), cut (CUD) | pin on the rotor, X passes, on the baking mat in the tray; loaf formed by the tin; cut with U1 | 3 min per tray | M | sticking; stiff dough |
| Grease, line (LIN), glaze (GLZ) | melted fat poured in, tin rolled by the rotor; flour dumped and tipped out; glaze with a silicone paddle | 40 s | M | corners |
| Score (SCO) | U1 with force and depth from the lag | 10 s | H | — |
| Stir on heat (STC, SAU), deglaze, reduce, thicken | paddle in the GN vessel, X sweep + roll fold; one puck serves up to four pots in turn, or one pot continuously | — | M | scorching in corners of rectangular ware |
| Sear, pan-fry, flip (SER, PFR, FLP) | pieces: low turner in the 20 mm griddle, roll 180° about the blade edge. Thin or fragile items: pan-pair inversion by the rotor (SM-127) | 8 s per piece; 15 s per pair | H pieces / M pair | pancake with butter |
| Baste (BST), sauce | 0.15 L cup as a spoon, roll | 10 s | H | — |
| Lids on and off, add to a hot vessel (COK-010) | hook rod, carry cup | 8 s | H | — |
| Oven in and out (BKE, RST, BRS) | vessel slid in X through the oven hatch with the hook rod | 20 s | M | sill, two-level rack |
| Unmould (UNM) | tin and plate clamped as a pair, rolled 180°, tin lifted | 30 s | M | release |
| Proof (PRF) | covered bowl in the oven at 30 °C, or in the closed tub with the tank water warming the floor | — | M | — |
| Assemble (ASM) | stacking with tongs and turner under the camera | 10 s per item | M (stacks) / L (folded items) | tacos, wraps |
| Hand over for plating | vessel carried or slid to the hatch; plating is the serving module's | 15 s | H | — |

Solved / avoided / failed against catalogue §2.4: G1 avoided by purchase; G2 (strip, pluck) failed, bought
frozen; G3 stacks solved, folded items failed; G4 rigid cavities solved, flat pockets failed; G5 failed;
G6 partly (flush); G7 failed; G8 avoided (bought tied); G9 not solved; G10 avoided by purchase.

---

## 5. Benchmark walk-throughs

Conventions: P1 = puck 1 (left), P2 = puck 2 (right). A *move* is one pick-and-place, tool change (6 s),
vessel transfer or dock action. Times are elapsed from order, for the stated number of persons, and include
waiting for heat. "Soiled" lists what goes through the wash.

### B1 Rinderrouladen, Rotkohl, Salzkartoffeln (4) — **yes**, low–medium confidence on rolling

| t (min) | Step | Vessel / tool |
|---|---|---|
| 0 | Braiser to hob 1, preheat. Red cabbage (bought as a half head) onto the green board; P1 lever knife: quarter, V-cut the core (blade tilted ± 30°) | board, U2 |
| 3 | P1 chop knife shreds 800 g in 3 mm steps against the comb on P2 (270 cuts, 2 min); apple on the spike: peel, punch the core, dice by knife; squeegee pushes all into GN 1/2-65 | U1, U4, U3, U13 |
| 8 | Rotkohl pot on hob 2: fat, onion (bought peeled, chopper cup), cabbage, apple, vinegar, wine, sugar, spices from carry cups; lid; simmer 75 min; P2 stirs every 10 min | GN 1/2-65, U8, cups |
| 10 | Red board and mat on T. Meat slices arrive through the hatch; tongs lay one along X. Mustard by spoon and paddle; bacon, onion strips, pickle by tongs | mat, U5, U7 |
| 12–20 | Roll (P2 lifts the hem bar), tip seam-down into the cradle; 8 rolls × 60–90 s | cradle insert |
| 21 | Rolls seared: cradle stays out; rolls are tipped seam-down onto the hot braiser floor in two rows (8 fit 325 × 265), 3 min, turned a quarter three times with the low turner | GN 1/2-100, U6 |
| 33 | Deglaze with wine and stock from cups, tomato paste; lid; braiser slid into the oven at 160 °C for 100 min | U14 |
| 35 | **Quick rinse of column A** (red board, mat, tongs, knife through the jet gate, 85 °C, 3 min). Meat work is finished before the potatoes start | jet gate |
| 100 | Potatoes (1 kg, 8 pieces): spike peel 25 s each; halve; into GN 1/4-150 on hob 3 with water and salt; boil 22 min | spike, U3, U1 |
| 128 | Potatoes drained: the pot (3 kg) is carried and tipped against its lid held ajar by P2 over the sump gutter; back on hob 3, off | U12 |
| 133 | Braiser pulled out; rolls lifted to a GN 1/2-65 with the turner; sauce thickened on hob 1 with flour slurry, paddle | U6, U8 |
| 140 | Three vessels to the hatch | — |

Elapsed **140 min** (T_ref 150; limit 183). About **95 moves**. Soiled: braiser, lid, 2 × GN 1/2-65, GN
1/4-150, 2 boards, mat, cradle, bowl, chopper cup, spike, 9 utensils, 5 cups. Peak: 2 hobs + oven.

### B2 Wiener Schnitzel, Bratkartoffeln, Gurkensalat (4) — **yes**, medium

Potatoes boiled skin-on first (GN 1/4-150, 20 min) while the cucumber is peeled on the spike (long item:
tail held by the tongs of P1), sliced 2 mm (150 cuts, 70 s), dressed in the 1.5 L bowl (sour cream, dill,
vinegar from cups), tossed with a paddle and parked cold at the hatch for the transport to chill. Potatoes are peeled raw
on the spike before boiling (8 × 25 s; slipping the skin after cooking is not solved here), then sliced
5 mm and fried in GN 1/2-65 on hob 2 with onion, turned by paddle sweep and roll every 2 min, 15 min.
Cutlets (bought thin): three breading trays in a row on the floor of column B; P1 tongs flour–egg–crumb,
40 s each. The front positions take only GN 1/4 and hob 2 is occupied, so the cutlets are fried two at a
time in the GN 1/2 griddle on hob 1: two batches of 3 min per side, the first held warm in the oven at
70 °C. Lemon wedges by U1.

Elapsed **48 min** (T_ref 30 for the schnitzel alone, 45 with the potatoes; limit about 62). About **80
moves**. Soiled: 3 trays, griddle, GN 1/2-65, GN 1/4-150, 2 bowls, 2 boards, spike, 8 utensils. Class R
(egg, pork) is last in column A; the salad is finished before the meat comes in.

### B3 Frikadellen, Kartoffelpüree, Erbsen-Möhren (4) — **yes**, medium–high

0 min: potatoes (1 kg, skin-on, halved by U1) into GN 1/4-150 on hob 3, boil 22 min. 2 min: carrots peeled
on the spike (3 × 30 s), diced through PZ grid 10 (1 stroke), with frozen peas into GN 1/4-65 on hob 4 with
butter and 100 mL water, lid. 8 min: bowl on T: soaked roll (squeezed by the beaker base against the bowl),
mince from the hatch, egg, chopped onion (cup on S), mustard, salt, parsley; kneading frame, 90 s at 60 rpm.
11 min: mass scraped into PZ (two loads of 350 g), orifice Ø 75: 8 discs of 85 g cut by the wire bow onto
two trays, then slid into the hot griddle on hob 1 by the turner; 6 min per side, flipped with the low
turner; core probe 72 °C. 24 min: potatoes: basket lifted, 20 s drain, tipped into PZ with the ricer plate
(PZ rinsed at the jet gate after the mince, 85 °C, 60 s), riced into GN 1/2-65 on hob 2 with hot milk and
butter, folded with the paddle. 32 min: hand over.

Elapsed **34 min** (limit 50). About **85 moves**. Soiled: bowl, PZ with 3 dies and piston, griddle,
3 GN vessels, basket, 2 trays, board, spike, chopper cup, 9 utensils. Weak point: the PZ is used for raw
mince and then for the mash; the intermediate rinse must disinfect (A₀ ≥ 60), or a second PZ tube is kept
(chosen: a second tube and piston, the screw and cap are outside the food).

### B4 Spaghetti Bolognese with grated cheese (4) — **yes**, high

Onion, carrot, celeriac (bought peeled cubes or spike-peeled) diced through PZ grid 10; garlic in the
chopper cup. GN 1/2-100 on hob 1: oil, mince seared (paddle breaks it up), vegetables, tomato paste, wine,
canned tomatoes (can poured and scraped by the pincer), stock, herbs; simmer 45 min, P2 sweeps every 5 min.
At 35 min: 4 L water in GN 1/2-150 with basket on hob 2 (3.5 kW: 7 min to the boil from 60 °C tank water,
11 min from cold); spaghetti (250 mm, fit the 325 side) tipped from the dock into a 2 L cup and dropped in;
10 min. Basket lifted (1.8 kg), 20 s, tipped into the sauce vessel or a serving GN. Cheese: drum grater,
40 g, into a cup. Elapsed **68 min** (limit 96). About **55 moves**. Soiled: 2 large GN, basket, PZ, cup,
board, 6 utensils, 4 cups.

### B5 Pizza, yeast dough from flour, 2 trays — **yes**, medium (tray pizza; round ones not offered)

Dry tub. Flour 500 g, salt through the port into the bowl on T; water 30 °C from the outlet, yeast
(crumbled in water in a cup), oil; kneading frame 8 min at 80 rpm (about 8 Nm). Bowl covered with its lid,
slid into the oven at 30 °C for 45 min. Sauce: canned tomatoes, salt, oregano, 10 s in the jug on S.
Mozzarella sliced with the wire bow. Dough tipped onto the board, halved by U1; each half on a baking mat in
a tray, rolled by the pin in X passes (100 N, 6–8 passes) and pushed into the corners by the pin's end;
sauce poured along X and spread by the paddle; cheese and salami placed by tongs (16 pieces per tray, 2 min).
Both trays in the two-level rack, slid into the oven at 250 °C, 12 min (rack turned end for end at half time
is not possible; combi fan evens it out). Elapsed **95 min** (T_ref 90; limit 114). About **70 moves**.
Soiled: bowl, lid, frame, pin, jug, 2 trays and mats, rack, board, 6 utensils.

### B6 Gemüseeintopf from whole vegetables (6) — **yes**, medium–high

1.2 kg potatoes and 400 g carrots peeled on the spike (13 pieces, 6 min with P2 peeling while P1 loads);
leek slit and washed in the basket, sliced by U1; celeriac bought as peeled cubes or slab-cut; green beans
bought trimmed or frozen (TRE is not solved). Dice: PZ grid 15, 6 strokes, 3 min. GN 1/2-150 on hob 1:
oil, leek sweated, all vegetables, 2.5 L stock, simmer 25 min, paddle every 5 min; frozen peas at 20 min;
parsley from the chopper cup. Hand-over: the pot weighs 7.5 kg; it is slid to the hatch. Elapsed **44 min**
(limit 50 + 10 for six persons). About **60 moves**. Soiled: pot, PZ, basket, spike, board, cup, 6 utensils.

### B7 Steak, oven fries, mixed salad with vinaigrette (2) — **yes**, high for steak and fries

Fries: 500 g potatoes pushed lengthwise through PZ grid 10: sticks of full potato length, no cut-off
(skin-on, or spike-peeled first). Rinsed and spun in the basket, tossed with 10 mL oil in the bowl, spread on
a tray with the paddle, oven 220 °C hot air 25 min. Salad first in time (RTE before raw): lettuce wedge cut,
washed and spun on T, tomato and cucumber sliced, carrot grated on the drum; vinaigrette in the chopper cup
on S; tossed in the 10 L bowl turning against a paddle just before hand-over. Steak: griddle on hob 1 at
240 °C, 2 steaks laid by tongs, 2.5 min per side with the low turner, butter and thyme added, basted with
the 0.15 L cup (roll axis), probe 56 °C, rested 5 min on a warm GN. Elapsed **38 min** (T_ref 60 with baked
potato; limit 79). About **60 moves**.

### B8 Pfannkuchen, 8 pieces — **adapted** (pan-pair flip), medium–low

Flour, milk, eggs, salt, sugar in the 1.5 L bowl on T, whisk wheel 60 s; rest 20 min. Two crêpe pans on
hobs 1 and 2 (their tangs point to the drive wall). Butter piece into pan A; 100 mL batter from the 0.15 L
cup; P2 tilts the pan by its tang to spread (roll ± 15°, then carry-tilt); 90 s. P2 sets pan B (hot, buttered)
on top, clamps both tangs with the pair clamp, rolls 180°, lifts A off; B goes on hob 2 for 60 s; A is
refilled. Finished pancake slid onto a warm GN by tilting the pan. Two pans alternate: 8 pancakes in 14 min.
Elapsed **38 min** (limit 50). About **75 moves**. Adapted because the flip is an inversion and the
spreading is by tilting; the result should be equivalent. Risk: butter running at the inversion.

### B9 Chicken curry with rice (4) — **yes**, high

Rice 300 g rinsed in the basket, GN 1/4-150 on hob 3 with 600 mL water, lid, absorption 15 min. Onion,
garlic, ginger in the chopper cup; chicken breast (bought as strips, or sliced by the draw knife on the red
board) seared in GN 1/2-65 on hob 1, paddle; paste, spices from the cup, coconut milk (can poured by the
pincer), simmer 15 min. Elapsed **33 min**. About **45 moves**.

### B10 Lasagne, béchamel from scratch — **yes**, medium

Ragù as B4 (45 min, hob 1). Béchamel on hob 3 in GN 1/4-65: butter melted, flour from a cup, P2 sweeps the
paddle continuously (the torque reading shows the roux binding), milk in four doses from a 0.5 L cup, 10 min.
P2 is bound to this pot for 10 min; P1 serves the ragù. Layering in the gratin dish GN 1/2-65 on T: cup of
ragù poured along X, paddle levels; three sheets from the dispenser by tongs (friction feed: a rubber finger
on the pincer pushes the top sheet out of the stack); béchamel; five layers, 4 min; grated cheese from the
drum sprinkled by a vibrated roll-dump. Dish slid into the oven, 190 °C, 40 min, 15 min rest. Portioning is
the serving module's. Elapsed **118 min** (T_ref 120; limit 148). About **85 moves**.

### B11 Rührkuchen in a tin, unmoulded — **yes**, medium

Butter (tempered, in 10 g pieces) and sugar in the bowl on T, kneading frame with the roller driven, 4 min
(creaming by a roller is slower than by a beater; volume about 80 % of a hand mixer's [E]); eggs one by one
through the port; flour and baking powder through a mesh lid; milk; paddle fold 40 s. Tin: 10 g melted
butter, rolled by the rotor through 360° in two planes (one by the rotor, the other by re-gripping the tin
turned on T), flour dumped and tipped out. Bowl tipped over the tin (bowl with 1.2 kg batter = 2.2 kg at
d = 190: fits), scraped with the paddle by P2. Oven 175 °C, 55 min. Cool 15 min; tin and a board plate
clamped as a pair, rolled 180°, tin lifted. Elapsed **95 min**. About **50 moves**. In doubt: creaming
quality; release of the loaf.

### B12 Scrambled eggs from shell eggs, toast, 1 person — **yes**, high

Two eggs from the dock module into the 0.3 L beaker on T, camera check, 20 mL milk, salt; whisk wheel Ø 50,
15 s. GN 1/4-20 griddle on hob 3 (the GN 1/6 is too narrow for the paddle): butter, eggs poured, paddle 150
swept every 5 s, 2 min at 110 °C. Toast: two slices laid on the hot griddle on hob 1, turned once with the low
turner, 90 s per side. Chives: U1 on the board, 10 cuts. Elapsed **9 min** (limit about 17). **22 moves.**
Soiled: beaker, 2 griddles, board, whisk wheel, paddle, turner, knife, cup: a *short wash* (§6), 10 min, 12 L.
The minimum-quantity case works; its cost is that a 6-minute dish occupies a 1.75 m machine and one wash.

**Summary**

| | B1 | B2 | B3 | B4 | B5 | B6 | B7 | B8 | B9 | B10 | B11 | B12 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Result | yes | yes | yes | yes | yes | yes | yes | adapted | yes | yes | yes | yes |
| Confidence | L–M | M | M–H | H | M | M–H | H | M–L | H | M | M | H |
| Elapsed, min | 140 | 48 | 34 | 68 | 95 | 44 | 38 | 38 | 33 | 118 | 95 | 9 |
| Moves | 95 | 80 | 85 | 55 | 70 | 60 | 60 | 75 | 45 | 85 | 50 | 22 |

"Yes" means: every step has a mechanism within the calculated force limits. It does not mean tested. Six
persons: B3 needs three griddle batches or both GN 1/2 positions (12 patties = 2 × 6), B2 three batches;
the 9.5 L pot and the 10 L bowl are sized for six. One person: GN 1/4 and GN 1/6 vessels, the 1.5 L bowl and
the 0.3 L beaker; the paddle 150 needs a vessel at least 162 mm wide, so the smallest stirred quantity is
about 0.15 L in the GN 1/4-20.

---

## 6. Cleaning

### 6.1 Principle and changes to the dishwasher idea

E's Spülzelle is blocked for 50 minutes because it washes like a household dishwasher: low mechanical
action, random distances, long time. K8 has two manipulators inside the wash chamber. It therefore washes
like a **commercial pass-through machine**: each item is carried through a fixed jet plane at 50–100 mm
distance, turned by the rotor so that the jets sweep every face, first with 60 °C detergent solution from an
8 L tank, then with fresh water at 85–90 °C from an 8 L boiler. There is no spray arm and no rack of randomly
loaded ware; the "load pattern" is a programmed path per item type, validated once with riboflavin.

Wash hardware, all static inside the tub: the **jet gate** (12 flat-fan nozzles in the left wall, ceiling
and floor, all aiming into the plane X = 60; 12 L/min at 4 bar), **two static spray balls** in the ceiling
for walls, ceiling, floor and hob (40 L/min recirculated), **a nozzle row** along the top strip for the
parked utensils, the **drip bar**, and the sump with a lift-out strainer.

### 6.2 Programmes

| Programme | When | Steps | Time | Water | Energy |
|---|---|---|---|---|---|
| **Tool rinse** | within 2 min after a utensil is used; between allergen steps | 5 s cold in the jet gate | 5–10 s | 0.5 L | — |
| **Red-to-green rinse** | after class R work if the same meal continues with RTE food | used utensils and the board: 20 s at 60 °C + 25 s at 88 °C in the jet gate (A₀ ≈ 60 at the surface); column A floor flushed | 3 min | 5 L | 0.35 kWh |
| **Short wash** | small meal without frying (B12, a salad, a dough) | ware and pucks only, through the gate; floor flushed | 10 min | 12 L | 0.65 kWh |
| **Full wash** | after every meal with frying, searing or boiling-over; at least daily | see below | 25 min to clean, dry ware; 35 min to a dry tub | 26 L | 1.5 kWh |
| **Intensive** | monthly, after service, after a failed verification | full wash with 5 min soak, 10 min hot recirculation at 82 °C on everything | 50 min | 40 L | 2.5 kWh |

**Full wash, step by step** [E]:

1. *Scrape* (2 min). Leftovers are handed over or scraped by paddle into the chip box; the squeegee pushes
   floor debris to the sump strainer; strainer basket emptied into the chip box; chip box out through the hatch.
2. *Cold pre-rinse* (2 min, 5 L to drain): spray balls and gate; starch and egg are rinsed cold (R11).
3. *Wash* (6 min, 8 L at 60 °C, recirculated, alkaline enzyme detergent 3 g/L): spray balls run; P1 and P2
   carry the vessels through the gate, 20 s each, rolled through 360°; cassette parts and cups one by one;
   the basket, bell and S rotors; the nozzle row washes the parked utensils, each of which is nudged 15 mm
   along the strip by a puck half-way so that its three foot contacts move.
4. *Rinse* (3 min, 11 L fresh at 85–90 °C): each vessel 6 s in the gate (0.6 L), then set down tilted on the
   drain rack over the hob; spray balls 3 L; utensil row 2 L.
5. *Pucks* (1.5 min): P2 hooks its bail on the rack peg of the drain rack in the gate plane; head 2 retracts
   16 mm and leaves; rotor and spider hang apart; gate 20 s wash, 20 s rinse at 88 °C. Then P1 does the same.
   The whole drive wall is now bare and is washed and rinsed by the spray balls.
6. *Dry* (10–20 min): steel ware leaves the rinse at about 75 °C and flashes dry in 3–5 min; exhaust fan
   100 m³/h through a condenser; a puck with the squeegee wipes the drive wall and the floor (the gantry is
   free again after step 5); walls and ceiling dry from the stored heat of 40 kg of steel (0.55 MJ per 30 K,
   enough to evaporate about 200 g of film).

Energy: 8 L × 48 K + 11 L × 75 K = 1.4 kWh heat, plus pumps and fan. Tank and boiler are heated during the
cooking phase by the power manager. The pucks make about 40 wash moves.

### 6.3 Soiling of the whole tub per meal

The honest picture: a frying meal puts grease aerosol and steam on all 3.25 m² of the tub and on every
parked utensil, used or not. K8 does not confine that soil; it washes it. Measures that reduce it: lids on
every pot (put on by the hook rod); a baffle and exhaust above the hob drawing 60–100 m³/h across the hob
towards the rear wall; searing done with the splash lid (a perforated flat lid) on. What remains is that
**every dinner ends with a full wash**, 26 L and 1.5 kWh, and the cell is closed for 25–35 minutes. For two
cooked meals and one small meal a day that is about 65 L and 3.7 kWh per day for the cell, which also
replaces the ware washer for all preparation and cooking ware (compare `research/06`: 35–60 L and 2.5–4 kWh
per day for the ware washer alone). Plates and boxes still need the separate washer.

Because the cell is its own washer, it cannot wash ware for the next course while it prepares it. A
two-course meal is prepared entirely before the wash; dessert ware is part of the resident set. A cake after
a roast on the same evening waits 35 minutes.

### 6.4 Surface inventory (HYG-010)

| Surface | Zone | Area | Soiled by | Cleaned by | Dries by | Shadows and crevices, honestly |
|---|---|---|---|---|---|---|
| Drive wall (door skin) | S | 0.77 m² | splashes, steam, skid tracks | spray balls once the pucks hang off; squeegee | squeegee, heat | skid tracks of polymer transfer film; the expansion bead all round; door gasket lip (3.6 m) |
| Rear wall, side walls, ceiling | S | 1.43 m² | grease aerosol, steam | spray balls | heat, fan | hatch and port shutter rims and their gaskets; camera windows; nozzle bodies; the ceiling is sprayed from its own plane, so the spray balls hang 60 mm below it |
| Floor (steel part) and sump well | S/F | 0.22 m² | everything that falls | spray balls, gate, squeegee | slope 3° | thimble roots (radius 8); sump strainer seat |
| Glass-ceramic hob plate | F (fixed station) | 0.31 m² | boil-over, fat | spray balls at 60 °C, squeegee, paddle as scraper | heat | silicone joint; burnt-on sugar or milk needs the intensive soak |
| T and S thimbles | S | 0.03 m² | drips under the bell | exposed when the bell and jug are lifted off | heat | none once exposed |
| Oven hatch sill | S | 0.03 m² | sliding vessels, drips | spray ball, squeegee | heat | the step between sill and shutter, 2 mm |
| Pucks (3) | F | 0.18 m² | splashes, food | gate, hanging apart | heat | **rotor–spider thrust washer and bush** (open 5 mm when hanging); skid seats (pressed-in PEEK, static joint ≤ 0.1 mm); bayonet lugs |
| Utensils (24) | F | 0.7 m² | food | nozzle row, gate | heat | three dome feet (moved once per wash); bayonet sockets (open, sprayed along their axis in the gate); silicone lips (moulded on, edge line); peeler flexure |
| Cassettes: PZ tube, screw, nut, piston, dies | F | 0.25 m² | food, mince | gate, each part separately: the screw is run out of the nut | heat | **Rd thread on screw and in the nut** (coarse round thread, open, but a thread); grid knife roots (R13: cleaned with the comb pusher first); ricer holes |
| Bell, S rotors, spike, mat, boards, trays, racks | F | 0.6 m² | food | gate | heat; PE boards and silicone dry slowly | PE board cuts (wear part, 2 per year); wire-rack weld nodes; bell bush |
| Vessels and lids (meal-dependent) | F | 0.8–1.6 m² | food, burnt-on fond | gate, rolled; burnt-on: 5 min soak with detergent on the warm hob first | heat | handles and tangs (welded); basket perforations |

Zone F + S per 4-person meal: about 2.8 m² of tub and resident parts plus 1–1.5 m² of vessels, all of it
every time. Zone N (gantry, motors, electronics) is behind the welded skin and stays dry by construction.

**Verification.** Process data per step (temperatures, flow, detergent dose); turbidity and conductivity of
the rinse leaving the sump (8 L loop, sensitive); each item is turned before the ceiling camera under white
and UV-A light after its rinse pass and compared with its reference image (the manipulator presents it;
HYG-026); weekly riboflavin self-test (SM-207); one witness coupon on the red board carrier. A part that
fails is washed once more in the gate (30 s); after a second failure it is put on the hatch tray as
quarantined and the spare is used.

**Raw meat and ready-to-eat** (FSF-040). Sequence: dry before wet, RTE before raw, raw animal food last in
column A (R11). Two board plates, two PZ tubes, two tongs. Where a meal forces raw before RTE (B1), the
red-to-green rinse runs between them. One tub means *temporal* separation only; splashes from raw meat on
the drive wall near column A are not removed by the rinse. The rule is therefore: after class R work no RTE
food is put down in column A except in a vessel, and RTE food is never laid on a surface that is not a
freshly rinsed board. A duplex (two tubs) would double the machine and is not proposed.

**Peelings and scraps** fall on the board or the floor of column A, are pushed by the squeegee into the chip
box (GN 1/6), which leaves through the hatch to the organic waste; nothing passes over the hob. Fines go to
the sump strainer (2 mm), which is lifted out by a puck and emptied into the chip box; no macerator. Frying
fat above 30 mL is poured into a lidded cup and leaves through the hatch (WSH-016).

---

## 7. Numbers

| Item | Value |
|---|---|
| Wall width at 600 depth | **1750 mm** with the oven bay; 1150 mm for the tub alone |
| Height use | 900–1600 tub; 1600–2000 dock, fan, condenser; 0–900 drives, hydraulics, ware store |
| Interior | 1100 × 475 × 700 mm, 366 L |
| Motion actuators | **14** in the cell (4 gantry, 2 spin, 2 retract, T, S, 3 shutters, lock) + 2 at the dock = 16 |
| Other drives | 3 pumps, 2 dosing pumps, fan, 12 valves, 4 induction generators |
| Dynamic seals | **0** |
| Static openings | door, 3 shutters, hob plate, 2 windows, nozzles |
| Custom part types | about 45: tub and door (2), head (4), puck (3), bell and S rotors (3), 15 utensils, PZ and dies (9), fixtures (6), jug and cup (2), shutters (1) |
| Loose parts resident in the tub | about 70 pieces (3 pucks, 24 utensils, 12 cassette parts, 30 vessels and lids) |
| Parts cost, one-off [E] | gantry 0.6 k€; two heads 1.0 k€; three pucks 0.75 k€; tub and door weldment 3.0 k€; hob (4 OEM modules, glass) 0.9 k€; T and S drives with bell and rotors 0.85 k€; hydraulics, tank, boiler, nozzles 1.35 k€; shutters 0.6 k€; cameras, sensors 0.4 k€; controls, drives, supply 0.8 k€; utensils 1.6 k€; cassettes 0.6 k€; vessels, racks 1.7 k€; fan, condenser 0.2 k€: **about 14 k€** without the oven (1.5–2.5 k€) and the dock |
| Manipulator alone (gantry, heads, pucks) | 2.35 k€, in line with D's 2–3 k€ |
| Peak power | hob 2 × 3.5 + 2 × 2.3 kW installed, managed to ≤ 7 kW with the oven at 3 kW; boiler 6 kW and tank 2 kW scheduled outside the cooking peak; motors < 0.8 kW; within 10.3 kW (UTL-010) |
| Noise sources | chopper and jug on S (65–70 dB(A) [E], seconds); jets on the 1.5 mm door skin, which faces the room (risk of drumming, target 48 dB(A) not assured); gantry belts and steppers; skids on the wall; kneading |
| Handling moves per meal | 45–95 (mean of the twelve benchmarks: 65), plus about 40 wash moves |
| Tool change | 6 s; about 10–20 per meal |
| Water per meal | 26 L full wash (12 L short) + 3–8 L rinses during the meal |
| Energy per meal for cleaning | 1.5 kWh (0.65 kWh short) |
| Cell closed after a meal | 25 min (ware dry), 35 min (tub dry) |

---

## 8. Coverage estimate against the 248-meal corpus

Not a meal-by-meal recomputation (the corpus appendix A procedure was not run); an estimate per blocker
under the purchase rule of MEAL-012 (scenario S1 of the corpus, where nine hard operations give 96.0 %).

| Operation (meals) | K8 | Meals lost [E] |
|---|---|---|
| Excluded by requirements 5.4 | — | 8 |
| FLP (32) | turner for pieces, pan pair for thin items; omelette fold by the turner | 0–1 |
| ASM (17) | stacks and layered items yes; folded or hand-held builds (taco, filled wrap, burrito) no: served as components or lost | 3–4 |
| STU (16) | rigid cavities and tubes yes; flat pockets (priority S) and tight poultry stuffing no | 1–2 |
| UNM (11) | pair inversion | 0–1 |
| CAR (12) | boneless with the draw knife; bone-in poultry carved by the guest (adapted) | 0 lost, 3 adapted |
| WRP (10), RLT (4) | mat roll for Rouladen, wraps around a filling; Kohlrouladen lost (LSP), strudel (S) doubtful | 2–3 |
| SHD (6), ROL (10) | tray pizza, loaf, Flammkuchen yes; lining a tart tin with stiff shortcrust weak; round rolls approximated | 1–2 |
| FRM (7), FRB, FRK | extrude and cut; Schupfnudeln approximated | 0–1 |
| BRD (5), SCO (7), POA (1) | yes | 0 |
| Kneading, mash, purée, stir on heat | yes | 0 |
| Depth-axis cases not caught above (arranging in rows across Y, piping) | — | 1–2 |

Lost beyond the agreed exclusions: **9–15 meals**. Coverage **225–231 of 248 = 91–93 % by count**, about
the same by weight (the losses are weight-1 and weight-2 meals; every weight-3 benchmark is covered on
paper). This misses MEAL-002 (95 %) by 5–11 meals. The shortfall is mostly the open-hand operations that
the catalogue lists as unsolved for everyone (G3, G4, G7), plus one or two that are specific to the missing
depth axis. Category check (MEAL-004): Mexican (7 meals) would fall below 85 %, but has fewer than 10 meals.

Adapted methods: the common ones (deep-fry to oven 10, stir-fry 7, skim or skewer 3 = 8 %) plus K8's own
(pan-pair flip for pancakes, crêpes and omelettes about 5 meals; bone-in carving 3; extruded disc patties
and dumplings are not counted as adapted) give about **11 %**, slightly above the 10 % of MEAL-013.

MEAL-009 (whole fresh produce): onion peeling unsolved, trimming of beans and sprouts unsolved, stripping
unsolved; K8 is no better than any other candidate here.

---

## 9. Failure modes and recovery

| Failure | Detection | Recovery | If recovery fails |
|---|---|---|---|
| Puck lags (overload, jam) | Hall lag > 5 mm | gantry yields, backs off, retries with a lower feed or the lever knife | step skipped, recipe re-planned or meal aborted |
| Puck decouples and falls | Hall field lost | other puck lifts it by the bail, head re-acquires; spare puck takes over meanwhile | human opens the door, 1 min; wash |
| Rotor slips a pole (torque overload) | angle lag jumps 18° | harmless: the ring re-locks one pole on; torque limit lowered | — |
| Utensil not locked on the bayonet, dropped | weight missing in the lag signal; camera | picked up by the tongs of the other puck from the floor or a vessel; if it fell into food: fished out, rinsed; food kept (the utensil is clean ware) unless a fragment is missing | human |
| Grit under a skid (salt, bone chip) | friction rise in the travel signal | puck driven through the jet gate (cold), wall squeegeed | scratch on the wall, cosmetic |
| Sticky soil on the wall, friction doubled | lag at no load | wet wall; squeegee pass | force-limited operations slowed |
| Dropped food on the floor | camera | squeegee to the chip box; never returned to food | — |
| Food stuck in the PZ grid or tube | torque reading rises without travel | retract, comb pusher stroke; tube opened (cap bayonet) and flushed in the gate | second tube |
| Dough climbs the kneading frame | torque drops, camera | reverse T for 5 s, scraper pass | — |
| Roulade opens when tipped into the cradle | camera | re-roll once; else pin with the Y-slide | braised open, served as "geschmorte Rinderscheiben" (failure recorded) |
| Pancake tears in the pair flip | camera | served as torn (Kaiserschmarrn rule) or discarded, next one with less butter | — |
| Boil-over | hob sensor, camera, sump turbidity | power down, lid off; spill runs over the flush glass to the gutter; full wash at the end anyway | — |
| A part fails wash verification | camera, turbidity | second gate pass; then quarantine through the hatch, spare part | user informed |
| Both bridges need the same X | planner | P1 and P2 cannot pass; tasks are assigned left and right; the right puck parks at X = 1080 to give P1 the hob | slower |
| Glass-ceramic cracked by a falling puck | camera, leak sensor under the plate | hob disabled, service | — |
| Gantry, head or motor fault | drive diagnostics | décor panel off, part exchanged from the room; the pucks stay on the wall (permanent magnets) | — |
| Power loss | — | pucks hold, Z brakes hold, hob off; on return the heads re-read the puck positions by Hall sensors | UC-12 rules |

---

## 10. Top risks and the cheapest experiment for each

| # | Risk | Experiment (cost, time) | Kill criterion |
|---|---|---|---|
| 1 | **The magnetic figures are calculated, not measured.** Real clamp, shear and torque may be 30 % lower | Rig: two laser-cut steel rings, 20 + 20 magnets, a 1.5 mm 1.4404 sheet, a spring scale and a torque wrench; measure N, F(x), T(θ) at gaps 3.5–5 mm (300 €, 2 days) | holding shear < 150 N or torque < 8 Nm at a 4 mm gap: the concept has no force path left |
| 2 | **Skid friction eats the shear**, above all on a soiled wall (dough smear, syrup, fat, dried starch) | Same rig with four PEEK skids: drag force clean, wet, and with five soils, fresh and dried 30 min (1 day) | friction > 50 % of the shear at 4 mm on the usual soils with the wet wall on |
| 3 | **No depth axis**: reach and approach problems that only show in three dimensions; the front row of the hob | Plywood mock-up of the tub with GN vessels; a hand-held dummy puck constrained to a sheet of acrylic (X, Z, roll only); act out B1, B2, B10 (2 days) | more than three steps per benchmark that cannot be done without moving in Y |
| 4 | **Screw cassette**: thread wear, efficiency, cleanability of the Rd thread and the grid | One PZ from a stainless tube, Rd screw and PEEK nut, driven by a torque-limited drill at 12 Nm: rice 1.5 kg potato, dice carrots, 200 cycles; then riboflavin in a dishwasher (600 €, 1 week) | < 1.5 kN at 12 Nm, or residue in the thread after the gate wash |
| 5 | **Stirring with a swept paddle in rectangular induction ware**: scorching in corners, uneven heat of GN multilayer bases on round coils | Bought GN 1/2 and 1/4 induction pans on a bought hob, a paddle moved by hand in X only: béchamel, risotto, porridge, caramelised onions (150 €, 2 days) | visible scorching with a 5 s sweep interval |
| 6 | **Wash by carrying ware through a jet gate**: coverage inside deep vessels, the puck's own washer and bush, utensil feet, time | Jet frame with 12 nozzles and a pump in a tub; soiled ware (egg, starch dried 2 h, burnt milk) moved by hand along the planned paths; riboflavin (500 €, 1 week) | any class of part not clean in ≤ 30 s of gate time |
| 7 | **Flatness, buckling and drumming of a 1.1 × 0.7 m, 1.5 mm door skin** at 85 °C; gap variation | One skin with the expansion bead in a frame, heated with a steam cleaner; dial gauge, and the rig of risk 1 dragged across (400 €, 3 days) | local waviness > 1 mm over 150 mm (the gap budget is ± 0.5 mm) |
| 8 | **A falling puck breaks the glass-ceramic plate** | Drop a 1.1 kg dummy with the bumper ring from 250, 400, 600 mm on a scrap hob (50 €, 1 hour) | cracks from 250 mm |
| 9 | **Kneading reaction through a frame leaning on the wall**; 1.6 kg of dough at 20 Nm on a canned coupling | Ankarsrum-type bowl drive with a torque sensor and a frame resting on a plate with a load cell (borrowed mixer, 2 days); a bought Ø 90 magnet coupling for the torque | tangential or radial force on the frame > 150 N in the unsupported direction |
| 10 | **Rouladen by mat and two pucks**, pancake by pan pair: shared untested food results | Hand trial with a sushi-type mat and only X–Z hand motion; two crêpe pans | < 80 % first-time success |
| 11 | **Too many loose parts** (about 70 resident, 45 custom types): handling reliability per move × 65–135 moves per meal against REL-001 (98 % of meals) needs 99.98 % per move | Count failures in the mock-up of risk 3; bayonet pick-up test, 1000 cycles on a printed spigot | pick-up failures > 1 in 1000 |
| 12 | **Heat at the pucks and in the door**: PEEK skids and SmCo in steam and fat mist; the gantry electronics sit 20 mm from a wall at 85 °C | Thermocouples on a dummy puck over a searing pan; door cassette with a fan | head magnets > 120 °C or electronics > 60 °C |

---

## 11. Improvements found, changes from the catalogue definition, and what I would borrow

### 11.1 Changes from the catalogue definition of K8

| # | Catalogue | Here | Why |
|---|---|---|---|
| 1 | Magnet heads behind the **back** wall | The drive wall is the **front door** | Every actuator is reachable from the room by removing a panel; the tub back is a plain fixed sheet. Otherwise the gantry would sit between the tub and the house wall, unserviceable |
| 2 | Hold magnets plus a Ø 90 spindle ring (D: 400 N, 150 N, 4–8 Nm) | **One Ø 150 ring of 20 poles** does clamping, dragging and spindle torque; the puck is a loose rotor + spider | Torque grows with radius without more clamp force; one magnet set instead of two; 12 Nm rated; the spider gives a pincer |
| 3 | Force limit handled by "magnet-driven vessels or a ram on a closed cassette" | **Torque-to-thrust cassette** (screw, 2.5 kN) driven by the puck itself; **lean-on-wall** reaction; no external ram | No penetration, no bellows; the force loop closes inside a washable part |
| 4 | Magnet turntable and spindle (face couplings, PEEK window in E) | **Canned radial couplings** in welded thimbles | No axial force, 25 Nm, all-steel tub, no window joint |
| 5 | Tools on pegs; "ordinary dishwasher programme"; 50 min | **Jet gate with the pucks as the conveyor**, tank and boiler; graded programmes; 25 min | The central weakness named in the catalogue |
| 6 | Cooking not placed | **Hob inside the tub**, rectangular ware, swept scraper; oven beside, slid in at floor level | The wash then also removes frying splatter (COK-019); the puck's roll axis serves flipping and pouring directly |
| 7 | — | **Gap modulation** (work / travel / release) and **Hall lag sensing** with a yielding gantry | Less friction in travel; a free force and torque sensor; decoupling becomes rare |
| 8 | No depth axis | **Y-slide utensil**; blade along Y; T under the board | Buys back a depth axis when needed, at the price of the roll |
| 9 | Ball port as the force fallback | Dropped; bellows ram named as the fallback | The calculation shows it is not needed for the benchmarks |
| 10 | Rollers under the puck (D) | **Skids** | Two-directional motion; no axle crevice; cost: friction (risk 2) |

### 11.2 The most valuable improvement

**Force from torque.** The catalogue treats the wall as a force limit. It is a force limit of about 110 N,
but a torque path of 12 Nm, and 12 Nm on a 6 mm screw is 2.5 kN. Dicing, ricing, patty forming and
extrusion move from "expected weak" to "fits", without any penetration. The same idea gives the Y-slide.

Second: **the pucks as the dishwasher's conveyor**, which halves the blocked time and makes coverage a
programmed path instead of a spray-arm lottery.

### 11.3 What I would borrow

* From the ram-and-die candidate (K5): its die set, comb pushers and piston details for the PZ; if K5 proves
  extrusion kneading, the turntable could be dropped.
* From the loose-ware candidate (K6): its 3-minute washer data to validate the gate times.
* From the vessel-stack candidate (K2): the rim standard for the pan pair and the unmoulding pair.
* The common egg module, seam-down cradle, lift-out basket, dosing dock and purchase fallbacks, as listed.
* From D's concept A: the fulcrum-eye lever knife and the comb, used here as drawn there.
* A bought **planar-motor** tile (D:N-idea, XPlanar class) would replace gantry and heads with no moving
  part at all behind the wall; at about 4 kg payload and a high price [U] it is a later option, not a baseline.

---

## 12. Open issues and requests to the architect

### Open issues

1. All magnetic and friction values await the rig (risks 1, 2). The 0.8 factor is a guess.
2. The coverage figure is an estimate per blocker, not a walk of the 248 rows.
3. Thermal design of the door cassette (electronics next to a hot skin) is not done.
4. Whether induction-capable GN ware exists in GN 1/4 and GN 1/6 with a base that heats evenly on a round
   coil was not verified [U]. If not, the front row uses small round pots and loses the full-width scraper.
5. The swept-paddle stirring and the roller creaming are the two food-quality assumptions specific to K8.
6. Reliability: 65 moves per meal plus 40 wash moves, each through one bayonet and one magnet coupling.
7. The three-phase budget with boiler, tank, four coils and oven needs the scheduler (UTL-011).
8. Noise of jets on the door skin.
9. The dock egg module and the piston box are outside the tub and are not washed by it; their cleaning is
   the common front end's open problem.
10. HYG-005: clean ware is stored in the same space in which raw food is open. It is washed again before the
    next meal only if the full wash ran; after a *short wash* the unused parked utensils were not washed.
    Rule proposed: short wash only if no class R food was open.

### Requests to the architect

| # | Request |
|---|---|
| A-1 | **Oven position.** K8 needs the oven beside the tub with its opening in the tub's right wall and its cavity floor at the tub floor level; the oven's own door is replaced by the hatch shutter (modified bought oven). If the transport system may serve the oven instead, the module shrinks from 1750 to 1150 mm |
| A-2 | **Box.** A pour edge and a gate or mesh lid for the dock tilter (X1, X4). K8 needs nothing else from the box; a piston box for pastes is wanted but has a plain-box fallback (spooning in the tub) |
| A-3 | **Transport** delivers into the tub from the left at 250–500 mm above the tub floor with a tray that enters 150 mm, carries up to 8 kg (a pot slid onto it), and also takes away the chip box and quarantined parts. Opened cans, jars and tubs arrive there upright |
| A-4 | **Serving** takes cooking vessels (GN, up to 8 kg) at that hatch and returns them empty for the wash, or K8's ware set is duplicated |
| A-5 | **Ruling on HYG-018**: a glass-ceramic hob plate as part of the tub floor (brittle material in Zone F/S) |
| A-6 | **Ruling on HYG-005 / FSF-040**: is temporal separation with a disinfecting rinse inside one chamber accepted, or is a second chamber required for RTE work? The latter would end K8 in its single-tub form |
| A-7 | **Washing module**: K8 washes all preparation and cooking ware itself and needs only detergent, rinse aid and softened water from the common utility (WSH-009); plates, cutlery and boxes remain with the ware washer |
| A-8 | **Rectangular cooking ware** as the vessel standard (R4 of the catalogue makes GN one of two families; K8 needs it to be the main one) |
| A-9 | A week of rig time for risks 1, 2, 7 and 8 before K8 is judged; they cost under 1000 € together and decide the concept |

---

## Appendix A — Magnetic model

Each block magnet is replaced by two sheets of magnetic surface charge ± B_r/µ₀ on its pole faces
(uniform magnetisation, µ_r = 1). A back-iron plate is represented by its mirror image, i.e. the magnet is
given twice its thickness on the iron side (ideal, unsaturated iron). The pole faces are meshed at
1.2–1.5 mm; the force and the torque on the puck array are the sum of the Coulomb forces between all charge
pairs of the two arrays. No iron saturation, no demagnetisation, no temperature effect; these are covered by
the 0.8 factor of the design values. Check case: two blocks 17.7 × 17.7 × 10 mm (the area of a Ø 20 disc),
B_r 1.30 T, no iron, 0.5 mm apart: 115 N (supplier value for Ø 20 × 10 N42 disc pairs: about 110 N [U]).

| Case (gap 4.0 mm unless stated) | Result |
|---|---|
| Ring R 68, 20 poles 14 × 14, head 6 mm NdFeB 1.33 T on iron, puck 5 mm SmCo 1.08 T on iron: N | 638 N (709 at 3.5; 575 at 4.5; 520 at 5.0) |
| Same, lateral force at 1 / 4 / 7 mm | 66 / 229 / 317 N, with N = 630 / 524 / 353 N |
| Same, torque at 3.7° / 9° | 20.2 / 33.9 Nm, with N = 500 / 0 N |
| Same, 3.7° and 4 mm together | S 180 N, N 421 N, T 17.3 Nm |
| Same, N at gap 8 / 10 / 14 / 20 mm | 291 / 200 / 97 / 34 N |
| Spider, 4 × 15 × 15 at R 95 | N 130 N; S 44 N at 4 mm; yaw 3.7 Nm at 2°, 5.5 Nm at 4° |
| For comparison, D's layout enlarged: 4 blocks 30 × 30 × 12 at the corners of a 110 square | N 804 N; S 170 N at 4 mm, 46 N/mm |
| For comparison, 16 blocks 15 × 15 in four 2 × 2 checkers | N 602 N; S 245 N at 4 mm; repels beyond 10 mm lag |
| For comparison, ring R 36, 8 poles 24 × 22 × 10 (the "Ø 90 spindle") | T_peak 28 Nm but N 1016 N: too much clamp force for its torque |

Eddy-current estimates use P ≈ ½·σ·(v·B)²·V·k with σ = 1.33 MS/m, B = 0.5–0.6 T under the poles, V the wall
volume under the poles and k = 0.5 for the return paths. They are order-of-magnitude figures.
