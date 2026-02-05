---
title: 文章模板示例
date: 2025-07-24 17:30:00
updated: 2025-07-25 10:00:00
tags:
  - 示例
  - 教程
  - Markdown
categories:
  - 技术文档
description: 这是一篇示例文章，展示如何使用 Markdown 编写 Hexo 博客文章
keywords: Hexo, Markdown, 博客, 教程
top: false
cover: /images/cover.jpg
---

这是文章的摘要部分，会显示在首页。建议简短描述文章内容，吸引读者点击阅读。

摘要可以包含多个段落。使用 `<!-- more -->` 标记来分隔摘要和正文。

<!-- more -->

# 正文开始

这里是文章的详细内容。下面展示各种 Markdown 语法的使用。

## 文本格式

### 基本格式

这是**粗体文字**，这是*斜体文字*，这是~~删除线~~。

这是`行内代码`示例。

### 引用

> 这是一段引用文字。
> 
> 引用可以包含多个段落。
> 
> —— 作者名

### 列表

#### 无序列表

- 第一项
- 第二项
  - 子项 2.1
  - 子项 2.2
    - 子子项 2.2.1
- 第三项

#### 有序列表

1. 第一步
2. 第二步
3. 第三步

#### 任务列表

- [x] 已完成的任务
- [x] 另一个已完成的任务
- [ ] 待完成的任务
- [ ] 另一个待完成的任务

## 链接和图片

### 链接

这是一个[内联链接](https://hexo.io/)。

这是一个[带标题的链接](https://hexo.io/ "Hexo 官网")。

### 图片

![图片描述文字](https://via.placeholder.com/800x400)

*图片标注：这是图片的说明文字*

### 图片链接

[![点击查看大图](https://via.placeholder.com/400x200)](https://via.placeholder.com/800x400)

## 代码示例

### 行内代码

使用 `console.log()` 输出信息。

### 代码块

#### JavaScript

\`\`\`javascript
// JavaScript 代码示例
function greet(name) {
  console.log(\`Hello, \${name}!\`);
}

greet('World');
\`\`\`

#### Python

\`\`\`python
# Python 代码示例
def greet(name):
    print(f"Hello, {name}!")

greet('World')
\`\`\`

#### HTML

\`\`\`html
<!DOCTYPE html>
<html>
<head>
  <title>示例页面</title>
</head>
<body>
  <h1>Hello, World!</h1>
</body>
</html>
\`\`\`

#### Shell/Bash

\`\`\`bash
# 安装 Hexo
npm install -g hexo-cli

# 创建新文章
hexo new "文章标题"

# 本地预览
hexo server
\`\`\`

## 表格

### 基本表格

| 列1标题 | 列2标题 | 列3标题 |
| ------- | ------- | ------- |
| 内容1   | 内容2   | 内容3   |
| 内容4   | 内容5   | 内容6   |
| 内容7   | 内容8   | 内容9   |

### 对齐表格

| 左对齐 | 居中对齐 | 右对齐 |
| :---- | :------: | -----: |
| 内容A | 内容B   | 内容C |
| 内容D | 内容E   | 内容F |

### 复杂表格

| 功能 | 说明 | 状态 |
| --- | --- | --- |
| 响应式设计 | 适配移动端和桌面端 | ✅ 已实现 |
| 文章归档 | 按时间归档文章 | ✅ 已实现 |
| RSS 订阅 | 提供 RSS 源 | ✅ 已实现 |
| 评论系统 | 支持读者评论 | ⏳ 计划中 |

## 分隔线

---

上面是一条分隔线。

***

这也是一条分隔线。

## 特殊内容

### 提示框（需要主题支持）

{% note info %}
这是一个提示信息框。
{% endnote %}

{% note warning %}
这是一个警告信息框。
{% endnote %}

{% note danger %}
这是一个危险信息框。
{% endnote %}

### 标签页（需要主题支持）

{% tabs 示例标签页 %}
<!-- tab 标签1 -->
这是标签1的内容。
<!-- endtab -->

<!-- tab 标签2 -->
这是标签2的内容。
<!-- endtab -->

<!-- tab 标签3 -->
这是标签3的内容。
<!-- endtab -->
{% endtabs %}

### 折叠内容（需要主题支持）

{% fold 点击展开 %}
这是折叠的内容，点击标题才会显示。
{% endfold %}

## 数学公式（需要插件）

### 行内公式

这是一个行内公式：$E = mc^2$

### 块级公式

$$
\frac{n!}{k!(n-k)!} = \binom{n}{k}
$$

$$
\int_{a}^{b} f(x) dx
$$

## 嵌入内容

### YouTube 视频（需要插件）

{% youtube video_id %}

### Bilibili 视频（需要插件）

{% bilibili BV1xx411c7mD %}

## 脚注

这是一段包含脚注的文字[^1]。

这是另一个脚注[^2]。

[^1]: 这是第一个脚注的内容。
[^2]: 这是第二个脚注的内容。

## Emoji 表情

支持 Emoji 表情：😀 😃 😄 😁 🎉 🎊 ✨ 🚀 💡 📚 ✅ ❌ ⚠️ 

## 总结

这篇文章展示了 Markdown 和 Hexo 支持的各种语法和功能。你可以：

1. ✅ 使用这个模板快速创建新文章
2. ✅ 根据需要选择合适的 Markdown 语法
3. ✅ 添加你自己的内容和创意
4. ✅ 使用 Hexo 插件扩展更多功能

## 下一步

- 阅读 [Hexo 官方文档](https://hexo.io/zh-cn/docs/)
- 浏览 [Markdown 指南](https://www.markdownguide.org/)
- 查看 [HOW_TO_ADD_ARTICLES.md](../HOW_TO_ADD_ARTICLES.md) 了解更多

---

**标签**: #示例 #教程 #Markdown
**分类**: 技术文档
**创建日期**: 2025-07-24
**最后更新**: 2025-07-25

---

## 附录：Front Matter 完整参数

\`\`\`yaml
---
title: 文章标题                 # 必填
date: 2025-07-24 17:30:00      # 必填，发布日期
updated: 2025-07-25 10:00:00   # 可选，更新日期
tags:                          # 可选，标签（可多个）
  - 标签1
  - 标签2
categories:                    # 可选，分类（可多个）
  - 分类1
  - 分类2
description: 文章描述          # 可选，用于 SEO
keywords: 关键词1, 关键词2     # 可选，用于 SEO
top: false                     # 可选，是否置顶
sticky: 0                      # 可选，置顶权重（数字越大越靠前）
cover: /images/cover.jpg       # 可选，封面图
comments: true                 # 可选，是否允许评论
toc: true                      # 可选，是否显示目录
mathjax: false                 # 可选，是否启用数学公式
password: 123456               # 可选，文章密码
---
\`\`\`

愉快写作！✨
