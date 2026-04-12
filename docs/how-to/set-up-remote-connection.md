---
title: Set up an SFTP remote connection
layout: default
parent: How-To Recipes
nav_order: 5
---

# Set up an SFTP remote connection

Connect to a remote server via SFTP and browse it like a local folder — with drag-and-drop uploads and live preview.

**Time:** ~5 minutes  
**Skill level:** Intermediate

---

## Before you start

You'll need:
- Hostname or IP address of the server
- Your SSH username
- Either a password **or** an SSH private key (`.pem`, `.ppk`, or OpenSSH format)
- Port number (default: 22)

---

## Step-by-step: password authentication

### 1. Add the connection

In the sidebar, find the **Remote** section. Right-click it and choose **Add connection**, or click the **+** icon next to the section header.

### 2. Fill in the connection details

| Field | Value |
|-------|-------|
| Name | A friendly label (e.g. `My VPS`) |
| Protocol | **SFTP** |
| Host | `192.168.1.10` or `myserver.example.com` |
| Port | `22` (leave blank for default) |
| Username | `ubuntu`, `admin`, etc. |
| Password | Your SSH password |

### 3. Connect

Click **Connect**. On first connection, SPAN Finder shows the server's host key fingerprint. Verify it matches what your hosting provider shows (usually in their control panel), then click **Trust and connect**.

### 4. Browse the server

The server now appears in the sidebar under **Remote**. Click it to browse. Navigation, preview, and file operations all work the same as with local folders.

---

## Step-by-step: SSH key authentication

SSH key auth is more secure than passwords and avoids storing your password on disk.

### 1. Add the connection (same as above)

Fill in Name, Protocol, Host, Port, and Username.

### 2. Set the SSH key

Leave **Password** blank. Click **Browse** next to **SSH Key** and select your private key file.

If your key is passphrase-protected, enter the passphrase in the **Passphrase** field. SPAN Finder stores it encrypted.

### 3. Connect and verify the host key

Same as password auth — verify the fingerprint on first connection.

---

## Uploading files

**Drag from a local folder to the remote:**

1. Open the remote folder in one pane (or tab)
2. Navigate to the local source in another tab or use [Split View](../../features/split-view/)
3. Drag files from the local pane to the remote pane

SPAN Finder streams the upload and shows a progress dialog. Large files can be paused or cancelled.

**Drag from the Shelf:**

Add local files to the [Shelf](../../features/shelf/), navigate to the remote destination, then click **Copy here**.

---

## Downloading files

Drag files from the remote folder to a local folder, or use <kbd>Ctrl</kbd> + <kbd>C</kbd> / <kbd>Ctrl</kbd> + <kbd>V</kbd> across panes.

---

## Typing a URL directly

You can also connect without saving by typing a URL in the address bar:

```
sftp://username@myserver.example.com/home/username/
sftp://username@192.168.1.10:22/var/www/
```

SPAN Finder will prompt for credentials if they are not saved.

---

## Managing saved connections

Right-click any saved connection in the sidebar:

- **Edit** — update host, port, credentials, or key
- **Rename** — change the display label
- **Delete** — remove the connection and wipe stored credentials

---

## Tips

- **Use Split View** (<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>E</kbd>) — local folder on the left, remote on the right. Drag between them to upload or download without switching tabs.
- **Preview works remotely** — text files, images, and code files preview inline over SFTP without downloading the whole file.
- **Auto-reconnect** — if the server disconnects you due to idle timeout, SPAN Finder reconnects automatically when you perform the next action.
- **Multiple servers** — save as many connections as you need. Each appears as a separate entry in the sidebar.

---

## See also

- [Remote Connections](../../features/remote-connections/) — Full protocol reference
- [Sidebar](../../features/sidebar/) — Where connections are managed
- [Split View](../../features/split-view/) — Ideal for local ↔ remote workflows
- [File Shelf](../../features/shelf/) — Batch upload with the Shelf
