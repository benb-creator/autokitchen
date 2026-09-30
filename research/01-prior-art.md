# R1 — Prior art: cooking robots and automated kitchens

Research task R1 of the AutoKitchen project. Input: `BRIEF.md`, `PLAN.md`. Date of research: 2026-09-30.

## 0. How to read this document

**Verification legend.** Every fact carries a source URL. Where the confidence is not "read on the page", it is tagged:

* **[V]** – read on the cited page during this research (WebFetch of the page).
* **[S]** – appears only in a web-search result summary (title/snippet), page itself not read (usually because it returned HTTP 403 or the fetch failed). Treat as probable.
* **[M]** – from my background knowledge, not verified in this session. Treat as unverified.
* **[E]** – my own estimate or engineering judgement, not a sourced fact.

**Limits of this research.** The web-search budget of the session was exhausted after roughly two thirds of the planned queries. The remaining companies were researched by fetching news-site archive pages (The Spoon) and company pages. Consequences: Panda Express wok robots, Bear Robotics (as a cooking company), any open-source/DIY project other than OliveR, and current (2026) status of several companies could not be verified. They are marked as such in section 2.

**Scope note.** Nearly all prior art is commercial (restaurant, canteen, ghost kitchen). Only Moley, Samsung, Thermomix-class machines, Posha/Nymble, Suvie, Cooki, Oliver and OliveR are home-scale. None of them attempts the AutoKitchen brief (storage + cold storage + prep + cooking + plating + dishwashing + ingestion of supermarket packages, all autonomous). The closest in ambition is Circus CA-1 (silos + induction pots + dishwasher, but commercial, 7-20 m²) and Moley (wall-integrated, but the human chops and loads).

---

## 1. Summary table

| # | System | Scale | Architecture | Ingredient storage/dosing | Cooking | Cleaning | Prep by machine | Meal range | Price | Outcome |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Moley Robotics | Home | Ceiling/wall-mounted 1-2 arms on rails, whole kitchen wall | Human pre-cuts, puts into designated bins/containers | Induction hob, arm stirs, scrapes | UV disinfection, "cleans up" claimed, details unverified | None (human chops) | 5,000 recipes claimed, ~60 dishes at launch | £80k (1 arm) to £248k (2 arms) | Few or no installs; niche luxury |
| 2 | Samsung Bot Chef | Home concept | 2 light arms under cabinet | Human | Demo only | n/a | Chop demo, choreographed? | n/a | none | Never a product |
| 3 | Miso Flippy | Restaurant | 1 arm on rail or on floor + vision + basket handling | Human loads baskets | Deep fryer | Ecolab-designed cleaning, robot "opens fully" | None | Fry station only | $5,400/month RaaS | ~20 sites, ongoing, slow |
| 4 | Spyce / Infinite Kitchen | Restaurant | 7 tilted rotating induction woks + conveyor + dispensers | Refrigerated bins, volumetric dispensers, commissary pre-chops | Wok tumbling, ~2.5-3 min | Self-clean woks (details unverified) | None (commissary) | Bowls | ~$500k/unit [S] | 20+ Sweetgreen sites, tech sold for $186M |
| 5 | Zume | Delivery pizza | Robot line + trucks with 56 ovens | Central prep | Ovens on trucks | n/a | Limited (dough press, sauce) | Pizza | n/a | Shut down 2020 (pizza), 2023 (company) |
| 6 | Creator | Restaurant | ~12 modules, grinder, slicers, sauce X-Y head | Fresh meat/veg loaded, grind and slice to order | Sear | Human cleaning heavy | Yes: grinds meat, slices tomato/onion/pickle | 1 burger | $6 burger | Closed 2020, reopened 2021, shut 2023, relaunch as B2B |
| 7 | Nymble / Posha | Home | Countertop: 4 hoppers, spice carousel, induction, camera, spatulas | User pre-chops, loads hoppers | Induction + stirring, vision | Parts dishwasher-safe | None | 500+ recipes, 10 cuisines | $1,500-1,750 | Shipping (200 units at time of article), $8M Series A |
| 8 | Suvie | Home | Refrigerated multi-zone water-jacket cooker | Meal-kit packs | Steam/slow/sous vide/oven | Wipe/remove trays | None | Meal-kit based | $599 announced, $1,199 retail | Sold; not a "robot" in motion terms |
| 9 | Thermomix / Cookit / Monsieur Cuisine | Home | Single vessel with bottom blade + heater + scale | User adds by weight | 37-160 °C (TM), 200 °C (Cookit) | Self-clean program + dishwasher for parts | Chops/grinds/kneads in vessel | Very wide (80,000 recipes) | $1,699 US; €1,399 Cookit | Mass-market success (~860k TM7 units in <1 year) |
| 10 | Sereneti Cooki | Home | Countertop pan, induction, 1 spatula arm, ingredient trays | Subscription pre-cut trays flip into pan | Induction + stirring | Arm passive below shoulder, dishwasher-safe | None | Subscription meals | $99-600 target | Company closed |
| 11 | Else Labs Oliver | Home, then pro | 5 top-loading jars, mixing arm, water tray | User fills jars | Heated chamber | Not verified | None | App recipes | $530 early bird | Home rollout paused 2022, pivot to "Oliver Fleet" |
| 12 | GoodBytz | Canteen | Robot arms shuttle pots between stations, rotating cooking shelf | Refrigerated storage 24-72 ingredients + 24 toppings | Induction on rotating shelf | Built-in dishwasher module (Winterhalter) | None | Bowls/hot dishes | RaaS (monthly + per dish) | Active, Sodexo pilot 2023, EUR 12M raise |
| 13 | Circus CA-1 | Canteen/retail | 2 arms in glass cell, heated silos, induction pots | Silos with sensors | Induction pots, arm stirs | Built-in commercial dishwasher | None | Soups, stir-fry, pasta, curry, porridge, eggs | dishes from EUR 6 | Series 4 in production; REWE Düsseldorf; Beijing MoU |
| 14 | Remy Robotics | Ghost kitchen | Custom robots, fridges, smart ovens | Central prep | Smart ovens | n/a | None | 100+ recipes | n/a | Operating in ES/FR/US (2023-24) |
| 15 | Aitme | Canteen kiosk | 8 m² kiosk, arms + rotating induction bowls | 40 hot/cold ingredients | Induction bowls | Self-cleaning | None | 10 meals | $3,900-5,600/month | Acquired by Circus 2023 |
| 16 | Karakuri | Restaurant | 2x2 m kiosk, 14 heated/cold chambers, assembly | Pre-prepped | Assembly only | n/a | None | Bowls | n/a | Shut down June 2023 |
| 17 | Dexai Alfred | Restaurant | 1 arm on cart + bowl-passing arm, tool swap | Bins with utensils inside | Assembly only | NSF design | None | Salads/bowls | n/a | 10 military bases, Gordon trial |
| 18 | Chef Robotics | Food factory | Arms on racks above assembly line | Pans slide in with locking | Assembly only | Open-angle frame, rounded utensils | None | Deformable ingredients | RaaS | 100M servings, >12 facilities |
| 19 | Hyper Food Robotics | Container | 20/40 ft container, 2 arms, ovens | Cold storage, 12 topping dispensers | Convection ovens | n/a | None | Pizza | n/a | Pizza Hut Israel |
| 20 | Botinkit / Chinese wok robots | Restaurant | Large rotating wok + seasoning dispensers, optional arm | Pre-cut in trays + 13 seasoning boxes | 350 °C wok | Auto-clean wok + tubes | None | Stir-fry, 30 cuisines | $32-43k | Sold in volume in Asia, Walmart China |
| 21 | Yo-Kai / Pazzi / Picnic / Stellar | Vending, pizza | Vending / conveyor / robots | Frozen bowls / dough / toppings | Reheat / oven | Auto sanitise cycle | None | Ramen, pizza | see text | Yo-Kai active; Pazzi 2022, Picnic 2026 shut |
| 22 | Mezli / YPC / SJW RoWok | Kiosk | Container, arm, multi-cookers | Central prep | Heat, multi-cooker | n/a | None | Mediterranean bowls; dishes | $7/meal | Status unverified |

