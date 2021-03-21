---
permalink: /doc/zh/Write-Custom-Theme/
---

## 更新 CSS 变量

如果你想定义字体、颜色或背景，建议覆盖现有的[ CSS 变量](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables)。macOS / Safari 的早期版本不支持这样做，但是它仍然更容易使用。常用的有:

```css
:root {
   --bg-color:  #ffffff; /*改变背景色*/
   --text-color: #333333; /*改变文字颜色*/
   --md-char-color: #C7C5C5; /*改变元字符的颜色，例如 markdown 中的“*”*/
   --meta-content-color: #5b808d; /*改变元内容的颜色，例如 markdown 中的图像文本和链接地址*/

   --primary-color: #428bca; /*主按钮的颜色*/
   --primary-btn-border-color: #285e8e;
   --primary-btn-text-color: #fff;

   --window-border: 1px solid #eee; /*边栏等的边框*/

   --active-file-bg-color: #eee; /*文件树或文件列表中当前项的背景色*/
   --active-file-text-color: inherit;
   --active-file-border-color: #777;

   --side-bar-bg-color: var(--bg-color); /*改变边栏颜色*/
   --item-hover-bg-color: rgba(229, 229, 229, 0.59); /*鼠标悬停时控件项的背景，如侧边栏中的菜单*/
   --item-hover-text-color: inherit;
   --monospace: monospace; /*代码的等宽字体*/
}
```

