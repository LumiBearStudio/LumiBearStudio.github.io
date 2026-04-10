---
title: Preview Panel
layout: default
parent: Features
nav_order: 8
---

# Preview Panel
{: .no_toc }

Know before you open. The preview panel renders images, video, audio, code, PDFs, fonts, hex dumps, and more — all inline, no external apps required.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

The preview panel is a side panel that automatically shows a rich preview of whichever file you have selected. It supports 10+ file categories covering almost everything you'll actually care about previewing — from JPEG photos to PDF first pages to font glyph samples.

For a larger, modal-style preview that takes over the window, see [Quick Look](../quick-look/).

## Toggling the panel

| Shortcut | Action |
|---|---|
| <kbd>Ctrl</kbd> + <kbd>P</kbd> | Toggle the preview panel |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> | Toggle the preview panel (alternate binding) |

The preview panel is per-pane — if you are using [Split View](../split-view/), each pane has its own preview panel that you can show or hide independently.

## Supported file types

### Images

JPEG, PNG, GIF, BMP, WebP, TIFF, and more. The panel shows the image along with metadata: resolution, file size, last modified date, and creation date.

### Video

MP4, MKV, AVI, MOV, WMV, WEBM, and more. Playback metadata (duration, codec, resolution) is displayed alongside a thumbnail.

Cloud-only MP4 files are supported too — Span Finder uses the Shell thumbnail cache to render them without triggering a download.

### Audio

MP3, AAC, M4A, and more. The preview shows artist, album, track title, and duration pulled from the file's tags.

### Text and code

30+ text extensions are recognized: `.txt`, `.json`, `.xml`, `.csv`, `.md`, and most source-code extensions. Previews render with syntax-aware display.

### PDF

First-page preview for any PDF.

### Markdown

`.md` files render with proper Markdown formatting — headings, lists, code blocks, links. The preview respects your current light/dark theme.

### CSV and TSV

Comma-separated and tab-separated files render as an interactive table (up to 200 rows).

### Fonts

Font files (`.ttf`, `.otf`, `.woff`, etc.) show a glyph sample with metadata.

### Binary and unknown

For unrecognized or binary formats, Span Finder falls back to a **hex dump viewer** that shows the first 512 bytes of the file in hex plus ASCII. You can turn the hex viewer off in Settings if you never want it.

### Folders

Selecting a folder shows its size, item count, and creation date. Folder sizes are computed in the background with caching so that repeat hits are instant.

## How it works

- **200 ms debounce** — Rapidly changing your selection (e.g. arrow-key scrolling through a long list) waits 200 ms before actually rendering, so Span Finder never wastes work previewing files you immediately scroll past.
- **Cloud-safe** — For cloud-only files (OneDrive, iCloud, Dropbox), the panel uses the Shell thumbnail cache and never triggers a download.
- **Remote files** — Previews work on files served over FTP, FTPS, and SFTP connections too.
- **Thumbnail limit** — Files larger than 20 MB skip local thumbnail decoding and fall back to Shell Thumbnail API caching.

## Metadata shown

For most file types the preview panel displays:

- File name
- Full path
- Size (human-readable)
- Last modified date
- Creation date
- Type (e.g. "JPEG image", "MP4 video")
- Format-specific metadata (resolution for images, duration for audio/video, etc.)

## Settings

Preview-related settings live under Tools & Integration in Settings (<kbd>Ctrl</kbd> + <kbd>,</kbd>):

- **Show thumbnails** — Master on/off for thumbnails and previews
- **Show hex preview** — Toggle the binary hex-dump fallback
- **Quick Look on Space** — Enable <kbd>Space</kbd> for the modal [Quick Look](../quick-look/)

## Tips & gotchas

> **Tip:** Hide the preview panel with <kbd>Ctrl</kbd> + <kbd>P</kbd> when you are doing repetitive file operations — you get more room for file lists and Span Finder skips the preview rendering work entirely.

> **Tip:** For a bigger preview or to browse through files with arrow keys while previewing, use [Quick Look](../quick-look/) instead.

> **Tip:** Cloud-only videos (files not yet downloaded from OneDrive/iCloud/Dropbox) still show a thumbnail. Span Finder uses the already-cached Shell thumbnail — it never forces a cloud download.

> **Gotcha:** Very large files (>20 MB) skip the direct-decode thumbnail path and rely on the Shell thumbnail cache. If Windows hasn't cached a thumbnail yet, you may see a generic icon until it does.

> **Gotcha:** Some PDF producers create files with missing first-page resources. Span Finder falls back to a generic PDF icon when that happens.

## See also

- [Quick Look](../quick-look/) — The full-screen modal preview
- [Miller Columns](../miller-columns/) — The main place you'll select files to preview
- [Split View](../split-view/) — Each pane has its own preview panel
- [Keyboard Shortcuts](../../shortcuts/)
