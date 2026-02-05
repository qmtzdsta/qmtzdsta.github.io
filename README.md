# qmtzdsta.github.io

个人博客网站 / Personal Blog Website

[![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-blue?logo=github)](https://qmtzdsta.github.io)
[![Hexo](https://img.shields.io/badge/Hexo-7.3.0-0E83CD?logo=hexo)](https://hexo.io/)
[![Website](https://img.shields.io/website?url=http%3A%2F%2F568923.xyz)](http://568923.xyz)

## 简介 / Introduction

这是使用 [Hexo](https://hexo.io/) 静态网站生成器构建的个人博客，托管在 GitHub Pages 上。

This is a personal blog built with [Hexo](https://hexo.io/) static site generator and hosted on GitHub Pages.

## 访问地址 / Website

- 🌐 主域名 / Primary Domain: [568923.xyz](http://568923.xyz)
- 🌐 GitHub Pages: [qmtzdsta.github.io](https://qmtzdsta.github.io)

## 技术栈 / Tech Stack

- **框架 / Framework**: Hexo 7.3.0
- **主题 / Theme**: Landscape (默认主题 / Default theme)
- **托管 / Hosting**: GitHub Pages
- **前端库 / Frontend**:
  - jQuery 3.6.4
  - Fork Awesome (Icons)
  - Fancybox (Image viewer)

## 项目结构 / Project Structure

```
.
├── 2025/           # 博客文章 / Blog posts
├── archives/       # 归档页面 / Archive pages
├── css/            # 样式文件 / Stylesheets
├── js/             # JavaScript 文件 / JavaScript files
├── fancybox/       # Fancybox 库 / Fancybox library
├── CNAME           # 自定义域名 / Custom domain
└── index.html      # 首页 / Homepage
```

## 功能特性 / Features

- ✅ 响应式设计 / Responsive design
- ✅ 文章归档 / Post archives
- ✅ RSS 订阅 / RSS feed
- ✅ 站内搜索 / Site search (Google)
- ✅ 社交分享 / Social sharing
- ✅ 图片灯箱 / Image lightbox

## 📝 如何添加文章 / How to Add Articles

### 快速开始 / Quick Start

```bash
# 1. 创建新文章 / Create new post
hexo new "文章标题"

# 2. 编辑文章 / Edit the article
# 打开 source/_posts/文章标题.md

# 3. 本地预览 / Preview locally
hexo server

# 4. 生成并部署 / Generate and deploy
hexo clean && hexo g -d
```

### 详细指南 / Detailed Guides

- 📖 **完整教程**: [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md) - 详细的文章添加指南
- ⚡ **快速参考**: [QUICK_START.md](./QUICK_START.md) - 常用命令速查表
- 🔄 **自动部署**: [.github/workflows/README.md](./.github/workflows/README.md) - GitHub Actions 自动部署

### 重要说明 / Important Note

⚠️ 本仓库只包含生成的静态文件。要添加文章，你需要：

1. 在本地或单独的分支维护 Hexo 源代码
2. 使用 `hexo new` 创建文章
3. 使用 `hexo generate` 生成静态文件
4. 将生成的文件推送到此仓库

详细说明请查看 [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md)

## 文档 / Documentation

- 📚 **项目分析**: [PROJECT_ANALYSIS.md](./PROJECT_ANALYSIS.md) - 完整的项目技术分析
- 📋 **项目总结**: [SUMMARY.md](./SUMMARY.md) - 快速了解项目状态
- 📝 **添加文章**: [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md) - 详细的文章添加教程
- ⚡ **快速入门**: [QUICK_START.md](./QUICK_START.md) - 快速参考和命令速查

## 关于 / About

- **作者 / Author**: qmtzdsta (去码头整点薯条啊)
- **创建日期 / Created**: 2025-07-24
- **许可证 / License**: 未指定 / Not specified

## 贡献 / Contributing

欢迎提出问题和建议！

Issues and suggestions are welcome!

## 联系方式 / Contact

- GitHub: [@qmtzdsta](https://github.com/qmtzdsta)

---

⚡ Powered by [Hexo](https://hexo.io/) & [GitHub Pages](https://pages.github.com/)
