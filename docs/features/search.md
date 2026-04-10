---
title: Search
layout: default
parent: Features
nav_order: 7
---

# Search
{: .no_toc }

Instant type-ahead filtering, recursive background search, wildcards, and a structured query language with `kind:`, `size:`, `date:`, and `ext:` filters.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

Span Finder ships three layers of search, from lightest to heaviest:

1. **Type-ahead** — Start typing to filter the current Miller column instantly
2. **Filter bar** — A persistent wildcard filter applied across every open column
3. **Recursive search** — Full BFS traversal of the current root, powered by a background producer/consumer pipeline, with a structured query language

Pick the layer that matches the job. Looking for a file whose name starts with "report" inside the current folder? Just start typing. Looking for every PDF larger than 10 MB modified this week across an entire drive? That is what recursive search is for.

## Type-ahead

Anywhere in Miller Columns, Details, List, or Icons view, just start typing:

- Each keystroke extends the current search buffer (800 ms timeout between keys)
- The first matching item in the active column is selected
- Letters, digits, and punctuation all count
- Continue typing to narrow the match

No shortcut required — simply type. This is the fastest way to find a single file whose name you partially remember.

## Filter bar

Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F</kbd> to toggle the live filter bar. Anything you type is applied as a wildcard filter to **every open Miller column** at once.

Examples:

- `*.exe` — Show only executables
- `*.mp3` — Show only MP3 files
- `report*` — Show only items starting with "report"
- `test?.doc` — Match `test1.doc`, `testA.doc`, etc.

Wildcard rules:

- `*` — Zero or more characters
- `?` — Exactly one character
- Plain text (no wildcards) — Case-insensitive substring match

## Recursive search

Press <kbd>Ctrl</kbd> + <kbd>F</kbd> to focus the search box. Type a query, press <kbd>Enter</kbd>, and Span Finder performs a breadth-first search of the **current navigation root** — not just the current folder.

- If you're in Miller Columns at `D:\Projects\src\Services`, the root is `D:\` (the first column). Recursive search walks the entire drive.
- Press <kbd>Esc</kbd> to cancel and restore the state you had before the search.
- Double-click a folder in the results to navigate to it. Double-click a file to open it.

### How it works

- **BFS traversal** — Matches macOS Finder's expected behavior
- **Producer / consumer pipeline** — File enumeration runs in a background thread; the UI thread pulls results in batches via a bounded channel (size 16)
- **50-item batches** — Results stream in as they arrive so you can start clicking before the search finishes
- **Backpressure** — The bounded channel prevents memory blowups on huge trees
- **Max 10,000 results** — Safety cap to protect memory
- **`EnumerationOptions.IgnoreInaccessible = true`** — Access-denied folders are skipped without aborting the whole search
- **Hidden file filtering** — Controlled by your Settings toggle and applied at the enumerator level
- **Progress reporting** — Every 20 folders, the status bar shows "Searching... N found (M folders scanned)"

### Cancel and restore

<kbd>Esc</kbd> cancels the in-flight search and restores the exact Miller column state you had before you started. Span Finder snapshots columns and path before launching the search and swaps them back atomically on cancel.

### Results view

Recursive search results are shown in a virtual folder labeled "Search results: {folder}". In Details view, Span Finder automatically shows a **Location** column with paths relative to the search root, so you can tell which directory each hit came from.

## Structured query syntax

The recursive search box understands a query language with typed filters. You can combine them freely — multiple filters are ANDed together.

### Exact phrase

Wrap terms in single or double quotes:

```
"quarterly report"
'hello world'
```

### `kind:` — File type filter

Filter by semantic file kind. 30+ aliases are supported:

| Kind | Aliases |
|---|---|
| `kind:image` | photo, photos, picture, pictures, pic, img, images |
| `kind:video` | videos, movie, movies, film |
| `kind:audio` | music, sound, sounds, song, songs |
| `kind:document` | documents, doc, docs, text |
| `kind:archive` | archives, zip, compressed |
| `kind:code` | source, script, scripts, program |
| `kind:exe` | executable, executables, app, application |
| `kind:font` | fonts |

Folders are automatically excluded from `kind:` matches.

### `size:` — File size filter

```
size:>1MB        # larger than 1 MB
size:<100KB      # smaller than 100 KB
size:>=500B      # 500 bytes or more
size:<=2GB       # 2 GB or smaller
size:=10MB       # exactly 10 MB
size:1GB         # shorthand for size:>=1GB
size:>1.5MB      # decimals allowed
```

Units: `B`, `KB`, `MB`, `GB`, `TB` (case-insensitive).

Presets: `empty` (= 0 B), `tiny` (< 16 KB), `small` (< 1 MB), `medium` (≥ 1 MB), `large` (> 128 MB), `huge` / `gigantic` (> 1 GB).

Folders are automatically excluded from `size:` matches.

### `date:` — Modification date filter

```
date:>2024-01-01
date:<2024-12-31
date:>=2024-06-01
date:<=2024-06-30
date:=2024-07-15    # date part only, time ignored
```

Operators default to `>=` when omitted.

Presets: `today`, `yesterday`, `thisweek` (Monday start), `lastweek`, `thismonth`, `lastmonth`, `thisyear`, `lastyear`.

### `ext:` — Extension filter

```
ext:.pdf
ext:txt          # dot is optional
ext:jpg;png;gif  # multiple extensions, any match wins
```

Folders are automatically excluded.

### Combining filters

All filters combine with implicit AND:

```
kind:image size:>1MB
*.pdf date:thisweek
kind:video size:>500MB date:lastmonth
report kind:document ext:docx
```

If a filter value is empty (e.g. just `kind:`), it falls back to being treated as plain text. Invalid values like `date:notadate` also fall back to text tokens, so you never get a hard error.

## Korean Hangul chosung search

The **Command Palette** (press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>) supports Korean initial-consonant (chosung) search: typing `ㅂㅅ` matches `복사` (copy), `ㅊㅅ` matches `취소` (cancel), and so on. This is powered by a dedicated Hangul helper that decomposes Korean syllables into their chosung components at match time.

Note: chosung search currently applies to the Command Palette's action list, not to regular file-name search in folder views.

## Tips & gotchas

> **Tip:** Use type-ahead for a known file in the current folder, the filter bar for a wildcard pattern across open columns, and recursive search for anything deeper.

> **Tip:** Combine `kind:` with `date:` to triage recent work — `kind:image date:today` pulls every picture added today.

> **Tip:** Press <kbd>Esc</kbd> during a long recursive search — Span Finder cancels cleanly and restores your previous view. No lost state.

> **Gotcha:** Recursive search walks from the **navigation root** (the leftmost Miller column), not the currently focused column. If you want a smaller scope, navigate to the desired subfolder first and open it as a new root.

> **Gotcha:** Results cap at 10,000 items. Tighten your query (add `size:>10MB` or `date:thisweek`) if you are hitting the cap.

## See also

- [Miller Columns](../miller-columns/) — Type-ahead lives here
- [File Operations](../file-operations/) — Run batch operations on search results
- [Preview](../preview/) — Preview files directly from the result list
- [Keyboard Shortcuts](../../shortcuts/)
