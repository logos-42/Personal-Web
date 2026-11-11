---
layout: post
title: 站点上线 — Notes 第一则
date: 2026-10-13
description: 用 al-folio v1.x 重建个人主页：六个页面的内容来源、Jekyll/Tailwind 技术栈、push 即部署的流水线，以及去模板化时踩过的坑与后续待补充项。
categories: site
---

本站由 [al-folio](https://github.com/alshedivat/al-folio) v1.x（Jekyll）构建，托管于 GitHub Pages。第一则札记记录站点是怎么搭起来的、内容从哪来、以及哪些决定是刻意的。

## 页面结构

| 页面 | 路径 | 内容来源 |
|---|---|---|
| About | `/` | 身份、三条研究主线、最新动态；中英双语（`data-lang` 切换） |
| Notes | `/notes/` | 研究札记与技术文章，即 `_posts/` |
| Research | `/research/` | 三条主线的「核心问题 — 为什么重要 — 方法 — 成果与未解」 |
| Publications | `/publications/` | `_bibliography/papers.bib`，由 jekyll-scholar 渲染 |
| Projects | `/projects/` | `_projects/` 里的项目卡片，按 `importance` 排序 |
| CV | `/cv/` | `_data/cv.yml` + `al_folio_cv` 插件渲染；中文与英文 PDF 均可下载 |

内容全部真实可核：论文来自 [arXiv:2511.11619](https://arxiv.org/abs/2511.11619) 与 aiXiv 平台的 6 条预印本记录，代码仓库均公开，简历 PDF 由 `resume/main.tex` 与 `resume/en.tex` 用 Tectonic 编译。

## 技术栈

- **运行时**：Jekyll，`theme: al_folio_core`（主题逻辑来自 gem，本地 `_layouts/` 只覆盖需要的部分）。
- **样式**：Tailwind v4.1.18（由 `al_folio.api_version: 1` 的 `style_engine` 指定），旧 Bootstrap 兼容层关闭。
- **内容插件**：jekyll-scholar 处理 BibTeX、jekyll-paginate-v2 分页、jekyll-archives-v2 归档、jekyll-sitemap 站点地图；al_folio_cv 负责 CV 页。
- **数学**：MathJax 3，供研究页里的公式使用。
- **图片**：jekyll-imagemagick 生成响应式 WebP。

## 部署流水线

推送 `master` 分支即触发 `.github/workflows/deploy.yml`：

1. GitHub Actions（Ruby 3.3.5 + bundler 缓存）执行 `JEKYLL_ENV=production bundle exec jekyll build`；
2. 产物 `_site` 由 `JamesIves/github-pages-deploy-action` 推到 `gh-pages` 分支；
3. GitHub Pages 从 `gh-pages` 提供服务。

本地构建需要 Ruby ≥ 3.1（macOS 自带的 2.6 不可用），所以仓库里也备了 `Dockerfile` 与 `docker-compose.yml`，`docker compose up --build` 即可起本地服务。

## 去模板化时踩过的坑

- **trophy 图片全 404**：免费的公共 github-profile-trophy 实例返回 402 / DEPLOYMENT_DISABLED，于是直接关掉该模块，而不是留一排破图。
- **Tailwind 间距被压坏**：jekyll-minifier 二次压缩 CSS 会把 `calc()` 里的 `var(--spacing)` 弄成非法的 `var( - - spacing)`，导致 `.fixed-top` 等工具类失效；因此 `compress_css: false`，JS 交给 jekyll-terser。
- **favicon 偏左**：主题默认把 emoji 塞进内联 SVG，`<text>` 没有水平居中；改为自备 SVG，用 `text-anchor="middle"` 居中。
- **模板残留**：删除主题自带的示例论文、示例项目与外部示例文章，全部换成真实条目。

## 刻意保留的取舍

- **双语并存**：中文与英文各写一版，而不是机翻；副标题用打字机效果在切换语言时重播。
- **不追外部服务**：Google Fonts、trophy、masonry 等外部依赖能关就关，减少第三方故障带来的破图与请求。
- **显式 add**：提交时逐文件列出，不用 `git add -A`，避免把本地素材、他人模板 PDF 或大图误推到公开仓库。

## 后续待补充

- 研究方向的配图（真实论文插图 / 架构图，放进 `assets/img/`）
- 更多研究札记：目前 Notes 只有四则，会随项目进展持续更新
- 项目与论文的交叉链接更细的粒度

站点源码：[logos-42/Personal-Web](https://github.com/logos-42/Personal-Web) · 在线：[logos-42.github.io](https://logos-42.github.io)
