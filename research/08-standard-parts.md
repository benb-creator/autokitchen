# R8 - Standard parts catalogue (motion, frames, actuators, grippers, sensors, water, control, appliances, 3D printing)

Status: research result for the AutoKitchen engineers. Date of research: 2026-09-30. Prices in EUR unless stated.

## 0. How to read this document

* Price tags: **[V]** = seen on a supplier page or in a search-result snippet during this research (the URL is in section 12; prices move, treat as +/-20 %). **[U]** = unverified: my estimate from general knowledge of the market. Please re-quote every [U] item before it goes into the BOM.
* Net vs gross: German shops quote gross (19 % VAT); B2B sites (Motedis, Unchained Robotics, igus) often show net. Each price says which where known.
* Research limits: the web search quota ran out after roughly two thirds of the planned queries. Topics with thin verification (Misumi/igus curved guides, HGR rails, belts, IP-rated motors, tool changer list prices, moteus, JMC motors, RealSense, Bambu H2D) are marked [U] and listed in "Open issues".
* Two facts that change the design more than any part number:
  1. **A domestic hob cannot be started remotely** (safety level "red" in Home Connect; Miele exposes hobs read-only). A machine that cooks unattended on a hob needs its own safety concept, or its own (non-domestic) induction module. See section 9.
  2. **Raspberry Pi 5 8 GB now costs EUR 218.90** at Reichelt [V] (memory-price crisis since February 2026). The "cheap SBC" assumption is no longer valid; budget EUR 100-220 for a host computer.

---

## 1. Frames, panels and the kitchen carcass grid

### 1.1 Aluminium T-slot extrusion

| Profile | Slot | Weight | Ix (strong) | Price | Source |
|---|---|---|---|---|---|
| 20x20 B-type, slot 6 (Motedis) | 6 mm | ~0.5 kg/m [U] | ~0.6 cm^4 [U] | from 3.95 EUR/m net [V] | Motedis |
| 30x30 B-type, slot 8 (Motedis) | 8 mm | ~1.0 kg/m [U] | ~2.5 cm^4 [U] | **7.81 EUR/m net / 9.30 gross** [V] | Motedis |
| 40x40 B-type, slot 8 (Motedis) | 8 mm | ~1.5-1.8 kg/m [U] | ~8-10 cm^4 [U] | from 13.29 EUR/m net [V] | Motedis |
| item Profile 8 40x40 2N90 light, natural | 10 mm | 1.82 kg/m [V] | 9.5 cm^4 [V] | not shown; ~25-35 EUR/m [U] | item24 |
| 40x80 (Motedis or item) | 8 / 10 mm | ~3.2 kg/m [U] | ~35-40 cm^4 [U] | ~25-45 EUR/m [U] | - |
| 40x40 generic (AliExpress, V-slot Poland etc.) | 8 mm | 1.4-1.8 kg/m | similar | ~7-10 EUR/m [U] | - |

Facts and choices:

* item (Profile 8, groove 10 mm) and the former Bosch Rexroth strut profile system (groove 10 mm, 40x40) are mutually compatible in groove geometry [U]; item is the reference system with the best documented load data (groove pull-out 2,500 N per slot for 40x40 [V]) and the widest accessory range. Motedis (groove 8 mm for 30/40 series, also offers 10 mm) is 2-3x cheaper, offers cutting to size (min 50 mm; up to 1980 mm listed, longer on request) and M8 tapped ends [V]. Motedis 30x30 and 40x40 share the 8 mm slot, hence the same T-nuts, brackets and cover strips: that is the attraction for a "house standard".
* Delivery lengths: item up to 6,000 mm [V]. A 2 m upright is trivial to ship; a 4 m rail carrier arrives as one bar.
* Surface: anodised natural is standard [V]. Black anodised costs ~+10-20 % [U]. Aluminium is not "dishwasher proof" (alkaline detergent attacks anodising, white bloom) and is not a food-contact material by default; keep it behind panels or in the dry zone.
* **Hygiene:** the open T-slot is a bacteria and grease trap. Rules: (a) in the splash/food zone use slot cover strips (Motedis "Abdeckprofil Nut 8", ~0.6-1.0 EUR/m [U]) or place the frame outside the wet zone behind stainless/HPL panels; (b) in the wet zone use welded 316/304 stainless tube or sheet-metal folded parts, not extrusion.
* **Stiffness reality check (calculated).** E = 70,000 N/mm^2, I = 9.5 cm^4 = 95,000 mm^4 for a 4040 light profile:
  * 2 m span, 50 kg (490 N) central load: delta = F L^3 / (48 E I) = 12 mm. Acceptable for a shelf beam, not for a rail carrier.
  * 4 m span, its own weight only (17.9 N/m): delta = 5 w L^4 / (384 E I) = **9 mm**. Consequence: **a 4-5 m axis must never be a self-supporting beam.** Bolt the rail to a continuous flat support (base-cabinet worktop plate, angle beam every 500 mm, or 4080/4040 with support at every 1,000 mm). Rails then only follow the support's flatness (0.2-0.5 mm/m needs machined or ground support surface, or use spring-loaded/floating rail mounting).
* Connectors: standard angle brackets (30/40 mm, ~1-2 EUR each [U]), concealed hidden connectors (Motedis "Verbinder", tension bolts), drop-in T-nuts M6/M8 (~0.10-0.20 EUR [U]), spring-loaded pre-assembly nuts. For vibration/wash: use serrated flange nuts plus threadlocker, or Nord-Lock-style washers.
* Panels (all prices [U] per m^2 from general knowledge, no supplier quote):
  * Stainless sheet 1.0-1.5 mm 1.4301 (304) or 1.4404 (316): 60-110 EUR/m^2 (304), 110-190 (316); laser-cut and folded via services (e.g., Kaiser+Kraft, Laserteile24, Xometry, Protolabs): 30-120 EUR per part. Best for splash walls, drip trays, hygiene panels; "brushed #4" finish; radius all inner corners >= 3 mm.
  * HPL compact 6-12 mm (Fundermax, Egger compact, Trespa): 60-120 EUR/m^2; cuts with woodworking tools; edges are watertight (solid core); standard in wet rooms; good for housing panels.
  * Aluminium composite (Dibond 3 mm): 30-50 EUR/m^2; light; cut edges expose PE core, needs edge sealing; ok for non-wash cosmetic panels only.
  * Polycarbonate 3-4 mm (Makrolon/Lexan, hygienic clear) 25-45 EUR/m^2; viewing windows and doors; hazy with hot dishwasher chemicals, avoid steam zone (> ~110 C, and alkaline cleaners craze it). Acrylic/PMMA cracks with detergents: avoid.
  * Tempered glass / ceramic glass (from oven doors) for viewing windows in hot zone.
* Adjustable feet: kitchen plinth feet (Hafele, Hettich, Rehau "Sockelfuss"; 100-150 mm, load 80-150 kg each, ~1.5-4 EUR each [U]); for heavy machine cabinets use M10/M12 machine levelling feet with stainless pad (~4-12 EUR each [U]). Plinth board: 16 mm PVC/ aluminium clip-on plinth (with seal) is standard.

### 1.2 The carcass grid (what "kitchen size" means)

Standard European kitchen dimensions (widely quoted; AMK/HEA/kitchen-planning pages; EN 1116 is the coordination standard):

* Width module: 300 / 400 / 450 / 500 / 600 / 800 / 900 / 1000 / 1200 mm; **600 mm is the base module**; grid 100 or 150 mm in some ranges (Nolte, Nobilia: 150 mm steps) [U].
* Depth: carcass 560 mm, with front (16-19 mm) and gap about 580; worktop 600 (sometimes 650-700) mm. Wall unit depth 320-350 mm (max ~400).
* Height: plinth 100-150 mm (adjustable; standard 100-120), base carcass 720 mm, worktop 38-40 mm -> worktop top edge about 900-920 mm; (910 mm is the value in the brief). Niche between worktop and wall units 500-600 mm. Tall units 2,000 / 2,100 / 2,230 (2,130?) mm, up to 2,450 with top boxes [U]. Ergonomic reference: work height = elbow height minus 10-15 cm.
* **EN 1116** (Furniture - Kitchen furniture - Coordination dimensions for kitchen furniture and kitchen appliances; edition 2018 exists as DIN EN 1116:2018 [V]) defines coordination dimensions of furniture, worktop, niches, fronts, panels, built-in appliances and sinks. Not applicable to commercial kitchens [V]. The standard text is paywalled; niche numbers below are from manufacturer data sheets (Bosch/Siemens/Miele/Neff), typical, [U]:
  * Built-in oven niche: 560 (W) x 585-595 (H) x 550 (D) mm; appliance front 595 x 595 mm. Tall-unit oven niche needs ventilation gap >= 5 mm and rear opening.
  * Hob cutout: 60 cm hob 560 x 490 mm; 80 cm hob 750 x 490 (varies); needs >= 20 mm gap to niche rear and a ventilation gap below (50 mm+ per maker), power 7.4 kW (3-phase) typical.
  * Built-in dishwasher (fully integrated): niche 600 W x 815-875 H x 550 D (appliance 598 x 815-865 x 550); 450 mm variant. Decor front mounted to the door.
  * Built-in fridge/freezer: niche 560 W x 1780 (or 1220 / 880 / 1020 / 1400 / 1580) H x 550 D; door-on-door (sliding-hinge) or fixed-hinge fronts; a fridge-freezer in 178 cm niche is the common one.
  * Microwave/compact niches: 380 mm and 450 mm high.
* **Integrating off-the-shelf built-in appliances**: design each niche to the EN 1116 sizes so the appliance can be swapped by a service tech like in any kitchen (also satisfies "easily accessible for repair"). Note appliance heat/ventilation gaps, plinth-side airflow for fridge compressor, condensate. The brief wants a fridge with a "slightly modified door": a built-in fridge door can be replaced by a custom door with a hatch; keep the original gasket circuit and insulation; the compressor and evaporator sit at the back, so the box grid inside needs a cold-air path (see R3). The 550 mm niche depth (vs 600 outer) leaves only ~30-40 mm for a rear pass-through for transport, so plan the transport interface at the FRONT (door) or from the top/side.
* Power/water: Kitchen circuits in Germany: sockets 230 V 16 A (B16); hob/oven on separate 400 V 3-phase 16 A ("Herdanschluss", 11 kW) is standard in new builds; the brief states only "220 V". Check with requirements team; see section 8.6.

