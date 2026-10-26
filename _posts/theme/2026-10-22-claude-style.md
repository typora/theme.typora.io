---
layout: theme
title: "Claude Style"
category: theme
homepage: "https://github.com/Xv-Bowen/Claude-Style-Typora"
download: "https://github.com/Xv-Bowen/Claude-Style-Typora/releases/latest"
author: "Xv-Bowen"
author_url: "https://github.com/Xv-Bowen"
thumbnail: "claude-style.png"
tags: [light, dark, clean, cjk]
built-in: false
typora-root-url: ../../
typora-copy-images-to: ../../media/theme/claude-style
---

# Claude Style

A light and a dark theme that make your documents read like a reply in Claude. The text, code and tables follow Claude's chat view, alerts follow the way Claude shows a document, a file linked on its own becomes the card Claude shows for a file it shares, and Typora's own interface (sidebar, menus, floating toolbar, find bar, dialogs) takes on Claude's look as well.

## Light

![](/media/theme/claude-style/preview-light.png)

## Dark

![](/media/theme/claude-style/preview-dark.png)

## File cards

Files linked in paragraphs of their own, in the light and the dark theme:

![](/media/theme/claude-style/file-cards-light.png)

![](/media/theme/claude-style/file-cards-dark.png)

## What it covers

- **Reading:** Claude's text size, line spacing and heading scale; links, quotes, lists, tables, keycaps, task lists and footnotes as in Claude.
- **Code:** Claude's code card with a language label and Claude's syntax colours; inline code as in Claude.
- **Math, alerts and diagrams:** formulas at the same size as in Claude, GitHub alerts the way Claude shows them in a document, Mermaid diagrams in Claude's colours.
- **File links:** a file linked in a paragraph of its own shows as the card Claude draws for a file it shares, coloured by the kind of file, with its icon, name, kind and extension. Command-click (Ctrl-click on Windows and Linux) opens it; put the caret in it to edit the link. Links to web pages, mail addresses, a place in the document or a part of a file stay links. HTML and PDF exports draw no cards: file links are plain links there.
- **Pictures:** when the text cursor moves onto a picture (click it, or reach it with the arrow keys), the picture is shown enlarged in the middle of the window with the rest of the window dimmed and a close button at its top right, as Claude shows a picture.
- **Sidebar:** file tree, outline and search in the look of Claude's sidebar, with its menus. Under the Files / Outline switch sit a search field and a New row, as at the top of Claude's sidebar (they read 搜索 and 新建 in Chinese, Search and New in English, and Typora's own words in other languages), and a heading reading 项目列表 ("project list"; it is in Chinese whatever language Typora is set to) stands over the files. On the Mac, the bar at the foot of the sidebar always shows. The sidebar search opens as a card in the middle of the window, like Claude's search, with the rest of the window dimmed; at its foot it names the keys that work there, with the search options on the right.
- **Floating toolbar:** the look of Claude's review bar; its buttons, menus and submenus open and behave the way Claude's do, and the heading levels sit in a submenu of Paragraph.
- **Find and quick open:** the find and replace bar is a card at the top right of the page, as Claude's find bar is. Quick open stands where Claude's search does, with the rest of the window dimmed, one line for each result (its icon, its name and its folder) and the matches in bold; at its foot it names the keys that work there.
- **Dialogs, outline window and file preview:** dialogs, notifications and tooltips in Claude's look; the floating outline window as the outline card of a Claude document; the file preview's header and Open with button as in Claude's document panel.
- **Modes and motion:** source mode as a plain code view; focus mode dims the other blocks to Claude's muted text colour; only what moves in Claude moves.
- **Export:** HTML and PDF use the same styles as the editor (file cards are drawn in the editor only).

The theme prefers Anthropic Serif, Anthropic Sans and JetBrains Mono NL when they are installed and falls back to Times New Roman, the system fonts and PingFang SC (Microsoft YaHei on Windows). No font is bundled or downloaded.

## Installation

1. Download `claude-style-light.css` and `claude-style-dark.css` from the [latest release](https://github.com/Xv-Bowen/Claude-Style-Typora/releases/latest).
2. In Typora, open **Settings → Appearance → Open Theme Folder** and copy both files there.
3. Quit and reopen Typora, then choose **Claude Style Light** or **Claude Style Dark** from the **Themes** menu.

Carefully designed on the Mac and thoroughly tested on macOS, Windows and Linux.

Claude Style is an independent theme. It is not made, endorsed or supported by Anthropic, and it contains no fonts, icons or other files from Anthropic. Claude is a trademark of Anthropic.
