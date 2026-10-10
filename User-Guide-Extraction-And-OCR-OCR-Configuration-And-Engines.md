# OCR configuration and engines

![OCR configuration and engines](images/user-guide/ocr-settings.png)

The OCR Configuration and Engines panel configures optical character recognition behavior, installed language packs, image preprocessing filters, and page segmentation modes. Open this screen when you need to transcribe non-English documents, improve recognition on low-contrast historical scans, or handle negative microfilm images.

## What you see

- **Engine and Language Pack Selection:**
  - **Tesseract Engine Status**: Confirms that the embedded local Tesseract OCR engine is active and ready.
  - **Installed Languages**: Dropdown and checklist to select active language models, including English (`eng`), German Fraktur (`frk`), German (`deu`), French (`fra`), Latin (`lat`), and Spanish (`spa`).
- **Image Preprocessing Filters:**
  - **Auto-Deskew**: Automatically straightens scans where the page was tilted on the scanner glass or camera copy stand.
  - **Contrast Enhancement (Binarization)**: Separates faint or faded iron gall ink from yellowed, foxed, or stained paper using adaptive thresholding.
  - **Invert Negative Images**: Inverts black-and-white negative microfilms (white handwriting on dark film) to standard dark text on white backgrounds before recognition.
- **Page Segmentation Mode (PSM):**
  - **Fully Automatic**: Best for mixed pages containing headings, multiple columns, and marginal notes.
  - **Single Column**: Optimized for continuous paragraphs (such as wills, deeds, or narrative letters).
  - **Single Block of Text**: Best for isolated document clippings, headstone inscriptions, or certificates.

## Common tasks

### Configure German Fraktur recognition

1. When working with historical 19th-century German church books, newspapers, or emigration records printed in blackletter Fraktur script:
2. Open the **Installed Languages** selector.
3. Choose **German Fraktur (`frk`)**.
4. Select **Save Preferences**.

Subsequent OCR runs will recognize archaic blackletter ligatures and font styles accurately.

### Enable negative microfilm inversion

1. If you are transcribing a digitized microfilm reel where the background is black and the text is white or translucent:
2. In the Image Preprocessing section, check **Invert Negative Images**.
3. Select **Save Preferences**.

The OCR preprocessor inverts the color values prior to passing the image to Tesseract, allowing standard OCR models to recognize the text without errors.

### Tune preprocessing for faint, stained documents

1. Check **Auto-Deskew** to ensure text lines are strictly horizontal.
2. Check **Contrast Enhancement (Binarization)** to boost light ink against darkened or water-damaged paper.
3. Run OCR on your target document to observe the improved text clarity.

## Practical use cases

- **Transcribing immigrant church registers:** Switch language packs to German or Latin when transcribing colonial Lutheran registers or Catholic baptismal ledgers, ensuring proper character accents and abbreviations are recognized.
- **Microfilm deed indexes:** Set the page segmentation mode to **Multi-column table** to read columnar deed grantee/grantor index pages without running text lines together across separate columns.
- **Handling cell phone courthouse photos:** Auto-deskew corrects slight angles introduced when photographing court records with a smartphone rather than a flatbed scanner.

## Good to know

- All OCR preprocessing and recognition occurs entirely on your local computer's processor. No images, scans, or text snippets are transmitted over the internet.
- Preprocessing filters do not modify your original image file stored in `<tree>.media/`. Filter adjustments are applied non-destructively in memory during the OCR analysis step.
- Multiple languages can be selected simultaneously for bilingual documents (such as Latin and English church records).
