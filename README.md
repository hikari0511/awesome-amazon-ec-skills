# Awesome EC Skills 跨境电商 Claude / AI Agent 技能合集

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](./CONTRIBUTING.md) [![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](./LICENSE)

> 为中国跨境电商卖家精选的 Claude Skills、Claude Code Plugins、MCP Servers 与 AI Agent。
> 覆盖 **Amazon / Rakuten / Shopify / TikTok Shop / Temu / SHEIN / 独立站** 全流程，含 1688 供货上游。

> **收录范围聚焦"出海 + 供货上游"。** 国内销售平台（小红书 / 抖音 / 微信 / 视频号 / 淘宝 / 京东 / 拼多多）**不收录**，请去其他 awesome-list 寻找。

---

## 📑 目录

- [🚀 30 秒快速开始](#30-秒快速开始)
- [💡 什么是 Claude Skill / Plugin / MCP？](#什么是-claude-skill--plugin--mcp)
- [🛒 为什么需要电商专用 Skill？](#为什么需要电商专用-skill)
- [🗂️ 分类导航（业务流程 × 平台）](#分类导航业务流程--平台)
- [📚 Skills 收录](#skills-收录)
  - [🔍 1. 选品调研](#product-research)
  - [📝 2. Listing 与内容](#listing-content)
  - [📸 3. 视觉与素材](#creative-visual)
  - [📊 4. 数据分析与 BI](#analytics-bi)
  - [🎯 5. 广告与流量](#ads-traffic)
  - [⭐ 6. 评论与口碑](#reviews-reputation)
  - [💬 7. 客服与售后](#customer-service)
  - [📦 8. 订单与物流](#orders-fulfillment)
  - [💰 9. 财务与合规](#finance-compliance)
  - [🤝 10. 团队协作与 SOP](#collaboration-sop)
  - [🧰 11. 平台运维](#platform-ops)
  - [🛠️ 12. 通用底座](#general-foundation)
- [🎓 上手指南](#上手指南)
- [🏗️ 创作你自己的 Skill](#创作你自己的-skill)
- [🤝 贡献指南](#贡献指南)
- [🔗 资源](#资源)
- [💬 加入社区](#加入社区)
- [📜 License](#license)

---

## 🚀 30 秒快速开始

### 在 Claude Code 里安装一个 marketplace
```bash
/plugin marketplace add anthropics/skills
/plugin install <skill-name>
```

### 在 Claude.ai 网页版
点聊天界面右侧 🧩 图标 → Upload skill → 上传 `.zip`。

### 在 Anthropic API
```python
client.messages.create(
    model="claude-opus-4-7",
    skills=["<skill-id>"],
    ...
)
```

详见 [Anthropic 官方 Skills 文档](https://docs.claude.com/en/docs/claude-code/skills)。

---

## 💡 什么是 Claude Skill / Plugin / MCP？

| 概念 | 一句话定位 | 适合做什么 |
|---|---|---|
| **Skill** | 给 Claude 的 SOP 文档（`SKILL.md`），按需加载 | 流程性、可复用任务（如写 Amazon listing） |
| **Plugin** | Claude Code 的本地扩展，可挂 hooks、slash commands、subagents | 工作流自动化、IDE 集成 |
| **MCP Server** | Model Context Protocol 服务端，给 Claude 接入外部工具/数据 | 调用平台 API（如 Shopify、Stripe） |
| **Subagent** | 在 Claude 内派生的专家角色，独立 context | 大型任务拆解（如选品 → 上架 → 投放） |

跨境电商场景三者会**组合用**：MCP 接平台 API → Skill 描述流程 → Subagent 派多个角色干活。

---

## 🛒 为什么需要电商专用 Skill？

跨境卖家工作流痛点：
- **平台规则碎片化**：Amazon / Rakuten / TikTok Shop 各家规则、API、词汇都不一样，通用 LLM 工具往往用不对
- **多语言 + 多市场**：日亚要日文、欧亚要欧标、北美要英文，需要 listing/客服文案多语言一致性
- **数据散落各平台**：业务报表要从 Seller Central / RMS / Shopify Admin / Google Sheets 来回搬
- **合规重**：VAT / EPR / 知识产权 / 品牌注册 / 二审 / Section 3，任一环节翻车都会封号
- **团队跨时区**：国内运营 + 海外仓 + 多平台客服，SOP 必须沉淀

本仓库只收录"能在以上场景里直接落地、被社区验证过"的 skill。

---

## 🗂️ 分类导航（业务流程 × 平台）

> 横轴是平台，纵轴是跨境卖家工作流的 12 个环节。✓ 表示该交叉象限有合格 skill；点击纵轴跳转到分类列表。

| 业务流程 \ 平台 | 🅰️ Amazon | 🅡 Rakuten | 🛍️ Shopify | 🎵 TikTok | 🟢 Temu/👗 SHEIN | 🌐 独立站 | 🛒 1688 | 🪶 飞书 |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| [🔍 选品调研](#product-research) | ✓ | — | — | — | — | — | — | — |
| [📝 Listing 与内容](#listing-content) | — | — | ✓ | — | — | ✓ | — | — |
| [📸 视觉与素材](#creative-visual) | ✓ | — | — | — | — | — | — | — |
| [📊 数据分析与 BI](#analytics-bi) | ✓ | — | — | — | — | — | — | — |
| [🎯 广告与流量](#ads-traffic) | — | — | — | — | — | ✓ | — | — |
| [⭐ 评论与口碑](#reviews-reputation) | ✓ | — | — | — | — | — | — | — |
| [💬 客服与售后](#customer-service) | — | — | — | — | — | — | — | — |
| [📦 订单与物流](#orders-fulfillment) | — | — | — | — | — | — | — | — |
| [💰 财务与合规](#finance-compliance) | — | — | — | — | — | ✓ | — | — |
| [🤝 团队协作与 SOP](#collaboration-sop) | — | — | — | — | — | ✓ | — | — |
| [🧰 平台运维](#platform-ops) | — | — | ✓ | — | — | — | — | — |
| [🛠️ 通用底座](#general-foundation) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

> **平台 emoji 完整说明**：`🅰️ Amazon` / `🅡 Rakuten Ichiba` / `🛍️ Shopify` / `🎵 TikTok Shop` / `🟢 Temu` / `👗 SHEIN` / `🏪 其他第三方（eBay/Walmart/Lazada/Shopee）` / `🌐 独立站（WooCommerce/Magento/自建）` / `🛒 1688/Alibaba/Made-in-China` / `🪶 飞书生态` / `🟦 通用`
>
> **元信息 emoji**：`🇨🇳 中文友好` / `🆓 完全免费` / `💎 需付费 API` / `💰 skill 本身付费` / `🅐 Anthropic 官方` / `⭐ 高星推荐（≥500 stars）` / `🆕 30 天内新增`

---

## 📚 Skills 收录

> 仓库刚起步，正在分批收录。欢迎通过 PR 贡献你发现的好 skill —— 参见 [CONTRIBUTING.md](./CONTRIBUTING.md) 与 [SKILLS_TEMPLATE.md](./SKILLS_TEMPLATE.md)。

### <a id="product-research"></a>🔍 1. 选品调研 / Product Research

> 找品、判断市场容量、需求挖掘、竞品分析、供应链匹配。

#### 🅰️ Amazon
* [APIClaw-Skills](https://github.com/SerendipityOneInc/APIClaw-Skills) - 亚马逊选品/竞品/趋势/Listing 体检 10 件套 🅰️ 🇨🇳 💎 _By [@SerendipityOneInc](https://github.com/SerendipityOneInc)_

### <a id="listing-content"></a>📝 2. Listing 与内容 / Listing & Content

> 标题、五点、A+、品牌故事、SEO 文案、多语言翻译。

#### 🛍️ Shopify
* [hydrogen-ecommerce-ux](https://github.com/hmtkyn/hydrogen-ecommerce-ux) - Shopify Hydrogen 店铺基于 Baymard UX 研究的 Skill 🛍️ 🆓 _By [@hmtkyn](https://github.com/hmtkyn)_

#### 🌐 独立站
* [ecommerce-email-sequences](https://github.com/charlieai-co/ecommerce-email-sequences) - 电商邮件序列 SOP（欢迎/弃购/复购/挽回）🌐 🆓 _By [@charlieai-co](https://github.com/charlieai-co)_

### <a id="creative-visual"></a>📸 3. 视觉与素材 / Creative & Visual

> 主图、详情图、A+ 模块图、短视频脚本、品牌 banner。

#### 🅰️ Amazon
* [kindle-cover-skill](https://github.com/nikmcfly/kindle-cover-skill) - Amazon KDP 平装书封面 PDF 生成（书脊+出血+安全区）🅰️ 🆓 _By [@nikmcfly](https://github.com/nikmcfly)_

### <a id="analytics-bi"></a>📊 4. 数据分析与 BI / Analytics & BI

> 销售、库存、Session、CVR、ACOS、利润看板与周报。

#### 🅰️ Amazon
* [amazon-sp-mcp](https://github.com/mansournorouzi/amazon-sp-mcp) - Amazon SP-API MCP，仅需 LWA OAuth 免 AWS IAM 🅰️ 🆓 _By [@mansournorouzi](https://github.com/mansournorouzi)_

### <a id="ads-traffic"></a>🎯 5. 广告与流量 / Ads & Traffic

> SP / SB / SD / DSP / 红人 / affiliate / 站外 deal / Google Shopping。

#### 🌐 独立站
* [mcp-gsc](https://github.com/AminForou/mcp-gsc) - Google Search Console MCP + 4 个 SEO Skill（周报、索引审计）🌐 🆓 ⭐ _By [@AminForou](https://github.com/AminForou)_
* [Agentic-SEO-Skill](https://github.com/Bhanunamikaze/Agentic-SEO-Skill) - 16 子 Skill + 10 Agent 的全栈 SEO 审计套件 🌐 🆓 ⭐ _By [@Bhanunamikaze](https://github.com/Bhanunamikaze)_
* [search-console-mcp](https://github.com/saurabhsharma2u/search-console-mcp) - GSC + Bing Webmaster + GA4 三合一 SEO MCP 🌐 🆓 _By [@saurabhsharma2u](https://github.com/saurabhsharma2u)_
* [markifact-mcp](https://github.com/markifact/markifact-mcp) - 统一 300+ 操作，含 Google/Meta/TikTok 广告 + Klaviyo 🌐 💎 _By [@markifact](https://github.com/markifact)_
* [konquest-meta-ads-mcp](https://github.com/brandu-mos/konquest-meta-ads-mcp) - 57 工具的 Meta Ads MCP（含商品目录/DPA）🌐 💎 _By [@brandu-mos](https://github.com/brandu-mos)_

### <a id="reviews-reputation"></a>⭐ 6. 评论与口碑 / Reviews & Reputation

> 抓评、差评分析、合规索评、QA 起草、品牌舆情监控。

#### 🅰️ Amazon
* [voc-amazon-reviews](https://github.com/mguozhen/voc-amazon-reviews) - 亚马逊 10 站点评论 VOC 分析 MCP，输出中英双语建议 🅰️ 🇨🇳 💎 _By [@mguozhen](https://github.com/mguozhen)_

### <a id="customer-service"></a>💬 7. 客服与售后 / Customer Service

> 邮件、站内信、退款、A-to-Z 申诉、纠纷处理、多语言客服。

_暂无合格收录。**此分类目前开源生态稀缺**——欢迎贡献：Amazon Buyer Message / Rakuten R-Mail / Shopify Customer Service 等场景。_

### <a id="orders-fulfillment"></a>📦 8. 订单与物流 / Orders & Fulfillment

> FBA、海外仓、头程、FNSKU 标签、tracking 监控、多渠道库存。

_暂无合格收录。**此分类目前开源生态稀缺**——欢迎贡献：4PX / 燕文 / 递四方 / 出海尾程（UPS/USPS/DPD）API 包装、FBA 货件助手等。_

### <a id="finance-compliance"></a>💰 9. 财务与合规 / Finance & Compliance

> 利润核算、汇率、VAT、EPR、payout 对账、品牌注册、商品合规。

#### 🌐 独立站
* [agent-toolkit](https://github.com/stripe/agent-toolkit) - Stripe 官方 Agent Toolkit + 远程/本地 MCP Server 🌐 🆓 ⭐ _By [@stripe](https://github.com/stripe)_

### <a id="collaboration-sop"></a>🤝 10. 团队协作与 SOP / Collaboration & SOP

> 飞书 / 钉钉 / Notion、周会纪要、新人 SOP、跨时区 standup、OKR。

#### 🌐 独立站 / 通用协作
* [mcp-google-sheets](https://github.com/xing5/mcp-google-sheets) - Google Sheets MCP，19 个工具（含图表生成）🌐 🆓 ⭐ _By [@xing5](https://github.com/xing5)_

### <a id="platform-ops"></a>🧰 11. 平台运维 / Platform Operations

> 账号健康、二审、视频验证、Section 3 申诉、多账号关联自查。

#### 🛍️ Shopify
* [shopify-mcp](https://github.com/GeLi2001/shopify-mcp) - Shopify GraphQL Admin API MCP，31 个工具 🛍️ 🆓 _By [@GeLi2001](https://github.com/GeLi2001)_

#### 🟦 通用
* [webapp-testing](https://github.com/anthropics/skills/tree/main/skills/webapp-testing) - 官方 Playwright Skill，自动化检查 Listing/结账流程 🟦 🆓 🅐 _By [@anthropics](https://github.com/anthropics)_

### <a id="general-foundation"></a>🛠️ 12. 通用底座 / General Foundation

> 电商场景下可二次包装的通用 skill（搜索、研究、文档、表格、PPT、可视化、爬虫等）。

#### 🟦 通用
* [firecrawl-mcp-server](https://github.com/firecrawl/firecrawl-mcp-server) - Firecrawl 官方 MCP，scrape / crawl / extract / search 全栈 🟦 💎 ⭐ _By [@firecrawl](https://github.com/firecrawl)_
* [brightdata-mcp](https://github.com/luminati-io/brightdata-mcp) - Bright Data MCP，60+ 站点结构化抓取 + 浏览器自动化 🟦 💎 ⭐ _By [@luminati-io](https://github.com/luminati-io)_
* [tavily-mcp](https://github.com/tavily-ai/tavily-mcp) - Tavily 网搜 MCP，含 search / extract / crawl / map 🟦 💎 ⭐ _By [@tavily-ai](https://github.com/tavily-ai)_
* [actors-mcp-server](https://github.com/apify/actors-mcp-server) - Apify Actor 商店 MCP，动态调用 5000+ 爬虫 🟦 💎 ⭐ _By [@apify](https://github.com/apify)_
* [skill-creator](https://github.com/anthropics/skills/tree/main/skills/skill-creator) - Anthropic 官方 Skill 创建器，输出规范 SKILL.md 🟦 🆓 🅐 _By [@anthropics](https://github.com/anthropics)_

---

## 🎓 上手指南

### 新手路径
1. 读官方 [Skills 文档](https://docs.claude.com/en/docs/claude-code/skills) 了解概念
2. 从「🛠️ 通用底座」分类挑 1 个 skill 装上跑一遍（推荐 [`skill-creator`](https://github.com/anthropics/skills/tree/main/skills/skill-creator) 或 [`tavily-mcp`](https://github.com/tavily-ai/tavily-mcp)）
3. 再按你主营平台从对应分类挑 skill

### 进阶路径
- 自己写 skill 投稿 → 参考 [`docs/how-to-skillify.md`](./docs/how-to-skillify.md)（v1 待补）
- 用 Anthropic Cookbooks 学 agent 编排
- 关注 [`anthropics/skills`](https://github.com/anthropics/skills) release

### 团队部署
- 给整团队配 Claude Code Enterprise + 私有 plugin marketplace
- SOP 沉淀到飞书 / Notion 后用 Skill 形式分发

---

## 🏗️ 创作你自己的 Skill

最小 Skill 包含一个 `SKILL.md` 文件，前缀 YAML frontmatter：

```markdown
---
name: my-amazon-helper
description: 用于 [具体任务] 的 skill；当用户提到 [触发关键词] 时使用
---

# 任务流程
1. ...
2. ...
```

进阶模板见官方 [`anthropics/skills`](https://github.com/anthropics/skills) 与 [`skill-creator`](https://github.com/anthropics/skills/tree/main/skill-creator)。

详细教程：`docs/how-to-skillify.md`（v1 补）。

---

## 🤝 贡献指南

详见 [CONTRIBUTING.md](./CONTRIBUTING.md)。

**5 步快速贡献**：
1. Fork → 找对应一级分类的 H3
2. 复制 [`SKILLS_TEMPLATE.md`](./SKILLS_TEMPLATE.md) 的 bullet 模板
3. 按"中文友好优先 + stars 降序"插入正确位置
4. 填好 PR 模板（电商使用案例必填）
5. 提交 PR

**收录硬门槛**：公开 GitHub repo + 兼容 license + 含 `SKILL.md` 或同类清单 + README ≥200 字 + 近 6 个月有 commit + 跨境电商落点。

---

## 🔗 资源

### 官方
- [Anthropic Skills 官方文档](https://docs.claude.com/en/docs/claude-code/skills)
- [`anthropics/skills`](https://github.com/anthropics/skills) — 官方 skill 主仓库
- [`anthropics/claude-cookbooks`](https://github.com/anthropics/claude-cookbooks) — agent 实践案例
- [Model Context Protocol (MCP) 规范](https://modelcontextprotocol.io)

### 同类 Awesome-list
- [`ComposioHQ/awesome-claude-skills`](https://github.com/ComposioHQ/awesome-claude-skills) — 通用 skill 大合集
- [`punkpeye/awesome-mcp-servers`](https://github.com/punkpeye/awesome-mcp-servers) — MCP 服务端集合

### 中文社区
- 公众号：宝玉xp、歸藏的 AI 工具箱、AI 出海周报
- 即刻圈子：AI 探索站、跨境电商人
- B 站：AI 出海、跨境老炮等 UP 主
- 知识星球：AI 跨境（按需搜索）

### 跨境电商工具生态
- [Helium 10](https://www.helium10.com/) / [Jungle Scout](https://www.junglescout.com/) / [Sellersprite 卖家精灵](https://www.sellersprite.com/) — 商业选品工具（对比参考）
- [Tavily AI](https://tavily.com) / [Bright Data](https://brightdata.com/) — LLM 友好搜索/爬虫服务

---

## 💬 加入社区

- 提 issue：[新 Skill 推荐](https://github.com/<你的用户名>/awesome-ec-skills/issues/new/choose)
- 讨论：开启 GitHub Discussions 后链接补充
- 联系维护者：通过 issue / PR

---

## 📜 License

本仓库内容（README、CONTRIBUTING、模板等文档）按 [CC0-1.0](./LICENSE) 释出到公共领域。
被收录的每个 skill 自身 license 以其原仓库声明为准。

---

> ⭐ 如果这个仓库对你有帮助，欢迎 star。也欢迎 [PR](./CONTRIBUTING.md) 贡献你发现的好 skill。
