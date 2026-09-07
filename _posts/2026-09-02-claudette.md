---
layout: post
title: "Claudette"
author: "CookPiu"
preview: "claudette.png"
homepage: "https://github.com/CookPiu/typora-theme-claudette"
download: "https://github.com/CookPiu/typora-theme-claudette/archive/refs/heads/main.zip"
description: "A warm, understated theme in light and dark: paper-toned page, a single terracotta accent, serif headings and hairline rules."
tags: [light, dark, clean, serif, minimal]
---

# Claudette

A warm, understated theme for Typora, in light and dark. Paper-toned background, a single terracotta accent, serif headings, sans-serif body text and hairline rules. Restraint over ornament.

![Claudette](https://raw.githubusercontent.com/CookPiu/typora-theme-claudette/main/screenshot.png)

![Claudette Dark](https://raw.githubusercontent.com/CookPiu/typora-theme-claudette/main/screenshot-dark.png)

## Features

- **Light and dark** — `claudette.css` and `claudette-dark.css`; the dark file imports the light one and only swaps tokens.
- **Warm paper palette** — `#faf9f5` page, `#f2f0e9` sidebar, alpha hairlines, near-black text and one terracotta accent used sparingly.
- **Editorial typography** — serif headings at weight 400, a lead paragraph after H1, uppercase H6 labels.
- **Quiet code blocks** — hairline border, `.75rem` radius, language pill, low-saturation syntax colors.
- **Hairline tables** — horizontal rules only, uppercase headers, subtle row hover.
- **Whole-app styling** — sidebar, outline, quick-open, search, menus, dialogs, source mode and scrollbars all match.
- **Print-ready** — decorations are stripped on export.

## Installation

1. Download `claudette.css` and `claudette-dark.css`.
2. Open Typora **Preferences → Appearance → Open Theme Folder**.
3. Copy both files into that folder.
4. Restart Typora and select **Claudette** or **Claudette Dark** from the Themes menu.

## Fonts

No fonts are bundled. Claudette prefers Source Serif 4, Inter and JetBrains Mono when installed, and falls back to Georgia / Segoe UI / Consolas and their CJK counterparts otherwise. Edit the `--font-*` variables in `:root` to change them.
