---
type: architecture
title: System Overview
description: High-level Tauri, React, and SQLite local-first desktop architecture, workspace crates, UI components, and report generation engines.
tags: [architecture, rust, tauri, react, sqlite, crates, system-overview, ui, reports]
sources:
  - id: openwiki-source-651d1fb6c9e49916a916ab51
    resource: repo://Cargo.toml
  - id: openwiki-source-a2371d6362e5db4bc834ad03
    resource: repo://CLAUDE.md
  - id: openwiki-source-df6d663c8300cf4ffe858da1
    resource: repo://theogony-ai/Cargo.toml
  - id: openwiki-source-0a92e91524b9981ef0c9df55
    resource: repo://theogony-app/Cargo.toml
  - id: openwiki-source-fb23fbb325b2a8122c3150c2
    resource: repo://theogony-app/src/lib.rs
  - id: openwiki-source-d7e9a325bf86e1ff1b0f94f1
    resource: repo://theogony-db-sqlite/Cargo.toml
  - id: openwiki-source-48654a26c1044d28c027e22e
    resource: repo://theogony-db-sqlite/src/schema.rs
  - id: openwiki-source-e757c628609b7e75af918e83
    resource: repo://theogony-dna/Cargo.toml
  - id: openwiki-source-61c917696a7dbf739bd28821
    resource: repo://theogony-domain/src/lib.rs
  - id: openwiki-source-aff8daa72644424d0311ddb5
    resource: repo://theogony-gedcom/Cargo.toml
  - id: openwiki-source-98f2c5993b8d1ac8166b80c6
    resource: repo://theogony-haplogroup/Cargo.toml
  - id: openwiki-source-d384a0a251d693ebb516385a
    resource: repo://theogony-ports/Cargo.toml
  - id: openwiki-source-436f4179fe22abf615d2f7d0
    resource: repo://ui/package.json
  - id: openwiki-source-77cf798aadbbfd08671e2630
    resource: repo://ui/src/components/PedigreeCanvas.tsx
  - id: openwiki-source-6ff378a34d0301bebf1cfaa0
    resource: repo://ui/src/reports/CitationReports.tsx
verified:
  - by: openwiki/0.5.1
    at: 2026-09-28T00:00:28.276Z
generated: { by: "openwiki/0.5.1", at: "2026-09-28T00:00:28.276Z" }
---

# System Overview

Theogony is a local-first desktop application designed for serious genealogical research, adhering strictly to the Genealogical Proof Standard (GPS). Built around a modular Rust backend workspace and a native-feeling React/TypeScript desktop UI powered by Tauri [repo://theogony-app/Cargo.toml], Theogony cleanly separates pure domain logic, persistence, DNA analysis, AI integration, and GEDCOM interchange into discrete workspace crates [repo://Cargo.toml] while guaranteeing ACID-compliant SQLite storage.

For related concepts and workflows, refer to the [Evidence-First Philosophy](/openwiki/concepts/evidence-first-philosophy.md) and [GEDCOM Portability](/openwiki/integrations/gedcom-portability.md).

## Architecture

<!-- openwiki: mermaid parse failed and this diagram was converted to a text fence so it does not break rendering. Fix the diagram source and restore the mermaid fence. Parser error: Heuristic: an unescaped angle bracket inside a label breaks rendering; rephrase the label. -->
```text
graph TD
    UI[React TypeScript UI<br/>Tauri Webview] -->|Tauri IPC Commands| App[Rust Core App<br/>theogony-app]
    App --> Domain[Domain and Evidence Engine<br/>theogony-domain]
    App --> DB[SQLite Persistence Layer<br/>theogony-db-sqlite]
    App --> Gedcom[GEDCOM Interchange<br/>theogony-gedcom]
    App --> DNA[DNA Analysis and Kits<br/>theogony-dna]
    DB --> File[(Local SQLite Database)]
```
System architecture showing Tauri UI interacting via IPC commands with the Rust core application, which orchestrates domain logic, SQLite storage, GEDCOM interchange, and DNA analysis crates.

## Crate Structure and Subsystems
- **`ui/`**: React, TypeScript, and Tailwind CSS frontend built with Vite, featuring rich interactive components (such as pedigree canvas, family views, data grids, context menus, and event dialogs) and report generation engines (Ahnentafel, family group sheets, citation reports, and place reports) communicating via Tauri IPC commands [repo://ui/package.json, repo://ui/src/components/PedigreeCanvas.tsx, repo://ui/src/reports/CitationReports.tsx].
- **`theogony-app/`**: Tauri command handlers, application state orchestration, diagnostics, backup management, and evidence management commands [repo://theogony-app/Cargo.toml].
- **`theogony-db-sqlite/`**: Robust SQLite persistence layer managing tables and repositories for sources, citations, personas, assertions, individuals, families, places, DNA kits, segments, and edit logging [repo://theogony-db-sqlite/Cargo.toml, repo://theogony-db-sqlite/src/schema.rs].
- **`theogony-gedcom/`**: Parser and exporter supporting GEDCOM 5.5.1 and GEDCOM 7 interchange standards [repo://theogony-gedcom/Cargo.toml].
- **`theogony-domain/`** / **`theogony-core/`**: Shared domain models, validation rules, and business logic adhering to the Genealogical Proof Standard [repo://theogony-domain/src/lib.rs].
- **`theogony-dna/`**, **`theogony-haplogroup/`**, **`theogony-ai/`**, **`theogony-ports/`**: Specialized crates providing DNA segment bucketing, clustering, WATO analysis, Y-STR markers, haplogroup classification, AI assistant integrations, and core port traits.
