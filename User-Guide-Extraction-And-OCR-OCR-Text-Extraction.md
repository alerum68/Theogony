# OCR text extraction

![OCR text extraction](images/user-guide/ocr-panel.png)

The OCR Text Extraction panel runs Optical Character Recognition on historical document scans and extracts searchable text from digital PDFs. Open this screen when you want to convert an image of a certificate, will, census page, or newspaper clipping into editable, searchable text right on your local machine.

## What you see

- **Document Header:** Shows the active media file name, image resolution, and page count.
- **Engine Toolbar:**
  - **Run OCR**: Starts the recognition process using the active local engine (Tesseract or embedded PDF text-layer extraction).
  - **Language Selector**: Choose the primary language pack (e.g., *English*, *German*, *French*, *Fraktur*).
  - **Clear Text**: Discards the current transcription draft if you wish to re-run with different settings.
- **Transcription Editor Pane:** A full text editor displaying the recognized text. You can type directly into this pane to correct OCR typos, fix misunderstood numerals, or format line breaks.
- **Bounding Box Overlay:** When viewing the document alongside this panel, each recognized line or word is tied to geographic coordinates on the image canvas.
- **Save Status:** Displays whether the transcription is saved to the media record.

## Common tasks

### Run OCR on an imported scan

1. Open a document scan from **Media Staging** or **Promoted Media**.
2. Select **Run OCR** in the toolbar.
3. Theogony processes the image through your local Tesseract engine. Progress updates in the status bar.
4. When finished, the recognized text appears in the editor pane.

### Correct OCR transcription errors

1. Historical documents often have faint letters or smudges (for example, reading an archaic long `s` as an `f`, or misinterpreting `1883` as `1885`).
2. Click directly into the text in the **Transcription Editor Pane**.
3. Type your corrections.
4. Select **Save Transcription**.

The corrected text is permanently stored with the media item, ready for AI evidence extraction or citation copy.

### Extract text from a digital PDF

1. When you import a modern digital PDF (such as a downloadable death certificate from a state vital statistics department or a digitized book page with an existing text layer):
2. Select **Extract Text Layer**.
3. Theogony reads the embedded computer text directly without running lossy optical recognition, giving you an exact 100% accurate transcription in seconds.

## Practical use cases

- **Transcribing published county history biographies:** Run OCR across five pages of a family biographical sketch. Rather than typing out paragraphs by hand, let the OCR generate the initial draft, make quick typo fixes, and save hours of manual transcription.
- **Reading 19th-century probate ledgers:** Process typed or clearly written legal documents, inventories, and letters of administration, making their contents instantly searchable across your entire database.
- **Preparing documents for AI evidence extraction:** Clean OCR text forms the primary input for Theogony's AI extraction pipeline, allowing the model to identify names, dates, and family connections accurately.

## Good to know

- Optical Character Recognition in Theogony runs **100% locally on your computer** using Tesseract. No images or text are transmitted to the cloud or external servers during OCR.
- If an image is skewed or low contrast, use the preprocessing filters in **OCR Configuration** before running recognition for significantly improved accuracy.
- OCR text is automatically indexed in your tree database, making every word in your transcribed documents discoverable via search.
