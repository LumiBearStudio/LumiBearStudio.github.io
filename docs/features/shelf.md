---
title: Shelf
layout: default
parent: Features
nav_order: 2
description: "The File Shelf — temporary holding area for batch file operations across folders."
---

# File Shelf
{: .no_toc }

A temporary holding area for files and folders, so you can collect items from many places and then move or copy them all at once.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is the Shelf?

Think of the Shelf as a **workshop bench**. You walk around the shop picking parts off different racks, drop them on the bench as you find them, and when you have everything you need you carry the whole pile to where it belongs. No trips back and forth, no forgetting what you were doing, and no worrying that the pile will disappear if the phone rings.

In Span Finder, that bench is a slim panel on the **right edge** of the window. Drop any file or folder onto it — from any tab, any path, any drive. Keep browsing. When you reach the destination folder, click **Move here** or **Copy here** and the whole pile lands in one operation. The pile also survives app restarts, so you can start curating tonight and finish tomorrow.

The Shelf is deliberately quiet: when empty it slides off-screen entirely, and once you drop an item into it, it shrinks to a 36-pixel badge on the right edge until you hover over it. That way it never steals workspace from the folders you are actually browsing.

## Why use the Shelf instead of copy-paste?

The obvious alternative is the clipboard — cut, navigate, paste. It works, but it hits a wall the moment your workflow gets even slightly non-linear.

| | Clipboard (Cut/Copy + Paste) | Shelf |
|:---|:---|:---|
| Items held at once | One batch | Up to 50, from any mix of folders |
| Visibility | Invisible — no way to see what is queued | Always visible (as a badge or full panel) |
| Pulling from many folders | Must paste between each pickup, or overwrite the clipboard | Drop, keep browsing, drop again |
| Reuse the same set | Lost after first paste | Stays until you clear it |
| Lock specific items | Not possible | Pin them — survives Move and Clear |
| Survives app restart | No | Yes (if "Save on exit" is on — default) |
| Drag as source | Limited | Drag items back out to any folder column |

The short version: **the clipboard is for one hop, the Shelf is for routes**.

## When to use it (3 real scenarios)

### Scenario 1: Photo curation

You shot 500 photos on a trip and want to cherry-pick the best 30 into a `Best/` folder for your album.

1. Open `Pictures/Trip/2026/`.
2. Scroll through the thumbnails. When you see a keeper, drag it to the right edge — the Shelf slides out to catch it. Drop and keep scrolling.
3. Multi-select and drag in batches when you hit an obvious run of good shots.
4. Need to check the RAW files in a sibling folder? Switch folders. The Shelf keeps everything you already collected.
5. When you are done, navigate to `Pictures/Trip/2026/Best/`.
6. Click **Move here**. All 30 photos land in one atomic operation.

### Scenario 2: Code refactor — collecting files to relocate

You are reorganizing a project. Three component files in `src/components/`, one helper in `src/utils/`, and a stylesheet in `src/styles/` all need to move into a new `src/features/auth/` folder.

1. Open `src/components/`, Ctrl-click the three component files, drag them to the Shelf.
2. Open `src/utils/`, drag the helper over.
3. Open `src/styles/`, drag the stylesheet over.
4. Navigate to `src/features/auth/` (creating it first if needed).
5. Click **Move here**. Five files from three folders, one click.

Because Span's Move is undo-aware, if you change your mind, `Ctrl+Z` rolls the whole thing back.

### Scenario 3: Receipt collection for tax season

Your receipts arrive all year as email attachments saved to `Downloads/`, screenshots in `Pictures/`, and PDFs in `Documents/`. Once a quarter you file them.

1. Navigate through each source folder picking out the receipts. Drag each to the Shelf as you find them.
2. **Pin** the "Receipt template.xlsx" — you refer to it often, so you want it to stick around even after the batch operation.
3. Navigate to `Documents/Taxes/2026Q1/`.
4. Click **Copy here** (you want a copy for the archive, not a move).
5. The pinned template stays on the Shelf for next quarter. Everything else copied over cleanly.

## Opening the Shelf

The Shelf has **three visual states**:

| State | Width | When |
|:---|:---|:---|
| Hidden | 0 px (off-screen) | Empty and not summoned |
| Collapsed | 36 px badge showing item count | Has items, cursor away |
| Full | 270 px panel | Summoned, or cursor hovering the collapsed badge |

It auto-shows in three situations:

1. **You drag a file near the right edge** — The Shelf slides out (Yoink-style) to receive the drop.
2. **You press the toggle shortcut** (`Ctrl+B` by default) or trigger **Add to Shelf** (`Ctrl+Shift+B`) — The panel opens to full width.
3. **The Shelf already has items** — It stays as a 36-px badge until you hover over it, at which point it expands to full width. Move the cursor away and after ~500 ms it slinks back to badge.

When the Shelf is completely empty and you are not dragging anything, it hides off-screen entirely so it never eats workspace.

> **Tip:** If you find the auto-collapse distracting while you work inside the Shelf, hold the cursor inside the panel — it only collapses when the pointer leaves. For a permanent toggle, use the close button (`X`) in the header to hide it entirely.

