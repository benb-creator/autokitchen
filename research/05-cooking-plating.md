# R5 — Cooking, baking, portioning, plating, hatch and dishwashing technology

Author: research agent R5. Inputs: `BRIEF.md`, `PLAN.md`. Consumers of this document: D5 (cooking and
baking), D6 (portioning, serving, dishes), D7 (cleaning), D9 (utilities and safety), D10 (control).

## 0. How to read this document (provenance tags)

The web-search quota ran out part-way through this research, and many vendor pages block automated
fetching (HTTP 403/404/429) or return only marketing text. Each number therefore carries a tag:

* **[W]** seen in a fetched page or search result in this session; URL in section 12.
* **[E]** my own engineering calculation or design estimate (assumptions are shown).
* **[BK]** background knowledge, *not* re-verified in this session. Treat as a lead to verify, not a fact.

Prices are EUR unless another currency is shown. USD prices are converted only loosely; a USD figure is
marked as such. Where a vendor only shows USD, the EU price is normally 10–30 % higher after VAT [BK].

## 1. Executive summary

1. **Ovens are controllable, hobs are not.** Consumer combi/steam ovens can be driven through cloud
   APIs (Home Connect, Miele 3rd-party API): select heating mode, set temperature and duration, start,
   stop, read cavity and core temperature [W]. Consumer *hobs* are monitor-only on Miele [W], and Home
   Connect hobs have no remote-start program to my knowledge [BK]. A hob for an automatic machine
   therefore has to be an **OEM induction module** (or a commercial hob with a knob/analog interface)
   that we control ourselves.
2. **Ovens need a physical "remote start" handshake.** Home Connect ovens require the user to press a
   Remote Start button on the appliance every time (or within a 15 min window with the door closed);
   a "Permanent Remote Start" option exists on some models, e.g. Thermador ovens/ranges and dishwashers
   [W]. Miele likewise needs MobileStart/remote enable [W]. So the API path works only with models that
   support permanent remote start, or with a mechanical or electrical retrofit that presses the button.
   This is the single biggest integration risk for the oven.
3. **Power is the binding constraint.** A 230 V / 16 A circuit gives 3.68 kW; a hob (3.6 kW), a combi
   oven (about 3–3.7 kW [BK]) and a dishwasher (about 2 kW) cannot run together. The brief lists only
   "220 V". Design for **one 16 A single-phase supply with a software load manager**, and offer an
   optional three-phase Herdanschluss (400 V, 3 x 16 A, up to about 11 kW) variant.
   Commercial combi ovens and undercounter warewashers usually need 400 V three-phase (Rational XS
   about 5.7 kW [BK]; Meiko UM 4.7 kW, 25 A fuse [W]) and do not fit a single-phase design.
4. **Avoid flipping and avoid deep frying.** Use the oven (convection, grill, air-fry, steam) for
   roasts, gratins, meatballs, sausages, fish, potatoes and baking. Use a **contact grill / clamshell**
   for patties, steaks and sandwiches (no flip). Pan-searing with a spatula arm is the fallback. A
   deep fryer costs too much (oil ageing, filtration, fire risk, odour) for the roughly 3 % of meals it
   enables. Recommend **no deep fryer in v1**.
5. **Stirring: overhead scraper head on a fixed induction pot** (plus optionally a Thermomix-type
   bottom-driven bowl for soups and purées). Consumer stirred-cooking appliances (Thermomix TM6,
   Bosch Cookit, Kenwood Cooking Chef XL) prove the concept and are dishwasher-safe [W] but have no
   open API.
6. **Cookware:** 18/10 stainless steel with a ferritic (magnetic) base, enamelled steel where needed.
   No carbon steel, cast iron or PTFE in a machine-washed, robot-handled cell. Two vessel families:
   round pot (about 240 mm, 4–6 L, two ear handles) and a sauté pan; GN 1/2 and 2/3 pans for the oven.
7. **Fumes, steam and fire have no duct.** The brief provides water, drain, power and Internet only, so
   the cell must be **recirculating**: grease filter + activated carbon + a condensing/dehumidifying
   stage. Fire safety must be a layered, hardware-based chain (thermal limiter, independent power
   cut-off, thermal camera or heat detector, sealed cell, wet-chemical or clean-agent suppression).
8. **Plating:** gravimetric closed loop (load cell under the plate) with per-component dispensers,
   ring mould for mounds, peristaltic pump with a 1–2 mm nozzle for sauce, vibratory or auger garnish
   dosing, warm plates from a warming drawer. Recommend **one plate type and one bowl type**, stored
   in a spring or motor "lowerator" so the top plate is always at the pick height.
9. **Serving hatch:** a **rotating two-shelf pass-through (lazy-susan)** gives a permanent physical
   barrier between the user and the robot; a motorised lift door needs force limiting per EN 12453
   [BK] plus a light curtain or safety edge.
10. **Dishwashing:** two separate washing functions. (a) A standard household dishwasher for
    human dishes (Bosch 45 cm from EUR 599, 8.9 L, 3 h 15 [W]) or, better, a commercial undercounter
    machine with a 2-minute cycle (Winterhalter UC-M: 500 x 500 rack, 2.4 L rinse water per cycle [W]).
    (b) Pot/tool/box cleaning either in the same commercial washer with special baskets, or in-place
    with a spray head in the lid. Cold-water-only supply means the internal boiler heating limits the
    cycle time (calculation in 9.2).

## 2. Power budget and electrical concept

### 2.1 What the household supplies

| Supply | Power at 230/400 V | Note |
|---|---|---|
| 1 x 230 V, 16 A | 3.68 kW peak, about 2.9 kW continuous (80 % rule) [E] | Brief says "220 V"; assume this |
| 1 x 230 V, 32 A | 7.36 kW | Rare in German flats, but common as a hob feed in some countries [BK] |
| German Herdanschluss 3 x 400 V, 16 A per phase | up to 11 kW (3 x 3.68 kW) [W, elektroda / BK] | Usually already in the kitchen; 5 x 2.5 mm2 cable |

The brief lists only 220 V. **Decision required from A1/Q1:** design for single-phase 16 A as a
minimum, and specify the three-phase connection as optional. Bosch sells 3.7 kW hobs for single-phase
installations with power management that limits to 10/13/16 A [W: elektroda forum summary]; this
confirms that a 16 A single-phase hob is normal practice.

Do not feed the machine through a Schuko plug at full load. Schuko sockets overheat at sustained
16 A [BK]; use a hard-wired terminal box like a Herdanschluss.

### 2.2 Loads (nameplate, indicative)

| Device | Peak power | Duty | Source |
|---|---|---|---|
| Induction, one large zone | 2.0–3.6 kW at the mains; 74–77 % reaches the pot [W: Wikipedia] | minutes to hours | [W][E] |
| Household combi-steam oven 60 cm | about 3.0–3.7 kW | heating phase; average 1.0–1.5 kW | [BK] |
| Compact commercial combi (Rational iCombi Pro XS 6-2/3) | about 5.7 kW, 400 V 3N [BK] | | [BK] |
| Household dishwasher 45/60 cm | about 1.8–2.4 kW heater phases | 1–3 h | [BK] |
| Commercial undercounter washer | Meiko UM: 4 kW boiler + 2 kW tank heater, total 4.7 kW, 25 A fuse [W] | 2–4 min cycles | [W] |
| Hot-water boiler for pasta water | 2–3 kW | short | [BK] |
| Warming drawer | 0.4–0.8 kW | continuous while serving | [BK] |
| Extraction fan, controls, robots, sensors | 0.3–0.8 kW | continuous | [E] |
| Fridge + freezer sections | 0.1–0.2 kW average | continuous | [E] |

