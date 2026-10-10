# Review queue

![Review queue](images/user-guide/review-queue.png)

The Review Queue is the central clearinghouse for all pending evidence in Theogony. Open this screen when you want to review unattached personas extracted from historical documents, manage unreviewed claims, or adjudicate incoming evidence before it enters your tree conclusions.

## What you see

- **Queue Filter Bar:** Filter queue items by source document, candidate persona, or item type (e.g., *Unattached Personas*, *Unreviewed Facts*, *Potential Duplicates*).
- **The Evidence Review Grid:** A virtualized DataGrid displaying:
  - **Persona / Subject:** The name of the person as written in the original historical document.
  - **Source Document:** The specific record (e.g., *1860 US Census* or *St. Paul Parish Register*) where the evidence was found.
  - **Proposed Claims:** The count and summary of asserted life events, dates, and relationships.
  - **Confidence / Status:** Processing state and informant quality level.
- **Queue Action Toolbar:** 
  - **Review Selected in Cards**: Opens the interactive step-by-step Proposal Review Cards interface.
  - **Link to Existing Person**: Manually associates a candidate persona with a conclusion person in your database.
  - **Create New Person**: Initializes a new individual in your tree from the persona's details.
  - **Dismiss / Archive**: Removes peripheral or unneeded evidence from the active queue.

## Common tasks

### Work through pending document claims

1. Select a document batch in the **Queue Filter Bar**.
2. Select **Review Selected in Cards** in the toolbar.
3. Theogony launches the **Proposal Review Cards** interface, allowing you to evaluate each claim, match personas to ancestors, and accept or reject proposed facts.

### Manually link an unattached persona to an ancestor

1. In the Review Queue grid, select an unattached persona (for example, a persona named `"Polly Hale"` extracted from a marriage bond).
2. Select **Link to Existing Person**.
3. In the search dialog, find and select `"Mary Elizabeth Hale"` in your tree.
4. Select **Confirm Link**.

The persona is permanently connected to Mary Elizabeth Hale as an evidence source, and its associated assertions are linked to her record.

### Review unattached personas from deleted individuals

1. When you delete individuals from your tree, their underlying document evidence is never erased; the personas move directly to the Review Queue.
2. Filter the queue by **Unattached Evidence**.
3. Re-link these personas to other relatives or keep them in the evidence layer for future correlation.

## Practical use cases

- **Controlled evidence intake:** Avoid the common pitfall of other genealogy programs where importing an index or record dumps hundreds of unverified names directly into your tree, cluttering your pedigree with duplicates and speculative data. The Review Queue acts as an essential quarantine layer.
- **Resolving identity conflicts:** When two people in the same county share the exact same name, keep their respective document personas in the Review Queue until you have assembled enough land and probate records to definitively separate them into distinct individuals.

## Good to know

- Evidence in the Review Queue never appears on published pedigree charts, family group sheets, or standard GEDCOM exports until you accept it.
- Items can remain in the Review Queue indefinitely without expiring or cluttering your primary family lists.
- You can leave the Review Queue at any time; your progress is automatically saved.
