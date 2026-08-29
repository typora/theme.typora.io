---
layout: theme
title: GitHub Dark Vanilla
category: fork
homepage: https://github.com/bailitaotao/typora-github-dark-vanilla-theme
download: https://github.com/bailitaotao/typora-github-dark-vanilla-theme/blob/main/github-dark-vanilla.css
author: tim
thumbnail: https://github.com/bailitaotao/typora-github-dark-vanilla-theme/assets/thumbnail.png
typora-root-url: ../../
typora-copy-images-to: ../../media/theme/github-dark-vanilla
---

# Github Dark Vanilla
![thumbnail](https://github.com/bailitaotao/typora-github-dark-vanilla-theme/assets/thumbnail.png)

## Description

Add a dark version of vanilla GitHub theme default in Typora.

This theme only changes colors.
No structure, typography layout, spacing, or component behavior is changed.

## Compatibility

Designed and tested on macOS.
Expected to work on Windows/Linux with Typora theme engine compatibility.

## Install

1. Open Typora Preferences.
2. Go to Appearance.
3. Click Open Theme Folder.
4. Put github-dark-vanilla.css into the theme folder.
5. Restart Typora and select github-dark-vanilla.

## Preview

![Screenshot 1](https://github.com/bailitaotao/typora-github-dark-vanilla-theme/assets/Screenshot%202026-03-26%20at%2001.14.15.png)

![Screenshot 2](https://github.com/bailitaotao/typora-github-dark-vanilla-theme/assets/Screenshot%202026-03-26%20at%2001.14.22.png)

![Screenshot 3](https://github.com/bailitaotao/typora-github-dark-vanilla-theme/assets/Screenshot%202026-03-26%20at%2001.14.29.png)


## What Changed

### 1. Global Variables and App Surface

- `--side-bar-bg-color`: `#fafafa` -> `#1b1e21`
- `--control-text-color`: `#777` -> `#8b949e`
- Added `--active-file-bg-color: #2a2d2f`
- Added `--item-hover-bg-color: #282c2e`
- Added `--select-text-bg-color: #3f638b`
- Added root `background-color: #1f2325`

### 2. Main Typography and Headings

- Body text: `rgb(51, 51, 51)` -> `rgb(201, 209, 217)`
- Link color: `#4183C4` -> `#58a6ff`
- `h1/h2` bottom border: `#eee` -> `#343739`
- `h6` text color: `#777` -> `#8b949e`

### 3. Dividers, Quotes, and Tables

- `hr` background: `#e7e7e7` -> `#2d3133`
- Blockquote border: `#dfe2e5` -> `#343739`
- Blockquote text: `#777777` -> `#8b949e`
- Table borders: `#dfe2e5` -> `#343739`
- Table striped/header background: `#f8f8f8` -> `#282c2e`

### 4. Inline Code and Code Blocks

- Code tooltip shadow: `rgba(0,28,36,.3)` -> `rgba(1, 4, 9, .6)`
- Code tooltip top border: `#eef2f2` -> `#343739`
- `code/tt/.md-fences` border: `#e7eaed` -> `#343739`
- `code/tt/.md-fences` background: `#f8f8f8` / `#f3f4f4` -> `#282c2e`
- Meta block background: `#f7f7f7` -> `#282c2e`
- Meta block text: `#777777` -> `#8b949e`
- Math inline background: `#fafafa` -> `#282c2e`

### 5. Sidebar and Quick Open UI

- Quick open border: `#ddd` -> `#343739`
- Quick open panel background: `#f8f8f8` -> `#282c2e`
- Quick open item background: `#FAFAFA` -> `#1f2325`
- Quick open item border-color: `#FEFEFE #e5e5e5 #e5e5e5 #eee` -> `#343739 #2d3133 #2d3133 #343739`
- Seamless sidebar background: `#fafafa` -> `#1b1e21`

### 6. Preferences and Menu Components

- Dropdown divider: `#e5e5e5` -> `#343739`
- Preferences window background: `#fafafa` -> `#1f2325`
- Active nav item background: `#999` -> `#2a2d2f`
- Active nav item text: `white` -> `#f0f6fc`
- Menu style button background: `#f5f8fa` -> `#282c2e`

### 7. Tags, Language Label, and Focus Mode

- Tag color: `#a7a7a7` -> `#6e7681`
- Code language label color: `#b4654d` -> `#ffa657`
- Focus mode blockquote border-left-color: `rgba(85, 85, 85, 0.12)` -> `#343739`

### 8. Added Syntax Highlight Palette (New Block)

`github-dark-vanilla.css` adds a dedicated CodeMirror token palette section not present in `github.css`, including:

- Editor selection and cursor adjustments for dark background
- Token colors for `.cm-keyword`, `.cm-string`, `.cm-comment`, `.cm-tag`, `.cm-number`, etc.
- Error token styling (`.cm-error`) with high-contrast foreground/background
- Added gutter styling: dark background (`#282c2e`) and right border (`#343739`)