---

## 2. Linear motion

### 2.1 Rail options

| Option | Size / capacity | Precision | Dry / wash-down | Cost per metre (rail) + carriage | Notes |
|---|---|---|---|---|---|
| MGN12H (miniature profile rail, Hiwin-type; Chinese clones) | 12 mm; C ~3-5 kN per block (varies by make) [U] | 0.02-0.1 mm | Grease-lubricated (needs H1 grease); no wash-down | 1 m rail + 1-2 blocks: **$29-45** (KB3D, eBay; stainless "high temp" version $45) [V] ~ 27-42 EUR | 3D-printer standard, very available. "Stainless" = 440C martensitic: rusts in dishwasher steam and chloride; NOT 316. Not for wash zone. |
| MGN15H | 15 mm; C ~7-8 kN [U] | same | same | ~10-15 EUR/m rail + 8-15 EUR/block [U] | Recommended step-up for gantry axes. |
| HGR15 (Hiwin HGH15CA clone) | 15 mm; C ~11 kN, C0 ~17 kN [U] | 0.02 mm | Grease; seals; no wash-down | Chinese: ~15-30 EUR/m + 15-25 EUR/block; genuine Hiwin/THK: 60-100 EUR/m + 50-90/ block [U] | For heavy Z or long spans. |
| Misumi SSEB/SSEBW (stainless miniature, SUS440C) | 9-20 mm | 0.01 mm class | Stainless; can use H1 grease | ~50-120 EUR per 100-300 mm guide + block [U]; eBay: SSEBW12 ~$65, SSEBWZ16 110 mm ~$114 [V]; +MX self-lube variant | Not hygienic design (recirculating balls); short lengths. |
| igus drylin W (aluminium rail, iglidur J/ J200 sliding block) | rail sizes 10/16/20/30/40; load 1-2 kN per block class | 0.05-0.1 mm (clearance) | Dry-running (no lubricant), tolerates dirt; hard-anodised | ~60-150 EUR/m + 25-60 EUR/carriage [U] | Best value dry-running option. |
| **igus drylin W in hygienic design** (316 stainless rail, iglidur A160 carriage, self-draining) | single/double rail modular | ~0.1 mm | **FDA and EU 10/2011 compliant materials, EHEDG-oriented, "regular cleaning with chemicals, steam and high-pressure water"** [V] | not published; quote; expect > 150-400 EUR/m [U] | Only ready-made, lubricant-free, washable rail found. Use in wet zone. |
| igus drylin stainless W (older 304 stainless rail + iglidur) | | | corrosion resistant, wash-down "underwater, chemical" [V] | quote [U] | cheaper than hygienic series [U] |
| V-slot (OpenBuilds-style 2040 with POM wheels) | 20-40 kg per carriage plate | 0.1-0.5 mm | Open groove: dirt/hygiene trap; POM wheels are dry | ~10-20 EUR/m + 25-45 EUR/plate [U] | Cheap, good for covered zones. |
| Round shaft + plain bearings (8/12/16 mm hardened, LM-UU or igus RJ4JP) | 12 mm shaft: ~0.5 kN per bearing [U] | 0.05-0.2 mm | igus iglidur plain bearings dry; shafts 1.4125 stainless | ~10-25 EUR/m shaft + 6-15 EUR/bearing [U] | Needs supports every 300-500 mm for span; cheap and washable. |
| HepcoMotion GV3 / PRT2 (V-guides, stainless option) | 10 kN and more, 5 m/s [V] | self-aligning, zero play with eccentric bearings | stainless, nitrile-sealed bearings [V] | quote; typically EUR 200-1,000 per metre incl. carriage [U] | Industrial; only company with stock 90 and 180 degree segments. |

Key data for the long axis:

* Recirculating-ball profile rails are supplied in 4 m max lengths in one piece; longer are butt-joined (matched-end rails, 0.01 mm offset). At 4-5 m: price of rail ~ 4x the 1 m figure, block price constant.
* Flatness demand of the support: 0.1 mm/m for profile rails (for HG-type) [U]; a 4 m "self-supporting" aluminium beam sags 9 mm (section 1.1): all long rails need continuous support.
* Wash-down: no recirculating-ball rail is truly hygienic (grooves, grease). Approach: keep all rails and belts in a **dry, sealed "machine deck"** above/below the wet zone; only the carried *box* and a slender gripper fork enter the wash zone.

### 2.2 Belts

| Belt | Typical use | Working tension / stiffness | Price |
|---|---|---|---|
| GT2 (2 mm pitch) 6-10 mm fibreglass/neoprene | 3D printer class; loads < 3 kg, speeds 0.5-1 m/s | ~30-60 N working per 6 mm [U] ; 5 m span stretch is significant | ~1-2 EUR/m [U] |
| GT3 3 mm / HTD 5M 15 mm | up to ~10 kg moving mass, 2-3 m | ~200-500 N [U] | ~4-8 EUR/m [U] |
| Steel-cord polyurethane T5/AT5/AT10, 16-32 mm (Optibelt, Contitech Synchroflex, Gates, Mulco) | long axes 3-10 m, stiffness like belt-driven gantry robots | AT5/25: 1-2 kN working, ~0.1-0.2 % stretch [U] | ~8-25 EUR/m [U] |
| White/blue FDA/food-grade PU belts (T5/AT5 with polyurethane cover, EU 10/2011 or FDA 21 CFR 177.2600 compliant), stainless cord | food-contact / wash-down | as above | ~+30-80 % over standard [U] |
| igus drylin ZLW belt: Basic = neoprene + glass fibre, Standard = **PU with steel** (HDT 3M, MTD3, RPP 3M, AT5, 8M) [V] | see 2.3 | | |

Belt facts to design with: belts need clean dry running (they are not wash-down); PU-steel belts tolerate short splashes but the steel cord corrodes at cut edges unless stainless/ sealed. Belt-driven axes have no backlash issue but need a tensioner and preload; a belt with the motor in the middle of the axis (as in the igus ZLW-1040-S double-axis with central NEMA 34 motor [V]) halves the stretch length.

### 2.3 Ready-made linear axes and modules

igus drylin ZLW belt axes (verified technical data [V], igus technical-data page):

| Model | Max stroke | Max speed | Max radial load | Position deviation |
|---|---|---|---|---|
| ZLW-0630 | 1,000 mm | 2 m/s | 150 N | +/-0.3 mm |
| ZLW-1040 (clearance height 45 mm) | 2,000 mm | 5 m/s (Standard), 3 m/s (Basic) | 300 N Std / 200 N Basic | +/-0.2 mm |
| ZLW-1080 | 2,000 mm | 5 m/s | 300 N | +/-0.2 mm |
| ZLW-1660 | 3,000 mm | 5 m/s | 300 N | +/-0.2 mm |
| ZLW-20120/-20160/-20200 | 3,000 mm | 5 m/s | 3,000 N | +/-0.2 mm |

* Prices [V, igus UK, stroke 100 mm, presumably net]: ZLW-1040-02-B-100 = GBP 368.85, ZLW-1040-02-S-100 = GBP 570.56. Price grows with stroke; a 2 m ZLW-1040 axis is roughly EUR 600-1,000 without motor [U].
* No IP class or food certificate stated for ZLW (checked [V]) -> treat as dry-deck parts. Stroke limit 3 m -> for 4-5 m use two axes end to end, or use a custom belt.
* Misumi/Chinese belt sliding tables (e.g., 60-100 mm wide, 1-2 m stroke): 150-500 EUR/m [U]; Chinese ball-screw sliding tables (FSK/SFU1605, 500-1500 mm): 150-400 EUR [U]; Rollon Speedy-Rail / Bosch Rexroth CKR: 10 m possible [U], 400-1,500 EUR/m.
* Rack-and-pinion: steel rack module 1-1.5, 15x15 mm ~ 20-40 EUR/m [U]; stainless 80-200 EUR/m [U]; igus iglidur plastic racks and pinions exist [U]; advantage over belts: no stretch at 5 m, high load; disadvantages: noise, open teeth (dirty), backlash (0.05-0.2 mm) unless split pinion.
* Lead/ball screws: Tr8x2/Tr8x8 lead screw 10-15 EUR/m [U] (stainless 20-40 EUR/m [U]); SFU1605 ball screw 500 mm with nut and BK/BF supports ~ 60-100 EUR [U]; igus drylin lead screw units with dry-running nuts (iglidur J) ~ 20-40 EUR per nut, screws 20-60 EUR/m [U]. Best for **vertical** axes (Z of a gantry, self-locking with Tr8x2; 8 mm lead is NOT self-locking, need brake). Max screw length ~ 1 m before whip speed limit (critical speed for 8 mm: ~1,500 rpm at 1 m [U]).
* Cost per metre in a full 1-axis kit (rail + carriage + belt + motor + driver), practical scale: 3D-printer class ~ 60-100 EUR/m; ZLW class ~ 500-800 EUR/m; hygienic igus / Hepco ~ 1,000-2,000 EUR/m [U].

### 2.4 Going around a 90 degree corner (L-shaped kitchen)

Options ranked by simplicity, then continuity:

| # | Concept | Parts | Cost (whole corner) | Comments |
|---|---|---|---|---|
| 1 | **Two straight axes plus a corner transfer cell** (box handed over by a rotary table or shuttle in the blind corner cabinet) | Turntable bearing (slewing ring 200-300 mm, 10-40 EUR; or igus PRT slewing ring [U]), NEMA23 + belt, box cradle | 150-400 EUR [U] | Simplest; the blind corner cabinet (900x900 mm) is dead space anyway. Adds 5-10 s per box passing. Recommended default. |
| 2 | Continuous curved V-guide track (HepcoMotion PRT2 ring/track: oval, square, S-bend systems, **90 and 180 degree segments from stock, stainless steel option, belt/chain/rack drives, 10 kN, 5 m/s, "functions in dirty environments"** [V]) | 90 degree PRT2 segment (e.g., R300-R500), straight slide, carriages, belt or chain drive | 600-2,500 EUR for corner + carriages [U]; PRT2 price is on request | Continuous path; carriage driven by roller chain or a belt following the curve; box on a cantilevered carriage puts moment loads on the bearings. A curved 600 mm-deep track has R of ~300 mm on the inside. Use for the option of an "L" with no handover. |
| 3 | igus curved drylin guides (drylin W-based curve/ring guides; also iglidur slewing rings) | | ~300-1,000 EUR [U] | Exists (curved guides listed in igus program) [U], not verified: check availability at igus. Dry, lubricant-free; not for wet zone unless hygienic version. |
| 4 | Overhead monorail / power-and-free conveyor | (e.g., Interroll, Montratec) | 2,000+ EUR [U] | Too large (min radius 300-500 mm and 50+ mm beam) and clean-up issue; not for 600 mm kitchens. |
| 5 | Conveyor corner unit (curved roller/belt conveyor 90 degree, Interroll, Rexnord) | | 1,500-4,000 EUR [U] | Inner radius min ~500 mm: does not fit in 600 mm depth. Rejected. |
| 6 | Gantry in the corner with two crossed X/Y carriages ("H-bot in L") | 2 short axes | | Just one gantry whose X axis is the L's long arm and Y axis short arm; passes boxes at the corner tile. Same as #1. |

