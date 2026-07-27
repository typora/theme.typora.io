---
layout: theme
title: "Kraft Paper"
author: "jasper0507"
homepage: "https://github.com/jasper0507/kraft-paper"
download: "https://github.com/jasper0507/kraft-paper/releases/latest"
thumbnail: "kraft-paper.png"
preview: "kraft-paper.png"
category: "theme"
description: "A warm paper-textured Typora theme (light + dark) inspired by claude.ai — fixed 768px measure, serif body, and CJK song/hei emphasis for long-form reading."
tags: [light, dark, clean, cjk, reading, minimal]
---

# Kraft Paper for Typora

Kraft Paper is a warm, paper-textured theme pair for long-form writing and reading in Typora. It follows the claude.ai warm-beige palette (terracotta accent + warm neutrals) and ships both light and dark variants with matching structure.

> Designed and tested primarily on **Windows 11**. Typora **≥ 1.5** recommended.

## Features

- **Light and dark** — `kraft-paper.css` and `kraft-paper-dark.css` share layout rules; differences stay in `:root` variables and a dark-only section.
- **Warm paper palette** — paper surfaces, terracotta accents, and warm gray borders instead of cold neutral grays.
- **Long-form measure** — body column fixed at **768px** (~48rem), aligned with claude.ai chat width.
- **Typography** — serif body + sans UI; Chinese follows “Song for body, Hei for emphasis” so bold text stays sharp.
- **Scoped content styles** — markdown layout lives under `#write` so tables and quotes do not leak into UI panels.
- **Editor coverage** — sidebar, quick open, search/replace, task lists, tables, fenced code, footnotes, and Windows megamenu theming.
- **Print / PDF** — dark theme switches back to the light paper palette when printing or exporting PDF.

## Installation

1. Download `kraft-paper.css` and/or `kraft-paper-dark.css` from the [latest release](https://github.com/jasper0507/kraft-paper/releases/latest).
2. Open **Typora → Preferences → Appearance → Open Theme Folder**.
3. Copy the CSS file(s) into the theme folder.
4. Restart Typora, then select **Kraft Paper** or **Kraft Paper Dark**.

| Platform | Theme folder |
| --- | --- |
| Windows | `%APPDATA%\Typora\themes\` |
| macOS | `~/Library/Application Support/abnerworks.Typora/themes/` |
| Linux | `~/.config/Typora/themes/` |

## Fonts

Optional brand fonts (Tiempos Text, Styrene B, etc.) improve the look if already installed. The repository does **not** redistribute proprietary fonts; missing faces fall back to system stacks. HTML export may load Source Serif 4 and IBM Plex Sans via `@include-when-export`.

## Disclaimer

Independent community theme inspired by the public design language of [claude.ai](https://claude.ai). Not affiliated with, endorsed by, or sponsored by Anthropic.

Homepage: [github.com/jasper0507/kraft-paper](https://github.com/jasper0507/kraft-paper)