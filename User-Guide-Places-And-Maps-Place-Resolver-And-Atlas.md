# Place resolver and atlas

![Place resolver and atlas](images/user-guide/atlas.png)

The Place Resolver and Atlas provides interactive mapping and geographic resolution for your family tree. Open this screen to visualize where your ancestors lived, resolve unmapped location strings into precise coordinates, evaluate historical jurisdiction boundaries, and trace family migration paths over time.

## What you see

- **Interactive Map Viewport:** A responsive Leaflet map (using OpenStreetMap cartography) displaying cluster pins for ancestral life events (births, marriages, residences, deaths, and burials).
- **Unresolved Places Panel:** A sidebar listing location strings imported from records or GEDCOM files that lack geographic coordinates or standardized jurisdictions.
- **Resolution Resolver Toolbar:**
  - **Search & Suggest:** Geocoding tool to search for matching historical and modern places.
  - **Coordinate Inputs:** Displays exact Latitude and Longitude.
  - **As-Of Date Field:** Enables time-aware jurisdiction lookup (for example, evaluating a location as it was defined in `1840` versus `1890`).
- **Event Cluster Inspector:** Clicking any map pin or region displays the specific ancestors and historical events located within that area.

## Common tasks

### Resolve an unmapped place string

1. Select an item from the **Unresolved Places** list (for example, `"Point Pleasant, Mason Co."`).
2. The resolver tool suggests the standard hierarchy: `Point Pleasant, Mason County, West Virginia, United States`.
3. Select **Apply Resolution** to attach the standardized hierarchy and geographic coordinates to the place.

The location is plotted onto the map, and all events linked to that place update immediately.

### Time-aware historical jurisdiction lookup

1. When researching an ancestor who lived in an area whose boundaries changed over time (for example, western Virginia prior to the creation of West Virginia in 1863):
2. Enter the place string and specify the historical event year in the **As-Of Date** field (e.g., `1850`).
3. Theogony resolves the historical jurisdiction as of that date (`Mason County, Virginia`), while retaining the geographic coordinates that point to its physical location on the modern map.

### Trace an ancestor's migration route

1. Select an ancestor in the active entity context.
2. In the Atlas, choose **Show Life Events for Selected Person**.
3. The map displays a sequential numbered path linking their birth place, census residences, marriage location, military posts, and cemetery, illustrating their lifetime journey.

### Inspect regional ancestor clusters

1. Pan and zoom into a specific geographic region (such as southeastern Pennsylvania or the Shenandoah Valley).
2. Click any clustered map marker.
3. The **Event Inspector** displays all family members who had events within that radius, helping you spot collateral relatives who lived in neighboring townships.

## Practical use cases

- **Evaluating geographic plausibility:** Catch impossible data errors early. If an ancestor is recorded as giving birth in Ohio in March 1872 and another child is recorded in Germany in July 1872, seeing them plotted on the map immediately highlights the conflict for resolution.
- **Historic boundary shift analysis:** Understand which courthouse holds the records. A family living on the exact same farm between 1780 and 1850 may appear in three different counties without ever moving, because the county was repeatedly subdivided. Time-aware place resolution clarifies where deed and probate records were filed.
- **Correlating DNA match locations:** When working with mystery DNA matches whose family trees share a specific ancestral county, map their locations alongside your own family lines to pinpoint common geographic origins.

## Good to know

- Map rendering and geocoding operate smoothly without sending private family details to third parties.
- Zooming and panning support standard mouse wheel and drag gestures, as well as on-screen zoom controls.
- Places without assigned coordinates appear in the Unresolved Places panel until resolved, ensuring your geographic dataset remains tidy and complete.
