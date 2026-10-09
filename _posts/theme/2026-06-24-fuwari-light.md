---
layout: theme
title: Fuwari Light
category: theme
homepage: "https://github.com/Caph-dev/typora-fuwari-theme"
download: "https://github.com/Caph-dev/typora-fuwari-theme/archive/refs/heads/main.zip"
built-in: false
author: Caphhh
thumbnail: fuwari-light.png
typora-root-url: ../../
description: "A soft, card-style light Typora theme inspired by Fuwari. Features an OKLCH color palette, restrained syntax highlighting, and CJK-friendly typography."
tags: [light, soft, card, cjk, clean]
---
# Fuwari Light for Typora

A soft, card-style light theme inspired by the [Fuwari](https://github.com/saicaca/fuwari) Astro blog template.

## Features

- **Card-style writing surface** — the editor area sits on a lightly tinted page background with a rounded white card
- **OKLCH color palette** — unified cool-toned palette with default hue 250, easily customizable
- **Slate Paper code fences** — cool, restrained syntax highlighting with distinct token colors
- **CJK-friendly typography** — carefully tuned font stack with Maple Mono for code, Roboto + system fallbacks for body
- **Dashed underline links** — subtle, modern link styling
- **Rounded inline code** — soft pill-shaped inline code (`#e2f0ff` background)
- **Mermaid diagram support** — styled diagram nodes and labels
- **GitHub-style alerts** — NOTE, TIP, IMPORTANT, WARNING, and CAUTION callout blocks

## Customization

Change the accent hue by editing one variable in `fuwari-light.css`:

```css
:root {
  --hue: 250; /* 200=teal, 310=purple/pink, 345=pink/red */
}
```

## Installation

1. Download and unzip the theme.
2. Copy `fuwari-light.css` and `fuwari-assets/` into Typora's theme folder.
3. Restart Typora and select **Fuwari Light** from the Themes menu.