Rule: a **load manager** (in D10) allows at most about 3.3 kW simultaneous draw on a single-phase
supply. Priority order (highest first): safety functions and fans, cold storage, induction, oven,
plate warming, dishwasher. Pre-heating the oven and heating the dishwasher rinse water are the
loads that can be deferred and scheduled around the hob. Recipes must be scheduled with
power in mind (D10): e.g. oven at full power while the induction runs at 1 kW.

### 2.3 Heat and moisture into a closed cabinet

* Waste heat about 1 kW to be removed continuously during cooking (oven shell, hob and pot radiation)
  [E]. With a 20 K allowable air temperature rise, that needs 1000 W / (1.2 kg/m3 x 1005 J/kgK x 20 K)
  = 0.041 m3/s, about **150 m3/h** of through-flow [E].
* Steam: a 6-portion meal may evaporate 0.5–2 kg of water [E]. Condensing 1 kg needs 2.26 MJ. A
  mains-water condenser at +20 K temperature rise would need about 27 L of cooling water per kg of
  steam [E]. That is too much. A compact refrigerant dehumidifier stage in the extraction loop
  (about 0.2 kWh/kg at COP 3) is the sensible way [E].

## 3. Hobs and induction

### 3.1 Options

| Option | Power / size | Control interface | Verdict |
|---|---|---|---|
| Built-in hob (Bosch/Siemens/Miele/Neff) | 4 zones, 7.4 kW total (3-phase) or 3.7 kW (1-phase) [BK] | Touch panel; Home Connect/Miele@home only *monitor* the hob; Miele integration: "heating plate status monitored, not controlled" [W] | Not controllable; would need panel hacking |
| Domino / flex 30 cm hob | 2 zones, up to 3.7 kW [BK] | as above | Same |
| Portable commercial single hob, e.g. 3.5 kW, 195–275 V, coil about 235 mm (9.25 in) | 0.4–3.5 kW [W: Abangdun listing] | Push-buttons or rotary knob; a knob is easiest to replace with a servo or digital potentiometer [BK] | Cheap, quick prototype; not for the final machine |
| OEM induction module (PCB + coil + NTC) | 2–3.5 kW, RS485/UART control offered by Chinese OEMs [W: Alibaba "3.5 KW Induction cooker SKD" listing] | UART/RS485 or PWM/analog power setpoint; the exact protocol depends on the vendor and must be requested in writing [BK] | **Recommended for the final machine** |
| All-in-one stirred cookers with built-in induction (Thermomix, Cookit, Cooking Chef) | 1.5–1.75 kW | Proprietary app/recipe ecosystem; no public API [BK] | Off-the-shelf pilot only |
| Robot-oriented commercial units (Posha/Nymble) | induction + stirrer arm, "microwave size", USD 1,500–1,750 [W] | Closed | Reference design, not a component |

### 3.2 Coil size, zones and pan detection

* Typical coil diameters 145 / 180 / 210 / 280 mm at 1.4 / 1.8–2.3 / 2.3–3.7 kW / 3.7 kW [BK]. The
  power density limit is about 20–25 W/cm2 of coil area [E].
* Operating frequency about 25–50 kHz for normal hobs; all-metal units go up to 120 kHz [W: Wikipedia].
* **Pan detection** is done by monitoring the power delivered (coil impedance and resonance): if there
  is no pan or the pan is too small, the hob shuts off [W: Wikipedia]. Minimum pan base diameter is
  typically 100–120 mm [BK]. This is a free safety feature for a robot: when the gripper lifts the
  pot, the heating stops within a fraction of a second.
* Only ferromagnetic base materials work (cast iron, carbon steel, magnetic stainless 430; not copper
  or aluminium) [W: Wikipedia]. 18/10 stainless is at best weakly magnetic, so pots need a ferritic
  base plate.
* Base flatness: concavity of less than about 0.05 % of the diameter when cold [BK].

### 3.3 Temperature sensing and closed-loop control

| Method | What it measures | Price / data | Pros / cons |
|---|---|---|---|
| NTC/PT1000 under the ceramic glass (spring-loaded) | Pan base via the glass | about EUR 1–5 [E] | Standard in hobs; lag 5–20 s [BK]; needs good contact |
| IR sensor MLX90614 | Surface temperature of pot side/base | USD 15.95; -70 to +380 C, +/-0.5 C at room temperature, 90 degree field of view, I2C [W] | Cheap, contactless. Bare stainless has emissivity of 0.1–0.3 and reads far too low; paint or oxidise a black band on the pot, or measure the food surface [BK] |
| Thermal camera MLX90640 (24 x 32 pixels) | Image of pot, food and cabinet | USD 74.95; -40 to +300 C, +/-2 C, 16 Hz, 55 degree or 110 degree field [W] | Good for fire watch, boil-over and burn patterns, pot position; low resolution; lens/steam fouling |
| Probe in the food (PT1000 in a thermowell in the stirrer shaft) | Real product temperature | EUR 10–30 [E] | Best for closed-loop soup/sauce/custard control; must be washable and sealed |
| Core probe (wired) in meat | Core temperature | Built into ovens (Miele, Bosch, Rational) [W: HA Miele doc lists core-temperature sensor] | The probe must be inserted by the robot; automatic insertion is hard [E] |
| Vision + weight + thickness model | Doneness estimate | | No contact; needs calibration per food |

Recommended control scheme (D5/D10):

1. Power setpoint from the controller to the induction module (0–100 %, updated at 1–10 Hz).
2. Cascade PID: outer loop on food or pot temperature (thermowell PT1000), inner loop on
   pan-base NTC limit (safety cap, for example 260 C for frying, 130 C for sauces) [E].
3. Boil detection: temperature plateau at about 100 C (minus altitude correction) drops power to a
   simmer level [E].
4. **Boil-over:** a rim capacitance or conductive foam electrode, or a ToF/ultrasonic level sensor,
   plus fill limit of 60 % of the pot volume, plus stirring [BK][E]. On detection, cut power and
   raise the stirrer speed.
5. **Burn detection:** rising stirrer motor current (torque), pan-base temperature slope
   (for example > 3 K/s with constant power) and the base temperature exceeding the recipe limit; a
   gas/VOC sensor as a confirmation [E].

### 3.4 Control routes for a hob (ranked)

1. **OEM module with UART/RS485 or analog input** (own certification, see section 8): best control
   quality and lowest cost (Chinese 3.5 kW boards about EUR 25–60 [BK]). Get the protocol document
   and sample before committing.
