---
layout: theme
title: high-contrast
category: theme
homepage: https://github.com/Zervan29131/high-contrast
download: https://github.com/Zervan29131/high-contrast
built-in: false
author: Zervan
thumbnail: high-contrast.png
typora-root-url: ../../
typora-copy-images-to: ../../media/theme/high-contrast
---

<h1 align='center'>High-Contrast Theme For Typora</h1>

A highcontrast theme for Typora, intended for creating a high contrast screen.

具有以下特点：

1. 优化大纲标题显示样式，层级分明，直观漂亮；
2. 部分标题增加了hover动画，鼠标移动上去有简单的互动；
3. 表格样式进行了调整，更加简约，代码块使用了亮色的Mac风格，很漂亮；
4. 超链接前面会加一个可爱的小图标。
5. 使用Typora导出网页，大纲目录的样式也进行了同样的优化



![image-20241229005550600](https://s2.loli.net/2024/12/29/4zq9VbuAKvkFhYo.png)

![image-20241229005801957](https://s2.loli.net/2024/12/29/mHh5nuwyVWvpoGI.png)

## **1.如何使用**

- 下载[主题文件](https://github.com/caolib/typora-onelight-theme/releases)
- 在typora中选择 文件 → 偏好设置 → 外观 → 打开主题文件夹
- 将下载的zip解压，将**css文件**和**文件夹**粘贴到typora的主题文件夹中

> [!caution]
>
> - **如果你想克隆本仓库，为了避免克隆到其他分支，请使用下面这条命令,这样只会克隆主分支**
>
>   ```shell
>   git clone --single-branch https://github.com/caolib/typora-onelight-theme.git
>   ```
>
> - 如果你想从网络导入
>
>   ```css
>   @import url("https://cdn.jsdelivr.net/gh/caolib/typora-onelight-theme@onelight/dist/onelight.min.css");
>   ```

---

## **2.关于字体**

在`onelight.css`文件开头设置了默认字体，可以自行修改
![](https://github.com/user-attachments/assets/ab75260f-cff0-43b7-b8e5-dfea38e8525c)

> **如果要使用主题中的字体，建议下载字体安装**,中文字体是[喵字果汁体](https://clb-cdn.pages.dev/fonts/MiaoZi-GuoZhiTi.ttf)，英文字体是Cascadia Code

## **3.关于背景图片**

> [!tip]
>
> 背景图片在`onelight/img`文件夹下，默认是bg.gif，可以自行替换,你也可以在css文件中搜索并替换文件
>
> ```css
> content {
>      background-color: transparent;
>      // 可以替换此处的图片，不想显示可以将这段整个注释掉
>      background-image: url('./onelight/img/bg.gif');
>      background-position: 100% 100%;
>      background-repeat: no-repeat;
>      // 修改图片大小
>      background-size: 200px auto;
>      transition: background-image .5s ease-in-out, background-size .5s ease-in-out
> }
> ```
>
> <img src="https://s2.loli.net/2024/12/15/Fn6LcrKWC2dlp1J.gif" alt="recording" style="zoom: 50%;" />


## Installation

1. [Download](https://github.com/Zervan29131/high-contrast)the zipped project package from Github.

2. Copy the highcontrast.css file and highcontrast folder to your Typora theme library.

3. Launch or restart Typora and choose highcontrast from the theme menu.

## Credits
