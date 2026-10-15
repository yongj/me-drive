# 用 AI 创造价值：应用场景与方法论

*不收面试内容。这个 focus 收"怎么用 AI + 被忽视的数据创造价值和商业机会"——应用场景探索。种子帖：thread 1186353。*

> 范围说明：只收 AI 的**应用场景和价值创造方法**——AI 在流程里的正确分工、被忽视的数据资产、已见的商业机会形态。**不收**"AI Engineer 职位考什么"（[ai-engineer.md](ai-engineer.md)）、**不收**"面试中怎么考核 AI coding"（[ai-coding-in-interviews.md](ai-coding-in-interviews.md)）。

## 核心洞察：AI 抹平的是下游信息

AI 出现后信息差没有消失，反而在某些维度变大——因为 AI 抹平的只是"下游信息"（已被写成文章、帖子、榜单的东西）的获取成本。一万个人问 AI 同一个问题，得到一万份几乎相同的二手答案，然后去竞争同一批机会。

真正的价值洼地在**上游**：躺在监管机构数据库里、以 CSV/XML/公示形式存在、没人做 SEO、AI 训练时未必啃过的结构化公开数据。政府维护、免费、几乎零噪音、法律上必须准确。（thread 1186353）

## AI 的正确分工：烧水不取水

大部分人用错了 AI，把它当成取水的人，其实它是烧水的人。

❌ 错误用法："阿姆斯特丹有哪些量化公司？"→ 二手、过时、可能带幻觉的下游榜单，和所有人一样。
✅ 正确用法（AI 真正擅长的四件事）：
1. **术语翻译**："在欧盟提供杠杆交易服务需要哪一类授权？对应法条是哪一条？"——把白话翻译成官方术语
2. **规则解释**："帮我读懂 MiFID II Annex I Section B(2) 的适用范围"——法条/文档解读
3. **结构化数据处理**："这是我下载的 CSV，帮我按城市分组、去掉已注销的、按授权项打标签"
4. **批量个性化**："根据这家公司的业务描述，帮我写一封提到他们具体产品线的冷邮件"

> AI 不负责替你取水，AI 负责替你把水烧开。取水这件事，你必须自己走到上游去。

## 通用方法：上游数据方法论

本质是"发现被忽视的数据资产"的方法，可迁移到任何受监管/需许可的领域：

**万能钥匙**：凡是需要许可才能做的事，世界上必然存在一份公开的"谁被允许做这件事"的名单。

**五步流程**：
1. **名词转动词**：不问"有哪些量化公司"，问"谁被批准做自营交易"
2. **找到管这个动词的机关**：金融→证券监管机构；招人→移民局；卖烟→烟草专卖局；卖药→药监
3. **找它的公示库**：`site:.gov.uk "register of" [牌照名]` / `site:europa.eu "public register" [牌照名]` / `"行政许可" "公示" [许可证名]` / `open data / 数据开放 [许可证名]`
4. **三维切片**：地理 + 权限 + 状态
5. **落地到人/行动**：实体名 → 官网 → 关键人 → 个性化触达

**已验证的上游库示例**（thread 1186353 第六节全表）：
- 欧洲金融：ESMA Registers → 各国 NCA（BaFin/AFM/FCA…），按 MiFID II 授权项精确检索
- 中国烟草零售：《烟草专卖零售许可证》库 + 地方数据开放平台（行政区划代码 + 发证日期 + 是否注销 → 密度/趋势/空白点/准入难度）
- 公司尽调：Companies House / Handelsregister / KVK / BRIS
- 资金信号：TED（欧盟公共采购）、CORDIS/ERC（科研经费）、SEC EDGAR Form D（美国私募融资）
- 产品先行指标：EUIPO 商标库、EPO Espacenet 专利库（商标注册通常早于产品发布 6–18 个月）

**美国 tech 求职的迁移**：H-1B sponsor 名单（USCIS 数据）、PERM filing 数据——精确筛出"有担保资格 + 真在招人"的公司，替代 LinkedIn 盲投。

## 案例：ATS 招聘数据的上游抓取与价值提炼

第二类上游：**平台侧结构化公开数据**。不靠政府强制公示，靠的是招聘 ATS（Applicant Tracking System）系统的公开职位页——公司为了招人必须把 JD 放在网上，Greenhouse / Lever / Ashby 有公开 boards API，职位天然结构化（title、地点、JD 文本），是"为了招人而被迫公开"的上游。

