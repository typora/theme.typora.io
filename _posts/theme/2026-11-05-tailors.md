---
layout: theme
title: Tailors
category: theme
homepage: https://chiamzhang.github.io/tailors.theme.typora/preview.html
download: https://github.com/ChiamZhang/tailors.theme.typora/raw/gh-pages/media/theme/tailors/tailors.zip
author: ChiamZhang
thumbnail: tailors.png
preview: tailors.png
description: A refined Typora theme featuring soft neumorphic elegance, clean classical typography, unified seamless background, A4-native reading width, and publisher-grade PDF export.
tags: [light, neumorphism, gradient, a4, clean, modern, typography]
built-in: false
typora-root-url: ../../
typora-copy-images-to: ../../media/theme/tailors
---

# Typora-Theme-Tailors Introduction [中文版](https://github.com/ChiamZhang/tailors.theme.typora/blob/gh-pages/Typora-Theme-Tailors%20%E4%B8%AD%E6%96%87%E4%BB%8B%E7%BB%8D.md)

> A refined Typora theme featuring soft neumorphic elegance, clean classical typography, full-bleed icy blue background, and publisher-grade PDF export.

[🌐 Live HTML Preview](https://chiamzhang.github.io/tailors.theme.typora/preview.html) | [⬇️ Download Theme (tailors.zip)](https://github.com/ChiamZhang/tailors.theme.typora/raw/gh-pages/media/theme/tailors/tailors.zip) | [⭐ GitHub Repository](https://github.com/ChiamZhang/tailors.theme.typora)

---

## 🎨 Visual Showcase

Tailors seamlessly combines classic sunset gradients (Phycat) with soft neumorphic (Neumorphism) aesthetics for a vibrant, expressive hierarchy:

### 1. Sunset Gradient & Chromatic Heading System (Headings)
- **Centered H1**: Prominent title accented by a signature sunset gradient indicator underline;
- **Signature H2 Sunset Capsule**: Iconic `linear-gradient(to right, #f7ce68, #fbabfe)` pill badge with soft neumorphic depth;
- **H3 ~ H6 Sunset Twilight Accents & Dot Patterns**:
  - **H3 Coral Sunset Orange**: Left vertical accent border accompanied by a 3-dot amber pattern;
  - **H4 Twilight Rose**: Solid glowing dot badge accompanied by a 4-dot rose pattern;
  - **H5 Iris Violet**: Delicate hollow ring accompanied by a 5-dot violet pattern;
  - **H6 Midnight Azure**: Minimal horizontal dash accompanied by a 6-dot azure pattern;
- **`<var>` Neumorphic Capsules**: Tactile raised pill badges with ambient gradient glow.

![Sunset Gradient & Chromatic Heading System](media/theme/tailors/showcase-headings.png)

---

### 2. Refined macOS-Style Code Fences
- Built-in classic **macOS red/yellow/green triple-dot window controls**;
- Soft neumorphic drop shadow paired with WCAG-compliant high-contrast syntax highlighting.

![macOS Code Block](media/theme/tailors/showcase-code.png)

---

### 3. Comprehensive Inline Text Formatting
- Full support for all Markdown inline syntax with harmonious visual weights;
- Fresh sky-blue fluorescent underline (`#3b82f6`) replaces harsh pure black lines;
- Distinct rendering for highlights (`==highlight==`), **bold**, *italic*, `inline code`, and strikethrough.

![Inline Styles Showcase](media/theme/tailors/showcase-inline.png)

---

### 4. Elegant Blockquotes & Modern Tables
- **Gradient Blockquote**: Left accent bar featuring the signature sunset gradient on a soft translucent canvas;
- **Airy Modern Table**: Sunset gradient headers, rounded card borders, and gentle alternating zebra striping.

![Tables & Quotes Showcase](media/theme/tailors/showcase-table.png)

---

### 5. Interactive Task Lists
- Clear interactive checkboxes with smooth strikethrough and subdued tones upon completion;
- Clean alignment without jittering animations for an efficient task tracking workflow.

![Interactive Task List Showcase](media/theme/tailors/showcase-tasks.png)

> 📸 **[View Full High-Resolution Showcase Image](media/theme/tailors/Introduction.png)**

---

## Introduction

This theme is inspired by my two favorite themes:

1. **Phycat** by XuJilong. Homepage: [GitHub - sumruler/typora-theme-phycat](https://github.com/sumruler/typora-theme-phycat) — *Mainly referencing the title hierarchical system and gradient accents.*
2. **Typora-Theme-Neumorphism** by Soanguy. Homepage: [GitHub - Soanguy/Typora-Theme-Neumorphism](https://github.com/Soanguy/Typora-Theme-Neumorphism) — *Mainly referencing the soft neumorphic inline styling.*
3. I refined color palettes and removed excessive hover animations to enhance sustained reading comfort. I also thoroughly resolved long-standing bugs left unmaintained in older community stylesheets.
4. Continuous maintenance — if you encounter any display issues or have suggestions, please feel free to open an issue on GitHub.
5. **Tailors** signifies carefully tailoring and seamlessly stitching together the finest design philosophies into a cohesive writing canvas!

---

## ✨ Features & Enhancements

- 🎨 **Full-Bleed Icy Blue Canvas** — The entire window and export output share the soothing `#F9FCFF` tone, completely eliminating harsh white cutouts.
- 📐 **Aligned with Typora Official Standards** — 
  - Standard `860px` max reading width with `30px` padding and `100px` bottom scroll padding.
  - Automatically expands to `1024px` on wide screens (>1400px) and `1200px` on ultra-wide screens (>1800px), matching GitHub and Night themes.
- 🖨️ **Publisher-Grade PDF Export** —
  - Default standard XiaoSi (小四号) body font size (`12pt / 16px`) with `1.65` line height for compact, book-like typography.
  - Zero-margin export CSS allows Typora's native print dialog to manage margins cleanly without doubling borders or white page edges.
  - Removes awkward blue hyperlink styling and replaces underlines with fresh sky-blue fluorescent accents.
  - Intelligent page-break management prevents code blocks and tables from awkward splits across pages.
- 💻 **macOS-Style Code Blocks** — Fenced code blocks feature classic macOS red/yellow/green triple-dot headers and high-contrast syntax highlighting.
- 🔤 **Authentic Classical Typography** — Preserves the original font stack (`Bellota`, `Tw Cen MT`, `HYHuaGuan`, `霞鹜文楷`, `华文中宋`), with offline fonts bundled in the package.

---

## 📦 Usage & Installation

1. Download **[tailors.zip](https://github.com/ChiamZhang/tailors.theme.typora/raw/gh-pages/media/theme/tailors/tailors.zip)**.
2. In Typora, open the theme folder:
   - macOS: **Typora → Preferences → Appearance → Open Theme Folder**
   - Windows/Linux: **File → Preferences → Appearance → Open Theme Folder**
3. Extract `tailors.zip` and move the contents directly into the theme folder:
   - `tailors.css` (theme stylesheet)
   - `tailors/` (offline font directory)
4. Restart Typora, and select **Tailors** from the **Themes** menu.

---

## ⚙️ Customization

To customize the primary gradient, font stacks, or layout width, simply open `tailors.css` and adjust the variables defined in the `:root` block.
