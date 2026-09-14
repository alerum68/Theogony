---
type: concept
title: Evidence-First Philosophy & GPS Standards
description: Explains how Theogony implements the Genealogical Proof Standard through structured evidence correlation, separating source documents, extracted personas, assertions, and concluded individuals and families.
tags: [evidence-first, gps, genealogical-proof-standard, methodology, data-architecture]
verified:
  - by: openwiki/0.5.1
    at: 2026-09-14T02:18:08.068Z
sources:
  - id: openwiki-source-a85aedb0d5dda666b82d51d2
    resource: repo://theogony-domain/src/records.rs
generated: { by: "openwiki/0.5.1", at: "2026-09-14T02:18:08.068Z" }
---

# Evidence-First Philosophy & GPS Standards

Theogony is built from the ground up on an **evidence-first philosophy**, adhering strictly to the **Genealogical Proof Standard (GPS)**. In traditional genealogy software, users often jump straight to creating conclusions (individuals, marriages, and parent-child relationships) and attach sources as an afterthought. This approach frequently obscures contradictions, destroys conflicting source evidence when data is overwritten, and makes it difficult to prove how a conclusion was reached.

Theogony decouples raw historical documentation from genealogical conclusions. Every piece of historical information passes through a disciplined four-stage pipeline: **Source Documents** $\rightarrow$ **Extracted Personas** $\rightarrow$ **Assertions** $\rightarrow$ **Concluded Individuals and Families**.

---

## The Four-Stage Evidence Hierarchy

To satisfy the rigorous demands of the Genealogical Proof Standard—specifically the requirement for thorough research, exhaustive source citation, and the resolution of conflicting evidence—Theogony structures data into four distinct layers:

<!-- openwiki: mermaid parse failed and this diagram was converted to a text fence so it does not break rendering. Fix the diagram source and restore the mermaid fence. Parser error: Heuristic: an unescaped angle bracket inside a label breaks rendering; rephrase the label. -->
```text
graph TD
    SD[Source Documents<br/><i>Original or derivative records, repositories, and citations</i>] --> EP[Extracted Personas<br/><i>Raw entities extracted from a single source document</i>]
    EP --> AS[Assertions<br/><i>Specific factual claims with active, disputed, or rejected status</i>]
    AS --> IF[Concluded Individuals & Families<br/><i>Synthesized genealogical entities and relationships</i>]
    
    style SD fill:#f9f,stroke:#333,stroke-width:2px
    style EP fill:#bbf,stroke:#333,stroke-width:2px
    style AS fill:#bfb,stroke:#333,stroke-width:2px
    style IF fill:#ff9,stroke:#333,stroke-width:2px
```

### 1. Source Documents
The foundation of the evidence hierarchy is the **Source Document**. A source document represents an original or derivative historical record (such as a census return, parish register, deed, tombstone, or probate record) along with its repository and citation details. Source documents are immutable records of historical artifacts.

### 2. Extracted Personas
When a source document is analyzed, researchers extract **Extracted Personas**. A persona represents a mention of an individual within a specific source document. For example, the 1850 US Federal Census listing for a household generates multiple personas—one for the head of household, one for the spouse, and several for children—each tied directly to that single census document (`repo://theogony-domain/src/records.rs#L315-L325`).

### 3. Assertions
Assertions are specific factual claims extracted from a persona that bear upon an individual or family (such as name, birth date, residence, parentage, or marriage). Unlike concluded entities, assertions retain their source context and surety ratings.

> [!IMPORTANT]
> **GPS Best Practice: Never Overwrite Conflicting Data**
> Historical records frequently contradict one another (e.g., varying birth years across censuses or conflicting parentage names in baptismal registers). Theogony prohibits silent overwriting. Instead, every assertion and relationship link (such as parentage or spouse links) is assigned a status: `active`, `disputed`, or `rejected` (`repo://theogony-domain/src/records.rs#L352-L356`). This preserves all historical evidence for future analysis and review.

### 4. Concluded Individuals and Families
At the apex of the hierarchy are **Concluded Individuals** and **Families**. These are the synthesized genealogical entities resulting from the correlation and analysis of multiple assertions across diverse source documents. When research supports a definitive conclusion, active assertions are linked to the concluded individual or family, while rejected or superseded assertions remain archived in the database for auditability and future re-evaluation.

---

## Non-Destructive Conflict Handling & Statuses

When multiple source documents provide conflicting claims about an individual (such as conflicting ages, birthplaces, or parent-child connections), traditional software often forces the user to pick one value and overwrite or delete the other. Theogony implements non-destructive conflict handling using explicit status markers on assertions and relationship links:

- **`active`**: The assertion or relationship link currently contributes to the active genealogical conclusion for the individual or family.
- **`disputed`**: The claim conflicts with other evidence or remains under active genealogical review, requiring further correlation before a definitive conclusion can be reached.
- **`rejected`**: The claim has been evaluated and determined to be incorrect, erroneous, or pertaining to a different individual, but it is retained in the database to prevent repeating past research errors and to maintain complete audit transparency.

---

## Related Guides

<!-- openwiki: broken internal link [/openwiki/operations/review-queue.md] file "/openwiki/operations/review-queue.md" does not exist. Fix the href or restore the target, then delete this comment. -->
- Review unattached personas and resolve conflicts in the [Review Queue](/openwiki/operations/review-queue.md).
- Learn how to record surety ratings and attach sources in [Adding and Citing Facts](/openwiki/workflows/adding-and-citing-facts.md).
- Get started quickly with [Quickstart](/openwiki/quickstart.md).
