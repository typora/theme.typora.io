---
layout: post
title: "Hekouwang"
author: "huiyonghkw"
preview: "hekouwang.png"
homepage: "https://github.com/huiyonghkw/hekouwang-typora-theme"
download: "https://github.com/huiyonghkw/hekouwang-typora-theme/archive/refs/heads/main.zip"
description: "A Typora theme for long-form Chinese Markdown. Hekouwang + Hekouwang Dark, paper card on #write, body 1rem / leading 1.65 / fluid 52em measure. Token-generated CSS, zero !important, ~100 KB Inter (OFL)."
tags: [light, dark, clean, cjk, minimal, reading, paper]
---

# Hekouwang for Typora

A Typora theme for people who write **long-form Markdown in Chinese** for hours.

Two themes ship in the menu:

| Menu | What you get |
|---|---|
| **Hekouwang** | Light · CJK long-form · paper card |
| **Hekouwang Dark** | Dark · same metrics · paper card |

Reading metrics: body `1rem`, leading `1.65`, measure `min(52em, 100% − gutter)`. The CSS is **generated from a token file** (`scripts/tokens.json` → `scripts/build.py`) rather than hand-written.

## Design principles

- **Built for CJK long-form, not chat bubbles.** Chinese paragraphs need leading `≥1.6` and a measure near ~40–50 characters.
- **No high-saturation accents.** Inline code uses warm brown (`#8a5a3c`) on a soft wash.
- **Hierarchy from size, weight and spacing — not color bars.**
- **Borders are ink at low alpha**, never flat gray on a warm page.
- **Paper card on `#write`** (light and dark): warm radial, large radius, outer shadow; sidebar / gutter sit one step behind as chrome.

## CJK / Latin mixing

Anthropic Sans contains **581 glyphs and zero CJK characters**. Chinese always falls back to the system face (PingFang SC on macOS). The theme pairs a Latin face with that system CJK face and **bundles no CJK font**.

Font stack: Anthropic Sans (`local()` only, never redistributed) → **Inter** (SIL OFL, Latin subset, ~100 KB, shipped) → system UI font.

## Customization

Do not edit the CSS; it is generated. Edit `scripts/tokens.json` and rebuild:

```bash
python3 scripts/build.py
./scripts/install.sh
```

Build checks:

- **zero `!important`**
- **zero `px` font sizes except the root**

## Relationship to the existing "Claude Theme"

There is already a [Claude Theme](https://theme.typora.io/theme/Claude-Theme/) in the gallery with a similar inspiration. **This is an independent implementation, not a fork** — no CSS was copied. Both themes may reference Anthropic brand colors; that is where any color overlap comes from.

| | Existing Claude Theme | Hekouwang |
|---|---|---|
| Authoring | ~3,158 hand-written lines | generated from tokens |
| `!important` | 397 | **0** (build-enforced) |
| Font sizes | some `px` | all `rem` except root |
| Bundled fonts | ~24 MB (full Noto Serif SC) | **~100 KB** (Inter Latin) |
| Anthropic fonts | redistributed | **not shipped**; `local()` + Inter |
| Body CJK | Noto Serif SC (serif) | system sans-serif |
| Latin weights | single 400 → synthetic bold | variable **300–800** + `opsz` |
| UI coverage | mainly the editor | sidebar, tree, outline, search, focus |

## Dark variant

`hekouwang-dark.css` is **sampled** from a desktop dark UI, not inverted from light:

- In dark mode the **sidebar / gutter (`#262626`) is lighter than the paper pane (`#1f1f1e`)** — the reverse of light mode.
- Inline code uses a **neutral white overlay** in dark, not the brand-orange wash used in light.

## Licensing note

This theme does **not** bundle or redistribute any Anthropic font. Only Inter (SIL OFL 1.1) is shipped. Independent work; not affiliated with Anthropic PBC.

## Installation

1. Download and unzip the theme.
2. Copy `theme/hekouwang.css`, `theme/hekouwang-dark.css` and the `theme/hekouwang/` folder into Typora's theme folder.
3. **Quit Typora completely and relaunch**, then select **Hekouwang** or **Hekouwang Dark**.

Or:

```bash
git clone https://github.com/huiyonghkw/hekouwang-typora-theme.git
cd hekouwang-typora-theme
./scripts/install.sh
```

## Platform support

Designed and tested on **macOS**. Not fully tested on Windows/Linux. Does not include styles for the Windows "unibody" style.
