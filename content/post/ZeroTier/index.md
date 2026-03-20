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
## 1. 下载软件
[ZeroTier下载地址](https://www.zerotier.com/download/)
点击下载地址，根据自己操作系统下载对应版本。
## 2. 加入网络（已加入请跳过）
以windows为例
打开 **PowerShell（管理员模式）**，复制并运行：
```powershell
zerotier-cli join <你的16位网络ID>
```

## 3. 奔向月球（解决 400ms 延迟的核心）

这一步是告诉你的 ZeroTier：**“别去国外绕路，直接走成都阿里云中转。”** 在同一个窗口继续运行：

```powershell
# 注意：后面的 Moon ID  必须连写两次
zerotier-cli orbit <Moon ID> <Moon ID>
```

## 4. 检查是否“上天”成功

输入以下命令验证：

```PowerShell
zerotier-cli listpeers
```

**验收标准：**

- 找到对应`服务器的Moon ID` 这一行。
- 后面 Role 显示的是 **`MOON`**。
- 延迟（Latency）在 **30-60ms** 之间。
