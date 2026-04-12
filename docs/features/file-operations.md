---
title: File Operations
layout: default
parent: Features
nav_order: 6
---

# File Operations
{: .no_toc }

Copy, move, rename, delete, compress, extract, and undo any of it — all with progress, conflict handling, and a full history stack.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

Span Finder handles every common file operation you expect from a file manager plus a few power features Windows Explorer lacks: batch rename with patterns, ZIP compression from the context menu, and a full Undo/Redo stack that covers copy, move, delete, rename, compress, and extract.

## Basic operations

| Shortcut | Action |
|---|---|
| <kbd>Ctrl</kbd> + <kbd>C</kbd> | Copy |
| <kbd>Ctrl</kbd> + <kbd>X</kbd> | Cut |
| <kbd>Ctrl</kbd> + <kbd>V</kbd> | Paste |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>V</kbd> | Paste as shortcut (.lnk) — see [Shortcut files](#shortcut-files-lnk) |
| <kbd>Ctrl</kbd> + <kbd>D</kbd> | Duplicate selected items (appends " copy") |
| <kbd>F2</kbd> | Rename |
| <kbd>Delete</kbd> | Move to Recycle Bin |
| <kbd>Shift</kbd> + <kbd>Delete</kbd> | Permanent delete |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>N</kbd> | New folder |
| <kbd>Alt</kbd> + <kbd>Enter</kbd> | Properties |
| <kbd>Ctrl</kbd> + <kbd>Z</kbd> | Undo |
| <kbd>Ctrl</kbd> + <kbd>Y</kbd> | Redo |

### Progress, pause, cancel

Long-running copies and moves show a progress dialog with pause, resume, and cancel buttons. Multiple operations run concurrently — you can queue up several copies and they will all make progress in parallel without blocking the UI.

### Virtual file paste

<kbd>Ctrl</kbd> + <kbd>V</kbd> handles virtual files too. You can paste attachments dragged from Outlook or files copied from a Remote Desktop session directly into a Span Finder folder.

## Rename

### Single rename

Press <kbd>F2</kbd> to enter inline rename mode. Press <kbd>Enter</kbd> to confirm or <kbd>Esc</kbd> to cancel.

Pressing <kbd>F2</kbd> repeatedly cycles the selection through three useful presets:

1. **File name only** (everything before the last dot)
2. **Full name** (including extension)
3. **Extension only**

This is a shortcut for users who rename files constantly — you don't need to manually select the part you want to edit.

### Batch rename

Select multiple files and press <kbd>F2</kbd> to open the Batch Rename dialog. It supports:

- **Find and replace** with optional regex and case sensitivity
- **Prefix / suffix** — add text to the start or end of every name
- **Sequential numbering** — `{n}` placeholder with configurable start and padding
- **Template patterns** — `{name}`, `{n}`, `{ext}` placeholders to rebuild names from scratch
- **Live preview** — see the new names before you commit
- **Conflict detection** — duplicate target names are highlighted before you apply

### Extension toggle

Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>H</kbd> to toggle file extension visibility everywhere in the app.

## Delete

- **Move to Recycle Bin** — <kbd>Delete</kbd>. Recoverable from the Recycle Bin tab.
- **Permanent delete** — <kbd>Shift</kbd> + <kbd>Delete</kbd>. Skips the Recycle Bin entirely.
- **Delete confirmation dialog** — Configurable in Settings (on by default).

The Recycle Bin appears as a dedicated tab where you can browse, restore, or empty it from the toolbar.

## Duplicate

<kbd>Ctrl</kbd> + <kbd>D</kbd> creates a copy in the same folder with " copy" appended. Select multiple files and Span Finder duplicates each one in a single operation that can be undone as a unit.

## Compress and extract

ZIP compression and extraction are available from the context menu on selected items:

- **Compress to ZIP** — Bundles the current selection into a new .zip in the same folder
- **Extract here** — Unpacks a ZIP into the current folder
- **Extract to folder** — Unpacks into a new subfolder named after the archive

Both operations are covered by Undo/Redo.

## Undo and Redo

Span Finder tracks every file operation in a per-window history stack. <kbd>Ctrl</kbd> + <kbd>Z</kbd> undoes the last operation; <kbd>Ctrl</kbd> + <kbd>Y</kbd> redoes it.

Supported operations:

- Copy
- Move
- Rename (single and batch)
- Delete (Recycle Bin only — permanent delete cannot be undone)
- Duplicate
- ZIP compression
- ZIP extraction

The default history depth is **50** operations and is configurable in Settings (range: 1–100).

Undo and Redo themselves are recorded in the [Action Log](#action-log) so you can audit exactly what happened.

## Conflict resolution

When a copy or move would overwrite an existing file, Span Finder prompts you per conflict:

- **Skip** — Leave the existing file alone
- **Replace** — Overwrite the existing file
- **Rename** — Append `" (n)"` to the incoming file name

Choose **Apply to all** to reuse the same decision for every remaining conflict in the operation.

For duplicates within the same folder (for example, <kbd>Ctrl</kbd> + <kbd>D</kbd>), Span Finder automatically appends `" (2)"`, `" (3)"`, etc. to avoid overwriting anything.

## Drag and drop

Drag-and-drop is just another way to invoke copy/move:

- **No modifier** — Move within the same drive, copy across drives (Windows convention)
- **Hold <kbd>Ctrl</kbd>** — Force copy
- **Hold <kbd>Shift</kbd>** — Force move
- **Spring-loaded folders** — Hover a folder for 800 ms while dragging to open it automatically

Drag targets include Span's own panes (including [Split View](../split-view/)), the sidebar Favorites section, Windows Explorer, and the Desktop.

## Action log

Every file operation is written to the Action Log (JSON, up to 1,000 entries, FIFO). The log viewer shows timestamp, operation type, status, and affected paths. You can filter for errors only, sort by any column, and clear the history.

## Tips & gotchas

> **Tip:** If a copy fails partway through, the Action Log captures the exact error. Filter by "errors only" to review what went wrong.

> **Tip:** Batch rename with `{n:03}` creates zero-padded numbers (`001`, `002`, `003`), perfect for photo sequences.

> **Gotcha:** Permanent delete (<kbd>Shift</kbd> + <kbd>Delete</kbd>) is **not** undoable. Only Recycle Bin deletes can be restored with <kbd>Ctrl</kbd> + <kbd>Z</kbd>.

> **Gotcha:** Conflict resolution does not apply to system-locked files — Windows will still refuse to overwrite in-use files and Span Finder will report the error.

## Shortcut files (.lnk)

<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>V</kbd> pastes the clipboard contents as a Windows shortcut (`.lnk`) instead of copying the actual file.

Clicking a `.lnk` file in SPAN Finder resolves the target automatically:
- **Folder target** → next Miller Column shows the target folder's contents
- **File target** → preview panel shows the target file's content
- **Double-click / Enter** → navigates into the target folder, or opens the target file with the default app

See [Preview Panel — Shortcuts](../preview/#shortcuts-lnk-files) for details on how `.lnk` previews work.

## See also

- [Split View](../split-view/) — Drag between panes
- [Search](../search/) — Find files first, then batch-operate on the results
- [Tabs](../tabs/) — Undo history is per window, shared across tabs
- [Keyboard Shortcuts](../../shortcuts/)