Recommendation: standard design = #1; keep #2 as fall-back if the architecture demands a continuous carriage. The "wall-to-wall" gantry in the L is not needed if the corner cabinet works as transfer cell.

### 2.5 Speeds and loads, planning numbers (engineering estimates)

Storage box mass: R3 says small to medium; assume 0.5-2.5 kg empty+full up to 5 kg; carriage plus gripper 2-3 kg -> moving mass 5-8 kg. With a 0.5 m/s cruise and 2 m/s^2 accel:
* Force to accelerate 8 kg: 16 N -> a 6-10 mm GT2 belt is enough; for margin use 10-15 mm HTD 5M.
* For Z axis (vertical) lifting 8 kg + friction: 80-100 N plus 30 %; 4 Nm NEMA23 at 10 mm pulley radius gives 400 N; 1.2 Nm NEMA23 with 20T GT2 (12.7 mm radius) = 94 N: marginal -> use a 2-3 Nm motor or a counterweight.
* Cycle time: 4 m at 0.5 m/s is 8 s, at 1 m/s 4 s + accel; fine for kitchen scale.

---

## 3. Actuators

### 3.1 Stepper and servo family

| Type | Example | Torque | Interface | IP | Price | Source |
|---|---|---|---|---|---|---|
| NEMA17 open loop | 17HS4401 0.4-0.5 Nm, 1.5 A | 0.4-0.6 Nm | step/dir | IP20 | 6-12 EUR [U]; Trinamic/Nanotec 25-50 EUR [U] | - |
| NEMA23 open loop | 1.2-3 Nm | | | IP20 | 20-40 EUR + driver 15-40 [U] | - |
| **NEMA23 closed loop stepper kit** (StepperOnline TS/TP series + CL57T-V41 driver, 24-48 V, 0-8 A) | 2-3 Nm | step/dir, encoder | IP20 (driver/motor) | **$64-87 per kit** (driver alone $36) [V] | omc-stepperonline |
| StepperOnline Easy Servo NEMA23 integrated, 90 W | 0.3 Nm cont., 3000 rpm, 20-50 VDC | pulse/dir | IP20 | ~$100-130 [U] | Amazon listing [V spec] |
| JMC iHSV57 / iSV57T integrated servo (NEMA23) | 0.6-3 Nm | RS485/CANopen options | IP20-IP54 [U] | ~120-220 EUR [U] | - |
| **Teknic ClearPath-SD** CPM-SDSK-2311S-ELN (NEMA23 servo, integrated drive) | 290 oz-in peak (2.0 Nm), 4000 rpm, 24-75 VDC | step/dir, 0.057 deg resolution | **IP53; IP66K/IP67 with M12 connector and shaft seal option** | **$338** (list SDSK $265-$369) [V] | teknic.com |
| Steppers with planetary gearbox (NEMA17 14:1/ 5:1) | 3-9 Nm at output | | | 30-60 EUR [U] | - |
| BLDC + ODrive S1 controller | 12-48 V, 40 A cont. | CAN 2.0B, USB, UART, step/dir | - | **$149** controller [V]; motors 40-150 EUR [U] | shop.odriverobotics.com |
| moteus c1 / n1 | 12-51 V, 20-40 A, CAN-FD | | | ~$100-140 [U] | mjbots.com (rate-limited, unverified) |
| DC gearmotor 12/24 V with encoder (37 mm, Pololu/ Chinese) | 1-10 kg cm | | IP20 | 15-40 EUR [U] | - |
| Worm-gear DC motor (self-locking, e.g., 12 V 20 RPM) | 5-30 Nm | | IP20-IP54 | 20-50 EUR [U] | - |
| RC/hobby servo (MG996R etc.) | 1 Nm | PWM | none | 5-10 EUR [U] | - |
| Smart serial servos (Feetech STS3215; Dynamixel XL430/XM430) | 1.5-4 Nm | TTL/RS485 | none (some waterproof clones, IP66 [U]) | Feetech ~15-25 EUR [U]; Dynamixel XL430 ~50 EUR, XM430 ~280 EUR [U] | - |
| Linear actuator 12/24 V, IP65-IP66 (Actuonix, Firgelli, Thomson), 100-500 mm stroke | 100-1000 N | on/off / feedback | IP54-IP66 | 60-200 EUR [U] | - |
| Push/pull solenoid or lock solenoid | 5-30 N | on/off | IP20-IP65 | 5-25 EUR [U] | - |

Points:
* NEMA17 at 24 V, ~0.5 Nm holds 100-150 N via a 20T GT2 pulley; enough for light axes and tool actuation.
* **Closed-loop** matters here: an unattended machine that loses steps during a 30 min cook cycle will crash a box or a tool. For axes carrying boxes use closed-loop (CL57T-V41-class, encoder feedback, alarm out) or servo (ClearPath). Trinamic StallGuard homing/stall detection is unreliable at low speed (feels marginal), so use real switches or encoders.
* 48 V beats 24 V for NEMA23 (higher top speed at same torque); Octopus Pro is sold in 48 V/60 V variants [V].
* **Wash-down/IP:** commodity steppers are IP20-IP40 with open connectors; nothing in the standard catalogue is IP69K or stainless below about EUR 400-1,000 per motor [U] (Oriental Motor, SEW, Nord). Approach: motors live in the dry machine deck; where a shaft must cross into the wet zone use a lip-seal/ V-ring, a labyrinth + stainless shaft, or a **magnetic coupling** through a stainless wall (neodymium pot magnet pairs, ~ 5-15 EUR each [U]). If the motor has to be exposed: ClearPath with shaft seal and M12 connectors (IP66K/IP67 [V]) is the cheapest IP67 servo found.
* Industrial high-IP stainless drives (Oriental Motor "AZ series IP66", SEW hygienic) will be listed as an option in the BOM for hard cases only.

### 3.2 Pneumatics vs electric vacuum

Compressor route (Piab/SMC ejector + compressor): SMC ZH ejectors are cheap ($15-116 depending on model) [V], but each ejector burns 20-60 NL/min compressed air while sucking [U], so a silent compressor (Silentaire 30-TC: 30 dB, $795 [V]; typical oil-less "Flüster" compressors 40-55 dB, 150-400 EUR, [U]) would cycle often. The Piab piCOBOT unit was listed at EUR 3,265.82 excl. VAT [V] (probably a full cobot vacuum unit; anyway far too expensive).

Electric route: a brushless diaphragm vacuum pump (12/24 V, e.g., Parker BTC, KNF, Schwarzer; 100-300 EUR [U]; cheap 12 V mini pumps 8-20 EUR, -60 to -70 kPa, 20-40 L/min, but 50-60 dB and limited life [U]) + 1 L buffer tank + solenoid + pressure sensor. Good for porous packages? Pumps are fine for sealed boxes, plate lifters, bag sealing.

Decision: **electric vacuum pump plus reservoir and small valve** as default; no compressed-air network anywhere in the kitchen (saves noise, hygiene risk of oil-mist, and a second utility). Use pneumatics only if some existing gripper needs it, then a single small silent compressor (< 45 dB) in the plinth.

---

## 4. Robot arms (option) versus a Cartesian gantry

Verified data [V] unless tagged:

| Arm | Payload | Reach | Repeatability | Weight | Price EUR | Protection | Notes |
|---|---|---|---|---|---|---|---|
| igus ReBeL 6DOF | 2 kg | 664 mm | +/-1 mm | 8.2 kg | **4,970** (open-source variant costs more: $9,223) [V] | not stated; optional "ReBeL Skin" cover protects against dirt, splash water, food contamination [V] | plastic (iglidur/ motorised joints), integrated control in the base; food suitability: not certified [U] |
| UFactory Lite 6 | 0.6 kg | 440 mm | +/-0.5 mm | ~3 kg [U] | **3,600 gross / 3,000 net** [V] | none | Too small; toy class |
| UFactory xArm 6 | 5 kg | 700 mm [U] | +/-0.1 mm | ~12 kg [U] | **6,360 gross / 5,300 net** [V] | none stated (IP54 on some series [U]) | Best price/performance of the Western brands |
| Fairino FR3 / FR5 | 3 kg / 5 kg | 622 / 922 mm [U] | +/-0.02 mm [U] | 17 / 22 kg [U] | **FR3 from 4,600 net, FR5 4,900** [V] | IP54 [U] | Chinese; force-torque; cheap |
| Dobot CR3 / CR5 | 3 kg / 5 kg | 620 / 900 mm [U] | +/-0.02 mm [U] | | 14,310-18,470 (CR3) [V] | IP54 [U] | Expensive; better ecosystem |
| Elephant myCobot 280 Pi | 0.25 kg | 280 mm | +/-0.5 mm [U] | 0.9 kg | $799 [V] | none | Toy/education |
| Annin AR4 MK5 (open source, self-built, Arduino/Teensy, steppers with gearboxes) | 1.9 kg | 629 mm | 0.2 mm | 12.25 kg | kit from $1,189; ~$1,790 with motors [V] | none | 198 W; 3D printed parts possible; DIY quality |
| Dobot MG400 SCARA-like desk arm | 0.75 kg | 440 mm | +/-0.05 mm | | 2,500-3,500 [U] | none | 4 axes |
| Epson T3 / Denso SCARA | 3 kg | 400-600 mm | +/-0.02 mm | | 8,000-12,000 [U] | IP20-IP65 clean-room / wash-down variants [U] | 4 axes, no tilt |

Honest comparison for a **600 mm deep, 2,000 mm tall cabinet**:

