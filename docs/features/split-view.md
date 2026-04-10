---
title: Split View
layout: default
parent: Features
nav_order: 4
---

# Split View
{: .no_toc }

Two folders, one tab, true dual-pane file browsing. Perfect for copying, comparing, and moving files between locations without juggling windows.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

Split View turns a single tab into two independent file panes. Each pane has its own current folder, its own view mode, its own selection, and its own preview panel. Drag a file from the left pane to the right pane to copy or move it — no alt-tabbing between windows, no scrolling back and forth.

If you have ever used a dual-pane file manager like Total Commander, this will feel familiar. If you haven't, think of it as a pro mode for any task where your brain needs to see **source** and **destination** at the same time.

## When to use it

- **Moving files between two folders** — drag-and-drop beats cut/paste every time
- **Comparing folder contents** — side-by-side scrolling makes differences obvious
- **Organizing downloads** — keep `Downloads` in the left pane and your destination folder in the right
- **Photo editing workflows** — RAW input on the left, edited JPEG output on the right
- **Repository auditing** — two branches or two project roots at once

## Enabling Split View

| Shortcut | Action |
|---|---|
| <kbd>Ctrl</kbd> + <kbd>E</kbd> | Toggle Split View on / off |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>E</kbd> | Toggle Split View on / off (alternate binding) |
| <kbd>F6</kbd> | Switch focus between the two panes |

You can also toggle Split View from the toolbar. The command is available in the [Command Palette](../../shortcuts/) as well.

## Using the two panes

Once enabled, the tab splits vertically into a left and a right pane. They behave exactly like two mini file browsers inside the same tab:

- **Independent navigation** — Back / Forward, address bar, breadcrumbs, sidebar clicks all apply to the focused pane only
- **Independent view modes** — You can run Miller Columns on the left and Details on the right (or any other combination)
- **Independent preview panels** — Each pane can show or hide its own preview area
- **Independent selection** — Selecting items on the left never changes the right

Press <kbd>F6</kbd> to jump between panes without touching the mouse.

## Drag between panes

The whole point of Split View is dragging files between the two halves:

- **Drag with no modifier** — Move within the same drive, copy across drives (Windows default)
- **Hold <kbd>Ctrl</kbd> while dragging** — Force copy
- **Hold <kbd>Shift</kbd> while dragging** — Force move

The cursor shows copy / move / forbidden icons in real time so you always know what will happen when you release the mouse.

You can also drag from an external app (Explorer, Desktop, Chrome) directly into either pane.

## View modes per pane

Each pane can use any view mode independently:

- **Miller Columns** on the left, **Details** on the right is a great combination for surfing a tree while cross-referencing file metadata
- **Icons** on both sides is ideal for photo work
- **List** on one side and **Home** on the other gives you quick access plus a destination folder

Change a pane's view mode with <kbd>Ctrl</kbd> + <kbd>1</kbd>–<kbd>4</kbd> after focusing that pane.

## Per-tab split state

Split View is a **per-tab** setting. Tab A can be split while Tab B is full-width and Tab C is split with completely different folders. When you switch tabs, each tab restores its own split state — exactly how you left it.

This also means session restore remembers the split configuration of every tab across app restarts.

## Collapsing Split View

Press <kbd>Ctrl</kbd> + <kbd>E</kbd> again to collapse back to a single pane. Span Finder keeps whichever pane currently has focus and discards the other.

> **Tip:** If you want to swap which pane stays after collapsing, press <kbd>F6</kbd> first to focus the pane you want to keep, then toggle Split View off.

## Tips & gotchas

> **Tip:** Use Split View with [Workspaces](../workspaces/) to save entire side-by-side layouts. "Photo Editing" workspace can spawn a tab already split with RAW input and JPEG output folders.

> **Tip:** Sidebar clicks navigate the **focused** pane. If clicking Favorites navigates the wrong side, press <kbd>F6</kbd> first.

> **Gotcha:** Both panes share the same tab title. Span Finder shows the focused pane's folder name in the tab header.

> **Gotcha:** The preview panel is per pane, but a [Quick Look](../quick-look/) modal is global — it always previews the focused pane's selection.

## See also

- [Miller Columns](../miller-columns/) — Works great on either side
- [Tabs](../tabs/) — Every tab owns its own split state
- [Workspaces](../workspaces/) — Save split layouts for later
- [File Operations](../file-operations/) — The copy/move actions behind drag-and-drop
- [Keyboard Shortcuts](../../shortcuts/)
