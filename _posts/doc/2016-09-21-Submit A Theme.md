---
layout: post
title: Submit a Theme
category: doc
author: typora.io
typora-root-url: ../../
---

- Fork [this site](https://github.com/typora/typora-theme-gallery) on Github
- Create a new post in the `_posts` directory and fill out the relevant YAML fields
- Make a 250x200 (or 500x400) thumbnail and drop it in the `thumbnails` directory. List its filename in the post's markdown file.
- Test it out (also test your theme), then push your changes up and open a pull request.

### Notes

- We recommend you to go through all html files inside the [theme toolkit](https://github.com/typora/typora-theme-toolkit), so that users could use it on OS platforms different from yours.

- If your theme does not include the styles for Typora on specific platform, please put a notice in post, for example:

  > Designed and tested on macOS. Not fully tested, but should work for Windows/Linux. But this theme does not include styles for Windows "unibody" style.

- If only small modifications are introduced, like changing a font or changing the padding of write area based on an existing theme, we recommend you to write your post under folder `/_posts/fork`, and set the category to be `fork` in the YAML front matter of the post, and then put a reference link in the original theme. 
