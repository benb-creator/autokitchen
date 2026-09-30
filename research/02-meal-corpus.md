# R2 - Meal corpus for the AutoKitchen 95 % goal

Author: research agent R2. Date: 2026-09-30. Scope: the customer requirement in [BRIEF.md](../BRIEF.md): *"At least 95 % of all traditional meals should be preparable"*, with the named examples salads, mashed potatoes, roast beef, Frikadellen, Rouladen, soups, steak, pasta.

This document turns that sentence into something measurable. It defines (1) a corpus of 248 traditional meals and basic components, weighted towards German / Central European home cooking, (2) an exhaustive taxonomy of 126 unit operations with a machine-difficulty rating, (3) the decomposition of every corpus meal into ordered unit operations, vessels, temperatures, times and hardest step, (4) coverage statistics that show which operations are needed for 80/90/95/99 % of meals and which operations block how many meals, (5) statistics of 180 ingredients with physical form, storage class, shelf life and handling notes, and (6) portion sizes and vessel volumes for 1 to 6 people. All numbers are derived from the tables in this document; the derivation is reproducible with the script in Appendix A.

Conventions: metric units, temperatures in degrees Celsius, masses in grams as raw weight unless stated. **Estimate** means the author's engineering judgement, not a measurement; the difficulty ratings D and the avoidability levels (Section 2) are estimates and are the most important assumptions to challenge.

## 0. Key results

| Question | Answer |
|---|---|
| Corpus size | 248 meals/components (138 German/Austrian/Swiss = 56 %); weighted sum 496 (weights 1-3 = occasional / common / staple) |
| Unit operations in taxonomy | 126 in 10 groups; 98 rated D1-D3, 28 rated D4-D5 (used in corpus) |
| Operations per meal | mean 15.6 distinct operations (incl. implicit dosing/washing), median 16, max 29 |
| Universal operations (>= 50 % of meals) | DSO 96 %, DUN 93 %, PLT 93 %, DLI 88 %, DPO 64 %, WSH 59 %, PLA 52 %, DBL 51 % |
| Coverage if ALL ops are implemented | 100 % by construction (every op in the taxonomy is used) |
| Coverage if every operation up to D4 is implemented but the five D5 operations (deboning, trimming, filleting, shelling, roll-and-tie) are not, and nothing is bought pre-processed | 94.4 % unweighted / 94.8 % weighted |
| ... and with pre-processed purchase allowed (boneless, trimmed, filleted, shelled = level 1) | 98.4 % / 98.2 % |
| ... and additionally convenience semi-finished products allowed (pre-made Rouladen, formed patties etc. = level 2) | 100.0 % / 100.0 % |
| Machine supports only ops up to D3 (no peeling, coring, flipping, stuffing ...) | 12.1 % of meals; with level-1 pre-processed purchase 61.3 %; with level-2 71.0 % |
| The hard "shaping cluster" (stuff, wrap, hand-form, shape dough, bread, roll-and-tie, skewer, separate cabbage leaves) | blocks 38 meals = 15.3 % and can only be avoided with semi-finished products |
| Hard operations needed on top of the foundation tier for >= 95 % under S2 (level-1 and level-2 purchase) | 4: FLP ASM UNM CAR (coverage 96.8 %) |
| Hard operations needed on top of the foundation tier for >= 95 % under S1 (level-1 purchase: peeled, trimmed, boneless ...) | 9: FLP ASM STU UNM CAR WRP SCO FRM SHD (coverage 96.0 %) |
| Hard operations needed on top of the foundation tier for >= 95 % under S0 (no purchase, machine does everything traditional) | 20: PLA COR FLP TRE PLS PLH SEP ASM STU UNM CAR WRP STR PLE SCO FRM SHD BRD TRM PIT (coverage 95.6 %) |
| Most frequent hard op | PLA peel onion/garlic: 129 meals = 52.0 %; avoidable by peeled onions / frozen diced onions / garlic paste |
| Heat sources | one dish alone needs 0/1/2/3 concurrent heat sources in 24/140/73/11 meals; typical menus (main + 2 sides) need up to 4 hobs + oven (Section 4.9) |
| Ingredient diversity | 180 ingredient types; the 135 most frequent cover 80 % of the meals and 168 cover 95 % (long tail: storage boxes must be freely assignable) |

## 1. Method, sources and representativeness

### 1.1 Sources

Web sources actually consulted (fetched or returned by search; chefkoch.de itself could not be fetched from the research environment, see Open issues):

* Gräfe und Unzer, *Die 100 Lieblingsgerichte der Deutschen* (ranking reproduced by Küchengötter, 97 of 100 titles retrievable): https://www.kuechengoetter.de/saisonale-rezepte-specials/schmecken-immer/die-100-lieblingsgerichte-der-deutschen ; top 10 also at https://www.schwaebische-post.de/ratgeber/genuss/lieblingsessen-der-deutschen-top-10-beliebtesten-gerichte-leibspeisen-zr-90261200.html (Pizza, Lasagne, Spaghetti Bolognese, Pfannkuchen, Rouladen, Semmelknödel, Rumpsteak, Pommes, Pesto, Rheinischer Sauerbraten).
* Chefkoch Foodstudie, category ranking of German home cooking (pasta, meat, salads, rice, fish, vegetarian, Aufläufe, soups, Eintöpfe, desserts, cakes, warm breakfast, pizza, vegan, wok): https://www.t-online.de/leben/aktuelles/id_100238102/chefkoch-foodstudie-umfrage-zeigt-das-lieblingsessen-der-deutschen.html
* apetito Menü-Charts 2024 (best-selling catering dishes by segment: Spaghetti Bolognese, Chicken Korma, Bami Goreng, Currywurst, Käsespätzle, Cordon bleu, Rinderroulade, Erbsensuppe, Kartoffelpuffer, Königsberger Klopse, Linsensuppe, Milchreis, Hühnerfrikassee, Falafel, Fischstäbchen): https://www.apetito.de/presse/menue-charts-2024
* Hausmannskost collections (home classics) (Eier in Senfsoße, Erbsensuppe, Hühnerfrikassee, Schichtkohl, Frikadellen im Speckmantel, Käsespätzle, Schweinebraten, Gröstl, Kohlrouladen, Königsberger Klopse): https://eat.de/rezeptidee/hausmannskost/ , https://www.lecker.de/hausmannskost-futtern-wie-bei-muttern-51349.html
* Blog top lists 2023-2025 showing current trends (Nudelsalat mit Mayo, Kartoffelsuppe, Carbonara, Ramen, Rhabarberblechkuchen, Nudelauflauf, Tiramisu, Air-fryer dishes): https://www.gaumenfreundin.de/top15-die-besten-rezepte-2023/ , https://www.s-kueche.com/2026/01/top-10-rezepte-2025/
* American home cooking (apple pie, meat loaf, fried chicken, potato salad, chocolate chip cookies, butter chicken, cast-iron pizza): https://www.tasteofhome.com/collection/regional-recipes-from-across-the-country/ , https://www.americastestkitchen.com/collections/15-of-our-all-time-most-popular-recipes
* Portion sizes: Swissmilk https://www.swissmilk.ch/de/rezepte-kochideen/tipps-tricks/mengenberechnung-pro-person/ ; EAT SMARTER https://eatsmarter.de/gesund-leben/news/richtige-portionsgroessen ; DGE/Apotheken Umschau figures via search summary (meat 150-180 g, potatoes 150-200 g, rice/pasta side 50-80 g, pasta main 120-150 g, vegetables 200 g side / 400 g main).
* Shelf life: t-online table https://www.t-online.de/leben/essen-und-trinken/id_85567482/fleisch-fisch-milch-so-lange-halten-sich-lebensmittel-im-kuehlschrank.html (beef 4 d, veal/pork 3 d, poultry 2 d, mince same day, cooked pasta 4 d, cooked rice 2 d); BVL storage guidance; AOK / HelloFresh on mince. Values not found in these sources are estimates from common practice.

### 1.2 How the corpus was built

1. Start from the 97 retrievable titles of the G&U top-100 (which mixes Italian classics with the German canon) and from the Chefkoch Foodstudie category order. All 97 titles are mapped to at least one corpus row (Appendix C); where the title is a variant (e.g. "Kir-Royal-Cupcakes", "Heidelbeermuffins") the row is the operation-equivalent base recipe.
2. Add the dishes the customer named (salads, mashed potatoes, roast beef, Frikadellen, Rouladen, soups, steak, pasta) and the classics of the Hausmannskost collections (Sauerbraten, Gulasch, Grünkohl, Eisbein, Leber Berliner Art, Tafelspitz, Eier in Senfsoße, Frankfurter Grüne Soße ...).
3. Add the commonly cooked Italian, French, Mediterranean, Asian, Indian, Mexican and American home dishes, breakfasts, bread, cakes, cookies, desserts, casseroles and side dishes so that every Chefkoch Foodstudie category is populated (Section 4.1).
4. Each row is decomposed into ordered unit operations by the author following the standard German/international home recipe (worst case: the traditional method, not a shortcut). Washing and dosing operations are derived automatically from the ingredient list; all other operations are written into the row.
5. Each row gets a weight W: 3 = staple cooked regularly in German households (appears in the top lists or is a basic side/component), 2 = common, 1 = occasional, seasonal or festive. Weights are an estimate; they are used only for the weighted coverage columns.

The corpus deliberately contains 248 rows rather than 150 so that individual rare operations (e.g. filleting, pretzel shaping) still have a non-zero count. 5 rows are basic sauces/components (SC) rather than complete dishes; they are kept because every roast, pasta and dessert depends on them.

### 1.3 Definitions used for coverage

* **Supported operation**: the machine can perform it autonomously, hygienically and cleanably at household scale (1-6 portions).
* **Meal preparable**: every unit operation of the meal is either supported, or is avoidable by buying a pre-processed ingredient at the allowed level.
* **Avoidability level** of an operation (column `av` in Section 2): 0 = cannot be avoided (the operation happens inside the machine or the dish changes); 1 = avoidable with a commodity pre-processed food that a normal supermarket sells all year (peeled, cored, pitted, trimmed, boneless, minced, filleted, shelled, pre-cut, grated, frozen chopped herbs, liquid egg); 2 = avoidable only with heavily semi-finished or ready-made products (formed patties, breaded cutlets, ready-stuffed or ready-rolled Rouladen, ready dough sheets, filled pasta).
* **Coverage scenarios**: S0 = no substitution allowed (the machine must do everything the traditional recipe does); S1 = level-1 substitution allowed; S2 = level-1 and level-2 substitution allowed. Substitution only applies to operations the machine does not support. Under S1/S2 the meal is *still the same traditional dish*; only the ingredient form differs, at the cost of price, shelf life and (for some items) taste.
* **Difficulty D (estimate)**: 1 = solved by standard mechanism (pump, heater, doser); 2 = known tool exists, needs hygienic design; 3 = custom mechanism or vision needed, considered feasible; 4 = hard, not solved at household scale with irregular natural produce; 5 = research-grade.

## 2. Taxonomy of unit operations

126 operations in 10 groups. Column `D` difficulty (1-5, estimate), `av` avoidability level (0/1/2, Section 1.3), `n` number of corpus meals containing the operation (implicit dosing/washing included), `%` share of corpus. Dosing operations (DSO ... DME) are derived from the physical form of each ingredient (Section 5); WSH/WLF are derived for fresh produce; GRS from whole pepper; GRF from nutmeg.

### 2.1 Dose

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| DSO | dose free-flowing solids | 1 | 0 | 238 | 96.0 | rice, sugar, salt, flour(as granulate), oats, lentils, breadcrumbs, frozen peas; 1-2000 g, +-2 % | screw/vibratory/star-wheel doser, load cell |
| DPO | dose powder / spice pinch | 2 | 0 | 158 | 63.7 | 0.2-20 g of spices, baking powder, cocoa, icing sugar; clumping, dust, +-10 % | auger micro-doser with agitator, sealed spice cartridges |
| DLI | dose thin liquids | 1 | 0 | 218 | 87.9 | water, milk, oil, stock, wine, vinegar; 5-3000 ml, +-2 % | pump + flow meter or load cell |
| DVI | dose viscous / sticky | 2 | 0 | 100 | 40.3 | tomato paste, mustard, mayonnaise, yoghurt, quark, cream, honey, jam, pesto, coconut milk; 5-500 g | piston/peristaltic pump, wide-bore squeeze, scraper, heated |
| DUN | dispense countable whole items | 3 | 0 | 231 | 93.1 | potatoes, onions, eggs, carrots, tomatoes, apples: irregular, 30-300 g each, 1-24 pieces | gravity singulator, gripper, vision counting |
| DBL | portion block solids | 2 | 0 | 127 | 51.2 | cut a defined portion off butter, cheese, tofu, chilled dough 5-500 g | wire cutter / guillotine / warm blade |
| DME | dispense raw meat / fish pieces | 3 | 0 | 107 | 43.1 | slippery, sticky, non-uniform; cutlets, roulades, fillets, whole birds 0.1-2 kg | tray-based storage (one piece per tray), gripper with peel-off liner |

### 2.2 Clean

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| WSH | wash robust produce | 2 | 1 | 146 | 58.9 | potatoes, carrots, apples, peppers, tomatoes, cucumbers, lemons; remove soil | tumble drum with spray; potatoes need brush |
| WLF | wash delicate / leafy produce | 3 | 1 | 86 | 34.7 | lettuce, herbs, berries, mushrooms, spinach, leek (sand between layers) | bubble bath + gentle spin; separate leaves first |
| RNS | rinse grains / pulses / pasta | 1 | 0 | 16 | 6.5 | rice, lentils, cooked pasta cold rinse, chickpeas | sieve bucket with spray |
| SOK | soak / steep in liquid | 1 | 0 | 11 | 4.4 | dried beans (12 h), bread roll, toast in egg-milk, raisins, gelatine, dried mushrooms | vessel + timer (long occupancy) |
| DRY | dry: spin or pat dry | 2 | 0 | 3 | 1.2 | salad, herbs, fish/meat before searing, fried aubergine | salad spinner (centrifuge), air knife, absorbent |

### 2.3 Peel

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| PLP | peel potato / smooth roots | 3 | 1 | 60 | 24.2 | potato, carrot, sweet potato; 1-3 mm skin, low loss | abrasive drum (loss 15-25 %), steam peeler, blade peeler; buy pre-peeled vacuum potatoes |
| PLH | peel hard / knobbly / woody | 4 | 1 | 18 | 7.3 | celeriac, kohlrabi, beetroot, white asparagus, pumpkin (rind), ginger | knife-based with vision / cut-away peel (loss 30 %); avoid: unpeeled Hokkaido, canned/cooked beet, jarred ginger |
| PLS | peel soft / thin-skinned fruit & veg | 4 | 1 | 26 | 10.5 | apple, pear, cucumber, kiwi, mango, banana, avocado (scoop) | spiral apple peeler (apple only); serve unpeeled where recipe allows; banana is a separate handling problem |
| PLM | peel tomato / peach (blanch, slip skin) | 3 | 1 | 2 | 0.8 | score, dip 10 s in 95 C water, shock, slip | blanch bath + roller; avoid: canned peeled tomatoes |
| PLA | peel alliums | 4 | 1 | 129 | 52.0 | onion, shallot (papery skin, 40-90 mm), garlic (cloves 10-30 mm) | air-jet onion peeler (industrial), garlic roller; buy peeled onions/garlic or paste |
| PLE | peel boiled egg | 4 | 1 | 7 | 2.8 | crackle and slip shell of hard-boiled egg | tumble + water spray; buy peeled boiled eggs |
| PLQ | shell shrimp / seafood | 5 | 1 | 1 | 0.4 | remove shell, tail, vein | buy frozen peeled shrimp |

### 2.4 Trim

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| TRE | trim ends / stems / roots | 4 | 1 | 31 | 12.5 | green beans, leek, spring onion, Brussels sprouts, mushrooms stem, strawberries hull, radish, asparagus ends | cut-off station with vision; buy trimmed (frozen beans, pre-cut leek) |
| COR | core / deseed / hull | 4 | 1 | 50 | 20.2 | pepper, apple, cabbage head, pumpkin, tomato, chili, cucumber, avocado stone, kohlrabi | coring punch for apple; pepper: cut-off cap + rinse; buy frozen pepper strips / canned tomatoes |
| PIT | pit / stone | 4 | 1 | 3 | 1.2 | cherry, plum, olive, avocado, peach | cherry pitter (per-fruit); buy pitted / jarred / frozen |
| STR | strip / pluck / break apart | 4 | 1 | 9 | 3.6 | herbs from stems, kale from stem, cauliflower/broccoli florets, spinach stems, lettuce heads | tear station; buy frozen chopped kale, florets, herb pastes |
| LSP | separate cabbage leaves (whole) | 4 | 2 | 1 | 0.4 | blanch head, peel off intact leaves for Kohlrouladen | blanch and peel; substitute pre-blanched leaves (rare) or chopped-cabbage casserole |
| TRM | trim meat: fat, sinew, silverskin, membrane | 5 | 1 | 6 | 2.4 | pork tenderloin silverskin, rib membrane, beef sinew, liver veins | buy trimmed cuts; no household-scale machine solution |
| DBN | debone meat / poultry | 5 | 1 | 2 | 0.8 | chicken, joints, bone-in roasts, ribs | buy boneless; bones are needed for stock only (buy stock) |
| FLT | fillet / gut / scale fish | 5 | 1 | 2 | 0.8 | whole fish to fillets | buy fillets (fresh/frozen) |
| BFL | butterfly / split / pocket-cut meat | 4 | 1 | 1 | 0.4 | pocket in cutlet (cordon bleu), butterfly chicken breast, devein shrimp, split sausage | buy pre-cut pockets/flat cutlets; or bake-in-bag alternative |

### 2.5 Cut

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| DIC | dice / cube | 2 | 1 | 106 | 42.7 | onion, carrot, potato, meat, cheese, bread; 5-25 mm | grid cutter (waterjet-style or dicer head), fixed-blade press |
| SLI | slice (uniform) | 2 | 1 | 70 | 28.2 | cucumber, potato (2-3 mm gratin), tomato, mushrooms, onion rings, sausage, cabbage shreds, apple; 1-10 mm | mandolin-type rotary slicer, feed by gripper/pusher |
| JUL | julienne / strips / sticks | 3 | 1 | 13 | 5.2 | fries 10 mm, pepper strips, carrot sticks, onion half-rings, meat strips | slicer + cross cutter, extrusion grid |
| GRC | grate / shred coarse | 2 | 1 | 22 | 8.9 | cheese, carrot, potato (Puffer), cucumber, apple | rotary grater drum; buy grated cheese |
| GRF | grate fine / zest | 2 | 1 | 29 | 11.7 | parmesan, nutmeg, ginger, lemon zest, chocolate | microplane disc; buy grated parmesan; nutmeg pre-ground |
| MIN | mince fine / crush | 2 | 1 | 35 | 14.1 | garlic, onion fine, ginger, chili | garlic press, pulse chopper; buy paste/frozen |
| CHH | chop herbs | 2 | 1 | 26 | 10.5 | parsley, chives, dill, basil; wet, fragile, bruise | rotating blade chopper; buy frozen chopped herbs |
| CRH | crush / chop coarse hard items | 2 | 1 | 5 | 2.0 | nuts, chocolate, ice, crackers | pulse chopper |
| WED | halve / quarter / wedge | 3 | 1 | 14 | 5.6 | potato wedges, tomato halves, lemon, cabbage head quarter (cleaving hard heads), pepper halves | guillotine / cleaver with clamp |
| CAR | carve / slice cooked meat | 4 | 0 | 12 | 4.8 | roast, bird (bone-in), steak; hot, juicy, bones, grain direction | slicer with fence for boneless roasts (D3); bone-in poultry D5; alternative: boneless joints, serve pulled/whole |
| SLB | slice baked goods / portion cake, pizza | 2 | 0 | 33 | 13.3 | bread with crust, cake, tart, pizza, lasagne, roulade; 10-20 mm | serrated ultrasonic blade, pizza wheel; sticky fillings |
| SLM | slice raw meat / fish | 3 | 1 | 15 | 6.0 | cutlets from loin, strips (Geschnetzeltes, Gyros), salmon cubes; semi-frozen helps | slicer for semi-frozen meat; buy pre-cut strips/cutlets (fresh, 2-3 d) |
| GRM | grind meat | 2 | 1 | 1 | 0.4 | beef/pork trim to mince, 3-6 mm plate; cold chain, hygiene | standard meat grinder (cleanable); buy mince (1 d fresh, or frozen) |
| GRS | grind spices / pepper | 1 | 0 | 108 | 43.5 | pepper mill, nutmeg grater, cumin | burr mill |
| POU | pound / tenderise / flatten | 3 | 1 | 5 | 2.0 | schnitzel/roulade 4-6 mm | roller press with foil, hammer plate; buy thin cutlets |
| JUI | juice / press citrus | 2 | 0 | 8 | 3.2 | lemon, orange | reamer/press |
| CUD | cut dough / pasta | 3 | 2 | 10 | 4.0 | noodles, gnocchi pieces, biscuits with cutters, rolls, strands | dough scraper/wheel/cutters; sticky |
| BCR | make crumbs / pulse dry | 2 | 1 | 1 | 0.4 | breadcrumbs from stale bread, ground nuts, oat flour | blender/pulse; buy crumbs |
| SHR | shred cooked meat | 3 | 0 | 3 | 1.2 | pulled pork, poultry for salad | counter-rotating forks/claws |

### 2.6 Mix

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| MXD | mix dry ingredients | 1 | 0 | 25 | 10.1 | flour + baking powder + sugar | paddle in bucket |
| MXW | mix / stir cold or batter | 1 | 0 | 39 | 15.7 | batters, dressings, quark, salad sauce, combine wet+dry | paddle/whisk in bucket |
| WHK | whisk / beat liquids smooth | 2 | 0 | 32 | 12.9 | eggs, batters, sauces, milk into roux | whisk on planetary head |
| WHP | whip to volume / stiff peaks | 2 | 0 | 10 | 4.0 | egg white (requires zero fat, clean bowl), cream 35 % | whisk head, bowl clean/dry, 1-3 min high speed |
| CRM | cream fat with sugar | 2 | 0 | 7 | 2.8 | butter + sugar 3-5 min until pale; butter at 18-20 C | paddle, butter tempering (butter storage is 4 C) |
| FLD | fold gently | 3 | 0 | 11 | 4.4 | egg white/cream into batter without deflating | slow planetary sweep / spatula path; vs deflation |
| KND | knead dough | 2 | 0 | 17 | 6.9 | yeast dough 500-1000 g flour, pasta/Muerbe dough; 8-12 min, 100-250 W | hook, planetary/spiral mixer; torque 10-30 Nm |
| KNM | mix / knead mince mass | 2 | 0 | 12 | 4.8 | Frikadellen mass with egg, bread, onion; sticky | paddle/hook, cold, no over-mixing |
| EMU | emulsify | 2 | 0 | 10 | 4.0 | mayonnaise, vinaigrette, hollandaise, carbonara sauce; temperature 40-70 C | high-shear whisk + slow oil dosing |
| MSH | mash / rice / crush | 2 | 0 | 9 | 3.6 | potato, pumpkin, banana, beans, avocado; no over-work (gluey) | potato ricer / masher plate, not blender |
| PUR | puree / blend | 2 | 0 | 15 | 6.0 | soup, sauce, smoothie, hummus; hot liquid 90 C safe | immersion or bottom-drive blender in vessel (vented) |
| RUB | rub in fat / crumble | 2 | 0 | 5 | 2.0 | Muerbeteig, Streusel, crumble topping; cold butter | paddle, cold |
| SFT | sift / sieve dry | 1 | 0 | 9 | 3.6 | flour, icing sugar, cocoa, lumps out | vibrating sieve |
| TOS | toss / coat in bowl | 2 | 0 | 36 | 14.5 | salad + dressing, pasta + sauce, vegetables + oil, meat in flour, wedges + spices | tilting rotating bucket, paddles |
| EXT | extrude / press through / pipe small | 3 | 0 | 3 | 1.2 | Spaetzle press, ricer, pasta press, spritz, piping rosettes | press with perforated plate over pot; batter viscosity |

### 2.7 Shape

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| FRB | form patties / balls from mince | 3 | 2 | 6 | 2.4 | Frikadellen, Klopse, burger patties, meatballs 60-120 g; wet, sticky | mould-plate patty former, ball portioner (scoop) + roll drum; buy formed frozen patties |
| FRK | form dumplings | 3 | 2 | 3 | 1.2 | Knoedel, Kloesse 80-150 g; sticky/crumbly dough, must hold in water | portioning scoop + rolling in wet hands mould; hard cases: potato, yeast dumplings |
| FRM | shape small pieces by hand | 4 | 2 | 7 | 2.8 | gnocchi rolling, Schupfnudeln, croquettes, falafel balls, cookies balls, truffles, pretzel strands | forming rollers/extrusion + cutter approximations |
| RLT | roll & tie / truss | 5 | 2 | 4 | 1.6 | Rouladen (flat slice + filling + roll + skewer/twine), roast tying, poultry trussing | no solution known; alternatives: pins/clips, roulade press mould, pre-made Rouladen from butcher |
| STU | stuff / fill | 4 | 2 | 16 | 6.5 | peppers, cabbage leaves, cordon bleu pocket, Maultaschen, tomatoes, cannelloni tubes, apples, poultry cavity, dumpling fill | dosing nozzle into rigid cavity (peppers: D3); soft/flat pockets D5 |
| WRP | wrap / roll flat item around filling | 4 | 2 | 10 | 4.0 | burrito, spring roll, sushi (mat), bacon wrap, Kohlroulade, biscuit roll, strudel | rolling belt with fold guides; sushi/roll cake D5 |
| SKW | skewer | 4 | 1 | 1 | 0.4 | meat/veg on sticks | pick-and-thread jig; alternative: no skewer (cubes in pan) |
| BRD | bread / coat (flour-egg-crumb) | 4 | 2 | 5 | 2.0 | Schnitzel, cordon bleu, fish, chicken, croquettes: 3 stations, shake off, press crumb | 3-bath tumble/dredge chain, air-blow; hygienic with raw egg + raw meat; buy pre-breaded |
| BAT | batter dip | 3 | 1 | 1 | 0.4 | tempura/Backteig, fish | dip basket, drip |
| MAR | marinate / brine / cure | 2 | 0 | 17 | 6.9 | submerge or coat and hold cold 2-72 h (Sauerbraten 3 d) | vessel occupancy in cold storage, long dwell |
| SEA | season / salt / rub surface | 2 | 0 | 29 | 11.7 | pepper, salt, spice rub, herbs on surface | dry dose + tumble/spread |
| ROL | roll out dough | 3 | 2 | 10 | 4.0 | pizza, Flammkuchen 2-3 mm, Muerbeteig 3-4 mm, cookies, puff pastry, pasta sheets; 10-40 cm | dough sheeter (rollers), pressing plates; buy rolled sheets |
| SHD | shape dough | 4 | 2 | 6 | 2.4 | loaf, rolls (portion + round), braid, pizza stretch, crimp pie edge, line tin with dough, fold pretzel | press + pre-shaped moulds; braids/pretzels D5 |
| LIN | line / grease / prepare tin, fill mould, spread batter | 3 | 0 | 22 | 8.9 | grease+flour tin, baking paper, pour and level batter, fill 12 muffin cups | reusable silicone/non-stick moulds, dosing nozzle, level bar |
| LAY | layer | 3 | 0 | 23 | 9.3 | lasagne sheets, gratin slices, tiramisu, cake layers, moussaka | dosing head over mould, sheet placement gripper |
| SPR | spread / apply evenly | 3 | 0 | 11 | 4.4 | butter/jam on bread, sauce on pizza, cream on cake, mustard on Roulade | scraper blade, roller, spray |
| TOP | sprinkle / top | 2 | 0 | 24 | 9.7 | grated cheese, crumbs, seeds, nuts on casserole/pizza | dose over area, oscillating nozzle |
| SCO | score / slash | 4 | 0 | 7 | 2.8 | pork rind cross-hatch, bread slashing, tomato cross | blade path with vision/force; bread lame |
| PIP | pipe / deposit shaped portions | 3 | 0 | 3 | 1.2 | cream rosettes, Spritzgebaeck, filling doughnuts, frosting | piping bag/nozzle with piston |

### 2.8 Egg

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| CRK | crack egg into vessel | 3 | 1 | 36 | 14.5 | 53-63 g, shell fragments, yolk intact; 1-12 eggs | industrial egg breaker knife; buy liquid pasteurised egg (not for fried egg) |
| SEP | separate egg (yolk/white) | 4 | 1 | 17 | 6.9 | no yolk in white for whipping | egg separator cup (yolk cup) after cracking; buy liquid yolk/white |

### 2.9 Heat

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| BOL | boil (rolling boil in water) | 1 | 0 | 47 | 19.0 | pasta 1 L/100 g, potatoes, eggs, dumplings, cabbage; 100 C | induction pot, basket lift-out |
| SIM | simmer / poach gently | 1 | 0 | 79 | 31.9 | soups, stews, dumplings in stock 85-95 C, sauces | induction with PID; lid |
| STM | steam | 2 | 0 | 3 | 1.2 | vegetables, dumplings, fish, rice; 100 C steam | steam insert or oven steam |
| BLA | blanch and shock | 2 | 0 | 3 | 1.2 | 30-180 s in boiling water then ice water (cabbage leaves, tomatoes, greens) | two-vessel transfer basket |
| SAU | saute / sweat | 2 | 0 | 84 | 33.9 | onions, garlic, vegetables, mince 120-160 C, stirring | pan + stirrer, 5-20 min |
| SER | sear / brown at high heat | 2 | 0 | 25 | 10.1 | steak, roast, mince crumbling 200-260 C surface | cast/carbon pan on induction, boost 3 kW |
| PFR | pan-fry / shallow-fry | 2 | 0 | 43 | 17.3 | cutlets, patties, eggs, potatoes 150-190 C, 2-6 min/side | pan with fat, batch capacity 2-4 items |
| STW | stir-fry (wok) | 3 | 0 | 7 | 2.8 | 250+ C, constant tossing, 3-8 min | wok on high-power induction (3.5 kW), tossing stirrer; wok hei not replicable |
| DFR | deep-fry | 3 | 0 | 10 | 4.0 | fries, Backfisch, falafel, Krapfen, spring rolls 160-190 C, 1-2 L oil | fryer with fire safety, oil filtering, cleaning, lift basket |
| BRS | braise | 2 | 0 | 9 | 3.6 | sear then liquid, covered, 150-170 C oven or 90-95 C hob, 1.5-3 h | lidded pot in oven/on hob |
| RST | roast (oven, dry heat) | 2 | 0 | 13 | 5.2 | 180-230 C, 30-240 min; basting; up to 5 kg (goose) | oven >= 40 L with fan, probe |
| BKE | bake | 2 | 0 | 44 | 17.7 | cake 160-180 C, bread 220-250 C with steam, pizza 250 C+, casseroles 180-200 C | oven with steam injection, top/bottom, stone/steel |
| GRL | grill / broil / gratinate | 2 | 0 | 8 | 3.2 | top heat 250-300 C 3-10 min; contact grill | oven top element / infrared, contact plate |
| ABS | cook by absorption | 1 | 0 | 23 | 9.3 | rice 1:2, couscous, bulgur, quinoa: measured water, lid, 12-18 min | closed pot + timer |
| RED | reduce | 1 | 0 | 14 | 5.6 | boil down liquid to 1/2-1/3 (sauce) | open pot, evaporation, vent |
| DGL | deglaze | 2 | 0 | 24 | 9.7 | add wine/stock to hot fond and scrape | dose liquid + scraper |
| THK | thicken | 2 | 0 | 29 | 11.7 | roux (butter+flour), starch slurry, cream, yolk liaison; lump-free | dose + whisk, sieve |
| CRL | caramelise | 3 | 0 | 4 | 1.6 | sugar 160-180 C (crème brûlée torch, sauce), onions 30-40 min at 120-140 C | precise temp control; torch/infrared for top |
| TST | toast dry | 2 | 0 | 13 | 5.2 | nuts, seeds, bread, croutons, buns 150-200 C | dry pan, toaster, oven |
| MLT | melt | 1 | 0 | 24 | 9.7 | butter, chocolate, cheese, fat 40-60 C | bain-marie or low induction |
| POA | poach egg / delicate item | 4 | 0 | 1 | 0.4 | egg dropped into 85 C water with vinegar, fish | vessel with egg-poaching cups |
| STC | stir continuously on heat | 2 | 0 | 16 | 6.5 | risotto (add stock stepwise), custard, béchamel, porridge, polenta, scrambled egg, pudding: scorch risk | stirrer with wall scraper, bottom heat control |
| BMA | bain-marie / gentle water bath | 3 | 0 | 5 | 2.0 | hollandaise 65 C, chocolate, cheesecake water bath | water jacket vessel |
| CNT | contact bake | 2 | 0 | 2 | 0.8 | waffle iron 180 C, toaster, sandwich press | contact plates, release |
| PRF | proof / rise dough | 2 | 0 | 11 | 4.4 | 28-35 C, 60-90 % RH, 30-90 min (fridge 12-16 h for sourdough/pizza) | proofing cell, cold storage |
| CHL | chill / set | 1 | 0 | 15 | 6.0 | pudding, mousse, aspic, cheesecake, salads 2-12 h | cold storage vessel dwell |
| FRZ | freeze / churn | 3 | 0 | 1 | 0.4 | ice cream, sorbet | ice cream machine module; or skip |
| RES | rest | 1 | 0 | 27 | 10.9 | meat 5-15 min, batter 20 min, dough 30 min | timer, warm holding |
| COL | cool down | 1 | 0 | 27 | 10.9 | cool potatoes, cakes on rack, rice, pasta | rack/air; fast cooling for food safety |
| KWM | keep warm / hold | 1 | 0 | 8 | 3.2 | 60-70 C for up to 60 min | warm holding in oven/insulated |
| SKM | skim foam / fat | 3 | 0 | 2 | 0.8 | broth scum, fat layer | skimming ladle with vision, or fat separator |
| BST | baste | 3 | 0 | 9 | 3.6 | spoon juices over roast every 20-30 min | pump + nozzle or oven turning |
| DRN | drain / strain | 2 | 0 | 56 | 22.6 | pasta, potatoes, rice, sauce through sieve, fried food on paper | lift-out basket, tilt to sieve |
| SQZ | squeeze out liquid | 3 | 0 | 4 | 1.6 | grated potato, spinach, cabbage, cucumber, tofu | press plate, centrifuge |
| FLP | flip / turn item | 4 | 0 | 32 | 12.9 | pancake (thin, 25 cm), steak, cutlet, patty, egg, omelette, tortilla; fold | spatula robots exist (Flippy); pancake/omelette/tortilla D5; patties D3; alternative: two-sided contact |
| PTH | pour and spread thin batter | 3 | 0 | 3 | 1.2 | pancake/crêpe: 100 ml in 24-28 cm pan, swirl | dose + tilt pan rotation, spreader |