* Reach geometry: a 6-axis arm needs a swept sphere with radius equal to its reach (440-900 mm). A 664 mm ReBeL mounted at the cabinet centre would sweep beyond the 600 mm depth (and the front door). To exploit it you would put it on a rail (7th axis) and give it a 700x700 mm "cell" plus dead zones under/over the base. Also each pivot creates hygiene seams (10+ joint gaps, cables, grease); arms as sold are not wash-down designs (ReBeL cover is a splash cover, not an EHEDG design).
* Payload: Low-cost arms carry 2-5 kg *including* the gripper. A loaded box is 2-5 kg and a pan with food 3-6 kg; the 2 kg ReBeL and 0.6 kg Lite 6 are out; xArm 6 (5 kg) and FR5 (5 kg) are borderline for a pan; nobody lifts a full stock pot.
* Precision: +/-1 mm (ReBeL) is not good enough for hitting a 1 mm slot; a gantry with profile rails and closed-loop steppers gets 0.1-0.2 mm cheaply.
* Cost: arm 3-5 kEUR plus controller/gripper 1-3 kEUR vs. a Cartesian XYZ 4 m x 0.6 m x 0.6 m gantry at 800-2,000 EUR of parts (with 3-axis, closed-loop, rails, belts).
* Flexibility: the arm wins in **tool handling and free motions** (pour a box into a pan at any tilt angle; open a lid; stir in a pot in place; place food on a plate at a nice angle; use a non-prescribed sequence); the gantry wins in **throughput, stiffness, cleanability, predictability and price**.
* **Verdict:** Storage/retrieval and transport = **Cartesian gantry** (or two gantries). Preparation and plating = either a gantry-mounted tilting wrist (3 linear + 2 rotary axes: Y-Z-X + tilt + rotate is "5-axis gantry") or one arm in a defined cell. Recommend designing the interfaces so the arm is an **optional** module (mounting plate, envelope, protected cable route); the base design must not depend on it. If one arm is chosen: xArm 6 or FR5 for payload/precision; ReBeL only for light plating (plastic, cheap, "Skin"), and only after igus states the IP rating.
* SCARA: good for plating (top-down, fast, 0.02 mm), but no tilt for pouring. 4-axis Dobot MG400 too small.

---

## 5. Grippers and tool changers

### 5.1 Grippers

| Item | Spec | Price | Source |
|---|---|---|---|
| Schunk EGP 25-N-N-B / -S-B (electric parallel, IP40) | 25 mm stroke [U] | EUR 2,200-2,600; $1,297-1,965 [V] | various |
| OnRobot RG2 | 2 kg, 110 mm stroke | EUR 4,521 net [V] | Unchained Robotics |
| Robotiq 2F-85 | 5 kg pinch, 85 mm | EUR 4,515-4,950 net [V] | Unchained Robotics, Wired Workers |
| DH-Robotics PGE/PGSE (servo) | 15-50 mm stroke, 15-100 N | PGSE-15-7 $395; PGE series $450-1,200 [V] | RobotShop etc. |
| Homemade: NEMA17 + leadscrew, or Feetech servo + 3D printed fingers (PETG/PA-CF) | 20-80 N | 30-70 EUR [U] | - |
| Vacuum cups (silicone food grade, FDA/EU 1935/2004; Schmalz, Piab, Festo, Pisco) | 10-100 mm Dm; 1 cup ~ 10 N per 100 kPa per 10 cm^2 | 5-20 EUR each [U] | - |
| Soft/FinRay fingers (Festo DHAS or printed TPU 95A); OnRobot Soft Gripper | conforming | DIY 10 EUR; industrial 1,000+ EUR [U] | - |

Design rule: **avoid clamping food and avoid clamping boxes.** Give the box two flanges or handles and use a fork/hook (hooks need no gripper force and no actuator, only a motion); use grippers only for tools, plates and sturdy items (a plate lifter or a pan handle). Then the gripper is a 30-50 EUR item, not a 3,000 EUR item.

### 5.2 Tool changers

| Solution | Payload | Repeatability | Price | Notes |
|---|---|---|---|---|
| Jubilee / E3D kinematic coupling (steel dowels + balls, 3 contact pairs, 6-point contact, latch by carriage lever/servo) | light, "non-load-bearing" (< 1 kg) [V] | < 40 micrometre [V] | 30-60 EUR per tool [U] | Cheapest; open geometry easy to wash (stainless dowels); Jubilee's design mostly PETG/ printed. |
| Magnetic dock (pot magnets 316, 32 mm, pull ~ 30-50 kg [U]) with alignment pins | 1-3 kg | 0.1-0.3 mm | 10-30 EUR per pair [U] | Simple; self-releasing by lever; risk: magnets pick up chips; keep magnets sealed in stainless cups. |
| ATI QC-11 (manual/pneumatic, ~11 kg) | 11 kg | 0.01 mm [U] | new ~1,000-2,000 EUR [U]; used $67-370 [V] | Industrial; needs air. |
| Schunk SWS-007 (16 kg) | 16 kg | 0.01 mm [U] | used $1,065 [V]; new ~2,500-4,000 EUR [U] | pneumatic lock, 80 pin power/ signal; too big. |
| Stäubli MPS 015 (10 kg) | 10 kg | 0.01 mm [U] | quote [V] | |
| Bayonet / quarter-turn dock (printed or turned, spring-loaded) | any | 0.1 mm | 10-30 EUR [U] | Rotate to lock; easy to clean. |
| **Rotating tool quick connect**: 1/4 inch hex drive (impact-driver bit shank) or Kitchen-aid-style square drive; splined "Thermomix"-style shaft; drive is spring-loaded with a dog clutch | 0.5-3 Nm | | 5-20 EUR [U] | The blade/whisk head is dropped into a hex socket; a magnetic reed sensor confirms lid/ tool presence. |

Recommendation: **kinematic dock + latch** for the tool head (printed brackets and stainless pins), a hex-drive for rotating tools, no industrial changer.

---

## 6. Sensors

| Function | Part | Spec | Price | Notes |
|---|---|---|---|---|
| Weighing (box, bucket, dosing) | Bar/beam load cell 1-50 kg (aluminium, IP65) | 0.02 % class | 5-15 EUR [U] | Cheap; 4 cells form a platform |
| | Stainless single-point load cell IP67-IP68 (Zemic L6E3, Bosche, HBM PW) | 10-100 kg | 40-120 EUR [U] | Use in wet zone |
| Load-cell ADC | HX711 (24-bit, 10/80 SPS) | poor temp drift, noisy | 1-3 EUR [U] | ok for boxes; better: ADS1232 / ADS1256 / NAU7802 (24-bit, ~10-15 EUR [U]) for dosing |
| Homing/limit | Inductive M8/M12 proximity IP67 (PNP 24 V) | 2-4 mm | 8-15 EUR [U] | Wash-proof; use for all axes |
| | Hall/ reed / optical slotted | | 1-5 EUR [U] | dry deck only |
| Distance | VL53L1X ToF (4 m), VL53L5CX 8x8 ToF | +/-5 mm | 6-16 EUR [U] | glass window, steam fogs the lens; Sharp/ inductive better wet |
| Camera (colour) | Raspberry Pi Camera Module 3 / HQ | 12 MP, AF | 30-60 EUR [U] | fine for AprilTag/ Datamatrix reading |
| Depth/AI camera | OAK-D Lite, 13 MP, 4 TOPS, USB | | **$269** [V] | on-device inference; OAK-D Pro W more |
| | Intel RealSense D435i | | ~300 EUR [U] | Company was spun out of Intel in 2025 [U] |
| Thermal camera | **MLX90640** 24x32, 55 x 35 degree FOV (110 x 70 variant), -40..300 C, +/-2 C, 16 Hz | | **$74.95** (Adafruit) [V] | Watch pan, boil-over, hob surface, boil-dry |
| | FLIR Lepton 3.5 160x120 | | ~250-300 EUR [U] | more pixels, radiometric |
| IR thermometer | MLX90614 (single point, 5-90 degree FOV variants) | +/-0.5 C | 10-20 EUR [U] | glass window must be IR-transparent (use ZnSe or open path) |
| Probe | PT1000 in 316 sheath (4x50 mm) + MAX31865 | +/-0.3 C | 10-25 EUR [U] | in-food or in-vessel temperature |
| | Type K thermocouple + MAX31856 | +/-1.5 C, to 1000 C | 8-15 EUR [U] | for oven/ pan (fast) |
| | Bluetooth wireless meat probes (Meater, Combustion Inc.) | | 30-130 EUR [U] | cannot survive a dishwasher |
| Flow | Hall turbine YF-S201 | 1-30 L/min | 3-6 EUR [U] | Not drinking-water approved (plastic/ lead-free issue) |
| | Digmesa FHKU / Gems, food-grade plastic | 0.05-3 L/min | 60-120 EUR [U] | dosing and CIP monitoring |
| | Sensirion SLF3x (liquid) | 0.1-40 mL/min | 100-150 EUR [U] | |
| Water level | Float switch (PP) | on/off | 5-15 EUR [U] | |
| | Capacitive non-contact tube sensor (e.g., XKC-Y25) | | 3-10 EUR [U] | ok for clear pipes; for non-conductive liquids |
| | Dishwasher pressure switch / air-bell sensor | | 8-20 EUR [U] | Cheap and proven for tank level |
| Turbidity | TSD-10 module / dishwasher "Aquasensor" | optical | 8-40 EUR [U] | use to judge rinse-clear |
| Door/ lid | Reed switch (dry deck); coded magnetic safety switch (Pilz PSEN, Schmersal, Euchner), PL d | | reed 2-5 EUR; safety 60-120 EUR [U] | Automatic hatch = safety function |
| Box ID | **NFC NTAG213/216 laundry/ industrial tags** (13.56 MHz, ISO 14443A; PPS "laundry" tags survive 85-90 C washes and 150 C dryers [U]) | 4-8 cm read range | 0.5-2 EUR each [U] | HF works at -25 C freezer; UHF (860 MHz) water-detunes and cross-reads: avoid |
| | **Moulded or engraved AprilTag / DataMatrix / QR** (laser-engraved on stainless or PP lid, or moulded into the printed box; contrast) | camera at 20-100 mm, 1-2 mm modules | ~0 EUR; laser engraving 0.5-3 EUR/part [U] | Dishwasher/freezer-proof if engraved, not printed labels. Use 2 codes: engraved tag + NFC redundancy |
| Current | INA226 (bus 36 V, 16-bit) or INA219 | +/-0.5 % | 3-8 EUR [U] | motor/ heater load monitoring; ACS712 is noisy |
| | Shelly Pro 3EM / Eastron SDM120 (Modbus) | | 25-50 EUR [U] | mains energy for load shedding |
| Smoke/gas | Photoelectric smoke alarm EN 14604 with relay output (Ei Electronics Ei650 etc.) | | 20-40 EUR [U] | needed for unattended cooking |
| | Electrochemical CO sensor; SGP30/ SCD40 (CO2/ VOC) | | 15-40 EUR [U] | MQ-x sensors: drift, do not rely on them |

