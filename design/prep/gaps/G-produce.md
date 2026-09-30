# Meal preparation — targeted inventions for the produce-side gaps

Round 2 of idea finding (PLAN.md, Phase 2P). Input: the gap list in
[02-concept-catalogue.md](../02-concept-catalogue.md) section 2.4. This document covers the produce gaps
G1, G2, G6, G7, G10 and three related operations (robust potato/carrot peeling, citrus peel and zest,
washing gritty produce). Assembly, stuffing, poultry and singulation gaps (G3, G4, G5, G8, G9) are not
covered here.

All mechanisms are **concept-independent modules**: a passive tool on a manipulator or spindle, a cassette
under a ram, a small station, or a fixture. Each states what it needs from its host (section 0.3).

---

## 0. Conventions and summary

### 0.1 Markers

| Marker | Meaning |
|---|---|
| [K] | Known practice (industrial machine, consumer product or established cook's method) |
| [C] | Calculated in this document from stated physics |
| [E] | Engineering estimate, not measured |
| [U] | Unknown; a bench test decides |
| [R2], [R4], [R6] | From `research/02-meal-corpus.md`, `04-food-prep-mechanisms.md`, `06-hygiene-cleaning.md` |

Mechanism numbers are **GP-nn** (gap, produce), so they do not collide with SM-001…SM-244. Confidence is
H / M / L as in the catalogue: H rests on known practice, M is plausible physics without a test, L is a
sketch. **Nothing in this document has been tested.** Every success rate is [E] unless marked [K].

Meal counts were recounted from the corpus rows (248 meals) by operation code and ingredient.

### 0.2 Result in one table

| Gap | Recommended | Conf. | Needs vision | Fallback | Cost of the fallback |
|---|---|---|---|---|---|
| G1 onion | GP-11 three deep slits with a depth shoe, dry wipe, then jet; camera check and one deeper re-pass | M | yes (axis, check) | frozen diced or peeled onion, garlic paste | MEAL-002: none. MEAL-009: fails (129 meals) |
| G1 garlic | GP-17 crack the bulb, press cloves skin-on through a 3 mm plate | H | no | garlic paste, frozen garlic | none under MEAL-012 |
| G2 soft herbs | GP-21 bundle cut at the leaf line, tender stems chopped with the leaves | H | no | frozen chopped herbs | none for cooked dishes; garnish quality |
| G2 woody herbs | GP-22 cook the sprig in an infuser basket and remove it; GP-23 freeze-thresh where loose leaves are needed | H / M | no | dried thyme, rosemary | none |
| G2 florets | GP-25 cone cut round the stalk, then size by a coarse grid; GP-26 whole-head cooking for SD18 | M / H | coarse (stalk side) | frozen florets | 3 meals in MEAL-009 |
| G6 pepper | GP-61 stalk-seeking plug corer in a floating nest, inverted rinse | M–H | coarse (stalk up) | frozen strips; no fallback for stuffed peppers | 26 meals in MEAL-009; DM13 in MEAL-002 |
| G6 others | same corer family in 3 diameters (tomato scar, apple, cucumber segments); chilli not deseeded; squash roasted first; avocado bought as pulp | H / M / buy | per item | frozen or tinned | avocado 2–4 meals in MEAL-009 |
| G7 cabbage leaves | GP-71 freeze–thaw the whole head (replaces blanching), cone-cut the core, release leaves by water into the core pocket | M | coarse (core side) | none permitted; Schichtkohl is a different dish | DM12 falls out: 1 of the 4 reserve meals of MEAL-002 |
| G7 lettuce | GP-75 butt cut, leaves separate in the wash basket | H | coarse (butt end) | bagged washed salad | none |
| G10 small items | GP-101 "do not trim" rules (mushroom, radish tail, sprout base), GP-102 camera-indexed single cut for ≤ 40 pieces; beans bought frozen | H / M / buy | yes for GP-102 | frozen beans and sprouts | ≤ 5 meals in MEAL-009 |
| Potato, carrot | GP-P1 route by recipe: cook in skin and slip or rice, or scrub skin-on; GP-P2 knurled-steel drum stopped by camera for raw-peeled uses | H / M–H | for the stop only | vacuum-peeled potatoes | none under MEAL-012 |
| Citrus | GP-Z1 fruit spun against a fine rasp at 2–4 N; peel by depth-shoe paring | H / M | no | bottled juice, no zest | quality only |
| Gritty produce | GP-W1 dunk basket over a sediment trap, baths repeated until the turbidity sensor is satisfied; leek is sliced before washing | H | no | bagged washed salad, frozen spinach | none |

### 0.3 What the modules ask of the host cell

| Need | Used by | Remark |
|---|---|---|
| One camera looking at the work position (colour, 2 MP is enough) | GP-11, GP-61, GP-71, GP-102, GP-P2 | Every candidate concept K1–K8 has at least one camera in the cell |
| A means to bring an item to a tool axis within ±15 mm and ±20° | GP-11, GP-61, GP-25, GP-71 | Manipulator regrasp, or a nest the item is dropped into |
| One slow rotary axis, 30–150 rpm, 0.5 Nm (spindle, turntable, wrist roll) | GP-11, GP-Z1, GP-25 | Not needed for the cassette variant GP-12 |
| A push of 60–100 N over 120 mm (ram, Z axis, manipulator) | GP-12, GP-61, GP-17 | |
| Mains water fan jet, 3 bar, about 0.35 L/s | GP-11, GP-61, GP-71 | Force 8 N [C], see 1.2 |
| The wash chamber takes all tools as loose ware | all | No tool in this document is cleaned in place |
| A strainer basket (2 mm) in the waste path, emptied to bio-waste | all | Skins, seeds and leaves must not enter the drain |

---

## 1. G1 — Peel onion, shallot and garlic from whole

### 1.1 Anatomy, and what it implies

```
            neck (dry, twisted leaf bases; dry tissue can reach 10–15 mm into the bulb)
             |
           __|__
        .-'  |  '-.      dry tunics: 1–3 sheets, 0.05–0.2 mm each, brittle when dry,
      .'  .--+--.  '.    leathery and sticky when wet; loose, often with an air gap
     /  .' .-+-. '.  \   semi-dry scale: 0.3–1 mm, dry at the top, fleshy at the base
    |  |  | ( ) |  |  |  fleshy scales: 8–12, the outer ones 3–5 mm thick (large onion),
     \  '. '-+-' .'  /                   2–3 mm (small onion, shallot)
      '.  '--+--'  .'    every scale is a closed shell of revolution; adjacent scales
        '-.__|__.-'      are joined ONLY at the basal plate; between them there is a
           \###/         membrane and no adhesive (sliced onion falls into rings [K])
            '-'  basal plate (stem): a cone 3–6 mm high; the OUTER scales attach at its rim
           roots
```

Four facts decide the design.

1. **A scale is a closed ring after the two pole caps are cut off.** It is barrel-shaped, so it cannot slide
   off axially and cannot be lifted off radially. It has to be opened. This is why top-and-tail alone does
   nothing and why every industrial peeler scores the skin first [K].
2. **One slit makes a C-ring, which must spring open by the full diameter to come off.** A dry tunic tears
   instead and leaves patches; a wet one clings. Two or more slits make segments of ≤ 180°, which have no
   undercut and fall off radially with no deformation at all. Round 1 proposed one slit almost everywhere
   (SM-060, SM-061); this is the first weakness.
3. **A scale that is not cut through stays a closed ring and cannot come off.** So the slit depth defines
   exactly what is removed, and the removal action does not have to be selective: it may be as rough as it
   likes. Round 1 slit 2 mm deep and then asked the jet or the rubber to decide what is skin; this is the
   second weakness. Industrial machines set the knife depth to take one or two layers for the same
   reason [K].
4. **The interesting boundary is visible on the top cut face.** After topping, the face shows concentric
   rings: brown or red translucent tunics outside, opaque white flesh inside, and dry neck tissue as a dark
   centre if the cut was too shallow. A camera reads it directly.

Size of the loss, for honesty [C]. Onion radius R, polar caps of height h: cap volume π h² (3R − h) / 3.

| Item removed | R = 35 mm (Ø 70, 170 g) | R = 25 mm (Ø 50, 60 g) |
|---|---|---|
| Top cap, h = 0.29 R (cut face Ø = 0.7 D) | 5.5 % | 5.5 % |
| Tail cap, h = 0.20 R (cut face Ø = 0.6 D) | 2.8 % | 2.8 % |
| Tunics | 2–4 % | 3–5 % |
| One fleshy scale, 1 − ((R − t)/R)³ | t = 3.5 mm: 27 % | t = 2.5 mm: 27 % |

So "lose one fleshy layer" costs 27 % of the onion, not the 10–15 % stated in round 1. At about
1.20 €/kg this is 5 cents per onion and irrelevant as money, but it is 45 g of extra waste per onion and
it sets the stock: plan 1.4 kg of whole onions per kg needed.

### 1.2 Forces available without a compressor [C]

| Source | Value |
|---|---|
| Mains water at 3 bar through a 1 × 15 mm fan nozzle | v = √(2 p/ρ) = 24 m/s; Q = 0.36 L/s; jet force ρ Q v = 8.6 N |
| Industrial air nozzle, 6 bar, Ø 2 mm | thrust about 2.4 N per nozzle, 200–400 L/min free air, 90–100 dB(A) at the nozzle |
| Spin, Ø 70 mm at 600 rpm | 138 m/s² = 14 g; a 15 g shell segment is thrown with 2 N |
| Silicone wiper at 5 N normal force | on dry tunic μ ≈ 0.8 [E] → 4 N shear; on wet flesh μ ≈ 0.2–0.3 [E] → 1–1.5 N |

A mains fan jet delivers more force than the air nozzle of an industrial peeler. The reason industry uses
air is that the skins stay dry and do not stick. Hence the order chosen below: **dry first, water last**.

### 1.3 Candidates

| ID | Mechanism | Physics and numbers | Vision | Cleaning | Conf. |
|---|---|---|---|---|---|
| **GP-11** | **Segment slit and wipe on a spit.** Top and tail to the cut-face rule (top Ø 0.7 D, tail Ø 0.6 D). Hold pole to pole. A blade with a depth shoe draws 3 meridian slits at 120°, 2.5 mm deep, running out through both faces. Rotate at 60–120 rpm against a silicone finger comb, dry, 5 s; then the fan jet 3 s. Camera check; if skin remains, 3 more slits at 5 mm, offset 60°, and repeat. | Slit 5–8 N per pass [E]; wipe torque 0.2 Nm; 25–30 s per onion, 45 s with a re-pass; water 1 L. Loss 11–13 % when the first fleshy scale survives, 38 % when it goes; average 18–25 % [E]. First pass 85–90 % [E], with re-pass ≥ 95 % [E] | Axis before chucking; top face after the top cut; whole surface after the wipe | Blade-and-shoe tool, comb and prong cups are loose stainless or moulded silicone ware → wash chamber. Work is done over a deep waste pan, skins never touch the cell wall | **M** |
| GP-12 | **Push-through slit-and-strip cassette.** The topped and tailed onion is pushed, standing on its flat, through two one-piece flexure crowns: crown 1 carries 3 shoes with 2.5 mm blades, crown 2 carries 6 silicone-tipped fingers pointing against the travel. The Ø 20 ram foot touches only the centre scales. | Same principle as GP-11 without rotation. Ram 40–80 N over 120 mm [E], 5 s. Accepts Ø 40–90 with 25 mm finger travel. No re-pass depth change unless a second cassette (5 mm) exists | Axis before the top and tail cuts only; check afterwards | Two laser-cut spring-steel crowns (1.4310), no pivots, no springs → wash chamber. Blade roots are the crevice to watch | M–L (fingers may ride over a segment instead of holding it [U]) |
| GP-13 | **Halve and shuck.** Top, tail, halve pole to pole, halves cut face down. A silicone pad wipes once over the dome from one straight edge to the other at 5–10 N. Every shell is now a free arch; the pad grips what is dry and slides over what is moist. | Relies on the friction contrast of 1.2 (4 N against 1–1.5 N). Not deterministic: the number of shells taken depends on moisture. 10 s per half. Loss 10–38 % | Axis; check | Pad is loose ware. Fits the grid dicer (SM-009), which wants halves face down anyway | M–L |
| GP-14 | **Steam-slip and pop** (SM-063 refined). Cut the tail only, 60 s in steam, squeeze from the neck end between two silicone rollers: the bulb pops out of the softened skin at the root opening (cook's method for pearl onions [K]). | Heat front √(α t) = √(1.4·10⁻⁷ × 60) = 2.9 mm [C]: the first scale is half-cooked. Steam 60 s at 2 kW = 33 Wh. 20 s handling | Axis | Rollers are ware; steam comes from the oven or a lidded pot | M for shallots and pearl onions (Ø ≤ 40); L for large onions, where the shell has to burst. Counts as adapted for raw use |
| GP-15 | **Dice skin-on, separate the skin by elutriation.** Top, tail, dice through the grid, then wash in an upward flow over a weir. | Terminal velocity in air: dry flake 0.9 m/s, 6 mm dice 10 m/s [C], but a wet flake is held to a dice by capillary force 1.7 mN against 0.65 mN of drag at 5 m/s [C], so air fails. In water the dice sink at about 5 cm/s, flakes at mm/s [C]; an upflow of 2 cm/s carries the flakes out | None, but the two end cuts still need the axis | Weir vessel and screen are ware | **L.** Flakes that stay attached to the outer dice end up in the food, and a failure cannot be seen or repaired. The wash also leaches the cut onion and wets it, which hinders browning. Only for stocks and sauces that are strained |
| GP-16 | **Compressed-air blast** after 4 slits (the industrial reference, about 95 % on dry sorted onions [K], [R4]). | 6–8 bar; a 24 L receiver gives one 3 s blast; silent compressor 150–300 €, 30–40 L of volume, condensate to drain | Axis | Dry, but flakes fly: needs a closed chamber with a filter | H as a process, **rejected** for the home: compressor, volume, noise near the L_AFmax limit of NOI-003 |

Rejected without a candidate number:

| Approach | Why not |
|---|---|
| Abrasive drum or rollers | Tunics are tough and flexible; abrasion removes 30 % and more before the neck and root hollows are clean, and onion juice coats the drum. No industrial onion line uses it |
| Freezing the skin | The dry tunic is already brittle; freezing damages the flesh below |
| Flame or hot dry drum (SM-054) | Works for industrial pearl onions with a washer behind it [K]; scorch taint and an open heat source in the cell |
| Undersized rigid die (SM-062, SM-057) | The bulb is a barrel: the die either cuts a cylinder out of it (yield 55–70 %) or is elastic, which is GP-12 |
| Lye | Hazardous chemical [R4] |

### 1.4 Recommended: GP-11

```
 side view                                   end view (from the top cut face)

   prong cup      depth shoe   prong cup            slit 1
   (driven)       + blade      (free)                 |
      |             __|__         |               .---+---.
      v            |  V  |        v             .'  tunics '.      <- 3 slits at 120°,
   ==[##]---( (  ( onion )  ) )---[##]==        | .-------. |         2.5 mm deep
            ^top cut        ^tail cut          /|'  flesh  '|\
                                         slit 3 '.         .' slit 2
      silicone finger comb  ///////              '-._____.-'
      (fixed, dry wipe against rotation)
      fan jet 3 bar ------->  (after the dry wipe)      all of it over a deep waste pan
```

Sequence, with the reason for each step:

1. **Find the axis** (camera: root beard and neck tuft), chuck pole to pole, 20–30 N axial.
2. **Top cut** at the height where the cut face is 0.7 of the diameter (10 mm on a Ø 70 onion). Camera
   reads the face: a dark centre means dry neck tissue, cut 4 mm more (up to 3 times).
3. **Tail cut** where the face is 0.6 of the diameter (7 mm). This severs the outer scales from the rim of
   the basal plate and leaves the core of the plate, which keeps the inner scales together for dicing.
4. **Three slits.** The shoe rides on the surface with 3–5 N and flattens loose tunics; the blade stands
   2.5 mm proud. This passes the tunics (≤ 0.5 mm) and the semi-dry scale (≤ 1 mm) and ends inside the
   first fleshy scale when that scale is thicker than about 2 mm, which then stays a closed ring (fact 3).
5. **Dry wipe**, then **jet**. Tunic segments fall; if the first fleshy scale was cut through, its three
   segments fall as well. Nothing else can.
6. **Camera check** of the turning onion: skin is brown/yellow or dark red, dull and translucent; flesh is
   white or pale and glossy. Residue > 5 % of the surface → second pass at 5 mm, offset by 60°.
7. The prong stubs are in the two caps, which are already waste.

Why this should reach 95 % where round 1 did not: the removal is decided by geometry (cut depth), the
segments have no undercut, the skins are removed dry, and there is a deterministic escalation that costs
yield and not success. What it does not cure:

| Case | Frequency [E] | Behaviour |
|---|---|---|
| Double onion (two centres, dry skin between them inside one bulb); most shallots | 3–8 % of onions, 30–50 % of shallots | Visible on the top face as a dark line. Halve along the line, treat each half with GP-13, or accept. Shallots: prefer GP-14 |
| Rotten or mouldy patch under the skin | 1–3 % | Found by the check; second pass; if still dark, reject the onion and take the next |
| Sprouted onion, green centre | seasonal | Not a peeling failure; recipe rule |
| Ø < 40 mm (small shallots) | — | Prong cups too large; GP-14 or substitute onion for shallot in the recipe |

**Batch mode.** Peeling does not have to happen at meal time. Peeled whole onions keep 10–14 days at
2–4 °C in a closed box [K, the commercial product]. The machine can peel a week's onions in one session at
night, soil the tools once, retry failures without time pressure and keep the noise out of the dinner
hour. The same applies to garlic cloves.

**Parts.** Blade with integral shoe (one machined stainless piece, blade 0.5 mm, two protrusions: 2.5 and
5 mm on opposite sides), silicone finger comb (moulded, off-the-shelf pastry-brush type is enough for the
test), two three-prong cups (apple-peeler type), fan nozzle (standard 1/4" flat-jet, 15°). Custom parts: 2.

### 1.5 Garlic

| ID | Mechanism | Numbers | Conf. |
|---|---|---|---|
| **GP-17** | **Crack and press.** The bulb is crushed flat-side down between two plates (60–120 N [E]) and breaks into cloves and loose outer skins. Cloves are dropped skin-on into a press cup with a 3 mm hole plate and pressed; flesh extrudes, the skin stays as a cake and is knocked out by inverting the cup over waste with a stud follower from the outlet side (SM-011, SM-064). | 150–300 N on a Ø 30 cup = 2–4 bar [E]; residue 10–20 % of the clove [K, consumer presses]; 5 s per batch | **H** for crushed garlic, which is what almost all of the 44 garlic meals use |
| GP-18 | **Shake-peel** of cracked cloves in a closed hard vessel pair, 15–20 s at 4–5 Hz and 60 mm stroke, then dry winnowing in the same vessel tilted over a 12 mm slot: cloves roll out, skins stay. | Cook's trick [K]; 70–90 % of cloves clean with dry garlic [E], much worse with fresh or damp garlic | M–L; only needed for whole or sliced cloves |
| GP-19 | **Roll under silicone**: clove rolled once under a silicone pad at 30 N; the skin cracks and sticks to the pad (garlic-tube principle [K]). | 3 s per clove; the pad then carries the skins to the waste | M; one clove at a time |

Recommendation: GP-17. Recipes that ask for sliced or whole cloves (few) are adapted to crushed garlic or
to whole unpeeled cloves that are roasted and squeezed; both are ordinary cooking practice.

### 1.6 Cheapest bench experiment (under 20 €, half a day)

Material: 30 onions (10 yellow Ø 60–80, 10 small yellow Ø 40–55, 5 red, 5 old and loose-skinned), kitchen
knife, a utility-knife blade screwed into a wooden block so that it stands 2.5 mm proud (second block:
5 mm), a silicone pastry brush or pot holder, a garden-hose flat nozzle on the tap, kitchen scale, phone
camera. Optional: cordless drill and two forks as a spit.

| Run | Variable | Record |
|---|---|---|
| 1 | Number of slits 1 / 2 / 3 / 4 at 2.5 mm, dry wipe | share of surface skin-free (photo), time |
| 2 | Depth 1.5 / 2.5 / 4 mm with 3 slits | which scale came off, mass loss |
| 3 | Dry wipe against wet wipe against jet only | residue, skins sticking |
| 4 | Tail-cut depth 4 / 7 / 10 mm | are the outer segments still attached at the root? |
| 5 | Re-pass at 5 mm on all failures | final success |

Pass: ≥ 26 of 30 skin-free (≤ 5 % of surface) after the first pass, 29 of 30 after the re-pass, mean loss
≤ 25 %. If run 1 shows no difference between 1 and 3 slits, fact 2 is wrong and GP-13 becomes the
candidate. Garlic: 3 bulbs, two cutting boards, a consumer press; weigh the residue.

### 1.7 Fallback

Frozen diced onion, peeled fresh onion, garlic paste or frozen garlic (MEAL-012 a). **MEAL-002 is not
affected.** MEAL-009 (≥ 90 % from whole produce) cannot be met: 129 meals (52 %) contain PLA, 112 of them
onion, 17 garlic only. With GP-17 alone (garlic) the 17 garlic-only meals are recovered and 112 remain.
Two practical caveats: peeled whole onions are a catering product and not on every supermarket shelf, so
the real fallback is frozen diced onion, which is watery and browns poorly [R2] and cannot give rings,
wedges or halves (Zwiebelrostbraten, onion in a stock, raw rings on a salad). That is a quality cost that
the coverage count does not show.

---

## 2. G2 — Strip and pluck: herbs, kale, florets

### 2.1 What the operation really is

STR is in 9 corpus meals. By ingredient: soft herbs in 5 (DM32 Grüne Soße, SP08, ME05, MX06, IN04 partly),
cauliflower in 3 (SD18, AS12, IN08), lettuce in 2 (SA08, MX02; treated under G7), spinach in 1. Thyme and
rosemary appear in 8 meals and kale in 1, but the corpus does not count STR for them (sprig cooked whole,
frozen kale). The gap is therefore four different tasks, and three of them have a cook's answer that is
not plucking:

| Task | What a cook does | Consequence |
|---|---|---|
| Parsley, coriander, dill, basil, chervil | Cuts the bunch where the leaves begin and chops the rest with its thin stems | No plucking; one cut |
| Thyme, rosemary, bay, sage | Puts the sprig in the pot and takes it out, or strips it between two fingers | Infuse and remove, or strip |
| Kale, chard, spinach with thick stems | Pulls the stem through the closed hand | A true stripping pull, on a stiff stem |
| Cauliflower, broccoli | Cuts round the stalk; florets fall; large ones are split | A cone cut and a sizing step |

### 2.2 Candidates

| ID | Mechanism | Physics and numbers | Vision | Cleaning | Conf. |
|---|---|---|---|---|---|
| **GP-21** | **Bundle cut at the leaf line.** The bunch arrives banded, butts to one end of a long box. It is pushed butt-first against a fence; one cut at 45 % of its length (parsley, coriander) or 60 % (dill); the butt part with the band goes to waste, the top part to washing and chopping (SM-024/-026). | Bunch 30–50 g; cut 20–40 N with a draw [E]; loss 35–45 % by mass, which is what a cook discards; 5 s | No; bunch length from the board scale or a light barrier | Knife and board only | **H** |
| **GP-22** | **Infuser basket.** Woody sprigs (and bay, cloves, peppercorns) go whole into a perforated stainless capsule (tea-ball type, Ø 50, hinged or two-part) that is hung on the pot rim and lifted out before serving. | No force; leaves give their flavour in 15–30 min of simmering as in a bouquet garni [K] | No | Capsule is ware; opened over waste | **H** for braises, soups, sauces (all 8 thyme meals are of this kind) |
| GP-23 | **Freeze-thresh and sieve.** Sprigs are frozen (crust-freeze plate SM-240, 60–100 s, or 15 min in the freezer airlock), tumbled 20 s in a closed cup, and tipped onto a 5 mm mesh shaken horizontally: leaves pass, stems (40–100 mm long) stay. Extends SM-027. | Frozen petioles are brittle and snap in bending [K, cook's trick for thyme]; leaf yield 85–90 % [E]; stem fragments < 5 % by mass [E]; tender tips break off and pass, which is harmless | No | Cup and mesh are ware; dry process | M; leaves are for cooked dishes and quick finishing, not for garnish |
| GP-24 | **Ripple comb.** A stainless plate with V-notches tapering from 8 to 1.5 mm, edges radiused 0.3 mm. The stem butt is laid into a notch from the side (no threading) and pulled through. A 12 mm notch does kale and chard. | Thyme 2–5 N per sprig, rosemary 5–10 N, kale stem 20–40 N [E]. Kale: one leaf in 3 s, yield 90 % [E]. Thyme: one sprig at a time, 20–40 sprigs per bunch | Stem butt must be found and gripped: yes for thyme, no for kale (stiff, thick) | Plate is ware, no crevices | **M–H for kale and chard; L for thyme** (gripping single floppy sprigs is the hard part, not the stripping) |
| **GP-25** | **Cone cut round the stalk.** Head stalk-up in a bowl nest. First a flat cut across the stalk 10–15 mm below the curd rim removes the leaf bases. Then a blade set at 25° to the axis turns once round the stalk (or 4 angled plunges), cutting a cone Ø 60 × 50 mm. Florets fall apart; pieces larger than 45 mm are pushed through a coarse wedge grid. Broccoli: one flat cut where the stalk branches does the same. | Stalk cut 40–80 N with draw [E]; 20 s per head; crumbs 5–10 % [E] (they go into the dish); industrial floretting works this way [K] | Coarse: which side is the stalk | Knife and grid are ware | M |
| **GP-26** | **Cook the head whole, portion afterwards** (SD18 in its traditional form) — or chunk-cut raw into 25 mm slabs and strips for curries (adapted cut). | Whole head Ø 150, 12–15 min steamed; portioned by a wedge cut or a spoon | No | — | H; chunk cut counts as adapted (MEAL-013) |
| GP-27 | **Slot plate over pull rollers** (grape-destemmer principle): two Ø 12 rubber rollers under a 2 mm slot pull stems down; leaves bunch at the slot and tear off. | Continuous; 10–20 N pull | No | Two shafts and a nip in the food zone | L; a machine for 9 meals, and the rollers are hard to clean. Rejected |

```
 GP-21 bundle cut                     GP-24 ripple comb (kale)          GP-25 cone cut

  fence                                   plate, 2 mm                        blade at 25°
   |  butts        leaf zone              .-\  /--\  /-.                        \
   |==###==========~~~~~~~~~~              |  \/    \/  |    pull             ___\____
   |  band    ^cut at 45 %                 |  V      V  | ------->           /  .-\-.  \   stalk up
   |__________|__________ board            '------------'   stem           /  /stalk\  \
      waste   |   to wash + chop           leaf stays on this side        ( florets fall )
```

### 2.3 Recommendation

GP-21 for soft herbs, GP-22 for woody herbs, GP-25 with GP-26 for florets, GP-24 (12 mm notch only) for
kale and chard. GP-23 is an option where a recipe wants loose thyme leaves; it needs no new hardware in
a cell that has a crust-freeze plate. With this split, STR needs **no dexterous plucking at all**. The
only new parts are the infuser capsule (bought), the notch plate (one laser-cut part) and the angled
blade (a bought curved grapefruit or coring knife will do for the test).

Request to ingestion: leafy bunches are stowed banded, aligned in a long box (GN 1/3 length), butts to the
marked end.

### 2.4 Bench experiment (under 15 €)

1. Parsley, coriander, dill, basil: cut 3 bunches each at 35 / 45 / 55 % of length, chop the top part, and
   have two people judge the stem share in a salad and in a sauce.
2. Thyme and rosemary: freezer for 15 min, shake in a jar for 20 s, sieve through a 5 mm colander; weigh
   leaves, stems and stem fragments. Compare with 5 min and 30 min of freezing.
3. Kale and chard: a 12 mm V-notch sawn into a plastic cutting board; pull force with a luggage scale.
4. Cauliflower and broccoli, 3 heads each: cone cut with a paring knife at 25°, count florets that fall
   free, weigh crumbs.

### 2.5 Fallback

Frozen chopped herbs, frozen florets, frozen chopped kale (MEAL-012 a): no loss under MEAL-002. Under
MEAL-009 the 9 STR meals would fall out; fresh herbs are needed for garnish and for DM32 Grüne Soße in any
case [R2], which GP-21 covers.

---

## 3. G6 — Deseed and core non-axial produce

### 3.1 Scope by ingredient

COR is in 50 meals: bell pepper 26, apple or pear only 18 (axial, solved by SM-040/-041), tomato 10,
cucumber 4, chilli 2, avocado 2, savoy cabbage 2 (core, see G7), pumpkin 1. PIT is in 3 (avocado 2, fruit
salad 1). The pepper is the gap. Only DM13 (stuffed peppers) needs the pepper hollow and whole.

Pepper anatomy: a hollow shell with 3–4 lobes. The seeds sit on a placenta that hangs **under the stalk**,
25–40 mm long, Ø 25–35, joined to the wall by 3–4 white ribs. The stalk is not on the body axis; offsets
of 5–15 mm are normal. A die centred on the body therefore misses (the 70 % of B:N20); a tool centred on
the stalk does not.

### 3.2 Candidates (pepper)

| ID | Mechanism | Physics and numbers | Vision | Cleaning | Conf. |
|---|---|---|---|---|---|
| **GP-61** | **Stalk-seeking plug corer.** A thin tube Ø 42 × 0.8 mm with a fine serrated rim and an internal cone that captures the stalk. The pepper stands in a shallow nest in which it can slide ±15 mm. The tube descends with ±30° oscillation; the cone pushes the pepper sideways until the stalk is centred; the rim cuts the shoulder and the upper rib roots to 30 mm depth. The plug (stalk, calyx, placenta, most seeds) is held in the tube by the stalk wedged in the cone and is pushed out over waste by an ejector pin. Then the pepper is inverted and rinsed with the fan jet for 2 s. | Plunge 30–50 N [E]; 8 s plus rinse; plug 12–18 % of mass [E]; seeds left after rinse ≤ 5 [E]; ribs remain (cosmetic); rotating-tube pepper corers are industrial practice [K] | Coarse: stalk up within ±20° and ±15 mm | Tube with cone and ejector: one open-ended stainless part plus a loose pin → wash chamber; no blind hole if the cone is a three-spoke insert | **M–H** |
| GP-62 | **Four cheeks.** Pepper stalk-up; four vertical chord cuts at 0.28 D from the stalk axis slice the walls off the seed pillar, which is left standing with the stalk and is discarded; the base is cut off and recovered. | Any knife, 20–40 N; 15 s; yield 65–75 % [E]; few seeds ever touch the cheeks; tolerant of an off-centre core because the cuts pass outside it [K, cook's method] | Coarse: stalk position | Knife and board | **H** for strips and dice (24 of 26 pepper meals); not for stuffed peppers |
| GP-63 | **Cap cut, pull, flush** (SM-042, round 1). Part off the cap 12 mm below the shoulder, pull it with the core, flush. | The ribs hold the placenta to the wall, so the core tears off the cap in about a third of peppers [E] | Stalk axis and shoulder height | Knife, jet | M |
| GP-64 | **Cut first, screen the seeds** (SM-043). Top the pepper, dice, tumble-rinse on a 6 mm screen. | Seeds are 3–4 mm discs and pass; placenta pieces stay in the food (white, slightly bitter) | Coarse: the stalk still has to come off | Screen basket | M; quality below GP-62 |
| GP-65 | **Corer-wedger die** (SM-041) centred on the body. | 70 % [E, B:N20] | None | Die | L–M; superseded by GP-61 |

```
 GP-61 plug corer, section                            GP-62 four cheeks, top view

        | shank, ejector pin inside                         cut 1
      __|__                                             .-----|-----.
     |  |  |  tube Ø 42, serrated rim                  /   .--+--.   \
     | /^\ |  three-spoke cone captures the stalk  cut 4--|  core |--cut 2     cuts at 0.28 D
     |/ | \|                                           \   '--+--'   /          from the stalk
    ..\_|_/..  <- shoulder of the pepper                '-----|-----'
   /  ( : )  \    placenta and seeds inside the tube        cut 3
  |   ribs    |
   \_________/   pepper free to slide ±15 mm in a shallow nest
```

### 3.3 The other items

| Item (meals) | Mechanism | Conf. | Note |
|---|---|---|---|
| Apple, pear (18) | Tube corer Ø 22 with ejector, or corer-wedger (SM-040, SM-041) | H | Axis from the stalk cavity; same shank as GP-61 |
| Tomato (10) | **GP-66**: small and medium tomatoes are not cored (scar core Ø < 8 mm, edible). Beef tomatoes: the GP-61 tool in Ø 14, 8 mm deep, on the stalk scar. Tomatoes for stuffing: cap cut and a spoon-loop on a spindle | H (skip) / M (gouge) | The scar has to be found by camera; tomatoes do not settle scar-up |
| Cucumber (4) | Cut into 100 mm lengths, push each through a ring with a Ø 18 centre tube (axial case); or do not deseed for salad, and grate and squeeze for tzatziki | H | |
| Chilli (2) | **Not deseeded**: slice into rings with seeds and reduce the recipe quantity by about 30 % | H | Standard practice; capsaicin is kept away from a tool that would be hard to rinse |
| Pumpkin, squash (1) | **GP-67 roast first**: Hokkaido whole at 180 °C for 40–50 min, halved soft (20 N instead of 150–400 N raw [E]), the seed mass lifted out in one piece with a spoon tool, flesh scooped. For raw cubes: buy frozen | M (adapted method for soup) | Raw halving of a Ø 200 pumpkin exceeds most cell force budgets |
| Avocado (2–4) | **GP-68**: blade to the stone while the fruit turns, twist the halves, three-prong stab and twist for the stone, loop scoop along the skin. Six steps, each ripeness-dependent | L | Honest answer: **buy avocado pulp or frozen halves**; guacamole from pulp is acceptable |
| Mango | Two cheek cuts at ±11 mm from the flat plane of the stone (yield 60–65 % [K]), flesh pressed out of the cheek through a 12 mm grid | M | Not in the corpus as COR/PIT; listed for completeness |
| Cherry, plum, olive (≤ 1) | Plunger pitter per fruit [K] | H as a device | Not worth a tool: buy pitted, jarred or frozen |

### 3.4 Recommendation

One **tube family on one shank** — Ø 14 (tomato scar, strawberry hull), Ø 22 (apple, pear, cucumber
segment), Ø 42 (pepper) — each with the same ejector pin, plus the rule set "chilli with seeds, small
tomato uncored, pumpkin roasted first, avocado as pulp". GP-62 (four cheeks) is kept as the zero-hardware
method for cut pepper and as the recovery when GP-61 misses. Custom parts: 3 tubes (turned and wire-eroded
or from bought cutters), 1 pin.

Cleaning: the tubes are open at both ends and are sprayed through; the plug never stays in the tool
because the ejector clears it after every piece. Seeds and rinse water go through the 2 mm waste strainer.

### 3.5 Bench experiment (under 25 €)

Ten blocky peppers and five pointed ones. A Ø 40–45 stainless pastry cutter or a piece of thin-walled
tube filed to a saw edge; a cone made from a funnel pushed inside. Pepper on a wet plate (slides freely).
Measure: does the stalk centre itself, does the plug come out whole, seeds left after a 2 s rinse, mass of
the plug. In parallel, four-cheek cuts on five peppers: yield and seed count. Pass: plug whole in ≥ 8 of
10 blocky peppers, ≤ 5 seeds after rinse.

### 3.6 Fallback

Frozen pepper strips (soft, cooked dishes only [R2]), tinned tomatoes, cored apple rings: no loss under
MEAL-002 **except DM13 stuffed peppers**, where ready-stuffed peppers are forbidden and a cored fresh
pepper is not a retail product: DM13 would take one of the 4 reserve meals. Under MEAL-009 the 26 pepper
meals fall out (raw pepper in salads SA01, SA07, SA10 also loses quality with frozen strips). Avocado as
pulp: 2–4 meals leave MEAL-009, none leaves MEAL-002.

---

## 4. G7 — Whole cabbage leaves for Kohlrouladen; lettuce leaves

### 4.1 The problem

DM12 needs 8–12 intact, pliable leaves of savoy (or white cabbage), about 200 × 250 mm. Raw leaves are
crisp and crack when bent; they are joined to the stalk by a thick base and overlap each other by more
than half a turn. The traditional method is to cut out the core, blanch the whole head in a 6–8 L pot
and take the leaves off one by one as they soften. Pre-blanched leaves are a forbidden purchase
(MEAL-012), so this single meal has no fallback. Only the outer 10–12 leaves are large enough; the heart
is chopped into the braise, as in the home recipe.

### 4.2 Candidates

| ID | Mechanism | Physics and numbers | Vision | Cleaning | Conf. |
|---|---|---|---|---|---|
| **GP-71** | **Freeze–thaw instead of blanching, then hydraulic release.** The head is frozen whole (or a savoy is kept in the freezer as a stock item), thawed in the fridge or in the steam oven at 60 °C. Ice crystals rupture the cells; the leaves become limp as if blanched [K, home practice]. The core is cut out as a cone (GP-25 blade, Ø 60 × 60 mm). Head core-up on a spike; mains water runs into the core hole at 0.1–0.2 L/s and fills the pocket between the outermost leaf and the next; the leaf folds outward and drops onto a tray or mat. Head turned a little after each leaf. | Freezing a 1 kg head: 12–20 h [E]; thawing 24–36 h at 5 °C or 25–40 min at 60 °C in steam [E]. Pocket pressure ρ g h at 0.1 m = 1 kPa on 200 cm² = 20 N opening force on a limp leaf [C]. 3–5 s per leaf, 10 leaves in about 1 min, 10–15 L of water. No 8 L blanching pot, no BLA step | Coarse: core side | Spike and tray are ware; water through the strainer to drain | **M**: the freeze–thaw effect is known; the hydraulic release is untested [U] |
| GP-72 | **Steam the cored head**, 10–12 min at 100 °C in the oven, then release as in GP-71 or by a silicone finger stroking from the apex down; return the head to the steam after 4–5 leaves. | Heat front in 10 min: √(α t) ≈ 9 mm [C], i.e. about 4–6 leaves per cycle; two or three cycles | Coarse | As above | M; more handling of a hot, wet head |
| GP-73 | **Blanch whole in the large pot** (traditional, C §7.2). | 6–8 L of water, 12–15 min to boil at 3.5 kW, head Ø 200 turned and lifted while hot | Coarse | Pot | M–L; the large pot, the hot lift and the repeated return are the cost |
| GP-74 | **No whole leaves**: layered cabbage and mince in a dish (Schichtkohl). | — | — | — | H as cooking; but it is a different dish, DM12 is then not covered |

```
 GP-71, head core-up after freeze–thaw
                 water 0.1–0.2 L/s
                     |
               ______v______
             .'   .-----.   '.         the pocket between leaf 1 and leaf 2 fills;
   leaf 1  /    /  cone   \    \       leaf 1 is free at its base (core removed)
   folds  /    |  cut out  |    \      and folds outward under about 20 N
   out <-'      \         /      '
                 '-.___.-'
                     |  spike into the apex (the heart is chopped later)
   ==================+==========  tray / mat catches the leaf flat
```

After separation the thick midrib is flattened with the pounding tool or a roller (UO-20 hardware,
1–2 kN/m line load [E]) so that the leaf rolls; the wrap itself is SM-079/-080.

### 4.3 Lettuce and other leaf heads

| ID | Mechanism | Conf. |
|---|---|---|
| **GP-75** | **Butt cut and wash.** One cut 15–25 mm above the butt (butterhead, romaine, lamb's-lettuce rosettes, pak choi); the leaves are then free and separate by themselves in the dunk basket of GP-W1. Iceberg: cone-cut the core (GP-25 blade), then chunk-cut. Romaine for Caesar salad: cross-cut into 30 mm strips from the tip, stop 25 mm before the butt | **H** [K, cook's method]; needs only "which end is the butt" |

### 4.4 Recommendation, experiment, fallback

Recommended: GP-71, with GP-72 as the variant when the meal was not planned two days ahead and no frozen
head is in stock. GP-75 for lettuce.

Bench experiment (under 10 €): two savoy heads and one white cabbage. Freeze one savoy for 24 h, thaw
overnight, cut the core out with a paring knife, hold it core-up under the kitchen tap. Count the leaves
that come off whole, time per leaf, tears. Repeat with a head steamed for 10 min and with a raw head
(expected to fail by cracking). Roll three leaves round 80 g of mince and braise for 45 min to see whether
thawed leaves behave like blanched ones.

Fallback: none that is permitted. If GP-71 and GP-72 fail, DM12 falls out and takes 1 of the 4 reserve
meals of MEAL-002 (section 5.4 of the requirements); savoy as a side dish is not affected.

---

## 5. G10 — Trim small items in quantity

### 5.1 Scope by ingredient

TRE is in 31 meals. Long goods (carrot 11, leek 4, zucchini 4, asparagus 3, spring onion 2) are solved by
fence or probe cuts (SM-037, SM-038). The small-item part is: mushroom 10, green beans 4, strawberry 2–3,
Brussels sprouts 1, radish 1 — about 18 meals (7 %).

### 5.2 First question: is the trim needed at all?

| Item | Trim in a home kitchen | Rule proposed (GP-101) | Meals |
|---|---|---|---|
| Cultivated mushrooms | 2 mm off the dry stem end | **None.** Sold with the stem already cut; the dry end is edible. Wipe or 5 s rinse, slice whole | 10 |
| Radish | Leaves and root tail | Buy topped (bag). The tail is edible: no trim. With leaves: one cut, GP-102 | 1 |
| Brussels sprouts | 2 mm off the base, loose outer leaves, cross-score | No base trim (sold trimmed at harvest); loose leaves come off in the wash basket; halve instead of scoring | 1 |
| Green beans | Stem end off; tail optional | Tail stays. Stem end: GP-103 or buy frozen | 4 |
| Strawberries | Calyx off | Must be done for cakes and fruit salad: GP-102 | 2–3 |

Ten of the 18 meals need no mechanism. This is a recipe-database decision, not hardware.

### 5.3 Candidates

| ID | Mechanism | Physics and numbers | Vision | Cleaning | Conf. |
|---|---|---|---|---|---|
| **GP-101** | **Do-not-trim rules** (table above). | — | — | — | **H** |
| **GP-102** | **Camera-indexed single cut.** Pieces are spread on a board; the camera finds the green calyx, leaf stub or pale base disc; the piece is pushed so that the end overhangs the board edge or sits under the blade; one cut. Strawberry: cap cut 4–5 mm below the calyx, or the Ø 14 tube of the corer family plunged 8 mm (hull and core). | 3–4 s per piece [E, D-manipulator]; 500 g of strawberries = 25–30 berries = 1.5–2 min; 500 g of sprouts = 30 pieces = 2 min; cut 5–15 N. Loss 8–12 % for a cap cut, 4–6 % for the tube [E]. Green on red is the easiest segmentation there is | **Yes** | Knife, board or tube: ware | M–H up to about 40 pieces; too slow for beans (80–100 pieces × 2 ends = 5 min and more) |
| GP-103 | **Shaftless snipper drum** for beans (SM-039 made as loose ware). A perforated stainless basket Ø 220 × 150 with 6 × 12 mm slots countersunk from inside, turning at 30–40 rpm on the spin-basket drive inside a fixed shell that carries one blade bar 0.4 mm outside the basket. Bean ends poke through and are cut. | 500 g in 2–3 min; 85–92 % of ends removed [E; industrial 90–95 % K]; loss 6–10 %; ends fall into the shell, which is the waste pan | No | Basket, shell and blade bar are three loose parts → wash chamber. The slot edges are the soil trap | M as a mechanism; **not recommended**: three custom parts for 4 meals |
| GP-104 | **Vibrate, align, fence-cut.** Beans in a V-trough vibrated 30 s until they lie lengthwise, pushed against an end fence, one cut 8 mm from the fence; then pushed to the other fence if both ends are wanted. | Curved and crossed beans stay misaligned: 70–85 % of ends [E]; 1 min | No | Trough and knife | M–L |
| GP-105 | **Cut into 30–40 mm pieces, do not trim.** | Stem nubs (3–4 mm, slightly woody on modern stringless beans) stay in the dish | No | — | H as a process; quality risk under MEAL-015 |

### 5.4 Recommendation, experiment, fallback

GP-101 everywhere it applies; GP-102 for strawberries, sprouts with a bad base and radishes with leaves;
**green beans are bought frozen and trimmed**, which is what most households do and is rated acceptable for
cooked dishes [R2]. GP-103 is kept on file for a later "fresh beans" upgrade.

Bench experiment (under 10 €): (1) blind tasting of mushrooms sliced with and without the stem-end trim,
and of sprouts cooked with and without base trim; (2) 30 strawberries on a white board under a phone
camera: threshold on green, measure how often the computed cut line is within ±2 mm of a hand-marked one;
(3) GP-104 with 300 g of beans in a length of roof gutter on a sander or phone vibration: count aligned
ends.

Fallback cost: frozen beans and frozen sprouts are permitted (MEAL-012 a); MEAL-002 unaffected. MEAL-009
loses the 4 bean meals (5 with sprouts) if no bean mechanism is built. Strawberries have no good frozen
substitute for a fresh cake topping: without GP-102 they are served with the calyx (garnish) or the 2–3
meals are adapted.

---

## 6. Peel potato and carrot robustly (irregular shapes, eyes)

### 6.1 Comparison of the three families

PLP is in 60 meals (potato 39, carrot 31). PRP-022: ≤ 5 % of the surface with peel, loss ≤ 25 %;
PRP-023: 1.5 kg washed, peeled and cut in ≤ 10 min.

| Family | Loss | Time for 1.5 kg | Irregular shapes | Eyes | Cleaning | Noise |
|---|---|---|---|---|---|---|
| Abrasive drum or disc (SM-049, SM-050) [K] | 12–25 %, grows with time | 2–3 min, batch | good (tumbling reaches convex areas; hollows stay) | remain; about 10 eyes × 20 mm² = 2 cm² of 150 cm² = 1.3 % of the surface [C], inside PRP-022 | one drum or liner as ware; starch slurry and peel to the strainer | 65–72 dB(A) [E] |
| Blade on a spit (SM-046) [K] | 15–20 % | 10–12 tubers × 20 s = 3.5–4 min, one at a time | poor on kidney shapes and knobs; 5–10 % chucking retries | missed; hollows missed | blade and prongs | low |
| Cook in skin, then slip or rice (SM-055, SM-056) [K] | 3–6 % | no peeling time; cooking as the recipe | any | skin comes out of eyes and hollows because it is loosened everywhere | the ricer plate holds the skins | none |
| Skin-on, scrubbed | 0–1 % | 1 min | any | remain, visible | brush or knurled roller | low |

### 6.2 Candidates

| ID | Mechanism | Numbers | Vision | Conf. |
|---|---|---|---|---|
| **GP-P1** | **Route by recipe.** Mash, boiled potatoes (as Pellkartoffeln, slipped), potato salad, Bratkartoffeln, dumplings from cooked potatoes, gnocchi: cook in skin, then slip in a rubber-stud tumble with water for 30–60 s, or rice. Wedges, oven fries, new potatoes, stews with waxy potatoes, all carrots: scrub skin-on. Only gratin, raw-grated dishes (Puffer, Rösti from raw, raw dumplings) and peeled fries go to GP-P2. | Covers about 30 of the 39 potato meals and all 31 carrot meals [E, by dish type]; boiled-then-slipped Salzkartoffeln count as adapted (MEAL-013) and are tossed in salted butter to make up for unsalted cooking | No | **H** |
| **GP-P2** | **Knurled-steel drum, stopped by camera.** Drum liner or floor disc with a rolled diamond knurl (no bonded grit, nothing to shed), spray on. A camera looks through the lid at the tumbling batch and stops when the brown fraction is below 5 % of the visible surface or the loss budget (by weight of the drum) reaches 20 %. | 1–1.5 kg, 60–150 s, loss 10–18 % instead of 25 % with a fixed timer [E]; eyes stay and stay within PRP-022 | For the stop only; a timer works without it | M–H |
| GP-P3 | **Steam pulse, then rub.** 4–5 min in atmospheric steam, then the rubber-stud tumble. The skin loosens in hollows and eyes too. | Heat front √(α t) at 5 min = 6.5 mm, gelatinised ring about 2–3 mm [C]; loss 5–8 % [E]. Not raw any more at the surface: fine for fries, gratin, stews; not for raw-grated | No | M; atmospheric steam needs minutes where industrial 15 bar steam needs seconds [R4] |
| GP-P4 | **Spit and blade plus camera-guided gouge for eyes** (SM-046 + SM-044). | 25–35 s per tuber; a vision skill per defect | Yes | M; rejected as the default: slowest, most software, worst on ugly tubers |
| GP-P5 | **Carrot: scrub only**, or the iris peeler (SM-048) when a recipe insists. | Scrub loss < 2 %; iris 8–12 % | No | H / M |

### 6.3 Recommendation, experiment, fallback

GP-P1 as the rule, GP-P2 as the one peeling device. The blade lathe is not needed for potatoes; a concept
that has a spit anyway may use it for apples, kohlrabi and citrus (section 7). Eyes are left: they meet
PRP-022 by area. Green or sprouted tubers are a rejection rule for the camera, not a peeling task.

Bench experiment (60–90 €): a household rumbler-type electric potato peeler (1 kg class). Peel 1 kg
batches of smooth, of knobbly and of old potatoes; stop every 20 s, photograph and weigh. Plot residual
skin against loss: this gives the stop rule and shows whether 5 % residual skin is reached below 20 %
loss on knobbly tubers. In parallel (no cost): steam 5 tubers for 3, 5 and 8 min, rub with rubber gloves
under the tap, weigh, cut open and measure the cooked ring.

Fallback: vacuum-peeled potatoes (2–4 weeks chilled, sulphited, boiling types only, 2–3 × the price [R2]),
permitted: no loss under MEAL-002. Under MEAL-009, GP-P1 alone recovers about 50 of the 60 PLP meals
[E]; the remaining raw-peeled dishes need GP-P2.

---

## 7. Peel citrus and zest

Lemon is in 33 meals (juice in 7 by JUI; zest is part of fine grating), orange in 4 (peeled in 3).

| ID | Mechanism | Physics and numbers | Vision | Cleaning | Conf. |
|---|---|---|---|---|---|
| **GP-Z1** | **Spin against a fine rasp.** Fruit on a two-prong spit (any axis; the holes do not matter because it is juiced afterwards) at 60 rpm; a curved photo-etched rasp is pressed on with 2–4 N and traverses pole to pole once. | Flavedo is 1–2 mm thick; at 2–4 N the rasp takes 0.3–0.5 mm per pass [E, K for hand zesting], so one pass cannot reach the white pith; 2–4 g of zest per lemon; 15 s. 20–30 % of the zest clings to the rasp [K]: it is rinsed off with the recipe's own liquid or juice | No (force limit, one pass) | Rasp is ware; citrus oil needs the alkaline wash | **H** |
| GP-Z2 | **Rasp cup.** The fruit is tumbled for 20–30 s in a Ø 120 cup lined with a fine rasp, under a lid, on the spin drive (industrial oil-rasping principle [K]). | No chucking; zest stays in the cup and is flushed out with liquid; depth not controlled, time is the only limit | No | One cup | M |
| GP-Z3 | **Channel zester or peeler blade with a 1 mm depth shoe** on the spit: strips for garnish or candying. | 5–10 N | No | Tool | M–H |
| **GP-Z4** | **Pare to the flesh** (cook's "à vif"): top and tail, then the GP-11 shoe-and-blade with 5–6 mm protrusion traverses the turning fruit and cuts peel and pith away; the fruit is then sliced into rounds. | Loss 30–35 % [K]; 20 s; gives rounds, not membrane-free segments | Top face after the cut gives the peel thickness | Blade, prongs | M |
| GP-Z5 | **Score four meridians 5 mm deep and pry the peel segments off** with a wedge. | Leaves pith on the fruit | — | — | L; pith remains |

Recommendation: GP-Z1 for zest, halving and a reamer for juice (SM-036), GP-Z4 for the three meals that
want peeled orange. Membrane-free segments are not offered [R4 section 15].

Bench experiment (under 10 €): lemon on a fork in a cordless drill, a fine hand zester held against it
with a kitchen scale underneath to read the force; count passes until white shows. Orange: pare with the
5 mm blade block of the onion test.

Fallback: bottled lemon juice and no zest, or dried zest; tinned mandarin for fruit salad. No coverage
loss; a flavour loss in cakes and desserts that a MEAL-015 tasting would notice.

---

## 8. Wash gritty produce (leek, spinach, lamb's lettuce)

### 8.1 Physics

Grit is quartz sand, 0.1–0.5 mm, density 2650 kg/m³. In air it is held to a wet leaf by capillary force;
under water that force is gone and only mechanical trapping in folds remains. Settling velocity in still
water [C]: 0.1 mm grain 9 mm/s (Stokes), 0.3 mm about 40 mm/s. Leaves are near neutral buoyancy and move
with the water. So: **loosen under water, let the sand fall through a perforated floor into a quiet sump,
and take the leaves out upward** — never pour the water off through the leaves (cook's rule [K]). A spray
in a spinning basket (SM-159) does not reach into a rosette and throws loosened sand onto the leaves
lying at the wall.

### 8.2 Candidates

| ID | Mechanism | Numbers | Vision | Cleaning | Conf. |
|---|---|---|---|---|---|
| **GP-W1** | **Dunk basket over a sediment trap, turbidity-terminated.** Perforated basket (Ø 5 mm holes) in a vessel with 40 mm of free depth below the basket floor. Fill with 3 L of cold mains water, plunge the basket 20 times at 1–1.5 Hz and 50 mm stroke, rest 10 s, lift the basket out, dump the water through the strainer. Repeat until a dishwasher turbidity sensor in the dump line reads below the threshold (usually 2 baths, 3–4 for lamb's lettuce). Then spin-dry. | Relative flow 0.15–0.3 m/s in the stroke [C]; a 0.3 mm grain falls the 40 mm in 1 s and through the holes; 6–12 L of water and 1.5–3 min per 200–300 g; spin 2 × 15 s at 40–110 g to ≤ 5 % adhering water [R4] | No | Basket and vessel are the existing wash/spin ware (SM-159); the sensor sits in the drain line, outside the food zone | **H** |
| GP-W2 | **Air-bubble bath** (industrial leaf washer [K]). | Sparger plate and air pump; gentler on leaves | No | The sparger is a wet, perforated part with an air line: a hygiene item | M; more parts than GP-W1 for no gain at this batch size |
| GP-W3 | **Flume with weir and sand trap** (SM-162). | Continuous flow 0.2 L/s | No | A channel to clean | M–H; larger than needed |
| **GP-W4** | **Leek: cut first, wash afterwards.** Trim root and dark green (two fence cuts), slice into rings or halve lengthwise, then GP-W1. The soil sits between the sheaths and is released only when they are opened. | One bath is usually enough once the rings are open [K] | No | — | **H** |
| GP-W5 | **Lamb's lettuce: cut the root stub** (GP-75) so that the rosette falls into single leaves before GP-W1. | Sand sits at the root crown; open leaves wash in 2 baths instead of 4 [E]. Rosettes arrive loose, so there is no bulk cut: one camera-indexed cut per rosette (GP-102), 40–60 rosettes per 200 g, which is too slow; default is whole rosettes and 3–4 baths | Yes, per rosette | — | L–M |

```
 GP-W1
        | plunge 50 mm, 1–1.5 Hz
     ___v_______________
    |  |  leaves     |  |     water line
    |  | ~~~~~~~~~~~ |  |
    |  |_o_o_o_o_o_o_|  |     basket floor, Ø 5 holes
    |    .  .   .  .    |     40 mm quiet zone: sand settles here and stays
    |___________________|     when the basket is lifted out
             |  dump → turbidity sensor → 2 mm strainer → drain
```

Recommendation: GP-W1 with GP-W4; whole rosettes of lamb's lettuce get up to 4 baths. Washing does not
make raw salad safe: water alone gives about 1 log reduction [R4], so the food-safety rules for raw
produce (FSF) stand as they are.

Bench experiment (under 15 €): a salad spinner (basket and bowl), 200 g of field-grown lamb's lettuce and
one leek. Add 1 g of fine sand to make it a worst case. Count baths until a white bowl shows no sediment;
then chew-test. Compare with a hand shower in the spinning basket.

Fallback: bagged ready-washed salad and lamb's lettuce, frozen leaf spinach, cut leek (MEAL-012 a): no
coverage loss; shelf life of bagged salad is 3–5 days.

---

## 9. Coverage accounting (MEAL-002, MEAL-009, MEAL-012)

MEAL-009 allows 24 of 248 meals to be not preparable from whole produce. The 8 meals already excluded
(requirements 5.4) count against it, so **16 meals are free** for produce operations that are not built.
Meals overlap between rows; the sum is an upper bound.

| Operation group | Meals at stake | Built as recommended | Left to purchase (leaves MEAL-009) |
|---|---|---|---|
| PLA onion | 112 | GP-11 | 0 if the bench test passes; **112 if not** |
| PLA garlic only | 17 | GP-17 | 0 |
| COR pepper | 26 | GP-61, GP-62 | 0 |
| COR apple, pear, tomato, cucumber, chilli | 34 | tube family and rules | 0 |
| COR / PIT avocado, pumpkin raw, stone fruit | 4–6 | roast-first for pumpkin | 3–5 (avocado pulp, pitted fruit) |
| STR | 9 | GP-21, -22, -25, -26 | 0–1 |
| LSP | 1 | GP-71 | 0 (but no fallback: MEAL-002 reserve) |
| TRE small items | 18 | GP-101, GP-102 | 4–5 (frozen beans, sprouts) |
| PLP | 60 | GP-P1, GP-P2 | 0 |
| Citrus, gritty wash | — | GP-Z1, GP-W1 | 0 |
| **Sum left to purchase** | | | **7–11 of the 16 free** |

Reading: MEAL-009 is within reach if, and only if, onion peeling works. Everything else on the produce
side can be built from known practice or waived within the budget. MEAL-002 is touched by only two meals
in this document, because only they have a forbidden or missing purchase form: DM12 Kohlrouladen (LSP)
and DM13 stuffed peppers (hollow cored pepper).

New custom parts for all recommended mechanisms together: blade with shoe (2 protrusions), finger comb,
three corer tubes with one pin, notch plate, angled core blade, knurled liner — 9 parts, all stainless or
moulded silicone, none printed (DECISIONS 4).

---

## 10. Open issues

1. **Nothing here is tested.** The onion numbers (85–90 % first pass, ≥ 95 % with re-pass, 18–25 % loss)
   are estimates. The test of 1.6 costs 20 € and half a day and should run before round P3 closes,
   because MEAL-009 depends on it alone.
2. Onion: the friction values of 1.2, the share of onions that lose the first fleshy scale at 2.5 mm, and
   the behaviour of freshly harvested (moist-skinned) and of red onions are unknown. The camera criterion
   "skin against flesh" is easy for yellow onions and uncertain for red ones, where the flesh is also
   purple.
3. Onion: doubles and shallots carry skin inside the bulb. No external peeler removes it. Whether a thin
   internal membrane counts against "≥ 95 % skin-free" (UO-12) needs a ruling.
4. Axis finding for onion, pepper, cabbage and tomato is assumed to be done by the host (camera and
   regrasp). Its success rate multiplies into every figure here and belongs to the concept documents.
5. GP-12 (passive cassette) would make onion peeling independent of any rotary axis, but it is the least
   certain variant. It should be tested right after GP-11 with a cardboard-and-spring mock-up.
6. Salzkartoffeln cooked in the skin and slipped are counted as an adapted method. If the customer wants
   them peeled raw, GP-P2 has to carry all 39 potato meals and the 10-minute target of PRP-023 becomes the
   drum's task.
7. Freeze–thaw cabbage needs the meal to be planned about two days ahead or a frozen savoy in stock; this
   is a request to the planner and the storage design. Texture after braising compared with blanched
   leaves is unverified.
8. The "do not trim" and "do not deseed" rules (mushroom, radish, sprouts, chilli, small tomato, bean tail)
   are recipe-database decisions and need a MEAL-015 tasting before they are counted.
9. Waste: onion skins, pepper plugs, cabbage cores and peel slurry add up to 100–400 g per meal. The 2 mm
   strainer and its emptying are assumed, not designed here.
10. Requests to the architect: bunches stowed aligned and banded in a long box; a turbidity sensor in the
    preparation drain line; a fan-jet nozzle on a valve at the preparation position; a freezer slot for one
    whole cabbage head.
11. Celeriac, kohlrabi, asparagus and ginger (PLH, 18 meals) were not part of this task; cut-away peeling
    (SM-059) stays the only proposal.

## 11. Risks

| Risk | Consequence | Likelihood | Mitigation or test |
|---|---|---|---|
| Onion segments do not fall after three slits (wet-film adhesion larger than assumed) | GP-11 fails; MEAL-009 out of reach | medium | Test 1.6 run 1 and 3; GP-13 and GP-14 as second candidates; batch peeling allows retries |
| Slit depth varies with loose tunics, so that the first fleshy scale is always cut through | Loss rises to 38 % per onion | medium | Accept (5 cents per onion) and size the onion stock at 1.4 kg per kg; or read the tunic thickness on the top face and set the depth |
| Wet onion skins cling to tools and pan | Skin fragments carried into food | medium | Dry wipe before any water; work over a dedicated waste pan; camera check of the onion before it leaves |
| Camera check passes an onion with skin left | Skin in the dish, a MEAL-015 defect | low–medium | Threshold tuned on red onions; default to the 5 mm re-pass when in doubt |
| Pepper plug tears and leaves the placenta inside | Seeds in the dish | medium | Camera looks into the cavity; GP-62 four cheeks as recovery; rinse |
| Stalk-seeking cone does not centre lying or pointed peppers | GP-61 works for blocky peppers only | medium | Pointed peppers: halve lengthwise and jet |
| Thawed cabbage leaves tear when released or when rolled | DM12 falls out (1 of 4 reserve meals) | medium | Test 4.4; GP-72 steam variant |
| Do-not-trim rules rejected in tasting | 10 mushroom meals need GP-102 at 3–4 s per piece | low | Tasting early; GP-102 exists |
| Knurled drum leaves deep-eyed old potatoes above 5 % residual skin before 20 % loss | PRP-022 missed on bad tubers | medium | Camera stop rule; route such batches to cook-in-skin |
| Gritty salad passes the turbidity test with sand still in the rosettes | Grit on the plate | low–medium | Threshold from the bench test; GP-W5 root cut; bagged washed salad as default for lamb's lettuce |
| Citrus oil and onion odour stay on silicone parts | Taint (HYG-025) | medium | Silicone parts kept to the comb and wiper; alkaline wash at 60 °C or more; spare set |
| Blade roots of the shoe tool and the corer serrations hold soil | HYG-020 failure | low–medium | One-piece parts, rinsed within 2 min of use, washed as ware after every session |
| The number of special tools grows (9 custom parts here) | Storage, handling moves, cost | medium | All are passive and small; the corer family shares one shank; the snipper drum and the blade lathe are deliberately not built |
