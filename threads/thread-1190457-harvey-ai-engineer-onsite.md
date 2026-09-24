---
thread_id: 1190457
url: https://www.1point3acres.com/home/thread/1190457
title: Harvet Ai engineer onsite（title typo；实际公司为 Harvey AI）
company: Harvey AI
role: AI Engineer（码农类 General）
posted: 2026-09-23
result: Fail
collected: 2026-09-24
tags: [AI Engineer, system design, multi-agent, sub agent, merge, cosine similarity, embedding, retrieval]
---

# Harvet Ai engineer onsite（Harvey AI）

- 原贴：https://www.1point3acres.com/home/thread/1190457（海外面经版，作者 sjc1，发帖 2026-09-23 北京时间 10:39；查看数当前 UI 未展示，1 回帖）
- 楼主档案：硕士；2 年经验（1–3 年范围）；在职跳槽；网上投递；找工季 2026 年 7–9 月
- 职位：码农类 General / AI Engineer；面试类别 Onsite；工作类别 全职
- 结果：Fail；体验 Neutral；难度 Average

## 楼主正文（原文摘录）

"1. Onsite system design : 根据几十个不同的法律规则(给出)修改合同（给出. 正确方式是根据每个规则spin up 一个sub agent, 分别修改， overlap的部分再让其他agent去merge.
2. bq: 常规聊项目
3. coding: 一个 实现embedding & retrieval via cosine similarity 的 colab, 需要对cosine similarity和 corresponding metric很熟悉"

## 各轮详情

### 1. Onsite System Design（Agentic / AI 系统设计）
- 题面：给出几十条不同的法律规则和一份合同，要求按规则修改合同
- 楼主标注的"正确方式"：为**每一条规则 spin up 一个 sub agent**，各自独立修改；多条规则影响同一条款（overlap）的部分，再让**其他 agent 去 merge**（协调合并）
- 考察点：多智能体并行修改 + 冲突合并的架构设计——任务分解、子 agent 并行、重叠修改的冲突检测与合并策略；典型"法律文档 + LLM agent"场景题

### 2. BQ
- 常规聊项目（无具体问题记录）

### 3. Coding（hands-on，colab 环境）
- 现场实现 **embedding & retrieval via cosine similarity**（余弦相似度的 embedding 与检索）
- 楼主强调：需要对 **cosine similarity 和 corresponding metric** 非常熟悉（向量归一化、相似度与距离的关系、top-k 检索及相关度量概念）
- 楼主未描述自己具体如何作答，也没有逐轮结果；帖子未提具体面试日期和地点

## 有价值的回帖

- 无实质干货：唯一回帖来自 trthank829（2026-09-24 13:32）："这全是新题啊"——侧面说明这几道题当时在地里较为新鲜/少见

## 准备资料（帖中提到的）

- 楼主未提到任何书籍、网站或备考资料；帖中唯一外链是 ByteByteGo 论坛广告（附优惠码 `1p3acre`），并非备考推荐

## 公司卡片（论坛聚合，仅供参考）

- Harvey AI 地里数据：84 主题 / 814 回复 / 61 篇面经 / 12 个工资数据 / 3 个内推 / 6 个讨论
- 基本工资平均值 **$250,000**（2026-09-24 更新）

## 备考要点

- **System Design**：重点练多 agent 协作的系统设计——任务分解（per-rule sub agent 并行）、子 agent 并行执行、overlap 冲突的检测与 merge 机制；能讲清多智能体并发修改同一文档时的冲突处理与一致性
- **Coding**：熟练实现 cosine similarity embedding 检索——向量归一化、cosine similarity 计算、top-k 检索及相关度量概念
- **场景熟悉**：法律规则→合同条款修改这类领域约束的 agent 设计是 Harvey AI 的典型业务场景，提前了解 legal-tech 用例加分
