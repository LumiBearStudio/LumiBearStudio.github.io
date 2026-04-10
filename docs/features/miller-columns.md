---
title: Miller Columns
layout: default
parent: Features
nav_order: 1
---

# Miller Columns
{: .no_toc }

Span Finder's signature navigation mode — the feature most users install the app for. If you have ever missed macOS Finder's column view on Windows, this is the page for you.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

Miller Columns is a hierarchical file browser that shows **every level of a folder path at the same time**, laid out left to right. Click a folder in column 1 and its contents appear in column 2. Click a subfolder in column 2 and column 3 opens. You never lose track of where you are, where you came from, or what siblings exist at each level.

Traditional Windows Explorer replaces the current view every time you enter a folder. You have to mentally stack breadcrumbs in your head and click Back to undo a wrong turn. Miller Columns eliminates that problem — the entire path is visible on screen, all the time.

> **Tip:** Press <kbd>Ctrl</kbd> + <kbd>1</kbd> at any time to switch back to Miller Columns from another view mode.

## When to use it

Miller Columns shines when you are:

- **Exploring an unfamiliar folder tree** — you can see siblings at every level without backtracking
- **Moving or copying across deep hierarchies** — drag between columns without losing context
- **Auditing project structures** — see at a glance how folders are organized
- **Drilling into monorepos or source trees** — `src` → `Span` → `Services` → `.cs` file, all visible at once

If you mostly work in a flat directory, switch to **Details** (<kbd>Ctrl</kbd> + <kbd>2</kbd>) or **Icons** (<kbd>Ctrl</kbd> + <kbd>4</kbd>) instead.

## How it works

### Opening a folder

Click a folder. A new column slides in to the right showing its contents. The previously active column stays visible — its selection is still highlighted so you know the full path.

Double-click behavior is configurable in Settings. By default Miller Columns uses **single-click to navigate** (like macOS Finder), but you can set it to **double-click** if you prefer Windows Explorer semantics.

### Keyboard navigation

Miller Columns is built for the keyboard. Every common action has a shortcut:

| Key | Action |
|---|---|
| <kbd>Left</kbd> / <kbd>Right</kbd> | Move between columns |
| <kbd>Up</kbd> / <kbd>Down</kbd> | Move within the current column |
| <kbd>Enter</kbd> | Open folder / launch file |
| <kbd>Backspace</kbd> | Go up one column (back toward the root) |
| <kbd>Home</kbd> / <kbd>End</kbd> | Jump to first / last item in the column |
| <kbd>A</kbd>–<kbd>Z</kbd>, <kbd>0</kbd>–<kbd>9</kbd> | Type-ahead search — starts filtering the column as you type (800 ms buffer) |
| <kbd>Space</kbd> | Open Quick Look preview (if enabled in Settings) |

Because every column is independently focusable, you can navigate with arrows alone — no mouse required.

### Column widths

Drag any column separator to resize. Three handy defaults cover most situations:

| Action | Shortcut / Gesture |
|---|---|
| Equalize all columns to the same width | <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>=</kbd> |
| Auto-fit the active column to its longest item | <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>-</kbd> |
| Auto-fit a single column to its content | Double-click its right edge |
| Apply the current column's width to **every** column | Hold <kbd>Ctrl</kbd> while dragging the separator |

Column widths are saved per session and restored on the next launch.

### Auto-scroll

As you drill deeper, Span Finder smoothly scrolls horizontally to keep the active column in view. You never have to manually pan.

## Miller Columns vs. traditional tree view

| | Tree view (Explorer left pane) | Miller Columns |
|---|---|---|
| **Shows siblings at every level** | Only for the path you expanded | Yes, always |
| **Wasted vertical space on deep trees** | High — long indented lines | None — horizontal layout |
| **Click to change level** | Requires expand/collapse discipline | Single click moves laterally |
| **Keyboard navigation** | Up/Down only | Arrows in two dimensions |
| **Good for wide folders** | No — vertical scroll mess | Yes — column width is adjustable |

A tree view forces you to think of folders as a vertical outline. Miller Columns treats the hierarchy as a conveyor belt that slides sideways — most people who try it stop going back.

## Settings

Open Settings with <kbd>Ctrl</kbd> + <kbd>,</kbd> and look under **Appearance** and **Navigation** for Miller-specific options:

- **Click behavior** — Single click (default) vs. double click to enter a folder
- **Thumbnails** — Show/hide image thumbnails in Miller cells
- **Checkboxes** — Enable checkbox selection mode
- **Row density** — Compact / Comfortable / Spacious (paired with 6-step font/icon size)
- **Hidden files** — Show or hide dotfiles and system-hidden items
- **File extensions** — Toggle extension visibility (also <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>H</kbd>)

## Tips & gotchas

> **Tip:** Use <kbd>Backspace</kbd> instead of <kbd>Alt</kbd> + <kbd>Left</kbd> when you want to go one level up. `Alt+Left` goes back in **history**, which may not be the parent folder if you navigated laterally.

> **Tip:** When comparing two folders at the same depth, open **Split View** (<kbd>Ctrl</kbd> + <kbd>E</kbd>) and put Miller Columns on both sides.

> **Gotcha:** Type-ahead search has an 800 ms buffer. If you pause, the next keypress starts a new search. This matches Finder and Explorer behavior.

> **Gotcha:** Very wide columns can push the active column off-screen on small displays. Use <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>-</kbd> to auto-fit everything at once.

## See also

- [Tabs](../tabs/) — Each tab keeps its own Miller Columns state
- [Split View](../split-view/) — Put two Miller Column trees side by side
- [Preview Panel](../preview/) — Show file previews without leaving the column view
- [Quick Look](../quick-look/) — Press <kbd>Space</kbd> for a large modal preview
- [Keyboard Shortcuts](../../shortcuts/) — Full reference
