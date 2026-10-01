# Storage S4 — aisle shuttle with a puller hook ("Rowa in a cabinet") for the 650 mm ambient column

Status: design proposal, storage round (brief `00-storage-brief.md`). Inputs: DECISIONS.md, requirements
(BOX, STO, CLD, CAP-020…026, PHY-001…004), `research/03-storage.md` §1–4, 6–7 (mechanism A, §3.2), K9b §2.
Marks: **[C]** calculated here, **[est]** estimate, **[U]** unverified, must be measured on a sample or a unit.
Coordinates as in S1, so that the two designs can be compared: ambient column = machine X 1200–1850; local
x 0–650 (left to right seen from the front), y 0 (wall) – 600 (front), z 0 (floor) – 2000. The K9b transport
gallery (z 2000–2200) is **not** part of S4. Density is counted the same way as in S1 (enclosure
650 × 600 × 2000 = 780 L, box envelope = 176 × 162 × (depth + 10 mm lid)).

## 0. Summary

* **Principle:** two single-deep rack faces (rear and front), 3 lanes wide, face each other across a 188 mm
  aisle. Lidded GN 1/6 boxes **hang by their rim on two runners** like pans in a GN trolley, with no shelf
  below them. An XZ carriage in the aisle carries a short piece of the same runners. A **passive J-hook** pulls
  any box straight out of its slot onto the carriage. The hook engages when the whole carriage lifts by 5 mm, so
  it needs no motor of its own. The carriage then rises to the top of the aisle, and **the carriage itself is
  the exit**: the gallery lifts the box off it through a roof hatch. Every box is one move away. There is no
  digging and no dig reserve.
* **Density [C]:** **96 positions** (all GN 1/6-100: 16 levels × 3 lanes × 2 faces), **all 96 usable**.
  That is **148 per metre of wall**. The box envelope is **38.6 %** of the enclosure. S1 has 126 positions
  (113 usable, 51 %), so S4 holds **24 % fewer positions than S1 nominal and 15 % fewer usable**. The aisle
  costs 28.5 % of the column. With the real height mix (S/M/T) S4 has 99 positions. It holds S1's reference
  set of 70 food boxes plus 26 empties with 3 slots spare. S1 has 31 spare.
* **Retrieval [C]:** the worst case is a bottom box in an outer lane, with the carriage parked at the top.
  It takes **6.1 s** to reach the exit (9 s with conservative axis data). The mean is ≈ 4 s, and ≈ 2 s with
  pre-fetching. A put-away takes ≤ 3.5 s. STO-003 (≤ 30 s, mean ≤ 15 s) is met for **every** box. S1 meets
  it only for the top 6 boxes of each stack.
* **Actuators:** 3 motors: Z (200 W servo with brake), X and Y (two NEMA 17 closed-loop motors). The hook is
  passive and the exit hatch belongs to the gallery. **Cost [est]:** machine part ≈ €1,450; rack and
  enclosure ≈ €850.
* **Biggest weakness:** **density**. The aisle takes a third of the usable depth, so S4 cannot reach S1's
  count in 650 mm. In a 178 cm built-in fridge shell only one face of 2 lanes fits (≈ 24 positions per
  shell), so S4 does **not** meet CAP-021 (chilled ≥ 45) with one shell [U: interior depth]. Second weakness: S4 needs a hook
  seat on the box rim [U] and ±1 mm runner alignment over 1.9 m.
* **Cold:** S4 works in the freezer: 24 positions ≥ CAP-022's 20. The exit is a **top-wall hatch** above the
  aisle, as in S1, and has the same good thermal behaviour. In the freezer two motors (X, Y) are inside the
  cold, compared with one in S1.

## 1. Principle and views

**Principle (3 sentences).** Lidded GN 1/6 boxes hang by their side rims on stainless runners, one box per
slot, in two single-deep rack faces of 3 lanes × 16 levels. The faces stand across a narrow aisle from each
other, and since a hanging box needs no shelf or fork space, each level costs only the box height plus 5 mm.
An XZ carriage with a short piece of the same runners stops in front of any slot, lifts 5 mm so that its
passive J-hook catches the box's end rim, pulls the box onto itself, and rises to the top of the aisle,
where the gallery lifts the box out through a roof hatch. For a put-away the gallery sets the box onto the
carriage and the same steps run in reverse.

### 1.1 Front view, section through the aisle (front rack face and door removed), x–z

```
 z (mm)                                                                    x (mm)
 2200 +----------------------------------------------------------------+
      |   K9b transport gallery (not S4)          [ hatch over lane B ] |
 2000 +======= roof 10 ======================[===== 190 x 168 =====]===+
 1990 |  Z drive shaft (top, behind the aisle, y 195-204), Z servo left |
 1985 |#|                         +=====beams 6x40 (y-edges of aisle)=+ |#|  <- carriage at HAND-OVER
 1945 |#|                         |   box on carriage (lid 1941)      | |#|     runners at R_h = 1930
 1930 |#|                         |~~runners~~~~~~~~~~~~~~~~~~~~~~~~~~| |#|     (gallery takes it here)
 1910 |#|=lane A==========|=lane B=|=========|=lane C================|#|  level 16 (R = 1910)
      |#|  rear-face slots seen through the aisle, boxes hang on rims  |#|
 1795 |#|=================|=================|=====================  |#|  level 15
      |#|       ...       |       ...       |        ...          |#|
      |#| 16 levels, R_k = 185 + 115 (k-1); M box (100) + lid 8 + 7 |#|
  645 |#|=================|=================|=====================  |#|  level 5
      |#|              +--------------------+                      |#|  carriage at level 4,
  530 |#|==============|~~ carriage runners ~|=====================  |#|  approach R - 5, lift 5
      |#|              |  box (hangs, 97)    |                      |#|
  300 |#|=================|=================|=====================  |#|  level 2
  185 |#|=================|=================|=====================  |#|  level 1 (body bottom 88)
  110 |o|  belt idlers (sealed), Z guide ends                        |o|
   80 +-+-----------------------------------------------------------+-+ (no grate: open lanes)
   60 |  drip tray 1.4301, slope 1 % to sump (front left), drain        |
    0 +==feet==========================================================+
      0 15  53|54.5     233.5|235      414|415.5    594.5|596  635 650
         Z   P0   lane A       P1  lane B   P2   lane C    P3  Z
      strip 38                 179 clear per lane                strip 39
      (vertical rail, belt,    partitions P 1.5 mm                (rail, belt,
       energy chain)           lane pitch 180.5                    servo on top)
```

