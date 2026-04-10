---
title: Themes & Customization
layout: default
parent: Features
nav_order: 10
---

# Themes & Customization
{: .no_toc }

Ten built-in themes, three icon packs, ten font options, and independent density controls — tune Span Finder until it looks exactly like **your** file manager.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is it?

Span Finder takes visual customization seriously. You can pick from ten color themes, switch between three icon packs, choose from ten fonts including Korean-friendly CJK fallbacks, and set row density to one of six presets — independently from font size.

All customization lives under Settings → **Appearance** (<kbd>Ctrl</kbd> + <kbd>,</kbd>).

## Themes

Ten themes are built in:

| Theme | Mode | Notes |
|---|---|---|
| **Light** | Light | Standard Fluent light theme |
| **Dark** | Dark | Standard Fluent dark theme |
| **System** | Auto | Follows Windows light/dark setting |
| **Dracula** | Dark | Pink/purple accents on soft dark background |
| **Tokyo Night** | Dark | Deep blue with neon highlights |
| **Catppuccin** | Dark | Pastel Mocha palette |
| **Gruvbox** | Dark | Warm retro earthtones |
| **Solarized** | Dark | Ethan Schoonover's signature palette |
| **Nord** | Dark | Cool arctic blues |
| **One Dark** | Dark | Atom's iconic palette |
| **Monokai** | Dark | Classic Sublime/TextMate warmth |

Themes apply instantly — no restart required.

> **Tip:** Leave theme set to **System** and Span Finder will flip with Windows when you change your system-wide appearance.

## Density and size

Span Finder separates **row height** from **font/icon size**, giving you six levels each to combine independently:

- **Row density** — 6 levels from Compact to Spacious
- **Font & icon size** — 6 levels from Small to Large

This is important: most file managers either give you one tiny "Compact" mode that shrinks everything or a "Comfortable" mode that bloats everything. Span Finder lets you pick, say, compact rows with large text (great for tired eyes) or spacious rows with small text (great for high-DPI displays).

## Fonts

Ten fonts are bundled:

- **Segoe UI Variable** (default) — Microsoft's modern system font
- **Consolas** — Microsoft's monospace classic
- **Cascadia Code** / **Cascadia Mono** — Designed for Windows Terminal
- **D2Coding** — Popular Korean coding font
- **JetBrains Mono** — JetBrains' official monospace
- **Fira Code** — Monospaced font with ligatures
- **Source Code Pro** — Adobe's open-source monospace
- **Noto Sans** — Google's universal sans-serif
- **IBM Plex Sans** — IBM's corporate typeface

A **CJK fallback chain** is applied automatically — if your primary font doesn't have glyphs for Korean, Japanese, or Chinese characters, Span Finder falls back to 맑은 고딕 (Malgun Gothic), Yu Gothic, or Microsoft YaHei as appropriate. You never see tofu boxes.

## Icon packs

Switch between three complete icon packs:

- **Remix Icon** — Clean geometric set
- **Phosphor Icons** — Flexible, friendly shapes
- **Tabler Icons** — Minimal, consistent stroke weights

Each pack provides icons for 60+ categories — files, folders, drives, sidebar sections, toolbar actions. Switching packs repaints every icon in the app instantly.

## Language

Nine languages are supported out of the box:

- English
- 한국어 (Korean)
- 日本語 (Japanese)
- 简体中文 (Chinese Simplified)
- 繁體中文 (Chinese Traditional)
- Deutsch (German)
- Español (Spanish)
- Français (French)
- Português BR (Portuguese, Brazil)

Language switching is **runtime** — no restart. You can also pick **System** to follow Windows.

Shell context menu verbs are translated in six languages (Korean, Japanese, German, Spanish, French, Portuguese) so even native shell extensions feel localized.

## Backdrop and system chrome

Span Finder uses **Mica** backdrop on Windows 11 for that translucent, wallpaper-tinted feel. Windows 10 falls back to a solid theme background.

## Where customization lives

Every option lives under Settings → **Appearance**:

1. Press <kbd>Ctrl</kbd> + <kbd>,</kbd> to open Settings
2. Select the **Appearance** section
3. Each control updates the app live — you can see the effect before committing

Settings are stored per-user. Switching Windows accounts gives each user their own theme.

## Tips & gotchas

> **Tip:** Combine **Compact** density with **Large** font size for a high-information layout that is still readable on a 4K display.

> **Tip:** If you work in multiple languages daily, switch Span Finder's language from the Settings tab directly — no restart required.

> **Gotcha:** Themes affect Span Finder's chrome and built-in views. They do **not** affect the preview panel's rendering of, say, a PDF — those render as they exist in the source file.

> **Gotcha:** Changing fonts can shift layout measurements slightly. If a column width looks off after changing fonts, double-click the column separator to auto-fit.

## See also

- [Miller Columns](../miller-columns/) — Density settings affect how much fits in each column
- [Sidebar](../sidebar/) — Icon pack drives sidebar section icons
- [Preview Panel](../preview/) — Theme affects Markdown/code rendering
- [Keyboard Shortcuts](../../shortcuts/)
