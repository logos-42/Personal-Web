# leo · logos-42 — 个人学术主页

https://logos-42.github.io

独立研究者 Leonard（刘元杰）的个人学术档案：数学物理与形式化验证、脑启发 AI、去中心化智能体协议。

基于 [al-folio](https://github.com/alshedivat/al-folio)（v1.x, Jekyll）构建，深度去模板化定制（Editorial 配色、真实论文与项目、中文/英文双语内容）。

## 页面结构

| 页面 | 路径 | 内容 |
|------|------|------|
| About | `/` | 身份、三线研究索引、最新动态 |
| Notes | `/notes/` | 研究札记与技术文章（`_posts/`） |
| Research | `/research/` | 三个方向：核心问题 / 方法 / 成果与未解 |
| Publications | `/publications/` | 论文列表（`_bibliography/papers.bib`，jekyll-scholar 渲染） |
| Projects | `/projects/` | 研究项目卡片（`_projects/`） |
| CV | `/cv/` | 履历（`_data/cv.yml`）+ PDF 下载（`assets/pdf/resume.pdf`） |

## 本地构建

需要 Ruby ≥ 3.1（macOS 自带 2.6 不可用，可用 Homebrew 或 Docker）。

```bash
# 方式一：Docker（推荐，无需装 Ruby）
docker compose up --build
# 访问 http://localhost:4000

# 方式二：原生 Ruby（≥ 3.1）
bundle install
bundle exec jekyll serve --livereload
# 访问 http://localhost:4000
```

## 部署

推送 master 分支即触发 GitHub Actions（`.github/workflows/deploy.yml`）：
`jekyll build` → 产物推送到 `gh-pages` 分支 → GitHub Pages 从 `gh-pages` 提供服务。

```bash
git add <本次文件>   # 显式列出，不要用 -A
git commit -m "..."
git push origin master
```

## 内容更新

- **新论文**：在 `_bibliography/papers.bib` 加一条（`html` 详情页 + `pdf` 直链），标记 `selected = {true}` 会出现在首页
- **新项目**：在 `_projects/` 加一个 `.md`（`importance` 越小越靠前）
- **新 Notes**：在 `_posts/` 加 `YYYY-MM-DD-title.md`
- **新动态**：在 `_news/` 加 announcement
- **主题色**：编辑 `_sass/_variables.scss`（`$purple-color` = 浅色强调，`$cyan-color` = 深色强调）

## 待补充

- [ ] 个人照片（about 页 `profile.image`）
- [ ] 研究方向的配图（真实论文插图/架构图，放入 `assets/img/`）
- [ ] 更多 Notes 研究札记