2. **Commercial hob with knob** and a servo or digital potentiometer: quick to build, but
   the knob position is not a repeatable power setpoint, and modifying a certified appliance voids
   its approval [BK].
3. **Panel hacking (serial UI emulation or MOSFET/relay across touch pads):** model specific,
   fragile, not recommended except as a pilot [BK].
4. **Stylus robot pressing the touch panel:** universal but slow and unreliable; last resort [E].

## 4. Cookware for automation

### 4.1 Materials in a machine-washed, robot-handled context

| Material | Induction | Dishwasher | Robot/scraper | Verdict |
|---|---|---|---|---|
| 18/10 stainless steel, 3-ply with ferritic base | Yes with 430 base | Excellent | Tolerates metal tools | **Use** |
| Enamelled steel | Yes | Good; chips at edges | Tolerates | Use for oven roasting and braising |
| Carbon steel | Yes | Rusts, seasoning removed by alkaline detergent | | Avoid |
| Cast iron | Yes | Rusts; heavy (5–8 kg) | | Avoid |
| PTFE non-stick | Yes if base is ferritic | Detergent and abrasion shorten life to about 1–2 years [BK]; PFAS restrictions in EU/France [BK] | Metal scraper destroys coating | Avoid in v1 |
| Ceramic (sol-gel) coating | Yes | Wears fast in dishwashers [BK] | | Avoid |
| Aluminium | No | Darkens in alkaline detergent | | Avoid (except as sandwiched core) |

Food sticking on bare stainless is handled by pre-heating to the correct temperature (checked by
the pan-base sensor), adequate fat, and a silicone or metal scraper; if that proves insufficient the
grill/oven route replaces pan-frying.

### 4.2 Shapes and handles for gripping

* **Round pot, about 240 mm diameter, 130–150 mm high, 4–6 L**, two welded ear handles (or loop handles)
  at rim height on opposite sides, plus a flat 8–10 mm flange for finger grippers [E]. Empty mass
  about 1.2–1.5 kg; filled about 6–7 kg [E]. A robot that must lift and pour this needs about 8 kg
  payload at 300 mm reach (wrist torque about 25 Nm) [E]. That is UR10e class (payload 12.5 kg, USD
  tens of thousands [BK]) and too expensive. Preferred alternative: **keep the pot fixed on the hob**, and
  move food in and out with chutes, a bottom drain valve plus pump for liquids, ladles/scoops, or
  a tilting cradle like a Bratt pan (Rational VarioCooking Center tilts the pan with an electric
  cylinder [W]).
* **Sauté pan 280 mm, 60 mm high**, low sloped sides so a spatula tool can reach the whole floor.
* **Lids**: flat lid with a steam vent and bayonet or magnetic catch. Lids may carry the stirrer
  passage or spray head (section 9.4).
* Pasta and blanching: perforated insert basket with a bail handle that the robot lifts and drains
  over the pot (as in Thermomix simmering basket / pasta pots) [BK].

### 4.3 GN containers (Gastronorm)

* GN sizes: 1/1 = 530 x 325 mm, 2/3 = 354 x 325, 1/2 = 325 x 265, 1/3 = 325 x 176 [BK].
  Rational's compact iCombi Pro XS holds 6 x 2/3 GN [W: horeca.com listing].
* A household oven cavity is usually about 460–480 mm wide inside [BK], so **GN 1/1 does not fit**;
  GN 2/3 and 1/2 do. This must be checked against the chosen oven's manual.
* GN pans are 304 stainless and normally not induction-capable; induction-ready GN versions with a
  magnetic base exist but are special and expensive [BK]. Use GN pans in ovens and bain-marie, but
  round induction pots on the hob.
* Standardising the oven vessel on GN 1/2 (perforated for steaming, solid for roasting/braising) makes
  robot handling uniform (rim flange all round, two lift handles).

## 5. Automatic stirring, scraping and flipping

### 5.1 Stirring mechanisms compared

| Mechanism | Example | Data | Fit |
|---|---|---|---|
| Rim-clip battery stirrer | StirChef, Ezstir | For 6–8.5 inch saucepans, battery, 3 paddles, intermittent setting [W] | Toy grade, low torque; not for a machine |
| Overhead lab stirrer | IKA type (BK) | 30–2000 rpm, 60–200 Ncm, EUR 1,000–3,000 [BK] | Torque adequate; not food-grade, not washable |
| Bottom-driven blade in a sealed bowl | Thermomix TM6 | 2.2 L bowl, 37–160 C, 500 W motor, 100–10,700 rpm, gentle stir 40 rpm, reversible, bowl/lid dishwasher-safe [W] | Best all-round for soup/purée/risotto/sauces; the seal and blade base need a wash cycle |
| Planetary stirrer + induction bowl | Kenwood Cooking Chef XL KCL95 | 6.7 L, 1500 W induction, 20–180 C; EUR 1,149–1,600 [W] | Largest consumer bowl; scrapes the wall; open or partly open lid |
| Stirred cooker with dishwasher-safe pot/lid/tools | Bosch Cookit MCC9555DWC | 3 L, 1750 W, up to 200 C; EUR 1,349–1,399 [W] | Good pilot; small |
| Robot stirring arm above induction | Posha/Nymble | 4 hoppers, spice carousel, camera, USD 1,500–1,750; limited ingredient capacity [W] | Shows the consumer price floor |
| Tilting Bratt pan / VarioCooking Center | Rational VCC 112 | 1200 x 777 x 1100 mm, tilting pan by electric cylinder [W]; price above EUR 20,000 [BK] | Too large, too costly |
| Kettle mixer with planetary scraper | Commercial jam/soup cookers | 5–100 L, EUR 2,000–10,000 [BK] | Too large for 1–6 portions |
| Rotating tilted drum wok | Spyce (MIT) [W: Sweetgreen article mentions the Spyce acquisition and closure of both Spyce locations], Chinese drum stir-fryers [BK] | Water washes the drum between batches [BK] | Good stir-fry, poor for sauces; complex |
| Magnetic stirrer | Lab units | | **Not viable**: coupling through an induction pot base is shielded and the bar would heat; too weak for thick food [E] |

**Recommendation:** an **overhead anchor/scraper stirrer** on the robot's tool interface, docking
onto the fixed pot lid or rim (D4/D5). The paddle is silicone or stainless with a spring-loaded
scraping blade that follows the pot wall and base. Design estimate for torque: 3–5 Nm at 20–120
rpm for thick purées (100–500 Pa yield stress) [E]; a 24 V BLDC motor with a planetary gear and
torque limiting is adequate. Add a second, small bottom-driven bowl (Thermomix-type) only if a
sealed pot-with-knife is wanted for soup, purée and dough tasks (overlaps with R4 mixing).

### 5.2 Scraping the bottom to prevent burning

* Anchor paddle at 20–60 rpm for sauces, with a fixed blade 1–2 mm off the base.
* Torque sensing gives a burn warning (section 3.3).
* Power is reduced automatically when the temperature slope or torque rises.
* Intermittent stirring (as StirChef offers [W]) is enough for boiling water and pasta.

### 5.3 Avoiding flips

