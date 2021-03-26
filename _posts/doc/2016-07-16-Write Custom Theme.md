---
layout: post
title: Write Custom Theme for Typora
category: doc
author: typora.io
typora-root-url: ../../
---

## Translations

[简体中文](/doc/zh/Write-Custom-Theme/)，[繁體中文](https://pjchender.github.io/2018/04/24/note-%E5%A6%82%E4%BD%95%E7%82%BA-typora-%E6%92%B0%E5%AF%AB%E5%AE%A2%E8%A3%BD%E5%8C%96%E6%A8%A3%E5%BC%8F/)

## Update -- CSS Variables

Overwriting existing [CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables) is more recommended if you want to define fonts, colors, backgrounds. Earlier versions of macOS/Safari does not support this, but it is still much easier to use. Common used ones are: 

```css
:root {
   --bg-color:  #ffffff; /*change background*/
   --text-color: #333333; /*change text color*/
   --md-char-color: #C7C5C5; /*change color of meta characetrs like `*` in markdown */
   --meta-content-color: #5b808d; /*change color of meta contents like image text or link address in markdown */

   --primary-color: #428bca; /* color of primary buttons */
   --primary-btn-border-color: #285e8e;
   --primary-btn-text-color: #fff;

   --window-border: 1px solid #eee; /*border for sidebar, etc*/

   --active-file-bg-color: #eee; /*background color if list item in file tree or file list*/
   --active-file-text-color: inherit;
   --active-file-border-color: #777;

   --side-bar-bg-color: var(--bg-color); /*change background of sidebar*/
   --item-hover-bg-color: rgba(229, 229, 229, 0.59); /*background of control items when hover, like menu in sidebar*/
   --item-hover-text-color: inherit;
   --monospace: monospace; /*monospace font for codes, fences*/
}
```

The variables may change in future, so you [could use DevTools in Typora to confirm it](#test-in-typora). 


## Summary

If you want to write a custom CSS theme for Typora, all you need to do is:

1. Create a new css file. The file name **should not include capitalised characters or whitespace**, for example: `my-typora-theme` is a valid file name.

2. Write the css file. 

   We prepared a [toolkit][toolkit] for you to get started or to do simple testing. 

   If you want to write one from scratch, pick the template.less, and fill it.

   If you want to convert existing css files (from Wordpress or Jekyll theme), just copy the content, and then add styles those css files did not cover, like styles for "toc" or for UI components. 

3. Tweak/Debug css classes and styles. 

   You could also follow [how to install custom theme][install-theme] to install and use the theme and test it with Typora.
   
   To debug CSS in Typora like in Safari or Chrome, you could enable debug mode from help menu (macOS) or from preferences panel (macOS/Linux/Windows) and find & click "Inspect Elements" from context menu, which will pop up the [DevTools](https://developer.chrome.com/devtools) like Safari or Chrome browser. On Linux/Windows version, you could toggle it from `View` menu or just press `F12`.
   
   You could also put the css file you created into toolkit/theme/test.css along with resources like image or font it uses. And open html files under toolkit/core and toolkit/electron to preview your css. Please preview the html files using Safari on Mac or Chrome on Linux/Windows. 

4. If you want to share your theme, just make a fork and make a pull request to [Typora Theme Gallery](https://github.com/typora/typora-theme-gallery).

## Basic Rules

1. File naming rule for theme css: Do not use capitalized letters, and please replace whitespace with `-`, and Typora will convert them to readable label in menu item. For example, for `my-first-typora-theme.css`, Typora will put an menu item "My First Typora Theme" under "Themes" menu.
2. Put default font size into `html`, then for elements like `h1` or `p`, use `rem` for their `font-size` property, or else custom font size in preference panel will not work.
3. Use tag as selectors if possible. For example, for `### heading 3`, use `h3` instead of `h3.md-header`, because for any markdown render, "### heading 3" will be converted to `h3` tag. And for typora, we will keep as less html attributes (including class) as possible just like other markdown convertors. You could limit `h3` in writing area by `#write h3` selector. 
4. Typora is created upon Webkit (on macOS) or Chromium (on Windows/Linux), so please use css properties supported by Chrome or Safari (aka Webkit).
5. Some modifications of CSS may cause Typora not to work as expected, for example, adding `white-space: pre-wrap;` to selector `#write` will make  `\t` cannot be inserted by pressing Tab key, so please overwrite default css styles as less as possible, test it out.

---

Table of Contents:

* Outline
{:toc}

## Changes and Updates

None

## Which CSS selector should I use?

### General

The window content of Typora is a webpage, so please put `background`, `font-family` or other general properties into the `html` tag. *On mac, if seamless window style is used, then the background color of the toolbar is defined by the `background-color` style of the `html`*.

The writing area is a div with id `#write`, change the `width`, `height`, `padding` will adjust the size of the writing area. The properties you set, for example, `color` for `html`, will apply to whole window content, including UI parts, like the font-color in insert table dialog, so if you just want to change the style of the writing content not the UI controller part, you could put them under `#write` selector.

```css
/** example **/
html, body {
  background-color: #fefefe; /*background color of the window and titlebar*/
  font-family: helvetica, sans-serif; /*custom font*/
  ...
}

html {
  font-size: 14px; /*default font size*/
}

#write {
  max-width: 90%; /*adjust size of the wriring area*/
  font-size: 1rem; /*basic font size*/
  color: #555; /*basic font color*/
  ...
}
```



Typora will try to render all elements as other output, so, paragraphs are wrapped by `<p>` tag, lists are wrapped by `<ul>` or `<ol>` just like they are parsed by other Markdown processors, so you could change their styles by applying css styles to those HTML tags. Also, because of these, css files created for Wordpress or other static sites would also affect most styles in typora, therefore you would direct "borrow" css rules from them, and add missing part or do some adjustment.

### Block Elements

As I wrote, Typora will try to render all elements as other output, for instance, `<p>` for paragraph, `<table>` for tables, `<h1>` for 1st level headings, etc, so you could change most typesetting by writing styles like:

```css
p {...}
h1 {...}
table {...}
table th td {...}
table tr:nth-child(2n) td {...}
...
```

You could add `#write` as ancestor selector to make the style only apply to the writing area, without affecting control component (For instance, title in some dialogs may also be wrapped by `h4` tag).

```css
/*this will only aplly to h4 in dialogs popped up by typora (just an example)*/
.dialog h4 {...} 

/*this will only apply to h4 inside writing area, which is generated after user input "#### " */
#write h4 {...} 
```

Aslo, all block elements has a `mdtype` attribute. For example, you could also select headings by selector `[mdtype="heading"]`. Possible type includes `paragraph`, `heading`, `blockquote`, `fences`, `hr`, `def_link`, `def_footnote`, `table`, `meta_block`, `math_block`, `list`, `toc`, `list_item`, `table_row`, `table_cell`, `line`. But in most cases, tag selector is enough.

| mdtype                                   | Output Css Selector                      | Explanation                              |
| :--------------------------------------- | :--------------------------------------- | :--------------------------------------- |
| paragraph                                | p                                        |                                          |
| line                                     | .md-line                                 | A paragraph can contain one or more `.md-line` |
| heading                                  | h1~h6                                    |                                          |
| blockquote                               | blockquote                               |                                          |
| list (unordered list)                    | ul li                                    |                                          |
| list (ordered list)                      | ol li                                    |                                          |
| list (task)                              | ul.task-list li. task-list-item          |                                          |
| toc                                      | .md-toc                                  | Also refer to [this doc][toc]            |
| fences (before codemirror is initialized) | pre.md-fences.mock-cm                    |                                          |
| fences                                   | pre.md-fences                            | please refer to "Code Fences" section    |
| diagrams                                 | pre[lang='sequence'], pre[lang='flow'], pre[lang='mermaid'] | They are special code fences with certain code language. |
| hr                                       | hr                                       |                                          |
| def_link                                 | .md-def-link                             | with children `.md-def-name`, `.md-def-content`, `.md-def-title` |
| def_footnote                             | .md-def-footnote                         | with children `.md-def-name`, `.md-def-content` |
| meta_block                               | pre.md-meta-block                        | content for YAML front matters           |
| math_block                               | [mdtype="math_block"]                    | preview part is `.mathjax-block`, html content is generated via [MathJax][]. TeX editor is powered by [CodeMirror][], please refer to "Code Fences" section |
| table                                    | table thead tbody th tr td               |                                          |



#### Lines

Typora will render hard line break as-is. Therefore, a paragraph may contain multiple lines split by `\n`, and `.md-line` selector is used for each "line" inside a `<p>`.

#### Code Fences

Syntax highlight is enabled by [CodeMirror][]'s feature. Please refer to [this doc][Code-Block-Styles] for detail.

#### Mermaid

Examples: [mermaid.css](https://github.com/knsv/mermaid/blob/master/dist/mermaid.css), [mermaid.dark.css](https://github.com/knsv/mermaid/blob/master/dist/mermaid.dark.css), [mermaid.forest.css](https://github.com/knsv/mermaid/blob/master/dist/mermaid.forest.css).

### Inline Elements

Inline elements are also rendered as it is rendered by most markdown parsers. So following could work:

```css
strong {
  font-weight: bold;
}
em {..}
code {..}
a {..}
img {..}
mark {..} /*highlight*/
```

An inline elements usually includes a wrapper span, meta syntax, and output inline element, for example `**strong**` will be rendered as

```html
<!--wrapper for strong element-->
<span md-inline="strong" class=""> 
  
  <!--meta syntax for strong element-->
  <span class="md-meta md-before">**</span> 
  
    <!--output for strong element-->
    <strong>
      <!--inner output-->
      <span md-inline="plain">strong</span> 
    </strong>
  
   <!--meta syntax for strong element-->
  <span class="md-meta md-after">**</span>
</span>
```

As you can see, the full part of an inline element is wrapped by a `span` with an `md-inline` attribute indicates the type info of the parse result. Possible attribute includes (some inline syntax need to be enabled from preference panel):

| `md-inline` | syntax                            | Output Tag |
| :---------- | :-------------------------------- | :--------- |
| plain       | `plain`                           | `span`     |
| strong      | `**strong**`                      | `strong`   |
| em          | `*em*`                            | `em`       |
| code        | <code>`code`</code>               | `code`     |
| underline   | `<u>underline</u>`                | `u`        |
| escape      | `\(`                              | `span`     |
| tag         | `<button>`                        |            |
| del         | `~~del~~`                         | `del`      |
| footnote    | `^1`                              | `sup`      |
| emoji       | `:smile:`                         | `span`     |
| inline_math | `$x^2$`                           | `span`     |
| subscript   | `~sub~`                           | `sub`      |
| superscript | `^sup^`                           | `sup`      |
| linebreak   | (two whitespace at end of a line) |            |
| highlight   | `==highlight==`                   | `mark`     |
| url         | `http://typora.io`                | `a`        |
| autolink    | `<http://typora.io>`              | `a`        |
| link        | `[link](href)`                    | `a`        |
| reflink     | `[link][ref]`                     | `a`        |
| image       | `![img](src)`                     | `img`      |
| refimg      | `![img][ref]`                     | `img`      |

Following are explanations about how Typora style inline markdown syntax such as `*` or `_`, which is hidden in most cases in Typora. Usually you do not need to set CSS rules for them specifically.

Meta syntax like `**` or `==` of those inline elements will disappear when you convert a markdown file to HTML. So they are wrapped by class `md-meta` and has style `display:none` by default. Some syntax like the markdown syntax for image will also be hidden by default, and they are wrapped by `md-content` class. When the cursor is inside those inline elements, the focused one will be wrapped by `md-expand` class, then `.md-meta` and `.md-content` will become visible. So, apply styles to `.md-meta` and `.md-content` if you want to modify the style of those meta syntax.

### Source Code Mode

SourceCode Mode is also powered by [CodeMirror][], so the class it uses for syntax highlight is same as code fences ([detail here][Code-Block-Styles]). Please note that code fences use codemirror theme `.cm-s-inner`, while in source code mode, codemirror theme is `.cm-s-typora-default`. So the CSS is like:

```css
.cm-s-typora-default .cm-header {
  /*styles for h1~h6 in source code mode*/
}
```

### Focus Mode

For this topic, please refer to [this doc][focus mode]

#### Custom Font

For this topic, please refer to [this doc][custom-font].

### Background

For this topic, please refer to [this doc][background].

### Controller UI

Most UI components including tooltip, dialog and buttons are painted by HTML. And you only need to change those part when you find the UI components are incompatible with your editor theme after finishing steps above. HTML files from the [toolkit][] includes most common UI components for you to easily debug.

### Additional UI for Windows/Linux

The Windows/Linux version of typora use much more HTML-powered components than macOS version, including context menu, preference panel, and even window frame itself if you use "unibody" window style on Windows. 

HTML files from the [toolkit][] could include most common UI components for you to easily debug.

### Print

Write css inside following block will make them only change the style of printed one or exported PDF.

```css
@media print {
    /* for example: */
    .typora-export * {
        -webkit-print-color-adjust: exact;
    }
    /* add styles here */
}
```

## Debug and Test

### Test in Browser

We provide some html files under `html-preview` folder from the [toolkit][] to preview your theme from Safari or Chrome. To use them, please rename and put your css file into `html-preview/theme/test.css`. 

### Test in Typora

Follow [this doc][install-theme] to learn about how to install a theme into Typora. 

Then for mac users, check `enable debug mode` from help menu, then click "Inspect Element" from context menu to pop up DevTools.

For Windows/Linux users, you could pop up the DevTools from `Toggle DevTools` from view menu.

## Tips and References on custom style

Related documents are [here](http://support.typora.io/style). 

Please make a pull request to [typora-wiki-site](https://github.com/typora/wiki-website) if you have some tips to share.



[CodeMirror]: http://codemirror.net
[custom-font]: https://support.typora.io/Custom-Font/
[focus mode]: https://support.typora.io/Change-Styles-in-Focus-Mode/
[Code-Block-Styles]: https://support.typora.io/Code-Block-Styles
[MathJax]: http://www.mathjax.org
[background]: https://support.typora.io/Backgound/

[install-theme]: /doc/Install-Theme/
[typora-theme-gallery]: https://github.com/typora/typora-theme-gallery
[toolkit]: https://github.com/typora/typora-theme-toolkit
