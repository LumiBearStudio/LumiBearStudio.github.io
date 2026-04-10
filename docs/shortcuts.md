---
title: Keyboard Shortcuts
layout: default
nav_order: 5
permalink: /docs/shortcuts/
description: "Complete keyboard shortcut reference for SPAN Finder, including Korean keyboard notes."
---

# Keyboard Shortcuts
{: .no_toc }

Complete reference for every default shortcut in SPAN Finder. All shortcuts (except a small set of system-reserved and structural keys) are remappable in **Settings -> Shortcuts**.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## How to remap

Open **Settings -> Shortcuts** (or press `Ctrl+,` and click **Shortcuts** in the sidebar). Click any binding row to capture a new key combination. Conflicts with other commands, system-reserved keys, and bare structural keys are detected and reported in real time.

Your overrides are persisted as a compact JSON patch on top of the built-in defaults, so future updates that add new commands will not wipe out your customizations. Hit **Reset to defaults** at any time to restore the original bindings.

> **Note:** Some shortcuts are owned by Windows itself (`Alt+F4`, `Ctrl+Alt+Delete`, anything with the `Win` key, and so on) and cannot be captured by any desktop application. SPAN will warn you if you try to assign one of them.

[Learn more about remapping](../features/keyboard-customization/){: .btn .btn-outline }

---

## Navigation

| Action | Shortcut | Notes |
|:-------|:---------|:------|
| Go back | `Alt+Left` | Moves to the previous location in history |
| Go forward | `Alt+Right` | |
| Go up one folder | `Alt+Up` | |
| Focus address bar | `Ctrl+L`, `Alt+D`, `F4` | Three defaults, all remappable |
| Search | `Ctrl+F`, `F3` | Opens inline search in the active panel |
| Filter bar | `Ctrl+Shift+F` | Quick filter on visible items |

---

## Edit

| Action | Shortcut | Notes |
|:-------|:---------|:------|
| Copy | `Ctrl+C` | |
| Cut | `Ctrl+X` | |
| Paste | `Ctrl+V` | |
| Paste as shortcut | `Ctrl+Shift+V` | Creates a `.lnk` in the target folder |
| Delete (to Recycle Bin) | `Delete` | |
| Delete (permanent) | `Shift+Delete` | Skips the Recycle Bin |
| Rename | `F2` | |
| Duplicate | `Ctrl+D` | Creates a copy alongside the original |
| New folder | `Ctrl+Shift+N` | |
| Undo | `Ctrl+Z` | File operation undo stack |
| Redo | `Ctrl+Y` | |

---

## Selection

| Action | Shortcut | Notes |
|:-------|:---------|:------|
| Select all | `Ctrl+A` | |
| Select none | `Ctrl+Shift+A` | |
| Invert selection | `Ctrl+I` | |

---

## View

| Action | Shortcut | Notes |
|:-------|:---------|:------|
| Miller columns view | `Ctrl+1` | |
| Details view | `Ctrl+2` | |
| List view | `Ctrl+3` | |
| Icon view | `Ctrl+4` | |
| Toggle split view | `Ctrl+Shift+E` | Second explorer pane |
| Toggle preview pane | `Ctrl+Shift+P` | |
| Equalize columns | `Ctrl+Shift+Plus` | Miller view only |
| Auto-fit columns | `Ctrl+Shift+Minus` | Miller view only |
| Refresh | `F5` | |
| Toggle hidden files | `Ctrl+H` | |
| Toggle file extensions | `Ctrl+Shift+H` | |
| Fullscreen | `F11` | **Not remappable** (handled at OS level) |
| Switch pane | `F6` | Moves focus between split panes |

---

## Tabs

| Action | Shortcut | Notes |
|:-------|:---------|:------|
| New tab | `Ctrl+T` | |
| Close tab | `Ctrl+W` | |
| Next tab | `Ctrl+Tab` | |
| Previous tab | `Ctrl+Shift+Tab` | |
| Open selection in new tab | `Ctrl+Enter` | Opens the focused folder in a new tab |

