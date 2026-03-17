---
title: "{{ replace .File.ContentBaseName `-` ` ` | title }}"
description: ""
date: {{ .Date }}
lastmod: {{ .Date }}
slug: "{{ .File.ContentBaseName }}"
draft: true

# 图床封面可以直接写完整 URL，例如：
# image: "https://img.example.com/blog/2026/03/cover.jpg"
image: ""

# 每篇文章建议 1-2 个分类，解决“这篇属于什么主题”
categories: []

# 标签用于关键词检索，建议 3-6 个
tags: []
---

这里先写一段导语，作为文章摘要的补充。

## 背景

说明这篇文章要解决什么问题。

## 过程

记录步骤、配置、代码或截图说明。

## 总结

补一段结论，方便以后检索。
