---
thread_id: 1178971
url: https://www.1point3acres.com/home/thread/1178971
title: 2026 美国 AI Engineer & MLE 招聘数据 —— 自己抓的，2,400+ 岗位拆解
company: （无，数据方法论系列，非公司面经）
role: 数据方法论 / 招聘市场分析
posted: 2026-06-03（估计，待核实）
result: （数据分析系列，非面经）
collected: 2026-10-01
tags: [上游数据, ATS, 招聘数据, 方法论, AI Engineer, MLE, SE, DE]
---

# 2026 美国 AI Engineer & MLE 招聘数据 —— 自己抓的，2,400+ 岗位拆解

- 原贴：https://www.1point3acres.com/home/thread/1178971
- 注：这是同作者"凤眼流盼的草稿本"的招聘数据系列第三篇。前两篇：SE 篇 https://www.1point3acres.com/bbs/thread-1178563-1-1.html（39,230 岗位 / 4,742 公司），DE 篇 https://www.1point3acres.com/bbs/thread-1178666-1-1.html（4,257 岗位 / 1,348 公司）。三篇的方法论相同：自己写脚本抓 ATS 公开职位。方法论提炼已归入 focus/ai-value-creation.md（ATS 上游抓取案例）。

## 上游数据源（楼主自述）

- **是什么**：Greenhouse、Lever、Workday、Workable 等 ATS 系统上的公开职位发布，绕开 LinkedIn / Indeed / Glassdoor 聚合站，直接抓公司招聘页。
- **规模口径**（前后不一）：正文称"美国 4,000+ 家公司招聘页，连续跑了几轮验证"；DE 篇评论称"差不多 2w 家公司，100w 个职位的样子"；AIE 篇首条评论称"超过 100 万个活跃职位发布，2.5w 个公司的样子"。4000+ 家的口径更可信（可稳定抓取的 Greenhouse/Lever board 量级），2.5 万家疑似把 ATS 全量盘子都算上了。
- **方法**：title 关键词匹配过滤岗位 → JD 文本提技能关键词出现率 → level 主要按 JD 描述中的年限要求推断（JD 没写就没办法）→ 按公司汇总。
- **未披露**：完整公司名单、careers 页面 URL 清单、抓取频率、去重逻辑、薪资覆盖率。有人直接问"爬的哪里的 source"，楼主未回复。

## 三篇数据摘要

**SE 篇**（39,230 岗 / 4,742 公司，median $135K）：Junior $99K / Mid $107K / Senior $140K / Lead $121K（反常低于 Senior）/ Staff $177K / Director $200K+。AI/LLM 出现在 50% 的 JD 里；remote 真实占比仅 14%（unspecified 80% 默认 onsite）；**80% 岗位不写 seniority**；Top 10 公司贡献一大半 openings。

**DE 篇**（4,257 岗 / 1,348 公司）：Junior $80K（仅 49 岗）/ Mid $102K / Senior $139K / Lead $150K / Staff $169K。Python 69% / SQL 66% 五五开；Data Pipeline 52%、AWS 50%、AI/LLM 43%、Spark 39%、Airflow 27%、Databricks 25%；dbt / Snowflake / Kafka 未进前十。Associate Degree 占 54%（tech 里学历最宽容的方向之一）。Top 雇主：PwC 80、Amazon 65、Amgen 65、Barclays 48、Capital One 46——咨询和金融占大头。

**AIE 篇**（2,434 岗 / 1,121 公司，median $150K）：Junior $102K（27 岗）/ Mid $122K（33）/ Senior $132K（129）/ Lead $159K（19）/ Staff $200K（74）。Junior + Mid 全美仅 60 岗。AI/LLM 出现率 100%；技能栈 LangChain 24% + AWS 36% + Docker 21% + CI/CD 26%（工程落地型）。Top 雇主：Capital One 71、Capco 27、Sezzle 26、Bosch 18、NVIDIA 18。Remote 倒挂：remote median $143K < 整体 $160K。

**MLE 篇**（2,430 岗 / 919 公司，median $162K）：Junior $125K（27）/ Mid $139K（50）/ Senior $159K（170）/ Lead $172K（12）/ Staff $200K（145）/ Manager $189K（16）。技能栈 PyTorch 46% + TensorFlow 33% + MLOps 21%（训模型型），与 AIE 完全不是一个方向。Remote 溢价：$177K > 整体 $166K。Top 雇主：Adobe 48、Waymo 39、GM 33、Spotify 30、Toloka AI 25、Unity 20。

## 评论区方法论问答（原文摘录）

- DE 篇 Atyrau 问数据源 → 楼主："数据来源是现在公开的 ats 系统，现在差不多 2w 家公司，100w 个职位的样子，ats 系统上的职位描述应该还是准确的，所以我觉得爬出来应该还是有参考作用的"
- AIE 篇楼主首条评论（主动解释）："数据来自 Greenhouse、Lever、Workday、Workable 等平台超过 100 万个活跃职位发布，2.5w 个公司的样子……有的公司发布一个 jd 可能会招多人，确实是，现在的统计是默认认为一个 jd 一个坑，所以数据可能会有偏差……这个我确实没什么好的办法解决"
- nsc 问 LinkedIn 岗位是否包括 → 楼主未正面回答，只说"后面我做个网站，把数据放上去，供大家免费查看"
- 匿名用户 Q51YE 质疑 level 岗位数加总 ≠ 2434 → 楼主："写差了……大部分是根据 jd 描述中的年限要求来分的，jd 里没写的就没辙了"
- 楼主自我修正："'Junior 死透了'，这个发言确实武断了，有些 lever jd 里没提及，大家理性看待～"
- SE 篇唯一一次提到 ATS："数据主要是海外 ats 的"；另有人质疑"浓浓的 AI 味" → 楼主："哈哈，文案确实借助 ai 写的，数据是真的"

## 方法论评价

**优点**：上游真实（ATS 公开职位是一手结构化数据，绕开聚合站噪音）；口径统一（title 过滤 + JD 文本挖掘，多轮验证）；"取水"动作标准化，可复现（Greenhouse/Lever/Ashby 有公开 boards API；Workday 需 JS 渲染、反爬严，是真正的技术门槛）。

**黑箱**：4000 家公司名单是抽样框黑箱——Top 雇主榜（Capital One、PwC 等金融/咨询靠前）到底是真实需求还是名单偏差，外人验证不了；薪资 median 只统计了 JD 写薪资的样本（选择偏差）；level 推断依赖 JD 年限要求（80% SE 岗不写 seniority）；一个 JD 默认一个坑（楼主承认无解）。

**价值提炼链路**：ATS 公开职位（取水）→ 聚合分析：薪资分层、技能栈、雇主榜、remote 逻辑（烧水）→ 帖子内容 + 计划中的免费查询网站（呈现/分发）。"免费数据 + 处理 + 呈现"本身就是 focus 文件里记录的商业机会形态之一。