### 2.10 Finish

| Code | Operation | D | av | n | % | Definition and parameters | Automation approach / workaround |
|---|---|---|---|---|---|---|---|
| PRT | portion into servings | 3 | 0 | 28 | 11.3 | divide by weight/count per person: 80-450 g per component | load-cell + scoop/dispenser/gripper; slicing of casseroles |
| PLT | plate / arrange | 3 | 0 | 231 | 93.1 | place components on plate, 1-6 plates | gripper/spoon/scoop/pour, per-plate zone allocation |
| GAR | garnish / dust / drizzle | 3 | 0 | 37 | 14.9 | herbs, lemon wedge, dusting icing sugar, sauce drizzle | dose + sprinkle nozzle; visual |
| SCE | sauce / ladle onto plate | 2 | 0 | 18 | 7.3 | gravy 50-100 ml per plate | pump/ladle, dosing |
| ASM | assemble / build | 4 | 0 | 17 | 6.9 | burger, taco, sandwich, wrap, bowl, pizza toppings, cake, moussaka | modular; multi-component pick-and-place of soft items |
| GLZ | glaze / brush | 3 | 0 | 7 | 2.8 | egg wash, butter, honey glaze, jam glaze, icing | brush/spray |
| UNM | unmould / turn out | 4 | 0 | 11 | 4.4 | cake from tin, pudding, waffle, panna cotta; release by inversion | non-stick/silicone moulds, flexing, blower; risk of breakage |

## 3. The corpus

Columns: `Reg` region (DE German/Austrian/Swiss, IT, FR, ME Mediterranean/Middle East, AS, IN, MX, US, INT); `W` weight 1-3; `GU` rank in the G&U top-100; ingredient keys are defined in Section 5 (dose operation and physical form of every key); `Implicit` = dosing/washing/grinding operations derived from the ingredients; `Ordered unit operations` = processing sequence after washing (parallel branches are listed in the order in which they are started); `H/B` = peak number of concurrent heat sources / peak number of concurrent food vessels for this dish alone (oven and hob count as heat sources; bowls count as vessels); `min` = elapsed minutes from start to plating, excluding holds of many hours (marinating, soaking, proofing overnight) which are stated in the temperature/time cell; `D` = highest difficulty of any operation in the row.

### 3.1 Breakfast and brunch (14)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| BF01 | Porridge / Haferbrei | INT | 2 | - | oats milk salt banana honey | DSO DLI DVI DUN | STC PLS SLI GAR PRT | 1/1 | milk 90 C, stir 5-8 min | scorch-free stirring; banana peeling | 10 | 4 |
| BF02 | Yoghurt muesli with fruit / Joghurt-Müsli mit Obst | DE | 3 | - | oats yoghurt apple berries honey nuts | DSO DVI DUN WSH | PLS COR SLI CRH TOS PRT GAR | 0/1 | cold | peeling+coring apple | 8 | 4 |
| BF03 | Scrambled eggs / Rührei | INT | 3 | - | egg milk butter salt pepper chives | DSO DLI DUN DBL WLF GRS | CRK WHK MLT STC CHH GAR PLT | 1/1 | pan 100-120 C, 2-3 min, stir | cracking eggs without shell; do not overcook | 6 | 3 |
| BF04 | Fried egg / Spiegelei | INT | 3 | - | egg butter salt pepper | DSO DUN DBL GRS | MLT CRK PFR PLT | 1/1 | pan 120-140 C, 3 min, lid optional | cracking with yolk intact; per-egg placement | 5 | 3 |
| BF05 | Boiled egg (soft/hard) / Gekochtes Frühstücksei | DE | 3 | - | egg water | DLI DUN | BOL COL PRT | 1/1 | boiling 100 C: 5-6 min soft, 9-10 min hard, cold shock | egg handling into boiling water without cracking; timing | 12 | 3 |
| BF06 | Pancake, thin German / Pfannkuchen, Eierkuchen | DE | 3 | - | flour_wheat milk egg salt sugar butter | DSO DPO DLI DUN DBL | SFT MXD CRK WHK RES PTH PFR FLP PLT GAR | 1/2 | batter rest 20 min; pan 180-200 C, 1.5-2 min per side, 100 ml per pancake | flipping a thin 25 cm pancake | 35 | 4 |
| BF07 | American pancakes with bacon / Pancakes mit Speck | US | 2 | - | flour_wheat bakingpowder milk egg butter sugar bacon honey | DSO DPO DLI DVI DUN DBL DME | SFT MXD CRK WHK MXW PFR FLP PFR PLT | 2/2 | pan 170-190 C, 2 min per side, 60 ml dollops; bacon 160 C 6 min | flipping soft thick pancakes; bacon in second pan | 25 | 4 |
| BF08 | Waffles / Waffeln | DE | 2 | 97 | flour_wheat butter sugar egg milk bakingpowder vanilla | DSO DPO DLI DUN DBL | CRM CRK WHK MXD MXW CNT UNM GAR | 1/1 | waffle iron 180-200 C, 3-4 min per waffle | dosing batter into hot iron; unmoulding sticky waffles | 30 | 4 |
| BF09 | French toast / Arme Ritter | DE | 2 | - | toastbread egg milk sugar cinnamon butter | DSO DPO DLI DUN DBL | CRK WHK SOK PFR FLP PLT GAR | 1/2 | pan 150-170 C, 2-3 min per side | flipping soaked, fragile bread | 15 | 4 |
| BF10 | Omelette with cheese and ham / Omelett | INT | 2 | - | egg cheese_semi ham chives butter salt | DSO DUN DBL DME WLF | CRK WHK GRC DIC CHH MLT PFR FLP PLT | 1/1 | pan 150 C, 3-4 min, fold | folding / flipping the omelette | 10 | 4 |
| BF11 | Bread with cold cuts, cheese, vegetables / Abendbrot, Frühstücksbrot | DE | 3 | - | bread butter cheese_semi ham sausage_cured tomato cucumber salt | DSO DUN DBL DME WSH | SLB SPR SLI SLI ASM PLT GAR | 0/0 | cold | slicing crusty bread and spreading butter on soft slices | 10 | 4 |
| BF12 | Shakshuka / Eier in Tomatensauce | ME | 1 | - | egg tomato_can bellpepper onion garlic spice_curry oil_olive salt parsley | DSO DPO DLI DVI DUN WSH WLF | PLA DIC MIN COR DIC SAU SIM CRK SIM GAR | 1/1 | pan 150 C, sauce 15 min, eggs poach 6-8 min in sauce | cracking eggs into simmering sauce without breaking | 30 | 4 |
| BF13 | Bircher muesli / Overnight oats | DE | 1 | - | oats milk yoghurt apple honey nuts lemon | DSO DLI DVI DUN WSH | GRC PLS COR JUI MXW CHL PRT | 0/1 | cold 8-12 h | apple peeling | 10 | 4 |
| BF14 | Poached eggs / Eggs Benedict | INT | 1 | - | egg butter lemon toastbread ham vinegar | DLI DUN DBL DME WSH | SEP MLT BMA WHK EMU POA TST ASM PLT | 2/3 | water 85 C + vinegar, egg 3 min; hollandaise 65 C | poaching eggs, hollandaise emulsion | 30 | 4 |

### 3.2 German and Central European meat, poultry and sausage mains (36)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| DM01 | Meatballs / Frikadellen, Buletten | DE | 3 | 39 | mince_mixed egg onion bread mustard salt pepper parsley oil_veg | DSO DLI DVI DUN DME WLF GRS | SOK PLA DIC SQZ CRK KNM FRB PFR FLP KWM PRT | 1/2 | pan 150-170 C, 5-6 min per side, core 72 C | forming sticky patties; flipping 12 patties in 3 batches | 35 | 4 |
| DM02 | Beef rolls / Rinderrouladen | DE | 3 | 5 | beef_roulade mustard onion bacon pickles salt pepper oil_veg tomato_paste wine_red stock flour_wheat | DSO DPO DLI DVI DUN DME GRS | PLA POU SPR SLI SLI TOP RLT SER SAU DGL BRS RES THK DRN SCE PLT | 1/2 | sear 220 C 3 min/side; braise 160 C or 90 C simmer 90-120 min, lid | rolling and tying the Rouladen (D5) | 150 | 5 |
| DM03 | Breaded pork/veal cutlet / Wiener Schnitzel, Schnitzel Wiener Art | DE | 3 | 2,11 | pork_cutlet flour_wheat egg breadcrumbs salt pepper lemon oil_veg butter | DSO DPO DLI DUN DBL DME WSH GRS | POU SEA BRD PFR FLP DRN KWM GAR PLT | 2/3 | fat 160-170 C, 3 min per side; 2 cutlets per 28 cm pan | 3-stage breading; flipping without losing crust; batches | 30 | 4 |
| DM04 | Pork cutlet with mushroom sauce / Jägerschnitzel, Rahmschnitzel | DE | 2 | 14 | pork_cutlet mushroom onion cream flour_wheat salt pepper butter wine_white | DSO DPO DLI DUN DBL DME WLF GRS | POU SEA TOS PFR FLP PLA DIC TRE SLI SAU DGL RED SCE PLT | 2/2 | pan 170 C 3 min/side; sauce 10 min | flipping; mushroom trimming | 30 | 4 |
| DM05 | Cordon bleu / Cordon bleu | DE | 2 | 41 | pork_cutlet ham cheese_semi flour_wheat egg breadcrumbs salt pepper oil_veg | DSO DPO DLI DUN DBL DME GRS | BFL POU STU SEA BRD PFR FLP BKE PLT | 2/3 | pan 150 C 4 min/side, then oven 180 C 10 min | pocket cut + stuffing + breading (D5 chain) | 35 | 4 |
| DM06 | Roast pork with crackling / Schweinebraten, Krustenbraten | DE | 3 | 60 | pork_roast onion carrot celeriac garlic salt pepper spice_whole stock oil_veg | DSO DPO DLI DUN DME WSH GRS | SCO SEA PLA PLP PLH DIC RST BST DGL RED THK DRN CAR SCE PLT | 2/2 | oven 180 C 2-2.5 h then 220 C 15 min for rind; core 78-80 C; rest 15 min | scoring the rind, carving with bone; basting | 190 | 4 |
| DM07 | Rhenish marinated pot roast / Sauerbraten | DE | 2 | 10 | beef_roast vinegar wine_red onion carrot celeriac raisins spice_whole salt pepper oil_veg flour_wheat | DSO DPO DLI DUN DME WSH GRS | MAR PLA PLP PLH DIC DRY SER SAU DGL BRS THK PUR DRN CAR SCE PLT | 1/2 | marinade 2-3 d in fridge; sear 220 C; braise 160 C 2-2.5 h | 72 h vessel occupancy in cold; carving | 190 | 4 |
| DM08 | Pot roast / Schmorbraten, Rinderbraten | DE | 2 | 94 | beef_roast onion carrot celeriac tomato_paste wine_red stock salt pepper oil_veg | DSO DPO DLI DVI DUN DME WSH GRS | PLA PLP PLH DIC SEA SER SAU DGL BRS RES THK DRN CAR SCE PLT | 1/2 | sear 220 C; braise 160 C 2.5-3 h; core 90 C | carving; long unattended holding | 200 | 4 |
| DM09 | Goulash / Rindergulasch | DE | 3 | - | beef_cubes onion paprika_pw tomato_paste stock wine_red bellpepper salt oil_veg flour_wheat | DSO DPO DLI DVI DUN DME WSH | PLA DIC COR DIC TRM SAU SER DGL BRS THK PLT | 1/1 | onions 120 C 15 min, sear 220 C, braise 90-95 C 90-120 min | trimming sinew; long onion sauté | 130 | 5 |
| DM10 | Meatballs in caper sauce / Königsberger Klopse | DE | 2 | 25 | mince_mixed egg onion bread pickles butter flour_wheat stock cream lemon salt pepper | DSO DPO DLI DUN DBL DME WSH GRS | SOK PLA DIC KNM FRB SIM DRN MLT THK EMU SCE PLT | 2/2 | broth 90 C, 15-20 min; sauce roux 5 min | forming sticky balls that survive simmer | 45 | 4 |
| DM11 | Meat loaf / Hackbraten | DE | 2 | - | mince_mixed egg onion bread mustard paprika_pw ketchup salt pepper butter | DSO DPO DVI DUN DBL DME GRS | SOK PLA DIC KNM FRB LIN RST BST CAR PLT | 1/1 | oven 175-180 C 60 min, core 72 C | loaf forming; carving | 80 | 4 |
| DM12 | Cabbage rolls / Kohlrouladen | DE | 2 | 30 | savoy mince_mixed rice_long onion egg bread salt pepper stock flour_wheat oil_veg | DSO DPO DLI DUN DME WSH GRS | LSP BLA PLA DIC KNM STU WRP RLT SER BRS THK PLT | 2/2 | leaves blanch 3 min; rolls braise 160 C 45-60 min | separating intact leaves; wrapping and tying | 90 | 5 |
| DM13 | Stuffed peppers / Gefüllte Paprika | DE | 2 | 19 | bellpepper mince_mixed rice_long onion tomato_can cheese_semi salt pepper paprika_pw oil_veg | DSO DPO DLI DVI DUN DBL DME WSH GRS | COR PLA DIC BOL DRN SAU KNM STU BKE GRC TOP PLT | 2/2 | rice 15 min; bake 180 C 40 min in tomato sauce | cutting cap and coring pepper; stuffing | 70 | 4 |
| DM14 | Currywurst / Currywurst mit Sauce | DE | 3 | 49 | sausage_raw ketchup tomato_paste spice_curry paprika_pw onion vinegar oil_veg | DPO DLI DVI DUN DME | PFR PLA DIC SAU SIM MXW SLI SCE GAR PLT | 2/2 | sausage 160 C 8-10 min; sauce 10 min simmer | sausage turning; fries are separate | 25 | 4 |
| DM15 | Bratwurst with onion gravy / Bratwurst mit Zwiebelsoße | DE | 3 | - | sausage_raw onion butter flour_wheat stock mustard salt pepper | DSO DPO DVI DUN DBL DME GRS | PLA SLI PFR SAU THK RED SCE PLT | 1/1 | pan 150 C 10-12 min, onions 15 min | turning sausages; casing splits | 25 | 4 |
| DM16 | Smoked pork chop with sauerkraut / Kassler mit Sauerkraut | DE | 2 | 54 | kassler sauerkraut onion apple spice_whole wine_white potato water salt | DSO DLI DVI DUN DME WSH | PLA DIC PLS COR DIC SAU SIM BOL PLP DRN CAR PLT | 3/3 | sauerkraut simmer 40-60 min; Kassler 20 min in stock; potatoes 25 min | none; synchronising 3 pots | 60 | 4 |
| DM17 | Pork knuckle / Eisbein, Schweinshaxe | DE | 1 | - | pork_knuckle salt pepper spice_whole onion carrot celeriac stock oil_veg | DSO DPO DLI DUN DME WSH GRS | SEA PLA PLP PLH DIC RST BST SCO DRN CAR PLT | 1/1 | oven 170-200 C 2-2.5 h or simmer 2 h | carving bone-in; large piece | 170 | 4 |
| DM18 | Liver Berlin style / Leber Berliner Art | DE | 1 | 96 | liver apple onion flour_wheat butter salt pepper | DSO DPO DUN DBL DME WSH GRS | TRM SLM TOS PFR FLP PLA SLI SAU PLS COR SLI SAU PLT | 2/2 | pan 200 C 2 min per side; onions 10 min | trimming liver; short high-heat window | 25 | 5 |
| DM19 | Chicken fricassee / Hühnerfrikassee | DE | 3 | 62 | chicken_breast carrot peas_fz asparagus mushroom butter flour_wheat cream lemon stock rice_long salt pepper | DSO DPO DLI DUN DBL DME WSH WLF GRS | SIM DIC PLP DIC TRE SLI BOL MLT THK SIM SCE ABS PLT | 2/2 | chicken 20 min 90 C; roux sauce 10 min; rice 15 min | boned breast avoids DBN; traditional whole bird needs DBN | 50 | 4 |
| DM20 | Roast chicken / Brathähnchen | DE | 3 | 33 | chicken_whole butter paprika_pw salt thyme lemon oil_veg | DSO DPO DLI DUN DBL DME WSH WLF | SEA STU RLT RST BST RES CAR DGL RED SCE PLT | 1/1 | oven 200 C 60-75 min, core 82 C in thigh; rest 10 min | trussing and carving bone-in bird | 90 | 5 |
| DM21 | Roast goose or duck / Gänsebraten, Ente | DE | 1 | 91 | duck_goose apple onion dried_herbs orange salt pepper stock wine_red | DSO DPO DLI DUN DME WSH GRS | SEA PLS COR WED PLA WED STU RLT RST BST DRN CAR THK SCE PLT | 1/1 | oven 160 C 3-4 h + 200 C crisp; baste every 30 min; 4-5 kg | handling a 4-5 kg bird, carving; oven volume | 260 | 5 |
| DM22 | Veal strips in cream sauce / Zürcher Geschnetzeltes, Kalbsgeschnetzeltes | DE | 2 | 81 | veal mushroom onion cream wine_white butter flour_wheat lemon salt pepper | DSO DPO DLI DUN DBL DME WSH WLF GRS | SLM TOS TRE SLI PLA MIN SER DGL RED THK SCE PLT | 1/1 | pan 220 C in 3 batches of 1-2 min; sauce 8 min | batch searing small pieces | 30 | 4 |
| DM23 | Beef steak / Rumpsteak | DE | 3 | 8 | beef_steak butter thyme garlic salt pepper oil_veg | DSO DLI DUN DBL DME WLF GRS | PLA SEA SER FLP BST RES CAR PLT | 1/1 | pan 230-260 C 2-3 min per side, core 54-58 C medium rare; rest 5 min | flip timing and doneness by core temperature | 20 | 4 |
| DM24 | Grilled pork neck steak / Nackensteak vom Grill | DE | 2 | 16 | pork_cutlet oil_veg paprika_pw garlic onion mustard salt pepper | DSO DPO DLI DVI DUN DME GRS | MAR PLA MIN GRL FLP RES PLT | 1/1 | marinade 2-12 h; grill 250 C 5 min per side, core 72 C | flipping on grill | 25 | 4 |
| DM25 | Pork tenderloin medallions / Schweinefilet mit Sauce | DE | 2 | 64 | pork_tender cream mustard pepper salt butter broccoli | DSO DLI DVI DUN DBL DME WSH GRS | TRM SLM SEA SER FLP DGL RED SCE STM PLT | 2/2 | sear 200 C 2 min per side; broccoli steam 6 min | trimming silverskin | 30 | 5 |
| DM26 | Fried potatoes with sausage and egg / Kartoffel-Wurst-Gröstl | DE | 2 | - | potato sausage_cooked onion egg butter salt pepper dried_herbs | DSO DPO DUN DBL DME WSH GRS | BOL PLP COL SLI PLA DIC SAU PFR CRK PFR PLT | 2/2 | potatoes boiled the day before; pan 170 C 20 min; egg 3 min | peeling cooked potatoes; cracking eggs on top | 50 | 4 |
| DM27 | Kale with smoked sausage / Grünkohl mit Pinkel | DE | 2 | 59 | kale onion oats sausage_cured bacon stock mustard salt pepper potato fat_solid | DSO DPO DVI DUN DBL DME WSH GRS | PLA DIC SAU SIM BOL PLP DRN PRT PLT | 2/2 | kale simmer 60-90 min; potatoes 25 min | none hard with frozen chopped kale (fresh kale needs STR) | 100 | 4 |
| DM28 | Lentils with Spätzle / Linsen mit Spätzle | DE | 2 | 51 | lentils onion carrot celeriac bacon vinegar sausage_cooked flour_wheat egg water salt stock | DSO DPO DLI DUN DME WSH | RNS PLA PLP PLH DIC SAU SIM SFT CRK WHK RES EXT SIM DRN SAU PLT | 3/3 | lentils simmer 30-40 min; Spätzle 2-3 min per batch | Spätzle extrusion into boiling water | 60 | 4 |
| DM29 | Boiled beef with horseradish / Tafelspitz | DE | 1 | - | beef_roast carrot celeriac leek onion horseradish potato water salt spice_whole | DSO DLI DVI DUN DME WSH WLF | PLA PLP PLH TRE SIM SKM BOL PLP CAR DRN PLT | 2/2 | simmer 2.5-3 h at 90 C; skim | skimming; carving | 200 | 4 |
| DM30 | Roast chicken legs / Hähnchenschenkel aus dem Ofen | DE | 3 | - | chicken_thigh paprika_pw salt pepper oil_veg garlic | DSO DPO DLI DUN DME GRS | PLA MIN SEA MAR RST PLT | 1/1 | oven 200 C 40-45 min, core 82 C | none (whole pieces) | 50 | 4 |
| DM31 | Eggs in mustard sauce / Eier in Senfsoße | DE | 3 | 57 | egg mustard butter flour_wheat milk potato salt pepper water | DSO DPO DLI DVI DUN DBL WSH GRS | BOL COL PLE MLT THK SIM PLP BOL PLT | 2/2 | eggs 9 min; sauce roux 8 min; potatoes 25 min | peeling boiled eggs; roux | 40 | 4 |
| DM32 | Frankfurt green sauce with potatoes and egg / Frankfurter Grüne Soße | DE | 1 | 87 | parsley chives dill basil quark yoghurt sourcream egg potato mustard salt pepper water | DSO DLI DVI DUN WSH WLF GRS | BOL COL PLE PLP BOL STR CHH MXW CHL DIC PLT | 2/3 | potatoes 25 min, eggs 9 min, sauce cold | stripping and chopping 7 herbs; peeling eggs | 50 | 4 |
| DM33 | Swabian Maultaschen in broth or fried / Maultaschen | DE | 2 | 32 | pasta_fresh stock onion egg butter chives salt | DSO DPO DUN DBL WLF | SIM SLI PLA SLI SAU CRK PFR GAR PLT | 1/2 | simmer 10 min or fry 170 C 4 min per side | none (ready-made filled pasta) | 20 | 4 |
| DM34 | Chicken in cream sauce / Hähnchen-Geschnetzeltes | DE | 2 | - | chicken_breast mushroom onion cream stock flour_wheat rice_long salt pepper paprika_pw oil_veg | DSO DPO DLI DUN DME WLF GRS | SLM TOS TRE SLI PLA DIC SER SAU DGL THK SCE ABS PLT | 2/2 | chicken sear 200 C 5 min; sauce 8 min; rice 15 min | batch searing | 35 | 4 |
| DM35 | Meatballs in pepper pan / Paprika-Hackbällchen-Pfanne | DE | 2 | 21 | mince_mixed egg onion bread bellpepper tomato_can cream paprika_pw salt pepper oil_veg rice_long | DSO DPO DLI DVI DUN DME WSH GRS | SOK PLA DIC KNM FRB PFR FLP COR JUL SAU SIM ABS PLT | 2/2 | balls 170 C 8 min; sauce 12 min; rice 15 min | forming balls; flipping/turning in sauce | 40 | 4 |
| DM36 | Balsamic chicken on pan vegetables / Balsamicohähnchen mit Pfannengemüse | DE | 2 | 48 | chicken_breast bellpepper zucchini onion vinegar oil_olive honey thyme salt pepper | DSO DLI DVI DUN DME WSH WLF GRS | SEA SLM PFR FLP PLA SLI COR JUL SAU RED PLT | 2/2 | chicken 180 C 5 min per side; vegetables 10 min | flipping fillets; cutting vegetables | 30 | 4 |

### 3.3 Soups and stews (20)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| SP01 | Pea soup with sausage / Erbsensuppe | DE | 2 | - | beans_dry potato carrot onion bacon sausage_cooked stock dried_herbs salt pepper water | DSO DPO DLI DUN DME WSH GRS | SOK RNS PLA PLP DIC PLH DIC SAU SIM PUR SLI PLT | 1/1 | soak 12 h; simmer 60-90 min | long soak occupancy; scorch risk when thick | 110 | 4 |
| SP02 | Lentil soup with sausage / Linsensuppe | DE | 3 | 83 | lentils carrot celeriac onion potato sausage_cooked vinegar stock bacon salt pepper water | DSO DPO DLI DUN DME WSH GRS | RNS PLA PLP PLH DIC SAU SIM SLI PLT | 1/1 | simmer 30-40 min | none hard (root peeling) | 50 | 4 |
| SP03 | Potato soup with sausage / Kartoffelsuppe | DE | 3 | 46 | potato carrot celeriac leek onion sausage_cooked stock cream dried_herbs parsley salt pepper water | DSO DPO DLI DUN DME WSH WLF GRS | PLP PLH TRE PLA DIC SAU SIM PUR SLI CHH GAR PLT | 1/1 | simmer 25 min; purée partly | peeling 4 root types | 45 | 4 |
| SP04 | Goulash soup / Gulaschsuppe | DE | 2 | - | beef_cubes bellpepper onion potato tomato_can paprika_pw stock salt pepper oil_veg tomato_paste | DSO DPO DLI DVI DUN DME WSH GRS | PLA DIC COR DIC PLP DIC TRM SER SAU SIM PLT | 1/1 | sear 220 C; simmer 90 min | trimming; long simmer | 110 | 5 |
| SP05 | Chicken soup with noodles / Hühnersuppe mit Nudeln | DE | 3 | 80 | chicken_thigh carrot celeriac leek onion pasta_dry parsley salt pepper water parsnip | DSO DLI DUN DME WSH WLF GRS | PLA PLP PLH TRE SIM SKM DRN DBN DIC BOL CHH PLT | 2/2 | simmer 60-90 min at 90 C; noodles 6 min | skimming; picking meat from bone | 100 | 5 |
| SP06 | Vegetable soup / Gemüsesuppe | DE | 3 | 70 | carrot potato leek celeriac greenbean peas_fz tomato stock parsley salt pepper oil_veg water parsnip | DSO DPO DLI DUN WSH WLF GRS | PLP PLH TRE COR DIC SAU SIM CHH PLT | 1/1 | simmer 20-30 min | trimming green beans | 35 | 4 |
| SP07 | Pumpkin soup / Kürbissuppe | DE | 2 | 88 | pumpkin onion carrot cream ginger coconutmilk stock seeds salt pepper oil_veg | DSO DPO DLI DVI DUN WSH GRS | COR PLA DIC WED DIC PLH SAU SIM PUR GAR PLT | 1/1 | simmer 20 min; blend hot | cutting and deseeding a hard pumpkin | 40 | 4 |
| SP08 | Tomato soup / Tomatensuppe | DE | 3 | - | tomato_can onion garlic cream basil stock sugar oil_olive salt pepper | DSO DPO DLI DVI DUN WLF GRS | PLA DIC MIN SAU SIM PUR STR GAR PLT | 1/1 | simmer 15 min; blend | none hard | 25 | 4 |
| SP09 | Cream of asparagus soup / Spargelcremesuppe | DE | 1 | - | asparagus butter flour_wheat cream egg stock salt pepper lemon sugar water | DSO DPO DLI DUN DBL WSH WLF GRS | PLH TRE DIC SIM MLT THK PUR SEP WHK THK SCE PLT | 1/2 | peels+ends stock 20 min; simmer 15 min | peeling asparagus; egg yolk liaison | 50 | 4 |
| SP10 | French onion soup / Zwiebelsuppe | FR | 1 | - | onion butter wine_white stock bread cheese_hard salt pepper dried_herbs | DSO DPO DLI DUN DBL GRS | PLA SLI CRL DGL SIM SLB TST TOP GRL PLT | 1/2 | onions caramelise 30-40 min 120-140 C; simmer 20 min; gratinate 250 C 5 min | long caramelisation; gratinate in portion bowls | 70 | 4 |
| SP11 | Pancake strips in broth / Pfannkuchensuppe, Flädlesuppe | DE | 2 | 92 | flour_wheat milk egg salt butter stock chives | DSO DPO DLI DUN DBL WLF | MXD CRK WHK RES PTH PFR FLP SLI SIM CHH PLT | 2/2 | pancakes 2 min per side; broth 90 C | flipping thin pancakes (as BF06) | 45 | 4 |
| SP12 | Green bean stew / Grüne-Bohnen-Eintopf | DE | 2 | - | greenbean potato mince_mixed onion stock dried_herbs salt pepper oil_veg water | DSO DPO DLI DUN DME WSH WLF GRS | TRE PLP DIC PLA DIC SER SAU SIM PLT | 1/1 | simmer 30-40 min | trimming beans | 50 | 4 |
| SP13 | Savoy cabbage or turnip stew / Wirsingeintopf, Kohleintopf | DE | 2 | 63 | savoy potato mince_mixed onion carrot stock salt pepper dried_herbs oil_veg | DSO DPO DLI DUN DME WSH GRS | COR SLI PLP PLA DIC SER SAU SIM PLT | 1/1 | simmer 35 min | coring and shredding cabbage | 50 | 4 |
| SP14 | Carrot-orange soup / Möhren-Orangen-Suppe | DE | 1 | 76 | carrot orange ginger cream stock onion butter salt pepper | DSO DPO DLI DUN DBL WSH GRS | PLP DIC PLA JUI SAU SIM PUR GAR PLT | 1/1 | simmer 20 min | peeling carrots | 35 | 4 |
| SP15 | Soljanka / Soljanka | DE | 1 | - | sausage_cooked pickles tomato_paste onion stock sourcream lemon pepper salt oil_veg | DSO DPO DLI DVI DUN DME WSH GRS | PLA DIC SLI SAU SIM GAR PLT | 1/1 | simmer 30 min | none hard | 40 | 4 |
| SP16 | Gazpacho / Gazpacho | ME | 1 | - | tomato cucumber bellpepper garlic oil_olive bread vinegar salt | DSO DLI DUN WSH | PLM PLS COR DIC PLA SOK PUR CHL GAR PLT | 0/1 | cold blend, chill 2 h | peeling cucumber, coring peppers | 20 | 4 |
| SP17 | Miso soup / Miso-Suppe | AS | 1 | - | miso tofu nori springonion water | DLI DVI DUN DBL WLF | SIM DIC SLI DVI GAR PLT | 1/1 | dashi 80 C 10 min; miso not boiled | none hard | 15 | 3 |
| SP18 | Minestrone / Minestrone | IT | 2 | - | carrot potato celerystalk onion tomato_can beans_can pasta_dry oil_olive stock basil salt pepper zucchini | DSO DPO DLI DVI DUN WSH WLF GRS | PLP DIC PLA DIC SAU SIM BOL GAR PLT | 1/1 | simmer 40 min; pasta last 10 min | none hard | 55 | 4 |
| SP19 | Creamy mushroom soup / Champignoncremesuppe | DE | 2 | - | mushroom onion butter flour_wheat stock cream parsley salt pepper | DSO DPO DLI DUN DBL WLF GRS | TRE SLI PLA DIC SAU THK SIM PUR CHH PLT | 1/1 | simmer 20 min | mushroom trimming | 30 | 4 |
| SP20 | Potato goulash with sausage / Kartoffelgulasch | DE | 2 | 75 | potato sausage_cooked onion bellpepper paprika_pw tomato_paste stock salt pepper oil_veg dried_herbs | DSO DPO DLI DVI DUN DME WSH GRS | PLP PLA DIC COR DIC SAU SIM SLI PLT | 1/1 | simmer 25 min | peeling potatoes | 40 | 4 |

