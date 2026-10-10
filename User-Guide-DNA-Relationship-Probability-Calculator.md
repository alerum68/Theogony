# Relationship probability calculator

![Relationship probability calculator](images/user-guide/relationship-probability.png)

The Relationship Probability Calculator determines the statistical likelihood of possible genealogical relationships for a given amount of shared DNA. Open this screen whenever you discover a new DNA match, want to evaluate what relationship degrees are genetically possible, or need to calculate the Time to Most Recent Common Ancestor (TMRCA) for Y-STR marker testing.

## What you see

- **Autosomal DNA Input Section:**
  - **Shared Centimorgans (cM)**: Numeric field to enter total shared cM (e.g., `224 cM`).
  - **Segment Count (Optional)**: Numeric field to enter the number of shared segments.
- **Probabilities Results Grid:** A ranked table displaying statistically viable relationships based on empirical Banyan and Blaine Bettinger's Shared cM Project distributions:
  - **Relationship Tier**: Groups candidate relationships sharing the same genetic distance (for example, *2nd Cousin / 1st Cousin Twice Removed / Half 1st Cousin Once Removed*).
  - **Statistical Probability (%)**: Percentage likelihood that the match falls into that specific tier.
  - **Empirical Range and Average**: Expected cM minimums, maximums, and averages for each candidate degree.
- **Endogamy and Pedigree Collapse Notice:** Direct link to open the **Pedigree Collapse** panel if you suspect endogamy or cousin marriages may have inflated the shared cM amount.
- **Y-STR TMRCA Calculator:** A dedicated section to calculate generation distances and probabilities for Y-DNA STR marker matches (e.g., comparing 37, 67, or 111-marker tests).

## Common tasks

### Calculate probabilities for an unknown match

1. Enter the total shared centimorgans reported by your testing company (for example, `450 cM`) into the **Shared Centimorgans (cM)** field.
2. The calculator evaluates the distributions and immediately renders the results table.
3. Review the ranked probabilities:
   - For 450 cM, you will see strong probabilities for *Half 1st Cousin*, *1st Cousin Once Removed*, *Half Great-Aunt/Uncle*, or *Great-Great-Aunt/Uncle*.
   - Relationships that are genetically impossible (such as *3rd Cousin* or *Full Sibling*) receive 0% probability and are excluded from the candidate list.

### Evaluate Y-STR genetic distance (TMRCA)

1. Navigate to the **Y-STR Calculator** section of the panel.
2. Select the tested panel size (e.g., *Y-37*, *Y-67*, or *Y-111*).
3. Enter the genetic distance (number of mutation mismatches, such as `GD = 2`).
4. The calculator displays the estimated **Time to Most Recent Common Ancestor (TMRCA)** with 50%, 90%, and 95% confidence intervals (for example, proving that the common paternal ancestor lived within 4 to 8 generations).

## Practical use cases

- **Ruling out proposed genealogical connections:** If an online family tree suggests a match is your 4th cousin, but your shared DNA is 185 cM, enter `185` into the calculator. The calculator reveals that a 4th cousin relationship has virtually 0% probability, proving that the match must share a much closer, unrecorded connection (such as a 2nd cousin once removed).
- **Evaluating multiple competing hypotheses:** When building a proof argument, cite the exact empirical probability percentage (e.g., *"A shared amount of 312 cM yields a 74% probability of a 2nd cousin tier relationship"*) to provide mathematical support for your conclusion.
- **Surname project validation:** Use the Y-STR TMRCA tool to confirm whether two men with the same surname who match on 67 markers shared a common ancestor in colonial America or further back in medieval Europe.

## Good to know

- Probabilities are based on peer-reviewed empirical datasets derived from tens of thousands of verified genealogical pairs.
- In endogamous populations (such as colonial islanders or Ashkenazi lineages), small segment accumulation can inflate total cM. If endogamy is present, consider the relationship one or two tiers further back than the raw cM suggests.
- You can copy the generated probability table to your clipboard with standard table selection and **Ctrl + C**.
