# Diagram round — every document with technical solutions gets animated illustrations

Customer request: for every document with technical solutions or ideas, an animated SVG that shows how
the machine or part works. **Assume the viewer does not read the text** — the drawing alone must explain
the principle. If a machine has several distinct parts (e.g. storage, cell, washer, hatch), make **one
diagram per part**, plus one overview showing how the parts fit together.

* Style: `design/prep/diagrams/STYLE.md` (binding; same look as the existing K1–K9b diagrams — look at the
  first 80 lines of `design/prep/diagrams/K9b-schlicht.svg` for the look).
* Content per diagram: a clear drawing (section or perspective-like view where that explains best), real
  proportions from the document, labels in plain words, a looping animation (10–40 s) of the part doing
  its job step by step, a caption line per step, key numbers in a corner. Prefer showing motion over text.
* File names: `<doc-id>-<part>.svg`, e.g. `K11-overview.svg`, `K11-wash-well.svg`, `S4-aisle-shuttle.svg`,
  `C1-B-top-exit.svg`, `A-turn-mill.svg`. Concept documents → `design/prep/diagrams/`; storage documents →
  `design/storage/diagrams/`; idea and gap documents → `design/prep/diagrams/ideas/`.
* SMIL or CSS animation only, no JavaScript, < 300 KB per file.
* Check each file: render at 2 animation times (headless Chrome via the puppeteer in `/tmp/pwtool` or
  `~/.cache/puppeteer` if present, else librsvg on time-frozen copies), look at the PNGs, fix overlaps and
  clipped text. Scripts and screenshots stay in /tmp.
* Do NOT edit `index.html` (a gallery is built at the end).
* Usage limits matter: read only the sections of the source document that describe the solution
  (`grep -n '^## '` for ranges), no helper agents, save each SVG as soon as it is drawn, commit once at the end
  with only your own files, no attribution lines (a hook pushes to GitHub).