| Food | Traditional method | Machine-friendly method |
|---|---|---|
| Steak | Pan sear, flip | Clamshell/contact grill (double-sided); or low-temp oven + short contact-grill finish; or pan sear with spatula flip |
| Frikadellen / patties | Pan fry, flip | Contact grill (patties are 20–25 mm; platen gap set to thickness); or convection oven 200 C, 12–15 min [E] |
| Pancake / crepe | Pan, flip or toss | Hot plate with a thin spatula flip; or bake as an oven pancake; low priority |
| Fish fillet | Pan, flip (skin sticks) | Combi oven steam or convection with parchment or oiled GN; no flip |
| Sausages, chicken pieces | Pan | Oven convection or grill; turn once by the rack tray only if needed |
| Roasts, Rouladen | Sear, braise | Sear in pan (rotate with tongs), braise closed in a GN pan in the oven |
| Potatoes, vegetables | Pan or oven | Oven convection or steam |
| Schnitzel | Deep or shallow fry | Shallow-fry with 5 mm oil and a flip, or oven-fry with sprayed oil |

* **Spatula mechanism:** thin stainless blade (0.5–1 mm) driven at a shallow angle; needs vision
  to find the food edge (Miso Robotics Flippy does this with cameras and a robot arm [W]). Limit to
  a fallback.
* **Clamshell/contact grill:** two heated platens, the lid coming down to the set thickness. Consumer
  units such as Tefal OptiGrill sense thickness and doneness and have removable dishwasher-safe
  plates [BK]. Plates need a release layer: PTFE-coated glass-fabric sheets or silicone mats that
  the robot swaps into the washer [BK]. Commercial clamshell grills are used for burger patties in
  chains [BK].
* **Basket flipping:** two shallow perforated baskets clamp the food and rotate through 180 degrees
  (fish grill baskets) [BK]. Good for fish and vegetables; adds a washable part.

## 6. Ovens and baking

### 6.1 Candidates

| Oven | Type | Data | API / control | Cleaning |
|---|---|---|---|---|
| Miele DGC 7440 AM, 60 cm compact combi-steam XL | Household, plumbed variants exist (DGC 6805 XL plumbed) [W] | USD 4,499 (DGC 7440 AM) up to 6,799 (DGC 7840 AM with roast probe) [W] | Miele 3rd-party API: monitor, set programs; "some programs, options, settings in the app may not be accessible via the API"; most appliances need MobileStart/remote enable [W]; LAN integration exists (unofficial) [W] | Descaling + cleaning programme [BK]; no pyrolysis in true-steam models [BK] |
| Bosch Serie 8 steam ovens HSG7584B1 / HSG7364B1 | Household combi-steam | from EUR 2,299 [W] | Home Connect cloud API [W] | Steam cleaning/descaling [BK] |
| Bosch Serie 8 HRG7764B1 | Household oven with steam assist, pyrolysis, Air Fry | from about EUR 989 [W]; 71 L; digital dial; manual steam burst [W] | Home Connect [W] | **Pyrolysis** up to about 480 C [W]: ash to wipe out (by hand, unless a robot does it) |
| Siemens, Neff, AEG equivalents | same platform as Bosch (Home Connect) or own | EUR 1,000–3,500 [BK] | Home Connect (Siemens, Neff); AEG/Electrolux own app [BK] | pyrolytic or hydrolytic |
| Anova Precision Oven 2.0 | Countertop combi, 12 modes incl. steam, sous-vide, broil, dehydrate | USD 999 sale / 1,299 regular [W] | App only; US 120 V product; no public API found [W] | Manual; water reservoir |
| Rational iCombi Pro XS 6-2/3 E | Commercial compact combi | EUR 6,950–9,140 [W]; 30–300 C [W]; iCareSystem with 9 cleaning programmes, overnight unattended cleaning; a short programme takes about 12 min [W] | ConnectedCooking (cloud) [BK]; 400 V 3-phase [BK]; water and drain connection [BK] | Automatic with Care tabs |
| Unox CHEFTOP MIND.Maps Compact Plus | Commercial combi | XACC-0513, 5 x GN 1/1, USD 12,800 excluding tax, 21.6 kWh/day [W]; ROTOR.Klean automatic washing with SENSE.Klean [W] | Unox cloud [BK] | Automatic |

### 6.2 Cleaning approaches

* **Pyrolytic**: 470–500 C for 1.5–3 h, about 4–6 kWh [BK]; needs removing GN pans and non-pyrolytic
  racks; fumes need venting (an issue in a duct-less cabinet); door locks. Available on steam-assist
  ovens (Bosch HRG type [W]) but not on true combi-steam models [BK].
* **Hydrolytic/steam cleaning**: 30–60 min at about 80 C with 0.3–0.5 L water; weaker on baked-on
  fat [BK]. Adequate if grease is contained by covered GN vessels.
* **Automatic detergent (Rational, Unox)**: rotor/spray system with Care tabs or liquid; cleans
  the cavity including steam generator; needs drain and water connection [W]. Best result but 400 V
  and about 4x the price of household ovens.

### 6.3 Controllability

* Home Connect cloud API: select and start heating modes, set setpoint temperature and duration, stop,
  pause and resume, read cavity temperature; the API "does not fully match" the app [W: HA Home
  Connect integration]. Documentation lists Setpoint Temperature, Duration, Fast Pre-heat, Level options
  [W: api-docs.home-connect.com].
* **Remote start rules** [W]: RemoteControl and RemoteStart flags must be true, LocalControl must be
  false, OperationState Ready. On ovens the user must press Remote Start on the appliance each
  time; the "yellow" level lets it stay active for 15 minutes after the door was last closed; the
  "orange" level deactivates it whenever the door opens. "Permanent Remote Start" can be activated on
  some ovens/ranges and dishwashers (dishwasher: confirm the blinking button once within 10 min) [W].
  Which EU models offer it must be checked per model.
* **Mitigations:** (a) choose a model with permanent remote start; (b) retrofit a relay/solenoid
  that presses the Remote Start key when the robot has closed the door (the robot closing the door
  meets the safety intent of the rule); (c) build the oven from an OEM cavity with our own controller
  (loses certification, hard); (d) use a commercial oven with an industrial API (Rational/Unox)
  and accept three-phase.
* **Door:** household oven doors swing down 90 degrees into the robot space and need a hand to open
  them. Options: robot pulls the handle; a linear actuator or motorised door retrofit; a retracting
  door such as Neff Slide&Hide [BK, verify]. The steam oven door gasket and hinges must not be
  damaged by retrofits. D5 to decide.
* **Core probe:** Miele/Bosch probes report core temperature to the API [W: HA Miele]; the probe has
  to be placed in the meat by the robot or replaced by a time/thickness model (section 3.3).

### 6.4 What replaces what

