# DNA review and kit manager

![DNA review and kit manager](images/user-guide/dna-review.png)

The DNA Review and Kit Manager dashboard is the central hub for managing genetic genealogy kits, importing match lists, and examining shared centimorgan data across testing companies. Open this screen when you want to import a new raw match file, link a DNA kit to a person in your tree, or search across your genetic matches.

## What you see

- **Kits Management Toolbar:**
  - **Import Matches...**: Opens the file importer supporting standard CSV and TSV match downloads from AncestryDNA, FamilyTreeDNA, GEDmatch, 23andMe, and MyHeritage.
  - **Add Kit / Tester**: Manually creates a new kit entry.
  - **Filter by Testing Company**: Filters your kit list by testing laboratory.
- **The DNA Kits List:** Displays all imported kits in your database:
  - **Kit Identifier and Tester Name**: The test subject or account pseudonym.
  - **Testing Platform**: Identifies the source company.
  - **Linked Tree Individual**: The person in your family tree linked to this genetic sample.
  - **Home Kit Indicator**: Designates your primary reference kit used across analysis tools.
  - **Total Match Count**: Number of imported genetic cousins for this kit.
  - **Y-DNA / mtDNA Haplogroups**: Displayed when available from the test results.
- **Match Explorer Grid:** When a kit is selected, the lower table lists all matching individuals, displaying:
  - **Match Name**: The genetic cousin.
  - **Total Shared cM**: Total centimorgans shared.
  - **Longest Segment**: Length of the largest continuous matching block.
  - **Estimated Relationship**: Company or standard estimated kinship degree.
  - **Linked Person Badge**: Highlights matches who have been identified and placed into your tree.

## Common tasks

### Import an autosomal match list

1. Download your match list file (CSV or TSV) from your testing provider (e.g., AncestryDNA or GEDmatch).
2. In Theogony, select **Import Matches...** in the toolbar.
3. Select your downloaded file.
4. Choose or create the tester kit to associate with the import.
5. Select **Import**.

Theogony processes the matches, parses total shared cMs and longest segments, and displays them immediately in the match explorer.

### Link a DNA kit to an ancestor in your tree

1. Select a kit row in the top kit list.
2. Select **Link to Person**.
3. Search for the tested individual in your family tree (for example, yourself, your parent, or a tested cousin).
4. Select **Confirm Link**.

The kit is now tied to that individual. Chromosome browser data and cluster matrices will now cross-reference their family pedigree.

### Designate your Home Kit

1. Right-click the kit belonging to the primary researcher (or focal tester).
2. Select **Set as Home Kit**.

This kit becomes the default reference kit across the Leeds Cluster Matrix, Chromosome Browser, and Migration Map.

### Search and filter matches

1. Use the search field above the Match Explorer grid to find matches by name or ancestral surname.
2. Filter by minimum shared centimorgans (e.g., typing `50` to view only matches sharing 50 cM or more).
3. Select any match row to view their segment breakdown or in-common-with matches.

## Practical use cases

- **Cross-company match consolidation:** Manage kits from AncestryDNA, FamilyTreeDNA, and GEDmatch in one unified local environment, avoiding the need to juggle multiple browser tabs.
- **Adoptee and unknown parentage research:** Import match files for an adoptee to establish a baseline of close matches, identify top matches sharing over 90 cM, and feed them directly into the **Leeds Cluster Matrix**.
- **Auditing family testing coverage:** Review your kit list to identify which ancestral branches have been verified by living testers (e.g., verifying that you have kits representing both your paternal grandfather's and maternal grandmother's lines).

## Good to know

- DNA match data in Theogony is stored locally within your `.theo` database file. Your genetic data is never uploaded to external servers.
- Importing the same match file multiple times is handled idempotently; existing match records are updated without creating duplicates.
- When exporting public trees or GEDCOM files, DNA links belonging to living individuals are automatically protected and redacted.
