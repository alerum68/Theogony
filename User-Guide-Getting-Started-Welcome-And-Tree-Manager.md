# Welcome and tree manager

![Welcome and tree manager](images/user-guide/welcome.png)

The Welcome screen is the front door of Theogony. You see this screen whenever you launch the application without an active tree, or after choosing **Close tree** from the file menu. It is where you start fresh research databases, open existing family files, manage recent projects, and configure application-wide appearance.

## What you see

The left pane holds the core file commands:
- **Create a new tree...**: Opens a standard file dialog to name and initialize a clean `.theo` SQLite database.
- **Open a tree...**: Opens your system file picker to select an existing `.theo` tree from your hard drive or an external archive.
- **Tree file path input**: Allows you to paste or type a direct path to a database file.
- **Appearance...**: Opens the appearance settings dialog to switch skins between Archival (light), Instrument (dark), or Match Windows.

The right pane displays your **Recent trees** list:
- Each card shows the database name, the absolute file path on your disk, and the date it was last modified.
- Accessible files provide a direct click to open, along with a **Settings...** button for tree configuration.
- Missing or moved files are greyed out with an explanatory notice and a **Remove from list** button to clear the dead entry.

## Common tasks

### Create a new tree database

1. Select **Create a new tree...** in the left column.
2. In your operating system file dialog, navigate to the folder where you keep your genealogy files (for example, `Documents/Genealogy/`).
3. Enter a descriptive filename (such as `Hale_Family.theo`) and select **Save**.

Theogony creates the database file alongside its companion media folder (`Hale_Family.theo.media/`), initializes the database schema, and opens the main research workbench.

### Open an existing tree

1. Select **Open a tree...**.
2. Locate your `.theo` file in the file picker.
3. Select **Open**.

The tree loads immediately, restoring your previous workbench tab layout and selection.

### Open a recent project

1. Find the target database card in the **Recent trees** list.
2. Click the tree card to open it immediately.

### Remove a missing tree from the recent list

1. If you have renamed, moved, or deleted a `.theo` file outside of Theogony, its card in **Recent trees** appears disabled with a "File not found" status.
2. Select **Remove from list** on the card.

The entry is removed from the recent history without touching any files on disk.

## Practical use cases

- **Separating distinct client or family lines:** Keep separate `.theo` databases for unrelated branches (e.g., your maternal line versus a research project for a friend). Switching between them from the Welcome screen takes two clicks.
- **Archiving point-in-time snapshots:** Before undertaking a major reorganization or testing complex parentage hypotheses, make a copy of your `.theo` file on disk. Both files appear independently in the recent list with their distinct file paths.
- **Working across portable drives:** If you store your genealogy on an encrypted USB drive, open the file directly via **Open a tree...**. Theogony keeps all media references relative to the `.theo` file, so drive letter changes between different computers never break photo or document links.

## Good to know

- Every Theogony tree is a single, self-contained SQLite database with the `.theo` file extension.
- Linked documents and photos are stored in a folder right next to the tree file, named `<filename>.media/`. Always copy or back up the database file and the `.media` folder together.
- Database writes use Write-Ahead Logging (`WAL`) and full disk synchronization. Every edit is saved immediately, protecting your data against unexpected computer crashes.
