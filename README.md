# 健康无抗抑郁药 - Health Without Antidepressants 中文翻译

> ⚠️ **免责声明**：所有内容仅供信息参考，不构成医疗建议。任何停药/用药决策请务必咨询专业医生。

## 关于本站

本站点收录了 [Health Without Antidepressants](https://healthwithoutantidepressants.com/browse-site-contents) 网站全部 38 篇文章的简体中文翻译。该网站面向抗抑郁药/度洛西汀(Cymbalta)使用者，关注减量与替代疗法。

- **翻译日期**：2026-08-05（2026-08-17 校对修订）
- **来源**：https://healthwithoutantidepressants.com/browse-site-contents
- **部署方式**：GitHub Pages

## 目录结构

```
HWA/
├── _config.yml                    # Jekyll 配置
├── index.md                       # 首页
├── README.md                      # 本文件
├── 入门与决策/                    # 4 篇 - 入门指南与决策参考
├── 减量方法/                      # 5 篇 - 安全减量的实操指南
├── 停药症状与应对/                # 5 篇 - 了解和应对停药症状
├── 副作用与危害/                  # 7 篇 - 抗抑郁药可能带来的风险
├── 社区经验/                      # 5 篇 - CHW 社区真实经历分享
├── 健康生活/                      # 6 篇 - 替代疗法、营养和生活方式
└── 支持与资源/                    # 6 篇 - 获取帮助和支持的渠道
```

## 快速导航

| 分类           | 文章数 | 说明                                                |
| -------------- | ------ | --------------------------------------------------- |
| 入门与决策     | 4      | 考虑服药/停药的决策参考、FAQ、研究资料              |
| 减量方法       | 5      | 数微丸法、称重法、高剂量减量、计算器                |
| 停药症状与应对 | 5      | 波动窗口期、静坐不能、恢复用药、血清素综合征        |
| 副作用与危害   | 7      | Cymbalta 副作用、双相、肠道、甲状腺、妊娠、体重增加 |
| 社区经验       | 5      | CHW 社区的错误减量、突然停药、成功经验等            |
| 健康生活       | 6      | 营养、饮食、纤维肌痛、失眠、快乐、管理抑郁          |
| 支持与资源     | 6      | 家人朋友、医生互助、医保、补剂、危机安全、参考资源  |

## 部署到 GitHub Pages

### 方法一：直接推送到 main 分支

1. 在 GitHub 创建新仓库（如 `hwa-zh`）
2. 将此目录内容推送到仓库
3. 在仓库 Settings → Pages → Source 选择 `main` 分支
4. 几分钟后访问 `https://<username>.github.io/hwa-zh/`

### 方法二：使用 GitHub Actions（推荐）

在仓库根目录创建 `.github/workflows/jekyll.yml`：

```yaml
name: Deploy Jekyll site to GitHub Pages

on:
  push:
    branches: ["main"]

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Pages
        uses: actions/configure-pages@v5
      - name: Build with Jekyll
        uses: actions/jekyll-build-pages@v1
        with:
          source: ./
          destination: ./_site
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

## 本地预览

安装 Jekyll 后运行：

```bash
cd HWA
bundle install
bundle exec jekyll serve
```

访问 http://localhost:4000 预览站点。

## 内容说明

- 每篇文档均保留原网页的标题层级（`#`/`##`/`###`）、列表、引用块、表格与超链接
- 医学/药学专有名词在首次出现处采用"中文译名 + 英文原文（括号）"形式
- 原文中的 URL 链接保留英文原样
- 所有文件名沿用原文 URL slug 以便溯源
