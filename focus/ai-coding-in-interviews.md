# AI Coding in Interviews（面试中对 AI 辅助编程的考核）

*各公司如何在面试中允许 / 要求 / 评估候选人使用 AI 辅助 coding。从已收集帖子中提炼，持续更新。*

> 范围说明：这个文件只收"面试这个**形式**"——公司怎么考核你"用 AI 写代码"的能力。**不收** AI agent 的设计内容（那是 [ai-engineer.md](ai-engineer.md) 的事）。注意这和面什么职位无关：SWE 的 coding 轮也可能以 AI-augmented 形式出现。

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

- 其他公司的 AI-augmented coding 轮样本：允许 / 要求 / 禁用 AI 的政策差异
- take-home、OA 中对 AI 使用的规定

## 相关帖子

- [thread-1190471-snowflake-ai-engineer.md](../threads/thread-1190471-snowflake-ai-engineer.md)
