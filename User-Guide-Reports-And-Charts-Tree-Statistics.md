# Tree statistics

The Tree Statistics dashboard provides deep demographic and genealogical analytics for your family database. Powered by **webR** (the R statistical computing language compiled to local WebAssembly), all calculations and charts are generated directly on your computer with scientific precision and zero privacy risk.

## What you see

- **Statistics Navigation Tabs:**
  - **Demographics**: Lifespans, age at marriage, family sizes, and birth seasonality distributions.
  - **Pedigree Completeness**: Percentage completeness of your direct ancestral tree across generations 1 through 12.
  - **DNA Metrics**: Statistical breakdown of imported genetic matches and segment lengths.
- **Demographic Visualization Canvas:**
  - **Lifespan Distribution Histogram**: Plots age at death across centuries (e.g., comparing 18th-century lifespans against 20th-century longevity).
  - **Marriage Age Analysis**: Visualizes the average age of men and women at first marriage over time.
  - **Children per Family**: Bar chart of family sizes, identifying average numbers of offspring per generation.
  - **Birth Seasonality Radar**: Monthly distribution of births across your tree, illustrating seasonal birth patterns in agrarian eras.
- **Completeness Table:** A detailed table listing each ancestral generation tier, showing theoretical slots, identified ancestors, and percentage completeness.

## Common tasks

### Measure your ancestral tree completeness

1. Select **Statistics** on the activity bar.
2. Click the **Pedigree Completeness** tab.
3. Review the generational breakdown:
   - **Gen 1 (Subject)**: 100% (1/1)
   - **Gen 2 (Parents)**: 100% (2/2)
   - **Gen 3 (Grandparents)**: 100% (4/4)
   - **Gen 4 (Great-Grandparents)**: 87.5% (7/8)
   - **Gen 5 (2nd Great-Grandparents)**: 75% (12/16)
4. Identify at which generational tier your tree drops below 50% completeness, establishing a clear metric for future research focus.

### Explore historical demographic shifts

1. Click the **Demographics** tab.
2. Examine the **Lifespan Distribution** chart.
3. Compare infant and child mortality rates in pre-1850 branches against modern branches, or observe historical spikes corresponding to yellow fever, cholera, or smallpox epidemics.

## Practical use cases

- **Evaluating historical research accuracy:** If the **Age at First Marriage** chart reveals a female ancestor married at age 9, or a father who was 75 years older than his first child, use the outlier flags to identify and investigate potential clerical or transcription errors in your data.
- **Quantifying research progress for family presentations:** Include objective pedigree completeness percentages (e.g., *"Our 5-generation tree is currently 94% complete with 30 of 32 ancestors identified"*) in family history books or research summaries.

## Good to know

- Statistics run entirely on your local CPU via WebAssembly; no data is ever transmitted to an external analytics server.
- Living individuals are appropriately factored into calculations without exposing private personal details.
- Charts can be exported as high-resolution images or vector graphics for inclusion in printed family history books.
