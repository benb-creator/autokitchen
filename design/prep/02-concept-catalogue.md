# Meal preparation — concept catalogue (round P2)

Round P2 of Phase 2P (see `PLAN.md`). Input: the six independent idea documents of round P1 in
`design/prep/ideas/`. Output: an inventory of everything proposed, a matrix of hard operations against
mechanisms, a set of eight distinct candidate concepts for round P3, and the findings common to all lenses.

This document does not choose a winner. Its two jobs are that no idea of round P1 is lost, and that
round P3 explores architectures that really differ.

Status of all statements: nothing in round P1 was built or tested. Every force, time, yield and success
rate quoted from the idea documents is a paper estimate of its author. The feasibility notes in section 1
are my first-pass reading of those estimates (H = known practice exists at a comparable scale, M = sound
but needs a bench test, L = speculative or contradicted by another inventor), not an assessment by test.

## 0. Conventions

**Source references.** The six idea documents reuse the letters A–D and the prefixes S, N and M, so every
reference carries the file letter first:

| Prefix | File | Lens | Own numbering |
|---|---|---|---|
| A: | `ideas/A-machine-tool.md` | machine tool | concepts A1–A4, sub-mechanisms M1–M17, tools T1–T16 |
| B: | `ideas/B-process-line.md` | food-industry process line | concepts A–D, sub-mechanisms N1–N24, lids M/I/O/S/K |
| C: | `ideas/C-universal-vessel.md` | the vessel is everything | concepts A–D, sub-mechanisms S-1…S-24 |
| D: | `ideas/D-manipulator.md` | manipulator | concepts A–E, sub-mechanisms N1–N20, utensils U1–U21 |
| E: | `ideas/E-cleaning-first.md` | cleaning first | concepts A–D, sub-mechanisms S1–S20, rules C1–C12 |
| F: | `ideas/F-first-principles.md` | first principles | concepts A–D, sub-mechanisms S1–S47, reordering table §5 |

Example: `B:N6` is sub-mechanism N6 of the process-line document; `C:A` is concept A (STACK) of the
universal-vessel document. Whole-system concepts also get a catalogue number W01–W25 (section 1.1),
sub-mechanisms SM-001…SM-244 (section 1.2), candidate concepts K1–K8 (section 3).

**Convergence.** "n/6" is the number of lenses (files) that reached the idea independently. The inventors
did not see each other's work, so n ≥ 3 is evidence that the idea follows from the problem and not from
the lens. It is not evidence that the idea works: six inventors can share one untested assumption (see
4.2).

**Operation codes** are those of `research/02-meal-corpus.md` (FLP, ASM, …); UO and MEAL numbers are
those of `requirements/requirements.md` section 5.

---

## 1. Inventory

### 1.1 Whole-system concepts (25)

"Alone?" is the author's own verdict on whether the concept is a complete preparation system.

