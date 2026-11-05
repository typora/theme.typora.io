---
layout: theme
title: Tailors
category: theme
homepage: https://chiamzhang.github.io/tailors.theme.typora/preview.html
download: https://github.com/ChiamZhang/tailors.theme.typora/raw/gh-pages/media/theme/tailors/tailors.zip
author: ChiamZhang
thumbnail: tailors.png
preview: tailors.png
description: A refined Typora theme featuring soft neumorphic elegance, sunset-gradient capsule headings, unified seamless background, A4-native reading width, and publisher-grade PDF export.
tags: [light, neumorphism, gradient, a4, clean, modern, typography]
built-in: false
typora-root-url: ../../
typora-copy-images-to: ../../media/theme/tailors
---

# Typora-Theme-Tailors Introduction [中文版](https://github.com/ChiamZhang/tailors.theme.typora/blob/gh-pages/Typora-Theme-Tailors%20%E4%B8%AD%E6%96%87%E4%BB%8B%E7%BB%8D.md)

> A refined Typora theme featuring soft neumorphic elegance, sunset-gradient capsule headings, full-bleed icy blue background, and publisher-grade PDF export.

[🌐 Live HTML Preview](https://chiamzhang.github.io/tailors.theme.typora/preview.html) | [⬇️ Download Theme (tailors.zip)](https://github.com/ChiamZhang/tailors.theme.typora/raw/gh-pages/media/theme/tailors/tailors.zip) | [⭐ GitHub Repository](https://github.com/ChiamZhang/tailors.theme.typora)

---

## 💡 How to View & Experience This Theme

> [!IMPORTANT]
> **Please Note**: Viewing raw `.md` files directly on GitHub or in plain text editors **will not render custom CSS themes** (GitHub only displays default unstyled markdown).
> 
> To experience or share the full aesthetic of the Tailors theme:
> 1. **In Typora**: Install the theme and select **Tailors** from the **Themes** menu for a true WYSIWYG writing experience.
> 2. **Export to Standalone HTML or PDF**:
>    - **Export to HTML**: In Typora, click **File → Export → HTML (with styles)**. The resulting HTML file can be opened in any browser to showcase the sunset gradient headings, neumorphic badges, and typography.
>    - **Export to PDF**: In Typora, click **File → Export → PDF** with seamless background printing and native A4 page layout.

---

## Introduction

This theme is inspired by my two favorite themes:

1. **Phycat** by XuJilong. Homepage: [GitHub - sumruler/typora-theme-phycat](https://github.com/sumruler/typora-theme-phycat) — *Mainly referencing the title system and sunset gradient capsule badges.*
2. **Typora-Theme-Neumorphism** by Soanguy. Homepage: [GitHub - Soanguy/Typora-Theme-Neumorphism](https://github.com/Soanguy/Typora-Theme-Neumorphism) — *Mainly referencing the soft neumorphic inline styling.*
3. I changed a lot of the colors and unnecessary hover CSS to make the overall style more compatible and pleasant for long reading. Since Soanguy hasn’t updated for a long time, I encountered some bugs while using it, which I fixed.
4. Continuous updates — if there are any issues, please feel free to raise them in the issue section, and I will fix them when I have time.
5. **Tailors** means that I have patched together this theme from various sources, feeling a bit embarrassed yet proud to share it with everyone!

---

## ✨ Features & Enhancements

- 🎨 **Full-Bleed Icy Blue Canvas** — The entire window and export output share the soothing `#F9FCFF` tone, completely eliminating harsh white cutouts.
- 📐 **Aligned with Typora Official Standards** — 
  - Standard `860px` max reading width with `30px` padding and `100px` bottom scroll padding.
  - Automatically expands to `1024px` on wide screens (>1400px) and `1200px` on ultra-wide screens (>1800px), matching GitHub and Night themes.
- 🖨️ **Publisher-Grade PDF Export** — Full-bleed zero-margin printing with no white borders, no distracting blue link underlines, and intelligent page-break handling.
- 💻 **macOS-Style Code Blocks** — Fenced code blocks feature classic macOS red/yellow/green triple-dot headers and high-contrast syntax highlighting.
- 🔤 **Authentic Classical Typography** — Preserves the original font stack (`Bellota`, `Tw Cen MT`, `HYHuaGuan`, `霞鹜文楷`, `华文中宋`), with offline fonts bundled in the package.
- 🚫 **Distraction-Free Experience** — Cleaned up table row hover jumpers and removed extraneous decorative shapes.

---

## 📦 Usage & Installation

1. Download **[tailors.zip](https://github.com/ChiamZhang/tailors.theme.typora/raw/gh-pages/media/theme/tailors/tailors.zip)**.
2. In Typora, click **Preferences → Appearance → Open Theme Folder**.
3. Extract `tailors.zip` and place:
   - `tailors.css`
   - `tailors` folder (offline fonts)
   
   directly into your Typora theme folder.
4. Restart Typora or select **Tailors** from the **Themes** menu.

---

## 🎨 Theme Visual Preview

Here is a full-length rendering of the Tailors theme in action. (You can also view the [Live HTML Rendering](https://chiamzhang.github.io/html/Typora-Theme-Tailors%20%20Introduction.html)):

![Tailors Full Preview](https://camo.githubusercontent.com/331531fc9fec0560bbbc2c95516dca6bc291a9a6e2db473c25b32acbe906a29d/68747470733a2f2f696d67322e62616964752e636f6d2f69742f753d333031323938343238332c38373937303731393126666d3d32353326666d743d6175746f266170703d31333826663d4a5045473f773d38303026683d31323030)

---

## ⚙️ Customization

Personalization can be done by modifying the CSS variables in the `:root` module inside `tailors.css`.