| Hob operation | Oven replacement | Quality difference |
|---|---|---|
| Boil potatoes, vegetables | 100 % steam in perforated GN, 10–25 min | Better nutrient retention; no water to drain |
| Cook rice | Solid GN, water 1:1.5, steam 100 C, about 25–30 min [BK] | Equivalent |
| Pan-fry chicken pieces, sausages, meatballs | Convection 200–220 C or Air Fry mode, 12–25 min | Slightly less crust on the underside |
| Sear steak | Low-temp roast + top-heat/grill finish (reverse sear) | Less crust than pan; acceptable with a contact-grill finish |
| Braise (Rouladen, goulash, roast beef) | Covered GN, 140–160 C, 1.5–3 h, steam-assisted | Equivalent; lower attention needed |
| Gratin, casseroles, lasagne | Top heat/grill | Native oven task |
| Fish | Steam 80–90 C or convection with steam | Better than pan |
| Baking bread, cake, pizza | Native (combi steam adds crust) | Native |
| Soups, sauces, custards | not possible without stirring | Need stirred pot |
| Pasta | Possible in steam only with special sequences [BK] | Better in boiling water |
| Frying in oil, deep frying | Air-fry mode | Different texture |

Conclusion: **the oven plus the stirred pot covers most meals**; the hob's job reduces to boiling
(pasta, dumplings), sauces, soups and searing.

## 7. Other cooking devices: value against complexity

| Device | Value | Complexity / cleaning | Recommendation |
|---|---|---|---|
| Pressure cooker | Stews and beans 3x faster | Locking lid, valve, sealing ring to wash; robot lid handling; safety | Not in v1; use oven braising with planned start time |
| Sous-vide | Perfect steak/egg | Needs vacuum bags and a sealer (consumables) | Not in v1; use combi low-temp mode with core probe, no bags |
| **Deep fryer** | Schnitzel, chips, tempura | Oil ageing; total-polar-compounds limit about 24–27 % [BK], sensor (about EUR 800 [BK]); filter/pump; waste oil storage; oil fire (autoignition about 330–370 C [BK]); odour | **No** in v1. Miso's Flippy is a robot fry station with oil basket handling and hot-hold, 100+ baskets/h, renting at USD 5,400/month [W]; illustrates cost at commercial scale |
| Rice cooker | Rice | Extra device and pot | Skip; steam oven or stirred pot |
| **Kettle / instant hot water** | Fills pasta pot with boiling water; 3 L from 12 to 100 C is 0.31 kWh [E], about 6 min on a 3.6 kW hob | Boiler with solenoid, cold-water fed | **Yes**: 5 L pressurised boiler 2–3 kW with valve, EUR 300–600 [BK]. Quooker taps cost EUR 1,220–1,570, use 10 W standby, are cold-water fed [W] but have no external control interface [BK] |
| Steam generator | | Scale | Use the combi's steam |
| Microwave | Defrost, reheat | Simple cavity; metal GN pans not allowed | Optional: defrost and reheat |
| Toaster | Bread | Crumbs | Skip; oven grill does toast |
| **Contact grill** | Patties, steaks, sandwiches without flipping | Removable plates or sheets | **Yes** |
| Air fryer | Crispy | Basket | Combi Air Fry replaces it [W: HRG7764B1 has Air Fry] |
| Salamander/top heat | Gratin | Grease | Oven top heat/grill |
| Thermomix-type bowl | Soup, sauce, purée, dough | Blade seal | Optional second stirred vessel |

## 8. Fume, steam, and fire safety in a closed cabinet

### 8.1 Extraction without a duct

* The brief has no exhaust duct. Options: recirculating hood with grease filter (dishwasher-safe
  metal mesh) + activated carbon (saturates in 3–6 months in homes; regenerable filters can be
  baked at about 200 C [BK]) + optionally plasma/ionisation or UV (ozone by-product; not
  preferred [BK]).
* A downdraft extractor built into the hob centre (Bora type) draws fumes directly and can be run
  in recirculating mode; it costs EUR 2,500–4,000 [BK] and is too large.
* **Recommended:** a closed cooking chamber with a slotted extraction plenum behind the hob, 100–150
  m3/h during cooking [E], through grease filter, carbon, and a compact dehumidifier stage (2.3).
  Face velocity 0.25 m/s over the open hob area of about 0.4 m2 would need about 360 m3/h; a closed
  chamber (door shut while cooking) reduces that to 100–150 m3/h [E].
* **Condensate:** stainless walls slope to a drain; a drip tray under the oven vent; dehumidifier
  condensate goes to the waste pipe. Avoid horizontal ledges. Spray nozzles wash the chamber
  (R6/D7).
* **Grease:** filter pack is the main sink for grease; chamber walls need a periodic hot-water and
  detergent wash cycle. Grease filters and carbon cartridges are wear parts: schedule replacement and
  log it (D9).

### 8.2 Fire hazard and protection

Cooking is the leading cause of home fires [BK: NFPA statistics]. An unattended machine multiplies
the risk, so the machine must **not rely on software alone**.

Layers:

1. **Prevention.** Hardware thermal limiter on each heat source (hob pan-base NTC limit 260 C, a
   thermal fuse independent of the controller [E]); limit oil quantity (dose, not free-pour); no
   deep frying; oven thermal cut-outs.
2. **Detection.** Thermal camera MLX90640 watching the pot and cabinet (USD 75 [W]) for hot spots
   over the limit; photoelectric smoke and rate-of-rise heat detectors in the extraction plenum; CO
   sensor; flame sensor. Two independent detection channels.
3. **Response.** An independent safety relay chain (not the main PC) opens both the hob supply and
   oven supply contactors; the extraction damper closes to starve the fire (a sealed cell holds only
   about 0.3 m3 of air [E]); notify the user by push message and alarm.
4. **Suppression.** For a residential range-top: automatic wet-chemical or fusible-link systems
   (UL 300A class) [BK]; for an enclosed cell: fine water mist (careful with oil fires) or a clean
   agent (FK-5-1-12 total flooding) or inert gas; cartridge cost EUR 300–800 [BK]. Class K wet
   chemical is the correct agent for cooking oil (saponification) [BK].
5. **Lock-out.** After an event the machine locks out heating until service inspection.

### 8.3 Standards (verify against the paid standard texts)

* **IEC/EN 60335-2-6**: household stationary cooking ranges, hobs, ovens and similar; abnormal operation
  tests (empty-pan overheating, boil-dry). The standard's requirement that a hob cannot be switched on
  by remote control without a local action is consistent with the Home Connect "Remote Start" design
  [W: Home Connect page]; the exact clause must be verified [BK].
* IEC/EN 60335-2-9: grills, toasters and similar portable cooking appliances [BK].
* IEC/EN 60335-2-13: deep fat fryers, frying pans [BK]. -2-14 kitchen machines; -2-15 liquid heating;
  -2-25 microwave; -2-5 dishwashers [BK].
* Commercial: -2-36 ranges/hobs; -2-37 fryers; -2-39 multipurpose pans; -2-42 convection ovens and
  steamers; -2-58 dishwashers; -2-64 kitchen machines [BK].
* **UL 858** household electric ranges; **UL 1026** cooking and food-serving appliances; **UL 197**
  commercial; UL 300 and 300A for cooking fire-extinguishing systems; NFPA 96 for commercial cooking
  exhaust; NFPA 17A wet-chemical systems [BK].
