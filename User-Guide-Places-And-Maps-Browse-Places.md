# Browse places

![Browse places](images/user-guide/places.png)

The Browse Places screen manages the master geographic catalog of every town, parish, county, state, and country recorded in your family tree. Open this screen when you want to standardize location names, clean up spelling variations imported from GEDCOM files, or inspect which events occurred in a specific jurisdiction.

## What you see

- **Search and Filter Bar:** Allows you to find any geographic string across your database by typing any portion of a town, county, or country name.
- **Master Places Grid:** A virtualized DataGrid displaying:
  - **Standardized Place Name:** The primary hierarchical location string (e.g., `Springfield, Clark County, Ohio, United States`).
  - **Jurisdiction Levels:** Broken down by Country, State/Province, County, and Town/Parish.
  - **Coordinates:** Recorded Latitude and Longitude for mapping.
  - **Linked Events Count:** The total number of births, marriages, deaths, and censuses associated with that place.
- **Action Toolbar:** Buttons to **Add Place**, **Edit Place**, and **Merge Places**.
- **Place Details Pane:** Displays the full hierarchy, notes on historical county boundary changes, and a list of all ancestors who lived, were born, or died there.

## Common tasks

### Search for a location

1. Click into the search field at the top of the screen.
2. Type a place name (such as `Gallia` or `Somerset`).
3. The grid immediately filters to display all matching locations.

### Edit and standardize a place name

1. Select a place row in the grid.
2. Select **Edit Place** (or double-click the row).
3. Update the standardized string (for example, correcting an abbreviated `Somerset, Eng.` to `Somerset, England`).
4. Enter or refine the specific county or parish fields.
5. Select **Save**.

The updated place name is immediately reflected across all linked life events in your tree.

### Merge duplicate place names

1. If your tree contains duplicate entries from GEDCOM imports (for example, `London, England` and `London, Greater London, England`):
2. Select both place rows in the grid using **Ctrl + Click**.
3. Select **Merge Places**.
4. In the dialog, select which of the two versions should serve as the authoritative standardized name.
5. Select **Confirm Merge**.

Theogony re-links all events from the duplicate entry to the master record and removes the redundant place.

### Inspect all events at a place

1. Select a place row in the grid.
2. In the **Place Details** pane, review the list of linked events.
3. Click any individual or event row to navigate directly to their personal record.

## Practical use cases

- **GEDCOM place cleanup:** After importing an external GEDCOM file, use this view to identify abbreviations (like `PA` vs `Pennsylvania`), missing county names, and misspellings, consolidating them into clean, standardized entries.
- **Cluster and FAN club research:** Select a specific historical county (such as `Augusta County, Virginia`) to review every ancestor and associated family who lived there concurrently, making it easy to spot potential intermarriages and neighbor connections.
- **Preparing for on-site courthouse visits:** When planning a research trip to a specific county archives, filter for that county, export the linked ancestors (**Ctrl + C**), and take a focused checklist of probate, deed, and marriage records to search.

## Good to know

- Merging places is fully logged in **Edit History** and can be undone using **Revert**.
- Coordinates assigned to places are used by the **Atlas** and **Place Resolver** to plot family events on interactive maps.
- Theogony supports historical place strings, allowing you to preserve the exact historical name of a location alongside its modern geographic coordinates.
