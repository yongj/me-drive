# AI Coding in Interviews（面试中对 AI 辅助编程的考核）

*各公司如何在面试中允许 / 要求 / 评估候选人使用 AI 辅助 coding。从已收集帖子中提炼，持续更新。*

> 范围说明：这个文件只收"面试这个**形式**"——公司怎么考核你"用 AI 写代码"的能力，以及各公司对面试中 AI 使用的政策（允许 / 要求 / 禁用）。**不收** AI agent 的设计内容（那是 [ai-engineer.md](ai-engineer.md) 的事）。注意这和面什么职位无关：SWE 的 coding 轮也可能以 AI-augmented 形式出现。

## 公司怎么考

### Snowflake —— "AI Augmented coding" 轮（thread 1190471，目前最完整的样本）
- 要求**自带电脑**，可提前预装任何 AI（也可用面试官的电脑）
- 题型有两种："refactor and debug" 和 "design and build"（楼主抽到后者：design and implement a rate limiter）
- 考核点：
  1. 可以用 AI 写 code，但必须**自己讲清楚**：选哪个 algorithm、为什么选这个、还有什么别的 algorithm、tradeoff 是什么
  2. 现场展示**怎么和 AI 交流**（prompt、迭代）
  3. **怎么 review AI 写的代码**
  4. **怎么写测试**验证
- 楼主（codex + claude 双 max 用户）评价：平时 AI native 的人会比较轻松愉快

## 公司政策对比：允许 / 要求 / 禁用

（截至 2026-10-02；政策变化快，备考前以 recruiter 给的最新说明为准）

