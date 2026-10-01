# Meal preparation — Cost round 2: K10, the €2 k machine

**K10** challenges K9c's conclusion (`K9c-design-to-cost.md` §6.3) that "K9b's function set does not reach
€2 k" and that "a machine without a gantry has never reached 93 %". It looks for a **different principle**,
not a cheaper build of K9b. Binding: DECISIONS #1–28, in particular #8/#25 (the machine washes, peels and
cuts produce), #26 (≥ 93 % coverage), #27 (no texture change), #4/#21 (food-contact materials), the hygiene
rules of C2 (no human cleaning, raw/ready-to-eat separation, disinfection) and #28 (machine part ≈ €2 k at
one-unit prices).

Markers as in K9c: **[D]** from an earlier document; **[W]** web price checked 2026-10-01 (URL in §2);
**[E]** engineering estimate; **[C]** calculated here; **[U]** unknown, a test decides. Prices: EU retail for
one unit incl. VAT, own assembly labour not counted. §1–§6 cost the meal-preparation cell on K9c's boundary;
§7 extends K10 to the whole machine (storage handling included, as Ben's €2 k is meant); ingestion is outside
everywhere.

**Result.** **K10 "KÜCHENGERÄT"** is a cell built from household appliances that a small hand feeds: a bought
**thermo-cooker** (Cecotec Mambo class, €219) replaces K9b's hub, ring coil, press cup and S ware; a **slim
dishwasher used as bought** (turned 90°, raised) is the only washer and the clean store; bought gadgets (unpeeled-
garlic press, ricer/Spätzle press, push dicer, mandoline) do the cutting; the **kitchen furniture is the
enclosure**; K9c's printer-class gantry with a cheap lip-sealed roll axis is the hand (4 actuators instead of 6).
**Cell machine part €2,520** (thermo-cooker as household appliance) — **€2,739 like-for-like against K9c's €4,313
(−37 %)**; with further cuts (K10-L) **€2,250 at 232 meals = 93.5 %**. Coverage −1 meal against K9b (MX06).
**Whole machine** (K10-W: the cell's X rail runs 3.6 m and a hoist digs lidded boxes from the tops of fridge,
freezer and ambient column, replacing the storage round's four robots and gallery): **≈ €3.0–3.3 k** at one-unit
prices against **≈ €7.5 k** (storage round + K10 cell) and **≈ €9.3 k** (storage round + K9c). **€2 k for the
whole machine at 93 % was not found**: hand, controls and storage handling alone cost €2.1 k; a series of ≥ 50
would reach ≈ €2.2–2.4 k. K9c's "≈ €3.3 k floor for the cell" is refuted; "no gantry-free machine at 93 %"
stands (bought arms carry ≤ 0.75 kg below €4 k).

---

## 0. Radical cost ideas (first pass, € effect against K9c's €4,733)

| # | Idea | Rough € effect |
|---|---|---|
| I1 | **Kitchen furniture is the enclosure**: IKEA METOD carcasses, a normal worktop, a bought stainless splash-back and an IKEA glass door; no custom deck, box, walls or frame | −700 … −900 |
| I2 | **Bought Thermomix-class clone** (heated jug, blade, scale, kneading, steaming) as the whole hub: replaces T, S, ring coil, kneading roller, press cup, blender jug, cutter cup, spinner | −500 … −700 net (clone +€300–450) |
| I3 | **Bought dishwasher used as is, front-loading, for ALL washing** (ware, tools, dishes, hatch trays), door and racks worked by the hand with a hook; no cut tub, no 30 L store, no well valves | −400 … −600 (machine) and −€200 (appliances) |
| I4 | **Duplicate cheap ware instead of washing during the meal**: every meal runs from clean ware, one dishwasher load after the meal; red/green separation by count, not by turnaround washing | −100 net, −1 programme, −rinse cup |
| I5 | **No roll axis and no canned coupling**: passive tools hung on a cheap pin coupler; pouring by tipping cradles or by the clone's own jug; 3 axes only | −250 … −300 |
| I6 | **Bought kitchen gadgets as the produce module**: V-mandoline (slice, julienne), lever dicer (dice), electric spiral peeler (apple, potato, pear, kiwi, mango), abrasive potato peeler, apple corer — the hand only feeds and pushes them | −300 (fixtures + stem tools) |
| I7 | **One cheap controls stack**: one Klipper board with on-board drivers + a €40 compute module, one USB camera, appliances driven through opto/relay "button pressers" on their own boards | −300 … −350 |
| I8 | **Bought desktop robot arm** (€300–1,500) instead of a gantry — only if nothing heavier than ≈ 0.5–1 kg is ever lifted | −200 … −400 if feasible; payload probably kills it |
| I9 | **Transport gallery as the cell's X axis**: one X beam carries the storage shuttle and the cell's Z mast | −250 (cross-module) |
| I10 | **Trade time for hardware**: prep (wash, peel, cut, portion) runs early, serially, into lidded GN boxes in the fridge; cooking is a short second phase → slow NEMA 17 belt axes, one tool at a time, no parallel stations | −150 … −250 |
| I11 | **Splash at the source, not at the walls**: every hot or wet process runs under a lid (clone closed, pans with splatter screens, dishwasher closed); open food only on the board → enclosure shrinks to a splash-back and a front guard | −300 … −500 (part of I1) |
| I12 | **No stubs on the ware**: handles gripped by a cheap servo parallel gripper or magnetic ware picked by an electro-permanent magnet | −250 … −320 |
| I13 | **No hatch drawer**: the guard door unlocks when the meal is ready; the diner takes plates from the serving shelf | −70 |
| I14 | **Appliance relays instead of interface boards** (hob, oven, clone, dishwasher): press their own buttons by opto-couplers soldered across the touch keys | −100 … −150 |
| I15 | **Worktop-height cell under the wall cabinets** (gantry under a wall-cabinet run, like a cooker hood), built-in hob and dishwasher below as in any kitchen | enables I1/I3 at €0 extra |

## 1. The ideas weighed, and the K10 principle

### 1.1 Verdicts

| # | Verdict | Reason |
|---|---|---|
| I1 | **Taken** | The worktop (Gastro table), splash-back, carcasses and bin pull-out are kitchen furniture the household needs in that wall section anyway; only the guard, liners, brackets, shelves and cut-outs are machine part (€465 instead of K9c's €860 net of furniture) |
| I2 | **Taken** — the core of K10 | One bought appliance replaces the hub (T, S, ring coil), the blender jug, cutter cup, kneading roller and part of the press cup; it is also the third heated position (COK-002), the scale and a closed, lidded wet process that splashes nothing. Searching above 120 °C stays on the domino |
| I3 | **Taken, with one installation change** | A slim 45 cm dishwasher is used as bought, but **turned 90° and raised to z 1,000** so that its door opens into the cell and its racks are loaded from above by the hand. No tub cut, no well, no 30 L store. It is also the clean store between meals |
| I4 | **Taken** | Household dishwashers need ≥ 1 h for a disinfecting programme, so nothing is washed during a meal; a second board, knife, tongs and GN make raw/RTE separation by items, not by turnaround washes. The thermo-cooker jug disinfects itself by boiling (§6) |
| I5 | **Rejected** | The roll axis carries the generic peeling (#25: produce on the fork-spit turned against a fixed peeler) and pouring, flipping, inverting into the dishwasher. It is made cheap instead: geared NEMA 23 with a lip seal (€110 instead of €185) |
| I6 | **Taken** | Ricer/Spätzle press, unpeeled-garlic press, push dicer, V-mandoline and pump spinner are bought, dishwasher-safe household gadgets; the hand only fills them and pushes their lever. The custom press cup (N3) disappears |
| I7 | **Taken** | Klipper on a €40 printer board with 4 on-board drivers; the appliances are driven through their own power stages (SSR, opto-couplers, interface boards) |
| I8 | **Rejected** | Bought arms: myCobot 280 0.25 kg $649, Dobot Magician V3 0.5 kg $1,899, UFactory Lite 6 0.6 kg €3,600, Dobot MG400 0.75 kg $3,780, SO-101 0.5 kg ≈ €150–500 (Q9). The lightest full item (pot with pasta, jug with soup) is 2.5–3.5 kg and the cell is 1.8 m wide; no arm under €4 k does it |
| I9 | **Option only** (K10-S, §8) | Saves ≈ €190 in the cell but moves the stiffness requirement (and cost) to the storage transport; not counted in the base |
| I10 | **Taken** | Produce prep may run hours ahead (K9b batch mode); the hand is K9c's printer-class gantry at 0.8 m/s, and slower steps (lazy-susan board, mandoline strokes) are accepted |
| I11 | **Taken** | Thermo-cooker closed, oven closed, dishwasher closed, pans with splatter lids; open food only at the bay (board, sink) |
| I12 | **Rejected** | A servo gripper on bought handles saves ≈ €120 of stubs but needs a motor in the splash zone and grasps that C3 cannot verify; the stub is kept, made cheaper (folded, riveted, €4.50) |
| I13 | **Taken** | No hatch drawer: plates are set on the bay front; the bay's guard panel unlocks for serving and dish return |
| I14 | **Taken** where cheap | Oven with mechanical knobs (SSR + thermocouple), dishwasher keys by opto-couplers; the domino keeps K9b's interface board |
| I15 | **Taken** | The cell sits like a kitchen run under the transport gallery; the gantry is the cooker-hood-height rear beam |

### 1.2 The K10 principle in one paragraph

**K10 "KÜCHENGERÄT" turns the cell from a machine that contains appliances into a set of household appliances
that a small hand feeds.** Everything wet and hot happens inside closed, bought appliances (thermo-cooker,
domino under splatter lids, mini oven, dishwasher); everything cut happens in bought, dishwasher-safe gadgets
or by knife on a board; the hand (K9c's printer-class X/Y/Z gantry plus a cheap roll axis, 4 actuators) only
carries, feeds, pushes levers, stirs pans and peels on the spit. The dishwasher is the only washer and the
clean store. The kitchen furniture is the enclosure; the machine adds a glazed guard, liners and a nozzle rail.

---

## 2. Web prices checked (2026-10-01, EU shops, incl. VAT)

New checks are **Q1–Q11**; K9c's checks **P1–P27** (`K9c-design-to-cost.md` §1.3) are reused as "K9c-Pn".

| # | Item | Price found | Shop and URL |
|---|---|---|---|
| Q1 | Thermo-cooker Lidl Monsieur Cuisine Smart (recurring offer); Smart Pro; Thermomix TM7 for comparison | €399; ≈ €599; ≈ €1,499 | mydealz: <https://www.mydealz.de/magazin/monsieur-cuisine-smart-lidl-angebot-27-april-test-vergleich-61036>; <https://felixgeringswald.com/neue-lidl-kuechenmaschine-2026-kann-der-monsieur-cuisine-smart-pro-mit-dem-thermomix-mithalten/> |
| Q2 | Thermo-cooker **Cecotec Mambo 11090** (3.3 L jug, 2.3 L usable, stainless jug dishwasher-safe, scale, kneading paddle, stirring attachment, two-level steamer, app); Mambo 9590 | **€219.00**; from €254.08 | Cecotec: <https://storececotec.de/de/kuchenmaschinen/mambo-11090>; Kaufland: <https://www.kaufland.de/product/375506332/> |
| Q3 | Mini oven 25 L with convection and rotary knobs, 250 °C (Steinborg, 46.5 × 34 × 30.5 cm); Stillstern 25 L (inner 34 × 29.8 × 24 cm); Severin with convection | €69.90; €74.90; €125.99 | Kaufland: <https://www.kaufland.de/product/324143963/>, <https://www.kaufland.de/product/365774152/>; <https://www.moderne-hausfrau.de/p/severin-minibackofen-mit-umluftfunktion-6695566/> |
| Q4 | Slim 45 cm dishwasher: Midea, Bomann, Amica (9 place settings); Bauknecht with cutlery drawer | €255–303; €440–480 | billiger.de: <https://www.billiger.de/categories/3596/85863-geschirrspueler-45-cm>; MediaMarkt: <https://www.mediamarkt.de/de/content/heim-garten/kueche/geschirrspueler-45-cm-in-tests>; K9c-P13 (€269–349) |
| Q5 | Under-sink boiler 5 L, open-vented, 35–85 °C, 2 kW (Stiebel Eltron SNU 5 SL) | €149.00–151.90 | Bauhaus: <https://www.bauhaus.info/warmwasserspeicher/stiebel-eltron-kleinspeicher-snu-5-sl/p/25391293>; <https://www.heizungsdiscount24.de/durchlauferhitzer/stiebel-eltron-kleinspeicher-snu-5-sl-5-liter-20-kw-230-v-drucklos.html> |
| Q6 | Garlic press for **unpeeled** cloves and ginger, 18/10 stainless, dishwasher-safe, with scraper lever (Rösle) | €30.99–54.95 (typ. €36.50) | Geizhals: <https://geizhals.de/roesle-knoblauchpresse-20cm-12895-a1830997.html> |
| Q7 | Potato ricer and Spätzle press, Cromargan stainless, dishwasher-safe (WMF Gourmet Multipresse) | from €28.05 | testsieger.de: <https://www.testsieger.de/kochzubehoer/FA5Q11GV1WGZ9-wmf-gourmet-multipresse-265-cm-kartoffelpresse-spaetzlepresse-cromargan-edelstahl-spuelmaschinenfest.html> |
| Q8 | V-mandoline with slicing/julienne inserts and fruit holder (Börner V5 PowerLine sets); dishwasher suitability stated inconsistently by shops [U] | €44.90–64.90 | Geizhals: <https://geizhals.de/boerner-v5-powerline-set-gemuesehobel-v222232.html> |
| Q9 | Bought robot arms (payload / price): myCobot 280 0.25 kg $649; Dobot Magician V3 0.5 kg $1,899; UFactory Lite 6 0.6 kg €3,600; Dobot MG400 0.75 kg $3,780; SO-101 kit 0.5 kg ≈ €130–170 parts, $499 kit | see left | <https://shop.elephantrobotics.com/products/mycobot-worlds-smallest-and-lightest-six-axis-collaborative-robot>; <https://www.robotlab.com/store/dobot-magician-v3-standard-edition/>; <https://www.robotshop.com/products/ufactory-6-axis-robot-arm-lite-6>; <https://www.robotlab.com/store/dobot-magician-pro/>; <https://www.roboticscenter.ai/hardware/so-101> |
| Q10 | Klipper board with 4 on-board TMC2209 drivers (BTT SKR Mini E3 V3.0) | €39.90–49.99 | HTA3D: <https://www.hta3d.com/en/skr-mini-e3-v3-32-bit-board-replacement-for-ender3-ender-3-pro-ender-5-cr10> |
| Q11 | Ready ball-screw linear stage 1,000 mm with NEMA 23 (VEVOR), for comparison with a self-built axis | €257.90 | Amazon.de: <https://www.amazon.de/VEVOR-Kugelgewindetrieb-CNC-Linearf%C3%BChrungs-Tischantrieb-Graviermaschinen-CNC-Fr%C3%A4smaschinen/dp/B0G69MSFVQ> |

**Findings that move the numbers**: (1) a full thermo-cooker with scale, kneading and steamer costs **€219** —
half of K9c's hub alone (€435) and less than K9c's press cup plus S ware (€260). (2) A 25 L convection oven
costs **€70–126**, so K10 can afford the thermo-cooker inside Ben's appliance budget. (3) The two key produce
gadgets exist as stainless, dishwasher-safe household parts: an **unpeeled-garlic press** (44 garlic meals,
C1 §7) and a **ricer that is also a Spätzle press**. (4) Bought arms carry ≤ 0.75 kg below €4 k — the gantry
stays. (5) A ready ball-screw stage (€258 per metre) is dearer than K9c's self-built axis (≈ €175), so the
gantry is built as in K9c.

---

## 3. The K10 machine

### 3.1 Width (PHY-004)

| Module | Machine X | Width | Contents |
|---|---|---|---|
| Cold storage | 0–1200 | 1200 | as K9b |
| Ambient storage | 1200–1800 | **600** | K9b 650 (−50 mm) |
| **Cell** | 1800–3600 | **1800** | bay 520, domino 300, thermo-cooker 400, dishwasher 580 |
| **Total** | | **3600** | PHY-004 M met; the cell is 50 mm wider than K9b, 140 mm wider than K9c |

Below, X is **cell-local** (0 = left cell wall = machine X 1800). Height as K9b: plinth 0–100, services
100–870, deck (Gastro table) z 870, work space 870–1900, X box in the rear lane z 1900–2000, transport gallery
z 2000–2200. Depth 600; mast lane y 0–120; guard at y 580–600.

### 3.2 Front view (guard removed)

```
 z (mm)
       0     260          520          820             1220                         1800
 2200 +-------------------------------------------------------------------------------+
      |   transport gallery (storage module); ceiling port above X 0-260              |
 2000 +==== X box, rear lane y 0-120: belt, 2 rails, labyrinth; mast travel X 60-1240 ===+
      | BOX    |              | OVEN 25 L      |              | DISHWASHER slim 45 cm  |
 1855 | SHELF  |              | 340 (X) x 465  |              | as bought, turned 90°: |
      | z 1500 |  oven door   | (y) x 305      |              | door faces -X, racks   |
 1550 |--------|  swings down | door faces -X  |              | pull out along -X      |
      | TOOL   |  over 270-520+----------------+              | body X 1225-1795,      |
 1300 | CADDY  |              |  arm passes under the oven,  | y 130-580, z 1000-1850 |
      | z 1300 |              |  roll axis <= 1240           |                        |
 1060 |        |              |  ... open DW door lies here (z 1060, X 570-1220) ... |-- door hinge
 1030 |        |              |                | TM top       |                        |
  870 |[SINK][CHUTE] [BOARD on |[  DOMINO  ]    |[TM in pocket]| profile frame          | deck
      |  lazy susan / SERVE]  |  2 zones       |  180 deep    | z 870-1000             |
      | bin 20 L, drains,     | hob body,      | TM base,     | boiler 5 L 85 °C,      |
      | sink trap             | interface board| pocket drain | Pi, Klipper board, PSU |
  100 |                       |                |              | DW hoses at X 1800     |
    0 +-------------------------------------------------------------------------------+
       0                     520              820            1220                    1800
```

### 3.3 Top view at deck level (z 870)

```
 y 600 +== guard: 3 glazed panels; the bay panel (X 0-520) slides open for serving/return =========+
 y 580 | BOARD Ø 320 on a lazy  | DOMINO     | THERMO-COOKER      |                                |
       | susan (prep) = SERVE / | front Ø210 | (Cecotec Mambo     |  DISHWASHER above (z 1000+)    |
       | RETURN zone after prep | 3.4 kW     | class) 340 x 330,  |  450 (y) x 570 (X)             |
       | (2 plates or 2 GN 1/3) |            | top z ~1030, in a  |  door hinge at X 1225,         |
 y 330 |------------------------|            | drained GN pocket  |  opens over X 570-1220         |
       | SINK Ø260 | CHUTE 120  | rear Ø180  |--------------------|                                |
       | rinse cup,| x 200, flap| 2.0 kW     | LEVER SEAT: garlic |  (under it: boiler, controls,  |
       | wash bowl,| PEELER POST|            | press, ricer/Spätz-|   DW plinth)                   |
       | 4 jets    | + stab nest|            | le press, dicer    |                                |
 y 120 +------------------------+------------+--------------------+--------------------------------+
       |== mast lane y 0-120: mast 60 x 120 hangs from the X carriage; fume slot behind the domino ==|
 y 0   +-------------------------------------------------------------------------------------------+
       0          280  420     520          820                  1220                            1800
```

(The y 330 line is schematic: the cooker stands at y 250–580, the lever seat at y 130–240.)

Clearance rules [C]: the **dishwasher door** (≈ 650 mm long) opens only when domino and thermo-cooker are idle;
it lies at z ≈ 1060 over the domino and the cooker, whose top in its 180 mm pocket is at z ≈ 1030 [U: model
height]; the lever seat behind the cooker is ≤ 60 mm high when the presses are out. The **oven door** opens only
when the domino pots are lidded or empty (K9b P-8); it swings over X 270–520 at z 1550, clear of the box shelf
and caddy (X 0–260). Under the oven the arm stays at z ≤ 1540 (roll axis ≤ 1240), as in K9b. The dishwasher's
3rd-level cutlery drawer would sit at z ≈ 1750, out of reach, so a model **without** it is used (tools go into
the lower-rack cutlery basket).

### 3.4 Actuators and dynamic seals

| # | Actuator | Type [E/W] | Travel | Seal |
|---|---|---|---|---|
| 1 | X | NEMA 23 3 Nm open loop, HTD 3M-15 belt, 2 × MGN15 on a 40 × 80 beam (K9c G1–G4, 1.4 m) | 1180 (mast X 60–1240) | none: labyrinth, purged by the cell's under-pressure (K9c) |
| 2 | Z | SFU1610 ball screw, NEMA 23 with 2 Nm brake, hanging mast (K9c G5–G7) | 900 (roll axis z 700–1600) | **band 1** (stainless cover strip) |
| 3 | Y | NEMA 17, MGN12, belt in a 60 × 60 stainless arm tube on the arm-root load cell (K9c G8–G9) | 450 | **band 2** |
| 4 | Roll | NEMA 23 + 10 : 1 MG planetary in a sealed bent-stainless housing; 1.4404 output shaft through a **PTFE lip seal**; K9b's J-slot sleeve and reaction tab on a 300 mm drop link | continuous, 0–120 rpm, ≈ 12 Nm with a TMC2209 at 1.8 A | **lip seal** (K9c: canned coupling, +€90 as fallback) |

**4 motion actuators** (K9b/K9c 6), **3 dynamic seals** (K9b/K9c 2; C5 limit 5). Not counted: the appliances'
own motors and pumps (cooker, dishwasher), 3 solenoid valves, extraction fan, guard lock.

**What the hand can do** (K9c limits, lighter duty): lift ≤ 4 kg with the centre of mass ≤ 150 mm in front of
the sleeve; roll ≤ 12 Nm (pour, invert, flip the pan pair, turn the spit, close pincers); push down 300 N within
y ≤ 420 and 150 N at full reach; 0.8 m/s; weigh by loss in weight ±5 g. It cannot yaw: the board turns on a
passive lazy susan that the hand pushes by a peg, and the cooker lid is turned by an XY-arc push on a pin of a
clamped lever (K9c H-E note). Nothing heavier than the full cooker jug (≈ 3.5 kg) or a pot of pasta water
(≈ 3 kg; pasta lifted out in its basket) is lifted; soups for four are ladled or tipped from the jug.

### 3.5 Stations

| Station | Where (cell X; y) | What it is | Actuators | Fixed food contact? |
|---|---|---|---|---|
| **Sink (rinse cup)** | 20–280; y 130–330 | bought bar-sink bowl Ø 260 with basket strainer; spout cold / hot (boiler); 4 flat-fan jets 85 °C in the rim for the sleeve (K9b RC); produce washed in the pot basket under the spout; drains the deck | 0 (2 valves) | strainer (ware) |
| **Chute + peeler post** | 290–420; y 130–330 | opening 120 × 200 with spring flap to a 20 L bin; on its rear rim a **bought swivel peeler blade on a sprung bracket** and a silicone-lined stab nest: produce on the fork-spit, rolled at 30–120 rpm, traversed in Y, pressed on by Z with 5–20 N (K9b G1) | 0 | peeler (ware, to DW daily) |
| **Board / serve zone** | 20–500; y 330–580 | PE-HD board Ø 320 (red / green) on a passive lazy susan with 8 push pegs; knife cuts in the y–z plane, the hand turns the board by a peg for cross cuts; after prep the board goes to the dishwasher and the zone becomes the serving and return place behind the sliding guard panel | 0 | board (ware) |
| **Domino** | 520–820 | household 30 cm induction domino, front Ø 210 (3.4 kW boost), rear Ø 180 (2.0 kW), K9b interface board; pans with splatter lids | 0 | glass under ware |
| **Thermo-cooker** | 860–1200; y 250–580 | **Cecotec Mambo 11090 class** (Q2): 2.3 L usable, ≤ 120 °C [U], scale, blade, kneading paddle, stirring attachment, two-level steamer; in a drained GN 1/1-200 pocket so its top is ≈ z 1030; stainless funnel in the lid opening; clamp-on stubs on jug handle and lid lever; driven by K10's controller through its own power board | 0 (own motor) | jug, lid (ware, to DW after the meal) |
| **Lever seat** | 830–1210; y 130–250 | one bent stainless plate with three clamps holding the lower handle of: the **unpeeled-garlic press** (Q6), the **ricer / Spätzle press** (Q7), the **push dicer** (6 / 10 mm); the hand lifts and pushes the upper handle (≤ 150 N at 4 : 1); the press is set over a GN 1/3 or the cooker funnel | 0 | presses (ware) |
| **Mandoline** | on a GN 1/3 at the bay front | bought V-mandoline (Q8) with slicing and julienne inserts; produce on the fork-spit stroked in Y (spit stops 12 mm above the blade) | 0 | ware |
| **Oven** | 520–860; z 1550–1855 | 25 L convection mini oven (Q3), mechanical knobs fixed at max/convection, power by SSR, temperature by K10's thermocouple (its own thermostat as limiter); turned, door faces −X, opened by the hook rod; GN 1/2 and its own tray; plate warmer (stack of 4) | 0 | ware only |
| **Dishwasher** | 1225–1795; z 1000–1850 | slim 45 cm freestanding (Q4), 9 place settings, no 3rd level, hygiene / intensive programme ≥ 65–70 °C; **as bought**, turned and raised on a frame; door and racks worked by the hook rod; keys by opto-couplers | 0 (own pumps) | — |
| **Box shelf** | 0–260; y 130–330; z 1500 | the transport lowers an opened box or GN carrier through the ceiling port (K9b) | 0 | no |
| **Tool caddy** | 0–260; y 330–580; z 1300 | GN 1/1-150 with a counterweighted hinged lid and two tool racks; filled from the dishwasher before any food is opened (C2 R-6); closed during cooking | 0 | no |
| **Splash cleaning** | rear wall, side liners, deck | fixed nozzle rail (hot rinse from the boiler, detergent by venturi); deck slopes to the sink; rear fume slot behind the domino to the extraction (appliance) | 0 (1 valve) | — |
| **Camera** | X box face | one wide camera with heated window, white and UV-A LEDs (K9c C6) | — | — |

### 3.6 How a meal runs (phases fixed by the dishwasher door)

| Phase | What happens | Dishwasher door |
|---|---|---|
| P0 Take-out | door open, racks out; all ware for the menu is taken out **before any food is opened**: tools to the caddy, pans and pots onto the domino or deck, GN and plates into the cold oven; racks in, door shut | open |
| P1 Prep (may run hours ahead, I10) | boxes via the box shelf; produce washed (sink), peeled (spit + peeler post), cut (board and knife, mandoline, push dicer, presses, cooker chop); **ready-to-eat items first on green ware, raw items last on red ware**; cut items in lidded GN 1/3 into the cold oven or back to cold storage | shut |
| P2 Prep ware away | domino idle: door open, prep ware loaded (board, knives, gadgets, peeler); door shut; for 4 persons this first load may run during cooking | open |
| P3 Cook | domino (pans under splatter lids, pot with basket), cooker (sauces, risotto, stirring, steaming, kneading), oven; the cooker jug is boil-cleaned in place between a raw and a ready-to-eat use (§6) | shut |
| P4 Serve | plates warm from the oven to the serve zone (plate cradle); components by ladle, turner, tongs; family style: 2–3 GN 1/3 serving dishes; the bay guard panel unlocks | shut |
| P5 Return and wash | diners put plates on the serve zone; panel locks; scraps over the chute (roll 180°); cooker boil-cleaned, jug and lid to the rack; plates, pans, GN, tools loaded; door shut; hygiene programme; nozzle rail rinses bay, walls and pocket; everything stays in the dishwasher as the **clean store** | open, then shut |

**Example**, Spaghetti Bolognese and cucumber salad for 4 [E]: P0 3 min; P1 cucumber peeled on the spit and
sliced on the mandoline (2 min), dressing in the cooker (1 min, then rinse-boil 3 min), carrot and celery peeled
(3 min) and chopped with onion in the cooker (10 s), garlic pressed in skin (1 min); P2 2 min; P3 mince seared
on the front zone in two batches (12 min), vegetables, tomatoes and simmer moved to the cooker jug (≤ 2.3 L,
45 min, stirred by the cooker), pasta water to the boil on the front zone from the 85 °C boiler (4 min), pasta
in the basket (10 min); P4 4 plates 4 min. Total ≈ 80 min from start, of which ≈ 40 min hand time — ≈ 15 min
longer than K9b [E], mainly from the single cooker jug and the slower hand.

---

## 4. Bill of materials of the K10 cell (one unit, EU retail incl. VAT, own labour not counted)

Cat.: **b** maker-market or hardware part, **job** job-shop stainless, **a** bought household item used as is,
**c** 3D print in the dry zone (#4). "K9c-Gn" etc. = the same line as in K9c §5.1.

### 4.1 Machine part

| # | Item | Qty | € each | € total | Cat. | Source |
|---|---|---|---|---|---|---|
| H1 | X beam, aluminium profile 40 × 80, 1.4 m | 1 | 30 | 30 | b | K9c-P1 [W] |
| H2 | X rails MGN15, 1.4 m, two blocks each | 2 | 58 | 115 | b | K9c-G2 pro rata [E] |
| H3 | X belt HTD 3M-15 3 m, pulleys, idler, tensioner | 1 | 45 | 45 | b | K9c-P3 [W] + [E] |
| H4 | X motor NEMA 23, 3 Nm | 1 | 25 | 25 | b | K9c-P4 [W] |
| H5 | Z ball screw SFU1610 ≈ 1 m, BK/BF12, nut housing, coupling | 1 | 60 | 60 | b | K9c-P7 [W] |
| H6 | Z motor NEMA 23 with 2 Nm brake | 1 | 45 | 45 | b | K9c-P5 [W] |
| H7 | Mast: profile 40 × 80 × 1.1 m, MGN15 1 m, bent stainless cover | 1 | 70 | 70 | b, job | K9c-G7 |
| H8 | Y: NEMA 17, MGN12 0.6 m, belt, pulleys | 1 | 60 | 60 | b | K9c-G8 |
| H9 | Arm tube stainless 60 × 60 × 620 with end plates | 1 | 40 | 40 | job | K9c-G9 |
| H10 | Sealing bands (stainless cover strip on magnetic strip) | 2 | 25 | 50 | b | K9c-G10 |
| H11 | X labyrinth lips, 1.4 m | 1 | 20 | 20 | job | K9c-G11 pro rata |
| H12 | Carriage plates (laser-cut aluminium), printed brackets | 1 | 40 | 40 | b, c | K9c-G12 |
| | **Gantry** | | | **600** | | K9c 640 |
| H13 | Roll motor NEMA 23 + 10 : 1 MG planetary | 1 | 35 | 35 | b | K9c-P6 [W] |
| H14 | Roll housing (bent 1.4404, O-ring static seals), PTFE lip seal, 1.4404 output shaft | 1 | 40 | 40 | job, b | [E] |
| H15 | Sleeve with J-slots, reaction tab, 300 mm drop link | 1 | 35 | 35 | job | K9c-R3/R4 without Hall sensors |
| H16 | Arm-root load cell 30 kg + 24-bit ADC (weighing and collision) | 1 | 25 | 25 | b | K9c-P12 [W] |
| | **Hand total** | | | **735** | | K9c 825 + 25 |
| C1 | Klipper board with 4 on-board TMC2209 (BTT SKR Mini E3 V3) | 1 | 40 | 40 | b | Q10 [W] |
| C2 | Raspberry Pi 5 4 GB + endurance storage, read-only root | 1 | 135 | 135 | b | K9c-P10 [W] + [E] |
| C3 | Camera Module 3 Wide, heated window, white + UV-A LEDs | 1 | 55 | 55 | b | K9c-P11 [W] + [E] |
| C4 | PSUs 24 V 200 W + 5 V 5 A | 1 | 40 | 40 | b | [E] |
| C5 | Domino interface board (COK-023) | 1 | 60 | 60 | b | K9b [D] (K9c: appliance side) |
| C6 | Thermo-cooker interface: its UI board bypassed, motor speed and direction, heater, NTC and lid switch driven by K10's controller | 1 | 40 | 40 | b | [E/U] (R1) |
| C7 | Oven: 25 A SSR, K thermocouple, MAX31855 | 1 | 30 | 30 | b | [E] |
| C8 | Dishwasher keys by opto-couplers, door-state input; boiler relay | 1 | 15 | 15 | b | [E] |
| C9 | Load shedding: 3 current sensors, 2 relays | 1 | 35 | 35 | b | [E] (K9c-C7 €70) |
| C10 | Safety: household door lock on the sliding panel, reed contacts on all panels, 2 force-guided relays | 1 | 50 | 50 | a, b | K9c-P21 [W] + [E] |
| C11 | Cable chains, cables, connectors | 1 | 60 | 60 | b | [E] |
| | **Controls and appliance interfaces** | | | **560** | | K9c 633 + 160 interfaces on its appliance side |
| E1 | Guard: 1 sliding glazed panel (bay) + 2 fixed glazed service panels, top track | 1 | 120 | 120 | b | [E] (K9c-E8 €130 for 2) |
| E2 | Side liners 1.0 mm stainless to z 1450, bent rear gutter | 1 | 70 | 70 | job | K9c-P18 [W] + [E] |
| E3 | Top panel with ceiling port, X-beam brackets on the carcass | 1 | 50 | 50 | b | [E] |
| E4 | Dishwasher frame (profile, z 870–1000) and room-side cover panel | 1 | 45 | 45 | b | [E] |
| E5 | Shelves: oven, box shelf, caddy | 1 | 35 | 35 | b, job | [E] |
| E6 | Deck job work: domino, sink and chute cut-outs; cooker pocket from a welded-in GN 1/1-200 with drain | 1 | 110 | 110 | job | [E] |
| E7 | Chute with spring flap | 1 | 35 | 35 | job | K9c-RC4 |
| | **Enclosure beyond kitchen furniture** | | | **465** | | K9c 1,280 − 420 furniture = 860 |
| W1 | Bar-sink bowl Ø 260 + basket strainer | 1 | 35 | 35 | a | K9c-RC1 |
| W2 | Spout + flow meter | 1 | 15 | 15 | b | K9c-RC3 |
| W3 | Four flat-fan jets (sleeve rinse, 85 °C) | 1 | 15 | 15 | b | K9c-RC2 |
| W4 | Solenoid valves: 2 hot-rated (jets, nozzle rail), 1 cold (spout) | 3 | 35 | 105 | b | K9c-P19 [W] |
| W5 | Nozzle rail | 1 | 40 | 40 | b | K9c-V3 |
| W6 | Piping, hoses, fittings | 1 | 40 | 40 | b | [E] |
| | **Water** | | | **250** | | K9c water + rinse cup + well 525 |
| WA1 | Bayonet stubs, laser-cut and folded 1.4404, riveted (K9c R2-3), on ≈ 40 items | 40 | 4.5 | 180 | job | [E] |
| WA2 | Pan-pair hook tab and catch | 1 | 20 | 20 | job | [E] |
| WA3 | Peeler post: bought swivel peeler on a sprung bracket, silicone stab nest | 1 | 30 | 30 | job, a | [E] |
| WA4 | Lever seat for the three presses | 1 | 35 | 35 | job | [E] |
| WA5 | Egg fixture (K9b design) | 1 | 40 | 40 | job | [E] |
| WA6 | Rouladen comb cradle + 2 raft forks | 1 | 40 | 40 | job | [E] |
| WA7 | Carving trough with gauge plate | 1 | 35 | 35 | job | [E] |
| WA8 | Fork-spit (bought carving fork, shortened, stub) | 1 | 15 | 15 | a, job | [E] |
| WA9 | Plate cradle, hook rod, scraper-squeegee | 1 | 30 | 30 | job | [E] |
| WA10 | Cooker lid funnel, clamp-on stubs for jug handle and lid lever | 1 | 25 | 25 | job | [E] |
| WA11 | Tool caddy: GN 1/1-150, counterweighted hinged lid, 2 tool racks | 1 | 40 | 40 | a, job | [E] |
| WA12 | Lazy susan: stainless bearing ring, locating and push pegs | 1 | 20 | 20 | b, job | [E] |
| | **Machine ware** | | | **510** | | K9c 1,010 |
| | **MACHINE PART K10 cell** | | | **2,520** | | |

Blocks: hand 735 (29 %), controls 560 (22 %), ware 510 (20 %), enclosure 465 (18 %), water 250 (10 %).
Custom part types ≈ 18 [E] (K9c ≈ 28): no hub, no press cup, no well tub, no canned coupling, no tool cabinet.

### 4.2 Bought kitchen gadgets (household kitchen content, e1, customer decision as in K9c)

| Item | € | Source |
|---|---|---|
| Ricer and Spätzle press (WMF Gourmet Multipresse) | 28 | Q7 [W] |
| Garlic press for unpeeled cloves (Rösle) | 37 | Q6 [W] |
| V-mandoline set with julienne insert (Börner V5) | 60 | Q8 [W] |
| Push dicer with 6 and 10 mm grids and container | 30 | [E] |
| Pump salad spinner | 30 | [E] |
| Swivel peelers (spares), apple and pepper corers, plunger pitter | 35 | [E] |
| Ravioli mould, dumpling press, rolling pin with gauge rings | 35 | [E] |
| Wireless core probe | 40 | [E] |
| **Gadgets** | **295** | (they replace K9c's press cup €150, S ware €110 and bought tools €90) |

Ordinary kitchen content (pans, pots, lids, GN, tins, knives, boards, utensils) as K9c §5.2 without kneading bowl
and spinner basket, plus the duplicates of I4 (second board, knife, tongs, two GN 1/3): **≈ €400** (K9c €375).
Kitchen furniture (e2): Gastro work table 1800 × 600 with upstand as the deck (K9c-P15), stainless rear
splash-back to z 1450, under-deck fronts, bin pull-out: **≈ €380**.

### 4.3 Appliances of the cell

| Appliance | € | Note |
|---|---|---|
| Induction domino 2 zones | 300 | K9b [D]; interface board in the machine part |
| Countertop convection oven 25 L | 130 | Q3 [W] (€70–126); Ben's list had €500 |
| Slim 45 cm dishwasher without 3rd level, hygiene programme | 350 | Q4 [W] (€255–440) |
| 5 L under-sink boiler 85 °C | 150 | Q5 [W]; replaces K9c's 30 L store (€200) |
| Hob-extractor fan with baffle filter | 150 | K9b [D] |
| **Thermo-cooker** (Cecotec Mambo 11090 class) | 219 | Q2 [W] — a household appliance; shown both ways in 4.4 |
| **Cell appliances** | **1,299** | K9c's cell appliances 1,810 (domino + interface, combi-steam oven + interface, dishwasher, 30 L store, extractor) |

With fridge + freezer (€1,000) and shelving (€500–1,000) as in #28, the appliances total **≈ €2,800–3,300** —
inside Ben's €3,000–3,500 although the thermo-cooker is included, because the mini oven and the small boiler are
cheaper than the oven and 30 L store of K9b/K9c.

### 4.4 Totals, shown four ways (cell only; storage handling see §7)

| Accounting | K9c | **K10** |
|---|---|---|
| (1) Machine part as defined for this round: thermo-cooker as household appliance, gadgets and kitchen content as household, furniture outside | — | **2,520** |
| (2) Thermo-cooker counted as machine part — **like-for-like with K9c's €4,313** (hub in the machine part, kitchen content and furniture outside) | 4,313 | **2,739** (−37 %) |
| (3) (2) + bought gadgets as machine part | 4,313 | 3,034 |
| (4) K9b accounting: (3) + kitchen content + furniture | 5,108 | 3,814 |

Where the €1,574 of row (2) come from (K9c blocks net of furniture → K10) [C]: machine ware 1,010 → 510
(−€500: no press cup, no S ware, gadgets bought, folded stubs, fewer fixtures); enclosure 860 → 430 (−€430:
furniture is the enclosure, caddy instead of tool cabinet; the cooker pocket is inside); well, water, rinse cup
and chute 525 → 285 (−€240: the dishwasher as bought); hub 435 → thermo-cooker 219 (−€216; its interface,
pocket, funnel and lever seat sit in the other blocks); hand 850 → 735 (−€115: shorter X, lip-sealed roll);
controls 633 → 560 (−€73, although K10 carries all appliance interfaces that K9c put on its appliance side).

---

## 5. Coverage (C1 standard N, 248 rows, 8 excluded by requirements 5.4)

Starting point: K9b central 233 (K9b §7.2; K9c unchanged). Each K10 change against K9b:

| Change | Meals | Note |
|---|---|---|
| Heated hub with stirring, S (blend, chop), kneading roller → **thermo-cooker** | 0 lost | risotto IT09, polenta IT14, béchamel SC01, vanilla sauce SC05, hollandaise (SD19), mayonnaise SC04, mousse DS07 rise from M to **H** (closed, stirred, temperature-held); soups for 4 cooked in the 5 L pot and blended in two batches |
| Press-cup dice → cooker chop for cooked dishes (onion, carrot, celery, garlic paste), push dicer for soft visible dice, knife cubes for raw potato and roots | 0 lost | cooker-chopped soffritto is common household practice; **#27 check** in R5; knife cubes take ≈ 5 min/kg |
| S discs → **mandoline with the fork-spit** as holder (slices 1.5–7 mm, julienne) | 0 lost | SD05 Kartoffelpuffer from fine julienne instead of a fine grate: **at risk** (low end) |
| Press-peel and mash in the **bought ricer** (piston from above, skin side up) | 0 lost | same principle as K9b G2; CK16 banana bread stays M, at risk in the low end |
| Avocado halved round the stone by **turning it on the spit** against a fixed blade (K9b turned the board on T) | **−1** | MX06 guacamole M → L–M: out in central, in at the high end |
| Garlic pressed in the skin in a press **made for unpeeled cloves** | 0 | the 44 garlic meals (C1 §7) stay H |
| Board turned by a passive lazy susan | 0 | +1–2 min per meal |
| 25 L convection oven instead of a combi-steam oven | 0 lost | sheet cakes (CK04, CK15), pizza for 4 (IT10), cookies (CK09) in 2 batches, +10–20 min; bread (BK01, BK03, BK05) with a water tray for steam; yeast dumplings DS11 in the cooker's steamer |
| Kneading ≤ ≈ 500–800 g flour per batch [U] (K9b 1.6 kg) | 0 lost | bread and pizza for 4 in 1–2 batches |
| No washing during the meal (duplicates, cooker boil-clean) | 0 lost | |
| Rolling pasta and ravioli sheets under K9c's push limits | 0 | IT17, DM33 unchanged at M (as K9c) |
| **Central** | **232 = 93.5 %** (range 229–235) | target 231: **reserve 1** (K9b 2). Out as K9b: AS08, IN07, CK12; at risk as K9b: DM12, AS09; new: MX06 out in central; low end also CK16, SD05, IT17 |

Hand time per 4-person meal is ≈ 10–20 min longer than K9b [E] (single jug, slower hand, lazy susan,
mandoline strokes, oven batches); produce prep can move hours ahead (P1), so the delay is felt mainly for
spontaneous meals. To be confirmed in K9b's E0 simulation with K10's station times.

---

## 6. Hygiene concept

| Rule (C2) | How K10 meets it |
|---|---|
| **No human cleaning** of food-contact parts | every ware item, gadget, the cooker jug and lid go into the dishwasher after every meal; the deck, side liners, rear splash-back and cooker pocket are rinsed by the fixed nozzle rail (hot water from the boiler, detergent by venturi) and drain to the sink; the human empties the bin and refills salt and detergent (household dishwasher practice). Inherited exception (K9b Q12): a soiled oven cavity; reduced by roasting in lidded GN |
| **Disinfection** | dishwasher hygiene/intensive programme, final rinse ≥ 65–70 °C, validated with loggers on the coldest item; target **A0 ≥ 60** (70 °C held ≥ 10 min) — **below K9b's A0 ≥ 90 at 82 °C**: a C2 decision; fallback a model with a longer 70 °C hygiene rinse (A0 ≥ 90 needs ≈ 15 min at 70 °C) [U]. **Cooker jug, blade and lid underside: boil-clean in place** (water + detergent at ≈ 100 °C, high speed, 3 min: A0 ≫ 600) between a raw and a ready-to-eat use. **Sleeve and reaction tab**: 85 °C jets 3–10 s after every soiled grip (K9b software interlock) |
| **Raw / ready-to-eat separation** | by **items** (red and green boards, knives, tongs, GN; no turnaround wash in the meal), by **sequence** (in P1 ready-to-eat produce first, raw items last; raw meat never leaves its GN except into the hot pan), by **time and place** (raw work only in P1; the nozzle rail rinses the bay before it becomes the serve zone in P4) and by the cooker's boil-clean |
| **Clean store** | the closed, dried dishwasher holds all ware between meals; everything a menu needs is taken out in P0 **before any food is opened** (C2 R-6); tools wait in the closed caddy, GN and plates in the cold oven |
| **Dirty items** | prep ware into the dishwasher in P2, before cooking; dishes and cooking ware only in P5; nothing soiled ever stands above or beside clean items for longer than the step it is used in |
| **Splash at the source** | cooker closed, pans with splatter lids, oven and dishwasher closed; open food only at the bay (board, sink, chute) |
| **Materials** (#4) | food contact only stainless, PE-HD boards, the gadgets' and the cooker's moulded food-grade plastics; FDM parts only in the dry X box |
| **Dynamic seals in the splash zone** | 3 (2 bands as K9b, + the roll lip seal: rinsed with the sleeve; riboflavin soak test R6; fallback K9c's canned coupling +€90) |
| **Storage boxes** | lidded in storage, opened at the bay (§7) |

---

## 7. The whole machine: one rail for storage and cooking (K10-W)

### 7.1 Why the cell alone is the wrong question

Ben's €2 k is for the **whole** machine part including storage handling. The storage round
(`design/storage/10-storage-comparison.md` §0, §4.5, §6) chose an S4 aisle shuttle (ambient), two S1 stack
robots behind C1-B top-wall hatches (fridge, freezer) and a gallery over everything: machine part **≈ €3,800 +
€635 access**, structure ≈ €1,250, and the gallery (one X axis, hoist, passive gripper) is **not counted** there
(≈ €500 [E]). That is 4 robots and ≈ 10 motors before a single meal is cooked. Storage + K10 cell ≈ €7.5 k;
storage + K9c cell ≈ €9.3 k.

K10-W removes the storage robots and the gallery: **the cell's X axis runs the whole 3.6 m**, and storage becomes
**top-access stacks** (the S1 principle, already rated "good" for the cold shells) that a hoist digs from above.
The storage round's box standard (stubless GN 1/6 and 1/9, flat lids, passive toggle gripper on the long-side
rims, stub carrier on the box shelf) is kept unchanged.

### 7.2 Two variants

* **K10-W1 — one carriage.** The hand gets a **5th motor: a hoist** (NEMA 17 spool, Dyneema line, the storage
  round's passive toggle gripper) beside the drop link. Over storage the arm runs at z ≈ 1900–2000, and because
  the roll unit hangs 300–400 mm below the arm, **the storage modules must end at z ≈ 1350**: 122–140 cm built-in
  fridge and freezer and a 1.35 m ambient column, each with its top opened to the hoist. Capacity [E]: freezer
  2 × 2 stacks ≈ 24 (as the storage round), fridge 2 × 2 ≈ 30–32 (storage round 38–45; #17 lets non-cooking
  chilled goods move to an ordinary fridge), ambient 3 × 3 stacks ≈ 80–90 lidded (S1 113 at 2 m).
  Storage moves load the cooking hand: ≈ 20–25 boxes × ≈ 20 s per 4-person meal, done before cooking.
* **K10-W2 — two carriages on one rail pair.** The rails and beam run 3.6 m as in W1, but storage gets its own
  small carriage (X belt, short Y, hoist, toggle gripper: 3 motors ≈ €300) that parks over storage and hands
  boxes to the cell's box shelf. Storage modules keep the storage round's full height and capacity; storage
  moves run in parallel with cooking. This is the gallery made cheap: it shares the cell's beam and rails and
  replaces the three in-store robots by digging from above.

```
 K10-W1, front view (fronts removed)
 z    X 0           600          1200         1800                                     3600
 2200 +---------------------------------------------------------------------------------+
      |== X box, rear lane y 0-120, ONE carriage over 3.6 m: mast, arm, roll, hoist ======|
 2000 +---------------------------------------------------------------------------------+
      |  arm corridor over storage (arm z 1900-2000, roll unit and hoist parked above   |
      |  z 1450); hoist dips through the open tops                                      |
 1350 +--[HATCH]-----+--[HATCH]-----+--[OPEN TOP]-+                                     |
      | FREEZER      | FRIDGE       | AMBIENT      |  K10 CELL (§3)                      |
      | 122-140 cm   | 122-140 cm   | 3 x 3 stacks |  bay | domino + oven | cooker |       |
      | built-in,    | built-in,    | GN 1/6, 1/9  |  dishwasher (raised)               |
      | top wall cut | top wall cut | lidded boxes |                                     |
      | to a lid,    | to a lid,    | human door   |                                     |
      | 2 x 2 stacks | 2 x 2 stacks | in front     |                                     |
  120 +--------------+--------------+--------------+                                     |
    0 +---------------------------------------------------------------------------------+
        ≈ 24 boxes     ≈ 30-32        ≈ 80-90       (W2: full-height modules as the
                                                     storage round, own storage carriage)
```

Hatches: the top wall of each cold shell is cut to a lid over the whole interior (C1-B's window enlarged so
that the hoist reaches all four stacks), on a magnetic gasket, spring-closed, **latched open by a €10 solenoid
that releases on power loss**; the hand opens it with the hook rod — no hatch motor (C1-B had one per shell). The
OEM doors stay for the human. Lids of the boxes are lifted at the bay by a suction-cup stem tool and parked in a
lid rack (the storage round's lid station, done by the hand).

### 7.3 Storage add-on BOM (machine part)

| # | Item | W1 € | W2 € | Source |
|---|---|---|---|---|
| S1 | X extension 1.4 → 3.5 m: profile, 2 × MGN15, belt, cable chain, dry X-box cover over storage (no labyrinth there) | 260 | 260 | K9c-P1/P2/P3 pro rata [E] |
| S2 | Longer Z (+100 mm) and taller mast cover | 10 | — | [E] |
| S3 | Hoist on the arm: NEMA 17 spool, Dyneema line, guide, passive toggle gripper (storage round §5.3) | 90 | — | [E] |
| S4 | Storage carriage: second X belt loop and NEMA 23, short Y (MGN12, NEMA 17), hoist, toggle gripper, plates | — | 300 | [E] |
| S5 | Controller with 5 (W1) or 8 (W2) drivers instead of 4 (BTT Manta class) | 5 | 45 | Q10, K9c-P10 range [W/E] |
| S6 | Cold hatches: top wall cut to a full lid, frame, magnetic gasket, freezer seat heater, spring, solenoid latch (2 shells) | 260 | 260 | [E] (C1-B €300–335 per shell with motor) |
| S7 | Stack guides in both cold shells (bent stainless or PP rails) | 100 | 100 | storage round "structure" €150 per shell, part [E] |
| S8 | Box-lid handling: suction-cup stem tool with a mini pump, lid rack for ≈ 25 lids | 75 | 75 | [E] |
| S9 | Temperature loggers in all stores, box DataMatrix read by the cell camera / a second camera over storage | 20 | 60 | [E] |
| | **Storage handling, machine part** | **820** | **1,100** | storage round: **4,435** + gallery ≈ 500 |

Structure (ambient column carcass and stack grids, cold-shell plinths) ≈ €700 (W1) / ≈ €900 (W2) on Ben's
"shelving" appliance line (storage round €1,250). Boxes ≈ €2,000 as in the storage round.

### 7.4 Whole machine compared

| Whole machine | Storage handling | Cell | **Machine part** | Width | Main loss against the storage round |
|---|---|---|---|---|---|
| Storage round + K9c cell | 4,435 + ≈ 500 gallery | 4,313 | **≈ 9,250** | 3,600 | — |
| Storage round + K10 cell | ≈ 4,935 | 2,520 | **≈ 7,450** | 3,650 | (ambient 600 instead of 650) |
| Storage round with its own levers (lean robots −€750, no cool section −€350) + K10 cell | ≈ 3,835 | 2,520 | ≈ 6,350 | 3,650 | cool section |
| **K10-W2** (two carriages, one rail) | 1,100 | 2,520 − 35 (box shelf/port now shared) | **≈ 3,585** | 3,600 | S4's 4–6 s random retrieval becomes dig-from-top (≈ 15–20 s for a top box, minutes for a deep one unless pre-dug from the menu plan); human access to deep boxes by unstacking |
| **K10-W1** (one carriage + hoist) | 820 | 2,485 | **≈ 3,305** | 3,600 | as W2, plus: 122–140 cm cold shells (fridge ≈ 30–32 boxes), storage moves on the cooking hand (+≈ 8 min hand time per 4-person meal, before cooking), one hand is a single point of failure for everything |
| K10-W1 + the cell cuts of §8 (K10-L) | 820 | 2,215 | **≈ 3,035** | 3,600 | + the K10-L risks (§8) |

Not counted anywhere yet (as in the storage round): **ingestion** (#3, #7: scanning, decanting, package
opening). It needs a hand-over place reachable by the hoist; the hand of K10-W could also serve it.

**Requirements K10-W touches** [U, for the storage critics]: STO-003 (≤ 30 s) holds only with menu-based
pre-digging (S1's weakness, now in all three stores); CAP-024 cool zone (8–15 °C) is dropped or placed in the
fridge's warmest level; frost and energy from the larger cold hatches during digging (each move ≈ 15–20 s open)
must be measured; the human reaches top boxes through the OEM doors, deep ones by unstacking.

---

## 8. The €2 k question, answered honestly

### 8.1 Further cuts on the cell (K10-L)

| # | Cut | Saves | Coverage | What it costs |
|---|---|---|---|---|
| L1 | BTT CB1 compute module (€41) instead of the Raspberry Pi 5 | 95 | 0 | still-image colour checks only (peel residue, egg shell, plate); K9c R2-2 |
| L2 | No arm-root load cell: weighing on the cooker's scale (items set on its closed lid), collisions by TMC2209 stall detection | 25 | 0 | no mass check of each grip (C3), camera only |
| L3 | No load-shedding hardware: each appliance on its own phase, software scheduling | 35 | 0 | a breaker can trip if the scheduler errs |
| L4 | Bought lever egg cracker in the lever seat instead of the custom egg fixture | 28 | 0 [U] | shell fragments; the per-egg camera check stays |
| L5 | Cold-rated valve for the nozzle rail (≤ 60 °C water) | 30 | 0 | no hot final rinse of the walls |
| L6 | Polycarbonate instead of glass panels | 30 | 0 | scratches; keep ≥ 150 mm from the oven door |
| L7 | Stubs on 34 instead of 40 items (no slicer knife, one lid, no 3 L pot) | 27 | 0 | fewer parallel pots for 4 persons |
| | **K10-L** (L1–L7) | **270** | **232 = 93.5 %** | cell **€2,250** |
| L8 | No Rouladen cradle and raft forks | 40 | **−1** (DM02, W3, named in the brief) | **231 = 93.1 %, reserve 0**; cell €2,210 |
| L9 | The cell's X axis booked to the whole-machine rail (K10-W) | 235 | 0 | accounting inside the whole machine only |

### 8.2 Results

| Question | Answer |
|---|---|
| Cheapest **cell** at ≥ 93 % | **K10-L ≈ €2,250 at 232 (93.5 %)**; ≈ €2,210 at 231 (93.1 %, no reserve). Like-for-like with K9c's €4,313 (cooker inside): ≈ €2,470 |
| Cheapest **cell** at ≈ €2,000 | **≈ €1,975 at 231 (93.1 %)** only when its X axis is counted in the whole-machine rail (L9); a stand-alone cell at €2,000 was not found above ≈ 91 % [E: further cuts would be the carving trough (−3…−6 roast meals) or one hob position (COK-002)] |
| Cheapest **whole machine** at ≥ 93 % (automatic storage) | **K10-W1 + K10-L ≈ €3,035** at one-unit prices (122–140 cm cold shells, fridge ≈ 30–32 boxes); **K10-W2 + K10-L ≈ €3,315** with full storage capacity. In a series of ≥ 50 (job-shop and maker-market parts −25…−30 %) ≈ **€2.2–2.4 k** [E] |
| **Whole machine** at €2,000 | **Not reachable with automatic storage.** The hand (735), controls (560) and storage handling (820) alone cost **€2,115**. What €2 k would buy: the K10-L cell with the household stocking a daily meal shelf from an ordinary fridge and pantry (brief violated, coverage unchanged), or K10-W1 without the roll axis and its generic peeling (−€155 only; #25 violated; ≈ 208–218 meals = 84–88 % [E]) — neither is worth building |
| Does K9c's conclusion stand? | **Partly refuted.** K9c said K9b's function set cannot go below ≈ €3.3–3.8 k (cell, round 2). K10 keeps that function set (and 232 meals) at **≈ €2.25–2.5 k** by changing the principle (bought thermo-cooker, dishwasher as the washer, furniture as the enclosure), not by cheaper parts. The gantry was **not** the cost problem (€600); the custom wet cell and the custom hub were. Its other conclusion — no gantry-free machine at 93 % — stands: bought arms carry ≤ 0.75 kg below €4 k |

**The honest number for Ben**: the whole machine part (storage handling + cooking + controls) is **≈ €3.0–3.3 k**
at one-unit prices with K10-W, against **≈ €7.5–9.3 k** with the storage round's robots. €2 k is ≈ 1.5 × short
of that one-unit floor, and is reachable only in a small series.

---

## 9. What is worse than K9b, and would Ben accept it?

| # | Worse than K9b | Severity | Ben's likely view [E] |
|---|---|---|---|
| W1 | **No washing during a meal**: disinfecting household programmes take 1.5–2.5 h; a 4-person meal needs 2 loads, all clean ≈ 3–5 h after hand-over (PERF-005 M 90 min **fails**); a second meal within 2 h needs the duplicate set | medium | likely yes: #6 asked that the machine washes, not how fast; a 2-person household rarely cooks twice in 2 h |
| W2 | **Disinfection at 65–70 °C** (A0 ≈ 60) instead of 82 °C (A0 ≥ 90) | medium (C2) | yes if C2 accepts household-dishwasher practice; a hygiene-option model is the fallback |
| W3 | **Thermo-cooker as the third hot position**: ≤ 120 °C, 2.3 L, one jug (serial use), kneading ≤ ≈ 0.5–0.8 kg flour | low–medium | likely yes; it also makes risotto, sauces and emulsions better. A spare jug (≈ €60) is the option |
| W4 | **25 L mini oven** instead of a combi-steam oven: no steam programmes, GN 1/2 trays, sheet cakes and pizza for 4 in 2 batches | low–medium | may want a better oven: any countertop oven ≤ 465 mm wide fits, inside his €500 oven budget |
| W5 | **Cooker-chopped** onions and soffritto in cooked dishes; mandoline slices instead of processor discs | low (#27 check) | likely yes for sauces; a blind test (R5) decides |
| W6 | **Slower**: +10–20 min per 4-person meal (+≈ 8 min more in K10-W1 for storage moves) | low | yes if prep runs ahead |
| W7 | **Reserve of 1 meal** above 93 % (K9b 2) | medium | Ben accepted 93 %; K10-L with L8 has none |
| W8 | **3 dynamic seals** (roll lip seal) instead of 2 | low | — |
| W9 | **Unusual installation**: the dishwasher raised and turned 90°; it blocks the domino and cooker while its door is open, so cooking and dishwasher access are strictly phased | low | yes (it is still a dishwasher as bought) |
| W10 | **Serving through a guard panel** on the bay instead of a heated hatch drawer; plates are warm from the oven, but the diner reaches ≈ 250 mm into the cell (K9b CC8, SRV-010) | low–medium | probably yes |
| W11 | **Hobby-grade electronics and appliance hacks** (Klipper board, Raspberry Pi, a consumer cooker's power board driven by K10) | medium | as K9c Q5; the cooker interface is the new risk (R1) |
| W12 | K10-W only: **dig-from-top storage** (STO-003 needs pre-digging), smaller cold shells (W1), one hand for everything (W1) | medium | the price of €3 k instead of €7.5 k — likely yes, since he asked for €2 k |

**Overall**: K10 keeps K9b's coverage within one meal, its hygiene rules (with W2 as a C2 question) and its
produce skills, and is closer to what Ben described in #28 — ordinary household appliances used largely as
bought, plus a modest machine. The main thing he may not accept is the remaining gap: ≈ €3 k for the whole
machine part, not €2 k.

---

## 10. Risks and the cheapest tests

| # | Risk | Cheapest test | Cost, time | Fallback |
|---|---|---|---|---|
| R1 | **Thermo-cooker cannot be driven** by K10 (closed protocol; touch UI; lid lock; safety cut-outs) | buy a Mambo 11090; first try its app interface (cloud or local?), then open it: map UI ↔ power-board signals, drive motor speed, direction and heater from a Pi; check the lid-switch chain stays hard-wired | €219 (the unit is re-used), 1 week | opto-couplers on its keys with camera read-back of the display; or a Monsieur Cuisine (€399) / a clone with knob controls |
| R2 | **Hand cannot work the cooker**: lid twist-lock by an XY arc, funnel feeding, lifting a 3.5 kg jug by a clamp stub, ladling | wooden mock-up of arm and sleeve on a drill-press stand; real cooker; 50 cycles | €60, 2 days | lid left locked and fed only through the funnel; ladle out instead of lifting the jug |
| R3 | **Dishwasher as bought, turned and raised**: door (latch force, counterbalance) and racks by the hook rod; rack runner life ≥ 3,000 cycles; plate tines and on-edge GN at the hand's angles; hygiene programme A0 with loggers on the coldest item; upper-rack reach | €300 slim dishwasher on a frame; hand-held hook rod with a force gauge; 3,000 rack cycles by a cheap linear actuator; 5 logged runs | €400, 1 week (dishwasher re-used) | a model with a hygiene option (+€100); C2 ruling on A0 |
| R4 | **Gadgets worked by the gantry**: unpeeled-garlic press (skin ejection, residue), ricer press-peel of avocado, banana, mango, Spätzle; push dicer forces on onion, cucumber, cooked potato; mandoline with the spit (end waste, 1.5 mm cucumber) | by hand with a force gauge and a lever seat of plywood; 10 items each; weigh waste | €200 (gadgets re-used), 3 days | K9b's press cup on the lever seat (+€150) |
| R5 | **#27 texture**: cooker-chopped soffritto, mandoline julienne Rösti and Kartoffelpuffer against a knife and grater reference | blind tasting with 6 people, 3 dishes | €30, 1 day | push dicer and knife for all visible dice |
| R6 | **Roll lip seal** collects soil (C2) | riboflavin soak of a sealed housing with a turning shaft, 85 °C jet rinse, UV check, 500 cycles | €40, 1 week | K9c's canned coupling (+€90) |
| R7 | **Cooker boil-clean** as raw → ready-to-eat disinfection | ATP swabs and riboflavin on jug, blade and lid after raw mince; logger in the jug | €60, 1 day | second jug (+€60), raw uses only at the end of a meal |
| R8 | **Coverage claim** (232) | walk the 248 corpus rows with K10's route table under C1 standard N; desk | €0, 2 days | — |
| R9 | **Mini-oven food result** (bread, pizza, roast, sheet cake in 2 batches) and its fit (≤ 465 mm along y) | buy the €70 oven; bake the four; measure | €100, 2 days | larger countertop oven at the K9b column (+width) |
| R10 | **Layout clearances**: dishwasher door over domino and cooker pocket, oven door over the bay, arm under the oven | cardboard and plywood mock-up at 1 : 1 with the real appliance dimensions | €50, 2 days | cooker beside the dishwasher door path (+150 mm) |
| R11 | K10-W: **dig-from-top in cold shells**: frost and energy with the larger hatch, retrieval times with the hoist, toggle gripper on lidded GN 1/6 | cut the top of a used 122 cm built-in fridge; hand-cranked hoist with the toggle gripper; time 50 picks; log energy for a week | €250, 2 weeks | the storage round's C1-B window + S1 robot (+€1,000 per shell) |
| R12 | K10-W1: **one hand for storage and cooking** overloads the meal timeline | add storage moves to K9b's E0 discrete-event simulation | €0, 1 day on E0 | K10-W2 (+€280) |

**Order**: R8 and R12 (desk) → R1 (it can stop the concept) → R2, R10 → R3, R4, R5 → R6, R7, R9 → R11.
Total ≈ €1.5 k and ≈ 4–5 weeks; most purchases become prototype parts.

---

## 11. Decisions needed from Ben

| # | Question | Default assumed in K10 |
|---|---|---|
| Q1 | Accept a **bought thermo-cooker** (Thermomix-class clone) as a household appliance at the heart of the cooking, driven by the machine? | yes (shown both ways in §4.4) |
| Q2 | Accept that dishes and ware are **washed after the meal only** (all clean 3–5 h later for 4 persons; PERF-005's 90 min dropped), with a duplicate set for back-to-back meals? | yes |
| Q3 | Accept **household dishwasher disinfection** (65–70 °C, A0 ≈ 60) — together with C2? | pending C2 |
| Q4 | Accept a **countertop oven** (25–30 L, ≤ 465 mm wide) instead of a built-in or combi-steam oven? | yes; any model in his €500 budget that fits |
| Q5 | For the whole machine: **storage dug from the top by one rail** (K10-W1 or W2) instead of the storage round's four robots — trading fast random access and full-height cold shells (W1) for ≈ €4 k? | W2 if the €280 is acceptable, else W1 |
| Q6 | Is **≈ €3.0–3.3 k** (one unit) / **≈ €2.2–2.4 k** (series) for the whole machine part acceptable, given that €2 k with automatic storage at 93 % was not found? | report and continue with K10-W |
| Q7 | Accept serving through an unlocked guard panel (no hatch drawer)? | yes |
