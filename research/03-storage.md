# R3 - Storage research: boxes, grid retrieval mechanisms, cold storage, food safety, capacity

Author: R3 research agent (Sonnet). Status: first complete version.
Scope: BRIEF.md "Storage" and "Cold storage" (boxes in a grid, any single box transported to an exit; cold version
works the same way but the exit is thermally closed, ideally inside an off-the-shelf fridge or freezer).

## 0. Method, data quality, conventions

* Sources: web search and page fetches (URLs in section 10). Search budget ran out before every question could be
  checked, and several manufacturer PDFs (Liebherr data sheet, Hamilton, Brooks, AutoStore bin sheet) could not be parsed.
  Where a figure comes from general engineering knowledge rather than a fetched page it is marked **[unverified]**.
  Figures marked **[est]** are my own calculations or estimates; the assumptions are stated next to them.
* Prices are EUR unless stated. "net" = excluding VAT. Retail prices move; treat them as order-of-magnitude
  (+-30 %).
* Dimensions in mm. "GN" = Gastronorm, EN 631-1 (footprints) - the dimensions given are the nominal *outer flange* size.
* Things I could not verify and that gate the design are collected in section 8 (Open issues). The two most important:
  (1) real flange width/thickness of the candidate GN boxes, (2) real interior dimensions of the candidate built-in
  fridges (the manufacturers publish niche and gross volume, not usable interior dimensions).

## 1. Summary of findings (read this first)

1. **Box: use Gastronorm (GN) containers, in the 176 mm family.** GN 1/9 (108 x 176), GN 1/6 (162 x 176 rotated) and
   GN 1/3 (325 x 176) all share the 176 mm dimension, and their other side is 108 : 162 : 325 = 2 : 3 : 6 units of
   54 mm. So S/M/L boxes hang side by side on the same pair of rails in a rack that is only 176 mm deep, with no dead
   space (section 2.4). GN boxes have a rim/flange designed to sit on rails (it is how they sit in a bain-marie or a
   fridge slide), come in polypropylene, polycarbonate, Tritan and stainless, survive -40 to +95/99 C and commercial
   dishwashers, and cost 4-10 EUR each with flat lids.
2. **Mechanism: aisle shuttle with a telescopic fork, the "Rowa/pharmacy" principle.** A carriage moves in X and Z in a
   narrow aisle between two rack faces (front and back of the cabinet) and pulls boxes off rails toward either side. Three actuators (X, Z, fork) plus a
   latch. Pharmacy robots (BD Rowa Vmax) are the proof that this works for years in a dense, cabinet-like setting:
   8-12 s to deliver a pack, 48 dB(A), plastic lead screws, no lubrication.
3. **Fit in 600 mm deep:** two racks of 176 mm plus a 192 mm aisle = 544 mm, leaving only ~56 mm total for skins.
   Feasible for the ambient module but tight; one-sided racks (176 + 192 = 368 mm) are the natural fit inside
   an off-the-shelf fridge. **[est]**
4. **Density:** ~168 boxes (GN 1/6, 100 mm deep, 1.5-1.6 L) per metre of module width. Boxes fill ~50 % of the cabinet
   volume as envelope, ~21 % as usable food volume **[est]**. That is the same ballpark as a household fridge
   (275 L gross in a 548 L niche = 50 %).
5. **Cold: two credible paths.** (A) Off-the-shelf integrated Liebherr-type 178 cm fridge or freezer (niche
   1772-1788 x 560-570 x 550 mm, 245-286 L gross, 999-1,799 EUR) with the door replaced/modified by an insulated
   panel plus a two-stage hatch, and a single-sided rack + carriage inside: ~36-45 GN 1/6 boxes per cell **[est]**.
   (B) A custom vacuum-insulated cold cell with its own compressor: ~2-4x the box count, but a real
   refrigeration development project. Recommend A first.
6. **Hatch leakage is small; box thermal mass is not.** A 350 x 200 mm hatch open 10 s into a -18 C cell exchanges
   ~73 L of air = ~5 kJ ~ 15 kWh/year at 30 openings/day **[est]**. Warming of the box and food during a round trip
   (~40 kJ per freezer round trip **[est]**) is the bigger load and the bigger food-safety issue. Peltier cooling is
   ruled out (COP 0.3-0.7 vs ~2.6 for vapour compression).
7. **Operating at -18 C is solved technology** (Hamilton/Brooks -20 and -80 C stores, Rowa cold modules): keep motors and
   electronics outside the insulation where possible, use low-temperature H1 grease or dry-running polymers, seal and
   conformal-coat everything inside, and expect frost from humid air entering; manage it with an airlock vestibule.
8. **Capacity:** a household of 4 for 2 weeks needs ~26 L (ambient), ~79 L (fridge), ~26 L (freezer) of nominal box
   volume by mass, but the *number of distinct products* (one box per product) drives the slot count:
   ~60-80 ambient, 40-60 fridge, 15-25 freezer boxes **[est]**. One 1 m ambient module + one fridge cell + one freezer
   cell covers this.

## 2. Storage boxes

### 2.1 Gastronorm (EN 631-1) facts

EN 631-1 (1993) defines the footprints of catering containers; standard depths are 20, 40, 65, 100, 150, 200 mm.
Source: gastronorm.it size guide, Wikipedia (section 10).

| GN size | Outer flange size (mm) | Standard depths (mm) | Volume (L) at 65 / 100 / 150 / 200 mm |
|---|---|---|---|
| 1/9 | 108 x 176 | 20, 40, 65, 100 | ~0.5 / ~1.0 / - / - **[unverified]** |
| 1/6 | 176 x 162 | 20 ... 150 (200 exists) | ~1.0 / **1.5-1.6** / 2.0-2.2 / 2.5 (Hendi 880425: 1.5 L at 100, 880418: 2 L at 150, 880401: 2.5 L at 200; gastronorm.it: 1.6 L at 100) |
| 1/4 | 265 x 162 | 20 ... 200 | ~1.9 / ~2.8 / ~4.2 / ~5.5 **[unverified]** |
| 1/3 | 325 x 176 | 20 ... 200 | ~2.5 / ~4.0 / ~6.0 / ~8.0 **[unverified]** |
| 1/2 | 325 x 265 | 20 ... 200 | 3.9 (Cambro Camwear, 65 mm) / **6.0** (Araven 09297, 100 mm, 325 x 265 x 100) / ~9 / ~12 |
| 1/1 | 530 x 325 | 20 ... 200 | 13 L at 100 (Araven) |

Observations:

* The footprint is the *nominal outer flange size*. The body below the flange is a few mm to ~15 mm smaller **[unverified,
  must be measured on the chosen product]**. The flange is what lets a GN container hang in a rail or bain-marie opening.
* GN is a system: every size takes lids of the same footprint, in every material, from every brand (Cambro, Araven,
  Hendi, Rieber, Stellinox, Metro...). Second sources are trivial.

### 2.2 Candidate products (measured/quoted data)

