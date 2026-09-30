# AutoKitchen — Project Brief

This is the customer's brief. It is the source of truth for all requirements and design work.

## Goal

A fully automatic kitchen that can cook most normal meals completely autonomously.

## Parts

* storage system
* cooled (fridge, freezer) storage system
* meal preparation, including cutting, mixing etc.
* cooking, including stirring
* portioning on a dish
* dish washer
* transport system
* opening product packaging

## Details

### Storage

Food is stored in rectangular plastic boxes of small to medium sizes. They are stored in a grid, in a
way that a specific single box can be transported to the exit of the storage system. Design this
transport system.

### Cold storage

Works in the same way, just that the exit is closed thermally. Otherwise, it works like the storage
system, inside a fridge or freezer. Ideally, it can be an off-the-shelf fridge/freezer, possibly with
a slightly modified door.

### Meal preparation

Design a multi-tool or multiple tools, so that it can perform all steps for preparing most meals,
from salads to mashed potatoes to roast beef, Frikadellen, Rouladen, soups, steak, pasta, you name
it. At least 95% of all traditional meals should be preparable.

Spend decent time thinking about how to design this tool or these tools, the holders, food bucket
etc., how to pour the various ingredients (potato, veggies, fruits, meat, salt, herbs, etc.) from the
storage box into the bucket, and from one bucket to another, and from the bucket to the sauce pan or
frying pan. Or maybe the sauce pan is the bucket — up to the designer.

Entirely novel tools for food preparation are welcome.

### Cleaning

Especially for these tools and the casing, make sure that it can all be cleaned automatically. The
machine operates with food, and it must be hygienic. The human will not clean anything — that would
defeat the purpose of automatic. So cleaning is a major consideration.

The same applies to all other parts of the machine, including storage boxes and transport system.

### Cooking and baking

Could be a normal induction plate for cooking, but the designer is free to design something
different. Ditto for baking.

### Portioning and serving

After the meal is cooked, the machine needs to put it on a dish for the human to eat. It should be
nicely presented. If cooking for multiple people at once, the system should be able to cook for all
of them at the same time and portion the food on the dishes for each person.

The dish(es) will be presented to the human at a specific place with an automatic door, where they
will take them.

### Dishes

After eating, the human will place the used dishes in a dish washer, and then put the clean dishes on
the same spot as before.

### Ingestion

To ingest food into the storage system, the user places the package as bought in the supermarket in
a container. The machine picks one package at a time, scans the bar code with EAN number, looks up
the product and what is inside on the Internet, then cuts open the package and lets the contents fall
into one of the storage boxes, using a funnel.

Alternatively, the user scans the bar code and pours the contents into the funnel.

Make those 2 versions of the ingestion machine.

### Modularity

Design the parts of the machine modular: e.g. storage, ingestion, preparation/cooking/portioning and
transport system are all different parts, with the transport system binding them together
physically. Each machine part should be designed independently.

### Physical constraints

* Dimensions like a normal kitchen: 60 cm deep, 200 cm high.
* The machine should be able to span a corner, i.e. "L" form, optionally.
* Available: cold fresh water pipe (flowing, 2.2 to 5 bar, drinking water), waste water pipe, 220 V
  power, Internet.

### Build constraints

* Use as many standard parts as possible, so that it can be built with off-the-shelf parts and a 3D
  printer.
* Self-cleaning (all parts).
* Easily accessible to a human for repair.
* Robust for everyday use.
* Does not waste footprint space.
