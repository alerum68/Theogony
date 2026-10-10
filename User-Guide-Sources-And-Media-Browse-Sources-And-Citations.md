# Browse sources and citations

![Browse sources and citations](images/user-guide/sources.png)

The Browse Sources and Citations screen manages your master catalog of documentary evidence, repository institutions, and individual citations. Open this screen when you want to review your documentary evidence, audit source quality under the Genealogical Proof Standard, or verify that citations are consistently applied across your tree.

## What you see

- **Search Bar:** Located at the top of the panel to quickly filter sources by title, author, or repository name.
- **Master Sources Grid:** A high-performance virtualized table displaying:
  - **Source Title:** The formal title of the book, register, microfilm reel, or record collection.
  - **Author / Originator:** The creator, government agency, or church authority that produced the record.
  - **Repository:** The archive, library, or website where the original material is preserved.
  - **Source Class:** Categorized as *Original*, *Derivative*, or *Authored* per standard genealogical proof conventions.
  - **AI Terms of Service Status:** Indicates whether the repository permits external cloud processing (`Allowed` vs `Restricted`).
  - **Citation Count:** The number of specific citations linked to this source across your tree.
- **Citation Inspector:** When a source is selected, the lower pane lists every specific citation (page numbers, certificate references, and transcribed text) and the events or individuals linked to them.

## Common tasks

### Add a master source

1. Select **Add Source** in the toolbar.
2. In the dialog, enter the source title (for example, *Gallia County, Ohio, Deed Books, 1803–1860*).
3. Select or enter the author/originator (e.g., *Gallia County Recorder*).
4. Link the repository (such as *Gallia County Courthouse* or *FamilySearch*).
5. Set the **Source Class** (*Original* or *Derivative*).
6. Select **Save**.

The source appears in the master catalog and is immediately available for citation across all personal events.

### Review all citations attached to a source

1. Select a source in the master grid (such as a county probate record book).
2. The **Citation Inspector** below displays every individual cited from that source, along with page numbers, file dates, and transcription notes.
3. Click any citation row to jump directly to the cited individual's record.

### Check repository AI Terms of Service restrictions

1. Locate a source hosted by a commercial genealogy provider (such as Ancestry or MyHeritage).
2. Observe the **AI ToS** badge:
   - Repositories marked **Restricted** protect your data: Theogony's extraction engine blocks these images from being sent to external cloud AI APIs, ensuring compliance with third-party service terms and preserving research privacy.
   - Local on-device tools (such as Tesseract OCR) remain fully enabled for all sources.

## Practical use cases

- **Evidence quality audits before publishing:** Review all sources across your tree to identify derivative indexes that should be upgraded to original register images, adhering to the Genealogical Proof Standard.
- **Tracking repository visits:** Group sources by repository to review everything you examined during an on-site archive visit, ensuring every cited volume has complete archive reference call numbers.
- **Citation reuse across family groups:** Easily cite a single document—such as an estate partition deed naming twelve heirs—across all twelve siblings without re-typing the publication and archive metadata each time.

## Good to know

- Citations in Theogony support verbatim transcription text and detailed research notes alongside standard page references.
- Deleting an individual from your tree never deletes their citations or master sources. Evidence is permanent; only conclusion links are severed.
- Exporting your tree to GEDCOM 5.5.1 or 7.0 includes complete source and citation records, preserving page numbers and transcriptions for interchange with other software.
