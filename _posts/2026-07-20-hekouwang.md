---
layout: post
title: "Hekouwang"
author: "huiyonghkw"
preview: "hekouwang.png"
homepage: "https://github.com/huiyonghkw/hekouwang-typora-theme"
download: "https://github.com/huiyonghkw/hekouwang-typora-theme/archive/refs/heads/main.zip"
description: "CJK long-form Typora theme (light + dark): body 1rem · leading 1.65 · fluid 52em · paper card on #write. Token-generated CSS, zero !important, ~100 KB Inter — MIT free default."
tags: [light, dark, clean, cjk, minimal, reading]
---

# Hekouwang for Typora

A Typora theme for people who write **long-form Markdown in Chinese** for hours — not chat-bubble density.

**Themes menu (this listing / MIT zip):**

| Menu | What you get |
|---|---|
| **Hekouwang** | Light · warm paper · CJK long-form |
| **Hekouwang Dark** | Dark · same reading metrics · paper card |

Shared metrics: body `1rem` · leading `1.65` · measure `min(52em, 100% − gutter)` · paper surface on `#write`.

The CSS is **generated from a token file** (`scripts/tokens.json` → `scripts/build.py`) rather than hand-written.

Repo: [huiyonghkw/hekouwang-typora-theme](https://github.com/huiyonghkw/hekouwang-typora-theme) · live notes: [GitHub Pages](https://huiyonghkw.github.io/hekouwang-typora-theme/)

## Design principles

- **Built for CJK long-form.** Chinese paragraphs need leading ≥1.6 and a measure near ~40–50 characters.
- **No high-saturation accents.** Inline code uses a low-saturation warm brown so a line with many `` `code` `` spans still reads as text.
- **Hierarchy from size, weight, and spacing — not color bars.** No left accent stripes.
- **Borders are ink at low alpha**, never flat gray on a warm page.
- **Paper card on `#write`** (light and dark): warm radial, large radius, outer shadow; chrome (sidebar / gutter) sits one step behind.

## CJK / Latin mixing

Anthropic Sans contains **581 glyphs and zero CJK characters** — not even ideographic punctuation. Chinese always falls back to the system face (PingFang SC on macOS). This theme pairs a Latin face with that system CJK face and **bundles no CJK font**.

Stack: Anthropic Sans (only if already on your machine — proprietary, never shipped) → **Inter** (SIL OFL, Latin subset, ~100 KB, shipped) → system UI. Most people see Inter.

## Installation

```bash
git clone https://github.com/huiyonghkw/hekouwang-typora-theme.git
cd hekouwang-typora-theme
./scripts/install.sh
```

Or copy `theme/hekouwang.css`, `theme/hekouwang-dark.css`, and the `theme/hekouwang/` folder into Typora’s themes directory (Preferences → Open Theme Folder).

Then **quit Typora completely (Cmd+Q) and relaunch** — switching themes does not reload a modified CSS file. Choose **Hekouwang** or **Hekouwang Dark**.

## Customization

Do not edit the CSS; it is generated. Edit `scripts/tokens.json` and rebuild:

```bash
python3 scripts/build.py
```

The build asserts:

- **zero `!important`**
- **zero `px` font sizes** except the root (so Typora’s font-size preference keeps working)

## Relationship to the gallery “Claude Theme”

There is already a [Claude Theme](https://theme.typora.io/theme/Claude-Theme/) with a similar goal. **This is an independent implementation, not a fork** — no CSS was copied. Both themes reference Anthropic’s published brand colors; that is where color overlap comes from.

| | Gallery Claude Theme | Hekouwang |
|---|---|---|
| Authoring | ~3,158 hand-written lines | generated from tokens |
| `!important` | 397 | **0** (build-enforced) |
| Font sizes | some `px` | all `rem` except root |
| Bundled fonts | ~24 MB (incl. Noto Serif SC) | **~100 KB** (Inter Latin) |
| Anthropic fonts | redistributed | **not shipped**; `local()` + Inter |
| Body CJK | Noto Serif SC (serif) | system sans-serif |
| Latin weights | single 400 → synthetic bold | variable **300–800** + `opsz` |

## Dark variant

`hekouwang-dark.css` is **sampled**, not inverted from light — light-mode relationships do not survive inversion (e.g. in dark mode the sidebar is *lighter* than the editor pane). Both variants share the same reading metrics; the `dark` block overrides only `color` / `alpha`.

## Licensing

MIT for the free theme CSS and scripts. Only Inter (SIL OFL 1.1) is shipped. This theme does **not** bundle or redistribute Anthropic fonts. Independent work; not affiliated with Anthropic PBC.

## Platform support

Designed and tested on **macOS**. Windows / Linux should work but are not fully tested. No Windows “unibody” styles.
