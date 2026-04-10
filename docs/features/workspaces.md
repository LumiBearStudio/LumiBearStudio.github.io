---
title: Workspaces
layout: default
parent: Features
nav_order: 5
---

# Workspaces
{: .no_toc }

Save your current tab layout — paths, view modes, split states, everything — as a named workspace and restore it in one click.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

A **workspace** is a saved snapshot of a Span Finder window's tab layout. Every tab, every path, every view mode, and every split-view configuration is captured so you can restore the exact same setup on demand. Think of it as project templates for file browsing.

Workspaces let you instantly jump between contexts like:

- **"Client A"** — five tabs pointing at that client's folders, in Details view
- **"Photo editing"** — one split tab with RAW input left, JPEG output right, both in Icons view
- **"Research"** — reference materials, draft documents, and the download folder, ready to go
- **"Screenshots"** — your screenshot folder split with the destination you upload to

Instead of opening and navigating tabs every morning, you open a workspace.

## When to use it

Use workspaces whenever you repeatedly open the same combination of folders. If you find yourself navigating to the same three folders every time you start a project, that's a workspace waiting to be saved.

## Saving a workspace

| Shortcut | Action |
|---|---|
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd> | Save the current tab layout as a new workspace |

You can also right-click a tab and choose **Save tab layout...** from the context menu. Span Finder prompts for a name and then adds it to your workspace list.

Everything about your current window is captured:

- The set of open tabs and their paths
- Each tab's view mode (Miller / Details / List / Icons)
- Each tab's icon size (for Icons view)
- Split View state per tab (on/off, which folders, pane view modes)
- The active tab

## Restoring a workspace

| Shortcut | Action |
|---|---|
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>W</kbd> | Open the workspace palette |

The palette lists every saved workspace. Click one, press <kbd>Enter</kbd>, and Span Finder opens every tab it contains in the current window.

You can also restore a workspace from the sidebar workspace button without opening the palette — it shows your saved workspaces as a quick-access list.

## Managing workspaces

From the workspace palette you can:

- **Restore** — Open every tab the workspace contains
- **Rename** — Change the workspace name (paths stay the same)
- **Delete** — Remove the workspace permanently

Workspaces are stored locally — they are not synced to the cloud.

## Use cases

### Working across multiple clients

Save one workspace per client: `client-acme`, `client-bravo`, `client-charlie`. Each workspace opens the folders you need for that account — contracts, assets, invoices, deliverables.

### Research and writing

A `research` workspace with source materials, a `draft` workspace with your work-in-progress, and a `published` workspace with final output. Jump between them without losing your place.

### Screenshot and video workflows

A `screenshots` workspace that splits your screenshot capture folder with the destination you upload to. Drag, drop, done.

### Development contexts

A `frontend` workspace with your UI source, asset folder, and package lock file side by side. A `backend` workspace with the API project, migrations folder, and log directory. Switch contexts in one shortcut.

## Tips & gotchas

> **Tip:** Workspaces capture the current window only, not every window you have open. If you run multi-window setups, save a workspace per window.

> **Tip:** Restoring a workspace does not close existing tabs — the restored tabs are added to your current window. Close them first if you want a clean slate.

> **Tip:** Combine workspaces with [Split View](../split-view/) to save entire dual-pane layouts for repeat tasks.

> **Gotcha:** If a folder inside a workspace no longer exists when you restore it (for example, a USB drive is unplugged), that tab is skipped silently. The rest of the workspace still opens.

## See also

- [Tabs](../tabs/) — The underlying concept workspaces snapshot
- [Split View](../split-view/) — Saved per tab inside a workspace
- [Miller Columns](../miller-columns/) — View mode is captured per tab
- [Keyboard Shortcuts](../../shortcuts/)
