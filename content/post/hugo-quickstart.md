---
title: Hugo 博客快速入门指南
date: 2024-01-02T09:00:00+08:00
lastmod: 2024-01-02T09:00:00+08:00
draft: false
description: 详细介绍如何使用 Hugo 快速搭建个人博客，包括主题选择、基本配置和部署。
categories:
  - 分享
tags:
  - Hugo
  - 静态博客
  - 建站
cover: ""
---

## 🚀 前言

Hugo 是一个用 Go 语言编写的静态网站生成器，以其超快的构建速度和灵活的模板系统著称。本文将带你快速搭建一个 Hugo 博客。

## 📦 安装 Hugo

### Windows

使用 Chocolatey 安装：

```powershell
choco install hugo-extended -y
```

### macOS

使用 Homebrew 安装：

```bash
brew install hugo
```

### 验证安装

```bash
hugo version
```

## 📁 创建新站点

```bash
hugo new site my-blog
cd my-blog
```

目录结构：

```
my-blog/
├── archetypes/      # 内容模板
├── content/        # 文章内容
├── layouts/        # 布局模板
├── static/         # 静态资源
├── themes/         # 主题
└── hugo.toml       # 配置文件
```

## 🎨 添加主题

推荐使用 hugo-theme-reimu 主题：

```bash
git init
git submodule add https://github.com/D-Sketon/hugo-theme-reimu.git themes/reimu
echo 'theme = "reimu"' >> hugo.toml
```

## ✏️ 编写文章

```bash
hugo new posts/my-first-post.md
```

编辑生成的文件：

```markdown
---
title: "我的第一篇文章"
date: 2024-01-01
draft: false
---

这里是文章内容...
```

## 🖥️ 本地预览

```bash
hugo server -D
```

访问 http://localhost:1313 查看效果。

## 🌐 部署到 GitHub Pages

### 1. 创建 GitHub 仓库

### 2. 添加 GitHub Actions 工作流

创建 `.github/workflows/hugo.yml`：

```yaml
name: Deploy Hugo site to Pages

on:
  push:
    branches: [main]

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      pages: write
      id-token: request

    steps:
      - uses: actions/checkout@v4

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v3

      - name: Build
        run: hugo --minify

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./public
```

### 3. 配置 GitHub Pages

在仓库 Settings → Pages → Source 选择 GitHub Actions。

## 📝 常用命令

| 命令 | 说明 |
|------|------|
| `hugo server` | 本地预览 |
| `hugo server -D` | 预览包含草稿 |
| `hugo` | 构建静态文件 |
| `hugo new posts/xxx.md` | 创建新文章 |
| `hugo new about.md` | 创建关于页 |

## 💡 小技巧

### 使用图床

推荐使用图床服务存放图片，如 SM.MS、ImgURL 等。

### 开启数学公式

在文章 front-matter 中添加：

```yaml
---
math: true
---
```

### 开启 Mermaid

```yaml
---
mermaid: true
---
```

## 🎯 写在最后

Hugo 博客搭建简单、功能强大，非常适合个人博主。希望这篇教程对你有帮助！

> 静待风起 🌬️