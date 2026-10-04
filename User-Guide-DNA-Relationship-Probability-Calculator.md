# Relationship probability calculator

![Relationship probability calculator](images/user-guide/relationship-probability.png)

Calculate statistical probabilities of relationship degrees for shared centimorgan values and filter your imported genetic matches. Open this screen when you want to evaluate how an unknown DNA match fits into your pedigree or compare Y-STR markers between tested lines.

## What you see

The **Check for pedigree collapse** button at the top opens the pedigree collapse analysis tool to evaluate duplicate ancestors in your tree.

The **Shared-cM relationship probability** area provides a **Shared cM** input box and a **Calculate** button to estimate genealogical relationships from total shared centimorgans.

The **Browse your matches** section contains a filter toolbar with an **All kits** dropdown, a **Search matches** field, **Min cM** and **Max cM** thresholds, provider checkboxes, and a region selector. The grid lists matches with columns for match name, tested kit, shared centimorgans, predicted relationship, parental side, ethnicity regions, and action buttons for **Check odds** and **Notes**.

The **Estimated relationships** table appears after a calculation, showing candidate relationships ranked by probability percentage, odds ratio, average centimorgans, and expected range.

The **Y-STR distance calculator** section provides **Kit A** and **Kit B** dropdown selectors to calculate genetic distance and estimated generations to a common paternal ancestor.

The **Anchors** table lists individuals linked to your tree who anchor specific branches to maternal or paternal sides.

## Common tasks

### Calculate relationship odds for a shared cM value

1. Enter a number into the **Shared cM** input field.
2. Select **Calculate**.

The **Estimated relationships** table displays possible relationships sorted by statistical likelihood.

### Filter matches and check relationship odds

1. Type a name into the **Search matches** input field or enter bounds into **Min cM** and **Max cM**.
2. Select **Check odds** on a match row in the table.

The calculator populates the **Shared cM** field with the match's value and displays the estimated relationship probabilities.

### Compare Y-STR genetic distance between kits

1. Choose the first kit from the **Kit A** dropdown in the Y-STR section.
2. Choose the second kit from the **Kit B** dropdown.

The panel calculates the genetic distance and reports the estimated generations to the common ancestor.

### Record notes for a match

1. Locate the person in the match grid.
2. Select **Notes** on the corresponding row.
3. Type your research notes into the dialog and close the window.

The application saves the notes against the match record.

## Good to know

- Calculations use statistical distributions based on published Shared cM Project data.
- Selecting **Check odds** on any match row automatically recalculates the probability table without clearing your search filters.
