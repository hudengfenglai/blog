---
title: 第一篇文章：欢迎来到我的博客
date: 2024-01-01T10:00:00+08:00
lastmod: 2024-01-01T10:00:00+08:00
draft: false
weight: 100
description: 这是博客的第一篇文章，介绍博客的基本功能和使用方法。
categories:
  - 分享
tags:
  - 博客
  - 入门
cover: ""
---

## 👋 前言

欢迎来到我的博客！这是一篇测试文章，用来展示博客的各种功能特性。

## ✨ 功能展示

### 代码高亮

博客支持多种编程语言的代码高亮：

```python
def hello_world():
    print("Hello, World!")
    return True
```

```javascript
const greeting = (name) => {
  console.log(`Hello, ${name}!`);
};
```

### 提示块引用

{{< alertBlockquote type="tip" >}}
这是一条提示信息，帮助你更好地理解内容。
{{< /alertBlockquote >}}

### 折叠面板

{{< details summary="点击查看更多" >}}
这里是折叠的内容，可以用来放一些额外的信息或参考资料。
{{< /details >}}

### 链接卡片

{{< link title="Hugo 官方文档" link="https://gohugo.io/" cover="auto" >}}

### 标签页

{{< tabs 1 "center" >}}

<!-- tab 安装 -->

```bash
hugo new site myblog
cd myblog
```

<!-- tab 配置 -->

编辑 `hugo.toml` 文件进行配置。

<!-- tab 运行 -->

```bash
hugo server
```

{{< /tabs >}}

## 📊 Mermaid 图表

如果需要展示流程图，可以这样写：

```mermaid
graph TD
    A[开始] --> B{判断条件}
    B -->|是| C[执行操作]
    B -->|否| D[执行其他操作]
    C --> E[结束]
    D --> E
```

## 📝 数学公式

博客支持 LaTeX 数学公式渲染：

行内公式：$E = mc^2$

独立公式：
$$
\int_{0}^{\infty} e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
$$

## 🎯 写在最后

这篇文章只是一个开始，后续我会分享更多学习笔记和技术文章。

如果你有任何问题或建议，欢迎在评论区留言！

> *静待风起，疾风知劲草 🌬️*