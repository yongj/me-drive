# AI Engineer 职位面试考核内容汇总

*面 AI Engineer（agent 方向）这个职位时，公司会考什么。从已收集帖子中提炼，持续更新。*

> 范围说明：这个文件只收"AI Engineer 职位考什么"——Agent 系统设计、相关知识、动手实践、项目深挖。**不收**"面试中怎么考核你用 AI 写代码"（那是 [ai-coding-in-interviews.md](ai-coding-in-interviews.md) 的事）。

## 考核维度

### 1. AI Agent 系统设计（核心）
- 设计**自动提取/蒸馏 agent skill 的 pipeline**（Snowflake onsite，thread 1190471）
- **agent memory 的常见 component**（Snowflake，thread 1190471）
- **几十条法律规则修改合同**：每条规则 spin up 一个 sub agent 并行修改，overlap 的部分再让其他 agent 去 merge（Harvey AI onsite，thread 1190457）——考察任务分解、子 agent 并行、重叠修改的冲突检测与合并策略

### 2. 相关知识
按"层"准备（thread 1188022 回帖 peddlefish 的框架——先搞清楚目标公司考哪一层）：
- **应用编排层**：tool calling、MCP、工作流设计 → Anthropic《Building Effective Agents》、OpenAI《A Practical Guide to Building Agents》（短但密度高，必读）
- **工程与可靠性层**：eval、latency/cost tradeoff、failure recovery、安全 → Chip Huyen《AI Engineering》书和博客
- 中文资料：李博杰《深入理解 AI Agent：设计原理与工程实践》：https://github.com/bojieli/ai-agent-book（开源免费，偏工程实现）
- 视频：Agent memory 常见组件：https://www.youtube.com/watch?v=mY3bR9qjZr4&t=56s
- 入门级（应付面试不够）：IBM RAG & Agentic AI 证书：https://www.coursera.org/professional-certificates/ibm-rag-and-agentic-ai

### 3. 动手实践 / Coding
- 现场实现 **embedding & retrieval via cosine similarity**（colab 环境，Harvey AI，thread 1190457）——向量归一化、cosine similarity 计算、top-k 检索及相关度量概念

### 4. 项目深挖（Senior 岗核心）
- 把自己做过的项目重新拆一遍：为什么这么设计、哪里出过问题、数据和 trade-off 是什么；没做过的东西背得再熟，被追问几层也容易露馅（thread 1183413）
- 例：一家 AI startup 的 agent API 轮，楼主能答下去"主要是因为那套系统我真的做过"

## 备考要点

- **自己动手做一个小 agent**（调 API + MCP + 简单 eval），能讲清楚设计决策：为什么选这个 orchestration 方式、怎么 eval、失败了怎么兜底、成本和延迟怎么权衡
- 面试官想听的是 **tradeoff，不是工具列表**
- 先定位目标公司考的是哪一层，再选资料，别眉毛胡子一把抓

## 市场需求信号（2026-10）

- Draup 独家给 CNBC 的分析（抓 LinkedIn 公开招聘，见 [misc/wall-street-ai-talent-demand-2026-draup.md](../misc/wall-street-ai-talent-demand-2026-draup.md)）：银行 AI 职位同比 +49%（约 139,819 个）；**Agent 编排工程师需求 +1,721%**——华尔街当前最热技能；**前沿部署工程师（forward-deployed engineers）**崛起（AI 直嵌交易/合规/运营场景，要求技术+业务领域知识）；LangGraph +679%、LlamaIndex +291%、RAG +259%；AI 治理类引用量约模型训练部署类的两倍
- 解读：市场要的（agent 编排、多智能体协同、AI 落地业务）和面试考的（Agent 系统设计）是同一套能力；"forward-deployed"这个 title 值得在求职时重点关注

## 相关帖子

- [thread-1190471-snowflake-ai-engineer.md](../threads/thread-1190471-snowflake-ai-engineer.md)
- [thread-1190457-harvey-ai-engineer-onsite.md](../threads/thread-1190457-harvey-ai-engineer-onsite.md)
- [thread-1188022-ai-agent-design-resources.md](../threads/thread-1188022-ai-agent-design-resources.md)
- [thread-1183413-laid-off-twice-10-month-job-search.md](../threads/thread-1183413-laid-off-twice-10-month-job-search.md)
