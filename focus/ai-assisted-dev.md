# AI-Assisted Dev（AI 辅助开发实战）

*Coding agent（Claude Code 等）驱动真实软件开发的案例，以及"开源平替主流软件 + 卖附加值服务"的小团队商业模式。从已收集帖子中提炼，持续更新。*

> 范围说明：这个文件收的是 **AI 实际参与写代码 / 驱动软件** 的实战案例和商业模式观察。**不收**面试中怎么考 AI coding（那是 [ai-coding-in-interviews.md](ai-coding-in-interviews.md) 的事），**不收** AI Engineer 岗位本身考什么（那是 [ai-engineer.md](ai-engineer.md) 的事）。

## 种子案例：ArtCraft —— Rust 重写 Adobe 全家桶（thread 1192774）

- 帖子：[直接抄袭，开源主流软件是最快发财的思路](https://www.1point3acres.com/home/thread/1192774)（2026-10，楼主实测分享）
- 项目：[ArtCraft](https://getartcraft.com/) —— "Controllable AI for Artists"，开源艺术家工具（官网自述：整个 studio 都在 GitHub 上，免费开源、无订阅；浏览器端直接跑 AI 生图/视频：Seedance 2.5、Nano Banana 2、图生 3D、3D 合成、抠图等）
- 商业模式（楼主总结）：直接复制 Adobe 全家桶 → 开源建社区 → 卖云服务（AI 生图/视频）+ 咨询服务
- 社区热度（楼主称）：每个 GitHub repo 几万 star，Discord 七万人
- 技术路线：纯 Rust；**天生提供 MCP 接口，支持所有 coding agent**
- 楼主实测：周末试了几个产品，**用 Claude Code 直接驾驭**，觉得非常好用；判断"使用体验几个版本以后必然大幅度超越 Adobe 本来的产品"
- 楼主的判断：以开源建立社区、卖附加值服务是小团队最强的思路，"估计大概率能被收购"
- 楼主抛出的选题：搞个 Topaz image/video upscaling 的平替会非常火；或者 Office 平替

## 提炼出的模式

1. **"抄袭 + 开源 + 卖服务" 是小团队的最优解**：不跟巨头拼功能完整度，用开源换社区和信任，变现靠云服务/增值服务。收购退出是合理预期（巨头买社区+买团队）。
2. **MCP 是新的分发渠道**：工具天生带 MCP 接口 = 直接被所有 coding agent 驱动。以前软件靠应用商店/SEO 获客，现在"能被 agent 调用"本身就是获客。
3. **Coding agent 正在改写"用什么软件"的决策**：楼主不是评价 ArtCraft 的 UI，而是评价"被 Claude Code 驾驭"的体验。软件的竞争维度从 human UX 转向 agent UX。
4. **Rust 重写经典软件**：内存安全 + 高性能 + 跨平台，适合从零重写吃性能的桌面/创意软件；配合 AI agent 写 Rust，心智负担比以前低得多。
5. **AI 时代，代码不再是瓶颈，瓶颈前移**（QCam 案例）：写代码最容易，难的是选题（硬件/领域 know-how，AI 没有你的测试机）、做减法（需求判断，AI 只会加功能）、渠道（distribution）。AI 把 build 成本打下来之后，稀缺能力变成了 taste 和 distribution。
6. **可观测的 AI 工程实践**：QCam 团队在 CLAUDE.md / AGENTS.md 约定每次 commit 署名模型，一年后能量化每个模型的真实贡献，决定"哪个值得付钱"——把 AI 成本核算做进了工程流程。

## 案例二：QCam —— 和朋友用 AI 做 iOS App 一年（thread 1192789）

- 帖子：[离开微软两年，和朋友用 AI 做一个 iOS App 做了一年，分享下踩过的坑（欢迎提问）](https://www.1point3acres.com/home/thread/1192789)（2026-10）
- 作者自述：2024 年从微软离职（之前在 Outlook iOS 组），现居加拿大做独立开发；此前在创业版发过两篇创业经验帖
- 作者身份备注：用户推测为 Mike Chong（ScreenKite 联合创始人），**未验证**——页面文本未显示作者名；已核验其 Substack（mikechong.substack.com）归档，最新一篇为 9 月 6 日，无 10 月 QCam 相关文章，无法佐证
- 项目：QCam（iPhone 相机 + 提词器 App），和两个做视频的朋友合作，9 月 1 日上架
- 核心观点：**有了 AI，写代码反而是最容易的部分**（合伙人原话："因为现在 build 是最容易的，就先做你最不愿意做的事情"）
- 具体坑与建议：
  1. 选难的题目：iPhone 17 换方形传感器，初期无第三方 App 能吃满整块传感器；相机这种碰硬件的只能真机一台一台测（作者手边六七台测试机）；"AI 手上没有你的手机，它只会按理想情况写代码"；建议选自己了解的领域（作者做过图片编辑器，视频编辑器本质是"连续的图片"）
  2. 做减法比加法难：AI 让加功能太容易，一度做得非常复杂，花一个月专门简化；合伙人对 feature 先听着、九成最后不加；建议每个功能先算账，拿不准问 AI："假设你是 Steve Jobs 和 Jony Ive，这个功能清单你会砍掉哪些？"
  3. 先跑通渠道，再造产品：先做好 landing page 卖"假产品"，有人买再写代码；landing page 被 AI 搜索收录后带来访问和留邮箱，甚至有 AI 推荐带来的成交
  4. 让 AI 每次提交署名模型：CLAUDE.md / AGENTS.md 加一句，每次 commit 写明哪个模型写的；一年数据：晚 8 点最猛（1 小时 207 commit），feat 520 / fix 504（修的和做的一样多）
  5. 1+1 远大于 2：提词器实时听音 + 高画质录制吃同一块芯片，叠加难度成倍，老机型尤其明显
  6. 给上班族：别急着辞职，业余时间先验证付费意愿；大厂 60-70 分交差，做出 stand out 的产品要 90 分以上
- 配套：复盘写成免费 newsletter（含 QCam 起源故事 + 两个开源 agent skill 推荐：做减法、自动化测试相关）

## 待观察 / 可跟进

- ArtCraft 的 GitHub star / Discord 人数是否持续涨（验证"开源换社区"飞轮）
- 是否真被收购、被谁收购（验证楼主判断）
- Topaz / Office 平替赛道有没有人按这个模式做起来
- MCP-native 工具的获客效率 vs 传统渠道，有无量化案例
- QCam 后续数据（下载/收入/留存）是否验证"先渠道后产品"
- "commit 署名模型"的做法有没有被更多团队采用
- thread 1192789 作者身份验证（是否为 Mike Chong）
