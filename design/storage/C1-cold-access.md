# C1 — Cold storage access: getting boxes out of the fridge and freezer

Storage round, cold-storage designer. Inputs: `00-storage-brief.md`, `research/03-storage.md` §4 (4.1–4.6),
the cold-variant sections (§7) of S1, S2, S3 and S4, `requirements/requirements.md` (CLD-001…014, CAP-012,
CAP-020…026, RES-004, PHY-004), `DECISIONS.md` #11, #20, #21, #22, #28, and K9b §2 (gallery interface).
Tags: **[C]** calculated here, **[E]** estimate, **[U]** unverified, must be measured or looked up on the real
appliance.

*Status: complete (storage round). Built outline-first; every [U] item is checked on a real unit (section 11).*

## Outline

0. Summary and recommendation
1. What decides the access
   1.1 The interface: the gallery takes boxes from above; there is no front lane in 600 mm depth
   1.2 What a door, a top wall and a side wall contain (where CLD-007 lets us cut)
   1.3 Heat physics: air exchange per opening, stack-effect leakage of a closed exit, conduction, box warm-up
2. Appliances, capacity, number of shells, wall width (built-in vs freestanding, larder fridge, chest freezer,
   drawer units, wine cooler as the cool zone)
3. Candidate access concepts (list)
   * **A** — door hatch with a two-stage vestibule (airlock) in a replacement door
   * **B** — exit through the top wall: a stainless exit plate with a lift-and-slide hatch (OEM door kept as the
     service door)
   * **C** — motorised drawer units (under-counter drawer fridges/freezers) around a shared shaft
   * **D** — door replaced by an insulated panel that carries the internal mechanism (S2) and a port
   * **E** — own idea: two-stage top airlock ("chimney"); a revolving pocket was considered
   * **F** — own idea: chest freezer on a stand, hatch in the lid (a door-only modification)
4. Concept A
5. Concept B
6. Concept C
7. Concept D
8. Concept E
9. Concept F
10. Comparison, recommendation for the fridge and the freezer
11. Gating checks and cheapest experiments

---

## 0. Summary and recommendation

* **The interface decides.** K9b's gallery takes boxes from above, and a 546 mm built-in appliance in a 600 mm deep
  machine leaves no front lane. Every **door** exit (A, C, D1) therefore needs a shaft: +220 mm of wall for a door
  vestibule, ≈ +1,470 mm for drawer units. A **top** exit costs no width at all.
* **Physics.** A horizontal top hatch with the cold air below exchanges only ≈ 5–10 L per pass, about the box's own
  volume: fridge ≈ 0.2 kJ, freezer ≈ 0.5 kJ and < 0.1 g of ice per pass. A vertical L hatch exchanges 37–58 L and an
  open drawer 90–125 L. Per day the **closed** exit matters more than the openings. The tall cell's stack effect
  (1.1–2.6 Pa) sucks room air in through any top leak, so the exit must close on a **compression (magnetic)
  gasket**, and in the freezer on a **heated seat**. Sliding or brush seals would grow ≈ 13 kg of ice a year in the
  seal.
* **Recommendation: concept B for both cells.** A window (M throat 210 × 200) is cut in the verified free middle
  band of the top wall and lined with a double-walled PP throat. A stainless exit plate carries a 40 mm
  lift-and-slide hatch on a magnetic gasket; it is spring-closed, opened by 1 small motor, and open ≈ 3.4 s per
  passage. The OEM door stays as the service door. Added energy: fridge ≈ 7 kWh/year (+6 %), freezer ≈ 38 kWh/year
  (+13–17 %). Access cost ≈ €300 (fridge) and ≈ €335 (freezer).
  * **Fridge:** 178 cm built-in static **larder** fridge (no ice box: it would sit under the window). Inside are
    S1-type stacks, ≈ 52–58 positions, the only mechanism that reaches CAP-021's 45 in one shell.
  * **Freezer:** 178 cm built-in **NoFrost** freezer, with a 100 mm skirt against the fan jet and a 3 W heated seat.
    Inside: S1 (≈ 32–34) or S4 (24, if the interior is ≥ 375 mm deep). Fallbacks: E (two-stage top airlock) if the
    fan jet cannot be shielded; F (chest freezer, the cheapest, but static frost fails CLD-008) for cost-down.
* **Shells and wall:** 2 shells, **1,200 mm** (K9b allotment, PHY-004 3.6 m). Three shells (1,800 mm) only if the
  fridge uses an aisle mechanism (S3/S4: 24–33 per shell) or for CAP-026. The appliances cost ≈ €1,700–2,800.
  Freestanding units are 650+ mm deep and do not fit.
* **Cool zone (8–15 °C, ≥ 8):** not in the cold shells. Use a thermoelectric box in the ambient storage, or an
  in-fridge heated "cellar sleeve" if the measured fridge has ≈ 15–20 spare positions. A wine cooler costs ≥ 300 mm
  for 8 boxes.
* **Rejected:** A (door vestibule): good thermally but +220 mm, 2 actuators, poor manual access. C (drawers): 2.7 m
  of wall, €9–17k, 10× the air per box. D1 (port in a mechanism-carrying door) does not fit. D2 = B's exit with
  S2 on the door: best service access, < 45 positions in a fridge.
* **Score** (simplicity, hygiene, fit, reliability, cost): B 4.40, D2 3.35, E 2.65, F 2.60, A 2.50, C 2.35.
* **Biggest weakness:** B depends on two things that are not published: what lies inside the chosen models' top
  wall, and the real interior depth. **Cheapest experiment:** cut the window into a used fridge (≈ €250) and
  measure the per-pass exchange with a CO₂ tracer and the energy and seat temperature for a week.

---

## 1. What decides the access

### 1.1 The interface: the gallery takes boxes from above; there is no front lane in 600 mm depth

K9b §2 fixes the hand-over: the **transport gallery runs at z 2000–2200 over the whole machine and enters each
module through a ceiling port**. Whatever happens inside the cold module, the box must finally rise to the gallery.
The depth budget decides where the cold exit can be:

```
 side section through the cold module (y = 0 at the wall, y = 580 inner front; z from the floor)
 z 2200 +------------------------------------------------------------+
        |  GALLERY (hoist, X travel)                                 |
   2000 +==================== gallery floor, port ===================+
        |  gap ~110: appliance vent outlet, exit plate, small motors |  <- the only free space
  ~1890 +------------------- appliance top wall --------------------+
        |rear |                                            |door  |fr|
        |vent | built-in appliance body  ~ 480 deep        |~60   |19|  <- 546 device + 19 front
        |~0-40| (liner, foam, interior ~ 400-430 deep)     |      |  |     = 565 of 580
        |     |                                            |      |  |
   ~120 +-----+--------------------------------------------+------+--+
        | plinth, carcass floor                                       |
      0 +------------------------------------------------------------+
         y 0                                                      580 600
```

* **Front exit:** a box leaving through the door needs a free lane in front of the door of at least box depth
  + clearance ≈ **220 mm** for a vertical lift. The device (546) plus furniture front (19) leaves ≈ 15–35 mm.
  A front lane would make the machine ≈ 820 mm deep, which DECISIONS #11 forbids. A box cannot be tilted on its
  side to pass a thin slot (BOX-008: liquids leak-tight only to 30°).
* **Side exit:** a vertical shaft beside the appliance costs **≥ 220 mm of wall per shaft**, plus a lift in it.
* **Top exit:** costs **no width and no depth**. The gap between the appliance top (z ≈ 1890 [E]) and the gallery
  floor (z 2000) already exists. It is also the **vent outlet** of a built-in appliance (air enters at the plinth,
  rises behind the device, leaves at the top; Liebherr asks ≈ 200 cm² [U]), so anything mounted there must leave a
  vent path, e.g. a front grille in the gap.

So concepts that open the **door** (A, C, D) have to pay with width (a shaft) or with a change of the transport,
while concepts that open the **top** (B, E, F) fit the K9b interface as it is.

### 1.2 What a door, a top wall and a side wall contain (where CLD-007 lets us cut)

General construction of current built-in appliances (Liebherr/BSH class); every line is **[U] per model** and is
checked with the service manual, a thermal camera (warm lines = condenser and frame heater, cold lines = suction
line) and a 6 mm borescope pilot hole before any cut.

