---
url: https://www.wenxuecity.com/news/2026/10/05/126795757.html
title: 华尔街AI人才争夺战升级：从"造模型"转向AI落地
published: 2026-10-05
source_note: 文学城转载；页面未署作者。核心数据来自企业招聘数据公司 Draup 独家提供给 CNBC 的分析（抓取 LinkedIn 等平台公开招聘信息）
type: 新闻（非面经）
collected: 2026-10-06
tags: [AI 人才需求, 招聘数据, Draup, Agent 编排, forward-deployed engineer, AI 治理]
---

# 华尔街AI人才争夺战升级：从"造模型"转向AI落地

- 原文：https://www.wenxuecity.com/news/2026/10/05/126795757.html
- 发布：2026-10-05；浏览约 4350+
- 数据来源：**Draup**（企业招聘数据公司）独家提供给 CNBC 的分析，基于抓取 LinkedIn 等平台公开招聘信息；引用 Draup CEO Vijay Swaminathan 及摩根大通 CEO 杰米·戴蒙表述；涉及摩根大通、花旗、Capital One 等银行
- 说明：Draup 未公开发布原始报告（2026-10-08 核查：其官网 draup.com 无此报告公开版，数据为独家提供给 CNBC；CNBC 2026-10-02 原文为 primary source）。数据最全的转述版本（含 2025 vs 2026 完整技能对照表）：https://techstartups.com/2026/10/02/wall-streets-hottest-ai-skill-surges-1721-as-banks-race-to-deploy-ai-agents/

## 核心数据

- 银行 AI 相关职位同比 **+49%**，约 **139,819** 个（摩根大通、花旗、Capital One 等）
- **Agent 编排工程师**需求引用量 **+1,721%**——华尔街当前最热技能；标志从聊天机器人阶段迈向多智能体协同处理业务（例：分别负责审查原始数据、分析文件、核查合规性的多个智能体协同）
- **前沿部署工程师（forward-deployed engineers）**崛起：把 AI 直接嵌入交易台、合规、后台运营等具体业务场景；要求技术能力 + 特定业务领域知识；任务复杂度远超预期（例：员工休假自动审批看似简单，实则大量边缘情况和例外）
- 工具链需求：**LangGraph +679%**、**LlamaIndex +291%**、**RAG +259%**；软性技能（解决问题、创造力、深层提问、对流程的深度理解）重要性回升
- **AI 治理岗爆发**："负责任 AI"引用 **+657%**，AI 治理 **+394%**、风险管理 **+359%**；治理类职位引用总量 16,000+，约模型训练/部署/运维类（8,400）的两倍；安全团队重点防第三方工具/外部模型接入的系统性安全漏洞
- 薪酬：生成式 AI 经理基本薪资中位数约 **19 万美元**，明显高于金融业其他技术岗；银行大力推进内部再培训弥合缺口；戴蒙谈及 AI 接管更多工作后的"大规模人员再部署计划"

## 收录价值

1. **AI Engineer 需求侧证据**：agent 编排 +1721%、forward-deployed engineer 崛起，直接对应 `focus/ai-engineer.md` 的"AI Agent 系统设计（核心）"考核维度——市场要的和面试考的是同一套能力
2. **上游数据 GTM 证据**：Draup 本人就是"抓招聘信息 → 卖人才分析"的已验证玩家，归入 `focus/upstream-data-gtm.md` 招聘数据类的 incumbent 案例
3. 用户计划据此写一篇职位需求分析帖，本文为素材之一

## 后续分析想法

- **公司官网 vs 招聘聚合站的"岗位差集"**：Draup 这类数据抓的是 LinkedIn 等聚合平台的公开信息。我们自建的公司库（直接抓各公司官网/ATS 职位页）可以回答一个聚合数据回答不了的问题——**有哪些岗位只出现在公司官网上，从没上过聚合网站？**
  - 这部分"暗岗位"可能包括：只在官网发布的保密岗、更新滞后的长尾岗、或公司有意不向聚合站同步的岗位
  - 方法：用公司库抓到的职位（req ID + title + 地点）与 LinkedIn/Indeed 等聚合站的同公司职位做匹配，差集即为"官网独有"
  - 价值：如果差集里 AI 岗占比显著高于聚合站口径，说明基于聚合数据的 AI 人才需求统计（如 Draup 这篇）系统性低估了真实需求——这正是自建上游数据相对 Draup 的差异化价值

---

# 华尔街开始为 AI 技能付费：加薪/奖金/晋升挂钩（Selby Jennings 调查）

