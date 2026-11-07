---
layout: theme
title: Libertinus
category: theme
homepage: https://github.com/wei-yuhang/typora-theme-libertinus
download: https://github.com/wei-yuhang/typora-theme-libertinus/releases/download/v1.0.0/libertinus.zip
built-in: false
author: Yuhang Wei
author_url: https://github.com/wei-yuhang
thumbnail: libertinus.png
description: A light, serif theme inspired by typeset articles, with Libertinus typography, restrained quotations, and booktabs-style tables.
tags: [light, serif, academic]
typora-root-url: ../../
typora-copy-images-to: ../../media/theme/libertinus
---

# Libertinus

Libertinus is a light theme for notes, essays, and technical writing, inspired by the appearance of a Pandoc and XeLaTeX article.

![Libertinus typography, an italic blockquote, and a booktabs-style table](/media/theme/libertinus/typography.png)

## Features

- Libertinus Serif typography with an A4-inspired, 16 cm reading measure and LaTeX-style headings.
- Italic blockquotes with a narrow grey border, while quoted code stays upright.
- Simple tables with booktabs-style horizontal rules.
- Warm grey code blocks with an editable language selector below the code when the block is focused.
- 思源宋体 (Source Han Serif) for Chinese text when installed, with serif fallbacks.
- A single CSS file, with no scripts or bundled fonts.

![Python code and a displayed equation in Libertinus](/media/theme/libertinus/code-and-math.png)

## Installation

1. [Download Libertinus](https://github.com/wei-yuhang/typora-theme-libertinus/releases/download/v1.0.0/libertinus.zip) and unzip it.
2. In Typora, open **Preferences → Appearance → Open Theme Folder**.
3. Copy `libertinus.css` into that folder.
4. Restart Typora and choose **Themes → Libertinus**.

For the intended typography, install **Libertinus Serif** and **Libertinus Sans** from the [official font releases](https://github.com/alerque/libertinus/releases). For Chinese text, install **思源宋体 (Source Han Serif)** from [Adobe’s releases](https://github.com/adobe-fonts/source-han-serif/releases). Fonts are not bundled; system fallbacks are used when they are unavailable. See the [README](https://github.com/wei-yuhang/typora-theme-libertinus#fonts) for the full font notes.

## Compatibility

Used long-term on **Windows** by the author, and checked in **Typora 1.14.15 on macOS**, including the latest layout changes and PDF export. **Linux has not been tested.**

Libertinus is a light theme with no separate dark variant. Math rendering and PDF page size and margins follow Typora’s settings.

## License

[MIT](https://github.com/wei-yuhang/typora-theme-libertinus/blob/main/LICENSE). Fonts installed separately retain their own licenses.
