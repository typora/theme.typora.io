---
title: Typora のカスタムテーマを作成する
permalink: /doc/ja/Write-Custom-Theme/
---

## 翻訳

[English](/doc/Write-Custom-Theme/), [简体中文](/doc/zh/Write-Custom-Theme/), [繁體中文](https://pjchender.github.io/2018/04/24/note-%E5%A6%82%E4%BD%95%E7%82%BA-typora-%E6%92%B0%E5%AF%AB%E5%AE%A2%E8%A3%BD%E5%8C%96%E6%A8%A3%E5%BC%8F/)

## 更新 -- CSS 変数

フォントや色、背景を定義したい場合は、既存の [CSS 変数](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables) を上書きする方がおすすめです。 macOS/Safari の初期バージョンではサポートされていませんが、それでもこちらの方がはるかに使いやすいです。 よく使われるのは、以下のようなものです。

```css
:root {
   --bg-color:  #ffffff; /* 背景色を変更する */
   --text-color: #333333; /* テキストの色を変更する */
   --md-char-color: #C7C5C5; /* Markdown で `*` のようなメタ文字の色を変更する */
   --meta-content-color: #5b808d; /* Markdown で画像テキストやリンクアドレスのようなメタコンテンツの色を変更する */

   --primary-color: #428bca; /* プライマリボタンの色 */
   --primary-btn-border-color: #285e8e;
   --primary-btn-text-color: #fff;

   --window-border: 1px solid #eee; /* サイドバーなどの境界線 */

   --active-file-bg-color: #eee; /* ファイルツリーまたはファイルリストにリストアイテムがある場合の背景色  */
   --active-file-text-color: inherit;
   --active-file-border-color: #777;

   --side-bar-bg-color: var(--bg-color); /* サイドバーの背景を変更する */
   --item-hover-bg-color: rgba(229, 229, 229, 0.59); /* サイドバーのメニューのように、ホバー時に表示するコントロールアイテムの背景 */
   --item-hover-text-color: inherit;
   --monospace: monospace; /* コード、フェンス用の等幅フォント */
}
```

将来的に変数が変わる可能性もあるため、[Typora の DevTools を使って確認できます](#test-in-typora)。


## 要約

Typora のカスタム CSS テーマを作成する場合は、以下のことを行う必要があります。

1. 新しい CSS ファイルを作成します。 ファイル名には **大文字や空白を含めないでください**。 たとば、`my-typora-theme` は有効なファイル名です。

2. CSS ファイルを書き込みます。

   これから始める方、簡単なテストをしたい方のために、[ツールキット][toolkit] を用意しました。 [^1]

   ゼロから作成する場合は、template.less を選択して入力します。

   既存の CSS ファイル (Wordpress や Jekyll のテーマから) を変換したい場合は、ファイルの中身をコピーしてから、"toc" や UI コンポーネントのスタイルなど、それらの CSS ファイルがカバーしていないスタイルを追加します。 

3. CSS のクラスとスタイルを微調整/デバッグします。

   また、[カスタムテーマのインストール方法][install-theme] に従って、テーマをインストールして使用し、Typora でテストすることも可能です。
   
   Typora で Safari や Chrome のように CSS をデバッグするには、ヘルプメニュー (macOS) または設定パネル (macOS/Linux/Windows) からデバッグモードを有効にして、コンテキストメニューから [要素を調査] を見つけてクリックすると、Safari や Chrome ブラウザのように [DevTools](https://developer.chrome.com/devtools) をポップアップすることができるようになります。Linux/Windows 版では、`表示` メニューからトグルするか、`Shift + F12` を押すだけです。
   
   また、作成した CSS ファイルを toolkit/theme/test.css に、使用している画像やフォントなどのリソースと一緒に配置できます。 そして、toolkit/core と toolkit/electron の下にある HTML ファイルを開いて、作成した CSS をプレビューします。 Mac の場合は Safari、Linux/Windows の場合は Chrome で HTML ファイルをプレビューしてください。

4. テーマを共有したい場合は、フォークを作成し、[Typora Theme Gallery](https://github.com/typora/typora-theme-gallery) にプルリクエストを送信してください。

## 基本ルール

1. テーマ CSS のファイル命名規則では、大文字は使用せず、空白は `-` に置き換えてください。 Typora はそれらをメニュー項目の中で読み取り可能なラベルに変換します。 たとえば、`my-first-typora-theme.css` の場合、Typora は [テーマ] メニューの下に「My First Typora Theme」というメニュー項目を作成します。
2. デフォルトのフォントサイズを `html` に設定し、`h1` や `p` などの要素には `font-size` プロパティに `rem` を使用します。 そうしないと、設定パネルのカスタムフォントサイズが機能しません。
3. 可能であれば、タグをセレクタとして使用してください。 たとえば、`### heading 3` の場合、`h3.md-header` ではなく、`h3` を使用します。 なぜなら、どの Markdown レンダーでも、「### 見出し3」が `h3` タグに変換されるからです。 また、Typora では、他の Markdown コンバーターと同様に、html 属性 (class を含む) をできるだけ少なくします。 さらに、`#write h3` セレクタを使用して、書き込み領域での `h3` を制限できます。 
4. Typora は Webkit (macOS の場合) または Chromium (Windows/Linux の場合) で作成されているため、Chrome または Safari (別名 Webkit) でサポートされている CSS プロパティを使用してください。
5. CSS を変更すると、Typora が期待どおりに機能しない場合があります。 たとえば、セレクタの `#write` に `white-space：pre-wrap;` を追加すると、Tab キーを押しても `\t` を挿入できなくなります。 このため、デフォルトの CSS スタイルの変更はできるだけ少なくして、テストしてください。

---

目次:

* Outline
{:toc}

## 変更点と更新情報

なし

## どの CSS セレクターを使用する必要がありますか?

### 一般的なプロパティ

Typora のウィンドウコンテンツは Web ページなので、`background` や `font-family` などの一般的なプロパティは `html` タグに記述してください。 *mac では、シームレスウィンドウスタイルが使用されている場合、ツールバーの背景色は `html` の `background-color` スタイルで定義されます*。

書き込み領域は id が `#write` の div で、`width`、`height`、`padding` を変更すると、書き込み領域のサイズを調整できます。 設定したプロパティ、たとえば `html` の `color` は、[テーブル挿入] ダイアログの font-color のように、UI 部分を含むウィンドウ全体のコンテンツに適用されるため、書き込み部分のスタイルを変更するだけの場合は、UI コントローラー部分ではなく、`#write` セレクタの下に配置することができます。

```css
/** 設定例 **/
html, body {
  background-color: #fefefe; /* ウィンドウとタイトルバーの背景色 */
  font-family: helvetica, sans-serif; /* カスタムフォント */
  ...
}

html {
  font-size: 14px; /* デフォルトのフォントサイズ */
}

#write {
  max-width: 90%; /* 書き込み領域のサイズを調整します */
  font-size: 1rem; /* 基本のフォントサイズ */
  color: #555; /* 基本のフォントの色 */
  ...
}
```



Typora はすべての要素を他の出力と同じようにレンダリングしようとする、つまり、他の Markdown プロセッサーでパースされるのと同じように、段落は `<p>` タグで、リストは `<ul>` や `<ol>` でラップされるので、これらの HTML タグに CSS スタイルを適用することによってスタイルを変更できます。 また、同じ理由で、Wordpress や他の静的サイトで作成された CSS ファイルも Typora のほとんどのスタイルに影響を与えることができ、直接 CSS ルールを「借用」して、足りない部分を追加したり、調整したりすることになります。

### ブロック要素

先ほど書いたように、Typora はすべての要素を他の出力としてレンダリングしようとします。 たとえば、段落は `<p>`、表は `<table>`、第1レベルの見出しは `<h1>` などで、以下のようにスタイルを書けば、ほとんどの組版 (タイプセット) を変更できます。

```css
p {...}
h1 {...}
table {...}
table th td {...}
table tr:nth-child(2n) td {...}
...
```

先祖 (ancestor) セレクタとして `#write` を追加すれば、コントロール コンポーネントに影響を与えずに、書き込み領域のみにスタイルを適用することができます (たとえば、一部のダイアログでは、タイトルも `h4` タグでラップされる場合があります)。

```css
/* これは、Typora によって表示されるダイアログの h4 のみに適用されます */
.dialog h4 {...} 

/* これは、ユーザーが "#### " を入力した後に生成される、書き込み領域内の h4 にのみ適用されます */
#write h4 {...} 
```

また、全てのブロック要素は `mdtype` 属性を持っています。 たとえば、セレクタ `[mdtype="heading"]` によって、見出しを選択することもできます。 選択できるタイプは、`paragraph`、`heading`、`blockquote`、`fences`、`hr`、`def_link`、`def_footnote`、`table`、`meta_block`、`math_block`、`list`、`toc`、`list_item`、`table_row`、`table_cell`、`line` が含まれます。 しかし、ほとんどの場合、タグセレクタで十分です。

| mdtype                                   | 出力 CSS セレクタ                         | 説明                                     |
| :--------------------------------------- | :--------------------------------------- | :--------------------------------------- |
| paragraph                                | p                                        |                                          |
| line                                     | .md-line                                 | 段落には、1つ以上の `.md-line` を含めることができます |
| heading                                  | h1~h6                                    |                                          |
| blockquote                               | blockquote                               |                                          |
| list (unordered list)                    | ul li                                    |                                          |
| list (ordered list)                      | ol li                                    |                                          |
| list (task)                              | ul.task-list li. task-list-item          |                                          |
| toc                                      | .md-toc                                  | [このドキュメント][toc]も参照してください   |
| fences (codemirror が初期化される前)      | pre.md-fences.mock-cm                    |                                          |
| fences                                   | pre.md-fences                            | 「コードフェンス」の項を参照してください    |
| diagrams                                 | pre[lang='sequence'], pre[lang='flow'], pre[lang='mermaid'] | これらは、特定のコード言語を使用した特別なコードフェンスです |
| hr                                       | hr                                       |                                          |
| def_link                                 | .md-def-link                             | `.md-def-name`、`.md-def-content`、`.md-def-title` 子要素を持つ |
| def_footnote                             | .md-def-footnote                         | `.md-def-name`、`.md-def-content` 子要素を持つ |
| meta_block                               | pre.md-meta-block                        | YAML フロントマターのコンテンツ           |
| math_block                               | [mdtype="math_block"]                    | プレビュー部分は `.mathjax-block` で、html コンテンツは [MathJax][] を介して生成されます。 TeX エディタは [CodeMirror][] を使用しています。 「コードフェンス」の項を参照してください |
| table                                    | table thead tbody th tr td               |                                          |



#### 行

Typora はハード改行をそのままレンダリングします。 そのため、段落には `<\n>` で分割された複数の行を含むことができ、`<p>` 内の各「行」に対して `.md-line` セレクタが使用されます。

#### コードフェンス

シンタックスハイライトは、[CodeMirror][] の機能によって有効になっています。 詳細については、[このドキュメント][Code-Block-Styles] を参照してください。

#### Mermaid

例: [mermaid.css](https://github.com/knsv/mermaid/blob/master/dist/mermaid.css), [mermaid.dark.css](https://github.com/knsv/mermaid/blob/master/dist/mermaid.dark.css), [mermaid.forest.css](https://github.com/knsv/mermaid/blob/master/dist/mermaid.forest.css).

### インライン要素

インライン要素も、ほとんどの Markdown パーサーでレンダリングされるのと同じようにレンダリングされます。 このため、以下の設定が動作する可能性があります。

```css
strong {
  font-weight: bold;
}
em {..}
code {..}
a {..}
img {..}
mark {..} /* ハイライト */
```

インライン要素は通常、ラッパースパン、メタ記法、および出力インライン要素を含み、たとえば `**strong**` は次のようにレンダリングされます。

```html
<!-- strong 要素のラッパー -->
<span md-inline="strong" class=""> 
  
  <!-- strong 要素のメタ記法 -->
  <span class="md-meta md-before">**</span> 
  
    <!-- strong 要素の出力 -->
    <strong>
      <!-- インライン出力 -->
      <span md-inline="plain">strong</span> 
    </strong>
  
   <!-- strong 要素のメタ記法 -->
  <span class="md-meta md-after">**</span>
</span>
```

上記のとおり、インライン要素は `span` でラップされ、 `md-inline` 属性はパース結果のタイプ情報を表します。 可能な属性は以下のとおりです (いくつかのインライン構文は、環境設定パネルから有効にする必要があります)。

| `md-inline` | 記法                              | 出力タグ    |
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
| emoji       | `:smile:`                      | `span`     |
| inline_math | `$x^2$`                           | `span`     |
| subscript   | `~sub~`                           | `sub`      |
| superscript | `^sup^`                           | `sup`      |
| linebreak   | (行末に2つの空白)                  |            |
| highlight   | `==highlight==`                   | `mark`     |
| url         | `http://typora.io`                | `a`        |
| autolink    | `<http://typora.io>`              | `a`        |
| link        | `[link](href)`                    | `a`        |
| reflink     | `[link][ref]`                     | `a`        |
| image       | `![img](src)`                     | `img`      |
| refimg      | `![img][ref]`                     | `img`      |

以下は、Typora でほとんどの場合に非表示になっている `*` や `_` などのインライン Markdown 記法のスタイルについての説明です。 通常、これらのために特別に CSS ルールを設定する必要はありません。

これらのインライン要素の `**` や `==` といったメタ記法は Markdown ファイルを HTML に変換する際に消えてしまいます。 このため、これらはデフォルトでは `md-meta` クラスでラップされ、 `display:none` というスタイルが設定されています。 画像のマークダウン記法のようないくつかの記法もデフォルトでは非表示になり、それらは `md-content` クラスでラップされています。 カーソルがこれらのインライン要素の中にある場合、フォーカスされている要素は `md-expand` クラスでラップされ、 `.md-meta` と `.md-content` が表示されます。 したがって、これらのメタ記法のスタイルを変更したい場合は、`.md-meta` と `.md-content` にスタイルを適用します。

### ソースコードモード

ソースコードモードも [CodeMirror][] を使っているので、シンタックスハイライトに使用するクラスはコードフェンスと同じです ([詳細はこちら][Code-Block-Styles])。 コードフェンスは codemirror のテーマ `.cm-s-inner` を使用しますが、ソースコードモードでは codemirror のテーマは `.cm-s-typora-default` となることに注意してください。 したがって、CSS は以下のようになります。

```css
.cm-s-typora-default .cm-header {
  /* ソースコードモードでの h1~h6 のスタイル */
}
```

### フォーカスモード

このトピックについては、[このドキュメント][focus mode] を参照してください。

#### Custom Font

このトピックについては、[このドキュメント][custom-font] を参照してください。

### Background

このトピックについては、[このドキュメント][background] を参照してください。

### コントローラー UI

ツールチップ、ダイアログ、ボタンなど、ほとんどの UI コンポーネントは HTML で描画されます。 そして、上記の手順を完了した後、UI コンポーネントがエディタのテーマと互換性がないことがわかった場合、これらの部分を変更する必要があります。 [toolkit][] の HTML ファイルには、ほとんどの一般的な UI コンポーネントが含まれているので、簡単にデバッグできます。[^1]

### Windows/Linux 用の追加 UI

Windows/Linux 版の Typora は、コンテキストメニュー、設定パネル、そして Windows で「ユニボディ」ウィンドウスタイルを使用している場合はウィンドウフレーム自体など、macOS 版よりもはるかに多くの HTML ベースのコンポーネントを使用しています。

[toolkit][] の HTML ファイルには、簡単にデバッグできる最も一般的な UI コンポーネントが含まれている可能性があります。[^1]

### 印刷

以下のブロックの中に CSS を記述することで、印刷物やエクスポートした PDF のスタイルのみを変更できます。

```css
@media print {
    /* たとえば */
    .typora-export * {
        -webkit-print-color-adjust: exact;
    }
    /* ここに、スタイルを追加する */
}
```

## デバッグとテスト

### ブラウザでテストする

[toolkit][] の `html-preview` フォルダ以下に、Safari や Chrome からテーマをプレビューするための HTML ファイルがいくつか用意されています。 これらのファイルを使用するには、ファイル名を変更して、CSS ファイルを `html-preview/theme/test.css` に置いてください。 [^1]

### Typora でテストする

Typora にテーマをインストールする方法については、[このドキュメント][install-theme] に従ってください。

次に、Mac の場合は、ヘルプメニューから [デバッグモードを有効にする] をオンにし、コンテキストメニューから [要素を調査] をクリックすると、DevTools が表示されます。

また、Windows/Linux ユーザーの場合は、[表示] メニューの `開発ツール表示切替` から DevTools をポップアップできます。

## カスタムスタイルに関するヒントと参考文献

関連資料は [こちら](http://support.typora.io/style) です。 

共有したいヒントがある場合は、[typora-wiki-site](https://github.com/typora/wiki-website) にプルリクエストを送信してください。



[CodeMirror]: http://codemirror.net
[custom-font]: https://support.typora.io/Custom-Font/
[focus mode]: https://support.typora.io/Change-Styles-in-Focus-Mode/
[Code-Block-Styles]: https://support.typora.io/Code-Block-Styles
[MathJax]: http://www.mathjax.org
[background]: https://support.typora.io/Backgound/

[install-theme]: /doc/Install-Theme/
[typora-theme-gallery]: https://github.com/typora/typora-theme-gallery
[toolkit]: https://github.com/typora/typora-theme-toolkit

**訳注**:
[^1]: 現在の Typora では、[ツールキット][toolkit] は非推奨であり、直接、Typora で動作確認するように推奨されています。
