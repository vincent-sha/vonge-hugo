# vonge-hugo（新主题）

这是一个全新的 Hugo 主题，复刻自 Zola 主题「Vonge」的视觉与交互风格，适用于作品集与博客型站点。主题内置首页内容块体系、博客/项目/标签/评价页模板，并提供完整的配置项与示例资源。

## 主题特性
- 首页内容块（Hero / Projects / Testimonials / Blog / Newsletter / Contact）
- 博客列表与文章页
- 项目列表与详情页
- 标签聚合页
- 客户评价轮播
- 响应式布局与图片放大

## 安装方式
提供 Hugo Modules 与 Git submodule 两种方式：

### 方式一：Hugo Modules（推荐）
前置要求：安装 Go（建议 1.20+）。

1) 在你的 Hugo 站点配置中添加模块导入：
  [module]
    [[module.imports]]
     path = "github.com/vincent-sha/vonge-hugo"

2) 在你的配置文件中启用主题：
  theme = "vonge-hugo"

3) 初始化并拉取模块：
  hugo mod init github.com/yourname/your-site
  hugo mod get -u github.com/vincent-sha/vonge-hugo

### 方式二：Git submodule
1) 在你的 Hugo 项目中添加子模块：
  git submodule add https://github.com/vincent-sha/vonge-hugo themes/vonge-hugo

2) 拉取子模块内容：
  git submodule update --init --recursive

3) 在你的配置文件中启用主题：
  theme = "vonge-hugo"

4) 复制示例内容与配置（可选但推荐）：
  - 将本仓库的 exampleSite/content/ 复制到你的项目 content/
  - 如需示例静态资源，请参考本仓库的 static/ 目录
  - 将 exampleSite/hugo.toml 中站点基础配置合并到你的配置
  - 多语言与语言参数请参考 exampleSite/config/_default/languages.toml 的结构

### 使用 exampleSite 预览主题
在本仓库根目录执行：
- hugo server -D --source exampleSite --themesDir .. --theme vonge-hugo

## 本地预览
确保已安装 Hugo（extended 版本优先），在项目根目录执行：
- hugo server -D --source exampleSite --themesDir .. --theme vonge-hugo --bind 0.0.0.0 --port 1313

浏览地址：
- http://localhost:1313

## 配置说明（exampleSite/hugo.toml + config/_default/languages.toml）
配置分为两部分：
- 站点基础配置：exampleSite/hugo.toml
- 多语言与语言参数：exampleSite/config/_default/languages.toml

- 基础站点信息
  - baseURL：站点域名
  - languageCode：语言
  - title：站点标题

- 分页与标签
  - [pagination].pagerSize：列表页分页大小
  - [taxonomies].tag：标签分类名（当前为 tags）

- 全局参数（[params]，位于 hugo.toml）
  - logo_image / social_media_share_image：站点 Logo 与社交分享图
  - disqus_identifier / google_analytics / twitter_handle：评论与统计参数
  - author_image：作者头像（全局默认）

- 社交链接（[params.social_icons]，位于 hugo.toml）
  - 建议放置全局共用社交链接

- 语言参数（[languages.<lang>.params]，位于 languages.toml）
  - author / description / keywords：SEO 与作者信息
  - date_format / language_direction：日期与语言方向
  - navigation：主导航（支持二级子菜单）
  - footer.menu：页脚导航
  - content_blocks：首页内容块（多语言文案与链接在此维护）

- 首页内容块（[[languages.<lang>.params.content_blocks]]）
  - hero / projects-section / testimonials-section / blog-section / newsletter / contact-form
  - 每个内容块的字段在配置中逐项可改

- 多语言（hugo.toml + languages.toml）
  - 默认语言与子目录：defaultContentLanguage / defaultContentLanguageInSubdir
  - 语言内容目录：content/en 与 content/zh-cn
  - 语言定义与参数位于 config/_default/languages.toml

## 目录结构（简要）
- exampleSite/content/：示例站点内容（文章、项目、页面、评价）
- exampleSite/content/en：英文示例内容
- exampleSite/content/zh-cn：中文示例内容
- exampleSite/hugo.toml：示例站点基础配置
- exampleSite/config/_default/languages.toml：多语言与语言参数配置
- layouts/：主题模板与组件
- static/：主题静态资源（CSS、图片、上传文件、JS）
- i18n/：多语言文案（en.toml / zh-cn.toml）

## 依赖说明
主题通过 CDN 引入以下前端库：
- Ionicons
- Lightense
- reframe.js
- tiny-slider
- ityped
- smoothscroll-polyfill