### 3.4 Side dishes (28)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| SD01 | Boiled potatoes / Salzkartoffeln | DE | 3 | - | potato water salt | DSO DLI DUN WSH | PLP WED BOL DRN KWM PRT | 1/1 | boil 100 C 20-25 min | peeling potatoes (D3 abrasive, D4 knife) | 30 | 3 |
| SD02 | Mashed potatoes / Kartoffelpüree | DE | 3 | - | potato butter milk nutmeg salt water | DSO DLI DUN DBL WSH GRF | PLP WED BOL DRN MSH MLT MXW KWM PRT | 1/1 | boil 20-25 min; mash hot; milk 80 C | peeling; do not overwork starch (gluey) | 35 | 3 |
| SD03 | Fried potatoes / Bratkartoffeln | DE | 3 | 29 | potato onion bacon oil_veg salt pepper dried_herbs | DSO DPO DLI DUN DME WSH GRS | BOL COL PLP SLI PLA DIC SAU PFR STC PLT | 2/2 | boil 20 min (day before), pan 160-180 C 20 min turning | turning slices without mashing | 50 | 4 |
| SD04 | French fries / Pommes frites | INT | 3 | 7 | potato oil_veg salt | DSO DLI DUN WSH | PLP JUL RNS DRY DFR DRN SEA PLT | 1/1 | fryer 150 C 5 min blanch, 180 C 3 min; 500 g per load in 2 L oil | peeling; fryer safety and oil cleaning | 30 | 3 |
| SD05 | Potato pancakes / Kartoffelpuffer, Reibekuchen | DE | 2 | 26 | potato onion egg flour_wheat salt oil_veg | DSO DPO DLI DUN WSH | PLP PLA GRC SQZ CRK MXW PFR FLP DRN KWM PLT | 1/2 | fat 170 C, 4-5 min per side, 4 per pan | squeezing wet potato mass; flipping fragile cake | 45 | 4 |
| SD06 | Potato salad / Kartoffelsalat | DE | 3 | 52 | potato onion stock vinegar oil_veg mustard pickles salt pepper dried_herbs water | DSO DPO DLI DVI DUN WSH GRS | BOL PLP SLI PLA DIC SIM TOS RES | 2/2 | boil 20 min; peel and slice warm; dressing stock 80 C; rest 30 min | peeling hot potatoes | 60 | 4 |
| SD07 | Potato dumplings / Kartoffelklöße, Knödel | DE | 2 | - | potato cornstarch egg semolina nutmeg salt water | DSO DPO DLI DUN WSH GRF | BOL PLP MSH MXD CRK KNM FRK SIM DRN KWM PLT | 2/2 | potatoes 25 min; dumplings 90 C 20 min | forming sticky dumplings that hold in water | 70 | 3 |
| SD08 | Bread dumplings / Semmelknödel | DE | 2 | 6 | bread milk egg onion parsley butter salt nutmeg water | DSO DLI DUN DBL WLF GRF | PLA DIC SAU CHH MXW CRK KNM RES FRK SIM DRN PLT | 2/2 | onion 5 min; rest 15 min; simmer 90 C 20 min (not boil) | forming and simmering without disintegration | 45 | 4 |
| SD09 | Spätzle / Spätzle | DE | 3 | - | flour_wheat egg water salt nutmeg butter | DSO DPO DLI DUN DBL GRF | SFT CRK WHK RES EXT SIM DRN SAU PLT | 2/2 | batter beat 5 min; boiling salted water, 2-3 min per batch; butter 100 C | extruding batter into boiling water; batching | 30 | 3 |
| SD10 | Rice / Reis | INT | 3 | - | rice_long water salt | DSO DLI | RNS ABS RES PRT | 1/1 | 1:2 water, 12-18 min covered; rest 5 min | none | 25 | 3 |
| SD11 | Red cabbage with apple / Apfelrotkohl | DE | 3 | - | redcab apple onion vinegar sugar spice_whole wine_red fat_solid salt | DSO DLI DUN DBL WSH | COR SLI PLA DIC PLS COR DIC SAU BRS PLT | 1/1 | simmer 60-90 min covered | coring and finely shredding a hard head | 90 | 4 |
| SD12 | Sauerkraut, cooked / Sauerkraut | DE | 2 | - | sauerkraut onion bacon spice_whole wine_white apple fat_solid | DSO DLI DVI DUN DBL DME WSH | PLA DIC SAU SIM PLT | 1/1 | simmer 40-60 min | none | 60 | 4 |
| SD13 | Creamed spinach / Rahmspinat | DE | 2 | 18 | spinach_fz cream onion garlic butter nutmeg salt pepper | DSO DLI DUN DBL GRS GRF | PLA MIN SAU SIM THK PLT | 1/1 | thaw and simmer 10-15 min | none (frozen) | 20 | 4 |
| SD14 | Brussels sprouts / Rosenkohl | DE | 2 | - | sprouts butter nutmeg salt water | DSO DLI DUN DBL WSH GRF | TRE BOL DRN SAU PLT | 1/1 | boil 8-10 min; butter toss | trimming and cross-cutting stems | 25 | 4 |
| SD15 | Green beans with bacon / Grüne Bohnen mit Speck | DE | 2 | - | greenbean bacon onion butter dried_herbs salt water | DSO DPO DLI DUN DBL DME WLF | TRE BOL DRN PLA DIC SAU TOS PLT | 2/2 | boil 10-12 min; bacon-onion pan 8 min | topping and tailing beans (D4) | 25 | 4 |
| SD16 | Kohlrabi in cream / Kohlrabigemüse | DE | 1 | - | kohlrabi butter flour_wheat cream milk nutmeg salt | DSO DPO DLI DUN DBL WSH GRF | PLH SLI SIM THK PLT | 1/1 | simmer 12-15 min | peeling kohlrabi | 25 | 4 |
| SD17 | Peas and carrots / Erbsen und Möhren | DE | 3 | - | carrot peas_fz butter sugar salt parsley water | DSO DLI DUN DBL WSH WLF | PLP DIC SIM DRN TOS CHH PLT | 1/1 | simmer 8-10 min | none hard | 20 | 3 |
| SD18 | Cauliflower or broccoli with butter crumbs / Blumenkohl | DE | 2 | - | cauli butter breadcrumbs nutmeg salt water | DSO DLI DUN DBL WSH GRF | BCR STR BOL DRN TST TOS PLT | 2/2 | boil 8-10 min; crumbs toasted 4 min | breaking into florets (D4) | 25 | 4 |
| SD19 | Asparagus with hollandaise and potatoes / Spargel mit Sauce Hollandaise | DE | 2 | 20 | asparagus butter egg lemon potato ham water salt sugar | DSO DLI DUN DBL DME WSH WLF | PLH TRE BOL PLP BOL DRN SEP MLT BMA WHK EMU KWM PLT | 3/4 | asparagus 12-15 min at 95 C; potatoes 20 min; hollandaise 65-70 C 10 min | peeling asparagus (D4); hollandaise emulsion | 50 | 4 |
| SD20 | Oven vegetables / Ofengemüse | INT | 3 | 68 | carrot zucchini bellpepper potato onion oil_olive thyme salt pepper seeds sweetpot | DSO DLI DUN WSH WLF GRS | PLP TRE COR PLA WED TOS RST TST PLT | 1/1 | oven 200 C 35-45 min | cutting mixed vegetables | 55 | 4 |
| SD21 | Potato croquettes / Kroketten | DE | 1 | - | potato egg nutmeg breadcrumbs flour_wheat oil_veg salt | DSO DPO DLI DUN WSH GRF | BOL PLP MSH SEP FRM BRD DFR DRN PLT | 2/3 | dough cold; fry 175 C 3-4 min | forming and breading soft croquettes | 70 | 4 |
| SD22 | Schupfnudeln with sauerkraut / Kraut-Schupfnudeln | DE | 2 | 77 | potato flour_wheat egg nutmeg sauerkraut onion bacon salt water butter | DSO DPO DLI DVI DUN DBL DME WSH GRF | BOL PLP MSH KNM FRM CUD SIM DRN PLA DIC SAU PFR PLT | 3/3 | dough rolls 15 mm, simmer 3 min, fry 170 C 8 min | rolling finger-shaped dough pieces | 70 | 4 |
| SD23 | Couscous / Couscous | ME | 2 | - | couscous stock butter salt | DSO DPO DBL | ABS RES MLT TOS PRT | 1/1 | boiling stock 1:1, cover 5 min | none | 10 | 3 |
| SD24 | Potato wedges / Kartoffelecken | INT | 2 | - | potato oil_veg paprika_pw salt | DSO DPO DLI DUN WSH | WED TOS RST PLT | 1/1 | oven 200-220 C 35 min | none (unpeeled) | 40 | 3 |
| SD25 | Baked potato with herb quark / Ofenkartoffel mit Kräuterquark | DE | 2 | 72 | potato quark sourcream chives parsley salt pepper butter | DSO DVI DUN DBL WSH WLF GRS | SEA RST WED STU CHH MXW PLT | 1/2 | oven 200 C 60 min | none | 65 | 4 |
| SD26 | Rösti / Rösti | DE | 1 | - | potato butter salt | DSO DUN DBL WSH | BOL COL PLP GRC PFR FLP PLT | 1/1 | pan 150 C 12 min per side | flipping a 20 cm potato cake | 50 | 4 |
| SD27 | Mushrooms in cream / Rahmchampignons | DE | 2 | - | mushroom onion butter cream parsley salt pepper wine_white | DSO DLI DUN DBL WLF GRS | TRE SLI PLA DIC SAU DGL RED CHH PLT | 1/1 | pan 180 C 8 min | mushroom handling | 15 | 4 |
| SD28 | Applesauce / Apfelmus | DE | 2 | - | apple sugar lemon cinnamon water | DSO DPO DLI DUN WSH | PLS COR DIC SIM MSH PLT | 1/1 | simmer 15 min | peeling and coring apples (D4) | 25 | 4 |

### 3.5 Basic sauces (5)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| SC01 | White sauce / Béchamel, Mehlschwitze | INT | 3 | - | butter flour_wheat milk nutmeg salt pepper | DSO DPO DLI DUN DBL GRS GRF | MLT MXD DLI STC SIM PLT | 1/1 | roux 2 min, milk in stages, simmer 8-10 min | lumps; scorch | 15 | 3 |
| SC02 | Gravy from roast juices / Bratensoße, Jus | DE | 3 | - | stock flour_wheat tomato_paste wine_red salt pepper | DSO DPO DLI DVI GRS | DGL RED THK DRN SCE | 1/1 | deglaze 200 C; reduce 10-15 min | none | 20 | 2 |
| SC03 | Vinaigrette or yoghurt dressing / Salatdressing | INT | 3 | - | oil_olive vinegar mustard honey salt pepper parsley yoghurt | DSO DLI DVI DUN WLF GRS | DLI DVI EMU CHH | 0/1 | cold | none | 5 | 3 |
| SC04 | Mayonnaise (home-made) / Mayonnaise | INT | 1 | - | egg oil_veg mustard lemon salt | DSO DLI DVI DUN WSH | SEP EMU | 0/1 | cold, oil added drop by drop | emulsion stability | 8 | 4 |
| SC05 | Vanilla sauce / Vanillesauce | DE | 2 | - | milk egg sugar vanilla cornstarch | DSO DPO DLI DUN | SEP WHK SIM STC THK CHL | 1/1 | milk 80 C, rose 80 C, do not boil | egg scrambling at >85 C | 20 | 4 |

### 3.6 Salads (16)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| SA01 | Mixed green salad / Bunter Salat, gemischter Salat | DE | 3 | 34 | lettuce tomato cucumber carrot bellpepper oil_olive vinegar mustard salt pepper parsley radish | DSO DLI DVI DUN WSH WLF GRS | WED SLI PLS SLI PLP GRC COR JUL EMU TOS GAR PLT | 0/2 | cold | washing/drying fragile lettuce; tossing gently | 15 | 4 |
| SA02 | Cucumber salad / Gurkensalat | DE | 3 | - | cucumber dill vinegar oil_veg sugar salt sourcream pepper | DSO DLI DVI DUN WSH WLF GRS | PLS SLI CHH MXW MAR PLT | 0/1 | cold; 15 min | peeling cucumber | 10 | 4 |
| SA03 | Tomato salad with onions / Tomatensalat | DE | 3 | - | tomato onion vinegar oil_olive salt pepper parsley sugar | DSO DLI DUN WSH WLF GRS | WED SLI PLA SLI MXW CHH PLT | 0/1 | cold | none | 8 | 4 |
| SA04 | Pasta salad with mayonnaise / Nudelsalat | DE | 3 | 38 | pasta_dry ham pickles peas_fz egg mayo yoghurt mustard salt pepper corn_can | DSO DVI DUN DME GRS | BOL DRN RNS COL DIC BOL COL PLE DIC MXW TOS CHL PLT | 2/2 | pasta 10 min; eggs 9 min; chill 2-12 h | peeling boiled eggs; dicing | 30 | 4 |
| SA05 | Coleslaw / Krautsalat | DE | 2 | - | whitecab carrot mayo vinegar sugar salt pepper oil_veg spice_whole | DSO DLI DVI DUN WSH GRS | COR SLI PLP GRC SQZ MXW MAR PLT | 0/1 | cold; steep 1 h | coring and fine shredding cabbage | 15 | 4 |
| SA06 | Sausage salad / Wurstsalat | DE | 1 | - | sausage_cooked cheese_semi onion pickles vinegar oil_veg salt pepper parsley | DSO DLI DUN DBL DME WLF GRS | PLA SLI JUL DIC MXW MAR CHH PLT | 0/1 | cold; steep 30 min | none hard | 15 | 4 |
| SA07 | Greek salad / Griechischer Salat | ME | 2 | 86 | tomato cucumber bellpepper onion feta pickles oil_olive dried_herbs salt mint | DSO DPO DLI DUN DBL WSH WLF | WED PLS SLI COR JUL PLA SLI DIC TOS GAR PLT | 0/2 | cold | cutting; feta crumbles | 15 | 4 |
| SA08 | Caesar salad with chicken / Caesar Salad | US | 2 | - | lettuce chicken_breast bread cheese_hard egg oil_olive lemon mustard pickles salt pepper | DSO DLI DVI DUN DBL DME WSH WLF GRS | STR TST PFR SLB SLI GRF EMU TOS PLT | 1/2 | chicken pan 200 C 5 min per side; croutons 180 C 6 min | dressing emulsion; cutting chicken; tossing without bruising | 30 | 4 |
| SA09 | Tomato mozzarella / Caprese | IT | 2 | - | cherrytom mozzarella basil oil_olive salt pepper | DSO DLI DUN WSH WLF GRS | SLI SLI LAY GAR PLT | 0/1 | cold | alternate slice layout | 8 | 3 |
| SA10 | Couscous salad / Couscoussalat | ME | 1 | 73 | couscous tomato cucumber bellpepper mint lemon oil_olive salt stock | DSO DPO DLI DUN WSH WLF | ABS RES DIC COR CHH JUI TOS PLT | 1/1 | cold | dicing mixed vegetables | 20 | 4 |
| SA11 | Bean or lentil salad / Bohnensalat | DE | 1 | - | beans_can onion vinegar oil_veg salt pepper parsley | DSO DLI DVI DUN WLF GRS | RNS DRN PLA DIC MXW MAR PLT | 0/1 | cold; steep 1 h | none hard | 10 | 4 |
| SA12 | Carrot-apple salad / Möhrensalat, Rohkost | DE | 2 | - | carrot apple lemon orange oil_veg sugar salt | DSO DLI DUN WSH | PLP GRC PLS COR GRC JUI MXW PLT | 0/1 | cold | peeling apple | 10 | 4 |
| SA13 | Egg salad / Eiersalat | DE | 2 | - | egg mayo onion chives pickles mustard salt pepper | DSO DVI DUN WLF GRS | BOL COL PLE DIC PLA DIC CHH MXW CHL PLT | 1/2 | eggs 9 min; chill | peeling boiled eggs | 25 | 4 |
| SA14 | Lamb's lettuce with bacon and egg / Feldsalat mit Speck | DE | 1 | - | saladmix bacon egg bread vinegar oil_veg mustard salt | DSO DLI DVI DUN DME WLF | DIC PFR TST SLB BOL PLE EMU TOS PLT | 2/2 | bacon pan 160 C 5 min; egg 9 min | washing fragile leaves; warm dressing | 20 | 4 |
| SA15 | Salade niçoise / Salade niçoise | FR | 1 | 79 | tuna_can egg potato greenbean tomato pickles lettuce oil_olive vinegar mustard salt | DSO DLI DVI DUN WSH WLF | BOL PLE BOL PLP BOL TRE SLI WED EMU LAY ASM PLT | 3/4 | eggs 9 min; potatoes 20 min; beans 8 min | assembling composed plate | 45 | 4 |
| SA16 | Marinated beetroot salad / Rote-Bete-Salat | DE | 1 | - | beet onion vinegar oil_veg horseradish salt sugar | DSO DLI DVI DUN | PLH DIC PLA SLI MXW MAR PLT | 0/1 | cold; steep 1 h | peeling raw beet; use cooked | 15 | 4 |

### 3.7 Pasta and Italian (20)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| IT01 | Spaghetti Bolognese / Spaghetti Bolognese | IT | 3 | 3 | mince_mixed onion carrot celeriac garlic tomato_can tomato_paste wine_red stock oil_olive sugar dried_herbs pasta_dry cheese_hard water salt pepper | DSO DPO DLI DVI DUN DBL DME WSH GRS | PLA PLP PLH DIC MIN SER SAU DGL SIM RED BOL DRN TOS GRF PLT | 2/3 | sauce simmer 45-90 min; pasta 1 L per 100 g, 9-11 min | synchronising sauce and pasta; otherwise no hard step | 75 | 4 |
| IT02 | Spaghetti Carbonara / Spaghetti Carbonara | IT | 3 | 23 | pasta_dry egg cheese_hard bacon pepper water salt | DSO DLI DUN DBL DME GRS | DIC PFR CRK SEP WHK GRF BOL DRN EMU TOS PLT | 2/3 | guanciale pan 150 C 6 min; pasta 10 min; sauce below 70 C off heat | temperature-controlled egg emulsion (scramble risk) | 20 | 4 |
| IT03 | Spaghetti aglio e olio / Spaghetti aglio e olio | IT | 2 | - | pasta_dry garlic chili oil_olive parsley salt water | DSO DLI DUN WSH WLF | PLA SLI CHH SAU BOL DRN TOS PLT | 2/2 | garlic 120 C 2 min (do not burn); pasta 10 min | garlic peeling; not burning garlic | 20 | 4 |
| IT04 | Spaghetti with tomato sauce / Napoli, Arrabbiata, alla busara | IT | 3 | 3 | pasta_dry tomato_can onion garlic basil oil_olive chili sugar water salt pepper | DSO DLI DVI DUN WSH WLF GRS | PLA DIC MIN SAU SIM BOL DRN TOS GAR PLT | 2/2 | sauce 15-20 min; pasta 10 min | none hard | 25 | 4 |
| IT05 | Lasagne / Lasagne | IT | 3 | 1 | lasagne_sheets mince_mixed onion carrot tomato_can tomato_paste wine_red butter flour_wheat milk nutmeg cheese_hard mozzarella oil_olive salt pepper dried_herbs | DSO DPO DLI DVI DUN DBL DME WSH GRS GRF | PLA PLP DIC SER SAU SIM MLT MXD STC LAY LAY LAY GRC TOP BKE RES SLB PRT PLT | 3/4 | Bolognese 45 min; béchamel 10 min; bake 180-200 C 40 min; rest 15 min | layer assembly; cutting hot lasagne into clean portions | 120 | 4 |
| IT06 | Pasta with pesto / Nudeln mit Pesto | IT | 3 | 9 | pasta_dry pesto cheese_hard seeds water salt oil_olive | DSO DLI DVI DBL | BOL DRN TST TOS GRF GAR PLT | 1/1 | pasta 10 min | none | 15 | 3 |
| IT07 | Salmon tagliatelle in cream sauce / Lachs-Tagliatelle | IT | 2 | 27 | pasta_dry salmon cream dill lemon onion butter wine_white water salt pepper | DSO DLI DUN DBL DME WSH WLF GRS | PLA DIC SLM SAU DGL SIM THK BOL DRN TOS CHH PLT | 2/2 | sauce 8 min; salmon added last 3 min; pasta 9 min | fragile salmon cubes break when stirred | 25 | 4 |
| IT08 | Gnocchi (home-made) / Gnocchi | IT | 1 | - | potato flour_wheat egg salt nutmeg butter thyme cheese_hard water | DSO DPO DLI DUN DBL WSH WLF GRF | BOL PLP MSH KNM FRM CUD BOL DRN MLT TOS GRF PLT | 2/2 | potatoes 30 min; gnocchi 2-3 min until float; butter 120 C | rolling and cutting sticky dough | 70 | 4 |
| IT09 | Risotto / Risotto (Milanese, Spargel) | IT | 2 | 42 | rice_round onion butter wine_white stock cheese_hard spice_curry salt pepper | DSO DPO DLI DUN DBL GRS | PLA DIC SAU TST DGL STC MXW MLT PLT | 1/1 | rice toast 2 min; stock stepwise 18 min at 90 C; off heat butter+parmesan | continuous stirring with stepwise dosing (solvable) | 30 | 4 |
| IT10 | Pizza, home-made / Pizza Margherita, Salami | IT | 3 | 4 | flour_wheat yeast water salt oil_olive tomato_can mozzarella basil sausage_cured cheese_hard | DSO DPO DLI DVI DUN DBL DME WLF | KND PRF SHD ROL LIN SPR TOP BKE SLB PRT | 1/2 | dough 10 min, proof 1-24 h; oven 250 C 8-12 min on stone | stretching dough to 30 cm and transferring to oven | 90 | 4 |
| IT11 | Aubergine parmigiana / Parmigiana di melanzane | IT | 1 | - | eggplant tomato_can mozzarella cheese_hard basil oil_olive flour_wheat egg salt garlic | DSO DPO DLI DVI DUN DBL WSH WLF | PLA TRE SLI SEA DRY PFR LAY TOP BKE PLT | 2/2 | slices 180 C 2 min per side; bake 180 C 40 min | frying many slices; layering | 75 | 4 |
| IT12 | Saltimbocca / Saltimbocca | IT | 1 | - | veal ham dried_herbs wine_white butter flour_wheat salt pepper | DSO DPO DLI DBL DME GRS | POU SEA ASM PFR FLP DGL RED SCE PLT | 1/1 | pan 180 C 2 min per side | attaching ham+sage to cutlet | 20 | 4 |
| IT13 | Bruschetta / Bruschetta | IT | 2 | - | bread tomato garlic basil oil_olive salt pepper | DSO DLI DUN WSH WLF GRS | SLB TST DIC PLA MIN TOS SPR PLT | 0/1 | toast 200 C 3 min | none hard | 15 | 4 |
| IT14 | Polenta / Polenta | IT | 1 | - | semolina water butter cheese_hard salt | DSO DLI DBL | STC MLT PLT | 1/1 | simmer 30-40 min stir | stirring thick mass | 40 | 3 |
| IT15 | Braised veal shank / Ossobuco | IT | 1 | - | veal carrot celerystalk onion tomato_can wine_white stock flour_wheat oil_olive lemon garlic parsley salt pepper | DSO DPO DLI DVI DUN DME WSH WLF GRS | PLA PLP DIC TOS SER SAU DGL BRS GAR PLT | 1/1 | braise 160 C 2 h | bone-in handling | 150 | 4 |
| IT16 | Four-cheese pasta / Pasta quattro formaggi | IT | 2 | 45 | pasta_dry cheese_hard cheese_semi creamcheese cream pepper water salt | DSO DLI DVI DBL GRS | GRC GRC MLT STC BOL DRN TOS PLT | 2/2 | sauce 8 min; pasta 10 min | cheese sauce splits when overheated | 20 | 3 |
| IT17 | Tortellini with ham-cream sauce / Tortellini in Schinken-Sahne-Soße | IT | 3 | - | pasta_fresh ham cream onion butter cheese_hard peas_fz salt pepper water | DSO DLI DUN DBL DME GRS | PLA DIC DIC SAU SIM BOL DRN TOS GRF PLT | 2/2 | sauce 8 min; pasta 4 min | none | 20 | 4 |
| IT18 | Cannelloni with spinach and ricotta / Cannelloni | IT | 1 | - | pasta_dry spinach_fz creamcheese tomato_can onion garlic cheese_hard mozzarella oil_olive nutmeg salt | DSO DLI DVI DUN DBL GRF | PLA MIN SAU MXW STU LAY TOP BKE PRT PLT | 2/2 | filling 10 min; bake 180 C 35 min | stuffing dry tubes | 60 | 4 |
| IT19 | Cheese Spätzle with fried onions / Käsespätzle | DE | 3 | 13 | flour_wheat egg water salt cheese_semi onion butter nutmeg | DSO DPO DLI DUN DBL GRF | SFT CRK WHK RES EXT SIM DRN GRC LAY PLA SLI SAU TOP BKE PLT | 3/3 | Spätzle 2-3 min per batch; onions 15 min 140 C; layer with cheese; oven 200 C 8 min | Spätzle extrusion; layering hot batches | 50 | 4 |
| IT20 | Tuna pasta / Thunfischnudeln | IT | 2 | - | pasta_dry tuna_can tomato_can onion garlic pickles oil_olive water salt pepper | DSO DLI DVI DUN GRS | PLA DIC MIN SAU SIM BOL DRN TOS PLT | 2/2 | sauce 12 min; pasta 10 min | none | 25 | 4 |

### 3.8 French (7)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| FR01 | Quiche Lorraine / Quiche Lorraine | FR | 2 | - | flour_wheat butter egg cream bacon onion cheese_semi nutmeg salt pepper milk | DSO DPO DLI DUN DBL DME GRS GRF | RUB KND RES ROL LIN DIC PLA DIC SAU CRK WHK MXW GRC BKE SLB PRT PLT | 2/2 | dough rest 30 min; blind bake 180 C 15 min; bake 180 C 35 min | rolling dough into tin (or buy ready dough) | 100 | 4 |
| FR02 | Ratatouille / Ratatouille | FR | 2 | - | eggplant zucchini bellpepper tomato onion garlic oil_olive thyme salt pepper | DSO DLI DUN WSH WLF GRS | TRE PLM COR DIC PLA MIN PFR SAU SIM PLT | 1/1 | fry 180 C in batches; simmer 40 min | dicing many vegetable types | 60 | 4 |
| FR03 | Chicken in red wine / Coq au vin | FR | 1 | - | chicken_thigh bacon mushroom onion carrot wine_red stock flour_wheat butter dried_herbs salt pepper | DSO DPO DLI DUN DBL DME WSH WLF GRS | PLA PLP DIC TRE SEA SER SAU DGL BRS THK PLT | 1/1 | sear 220 C; braise 160 C 60-75 min | none hard | 90 | 4 |
| FR04 | Beef in red wine / Boeuf bourguignon | FR | 1 | - | beef_cubes bacon onion carrot mushroom wine_red stock tomato_paste flour_wheat butter dried_herbs salt pepper | DSO DPO DLI DVI DUN DBL DME WSH WLF GRS | PLA PLP DIC TRE TRM SER SAU DGL BRS THK PLT | 1/1 | braise 160 C 2-2.5 h | trimming | 170 | 5 |
| FR05 | Tarte flambée / Flammkuchen | FR | 2 | 66 | flour_wheat yeast water salt oil_veg sourcream bacon onion nutmeg pepper | DSO DPO DLI DVI DUN DBL DME GRS GRF | KND RES ROL SPR PLA SLI DIC TOP BKE SLB PRT PLT | 1/1 | dough rest 60 min; roll 2-3 mm; oven 250-280 C 6-8 min | rolling paper-thin dough and transfer to oven | 90 | 4 |
| FR06 | Croque monsieur / Croque Monsieur | FR | 1 | - | toastbread ham cheese_semi butter flour_wheat milk nutmeg | DPO DLI DUN DBL DME GRF | MLT MXD DLI STC SPR LAY GRC ASM GRL PLT | 2/2 | béchamel 10 min; grill 250 C 8 min | assembling and gratinating | 25 | 4 |
| FR07 | Fish soup / Fischsuppe, Bouillabaisse | FR | 1 | - | whitefish salmon shrimp fennel tomato_can onion garlic oil_olive stock wine_white spice_curry salt pepper parsley | DSO DPO DLI DVI DUN DME WSH WLF GRS | PLA FLT DBN DIC TRE SLI SAU DGL SIM SLM PUR GAR PLT | 1/1 | broth 20 min; fish 5 min | fragile fish pieces | 40 | 5 |

