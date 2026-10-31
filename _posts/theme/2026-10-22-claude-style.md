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
- **Code:** Claude's code card with a language label and Claude's syntax colours, and a copy button at its top right while the pointer is on it (it works with the enhancement script); inline code as in Claude.
- **Math, alerts and diagrams:** formulas at the same size as in Claude, GitHub alerts the way Claude shows them in a document, Mermaid diagrams in Claude's colours.
- **File links:** a file linked in a paragraph of its own shows as the card Claude draws for a file it shares, coloured by the kind of file, with its icon, name, kind and extension. Command-click (Ctrl-click on Windows and Linux) opens it; put the caret in it to edit the link. Links to web pages, mail addresses, a place in the document or a part of a file stay links. HTML and PDF exports draw no cards: file links are plain links there (with the enhancement script's export snippet, exports draw them too).
- **Pictures:** when the text cursor moves onto a picture (click it, or reach it with the arrow keys), the picture is shown enlarged in the middle of the window with the rest of the window dimmed and a close button at its top right, as Claude shows a picture.
- **Sidebar:** file tree, outline and search in the look of Claude's sidebar, with its menus. Under the Files / Outline switch sit a New row and a Search row, as at the top of Claude's sidebar (they read 新建 and 搜索 in Chinese, New and Search in English, and Typora's own words in other languages), and a heading reading 项目列表 ("project list"; it is in Chinese whatever language Typora is set to) stands over the files. On the Mac, the bar at the foot of the sidebar always shows. The bar at the foot of the sidebar has no switch between the file tree and the article list; switch with View → File Tree or View → Articles. At the right of the bar at the foot of the sidebar, a lock shows whether the document is in Read-Only Mode (View → Readonly Mode): open while you can edit, shut and shown pressed while the mode is on. Without the enhancement script, clicking it does nothing; with the script, a click switches the mode. A name too long for its row fades out at the end, as in Claude's sidebar. The sidebar search opens as a card in the middle of the window, like Claude's search, with the rest of the window dimmed; at its foot it names the keys that work there, with the search options on the right.
- **Floating toolbar:** the look of Claude's review bar; its buttons, menus and submenus open and behave the way Claude's do, and the heading levels sit in a submenu of Paragraph.
- **Find and quick open:** the find and replace bar is a card at the top right of the page, as Claude's find bar is. Quick open stands where Claude's search does, with the rest of the window dimmed, one line for each result (its icon, its name and its folder) and the matches in bold; at its foot it names the keys that work there.
- **Dialogs, outline window and file preview:** dialogs, notifications and tooltips in Claude's look; the floating outline window as the outline card of a Claude document; the file preview's header and Open with button as in Claude's document panel.
- **Modes and motion:** source mode as a plain code view; focus mode dims the other blocks to Claude's muted text colour; only what moves in Claude moves.
- **Export:** HTML and PDF use the same styles as the editor (file cards are drawn in the editor only, and in exports too with the enhancement script's export snippet).

The theme prefers Anthropic Serif, Anthropic Sans and JetBrains Mono NL when they are installed and falls back to Times New Roman, the system fonts and PingFang SC (Microsoft YaHei on Windows). No font is bundled or downloaded.

Since the 1.2 series, the theme follows the desktop app's new interface in its sizes, spacing, corners, type, layout and icons, but not in everything: the new interface also made secondary text and dividing lines fainter, took the red and the border away from inline code and the border and header fill away from tables, and turned file cards into one-line rows, which makes documents harder to read. So the 1.2 series keeps the colours of the 1.1 series, its tables, its red and bordered inline code and its file cards coloured by the kind of file. The one colour taken from the new interface is in the sidebar: file names and their extensions, outline headings, New and Search, the 项目列表 heading and the folder's name in the footer are always in the colour of the body text. The 1.1 series is no longer updated, and moving to the 1.2 series is recommended; its releases stay on the [releases page](https://github.com/Xv-Bowen/Claude-Style-Typora/releases).

## Installation

1. Download `claude-style-light.css` and `claude-style-dark.css` from the [latest release](https://github.com/Xv-Bowen/Claude-Style-Typora/releases/latest).
2. In Typora, open **Settings → Appearance → Open Theme Folder** and copy both files there.
3. Quit and reopen Typora, then choose **Claude Style Light** or **Claude Style Dark** from the **Themes** menu.

## Enhancement script (optional)

The same release has `claude-style-enhance.zip`, an optional script that adds what a theme cannot do: a picture viewer that zooms and drags, file names and picture thumbnails on file cards, clicks on the code cards' copy button and on the sidebar's lock (the theme draws both, the script makes them work), a sidebar search that finds as you type, with no repeated words in its results, a top folder that folds, and file cards in exported HTML and PDF. It comes with installers for macOS, Windows and Linux; the [README](https://github.com/Xv-Bowen/Claude-Style-Typora#enhancement-script-optional) says how to install it, with or without the installers. Without the script, the theme works as described above, except that the copy button and the lock do nothing when clicked. The script is made for the 1.2 series only: script 0.1.3 and later need Claude Style 1.2.3 or later, and with an older theme (the 1.1 series included) the script does nothing. Scripts 0.1.5 (from Claude Style 1.2.5), 0.1.4 (in Claude Style 1.2.4), 0.1.3 (in Claude Style 1.2.3) and 0.1.1 (in Claude Style 1.2.2) are adapted to Typora 1.14.15, and 0.1.0 (in Claude Style 1.2.1) to Typora 1.14.10. The script works by hooking into Typora's own code, so a later version of Typora may need an update of the script.

Carefully designed on the Mac and thoroughly tested on macOS, Windows and Linux.

Claude Style is an independent theme. It is not made, endorsed or supported by Anthropic, and it contains no fonts, icons or other files from Anthropic. Claude is a trademark of Anthropic.
