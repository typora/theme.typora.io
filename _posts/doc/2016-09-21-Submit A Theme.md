---
layout: post
title: Submit A Theme
category: doc
author: typora.io
typora-root-url: ../../
---

- Fork [this site](https://github.com/typora/typora-theme-gallery) on Github
- Create a new post in the `_posts` directory and fill out the relevant YAML fields
- Make a 250x200 thumbnail and drop it in the `thumbnails` directory. List its filename in the post's markdown file.
- Test it out (also test your theme), then push your changes up and open a pull request.

### Notices

- We recommand you to go through all html files inside the [theme toolkit](https://github.com/typora/typora-theme-toolkit), so user could use it in OS platforms that differ then yours.

- If your theme does not include the styles for Typora on specific platform, please put a notice in post, for example:

  > Designed and tested on macOS. Not fully tested, but should work for Windows/Linux. But this theme does not include styles for Windows "unibody" style.
  
- If only small modifications are introduced, like changing a font or changing the padding of write area based on an exisiting theme, we could recommand you to edit the post of the original theme, and add links or discriptions about your "forked" one.
