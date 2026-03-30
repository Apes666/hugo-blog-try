---
title: "从零开始推导傅立叶变换"
description: ""
math: true
date: 2026-03-22T01:57:15+08:00
lastmod: 2026-03-22T01:57:15+08:00
slug: "my-first-post"
draft: false

# 图床封面可以直接写完整 URL，例如：
# image: "https://img.example.com/blog/2026/03/cover.jpg"
image: "https://picr2.060216.xyz/1774873310673_Firefox_2026-03-30_20.21.31.webp"

# 每篇文章建议 1-2 个分类，解决“这篇属于什么主题”
categories: []

# 标签用于关键词检索，建议 3-6 个
tags: [
    math
]
---

## 历史起源

傅立叶在研究热传导方程时提出的思路，用三角函数级数表示任意周期函数

## 傅立叶级数推导

*F.S.*（Fourier Series）

**概括**：傅立叶级数就是用**三角函数系**表示**周期函数**的一种方法

> 三角函数系（1，cosx，sinx）的正交完备性：（周期内）
>
> 1. 正交性：除自己，点乘为0
> 2. 完备性：可以表示所有函数

> 函数点乘：在一定区间上乘积的积分；
> 从一般向量内积类比，对应维度的数相乘，最后相加。函数可以看作无穷维的向量，每个点的乘积再求和。因为点的无穷小的特性，求和也就变成了积分。

$$
f(x) = \frac{a_0}{2}+\Sigma^{\infin}_{n=1}a_n\cos{\omega_nx}+b_n\sin{\omega_nx}
$$

**系数计算**：

从正交性出发，欲求$a_i$便将等式两边同时在一定区间点乘**对应的函数项**

即为$\int_{-\frac{T}{2}}^{\frac{T}{2}}f(x)\cos{\omega_nx}\ \mathrm{d}x=a_n\int_{-\frac{T}{2}}^{\frac{T}{2}}\cos^2{\omega_nx}\ \mathrm{d}x$

同时，有这个关系
$$
\omega_n=n\omega_0\\
T = \frac{2\pi}{\omega_0}
$$
求得$a_n$
$$
a_n=\frac{\int_{-\frac{T}{2}}^{\frac{T}{2}}f(x)\cos{\omega_nx}\ \mathrm{d}x}{\int_{-\frac{T}{2}}^{\frac{T}{2}}\cos^2{\omega_nx}\ \mathrm{d}x}=\frac{2}{T}\int_{-\frac{T}{2}}^{\frac{T}{2}}f(x)\cos{\omega_nx}\ \mathrm{d}x
$$
$b_n$同理（实际上同周期的两个三角函数系只是经过相位平移的相同波形，通过**辅助角公式**可以化为一个周期函数$A\cos{(\omega x+\phi)}$，a和b**两个参数**去描述这个周期函数，对应了此合并过函数的**幅度**和**相位**）

## 傅立叶级数的推广

**概括**：在**复数域**对周期函数进行表示

复数域在实数域上多了一根虚轴，因此如需几何形象化表示函数，加上函数的（单）自变量（t or x），需要三个轴，即在**三维空间**表示复数域的函数。

![CleanShot 2026-03-30 at 17.15.18](https://picr2.060216.xyz/2026/03/ae30327b73ae61fd9da9a6655c697a81.gif)

对于此空间中的**基底**，是以**不同角速度**旋转的**单位向量**，即$e^{jn\omega_0 t}$

此时的完备正交函数系就是**$e^{jn\omega_0 t} \ n\in \mathrm{Z}$**（无需0处的额外处理）

如此，有了拓展后的傅立叶级数
$$
f(t) = \Sigma_{n=-\infty}^{\infty}c_ne^{jn\omega_0t}
$$
**系数计算**：
$$
\int _{-\frac{T}{2}}^{\frac{T}{2}}f(t)\cdot e^{-jn\omega_0t}=T\cdot c_n\\
c_n=\frac{1}{T}\int _{-\frac{T}{2}}^{\frac{T}{2}}f(t)\cdot e^{-jn\omega_0t}
$$

### 与实数形式的联系

根据**欧拉公式**：
$$
\cos x = \frac{e^{ix}+e^{-ix}}{2}\\\sin x = \frac{e^{ix}-e^{-ix}}{2i}
$$

$$
f(x) = \frac{a_0}{2}+\Sigma \frac{a_n}{2}(e^{ix}+e^{-ix})+\frac{b_n}{2i}(e^{ix}-e^{-ix})\\
f(x) = \frac{a_0}{2}+\Sigma \frac{1}{2}(a_n-ib_n)e^{ix}+\frac{1}{2}(a_n+ib_b)e^{-ix}
$$

两式系数可一一对应，同时可以注意到，n绝对值相同的复数基底互为共轭，相加成对抵消了虚数部分，因此导出了函数为实数的结论。由此可以看出，实数域*F.S.*只是复数域的一种**特殊情况**。

## 傅立叶变换的推导

*F.T.*（Fourier Transform）

**概括**：和傅立叶级数形式类似的、有些渊源的**积分变换**

由头：非周期函数能否看成**周期无限大**的一种另类的周期函数，来用傅立叶级数去表示呢？

将这种想法写出数学表达式：
$$
f(t) = \lim_{T \to \infty \ \omega_0 \to 0}\Sigma_{n=-\infty}^{\infty}c_ne^{jn\omega_0t}
\\f(t) = \int_{-\infty}^{\infty}F(j\omega)e^{j\omega t}\mathrm{d}\omega
$$

### 傅立叶变换性质

……