Sensor-quality rules: everything in the wet/hot zone is either (a) a stainless/PPS/PEEK-housed industrial sensor with IP67+ or (b) behind a window. Consumer-grade PCBs (HX711, VL53L1X modules) live in the dry deck in potted enclosures with stainless bulkhead glands.

---

## 7. Water components

### 7.1 Legal frame for the water inlet

* Household appliances directly connected to the drinking-water network need a **backflow protection according to EN 1717 (DIN EN 1717)**; the standard groups liquids in five categories; minimum for category 2 (e.g., washing/dishwashing without chemicals in the appliance) is a **controllable non-return valve type EA** (EN 13959, brass housing, max 10 bar, up to 90 C [V]); Type EA/EB protects up to category 2 [V]. Dishwashers and washing machines for domestic use are typically protected with an EA valve or integrated air gap [V].
* This kitchen doses detergent/rinse aid and possibly steam generator, and has multiple outlets into containers: treat as **category 3** (low health hazard, e.g., detergent-dosing) or worse if bulk boiler additives are used. Types allowed for category 3: air gap (type AA/AB/AD; EN 13076 type AA), or a **system separator BA** (EN 12729, category 4 also) [U]; EA is NOT sufficient for category 3.
* **Preferred design** (simplest, cheapest, silent): a **break tank with type AA free air gap** (tap filling the tank with a min. air gap of 20 mm or 2 x inlet diameter [U], float valve) and a pump feeding the machine from that tank. Consequences: (a) legal safety without an expensive BA separator (BA units cost 150-400 EUR [U]); (b) machine water pressure independent of the 2.2-5 bar mains, so no pressure reducers needed; (c) permits use of dishwasher pumps as feed pumps; (d) tank cleaning: needs CIP (heat, detergent) and an overflow with siphon into the drain (drain height per DIN EN 274; overflow must be above the waste outlet).
* Also required (DIN 1988-100, EN 806): shut-off valve upstream (angle valve), filter (mesh 90 micrometre [U]), and **Aquastop** (electronic solenoid inlet plus leak detection).
* Drain: trap (Siphon, EN 274) with air gap or backflow loop for the dishwasher drain hose (loop min 600 mm above floor or "Rueckstauschleife").
* Solenoid valves and wetted parts touching drinking water should carry KTW-BWGL/ DVGW W270 (hygiene) or WRAS/ NSF-61 markings; DVGW/KTW-approved parts are available from dishwasher and washing-machine spare parts (below) and from Bürkert/ Parker/ ASCO/ Danfoss.

### 7.2 Components

| Function | Part | Spec | Price | Notes |
|---|---|---|---|---|
| Fill valve (drinking water) | **Dishwasher/washing-machine double inlet valve** 230 V AC (Bosch, Miele, generic spare) | 3/4 inch, 0.3-10 bar, 230 V, KTW [U] | 8-15 EUR [U] | Cheap, certified as part of household appliance. Switch with SSR. 24 V DC coil versions exist [U]. |
| | Bürkert 0330 / 6013 / 6027 (brass/ stainless, FKM/EPDM), ASCO 262 (DVGW), SMC VXZ | 24 V DC, 1/2 inch | 70-150 EUR [U] | Long life, KTW. |
| | Generic Chinese 24 V stainless/brass valve, 1/2 inch | | ~35 EUR (FSA "E-1/2-24-O") [V] | No KTW/ DVGW: not for drinking water. Use for non-potable spray after the break tank. |
| Backflow | EA controllable non-return valve (SYR, Caleffi, A+K Mueller 49.0xx) | up to 10 bar, 90 C | 15-40 EUR [U] | Category 2 only. |
| | Break tank / air gap unit AA (Geberit, Viega) | | 30-150 EUR [U] | Category 3-5. |
| | System separator BA (Syr, Honeywell BA295, Watts) | | 150-400 EUR [U] | if a break tank is not used. |
| Pressure reducer | 1/2 inch, 1.5-6 bar (Honeywell D04, Syr) | | 25-60 EUR [U] | Mains 2.2-5 bar is already low: only needed after mains for nozzles requiring 2 bar; the break-tank scheme removes the need. |
| Circulation pump | **Dishwasher heater/ circulation pump** ("Heizpumpe") Bosch/Siemens/Miele | 230 V, 0.3-0.8 bar, ~15 L/min, integrated 2 kW heater in the heater-pump variant | **used 20-50; original 85-143** [V] | Proven, cheap, hygiene-tested; mounting flange standard; brushless variants (EC) exist |
| Drain pump | Dishwasher drain pump (Copreci, Hanning, Askoll), 230 V AC, 30-40 W | | 8-25 EUR [U] | |
| Diaphragm pump | Shurflo 12 V, 3.8 L/min, 7 bar (food-grade heads exist) | | 50-90 EUR [U] | dosing, high-pressure nozzle |
| Peristaltic dosing pump | Kamoer NKP 24 V (food-grade tube), ~ 30-200 mL/min | | 20-40 EUR [U] | dosing detergent/ liquid ingredients; tube replacement |
| Gear pump | small oil/ liquid pumps | | 30-60 EUR [U] | oils |
| Water heater | Flow-through heater from dishwashers; **or** 2 kW stainless immersion heater in break tank (Fritz, Backer, ~30-60 EUR [U]) | | 20-60 EUR [U] | do not use a 3.5-27 kW instant heater (Clage, Stiebel) on a 16 A circuit |
| Steam | mini steam generator (Miele/ Bosch spare) | 1.2-1.8 kW | 60-120 EUR [U] | |
| Spray nozzles | Dishwasher spray arm (Miele, Bosch, generic) | | 8-30 EUR [U] | proven spray pattern; spray-ball (Lechler, Bete, Spraying Systems) 316 SS | 20-100 EUR [U] | Use in tool/vessel washer |
| Hoses & fittings | John Guest Speedfit / Push-fit (PP/ acetal, 8/10/12/15 mm; WRAS/ NSF/ KTW available), Festo/ Legris | 10 bar, 65-95 C | 2-8 EUR/fitting [U]; hose 0.5-3 EUR/m | Push-fit ok in dry deck; in wet/food zone use welded, hygienic clamp (Tri-clamp) or hygienic fittings |
| Food-grade hose | silicone / PU / PTFE | | 2-8 EUR/m [U] | |
| Leak sensor | Aquastop hose with safety valve (double wall, VDE) | 3/4 inch, 1.5-4 m | 15-55 EUR [V] | recommended default inlet |
| | Conductive floor sensor / drip-tray float (Aqara, Shelly Flood, Zigbee) | | 15-25 EUR [U] | + normally-closed inlet valve |
| Level in break tank | 3 float switches (min, max, overflow) | | 3x8 EUR [U] | |

Note on the water/temperature limits: dishwasher pumps are rated up to 70-75 C water; do not run 100 C steam through them.

---

## 8. Control electronics and software

### 8.1 Host computer

* **Raspberry Pi 5 8 GB: EUR 218.90 gross (Reichelt, in stock)** [V]; Pi 5 price increases due to LPDDR4 shortage: 2 GB +$10, 4 GB +$15, 8 GB +$30, 16 GB +$60 (announced 2 Feb 2026) [V]; production guaranteed until at least January 2036 [V]. The 16 GB model lists at $305 [V]. 4 GB at ~ EUR 100-130 is probably enough for Klipper + camera + recipe engine [U].
* Alternative: fan-less industrial Intel N100 mini PC (8-16 GB, 128-256 GB SSD), 130-250 EUR [U], runs ROS 2, Home Assistant, Klipper; no RPi supply issues; 10-15 W.
* Also Orange Pi 5 / Radxa; CM5 modules with carrier boards; pick per availability.
* Operating conditions: heat sink or fan advised [V]; the electronics compartment must be ventilated and separate from the steam zone.

### 8.2 Motion controllers

| Family | Boards / prices | Strengths | Limits |
|---|---|---|---|
| **Klipper** (3D-printer firmware; Python host + MCU) | BTT Octopus Pro from **$62.99** (8 drivers, STM32; 48/60 V variants), BTT Manta M8P from $49.99 (needs CB1/CM4, $25+), EBB36 Gen2 CAN toolhead $47.99, U2C V3 USB-CAN $28.99 [V] | Multi-MCU, CAN toolheads (EBB36 with 3 outputs, thermistor input, stepper), huge community, cheap, Moonraker REST API, G-code macros, pressure advance not needed; heaters with PID; cartesian/ corexy/ custom kinematics via "manual_stepper" and "extra kinematics" | Not a safety-rated system; real-time only in MCU; step/dir only (external closed-loop drivers OK: Octopus has step/dir headers); homing switch per axis; limited inverse kinematics for arms (community plug-ins) |
| Duet 3 (RepRapFirmware): 6HC ~250-300 EUR [U], CAN-FD expansion boards | Mature, dozens of axes, closed-loop step/dir support (CL-stepper plug-in with Duet3 "closed loop" for 1LC boards) | costs 3-5x Klipper board; smaller community for custom needs | |
| LinuxCNC + Mesa (7i96S etc., ~120-200 EUR [U]) | Real-time CNC with kinematics modules, 5-axis | needs real-time Linux tuning, x86; more setup | |
| grblHAL / FluidNC (ESP32) | 10-50 EUR [U] | trivial, GRBL; 3-6 axes; WiFi | no coordination of many accessories |
| ODrive S1 ($149 [V]) / moteus / VESC | closed loop BLDC, CAN | fast; torque control; for high dynamic axes | need motors + encoders |
| EtherCAT (Beckhoff EK1100 + EL7031 or Chinese closed-loop stepper/ servo drives: StepperOnline, Leadshine, Delta ASDA-B3, JMC 150-500 EUR each [U]) | deterministic multi-axis coordinated motion, DC clocks; open-source master (IgH/SOEM), LinuxCNC/ROS 2 ros2_control support | | higher cost; harder cabling; fewer hobby resources |
| PLC (Siemens LOGO! ~150-250 EUR; Arduino Opta ~ 160-250; Wago PFC/ CODESYS ~400+ EUR [U]) | rugged 24 V IO, safety-certified variants | good for interlock, valves, pumps, heaters | poor for motion |

