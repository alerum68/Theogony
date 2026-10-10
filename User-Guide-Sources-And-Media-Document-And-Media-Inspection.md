# Document and media inspection

![Document and media inspection](images/user-guide/promoted-media.png)

The Document and Media Inspection viewer (Promoted Media) provides a deep, high-resolution workspace for reading historical documents, inspecting handwriting, verifying OCR transcriptions, and linking documentary evidence to individuals in your tree.

## What you see

- **High-Resolution Image Viewport:** A smooth canvas viewer supporting deep zoom and panning for large document scans (such as double-page census sheets, deed ledgers, and probate files).
- **Navigation and Zoom Toolbar:** Includes controls for zoom in/out, fit to window, 100% actual size, image rotation, and contrast adjustment.
- **Transcription Pane:** Displays the machine-read (OCR) or manually entered text side-by-side with the original scan.
- **Word Bounding Box Highlights:** When OCR text is available, words in the transcription are tied directly to coordinates on the image. Selecting a transcribed word highlights its exact box on the scan.
- **Evidence Extraction Sidebar:** Tools to extract candidate personas, events, and citations directly from the displayed document and send them to the Review Queue.

## Common tasks

### Inspect faint handwriting or small text

1. Open a document scan from the **Media Gallery** or by clicking an attached document thumbnail in a person's record.
2. Use your mouse scroll wheel (or the zoom buttons in the toolbar) to zoom in on challenging handwriting.
3. Click and drag the image canvas to pan smoothly across the page without losing your position.

### Verify transcribed text against the image

1. Look at the **Transcription Pane** alongside the document scan.
2. Click any sentence or word in the transcription text.
3. The viewer immediately highlights the corresponding bounding box on the original image, allowing you to quickly verify whether a difficult letter is an `e`, `o`, `a`, or `u`.

### Link a document to an ancestor

1. In the inspection toolbar, select **Link to Person**.
2. Search for the target individual in the person picker.
3. Choose whether to link the image as a general media item, a portrait thumbnail, or attach it to a specific event (such as a *Death* fact).
4. Select **Confirm Link**.

The document is attached to the individual and appears in their media gallery.

## Practical use cases

- **Transcribing multi-column census ledgers:** Keep the original 1880 census page open on one side of your screen while reading family names, ages, occupations, and birthplaces, confirming line numbers without switching back and forth between separate apps.
- **Deciphering 18th-century wills and deeds:** Zoom into complex archaic handwriting (such as secretary hand or legal cursive), adjusting image contrast to enhance faded iron gall ink against yellowed parchment.
- **Comparing historical signatures:** Open two documents side-by-side (such as a 1795 marriage bond and an 1820 land indenture) to compare signatures and establish whether they represent the same individual or a father and son sharing the same name.

## Good to know

- Promoted Media supports high-resolution formats including TIFF, PNG, JPEG, and multi-page PDF documents.
- Image files are stored in your tree's content-addressed media folder (`<tree>.media/`), keeping file access fast and reliable even with gigabytes of high-resolution scans.
- Zooming, panning, and bounding box inspection occur entirely on your local machine with zero lag and no data sent over the network.
