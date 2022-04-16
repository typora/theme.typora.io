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

Open the preference panel using the keyboard combination <code>cmd+`</code>, then click "Open Theme Folder"

![typora-preference-mac](/media/doc/install-theme/Snip20160921_1.png)

On macOS, the theme folder is usually in  `/Users/{username}/Library/Application Support/abnerworks.Typora/themes/`

### Windows/Linux

Open preference panel from `File` → `Preference` from menubar, then click "Open Theme Folder":

![typora-preference-electron](/media/doc/install-theme/Snip20160921_2.png)

## FAQ

#### Where to find/download Typora themes ?

Visit [Typora Theme Gallery](http://theme.typora.io) to download themes provide by other users to us.

#### The theme not show in theme menu bar, or after selecting it, the theme not updated.

This problem can happen when your CSS filename contains capitalized characters or whitespace. Please change the filename to lowercase and surround it with hyphens, e.g., `my-typora-theme.css`.

#### How to modify existing theme.

If the theme is created by you, you would modify it directly.

If the theme is built-in with Typora or was downloaded from a website, you may need to update it by downloading a new one to replace the original. In this case, we recommend you make your modifications using a copy that has been renamed. Otherwise Typora might overwrite your changes if  the theme file is updated. 

Note that you can put your modifications in two files:

-   `base.user.css` under the theme folder, the css rules inside it will be applied to all themes.
-   `{theme-css-name}.user.css`, the css rules inside it will only be applied to the theme file `{theme-css-name}.css`.

For more details, please check [Add Custom CSS](https://support.typora.io/Add-Custom-CSS/).

#### How to write my own theme?

Please refer to [Write Custom Theme for Typora](/doc/Write-Custom-Theme/).
