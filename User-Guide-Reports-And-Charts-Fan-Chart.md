# Fan chart

The Fan Chart displays direct ancestral lines in concentric radial ring segments centered on a focal root individual. Open this chart when you want a compact, visually striking representation of multiple ancestral generations (up to 12 generations), or to inspect ancestral completeness across all family quadrants simultaneously.

## What you see

- **Focal Individual:** Occupies the central circular hub or origin point.
- **Concentric Ancestral Rings:** Each concentric ring outwards represents one ancestral generation (Parents in Ring 1, Grandparents in Ring 2, Great-Grandparents in Ring 3, up to Ring 12):
  - Each parent's segment lies directly behind and spans the angular width of their child's segment.
  - Text curvature automatically adapts: names curve along the arc in inner rings and radiate outward along spokes in outer rings to maximize legibility.
- **Chart Options Toolbar:**
  - **Fan Span Selector**: Toggle between **180° (Half Circle)**, **270° (Three-Quarter Circle)**, and **360° (Full Circle)**.
  - **Generations**: Display between 3 and 12 generations.
  - **Color By**: Color by *Generation*, *Lineage* (separating paternal and maternal quadrants), or *Sex*.
  - **Show Dates and Places**: Toggle birth and death dates within segment blocks.
  - **Export PDF...**: Generate vector PDF exports.

## Common tasks

### Switch fan angular span

1. In the chart options toolbar, open the **Fan Span** dropdown.
2. Select **180°** for a classic half-circle fan (ideal for framing or standard landscape pages).
3. Select **270°** or **360°** for deep pedigrees (7+ generations) where wider arc spacing is needed for readable names in outer rings.

The chart smoothly re-lays out its geometry in real time.

### Color-code by ancestral quadrant

1. In the options popover, set **Color By** to **Lineage**.
2. The chart colors each quadrant distinctly:
   - Paternal grandfather's line.
   - Paternal grandmother's line.
   - Maternal grandfather's line.
   - Maternal grandmother's line.

This makes it easy to track which quadrant an ancestor belongs to even in distant 6th and 7th generations.

### Re-root the fan chart

1. Click any segment on the fan to select that ancestor.
2. Double-click the segment (or press **Enter**) to re-root the fan chart on them, generating their own complete ancestral fan.

## Practical use cases

- **Family reunion displays and heirloom gifts:** A 180° or 360° fan chart is one of the most popular visual formats for family reunions and printed wall displays, packing up to 256 or 512 ancestors into a clean, balanced circular geometric shape.
- **Visualizing research completeness at a glance:** Unidentified ancestors appear as blank wedge segments. Seeing which quadrant has large white gaps instantly tells you which ancestral branch needs more archival research.

## Good to know

- Text fitting is handled with precision vector measurement (`fitText`): names wrap to multiple lines inside segments before truncating.
- Living individuals are automatically redacted to **Private** with dates hidden.
- Exporting to PDF produces crisp Bézier curves and vector fonts that maintain clarity at high-resolution poster print sizes.