* **EMC:** EN 55014-1, EN 61000-3-2/-3-3 (induction hob harmonics and flicker), EN 62233 (EMF) [BK].
* **Machinery:** Directive 2006/42/EC, replaced by Regulation (EU) 2023/1230 from January 2027 [BK];
  EN ISO 12100, EN ISO 13849 for the safety functions, EN ISO 13857 for safety distances [BK].
* A machine that cooks unattended sits between "household appliance" and "machine"; **a notified-body
  or lab consultation is needed early** (Open issues).

## 9. Portioning, plating and serving

### 9.1 How commercial systems dose

| Technique | Use | Price / data |
|---|---|---|
| Multihead combination weigher | Salads, dry goods, snacks | Ishida etc., EUR 20,000–100,000 [BK] |
| Gravimetric scoop or arm with load cell | Rice, veg, pasta, stew portions | Chef Robotics, Dexai; load cell 5 kg about EUR 10–30 [BK] |
| Piston depositor | Mash, dough, batter, sauces | Bakery depositors EUR 5,000–20,000 [BK] |
| Peristaltic or gear pump | Sauces, soups | Small peristaltic pumps EUR 30–60; Watson-Marlow about EUR 2,000–3,000 [BK] |
| Ladle on servo arm | Soup, stew | [BK] |
| Gravity chute + conveyor bowl | Sweetgreen Infinite Kitchen: automation is used for food assembly, not for food preparation; profit margin reported 28 % at two locations by Q1 2024 [W] | |

### 9.2 Plating techniques a machine can do

* **Ring mould:** stainless ring 80–100 mm lowered on the plate, filled by scoop, pressed with a
  plunger, lifted; produces a neat mound of rice, mash, veg [BK]. The ring is cleaned by wiping or the
  washer.
* **Sauce:** peristaltic pump with a 1–2 mm nozzle on an XY axis or the robot arm; drops, lines,
  swoosh (drop, then drag with a spoon) [BK]. Turntable plate for circular patterns.
* **Stacking:** layered ring fills (starch, protein, veg), then sauce, then garnish [BK].
* **Garnish:** vibratory chute or auger dispenser for herbs/seeds; salt/pepper shaker [BK].
* **Rim cleanliness:** deposit inside a ring or mask; an air knife or a wipe strip for the rim if
  needed [E].
* **Vision check** after plating with a camera; retry or flag the plate [E].
* **Warm plates:** warming drawer (Miele ESW type, about EUR 1,000–1,300 [BK]) at 60–65 C, or use the
  hot drying stage of the dishwasher; infrared lamp at the pass for a short hold [BK].

### 9.3 Plate types, storage and handling

* Recommend **two ceramic items**: a deep coupe plate of 250–270 mm and a bowl of 150–200 mm, both
  stackable, with a flat foot ring [E].
* **Stack handling:** a spring or motor **lowerator** (plate dispenser; commercial units hold 50–100
  plates, EUR 300–1,500, heated versions exist [BK]) keeps the top plate at a constant pick height,
  so a stack put in by the human in any state works.
* **Picking one plate:** 2–3 bellows suction cups of 40–60 mm on the plate centre (fails on greasy
  or wet plates) or three-finger rim grippers (more robust) [E]; screw destackers (helical
  escapement, as for trays/cups) as a mechanical alternative [BK].
* Different types must be separate stacks. Identify them with vision or with keyed slots.
* **Cutlery:** 18/10 spoons and forks are not magnetic; 18/0 is [BK]. Options: cutlery cassette
  loaded by the human, robot dispensing from slots, or leave cutlery to the human. Decision open.
* The human returns clean plates to the same spot (brief): the return position must tolerate
  imprecise stacking, so use a shallow funnel/guide and vision.

### 9.4 Serving hatch

* Options: motorised lift door, roller shutter (tubular motor, EUR 150–400 [BK]), vertical sliding
  glass door.
* **Recommended: rotating two-shelf pass-through (lazy-susan).** One shelf is always outside, one
  inside; a fixed barrier is always between user and robot. No pinch point except at the shelf
  edges (enclosed by a soft seal and a torque limit) [E].
* If a door is used: power-operated door force limits per **EN 12453**: dynamic peak 1400 N, 400 N
  after 0.75 s, 150 N after 5 s, static 150 N [BK, verify]; plus a **light curtain (EN 61496 type 2)
  or a resistive safety edge (EN 12978)**, motor current monitoring, speed below 0.1 m/s, and an
  interlock so the door opens only when the robot has left the hatch zone. EN ISO 13857 sets safe
  distances for openings the arm can pass through [BK].
* Add a **presence/removal sensor** (load cell or IR beam) on the hatch shelf so the tray is only
  retracted after the plate is taken (with time-out and reminder).

## 10. Dishwashing

### 10.1 Products

| Product | Data | Source |
|---|---|---|
| Bosch SPS4ELW01D, 45 cm, Home Connect | from EUR 599; eco programme 3 h 15; 8.9 L; 59 kWh/100 cycles | [W] |
| Bosch SPS4HMI49E, 45 cm | EUR 799; 3 h 40; 9.5 L; 10 place settings | [W] |
| Bosch SPU4HMS10E (built-under 45 cm) | listed | [W] |
| Miele G 7000 series | water from 6 L; short programme 58 min; AutoDos; door auto-open at the end [BK]; Miele@home | [W] partially |
| Miele G 5740 SCi SL (45 cm) | listed | [W] |
| Fisher & Paykel DishDrawer Series 7 single | USD 1,049; 7 place settings; 1.81 gal (6.9 L) per cycle; plates up to 11 in (280 mm); 43 dBA | [W] |
| Miele Professional PFD 401 (built-under, fresh water) | 380 plates/h or 20 baskets/h; shortest programme 6 min; 60 cm niche; M Touch Flex display | [W] |
| Winterhalter UC-M | rack 500 x 500 mm; tank 15.3 L; rinse water 2.4 L per cycle; tank 40–66 C; rinse 40–85 C; 600 x 637 x 725–760 mm; door open depth 940 mm; capacity 40/28/24 racks/h in three programmes; cycle times adjustable 120/90/60 s (another source: 47–163 s); max theoretical 77 racks/h | [W] |
| Meiko M-iClean UM | rack 500 x 500 mm; tank 11 L; rinse water 2.4 L; 180/180/240 s (another source states 95/150/210 s); 4 kW boiler + 2 kW tank heater, total 4.7 kW; 25 A fuse; ComfortAir heat recovery saves up to 21 % | [W] |
| Miele PG 8172 (throughfeed/hood) | shortest 50 s; 72 baskets/h; automatic start on closing hood; integrated dosing pumps; turbidity sensor | [W] |

### 10.2 Cycle time and energy from first principles

* Cold-fill rinse: 2.4 L heated from 12 to 85 C needs 2.4 x 4.19 x 73 = 734 kJ = 0.20 kWh [E].
  With a 4 kW boiler that is 3 minutes of heating, which is why cycles with cold-water supply
  are 180 s and not 60 s; the 60–90 s cycles assume a hot supply or a large boiler buffer [E].
* Tank: 11 L from 12 to 60 C needs 0.61 kWh; with a 2 kW heater that is about 18 min warm-up [E].
  Leave the tank hot for the duration of use (standby loss).
