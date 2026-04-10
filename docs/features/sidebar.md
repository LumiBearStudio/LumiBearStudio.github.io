---
title: Sidebar
layout: default
parent: Features
nav_order: 11
---

# Sidebar
{: .no_toc }

The left panel that collects your drives, favorites, cloud accounts, network shares, and remote connections into one always-visible hub.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

Span Finder's sidebar is a categorized navigation panel that sits on the left of every window. It gives you one-click access to everything you care about — your drives, your favorites, your cloud accounts, your network, your recycle bin, and your saved remote connections. You can hide individual sections you don't use, reorder your favorites by dragging, and pin new folders with a right-click.

## Sections

### Home

A virtual "starting point" tab with quick-access tiles for recent folders, favorites, and drives. Selecting Home in the sidebar opens the Home view in the current tab.

### Favorites

Your own curated list of pinned folders.

- **Add to Favorites** — Drag a folder onto the sidebar, or right-click a folder and choose **Pin to Favorites**
- **Reorder** — Drag favorites up and down within the section
- **Unpin** — Right-click a favorite and choose **Unpin** (or drag it off the sidebar)
- **Rename** — Right-click → Rename (display name only — the underlying folder is untouched)
- **Open in new tab** — Middle-click

### Recent folders

Up to 20 most recently visited folders, saved automatically. This list is also synced with the Windows Quick Access area.

### Local drives

Every local drive Span Finder can see — HDD, SSD, USB. USB hot-plug is detected live via `WM_DEVICECHANGE`, so plugging in a thumb drive adds it to the sidebar immediately (and unplugging removes it just as fast).

Right-click any drive for drive-specific actions including **Format** and **Disk Cleanup**.

### Cloud storage

Span Finder auto-detects the major cloud providers:

- **OneDrive**
- **iCloud Drive**
- **Dropbox**
- **Google Drive**

Detection uses a combination of the Windows `SyncRootManager` registry, the Navigation Pane CLSID entries, and provider-specific folder detection — so it catches providers that only register one of the three mechanisms.

Cloud files also show sync-status badges (Cloud-only, Synced, Pending upload, Syncing) in their folder views — see [File Operations](../file-operations/) for more.

### Network

Browse SMB shares and mapped network drives:

- **Network enumeration** — Via `WNetEnumResourceW` P/Invoke
- **Share listing** — Via `NetShareEnum`
- **Admin shares filtered** — Hidden shares ending in `$` are skipped automatically
- **5-second timeout per operation** — Slow networks don't freeze the sidebar

### Remote connections

Saved FTP, FTPS, and SFTP connections:

- **FTP / FTPS** — Powered by the FluentFTP library; directory browse, upload, and download all work
- **SFTP** — Supports both SSH key authentication and password authentication
- **Credential storage** — Connections are encrypted at rest

Connections are managed through a dedicated connection manager UI where you can add, edit, and remove entries.

### Recycle Bin

A dedicated Recycle Bin entry that opens the bin as a full tab. You can browse deleted items with any view mode, restore them, permanently delete individual entries, or empty the entire bin with a toolbar button.

Double-click the Recycle Bin item in the sidebar (and in address bar auto-complete) to open it — Span Finder recognizes both `shell:RecycleBinFolder` and the well-known CLSID.

### Workspaces

If you use [Workspaces](../workspaces/), the sidebar shows a workspaces button that lists every saved workspace for one-click restoration.

## Showing and hiding sections

Every sidebar section can be turned off independently under Settings → **Window & Session**. If you never use FTP, hide the Remote Connections section. If your machine has no cloud accounts, hide Cloud Storage.

Settings for sidebar visibility persist across sessions.

## Middle-click to open in new tab

Middle-click any sidebar item — favorite, drive, cloud root, network share, or recent folder — to open it in a new tab without losing your current view.

## Drag and drop

- **Drop files onto Favorites** — Pins a new favorite
- **Drop files onto a drive or folder** — Copies or moves (standard drag-drop rules apply: <kbd>Ctrl</kbd> = copy, <kbd>Shift</kbd> = move)

## Tips & gotchas

> **Tip:** The sidebar is the fastest way to jump between cloud providers. Pin the specific OneDrive subfolders you work in most instead of scrolling through OneDrive every time.

> **Tip:** Middle-click is your friend — it opens items in background tabs without disturbing your current work.

> **Tip:** If you never use a section (say, you don't have cloud accounts), hide it in Settings for a cleaner sidebar.

> **Gotcha:** Network enumeration has a 5-second timeout per operation. On slow networks, shares may not all show up immediately — they'll appear as the background scan completes.

> **Gotcha:** USB drives appearing and disappearing with hot-plug is driven by Windows messages. If you see a stale entry, press <kbd>F5</kbd> in any folder view to force a refresh.

## See also

- [Tabs](../tabs/) — Middle-click sidebar items to open in background tabs
- [Workspaces](../workspaces/) — Restore saved layouts from the sidebar
- [File Operations](../file-operations/) — Drag files onto the sidebar to pin or copy
- [Keyboard Shortcuts](../../shortcuts/)
