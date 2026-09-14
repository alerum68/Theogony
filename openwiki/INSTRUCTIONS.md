# OpenWiki Documentation Brief: Theogony

## Target Audience
- Primary: Genealogists, family history researchers, and general users seeking step-by-step guidance on using Theogony and applying the Genealogical Proof Standard (GPS).
- Secondary: Power users and developers seeking an overview of data portability, GEDCOM interchange, and system architecture.

## 1. What the Wiki Must Capture

1. Evidence-First Philosophy & GPS Standards:
   - How Theogony separates Source Documents -> Extracted Personas -> Assertions -> Concluded Individuals and Families.
   - Non-destructive conflict handling: marking assertions as `active`, `disputed`, or `rejected` rather than overwriting conflicting data.

2. Core User Workflows:
   - Navigating the interface (Tree Navigator, Details Panel, Person Picker).
   - Adding and citing facts, recording surety ratings, and attaching sources.
   - Working with family structures (spouses, parent-child links, custom facts).

3. Data Hygiene & Auditability:
   - Review Queue: Resolving unattached personas and handling individuals cited by multiple sources.
   - Edit History & Selective Revert: Navigating the audit log and understanding two-step revert actions (Refuse, Cascade, Reassign).

4. Data Portability & Interchange:
   - Importing and exporting standard GEDCOM 5.5.1 and GEDCOM 7 (`.ged`).
   - Complete database backups (`.theb`) and lossless data packages (`.tgpkg`).
   - How vendor-specific extension tags are preserved during import.

5. System Overview (High-Level):
   - Local-first desktop application architecture (Tauri, React, SQLite).
   - High-level crate structure (Domain, Persistence, GEDCOM, UI).

## 2. What Must Be Excluded (Internal Only)

- Developer and Agent Tooling: Automation scripts, API key rotation logic, CLI wrappers, and internal harness files (`.agents/`).
- Low-Level Code Plumbing: Internal Rust trait wrappers, FFI serialization details, and raw memory structures.
- Raw Database Scripts: SQL table migration internals, SQLite PRAGMA tuning, and transaction lock mechanics.
- Unit Test Implementations: Internal test fixtures, mock setups, and CI workflow pipelines.

## 3. Formatting and Style Instructions for the Model

1. Mermaid Diagrams:
   - Include a Mermaid diagram (`graph TD` or `sequenceDiagram`) on every major concept and workflow page.
   - Use diagrams to visualize the Evidence Hierarchy, Import/Export data flows, and Revert State transitions.

2. Task-Oriented Procedures:
   - Format user actions using bold text for UI controls (for example: "On the Activity Bar, click **Review Queue**").

3. Markdown Alerts:
   - Use GitHub-flavored alert blocks (`> [!NOTE]`, `> [!IMPORTANT]`, `> [!WARNING]`) for key notices, GPS best practices, and export caveats.

4. Cross-Linking:
   - Maintain direct markdown links between theoretical concepts and practical workflow guides.

5. Tone and Style:
   - Clear, direct, professional technical documentation.
   - No decorative emojis or conversational filler.
