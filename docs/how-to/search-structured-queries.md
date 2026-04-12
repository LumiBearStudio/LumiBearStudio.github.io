---
title: Search with structured queries
layout: default
parent: How-To Recipes
nav_order: 4
---

# Search with structured queries

Go beyond simple filename search — filter by file type, size, date, and extension using a concise query syntax.

**Time:** ~5 minutes  
**Skill level:** Intermediate

---

## Three ways to search

SPAN Finder has three search layers, each suited to different needs:

| Method | Shortcut | Best for |
|--------|----------|---------|
| **Type-ahead** | Just start typing | Jumping to an item in the current folder |
| **Filter bar** | <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F</kbd> | Narrowing down a large folder by name pattern |
| **Recursive search** | <kbd>Ctrl</kbd> + <kbd>F</kbd> | Finding files anywhere inside a folder tree |

---

## Basic recursive search

Press <kbd>Ctrl</kbd> + <kbd>F</kbd> and type a filename or keyword. SPAN Finder searches the current folder and all subfolders, streaming results as it finds them.

Press <kbd>Ctrl</kbd> + <kbd>Enter</kbd> (instead of <kbd>Enter</kbd>) to search from the **drive root** — useful when you're not sure which subfolder contains the file.

---

## Structured query syntax

Add one or more **filter tokens** to any search to narrow results by type, size, date, or extension. Tokens can be combined freely.

### `kind:` — filter by file type

```
kind:image
kind:video
kind:audio
kind:document
kind:code
kind:archive
kind:font
kind:executable
```

**Example:** Find all images in the current folder tree:
```
kind:image
```

Find all Python source files:
```
kind:code report
```
(finds code files whose name contains "report")

**Supported aliases:**

| Kind | Aliases |
|------|---------|
| `image` | `photo`, `picture`, `pic`, `img` |
| `document` | `doc`, `docs`, `text` |
| `video` | `movie`, `film` |
| `audio` | `music`, `sound`, `song` |
| `archive` | `compressed`, `zip` |
| `code` | `source`, `script`, `program` |
| `executable` | `exe`, `app`, `application` |

---

### `size:` — filter by file size

```
size:>10MB
size:<500KB
size:>1GB
size:empty
size:large
size:small
```

**Supported units:** B, KB, MB, GB, TB  
**Supported operators:** `>`, `<`, `>=`, `<=`, `=`  
**Presets:** `empty` (0 bytes), `small` (<1 MB), `large` (>100 MB)

**Example:** Find videos larger than 1 GB:
```
kind:video size:>1GB
```

---

### `date:` — filter by modification date

```
date:today
date:yesterday
date:thisweek
date:thismonth
date:thisyear
date:>2024-01-01
date:<2023-12-31
```

**Example:** Files modified this week:
```
date:thisweek
```

Find old log files from last year:
```
kind:document log date:<2025-01-01
```

---

### `ext:` — filter by extension

```
ext:.pdf
ext:.csv
ext:.jpg
```

You can omit the leading dot: `ext:pdf` works the same as `ext:.pdf`.

**Example:** Find all spreadsheets:
```
ext:.xlsx
```

---

## Combining filters

All tokens are combined with AND — every token must match for a file to appear in results.

**Real-world examples:**

| Query | What it finds |
|-------|--------------|
| `kind:image size:>5MB` | Large photos (good for finding duplicates) |
| `kind:video date:thismonth` | Videos added this month |
| `report kind:document date:thisyear` | Documents with "report" in the name, modified this year |
| `ext:.log size:>10MB` | Large log files worth cleaning up |
| `kind:code size:<10KB date:thisweek` | Recently edited small source files |
| `kind:archive size:>500MB` | Large archives worth extracting or deleting |

---

## Korean Hangul search

Type a **chosung** (초성) character to search by the initial consonant of Korean filenames. For example, type `ㄷ` to find `다운로드`, `데이터`, `동영상`, etc.

This works in type-ahead, the filter bar, and recursive search.

---

## Tips

- **Results are streamed** — results appear as SPAN scans, so you can act on early results before the full scan finishes.
- **Cancel anytime** — press <kbd>Esc</kbd> to stop the search. Results found so far are preserved.
- **Act on results** — once you have search results, you can select all (<kbd>Ctrl</kbd> + <kbd>A</kbd>), batch rename (<kbd>F2</kbd>), or drag them to the Shelf for bulk operations.
- **Filter bar vs. recursive** — the filter bar (<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F</kbd>) only filters the current folder's visible items (instant, no I/O). Recursive search (<kbd>Ctrl</kbd> + <kbd>F</kbd>) walks subdirectories (slower but finds everything).

---

## See also

- [Search](../../features/search/) — Full search reference
- [File Shelf](../../features/shelf/) — Act on search results in bulk
- [File Operations](../../features/file-operations/) — Batch rename search results
