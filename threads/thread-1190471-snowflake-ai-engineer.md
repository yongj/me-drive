---
thread_id: 1190471
url: https://www.1point3acres.com/home/thread/1190471
title: 雪花 AI Engineer 昂赛特
company: Snowflake
role: AI Engineer（偏 agent 方向）
posted: 2026-09-23
result: Pass（楼主最终未接 offer）
collected: 2026-09-25
tags: [AI Engineer, agent, AI Augmented Coding, system design, rate limiter, agent memory]
---

# 雪花 AI Engineer 昂赛特

- 原贴：https://www.1point3acres.com/home/thread/1190471（海外面经版，作者匿名，发帖 2026-09-23，0 回帖）
- 楼主背景：MLE，在职跳槽；其他家都面偏模型岗，只有这家面偏 agent
- 组里直招（非 general hire）；实打实的 in-person onsite，要去 office

## 时间线

1. 一轮 coding：正常 leetcode
2. 一轮 ML Fundamental（他家叫 ML Expertise）
3. onsite 共三轮

## Onsite 三轮详情

### 1. AI Augmented coding（特色轮）
- 要求自带电脑，可提前预装任何 AI（也可用面试官电脑）
- 题型有两种："refactor and debug" 和 "design and build"，楼主抽到后者
- 题目：design and implement a rate limiter（经典系统设计题）
- **考察重点**：可以用 AI 写 code，但必须自己讲清楚——选哪个 algorithm、为什么选这个、还有什么别的 algorithm、tradeoff 是什么；还要现场展示自己是怎么和 AI 交流的、怎么 review AI 写的代码、怎么测试
- 楼主评价：平时 AI native 的人会比较轻松愉快

### 2. Expertise（贴合组里实际工作的 system design）
- 如何设计一个能自动帮企业用户提取/蒸馏 agent skill 的 pipeline
- agent memory 里的常见 component

### 3. Behavior
- 和 Hiring Manager 聊，正常的 behavior 轮

## 其他信息

- 发 offer 前有 **reference check**，需要提供两个联络人（前同事或前老板）
- 薪资给得大方，但**没有公式性 refresh**（每年的 refresh 看老板心情）
- 楼主最终没选：更想做模型相关 + 听说文化很毒；但推荐偏 agent 方向的人去面

## 准备资料（帖中提到的）

- Rate limiter 系统设计：https://www.geeksforgeeks.org/system-design/rate-limiting-algorithms-system-design/
- Agent skill 提取/蒸馏 pipeline 设计题：https://tctothemoon.com/questions/tctm-29
- Agent memory 常见组件：https://www.youtube.com/watch?v=mY3bR9qjZr4&t=56s

## 有价值的回帖

- 无（本帖 0 回复）

## 备考要点

- **AI Augmented coding 轮**：练熟"用 AI 写代码 + 口头讲清设计决策和 tradeoff + 现场 review AI 代码 + 写测试"的全流程；rate limiter 各算法（token bucket、leaky bucket、fixed/sliding window log/counter）及 tradeoff 要能脱口而出
- **Agent 方向 system design**：skill 提取/蒸馏 pipeline 的设计思路；agent memory 组件（short-term / long-term、episodic / semantic 等）
- Reference check 提前准备好两个愿意配合的联络人
