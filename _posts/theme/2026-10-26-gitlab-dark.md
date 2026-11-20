---
layout: theme
category: theme
title: "GitLab Dark"
author: "githubcreaker"
author_url: "https://github.com/githubcreaker"
thumbnail: "gitlab-dark.png"
homepage: "https://github.com/githubcreaker/typora-theme-gitlab-dark"
download: "https://github.com/githubcreaker/typora-theme-gitlab-dark/archive/refs/heads/main.zip"
built-in: false
description: "Renders Markdown the way gitlab.com does in dark mode: GitLab Sans and GitLab Mono, the Pajamas palette, and spacing measured from gitlab.com."
tags: [dark, gitlab, code, clean]
---

# GitLab Dark

A dark theme that renders Markdown the way gitlab.com does in its dark UI mode. Typography, spacing, colors, and the styling of tables, alerts and block quotes were measured from the computed styles of rendered Markdown on gitlab.com.

![GitLab Dark](https://raw.githubusercontent.com/githubcreaker/typora-theme-gitlab-dark/main/screenshot.png)

## Features

- **GitLab typography**: GitLab Sans for text and GitLab Mono for code, at gitlab.com's 14px base size and heading scale. The fonts are bundled, so the theme works offline.
- **Pajamas dark palette**: the background, text, border and link colors from GitLab's design system.
- **Code**: inline code chips, fenced code blocks with Tomorrow Night syntax colors, and a dark source mode.
- **Tables**: an inner grid inside a rounded outer frame, with a semibold header row.
- **Alerts**: `> [!NOTE]`, `[!TIP]`, `[!IMPORTANT]`, `[!WARNING]` and `[!CAUTION]` use GitLab's colors.
- **Task lists, footnotes, math and Mermaid diagrams** are all styled to match.
- **App interface**: sidebar, file tree, outline, menus, dialogs and scrollbars use the same palette.

## Installation

1. Download and extract the repository archive.
2. In Typora, open **Preferences → Appearance → Open Theme Folder**.
3. Copy `gitlab-dark.css` **and** the `gitlab-dark/` folder into the theme folder.
4. Restart Typora and choose **Gitlab Dark** from the **Themes** menu.

Designed and tested with Typora 1.14 on macOS. The theme includes styles for the Windows/Linux title bar and menu, but those have not been tested.

The bundled GitLab Sans and GitLab Mono fonts come from GitLab's `@gitlab/fonts` package and are licensed under the SIL Open Font License 1.1. This is an unofficial theme, not affiliated with GitLab Inc.
