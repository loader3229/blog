# AGENTS.md

本仓库是 loader3229 的个人博客（Jekyll + GitHub Pages，主题 jekyll-theme-cayman，全站中文）。

## 发布配置（重要）

- GitHub Pages 发布源：`gh-pages` 分支。只有推送到 `gh-pages` 的改动才会线上生效，推送到其他分支不会触发站点更新。
- 站点地址：https://loader3229.github.io/blog/（部署在 /blog 子路径；GitHub Pages 会自动注入 baseurl，站内链接一律使用 `relative_url` 过滤器）。

## 分支说明

- `gh-pages`：发布源分支，线上内容以它为准。
- `trae`：TRAE agent 的工作分支，需与 `gh-pages` 保持同步。
- `main`：历史分支，不用于发布。

## 目录结构

- `_posts/`：文章目录，文件名格式 `YYYY-MM-DD-标题.md`（文件名中的日期即发布日期）。
- `_layouts/`：布局目录（必须是复数 `_layouts`，不能写成 `_layout`）。`article.html` 为文章布局，继承主题 default 布局。
- `index.html`：首页，按日期倒序展示文章列表。
- `archive.html`：按年份归档页。
- `_config.yml`：站点配置（标题、描述、主题、语言）。

## 发布文章流程

1. 在 `_posts/` 新建 `YYYY-MM-DD-标题.md`，front matter 包含 `layout: article`、`title`、`date: YYYY-MM-DD`，正文为 Markdown。
2. 将改动推送到 `gh-pages` 分支，并同步 `trae` 分支。
3. 等待 GitHub Pages 自动构建（约 1~2 分钟），用 `curl` 验证线上页面（中文标题 URL 需编码）。
