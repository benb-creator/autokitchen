# Meal preparation — Cost round 1: K9c design-to-cost revision of K9b

**K9c** is K9b SCHLICHT (`K9b-combined-simplest.md`) revised for cost (#28: machine part ≈ €2 k as the
target, not a hard limit), width and simplicity (#20). Function, hygiene rules (C2, #4) and coverage
target (#26: ≥ 93 %) stay binding. Decision state: DECISIONS #1–28.

Markers: **[D]** from K9b or an earlier document; **[W]** web price checked on 2026-10-01 (URL in §1.3);
**[E]** engineering estimate; **[C]** calculated here; **[U]** unknown, a test decides. Price convention:
EU retail or job-shop price for **one unit**, incl. VAT, own assembly labour not counted (K9b used
small-series prices ±30 %; the K9b split into lines below is this document's [E] and adds up to K9b's
block totals).

**Result**: machine part **€6,790 → €5,108** at K9b accounting (−25 %), **€4,733** with kitchen content
counted as household, **€4,313** with kitchen furniture also counted as household. Cell width 1750 → **1660 mm**;
still 6 motion actuators and 2 dynamic seals, ≈ 28 instead of ≈ 35 custom part types; coverage unchanged
(233 meals). Biggest cuts: printer-class gantry under Klipper, the donor dishwasher's own tub as the well,
Gastro table and liners as the enclosure, a €50 induction plate as the hub coil's generator. Remaining gap
to €2 k: €2.3–3.1 k; round 2 reaches ≈ €3.3–3.8 k (≈ €2.8 k in a series). §8 lists Ben's decisions.

---

## 1. Baseline: the K9b machine part, line by line

### 1.1 K9b machine part (K9b §7.4, blocks M1–M11, split into lines)

| # | Item | Qty | € each | € total | Source of estimate |
|---|---|---|---|---|---|
| M1.1 | X toothed-belt linear module 1.7 m, two profile rails, in the dry X box | 1 | 300 | 300 | K9b M1 [D], split [E] |
| M1.2 | Z ball screw 16 × 10 with brake on the hanging mast | 1 | 200 | 200 | [D/E] |
| M1.3 | Y belt module in the closed arm tube 70 × 70 × 620 | 1 | 120 | 120 | [D/E] |
| M1.4 | Closed-loop steppers 400 W class with drivers (X, Y, Z) | 3 | 70 | 210 | [D/E] |
| M1.5 | Sealing bands (Z rear face, Y top face) | 2 | 40 | 80 | [D/E] |
| M1.6 | X labyrinth slot and purge fan | 1 | 50 | 50 | [D/E] |
| M1.7 | Mast and arm tubes | 1 | 40 | 40 | [D/E] |
| M2.1 | Roll stepper + 20 : 1 planetary | 1 | 80 | 80 | K9b M2 [D], split [E] |
| M2.2 | Canned magnet coupling (welded 0.5 mm can, NdFeB inner and SmCo sleeve rotor, PEEK bushes) | 1 | 150 | 150 | [D/E] |
| M2.3 | Sleeve with bayonet bore and J-slots, reaction tab | 1 | 40 | 40 | [D/E] |
| M2.4 | Hall sensors (coupling lag = torque) | 2 | 5 | 10 | [D/E] |
| M2.5 | Sealed housing and 300 mm drop link | 1 | 20 | 20 | [D/E] |
| M3 | Arm-root single-point load cell 30 kg + amplifier | 1 | 60 | 60 | K9b M3 [D] |
| M4.1 | Hub drawn pocket Ø 120 × 60 and S thimble | 1 | 80 | 80 | K9b M4 [D], split [E] |
| M4.2 | T plug (magnets in a welded can, PEEK bush, lug slots) | 1 | 40 | 40 | [D/E] |
| M4.3 | NEMA 34 + 10 : 1 planetary + driver (T) | 1 | 130 | 130 | [D/E] |
| M4.4 | 600 W BLDC + driver (S) | 1 | 100 | 100 | [D/E] |
| M4.5 | Coaxial hollow shaft and bearings | 1 | 40 | 40 | [D/E] |
| M4.6 | Hub load cells + amplifier | 3 | 15 | 45 | [D/E] |
| M4.7 | Anchor post Ø 25 with fork | 1 | 15 | 15 | [D/E] |
| M5.1 | OEM ring induction coil Ø 135/280 with 2.5 kW generator | 1 | 220 | 220 | K9b M5 [D], split [E] |
| M5.2 | Glass-ceramic disc Ø 330 with Ø 130 hole and gasket | 1 | 80 | 80 | [D/E] |
| M6.1 | Welded insulated 1.4404 well tub 420 × 440 × 450 with combs | 1 | 420 | 420 | K9b M6 [D], split [E] |
| M6.2 | Lid-bench 460 × 460 with gas strut | 1 | 80 | 80 | [D/E] |
| M7.1 | Rinse cup with strainer basket and 4 rim jets | 1 | 80 | 80 | K9b M7 [D], split [E] |
| M7.2 | Turbidity sensor | 1 | 20 | 20 | [D/E] |
| M7.3 | Tap spout with flow meter | 1 | 20 | 20 | [D/E] |
| M7.4 | Chute with spring flap | 1 | 30 | 30 | [D/E] |
| M7.5 | Bin drawer 20 L | 1 | 30 | 30 | [D/E] |
| M8.1 | Stainless deck with cut-outs | 1 | 250 | 250 | K9b M8 [D], split [E] |
| M8.2 | X box (dry rear lane housing) | 1 | 150 | 150 | [D/E] |
| M8.3 | Walls and rear gutter | 1 | 350 | 350 | [D/E] |
| M8.4 | Glazed cell door with guard lock | 1 | 250 | 250 | [D/E] |
| M8.5 | Tool cabinet with spring flaps and box shelf | 1 | 200 | 200 | [D/E] |
| M8.6 | Oven mount | 1 | 50 | 50 | [D/E] |
| M8.7 | Hatch drawer: runners, solenoid lock, 150 W heater, 2 trays | 1 | 250 | 250 | [D/E] |
| M9.1 | Solenoid valves | 8 | 15 | 120 | K9b M9 [D], split [E] |
| M9.2 | Fixed nozzle rail | 1 | 60 | 60 | [D/E] |
| M9.3 | Fan dry | 1 | 40 | 40 | [D/E] |
| M9.4 | Piping | 1 | 80 | 80 | [D/E] |
| M10.1 | Controller (single board) | 1 | 150 | 150 | K9b M10 [D], split [E] |
| M10.2 | 3-phase power manager | 1 | 120 | 120 | [D/E] |
| M10.3 | Cameras with heated windows and white/UV-A light | 2 | 60 | 120 | [D/E] |
| M10.4 | Safety relay | 1 | 60 | 60 | [D/E] |
| M10.5 | Wiring | 1 | 150 | 150 | [D/E] |
| M11.1 | Bought pots, pans, GN, tins, processor discs | 1 | 500 | 500 | K9b M11 [D] |
| M11.2 | Stubs, drip collars, dog rings welded on ≈ 40 items | 40 | 10 | 400 | [D] |
| M11.3 | Press-cup kit with bought grids | 1 | 200 | 200 | [D] |
| M11.4 | Custom tools, fixtures and carriers | 1 | 500 | 500 | [D] |
| | **K9b machine part** | | | **6,790 ≈ 6,800** | K9b §7.4 (range 5,000–9,000) |

Block totals: M1 1,000 · M2 300 · M3 60 · M4 450 · M5 300 · M6 500 · M7 180 · M8 1,500 · M9 300 ·
M10 600 · M11 1,600.

### 1.2 K9b appliances (unchanged reference, K9b §7.4)

| Appliance | € |
|---|---|
| Induction domino 2 zones + interface board | 300 + 60 |
| Countertop combi-steam oven + control interface + float valve | 550 + 100 |
| Slim household dishwasher as wash-parts donor | 400 |
| 30 L under-sink water heater | 200 |
| Hob-extractor fan with baffle filter | 150 |
| Fridge + freezer | 1,000 |
| Shelving | 500–1,000 |
| **Appliances** | **≈ 3,260–3,760** |

### 1.3 Web prices checked (2026-10-01, EU shops, incl. VAT unless noted)

US$ prices converted at ≈ €0.88 per US$ [E]. Sale prices are marked; the BOM in §5 uses a normal price.

| # | Item | Price found | Shop and URL |
|---|---|---|---|
| P1 | Aluminium profile 40 × 40 I-type slot 8 | €17.17–20.43 per m | Motedis: <https://www.motedis.com/de/Aluprofil-40x40-1N-I-Typ-Nut-8>, <https://www.motedis.at/de/Aluprofil-40x40L-I-Typ-Nut-8> |
| P2 | MGN15 rail 1500 mm with MGN15H block | €139.78 | Amazon.de: <https://www.amazon.de/TEN-HIGH-Miniatur-Linearf%C3%BChrung-Linearschiene-Gleitst%C3%BCck/dp/B07M6JKJC4> |
| P3 | HTD 3M timing belt 15 mm, by the metre | €4.70–7.30 per m (PU with steel cords €7.30) | Dold Mechatronik: <https://www.dold-mechatronik.de/PU-Zahnriemen-HTD-3M-Breite-15mm-Meterware-Laenge-waehlbar> |
| P4 | NEMA 23 stepper 3 Nm (23HS45-4204S) | US$28.70 ≈ €25 | StepperOnline: <https://www.omc-stepperonline.com/nema-23-bipolar-3nm-425oz-in-4-2a-57x57x114mm-4-wires-stepper-motor-cnc-23hs45-4204s> |
| P5 | NEMA 23 3 Nm with 2 Nm holding brake (23HS45-4204D-B200) | US$50.56 ≈ €45 | StepperOnline: <https://omc-stepperonline.com/nema-23-stepper-30nm425ozin-w-brake-friction-torque-20nm283ozin-23hs45-4204d-b200.html> |
| P6 | NEMA 23 with 10 : 1 planetary (MG series / HG precision) | US$40 / US$83 ≈ €35 / €73 | StepperOnline: <https://www.omc-stepperonline.com/nema-23-stepper-motor-l-76mm-gear-ratio-10-1-mg-series-planetary-gearbox-23hs30-2904s-mg10> |
| P7 | Ball screw SFU1610 set with BK/BF12, nut housing, coupling; screw 1000 mm alone | €46 (set, eBay); €89 (screw 1 m) | <https://www.ebay.com/itm/314317684865>; DHM: <https://www.dhm-online.com/de/kugelgewindetriebe/1621-sfu1610-kugelumlaufspindel-100-cm.html> |
| P8 | Klipper board BTT Octopus Pro (8 driver slots) | €75 | Botland: <https://botland.store/motherboards-and-electronics-for-3d-printers/20840-bigtreetech-octopus-pro-v101-stm32f446zet6stm32f429zgt6-motherboard-for-3d-printers.html> |
| P9 | Stepper driver BTT TMC5160T Pro | €22.45–23.17 | HTA3D: <https://www.hta3d.com/en/tmc5160t-pro-spi-stepper-motor-controller-silent-driver> |
| P10 | Raspberry Pi 5, 4 GB (2026 memory prices); alternatives BTT CB1, Manta M8P V2 | €120.60; CB1 €40.99; M8P €79–89 | Reichelt: <https://www.reichelt.com/de/en/shop/product/raspberry_pi_5_b_4x_2_4_ghz_4_gb_ram_wlan_bt-359842>; 3DJake: <https://www.3djake.ie/bigtreetech/cb1>; Comprise: <https://www.comprise.de/en/bigtreetech-manta-m8p_36302_9379> |
| P11 | Raspberry Pi Camera Module 3 Wide | €35.90–39.90 | Welectron: <https://www.welectron.com/Official-Raspberry-Pi-Camera-Module-3-Wide>; BerryBase: <https://www.berrybase.de/en/raspberry-pi-camera-module-3-wide-12mp> |
| P12 | Load cell 30 kg (bar type) | €16.87 | Amazon.de: <https://www.amazon.de/Marhynchus-30-kg-elektronischer-W%C3%A4gezellen-Pr%C3%A4zisionswaagen-Gewichtssensor/dp/B082R62Y32> |
| P13 | Slim 45 cm dishwasher, freestanding, under-counter capable (Exquisit GSP9109-030E; Bomann GSP 7418) | from €268.60; from €349 | <https://www.preissuchmaschine.de/in-Geschirrspueler/45-cm-Breite/von-Exquisit/>; <https://testundtipps.de/kueche-lifestyle/kuechengeraete/spuelmaschine/spuelmaschine-45-cm> |
| P14 | Food processor Bosch MultiTalent 3 MCM3501M (800 W, bowl 2.3 L, blender 1 L, discs) | €89.99–109 | Geizhals: <https://geizhals.de/bosch-mcm3501m-food-processor-a1765842.html>; Amazon.de: <https://www.amazon.de/Bosch-MCM3501M-Multifunktions-K%C3%BCchenmaschine/dp/B015DR863C> |
| P15 | Gastro stainless work table 1800 × 600 with base shelf (GGM PREMIUM, sale) / with upstand (GastroHero Profi, sale) | €164.99 / €409 | GGM: <https://www.ggmgastro.com/de-de-eur/edelstahl-arbeitstisch-premium-1800x600mm-mit-grundboden-atk186>; GastroHero: <https://gastro-hero.de/edelstahl-arbeitstisch-profi-1800-x-600-mm-mit-grundboden-und-aufkantung> |
| P16 | Gastro stainless wall cabinet 1600 × 400 × 650, sliding doors (ECO) | €214.99 | GGM: <https://www.ggmgastro.com/de-de-eur/edelstahl-wandhaengeschrank-eco-1600x400mm-mit-schiebetuer-650mm-hoch-wsk164z> |
| P17 | IKEA METOD base cabinet frame 60 × 60 × 80 | €31 | IKEA: <https://www.ikea.com/de/de/p/metod-unterschrank-weiss-50205626/> |
| P18 | Stainless sheet 1.4301 2B 1.0 mm, cut to size | from €68.43 per m² | Alufritze: <https://alufritze.de/edelstahlblech-matt-2b-1-4301-x5crni18x10x1mm-nach-mass.html> |
| P19 | Solenoid valve ½″ 24 V for water (brass) | €40–80; Amazon.de range from €10.59 | Regenwasser24: <https://www.regenwasser24.de/Magnetventil-mit-1-2-Zoll-IG-aus-Messing-24V/MVM24V-G1-2>; Wittko: <https://wittko.eu/product-2-2-wege-magnetventil-1-2-zoll-nc-24v-luft-wasser> |
| P20 | Industrial safety: Pilz PNOZ s4 safety relay; Schmersal AZM 415 guard lock | ≈ €210 (price comparison); €636.91 | <https://www.deutschlandcard.de/preisvergleich/p/A164_9869658-pilz-sicherheitsschaltgerat-pnoz-s4-750104-relais>; <https://www.eichten-spareparts.de/produkte/werkzeugmaschinentechnik/sicherheitstechnik/tuerschalter/schmersal-sicherheitszuhaltung-azm-415-11-11zpkt-24-vac-dc-m20/> |
| P21 | Household door lock (washing-machine type, BSH spare part) | €6.95–33.95 | Ersatzteil-Lager: <https://www.ersatzteil-lager.com/Original-Bosch-Tuerverriegelung-Relais-Tuerschloss-Siemens-Neff-Koenic-fuer-Waschmaschine-Waschtrockner-EMZ-881-00633765-633765> |
| P22 | Magnetic couplings (bought, pump/mixer type) | US$67–257 | AliExpress: <https://www.aliexpress.com/w/wholesale-magnetic-couplings.html> |
| P23 | Battery pot stirrer (household gadget) | €29.99 | Amazon.de: <https://amazon.de/%C3%BCutensil-Stirr-Automatischer-Topfumr%C3%BChrer-Nylon-Beine/dp/B008OWT95S> |
| P24 | IKEA 365+ stainless cookware 6 pieces (5 L, 3 L pots, 2 L casserole, lids); 5 L pot alone | €34.99; €12.99 | IKEA: <https://www.ikea.com/at/de/p/ikea-365-kochgeschirr-6-tlg-edelstahl-80484329/>, <https://www.ikea.com/de/de/p/ikea-365-topf-mit-deckel-edelstahl-60484250/> |
| P25 | GN 1/3-65 stainless containers, 6 pieces | €24.99–29.99 | GGM: <https://www.ggmgastro.com/de-de-eur/6-stueck-edelstahl-gn-behaelter-1-3-hoehe-65mm-gby1365-set6> |
| P26 | Countertop combi-steam ovens 30–31 L (Panasonic NN-CS89, Smeg COF01) | ≈ €699–729 | <https://www.vergleich.org/kombi-dampfgarer/> |
| P27 | Single induction plate 2000 W (Caso Touch 2000, AMZCHEF, Medion) | €39.95–68 | Amazon.de: <https://www.amazon.de/Induktionskochfeld-AMZCHEF-einzel-induktionskochplatte-Kristallglasoberfl%C3%A4che-Sensor-Touch-Steuerung/dp/B09MYK6B2N>; <https://testundtipps.de/kueche-lifestyle/kuechengeraete/kochplatten/induktionsplatten/einzelne-induktionskochplatte> |

**Findings that move the numbers**: (1) maker-market motion parts are 3–5 × cheaper than K9b's industrial modules —
a complete NEMA 23 axis drive (motor + driver) is ≈ €50, a ball-screw set ≈ €50–90; the rails are the dearest
gantry part. (2) A Raspberry Pi 5 now costs €120 (memory prices), so the host is no longer "≈ €50". (3)
Industrial safety parts are expensive (€210 relay, €640 guard lock) against €7–34 for a household door lock.
(4) Gastro furniture is cheap for what it is: a welded stainless table 1.8 m for €165, a stainless wall cabinet
for €215. (5) A slim dishwasher costs only €270–350, a food processor with discs €90–110. (6) The countertop
combi-steam oven that K9b priced at €550 costs ≈ €700 (appliance side, +€150).

---

## 2. Line-by-line review (categories a–e)

Categories: **(a)** household appliance, Gastro item or accessory used as bought; **(b)** hardware-store, 3D-printer
or maker-market part; **(c)** 3D print in the non-food zone (#4); **(d)** deleted or merged; **(e)** ordinary kitchen
content or furniture the household buys anyway — **customer decision**, shown both ways in §5. "Job" = job-shop
stainless or aluminium part (#21). "OK?": **Y** acceptable, **Y\*** acceptable with the named condition or test,
**N** not acceptable (kept as in K9b).

| K9b line | € K9b | Cat. | K9c choice | € K9c | What the cut costs | OK? |
|---|---|---|---|---|---|---|
| M1.1 X belt module + rails, dry box | 300 | b | 40 × 80 profile 1.75 m, **two MGN15 rails** (P2), HTD 3M-15 belt (P3), NEMA 23 open loop (P4) | 250 | repeatability ±0.1–0.3 mm (stubs and combs take ±3 mm); speed 1.2 → 0.8 m/s (+2–4 s per long move); rails re-greased and belt checked yearly, belt ≈ €30 every ≈ 5 years | Y |
| M1.2 Z ball screw with brake | 200 | b | SFU1610 set (P7), NEMA 23 with 2 Nm brake (P5), mast = 40 × 80 profile + MGN15 1 m in a bent stainless cover | 175 | C7 rolled screw: backlash ≈ 0.05 mm, irrelevant; **hand push limited to 150 N** (K9b 400 N) by the printer-class frame stiffness — the press work stays in the press cup, the rolling pin needs < 150 N [E] | Y\* (rig K1) |
| M1.3 Y belt module in arm tube | 120 | b | NEMA 17, MGN12 0.6 m, GT2/HTD belt in a stainless tube 60 × 60 × 620 | 100 | none beyond M1.1 | Y |
| M1.4 3 closed-loop steppers + drivers | 210 | b, d | open-loop steppers (in the axis lines), TMC5160 drivers in the controls (P9); **lost steps detected by the arm-root load cell (collision spike) and Klipper stall detection** instead of encoders | 0 (moved) | a collision is seen as force, not as position error; re-home after a fault (≈ 20 s) | Y\* (K2) |
| M1.5 Two sealing bands | 80 | b | stainless cover strip on a magnetic strip (CNC "Abdeckband" practice) | 50 | strip wear ≈ 5 years [E] | Y |
| M1.6 X labyrinth + purge fan | 50 | d | labyrinth lips kept; **purge fan deleted**: the extraction keeps the cell below room pressure, so air flows from the X box into the cell through the labyrinth (the same direction the fan gave) | 25 | purge stops when extraction is off: then the cell is idle and dry | Y |
| M1.7 Mast and arm tubes | 40 | b, c | in M1.2/M1.3; laser-cut carriage plates and **3D-printed brackets** (ASA, dry zone ≤ 50 °C) | 40 | printed brackets creep above ≈ 60 °C: aluminium near the oven (E8) | Y\* |
| M2.1 Roll stepper + 20 : 1 planetary | 80 | b | NEMA 23 + MG-series planetary (P6 class) | 50 | gearbox rated torque 10 Nm [U]; backlash 0.5° irrelevant | Y\* |
| M2.2 Canned magnet coupling | 150 | b, job | bought N52 magnet segments in job-shop rotors, 0.5 mm 1.4404 can (bought couplings P22 as fallback) | 90 | none if E2 passes | Y |
| M2.3–2.5 Sleeve, Hall sensors, housing, drop link | 70 | job, b | same design, bent-sheet housing | 45 | — | Y |
| M3 Arm-root load cell + amplifier | 60 | b | 30 kg bar cell (P12) + 24-bit ADC; **also the collision sensor** | 25 | cheap cell drift: ±5 g needs temperature compensation and tare before each weighing [U] | Y\* (K10) |
| M4.1 Drawn pocket + S thimble | 80 | b, job | bought deep-drawn stainless cup welded into the deck; turned thimble | 50 | — | Y |
| M4.2 T plug | 40 | job | same | 45 | (incl. the driver magnet ring) | Y |
| M4.3 NEMA 34 + 10 : 1 + driver (T) | 130 | b | NEMA 23 + 10 : 1 precision planetary (P6), driver in the controls | 70 | T torque 25 → ≈ 20 Nm [U]: dough for ≤ 1 kg flour, press cup ≤ 2.3 kN at Rd 28 × 6 [E] | Y\* |
| M4.4 600 W BLDC + driver (S) | 100 | b | hobby 48 V 400 W BLDC + driver | 75 | S 600 → 400 W: blending a 1.5 L soup takes ≈ 60 → 90 s [E]; bearing life of a hobby motor 2–5 years [E] | Y\* (K7) |
| M4.5 Coaxial shaft + bearings | 40 | job | same | 40 | — | Y |
| M4.6 3 hub load cells | 45 | d | **deleted**: all weighing by loss in weight at the arm-root cell | 0 | gains into a T vessel no longer checked (±2 g → ±5 g by loss in weight) | Y |
| M4.7 Anchor post | 15 | job | same | 15 | — | Y |
| M5.1 Ring coil + generator | 220 | a, b | **kept, from a bought single induction plate** (P27, €40–68): its 2 kW generator board and touch board re-used (interface as for the domino, COK-023), a ring coil wound with litz wire and ferrite bars round the pocket, resonance re-matched by capacitors. Deleting the coil (K9b CC7) was examined and **rejected**: it leaves the domino's 2 zones as the only hob positions and **fails COK-002 M (≥ 3 simultaneously heated positions)**; it would also add 6–12 events per stirred meal (B3 47/50) | 100 | 2.5 → 2.0 kW at the hub: 1 L to the boil ≈ 1 min slower [E]; a hobby-matched generator is the riskiest electrical item (EMC, pan detection with a centre hole) [U] — fallback OEM coil +€120 | Y\* (E4, K6) |
| M5.2 Glass disc with hole | 80 | a, job | the plate's own glass-ceramic top, Ø 130 hole core-drilled by a glass shop, gasketed to the pocket | 40 | glass size follows the bought plate (≈ 280 × 350): fits the 300 mm hub column | Y\* |
| M6.1 Welded insulated well tub | 420 | a, job | **the donor dishwasher's own tub** (appliance budget), ceiling cut out to a 400 × 440 mouth, collar flange and gasket to the deck; fan-nozzle rows fed from the removed upper-arm line; bent combs | 145 | well follows the dishwasher (inner ≈ 400 × 500 × 550 [U]); cut top not double-walled (the lid is); warranty void; the door stays shut and becomes the **service door to the filter** (gain); **width −70 mm** | Y\* (K5) |
| M6.2 Lid-bench + gas strut | 80 | job, b | same, simpler sandwich | 60 | — | Y |
| M7.1 Rinse cup + strainer + 4 jets | 80 | a, b | bought round bar-sink bowl, bought basket strainer, 4 flat-fan nozzles | 50 | — | Y |
| M7.2 Turbidity sensor | 20 | d | **deleted**: fixed jet times (K9b already rinses 3–10 s) + camera | 0 | no "clean" proof per rinse; validated times instead | Y |
| M7.3 Tap spout + flow meter | 20 | b | same (flow meter €5 class) | 15 | — | Y |
| M7.4 Chute with flap | 30 | job | same | 35 | — | Y |
| M7.5 Bin drawer 20 L | 30 | e | ordinary kitchen bin pull-out | 30 | — | Y |
| M8.1 Stainless deck | 250 | a, job | **Gastro work table ≈ 1700 × 600 with upstand and base shelf** (P15) as deck **and** under-deck frame; cut-outs and the flush domino rebate by a job shop | 310 | finished table top is 1–1.2 mm on a stiffener frame: flatness for sliding (P-9) and the flush domino rebate must be checked [U] | Y\* (K8) |
| M8.2 X box | 150 | job | bent cover only; the structure is the frame (M8.3) | 50 | — | Y |
| M8.3 Walls and rear gutter | 350 | b, job | back liner 1.0 mm stainless (P18) to z 1450 with the bent gutter, HPL above; sides stainless in the splash zone, HPL above; frame of 40 × 40 profile ≈ 6 m (P1); ceiling panel | 430 | more joints above z 1450 (outside the splash zone); HPL must be sealed at its edges | Y |
| M8.4 Glazed door + guard lock | 250 | a, b | two sliding glazed panels on a top track; **household door lock** (washing-machine type, P21) + reed contact as second channel | 160 | safety level of a household appliance (EN 60335) instead of machinery practice (P20: €210 relay, €640 guard lock) [U] | Y\* (K4) |
| M8.5 Tool cabinet + box shelf | 200 | a, e, job | IKEA wall-cabinet carcass (P17 range) with a bent stainless tray liner and rear spring flaps; bent box shelf | 120 | particle board outside the liner: kept dry by the liner and flaps | Y |
| M8.6 Oven mount | 50 | b | two profiles and a shelf | 30 | — | Y |
| M8.7 Hatch drawer | 250 | a, b | bought full-extension runners, two GN 1/1 trays, 150 W silicone heater mat, solenoid lock, flap | 70 | — | Y |
| (in M8) Service fronts | — | e | IKEA fronts on the under-deck bays | 80 | — | Y |
| M9.1 ≈ 8 solenoid valves | 120 | b, d | **4 valves**: 2 hot-rated brass (85 °C jets; store → well), 2 cold (spout, nozzle rail); the well fills through the donor's own inlet valve | 120 | warm 45 °C at the spout by a bought thermostatic mixer instead of a valve pair | Y |
| M9.2 Nozzle rail | 60 | b | bought flat-fan nozzles on a stainless tube | 40 | — | Y |
| M9.3 Fan dry | 40 | d | **merged** with the hob-extractor fan (lid ajar, cell air drawn through the well) | 0 | drying ≈ 10 min longer when cooking extraction runs at the same time [E] | Y |
| M9.4 Piping | 80 | b | PEX/PTFE hoses; the donor's EN 1717 air gap reused for the well | 60 | — | Y |
| M10.1 Controller | 150 | b | **Klipper on a BTT Octopus Pro** (P8) + **Raspberry Pi 5 4 GB** (P10) with eMMC/NVMe storage | 210 | hobby-grade boards: SD-card and connector failures are the known weak points; mitigated by eMMC, read-only root, locking connectors | Y\* (K3) |
| (in M1/M4) Drivers | — | b | 4 × TMC5160 (X, Z, T, roll), 1 × TMC2209 (Y); PSUs 48 V 350 W + 24 V 100 W | 153 | stepper noise at mid speed ≈ 50–55 dB(A) at 1 m [E], below a running hood | Y\* (K15) |
| M10.2 3-phase power manager | 120 | b | 3 contactors + relay board + 1 current sensor per phase; the domino keeps its own limiter | 70 | — | Y |
| M10.3 Two cameras with lights | 120 | b, d | **one** Pi Camera Module 3 Wide (P11) with heated window and white/UV-A LEDs (K9b CC6) | 60 | well mouth and plate rim seen obliquely; no vision redundancy | Y\* (K13) |
| M10.4 Safety relay | 60 | b | two force-guided relays cutting motor power, monitored by the MCU and the door lock | 40 | see M8.4 | Y\* (K4) |
| M10.5 Wiring | 150 | b, c | cable chains, cables, printed cable guides | 100 | — | Y |
| M11.1 Bought pots, pans, GN, tins, discs | 500 | **e** | IKEA 365+ class pots (P24), GGM GN (P25), mid-price pans and knives; **second set deleted** (option +€80) | 375 (e) | second set: PERF-005's next meal within 30 min fails (K9b CC9); fine for 2 persons | Y\* (Ben) |
| M11.2 Welded stubs, drip collars, dog rings on ≈ 40 items | 400 | job | turned 1.4404 stubs **riveted with solid stainless rivets like pot handles** on ≈ 35 items; dog rings (T drive and pan detection) on the 5 T-vessels | 320 | rivet heads are crevices: must pass riboflavin and 500 well cycles (household pots are riveted the same way) | Y\* (K9) |
| M11.3 Press-cup kit | 200 | b, job | same design, bought push-dicer grids and ricer die | 150 | — | Y |
| M11.4 Custom tools, fixtures, carriers | 500 | a, b, job | S ware on bought jars and processor discs (110); bought corers, pitter, ravioli mould, dumpling press, probe, spoons (90); custom fixtures (280); carriers = bought gastro plate racks + bent tool racks; **glass and cutlery baskets from the donor dishwasher** (60) | 540 | — | Y |

**What was looked at and kept**: the canned roll and hub (P-3, hygiene); the bayonet stub (no cheaper grip);
the press cup (cheap and covers dice, rice, press-peel); the anchor post; the hatch drawer (K9b CC8 saves only
≈ €40 now); the tool cabinet (C2 R-6); the Y axis (without it the layout becomes one line: +width).

---

## 3. Architecture challenges

### 3.1 Options weighed

| Topic | Option | € (machine part) | Verdict and reason |
|---|---|---|---|
| **Manipulator** | K9b: industrial belt and screw modules, closed-loop steppers | 1,000 + drivers | replaced |
| | **Printer/CNC-class Cartesian at the rear wall**: profiles, MGN rails, HTD belt, SFU ball screw, open-loop NEMA 23 | **640** (+ drivers in controls) | **chosen**: same layout and hygiene as K9b (mast lane, bands, labyrinth), maker-market parts |
| | CoreXY / ceiling gantry (printer style, XY bridge over the work area) | ≈ 450 | **rejected**: belts, rails and a moving bridge over open food (P-3, P-8); the cost gain over the Cartesian rear gantry is ≈ €150 |
| | V-slot profile with POM V-wheels instead of MGN rails | −150 | **rejected**: the cantilevered arm puts 37 Nm (6 kg at 620 mm) and up to 93 Nm (150 N push) on the X carriage; ≈ 1 kN per wheel pair is above POM-wheel ratings [E] |
| | Z by belt + counterweight instead of ball screw | −30 | rejected for now: brake motor and screw are as cheap and hold position without power |
| **Enclosure** | K9b: custom stainless deck, box, walls, door with industrial guard lock | 1,500 | replaced |
| | **Gastro table as deck and base; stainless liners only in the splash zone, HPL above; profile frame; IKEA wall carcass as tool cabinet; sliding glazed panels with a household door lock** | **1,280** (of which 420 furniture-equivalent, §5) | **chosen** |
| | Room wall and kitchen wall cabinets as structure (X beam on the room wall) | −150 | round 2: depends on the installation rule (masonry wall, fitter) |
| | Cell shares walls, ceiling and frame with the storage modules and the transport gallery | −175 | round 2 (whole-machine carcass design) |
| **Hub** | K9b H-A: canned T + coaxial canned S + ring coil, 3 load cells | 750 | replaced |
| | **H-B: same canned T + coaxial S with hobby motors; ring coil from a cannibalised single induction plate; no hub cells** | **295 + 140** | **chosen**: keeps one seat (width), canned (no seal), all T functions (board turn, coring oscillation, press cup, kneading roller, spinner, folding), the third hot position (COK-002 M) and the stirring that frees the hand |
| | H-B without coil (K9b CC7) | 295 | **rejected**: fails COK-002 M (2 hob positions + oven), +6–12 events per stirred meal |
| | H-C: **bought food processor as the whole hub** (Bosch MCM3 class, P14); T deleted; board on a passive lazy-susan turned by the hand; bought lever dicer and lever ricer pushed by Z; pump salad spinner; dough in the processor bowl | ≈ 230 incl. lever tools, −S ware 110, −press cup 150 | **round-2 candidate only together with a third hot position elsewhere** (−€300 net before that, −1 actuator, −N3, −N4). Costs: the hub is no longer heated, so COK-002 M needs a bought single induction plate in another place (+€50, **+300 mm width**) or Ben's waiver; more hand events (B6 is already bound by the single hand, 46/50); coring oscillation and "turning half" skin cuts lost (melon, pineapple slower); dough ≤ ≈ 500 g flour per batch [U]; open drive dog at the deck (splash zone); bowl twist-lock bypassed by a fixed seat. Decide with E0 |
| | H-D: bought processor base as S in a second seat beside T | −100 | **rejected**: needs +230 mm width; in the same column the S bowl overlaps the T vessel because T vessels must sit at y ≥ 320 for the stub reach |
| | H-E: Thermomix-class cooker (heated jug, blade, scale) beside the hub | +300…450 | **rejected for cost**; kept as coverage option if E0 shows the hand overloaded by interval stirring; jug 2.2–3 L, lid twist-lock needs an XY-arc push (the hand cannot yaw), no remote start (#5 analogue) |
| | H-F: bought planetary stand mixer as T | +100 | rejected: replaces only kneading; tilting head and bowl twist-lock |
| | H-G: bought battery pot stirrer for stirred dishes on the domino (P23) | +30 | **round-2 test**: the cheapest stand-in for the coil's continuous stirring; torque for polenta and washability of the legs [U] |
| **Controls** | K9b: single industrial board, 2 cameras, safety relay | 600 (drivers elsewhere) | replaced |
| | **Klipper on BTT Octopus Pro + Raspberry Pi 5; open-loop TMC drivers; 1 camera; household safety chain** | **633 incl. drivers and PSUs** | **chosen**: Klipper does the real-time motion (X, Y, Z as a Cartesian printer; roll and T as `manual_stepper`; S by PWM); recipes, vision and the safety logic run on the Pi; the hard safety chain (door lock, relays) does not depend on software |
| | BTT CB1 (€41) or Manta M8P + CB1 instead of Octopus + Pi 5 | −95…−130 | round 2 if one-camera vision fits in 1 GB RAM |
| **Sensors** | K9b: 2 cameras, 3 hub cells, arm-root cell, turbidity, 2 Hall | — | **K9c: 1 camera, arm-root cell (weighing and collision), 2 Hall (roll torque), 3 endstops, door lock + reed**; the appliances keep their own sensors |
| **Well** | K9b: welded insulated tub + donor wash parts | 500 + donor | replaced |
| | **Donor dishwasher's own tub, top cut open** | **205** | **chosen**; −70 mm width |
| | Gastro deep sink bowl as tub | 100–150 | rejected: typical depth ≤ 300 mm is too shallow for on-edge Ø 280 pans and the comb heights [E] |
| | Dishwasher used front-loading as bought | 0 | rejected: open door and pulled-out rack lie outside the 600 mm depth and below the hand's reach (roll axis ≥ z 700) |

### 3.2 Simplicity effect (#20)

Removed from K9b: the three hub load cells, the turbidity sensor, the purge fan, the fan dryer, one camera,
the industrial safety relay, closed-loop drives, the welded well tub, the custom glass disc, four valves, the
second ware set and the dog rings on non-T items. Added: nothing that moves. Custom part types (K9b counting
≈ 35) fall to **≈ 28** [E]: deck, well tub, rinse cup, hatch drawer, tool cabinet, carriers and the induction
generator are now bought items with job-shop cut-outs, liners or re-wound coils. Novel mechanisms unchanged
(**2 / 4**); N4 (ring coil) becomes riskier because its generator is a re-matched consumer board.

**Note on COK-002**: the requirement asks for ≥ 3 positions **of which ≥ 2 with ≥ 3 kW**. K9b's three
positions (domino 3.4 kW boost / 2.0 kW, hub 2.5 kW) give only **one** zone ≥ 3 kW; K9c (hub 2.0 kW) is the
same. Either the domino's rear zone is boosted (most dominos share 3.6–3.7 kW between both zones, so only one
can boost at a time) or COK-002's power clause needs Ben's waiver. This is inherited from K9b, not caused by K9c.

---

## 4. The K9c machine (changes against K9b)

### 4.1 What changed

K9c keeps K9b's architecture, kinematics, stations, recipe routes, hygiene rules and ware list (K9b §2–§5).
It changes **how each part is bought and built**, and five functions:

1. **Gantry**: printer/CNC-class Cartesian at the rear wall — X on a 40 × 80 profile with two MGN15 rails and an
   HTD 3M-15 belt; Z on an SFU1610 ball screw with a brake motor; Y on MGN12 + belt in a stainless tube; roll as
   K9b with a NEMA 23 + planetary. Open-loop steppers on TMC drivers under **Klipper**. Bands, labyrinth and the
   300 mm drop link as K9b. The arm-root load cell doubles as the **collision sensor**.
2. **Hand capability**: lift ≤ 6 kg at ≤ 160 mm (unchanged), roll 10 Nm (unchanged); **downward push limited to
   90 Nm about the X carriage**, i.e. 300 N within y ≤ 420 (stab nest and corer in the rear row: K9b's ≤ 300 N
   coring still works) and 150 N at full reach (rolling pin); top speed 1.2 → 0.8 m/s.
3. **Hub**: canned T (NEMA 23 + 10 : 1, ≈ 20 Nm) and coaxial canned S (hobby 400 W BLDC) as K9b; **the ring coil
   is driven by the generator board of a bought €40–68 single induction plate**, under that plate's own
   glass-ceramic top with a core-drilled Ø 130 hole (2.0 kW); no hub load cells.
4. **Well**: the **donor slim dishwasher stays whole** under the deck; its tub ceiling is cut to a 400 × 440
   mouth with a collar to the deck; the upper basket and arm are removed and their feed drives two fan-nozzle
   rows; the dishwasher door stays shut and becomes the front service door to its filter; its glass and
   cutlery baskets become the machine's baskets. Well column 550 → **480 mm**.
5. **Enclosure**: a **Gastro stainless work table** is the deck and the under-deck frame; stainless liners only in
   the splash zone (back wall and sides to z 1450), HPL above; a 40 × 40 profile frame; an IKEA wall carcass
   with a stainless tray liner is the tool cabinet; two sliding glazed panels with a **household door lock**
   (washing-machine type) and a reed contact; the safety chain is two force-guided relays.
6. **Sensors and controls**: one wide camera instead of two; no turbidity sensor; no purge fan (the extraction's
   under-pressure purges the X box labyrinth); no fan dryer (extraction, lid ajar); Klipper on an Octopus Pro
   with a Raspberry Pi 5 host.
7. **Ware**: stubs turned and **riveted** like pot handles instead of welded with drip collars; dog rings only on
   the five T-vessels; bought pots, pans, GN and knives at IKEA/GGM price level and shown as kitchen content
   (customer decision); **no second set** (option).

Unchanged: 6 motion actuators, roll-bayonet grip (N1), produce module (N2), press cup (N3), heated hub (N4),
domino, high countertop combi-steam oven with hook-rod door, rinse cup, chute and blade post, egg fixture,
hatch drawer pulled by the diner, plate carriers, coverage routes. **Coverage: central 233 = 94.0 %, as K9b**
[D]; no route is removed. Hand time: +2–4 s per long X move (0.8 m/s) and ≈ +1 min per boil on the 2.0 kW hub
[E]; to be confirmed in E0.

### 4.2 Width

| Module | Width K9b | Width K9c | Note |
|---|---|---|---|
| Cold storage | 1200 | 1200 | unchanged (not machine part) |
| Ambient storage | 650 | 650 (or 740) | the 90 mm saved can go to ambient storage |
| Cell: S column | 600 | **580** | egg fixture narrowed; rear row rinse cup 150 + chute 200 + egg 180 + walls |
| Cell: domino | 300 | 300 | |
| Cell: hub | 300 | 300 | the induction plate's glass (≈ 280 × 350) fits |
| Cell: well and oven column | 550 | **480** | slim dishwasher 450 + 2 × 15; the oven above must be ≤ 480 deep along X [U: E1] |
| **Cell** | **1750** | **1660** | −90 mm |
| **Whole machine** | 3600 | **3510** (or 3600 with ambient 740) | PHY-004 M ≤ 3600 met |

### 4.3 Actuators and dynamic seals

| # | Actuator | K9b | K9c | Seal / penetration |
|---|---|---|---|---|
| 1 | X | closed-loop 400 W stepper, belt module | NEMA 23 3 Nm open loop, HTD 3M-15 belt, 2 × MGN15 | none (labyrinth, purged by cell under-pressure) |
| 2 | Z | ball screw 16 × 10 with brake | SFU1610, NEMA 23 with 2 Nm brake | **band 1** (stainless cover strip) |
| 3 | Y | belt in the arm tube | NEMA 17, GT2/HTD belt, MGN12 | **band 2** (stainless cover strip) |
| 4 | Roll | stepper + 20 : 1, canned coupling | NEMA 23 + 20 : 1 MG planetary, canned coupling with bought magnets | none (canned) |
| 5 | T | NEMA 34 + 10 : 1, 25 Nm | NEMA 23 + 10 : 1, ≈ 20 Nm [U] | none (canned) |
| 6 | S | 600 W BLDC | 400 W hobby BLDC | none (canned thimble) |

**6 motion actuators, 2 dynamic seals** (as K9b). Not counted: the dishwasher's own pumps and valves, 4 solenoid
valves, the extraction fan, 3 induction generators (2 in the domino, 1 from the single plate), the hatch
solenoid, the door lock. **Peak power** ≈ 9.2 kW (K9b 9.7; hub 2.5 → 2.0 kW).

---

## 5. K9c bill of materials and totals

One-unit EU retail and job-shop prices incl. VAT, own assembly labour not counted (see the header). Cat. as §2;
**e2** = furniture equivalent (customer decision, §5.4).

### 5.1 Machine part

| # | Item | Qty | € each | € total | Cat. | Source |
|---|---|---|---|---|---|---|
| G1 | X beam, aluminium profile 40 × 80, 1.75 m | 1 | 35 | 35 | b | P1 [W/E] |
| G2 | X rails MGN15 1.75 m, two blocks each | 2 | 70 | 140 | b | P2 [W]: €140 per 1.5 m on Amazon.de; AliExpress level [E] |
| G3 | X belt HTD 3M-15 3.6 m, pulleys, idler, tensioner | 1 | 50 | 50 | b | P3 [W] + [E] |
| G4 | X motor NEMA 23, 3 Nm | 1 | 25 | 25 | b | P4 [W] |
| G5 | Z ball screw SFU1610 ≈ 1 m, BK/BF12, nut housing, coupling | 1 | 60 | 60 | b | P7 [W] |
| G6 | Z motor NEMA 23, 3 Nm, 2 Nm brake | 1 | 45 | 45 | b | P5 [W] |
| G7 | Mast: profile 40 × 80 × 1.1 m, MGN15 1 m, bent stainless cover | 1 | 70 | 70 | b, job | P1, P2 [W/E] |
| G8 | Y: NEMA 17, MGN12 0.6 m, belt, pulleys | 1 | 60 | 60 | b | [E] |
| G9 | Arm tube stainless 60 × 60 × 620 with end plates | 1 | 40 | 40 | job | [E] |
| G10 | Sealing bands (stainless cover strip on magnetic strip) | 2 | 25 | 50 | b | [E] |
| G11 | X labyrinth lips | 1 | 25 | 25 | job | [E] |
| G12 | Carriage plates (laser-cut aluminium), 3D-printed brackets | 1 | 40 | 40 | b, c | [E] |
| | **Gantry** | | | **640** | | K9b 1,000 + drivers |
| R1 | Roll motor NEMA 23 + 20 : 1 MG planetary | 1 | 50 | 50 | b | P6 [W] |
| R2 | Canned coupling: bought magnets, turned rotors, 0.5 mm 1.4404 can, PEEK bushes | 1 | 90 | 90 | b, job | [E]; P22 |
| R3 | Sleeve with J-slots, reaction tab | 1 | 25 | 25 | job | [E] |
| R4 | Housing, drop link, 2 Hall sensors | 1 | 20 | 20 | job, b | [E] |
| | **Roll unit** | | | **185** | | K9b 300 |
| W1 | Arm-root load cell 30 kg + 24-bit ADC | 1 | 25 | 25 | b | P12 [W] |
| H1 | T: NEMA 23 + 10 : 1 precision planetary | 1 | 70 | 70 | b | P6 [W] |
| H2 | T plug + driver magnet ring | 1 | 45 | 45 | job | [E] |
| H3 | Pocket (bought deep-drawn cup, welded in) + S thimble | 1 | 50 | 50 | job | [E] |
| H4 | S: 400 W 48 V BLDC + driver | 1 | 75 | 75 | b | [E] |
| H5 | Coaxial shaft, bearings | 1 | 40 | 40 | job, b | [E] |
| H6 | Anchor post | 1 | 15 | 15 | job | [D] |
| H7 | Single induction plate 2 kW (generator board, touch board, glass top) | 1 | 50 | 50 | a | P27 [W] |
| H8 | Ring coil (litz wire, ferrite bars), matching capacitors, Ø 130 hole in the glass, gasket | 1 | 90 | 90 | b, job | [E] |
| | **Hub with heated ring** | | | **435** | | K9b 750 |
| WL1 | Dishwasher tub opened: cut, collar flange, gasket | 1 | 80 | 80 | job | [E] |
| WL2 | Fan-nozzle rows on the long walls | 1 | 25 | 25 | b | [E] |
| WL3 | Fork combs with flats | 1 | 40 | 40 | job | [E] |
| WL4 | Lid-bench 460 × 460 + gas strut | 1 | 60 | 60 | job, b | [E] |
| | **Well** (dishwasher in the appliances) | | | **205** | | K9b 500 |
| RC1 | Rinse cup: bar-sink bowl + basket strainer | 1 | 35 | 35 | a | [E] |
| RC2 | Four flat-fan jets | 1 | 15 | 15 | b | [E] |
| RC3 | Tap spout + flow meter | 1 | 15 | 15 | b | [E] |
| RC4 | Chute with spring flap | 1 | 35 | 35 | job | [E] |
| | **Rinse cup and chute** | | | **100** | | K9b 150 (+ bin in E14) |
| E1 | Gastro stainless work table ≈ 1700 × 600, upstand, base shelf | 1 | 190 | 190 | a, **e2** | P15 [W] |
| E2 | Cut-outs and flush domino rebate | 1 | 120 | 120 | job | [E] |
| E3 | Back liner 1.0 mm stainless to z 1450 with bent gutter; HPL above | 1 | 150 | 150 | job, b | P18 [W] + [E] |
| E4 | Side panels (stainless splash zone, HPL above) | 1 | 90 | 90 | job, b | [E] |
| E5 | Frame: 40 × 40 profile ≈ 6 m + brackets | 1 | 150 | 150 | b | P1 [W] |
| E6 | Ceiling panel with port | 1 | 40 | 40 | b | [E] |
| E7 | X box cover | 1 | 50 | 50 | job | [E] |
| E8 | Two sliding glazed panels + top track | 1 | 130 | 130 | b | [E] |
| E9 | Household door lock (washing-machine type) + reed contact | 1 | 30 | 30 | a | P21 [W] |
| E10 | Tool cabinet: IKEA wall carcass, stainless tray liner, rear spring flaps; box shelf | 1 | 120 | 120 | a, job, **e2** | P17 range [E] |
| E11 | Oven mount | 1 | 30 | 30 | b | [E] |
| E12 | Hatch drawer: runners, 2 GN 1/1 trays, 150 W heater mat, solenoid lock, flap | 1 | 70 | 70 | a, b | [E] |
| E13 | Under-deck fronts (IKEA) | 1 | 80 | 80 | **e2** | [E] |
| E14 | Bin pull-out with 20 L bin | 1 | 30 | 30 | **e2** | [E] |
| | **Enclosure** | | | **1,280** | | K9b 1,500 + 30 |
| V1 | Solenoid valves, hot-rated brass | 2 | 45 | 90 | b | P19 [W] |
| V2 | Solenoid valves, cold | 2 | 15 | 30 | b | P19 [W] |
| V3 | Nozzle rail | 1 | 40 | 40 | b | [E] |
| V4 | Piping, hoses, fittings, thermostatic mixer for the spout | 1 | 60 | 60 | b | [E] |
| | **Water** | | | **220** | | K9b 300 |
| C1 | Klipper board BTT Octopus Pro | 1 | 75 | 75 | b | P8 [W] |
| C2 | Raspberry Pi 5 4 GB + eMMC/NVMe storage | 1 | 135 | 135 | b | P10 [W] + [E] |
| C3 | TMC5160 drivers (X, Z, T, roll) | 4 | 23 | 92 | b | P9 [W] |
| C4 | TMC2209 driver (Y) | 1 | 6 | 6 | b | [E] |
| C5 | PSUs 48 V 350 W + 24 V 100 W | 1 | 55 | 55 | b | [E] |
| C6 | Camera Module 3 Wide, heated window, white + UV-A LEDs | 1 | 60 | 60 | b | P11 [W] |
| C7 | Power manager: 3 contactors, relay board, current sensors | 1 | 70 | 70 | b | [E] |
| C8 | Safety chain: 2 force-guided relays | 1 | 40 | 40 | b | [E]; P20 for comparison |
| C9 | Cable chains, cables, connectors, printed guides | 1 | 100 | 100 | b, c | [E] |
| | **Controls** | | | **633** | | K9b 600 (drivers were in M1/M4) |
| WA1 | Bayonet stubs riveted (35 items) + dog rings (5 T-vessels) | 40 | 8 | 320 | job | [E] |
| WA2 | Press-cup kit with bought grids and ricer die | 1 | 150 | 150 | job, b | [E] |
| WA3 | S ware: blender jug and cutter cup on magnet rotors, bought processor discs | 1 | 110 | 110 | job, b | [E] |
| WA4 | Bought special tools: corer tubes, pitter, ravioli mould, dumpling press, wireless probe, measuring spoons, strainer basket, fat cup | 1 | 90 | 90 | a | [E] |
| WA5 | Custom fixtures: blade post, egg fixture, Rouladen cradle + 2 raft forks, carving trough, plate cradle, hook rod, fork-spit, hung scraper, kneading roller, lift-rack pair | 1 | 280 | 280 | job | [E] |
| WA6 | Carriers: 2 bought plate racks (modified), 3 tool racks; glass and cutlery baskets from the donor dishwasher | 1 | 60 | 60 | a, job | [E] |
| | **Machine ware** | | | **1,010** | | K9b 1,100 (without bought pots etc.) |
| | **MACHINE PART K9c** (kitchen content outside, furniture-equivalent inside) | | | **4,733** | | K9b 6,290 on the same basis |

Blocks: enclosure 1,280 (27 %), machine ware 1,010 (21 %), gantry 640 (14 %), controls 633 (13 %), hub 435
(9 %), water 220, well 205, roll 185, rinse cup and chute 100, weighing 25. Job-shop content ≈ €1.8 k [E].

### 5.2 Optional kitchen content (e1, customer decision)

| # | Item | Qty | € each | € total | Source |
|---|---|---|---|---|---|
| K1 | Frying pans tri-ply Ø 280 (pan pair) | 2 | 40 | 80 | [E] |
| K2 | Pots 5 L with insert, 3 L, 1.5 L | 1 | 35 | 35 | P24 [W] |
| K3 | Braiser Ø 280, 5.5 L | 1 | 40 | 40 | [E] |
| K4 | Lids Ø 280 / 220 / 160, strainer lid | 1 | 15 | 15 | [E] |
| K5 | Kneading bowl Ø 280 stainless | 1 | 15 | 15 | [E] |
| K6 | GN 2/3 × 3, GN 1/3-65 × 3 with lids | 1 | 45 | 45 | P25 [W] |
| K7 | Loaf tin, springform | 1 | 25 | 25 | [E] |
| K8 | Knives: chef's red and green, scalloped slicer | 3 | 15 | 45 | [E] |
| K9 | Turner, ladle, silicone spatula, balloon whisk, rolling pin, Spätzle slider | 1 | 45 | 45 | [E] |
| K10 | PE-HD boards red and green | 2 | 10 | 20 | [E] |
| K11 | Salad-spinner basket | 1 | 10 | 10 | [E] |
| | **Kitchen content** | | | **375** | K9b 500 |
| | Option: second set (pan, 5 L pot, board, knife, spatula-tongs, 5 stubs) | | | +80 | |

These items still get stubs and dog rings (WA1, machine part); only the bare bought items are in question.

### 5.3 Appliances (K9c)

| Appliance | € | Change against K9b |
|---|---|---|
| Induction domino 2 zones + interface board | 300 + 60 | — |
| Countertop combi-steam oven 25–32 L + interface + float valve | 700 + 100 | +150 (P26 web price) |
| Slim 45 cm dishwasher, used whole as the well | 300 | −100 (P13: €270–350) |
| 30 L under-sink water heater 88 °C | 200 | — |
| Hob-extractor fan with baffle filter | 150 | — |
| Fridge + freezer | 1,000 | — |
| Shelving | 500–1,000 | — |
| **Appliances** | **3,310–3,810** | +50 (customer's figure ≈ 3,000–3,500) |

### 5.4 Totals, shown both ways

| Accounting | K9b | **K9c** | Gap to €2,000 |
|---|---|---|---|
| Machine part, **K9b accounting** (kitchen content inside) | 6,790 | **5,108** | 3,108 |
| Machine part, **kitchen content as household** (e1 out) | 6,290 | **4,733** | 2,733 |
| Machine part, **kitchen content and furniture-equivalent as household** (e1 and e2 = €420 out: work table, tool-cabinet carcass, fronts, bin pull-out) | ≈ 5,800 | **4,313** | 2,313 |
| Appliances | 3,260–3,760 | 3,310–3,810 | |
| **Whole machine** (appliances + machine part + kitchen content) | 10,050–10,550 | **8,420–8,920** | |

Round 1 saves **€1.7 k (−25 %)** on the machine part at K9b accounting, **€1.6 k** with kitchen content outside.
Where the €1,682 come from: gantry (−€360; its drivers moved to the controls), hub with a cannibalised
induction plate and hobby motors (−€315), well from the donor tub (−€295), enclosure (−€250), kitchen content at
IKEA/GGM prices and no second set (−€125), roll (−€115), machine ware (−€90 net: riveted stubs, cheaper press
cup, more bought tools), water, rinse cup and load cell (−€165), controls (+€33 incl. drivers and PSUs).

---

## 6. Remaining gap and round-2 candidates

### 6.1 Why K9c is still at €4.7 k

The closed wet cell (€1,280), the hand (gantry + roll €825) and the controls (€633) alone cost **€2.7 k** —
more than the target before any station or ware is counted. These three blocks are now built from bought
maker-market and Gastro parts; what remains in them is mostly material (stainless sheet, rails, a Raspberry Pi
at 2026 memory prices) and job-shop work. The remaining €2 k are spread thinly over ≈ 50 lines, none above
€320. **Further large cuts therefore need either a different accounting, a series, or a function decision.**

### 6.2 Round-2 candidates (ordered by € saved per loss)

| # | Cut | Saves [E] | Costs | Precondition |
|---|---|---|---|---|
| R2-1 | **Shared carcass**: cell side wall, ceiling and frame shared with the ambient module and the transport gallery; the X beam carried by the gallery frame | 150–200 | design coupling between modules; none functionally | whole-machine carcass design |
| R2-2 | Host on a **BTT CB1** (€41) or Manta M8P + CB1 instead of Octopus Pro + Pi 5 | 95–130 | vision limited to still-image checks at low frame rate | K13 on the CB1 |
| R2-3 | **Stubs as one laser-cut and folded part** (no turning), riveted | 100–130 | the J-slot lock geometry must survive folding tolerances | E2 |
| R2-4 | Rails, ball screw, motors and BLDC from AliExpress/EU warehouses instead of Amazon.de | 80–120 | quality spread, lead time; 10 % spares | — |
| R2-5 | Custom fixtures replaced by bought items (carving board with gauge, roulade clips) or recipe routes | 60–100 | each must keep its meals; coverage reserve is 2 meals | C1 coverage check |
| R2-6 | Hatch drawer → fixed heated tray behind a manual flap (K9b CC8) | 40 | the diner reaches ≈ 250 mm into the machine (SRV-010) | Ben |
| R2-7 | One sliding glazed panel + one fixed panel with a service hatch | 40 | narrower service access | — |
| R2-8 | **H-C: bought food processor as the whole hub** (§3.1) | 300, −1 actuator | needs a third hot position elsewhere (+€50, **+300 mm**) or a COK-002 waiver; more hand time (B6) | E0 and Ben |
| R2-9 | **Series of ≥ 50 units**: job-shop content ≈ €1.8 k at −25…−35 % | 450–630 | needs a series | — |
| R2-10 | Appliance side: the donor dishwasher heats the final rinse to 82 °C; the 30 L store is deleted | 200 (appliances) | sump and pump plastics at 82 °C [U]; +3 min per load; 0.3 kWh/day standby saved | E6 |
| R2-11 | Accounting: furniture-equivalent e2 counted as household | 420 | none | Ben |

**Projection** [C]: R2-1…R2-7 → ≈ €4.05 k; + R2-8 → ≈ €3.75 k; + R2-11 → ≈ €3.35 k; + R2-9 → **≈ €2.8 k**.

### 6.3 What would close the last ≈ €0.8 k (function decisions, each Ben's call)

| # | Function given up | Saves [E] | Cost in function |
|---|---|---|---|
| F1 | S (blend, slice, grate on the hub): cordless stick blender held by the hand, slicing by knife and blade-post rasp (K9b CC10) | 200 | +3–5 min per meal; slicing quality by knife; one battery item |
| F2 | Heated hub (COK-002 waiver: 2 hob positions + oven) | 140 | +6–12 events per stirred meal; 4-pot menus serialised; risotto, polenta at risk |
| F3 | Plate service (family style only: no plate cradle, plate carriers stay for dish return) | 30 | the household plates at the table for every meal |
| F4 | Special meal fixtures (ravioli plate, dumpling press, Rouladen cradle) | 60 | −3 to −5 meals → < 93 %: **not allowed (#26)** |

With every round-2 candidate, both accounting decisions, a series **and** F1–F3, the machine part is still
≈ €2.4–2.6 k. **Conclusion: K9b's function set does not reach €2 k. At one-unit prices its realistic floor is
≈ €3.3–3.8 k (round 2); in a series of ≥ 50 with kitchen content and furniture counted as household ≈ €2.8 k.**
Getting to €2 k would need a cheaper principle for the wet cell or the hand, which no concept so far has shown
at 93 % coverage (K9b §8.1).

---

## 7. Risks introduced by the cheaper choices, and the cheapest tests

K9b's experiments E0–E10 (K9b §9.1) stay; E4 and E6 change as noted. New risks, cheapest first within
each kill level:

| # | Risk (from which cut) | Cheapest test | Cost, time | Fallback and its cost |
|---|---|---|---|---|
| K6 | **Hand becomes the bottleneck** with 0.8 m/s, 2.0 kW hub and 150–300 N push (G, H) | add the K9c speeds and limits to the E0 discrete-event simulation (B1–B12, 4 menus) | €0, 1 day on top of E0 | X closed-loop 1.2 m/s (+€60); OEM coil 2.5 kW (+€120) |
| K4 | **Household-grade safety chain** (door lock + force-guided relays) not adequate for a machine with knives, hot oil and a moving gantry (E9, C8) | paper risk assessment: EN 60335-1/-2-x vs Machinery Regulation 2023/1230, PL estimate per EN ISO 13849 with a safety engineer | €0–500, 2 days | Pilz relay + guard lock (+€300–800, P20) |
| K1 | **Printer-class gantry stiffness**: tip deflection and settling with 6 kg at 620 mm and 150–300 N push; X carriage moment on two MGN15 rails (G1–G9) | build X (1 m) + Z + Y from the BOM on a bench; dial gauge at the tip under 6 kg and 300 N; 10 000-move repeatability run | €450, 1 week (parts re-used in the prototype) | wider rail spacing, 40 × 80 → 80 × 80 mast (+€60); MGN20 (+€80) |
| K2 | **Open-loop lost steps undetected** (M1.4) | on the K1 rig: deliberate collisions and stalls; check the load-cell spike stop and Klipper stall detection; re-home time | €0 on K1, 1 day | AS5600/MT6826 angle sensors on X and Z (+€15) or closed-loop X/Z (+€120) |
| K5 | **Donor dishwasher tub cut open**: tub stiffness, spray coverage without the upper arm, steam escape at the lid, 82 °C rinse via the 30 L store into a household sump (WL) | E6 re-done with a bought €270 dishwasher: cut, collar, combs; riboflavin on pots, GN, plates; loggers on the coldest item at 82 °C / 60 s; cycle time | €400, 1 week (replaces E6's plywood well) | K9b's welded tub (+€295) |
| K6b | **Cannibalised induction generator** with a ring coil (H7, H8): resonance, pan detection with a Ø 130 hole and the dog-ring gap, EMC, board heat under the deck | E4 re-done with a €40 plate: wind the ring coil, re-match, crêpe and béchamel tests, IR map, board temperature, a simple EMC pre-scan with a near-field probe | €250, 4 days | OEM ring coil + generator (+€120) |
| K3 | **Hobby electronics in a hot, humid cabinet** (C1–C9): SD/eMMC corruption, connector fretting, Pi throttling | 2-week soak of the control stack running a motion script in a box at 40 °C / 80 % RH next to a running oven; power-cut test 200 × | €100, 2 weeks (parallel) | conformal coating, eMMC + read-only root (in BOM); industrial PLC (+€400) |
| K7 | **Hobby BLDC S in the canned thimble**: heat, bearing life, noise at 6000 rpm (H4) | 40 h duty cycle with the canned thimble, temperature and dB(A) | €150, 1 week | K9b's 600 W BLDC (+€25) |
| K8 | **Gastro table as deck**: flatness for sliding vessels (P-9), the flush domino rebate in 1–1.2 mm sheet, cut-out edges (E1, E2) | buy the table; cut the domino rebate and one round hole; straight-edge flatness ±1 mm; slide a 5 kg braiser across all joints | €250, 2 days (table re-used) | 1.5 mm custom deck (+€120) |
| K9 | **Riveted stubs**: crevices under rivet heads, loosening under well heat cycles (WA1) | 20 stubs riveted to IKEA pots; 500 well cycles; unlock torque and wobble; riboflavin after soiling | €150, 3 weeks (in E6 loads) | welded stubs (+€80) |
| K10 | **Cheap load cell drift**: ±5 g weighing at 20–45 °C, creep (W1) | temperature sweep in an oven at 30–50 °C, 30-min creep with 3 kg | €40, 1 day | 30 kg single-point cell of OIML class C3 (+€60) |
| K13 | **One camera**: blind spots at the well mouth, plate rim, hatch tray (C6) | cardboard mock-up of the cell, Pi camera at the X box face; run C3's 12 vision checks from photos | €50, 1 day | second camera (+€60) |
| K11 | **Belt and printed brackets near the oven** (G3, G12) | thermocouples on the X box during E8 | €0 on E8 | aluminium brackets (+€40), steel-cord belt (in BOM) |
| K15 | **Noise** of open-loop steppers (C3) | dB(A) at 1 m on the K1 rig with stealthChop and spreadCycle | €0 on K1 | closed-loop X (+€60) |
| K14 | **Price and supply volatility** (Pi 5 at €120 in 2026; marketplace quality) | buy all rig parts from two sources and compare | €0 | EU stock at ≈ +30 % |

**Order**: K6 and K4 (desk work, they can stop the cut) → K1/K2/K15 on one rig → K5 and K6b (replace E6 and E4)
→ K8, K10, K13 → K3, K7, K9 as long-running soaks. Total ≈ €2.1 k and 5–6 weeks; K5 and K6b (€650) replace
K9b's E6 and E4 (€1,000), so the net addition to K9b's test plan is ≈ €1.1 k.

---

## 8. Decisions needed from Ben

| # | Question | Default assumed in K9c |
|---|---|---|
| Q1 | Count **ordinary kitchen content** (pots, pans, GN, knives, utensils: €375) as household equipment rather than machine part? | shown both ways; machine part €4,733 without, €5,108 with |
| Q2 | Count the **furniture equivalent** (Gastro work table as base and worktop, tool-cabinet carcass, fronts, bin pull-out: €420) as the household's kitchen furniture? | not counted (inside €4,733) |
| Q3 | Accept that K9b's function set does not reach €2 k: **≈ €4.7 k after round 1, ≈ €3.3–3.8 k after round 2** at one-unit prices, ≈ €2.8 k in a series — or name functions to give up (§6.3)? | continue with round 2 |
| Q4 | **Household-grade safety** (washing-machine door lock, force-guided relays, EN 60335 practice) instead of machinery-grade parts (+€300–800)? | yes, pending K4 |
| Q5 | **Hobby-grade electronics and motion** (Klipper, Raspberry Pi, open-loop steppers, maker-market rails) in a household appliance with a 10-year life, repaired by swapping €20–135 modules? | yes |
| Q6 | **No second ware set** (the next meal within 30 min, PERF-005, needs +€80 + stubs)? | option, not in the BOM |
| Q7 | COK-002's "≥ 2 positions with ≥ 3 kW": accept one boosted domino zone (inherited from K9b)? | yes |
| Q8 | Round 2: try **H-C** (a bought food processor as the whole hub, −€300, −1 actuator) although it needs a third hot position elsewhere (+300 mm) or a COK-002 waiver and costs hand time? | only if E0 shows hand time to spare |