**案例**（thread 1178971 系列，作者"凤眼流盼的草稿本"，SE / DE / AIE / MLE 四组数据）：

- **取水**：绕开 LinkedIn / Indeed / Glassdoor 聚合站，直接抓 4,000+ 家公司招聘页（自述口径；评论里另有 2 万家 / 100 万职位的说法，口径打架，4000+ 更可信）。技术门槛排序：Greenhouse / Lever / Ashby 有公开 API 好抓，Workday 要 JS 渲染 + 反爬严，是真正的门槛。
- **烧水**：title 关键词过滤 → JD 文本挖技能关键词出现率 → 按 JD 年限要求推断 level → 按公司汇总。产出四层洞察：薪资分层（AIE median $150K / MLE $162K / SE $135K）、技能栈分野（AIE=LangChain+AWS+Docker 工程落地型 vs MLE=PyTorch+TF+MLOps 训模型型）、雇主榜（金融/咨询是隐藏大雇主：Capital One、PwC）、remote 逻辑分化（AIE remote 倒挂 vs MLE remote 溢价）。
- **呈现/分发**：论坛系列帖 + 计划中的免费查询网站。"免费数据 + 处理 + 呈现"本身就是下面"已见的商业机会形态"之一。

**这个案例给方法论补的三块**：

1. 上游不只有"政府牌照名单"，还有"平台被迫公开的结构化数据"——判断标准是：**数据生产者是否有动机持续、准确地公开它**（公司要招人，JD 必须准；政府要监管，牌照库必须准）。
2. 烧水环节的标准化动作可复用：关键词出现率、按年限推断 level、分雇主/分 remote 切片——同一套 pipeline 可以跑 PM、Security、DevOps（作者排队中的下一篇）。
3. 反面教材：**抽样框黑箱**。4000 家公司名单未披露，Top 雇主榜无法排除名单偏差；且作者承认三个硬伤：一个 JD 默认一个坑（实际可能招多人）、level 推断依赖 JD 年限（80% SE 岗不写 seniority）、薪资 median 只覆盖写了薪资的 JD。取水时就要记录抽样框，否则烧出来的水没法验证。

## 案例：AI 数据标注小时工平台（打工者视角的上游人力市场）

