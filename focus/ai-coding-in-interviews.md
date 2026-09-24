# AI Coding in Interviews（面试中的 AI 编程）

*从已收集帖子中提炼，持续更新*

## 公司怎么考：允许 / 要求 / 评估

**Snowflake —— "AI Augmented coding" 轮（thread 1190471，最完整的样本）**
- 要求**自带电脑**，可提前预装任何 AI（也可用面试官的电脑）
- 题型有两种："refactor and debug" 和 "design and build"（楼主抽到后者：design and implement a rate limiter）
- 考察重点：
  - 可以用 AI 写 code，但必须**自己讲清楚**：选哪个 algorithm、为什么选这个、还有什么别的 algorithm、tradeoff 是什么
  - 现场展示**怎么和 AI 交流、怎么 review AI 写的代码、怎么测试**
- 楼主（codex + claude 双 max 用户）评价：平时 AI native 的人会比较轻松愉快

## 求职者怎么用 AI 准备面试

- **和 Claude 一起讨论面试答案**：拿到面试先去一亩三分地翻面经，再和 Claude 讨论答案（thread 1183413 楼主的方法）
- **用 Codex 自动生成找工总结**：1183413 的正文本身就是楼主用 Codex 基于聊天记录、邮件和 calendar 生成的
- **动手做小 agent 然后讲清设计决策**：调 API + MCP + 简单 eval，能说出为什么选这个 orchestration 方式、怎么 eval、失败怎么兜底（thread 1188022）

## 备考要点

- 练熟全流程：**"用 AI 写代码 + 口头讲清设计决策和 tradeoff + 现场 review AI 代码 + 写测试"**
- 经典题（如 rate limiter）的各种算法及 tradeoff 要能**脱口而出**，不能只会让 AI 写
- 关键区分点：AI 是工具，面试官考的是你的**判断力**——选型理由、tradeoff 分析、代码审查能力
- 平时就用 AI 写代码的人有天然优势，但"会 prompt"不等于"能讲清为什么"

## 相关帖子

- [thread-1190471-snowflake-ai-engineer.md](../threads/thread-1190471-snowflake-ai-engineer.md)
- [thread-1183413-laid-off-twice-10-month-job-search.md](../threads/thread-1183413-laid-off-twice-10-month-job-search.md)
