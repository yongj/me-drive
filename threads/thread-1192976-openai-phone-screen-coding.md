---
thread_id: 1192976
url: https://www.1point3acres.com/home/thread/1192976
title: openai店面coding
company: OpenAI
role: SWE（码农类 General）
posted: 2026-10-14
result: Other（进行中/未知）
collected: 2026-10-15
tags: [OpenAI, phone screen, coding, kvstore, chunking, disk]
---

# openai店面coding

- 原贴：https://www.1point3acres.com/home/thread/1192976（海外面经版，作者匿名用户-OREXC，发帖 2026-10-14 10:02；7 回复）
- 楼主档案：硕士；在职跳槽；社招；找工季 2026 年 10–12 月
- 职位：码农类 General；技术电面；全职 @openai
- 结果：Other（未知/进行中）；体验 Positive；难度 Hard
- **注意：正文被 188 大米 paywall，以下为页面可见部分 + 回帖拼凑**

## 题目（据可见片段与回帖还原）

**kvstore 设计/实现题**：k,v 对应关系涉及按 byte 的 length（可见片段："k,v … 对应 … length … byte"）。

**第二部分**：按固定 size 把数据切成 chunk 后存到 disk；拼装读取时的问题——是把全部 chunk 合并后再解决（resolve），还是 per-chunk 逐个解决？楼主在回帖中明确回复：**先拼装再解决**。

## 有价值的回帖

- 匿名用户-NTJWE：追问第二部分——按 size chunk 存盘后，"拼装时是把全部 chunk 合并再解决，还是 per-chunk 解决？" → 楼主（OREXC）回复"先拼装再解决"。
- 匿名用户-O60GH / 楼主：讨论 bytes 转换的 helper function（细节不可见）。
- 匿名用户-GELFI：问 OpenAI 现在店面 coding 是否还带 SD（system design）环节（问题可见，无明确答复）。
- 其余为加米/恭喜（shshrosh、weibest、RGDVG、XAKT5）。

## 备注

- 完整题面在 paywall 后；如后续有人补充细节，可再补全。本帖主要价值是记录 OpenAI 店面仍在考 kvstore + chunk/disk 这类存储向 coding 题。