| Product | Outer dims (mm) | Volume | Material | Temp. range | Lid | Price | Notes |
|---|---|---|---|---|---|---|---|
| **Cambro Camwear GN 1/6-65** (polycarbonate) | 176 x 162 x 65 | ~1.0 L **[unverified]** | Polycarbonate (clear) | -40 to +99 C, dishwasher | Cambro "seal cover" (flat, inner seal, -40 to +99 C, dishwasher) or "GripLid" (60CWGL135, PU gasket); flat lid ~4.66 net | 8.39 net / 9.98 gross (Metro/GastroDAX, one source ambiguous); lid 4.66 net | Cambro lids have a grip notch. PC: see BPA note below. Cambro also sells 1/6 x 100 (code DM752 at smartuk) |
| **Cambro GN 1/6-150 PP, translucent** | 176 x 162 x 150 | 2.2 L | Polypropylene | ~-40 to +100 C **[unverified]** | seal cover | 4.15 (restomaster.ee, VAT status unclear) | cheapest data point found |
| **Araven GN 1/6-100** (PP, transparent, airtight lid) | 176 x 162 x 100 | ~1.6 L | Polypropylene | -40 to +95 C, dishwasher (Araven 1/2 spec page) | dual-closure lid: press-on with optional clips, lid doubles as tray; stackable/nestable | 7.10 net / 8.59 gross (horeca.com) | Araven 1/2-100 article 09297 (325 x 265 x 100, 6 L) confirmed; 1/6 lid geometry not fetched |
| **Hendi Profi Line GN 1/6 PP** (880425 / 880418 / 880401) | 176 x 162 x 100/150/200 | 1.5 / 2.0 / 2.5 L | PP, transparent | -40 to +80 C, microwave, dishwasher | lid 881828 "with seal" | price not shown (out of stock online) | temp range lower than Araven claim; confirm |
| **Gastronorm.it polycarbonate/Tritan/stainless/PP** | GN 1/9 ... 1/1 | see 2.1 | PC, Tritan, PP, SAN, stainless AISI 304 | - | flat and clip lids | not fetched | Italian maker, Tritan option (BPA-free, clear) |
| **Cambro CamSquares** 2 qt / 4 qt, PC or PP | 184 x 184 x 97 (2 qt), 184 x 184 x 187 (4 qt); lid 190 x 190 x 13 | 1.9 L / 3.8 L | Polycarbonate (Classic) or PP (translucent) | -40 to ~+99 C **[unverified for PP]** | flat push-on lid, one lid fits 2 and 4 qt | US only: 4.49 / 5.99 USD, lid 1.99 USD | Excellent modularity (2 qt : 4 qt = 1 : 2 in height). No flange; rim is a plain bead. Not stocked at EU wholesalers I found |
| **Auer EG 3212** Euro container 300 x 200 | 300 x 200 x 120, inner 270 x 170 x 115 | 5.3 L | PP | typically -30 to +90 C **[unverified]** | none as standard; EDP hinged lid versions exist | not found | Larger "L" size. 170 mm high version: 7.6 L. Grid basis is 200 mm, incompatible with 176 mm GN rack |
| **Euro containers 400 x 300 / 600 x 400** | 400 x 300 x 220 = 20 L; 600 x 400 x 120-320 = 24-65 L | 20-65 L | PP | - | lids optional | - | Too big for "small to medium" box; useful only for bulk (potatoes, flour sack) - mention only |
| **Lock&Lock HPL817 / HPL818** | 205 x 134 (817: 1 L; 818: x 118 mm, 1.9 L) | 1.0 / 1.9 L | PP | freezer to +100 C **[unverified]** | 4 hinged latches + silicone gasket (airtight, watertight) | 5.29 / 11-14 (Amazon.de, Otto; 6.29 bulk) | cheap consumer standard; latch lids are hard to automate, rim not a rail flange |
| **IKEA 365+ rectangular** | 210 x 150 x 70 (1.0 L), 210 x 150 x 120 (2.0 L) | 1.0 / 2.0 L | PP, with silicone-sealed lid | freezer, microwave, dishwasher | clip lid | 2.99 / lid 2.50 / set 5.49 USD (US site) | cheapest; sizes stack; lid clips not machine-friendly |
| **Rotho Domino freezer boxes** | approx. 157 x 118 x 75 (0.75 L); 233 x 118 x 105 (1.5 L) **[dimensions from garbled search snippets - unverified]** | 0.2-1.5 L | PP, BPA-free | -40 C (freezer) to microwave, dishwasher | press-on lid | ~8 EUR / 4-pack | consumer freezer boxes |
| **OXO Good Grips POP** | not researched | - | - | - | push-button airtight lid | - | **not researched, no data**; push-button lid could in principle be actuated by a machine; likely not freezer-rated **[unverified]** |
| **Laboratory / industrial small-parts bins** (Auer/Schoeller "Lagersichtkästen", "Regalkästen") | many sizes, e.g. 300 x 200 x 120 | 1-10 L | PP | - | open front, no lid | ~3-8 EUR **[unverified]** | Open boxes accumulate dust/food; hygiene poor for food; only useful for non-food parts inside the machine |

BPA note **[unverified, verify before design freeze]**: polycarbonate contains bisphenol A. I recall that the EU adopted a
regulation (2024/3190) banning BPA/bisphenols in food-contact materials, phased in from 2026. That would rule
new PC boxes out for a product sold in the EU. Prefer PP, Tritan (copolyester) or PPSU, which are also free of the aging
(crazing, clouding) that PC shows in commercial dishwashers with alkaline detergents.

### 2.3 Criteria specific to this machine

| Criterion | GN (flange) | CamSquare / Euro (no flange) | Consumer clip boxes |
|---|---|---|---|
| Hanging on rails | yes, flange is the interface | no; would need a carrier tray or side pockets | no |
| Gripping by a machine | fork under flange, or hooks over flange | must grip walls or use a carrier | walls only |
| Lid removable by a machine | flat lid: vacuum cup or hook in grip notch. Clip lids: needs clip release, avoid | flat lid (CamSquare): vacuum cup | latches: 4 actuators, no |
| Stackable/nestable | nestable (empty), stackable (with lids) | stackable | stackable |
| Dishwasher (box washer) | yes, gastro dishwashers have GN baskets | yes | consumer dishwasher |
| Freezer | yes, -40 C | yes | yes |
| Second sources | many | few in EU | many |
| Cost/box | 4-10 EUR | ~5 USD | 3-14 |

**Lid strategy.** Recommended lid: flat, gasketed press-on lid without clips (Cambro seal cover/GripLid type; Araven lid
used without its clips). Machine opens it at a lid station: vacuum cup on the flat top, or a hook into the grip notch,
lifts it and parks it on a lid rest; the lid is washed with the box. Freezer detail: PP/PC shrinks at -18 C
and gasket lids grip tighter; the lid-lifting force must be tested at -18 C **[unverified]**.

**Rim geometry for hanging on rails.** Two L-section stainless rails per level (running front to back) carry the flange
undersides. Required: flange width >= ~6 mm and rigid; the lid must sit *on top of* the flange, not wrap around it
(Cambro seal covers are of this type), or the rail cannot reach the flange. **[must be verified on samples]**

### 2.4 Recommended box families and the S/M/L grid

**Family 1 (primary): GN 176-family in PP or Tritan (PC only if BPA regulation allows).**

| Size | GN | Footprint in rack (X x Y) | Depths / usable volume | Use |
|---|---|---|---|---|
| S | 1/9 | 108 x 176 | 65 mm (~0.5 L), 100 mm (~1.0 L) **[unverified]** | spices, herbs, salt, sugar, small items |
| M | 1/6 | 162 x 176 (rotated) | 65 (1.0 L), 100 (1.5-1.6 L), 150 (2.0-2.2 L) | the standard box: veg, meat portions, cheese, rice |
| L | 1/3 | 325 x 176 | 100 (~4 L), 150 (~6 L) **[unverified]** | pasta, flour, potatoes, roast, bulk |

Why they fit together: Y = 176 mm for all three. X = 108, 162, 325 mm = 2, 3, 6 units of 54 mm
(324 for 1/3 within 1 mm). With continuous rails per level the boxes can be placed at any X position (no fixed slots),
so mixed sizes never leave a gap larger than the free fraction of the level. Depths are multiples of a 25 mm
module: rack pitch = box depth + ~25 mm (lid, fork lift, clearance) **[est]**: 65 mm -> 100 pitch, 100 -> 125,
150 -> 175, 200 -> 225. Use adjustable rail heights on perforated uprights.

