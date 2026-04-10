---
title: Quick Look
layout: default
parent: Features
nav_order: 9
---

# Quick Look
{: .no_toc }

Press <kbd>Space</kbd> to preview any file instantly in a large, modal window — macOS Finder style. Keep tapping arrow keys to flip through files without ever closing the preview.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

Quick Look is a modal preview dialog that pops up over the Span Finder window when you press <kbd>Space</kbd>. Unlike the [Preview Panel](../preview/), which is a small side panel, Quick Look is a full-size preview window that gives the file's content the space it deserves.

It's the fastest way to triage a folder of photos, flip through PDFs, or glance at source code without opening your editor.

## Opening Quick Look

| Key | Action |
|---|---|
| <kbd>Space</kbd> | Open Quick Look on the current selection |
| <kbd>Space</kbd> (while open) | Close Quick Look |
| <kbd>Esc</kbd> | Close Quick Look |

Quick Look must be enabled in Settings — it's opt-in because <kbd>Space</kbd> is also sometimes used for item selection in traditional file managers. Enable it under **Navigation behavior** → **Quick Look (Space)**.

## Navigating while open

The killer feature: Quick Look does not lock you in. You can keep navigating the file list while the preview is open and Quick Look updates live.

| Key | Action |
|---|---|
| <kbd>Left</kbd> / <kbd>Right</kbd> | Preview previous / next file |
| <kbd>Up</kbd> / <kbd>Down</kbd> | Move through the file list (same as when Quick Look is closed) |
| <kbd>Space</kbd> | Close Quick Look |
| <kbd>Esc</kbd> | Close Quick Look |

This makes Quick Look ideal for quickly sorting through dozens or hundreds of files. Tap <kbd>Right</kbd> repeatedly to flip through a folder of images, pausing on the ones you want to keep.

## Supported file types

Quick Look uses the same renderers as the [Preview Panel](../preview/), so it supports:

- **Images** — JPEG, PNG, GIF, BMP, WebP, TIFF
- **Video** — MP4, MKV, AVI, MOV, WMV, WEBM
- **Audio** — MP3, AAC, M4A with artist/album/duration metadata
- **Text and code** — 30+ extensions with syntax-aware rendering
- **PDF** — First page preview
- **Markdown** — Rendered with your current light/dark theme
- **CSV / TSV** — Table view (up to 200 rows)
- **Fonts** — Glyph samples
- **Binary** — Hex dump fallback (first 512 bytes)

## Window size persistence

Quick Look remembers the last size and position you used. Resize it once to fit your workflow and every subsequent invocation opens at that size. The setting persists across app restarts.

## Quick Look vs. Preview Panel

| | Preview Panel | Quick Look |
|---|---|---|
| **Shortcut** | <kbd>Ctrl</kbd> + <kbd>P</kbd> | <kbd>Space</kbd> |
| **Type** | Persistent side panel | Modal dialog |
| **Size** | Small / medium | Large, resizable |
| **Navigate while open** | Automatic (selection-driven) | Arrow keys |
| **Best for** | Glancing at metadata while browsing | Triaging folders, reviewing content |
| **Per-pane in Split View** | Yes, independent per pane | No, one global instance |

Most people use both: Preview Panel as a constant companion, Quick Look as a deep-dive shortcut.

## Tips & gotchas

> **Tip:** Quick Look flips through files in the **current sort order**. Sort by date to walk through a folder in chronological order, or by size to triage large files first.

> **Tip:** Use Quick Look with [Search](../search/) results — after running a recursive search, tap <kbd>Space</kbd> on each hit to see what it actually contains without opening anything.

> **Tip:** The remembered window size is per-user, not per-file-type. Resize it to a shape that works for both portrait photos and wide code files.

> **Gotcha:** Quick Look respects the same 20 MB thumbnail limit as the preview panel. Gigantic files fall back to the Shell thumbnail cache.

> **Gotcha:** Quick Look is a single global instance. If you use [Split View](../split-view/), pressing <kbd>Space</kbd> always previews the currently focused pane's selection.

## See also

- [Preview Panel](../preview/) — The smaller, always-visible companion
- [Miller Columns](../miller-columns/) — Where <kbd>Space</kbd> lives
- [Search](../search/) — Triage results with Quick Look
- [Keyboard Shortcuts](../../shortcuts/)