### 3.9 Mediterranean and Middle Eastern (10)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| ME01 | Paella / Paella | ME | 2 | 85 | rice_round chicken_thigh shrimp bellpepper peas_fz onion garlic tomato spice_curry stock oil_olive lemon salt | DSO DPO DLI DUN DME WSH | PLA DIC COR PLQ SEA SER SAU DGL ABS RES PLT | 1/1 | sear 220 C; rice 100-110 C 18 min uncovered without stirring in wide pan (40 cm for 6) | wide shallow pan with even heat; bone-in chicken | 50 | 5 |
| ME02 | Moussaka / Moussaka | ME | 2 | 53 | eggplant lamb potato tomato_can onion garlic butter flour_wheat milk nutmeg cheese_semi oil_olive dried_herbs salt pepper | DSO DPO DLI DVI DUN DBL DME WSH GRS GRF | TRE SLI PLP SLI PFR PLA DIC SER SAU SIM MLT MXD STC LAY LAY TOP BKE RES SLB PRT PLT | 3/4 | aubergine 180 C 3 min per side; ragout 30 min; béchamel; bake 180 C 45 min | frying many slices; layering; clean cutting after baking | 130 | 4 |
| ME03 | Gyros in pita with tzatziki / Gyros mit Tzatziki, Fladenbrot | ME | 2 | 67 | pork_strips onion buns yoghurt cucumber garlic tomato oil_olive dried_herbs salt pepper lettuce | DSO DPO DLI DVI DUN DME WSH WLF GRS | MAR PLA SLI PFR PLS GRC SQZ MIN MXW TST SLI SLI ASM PLT | 2/3 | marinate 4-12 h; pan 220 C 8 min in batches; pita 150 C | assembling pita; crisp meat in batches | 30 | 4 |
| ME04 | Souvlaki, kebab skewers / Souvlaki, Schaschlik | ME | 1 | - | pork_cutlet bellpepper onion oil_olive dried_herbs paprika_pw salt pepper | DSO DPO DLI DUN DME WSH GRS | DIC COR WED PLA MAR SKW GRL FLP RES PLT | 1/1 | grill 250 C 10-12 min; turn | threading skewers, turning them | 30 | 4 |
| ME05 | Falafel / Falafel | ME | 1 | - | chickpeas_dry onion garlic parsley coriander spice_curry flour_wheat bakingpowder oil_veg salt | DSO DPO DLI DUN WLF | SOK RNS PLA MIN STR CHH GRM PUR MXD FRM DFR DRN PLT | 1/2 | soak 12-24 h; deep-fry 170 C 4 min | forming crumbly balls; deep-frying | 50 | 4 |
| ME06 | Hummus / Hummus | ME | 2 | - | chickpeas_can tahini garlic lemon oil_olive salt spice_curry water | DSO DPO DLI DVI DUN WSH | PLA MIN JUI RNS PUR MXW GAR PLT | 0/1 | cold blend 3 min | peeling garlic | 10 | 4 |
| ME07 | Garlic shrimp / Gambas al ajillo, Knoblauchgarnelen | ME | 2 | 56 | shrimp garlic chili oil_olive parsley lemon salt bread | DSO DLI DUN WSH WLF | PLA SLI CHH SAU PFR SLB PLT | 1/1 | oil 130 C garlic 1 min; shrimp 3 min | peeling garlic | 15 | 4 |
| ME08 | Spanish potato omelette / Tortilla española | ME | 1 | - | potato onion egg oil_olive salt | DSO DLI DUN WSH | PLP SLI PLA SLI PFR CRK WHK MXW PFR FLP SLB PLT | 1/2 | potatoes poach in oil 140 C 15 min; tortilla 3 min + flip + 3 min | flipping a 24 cm omelette (D5) | 35 | 4 |
| ME09 | Köfte / Köfte, Hackbällchen | ME | 1 | - | mince_beef onion garlic parsley spice_curry breadcrumbs egg salt pepper oil_veg yoghurt | DSO DPO DLI DVI DUN DME WLF GRS | PLA DIC MIN CHH KNM FRB GRL FLP PLT | 1/1 | pan or grill 200 C 5 min per side | forming and flipping | 30 | 4 |
| ME10 | Roast leg of lamb / Lammkeule | ME | 1 | - | lamb garlic thyme oil_olive wine_red stock salt pepper potato | DSO DPO DLI DUN DME WSH WLF GRS | PLA MIN SEA SCO RST BST RES CAR DGL RED SCE PLT | 1/1 | oven 160 C 90-120 min, core 60-65 C | carving bone-in leg | 150 | 4 |

### 3.10 Fish (7)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| FI01 | Fish fingers with mashed potato and spinach / Fischstäbchen | DE | 3 | 95 | fishsticks potato butter milk spinach_fz cream nutmeg oil_veg salt water | DSO DLI DUN DBL WSH GRF | PFR FLP PLP WED BOL DRN MSH MXW SIM THK PLT | 3/3 | fry 160 C 4 min per side or oven 220 C 15 min | frozen pre-breaded product | 30 | 4 |
| FI02 | Breaded or battered fried fish / Backfisch | DE | 2 | - | whitefish flour_wheat egg breadcrumbs lemon oil_veg salt pepper | DSO DPO DLI DUN DME WSH GRS | SEA BRD DFR FLP DRN GAR PLT | 1/2 | fry 175 C 4-5 min; fragile fillet | breading fragile fillets | 30 | 4 |
| FI03 | Pan-fried or baked salmon fillet / Lachsfilet | INT | 3 | - | salmon lemon butter dill salt pepper oil_olive | DSO DLI DUN DBL DME WSH WLF GRS | SEA PFR FLP BST PLT | 1/1 | pan 180 C, skin down 4 min, flip 2 min; or oven 180 C 15 min | turning fragile fillet | 15 | 4 |
| FI04 | Trout meunière / Forelle Müllerin | DE | 1 | - | trout flour_wheat butter lemon parsley salt pepper | DSO DPO DUN DBL DME WSH WLF GRS | SEA TOS PFR FLP BST GAR PLT | 1/1 | pan 170 C 5 min per side | flipping whole fish; no deboning done by machine | 20 | 4 |
| FI05 | Herring with apples and onions / Matjes Hausfrauenart | DE | 2 | - | herring apple onion pickles sourcream yoghurt vinegar sugar salt pepper dill | DSO DLI DVI DUN DME WSH WLF GRS | PLA SLI PLS COR SLI SLI MXW MAR CHL PLT | 0/1 | cold; 4-12 h | slippery fillet handling | 20 | 4 |
| FI06 | Fish fillet in mustard-dill sauce / Seelachs in Senf-Dill-Soße | DE | 2 | - | whitefish mustard dill cream butter flour_wheat stock lemon rice_long salt pepper | DSO DPO DLI DVI DUN DBL DME WSH WLF GRS | MLT THK SIM SEA SIM CHH ABS PLT | 2/2 | fillet poach 90 C 8 min; sauce 8 min | fragile fillet | 25 | 3 |
| FI07 | Baked whole sea bream / Dorade aus dem Ofen | ME | 1 | - | trout lemon dill oil_olive garlic salt pepper potato | DSO DLI DUN DME WSH WLF GRS | PLA MIN STU SEA RST FLT PLT | 1/1 | oven 200 C 25-30 min; core 65 C | filleting a cooked whole fish for plating (D5) | 40 | 5 |

### 3.11 Asian (12)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| AS01 | Fried rice / Gebratener Reis | AS | 2 | 22 | rice_long egg carrot peas_fz onion soysauce oil_veg springonion salt pepper | DSO DLI DUN WSH WLF GRS | RNS ABS COL PLP DIC PLA DIC CRK STW SEA GAR PLT | 2/2 | rice cooked and cooled; wok 250 C 6-8 min | wok tossing at high heat | 40 | 4 |
| AS02 | Fried noodles / Bami Goreng, Chow Mein | AS | 2 | 44 | noodles_asian chicken_breast whitecab carrot springonion soysauce oil_veg garlic chilipaste egg water | DSO DLI DVI DUN DME WSH WLF | PLP JUL PLA MIN TRE SLI SLM BOL DRN STW CRK STW PLT | 2/2 | noodles 4 min; wok 250 C 8 min | wok tossing; many small cuts | 30 | 4 |
| AS03 | Thai red curry with chicken / Rotes Thai-Curry | AS | 3 | 15 | chicken_breast coconutmilk chilipaste bellpepper zucchini rice_long onion garlic ginger oil_veg lemon salt sugar | DSO DLI DVI DUN DME WSH | PLA MIN PLH SLM COR JUL SAU SIM RNS ABS PLT | 2/2 | paste fry 1 min, simmer 15 min; rice 15 min | none hard | 40 | 4 |
| AS04 | Pad Thai / Pad Thai | AS | 1 | - | noodles_asian egg tofu beansprouts nuts lemon soysauce sugar oil_veg springonion garlic chilipaste | DSO DLI DVI DUN DBL WSH WLF | PLA SOK DIC MIN CRH CRK STW JUI TOS GAR PLT | 1/2 | wok 250 C 6 min | wok tossing | 25 | 4 |
| AS05 | Sushi rolls / Sushi, Maki | AS | 1 | 24 | rice_round nori salmon cucumber avocado vinegar sugar salt soysauce | DSO DLI DUN DME WSH | RNS ABS MXW COL SLM JUL PLS PIT SLI ASM WRP SLB PLT | 1/2 | rice 15 min; roll and cut 8 pieces | rolling with mat and clean cutting of sticky roll (D5) | 60 | 4 |
| AS06 | Ramen / Ramen | AS | 1 | - | noodles_asian stock egg miso springonion soysauce pork_strips nori water seeds | DSO DPO DLI DVI DUN DME WLF | BOL COL PLE SLM SEA SER SIM BOL DRN SLI ASM PLT | 2/3 | broth 90 C 20 min; noodles 3 min; egg 6.5 min | peeling soft-boiled egg; assembling bowl | 40 | 4 |
| AS07 | Sweet and sour chicken / Süß-saures Hähnchen | AS | 2 | - | chicken_breast bellpepper onion pineapple_can ketchup vinegar sugar cornstarch soysauce oil_veg rice_long egg | DSO DPO DLI DVI DUN DME WSH | PLA COR DIC SLM BAT DFR DRN SIM THK STW ABS PLT | 3/3 | fry 180 C 4 min; sauce 5 min; rice 15 min | batter, deep fry, sauce sequence | 40 | 4 |
| AS08 | Spring rolls / Frühlingsrollen | AS | 1 | - | wrapper whitecab carrot beansprouts mince_mixed springonion soysauce oil_veg garlic | DLI DUN DME WSH WLF | PLP JUL SLI PLA MIN SAU WRP DFR DRN PLT | 2/2 | filling 6 min; fry 175 C 4 min | folding and rolling wrappers (D5) | 50 | 4 |
| AS09 | Gyoza, dumplings / Gyoza | AS | 1 | - | wrapper mince_mixed whitecab springonion garlic ginger soysauce oil_veg seeds | DSO DLI DUN DME WSH WLF | PLA MIN GRC KNM STU PFR STM PLT | 1/1 | fry 170 C 2 min then steam 4 min | pleating dumplings (D5) | 40 | 4 |
| AS10 | Teriyaki chicken with rice / Teriyaki-Hähnchen | AS | 2 | - | chicken_thigh soysauce sugar ginger garlic oil_veg rice_long seeds springonion | DSO DLI DUN DME WLF | PLA MIN SLM MAR PFR FLP RED ABS GAR PLT | 2/2 | pan 200 C 6 min; sauce reduce 4 min | flipping; reducing sauce | 30 | 4 |
| AS11 | Wok vegetables with tofu or chicken / Asia-Gemüsepfanne | AS | 3 | 40 | tofu asianveg carrot bellpepper mushroom springonion garlic ginger soysauce oil_veg rice_long cornstarch | DSO DPO DLI DUN DBL WSH WLF | PLA MIN PLP JUL COR SLI TRE SLI DIC STW ABS PLT | 2/2 | wok 250 C 6 min | wok tossing | 25 | 4 |
| AS12 | Vegetable coconut curry / Gemüse-Curry | AS | 2 | - | potato carrot cauli bellpepper coconutmilk chilipaste onion garlic ginger spice_curry rice_long oil_veg peas_fz | DSO DPO DLI DVI DUN WSH | PLP PLP STR COR DIC PLA MIN SAU SIM ABS PLT | 2/2 | simmer 25 min; rice 15 min | cutting several vegetables | 40 | 4 |

### 3.12 Indian (8)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| IN01 | Butter chicken, tikka masala / Chicken Tikka Masala | IN | 3 | 55 | chicken_thigh yoghurt spice_curry tomato_can cream butter onion garlic ginger chilipaste rice_long salt oil_veg | DSO DPO DLI DVI DUN DBL DME | MAR PLA DIC MIN SLM GRL SAU PUR SIM THK ABS PLT | 2/2 | marinate 4-12 h; grill 250 C 10 min; sauce 20 min; rice 15 min | marinate hold; blending hot sauce | 50 | 4 |
| IN02 | Dal / Dal, Linsen-Curry | IN | 2 | - | lentils onion tomato garlic ginger spice_curry fat_solid coconutmilk salt water rice_long | DSO DPO DLI DVI DUN DBL WSH | RNS PLA DIC MIN SIM SAU TOP ABS PLT | 2/2 | lentils 30 min; tarka 180 C 1 min | tarka spice timing | 45 | 4 |
| IN03 | Chana masala / Chana Masala | IN | 2 | - | chickpeas_can tomato_can onion garlic ginger spice_curry oil_veg salt rice_long | DSO DPO DLI DVI DUN | PLA DIC MIN RNS SAU SIM ABS PLT | 2/2 | simmer 25 min | none hard | 35 | 4 |
| IN04 | Palak paneer / Palak Paneer | IN | 1 | - | spinach paneer cream onion garlic ginger spice_curry oil_veg salt rice_long | DSO DPO DLI DUN DBL WLF | PLA STR BLA DIC MIN DIC PFR SAU PUR SIM ABS PLT | 2/2 | paneer fry 180 C 4 min; sauce 12 min | fragile paneer | 35 | 4 |
| IN05 | Biryani / Biryani | IN | 1 | - | rice_long chicken_thigh yoghurt onion spice_curry spice_whole oil_veg fat_solid stock salt | DSO DPO DLI DVI DUN DBL DME | MAR PLA SLI DFR RNS BOL DRN LAY BKE PLT | 2/2 | onions fry 160 C 15 min; rice 70 % boil 6 min; dum bake 180 C 30 min | layering and dum-sealing | 90 | 4 |
| IN06 | Naan bread / Naan | IN | 1 | - | flour_wheat yeast yoghurt water salt sugar oil_veg butter | DSO DPO DLI DVI DBL | KND PRF CUD ROL PFR FLP GLZ PLT | 1/1 | dough proof 60 min; pan 250 C 1-2 min per side | rolling and flipping puffy bread | 100 | 4 |
| IN07 | Samosa / Samosa | IN | 1 | - | flour_wheat potato peas_fz onion spice_curry oil_veg salt water | DSO DPO DLI DUN WSH | KND RES PLP DIC BOL PLA SAU ROL CUD STU WRP DFR DRN PLT | 2/3 | filling 15 min; fry 170 C 5 min | folding filled pastry triangles | 80 | 4 |
| IN08 | Potato-cauliflower curry / Aloo Gobi | IN | 1 | - | potato cauli tomato onion garlic ginger spice_curry oil_veg salt coriander | DSO DPO DLI DUN WSH WLF | PLP STR DIC PLA MIN SAU SIM PLT | 1/1 | simmer 25 min | none hard | 40 | 4 |

### 3.13 Mexican and Tex-Mex (7)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| MX01 | Chili con carne / Chili con Carne | MX | 3 | 28 | mince_beef beans_can corn_can tomato_can onion bellpepper chili garlic spice_curry tomato_paste stock salt oil_veg rice_long | DSO DPO DLI DVI DUN DME WSH | PLA DIC COR DIC MIN SER SAU SIM ABS PLT | 2/2 | sear 220 C; simmer 45-60 min; rice 15 min | none hard | 70 | 4 |
| MX02 | Tacos / Tacos | MX | 2 | 89 | tortilla mince_beef spice_curry lettuce tomato cheese_semi sourcream onion tomato_can salt oil_veg avocado | DSO DPO DLI DVI DUN DBL DME WSH WLF | PLA DIC SER SAU SIM STR SLI GRC ASM PLT | 1/2 | meat 12 min; shells warm 3 min | filling fragile taco shells | 25 | 4 |
| MX03 | Burritos / Burritos | MX | 2 | - | tortilla rice_long beans_can mince_beef cheese_semi tomato_can bellpepper onion spice_curry sourcream | DSO DPO DVI DUN DBL DME WSH | PLA DIC COR ABS SER SAU SIM GRC ASM WRP TST PLT | 2/3 | filling 20 min; tortilla 30 s each | folding burritos (D4-5) | 35 | 4 |
| MX04 | Quesadillas / Quesadillas | MX | 2 | - | tortilla cheese_grated bellpepper chicken_breast onion oil_veg sourcream | DSO DLI DVI DUN DME WSH | PLA COR JUL SAU ASM PFR FLP SLB PLT | 1/2 | pan 160 C 2 min per side | flipping loaded tortilla | 20 | 4 |
| MX05 | Fajitas / Fajitas | MX | 2 | - | chicken_breast bellpepper onion tortilla spice_curry lemon oil_veg sourcream avocado | DPO DLI DVI DUN DME WSH | PLA COR JUL SLM MAR STW WRP ASM PLT | 1/2 | wok/pan 250 C 6 min | tossing; wrapping at table | 25 | 4 |
| MX06 | Guacamole / Guacamole | MX | 2 | - | avocado tomato onion lemon coriander chili salt | DSO DUN WSH WLF | PLA COR PLS PIT MSH DIC CHH JUI MXW PLT | 0/1 | cold | halving, pitting and scooping soft avocado | 10 | 4 |
| MX07 | Enchiladas / Enchiladas | MX | 1 | - | tortilla chicken_breast tomato_can cheese_grated onion bellpepper spice_curry sourcream oil_veg | DSO DPO DLI DVI DUN DME WSH | PLA DIC SIM SHR SAU STU WRP LAY TOP BKE PLT | 2/2 | sauce 15 min; bake 200 C 20 min | filling and rolling tortillas | 50 | 4 |

### 3.14 American (8)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| US01 | Hamburger, cheeseburger / Hamburger | US | 3 | 31 | mince_beef buns cheese_semi lettuce tomato onion pickles ketchup mustard salt pepper oil_veg | DSO DLI DVI DUN DBL DME WSH WLF GRS | PLA SEA FRB PFR FLP TST SLI SLI SLI ASM PLT | 2/2 | patty 200 C 3-4 min per side, core 72 C; bun 150 C | forming patties; stacking a burger | 25 | 4 |
| US02 | Hot dog / Hot Dog | US | 2 | - | sausage_cooked buns mustard ketchup onion pickles | DVI DUN DME | SIM TST PLA DIC ASM PLT | 1/1 | sausage 80 C 6 min | assembly in soft bun | 10 | 4 |
| US03 | Macaroni and cheese / Mac and Cheese | US | 2 | - | pasta_dry cheese_semi milk butter flour_wheat mustard nutmeg salt breadcrumbs water | DSO DPO DLI DVI DUN DBL GRF | BOL DRN MLT MXD DLI STC GRC TOS TOP BKE PLT | 2/2 | sauce 10 min; pasta 9 min; optional bake 200 C 15 min | none hard | 30 | 3 |
| US04 | BBQ spare ribs / Spareribs | US | 1 | - | ribs ketchup honey vinegar spice_curry paprika_pw soysauce salt pepper | DSO DPO DLI DVI DME GRS | TRM SEA RST GLZ GRL CAR PLT | 1/1 | oven 150 C 2.5-3 h; glaze 250 C 5 min | removing membrane; carving bones | 190 | 5 |
| US05 | Fried chicken / Fried Chicken | US | 1 | - | chicken_thigh milk flour_wheat spice_curry paprika_pw salt oil_veg | DSO DPO DLI DME | MAR BRD DFR DRN KWM PLT | 1/2 | marinate 4-12 h; fry 170 C 12-15 min in 2 L oil | breading bone-in pieces | 40 | 4 |
| US06 | Pulled pork / Pulled Pork | US | 1 | - | pork_roast paprika_pw spice_curry ketchup vinegar honey buns lettuce mayo salt | DSO DPO DLI DVI DUN DME WLF | SEA MAR RST SHR TOS ASM PLT | 1/1 | oven 130 C 6-8 h; core 95 C | 8 h occupancy; shredding | 480 | 4 |
| US07 | Toasted cheese sandwich / Toast Hawaii, Grilled Cheese | US | 3 | - | toastbread cheese_semi ham butter pineapple_can | DVI DUN DBL DME | SPR LAY ASM CNT GRL SLB PLT | 1/1 | pan 150 C 3 min per side or grill 250 C 5 min | flipping loaded toast | 10 | 4 |
| US08 | Cold sandwich or wrap / Belegtes Sandwich, Wrap | US | 2 | - | bread ham cheese_semi lettuce tomato cucumber mayo mustard butter | DVI DUN DBL DME WSH WLF | SLB SPR SLI SLI ASM SLB PLT | 0/0 | cold | stacking soft ingredients | 10 | 4 |

### 3.15 Vegetarian mains (5)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| VG01 | Vegetable pan with feta / Gemüsepfanne mit Schafskäse | DE | 3 | 40 | zucchini bellpepper eggplant onion tomato feta oil_olive dried_herbs salt pepper garlic rice_long | DSO DPO DLI DUN DBL WSH GRS | PLA TRE COR DIC MIN DIC SAU STW DIC TOP ABS PLT | 2/2 | pan 180 C 15 min | dicing mixed vegetables | 30 | 4 |
| VG02 | Spinach with egg and potatoes / Spinat mit Spiegelei und Kartoffeln | DE | 3 | - | spinach_fz cream egg potato butter nutmeg onion salt water | DSO DLI DUN DBL WSH GRF | PLP BOL DRN PLA DIC SAU SIM CRK PFR PLT | 3/3 | potatoes 20 min; spinach 12 min; egg 3 min | peeling potatoes; egg | 35 | 4 |
| VG03 | Mushroom cream ragout with pasta / Champignon-Rahm-Nudeln | DE | 2 | - | mushroom onion cream butter pasta_dry parsley wine_white salt pepper water | DSO DLI DUN DBL WLF GRS | TRE SLI PLA DIC SAU DGL RED BOL DRN TOS CHH PLT | 2/2 | mushroom 200 C 8 min; pasta 10 min | mushroom trimming | 25 | 4 |
| VG04 | Stuffed zucchini / Gefüllte Zucchini | DE | 1 | - | zucchini feta tomato onion breadcrumbs cheese_semi oil_olive salt pepper garlic | DSO DLI DUN DBL WSH GRS | PLA MIN WED COR DIC SAU STU TOP BKE PLT | 1/1 | bake 200 C 30 min | hollowing zucchini | 50 | 4 |
| VG05 | Rice pan with vegetables / Reispfanne mit Gemüse | DE | 2 | 22 | rice_long bellpepper veg_fz onion egg oil_veg stock salt pepper | DSO DPO DLI DUN WSH GRS | PLA DIC COR SAU RNS ABS CRK STC PLT | 1/1 | rice 15 min; pan 12 min | none hard | 30 | 4 |

### 3.16 Casseroles (Aufläufe) (6)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| CS01 | Vegetable casserole / Gemüseauflauf | DE | 3 | 12 | zucchini bellpepper carrot potato cheese_semi cream egg milk onion dried_herbs salt pepper | DSO DPO DLI DUN DBL WSH GRS | PLP TRE COR DIC PLA SLI BLA LIN LAY GRC TOP BKE PLT | 1/1 | bake 200 C 35-40 min | cutting and layering many vegetables | 55 | 4 |
| CS02 | Pasta bake with ham and cheese / Nudelauflauf, Schinkennudeln | DE | 3 | 17,84 | pasta_dry ham cream egg cheese_semi milk butter salt pepper nutmeg water | DSO DLI DUN DBL DME GRS GRF | BOL DRN DIC MXW CRK WHK LIN LAY GRC TOP BKE PRT PLT | 2/2 | pasta 8 min; bake 200 C 30 min | none hard | 50 | 3 |
| CS03 | Potato gratin / Kartoffelgratin | DE | 3 | 37 | potato cream milk garlic cheese_semi nutmeg butter salt pepper | DSO DLI DUN DBL WSH GRS GRF | PLP SLI PLA MIN LIN LAY TOP GRC BKE PRT PLT | 1/1 | bake 180 C 60 min | peeling; even 2-3 mm slicing | 70 | 4 |
| CS04 | Minced meat and potato bake / Hackfleisch-Kartoffel-Auflauf | DE | 2 | - | potato mince_mixed onion cream cheese_semi tomato_can egg salt pepper paprika_pw oil_veg | DSO DPO DLI DVI DUN DBL DME WSH GRS | PLP SLI PLA DIC SER SAU LIN LAY TOP GRC BKE PRT PLT | 1/1 | bake 200 C 60 min | peeling and slicing | 85 | 4 |
| CS05 | Bread pudding with apples / Ofenschlupfer | DE | 1 | - | bread apple milk egg sugar cinnamon butter raisins vanilla | DSO DPO DLI DUN DBL WSH | SLB PLS COR SLI CRK WHK MXW LAY BKE PRT PLT | 1/1 | bake 180 C 40 min | apple peeling | 55 | 4 |
| CS06 | Layered cabbage bake / Schichtkohl | DE | 2 | - | savoy mince_mixed onion potato stock cream salt pepper paprika_pw oil_veg | DSO DPO DLI DUN DME WSH GRS | COR SLI PLA DIC SER SAU LAY SIM PLT | 1/1 | braise 45 min in pot | coring and shredding cabbage | 60 | 4 |

### 3.17 Bread and yeast bakes (6)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| BK01 | Yeast bread, mixed wheat-rye / Mischbrot, Hefebrot | DE | 3 | - | flour_wheat flour_other yeast water salt | DSO DPO DLI DBL | MXD KND PRF SHD PRF SCO BKE COL SLB PLT | 1/1 | knead 10-12 min; proof 60+45 min at 30 C; bake 240 C 10 min then 200 C 40 min with steam | shaping the loaf, scoring, dough transfer | 180 | 4 |
| BK02 | Sourdough bread / Sauerteigbrot | DE | 2 | - | flour_wheat flour_other sourdough water salt | DSO DPO DLI DVI | MXD KND PRF SHD PRF SCO BKE COL SLB PLT | 1/1 | knead 10 min; fermentation 8-16 h; bake 240 C 40 min | starter feeding; shaping; long proof occupancy | 900 | 4 |
| BK03 | Bread rolls / Brötchen | DE | 2 | - | flour_wheat yeast water salt butter sugar | DSO DPO DLI DBL | MXD KND PRF CUD FRM PRF SCO BKE COL PLT | 1/1 | proof 60 min; bake 220 C 20 min with steam | portioning and rounding 8 rolls, scoring | 130 | 4 |
| BK04 | Sweet braided yeast bread / Hefezopf | DE | 2 | - | flour_wheat milk butter egg sugar yeast raisins vanilla | DSO DPO DLI DUN DBL | MXD KND PRF CUD FRM SHD GLZ BKE COL SLB PLT | 1/1 | proof 2 x 45 min; bake 180 C 35 min | braiding three strands (D5) | 160 | 4 |
| BK05 | Focaccia / Focaccia | IT | 1 | - | flour_wheat yeast water salt oil_olive thyme | DSO DPO DLI DUN DBL WLF | MXD KND PRF LIN SHD TOP BKE SLB PLT | 1/1 | proof 60 min; bake 230 C 20 min | dimpling and stretching dough into tray | 110 | 4 |
| BK06 | Pretzels / Laugenbrezeln | DE | 1 | - | flour_wheat yeast water salt butter | DSO DPO DLI DBL | MXD KND PRF CUD FRM SHD BOL SCO TOP BKE PLT | 2/2 | lye bath 4 % NaOH 20 s (hazard); bake 220 C 15 min | tying the pretzel knot (D5); food-grade lye handling | 150 | 4 |

### 3.18 Cakes, tarts and cookies (17)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| CK01 | Marble cake, pound cake / Rührkuchen, Marmorkuchen, Gugelhupf | DE | 3 | - | butter sugar egg flour_wheat bakingpowder milk vanilla cocoa | DSO DPO DLI DUN DBL | LIN CRM CRK WHK MXD SFT MXW LIN BKE COL UNM SLB GAR PLT | 1/1 | tin greased; bake 175 C 60 min; cool 20 min | greasing tin and unmoulding; doneness test | 100 | 4 |
| CK02 | Cheesecake / Käsekuchen | DE | 3 | 50 | quark egg sugar butter flour_wheat semolina pudding_powder lemon milk vanilla | DSO DPO DLI DVI DUN DBL WSH | RUB KND RES ROL LIN SEP CRM WHK WHP FLD LIN BKE COL UNM SLB PRT PLT | 1/1 | dough 30 min rest; bake 170-180 C 60-70 min; cool in oven | rolling dough into tin; folding egg white; unmoulding | 150 | 4 |
| CK03 | Apple cake / Apfelkuchen | DE | 3 | 74 | apple flour_wheat butter egg sugar cinnamon bakingpowder lemon milk | DSO DPO DLI DUN DBL WSH | PLS COR SLI CRM CRK MXD MXW LIN LAY BKE COL UNM SLB PLT | 1/1 | bake 175 C 50 min | peeling coring and slicing apples | 90 | 4 |
| CK04 | Streusel or sheet cake with yeast dough / Streuselkuchen, Blechkuchen | DE | 2 | - | flour_wheat yeast milk butter sugar egg vanilla cinnamon | DSO DPO DLI DUN DBL | KND PRF ROL LIN RUB TOP BKE COL SLB PRT PLT | 1/1 | proof 45 min; bake 180 C 30 min | rolling to tray size, streusel spreading | 120 | 3 |
| CK05 | Strawberry sponge cake / Erdbeerkuchen, Obstkuchen mit Tortenguss | DE | 3 | 35,47 | egg sugar flour_wheat cornstarch strawberry pudding_powder quark cream vanilla juice | DSO DPO DLI DVI DUN WLF | SEP WHK WHP FLD LIN BKE UNM TRE SLI LAY SIM THK GLZ CHL SLB PLT | 1/1 | sponge 175 C 25 min; glaze 1 min boil; chill 2 h | egg separation, folding, unmoulding fragile sponge, fruit arrangement | 120 | 4 |
| CK06 | Flourless chocolate cake / Schokokuchen | DE | 2 | 61 | chocolate butter egg sugar nuts cocoa | DSO DPO DUN DBL | MLT BMA SEP WHK WHP FLD LIN BKE COL UNM GAR SLB PLT | 2/2 | melt 45 C; bake 170 C 25-30 min | egg white folding; fragile unmoulding | 60 | 4 |
| CK07 | Muffins, cupcakes / Muffins, Cupcakes | INT | 3 | 58,82 | flour_wheat sugar egg milk oil_veg bakingpowder berries vanilla butter | DSO DPO DLI DUN DBL | MXD MXW CRK WHK FLD LIN BKE COL UNM PIP PLT | 1/1 | bake 180 C 22 min | filling 12 cups; unmoulding | 45 | 4 |
| CK08 | Black Forest cake / Schwarzwälder Kirschtorte | DE | 1 | 90 | egg sugar flour_wheat cocoa stonefruit cream chocolate spirits cornstarch | DSO DPO DLI DUN DBL WSH | SEP WHK WHP FLD LIN BKE UNM SLB SIM THK WHP SPR LAY PIP CRH GAR CHL SLB PLT | 1/2 | sponge 175 C 30 min; chill 3 h | horizontal slicing of sponge and decorating (D5) | 180 | 4 |
| CK09 | Christmas cookies / Plätzchen, Ausstecherle | DE | 2 | - | flour_wheat butter sugar egg vanilla salt | DSO DPO DUN DBL | SFT RUB KND RES ROL CUD LIN GLZ BKE COL PLT | 1/1 | dough rest 60 min at 4 C; roll 3 mm; bake 180 C 10 min in batches | cutting shapes and lifting them onto trays | 150 | 3 |
| CK10 | Brownies / Brownies | US | 2 | - | chocolate butter egg sugar flour_wheat cocoa nuts | DSO DPO DUN DBL | MLT MXW CRK WHK MXD FLD CRH LIN BKE COL SLB PRT PLT | 1/1 | bake 175 C 25 min | clean cutting of fudgy bake | 50 | 3 |
| CK11 | Yeast doughnuts / Berliner, Krapfen | DE | 1 | - | flour_wheat milk butter egg sugar yeast jam oil_veg | DSO DPO DLI DVI DUN DBL | KND PRF ROL CUD PRF DFR FLP PIP DPO GAR PLT | 1/2 | proof 2 x 30 min; fry 170 C 2.5 min per side in 2 L oil | flipping in oil; filling | 120 | 4 |
| CK12 | Apple strudel / Apfelstrudel | DE | 1 | - | flour_wheat oil_veg egg apple raisins sugar cinnamon breadcrumbs butter nuts | DSO DPO DLI DUN DBL WSH | KND RES ROL PLS COR SLI SAU STU WRP GLZ BKE SLB PLT | 1/1 | dough rest 30 min; stretch to 0.5 mm; bake 190 C 40 min | stretching and rolling strudel (D5) | 100 | 4 |
| CK13 | Sponge roll / Biskuitrolle | DE | 1 | - | egg sugar flour_wheat jam cream | DSO DPO DLI DVI DUN | SEP WHK WHP FLD LIN BKE WRP SPR WRP SLB PLT | 1/1 | bake 200 C 10 min; roll while hot | rolling hot sponge without cracking (D5) | 50 | 4 |
| CK14 | Chocolate chip cookies / Cookies | US | 2 | - | flour_wheat butter sugar egg chocolate bakingpowder vanilla salt | DSO DPO DUN DBL | SFT CRM CRK MXD CRH MXW LIN BKE COL PLT | 1/1 | bake 180 C 10-12 min in batches | portioning dough balls | 40 | 3 |
| CK15 | Rhubarb sheet cake / Rhabarberkuchen | DE | 2 | - | rhubarb flour_wheat butter egg sugar bakingpowder milk vanilla | DSO DPO DLI DUN DBL WSH | TRE PLS SLI CRM CRK MXD MXW LIN LAY BKE COL SLB PRT PLT | 1/1 | bake 180 C 40 min | stringy rhubarb peeling | 70 | 4 |
| CK16 | Banana bread / Bananenbrot | US | 1 | - | banana flour_wheat butter egg sugar bakingpowder nuts cinnamon | DSO DPO DUN DBL | PLS MSH CRM CRK MXD MXW LIN BKE COL UNM SLB PLT | 1/1 | bake 175 C 55 min | none hard | 75 | 4 |
| CK17 | Apple turnovers with puff pastry / Apfeltaschen | DE | 2 | - | pastry_dough apple sugar cinnamon egg raisins | DSO DPO DUN WSH | PLS COR DIC SIM CUD STU GLZ BKE COL PLT | 2/2 | filling 10 min; bake 200 C 20 min | folding and sealing pastry squares | 45 | 4 |

