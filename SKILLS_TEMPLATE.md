# Skill 收录模板

复制下方 bullet 行，按格式填好后插入到 `README.md` 对应的一级分类位置下。

## 单行 bullet 格式

```markdown
* [Skill 名称](GitHub URL) — 一句话中文描述（≤40 字）<标签 emoji><元信息 emoji> _By [@author](profile URL)_
```

## 字段填写说明

| 字段 | 必填 | 示例 | 说明 |
|---|---|---|---|
| Skill 名称 | ✓ | `voc-amazon-reviews` | 用原仓库名 / 项目名 |
| URL | ✓ | `https://github.com/xxx/voc-amazon-reviews` | 优先直链子目录或 `SKILL.md` |
| 描述 | ✓ | `亚马逊 10 站点评论 VOC 分析 MCP` | 中文，≤40 字，**句末不加句号** |
| 标签 emoji | ✓ ≥1 | `🅰️` | 见下方标签表 |
| 元信息 emoji | 选填 ≤2 | `🇨🇳🆓` | 见下方元信息表 |
| 作者 | 选填 | `_By [@gg](https://github.com/gg)_` | 第三方 skill 必填，官方/匿名可省 |

> **emoji 紧凑书写**：标签与元信息 emoji 之间**不空格**，让视觉更紧凑（如 `🅰️🇨🇳🆓`，不要 `🅰️ 🇨🇳 🆓`）。

## 标签 emoji（每条 skill ≥1 个）

| Emoji | 含义 |
|---|---|
| 🅰️ | **Amazon**（全站点）—— 直接服务 Amazon 的 skill |
| 🛒 | **1688/Alibaba/Made-in-China** —— 供货上游 |
| 🪶 | **飞书** —— 用飞书做 Amazon 数据落地 / 团队 SOP |
| 🟦 | **通用底座** —— 跨场景通用工具（搜索/抓取/表格等），需能讲清 Amazon 场景落点 |

> 本仓库**仅收录** Amazon + 1688/供货上游 相关 skill。其他出海平台（Rakuten / Shopify / TikTok Shop / Temu / SHEIN / eBay / Walmart / Lazada / Shopee / 独立站）与国内销售平台（小红书 / 抖音 / 微信 / 视频号 / 淘宝 / 京东 / 拼多多）**不收录**。

## 元信息 emoji（可选，最多 2 个）

| Emoji | 含义 |
|---|---|
| 🇨🇳 | 中文友好（README/示例/prompt 是中文，或对中文用户输入友好）|
| 🆓 | 完全开源免费 |
| 💎 | 开源但需付费 API key（如 Sorftime / SIF / OpenAI / 第三方 SaaS）|
| 💰 | Skill 本身付费（订阅 / 一次性）|
| 🅐 | Anthropic 官方出品 |
| ⭐ | 高星推荐（≥500 stars 或维护者背书）|
| 🆕 | 30 天内新增收录 |

> 建议起步只用"标签 + 付费"2 维（必选）。`🇨🇳` / `⭐` / `🆕` / `🅐` 为可选标识。

## 示例

```markdown
### 🔍 选品调研

* [Amazon-ABAkeyword](https://github.com/luotwo/Amazon-ABAkeyword) — 监测 Amazon ABA 爆品关键词并出飞书仪表盘 🅰️🪶🇨🇳🆓 _By [@luotwo](https://github.com/luotwo)_
* [zach-product-research](https://github.com/zach22-1999/amazon-skills/tree/main/skills/zach-product-research) — Sorftime MCP 选品分析交付四件套 🅰️🇨🇳💎 _By [@zach22-1999](https://github.com/zach22-1999)_

### 🛠️ 通用底座

* [tavily-mcp](https://github.com/tavily-ai/tavily-mcp) — 给 Claude 接入高质量 LLM 优化搜索 🟦💎⭐ _By [@tavily-ai](https://github.com/tavily-ai)_
```

## 排序规则

每个一级分类下：
1. 按"中文友好（🇨🇳）优先 → stars 降序"排
2. 通用底座统一放在最后一个一级分类

## 收录前自检（PR 时必勾）

- [ ] 仓库 public 且 license 兼容（CC0/MIT/Apache/BSD）
- [ ] 含 `SKILL.md` / `plugin.json` / `mcp.json` / `manifest.json` 之一
- [ ] README ≥ 200 字（含安装+用法+示例）
- [ ] **近 6 个月内有 commit 或 release**
- [ ] 在本地实测过（或附截图）
- [ ] 已搜索本仓库，确认无重复
- [ ] 能给出至少 1 个 **Amazon 跨境出海或 1688 供货** 使用场景
- [ ] 不属于 KDP / Kindle 出版生态
- [ ] bullet 行格式严格符合本模板
