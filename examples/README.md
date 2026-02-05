# 示例文件 / Example Files

这个目录包含各种示例文件，帮助你快速上手 Hexo 博客写作。

This directory contains various example files to help you get started with Hexo blog writing.

## 📄 文件列表 / File List

### article-template.md

**完整的文章模板示例**，展示：

- ✅ Front Matter 配置
- ✅ 各种 Markdown 语法
- ✅ 代码块示例
- ✅ 图片和链接
- ✅ 表格和列表
- ✅ 特殊功能（需主题支持）

**使用方法 / Usage**:

1. 复制这个文件到你的 Hexo 项目的 `source/_posts/` 目录
2. 修改 Front Matter（标题、日期、标签等）
3. 替换示例内容为你自己的内容
4. 保存并使用 `hexo generate` 生成

或者直接作为参考，查看各种 Markdown 语法的使用方式。

## 🚀 快速使用 / Quick Start

如果你已经设置好 Hexo 环境：

```bash
# 1. 复制模板到你的 Hexo 项目
cp examples/article-template.md /path/to/your/hexo/source/_posts/my-new-article.md

# 2. 编辑文章
# 使用你喜欢的编辑器打开并修改

# 3. 预览
hexo server

# 4. 生成并部署
hexo clean
hexo g -d
```

## 💡 提示 / Tips

### 创建自己的模板

你可以创建自己的文章模板：

1. 在 Hexo 项目中创建 `scaffolds/post.md`
2. 添加你常用的 Front Matter 配置
3. 使用 `hexo new "文章标题"` 时会自动使用这个模板

示例 `scaffolds/post.md`:

```markdown
---
title: {{ title }}
date: {{ date }}
tags:
categories:
description:
---

文章摘要...

<!-- more -->

正文内容...
```

### Markdown 编辑器推荐

- **VS Code** + Markdown Preview Enhanced 插件
- **Typora** - 所见即所得的 Markdown 编辑器
- **MarkText** - 开源的 Markdown 编辑器
- **Obsidian** - 强大的知识管理工具

### 在线 Markdown 工具

- [Markdown Guide](https://www.markdownguide.org/) - Markdown 语法指南
- [Tables Generator](https://www.tablesgenerator.com/markdown_tables) - 表格生成器
- [Carbon](https://carbon.now.sh/) - 代码截图工具

## 📚 相关文档 / Related Documentation

- [HOW_TO_ADD_ARTICLES.md](../HOW_TO_ADD_ARTICLES.md) - 详细的文章添加教程
- [QUICK_START.md](../QUICK_START.md) - 快速参考指南
- [Hexo 官方文档](https://hexo.io/zh-cn/docs/writing.html) - 官方写作指南

## 🎨 更多示例

如果你需要更多示例：

1. 查看 Hexo 主题的 Demo 网站
2. 浏览其他 Hexo 博客的源代码
3. 访问 [Hexo 官方示例](https://hexo.io/zh-cn/docs/tag-plugins.html)

---

**最后更新**: 2026-02-05

愉快写作！✨