| W | Source | Name | Essence | Alone? | Author's own main weakness |
|---|---|---|---|---|---|
| W01 | A:A1 | TURN-MILL | One main spindle on a tilting trunnion holds a workpiece between centres (peel, slit, part off) or a vessel by its base ring (bowl, drum, pour, dump-flip, spin-dry). All other axes are round rods through the walls. | No | No pick-and-place: fails assemble and carve, poor with flat limp items; 900 wide |
| W02 | A:A2 | CEILING-QUILL FMC | One vertical 3 kN spindle through a flat twin-eccentric-disc ceiling; torque, push rod and fluid through the nose make every tool passive; food knowledge sits in pallets and die cassettes; the spindle washes the cell. | Yes (author's bet) | One quill and two large seals carry everything; strictly serial (60–90 tool changes per meal); grows to two quills, 1200 wide |
| W03 | A:A3 | TURRET PRESS | One fixed ram; upper turret of feed tubes, lower turret of dies, carousel of vessels; food falls from box to tube to die to vessel; die plate washed by rotating through a wash sector. | No | Cannot pick, place, turn or spread; needs an added arm; mass smears on the die plate |
| W04 | A:A4 | BELT & BLADE | Washable homogeneous belt carries food past fixed powered blades in the nose gap; pocket rollers roll Rouladen; one rocker rod carries roller, sifter, platen, syringe; bowl station beside it. | No | 1 m² of flexing polymer to validate after raw meat; weak peeling; needs a bowl station |
| W05 | B:A | FALLTURM | Vertical 180 mm shaft from a tipper dock at 1700 mm down to the vessel; floorless stages (peel/wash/spin disc under a lifting sleeve, cutter disc) swing in; the wash enters at the same dock. | No | Flat items do not fit; 2.3 m² wetted every meal; 15 axes |
| W06 | B:B | TROMMELWERK | One tilting drum Ø 300 × 350 (5–900 rpm, mouth up to mouth down) with loose liners and a swing-in tool arm: washer, spinner, peeler, tumbler, kneader, bowl chopper, rotating induction wok; washes and induction-dries itself. | No (bulk half of the author's bet) | Serial bottleneck; does none of the no-workaround operations |
| W07 | B:C | KOLBENSTRANG | Food as a plug in a 110 mm cartridge with a free piston, pushed by a 10 kN press through exchangeable dies and cut off; piston pigs the bore. | No | "Half a kitchen": no wash, peel, toss, whip, flat items; 10 kN frame |
| W08 | B:D | FLACHBAND | 300 × 800 reversible monolithic belt under a bridge of fixed stations (sifter, curtain, press roller, gang knives, guillotine, curl belt, retracting nose); washed on the return strand. | No (flat half of the author's bet) | No liquids, no mixing, no round produce; station bridge above food is the hardest thing to wash |
| W09 | C:A | STACK | One rim standard (R260); cans, open sleeves and interposer discs stacked in a column with an 8 kN quill above and a turntable below; rim-to-rim inverter; wash lathes. No shaft through any vessel. | Yes (author's bet, with W10 as flat family) | About 49–55 loose parts, 60–90 gantry moves per meal; one Schnitzel per round pan |
| W10 | C:B | SANDWICH | Everything is a bought GN tray; the tray rides a slide under a bridge of fixed heads; two trays with an interposer are inverted as a clamshell; the hob shakes. | No | No native round work (chop, knead, whip, peel, spin); ends with bought appliances a robot must dismantle |
| W11 | C:C | TWIN-SPINDLE | Two or three drums stay chucked on a spindle facing a second coaxial spindle that holds heads or a second vessel; the frame tilts 360°; drums are washed in place in 3 min with induction flash. | No | Flat and formed food foreign; 850 mm swing circle; queueing |
| W12 | C:D | SKIN | Silicone bags with a rigid rim and flat silicone folders; paddles, rollers and platens work on the outside of the skin; bags are emptied and washed by turning them inside out. | No | Cannot cut, cook or whip; odour uptake; unproven kneading and fatigue life |
| W13 | D:A | TWIN TURRET | Two (after corpus check three) disc-in-disc turrets in a flush ceiling, each with one plain rod (X-Y by two rotations, Z, yaw; one rod with a roll elbow); 21 passive utensils; turning, tilting board on load cells; the hand hoses the cell. | Yes (author's bet) | Ceiling seams above food; about 30 utensil skills of software; serial; 1500 wide with three turrets |
| W14 | D:B | WALL PUCK | Zero-penetration cell: a passive magnetic puck on the inside of a flat wall follows an H-bot behind it; a magnet ring turns a spindle in the puck (the horizontal wrist axis). The puck is ware. | No (needs driven vessels) | 60–100 N, 4–8 Nm; puck can drop; no Y axis |
| W15 | D:C | ROLLO | The board is a 320 mm cantilevered belt; a gate of two rods carries guillotine, slitter, sheeting roller, press plate or doctor bar; one turret hand picks and places. | Partly | Belt hygiene; one hand; no roll axis as drawn |
| W16 | D:D | SOCK ARM | Bought six-axis cobot hung from the ceiling inside one inflated, leak-tested silicone sleeve; lever knife for force; board as third hand. | Partly | Sleeve life; 30 N; hardest software; swept volume exceeds 520 mm depth |
| W17 | D:E | SPIT AND STATIONS | Kitchen lathe through the side walls (spindle, tail rod, swing tool rod) for all round produce, eggs and mandrel-wound Rouladen; one turret hand loads it and does flat work on a press table. | No | Only bodies of revolution; the single hand is the bottleneck |
| W18 | E:A | SPÜLZELLE | Preparation inside a dishwasher tub; tools hang in it on pegs and are never taken out; motion enters through two ball ports, a magnet turntable and a magnet spindle; the tub washes itself and everything in it. | Partly | Whole tub soiled and blocked 50 min for one onion; ball seat is a dynamic seal in the food zone |
| W19 | E:B | ALLES IST GESCHIRR | Nothing food-contact is attached to the machine: GN 1/2 steel trays as benches, stem tools gripped above a drip collar, passive cassettes; a 3-minute commercial-type washer as the heartbeat. | Yes (logistics half of the author's bet) | 80–120 handling moves per meal, about 45 loose items in two sets |
| W20 | E:C | KOLBENROHR | Open dairy tube with a loose piston as universal vessel: microtome slicer, dicer, ricer, former, paste syringe, variable-volume chopper, reciprocating-extrusion kneader; cleaned by pigging and pipe flow. | No (needs a flat bench) | Only what can be pushed; kneading and foaming unproven; no liquids |
| W21 | E:D | ZWEI-BAHNEN-KÜCHE | Raw meat, dough and coatings handled between two paper webs from rolls; tools touch only paper; used paper goes to waste. | No | Covers a fifth of operations; consumable; cannot cut on paper |
| W22 | F:A | TUCH | Reel-to-reel reinforced mat between two bars: shuttles food under a rail of fixed tools, hangs as a loop (tumble, toss, fold, knead, roll up), is pulled from under the food at a nose; washed by reeling through spray and steam. | Yes (author's bet, with die head and cold clamp) | Mat life and stickiness unknown; no liquids; one line |
| W23 | F:B | SÄULE | Vertical 8 kN ram pushes food in a sleeve through a revolver of fixed dies with a face rotor; food only falls; the idle half of the revolver sits in a wash box. | No | Only what fits a Ø 140 tube and falls; needs a handler and platen table |
| W24 | F:C | TROMMEL | Washing-machine drum with tilt axis, exchangeable liners and a stator arm through the mouth. | No | No cubes, sheets, Rouladen, assembly |
| W25 | F:D | ZUSTAND | Thermal conditioning before mechanics: a −25 °C double contact plate makes meat, mince and dough rigid in 2–4 min; steam or blanch loosens skins; then a plain gantry with gripper, trays and moulds. | Partly | Plate queue; 14 axes; many loose parts; customer acceptance of surface-frozen meat |

**The inventors' bets.** Every bet is a hybrid, and five of six pair a machine for bulk and round food with
a second machine for flat food:

| Lens | Bet | Bulk / round half | Flat half |
|---|---|---|---|
| A | W02 with W01's spin chuck, W03's dies as cassettes, W04's pocket band as a pallet | spindle + die cassettes | same spindle, pick and place |
| B | W06 + shortened W08, piston box between them | drum | belt |
| C | W09 + the GN 2/3 flat pair of W10, folders from W12 | quill stack | clamshell trays |
| D | W13 in three-turret form, ice chuck, fakir hand, clamshell pan; W15's gate and belt if cutting is the bottleneck; W14 to be explored anyway | two hands on a board | same hands |
| E | W19 with W20 as main cassette, W21 in reserve | tube and piston | loose trays and stem tools |
| F | W22 with W23 reduced to a die head and W25 reduced to one cold clamp | die head | mat |

### 1.2 Sub-mechanisms (SM-001 … SM-244)

Columns: ID; name and essence; sources; conv. = number of lenses; F = first-pass feasibility (H/M/L) with
the main open point. Basic building blocks that several concepts assume (tilt-pour dock, lift-out basket)
are listed too, because the operation matrix of section 2 refers to them.

#### Workholding and orientation

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-001 | **Spike lathe**: round produce between a driven fork/spur and a free tail cup; tools come to it. Pole caps are sacrificial chucking stock. Also as a hand-held spit on a manipulator's roll axis. | A:A1; D:A, D:B, D:E; E:S3 | 3/6 | H for peeling (consumer peelers), M for loading lumpy items on centres (5–10 % retry, D:E). Too small: garlic, shallots |
| SM-002 | **Workpiece in the spindle**: piece stabbed on a three-prong fork with stripper, stood on end first in an orienting cone, then moved past fixed passive tools. | A:A2 | 1/6 | M; depends on a firm, reasonably straight piece |
| SM-003 | **Fakir hand**: comb or needle bed pins produce to the board; the blade runs in the lanes between the tines. As a comb fence it sets the slice pitch for carving. | D:N2, D:U4; E §5 (comb fence) | 2/6 | H (consumer onion holder) |
| SM-004 | **Ice chuck / freeze fixture**: a Peltier-cooled flat steel patch freezes a wet cut face on in 5–15 s; reversed current releases. | A:M9; D:N1 | 2/6 | M; frost in a humid cell; not for RTE cut faces |
| SM-005 | **Helical twin brush rollers**: scrub, align the long axis, convey and hand out one piece at a time; then serve as steady rest. | A:M4 | 1/6 | H as a washer/singulator; brushes are a hygiene item and must be removable ware |
| SM-006 | **Passive self-orientation**: funnel cup (stand on end), three-finger centring cone above a die, off-centre wheel that settles a fruit on its stem cavity, converging rails or V-groove on a belt or board. | A:A2; B:N20; F:S26; A:A4; D:A | 4/6 | M; each aid works for one class of shape |
| SM-007 | **Hold-down roller** just upstream of a cut on a belt or mat. | D:C; F:A | 2/6 | H |
| SM-008 | **Feature board**: turning, tilting board on load cells; variants with V-groove, fulcrum eye, spike row; second coloured board for class R. | D:A, D:D | 1/6 | H; HDPE board is a wear part |

#### Cutting, trimming, coring

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-009 | **Ram through a fixed grid with flush cut-off** ("grid as fixture"): the grid that makes cuts 1 and 2 holds the sticks for cut 3; dice length = advance per cut. | A:A2, A:A3; B:C; C:A; E:B, E:C; F:S6 | 5/6 | H (push dicers, Dynacube). Force 1–5 kN per load; pitch fixed by the die |
| SM-010 | **Staggered or two-tier grid blades** so that only part of the edge engages at once (force ÷ 3–4). | A:A2; C:A; E:C; F:S7 | 4/6 | H |
| SM-011 | **Comb piston / push-out follower / heel pig**: a pusher with the grid's negative (studs, silicone block, sacrificial potato slice, ice puck) drives the last plug through, so the grid reaches the wash free of fibres. | B:A, B:C; C:S-19; F:S8 | 3/6 | H for studs and silicone block, M for ice |
| SM-012 | **Vessel rim as cut-off knife**: a blade bridge or sweep knife on the rim of the rotating receiving vessel cuts what the die extrudes; pieces fall into that vessel; no cut-off actuator. | A:M16; C:A, C:S-2 | 2/6 | H |
| SM-013 | **Receiving vessel is the rotor**: slicing or shredding disc clipped to the rim of a rotating vessel under a stationary feed tube; a food processor without shaft, hub or seal. | C:S-2 | 1/6 | H |
| SM-014 | **Feed-through disc cutter** (slicing disc over dicing grid, vegetable-cutter class), as a stage, a head closing a drum mouth, or a bought unit. | B:A, B:B, B:D; C:B; F:D | 3/6 | H; irregular below 5 mm; chute and discs to wash |
| SM-015 | **Open-mouth microtome**: ram advances the column continuously, a sickle or face blade sweeps the mouth once per revolution; slice thickness = ram speed / sweep rate, freely programmable. | A:A3; B:C; E:C; F:B | 4/6 | H |
| SM-016 | **Fixed powered blade, workpiece under CNC**: tensioned scalloped blade or wire reciprocating 10 mm at 40 Hz; feed force a few newtons; never cuts into an anvil; partial-depth cuts. | A:M15, A:A4 | 1/6 | H (electric carving knife); blade fatigue; onion root stub 10–15 % |
| SM-017 | **Belt-metered guillotine at or just beyond the nose** ("overhang cut"): belt advance sets the slice thickness, the slice falls straight into the vessel, the blade never touches the belt. | A:A4; B:D; D:C | 3/6 | H |
| SM-018 | **Belt dicing in passes**: slabs laid flat, through frame blades or a slitter bar (strips), then cross-cut. | A:A4; B:D; D:C | 3/6 | M; pieces disordered ("statistical" dice); onion slabs fall into rings; slitter discs roll on the belt |
| SM-019 | **Lathe dicing**: meridian cuts to the core with indexing (or chordal cuts), then parting slices; the cook's onion method. | A:A1; D:E; E:S3 | 3/6 | M; 25–60 s per onion; do the cut layers hold until the cross cut? |
| SM-020 | **Cook's method with passive utensils**: halves face down, comb pins, horizontal blade on a Z-shank, vertical blade between the tines, board turns 90°. | D:A (U1, U2, U4) | 1/6 | M; 45 s per onion, about 40 cuts |
| SM-021 | **Lever / pivot knife**: blade tip hooks in a fulcrum eye (3:1), or the knife swings on a spindle normal to the wall (paper-cutter cut). | D:N9, D:B | 1/6 | H |
| SM-022 | **Blade against a soft anvil**: rolling-disc knife and gang wheel, rocking mezzaluna, or a straight blade chopping on a TPU mat that jogs between strokes; for herbs, dough, pastry, slices. | D:N10, D:U3; A:A2 (T9); C:B; F:A (CHOP) | 4/6 | H; needs a surface the edge may touch (wear part) |
| SM-023 | **Zig-zag stamp chopper** on a quill, vessel indexes between strokes. | C:A | 1/6 | H; PE floor insert is a consumable that scores |
| SM-024 | **Top-entering rotary blade in the vessel**: blade stalk, bell-guarded blade, Kutter sickles through a drum mouth, chopper cup with magnet-driven blade lid, blade rotor in a braked liner. No bottom shaft seal. | A:A2 (T7); B:A, B:B; C:A, C:C; E:A, E:B; F:C | 5/6 | H; bruises soft herbs; tilt keeps small quantities under the blade (C:C) |
| SM-025 | **Variable-volume chopper**: blade cap on a tube, the piston sets the chamber volume to the batch and then ejects everything. | E:C | 1/6 | M |
| SM-026 | **Compressed-bundle chiffonade**: herbs or leaves compressed in a tube or under a hold roller and sliced at 1–2 mm steps; second pass turned 90°. | A:A3, A:A4; B:C, B:D; D:C; F:B | 4/6 | H for a clean cut; slow; "fine mince marginal" (A:A3) |
| SM-027 | **Cryo-crumble**: herbs frozen at ingestion and shattered frozen; no blade. | F:S19 | 1/6 | H for cooked dishes; not for fresh garnish; ingestion and freezer interface |
| SM-028 | **Centrifugal slicer**: impeller carries pieces round a stationary ring with a knife gap; thickness independent of shape; no workholding. | F:S27, F:C | 1/6 | M; several knife holders to clean |
| SM-029 | **Mini band knife**, 10–20 m/s, near-zero normal force; wiper and spray box on every turn. | F:S38 | 1/6 | H technically, M for guide hygiene; guarding |
| SM-030 | **Mandoline or grater interposer** between box and tray, the sandwich shaken. | C:B | 1/6 | L–M; random orientation |
| SM-031 | **Sickle carving in the stack**: roast on end in a wide sleeve under a follower, sickle on the rim of the rotating pan takes one slice per turn. | C:S-23 | 1/6 | M; hot braised meat may tear |
| SM-032 | **Draw-knife carving**: roast on a spiked board or behind a comb fence, carving knife drawn or reciprocated by a manipulator. | A:A2; D:A; E §5 | 3/6 | H for boneless roasts |
| SM-033 | **Scoring to a depth stop**: single blade on a programmed path, comb of parallel blades stamped, gang knives or guillotine with depth stop over a belt, tray driven under a fixed blade. | A:A1, A:A2, A:A4; B:D; C:A, C:B; D; E §5; F:A | 6/6 | H |
| SM-034 | **Laser-line portion knife**: cross-section measured as the item is fed, feed per cut computed for a target mass. | D:N16 | 1/6 | H on a belt or turntable |
| SM-035 | **Grating and zesting**: spinning workpiece pressed on a grater plate; or block pushed over a grater die. | D:E; A:M10; C:A (shred disc) | 3/6 | H |
| SM-036 | **Citrus juicing**: halved fruit against a reamer on a spindle, or a cone die under a press. | D:E; B:C; F:B | 3/6 | H |
| SM-037 | **End trimming by probe and part-off, or first-and-last slice to waste** through a diverter. | A §1.5; B:D; C §7.3; F:B, F:A | 4/6 | H for long goods lying along the feed axis |
| SM-038 | **Bundle end trim**: bundle pushed against a fence, or stood upright in a tube, one cut per end. | D §8.3; E §5 | 2/6 | M |
| SM-039 | **Snipper drum** for bean ends, radishes, gooseberries. | B:N22 | 1/6 | M; gap between basket and blade |
| SM-040 | **Tube corer with ejector** along the stalk axis (manipulator tool, hollow tailstock, ram end tool). | A §1.5; D §8.3; E §5 | 3/6 | H for apple, pear; needs the stalk axis found |
| SM-041 | **Corer-wedger die**: radial blades round a centre tube; wedges fall into the vessel, the core goes up or down the tube into a separate receiver. | B:N20; C:S-21; F:B | 3/6 | H apple, L–M pepper (off-centre core, 70 % expected) |
| SM-042 | **Pepper: part off the cap, pull it with the seed core, flush the inside** by a jet while spinning mouth down or with a gouge. | A §1.5; D §8.3; E §5 | 3/6 | M; white ribs remain; vision per vegetable |
| SM-043 | **Cut first, separate seeds afterwards** by tumble-rinse in a perforated basket or through a 6 mm screen. | B:N21; F:S37 | 2/6 | M |
| SM-044 | **Gouge** (sharp-rimmed cup) for eyes, stalks and cores, camera-guided. | D:U6; D:E (T6) | 1/6 | M; software per defect |
| SM-045 | **Floret and stem removal**: blade round the stalk with the head held stalk-up; florets broken by tumbling. | D §8.3; F §4 | 2/6 | L; both authors rate it low |

#### Peeling

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-046 | **Floating sprung blade on a lathe-held workpiece** (peeler traverses pole to pole). | A:A1; D:A, D:B, D:E; E:S3 | 3/6 | H for regular tubers, apples, kohlrabi; eyes and hollows remain without a camera step |
| SM-047 | **Peel ring**: three gimballed floating blades and three rollers; the spinning piece is pushed through (or the ring rotates round a non-rotating piece). | A:A2, A:A3 | 1/6 | M; quality on ugly potatoes is the author's own first check |
| SM-048 | **Iris peeler for long goods**: ring of blades on spring fingers (one-piece flexure, or six sprung blades); carrot, cucumber, asparagus, salsify pushed through. | E:S9; F:S10 | 2/6 | M–H (industrial carrot peelers); crevice-free blade attachment |
| SM-049 | **Abrasive disc under a lifting sleeve** ("rumbler"), also from a rasp floor disc in a sleeve. | B:A; C:A | 2/6 | H (commercial peelers); loss 12–25 %, eyes remain; short carrots only |
| SM-050 | **Abrasive drum liner / rasp drum**. | B:B; C:C; F:C | 3/6 | H; gentler, takes long carrots; bonded grit may shed (use knurled or etched steel) |
| SM-051 | **Roller-bed peeler and washer**: parallel abrasive, brush or rubber rollers in a trough. | B:N13; A:A4 | 2/6 | H; eight shaft seals |
| SM-052 | **Rasp mat in a loop**. | F:A (M5) | 1/6 | M; 4–6 min per 1.5 kg |
| SM-053 | **Belt rolls the piece against a fence** while a sprung peeler traverses. | D:C | 1/6 | M; 85–90 % coverage, gouge touch-up |
| SM-054 | **Thermal-shock peel** in a dry 180 °C induction drum, then quench and rub. | B:N10 | 1/6 | M; scorch taint |
| SM-055 | **Heat first, then slip the skin**: steam or boil skin-on, shock, then rubber fingers, two cups, or a tumble; tomato and peach by blanching. | A §1.5; B:N10; C §7.3; D:N15; E §5; F:S12, F §5 | 6/6 | M–H; not for raw-potato dishes; some uses count as adapted method |
| SM-056 | **Skin-on cooking and ricer**: the ricer plate retains the skins. | A §4; B:C; C:A; E:C; F §5 | 5/6 | H; mash, purée, passata only |
| SM-057 | **Broach-peeling**: outer ring of grid cells leads to waste. | F:S9 | 1/6 | H to build, L on yield (55–70 %, misses PRP-022) |
| SM-058 | **100 bar water-jet peeling**. | E:S15 | 1/6 | L–M; noise, aerosol |
| SM-059 | **Cut-away peeling in facets** on an indexed spit for knobbly produce. | A §1.5; D §8.3; E §5 | 3/6 | H; loss about 30 % |
| SM-060 | **Onion: top, tail, one meridian slit, then a tangential mains-water jet on the spinning onion** (variants: silicone thumb at the score; 600 rpm centrifugal throw; tumble in a basket under jets). | A:M5; D:A, D:E; E:A; F:S11 | 4/6 | M–L; every author asks for a test; wet skins stick to walls |
| SM-061 | **Onion: slit, then rub** in a wet rubber-stud tumbler, on rubber rollers, against a silicone-finger fence on a belt, or in a loop under a roller. | B:N7; A:A4; D:C; F:A | 4/6 | M–L; loses one fleshy layer (10–15 %) |
| SM-062 | **Onion: cold squeeze ring or undersized die**; inner layers pass, skin and first layer stay. | A:A3; C:S-12 | 2/6 | L–M; 85–90 % success or 20–30 % loss |
| SM-063 | **Onion: loosen by steam or blanch (45–60 s), then ring, die or rubber fingers**. | C §7.3; E:S16; F:S12 | 3/6 | M; outer layer slightly cooked (adapted for raw use) |
| SM-064 | **Garlic: press skin-on through a grid or ricer plate**, skin retained; or shake-peel in a closed vessel pair. | C:S-20; D §8.3; E §5; F §4 | 4/6 | H for the press route |
| SM-065 | **Boiled-egg peeling**: craze the shell, then tumble or shake with water (rubber studs, closed tray or can pair). | A §1.5; B §3.1; C:S-20; D §8.1; E §5; F:C | 6/6 | M; yield guesses 70–90 % |

#### Forming and shaping

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-066 | **Extrude through an orifice and cut off**: pucks, dumpling portions, gnocchi blanks, Spätzle over the pot. | A:A1–A4, A:M13; B:A, B:C; C:A, C:D; E:C; F:B | 5/6 | H (factory former); ±3–10 % by stroke |
| SM-067 | **Mould-plate former**: open tube slides on a plate over a cavity, press, shear, knock out. | A:M14 | 1/6 | H for stiff masses; smear on the plate |
| SM-068 | **Slab and ring cutter**: mass pressed or rolled to a slab between rails, pucks stamped, rest re-rolled. | D:A; E:A, E:B | 2/6 | H |
| SM-069 | **Form in the cooking vessel**: press the mass to an even layer in the pan, part it with a divider lid, fry in place, flip the set. | C:S-7 | 1/6 | H; rounded-rectangle Frikadellen (adapted?) |
| SM-070 | **Smash-forming**: drop a weighed portion in the pan and press it flat there. | F §5; B:B | 2/6 | H |
| SM-071 | **Ice-cube-tray forming**: screed the mass into a mould tray or cavity mat, crust-freeze 2–4 min, pop out as rigid parts. | F:S17, F:A (M6) | 1/6 | H; plate time |
| SM-072 | **Log and cut on a belt or mat**: extruded or loop-rolled log, or a sheeted slab, cut by the cross blade by length or by weight; strand rolled under a press plate moving to and fro (a palm) for gnocchi and Schupfnudeln. | A:A4; B:D; D:C, D §8.2; F:A | 4/6 | H for logs and blocks, M for tapered shapes |
| SM-073 | **Orbiting rounder cup** (bakery rounding) for balls, Klöße, rolls; squash afterwards for a closed-edge Frikadelle. | B:N11; D:U13; E:C | 3/6 | H dough, M mince (wet, cold surfaces) |
| SM-074 | **Rounding by tumbling or in a pocket band**. | A:M7; C:C, C §7.2; F:C | 3/6 | M |
| SM-075 | **Core tube with ejector**: takes a core of known volume from butter, paste, mince, dough; Ø 60 × 35 of mince is a formed patty. | F:S4 | 1/6 | M–H; last 15 % of the box |
| SM-076 | **Nozzle filling of rigid cavities** (peppers, tomatoes, apples, cannelloni stood in a rack) from a syringe, piston tube or sleeve; piping. | A §1.5; B §3.1; C §7.2; D §8.2; E §5; F §4 | 6/6 | H for rigid cavities |
| SM-077 | **Flat pocket by fold and pin** (cordon bleu as a Roulade variant). | D §8.2 | 1/6 | M; the only proposal for flat pockets |
| SM-078 | **Ring-build and push-out**: sleeve on a base disc as chef's ring and spring form; layers dosed in, sleeve lifted off. | C:S-22 | 1/6 | H; M for sticky cakes |

#### Flat and limp items: rolling, securing, coating, sheeting, assembling

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-079 | **Pocket band / roll loop / loop roller**: slack loop between two bars or rollers; the filled slice sags in, the rollers close, the band is driven and the content rolls up contained all round. | A:M7; B:N2; E:S11; F:S14 | 4/6 | M–H; starting the first turn, filling squeezed out at the ends |
| SM-080 | **Apron or mat roll** (sushi mat): one edge of the mat lifted and carried over, or the hem drawn over a fixed bar by the tray's own travel. | C:S-6, C:B, C:D; D:A, D:B, D:D; E:A | 3/6 | M; C's own estimate 80 % first-time success |
| SM-081 | **Curl on a belt**: leading edge climbs a curl belt or doctor bar running against the feed (bakery croissant curling). | B:D; D:C | 2/6 | M; filling pushed ahead of the roll |
| SM-082 | **Mandrel winding**: slotted mandrel grips the leading edge, 2.5 turns, stripped axially. | A:A1; D:E | 2/6 | M |
| SM-083 | **Closing U-cradle** (hinged or silicone), like a dumpling press. | F:B, F:D | 1/6 | M–L |
| SM-084 | **Seam-down fixture that stays with the workpiece**: comb rack, channel or trough insert, sleeves; rolls packed against each other, seam seared first, braised and lifted out in it. No tying. | A:M8; B:N3; C:S-6; E:S11; F §5 | 5/6 | H as a part, **unproven through a two-hour braise** (all five say so); browning shadowed |
| SM-085 | **Pins**: stainless pin through the seam by a guided setter; ferritic pins counted out against in by a magnet at plating. | D:U20; E:A; F:S15 | 3/6 | H; traditional method |
| SM-086 | **Snap C-ring** of spring steel pushed on radially. | D:N5; C:S-6 (fallback) | 2/6 | H; pale stripes |
| SM-087 | **Ice-weld seam**: freeze the closed roll 3–4 min, sear seam-down. | F:S16 | 1/6 | M–L |
| SM-088 | **Hot-bar seam bonding** (5 s at 200 °C with salt). | E:S11 | 1/6 | L–M |
| SM-089 | **Platen flattening** at 0.5–1.5 kN on spacers. | A:A2, A:A3; B:N1; C:A, C:B; D:E; E:D; F:B | 6/6 | H |
| SM-090 | **Roller / nip flattening** in passes over a belt, mat or board. | A:A4; B:D; D:C; F:A | 4/6 | H |
| SM-091 | **Work between two flexible sheets**: silicone folder, two silicone mats, two paper webs, sacrificial paper interleaf; tools touch only the back of the sheet; the sheet is peeled off at 150–180°. | C:D; D:C, D:N20; E:B, E:D | 3/6 | H (cook's method); silicone odour, paper consumable |
| SM-092 | **Flat-bed breading on a belt**: sifter, egg curtain or syringe, crumb bed, press roller, flip, second side. | A:A4; B:D; D:C | 3/6 | H (industrial); about 30 % crumb waste |
| SM-093 | **Breading by flipping** between three closed shallow vessels with a rack interposer; no gripper touches the cutlet. | C:S-5 | 1/6 | H; about 8 inversions per cutlet |
| SM-094 | **Three trays with fork, tongs or gripper**; with a tempered (rigid) cutlet it becomes a dip process. | A:A2; D:A; E:A, E:B; F:D | 4/6 | M–H |
| SM-095 | **Breading in a closed flexible "bag"**: mat loop or silicone folder, coatings dosed to what adheres. | C:D; F:A | 2/6 | M |
| SM-096 | **Tumble coating** for cubes, strips, nuggets, balls. | B:B; C:C; F:C | 3/6 | H for small pieces; not for cutlets |
| SM-097 | **Spin-coat**: egg wash on a cutlet, crêpe batter in a pan, pizza sauce spiral, by rotating the platen or pan. | A:A1, A:M16; C:S-15; F:S47 | 3/6 | M–H batter, L dough |
| SM-098 | **Freeze-plate gripper**: flat −10 °C plate freezes the surface film and lifts exactly one slice; heat pulse releases. | A:M9; C:S-3; D:N19; E:S6 | 4/6 | M; fails on fatty, dry or floured surfaces; needs power or a cold-charged mass |
| SM-099 | **Vacuum cup or suction plate** for slices, bacon, pasta sheets, eggs. | A:A2; B:N23; D:U18 | 3/6 | M; clogging, vacuum line to clean |
| SM-100 | **Create slices one at a time** from a tempered block (blade or band knife), each landing on its own carrier; avoids singulating a bought stack. | F:A, F:D | 1/6 | H; conflicts with buying cut slices (MEAL-012 a allows both) |
| SM-101 | **Nose transfer**: belt or mat pulled out from under the item round a thin nose bar; pick-up and lay-down without sliding. | A:A4; B:D, B:N4; D:C; E:D; F:S21 | 5/6 | H (bakery peel) |
| SM-102 | **Band spatula**: powered PTFE-glass belt on an 8 mm nose crawls under a steak in the pan. | B:N4 | 1/6 | M–H; belt cassette washed after every use |
| SM-103 | **Book flipper**: two leaves hinged like a book, 2 kN closing; flips, breads both sides, flattens, presses sheets and patties. | B:N1; E:D (book-flip table) | 2/6 | H |
| SM-104 | **Reversing sheeter**: belt or mat under a roller whose gap steps down. | A:A4; B:D; D:C; F:A | 4/6 | H; tray-size rectangular sheets |
| SM-105 | **Cone roller on a rotating platen** (potter's jigger): round sheet to the platen diameter. | A:A1, A:A2; C:S-15 | 2/6 | H; round only |
| SM-106 | **Roller over gauge rails in a tray or between two sheets**; rolling pin utensil. | C:B; D:U12; E:B, E:D | 3/6 | H |
| SM-107 | **Other sheeting**: platen-pressed disc, slot-die ribbon laid side by side, band formed on a drum wall, spin. | A:A3; B:C, B:B, B:N1; E:C; F:B, F:S47 | 4/6 | L–M; all rated second-rate by their authors |
| SM-108 | **Assembly by moving the dish under fixed depositors** (slot die, sifter, sheet dropper). | B:N23; C:B; A:A4 | 3/6 | H for sauce and sprinkle layers |
| SM-109 | **Assembly by pick and place** with tongs, fork, vacuum cup, freeze plate, turner, top-down camera. | A:A2; D:A, D:D; E:B; F:D | 4/6 | M; software |
| SM-110 | **Spreading**: slot-die ribbon; syringe raster plus paddle; roller at 1–2 mm gap; spatula. | A:A2; B:C, B:D; C:B; D:A; E:C; F:A | 6/6 | H |

#### Transfer and pouring

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-111 | **Rim-to-rim inversion ("hourglass")**: two vessels with equal rims clamped mouth to mouth and turned over. Closed transfer without pouring arc, dust or dribble. | C rule 2; E:S4 | 2/6 for transfer (6/6 as flip, SM-127) | H; needs equal rims and a gasket; max fill about 60 % for hot liquids |
| SM-112 | **Interposer between two rims** turns a transfer into an operation (strainer, grid, ricer, rack, gate). | C rule 3 | 1/6 | H |
| SM-113 | **Passive pivot pour**: vessel hung by a rim hook or base ring on a fixed bar; a vertical lift of the far side pours it (to 120°). | A:A2 (pour bracket, M17); D:N4 | 2/6 | H; vessels to about 6 kg |
| SM-114 | **Powered vessel inverter**: trunnion, "Wender", frame tilt. | A:A1, A:A3; C:A, C:C | 2/6 | H |
| SM-115 | **Tilt-pour with a fixed scraper on the rotating wall**. | A:A1; B:B; C:C | 3/6 | M; residue ≤ 2 % claimed for dough, unmeasured |
| SM-116 | **Reversing-helix discharge**: one direction mixes, the other screws the charge out in portions. | B:N8; C:C; F:S28 | 3/6 | H for loose pieces, useless for pastes |
| SM-117 | **Push-up floor / piston vessel / pigged tube**: loose piston floor empties sticky contents to ≤ 1 % and meters by stroke; tube and disc fall apart for washing. | A:M13; B:N5, B:C; C:A; E:C, E:S10; F:B | 5/6 | H round, M rectangular; not liquid-tight |
| SM-118 | **Eversion**: soft vessel turned inside out over a mandrel. | C:S-16 | 1/6 | M; durability, odour |
| SM-119 | **Recipe liquid as chase**: the water, stock or milk of the recipe is dosed last through the soiled path, over the board, or as a rinse of the emptied vessel into the pot. | B:N9; D:N14; F:S42 | 3/6 | H; costs nothing |
| SM-120 | **Gravity cascade**: dock above, processing in the middle, vessel below; food only falls. | A:A3; B:A, B §0; D:B; F:B | 4/6 | H; drop into hot fat not acceptable (vessel lift) |
| SM-121 | **Flume / hydro-transfer** of cut vegetables in water. | E:S18; F:S37 | 2/6 | M |
| SM-122 | **Tools ride with their vessel**: a rim holder carries the tools that vessel needs, in and out. | A:M12 | 1/6 | H; costs spare tools |
| SM-123 | **Parts-catcher / diverter flap** under the cut: product to the vessel, waste to the chip chute. | A §0.1; B:A; D:E; F:B | 4/6 | H |
| SM-124 | **Clamshell scoop**: tongs, scoop, ladle and ball mould in one tool with the hinge out of the food. | F:S5 | 1/6 | H |
| SM-125 | **Tray tipped over a corner spout with a following squeegee; board tilted with a scraper**. | D:A; E:B | 2/6 | H |
| SM-126 | **Wild cards**: planar-motor levitating vessel carriers; vacuum wand for granules (listed by its author to be rejected). | D:N18; F:S30 | — | L |

#### Flipping

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-127 | **Double-pan inversion**: second preheated, oiled pan set face down on the first, pair turned 180°, upper pan lifted off. Everything in the pan turns at once; nothing goes under the food. | A:M17; B:N1; C:A–C; D:N13; E:S4; F:S20 | **6/6** | H; needs a second hot pan and position, little fat (< 30 mL) or drained first; 36 cm pan pair is heavy |
| SM-128 | **Flip lid**: preheated flat steel disc with a 10 mm rim instead of a second pan; item slid back. | E:S4 | 1/6 | M–H; 28 cm pan only |
| SM-129 | **Turner on a horizontal roll axis**, with a counter-holder; angle-head turner; pancake turner. | A:A2 (T11); D:A, D:B, D:D; E:B | 3/6 | H patties, steaks, cutlets; pancakes doubtful (D5 in the corpus) |
| SM-130 | **Belt-nose or curl-belt flip**: item dropped over a nose onto a lower surface lands turned. | A:A4; B:D; F:S21 | 3/6 | M; before the pan, or with SM-102 in the pan |
| SM-131 | **Turning loose pieces by tumbling or by a shaking hob** (slip-stick conveying against a curved end wall). | B:B; C:S-4, C:C; F:C | 3/6 | H in a drum, M shaking hob (liquids slosh) |
| SM-132 | **No flip**: two-sided contact heat, heated platen lid, top heat for thick omelettes. | A:A3, A:A4; B §3.1; C:B; F §5 | 4/6 | H; adapted method for steak; cooking-module feature |

#### Dosing

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-133 | **Dock tilt-pour with vibration and weight feedback** (box tilted 0–135/180° about its pour edge). | A §0.2; B §1.1; E §0; F §2 | 4/6 | H for free-flowing goods |
| SM-134 | **Own-lid dosing**: the dosing element stays on the box for its whole filling cycle and is washed with it; the machine only actuates it from outside. | B §1.1; C:A (sifter inserts); D (wiper insert for SM-140); E:B (sifter lid); F:S1, F:S2 | 5/6 | H as a principle; **changes the box standard** (section 4.3) |
| SM-135 | **Vibration-gated mesh**: cohesive powder arches on a 1–2 mm mesh and flows only while vibrated. | B:N17; C:S-11; F:S2 | 3/6 | H flour and spices, M in a humid kitchen; free-flowing crystals dribble |
| SM-136 | **Hourglass orifice**: flow independent of fill level (Beverloo); dose by time, trim by scale. | C:S-11; F:S1 | 2/6 | H granules only |
| SM-137 | **Iris-sleeve lid and duckbill spout lid**. | B §1.1 | 1/6 | M; two more lid types |
| SM-138 | **Box inverted onto a collar** (orifice, sieve, piece chute, spout) in the inverter; the box is the hopper for seconds. | C:A, C:B | 1/6 | M; box must fit the rim |
| SM-139 | **Scoop, spoon or ladle on a roll axis**, dumped by rotation, trickled with yaw dither; spoon scraped by a second hand. | D:A, D:B, D:D | 1/6 | H; 20–40 s per dose; no bridging problem |
| SM-140 | **Spice wand**: grooved pin through a wiper hole, 0.1 mL per dip, thrown off by spin. | D:N11 | 1/6 | M–H; oily spices pack |
| SM-141 | **Seasoning weighed into a small cup in dry air and carried to the pot** (weigh cup on a 200–300 g cell; clamshell-bottom carrier cup; beaker inverted onto the pot). | A §0.2; B:N19; C:A, C:C | 3/6 | H |
| SM-142 | **Downdraft shaft / steam lock** at the dosing opening. | B:N16 | 1/6 | H; air must be condensed and filtered |
| SM-143 | **Salt as brine** (and sugar syrup, starch slurry) dosed by volume. | F:S31 | 1/6 | H; changes nothing on the plate |
| SM-144 | **Air-displacement pipette / syringe tool**: only the tip or barrel is wetted. | A:A2 (T10); D:U17; F:S3 | 3/6 | H thin liquids; film with oil and cream |
| SM-145 | **Water (and air, vacuum) through the spindle, rod or lid hub**. | A:M2; C:A; D:N7 | 3/6 | H |
| SM-146 | **Piston box**: prismatic box with a loose follower floor, pushed by a dock ram, strand cut by a wire. | A:M13; B §1.1 (K), B:N5; E:S10 | 3/6 | M–H; **no draft, lip seal at −25 °C, ram hole in the storage grid** (section 4.3) |
| SM-147 | **Freeze to count; dice blocks once, then count**: pastes frozen in 5 g and 20 g cells, butter and cheese diced when the pack is opened; dosed as pieces. | C:S-9, C:S-24 | 1/6 | H; ingestion and freezer interface |
| SM-148 | **Dose by cutting from bar stock**: frozen or chilled block grated until the scale says stop; butter cut by length. | A:M10; D:A | 2/6 | H for butter, cheese, frozen paste |
| SM-149 | **Pouch squeezer**: two rollers travel a measured distance down a pouch or tube. | C:S-10, C:D | 1/6 | H |
| SM-150 | **Piece dosing by pulse-tilt or singulation with camera and scale**. | A:M4; B §1.1 (O); C:A; D:C; E:B; F §2 | 6/6 | M; resolution is one piece |
| SM-151 | **The recipe follows the scale**: take what comes out, weigh it, scale seasoning, liquid and time. | C:S-14 | 1/6 | H; control rule |
| SM-152 | **Pick pieces** with tongs, fork (impale) or two-rod pinch. | A:A2; D:A; E:A | 3/6 | H for firm pieces |
| SM-153 | **Leafy goods**: handfuls by tongs or two forks with weighing; or the whole box emptied and the surplus kept cold. | A:A2; C:A; D:A; E:A; F:A | 5/6 | M; ±10 g at best |
| SM-154 | **Box-in-box colander**: produce stored in a perforated liner that lifts out as wash basket. | F:S32 | 1/6 | H; one more ware type |

#### Draining, washing and drying of food

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-155 | **Lift-out perforated basket**, held 20 s over the pot. | A:A2; B:A; C §7.5; D; E §0 | 5/6 | H; R4's recommendation |
| SM-156 | **Strainer lid or mouth sieve and tilt** into the cell drain or a closed chute. | A:A1, A:A3; B:A, B:B; C:C | 3/6 | H up to about 6 kg |
| SM-157 | **Three-layer inversion**: pot / strainer / empty pot; solids return to their own pot, liquid is caught. | C:S-13 | 1/6 | H; not for the full 9 L pot |
| SM-158 | **Venturi drain wand**: mains-water ejector sucks the cooking water out through a slotted tip. | F:S41 | 1/6 | H; 7 L motive water per 4 L pot |
| SM-159 | **Spin basket** on a chuck or spindle: wash with reversing rotation, spin-dry at 40–110 g. | A:A1, A:A2; C:A; D:E; E:A, E:B | 4/6 | H; imbalance |
| SM-160 | **French-press piston** and press against a fine die (UO-36). | B:C; C:S-18 | 2/6 | H |
| SM-161 | **Mangle**: mesh belt folded round the food through a nip; rices cooked flesh, wrings grated potato. | F:S13 | 1/6 | M–H |
| SM-162 | **Flotation wash** with a weir and sand trap. | F:S37 | 1/6 | M–H |
| SM-163 | **Perforated mat**: wash in the loop, spin the rolled-up mat. | F:A (M3) | 1/6 | M |

#### Egg

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-164 | **Score the equator between two cups and pull apart**: egg held at its poles by two suction cups, rotated once against a carbide scribe or toothed wheel (or a blade from below), cups pull apart with a twist; contents drop untouched, each cup keeps its half shell. | A:M6; B:N6; C:S-8; D:N6, D:E; F:S22 | **5/6** | M; shell thickness 0.3–0.45 mm needs scribe force control; vacuum lines need a trap |
| SM-165 | **Blade-and-spread cracker** (conventional): as a cassette worked by one ram stroke, a wall anvil with cam-spread blades, or a push-rod tool. | A:A2; C:A, C:B; D:A; E:B | 4/6 | H (existing kinematics); pin hinges to wash |
| SM-166 | **Tap on an edge and pull apart**. | D:D; E:A | 2/6 | M; about 90 % clean |
| SM-167 | **Decap**: egg topper scores a circle on the blunt end, cap lifted, egg inverted. | E:S17 | 1/6 | M; yolk through Ø 32 |
| SM-168 | **Inspect before commit**: egg opened into a clear cup or saucer on a scale, camera checks shell and yolk, then tipped in. | C:A; D:A; E:A, E:B; F:S22 | 4/6 | H |
| SM-169 | **Separation**: slotted cup or saucer; tilted lower half-shell holds the yolk; soft wide suction tip lifts the yolk. | A:M6; B §3.1; C:S-8; D:E; E §5; F:S22 | 6/6 | M |
| SM-170 | **Poaching cup** (rigid cup vessel, or floated silicone cup everted). | A §1.5; C §7.1 | 2/6 | M; one meal |

#### Dough, mixing, whipping

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-171 | **Rotating vessel against a fixed roller and scraper** (Ankarsrum principle): bowl, pot, drum or liner turns, the tool is only held; no seal. | A:A1; B:A, B:B; C:A, C:C; E:A, E:B; F:B, F:C, F:D | **5/6** | H (proven: 5 kg on 600 W); 10–20 Nm at 60–100 rpm |
| SM-172 | **Hook on the manipulator**: planetary by kinematics (tool orbits while yaw spins, programmable radius), or hook in the spindle with the bowl counter-rotating. | A:A2; D:N17 | 2/6 | H; needs 15–20 Nm on the tool axis |
| SM-173 | **Reciprocating extrusion** between two piston tubes through an orifice plate (kneads, mixes mince). | B:C; E:C | 2/6 | M–L; both authors doubt gluten development |
| SM-174 | **Loop fold and nip**: fold in the mat loop, flatten under the roller, 40–60 cycles. | F:A | 1/6 | M; a sheeter (dough-brake) method |
| SM-175 | **Walker**: paddles knead through the wall of a hanging silicone bag. | C:D | 1/6 | M–L at 1.5 kg |
| SM-176 | **Small-quantity vessel**: insert, cup or small beaker on the common interface for one egg white or 100 g of dough. | A §0.2; B §3.1; C §7.5; D §8.4; F:C (L7) | 5/6 | H; required by PRP-038 |
| SM-177 | **Whipping and emulsifying**: a top-driven whisk in a small vessel is the standard answer of all lenses (whisk stalk through a splash lid, whisk lid on a tube, whisk on the manipulator's yaw axis, driven whisk head in a drum insert). Alternative: forcing through a mesh or orifice plate between two piston tubes (two-syringe method); eggs whisked in a bag by the walker. | A:A2 (T5); B:C; C:A, C:D; D:U11; E:B, E:C; F:C | 6/6 whisk; 1/6 extrusion | H whisk; L–M foams by extrusion, H emulsions |
| SM-178 | **Proofing in the working vessel** (low induction power on a slowly turning drum; covered loop). | B:B; F:A | 2/6 | H |

#### Stirring, mashing, tossing

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-179 | **Rotating scraper lid** on a light hob quill: one welded piece following floor, corner and wall; hollow hub for liquids. | C:A | 1/6 | H |
| SM-180 | **Pot turns on its hob drive against a loose scraper hung on the rim**. | E:B | 1/6 | H; needs rotating hob positions |
| SM-181 | **Rotation of a tilted drum with a fin** (rotating wok). | B:B; C:C | 2/6 | H (commercial wok robots) |
| SM-182 | **Shaking hob; tray shuttling under a fixed wiper bar**. | C:S-4, C:B | 1/6 | M; about 1.2 L liquid limit |
| SM-183 | **Stirring tool on the manipulator** (paddle on the spindle; "cook hand"). | A:A2 (T6); D §8.4; E:B | 3/6 | H; occupies the manipulator or needs a dedicated one |
| SM-184 | **Ricer press**: plunger or piston drives cooked potato through 2.5–3 mm holes (also as a French press in the pot, plate left in). | A:A1–A3; B:C; C:A; E:B, E:C; F:B | 5/6 | H; 1–4 kN |
| SM-185 | **Grid masher** driven on a raster to the pot floor; masher plate or grid held in a rotating vessel. | B:A, B:B; C:C; D:A | 3/6 | H; "Stampf" texture in the drum variant |
| SM-186 | **Tumble toss in a closed or lidded vessel** (drum mode, vessel pair in an inverter, lidded tray inverted, salad drum chucked on a lathe). | A:A1, A:A3; B:B; C:A–C; D:E; E:B; F:C | 6/6 | H |
| SM-187 | **Toss with two tools or in the mat loop**. | A:A2; D:A; F:A | 3/6 | H |

#### Cleaning

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-188 | **The manipulator washes the cell**: spindle- or rod-held rotary jet head on a fixed programmed path at constant stand-off; coverage is a program, validated once. | A:M11; D:A (U21) | 2/6 | H where an axis reaches all walls and nothing is fixed in the cell |
| SM-189 | **Spinning faceplate as wash impeller**, swept by the tilt axis. | A:A1 | 1/6 | M |
| SM-190 | **Wash where the tool parks**: holster pockets with jets aimed at that tool; form-fitting sheath with 3 mm gap and 1.5 m/s pipe flow; torpedo core for tubes; tool rod withdrawn into a CIP tube on the dry side. | A:A2; D:E; E:S2, E:C | 3/6 | H simple tools, M whisks; holster rinse is not the validated disinfecting cycle |
| SM-191 | **Rod car-wash collar**: ring nozzle, scraper, drained lantern chamber, dry seal, air purge at every penetration. | A §0.2; D:N8 | 2/6 | H (hygienic rod-seal practice); wear part |
| SM-192 | **Wash lathe / spin-rinse-dry**: axisymmetric part rotated past one fixed meridian of jets, then spun. | C:S-1; E:S14 | 2/6 | H; argues for round ware with one rim |
| SM-193 | **Self-washing drum**: liquor, tumble with reversal, lance, drain, spin. | B:B; C:C; F:C | 3/6 | H; liner-to-shell gap is the biofilm site |
| SM-194 | **Tools washed inside the dirty vessel** during that vessel's own wash. | A:A3; B:B; C:S-17; F:C | 4/6 | M; faces turned away from the jet |
| SM-195 | **Belt or mat washed on its return run or by reeling through** a scraper, spray bars, hot or steam pass and air knife; tension released to reach the inner face. | A:A4; B:D; D:C; F:S23 | 4/6 | H for homogeneous belts; edges, inner face and rollers need a riboflavin test |
| SM-196 | **Turret washed on its idle half**: die plate rotates through a fixed wash sector or wash box behind lip seals. | A:A3; F:S24 | 2/6 | M–H; lip seals |
| SM-197 | **Wash cartridge docked where the food box docks**; wash follows the food path. | B:A | 1/6 | H |
| SM-198 | **Jet gate**: fixed plane of fan nozzles; the manipulator passes each tool through it, turning it. | E:S5 | 1/6 | H |
| SM-199 | **Steam gate** for a blade between two ingredients. | E:S20 | 1/6 | H |
| SM-200 | **Dishwasher tub as the cell**, fixed validated load pattern, tools never leave. | E:A | 1/6 | M; 50 min blocked |
| SM-201 | **Wash as you go**: all-steel ware, tank washer with 85 °C rinse, 3–4 min per rack. | E:B | 1/6 | H (commercial); noise, pH 12–13 |
| SM-202 | **Drip-collar stem**: every tool has a knob above a conical collar; the gripper touches only the knob. | E:S1 | 1/6 | H; limits reach into narrow vessels |
| SM-203 | **Magnet-parked utensils** on a bare wall. | D:N12 | 1/6 | H |
| SM-204 | **Throw the surface away**: paper webs, interleaf sheets, paper mould liners. | D:N20; E:D | 2/6 | H; consumable against HUM-004/GEN-003; not for cutting |
| SM-205 | **Flash pyrolysis** of plain steel grids and plates on an induction coil (450 °C). | E:S7 | 1/6 | M as weekly reset; heat tint, smoke |
| SM-206 | **Pigs**: bread slice through tube and grid into the Frikadellen mass; ice slurry. | B:N18; E:S8; F:S8 | 3/6 | H bread, L–M ice |
| SM-207 | **Verification aids**: witness coupon in each class-R rack; weekly riboflavin self-test under UV; mirror ware with stripe projection; bore camera; part rotating past one camera; small wash loops for sensitive turbidity. | A:M11; C:S-1; E:S12, E:S13, E:S19, E rule C11 | 3/6 | H |
| SM-208 | **Sequencing and duplicate ware**: dry before wet, RTE before raw, raw animal food last; green and red ware sets; second board for class R. | D:A; E rule C9 | 2/6 | H; removes most mid-meal washes |
| SM-209 | **Waste path**: perforated chip box carried off like a box; rotating drum strainer back-flushed to the bio bin; wedge-wire screen with screw. No macerator. | A §0.2; B:A; E:A | 3/6 | H |
| SM-210 | **Cleaning heads that hang above food**: wash tray with upward nozzles driven under the bridge; lift-out bridge; spray from between the belt strands. | B:D; C:B | 2/6 | M; least certain riboflavin result (B's own words) |
| SM-211 | **Inflated sleeve with pressure-decay test and "shower dance"**. | D:D | 1/6 | M; sleeve fatigue |

#### Drying of ware and cell

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-212 | **Induction flash-dry and thermal disinfection**: wet ferritic or tri-ply ware heated to 105–110 °C for 30–60 s by a coil (in the wash chamber, or the drum's own coil). | B:N15, B:B; C:S-1, C:C | 2/6 | H simple rotational shapes, M even heating; not for blades or polymers; constrains the ware material |
| SM-213 | **Spin-dry** vessels, baskets, racks, rotary tools (60–110 g). | A:M16; B:B; C:S-1; E:S14; F:S25 | 5/6 | H |
| SM-214 | **Squeegee tool** for flat walls and deck. | A:A2 (T16); D:U19, D:B; E:B | 3/6 | H |
| SM-215 | **Thin or hot parts dry themselves**: steel ware leaving an 80–85 °C rinse; 1 mm mat through a steam bar. | E rule C5; F:A | 2/6 | H steel, M mats; plastics and silicone stay wet |
| SM-216 | **Heated ceiling and dry-air purge** against condensate above food. | D:A | 1/6 | H |

#### Vessel and rim standards

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-217 | **One round rim for all vessels** (R260 family: cans, sleeves, interposer discs, hat-shaped beakers that nest). | C:A; E:S4, E:S14 | 2/6 | H; GN 1/6 box fits inside, GN 1/3 does not |
| SM-218 | **Base ring with three tapered lugs** (bayonet "zero-point clamp") common to chuck, hob, wash rack and gripper; drive notches in the skirt. | A §0.2; C:S-2; B:A (base flange) | 3/6 | H; architecture must freeze it |
| SM-219 | **Rim with pivot hook and bail pocket** on every vessel and box (for SM-113). | D:N4 | 1/6 | H; affects the box |
| SM-220 | **GN trays as universal ware**: bench, vessel, pan (thermoplate), roasting tin, oven tray, breading tray. | C:B; E:B; D:A (GN 1/6 trays) | 3/6 | H; bought; rectangular ware does not spin |
| SM-221 | **Drum with exchangeable loose liners** (smooth, perforated, rasp, rubber-stud, helix, slicing ring, small insert). | B:B; C:C; F:C | 3/6 | H |
| SM-222 | **Exchangeable mats** as the vessel set (silicone-glass, TPU, perforated, mesh, rasp, cavity). | F:A | 1/6 | M; life unknown |
| SM-223 | **Soft everting bag with a rigid rim; die rings on the rim**. | C:D | 1/6 | M |
| SM-224 | **Flat GN 2/3 pair beside the round family** for frying and braising for six (equals a 36 cm pan; twelve Rouladen). | C §6, §7.5 | 1/6 | H; two rim standards in one inverter |
| SM-225 | **Bowl rotates, pan rotates**: every heated or mixing position has a turntable (needed by SM-012, -013, -097, -105, -171, -180). | A; C; E:B | 3/6 | H; cooking-module interface |

#### Manipulators, penetrations, drives

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-226 | **Twin-eccentric disc penetration** (disc-in-disc SCARA flush in the ceiling): two rotations place a rod anywhere in a circle; only rotary seals face the food. | A:M3; D:A | **2/6, independently** | M; seal length 2.4 m per turret, seams above food, slewing-ring stiffness under press load; fallback gantry behind a cover |
| SM-227 | **Only round things cross the wall**: rotary seals and rod seals, no slots, bellows or guides in the cell; all bars cantilevered from one wall. | A §0.1; D §0.1; F:A | 3/6 | H |
| SM-228 | **Ball port**: polished rod through a sealed ball (hot-cell manipulator). | E:A | 1/6 | M; polar kinematics poor for flat work |
| SM-229 | **Magnetic through-wall drive**: puck following an H-bot behind a flat wall with a magnet-ring spindle; magnet-coupled turntable, high-speed spindle, jaw. | D:B; E:A, E:B | 2/6 | M; 60–100 N, 4–8 Nm; NdFeB below 80 °C |
| SM-230 | **Sleeved bought cobot**. | D:D | 1/6 | M; software |
| SM-231 | **Gantry in a dry slot behind a labyrinth**, closed-tube arm with tilt and spin wrist. | E:B; C (transport gantry); F:D | 3/6 | H; slot and arm are Zone S |
| SM-232 | **One rod as a gantry**: rocker rod that slides and rocks to select stations; gate of two rods; Swiss-lathe tool bar. | A:A1, A:A4; D:C, D:E | 2/6 | H |
| SM-233 | **Three-media tool interface**: torque, a push rod and a fluid channel (water, air, vacuum) through the spindle or rod, so every tool is passive. | A:M2; D:N7 | 2/6 | H |
| SM-234 | **Tool pick-up without a changer actuator**: hydraulic expansion mandrel in a plain H7 bore; bayonet using Z and yaw; taper bayonet. | A:M1; D:A; E:A | 3/6 | M–H; soil in the bore stops a change |
| SM-235 | **Two rods as a parallel gripper** for large objects. | D:A | 1/6 | H |
| SM-236 | **Contact-free sealing of turntables and posts**: umbrella labyrinth, raised boss, diaphragm-sealed load-cell posts. | A:A2; C:A; D:N3 | 3/6 | H |
| SM-237 | **Mains-water hydraulic press** (rolling-diaphragm cylinder, 4–10 kN at 2.2–5 bar). | B:N14 | 1/6 | M; EN 1717 backflow |
| SM-238 | **Force sensing outside the cell**: load cells under the board or platen, fork load pins, swing-motor current, weighing with the Z axis. | A §2; C:A; D:N3, D:C, D:E | 3/6 | H |
| SM-239 | **Canned cycles with probe, process and verify step**; blade check after every cut (PRP-035); adaptive feed on torque and force. | A §0.3 | 1/6 | H |

#### Thermal tricks and recipe reordering

| ID | Mechanism | Sources | Conv. | F and note |
|---|---|---|---|---|
| SM-240 | **Temper before handling**: crust-freeze meat, mince, bacon, fish, butter on a −25 °C double contact plate (100–200 s) or in the freezer airlock (20–40 min); then cut, grip, dip and stack as a rigid body. | B:N12; F:S18, F:D; A:M9; D:N1 | 4/6 | H (meat-plant practice); plate queue; customer acceptance |
| SM-241 | **Release by heat flash**: 1–2 s induction pulse on a ferritic mould melts the contact film. | B:N24; F:S17 | 2/6 | M–H; moulds must be ferritic |
| SM-242 | **Buy it prepared** (MEAL-012 a): peeled or frozen diced onion and garlic; also trimmed, cored, frozen-chopped produce, liquid egg, cut meat. | A, B, C, D, E, F | **6/6** | H; blocks MEAL-009 (≥ 90 % from whole produce) |
| SM-243 | **Reorder the recipe** so that a hard operation vanishes (F §5, 21 rows): boil skin-on then slip or rice; pass sauces through the ricer; smash-form; press dough directly on the tray; one large Roulade; combined flour-egg batter; freeze herbs at ingestion. | F §5; C:S-7; D:N15 | 3/6 | H; class-A rows count against the 10 % of MEAL-013 and have not been counted |
| SM-244 | **Serve as components**: tacos, wraps, filled sandwiches not assembled; whole birds cooked and served as parts; whole fish carved by the guest. | C §7.1; requirements X-03, X-04 | 1/6 | — ; a coverage decision, not a mechanism |

### 1.3 Convergence summary

Ideas that at least four of six lenses reached independently:

| Idea | SM | Lenses |
|---|---|---|
| Buy peeled onions and garlic first, build a peeler later | SM-242 | 6 |
| Flip by inverting a pan pair | SM-127 | 6 |
| Heat first, then slip the skin | SM-055 | 6 |
| Toss by tumbling a closed vessel | SM-186 | 6 |
| Nozzle-fill rigid cavities | SM-076 | 6 |
| Ram through a grid, cut off flush | SM-009 | 5 |
| Rotating vessel against a fixed roller for kneading (no bottom shaft, no seal) | SM-171 | 5 |
| Top-entering blade, no bottom shaft | SM-024 | 5 |
| Extrude and cut off for patties and dumplings | SM-066 | 5 |
| Push-up floor / piston vessel | SM-117 | 5 |
| Equator-scored egg opening between two cups | SM-164 | 5 |
| Seam-down cradle instead of tying Rouladen | SM-084 | 5 |
| Nose transfer of limp items | SM-101 | 5 |
| Ricer; skin-on potatoes through it | SM-184, SM-056 | 5 |
| Lift-out basket for pasta; never pour 9 L | SM-155 | 5 |
| Dosing element stays with the box | SM-134 | 5 |
| Spin-dry | SM-213 | 5 |
| A small vessel for one egg white | SM-176 | 5 |
| Belt or mat as the flat work surface, washed on the run | SM-195 with SM-017, -090, -104 | 4 |
| Pocket band / loop roller for Rouladen | SM-079 | 4 |
| Freeze-plate pick-up of one slice | SM-098 | 4 |
| Temper meat before cutting | SM-240 | 4 |
| Slit-and-jet and slit-and-rub onion skinning | SM-060, SM-061 | 4 each |

Two convergences of lower count deserve a note. The **disc-in-disc ceiling** (SM-226) was invented twice,
by the machine-tool and the manipulator lens, with nearly the same dimensions (Ø 470–500 outer disc,
reach Ø 470–480). **Induction flash-drying** (SM-212) and **reciprocating-extrusion kneading** (SM-173)
were each invented twice; for the second, both inventors doubt it.

Ideas that are strong in one lens and absent from all others (candidates for being lost): vessel as
cutting rotor (SM-013), three-layer drain (SM-157), breading by flipping (SM-093), form in the pan
(SM-069), recipe follows the scale (SM-151), freeze to count (SM-147), drip-collar stem (SM-202), jet
gate (SM-198), witness coupon and riboflavin self-test (SM-207), salt as brine (SM-143), venturi wand
(SM-158), cryo-crumble (SM-027), ice-cube-tray forming (SM-071), magnetic counted pins (part of SM-085),
spice wand (SM-140), tools ride with the vessel (SM-122), planetary by kinematics (SM-172), through-wall
puck (SM-229), eversion (SM-118), recipe reordering table (SM-243).

---

## 2. Operation × mechanism matrix

Rows: the operations the machine must perform itself (MEAL-018), the corpus blockers, and the everyday
operations the brief names (dosing, transfer, stirring). "Strongest" is a first-pass reading of
convergence, existing practice and the authors' own confidence; it is an input to round P3, not a
selection.

Status: **OK** = at least one mechanism rests on known practice and its author rates it high.
**TEST** = mechanisms exist, none is proven, a bench test decides. **GAP** = no convincing mechanism in
round P1; becomes a targeted invention task for round 2 (section 2.4).

### 2.1 Operations with no purchase workaround (MEAL-018 a) and the shaping cluster (MEAL-018 b)

| Operation (code, share of meals, UO) | Proposed mechanisms | Strongest at first pass | Status |
|---|---|---|---|
| Flip pieces: patty, steak, cutlet (FLP, 12.9 % all flips, UO-55) | SM-129, SM-127, SM-103, SM-130, SM-102, SM-131, SM-132 | SM-127 (turns the whole pan at once) and SM-129 (single pieces, needs a roll axis) | OK |
| Flip whole-pan items: pancake, omelette, Rösti, tortilla, fish (FLP, UO-63) | SM-127, SM-128, SM-102, SM-132 | SM-127: the only 6/6 idea; SM-128 as the light variant | TEST (hot fat, second hot pan and position, mass of a 36 cm pair; nobody has a second answer) |
| Assemble layered dishes in a vessel: lasagne, gratin, moussaka, pizza topping (ASM/LAY/TOP/SPR, UO-43, -88, -90, -91) | SM-108, SM-110, SM-078, SM-109, SM-097 | SM-108 with SM-110 (factory method); SM-078 for cold layered builds | OK |
| Assemble open-hand food: burger, taco, sandwich, wrap, bowl, layered cake; stack stable to the hatch (ASM, 6.9 %, UO-88) | SM-109, SM-078 (burger), SM-080 (wrap), SM-244 | SM-109 on a top-down cell; SM-078 for the burger | **GAP** for taco, filled sandwich, layered cake; C and B state it openly; A and D rate pick-and-place of soft items "medium, slow" |
| Carve a boneless roast, slices intact (CAR, 4.8 %, UO-80) | SM-017, SM-029, SM-032, SM-031, SM-016, SM-015 (only ≤ Ø 110–140) | SM-017 (belt and cross blade: "the best slicer", A, B, D, F agree) and SM-032 (knife plus comb fence, no extra machine) | OK; TEST for hot, soft braised meat |
| Carve bone-in poultry into portions (CAR, priority S) | — | — | **GAP**; all six say "not solved" or "serve as parts" (SM-244) |
| Unmould cake, pudding, panna cotta (UNM, 4.4 %, UO-87) | SM-111 onto a plate, SM-078, SM-117, SM-241, SM-118, SM-204 (paper-lined mould), SM-071 (cavity mat peeled off) | Inversion (SM-111/127 hardware) combined with a positive release: SM-078 sleeve lift, SM-117 push-up floor or SM-204 liner | TEST (sticking, as for a human; ≥ 95 % undamaged) |
| Score pork rind, bread, tomato (SCO, 2.8 %, UO-92) | SM-033 | any depth-stopped blade; draw cut for proved bread | OK |
| Stuff rigid cavities and tubes: pepper, tomato, apple, cannelloni (STU, 6.5 %, UO-44) | SM-076 with SM-117 or SM-144; cavity prepared by SM-041/-042 | SM-076 (6/6) | OK |
| Stuff soft or flat pockets, dumpling cores, poultry cavity (STU; flat pockets S, the rest M) | SM-077 | — | **GAP**; dumpling cores and the poultry cavity are priority M in UO-44 and no inventor addresses them |
| Wrap a flat item round a filling: cabbage roll, burrito, bacon wrap, enchilada, biscuit roll (WRP, 4.0 %, UO-42) | SM-079, SM-080, SM-081, SM-082, SM-083, SM-091 (rolled in its own mat or paper) | SM-079 (4/6) and SM-080 (3/6) | TEST |
| Separate whole cabbage leaves for the rolls (LSP, 1 meal; pre-blanched leaves forbidden by MEAL-012) | blanch the head whole (C §7.2) | — | **GAP** |
| Hand-form small pieces: gnocchi, Schupfnudeln, croquettes, falafel, cookie balls (FRM, 2.8 %, UO-46) | SM-066, SM-072, SM-073, SM-074, SM-071, SM-075 | SM-066 for portions plus SM-073 for rounding | TEST; tapered Schupfnudeln only by SM-072 (palm plate) |
| Form patties and dumplings (FRB/FRK, UO-40) | SM-066, SM-067, SM-068, SM-069, SM-070, SM-071, SM-072, SM-073, SM-075 | SM-066 (5/6, factory former); SM-070 if no former is wanted | OK |
| Roll Rouladen (RLT, 1.6 %, brief, UO-42) | SM-079, SM-080, SM-081, SM-082, SM-083; slice laid by SM-098/-099/-100/-101; spread by SM-110 | SM-079 and SM-080; mandrel (SM-082) where a lathe exists | TEST; five mechanisms, none tried with a real filled slice |
| Secure Rouladen through browning and braising (RLT) | SM-084, SM-085, SM-086, SM-087, SM-088 | SM-084 (5/6) with SM-085 as the traditional fallback | TEST; **highest-priority test**: the brief names Rouladen and nobody has braised an untied roll for two hours |
| Truss poultry, tie a roast (RLT, priority S) | — (buy tied) | — | **GAP** (S) |
| Bread: flour, egg, crumbs, ≥ 95 % coverage (BRD, 2.0 %, UO-41) | SM-092, SM-093, SM-094, SM-095, SM-103, SM-097, SM-096 (small pieces only) | SM-092 (industrial practice, 3/6), SM-093 (fully enclosed), SM-094 with SM-240 (rigid cutlet) | OK in principle; TEST for coverage and for crumb waste after raw-meat contact |
| Roll out dough 2–10 mm ± 1 up to tray size (ROL, UO-45) | SM-104, SM-105, SM-106, SM-107 | SM-104 (rectangular, 4/6); SM-106 where no belt exists; SM-105 for round only | OK |
| Shape dough: loaf, rolls, pizza base (SHD, 2.4 %, UO-45) | loaf baked in its tin; rolls SM-066 + SM-073; pizza SM-104/-105/-106 | as listed | OK |
| Line a tin with a dough sheet (SHD/LIN) | stepped platen presses dough into the tin (C §7.2); sheet on a mat flipped into the tin (D §8.2); paper liner pressed in by a former (E:D) | — | TEST; three single-lens sketches |
| Knead 0.1–1.6 kg dough; mix mince mass (KND/KNM, UO-32) | SM-171, SM-172, SM-174, SM-173, SM-175 | SM-171 (5/6, proven) | OK |

### 2.2 Peeling, trimming, cutting, egg

| Operation (code, share of meals, UO) | Proposed mechanisms | Strongest at first pass | Status |
|---|---|---|---|
| Peel potato and smooth roots (PLP, 24 %, UO-11, PRP-022) | SM-046, SM-047, SM-049, SM-050, SM-051, SM-052, SM-053, SM-054, SM-057, SM-058; avoid by SM-055, SM-056 | Two families: abrasive batch (SM-050, SM-049: proven, 12–25 % loss, eyes remain) and blade on a rotating piece (SM-046: 15–20 % loss, one piece at a time, needs SM-044 for hollows) | OK; the loss limit of PRP-022 (25 %) is tight for abrasion |
| Peel carrot, cucumber, asparagus | SM-048, SM-051, SM-050, SM-046 with a steady rest | SM-048 | TEST |
| Peel onion from whole, ≥ 95 % skin-free (PLA, 52 %, UO-12, priority S) | SM-060, SM-061, SM-062, SM-063; SM-242 | none rated above medium by its own author; SM-060 and SM-063 have the most support | **GAP** in the sense of "no convincing mechanism": about a dozen variants, zero tests. All six fall back on SM-242 |
| Peel garlic (PLA) | SM-064 | press skin-on (4/6) | OK for minced garlic; whole peeled cloves TEST (shake-peel) |
| Peel soft and knobbly produce, tomato, boiled egg (PLS, PLH, PLM, PLE, UO-24, S) | apple, kohlrabi SM-046; knobbly SM-059 or SM-050; tomato SM-055; egg SM-065 | as listed | OK / TEST (egg) |
| Core, deseed, hull (COR, 20 %, UO-13, S): apple, pear | SM-040, SM-041 with SM-006 | SM-041 | OK |
| Core, deseed: pepper, tomato stalk, cucumber and pumpkin seeds, strawberry hull | SM-042, SM-043, SM-041, SM-044 | SM-042 | **GAP-leaning TEST**: best estimate for the die is 70 % (B:N20); every vegetable is its own vision skill (D) |
| Trim ends (TRE, 12.5 %, UO-13): long goods | SM-037, SM-038 | SM-037 | OK |
| Trim ends: beans, sprouts, radishes, mushrooms, strawberries | SM-039, SM-038, single vision-guided cuts (D §8.3) | — | TEST; slow (3–4 s per sprout) |
| Strip, pluck, break into florets (STR, 3.6 %, UO-13) | SM-045; herbs chopped with their tender stems; woody herbs cooked whole and removed | — | **GAP**; B, D and E say "not solved by any concept here" |
| Dice 3–25 mm (DIC, 43 %, UO-15, PRP-021) | SM-009 with SM-010, -011, -012; SM-014; SM-018; SM-019; SM-020; SM-016 | SM-009 (5/6) | OK; pitch set by the die, free pitch only with SM-016/-018/-020 |
| Slice 1–20 mm (SLI, UO-14) | SM-015, SM-013, SM-014, SM-017, SM-016, SM-028, SM-029, parting on SM-001 | SM-015 (tube concepts), SM-017 (belt concepts), SM-013 (vessel concepts) | OK |
| Mince fine, chop herbs < 3 mm (MIN/CHH, UO-16) | SM-024, SM-026, SM-022, SM-023, SM-025, SM-027 | SM-024 (fast, bruises) or SM-026/SM-022 (clean cut, slower) | OK |
| Grate, zest, juice (GRC, GRF, JUI, UO-17, -21) | SM-035, SM-036 | as listed | OK |
| Crack eggs shell-free, 12 in ≤ 3 min (CRK, 14.5 %, UO-05) | SM-164, SM-165, SM-166, SM-167; always with SM-168 | SM-165 as the known baseline; SM-164 (5/6) as the low-fragment candidate | TEST |
| Separate egg (SEP, 6.9 %, UO-06, S) | SM-169 | slotted cup under SM-164/-165 | TEST |

### 2.3 Everyday operations named in the brief

| Operation | Proposed mechanisms | Strongest at first pass | Status |
|---|---|---|---|
| Mash, no lump > 5 mm, not gluey (MSH, UO-33) | SM-184, SM-185, SM-161 | SM-184 (5/6), with skin-on cooking SM-056 | OK |
| Whip from 1 to 6 egg whites, emulsify (WHP/WHK/EMU, UO-31, PRP-038) | SM-177 in SM-176 | top-driven whisk in a small vessel | OK |
| Toss salad without bruising (TOS, UO-30, -86) | SM-186, SM-187 | SM-186 (6/6) | OK |
| Wash and dry leaves, ≤ 5 % water (WLF/DRY, UO-10) | SM-159, drum (SM-221 perforated liner), SM-163, SM-162 | SM-159 or a drum | OK |
| Drain pasta, potatoes (DRN, 22.6 %, UO-36) | SM-155, SM-156, SM-157, SM-158, SM-159 | SM-155 (5/6); SM-157 and SM-158 are the two ways that never move hot water over the cell | OK |
| Squeeze out liquid (SQZ, UO-36) | SM-160, SM-161, SM-159 | SM-160 | OK |
| Transfer vessel → vessel → cooking vessel, residue ≤ 3 % / ≤ 8 % (UO-03, PRP-013) | SM-111, SM-113, SM-114, SM-115, SM-116, SM-117, SM-118, SM-119, SM-125, SM-120; limp items SM-101 | Three families: closed inversion (SM-111), pour about a passive pivot (SM-113) with scraper and chase (SM-119), piston (SM-117) for sticky masses | OK; residue figures for dough and mince are claims (≤ 0.5–2 %), not measurements |
| Stir and scrape while cooking (STC/SAU, UO-54, -75) | SM-179, SM-180, SM-181, SM-182, SM-183 | depends on the architecture: lid-borne scraper (SM-179/-180) frees the manipulator; SM-183 needs a dedicated "cook hand" | OK as mechanisms; **ownership between preparation and cooking is open** (section 5) |
| Flatten meat to 4–10 mm (POU, UO-20, S) | SM-089, SM-090, with SM-091 | either | OK |
| Thin batter poured and spread (PTH, UO-47, -63) | SM-097, metering by SM-144 or SM-117 | SM-097 | OK |

**Dosing per ingredient form (PRP-010 a–k).**

| Form | Proposed mechanisms | Strongest at first pass | Status |
|---|---|---|---|
| (a) free-flowing granular | SM-133, SM-136, SM-137 (iris), SM-139 | SM-133 or SM-136 | OK |
| (b) powders incl. cohesive | SM-135, SM-133, SM-139, with SM-142 | SM-135 (3/6) | TEST (flour at 60–70 % RH; caking near steam) |
| (c) seasoning 0.2–5 g | SM-141 with a sifter lid (SM-134/-135); SM-140; SM-143 for salt | SM-141; SM-143 removes the most frequent case | OK |
| (d) liquids | water: valve and flow meter, SM-145; others: SM-133 with a pour lip or spout lid (SM-137), SM-144 | SM-144 works from any opened carton (STOW lane, DEC-3) | OK |
| (e) viscous and pasty | SM-146, SM-117, SM-075, SM-144 (syringe), SM-147, SM-148, SM-149, SM-139 | piston (SM-146/-117, 3–5/6) or "make it a piece" (SM-147/-148) | TEST; all need the product moved from jar or tube into a box, tube, tray or pouch at ingestion or first opening |
| (f) solid fats | SM-148, SM-147, SM-075, SM-146 | SM-148 or SM-147 | OK |
| (g) discrete pieces by count or mass | SM-150, SM-152, SM-005, SM-154, with SM-151 | SM-150 plus SM-151 | TEST; eggs from a tray insert by cup or tongs |
| (h) leafy and bulky | SM-153 | — | TEST; ±10 g at best; part of a head of lettuce is not addressed |
| (i) sticky or wet pieces, raw meat, fish | pieces and mince: tilt-slide or inversion of the pack; slices: SM-098, SM-099, SM-100, SM-152, SM-091 | SM-098 (4/6) | TEST; **slices that stick together in the pack (bacon, cold cuts) are unsolved** except by SM-100 or diced bacon |
| (j) frozen loose | as (a); blocks handled as pieces | SM-133 | OK |
| (k) long goods | slot collar or Ø 60 feed insert (C:A), two-rod pinch (D:A), laid along a belt (D:C) | — | TEST; spaghetti by mass is thinly covered |

### 2.4 Operations with no convincing mechanism yet (invention tasks for round 2)

| # | Operation | Meals at stake | Why it is on the list |
|---|---|---|---|
| G1 | Peel onion from whole at ≥ 95 % (PLA) | 52 % (all avoidable by purchase; decides MEAL-009) | About a dozen variants in four families (SM-060 to SM-063), best self-rating "medium", no test. The single most valuable unsolved operation (C, D, F say so in these words) |
| G2 | Strip and pluck: herb leaves from stems, kale, florets (STR) | 3.6 % | No mechanism at all in four lenses, a low-confidence one in two |
| G3 | Open-hand assembly: taco, filled sandwich, wrap, burger, layered cake, stable to the hatch (ASM) | up to 6.9 % minus the layered-dish share (C estimates 11–13 of 17 meals covered) | No purchase workaround; only slow pick-and-place or "serve as components" |
| G4 | Stuff soft or flat pockets, dumpling cores, poultry cavity (STU) | about 6 of 16 STU meals (C's estimate) | One single-lens sketch (fold and pin) |
| G5 | Carve bone-in poultry (CAR, S) | part of 4.8 % | Nothing proposed |
| G6 | Deseed peppers and other non-axial cores (COR) | large part of 20 % (avoidable by purchase) | 70 % at best |
| G7 | Separate whole cabbage leaves (LSP) | 1 meal, but the workaround is forbidden | Nothing beyond blanching the head |
| G8 | Truss poultry, tie a roast (RLT, S) | part of 1.6 % | Nothing proposed; buy tied |
| G9 | Singulate slices that stick together; dose leafy goods and long goods by mass | foundation tier (DME 43 %, leafy in most salads) | Only freeze plate (M) and whole-box emptying |
| G10 | Trim small items in quantity: beans, sprouts, mushrooms, strawberries (TRE) | part of 12.5 % (avoidable by purchase) | Snipper drum (M) or one vision-guided cut per item |

Not gaps, but **mechanisms that all depend on an untested food result**, to be bench-tested before or
during round P3 because several candidates share them: tie-free Rouladen in a seam-down cradle (SM-084);
the pan-pair flip with a realistic amount of fat (SM-127); equator-scored egg opening (SM-164); powder
through a vibrated mesh in humid air (SM-135); residue of scraper and piston transfers (SM-115, SM-117).

**Operations of priority M that no inventor addressed** (not judged hard by the corpus, but they have no
mechanism in any idea document and must not fall between preparation, cooking and serving):
grease a baking vessel (LIN, 22 meals), glaze and brush (GLZ, 7), baste (BST, 9; only W16 mentions it),
fold gently (FLD, 11; only C names the scraper lid), rub fat into flour (RUB, 5), cream fat with sugar
(CRM, 7), sift (SFT, 9; sifters exist as dosing parts), slice baked goods and portion cake (SLB, 33;
belongs to serving), shred cooked meat (SHR, S).

---

## 3. Candidate concepts for round P3

### 3.1 How the set was chosen

The 25 whole-system concepts differ along three axes. Each candidate below takes a distinct position on
all three, and each is a complete answer (it names its bulk path, its flat path, its dosing, its
cooking-side handling and its cleaning), built the way its authors' own bets were built.

| Axis | Positions found in round P1 |
|---|---|
| **What carries the food** | rigid vessels that are stacked and inverted · a drum · a flexible belt or mat · a tube with a piston · a board or tray under a manipulator · a frozen-rigid item on a tray |
| **How motion enters the food zone** | rods and rotary seals through a ceiling or wall · magnetic coupling through a closed wall · rotation or inversion of the whole vessel · a ram on the dry side of a piston · a gantry gripping above a drip collar |
| **Where cleaning happens** | wash-down cell washed by its own manipulator · everything is loose ware for a washer · the carrier washes itself (drum, belt, mat, turret sector) · pipe flow and pigging · the cell is a dishwasher |

| K | Food carrier | Motion enters by | Cleaning | Character |
|---|---|---|---|---|
| K1 | board, pallets, fixtures under hands | rods through a twin-eccentric ceiling | wash-down cell, hand-held jet; tools to washer or holsters | the generalist; two inventors' bet |
| K2 | rigid vessels of one rim | quill from above, turntable below, inverter | all loose axisymmetric ware; wash lathe | closed stacks, no wet cell |
| K3 | drum (bulk) and endless belt (flat) | rotary shafts only | drum and belt wash themselves in place | process line, no manipulator |
| K4 | exchangeable mat, loop as vessel | six rotary shafts through one wall | reel-through wash with steam | two-dimensional cell; radical |
| K5 | tube with piston; dies | ram on the dry side; gravity | pigging, pipe flow, turret wash | push and fall |
| K6 | GN trays, stem tools, cassettes | gantry above drip collars | 3-minute washer, nothing fixed is food-contact | conservative, proven parts |
| K7 | rigid (tempered) items on trays and in moulds | plain gantry and gripper | loose ware | change the state first; radical |
| K8 | board and vessels in a closed tub | magnets through closed walls | the cell is a dishwasher; manipulator is ware | zero penetration; radical |

Common to all candidates (not repeated below; section 4.1): the dosing dock front end, the egg module,
the pan-pair flip at the hob, a small-quantity vessel, a lift-out basket for the 9 L pot, a seam-down
cradle for Rouladen, and the purchase fallback for onions. An explorer may replace any of these but must
say so.

Every explorer answers the same **standard questions** in addition to the specific ones:
(1) walk the 15 reference menus of corpus 4.9 and the eight brief meals (MEAL-005) through the concept
for 4 persons, and at least three of them for 1 and 6 persons; (2) list which of the MEAL-018 operations
and which rows of section 2.4 the concept solves, avoids or fails, meal by meal; (3) surface inventory
with Zone F and Zone S area in m², cleaning method, water and time per meal (HYG-002, HYG-010);
(4) count of axes, of loose parts, of handling moves per reference meal, and the elapsed time against
PRP-023; (5) module width and height at 600 depth for the 6-person vessel set (9 L pot, 8–10 L mixing,
28 and 36 cm pan or GN 2/3) and four heated positions; (6) class R / RTE separation within one meal
(FSF-040); (7) what it asks of the box standard, transport, cooking and washing modules; (8) share of
meals needing an adapted method (MEAL-013 limit 10 %).

### 3.2 K1 — Ceiling-turret cell with passive utensils

Output file: `design/prep/concepts/K1-ceiling-turret-cell.md`

**Definition.** A welded wash-down cell whose flat, sealed ceiling carries two or three disc-in-disc
turrets; through each passes one plain round rod (X-Y by two rotations, Z, yaw), and nothing else hangs
in the cell. Torque, a push rod and a fluid channel run through the rod, so all utensils, fixtures,
pallets and die cassettes are passive stainless parts that are picked up without a tool changer. One rod
carries a horizontal roll axis (flip, pour, ladle); heavy pressing (dice, rice, flatten: 1–3 kN) is done
either by one stiff quill or by a press bracket fixed to the wall. The work happens on a turning, tilting
board on load cells and on pallets on a spin chuck; the hands also lift vessels, pour them about a
passive pivot, and wash the cell by carrying a jet head along a programmed path. Food knowledge lives in
tooling: a missing operation is a new passive part.

| | |
|---|---|
| Source concepts | W02 (A:A2), W13 (D:A); fixtures and mechanisms from W01 (A:A1), W17 (D:E), W03 (dies as cassettes) |
| Includes | SM-226, -227, -233, -234, -235, -191, -188, -214, -216, -236, -238, -239 (cell and hands); SM-008, -003, -004, -002, -001 as spit or side-wall lathe option, -046/-047, -044, -009 + -012 (dice cassette), -020, -022, -016, -032, -033 (cutting); SM-129, -127 via -113, -109, -079 or -080 with -084/-085/-086, -094, -098/-099, -068, -073 (flat and formed); SM-171/-172, -159, -184/-185, -187 (bowl work); SM-139, -140, -141, -144, -145, -152, -153 (dosing); SM-164/-165 (egg); SM-122, -203, -190 (tool logistics) |
| Deliberately excludes | belts and mats as work surface; drums; closed-stack inversion as the transfer principle; any fixed process station inside the cell |
| Expected strong | assemble, flip pieces, carve, score, stuff, bread, pick and place of any ingredient form, breadth ("one more tool" extensibility), reproducible cell wash |
| Expected weak | throughput (serial hands, 60–90 tool changes per meal); onion; software for about 30 skills; whole-pan flip; large seals above food (HYG-004, HYG-016); width |

Questions for the explorer:

1. One stiff 3 kN quill with fixtures (W02) or two to three light 200 N hands plus a separate press (W13)?
   Work both far enough to decide, or justify a mix. Stiffness of a Ø 500 disc under 3 kN.
2. Ceiling seam design: seal type, leak-off, purge, drip edge, wear debris path, how it is proven and how
   it is replaced. What is the fallback if the seams fail (gantry behind a stainless cover)?
3. Number of turrets and cell width for the 6-person vessel set. Are the hobs inside the cell (the same
   hands stir and flip, but grease and steam reach the manipulator) or outside?
4. Tool logistics: holsters with local wash (SM-190), tools riding with vessels (SM-122), or magnet-parked
   utensils sent to the washer (SM-203)? Tool changes and time per reference meal.
5. Which produce operations justify a side-wall lathe spindle (SM-001 with SM-046, SM-164, SM-082)?
6. Utensil and fixture count, each justified by corpus frequency (PRP-003).

### 3.3 K2 — Vessel stack and inversion

Output file: `design/prep/concepts/K2-vessel-stack-inversion.md`

**Definition.** No shaft ever passes a food-contact wall and no food is ever poured through open air.
All vessels share one round rim; cans, open sleeves and flat interposer discs are stacked in a column
with a press-and-spin quill above and a turntable below, so that cutting, ricing, dicing and extruding
happen between two vessels inside a closed stack. Every transfer, every flip, draining and unmoulding is
a rim-to-rim inversion in an inverter. Flat food uses a second, rectangular GN 2/3 clamshell pair on the
same inverter. All food-contact parts are passive, mostly axisymmetric ware washed on a wash lathe and
flash-dried by induction; the machine around the stacks stays Zone S.

| | |
|---|---|
| Source concepts | W09 (C:A), flat family of W10 (C:B); tilting-column idea of W11 (C:C); folders of W12 (C:D); hourglass of E:S4 |
| Includes | SM-217, -218, -224, -225 (standards); SM-111, -112, -114, -157, -127 (inversion family); SM-009, -010, -011, -012, -013, -015, -023/-024, -031, -033, -041 (cutting in the stack); SM-049, -064, -065 (peeling); SM-066, -069, -078, -076 (forming, filling); SM-093, -089, -091, -080 + -084, -098, -105, -097 (flat); SM-171, -179, -184, -186, -159, -160 (bowl and hob); SM-138, -135, -136, -141, -147, -149, -151 (dosing); SM-192, -212, -213, -207 (cleaning) |
| Deliberately excludes | a wash-down cell; any tool reaching into an open vessel other than one-piece stalks from above; belts; a manipulator beyond the part-handling gantry and a freeze-plate lid |
| Expected strong | flip and unmould (no extra mechanism), drain, dice, slice, mash, bread enclosed, no dust and no spill, no seal or bearing in any washed part, inspection by one camera |
| Expected weak | part count (about 55) and traffic (60–90 moves per meal); open-hand assembly; carving (test); onion; the full 9 L pot cannot be inverted; two rim standards |

Questions for the explorer:

1. Moves and elapsed time per reference meal; who moves the parts (own gantry or the transport system,
   TRN-002)? Mis-seat detection before 8 kN is applied.
2. Safety and sealing of inverting hot liquids (gasket, clamp sensing, fill limit, splash hood).
3. One inverter for the round rim and GN 2/3: geometry, swing circle, clamp.
4. Cut the kit: which of the 55 parts survive a corpus walk-through (PRP-003)?
5. Wash lathe against the central washer of D7: which parts go where; induction flash on tri-ply walls.
6. Rim against the box standard: which box sizes can be inverted onto a collar; what happens to the rest.
7. Is a tilting column (its own inverter and tumbler) worth the swing space?

### 3.4 K3 — Self-cleaning drum and flat belt line

Output file: `design/prep/concepts/K3-drum-and-belt-line.md`

**Definition.** Two process machines and no manipulator. Bulk and liquid food goes into one tilting drum
(tumble to centrifuge speed, mouth up to mouth down) with loose liners and a tool arm through the mouth:
it washes, spins, peels, tumble-coats, mixes, kneads, chops, proofs and can cook tumble dishes, discharges
by tilt or reversing helix, and washes, disinfects and dries itself with its own induction coil. Flat,
formed, layered and carved food rides a short reversible endless belt under a bridge of fixed stations
(sifter, curtain, press roller, knives with depth stop, guillotine in the nose gap, curl belt or pocket
rollers, retracting nose, dish slide); the belt is washed in place on its return strand. A piston box
meters pastes and forms patties between the two. Dosing is by own-lid boxes at a tipper dock above.

| | |
|---|---|
| Source concepts | W06 (B:B) and W08 (B:D) as in B's bet; W24 (F:C), W11 (C:C), W04 (A:A4), gate of W15 (D:C); dock, downdraft and wash cartridge of W05 (B:A) |
| Includes | SM-221, -050, -054, -061, -024, -014, -171, -178, -181, -116, -115, -156, -186, -096, -193, -194, -212, -213 (drum); SM-195, -210, -017, -018, -033, -034, -090, -092, -104, -081 or -079, -101, -102, -130, -108, -110 (belt); SM-146, -117, -066, -073 (piston box); SM-133, -134, -135, -137, -142, -141, -119 (dosing); SM-164, -084 |
| Deliberately excludes | pick-and-place manipulators (beyond a suction plate); loose-ware logistics as the main path; exchangeable mats and loop mode (K4); a press column (K5) |
| Expected strong | foundation tier in bulk, potato peeling, wash-spin-toss, kneading, drum cleaning (6 L, 9 min, no shaft seal in the food zone); breading, sheeting, carving, scoring, Rouladen, layering on the belt |
| Expected weak | one drum as serial bottleneck; true dice; station bridge above food (HYG-004) and its cleanability; placing discrete soft items; whole-pan flip; eggs and small quantities need satellites; two modules of width |

Questions for the explorer:

1. Schedule one drum through four-component meals for six; is a second small drum needed? Balancing at
   450–900 rpm in a kitchen cabinet.
2. Can the station bridge and the belt pass a riboflavin test; what is the class R → RTE procedure on one
   belt; belt life?
3. How does food pass from drum to belt and back (piston box, chute, nose)? How are regular dice made?
4. Pan work: belt nose or band spatula in the pan against the pan-pair flip; hot fat on the belt.
5. Drum material for induction, corrosion and HYG-011; liner-to-drum gap.
6. Shortest belt and smallest station set that still covers the no-workaround operations; fallback to a
   book flipper (SM-103) if the bridge cannot be cleaned.

### 3.5 K4 — Shuttle mat: the membrane cell

Output file: `design/prep/concepts/K4-shuttle-mat.md`

**Definition.** The preparation cell is two-dimensional. A reinforced exchangeable mat runs reel-to-reel
between two bars across a small table under a rail of fixed tools; five primitives do everything:
shuttle (food passes under a tool), loop (the slack mat hangs as a trough with a moving wall: tumble,
toss, fold, knead, roll up), nip (roller against the table), nose (the mat is pulled from under the food)
and chop (blade against the mat). Sticky food touches only the mat, which is peeled off the food, and
the mat cleans itself by reeling through spray and steam; a magazine holds mats of different kinds
(plain, TPU anvil, perforated, mesh, rasp, cavity). A ram-and-die head at the head of the mat makes dice
and slices; liquids, whipping and boiling stay in a bowl and pots. All drives are rotary shafts through
one wall.

| | |
|---|---|
| Source concepts | W22 (F:A) with the die head of W23 (F:B); the skin ideas of W12 (C:D); W21 (E:D) and D:N20 as the disposable variant of the same principle |
| Includes | SM-222, -227, -101, -079, -090, -104, -174, -022, -007, -033, -072, -071 (cavity mat), -095, -187, -052, -061, -163, -161 (mat); SM-009, -010, -011, -015 (die head); SM-075, -144, -143, -136, -135 (dosing); SM-085, -084; SM-195, -215 (cleaning); SM-091, -118, -204 as variants; SM-127, -158 at the hob |
| Deliberately excludes | drums; rigid manipulators; an endless belt with a station bridge washed in place (K3); reliance on a cold plate (K7 owns that; the explorer states separately what one cold clamp would add) |
| Expected strong | the whole shaping cluster, carving, sheeting, kneading by fold-and-nip, tossing, transfer of limp items, cleaning of the main surface in minutes with 4 L, lowest mechanical complexity |
| Expected weak | liquids and batters; cubes without the die head; slow peeling; eggs; whipping; mat life, stickiness and odour (HYG-025); one line for the whole meal; fixed table, cheeks and blade are Zone F (HYG-033) |

Questions for the explorer:

1. Does a silicone-glass or TPU mat release wet yeast dough and raw mince by peeling alone? Life under
   blade, steam and onion oil; odour. What does a one-week bench rig have to show?
2. Loop control (slack length, loop depth), and sticky mass winding round the roller.
3. Throughput with one mat line; a second reel pair; mat magazine and exchange; who replaces mats, how often
   (HUM-007).
4. The liquid path: which bowl, whisk and pot operations remain, and what handles them.
5. Cleaning of the fixed Zone F parts (table, cheeks, roller, blade) and of the bars.
6. Disposable web (paper) against washable mat for class R work: certainty against consumable.

### 3.6 K5 — Ram-and-die column with piston vessels

Output file: `design/prep/concepts/K5-ram-and-die-column.md`

**Definition.** Every shape-giving operation is "push through a die and cut off", and food only falls.
The universal vessel is a straight open tube with a loose piston floor: it is filled at the dock, weighed,
capped, and a ram on the dry side of the piston makes it a microtome slicer, grid dicer, ricer, Spätzle
press, patty and dumpling former, filling gun, paste syringe and variable-volume chopper; two tubes nose
to nose knead and mix. Dies sit in a turret or are clamped as loose end plates; product drops straight
into the pot, pan or tray below. The piston pigs the bore, tubes are washed as pipes, dies on the idle
half of the turret. The concept is completed by the smallest flat bench that covers what cannot be
pushed (whole meat, leaves, eggs, breading, rolling, flipping), and by one raw peeler.

| | |
|---|---|
| Source concepts | W07 (B:C), W20 (E:C), W23 (F:B), W03 (A:A3); gravity tower W05 (B:A); flat bench taken from W19 in its smallest form |
| Includes | SM-117, -009, -010, -011, -015, -025, -026, -037, -038, -041, -048, -057, -036 (tube and dies); SM-066, -067, -076, -184, -160, -173, -177 (forming, mixing); SM-120, -123, -119 (gravity); SM-146 (piston box docks to the press); SM-190 torpedo or SM-196 turret wash, -205, -206, -207; SM-237 as a drive option; bench: SM-068, -080 + -084, -094, -127/-128 |
| Deliberately excludes | drums, belts, dexterous manipulators; bowls as the main mixing vessel (kept only as the fallback kneader) |
| Expected strong | dice, slices of any thickness, mash, patties and dumplings, stuffing and piping, paste dosing to ±2–3 %, dust enclosed from box to pot, residue ≤ 0.5 %, the strongest cleaning proof (pig, pipe flow, one camera down the bore) |
| Expected weak | everything flat or limp; peeling; leaves; liquids (lip not tight); eggs; whipping; large roasts (tube Ø 100–140); vessel size (2–3 L against 8–10 L); ram force 3–10 kN behind a household door; height |

Questions for the explorer:

1. Tubes as loose ware carried by a gantry (W20) or fixed sleeves on a turret washed in place (W03, W23)?
   Tube bore (100, 110, 140) against force, roast size and wash.
2. Required ram force with staggered grids and single-layer loading; frame, noise and safety case.
3. Does reciprocating extrusion knead bread dough to home quality and whip egg white? What is the
   fallback, and what does it cost the concept?
4. Define the flat bench: the smallest set of trays, tools and axes that closes the gaps, and how much of
   the concept's simplicity survives it.
5. Which raw peeler (iris for long goods, broach loss, or a borrowed lathe or rumbler)?
6. Grid hygiene: comb piston, reverse jets, flash pyrolysis; smear of mince on a turret plate.

### 3.7 K6 — All-loose-ware bench with a fast washer (the conservative candidate)

Output file: `design/prep/concepts/K6-loose-ware-fast-washer.md`

**Definition.** Nothing that touches food is attached to the machine, and nothing novel is required of
physics. Work surfaces are bought GN steel trays on weigh frames; tools are plain welded steel parts on a
stem with a drip collar, gripped above the collar by one gantry with a tilt-and-spin wrist; mechanisms
are passive cassettes that fall apart into simple shapes and are driven from a flat power wall (low-speed
dog, magnet high-speed drive, a 2 kN ram): rotating-bowl kneader, push-through dicer, ricer, chopper
cup, egg cracker, spike-lathe peeler, apron roller. A small commercial-type washer with a 3–4 minute
cycle stands at the end of the bay, so ware is washed during the meal ("wash as you go") and dries by
its own heat; two ware sets separate raw from ready-to-eat. The bay itself is only Zone S.

| | |
|---|---|
| Source concepts | W19 (E:B); GN logistics and bought-principle machines of W10 (C:B); W16 (D:D) as the alternative manipulator; W21 (E:D) in reserve |
| Includes | SM-202, -201, -208, -220, -231 (or -230), -125, -111, -128, -129, -198, -207, -215 (logistics, cleaning); cassettes SM-171, -009, -184, -024, -165, -001 + -046, -048, -080 + -084; bench work SM-068, -094, -106, -032, -033, -109, -098, -076, -186; SM-133, -141, -146 (dosing) |
| Deliberately excludes | any food-contact surface cleaned in place; novel kinematics and seals; process steps without household or catering precedent |
| Expected strong | breadth with known tools; flip, assemble, carve, unmould on a flat bench; proven, fast, verifiable cleaning; no fixed Zone F; standard parts (GN, commercial washer) |
| Expected weak | 80–120 handling moves per meal (98 % per meal needs 99.98 % per move); about 45 loose items in two sets; speed; washer noise and pH 12–13 chemistry; onion; many skills to program |

Questions for the explorer:

1. Handling count, per-move reliability needed for REL-001, self-locating features, retry strategy.
2. Washer: cycle, water and energy per meal (E estimates 25 L, 2.2 kWh), noise, detergent, and whether it
   can be the central washer of D7 or must be a second one.
3. Gantry in a dry slot against a sleeved six-axis arm (W16): reach in 520 mm depth, payload, software.
4. The minimal cassette set for the corpus; which cassette is the weakest against HYG-013.
5. Throughput against PRP-023 (1.5 kg potatoes in 10 min, 12 patties in 5 min) with one gantry.
6. How much the tube-and-piston cassette of K5 would remove (E claims 45 → 30 items, half the moves):
   state it as a delta, do not merge the concepts.

### 3.8 K7 — State change first: cold plate, steam, rigid-body handling (radical)

Output file: `design/prep/concepts/K7-state-change-rigid-handling.md`

**Definition.** Stiffness and adhesion are treated as process variables. Before any mechanics, soft food
is made rigid on a double-sided −25 °C contact plate (a 3 mm crust in about 100 s) and bonded skins are
loosened by steam or a 60 s blanch. After that the cell needs only what a pick-and-place cell needs: a
plain gantry with a two-finger gripper, thin trays, mould trays, cradles, one low-force band knife and a
rubber-finger skin slipper. Mince and dumpling mass are formed like ice cubes and handled as solid parts;
meat slices are created one at a time from a tempered block; cutlets are breaded as rigid plates;
Rouladen are closed in a cradle and the seam is frozen shut; pastes, herbs and butter are stored as
countable frozen pieces. Recipes are reordered wherever that makes an operation vanish.

| | |
|---|---|
| Source concepts | W25 (F:D); reordering table F §5; freeze-to-count of C; ice chuck and freeze gripper of A, D, E; crust-freeze of B |
| Includes | SM-240, -071, -087, -100, -029, -094, -083, -241, -004, -098 (cold side); SM-055, -063, -056, -065 (heat side); SM-147, -148, -027, -143 (storage as pieces); SM-243, -151 (recipe); SM-231, -124, -109 (handling); SM-014 or -009 for produce; SM-171, -184 in a bowl; SM-085 as the seam fallback |
| Deliberately excludes | flexible work surfaces; dexterous handling of limp items; tying; abrasive raw peeling as the default (kept only if the adapted-method budget is exceeded) |
| Expected strong | raw meat and fish handling, slicing, portioning, patties and dumplings, breading, unmoulding, carving, paste and fat dosing, herb shelf life; every mechanism is simple |
| Expected weak | time (every soft item waits 2–4 min on one plate); raw peeled potatoes and raw onion; 8–12 loose parts per meal; frost and condensate; energy; customer acceptance of surface-frozen fresh meat; MEAL-013 budget |

Questions for the explorer:

1. Verify the Plank times; plate area and count for six Rouladen plus six Frikadellen; schedule.
2. Does crust-freezing change the result (MEAL-015: juice loss, browning, crumb adhesion)?
3. Count the class-A reorderings against the 248 meals: is the concept inside the 10 % of MEAL-013?
   Which raw peeler is needed for the staples that cannot be reordered?
4. Ice-weld seam through a two-hour braise; pin fallback.
5. Frost, condensation and defrost of the clamp in a humid cell; interface to the freezer, to ingestion
   (freezing herbs, pastes, dicing blocks at ingestion) and to the transport time limits (FSF-013).
6. Customer decision needed: is surface-freezing of fresh meat acceptable?

### 3.9 K8 — Sealed tub with zero penetrations: the manipulator is a dish (radical)

Output file: `design/prep/concepts/K8-sealed-tub-magnetic-puck.md`

**Definition.** The preparation cell is a dishwasher tub with no dynamic seal at all. Its walls are
flat, closed stainless sheets; behind the back wall an ordinary H-bot carries magnet heads, and inside
the tub passive pucks cling to the wall, follow them, and turn a spindle through the wall (the
horizontal wrist axis: knife as a paper cutter, fork as a spit, turner, scoop). A turntable in the floor
and a high-speed spindle in the wall are magnet-coupled too. Pucks, utensils, board and vessels hang in
the tub on fixed pegs in a validated pattern or leave as ware; after the work the door closes and the tub
washes itself and everything in it with an ordinary dishwasher programme. Operations above the magnetic
force limit (about 100 N, 8 Nm) are moved into magnet-driven vessels or to a ram acting on a closed
cassette.

| | |
|---|---|
| Source concepts | W14 (D:B), W18 (E:A); magnet drives of W19 (E:B); ball port of E:A as the fallback for force |
| Includes | SM-229, -200, -198, -203, -209, -207, -208 (cell); SM-021, -003, -020, -022 (cutting at low force); SM-001 + -046 (spit on the puck spindle, turntable spike), -060; SM-129 (spindle turner), -127/-128; SM-171 on the magnet turntable, -024 chopper cup on the magnet spindle, -159; SM-080 + -085, -094; SM-139, -152; SM-166/-165 |
| Deliberately excludes | rods, discs or shafts through the cell wall; belts; in-cell press forces above about 100 N; any part that is not either a flat wall or an item in the wash pattern |
| Expected strong | cell cleanability and its proof (five bare sheets, fixed load, HYG-019); flipping and pouring with a natural roll axis; peeling on a spit; lowest hardware cost (D estimates 2–3 k€ for the manipulator) |
| Expected weak | force: kneading, pressing, dicing through a grid, mashing, rolling stiff dough; a decoupled puck falls into the food; no depth axis; tub blocked during its wash (50 min) unless duplex; magnets near heat |

Questions for the explorer:

1. Measure or calculate properly: normal, shear and torque capacity through 1.5 mm stainless; stiffness
   under a 60 N cut; what happens on decoupling (tether, catch, discard).
2. How are dice, mash, flattening and kneading done under the force limit (lever knife, driven vessels,
   closed cassettes under an external ram)? Does that re-introduce a penetration?
3. Wash logistics: is the tub blocked for the whole programme; quick jet-gate rinse between steps;
   duplex green/red tubs against strict sequencing; total Zone F + S wetted per meal.
4. Working volume: a slice of space 60–250 mm from the wall and a turntable; does the 6-person vessel
   set fit a 60 cm tub; how ware and food enter and leave.
5. Particles between roller and wall; wall wear; magnet temperature near the hob.
6. Is a single ball port (one dynamic seal, washed in place) an acceptable addition for force?

### 3.10 Where every source concept went

| W | Source concept | Explored in | Note |
|---|---|---|---|
| W01 | A:A1 TURN-MILL | K1 (lathe, mandrel and egg fixtures; spin chuck) | not a candidate of its own: both lathe authors rate the lathe a produce station, not a system |
| W02 | A:A2 CEILING-QUILL FMC | K1 | |
| W03 | A:A3 TURRET PRESS | K5 | |
| W04 | A:A4 BELT & BLADE | K3 | pocket rollers, rocker rod, powered blades |
| W05 | B:A FALLTURM | K5 (gravity column); its dock, downdraft and wash cartridge are common front-end options | |
| W06 | B:B TROMMELWERK | K3 | |
| W07 | B:C KOLBENSTRANG | K5 | |
| W08 | B:D FLACHBAND | K3 | |
| W09 | C:A STACK | K2 | |
| W10 | C:B SANDWICH | K2 (flat pair), K6 (GN logistics) | shaking hob (SM-182) is a cooking-module idea, carried in section 4 |
| W11 | C:C TWIN-SPINDLE | K3 (drum variant), K2 (tilting column) | |
| W12 | C:D SKIN | K4 (membrane family), K2 (folders) | |
| W13 | D:A TWIN TURRET | K1 | |
| W14 | D:B WALL PUCK | K8 | |
| W15 | D:C ROLLO | K3 (gate and belt), K1 (its turret hand) | |
| W16 | D:D SOCK ARM | K6 (alternative manipulator) | not a candidate of its own; see open issue 3 |
| W17 | D:E SPIT AND STATIONS | K1 (side-wall lathe option), K8 (spit on the puck) | |
| W18 | E:A SPÜLZELLE | K8 | |
| W19 | E:B ALLES IST GESCHIRR | K6 | |
| W20 | E:C KOLBENROHR | K5 | |
| W21 | E:D ZWEI-BAHNEN-KÜCHE | K4 (disposable variant), K6 (reserve) | |
| W22 | F:A TUCH | K4 | |
| W23 | F:B SÄULE | K5; its die head also in K4 | |
| W24 | F:C TROMMEL | K3 | |
| W25 | F:D ZUSTAND | K7 | |

The candidates do not reproduce the inventors' bets one to one, on purpose. B's bet is K3; C's is K2;
A's and D's fall together in K1; E's bet is K6 with K5 as a cassette, and F's is K4 with parts of K5
and K7. Keeping K5 and K7 separate from K6 and K4 lets round P3 judge each principle at full strength;
the hybrids can be re-formed in round P5 from explored parts.

---

## 4. Common findings

### 4.1 Design rules that every lens arrived at (or that no concept can avoid)

| # | Rule | Evidence | Consequence for the architecture (A1) |
|---|---|---|---|
| R1 | **A rim standard that lets two vessels be clamped mouth to mouth and inverted.** Flipping, unmoulding and closed transfer all use it. | SM-127 is 6/6; SM-111; C makes it the core rule, E asks for "equal rim diameters as an architecture rule" | Pans, pots, moulds and at least one plate carrier need matching rims and a gripping feature for an inverter or a pivot; a second, preheated pan and a position for it must exist at the hob |
| R2 | **One horizontal roll axis somewhere**, able to turn a loaded pan pair or tray 180°. | D: "a horizontal roll axis is not optional"; A (trunnion, flip bracket), B (book flipper), C (inverter), E (wrist), F (S20) | Whether it belongs to preparation or to the cooking module must be decided (section 5, issue 1) |
| R3 | **No shaft through a food-contact wall; no bottom blade.** Rotate the vessel against a fixed tool, or enter from above. | SM-171 (5/6), SM-024 (5/6); C rule 1, E rule C6, HYG-016 | Vessel positions for mixing need a turntable (SM-225); a common base ring or skirt with drive features (SM-218) |
| R4 | **A rectangular flat family next to the round one**: GN trays for cutlets, Rouladen, tray-size dough, braising and the oven. A round pan fries one Schnitzel; GN 2/3 equals a 36 cm pan and takes twelve Rouladen. | C §7.5, E:B, D (GN 1/6 trays), B (baking dish under the nose), F (tray, tin) | Two vessel geometries in hob, oven, inverter and washer |
| R5 | **Four heated positions plus an oven, and the 6-person vessel set** (9 L pot, 8–10 L mixing, 28 and 36 cm pan, 6 L braiser) change every concept's size. | Corpus 4.9, 6.3; A (1200 mm, two quills), C (+450 mm, four positions), D (1500 mm, three turrets), B, E, F | First sketches were all drawn one size too small; P3 must dimension for six |
| R6 | **A small-quantity vessel** on the common interface for one egg white, 100 g of dough, a sauce of 0.15 L. | SM-176 (5/6); PRP-038 | Part of the vessel family |
| R7 | **The full 9 L pot is never lifted, tilted or inverted.** Drain by basket, by wand, or through a floor-level valve. | A, C, D, E, F explicitly | Lift-out basket in the vessel family; hot water stays below the hob level |
| R8 | **Seasoning and powders are never dosed from the box above a steaming vessel.** Weigh in a dry corner into a cup and carry it, or use a downdraft, or dose salt as brine. | A, B, C, D, F; R4 §9.3 | The dosing dock is a dry place with its own small load cell |
| R9 | **Two weighing ranges**: about 10 kg at ±1–2 g under the vessel position, 200–300 g at ±0.05–0.2 g for seasoning. Loss-in-weight at the dock or gain-in-weight at the vessel. | A, B, C, D, E, F (6/6) | Load cells outside the wet zone through sealed posts (SM-236, SM-238) |
| R10 | **Waste never passes over open food**, and leaves as solids on a strainer, not through a macerator. | A (chip box), B, D, E (drum strainer); PRP-033 | A waste chute or chip box under every cutting and peeling place |
| R11 | **Rinse cold, within minutes, before the hot wash**; give raw and ready-to-eat food separate ware instances; sequence dry before wet and raw animal food last. | E rules C8, C9; A (holster rinse within 2 min); D (second board) ; FSF-040, HYG-030 | Duplicate ware and a scheduler rule |
| R12 | **The fixture stays with the workpiece** where holding is the problem: Rouladen cradle, trough or channel insert, divider lid, baking mat or paper under the dough. | SM-084 (5/6), SM-069, SM-091, SM-122 | Inserts are part of the cooking vessel family |
| R13 | **Every grid needs its mating pusher.** | SM-011 (3/6), E risk 4, A risk "blade roots" | Dies come as pairs |
| R14 | **Plain mains water at 4–5 bar is a tool**: jet skinning, flushing seeds, washing on the spot, chase water, ejector drain, even a hydraulic press. | SM-060, -042, -119, -158, -237 | A pressure-regulated cold-water line into the preparation zone |
| R15 | **Top-down camera over a known surface, plus weight and force signals**, is the sensing every concept relies on; inspect the egg before it is committed. | A (probing), C, D (board feels), E (saucer), F (clear cup) | Heated camera windows; PRP-035 blade check after each cutting cycle |

### 4.2 Assumptions that every inventor made

These are shared and untested. If one is wrong, all eight candidates are affected.

1. **Onions and garlic are bought peeled or frozen-diced** until a peeler is proven. This is allowed by
   MEAL-012 a, but MEAL-009 (≥ 90 % from whole fresh produce, priority S) cannot be met without G1.
2. **A box can be opened, tilted 95–180° at a dock and closed again** by the machine, repeatedly, and its
   contents flow or roll out. Everything in the dosing column of section 2.3 starts there.
3. **The box is of the GN 176 mm family** (B, C, F explicitly; E uses GN 1/2 trays).
4. **The induction zones are inside the preparation cell or within reach of its manipulator** (A, C, D,
   and B's drum cooks itself); E and F treat stirring and flipping as a cooking-side task done with
   preparation tools. Nobody designed the hob.
5. **A pass-through wash chamber for loose ware exists** (the R6 backbone, 480 × 480 × 400 mm, 55–75 min),
   or a faster one (E). Every concept still sends its dies, discs, tools or trays there at least daily.
6. **Deep-frying is excluded** (X-01) and butchery is bought (X-03); nobody challenges section 5.4.
7. **Potatoes may be cooked skin-on and riced** as the default for mash; raw peeling is needed only for
   the dishes that show a raw-peeled potato.
8. **The three-phase connection (DEC-1) is used** (induction flash, 6 kW boiler, 3 kW hobs in parallel).
9. **Adapted methods will be accepted**: untied Rouladen seared seam-down, diced instead of sliced bacon,
   rounded-rectangle or disc-shaped Frikadellen, two-sided contact instead of flipping, blanched onions.
   Nobody has counted them against the 10 % of MEAL-013.
10. **Coverage was judged per operation, not per meal.** All six documents say so in their open issues;
    the coverage figures quoted (A: 93–96 % for W02; D: 90–96 % for W13) are estimates.

### 4.3 Conflicts with the box, storage and module standards

For the system architect (A1). Each is a request or a collision that one module cannot settle alone.

| # | Conflict | Raised by | What it collides with |
|---|---|---|---|
| X1 | **Own-lid dosing**: up to four lid types plus a piston box (mesh, iris, spout, plain; hourglass and mesh-valve lids; per-spice sifter or wiper inserts). Adds 20–30 mm of height per box and a tuned mesh per product class. | B §1.1, C, D, E, F (5/6) | BOX-007 (one closure the machine opens, spill-proof in any transport motion), BOX-002 (≤ 4 sizes, one grid), BOX-005 (one interface), storage height pitch and capacity (STO-005), PRP-003 (number of part types), box washing |
| X2 | **Piston box**: prismatic, zero draft, loose follower floor, lip tight at −25 °C, and a hole pattern in the storage grid or dock for the ram. | A:M13, B:N5, E:S10 | GN boxes have draft (F says so and uses a separate process sleeve instead); BOX-008 leak-tightness; BOX-010; BOX-011 off-the-shelf |
| X3 | **Box as hopper**: the box is inverted onto a collar in the inverter; it must fit inside the vessel rim (GN 1/6 fits R260, GN 1/3 does not) and present a sealing rim. | C:A | Box family sizes; box rim design; TRN-002 if the inverter takes boxes from storage directly |
| X4 | **Pour features on every box**: pour edge for a dock tilter; hook lip and bail pocket for a tip bar; bayonet knob on the lid. | A, B, D, E | BOX-005, BOX-010 (no undercuts) |
| X5 | **Liners and inserts in the box**: perforated colander liner for produce (also the vented closure of BOX-007), egg tray insert, burr mill in the pepper box. | F:S32; A, B, E; C §7.4 | More ware types; washing of inserts |
| X6 | **Work done at ingestion or first opening**: freeze pastes into counted pucks, dice butter and cheese once, freeze fresh herbs, fill piston boxes or pouches from jars and tubes, keep a brine box. | C:S-9, S-24; F:S19, S31; B §1.1 | Ingestion module scope (D8), freezer capacity (about 12 small boxes, C), DEC-3 (STOW lane: open just in time) |
| X7 | **Tempering in the cold store**: meat held 20–40 min in a freezer airlock before cutting; marinating bags returned to the fridge; frozen boxes out for ≤ 90 s. | B:N12; C:D; D | CLD-004 (exit open ≤ 10 s), FSF-013 (time outside cold storage), scheduler |
| X8 | **Own part-handling gantry** inside the preparation module moving vessels, tubes, dies and tools between stations, washer and store (60–120 moves per meal). | C:A, E:B, E:C, F:D | TRN-002 (all flow between modules through the transport system), TRN-005 (move times), TRN-011 (no transport part is Zone F), CAP-030 |
| X9 | **Fixed food-contact surfaces cleaned in place**: belts, mats, table, die turret, drum, board. E's rule C1 forbids them; A, B, D, F rely on them. | A:A3, A:A4, B:A, B:B, B:D, D:C, F:A–C against E rule C1 | HYG-033 (cleaned after each meal), HYG-019 (spray-shadow-free, proven), HYG-026 (verified in operation) |
| X10 | **Drives or mechanisms above open food**: ceiling turrets, station bridges, bridge heads, tool rails, a sleeved arm. | A:A2, B:D, C:B, D:A, D:D, F:A | HYG-004 (only under a drip-proof cover that is itself Zone S) |
| X11 | **Dynamic seals in or facing Zone F**: two Ø 470–500 seals per turret, rod collars, ball seat, revolver lip seals, belt drive shafts. | A, D, E:A, F:B | HYG-016 (avoid; else cleanable in place and an LRU) |
| X12 | **Second washer or wash stations inside preparation** (wash lathe, holsters, torpedo, 3-minute tank washer, drum self-wash). | C, A, E, B | Scope of D7; water and energy budget; noise (3-minute washer, spin at 800–900 rpm); detergent supply (HUM-004) |
| X13 | **Consumables and wear parts the human replaces**: paper rolls, silicone mats and bags (yearly), belts (yearly), PE chopping inserts, brushes, sleeves. | D:N20, E:D, F:A, C:A, C:D, D:C, D:D, A:M4 | HUM-004, HUM-007 (≤ 2 × per year, ≤ 15 min), HYG-025 (odour, for silicone) |
| X14 | **Press forces of 3–10 kN and spin speeds of 800–1500 rpm** behind a household door. | A, B:C, C:A, E:C, F:B | Safety requirements of section 11.4; noise limits of 6.5 |
| X15 | **Ware material fixed by the cleaning idea**: induction flash needs ferritic or tri-ply steel; magnet parking needs a ferritic slug; magnet pucks need a non-magnetic wall; polymers excluded from flash and pyrolysis. | B:N15, C:S-1, D:N12, D:B, E:S7 | Vessel standard; HYG-011 corrosion at pH 2–12.5 |
| X16 | **Ferritic pins, clips and cradles travel with the food to the plate.** | A:M8, D:N5, F:S15 | Serving module must remove and count them (PRP-035, SRV) |

---

## 5. Open issues

1. **Who owns the pan?** Flipping, stirring, draining, basting, deglazing and the Rouladen cradle sit on
   the border between preparation and cooking. A, C and D assume the hobs are inside the preparation
   cell; E and F hand preparation tools to a separate cooking module; B's drum cooks. The architecture
   (A1) is frozen only after P6, but P3 explorers need one working assumption. Proposed for the
   orchestrator's decision: each explorer designs the handling at four heated positions as part of the
   concept and states what it requires of the cooking module.
2. **Eight candidates, eight explorers.** If fewer are wanted, the least independent pairs are K6 with K5
   (E's bet combines them) and K4 with K7 (F's bet combines them). I recommend keeping all eight for one
   round: merging early is exactly how the hybrids of round P1 hid the weaknesses of their halves.
3. **Concepts without a candidate of their own**: the lathe cell (W01, W17) is carried as a fixture option
   in K1 and K8; the sleeved cobot (W16) as an alternative manipulator in K6; the shaking hob (SM-182)
   only as a cooking-module idea. If the orchestrator wants a pure "bought robot arm" candidate as a
   reference point against prior art (Moley), it would be a ninth, K9.
4. **The ten invention tasks of section 2.4** have no owner. They are independent of the candidate
   concepts and can run in parallel with P3 as a targeted second idea round (onion peeling first).
5. **Bench tests** would settle more than further paper work for five shared mechanisms (list under
   2.4) and for the concept-specific make-or-break items: ceiling seam (K1), mat release and life (K4),
   extrusion kneading (K5), magnetic force through the wall (K8), crust-freeze quality (K7), station
   bridge and belt coverage (K3), hot inversion sealing (K2). The plan has no test phase before P6.
6. **Coverage numbers.** No document walked the 248 meals through a concept. Standard question 1 of
   section 3.1 asks for the reference menus only; the full recomputation per corpus appendix A is left to
   P4 or V2.
7. **The adapted-method budget (MEAL-013, 10 %)** has not been counted by anyone, and several cheap
   solutions spend it (assumption 9 in 4.2, reordering table SM-243). A single count for all candidates,
   with a ruling on which substitutions count as "adapted", is needed before P4 scores coverage.
8. **MEAL-009** (≥ 90 % from whole produce, priority S) is quietly dropped by every bet through
   SM-242. It should be either confirmed as a later upgrade or kept as a scoring criterion in P4.
9. **Operations nobody addressed** (end of section 2.4: grease, glaze, baste, fold, rub in, cream, sift,
   slice baked goods, shred) need an owner among preparation, cooking and serving.
10. **Feasibility notes in section 1.2 are mine**, from reading only; where two inventors contradict each
    other (C: white asparagus not peelable, E and F: iris peeler does it; A: water jet unwinds onion skin
    in 3–5 s, F: medium-low), the lower rating was taken.
11. **Numbering**: the SM list has 244 entries because basic building blocks were included for the
    matrix; about 150 of them are the novel ideas counted in the task. The IDs are stable from here on;
    new ideas of round P5 continue at SM-245.
12. **Not read for this catalogue**: research R4, R5, R6 and R8 themselves (only as cited by the
    inventors), and corpus sections 3 and 5–6 in detail. Numbers attributed to them are second-hand.

## 6. Risks

| # | Risk | Affects | Consequence | Mitigation |
|---|---|---|---|---|
| 1 | The clustering hides a good hybrid, or an explorer treats the candidate as closed and ignores sub-mechanisms from other lenses | P3 | A winning combination is never examined | Section 1.2 is open to every explorer; P5 exists to re-form hybrids; explorers report "what I would import" |
| 2 | Convergence is mistaken for proof: six inventors share the same untested assumption (tie-free Rouladen, pan-pair flip with fat, mesh dosing, peeled onions) | all K | 95 % reached on paper only | Bench tests of the shared mechanisms (issue 5); P4 critics score "tested / untested" separately |
| 3 | Onion peeling stays unsolved | all K | MEAL-009 fails; 52 % of meals depend on a purchased form with shorter shelf life and different browning | Targeted invention round G1; keep a slot for a peeler in every concept |
| 4 | The no-workaround operations with a GAP (open-hand assembly, flat pockets, bone-in carving) add up to more than the reserve of four meals in requirements 5.4 | all K | MEAL-002 missed by a few meals | Count them meal by meal early; invention tasks G3–G5; customer decision on "served as components" |
| 5 | Every first sketch was one size too small for six persons; the grown versions (1200–1500 mm) may not fit a kitchen run with storage, cold storage, oven and washer | K1, K2, K3 most | Footprint constraint of the brief | Standard question 5; dimension for six from the start |
| 6 | Own-lid dosing and piston boxes are assumed by most concepts but collide with the box standard | K3, K5, K6, and the common front end | Dosing has to be redesigned late | Architect rules on X1–X5 before P3 ends, or explorers carry a plain-box fallback |
| 7 | The border to the cooking module stays undecided and each explorer assumes a different hob | all K | Concepts cannot be compared in P4 | Issue 1: one working assumption for all |
| 8 | Handling-count concepts are judged only on mechanism elegance, process concepts only on coverage | K2, K6 against K3, K4, K5 | Biased selection | Same standard questions for all (3.1): moves per meal, reliability per move, Zone F area, time |
| 9 | The radical candidates (K4, K7, K8) depend on one physical unknown each and cannot be judged on paper | K4, K7, K8 | Dropped or kept for the wrong reason | One-week rigs as proposed by their inventors; P4 marks "decided by test X" |
| 10 | Cleanability claims rest on "coverage by construction" arguments that no riboflavin test has checked (belt return wash, turret sector, programmed jet path, torpedo, wash lathe) | K1–K5 | HYG-019/-020 failed after selection | P4 hygiene critic; prefer candidates whose Zone F is loose ware when scores are close |
| 11 | Count of part and tool types grows with every gap closed by "one more passive part" | K1, K2, K6 | PRP-003, CAP-030, wash capacity and store volume exceeded | Each part justified by corpus frequency; parts used in < 1 % of meals dropped |
| 12 | This catalogue misreads or drops an idea | P2 | Lost idea | Source references on every row; section 1.3 lists the single-lens ideas most at risk; the idea files remain the reference |
