---
type: operations
title: Edit History and Revert
description: Navigating the audit log and executing safe two-step selective reverts (Refuse, Cascade, Reassign) in SQLite.
tags: [audit-log, edit-history, selective-revert, cascade, reassign, refuse, transactions, data-hygiene]
sources:
  - id: openwiki-source-5b54a58d1b51cd490b0e7162
    resource: repo://package.json
verified:
  - by: openwiki/0.5.1
    at: 2026-09-16T23:59:03.017Z
generated: { by: "openwiki/0.5.1", at: "2026-09-16T23:59:03.017Z" }
---

# Edit History and Revert

Theogony records every data mutation in an immutable audit log (`repo://theogony-db-sqlite/src/edit_log.rs`). Because genealogical research relies on verifiable evidence and rigorous attribution, the audit log allows researchers to inspect past modifications, audit provenance metadata, and perform **Selective Revert** actions to undo specific edits without discarding subsequent unrelated work.

---

## The Audit Log & Edit Architecture

Every write operation performed in the application—whether creating an individual, attaching a source citation, merging personas, or modifying a fact—is recorded as an atomic transaction action composed of structured operations.

Each edit action includes:
- **Action ID**: A monotonically increasing sequential identifier (`#1`, `#2`, ...).
- **Kind & Description**: The nature of the operation (e.g., `create`, `update`, `delete`, `merge_persons`) and a human-readable summary.
- **Timestamp & Provenance**: Creation time, provenance metadata (`source: manual` or AI-assisted attribution), and the originating branch.
- **Reversion Tracker**: A `reverted_by` reference pointing to the action ID that successfully reverted this entry, if applicable.

> [!WARNING]
> **Audit Trail Integrity**: The audit log forms the backbone of Theogony's verifiable research model and the Genealogical Proof Standard (GPS). Manually altering or bypassing the SQLite audit tables corrupts rollback guarantees, breaks branch merging invariants, and destroys provenance transparency. Never edit audit tables directly outside of official application migrations and reversion routines.

---

## Selective Revert & Conflict Resolution

When attempting to revert an historical action (e.g., action `#15`), subsequent edits may have modified or depended upon the data affected by `#15`. Rather than failing outright or blindly overwriting newer work, Theogony's selective revert engine (`repo://theogony-db-sqlite/src/revert.rs`) performs pre-flight conflict analysis (`all_conflicts`).

If conflicts are detected, the system requires the researcher to resolve each conflict using one of three explicit strategies: **Refuse**, **Cascade**, or **Reassign**.

<!-- openwiki: mermaid parse failed and this diagram was converted to a text fence so it does not break rendering. Fix the diagram source and restore the mermaid fence. Parser error: Heuristic: an unescaped angle bracket inside a label breaks rendering; rephrase the label. -->
```text
graph TD
    UserReq["User Requests Revert (Action N)"] --> FindOps["Gather Operations & Before/After Snapshots"]
    FindOps --> CheckConflicts["Run Pre-flight Conflict Analysis"]
    CheckConflicts --> HasConflicts{"Conflicts Detected?"}
    
    HasConflicts -->|No Conflicts| ApplyRevert["Apply Reverse Operations & Log Revert Action"]
    HasConflicts -->|Yes Conflicts| PromptDecisions["Prompt Researcher for Conflict Decisions"]
    
    PromptDecisions --> DecisionRefuse["**Refuse**<br>Abort revert for this branch or conflict"]
    PromptDecisions --> DecisionCascade["**Cascade**<br>Automatically revert blocking actions newest first"]
    PromptDecisions --> DecisionReassign["**Reassign**<br>Point dependent foreign key to alternative target"]
    
    DecisionRefuse --> Abort["Halt Revert"]
    DecisionCascade --> ExecuteCascade["Recursively Revert Blocking Actions in Reverse Chronological Order"]
    DecisionReassign --> ExecuteReassign["Update Dependent Foreign Key in Database Transaction"]
    
    ExecuteCascade --> ApplyRevert
    ExecuteReassign --> ApplyRevert
    
    ApplyRevert --> Success["Revert Complete & Recorded"]
```

---

## Two-Step Revert Actions

When executing a selective revert in the **Edit History** interface, researchers choose how the system handles dependent downstream changes:

1. **Refuse**:
   - **Behavior**: Halts the revert operation and preserves the conflicting downstream changes.
   - **Use Case**: When a newer edit represents verified, independent research that should remain intact despite rolling back an earlier related action.

2. **Cascade**:
   - **Behavior**: Recursively reverts blocking downstream actions in reverse chronological order (newest first) (`repo://theogony-db-sqlite/src/revert.rs#L43-L58`) before executing the primary revert.
   - **Use Case**: When a sequence of dependent edits builds upon an erroneous premise and all subsequent modifications must be cleanly unwound together.

3. **Reassign**:
   - **Behavior**: Remaps dependent foreign keys or field references to point to an alternative valid target record (`repo://theogony-db-sqlite/src/revert.rs#L69-L85`), allowing the primary revert to proceed without destroying unrelated downstream modifications.
   - **Use Case**: When reverting a person merge or identity split where subsequent citations or facts should be reassigned to the surviving individual rather than deleted.

---

## Operational Best Practices

- **Inspect Before Reverting**: Always open the **Edit History** panel to review the exact before-and-after JSON snapshots of an action before initiating a selective revert.
- **Understand Dependencies**: When the system flags downstream conflicts during a revert, evaluate whether a **Cascade** (undoing the chain) or **Reassign** (salvaging downstream work) best preserves your research integrity.
- **Database Backups**: Always create a database backup or export a portability package before performing complex multi-action reverts or branch merges.