> **Tip:** Drag a tab out of the tab strip to tear it off into its own window. Drag it back onto another SPAN window's tab strip to re-dock.

---

## Window

| Action | Shortcut | Notes |
|:-------|:---------|:------|
| New window | `Ctrl+N` | |
| Open terminal | `Ctrl+` `` ` `` , `Ctrl+'` | Two defaults — see **Korean keyboard notes** below |
| Open settings | `Ctrl+,` | Settings opens as a dedicated tab |
| Properties | `Alt+Enter` | Shows properties for the focused item |
| Help | `F1`, `Shift+/` | |
| Quick Look | `Space` | Preview the focused file without opening it |

---

## Workspaces

| Action | Shortcut | Notes |
|:-------|:---------|:------|
| Save workspace | `Ctrl+Shift+S` | Saves current tab layout as a workspace |
| Open workspace palette | `Ctrl+Shift+W` | Browse and switch between saved workspaces |

---

## Shelf

The File Shelf is a persistent staging area for files you want to move, copy, or act on later.

| Action | Shortcut | Notes |
|:-------|:---------|:------|
| Add to shelf | `Ctrl+Shift+B` | Adds current selection to the shelf |
| Toggle shelf | `Ctrl+B` | Show or hide the shelf panel |
| Move shelf items here | *(unassigned)* | Remap in Settings if desired |
| Copy shelf items here | *(unassigned)* | Remap in Settings if desired |
| Clear shelf | *(unassigned)* | Remap in Settings if desired |

> Shelf contents persist across sessions when the **Save shelf between sessions** setting is enabled.

---

## Command Palette

> **Hidden in v1.3.1+.** The command palette is retained in the codebase but is not bound to any default key, because it did not fit common file-manager workflows. You can re-enable it by assigning a shortcut in **Settings -> Shortcuts** (the command ID is `span.commandPalette.open`). A common choice is `Ctrl+K`.

---

## Settings toggles

All of the following toggle a single setting instantly. They have no default key bindings, but you can assign any combination in **Settings -> Shortcuts** under the **Settings** category.

| Command | Description |
|:--------|:------------|
| Toggle hidden files | Same as `Ctrl+H` |
| Toggle extensions | Same as `Ctrl+Shift+H` |
| Toggle checkboxes | Show/hide selection checkboxes |
| Toggle thumbnails | Enable/disable image thumbnails |
| Toggle Quick Look | Enable/disable Quick Look preview |
| Toggle WASD navigation | Use WASD keys for arrow-key navigation |
| Toggle confirm delete | Ask before sending to Recycle Bin |
| Toggle preview folder info | Show folder size/count in preview pane |
| Toggle default preview | Enable built-in previewer |
| Toggle favorites tree | Show favorites tree in sidebar |
| Toggle shelf | Enable File Shelf feature |
| Toggle shelf persistence | Save shelf between sessions |
| Toggle context menu integration | Enable Windows "Open with SPAN" |
| Toggle tray icon | Run SPAN in the system tray |
| Toggle remember window position | Restore last window position on launch |
| Toggle Git integration | Show Git status overlays |
| Toggle hex preview | Enable hex preview for unknown files |
| Toggle file hash | Compute file hashes in properties |
| Toggle shell extensions | Load third-party shell extensions |
| Toggle Windows shell extras | Enable additional Windows shell features |
| Toggle Copilot menu | Enable Copilot integration |

---

## Settings jumps

These commands jump directly to a section in the Settings tab. Assign keys in **Settings -> Shortcuts** under **SettingsSection**.

| Command | Jumps to |
|:--------|:---------|
| Open General | General section |
| Open Appearance | Appearance section |
| Open Browsing | Browsing section |
| Open Sidebar | Sidebar section |
| Open Tools | Tools section |
| Open Shortcuts | Shortcuts editor |
| Open Advanced | Advanced section |

---

## Theme, density, language, icon pack

These commands select a specific value and are useful if you want a one-press toggle between, say, light and dark themes. None have default bindings.

