---
title: Remote Connections
layout: default
parent: Features
nav_order: 12
---

# Remote Connections
{: .no_toc }

Browse FTP, FTPS, and SFTP servers as if they were local folders — with saved credentials, drag-and-drop uploads, and full preview support.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Supported protocols

| Protocol | Default Port | Notes |
|----------|-------------|-------|
| **FTP** | 21 | Standard file transfer, no encryption |
| **FTPS** | 990 (implicit) / 21 (explicit) | FTP over TLS — recommended over plain FTP |
| **SFTP** | 22 | SSH-based transfer — most secure, supports key auth |

> **Recommendation:** Use SFTP where possible. FTPS is a good fallback for hosts that don't support SSH.

## Adding a connection

1. Click the **Remote** section in the sidebar (or right-click it and choose **Add connection**)
2. Fill in the connection form:

| Field | Description |
|-------|-------------|
| **Name** | Display name shown in the sidebar |
| **Protocol** | FTP, FTPS, or SFTP |
| **Host** | Hostname or IP address |
| **Port** | Leave blank for the default port |
| **Username** | Your login username |
| **Password** | Your password (stored encrypted) |
| **SSH Key** (SFTP only) | Path to your private key file (`.pem`, `.ppk`, `.key`) |
| **Passphrase** (SFTP only) | If your key is passphrase-protected |

3. Click **Connect** to test and save.

You can also type a URL directly in the address bar:

```
ftp://user@ftp.example.com/public/
ftps://user@ftp.example.com:990/
sftp://user@ssh.example.com/home/user/
```

SPAN Finder will prompt for credentials if they are not yet saved.

## SSH key authentication (SFTP)

SFTP connections support public-key authentication:

- **Supported key types:** RSA, DSA, ECDSA, Ed25519
- **Supported formats:** OpenSSH, PuTTY (`.ppk`)
- **Passphrase support:** Yes — the passphrase is stored encrypted alongside the key path

To use a key:
1. Add a new SFTP connection
2. Leave **Password** blank
3. Set **SSH Key** to the path of your private key file

### Host key verification (TOFU)

On first connection to a new host, SPAN Finder shows the server's host key fingerprint and asks you to confirm it. This is the "Trust On First Use" model — once accepted, the fingerprint is saved and verified on every subsequent connection.

If the fingerprint changes (e.g., the server was rebuilt), SPAN Finder will warn you before proceeding.

## Browsing remote folders

Once connected, remote folders behave like local ones:

- Navigate with Miller Columns, Details, List, or Icon view
- Preview files inline (images, text, video thumbnails via shell cache)
- Use the address bar to jump to any path on the server
- Middle-click a remote folder to open it in a new tab

**Supported operations on remote files:**

| Operation | Supported |
|-----------|-----------|
| Browse folders | ✅ |
| Preview files | ✅ (text, images — binary streamed) |
| Download (drag to local folder) | ✅ |
| Upload (drag from local to remote) | ✅ |
| Delete | ✅ |
| Rename | ✅ |
| Create folder | ✅ |
| Move within same server | ✅ |
| Copy between two remote servers | ❌ (download + re-upload) |

## Managing saved connections

Right-click any connection in the sidebar to:

- **Connect / Disconnect**
- **Edit** — update host, credentials, or key
- **Rename** — change the display name
- **Delete** — remove saved credentials permanently

Credentials are stored encrypted in `%LOCALAPPDATA%\Packages\LumiBearStudio.SpanFinder_<hash>\LocalState\connections.json`.

## Connection behavior

- **Auto-reconnect:** If a connection drops mid-operation (e.g., idle timeout), SPAN Finder detects the stale socket and reconnects automatically before retrying.
- **Timeout:** Commands time out after **8 seconds**. If the server is unreachable, a clear error is shown.
- **Session persistence:** Connections you had open when you quit SPAN Finder are restored on the next launch (if the server is reachable).

## Tips & gotchas

> **Tip:** Use [Split View](../split-view/) with one pane on a local folder and one on a remote — drag files between them to upload or download.

> **Tip:** Remote connections appear in the sidebar's **Remote** section. Pin frequently used servers to **Favorites** for one-click access.

> **Tip:** The [Preview Panel](../preview/) works on remote text files — SPAN Finder streams just enough bytes to render the preview without downloading the full file.

> **Gotcha:** Very large files (>1 GB) on slow connections may stall the progress dialog. Pause/resume is available on SFTP transfers; FTP transfers must be restarted.

> **Gotcha:** Some SFTP servers restrict the allowed commands (e.g., no `rename` or `mkdir`). SPAN Finder will report the server's error message in the Action Log.

> **Gotcha:** FTP (not FTPS) sends credentials in plaintext. Only use it on private networks or when FTPS/SFTP is unavailable.

## See also

- [Sidebar](../sidebar/) — Where remote connections live
- [Split View](../split-view/) — Ideal for local ↔ remote drag-and-drop
- [File Operations](../file-operations/) — Copy, move, and undo on remote files