| Part | Built-in static larder fridge | Built-in NoFrost freezer | Chest freezer | Cut allowed? |
|---|---|---|---|---|
| **Door / lid** | PU foam 40–60 mm, steel or ABS skin, door liner with bin ribs, magnetic gasket in a groove, door-switch magnet, fixing rail for the furniture front. **No refrigerant.** | same, 60–80 mm foam [U] | lid: PU 50–70 mm, gasket, counterbalanced hinges, sometimes a lamp | **yes** (CLD-007: "door or exit") |
| **Top wall** | PU 40–60 mm. Front 60–80 mm: hinge reinforcement plates in both front corners (reversible door), door switch, often the **control unit / display and LED light in the ceiling front** [U]. Rear: niche fixing brackets, sometimes the cable junction. Refrigerant: normally none — the roll-bond evaporator is foamed behind the **rear** liner, the capillary and suction line run down the rear | PU 60–80 mm [U]. **Hot-gas frame heater** (a refrigerant tube) in the front flange, ≈ 20–40 mm behind the front face. NoFrost: fan and evaporator behind the rear cover, in some models **air ducts or outlets along the ceiling** [U] | there is no top wall, only the lid; the evaporator is wrapped around the four inner walls and the condenser is a skin in the outer walls | **only "at the exit"**, in a verified free window: middle band ≥ 80 mm behind the front face, ≥ 100 mm in front of the rear wall, ≥ 40 mm from the side walls [E] |
| **Side walls** | built-in: usually free (condenser at the rear/base); fixing screws in pre-set holes. Freestanding units often have **skin condensers in the side walls** | same | evaporator + condenser skins: **no-go** | possible "at the exit", but it needs a shaft (1.1) |
| **Rear wall** | evaporator, drain hole and channel | fan, evaporator, defrost heater, drain | evaporator | **no-go** |
| **Bottom** | compressor step (≈ 200 × 200 [U]), drain to the evaporation tray | same, larger | compressor step at one end | **no-go** |

**Consequence 1:** the cut-able window in the top wall lies in the **middle band**, not at the front edge. Any
in-cell mechanism must bring the box under that window. **Consequence 2:** a fridge with an internal **4-star ice
box** (e.g. the IRBe 5121 used as reference in research 4.6 and S1–S4, 248 + 27 L) has that ice box at the top of
the interior, right under the window. **Use the larder version without ice box** (section 2).

**CLD-007 reading used here.** The door and its gasket may be replaced or changed. Inside, shelves, bins and drawers
may be removed and fittings added if they hook into the liner's existing shelf ribs (no drilling of the liner). One
opening may be cut for the exit, in the top wall or in the door, provided the window is verified free of refrigerant,
wiring and hinge plates; its foam edge is sealed vapour-tight (otherwise moisture diffuses into the foam and, in a
freezer, ices it up over years). The controller and refrigerant circuit stay untouched. Warranty is void in every
concept except F.

### 1.3 Heat physics: per opening, closed-exit leakage, conduction, box warm-up

Conditions as research 4.4: room 20 °C / 50 % RH; fridge +4 °C (≈ 30 kJ per m³ of exchanged air, ≈ 4 g of
water per m³ condensing); freezer −18 °C (≈ 70 kJ/m³, ≈ 7.8 g/m³ of ice). Daily passes from CAP-012: **fridge 25
retrieve + 25 return + ≈ 5 ingestion = 55 passes/day; freezer 5 retrieve + ≈ 1 return (thawed food is not refrozen)
+ ≈ 4 ingestion = 10 passes/day**.

**(a) Exchange while open** [C, ± factor 2]. Vertical openings (door hatch, drawer slot): buoyancy flow
Q = (Cd/3)·A·√(g·H·ΔT/T), Cd 0.6.

| Opening | Fridge | Freezer |
|---|---|---|
| vertical hatch 206 × 150 (M box) | 1.8 L/s | 2.8 L/s |
| vertical hatch 350 × 200 (L box) | 4.7 L/s | 7.3 L/s |
| drawer slot 560 × 200 (drawer out) | 7.4 L/s | 11.7 L/s |
| **horizontal top hatch, cold air below** | **stable layering: no buoyancy flow.** Exchange = box volume displaced + wake + gripper ≈ **5–10 L per pass** [E] | same if no fan jet passes under the hatch; **10–40 L** if the NoFrost ceiling jet sweeps the opening [E, U] |
| top hatch open, chimney through the cell | limited by the cell's bottom leaks (drain, gasket) ≈ 50 mm² [E]: 0.04 L/s, **< 0.3 L per 4 s opening** | 0.06 L/s, < 0.3 L |

**(b) Leakage of the *closed* exit — the stack effect** [C]. A cold cell 1.5–1.6 m tall is a chimney turned upside
down: cold air presses outwards at the bottom and the cell sucks room air in at the top with Δp = Δρ·g·H =
**1.1 Pa (fridge), 2.6 Pa (freezer)**. Any leak in a *top* exit therefore leaks **inwards**, and in a freezer the
inflowing humid air freezes **right at the leak**, i.e. in the hatch gasket. With the cell's own bottom leak
≈ 50 mm² [E] in series:

| Added leak at the top | Fridge: air / energy / water per day | Freezer: air / energy / **ice** per day |
|---|---|---|
| 10 mm² (gasket as good as an OEM door, ≈ 8 mm²/m) | 0.7 m³ / 20 kJ / 3 g | 1.0 m³ / 70 kJ / **8 g** |
| 100 mm² (sliding or brush seal, 0.1 mm × 1 m) | 3.0 m³ / 90 kJ / 12 g | 4.5 m³ / 320 kJ / **35 g (13 kg/year)** |

**Design rule:** an exit must close on a **compression gasket** (magnetic, like the door), never on a sliding or brush
seal, and the freezer exit needs a **heated frame** (as the OEM door frame has) so that the inward leak does not
build ice. A low exit (bottom of a door) leaks *outwards* instead: dry cold air, no ice, but a sweating front.

**(c) Conduction of an exit** [C]. Example for an L-size throat (350 × 210): a 40 mm PU hatch replaces 50–70 mm of wall over ≈ 0.12 m²; gasket line ≈ 1.24 m
at ψ ≈ 0.03 W/(m·K) [E], throat/frame ≈ 1.12 m at ψ ≈ 0.02 W/(m·K) with a plastic thermal break [E]: **UA ≈ 0.074 W/K**.
At 25 °C room (RES-004): fridge 1.6 W → **≈ 7 kWh/year** electric (COP ≈ 2); freezer 3.2 W, plus a dew-point
controlled 4 W frame heater at ≈ 50 % duty (half of it entering the cell) → **≈ 44 kWh/year**. Against a built-in
larder fridge ≈ 115–125 kWh/year and a 178 cm NoFrost freezer ≈ 220–300 kWh/year [U], that is **+6 % and +15–20 %**:
inside CLD-005's +25 %, and it shows that **the closed exit costs far more than the openings** (fridge top hatch:
55 × 8 L × 30 kJ/m³ = 13 kJ/day ≈ 1.3 kWh/year of heat). B's smaller M throat (section 5) has UA ≈ 0.054 W/K.

**(d) Box warm-up — the same for every concept** [C]. A chilled box (0.4 kg food, 0.15 kg PP) out for ≈ 10 min warms
by ≈ 3 K (food) / 12 K (shell): ≈ 8 kJ to re-cool, ×25 = **≈ 0.2 MJ/day** — ten times the fridge's opening losses.
It condenses ≈ 0.5–1 g of water on the box when it leaves (dew point 9 °C), which the transport must tolerate. Frozen
boxes rarely return (research 4.4), so the freezer's box load is mostly ingestion. **Conclusion: opening losses do
not separate the concepts unless the opening is vertical and large (drawers). Tightness when closed, frost at the
seal, fit to the interface and simplicity do.**

---

## 2. Appliances, capacity, number of shells, wall width

### 2.1 Which appliance

