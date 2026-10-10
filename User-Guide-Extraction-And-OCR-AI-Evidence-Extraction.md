# AI evidence extraction

![AI evidence extraction](images/user-guide/extraction-panel.png)

The AI Evidence Extraction panel uses generative AI to analyze transcribed document text and extract structured genealogical claims, candidate personas, dates, places, and family relationships. Open this screen when you have transcribed a document and want to transform the narrative text into candidate assertions ready for adjudication.

## What you see

- **Document Source Header:** Displays the active document name, its master citation, and the transcribed text being analyzed.
- **Extraction Template Selector:** 
  - Choose from pre-configured source-type templates (such as *Federal Census*, *Birth Certificate*, *Marriage Record*, *Death Certificate*, *Will / Probate*, or *Military Draft*), or select custom user templates.
  - Includes a link to open the **Templates Manager** to edit or build custom templates.
- **Model and Execution Controls:**
  - **Selected AI Model**: Shows the active model (e.g., `gemini-3.5-flash-lite` or `gemini-2.5-flash`).
  - **Estimate Tokens & Cost**: Calculates anticipated token usage and cost before dispatching any API call.
  - **Run Extraction**: Submits the transcribed text and template schema to the model.
- **Extraction Results Preview:** Displays real-time structured candidate claims (names, ages, relationships, event dates, and places) parsed from the document.
- **Submit to Review Queue:** Sends all generated proposals to the Review Queue for human verification.

## Common tasks

### Extract evidence from a census record

1. Open a transcribed census document in **Promoted Media** or the **Extraction Panel**.
2. In the template picker, select **US Federal Census (1880–1940)**.
3. Select **Estimate Tokens & Cost** to review the prompt size and anticipated cost.
4. Select **Run Extraction**.
5. Review the generated candidate personas (head of household, wife, children, boarders) and their asserted ages, birthplaces, and parent birthplaces.
6. Select **Send to Review Queue**.

The candidate claims enter your evidence holding area without touching your tree conclusions.

### Manage and customize extraction templates

1. Select **Manage Templates...** in the extraction toolbar.
2. In the **Templates Manager**, you can:
   - **Duplicate** an existing template (e.g., duplicating *Will / Probate* to create a specialized *Colonial Estate Inventory* template).
   - **Edit** the prompt instructions and expected field schema. Each save creates a new immutable version.
   - **Preview** the template against an open staged document to test the output quality.
   - **Set as Default** for a specific source type so Theogony selects it automatically whenever that document category is opened.
   - **Export / Import** templates as `.json` files to share with other genealogists.

## Practical use cases

- **Complex probate files naming dozens of heirs:** Wills often mention grandchildren, married daughters with new surnames, sons-in-law, and executors across multiple pages. The extraction model parses out each person and their asserted relationship, preventing you from missing obscure collateral relatives.
- **Multi-family tenement census pages:** When a census page lists several families living together or lodgers who might be unrecorded relatives, AI extraction captures every individual on the page as distinct personas in one step.
- **Standardizing foreign vital certificates:** Use specialized templates to translate and extract key dates, witness names, and parish locations from transcribed civil or church certificates.

## Good to know

- **Evidence is never written directly to conclusions:** Machine output lands strictly in the evidence layer as *proposals*. Nothing is added to an individual's concluded timeline or family tree until you explicitly accept it in the **Review Queue** or **Review Cards**.
- Cloud AI requests are restricted by repository Terms of Service: documents linked to restricted repositories (such as Ancestry or MyHeritage) are blocked from cloud extraction to preserve privacy and contract terms.
- API keys are stored securely in your operating system keychain and are never saved in the database or plain-text settings files.