Not compatible with Y = 176: GN 1/4 (265 x 162) and GN 1/2 (325 x 265) - avoid them.

**Family 2 (alternate for dry bulk): Cambro CamSquares 184 x 184** (2 qt = 97 mm high, 4 qt = 187 mm high, one lid) -
needs a carrier tray, US supply only. Not recommended.

**Family 3 (alternate L size): Euro 300 x 200 x 120-170 (5.3-7.6 L)**, mounted in carriers - different grid (200 mm), not
recommended unless L boxes larger than 6 L are needed.

**Family 4 (fallback for cheap prototypes): Lock&Lock HPL817/818 or IKEA 365+ 2 L**, for the first hand-built prototype
only.

Stainless GN (AISI 304, e.g. maxima.com 1/6 x 100): pros: indestructible, hot-washable, no odour retention; cons: opaque
(no camera check of contents), heavier (0.3-0.5 kg vs 0.1-0.2 kg), cold conductive (ok), more expensive (~10-25 EUR
each **[unverified]**), no vacuum-cup on domed lid. Keep as an option for hot-fill only.

## 3. Grid retrieval mechanisms

### 3.1 Comparison

Reference cabinet: 600 mm deep x 2000 mm high, module width 1000-1200 mm. "Density" = share of cabinet volume that
is occupied by box envelopes (boxes only, without contents fraction). Numbers for candidate A are my calculation, for
others rough estimates **[est]** unless a source is given.

| # | Mechanism | Density (boxes in cabinet volume) | Actuators | Retrieval time | Main failure modes | Cleanability | Fit in 600 x 2000 | Off-the-shelf linear parts? |
|---|---|---|---|---|---|---|---|---|
| A | **Aisle shuttle (XZ carriage + telescopic fork), racks left/right of the aisle (BD Rowa Vmax principle; mini-load AS/RS)** | ~50 % (2 racks + aisle) | 3 (X, Z, fork) + 1 latch | 10-20 s; Rowa quotes 8-12 s for a pack | jammed box, belt slip, lost position (home switch), box tilting on rail | good: open rails, no crevices, aisle can be sprayed; no moving parts under food | excellent (544 mm, see 3.2) | yes: belts/leadscrews, MGN/HGR rails, igus drylin, NEMA 23 steppers |
| B | **Top-access cube grid (AutoStore)** miniaturised to 176 mm boxes | 85-90 % (only top layer for robot) | 4 (X, Y, hoist, gripper) | 30-90 s (dig through stacks above; bins 220-425 mm high, up to 26 levels; robot 3.1 m/s) | digging failure, blocked stack, gripper misgrip, top 250 mm lost | moderate: top and grid open to falling debris; walls can be washed | grid needs ~3 boxes x ~7 columns; top 250 mm for robot; exit is at the *top* (2000 mm high) | no: hoist and gripper are custom; standard rails for XY |
| C | **Vertical lift module (Kardex Shuttle)** | 55-60 % (tray + 100 mm height grid) | 3 (extractor lift, tray drive, box picker at window) | 15-40 s (tray to window, then pick) | tray jam blocks a whole tray, tray drive loads | poor: trays and open extractor | Kardex minimum tray width 1,580 mm, depth 2,312-4,343 mm, load 560-1,000 kg per tray - **does not scale down**; only the principle | no |
| D | **Vertical carousel/paternoster (trays on chain loop)** | 40-50 % (return path unusable) | 1 (chain) + 1-2 (exit puller) | 10-60 s (half loop) | chain elongation, tray tilt, single point of failure, motor brake | poor to moderate: chain, hangers, food spill spreads | trays 1.1 x 0.55 m fit; loop height 1.7 m gives ~17 trays x 6 boxes = ~100 boxes | yes: standard roller chain (H1 lube) and motor; custom trays |
| E | **Racks on wall served by XZ gantry in front with fork (pharmacy "front picker")** | 35-40 % (single face) | 3 | 10-20 s | same as A | good | aisle at front = user side, unattractive; the machine is closed anyway | yes |
| F | **Sliding puzzle (15-puzzle) grid** | 90-98 % | 2 per row and per column, or many small drives (e.g. 12 rows + 6 columns) | 20 s to minutes (many shifts) | jams, tolerance stack-up, synchronised motion, one stuck drive freezes a row | poor: rollers and pushers everywhere | fits, but 18+ motors | partly (many identical drives) |
| G | **Pharmacy picking robot (Rowa Vmax, Gollmann)** = A with a multi-pack picking head | up to 4,000 packs per running metre and 56,000 packs (Vmax, manufacturer claim); packs 35x15x15 to 230x140x145 mm | XZ + horizontal toggle between two opposite shelves, picking head with drylin high-helix lead screw (14 mm dia, 25 mm lead) | 8-12 s | ~ none reported; optional second picking head and backup drives for availability | "automated cleaning module available" | Vmax 130: 1.33 m wide, 2.12-3.52 m high, 2.68-15.17 m long: larger, but scalable principle | yes: igus drylin screws/guides, chains |
| H | **Vending machine elevator/lift** (delivery bucket) | n/a | 1-2 | 3-6 s | product jams | good | fine | yes |
| I | **3D-printer tool changers / filament and tool storage** (Prusa XL, Jubilee, CNC ATC carousels) | 30-60 % | 1-3 | 2-10 s | mis-docking, dust | moderate | scale is small | yes |
| J | **Laboratory sample stores at -20/-80 C (Hamilton Verso Q, BiOS; Brooks SampleStore SE)** | 100,000-4,000,000 tubes; Verso Q 152,000 tubes at ambient to -20 C | robot inside the cold space (gantry/XYZ picker) + access module | Verso Q up to 390 tubes/h; BiOS up to 100 tubes/h at 5 % hit rate | ice on robot, mis-pick | closed, automatic defrost cycles **[unverified]** | not cabinet-size, but proves robot-in-freezer | no (proprietary) |

### 3.2 Recommended geometry (candidate A, "Rowa in a cabinet")

Plan view (looking down), ambient module:

```
 front of cabinet (user side / transport side)
 +-------------------------------------------------------------+
 | rack row F  (boxes, Y=176 deep, hanging on rails)           |  176
 |-------------------------------------------------------------|
 |  aisle: carriage moves in X, lifts in Z, fork in +/-Y        |  192
 |-------------------------------------------------------------|
 | rack row B                                                  |  176
 +-------------------------------------------------------------+
   back wall                                      total 544 mm + skins ~ 2 x 15 = 574 mm  (cabinet 600)

 Section (Y-Z), one rack face:   rails at every 100/125/175 mm pitch, boxes hang by the flange.
 Exit hatch at the aisle end (or in the aisle side wall): carriage brings box to the hatch opening.
```

Numbers **[est]**:

* Per 1000 mm module width: 6 boxes GN 1/6 per level and face (162 wide + 4 mm clearance = 166 pitch; 6 x 166 = 996 mm, so ~1,030 mm inside width is really needed).
* Usable rack height ~1,750 mm (2,000 minus plinth ~100, minus top/electronics ~100, minus carriage top clearance
  ~50): 14 levels at 125 mm pitch (100 mm boxes).
* Boxes per metre of width: 6 x 14 x 2 faces = **168 boxes** GN 1/6-100 = 252 L content (1.5 L) or 599 L envelope
  (168 x 176 x 162 x 125 mm) out of 1,200 L cabinet volume -> 50 % envelope, 21 % content.
