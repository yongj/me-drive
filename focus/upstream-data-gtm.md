# 上游数据的商业化：客户触达（Go-to-Market）

*2026-10-02 整理；2026-10-09 增补 B-11（联邦部委新闻室，DHS 样本）、B-12（国会委员会新闻室，中国问题特别委员会样本）。来源：与用户的讨论（招聘数据 GTM 分析，2026-10-02）+ `ai-value-creation.md` 的上游数据源清单。用途：判断每类上游数据"卖给谁、卖什么形态、怎么触达到人"。*

> 定位：这是 [ai-value-creation.md](ai-value-creation.md) 的下游——那篇讲"取水烧水"的方法论，这篇讲"水烧开了卖给谁"。

## 总原则（所有上游数据通用）

1. **需求验证先行，先卖再做**：10 封 cold email / 一篇内容帖 + waitlist，拿到 2 个付费信号再投入抓取 pipeline。数据能力是入场券，付费意愿才是生意。（2026-10-02 讨论）
2. **卖工作流，不卖数据**：数据本身是商品，值钱的是它替客户做的那个决策——销售是"这周打哪 50 家"，猎头是"哪个客户在扩招"，律师是"哪个案源刚出现"。
3. **好客户三条件**：谁疼（痛点够痛）、谁有钱（有预算）、谁找得到（触达路径短）。求职者疼但没钱；投资人有钱但触达难、周期长。
4. **可持续 = 订阅**：一次性名单不复购；每周更新的雷达/提醒才有续费。AI Agent 的 moat 恰好是低成本维持新鲜度——人工维护几千个源是成本，agent 跑边际成本接近零。
5. **合规边界**：Workday 类站点反爬严、PACER 按页收费、法院/医疗数据有使用限制；节奏控制在"像人"，规模化前先读 ToS。

## A. 招聘数据（已验证场景）

*来源：2026-10-02 试点抓取（`~/workspace/upstream-samples/jobs_pilot.csv`，6 家公司、4013 个近三个月职位）+ 与用户的讨论。*

**客户排序（按付费意愿）**：

1. **卖 AI infra / 开发工具的销售团队**——"某公司 30 天内发了 5 个 MLE 的 JD"就是购买信号，能直接塞进 prospecting 流程；这类团队已在为 Apollo、ZoomInfo 付 $100+/人/月（公开定价），预算存在。触达：LinkedIn 找销售负责人 cold outreach。MVP：一份 CSV（300 家近 30 天在招 AI 岗的公司 + 职位 + 地点 + 薪资），定价 $500 发 10 人，2 人付费即验证成立。
2. **猎头 / 招聘机构**——"谁在招人"是刚需；触达：1point3acres、LinkedIn 猎头群，路径短。MVP：每周"AI 岗新增/消失雷达"订阅，几百刀/月。
3. **投资人**——招聘增速是正经 alternative data（公开案例：SignalFire 靠另类数据起家），但销售周期长、对数据质量要求高，不做 wedge，往后放。
4. **求职者**——注意力高（[thread-1178971](../threads/thread-1178971-ats-job-scraping.md) 系列 2.4w 浏览证明了流量），但付费意愿全网最低：焦虑高、预算低、找到工作就流失。做免费内容换流量，不做主力变现。

**试点数据里现成的验证素材**：Accenture 近三个月 48 个 AI 相关岗（"AI Engineer / Agentic AI Engineer"、"Forward Deployed AI Engineer"），"AI Engineer" title 反而是咨询公司用得最成体系、Amazon 几乎不用；Wolters Kluwer 版面 442 个职位里 184 个是 30 天以上老帖。

**已验证案例：jobuzzer.com（[thread-1178300](../threads/thread-1178300-jobuzzer.md)，2026-05-28，1.7w 浏览 / 316 收藏）**：独立开发者高频监控 7k→9k 家公司官网招聘页，"比 LinkedIn 更早看到职位"，免费搜索 + 付费邮件通知。验证了三点：①"卖 workflow 不卖数据"——用户买的是"更早知道"+被动通知；②求职者获客成立、付费天花板低——作者自述"收入还未能够支持开支"，与本节第 4 条排序一致；③成本纪律决定生死——工程化 diff 先行、有增量才用 AI 分类，数据源按 ATS API → 渲染浏览器 → LLM 三级走，成本递增。

