---
title: 数学公式排版
slug: math-typesetting
description: 使用 KaTeX 渲染数学公式
date: 2023-08-24 00:00:00+0000
math: true
---

Stack 主题内置了对 [KaTeX](https://katex.org/) 的支持，可以直接在文章中渲染数学公式。

**它默认不会在全站启用，** 你可以像这篇文章一样，在 front matter 中添加 `math: true` 按文章启用；如果你希望整站开启，可以在 `config/_default/params.toml` 的 `params.article` 部分设置 `math = true`。

## 行内公式

这是一个行内数学公式：$\varphi = \dfrac{1+\sqrt5}{2}= 1.6180339887…$

```markdown
$\varphi = \dfrac{1+\sqrt5}{2}= 1.6180339887…$
```

## 块级公式

$$
    \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } } 
$$

```markdown
$$
    \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } } 
$$
```

$$
    f(x) = \int_{-\infty}^\infty\hat f(\xi)\,e^{2 \pi i \xi x}\,d\xi
$$

```markdown
$$
    f(x) = \int_{-\infty}^\infty\hat f(\xi)\,e^{2 \pi i \xi x}\,d\xi
$$
```