| Type | Example (research 4.1 or [U]) | Outer size W × H × D | Interior [E] | Fits 600 depth? | Top exit possible? | Price [U] | Verdict |
|---|---|---|---|---|---|---|---|
| **Built-in 178 cm larder fridge** (no ice box), static | Liebherr IRBe/IRBd 51**20** class, ≈ 300 L [U model] | 559 × 1770 × 546 | ≈ 470 W × 410 D × 1620 H; compressor step ≈ 200 × 200 at the rear bottom | yes | yes, middle band | 800–1,300 | **fridge choice** |
| Built-in 178 cm fridge with 4-star ice box | IRBe 5121 (248 + 27 L, 999–1,299) | same | ≈ 480 × 380 × 1500, **ice box at the top** | yes | **no** (ice box under the window) | 999–1,299 | avoid |
| Built-in 178 cm fridge-freezer | ICNb/ICNc 5123 (253–264 L) | same | two compartments | yes | only the upper one | – | avoid: the lower compartment has no exit |
| **Built-in 178 cm NoFrost freezer** | Siemens GI81NA…, Bosch GIN81…, Liebherr IFN…51xx class, ≈ 210 L [U] | 559 × 1770 × 546 | ≈ 430 W × 370 D × 1450 H (thicker walls, fan cover ≈ 40 mm) | yes | yes, if no ceiling duct in the window | 900–1,500 | **freezer choice** |
| Built-in under-counter (82–88 cm) | IFNd 3924 87 L 1,099; IFNbi 3553 65 L | 560 × 880 × 550 | ≈ 87 L | yes | only one unit per column has a free top | ≈ 1,100 | wastes half a column |
| Freestanding larder fridge | 600 × 1850 × **650–680** | – | ≈ 500 × 480 × 1700 | **no** (#11) | side walls often skin condensers | 600–900 | rejected |
| Under-counter drawer units | Liebherr UIKo 1550, Miele KU 7175 D (2 drawers, each 0–14 °C) | 597 × 820 × 550 | 3 drawers ≈ 90 L | yes, but the drawers open into the room | – | 1,500–2,800 | concept C |
| Chest freezer ≈ 100 L | many brands, static | ≈ 550 × 850 × 560 | ≈ 450 × 360 × 650 + step | yes | **the lid is the door** | 250–350 | concept F |
| Wine cabinet (5–20 °C) | built-in 88 cm, compact 45 cm niche, 30 cm wide under-counter [U] | – | – | yes | yes (thermoelectric units have no refrigerant at all) | 500–1,500 | cool zone, see 2.4 |

The two 178 cm built-in shells cost **≈ €1,700–2,800** together, against ≈ €1,000 assumed in DECISIONS #28 for a
"large fridge + freezer": built-in, larder-type and NoFrost each cost extra. The chest freezer (F) saves ≈ €800.

### 2.2 Positions per shell, by in-cell mechanism [E, on the interior estimates above]

| In-cell mechanism (design doc) | Needs inner depth | Larder fridge 470 × 410 × 1620 | NoFrost freezer 430 × 370 × 1450 |
|---|---|---|---|
| S1 stacks, grab from top (digging) | 2 rows: 360 | 2 rows × 2 M stacks = **≈ 40–44 M**; with a tight pitch (176/112) a 3rd stack of S per row: **≈ 60–68 raw, ≈ 52–58 usable** after the dig reserve | 2 × 2 M stacks, rear row over the step: **≈ 32–34** |
| S2 car on the door, 1 lane per level | 1 lane + shaft: ≈ 370 + flat door | ≈ 38–42 | ≈ 30 |
| S3 belts, 1 row per level | 386 | ≈ 27–33 | **does not fit** (370 < 386) |
| S4 aisle shuttle, one rack face | 371 | ≈ 24–26 | **zero margin** (370 vs 371) |

The fridge reaches CAP-021 (≥ 45) in **one** shell only with stacks (S1), and only with the larder interior. The
freezer reaches CAP-022 (≥ 20) with S1 or S2 for sure, with S3/S4 only if the measured inner depth is ≥ 375–390.
**The inner depth of both chosen models is the first measurement of the whole cold design.**

### 2.3 Number of shells and wall width

| Plan | Shells | Wall | Chilled / frozen positions | Meets |
|---|---|---|---|---|
| **P1 (MVC, recommended)** | 1 larder fridge (S1-type stacks) + 1 NoFrost freezer | **1,200 mm** (K9b allotment) | ≈ 52–58 / ≈ 24–34 | CAP-021, -022, PHY-004 3.6 m |
| P2 (aisle mechanism in the fridge) | 2 larder fridges (S3/S4) + 1 freezer | 1,800 mm | ≈ 50–60 / ≈ 24–34 | total ≈ 4.2 m: **fails PHY-004 (M)**, only the larger configuration |
| P3 (CAP-026 larger storage: chilled ≥ 90, frozen ≥ 35) | 2 larder fridges (stacks) + 1 freezer (+ a 2nd freezer if the first gives < 35) | 1,800–2,400 mm | ≈ 104–116 / ≈ 32–68 | within 4.2 m only with 3 shells |
| P4 (3.0 m target: chilled + frozen in one 600 cell) | – | 600 mm | – | **impossible off the shelf**; needs a custom VIP cell (research 4.3 option 6), outside CLD-007 |

### 2.4 The cool zone (8–15 °C, ≥ 8 boxes, CAP-024)

| Option | Energy [C/E] | Width | Positions lost | Remarks |
|---|---|---|---|---|
| **(i) Thermoelectric cool box in the ambient module** (insulated 50 mm PU, ≈ 50 L, Peltier with fans, no refrigerant) | load 4–9 W (room 20–32 °C), COP 0.5–1 → **≈ 50–110 kWh/year** | inside the ambient allotment (≈ 250 × 450 × 600) | none in the cold | **recommended**; owner is the ambient designer; uses the ambient mechanism; ethylene producers in their own boxes |
| (ii) "Cellar sleeve" inside the larder fridge: one stack enclosed in a 25 mm insulated sleeve, ≤ 5 W PTC heater, an insulated "plug box" on top that the S1 hoist moves aside like any box | heater ≈ 3.5 W + fridge re-cools it → **≈ 46 kWh/year**, independent of room temperature | 0 | **≈ 15–20 fridge positions** (sleeve walls take the S stack's width) | only if the measured fridge gives ≥ 65 raw positions |
| (iii) Compressor wine cooler (30 cm or 60 cm column, or 45 cm compact) | 100–150 kWh/year [U] | **≥ 300 mm** | – | own exit to automate, glass door; too much for 8 boxes |
| (iv) Convertible zone of a fridge-freezer | – | – | – | none found in 178 cm built-in units [U] |

---

## 3. Candidate access concepts

| | Concept | Where the box leaves | Thermal barrier | In-cell mechanism assumed |
|---|---|---|---|---|
| **A** | Door hatch with two-stage vestibule in a replacement door | through the door, sideways into a shaft | inner flap + vestibule + outer flap | S4 aisle behind the door |
| **B** | Top-wall exit plate with a lift-and-slide hatch, OEM door kept | up through a window in the top wall | one insulated slide on a magnetic gasket | S1 stacks (fridge), S1 or S4 (freezer) |
| **C** | Motorised drawer units around a shared shaft | drawer pulls out into the shaft, gallery hoist picks from above | the drawer front | none (the drawer is the mechanism) |
| **D** | Panel door carrying the mechanism (S2) | D1: port in the door (needs a shaft); **D2: up through B's top window** | as A or B | S2 car on the door |
| **E** | Own idea: two-stage top airlock ("chimney") | up, through two hatches | inner leaves + outer slide | bottom-carrying lift (S3 type) |
| **F** | Own idea: chest freezer on a stand, hatch in the lid | up through the lid | lid hatch | S1-type, or the gallery hoist itself |

Common data. Boxes from research 2.4: S 108 × 176, M 162 × 176, L 325 × 176 footprints; M with lid ≈ 115 mm
high, L up to ≈ 165. A clear throat of **350 × 210** passes S, M, L and a 1 L carton carrier; an M-only throat
is 210 × 200. Cell inner sizes from 2.1. Passes per day from 1.3: fridge 55, freezer 10.

---

## 4. Concept A — door hatch with a two-stage vestibule (airlock) in a replacement door

**Principle.** The OEM door is replaced by a flat machine-built door (60 mm PU between stainless skins, OEM gasket
profile, OEM hinges) with an insulated vestibule at the top level: an inner flap towards the cell, an outer flap
towards the outside, never open together. The in-cell carriage pushes the box into the vestibule, the inner flap
closes, the outer flap opens and the box is pushed out onto a ledge. Since there is no front lane (1.1), **the
shells are turned 90° so that both doors face a shared vertical shaft**, and the gallery hoist descends into the
shaft to the ledge.

```
 top view of the cold module, z at the hatch level (≈ 1700)           x along the wall
 x  0  40                    590      830                    1380 1420
    +--+----------------------+-------+-----------------------+--+  y 580 (front, room)
    |v |  FRIDGE (turned)      |       |       FREEZER (turned) | v|
    |e |  559 wide now in y    |SHAFT  |                        | e|
    |n |  interior 410 (x)     | 240   |                        | n|
    |t |  S4 rack | aisle ->[V]|ledge  |[V]<- aisle | S4 rack   | t|
    |  |          |         ^ |  ^     |                        |  |
    +--+----------------------+-------+-----------------------+--+  y 0 (wall)
              vestibule in the door bay ^  ^ gallery hoist comes down 300 mm onto the ledge
 total ≈ 1,420 mm instead of 1,200: +220 mm (more if the doors must swing open)

 section through one door at the vestibule (side of the shaft)
        cell                door (60 PU)                 shaft
   ... box --push-->  |inner flap| VESTIBULE |outer flap|  --> ledge
                      | 40 PU,   | 240 x 220 | 40 PU,    |
                      | magnetic | x 200 D   | magnetic  |
                      | gasket   | 10.6 L    | gasket    |
                      +---- the bay protrudes 150 mm into the cell (top level only)
```

| Item | Design and figures |
|---|---|
| **Opening and seal** | Two vertical guillotine flaps, 40 mm PU in PP shells, each pressed onto a magnetic gasket by end-of-travel wedges (compression seal, 1.3 b). **One cam shaft** sequences both (inner open → both closed → outer open), so they cannot both be open: 1 gear motor on the door's outer face, spring return to "both closed" on power loss. Outer flap seat heated (4 W, freezer). |
| **Inside** | S4 aisle shuttle behind the door; its carriage pushes the box 200 mm into the vestibule. A small belt in the vestibule floor (motor in the door foam, warm side) pushes it out onto the ledge. Motors outside the cold: flap cam, vestibule belt; S4's X/Y motors ride inside (S4 §7). **Frost:** the vestibule takes humid air every cycle, 0.08 g of ice per freezer cycle → it needs a daily warm-up (10 W for 10 min with both flaps shut) and a drain tube with a trap to the evaporation tray (CLD-008). **Condensation** on the outer flap face: thermal break and heater. |
| **Heat per opening** [C] | vestibule 10.6 L (M+L size): fridge 0.3 kJ, freezer 0.75 kJ and 0.08 g ice. Without vestibule (one flap, 8 s open, L size): fridge 37 L / 1.1 kJ, freezer 58 L / 4.1 kJ / 0.45 g. |
| **Heat per day** [C] | openings: fridge 55 × 0.3 = 17 kJ, freezer 10 × 0.75 = 8 kJ. Closed: two gasket lines + vestibule walls, UA ≈ 0.10 W/K → fridge **≈ 9 kWh/year**; freezer ≈ 27 kWh/year + seat heater (4 W, 50 % duty, as 1.3 c) ≈ 24 + vestibule warm-up ≈ 1 → **≈ 52 kWh/year**. |
| **Retrieval time** | S4 in-cell ≈ 10 s, push in 2 s, cam 1 s, outer open 1 s, belt out 2 s, outer close 1 s = **≈ 17 s** + gallery dip 300 mm and lift ≈ 5 s → **≈ 22 s** (CLD-006 ≤ 45 s). Outer flap open ≈ 3 s (CLD-004). |
| **Manual use** | **Poor.** The doors face a 240 mm shaft and cannot swing open; service means lifting the door off its hinges after removing the shaft ledge, or making the shaft ≥ 600 mm (+580 mm width). A side-wall variant **A'** (shells face the room as usual, the vestibule is cut into the side wall towards a shaft between them) keeps the OEM doors and the same +220 mm, but is a side-wall cut, not a door change. |
| **Cleaning** | vestibule: smooth PP, drained; the floor belt touches box bottoms only, wiped by a lip; cell interior as any fridge (human, twice a year). |
| **Parts, cost per shell** [E] | custom door (stainless, foamed) €250, vestibule with 2 flaps, gaskets, wedges €150, cam motor and spring €60, vestibule belt €80, heater, warm-up and drain €45, ledge €30, sensors €40 → **≈ €655 per shell**, plus the shaft frame (≈ €100) and **+220 mm of wall**. |
| **Risks** | (1) width: 1,420 mm breaks K9b's 1,200 allotment (PHY-004 then needs ambient −220 mm); (2) human access; (3) vertical flaps frost up at the seat, and the vestibule needs its own defrost and drain; (4) appliances turned 90° ventilate into the end walls — needs 40 mm gaps (included); (5) the door bay costs ≈ 150 mm of interior depth at the top level. |

**Verdict A.** Thermally it is the best *vertical* exit (the vestibule cuts the open exchange from 37–58 L to 11 L),
but in K9b it costs 220 mm of wall, two extra actuators per shell plus a vestibule defrost, and it ruins manual
access. It belongs to an architecture with a front transport lane, which K9b does not have.

---

## 5. Concept B — exit through the top wall: stainless exit plate with a lift-and-slide hatch

**Principle.** One window is cut into the appliance's top wall, in the verified free middle band, and lined with a
double-walled plastic throat that seals the foam edge; a stainless exit plate around it carries a 40 mm insulated
slide that lies on a magnetic gasket like a door. The in-cell mechanism presents the box under the throat with the
hatch closed; the slide lifts off and moves aside for ≈ 3.4 s while the gallery hoist reaches ≈ 190 mm down, grips
and lifts the box. The OEM door, controller and refrigerant circuit stay untouched; the door is the service and
emergency door. Cold air does not climb, so the open hatch exchanges little more than the box's own volume.

**Throat size: M width.** A one-piece slide must park on the appliance top (559 × 486 without the door). For an
L throat (350 × 210) the slide plus its travel needs ≈ 800 mm in X or ≈ 520 mm in Y: it does not fit. The cold
cells therefore use **S and M boxes only** (and a 1 L carton carrier on the M footprint); the M throat is
**210 × 200**. Volume check: 45 × 1.0–1.6 L = 45–72 L ≥ 35 (CAP-021); 20 × 1.0–1.6 L ≥ 20 L (CAP-022). An L-capable
option is in the risk table.

```
 TOP VIEW of one shell's top wall (machine x along the wall; y = 0 at the wall, front at y 580)
 x  0  20       65                                                535   579 600
 y 560 +--+------------------------- door top (moves: keep free) ----------+--+
   500 |  +--- cabinet front face ---------------------------------------- +  |
       |  | [hinge]   front strip: hinges, display, light, frame heater [hinge]|
       |  |           ---- NO CUT within 90 mm of the front face ----     |  |
   410 |  |  +====================+-------- window cut 260 x 260 ---+     |  |
       |  |  | SLIDE parked       |   +- throat 210 x 200 -+       |     |  |
       |  |  | 250 x 240 x 40     |   |   box M 162 x 176   |       |     |  |
       |  |  | <-- travel 260 --> |   +---------------------+       |     |  |
   150 |  |  +====================+---------------------------------+     |  |
       |  |   exit plate 1.4016 (magnetic stainless) 520 x 300, bonded |     |  |
       |  |   [gear motor + constant-force spring]  [space for the in-cell drives' bushings]
    40 |  +--- rear: niche fixings; vent channel behind the device ------+  |
     0 +--+---------------------------------------------------------------+--+
          slide park x 20-270            window x 270-530 (inside the liner, x 65-535)

 SECTION through the throat (y-z), freezer figures in brackets
 z 2000 =========== gallery floor ======[ port ≥ 230 x 220 ]===========
                                          | gallery hoist gripper
  1950           rails + ramps   +-------+v+-------+  slide 40 PU in a PP shell,
                                 | SLIDE (closed)  |  magnetic gasket underneath
  1892 ==exit plate (1.5)========+==+===========+==+=========
       top wall PU 50 [70]       |PP|  throat   |PP|  double-wall PP sleeve, cavity foamed,
  1840 ======= liner ============|  |  210x200  |  |  MS-polymer seals both flanges
                                 |  | skirt 60  |  |  [100 in the freezer: below the ceiling jet]
  1780                           +gutter ring---+--+  drains to the cell's own drain channel
  1760                        [ box M presented, lid 20 mm below the skirt ]
                                    (port stack of S1, or S4 carriage)
```

| Item | Design and figures |
|---|---|
| **Opening** | Slide on two drylin rails with **ramps**: the first 6 mm of travel lift it 4 mm (peels the magnetic gasket from one end, like opening a door, ≈ 15 N), then it slides 260 mm along −x to its park position. A **constant-force spring** pulls it back and the ramps drop it onto the gasket: **fail-closed** on power loss (CLD-004, CLD-012). Drive: one 12 V gear motor with a cord drum (≈ 0.8 s per stroke), two Hall end switches. Option: no motor — a cam tab on the gallery carriage pushes the slide open during the last 260 mm of its approach and the spring closes it as the carriage leaves (−1 actuator, but couples the timing to the gallery). |
| **Seal** | **Compression seal**, never sliding (1.3 b): OEM-style magnetic door gasket profile, corner-welded ring 250 × 240, on 1.4016 ferritic stainless (magnetic). Target leak ≤ 10 mm² (as an OEM door per metre). **Freezer:** a 3 W silicone heater wire under the gasket seat, switched by a dew-point controller (room T/RH + seat NTC; ≈ 50 % duty assumed) — CLD-014 "does not freeze shut". **Fridge:** no heater; the plastic throat is the thermal break, so the seat stays above the room dew point. |
| **Cut and foam edge** | Survey first (1.2). Cut 260 × 260 with R 20 corners: skin by oscillating tool, foam by hot wire/knife, liner last from inside; no flame, gas detector running (R600a). The PP sleeve's outer flange laps the skin, its inner ring snaps on from below and laps the liner; the cavity is filled with 1-K PU; the outer flange is sealed with butyl (vapour barrier), the inner one with food-safe MS polymer. No screw through the skin outside the window. |
| **Inside: mechanism and motors** | Fridge: **S1 stacks** (the only in-cell mechanism that gives ≥ 45 in one shell, 2.2), with the port stack under the throat; S1's XY motors sit on the top, their shafts pass **through the same exit plate** (PTFE bushings), so the window is the only modification. Freezer: S1 (≈ 32–34) or S4 (24, if the depth is ≥ 375). All penetrations — shafts, the PUR −40 °C sensor cable — go through the exit plate, "at the exit". Digging and travel happen with the hatch closed. |
| **Frost, condensation, defrost** | Fridge: the cold sleeve wall gets a short film of condensate in humid summer air (dew point 23 °C at 32 °C / 60 %); it runs down the sleeve to the **gutter ring** at the skirt's lower edge and through a PUR tube along a liner rib into the cell's own drain channel — no drip on the presented box (CLD-014). Freezer: 0.04–0.08 g of rime per opening forms on the skirt; the NoFrost cell's dry air sublimates it [E], the evaporator collects the rest and the appliance defrosts itself (CLD-008). The heated seat stops the closed-hatch inward leak from building ice in the gasket. **NoFrost fan jet:** if the ceiling outlet blows across the window, the open exchange rises to 10–40 L; the 100 mm skirt reaches below the ceiling jet layer [E, U: smoke test, 11]. |
| **Heat per opening** [C] | fridge 5–10 L → **0.15–0.3 kJ**; freezer 5–10 L → **0.35–0.7 kJ, 0.04–0.08 g ice** (up to 2.8 kJ / 0.3 g if the fan jet is not shielded). Chimney flow while open < 0.3 L (1.3 a). |
| **Heat per day and year** [C] | M throat: UA ≈ 0.054 W/K. **Fridge:** conduction ≈ 5.0 + closed-gasket leak ≈ 1.0 + openings (55 × 0.3 kJ) ≈ 0.8 → **≈ 7 kWh/year electric (+6 %)**. **Freezer:** conduction + heater ≈ 32 + leak ≈ 5 + openings ≈ 0.5 → **≈ 38 kWh/year (+13–17 %)**; the heater is the largest item, so its dew-point control matters more than the opening time. Both inside CLD-005 (+25 %). |
| **Retrieval time** | Hatch sequence: open 0.8 s, gallery hoist down 190 mm 0.5 s, grip 0.5 s, up 300 mm 0.8 s, close 0.8 s → **hatch open ≈ 3.4 s** (CLD-004 ≤ 10 s). In-cell part from the mechanism: S1 top box ≈ 4–5 s, planned retrievals ≈ 6 s mean; an unplanned bottom box of an 11-high stack ≈ 55–60 s [E, scaled from S1 §3.2], which **misses CLD-006 (≤ 45 s)** unless placement by expected use (S1 §3.3) is kept — that is S1's weakness, not the exit's. S4 in the freezer ≈ 8 s. |
| **Put-away** | reverse: the in-cell mechanism waits under the throat (S1: empty port stack top; S4: carriage at the top), the hatch opens, the gallery sets the box down, the hatch closes, the in-cell mechanism stores it. Returned freezer boxes are blown dry at the transport first (S1/S2 freeze-bonding rule). |
| **Manual use** | The OEM door opens normally at any time: the front stacks are in direct reach (S1), all lanes with S4. A stick-on reed switch on the carcass and a magnet on the furniture front tell the machine the door is open → in-cell motion stops (no appliance modification). Power loss: hatch springs shut, door works. |
| **Cleaning** | Throat and skirt: smooth PP, radii ≥ 6 mm, wiped weekly by a **"swab box"** (a box-shaped tool with an ethanol-wetted sponge collar that the gallery passes down and up through the throat) [idea, optional]. Slide underside and gasket: wipeable from above when parked. Spills inside go to the cell floor and the appliance drain; the in-cell grid is cleaned as in the S-document; like any fridge, a human wipe-out about twice a year remains [E]. |
| **Parts and cost per shell** [E] | exit plate 1.4016 laser + bent €60; double-wall PP throat €60; slide (PP shell, PU core) €50; magnetic gasket ring €15; rails + ramp blocks €40; gear motor, constant-force spring, 2 Hall switches €55; butyl, MS polymer, 1-K PU €15; door reed €5 → **fridge ≈ €300**; freezer + heater wire, dew-point sensor, SSR €35 → **≈ €335**. Plus ≈ 2 h survey and cut. |
| **Actuators / seals** | **+1 actuator per shell** (0 with the gallery cam option); **0 dynamic seals** (the slide seals statically). |

**Risks and mitigations**

| Risk | Effect | Mitigation |
|---|---|---|
| The chosen model has control unit, light, ducts or frame heater in the window | cannot cut | pick the model by service manual and thermography **before buying in series**; fallback D2 window position or concept D1/A |
| NoFrost ceiling jet under the window (freezer) | 10–40 L per opening, more rime | 100 mm skirt; place the window away from outlets; smoke test (11) |
| Gasket frost (freezer) | hatch sticks, leaks more | heated seat, dew-point control, magnetic compression gasket; motor current shows a stuck slide |
| Foam edge not vapour-tight | ice in the foam over years, λ rises | double-wall sleeve, butyl outside; inspect by thermography yearly |
| Vent outlet in the gap partly blocked | condenser runs hot | slide and motor occupy ≤ 40 % of the top; front vent grille ≥ 200 cm² in the gap |
| L boxes needed in the cold | M throat too small | two upward-opening leaves (105 mm each) that stand up into the gallery port: L throat 350 × 210 fits, at the price of a centre seam and a second actuator |
| Interior smaller than estimated | < 45 positions | measure first (11); then P2 (3 shells) or the cellar-sleeve option drops |

**Verdict B.** The cheapest and simplest exit that fits K9b without width: one cut in a verified window, one slide,
one small motor, a static gasket, and the OEM door kept for humans. Its open exchange is about the box's own
volume, so a vestibule would not improve it (see E). Its uncertainties are all on the appliance — what is in the top
wall, how deep the interior is, where the freezer's fan blows — and each is checked on one unit before buying.

---

## 6. Concept C — motorised drawer units around a shared shaft

**Principle.** Under-counter drawer fridges and freezers (597 × 820 × 550) are left completely unmodified except
for a pull bar screwed to each drawer front. Facing the room their drawers would open into the kitchen, where no
machine part can reach (1.1), so the units are **turned 90° and face a shaft**, two units high on each side. A
lift in the shaft hooks a drawer and pulls it out; the gallery hoist descends into the shaft and picks the box from
the open drawer from above; the drawer is pushed back.

```
 front view (fronts removed), one shaft with a column of units on each side
 x  0  40           590            1060            1610 1650
 2000 +===================== gallery floor, port over the shaft ==============+
      |  |  (unused 240)  |   SHAFT 470   |  (unused 240)   |  |
 1760 |  +---------------+  ^ rope hoist  +-----------------+  |
      |v | FRIDGE unit 2 |  | down to     | FREEZER unit 2  | v|
      |e | 3 drawers ->  |  | 1.7 m       |<- 3 drawers     | e|
  940 |n +---------------+  |  [drawer    +-----------------+ n|
      |t | FRIDGE unit 1 |  |   pulled    | COOL unit (Miele| t|
      |  | 3 drawers ->  |  |   into the  | KU 7175 D type, |  |
  120 |  +---------------+  |   shaft]    | one drawer 10 C)|  |
      |  plinth           lift with drawer hook on the wall side       |
    0 +--------------------------------------------------------------------+
 per unit (UIKo 1550 class): 3 drawers, each ≈ 450 x 480 x 150-200 inside [U] -> 4 M + 2 S, 12-18 per unit [E]
```

| Item | Design and figures |
|---|---|
| **Positions and width** | 12–18 per unit [E] (research 4.3: "≈ 12 GN 1/6"). P1 needs chilled ≥ 45 → **3 fridge units**, frozen ≥ 20 → **2 freezer units** (IFNbi 3553 class, 3 drawers, 65 L), cool ≥ 8 → **1 dual-zone unit** with one drawer at 10 °C (the one attraction of C: the cool zone comes free). 6 units = 3 columns of 2 → 2 shafts: **≈ 3 × 550 + 2 × 470 + 80 ≈ 2,670 mm of wall** (vs 1,200). Units are 820 high, so 240 mm under the gallery stay unused. |
| **Opening and seal** | the OEM drawer front with its OEM magnetic gasket — **no appliance modification at all** (CLD-007 fully met). The shaft lift (Z) carries a hook (X) that engages the pull bar; drawer out 450 mm in ≈ 2.5 s, back in ≈ 2.5 s, OEM soft-close. |
| **Inside** | no in-cell mechanism: the drawer is the mechanism and the boxes stand in one layer (no digging, no stacking, no freeze-bonding between boxes). Motors: shaft lift and hook, both in the warm shaft. **Frost:** every opening exposes the whole drawer and its ≈ 6 boxes to room air; in the freezer ≈ 1 g of rime per opening lands on boxes and drawer walls, not on the evaporator; NoFrost air sublimates it slowly [E]. |
| **Heat per opening** [C] | drawer slot 560 × 200 open ≈ 9 s plus half the drawer's air: fridge 7.4 L/s × 9 s + 20 L ≈ 90 L → **2.7 kJ**; freezer 11.7 L/s × 9 s + 20 L ≈ 125 L → **8.8 kJ, 1.0 g ice** — ≈ 10× concept B. |
| **Heat per day and year** [C] | fridge 55 × 2.7 = 150 kJ/day → ≈ 8 kWh/year electric; freezer 10 × 8.8 = 88 kJ/day → ≈ 6 kWh/year and **≈ 3.6 kg of ice per year**. No added conduction (OEM fronts). Six small appliances use far more energy in total than two large ones (≈ 6 × 90–150 kWh/year [U] vs ≈ 350–420). |
| **Retrieval time** | lift to the drawer ≈ 2 s, drawer out 2.5 s, gallery hoist down 1.0–1.7 m ≈ 1.5 s, grip 0.5 s, up 1.5 s, drawer in 2.5 s → **≈ 10.5 s**, of which the drawer is **open ≈ 9 s** (CLD-004 ≤ 10 s: borderline). A 1.7 m rope descent needs sway control. |
| **Manual use** | **Good**: a removable 470 mm shaft front panel; a person pulls any drawer into the shaft by hand. |
| **Cleaning** | drawers are removable and the boxes stand in one layer; spills stay in one drawer; the shaft is dry and open. |
| **Parts and cost** [E, U] | 6 drawer units at €1,500–2,800 = **≈ €9,000–17,000**; per shaft: lift, hook, frame ≈ €400. |
| **Risks** | width (2.7 m: PHY-004 cannot be met), appliance cost, open time at the CLD-004 limit, rime on every frozen box of an opened drawer, long rope descent. |

**Verdict C.** Rejected for the main store. It is the only concept with zero appliance modification, it is the
friendliest to humans and it would give the cool zone for free, but it costs ≈ 2.2× the wall and ≈ 5–10× the
appliance money of B, and it opens 10× more cold air per box. A single dual-zone drawer unit could still serve a
*larger-storage* configuration (CAP-026) as cool zone if the wall is there.

---

## 7. Concept D — door replaced by an insulated panel that carries the mechanism (S2's idea)

**Principle.** The OEM door is replaced by a flat machine-built panel (60 mm PU between stainless skins, the OEM
gasket profile, the OEM hinges); S2's car runs on two Z rails bolted to its inner face, with the Z motor on the warm
outer face, and two cone pins register the closed door to the shelf frame (S2 §7). Opening the door swings the
whole mechanism out of the cell. The port is the open question:

* **D1 — port in the door.** The box leaves forward through a hatch in the panel. With no front lane (1.1) the
  shells must face a shaft (as A), and because the mechanism hangs on the door, the door must swing open for
  service: the shaft would have to be ≥ 600 mm wide. **Not feasible** in K9b.
* **D2 — door carries the mechanism, the exit is B's top window.** The car lifts the box to the top level and its
  toe pushes it ≈ 100 mm rearwards onto a fixed **port shelf** under the throat (the car row is the first 182 mm
  behind the door, the window band starts 90 mm behind the front face); the gallery hoist takes it from there.

```
 side section D2 (y from the cabinet front face, rearwards)
 z 2000 ======= gallery floor ===========[port]===================
  1892 ==== top wall ====[ B: exit plate, slide, throat 210 x 200 ]====
                          |  throat  |
  1780   car at top level | ---> [port shelf] (fixed, on liner ribs)
         |<- car row 182 ->|<- one storage lane 182 ->| 60-75 free, evaporator
  door   |  car on Z rails |  level n                 |
  panel  |  (X, Y motors   |  level n-1  ...          |
  60 PU  |   ride inside)  |                          |
  [Z motor outside, shaft through the panel in a PTFE bush; cable loop at the hinge]
```

| Item | D2 design and figures |
|---|---|
| **Opening and seal** | B's lift-and-slide hatch over the window (same parts, same 3.4 s). The new door seals on its OEM-profile magnetic gasket and is never opened in operation. |
| **Inside** | S2 car on the door: Z motor warm (outside), **X and Y motors ride on the car inside** (S2: NEMA 17 rated −30 °C [U], low-temperature grease, IP65); belts PU, slides drylin, cables PUR −40 °C. Frost and condensation as B. One lane per level (S2: 50 % of the plan area). |
| **Heat per opening** | as B: fridge 0.15–0.3 kJ, freezer 0.35–0.7 kJ. |
| **Heat per day and year** [C] | B's figures plus the Z shaft bush, 0.02–0.05 W/K [S2 value is the upper end]: fridge ≈ 7 + 2–5 = **≈ 9–12 kWh/year**, freezer ≈ 38 + 5–13 = **≈ 43–51 kWh/year**. The custom door must match the OEM door's gasket tightness (5 m of gasket — the largest leak line of the whole cell). |
| **Retrieval time** | S2 ≈ 13 s inside + 1 s push onto the shelf + hatch ≈ 3.4 s → **≈ 17 s** (CLD-006 met; S2 has no digging). |
| **Manual use** | **Best of all concepts**: opening the door swings the car out and every lane is open to the hand. But the door gains ≈ 6–8 kg [E] on OEM hinges whose load rating with a furniture front is ≈ 18–25 kg [U], and the motor cable must loop across the hinge. |
| **Cleaning** | the mechanism comes out with the door and is wiped outside the cold; shelves are stainless on liner ribs, sloped to a rear gutter (S2). Throat as B. |
| **Capacity** | S2: **≈ 38–42 in a larder fridge** (< 45: P2 with two fridge shells, 1,800 mm) and ≈ 30 in the freezer (≥ 20). |
| **Parts and cost per shell** [E] | door panel ≈ €200 + B's exit ≈ €300–335 = **≈ €500–535 for the access**; with S2's car and shelves (≈ €600) ≈ €1,100–1,150 per shell. |
| **Risks** | hinge load and door sag (registration by cone pins tolerates ± 2 mm); custom door gasket quality; two motors in the cold on a moving car; the furniture front must hang on the custom door. |

**Verdict D.** D1 does not fit. D2 is B's exit with a different in-cell mechanism: it buys the best service access
and keeps every fitting off the liner, at the price of a custom door (gasket risk, hinge load) and two motors in the
cold. With S2 it does not reach 45 in one fridge shell. It is a good alternative **for the freezer** if S2 is chosen
there; as an access concept it adds nothing to B except the door-mounted service swing.

---

## 8. Concept E — own idea: two-stage top airlock ("chimney")

**Principle.** B's window becomes a short vertical airlock: inner leaves at the liner level, B's slide at the top,
and between them a vestibule just tall enough for one box. The cell is never open to the room, even for 3 s. This
is research 4.3's recommended vestibule, moved from the door to the top.

```
 section (y-z), freezer
 z 2000 ====== gallery floor, recessed 30 mm over the port =====
  1970          +------- B slide (outer), magnetic gasket -----+
  1930          | collar | VESTIBULE 210 x 200 x 140 = 5.9 L   |   raised PP collar 80 mm
  1892 === top wall 70 ===|   box M rests on 2 spring pawls     |
  1822 === liner =========+== inner leaves: 2 x 105, slide apart in x, ramps onto a gasket ==
                 cell     ^ bottom-carrying lift (S3/S2 type) pushes the box up through
```

| Item | Design and figures |
|---|---|
| **Opening and seal** | outer: B's slide. Inner: two leaves of 105 × 220 × 30 mm that slide apart in x under the ceiling and drop onto a compression gasket on ramps (1.3 b: no sliding seal), one motor with a rack-and-pinion pair. Interlock in software and by a mechanical blocker. |
| **Box path** | Retrieval: the in-cell lift **carries the box from below** (a top-gripping hoist would be trapped between the two closures) through the open inner leaves; two spring pawls in the collar let the rim pass upwards and hold it; lift down, inner leaves close, outer slide opens, gallery hoist lifts the box off the pawls. Return: the gallery sets the box on the pawls, outer closes, inner opens, the lift comes up under the box, **a solenoid retracts the pawls**, the lift lowers. Rotating "revolving-door" pockets were considered and dropped: with a vertical box flow they turn the box upside down. |
| **Frost, defrost** | each cycle brings ≈ 5.9 L of room air into the vestibule; in the freezer its ≈ 0.05 g of water rimes onto the vestibule walls, the pawls and the inner leaves, **not** onto the evaporator. The vestibule needs a 10 W warm-up for 10 min per day (both closures shut) and a drain tube with a trap (CLD-008). |
| **Heat per opening** [C] | 5.9 L: fridge 0.18 kJ, freezer 0.41 kJ / 0.05 g — **the same as B's single hatch (5–10 L)**, because a top hatch is already layered. E wins only if a NoFrost jet sweeps the window (B: 10–40 L). |
| **Heat per day and year** [C] | two gasket lines, UA ≈ 0.07 W/K: fridge ≈ 9 kWh/year; freezer ≈ 38 + 4 (second line) + 2 (warm-up) ≈ **44 kWh/year** — slightly worse than B. |
| **Retrieval time** | B + ≈ 2.1 s (lift into the vestibule, inner close): exit ≈ 5.5 s, outer open ≈ 3.4 s. |
| **Manual use, cleaning** | as B; the vestibule has two more corners and pawls to wipe. |
| **Parts and cost per shell** [E] | B ≈ €300–335 + inner leaves, ramps, motor €90 + pawls and solenoid €40 + warm-up heater and drain €40 → **≈ €470–505**; **+2 actuators** (3 per shell). Needs a bottom-carrying in-cell lift, which rules out S1 and S4 (top grippers). |
| **Risks** | pawls and leaves rime up (freezer); 30 mm gallery recess; three actuators in series on every cold retrieval. |

**Verdict E.** A vestibule is worth it for a *vertical* opening (A: 37–58 L → 11 L) but not for a *horizontal*
one: cold air does not climb out of a top hatch, so B already behaves like an airlock. E keeps a role only as
**fallback for the freezer** if the smoke test (11) shows that the NoFrost jet cannot be kept away from B's window.

---

## 9. Concept F — own idea: chest freezer on a stand, hatch in the lid

**Principle.** A chest freezer is a top-access appliance by nature: its lid is its door, its evaporator and
condenser are in the walls, so a window in the **lid** is a pure door modification (CLD-007 at its cleanest). A
≈ 100 L chest (≈ 550 × 850 × 560 [U], €250–350) stands on a stainless stand so that its lid is at z ≈ 1890, like
the shells; B's slide sits on the lid. Inside, four M stacks stand on a **turntable** turned by a shaft through the
lid, so any stack can be brought under the fixed hatch; the gallery hoist itself digs through the hatch.

```
 front view of the column                     top view inside the chest (≈ 450 x 360 + compressor step)
 z 2000 ===== gallery floor, port ======        +--------------------------------------+------+
  1890  [B slide on the LID][turntable motor]   |   turntable Ø ≈ 340 with 4 M stacks  | comp.|
        +-------------------------------+       |   (2 x 2, 5 high);  hatch over       | step |
        | CHEST FREEZER ≈ 100 L, static |       |   position "P"                       | 2 S  |
        | 4 M stacks x 5 + 2 over step  |       |        [A][B]                        | stks |
  1040  +-------------------------------+       |        [D][P] <- hatch               |      |
        | stand; 940 mm without top     |       +--------------------------------------+------+
        | access (electronics, or ambient racks reached from the ambient module's side [U])
   100  +-------------------------------+
```

| Item | Design and figures |
|---|---|
| **Opening and seal** | B's lift-and-slide hatch, M throat, heated magnetic seat, on the lid. OEM lid hinges and gasket kept; the whole lid opens by hand for service. Variant **F'**: no cut at all — a motor arm lifts the OEM lid and the gallery digs with the lid open; but the open lid needs ≈ 550 mm headroom (chest top ≤ z 1450), the gallery needs a Y axis, and the lid stays open for the whole dig (≈ 30 s), which breaks CLD-004 even though a horizontal opening loses little. |
| **Inside** | turntable (stainless disc on a dry PEEK slewing ring), shaft through the lid in a PTFE bush, motor on the lid (warm); no motor, wire or grease in the cold. **Digging is done by the gallery hoist through the hatch**: each dug box is lifted out and set back on another stack after a turntable step, with the hatch closed while turning. **Frost:** the chest is **static**: rime from hatch passes and the lid gasket deposits on the walls; chests need a manual defrost every 1–2 years and have **no automatic drain** — **CLD-008 (M) is not met** [U: a NoFrost chest in this size was not found]. |
| **Positions** | 4 stacks × 5 M + 2 S stacks over the step ≈ **22–25** [E] (CAP-022 ≥ 20, little margin). |
| **Heat per opening** [C] | horizontal, static, no fan: 5–10 L → 0.35–0.7 kJ, 0.04–0.08 g. A dig costs ≈ 2 passes per dug box. |
| **Heat per day and year** [C] | ≈ 30 passes/day (10 retrievals × ≈ 3 with digging) → ≈ 21 kJ/day; closed: B exit + turntable shaft UA ≈ 0.074 W/K + seat heater → **≈ 38 kWh/year**, against ≈ 140–180 kWh/year for the chest [U]: **+21–27 %**, at the CLD-005 limit because the base appliance is so frugal. |
| **Retrieval time** | top box of the stack under the hatch: ≈ 4 s; other stack: + turntable 2 s; bottom of 5: 4 dig moves × ≈ 6 s + pick ≈ **30 s** (CLD-006 met), hatch open ≈ 3 s per passage. The gallery is busy during the dig (TRN coupling). |
| **Manual use** | poor: the lid is at 1.9 m (step stool), boxes are stacked. |
| **Cleaning** | the chest is a tub: spills stay at the bottom, drained by hand through the defrost plug. |
| **Parts and cost** [E] | chest €250–350, stand €80, B exit on the lid €335, turntable + shaft + motor €150 → **≈ €800–900 including the appliance**, ≈ €600–1,000 less than a built-in NoFrost freezer with its in-cell mechanism. |
| **Risks** | CLD-008 failed (static frost, manual drain); 940 mm of column without top access; 35 kg appliance at height; zero capacity margin. |

**Verdict F.** The cleanest CLD-007 solution and the cheapest freezer, with no motor in the cold. It fails CLD-008 and
wastes the lower half of the column. Keep it as the **cost-down fallback for the freezer** if the customer accepts a
yearly service defrost, or for a design where the space under the chest is reachable from the ambient storage.

---

## 10. Comparison and recommendation

### 10.1 Figures side by side (per shell; "freezer" = NoFrost unless F)

| | A door vestibule | **B top slide** | C drawers | D2 door mech. + B exit | E top airlock | F chest + lid hatch |
|---|---|---|---|---|---|---|
| Wall for P1 capacity | 1,420 (+220) | **1,200** | ≈ 2,670 | 1,800 (S2 < 45 in a fridge) | 1,200 | freezer only; 940 mm of column lost |
| Air per opening, fridge / freezer | 11 / 11 L | **5–10 / 5–10 L** (10–40 L with fan jet) | 90 / 125 L | as B | 6 / 6 L | – / 5–10 L |
| Heat per opening, fridge / freezer | 0.3 / 0.75 kJ | **0.15–0.3 / 0.35–0.7 kJ** | 2.7 / 8.8 kJ | as B | 0.18 / 0.41 kJ | – / 0.35–0.7 kJ |
| Added energy per year, fridge / freezer | 9 / 52 kWh | **7 / 38 kWh** | 8 / 6 kWh (+ 6 small appliances) | 9–12 / 43–51 kWh | 9 / 44 kWh | – / 38 kWh (+21–27 %) |
| Exit open per passage | ≈ 3 s | **≈ 3.4 s** | ≈ 9 s | ≈ 3.4 s | ≈ 3.4 s | ≈ 3 s |
| Exit part of a retrieval | ≈ 12 s | **≈ 3.4 s** | ≈ 10.5 s (all) | ≈ 4.4 s | ≈ 5.5 s | ≈ 4 s + dig |
| Actuators added per shell | 2 | **1** (0 with gallery cam) | 2 per shaft | 1 (+ S2's) | 3 | 2 |
| Access cost per shell | ≈ €655 + shaft | **≈ €300–335** | ≈ €400 per shaft + €9–17k appliances | ≈ €500–535 | ≈ €470–505 | ≈ €565 + chest €250–350 |
| Manual use | poor | **good** (OEM door) | good | **best** | good | poor |
| CLD-007 / CLD-008 | door ✓ / vestibule defrost | top-wall window ✓ (if verified) / ✓ | ✓✓ / ✓ | door + window ✓ / ✓ | window ✓ / vestibule defrost | lid only ✓✓ / **✗ static** |

### 10.2 Score (brief criteria, 1–5)

| Criterion (weight) | A | **B** | C | D2 | E | F |
|---|---|---|---|---|---|---|
| Simplicity (30 %) | 2 | **5** | 2 | 3 | 2 | 3 |
| Hygiene (25 %) | 3 | **4** | 4 | 4 | 3 | 2 |
| Coverage / fit (20 %) | 2 | **4** | 1 | 3 | 3 | 2 |
| Reliability (15 %) | 3 | **4** | 3 | 3 | 2 | 2 |
| Cost (10 %) | 3 | **5** | 1 | 4 | 4 | 5 |
| **Weighted** | 2.50 | **4.40** | 2.35 | 3.35 | 2.65 | 2.60 |

### 10.3 Recommendation

```
 FRONT VIEW, cold module, plan P1 (x 0-1200), fronts on
 z 2200 +--------------------------------------------------------------+
        |                  gallery (hoist, X travel)                   |
   2000 +==========[port]=============================[port]==========+
        | vent grille [slide|window]     | vent grille [slide|window]  |  gap ≈ 110
  ≈1890 +--------------------------------+-----------------------------+
        |  LARDER FRIDGE 178, static     |  NoFrost FREEZER 178        |
        |  (no ice box), 559 wide        |  559 wide                   |
        |  OEM door = service door       |  OEM door = service door    |
        |  S1 stacks 2 rows x (2 M + 1 S)|  S1 2 x 2 M  or  S4 2 lanes |
        |  ≈ 52-58 usable positions      |  ≈ 32-34  /  24 positions   |
        |  window: M throat 210 x 200,   |  same + 100 mm skirt +      |
        |  no heater                     |  3 W dew-point heated seat  |
  ≈ 120 +--------------------------------+-----------------------------+
        |  plinth: vent intake                                         |
      0 +--------------------------------------------------------------+
        x 0                             600                         1200
```

* **Fridge: concept B** on a 178 cm built-in **static larder fridge without ice box**, M throat 210 × 200 in the
  middle band of the top wall, lift-and-slide hatch on a magnetic gasket, no heater, gutter ring; in-cell **S1-type
  stacks** (the only mechanism giving ≥ 45 in one shell). Added energy ≈ 7 kWh/year (+6 %), hatch open ≈ 3.4 s,
  ≈ €300.
* **Freezer: concept B** on a 178 cm built-in **NoFrost freezer**, with a 100 mm throat skirt against the fan jet and
  a 3 W dew-point-controlled heated seat; in-cell S1 (≈ 32–34) or S4 (24, if the depth is ≥ 375) or S2 on a D2 door.
  Added energy ≈ 38 kWh/year (+13–17 %), ≈ €335. **Fallbacks:** E if the jet cannot be shielded; F (chest) as the
  cost-down freezer if a yearly service defrost is accepted.
* **Shells and wall:** 2 shells, **1,200 mm** (K9b allotment, PHY-004 3.6 m kept). A third shell (1,800 mm) is needed
  only if the fridge uses an aisle mechanism or for CAP-026. Appliances ≈ €1,700–2,800 (more than #28's €1,000).
* **Cool zone:** not in the cold shells — a thermoelectric box in the ambient storage (≈ 50–110 kWh/year), or the
  in-fridge cellar sleeve (≈ 46 kWh/year, −15–20 fridge positions) if the measured fridge has room. A wine cooler costs
  ≥ 300 mm of wall for 8 boxes.
* **Vestibules:** not needed on a top exit (E shows why); they are only worth it on vertical openings.

**Biggest weakness (honest):** B stands or falls with what is inside the top wall of the chosen models and with the
real interior depth. Neither is published (research 4.1), and both are measured on one unit before anything is
bought in series (section 11).

---

## 11. Gating checks and cheapest experiments

| # | Check | How | Cost, time | Decides |
|---|---|---|---|---|
| 1 | **Interior and top wall of the chosen models** | service manuals; measure W × D × H, compressor step, top-wall thickness on a showroom unit; thermal camera on the top after 2 h of running (frame heater, ducts, cables) | ≈ €0–100, 1 day | P1 vs P2, window position, S1/S4 in the freezer |
| 2 | **Cut test in a used fridge** (the cheapest proof of B) | second-hand static fridge €50–150; cut a 260 × 260 window; plywood/XPS slide with a magnetic gasket strip; log cell temperature, energy (smart plug) and seat temperature for one week at 50 % and 70 % RH; measure exchange per pass with a CO₂ tracer (fill to ≈ 5,000 ppm, pass a box dummy with the hatch open 3.4 s, read the drop) | ≈ €250, 2 weeks | the 5–10 L per pass and the +6 % claim |
| 3 | **NoFrost jet** | smoke pencil and hot-wire anemometer through a 6 mm pilot hole at the window position of a running NoFrost freezer, door closed | ≈ €50, 1 day | skirt length, or concept E |
| 4 | **Closed-hatch tightness** | small fan and a 0–10 Pa manometer on the slide mock-up: leak area ≤ 10 mm²; then one week in a freezer: no ice in the gasket with the heated seat | ≈ €80 | the CLD-014 claim and the heater duty |
