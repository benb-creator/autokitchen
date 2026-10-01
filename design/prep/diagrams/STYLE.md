# Concept diagrams — common style

One self-contained animated SVG per candidate concept, so the customer can see how each concept works.

## Files

`design/prep/diagrams/K<n>-<slug>.svg` (same slug as in `design/prep/concepts/`), plus `index.html`
showing all eight with titles and one-line captions.

## Content of each SVG

* **Two views side by side:** front view (as seen from the kitchen, door removed) on the left, top view on
  the right. Both to the same scale, with a scale bar and the overall dimensions (width × 600 deep ×
  height) as stated in the concept document. Show the 600 mm depth and the oven, hobs and wash station
  where the concept puts them.
* **Label every major part** with short names that match the concept document.
* **Animation:** one looping sequence of about 20–40 s showing the concept's characteristic workflow on a
  real task, e.g. box arrives → ingredient dosed → cut/processed → transferred → cooked → flipped/stirred
  → handed over → cleaned. Moving parts move along their real axes. A caption line at the bottom
  changes with each step ("1/8 Box docks and tilts: potatoes into the wash basket").
* **Title block** top left: concept ID, name, one-line essence; key numbers top right (wall width,
  actuators, est. coverage, est. parts cost), taken from the concept document.

## Look

* viewBox `0 0 1600 900`, white background, flat colours, 2 px dark-grey outlines, sans-serif text
  (`font-family: system-ui, sans-serif`), minimum font size 14 px.
* Colours: structure/casing light grey `#d0d4d9`; stainless food-contact ware steel blue `#8fa8c0`;
  moving mechanisms orange `#f28c28`; food green/brown/yellow as appropriate; water/wash `#4aa3df`;
  heat (active induction, oven) red `#e04a3a`; seals/elastomers dark purple `#6b4c8a`.
* Animation with SMIL (`<animate>`, `<animateTransform>`, `<animateMotion>`, `<set>`) or CSS keyframes
  inside the SVG; no JavaScript, no external files or fonts, so it plays in a browser and as an `<img>`.
* Keep each file below ~200 KB.

## Accuracy

Draw what the concept document says (dimensions, positions, kinematics), simplified. Where the document
is vague, choose the simplest reading and say so in a `<!-- comment -->`. Diagrams illustrate; they
do not change the design.
