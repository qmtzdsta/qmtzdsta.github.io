# 快速参考：添加文章 / Quick Reference: Adding Articles

## 🚀 最快上手方式 / Quickest Way to Start

### 第一次使用 / First Time Setup

```bash
# 1. 安装 Hexo
npm install -g hexo-cli

# 2. 创建博客源代码目录
mkdir my-hexo-blog
cd my-hexo-blog
hexo init
npm install

# 3. 配置站点信息（编辑 _config.yml）
# - title: 你的博客名
# - author: 你的名字  
# - url: http://568923.xyz

# 4. 配置部署（在 _config.yml 末尾添加）
deploy:
  type: git
  repo: https://github.com/qmtzdsta/qmtzdsta.github.io.git
  branch: main
```

### 日常写作流程 / Daily Writing Workflow

```bash
# 1. 创建新文章
hexo new "文章标题"

# 2. 编辑文章
# 打开 source/_posts/文章标题.md 文件进行编辑

# 3. 本地预览
hexo server
# 访问 http://localhost:4000 查看效果

# 4. 生成并部署
hexo clean
hexo generate
hexo deploy
```

## 📝 文章模板 / Article Template

```markdown
---
title: 文章标题
date: 2025-07-24 17:30:00
tags:
  - 标签1
  - 标签2
categories:
  - 分类名称
description: 这是文章的简短描述，用于 SEO 和摘要
---

文章摘要内容，会显示在首页。

<!-- more -->

# 正文标题

这里是文章的详细内容。

## 小节标题

内容...

\`\`\`javascript
// 代码示例
console.log("Hello World");
\`\`\`

![图片描述](图片URL)
```

## ⚡ 常用命令速查 / Command Cheatsheet

| 命令 | 说明 | 缩写 |
|------|------|------|
| `hexo new "标题"` | 创建新文章 | `hexo n "标题"` |
| `hexo new page "页面"` | 创建新页面 | - |
| `hexo generate` | 生成静态文件 | `hexo g` |
| `hexo server` | 启动本地服务器 | `hexo s` |
| `hexo deploy` | 部署到远程 | `hexo d` |
| `hexo clean` | 清除缓存 | - |
| `hexo g -d` | 生成并部署 | - |

## 🎯 推荐工作流程 / Recommended Workflows

### 方案 A：本地开发 + 手动部署

```bash
cd my-hexo-blog         # 进入源代码目录
hexo new "新文章"       # 创建文章
# 编辑文章...
hexo s                  # 预览
hexo g -d               # 生成并部署
```

**优点**: 简单直接  
**缺点**: 需要手动操作

### 方案 B：分支管理 + 手动部署

```bash
# 初始化设置
git clone https://github.com/qmtzdsta/qmtzdsta.github.io.git
cd qmtzdsta.github.io
git checkout -b source   # 创建 source 分支
# 添加 Hexo 源代码到这个分支

# 日常使用
git checkout source      # 切换到源代码分支
hexo new "新文章"        # 创建文章
# 编辑文章...
git add .
git commit -m "Add new article"
git push origin source   # 推送源代码
hexo g -d                # 生成并部署到 main 分支
```

**优点**: 源代码和静态文件分离，易于管理  
**缺点**: 需要手动部署

### 方案 C：GitHub Actions 自动部署（最佳）

```bash
# 日常使用
git checkout source      # 在 source 分支工作
hexo new "新文章"        # 创建文章
# 编辑文章...
git add .
git commit -m "Add new article"
git push origin source   # 推送后自动触发部署
```

**优点**: 完全自动化，推送即部署  
**缺点**: 需要配置 GitHub Actions

详细配置见 [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md) 中的方案三。

## 🔧 故障排查 / Troubleshooting

### 问题：文章不显示

```bash
# 解决方案
hexo clean              # 清除缓存
hexo generate           # 重新生成
hexo server            # 本地测试
```

### 问题：部署失败

```bash
# 检查配置
cat _config.yml | grep -A 5 "deploy:"

# 重新安装部署插件
npm install hexo-deployer-git --save

# 重新部署
hexo clean
hexo g -d
```

### 问题：本地预览正常，部署后样式丢失

检查 `_config.yml` 中的 URL 配置：
```yaml
url: http://568923.xyz  # 确保使用你的实际域名
root: /                  # 确保根路径正确
```

## 📁 目录结构参考 / Directory Structure

```
my-hexo-blog/           # Hexo 源代码目录
├── _config.yml         # 站点配置文件
├── package.json        # 依赖配置
├── source/             # 源文件目录
│   ├── _posts/        # 文章目录（Markdown 文件）
│   │   ├── article1.md
│   │   └── article2.md
│   ├── about/         # 关于页面
│   └── images/        # 图片资源
├── themes/            # 主题目录
│   └── landscape/     # 默认主题
├── public/            # 生成的静态文件（部署这个）
└── node_modules/      # 依赖包
```

## 🌟 进阶技巧 / Advanced Tips

### 文章置顶

```markdown
---
title: 重要文章
top: true              # 置顶
sticky: 100            # 置顶权重（数字越大越靠前）
---
```

### 文章加密

安装插件：
```bash
npm install hexo-blog-encrypt --save
```

在文章中添加：
```markdown
---
title: 私密文章
password: 123456       # 访问密码
abstract: 这是加密文章
message: 请输入密码访问
---
```

### 草稿管理

```bash
# 创建草稿
hexo new draft "草稿标题"

# 预览草稿
hexo server --draft

# 发布草稿
hexo publish "草稿标题"
```

## 🔗 相关链接 / Related Links

- **详细教程**: [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md)
- **项目分析**: [PROJECT_ANALYSIS.md](./PROJECT_ANALYSIS.md)
- **项目总结**: [SUMMARY.md](./SUMMARY.md)
- **Hexo 官方文档**: https://hexo.io/zh-cn/docs/

---

**提示**: 如果这是你第一次使用 Hexo，建议完整阅读 [HOW_TO_ADD_ARTICLES.md](./HOW_TO_ADD_ARTICLES.md) 文档。
