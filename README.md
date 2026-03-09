# SCIRecycle-Journal

## 项目简介
SCIRecycle 是一个基于 MkDocs 构建的纯静态开源网站，定位为一本独立学术期刊。本项目探讨社会学、性别平权、隐性劳动及日常微观权力学等议题。
## 技术栈
* 核心框架：MkDocs
* 前端主题：Material for MkDocs
* 评论组件：Giscus (基于 GitHub Discussions)
* 部署环境：GitHub Pages
* 收稿通道：腾讯问卷 iframe 内嵌

## 目录结构说明
* `docs/`：存放所有 Markdown 格式的文章源码和静态页面。
  * `index.md`：网站首页，包含最新动态和栏目导航。
  * `submit.md`：投稿须知页面，底部已接入自动化收稿表单。
  * `board.md`：编委会名单及介绍。
  * `vol1/`：第一期（创刊号）文章目录。
* `overrides/`：用于存放自定义的主题覆盖文件，目前包含 Giscus 评论模块的注入代码 (`partials/comments.html`)。
* `mkdocs.yml`：站点的全局配置文件，管理导航树、主题样式、自定义 CSS/JS 及各类插件。

## 本地开发与部署
本项目依赖 Python 环境。在克隆项目到本地后，请按以下流程进行开发和发布。

### 1. 环境配置
请确保本地已安装 MkDocs 及 Material 主题：
```bash
pip install mkdocs mkdocs-material
```

### 2. 本地预览
在项目根目录下执行以下命令，启动本地测试服务器。可在 `http://127.0.0.1:8000` 实时预览 Markdown 文件的修改效果：
```bash
mkdocs serve
```

### 3. 编译与上线
所有内容修改并确认无误后，通过以下命令将源码提交至 GitHub，并自动将编译后的静态文件部署到 GitHub Pages：
```bash
git add .
git commit -m "更新说明"
git push origin main
mkdocs gh-deploy
```

## 投稿与协作
读者可通过网站 `submit.md` 页面底部的表单直接进行在线投稿。如需对网站底层的静态框架、前端样式或路由配置进行修改，可通过 Pull Request 提交代码。
