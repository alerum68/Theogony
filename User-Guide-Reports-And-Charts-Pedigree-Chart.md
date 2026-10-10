# Pedigree chart

The Pedigree Chart displays direct ancestral lines (parents, grandparents, great-grandparents) extending horizontally from a focal individual. Open this chart when you want a clean, classic overview of direct ascendants, to inspect generational depth, or to produce publication-quality ancestral pedigree printouts.

## What you see

- **Focal Root Individual:** Pinned at the left edge of the chart canvas.
- **Ancestral Generations:** Extend from left to right across generational columns (father above, mother below), connected by crisp vector elbow lines joining each child to their parents' bracket bar.
- **Person Boxes:** Display primary display name, birth year and place, death year and place, and portrait photos when enabled.
- **Chart Options Toolbar:**
  - **Generations**: Slider or selector to display between 3 and 12 ancestral generations.
  - **Name Format**: Toggle between *Given Surname* ("Mary Hale"), *Surname, Given* ("Hale, Mary"), or *Given Only*.
  - **Show Dates / Places / Photos**: Checkboxes to customize box contents.
  - **Color By**: Color nodes by *None*, *Sex* (blue/pink), *Generation* (distinct color ramp per generational tier), or *Lineage* (paternal vs. maternal lines).
  - **Leave Space for Unknown Ancestors**: Reserves blank geometric placeholder boxes for missing ancestors so generational alignment is preserved.
  - **Export PDF...**: Opens the vector PDF export dialog with page fitting and multi-page tiling.

## Common tasks

### Re-root the chart on an ancestor

1. Double-click any ancestor's box in the chart, or select it and press **Enter**.
2. The chart smoothly re-renders with that selected person as the new focal root, extending their ancestral lines forward.

### Navigate the chart with mouse and keyboard

- **Pan**: Click and drag anywhere on the chart canvas.
- **Zoom**: Hold **Ctrl** and scroll your mouse wheel, or press `+` to zoom in and `-` to zoom out.
- **Fit to Screen**: Press `0` to instantly scale and center the entire chart within the viewport.
- **Select Neighbor**: Use the **Arrow keys** to navigate the active selection up, down, left, or right across branches.
- **Context Menu**: Right-click any box (or press `Shift + F10`) to open the action menu (*Open Person*, *Make Root*, *Copy Name*).

### Export a publication-quality PDF

1. Select **Export PDF...** in the report toolbar.
2. Choose your page size (Letter, Legal, Tabloid, A4, A3).
3. Select **Orientation** (Landscape is recommended for pedigree charts).
4. Choose your **Fit Mode**:
   - **Fit to single page**: Scales the entire pedigree onto one sheet (ideal for digital sharing or poster printing).
   - **Tile across multiple pages**: Splices large pedigrees across a grid of standard sheets (e.g., 2 $\times$ 2 pages) at 100% scale with printed cut lines for assembly.
5. Review the vector print preview.
6. Select **Export PDF**.

## Practical use cases

- **Evaluating direct line research completeness:** Display 6 or 8 generations with **Leave Space for Unknown Ancestors** enabled to spot blank gaps in your ancestral lines at a glance.
- **Lineage society applications:** Export clean, uncrowded 5-generation pedigree charts for DAR, SAR, or Mayflower Society documentation packets.
- **Color-coding paternal versus maternal heritages:** Set **Color By** to *Lineage* to instantly distinguish the father's ancestral lines from the mother's ancestral lines.

## Good to know

- Living and private individuals are automatically protected: names render as **Private**, and all vital dates, places, and photos are redacted while preserving line geometry.
- The chart renders using pure vector geometry (`ChartScene`); text remains razor-sharp at any zoom level, and exported PDFs contain real vector text and lines rather than pixelated raster images.
