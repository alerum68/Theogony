---
type: workflow
title: Navigating the Interface
description: Guides users through the main user interface components and layout of Theogony, including the Tree Navigator, Details Panel, and Person Picker.
tags: [ui, workflow, navigation, workbench, components]
verified:
  - by: openwiki/0.5.1
    at: 2026-09-14T02:18:08.068Z
sources:
  - id: openwiki-source-3d2a85713446b48c5b2eb521
    resource: repo://ui/src/components/PersonPicker.tsx
  - id: openwiki-source-581ccfdbc4f29f5dcf09c2df
    resource: repo://ui/src/screens/People.tsx
  - id: openwiki-source-20250499b40f61144244af93
    resource: repo://ui/src/screens/Person.tsx
  - id: openwiki-source-f87f9cc8e5ca8b9e6e4b28b2
    resource: repo://ui/src/shell/DockWorkbench.tsx
generated: { by: "openwiki/0.5.1", at: "2026-09-14T02:18:08.068Z" }
---

# Navigating the Interface

Theogony provides a VS Code-inspired desktop workspace built with React, Fluent UI React components, and `dockview-react`. The application interface is structured around dedicated activity views, a resizable sidebar, dockable workbench panels, and interactive pickers.

## Interface Layout and Architecture

The user interface layout consists of a top **Title Bar**, a left **Activity Bar**, a **Side Bar**, and a central dockable workbench (`dockview-react`). Individual records, pedigree trees, family views, and management tools can be opened as side-by-side or tabbed panels within the workbench.

```mermaid
graph TD
    TB[Title Bar / Header & Nav controls] --> AB[Activity Bar / Research & Utility Views]
    AB --> SB[Side Bar / Filters & Context]
    AB --> DW[Dock Workbench / Dockview Panels]
    DW --> TN[Tree Navigator / Index & Pedigree Canvas]
    DW --> DP[Details Panel / Person & Record Details]
    DW --> PP[Person Picker / Search Combobox]
```

## Key UI Components

### Tree Navigator
The **Tree Navigator** encompasses index tables (such as the **Individuals Index** in `People.tsx`) and visual graph canvases (such as the **Pedigree Canvas** and **Family View**). It allows researchers to browse, sort, search, and navigate through individuals across the genealogical tree.
- **Individuals Index (`People.tsx`)**: Displays paginated rows of people with customizable columns, sorting, debounced prefix search (`useDebouncedValue`), and multi-row selection for operations like merging records.
- **Pedigree & Family Canvases**: Interactive visual layouts (`PedigreeCanvas.tsx`, `FamilyView.tsx`) enabling direct node selection, parent/child navigation, and expanding ancestral lines.

### Details Panel
The **Details Panel** (represented by the **Individual Record** panel and screen components like `Person.tsx`) serves as the comprehensive property inspector and editor for selected entities.
- **Record Inspection & Editing**: Displays and updates individual attributes such as given name, surname, prefix, suffix, sex, and privacy flags (`updateIndividualName`, `updateIndividual`).
- **Embedded Sub-panels**: Houses modular event timelines (`EventsPanel.tsx`) and relationship matrices (`RelationshipsPanel.tsx`) to manage life events, citations, parents, spouses, and children.

### Person Picker
The **Person Picker** (`PersonPicker.tsx`) is a reusable search combobox component used throughout dialogs (such as **Attach Persona Dialog** and **Merge Dialog**) and workflow screens.
- **Debounced Search**: Automatically queries individuals matching the entered text prefix using `listPeople`.
- **Exclusion Support**: Supports excluding specific entity IDs (e.g., the primary record being edited or merged) to prevent circular references or self-selection.

## Operations & Workflow Integration

1. **Switching Views**: Use the **Activity Bar** on the left to switch between core research views (People, Pedigree, Family, Places, Sources, Review Queue) and utility views.
2. **Opening Records**: Clicking a person in an index or tree opens an **Individual Record** panel side-by-side in the **Dock Workbench**.
3. **Editing & Linking**: Use the **Details Panel** to modify biographical details and manage family relationships, or utilize the **Person Picker** when attaching personas or merging duplicate records.
