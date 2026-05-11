# Sprinkler Plan · 5589 rue Goddard

Interactive irrigation schematic for the property at 5589 rue Goddard. Built from a hand-drawn map of all sprinkler head locations, zones, and known issues.

**Live tool:** https://joshhamilton469.github.io/sprinkler-plan/

## What's here

- **`index.html`** — the self-contained interactive map. Click to place heads, edit zones, drag to move, add notes, export PNG/JSON snapshots.
- **`data/`** — JSON snapshots of the plan over time. Each snapshot captures every head position, zone assignment, note, and on-map annotation. Latest is `data/latest.json`.
- **`docs/irrigation-reference.xlsx`** — companion maintenance workbook. Four tabs: System Summary (totals, water source, controller, contacts, seasonal schedule), Zone Reference (per-zone breakdown with editable head counts, types, GPM, run times), Head Inventory (one row per head, with status and service date), and Maintenance Log (pre-seeded with seasonal reminders).
- **`.github/workflows/pages.yml`** — auto-deploys the tool to GitHub Pages on every push to `main`.

## Using the tool

Open the live URL (or `index.html` locally). Modes:

- **Place** (default) — click empty space to add a head in the active zone (sidebar)
- **Select** — click a head to edit zone/note or delete; drag to move
- **Pan** — drag to move around when zoomed in

Keyboard: `P / S / H` to switch modes, `1-9` to pick active zone, `F` to fit view, `Ctrl+Z` to undo, `Delete` to remove selected head.

The tool auto-saves to your browser's local storage. **For real backups, click "Export JSON data" and commit the file** to `data/` (see below).

## Saving a snapshot back to the repo

When you've made meaningful edits worth keeping:

1. Click **⬇ Export JSON data** in the sidebar — you'll get `sprinkler-plan-YYYY-MM-DD.json`
2. Save it to the `data/` folder, also overwriting `data/latest.json`
3. Commit and push:

   ```bash
   cd ~/Code/sprinkler-plan
   cp ~/Downloads/sprinkler-plan-YYYY-MM-DD.json data/
   cp data/sprinkler-plan-YYYY-MM-DD.json data/latest.json
   git add data/
   git commit -m "Update plan: <what changed>"
   git push
   ```

To **load** a saved snapshot, click **⬆ Import JSON data** in the tool and pick the file. (Confirm the replace prompt.)

## System summary

- 11 active zones (Z1 through Z11) plus an unused Zone 12
- ~45 heads total, including 1 head buried under the deck with unknown zone
- 1 known broken head on the east property line (Zone 8)
- Other annotations: 1 head buried under rock

Full per-zone breakdown is in the companion spreadsheet (`irrigation-reference.xlsx`, kept separately).

## Maintenance notes

- **Spring start-up** — late April / early May (after last frost). Walk all zones, check coverage.
- **Mid-season check** — mid-July. Adjust heads, check pressure.
- **Pre-winter inspection** — late September. Confirm all heads functional.
- **Winterize** — before first hard freeze (~late October Ottawa). Compressor blow-out, controller off.

## License

Personal use only. Not for redistribution.
