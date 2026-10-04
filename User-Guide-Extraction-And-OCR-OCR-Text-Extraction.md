# OCR text extraction

![OCR text extraction](images/user-guide/ocr-panel.png)

Optical character recognition turns historical documents and images into searchable plain text, bounding boxes, and multi-column document transcriptions. Open this panel when you want to transcribe an attached source or document without typing the text by hand.

## What you see

The action toolbar holds the primary controls for running character recognition. The available options include **Extract PDF Text**, **Extract (Tesseract)** for local processing, and **Extract (Gemini AI)** for cloud processing. 

The history combobox lists previous text extraction results for the active item. You can switch between prior runs to compare different extraction engines or dates.

The meta bar displays technical details for the selected extraction result. It shows the engine, model name, processing cost, and the date and time of the run.

The text area displays the full transcribed plain text for the selected extraction result. This area is read-only.

## Common tasks

### Extract text using Tesseract

1. Select **Extract (Tesseract)** in the action toolbar.
2. Wait for the progress indicator to finish processing.
3. View the generated text in the text area.

### Extract text using Gemini AI

1. Select **Extract (Gemini AI)** in the action toolbar to open the cost estimate dialog.
2. Confirm the repository and cost details in the dialog to start the run.
3. Wait for the background process to complete and load the results.

### Copy extracted text to the clipboard

1. Select a previous extraction result from the history combobox if you have multiple runs.
2. Select **Copy Text** in the action toolbar.

## Good to know

- The **Extract PDF Text** button only appears if the selected document uses a PDF media type.
- The local Tesseract engine requires Tesseract to be installed on your computer.
- The Gemini AI engine requires an API key saved in the program settings.