* Mixed heights and sizes reduce the count by 15-25 % (fragmentation); 130-140 boxes is a realistic number.
* Carriage: 192 mm wide aisle = box 176 + 2 x 8 clearance; fork: telescopic 2-stage 300 mm stroke (one-way
  176 + margin), driven by a stepper with a rack, or a linear rail with a belt; hooks engage under the flange or into the
  lid grip notch. Z: belt with counterweight or a ball screw (leadscrew must not back-drive: 2 kg carriage +
  2-6 kg box). X: belt on rails.
* Speed: X 0.5-1 m/s, Z 0.3-0.5 m/s, fork 0.3 m/s -> mean 12-20 s per retrieval including hatch handover.
* Position sensing: reference switches, encoders on steppers or closed-loop steppers; per-level barcode or
  RFID to verify the box ID at the fork (camera-free).
* Failure recovery: any jam leaves the box in the aisle; the carriage can reverse; a service flap on the aisle end
  face lets a human remove a stuck box (repair accessibility requirement).
* Actuator count: 3 axes + hatch + lid station. Compare the sliding puzzle (~18) or a carousel (2-3 with exit puller).

Cleaning of the aisle **[est, coordinate with R6]**: boxes are lidded, so contamination reaches the store mainly via
box exteriors and the hatch. A periodic wash cycle (spray nozzles in the aisle ceiling and between rack rows, sloped floor with drain, boxes may stay in if lids
are closed and rails are stainless) is sufficient; the carriage parks in a drying position. Hygienic design rule:
no exposed cable chains or greased screws inside the aisle unless H1 lubricant and washable; use stainless
or plastic rails and belts of PU with FDA/EU-compliant material.

**Why not the others:**

* B (AutoStore-style) gives the best density and fits a top-loading chest, but random access needs "digging" and free
  stacks; with a box stack 14 high the expected number of boxes to move is ~7 and retrieval takes a minute or more. The gripper and hoist are custom. The
  robot must sit on top of the cabinet.
* C (VLM): principle is right for tray-based goods but the machine sizes are >1.5 x 2.3 m and trays are heavy, so it does not scale down.
* D (paternoster) is the simplest fallback (few motors) but hygiene and the return-path volume loss (~50 %) are worse.
* F (sliding puzzle) has the best density but too many actuators and jam risk; also every drive would be inside the cold cell.

## 4. Cold storage

### 4.1 Off-the-shelf built-in and freestanding candidates

All Liebherr figures are from liebherr.com pages fetched or found in search results (URLs in section 10). Niche dimensions
are height / width / depth in cm.

| Model | Type | Niche H/W/D (cm) | Gross/net volume | Cooling | Energy | Price (EUR incl. VAT) | Notes |
|---|---|---|---|---|---|---|---|
| Liebherr **IRBe 5121** | fridge + small freezer compartment, integrated | 177.2-178.8 / 56-57 / 55 | 248 L fridge + 27 L freezer (275 L) | static **[unverified]** | not found | 999-1,299 (Otto, Euronics) | cheapest 178 cm option; device 559 x 1770 x 546 mm |
| Liebherr **IRBd 5121 plus BioFresh** | fridge | 177.2-178.8 / 56-57 / 55 | 275 L | BioFresh drawers (0 C, "HydroSafe/DrySafe" humidity drawers **[unverified details]**) | not found | 1,659 | fixed door, hinge reverse 49 EUR |
| Liebherr **IRDdi 5121 plus** | fridge with EasyFresh | 177.2-178.8 / 56-57 / 55 | 286 L | - | not found | 1,519 | |
| Liebherr **ICc 5123 plus** | fridge-freezer | 177.2-178.8 / 56-57 / 55 | 264 L | - | - | - | |
| Liebherr **ICNb / ICNc 5123 plus NoFrost** | fridge-freezer, NoFrost | 177.2-178.8 / 56-57 / 55 | 253 L | NoFrost (fan, evaporator behind wall) | - | - | |
| Liebherr **ICBNci 5153 prime BioFresh NoFrost** | fridge-freezer | 178 cm niche | 245 L | NoFrost | - | - | |
| Liebherr **IFNd 3924 plus NoFrost** | under-counter freezer | 87.4-89 / 56-57 / 55 | 87 L | NoFrost | class D | 1,099 | too small alone |
| Liebherr **IFNbi 3553 prime NoFrost** | under-counter freezer, 3 drawers | 71.4-73 / 56-57 / 55 | 65 L | NoFrost | 94 kWh/year (0.257 kWh/24 h), class B, 33 dB | GBP 1,199 / CHF 1,430 | |
| Liebherr **UIKo 1550-26** | under-counter drawer fridge | 59.7 wide x 82 high x 55 deep (device) | 132 L per one source **[conflicting]** | - | - | - | 3 drawers on telescopic rails; test.de: UIK 1550 ~90 L usable |
| Miele **KU 7175 D** | under-counter, 2 drawers with individual 0-14 C zones | 60 cm | - | - | - | from spring 2026 | independent temperature zones |
| Norcool drawer fridge | under-counter, 2 drawers + inner drawer | 82 cm niche | 180 L gross / 104 L net | - | - | - | Fisher & Paykel style |

What is not available from manufacturers: **interior dimensions**. A niche of 560 x 550 with 40-50 mm insulation and
a door with shelves typically gives an interior of ~ 480-500 W x ~1,500 H x ~350-400 D **[unverified, est]** (275 L gross
in a 548 L niche = 50 % suggests it). A GN 1/6 rack with 3 boxes across (3 x 166 = 498) would just fit width-wise; depth 176 + carriage aisle ~192 = 368 is
borderline. This is **the** gating check for the cold design; measure a real unit.

### 4.2 Cooling type matters

* **Static** (plate evaporator, natural convection; fridges): evaporator plates on the rear wall are the coldest
  surface and collect the frost; air is not blown, so humidity stays high (~80-90 %) which is good for produce
  but the cell warms more after opening. Simple, quiet. Interior has free space in front of the rear wall.
* **No-frost / fan** (freezers, fridge-freezers): fan and evaporator behind a rear or top cover; strong airflow
  removes moisture from food (freezer burn, dry vegetables), a defrost heater melts evaporator ice cyclically.
  Frequent small openings inject humid air, so the defrost frequency rises; fans push cold air through hatch openings
  faster. Advantage: temperature recovers quickly and frost stays on the evaporator, not on the rails.
  The fan duct takes ~30-50 mm of interior depth.
* Recommendation **[est]**: fridge = static (humidity); freezer = no-frost (frost management, recovery).

### 4.3 Ways to automate access (ranked)

1. **Fridge/freezer shell, original door replaced (or kept as service door) by an insulated panel with a two-stage hatch.**
   Keep the original interior, evaporator and controller; build a single-sided rack and X/Z carriage inside (motors outside).
   This is the brief's "ideally an off-the-shelf fridge/freezer, possibly with a slightly modified door".
   Door: original door foam is ~40-50 mm PU. Best practice: keep the OEM door in place as a **service door** (open
   for repair and deep cleaning) and fit the hatch in it, or replace it by a machine-built door with the same
   gasket geometry. Warranty is void either way.
2. **Airlock vestibule (recommended sub-concept for any option):** a small insulated chamber (e.g. 350 x 200 x 250 mm =
   17 L) with two doors (outer, inner) that are never open at the same time; the carriage puts the box in the vestibule, inner door
   closes, outer door opens to the transport system. Warm/humid air enters only the vestibule volume (17 L, not 73 L), and a small
   dry-air purge (or a silica-gel cartridge) can keep the vestibule frost-free.
