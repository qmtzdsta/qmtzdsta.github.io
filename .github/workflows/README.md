# GitHub Actions Workflow

这个目录包含用于自动部署 Hexo 博客的 GitHub Actions 工作流配置。

This directory contains GitHub Actions workflow configurations for automatically deploying the Hexo blog.

## 📄 文件说明 / File Description

### deploy.yml

自动部署工作流，用于将 Hexo 源代码自动生成并部署到 GitHub Pages。

Automatic deployment workflow for generating and deploying Hexo source code to GitHub Pages.

## 🚀 使用方法 / How to Use

### 前提条件 / Prerequisites

1. 创建 `source` 分支存放 Hexo 源代码
2. 在 `source` 分支的根目录中包含：
   - `_config.yml` - Hexo 配置文件
   - `package.json` - 依赖配置
   - `source/` - 源文件目录（包含文章）
   - `themes/` - 主题目录

### 工作流程 / Workflow

1. 在 `source` 分支创建或编辑文章
2. 提交并推送到 GitHub
3. GitHub Actions 自动触发工作流
4. 工作流自动：
   - 安装依赖
   - 生成静态文件
   - 部署到 `main` 分支
5. GitHub Pages 自动更新网站

### 分支结构 / Branch Structure

```
qmtzdsta.github.io/
├── main 分支           # 静态文件（自动生成）
│   ├── index.html
│   ├── archives/
│   ├── css/
│   └── ...
└── source 分支         # Hexo 源代码（手动维护）
    ├── _config.yml
    ├── package.json
    ├── source/
    │   └── _posts/
    └── themes/
```

## 🔧 配置说明 / Configuration

### 触发条件 / Trigger Conditions

工作流在以下情况触发：

1. 推送到 `source` 分支时
2. 手动触发（workflow_dispatch）

### 自定义域名 / Custom Domain

如果你使用自定义域名，在 `deploy.yml` 中修改：

```yaml
cname: 568923.xyz  # 改为你的域名
```

如果不使用自定义域名，删除或注释这一行。

### Node.js 版本 / Node.js Version

当前使用 Node.js 18，如需更改：

```yaml
node-version: '18'  # 改为 '16', '20' 等
```

## 📝 本地测试 / Local Testing

在推送前，建议本地测试：

```bash
# 1. 进入 source 分支
git checkout source

# 2. 安装依赖
npm install

# 3. 本地预览
hexo server

# 4. 生成静态文件测试
hexo clean
hexo generate

# 5. 确认无误后推送
git add .
git commit -m "Add new article"
git push origin source
```

## 🐛 故障排查 / Troubleshooting

### 工作流失败

1. 查看 GitHub Actions 日志：
   - 进入仓库的 Actions 标签页
   - 点击失败的工作流
   - 查看详细日志

2. 常见问题：
   - `package.json` 缺失或配置错误
   - `_config.yml` 配置错误
   - 依赖安装失败
   - 主题文件缺失

### 部署成功但网站未更新

1. 检查 `main` 分支是否有新的提交
2. 检查 GitHub Pages 设置：
   - Settings → Pages
   - Source: Deploy from a branch
   - Branch: main / (root)
3. 清除浏览器缓存
4. 等待几分钟（GitHub Pages 可能需要时间更新）

## 📚 相关文档 / Related Documentation

- [HOW_TO_ADD_ARTICLES.md](../HOW_TO_ADD_ARTICLES.md) - 详细的文章添加指南
- [QUICK_START.md](../QUICK_START.md) - 快速入门指南
- [GitHub Actions 文档](https://docs.github.com/en/actions)
- [Hexo 官方文档](https://hexo.io/zh-cn/docs/)

## 💡 提示 / Tips

1. **首次设置**：如果这是第一次设置工作流，请确保 `source` 分支已创建并包含完整的 Hexo 项目。

2. **权限问题**：GitHub Actions 使用内置的 `GITHUB_TOKEN`，无需额外配置。

3. **部署历史**：可以在 Actions 标签页查看所有部署历史和日志。

4. **手动触发**：在 Actions 标签页，选择工作流，点击 "Run workflow" 可手动触发部署。

---

**最后更新**: 2026-02-05
