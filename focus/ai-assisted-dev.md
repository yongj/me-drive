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

## 待观察 / 可跟进

- ArtCraft 的 GitHub star / Discord 人数是否持续涨（验证"开源换社区"飞轮）
- 是否真被收购、被谁收购（验证楼主判断）
- Topaz / Office 平替赛道有没有人按这个模式做起来
- MCP-native 工具的获客效率 vs 传统渠道，有无量化案例
