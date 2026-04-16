# 等风来 - 个人博客

> 静待风起 | 疾风知劲草

[![Hugo](https://img.shields.io/badge/Hugo-Latest-blue.svg)](https://gohugo.io)
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()

这是一个基于 Hugo 的个人博客项目，采用简洁优雅的设计风格。

## 📋 项目概述

- **博客名称**：等风来
- **主题**：hugo-theme-reimu
- **语言**：简体中文
- **作者**：等风来
- **座右铭**：少女祈祷中... | 静待风起 | 疾风知劲草

## 🚀 快速开始

### 前置要求

- **Hugo** (Extended版本推荐)
  - 安装地址：https://gohugo.io/installation/

### 安装步骤

1. **克隆或下载项目**
```bash
cd e:\blog_hugo\blog
```

2. **启动本地开发服务器**
```bash
hugo server
```
然后在浏览器中访问 `http://localhost:1313`

### 编译生成静态网站

```bash
hugo
```

生成的静态文件将输出到 `public/` 目录，可直接用于部署。

## 📁 项目结构

```
blog/
├── archetypes/          # 文章模板
├── assets/              # 静态资源
├── content/             # 博客内容
│   ├── about.md         # 关于页面
│   ├── friend.md        # 友链页面
│   ├── archives/        # 档案/归档
│   └── post/            # 博客文章
├── data/                # 数据文件
│   ├── covers.yml       # 封面配置
│   ├── friends.yml      # 友链列表
│   └── vendor.yml       # 供应商信息
├── i18n/                # 国际化配置
├── layouts/             # 页面布局和模板
│   ├── 404.html         # 404 页面
│   ├── index.html       # 首页
│   ├── _default/        # 默认模板
│   ├── archives/        # 归档页面模板
│   ├── partials/        # 页面组件
│   └── shortcodes/      # 自定义短代码
├── static/              # 静态文件
│   ├── avatar/          # 头像
│   └── images/          # 图片资源
├── themes/              # 主题目录
│   └── hugo-theme-reimu/# 使用的主题
├── public/              # 生成的网站（部署用）
├── resources/           # 构建缓存
├── hugo.toml            # 项目配置文件
└── README.md            # 本文件
```

## ⚙️ 主要配置

### hugo.toml 配置说明

```toml
baseURL = 'https://example.org/'      # 网站网址
languageCode = 'zh-CN'                # 语言
defaultContentLanguage = 'zh-CN'      # 默认语言
title = '等风来'                       # 网站标题
theme = "hugo-theme-reimu"            # 使用主题

# 作者信息
[params]
  author = "等风来"
  subtitle = "少女祈祷中..."
  avatar = "avatar.jpg"               # 头像
  description = "静待风起 | 疾风知劲草"
  banner = "images/banner.webp"       # 首页横幅
```

## 📝 常见操作

### 创建新文章

```bash
hugo new post/文章标题.md
```

### 发布文章

编辑文章时，在 Front Matter 中设置：
```markdown
---
title: 文章标题
description: 文章描述
date: 2024-01-01T12:00:00+08:00
draft: false  # 改为 false 发布
---
```

### 修改配置

所有网站配置都在 `hugo.toml` 中。修改后，开发服务器会自动重新加载。

### 修改主题

主题文件位于 `themes/hugo-theme-reimu/`

## 🎨 主要功能

- ✅ 响应式设计，支持移动端
- ✅ 左侧侧边栏导航
- ✅ 文章分类和标签系统
- ✅ 友链功能
- ✅ 归档页面
- ✅ 暗黑模式支持（主题支持）
- ✅ SEO 优化

## 📦 部署

### 静态托管（GitHub Pages, Netlify 等）

1. 运行 `hugo` 生成静态文件
2. 将 `public/` 目录内容上传到托管平台
3. 部署完成

### 修改 baseURL

部署前，在 `hugo.toml` 中修改 `baseURL` 为实际网址：

```toml
baseURL = 'https://yourdomain.com/'
```

## 🛠️ 开发工作流

```bash
# 1. 启动本地服务器
hugo server

# 2. 编辑内容
# 编写或修改 content/ 中的文章

# 3. 实时预览
# 浏览器自动刷新，查看效果

# 4. 准备发布
# 确认所有文章 draft: false

# 5. 生成并部署
hugo
# 上传 public/ 到服务器
```

## 📚 更多信息

- [Hugo 官方文档](https://gohugo.io/documentation/)
- [Hugo Themes](https://themes.gohugo.io/)
- [hugo-theme-reimu 主题](https://github.com/D-Sketon/hugo-theme-reimu)

## 📄 许可证

MIT License

## 🙋 联系方式

- 博客地址：[等风来](https://example.org/)（修改 baseURL 后）
- 作者：等风来

---

**祝你写博客愉快！** ✨