**Incumbent 案例：Draup（2026-10-06 收录，见 [misc/wall-street-ai-talent-demand-2026-draup.md](../misc/wall-street-ai-talent-demand-2026-draup.md)）**：企业招聘数据公司，抓取 LinkedIn 等平台公开招聘信息，卖人才分析（talent intelligence）——2026-10 独家给 CNBC 提供了华尔街 AI 人才数据（银行 AI 职位 +49%、Agent 编排 +1721%）。这是"招聘上游数据 → B2B 订阅/报告"形态已经跑通的玩家：客户是企业 HR/战略部门而非求职者，客单价和续费逻辑与求职者端完全不同。做同类方向时，Draup 是要正面研究的对标。

**已验证案例：JobRadar（[thread-1190421](../threads/thread-1190421-jobradar.md)，2026-10）**：独立开发者做的免费求职工具，盯数千家公司官网招聘页、每周抓 3.5 万+新职位，1 分钟内推送通知（"经常比求职平台早上一截"），另有 Chrome 插件自动填表 + 简历-JD 匹配度分析。验证了两点：①"头两天投的简历才会被看"是求职者侧最痛的点，"更早知道"本身就是可传播的钩子；②与 jobuzzer 同赛道、仍在免费 Beta，再次确认求职者端适合做流量入口、不做主力变现——两个独立开发者不约而同选了同一形态，说明"监控官网 ATS + 通知"这个 workflow 方向已被重复验证。

## B. 上游数据源清单 × 客户触达矩阵

*逐类格式：信号 → 谁付费 → 卖什么形态 → 怎么触达 → 最小验证实验。数据源出自 [ai-value-creation.md](ai-value-creation.md) 的"上游数据源清单"。*

### 1. 移民 / 劳工（USCIS H-1B Employer Data Hub、DOL PERM/LCA）

- **信号**："谁在给外国人办身份 + 开什么工资"。LCA 披露 title / 工资 / 地点 / 雇主，是**带雇主名的全量薪资数据**（✅ 2026-10-01 已拉取验证：PERM FY2026Q3 全量 925,430 条）。
- **谁付费**：①移民律师事务所（"这家公司上季度 file 了 50 个 LCA，需要移民律师"＝案源）；②专做 H-1B 候选人安置的猎头；③HR / comp 咨询（LCA 工资基准）。求职者本人焦虑高但预算低。
- **卖什么**："Sponsor 雷达"订阅（求职者端 freemium 换流量）；LCA 工资基准报告 / API（B2B）。
- **触达**：1point3acres 发帖（受众极度精准）、律师名录 cold email、HR 科技展会。
- **验证**：一篇"H-1B sponsor 公司 50 强"分析帖 + waitlist；给 10 家移民律师发"上季度 LCA 激增公司"样品名单。
- **现有渠道 / 成熟度 / 缝隙**：USCIS/DOL 官方库免费；求职者端有 RedBus2US 等免费信息站；律所有 AILA 资源与 INSZoom 类案件系统。成熟度中高。缝隙：三源融合（sponsor 名单 × 在招职位 × LCA 工资）的一站式产品少；小律所 / 独立猎头买不起定制数据。

### 2. SEC EDGAR（Form D、13F、内幕交易）

- **信号**：Form D＝"谁刚拿到私募钱"（有钱＝有预算＝要招人＝要买工具）；13F / 内幕交易信号拥挤（WhaleWisdom 等已做，不碰）。
- **谁付费**：①B2B 销售团队（刚融资的 startup 是最佳 cold outreach 时机）；②VC 分析师（deal sourcing）；③猎头（funded startups 扩招）。
- **卖什么**："本周新融资公司雷达"（公司 + 金额 + 投资人 + 招聘页链接），周更订阅。
- **触达**：同招聘数据的 cold outreach（销售负责人）；VC 分析师在 Twitter / LinkedIn。
- **验证**：Form D 扫描已在跑（2026-09-28～30 扫出 881 条 D/D-A，见 `~/workspace/upstream-samples/`）；包 50 家"本周刚融资的 AI 公司"发 10 封邮件。
- **现有渠道 / 成熟度 / 缝隙**：VC 端 CB Insights、Harmonic.ai、PitchBook（成熟）；B2B 销售端的融资 trigger 已是 Apollo / ZoomInfo 标配功能。成熟度高。缝隙：垂直切法（AI 公司 × 融资 × 招聘三源融合评分）；买不起大平台的长尾销售团队。

### 3. 许可 / 执照库（职业执照、FCC/FAA、ESMA/MiFID、FCA、烟草许可证）