Field buses: CAN (Klipper toolheads, CANopen, 1 Mbit/s up to 25 m, 250 kbit/s up to 250 m [U]); RS-485 Modbus RTU (cheap, 9,600-115,200 bit/s; hobs, meters, VFDs; ok for slow setpoints); EtherCAT; I2C only inside the enclosure.

### 8.3 Actuator/heater switching

* Contactors/ relays: 24 V DC coil 16-25 A relays (Finder 40.52, 6-10 EUR [U]); DIN-rail relay modules 4-16 channels (10-40 EUR [U]).
* SSR for heaters/ valves: Carlo Gavazzi RA/RGC (25-40 A, 25-40 EUR [U]); avoid cheap Fotek SSRs (counterfeits) [U]; zero-crossing burst-fire for resistive loads.
* Motor drivers: TMC2209/TMC5160 (5-12 EUR, in Octopus), CL57T-V41 closed loop, ClearPath.

### 8.4 Safety chain

* Standards: household part follows EN 60335-1 / EN 60335-2-xx; the moving machine part (gantry with an automatic hatch and human reach into the dishwasher zone) counts under the **Machinery Directive 2006/42/EC; replaced by Regulation (EU) 2023/1230 from 20 January 2027** [U]; risk assessment per EN ISO 12100; safety functions per EN ISO 13849-1 (PL d typical for guard interlocks/ e-stop).
* E-stop: red mushroom E-stop per EN ISO 13850, contact 22 mm (Schneider XB4, Eaton RMQ) ~10-15 EUR [U] -> **safety relay** (Pilz PNOZ s3/ PNOZ e1p, Schmersal SRB, Dold, Sick; ~120-250 EUR [U]) -> opens the motor DC bus contactor and heater/ valve supply (STO by cutting 48 V supply / drive enable).
* Guards: coded magnetic safety switches at every service door; light curtains not needed: the human-facing hatch is small.
* The kitchen also needs **fire safety measures**: hob temperature limiting by hardware thermostat, thermal fuse, thermal imaging watchdog, smoke alarm with relay to cut power, fire blanket dispensing? (design decision in D9).

### 8.5 Power supplies

* 24 V for logic, valves, sensors: Mean Well LRS-350-24 (24 V 14.6 A, 35-50 EUR [U]); 48 V for motors: Mean Well LRS-350-48 (48 V 7.3 A), or RSP-750-48 (16 A), 45-110 EUR [U]. Closed-loop steppers: 24-48 V [V]; ClearPath 24-75 V [V]; ODrive 12-48 V [V].
* 5 V: DIN rail 5 V/5 A for Raspberry Pi 5 (official Pi 5 supply 27 W is 5 V 5 A [V]); or 24->5 V buck (Mean Well DDR-30, 12 EUR [U]).
* Use UPS/ ride-through: a small 24 V battery/ supercap for controlled shut-down on power loss; Raspberry Pi corruption on power fail.

### 8.6 Power budget on one 230 V, 16 A circuit

Nominal capacity 230 V x 16 A = 3.68 kW; continuous design limit 80 % = 2.9 kW [U] (breaker vs cable heating).

| Load | Power | Duty | Comment |
|---|---|---|---|
| Induction hob zone 20 cm | 1.4-3.7 kW (2.3 kW typical simmer/ boil) | cooking | main consumer |
| Oven (built-in) | 2.2-3.5 kW (steam ovens 2-3 kW) | preheat 10 min then 30 % duty | |
| Dishwasher (household) | 1.8-2.4 kW heater | 10-15 min per cycle (heat) | plus 100 W pump |
| Fridge + freezer | 100-200 W average, 300 W start | continuous | |
| Motion (all axes, mean) | 100-300 W (peak 600-1000 W) | | |
| Controller (Pi + boards + cameras) | 30-60 W | continuous | |
| Vacuum pump, valves, pumps | 50-300 W | intermittent | |
| Break-tank heater 2 kW | 2 kW | intermittent | |

* **Conclusion:** on one 16 A circuit, hob + oven + dishwasher heating cannot run simultaneously (5-9 kW). Options: (1) ask the customer for a **400 V 3-phase 16 A (11 kW) "Herd" circuit** for hob/oven plus 230 V/16 A for electronics, dishwasher, fridge; (2) load-management by the controller (one heater at a time; hob power limit set in hob menu to 2.3-3.0 kW [U]; measure with Shelly Pro 3EM / SDM120); the recipe planner treats power as a schedulable resource. Design decision is for A1 and requirements Q1.

### 8.7 Software stack

* **ROS 2** (Jazzy Jalisco LTS, supported to 2029 [U]) with **MoveIt 2** only where an arm is used; ros2_control for gantry axes; behaviour orchestration with **BehaviorTree.CPP v4** or **py_trees** (both permissive licences [U]); state machines with SMACH/YASMIN/FlexBE [U].
* Klipper/Moonraker handle low-level gantry motion; a ROS/ Python node sends G-code or `manual_stepper` commands via Moonraker (REST/WebSocket). Alternative: skip ROS at first; a plain Python service + MQTT + SQLite is simpler.
* **Home Assistant** as UI/ integration hub: has Home Connect, Miele, SmartThings, MQTT, ESPHome, Zigbee integrations [V]; Node-RED for glue.
* Vision: OpenCV 4.x (AprilTag via `apriltag`/ OpenCV aruco), Depthai for OAK-D, pyzbar/ zxing for barcodes, YOLO models on OAK/ Hailo-8L (Pi AI Kit, ~70-90 EUR [U]) for ingredient recognition.
* Recipe format: schema.org/Recipe JSON-LD for import, augmented by an own unit-operation graph (see R2) executed by behaviour trees; product database: Open Food Facts (R7).

---

## 9. Appliance control: off-the-shelf appliances and their APIs

| Ecosystem | Brands | API | Remote start of programs | Hob | Oven | Dishwasher | Fridge | Notes |
|---|---|---|---|---|---|---|---|---|
| **Home Connect** | Bosch, Siemens, Neff, Gaggenau, Constructa | Official cloud REST API (OAuth2, developer account, Server-Sent Events); HA integration [V] | Requires user to enable "Remote Start" on the appliance; API cannot bypass | **Remote start not permitted** (safety level "red", local jurisdiction/safety regulations); cooktop program support "not planned" via API [V] (settings/state read only) | Programs with setpoint temperature and duration possible [V]; safety level "yellow": user must push "Remote Start" each time; stays active 15 min even if door opened, but later door opening cancels it [V] | Start/select programs via API when Remote Start enabled [V] | Read temperatures, door; set super-cool (some) [U] | **Rate limits: 1,000 calls/day per client and user, 50 calls/min, 5 program starts/min, 10 req/s; SSE messages do not count** [V]. Cloud only; no local API [U]. |
| **Miele@home 3rd Party API** | Miele | Official cloud REST API (developer.miele.com), OAuth; all app devices reachable; "professional/ semi-professional series not supported" [V] | START/STOP/ startTime via processAction "when appliance offers it"; user must activate "MobileStart"/remote control on the appliance [V] | **Hobs monitor only: plates can only be monitored, not controlled** [V] | Oven program action with temperature setting [V] | start/pause/stop [V] | temperatures, supercool/ superfreeze switches [V] | Needs Miele CloudService; Zigbee models via Miele@home Gateway XGW3000 [V]. A LAN option via XKM module exists in community integration (ha-miele-at-lan) [U]. |
| **Samsung SmartThings** | Samsung | SmartThings REST API; oven timed cook start possible for electric ovens; **gas oven cannot be turned on remotely** [V]. **Free API access to be phased out from October 2026; paid Personal Plan $4.99/month** [V] | | induction hob: limited/ no | timed cook via API [V] | | | subscription risk |
| **LG ThinQ** | LG | ThinQ Connect API launched Dec 2024; documentation says partner agreement (B2B) required [V]; (community reports personal PAT access; conflicting) | | | | | | check licence terms |
| **Tuya** | Chinese white label (Tuya-based induction cookers, sous-vide, air fryers) | Tuya Cloud API + local LAN protocol (tinytuya, [U]); standard instruction set for induction cooker category exists [V] | Vendor-dependent: power on/ temperature | some models remote-startable [U] | | | | Cheap OEM appliances; certification for unattended operation unclear |

Design implications:

* **Nothing off-the-shelf allows the machine to start a hob autonomously.** Hobs: Home Connect "red", Miele read-only. This is a regulatory design (EN 60335-2-6 / IEC 60335-2-6: remote operation restrictions [U]) not a technical gap. Options: (A) the machine itself physically operates the hob knob/ touch surface (fragile, not recommended); (B) use a **non-domestic, integrated induction module** (OEM/ commercial single-zone induction with RS-485/ Modbus, 0-10 V or PWM power control, e.g., commercial "table-top" induction units and OEM heating boards 1.5-3.5 kW, 150-500 EUR [U]) that becomes part of the machine and is certified in the machine's own risk assessment; use pan-presence detection, thermocouple/ IR feedback, boil-dry cut-off, and a supervisor over the thermal camera; (C) cook in an oven/ steam oven where remote start is allowed (yellow level) and the door/human interlock is the user's job. Requires further legal study (R6 / D5).
* Ovens: remote start must be enabled by the human at the oven every time (yellow): not unattended-friendly. For the machine, "oven" would be operated as a part with the human giving remote-start once per session, or the machine uses a custom oven module (e.g., small combi-steamer, commercial).
* Dishwashers: **the human loads and starts** anyway; the API is useful for status/ programme/ end-of-cycle notification. For the machine's own tool washer, use a machine-internal dishwashing circuit (section 7), not an appliance.
* Fridge/ freezer: read temperature and door state via API; no control of the door. The box exit hatch is our own hardware.
* Rate limit design: 1,000 Home Connect calls/day; use the SSE stream and poll no more than every 90 s [V arithmetic: 24 h x 60/90 = 960].

---

## 10. 3D printing

### 10.1 Printers

