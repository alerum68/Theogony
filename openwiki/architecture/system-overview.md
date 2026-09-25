---
type: architecture
title: System Overview
description: Architectural overview of Theogony's local-first Tauri, React, and SQLite stack.
tags: [architecture, rust, tauri, react, sqlite, crates, system-overview]
sources:
  - id: openwiki-source-651d1fb6c9e49916a916ab51
    resource: repo://Cargo.toml
  - id: openwiki-source-a2371d6362e5db4bc834ad03
    resource: repo://CLAUDE.md
  - id: openwiki-source-0a92e91524b9981ef0c9df55
    resource: repo://theogony-app/Cargo.toml
  - id: openwiki-source-fb23fbb325b2a8122c3150c2
    resource: repo://theogony-app/src/lib.rs
  - id: openwiki-source-d7e9a325bf86e1ff1b0f94f1
    resource: repo://theogony-db-sqlite/Cargo.toml
  - id: openwiki-source-61c917696a7dbf739bd28821
    resource: repo://theogony-domain/src/lib.rs
  - id: openwiki-source-436f4179fe22abf615d2f7d0
    resource: repo://ui/package.json
verified:
  - by: openwiki/0.5.1
    at: 2026-09-25T15:04:19.343Z
generated: { by: "openwiki/0.5.1", at: "2026-09-25T15:04:19.343Z" }
---

# System Overview

Theogony is a high-performance, local-first genealogy desktop application engineered for rigorous evidence analysis, multi-user interchange, and historical family tree research. Built around a modular Rust backend workspace and a native-feeling React/TypeScript desktop UI powered by Tauri [repo://theogony-app/Cargo.toml], Theogony cleanly separates pure domain logic, persistence, DNA analysis, AI integration, and GEDCOM interchange into discrete workspace crates [repo://Cargo.toml] while guaranteeing ACID-compliant SQLite storage.

## Architectural Boundaries & Data Flow

Theogony follows a strict layered architecture where dependencies flow inward. Pure domain types and ports reside at the center, completely isolated from database drivers, UI frameworks, and interchange protocols.

```mermaid
graph TD
    subgraph UI ["Desktop UI (React + TypeScript)"]
        React[React Components / Views]
        AppShell[AppShell & Screens]
    end

    subgraph Tauri ["Tauri Shell (theogony-app)"]
        Commands[Tauri Commands / IPC Handlers]
        State[AppState & Transport Layers]
    end

    subgraph Backend ["Rust Workspace Backend"]
        Ports["theogony-ports\n(Traits & Storage Interfaces)"]
        Domain["theogony-domain\n(Pure Domain Records, IDs, Provenance)"]
        DB["theogony-db-sqlite\n(SQLite Persistence Spine)"]
        Gedcom["theogony-gedcom\n(GEDCOM 7 & .tgpkg Interchange)"]
        AI["theogony-ai\n(AI Analysis & Synthesis)"]
        DNA["theogony-dna\n(DNA Segments, Bucketing & WATO)"]
        Haplogroup["theogony-haplogroup\n(Haplogroup Calculations)"]
    end

    React -->|Tauri IPC Invoke| Commands
    Commands --> Tauri
    Tauri --> Ports
    Ports --> DB
    Ports --> Gedcom
    Ports --> AI
    Ports --> DNA
    Ports --> Haplogroup
    DB -. implements .- Ports
    Gedcom -. implements .- Ports
    AI -. implements .- Ports
    DNA -. implements .- Ports
    Haplogroup -. implements .- Ports
    DB --> Domain
    Gedcom --> Domain
    AI --> Domain
    DNA --> Domain
    Haplogroup --> Domain
    Tauri --> UI
```

---

## Workspace Crate Structure

The Rust workspace (`Cargo.toml`) is organized into eight specialized crates enforcing strict modular boundaries [repo://Cargo.toml]:

1. **`theogony-domain`**
   - **Purpose:** Pure domain models, record structs (`Individual`, `Family`, `Fact`, `Citation`, `SourceDocument`, `Place`, `Repository`), strongly typed identifiers, and error enums [repo://theogony-domain/src/lib.rs].
   - **Invariants:** Zero external data-shape or database dependencies; safe to compile anywhere core genealogical entities are needed.

2. **`theogony-ports`**
   - **Purpose:** Trait definitions and repository interfaces defining the contract between application execution logic and storage implementations.

3. **`theogony-db-sqlite`**
   - **Purpose:** ACID-compliant SQLite storage spine (`theogony-db-sqlite`) [repo://theogony-db-sqlite/Cargo.toml]. Implements migration management, versioned schema, high-performance queries, hypothesis branching, and transaction logs.

4. **`theogony-gedcom`**
   - **Purpose:** GEDCOM 7 parser, serialization engine, THEB interchange package format (`.tgpkg`), vendor dialect mapping, and conformance validation.

5. **`theogony-ai`**
   - **Purpose:** Local and cloud-assisted AI analysis helpers, AI override tracking, and Terms of Service (ToS) state management.

6. **`theogony-dna`**
   - **Purpose:** DNA segment mapping, chromosome browser calculations, genetic match bucketing, and WATO (What Are The Odds) hypothesis scoring.

7. **`theogony-haplogroup`**
   - **Purpose:** Haplogroup calculations and phylogenetic branch analysis.

8. **`theogony-app`**
   - **Purpose:** Tauri desktop application entrypoint, plain Rust command handlers over `AppState`, IPC routing, export/import orchestration, and TypeScript binding generation via `ts-rs` [repo://theogony-app/Cargo.toml, repo://theogony-app/src/lib.rs].

---

## Local-First Storage, Tauri Commands, and SQLite Backing

Theogony is engineered specifically as a desktop-native application with robust local-first guarantees:

- **Local-First Storage:** Every family tree is stored in a self-contained SQLite database file equipped with WAL mode, foreign key enforcement, and explicit migration paths, ensuring instant local startup, zero server dependency, and robust backup/restore capabilities via `.tgpkg` archives.
- **Tauri Commands & IPC:** Operations exposed to the React frontend are defined as plain Rust functions over `AppState` inside `theogony-app/src/commands/` [repo://theogony-app/src/lib.rs]. Thin transport adapters marshal arguments and serialize results without embedding business logic.
- **SQLite Backing:** The persistence layer (`theogony-db-sqlite`) wraps connections with reader pools and exclusive writer locks, implementing robust transaction management, hypothesis branching, and change history logs.
