# AI 能帮你干什么：个人实战清单

*不谈商业、不谈方法论，只谈 AI 在你（求职者/工程师）手里具体能干什么——每条都来自地里帖子的实战经验。*

> 范围说明：收"个人怎么用 AI 干活"。与 [ai-value-creation.md](ai-value-creation.md) 的分工：那篇谈"AI 在流程里的正确分工 + 上游数据方法论"（偏商业/方法论），这篇谈"你个人拿 AI 干什么"（偏个人实战）。与 [ai-coding-in-interviews.md](ai-coding-in-interviews.md) 的分工：那篇谈"公司在面试里怎么考核你用 AI"，这篇谈"你平时怎么用 AI"。

## 求职：面经 + AI 对答案

thread 1183413（被裁两次找工 10 个月总结，作者 35 家去重、11 个 onsite、3 个 offer）的准备方法："每次拿到面试先去一亩三分地**翻面经**，再和 **Claude** 一起讨论答案"。

注意这个顺序：**先有人的一手面经，再让 AI 参与讨论**。AI 的角色是讨论/验证，不是替你背答案。同一帖作者认为"最有用的"还是把自己做过的项目重新拆一遍——为什么这么设计、哪里出过问题、数据和 trade-off 是什么；"没做过的东西背得再熟，被追问几层也很容易露馅"。

AI 在这里的正确用法是当**追问者**：把你的项目描述喂给它，让它扮演面试官往深了追问 trade-off，而不是让它替你编答案。

## 求职：反向拆 JD

thread 1178971 系列（ATS 招聘数据抓取）的方法论可以反过来用：作者用"JD 文本挖技能关键词出现率"区分出 AIE（LangChain+AWS+Docker 工程落地型）和 MLE（PyTorch+TF+MLOps 训模型型）是两种不同的技能栈。求职者可以把目标岗位的 JD 批量喂给 AI，拆出技能关键词出现率，对照自己的简历找 gap——这正是 AI 擅长的"结构化文本处理"（thread 1186353"烧水不取水"四件事之三）。

## 工作：AI coding 日常提效

面试里各公司对 AI coding 是 allow / require / ban 三种政策（见 [ai-coding-in-interviews.md](ai-coding-in-interviews.md) 政策表），但那是**考核场景**。日常工作中，AI 写样板代码、解释报错、补测试、写文档注释是纯提效——两回事。不要因为面试有政策限制，就在日常也不用。

## 省钱：AI 只用在刀刃上

thread 1178300（Jobuzzer，监控 7k→9k 家公司招聘页）的成本纪律："AI 很烧钱…有新工作才让 AI/agent 工作，否则成本会高到破产"。技术路线是 ATS API → 渲染浏览器 → LLM 三级，**先用工程方式 diff 出变化，有增量才交给 AI 做分类整理**。

个人启示：无论用免费额度还是订阅，把 AI 留给"判断/分类/整理/解释"这类高价值环节；能用脚本、模板、diff 解决的别上 LLM。这条对自建 agent/工作流同样适用。

## 边界：AI 干不了的三件事

1. **替你取水**：[ai-value-creation.md](ai-value-creation.md)"烧水不取水"——AI 给的是一万个人问同一个问题得到的一万份相同的二手答案（thread 1186353），上游信息（牌照名单、H-1B 数据、一手面经）得自己去拿。
2. **替你验证**：AI 说的事实要一手验证。thread 1190956 里 OpenAI 面试"允许 AI"这一行在 repo 里标注的就是"待一手验证"——连我们自己收录的信息都这样要求，对 AI 的输出更该如此。
3. **替你做没做过的事**：thread 1183413 作者的警告——"没做过的东西背得再熟，被追问几层也很容易露馅"。AI 能帮你整理表达，变不出你没做过的经历。

## 相关帖子

- [thread-1183413-laid-off-twice-10-month-job-search.md](../threads/thread-1183413-laid-off-twice-10-month-job-search.md)——面经 + Claude 对答案、项目深挖准备法。
- [thread-1178971-ats-job-scraping.md](../threads/thread-1178971-ats-job-scraping.md)——JD 技能关键词挖掘方法论（反向用于求职）。
- [thread-1178300-jobuzzer.md](../threads/thread-1178300-jobuzzer.md)——"AI 只用在刀刃上"的成本纪律。
- [thread-1186353-upstream-info-job-hunting.md](../threads/thread-1186353-upstream-info-job-hunting.md)——"烧水不取水"：AI 正确分工的源头。