### 3.19 Desserts (16)

| ID | Meal (EN / DE) | Reg | W | GU | Ingredients | Implicit ops | Ordered unit operations | H/B | Temperatures and times | Hardest step for a machine | min | D |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| DS01 | Rice pudding with cinnamon sugar / Milchreis, Apfelmilchreis | DE | 3 | 36 | rice_round milk sugar vanilla cinnamon salt apple butter | DSO DPO DLI DUN DBL WSH | STC SIM PLS COR SLI SAU TOP PRT PLT | 1/1 | milk 90 C, stir 35-40 min | long gentle stirring without scorching | 45 | 4 |
| DS02 | Semolina pudding / Grießbrei | DE | 2 | 71 | semolina milk sugar vanilla butter berries | DSO DPO DLI DBL | STC SIM PRT PLT | 1/1 | simmer 5 min stir | none | 10 | 3 |
| DS03 | Pudding from powder / Pudding, Schokopudding mit Karamellsoße | DE | 2 | 93 | pudding_powder milk sugar vanilla cocoa nuts | DSO DPO DLI | STC CRL CHL UNM PLT | 1/1 | boil 1 min stir; chill 2 h | caramelising sugar without burning | 30 | 4 |
| DS04 | Red berry compote / Rote Grütze | DE | 2 | - | berries juice sugar cornstarch vanilla | DSO DPO DLI | SIM THK CHL PLT | 1/1 | simmer 5 min; chill 3 h | none | 15 | 3 |
| DS05 | Shredded pancake / Kaiserschmarrn | DE | 2 | 43 | flour_wheat egg milk sugar raisins butter spirits salt | DSO DPO DLI DUN DBL | SEP WHK WHP FLD PFR FLP SHR CRL DPO PLT | 1/1 | pan 170 C 4 min per side, tear apart, caramelise 2 min | flipping heavy pancake, tearing | 30 | 4 |
| DS06 | Tiramisu / Tiramisu | IT | 2 | 69 | creamcheese egg sugar sponge_biscuit cocoa spirits cream vanilla | DSO DPO DLI DVI DUN | SEP WHK WHP FLD SOK LAY CHL DPO PLT | 0/2 | cold; chill 6 h | egg separation, folding, layering wet biscuits | 30 | 4 |
| DS07 | Chocolate mousse / Mousse au chocolat | FR | 2 | - | chocolate egg cream sugar | DSO DLI DUN DBL | MLT BMA SEP WHP FLD CHL PLT | 1/2 | melt 45 C; chill 3 h | folding stiff egg white | 30 | 4 |
| DS08 | Panna cotta / Panna cotta | IT | 1 | - | cream sugar gelatine vanilla berries | DSO DPO DLI DUN | SOK SIM MXW CHL UNM PLT | 1/1 | heat 80 C; set 4 h | unmoulding | 20 | 4 |
| DS09 | Crème brûlée / Crème brûlée | FR | 1 | - | cream egg sugar vanilla | DSO DPO DLI DUN | SEP WHK SIM BMA BKE CHL CRL PLT | 1/2 | bake 150 C 40 min in water bath; chill 4 h; torch | caramelise crust with torch | 70 | 4 |
| DS10 | Fruit salad / Obstsalat | INT | 2 | - | apple banana orange strawberry pear lemon berries sugar | DSO DUN WSH WLF | PLS COR PLS PLS TRE PIT DIC JUI TOS PLT | 0/1 | cold | peeling five kinds of fruit (D4 each) | 20 | 4 |
| DS11 | Yeast dumplings, steamed / Germknödel, Dampfnudeln | DE | 1 | 78 | flour_wheat milk butter egg sugar yeast jam cinnamon | DSO DPO DLI DVI DUN DBL | KND PRF FRK STU PRF STM DPO PLT | 1/1 | proof 60 min; steam 15 min | filling and closing dough balls | 120 | 4 |
| DS12 | Quark with fruit / Quarkspeise, Obstquark | DE | 2 | - | quark berries sugar lemon vanilla cream | DSO DPO DLI DVI DUN WSH | WHP MXW GAR PLT | 0/1 | cold | none | 5 | 3 |
| DS13 | Ice cream / Vanilleeis, Erdbeereis | INT | 1 | 65 | cream egg sugar vanilla strawberry creamcheese | DSO DPO DLI DVI DUN WLF | SEP WHK SIM WHP PUR FLD FRZ PRT PLT | 1/1 | custard 80 C; churn/freeze 3-6 h at -18 C | needs freezer module | 240 | 4 |
| DS14 | Apple crumble / Apple Crumble | INT | 2 | - | apple flour_wheat butter sugar oats cinnamon raisins | DSO DPO DUN DBL WSH | PLS COR SLI RUB LAY TOP BKE PRT PLT | 1/1 | bake 180 C 40 min | apple peeling | 55 | 4 |
| DS15 | Baked apple / Bratapfel | DE | 1 | - | apple raisins nuts marzipan cinnamon butter sugar | DSO DPO DUN DBL WSH | COR STU BKE PLT | 1/1 | bake 190 C 30 min | coring whole apple | 40 | 4 |
| DS16 | Sweet pancake with jam or compote / Pfannkuchen süß, Crêpes | FR | 3 | - | flour_wheat milk egg sugar butter jam | DSO DPO DLI DVI DUN DBL | SFT MXD CRK WHK RES PTH PFR FLP SPR WRP DPO PLT | 1/2 | as BF06 | flipping thin pancake; folding/rolling | 35 | 4 |

## 4. Statistics

### 4.1 Corpus composition

| Region | Meals | Share | Weighted share |
|---|---|---|---|
| German / Austrian / Swiss | 138 | 55.6 % | 59.7 % |
| Italian | 24 | 9.7 % | 9.5 % |
| French | 12 | 4.8 % | 3.6 % |
| Mediterranean / Middle East / Balkan | 16 | 6.5 % | 4.6 % |
| Asian | 13 | 5.2 % | 4.4 % |
| Indian | 8 | 3.2 % | 2.4 % |
| Mexican | 7 | 2.8 % | 2.8 % |
| American | 13 | 5.2 % | 4.8 % |
| International / generic | 17 | 6.9 % | 8.1 % |

| Category | Meals |
|---|---|
| Breakfast and brunch | 14 |
| German and Central European meat, poultry and sausage mains | 36 |
| Soups and stews | 20 |
| Side dishes | 28 |
| Basic sauces | 5 |
| Salads | 16 |
| Pasta and Italian | 20 |
| French | 7 |
| Mediterranean and Middle Eastern | 10 |
| Fish | 7 |
| Asian | 12 |
| Indian | 8 |
| Mexican and Tex-Mex | 7 |
| American | 8 |
| Vegetarian mains | 5 |
| Casseroles (Aufläufe) | 6 |
| Bread and yeast bakes | 6 |
| Cakes, tarts and cookies | 17 |
| Desserts | 16 |

Coverage of the Chefkoch Foodstudie categories (rows may appear in several categories):

| Foodstudie category (rank order) | Corpus rows |
|---|---|
| Pasta | 16 |
| Meat dishes | 34 |
| Salads | 16 |
| Rice dishes | 7 |
| Fish dishes | 8 |
| Vegetarian | 14 |
| Casseroles (Aufläufe) | 10 |
| Soups | 16 |
| Stews (Eintöpfe) | 7 |
| Desserts | 16 |
| Cakes / tarts / pastry | 18 |
| Warm breakfast | 10 |
| Pizza | 3 |
| Vegan | 37 rows vegan by ingredient list (no meat, fish, egg, dairy, honey), 137 rows vegetarian (no meat or fish); the remainder are adaptable with substitutes |
| Wok dishes | 7 |

### 4.2 Frequency of every unit operation

`n` = meals containing the operation, `%` = share of the corpus, `w%` = share of the weighted corpus. Sorted by frequency.

| Rank | Code | Operation | D | av | n | % | w% |
|---|---|---|---|---|---|---|---|
| 1 | DSO | dose free-flowing solids | 1 | 0 | 238 | 96.0 | 96.2 |
| 2 | DUN | dispense countable whole items | 3 | 0 | 231 | 93.1 | 93.5 |
| 3 | PLT | plate / arrange | 3 | 0 | 231 | 93.1 | 91.7 |
| 4 | DLI | dose thin liquids | 1 | 0 | 218 | 87.9 | 87.7 |
| 5 | DPO | dose powder / spice pinch | 2 | 0 | 158 | 63.7 | 61.7 |
| 6 | WSH | wash robust produce | 2 | 1 | 146 | 58.9 | 58.5 |
| 7 | PLA | peel alliums | 4 | 1 | 129 | 52.0 | 51.6 |
| 8 | DBL | portion block solids | 2 | 0 | 127 | 51.2 | 52.8 |
| 9 | GRS | grind spices / pepper | 1 | 0 | 108 | 43.5 | 46.6 |
| 10 | DME | dispense raw meat / fish pieces | 3 | 0 | 107 | 43.1 | 43.3 |
| 11 | DIC | dice / cube | 2 | 1 | 106 | 42.7 | 43.1 |
| 12 | DVI | dose viscous / sticky | 2 | 0 | 100 | 40.3 | 40.1 |
| 13 | WLF | wash delicate / leafy produce | 3 | 1 | 86 | 34.7 | 32.9 |
| 14 | SAU | saute / sweat | 2 | 0 | 84 | 33.9 | 35.1 |
| 15 | SIM | simmer / poach gently | 1 | 0 | 79 | 31.9 | 33.3 |
| 16 | SLI | slice (uniform) | 2 | 1 | 70 | 28.2 | 29.2 |
| 17 | PLP | peel potato / smooth roots | 3 | 1 | 60 | 24.2 | 25.6 |
| 18 | DRN | drain / strain | 2 | 0 | 56 | 22.6 | 24.2 |
| 19 | COR | core / deseed / hull | 4 | 1 | 50 | 20.2 | 20.6 |
| 20 | BOL | boil (rolling boil in water) | 1 | 0 | 47 | 19.0 | 20.2 |
| 21 | BKE | bake | 2 | 0 | 44 | 17.7 | 17.3 |
| 22 | PFR | pan-fry / shallow-fry | 2 | 0 | 43 | 17.3 | 17.9 |
| 23 | MXW | mix / stir cold or batter | 1 | 0 | 39 | 15.7 | 15.5 |
| 24 | GAR | garnish / dust / drizzle | 3 | 0 | 37 | 14.9 | 15.1 |
| 25 | CRK | crack egg into vessel | 3 | 1 | 36 | 14.5 | 16.1 |
| 26 | TOS | toss / coat in bowl | 2 | 0 | 36 | 14.5 | 15.1 |
| 27 | MIN | mince fine / crush | 2 | 1 | 35 | 14.1 | 13.7 |
| 28 | SLB | slice baked goods / portion cake, pizza | 2 | 0 | 33 | 13.3 | 13.1 |
| 29 | FLP | flip / turn item | 4 | 0 | 32 | 12.9 | 12.7 |
| 30 | WHK | whisk / beat liquids smooth | 2 | 0 | 32 | 12.9 | 13.5 |
| 31 | TRE | trim ends / stems / roots | 4 | 1 | 31 | 12.5 | 12.9 |
| 32 | GRF | grate fine / zest | 2 | 1 | 29 | 11.7 | 13.3 |
| 33 | SEA | season / salt / rub surface | 2 | 0 | 29 | 11.7 | 11.1 |
| 34 | THK | thicken | 2 | 0 | 29 | 11.7 | 12.5 |
| 35 | PRT | portion into servings | 3 | 0 | 28 | 11.3 | 12.9 |
| 36 | COL | cool down | 1 | 0 | 27 | 10.9 | 11.7 |
| 37 | RES | rest | 1 | 0 | 27 | 10.9 | 12.1 |
| 38 | CHH | chop herbs | 2 | 1 | 26 | 10.5 | 11.1 |
| 39 | PLS | peel soft / thin-skinned fruit & veg | 4 | 1 | 26 | 10.5 | 10.1 |
| 40 | MXD | mix dry ingredients | 1 | 0 | 25 | 10.1 | 10.7 |
| 41 | SER | sear / brown at high heat | 2 | 0 | 25 | 10.1 | 10.5 |
| 42 | DGL | deglaze | 2 | 0 | 24 | 9.7 | 9.5 |
| 43 | MLT | melt | 1 | 0 | 24 | 9.7 | 10.1 |
| 44 | TOP | sprinkle / top | 2 | 0 | 24 | 9.7 | 10.1 |
| 45 | ABS | cook by absorption | 1 | 0 | 23 | 9.3 | 10.1 |
| 46 | LAY | layer | 3 | 0 | 23 | 9.3 | 9.3 |
| 47 | GRC | grate / shred coarse | 2 | 1 | 22 | 8.9 | 9.3 |
| 48 | LIN | line / grease / prepare tin, fill mould, spread batter | 3 | 0 | 22 | 8.9 | 9.9 |
| 49 | PLH | peel hard / knobbly / woody | 4 | 1 | 18 | 7.3 | 7.7 |
| 50 | SCE | sauce / ladle onto plate | 2 | 0 | 18 | 7.3 | 7.9 |
| 51 | ASM | assemble / build | 4 | 0 | 17 | 6.9 | 6.0 |
| 52 | KND | knead dough | 2 | 0 | 17 | 6.9 | 6.0 |
| 53 | MAR | marinate / brine / cure | 2 | 0 | 17 | 6.9 | 6.0 |
| 54 | SEP | separate egg (yolk/white) | 4 | 1 | 17 | 6.9 | 5.8 |
| 55 | RNS | rinse grains / pulses / pasta | 1 | 0 | 16 | 6.5 | 6.7 |
| 56 | STC | stir continuously on heat | 2 | 0 | 16 | 6.5 | 7.1 |
| 57 | STU | stuff / fill | 4 | 2 | 16 | 6.5 | 4.6 |
| 58 | CHL | chill / set | 1 | 0 | 15 | 6.0 | 5.2 |
| 59 | PUR | puree / blend | 2 | 0 | 15 | 6.0 | 5.2 |
| 60 | SLM | slice raw meat / fish | 3 | 1 | 15 | 6.0 | 5.6 |
| 61 | RED | reduce | 1 | 0 | 14 | 5.6 | 6.2 |
| 62 | WED | halve / quarter / wedge | 3 | 1 | 14 | 5.6 | 6.0 |
| 63 | JUL | julienne / strips / sticks | 3 | 1 | 13 | 5.2 | 5.4 |
| 64 | RST | roast (oven, dry heat) | 2 | 0 | 13 | 5.2 | 4.8 |
| 65 | TST | toast dry | 2 | 0 | 13 | 5.2 | 5.2 |
| 66 | CAR | carve / slice cooked meat | 4 | 0 | 12 | 4.8 | 4.4 |
| 67 | KNM | mix / knead mince mass | 2 | 0 | 12 | 4.8 | 4.4 |
| 68 | FLD | fold gently | 3 | 0 | 11 | 4.4 | 4.4 |
| 69 | PRF | proof / rise dough | 2 | 0 | 11 | 4.4 | 3.8 |
| 70 | SOK | soak / steep in liquid | 1 | 0 | 11 | 4.4 | 3.8 |
| 71 | SPR | spread / apply evenly | 3 | 0 | 11 | 4.4 | 4.8 |
| 72 | UNM | unmould / turn out | 4 | 0 | 11 | 4.4 | 4.8 |
| 73 | CUD | cut dough / pasta | 3 | 2 | 10 | 4.0 | 3.0 |
| 74 | DFR | deep-fry | 3 | 0 | 10 | 4.0 | 2.8 |
| 75 | EMU | emulsify | 2 | 0 | 10 | 4.0 | 3.8 |
| 76 | ROL | roll out dough | 3 | 2 | 10 | 4.0 | 3.6 |
| 77 | WHP | whip to volume / stiff peaks | 2 | 0 | 10 | 4.0 | 3.8 |
| 78 | WRP | wrap / roll flat item around filling | 4 | 2 | 10 | 4.0 | 3.0 |
| 79 | BRS | braise | 2 | 0 | 9 | 3.6 | 3.6 |
| 80 | BST | baste | 3 | 0 | 9 | 3.6 | 3.6 |
| 81 | MSH | mash / rice / crush | 2 | 0 | 9 | 3.6 | 3.4 |
| 82 | SFT | sift / sieve dry | 1 | 0 | 9 | 3.6 | 4.6 |
| 83 | STR | strip / pluck / break apart | 4 | 1 | 9 | 3.6 | 3.0 |
| 84 | GRL | grill / broil / gratinate | 2 | 0 | 8 | 3.2 | 2.6 |
| 85 | JUI | juice / press citrus | 2 | 0 | 8 | 3.2 | 2.4 |
| 86 | KWM | keep warm / hold | 1 | 0 | 8 | 3.2 | 3.8 |
| 87 | CRM | cream fat with sugar | 2 | 0 | 7 | 2.8 | 3.2 |
| 88 | FRM | shape small pieces by hand | 4 | 2 | 7 | 2.8 | 2.0 |
| 89 | GLZ | glaze / brush | 3 | 0 | 7 | 2.8 | 2.4 |
| 90 | PLE | peel boiled egg | 4 | 1 | 7 | 2.8 | 2.4 |
| 91 | SCO | score / slash | 4 | 0 | 7 | 2.8 | 2.6 |
| 92 | STW | stir-fry (wok) | 3 | 0 | 7 | 2.8 | 3.0 |
| 93 | FRB | form patties / balls from mince | 3 | 2 | 6 | 2.4 | 2.6 |
| 94 | SHD | shape dough | 4 | 2 | 6 | 2.4 | 2.4 |
| 95 | TRM | trim meat: fat, sinew, silverskin, membrane | 5 | 1 | 6 | 2.4 | 2.0 |
| 96 | BMA | bain-marie / gentle water bath | 3 | 0 | 5 | 2.0 | 1.6 |
| 97 | BRD | bread / coat (flour-egg-crumb) | 4 | 2 | 5 | 2.0 | 1.8 |
| 98 | CRH | crush / chop coarse hard items | 2 | 1 | 5 | 2.0 | 1.8 |
| 99 | POU | pound / tenderise / flatten | 3 | 1 | 5 | 2.0 | 2.2 |
| 100 | RUB | rub in fat / crumble | 2 | 0 | 5 | 2.0 | 2.2 |
| 101 | CRL | caramelise | 3 | 0 | 4 | 1.6 | 1.2 |
| 102 | RLT | roll & tie / truss | 5 | 2 | 4 | 1.6 | 1.8 |
| 103 | SQZ | squeeze out liquid | 3 | 0 | 4 | 1.6 | 1.8 |
| 104 | BLA | blanch and shock | 2 | 0 | 3 | 1.2 | 1.2 |
| 105 | DRY | dry: spin or pat dry | 2 | 0 | 3 | 1.2 | 1.2 |
| 106 | EXT | extrude / press through / pipe small | 3 | 0 | 3 | 1.2 | 1.6 |
| 107 | FRK | form dumplings | 3 | 2 | 3 | 1.2 | 1.0 |
| 108 | PIP | pipe / deposit shaped portions | 3 | 0 | 3 | 1.2 | 1.0 |
| 109 | PIT | pit / stone | 4 | 1 | 3 | 1.2 | 1.0 |
| 110 | PTH | pour and spread thin batter | 3 | 0 | 3 | 1.2 | 1.6 |
| 111 | SHR | shred cooked meat | 3 | 0 | 3 | 1.2 | 0.8 |
| 112 | STM | steam | 2 | 0 | 3 | 1.2 | 0.8 |
| 113 | CNT | contact bake | 2 | 0 | 2 | 0.8 | 1.0 |
| 114 | DBN | debone meat / poultry | 5 | 1 | 2 | 0.8 | 0.8 |
| 115 | FLT | fillet / gut / scale fish | 5 | 1 | 2 | 0.8 | 0.4 |
| 116 | PLM | peel tomato / peach (blanch, slip skin) | 3 | 1 | 2 | 0.8 | 0.6 |
| 117 | SKM | skim foam / fat | 3 | 0 | 2 | 0.8 | 0.8 |
| 118 | BAT | batter dip | 3 | 1 | 1 | 0.4 | 0.4 |
| 119 | BCR | make crumbs / pulse dry | 2 | 1 | 1 | 0.4 | 0.4 |
| 120 | BFL | butterfly / split / pocket-cut meat | 4 | 1 | 1 | 0.4 | 0.4 |
| 121 | FRZ | freeze / churn | 3 | 0 | 1 | 0.4 | 0.2 |
| 122 | GRM | grind meat | 2 | 1 | 1 | 0.4 | 0.2 |
| 123 | LSP | separate cabbage leaves (whole) | 4 | 2 | 1 | 0.4 | 0.4 |
| 124 | PLQ | shell shrimp / seafood | 5 | 1 | 1 | 0.4 | 0.4 |
| 125 | POA | poach egg / delicate item | 4 | 0 | 1 | 0.4 | 0.2 |
| 126 | SKW | skewer | 4 | 1 | 1 | 0.4 | 0.2 |

Group totals (meals containing at least one operation of the group):

| Group | Meals | Share |
|---|---|---|
| Dose | 248 | 100.0 % |
| Clean | 184 | 74.2 % |
| Peel | 167 | 67.3 % |
| Trim | 88 | 35.5 % |
| Cut | 222 | 89.5 % |
| Mix | 144 | 58.1 % |
| Shape | 120 | 48.4 % |
| Egg | 52 | 21.0 % |
| Heat | 231 | 93.1 % |
| Finish | 244 | 98.4 % |

### 4.3 Complexity per meal

| Statistic | Value |
|---|---|
| Ordered ops written per meal (mean / median / max) | 9.8 / 10 / 21 |
| Distinct ops incl. implicit (mean / median / max) | 15.6 / 16 / 29 |
| Ingredients per meal (mean / max) | 8.7 / 17 |
| Meals whose hardest operation is D1 | 0 (0.0 %) |
| Meals whose hardest operation is D2 | 1 (0.4 %) |
| Meals whose hardest operation is D3 | 29 (11.7 %) |
| Meals whose hardest operation is D4 | 204 (82.3 %) |
| Meals whose hardest operation is D5 | 14 (5.6 %) |
| Elapsed time < 15 min | 23 (9.3 %) |
| Elapsed time 15-29 min | 57 (23.0 %) |
| Elapsed time 30-59 min | 97 (39.1 %) |
| Elapsed time 60-119 min | 43 (17.3 %) |
| Elapsed time 120-239 min | 24 (9.7 %) |
| Elapsed time >= 240 min | 4 (1.6 %) |

### 4.4 Coverage by difficulty tier

Machine supports all operations with D <= t and none above. Unweighted coverage / weighted coverage. "Needs purchase" = share of the covered meals in which at least one operation is replaced by a pre-processed ingredient.

| Supported tier | S0 (no substitution) | S1 (level-1 purchase) | needs purchase (S1) | S2 (level-2 purchase) | needs purchase (S2) |
|---|---|---|---|---|---|
| D <= 1 (17 ops) | 0.0 % / 0.0 % | 0.0 % / 0.0 % | 0 % | 0.0 % / 0.0 % | 0 % |
| D <= 2 (63 ops) | 0.4 % / 0.6 % | 0.4 % / 0.6 % | 0 % | 0.4 % / 0.6 % | 0 % |
| D <= 3 (98 ops) | 12.1 % / 14.5 % | 61.3 % / 65.3 % | 80 % | 71.0 % / 72.2 % | 83 % |
| D <= 4 (121 ops) | 94.4 % / 94.8 % | 98.4 % / 98.2 % | 4 % | 100.0 % / 100.0 % | 6 % |
| D <= 5 (126 ops) | 100.0 % / 100.0 % | 100.0 % / 100.0 % | 0 % | 100.0 % / 100.0 % | 0 % |

Reading: almost every meal contains at least one D3 operation (dispensing whole items DUN or raw meat DME, plating PLT, washing leafy produce WLF), so D<=2 covers 0.4 %; D<=3 is the *foundation tier* that every design must reach. The D4 operations decide whether the goal is met, and level-1 purchase of pre-processed food is worth 49 percentage points at the foundation tier.

### 4.5 Ranked list of hard operations (D >= 4)

`Blocks` = number of meals that cannot be prepared if this operation alone is unsupported and no substitution is allowed (S0). `Residual S1/S2` = meals still blocked when the level-1 / level-2 purchase is allowed. `Cum.` = share of the corpus blocked when this and all higher-ranked hard operations are unsupported (union, S0). Ranked by blocked meals.

| Rank | Code | Operation | D | Blocks (n) | Blocks % | Blocks w% | Cum. union % | av | Residual S1 (n) | Residual S2 (n) | What to buy instead / alternative |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | PLA | peel alliums | 4 | 129 | 52.0 | 51.6 | 52.0 | 1 | 0 | 0 | air-jet onion peeler (industrial), garlic roller; buy peeled onions/garlic or paste |
| 2 | COR | core / deseed / hull | 4 | 50 | 20.2 | 20.6 | 58.5 | 1 | 0 | 0 | coring punch for apple; pepper: cut-off cap + rinse; buy frozen pepper strips / canned tomatoes |
| 3 | FLP | flip / turn item | 4 | 32 | 12.9 | 12.7 | 65.7 | 0 | 32 | 32 | spatula robots exist (Flippy); pancake/omelette/tortilla D5; patties D3; alternative: two-sided contact |
| 4 | TRE | trim ends / stems / roots | 4 | 31 | 12.5 | 12.9 | 68.5 | 1 | 0 | 0 | cut-off station with vision; buy trimmed (frozen beans, pre-cut leek) |
| 5 | PLS | peel soft / thin-skinned fruit & veg | 4 | 26 | 10.5 | 10.1 | 70.2 | 1 | 0 | 0 | spiral apple peeler (apple only); serve unpeeled where recipe allows; banana is a separate handling problem |
| 6 | PLH | peel hard / knobbly / woody | 4 | 18 | 7.3 | 7.7 | 70.6 | 1 | 0 | 0 | knife-based with vision / cut-away peel (loss 30 %); avoid: unpeeled Hokkaido, canned/cooked beet, jarred ginger |
| 7 | ASM | assemble / build | 4 | 17 | 6.9 | 6.0 | 73.4 | 0 | 17 | 17 | modular; multi-component pick-and-place of soft items |
| 8 | SEP | separate egg (yolk/white) | 4 | 17 | 6.9 | 5.8 | 78.2 | 1 | 0 | 0 | egg separator cup (yolk cup) after cracking; buy liquid yolk/white |
| 9 | STU | stuff / fill | 4 | 16 | 6.5 | 4.6 | 79.4 | 2 | 16 | 0 | dosing nozzle into rigid cavity (peppers: D3); soft/flat pockets D5 |
| 10 | CAR | carve / slice cooked meat | 4 | 12 | 4.8 | 4.4 | 79.8 | 0 | 12 | 12 | slicer with fence for boneless roasts (D3); bone-in poultry D5; alternative: boneless joints, serve pulled/whole |
| 11 | UNM | unmould / turn out | 4 | 11 | 4.4 | 4.8 | 81.9 | 0 | 11 | 11 | non-stick/silicone moulds, flexing, blower; risk of breakage |
| 12 | WRP | wrap / roll flat item around filling | 4 | 10 | 4.0 | 3.0 | 81.9 | 2 | 10 | 0 | rolling belt with fold guides; sushi/roll cake D5 |
| 13 | STR | strip / pluck / break apart | 4 | 9 | 3.6 | 3.0 | 83.1 | 1 | 0 | 0 | tear station; buy frozen chopped kale, florets, herb pastes |
| 14 | FRM | shape small pieces by hand | 4 | 7 | 2.8 | 2.0 | 84.7 | 2 | 7 | 0 | forming rollers/extrusion + cutter approximations |
| 15 | PLE | peel boiled egg | 4 | 7 | 2.8 | 2.4 | 85.9 | 1 | 0 | 0 | tumble + water spray; buy peeled boiled eggs |
| 16 | SCO | score / slash | 4 | 7 | 2.8 | 2.6 | 86.7 | 0 | 7 | 7 | blade path with vision/force; bread lame |
| 17 | SHD | shape dough | 4 | 6 | 2.4 | 2.4 | 87.5 | 2 | 6 | 0 | press + pre-shaped moulds; braids/pretzels D5 |
| 18 | TRM | trim meat: fat, sinew, silverskin, membrane | 5 | 6 | 2.4 | 2.0 | 87.5 | 1 | 0 | 0 | buy trimmed cuts; no household-scale machine solution |
| 19 | BRD | bread / coat (flour-egg-crumb) | 4 | 5 | 2.0 | 1.8 | 87.9 | 2 | 5 | 0 | 3-bath tumble/dredge chain, air-blow; hygienic with raw egg + raw meat; buy pre-breaded |
| 20 | RLT | roll & tie / truss | 5 | 4 | 1.6 | 1.8 | 87.9 | 2 | 4 | 0 | no solution known; alternatives: pins/clips, roulade press mould, pre-made Rouladen from butcher |
| 21 | PIT | pit / stone | 4 | 3 | 1.2 | 1.0 | 87.9 | 1 | 0 | 0 | cherry pitter (per-fruit); buy pitted / jarred / frozen |
| 22 | DBN | debone meat / poultry | 5 | 2 | 0.8 | 0.8 | 87.9 | 1 | 0 | 0 | buy boneless; bones are needed for stock only (buy stock) |
| 23 | FLT | fillet / gut / scale fish | 5 | 2 | 0.8 | 0.4 | 87.9 | 1 | 0 | 0 | buy fillets (fresh/frozen) |
| 24 | BFL | butterfly / split / pocket-cut meat | 4 | 1 | 0.4 | 0.4 | 87.9 | 1 | 0 | 0 | buy pre-cut pockets/flat cutlets; or bake-in-bag alternative |
| 25 | LSP | separate cabbage leaves (whole) | 4 | 1 | 0.4 | 0.4 | 87.9 | 2 | 1 | 0 | blanch and peel; substitute pre-blanched leaves (rare) or chopped-cabbage casserole |
| 26 | PLQ | shell shrimp / seafood | 5 | 1 | 0.4 | 0.4 | 87.9 | 1 | 0 | 0 | buy frozen peeled shrimp |
| 27 | POA | poach egg / delicate item | 4 | 1 | 0.4 | 0.2 | 87.9 | 0 | 1 | 1 | vessel with egg-poaching cups |
| 28 | SKW | skewer | 4 | 1 | 0.4 | 0.2 | 87.9 | 1 | 0 | 0 | pick-and-thread jig; alternative: no skewer (cubes in pan) |

Clusters (meals with at least one op of the cluster; overlaps exist):

