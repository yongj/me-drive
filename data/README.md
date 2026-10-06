# 公司库数据（上游数据源）

本目录存放**公司层**的基础数据：公司名单 + 招聘 ATS（Applicant Tracking System）状态。
**不含任何职位信息**——职位抓取数据另行存放，不进本仓库。

## l1_company_library.csv

- 快照日期：2026-10-07（随 Round 3 进展持续更新）
- 内容：L1 科技层 500 家公司
- 列：company（公司名）, ticker（上市代码）, domain（官网域名）, ats_platform（招聘系统，如 workday/greenhouse/lever）, ats_token（抓取用标识，如 Workday 的 tenant/site、Greenhouse 的 board slug）, method（ATS 确认方式）, note（证据/备注）

### ATS 分布（2026-10-07 快照，261/500 已确认）

| 平台 | 公司数 |
|---|---|
| workday | 113 |
| greenhouse | 67 |
| lever | 16 |
| custom（自建站） | 15 |
| smartrecruiters | 12 |
| jobvite | 10 |
| icims | 7 |
| workable | 4 |
| phenom / eightfold | 各 3 |
| taleo / oracle / adp / ashby | 各 2 |
| successfactors / kandidatenportal / dayforce | 各 1 |

### 名单构成

500 家 = 153 家指数成分（S&P 500 / Nasdaq-100 / S&P MidCap 400 筛科技）+ 347 家人工补足（大型软件、半导体设备/EDA、IT 分销商、日韩欧台区域龙头）。偏大、偏美、偏上市，非严格随机抽样。

### 方法

三轮 ATS 发现：Round 1 官网 careers 页静态扫描 → Round 2 搜索引擎（Workday 优先）→ Round 3 搜索指纹 + 浏览器反查。Workday 租户已验证 CXS JSON API 可直接抓取（68 家 tenant/site 已确认）。

### 用途

支撑"自抓职位数据的 AI 人才需求分析"：按 ATS 平台分别抓取各公司在招职位，再与 LinkedIn/Indeed 等聚合站数据做"官网独有岗位差集"对比（见 `misc/wall-street-ai-talent-demand-2026-draup.md` 后续分析想法）。
