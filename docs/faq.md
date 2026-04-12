---
title: FAQ
layout: default
nav_order: 6
permalink: /docs/faq/
---

# Frequently Asked Questions
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Is SPAN Finder free?

Yes. SPAN Finder is free and open source under the MIT License. If you'd like to support development, you can [sponsor on GitHub](https://github.com/sponsors/LumiBearStudio) or use the in-app **Coffee / Hamburger / Steak** support tiers via Microsoft Store.

## Does SPAN Finder collect telemetry?

No. SPAN Finder does not collect, transmit, or store any usage data. Sentry is used for **crash reports only** — all file paths are scrubbed before sending, and you can opt out entirely in **Settings → Advanced → Crash reporting**. See our [Privacy Policy](https://github.com/LumiBearStudio/SpanFinder/blob/main/PRIVACY.md).

## Can I replace the default Windows file explorer with SPAN?

Partially. SPAN Finder can register itself as the default handler for folder navigation. Go to **Settings → Advanced → Set as default file manager**.

> **Note:** Some apps (like Chrome's "Show in folder") hard-code calls to `explorer.exe` and cannot be redirected. This is a Windows API limitation, not a SPAN bug.

## What languages does SPAN Finder support?

9 languages: English, 한국어, 日本語, 中文 (简体/繁體), Deutsch, Español, Français, Português (Brasil).

Change the language in **Settings → Appearance → Language**.

## Where are my settings stored?

In `%LOCALAPPDATA%\Packages\LumiBearStudio.SpanFinder_<hash>\LocalState\`.

Settings, workspaces, shelf state, and keyboard shortcuts are all stored as JSON files in that directory. You can back them up or copy them to a new machine.

## How do I reset SPAN Finder to default settings?

Delete the contents of `%LOCALAPPDATA%\Packages\LumiBearStudio.SpanFinder_<hash>\LocalState\` and restart the app. This resets all settings, workspaces, and saved connections.

## Does SPAN Finder work on Windows 10?

Yes, from **Windows 10 version 1809** (October 2018 Update) onward. Some visual effects like Mica background blur are Windows 11-only but all core features work on Windows 10.

## Does SPAN Finder support ARM64?

Yes. Both x64 and ARM64 builds are available on the Microsoft Store and GitHub Releases.

## Can I use SPAN Finder without installing it from the Store?

Yes. Download the `.msix` package from [GitHub Releases](https://github.com/LumiBearStudio/SpanFinder/releases). You'll need to trust the signing certificate first — see [Troubleshooting](../troubleshooting/#manual-install-this-app-package-is-not-trusted) for instructions.

## How do I report a bug?

[Open a GitHub issue](https://github.com/LumiBearStudio/SpanFinder/issues/new). Include your Windows version, SPAN version (Settings → About), and steps to reproduce. The more detail, the faster we can fix it.

## How do I request a feature?

[Start a GitHub discussion](https://github.com/LumiBearStudio/SpanFinder/discussions/new?category=ideas) in the Ideas category.

## Does SPAN Finder support network drives?

Yes. Network shares (UNC paths like `\\server\share`) appear in the sidebar under **Network** and work like local drives. For direct SSH/SFTP access, use [Remote Connections](../features/remote-connections/).

## Does SPAN Finder work with cloud storage (OneDrive, Dropbox, iCloud)?

Yes. SPAN Finder detects cloud sync folders automatically and shows real-time sync status badges on files. Cloud-only files (not yet downloaded) are handled safely — previews use the Shell thumbnail cache and never force a download.

## Is there a portable version?

Not currently. SPAN Finder is distributed as an MSIX package, which requires installation. A portable build is not planned as it would conflict with the MSIX security model.

## How do I uninstall SPAN Finder?

Uninstall via **Settings → Apps** (or the Microsoft Store). Note: if you set SPAN Finder as the default file manager, Windows will automatically fall back to `explorer.exe` when the app is removed.

## What is the File Shelf?

The Shelf is a Yoink-style temporary holding panel on the right edge of the window. Drop files onto it from any folder, then navigate to the destination and click **Move here** or **Copy here**. See [File Shelf](../features/shelf/) for full details.
