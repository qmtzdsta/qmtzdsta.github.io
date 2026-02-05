# 📝 如何添加文章 - 完整解决方案

## 问题回答 / Answer to Your Question

**问题**: 我该怎么去添加我的文章呢？

**答案**: 我已经为你创建了完整的添加文章指南！请查看以下文档。

---

## 📚 文档导航 / Documentation Guide

### 🚀 快速开始（推荐先看这个）

**文件**: [QUICK_START.md](./QUICK_START.md)

这是**最快上手的文档**，包含：
- ✅ 一次性设置步骤
- ✅ 日常写作流程
- ✅ 常用命令速查表
- ✅ 文章模板
- ✅ 故障排查

**适合人群**: 想快速开始写作的用户

---

### 📖 详细教程（完整指南）

**文件**: [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md)

这是**最详细的文档**（13KB），包含：
- ✅ 三种完整方案对比
- ✅ Hexo 安装和配置
- ✅ 文章写作指南
- ✅ Markdown 语法详解
- ✅ 常见问题解答
- ✅ 推荐资源

**适合人群**: 第一次使用 Hexo 或需要深入了解的用户

---

### ⚡ 自动部署方案（最佳实践）

**文件**: [.github/workflows/deploy.yml](./.github/workflows/deploy.yml)

这是**自动化部署配置**，实现：
- ✅ 推送代码自动部署
- ✅ 无需手动生成和推送
- ✅ 源代码和静态文件分离

**使用说明**: [.github/workflows/README.md](./.github/workflows/README.md)

**适合人群**: 想要完全自动化部署的用户

---

### 📝 文章模板示例

**文件**: [examples/article-template.md](./examples/article-template.md)

这是**完整的文章模板**，展示：
- ✅ Front Matter 配置
- ✅ 各种 Markdown 语法
- ✅ 代码块、表格、图片等
- ✅ 特殊功能使用

**适合人群**: 需要参考 Markdown 语法的用户

---

## 🎯 三种方案对比 / Three Approaches Comparison

### 方案一：本地 Hexo + 手动部署

**优点**: 简单直接  
**缺点**: 每次都要手动操作  
**适合**: 偶尔更新博客的用户

**步骤**:
```bash
hexo new "文章标题"    # 创建文章
hexo server            # 预览
hexo g -d              # 生成并部署
```

---

### 方案二：分支管理 + 手动部署

**优点**: 源代码有备份  
**缺点**: 需要手动部署  
**适合**: 重视源代码管理的用户

**步骤**:
```bash
git checkout source    # 切换到源代码分支
hexo new "文章标题"    # 创建文章
git add . && git commit -m "..." && git push
hexo g -d              # 生成并部署
```

---

### 方案三：GitHub Actions 自动部署 ⭐ 推荐

**优点**: 完全自动化，推送即部署  
**缺点**: 需要配置 GitHub Actions  
**适合**: 经常更新博客的用户

**步骤**:
```bash
git checkout source    # 切换到源代码分支
hexo new "文章标题"    # 创建文章
git add . && git commit -m "..." && git push
# 自动触发部署！无需其他操作
```

---

## 💡 快速决策指南 / Quick Decision Guide

### 如果你...

#### 🆕 第一次使用 Hexo
1. 阅读 [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md) 了解完整流程
2. 按照"方案一"开始
3. 熟悉后升级到"方案三"

#### ⚡ 想要最快开始
1. 阅读 [QUICK_START.md](./QUICK_START.md)
2. 复制 [examples/article-template.md](./examples/article-template.md) 作为模板
3. 使用"方案一"快速上手

#### 🚀 想要自动化部署
1. 阅读 [.github/workflows/README.md](./.github/workflows/README.md)
2. 创建 `source` 分支
3. 配置 GitHub Actions（已提供配置文件）
4. 推送即自动部署

#### 📚 想要深入学习
1. 完整阅读 [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md)
2. 研究 [examples/article-template.md](./examples/article-template.md)
3. 访问 [Hexo 官方文档](https://hexo.io/zh-cn/docs/)

---

## 📋 核心步骤总结 / Core Steps Summary

### 一次性设置（只需做一次）

```bash
# 1. 安装 Hexo
npm install -g hexo-cli

# 2. 创建项目
mkdir my-blog && cd my-blog
hexo init
npm install

# 3. 配置 _config.yml
# - 修改 title, author, url
# - 配置 deploy 部分
```

### 日常写作（每次写文章）

```bash
# 1. 创建文章
hexo new "文章标题"

# 2. 编辑文章
# 在 source/_posts/文章标题.md 中编写

# 3. 预览
hexo server

# 4. 部署
hexo clean && hexo g -d
```

---

## ❓ 常见问题快速解答 / Quick FAQ

### Q: 我没有 Hexo 源代码怎么办？
**A**: 按照 [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md) 的"方案一"创建新的 Hexo 项目。

### Q: 如何修改网站标题和作者信息？
**A**: 编辑 Hexo 项目中的 `_config.yml` 文件。

### Q: 文章写好后如何发布？
**A**: 使用 `hexo generate` 生成静态文件，然后用 `hexo deploy` 部署。

### Q: 可以自动部署吗？
**A**: 可以！使用 [GitHub Actions](./.github/workflows/README.md) 实现自动部署。

### Q: 如何添加图片？
**A**: 参考 [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md) 中的"资源文件"部分。

### Q: Markdown 语法怎么写？
**A**: 查看 [examples/article-template.md](./examples/article-template.md) 模板示例。

---

## 🛠️ 推荐工具 / Recommended Tools

### Markdown 编辑器
- **VS Code** + Markdown Preview Enhanced
- **Typora** - 所见即所得
- **MarkText** - 开源免费

### Hexo 主题推荐
- **NexT** - 最受欢迎
- **Fluid** - Material Design
- **Butterfly** - 功能丰富

---

## 📞 获取帮助 / Get Help

### 本项目文档
- [PROJECT_ANALYSIS.md](./PROJECT_ANALYSIS.md) - 项目分析
- [SUMMARY.md](./SUMMARY.md) - 项目总结
- [README.md](./README.md) - 项目说明

### 外部资源
- [Hexo 官方文档](https://hexo.io/zh-cn/docs/)
- [Hexo GitHub](https://github.com/hexojs/hexo)
- [Hexo 社区](https://discuss.hexo.io/)

---

## 🎉 开始写作 / Start Writing

选择最适合你的方案，开始你的博客之旅！

1. 📖 完整学习 → [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md)
2. ⚡ 快速开始 → [QUICK_START.md](./QUICK_START.md)
3. 🚀 自动部署 → [.github/workflows/README.md](./.github/workflows/README.md)
4. 📝 参考模板 → [examples/article-template.md](./examples/article-template.md)

---

**创建日期**: 2026-02-05  
**文档版本**: 1.0

祝你写作愉快！✨
