---
title: Basic Navigation
layout: default
parent: Getting Started
nav_order: 3
---

# Basic Navigation
{: .no_toc }

From the address bar to keyboard shortcuts, here's everything you need to move around SPAN Finder with confidence.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## The address bar

The address bar at the top of each pane shows your current location. Click it (or press <kbd>Ctrl</kbd> + <kbd>L</kbd> / <kbd>Alt</kbd> + <kbd>D</kbd>) to type a path directly. Press <kbd>Enter</kbd> to navigate.

- **Breadcrumb chips** — Each folder segment is clickable; click any ancestor to jump up without losing your place in child columns.
- **Type-ahead** — As you type, the address bar suggests matching paths from your history and known locations.
- **Localized names** — You can type both the localized display name ("Downloads") and the raw path (`C:\Users\You\Downloads`) — both work.
- **Special paths** — `shell:RecycleBinFolder`, `shell:Desktop`, `ftp://`, `sftp://` are all valid.

## Miller Columns navigation

Miller Columns is SPAN Finder's primary navigation mode (<kbd>Ctrl</kbd> + <kbd>1</kbd>). Each column represents one folder level.

### Mouse navigation

| Action | Result |
|--------|--------|
| Click a folder | Opens it in the next column |
| Click a file | Shows its preview on the right |
| Double-click a folder | Navigates into it (in double-click mode) |
| Double-click a file | Opens it with the default app |
| Scroll horizontally | Pans between columns |

### Keyboard navigation

| Key | Action |
|-----|--------|
| <kbd>→</kbd> | Open selected folder / move to next column |
| <kbd>←</kbd> | Move to parent column |
| <kbd>↑</kbd> / <kbd>↓</kbd> | Move up/down in the current column |
| <kbd>Home</kbd> / <kbd>End</kbd> | Jump to first / last item |
| <kbd>Enter</kbd> | Open folder or file |
| <kbd>Backspace</kbd> | Go up to parent folder |
| <kbd>Alt</kbd> + <kbd>←</kbd> | Back (history) |
| <kbd>Alt</kbd> + <kbd>→</kbd> | Forward (history) |
| <kbd>Alt</kbd> + <kbd>↑</kbd> | Navigate to parent directory |

### Type-ahead search in columns

Start typing any letter while a column is focused and SPAN Finder jumps to the first matching item. Works with:
- Latin characters (case-insensitive)
- Korean Hangul chosung (초성 검색) — type `ㄷ` to jump to 다운로드

## Sidebar navigation

The sidebar on the left provides one-click access to common locations:

| Section | What's inside |
|---------|---------------|
| **Home** | Pinned favorites and quick links |
| **Favorites** | Folders you've pinned (drag to reorder) |
| **Recent** | Recently visited folders |
| **This PC** | Local drives (C:, D:, USB, etc.) |
| **Cloud** | OneDrive, iCloud, Dropbox (auto-detected) |
| **Network** | SMB shares and mapped drives |
| **Remote** | FTP/SFTP saved connections |
| **Recycle Bin** | Browse deleted files |
| **Workspaces** | Saved tab layouts |

**Tips:**
- **Middle-click** any sidebar item to open it in a new tab.
- **Right-click** to pin/unpin favorites or add a remote connection.
- Toggle sections on or off via **Settings → Sidebar**.

## Back, forward, and history

SPAN Finder maintains a per-pane navigation history — just like a browser.

| Shortcut | Action |
|---------|--------|
| <kbd>Alt</kbd> + <kbd>←</kbd> | Back |
| <kbd>Alt</kbd> + <kbd>→</kbd> | Forward |
| Right-click the Back button | History dropdown (jump to any prior location) |

## Switching view modes

| Shortcut | View |
|---------|------|
| <kbd>Ctrl</kbd> + <kbd>1</kbd> | Miller Columns |
| <kbd>Ctrl</kbd> + <kbd>2</kbd> | Details (table with size, date, type) |
| <kbd>Ctrl</kbd> + <kbd>3</kbd> | List (dense, multi-column) |
| <kbd>Ctrl</kbd> + <kbd>4</kbd> | Icons (thumbnail grid) |

Each tab remembers its own view mode independently.

## Tabs

| Shortcut | Action |
|---------|--------|
| <kbd>Ctrl</kbd> + <kbd>T</kbd> | New tab |
| <kbd>Ctrl</kbd> + <kbd>W</kbd> | Close tab |
| <kbd>Ctrl</kbd> + <kbd>Tab</kbd> | Next tab |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>Tab</kbd> | Previous tab |
| <kbd>Ctrl</kbd> + <kbd>Enter</kbd> | Open selected folder in new tab |

See [Tabs](../../features/tabs/) for advanced features like tear-off, session restore, and workspaces.

## Split view

Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>E</kbd> to split the window into two independent panes. Use <kbd>F6</kbd> to switch focus between panes. Each pane has its own address bar, navigation history, and view mode.

See [Split View](../../features/split-view/) for details.

## Quick file operations from the keyboard

While browsing, you can do almost everything without touching the mouse:

| Shortcut | Action |
|---------|--------|
| <kbd>Space</kbd> | Quick Look (instant preview window) |
| <kbd>F2</kbd> | Rename selected item |
| <kbd>Delete</kbd> | Move to Recycle Bin |
| <kbd>Ctrl</kbd> + <kbd>C</kbd> / <kbd>X</kbd> / <kbd>V</kbd> | Copy / Cut / Paste |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>N</kbd> | New folder |
| <kbd>Ctrl</kbd> + <kbd>F</kbd> | Search in current folder |
| <kbd>F5</kbd> | Refresh |

## See also

- [Miller Columns](../../features/miller-columns/) — Deep dive into the column view
- [Tabs](../../features/tabs/) — Multi-tab and session restore
- [Keyboard Shortcuts](../../shortcuts/) — Complete shortcut reference
- [Search](../../features/search/) — Filter and recursive search