## Adding items

There is no single "right" way to add items — Span accepts everything a normal file manager would.

- **Drag from a folder column** to the Shelf. Works from Miller columns, Details view, and Icon view.
- **Drag from another application** (another Explorer window, Visual Studio, Chrome downloads bar, etc.) onto the Shelf. Anything that exposes file paths via standard OS drag-drop works.
- **Multi-select then drag.** Shift-click for range, Ctrl-click for individual selection. Whatever is selected when you start the drag comes along.
- **Ctrl+Shift+B** on the current selection adds it to the Shelf without touching the mouse.

Adding an item that is already on the Shelf is a no-op — duplicates are silently skipped.

## Working with items in the Shelf

### Multi-select

The Shelf list behaves like any file list. Click to select one, **Shift-click** for a range, **Ctrl-click** to toggle individual items, or drag a rubber-band rectangle across the items to select multiple at once.

### Drag items out

You can drag items **from** the Shelf to any folder column to move them there. The default drag operation is **Move** — the item is removed from the Shelf once the drop succeeds. Hold `Ctrl` while dragging to **Copy** instead (the item stays on the Shelf).

Pinned items are never removed from the Shelf after a drag-out, even on a Move operation.

### Pin / Unpin

Hover over an item in the Shelf list. Two small buttons appear on the right — a **pin** and an **X**. Click the pin to lock the item. Pinned items display a small pin indicator in the top-right corner of their icon, and they have two important properties:

- They **survive Clear All** (the trash icon in the Shelf header leaves them in place).
- They **survive Move here** (the batch Move operation leaves pinned items on the Shelf but updates their stored paths to point to the new destination).
- They **persist across app restarts** along with their pin state.

You can also right-click an item and choose **Pin** / **Unpin** from the context menu.

Unpinning works the same way — click the pin button again or use the context menu.

### Right-click menu

Right-click any Shelf item for:

- **Open** — launches the file with its default application (via the shell).
- **Go to source** — navigates the active tab to the folder the item came from.
- **Pin** / **Unpin** — toggle lock state.
- **Remove** — takes the item off the Shelf (does not delete the file).

### Open an item

Double-click any item to open it with the system default application. Folders open in a new location in the active tab.

### Remove

Hover an item and click the ✕ button, or select one or more items and press `Delete`. This only removes the item from the Shelf — it never deletes the actual file on disk.

### Clear all (except pinned)

The trash icon in the Shelf header (top-right area) clears every **unpinned** item in a single click. Pinned items stay exactly where they are. If a Clear leaves the Shelf with at least one pinned item, a toast notification confirms that the pinned items were kept.

### Close the panel

The **X** button next to the trash icon fully hides the Shelf (slides it off-screen). If items remain, the Shelf will still reappear as a 36-px badge the next time you move the cursor to the right edge — hiding is not the same as clearing.

## Moving and copying to a destination

The footer of the Shelf panel has two buttons:

- **Move here** — batch-moves every item currently on the Shelf to the active tab's current folder. Unpinned items are removed from the Shelf; pinned items are kept (and their recorded source path is updated to point to the destination).
- **Copy here** — batch-copies every item to the active tab's current folder. Nothing is removed from the Shelf. Use this when you want the same batch to go to multiple destinations.

Both buttons use Span's standard file operation engine, which means they inherit:

- **Progress reporting** in the operation status bar
- **Conflict resolution** (skip / replace / rename / apply-to-all)
- **Undo support** (`Ctrl+Z` reverts the entire batch)
- **Continue-on-error** behavior for read-only or in-use files

> **Tip:** You can also **drag items out of the Shelf** directly onto any folder column in Miller view to move them just to that folder. This is handy when you want to split the Shelf pile across several destinations — dribble a few to one folder, a few to another.

## Capacity and limits

| Limit | Value | Why |
|:---|:---|:---|
| Max items | **50** | Performance, visual clarity, and to nudge you to actually complete your batch |
| Max selection size per drop | Unlimited (until the 50-item cap) | Drop a whole Explorer window worth of selection in one go |
| Persistence | Yes (JSON, local settings) | Safe across app restarts |
| Sharing between windows | No (per-window) | Each SPAN window has its own Shelf (see FAQ) |

When you try to add an item that would push the total past 50, the Shelf rejects the new item and shows a brief toast notification. Remove some items or complete your batch first.

## Persistence — what survives an app restart?

On app exit, Span serializes the Shelf to a JSON blob in the application settings. On the next launch, it deserializes and reconstructs the Shelf.

What is saved:

- The **full path** of each item.
- The **pin state** (`IsPinned`) of each item.

What is *not* saved (it is recomputed fresh on load):

- Icons (rebuilt from the current icon theme).
- File size and timestamps (re-read from disk).
- Selection state, scroll position, hover state.

On load, Span rebuilds each item by checking that the file or folder still exists. **Items whose underlying path no longer exists are silently filtered out** — you will not see ghost entries pointing at deleted files.

