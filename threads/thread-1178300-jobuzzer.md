---
thread_id: 1178300
url: https://www.1point3acres.com/home/thread/1178300
title: 建了个网站，比 LinkedIn 更快看到职位
company: 无（自荐项目 jobuzzer.com）
role: 上游数据产品化案例 / 求职工具（非面经）
posted: 2026-05-28
result: （产品自荐帖，非面经；已收录为 upstream-data-gtm 验证案例）
collected: 2026-10-03
tags: [上游数据, 招聘数据, ATS 抓取, jobuzzer, 产品化案例, GTM 验证]
---

# 建了个网站，比 LinkedIn 更快看到职位

- 原贴：https://www.1point3acres.com/home/thread/1178300
- 作者：pppwww；创业版；2026-05-28 12:15（APP 发布）
- 数据：17707 浏览 / 84 回复 / 316 收藏 / 77 大米；支持 114、表态 53
- 性质：**独立开发者自荐帖，非面经**。作者在多伦多，起因是自己曾为申请加拿大 PR 经历 10 个月焦虑求职（"每天一睁眼坐在电脑前，每隔一小时疯狂刷新 LinkedIn、Indeed 和公司官网"）。网站：https://jobuzzer.com/

## 产品（jobuzzer.com）

- **模式**：主动高频监控公司官网招聘页，岗位比 LinkedIn / Indeed 更早出现（作者称后两者因 verification process 要慢半天到几天）。
- **规模**：发帖时监控约 7000 家公司（目标下月 1 万家）；06-05 更新 watch list 达 9k（含 Apple、Figure）；约 50% 职位在北美，其余按量为英国、澳洲/南美、新加坡、日本、台湾。
- **价格**：搜索完全免费；付费项目是被动 notifications（邮件通知），收入 re-invest 到项目。发过优惠码 `1A3P`。
- **迭代**（作者在帖内持续更新）：06-05 watch list 9k；06-15 notification 美化；06-16 导入 67 家公司；06-29 推出 MCP（beta）；后陆续上线中文 AI 翻译、AI resume match、web push、YOE/身份学历 filter、md/txt 导出。

## 技术路线（作者 05-31、09-21 回复披露）

- **监控频率**：每家公司每天至少检查 12–24 次；Google、Amazon 等明星公司每 20–40 分钟随机检查一次。
- **成本控制三级数据源**（按成本递增）：ATS 工具（Workday、Greenhouse）数据工整→走 API 或自动化爬取；难搞的（如 Apple）→ render 一个 browser（Cloudflare browse run）爬取；都不行→ LLM 直接爬（很贵）。先用工程方式 diff 岗位变化，**有新职位才交给 AI 做分类整理**——"AI 很烧钱…有新工作才让 AI/agent 工作，否则成本会高到破产"。需处理 rate limit、访问时间/频率、IP rotate。
- 用户建议驱动的功能：Work Authorization filter（正则提取 clearance/sponsor/citizen）、YOE filter、md/txt 导出（方便用户 agent 自动申请）、举报按钮移除已下线岗位。

## 用户反馈（评论区）

- **正向**：99922271kk（付费近两周，06-13）："通知十分有用，最近拿到一个面试，节省很多主动找工作的时间…这个价钱我觉得太值得"；西瓜味小可爱确认职位确实来自公司官网、比 LinkedIn 快。
- **bug**：location filter 失效、Google sign-in 在 Chrome 无反应（Safari 正常）、订阅用户收不到邮件通知（后修复）、MCP endpoint 报错、Google 岗位抓取不全、intern 长期被错分类为 full time。
- **质疑**：pinkerOberry（08-21）："本地每天 pull 一下就行，做成服务不一定比 LinkedIn 好，用户多了反而不能及时更新"——直指规模化后的成本/时效矛盾。
- **合作意向**：Dex97 问是否开源/找合作者，作者："有想过开源！但看到自己写的屎山代码…合作者暂时不考虑，有钱赚再算吧"；多伦多用户 gongchangzhANYK 愿线下 coffee chat，已成为付费 customer。

## 商业现状（作者自述）

- 06-07：300 注册；06-15："现在收入还未能够支持开支"；"新付费模式在规划中"。
- 即：**流量验证成立（1.7w 浏览、316 收藏、付费转化存在），但单位经济模型尚未跑通**——与 focus/upstream-data-gtm.md 里"求职者注意力高、付费意愿全网最低"的判断一致。

## GTM 价值提炼

1. **"卖 workflow 不卖数据"的活案例**：用户买的不是职位列表，是"比别人更早知道"+ 被动通知，jobuzzer 的免费搜索 + 付费通知正是这个形态。
2. **成本纪律是关键**：高频监控 + LLM 的成本结构决定生死，作者"工程 diff 先行、AI 只处理增量"的三级策略是可复制的工程经验。
3. **免费获客楔子成立**：搜索免费换流量（1.7w 浏览、316 收藏），但求职者付费天花板低——作者自己也承认收入未覆盖开支，验证了"求职者不做主力变现"的排序。
4. **社区冷启动路径**：1point3acres 创业版自荐 → 真实用户反馈 bug/功能 → 快速迭代，是独立开发者验证上游数据产品的标准打法。
