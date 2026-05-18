# Awesome Amazon EC Skills 亚马逊跨境电商 Claude / AI Agent 技能合集

![Logo](./logo.png)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](./CONTRIBUTING.md) [![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](./LICENSE)

> 为亚马逊跨境卖家精选的 Claude Skills、Claude Code Plugins、MCP Servers 与 AI Agent。
> 覆盖选品 → 竞品 → Listing → 视觉 → 数据 BI → 广告 → 评论 全流程，含 1688 供货上游。

> **收录范围**：聚焦 Amazon + 1688/Alibaba 供货上游。其他出海平台（Rakuten / Shopify / TikTok Shop / Temu / SHEIN 等）与国内销售平台（小红书 / 抖音 / 微信 / 视频号 / 淘宝 / 京东 / 拼多多）均不收录。

---

## 📑 目录

- [💡 什么是 Claude Skill / Plugin / MCP？](#什么是-claude-skill--plugin--mcp)
- [🛒 为什么需要 Amazon 专用 Skill？](#为什么需要-amazon-专用-skill)
- [📚 Skills 收录](#skills-收录)
  - [🔍 选品调研](#product-research)
  - [⚔️ 竞品分析](#competitor-analysis)
  - [📝 Listing 与内容](#listing-content)
  - [📸 视觉与素材](#creative-visual)
  - [📊 数据分析与 BI](#analytics-bi)
  - [🎯 广告与流量](#ads-traffic)
  - [⭐ 评论与口碑](#reviews-reputation)
  - [💬 客服与售后](#customer-service)
  - [🛠️ 通用底座](#general-foundation)
- [🎓 上手指南](#上手指南)
- [🏗️ 创作你自己的 Skill](#创作你自己的-skill)
- [🤝 贡献指南](#贡献指南)
- [🔗 资源](#资源)
- [💬 加入社区](#加入社区)
- [📜 License](#license)

---

<a id="什么是-claude-skill--plugin--mcp"></a>
## 💡 什么是 Claude Skill / Plugin / MCP？

| 概念 | 一句话定位 | 适合做什么 |
|---|---|---|
| **Skill** | 给 Claude 的 SOP 文档（`SKILL.md`），按需加载 | 流程性、可复用任务（如写 Amazon listing、做 VOC 分析） |
| **Plugin** | Claude Code 的本地扩展，可挂 hooks、slash commands、subagents | 工作流自动化、IDE 集成 |
| **MCP Server** | Model Context Protocol 服务端，给 Claude 接入外部工具/数据 | 调用 Amazon SP-API、SIF MCP、Sorftime 等 |
| **Subagent** | 在 Claude 内派生的专家角色，独立 context | 大型任务拆解（如选品 → 上架 → 投放） |

Amazon 卖家场景三者常**组合用**：MCP 接 SP-API / 第三方数据源 → Skill 描述运营 SOP → Subagent 派多个角色干活。

---

<a id="为什么需要-amazon-专用-skill"></a>
## 🛒 为什么需要 Amazon 专用 Skill？

Amazon 跨境卖家的痛点：
- **规则繁复**：A9 / COSMO / Rufus 算法迭代快，BSR / SP / SB / SD / DSP 各有玩法，通用 LLM 工具往往写不对 listing 或投不对广告
- **数据散在 SP-API / 各 SaaS**：Business Report / Search Term Report / Brand Analytics / ABA / 卖家精灵 / Helium10 / SIF / Sorftime 各家一摊
- **多站点 + 多语言**：美/英/德/法/意/西/日/加/墨/澳，listing、客服、Q&A 都要本地化
- **合规压力大**：VAT / EPR / Brand Registry / 二审 / Section 3 / Buyer-Seller Communication，一步错可能封号
- **供应链上游零碎**：1688 找货比价、打样、贴牌、头程 SOP 全靠人记

本仓库只收录"能在 Amazon 跨境出海场景里直接落地、被社区验证过"的 skill。

> **元信息 emoji**（出现在 skill 行末）：`🆓 完全免费` / `💎 需付费 API` / `💰 skill 本身付费` / `🅐 Anthropic 官方` / `⭐ 高星推荐（≥500 stars）` / `🆕 30 天内新增`

---

<a id="skills-收录"></a>
## 📚 Skills 收录

> 仓库刚起步，正在分批收录。欢迎通过 PR 贡献你发现的好 skill —— 参见 [CONTRIBUTING.md](./CONTRIBUTING.md) 与 [SKILLS_TEMPLATE.md](./SKILLS_TEMPLATE.md)。

### <a id="product-research"></a>🔍 选品调研

> 找品、判断市场容量、需求挖掘、关键词监测、供应链匹配。

* [Amazon-ABAkeyword](https://github.com/luotwo/Amazon-ABAkeyword) — 监测 Amazon ABA 爆品关键词并出飞书仪表盘，三级预警 🆓 _By [@luotwo](https://github.com/luotwo)_
* [amazon-product-search](https://github.com/luotwo/amazon-product-search) — Sorftime MCP 数据 → 飞书多维表 + Dashboard 可视化 💎 _By [@luotwo](https://github.com/luotwo)_
* [sorftime-cli](https://github.com/sorftime/sorftime-cli) — Sorftime 官方多平台数据 CLI，类目/产品/关键词查询 💎 _By [@sorftime](https://github.com/sorftime)_
* [BSC-amazon-VOC-trending-products](https://github.com/luotwo/BSC-amazon-VOC-trending-products) — Amazon 选品+VOC+竞品研究一体化流水线 🆓 _By [@luotwo](https://github.com/luotwo)_
* [BSC-SIF-Amazon-keyword-database](https://github.com/luotwo/BSC-SIF-Amazon-keyword-database) — SIF MCP 关键词数据库 skill，飞书结构化交付 💎 _By [@luotwo](https://github.com/luotwo)_
* [1688-product-find](https://github.com/next-1688/1688-product-find) — 1688 智能找商品/找同款，支持文本/图片/链接 🆓 _By [@next-1688](https://github.com/next-1688)_
* [BSC-Amazon-sif-keyword-lark-builder](https://github.com/luotwo/BSC-Amazon-sif-keyword-lark-builder) — Sif 关键词 Excel → Lark 文档/多维表/Dashboard 💎 _By [@luotwo](https://github.com/luotwo)_
* [1688-source-suppliers](https://github.com/next-1688/1688-source-suppliers) — 1688 找供应商/工厂/产业带查询 🆓 _By [@next-1688](https://github.com/next-1688)_
* [google-trends-skills](https://github.com/WaytoAIC/google-trends-skills) — Google Trends 热度雷达 + 关键词监测 🆓 _By [@WaytoAIC](https://github.com/WaytoAIC)_
* [zach-product-research](https://github.com/zach22-1999/amazon-skills/tree/main/skills/zach-product-research) — Sorftime MCP 选品分析，交付 MD/HTML/Dashboard/Excel 四件套 💎 _By [@zach22-1999](https://github.com/zach22-1999)_
* [zach-feature-demand-validator](https://github.com/zach22-1999/amazon-skills/tree/main/skills/zach-feature-demand-validator) — Review/关键词/社区三维数据验证微创新是否真实需求 🆓 _By [@zach22-1999](https://github.com/zach22-1999)_

### <a id="competitor-analysis"></a>⚔️ 竞品分析

> ASIN/卖家/品牌追踪、竞品 Listing 解构、价格/库存动态监控。

* [amazon-competitor-monitor](https://github.com/WaytoAIC/amazon-competitor-monitor) — Amazon 竞品监控 Skill，含 ASIN / seller / brand 追踪 🆓 _By [@WaytoAIC](https://github.com/WaytoAIC)_

### <a id="listing-content"></a>📝 Listing 与内容

> 标题、五点、A+、品牌故事、SEO 文案、合规审核、COSMO/Rufus 适配。

* [BSC-Amazon-Rufus-Cosmo](https://github.com/luotwo/BSC-Amazon-Rufus-Cosmo) — Amazon ASIN 的 COSMO + Rufus + Listing 审计与改写 🆓 _By [@luotwo](https://github.com/luotwo)_
* [ecommerce-content-compliance-review](https://github.com/WaytoAIC/ecommerce-content-compliance-review) — 跨境电商内容合规审核 Skill 🆓 _By [@WaytoAIC](https://github.com/WaytoAIC)_
* [zach-listing-health-checker](https://github.com/zach22-1999/amazon-skills/tree/main/skills/zach-listing-health-checker) — 真实消费者视角 9 维 Listing 健康度体检，零三方依赖 🆓 _By [@zach22-1999](https://github.com/zach22-1999)_

### <a id="creative-visual"></a>📸 视觉与素材

> 主图、详情图、A+ 模块图、短视频脚本、品牌 banner。

_暂无合格收录，欢迎贡献。_

### <a id="analytics-bi"></a>📊 数据分析与 BI

> 销售、库存、Session、CVR、ACOS、利润看板与周报、运营诊断。

* [amazon-sp-mcp](https://github.com/mansournorouzi/amazon-sp-mcp) — Amazon SP-API MCP，仅需 LWA OAuth 免 AWS IAM 🆓 _By [@mansournorouzi](https://github.com/mansournorouzi)_
* [BSC-amazon-SIF-Tool](https://github.com/luotwo/BSC-amazon-SIF-Tool) — 用 SIF MCP 分析 ASIN 流量/广告/关键词/销量并发飞书 💎 _By [@luotwo](https://github.com/luotwo)_
* [Amazon-Operations-Analysis-Dashboard](https://github.com/luotwo/Amazon-Operations-Analysis-Dashboard) — Sorftime × Claude Code 智能运营诊断 + 类目机会导航 💎 _By [@luotwo](https://github.com/luotwo)_
* [sif-mcp-skills](https://github.com/WaytoAIC/sif-mcp-skills) — SIF MCP 套件：Amazon 流量/关键词/广告/异常多维分析（4 子 skill）💎 _By [@WaytoAIC](https://github.com/WaytoAIC)_

### <a id="ads-traffic"></a>🎯 广告与流量

> SP / SB / SD / DSP / Posts / 红人 / affiliate / 站外 deal 站。

* [BSC-amazon-advertising-strategy](https://github.com/luotwo/BSC-amazon-advertising-strategy) — 面向 Amazon 卖家的广告策略 skill，生成可执行投放方案 🆓 _By [@luotwo](https://github.com/luotwo)_
* [zach-search-term-report-analyzer](https://github.com/zach22-1999/amazon-skills/tree/main/skills/zach-search-term-report-analyzer) — 分析 SP/SB/SD 广告搜索词报告，识别低效/放量/属性/场景词 🆓 _By [@zach22-1999](https://github.com/zach22-1999)_

### <a id="reviews-reputation"></a>⭐ 评论与口碑

> 抓评、差评分析、合规索评、QA 起草、品牌舆情监控。

* [review-analyzer-skill](https://github.com/buluslan/review-analyzer-skill) — AI 评论深度分析（22 维标签 + VOC 看板），跨境电商优先 🆓 _By [@buluslan](https://github.com/buluslan)_
* [voc-amazon-reviews](https://github.com/mguozhen/voc-amazon-reviews) — 亚马逊 10 站点评论 VOC 分析 MCP，输出中英双语建议 💎 _By [@mguozhen](https://github.com/mguozhen)_
* [amazon-reviews](https://github.com/luotwo/amazon-reviews) — Sorftime MCP 评论分析 + lark-cli 发飞书文档报告 💎 _By [@luotwo](https://github.com/luotwo)_

### <a id="customer-service"></a>💬 客服与售后

> Buyer Message、A-to-Z 申诉、Negative Feedback 移除、多语言客服。

_暂无合格收录。**此分类目前开源生态稀缺**——欢迎贡献：Amazon Buyer Message 模板、A-to-Z 申诉信、Section 3 申诉等场景。_

### <a id="general-foundation"></a>🛠️ 通用底座

> Amazon 场景下可二次包装的通用 skill（综合 OS / 创建器 / 搜索 / 抓取 / 测试等）。

* [firecrawl-mcp-server](https://github.com/firecrawl/firecrawl-mcp-server) — Firecrawl 官方 MCP，抓 Amazon Listing/竞品独立站结构化数据 💎⭐ _By [@firecrawl](https://github.com/firecrawl)_
* [brightdata-mcp](https://github.com/luminati-io/brightdata-mcp) — Bright Data MCP，60+ 站点结构化抓取，反爬强 💎⭐ _By [@luminati-io](https://github.com/luminati-io)_
* [tavily-mcp](https://github.com/tavily-ai/tavily-mcp) — Tavily 网搜 MCP，Amazon 选品调研做行业/趋势快搜 💎⭐ _By [@tavily-ai](https://github.com/tavily-ai)_
* [actors-mcp-server](https://github.com/apify/actors-mcp-server) — Apify Actor 商店 MCP，含 Amazon Scraper 等 5000+ 爬虫 💎⭐ _By [@apify](https://github.com/apify)_
* [BSC-Amazon-OPC-Agent-OS](https://github.com/luotwo/BSC-Amazon-OPC-Agent-OS) — BSC OPC Agent OS V2.0 — Amazon 产品运营综合 AI 工作台 🆓 _By [@luotwo](https://github.com/luotwo)_
* [zach-seller-skill-creator](https://github.com/zach22-1999/amazon-skills/tree/main/skills/zach-seller-skill-creator) — 亚马逊卖家专用 skill 创建器，含 6 问准入闸 🆓 _By [@zach22-1999](https://github.com/zach22-1999)_
* [skill-creator](https://github.com/anthropics/skills/tree/main/skills/skill-creator) — Anthropic 官方 Skill 创建器，输出规范 SKILL.md 🆓🅐 _By [@anthropics](https://github.com/anthropics)_

---

<a id="上手指南"></a>
## 🎓 上手指南

### 新手路径
1. 读官方 [Skills 文档](https://docs.claude.com/en/docs/claude-code/skills) 了解概念
2. 从「🛠️ 通用底座」分类挑 1 个 skill 装上跑一遍（推荐 [`skill-creator`](https://github.com/anthropics/skills/tree/main/skills/skill-creator) 或 [`tavily-mcp`](https://github.com/tavily-ai/tavily-mcp)）
3. 再从「🔍 选品调研」/ 「📝 Listing 与内容」按你的业务环节挑 skill

### 进阶路径
- 自己写 skill 投稿 → 参考 [`docs/how-to-skillify.md`](./docs/how-to-skillify.md)（v1 待补）
- 用 [`anthropics/claude-cookbooks`](https://github.com/anthropics/claude-cookbooks) 学 agent 编排
- 关注 [`anthropics/skills`](https://github.com/anthropics/skills) release

---

<a id="创作你自己的-skill"></a>
## 🏗️ 创作你自己的 Skill

最小 Skill 包含一个 `SKILL.md` 文件，前缀 YAML frontmatter：

```markdown
---
name: my-amazon-helper
description: 用于 [具体 Amazon 场景] 的 skill；当用户提到 [触发关键词] 时使用
---

# 任务流程
1. ...
2. ...
```

进阶模板见官方 [`anthropics/skills`](https://github.com/anthropics/skills) 与 [`skill-creator`](https://github.com/anthropics/skills/tree/main/skill-creator)。
卖家场景模板可参考收录中的 [`zach-seller-skill-creator`](https://github.com/zach22-1999/amazon-skills/tree/main/skills/zach-seller-skill-creator)。

---

<a id="贡献指南"></a>
## 🤝 贡献指南

详见 [CONTRIBUTING.md](./CONTRIBUTING.md)。

**5 步快速贡献**：
1. Fork → 找对应一级分类的 H3
2. 复制 [`SKILLS_TEMPLATE.md`](./SKILLS_TEMPLATE.md) 的 bullet 模板
3. 按 stars 降序插入正确位置
4. 填好 PR 模板（Amazon 真实使用案例必填）
5. 提交 PR

**收录硬门槛**：公开 GitHub repo + 兼容 license（或作者公开声明开源）+ 含 `SKILL.md` 或同类清单 + README ≥200 字 + 近 6 个月有 commit + Amazon 跨境出海或 1688 供货落点。

---

<a id="资源"></a>
## 🔗 资源

### 官方
- [Anthropic Skills 官方文档](https://docs.claude.com/en/docs/claude-code/skills)
- [`anthropics/skills`](https://github.com/anthropics/skills) — 官方 skill 主仓库
- [`anthropics/claude-cookbooks`](https://github.com/anthropics/claude-cookbooks) — agent 实践案例
- [Model Context Protocol (MCP) 规范](https://modelcontextprotocol.io)
- [Amazon SP-API 官方文档](https://developer-docs.amazon.com/sp-api/)

### 同类 Awesome-list
- [`ComposioHQ/awesome-claude-skills`](https://github.com/ComposioHQ/awesome-claude-skills) — 通用 skill 大合集
- [`punkpeye/awesome-mcp-servers`](https://github.com/punkpeye/awesome-mcp-servers) — MCP 服务端集合

### Amazon 卖家工具生态
- [Helium 10](https://www.helium10.com/) / [Jungle Scout](https://www.junglescout.com/) / [Sellersprite 卖家精灵](https://www.sellersprite.com/) — 商业选品 SaaS（对比参考）
- [Sorftime](https://sorftime.com/) / [SIF](https://sif.so/) — 卖家常用数据 MCP 服务源
- [Tavily AI](https://tavily.com) / [Bright Data](https://brightdata.com/) / [Firecrawl](https://firecrawl.dev/) — LLM 友好搜索/爬虫

---

<a id="加入社区"></a>
## 💬 加入社区

- 提 issue：[新 Skill 推荐](https://github.com/hikari0511/awesome-amazon-ec-skills/issues/new/choose)
- 讨论：开启 GitHub Discussions 后链接补充
- 联系维护者：通过 issue / PR

---

<a id="license"></a>
## 📜 License

本仓库内容（README、CONTRIBUTING、模板等文档）按 [CC0-1.0](./LICENSE) 释出到公共领域。
被收录的每个 skill 自身 license 以其原仓库声明为准。

---

> ⭐ 如果这个仓库对你有帮助，欢迎 star。也欢迎 [PR](./CONTRIBUTING.md) 贡献你发现的好 skill。