Span also understands an older storage format from pre-pin versions (a plain `List<string>` of paths). If it finds one, it auto-migrates every path to the new format with `IsPinned = false`. You do not need to do anything.

If you turn off **Save Shelf on exit** in Settings, Span writes an empty Shelf at shutdown, effectively clearing it for the next session.

## Auto-hide behavior

The Shelf panel's visibility is derived from three internal signals (from `MainViewModel.IsShelfPanelVisible`):

```
Visible  =  user manually toggled it on
         OR something is being dragged near the right edge
         OR the Shelf currently has at least one item
Hidden   =  none of the above
```

In practical terms:

- **Empty + idle** → hidden off-screen. Shelf does not exist visually.
- **Dragging near the right edge** → slides out to full panel (Yoink mode).
- **Has at least one item** → stays as a 36-px badge on the right edge; expands to full on hover; collapses again 500 ms after the cursor leaves.
- **You pressed `Ctrl+B`** → opens to full panel regardless of count, stays open until you press `Ctrl+B` again or click **X**.

Once you drop the first item, the Shelf stays visible (as a badge minimum) until you either clear it entirely or click the close button.

## Settings

Open **Settings → Sidebar** (or search "shelf" in Settings) for:

- **File Shelf** (`ShelfEnabled`, default **on**) — master switch. When off, the panel is hidden, drag-to-right-edge does nothing, and the `Ctrl+B` / `Ctrl+Shift+B` shortcuts no-op. Useful if you prefer to keep workflows strictly inside the columns.
- **Save Shelf on exit** (`ShelfSaveEnabled`, default **on**) — persist the Shelf contents across app restarts. Turn off if you want each session to start with a clean Shelf.

Toggling **File Shelf** off at runtime also stops any active collapse timers and pointer tracking immediately. Toggling it back on with items still saved restores them directly to the collapsed (36-px badge) state.

## Keyboard shortcuts

Both shortcuts are defined in `KeyBindingService` and are fully remappable from **Settings → Shortcuts**.

| Action | Default | Remappable |
|:---|:---|:---|
| Toggle Shelf panel (open/close) | `Ctrl+B` | Yes |
| Add current selection to Shelf | `Ctrl+Shift+B` | Yes |
| Remove selected Shelf items | `Delete` (when Shelf list has focus) | Built-in |

There are currently **no default shortcuts** for "Move here", "Copy here", or "Clear all" — those are click-only actions. If you use them frequently, remap them in **Settings → Shortcuts** (the Shelf command palette entries surface the same operations).

[Full shortcuts list](../../shortcuts/)

## FAQ

### Will Shelf items be moved if I drag them out to a folder?

Yes — drag is a **move** by default, and the item is removed from the Shelf when the drop completes. Hold `Ctrl` while dragging to **copy** instead (item stays on the Shelf). Pinned items are always kept on the Shelf even on a move.

### What happens to Shelf items if I delete the original file outside of Span?

The file disappears from disk, but the entry stays on the Shelf until the next time Span reloads it (at app restart). On load, Span checks every stored path against the filesystem and drops entries whose underlying file or folder no longer exists. You will not see permanent ghost entries.

If you want the ghosts gone immediately, restart the app or manually remove them with the ✕ button.

### Can I have multiple separate Shelves?

Not currently. There is one Shelf per SPAN window, and it is shared across every tab within that window. Named or multiple-workspace Shelves are on the backlog.

### Does the Shelf sync across multiple SPAN windows?

**No.** Each SPAN window owns its own Shelf in memory. Only **one window's Shelf is persisted** across restarts (whichever saves last wins). Treat the Shelf as per-window for now — collect and drop inside the same window to avoid surprises.

### Why can't I see the Shelf at all?

One of four things:

1. **It is empty** and auto-hidden. Drag any file to the right edge of the window (or press `Ctrl+B`) to summon it.
2. **It is collapsed** to the 36-px badge on the right edge. Hover over the right edge and it will expand.
3. **It is disabled** in Settings. Open **Settings → Sidebar → File Shelf** and turn it on.
4. **The window is very narrow** and the badge is hidden behind other UI. Resize the window wider.

### Does Move here respect conflict resolution?

Yes. Move here and Copy here both use Span's standard file operation engine, so you get the normal conflict dialog (skip / replace / rename, with "apply to all") and full undo support via `Ctrl+Z`.

### Are pinned items persistent across restarts?

Yes. Pin state is serialized alongside the path and restored on the next launch.

### Can I clear the Shelf without losing pinned items?

Yes — that is exactly what **Clear all** (the trash icon in the Shelf header) does. Pinned items stay, unpinned items are removed, and a toast notification confirms pinned items were kept.

### What's the max number of items?

50. Attempting to add more shows a "Shelf is full" toast and rejects the new items until you make room.

## See also

- [Miller Columns](../miller-columns/) — The view mode that pairs most naturally with drag-to-Shelf workflows
- [Tabs](../tabs/) — Use multiple tabs and the Shelf together for cross-folder collection
- [Keyboard Shortcuts](../../shortcuts/) — Full shortcut list including Shelf bindings
