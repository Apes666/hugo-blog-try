---
title: "ZeroTier 操作指南"
description: ""
date: 2026-03-20T18:16:33+08:00
lastmod: 2026-03-20T18:16:33+08:00
slug: "ZeroTier"
draft: false

# 图床封面可以直接写完整 URL，例如：
# image: "https://img.example.com/blog/2026/03/cover.jpg"
image: "https://picr2.060216.xyz/3297359d3aac4dabaa77df2104339369.webp"

# 每篇文章建议 1-2 个分类，解决“这篇属于什么主题”
categories: [Tech]

# 标签用于关键词检索，建议 3-6 个
tags: []
---


# 1. 加入网络（已加入请跳过）

打开 **PowerShell（管理员模式）**，复制并运行：
```powershell
zerotier-cli join a581878f7d2e93c3
```

# 2. 奔向月球（解决 400ms 延迟的核心）

这一步是告诉你的 ZeroTier：**“别去国外绕路，直接走成都阿里云中转。”** 在同一个窗口继续运行：

```powershell
# 注意：后面的 ID 7764302f8c 必须连写两次
zerotier-cli orbit 7764302f8c 7764302f8c
```

# 3. 检查是否“上天”成功

输入以下命令验证：

```PowerShell
zerotier-cli listpeers
```

**验收标准：**

- 找到 `7764302f8c` 这一行。
- 后面 Role 显示的是 **`MOON`**。
- 延迟（Latency）在 **30-60ms** 之间。
