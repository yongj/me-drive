# AI Engineer（Agent 方向）资料汇总

*从已收集帖子中提炼，持续更新*

## 学习资料

**必读（短但密度高）**
- Anthropic《Building Effective Agents》——应用编排层：tool calling、MCP、工作流设计
- OpenAI《A Practical Guide to Building Agents》——同上

**工程与可靠性层**
- Chip Huyen 的 AI Engineering 书和博客——eval、latency/cost tradeoff、failure recovery、安全
- 李博杰《深入理解 AI Agent：设计原理与工程实践》：https://github.com/bojieli/ai-agent-book（开源免费，中文，偏工程实现）

**视频**
- Agent memory 常见组件：https://www.youtube.com/watch?v=mY3bR9qjZr4&t=56s

**入门级（应付面试不够）**
- IBM RAG & Agentic AI 证书：https://www.coursera.org/professional-certificates/ibm-rag-and-agentic-ai（偏入门科普）

## 面试考的"层"（来自 thread 1188022 回帖 peddlefish）

先搞清楚目标公司考的是哪一层，资料完全不同：

1. **应用编排层**：tool calling、MCP、工作流设计 → 读 Anthropic / OpenAI 那两篇
2. **工程与可靠性层**：eval、latency/cost tradeoff、failure recovery、安全 → 读 Chip Huyen

## 真实考题

- **设计自动提取/蒸馏 agent skill 的 pipeline**（Snowflake AI Engineer onsite，thread 1190471）
- **agent memory 常见 component**（Snowflake，thread 1190471）
- **几十条法律规则修改合同**：每条规则 spin up 一个 sub agent 并行修改，overlap 的部分再让其他 agent 去 merge（Harvey AI onsite，thread 1190457）——考察任务分解、子 agent 并行、重叠修改的冲突检测与合并策略
- **现场实现 embedding & retrieval via cosine similarity**（colab 环境，Harvey AI，thread 1190457）——向量归一化、cosine similarity 计算、top-k 检索及相关度量概念

## 备考要点

- **自己动手做一个小 agent**（调 API + MCP + 简单 eval），能讲清楚设计决策：为什么选这个 orchestration 方式、怎么 eval、失败了怎么兜底、成本和延迟怎么权衡
- 面试官想听的是 **tradeoff，不是工具列表**
- Senior 岗：**项目深挖是核心**——为什么这么设计、哪里出过问题、数据和 trade-off 是什么；没做过的东西背得再熟，被追问几层也容易露馅（thread 1183413）

## 相关帖子

- [thread-1190471-snowflake-ai-engineer.md](../threads/thread-1190471-snowflake-ai-engineer.md)
- [thread-1190457-harvey-ai-engineer-onsite.md](../threads/thread-1190457-harvey-ai-engineer-onsite.md)
- [thread-1188022-ai-agent-design-resources.md](../threads/thread-1188022-ai-agent-design-resources.md)
- [thread-1183413-laid-off-twice-10-month-job-search.md](../threads/thread-1183413-laid-off-twice-10-month-job-search.md)