- **信号**："谁刚拿到执照开始营业"＝B2B 获客信号（[thread-1186353](../threads/thread-1186353-upstream-info-job-hunting.md) 的万能钥匙：需许可的事必有公开名单）。
- **谁付费**：①卖给持牌人的供应商（牙科设备商、诊所 SaaS、保险经纪、POS 系统商、分销商）；②商业地产（选址）；③合规咨询、猎头。
- **卖什么**："本月新发执照"名单 + 提醒（按地理 / 执照类型切片）。
- **触达**：行业供应商的销售负责人（LinkedIn）、行业协会。
- **验证**：以 thread-1186353 的烟草许可证库为例，包"某市本月新发烟草零售许可证"名单发给 10 家 POS / 分销商。
- **现有渠道 / 成熟度 / 缝隙**：Data Axle / ReferenceUSA 等通用 mailing list 数据商；各州官方库免费。通用名单成熟度中高，高频"新发执照提醒"成熟度低。缝隙：按地理 / 行业切片的高频新执照提醒；niche 行业包。

### 4. 医药 / 健康（openFDA、ClinicalTrials.gov、CMS / NPI）

- **信号**：NPI＝全美医疗从业者名录；openFDA 不良事件激增＝诉讼 / 产品信号；ClinicalTrials＝试验点 / 患者招募信号。
- **谁付费**：①医疗器械 / 药企销售（NPI 名单是经典获客数据）；②mass tort 律师（不良事件激增＝案源，付费意愿极强）；③CRO / 患者招募公司。
- **卖什么**：按专科 / 地理切片的从业者名单；不良事件监控提醒。
- **触达**：医疗器械公司销售 VP、mass tort 律所（公开名录）。
- **验证**：往后放（领域专业度要求高）。
- **现有渠道 / 成熟度 / 缝隙**：IQVIA（巨头，NPI 数据是其业务一部分）；mass tort 有成熟 lead-gen 公司。成熟度高。缝隙：买不起 IQVIA 的小律所 / 独立医疗器械销售；轻量不良事件监控提醒。

### 5. 钱的流向（USASpending / SAM.gov、FEC）

- **信号**："谁刚拿到政府合同"；"谁给谁捐了钱"。
- **谁付费**：①GovCon contractor（找分包 / 组队机会——GovWin、Bloomberg Government 收高价年费，说明预算存在）；②卖给政府的供应商；③政治咨询 / 筹款人（FEC 捐款人＝捐款 prospect）。
- **卖什么**：合同中标提醒（按 NAICS / 机构切片）、捐款人名单。
- **触达**：GovCon 行业协会 / 展会、contractor 的 BD 负责人。
- **验证**：往后放（美国本土网络要求高）。
- **现有渠道 / 成熟度 / 缝隙**：GovWin（Deltek，govwin.com）、Bloomberg Government，又贵又深，护城河是关系＋历史数据。成熟度极高。缝隙：被高价挡住的小 contractor（轻量低价版）；特定 NAICS 切片提醒。

### 6. 法规 / 立法 / 游说（Federal Register、LDA、FARA、Congress.gov）

- **信号**："谁在为什么议题雇游说公司"（LDA）；"什么法规要变"（Federal Register）。
- **谁付费**：①游说公司（竞争情报）；②行业协会（监管风险监控）；③记者、智库（FARA 外国代理人）。
- **卖什么**：议题监控提醒（"你的竞争对手刚雇了 X 游说公司谈 Y 议题"）。
- **触达**：游说公司合伙人、协会政策负责人。
- **验证**：往后放（客户高度集中在 DC，小众）。
- **现有渠道 / 成熟度 / 缝隙**：Bloomberg Gov、Quorum、FiscalNote（法规追踪 SaaS，成熟）。成熟度高。缝隙：小众议题、非 DC 客户。

### 7. 法院（CourtListener / RECAP、PACER）

- **信号**："谁刚被诉"（原告律师的案源；被告公司的风险）；"这个法官怎么判"（judge analytics——Lex Machina 卖企业价，说明有人买单）。
- **谁付费**：①诉讼律师（案源＋法官画像）；②诉讼资助机构；③企业法务（监控自己被诉）。
- **卖什么**：新诉讼提醒（按行业 / 法院切片）、法官画像报告。
- **触达**：律所合伙人（公开名录）。
- **验证**：往后放（PACER 按页收费，成本先行）。
- **现有渠道 / 成熟度 / 缝隙**：Lex Machina（LexisNexis 旗下）、Westlaw Edge。成熟度高。缝隙：买不起 Lex Machina 的小律所；特定法院 / 案由的轻量监控。

