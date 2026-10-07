# 公司库数据（上游数据源）

本目录存放**公司层**的基础数据：公司名单 + 招聘 ATS（Applicant Tracking System）状态。
**不含任何职位信息**——职位抓取数据另行存放，不进本仓库。

## l1_company_library.csv

- 快照日期：2026-10-07
- 内容：L1 科技层 494 家公司（500 家名单去重 6 家：Arista/Cadence/Ceridian/Guidewire/II-VI/Juniper 均为重复条目）
- 列：company（公司名）, ticker（上市代码）, domain（官网域名）, ats_platform（招聘系统，如 workday/greenhouse/lever）, ats_token（抓取用标识，如 Workday 的 tenant/site、Greenhouse 的 board slug）, method（ATS 确认方式）, note（证据/备注）

### ATS 分布（2026-10-07 快照，454/494 已确认，92%）

| 平台 | 公司数 |
|---|---|
| workday | 142 |
| greenhouse | 82 |
| custom（自建站） | 48 |
| successfactors | 22 |
| smartrecruiters | 20 |
| icims | 18 |
| oracle | 17 |
| lever | 16 |
| jobvite | 12 |
| phenom | 10 |
| eightfold | 10 |
| adp / ashby | 各 7 |
| taleo / ukg / avature / workable | 各 5 |
| comeet | 3 |
| dayforce / paylocity | 各 2 |
| 其他（jazzhr、rippling、teamtailor、pageup 等） | 各 1 |

### 名单构成

494 家 = 153 家指数成分（S&P 500 / Nasdaq-100 / S&P MidCap 400 筛科技）+ 347 家人工补足（大型软件、半导体设备/EDA、IT 分销商、日韩欧台区域龙头），去重 6 家。偏大、偏美、偏上市，非严格随机抽样。

### 方法

三轮 ATS 发现：Round 1 官网 careers 页静态扫描 → Round 2 搜索引擎（Workday 优先）→ Round 3 搜索指纹 + curl/搜索直查。Workday 租户 CXS JSON API 可直接抓取（125 个站点已确认，68 家经 POST /jobs 验证）。

### 用途

支撑"自抓职位数据的 AI 人才需求分析"：按 ATS 平台分别抓取各公司在招职位，再与 LinkedIn/Indeed 等聚合站数据做"官网独有岗位差集"对比（见 `misc/wall-street-ai-talent-demand-2026-draup.md` 后续分析想法）。

## l2_company_library.csv

- 快照日期：2026-10-07
- 内容：L2 金融层 410 家公司（银行、保险、资管、交易所等，49 个国家/地区）
- 列：company（公司名）, ticker（上市代码）, domain（官网域名）, ats_platform（招聘系统）, ats_token（抓取标识）, careers_url（招聘页 URL）, note（证据/备注）

### ATS 分布（2026-10-07 快照，288/410 已确认，70%）

| 平台 | 公司数 |
|---|---|
| custom（自建站） | 125 |
| workday | 61 |
| phenom | 25 |
| greenhouse | 19 |
| icims | 11 |
| taleo | 9 |
| oracle / successfactors | 各 7 |
| eightfold | 4 |
| jobvite / lever | 各 3 |
| ashby | 2 |
| 其他 | 各 1 |

### 验证情况

L1+L2 共 239 家公司经接口实测拉到过真实职位数据（Workday CXS、Greenhouse Boards API、Lever、Ashby、SmartRecruiters 公开接口）。