---

## 2. Profiles

### 2.1 Moley Robotics

* **Architecture.** Wall-integrated kitchen: cabinets, induction hob, sink and protective screen, with either one arm (X-AiR: a Universal Robots arm) or two anthropomorphic arms with five-finger hands (R-kitchen, hands developed with Universal Robots and SCHUNK). Arms move on an overhead rail. [V] https://www.engadget.com/home/kitchen-tech/a-105000-robot-arm-nobody-needs-cooked-me-a-delicious-lunch-140050065.html , https://en.wikipedia.org/wiki/Moley_Robotics , https://thespoon.tech/moleys-robotic-kitchen-goes-on-sale/
* **Ingredients.** The human chops and puts ingredients into designated bins and tells the machine where they are (diagram). The X-AiR "operates from memory", has no built-in vision, and occasionally drops debris; it cannot improvise or substitute. Produces 8-10 portions per session. [V] Engadget.
* **Cooking/stirring.** Arm heats oil, adds ingredients sequentially, stirs, scrapes utensils. Recipes were captured from chefs (Tim Anderson) via 3D cameras and gloves. [V] Wikipedia, Spoon.
* **Cleaning.** Marketed as "even cleans up" (Robb Report headline) and UV disinfection is listed [V Wikipedia for UV; S for headline https://robbreport.com/gear/electronics/moley-robotics-robot-kitchen-uk-for-sale-1234590791/]. I could not verify how pots, hob and arms are actually cleaned. Assume the human still does part of it.
* **Prep.** None: the human chops. **Range:** 5,000 recipes claimed, ~60 dish types at launch [S]. **Price:** £80,000 (X-AiR, ~$105k), £128,000 without arms and £248,000 with arms [V Spoon, Engadget].
* **Outcome.** Debuted CES Asia 2015, on sale 2020 [V Spoon]. Engadget reported that no unit had been installed yet, installs "expected in 3-6 months" (date of that article not confirmed; the search index dated it roughly two years back) [V]. Actual sales unverified.
* **Why.** A high-DOF humanoid solution replays recorded motions in a fixed layout, needs the human for all prep, costs 60-200 times a Thermomix, and offers little a cheap machine cannot do. It has the same problem as the whole class of "recorded-motion" robots: no adaptation to ingredient variation.

### 2.2 Samsung Bot Chef

* Two light 6-DOF arms with 3 fingers, mounted under the cabinet; showed cutting, whisking, stirring, salting, pouring at KBIS and CES 2020. [S] https://robbreport.com/gear/personal-technology/samsung-bot-chef-2891606/
* TechCrunch: the company could not say how much was autonomous versus choreographed; "all flash and little productizing"; no price or availability. [V] https://techcrunch.com/2020/01/07/samsungs-knife-wielding-robotic-chef-is-all-flash/
* Status: no product I know of [M]. Lesson: a demonstrator, not evidence.

### 2.3 Miso Robotics (Flippy)

* **History.** Flippy 1 (2017, burger grill at CaliBurger Pasadena, ~$60k [S]) was retired; the company pivoted to frying. Flippy 2 / Fry Station has an AutoBin basket-handling system, "56% reduced aisle intrusion, 13% lower", fewer surfaces to clean, up to 60 baskets/h (Flippy 2). [V] https://thespoon.tech/miso-introduces-second-generation-restaurant-kitchen-robot-the-flippy-2/ ; retired units now decorate the CaliExpress restaurant [S] https://www.restaurantdive.com/news/caliexpress-flippy-robotic-restaurant-opens-pasadena-california/701617/
* **Current product.** Smaller, faster arm plus NVIDIA vision, >100 baskets/h ("almost twice humans"), 50% smaller, install overnight, **$5,400/month RaaS**, claims $5-20k/month benefit; Ecolab helped design cleaning procedures; runs with under-18 staff. [V] https://www.therobotreport.com/miso-robotics-refines-flippy-fry-station-with-ai-partners/ ; ~20 locations (Jack in the Box, White Castle) [S] https://www.robotics247.com/article/miso_roboworx_partner_to_scale_service_flippy_fry_station_robots/miso_robotics
* **ROAR** (Robot-on-a-Rail): overhead rail keeps the arm out of aisles; planned price cut from $30k to $20k at scale (2020). [V] https://www.therobotreport.com/white-castle-miso-robotics-test-flippy-roar-frying-robot-fast-food-trials/
* **Cleaning.** The robot "opens fully" for cleaning [S]; no robotic self-cleaning.
* **Why it (partly) works.** One narrow, dangerous, repetitive job (fryer), RaaS pricing, retrofit into existing kitchens, a chain that already has the process. Why slow: after 9 years about 20 sites; CEO/co-founder departed [V-title https://thespoon.tech/?s=flippy]. Even the best single-task arm has a long adoption curve.

### 2.4 Spyce / Sweetgreen Infinite Kitchen

* **Architecture.** Seven tilted, rotating, induction-heated woks; ingredient bins refrigerated behind them; a "runner" shuttles along and volumetric dispensers portion ingredients; cooks ~2.5-3 minutes; wok tips itself over to pour into a bowl; a human "garde manger" adds cold garnishes. [V/S] https://mitsloan.mit.edu/ideas-made-to-matter/spyce-restaurant-opens-robotic-kitchen-ready-to-serve (woks, dispensing, garde manger, commissary chops) ; https://www.10news.com/news/national/mit-grads-create-robotic-dining-experience [S] (induction, runner, 2.5 min).
* **Prep.** A "commissary team" chops off-site. "Without humans, our robotic kitchen would not function." [V] MIT Sloan.
* **Cleaning.** The robots self-clean after cooking [V] https://en.wikipedia.org/wiki/Spyce_Kitchen ; method (I recall high-pressure water jets and a hot wash [M]) not verified.
* **Infinite Kitchen (Sweetgreen).** Conveyor under ingredient dispensers, similar to the Creator makeline; "about half of Sweetgreen's labor is food assembly and this takes the majority of it". [V] https://thespoon.tech/two-years-after-buying-spyce-sweetgreen-launches-infinite-kitchen-robotic-restaurant/ First site Naperville IL (2023). >20 restaurants now. [V] https://www.sec.gov/Archives/edgar/data/1477815/000162828026000636/exhibit991-pressreleaseswe.htm
* **Money.** Spyce raised $21M Series A (2018), bowls from $7.50, both original Spyce restaurants closed (Oct 2021 and Feb 2022) [V Wikipedia]. Sweetgreen bought Spyce in 2021 for ~$70M and sold it to Wonder for $186.4M ($100M cash + $86.4M Wonder stock) on 29 Dec 2025, retaining a licence and supply agreement at cost plus 5%; that 5% is reported as ~$25k, implying ~$500k per unit [S: Restaurant Business / QSR / search summaries; the pages returned 403 so the $500k figure is unverified] https://www.restaurantbusinessonline.com/technology/sweetgreen-sell-spyce-technology-company-wonder-1864m
* **Why it worked.** It does one thing (assembly of pre-cut items into bowls, wok-cooking the hot component) inside a chain with a fixed, small menu, a central commissary and high labour cost. It is the most successful "dedicated stations + passive dosing" system. **Why it is not our design:** it needs commissary prep; ~$500k per unit; 2-3 min bowls only.

### 2.5 Zume

* Central "robot production line" (dough, sauce, oven loading) plus trucks with **56 ovens** that bake en route; $6M Series A 2016, **$375M from SoftBank 2018** ($2.25B valuation); shut pizza delivery Jan 2020 after laying off ~360 people (80%), then pivoted to packaging, closed 2023. [V] https://physicsworld.com/a/robot-cooked-pizza-delivered-to-your-door-heres-what-zumes-failure-tells-us/ , https://thespoon.tech/between-cafe-x-zume-and-creator-are-we-in-a-food-robo-pocalypse-nah/
* Failure causes (as reported): low-margin product with high capital cost; trucks (~$750k each [S]) for single pizzas; product only "okay"; scaled to 3 cities before mastering one; ~$10M/month burn [S https://thestartupdigests.substack.com/p/how-a-robot-pizza-startup-burned-d35]. The Spoon notes the robots "only did things like pull crusts out of the oven".
* Lesson: cooking in a moving unit, cheese sliding: irrelevant to us; the general lesson is capex-heavy automation of a low-margin product.

### 2.6 Creator (burger robot)

* **Architecture.** A dozen-plus modules, 20 Linux computers (BeagleBone Black), 350 sensors; refrigerated grinder turns marinated brisket/chuck into a patty to order; **slicers for tomato, onion and pickle were "worked on longer than anything else"**; 15 condiments through positive-displacement pumps and an X-Y plotter-style head, dosing "to the milliliter". [V] https://makezine.com/article/digital-fabrication/how-two-california-kids-overcame-doubters-to-automate-the-freshest-burger-ever-served/
* **Rates and price.** ~4-6 minutes per burger, one every ~30 s as a line; $6 burger. [V] Hackaday https://hackaday.com/2018/10/11/i-ate-a-robot-hamburger-before-the-restaurant-went-out-of-business/ (the same author counted ~10 people working in the restaurant, 6 of them "working the machine", meaning manual loading, cleaning and maintenance.)
* **History.** Opened SF June 2018; temporarily closed June 2020 (COVID emptied SoMa) [V https://thespoon.tech/creator-temporarily-closes-its-robot-restaurant/]; reopened in Daly City Aug 2021 with a 30% faster robot (3.5 min) [S]; shut down March 2023 [V https://thespoon.tech/karakuri-joins-the-growing-list-of-food-robot-startups-that-have-shut-down/]; founder left March 2023; relaunched as a B2B platform to license the robot to chains, abandoning "robot theater" [V https://thespoon.tech/creator-is-making-a-comeback-only-this-time-as-a-platform-player-and-not-robot-theater/]. Funding: $18M cited in 2020 [V], ~$60M total in "first life" [V].
* **Cleaning.** Not documented in what I could read; the Hackaday author noted meat processing has to be hidden, implying heavy sanitation. The company added an "air lock" pick-up for COVID [S]. Fresh grinding and slicing to order is **the only fully-fresh raw-prep prior art** and it needed a restaurant's worth of staff for loading/cleaning.

### 2.7 Nymble → Posha

* Microwave-sized: four ingredient hoppers, spice carousel, induction cooktop, several spatulas, a top camera that judges colour/texture. User must **pre-chop** and load. Spaghetti Alfredo took ~30 min with minimal interaction. **$1,750 retail / $1,500 pre-order**; 200 units shipped, 600 more projected (at time of article). [V] https://thespoon.tech/is-posha-the-robotic-heir-to-the-thermomix-the-founder-sure-hope-so/
* 500+ recipes across ten cuisines; $8M Series A May 2025 (Accel); renamed from Nymble May 2025. [V] https://en.wikipedia.org/wiki/Posha_(company) . Food-contact parts dishwasher-safe, cleanup ~5 min [S https://www.livingetc.com/news/nymble-kitchen-robot]. Criticised for price and limited capacity.
* Lesson: the consumer market accepted ~$1.5k for "cook while I do something else" **only with the human doing all cutting**. Whole hoppers can hold only a small volume.

### 2.8 Suvie

* Countertop refrigerator + four-zone water-jacket cooker (steam, slow cook, sous vide, oven): chills meal-kit packs until the start time, then cooks. Announced $599, ships at **$1,199** ("components turned out more expensive than we anticipated"); meal plans $10-12 per serving. [V] https://thespoon.tech/suvies-refrigerator-connected-cooking-device-ships-but-retail-price-doubles/ . Three generations, current $649 [S https://www.suvie.com/kitchen-robot/] (with meal plan $149).
* Relevance: a working example of **refrigerated holding until cooking** (water-jacket + compressor, 40-205 °F) and of price creep. No motion, no dispensing.

### 2.9 Thermomix, Bosch Cookit, Monsieur Cuisine ("one vessel does everything")

* **Thermomix TM7 (2025).** Bowl 2.2 L max, Varoma steamer 6.8 L, 33.6 x 25.3 x 40.5 cm, 8.6 kg [V https://service.thermomix.com/hc/en-us/articles/45021284196499-What-are-the-technical-specifications-of-the-new-Thermomix-TM7]; blade up to 160 °C, both directions [S https://thermomix.com.au/products/thermomix-tm7]; built-in scale [V https://en.wikipedia.org/wiki/Thermomix]; **$1,699 (US), A$2,649** [S]. About 860,000 TM7 units since February 2025, the most successful launch in Vorwerk history [S https://www.directsellingnews.com/2025/11/24/thermomix-tm7-launch-breaks-sales-records/]. Sold via direct-sales consultants (MLM-like); A$4.6M fine in Australia over hot-splash defects [V Wikipedia] (interlock/safety matters).
* **Cleaning.** "Pre-clean mode" runs water + detergent through a bowl cycle; all parts except the base are dishwasher-safe; the knife still has to be disassembled and rinsed/brushed [V https://service.thermomix.com/hc/en-us/articles/51486550720403-How-do-I-best-clean-my-Thermomix-TM7]. CHOICE lists lid crevices and rubber seals holding odours as the tedious parts. [V https://www.choice.com.au/home-and-living/kitchen/all-in-one-kitchen-machines/articles/is-a-thermomix-really-worth-it]
* **Limits.** Browning/caramelising only in small batches, no viewing window, no dry ingredient addition during cooking, over-processing of soft veg. [V CHOICE]
* **Bosch Cookit.** €1,399, 3 L bowl, 1,700 W, up to 200 °C (steak, popcorn), 3D stirrer, interchangeable elements (twin whisk, chopping disc); cannot grind; residue burns on the bottom because the stirrer does not reach the bottom. [V https://www.techadvisor.com/article/2132345/thermomix-tm6-vs-bosch-cookit-2.html]
* **Tokit Omni Cook** (a Thermomix-class competitor): 21 functions, up to 180 °C, self-cleaning with water and lemon-acid concentrate. [V https://www.tokit.com/blogs/news/nymble-cooking-robot-vs-tokit-cooking-robot]
* **Lesson.** The only home cooking automation with mass-market success. Its strengths: a **single vessel with heater, weighing and bottom blade** covers soup, sauce, puree, dough, mash, steam, risotto, and it is cheap because there is no motion system. It automates neither storage, dosing, nor cleaning of the seal/blade.

### 2.10 Sereneti Cooki

* CES 2015 prototype: induction pan, **robotic arm with spatula that is unpowered below the shoulder ("dishwasher-safe")**, ingredient trays that flip over into the pan at the recipe time; subscription of **pre-cut, pre-measured trays** ($4-5 per meal); target price $500-600; $99 + $49/month subscription also floated. [V https://www.reviewed.com/ovens/features/cooki-may-someday-be-your-robot-chef ; S https://www.digitaltrends.com/home/onecook-and-serenetis-cooki-are-robotic-chefs/]
* Sereneti Kitchen is listed as closed [S, search summary of Crunchbase]. The reviewer noted the cooking time is unchanged and the user still stocks and maintains it.
* Lesson: consumables logistics (pre-cut trays) is a business, not a machine feature; it did not survive.

### 2.11 Else Labs Oliver

* Five top-loading jars, back-loading water tray, a central mixing arm; dispenses per app recipe; Indiegogo Sept 2020: **$530** early bird, $120,825 from 181 backers. [S https://www.indiegogo.com/en/projects/elselabs/oliver-automated-smart-cooking-robot]
* Home rollout **paused** because of "supply chain disruptions, component shortages and price changes"; pivot to "Oliver Fleet" for commercial kitchens with reinforced internals. [V https://thespoon.tech/else-labs-announces-commercial-kitchen-focused-oliver-fleet-as-it-pauses-rollout-of-home-cooking-robot/]
* Lesson: small hardware companies die on BOM cost and supply chain; use standard parts (a brief requirement).

### 2.12 GoodBytz

* Hamburg, founded Aug 2021. Robot arms move **pots** under ingredient dispensers, add sauces, put pots on a **rotating cooking shelf** (Spyce-like), then to a serving module (4 bowl types). Refrigerated storage for 24-72 ingredients/sauces, topping dispenser for up to 24, a **dishwasher module**; ~200 sq ft (~18.6 m²), up to 3,000 meals/day, ~125-150/h. RaaS: monthly fee + per dish. First major deployment with Sodexo in Q3 2023; partners Palux (cooking equipment) and Winterhalter (warewashing). EUR 12M raise Oct 2023. [V https://thespoon.tech/goodbytz-unveils-modular-robotic-kitchen-that-can-make-up-to-three-thousand-meals-per-day/ ; S https://tech.eu/2023/10/27/germany-s-goodbytz-raises-12m-robotic-kitchen-assistants/]
* Current status 2026 not verified.
* **Relevance:** the **pot is the transfer vessel**, moved between dosing, cooking, serving and washing stations, and warewashing is an off-the-shelf commercial unit. This is the closest architectural precedent for our brief.

### 2.13 Circus (CA-1)

* Munich. Fully enclosed 7 m² cell (early) to ~20 m² (Beijing deal text); **two robot arms** behind glass, climate-controlled/heated silos with sensors, induction pots, stirring speed adaptive to meal, plating, built-in **commercial dishwasher** that sanitises equipment between meals; up to 120 dishes/h; Series 4 is ~450 kg lighter than early prototypes; >29,000 components, 150+ tests per unit; dishes from EUR 6; pilot at REWE Düsseldorf; hospitals/universities/factories explored. [V https://interestingengineering.com/innovation/autonomous-ai-robotic-cooking ; https://www.therobotreport.com/circus-se-completes-first-production-of-ca-1-robots-in-high-volume-facility/ ; https://www.therobotreport.com/autonomous-kitchen-developer-circus-roll-out-5400-robots-across-beijing/]
* Range: soups, stir-fries with noodles or rice, pasta, curries, stews, porridge, scrambled eggs. Ingredients are pre-prepared (pre-cut, portioned) [E from the absence of any prep step in any description].
* Claimed 5,400 robots across 92 Beijing institutions is an **MoU**, not a contract, with "low single-digit billion euro" revenue expectations. Treat as aspirational. [V Robot Report]. Price per unit and financial health: not verified.
* Circus acquired Aitme in Aug 2023 [S https://www.robotics247.com/article/circus_se_rolls_out_ca_1_food_production_robots_across_beijing_education_institutions].

### 2.14 Aitme

* Berlin. Kiosk 8 m² (next version 4 m²), **40 hot and cold ingredients, 10 meals**, "articulating arms grab ingredients, rotating induction bowls heat and mix", 120 meals/h, self-cleaning, restock once a day; EUR 3M raised, one contract (Mar 2021) [V https://thespoon.tech/aitme-is-building-a-robot-restaurant-kiosk-in-berlin/]. Rental $3,900-5,600/month; plasma exhaust-air cleaning [S https://www.ottomate.news/p/video-see-aitmes-all-in-one-robot]. Acquired by Circus in 2023 [S].
* The **rotating induction bowl** is the simplest stirring: rotate the vessel, keep a fixed scraper.

### 2.15 Karakuri

* London, Ocado-backed ($9.1M seed, GBP 6.5M later [S]). Semblr: 2 x 2 m kiosk, up to 14 enclosed hot/cold chambers, 110 meals/h, 4 in parallel, ~30 s per meal, 17 ingredients at Ocado HQ; **assembles pre-prepped ingredients, does not cook**. [V https://thespoon.tech/karakuri-semblr-food-robot-to-feed-up-to-four-thousand-employees-at-ocado-hq/]
* **Shut down June 2023**: pandemic, "unable to find the funding to move to the next level" (gap between seed and Series A/B). [V https://thespoon.tech/karakuri-joins-the-growing-list-of-food-robot-startups-that-have-shut-down/]

### 2.16 Dexai Robotics (Alfred)

* Alfred 2.0: main arm + **bowl-passing arm**, refrigeration units, kitchen display; **utensil-swapping** so that allergen groups keep dedicated tools (ServSafe); utensils are stored inside the food bins at food-safe temperature. [V https://www.therobotreport.com/dexai-designs-alfred-2-0-safe-food-service-help-restaurants-pandemic/]
* $5.5M seed [V-title https://thespoon.tech/?s=dexai]; trial at Gordon Food Service (assembles 100 chicken Caesar salads), deployment to 10 US military bases [V https://thespoon.tech/foodservice-distributor-gordon-trials-dexais-bowl-food-making-robot/]. NSF design. Price not disclosed.
* Lesson: **tool-per-ingredient, stored in the bin**, is a hygiene pattern worth copying: the container brings its own dosing tool (no shared tool means no cross-contamination and no tool washing between ingredients).

### 2.17 Chef Robotics

* Arms hung from racks above food-assembly lines in factories (Amy's Kitchen, Sunbasket, Chef Bombay, Cafe Spice); vision + learned scooping of deformable ingredients; ingredient pans slide in with a locking mechanism; the Chef+ frame is open-angle iron (cleanability), rounded flat utensils; RaaS. [V https://www.therobotreport.com/chef-robotics-launches-most-advanced-assembly-robot-yet/]
* **100M servings**, >12 facilities in US/Canada/Europe, $43.1M Series A March 2025 ($20.6M equity + $22.5M equipment debt), total $65.6M. "High-volume, lower-complexity tasks like portioning and assembly", real-world (not simulated) data. [V https://www.therobotreport.com/chef-robotics-completes-100-million-product-servings-milestone/ ; S https://www.therobotreport.com/chef-robotics-brings-in-43m-to-deploy-more-food-assembly-robots/]
* The most volume of any food robot company, and the task is **only portioning/assembly**. No cooking, no cutting.

### 2.18 Hyper Food Robotics

* Container restaurant, 20 ft [V hyper-robotics.com knowledgebase] vs 40 ft [S nocamels/search] (sources conflict); 2 dispensing arms, up to 12 topping dispensers, 3 convection ovens, conveyor, slicer, boxing, 30 warming cabinets; **50 pies/h**; Pizza Hut Israel is the first user (its CEO is also Hyper's CEO); "save up to $4,000/month labour". [V https://thespoon.tech/hyper-robotics-launches-robot-pizza-restaurant-in-a-box/ ; https://www.hyper-robotics.com/knowledgebase/hyper-food-robotics-unveils-20-foot-autonomous-pizza-making-marvel/]
* Cleaning, price and sales volume: not disclosed.

### 2.19 Chinese wok robots (Botinkit and others)

* **Botinkit** (Shenzhen, 2020). OMNI: 30 L cast-iron wok (180 kg), up to **350 °C, 8 °C/s heating**, portions 0.2-8 kg, up to **13 simultaneous seasonings** across 4 types (dry, sauce, liquid, oil) in 650 ml to 1.5 L boxes, **auto-cleaning of wok and tubes**, power 10-12 kW, ~1 m² footprint, pre-measured ingredients loaded by hand, optional robot arm add-on. [V https://botinkit.ai/product/cooking-robot/ ; https://restauranttechnologynews.com/2024/12/botinkits-ai-powered-wok-robot-seeks-to-revolutionize-restaurant-kitchens-in-asia-and-beyond/]
* ChefBot: 60-90 dishes/h, **automated wash cycle between dishes (90 s), automated deep clean at shift end (15 min)**, HACCP logging; purchase from $43,000 (reseller) or $1,199/month for 36 months; OMNI reseller price $32,450. Recipe programming = a chef cooks once while the machine records temperature, time and agitation. [V https://www.robotlab.com/manufacturers/botinkit/ ; S usaequipmentdirect]. Reseller prices; manufacturer price not verified.
* Customers include Walmart China and Delibowl (Singapore); claims that labour drops from 6-10 to 1-2 people in a 100 m² kitchen, -30% ingredient loss, -40% energy vs gas. [V restauranttechnologynews]
* **SJW Robotics RoWok** (US): pre-cut ingredients in segmented silos on a perforated tray through a steam tunnel then a wok, 80-90 s/meal, 2 woks (planned 6, ~60 meals/h), storage for 320 meals. Cleaning not documented. [V https://thespoon.tech/sjw-robotics-demoes-rowok-a-fully-robotic-wok-restaurant-kiosk/]
* **Panda Express wok robots**: I could not find any verifiable source. **Not verified.** Other Chinese wok machines (Alibaba listing category "automatic stir-fry machine") exist in large numbers [S https://www.alibaba.com/showroom/automatic-wok-machine.html] but I did not analyse individual models.
* Lesson: the **large, simple, rotating wok with volumetric seasoning dispensers and water-and-detergent self-wash** is the most mature cooking-automation design in the world and sells at $30-45k; it demands pre-cut ingredients, and it is designed for 10 kW.

### 2.20 Vending and pizza

* **Yo-Kai Express.** Ramen made in a central kitchen, partly cooked and **flash-frozen**, RFID freezer of 20-24 bowls, reheated in ~90 s ("300 °C" as claimed); sanitising cycle per bowl; airports and offices. [V https://www.vendingtimes.com/news/yo-kai-express-intros-ramen-vending-machine-with-storage-freezer/ ; S apex.aero, digitimes] The trade-off is stark: **no cooking at all**, only heating of prepared frozen meals.
* **Pazzi** (Paris): dough press, sauce, toppings, oven transfer, boxing; 80 pizzas/h, one per 47 s; 97% uptime (3% for maintenance, cleaning, restocking) [S food-service.de]; humans still did cleaning/customer service [V https://www.pmq.com/pazzi-paris/]. **Closed 3 Oct 2022**, court-ordered liquidation, 35 laid off, EUR 12M+ raised; CEO blamed an immature French hardware-funding ecosystem and public mistrust of robots. [V https://thespoon.tech/french-robot-pizza-restaurant-startup-pazzi-shuts-its-doors/]
* **Picnic** (Seattle): topping-assembly conveyor (sauce, cheese, fresh-sliced pepperoni), 100-300 pies/h, RaaS $3,500-4,500/month (3-year term), Q1 2022 sold out. [V https://thespoon.tech/lets-order-a-pizzabot-picnic-reveals-pricing-opens-ordering-for-pizza-robot/] Layoffs and CEO departure in 2023, **shut down and sold assets May 2026**, never profitable despite Domino's and MOTO Pizza partnerships; the article lists Zume, Pazzi, Basil Street and Pizzametry as failed pizza robots. [V https://thespoon.tech/as-picnic-shuts-down-and-sells-assets-others-look-to-fill-their-shoes/]
* **Stellar Pizza** (ex-SpaceX): truck with robot claws taking dough balls from a 420-ball refrigerated chamber, press, topping line, pepperoni saw slicing 19 logs [S https://www.verdictfoodservice.com/news/stellar-launches-robot-pizza-machine/]; 12-inch pizza in ~5 minutes per Korea Herald (45 s claimed elsewhere; conflict); $22.6M invested; **acquired by Hanwha Foodtech (contract March 2024)**; pizza $8-9 in LA. [V https://www.koreaherald.com/article/3338921]

### 2.21 Bear / YPC / Mezli

* **YPC Technologies** (Canada): articulating arm feeds ingredients into **multi-cookers** that chop, stir and cook; ~100 dishes/h; salmon, mushroom risotto, sorbet; ~40 m² target; aims to automate 60% of the kitchen, human does restocking and plating ("plating of the dishes is very difficult to achieve with robots"); pre-seed, CAD 1.8M. [V https://thespoon.tech/ypc-wants-to-bring-fast-food-robotics-to-fresh-food-cooking/ ; S title https://thespoon.tech/ypc-raises-1-8-million-cad-for-its-versatile-robot-cooking-kiosk/] Status unknown. Note the **use of a multi-cooker (Thermomix-like) as the cooking device** in a robot kitchen.
* **Bear Robotics**: I found no cooking product; my recollection is that Bear is a restaurant-serving robot (Servi) company [M]. I could not verify the "Bear" reference in the assignment. Not verified.
* **Mezli** (Stanford founders, San Francisco): containerised restaurant; food is **prepped and pre-cooked by humans in a central kitchen**, kept refrigerated in the container; the robot heats, plates and garnishes into pickup lockers; up to 75 meals/h (claim); $7 per meal (target $4.99); Mediterranean plates; robot needs servicing every 48 h or 300 meals; first restaurant opened in SF 28 Aug (year not in the snippet, 2022 [E]). [V https://thespoon.tech/mezlis-containerized-robot-restaurant-opens-to-public-this-weekend/ ; https://thespoon.tech/mezli-building-a-new-robo-restaurant-in-a-shipping-container/] Current status not verified.

### 2.22 Remy Robotics

* Barcelona, ghost kitchens (Barcelona, Madrid, Paris, NYC "Better Days"); builds its own robots, fridges and **smart ovens with temperature/moisture/weight sensors**; "algorithmic cooking" from a recipe to parameters; philosophy: **do not imitate the human, design the cooking method for the robot** and put the robot at the centre; a kitchen installed in ~48 h; 100+ recipes; 60k own-brand meals, 100k+ overall (as of ~2023). [V https://thespoon.tech/for-restaurant-robots-to-succeed-remy-robotics-believes-they-need-to-be-at-the-center-of-the-kitchen/ ; https://thespoon.tech/remy-robotics-unveils-robotic-ghost-kitchen-platform-as-it-opens-third-location-in-barcelona/ ; S https://www.therobotreport.com/remy-robotics-exits-stealth-with-3-autonomous-kitchens-operating/]
* Arm model, prep strategy, cleaning, price: not disclosed. Status in 2026 not verified.

### 2.23 Others found on the way

* **Cafe X** (robot barista kiosk): closed 3 downtown SF sites and airport sites, then re-opened SFO and Tesla Giga Berlin; coffee is the easy, liquid-only, low-prep case. [V titles https://thespoon.tech/?s=cafe+x]
* **Chowbotics Sally** (salad vending robot): acquired by DoorDash, ~$21M funding; pre-cut ingredients in canisters with volumetric dosing. [V titles https://thespoon.tech/?s=chowbotics]
* **Rotimatic** (flatbread robot): single-purpose, works; not analysed.
* **SVFactory** (Sebastian Thrun, home cooking robot, stealth): outcome unknown. [V https://thespoon.tech/can-this-self-driving-car-pioneer-crack-the-code-on-cooking-robots/]

### 2.24 Home-scale DIY / open source

* **OliveR** (Oak Robotics, 2014): programmable stirring rod, temperature control and timing over a normal pot; the human cuts and adds ingredients; no cleaning story; no evidence it reached market. [V https://hackaday.com/2014/01/09/oliver-the-programmable-cooking-robot/]
* GitHub topic `cooking-robot` had no repositories (checked). [V https://github.com/topics/cooking-robot]
* I did not find any open-source home kitchen with automatic ingredient dosing and cleaning. **Nothing else verified.** Research-arm projects (e.g. MIT/Google/Berkeley manipulation research on cooking) exist [M] but are not products.

---

## 3. Cleaning: what has actually been done

| Pattern | Who | What is cleaned how | Verdict for us |
|---|---|---|---|
| Remove parts, wash in domestic/commercial dishwasher | Posha, Cooki, Thermomix, Oliver | Hopper/bowl/spatula are demountable | Works, but the human does it. In our machine the **machine has to do the removal and washing** (GoodBytz/Circus do it with a commercial dishwasher module). |
| Self-clean program with water + detergent, run the actuator | Thermomix pre-clean, Tokit (lemon acid) | Bowl and knife; seals and knife hub still hand-rinsed | Good for the vessel, insufficient alone; must be combined with a removable blade/seal or a design with no gaps |
| Auto-wash of wok and tubes between dishes (90 s) + deep clean at shift end (15 min) | Botinkit | Wok internal spray, seasoning lines flushed | Proven pattern for liquid lines and the wok; needs waste-water drain and water |
| Built-in commercial warewasher module | Circus CA-1, GoodBytz (Winterhalter) | Pots, tools, bowls in rack dishwasher | Best documented match for our brief's "dish washer + vessels + tools" |
| Tool per ingredient stored in the food bin | Dexai | Bin-and-tool set is washed together, no cross-use | Neat: dosing tool is part of the box |
| Design for cleanability of the robot itself | Chef Robotics, Miso | Open-angle frame, rounded edges, fewer surfaces, robot "opens fully" | Necessary, not sufficient |
| Passive arm segment | Cooki | Nothing electric below the shoulder, dishwasher-safe | Applicable to our end effectors |
| Central prep + sealed packaged food, only heating on site | Yo-Kai, Mezli | No raw food in the machine, only sanitise-per-order | The cleanability shortcut everyone takes; incompatible with our brief |
| Human cleans | Creator, Pazzi, Miso (dry parts) | Manual | This is what killed unit economics |

**Observation.** In no case is *everything* automatically cleaned: dry dispensers (bins), tracks, the outside of the enclosure, the exhaust and the grease are still cleaned by people. Only **Circus/GoodBytz claim end-to-end self-cleaning**, and only for vessels/tools, not for the enclosure, and their independent evidence is thin.

---

## 4. Synthesis

### 4.1 Recurring design patterns that work

1. **Dedicated stations + a shuttle, not a general-purpose humanoid.** The systems with volume (Infinite Kitchen, Chef Robotics, Picnic while it lasted, Botinkit, Creator's line, Karakuri, Aitme, GoodBytz, Circus) all have fixed stations, and arms only where they *move standard containers or standard tools*. The two anthropomorphic, recorded-motion projects (Moley, Samsung) have essentially no volume.
2. **The vessel is the transfer unit.** GoodBytz moves pots between stations; Aitme/Spyce have the vessel be the cooker; Circus moves pots; YPC feeds multi-cookers. This is a natural fit for the brief ("maybe the sauce pan is the bucket").
3. **Passive, gravity- or volume-based dosing** for pre-cut/granular items (Spyce volumetric dispensers, Sally, Cooki trays, RoWok silos, Posha hoppers), **pumps for liquids** (Creator pumps to the ml; Botinkit 13 seasoning boxes with dry/sauce/liquid/oil types), **grippers/scoops only for deformables and portioning** (Chef Robotics, Dexai).
4. **Rotate or tilt the vessel instead of stirring with an arm.** Spyce (tilted rotating woks), Botinkit (rotating wok, 350 °C), Aitme (rotating induction bowls), GoodBytz (rotating shelf). Simplest hygiene: no reaching stirrer, and the tilt doubles as the pouring mechanism.
5. **Bottom-blade single vessel for everything wet** (Thermomix, Cookit, Tokit; YPC uses multi-cookers). Very cheap, very versatile, proven with ~10^6 units/year (TM7: ~860k units in <1 year [S]).
6. **Weighing.** Thermomix has a built-in scale; closed-loop by weight is the norm in the home segment [V Wikipedia].
7. **Standard components:** Circus and GoodBytz build on commercial induction, commercial dishwashers (Winterhalter) and industrial arms; Moley uses a Universal Robots arm; the Oliver failure is what happens when custom components hit a supply crisis.
8. **Human-in-the-loop for the parts that are hard:** restocking, garnishing, plating (Spyce garde manger, YPC "plating is very difficult"). Nobody automated presentation well.
9. **A tight menu.** Successful systems cook 1-10 kinds of dish (bowls, burgers, fries, pizza). The broad-menu ones (Circus, Remy, Botinkit, Posha) sit at ~100-500 recipes and have unproven volume.
10. **RaaS** ($3.5-5.6k/month: Picnic, Miso, Aitme; $1.2k/month Botinkit) is how commercial customers accept the capex. Not applicable to a one-off home product.

### 4.2 Recurring failure causes

1. **Capex versus a low-margin product** (Zume, Creator, Pazzi, Picnic: never profitable).
2. **Human labour did not vanish.** Creator needed ~6 people around the machine; Spyce needed a commissary; Pazzi's humans clean; Mezli needs central-kitchen prep. Automation moved the labour upstream.
3. **Product not better than the human alternative** (Zume "okay pizza", Creator $15 meal similar to competitors).
4. **Funding valley / macro shock** (Karakuri, Creator, Pazzi, Zume, Cafe X: pandemic, SoftBank pullback, immature hardware funding).
5. **Complexity and integration burden** (Creator: 350 sensors, 20 computers; Zume's overly complex line; Circus 29,000 components).
6. **Supply chain and BOM creep** (Else Labs; Suvie price doubled from $599 to $1,199).
7. **Consumer price ceiling**: home machines sell at ~$1.5-1.7k (Posha, Thermomix). Moley at $105-335k is a luxury item. Anything above ~$5k needs a very strong story [E].
8. **"Robot theater"**: the tech is the attraction, not the food (Creator's own admission).
9. **Recorded-motion and demo-driven robots** (Samsung, Moley) not demonstrated in unattended use.
10. **Poor hygiene design** raises the human cleaning load (Creator, Thermomix seals/lid, Cookit residue on the bottom).

### 4.3 What nobody has solved (evidence-based)

| Gap | Evidence |
|---|---|
| **Raw-ingredient prep** (peeling, trimming, boning, cutting arbitrary produce) | Every system either uses a human commissary (Spyce, Mezli, Yo-Kai, Karakuri, Sereneti), a human at home (Moley, Posha, Oliver, OliveR), or cuts only a fixed set of standard items (Creator: tomato, onion, pickle slicers took longest; patty grinder). Thermomix chops in the vessel only. **No system peels.** |
| **Self-cleaning of the entire machine** | Only vessels/tools are cleaned (Botinkit, Circus, GoodBytz). Enclosure, bins, exhaust, tracks are human-cleaned. |
| **Ingestion of supermarket packages** (open, empty, identify, store) | No prior art found. Industrial analogues: bag-openers/decanters in food factories [M]. Cooki/Posha/Karakuri all needed pre-cut delivered or user-chopped ingredients in their own trays. |
| **Whole-cut meat handling** (roast, Rouladen, steak, Frikadellen mixing) | Creator (grind to patty) is the only meat prep. Aitme/Circus menus are curries, pasta, bowls. |
| **Baking/oven work** | Only pizza lines (Zume, Pazzi, Hyper, Stellar) and Suvie; no bread, roasts. |
| **Attractive plating** | YPC quote; Spyce human garnish. |
| **Breadth ≥95% of traditional meals** | Widest claims: Thermomix 80,000 recipes (with a human), Botinkit "10,000 recipes" [S], Circus ~7 dish families. Nobody measured a coverage against a corpus. |
| **Storage of raw food (fridge/freezer grid + retrieval)** | Circus silos and GoodBytz refrigerated storage (24-72 items) and Aitme (40) are the only ones; none stores in a general box grid. |

### 4.4 Quantitative cross-check: commercial versus home scale [E]

Commercial systems are designed for 60-150 meals/h. A household needs 2-8 portions per meal, i.e. a factor 20-50 less. All the complexity (many woks, conveyors, 10-12 kW power, 7-20 m²) is throughput-driven. Posha takes ~30 min and accepts that. Consequence: **our design should trade speed for simplicity, with one or two cooking vessels used sequentially and a low power budget.**

Power estimate: a 230 V/16 A outlet gives 3.7 kW; Botinkit needs 10-12 kW [V]. Heating 2 kg of food (c ≈ 3.5 kJ/kgK) from 5 to 100 °C needs ≈ 665 kJ; at 2.5 kW effective it takes ≈ 4.5 minutes plus the vessel's thermal mass. That is acceptable at home. Two simultaneous induction zones would each be limited; a 400 V 3-phase feed or load management is a decision for the architecture.

Footprint comparison: Circus 7-20 m², GoodBytz ~18.6 m², Aitme 8 → 4 m², Karakuri 4 m², Botinkit Omni ~1 m² (one station), Posha/Thermomix ≈ 0.1 m². A 0.6 m x 3 m run x 2 m is 1.8 m² floor but ~3.6 m³ envelope [E]: we are between a single station and a canteen kiosk, with storage added.

---

## 5. Recommendations for AutoKitchen

Numbers marked [E] are estimates for later verification by R4, R5, R8.

### 5.1 Overall architecture: stations + a vessel shuttle

**Recommend** a fixed set of stations along the 600 mm-deep unit, served by **one vertical-plane Cartesian shuttle (X-Z gantry) that carries boxes and vessels** (the same transport system as the storage grid), with **no general-purpose 6-axis arm in the cooking path**.

Reasons from prior art:
* Arms with anthropomorphic reach need free volume and produce splash zones nobody can clean; the two anthropomorphic home products (Moley, Samsung) have no real volume; commercial arm systems (Circus, GoodBytz, Aitme, YPC, Remy) are 4-20 m² cells because arms sweep large volumes.
* In a 600 mm-deep cabinet a 6-axis arm's swept volume would waste footprint; a planar gantry uses only a slot along the front [E].
* The proven usage of arms in this space is *moving standard containers* (GoodBytz pots, Dexai bowls, Chef Robotics scoops). A gantry with a gripper/tilt head does the same with standard linear axes, and gives repeatable docking (a requirement for washing and dosing).
* Where an arm is unavoidable (plating, pick-and-place of garnish), use a small SCARA/delta or a 4-axis cartesian on the plating station only (Chef Robotics' arm-on-rack shows tolerable hygiene if the frame is open-angle and utensils are rounded).

### 5.2 Vessels and cooking: two vessel types on one interface

1. **Tilting rotary induction wok** for stir-fry, searing, roasting of pieces, pan-frying-type operations (Spyce, Botinkit, Aitme). Simple, self-emptying by tilt, no stirrer to clean. Working size: **~5-8 L drum for 4 portions (~1.6-2 kg)**, far smaller than Botinkit's 30 L [E]. Power 2-3 kW induction under a 3.7 kW mains budget [E].
2. **Stirred pot with bottom-mounted blade/scraper** (Thermomix/Cookit style) for soups, sauces, purée, mash, dough, risotto, steaming, and for chopping in the vessel. Working volume **3-4 L** (Cookit 3 L, TM 2.2 L; a family batch of soup ≈ 1.5-2 L) [E]. Lessons: put the blade in a removable, washable cartridge; make sure the stirrer reaches the bottom (Cookit's residue problem); keep seals removable (Thermomix seals retain odour); provide a sight/camera path (TM7 has no window); allow ingredient addition while running.
3. **Same docking flange** so either vessel can be moved by the gantry between dosing, heating, plating and washing. GoodBytz precedent.
4. **Separate oven** (baking/roast/steak alternative) and **contact grill or pan** as later stations; prior art gives no guidance beyond pizza lines and Suvie, so this is R5's problem.

### 5.3 Ingredient storage and dosing

* **The storage box is the dispenser** (as the brief suggests): the gantry tips the box over the vessel; precedent: Cooki trays that flip into the pan, Spyce/Sally volumetric dispensers, RoWok silos, Posha hoppers. For free-flowing items (rice, pasta, sugar, flour, salt, herbs) use a **metering lid** with vibration or a shaker/auger cap in the box lid rather than a whole-box pour [E].
* **Weigh in the vessel** with load cells (Thermomix has a built-in scale) and dose closed-loop. Verify with camera (Posha).
* **Liquids and oils in bottles with positive-displacement or peristaltic pumps**, with a flush cycle after each use (Creator pumps to the ml; Botinkit tube auto-clean).
* **Sticky/wet/whole items** (mince, chopped onions, meat pieces): nobody dispenses them reliably from bins; Chef Robotics needs vision and scoops, Creator grinds to order. Use a **scoop/spatula per box stored in the box (Dexai)** or push-out (piston) boxes; treat as an open R4 item.
* **Allergen and cross-contamination**: a tool dedicated to each box (Dexai) removes the need to wash tools between ingredients.

### 5.4 Preparation

* **Chop, grate, puree, knead inside the stirred vessel** (Thermomix proves this covers a huge range and it removes a separate cutting station).
* **A slicing/dicing station** like Creator's (rotary blade + pusher), for firm produce and cheese. Creator says slicers took the longest to develop, so budget for it [V].
* **Meat**: fresh grinder is proven (Creator). Whole-muscle cutting (Rouladen, steak trimming) has no precedent; consider accepting "pre-cut by the butcher" and vacuum-packed items as a documented limit.
* **Peeling** is unsolved by everyone; design around it: buy pre-peeled/frozen produce, peel-on cooking (potatoes are washed, cooked and peeled/mashed via a sieve), an abrasive-drum potato peeler [M: exists in industry, R4 to verify]. Include this in the coverage analysis against the 95% goal rather than promising it.

### 5.5 Cleaning concept

1. **Vessels, blades, tools, boxes' lids and plates go through a built-in commercial-style warewasher** (Circus and GoodBytz precedent; GoodBytz partners with Winterhalter). This is the brief's "dish washer" reused for machine parts, with racks that the gantry loads.
2. **In-place wash for the vessel between dishes** (Thermomix pre-clean; Botinkit 90 s between dishes, 15 min deep clean): spray ring, drain, detergent dosing; at 2.2-5 bar mains, a rotating spray head is feasible [E].
3. **Liquid lines flushed after each use** (Botinkit; Creator).
4. **No open mechanisms above food**: motors, chains and cables outside a sealed splash zone; **open-angle frames and rounded edges** (Chef Robotics); pass-through shafts only with washable seals; **passive end effectors** (Cooki: nothing electric in the tool).
5. **Dry storage boxes are washed in the warewasher when emptied**; ingestion funnel and chutes need a spray-wash cycle (no prior art).
6. **Exhaust/steam**: Aitme's plasma exhaust cleaning shows steam and grease are real issues [S]; use a condensing hood with a washable filter and drain.

### 5.6 Cold storage

Suvie proves refrigerated holding with a compressor plus a water-jacket [S]. Circus silos and GoodBytz refrigerated bins prove that "storage with a robot exit" exists, at 24-72 items. Our brief (an off-the-shelf fridge/freezer with a modified door) has no direct precedent; R3 owns it.

### 5.7 Scope and product-definition advice

* **Do not** copy the commercial throughput target. Design for ~4-8 portions in ~30-45 minutes (Posha ~30 min for a dish). This removes the need for multiple woks, conveyors and 10 kW.
* **Do** define the vessel/box/station interfaces first (the plan already does): GoodBytz and Circus succeed by standardising on a **pot** and a **pot wash**.
* Where the machine cannot do something (peeling, whole-muscle trim, plating flourishes), **state the limit** and measure the 95% goal (R2) against it. Prior art shows no system has ever been evaluated against a real meal corpus.
* Budget: prior art suggests home customers pay ≤ $2k for a Thermomix-class and ≥ $100k for Moley-class. A full AutoKitchen belongs to a third class (a fitted kitchen, EUR 20-60k [E]); be explicit that parts count and cost drive the design.

---

## 6. Open issues

1. **Status in 2026** of Moley (actual installs), Samsung Bot Chef, Remy, GoodBytz, Circus (finances; Beijing MoU only), Mezli, YPC, Hyper, Dexai, Stellar, Botinkit volume: not verified. Suggest re-checking before quoting any as "successful".
2. **Panda Express wok robots** and Bear Robotics as a cooking company: no source found. Removed from analysis.
3. **Actual cleaning methods** of Spyce woks, Infinite Kitchen, Circus, GoodBytz, Aitme, Moley, Miso: not documented in any source I could read. Ask via the vendors or find installation/maintenance manuals; this is the most important open fact for D7.
4. **Infinite Kitchen unit price (~$500k)** is inferred from "cost plus 5% ≈ $25k" in search-result text only.
5. **Botinkit prices** come from resellers ($32,450 OMNI; $43,000 ChefBot; $1,199/month RaaS); the manufacturer's actual price is unknown; wok cleaning method (spray? detergent?) is not described.
6. **Failures still unexplained by primary sources**: Sereneti's closure (only an aggregator entry), Creator's 2023 shutdown reasons, Picnic's date (May 2026 per The Spoon; not cross-checked).
7. **Conflicting figures**: Hyper container 20 ft vs 40 ft; Stellar pizza time 45 s vs 5 min; Creator funding $18M vs ~$60M; Creator burger time 3.5-6 min.
8. **Industrial analogues not researched** (belong to R4/R6/R7): food-factory bag openers, potato peelers, drum washers, clean-in-place (CIP) hardware, commercial warewasher racks and robot-loaded dishwashers.
9. **DIY/open source**: search budget prevented a proper sweep of Hackaday, Instructables, GitHub, academic labs (e.g. robotic kitchens in research). Only OliveR verified.
10. **No prior art evaluated against a meal corpus**: coverage claims (5,000 / 10,000 / 80,000 recipes) are marketing numbers.

## 7. Risks

1. **The brief is beyond any shipped system.** Not one product combines storage, prep of raw ingredients, cooking, plating, self-cleaning and package ingestion; the failed and pivoted projects tried subsets. Risk of an unbuildable or unaffordable machine. Mitigation: rank features by how many meals they unlock (R2) and set explicit limits.
2. **Raw-ingredient prep and package ingestion are unsolved.** Expect the largest engineering effort and the biggest gap versus the "95%" target; possible fallback: restrict to pre-cut/frozen/pre-peeled inputs and document it.
3. **Hygiene is where the human labour returns** (Creator, Pazzi, Thermomix seals). A design where any surface is only cleanable by hand will fail the brief's "human will not clean anything".
4. **Cleaning water/detergent and heat load in a 600 mm cabinet**: steam, grease and moisture reaching electronics and the storage grid; the prior art has no small, sealed, self-cleaning combination.
5. **Power**: mains 3.7 kW vs. 10-12 kW for commercial woks; cooking, dishwashing and cold storage compete for power. Requires load management or a 3-phase feed.
6. **Food safety and liability**: hot-splash recalls and a A$4.6M fine hit Thermomix; an unattended machine that heats oil to 200+ °C needs interlocks, fire suppression and certification (R6, D9).
7. **Custom-parts and BOM creep** (Oliver, Suvie): the standard-parts constraint is protective; violating it risks cost and supply chain failure.
8. **Breadth vs reliability**: broad menus made unproven volume in every case (Circus, Remy, Botinkit); reliability of a 20-station mechanism with many dosing boxes and sticky foods is untested.
9. **Perception risk**: "robot theater" and public mistrust (Pazzi) and the tendency of demos to be choreographed (Samsung). Validate with unattended runs of real recipes (V2).
10. **Evidence quality**: much of the above rests on trade-press and vendor claims, several of them from search summaries (tagged [S]); numbers should be re-confirmed before they drive a specification.