3. **Simple hatch flap** (single door, one 10 s opening): acceptable for the fridge, borderline for the freezer.
4. **Motorised drawer** (under-counter drawer fridge on telescopic rails): the drawer opens into a vestibule-like area where a gripper picks boxes from the
   top. Simple but open time and opening area are large; 3 drawers hold only ~12 GN 1/6 boxes. Good for a small
   "daily use" fridge, not for the main store.
5. **Wine-cooler/display fridge** (commercial 600 mm units, fan cooled): interior is roomy and racks are modifiable,
   glass doors leak heat; depth ~600 mm typical **[unverified]** means the cabinet would exceed 600. Not recommended.
6. **DIY cold cell with monoblock unit or own compressor:**
   * plug-in monoblock units (e.g. Kältetechnikshop/Viessmann/Rivacold): wall unit for +2 C cells from ~1,800 EUR net; ceiling units for deep-freeze
     3,000-9,200 EUR net; sized for 5-15 m^3 - hugely oversized for a 0.5-1 m^3 cell.
   * Insulation: PIR panel for -18 C needs ~100 mm per wall; in a 600 mm deep cabinet that leaves only 400 mm interior. **Vacuum insulation panels (VIP)** ~20-25 mm
     give the same U-value (lambda ~7 mW/mK vs 22-25 for PIR **[unverified]**) and leave ~500 mm interior; VIP cost ~ 3-5x PIR **[unverified]**.
   * Compressor: small R290/R600a hermetic compressors (e.g. Secop/Danfoss, 100-300 W cooling) with a static or fan evaporator - these are
     what the household fridge already contains. Re-using the refrigeration chassis of a household freezer is an option but a hack.
7. **Peltier:** COP 0.3-0.7 versus ~2.6 for vapour compression (source: ScienceDirect comparison); at -18 C with ambient +25 C (dT ~ 43 K)
   the COP falls far below 0.5 **[unverified]**, i.e. >200 W electrical for a 50-100 W load. Not viable for the main store;
   acceptable only for local tasks (dehumidifying a vestibule, cooling a small box).

### 4.4 Heat leakage estimates for a hatch **[est]**

Method: buoyancy-driven exchange through an opening (Brown-Solvason / Gosney-Olama simplified):
volumetric flow Q = (Cd/3) x A x sqrt(g x H x dT / T), Cd ~ 0.6, H = opening height, dT = ambient - cell,
T = mean absolute temperature. Room air 20 C / 50 % RH (h = 38.5 kJ/kg, w = 7.3 g/kg); freezer air -18 C over ice
(h = -16 kJ/kg, w = 0.8 g/kg). Enthalpy difference 54.7 kJ/kg ~ 70 kJ/m^3; fridge +4 C, 80 % RH: dh = 24 kJ/kg ~ 30 kJ/m^3.
These are crude (factor 2 accuracy).

| Opening | Freezer flow while open | Air exchanged per 10 s opening | Energy per opening | at 30 openings/day | Ice load (freezer) |
|---|---|---|---|---|---|
| Small hatch 206 x 150 mm (for GN 1/6) | ~2.8 L/s | 28 L | ~2 kJ | ~6 kWh/year | ~0.2 g |
| Hatch 350 x 200 mm (for GN 1/3) | ~7.3 L/s (160-450 W while open) | 73 L | ~5 kJ | ~15 kWh/year (~8-10 kWh electric at COP 1.5-2) | 0.57 g per opening = ~6 kg/year on evaporator |
| Airlock vestibule 17 L | - | 17 L per cycle | ~1.2 kJ | ~4 kWh/year | 0.13 g |
| Fridge (+4 C) 350 x 200 mm hatch | ~4.6 L/s | 46 L | ~1.4 kJ | ~4 kWh/year | negligible |
| Closed hatch, 50 mm PU insulation, seal | conduction 0.3-1 W | - | - | ~3-9 kWh/year | - |

Compare: complete household freezer 65 L class B = 94 kWh/year (Liebherr IFNbi 3553), a 180-250 L unit ~150-250 kWh/year
**[unverified]**. So hatch air leakage adds 5-15 %. **Warm boxes are the bigger load:** a frozen box (1 kg food at 2 kJ/kgK +
0.25 kg PP at 1.9 kJ/kgK) that warms by 10 K (food) / 38 K (box shell) during a 10-minute trip costs ~40 kJ to
re-cool: ~1 MJ/day at 25 trips/day (0.3 kWh/day = 100 kWh/year). Design for few trips: pull only what the recipe needs,
consume within the session, and return the leftovers as new inventory only for fridge-class items (freezer items must
not be refrozen after thawing).

### 4.5 Motors, rails, electronics and sensors at +4 C and -18 C

Sources: general practice and search results on cold-storage robots; specific device data not verified.

| Topic | +4 C (fridge) | -18 C (freezer) | Mitigation |
|---|---|---|---|
| Condensation | when humid room air enters, water condenses on all surfaces colder than dew point (rails, boxes, electronics) | vapour deposits as frost (rime) on surfaces at/below 0 C | vestibule, dry-air purge, keep all electronics warmer than the air (self-heating) or sealed |
| Icing of rails | thin water film, corrosion of carbon steel | frost builds on rails and in grooves; friction rises, sensors are blinded | stainless rails, wipers/scrapers on the carriage, wide clearances, dry-running plastic on steel (no grease), periodic warm-up/defrost cycle (no-frost fridge already does this on the evaporator) |
| Lubricant | any H1 grease | grease stiffens ("honey" at -20 C for normal grease); use H1 low-temp grease: Klüberalfa BF 83-102 (-45/-50 C), Molykote 33 medium (silicone, -73 C; not H1-food certified **[unverified]**), Food Grease LT2 (Al-complex, -40 C, NSF H1), LPS Detex Food Grade Low-Temp (-40 C..) | **prefer dry-running plastics** (igus drylin/iglidur, high-helix screws with plastic nut; used in Rowa Vmax without lubrication) |
| Stepper motors | no problem | ordinary industrial steppers are specified about -20 to +50 C ambient **[unverified]**; winding resistance falls, so torque is available, but bearing grease stiffens, frost and ice on the rotor gap is a risk; the stepper's own heat helps | mount motors **outside** the insulated cell with a shaft through a low-conductivity bushing (thermal-bridge minimised) or in a warm pocket; else use sealed (IP65+), low-temp bearing grease |
| Belts | PU/neoprene ok | PU timing belts (steel or aramid cord) stay flexible to about -30 C **[unverified]**; neoprene ~ -30 C; avoid PLA parts (brittle) - use PETG/PA12 | choose PU GT2/HTD, tension check, check wheels for ice |
| Cables/connectors | ok | PUR-jacketed chainflex cables rated to -40 C (igus), silicone leads; standard PVC cracks at about -15 to -20 C **[unverified]** | cold-rated cables; pass-throughs in a thermal break; dielectric grease on connectors |
| Electronics | conformal coat, IP54 | IP65/67 housings, conformal coating on PCBs, keep controllers outside; freezers and warm-up cycles bring condensation | controllers outside the cell, only sensors and stepper drivers' outputs go in; heating element (5-10 W) for encoder heads |
| Sensors | ok | optical encoders/limit switches ok, camera lenses fog when the vestibule opens; **load cells** drift at -18 C (compensated range typically -10..+40 C **[unverified]**) | put load cell, camera and barcode reader in the warm exit station, not inside the cell; use Hall/inductive sensors inside |
| Refrigeration load from motors | negligible | each watt inside costs ~0.5-0.7 W of compressor electricity | keep dissipation low: brake holding current off when parked, duty cycle low |