### 8. 专利 / 商标（USPTO、EUIPO、EPO）

- **信号**：商标注册通常早于产品发布 6–18 个月（[thread-1186353](../threads/thread-1186353-upstream-info-job-hunting.md)）＝产品先行指标。
- **谁付费**：①品牌保护 / 知产律所；②竞品情报团队；③域名投资人；④VC（赛道扫描）。
- **卖什么**："本周新注册商标监控"（按关键词 / 类别）、竞品商标动态。
- **触达**：知产律所、品牌 agency。
- **验证**：往后放。
- **现有渠道 / 成熟度 / 缝隙**：Derwent、IFI CLAIMS；品牌保护公司 Corsearch、MarkMonitor。成熟度高。缝隙：给中小品牌方的轻量竞品商标监控。

### 9. 房地产（county assessor / parcel、NYC ACRIS）

- **信号**：房主、估值、交易记录。"absentee owner 名单"是美国房地产批发最经典的付费名单生意——PropStream、BatchLeads 收约 $100/月（公开定价），模式已被验证，是清单里商业化最成熟的一类。
- **谁付费**：①房产投资人 / wholesaler；②地产经纪；③贷款经纪、保险。
- **卖什么**：按条件切片的业主名单（欠税、空置、absentee）＋周更。
- **触达**：REIA 线下投资人聚会、投资者 Facebook 群组、YouTube。
- **验证**：可直接对标 PropStream 定价做竞品分析。
- **现有渠道 / 成熟度 / 缝隙**：PropStream、BatchLeads、Privy，红海中的红海。成熟度极高。缝隙：通用名单几乎没有；只剩超细分地理或特定策略名单。

### 10. 统计（Census、BLS、BEA）

- **信号**：人口 / 就业 / 经济宏观数据——通常做原材料，不直接卖。
- **谁付费**：零售选址、市政咨询、pitch deck 市场规模测算（打包进咨询报告）。
- **结论**：单独难成产品，适合作为其他产品的增强层。

### 11. 联邦部委新闻室（agency press rooms；样本：DHS，2026-10-09 收录）

- **信号**："官方政策事件流"——新规提案公告、收费标准、公众意见征询期起止、执法行动、拨款机会。部委官网首发，比媒体快半天到一天，带精确日期和原文链接。实例：DHS 2026-10-07 首发 OPT $70k 收费提案（公众意见期 10/8–11/9），路透社当日跟进报道。
- **谁付费**：①移民律所（政策变化＝案源＋客户咨询）；②行业协会 / 企业合规（监管风险监控）；③记者、智库；④GovCon contractor（拨款机会）。
- **卖什么**："政策事件雷达"订阅——结构化抽提案名称 / 金额 / 征询期 / 生效日期 / 原文链接，按主题推送。
- **触达**：律所合伙人（公开名录）、协会政策负责人、记者。
- **验证**：往后放；或先做单主题 MVP（如"移民政策 30 天变化简报"）发 10 家律所。
- **现有渠道 / 成熟度 / 缝隙**：FederalRegister.gov 有 API（法规全文）；FiscalNote / Quorum / Bloomberg Gov（成熟，贵）。部委新闻室层面：无 RSS、无新闻室 API（2026-10-09 实测 dhs.gov/news，直抓 403），只有 GovDelivery 邮件/短信按主题订阅。成熟度低。缝隙：跨部委新闻室聚合＋结构化（DHS / USCIS / DOL / DOE…）；被高价挡住的长尾（小律所、独立顾问）。
- **抓取注意**：dhs.gov 有反爬（直抓 403），用 GovDelivery 订阅或低频爬 all-news-updates 列表页；内容偏 PR 口径，法律细节以 Federal Register 为准。

### 12. 国会委员会新闻室（样本：中国问题特别委员会，2026-10-09 收录）

