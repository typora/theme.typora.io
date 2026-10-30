---
layout: theme
title: Lyle Light
category: theme
homepage: https://github.com/Le0v1n/lyle-light
download: https://github.com/Le0v1n/lyle-light/releases/latest/download/lyle-light.zip
built-in: false
author: Le0v1n
author_url: https://github.com/Le0v1n
thumbnail: lyle-light.png
description: A clean light theme with comfortable CJK typography, blue-gray accents, and standard and wide layouts.
tags: [light, cjk, minimal, wide]
typora-root-url: ../../
---

# Lyle Light

Lyle Light is a clean light theme for reading and writing in Typora. It pairs a white page and near-black text with blue links, subtle horizontal table rules and softly shaded code blocks.

## Two layouts

- **Lyle Light:** centered content up to 1000px wide.
- **Lyle Light Wide:** centered content up to 1600px wide, for large screens, wide tables and code.

Both CSS files are standalone and adapt to smaller windows. Body text uses 17px with 1.75 line height, while code blocks use 14px.

## Features

- Inter and Source Han Sans SC font preferences, with system fallbacks. Fonts are optional and not bundled.
- Native interactive task lists, nested blockquotes and syntax highlighting.
- Compact table spacing and a darker header separator.
- Blue-gray Mermaid styling, native math, images, footnotes and HTML details styling.
- Separate A4 print rules for text size and long-code wrapping.

## Preview

Actual Typora screenshot of the Wide variant on Windows:

![Lyle Light Wide typography, table, quotes, tasks and code](/media/theme/lyle-light/preview.png)

## Installation

1. Download and extract the theme ZIP.
2. In Typora, open **Preferences → Appearance → Open Theme Folder**.
3. Copy `lyle-light.css` and/or `lyle-light-wide.css` into that folder.
4. Restart Typora and choose **Lyle Light** or **Lyle Light Wide**.

No plugins, runtime scripts or remote fonts are required. Optional fonts and customization are documented in the [repository](https://github.com/Le0v1n/lyle-light).

## Compatibility

Designed and tested with Typora 1.9.5 on Windows. macOS and Linux are untested. Markdown extensions must be enabled in Typora as needed. Mermaid layout depends on the bundled renderer; custom node colors may be overridden. Large diagrams and tables may need manual PDF pagination adjustments, and this release has not received a full PDF regression pass.

## License

MIT, by [Le0v1n](https://github.com/Le0v1n). Optional fonts retain their own licenses.
