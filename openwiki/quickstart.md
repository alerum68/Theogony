---
type: documentation quickstart
title: Theogony Documentation Quickstart
description: Main task-routing hub and introduction for users, researchers, and developers exploring Theogony genealogy documentation.
tags: [quickstart, documentation, task-routing, genealogy, tauri, sqlite]
verified:
  - by: openwiki/0.5.1
    at: 2026-09-14T02:18:08.068Z
sources:
  - id: openwiki-source-a2371d6362e5db4bc834ad03
    resource: repo://CLAUDE.md
  - id: openwiki-source-23775c3de52f3ab95a13cb8b
    resource: repo://README.md
generated: { by: "openwiki/0.5.1", at: "2026-09-14T02:18:08.068Z" }
---

# Theogony Documentation Quickstart

Welcome to **Theogony**, a local-first desktop genealogy application built with Tauri, React, and SQLite, adhering strictly to the Genealogical Proof Standard (GPS). 

This quickstart serves as the central task-routing hub for users, family history researchers, and developers exploring the documentation and features of Theogony.

---

## What is Theogony?

Theogony is engineered for rigorous genealogical research. Unlike traditional tree-building software that conflates raw historical records with final conclusions, Theogony implements an **Evidence-First Philosophy**. It preserves the distinction between:
1. **Source Documents**: Original or derivative historical records.
2. **Extracted Personas**: Abstracted individuals mentioned in specific documents.
3. **Assertions**: Individual claims (birth, marriage, residence) tied to citations and surety ratings.
4. **Concluded Individuals and Families**: Synthesized genealogical entities formed by correlating multiple assertions.

All data is stored locally in an encrypted or standard SQLite database, guaranteeing complete data sovereignty and privacy.

---

## Documentation Task-Routing Map

Use the table below to navigate directly to the concepts, workflows, data portability guides, operations, and architecture pages within the OpenWiki documentation.

| Category | Page Title & Description | Target Audience | Direct Link |
| :--- | :--- | :--- | :--- |
| **Architecture** | **System Architecture Overview**: High-level technical overview of Theogony's local-first architecture, Tauri backend, SQLite storage, and crate organization. | Developers & Power Users | [System Architecture Overview](/openwiki/architecture/system-overview.md) |
| **Concepts** | **Evidence-First Philosophy & GPS Standards**: Explains how Theogony implements the Genealogical Proof Standard through structured evidence correlation. | Researchers & Users | [Evidence-First Philosophy](/openwiki/concepts/evidence-first-philosophy.md) |
| **Workflows** | **Navigating the Interface**: Guides users through the main user interface components and layout of Theogony. | New Users | [Navigating the Interface](/openwiki/workflows/navigating-the-interface.md) |
| **Workflows** | **Adding and Citing Facts**: Step-by-step instructions for recording genealogical assertions with surety ratings and citations. | Researchers & Users | [Adding and Citing Facts](/openwiki/workflows/adding-and-citing-facts.md) |
<!-- openwiki: broken internal link [/openwiki/workflows/family-structures.md] file "/openwiki/workflows/family-structures.md" does not exist. Fix the href or restore the target, then delete this comment. -->
| **Workflows** | **Working with Family Structures**: Guide on establishing and managing parent-child relationships, spouses, and custom family attributes. | Researchers & Users | [Working with Family Structures](/openwiki/workflows/family-structures.md) |
<!-- openwiki: broken internal link [/openwiki/operations/review-queue.md] file "/openwiki/operations/review-queue.md" does not exist. Fix the href or restore the target, then delete this comment. -->
| **Operations** | **Review Queue & Persona Resolution**: Guide on clearing unattached extracted personas and reconciling multi-source individual claims. | Researchers & Users | [Review Queue & Persona Resolution](/openwiki/operations/review-queue.md) |
| **Operations** | **Edit History & Selective Revert**: Explains how to navigate the audit log and safely execute selective reverts without data loss. | Researchers & Users | [Edit History & Selective Revert](/openwiki/operations/edit-history-and-revert.md) |
| **Integrations** | **GEDCOM Portability & Interchange**: Reference for importing and exporting standard GEDCOM files and preserving vendor extensions. | All Users | [GEDCOM Portability](/openwiki/integrations/gedcom-portability.md) |
| **Integrations** | **Database Backups & Lossless Packages**: Guide for creating secure database backups (`.theb`) and lossless portability packages (`.tgpkg`). | All Users | [Database Backups & Packages](/openwiki/integrations/backups-and-packages.md) |

---

## Quick Navigation Flow

```mermaid
graph TD
    QS[Theogony Quickstart Hub] --> C[Concepts & GPS]
    QS --> W[User Workflows]
    QS --> O[Operations & Audit]
    QS --> I[Data Portability]
    QS --> A[System Architecture]

    C --> |Evidence-First| EFP[Evidence-First Philosophy]
    W --> |Interface & Facts| NAV[Navigating Interface]
    W --> |Assertions| FAC[Adding & Citing Facts]
    W --> |Relating| FAM[Family Structures]
    O --> |Queue & Review| RQ[Review Queue]
    O --> |Audit Log| EH[Edit History & Revert]
    I --> |Interchange| GED[GEDCOM Portability]
    I --> |Backups| PKG[Backups & Packages]
    A --> |Tauri & SQLite| SOA[System Architecture Overview]
```

---

## Getting Started

> [!NOTE]
> **Local-First Privacy**: Theogony stores all genealogical records directly on your local machine in SQLite databases. No cloud accounts or mandatory subscriptions are required.

1. **Launch Theogony**: Open the desktop application to view the Welcome Screen and recent trees.
2. **Create or Import a Tree**: Start a new family tree or import an existing `.ged` GEDCOM file or `.tgpkg` portability package.
3. **Review Extracted Personas**: Check the **Review Queue** to process newly imported records or unattached extracted personas.
4. **Cite Your Sources**: Attach original documents and assign surety ratings (High, Medium, Low, Untested) to every genealogical claim you record.
