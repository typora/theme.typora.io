---
layout: post
title: Install Theme
category: doc
author: typora.io
typora-root-url: ../../
---

## Summary

1. Open Theme Folder from `Preference Panel` → `Appearance` section.
2. Copy css and related resources, like fonts or images, into the newly opened folder.
3. Restart typora, then select it from `Themes` menu.

---

## How to Open Theme Folder

### macOS

Open preference panel by <code>cmd+`</code>, then click "Open Theme Folder"

![typora-preference-mac](/media/doc/install-theme/Snip20160921_1.png)

On macOS, usually it is `/Users/{username}/Library/Application Support/abnerworks.Typora/themes/`

### Windows/Linux

Open preference panel from `File` → `Preference` from menubar, then click "Open Theme Folder":

![typora-preference-electron](/media/doc/install-theme/Snip20160921_2.png)

## FAQ

#### Where to find/download Typora themes ?

You could visit [Typora Theme Gallery](http://theme.typora.io) to download themes provide by other users to us.

#### The theme not show in theme menu bar, or after selecting it, the theme not updated.

It may be caused by your CSS filename contains capitalised characters or whitespace. Please change to lowercase + hyphen, e.g. `my-typora-theme.css`.

#### How to modify existing theme.

Briefly speaking, if the theme is created by you, you would modify it directly. 

If the theme is built-in with Typora, or was downloaded from website, then, you may need to update them by download new one to replace the original one. In this case, we recommend you to put your modifications into another files, which won;t be overwritten when typora, or the theme file is updated. You could put your modifications into:

- `base.user.css` under theme folder, the css rules inside it will be applied to all themes.
- `{theme-css-name}.user.css`, the css rules inside it will only be applied to theme file `{theme-css-name}.css`.

For more details, please check [Add Custom CSS](http://support.typora.io/Add-Custom-CSS/).

#### How to write my own theme?

Please refer to [Write Custom Theme for Typora](/doc/Write-Custom-Theme/).