| 公司 | 政策档 | 形式 / 说明 | 出处 |
| --- | --- | --- | --- |
| Meta | 允许（已上线） | 2025-10 上线的 AI-enabled coding 轮，替代两轮 onsite coding 中的一轮：60 分钟 CoderPad，会话内置 AI（可选 GPT-4o mini、GPT-5、Claude Sonnet 4/4.5、Gemini 2.5 Pro、Llama 4 Maverick 等）。有 AI 之后题目反而更难：偏向模糊需求、系统级思考，AI 能搭脚手架但做不完。2026 年向所有后端 / 运维岗位铺开 | [mlq.ai（2025-08 试点报道）](https://mlq.ai/news/meta-pilots-ai-assisted-coding-interviews-letting-candidates-use-ai-tools-in-technical-assessments/)、[Montes（2026-03 rollout 细节）](https://medium.com/@montes.makes/meta-gave-candidates-gpt-5-and-claude-during-interviews-the-questions-got-harder-ca11b34774c1) |
| Google | 允许（试点） | 2026 下半年起的试点：美国部分团队（Cloud、Platforms & Devices）初中级 SWE 岗位新增"代码理解"（code comprehension）轮，可用 Google 指定的 AI 助手（Gemini），内容是读 / 调试 / 优化现有代码库。考核明确包含"AI 熟练度"：prompt、输出验证、debug。配套改动：Googleyness & Leadership 轮改为讨论候选人过往项目的技术细节，初级岗一轮传统技术轮换成开放式工程挑战。招聘 VP Brian Ong 对 BI 确认：试点是为"更贴近团队在 AI 时代的实际工作方式"（human-led, AI-assisted）。试点成功再全球推广 | [webpronews（BI 内部文件报道，2026-05）](https://www.webpronews.com/google-lets-candidates-bring-ai-to-interviews-inside-the-pilot-reshaping-tech-hiring/)、[thehrdigest（2026-05 报道）](https://www.thehrdigest.com/using-ai-assistants-during-job-interviews-google-embraces-a-new-era-of-hiring/)、[Exponent 2026 指南](https://www.tryexponent.com/blog/google-ai-coding-interview) |
| LinkedIn | 允许（已成标配） | AI-enabled 轮已成标准：两轮 coding 中的一轮，在 CoderPad 上带 AI 聊天面板（Claude/Opus 级）。AI 不能直接改代码——你负责粘贴和验证。4 分制，3 分过，按相对排名打分；写出能跑的代码之后，追问才是真正的门槛（并发 / 线程安全、扩展性、脏输入、生产就绪） | [coding-interview-questions（2026 年 FAANG 政策表）](https://github.com/shanmukhdatta/coding-interview-questions/blob/HEAD/FAANG-Recent-Questions.md) |
| Snowflake | 要求 | "AI Augmented coding" 轮：要求**自带电脑**，可提前预装任何 AI（也可用面试官的电脑）。详见上面"公司怎么考" | [thread-1190471](../threads/thread-1190471-snowflake-ai-engineer.md) |
| Canva | 要求 | 2025 年 6 月起强制：传统 CS 基础轮换成"AI-Assisted Coding"轮，覆盖后端 / 前端 / ML 岗位。候选人用自带 AI 助手（Copilot、Cursor、Claude 均可），60 分钟内在脚手架项目里完成产品向任务（如实现模板系统），边做边讲清思路；考核的是指挥 AI、review 输出、抓 bug 和 edge case 的能力。官方原话："Yes, you can use AI in our interviews. In fact, we insist." | [The Register（2025-06 报道）](https://www.theregister.com/software/2025/06/11/canva-now-requires-use-of-ai-during-developer-job-interviews/)、[dig.watch（2025-06）](https://dig.watch/updates/canva-makes-ai-use-mandatory-in-coding-interviews)、[Final Round AI（2026 指南）](https://www.finalroundai.com/blog/canva-interview-process) |
| Amazon | 禁用 | 严格禁 AI：从 OA 到终面全程"零辅助"。面试官会盯异常停顿、瞟屏幕、答案过于完美等信号 | [ITPro 2025-03 报道，经 Medium 整理](https://medium.com/@the_tiredman/ai-in-interviews-why-meta-allows-it-and-amazon-bans-it-and-what-it-means-for-job-seekers-7019ac6b5565) |
| Anthropic | 分情况 | take-home 可用 AI；live 面试严格禁用 | [coding-interview-questions（2026 年 FAANG 政策表）](https://github.com/shanmukhdatta/coding-interview-questions/blob/HEAD/FAANG-Recent-Questions.md) |
| ByteDance / Palantir | 禁用 | 明确禁用 AI | [同上](https://github.com/shanmukhdatta/coding-interview-questions/blob/HEAD/FAANG-Recent-Questions.md) |
| OpenAI | 允许（公开信息汇编，待一手验证） | 楼主整理称 OpenAI 明确面试中可用 AI 生成辅助代码并解释；出处为公开信息汇编帖、非一手面经，备考前以 recruiter 说明为准 | [thread-1190956](../threads/thread-1190956-ai-rewriting-sde-interviews.md) |

新政策帖按上表加一行即可：公司、政策档（允许 / 要求 / 禁用 / 分情况）、形式说明、带链接的出处。

## 考核维度提炼

1. **AI 协作能力**：能不能高效地跟 AI 交流、迭代出正确的代码
2. **代码审查能力**：能不能发现 AI 生成代码的问题，不盲信 AI
3. **测试意识**：会不会写测试来验证 AI 的输出
4. **设计判断力**：算法选型和 tradeoff 必须自己讲清楚——这是 AI 替不了的部分，也是面试官真正要听的

## 备考要点

- 练熟全流程：**"用 AI 写代码 + 口头讲清设计决策和 tradeoff + 现场 review AI 代码 + 写测试"**
- 经典题（如 rate limiter）的各种算法及 tradeoff 要能**脱口而出**，不能只会让 AI 写
- 平时就用 AI 写代码的人有天然优势，但"会 prompt"不等于"能讲清为什么"

## 待补充

- 继续加行：Apple、Microsoft、DoorDash 等的政策（按上表格式）
- take-home、OA 中对 AI 使用的规定

## 相关帖子

- [thread-1190471-snowflake-ai-engineer.md](../threads/thread-1190471-snowflake-ai-engineer.md)
- [thread-1190956-ai-rewriting-sde-interviews.md](../threads/thread-1190956-ai-rewriting-sde-interviews.md)（2025-2026 面试政策变化汇编：OA 防作弊、Meta/Google/OpenAI 允许 AI 辅助、AI 原生场景题）
