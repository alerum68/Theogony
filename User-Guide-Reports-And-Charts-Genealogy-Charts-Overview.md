# Genealogy charts overview

Theogony provides 11 interactive genealogy chart layouts built with high-precision vector geometry on screen and in vector PDF exports. Each style is purpose-built to answer specific genealogical questions, from direct ancestral pedigrees to radial descendant rings and extended collateral networks.

## The 11 Chart Layouts

### 1. Pedigree Chart
- **What it shows:** Direct ancestral line (parents, grandparents, great-grandparents) extending from left to right.
- **When to use:** Classic ancestral overview focusing exclusively on direct biological or legal ascendants.

### 2. Ancestor with Siblings
- **What it shows:** Direct ancestor line along with sibling brackets beside each ancestor.
- **When to use:** Researching complete family groups across ancestral generations without losing the direct line.

### 3. Descendant (Top-Down)
- **What it shows:** Direct descendants hanging downwards from the progenitor couple, with spouses grouped on single rows.
- **When to use:** Tracking family branches downwards across generations like a traditional family tree.

### 4. Descendant (Left-Right)
- **What it shows:** Direct descendants spreading horizontally from left to right across generational columns.
- **When to use:** Wide descendant trees where vertical screen space is constrained.

### 5. Hourglass Chart
- **What it shows:** Ancestors stacked upward and descendants hanging downward from a single focal individual.
- **When to use:** Complete generational perspective centered on a single person (e.g., yourself or an immigrant ancestor).

### 6. Bow Tie Chart
- **What it shows:** Paternal ancestors on the left half, maternal ancestors on the right half, and descendants hanging below.
- **When to use:** Clear, balanced visual separation of paternal and maternal ancestral lines.

### 7. Fan Chart
- **What it shows:** Concentric ring segments spanning 180°, 270°, or 360° centered on the focal root.
- **When to use:** Compact radial representation of up to 12 ancestral generations on a single poster or page.

### 8. Dandelion Chart
- **What it shows:** Weighted spokes radiating from the center to ancestral nodes, with spoke angles proportional to branch size.
- **When to use:** Visualizing ancestral completeness and relative line depth in a clean radial network.

### 9. Embroidery Chart
- **What it shows:** Radial descendant rings spanning 360° with outer spouse bands along each branch.
- **When to use:** Circular descendant display highlighting partner linkages and family branch proportions.

### 10. Trellis Chart
- **What it shows:** Comprehensive network including collateral relatives (aunts, uncles, nieces, nephews, cousins) up to 5,000 individuals.
- **When to use:** Exploring extended family connections, intermarried neighbor families, and community networks.

### 11. Kinship Chart
- **What it shows:** The exact genealogical path connecting two chosen individuals up to their nearest common ancestor couple, with a calculated kinship label.
- **When to use:** Verifying relationship paths (e.g., "2nd cousin once removed") and demonstrating proof of kinship.

---

## Chart Customization Options

Open the **Options...** popover in the report toolbar to customize any active chart:

- **Generations:** Adjust the depth of generations displayed (from 3 to 12 generations).
- **Name Format:** Select between *Given Surname* ("Mary Hale"), *Surname, Given* ("Hale, Mary"), or *Given Only*.
- **Show Dates:** Toggle birth and death date ranges.
- **Show Places:** Display birth and death locations when recorded.
- **Show Photos:** Display portrait photos within person boxes.
- **Color By:** Color nodes by *None*, *Sex* (blue/pink), *Generation* (distinct color ramp per tier), or *Lineage* (paternal vs. maternal).
- **Fan Span:** For fan charts, select between 180° (half circle), 270° (three-quarter circle), or 360° (full circle).
- **Leave Space for Unknown Ancestors:** In pedigree layouts, reserves blank placeholder boxes for missing ancestors to keep generational alignment consistent.
- **Kinship Selector:** When viewing a Kinship Chart, provides an **Other Person** picker to choose the second relative to compare against the root person.

---

## Viewport Controls and Navigation

All charts support high-performance panning, zooming, and keyboard navigation:

### Mouse and Touch
- **Pan:** Click and drag anywhere on the canvas background.
- **Zoom:** Hold **Ctrl** and scroll the mouse wheel, or use pinch gestures on touchpads.
- **Select Person:** Single-click any person box or segment.
- **Re-root Chart:** Double-click any person box to make them the focal root.
- **Context Menu:** Right-click a person box (or press `Shift + F10`) to open actions (*Make Root*, *Open Person*, *Copy Name*).

### Keyboard Navigation
| Key | Action |
| --- | --- |
| `Arrow Keys` | Move selection to nearest neighboring person box |
| `+` / `=` | Zoom in |
| `-` | Zoom out |
| `0` | Fit entire chart to viewport |
| `Enter` | Re-root chart on selected person |
| `Shift + F10` | Open context menu for selected person |

---

## Exporting Publication-Quality Vector PDFs

Click **Export PDF...** in the toolbar to generate publication-grade PDF charts:

- **Standard Page Sizes:** Letter, Legal, Tabloid, A4, A3.
- **Orientation:** Portrait or Landscape.
- **Fit Mode:**
  - **Fit to single page**: Scales the entire chart to fit onto one sheet (ideal for digital sharing or poster plotters).
  - **Tile across multiple pages**: Splices large charts across a grid of standard sheets (e.g., 2 $\times$ 3 pages) at 100% scale, complete with printed alignment marks and cut guides for assembly.
- **Print Palette**: Exported PDFs use an archival print palette (Newsreader serif typography, dark ink, and subtle rules) that remains razor-sharp at any resolution.

---

## Privacy and Living Person Redaction

Living and private individuals are automatically protected across all chart styles:
- Names render as **Private**.
- All birth dates, marriage dates, death dates, places, and portrait photos are hidden.
- Family links and chart geometry remain intact so the structural integrity of the tree is never broken.