- 原文（文学城转载）：https://www.wenxuecity.com/news/2026/10/14/126804880.html
- 发布：2026-10-14 13:40:39；抓取时约 3570 阅读、2 评论；页面标注"文章来源：华尔街见闻"，**未给任何回链**
- 信源链（三层）：**Reuters 一手**（2026-10-14，Nupur Anand，"Wall Street firms tie bonuses, promotions to AI skills, survey finds"，https://www.reuters.com/business/finance/wall-street-firms-tie-bonuses-promotions-ai-skills-survey-finds-2026-10-14/ ）→ **华尔街见闻二手编译**（自拟标题"想升职加薪走向人生巅峰？在华尔街 你得先懂AI"，"人生巅峰"是编译加的味，路透原标题是中性陈述句）→ **文学城三手转载**
- 调查方：**Selby Jennings**（金融服务招聘公司，Phaidon International 菲顿国际旗下）；执行方 **Censuswide**，调查时间 2026-08-19 至 08-26（据 yellow.com，路透未写）
- **样本口径出入**：路透写 "500 executives"，yellow.com 写 "500 finance HR professionals"——无原始报告，对不上

## 核心数据

- 约 **1/4** 机构将 AI 熟练度与加薪/奖金/晋升挂钩
- **30%** 要求员工在绩效评估中披露 AI 工具使用情况
- **42%** 引入正式标准评估员工 AI 技能
- **30%** 组建专门团队/职能角色追踪 AI 投入回报
- Dylan Gomez（Selby Jennings 执行董事，直接接受路透采访）："企业不再只看员工是否用 AI，而是开始监测其对产出的实际影响"；目前无统一的薪酬挂钩量化标准，预计明年更清晰
- Jacob Summers（Selby Jennings 技术招聘负责人，据 yellow.com 引述）：该做法在金融科技初创和小公司更普遍，大银行反而保守；**招聘时 AI 技能权重约是大学背景的 4 倍**
- 横向参照（yellow.com 引 investmentnews.com）：PwC 更大样本调查（1000 名美国金融高管）显示 58% 计划将薪酬与 AI 生产力挂钩，86% 认为 AI 培训比 MBA 更重要，90%+ 已在给有 AI 技能的员工加薪

## 一手报告核查（2026-10-15 初查；2026-10-16 用户找到公开页，修正）

- **公开报告地址**：https://www.selbyjennings.com/insights/ai-talent-pulse-report/ （标题 "AI Talent Pulse Report: The AI Fluency Gap"）。此前在 newsroom 路径（/en-us/industry-insights/...）下只找到同名占位页且内容未渲染，系站内多路径问题 —— "无公开发布"的初判不准确，insights 路径下有完整公开页
- **方法论（一手确认）**：Censuswide 执行，**500 名美国金融业 HR 专业人士**（22–64 岁），2026-08-19 至 08-26。结论：yellow.com 的 "500 HR professionals" 是对的，**路透的 "500 executives" 是宽松写法** —— 样本口径出入至此解决
- **报告四部分结构**：Part 1 招聘盲区 / Part 2 "AI fluency 是不是新的藤校？" / Part 3 候选人用 AI 作弊 vs HR 反制 / Part 4 AI 技能进绩效。**路透只取了第四部分**（薪酬挂钩，最新闻点）；报告真正的主线是第一部分 —— 招得越快越盲目：AI 岗招聘量 +74%、招聘 spend +70%，但 31% 说内部没人能自信评估候选人，50% 说面到的不合格候选人变多了
- **发言人**：报告页署名 Ben Hodzic（Managing Director）；路透引的是 Dylan Gomez（Executive Director）—— 媒体通稿给了两个发言人，通稿口径一致
- 信息最全的二手版本仍是 yellow.com（https://yellow.com/news/financial-firms-reward-ai-fluency-survey ），它还整合了 Semafor 的 Jacob Summers 采访（"AI 技能权重约是大学背景 4 倍"，报告公开页未见此句，应为通稿专访口径）

## 收录价值

1. **需求侧→薪酬侧的闭环证据**：上一篇 Draup 讲的是"招什么人"（agent 编排 +1721%），这篇讲的是"怎么考核/付费"（1/4 机构挂钩薪酬）——AI 技能从招聘卖点变成绩效考核项，说明华尔街 AI 落地进入"要 ROI"的第二阶段
2. **方法论警示**：招聘公司做"AI 技能溢价"调查有立场动机（卖人才生意的），且样本定义在转述中走样（executives vs HR professionals）——引用时需标注信源立场，这正是本系列"溯源"的意义
3. 英文圈同日跟进：Finimize、fstech.co.uk，均注明 "seen by Reuters" / "told the newswire"，侧面坐实路透为一手
