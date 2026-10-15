# 平台二级域名网站示例

> 整理日期：2026-10-15。例子来自公开搜索结果，证明免费二级域名可以承载真实流量。

## Substack（`xxx.substack.com`）

- `thehyphen.substack.com` —— Emma Gannon 的 The Hyphen，文化/生活方式类
- `jillschildhouse.substack.com` —— Jill Schildhouse，媒体/自由撰稿人类
- Lenny's Newsletter —— 产品管理类，50 万+订阅，Substack 上最成功的 newsletter 之一
- Letters from an American —— Substack 全站阅读量最高的 newsletter 之一
- Sinocism（Bill Bishop）、Popular Information（Judd Legum）—— 付费订阅标杆，每月 $6–15

## Blogspot（`xxx.blogspot.com`）

- `joemygod.blogspot.com` —— JoeMyGod，曾进入 Technorati 全球博客 Top 100（第 63 位），至今仍在运营
- `directorblue.blogspot.com` —— Director Blue，Technorati 第 79 位

## WordPress.com（`xxx.wordpress.com`）

- **特点是长尾，没有"著名"站点**：典型是个人博客和小企业博客。案例：Portland 的 Sweet Crumb bakery 用免费 WordPress.com 博客做内容，3 个月内博客带来 40% 网站流量（据 wegic.ai 2026 年案例）。
- **SEO 圈实测可用**：wickedfire 论坛的案例研究显示，关键词型 `xxx.wordpress.com` 子域名在低竞争词上能进 Google 首页——免费二级域名确实能吃到搜索流量。
- 限制：免费版不能装自定义插件/主题，有 WordPress.com 品牌露出；想解绑需付费升级。

## GitHub Pages（`xxx.github.io`）

以下来自 GitHub 官方 Pages examples 合集（github.com/collections/github-pages-examples），全是真实在跑的：

- `square.github.io` —— Square 开源项目门户
- `yelp.github.io` —— Yelp 开源项目展示
- `artsy.github.io` —— Artsy 工程博客
- `netflix.github.com` —— Netflix 开源门户
- `twbs` / `jekyll` 等知名开源项目的文档站也都用 Pages 托管

定位：纯静态站，适合开发者博客、项目文档、作品集；**不适合内容农场**（无服务端、无 CMS、无 SEO 插件生态）。

## Vercel（`xxx.vercel.app`）

- `emojidb.vercel.app` —— emoji 数据库小应用（Vercel 社区用户分享）
- `webskills.vercel.app` —— Web 技能学习站（社区分享）
- **本质是部署 URL**：上面多为个人 demo 和小应用，没有著名的内容型站点。另有一面：`xxx.vercel.app` 常被钓鱼/恶意软件滥用（cyberpress 2025 年报道多起案例），在大众和邮件网关那里的信任度偏低。

## Netlify / Cloudflare Pages（`xxx.netlify.app` / `xxx.pages.dev`）

- 同上：多为部署演示和个人项目，**没有著名的内容型站点**。
- dev.to 2026 年的对比文章说得很直白：这类域名 "signal 'this is a build artifact'"（一看就是构建产物，不是正式产品），且换托管平台就作废。

## 一句话总结

| 平台 | 有无著名内容站 | 适合干嘛 |
|---|---|---|
| Substack 子域名 | 有（几十万订阅级） | newsletter / 订阅制内容 |
| Blogspot | 有（全球 Top 100 博客） | 传统博客，Google 亲儿子 |
| WordPress.com | 无（长尾为主） | 个人博客、小企业博客 |
| GitHub Pages | 有（大厂开源门户） | 静态站、文档、开发者博客 |
| Vercel/Netlify/Pages | 无（多为 demo） | 部署预览、小应用 |

免费二级域名**可以**做出真实流量，但注意两点：一是子域名不继承主域全部权重（Google 把它当独立站点）；二是做大之后多数会花 $10 买独立域名——二级域名没有资产价值、不能卖、换平台就作废。
