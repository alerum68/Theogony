# AI evidence extraction

![AI evidence extraction](images/user-guide/extraction-panel.png)

The Extraction Panel uses generative AI to extract structured genealogical assertions, personas, dates, places, and relationships from transcribed document text. You open this screen when reviewing an OCR-processed document to turn its text into structured records.

## What you see

The top toolbar holds the main operational controls, including the **Source type** selector, the **Also send the original image** checkbox, and the **Extract…** and **Extract from image…** buttons. When you have multiple runs, a history menu appears here to let you switch between past extractions.

The metadata area displays run details such as the template, model, cost, status, and any suggestions from the model. 

The proposal section lists the extracted facts, personas, and relationships for review. You can reject individual proposals here or view the raw response.

## Common tasks

### Run an extraction

1. Select a document type from the **Source type** menu.
2. Select **Also send the original image** if you want to include the source image in the request.
3. Select **Extract…** to open the estimate dialog and confirm the run.
4. Watch the progress bar while the extraction runs and updates the results.

### Extract directly from an image

1. Select **Extract from image…** to open the one call dialog.
2. Confirm the settings in the dialog to start the run.
3. Monitor the progress bar until the results appear in the proposal section.

### Review proposals

1. Select **View raw response** if you need to inspect the complete JSON output from the model.
2. Select reject on any proposal you do not want to keep in the results.

## Good to know

Run OCR on the document before you start an extraction. The extraction reads the OCR text and proposes records, but nothing is added to your tree automatically.
