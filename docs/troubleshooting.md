---
title: Troubleshooting
layout: default
nav_order: 7
permalink: /docs/troubleshooting/
---

# Troubleshooting
{: .no_toc }

Something not working right? Start here.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Installation issues

### SPAN Finder won't install from the Microsoft Store

- Make sure you are running **Windows 10 version 1809 or later** (Settings → System → About → OS Build).
- Confirm that your Microsoft Store is signed in and up to date.
- Try restarting the Microsoft Store app, then retry the install.

### Manual install: "This app package is not trusted"

When installing a `.msix` from GitHub Releases you need to trust the signing certificate first:

1. Right-click the `.msix` file → **Properties** → **Digital Signatures** tab
2. Select the certificate → **Details** → **View Certificate** → **Install Certificate**
3. Choose **Local Machine** → **Place all certificates in the following store** → **Trusted People**
4. Install, then retry the `.msix` install.

---

## Startup issues

### SPAN Finder crashes immediately on launch

1. Open **Event Viewer** (Win + R → `eventvwr`) and check **Windows Logs → Application** for an entry from `SpanFinder`.
2. If you see a `COMException` or `UnauthorizedAccessException`, try:
   - Reinstalling the app from the Microsoft Store
   - Clearing the local state: navigate to `%LOCALAPPDATA%\Packages\` and delete the `LumiBearStudio.SpanFinder_*` folder (this resets all settings)

### Blank white window on startup

This usually happens when the WinUI runtime is outdated.

1. Open **Microsoft Store** → search for **"Windows App Runtime"** → update if available.
2. Restart SPAN Finder.

---

## Navigation issues

### Folders load slowly or show a spinner for a long time

- Network drives and OneDrive-only folders can be slow. SPAN Finder always loads asynchronously so the UI stays responsive, but it can't speed up the underlying storage.
- For very large folders (10,000+ files), try switching to **Details view** (<kbd>Ctrl</kbd> + <kbd>2</kbd>) which renders rows progressively.
- Check if your antivirus is scanning every file SPAN accesses. Add `%LOCALAPPDATA%\Packages\LumiBearStudio.SpanFinder_*` to your AV exclusion list.

### Clicking a folder in Miller Columns doesn't open the next column

- Make sure you are in **Miller Columns mode** (<kbd>Ctrl</kbd> + <kbd>1</kbd>). Details/List/Icon modes use double-click to navigate.
- Check **Settings → Browsing → Click behavior** — it may be set to double-click.
- If the folder is a system folder (Control Panel, This PC), SPAN Finder may show an empty column — this is expected, as these virtual folders don't expose their contents the same way.

### Address bar shows wrong path after switching tabs

This is the expected behavior: the address bar always reflects the **focused tab's** current path. If the tab focus changes (e.g. due to a new window opening in the background), the bar updates to match.

---

## File operation issues

### Copy or move operation fails with "Access denied"

- You need write permission on the destination folder. Try running SPAN Finder as Administrator (right-click the app → Run as administrator) to confirm this is the cause.
- System folders (`C:\Windows`, `C:\Program Files`) require elevation. SPAN Finder does not auto-elevate — use an elevated File Explorer or terminal for those locations.

### Undo (Ctrl+Z) doesn't restore a deleted file

- Only **Recycle Bin deletes** (<kbd>Delete</kbd>) are undoable. **Permanent deletes** (<kbd>Shift</kbd> + <kbd>Delete</kbd>) bypass the Recycle Bin entirely and cannot be recovered by SPAN Finder.
- Check the Recycle Bin tab — the file may still be there even if Undo didn't work.

### Batch rename changed the wrong files

- The batch rename dialog shows a live preview with old → new name mappings before you apply. Always verify the preview before clicking **Rename**.
- Use <kbd>Ctrl</kbd> + <kbd>Z</kbd> immediately after to undo the entire batch rename in one step.

---

## Preview issues

### Preview panel shows a generic icon instead of a preview

- The file may be **cloud-only** (not yet downloaded from OneDrive/iCloud/Dropbox). SPAN Finder uses the Shell thumbnail cache for cloud files — if Windows hasn't cached a thumbnail yet, you'll see a generic icon.
- For very large files (>20 MB for images, >100 MB for text), SPAN Finder skips direct decoding. The Shell thumbnail cache is used as a fallback.
- Try pressing <kbd>F5</kbd> to refresh the folder — this clears SPAN's thumbnail cache for the current folder.

### Quick Look (Space) opens but shows nothing

- Confirm that **Quick Look** is enabled: **Settings → Preview → Enable Quick Look**.
- Quick Look supports the same file types as the Preview Panel. For unsupported types, it shows the hex dump view (if enabled).

### Video preview doesn't play

- Make sure the required codec is installed. SPAN Finder uses the Windows Media Foundation pipeline — install the appropriate codec pack (e.g. **HEVC Video Extensions** from the Microsoft Store for H.265 content).

---

## Shelf issues

### Items I added to the Shelf are gone after restart

- Check that **Settings → Shelf → Save shelf on exit** is enabled (it is by default).
- The Shelf state is saved to `%LOCALAPPDATA%\Packages\LumiBearStudio.SpanFinder_<hash>\LocalState\shelf.json`. If this file was deleted or corrupted, the Shelf starts empty.

### The Shelf panel doesn't appear when I hover the right edge

- Make sure the Shelf is enabled: **Settings → Shelf → Enable Shelf** (<kbd>Ctrl</kbd> + <kbd>B</kbd> to toggle).
- The Shelf appears on the **right edge of the main window**. If SPAN Finder is maximized on a multi-monitor setup, make sure you are hovering the right edge of the correct monitor.

---

## Remote connection issues

### SFTP connection fails with "Host key verification failed"

- This happens when the server's host key has changed since you last connected (e.g., after a server rebuild).
- Right-click the connection in the sidebar → **Edit** → **Clear saved host key** → reconnect and re-accept the new fingerprint.

### FTP connection times out

- Some servers require **Passive Mode**. Edit the connection and toggle **Passive mode**.
- Check your firewall — FTP passive mode uses ephemeral high ports that some firewalls block.

### Remote files show as empty or 0 bytes

- This can happen with FTPS servers that use implicit TLS and have strict cipher requirements. Try switching to **Explicit FTPS** or **SFTP** if your server supports it.

---

## Git integration issues

### No Git badges appear in my repo folder

- Confirm that `git.exe` is in your PATH: open a terminal and run `git --version`.
- Check that Git integration is enabled: **Settings → Advanced → Git integration**.
- Very large repos (`.git/index` > 5 MB) skip per-file status badges — only the branch name is shown.

### Wrong branch name shown in the status bar

- The status bar refreshes every 30 seconds. Navigate away and back to force a refresh, or press <kbd>F5</kbd>.

---

## Display and UI issues

### Text or icons look blurry on high-DPI displays

- Go to **Settings → Appearance → Font scale** and adjust the slider.
- Make sure Windows' display scaling is set correctly (Settings → System → Display → Scale).
- If running on a multi-monitor setup with mixed DPI, move the SPAN window to the target monitor and restart it.

### Themes don't apply after changing

- Themes apply immediately — if you don't see a change, try scrolling or clicking to force a redraw.
- On Windows 10, Mica blur effects are not available. The theme colors still apply but the background will be solid.

---

## Performance issues

### SPAN Finder is using too much memory

- Many open tabs with large folders each consume memory. Close unused tabs (<kbd>Ctrl</kbd> + <kbd>W</kbd>).
- Disable thumbnail loading for large icon folders: **Settings → Browsing → Show thumbnails**.
- Check the Action Log for runaway operations: press <kbd>F3</kbd> or open the Action Log tab.

### UI freezes momentarily when navigating large folders

- This is usually caused by antivirus scanning. Add SPAN Finder to your AV exclusion list.
- Try **Details view** (<kbd>Ctrl</kbd> + <kbd>2</kbd>) for folders with 10,000+ items — it renders progressively and handles large lists more efficiently than Miller Columns.

---

## Still stuck?

- [Search existing issues](https://github.com/LumiBearStudio/SpanFinder/issues) — your problem may already be reported.
- [Open a new issue](https://github.com/LumiBearStudio/SpanFinder/issues/new) — include your Windows version, SPAN version (Settings → About), and exact steps to reproduce.
- [Start a discussion](https://github.com/LumiBearStudio/SpanFinder/discussions) — for questions, ideas, or general help.
