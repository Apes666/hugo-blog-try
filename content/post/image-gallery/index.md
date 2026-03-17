---
title: 图片画廊
slug: image-gallery
description: 使用 Markdown 创建交互式图片画廊
date: 2023-08-26 00:00:00+0000
image: 2.jpg
---

Hugo Theme Stack 支持直接用 Markdown 创建交互式图片画廊。它底层使用的是 [PhotoSwipe](https://photoswipe.com/)，写法灵感来自 [Typlog](https://typlog.com/)。

要使用这个功能，图片必须和 Markdown 文件放在同一个目录中。因为它依赖 Hugo 的 page bundle 机制读取图片尺寸，所以 **不支持外链图片**。

## 语法

```markdown
![图片 1](1.jpg) ![图片 2](2.jpg)
```

## 效果

![图片 1](1.jpg) ![图片 2](2.jpg)

> 图片来自 [mymind](https://unsplash.com/@mymind) 和 [Luke Chesser](https://unsplash.com/@lukechesser) 在 [Unsplash](https://unsplash.com/) 上的作品。
