# Skill 收录模板

复制下方 bullet 行，按格式填好后插入到 `README.md` 对应的"一级分类 → 平台子分组"位置下。

## 单行 bullet 格式

```markdown
* [Skill 名称](GitHub URL) - 一句话中文描述（≤40 字） <平台 emoji> <元信息 emoji> _By [@author](profile URL)_
```

## 字段填写说明

| 字段 | 必填 | 示例 | 说明 |
|---|---|---|---|
| Skill 名称 | ✓ | `amazon-listing-creator` | 用原仓库名 / 项目名，保留作者命名 |
| URL | ✓ | `https://github.com/xxx/amazon-listing-creator` | 优先直链子目录或 `SKILL.md` |
| 描述 | ✓ | `亚马逊 Listing 全流程文案与主图 prompt 生成` | 中文，≤40 字，**句末不加句号** |
| 平台 emoji | ✓ ≥1 | `🅰️` | 见下方平台表 |
| 元信息 emoji | 选填 ≤2 | `🇨🇳 🆓` | 见下方元信息表 |
| 作者 | 选填 | `_By [@gg](https://github.com/gg)_` | 第三方 skill 必填，官方/匿名可省 |

## 平台 emoji（每条 skill ≥1 个）

| Emoji | 平台 | 类型 |
|---|---|---|
| 🅰️ | Amazon（全站点） | 出海销售 |
| 🅡 | Rakuten Ichiba | 出海销售 |
| 🛍️ | Shopify | 出海销售 |
| 🎵 | TikTok Shop | 出海销售 |
| 🟢 | Temu | 出海销售 |
| 👗 | SHEIN | 出海销售 |
| 🏪 | 其他第三方（eBay/Walmart/Lazada/Shopee） | 出海销售 |
| 🌐 | 独立站（WooCommerce/Magento/自建） | 出海销售 |
| 🛒 | 1688/Alibaba/Made-in-China | 供货上游 |
| 🪶 | 飞书生态 | 内部协作 |
| 🟦 | 通用（跨平台适用） | 跨平台 |

> 国内销售平台（小红书/抖音/微信/视频号/淘宝/京东/拼多多）暂**不收录**。

## 元信息 emoji（可选，最多 2 个）

| Emoji | 含义 |
|---|---|
| 🇨🇳 | 中文友好（README/示例/prompt 是中文，或对中文用户输入友好） |
| 🆓 | 完全开源免费 |
| 💎 | 开源但需付费 API key（如 OpenAI / 第三方 SaaS） |
| 💰 | Skill 本身付费（订阅 / 一次性） |
| 🅐 | Anthropic 官方出品 |
| ⭐ | 高星推荐（≥500 stars 或维护者背书） |
| 🆕 | 30 天内新增收录 |

> 建议起步只用"平台 + 付费"2 维（必选）。`🇨🇳` / `⭐` / `🆕` / `🅐` 为可选标识。

## 示例

```markdown
### 🔍 选品调研 / Product Research

#### Amazon
* [amazon-bsr-tracker](https://github.com/example/amazon-bsr-tracker) - 抓取 Amazon BSR 历史趋势并输出蓝海机会词 🅰️ 🇨🇳 🆓 _By [@example](https://github.com/example)_

#### Rakuten
* [rakuten-blue-ocean](https://github.com/example/rakuten-blue-ocean) - 基于乐天排行榜与 review 反推蓝海类目 🅡 🆓 _By [@example](https://github.com/example)_

### 🛠️ 通用底座 / General Foundation
* [tavily-search](https://github.com/tavily-ai/tavily-mcp) - 给 Claude 接入高质量 LLM 优化搜索的官方 skill 🟦 💎 ⭐ _By [@tavily-ai](https://github.com/tavily-ai)_
```

## 排序规则

每个一级分类下：
1. 先按平台 emoji 分子分组（H4 标题）
2. 同一平台内按"中文友好优先 → stars 降序"排
3. 通用底座统一放在所有一级分类之后

## 收录前自检（PR 时必勾）

- [ ] 仓库 public 且 license 兼容（CC0/MIT/Apache/BSD）
- [ ] 含 `SKILL.md` / `plugin.json` / `mcp.json` / `manifest.json` 之一
- [ ] README ≥ 200 字（含安装+用法+示例）
- [ ] **近 6 个月内有 commit 或 release**
- [ ] 在本地实测过（或附截图）
- [ ] 已搜索本仓库，确认无重复
- [ ] 能给出至少 1 个跨境电商使用场景
- [ ] bullet 行格式严格符合本模板
