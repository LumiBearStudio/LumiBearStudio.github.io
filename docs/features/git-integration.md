---
title: Git Integration
layout: default
parent: Features
nav_order: 11
---

# Git Integration
{: .no_toc }

Branch name, file status, and recent commits — surfaced right in the file manager without opening a terminal.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

When you navigate to a folder that is inside a Git repository, SPAN Finder automatically detects it and displays:

- The **current branch name** in the status bar
- **File status badges** next to each file in the folder list
- **Recent commit info** in the preview panel

Everything runs asynchronously in the background — navigating a large repo never blocks the UI.

## Requirements

SPAN Finder needs `git.exe` to be available on your system. It checks:

1. The `PATH` environment variable
2. Common install paths (`C:\Program Files\Git\bin\git.exe`, etc.)

If Git is not found, the integration is silently skipped. You can verify your Git installation by opening a terminal and running `git --version`.

## File status badges

Each file and folder in the list view gets a colored badge showing its Git status:

| Badge | Status | Meaning |
|-------|--------|---------|
| **M** | Modified | Tracked file with unstaged or staged changes |
| **A** | Added | New file staged for the next commit |
| **D** | Deleted | File deleted but not yet committed |
| **?** | Untracked | File not tracked by Git |
| **R** | Renamed | File renamed (staged) |
| **C** | Copied | File copied (staged) |

Badges appear in all view modes: Miller Columns, Details, List, and Icons.

## Status bar

When inside a repo, the status bar at the bottom of the pane shows:

```
 main  ↑2 changes
```

- **Branch name** — the currently checked-out branch
- **Change count** — number of modified or staged files

## Preview panel — commit info

Select any file inside a repo and the [Preview Panel](../preview/) shows an extra **Git** section with:

- Last commit hash (short)
- Last commit message
- Author name
- Commit date
- How long ago (e.g. "3 days ago")

## Repository detection

SPAN Finder searches upward from the current folder for a `.git` directory, up to **15 parent levels**. This means it works correctly even if you navigate deep into a subdirectory — it will still find the repo root and show the correct branch.

**Caching tiers:**
- Repo root path is cached permanently per session (no repeated disk walks)
- Branch and status info refreshes every **30 seconds**
- File status is refreshed on every folder navigation

## Settings

Git integration can be toggled in **Settings → Advanced → Git integration**.

When disabled, no `git.exe` processes are launched at all — useful on machines where `git` is in PATH but the Git integration creates unwanted overhead for non-development work.

## Performance notes

SPAN Finder uses several safeguards to keep Git queries from affecting navigation speed:

- All Git commands run on a background thread
- Commands time out after **8 seconds**
- `stdout` is capped at **128 KB** to prevent runaway output from very large repos
- Repos with a `.git/index` larger than **5 MB** skip the per-file status step (only branch info is shown)

## Tips & gotchas

> **Tip:** If you work with multiple repos simultaneously, use [Split View](../split-view/) — each pane tracks its own repo root independently.

> **Tip:** Git badges work inside [Archive](../file-operations/#compress-and-extract) views too, as long as the archive path resolves to a tracked location.

> **Gotcha:** Submodules are detected as separate repos. Navigating into a submodule folder switches the branch display to the submodule's HEAD.

> **Gotcha:** Bare repositories (no working tree) are not supported — SPAN Finder looks for a `.git` directory containing a `config` file.

## See also

- [Preview Panel](../preview/) — Where commit metadata appears
- [Sidebar](../sidebar/) — Remote connections for Git hosts over SFTP
- [Keyboard Shortcuts](../../shortcuts/)
