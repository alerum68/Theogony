# Theogony User Guide

Theogony is desktop genealogy research software built around the **Genealogical Proof Standard (GPS)**. It is local-first, stores your data directly on your computer in an archival SQLite file, and strictly separates the raw evidence found in historical documents from the conclusions you draw about your ancestors.

This guide walks through every screen, tool, and feature currently in the application, explaining how each control works and how to apply them to real-world genealogical problems.

---

## Table of Contents

### Getting Started
- [Welcome and tree manager](User-Guide-Getting-Started-Welcome-And-Tree-Manager): Creating new `.theo` tree databases, opening existing files, and managing recent projects.

### People and Families
- [Browse people](User-Guide-People-And-Families-Browse-People): Master directory of individuals, search, multi-selection, copying data to spreadsheets, and safe deletion.
- [Edit a person](User-Guide-People-And-Families-Edit-A-Person): Biographical timelines, parentage and marital relationships, life events, notes, and evidence citations.
- [Browse facts by type](User-Guide-People-And-Families-Browse-Facts-By-Type): Cross-tree analysis auditing specific fact categories (Birth, Census, Military, Death) across all individuals.
- [Pedigree collapse and endogamy](User-Guide-People-And-Families-Pedigree-Collapse-And-Endogamy): Identifying duplicate ancestors, calculating coefficients of relationship, and evaluating endogamy impacts on shared DNA.

### Places and Maps
- [Browse places](User-Guide-Places-And-Maps-Browse-Places): Master geographic catalog, standardizing place hierarchies, and merging duplicate location entries.
- [Place resolver and atlas](User-Guide-Places-And-Maps-Place-Resolver-And-Atlas): Interactive Leaflet map, geocoding coordinates, historical jurisdiction lookups, and migration trails.
- [Ancient DNA migration map](User-Guide-Places-And-Maps-Ancient-DNA-Migration-Map): Prehistoric Y-DNA and mtDNA migration routes and ancient archaeological DNA burial sites.

### Sources and Media
- [Browse sources and citations](User-Guide-Sources-And-Media-Browse-Sources-And-Citations): Master documentary catalog, repository tracking, evidence evaluation (Original/Derivative, Primary/Secondary, Direct/Indirect), and repository AI ToS safeguards.
- [Document and media inspection](User-Guide-Sources-And-Media-Document-And-Media-Inspection): High-resolution document viewer (Promoted Media), deep zoom, transcription editor, and word bounding box overlays.
- [Media staging and gallery](User-Guide-Sources-And-Media-Media-Staging-And-Gallery): Intake gallery, drag-and-drop ingestion, and content-addressed SHA-256 deduplicated media storage.

### Extraction and OCR
- [OCR text extraction](User-Guide-Extraction-And-OCR-OCR-Text-Extraction): Running local Tesseract OCR on historical scans and extracting text layers from digital PDFs.
- [OCR configuration and engines](User-Guide-Extraction-And-OCR-OCR-Configuration-And-Engines): Selecting language packs (English, German Fraktur, French, Latin), auto-deskew, contrast enhancement, and negative microfilm inversion.
- [AI evidence extraction](User-Guide-Extraction-And-OCR-AI-Evidence-Extraction): Generative AI extraction of candidate personas, dates, places, and relationships using customizable templates.
- [Extraction proposals list](User-Guide-Extraction-And-OCR-Extraction-Proposals-List): Tabular overview of all extracted candidate claims, status filtering, and bulk triage.
- [Extraction model settings](User-Guide-Extraction-And-OCR-Extraction-Model-Settings): Configuring Gemini models, temperature strictness, and secure keychain API credentials.
- [Extraction estimate dialog](User-Guide-Extraction-And-OCR-Extraction-Estimate-Dialog): Pre-execution token usage and cost estimator in USD, ensuring full transparency before any cloud request.

### Review
- [Review queue](User-Guide-Review-Review-Queue): Central holding area for incoming evidence, unattached personas, and unreviewed claims.
- [Proposal review cards](User-Guide-Review-Proposal-Review-Cards): Step-by-step interactive card deck for matching candidate personas and accepting facts into your tree conclusions.

### DNA Suite
- [DNA review and kit manager](User-Guide-DNA-DNA-Review-And-Kit-Manager): Managing imported autosomal kits (AncestryDNA, FTDNA, GEDmatch), match exploration, and linking kits to tree individuals.
- [DNA cluster matrix (Leeds method)](User-Guide-DNA-DNA-Cluster-Matrix-Leeds-Method): Automated Leeds Method clustering of in-common-with matches into four grandparent branches.
- [DNA chromosome browser](User-Guide-DNA-DNA-Chromosome-Browser): Painting shared genetic segments on chromosomes 1–22 and X, segment triangulation, and MRCA ancestor linking.
- [Relationship probability calculator](User-Guide-DNA-Relationship-Probability-Calculator): Empirical Banyan and Shared cM Project statistical probabilities, and Y-STR TMRCA calculations.
- [What Are The Odds (WATO)](User-Guide-DNA-What-Are-The-Odds-WATO): Evaluating competing tree placement hypotheses for an unknown person against multiple known DNA matches.
- [Haplogroup lineage lookup](User-Guide-DNA-Haplogroup-Lineage-Lookup): Tracing direct paternal Y-DNA and maternal mtDNA phylogenetic trees from root ancestors to terminal subclades.

### Reports and Charts
- [Genealogy charts overview](User-Guide-Reports-And-Charts-Genealogy-Charts-Overview): Overview of all 11 vector chart layouts, viewport navigation, options, living person redaction, and vector PDF export.
- [Pedigree chart](User-Guide-Reports-And-Charts-Pedigree-Chart): Classic horizontal ancestral tree layout (parents, grandparents, great-grandparents).
- [Fan chart](User-Guide-Reports-And-Charts-Fan-Chart): Concentric radial ring segments spanning 180°, 270°, or 360° up to 12 generations.
- [Descendant chart](User-Guide-Reports-And-Charts-Descendant-Chart): Vertical top-down or horizontal left-right descendant trees with paired couples and centered children.
- [Trellis chart](User-Guide-Reports-And-Charts-Trellis-Chart): Comprehensive generational network displaying collateral relatives (aunts, uncles, cousins, in-laws) for up to 5,000 individuals.
- [Family group sheets and reports](User-Guide-Reports-And-Charts-Family-Group-Sheets-And-Reports): Standard nuclear family group sheets, place reports, citation audits, and media inventories.
- [Tree statistics](User-Guide-Reports-And-Charts-Tree-Statistics): In-browser WebAssembly statistical analytics (webR) for demographic distributions and generational pedigree completeness.

### Settings and Appearance
- [Date format settings](User-Guide-Settings-Date-Format-Settings): Configuring ambiguous numeric date interpretation (DMY vs MDY), display formats, and calendar rules.
- [Skins and visual themes](User-Guide-Settings-Skins-And-Themes): Archival (light), Instrument (dark), Match Windows, importing `.theoskin` archives, and WCAG AA contrast verification.