| Cluster | Meals | Share |
|---|---|---|
| Vegetable peeling / trimming (PLA PLP PLH PLS PLM PLE TRE COR PIT STR LSP) | 173 | 69.8 % |
| Butchery (TRM DBN FLT BFL PLQ) | 11 | 4.4 % |
| Shaping (STU WRP FRM SHD BRD RLT SKW) | 38 | 15.3 % |
| Manipulation and finishing (FLP UNM ASM CAR SCO POA SEP) | 83 | 33.5 % |
| Egg handling (CRK SEP PLE POA) | 59 | 23.8 % |
| Deep-fry (DFR) | 10 | 4.0 % |
| Any D4/D5 operation | 218 | 87.9 % |

Findings:

* Only 14 meals (5.6 %) contain a D5 operation. Deboning, trimming, filleting and shelling can all be bought away (level 1); roll-and-tie (Rouladen, Kohlrouladen, poultry trussing) is the only D5 operation that needs a level-2 substitute (ready-rolled Rouladen from the butcher counter) and blocks 4 meals. The customer names Rouladen explicitly, so RLT deserves a dedicated mechanism (Section 7).
* The largest single blocker is onion/garlic peeling (52.0 % of meals). It is a D4 operation at household scale but has the most mature substitutes (peeled onions, frozen diced onion, garlic paste). It should be treated as *buy pre-processed first, build a peeler later*.
* After PLA, the biggest blockers with **no** substitute (av=0) are flipping/turning (12.9 %), assembling (6.9 %), carving cooked meat (4.8 %), unmoulding (4.4 %), scoring (2.8 %) and egg poaching (0.4 %). Together their union is 29.0 % of meals. These are the operations for which R4/R5/D4/D6 must produce real mechanisms, because purchasing cannot help.
* Egg operations: cracking (CRK) occurs in 36 meals (14.5 %) and separating (SEP) in 17 (6.9 %), mostly baking and desserts. Liquid pasteurised egg can replace CRK/SEP in every recipe except fried/boiled/poached eggs (BF03-BF05, BF14) and dishes that show the egg.

### 4.6 Build order: which hard operations are needed for 80 / 90 / 95 / 99 % coverage

Start from the foundation tier (all D<=3 operations supported). Then add the D4/D5 operations one at a time by a cost-aware greedy rule (fractional progress towards completing blocked meals, divided by D squared as an effort proxy). Coverage after each addition, unweighted / weighted.

**S0: no pre-processed purchase (the machine must do everything traditional)**

| Step | Add operation | D | Coverage | Weighted | Covered meals needing a purchase |
|---|---|---|---|---|---|
| 0 | foundation tier (all D<=3) | - | 12.1 % | 14.5 % | 0 % |
| 1 | PLA peel alliums | 4 | 29.0 % | 32.5 % | 0 % |
| 2 | COR core / deseed / hull | 4 | 32.7 % | 35.9 % | 0 % |
| 3 | FLP flip / turn item | 4 | 40.3 % | 43.1 % | 0 % |
| 4 | TRE trim ends / stems / roots | 4 | 48.0 % | 51.4 % | 0 % |
| 5 | PLS peel soft / thin-skinned fruit & veg | 4 | 54.0 % | 57.9 % | 0 % |
| 6 | PLH peel hard / knobbly / woody | 4 | 58.1 % | 62.5 % | 0 % |
| 7 | SEP separate egg (yolk/white) | 4 | 62.1 % | 65.9 % | 0 % |
| 8 | ASM assemble / build | 4 | 66.1 % | 70.0 % | 0 % |
| 9 | STU stuff / fill | 4 | 69.4 % | 72.2 % | 0 % |
| 10 | UNM unmould / turn out | 4 | 73.8 % | 77.0 % | 0 % |
| 11 | CAR carve / slice cooked meat | 4 | 76.2 % | 79.4 % | 0 % |
| 12 | WRP wrap / roll flat item around filling | 4 | 79.4 % | 81.9 % | 0 % |
| 13 | STR strip / pluck / break apart | 4 | 82.3 % | 84.5 % | 0 % |
| 14 | PLE peel boiled egg | 4 | 85.1 % | 86.9 % | 0 % |
| 15 | SCO score / slash | 4 | 86.3 % | 87.9 % | 0 % |
| 16 | FRM shape small pieces by hand | 4 | 87.9 % | 89.1 % | 0 % |
| 17 | SHD shape dough | 4 | 90.3 % | 91.5 % | 0 % |
| 18 | BRD bread / coat (flour-egg-crumb) | 4 | 91.9 % | 92.9 % | 0 % |
| 19 | TRM trim meat: fat, sinew, silverskin, membrane | 5 | 94.4 % | 95.0 % | 0 % |
| 20 | PIT pit / stone | 4 | 95.6 % | 96.0 % | 0 % |
| 21 | RLT roll & tie / truss | 5 | 96.8 % | 97.4 % | 0 % |
| 22 | SKW skewer | 4 | 97.2 % | 97.6 % | 0 % |
| 23 | POA poach egg / delicate item | 4 | 97.6 % | 97.8 % | 0 % |
| 24 | LSP separate cabbage leaves (whole) | 4 | 98.0 % | 98.2 % | 0 % |
| 25 | BFL butterfly / split / pocket-cut meat | 4 | 98.4 % | 98.6 % | 0 % |
| 26 | FLT fillet / gut / scale fish | 5 | 98.8 % | 98.8 % | 0 % |
| 27 | DBN debone meat / poultry | 5 | 99.6 % | 99.6 % | 0 % |
| 28 | PLQ shell shrimp / seafood | 5 | 100.0 % | 100.0 % | 0 % |

Thresholds: 80 % after step 13 (STR); 90 % after step 17 (SHD); 95 % after step 20 (PIT); 99 % after step 27 (DBN).

**S1: level-1 purchase allowed (peeled, cored, boneless, trimmed, filleted, minced, cut)**

| Step | Add operation | D | Coverage | Weighted | Covered meals needing a purchase |
|---|---|---|---|---|---|
| 0 | foundation tier (all D<=3) | - | 61.3 % | 65.3 % | 80 % |
| 1 | FLP flip / turn item | 4 | 71.0 % | 74.2 % | 77 % |
| 2 | ASM assemble / build | 4 | 76.2 % | 79.0 % | 75 % |
| 3 | STU stuff / fill | 4 | 79.8 % | 81.5 % | 75 % |
| 4 | UNM unmould / turn out | 4 | 84.3 % | 86.3 % | 74 % |
| 5 | CAR carve / slice cooked meat | 4 | 87.1 % | 88.9 % | 75 % |
| 6 | WRP wrap / roll flat item around filling | 4 | 90.7 % | 91.5 % | 76 % |
| 7 | SCO score / slash | 4 | 91.9 % | 92.5 % | 76 % |
| 8 | FRM shape small pieces by hand | 4 | 93.5 % | 93.8 % | 75 % |
| 9 | SHD shape dough | 4 | 96.0 % | 96.2 % | 74 % |
| 10 | BRD bread / coat (flour-egg-crumb) | 4 | 98.0 % | 98.0 % | 73 % |
| 11 | RLT roll & tie / truss | 5 | 99.2 % | 99.4 % | 73 % |
| 12 | POA poach egg / delicate item | 4 | 99.6 % | 99.6 % | 73 % |
| 13 | LSP separate cabbage leaves (whole) | 4 | 100.0 % | 100.0 % | 73 % |

Thresholds: 80 % after step 4 (UNM); 90 % after step 6 (WRP); 95 % after step 9 (SHD); 99 % after step 11 (RLT).

**S2: level-1 and level-2 purchase allowed (also ready-stuffed, ready-rolled, formed, ready dough)**

| Step | Add operation | D | Coverage | Weighted | Covered meals needing a purchase |
|---|---|---|---|---|---|
| 0 | foundation tier (all D<=3) | - | 71.0 % | 72.2 % | 83 % |
| 1 | FLP flip / turn item | 4 | 82.3 % | 83.1 % | 80 % |
| 2 | ASM assemble / build | 4 | 88.7 % | 88.9 % | 79 % |
| 3 | UNM unmould / turn out | 4 | 93.1 % | 93.8 % | 77 % |
| 4 | CAR carve / slice cooked meat | 4 | 96.8 % | 97.2 % | 78 % |
| 5 | SCO score / slash | 4 | 99.6 % | 99.8 % | 79 % |
| 6 | POA poach egg / delicate item | 4 | 100.0 % | 100.0 % | 79 % |

Thresholds: 80 % after step 1 (FLP); 90 % after step 3 (UNM); 95 % after step 4 (CAR); 99 % after step 5 (SCO).

The full ranking without the foundation-tier assumption (all 126 operations from scratch, S0) is in Appendix B; it shows the long tail: 50 % needs 81 of 126 operations, 80 % needs 104, 90 % needs 112, 95 % needs 115, 99 % needs 124.

### 4.7 What can be avoided by buying pre-processed ingredients

Meals affected = corpus meals containing the operation the purchase replaces. Storage class and shelf life refer to the pre-processed product (estimates from common retail products).

| Pre-processed product | Replaces | Level | Meals affected | Storage / shelf life of the product | Caveat |
|---|---|---|---|---|---|
| Peeled onions (fresh-cut) or frozen diced onion; garlic paste or frozen crushed garlic | PLA (+DIC/MIN) | 1 | 129 | fresh-cut onion C 1-2 wk; frozen F 12 mo; garlic paste C 4-8 wk | frozen onion is watery, changes browning; peeled cloves oxidise |
| Vacuum-peeled potatoes / peeled carrots | PLP | 1 | 60 | vacuum potatoes C 2-4 wk sealed, 2-3 d opened | only boiling potatoes; sulphite-treated; price 2-3 x |
| Peeled celeriac/kohlrabi cubes, cooked vacuum beetroot, jarred ginger paste, frozen pumpkin cubes, canned white asparagus | PLH | 1 | 18 | cubes C 5-7 d; frozen F 12 mo; cooked beet C 4-8 wk | seasonal quality; white asparagus canned is a different dish |
| Unpeeled use, or fresh-cut apple slices (ascorbate-treated) | PLS | 1 | 26 | C 7-10 d | many recipes accept unpeeled apples; cucumber unpeeled is acceptable |
| Canned peeled tomatoes | PLM | 1 | 2 | A 24 mo | fine for cooked dishes only |
| Frozen pepper strips, canned tomatoes, pitted jarred cherries, pre-cored apple rings | COR, PIT | 1 | 51 | F 12 mo / A 24 mo | texture of frozen pepper is soft (cooked dishes only) |
| Frozen cut beans, cut leek rings, frozen Brussels sprouts, trimmed asparagus | TRE | 1 | 31 | F 12 mo / C 5-7 d | frozen is acceptable for cooked dishes |
| Frozen chopped kale, frozen florets, frozen herbs, herb paste | STR, CHH | 1 | 33 | F 12 mo | frozen herbs lose aroma; fresh needed for garnish and Grüne Soße |
| Liquid pasteurised egg, egg yolk, egg white (carton) | CRK, SEP | 1 | 52 | C 3-4 wk unopened, 3 d opened | not for fried/boiled/poached egg; whipping quality of carton white is lower |
| Peeled boiled eggs (vacuum) | PLE | 1 | 7 | C 4-6 wk | - |
| Boneless cuts (breast, thigh, boneless roast), ready trimmed tenderloin, trimmed ribs | DBN, TRM | 1 | 8 | C 2-4 d / F | bones give stock and flavour; use bought stock |
| Fish fillets (fresh or frozen), frozen peeled shrimp | FLT, PLQ | 1 | 3 | F 6-12 mo / C 1-2 d | whole-fish dishes (trout, bream) remain whole and are carved on the plate by the guest |
| Minced meat (fresh 1 d, vacuum 3 d, frozen 3 mo), sliced strips and cutlets from the butcher | GRM, SLM, POU, BFL | 1 | 21 | C 1-3 d / F 3 mo | mince is the most perishable item; freezing needs thaw lead time; the machine can also grind |
| Grated cheese, pre-grated Parmesan, pre-ground nutmeg | GRC, GRF | 1 | 44 | C 1-2 wk | anti-caking agents, less flavour |
| Pre-sliced bread, ham, cheese, sausage | SLB, SLI (cold cuts) | 1 | 33 | C 3-7 d | bread staling |
| Breadcrumbs | BCR | 1 | 1 | A 12 mo | - |
| Frozen breaded Schnitzel/fish, frozen formed patties/Frikadellen, frozen dumplings, ready-stuffed peppers | BRD, FRB, FRK, STU | 2 | 28 | F 6-12 mo | this is the convenience-food route; not the traditional dish quality; breading dominates Schnitzel/cordon bleu |
| Ready-rolled fresh Rouladen (butcher counter), pre-blanched cabbage leaves | RLT, LSP | 2 | 4 | C 2-3 d | not available everywhere; price 1.5-2 x |
| Rolled pastry/pizza dough sheets, fresh pasta, ready-made wrappers | ROL, SHD, CUD, WRP | 2 | 27 | C 4-6 wk / F | standard for quiche/Flammkuchen; bread loaf shaping cannot be bought away except by buying ready dough balls |

### 4.8 Cross-cutting operations that are not in the taxonomy

* **Tasting and adjusting seasoning** ("abschmecken") appears in nearly every recipe. It cannot be done by a machine directly; the machine uses fixed recipe doses scaled by portion count and lets the user adjust with a personal seasoning factor (salt 0.8-1.2). Rated D5; treated as a recipe/control issue (D10), not a unit operation.
* **Doneness detection** (core temperature probe, colour, vision, weight loss): needed for steak, roasts, poultry, eggs, cakes (skewer test), bread. Treated as sensing (D10, D5).
* **Timing synchronisation** of several dishes to finish together (Section 4.9 menus); scheduler problem.
* **Beverages** (coffee, tea) are out of scope of this corpus.
* **Hot-air "air fryer" cooking** (trend 2025) is a convection oven mode (BKE/RST/GRL with high fan), not a separate unit operation.

### 4.9 Heat sources, vessels, temperatures and times

Per-dish peak concurrency from the corpus:

| Concurrent heat sources H | Meals | Share |
|---|---|---|
| 0 | 24 | 9.7 % |
| 1 | 140 | 56.5 % |
| 2 | 73 | 29.4 % |
| 3 | 11 | 4.4 % |

| Concurrent vessels B | Meals | Share |
|---|---|---|
| 0 | 2 | 0.8 % |
| 1 | 131 | 52.8 % |
| 2 | 93 | 37.5 % |
| 3 | 18 | 7.3 % |
| 4 | 4 | 1.6 % |

Real meals are menus: main + one to three sides + sauce. The table lists typical menus; peak H is the maximum number of heat sources active at the same time (oven counts as one), B the peak of food vessels.

| Menu | Vessels | Peak H | Peak B | Notes |
|---|---|---|---|---|
| Spaghetti Bolognese (IT01) | sauce pot; pasta pot | 2 | 3 | Bolognese 45-90 min, pasta 10 min starts at 35 min before end |
| Schnitzel + Pommes + mixed salad (DM03, SD04, SA01) | pan; fryer; salad bowl; 3-stage breading station | 2 | 5 | fries blanched in advance; schnitzel in 3 batches of 2 (28 cm pan) |
| Steak + baked potato + salad (DM23, SD25, SA01) | pan; oven; bowl | 2 | 3 | potato 60 min in oven first |
| Frikadellen + potato salad + cucumber salad (DM01, SD06, SA02) | potato pot; pan; 2 bowls | 2 | 4 | potato salad needs 30 min rest; pan in 3 batches |
| Pizza + salad (IT10, SA01) | oven; dough bowl; salad bowl | 1 | 3 | dough proof 1-24 h; pizza one at a time in one oven |
| Käsespätzle + salad (IT19, SA01) | Spätzle pot; onion pan; oven or gratin dish; salad bowl | 3 | 4 | Spätzle in 3-4 batches of 150 g flour |
| Fish fingers + mash + creamed spinach (FI01, SD02, SD13) | pan or oven; potato pot; spinach pot | 3 | 4 | - |
| Rouladen + red cabbage + potato dumplings (DM02, SD11, SD07) | braiser; red cabbage pot; potato pot then dumpling pot | 3 | 5 | critical path Rouladen 150 min; dumplings last 40 min |
| Roast pork + dumplings + red cabbage + gravy (DM06, SD07, SD11, SC02) | oven; red cabbage pot; potato/dumpling pot; sauce pot | 4 | 6 | critical path roast 190 min; gravy from roast juices |
| Goose + red cabbage + dumplings + gravy (DM21, SD11, SD07, SC02) | oven (4-5 kg bird); red cabbage pot; potato/dumpling pot; sauce pot | 4 | 6 | critical path 260 min; oven fully occupied |
| White asparagus + hollandaise + potatoes + schnitzel (SD19, DM03) | asparagus pot; potato pot; bain-marie; pan | 4 | 6 | hollandaise last; asparagus peeling 25-30 min for 6 |
| Butter chicken + rice + naan + raita (IN01, SD10, IN06) | oven or grill; sauce pot; rice pot; pan for naan | 4 | 5 | naan pan in 6 batches of 1 |
| Burger + fries + coleslaw (US01, SD04, SA05) | pan; fryer; bun toaster; bowl | 3 | 4 | - |
| Lasagne + salad (IT05, SA01) | Bolognese pot; béchamel pot; oven; bowl | 3 | 4 | oven preheat during sauces; bake 40 min + rest 15 min |
| Breakfast for 6: scrambled eggs, pancakes, bacon, porridge (BF03, BF06, BF07, BF01) | 2-3 pans; porridge pot | 4 | 5 | pancakes are the bottleneck (12 x 2 min sequential) |

Of 15 typical menus, 5 need <= 2 heat sources, 5 need 3 and 5 need 4. **Design target derived from the data: 4 independent hob zones (induction, at least 2 of them boost >= 3 kW) + 1 oven (>= 45 L, fan, steam, 250-280 C top/bottom) + 1 deep-fryer (3 L oil) that may share a hob zone, and a warm-hold.** Menus with 5 heat sources do not occur in the list; a 5th could be created by a sequential schedule (dumplings after roast).

Power check (estimate): heating 9 L of pasta water from 15 to 100 C takes 9 kg x 4.19 kJ/(kg K) x 85 K = 3.2 MJ = 0.89 kWh, i.e. 18 min at 3 kW. A roast menu (oven 2.5 kW average + 3 hobs at 1.5 kW) peaks at 7-8 kW, and the brief allows only "220 V": a single-phase 16 A circuit gives 3.7 kW. See Open issues.

Cooking modes needed (temperature at the food or pan surface; from the corpus rows):

| Mode | Temperature | Time | Meals (approx.) | Notes |
|---|---|---|---|---|
| Boil (pasta, potatoes, eggs) | 100 C rolling | eggs 5-10 min, pasta 8-12 min, potatoes 20-25 min | 47 | 1 L water per 100 g pasta; salt 10 g/L |
| Simmer / poach | 85-95 C | 10-120 min | 79 | PID control, no boil for dumplings and delicate fish |
| Steam | 100 C | 5-20 min | 3 | insert or oven steam |
| Absorption (rice, couscous) | 100 C then 90 C covered | rice 12-18 min, couscous 5 min | 23 | exact water ratio 1:1 to 1:2 |
| Sauté / sweat | 120-160 C | 5-20 min | 84 | onions must not brown unless intended |
| Sear / high-heat pan | 200-260 C surface | 1-4 min per side | 25 | 3 kW boost, oil smoke point 200-240 C |
| Pan-fry / shallow-fry | 150-190 C | 2-6 min per side | 43 | batch size 2-4 items per 28 cm pan |
| Stir-fry | 250+ C | 3-8 min | 7 | wok, tossing; 3.5 kW class |
| Deep-fry | 160-190 C | 1-5 min | 10 | 2-3 L oil, batch 500-750 g |
| Braise | 150-170 C oven or 90-95 C hob | 1.5-3 h | 9 | lid, low evaporation |
| Roast | 160-230 C | 0.5-4 h (goose 3-4 h) | 13 | core probe; basting; rind 220 C |
| Bake cake/casserole | 160-200 C | 20-70 min | 44 | top/bottom heat, fan optional |
| Bake bread/pizza | 220-280 C with steam | bread 40-50 min, pizza 6-12 min | 8 | pizza and Flammkuchen want 250-280 C; household ovens stop at 250 C |
| Grill / gratinate | 250-300 C top heat | 3-10 min | 8 | infrared element close to food |
| Bain-marie | 65-80 C water | 10-45 min | 5 | hollandaise 65-70 C, custards 80 C |
| Proof | 28-35 C, 75-90 % RH | 30-90 min (12-16 h in fridge) | 11 | or use cold storage |
| Chill / set | 2-5 C | 2-12 h | 15 | needs cold vessel dwell |
| Freeze / churn | -18 C and below | 3-6 h | 1 | only ice cream |

Maximum temperatures required: pan surface 260 C, oil 190 C, oven 250-280 C, top heat 300 C. Of the 57 meals that use the oven for baking or roasting only 2 (pizza IT10, Flammkuchen FR05) want more than 250 C; a 250 C oven serves the rest, and naan (IN06) is done in a pan. Minimum: 2 C (chill), -18 C (freeze, ice cream).

## 5. Ingredient statistics

180 ingredient types occur in the corpus (more than the ~150 requested; types used by only one or two meals are rare specialities), listed by class and then by frequency. `n` = meals using the ingredient. Storage: **A** ambient (15-22 C dry), **A\*** ambient but prefers cool dark 8-15 C, **C** fridge 2-5 C, **F** freezer -18 C. Shelf life is what the box can expect inside the machine's storage class (estimate, see sources). `Dose` = the dosing/dispensing operation from Section 2 that the ingredient requires.

