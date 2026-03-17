---
title: Shortcodes 短代码
slug: shortcodes
description: 展示 Markdown 中可直接使用的常见 Hugo Shortcodes
date: 2023-08-25 00:00:00+0000
image: cover.jpg
---

更多说明可以查看文档：https://stack.jimmycai.com/writing/shortcodes

## Bilibili 视频

{{< bilibili "BV1d4411N7zD" >}}

## 腾讯视频

{{< tencent "g0014r3khdw" >}}

## YouTube 视频

{{< youtube "0qwALOOvUik" >}}

## 通用视频文件

{{< video "https://www.w3schools.com/tags/movie.mp4" >}}

## GitLab

{{< gitlab 2589724 >}}

## 引用

{{< quote author="某位知名作者" source="一本广为流传的书" url="https://en.wikipedia.org/wiki/Book">}}
Shortcode 适合封装那些需要重复使用、但直接写在 Markdown 里又比较啰嗦的片段。像视频嵌入、引用卡片、外部内容嵌入，都很适合用这种方式统一管理。
{{< /quote >}}

-----

> 封面图片来自 [Codioful](https://unsplash.com/@codioful) 在 [Unsplash](https://unsplash.com/photos/WDSN62Qdxuk) 上的作品。
