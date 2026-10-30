---
layout: theme
title: Graphite Island Spectrum
category: theme
homepage: https://github.com/Jenlybein/typora-graphite-island-spectrum
download: https://github.com/Jenlybein/typora-graphite-island-spectrum/archive/refs/heads/main.zip
built-in: false
author: Jenlybein
author_url: https://github.com/Jenlybein
thumbnail: graphite-island-spectrum.png
preview: graphite-island-spectrum.png
description: A soft Bauhaus Typora theme on a strict five-colour palette — graphite structure lines, warm paper, six heading tones, and a warm code card. No external dependencies.
tags: [light, bauhaus, minimal, warm, graphite, cjk]
---
# Graphite Island Spectrum

A soft Bauhaus theme built on five colours and no more: **graphite** draws every structure line,
**paper** holds the air, **mist** sets sections apart, and two warm accents — **amber** and **clay** —
do all the talking.

Six heading levels carry six different tones. The idea is that you can find your place in a long
document by colour alone: hue tells you the level, lightness stays put so the page stays calm.

![Graphite Island Spectrum — headings, body text, nested blockquote](/media/theme/graphite-island-spectrum/preview.png)

## Highlights

- **A strict five-colour palette** — graphite `#1D1D1F`, paper `#FBFBFD`, mist `#F5F5F7`,
  amber `#D8A24B`, clay `#BF4800`. Every other value in the theme is one of these five, stated as a
  tint or a shade; no sixth colour sneaks in.
- **Six heading tones** — H1 graphite, H2 clay, H3 ochre `#8A5E14`, H4 olive `#55602F`,
  H5 plum `#6B4A5B`, H6 warm grey `#6B645D`. Hues are spread from 23° to 326° while lightness stays
  inside one narrow band, so the levels separate without clashing. All six hold at least **4.5:1**
  against the paper surface (worst case H2 at 4.91); body text sits at **16.3:1**.

  ![Six heading levels, six tones](/media/theme/graphite-island-spectrum/headings.png)
- **Geometry instead of ornament** — 1px structure lines rather than soft shadows, one flat 3px
  shadow that reads as a lifted card, 18px radii, and a faint 40px drafting grid printed on the
  drawing-board background. Triangle-and-square marks carry the section titles. No gradients, no
  glass, no dark-mode-only tricks.
- **Warm code card** — the code area is deliberately out-of-palette and inherited from its parent
  theme, [Animal Island](https://github.com/YanyingWei1997/typora-theme-animal-island): warm
  sand-paper surface `#efe9d6`, 2px sand border, 18px radius, 3px flat shadow, and a
  mint / red / amber / green syntax set. One deviation is deliberate: because Typora renders every
  CodeMirror line as its own `<pre>` and its own reset does not touch `box-shadow`, the card's 3px
  shadow leaked onto every line and drew a rule between code lines — here it is thinned to 1px, and
  removed in source mode.

  ![Code card and inline code](/media/theme/graphite-island-spectrum/code.png)
- **CJK-friendly typography** — body prefers `Noto Sans SC` / `MiSans` / `Microsoft YaHei` /
  `PingFang SC`, headings prefer `Bahnschrift`, code prefers `JetBrains Mono` / `Cascadia Code` /
  `SF Mono` / `Consolas`; 16px at 1.85 line-height. Every stack ends in a system fallback, so no font
  installation is needed.
- **Zero external dependencies** — no `@import`, no web fonts, no remote images; the two decorative
  marks are inline `data:` SVGs. It works offline, on any platform, and exports cleanly to PDF.
- **Print / PDF** — the grid, borders, radii and shadows are stripped; only ink stays.
- **Reduced motion** — transitions collapse when the system asks for it.

## Elements covered

Headings 1–6 with their own marks, body text, highlights and `<mark>`, links, emphasis and
strikethrough, ordered/unordered lists, task lists, tables, footnotes, quotes and nested quotes,
inline code and fenced blocks, source mode, selection colours, the sidebar/outline/footer ground.

Not customised (nothing looks broken, they simply keep Typora's default): Mermaid diagrams, the TOC
pane, GitHub-style alerts, `<kbd>` keys, inline math.

## Installation

1. Download and unzip the theme, or clone the
   [repository](https://github.com/Jenlybein/typora-graphite-island-spectrum).
2. Copy `graphite-island-spectrum.css` directly into Typora's theme folder
   (**Preferences → Appearance → Open Theme Folder**). It must sit at the top level of that folder.
3. Restart Typora, then pick **Graphite Island Spectrum** from the Themes menu.

> The name shown in Typora comes from the filename: `graphite-island-spectrum.css` becomes
> **Graphite Island Spectrum**.

## Customisation

Every colour lives in the `:root` token block at the top of the file — change those five values and
the whole theme re-skins consistently. Heading tones are six separate tokens (`--bb-h1` … `--bb-h6`),
so they can be flattened to one colour without touching anything else.

```css
:root {
  --bb-ink:   #1D1D1F;   /* all structure */
  --bb-paper: #FBFBFD;   /* page and cards */
  --bb-amber: #D8A24B;   /* warm accent */
  --bb-clay:  #BF4800;   /* strong accent */
  --bb-mist:  #F5F5F7;   /* grey ground */
}
```

## Notes

Designed and tested on **Windows 11 with Typora 1.14.15**. It carries no platform-specific "unibody"
styles, so macOS and Linux should work as well, but they are not fully tested. Light theme only.

## License and credits

MIT. This theme is derived from **Animal Island** by **YanyingWei1997**
([repository](https://github.com/YanyingWei1997/typora-theme-animal-island), MIT, itself inspired by
[animal-island-ui](https://github.com/guokaigdg/animal-island-ui)) — the original files were never
modified, this is a copy that was re-skinned and extended, and the original copyright notice travels
with it.