| Key | Ingredient | Class | Physical form | Size / unit | Storage | Shelf life | Handling notes | Dose | n |
|---|---|---|---|---|---|---|---|---|---|
| potato | Potato / Kartoffel | root/tuber | whole, irregular ovoid | Ø 35-90 mm, 60-300 g | A* | 3-8 wk cool-dark; 2-3 wk at 20 C | earthy, dirty, sprouts and turns green in light, tolerates knocks, sheds soil | DUN | 44 |
| carrot | Carrot / Moehre | root/tuber | whole, tapered cylinder | Ø 20-40 x 120-250 mm, 50-200 g | C | 2-4 wk | dirty, goes limp when dry, tapered ends | DUN | 32 |
| ginger | Ginger / Ingwer | root/tuber | knobbly rhizome | 40-120 mm pieces | C | 3-4 wk (F longer) | fibrous, irregular, strong odour | DUN | 12 |
| celeriac | Celeriac / Sellerie | root/tuber | whole, knobbly sphere | Ø 80-150 mm, 300-800 g | C | 3-4 wk | knobbly with soil in folds, very hard, heavy | DUN | 11 |
| parsnip | Parsnip, parsley root / Pastinake | root/tuber | tapered cylinder | Ø 30-60 x 150-250 mm | C | 2-3 wk | like carrot, woody core | DUN | 2 |
| beet | Beetroot / Rote Bete (mostly cooked, vacuum) | root/tuber | whole sphere | Ø 50-100 mm, 100-300 g | C | raw 2-3 wk; cooked vacuum 4-8 wk | stains everything red, slippery when cooked | DUN | 1 |
| kohlrabi | Kohlrabi | root/tuber | whole sphere with leaf stubs | Ø 70-120 mm, 200-500 g | C | 1-2 wk | woody when old, leaf stubs | DUN | 1 |
| sweetpot | Sweet potato / Suesskartoffel | root/tuber | whole, elongated | Ø 50-90 x 100-250 mm, 200-500 g | A* | 3-4 wk | sticky sap, irregular, bruises easily | DUN | 1 |
| onion | Onion / Zwiebel | allium | whole sphere, papery skin | Ø 40-90 mm, 60-250 g | A* | 1-2 months | skin flakes and dust, tear gas, odour, rolls | DUN | 112 |
| garlic | Garlic / Knoblauch | allium | bulb of cloves | bulb Ø 40-60 mm, clove 10-30 mm | A* | 1-2 months | sticky skin, strong odour, small | DUN | 44 |
| springonion | Spring onion / Lauchzwiebel | allium | bunch of stalks | Ø 10-25 x 200-300 mm | C | ~1 wk | wilts, wet, slippery | DUN | 9 |
| leek | Leek / Lauch, Porree | allium | long cylinder | Ø 25-40 x 250-350 mm white part | C | 1-2 wk | soil trapped between layers, long, floppy | DUN | 4 |
| bellpepper | Bell pepper / Paprika | fruit-veg | hollow whole, thin wall | Ø 70-100 x 90-150 mm, 150-250 g | C | 1-2 wk | hollow with seeds, light, nests poorly | DUN | 27 |
| tomato | Tomato | fruit-veg | whole, soft | Ø 40-80 mm, 60-200 g | C | 5-10 d | fragile, bruises, juicy, cold dulls flavour | DUN | 20 |
| cucumber | Cucumber / Gurke | fruit-veg | whole, long | Ø 40-55 x 250-400 mm, 300-450 g | C | 7-10 d | wet, slippery, soft skin, cold damage | DUN | 9 |
| zucchini | Zucchini | fruit-veg | whole cylinder | Ø 30-60 x 150-250 mm, 150-350 g | C | ~1 wk | soft skin scratches, slippery | DUN | 8 |
| chili | Fresh chili | fruit-veg | pod | 50-100 mm, 5-20 g | C | 1-2 wk | capsaicin hazard, cross-contamination | DUN | 5 |
| avocado | Avocado | fruit-veg | whole, soft when ripe | Ø 60-80 x 90-120 mm, 150-250 g | A ripening / C ripe | 3-7 d ripe | large pit, oxidises brown, bruises, ripeness varies | DUN | 4 |
| eggplant | Aubergine / Eggplant | fruit-veg | whole, ovoid | Ø 60-100 x 150-250 mm | C | ~1 wk | bruises, absorbs oil, bitter juice | DUN | 4 |
| cherrytom | Cherry tomato | fruit-veg | whole, soft small | Ø 15-30 mm, 10-20 g | C | 7-10 d | splits, rolls | DUN | 1 |
| fennel | Fennel bulb / Fenchel | fruit-veg | whole bulb | Ø 80-120 mm, 200-400 g | C | 1-2 wk | fibrous outer layers | DUN | 1 |
| pumpkin | Pumpkin / Kuerbis (Hokkaido, Butternut) | fruit-veg | whole, hard rind | Ø 150-250 mm, 0.8-2 kg | A* | 1-3 months whole; cut 3-5 d C | very hard, heavy, slippery seeds and strands | DUN | 1 |
| radish | Radish / Radieschen | fruit-veg | small sphere | Ø 20-30 mm | C | 5-7 d | leaves, dirty | DUN | 1 |
| whitecab | White cabbage / Weisskohl | brassica | head | Ø 150-250 mm, 1-2 kg | C | 4-8 wk | heavy, hard core, dirty outer leaves | DUN | 4 |
| cauli | Cauliflower / Blumenkohl | brassica | head | Ø 120-180 mm, 0.5-1 kg | C | 1-2 wk | florets fall apart, odour | DUN | 3 |
| savoy | Savoy cabbage / Wirsing | brassica | head, crinkled leaves | Ø 150-220 mm, 0.8-1.5 kg | C | 2-3 wk | crinkled leaves trap dirt | DUN | 3 |
| broccoli | Broccoli | brassica | head | Ø 100-150 mm, 300-500 g | C | 4-7 d | yellows, florets fall apart | DUN | 1 |
| kale | Kale / Gruenkohl (frozen chopped is common) | brassica | leafy, stiff stems; frozen: chopped pellets | fresh 200-800 g bunch | F (fresh C) | fresh 4-5 d; frozen 12 mo | bulky, stem must be stripped; frozen clumps to blocks | DSO | 1 |
| redcab | Red cabbage / Rotkohl | brassica | head | Ø 150-250 mm, 1-2 kg | C | 4-8 wk | stains, hard core | DUN | 1 |
| sprouts | Brussels sprouts / Rosenkohl | brassica | small heads | Ø 20-40 mm, 10-25 g | C | 5-7 d (F 12 mo) | odour, outer leaves | DUN | 1 |
| lettuce | Lettuce / Kopfsalat, Romana, Eisberg | leafy | head | 150-400 g | C | 3-7 d | fragile, wet, browns at cuts, bulky | DUN | 8 |
| celerystalk | Celery stalks / Staudensellerie | leafy | stalks | Ø 20-30 x 200-300 mm | C | 1-2 wk | stringy | DUN | 2 |
| asianveg | Pak choi, Chinese cabbage | leafy | heads | 150-400 g | C | 4-7 d | leaf stems + leaves differ in cook time | DUN | 1 |
| saladmix | Salad leaves / Feldsalat, Rucola, Babyleaf | leafy | loose leaves | 100-250 g bag | C | 2-5 d | very fragile, wilts and goes slimy | DUN | 1 |
| spinach | Spinach, fresh / Spinat | leafy | loose leaves | 200-500 g | C | 2-3 d | fragile, sand, wilts | DUN | 1 |
| greenbean | Green beans / Gruene Bohnen | stem/pod | pods | Ø 6-10 x 100-150 mm | C | 4-7 d | tangle, must be topped and tailed | DUN | 4 |
| asparagus | Asparagus / Spargel (white or green) | stem/pod | spears | Ø 12-25 x 200-250 mm | C, wrapped moist | 3-5 d | fragile tips, woody ends, must be peeled (white), seasonal Apr-Jun | DUN | 3 |
| beansprouts | Bean sprouts / Sojasprossen | stem/pod | thin tangled threads | 100-300 g | C | 2-3 d | very perishable, wet, tangle | DUN | 2 |
| mushroom | Mushrooms / Champignons | fungus | whole caps | Ø 30-60 mm, 15-40 g | C | 3-5 d | fragile, absorb water, bruise brown | DUN | 10 |
| parsley | Parsley / Petersilie | herb | bunch | 30-50 g bunch | C | 5-7 d (F chopped 6 mo) | wet, fragile, bruises | DUN | 24 |
| basil | Basil | herb | bunch or pot | 20-30 g | A pot / C | 3-5 d | blackens when cold or bruised | DUN | 8 |
| thyme | Thyme, rosemary (fresh) | herb | woody stems | 10-20 g | C | 1-2 wk | strip leaves, woody | DUN | 8 |
| chives | Chives / Schnittlauch | herb | bunch of hollow stems | 20-30 g | C | 5-7 d | fragile, hollow | DUN | 7 |
| dill | Dill | herb | bunch | 20-30 g | C | 3-5 d | very fragile | DUN | 7 |
| coriander | Coriander / Koriander | herb | bunch | 20-30 g | C | 3-5 d | fragile | DUN | 3 |
| mint | Mint / Minze | herb | bunch | 20-30 g | C | 3-5 d | fragile | DUN | 2 |
| lemon | Lemon / Zitrone (also lime) | fruit | whole | Ø 50-70 mm, 80-150 g | C | 2-4 wk | zest oils | DUN | 33 |
| apple | Apple / Apfel | fruit | whole | Ø 60-90 mm, 120-250 g | C | 3-6 wk | bruises, browns after cutting | DUN | 18 |
| raisins | Raisins, dried fruit / Rosinen | fruit | sticky granular | Ø 8-15 mm | A | 6-12 mo | sticky, clump together | DSO | 8 |
| berries | Berries (blue-, rasp-, blackberry; usually frozen) | fruit | frozen or fresh loose | Ø 8-20 mm | F (fresh C) | frozen 12 mo; fresh 2-4 d | fragile, stain, clump when thawed | DSO | 7 |
| orange | Orange | fruit | whole | Ø 65-85 mm, 150-250 g | C | 2-3 wk | juicy, sticky | DUN | 4 |
| banana | Banana | fruit | whole, curved | 30 x 150-200 mm, 120-180 g | A | 3-5 d | bruises, spotted, peel slips | DUN | 3 |
| strawberry | Strawberry / Erdbeere | fruit | whole, soft | Ø 20-40 mm, 15-30 g | C | 2-3 d | very fragile, moulds, stains | DUN | 3 |
| pear | Pear / Birne | fruit | whole, soft when ripe | Ø 60-80 x 80-120 mm | C | 1-2 wk | bruises, ripens fast | DUN | 1 |
| rhubarb | Rhubarb / Rhabarber | fruit | stalks | Ø 20-40 x 250-400 mm | C | ~1 wk | stringy, seasonal Apr-Jun | DUN | 1 |
| stonefruit | Cherry, plum, peach / Steinobst | fruit | whole, stone | Ø 20-70 mm | C | 3-5 d (jar A 12 mo) | pits, bruises | DUN | 1 |
| pork_cutlet | Pork cutlet, chop, neck / Schnitzel, Kotelett, Nacken | meat raw | slices | 120-250 g, 8-25 mm | C | 2-3 d (F 6 mo) | slippery, sticky | DME | 5 |
| beef_cubes | Beef stew meat / Gulaschfleisch | meat raw | cubes | 25-40 mm, 20-40 g | C | 1-2 d | sticky, clumps | DME | 3 |
| beef_roast | Beef pot roast, boiling beef / Schmorbraten, Tafelspitz | meat raw | block | 1-2 kg | C | 3-4 d | heavy, drips | DME | 3 |
| veal | Veal cutlet or strips / Kalb | meat raw | slices or strips | 120-180 g | C | 2-3 d | slippery, delicate | DME | 3 |
| lamb | Lamb leg or mince / Lamm | meat raw | leg 1.5-2 kg or mince | 1.5-2 kg | C | 3 d | strong fat | DME | 2 |
| pork_roast | Pork roast with rind / Schweinebraten | meat raw | block with rind and bone | 1.5-2.5 kg | C | 3 d | heavy, hard rind | DME | 2 |
| pork_strips | Pork/turkey strips (Gyros, Geschnetzeltes), marinated | meat raw | strips in brine/marinade | 5 x 10 x 60 mm | C | 2 d | wet, sticky, marinade drips | DME | 2 |
| beef_roulade | Beef roulade slices / Rinderroulade | meat raw | flat slices | 150-200 g, 4-8 mm thick, 12 x 20 cm | C | 2-3 d (F 3 mo) | slippery, sticky, tears, drips | DME | 1 |
| beef_steak | Beef steak / Rumpsteak | meat raw | slab | 200-300 g, 20-30 mm | C | 3-4 d | drips, tempering needed | DME | 1 |
| liver | Liver / Leber (calf, pork) | meat raw | slices | 100-150 g, 5-10 mm | C | 1 d | perishable, slippery, veins | DME | 1 |
| pork_knuckle | Pork knuckle / Eisbein, Haxe | meat raw | bone-in | 0.8-1.5 kg | C | 3 d | awkward shape | DME | 1 |
| pork_tender | Pork tenderloin / Schweinefilet | meat raw | long tapered | Ø 40-60 x 250-350 mm, 300-500 g | C | 3 d | silverskin, slippery | DME | 1 |
| ribs | Pork ribs / Spareribs | meat raw | racks with bone | 0.8-1.2 kg | C | 3 d | membrane, bones, long | DME | 1 |
| mince_mixed | Mixed minced meat (beef+pork) / Gehacktes halb-halb | minced | paste-like mass | 250-1000 g | C fresh / F | 1 d fresh, 3 d vacuum; F 3 mo | most perishable item, sticky, smears, drips, must be cold | DME | 14 |
| mince_beef | Beef mince / Rinderhack | minced | paste-like mass | 250-1000 g | C / F | 1 d fresh; F 3 mo | as above | DME | 5 |
| bacon | Bacon, Speck | meat cured | slices or block | 1-2 mm slices; block 200 g | C | 2-3 wk | greasy, slices stick together | DME | 16 |
| ham | Cooked ham, cold cuts / Schinken, Aufschnitt | meat cured | slices | 1-2 mm, 15-20 g each | C | 3-5 d opened | stack sticks together, dries out | DME | 12 |
| sausage_cooked | Cooked sausage / Wiener, Bockwurst, Saitenwurst | meat cured | links | Ø 20-28 x 100-200 mm | C | 5-7 d | greasy, brine-wet | DME | 9 |
| sausage_cured | Cured sausage / Salami, Mettwurst, Pinkel | meat cured | links or slices | Ø 30-60 mm | C | 2-4 wk | greasy, hard casing | DME | 3 |
| sausage_raw | Raw sausage / Bratwurst | meat cured | links | Ø 22-28 x 120-180 mm, 80-150 g | C | 3 d (F 3 mo) | casing splits, slippery, greasy | DME | 2 |
| kassler | Kassler (smoked pork chop) | meat cured | slab | 150-250 g slices or 1 kg piece | C | 1-2 wk | brine-wet | DME | 1 |
| chicken_breast | Chicken breast fillet / Haehnchenbrust | poultry | fillet | 150-250 g | C | 2 d (F 9 mo) | salmonella, slippery | DME | 10 |
| chicken_thigh | Chicken thigh, drumstick / Keule, Schenkel | poultry | bone-in pieces | 150-300 g | C | 2 d (F 9 mo) | salmonella, bone | DME | 8 |
| chicken_whole | Whole chicken / Haehnchen | poultry | whole bird | 1.2-1.8 kg | C | 2 d (F 9 mo) | salmonella, awkward shape, drips | DME | 1 |
| duck_goose | Goose / duck | poultry | whole bird | 2-5 kg | C or F | 2 d (F 9 mo) | very large, fat | DME | 1 |
| salmon | Salmon fillet / Lachs | fish | fillet, skin on | 150-200 g, 25-40 mm | C or F | C 1-2 d; F 3 mo | fragile, flakes, slippery, odour | DME | 4 |
| shrimp | Shrimp, frozen peeled / Garnelen | fish | frozen curled | 20-40 mm | F | 12 mo | clumps, thaw drip | DSO | 3 |
| whitefish | White fish fillet / Kabeljau, Seelachs | fish | fillet | 120-180 g | F (or C) | F 6 mo; C 1 d | very fragile, releases water | DME | 3 |
| trout | Trout, whole / Forelle | fish | whole fish | 300-400 g | C | 1 d | slippery, scales, odour | DME | 2 |
| herring | Herring fillets / Matjes, Hering | fish | fillets in brine or oil | 60-100 g each | C | 2-4 wk closed | slippery, salty, odour | DME | 1 |
| egg | Egg / Hühnerei | egg | whole ovoid | 44 x 57 mm, 53-63 g | C | 28 d from laying | fragile shell, salmonella, sticky when broken | DUN | 82 |
| cream | Cream / Sahne (30-36 %) | dairy liquid | liquid, foams | 5-500 ml | C | closed 1-2 wk; opened 3 d | whips when overworked, splashes | DLI | 40 |
| milk | Milk / Milch | dairy liquid | liquid | 5-2000 ml | C (UHT closed: A) | opened 3-4 d; UHT closed 3-6 mo | foams, scorches, splashes | DLI | 39 |
| sourcream | Schmand, Creme fraiche, sour cream | dairy viscous | viscous | 150-250 g | C | 2-3 wk closed | curdles when boiled | DVI | 11 |
| yoghurt | Yoghurt | dairy viscous | viscous | 150-500 g | C | 2-3 wk closed | sticky | DVI | 11 |
| quark | Quark | dairy viscous | viscous curd | 250-500 g | C | ~2 wk closed | sticky, separates | DVI | 5 |
| creamcheese | Cream cheese, mascarpone, ricotta | dairy viscous | viscous | 200-500 g | C | 1-2 wk closed | sticky | DVI | 4 |
| butter | Butter | dairy block | block | 250 g | C | 4-6 wk (F 6 mo) | hard when cold, smears, melts 30 C | DBL | 94 |
| cheese_semi | Gouda, Emmentaler, mountain cheese | dairy block | block or slices | 200-500 g | C | 2-4 wk | greasy, slices stick | DBL | 21 |
| cheese_hard | Parmesan, hard cheese | dairy block | block/wedge | 200-500 g | C | 4-8 wk | hard, dry | DBL | 14 |
| mozzarella | Mozzarella | dairy block | ball in brine | 125 g ball | C | 3-5 d opened | slippery, wet | DUN | 5 |
| feta | Feta / Schafskaese | dairy block | block in brine | 200 g | C | 2-3 wk | crumbles, brine | DBL | 3 |
| cheese_grated | Grated cheese (pre-grated) | dairy block | granular, clumpy | 150-250 g bag | C | 1-2 wk | clumps, moulds | DSO | 2 |
| paneer | Paneer, halloumi | dairy block | block | 200-250 g | C | 2-3 wk closed | brine, squeaky, fragile when hot | DBL | 1 |
| tofu | Tofu | protein | block in water | 250-400 g | C | 5-7 d opened | fragile, wet | DBL | 3 |
| rice_long | Rice (long grain, basmati, jasmine) | grain | granular | Ø 2 x 6-8 mm | A | 12-24 mo | starch dust, free-flowing | DSO | 22 |
| pasta_dry | Pasta, dry (long, short, sheets) | grain | brittle sticks or shapes | spaghetti 250 mm; shapes 10-40 mm | A | 24 mo | long strands break/tangle, sheets stack | DSO | 15 |
| oats | Oats, muesli / Haferflocken | grain | flakes | Ø 10-15 mm, light | A | 6-12 mo | light, dusty, bridges in hopper | DSO | 5 |
| rice_round | Rice (milk rice, risotto, paella, sushi) | grain | granular | Ø 3 x 5 mm | A | 12-24 mo | starch dust, free-flowing | DSO | 4 |
| noodles_asian | Rice or egg noodles | grain | brittle nests/sticks | nests 50 mm | A | 24 mo | brittle | DSO | 3 |
| couscous | Couscous, bulgur | grain | granular | 1-3 mm | A | 12 mo | free-flowing | DSO | 2 |
| pasta_fresh | Fresh pasta, gnocchi, tortellini, Maultaschen | grain | soft pieces | 10-100 mm | C | 1-2 wk (vacuum 4 wk) | sticky, fragile, clump | DSO | 2 |
| lasagne_sheets | Lasagne sheets | grain | flat dry sheets | 100 x 200 mm | A | 24 mo | brittle, fragile | DUN | 1 |
| flour_wheat | Wheat flour / Mehl (405, 550, 1050) | baking | powder | fine <200 um | A | 6-12 mo | dust, clumps when humid, bugs | DPO | 74 |
| yeast | Yeast (fresh cube or dry) | baking | crumbly block or granular | 42 g cube / 7 g sachet | C fresh / A dry | 3 wk / 12 mo | dies at >45 C | DBL | 11 |
| bakingpowder | Baking powder, baking soda | baking | powder | fine | A | 12 mo | clumps, moisture | DPO | 9 |
| breadcrumbs | Breadcrumbs / Paniermehl | baking | granular | 1-2 mm | A | 12 mo | absorbs moisture, clumps | DSO | 9 |
| cornstarch | Cornstarch, potato starch / Staerke | baking | powder | fine | A | 24 mo | clumps in liquid, dust | DPO | 7 |
| semolina | Semolina, polenta, Griess | baking | granular | 0.2-0.8 mm | A | 12 mo | clumps in liquid | DSO | 4 |
| pudding_powder | Pudding powder / Puddingpulver | baking | powder | - | A | 18 mo | clumps in liquid | DPO | 3 |
| flour_other | Rye, wholemeal, spelt flour | baking | powder | coarser | A | 3-6 mo | rancid, dust | DPO | 2 |
| gelatine | Gelatine (leaf or powder) | baking | leaf / powder | - | A | 24 mo | needs soaking, clumps | DUN | 1 |
| sourdough | Sourdough starter | baking | viscous culture | 50-200 g | C | indefinite with weekly feeding | needs feeding, gas builds up | DVI | 1 |
| bread | Bread, rolls, stale bread / Brot, Broetchen | baked | loaf or rolls | Ø 60-80 mm rolls; loaf 500-1000 g | A | 2-5 d; F 3 mo | crumbs, moulds, dries | DUN | 15 |
| tortilla | Tortillas, wraps, taco shells | baked | flat discs / shells | Ø 20-30 cm | A / C | 2-4 wk | sticky stack, shells break | DUN | 5 |
| buns | Burger buns, pita, flatbread | baked | soft round/flat | Ø 90-250 mm | A / C | 3-5 d (F) | squashes, dries | DUN | 4 |
| toastbread | Sliced toast / Toastbrot | baked | slices | 100 x 100 x 10 mm | A | ~1 wk opened | sticky when moist, tears | DUN | 4 |
| wrapper | Spring-roll, dumpling wrappers, rice paper | baked | thin sheets | Ø 90-200 mm | C | 2-4 wk | dries out, tears, sticks | DUN | 2 |
| sponge_biscuit | Sponge fingers, biscuits / Loeffelbiskuit, Butterkeks | baked | brittle pieces | 100 x 30 mm | A | 6-12 mo | brittle, absorb moisture | DUN | 1 |
| pastry_dough | Ready dough (puff pastry, shortcrust, pizza) | dough | rolled sheet | 260 x 420 mm, 270 g | C | 4-6 wk (F 6 mo) | sticky when warm, must be cold | DUN | 1 |
| sugar | Sugar (granulated, brown, icing) / Zucker | sweet | granular / powder | granulated 0.5 mm; icing fine | A | indefinite | hygroscopic, clumps; icing sugar dusts | DSO | 61 |
| vanilla | Vanilla sugar, extract | sweet | powder / liquid | - | A | 24 mo | strong aroma | DPO | 21 |
| honey | Honey, syrup / Honig | sweet | viscous | 5-50 g | A | 24 mo | very sticky, crystallises | DVI | 8 |
| cocoa | Cocoa powder / Kakao | sweet | powder | fine | A | 24 mo | dust, clumps | DPO | 6 |
| chocolate | Chocolate, couverture / Schokolade | sweet | bars, chips | bar 100 g | A (<24 C) | 12 mo | melts above 28 C, blooms | DBL | 5 |
| jam | Jam / Marmelade | sweet | viscous with pieces | 10-200 g | A / C opened | 12 mo (opened 4 wk) | sticky, pieces | DVI | 4 |
| marzipan | Marzipan | sweet | block | 200 g | A | 6 mo | sticky, hard | DBL | 1 |
| nuts | Nuts (almond, walnut, hazelnut, peanut) | nut/seed | whole or ground | Ø 8-30 mm | A | 3-6 mo (fat turns rancid) | dust, rolls; ground: clumps | DSO | 9 |
| seeds | Seeds, pine nuts, sesame | nut/seed | granular | Ø 2-15 mm | A | 3-6 mo | small, oily | DSO | 6 |
| lentils | Lentils (dried) / Linsen | legume | granular | Ø 3-6 mm | A | 24 mo | dust, small stones, free-flowing | DSO | 3 |
| beans_dry | Beans, peas (dried) / Bohnen, Erbsen | legume | granular hard | Ø 6-12 mm | A | 24 mo | hard, need 12 h soak | DSO | 1 |
| chickpeas_dry | Chickpeas (dried) / Kichererbsen | legume | granular hard | Ø 8-10 mm | A | 24 mo | need 12 h soak | DSO | 1 |
| tomato_can | Canned tomatoes, passata / Dosentomaten | canned | chunks in juice or puree | 400 g can, 700 ml | A | 24 mo (opened C 3 d) | stains, splashes, acid | DVI | 23 |
| tomato_paste | Tomato paste / Tomatenmark | canned | viscous paste | 70-200 g tube | A (opened C) | 24 mo (opened 2 wk) | stains, sticky | DVI | 12 |
| beans_can | Beans, canned (kidney, white) | canned | beans in brine | 400 g can | A | 24 mo | brine, foaming | DVI | 4 |
| coconutmilk | Coconut milk | canned | liquid/viscous | 400 ml can | A | 24 mo | separates, must shake | DVI | 4 |
| chickpeas_can | Chickpeas, canned | canned | in brine | 400 g can | A | 24 mo | brine, foaming | DVI | 2 |
| corn_can | Sweetcorn, canned | canned | kernels in brine | 340 g can | A | 24 mo | brine | DVI | 2 |
| pineapple_can | Pineapple, canned | canned | rings/chunks in juice | 400 g | A | 24 mo | sticky | DVI | 2 |
| tuna_can | Tuna, canned / Thunfisch | canned | chunks in oil/brine | 150 g can | A | 3 yr | oil/brine drip | DVI | 2 |
| peas_fz | Peas, frozen / TK-Erbsen | frozen | frozen granular | Ø 8 mm | F | 12 mo | free-flowing when frozen, clump when thawed | DSO | 9 |
| spinach_fz | Spinach, frozen (leaf or creamed) | frozen | frozen block or pellets | 450 g block | F | 12 mo | freezes to a block; needs thawing | DBL | 4 |
| fishsticks | Fish fingers / Fischstaebchen (frozen) | frozen | rectangular sticks | 20 x 25 x 90 mm, 28 g | F | 12 mo | free-flowing when frozen, breaks | DUN | 1 |
| veg_fz | Mixed vegetables, frozen | frozen | frozen pieces, mixed | 5-20 mm | F | 12 mo | free-flowing, thaw wet | DSO | 1 |
| salt | Salt / Salz | spice | granular | fine 0.5 mm; coarse 2 mm | A | indefinite | hygroscopic, caking, corrosive to metal | DSO | 188 |
| pepper | Pepper (whole) / Pfeffer | spice | whole peppercorns | Ø 4-5 mm | A | 24 mo | grind at time of use | DSO | 108 |
| nutmeg | Nutmeg | spice | whole nut or powder | Ø 25 mm | A | 24 mo | grate at time of use | DUN | 24 |
| spice_curry | Curry, garam masala, chili, cumin (ground), saffron | spice | fine powder | - | A | 12 mo | stains, clumps, dust | DPO | 24 |
| dried_herbs | Dried herbs (oregano, thyme, marjoram, bay leaf) | spice | flakes | - | A | 12 mo | light, fluffy, bridging | DPO | 22 |
| paprika_pw | Paprika powder | spice | fine powder | - | A | 12 mo | dust, stains, burns in hot fat | DPO | 18 |
| cinnamon | Cinnamon | spice | powder or sticks | - | A | 12 mo | dust | DPO | 12 |
| spice_whole | Whole spices (juniper, cloves, cumin seed, mustard seed) | spice | granular | Ø 2-8 mm | A | 24 mo | small, hard | DSO | 9 |
| stock | Stock (powder, paste, liquid) / Bruehe | condiment | powder / paste / liquid | - | A | 12-24 mo | salty, hygroscopic | DPO | 49 |
| vinegar | Vinegar (wine, balsamic, apple) | condiment | liquid | 5-100 ml | A | 24 mo | acidic, corrosive to some metals | DLI | 24 |
| mustard | Mustard / Senf | condiment | paste | 5-50 g | A / C | 12 mo | sticky | DVI | 23 |
| pickles | Gherkins, capers, olives, anchovies (jarred) | condiment | pieces in brine | Ø 10-40 mm | A / C opened | 24 mo (opened 4-8 wk) | brine drip, slippery | DUN | 14 |
| soysauce | Soy sauce, Worcestershire, Maggi, fish sauce | condiment | liquid | 5-50 ml | A | 24 mo (opened 12) | stains, salty, corrosive | DLI | 11 |
| ketchup | Ketchup, BBQ sauce | condiment | viscous | 20-200 g | A / C | 6 mo opened | sticky, stains | DVI | 7 |
| chilipaste | Curry paste, harissa, sambal | condiment | viscous | 20-100 g | A / C opened | 12 mo | stains, capsaicin | DVI | 5 |
| mayo | Mayonnaise, remoulade | condiment | viscous | 20-200 g | C opened | 3 mo opened | sticky, separates when frozen | DVI | 5 |
| nori | Nori seaweed sheets | condiment | thin dry sheets | 190 x 210 mm | A | 12 mo | absorbs moisture, brittle | DUN | 3 |
| horseradish | Horseradish (jar) / Meerrettich | condiment | viscous | 10-50 g | C opened | 4 wk | pungent | DVI | 2 |
| miso | Miso paste | condiment | viscous | 20 g | C | 12 mo | salty | DVI | 2 |
| pesto | Pesto (jar) | condiment | viscous with pieces | 190 g jar | C opened | 1-2 wk opened | oily, sticky | DVI | 1 |
| tahini | Tahini, peanut butter | condiment | very viscous, separates | 20-100 g | A | 12 mo | oil separates | DVI | 1 |
| oil_veg | Vegetable / sunflower / rapeseed oil | oil/fat | liquid | 5-500 ml | A | 12 mo | drips, polymerises to sticky film | DLI | 74 |
| oil_olive | Olive oil | oil/fat | liquid | 5-200 ml | A | 18 mo | drips | DLI | 40 |
| fat_solid | Lard, margarine, ghee, coconut fat | oil/fat | solid, softens | 250 g | A / C | 3-12 mo | softens at 25-30 C | DBL | 5 |
| water | Water / Wasser | liquid | liquid (pipe) | 0.1-9 L | pipe | - | limescale | DLI | 58 |
| wine_red | Red wine / Rotwein | liquid | liquid | 50-500 ml | A (opened C) | opened 5-7 d | stains | DLI | 12 |
| wine_white | White wine / Weisswein | liquid | liquid | 50-300 ml | A (opened C) | opened 5-7 d | - | DLI | 12 |
| spirits | Rum, kirsch, liqueur | liquid | liquid | 5-50 ml | A | indefinite | flammable, 40 % vol | DLI | 3 |
| juice | Fruit juice / Saft | liquid | liquid | 50-500 ml | A / C opened | closed 12 mo; opened 5 d | sticky | DLI | 2 |
| sauerkraut | Sauerkraut | preserved | wet shreds in brine | 500 g-1 kg | A closed / C opened | closed 12 mo; opened 1-2 wk | wet, sour, odour, corrosive | DVI | 3 |

### 5.1 Storage classes

| Primary storage class | Ingredient types | Share of types | Meal-uses (sum of n) |
|---|---|---|---|
| A ambient | 69 | 38 % | 1083 |
| A* ambient cool-dark | 5 | 3 % | 202 |
| C fridge | 97 | 54 % | 782 |
| F freezer | 8 | 4 % | 29 |
| pipe (water) | 1 | 1 % | 58 |

Several ingredients are sold frozen or fresh (kale, berries, spinach, shrimp, fish, minced meat): the user decides at ingestion, so the storage system must allow the same ingredient in fridge or freezer. Raw mince, poultry, fish, liver, leafy salad, herbs, mushrooms, strawberries, sprouts and asparagus last only 1-5 days in the fridge and will spoil unless the machine cooks them in time or the user plans purchases.

### 5.2 Dosing classes

| Dose op | Meaning | Ingredient types | Meal-uses |
|---|---|---|---|
| DSO | dose free-flowing solids | 25 | 483 |
| DPO | dose powder / spice pinch | 12 | 247 |
| DLI | dose thin liquids | 11 | 315 |
| DVI | dose viscous / sticky | 24 | 144 |
| DUN | dispense countable whole items | 68 | 685 |
| DBL | portion block solids | 11 | 162 |
| DME | dispense raw meat / fish pieces | 29 | 118 |

### 5.3 Most frequent ingredients (top 40)

| Rank | Key | n | % of meals |
|---|---|---|---|
| 1 | salt | 188 | 76 % |
| 2 | onion | 112 | 45 % |
| 3 | pepper | 108 | 44 % |
| 4 | butter | 94 | 38 % |
| 5 | egg | 82 | 33 % |
| 6 | flour_wheat | 74 | 30 % |
| 7 | oil_veg | 74 | 30 % |
| 8 | sugar | 61 | 25 % |
| 9 | water | 58 | 23 % |
| 10 | stock | 49 | 20 % |
| 11 | garlic | 44 | 18 % |
| 12 | potato | 44 | 18 % |
| 13 | cream | 40 | 16 % |
| 14 | oil_olive | 40 | 16 % |
| 15 | milk | 39 | 16 % |
| 16 | lemon | 33 | 13 % |
| 17 | carrot | 32 | 13 % |
| 18 | bellpepper | 27 | 11 % |
| 19 | nutmeg | 24 | 10 % |
| 20 | parsley | 24 | 10 % |
| 21 | spice_curry | 24 | 10 % |
| 22 | vinegar | 24 | 10 % |
| 23 | mustard | 23 | 9 % |
| 24 | tomato_can | 23 | 9 % |
| 25 | dried_herbs | 22 | 9 % |
| 26 | rice_long | 22 | 9 % |
| 27 | cheese_semi | 21 | 8 % |
| 28 | vanilla | 21 | 8 % |
| 29 | tomato | 20 | 8 % |
| 30 | apple | 18 | 7 % |
| 31 | paprika_pw | 18 | 7 % |
| 32 | bacon | 16 | 6 % |
| 33 | bread | 15 | 6 % |
| 34 | pasta_dry | 15 | 6 % |
| 35 | cheese_hard | 14 | 6 % |
| 36 | mince_mixed | 14 | 6 % |
| 37 | pickles | 14 | 6 % |
| 38 | cinnamon | 12 | 5 % |
| 39 | ginger | 12 | 5 % |
| 40 | ham | 12 | 5 % |

### 5.4 How many ingredient types are needed for a share of the corpus

Greedy selection of ingredient types that completes the most meals (a meal counts only if all its ingredients are stocked; salt, water, oil included):

| Share of meals | Ingredient types needed | of total |
|---|---|---|
| 25 % | 53 | 180 |
| 50 % | 87 | 180 |
| 80 % | 131 | 180 |
| 90 % | 154 | 180 |
| 95 % | 166 | 180 |
| 99 % | 176 | 180 |
| 100 % | 180 | 180 |

Monte-Carlo check (3000 draws, meals drawn proportional to weight W, salt/water/oil included): a week of 7 dinners uses 38 ingredient types on average (10-90 % range 32-44), two weeks of 14 dinners use 58 (50-65). Stocking only the 30 most frequent ingredients completes 8 % of the corpus, the top 60 25 %.

Consequence for storage design: the full repertoire needs 180 ingredient types (74 ambient, 97 fridge, 8 freezer as primary class, many of them optional frozen alternatives), but one household stocks 40-60 at a time. The grid must therefore offer free assignment of ingredient to box (not fixed compartments per ingredient) with a stock of the order of 100-180 boxes for a fully stocked machine; R3 sizes the grid and the box variants (small boxes for the 12 powder/spice types, large boxes for produce).

### 5.5 Physical envelope of whole items (drives box, funnel and gripper sizes)

| Item | Envelope (mm / kg) |
|---|---|
| Largest round produce | Ø 250 mm, 2 kg (pumpkin, cabbage head); Ø 150-220 mm typical for celeriac, cauliflower |
| Longest produce | cucumber 400, rhubarb 400, leek 350, celery 300, asparagus 250, spaghetti 250 (dry pasta up to 260) |
| Smallest items to singulate | peas 8 mm, rice 2 x 7, lentils 4, cloves 10-30 mm, spice pinch 0.2 g |
| Whole poultry | chicken 1.2-1.8 kg (about 350 x 200 x 150 mm); goose 4-5 kg (about 450 x 250 x 200 mm) |
| Meat joints | pork roast with rind 1.5-2.5 kg (250 x 150 x 120 mm), pot roast 1-2 kg, ribs rack 300 x 150 mm |
| Flat meat | cutlets 120-250 g at 8-25 mm; Rouladen 120 x 200 mm, 4-8 mm |
| Eggs | 44 x 57 mm, 53-63 g, 1-12 per meal |
| Bread | loaf 250 x 120 x 100 mm, 500-1000 g; rolls Ø 60-80 mm |
| Cans and jars | Ø 73-100 mm, 400-850 ml; jar 190-720 ml |
| Fresh pasta packs | 150 x 100 mm, 250-500 g |

## 6. Typical quantities

### 6.1 Portion sizes per person and totals for 1-6 people

