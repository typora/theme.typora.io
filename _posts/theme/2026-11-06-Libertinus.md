---
layout: theme
title: Libertinus
category: theme
homepage: https://github.com/wei-yuhang/typora-theme-libertinus
download: https://github.com/wei-yuhang/typora-theme-libertinus/releases/download/v1.1.0/libertinus.zip
built-in: false
author: Yuhang Wei
author_url: https://github.com/wei-yuhang
thumbnail: libertinus.png
description: A light and dark serif theme inspired by typeset articles, with Libertinus typography, restrained quotations, and booktabs-style tables.
tags: [light, dark, serif, academic]
typora-root-url: ../../
typora-copy-images-to: ../../media/theme/libertinus
---

# Libertinus

Libertinus is a light and dark theme for notes, essays, and technical writing, inspired by the appearance of a Pandoc and XeLaTeX article.

![Libertinus typography, an italic blockquote, and a booktabs-style table](/media/theme/libertinus/typography.png)

## Features

- Libertinus Serif typography with an A4-inspired, 16 cm reading measure and LaTeX-style headings.
- Italic blockquotes with a narrow grey border, while quoted code stays upright.
- Simple tables with booktabs-style horizontal rules.
- Fira Code when installed, with monospace fallbacks. Warm grey or charcoal code blocks with an editable language selector below the code when the block is focused.
- 思源宋体 (Source Han Serif) for Chinese text when installed, with serif fallbacks.
- Two small CSS files sharing one layout, with no scripts or bundled fonts.
- A warm charcoal dark variant with matching syntax highlighting, source mode, and sidebar colors. Light print styling; choose Libertinus as the PDF export theme for white page margins.

![Python code and a displayed equation in Libertinus](/media/theme/libertinus/code-and-math.png)

![Libertinus Dark typography](/media/theme/libertinus/dark-typography.png)

![Fira Code and mathematics in Libertinus Dark](/media/theme/libertinus/dark-code-and-math.png)

## Installation

1. [Download Libertinus](https://github.com/wei-yuhang/typora-theme-libertinus/releases/download/v1.1.0/libertinus.zip) and unzip it.
2. In Typora, open **Preferences → Appearance → Open Theme Folder**.
3. Copy **both** `libertinus.css` and `libertinus-dark.css` into that folder. Keep them together: the dark variant imports the shared light stylesheet.
4. Restart Typora and choose **Themes → Libertinus** or **Libertinus Dark**.

For the intended typography, install **Libertinus Serif** and **Libertinus Sans** from the [official font releases](https://github.com/alerque/libertinus/releases). For Chinese text, install **思源宋体 (Source Han Serif)** from [Adobe’s releases](https://github.com/adobe-fonts/source-han-serif/releases). The screenshots also use [Fira Code](https://github.com/tonsky/FiraCode) for code. Fonts are not bundled; system fallbacks are used when they are unavailable. See the [README](https://github.com/wei-yuhang/typora-theme-libertinus#fonts) for the full font notes.

## Compatibility

The original light theme has been used long-term on **Windows** by the author. Both variants have been checked in **Typora 1.14.15 on macOS**, including code, math, source mode, sidebar layout, and PDF export. The new dark variant still needs Windows verification. **Linux has not been tested.**

For white PDF page margins while editing in dark mode, choose **Libertinus** in **Settings → Export → PDF → Theme**. Math rendering and PDF page size and margins follow Typora’s settings.

## License

[MIT](https://github.com/wei-yuhang/typora-theme-libertinus/blob/main/LICENSE). Fonts installed separately retain their own licenses.
