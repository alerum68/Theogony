# Skins and visual themes

A skin governs the complete visual appearance of Theogony: its background surfaces, text contrasts, accent colors, typography, row heights, and list density. Theogony provides two carefully designed built-in skins, supports automatic synchronization with your operating system's dark/light mode, and allows importing, creating, and sharing custom skin archives (`.theoskin`).

## Built-in Skins

### 1. Archival (Light)
- **Character:** Evokes an archival records office, rare manuscript collection, or finely bound family history volume.
- **Surfaces:** Warm linen neutrals (`#efece5` app background, `#f6f3ec` raised headers, `#fbf9f4` grid body).
- **Typography:** `Newsreader` (variable serif) for person names, record headings, section titles, and quoted transcriptions; `Segoe UI Variable` for controls and data.
- **Accents:** Deep bottle green (`#2c5a4f`).

### 2. Instrument (Dark)
- **Character:** Designed like a professional research instrument (such as Adobe Lightroom or DaVinci Resolve) for high-density, low-glare nighttime work.
- **Surfaces:** Deep graphite neutrals (`#17191d` app background, `#1b1e23` raised panels, `#131518` activity rail).
- **Typography:** `Segoe UI Variable` for controls; `IBM Plex Mono` for dates, IDs, numbers, and transcribed evidence.
- **Accents:** Signal blue (`#4f8fd6`).

---

## Choosing a Skin and Matching the OS

To choose your skin:
1. Open **Settings $\rightarrow$ Appearance** (or from the Welcome screen, select **Appearance...**).
2. Choose your preferred mode:
   - **Archival**: Forces the light archival skin at all times.
   - **Instrument**: Forces the dark instrument skin at all times.
   - **Match Windows**: Automatically follows your operating system. When Windows switches between light and dark mode, Theogony instantly switches between your chosen light skin and dark skin.
3. Your selection applies instantly across the entire application without needing to restart.

---

## Importing and Sharing Skins (`.theoskin`)

A skin can be exported as a compact `.theoskin` file to share with colleagues or use across multiple computers.

### Import a skin
1. In Settings $\rightarrow$ Appearance, select **Import skin...**.
2. Select a `.theoskin` file from your disk.
3. If a skin with the same identifier is already installed, Theogony prompts you whether to replace it.
4. **Contrast Verification:** Theogony automatically audits every text-to-surface color pair against **WCAG AA accessibility standards** (contrast ratio $\ge$ 4.5:1). If any pairs fail, the skin is still imported, and a report lists the failing pairs with their exact contrast ratios.

### Export a custom skin
1. Select your custom skin in the appearance list.
2. Select **Export...**.
3. Choose a destination folder to save the self-contained `.theoskin` archive.
*(Note: Built-in skins cannot be exported directly; duplicate them first to create an editable copy).*

---

## Creating a Custom Skin

You can author your own skins using standard JSON format:

1. Select **Duplicate...** on either Archival or Instrument. This writes a complete, editable `skin.json` into your local skins directory.
2. Select **Open skins folder**.
3. Open `skin.json` in your favorite text editor (such as VS Code or Notepad).
4. Edit the colors, metrics, or fonts.
5. In Theogony, select **Reload**. If a skin contains a syntax error, the error is displayed cleanly in the list rather than crashing.

### Smallest Useful Skin Example
```json
{
  "format": 1,
  "id": "burgundy",
  "name": "Burgundy Archival",
  "mode": "light",
  "base": "archival",
  "colors": {
    "accent": "#6e2a2f"
  }
}
```

### Key Token Reference
- **Surfaces:** `surface-app` (window background), `surface-raised` (dialogs, toolbars), `surface-sunken` (insets), `surface-grid` (table bodies), `surface-header` (grid and panel headers), `surface-hover`.
- **Text:** `text`, `text-muted`, `text-on-accent`, `accent-text` (links).
- **Accent:** `accent`, `accent-hover`, `focus-ring`, `selection-bg`, `selection-text`.
- **Status:** `warning`, `error`, `success`, `info`.
- **Evidence Quality Chips:** `quality-source-bg/-text`, `quality-information-bg/-text`, `quality-evidence-bg/-text`.
- **DNA Tracks:** `dna-paternal` (blue), `dna-maternal` (red/pink), `dna-both`.
- **Charts:** `generation-1...8`, `chart-series-1...8`, `sex-male`, `sex-female`, `sex-other`.
- **Metrics (px):** `row-height` (20–36 px), `radius` (0–8 px), `font-size-sm` (10–13 px), `font-size-md` (12–15 px).
- **Font Roles:** `ui` (controls and buttons), `record` (person names and headings), `data` (grids, dates, numbers), `quote` (transcriptions).

---

## Limits and Safety

A skin in Theogony is strictly **data, not executable code**:
- Theogony refuses archives that contain anything other than `skin.json`, `README.txt`, and listed font files.
- File paths that leave the skin's directory are rejected.
- Colors are accepted only as hexadecimal values (`#rgb`, `#rrggbb`, `#rrggbbaa`).
- The skin engine **never makes network requests** or downloads remote fonts; all fonts must be installed on your computer or bundled locally as `.woff2` files within the archive.
