# Extraction proposals list

![Extraction proposals list](images/user-guide/extraction-proposals.png)

The Extraction Proposals List displays individual structured claims generated from document evidence extraction runs. Open this screen when you want to survey all pending claim candidates from a document, filter proposals by status, or inspect raw machine claims before adjudicating them into your tree.

## What you see

- **Document Filter Bar:** Allows you to filter the proposal list by specific source documents, batches, or extraction runs.
- **Status Filter Tabs:** Switch between **All**, **Pending / Proposed**, **Accepted**, **Rejected**, and **Disputed** proposals.
- **The Proposals Grid:** A virtualized DataGrid showing:
  - **Claim Subject:** The candidate persona or individual the claim describes.
  - **Claim Category:** Classified as *Name*, *Event / Fact*, *Relationship*, or *Characteristic*.
  - **Proposed Value:** The exact extracted detail (e.g., `Birth: 14 Aug 1862`, `Occupation: Blacksmith`, or `Father: John Hale`).
  - **Stated Evidence Text:** The exact snippet from the document transcription supporting the claim.
  - **Status:** Current adjudication status badge.
- **Actions Toolbar:** Buttons to **Review Proposals** (opens the interactive Proposal Review Cards), **Accept**, **Reject**, or **Delete**.

## Common tasks

### Inspect pending proposals for a document

1. Select the source document from the document dropdown at the top of the panel.
2. Ensure the **Pending / Proposed** tab is selected.
3. Review the extracted claim rows to verify that all relevant people and events mentioned in the document were captured.

### Launch the card review interface

1. Select **Review Proposals** in the toolbar.
2. The interactive **Proposal Review Cards** interface opens, presenting each claim one by one with tools to link personas, accept facts, or resolve conflicts.

### Bulk reject peripheral claims

1. Historical documents often mention non-relatives (such as neighboring landowners in a deed or court clerks in a marriage register).
2. Select the rows for these peripheral claims in the grid using **Ctrl + Click** or **Shift + Click**.
3. Select **Reject**.

The selected claims are marked as rejected and hidden from the pending review queue, preserving an audit trail of why they were not adopted into the family tree.

## Practical use cases

- **Quality auditing AI extraction outputs:** Review all claims extracted from a difficult 18th-century handwritten document in a single tabular view to verify that names and dates were read accurately before integrating them into your tree.
- **Tracking disputed evidence:** If an informant's testimony in an equity court dispute contradicts established facts, mark the extracted assertions as **Disputed**. They remain preserved in the evidence layer without contaminating your verified tree conclusions.

## Good to know

- Deleting a proposal completely removes it from the database; rejecting a proposal retains the claim with a `rejected` status for research audit records.
- Each proposal retains an immutable link to the exact line and word coordinates in the source document where the evidence was found.
- The list updates in real time as claims are accepted or modified in the Review Cards or Review Queue.
