---
type: concept
title: Evidence-First Philosophy & GPS Standards
description: Core philosophical framework and genealogical proof standard implementation in Theogony, separating source documents, extracted personas, assertions, and concluded individuals and families.
tags: [evidence-first, genealogy, gps, personas, assertions, conflict-handling, architecture]
verified:
  - by: openwiki/0.5.1
    at: 2026-09-25T15:04:19.343Z
sources:
  - id: openwiki-source-17ccbeaa6afd5efa0cb28ccd
    resource: repo://theogony-db-sqlite/src/assertions.rs
  - id: openwiki-source-aee410ac1172dae3922a857f
    resource: repo://theogony-db-sqlite/src/personas.rs
  - id: openwiki-source-f27b89db9906f12cec9ef142
    resource: repo://theogony-db-sqlite/src/sources.rs
  - id: openwiki-source-a85aedb0d5dda666b82d51d2
    resource: repo://theogony-domain/src/records.rs
generated: { by: "openwiki/0.5.1", at: "2026-09-25T15:04:19.343Z" }
---

# Evidence-First Philosophy & GPS Standards

Theogony is built upon an **evidence-first genealogical model** inspired by Elizabeth Shown Mills's *Evidence Explained* methodology and the **Genealogical Proof Standard (GPS)** formulated by the Board for Certification of Genealogists (BCG). Rather than treating a family tree as a collection of mutable entity records where users overwrite birth dates or parent links directly, Theogony strictly separates raw source documents, extracted actors (*personas*), asserted claims, and concluded historical individuals and families.

---

## The Evidence-First Data Model Hierarchy

The data architecture moves deliberately from uninterpreted historical artifacts to conclusive genealogical conclusions across four primary layers:

1. **Source Documents & Citations (`SourceDocument`, `Citation`)**
   - Represents physical or digital archival records, books, census pages, vital records, repositories, or DNA test kits.
   - Each source document contains specific citations (page references, transcriptions, and footnote texts) linked to assertions, facts, or personas via citation links (`CitationLink`).

2. **Extracted Personas (`Persona`, `PersonaName`, `PersonaParent`, `PersonaSpouse`)**
   - Represents an unlinked individual as they appear within a specific source document.
   - A single historical person (e.g., John Smith) might appear across multiple census returns, land deeds, and marriage certificates, generating multiple distinct `Persona` records in the database.
   - Personas capture names, reported sexes, parent links (`PersonaParent`), and spouse links (`PersonaSpouse`) as stated *in that specific source document*.

3. **Assertions (`Assertion`)**
   - Represents specific claims made by a persona or source regarding facts (birth, death, residence, occupation) or names.
   - Assertions carry explicit **surety** ratings (e.g., primary, secondary, questionable) and operational status attributes.

4. **Concluded Individuals and Families (`Individual`, `Family`, `FamilyChild`)**
   - Represents the genealogist's synthesized conclusions—the canonical historical individuals (`Individual`) and family units (`Family`) established by exhaustively analyzing and correlating underlying assertions across multiple sources.

```mermaid
graph TD
    subgraph Sources ["1. Source & Citation Layer"]
        SD[SourceDocument] -->|has citations| Cit[Citation]
        Cit -->|linked via CitationLink| CL[Owners: Persona, Fact, Assertion]
    end

    subgraph Personas ["2. Extracted Persona Layer"]
        SD -->|generates| P[Persona]
        P -->|has names, parent links, spouse links| PN[PersonaName / PersonaParent / PersonaSpouse]
    end

    subgraph Assertions ["3. Assertion & Conflict Layer"]
        P -->|asserts facts & names| Ass[Assertion]
        Ass -->|carries surety & status| Status[Status: active, disputed, rejected, proposed]
    end

    subgraph Conclusions ["4. Conclusion Layer"]
    subgraph Conclusions ["4. Conclusion Layer"]
        Ass -->|synthesized into| Ind[Concluded Individual]
        Ass -->|synthesized into| Fam[Concluded Family]
    end
```

---

## Non-Destructive Conflict Handling

Genealogical research frequently encounters contradictory evidence—such as conflicting birth years across successive censuses, competing parentage claims, or contradictory assertions. Traditional software often forces users to overwrite data or delete alternatives. Theogony implements **non-destructive conflict handling**:

- **Status Vocabulary:** Assertions, persona-parent links (`PersonaParent`), and persona-spouse links (`PersonaSpouse`) support operational statuses including `active`, `disputed`, and `rejected`:
  - `active`: Currently accepted evidence supporting a working conclusion or active hypothesis branch.
  - `disputed`: A conflicting claim that challenges an existing conclusion or active assertion, retained for transparent analysis rather than deleted.
  - `rejected`: A claim evaluated and formally rejected under GPS scrutiny.
- **Audit Trails & Conflict States:** When conflicting evidence arises, records are not overwritten. Instead, competing assertions or relationship links are marked as `disputed` or `rejected`, allowing researchers to review alternative interpretations side-by-side. All modifications are recorded in immutable edit logs (`Action`, `Op`) and branch revision structures.

```mermaid
stateDiagram-v2
    [*] --> active : Initial Import / Creation
    active --> disputed : Challenged by Conflicting Source
    disputed --> active : Reaffirmed after Analysis
    disputed --> rejected : Proven Incorrect under GPS
    active --> rejected : Invalidated by New Evidence
    rejected --> active : Reconsidered / Restored
```

---

## The Genealogical Proof Standard (GPS)

To establish reliable genealogical conclusions, Theogony's architecture supports the five pillars of the **Genealogical Proof Standard**:

1. **A reasonably exhaustive search** for all available sources that could contain information about each identity or event.
2. **Complete and accurate citations** of every source used (`SourceDocument`, `Citation`).
3. **Thorough analysis and correlation** of the collected evidence (supported by `Assertion` statuses, surety levels, and persona linking).
4. **Resolution of conflicting evidence** (supported by non-destructive `active`, `disputed`, and `rejected` states rather than silent overwrites).
5. **A soundly reasoned, written conclusion** explaining how the evidence proves the identity, relationship, or event.