**What automated freezers do.** Hamilton BiOS (-80 C, 100,000-23 million samples, up to 100 tubes/h at 5 % hit rate) and Brooks/
Hamilton -20 C stores (Verso Q: 152,000 tubes, 390 tubes/h; Brooks SampleStore SE 105,000 2 mL tubes) put the robot inside
the cold, keep the sample carriers in cold, and use an access chamber to hand over. I could not fetch the
manuals; typical practice (from literature and marketing) is a dry, nitrogen or dry-air purge, cold-rated motors
and lubricants, automatic heating cycles for the robot, and minimal exposure of samples to warm air (this is
the same core problem as here, with 1000x more expensive hardware). Pharmacy robots (BD Rowa) offer "refrigerated storage units with lamella
technology" (possibly a curtain that separates a 2-8 C module from the room; details **[unverified]**) and run 8-12 s picks at 48 dB(A) with plastic lead screws.

### 4.6 Recommended cold design (D2 input)

* **Cold cell 1 (fridge):** integrated 178 cm static fridge (e.g. Liebherr IRBe 5121, 999-1,299 EUR), remove the door
  bins and shelves, install a 3-column x ~11-12-level single-sided rack (front aisle with carriage, back-wall rack) **[est]** with
  3 x 166 mm = 498 mm width (measure first!). ~33-45 GN 1/6 boxes (1.0-1.6 L), i.e. ~50-70 L of food.
* **Cold cell 2 (freezer):** integrated 178 cm NoFrost freezer of the same niche (IFNe/IFNd 5x53 class **[model not verified]**;
  the verified NoFrost freezers are the under-counter ones: IFNd 3924 87 L 1,099 EUR, IFNbi 3553 65 L). Alternative: two IFNd 3924 stacked
  (2 x 88 cm niche = 176 cm) - too little interior.
* Door: replace with an insulated door incl. two-stage hatch and vestibule; keep OEM door as service access.
* Drives: X and Z motors outside the insulation, belts through a labyrinth slot in the cell wall with a brush seal (cheap) or magnetic
  coupling (sealed, no penetration; costly).
* If the interior turns out too small: option B (VIP cell) in the same cabinet footprint.

## 5. Food safety aspects of storage

Sources: EU/BfR guidance from general knowledge; the BfR page fetched carried no storage details, so this
section is **[unverified] but standard practice**.

| Food group | Store | Temperature | Humidity | Notes |
|---|---|---|---|---|
| Dry staples (flour, rice, pasta, sugar, salt, oil, dried legumes, canned goods) | ambient | <= 20-25 C, dark | low (<60 % RH) | sealed boxes vs pantry moths and moisture |
| Potatoes, onions, garlic, squash | ambient/cool, dark | 8-12 C ideal, 15-20 C ok for 2 weeks | onions/garlic dry 60-70 %, potatoes 85-90 % | potatoes < 6 C: starch to sugar (acrylamide when fried) - **not** the fridge; onions/garlic separate from potatoes (onions release gas, sprouting) |
| Tomatoes, bananas, avocado, citrus, pineapple, cucumbers (sensitive < 10 C) | ambient | 12-18 C | - | cold damage; tomatoes lose flavour in the fridge |
| Fresh vegetables (leafy, broccoli, carrots, peppers), berries, mushrooms | fridge | 2-8 C (4-5 C typical) | 85-95 % (crisper) | ventilated or loosely closed boxes, drier for mushrooms |
| Fresh meat and fish | fridge coldest zone | 0-4 C | - | lidded, separate boxes; raw items lowest |
| Dairy, eggs, cooked leftovers, opened jars | fridge | <= 7 C (EU law), ~4 C target | - | leftovers are the highest risk: 2-3 days |
| Frozen food | freezer | -18 C or colder | - | never refreeze thawed items; sublimation ("freezer burn") shortens quality: lidded boxes |
| Bread | freezer or ambient | - | - | fridge accelerates staling |

* **Ethylene:** apples, pears, bananas, tomatoes, avocados, melons emit ethylene (Wikipedia: bananas/apples);
  broccoli, leafy greens, cucumbers, carrots, berries and flowers are damaged. In lidded boxes with only a few
  hundred mL of air, buildup is small but real; keep emitters in their own boxes and keep the lids closed, or place
  them in the ambient zone.
* **Odours:** onions, garlic, cheese, fish and strong spices transfer odour to PP (PP is porous to aromatics and
  stains with tomato/curry; Tritan and stainless do not). Use a lid gasket, wash the box (box washer 60-85 C) after each
  emptying, and consider separate boxes for strong foods.
* **Open vs lidded:** lidded always in freezer and fridge (odour, freezer burn, drying, cross-contamination when the carriage
  handles other boxes). Produce boxes: vented lids or loosely fitted lids to prevent condensation; never seal wet produce airtight
  in the fridge for more than a few days.
* **FIFO and shelf life:** inventory unit = the box (one product batch per box; never mix batches). Database record: box ID,
  EAN, product, batch, ingest date, "use by", opened date, storage class; retrieval prefers the earliest expiry;
  reminder or automatic menu suggestion before expiry; cooked leftovers get a 2-3 day timer. HACCP-style log: cell
  temperature every minute; alarm above 7 C for > 2 h (fridge) or above -15 C (freezer), automatic block of
  affected boxes ("quarantine") and notification. A box outside the cell for more than 2 h (2-hour rule) must be consumed or discarded.
* **Weight sensing:** a load cell at the exit station (warm, outside the cell) weighs each box on the way out and back:
  tare weight per box ID (stored), so net content weight is known to ~1-2 g (5-20 kg cells, 24-bit ADC) **[est]**;
  the difference before/after a dosing step is the used quantity, automatically updating stock and detecting empty
  or wrong contents. Box ID: 2D code or NFC tag on the box body, not the lid (lids can be swapped), must survive 85 C dishwasher; laser
  engraved QR on PP/Tritan works, or laundry-grade NFC tags. Optional: humidity/temperature logger per cell; door-open counter.

## 6. Capacity estimate

Assumptions **[est]**: food purchased and stored 1.2 kg/person/day excluding beverages (about 1.0 kg eaten + waste and packaging;
German household food consumption is roughly 1.0-1.5 kg/person/day **[unverified]**); split by mass: ambient 30 %, fridge 50 %,
freezer 20 %. Bulk density as stored in boxes: ambient 0.6, fridge 0.5, freezer 0.6 kg/L. Box fill 85 % of the nominal volume. Then
stock = persons x days x 1.2 kg.

| Household / autonomy | Mass (kg) | Ambient: mass -> box volume (L) | Fridge: mass -> box volume (L) | Freezer: mass -> box volume (L) |
|---|---|---|---|---|
| 2 persons, 1 week | 16.8 | 5.0 kg -> 9.9 L | 8.4 kg -> 19.8 L | 3.4 kg -> 6.6 L |
| 2 persons, 2 weeks | 33.6 | 10.1 -> 19.8 | 16.8 -> 39.5 | 6.7 -> 13.2 |
| 3 persons, 2 weeks | 50.4 | 15.1 -> 29.6 | 25.2 -> 59.3 | 10.1 -> 19.8 |
| 4 persons, 1 week | 33.6 | 10.1 -> 19.8 | 16.8 -> 39.5 | 6.7 -> 13.2 |
| 4 persons, 2 weeks | 67.2 | 20.2 -> 39.5 | 33.6 -> 79.0 | 13.4 -> 26.3 |

The volume of the *cabinet* is not the driver: **the number of boxes is set by the number of distinct products**, since a
box holds one product. Assuming a household has ~60-80 ambient items (spices ~25 in GN 1/9 boxes; staples), 40-60 fridge items and 15-25
freezer items, plus a 1.3 partial-fill factor, needed slots **[est]**:

| Zone | Boxes needed (2-4 persons, 1-2 weeks) | Box mix | One 1 m module gives | Cold cell (see 4.6) |
|---|---|---|---|---|
| Ambient | 60-80 (of which 25-30 S = GN 1/9) | S 30 %, M 50 %, L 20 % | ~130-168 | - |
| Fridge | 40-60 (M 65-100 mm, L 100 mm) | M 70 %, L 15 %, S 15 % | - | 33-45 per 178 cm cell -> **plan 1 cell for 2 persons, 1.3 cells for 4** (tight), or 2 cells |
| Freezer | 15-25 (M 100-150 mm) | M 80 %, L 20 % | - | 33-45 per cell: **comfortable** |

Total box population for a 4-person, 2-week household: ~115-165 boxes; all volumes together ~135-150 L box volume by mass or ~270-330 L when
counting envelope volume (150 boxes x 1.5-2 L nominal x 1.3 fragmentation). The three zones together (one 1 m ambient module,
one fridge cell, one freezer cell) fit inside a **2.4-3.0 m wide** run of the machine, i.e. about 2-3 kitchen modules of 60 cm width and 2 m height.
Sensitivity: a stock-loving household (x2) needs 2 fridge cells.

## 7. Recommendations and ranked alternatives

**Box.** Recommended: **GN polypropylene or Tritan boxes in the 176 mm family: S = GN 1/9 (108 x 176), M = GN 1/6 (162 x 176), L = GN 1/3
(325 x 176), depths 65/100/150 mm, with flat gasketed press-on lids.** Prices 4-10 EUR per box, 4-5 EUR per lid, second sources
(Cambro, Araven, Hendi, Gastronorm.it). Ranking:
1. GN PP/Tritan (Araven, Hendi 880401/880418/880425 + lid 881828, Cambro PP) - primary.
2. GN polycarbonate (Cambro Camwear + Seal Cover) - best lid, pending BPA rules.
3. GN stainless - specific uses (hot fill, very durable).
4. CamSquares - fallback for a square footprint (with carrier).
5. Consumer boxes (IKEA 365+, Lock&Lock) - only for first prototypes.

**Ambient store mechanism.** Recommended: **aisle shuttle A (XZ carriage + telescopic fork)** with two 176 mm racks and a 192 mm aisle
(544 mm), ~168 boxes/m. Ranking:
1. A - aisle shuttle (Rowa principle). 3 actuators, 8-20 s, off-the-shelf parts.
2. D - vertical paternoster with exit puller. 2-3 actuators; simpler, but more space loss and hygiene issues.
3. B - top-access cube grid; best density, best cold retention (cold air stays, like a chest freezer), but long and irregular retrieval and custom parts.
4. C - VLM: principle only.
5. F - sliding puzzle: not recommended.

**Cold store.** Recommended: **off-the-shelf 178 cm integrated fridge and freezer (Liebherr class) with single-sided rack and carriage, door replaced by a two-stage
hatch/vestibule**, motors outside. Ranking:
1. Fridge shell + vestibule + rack (Liebherr IRBe 5121 999-1,299 EUR for the fridge; freezer 178 cm NoFrost, model to be verified).
2. Custom VIP-insulated cell with an own small compressor: ~2-4x capacity, larger development risk.
3. Fridge shell with the original door opened by the gantry (no hatch): simplest, higher air exchange.
4. Motorised drawer fridge: small daily-use fridge.
5. Peltier: no.

**Handoff/interface for the architecture (A1):** box standard = GN 176-family with flange on rails; rack pitch 25 mm
modules; aisle width 192 mm; exit hatch 350 x 200 mm for L boxes (206 x 150 for M); box weight limit 6 kg (L 150 mm full ~ 6 L x 0.6 = 3.6 kg + 0.3); box ID = 2D
code + NFC on box body; weighing at the exit station; lid station downstream of the exit.

## 8. Open issues

1. **Flange geometry** of chosen GN boxes (flange width, thickness, lid overlap, body-to-flange offset). Buy samples of Araven, Hendi and Cambro GN 1/6 (and 1/9, 1/3) and measure; decide rail profile from that.
2. **Interior dimensions** of the candidate integrated fridges/freezers (Liebherr IRBe/IRBd/IRDdi 5121, ICNb 5123 and NoFrost freezers on a 178 cm niche); no manufacturer publishes them. Requires a measured unit or Liebherr technical drawings (drawings exist in their downloads).
3. **178 cm NoFrost freezer** model identification (e.g. Liebherr IFNe 5x23/IFNd 5x53 class); verified data only for under-counter freezers.
4. **Lid removal force at -18 C** and lid seal behaviour with flat gasket lids; choose between vacuum cup and notch hook after a test.
5. **PC and bisphenols** regulation timing (EU 2024/3190) - verify before selecting Camwear polycarbonate.
6. **Hygiene of GN PP** (odour, staining) - Tritan or PPSU alternative; get supplier availability and prices for Tritan GN 1/9, 1/6, 1/3.
7. **Liquids** (oil, milk, stock, sauces): GN boxes are open-top and not spill-proof under fork acceleration; need lidded liquid boxes with a spout or a separate bottle module.
8. **Spice dosing:** 25+ spices in GN 1/9 boxes each need pouring; maybe better a separate dosing carousel (R4 topic).
9. **Depth budget:** two racks + aisle = 544 mm leaves ~56 mm for panel and skin; check with D9 (frame) whether the 600 mm cabinet depth includes front panels. If not, use 162 mm orientation for M boxes (Y = 162, X = 176) which gives 502 mm but loses GN 1/3.
10. **Exit handoff** to the transport system: where the hatch is (which face/height) is defined by A1; the cold hatch might be at a height different from the ambient exit.
11. **Ingestion** fills boxes through a funnel: interface between lid station and funnel (lid station shared?).
12. **Brooks/Hamilton/Rowa data** were not readable in the tool; need the actual manuals for cold-operation practice (dry-air purge, heaters).
13. **Prices** not found: Auer EG 3212, Cambro GN 1/6-100 in EUR, Gastronorm.it Tritan boxes, VIP panels, liter-class compressor units.

## 9. Risks

| Risk | Impact | Mitigation |
|---|---|---|
| Flange too thin/flexible or lids overlap the flange -> boxes can't hang on rails | box interface changes | test samples now; design carrier clips as plan B |
| Interior of the standard fridge too small for a rack + aisle | cold capacity drops to ~20 boxes | VIP custom cell (option B); measure before ordering |
| Frost/ice on rails, latch and sensors in the freezer | jams, service calls | dry-running plastics, wipers, vestibule, purge, periodic warm-up, easy-service access |
| Door modification voids fridge warranty and may impair seals | efficiency and safety | keep the original door as service door; design the hatch as a plug with a gasket; monitor power |
| Warm boxes or slow retrieval break the cold chain | food safety | HACCP logging; return rules; 2-hour rule; keep the vestibule cold |
| PP retains odours; PC banned | hygiene complaints/regulation | Tritan/PPSU option; wash after each empty |
| Aisle 544 mm depth leaves no reserve | interference with skin/insulation | check with A1/D9; alternative orientation |
| Low retrieval speed if several dishes need many boxes | cooking delay | carriage pre-fetches boxes in recipe order; 2 carriages per module optional |
| Belt/leadscrew failure in a 2 m tall Z axis (falling carriage) | damage, injury | brake, counterweight, non-back-driving screw, end stops |
| Weight sensing drift or wrong tare after box swapping | inventory errors | tare at each wash, box ID check |
| Data in this file partly unverified | wrong design values | verify list in section 8 before freezing interfaces |

