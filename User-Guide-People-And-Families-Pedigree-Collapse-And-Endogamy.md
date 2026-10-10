# Pedigree collapse and endogamy

![Pedigree collapse and endogamy](images/user-guide/pedigree-collapse.png)

The Pedigree Collapse and Endogamy panel evaluates duplicate ancestors and intermarriage within an individual's ancestral lines. Open this screen when you want to measure pedigree collapse, calculate coefficients of relationship, or understand why DNA matches in certain branches appear much closer genetically than their paper trail suggests.

## What you see

- **Focal Individual Selector:** Choose the target person whose ancestral tree is being evaluated.
- **Summary Metrics Panel:**
  - **Theoretical vs. Actual Ancestors:** Compares the theoretical number of ancestor slots (e.g., 64 at generation 6) against the number of unique individuals found.
  - **Pedigree Collapse Percentage:** Quantifies the proportion of duplicated ancestral slots across the tree.
  - **Inbreeding Coefficient ($F$) / Coefficient of Relationship:** Mathematical measure of genetic overlap resulting from shared ancestors.
- **Duplicate Ancestors Table:** A DataGrid listing every individual who appears more than once in the ancestral tree, showing:
  - **Ancestor Name:** The individual duplicated in the tree.
  - **Appearance Count:** The number of distinct slots they occupy.
  - **Generations:** The ancestral generation numbers where they appear (e.g., *Gen 4 and Gen 5*).
  - **Ahnentafel Numbers:** The exact slot positions occupied in the pedigree.
- **Ancestral Paths Detail:** Shows the complete generational paths connecting the focal individual to each occurrence of the duplicate ancestor.

## Common tasks

### Analyze pedigree collapse for an ancestor

1. Open the **Pedigree Collapse** view from the view manager.
2. Select the focal individual from the person selector (or select someone in the Pedigree canvas and open this panel).
3. The panel evaluates all ancestral lines up to the maximum available generation and populates the duplicate ancestors table.

### Inspect multiple lines to a shared ancestor

1. In the **Duplicate Ancestors** table, select an ancestor who appears multiple times (for example, a great-great-grandfather who appears twice).
2. Look at the **Ancestral Paths** pane below.
3. Compare the two distinct lineages (e.g., Path A via the father's maternal line, and Path B via the mother's paternal line) to pinpoint where the cousin marriage occurred.

### Evaluate endogamous DNA inflation

1. Review the **Endogamy Impact** metric in the summary panel.
2. Note the calculated inflation factor. When evaluating autosomal DNA matches descending from this ancestor, this metric warns you if expected centimorgan ranges need to be adjusted upward.

## Practical use cases

- **Endogamous population research:** Essential when researching endogamous communities—such as Ashkenazi Jewish lineages, French-Canadian Acadian families, early colonial New England settlements, Mennonite communities, or isolated island populations—where intermarriage within the community was customary across centuries.
- **Disentangling inflated DNA matches:** If two known 3rd cousins share 250 cM (an amount typical of a 2nd cousin or 1st cousin twice removed), this view helps you prove that the excessive shared DNA is due to three shared ancestral couples rather than a single recent connection.
- **Detecting pedigree loops in genealogical proof arguments:** When building a formal proof argument under the Genealogical Proof Standard (GPS), identifying duplicate ancestral lines ensures that evidence from collateral relatives is evaluated accurately and not counted multiple times as independent proof.

## Good to know

- Pedigree collapse is distinct from pedigree completeness. A tree can be 100% complete across six generations while exhibiting significant pedigree collapse due to first or second-cousin marriages.
- Pedigree collapse calculations are performed purely in local memory from your database and do not require internet access.
- When exporting genealogical charts (such as Fan or Trellis charts), Theogony respects these duplicate lines without creating infinite rendering loops.
