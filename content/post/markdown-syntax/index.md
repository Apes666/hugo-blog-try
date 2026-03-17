---
title: Markdown 语法指南
slug: markdown-syntax-guide
date: 2023-09-07
description: 一篇示例文章，用来展示 Hugo 内容文件中常见的 Markdown 语法和 HTML 元素样式。
tags: 
    - markdown
    - css
    - html
    - themes
categories:
    - themes
    - syntax
---

这篇文章展示了 Hugo 内容文件里最常用的 Markdown 写法，同时也用来检查主题是否已经为基础 HTML 元素补好了样式。

<!--more-->

## 标题

下面的 HTML `<h1>` 到 `<h6>` 一共表示六级标题，其中 `<h1>` 层级最高，`<h6>` 层级最低。

# H1
## H2
### H3
#### H4
##### H5
###### H6

## 段落

Markdown 最常见的内容就是普通段落。只要中间留出空行，Hugo 在渲染时就会自动把它们拆成独立的 `<p>` 标签。

如果一篇文章以中文为主，记得把站点的 `hasCJKLanguage` 打开。这个项目已经在 `config/_default/config.toml` 里启用了它，这样摘要截取和字数统计才会更合理。

## 引用块

引用块通常用来放引文、提示或者需要视觉区分的说明文字。你可以只放正文，也可以附带出处。

### 不带出处的引用

> 这是一段简单的引用内容。
> **注意**：引用块里依然可以继续使用 *Markdown 语法*。

### 带出处的引用

> Don't communicate by sharing memory, share memory by communicating.<br>
> — <cite>Rob Pike[^1]</cite>

[^1]: 这句话摘自 Rob Pike 在 2015 年 11 月 18 日 Gopherfest 演讲中的一段分享：[视频链接](https://www.youtube.com/watch?v=PAAkCSZUG1c)。

## 表格

表格不是 Markdown 最核心的语法之一，但 Hugo 默认就支持。

   姓名 | 年龄
--------|------
   小王 | 27
   小李 | 23

### 表格中的行内 Markdown

| Italics   | Bold     | Code   |
| --------  | -------- | ------ |
| *italics* | **bold** | `code` |

| A                                                        | B                                                                                                             | C                                                                                                                                    | D                                                 | E                                                          | F                                                                    |
|----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------|------------------------------------------------------------|----------------------------------------------------------------------|
| 这一列可以放较长的文本。                                 | Hugo 会按表格语法把内容渲染成对应的 HTML 表格结构。                                                            | 如果主题样式正常，这里应该能看到边距、字号和对齐方式都已经处理好。                                                                  | 也可以混合较短的字段。                            | 表格内容不一定非得是英文。                                 | 中文内容同样可以正常展示。                                         |

## 代码块
### 使用反引号的代码块

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example HTML5 Document</title>
</head>
<body>
  <p>Test</p>
</body>
</html>
```

### 使用四个空格缩进的代码块

    <!doctype html>
    <html lang="en">
    <head>
      <meta charset="utf-8">
      <title>Example HTML5 Document</title>
    </head>
    <body>
      <p>Test</p>
    </body>
    </html>

### Diff 代码块

```diff
[dependencies.bevy]
git = "https://github.com/bevyengine/bevy"
rev = "11f52b8c72fc3a568e8bb4a4cd1f3eb025ac2e13"
- features = ["dynamic"]
+ features = ["jpeg", "dynamic"]
```

### 单行代码块

```html
<p>A paragraph</p>
```

## 列表类型

### 有序列表

1. 第一项
2. 第二项
3. 第三项

### 无序列表

* 列表项
* 另一个列表项
* 再来一个列表项

### 嵌套列表

* 水果
  * 苹果
  * 橙子
  * 香蕉
* 乳制品
  * 牛奶
  * 奶酪

## 其他元素：缩写、上下标、按键、标记

<abbr title="Graphics Interchange Format">GIF</abbr> 是一种位图图像格式。

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

按下 <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>Delete</kbd> 可以结束当前会话。

大多数 <mark>蝾螈</mark> 都是夜行动物，会捕食昆虫、蠕虫和其他小型生物。