### 1.2 Side view (from the right, lane C cut), y–z

```
 z      y=0 wall                                                                  y=600 front
 2200 +---------------------------------------------------------------------------+
      |  gallery: lowers its gripper through the roof hatch onto the carriage      |
 2000 +================== roof ==========[ hatch y 214-382 ]=======================+
      | Z shaft o (y 200)  beam|+-----------------------------+|beam                 |
 1930 |                        ||  box on carriage (hand-over)||                     |
      |------------------------|+-----------------------------+|--------------------|
 1910 |  ||==== rear slot ====||  carriage serves any level   ||==== front slot ===| |
      |  ||  box 162          ||  and either face             ||  box 162          | |
      |  ||  (hangs on rims)  ||                              ||                   | |door
      |  ||  ...16 levels     ||          AISLE 188           ||  ...16 levels     | |25,
      |  ||                   ||                              ||                   | |gasket,
  185 |  ||===================||                              ||===================| |inter-
   88 |  || body bottom       ||                              ||                   | |lock
   80 +--+--------------------+--------------------------------+-------------------+-+
    0 +============ drip tray, sump at front left ======================================+
      0 20 22  42           204 208                    388 392                 554 575 600
        |   |   |far tab      |   carriage y 208-388 = 180 |    |near end    far tab|
       gap liner box 42-204  rack face             (4 mm clear each side)  box 392-554
      rear rack y 22-204 (182)      aisle y 204-392 (188)      front rack y 392-575 (183)
```

### 1.3 Top view, x–y (partitions `|`, runners `=` under the side rims)

```
 y 600 +-----------------------------------------------------------------+ front, door y 575-600
   575 | |  +--------------+ +--------------+ +--------------+  |         |
       | |  | front A      | | front B      | | front C      |  |         |  front face: hand access
       | |  | 176 x 162    | |              | |              |  |         |  from the door (pull +y)
   392 | |  +--hook seat---+ +--------------+ +--------------+  |         |
       |Z|..........................................................|Z|  AISLE 188:
       | |   +====beam (y 208-214)=====+                            | |  carriage 196 (x) x 180 (y),
       | |   | J  box on carriage    J |  <- J-hook on the end rim  | |  X travel 361 (lane A..C)
       | |   +====beam (y 382-388)=====+                            | |
   204 |.|..........................................................|.|
       | |  +--hook seat---+ +--------------+ +--------------+  |    |
       | |  | rear A       | | rear B       | | rear C       |  |    |  rear face
    22 | |  +--------------+ +--------------+ +--------------+  |    |
     0 +-----------------------------------------------------------------+ wall
       0 15 53 54.5     233.5 235       414 415.5     594.5 596   635 650
 lane width 179 between partitions (176 rim + 3 play); 4 partitions per face
```

### 1.4 The J-hook (section y–z at the box end, 25–45 mm from the left corner)

```
  carriage side            rack face                    carriage side           rack face
        beam |  J-arm (z R+12..15)  :                          |  J-arm       :
             |  ==========+         :  lid =========           |  ======+     :  lid =========
             |            | shank   :  rim =====+              |        |     :  rim =====+
             |            |  2 mm   :  skirt -->| |            |        |     :      |<-seat|
             |            +--+      :           | |  body      |        +--+  :      | ++ | body
             |   tip 3 mm -> ^^     :           | |            |  tip ->  ^^  :      | ^^ |
       carriage runner at R-5      rack runner R               carriage runner at R  (aligned)
   (a) approach: tip 2 mm below the seat     (b) carriage +5 mm: tip 3 mm in the seat, pull or push
```

The carriage is an open frame: two flat-bar beams (6 × 40) along the aisle edges above the lid, two side plates
carrying the runners, and the Y slider with the J-arm on the left side plate. **Above the box the carriage is
open**: the clear width between the beams is 168 mm in y, so the gallery's gripper can come down onto the lid
and lift the box out vertically. The J-tip sits inside the skirt, so lifting the box moves the rim away from
the tip, and nothing has to be released first.

**Height budget of the aisle and the racks [C]:**

| z (mm) | Content | Height |
|---|---|---|
| 0–80 | feet, drip tray with sump (no grate: hanging boxes leave the lanes open) | 80 |
| 80–88 | clearance under the lowest box | 8 |
| 88–1921 | 16 levels × 115 (M box 100 + lid 8 = 108, + 7 clearance) | 1833 + 7 |
| 1921–1990 | top 69 mm: in the racks unused; in the aisle the carriage overhead at the hand-over (beams up to R + 55) | 69 |
| 1990–2000 | roof with the gallery hatch | 10 |

**The aisle is the cost of S4**: 188 mm of 553 mm usable depth, over the full height, = 28.5 % of the
column. A box level costs only 5 mm more than a stacked box in S1 (lid 8 + clearance 7, against S1's 10 mm lid
with pads), and S4
has no robot zone above the boxes (S1: 350 mm).

## 2. Box standard