Typical raw masses per person (range from Swissmilk, EAT SMARTER, DGE guidance; the typical value is the author's choice within the range, for a cooked main meal at normal appetite). The last column is the volume of 6 portions as loaded into a vessel, computed with assumed bulk densities between 0.08 kg/L (loose salad leaves) and 1.0 kg/L (meat, liquids); these densities are estimates.

| Component | Typical g per person | Range | 1 | 2 | 3 | 4 | 5 | 6 | Volume at 6 persons (L) |
|---|---|---|---|---|---|---|---|---|---|
| Meat, boneless raw (cutlet, steak, Roulade) | 150 | 120-200 | 150 | 300 | 450 | 600 | 750 | 900 | 0.9 |
| Meat, bone-in (chicken legs, ribs, knuckle) | 300 | 250-400 | 300 | 600 | 900 | 1200 | 1500 | 1800 | 3.0 |
| Whole poultry (fraction of bird) | 350 | 300-450 | 350 | 700 | 1050 | 1400 | 1750 | 2100 | 5.2 |
| Roast joint, boneless | 180 | 150-220 | 180 | 360 | 540 | 720 | 900 | 1080 | 1.1 |
| Roast joint with bone/rind | 280 | 250-350 | 280 | 560 | 840 | 1120 | 1400 | 1680 | 2.1 |
| Mince for patties, balls, loaf | 130 | 100-160 | 130 | 260 | 390 | 520 | 650 | 780 | 0.8 |
| Mince for sauce (Bolognese, chili) | 100 | 80-125 | 100 | 200 | 300 | 400 | 500 | 600 | 0.6 |
| Sausage | 150 | 100-200 | 150 | 300 | 450 | 600 | 750 | 900 | 1.1 |
| Fish fillet | 150 | 120-200 | 150 | 300 | 450 | 600 | 750 | 900 | 1.0 |
| Shrimp | 100 | 80-125 | 100 | 200 | 300 | 400 | 500 | 600 | 0.9 |
| Eggs as main or breakfast (2 pieces) | 110 | 55-165 | 110 | 220 | 330 | 440 | 550 | 660 | 0.7 |
| Potatoes raw, unpeeled, side dish | 250 | 200-300 | 250 | 500 | 750 | 1000 | 1250 | 1500 | 2.3 |
| Potatoes as main (gratin, Puffer, salad) | 350 | 300-400 | 350 | 700 | 1050 | 1400 | 1750 | 2100 | 3.2 |
| Potatoes for fries (raw) | 300 | 250-350 | 300 | 600 | 900 | 1200 | 1500 | 1800 | 2.8 |
| Rice dry, side | 70 | 50-80 | 70 | 140 | 210 | 280 | 350 | 420 | 0.5 |
| Rice dry, main (risotto, paella, pan) | 90 | 75-100 | 90 | 180 | 270 | 360 | 450 | 540 | 0.6 |
| Pasta dry, main | 100 | 80-125 | 100 | 200 | 300 | 400 | 500 | 600 | 1.5 |
| Pasta dry, side or soup | 60 | 50-80 | 60 | 120 | 180 | 240 | 300 | 360 | 0.9 |
| Fresh pasta / gnocchi / tortellini | 150 | 125-200 | 150 | 300 | 450 | 600 | 750 | 900 | 1.5 |
| Dumplings (2-3 pieces) raw mass | 200 | 150-250 | 200 | 400 | 600 | 800 | 1000 | 1200 | 1.2 |
| Spätzle (flour + egg) raw batter | 150 | 120-180 | 150 | 300 | 450 | 600 | 750 | 900 | 0.9 |
| Vegetables raw, side | 200 | 150-250 | 200 | 400 | 600 | 800 | 1000 | 1200 | 3.0 |
| Vegetables raw, main or casserole | 400 | 350-450 | 400 | 800 | 1200 | 1600 | 2000 | 2400 | 6.0 |
| Cabbage raw (red, white, savoy), side | 200 | 150-250 | 200 | 400 | 600 | 800 | 1000 | 1200 | 4.0 |
| Salad leaves raw | 80 | 50-100 | 80 | 160 | 240 | 320 | 400 | 480 | 6.0 |
| Salad vegetables (tomato, cucumber, pepper) | 120 | 100-150 | 120 | 240 | 360 | 480 | 600 | 720 | 1.4 |
| Soup, starter (ml) | 300 | 250-350 | 300 | 600 | 900 | 1200 | 1500 | 1800 | 1.8 |
| Soup, main (ml) | 450 | 400-500 | 450 | 900 | 1350 | 1800 | 2250 | 2700 | 2.7 |
| Stew (Eintopf) (ml) | 550 | 450-600 | 550 | 1100 | 1650 | 2200 | 2750 | 3300 | 3.3 |
| Sauce / gravy (ml) | 80 | 60-120 | 80 | 160 | 240 | 320 | 400 | 480 | 0.5 |
| Cream or milk in a dish (ml) | 50 | 30-100 | 50 | 100 | 150 | 200 | 250 | 300 | 0.3 |
| Dessert (pudding, mousse, rice pudding) | 180 | 120-250 | 180 | 360 | 540 | 720 | 900 | 1080 | 1.1 |
| Cake (1/12 of a 26 cm springform) | 120 | 100-150 | 120 | 240 | 360 | 480 | 600 | 720 | 1.4 |
| Bread (2 slices) / loaf share | 100 | 80-120 | 100 | 200 | 300 | 400 | 500 | 600 | 2.0 |
| Pizza, one 30 cm pizza (dough + topping) | 400 | 350-450 | 400 | 800 | 1200 | 1600 | 2000 | 2400 | 4.0 |
| Frying oil, shallow (ml) | 15 | 10-25 | 15 | 30 | 45 | 60 | 75 | 90 | 0.1 |
| Cheese for topping/grating | 35 | 20-50 | 35 | 70 | 105 | 140 | 175 | 210 | 0.4 |
| Herbs, garnish | 5 | 2-10 | 5 | 10 | 15 | 20 | 25 | 30 | 0.3 |

Rules that follow from the table: all dosing must scale linearly 1-6 (dynamic range 6:1) except (a) whole units (eggs 1-12, rolls, cutlets), (b) fixed process minimums (frying oil, deep-fry oil 2-3 L fixed, roasting tray, cake tin) and (c) cooking water (pasta 1 L per 100 g dry with a minimum of 1.5 L; potatoes just covered).

### 6.2 Plate composition

| Plate | Composition | Mass on plate |
|---|---|---|
| Main course with meat | 150 g meat (cooked ~110 g) + 200 g starch (cooked) + 150 g vegetable + 80 ml sauce | 550-650 g |
| Pasta main | 100 g dry pasta (cooked ~250 g) + 150 g sauce + 10 g cheese | 400-450 g |
| Soup main | 450 ml | 450-500 g |
| Breakfast | 2 eggs or 2 pancakes + bread 80 g | 250-350 g |
| Dessert or cake | 1 slice or 180 g | 120-250 g |

### 6.3 Vessel volumes for 6 people (maximum) and minimum fill

Working volume = content + headspace/foam; nominal volume adds a safety margin for stirring. The minimum is the smallest amount for which the vessel still heats, stirs and senses (1 person). Estimates.

| Vessel | Use | Content at 6 persons | Nominal volume | Minimum fill (1 person) | Remarks |
|---|---|---|---|---|---|
| Pasta / large boil pot | pasta, stock, Tafelspitz, blanching | 6 L water + 0.6 L pasta, foam +30 % | 9 L (8.6 L calc.) | 1.5 L water for 100 g pasta | 2 sizes needed or one 9 L pot with induction sensor min fill 1.5 L; 5.5-6 L if water ratio 700 ml/100 g is accepted |
| Potato / vegetable pot | potatoes, dumplings, green beans, asparagus (long: 250 mm) | 1.5 kg potatoes (2.3 L) + 1.4 L water | 4 L | 250 g potatoes + 0.4 L water in 1.5 L | asparagus needs a pot of at least 250 mm inner length or a lay-flat pan |
| Rice / couscous pot | absorption cooking | 420 g rice dry + 0.85 L water; cooked 1.6 L | 2.5 L | 70 g rice + 140 ml water in 0.5 L | tight-fitting lid, sensor for boil-dry |
| Soup / stew pot | soups, stews, Gulasch, chili, curry | 3 L stew + 30 % headspace | 4-5 L (6 L for 8 persons) | 0.3 L in 1.5 L pot | hot blending needs 40 % headspace or splash guard |
| Sauce pot | béchamel, gravy, hollandaise, custard | 0.5-0.8 L | 1.5 L | 0.15 L in 0.5 L pot | stirring scraper reaching the bottom edge; small radius for 1 person |
| Braiser (oven and hob) | Rouladen, Sauerbraten, Gulasch, Kohlrouladen, Coq au vin | 12 Rouladen (1.8 kg) + 1.2 L liquid + 0.4 L vegetables | 6 L, oval 320 x 240 x 110 mm, oven-safe lid | 2 Rouladen + 0.3 L | must go from hob to oven or be heated in place; wall 3-4 mm |
| Frying pan | cutlets, steak, patties, pancakes, potatoes | 28 cm: 2 cutlets, 4 patties, 1 pancake, 300 g fried potatoes | 28 cm, 36 cm for Bratkartoffeln (6 portions = 1.5 kg) | 1 cutlet, 1 egg | 6 persons = 3 batches; keep-warm at 70-80 C for 20 min required |
| Wok | stir-fry, fajitas, fried rice | 0.8 kg food | 36 cm, 5 L | 0.2 kg | 3.5 kW class heat source, tossing motion |
| Deep fryer | fries, Backfisch, Krapfen, falafel | 3 batches of 500 g fries | 2-3 L oil, 4 L vessel | one batch of 250 g fries | oil filtration/ replacement, safe lid and extraction, cleaning cycle |
| Mixing bucket | dough, batter, mince mass, salad, dumpling mass | dough 1.6 kg (1 kg flour) rising to 4-5 L; 6 egg whites whipped 1.5 L; salad 1.2 kg leaves ~ 5 L; Spätzle batter 1.2 L; mince mass 1 kg | 8 L working, 10 L nominal | 1 egg white (30 ml) whipped; 100 g dough | one bucket cannot whip 1 egg white and knead 1 kg dough: needs interchangeable small/large inserts (D4) |
| Roasting tray / oven cavity | roast, poultry, Ofengemüse, goose | pork roast 1.7 kg (250 x 150 x 120 mm); chicken 1.6 kg; goose 5 kg (450 x 250 x 200 mm) | tray 400 x 300 x 60 mm, oven >= 45 L, cavity 450 x 400 x 250 mm | 1 chicken leg | goose is the largest single item; treat as edge case if the oven is smaller |
| Baking moulds and trays | cakes, bread, casseroles, pizza | springform 26 cm (12 slices, 1.2 L batter), sheet 400 x 300 mm (16 pieces), loaf tin 300 mm, gratin 30 x 20 x 6 cm (2.4 L), muffin 12 x 100 ml, pizza 320 mm | as listed | - | cakes do not scale to 1 person: half cake or freeze slices |

## 7. Implications for the design documents

1. **Foundation tier (all 98 operations with D<=3; the widespread D3 operations are DUN, DME, PLT, WLF, CRK)** must be complete before any percentage can be claimed. On its own it covers 12 % of meals in S0 and 61 % in S1.
2. **Peeling of onion/garlic (PLA)** touches 52 % of meals: start with purchase of peeled or frozen forms (R7 ingestion must recognise them) and treat the peeler as an upgrade module.
3. **Hard operations without a purchase workaround** (FLP 12.9 %, ASM 6.9 %, CAR 4.8 %, UNM 4.4 %, SCO 2.8 %, POA 0.4 %; union 29.0 % of meals) need real mechanisms. The shaping cluster (STU, WRP, FRM, SHD, BRD, RLT, SKW: 15.3 % of meals) can be avoided only with semi-finished products.
4. **Rouladen** (RLT, D5) is named explicitly by the customer; R4/D4 should evaluate a mould/press-based roulade roller with pins or clips, which would also serve Kohlrouladen, wraps and poultry closing. Purchase workaround: ready-rolled Rouladen from the butcher counter.
5. **Dough** (KND, PRF, ROL, SHD, SCO, BKE) is needed by 17 meals (7 %): bread, pizza, Flammkuchen, cakes, pastry. Dough shaping is D4 and scales poorly to one portion. A dough sheeter plus press plate covers pizza, Flammkuchen and Muerbeteig; loaf shaping and braiding need a separate decision.
6. **Heat sources**: 4 hob zones, 1 oven >= 45 L with steam, 1 fryer, warm-hold; the power budget must be solved at architecture level.
7. **Vessels**: two boil pots (4 L and 9 L), one 6 L braiser, 28 and 36 cm pans, a wok, 1.5 L sauce pots and an 8-10 L mixing bucket with a small insert. Peak simultaneous food vessels for one menu is 6.
8. **Storage**: 180 ingredient types, of which a household holds 40-60 at a time (Section 5.4); free box assignment; the same ingredient must be storable in fridge or freezer at the user's choice; raw mince, poultry, fish, liver, leafy salad, herbs and mushrooms last only 1-5 days.

## Open issues

1. **chefkoch.de could not be fetched** from the research environment, so the corpus follows the Chefkoch Foodstudie category order, the G&U/Kuechengoetter top-100, the apetito charts and Hausmannskost collections instead of the raw Chefkoch top-recipe ranking. A revision should add a genuine cooking-frequency dataset (ratings counts of the most-rated recipes).
2. **Difficulty ratings D and avoidability levels are estimates.** All coverage numbers move with them; engineers should re-score D per operation after prototyping and re-run Appendix A. First candidates for challenge: PLA (peel onion) and FLP (flip), because they carry the largest shares.
3. **Weights W are subjective** (1-3). Weighted and unweighted coverage differ by 0-4 percentage points; the conclusions do not change, but a survey-based weighting would be better.
4. **Menu-level modelling is thin**: 15 typical menus only. A multi-dish scheduler needs a menu corpus (main + sides + dessert + drinks) with realistic combinations.
5. **Power**: the brief lists 220 V only; the peak menus need 7-8 kW (Section 4.9). Options: 3-phase 400 V (standard in German kitchens for the hob), staggered scheduling, pre-heated water/thermal storage. To be resolved in A1, D5 and D9.
6. **Scaling to one person**: cakes, bread and roasts do not scale below 3-4 portions; policy needed (bake whole and freeze slices, or smaller moulds).
7. **Seasoning to taste** and **doneness detection** are not unit operations but recur in every recipe (Section 4.8); D10 must decide sensors and recipe adaptation.
8. **Vegetarian/vegan variants**: 37 rows are vegan and 137 vegetarian by ingredient list; substitutes (tofu, plant milk, egg replacers) are not analysed.
9. **Out of corpus**: beverages, fondue and raclette (table-top), outdoor grilling, sous-vide, fermenting (sauerkraut, yoghurt), preserving.
10. **Sourdough starter** (BK02) needs a living culture in cold storage with weekly feeding; either excluded or a special box type.
11. **Liability and food-safety operations** (core temperature for poultry and mince, egg pasteurisation, lye handling for pretzels BK06) are not modelled here; R6 must define them.

## Risks

| Risk | Effect | Mitigation |
|---|---|---|
| The 95 % goal is decided by a handful of shaping and assembly operations that have no market solution at household scale (FLP, STU, WRP, SHD, BRD, RLT, ASM, UNM, CAR) | With level-1 purchases only and no D4/D5 operation built, coverage is 61 %. Building the six operations without any purchase workaround (FLP, ASM, CAR, UNM, SCO, POA) lifts it to 85 %; the remaining 15 % are the shaping cluster (STU, WRP, FRM, SHD, BRD, RLT, LSP), which can only be bought away as semi-finished products | Prototype FLP, ASM, STU, UNM, CAR, WRP first (Section 4.6); accept level-2 purchases (formed, breaded, ready-rolled) for the last 5-10 %; state per recipe which ones rely on them |
| Reliance on pre-processed ingredients shifts effort and cost to the user | 80 % of the meals covered at the foundation tier in S1 need at least one pre-processed item (mostly peeled onions/garlic), which raises running cost and weakens the traditional claim | Build the onion/garlic peeler; support frozen and pre-cut forms in ingestion (R7); mark recipe cards |
| Mince, poultry and fish last 1-3 days | Waste or food-safety incident if stored too long; salmonella cross-contamination | Freezer for these items with thaw lead time; stock-aware scheduling; HACCP concept from R6 |
| Corpus bias towards German home cooking and textbook recipes | Under-represents Asian street food, one-pot, air-fryer and modern trends | Extend rows in a revision; keep the operation taxonomy stable |
| Difficulty and avoidability ratings are subjective | Coverage curves could be off by 10 percentage points | Tables are published; re-score after R4/R5; Appendix A script |
| Ingredient diversity (180 types) drives box count and dosing hardware | A machine stocking only the 30 most frequent ingredients completes 8 % of the meals (Section 5.4) | Free box assignment; universal dosing per form class (7 dose classes); user-defined ingredients |
| Peak power and heat-source count | A design that cannot run 4 hobs and an oven simultaneously fails festive and large menus (5 of 15 typical menus need 4) | Schedule-aware cooking; power budget in A1; 3-phase connection |
| Hygiene: raw egg + raw meat + breading in one station, deep-fryer oil, mince | Cross-contamination; heavy cleaning effort | Separate raw-handling stations; CIP concept from R6; liquid pasteurised egg for breading |

## Appendix A. Recomputing the coverage numbers

The tables in Sections 2 and 3 are the dataset. The following script parses this file, derives the operation set of every meal (ordered operations plus implicit operations), and prints coverage for a given supported difficulty tier and substitution level. Change the D or av value in a row of the Section 2 tables (or the ordered operations of a meal in Section 3) and re-run to see the effect.

```python
import re, sys
rows = open(sys.argv[1], encoding='utf-8').read().split('\n')
OP = {}   # code -> (D, av)
MEALS = []  # (id, weight, set of ops)
for r in rows:
    c = [x.strip() for x in r.strip().strip('|').split(' | ')]
    if len(c) == 8 and re.fullmatch(r'[A-Z]{3}', c[0]) and c[2].isdigit():   # Section 2 rows
        OP[c[0]] = (int(c[2]), int(c[3]))
    if len(c) == 13 and re.fullmatch(r'[A-Z]{2}\d\d', c[0]):                # Section 3 rows
        ops = set(c[6].split()) | set(c[7].split())
        MEALS.append((c[0], int(c[3]), ops))
def coverage(dmax, level):
    ok = okw = 0
    for mid, wgt, ops in MEALS:
        blocked = any(OP[o][0] > dmax and not (OP[o][1] and OP[o][1] <= level) for o in ops)
        if not blocked: ok += 1; okw += wgt
    return ok / len(MEALS), okw / sum(m[1] for m in MEALS)
for level in (0, 1, 2):
    print(level, [tuple(round(100 * x, 1) for x in coverage(d, level)) for d in (2, 3, 4, 5)])
```

Usage: `python3 recompute.py research/02-meal-corpus.md`. Expected output for the values in this document is listed in Section 4.4.

## Appendix B. Build order of all operations from scratch (S0)

Cost-aware greedy (progress towards completing meals divided by D squared), starting with nothing supported; coverage counts only meals whose every operation is already supported. It shows the long tail: the last 5 % of meals need the rarest, hardest operations.

| Step | Operation | D | Coverage | Weighted |
|---|---|---|---|---|
| 1 | DSO dose free-flowing solids | 1 | 0.0 % | 0.0 % |
| 2 | DLI dose thin liquids | 1 | 0.0 % | 0.0 % |
| 3 | GRS grind spices / pepper | 1 | 0.0 % | 0.0 % |
| 4 | SIM simmer / poach gently | 1 | 0.0 % | 0.0 % |
| 5 | BOL boil (rolling boil in water) | 1 | 0.0 % | 0.0 % |
| 6 | MXW mix / stir cold or batter | 1 | 0.0 % | 0.0 % |
| 7 | DPO dose powder / spice pinch | 2 | 0.0 % | 0.0 % |
| 8 | WSH wash robust produce | 2 | 0.0 % | 0.0 % |
| 9 | DBL portion block solids | 2 | 0.0 % | 0.0 % |
| 10 | COL cool down | 1 | 0.0 % | 0.0 % |
| 11 | MLT melt | 1 | 0.0 % | 0.0 % |
| 12 | RES rest | 1 | 0.0 % | 0.0 % |
| 13 | ABS cook by absorption | 1 | 0.0 % | 0.0 % |
| 14 | DUN dispense countable whole items | 3 | 0.0 % | 0.0 % |
| 15 | MXD mix dry ingredients | 1 | 0.0 % | 0.0 % |
| 16 | PLT plate / arrange | 3 | 0.0 % | 0.0 % |
| 17 | DVI dose viscous / sticky | 2 | 0.0 % | 0.0 % |
| 18 | DIC dice / cube | 2 | 0.0 % | 0.0 % |
| 19 | RNS rinse grains / pulses / pasta | 1 | 0.0 % | 0.0 % |
| 20 | SAU saute / sweat | 2 | 0.0 % | 0.0 % |
| 21 | CHL chill / set | 1 | 0.0 % | 0.0 % |
| 22 | SLI slice (uniform) | 2 | 0.0 % | 0.0 % |
| 23 | DRN drain / strain | 2 | 0.0 % | 0.0 % |
| 24 | RED reduce | 1 | 0.0 % | 0.0 % |
| 25 | TOS toss / coat in bowl | 2 | 0.0 % | 0.0 % |
| 26 | DME dispense raw meat / fish pieces | 3 | 0.0 % | 0.0 % |
| 27 | PFR pan-fry / shallow-fry | 2 | 0.0 % | 0.0 % |
| 28 | SFT sift / sieve dry | 1 | 0.0 % | 0.0 % |
| 29 | GRF grate fine / zest | 2 | 0.0 % | 0.0 % |
| 30 | PLA peel alliums | 4 | 0.8 % | 1.0 % |
| 31 | MIN mince fine / crush | 2 | 1.6 % | 1.8 % |
| 32 | WLF wash delicate / leafy produce | 3 | 1.6 % | 1.8 % |
| 33 | CHH chop herbs | 2 | 2.0 % | 2.2 % |
| 34 | THK thicken | 2 | 2.8 % | 3.0 % |
| 35 | PLP peel potato / smooth roots | 3 | 3.6 % | 4.2 % |
| 36 | KWM keep warm / hold | 1 | 3.6 % | 4.2 % |
| 37 | SOK soak / steep in liquid | 1 | 3.6 % | 4.2 % |
| 38 | STC stir continuously on heat | 2 | 4.8 % | 5.6 % |
| 39 | WHK whisk / beat liquids smooth | 2 | 4.8 % | 5.6 % |
| 40 | BKE bake | 2 | 4.8 % | 5.6 % |
| 41 | SLB slice baked goods / portion cake, pizza | 2 | 5.2 % | 6.0 % |
| 42 | SEA season / salt / rub surface | 2 | 5.6 % | 6.5 % |
| 43 | SER sear / brown at high heat | 2 | 5.6 % | 6.5 % |
| 44 | DGL deglaze | 2 | 5.6 % | 6.5 % |
| 45 | SCE sauce / ladle onto plate | 2 | 6.5 % | 7.7 % |
| 46 | GAR garnish / dust / drizzle | 3 | 8.5 % | 9.7 % |
| 47 | CRK crack egg into vessel | 3 | 10.5 % | 12.3 % |
| 48 | GRC grate / shred coarse | 2 | 10.9 % | 12.7 % |
| 49 | TOP sprinkle / top | 2 | 11.7 % | 13.5 % |
| 50 | PRT portion into servings | 3 | 13.7 % | 15.9 % |
| 51 | TST toast dry | 2 | 14.5 % | 16.9 % |
| 52 | MAR marinate / brine / cure | 2 | 14.9 % | 17.1 % |
| 53 | COR core / deseed / hull | 4 | 16.9 % | 19.2 % |
| 54 | PUR puree / blend | 2 | 16.9 % | 19.2 % |
| 55 | LAY layer | 3 | 18.1 % | 20.6 % |
| 56 | EMU emulsify | 2 | 18.5 % | 21.2 % |
| 57 | RST roast (oven, dry heat) | 2 | 19.0 % | 21.8 % |
| 58 | TRE trim ends / stems / roots | 4 | 22.2 % | 25.2 % |
| 59 | WED halve / quarter / wedge | 3 | 23.8 % | 27.4 % |
| 60 | LIN line / grease / prepare tin, fill mould, spread batter | 3 | 25.0 % | 29.0 % |
| 61 | MSH mash / rice / crush | 2 | 25.4 % | 29.6 % |
| 62 | BRS braise | 2 | 26.2 % | 30.0 % |
| 63 | KNM mix / knead mince mass | 2 | 26.2 % | 30.0 % |
| 64 | FLP flip / turn item | 4 | 28.6 % | 32.3 % |
| 65 | PLS peel soft / thin-skinned fruit & veg | 4 | 31.5 % | 35.5 % |
| 66 | JUI juice / press citrus | 2 | 33.5 % | 36.9 % |
| 67 | CRM cream fat with sugar | 2 | 33.9 % | 37.3 % |
| 68 | SLM slice raw meat / fish | 3 | 35.5 % | 38.9 % |
| 69 | GRL grill / broil / gratinate | 2 | 36.3 % | 39.9 % |
| 70 | JUL julienne / strips / sticks | 3 | 37.9 % | 41.5 % |
| 71 | PLH peel hard / knobbly / woody | 4 | 41.5 % | 45.8 % |
| 72 | KND knead dough | 2 | 41.5 % | 45.8 % |
| 73 | CRH crush / chop coarse hard items | 2 | 42.3 % | 46.8 % |
| 74 | WHP whip to volume / stiff peaks | 2 | 42.7 % | 47.2 % |
| 75 | STW stir-fry (wok) | 3 | 44.8 % | 49.4 % |
| 76 | PRF proof / rise dough | 2 | 44.8 % | 49.4 % |
| 77 | RUB rub in fat / crumble | 2 | 45.2 % | 49.8 % |
| 78 | SPR spread / apply evenly | 3 | 45.6 % | 50.2 % |
| 79 | ASM assemble / build | 4 | 47.6 % | 52.2 % |
| 80 | FRB form patties / balls from mince | 3 | 49.2 % | 53.8 % |
| 81 | ROL roll out dough | 3 | 50.4 % | 55.0 % |
| 82 | BST baste | 3 | 51.2 % | 55.8 % |
| 83 | CNT contact bake | 2 | 51.6 % | 56.5 % |
| 84 | SQZ squeeze out liquid | 3 | 53.2 % | 58.3 % |
| 85 | BLA blanch and shock | 2 | 53.6 % | 58.9 % |
| 86 | FLD fold gently | 3 | 54.0 % | 59.3 % |
| 87 | SEP separate egg (yolk/white) | 4 | 56.0 % | 61.1 % |
| 88 | UNM unmould / turn out | 4 | 58.5 % | 63.7 % |
| 89 | CAR carve / slice cooked meat | 4 | 60.1 % | 65.5 % |
| 90 | DRY dry: spin or pat dry | 2 | 60.9 % | 66.1 % |
| 91 | DFR deep-fry | 3 | 61.7 % | 66.9 % |
| 92 | EXT extrude / press through / pipe small | 3 | 62.9 % | 68.5 % |
| 93 | STU stuff / fill | 4 | 64.9 % | 70.0 % |
| 94 | STR strip / pluck / break apart | 4 | 67.3 % | 72.2 % |
| 95 | BMA bain-marie / gentle water bath | 3 | 68.5 % | 73.4 % |
| 96 | GLZ glaze / brush | 3 | 69.0 % | 74.0 % |
| 97 | CUD cut dough / pasta | 3 | 70.2 % | 75.0 % |
| 98 | PLE peel boiled egg | 4 | 73.0 % | 77.4 % |
| 99 | POU pound / tenderise / flatten | 3 | 73.8 % | 78.0 % |
| 100 | PTH pour and spread thin batter | 3 | 74.6 % | 79.0 % |
| 101 | WRP wrap / roll flat item around filling | 4 | 77.4 % | 81.2 % |
| 102 | STM steam | 2 | 77.8 % | 81.5 % |
| 103 | PIP pipe / deposit shaped portions | 3 | 79.0 % | 82.5 % |
| 104 | CRL caramelise | 3 | 80.2 % | 83.3 % |
| 105 | FRK form dumplings | 3 | 81.5 % | 84.3 % |
| 106 | SCO score / slash | 4 | 82.7 % | 85.3 % |
| 107 | SHD shape dough | 4 | 84.3 % | 87.1 % |
| 108 | FRM shape small pieces by hand | 4 | 86.3 % | 88.7 % |
| 109 | BCR make crumbs / pulse dry | 2 | 86.7 % | 89.1 % |
| 110 | BRD bread / coat (flour-egg-crumb) | 4 | 88.3 % | 90.5 % |
| 111 | SHR shred cooked meat | 3 | 89.5 % | 91.3 % |
| 112 | TRM trim meat: fat, sinew, silverskin, membrane | 5 | 91.9 % | 93.3 % |
| 113 | PLM peel tomato / peach (blanch, slip skin) | 3 | 92.7 % | 94.0 % |
| 114 | RLT roll & tie / truss | 5 | 94.0 % | 95.4 % |
| 115 | PIT pit / stone | 4 | 95.2 % | 96.4 % |
| 116 | SKM skim foam / fat | 3 | 95.6 % | 96.6 % |
| 117 | GRM grind meat | 2 | 96.0 % | 96.8 % |
| 118 | BAT batter dip | 3 | 96.4 % | 97.2 % |
| 119 | DBN debone meat / poultry | 5 | 96.8 % | 97.8 % |
| 120 | BFL butterfly / split / pocket-cut meat | 4 | 97.2 % | 98.2 % |
| 121 | LSP separate cabbage leaves (whole) | 4 | 97.6 % | 98.6 % |
| 122 | FRZ freeze / churn | 3 | 98.0 % | 98.8 % |
| 123 | FLT fillet / gut / scale fish | 5 | 98.8 % | 99.2 % |
| 124 | PLQ shell shrimp / seafood | 5 | 99.2 % | 99.6 % |
| 125 | POA poach egg / delicate item | 4 | 99.6 % | 99.8 % |
| 126 | SKW skewer | 4 | 100.0 % | 100.0 % |

Steps to reach 50/80/90/95/99 %: 81 / 104 / 112 / 115 / 124 of 126 operations.

## Appendix C. Mapping of the G&U top-100 titles to corpus rows

| Rank | Title | Corpus row(s) |
|---|---|---|
| 1 | Klassische Lasagne | IT05 |
| 2 | Schnitzel Wiener Art | DM03 |
| 3 | Spaghetti alla busara | IT01, IT04 |
| 4 | 24-Stunden-Pizzateig | IT10 |
| 5 | Geschmorte Rinderrouladen | DM02 |
| 6 | Bayerische Semmelknödel | SD08 |
| 7 | Pommes frites | SD04 |
| 8 | Rumpsteaks mit Chili-Salsa | DM23 |
| 9 | Nudeln mit Pesto | IT06 |
| 10 | Rheinischer Sauerbraten mit Rosinen | DM07 |
| 11 | Einfaches Wiener Schnitzel | DM03 |
| 12 | Vegetarischer bunter Gemüseauflauf | CS01 |
| 13 | Käsespätzle mit Appenzeller | IT19 |
| 14 | Schnitzel in Weißweinsauce | DM04 |
| 15 | Rotes Thai-Curry mit Hähnchen | AS03 |
| 16 | Nackensteaks vom Grill | DM24 |
| 17 | Nudelauflauf mit Käse und Gemüse | CS02 |
| 18 | Rahmspinat mit Reherl und Ei | SD13 |
| 19 | Gefüllte Paprikaschoten | DM13 |
| 20 | Spargel mit Sauce Hollandaise | SD19 |
| 21 | Paprika-Hackbällchen-Pfanne | DM35 |
| 22 | Reispfanne mit Lachs | AS01, VG05 |
| 23 | Spaghetti Carbonara | IT02 |
| 24 | Avocado-Tofu-Sushi | AS05 |
| 25 | Königsberger Klopse mit Kapern | DM10 |
| 26 | Kartoffel-Puffer mit Mus | SD05 |
| 27 | Lachs-Tagliatelle mit Kräuter-Limetten-Rahm | IT07 |
| 28 | Chili con Carne | MX01 |
| 29 | Bratkartoffeln | SD03 |
| 30 | Kohlrouladen mit Hack-Sauerkraut-Füllung | DM12 |
| 31 | Saftige Hamburger | US01 |
| 32 | Vegetarische geschmälzte Maultaschen | DM33 |
| 33 | Saftiges Brathähnchen | DM20 |
| 34 | Bunter Sommersalat | SA01 |
| 35 | Verführerischer Erdbeerkuchen | CK05 |
| 36 | Apfelmilchreis mit Zimtzucker | DS01 |
| 37 | Einfaches vegetarisches Kartoffelgratin | CS03 |
| 38 | Nudelsalat mit Schinken und klassischem Mayonnaise-Dressing | SA04 |
| 39 | Frikadellen mit Kartoffelsalat | DM01 |
| 40 | Schnelle Gemüsepfanne mit Schafskäse | AS11, VG01 |
| 41 | Cordon bleu mit Emmentaler | DM05 |
| 42 | Schnelles Risotto mit grünem Spargel | IT09 |
| 43 | Kaiserschmarrn mit Rum | DS05 |
| 44 | Shrimps-Pasta aus dem Wok | AS02 |
| 45 | Pasta quattro formaggi | IT16 |
| 46 | Kartoffelsuppe mit Würstchen | SP03 |
| 47 | Bunter Obstkuchen | CK05 |
| 48 | Balsamicohähnchen auf buntem Pfannengemüse | DM36 |
| 49 | Currywurst mit Sauce | DM14 |
| 50 | Käsekuchen für Kinder | CK02 |
| 51 | Linsen und Spätzle | DM28 |
| 52 | Kartoffelsalat mit Kräutern | SD06 |
| 53 | Auberginenauflauf Moussaka | ME02 |
| 54 | Sauerkraut mit Kassler | DM16 |
| 55 | Masala Chicken | IN01 |
| 56 | Knoblauchgarnelen | ME07 |
| 57 | Eier in Senfsauce | DM31 |
| 58 | Heidelbeermuffins | CK07 |
| 59 | Grünkohl mit Speck | DM27 |
| 60 | Schweine-Krustenbraten | DM06 |
| 61 | Schokokuchen ohne Mehl | CK06 |
| 62 | Hühnerfrikassee mit Spargelstangen | DM19 |
| 63 | Vegetarischer Graupeneintopf mit Steckrüben | SP13 |
| 64 | Schweinefilet mit Brokkoli | DM25 |
| 65 | Schnelles Erdbeereis mit Mascarpone | DS13 |
| 66 | Flammkuchen | FR05 |
| 67 | Fladenbrot mit Gyros | ME03 |
| 68 | Ofengemüse mit Pinienkernen | SD20 |
| 69 | Tiramisu | DS06 |
| 70 | Sommergemüsesuppe mit Gremolata | SP06 |
| 71 | Mandel-Grießbrei mit Nektarinen | DS02 |
| 72 | Ofenkartoffel mit Kräutercreme | SD25 |
| 73 | Einfacher Couscoussalat | SA10 |
| 74 | Backschatz Apfelkuchen | CK03 |
| 75 | Kartoffelgulasch mit Würstchen | SP20 |
| 76 | Möhren-Orangen-Suppe | SP14 |
| 77 | Kraut-Schupfnudeln | SD22 |
| 78 | Dampfnudeln mit Krusterl | DS11 |
| 79 | Salade niçoise au thon | SA15 |
| 80 | Hühnersuppe mit Nudeln | SP05 |
| 81 | Kalbsgeschnetzeltes mit Gurke und Dill | DM22 |
| 82 | Kir-Royal-Cupcakes | CK07 |
| 83 | Linsensuppe mit Würstchen | SP02 |
| 84 | Schnelle Schinkennudeln | CS02 |
| 85 | Spanische Paella | ME01 |
| 86 | Griechischer Salat mit Minze | SA07 |
| 87 | Frankfurter grüne Sauce | DM32 |
| 88 | Steirische Kürbissuppe | SP07 |
| 89 | Tacos mit Chili und Orangencreme | MX02 |
| 90 | Schwarzwälder Kirschtorte im Miniformat | CK08 |
| 91 | Klassischer Gänsebraten | DM21 |
| 92 | Pfannkuchensuppe | SP11 |
| 93 | Schokopudding mit Karamellsauce und Erdnüssen | DS03 |
| 94 | Rinderbraten in Prosecco | DM08 |
| 95 | Fischstäbchen | FI01 |
| 96 | Kalbsleber | DM18 |
| 97 | Waffeln | BF08 |

Ranks 98-100 could not be retrieved; they are not needed for the representativeness check.

