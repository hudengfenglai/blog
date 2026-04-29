# 等风来

一个基于 Hugo 搭建的个人博客，当前使用 `hugo-theme-reimu`，并已经适配 GitHub Pages 项目站部署。

线上地址：

- `https://hudengfenglai.github.io/blog/`

## 技术栈

- Hugo Extended
- 主题：`hugo-theme-reimu`
- 部署：GitHub Pages + GitHub Actions

## 本地开发

启动本地预览：

```bash
hugo server
```

如果需要和线上构建保持一致，可以使用：

```bash
hugo --gc --minify --cacheDir .hugo_cache
```

构建产物会输出到：

- `public/`

## 文章写在哪里

日常博客文章写在：

- `content/post/`

例如：

- `content/post/my-first-post.md`
- `content/post/hugo-notes.md`

也可以直接让 Hugo 帮你创建：

```bash
hugo new post/my-first-post.md
```

创建后把文档里的 `draft` 改成 `false`，文章才会在首页、归档和文章页中显示。

推荐 front matter 示例：

```yaml
---
title: "我的第一篇文章"
date: 2026-04-16T20:00:00+08:00
draft: false
description: "一句简短摘要"
categories:
  - 学习笔记
tags:
  - Hugo
  - 博客
cover: "images/banner.webp"
---
```

正文就直接写在 front matter 下面，使用 Markdown 即可。

如果某篇文章需要单独管理图片，推荐使用 page bundle：

```text
content/post/my-post/
├─ index.md
├─ cover.png
└─ image-1.png
```

这样文章内图片可以和正文放在同一个目录里，后期整理更方便。

## 其他页面写在哪里

- 关于页：`content/about.md`
- 友链页：`content/friend.md`
- 归档页入口：`content/archives/_index.md`

友链数据在：

- `data/friends.yml`

## 站点结构

```text
blog/
├─ content/                  # 站点内容
│  ├─ about.md               # 关于页
│  ├─ friend.md              # 友链页
│  ├─ archives/_index.md     # 归档页
│  └─ post/                  # 博客文章
├─ data/                     # 站点数据
│  ├─ covers.yml
│  └─ friends.yml
├─ layouts/                  # Hugo 模板
├─ static/                   # 静态资源
│  ├─ avatar/
│  └─ images/
├─ themes/hugo-theme-reimu/  # 主题
├─ hugo.toml                 # 全站配置
└─ .github/workflows/        # GitHub Actions 部署配置
```

## 常用修改位置

站点基础配置：

- `hugo.toml`

首页专题卡、banner、社交链接等配置：

- `hugo.toml` 中的 `params.showcase.*`

分类专题封面图：

- `static/images/categories/`

头像：

- `static/avatar/avatar.jpg`

## 发布流程

推送到 `main` 后，GitHub Actions 会自动构建并发布到 GitHub Pages。

常用流程：

```bash
git add .
git commit -m "write new post"
git push origin main
```

部署日志查看位置：

- GitHub 仓库 `Actions`

## 当前约定

- 项目站部署路径是 `/blog/`
- `baseURL` 已配置为 `https://hudengfenglai.github.io/blog/`
- 首页文章流读取 `content/post/` 下的公开文章
- 归档页也基于 `content/post/` 自动生成

## 一句话说明

如果你只是想开始写博客，那么直接去 `content/post/` 新建 Markdown 文件就可以了。
