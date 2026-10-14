---
thread_id: 1192987
url: https://www.1point3acres.com/home/thread/1192987
title: 人类学senior全套面经（Anthropic senior SWE）
company: Anthropic
role: Senior SWE（码农类 General）
posted: 2026-10-14
result: Pass
collected: 2026-10-15
tags: [Anthropic, senior SWE, onsite, OA, system design, prompt playground, LRU cache, WAL, multiprocessing, image processing, culture fit, reference check, pool hire]
---

# 人类学senior全套面经（Anthropic senior SWE）

- 原贴：https://www.1point3acres.com/home/thread/1192987（海外面经版，作者匿名用户-L8XZE，发帖 2026-10-14 11:07；6 回复，其中 3 条为楼主本人回复）
- 注：标题"人类学"即 Anthropic 的谐音梗；以下内容为楼主自述的意译转述
- 楼主档案：硕士；4 年多 YOE；在职跳槽；内推，内推后 2 个工作日收到 recruiter 联系；找工季 2026 年 7–9 月
- 职位：码农类 General / Senior SWE；面试类别 Onsite；工作类别 全职
- 结果：Pass；体验 Positive；难度 Hard

## 面试流程（按顺序）

1. **OA**：bank system 题。楼主提前准备过（答案已背熟），拿满分；提醒听说最好做满分
2. **Recruiter call**：why anthropic + 对 AI safety 的看法
3. **店面 coding**：猫图片的图像处理题（image processing），分两个 part
4. **Pool hire → match**：最初是 pool hire，店面后安排的 onsite loop 里已含 hiring manager 轮，判断已 match 到具体组
5. **Onsite 共 5 轮**：system design → coding → project deep dive → culture → hiring manager
6. **Reference check**：材料在 onsite 之前就提交了（recruiter 称可加快进度）；店面后约 2 个工作日楼主催了一下，recruiter 回复开始走 reference check

## 各轮详情

### 1. 店面 Coding：图像处理（pillow + multiprocessing）
- 题面：猫图片的 image processing，题目明确要求用 pillow 做图像库，并给出每个 transform 的调用方法
- Part 1：基础图像处理（按给定 transform 实现）
- Part 2：时间优化——楼主用 **multiprocessing** 实现；面试官追问**为何选 multiprocessing 而非 multithreading**，以及**用几个 worker 合适**（进程开销 vs worker 数量的 tradeoff）
- 两个 part 的测试都通过；测试会显示跑完所有图片的总耗时
- 考察点：pillow 实操 + 并行优化的工程 tradeoff（GIL、进程开销、worker 数量选择）

### 2. Onsite System Design：prompt playground（提示词游乐园）
- 与站内既有 Anthropic 面经一致：先写基础 database schema
- 面试官有一串预设 follow-up，逐一深入（每答完一个就打断推向下一个）：
  - large prompt 如何处理
  - share 功能
  - 用户每次只改一两个字符时的存储策略
- 楼主方案：存 **delta**；需进一步考虑 delta 存到哪里（object storage vs database），并对各方案做 tradeoff
- 考察点：AI 产品场景的系统设计——大文本存储、增量更新、分享功能；重点是 follow-up 驱动的 tradeoff 论述

### 3. Onsite Coding：LRU cache（2 parts，WAL 恢复）
- Part 1：为函数及其参数生成缓存 key（generate key for function and arguments）
- Part 2：从 crash 中恢复缓存——楼主给出 **WAL** 方案
- 注意与 hack2hire 版本不同：题目给了 file_path，要求**每次 append log 时打开文件写入磁盘**；楼主不熟悉 Python 中如何设定 delimiter，纠结如何 partition log 才能在重读时正确 split，最后面试官提示可用**换行符分隔**
- 结果：没时间 debug 完，test case 没跑过就结束了；面试官人很好，让楼主写到最后一刻
- 楼主建议这道题要好好准备
- 回帖追问（PXLCW）：复杂数据类型作 key 怎么办（如 set、dict）？楼主回复：kwargs 本身是 dictionary；他当场问了面试官 dict 内部的 type，对方说**可以假设给定的 type 都是可序列化的**，题目里也给出了 serialize 的用法

### 4. Onsite Project Deep Dive
- Recruiter 事先给了 prompt 说明要 cover 的部分；很常规——一半时间 present，一半时间回答提问

### 5. Onsite Culture
- 都是站内面经里出现过的问题
- 楼主感受：他们希望看到 **critical thinking、诚实、有自己的价值观和坚持、但不固执、能听劝、知错就改** 的人；讲的故事最好能体现这种态度

### 6. Onsite Hiring Manager
- 常规 BQ 题，还留了时间让楼主问组里的情况

## 有价值的回帖

- 匿名用户-OEQOF：恭喜，问楼主几年 YOE 面 senior → 楼主：4 年多
- 匿名用户-HYH9D：问 reference 什么时候提供的 → 楼主：onsite 之前就提供了，recruiter 说能加快后续进度
- 匿名用户-PXLCW：已加米；追问 LRU cache 生成 key 时复杂数据类型（set/dict）怎么处理 → 楼主：可假设给定 type 均可序列化，题目给了 serialize 用法

## 备考要点

- **OA**：bank system 这类题疑似题库固定，提前准备、目标满分
- **Recruiter call**：准备 why anthropic + 对 AI safety 的看法（使命认同是 Anthropic 的必考项）
- **Coding**：pillow 图像处理实操；multiprocessing vs multithreading 的 tradeoff 要能讲清（GIL、进程开销、worker 数量）；LRU + WAL crash recovery 组合题，重点练"按行分隔 log"的落盘细节，Python 文件 IO 的 delimiter 处理
- **System design**：prompt playground 是 Anthropic 高频题——schema 之后必有 large prompt / share / 增量编辑存储三连追问，提前准备 delta 存储 + object storage vs database 的 tradeoff
- **Culture**：准备体现 critical thinking、诚实、知错就改的故事；态度上"有坚持但不固执、能听劝"
- **流程**：pool hire 起步也可能转 match；reference 材料可提前准备，onsite 前提交能加速