* A household dishwasher uses about 0.8–1.0 kWh and 9 L per cycle over 3+ hours [W: 59 kWh/100 cycles,
  8.9 L] but at lower peak power (about 2 kW).
* Detergent: commercial units have built-in dosing pumps for detergent and rinse aid (Winterhalter
  chemical dosing; Miele PG dispenser pumps [W]); household units use tablets or AutoDos [BK].

### 10.3 Controllability

* **Household (Home Connect / Miele@home):** programmes can be started remotely; dishwashers support
  Permanent Remote Start after a one-off confirmation on the appliance [W]. Door opening by the
  robot is not supported (partial auto-open only) [BK].
* **Commercial:** start on door/hood close is standard (Miele PG 8172 [W]); Winterhalter offers
  CONNECTED WASH for monitoring [W]. A programmable external interface (potential-free start
  contact or Modbus) must be asked from the vendor [BK]. A hood or drawer motor is easier to retrofit
  than a hinged door with 940 mm swing.

### 10.4 Washing pots, tools and boxes automatically

| Object | Method | Notes |
|---|---|---|
| Plates, cups, cutlery | Standard rack in household or commercial washer | Human returns them, per brief |
| Cooking pot and pans | (a) **In-place spray head in the lid** with recirculating pump, detergent dosing, heated wash water, drain valve; (b) robot transfers to commercial washer basket | (a) is a small CIP system (spray ball/rotary head, flow of tens of L/min at 1.5–3 bar [E]); risks: burnt residue, bottom-drain leaks |
| Stirrer, spatulas, ring moulds, tongs | Robot places them in a tool basket in the washer, or a tool-cleaning bay with nozzle jets and hot air dry | Ultrasonic 40 kHz baths (10–30 L, EUR 300–1,500 [BK]) clean graters and meshes but need tank hygiene and add noise: optional |
| Storage boxes (size from R3) | Commercial rack washer or crate washer; boxes on edge in a special rack in a 500 x 500 rack | Confirm box size against washer entry height: Meiko US/UM 315 mm; UM+/UL 435 mm entry [W] |
| Oven | Own cleaning programme (section 6) | |
| Cooking chamber | Spray nozzles | R6/D7 |

Dish-washer options for the brief's "human puts the used dishes in a dishwasher":

* **Option 1 (pragmatic v1):** ordinary household dishwasher for human dishes (manual door), plus a
  separate process washer for the machine's own items.
* **Option 2 (target):** one commercial undercounter washer for everything; the human puts used
  dishes on a tray at the hatch; the robot loads a rack (a 500 x 500 rack holds about 18 plates
  [BK]); 2–4 minute cycles; needs the power and a robot-friendly door.

## 11. Recommendations: a compact, self-cleaning, mostly off-the-shelf cooking cell

Baseline for 1–6 portions (D5/D6/D7 to refine):

```
        600 mm depth, about 1.2 m width, cooking zone 0.9-1.2 m above floor
   +-----------+-----------------------+-----------+
   | COMBI     |  Induction zone 1     | Plating   |
   | OVEN 60   |  (stir-pot, fixed)    | station   |--> rotating hatch
   | (GN 1/2)  |  Induction zone 2     | + plate   |
   |           |  (sauté / kettle)     | lowerator |
   +-----------+-----------------------+-----------+
   | Process   |  Boiler, pumps, PSU,  | Warming   |
   | washer    |  extraction + filters | drawer    |
   +-----------+-----------------------+-----------+
```

1. **Oven:** household plumbed combi-steam (Miele DGC XL class, Bosch Serie 8 HSG) or, if a
   three-phase supply exists, Rational iCombi Pro XS; choose a model with **permanent remote start**
   or add the Remote Start retrofit; add an automated or robot-openable door; cover GN 1/2 or 2/3.
   Alternative for cleaning: a Bosch HRG7764B1 class steam-assist pyrolytic oven for roast/bake plus
   pot steaming.
2. **Hobs:** two OEM induction zones (2 x 2.0–3.5 kW under a load manager), each with pan detection,
   pan-base NTC, and a UART/RS485 or analog control. Prototype on a commercial 3.5 kW knob hob.
3. **Stirred pot:** 4–6 L 18/10 pot with ferritic base and two ear handles, overhead scraper head from
   the tool changer, thermowell PT1000; optional fixed Thermomix/Cookit-type bowl for purées. Pilot
   with an off-the-shelf Kenwood Cooking Chef XL (6.7 L) or Bosch Cookit (3 L).
4. **Sauté/sear:** stainless pan; spatula arm as fallback; **contact grill** for patties and steaks.
5. **Water:** 5 L pressurised boiler with solenoid for pasta water and rinsing.
6. **Extraction:** closed chamber, 100–150 m3/h, grease mesh, carbon, dehumidifier stage; drain.
7. **Safety:** independent hardware chain for power cut-off; thermal camera + heat/smoke detection;
   suppression cartridge; load manager; door interlocks.
8. **Plating:** load cell under the plate, per-component dispensers, ring mould, peristaltic sauce
   pump, garnish shaker, warming drawer, lowerator with plate and bowl stacks.
9. **Hatch:** rotating two-shelf pass-through with removal sensor.
10. **Washing:** commercial undercounter washer (Winterhalter UC-M/Miele PFD 401/Meiko UM class) with
    baskets for tools, boxes and plates; in-lid spray head for the stir-pot; household dishwasher as
    fallback.

Indicative purchased-part cost (EUR, order of magnitude): oven 2,300–5,500; OEM induction 2 x 60
plus certification effort; consumer stirred cooker pilot 1,150–1,400; boiler 300–600; warming
drawer 1,000–1,300; commercial washer 4,000–7,000 [BK]; thermal camera 70; extraction and filters
500–1,000 [E].

## 12. Sources actually retrieved

