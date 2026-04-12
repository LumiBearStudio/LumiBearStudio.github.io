---
title: Set up and use Workspaces
layout: default
parent: How-To Recipes
nav_order: 2
---

# Set up and use Workspaces

Workspaces let you save and instantly restore named tab layouts — perfect for switching between project contexts without manually reopening folders every time.

**Time:** ~3 minutes  
**Skill level:** Beginner

---

## The scenario

You work on multiple projects throughout the day. Each project needs its own set of tabs: source code folder, assets, docs, and maybe a remote server. Instead of navigating from scratch every time you switch context, save each layout as a named Workspace and restore it in one keystroke.

---

## Step-by-step

### 1. Open the tabs you need for a project

Press <kbd>Ctrl</kbd> + <kbd>T</kbd> to open new tabs and navigate each one to the folder you want. Arrange them in whatever order makes sense:

- Tab 1: Source code root
- Tab 2: Build output / dist
- Tab 3: Assets folder
- Tab 4: Remote SFTP connection

Set the view mode (<kbd>Ctrl</kbd> + <kbd>1</kbd> through <kbd>4</kbd>) for each tab as needed — Workspaces remember each tab's view mode independently.

### 2. Save the Workspace

Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd> (or go to **Settings → Workspaces → Save current layout**).

Type a descriptive name, e.g. `Project Alpha`. Click **Save**.

### 3. Restore the Workspace later

Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>W</kbd> to open the Workspace picker. Select `Project Alpha` and press <kbd>Enter</kbd>.

SPAN Finder replaces the current tab layout with the saved one — all tabs, paths, and view modes exactly as you left them.

**Tip:** Workspaces also appear in the sidebar under the **Workspaces** section. Click any workspace there to restore it instantly.

### 4. Create multiple Workspaces

Repeat for each project or context. There's no limit to how many you can save.

Suggested workspace names:
- `Work — Project Alpha`
- `Work — Project Beta`
- `Personal`
- `Downloads cleanup`

### 5. Manage Workspaces

Go to **Settings → Workspaces** to:
- **Rename** a workspace
- **Delete** a workspace
- **Restore** a workspace from the list

---

## Tips

- **Auto-save on exit** — SPAN Finder saves an `_autosave` workspace whenever you quit. If you close the app accidentally, this lets you recover your last session even if you hadn't explicitly saved a workspace.
- **Startup behavior** — In **Settings → General → On startup**, choose to restore the last session automatically, open a blank tab, or open a specific workspace.
- **Multiple windows** — Each window can have its own active workspace. Open a second window with <kbd>Ctrl</kbd> + <kbd>N</kbd> and restore a different workspace in it.
- **Workspaces save split view** — If you have [Split View](../../features/split-view/) enabled in a tab, the workspace remembers both pane paths.

---

## See also

- [Workspaces](../../features/workspaces/) — Full Workspaces reference
- [Tabs](../../features/tabs/) — Multi-tab and session restore
- [Split View](../../features/split-view/) — Dual-pane layouts
