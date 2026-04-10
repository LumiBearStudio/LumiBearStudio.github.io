---
title: Tabs
layout: default
parent: Features
nav_order: 3
---

# Tabs
{: .no_toc }

Open as many folders as you want in a single window, tear tabs out into new windows, re-dock them, and pick up exactly where you left off after restart.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

Span Finder gives every folder its own tab — like a browser. Each tab has an independent path, view mode, navigation history, and (if you use it) a split-view state. You can open unlimited tabs in a window, drag tabs between windows, tear a tab out to create a new window, and have every tab restored automatically the next time you launch the app.

Windows 11 File Explorer added basic tabs, but it does not offer tear-off, re-docking, duplication, session restore across restarts, or per-tab view modes. Span Finder does.

## Opening, closing, and switching

| Shortcut | Action |
|---|---|
| <kbd>Ctrl</kbd> + <kbd>T</kbd> | New tab |
| <kbd>Ctrl</kbd> + <kbd>W</kbd> | Close current tab |
| <kbd>Ctrl</kbd> + <kbd>N</kbd> | New window |
| <kbd>Ctrl</kbd> + <kbd>Tab</kbd> | Next tab |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>Tab</kbd> | Previous tab |
| Middle-click a tab header | Close that tab |
| Middle-click a folder / drive / favorite | Open it in a new tab |

> **Korean keyboard note:** <kbd>Ctrl</kbd> + <kbd>T</kbd>, <kbd>Ctrl</kbd> + <kbd>W</kbd>, <kbd>Ctrl</kbd> + <kbd>Tab</kbd>, and numeric switchers work on Korean IME layouts without any extra config. If you use <kbd>Ctrl</kbd> + <kbd>&#96;</kbd> to open a terminal and it doesn't register, <kbd>Ctrl</kbd> + <kbd>'</kbd> is available as a fallback — Span Finder adds both because the backtick scancode differs on Korean keyboards.

## Tab context menu

Right-click any tab header for quick actions:

- **Duplicate** — Clones the tab with its exact path, view mode, and icon size
- **Close** — Close this tab
- **Close others** — Keep only the right-clicked tab
- **Close tabs to the right** — Keep this tab and everything to the left
- **Move to new window** — Tear the tab off without dragging
- **Save tab layout...** — Save all current tabs as a [Workspace](../workspaces/)

## Tear-off and re-docking

Drag a tab away from the tab bar and you get a brand-new window containing just that tab. Drop a tab from another Span Finder window onto your tab strip to re-dock it.

- **Dragging out of the window** — Tear-off. The new window opens where you drop and a TabStateDto snapshot carries the path, history, view mode, and split state.
- **Dragging onto another Span Finder window** — Re-dock. A ghost-tab indicator shows exactly where the tab will land and the target window becomes slightly translucent while hovering.
- **Dragging within the same tab bar** — Reorder.
- **Dragging a single-tab window** — Moves the window instead of tearing (tear-off is suppressed when there is nothing left behind).

Tab widths are fixed, Chrome-style — dragging a tab with a long folder name will not shove its neighbors around.

## Session restore

By default, Span Finder remembers your tabs between sessions. Close the app with 12 tabs open across two windows, and the next launch brings them all back — same paths, same view modes, same split states, same Miller column selections.

To change this behavior:

1. Press <kbd>Ctrl</kbd> + <kbd>,</kbd> to open Settings
2. Navigate to **Startup behavior**
3. Choose between **Restore last session** (default) or **Home screen**

You can also disable tab session saving entirely under **Window & Session** settings.

> **Tip:** Session restore validates every saved path before opening. If a folder was deleted or a USB drive was ejected, the tab is skipped gracefully — no error dialogs on startup.

## Per-tab state

Every tab independently tracks:

- **Current folder path and selection**
- **Navigation history** (Back / Forward stack, up to 50 entries)
- **View mode** — Miller / Details / List / Icons
- **Icon size** (for the Icons view)
- **Split view** — Whether it's on, which folders are open in each pane, each pane's view mode
- **Preview panel state** — Open/closed, file being previewed

Switching tabs restores all of this instantly thanks to per-tab folder caches.

## Special tabs

- **Home** — Shows quick access, recent folders, and favorites. One click away from any new tab.
- **Settings** — Opens as a dedicated tab (<kbd>Ctrl</kbd> + <kbd>,</kbd>). Only one Settings tab can exist at a time, and it is excluded from session save.
- **Recycle Bin** — Opens as a regular tab that you can browse, restore from, or empty.

## Workspaces

When you have a tab layout you want to reuse — say, "client-A project" across five specific folders, or "photo editing" across your RAW input and JPEG output folders — save it as a **workspace**:

- <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd> — Save the current tab layout as a workspace
- <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>W</kbd> — Open the workspace palette to restore, rename, or delete one

See the [Workspaces](../workspaces/) page for the full writeup.

## Multi-window

You can open as many Span Finder windows as you need. Each window owns its own tab set. Closing the last window exits the app — the app registers and unregisters every window centrally, so tabs in background windows never disappear unexpectedly.

## Tips & gotchas

> **Tip:** Hold <kbd>Ctrl</kbd> while middle-clicking a folder in the sidebar to open it as a new tab in the background without switching focus.

> **Tip:** Re-docking lets you consolidate scattered windows. Drag every stray tab back into your main window at the end of the day.

> **Gotcha:** Session restore saves **tab paths**, not open files. If you had a file selected in Quick Look when you quit, Quick Look will not reopen automatically.

## See also

- [Miller Columns](../miller-columns/) — Each tab has its own Miller state
- [Split View](../split-view/) — Works independently per tab
- [Workspaces](../workspaces/) — Save and restore named tab layouts
- [Keyboard Shortcuts](../../shortcuts/) — Full shortcut reference