* Home Connect API documentation: https://api-docs.home-connect.com/
* Home Connect remote start (search summary): https://www.home-connect.com/ba/en/discover-home-connect/discover/remote-start
* Thermador Permanent Remote Start: https://www.thermador.com/us/home-connect/permanent-remote-start
* Home Assistant Home Connect integration: https://www.home-assistant.io/integrations/home_connect/
* Home Assistant Miele integration: https://www.home-assistant.io/integrations/miele/
* Miele developer portal: https://developer.miele.com/
* Miele DGC combi-steam ovens (USD prices): https://www.mieleusa.com/e/combi-steam-ovens-1013128-c
* Bosch Serie 8 steam ovens (EUR prices): https://geizhals.de/bosch-serie-8-hrg7764b1-backofen-mit-dampfunterstuetzung-a3022959.html and https://www.bosch-home.com/de/de/category/kochen-backen/dampfbackoefen-dampfgarer
* Rational iCombi Pro XS: https://www.horeca.com/en/product/67416/rational-icombi-pro-xs-6-2-3e-electric-combi-steamer
* Unox CHEFTOP MIND.Maps Compact: https://www.unox.com/us_us/lines/cheftop-mindmaps-plus-compact/
* Anova Precision Oven 2.0: https://anovaculinary.com/products/anova-precision-oven
* Kenwood Cooking Chef XL: https://www.kenwood.com and retailer listings (search summary), e.g. https://shop.kenwoodworld.com/kw_sg/baking/stand-mixers/cooking-chef-xl-6-7l-kcl95004si.html
* Bosch Cookit MCC9555DWC: https://www.bosch-home.com/de/de/product/kuechenmaschinemitkochfunktion/cookit/MCC9555DWC
* Thermomix: https://en.wikipedia.org/wiki/Thermomix and https://www.vorwerk.com/gb/en/c/dam-home/service/instruction-manuals/TM6_digital_manual_MGB-en-GB_prefill_20190207.pdf (via search)
* Rational VarioCooking Center: https://www.manualslib.com/manual/1549785/Rational-Variocooking-Center-112.html (via search)
* StirChef: https://www.amazon.com/StirChef-SAUCEPAN-STIRRER-HandsFree-StoveTop/dp/B0000TPBYG
* Posha/Nymble: https://en.wikipedia.org/wiki/Posha_(company)
* Miso Robotics Flippy: https://www.therobotreport.com/miso-robotics-refines-flippy-fry-station-with-ai-partners/
* Sweetgreen/Spyce: https://en.wikipedia.org/wiki/Sweetgreen
* Induction cooking: https://en.wikipedia.org/wiki/Induction_cooking
* Induction OEM listing (Alibaba): https://sdhighway.en.alibaba.com/productgrouplist-805347473/3_5KW_Induction_cooker_SKD.html
* Commercial induction burner: https://abangdun.com/products/commercial-induction-cooktop-induction-burner-lower-power-even-heating-hot-plate-3500w-220v
* Single-phase induction power forum threads: https://www.elektroda.com/rtvforum/topic3441391.html
* MLX90640: https://www.adafruit.com/product/4407 ; MLX90614: https://www.adafruit.com/product/1747
* Quooker: https://www.quooker.de/
* Winterhalter UC series: https://www.winterhalter.com/products/undercounter-warewashers/uc-series/ and https://technology-products.dksh.com/product/winterhalter-under-counter-warewashers-uc-series-u50/
* Meiko M-iClean U: https://www.meiko.com/en-gb/products/commercial-dishwashing/under-counter-dishwashers-and-glasswashers/m-iclean-u/technical-data
* Miele PFD 401: https://www.mieleusa.com/e/professional-built-under-dishwashers-1015660-c
* Miele PG 8172: https://www.liverlaundryequipment.co.uk/commercial-dishwashers/pass-through-dishwashers/pg8172-performance-dishwasher/
* Miele G 7000: https://www.miele.de/de/m/der-autonome-geschirrspueler-g-7000-von-miele-4828.htm (search summary only; page fetch blocked)
* Bosch 45 cm dishwashers: https://www.bosch-home.com/de/de/product/geschirrspueler/geschirrspueler-freistehend/geschirrspueler-45-cm-freistehend/SPS4HMI49E
* Fisher & Paykel DishDrawer: https://www.fisherpaykel.com/us/dishwashing/built-in/series-7-contemporary-single-dishdrawer-dishwasher-dd24sax9-n-82333.html

## Open issues

1. **Supply:** is the household supply 1 x 230 V 16 A, or is a Herdanschluss available? (Brief says
   only "220 V".) This decides oven class (household versus Rational/Unox) and washer class.
2. **Oven API remote start:** which EU models support permanent remote start, and does the Miele/Bosch
   local network path work without a human at the appliance? Needs a hands-on test on a real oven.
3. **Oven door:** motorised, retracting, or robot-pulled; no vendor supports robot loading. Needs a
   mechanical concept and door-gasket/hinge lifetime check.
4. **OEM induction module:** protocol document, sample, EMC/LVD certification path, cooling in a
   closed cabinet. Confirm that the pan-detection status and NTC value can be read.
5. **Certification:** whether the whole cell is a machine (2006/42/EC, then 2023/1230) or a
   household appliance (LVD, IEC 60335-2-6); how unattended operation is treated; a lab
   consultation is needed. Verify every standard reference in section 8.3 against the paid texts.
6. **Vessel emptying:** fixed pot with drain valve and pump versus tilting versus robot lift and
   pour; interacts with D4 and the payload of the robot.
7. **Contact grill release layer:** PTFE sheet versus metal plates; washing of sheets.
8. **Meat core temperature:** automatic probe insertion or a model based on thickness and time.
9. **Cutlery** handling and the plate/bowl standard (single stack per type).
10. **Washer interface:** does the chosen commercial washer expose a start/stop and status
    interface, and can the door be motorised? Cold-water-only supply and the boiler time
    (section 10.2) versus the cycle time the recipe scheduler needs.
11. **Condensation stage:** dehumidifier versus accepting humid air; noise and drain.
12. **Fire suppression:** agent and product selection (wet chemical versus clean agent) for a 0.3 m3
    chamber; no product data were verified here.
13. **Missing data:** WebSearch quota ran out before these searches were done: commercial induction
    with an external control input (Hendi, Bartscher, CookTek), Bora/downdraft data, plate
    dispenser prices, Chef Robotics and Dexai specifications, fire-suppression products, Miele
    PFD 401 EU price and electrical data, Winterhalter EU prices. These need a second research pass.

## Risks

1. **Oven control lock-out (high):** if no oven offers permanent remote start and a retrofit is
   rejected, the cell cannot bake unattended. Mitigation: commercial oven with three-phase supply,
   or an OEM-built oven.
2. **Power (high):** simultaneous hob + oven + washer heating cannot be met on 16 A. Mitigation:
   load manager, scheduling in D10, optional three-phase.
3. **Fire (high):** unattended pan-frying and a hot oven in a closed cabinet. Mitigation: layered
   independent hardware safety (section 8.2), no deep frying, conservative temperature limits.
4. **Certification (high):** OEM induction and custom control of a heat source need approvals; time and
   cost are not estimated.
5. **Sticking and burning (medium):** stainless steel without non-stick coating needs correct
   pre-heat and fat; failures cause burnt residue that the washer may not remove. Mitigation:
   scraper, torque sensing, soak programme.
6. **Extraction saturation (medium):** grease and carbon filters clog; wear parts must be scheduled.
7. **Steam and grease damage to electronics (medium):** sensors, motors and camera lenses inside the
   cooking chamber need IP65+ housings or heated/air-purged windows.
8. **Sensor errors (medium):** IR readings on shiny stainless are wrong; a mis-set thermal
   limit can trigger false alarms or miss a fire. Mitigation: dual channels, black band, calibration.
9. **Washer door and power (medium):** commercial washers assume a hinged door with 940 mm swing and
   three-phase power [W]; a robot-friendly variant may not exist as a product.
10. **Price creep (medium):** each commercial unit (Rational/Unox EUR 7,000–12,000+; commercial washer
    EUR 4,000–7,000) may exceed the target budget of a consumer machine.
11. **Vendor dependence (medium):** cloud APIs (Home Connect/Miele) may change, limit features
    and need Internet; a local fallback must exist for safety functions.
12. **Data quality (low to medium):** many numbers here are [BK] or [E]; they must be re-verified
    before D5/D6/D7 rely on them.