**Theme** (category `Theme`): System, Light, Dark
**Density** (category `Density`): Compact, Comfortable, Spacious
**Language** (category `Language`): System, English, Korean, Japanese, Chinese (Simplified), Chinese (Traditional), German, Spanish, French, Portuguese (Brazil)
**Icon pack** (category `IconPack`): Remix, Phosphor, Tabler

**Sidebar sections** (category `Sidebar`): Home, Favorites, Drives, Cloud, Network, Recycle Bin

---

## Korean keyboard notes

Korean (한글) keyboard layouts produce different `VirtualKey` values for a few punctuation keys, which can silently break shortcuts that rely on the US layout. SPAN includes a hardware-level **ScanCode fallback** so these shortcuts work reliably on every layout.

### `Ctrl+` `` ` `` — Open Terminal

On some Korean keyboards the backtick key does not produce `VirtualKey 192`. SPAN detects this using **ScanCode 41** and resolves it to the Open Terminal command anyway.

> **Tip:** If `Ctrl+` `` ` `` still misbehaves (for example because of a non-standard driver), the alternative `Ctrl+'` (single quote, ScanCode 40) is also bound to Open Terminal by default.

### `Ctrl+,` — Open Settings

Similarly, the comma key is resolved via **ScanCode 51** as a fallback, so `Ctrl+,` reliably opens Settings on Korean keyboard layouts.

### `Ctrl+ㅗ`, `Ctrl+ㅎ`, etc. (한/영 mode)

When the IME is in Hangul mode, modifier shortcuts like `Ctrl+C` are normally eaten by the IME because the system delivers a Hangul jamo character instead of the Latin letter. SPAN resolves shortcuts from the underlying `VirtualKey`, so most `Ctrl+` combinations keep working even in Hangul mode. If a specific shortcut fails, **toggle to English mode (Right Alt / 한/영 key)** and try again.

### How the fallback works (under the hood)

```
ResolveCommand(key, ctrl, shift, alt, scanCode):
    1. Try the VirtualKey path:  "Ctrl+`"
    2. If nothing matched and scanCode is in {41, 40, 51}:
         rebuild key string from scanCode  ->  "Ctrl+`" / "Ctrl+'" / "Ctrl+,"
         look up the rebuilt string in the reverse index
    3. Return the resolved command, or null
```

Only three ScanCodes are currently mapped (`41 -> ` `` ` `` , `40 -> '`, `51 -> ,`). If you find another punctuation key that misbehaves on your layout, please [open an issue](https://github.com/LumiBearStudio/SpanFinder/issues) with your keyboard layout name.

---

## System-reserved shortcuts (cannot be assigned)

These shortcuts are owned by Windows and cannot be intercepted by any desktop application, SPAN included:

- `Alt+F4` — Close window
- `Alt+Tab` — Switch app
- `Alt+Space` — Window menu
- `Ctrl+Alt+Delete` — Security screen
- `Ctrl+Shift+Escape` — Task Manager
- `Ctrl+Escape` — Start menu
- `PrintScreen` — Screen capture
- **Any combination with the `Win` key** — Reserved in full for Windows Logo shortcuts

Attempting to bind any of the above in the Shortcuts editor will show a "reserved by the system" error.

---

## Structural keys (cannot be used bare)

These keys drive the internal navigation of SPAN's UI (list focus, dialog close, text editing, etc.) and cannot be assigned as **bare** (no-modifier) shortcuts:

- `Left`, `Right`, `Up`, `Down` — Arrow keys
- `Enter`, `Back`, `Tab`
- `Home`, `End`
- `Escape`

You **can** combine them with modifiers — e.g. `Alt+Enter` (Properties), `Ctrl+Enter` (Open in new tab), `Alt+Left` (Go back), `Ctrl+Tab` (Next tab) are all valid and used by default.

`Space` is treated specially: it is bound to Quick Look by default and may be bound bare, but if you want it for a custom action you should give it a modifier (e.g. `Ctrl+Space`).

---

## See also

- [Keyboard Customization](../features/keyboard-customization/) — Full remapping guide
- [Settings -> Shortcuts](../features/settings/) — UI walkthrough
- [FAQ](../faq/) — Common questions, including reserved shortcuts