- **信号**："政策前置信号"——质询信（letters）和调查报告（reports）经常比立法/制裁早几个月。实例：该委员会 2024-12 致函质询 Webull，2026-10-07 发布《Free Trades, Hidden Ties》报告，当天 BULL 股价跌 18–26%。盯 letters + reports 等于提前看到"下一个被盯上的公司"名单。
- **谁付费**：①投研 / 做空研究（事件驱动）；②企业合规与 GR（政府关系）团队；③律所（制裁/出口管制业务）；④记者。
- **卖什么**："委员会动向雷达"——新质询信、新报告、新听证会的即时提醒＋被点名公司/议题的结构化摘要。
- **触达**：对冲基金研究员、合规负责人（LinkedIn）、制裁业务律所。
- **验证**：往后放；或先做单委员会 MVP（每周"Select Committee on CCP 本周动向"简报）发 10 家目标机构。
- **现有渠道 / 成熟度 / 缝隙**：Congress.gov 有 API（法案/听证会元数据）；Bloomberg Gov、Quorum（成熟，贵）。委员会新闻室层面：有 RSS（chinaselectcommittee.house.gov/rss.xml，标准 RSS 2.0，含新闻稿/信函/报告），抓取门槛低；无 API、无 sitemap。成熟度低。缝隙：跨委员会聚合（拨款委员会、金融服务委员会、能源商务委员会等）＋被点名实体抽取；被高价挡住的长尾。
- **抓取注意**：RSS 可直接订阅；报告 PDF 托管在 Constant Contact（files.constantcontact.com），无本站稳定直链，存档需自抓；注意委员会换过域名（selectcommitteeonccp.house.gov → chinaselectcommittee.house.gov），硬编码域名会失效。
- **可泛化**：众议院各专门委员会网站多为同构（Drupal），有 press releases / letters / hearings 栏目和 RSS；B-11（部委新闻室）＋ B-12（国会委员会）可合并为"官方政策信号源"大类统一抓取。

## C. 通用验证实验模板

1. 选一个信号 ＋ 一个客户（必须同时满足疼 / 有钱 / 找得到）。
2. 用已有 pipeline 包 30–50 条真实样品（CSV / 一页 PDF）。
3. 写 10 封个性化 cold email（提到对方具体业务，不群发），或发一篇内容帖结尾留 waitlist。
4. 计数：回复率、愿意付费数。2/10 付费＝继续投入；0/10＝换客户或换信号。
5. 全程记录：样品来源、发送对象、回复原文——这是以后的 case bank。

## D. 风险与边界

- **先做 incumbent check（2026-10-02 讨论修正）**：只论证"有人付费"不够，还要论证"轮得到你"。数据公开＝无套利空间；拼同样的数据卖给同样的人是红海。缝隙只在三处：跨源融合信号、被定价挡住的长尾、垂直切法。

- 反爬与 ToS：Workday 类站点反爬严（试点已见），节奏控制在"像人"；规模化前先读 ToS。
- 数据商品化："抓一次"谁都会，壁垒只在持续更新＋切到客户工作流里。
- 持牌 / 注册实体 ≠ 运营实体：大集团持牌的可能是空壳，名单要配实体校验（[ai-value-creation.md](ai-value-creation.md) 边界）。
- 抽样框黑箱：凡是 Top 榜单类产品，必须披露名单来源构成（[thread-1178971](../threads/thread-1178971-ats-job-scraping.md) 教训）。

## 相关

- [ai-value-creation.md](ai-value-creation.md)——上游数据方法论与数据源清单（本篇的上游）。
- [thread-1178971-ats-job-scraping.md](../threads/thread-1178971-ats-job-scraping.md)——ATS 招聘数据案例（2.4w 浏览的注意力验证）。
- [thread-1186353-upstream-info-job-hunting.md](../threads/thread-1186353-upstream-info-job-hunting.md)——种子帖：万能钥匙与五步流程。
- 小样本试点数据：`~/workspace/upstream-samples/jobs_pilot.csv`（4013 个近三个月职位，2026-10-02）。

## E. 需求 / 项目发布平台清单（2026-10-02 整理，链接 2026-10-11 复核）

说明：客户主动发布需求 / RFP / 项目的平台。价格信息来自 2026-10-02 公开网页搜索的第三方对比文章（rfphawk.com、cleat.ai、sourceforge 等），非官网实时报价，仅供参考。官网链接 2026-10-11 逐一复核：全部改为标准 Markdown 链接格式（之前裸 URL 套全角括号在 GitHub 上点不开）；两个已下线平台已标注。

### 政府采购 / RFP 平台