## 10. Sources

Boxes and containers
* Gastronorm sizes and depths: https://www.gastronorm.it/en/The-Gastronorm-measures , https://en.wikipedia.org/wiki/Gastronorm_sizes , https://www.gastronorm.it/en/Gastronorm-GN-1-6-176x162-mm , https://www.gastronorm.it/en/polycarbonate.d129 (404 on fetch, found via search)
* Araven GN 1/2 h100 (09297): https://araven.com/en/gastronorm-food-pans-with-polypropylene-lid/gn-1-2-h-100mm-4-6-l-6-3qt-storage-container/
* Araven GN 1/6 100 mm price 7.10 net: https://www.horeca.com/en/product/89144/araven-plastic-gastronorm-container-1-6-gn-100-mm (via search)
* Hendi GN 1/6 PP (880401/880418/880425, lid 881828): https://www.hendi.eu/en/container-gn-16-polypropylene-4118.html
* Cambro GN polycarbonate 1/6 and lids: https://www.smartuk.net/plastic-gastronorm-containers/cambro-polycarbonate-1-6-gastronorm-pan-100mm-dm752/ , https://www.easyequipment.com/cambro-clear-polycarbonate-1-6-gastronorm-lid-dc666.html , https://www.lockhart.co.uk/Kitchen-Equipment/Food-Storage-and-Labelling/Gastronorm-Containers/Cambro-Gastronorm-Seal-Cover-Lid-1-6-White-Polycarbonate~p~EC923 , https://www.restaurantsupply.com/products/cambro-60cwgl135-6-3-8-inch-clear-food-pan-cover-with-griplid-polycarbonate
* Cambro PP GN 1/6-150 (4.15 EUR): https://www.restomaster.ee/en/a/container-gn-1-6-transparent-polypropylene.-cambro-2.2-l-h-150-mm-gn-1-6-2-2l-transparent-162x176x-h-150mm
* Cambro Camwear prices (Metro, GastroDAX): https://www.metro.de/marktplatz/product/dd4f13b0-7d05-4800-861c-5e33f471186e , https://www.gastrodax.de/gastrobedarf/gn-behaelter/gn-1-6
* Cambro CamSquares: https://www.webstaurantstore.com/cambro-4sfspp190-camsquare-4-qt-translucent-food-storage-container-with-kelly-green-graduations/2144SFSPP.html , https://www.katom.com/144-SFC2452.html
* IKEA 365+: https://www.ikea.com/gb/en/p/ikea-365-food-container-with-lid-rectangular-plastic-s99269080/ (search snippet; page not fetchable), https://www.ikea.com/us/en/p/ikea-365-food-container-with-lid-rectangular-plastic-s39567068/
* Lock&Lock: https://www.amazon.de/LOCK-Dose-Liter-luft-fl%C3%BCssigkeitsdicht/dp/B009WR9FNA , https://www.amazon.de/Lock-HPL817-Frischhaltebox-rechteckig-St%C3%BCck/dp/B00IQX8WYY
* Rotho Domino: https://www.hofmeister.de/product/rotho-gefrierdose-domino/130399-04/ , https://ch.rotho.com/products/4er-set-gefrierdosen-0-75-l-domino
* Euro containers: https://www.ackrutat-shop.de/kisten-boxen/regalkaesten-einsatzkaesten/14816/105x-auer-eg-3212-regalkaesten-300x200x120-mm-eurobehaelter-stapelkisten-grau , https://www.dieboxfabrik.de/stapelbehaelter/eurobehaelter/300-x-200-mm/ , https://www.auer-packaging.com/de/Eurobeh%C3%A4lter-mit-Scharnierdeckel-Pro/EDP-3212-HG.html

Mechanisms
* BD Rowa Vmax: https://rowa.de/en/products/store-pick/bd-rowa-vmax/ , https://www.design-engineering.com/features/bd-rowa-igus-1004028869/ , https://www.igus.co.uk/industry/vending-machines/applications/energy-chains-for-pharmacy-order-picking-systems
* Kardex Shuttle: https://www.kardex.com/en-gb/products/vertical-lift/kardex-shuttle
* AutoStore: https://www.autostoresystem.com/faq/bins , https://www.kardex.com/en-us/blog/how-autostore-works , https://www.autostoresystem.com/system/flexbins
* Hamilton: https://www.hamiltoncompany.com/ambient-plus-4-minus-20-sample-storage/verso-q-series , https://www.hamiltoncompany.com/minus-80-sample-storage/bios (pages returned 403; data from search summaries)
* Brooks: https://cdn.ymaws.com/www.isber.org/resource/resmgr/virtual_exhibit_hall/brooks_life_sciences/company_document_2_automated.pdf (PDF unreadable; data from search summary)

Cold storage
* Liebherr IFNd 3924: https://www.liebherr.com/de-de/p/ifnd-3924-2451489
* Liebherr IRBd 5121: https://www.liebherr.com/de-de/p/irbd-5121-2451438
* Liebherr IFNbi 3553: https://www.liebherr.com/en-gb/p/ifnbi-3553-3011735 , https://www.liebherr.com/de-de/p/ifnbi-3553-2451489 (94 kWh/year via search snippet)
* Liebherr ICNb 5123, ICc 5123, ICBNci 5153: https://www.liebherr.com/de-de/p/icnb-5123-2451430 , https://www.liebherr.com/de-de/p/icc-5123-2451430 , https://www.liebherr.com/de-de/p/icbnci-5153-2451430
* IRBe 5121 price: https://www.otto.de/p/liebherr-einbaukuehlschrank-irbe-5121_991626751-177-cm-hoch-55-9-cm-breit-4-jahre-garantie-inklusive-1377686574/ , https://www.euronics.de/haus-und-haushalt/kuehlen-und-gefrieren/kuehlschraenke/einbaukuehlschraenke/irbe-5121-20-einbau-kuehlschrank-mit-gefrierfach-weiss-e-4065327036206
* Drawer fridges: https://www.test.de/Liebherr-UIK-1550-Ein-Kuehlschrank-mit-Schubladen-5270696-0/ , https://www.miele.de/de/m/miele-unterbau-kuehlschrank-mit-doppelschublade-7900.htm , https://fisherpaykelkuehlschrank.de/shop/norcool-kuehl-schublade-unterbau-nisch-82-cm-tuer-auf-tuer/
* Monoblock cooling units: https://www.kaeltetechnikshop.com/kaelte/kuehlraum/steckerfertige-kuehlaggregate/ , https://www.gastro-hero.de/K%C3%BChltechnik/K%C3%BChlzellen-und-Aggregate
* Peltier vs vapour compression: https://www.sciencedirect.com/science/article/abs/pii/S0306261911005538 , https://www.nature.com/articles/s41598-024-72500-1
* Lubricants: https://www.klueber.com/ecoma/files/Klueber_Food_Recipe_for_Success_EN.pdf , https://www.dupont.com/products/molykote-33-medium-extreme-low-temperature-grease.html , https://www.itwprobrands.com/product/lps-detex-food-grade-low-temp-grease
* Cold-storage robotics: https://www.roboticstomorrow.com/article/2026/09/cold-chain-robotics/27036 , https://reemanbot.com/posts/cold-storage-warehouse-automation-robots-that-work-in-extreme-conditions

Food safety
* Ethylene: https://en.wikipedia.org/wiki/Ethylene_(plant_hormone)
* BfR/consumer advice pages were not retrievable (404/no storage content); food-group table is standard practice from general knowledge, **[unverified]**.
