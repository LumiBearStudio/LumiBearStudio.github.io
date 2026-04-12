---
title: Batch rename files
layout: default
parent: How-To Recipes
nav_order: 6
---

# Batch rename files

Rename dozens of files at once using regex, prefix/suffix, or sequential numbering — with a live preview before you commit.

**Time:** ~3 minutes  
**Skill level:** Intermediate

---

## Opening the Batch Rename dialog

1. Select the files you want to rename (<kbd>Ctrl</kbd> + <kbd>A</kbd> for all, or <kbd>Ctrl</kbd> + click for individual picks)
2. Press <kbd>F2</kbd>

When multiple files are selected, <kbd>F2</kbd> opens the **Batch Rename** dialog instead of inline rename.

---

## Mode 1: Find and Replace

Replace a specific text string in every filename.

**Example:** Rename `IMG_001.jpg`, `IMG_002.jpg`, `IMG_003.jpg` → `Photo_001.jpg`, `Photo_002.jpg`, `Photo_003.jpg`

| Field | Value |
|-------|-------|
| Find | `IMG_` |
| Replace | `Photo_` |

Options:
- **Case sensitive** — `IMG` and `img` are treated differently when on
- **Regex** — enables regular expression patterns in the Find field

**Regex example:** Remove trailing numbers from filenames  
Find: `\s+\d+$`  
Replace: *(leave blank)*

This turns `Report 2024`, `Report 2025` → `Report`, `Report`.

---

## Mode 2: Prefix / Suffix

Add text to the beginning or end of every filename.

**Example:** Add `2024_` to the start of all files in a project folder:

| Field | Value |
|-------|-------|
| Prefix | `2024_` |
| Suffix | *(blank)* |

`budget.xlsx` → `2024_budget.xlsx`  
`notes.txt` → `2024_notes.txt`

**Add a suffix before the extension:**

| Field | Value |
|-------|-------|
| Prefix | *(blank)* |
| Suffix | `_final` |

`report.docx` → `report_final.docx`

---

## Mode 3: Sequential Numbering

Rename files to a numbered pattern. Use `{name}`, `{n}`, and `{ext}` as placeholders.

**Example:** Rename a photo dump to `Photo_001.jpg`, `Photo_002.jpg`, etc.

| Field | Value |
|-------|-------|
| Pattern | `Photo_{n}` |
| Start | `1` |
| Increment | `1` |
| Padding | `3` (zero-pads to 3 digits: 001, 002…) |

The `{name}` placeholder inserts the original filename (without extension):

Pattern `{name}_{n}` → `sunset_001.jpg`, `sunset_002.jpg`

---

## Live preview

The dialog always shows a table of **Old name → New name** for every selected file before you apply. Review it carefully, especially when using regex.

If two files would end up with the same name, they are highlighted in red — fix the pattern before applying.

---

## Undo

Press <kbd>Ctrl</kbd> + <kbd>Z</kbd> immediately after to reverse the entire batch rename in a single undo. Individual file renames within the batch are reversed together.

---

## Real-world examples

### Clean up downloaded files

**Before:** `file (1).pdf`, `file (2).pdf`, `file (3).pdf`  
**Goal:** Remove the ` (n)` duplicate suffix

Mode: **Find and Replace**, Regex on  
Find: `\s+\(\d+\)`  
Replace: *(blank)*

---

### Add a date prefix to photos

**Before:** `DSC_0001.jpg`, `DSC_0002.jpg`  
**Goal:** `2024-06-15_DSC_0001.jpg`

Mode: **Prefix / Suffix**  
Prefix: `2024-06-15_`

---

### Number a set of slides

**Before:** `intro.pptx`, `overview.pptx`, `demo.pptx`  
**Goal:** `01_intro.pptx`, `02_overview.pptx`, `03_demo.pptx`

Mode: **Sequential Numbering**  
Pattern: `{n}_{name}`  
Start: `1`, Padding: `2`

---

## Tips

- **Sort first** — The numbering order follows the current sort order in the file list. Sort by name, date, or size before opening Batch Rename to control which file gets which number.
- **Filter then rename** — Use the filter bar (<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F</kbd>) to isolate the files you want, then select all (<kbd>Ctrl</kbd> + <kbd>A</kbd>) and press <kbd>F2</kbd>.
- **Extension toggle** — If you need to rename extensions too, enable **full name** mode by pressing <kbd>F2</kbd> twice on single-file inline rename. For batch, the extension is always included in patterns.

---

## See also

- [File Operations](../../features/file-operations/#batch-rename) — Full batch rename reference
- [Search](../../features/search/) — Find the right files before renaming
- [Keyboard Shortcuts](../../shortcuts/) — Complete shortcut list