- [SAM.gov](https://sam.gov)——美国联邦官方招标站，免费，基准线。
- [GovWin IQ](https://www.govwin.com) / Deltek——联邦＋州地方＋预测，企业级，五位数/年。
- [Bloomberg Government](https://about.bgov.com)——政策＋采购，约 $6,000+/年/席位。
- [BidNet Direct](https://www.bidnetdirect.com)——州/地方政府招标聚合，约 $1,000–2,000/年。
- [GovTribe](https://govtribe.com)——联邦＋部分州地方，约 $2,000–3,000/年。
- [RFPHawk](https://www.rfphawk.com)——免费档＋Pro $20/月。
- [GovBidWire](https://www.govbidwire.com)——免费档，付费 $39–149/月，带 AI 标书分析。
- [HigherGov](https://www.highergov.com)——Starter $500/年起。
- 免费数据源：[USASpending.gov](https://www.usaspending.gov)（历史中标）、[Grants.gov](https://www.grants.gov)（联邦 grants）、[GSA eBuy](https://www.ebuy.gsa.gov)。
- 国际：[TED](https://ted.europa.eu)（欧盟）、[MERX](https://www.merx.com)（加拿大）、[Contracts Finder](https://www.contractsfinder.service.gov.uk)（英国）。

### 自由职业 / 项目外包平台

- [Upwork](https://www.upwork.com)——量最大，抽成 5–20% 阶梯。
- [Fiverr](https://www.fiverr.com)——gig 模式，抽 20%。
- [Toptal](https://www.toptal.com)——只收前 3%，高端路线。
- [Freelancer.com](https://www.freelancer.com)——竞标制，项目量极大。
- [Guru](https://www.guru.com)、[PeoplePerHour](https://www.peopleperhour.com)、[Contra](https://contra.com)。
- 开发者垂直：[Gun.io](https://www.gun.io)、[Lemon.io](https://lemon.io)（审核制，$60–200/小时）。

### 国内平台

- [猪八戒网](https://zbj.com)——量最大，抽成高、需保证金。
- [程序员客栈](https://www.proginn.com)——程序员/产品/设计垂直。
- 开源众包（zb.oschina.net，开源中国旗下）——**已下线**，网站已无法访问。
- CODING 码市（mart.coding.net，软件外包）——**已下线**；腾讯 CODING DevOps 系列产品自 2025-09 起陆续停服。
- [开发邦](https://www.kaifabang.com)、[猿急送](https://www.yuanjisong.com)。

观察（2026-10-02）：GovCon 已出现"便宜版 GovWin"（RFPHawk $20/月、GovBidWire $39/月，对标 GovWin 五位数/年），印证 D 部分"被定价挡住的长尾"缝隙真实存在。

## F. 三平台需求抽样观察（2026-10-02）

方法：只读浏览各平台公开最新发布列表 10–25 条，未登录。来源：SAM.gov 合同机会搜索页、Upwork 公开职位搜索页、猪八戒网任务大厅。

- **SAM.gov**：Top 类别为设施/后勤服务、建筑与工程、IT 与设备采购、咨询与专业服务、医疗/健康服务；最大发布方为 VA、DoD、GSA、农业部林务局。Solicitation 不披露预算（只列合同类型与截止日期），金额只在 Award Notice 中标公示中出现。描述为高度格式化的法律文书（PSC 分类码＋FAR 条款＋附件 SOW）。注意"Sources Sought"/"RFI"仅征集信息，非正式招标。
- **Upwork**：Top 类别为营销与销售、法律服务、设计/摄影、行政调研、音频/音乐。约七成时薪制（$15–35 至 $100–150/小时）；固定价 $300 至 $52,000 跨度大，中低预算占绝大多数。描述最长最规范（300–600 词结构化 SOW＋交付物清单＋筛选问题），客户历史花费透明。警惕混入的"纯佣金无底薪"销售岗。
- **猪八戒网**：Top 类别为设计类、开发类（小程序/网站/AI 智能体）、视频/拍摄、营销推广、企业服务。多数"待服务商报价"无明确预算；有预算的多为几百至几千元。描述极简，多为一句话甚至只有标题，交易靠后续私聊补细节；页面混杂服务商广告位。

一句话对比：SAM.gov 是法律文书式政府采购（无预算、重附件），Upwork 是详细 SOW 式中长单（预算透明、描述最长），猪八戒是标题式小额快单（多无预算、描述最短）。

GTM 含义：Upwork 的公开职位本身就是需求信号源（发布 $5K+ 项目的公司＝明确购买意向），可纳入"销售信号"数据源；SAM.gov 的 solicitation 无预算字段，做信号需配 Award Notice；猪八戒需求过于简略，结构化提取价值低。
