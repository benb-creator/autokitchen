# K4b — Shuttle mat, improved (round P5a)

Round P5a improvement of K4 (`design/prep/concepts/K4-shuttle-mat.md`) after the critiques C1–C5, following
`00-improvement-brief.md`. Inputs: the K4 document, the K4 findings and round-2 recommendations of C1–C5, the
decision matrix, the other concept documents (K1, K2, K3, K5, K6, K8; K7 is out by #27), the catalogue, the
gap documents G-produce and G-assembly-meat, the finished K1b, K2b, K5b, K6b, K8b, DECISIONS #1–#28.
Nothing was built or tested. Tags: **[C]** calculated here, **[E]** estimate, **[K]** known practice
(product, trade or cook's method), **[U]** unverified, **[D]** from a concept document, **[Cn]** from
critique Cn. Coordinates: X along the wall from the left inner wall, Y from the inner face of the back wall
towards the door, Z from the room floor; all mm.

**Core idea kept:** food that must be laid flat, rolled, wrapped, sliced, shingled or carried is worked on a
washable mat that comes out of the machine, is driven only by rotating shafts, lies under a top camera as a
plain background, and goes back in through a wash gate minutes after use. **What changed most:** the mat
no longer does everything. It is two solid silicone bands that hang in their own slots (never wound for
storage) and are steamed and dried there; nothing cuts on it any more — a straight-stroke blade cuts past its
nose onto a loose anvil stick; one arm replaces K4's two; and a single turning, pressing, heating position P1
next to the mat gives the cell what K4 lacked: yaw, plunge and a lathe. **26 → 9 actuators, 22 → 4 dynamic
seals, 10 → 1.7 m² of mat surface, oven out of the cell.**

## 0. Brainstorm

Notes written while reading each concept, each idea with a quick verdict (*take* / *maybe* / *reject*); 0.1
adds the own ideas, 0.2 the final pick (some early *take*s were later replaced by a better route, as noted there).

Charges to fix (C1–C5 on K4): no yaw/no plunge (C1 K4-1 fatal as whole kitchen); release of dough/mince
from silicone untested (C1 K4-2, R1); 10 m² fabric-cored mat stored wound and damp (C2 K4-1); raw-meat
disinfection of K covers 5 % (C2 K4-2); gate water ×10 (C2 K4-3); shared blade/table/cheeks R↔RTE (C2 K4-4);
cutting mat scored (C2 K4-5, C3 K4-3); oven above hobs at head height (C2 K4-6, C3 K4-4, C4 K4-1); mat arm
28 mm thin, 2–5 mm bar skew, mat walks (C3 K4-1 fatal as drawn); zero depth margin (C3 K4-2); mats
€570/yr vs €300 all wear parts (C4 K4-2); 26 actuators, 22 rotary passages, 8 novel (C5); one serial line
(C3 K4-5); 300–900 strokes uncounted (C4 K4-5); Bratkartoffeln ploughed 15 min (C1 K4-3); apple core in red
cabbage (C1 K4-4); no core probe (C1 K4-5); gravy without roasted onion/paste (C1 K4-6); mash gluey (K4-7);
mince stewed (K4-8). Hard limits (C5 / matrix 6.1): ≤ 10 actuators, ≤ 5 seals, ≤ 2 novel, ≤ 70 events.

**From K1 (ceiling turret):**
- Fixed press ram + die cassettes between two hands; cup on a turntable under it as a 2-station carousel →
  K4 needs exactly this plunge: a press over P1's turntable (dice, garlic, ricer, corer, Spätzle). *take, as
  a press on the turntable position*
- Arm C of K4 already has X–Z + roll about Y; with the turntable under it, a vertical push by arm C reaches
  every point of a vessel (polar) → probe, corer, press plate, ladle can be arm-C tools. *take*
- Spit + sprung peeler (lathe) → for K4 a back-wall spit along Y is "a rotary shaft through one wall";
  corkscrew spit pulls produce on by rotation only (no linear seal). *maybe (one more drive)*
- Roll head = passive wrist that is ware → K4's arm C bar spin already is a wrist; tools are ware. *take*
- Jet gate: tool spun in a fixed fan for a rinse between two foods → rinse for the mat-arm bar / tools. *maybe*
- Loose silicone mat in a tray rolled with a pin (K1 ROL) = the cheap alternative to the whole mat line;
  K4b must beat it on sheets larger than a tray, rolls and wraps. *note (benchmark for K4b's worth)*

**From K2 (vessel stack):**
- Press column standing on a hob with an annular turntable (K/H): dice, rice, knead, whisk in the cooking
  pot → K4's P1 (turntable + spindle under the nose) becomes the one "force and speed" position. *take*
- Grid/disc clipped on a turning receiving vessel under a stationary feed sleeve (food-processor principle
  inverted): P1 turns the disc, the mat nose drops produce into the sleeve → slicing/grating without a blade
  landing on the mat. *take as option for slicing/grating*
- Load pins in the grip: every transfer weighed → arm shoe with a load cell. *maybe*
- Rim-to-rim inversion, grease by spin, flour by tumbling, induction release pulse for unmoulding. *take
  (pulse + spin-grease on P1)*
- Paste cartridge (piston barrel) pushed by the press → K4 had no paste dosing; the press on P1 can push it.
  *maybe*
- Kits: stalk tools hang in their lids → fewer moves. *take for the arm's tools*

**From K3 (drum and belt):**
- **Overhang guillotine**: the blade passes just in front of the nose and never touches the belt; belt
  advance = slice thickness → K4's CHOP moves from "blade lands on mat K over a soft anvil" to "shear at the
  table edge": no scoring, no cutting mat K, no UHMW-PE disinfection problem (C2 K4-2, K4-5; C3 K4-3).
  *take — the key cutting change*
- **Dancer loop** on the return strand and a **pocket** made by releasing slack between two rollers → the
  mat store can be a gravity dancer instead of five motor reels; loop slack comes from the dancer, not a
  2-link arm. *take (dancer store)*
- Homogeneous fabric-free belt (no fabric core) → a solid silicone mat is possible when the tension is low
  and constant (dancer). *take*
- Cutter cartridges (bought vegetable-cutter disc + grid in a cage, top-driven) fed by the nose, dice fall
  into the pot below → P1's spindle drives the same cartridge; replaces slab–strip–chop (R4). *take*
- "Order on the belt = order in the stack": burger/sandwich laid item by item by the nose onto a plate
  → answers C1's "no stacking" for K4. *take*
- Rumbler: knurled floor disc in a turning vessel + stationary scraper in the charge = commercial disc
  peeler → replaces rasp mat R on the P1 turntable. *take*
- Breading without flip: flour bed, egg on a rocked tray, nose crawls under the cutlet onto a crumb bed.
  *maybe (K4's own LOOP breading is similar)*
- Tail scraper and chute: first/last slices and surplus flour leave at the far end, away from vessels. *take*

**From K5 (ram and die):**
- Press with loose tube, piston and dies (ricer, Spätzle, garlic, corer-wedger, former, slot die) → K4's
  spindle crank at P1 already moves a head 300 mm up and down; with a self-locking worm drive it can push
  ≈ 1 kN: the **spindle head becomes a light press head** (ricer, garlic cup, corer, Spätzle, paste piston)
  without a new actuator; dicing (3–8 kN) stays with the cutter cartridge. *take*
- Paste cartridge (small tube with piston) stored cold, metered by the ram → mustard/tomato paste dosing,
  K4's weakest intake form. *take (cartridge pushed by the head)*
- Slot die 120 × 2 for mustard ribbons → spread on a Rouladen slice lying on the mat. *maybe*
- Rotating round positions with ring drive; scraper hung on the rim held by a rear post; rasp can on a
  rotating position. *take (P1/P2 turntables, rasp/knurl insert)*
- Diverter to a chip box: first/last slice and cores never cross food. *take (tail of the mat = waste side)*
- Loose-floor moulds for unmoulding. *take (ware)*
- Frying book: two drives, two seals by fat. *reject (C5)*
- K5's own wish list names K4's mat as the sheeting/rolling/wrapping module (11.3). *note: the value K4b
  must keep*

**From K6 (loose ware, fast washer):**
- Form-fit tang with conical pins instead of an EPM shoe (C3 rank 5) → K4's arm cannot close a chuck, but
  a dovetail with a sprung pawl released by fixed cams at every set-down place gives the same positive lock
  without an actuator. *take*
- Workpiece on a fork, blade fixed (peeler post) → **inverted for K4**: the produce turns on a spit on the
  P1 turntable, the crank head is the tailstock, the arm (X–Z) carries the sprung peeler from pole to pole —
  a vertical lathe from three existing axes. Peel potato, apple, kohlrabi, celeriac, cucumber; cap a pepper;
  cone-cut a cabbage core. *take (answers C1 "no yaw, no plunge" and #25)*
- Corer-wedger end plate, ricer, Spätzle plate, garlic plate on a press tube → all under the crank head. *take*
- One manipulator, serial work, everything else passive (S-min) → **one arm for mat and vessels** instead of
  K4's arms B and C: −3 actuators, −3 seals. *take*
- Wash-as-you-go wells; turning positions with umbrella-capped roller posts (no contact seal). *take the
  turntable sealing; washer stays outside the cell (shared bought washer)*
- Sink = produce wash + waste port → basket in the P1 bowl for washing; waste through a dump port. *take*
- Batch by tool (two Rouladen per stroke, all patties in one cycle). *take as planning rule*
- Silicone apron with two hem bars as loose ware (K6's own Rouladen set) = a manual copy of K4's LOOP:
  confirms the principle; K4b keeps it fixed and washed in place. *note*

**From K8 (sealed tub, magnetic puck):**
- **Canned radial couplings in welded thimbles** (T 25 Nm, S 6000 rpm, no seal) → P1 gets a coaxial slow
  turntable T and fast hub S under the deck with zero dynamic seals; P2's turntable the same. *take*
- Force from torque inside a closed ware cassette (screw press 2.5 kN from 12 Nm) → for K4b the vertical
  crank head is simpler; the screw cassette is the fallback if the head's worm drive is too weak. *maybe*
- Slide vessels across a flush deck (24 N for 12 kg) instead of lifting → the arm pushes pots between P1–P3
  with its shoe; no 8 kg lift at full reach. *take*
- Jet gate with the manipulator as conveyor → the arm holds a soiled tool in a fixed fan for a rinse. *take*
- Enclosure of the frying zone (C2) → a lid on every frying pan and an extraction slot behind the hob row;
  a full partition is impossible because the arm crosses. *take (partial)*
- Planar motor, gap modulation, skid friction. *reject (not K4's principle)*
- K8b's household hob under-mounted with its own control replaced (DEC-28) → plain position P3 can be a
  bought hob zone; P1/P2 stay custom because of the thimbles. *maybe (cost rounds)*
- K8b's T-lathe and portion scoop (disher) for round Frikadellen (R-10) → same lathe idea as from K6;
  disher on the arm for balls. *take*

**From the gap documents and the other round-2 drafts:** GP-17 garlic press cup, GP-61 plug corer and
GP-62 four cheeks, GP-25 cone cut, GP-P1 cook in skin and rice, GP-P2 knurled drum, GP-W1 dunk basket,
GP-Z1/Z4 zest and pare (all *take*: they need a plunge, a slow rotary axis and a free X–Z tool, which K4b
now has); GA-01 peel lay-down = K4's NOSE (*take*); GA-04 plough rails (*take*, as ware); GA-08 fold and
crimp (*take*); GA-09 ridge tray for ravioli and square turnovers (*take*); GA-11 inject jam after steaming
(*take*); GA-20 hairpin raft (*take*); GA-36 lift-rack turn (*take*); GA-24 shear dealer (*maybe*, see N27).
K1b/K8b canned wrist coupling (*take* for the bar joint). Oven outside in an oven column served by the
transport, as K1b, K2b, K8b (*take*).

### 0.1 Own new ideas

| # | Idea | Verdict |
|---|---|---|
| N1 | **Hanging dancer store**: each mat hangs as a U-loop around a weighted dancer roller in a 55 mm slot under the table; constant 25 N tension, no reel motor, never wound in storage | **take** (−5 actuators, −5 seals, answers C2 K4-1) |
| N2 | **Wash on retraction, then steam and hot air in the closed slot**: the whole hanging mat, both faces, 60 s of saturated steam (A0 > 1 000 s) and 5 min at 65 °C | **take** (answers C2 K4-1, K4-2) |
| N3 | **Solid platinum silicone mat, no fabric core**, possible because the dancer keeps the tension at 25 N (strain about 3 %) | **take** (no wicking, no fray, one-piece moulded: C2 R-9) |
| N4 | **Guillotine at the table edge**: a straight-stroke blade on a pull-down column lands on a loose anvil stick (ware) just past the nose; nothing cuts on the mat | **take** (no cutting mat, no scoring) |
| N5 | **Catch bar G** 65 mm below the anvil: the cut product falls onto the moving mat, which shingles it and carries it to the nose; trimmings go to the dump by the same nose | **take** |
| N6 | **Driven capstan nose E** (canned drive): positive feed for the blade, a running loop for rolling, and autonomous slicing into a pocket while the arm works elsewhere | **take** (+1 actuator, 0 seals) |
| N7 | **One arm, two ends**: the bar carries the hem key slot along its length and a dovetail shoe with an electro-permanent magnet at its root | **take** (replaces arms B and C) |
| N8 | **Vertical lathe at P1** from three existing axes: turntable = headstock, press head = tailstock, arm = tool post moving in Z and X | **take** (generic peeling #25, cone cut, parting, avocado) |
| N9 | **Rolling pin with gauge rings carried by the arm** on the stationary mat; thickness from the rings, not from arm stiffness | **take** (removes the roller arm) |
| N10 | **Disher on the arm** for Frikadellen, dumplings and cookie dough, released against a fixed post, flattened by the pin | **take** (round, hand-like shape; independent of mat release) |
| N11 | **Order on the mat = order in the stack** (K3) with lay-down onto a plate on P1 | **take** (burger, toast) |
| N12 | Two mats only: **S** (raw meat, odorous) and **D** (dough, ready-to-eat, cooked) | **take** (K, R, P dropped) |
| N13 | ENVELOPE no longer a general primitive; kept as the **page-turn fold** (cordon bleu, turnovers) | **take** |
| N14 | **Polar plating** on the P1 turntable (ladle arc, nose lay-down, disher) | **take** |
| N15 | **Press-peel**: banana pieces pushed out of their skin ring; avocado and cooked pumpkin halves pressed skin-up through a grid | **take** (#25, CK16, MX06, SP07) |
| N16 | **Plough rails as ware**, dropped into two sockets at the table edges, fold the side margins before the loop | **take** |
| N17 | Mat as one long two-zone band instead of two mats | reject: the store would need 1.2 m of height |
| N18 | Magnetic rodless carriage for the blade (K3 principle, no seal) | maybe: K9b option; force-limited (≈ 600 N derated), novel |
| N19 | Paper interleaf from a roll over mat S (K4 6.6) | reject as baseline (consumable); fallback if release fails |
| N20 | Pasta-roller cassette on the S hub | reject: feeding and take-off need a second hand |
| N21 | Two cuts with a 90° turn plate for meat cubes | reject (slow); meat bought diced (#8) or cut into bite pieces |
| N22 | In-cell wash well (K6b type) sharing the mat wash core | maybe: option +360 mm, see 2.7 |
| N23 | Passive box cradle tilted by the arm via a lever; lids removed outside the cell (C5 A1, Q7) | **take** (−3 dock actuators) |
| N24 | Egg spoon on the arm + passive blade-and-spread cracker struck by the press (G-assembly 7.2) | **take** (−3 egg actuators) |
| N25 | Retard fingers on the table as a "mat dealer" for shingled meat slices | maybe (L–M); baseline: interleaved packs or own slicing |
| N26 | Spin-coated pancakes and vortex-poached eggs on P1 | **take** |
| N27 | Lid on every frying pan, extraction slot behind the hob row (partial K8 containment) | **take** |

### 0.2 Picked

The concept keeps K4's mat and its primitives SHUTTLE, LOOP, NOSE, SLING and the cut at the table edge, and
rebuilds everything around them: N1–N16, N23, N24, N26, N27; from the others the canned couplings (K8), the
pull-down column press with swing (K6, K7), the turning positions with hung tools (C3 rank 1), the vertical
lathe (K6/K8b inverted), the tube corers, ricer, Spätzle and garlic plates (K5/K6), the order-on-the-belt
stack and overhang cut (K3), GA-01/-04/-08/-09/-11/-20/-36, the G-produce set, the oven column (K1b, K2b,
K8b). Rejected: wound mats, cutting on the mat, five mat types, the second arm, the roller arm, the dock and
egg modules, turntables at every position, the oven above the hob.

---

## 1. What changed and why

Effect columns: **S** simplicity, **H** hygiene, **C** coverage and food result, **R** reliability and
mechanics, **F** system fit (cost, width, wear, power). ++ / + / 0 / − against K4.

| # | Problem (reference) | Change in K4b | S | H | C | R | F |
|---|---|---|---|---|---|---|---|
| 1 | **No yaw, no plunge**: no apple coring, garlic press, Spätzle, heads, stacks; G-produce modules not hostable (C1 K4-1 fatal; matrix 2.3 "donor") | Position **P1** = turntable T (yaw) + canned fast hub S + 3 kW induction + **pull-down swing press 2.5 kN** (plunge); the arm is an X–Z tool post. Gives the vertical lathe, tube corers, ricer, Spätzle and garlic plates, press-peel, polar plating, probe placement (3) | 0 | 0 | ++ | + | + |
| 2 | **Everything depends on release** of dough and mince from silicone (C1 K4-2, K4 R1) | Kneading and mince mixing in the bowl on P1 against a hung roller (Ankarsrum [K]); Frikadellen by disher; sheeting by a ring-gauged pin on a floured, stationary mat; the mat carries only floured, wetted or oiled items, as a cook's board does | + | 0 | + | + | 0 |
| 3 | **10 m² of fabric-cored mat stored wound and damp** (C2 K4-1, R-9) | **Two solid silicone mats** (S raw/odorous, D dough/RTE), 280 × 1 550 × 2, no fabric; each **hangs in its own slot** on a passive dancer, is washed on retraction, **steamed and hot-air dried in the slot** | ++ | ++ | 0 | + | + |
| 4 | **Raw-meat disinfection of mat K covers 5 %** (C2 K4-2) | No cutting mat. Mat S is steamed over 100 % of its length (A0 > 1 000 s, [C] 5.3); the blade is steamed in its park; the anvil stick is ware | + | ++ | 0 | 0 | 0 |
| 5 | **Gate water under-counted ten-fold** (C2 K4-3) | Budget from nozzle flow × time: 2.6 L per retraction, 9–13 L per meal for mats and fixed parts (5.4) | 0 | 0 | 0 | 0 | − (honest) |
| 6 | **Blade, table, cheeks, bar shared by raw and RTE** (C2 K4-4) | Cheeks gone; food never touches the table (the mat lies on it); anvil sticks red/green as ware; the blade and its fingers get a steam park; raw work on mat S only | + | + | 0 | 0 | 0 |
| 7 | **Cutting mat scored, UHMW-PE consumable** (C2 K4-5, C3 K4-3) | Nothing lands on a mat: the blade lands on an anvil stick (POM, €10, ware) past the nose | + | + | 0 | + | + |
| 8 | **Oven hung over the hobs at head height**, no human access (C2 K4-6, C3 K4-4, C4 K4-1) | Oven leaves the cell: household 60 cm oven with automatic door (#24) in an oven column at normal height, served by the transport (as K1b, K2b, K8b) | + | + | 0 | + | + |
| 9 | **Thin arm cannot keep the mat tracking**, 2–5 mm bar skew (C3 K4-1, fatal as drawn) | One arm with 50 mm links instead of two 28 mm ones; mat tension 300 → 25 N (dancer); mat 400 → 280 wide: skew ≤ 0.3 mrad [C] 2.3 | + | 0 | 0 | ++ | 0 |
| 10 | **Zero depth margin** (C3 K4-2) | Mat 280 wide, gallery 65, drive room 90: 22 mm margin plus 10 mm rear allowance (2.1) | 0 | 0 | − (sheets ≤ 280 wide) | + | + |
| 11 | **Mats €570 a year** against €300 for all wear parts (C4 K4-2, C3 K4-3) | Two mats at ≈ €80 every 2–3 years, four anvil sticks a year: ≈ €90 a year (6.1) | + | 0 | 0 | + | ++ |
| 12 | **26 actuators, 22 rotary passages, 8 novel** (C5; K4 §7) | **9 actuators, 4 dynamic seals, 2 novel** (6.2): arm 3, capstan nose 1, blade column 1, press column 1, T, S, T2; dancer, cradle, egg fixture, gate lips passive | ++ | + | 0 | ++ | + |
| 13 | **Two arms that cannot pass; one serial line** (C3 K4-5) | One arm by design (C5 Q2); the capstan nose slices into a pocket while the arm works elsewhere; turntables stir and knead unattended | + | 0 | 0 | + | 0 |
| 14 | **300–900 mat strokes uncounted** (C4 K4-5) | No chopping on the mat, no shuttle-sheeting; 40–90 mat strokes per meal, counted with their failure modes (6, 9) | + | 0 | 0 | + | 0 |
| 15 | **Bratkartoffeln ploughed for 15 min, sliced hot** (C1 K4-3) | Potatoes boiled in skin early and cooled, slipped, sliced 5 mm at the blade, fried in the wide pan, turned every 4 min by the turner (C1 10.3 rule 3) | 0 | 0 | + | 0 | 0 |
| 16 | **Apple eighths with core in red cabbage** (C1 K4-4) | Apple on the lathe: pared, then corer-wedger under the press | 0 | 0 | + | 0 | 0 |
| 17 | **No core probe** (C1 K4-5, A-5) | Wireless probe set by the arm; the pan turns on T until the piece is under the probe line | 0 | 0 | + | 0 | 0 |
| 18 | **Gravy without roasted onion and paste; mince stewed** (C1 K4-6, K4-8, A-2) | Sequence rules of C1 10.3 in the recipe format: sear, remove, roast onion and paste in the fond, deglaze; mince first in the wide hot pan | 0 | 0 | + | 0 | 0 |
| 19 | **Mash by flat beater, gluey** (C1 K4-7) | Ricer plate under the press, skin-on potatoes, skins stay on the plate (GP-P1) | 0 | 0 | + | 0 | 0 |
| 20 | **Schnitzel in 1.3 mm of fat** (C1 A-3) | 250 mL in a 28 cm pan (4 mm), turned by the lift-rack pair GA-36, fried last (A-4) | 0 | 0 | + | 0 | 0 |
| 21 | **Burger, toast, hot dog rated L** (C1 K4-1) | Order on the mat = order in the stack; nose lay-down onto a plate on P1; W-rack for the hot dog (GA-03) | 0 | 0 | + | 0 | 0 |
| 22 | **"Liquids need a second machine as large as the first"** (K4 12.1-4) | The cooking side is the minimum every concept has (three positions); P1 is prep and cook station at once; the mat line adds 400 mm of width and one drive of its own | + | 0 | 0 | 0 | + |
| 23 | **Dock 3 and egg module 3 actuators** (C5 A1, A2) | Passive box cradle tilted by the arm through a lever; passive blade-and-spread egg cracker struck by the press | ++ | 0 | 0 | + | + |
| 24 | **A dropped hem behind the table needs a human** (K4 §9, C3 K4-5) | Hems park in forks on top of the table; nothing can fall behind it (the slots are closed below the gate) | 0 | 0 | 0 | + | 0 |
| 25 | **Zone S 8.3 m², hob open to the mat bay** (C2 K4-7, K4 12.2-12) | Lids on frying pans, extraction slot behind the hob row, fixed nozzle plan: 4.6 m² of zone S washed per meal | 0 | + | 0 | 0 | 0 |


---

## 2. The improved concept

### 2.1 Definition in one page

K4b is a stainless wash-down cell **1400 mm wide, 600 deep, 2100 high** with three zones side by side:

* **Mat line (X 0–520).** A 400 × 300 table at Z 1100. Two solid silicone mats, **S** (raw meat, odorous
  food) and **D** (dough, ready-to-eat, cooked food), each 280 × 1 550 × 2 mm, hang in their own 55 mm slots
  under the left end of the table, each as a U-loop round a 5 kg dancer roller (25 N constant tension). The
  active mat comes up through its gate (sprays, squeegee), over its L bar, across the table and over the
  **driven capstan nose E** (Ø 20, X 405). Just past E lies a loose **anvil stick** on which a straight-stroke
  **blade** lands; the blade hangs from a pull-down **blade column** in the front strip. 65 mm below the anvil
  the fixed **catch bar G** turns the mat towards the arm, so everything the blade cuts falls onto the moving
  mat. The free end of the mat (the hem) is held by the bar of the **arm**.
* **Work and cooking row (X 515–1360).** Three induction positions on one deck at Z 820: **P1** (3 kW,
  turntable T 0–600 rpm and fast hub S 0–12 000 rpm, both canned through the deck, load cells, and the
  **pull-down swing press** 2.5 kN in front of it), **P2** (2.5 kW, slow turntable T2), **P3** (3 kW,
  plain, load cells). A dump funnel with strainer lies in the deck between the anvil and P1, under the catch
  pocket.
* **One arm** on the back wall (shoulder X 700, Z 1520; two closed links of 420 mm in the gallery Y 8–58).
  Its bar (Ø 40, along Y) carries the hem key slot along its length and, at its root, a dovetail shoe with an
  electro-permanent magnet that takes every piece of ware by its tab. The arm draws and parks the mats,
  forms loops and delivers by the nose, carries and tilts vessels, presses the rolling pin, holds the peeler
  on the lathe, works the passive box cradle, plates.

Seven primitives remain; four are K4's, three are new:

| Primitive | What moves | Used for |
|---|---|---|
| SHUTTLE (K4) | capstan E feeds the mat, the dancer takes it back | carry food to the blade at exact steps; bring it back onto the table |
| CUT (new form of K4's CHOP) | blade column lands on the anvil stick past E | slices 1–40 mm, shreds, rings, strips, halving heads, trimming, portioning logs and sheets, carving; product falls onto the mat and is shingled |
| LOOP (K4) | arm pays out, E and the bar run together | rolling Rouladen, wraps, sponge roll, Maultaschen; tumbling; catching cut product (pocket) |
| NOSE and SLING (K4) | arm holds the hem over a target and winds | lay-down into P1–P3, onto trays and plates, into the dump; stacks in order |
| PIN (new) | arm rolls a ring-gauged pin over the stationary mat | sheeting dough 1–10 mm, flattening cutlets and slices, pressing crumbs, spreading dots of paste |
| PRESS and LATHE at P1 (new) | press column, turntable, arm as tool post | dice, rice, Spätzle, garlic, corers, press-peel; pare, core, cone-cut, zest, halve round a stone |
| TURN (new for K4) | T, T2, S under the deck | stir under hung scrapers, knead, whisk, blend, spin salad, spin-coat pancakes, poach, plate in polar coordinates |

Liquids are dosed into cups and vessels, never onto a mat (as K4). Water comes from a fixed spout over each
position. The oven is **not** in the cell (2.7).

```
 FRONT VIEW (door removed; Z above the floor; X from the left inner wall; outer width 1400 = 20 + 1360 + 20)

 Z
 2100 +------------------------------------------------------------------------------------------+
      | camera C1 over table and P1      lights      camera C2 over P2, P3, port   extraction duct |
 1950 |                                                                                          |
      |                                  (sh) arm shoulder X 700, Z 1520; links 420 + 420        |
 1450 |[box]--lever--.                                                                           |
      |[GN ]  \      |              ||<- blade column (front strip, X 445)                       |
 1230 |cradle  pour edge X 170      ||  blade parked Z 1380   ||<- press column (front, X 655)   |
      |              v              ||                        ||   swing arm parks along X       |
 1100 |=L_S===L_D======= TABLE ====(E)[anvil]                 ||                                 |
      |  |S |  |D |  gates: spray,  |  blade lands at X 430    ||                                 |
 1035 |  |  |  |  |  squeegee     G(o)~~~~~~~~~o pocket fork X 520                                |
      |  |  |  |  |                  \_______/      .-------.      .-------.      .-------.       |
      |  |  |  |  |  wash core:       catch pocket  |  pot  |      |  pot  |      |  pan  |       |
  960 |  |  |  |  |  pump, boiler 8 L,              |  P1   |      |  P2   |      |  P3   |       |
  820 |  |()|  |()|  steam gen. 2 kW, [dump funnel]=[T+S, 3 kW]===[T2, 2.5 kW]==[ 3 kW ]=== deck  |
      |  |  |  |  |  sump 3 L, dryer  [strainer]   induction modules, canned T/S/T2 drives,      |
  230 |  +--+  +--+  fan and heater                 column drives, load cells, drain             |
    0 +------------------------------------------------------------------------------------------+
      X: slot S 5-60 | slot D 65-120 | table 0-400 | E 405 | anvil 421-439 | funnel 440-510 |
         P1 655 (rim 515-795) | press column 655, front | P2 935 | P3 1215 | right wall 1360

 TOP VIEW at table level (Z 1100). Y from the inner face of the back wall towards the door.

  Y
  480 +== door, glass in a frame, interlocked (outer face) ======================================+
  445 |  front strip Y 375-445: blade column (o) X 445; press column (o) X 655 with swing arm    |
  375 |  +--------------------------------+E  anvil                                             |
      |  |S| |D|   TABLE 400 x 300       (o)[=]    .--P1--.   .--P2--.   .--P3--.              |
      |  |m| |m|   mat 280 wide, beads     |  ^     | T  S |   |  T2  |   |      |  right port  |
      |  |o| |o|   (food never touches     | blade  | Ø280 |   | Ø280 |   | Ø280 |  Z 880-1120  |
      |  |u| |u|   the table itself)       | X 430  '------'   '------'   '------'              |
   65 |  +--------------------------------+G below E; vessel centres at Y 220                   |
      |  gallery Y 0-65: arm links Y 8-58, shoulder cartridge X 700; bearings of E, G, L        |
    0 +== back wall 3 mm: arm cartridge, canned drive of E (no slot, no linear seal) ===========+
  -93 |  drive room 90 (dry): arm motors, E servo, controller                                  |
 -103 +-- rear installation allowance 10 -------------------------------------------------------+
      box port in the left wall (Z 1230-1450); ware and plate port in the right wall (Z 880-1120)
```

Depth budget: rear installation allowance 10 + drive room 90 + back wall 3 + gallery 65 + mat zone 310
(mat 280 at Y 80–360, beads and clearance) + front strip 70 + door 35 = 583, **margin 17 mm** plus the 10 mm
allowance (C3 K4-2 asked for both).

### 2.2 The mat line

**Mats.** Solid platinum-cured silicone, 70 Shore A, 2.0 mm, 280 wide, 1 550 long, one-piece moulded with a
convex edge bead on the food face (4 high, 5 wide, root fillets R 2.5, no undercut) and a hem of the same
material moulded round a Ø 8 stainless rod (the rod is fully enclosed; no pocket). At 25 N the strain is
0.7 % [C: 25 N / (560 mm² × 6 MPa)], so a fabric core is not needed. No blade lands on a mat. Coloured edge
marks (two-colour moulding, flush) every 50 mm let camera C1 measure the actual feed. Expected life 2–3 years
[E]; replacement 2 min without tools (2.8).

| Mat | Food | Never |
|---|---|---|
| **S** | raw meat and fish, mince, breading, Rouladen, cordon bleu, raw filling for Maultaschen | dough for baking, ready-to-eat food |
| **D** | dough and pastry, washed produce for raw use, cooked food (roast, potatoes), cheese, bread, assembly | raw meat; unwashed produce (class R, washed first in the P1 basket) |

**Stores.** Each slot is a closed 1.4404 box, 55 × 300 × 770 (X × Y × Z), from Z 230 to 1000 under the left
end of the table, drain at the bottom, warm-air inlet at the bottom, outlet at the gate. The mat is anchored
at the top of the slot's left wall, hangs down round the dancer (solid Ø 50 × 300 roller, 5 kg, ends guided
in vertical grooves of the slot's end plates by PEEK sliders) and rises to the gate. The dancer travel of
650 mm stores up to 1.5 m (the whole mat when its hem is parked) and lets up to 1.3 m out. **The mat is never wound for storage**; both faces hang in air.

**Gate** (at the slot mouth, Z 1000–1090, sequence seen by a point of the mat on retraction at 50 mm/s):
scraper lips (gross soil falls back onto the table and is rinsed off later), cold pre-rinse (3 flat-fan
nozzles per face), detergent at 60 °C recirculated from a 3 L sump through a strainer (3 per face), hot rinse
85 °C (3 per face), squeegee lips. All lips are always closed and flexible enough to pass the hem; no gate
actuator. A small mirror and LED let camera C1 see the back face as it comes out.

**In-slot steam and drying.** After a class R use, or once a day for mat D: steam from the 2 kW generator
fills the closed slot (lips closed, drain trap) until the slot sensors read ≥ 95 °C for 60 s
(A0 ≈ 60 × 10^1.5 ≈ 1 900 s for the whole mat, dancer and slot) [C]; then 65 °C air at 30 m³/h for 4 min dries
it. The mat hangs dry until its next use.

**Table and bars.** Table plate 1.4404, 400 × 300 × 5, 1.5° cross fall to the gallery gutter; two mouths for
the mats with fixed L bars (Ø 16, polished); the hem of S parks in a fork on top at X 70, the hem of D in a
recess flush with the table at X 130 (mat S passes over it). **E**: Ø 20 stainless roller driven through a
canned magnetic coupling in the back wall (≈ 2 Nm, 120 N pull at 25 N back tension) [E], front end in a PEEK
bush in the front strip. **G**: fixed Ø 16 polished bar at X 409, Z 1035, so that the mat drops almost vertically from E to G.
The mat normally runs **E → G → bar**: whatever passes the nose drops 65 mm onto the moving band — cut product,
pieces, cutlets, Rouladen slices entering the loop. Only sheets that must stay flat (dough, pasta) take the
direct path from the top of E down to the bar at ≤ 25°; for that the arm first lifts the anvil stick out
(one event).

**Blade and anvil.** Blade beam 90 × 12, 1.4116 blade edge 300 long, inclined 8° in Y (39 mm rise) for a
draw cut, cantilevered 325 mm from the top of the blade column; deflection under 800 N at the far end
0.06 mm [C]. Blade plane X 430; a one-piece sprung finger comb (6 leaf fingers, 1.4310) on the product side
reaches 30 mm below the edge and holds the product down with 5–20 N before the edge arrives. The edge lands
on the **anvil stick** (POM-C 18 × 12 × 300, in a groove bracket X 421–439, 4 mm clear of the mat that drops from E, top at Z 1100), which is ware with
a tab (two red, two green). Column: Ø 40, pull-down through the deck, ball screw below the deck, 1 kN,
stroke 300, 250 mm/s; landing detected by motor current. About 2 cuts per second on a 40 mm product.

**Catch pocket.** For cutting without the arm, the hem is parked in a fork at X 520, Z 1040 (brackets on the
back wall and the blade column). E then feeds the mat, which sags between G and the fork into a pocket above
the dump funnel; everything the blade cuts falls 60–70 mm into it. The pocket holds about 400 mm of mat
(two cucumbers of slices, a cabbage half of shreds). The arm comes back later, takes the hem and delivers.

### 2.3 The arm: one arm, two ends

Two closed welded 1.4404 links, 420 and 420 mm, 50 (Y) × 100 × 2 box section, in the gallery (Y 8–58). One
coaxial cartridge through the back wall (shoulder 150 Nm; elbow 80 Nm through a belt inside the upper link
and a planetary stage at the elbow; bar spin 15 Nm through two belts) with one lip seal Ø 90 at the wall; one
lip seal Ø 60 at the elbow; the bar is driven through a **canned magnetic coupling** at the wrist (no seal
next to the mat; K1b, K8). All motors in the dry room.

**Bar.** Ø 40 × 2 tube from the wrist (Y 30) to Y 375. A key slot along Y 70–375 takes the hem rod (half a
turn wraps the mat over it, the capstan holds it [K4]). A UHMW-PE doctor lip on the forearm wipes the mat
before it winds. At the root (Y 40–95) the **shoe**: a vertical dovetail slot with an electro-permanent
magnet (400 N nominal). Every piece of ware has a ferritic dovetail **tab** 30 × 40 on the side that faces
the back wall; the shoe slides over it from above. The dovetail holds the item positively in every upright and
tilted attitude up to 90°; the magnet adds 400 N (rated 200 N with a fat film) only for inversion (pan pair,
lift rack, unmoulding). Payload 8 kg at 800 mm reach.

**Stiffness for tracking** [C]. Out-of-plane moment from the mat at 25 N on a 190 mm lever: 4.8 Nm (10 Nm
with transients). Twist of one link: M L / (G J) with J = 6.1 × 10⁵ mm⁴ → 9 × 10⁻⁵ rad; lateral bending of
both links with I = 2.6 × 10⁵ mm⁴ → 8 × 10⁻⁵ rad; joints 5 × 10⁻⁵ rad. Total ≤ 0.5 mrad at 10 Nm, i.e.
≤ 0.15 mm over the 280 mm of mat width, against 4–10 mrad in K4 (C3 K4-1) and the 1 mm/m rule for belts.
Edge guidance by the flanges of L, E and G remains as a second line.

**Collision rules.** The bar never passes under the parked blade beam below Z 1300 or above an open vessel
on P1 while the press swings; the press column and the blade column stand in the front strip, in front of
the bar's tip (Y 375), so the bar and the mat pass them freely.

### 2.4 Stations P1, P2, P3

**P1 — work and cook position** (centre X 655, Y 220). Glass-ceramic insert with a Ø 75 central hole over a
3 kW ring coil (OEM module, #5); in the hole two coaxial deep-drawn thimbles: **T** (Ø 70, 12-pole magnet
coupling, 15 Nm, 0–600 rpm) and **S** (Ø 36, 1.5 Nm, 0–12 000 rpm). Ware sits on a loose spider (three
arms, centring dogs) that rides on T's bell; S drives the rotor of the blender jug or the whisk rotor through
the jug floor. Three 10 kg load cells under the P1 sub-frame (±2 g). A one-piece hung tool (kneading roller
with scraper, or stirring scraper) hooks onto two pegs on the back wall and stands in the turning bowl or pot
(Ankarsrum principle [K], C3 rank 1).

**Press** (pull-down swing column, K6/K7 structure, C3 rank 3). Column Ø 40 at X 655, Y 400 (in front of P1's axis), through a
raised boss in the deck with scraper, drained lantern and dry seal; ball screw and servo below the deck;
2.5 kN, stroke 250; in the top 25 mm a helical cam swings the 180 mm arm through 90°: in work it points along
−Y to P1's axis, parked it points along +X inside the front strip, never above a vessel. The arm ends in a plain Ø 100 pressure plate. **The press holds no
tools**: the arm places the tool on the work (piston in the tube, corer on the apple, tailstock cup on the
produce), and the plate pushes it. Deflection at 2.5 kN ≈ 2 mm [C, as K6].

**P2** (X 935): 2.5 kW coil with a Ø 60 hole, T2 thimble (15 Nm, 0–120 rpm), peg pair for a hung scraper.
**P3** (X 1215): 3 kW coil, plain, load cells; takes the 28 cm frying pan and the braiser.

Power: P1 + P2 + P3 managed to ≤ 5.6 kW on two phases (C4 9.1); boiler (3 kW) and steam generator (2 kW) heat
only while the coils are below 3 kW together; the oven is on its own phase in the oven column.

### 2.5 Actuators and seals

| # | Actuator | Drive | Rating | Seal in the splash zone |
|---|---|---|---|---|
| 1 | Arm shoulder | servo + planetary, coaxial cartridge | 150 Nm | lip seal Ø 90 at the wall (one for the three coaxial shafts) |
| 2 | Arm elbow | servo in the dry room, belt in the upper link, planetary at the elbow | 80 Nm | lip seal Ø 60 at the elbow |
| 3 | Bar spin | servo, two belts | 15 Nm, 0–200 rpm | none: canned coupling at the wrist |
| 4 | Capstan nose E | servo 200 W | 2 Nm | none: canned coupling in the back wall |
| 5 | Blade column | ball screw, servo under the deck | 1 kN, 300 mm, 250 mm/s | rod seal (scraper, drained lantern, dry seal) |
| 6 | Press column with swing | ball screw, servo under the deck, helical cam | 2.5 kN, 250 mm + 90° | rod seal (same) |
| 7 | P1 turntable T | stepper + planetary under the deck | 15 Nm, 0–600 rpm | none: canned |
| 8 | P1 hub S | BLDC 800 W | 1.5 Nm, 0–12 000 rpm | none: canned |
| 9 | P2 turntable T2 | geared stepper | 15 Nm, 0–120 rpm | none: canned |

**9 motion actuators, 4 dynamic seals.** Switched devices, not counted: the EPM in the shoe, about 12
valves, wash pump, boiler heater 3 kW, steam generator 2 kW, dryer fan and heater, extraction fan, three
induction modules. Passive: two dancers, gate lips, box cradle (tilted by the arm through its lever, on a
6 kg load cell), egg cracker (struck by the press), catch fork, plough rails, disher release post.

### 2.6 Ware

Every item carries the dovetail tab; vessels carry three dogs for the spider. B = bought, M = bought with a
welded tab, C = custom (laser-cut, bent, turned, welded).

| Group | Items | Qty | Make |
|---|---|---|---|
| Cooking | pot 6 L Ø 240 with lift-out basket; pots 4 L Ø 220 (2); sauce pots 1.5 L Ø 160 (2); frying pans Ø 280 shallow, a flip pair with drip skirt (2); braiser Ø 280 × 100 with lid; lids (5) | 13 | M |
| Mixing | bowl 5 L Ø 260 with wash/spin basket; blender jug 1.5 L with canned blade rotor and whisk rotor; kneading frame and stirring scraper for the pegs (2); knurled peel disc for the 6 L pot | 8 | M / C |
| Press set | stand; tube Ø 90 × 120 with plain and comb piston; plates: grid 10 and grid 6 (two-tier, bought push-dicer blades), ricer 3, Spätzle 6, corer-wedger 8, grid-skin 10, press-peel ring Ø 34 with plunger; small tube Ø 40 with garlic plate 2 mm and nozzle (also the paste cartridge); tube corers Ø 14/22/42 with ejector; crimp frame; ridge tray | 18 | C (grids, plates bought where possible) |
| Lathe set | spike base with dogs; tailstock cup with PEEK thrust face; sprung peeler with three depth shoes (1, 2.5, 5 mm); paring and parting knife; zester rasp; avocado cup pair | 6 | C / M |
| Arm tools | wide turner; lift-rack pair (GA-36); ladle 150 mL; spoon-scraper with moulded lip; dishers Ø 50 and Ø 35; rolling pin Ø 50 × 300 with ring sets 1/2/4/6/10 mm; pastry-wheel gang (pitch 50/100); sifter cup; wide-lip trough cup 250 mL; cups 50 mL (2) and 1 L; egg spoon; probe holder with wireless probe; plough rails (pair); hairpin raft fork with comb cradle | 20 | C / M |
| Bake and serve | baking trays 400 × 300 (2); gratin dish 300 × 200; loaf tin and springform 26 with loose floors; W-rack; platters Ø 300 (2); egg cracker cassette and slotted saucers (2); anvil sticks (2 red, 2 green); waste bowl | 15 | B / M |

**About 80 pieces of about 50 types** (K4: 36 + 5 mats; the growth is the press, lathe and tool set that
the critics asked for). A 4-person meal uses 15–25. Custom part types: about 42 (cell assemblies about 14, custom ware about 28).

### 2.7 Where hob, oven and washer sit

* **Hob**: in the cell, P1–P3 as above. P3 could be a bought household domino zone with its touch control
  replaced by an interface board (K8b, #28); P1 and P2 need the thimbles and stay custom.
* **Oven**: outside the cell, in an **oven column** at normal height with front access for the human: a
  household 60 cm oven with an automatic door (#24), loaded by the transport through the oven door (as K1b,
  K2b, K8b). Trays leave the cell through the right port. K4's oven above the hob is gone (C2 K4-6, C3 K4-4,
  C4 K4-1).
* **Washer**: the cell washes its mats and fixed parts itself; loose ware leaves through the right port to
  the machine's one bought washer for ware and dishes (decision-matrix 6.1 H-S1, C5 Q1). Option for a
  self-contained cell: a K6b-type top-loading well at the right end, sharing K4b's pump, boiler and steam
  generator, +360 mm of width (cell 1 760).

### 2.8 Interfaces

| Interface | K4b needs | Request to the architect |
|---|---|---|
| Box port, left wall, Z 1230–1450 | GN 1/6 or 1/3 box set into the passive cradle, **lid already off**; pour edge along Y; the cradle tilts the box onto mat D or into a cup or basket held by the arm, loss in weight on its 6 kg cell | lids removed by the lid station (C5 Q7); long goods, fillets, sausages stored **lengthwise** (pour direction sets orientation, K4); meat slices interleaved or shingled; eggs in a 2 × 3 insert; stowed packs arrive opened in a carrier box (#3); pastes filled once into small-tube cartridges kept cold (K5) |
| Ware and plate port, right wall, Z 880–1120 | the arm sets vessels, trays, plates, waste bowl and soiled ware on a pass tray; the transport takes and brings | transport serves the oven column and the washer; dish stock delivers warm plates on request |
| Serving | plates filled on P1 by polar placement, or vessels handed out | hatch and plate transport (C4 9.5) |
| Utilities | cold water 2.2–5 bar, drain with trap, 400 V 3N~, 120 m³/h extraction | detergent supply to the 3 L sump |
| Human | door interlocked; mat change 2 min without tools (pull the dancer and mat out of the slot upward, hook the new anchor, lay the hem in its fork); anvil sticks yearly | HUM-007: two mats every 2–3 years, four sticks a year |

---

## 3. How the hard operations work now

Times for 4 persons unless stated [E]. "Ev." = handling events of the arm (one pick-and-place of a vessel,
tool or hem, one cradle tilt); blade cuts, press strokes and mat feeds are process strokes and are listed
separately where they matter. Confidence H / M / L as in round 1.

### 3.1 Generic peel, core and stone (#25, PRP-039)

Three mechanisms cover the list, all at P1, plus two recipe routes that need no mechanism:

* **G1 Vertical lathe.** The washed item drops into the *spike cup* on T (a shallow dish with a 3-prong
  spike Ø 8 in a centring cone). The arm sets the *tailstock cup* on top; the press comes down and impales
  the item (30–60 N) and then holds it (20–40 N); the cup turns with the item on its PEEK thrust face under
  the still press plate. T turns at 60–150 rpm; the arm brings the **sprung peeler with depth shoe** (1, 2.5
  or 5 mm) to the upper pole and traverses down in Z, following the radius in X, 8–12 mm per turn; camera C1
  checks the surface and a second pass, offset by half a pitch, takes what is left. Peel falls into the
  dish. The press lifts; the arm slides a stripper fork under the item (X) and lifts it off the spike (Z).
  The poles (spike and cup marks, Ø 15) are trimmed at the blade if the recipe slices the item anyway.
* **G2 Press family** (press plate pushes, the arm sets the tool): tube corers Ø 14 / 22 / 42 with ejector
  pin, corer-wedger (8 wedges + Ø 22 core), plug corer GP-61 with T oscillating ±30° under it, pitter ring,
  **press-peel** (ricer plate or ring seat: flesh passes, skin stays), **grid skinning** (half fruit skin-up
  on the 10 mm grid).
* **G3 Knurled disc on T** (GP-P2): 1–1.5 kg of potatoes in the 6 L pot on P1 over the knurled floor disc,
  250 rpm, the hung roller-scraper holds the charge, spout water on, camera stop at ≤ 5 % brown surface.
* Routes: **cook in skin, then rice or slip** (GP-P1) for mash, Pellkartoffeln, potato salad,
  Bratkartoffeln, dumplings; **blanch and slip** in the P1 basket for tomato, peach, apricot (cross scored by
  two blade cuts).

| Item | Mechanism and sequence | Time | Conf. | Untested |
|---|---|---|---|---|
| Potato, raw-peeled (gratin, Rösti, Salzkartoffeln) | G3, 2.5 min per 1.2 kg; or G1 for ≤ 4 pieces | 3 min | M–H | stop rule on knobbly tubers |
| Potato for mash, salad, Bratkartoffeln | boiled in skin; riced (skins stay on the plate) or slipped by 40 s of rubbing in the wash basket on T with water | 0 min extra | H | — |
| Carrot, parsnip | scrubbed 60 s on G3; G1 for long ones cut to ≤ 160 mm | 1–3 min | H / M | whip of thin carrots on the spike |
| Celeriac, kohlrabi, beetroot | celeriac halved at the blade, G1 with the 2.5 mm shoe (knobs: second pass, loss ≈ 25 %); kohlrabi G1; beetroot cooked in skin, slipped | 40 s each | M | knobs and leaf scars |
| Apple, pear (whole) | settles stem-axis vertical in the cone (oblate fruit is stable that way); G1 1 mm shoe; Ø 22 corer down round the spike (baked apple, DS15) or corer-wedger (cake, red cabbage, compote) | 25 s each | M (pare) / H (core) | axis found in ≥ 90 % of apples |
| Cucumber, courgette | cut to 150 mm at the blade; G1 1 mm shoe (or striped by two passes); seeds: halving lengthwise is not possible at the blade, so tzatziki uses flesh grated on the lathe and squeezed in the press | 30 s per piece | M | — |
| Bell pepper | strips and dice: **four cheeks** (GP-62) on a plate on T, stalk up, the arm pushes the knife down in four chord cuts, T indexes 90°; stuffed peppers: plug corer GP-61, inverted rinse | 20 s / 15 s | H / M–H | stalk found by camera |
| Tomato | small: not cored; beef tomato: Ø 14 corer on the scar; skin: blanch and slip | 10 s | H | — |
| Avocado (MX06) | **cup pair**: bottom cup on T, top cup under the press; the arm's paring knife cuts radially to the stone while T turns once; T turns 90° against the held top half: halves part; the arm's 3-prong tool stabs the stone, T twists, the arm lifts the stone out; halves skin-up on the grid: the press pushes the flesh through | 90 s for 2 | L–M | ripeness spread; skin tearing on the grid |
| Banana (CK16 bread, DS10) | for mash: tips trimmed and 40 mm pieces cut at the blade, pressed with skin through the ricer plate, skins stay; for slices: 60 mm pieces fall end-first from the nose into the Ø 40 press-peel tube, the plunger pushes the flesh out, the skin ring stays | 60 s / 90 s | M / L–M | skin strength of ripe bananas |
| Orange, lemon | zest: rasp pressed with 2–4 N by the arm against the fruit on the lathe, one pass (GP-Z1); juice: halved at the blade, half pressed cut-face down by the press onto a reamer cone on T; segments: pared *à vif* on the lathe (5 mm shoe), sliced into rounds (class c for segments) | 15–40 s | H / H / M | — |
| Pumpkin, squash | roasted whole first (GP-67, oven column), halved soft at the blade, seeds scraped by the arm's spoon while T turns, halves riced skin-up | 3 min | M | — |
| Kiwi, mango | kiwi on the lathe, 1 mm shoe; mango: cheeks only by the four-cheek rule on T (stone plane found by camera, L–M) | 30 s | M / L–M | — |
| Grate (carrot, apple, celeriac, cucumber, cheese block) | coarse or fine rasp held by the arm against the item turning on the lathe at 60–120 rpm, traversed in Z; gratings fall into the spike dish (K8b's T-lathe principle); hard cheese bought grated by default | 60 s per 200 g | M–H | last 15 mm at the spike |
| Garlic (44 meals) | GP-17: the press cracks the bulb lightly in a cup; cloves skin-on into the small tube with the 2 mm plate; the press squeezes, the skins stay in the tube | 30 s | H | — |
| Onion | bought peeled (#9). Upgrade slot: GP-11 slits with the 2.5 mm shoe on the lathe and a jet | — | L–M | everything (G-produce 1.6) |
| Cabbage core | half cabbage cut face up in a cone cup on T; the arm holds the knife at 30° and T turns once (cone cut, GP-25); the 3-prong lifts the cone out | 40 s | M | — |
| Cherry, plum, pineapple (S) | pitter ring under the press; pineapple topped and tailed at the blade, pared on the lathe (5 mm shoe), cored Ø 22 | — | M / L–M | — |
| White asparagus | not solved (spear too slender for the spike); class (c) as for every concept | — | — | — |

Mechanism count for PRP-039: **three** (lathe, press family, knurled disc), as asked; no single-purpose
device.

### 3.2 Dice an onion

Peeled onion (bought, #9) from the cradle into a cup held by the arm → onto mat D → E feeds it under the
fingers; one cut halves it; the halves fall into the pocket → the nose drops them into the **press tube** (Ø 90,
two-tier 6 mm grid) that stands on its ring over the bowl on P1 → the arm sets the comb piston on top →
the press pushes 1–2 kN [C: half onion 2 200 mm², edge 2A/p = 730 mm, 2–5 N/mm × 1.5, two-tier ÷ 3 ≈
0.7–1.8 kN] → 6 mm dice fall into the bowl. Two onions: four halves in two loads, **≈ 70 s, 6 ev.**
10 mm dice: whole onion on the 10 mm grid, one load. Fine mince (< 3 mm): blender jug on S, 3 × 1 s pulses.
Half-rings: halves fed cut face down to the blade at 3 mm. Confidence **H** for the grid (C1 §5: press-through
dicing H for onion halves), M for the 1.8 kN worst case. The 2.5 kN press reaction goes through the ring
into three thrust pads in the deck beside the coil, never through the canned thimble.

### 3.3 Rouladen (8 rolls): fill, roll, secure, sear, braise

| t | Step | Where | Ev. |
|---|---|---|---|
| 0 | Mise: onion 6 mm dice (3.2) into a cup; gherkins cut to 3 mm coins at the blade, into a cup; bacon diced (the family variant, G-assembly 5.2) from a cold block through the 6 mm grid in the press; mustard 60 g pressed from its cartridge (small tube, press) into a cup on P1's scale | mat D, P1 | 10 |
| 8 | Mat D retracted and washed; mat S drawn out, hem parked in the pocket fork; the cradle tips the opened carrier of interleaved slices onto the table: two slices side by side, long side along X | mat S | 3 |
| 9 | Per pair: pin with 5 mm rings, wetted, 6 passes; salt and pepper by the sifter cup; mustard: three dots per slice from the spoon-scraper, kept 35 mm clear of the seam end, spread by two pin passes; seam end dusted with flour (GA 4.2-2); filling as a curtain along Y from the wide-lip trough cup over the leading third | table | 6 per pair |
| 11 | Plough rails set into their sockets at the table end (once): as E feeds the pair forward, the rails fold 15 mm of each side margin over the filling (GA-04) | table end | 2 once |
| 12 | Arm takes the hem; E feeds the pair over E and G; the arm pays out until the loop is 1.1 × the roll circumference (≈ 160 mm); **E and the bar then run together**: the loop runs, the slices roll 2 turns on themselves (SM-079, K3 pocket); C1 sees the seam and stops it at 5 o'clock | loop | 2 |
| 13 | Nose: the bar winds, the two rolls ride up and drop 40 mm into slots of the **comb cradle** standing cold on P1 | P1 | 1 |
| 9–25 | Four pairs | | |
| 25 | **Raft** (GA-20): the arm pushes the two-tine hairpin fork along X through the cradle's guide slots and four rolls (30–60 N); second raft for the other four | P1 | 4 |
| 27 | Braiser on P3 with 40 mL fat at 200 °C: each raft lowered seam-down by its handle tab, 90 s untouched, rolled 180° about Y for the second face, 90 s; rafts out onto a tray | P3 | 8 |
| 34 | **Fond** (C1 10.3 rule 1): onion dice and a tomato-paste dose roasted in the fat 4 min, stirred by the spoon-scraper every 30 s; deglazed with wine and stock from cups | P3 | 6 |
| 40 | Rafts back in, lid on, P3 at a simmer for 100 min (or the oven column at 160 °C) | P3 | 3 |
| 140 | Rafts lifted, drained; pulled back in X through the stripper comb of the cradle: rolls drop seam-down onto a warm platter; sauce thickened with a starch slurry, stirred | P3, P1 | 6 |

**≈ 34 min of work, ≈ 50 ev.** Confidence: rolling **M** (shared SM-079 test, now with the side folds and a
measured seam), securing **H** for holding (GA-20), browning on two faces (≈ 60 % of the surface, GA 4.2).
Untested: the first turn in the running loop on silicone; release of the rolled slice from mat S (wet,
floured flap). Fallback: single steel pins set through the cradle slots, counted back by camera.

### 3.4 Breaded Schnitzel in 3–4 mm of fat

| Step | How | Ev. |
|---|---|---|
| Flatten | cutlets (bought, 4 × 150 g) tipped onto mat S; pin with 5 mm rings, wetted, then 4 mm; two at a time | 4 |
| Flour | on the mat: the sifter cup dusts the pair; the wide turner slides under each cutlet in X, turns it over by rolling 180° and lays it back; second dusting | 4 |
| Egg | turner carries each into the egg pan on P2 (egg beaten in the jug, strained through the slotted saucer), turns it, holds it 5 s to drip | 4 |
| Crumbs | crumb bed (50 g) poured by the trough cup onto mat S; turner lays the cutlet on it; curtain of crumbs on top; pin with 6 mm rings, one light pass (adhesion without crushing) | 4 |
| Fry | **250 mL of fat in the 28 cm pan on P1** at 170 °C (4 mm depth, C1 A-3); the lift rack already lies in the fat; the nose lays the breaded pair onto the rack from 40 mm; 3 min; the second rack is set on top, the pair of racks lifted by both tabs (shoe + magnet), drained 5 s, turned 180°, lowered; 3 min; lifted out, drained, onto a vented tray kept at 80 °C | 6 |
| Second pair | breading of pair 2 runs while pair 1 fries | — |

Per pair ≈ 9 min of which 6 frying; **4 cutlets ≈ 15 min, ≈ 40 ev.**; the fried items are the last thing made
(C1 A-4), holding ≤ 6 min. Confidence **M–H** (GA-36 rack turn M–H; crumb coverage at the turner's contact
lines M). The fat stays in the pan; after the meal it is poured through the dump funnel into a fat cup in the
waste drawer when below 60 °C.

### 3.5 Frikadellen (8 pieces)

Day-old roll soaked 2 min in milk in the bowl on P1 (T slow); onion 6 mm dice, egg (cracker on P1),
mustard, salt; mince 600 g tipped by the cradle into the bowl held by the arm under its pour edge. **Mixed**
90 s, T at 40 rpm against the hung kneading frame (KNM, Ankarsrum [K]). **Portioned** by the wetted Ø 50
disher (≈ 75 g, ±6 g by P1's scale) onto mat S in two rows of four; the disher releases against the fixed post
at the table end. **Shaped** by one pass of the pin with 22 mm rings: flattened balls with rounded edges, the
hand-made shape (C1 R-10). **Fried** in the 28 cm pan on P1 (40 mL fat): the nose lays a row of four,
then the second; 5 min, turned one by one with the turner (8 × 6 s), 5 min; probe in the thickest piece to
72 °C. **≈ 20 min, ≈ 30 ev.**, confidence **M–H** (the disher and the pin are cook's methods; mince on wet
silicone releases at the nose with the doctor lip — the residue is washed in the gate, not eaten).

### 3.6 Mash

1 kg potatoes boiled in skin (GP-P1) in the 6 L pot with basket on P2 (25 min). The 4 L pot with 150 mL milk
and 40 g butter warms on P1; the press ring and tube with the **ricer plate** stand on it. The arm lifts the
basket, drains it 20 s, tips about a third into the tube, sets the piston; the press rices at 1–1.5 kN; the
arm lifts the tube and knocks the skins off the plate over the dump funnel; three loads. Then T turns the pot
at 30 rpm under the hung whisk-scraper for 30 s; nutmeg from the seasoning cup. **≈ 4 min, 12 ev.**, **H**
(ricer [K]; C1 K4-7 fixed: no beater).

### 3.7 Kneading and shaping dough

* **Knead** (500 g flour, pizza): flour from the cradle into the bowl held by the arm, water 320 mL at 30 °C
  from the spout, yeast, salt, oil from cups; bowl on P1; T at 60–100 rpm against the hung roller frame,
  6–8 min; torque logged as the end point (C1 rank 2, C3 rank 1: **H**). Proof: lidded bowl at 32 °C on P1
  at minimum power or in the oven column, 60 min.
* **Divide**: the arm tips the bowl over floured mat D; the lump slides out (≤ 3 % stays in a floured bowl
  [E], scraped later by the hung scraper while T turns); a blunt bench-scraper tool pressed by the arm cuts it
  on the mat (soft dough, ≤ 100 N; a blunt edge does not cut silicone).
* **Sheet** (log first, then sheet): one piece is rolled under the pin at light force to a log lying along Y,
  280 mm long (a lump rolled along X becomes a cylinder across the motion); then the pin with 4 mm rings
  sheets it along X in 8–10 passes to **380 × 280 × 4 mm**; flour dusted by the sifter between passes. The
  rings set the thickness, not the arm. Round bases: on a floured plate on T, the pin rolls along X and T
  turns 60° between passes. Confidence **M–H** (rolling pin with spacer rings [K]; spring-back of yeast dough
  is handled by a 5 min rest between passes 6 and 7).
* **Lay on the tray**: anvil stick lifted out; tray on P3; the mat runs from the top of E down to the bar at
  ≤ 25°; the arm holds the hem over the tray's left end and **moves the bar along X while winding at the same
  speed**: the sheet is laid flat without stretching (retracting nose [K]).
* **Shape** rolls: Ø 50 disher portions onto mat D, rested; loaves: the dough log rolled to tin length, the
  nose drops it into the loaf tin; cinnamon rolls: sheet, spread, rolled in the running loop, cut at the
  blade into 30 mm snails which fall onto the mat, nose onto the tray.
* **Thin sheets** for Maultaschen, ravioli, spring rolls: pasta dough sheeted with 2 mm then 1.5 mm rings
  (≈ 200 N from the arm near the table [C]); 1 mm only at L–M.

### 3.8 Pancake flip

Batter whisked in the jug on S (whisk rotor, 30 s), rested. Two shallow pans: pan 1 on P1, pan 2 with a drip
skirt preheated on P2, 3 g butter each. The arm pours 100 mL (by P1's scale, ±8 g); **T spin-coats** at 90 rpm
for 3 s (K4's idea kept); 90 s. **Pan-pair flip** under G-assembly 7.1: release check (5 mm jerk by T, camera
sees the pancake move), pan 2 set upside down on pan 1, both tabs in the shoe, magnet on, lift 120 mm, turn
180° in 0.8 s about Y, set down on P1, pan 1 lifted off and returned to P2 with fresh butter. Free fat
≤ 30 mL by recipe. **Cycle 2 min, 8 pancakes ≈ 17 min, 5 ev. per pancake.** Confidence **M–H** for full-floor
pancakes (shared test).

### 3.9 Draining pasta

Spaghetti (dosed lengthwise from their box by the cradle onto mat D, mass by loss in weight, laid end-first
by the nose into the basket in boiling water in the 6 L pot on P1; pushed under after 60 s by the
spoon-scraper). The arm lifts the **basket** (≤ 2.5 kg), holds it 20 s over the pot, tips the pasta into the
sauce in the wide pan on P3 or into the serving vessel; a ladle of cooking water first if the recipe wants
it. The water stays in the pot; when below 60 °C the arm **slides** the pot on the flush deck to P1's left
edge and tilts it about the lip bar of the dump funnel — the pot is never lifted full (K4 rule R7). **H.**

### 3.10 Carving (boneless roast)

The roast rests on its rack in the oven tray (lengthwise along X, as set before roasting) and comes back
from the oven column through the right port. The arm tips the tray's juice into the gravy pot on P3, then
lifts the rack and slides the roast onto mat D. E feeds it to the blade in 6–8 mm steps; the fingers hold it
behind the cut; the **draw-cut blade** lands on the anvil stick; each slice falls 65 mm onto the moving mat,
which advances by the same step: the slices land **shingled** in carving order (GA-14 kinematics without its
twin blade). The nose then lays the shingled row on a warm platter, or three slices per plate (3.11). 12
slices ≈ 1 min, 6 ev. **H** for firm roasts, **M** for braised meat (8–10 mm, fingers at 5 N). Bone-in
poultry: parts (R-06 b), as everyone.

### 3.11 Plating 2–4 portions nicely

Warm plates come from the dish stock through the right port. One plate at a time sits on P1's spider (plate
adapter); T gives the angle, the arm the radius — **polar placement**: (1) sauce: ladle poured in a 120° arc
while T turns; (2) meat: the nose lays three shingled slices at r = 60 mm, or a Roulade from the stripper, or
a Schnitzel slid off its rack; (3) mash or rice: disher Ø 60 at r = 60 mm, T + 120°; (4) vegetables: slotted
spoon, T + 120°; (5) garnish: chopped herbs from the sifter cup; (6) rim: a silicone wiper held at the rim
while T turns once. C1 checks each element against the plating template. The plate leaves through the port.
**≈ 50 s and 6 ev. per plate: 2 plates 1.7 min, 4 plates 3.5 min** (C4's 3 min for 4 is missed by 30 s; the
first two plates can be filled while the fried item finishes).

---

## 4. Benchmark check B1–B12

Times from the order to hand-over [E]; "ev." = handling events as in section 3 (arm picks and places, hem
takes and parks, cradle tilts, port transfers, plating). Limits are PERF-001 as listed in K4 §5. B6 is
walked at 4 persons (#19 caps a meal at 4). Notes only where K4b differs from K4.

| | Result | 4 p: time / limit, ev. | 2 p: time, ev. | What changed against K4 |
|---|---|---|---|---|
| B1 Rouladen, Rotkohl, Salzkartoffeln | yes | 160 / 183 min, ≈ 100 | 155 min, ≈ 72 | rolls in pairs in the running loop with side folds, GA-20 rafts, seared on two faces, fond with roasted onion and paste (3.3); red cabbage halved at the blade, cone-cored on T, shredded 2 mm at the blade, apple pared and wedge-cored (C1 K4-4 fixed); potatoes raw-peeled on the knurled disc; Rotkohl simmers on P2 under the hung scraper |
| B2 Schnitzel, Bratkartoffeln, Gurkensalat | yes | 52 / 68 min, ≈ 80 | 45 min, ≈ 60 | potatoes boiled in skin ahead (idle hours, C5 Q2) and kept cold, slipped, sliced 5 mm at the blade, fried on P3 and turned every 4 min (C1 K4-3); cucumbers pared on the lathe, sliced 2 mm into the catch pocket while the arm breads; dill cut at 1 mm; Schnitzel in 250 mL fat, rack turn, fried last (3.4) |
| B3 Frikadellen, Püree, Erbsen-Möhren | yes | 40 / 50 min, ≈ 65 | 36 min, ≈ 50 | carrots scrubbed and diced 10 mm in the press; Frikadellen mixed on T, portioned by disher, shaped by the pin, probe 72 °C (3.5); potatoes in skin, riced (3.6); 10 min of margin instead of 2 |
| B4 Spaghetti Bolognese | yes | 72 / 96 min, ≈ 40 | 68 min, ≈ 32 | onion, carrot, celeriac diced in the press, garlic pressed (GP-17); **mince seared first** in the wide pan on P3, vegetables after (C1 K4-8); simmer on P2 under the scraper; spaghetti laid end-first by the nose (3.9) |
| B5 Pizza, 2 trays | yes | 95 / 113 min, ≈ 45 | (1 tray) 92 min, ≈ 30 | kneaded on T (not on the mat); log-then-sheet with the ringed pin, laid on the tray by the moving nose; salami cut at the blade with a 50 mm feed per cut so the slices land spaced and are laid in rows; trays baked in the oven column |
| B6 Gemüseeintopf (walked at 4 p) | yes | 45 / 60 min, ≈ 40 | 40 min, ≈ 30 | leek cut into rings at the blade **before** washing (GP-W4), washed in the dunk basket on P1; celeriac pared on the lathe; everything diced 10/20 mm in the press |
| B7 Steak, oven fries, salad (2 p) | yes | — | 45 / 79 min, ≈ 50 | fries: potatoes through the 10 mm grid without cross-cut (sticks), oiled in the bowl on T, baked in the oven column; lettuce butt cut at the blade, dunk-washed and spun on T; pepper by four cheeks; **probe** in the steak (C1 K4-5) |
| B8 Pfannkuchen, 8 | yes | 42 / 50 min, ≈ 50 | (4) 30 min, ≈ 28 | spin-coat on T kept; pan-pair flip under the G-assembly 7.1 rules (3.8) |
| B9 Chicken curry, rice | yes | 40 / 68 min, ≈ 35 | 36 min, ≈ 28 | chicken bought diced (#8) or thigh fillets cut into 20 mm bite strips at the blade on mat S; ginger and garlic through the press; rice rinsed in the fine basket and cooked by absorption on P2 |
| B10 Lasagne, béchamel | yes | 120 / 148 min, ≈ 60 | 115 min, ≈ 45 | béchamel in the 1.5 L pot on P1 under the hung whisk-scraper; **fresh sheets** sheeted to 1.5 mm and cut at the blade (or dry sheets dealt from a stack by the fingers as a retard, M); sheets laid across the dish by the nose; baked in the oven column |
| B11 Rührkuchen, unmoulded | yes | 105 / 125 min, ≈ 25 | — | creamed on T under the hung beater-scraper; tin greased by spin; bowl emptied in two pours with a scrape on T between (≤ 5 % residue [E], PRP-013); induction release pulse and inversion with tin and platter in the shoe (K2) |
| B12 Scrambled eggs, toast, 1 p | yes | — | 1 p: 9 / 17 min, ≈ 14 | eggs by the egg spoon and the cracker on P1; small pot on P1 under the hung scraper at 20 rpm; toast in the dry pan on P3, turned by the turner; chives cut at the blade |

**Mean ≈ 53 events at 4 persons and ≈ 40 at 2 persons**; B1 and B2 at 4 persons exceed C5's 70 (6.2).
Process strokes per meal (not counted as events): 100–400 blade cuts, 10–40 press strokes, 30–80 pin passes,
20–60 mat feeds and nose deliveries.

---

## 5. Cleaning

### 5.1 Principle

1. **Mats** — the only flexible food surfaces — are washed while they retract through their gate, then
   **steamed and dried hanging in their own closed slot** (after every class R use; mat D at least daily).
   Both faces, the full length, the dancer and the slot walls reach ≥ 95 °C for 60 s: A0 ≈ 1 900 s [C], moist
   heat (C2 R-3). Nothing is wound while wet (C2 R-9).
2. **Fixed food-contact parts** are few, smooth and visible: the bars L, E, G (they touch only the back face
   of the mat), the blade and its one-piece finger comb (they touch food), the top of the press plate (it
   touches tools, not food). Rinsed by fixed nozzles after each use, washed hot after the meal; the blade and
   fingers have a **steam park** at Z 1380 (a hood with a steam nozzle bar) used after every class R cut.
3. **Everything else is ware** with a tab and leaves through the right port for the machine's washer:
   vessels, press and lathe sets, arm tools, **anvil sticks**, the comb cradle, the plough rails.
4. **Zone S** (walls, gallery, deck, front strip, columns, arm) is washed by fixed fan nozzles and two
   rotating heads after each warm meal and dried by the extraction fan (C2 R-7).

### 5.2 Surface inventory (HYG-010)

| Surface | Zone | Area m² [E] | Soiled by | Cleaned by | When | Dries by | Verified by |
|---|---|---|---|---|---|---|---|
| Mats S, D, both faces | F | 2 × 0.87 | food (S raw, D dough/RTE) | gate on retraction; steam and hot air in the slot | every use; steam after class R and daily | 65 °C air in the slot, 4 min | C1 sees the food face, a gate mirror the back face, at every draw-out; slot temperature log gives A0 |
| Slots, dancers, anchors | S/F | 2 × 0.6 | mat back face, gate run-off | steam with the mat; slot nozzle at the top | with the mat | hot air | temperature log |
| Table plate (under the mat) | F | 0.12 | wet film under the mat, edge spill | spray bar above the table when the mat is in | after each retraction; hot after the meal | 1.5° fall, warm air | C1 (bare table) |
| L bars, E, G | F (back face) | 0.03 | mat back face | fixed nozzles while E turns | after each use | air | C1 oblique, parameters |
| Blade, finger comb | F | 0.05 | every cut | nozzle rinse at park; **steam park** after class R; hot wash after the meal | each cutting job | own heat | C1 images the edge against the white mat (PRP-035) |
| Anvil sticks (4) | F | 0.01 each | every cut | ware → washer | per meal (red after every class R job) | washer | washer camera |
| P1/P2 spiders, thimble domes, deck inserts | S | 0.3 | spill, boil-over | deck nozzles; spiders are ware | per meal | slope to the front gutter | C2 camera |
| Bar of the arm (hem zone) | S | 0.05 | mat leader, never food | nozzle while it spins | per meal | spin | C1 |
| Dump funnel, strainer | S/F | 0.08 | waste, pot water | flush from its rim nozzle; strainer basket is ware | each use / per meal | — | level sensor |
| Walls, gallery, arm links, columns, front strip, deck | S | 4.6 | splash, fat aerosol (lids on frying pans), flour | 14 fan nozzles + 2 rotating heads, 60 °C | after each warm meal | extraction fan 10 min | riboflavin self-test monthly; camera |
| Loose ware, 15–25 items per meal | F | 1.2–2.0 | food | washer of the machine | per meal | washer | washer |

**Fixed zone F ≈ 0.25 m²** (K4: 0.69 m² plus 10 m² of mats). Mats 1.7 m² (K4: 10 m²). Zone S 4.6 m² (K4: 8.3).

### 5.3 Raw and ready-to-eat

* **Instances**: mat S for raw meat and fish, mat D for dough and ready-to-eat; red and green anvil sticks;
  red ware for class R (two pans, one bowl, the lift racks) where two items must overlap in time.
* **Sequence**: ready-to-eat cutting before raw cutting in the plan; if a ready-to-eat cut must follow a raw
  one (garnish), the blade and fingers run their steam park (3 min), the anvil stick is swapped red → green,
  and mat D is used.
* **Unwashed produce is class R** (C2 R-5): it never touches a mat. The cradle pours it into the wash basket
  held by the arm; it is washed in the bowl on P1 (dunk basket, GP-W1) and only then goes onto mat D, the
  lathe or the press.
* **E and G** touch only the back face of a mat; the table only the back face. They are rinsed after each use
  and washed hot after the meal; no class R food touches them.
* The blade is the one fixed part that cuts raw meat. Its moist-heat park is the reason it can stay fixed;
  if the log shows < 95 °C for 60 s, class R cutting is blocked until it passes.

### 5.4 Water, energy, time per 4-person meal (from nozzle flow × time, C2 R-4)

| Item | Water L | Energy kWh | Time |
|---|---|---|---|
| Gate on retraction: 3 + 3 nozzles pre-rinse, 3 + 3 hot rinse at 0.3 L/min each, 31 s per 1.55 m at 50 mm/s, 3 retractions | 5.6 | 0.30 (rinse at 85 °C) | 1.5 min, parallel |
| Detergent sump 3 L, renewed per meal and after class R | 3 | 0.15 | — |
| Steam in a slot, 220 g per cycle [C: 500 kJ for mat, dancer, walls], 1.5 cycles | 0.3 | 0.21 | 3 min per cycle, parallel |
| Hot-air drying 1 kW, 4 min, 2 cycles | — | 0.13 | parallel |
| Fixed parts: table spray, bars, blade park (steam 40 g) | 2 | 0.10 | 1 min |
| Zone S wash after the meal: 14 fans + 2 heads, 60 °C, 90 s | 5 | 0.30 | 4 min + 10 min drying |
| **In-cell cleaning** | **≈ 16 L** | **≈ 1.2 kWh** | cell clean **≈ 15 min** after the last food contact |
| Ware in the machine's washer (15–25 items ≈ 0.6 of a commercial undercounter load) | ≈ 10 | ≈ 0.8 | other module |
| Produce washing (dunk baths) and cooking water | 8–14 | — | — |

For 2 persons: ≈ 13 L in the cell and ≈ 1.0 kWh (the mat and zone S washes do not scale with persons). The
K4 figure of 15 L for the cell was a mist; C2 recomputed 62–76 L for K4 in total. K4b's in-cell share is
lower because 1.7 m² of mat instead of 6–8 m² passes the gate.

### 5.5 Crevices, seals and spray shadows, named

1. **Mat edge beads**: convex, root fillet R 2.5, no undercut; fans reach them from both sides at the gate.
2. **Hem**: rod moulded in, no pocket; the first 30 mm never carry food and park outside the gate.
3. **Mat anchor** at the top of the slot: a clamp bar; steamed with the slot, not sprayed directly.
4. **Dancer guides**: PEEK sliders in vertical grooves of the slot end plates — a wet sliding pair, steamed.
5. **Blade-to-beam and finger comb**: welded one-piece comb; the beam joint to the column is in zone S.
6. **Two column rod seals** (blade, press): scraper, drained lantern, dry seal (SM-191); the press column is
   in front of P1, outside the projection of its vessel; the blade column in front of the anvil.
7. **Arm elbow seal and shoulder cartridge seal**: in the gallery, never above a vessel; the wrist is canned.
8. **Thimbles of T, S, T2**: no seal; the PEEK bushes of the spider bells are ware.
9. **Bar of the arm over an open vessel** while it carries that vessel: a smooth tube, washed per meal — an
   accepted deviation from C2 R-2, as for every carrier that grips a vessel from behind.
10. **Spray shadows**: the underside of the parked blade beam (reached by the steam park), the inside of the
    front strip behind the columns (rotating head), the funnel lip bar.

### 5.6 Peelings and scraps

Peel from the lathe stays in the spike dish and is tipped into the dump funnel after each batch; trimmings
from the blade fall onto the mat and are delivered by the nose into the funnel; knurled-disc slurry is
poured off the pot through the funnel within 2 minutes (C2 R-8). The funnel's 2 mm strainer basket is ware
and goes with the waste drawer (GN 1/6) to the transport after the meal; water goes to the drain through a
trap and a turbidity sensor.

---

## 6. Numbers before → after

| Quantity | K4 (critic figures where they differ) | K4b | Note |
|---|---|---|---|
| Cell width | 1 560 incl. oven above the hob; oven did not fit the depth (C4) | **1 400** without oven and ware washer | mat bay 520 (table 400 over the store slots, anvil and funnel strip 120) + P1–P3 840 + walls |
| Like for like: cell + oven column + ware washing | ≈ 2.2 m (C3 X3 scope) | **2.0 m + the machine's shared washer**, or **2.36 m** with the in-cell well option (2.7) | K1b 1.85, K6b 1.86, K8b 1.78 m: K4b is the widest of the improved cells (7) |
| Depth margin | 0 mm, no rear allowance | **17 mm + 10 mm** rear allowance | 2.1 |
| Height | 2 000 | 2 100 (≤ 2 200, #11) | camera and duct in the top 150 |
| Motion actuators (C5 ≤ 10) | 26 stated, 20 C5-normalised | **9** | arm 3, capstan E, blade column, press column, T, S, T2 |
| Dynamic seals (≤ 5) | 22 | **4** | shoulder cartridge, elbow, two column rod seals; wrist, E, T, S, T2 canned |
| Independent novel mechanisms (≤ 2) | 8 | **2** by C5's S-min convention, **4** strictly | 6.1 |
| Distinct mechanism types | 12 | 7 | arm, mat store and gate, capstan nose, blade column, press column, canned turning hub, wash core |
| Custom part types | ≈ 48 | ≈ 42 | |
| Loose ware | 36 items + 5 mats | ≈ 80 items, ≈ 50 types; 15–25 per meal | the press, lathe and tool sets the critics asked for |
| Flexible food surface | 10 m², fabric-cored, stored wound | **1.7 m²** (both faces of two mats), solid silicone, stored hanging, steamed | |
| Fixed zone F | 0.69 m² | ≈ 0.25 m² | 5.2 |
| Handling events per meal | ≈ 95 + 300–900 uncounted strokes (C5) | **≈ 53 mean at 4 p, ≈ 40 at 2 p**; B1/B2 at 4 p 80–100 | 4 |
| Series chain, B3 | 11 | 7 (arm, press, T, mat S + capstan, P1 pan, P2, washer) | |
| Cleaning stations | 4 + chamber | 3 (gates with their slots, blade steam park, fixed nozzle system) + the shared washer | |
| Peak power of the cell | 11 kW (C4) | ≤ 7.5 kW: hob ≤ 5.6 kW on two phases, motors ≤ 1 kW, boiler or steam only in hob pauses | oven on its own phase outside |
| Water per meal, in the cell | 15 L claimed; C2: whole meal 62–76 L | 16 L (4 p), 13 L (2 p); whole meal incl. ware, produce, cooking ≈ 35–40 L (4 p), ≈ 30 L (2 p) | 5.4 |
| Wear parts a year | ≈ €570 (mats only) | **≈ €130**: mats every 2–3 years, four anvil sticks, two column scraper rings | HUM-007: one visit a year, < 10 min |
| Coverage, C1 standard N, central | 202 = 81.5 % (208 with modules) | **232 = 93.5 %**, range 227–238 | 6.2 |
| Parts cost | €16 k claimed; C3 25–29 k€; C4 19.5 k€ | **≈ €7.1 k machine part** design-to-cost (prototype ≈ €12.8 k) + oven €500 outside | 6.3; #28's €2 k missed by 3.5 × |

### 6.1 The C5 hard limits

* **Actuators ≤ 10: 9. Dynamic seals ≤ 5: 4.** Met.
* **Novel mechanisms ≤ 2**: by the convention C5 used for its own S-min (canned couplings, turning
  positions with hung tools, the pull-down press, pan pair, raft and egg fixture are known or shared) K4b has
  two: **(1) the mat line** — solid mats hanging on dancers, washed on retraction, steamed and dried in
  their slots, driven by a capstan nose, with a running loop for rolling; **(2) the vertical lathe at P1**
  (turntable, press as tailstock, arm as tool post). Strictly two more are combinations of known parts that
  still need a rig: the blade landing on a loose anvil past a capstan nose with the catch bar G (belt-end
  guillotines are industrial practice [K], the soft silicone feed and the 65 mm fall are not), and the
  dovetail shoe with an electro-permanent magnet gripping in soil (C3 K4-6). Exception argued: the mat line
  *is* the concept; the lathe replaces three single-purpose peelers and is the host of #25.
* **Events ≤ 70**: met for the 2-person household (≈ 40) and by ten of twelve benchmarks at their brief size;
  B1 and B2 at 4 persons need 80–100 (as K1b 88–105, K6b 92–102). Every event is a form-fit dovetail on a
  fixed tab, checked by the shoe's magnet flux and P1's or P3's load cells.

### 6.2 Coverage under C1's standard N

Population 248; the 8 meals of requirements 5.4 are out for everyone. Starting point: C1's K4 list with
modules (23 out, 9 at risk). K4b now has the axes the modules need (plunge, slow rotary, fast rotary, a free
X–Z tool), so it hosts the G-produce and G-assembly sets like K1 and K6, and keeps K4's sheet-and-roll
strengths.

| Group | Meals | Count |
|---|---|---|
| Excluded (5.4) | CK11 DM21 DS13 BF08 AS05 BK06 CK08 BK02 | 8 |
| Out, firm | IN07 samosa (folded cones), CK12 strudel (hand-pulled dough excluded by X-06) | 2 |
| At risk (L–M, out in the central figure) | AS08 spring rolls (1 mm wrapper sheets, L–M), AS09 gyoza (square pockets), MX06 guacamole (avocado chain), BF14 poached egg (vortex on T), DM12 cabbage rolls (whole leaves), DM27 kale (stripping) | 6 |
| Recovered against K4 | apples peeled and cored: BF13, CK03, CS05, DM18, DS14, DS15, FI05, SA12, SD28, SD11; Spätzle press: SD09, IT19, DM28; heads at the blade and cone-cored: CS06, SA05, SP13; garlic: IT03, ME07 and ≈ 40 garlic dishes from (c) to (a); stacks by order on the mat: US01, US02, US07; DM05 cordon bleu (page-turn fold, crimp under the press); DS11 Germknödel (disher, jam injected after steaming, GA-11); SP07 pumpkin; CK16 banana (press-peel); DM33 Maultaschen (1.5 mm sheets, folded and crimped, cut at the blade); IT17 and CK17 (square pockets on the ridge tray, mandated c) | — |
| **Central** | 248 − 8 − 2 − 6 | **232 = 93.5 %** |
| High (at-risk meals in) | | 238 = 96.0 % |
| Low (K4b's own M results fail: running-loop rolling falls back to one large roll, adapted; stacks US01, US02, US07; press-peel CK16, DS10) | | 227 = 91.5 % |

Designer class (c) ≈ 10: IT17 (W3), CK17 (mandated), DS10 (orange rounds, strawberries with calyx), SD19
and SP09 (white asparagus), BK04 (unbraided), Rouladen gherkin coins (detail, not counted), wedges as rounds
for lemon. Weight-3 meals in (c): 1–2. By weight about 95 % [E, by analogy with C1's K1/K6 figure].

### 6.3 Cost (#22 reported; #28: household appliances plus about €2 000 for the machine part)

**Household appliances used largely as bought:** 60 cm oven (≈ €500) in the oven column with an automatic
door (#24); the machine's washer for ware and dishes (≈ €500, shared, not counted here). P3 can be a bought
domino zone with an interface board (−€100 against an OEM module). No commercial appliance.

**Machine part**, design-to-cost at small-series prices [E]; a one-off prototype costs about 1.8 ×:

| Item | € |
|---|---|
| Cell weldment: wet enclosure, table, two store slots with gates, deck with inserts, front strip, funnel | 1 400 |
| Arm: two welded links, coaxial cartridge, three servos with gearing, belts, canned wrist, shoe with EPM | 1 000 |
| Capstan nose E with canned drive and servo; L and G bars | 150 |
| Blade column: ball screw, servo, rod-seal set, beam, bought blade, finger comb, steam park | 350 |
| Press column with helical-cam swing: ball screw 2.5 kN, servo, rod-seal set, arm and plate | 450 |
| P1 coaxial hub T + S (two drawn thimbles, magnet rotors, stepper with planetary, 800 W BLDC); P2 hub T2 | 550 |
| Three OEM induction modules, glass inserts with holes, six load cells | 550 |
| Two solid silicone mats (moulded), two dancers | 250 |
| Wash core: pump, 8 L boiler, 2 kW steam generator, 12 valves, ≈ 30 nozzles, dryer fan and heater, sump | 550 |
| Two cameras with heated windows, gate mirrors, controller, drivers, power supply, sensors | 550 |
| Passive box cradle with load cell, egg fixture, catch fork, plough rails, disher post | 150 |
| Ware ≈ 80 pieces (bought pots and pans with welded tabs, press and lathe sets, tools) | 1 000 |
| Extraction fan, grease filter | 150 |
| **Machine part** | **≈ 7 100** (prototype ≈ 12 800) |

K4b costs about 1.2 × K8b (€5.9 k) and 0.65 × K1b/K6b (≈ €10–11 k). Largest levers for the cost rounds:
the weldment (20 %; the mat bay is two folded boxes and a plate), the ware (14 %), the arm (14 %). The mats
themselves are now 4 % of the cost and 1 % of the yearly wear (6).

---

## 7. Self-assessment

Scores on the critics' 1–10 scales; "before" is the matrix input for K4 (04-decision-matrix 4).

| Criterion (weight) | K4 | K4b [E] | Why |
|---|---|---|---|
| Simplicity (30 %) | 3.8 | **6.0** | 9 actuators, 4 seals, 2 novel (4 strictly), 7 mechanism types, ≈ 53 events, 3 cleaning stations; against: ≈ 80 loose items, 42 custom types, ≈ 28 skills |
| Coverage and food (20 %) | 4 | **7** | 232 central with traditional methods (ricer, Spätzle press, garlic press, disher, rolling pin, fond rule, 4 mm fat, probe, lathe-pared apples); K4's sheet, roll and carve strengths kept; avocado, thin wrappers and cabbage leaves still at risk |
| Hygiene (25 %) | 3 | **6** | 1.7 m² of solid mat, stored hanging, steamed over its full length; no cutting surface; few, visible fixed F parts; unwashed produce never on a mat; against: the fixed blade cuts raw meat (steam park), wet sliders in the slots, the bar above a carried vessel, back face seen only by mirror |
| Mechanics and reliability (15 %) | 3.5 | **5.5** | stiff arm and 12 × lower tension (tracking ≤ 0.5 mrad), pull-down columns and canned hubs are known parts, all drives reachable from the dry room or below the deck; against: one arm is a single point of failure, the running loop and the dovetail-magnet grip in soil need rigs |
| System fit (10 %) | 4.5 | **5** | oven out with front access, wear €130 a year, ≤ 7.5 kW, ≈ 35 L per meal, cost ≈ €7 k; against: the widest improved cell (2.0 m with the oven column, plus washing), no washer inside, 80 ware items through the port |
| **Weighted** | **3.66** | **≈ 6.0** | |

**Remaining weaknesses, honestly ranked:**

1. **Width.** 1 400 mm for the cell without oven and washer — about 0.3–0.5 m more than K8b, K1b or K6b like for
   like. The mat bay (520 mm) is the price of the flat-food skills; the three positions stand in one row
   because the arm reaches only one line in Y.
2. **One arm, serial.** It draws the mat, carries the vessels, holds the pin and the peeler, plates. The
   capstan nose and the turning positions run alone, but four-component menus for 4 persons reach 80–100
   events and sit near the PERF limits.
3. **The mat line is still the novel core**: the first turn in the running loop, release with flour or water
   at the nose, tracking of a solid band, and the steam-and-dry slot are unproven (R1–R4).
4. **The blade is a fixed part that cuts raw meat.** Its steam park makes it defensible (moist heat, logged),
   but it is not ware (C2 R-1 asks for ware or a closed cavity).
5. **More loose parts than K4** (≈ 80 against 41): the press, lathe and tool sets that bring the coverage.
6. **Thin sheets (≤ 1 mm)** depend on about 200 N from the arm on a ringed pin: spring rolls and gyoza stay at
   risk.
7. **Cost** ≈ 3.5 × the #28 target, like every improved concept.

---

## 8. Best ideas for the combined machine (K9b)

1. **Hanging, steamed band store** (N1–N3). A solid silicone band hangs as a U-loop on a passive 5 kg dancer
   in a closed 55 mm slot; it is washed as it retracts and then steamed (A0 ≈ 1 900 s) and hot-air dried in
   place, never wound. Any flexible food surface K9b keeps (rolling apron, sheeting mat) gets a credible
   hygiene case from it; one slot is 55 mm wide and hides under a bench.
2. **Cut past the nose, catch on the band** (N4–N6). A straight-stroke blade on a pull-down column lands on a
   loose anvil stick just past a driven capstan nose; the cut product falls onto the moving band, which
   shingles slices (carving fan, cucumber rows), spaces them (salami on pizza) and delivers trimmings to waste
   by its nose. With the hem parked, it slices into a pocket while the manipulator works elsewhere. A belt
   slicer without a fixed cutting surface.
3. **Vertical lathe from parts K9b already has** (N8). Spike cup on a turning position, the press plate as
   tailstock, the manipulator moving a sprung peeler with depth shoes in Z: pares apples, potatoes, kohlrabi,
   celeriac, citrus, cone-cuts cabbage cores, halves an avocado round its stone. Zero extra drives in K6b,
   K8b or K2b; it is the generic module of #25 for round produce.
4. **Ring-gauged rolling pin on the manipulator, log first, then sheet, then lay down by a moving nose**
   (N9). Thickness from rings, not from manipulator stiffness; 380 × 280 × 4 mm pizza bases and 1.5 mm pasta
   sheets; the sheet is laid on the tray by moving the band end while winding it.
5. **Order on the band = order in the stack; polar plating** (N11, N14). Burger, toast and plates are built by
   lay-down and turntable angle, without any pick-and-place of limp food.

---

## 9. Risks, cheapest kill experiments, open questions

| # | Risk | If true | Cheapest experiment | Cost, time |
|---|---|---|---|---|
| R1 | **Running-loop rolling** on solid silicone does not start the first turn, side folds spring back | Rouladen, wraps, sponge roll, Maultaschen rolls fail; fallback GA-20 raft with rolls made by the K1 slotted mandrel on the arm, or one large Roulade (adapted) | Bench: a driven Ø 20 capstan, a winding bar, a 2 mm silicone sheet, a fixed bar G; 20 Rouladen with and without plough folds, 10 tortillas, 5 sponge rolls | €300, 2 days |
| R2 | **Release** of floured dough and wetted mince at the nose is poor (> 5 % residue) | sheets tear on lay-down, Frikadellen smear | Same rig: dough 60/65 % with dusting flour, Frikadellen mass on a water film; weigh residue after nose transfer | in R1 |
| R3 | **Tracking and life** of a 2 mm solid band at 25 N over Ø 16–20 bars; puncture by bone splinters | mats walk, need flanged guidance or a reinforced band | Same rig unattended, 10 000 draws and 100 000 bends; edge wander by camera; puncture test with a bone splinter under the pin | 1 week |
| R4 | **Slot steam and drying**: cold spots at the anchor, dancer guides, bead roots; mat not dry after 4 min | hygiene case of the mat lost (C2 K4-1 returns) | Slot mock-up (folded sheet, 0.8 m), wallpaper steamer, four loggers; riboflavin and dried egg, mince and dough soils; weigh the mat after drying | €200, 2 days |
| R5 | **Cut quality past the nose**: accordion slices of cucumber and tomato, braised meat tears, 65 mm fall scatters slices | slicing needs a shear edge or a press | A knife on a drill-press stand over a POM stick past a Ø 20 roller, sheet fed by hand: cucumber 2 mm, tomato 6 mm, herbs 1 mm, chicken 20 mm, braised beef 8 mm; count and photograph | €100, 1 day |
| R6 | **Vertical lathe**: impaling fails on hard roots, paring misses knobs, apples settle off-axis | #25 falls back to knurled disc and recipe routes; apples cored only (wedges unpeeled) | Drill-press lathe: spike in a dish, live centre on top, sprung peeler on a hand slide; 20 apples, 10 potatoes, 4 celeriac halves, 4 kohlrabi, 6 avocados | €150, 2 days |
| R7 | **Press 2.5 kN at P1**: onion halves on the 6 mm two-tier grid need more; thrust into the turntable | dice 10 mm only, or a stronger press | Bought push-dicer grid in a Ø 90 tube on a workshop press with a load cell (C3 rec. 11) | €500, 1 day |
| R8 | **Dovetail shoe with electro-permanent magnet** in fat and flour; the pan-pair and rack turns | dropped hot pans | 10 000 grip cycles, soiled; 200 pan-pair turns with 30 mL oil | €1 000, 1 week |
| R9 | **Odour** of mat S after mustard, curry, mince and steam cycles | S becomes a yearly part; D must stay dough-only | Triangle test with butter after 20 cycles (K4 R9) | €50 |

**Open questions and requests**

1. **One washer for ware and dishes** (C5 Q1)? If not, K4b takes the in-cell well option (+360 mm).
2. **Oven column served by the transport** (C5 Q5, Q6), as in K1b, K2b, K8b.
3. **Lids off before the port** (C5 Q7) and **meat slices interleaved** at package opening (G9); otherwise
   Rouladen slices are cut from a block at the blade (M).
4. **Maultaschen as folded rectangles** (traditional, class a?) and **IT17 as square ravioli** (mandated c,
   C5 Q4).
5. **A two-position variant** (P1 + P2, cell 1 120 mm) if the oven column also carries a bought hob zone —
   would close most of the width gap.
6. **Software**: about 28 skills, 8 with vision on deformable food (feed by mat marks, seam angle, stack
   lay-down check, lathe pass check, slice count on the band). Not estimated in effort.
7. **Safety**: two columns (1 kN, 2.5 kN), a blade and a 12 000 rpm hub behind an interlocked household door;
   all motion stops and the blade parks in its hood before the door unlocks (K1's rule).