| Printer | Chamber | Max nozzle / bed | Price | Notes |
|---|---|---|---|---|
| Bambu Lab P1S / X1C | enclosed, 256^3 | 300 C / 110 C | ~600-1,300 EUR [U] | reliable; AMS multi-material; hardened nozzle for CF |
| Bambu Lab H2D | heated chamber (65 C), 350x320x325 | 350 C | ~2,000-2,500 EUR [U, page not retrieved] | for PA-CF/PPS-CF |
| Prusa Core One / Core One L | enclosed | 290 C | ~1,000-1,800 EUR [U] | open firmware; good for PETG/ASA/PA |
| Voron 2.4 (self-build) | 350^3 | 300 C | 1,200-1,600 EUR [U] | Klipper native, same ecosystem as the machine |
| Large format (Creality K2 Plus, Prusa XL) | | | 1,500-3,500 EUR [U] | for 600 mm parts |

Build a **printer farm** in the project: same Klipper/CAN parts as the machine itself (interesting: one BTT ecosystem).

### 10.2 Materials (typical; 1.75 mm, values are datasheet-typical [U])

| Material | Heat deflection (HDT 0.45 MPa) / continuous | Strength | Chemical/ hygiene | Price EUR/kg | Sensible parts |
|---|---|---|---|---|---|
| PLA | 55 C | high stiffness, brittle | dissolves/warps in dishwasher | 18-25 | prototypes only |
| **PETG** | 70-80 C / 65 C max; dishwasher ~ borderline | tough, layer adhesion good | alkali-resistant, ok for splash zone; not steam | 20-28 | brackets, covers, guides, jigs in dry/ splash zone |
| **ASA** | 95-100 C / ~85 C | UV/heat stable, good layer adhesion | resists detergents better than ABS; not food-safe by default | 25-35 | housings, gripper fingers, wash-zone mounts |
| PC / PC-CF | 115-140 C | high | absorbs water little | 40-70 | tools near oven door |
| PA6/PA12 (dried) | 80-100 C dry | tough | **hygroscopic (PA6 up to 9 % water): dimensional change and weakened when wet**; PA12 less (1.5 %) | 40-60 | gears, bushings (PA12) in dry/ humid; avoid in dishwasher |
| **PA-CF (PA12-CF / PA6-CF)** | 150-180 C (PA6-CF, dry) | very stiff (like aluminium in stiffness/ weight), no creep | moisture same as PA; CF conductive; abrasive (needs hardened nozzle) | 60-100 | stiff brackets, carriage plates, gantry connectors, jigs |
| **PP / PP-GF** | 100-110 C, continuous 90-100 C | fatigue-resistant, living hinges | **dishwasher-safe, chemical resistance excellent, low water absorption**; FDA-grade natural PP exists | 35-70 | food-side parts, lids, clips, funnels (with printing via PP-capable printer, bed adhesion problem) |
| TPU 95A (or 90A) | 60-80 C (soft), 100 C short | elastic 300+ % | chemical resistance ok; not FDA-certified for most | 30-45 | seals, gripper pads, damping, gaskets (unless certified) |
| PPS-CF / PEEK / PEI (Ultem 1010, Kimya) | 200-250 C | very high | steam/ chemical proof; **Ultem 1010 is food contact certified** [U] | 200-400 | only in very special hot-zone parts |

Rules:
* **Food-contact FDM parts are hygienically dubious**: layer lines (50-200 micrometre grooves) and voids harbour bacteria; 3D-printed PLA/PETG is generally not accepted as food-contact material unless printed with certified filament AND sealed/ coated (e.g., food-safe epoxy coating (EU 10/2011 declared) or ironing/ vapour smoothing) or replaced by SLS/MJF PA12 + coating, or by injection moulded/ machined parts (R6 covers this). Use printing for **jigs, brackets, cable guides, covers, drip trays, sensor housings, spacers, gripper fingers with replaceable liners, carriage plates, gears in the dry deck**.
* Not sensible to print: pressure vessels, heated parts above ~90 C (use metal), hygienic surfaces, screws/ threads (use heat-set brass inserts M3-M8, 0.05-0.15 EUR each [U]; in wet areas stainless inserts), load-bearing shafts, sliding surfaces without dry lube (use igus iglidur bushings, or printed iglidur i150/i180 filament [U]).
* Print settings: >= 4 walls, 40-60 % gyroid infill, print in the load direction; PETG 240 C / 80 C bed; ASA 250 C / 100 C chamber warm; PA-CF 280-300 C dried 80 C 8-12 h; annealing raises HDT in PETG/PA.
* Tolerances: printed holes -0.1 to -0.3 mm; use 4-5 % oversize, design for M3 heat-set.

---

## 11. Recommended default choices ("house standard")

The engineers should pick from these unless the module design explains why not.

| Category | Default | Why | Price |
|---|---|---|---|
| Frame extrusion | **Motedis-type B-type, slot 8: 40x40 (primary, uprights, beams) and 30x30 (secondary), same M8 drop-in T-nuts, angle brackets and slot covers**; 40x80 for long spans. item Profile 8 is a like-for-like alternative only where groove 10 mm and item load data are needed. | Cheapest, cut-to-length service, one T-nut for both sizes | 30x30: 7.81 EUR/m net [V]; 40x40: 13.29 EUR/m net [V]; T-nut M8 ~0.15 EUR [U]; cover strip ~0.8 EUR/m [U]; brackets ~1.5 EUR [U] |
| Panels | 1.5 mm 304 stainless (brushed) for wet/ splash surfaces; 8 mm HPL compact for housing panels; 4 mm polycarbonate for windows; no aluminium composite in wet zone | | 60-110 EUR/m^2 (304), 60-120 (HPL), 25-45 (PC) [U] |
| Linear rail | **15 mm miniature profile rail: MGN15H** (H1 grease) for dry-deck axes, box-carrying axes and Z; step-up to HGR15 only for the largest loads; **igus drylin W hygienic (316 rail, iglidur A160)** in the wet zone; two 12 mm shafts + iglidur bearings for cheap short axes | one rail family (15 mm) in the dry deck; igus is the only washable one | MGN15H 10-15 EUR/m + 8-15 EUR/block [U]; igus hygienic quote (>150 EUR/m [U]) |
| Belt | **HTD 5M 15 mm** (fibreglass) for axes up to 2 m; **AT5 25 mm steel-cord PU** for 2-5 m; GT2 10 mm for light axes and tool actuators; 20-tooth pulleys; central motor drive on axes > 2 m | | 4-8 / 10-25 / 1-2 EUR/m [U] |
| Vertical axis | Tr8x2 lead screw or TR10x2 with igus/ brass nut + 2 profile rails, or belt + counterweight/ brake | self-locking for safety | 10-15 EUR/m [U] |
| Motors | **NEMA23 closed-loop stepper (2-3 Nm, CL57T-V41 driver, 48 V)** for all box-carrying axes; **NEMA17 open loop (TMC2209, 24 V)** for tools, small actuators; **ClearPath SD (IP66K option)** where a motor is exposed | closed loop = no lost steps; cheap | $64-87 per kit [V]; $338 ClearPath [V]; NEMA17 6-12 EUR [U] |
| Controller | **Klipper on Raspberry Pi 5 (4 or 8 GB; or N100 mini-PC)** + **BTT Octopus Pro** main MCU + **EBB36 CAN toolheads/ remote IO** + U2C (CAN); Modbus RS-485 for hobs/ meters; ESP32 (ESPHome) for peripheral boards; hard-wired safety chain outside the software | one firmware and one board family for the whole machine | Pi 5 8 GB 218.90 EUR [V]; Octopus Pro $62.99+ [V]; EBB36 $47.99 [V]; U2C $28.99 [V] |
| Power | 24 V 350 W and 48 V 350-750 W Mean Well DIN-rail; safety relay + contactor | | 35-110 EUR each [U] |
| Fasteners | **A2-70 stainless, metric ISO 7380 button head (hex) M3, M4, M5, M6, M8**, DIN 6923 flange nuts, DIN 125 washers, heat-set inserts M3/M4/M5 for printed parts, M8 drop-in T-nuts; one 2.5 mm/3/4/5/6 mm hex key set; 316 in wash zone; no Phillips/ slotted heads | one tool set; A2 corrosion resistance; button heads have fewer edges to clean than ISO 4762 | ~0.05-0.15 EUR/screw [U] |
| Water | Break tank AA + feed pump from a dishwasher circulation pump; Aquastop inlet; inlet valve from a dishwasher; drain pump from dishwasher; nozzles from dishwasher spray arms | legal and cheap | see 7.2 |
| Vacuum | 12/24 V brushless diaphragm pump + 1 L reservoir + valve + silicone bellows cups | no compressor | 100-300 EUR [U] |
| Tool interface | Jubilee-style kinematic dock + latch, 1/4 inch hex rotary drive | | 30-60 EUR per tool [U] |
| Box ID | engraved AprilTag/ DataMatrix on box + embedded NFC NTAG (laundry type) | dishwasher/ freezer proof | 0.5-3 EUR per box [U] |
| Camera/ vision | Pi Camera 3 + OAK-D Lite for depth/ AI; MLX90640 for thermal safety | | 40 / $269 / $75 [V] |
| Printer | 1-2 enclosed printers (Prusa Core One or Bambu P1S/H2D or a Voron), PETG/ASA default, PA-CF for stiffness, PP for food-side | | 600-2,500 EUR [U] |

Indicative cost of a "one-axis kit" (rail + carriage + belt + closed-loop motor + driver + PSU share) for a 2 m axis: MGN15H 1 m rails (2 of them) ~30 EUR; block 2x ~20; belt/pulleys ~30; NEMA23 CL kit ~75; frames ~40 = about 200-250 EUR per axis [U], vs ~800-1,200 EUR with igus ZLW plus motor [V/U]. A whole gantry XYZ over 4 m: ~ 700-1,200 EUR [U].

---

## 12. Sources

