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
有两种方式安装主题：

### 方式一：作为主题使用
1) 将本仓库放入你的 Hugo 项目的 themes/ 目录：
   themes/vonge-hugo

2) 在你的配置文件中启用主题：
   theme = "vonge-hugo"

3) 复制示例内容与配置（可选但推荐）：
  - 将本仓库的 exampleSite/content/ 复制到你的项目 content/
  - 如需示例静态资源，请参考本仓库的 static/ 目录
  - 将 exampleSite/hugo.toml 中 [params] 与 [params.content_blocks] 合并到你的配置

### 方式二：使用 exampleSite 预览主题
在本仓库根目录执行：
- hugo server -D --source exampleSite --themesDir .. --theme vonge-hugo

## 本地预览
确保已安装 Hugo（extended 版本优先），在项目根目录执行：
- hugo server -D --source exampleSite --themesDir .. --theme vonge-hugo --bind 0.0.0.0 --port 1313

浏览地址：
- http://localhost:1313

## 配置说明（exampleSite/hugo.toml）
核心参数位于 [params] 与 [params.content_blocks]：

- 基础站点信息
  - baseURL：站点域名
  - languageCode：语言
  - title：站点标题

- 分页与标签
  - [pagination].pagerSize：列表页分页大小
  - [taxonomies].tag：标签分类名（当前为 tags）

- 全局参数（[params]）
  - author / author_image：作者与头像
  - description / keywords：SEO 描述与关键词
  - logo_image / social_media_share_image：站点 Logo 与社交分享图
  - disqus_identifier / google_analytics / twitter_handle：评论与统计参数
  - date_format / language_direction：日期与语言方向

- 导航与社交（[params.navigation] / [params.social_icons]）
  - 支持 $BASE_URL 占位符
  - Pages 菜单包含二级子菜单

- 页脚（[params.footer]）
  - footer.menu：页脚导航

- 首页内容块（[[params.content_blocks]]）
  - hero / projects-section / testimonials-section / blog-section / newsletter / contact-form
  - 每个内容块的字段在配置中逐项可改

## 目录结构（简要）
- exampleSite/content/：示例站点内容（文章、项目、页面、评价）
- exampleSite/hugo.toml：示例站点配置与参数
- layouts/：主题模板与组件
- static/：主题静态资源（CSS、图片、上传文件、JS）

## 依赖说明
主题通过 CDN 引入以下前端库：
- Ionicons
- Lightense
- reframe.js
- tiny-slider
- ityped
- smoothscroll-polyfill