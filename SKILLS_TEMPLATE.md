# Skill 收录模板

复制下方 bullet 行，按格式填好后插入到 `README.md` 对应的一级分类位置下。

## 单行 bullet 格式

```markdown
* [Skill 名称](GitHub URL) — 一句话描述（≤40 字） <元信息 emoji> _By [@author](profile URL)_
```

## 字段填写说明

| 字段 | 必填 | 示例 |
|---|---|---|
| Skill 名称 | ✓ | `voc-amazon-reviews` |
| URL | ✓ | `https://github.com/xxx/voc-amazon-reviews` |
| 描述 | ✓ | `亚马逊 10 站点评论 VOC 分析 MCP` |
| 元信息 emoji | 选填 ≤2 | `🆓` / `💎` / `💰` / `🅐` / `⭐` / `🆕` |
| 作者 | 选填 | `_By [@gg](https://github.com/gg)_` |

## 元信息 emoji（可选，最多 2 个）

| Emoji | 含义 |
|---|---|
| 🆓 | 完全开源免费 |
| 💎 | 开源但需付费 API key（如 Sorftime / SIF / OpenAI / 第三方 SaaS）|
| 💰 | Skill 本身付费（订阅 / 一次性）|
| 🅐 | Anthropic 官方出品 |
| ⭐ | 高星推荐（≥500 stars 或维护者背书）|
| 🆕 | 30 天内新增收录 |

## 示例

```markdown
* [Amazon-ABAkeyword](https://github.com/luotwo/Amazon-ABAkeyword) — 监测 Amazon ABA 爆品关键词并出飞书仪表盘 🆓 _By [@luotwo](https://github.com/luotwo)_
* [tavily-mcp](https://github.com/tavily-ai/tavily-mcp) — 给 Claude 接入高质量 LLM 优化搜索 💎⭐ _By [@tavily-ai](https://github.com/tavily-ai)_
```

## 排序规则

每个一级分类下按 **stars 降序**排序。

## 收录前自检（PR 时必勾）

- [ ] 仓库 public 且 license 兼容（CC0/MIT/Apache/BSD），或作者公开声明开源
- [ ] 含 `SKILL.md` / `plugin.json` / `mcp.json` / `manifest.json` 之一
- [ ] README ≥ 200 字（含安装+用法+示例）
- [ ] **近 6 个月内有 commit 或 release**
- [ ] 在本地实测过（或附截图）
- [ ] 已搜索本仓库，确认无重复
- [ ] 能给出至少 1 个 **Amazon 跨境出海或 1688 供货** 使用场景
- [ ] 不属于 KDP / Kindle 出版生态
- [ ] bullet 行格式严格符合本模板