变量将来可能会发生更改，你可以使用[ Typora 的 DevTools](#在-Typora-中测试) 来确认其是否可用。

## 概述

如果你想为 Typora 编写一个 CSS 主题，你只需要:

1. 创建一个新的 CSS 文件。

   文件名**不应该包含大写字符或空格**，例如：` my-typora-theme `是一个有效的文件名。

2. 编写 CSS 文件。

   我们为你准备了一个[工具箱][toolkit]，以便进行简单的测试。

   如果你想从头开始编写，可以将工具箱中的 template.less 作为模板。

   如果你想在已存 CSS 文件(来自 Wordpress 或 Jekyll 主题) 的基础上进行修改，只需复制内容，然后补充那些 CSS 文件没有覆盖的样式，比如“ toc ”或 UI 组件的样式。

3. 调整/调试 CSS 类和样式。

   你也可以使用 Typora 对主题进行测试，如何在 Typora 中安装主题见[如何安装自定义主题][install-theme]。

   要想像在 Safari 或 Chrome 里一样在 Typora 上调试 CSS，需要从帮助菜单(macOS)中启用调试模式，然后从上下文菜单中找到并单击“检查元素”，这将使 Typora  像 Safari 或 Chrome 那样弹出 DevTools。

   > **注**：在 Linux/Windows 版本中，你需要从偏好设置中启用调试模式，然后在“视图”菜单中打开开发者模式(或者按`F12 `)。

   你还可以将你创建的 CSS 文件以及它所使用的图像、字体等资源放入 toolkit/theme 中。并在 toolkit/core 和 toolkit/electron 下打开 html 文件以预览 CSS 效果（请使用 Mac 上的 Safari 或 Linux/Windows 上的 Chrome 预览）。​​

4. 如果你想分享你的主题，只需给 [Typora Theme Gallery][typora-theme-gallery] 提 PR。

## 基本规则

1. 主题 CSS 的文件命名规则：请勿使用大写字母，并将空格替换为`-`，Typora 会将其转换为菜单项中的可读标签。例如，对于`my-first-typora-theme.css`，Typora 将在“主题”菜单下生成一个菜单项“my first typora theme”。
2. 将默认字体大小放入` html `中，然后将` rem `用作` h1 `及` p `这类元素的` font-size `属性，否则偏好设置面板中的自定义字体大小将不起作用。
3. Typora 是基于 Webkit（macOS ）及 Chromium（Windows / Linux）创建的，因此请使用 Chrome 及 Safari（又名Webkit）支持的 CSS 属性。
4. CSS 的某些修改可能会导致 Typora 无法按预期工作，例如，添加`white-space: pre-wrap;`到选择器` #write `将导致无法通过按 Tab 键插入`\t`，因此请尽可能覆盖默认的 CSS 样式然后进行测试。

------

目录：

* Outline
{:toc}

## 更改和更新

无

## 如何确定 CSS 选择器

### 一般属性

Typora 的窗口内容是一个网页，因此请在` html `标签中添加`background`, `font-family`或其他一般属性。在 mac 上，如果使用无缝窗口样式，则工具栏的背景颜色由` html `的`background-color`属性定义。

写入区域是一个 id 为`#write `的 div 元素，改变`width`, `height`, `padding`属性可调整写入区域的大小。你设置的属性如` html `的`color` ，将应用于整个窗口内容（包括 UI 部分，例如插入表对话框中的字体颜色），因此如果你只想更改写入内容而不是 UI 部分的样式，你可以将它们置于` #write `选择器下。

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

Typora 将尝试将所有元素呈现为其他输出，因此，其他许多 Markdown 解析器类似，段落被 `<p>` 标记，列表被` <ul> `或 `<ol>` 标记，所以你可以通过对这些 HTML 标记应用 CSS 样式来改变它们的呈现效果。正因如此，为 Wordpress 或其他静态站点创建的 CSS 文件也会影响 Typora 中的大多数样式，因此你可以直接复制它们的 CSS 规则，然后添加缺少的内容或做一些调整。

### 块元素

正如前面所写的，Typora 将尝试将所有元素呈现为其他输出，例如，段落为 `<p>` 、表格为 `<table>`、第一级标题为 `<h1>` 等等，这样你就可以通过编写如下样式来更改大多数排版:

```css
p {...}
h1 {...}
table {...}
table th td {...}
table tr:nth-child(2n) td {...}
...
```

你可以添加 `#write` 作为祖先选择器，以使样式只适用于写入区域，而不影响控制组件（例如，某些对话框中的标题可能也由`h4`标记）：

```css
/*this will only aplly to h4 in dialogs popped up by typora (just an example)*/
.dialog h4 {...} 

/*this will only apply to h4 inside writing area, which is generated after user input "#### " */
#write h4 {...} 
```

另外，所有块元素都有一个`mdtype`属性。例如，你还可以通过选择器`[ mdtype = "heading"]`选择标题（不过大多数时候，使用标签选择器就足够了）。其他可能的`mdtype`值包括`paragraph`，`heading`，`blockquote`，`fences`，`hr`，`def_link`，`def_footnote`，`table`，`meta_block`，`math_block`，`list`，`toc`，`list_item`，`table_row`，`table_cell`，`line`。

| `mdtype`值                                | **对应 Css 选择器**                                         | **说明**                                                     |
| :---------------------------------------- | :---------------------------------------------------------- | :----------------------------------------------------------- |
| paragraph                                 | p                                                           |                                                              |
| line                                      | .md-line                                                    | 一个段落可以包含一个或多个`.md-line`                         |
| heading                                   | h1~h6                                                       |                                                              |
| blockquote                                | blockquote                                                  |                                                              |
| list (unordered list)                     | ul li                                                       |                                                              |
| list (ordered list)                       | ol li                                                       |                                                              |
| list (task)                               | ul.task-list li. task-list-item                             |                                                              |
| toc                                       | .md-toc                                                     |                                                              |
| fences (before codemirror is initialized) | pre.md-fences.mock-cm                                       |                                                              |
| fences                                    | pre.md-fences                                               | 请参考[代码片段](#代码片段)                                  |
| diagrams                                  | pre[lang='sequence'], pre[lang='flow'], pre[lang='mermaid'] | 它们是具有某些代码语言的特殊代码片段。                       |
| hr                                        | hr                                                          |                                                              |
| def_link                                  | .md-def-link                                                | 带有子元素的`.md-def-name`, `.md-def-content`, `.md-def-title` |
| def_footnote                              | .md-def-footnote                                            | 带有子元素的`.md-def-name`, `.md-def-content`                |
| meta_block                                | pre.md-meta-block                                           | YAML front matter 内容                                       |
| math_block                                | [mdtype="math_block"]                                       | 预览部分是`.mathjax-block`，HTML 内容由 [MathJax][MathJax] 生成. TeX 由 [CodeMirror][CodeMirror] 支持, 请参考 [代码片段](#代码片段) |
| table                                     | table thead tbody th tr td                                  |                                                              |

#### 多行

在 Typora 中，一个段落可能包含由`\n`分隔的多个行，使用`.md-line`选择器可选择一个`<p>`标签中的每个“行”。

#### 代码片段

语法高亮显示按 [CodeMirror][CodeMirror] 的启用。详细信息请参阅[此文档][Code-Block-Styles]。

### 内联元素

内联元素也会像大多数解析器那样呈现。 因此，可以进行以下操作：

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

内联元素通常包括一个 span 元素、元语法和输出内联元素，例如 `**strong**` 将呈现为

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

如你所见，内联元素的整个部分由具有`md-inline`属性的`span`元素包裹，该元素表示解析结果的类型信息。可能的属性包括（一些内联语法需要从偏好设置中启用）:

| `md-inline`值 | 对应 Markdown 语法                | 输出标签 |
| :------------ | :-------------------------------- | :------- |
| plain         | `plain`                           | `span`   |
| strong        | `**strong**`                      | `strong` |
| em            | `*em*`                            | `em`     |
| code          | <code>`code`</code>               | `code`   |
| underline     | `<u>underline</u>`                | `u`      |
| escape        | `\(`                              | `span`   |
| tag           | `<button>`                        |          |
| del           | `~~del~~`                         | `del`    |
| footnote      | `^1`                              | `sup`    |
| emoji         | `:smile:`                         | `span`   |
| inline_math   | `$x^2$`                           | `span`   |
| subscript     | `~sub~`                           | `sub`    |
| superscript   | `^sup^`                           | `sup`    |
| linebreak     | (two whitespace at end of a line) |          |
| highlight     | `==highlight==`                   | `mark`   |
| url           | `http://typora.io`                | `a`      |
| autolink      | `<http://typora.io>`              | `a`      |
| link          | `[link](href)`                    | `a`      |
| reflink       | `[link][ref]`                     | `a`      |
| image         | `![img](src)`                     | `img`    |
| refimg        | `![img][ref]`                     | `img`    |

下面是对 Typora 风格的内嵌 Markdown 语法如 `*` 或 `_` 的解释（大多数情况下它们在 Typora 中都是隐藏的）。通常你不需要为它们专门设置 CSS 规则。

当你将 Markdown 文件转换为 HTML 时，像 `**` 或 `==` 这些内联元素的元语法将会消失。它们被 `md-meta` 类包装，并且默认情况下有样式 `display:none` 。默认情况下，图像的 Markdown 语法也是隐藏的，它们被 `md-content` 类包装起来。当光标位于这些内联元素中时，被聚焦的部分将被 `md-expand` 类包装，然后。 `.md-meta` 和`.md-content` 会变得可见。因此，如果你想修改那些元语法的样式，则需要将样式应用到 `.md-meta` 和`.md-content`上。

### 源代码模式

源代码模式也是由 [CodeMirror][CodeMirror] 驱动的，因此它用于语法高亮显示的类与代码块相同([详见此处][Code-Block-Styles])。请注意，代码块使用 codemirror 主题`.cm-s-inner`，而在源代码模式下，codemirror 主题是`.cm-s-typora-default`。所以 CSS 是这样的:

```css
.cm-s-typora-default .cm-header {
  /*styles for h1~h6 in source code mode*/
}
```

### 聚焦模式

关于这个主题，请参考[这个文档][focus mode]。

#### 自定义字体

关于这个主题，请参考[这个文档][custom font]。

### 背景

关于这个主题，请参考[这个文档][background]。

### 用户界面

大多数 UI 组件，包括工具提示、对话框和按钮都是通过 HTML 绘制的。在完成上面的步骤后，你只需要在发现 UI 组件与编辑器主题不兼容时更改相应内容即可。为便于调试，[工具包][toolkit]中的 HTML 文件包含了大多数常用的 UI 组件。

### Windows/Linux 的附加用户界面

Typora 的 Windows/Linux 版本比 macOS 版本支持更多的 html 组件，包括上下文菜单、偏好设置面板，甚至是你在 Windows 上使用“unibody”窗口样式时的窗口框架。

为便于调试，[工具包][toolkit]中的 HTML 文件包含了大多数常用的 UI 组件。

### 打印

在下面的选择器中写入 CSS 将更改 PDF 及打印内容的样式。

```css
@media print {
    /* for example: */
    .typora-export * {
        -webkit-print-color-adjust: exact;
    }
    /* add styles here */
}
```

## 调试和测试

### 在浏览器中测试

我们在[工具包][toolkit]的 `html-preview` 文件夹下提供了一些 html 文件以方便从 Safari 或 Chrome 浏览器预览你的主题。 要使用它们，请重命名并将你的 CSS 文件放入`html-preview/theme/test.css`。

### 在 Typora 中测试

查看[这个文档][install-theme]学习如何在 Typora 安装一个主题。

安装好需要调试的主题后，对于 mac 用户，从帮助菜单中选择启用调试模式，然后从上下文菜单中单击“检查元素”弹出 DevTools。对于 Windows/Linux 用户，可以在“视图”菜单下点击“开发者工具”进入。

## 提示和参考

相关文档可参考[这里](http://support.typora.io/style)。

如果你有一些建议想要分享，请向[ typora-wiki-site ](https://github.com/typora/wiki-website)提 PR。

[CodeMirror]: http://codemirror.net
[Custom Font]: http://support.typora.io/Custom-Font/
[focus mode]: http://support.typora.io/Change-Styles-in-Focus-Mode/
[Code-Block-Styles]: http://support.typora.io/Code-Block-Styles
[MathJax]: http://www.mathjax.org
[background]: http://support.typora.io/Backgound/
[install-theme]: https://github.com/typora/typora-theme-gallery/blob/gh-pages/_posts/doc/2016-09-21-Install%20Theme.md
[typora-theme-gallery]: https://github.com/typora/typora-theme-gallery
[toolkit]: https://github.com/typora/typora-theme-toolkit
