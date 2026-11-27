---
layout: theme
title: Graphite Island Spectrum
category: theme
homepage: https://github.com/Jenlybein/typora-graphite-island
download: https://github.com/Jenlybein/typora-graphite-island/archive/refs/heads/master.zip
built-in: false
author: Jenlybein
author_url: https://github.com/Jenlybein
thumbnail: graphite-island-spectrum.png
preview: graphite-island-spectrum.png
description: A soft Bauhaus Typora theme on a strict five-colour palette with six distinct heading tones, geometry instead of ornament, and a separate warm code area. No external dependencies.
tags: [light, bauhaus, minimal, geometric, clean, cjk]
---

# Graphite Island Spectrum for Typora

A soft Bauhaus theme drawn on graphite drafting paper: a strict **five-colour palette** holds the whole surface, **six heading levels each take their own tone**, and structure is carried by geometry instead of ornament.

## Features

- **Five colours, no more** — graphite ink, paper white, warm sand, clay red, and mist grey. Every other colour is one of these five as a tint or a shade; no sixth hue sneaks in.
- **Six heading levels, six tones** — the six hues are spread wide (23° → 37° → 83° → 326°) so each level is recognisable at a glance, while lightness stays in one narrow band so they never fight. All six keep at least 4.5:1 against the paper; body text sits at 16.2:1.
- **Geometry, not ornament** — 1px structure lines instead of soft shadows, one flat 3px "lifted card" shadow, 18px radii, and a faint 40px drafting grid printed on the drawing-board background.
- **Separate warm code area** — inline code, fenced blocks, CodeMirror and source mode share one warm sand-paper card (`#efe9d6`) with a mint / red / amber / green syntax set, kept out of the body palette on purpose.
- **Zero external dependencies** — no `@import`, no web fonts, no remote images; the two decorative marks are inline `data:` SVGs. Works offline and exports to PDF cleanly.
- **CJK-friendly typography** — body prefers Noto Sans SC / MiSans / Microsoft YaHei / PingFang SC at 16px and 1.85 line-height; headings prefer Bahnschrift; code prefers JetBrains Mono / Cascadia Code / SF Mono / Consolas. Every stack ends in a system fallback.
- **Full coverage** — headings 1–6 with their own marks, body, marks/highlights, links, emphasis and strikethrough, ordered/unordered/task lists, tables, footnotes, quotes and nested quotes, inline code and fenced blocks, source mode, selection colours, sidebar/outline/footer ground, plus print and reduced-motion behaviour.

## Installation

1. Download and unzip the theme, or clone the [repository](https://github.com/Jenlybein/typora-graphite-island).
2. Copy `graphite-island-spectrum.css` directly into Typora's theme folder (**Preferences → Appearance → Open Theme Folder**), keeping it at the top level.
3. Select **Graphite Island Spectrum** from the theme menu. If nothing changes, restart Typora — it caches theme styles until relaunched.

> The name shown in Typora's theme list comes from the filename: `graphite-island-spectrum.css` becomes **Graphite Island Spectrum**.

## Customisation

All colours live in the `:root` token block at the top of the CSS. Changing the five base values re-skins everything consistently:

```css
:root {
  --bb-ink:   #1D1D1F;   /* all structure */
  --bb-paper: #FBFBFD;   /* page and cards */
  --bb-amber: #D8A24B;   /* warm accent */
  --bb-clay:  #BF4800;   /* strong accent */
  --bb-mist:  #F5F5F7;   /* grey ground */
}
```

Heading tones are their own six tokens (`--bb-h1` … `--bb-h6`), so you can flatten them to one colour without touching anything else.

## License

MIT — Copyright (c) 2026 Jenlybein
