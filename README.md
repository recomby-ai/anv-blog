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

## 🎨 Schema.org 设置（灵活且强大）

### 📌 固定保留的Schema（自动生成）

每篇文章**默认包含**以下schema，无需任何配置：

1. **Organization** - 公司信息（全站通用）
2. **BlogPosting** - 文章基础信息（标题、作者、日期等）

### ✨ 三种使用方式

#### 方式1：极简模式（什么都不加）

```yaml
---
layout: post
title: "我的新文章"
description: "文章描述"
---

文章正文...
```

**自动包含**: Organization + BlogPosting

---

#### 方式2：添加FAQ（简单快捷）

```yaml
---
layout: post
title: "定制袜子常见问题"
faq:
  - q: "最低起订量是多少？"
    a: "500双起订"
  - q: "交货期多久？"
    a: "15-30天"
---

文章正文...
```

**包含**: Organization + BlogPosting + **FAQ**

---

#### 方式3：添加自定义Schema（最强大）

在 front matter 中使用 `custom_schemas` 添加额外的 schema：

```yaml
---
layout: post
title: "ANV Pro运动袜上市"
custom_schemas:
  - |
    {
      "@context": "https://schema.org",
      "@type": "Product",
      "name": "ANV Pro运动袜",
      "description": "高弹性专业运动袜",
      "brand": {
        "@type": "Brand",
        "name": "ANV Socks"
      },
      "offers": {
        "@type": "Offer",
        "price": "8.99",
        "priceCurrency": "USD",
        "availability": "https://schema.org/InStock"
      }
    }
---

文章正文...
```

**包含**: Organization + BlogPosting + **Product**

---

### 🔥 Schema可以叠加！

你可以同时使用FAQ和自定义Schema：

```yaml
---
layout: post
title: "新款运动袜发布"
faq:
  - q: "适合什么运动？"
    a: "跑步、篮球、足球都适合"
custom_schemas:
  - |
    {
      "@context": "https://schema.org",
      "@type": "Product",
      "name": "ANV运动袜",
      "offers": {
        "@type": "Offer",
        "price": "8.99",
        "priceCurrency": "USD"
      }
    }
  - |
    {
      "@context": "https://schema.org",
      "@type": "VideoObject",
      "name": "产品展示视频",
      "contentUrl": "https://youtube.com/xxxxx"
    }
---
```

**包含**: Organization + BlogPosting + FAQ + Product + Video

---

### 🔧 高级选项

#### 禁用默认BlogPosting（很少需要）

```yaml
---
layout: post
title: "我的文章"
disable_auto_schema: true
custom_schemas:
  - |
    { 你的完全自定义schema }
---
```

**包含**: Organization + 你的自定义schema（没有BlogPosting）

---

### 📚 常用Schema类型

| Schema类型 | 用途 | 效果 |
|-----------|------|------|
| **Product** | 产品介绍 | 显示价格、库存 |
| **HowTo** | 教程步骤 | 显示步骤列表 |
| **Review** | 评价评分 | 显示星级⭐ |
| **Video** | 视频内容 | 视频搜索优化 |
| **Event** | 活动通知 | 显示时间地点 |
| **FAQ** | 常见问题 | 显示问答框 |

详细的Schema示例，请查看项目Wiki或联系技术支持。

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
