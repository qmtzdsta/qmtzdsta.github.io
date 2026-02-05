# 如何添加文章 / How to Add Articles

本文档详细说明如何为你的 Hexo 博客添加新文章。

This document explains how to add new articles to your Hexo blog.

---

## 📋 目录 / Table of Contents

1. [重要说明](#重要说明)
2. [方案一：设置 Hexo 源代码环境（推荐）](#方案一设置-hexo-源代码环境推荐)
3. [方案二：手动创建 HTML 文件（不推荐）](#方案二手动创建-html-文件不推荐)
4. [方案三：使用 GitHub Actions 自动部署（最佳方案）](#方案三使用-github-actions-自动部署最佳方案)
5. [文章写作指南](#文章写作指南)
6. [常见问题](#常见问题)

---

## 🔔 重要说明

### 当前情况

你的仓库 `qmtzdsta.github.io` **只包含生成后的静态 HTML 文件**，没有 Hexo 的源代码。这意味着：

- ❌ 无法直接在此仓库中使用 `hexo new` 命令
- ❌ 没有 `_config.yml` 配置文件
- ❌ 没有 `source/` 目录存放 Markdown 文章
- ❌ 没有 `themes/` 目录

### 推荐方案

**你需要在本地或另一个分支/仓库中维护 Hexo 源代码**，然后将生成的静态文件推送到此仓库。

---

## 方案一：设置 Hexo 源代码环境（推荐）

### 步骤 1：安装 Node.js 和 Hexo

```bash
# 1. 确保已安装 Node.js (https://nodejs.org/)
node --version  # 应该显示版本号，如 v18.x.x

# 2. 全局安装 Hexo CLI
npm install -g hexo-cli

# 3. 验证安装
hexo version
```

### 步骤 2：创建 Hexo 项目

有两种方式：

#### 方式 A：创建新的 Hexo 项目（推荐）

```bash
# 1. 创建新项目目录
mkdir hexo-blog-source
cd hexo-blog-source

# 2. 初始化 Hexo 项目
hexo init .
npm install

# 3. 查看项目结构
ls -la
# 你会看到：
# _config.yml     - 站点配置文件
# source/         - 源文件目录（存放 Markdown 文章）
# themes/         - 主题目录
# package.json    - 依赖配置
```

#### 方式 B：使用现有的 Hexo 项目

如果你之前在其他地方创建过这个博客的源代码，直接找到那个目录使用即可。

### 步骤 3：配置 Hexo

编辑 `_config.yml` 文件：

```yaml
# 站点信息
title: 你的博客标题
subtitle: 副标题
description: 博客描述
keywords: 关键词1, 关键词2
author: 你的名字
language: zh-CN
timezone: Asia/Shanghai

# URL 配置
url: http://568923.xyz
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:
pretty_urls:
  trailing_index: true
  trailing_html: true

# 部署配置
deploy:
  type: git
  repo: https://github.com/qmtzdsta/qmtzdsta.github.io.git
  branch: main
```

### 步骤 4：创建新文章

```bash
# 创建新文章
hexo new "我的第一篇文章"

# 或使用缩写
hexo n "我的第一篇文章"

# 这会在 source/_posts/ 目录下创建一个 Markdown 文件
```

文件会自动生成以下结构：

```markdown
---
title: 我的第一篇文章
date: 2025-07-24 17:30:00
tags:
---

在这里写文章内容...
```

### 步骤 5：编写文章内容

打开生成的 Markdown 文件（位于 `source/_posts/` 目录），添加内容：

```markdown
---
title: 我的第一篇文章
date: 2025-07-24 17:30:00
tags: 
  - 教程
  - Hexo
categories: 
  - 技术
---

# 文章标题

这是文章的第一段内容。

## 小节标题

- 列表项 1
- 列表项 2

## 代码示例

\`\`\`javascript
console.log("Hello, World!");
\`\`\`

## 插入图片

![图片描述](图片URL)

<!-- more -->  # 这个标记之前的内容会显示在首页摘要中
```

### 步骤 6：本地预览

```bash
# 启动本地服务器
hexo server

# 或使用缩写
hexo s

# 默认访问地址：http://localhost:4000
```

在浏览器中打开 `http://localhost:4000` 查看效果。

### 步骤 7：生成静态文件

```bash
# 清除缓存
hexo clean

# 生成静态文件
hexo generate

# 或使用缩写
hexo g

# 生成的文件在 public/ 目录中
```

### 步骤 8：部署到 GitHub Pages

有两种方式：

#### 方式 A：使用 Hexo 部署插件（推荐）

```bash
# 1. 安装部署插件
npm install hexo-deployer-git --save

# 2. 确保 _config.yml 中配置了 deploy 部分
# deploy:
#   type: git
#   repo: https://github.com/qmtzdsta/qmtzdsta.github.io.git
#   branch: main

# 3. 一键部署
hexo deploy

# 或使用缩写
hexo d

# 或生成并部署
hexo g -d
```

#### 方式 B：手动复制文件

```bash
# 1. 生成静态文件
hexo generate

# 2. 进入 public 目录
cd public

# 3. 初始化 git（如果需要）
git init
git add .
git commit -m "Update blog"

# 4. 推送到 GitHub
git remote add origin https://github.com/qmtzdsta/qmtzdsta.github.io.git
git push -f origin main
```

---

## 方案二：手动创建 HTML 文件（不推荐）

如果你不想使用 Hexo 源代码，可以手动创建 HTML 文件，但这**非常不推荐**，因为：

- ❌ 需要手动维护所有 HTML 结构
- ❌ 需要手动更新索引页面
- ❌ 需要手动更新归档页面
- ❌ 失去了 Hexo 的便利性

### 手动创建步骤

1. 在 `2025/` 目录下创建相应的日期目录
2. 创建文章目录，如 `2025/07/25/my-article/`
3. 在文章目录中创建 `index.html`
4. 复制现有文章的 HTML 结构，修改内容
5. 手动更新 `index.html`、`archives/index.html` 等文件

**这种方式工作量大且容易出错，强烈建议使用方案一或方案三。**

---

## 方案三：使用 GitHub Actions 自动部署（最佳方案）

### 优点

- ✅ 自动化部署流程
- ✅ 源代码和静态文件分离
- ✅ 无需手动生成和推送
- ✅ 支持多人协作

### 实现步骤

#### 1. 创建源代码分支

```bash
# 在本地 Hexo 项目中
git init
git checkout -b source  # 创建 source 分支存放源代码

# 添加 .gitignore
cat > .gitignore << EOF
.DS_Store
Thumbs.db
db.json
*.log
node_modules/
public/
.deploy*/
EOF

# 提交源代码
git add .
git commit -m "Initial Hexo source"
git remote add origin https://github.com/qmtzdsta/qmtzdsta.github.io.git
git push origin source
```

#### 2. 创建 GitHub Actions 工作流

在 Hexo 项目根目录创建 `.github/workflows/deploy.yml`：

```yaml
name: Deploy Hexo to GitHub Pages

on:
  push:
    branches:
      - source  # 当推送到 source 分支时触发

jobs:
  deploy:
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout source
      uses: actions/checkout@v3
      with:
        ref: source
    
    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'
    
    - name: Install dependencies
      run: |
        npm install
        npm install hexo-cli -g
    
    - name: Generate static files
      run: |
        hexo clean
        hexo generate
    
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./public
        publish_branch: main  # 部署到 main 分支
        cname: 568923.xyz     # 你的自定义域名
```

#### 3. 使用流程

```bash
# 1. 在 source 分支工作
git checkout source

# 2. 创建新文章
hexo new "新文章标题"

# 3. 编写文章
# 编辑 source/_posts/新文章标题.md

# 4. 提交并推送
git add .
git commit -m "Add new article: 新文章标题"
git push origin source

# 5. GitHub Actions 会自动：
#    - 生成静态文件
#    - 部署到 main 分支
#    - 更新网站
```

#### 4. 分支说明

- `source` 分支：存放 Hexo 源代码（Markdown 文章、配置文件、主题等）
- `main` 分支：存放生成的静态 HTML 文件（由 GitHub Actions 自动生成）

---

## 📝 文章写作指南

### Front Matter（文章头部信息）

每篇文章开头需要包含 Front Matter：

```markdown
---
title: 文章标题
date: 2025-07-24 17:30:00
updated: 2025-07-25 10:00:00  # 可选：更新时间
tags:                          # 可选：标签
  - 标签1
  - 标签2
categories:                    # 可选：分类
  - 分类名称
description: 文章摘要描述      # 可选：用于 SEO
keywords: 关键词1, 关键词2    # 可选：用于 SEO
top: false                     # 可选：是否置顶
cover: /images/cover.jpg       # 可选：封面图
---
```

### Markdown 语法

#### 标题

```markdown
# 一级标题
## 二级标题
### 三级标题
```

#### 文本格式

```markdown
**粗体文字**
*斜体文字*
~~删除线~~
`行内代码`
```

#### 列表

```markdown
# 无序列表
- 项目 1
- 项目 2
  - 子项目 2.1
  - 子项目 2.2

# 有序列表
1. 第一项
2. 第二项
3. 第三项
```

#### 链接和图片

```markdown
# 链接
[链接文字](https://example.com)

# 图片
![图片描述](图片URL)

# 图片带链接
[![图片描述](图片URL)](链接URL)
```

#### 代码块

```markdown
\`\`\`javascript
function hello() {
  console.log("Hello, World!");
}
\`\`\`

\`\`\`python
def hello():
    print("Hello, World!")
\`\`\`
```

#### 引用

```markdown
> 这是一段引用文字
> 可以有多行
```

#### 表格

```markdown
| 列1 | 列2 | 列3 |
| --- | --- | --- |
| 内容1 | 内容2 | 内容3 |
| 内容4 | 内容5 | 内容6 |
```

#### 分隔线

```markdown
---
或
***
```

### 摘要设置

使用 `<!-- more -->` 标记来设置首页显示的摘要内容：

```markdown
---
title: 文章标题
date: 2025-07-24 17:30:00
---

这是文章的摘要部分，会在首页显示。

<!-- more -->

这是文章的详细内容，只有点击"阅读更多"后才能看到。
```

### 资源文件（图片、附件等）

#### 方法 1：使用图床

推荐使用图床服务（如 GitHub、七牛云、阿里云 OSS 等）：

```markdown
![图片描述](https://图床URL/image.jpg)
```

#### 方法 2：使用资源文件夹

在 `_config.yml` 中启用：

```yaml
post_asset_folder: true
```

然后：

```bash
hexo new "文章标题"
# 会同时创建：
# source/_posts/文章标题.md
# source/_posts/文章标题/  （资源文件夹）
```

在文章中引用：

```markdown
{% asset_img example.jpg 这是示例图片 %}
```

---

## 🛠️ 常用 Hexo 命令

```bash
# 创建新文章
hexo new "文章标题"
hexo n "文章标题"

# 创建新页面
hexo new page "页面名称"

# 创建草稿
hexo new draft "草稿标题"

# 发布草稿
hexo publish "草稿标题"

# 清除缓存
hexo clean

# 生成静态文件
hexo generate
hexo g

# 启动本地服务器
hexo server
hexo s

# 启动本地服务器（草稿模式）
hexo s --draft

# 部署
hexo deploy
hexo d

# 生成并部署
hexo g -d

# 查看版本
hexo version
```

---

## ❓ 常见问题

### Q1: 我没有 Hexo 源代码怎么办？

**A**: 你需要创建一个新的 Hexo 项目，按照**方案一**的步骤操作。生成的静态文件需要推送到 `qmtzdsta.github.io` 仓库。

### Q2: 如何找回之前的 Hexo 源代码？

**A**: 检查以下位置：
- 本地电脑的其他目录
- 其他分支（运行 `git branch -a` 查看）
- 其他 Git 仓库
- 云盘或备份

### Q3: 可以在 qmtzdsta.github.io 仓库直接添加源代码吗？

**A**: 可以，但建议使用分支分离：
- `source` 分支：存放 Hexo 源代码
- `main` 分支：存放生成的静态文件

### Q4: 如何更改主题？

**A**: 
```bash
# 1. 下载主题到 themes 目录
cd themes
git clone https://github.com/theme-next/hexo-theme-next next

# 2. 修改 _config.yml
theme: next

# 3. 重新生成
hexo clean
hexo g
```

### Q5: 文章不显示怎么办？

**A**: 检查：
- 文件是否在 `source/_posts/` 目录
- Front Matter 格式是否正确
- 是否运行了 `hexo clean` 和 `hexo generate`
- 本地预览是否正常（`hexo server`）

### Q6: 如何设置文章置顶？

**A**: 
1. 安装置顶插件：`npm install hexo-generator-index-pin-top --save`
2. 在文章 Front Matter 中添加：`top: true`

### Q7: 如何添加分类和标签页面？

**A**:
```bash
# 创建分类页面
hexo new page categories
# 编辑 source/categories/index.md，添加 type: "categories"

# 创建标签页面
hexo new page tags
# 编辑 source/tags/index.md，添加 type: "tags"
```

### Q8: 如何优化 SEO？

**A**:
- 在 `_config.yml` 中配置 `description` 和 `keywords`
- 在每篇文章 Front Matter 中添加 `description` 和 `keywords`
- 安装 `hexo-generator-sitemap` 生成站点地图
- 安装 `hexo-generator-feed` 生成 RSS

---

## 📚 推荐资源

### 官方文档
- [Hexo 官方文档（中文）](https://hexo.io/zh-cn/docs/)
- [Hexo 官方文档（英文）](https://hexo.io/docs/)

### 主题推荐
- [NexT](https://github.com/theme-next/hexo-theme-next) - 最受欢迎的主题
- [Fluid](https://github.com/fluid-dev/hexo-theme-fluid) - 优雅的 Material Design 风格
- [Butterfly](https://github.com/jerryc127/hexo-theme-butterfly) - 功能丰富
- [Matery](https://github.com/blinkfox/hexo-theme-matery) - Material Design 风格
- [更多主题](https://hexo.io/themes/)

### 插件推荐
- `hexo-generator-sitemap` - 生成站点地图
- `hexo-generator-feed` - 生成 RSS
- `hexo-deployer-git` - Git 部署插件
- `hexo-asset-image` - 图片资源管理
- `hexo-wordcount` - 字数统计
- `hexo-abbrlink` - 永久链接

### 学习资源
- [Hexo 博客搭建教程](https://www.cnblogs.com/fengxiongZz/p/7707219.html)
- [Hexo + GitHub Pages 搭建个人博客](https://juejin.cn/post/6844903843096346632)

---

## 📞 需要帮助？

如果你在添加文章过程中遇到问题：

1. 查看 [Hexo 官方文档](https://hexo.io/zh-cn/docs/)
2. 搜索 [Hexo GitHub Issues](https://github.com/hexojs/hexo/issues)
3. 访问 [Hexo 社区](https://discuss.hexo.io/)
4. 查看本仓库的其他文档：
   - [PROJECT_ANALYSIS.md](./PROJECT_ANALYSIS.md)
   - [SUMMARY.md](./SUMMARY.md)
   - [README.md](./README.md)

---

**最后更新**: 2026-02-05
**文档版本**: 1.0

祝你写作愉快！✨