Key URLs consulted (2026-09-30):
* Motedis 30x30 B-type slot 8 (7.81 EUR/m net): https://www.motedis.com/de/Aluprofil-30x30-B-Typ-Nut-8 ; Motedis profiles: https://www.motedis.com/de/Aluprofile ; 20x20 / 40x40 prices from search snippets: https://www.motedis.ch/de/Aluprofil-20x20-B-Typ-Nut-6 , https://www.motedis.com/de/Aluprofil-40x40-1N-I-Typ-Nut-8
* item Profile 8 40x40 (1.82 kg/m, Ix 9.5 cm^4, up to 6 m): https://www.item24.com/de-de/profil-8-40x40-2n90-leicht-natur-40450
* EN 1116 references: https://webstore.ansi.org/standards/din/dinen11162018de , https://www.bdb.at/Service/NormenDetail?id=628103 , https://www.hea.de/fachwissen/kuechenplanung/planungsgrundlagen , https://www.amk.de/wp-content/uploads/2025/02/AMK-Merkblatt-016_2025-02.pdf , https://www.lieblingskuechen.de/hoehe-kuechenschraenke/
* igus ZLW technical data: https://www.igus.eu/drive-technology/linear-axes-with-toothed-belts/technical-data ; ZLW-1040 page: https://www.igus.co.uk/info/linear-guides-zlw-1040 ; ZLW-1040-S: https://www.igus.eu/product/22555
* igus hygienic drylin W: https://press.igus.eu/clean-safe-lubrication-free-igus-presents-the-hygienic-design-linear-guide/ ; https://www.igus.com/linear-bearings/news/n22-hygienic-dual-rail-system ; https://www.igus.com/industry/food-and-packaging/fda-and-eu-compliant-products
* HepcoMotion PRT2: https://www.hepcomotion.com/product/curved-rails-and-track-system-components/prt2-precision-track-systems/
* MGN12H prices: https://kb-3d.com/store/motion/377-kb3d-mgn12h-linear-rail-guide-with-carriage-multiple-lengths-1646161437836.html , https://www.opulo.io/products/mgn12h-linear-rail-kit ; Misumi: https://us.misumi-ec.com/pdf/fa/2014/p1_0533.pdf
* StepperOnline closed loop: https://www.omc-stepperonline.com/closed-loop-stepper-driver-v4-1-0-8-0a-24-48vdc-for-nema-17-23-24-stepper-motor-cl57t-v41 ; Easy Servo: https://www.amazon.com/STEPPERONLINE-Integrated-3000rpm-42-49oz-20-50VDC/dp/B09LCGZT46
* Teknic ClearPath SD: https://teknic.com/model-info/CPM-SDSK-2311S-ELN/ , https://teknic.com/nema-23-nema-34-servo-motors/
* ODrive S1: https://shop.odriverobotics.com/products/odrive-s1
* BTT boards: https://west3d.com/collections/bigtreetech-btt , https://biqu.equipment/products/bigtreetech-ebb36-42-can-bus-u2c-v2-1-klipper-board
* Raspberry Pi 5: https://www.reichelt.com/de/en/shop/product/raspberry_pi_5_b_4x_2_4_ghz_8_gb_ram_wlan_bt-359846 ; https://www.raspberrypi.com/news/more-memory-driven-price-rises/ ; https://www.raspberrypi.com/products/raspberry-pi-5/
* Arms: https://www.igus.com/product/21465 , https://rbtx.com/en-US/components/robots/rebel-cobot-6-degrees-of-freedom-reach-664-mm ; https://www.robotshop.com/products/ufactory-6-axis-robot-arm-lite-6-kit ; https://www.generationrobots.com/en/472_ufactory ; https://www.fairino.be/product/fr3-collaborative-robot ; https://unchainedrobotics.de/en/products/robot/cobot/dobot-cr3 ; https://shop.elephantrobotics.com/collections/mycobot-280 ; https://anninrobotics.com/product-page/ar4-mk5-robot-combo-kit/ ; https://blog.igus.eu/smart-and-inexpensive-rebel-the-igus-cobot-for-automation-now-with-smart-plastics-technology/
* Grippers/ changers: https://unchainedrobotics.de/en/products/end-of-arm-effectors/grippers/finger-grippers/onrobot-rg2 , https://unchainedrobotics.de/en/products/end-of-arm-effectors/grippers/finger-grippers/robotiq-2f-85 , https://www.robotshop.com/products/dh-robotics-pgse-15-7-slim-type-electric-parallel-gripper-eoat , https://schunk.com/us/en/gripping-systems/parallel-gripper/egp/egp-25-n-s-b/p/000000000000310902 , https://www.ati-ia.com/products/toolchanger/QC.aspx?ID=QC-11 , https://www.researchgate.net/publication/341697828_Jubilee_An_Extensible_Machine_for_Multi-tool_Fabrication , https://jubilee3d.com/index.php?title=Locating_Tools
* Vacuum: https://www.smcpneumatics.com/ZH-VACUUM-EJECTOR_c_433.html , https://unchainedrobotics.de/en/products/end-of-arm-effectors/grippers/vacuum-grippers/piab-picobot , https://www.compressorpros.com/silent-air-compressors/
* Sensors: https://www.adafruit.com/product/4407 (MLX90640) ; https://shop.luxonis.com/products/oak-d-lite-1
* Water/ EN 1717: https://www.sbz-online.de/sanitaer/trinkwasserschutz-nach-din-en-1717 ; https://www.akmueller.de/produkte/detail/rueckflussverhinderer-typ-ea-ec-49-0xx-x26 ; https://www.syr.de/download/service/9.0002.02_Trinkwasserschutz_1525.pdf ; https://www.caleffi.com/sites/default/files/media/external-file/03195_DE_SICHERUNGSARMATUREN%20GEGEN%20R%C3%9CCKFLIESSEN.pdf ; https://www.ebay.de/b/Bosch-Geschirrspuler-Pumpen/116026/bn_13030017 ; https://www.smartgoods.de/zulaufschlauch-aquastop-4-0m-90-c-universal-fuer-waschmaschine-geschirrspueler.html ; https://www.ebay.de/p/913834250 (24 V 1/2" stainless valve)
* Appliance APIs: https://api-docs.home-connect.com/ , https://api-docs.home-connect.com/states , https://developer.home-connect.com/docs/general/ratelimiting , https://www.home-connect.com/global/inspiration/how-to-use-the-app/remote-start , https://github.com/thoukydides/homebridge-homeconnect/discussions/321 , https://www.home-assistant.io/integrations/home_connect/ , https://www.home-assistant.io/integrations/miele/ , https://developer.miele.com/docs/get-started , https://community.smartthings.com/t/samsung-oven-apis-for-setting-cooking-mode-setpoint-cooking-time/251558 , https://www.lgnewsroom.com/2024/12/lg-opens-thinq-api-to-foster-smart-home-innovation/ , https://developer.tuya.com/en/docs/iot/kitchen-appliances?id=Kaiuz2k9t5yq8

---

## Open issues

1. **Curved/corner motion parts unpriced.** HepcoMotion PRT2 and igus curved guides have no public prices; request quotes for a 90 degree segment (R300-R500, stainless) with a belt/chain drive before choosing between corner transfer cell and continuous track. Check whether igus has a curved hygienic drylin.
2. **Wash-down rated drives.** No verified IP66/69K motor below ~EUR 300 other than Teknic ClearPath with shaft seal ($338 [V]). JMC/StepperOnline IP-rated integrated servos, Oriental Motor and stainless steppers need a quote. Decide between "motors always in dry deck" (recommended) and "exposed IP67 motors".
3. **Verify [U] prices**: HGR15, belts (AT5 steel/ FDA PU), igus drylin W (standard and hygienic), Misumi stainless rails, load cells (stainless), moteus, JMC, Duet 3, FLIR Lepton, RealSense, Bambu H2D and Prusa Core One, tool changers new, silent compressors, Ultem filament. Search quota ended before these were checked.
4. **Power supply assumption**: brief says "220 V". Requirements must state whether a 3-phase Herd circuit is available; otherwise every heater is a schedulable resource on 3.68 kW.
5. **Induction hob safety concept**: no domestic hob may be started remotely (Home Connect red; Miele read-only). Decide whether to use an OEM/ commercial induction module with own certification, and get an expert opinion (EN 60335-2-6 clauses on unattended/ remote operation) [U]. Same for oven: remote start needs a human press each time (yellow).
6. **Water law**: confirm with a Trinkwasser installer/ DVGW how the machine is classified (EN 1717 category 3 vs. 5 due to steam generator/ chemical dosing); the break-tank AA solution is my recommendation, not a certified design.
7. **Raspberry Pi 5 pricing/ supply** is volatile (RAM crisis); confirm an alternate host (N100/ Radxa) in the control design.
8. **Regulation date**: Machinery Regulation 2023/1230 application date 20 Jan 2027 taken from memory [U]; verify.
9. **Niche dimensions** in section 1.2 are from manufacturer data sheets; verify against the purchased EN 1116:2018 text before freezing the interfaces.
10. **ReBeL IP class, food suitability, and FR5/ xArm IP ratings** not found: ask vendors if an arm stays in the plan.

## Risks

1. **Price staleness**: several [V] prices are from snippets (dated 2026) and market prices are volatile (memory-driven price rises, USD/EUR, import duties on Chinese parts: StepperOnline, BTT, AliExpress ship from China/ US warehouses with 3-14 days delivery).
2. **Hygiene of catalogue parts**: linear rails, belts, motors and push-fit fittings are mostly not hygienic designs; food/steam/detergent will eventually reach them unless the machine deck is sealed and slightly over-pressurised or air-swept. The design has to contain this, not the parts.
3. **Long-axis accuracy and stiffness**: 4-5 m belts stretch and aluminium beams sag (9 mm self-weight over 4 m); needs continuous rail supports, splice geometry, thermal expansion joints (aluminium 23 micrometre/m/K: 4 m x 20 K = 1.8 mm).
4. **Regulatory**: unattended cooking, remote-start bans and the drinking-water rules (EN 1717) can force redesigns late; a certifying body (CE, VDE/ TUV) is required for a product, not for a private build.
5. **Cloud dependency and subscriptions**: Home Connect (rate limits), Miele (cloud), SmartThings (paid from Oct 2026), LG (partners): APIs can change or be withdrawn; local fallbacks are needed for appliance state.
6. **Closed-loop steppers and Klipper**: step/dir external drivers lose direct fault feedback unless the alarm output is wired to an MCU input; Klipper has no built-in safety certification; PL d functions must be realised in hardware (safety relay).
7. **3D-printed parts in wet/ hot areas**: PETG creep above 60 C, PA absorbs water and changes dimensions, printed parts are porous for food contact; keep printed parts to the dry deck or coat/ replace.
8. **Robot arms are optional**: a design that silently assumes a 2 kg / +/-1 mm arm (ReBeL) would fail on payload, precision and hygiene.
9. **Single-source parts**: igus hygienic rails, Teknic and BTT boards have one supplier each; keep a second-source plan (MGN15H with H1 grease, StepperOnline closed loop, Duet 3).
