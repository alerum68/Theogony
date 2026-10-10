# Browse facts by type

![Browse facts by type](images/user-guide/facts-by-type.png)

The Browse Facts by Type screen groups every life event and assertion across your entire tree by its fact category (such as *Birth*, *Marriage*, *Death*, *Census*, *Occupation*, or *Military Service*). Open this screen when you want to conduct cross-tree analysis, audit specific record groups, or survey a historical event across your family network.

## What you see

- **Fact Type Selector:** A dropdown menu at the top left allowing you to choose any fact category present in your database.
- **Search and Filter Controls:** Quick-filter inputs to narrow the displayed events by person name, date year, or geographic location.
- **The Cross-Tree Facts Grid:** A virtualized DataGrid displaying:
  - **Person Name:** The individual who experienced or participated in the event.
  - **Date:** The recorded historical date (e.g., `12 May 1864` or `abt 1820`).
  - **Place:** The jurisdiction where the event took place.
  - **Description / Value:** Any supplementary details (such as occupation titles, military units, or burial plot identifiers).
  - **Citations:** The number of documentary citations verifying the assertion.
- **Summary Count:** Displays the total number of recorded instances of the selected fact type in the tree.

## Common tasks

### Audit all instances of a fact type

1. Open the **Fact Type** dropdown menu at the top of the panel.
2. Select a category, such as **Military Service** or **Census**.
3. The grid instantly updates to show every individual in your database with that fact recorded.

### Filter events by location or year

1. With a fact type selected (for example, **Death**), type a year (such as `1918`) or a location (such as `Philadelphia`) into the filter bar.
2. The list filters dynamically, showing all deaths that occurred in that place or time.

### Jump to an individual from a fact row

1. Locate an event of interest in the grid.
2. Double-click the row or press **Enter**.

The individual's full **Person** record opens immediately in the workbench, allowing you to edit the event or examine its evidence citations.

### Export fact lists to a spreadsheet

1. Select one or more rows in the grid (use **Ctrl + A** to select all matching events).
2. Press **Ctrl + C** to copy the data as tab-separated values.
3. Paste (**Ctrl + V**) into Excel or Google Sheets to build custom research checklists or timelines.

## Practical use cases

- **Epidemic and historical mortality studies:** Filter the **Death** fact type for `1918` to identify all family members lost during the global influenza pandemic, or filter for `1832` in London to investigate cholera outbreak victims.
- **Census research audits:** Select the **Census** fact type and sort by date to verify that every family branch has entries for the 1850, 1860, 1870, and 1880 Federal Censuses, instantly highlighting missing decades.
- **Military cohort analysis:** Select **Military Service** to review all ancestors who served in the American Civil War, Revolutionary War, or World War I, comparing enlistment locations and regiment details.
- **Standardizing occupational titles:** Select **Occupation** to spot variations and archaic terms (such as *Cooper*, *Cordwainer*, *Ostler*, or *Blacksmith*) across generations.

## Good to know

- Sorting any column (such as Date or Place) sorts the entire cross-tree dataset instantly.
- The list includes events from both primary individuals and family group records.
- Facts with zero citations are clearly highlighted, making this view an invaluable tool for finding unsourced assertions that need documentary proof.
