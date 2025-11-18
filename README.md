# ANV Socks Blog

专业袜子制造商博客 - 基于 Jekyll 构建

## 📝 如何发布文章

### 1. 创建新文章

在 `_posts/` 目录下创建文件，命名格式：`YYYY-MM-DD-title.md`

例如：`2025-11-18-my-new-post.md`

### 2. 文章结构

每篇文章由两部分组成：

#### Front Matter（文章元数据）

```yaml
---
layout: post
title: "文章标题"
description: "文章描述（用于SEO）"
date: 2025-11-18
author: "ANV Team"
tags: [socks, manufacturing, custom]
category: "Blog"
---
```

#### 正文内容

使用 Markdown 格式编写文章内容。

---

## 🎨 Schema.org 设置（三种方式）

### 方式1：使用默认自动生成（推荐给简单文章）

什么都不用做，模板会自动生成基础的 BlogPosting schema。

```yaml
---
layout: post
title: "我的文章"
description: "文章描述"
---

文章正文...
```

### 方式2：使用 FAQ 辅助（适合有常见问题的文章）

在 front matter 中添加 `faq` 字段：

```yaml
---
layout: post
title: "我的文章"
faq:
  - q: "问题1"
    a: "答案1"
  - q: "问题2"
    a: "答案2"
---

文章正文...
```

### 方式3：完全自定义 Schema（最灵活）

在 front matter 中使用 `custom_schemas` 定义完整的 schema：

```yaml
---
layout: post
title: "我的文章"
custom_schemas:
  - |
    {
      "@context": "https://schema.org",
      "@type": "BlogPosting",
      "headline": "自定义标题",
      "description": "自定义描述",
      "author": {
        "@type": "Person",
        "name": "作者名"
      }
    }
  - |
    {
      "@context": "https://schema.org",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "自定义问题",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "自定义答案"
          }
        }
      ]
    }
---

文章正文...
```

**说明**：
- 使用 `custom_schemas` 后，会**完全替代**自动生成的 schema
- 可以定义**多个** schema（数组形式）
- 在 YAML 中使用 `|` 符号来保持 JSON 格式
- 你需要自己确保 JSON 格式正确

### 禁用自动 Schema

如果你想完全控制 schema，可以禁用自动生成：

```yaml
---
layout: post
title: "我的文章"
disable_auto_schema: true
---
```

---

## 📊 表格和其他内容

**直接在文章正文中使用 Markdown 语法编写表格：**

```markdown
| 规格 | 说明 |
|------|------|
| 材质 | 棉质 |
| 尺码 | 均码 |
```

不需要在 front matter 中定义！

---

## 🖼️ 图片使用

将图片放在 `assets/images/` 目录下，然后在文章中引用：

```markdown
![图片描述]({{ site.url }}{{ site.baseurl }}/assets/images/your-image.jpg)
```

或者使用相对路径：

```markdown
![图片描述](/assets/images/your-image.jpg)
```

---

## 📁 项目结构

```
anv-blog/
├── _config.yml          # 站点配置
├── _layouts/            # 页面模板
│   ├── default.html     # 基础模板
│   └── post.html        # 文章模板
├── _posts/              # 文章目录
│   └── YYYY-MM-DD-title.md
├── assets/              # 静态资源
│   ├── images/          # 图片
│   └── README.md
├── index.html           # 首页
└── README.md            # 本文件
```

---

## 🚀 部署

本项目使用 GitHub Actions 自动部署到 GitHub Pages。

**当前部署地址**：https://recomby-ai.github.io/anv-blog/

每次推送到主分支时，会自动触发构建和部署。

---

## 🔧 本地开发

### 安装依赖

```bash
bundle install
```

### 本地预览

```bash
bundle exec jekyll serve
```

访问：http://localhost:4000/anv-blog/

---

## 📞 联系信息

**公司**：ZHUJI DATANG KAIRONG KNITTING CO., LTD.
**邮箱**：vickeychan@xmghp.com
**网站**：[www.anvsocks.com](https://www.anvsocks.com)
**博客**：[recomby-ai.github.io/anv-blog](https://recomby-ai.github.io/anv-blog/)

---

## 📄 License

© 2002-2025 ANV Socks. All rights reserved.
