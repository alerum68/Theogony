---
type: architecture
title: System Overview
description: High-level Tauri, React, and SQLite local-first desktop architecture and crate structure.
tags: [architecture, rust, tauri, react, sqlite, crates, system-overview]
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
verified:
  - by: openwiki/0.5.1
    at: 2026-09-27T18:50:08.444Z
generated: { by: "openwiki/0.5.1", at: "2026-09-27T18:50:08.444Z" }
---

# System Overview

Theogony is a local-first desktop application designed for serious genealogical research, adhering strictly to the Genealogical Proof Standard (GPS). Built around a modular Rust backend workspace and a native-feeling React/TypeScript desktop UI powered by Tauri [repo://theogony-app/Cargo.toml], Theogony cleanly separates pure domain logic, persistence, DNA analysis, AI integration, and GEDCOM interchange into discrete workspace crates [repo://Cargo.toml] while guaranteeing ACID-compliant SQLite storage.

For related concepts and workflows, refer to the [Evidence-First Philosophy](/openwiki/concepts/evidence-first-philosophy.md) and [GEDCOM Portability](/openwiki/integrations/gedcom-portability.md).

## Architecture

<!-- openwiki: mermaid parse failed and this diagram was converted to a text fence so it does not break rendering. Fix the diagram source and restore the mermaid fence. Parser error: Heuristic: an unescaped angle bracket inside a label breaks rendering; rephrase the label. -->
```text
graph TD
    UI[React / TypeScript UI<br/>Tauri Webview] -->|Tauri IPC / Commands| App[Rust Core App<br/>theogony-app]
    App --> Domain[Domain & Evidence Engine<br/>theogony-core / theogony-app]
    App --> DB[SQLite Persistence Layer<br/>theogony-db-sqlite]
    App --> Gedcom[GEDCOM Import/Export<br/>theogony-gedcom]
    DB --> File[(Local SQLite DB)]
```

## Crate Structure
- **`ui/`**: React, TypeScript, and Tailwind CSS frontend built with Vite, communicating via Tauri IPC commands [repo://ui/package.json].
- **`theogony-app/`**: Tauri command handlers, application state orchestration, and evidence management commands [repo://theogony-app/Cargo.toml].
- **`theogony-db-sqlite/`**: SQLite persistence layer managing tables for sources, citations, personas, assertions, individuals, and families [repo://theogony-db-sqlite/Cargo.toml].
- **`theogony-gedcom/`**: Parser and exporter for GEDCOM 5.5.1 and GEDCOM 7 standards [repo://theogony-gedcom/Cargo.toml].
- **`theogony-core/`** / **`theogony-domain/`**: Shared domain models, validation rules, and business logic [repo://theogony-domain/src/lib.rs].