训练数据不是天上掉下来的——是小时工生产的。thread 1192101（[[求比较] $ Opportunities 小时工，求比较！](https://www.1point3acres.com/home/thread/1192101)，zellsun，2026-10-07，职场达人版，1418 浏览 / 15 回复）是打工者视角的 AI 数据标注平台对比帖，正好补上"上游数据"的人力生产端。

**楼主列的 6 家平台**：dataannotation.tech、work.mercor.com、experts.afterquery.com、micro1.ai、surgehq.ai、jobs.lever.co/weloglobal。原帖基本只有链接列表（"有没有赚到的？哪家好一些？求比较！"），实质比较在回帖里也没展开——楼主 10-15 追问"有人上项目的吗"，无人回报实际入职体验。

**回帖里真正的信息**：

- **唯一具体的薪资数据点**：jing0020（加精）亲身做过 Surge 的 SWE Evaluation，时薪 $100+/小时，"还不错"。除此之外全帖没有任何一家平台的薪资/体验数据——这类市场的信息透明度极低。
- **合规与税务才是讨论焦点**，而非平台优劣：
  - 匿名（加精，3 赞）："有身份就能拿钱"，不与全职冲突（类比"白天 fulltime SDE、晚上当家教"），但"不报税可是大忌"。
  - 有名人士：别接和全职东家业务有 conflict of interest 的项目，其他没问题。
  - 匿名-ASGD0 / e7598020：追问 fulltime 会不会被发现、要不要报税、要不要向全职单位报批——楼主半开玩笑回"用你媳妇儿的身份🤓"。
- **"拿 AI 干活"**：匿名-MUTSC 建议多平台同时接，"反正都是拿 ai 干活"——用 AI 辅助生产 AI 训练数据，套娃闭环。
- **无答案的问题**：匿名-VNCWQ 问"会有可以拿钱又值得写简历的工作机会吗？"——无人正面回答，小时工的 resume 价值存疑。
- **准入门槛**：匿名-KBJGD 问面试流程；楼主：每个职位要求不同，他之前做的"只要 OA 过了就进去开工"。

**这个案例给 focus 补的一块**：上游数据方法论一直讲"数据从哪来"，这个帖子回答的是"谁在生产"——AI 训练数据供应链的人力层。Surge / Mercor / Data Annotation 这些平台本身就是上游数据供应商（vendor 侧）；打工者视角是同一市场的另一面：SWE eval 类高质量标注时薪 $100+/hr 说明是真金白银的市场，而信息不透明 + 税务合规风险才是入场前真正的门槛。跟 ATS 案例对照看：一个是"平台被迫公开的数据"，一个是"平台花钱购买的人力"，合起来才是上游数据的完整图景。

## 案例：AI 内容农场 tech-insider.org（流量套利型商业形态）

AI 商业机会光谱的**灰色端**：不生产一手信息，靠 AI 洗稿 + SEO/推荐流套利。2026-10-15 因一条 Intel GPU 新闻页（https://tech-insider.org/intel-gpu-d-series-crescent-island-2026/ ，2026-10-14 发布）顺藤摸瓜扒出的完整样本，核查日期均为 2026-10-15。

**站点画像**
- 自称"2024 年创办于瑞典斯德哥尔摩的独立科技媒体"，4 人编辑团队（主编 Sofia Lindström 等），4 种语言出版 —— 来源：https://tech-insider.org/about/ （发布 2026-03-10，更新 2026-10-11）
- WHOIS 显示域名注册于 **2013-10-03**，与"2024 年创办"自相矛盾 —— 买的老域名，吃历史权重（来源：ipaddress.com 的 WHOIS 记录）
- 4 个"记者"配 stock 风证件照（`ti-author-*.jpg`，2026/03 上传），履历（Dagens Industri、ZDNet、F-Secure……）全网查无此人 —— AI 人设包装高度可疑
- 内容节奏：一天数篇 12–22 分钟长文，标题统一 `[2026]` SEO 后缀；首页 6 篇全是 2026-10-14 当天

**生产模式：洗稿**
- 无一手采访。Intel GPU 一文的信源链：Tom's Hardware、Intel 官方 newsroom、StorageReview、Pulse2 的真实报道 → AI 抓取重写扩写，配对比表格 + 站内文章互链，引用格式做得像模像样
- 事实骨架是真的（OCP Summit 上 Intel 确实发布了 GPU D-Series），观点分析全是 AI 现编 —— **它是二道贩子，不是信源**
- **配图也是 AI 生成的**：每篇文章配一张题图，文件名统一为 `{slug}-gen.webp`（如 `north-wales-ai-data-center-protest-24k-signers-2026-gen.webp`，1344×768 webp，2026-10-15 核查）—— `gen` 即 generated，pipeline 里随文章一起自动生成，零版权风险；横构图正好适配 Google Discover 的大图卡片

**流量**（第三方估算，各工具口径打架严重，只看量级；来源 hypestat.com）
- 月访问：SimilarWeb 口径约 76 万（2026-08，环比 +207%），SEMrush 口径 479 万；此前两月 30 万 → 24 万 —— Discover 赏饭型暴涨暴跌
- 来源构成：Direct 72.09% / 搜索 25.97% / 社交 0.16% / 外链 1.79% / 付费 0；**95.05% 移动端** —— "直接访问"大头实为 Google Discover/News 信息流（统计常被归入 direct）；站内嵌"Add Tech Insider"推广模块，蹭 Google Preferred Sources 功能把推荐流转成半个私域
- 自然搜索：SEMrush 显示 1.7 万关键词进 Google 前 20（长文 + SEO 标题堆出来）
- 外链：91,219 条 / 6,223 引用域名；但 TLD 构成露馅：.xyz 499 个、.ai 277 个 —— 便宜垃圾域名站群刷链；Authority Score 48 / Ahrefs DR 62

**变现（三层）**
1. 展示广告 / affiliate：About 页披露使用 affiliate 链接；但**无 ads.txt**（实测 404）——没接 Google 大联盟，推测小广告网络 + affiliate
2. **卖外链**：在 guestpostnow.com 公开售卖 guest post，$10/篇、$15 插一条外链，卖点就是"DR 62 域名的 dofollow 链接"
3. 自吹"月 1500 万曝光、220+ 国家、10 个语言版本"（https://tech-insider.org/write-for-us/ ）——与 About 页"4 种语言"自相矛盾，注水明显

**成本清单**（2026-10 估算）
- 一次性：老域名 $100–500（二手市场）+ WordPress 主题 $0–60
- 按月：VPS $5–12 + Cloudflare $0（免费版，该站即用 Cloudflare）+ AI API（一天 5 篇长文：便宜模型 $10–50/月，好模型 $75–300/月）+ 配图/SEO 插件 $0
- 合计：启动 $100–600，月运营 $30–350，年 $500–2,000 封顶
- 对比收入估算（100 万月 PV × RPM $5–15 → $5K–15K/月）：首月可回本，毛利率 90%+ —— 这就是可批量复制的原因

**打法拆解（流量从哪来）**
1. 买老域名：继承历史权重（买的是过去攒下的链接和信任，不是年龄本身）
2. 刷外链：6 千+ 引用域把 DR 顶到 60+
3. 进 Google News/Discover：新闻站点入场券，95% 移动流量全靠推荐流
4. 高频 AI 长文：一天数篇，标题 SEO 化，覆盖尽可能多关键词
5. 蹭 Preferred Sources：站内弹窗求用户一键添加
6. 多语言铺量：同一内容多语言版本，流量乘数

**本案例带出的 SEO 原理**
- Google 把 `xxx.blogspot.com` 这类免费子域名当独立站点，**不继承**主域全部权重；Medium 的 `medium.com/@用户` 是路径不是子域名，蹭根域能力更强
- Google 官方（John Mueller）多次表示域名年龄本身几乎不是排名因素；真正起作用的是**链接图谱 + 历史行为数据**（外链存量、历史信任、品牌信号、抓取配额）——DA/DR 本质上就是在量化这两样
- 零成本验证路线：Blogger（Google 亲儿子，免费二级域名）+ Google Search Console 的 **Discover 效果报告** —— 20–30 篇、跑 2–4 周，看 Discover 展示数是否 >0，即可定性验证"AI 洗稿能不能吃到推荐流"；子域名权重低只影响量级不影响定性结论

**风险**
- 命脉捏在 Google 手里：一次"低价值 AI 内容"算法更新即可归零；30 万→24 万→76 万的剧烈波动就是证据
- 所谓"保证流量"不存在 —— 本质是**用 $500 成本赌不对称收益**：成了月入上万，败了换个域名重来；这类站从不做品牌，只做批量

**这个案例给 focus 补的一块**：AI 商业机会光谱的灰色端 —— "AI + 公开信息"的最低形态：不取水（无一手信息）、只烧水（洗稿扩写）、赚推荐流量的注意力差价。与本 focus 提倡的"上游数据 + AI 处理"正道对照看：ATS 案例的数据生产者有动机持续准确公开（公司要招人），内容农场只想套利。理解它有助于识别什么是真正的上游价值 —— **收录为反面教材**。

## 案例延伸：shattered.io（疑似同一运营者的矩阵站）

tech-insider.org 案例的后续。2026-10-15 用户问起 shattered.io 流量时，发现这是**同一套打法在另一个域名上的复刻** —— 而且手法更激进。

**域名背景**：shattered.io 原是 Google 与 CWI Amsterdam 在 2017 年 SHAttered（首次 SHA-1 碰撞演示）项目的官方站点（域名 2017-02-10 注册），密码学史上留名，外链含维基百科与大量安全媒体。约 2026-06-10 被转制为 AI 内容农场（页面标注 Published 2026-06-10，Updated 2026-09-22）。

**转制手法（"借尸还魂"升级版）**
- 首页保留 SHAttered 原始故事，保住老外链权重；meta 描述改成与 tech-insider.org **一字不差**的模板："Shattered covers AI, cybersecurity, cloud computing, hardware, software, startups, gaming, and mobile technology. In-depth analysis and breaking news…"
- 过渡话术："These guides pick up where the research leaves off" —— 拿 SHAttered 余威给新内容导权重
- 站内已批量发布 AI 长文（2026-08/09/10）：SteamDB 被收购（https://shattered.io/steamdb-nexus-mods-acquisition-2026/ ）、Cloudflare Workers vs Vercel Edge（https://shattered.io/cloudflare-workers-vs-vercel-edge-2026/ ）、R6 vs Valorant 排名对比 —— 同一配方：长文 + 对比表 + FAQ + `[2026]` 标题 + 站内互链
- robots.txt 暴露 9 个多语言子目录 sitemap（/de /fr /it /dk /se /fi /no /at /pt）—— 与 tech-insider.org 的多语言铺量策略一致

**流量**：sitezilla（约 2 个月前数据）：589 独立用户/天 ≈ 1.8 万/月，全球排名 ~125 万 —— 转制仅 3–4 个月，还在起量期；约为 tech-insider.org（76 万/月）的 1/40

**"同一运营者"验证结论：高度疑似，未实锤**（2026-10-15 核查）
- 支持：meta 描述模板一字不差（最强信号）；多语言组合高度重合（北欧+西欧）；内容配方、WordPress、双站 ads.txt 都是 404，全一致
- 存疑：WHOIS 仍是 Google 时代旧数据且 registrant 已 redacted，无法比对注册人；robots.txt 风格不同（tech-insider.org 是 RankMath 式详细版，shattered.io 是 WP 默认极简版），可能是不同批次配置差异
- 实锤还缺：GA/AdSense ID、同一 Cloudflare 账号、HTML 模板指纹 —— 需看网页源码，文本抓取拿不到

**这个延伸案例给 focus 补的一块**："买老域名"打法的天花板不是去二手市场淘 2013 年域名，而是**直接拿下有维基外链的知名研究/项目域名借尸还魂**。shattered.io 的权重基础远超 tech-insider.org，起量后天花板可能更高。这也解释了为什么这类运营者要做矩阵：单个域名随时可能被 Google 降权，矩阵 = 风险分散。

### 追问 1：免费二级域名能吃 Google Discover 吗？（2026-10-15）

**先说机制**：Discover 看的是页面，不是域名。门槛是被 Google 索引 + 符合 Discover 内容政策 + 有大图（官方建议 1200px 以上，需 `max-image-preview:large`）。二级域名本身不被排除，但各平台实际差距很大：

- **Blogspot（`xxx.blogspot.com`）✅ 最有实证**：南亚博主圈（巴基斯坦/印度）大量案例，有人专门写教程教 blogspot 博主吃 Discover，单篇爆了 5,000–50,000 访问，Search Console 里有专门的 Discover 报告。但代价是 Google 默认把 blogspot 子域名当 "hobbyist"，信任分起步低、抓取慢，需靠持续日更 + 高质量配图硬拉回来。
- **Substack（`xxx.substack.com`）⚠️ 搜索流量有，Discover 少见**：有人晒 GSC 证明 substack 子域名能吃到 Google 搜索流量；但 Discover 专门案例很少。结构性原因：Substack 无 schema 标记、sitemap 管理弱、图片控制少，而这些正是 Discover 分发看重的信号 —— 平台为邮件和订阅设计，不是为 Google 排名设计。
- **WordPress.com 免费版**：理论上可以（能被索引），但没见到 Discover 成功实证；免费版有平台广告、优化手段受限。
- **GitHub Pages**：技术上具备资格（页面可被索引），但内容类型进不了 Discover 兴趣流 —— dev 博客和项目文档不是 Discover 推的新闻/生活/好奇心类内容。实证：al-folio 主题 demo 站的 marimo 示例页（https://alshedivat.github.io/al-folio/blog/2025/marimo/ ）被索引了但零分发；整站 1.1 万/月流量中搜索仅占 2.5%，76% 直接访问 + 19% 社交，全是来看主题的人。
- **Vercel / Netlify / Cloudflare Pages**：没戏。上面基本没有内容页可言（全是 demo 和小应用），且 `vercel.app` 类域名曾被钓鱼滥用，在 Google 那里的信任分是负的。

### 追问 2：内容农场是否只有"买域名"一条路？（2026-10-15）

**不是。买域名是整套打法里最便宜的一环**（约 $12/年），根本不是门槛。不买域名的路至少有三条：Blogspot 子域名（上文，有 Discover 实证）、Parasite SEO（直接在 Medium、LinkedIn 文章、Quora 等高权重平台发内容，吃它们的域名信任分）、社交流量（Facebook 页面/群组导流，很多农场根本不靠 Google）。

**真正的变量不是域名，而是 Google 的 spam 政策** —— 这是对上文 shattered.io "借尸还魂天花板"论的重要修正：
- 2024 年 3 月起，"**过期域名滥用**"（expired domain abuse）和"**规模化内容滥用**"（scaled content abuse）都是 Google 的明文 spam 政策。
- tech-insider.org（2013 年老域名 repurpose + AI 规模化产文）和 shattered.io（2017 年 Google 自家 SHAttered 项目域名 repurpose）**正好两条全踩**。
- 所以这套打法的现状是**跟 Google 反垃圾政策对赌**：$12 的域名和 $0 的二级域名，在"会不会被一波核心更新连根拔起"面前没有区别。矩阵站的本质就是风险分散 —— 赌的是"被抓之前先赚一波"。

**给 focus 的结论**：评估这类流量套利形态时，关键问题不是"域名要不要买、买什么样的"，而是"这是长期资产还是赚一波就跑的套利"。域名成本从来不是壁垒，政策风险才是。

### 追问 3：二级域名流量起来了，能挂广告赚钱吗？（2026-10-15）

分平台结论：只有一个是顺的，其他全是坑。

- **Blogspot（`xxx.blogspot.com`）✅ 唯一顺的**：Blogger 后台原生集成 AdSense，"Make Money" 一键接入 —— Google 自家产品，有特殊通道。AdSense 注册时 `xxx.blogspot.com` 是被允许的例外（Google 员工在官方论坛确认过 Blogger 是 special case）。但实测通过率 20–30%，独立域名 70–80% —— 能赚钱，但审核更严。
- **WordPress.com 免费版 ❌ 钱是平台的**：免费版访客看到的是 WordPress.com 自己放的广告，站长一分没有；也不能挂 AdSense 或任何第三方广告 —— 要挂 AdSense 得上 Business 版（$25/月起）。流量起来了，变现的是 Automattic。
- **Substack ❌ 模式就不对**：变现 = 付费订阅，不支持挂展示广告。流量起来的正确姿势是开付费墙（$5–15/月/人），不是广告。
- **GitHub Pages：技术上行，经济上不行**：静态托管随便嵌广告 JS 没人拦，但受众是开发者（广告屏蔽率最高的人群），内容是文档（广告单价最低的内容），流量还小 —— 能挂，赚不到。
- **Vercel / Netlify ⚠️**：技术上能嵌代码，但免费 tier 有带宽上限 —— 流量真起来先爆的是带宽账单，不是广告收入。

**算账**：就算 Blogspot + AdSense 跑通，Discover 流量的 RPM（千次展示收入）一般 $1–5，发展中国家流量更低。单篇爆 5 万阅读 ≈ $50–250。**单站单篇的钱很薄，只能靠量堆** —— 这就是内容农场要矩阵化、日更几十篇的经济原因。

**丑话**：AdSense 对"无价值/AI 洗稿内容"也有封号政策。tech-insider.org 那种 AI 规模化洗稿站，就算流量起来，AdSense 审核和账号存活是另一道鬼门关 —— 这也解释了为什么它要卖 $10 一条的外链：**广告可能是它最不靠谱的那块收入**，卖外链反而是更确定的现金流。

## 上游数据源清单

按领域整理的公开上游数据源。规律：凡是"需要政府批准才能干的事"（雇人、募资、卖药、开诊所、拿合同、游说），背后都有一个强制公示库。✅ 表示已实际拉取验证过。

**移民 / 劳工**
- ✅ USCIS H-1B Employer Data Hub —— 全美雇主 H-1B 初次批准/拒绝数（FY2009–FY2026Q2），可按公司/城市/州/NAICS 查询导出
- ✅ DOL OFLC Performance Data —— PERM（绿卡劳工证）、LCA（H-1B 工资申报）、H-2A/H-2B 全量披露，含雇主、职位、工资、工作地
- DOL prevailing wage 库 —— 各职位各地区的法定最低工资

**公司 / 金融**
- SEC EDGAR —— 上市公司 10-K/10-Q、13F（机构持仓）、Form D（私募融资披露）、内幕交易申报
- 各州 Secretary of State 公司注册库 —— 公司状态、注册代理人、高管名单（Florida Sunbiz、Washington 等支持免费 bulk 下载）
- IRS Form 990 —— 非营利组织财报
- OpenCorporates —— 跨国公司实体图谱

**许可 / 执照**
- 各州职业执照库 —— 医生、律师、承包商、电工等，很多州直接提供全量 CSV 下载
- FCC 执照库、FAA 航空器/飞行员注册库
- 欧洲：ESMA Registers → 各国 NCA（MiFID 牌照，thread 1186353 案例）；英国 FCA Register；中国《烟草专卖零售许可证》库（thread 1186353 案例）

**医药 / 健康**
- openFDA —— 药品不良事件报告（1500 万+）、药品标签
- ClinicalTrials.gov —— 40 万+ 临床试验
- CMS data.cms.gov —— Medicare 支付、医院/医生数据；NPI Registry —— 全美医疗从业者注册

**钱的流向**
- USASpending.gov / SAM.gov —— 联邦政府采购合同全量（谁刚拿到政府 AI 合同 → 可能扩招）
- FEC —— 竞选捐款、候选人、委员会，支持 bulk 下载

**法规 / 立法 / 游说**
- Federal Register API —— 联邦法规、拟议规则（1994 至今），免费免 key
- regulations.gov —— 法规公众评论意见
- Congress.gov API —— 法案、投票记录
- Senate Lobbying Disclosure（LDA）—— 谁在为什么议题雇游说公司；FARA —— 外国代理人登记

**法院**
- CourtListener / RECAP —— 免费判例和案卷
- PACER —— 联邦法院全量案卷（付费）

**专利 / 商标**
- USPTO bulk data —— 专利、商标申请全量
- EUIPO 商标库、EPO Espacenet（thread 1186353：商标注册通常早于产品发布 6–18 个月，是产品先行指标）

**房地产**
- 各县 assessor / parcel 数据 —— 房主、估值、交易记录；NYC ACRIS 有 bulk 下载

**统计**
- Census（人口普查）、BLS（劳工统计）、BEA（经济分析）

**招聘 / 职位**（平台被迫公开的结构化数据）
- Greenhouse / Lever / Ashby boards API —— 公司 ATS 公开职位，title + JD 天然结构化（thread 1178971 系列案例：4,000+ 家公司招聘页抓取）
- Workday 职位页 —— 覆盖公司极多，但需 JS 渲染、反爬严，抓取成本高

**总入口**
- data.gov（美国）、data.gov.uk（英国）、data.gouv.fr（法国）、欧盟 open data portal

## 已见的商业机会形态

- **商业化与客户触达**（2026-10-02）：[upstream-data-gtm.md](upstream-data-gtm.md)——数据源清单 × 客户触达矩阵：每类上游数据卖给谁、卖什么形态、怎么触达、最小验证实验；总原则：需求验证先行、卖工作流不卖数据、可持续＝订阅。

- **免费数据包装成订阅**：网上大量订阅站把 GOV.UK 的免费 CSV 包装成 £9.99/月的"独家数据库"——"上游数据 + 处理 + 呈现"本身就是一门生意，自己下载 + Excel 筛选功能完全一样，差的是包装和触达。
- **信息服务**：求职端的公司挖掘（案例 A 的完整链路：名单 → 三维过滤 → 落地到 hiring manager 的冷邮件）。
- **商业分析**：商圈/密度分析（案例 B：持证数、扩张收缩趋势、空白点、准入难度反推）。
- **AI 内容农场（流量套利，灰色，反面教材）**：tech-insider.org —— AI 洗稿科技新闻 + 老域名/刷外链 + Google Discover 吃推荐流；启动 $100–600、月运营 $30–350，变现靠广告/affiliate + 卖外链（$10/篇）；无一手信息，命脉在 Google 算法手里。详见本文件"案例：AI 内容农场 tech-insider.org"一节。

## 边界与局限

- 上游数据给的是**骨架不是肉**：告诉你"谁被允许做"，不告诉你"谁在招人"——仍需下游信息补全画像。
- 持牌实体 ≠ 实际运营实体：大集团里持牌的可能是空壳法人。
- 更新频率差异大：用之前先看"最后更新日期"。
- 只覆盖有公开数据源的领域：不需要任何牌照的创业公司，这套方法帮不上忙。
- 平台侧上游要记录抽样框：ATS 抓取类项目必须披露公司名单/来源构成，否则 Top 榜单无法排除名单偏差（thread 1178971 教训）。

## 相关帖子

- [thread-1186353-upstream-info-job-hunting.md](../threads/thread-1186353-upstream-info-job-hunting.md)——种子帖：上游信息方法论、AI 正确分工、欧洲金融 MiFID 牌照库与中国烟草许可证库双案例。
- [thread-1178971-ats-job-scraping.md](../threads/thread-1178971-ats-job-scraping.md)——ATS 招聘数据系列（SE/DE/AIE/MLE 三篇）：平台侧上游抓取的方法论、数据摘要、评论区问答与方法论评价。
