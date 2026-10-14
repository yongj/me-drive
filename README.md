# Interview Prep

Interview experiences & prep materials collected from [一亩三分地 (1point3acres)](https://www.1point3acres.com/).

## Focus

- **SWE** — especially distributed storage / cloud storage background
- **AI Engineer** — agent direction
- **AI coding in interviews** — how companies assess candidates' use of AI coding tools
- **AI value creation** — AI 应用场景探索：用 AI + 上游数据创造价值和商业机会（不收面试内容）
- **AI personal use** — AI 能帮你干什么：个人实战清单（求职/工作/学习），区别于 AI value creation 的商业视角
- **AI-assisted dev** — coding agent 实战（Claude Code 驱动真实软件）与"开源平替主流软件 + 卖服务"的小团队商业模式（[ai-assisted-dev.md](focus/ai-assisted-dev.md)）
- **Upstream data GTM** — 上游数据的商业化：每类上游数据源卖给谁、卖什么形态、怎么触达客户

## Companies

按公司查看收录的帖子（[companies/](companies/)，一家公司一个文件，帖子按时间倒序列出；有新帖时把链接追加到对应公司文件即可）：

- [Anthropic](companies/anthropic.md) — 1192987 senior SWE onsite（Pass）、1192970 店面（链接收录）
- [OpenAI](companies/openai.md) — 1192976 店面 coding（链接收录为主）
- [Snowflake](companies/snowflake.md) — 1190471 AI Engineer onsite
- [Harvey AI](companies/harvey-ai.md) — 1190457 AI Engineer onsite
- [Meta](companies/meta.md) / [Google](companies/google.md) / [Amazon](companies/amazon.md) — 1190956 面试 AI 政策
- [Apple](companies/apple.md) — 1190004 薪酬统计
- [Microsoft](companies/microsoft.md) / [Mercor](companies/mercor.md) / [Databricks](companies/databricks.md) — 1183413 求职总结提及

## Collected threads

| Collected | Thread | Company | Role | Notes |
|-----------|--------|---------|------|-------|
| 2026-09-25 | [雪花 AI Engineer 昂赛特](https://www.1point3acres.com/home/thread/1190471) | Snowflake | AI Engineer（偏 agent） | Onsite 三轮：AI Augmented coding（rate limiter）、Expertise（agent skill pipeline + agent memory）、Behavior；Pass 未接 |
| 2026-09-25 | [被裁两次找工10个月总结](https://www.1point3acres.com/home/thread/1183413) | 多家（OpenAI/Mercor/Databricks/Microsoft AI/TT） | Senior SDE（AI agent/chatbot 后端） | 35 家去重、11 个 onsite、3 个 offer；签约 Series D/E AI startup；干货：项目深挖、面经+Claude 对答案、reachout/referral 渠道 |
| 2026-09-24 | [请推荐ai agent design的学习资料](https://www.1point3acres.com/home/thread/1188022) | 无（求资料帖） | AI Engineer（agent design） | 楼主 fail 几轮 agent design 面经求资料；干货：按"层"选资料（应用编排层 Anthropic/OpenAI 必读、工程层 Chip Huyen、中文 李博杰开源书）、IBM 证书太基础；自己动手做小 agent、讲清楚 tradeoff |
| 2026-10-01 | [信息也是食物：为什么有了 AI，海外求职依然存在巨大的信息差](https://www.1point3acres.com/home/thread/1186353) | 无（方法论长文） | AI 应用场景 / 求职方法论 | 上游信息方法论：许可名单万能钥匙、五步流程、AI 正确分工（烧水不取水）；欧洲金融 MiFID 牌照库、中国烟草许可证库双案例；ai-value-creation focus 种子帖 |
| 2026-10-01 | [2026 美国 AI Engineer & MLE 招聘数据 —— 自己抓的，2,400+ 岗位拆解](https://www.1point3acres.com/home/thread/1178971) | 无（数据系列：另有 SE 篇 thread-1178563、DE 篇 thread-1178666） | 招聘市场数据方法论 | ATS 公开职位抓取（Greenhouse/Lever/Workday/Workable）；SE 39,230 / DE 4,257 / AIE 2,434 / MLE 2,430 岗；方法论黑箱在公司名单未披露；ai-value-creation focus 新增 ATS 上游抓取案例 |
| 2026-10-02 | [AI 正在重写 SDE 面试：从 OA 到 onsite 的 5 个变化](https://www.1point3acres.com/home/thread/1190956) | 多家（Meta/Google/OpenAI/Amazon） | SDE 面试政策整理（非面经） | 2025-2026 公开信息汇编：OA 防作弊升级、Meta/Google/OpenAI 面试允许 AI 编程助手、面试题转向 AI 原生场景；OpenAI「允许」行已并入 ai-coding-in-interviews 政策表（待一手验证） |
| 2026-10-03 | [🍎苹果2026年度Review数字交流统计贴](https://www.1point3acres.com/home/thread/1190004) | Apple | 薪酬统计（非面经，归 `misc/`） | 仅 3 条完整数据：AIML ICT4 refresh 450K/4y、AIML ICT5 refresh 870K/4y、HWT ICT4 refresh 120K；评论区信号：AIML 内部分化极大、HW/ASE 约为 1/4、org 归属有争议；样本极小勿当基准 |
| 2026-10-03 | [建了个网站，比 LinkedIn 更快看到职位](https://www.1point3acres.com/home/thread/1178300) | 无（自荐 jobuzzer.com） | 上游数据产品化案例（非面经） | 高频监控 7k→9k 家公司官网招聘页、比 LinkedIn 更早；免费搜索 + 付费通知；技术路线：ATS API → 渲染浏览器 → LLM 三级成本控制；1.7w 浏览/316 收藏但收入未覆盖开支；已并入 upstream-data-gtm 作验证案例 |
| 2026-10-07 | [[求比较] $ Opportunities 小时工，求比较！](https://www.1point3acres.com/home/thread/1192101) | Surge AI / Mercor / Data Annotation 等（数据标注平台） | AI 数据标注小时工市场（非面经） | 打工者视角对比 6 家标注平台；唯一薪资数据点 Surge SWE eval $100+/hr；讨论集中在报税/竞业合规而非平台优劣；"拿 AI 干活"套娃；已并入 ai-value-creation 作人力层案例 |
| 2026-10-14 | [人类学senior全套面经](https://www.1point3acres.com/home/thread/1192987) | Anthropic | Senior SWE（码农类 General） | 内推→OA(bank system)→店面(图像处理+pillow+multiprocessing)→onsite 5 轮：prompt playground SD / LRU+WAL coding / project deep dive / culture / HM；Pass，Positive/Hard；4 年+YOE 在职跳槽；pool hire 转 match；reference check 前置加速 |
| 2026-10-14 | [openai店面coding](https://www.1point3acres.com/home/thread/1192976) | OpenAI | SWE（码农类 General） | 店面 coding：kvstore（k,v 按 byte length）+ 按 size 分 chunk 存盘（先拼装再解决）；正文 188 大米 paywall，仅收录链接+回帖拼凑 |
| 2026-10-14 | [Anthropic 店面 过经](https://www.1point3acres.com/home/thread/1192970) | Anthropic | 码农类（未注明级别） | 店面：chat system（pub/sub 细节 + partition key）；Pass；正文 188 大米 paywall，仅收录链接 |

## Layout

- `threads/` — one markdown file per thread, with original post link, interview rounds, useful replies, and prep notes.
- `misc/` — occasional non-interview threads (e.g. compensation stats), one file per thread.
- `focus/` — per-focus summaries distilled from collected threads.
- `companies/` — one file per company, listing related threads in reverse chronological order.
- `drive/` — positions actively being prepared: one file per role with posting link, key facts, and interview prep notes.
- `data/` — upstream data: company library (L1 500 tech companies with ATS status; no job postings).