| Item | S4 requirement |
|---|---|
| Footprint | **GN 1/6, 176 × 162 mm rim**, the same box as S1 (research/03 family 1). It is stored with **176 across the lane (x) and 162 in the pull direction (y)**. Because 176 is the GN family's common dimension, every slot and the carriage share one runner spacing. |
| Heights | S = 1/6-65 (≈ 1.0 L, level pitch 80), M = 1/6-100 (1.5–1.6 L, pitch 115), T = 1/6-150 (≈ 2.1 L, pitch 165), XL = 1/6-200 (≈ 2.5 L, pitch 215). Pitch = depth + 8 lid + 7 clearance. The level heights are set per rack face, so the height mix is a rack setting (§4.2). |
| GN 1/9 (108 × 176) | Fits any slot with the 176 rim across the lane and wastes 54 mm of slot depth. Optional for spices; the count below uses 1/6-65 for spices, as S1 does. |
| GN 1/3 (L, 325 × 176) | **Not supported.** The aisle carries at most 162 mm in y. Long pasta and ≥ 4 L bulk need another place (the same limit as S1's baseline). |
| Material, washing, cold | PP or Tritan GN (Araven, Hendi, Cambro PP; PC only if the BPA rule allows), −40…+95 °C, dishwasher-proof (BOX-009). |
| Lid | Flat gasketed press-on lid that sits **on top of** the rim and ends flush with its outer edge (seal-cover type, no clips), ≤ 8 mm. No stand-off pads are needed: boxes never touch each other in S4. |
| **Rim, hanging** | The box hangs on its two **162 mm side rims**. Each runner is 8 mm wide, so the rim must overhang the body by **≥ 9 mm** at the sides. If the rim has a downturned skirt, the box rests on the skirt edge, which works just as well. **[U: measure on samples.]** |
| **Rim, hook seat** | On **both 176 mm ends** the hook needs a **vertical face ≥ 4 mm high on the inside of the rim, 25–45 mm from the left corner** (seen from that end), with **≥ 5 mm free between that face and the body wall**. That face is normally the downturned edge of the rim. If the chosen box has a flat rim, a 4 × 20 mm slot is punched into the rim outside the lid's seal line and the hook catches its edge. **[U: this is the main sample check, §8.]** |
| Gallery grip | The gallery grips the box on its **176 mm ends at mid-span** (x 68–108 from the left rim edge), where the hook seat is not. The 162 mm side rims rest on the carriage runners and are not free. **To be agreed with the transport designer** (S1 assumed hooks on the 162 mm sides). |
| No protrusions | Nothing may stick out of the 176 × 162 rim outline. A K9b bayonet stub (Ø 22 × 40 + stand-off) on an end would add ≈ 55 mm to both slot depths and to the aisle. That is 661 mm > 553, so only one rack face would fit (−50 %). As in S1, the cell gets the opened box in a stub carrier, or grips the rim. |
| Identity | **Two HF/NFC inlays (13.56 MHz), one in each end rim**, rated for washing and −40 °C [U: 11,000 cycles]. The carriage reads the tag of the slot in front of it (≤ 30 mm range, so each read is unambiguous), at every pick and in an inventory scan. There is also a DataMatrix laser-marked on both ends for the cameras (BOX-006, STO-009). |
| Mass | ≤ 5 kg gross (BOX-004). The carriage runners sit on a single-point load cell and weigh every box while it is on the carriage (BOX-012, ±5 g [est]). |

So a bought GN 1/6 box qualifies if its rim has the side overhang and the end seat. It needs two tags
(≈ €1 more than S1's single UHF tag), and possibly one punched slot per end.

## 3. Retrieval sequence

### 3.1 Motion data (design point) [est]

| Axis | Data |
|---|---|
| Z | 200 W 48 V integrated servo, spring-applied brake, 3 : 1 planetary (the same part as S1's hoist), driving a cross shaft at the top. Two HTD-5M PU/steel-cord belts, one per end of the aisle, run in closed loops over sealed stainless bottom idlers at z 110. Speed 0.8 m/s, 3 m/s² with a 5 kg box. An **absolute magnetic tape scale** on the left Z rail gives ±0.1 mm. Stroke 175–1935 |
| X | NEMA 17 closed-loop stepper, GT2 belt along the rear beam, PTFE/iglidur slide shoes on the 6 × 40 flat-bar beams; 0.5 m/s, 3 m/s²; stroke 361 (lane A ↔ C) |
| Y (hook) | NEMA 17 closed-loop stepper, GT2 belt on the left side plate; 0.4 m/s, 2 m/s² with a box (pull force ≤ 30 N: friction μ ≈ 0.3 × 5 kg + acceleration); hook range −4…+184 mm across the 180 mm carriage |
| Engage / release | Z +5 / −5 mm and settle: 0.2 s each |
| Transfer rule | On a pull the carriage runners sit 0.5 mm below the rack runners; on a push, 0.5 mm above, so the box always steps down. All runner ends have 2 mm × 30° lead-ins, which absorb ±1.5 mm |

### 3.2 Worst case: bottom box of an outer lane, carriage parked at the top

The target is rear face, lane A, level 1 (runner R = 185, box bottom at 88). The carriage waits empty at the
hand-over position (lane B, R = 1930), with the hook at its front end. There is no blocked box in S4, so the
worst case is the farthest box. The front face is the mirror image (pull −y).

| # | Move | Time s [C] |
|---|---|---|
| 1 | Z down 1.75 m to R − 5 = 180. At the same time: X 180 mm to lane A, hook to the rear end of the carriage | 2.45 |
| 2 | Settle. The ToF sensor checks that the box's near end is at the rack face (displaced box, STO-013); NFC reads the tag (STO-009) | 0.15 |
| 3 | Z +5 mm: the J-tip rises into the hook seat; carriage runners now 0.5 mm below the rack runners | 0.20 |
| 4 | Y pull 167 mm: the box slides off the rack runners onto the carriage runners. The Y-motor current gives the pull force (jam check); the ToF confirms the box is fully on | 0.62 |
| 5 | Z up 1.745 m to the hand-over, X back to lane B (at the same time); the load cell weighs during the last 0.3 s | 2.45 |
| 6 | Settle, "out-box ready" to the gallery | 0.20 |
| | **Total: the box is ready for the gallery** | **≈ 6.1 s** |

With conservative axis data (Z 0.5 m/s and 2 m/s², Y 0.25 m/s, settle times doubled) the same case takes
**≈ 9.3 s**. The hook stays engaged during the Z travel, so the box cannot slide on the carriage.

**Retrieval time against level** (from the hand-over, outer lane, design point) [C]:

| Level (runner z) | 16 (1910) | 12 (1450) | 8 (990) | 4 (530) | 1 (185) |
|---|---|---|---|---|---|
| s | 2.2 | 2.9 | 4.1 | 5.2 | 6.1 |

The mean over all slots is **≈ 4 s**. STO-003 (≤ 30 s for any box, mean ≤ 15 s) is met for all 96 positions
by a factor of 5. S1 meets the 30 s limit for 54 of its 126 positions.

### 3.3 Put-away (≈ 2.5 s mean, ≤ 3.5 s)

1. Before the gallery arrives, the carriage waits empty at the hand-over. It moves its hook to the end that
   will be the **trailing end** for the chosen face: the front end of the carriage for a rear slot, the rear
   end for a front slot.
2. The gallery lowers the box between the beams onto the carriage runners. As the rim comes down, the skirt
   passes outside the J-tip and the body passes inside it, so the tip ends up in the hook seat with nothing
   moving [the gallery must place within ±1.5 mm in y].
3. Z to the target level with the runners 0.5 mm above the rack runners (≤ 2.45 s). Y push 167 mm (0.62 s):
   the hook pushes the body wall, the box slides in until its far rim touches the end tab.
4. Z −5 mm (0.2 s): the tip drops 2 mm below the seat. The hook retracts during the next move.

Free slots are chosen by expected use (3.4). No other box moves, ever.

### 3.4 What normally happens: placement and pre-fetch

* **Placement by expected use.** Frequent boxes (salt, oil, onions, the current menu) go to the top levels,
  slow stock and empties to the bottom. The gain is small (2 s instead of 6 s), so the placement rule matters
  far less than in S1.
* **Pre-fetch.** The menu is planned (UC-04). In idle time S4 moves the next meal's boxes into the top three
  levels; a planned retrieval then takes ≈ 2–3 s, and the 10–15 ambient boxes of a 4-person meal cost
  ≈ 1 min of storage time (retrievals plus returns), all of it overlapped with cooking.
* **Decoupling (TRN-008).** The carriage is the exit and holds one box. It holds an out-box only on request;
  the next box waits in a top-level slot 1.5–2 s away, so the gallery never waits for more than one transfer.
* **Limit: no cross-face move without the gallery.** A box on the carriage stays hooked at the end where it
  was taken, so S4 can put it back into any slot of the **same face** but not into the other face. Moving a
  box to the other face (rebalancing only, rare) needs one lift and set-down by the gallery (≈ 8 s of gallery
  time).

### 3.5 Hand-over to the gallery

The carriage at R = 1930 presents the box with its lid top at z 1941 under the roof hatch (190 × 168, spring
flap opened by the gallery, brush seal). The gallery's gripper comes down ≈ 50 mm between the two beams,
grips the 176 mm ends at mid-span and lifts. Because the J-tip sits under the rim inside the skirt, lifting
needs no release step. Handshake as in S1: S4 reports *free / out-box ready / locked*, and does not move
while the gallery's gripper is below the roof (software interlock plus the gallery's position signal).

## 4. Density

### 4.1 Positions and volume [C]

Enclosure 650 × 600 × 2000 mm = 780 L, as in S1.

| Quantity | S4 | S1 (for comparison) |
|---|---|---|
| Positions, all GN 1/6-100 | **96** (16 levels × 3 lanes × 2 faces) | 126 |
| Usable (without dig reserve) | **96** | 113 |
| Positions per metre of wall | **148 /m** | 194 /m nominal, 174 /m usable |
| Box envelope 176 × 162 × 110 | 301 L = **38.6 %** | 395 L = 50.7 % (usable 45 %) |
| Box envelope at S4's own pitch (× 115) | 315 L = 40.4 % | – |
| Box content (GN 1/6-100 ≈ 1.55 L) | 149 L = 19 % | 195 L = 25 % (usable 22 %) |
| STO-005 (≥ 55 % envelope) | **not met** | not met |
| Positions reachable within STO-003's 30 s | **96** | 54 |
| Worst case | 6.1 s | 72 s |

**Where the 780 L go (all-M, full rack):**

| Share | Volume | What |
|---|---|---|
| 38.6 % | 301 L | box positions (96) |
| 1.8 % | 14 L | level clearance: 5 mm per level more than S1's stacking |
| **28.5 %** | **223 L** | **aisle** (188 mm deep, 620 wide, full height): carriage path and hand-over |
| 8.2 % | 64 L | x-direction: the two Z strips (38 + 39 mm) and 4 partitions with play, over the rack depth |
| 5.1 % | 40 L | y-direction: slot depth beyond the box (≈ 20 mm per face: far tab, finger room) |
| 1.7 % | 14 L | z-direction: top 69 mm of the racks (carriage overhead at the top level) |
| 16.0 % | 125 L | shell: side walls 2 × 15, rear service gap and liner 22, door 25, plinth and tray 80, roof 10 |

**Honest comparison with S1.** The non-access losses are almost equal: S4 31 % (shell, strips, slot depth,
top) against S1 32 % (grid tiling, walls, tray, top gap). The whole difference is the price of access: S4's
aisle plus level clearance cost **30 %**, S1's robot zone plus dig reserve **23 %**. The reason is
geometric: 553 mm of usable depth holds exactly three rows of 162 mm boxes. S1 stacks all three. In S4 one
row is the aisle, so S4 has 6 boxes per level against S1's 9 per layer. S4 recovers part of that with 16
levels against S1's 14, because it needs no 350 mm robot zone above the boxes. Narrowing the aisle gains
nothing short of removing it. It could shrink by at most 18 mm, by moving the beams off the box ends, but
that costs a port slot and the open top, and frees no further row.

### 4.2 Reference allocation (2-person household, CAP-020, CAP-023)

The level heights are set per face when the partitions are made (§5.2). Budget per face
[C]: lowest box bottom ≥ 88, top runner ≤ 1930 → Σ pitch ≤ 1860 mm.

| Face | Levels from the bottom | Positions | Holds |
|---|---|---|---|
| Rear | 8 × S (pitch 80) + 10 × M (115) = 1790 | 24 S + 30 M | 24 seasonings; 17 M food + 13 empty M |
| Front | 5 × S + 5 × M + 5 × T (165) = 1800 | 15 S + 15 M + 15 T | 6 seasonings + 8 empty S; 13 M food; 10 T food (cans, jars) + 5 empty T |
| **Total** | | **99** (39 S, 45 M, 15 T) | **70 food + 26 empty = 96 boxes, 3 free** |

Food volume 30 × 1.0 + 30 × 1.55 + 10 × 2.1 ≈ 97 L ≥ 45 L; ≥ 30 smallest boxes. **CAP-020 is met, and S4
alone holds the 26 empties of CAP-023** (the guest shop of CAP-013 fills empties). This is exactly S1's
reference set, but with 3 free slots instead of 31. S4 has no room to grow in 650 mm; the next step is a
900 mm column (4 lanes, +33 %, §4.3) or nesting the empties outside S4.

### 4.3 Variations: the density levers that were tried

| Variation | Positions (all-M) | Worst case | Motors | Verdict |
|---|---|---|---|---|
| **Baseline**: 2 faces single-deep, boxes hanging on rim runners, passive J-hook, the carriage is the exit | **96 (96 usable)** | 6 s | 3 | **chosen** |
| Telescopic fork under the box (research A as written) | fork plate + lift ≈ +25 mm per level → 15 levels → **90**; fork side gaps | 7–8 s | 3 + a 2-stage telescope | rejected: fewer boxes, more mechanism |
| Boxes standing on sheet shelves, hook on the box | 16 levels → 96, but the hook height then depends on the box depth (4th axis), and spills stay on the shelves | – | 4 | rejected |
| Box pitch: M turned (162 across the lane) | 166.5 lanes → still 3 per face (4 need 666 > 620), and GN 1/9 no longer fits the runner spacing | – | – | rejected |
| A 4th, narrow spice lane (GN 1/9 turned, 108 across) | needs 112 mm, 77 mm left after 3 lanes, which the Z strips need | – | – | not possible in 650 |
| **Double-deep rear face** (rear 216 for 2 S deep, aisle 172, front 165) with a 2-stage telescopic hook arm | with the 4.2 mix: rear S levels hold 48 instead of 24 → **≈ 120 (+21 %)**. But 216 + 165 + 188 > 553, so the aisle shrinks to 172, the beams no longer straddle the box, and the exit becomes a port slot (−1); the S pitch grows to 90 for the arm | rear box: one shuffle, ≈ 12 s | 3 + telescope | **option** if more spice positions are needed; it buys density with the complexity S4 is meant to avoid |
| **Double-deep with a spring pusher** (supermarket shelf pusher advances the rear box to the face) | same +21 % without a telescope | 6 s | 3 + a spring per lane | rejected: the face detent that holds a full box against the spring cannot also hold an empty box (0.15 kg); each lane would need a gate that the carriage opens (≈ 40 gates) |
| **One-sided rack, aisle at the front** | single-deep 48; double-deep (rack 365 = 2 M) 96, but with a telescopic reach | 6 s / ≈ 12 s | 3 + telescope | rejected: at best the baseline's count, with half the boxes behind others |
| **One-sided rack served by the existing K9b gantry** (no own carriage) | (a) K9b cell hand, its X box extended over the column: Z stroke 900 (arm z 1000–1900) → 8 levels × 3 lanes = **24**. (b) The gallery carriage: needs a guided 1.9 m Z (K9b lowers 0.45 m) and a Y-puller, and the gallery is blocked during every storage move (TRN-008) | – | (a) −3; (b) −3 in S4, +2 in the gallery | rejected for the 650 column. (a) also brings the wet cell hand into the dry store (TRN-011/012). (b) is an idea for the system round, if the transport becomes a full-height XZ gantry anyway: then **all** storage could be one-sided racks along one machine-length aisle, and the aisle would be paid once for every module |
| Wider column (PHY-003 grid) | 750: still 3 lanes (4 need 800); **900: 4 lanes → 128 (142 /m)**; 1200: 6 lanes → 192 (160 /m) | same | 3 | S4 scales linearly with width; 650 sits just under a lane step |
| Nested empties outside S4 (lid station keeps the lids, as S1 suggests) | 26 empties take ≈ 4 slots instead of 26 → +22 free | – | – | system option |

## 5. Actuators, seals, sensors, parts, cost, failures, manual access

### 5.1 Actuators

| # | Actuator | Type [est] | Travel |
|---|---|---|---|
| 1 | Z | 200 W 48 V servo, spring-applied brake with hand release, 3 : 1 planetary, cross shaft at the top (y 195–204, above the rear face's top level). Two belts in the side strips. Two vertical rails (MGN15 stainless or igus drylin T), with two long blocks per end block so the frame cannot rock | 1.76 m |
| 2 | X | NEMA 17 closed-loop stepper on the left end block, GT2 belt along the rear beam; carriage on dry slide shoes on the two flat-bar beams | 361 mm |
| 3 | Y (hook) | NEMA 17 closed-loop stepper on the carriage, GT2 belt and MGN9 rail on the left side plate, J-arm on the block | 188 mm |
| – | J-hook | **passive, 0 motors, 0 wires**: engaged and released by Z ±5 mm | – |
| – | Roof hatch | spring flap with brush seal, opened by the gallery (transport side, as in S1) | – |

**3 motors**, the same count as S1 and one fewer than research A (X, Z, fork, latch). No motor sits under or
above a stored box: Z is at the top of a side strip, X and Y ride in the aisle.

**Seals:** none dynamic; the module is a dry zone. Static: door gasket (STO-008), brush seal at the roof
hatch, cable glands, drain trap.

**Sensors:** absolute magnetic tape scale on Z; X/Y closed-loop encoders with Hall home sensors; Y-motor
current as the pull force; two ToF sensors, one per carriage end, looking into the slot (box present, near-end
position, displaced box: STO-013); a 10 kg single-point load cell under the carriage runners; two NFC readers,
one per carriage end; an optional camera with LED looking into the slot (lid, spill, broken box); door
interlock; leak electrodes in the sump; T/RH sensor (STO-007).

### 5.2 Rack

* **Partitions:** 8 ladder partitions, 4 per face, each 183 × 1900 mm, laser-cut from 1.5 mm 1.4301. Two stiles
  and one rung per level leave large windows for light, spray and drainage.
* **Runners:** flat strips 2 × 8 mm, laser-welded along their whole length to the rungs, on both faces where
  needed (no crevice). Each face has 6 strips per level, ≈ 190 in all. A 4 mm upturned tab at the far
  end stops the box; a 0.8 mm bump at the near end keeps it from creeping out (the hook overcomes it with
  ≈ 2 N).
* **Mounting:** the partitions hang from a top frame and are pinned in a bottom frame. The rear face is fixed
  to the liner, the front face to a front frame whose uprights lie in the partition planes, so every front
  lane stays open towards the door.
* **Height mix:** fixed by the partition set (§4.2). Any box fits any slot of its height class or taller.
  Changing the S/M/T ratio means fitting another partition set (or the option of tool-free clip runners in a
  5 mm hole grid, at the price of small crevices). **STO-006 is met only partly**; S1 meets it fully, since
  any box stands on any stack.
* **Calibration:** at commissioning and after every door opening, the carriage measures the height of each
  runner pair with its ToF (±0.2 mm [est]). The Z targets are stored per slot (TRN-009 practice).

### 5.3 Parts and cost (machine part, small series, net) [est]

| Part | Bought / custom | € |
|---|---|---|
| Z servo 200 W, planetary, brake | bought | 220 |
| 2 closed-loop NEMA 17 + drivers | bought | 120 |
| Z rails 2 × 1.9 m + 4 blocks | bought | 170 |
| Z belts, pulleys, cross shaft, bearings, 2 sealed idlers | bought | 90 |
| X/Y belts, pulleys, MGN9 rail, slide shoes | bought | 60 |
| Absolute magnetic tape scale 2 m + read head | bought | 120 |
| Load cell + amplifier, 2 ToF, 2 NFC readers | bought | 110 |
| Camera + LED (optional) | bought | 50 |
| Controller, 48 V 400 W PSU, energy chains (Z 2 m, X 0.4 m), cabling | bought | 250 |
| Hall sensors, door interlock, leak and T/RH sensors | bought | 50 |
| Spray valve, nozzle bar on the carriage, hose | bought | 70 |
| Carriage: beams, end blocks, side plates, runners, J-hook | custom (laser, bent, welded) | 160 |
| **Machine part** | | **≈ 1,470** (lean: no camera, Z re-homed instead of a tape scale, open-loop X/Y ≈ 1,200) |
| Rack: 8 partitions, ≈ 190 welded runner strips, top and bottom frames | custom | 450 |
| Enclosure: sides, roof with hatch, liner, gasketed door, drip tray with sump | custom | 400 |
| **Rack and enclosure (the "shelving")** | | **≈ 850** |
| Boxes: 96 × (GN 1/6 PP + lid + 2 NFC tags) ≈ €14 (about the same for every storage design) | bought | ≈ 1,340 |

Against #28 (≈ €2,000 for the whole machine part), one ambient column takes ≈ 70 % of the budget, as S1
does. Per usable position S4 is dearer: ≈ €24 of machine part and shelving, against ≈ €17 for S1. The
rack is the reason: it costs more than S1's posts.

### 5.4 Failure modes and recovery

| Failure | Detection | Automatic recovery | Human |
|---|---|---|---|
| Box jams in its slot (rim catches a runner end, box tilted) | Y current > 2 × expected, or stall | push back 5 mm, dither Z ±0.5 mm, retry at 0.1 m/s; after 3 tries the slot is marked *blocked* and the other 95 work on | free the slot by hand |
| Hook misses the seat (displaced box, damaged rim) | ToF before engaging; no load rise in the first 3 mm of the pull | release, push the box home against its tab, measure again, retry; then mark the box *ungrippable* | replace the box |
| Lid ajar or box displaced in a slot | ToF near-end position, camera | push home; a box with its lid ajar is still pulled by the rim and goes to the lid station | – |
| Box dropped (rim breaks during a transfer) | load-cell step, ToF | in a lane it falls onto the lid of the box below and stays between the partitions; in the aisle it falls to the tray (≤ 1.9 m, may break) | remove; spill per §6 |
| One Z belt breaks | Z scale against motor position | the other belt holds the frame alone (safety factor ≈ 8); brake | replace the belt |
| **Power loss mid-move** | – | the brake holds Z, the hook holds the box on the carriage; a box caught half-way rests on rack and carriage runners at once and stays. On restore: absolute Z, X/Y re-homed away from the box, move journal plus ToF → finish or undo the move: **< 30 s, STO-010 met** | – |
| Door opened, boxes moved by hand | interlock | on closing, an **inventory scan**: the carriage passes all 32 lane-levels and reads the tags at the slot ends on both faces (≈ 0.3 s per slot): **≈ 1 min even if everything was reshuffled** (S1: up to 25 min) | – |
| Carriage blocked (foreign object in the aisle) | following error | stop, reverse, mark the zone | remove the object |

### 5.5 Getting a box out by hand (STO-011)

* **Power off, front face (48 boxes):** open the door, lift the box 5 mm over its far tab and pull it out
  towards you. A few seconds per box. The top lid is at 1921 mm, the limit of comfortable reach, so short
  people need a step.
* **Power off, rear face:** take out the front box of the same lane and level. Reach through the empty slot
  (179 × 122 mm clear), across the aisle (≈ 370 mm in all), pull the rear box towards you and lift it out
  through the same slot: ≈ 15 s. The carriage normally parks at the top. If it stopped at that level, release
  the Z brake with its hand lever and turn the top shaft with the crank stored behind the top cover
  (TRN-015 style).
* **Power on, service mode:** S4 parks the carriage at the top and unlocks the door. The UI shows face, lane
  and level. The boxes are transparent and the slot is labelled.
* **So in S4 every box is at most one other box away from the human,** against up to ≈ 40 in S1.

## 6. Cleaning

**Design for cleanability.** A box touches only the two runners and the hook, and only with its rim, which is
outside Zone F. **No box ever stands on another box**, so box bottoms stay clean. S1's stacking contact path
does not exist here. Nothing lies under a box: the lanes are open down to the drip tray, the partitions are
flat stainless sheets with windows, and the runners are welded without crevices. The aisle mechanism is
stainless, PU and PTFE, runs dry (TRN-011: slide shoes and dry-running guides) and has sealed bearings. The
Z servo and cross shaft sit at the top, behind a drip shield.

| Event | Detection | Machine response |
|---|---|---|
| **Crumbs, dust** (from box outsides) | camera; schedule | they fall through the open lanes onto the lids below and down to the tray; a weekly flush nozzle at the high end of the tray rinses them to the sump and drain (drain shared with the machine, air break) |
| **Spill from a leaking box** | sump leak electrodes; weight loss at the box's next pick (±5 g); wet lids in the camera image | the partitions keep a drip inside its lane, so the wet tray zone gives the lane. The carriage pulls that lane's boxes one by one from the top down (each is directly accessible, no unstacking), weighing and photographing each. The leaker goes via the gallery to the cell for decanting and washing. Boxes with wet lids below it go out for an exterior rinse **[assumes the lid station can rinse a lidded box, as in S1]**. Then a lane wash (below) |
| **Broken box** | camera; ungrippable | **human task**: remove the pieces; then an automatic lane wash. A box whose rim breaks falls only onto the box below in its own lane |
| **Routine wash** (monthly, at night) | schedule | slot by slot: the box goes to a free slot (≈ 3 s), the carriage's nozzle bar sprays the empty slot (runners, partition faces, tab) with 60 °C detergent water and then a clear rinse (≈ 10 s), and the box comes back (≈ 3 s). ≈ 20 s per slot, ≈ 35 min for all 96. Water runs down the partitions to the tray. On the way down the carriage also sprays the aisle faces. In its park position at the bottom of the aisle, two fixed nozzles rinse the carriage itself. The fan and dehumidifier dry the module to RH ≤ 65 % (1–3 h [est]) |

**Honest limits.** S4 has more stainless surface to wash than S1 (8 partitions ≈ 2.8 m², ≈ 190 runners),
and the Z belts and rails in the side strips are in the spray path, so they must be wash-proof (stainless,
PU, sealed). Spraying a slot also splashes the lidded neighbours, as in S1, so every ambient box must be
splash-tight (BOX-007). Against S1, S4 can empty any slot with one move and wash it at once, and a spill
stays in one lane instead of running down a whole stack.

## 7. Cold variant

### 7.1 Fit in the K9b cold allotment (two 600 mm, 178 cm built-in shells)

```
 side view, one shell (interior figures [U], research/03 4.1, as S1: ~480 W x 380 D x 1500 H)
 z 2200 +--------------------------------------------------+
        |  gallery                                         |
   2000 +==============================[ gallery port ]===+
        |  Z servo + cross shaft on the cabinet top (warm) |
  ~1872 +=== cabinet top wall =========[TOP HATCH 190x168]=+  <- the cut: an "exit plate" with
        |  carriage overhead / hand-over                   |     the hatch and 1 shaft bushing
        |  ||=rack face (rear), 2 lanes=||   AISLE 188     |
        |  ||  12 levels M (or 18 S)    ||   carriage      |   one face only: 183 + 188 = 371 <= 380
        |  ||  hanging on rim runners   ||   (Z belts in   |   2 lanes: 362.5 + 2 x 38 strips
        |  ||                           ||    the strips)  |            = 438.5 <= 480
   ~320 +--------------------------------------------------+
        |  compressor, plinth                              |
      0 +--------------------------------------------------+
        rear wall (evaporator)                        OEM door kept as the SERVICE door
```

| Item | Fridge (+4 °C) | Freezer (−18 °C) |
|---|---|---|
| Positions [C on U interior] | one face (two faces need 554 mm depth), 2 lanes × 12 M levels = **24** (36 with S boxes only) | **24** |
| Against the requirement | CAP-021 ≥ 45: **not met** with one shell; two fridge shells give 48 but cost 600 mm of wall (PHY-004: only within the 4.2 m option). S1 gets ≈ 40–45 in the same shell | CAP-022 ≥ 20: **met**, with little margin |
| Exit | as S1: **hatch in the cabinet's top wall** above the aisle. The carriage brings the box up under it and the gallery lifts it out. Insulated flap 40 mm PU, heated gasket frame (≈ 5 W, CLD-014), flap motor on the cabinet top | same |
| Open time (CLD-004 ≤ 10 s) | ≈ 3–4 s, only while the gallery passes; all transfers inside run with the hatch closed | same |
| Air exchange | horizontal opening with the cold air below, so the air stays layered; ≤ 10 L per opening [est], as in S1 | ≈ 0.7 kJ per passage [est]; negligible at 5 per day (CAP-012) |
| Motors | Z servo outside on the cabinet top, its shaft through one bushing in the exit plate; X and Y motors ride inside at +4 °C (IP65, coated; ≈ 10 W while moving, < 1 W parked) | Z outside. **X and Y ride on the carriage at −18 °C**: cold-rated IP67 steppers with −40 °C H1 grease, kept warm by 3–5 W of idle current each (CLD-009). **That is two moving motors in the cold, against one (the hoist) in S1.** Option without motors inside: two vertical hex shafts from motors on the cabinet top, on which the carriage slides, driving X and Y through bevel gears (+2 bushings, ≈ +€250, more friction) |
| Hook, runners, sensors inside | passive hook; NFC reads through condensation; ToF on the carriage | passive hook; NFC works at −40 °C and through frost; the load cell drifts, so **weighing moves to the lid station** (as S1). PUR cables rated to −40 °C |
| Frost and condensation | little humid air enters through a top hatch; stainless and PP do not mind condensation | NoFrost cell. A hanging box touches the runners with its rims only, so **there is no box-on-box freeze-bonding** (an S1 risk). The rim wipes the runner on every transfer; Y current tracks rising friction, and a warm-up cycle is triggered when it rises [est] |
| Raw meat (CLD-011) | R boxes in the bottom levels of their own lanes: a drip stays in the lane and reaches the tray, never an RTE box. **S4 never puts an R box above an RTE box, not even for seconds** (S1's digging does). The 0–2 °C sub-zone (CLD-003) still needs its own compartment | – |
| Human access | open the OEM door: the aisle and carriage are in front, and **all 24 boxes are directly reachable** | same, with gloves |

**CLD-007 risk:** the same as S1. The top wall is cut for the exit plate, which is allowed "at the exit" only
if no refrigerant line, sensor or cable runs there [U: check by thermography or the service manual].

### 7.2 Verdict, cold

The mechanism works at +4 °C and −18 °C, and its exit is as good thermally as S1's. **Capacity is the
problem.** A 178 cm shell is only ≈ 380 mm deep inside, so it takes one rack face of 2 lanes: 24 positions.
That is enough for the freezer but about half of what the fridge needs. Possible routes:

* S4 for ambient and the freezer, S1 stacks for the fridge;
* two fridge shells;
* a custom VIP cell over the whole 1,200 mm (research option B): one face, 5 lanes × 16 levels ≈ 80
  positions, for both cold zones.

**The deciding measurement is the interior of the chosen shell.** Two faces (48 positions) would need
≈ 554 mm of depth, or, with the aisle running front to back, ≈ 554 mm of width and ≈ 400 mm of depth. The
research expects ≈ 480 × 380, which is not enough for either.

## 8. Score, biggest weakness, cheapest experiment

Scores 1 (poor) – 5 (excellent), weights from the brief.

| Criterion | Weight | Score | Reason |
|---|---|---|---|
| Simplicity | 30 % | 4 | 3 motors and a passive hook engaged by Z. Each retrieval is one transfer, no other box ever moves, and there is no digging or placement logic. Bought linear parts. Against: 8 partitions with ≈ 190 runners that must stay within ±1.5 mm over 1.9 m, and the hook needs a feature on the box rim [U] |
| Hygiene | 25 % | 4 | Hanging boxes leave nothing under a box. Box bottoms never touch another box, and only rims touch the machine. Open lanes drain to the tray, a spill stays in its lane, and any slot can be emptied with one move for washing. Against: more stainless surface and weld seams than S1's posts; the Z belts and rails are in the spray path |
| Coverage / fit | 20 % | 2.5 | STO-003 met for every box (6 s), STO-010 by a 1 min scan, STO-011 with every box at most one box away. Against: 96 positions (S1 126 / 113 usable), envelope 39 % (STO-005 asks 55 %), only 3 spare slots in the reference allocation, no GN 1/3, height mix fixed by the partition set (STO-006 partly), no K9b stub, and in the cold only 24 per 178 cm shell (CAP-021 not met with one fridge shell) |
| Reliability | 15 % | 4 | ≈ 60 transfers a day instead of S1's ≈ 100–200 grip cycles; passive hook, brake, two belts, absolute Z; a fall is contained in the lane; < 30 s recovery after power loss, 1 min re-scan. Against: every transfer depends on runner alignment and on the rim seat geometry. A jam blocks one slot only |
| Cost | 10 % | 3 | machine part ≈ €1,450 + rack and enclosure ≈ €850. ≈ €24 per usable position (S1 ≈ €17) |
| **Weighted** | | **3.6 / 5** | (S1: 3.4) |

**Honest biggest weakness: density.** A 600 mm deep cabinet offers three rows of 162 mm boxes, and the
aisle takes one of them. S4 therefore holds 96 positions in the 650 mm column, where S1 holds 126 (113
usable): −24 % nominal, −15 % usable, 148 instead of 194 per metre. In the column it is enough for the
2-person reference stock (70 food boxes + 26 empties) with only 3 slots spare; more needs a wider column
(900 mm: 128). In a 178 cm fridge shell only one face fits, 24 positions, which is about half of CAP-021.
Everything else S4 trades for this aisle is better than S1:

* worst case 6 s instead of 72 s;
* no prediction or pre-digging needed;
* every box within one box of a human hand;
* no box-on-box contact;
* 1 min re-scan.

**Cheapest experiment (≈ €500, 2 weeks).** Build one lane of one face, 6 levels high: two laser-cut
partitions with welded runners, and 12 real GN 1/6-100 PP boxes with seal-cover lids from at least two makers
(≈ €180). Add a 1 m vertical Z axis from 3D-printer parts (belt, NEMA 23, brake) with a carriage section,
and the J-hook on a Y belt as an FDM prototype (non-food zone, allowed by #4). Measure:

1. **Rim geometry and hook seat** on the boxes of 3 makers: side overhang, skirt height, skirt-to-body gap.
   Engagement and pull/push with 0.2–5 kg over 1,000 cycles; target < 1 failure in 10³, and no skirt
   damage. If the seat is missing or too weak, test the punched-slot version.
2. **Transfer robustness** against the step between rack and carriage runners (0, ±0.5, ±1, ±1.5, ±2 mm)
   and the gap between them (2–6 mm), with full and empty boxes.
3. **Sliding friction** of the rim on stainless: dry, wet, and after a night at −18 °C with frost; the pull
   force must stay < 30 N.
4. **Transfer time** compared with the model in §3 (0.6 s per pull), and lifting the box off the carriage
   from above with the hook still in its seat (the gallery hand-over).

If (1) fails on all bought boxes, S4 depends on a box modification (punched slot or a clip). If (2) needs
better than ±0.5 mm, the runners get self-centring lead-ins or the carriage gets a touch probe, before S4 is
compared with the pusher and belt designs.

