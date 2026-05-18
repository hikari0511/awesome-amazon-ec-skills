# 贡献指南 / Contributing

感谢你想为 **awesome-ec-skills** 添砖加瓦！本仓库是一个 awesome-list，**只收录推荐链接，不存放 skill 内容**。

## 收录范围

本仓库聚焦 **跨境出海电商 + 供货上游** 场景的 Claude / AI Agent / MCP / Plugin。

✅ **会收录**
- 出海销售平台：Amazon / Rakuten Ichiba / Shopify / TikTok Shop / Temu / SHEIN / eBay / Walmart / Lazada / Shopee / WooCommerce / Magento / 独立站
- 供货上游：1688 / Alibaba.com / Made-in-China.com
- 协作工具（用于电商团队 SOP/数据流）：飞书 / Lark / Notion
- 通用底座（必须能讲清楚电商落点）：tavily-search、deep-research、anthropics/skills 的 xlsx/pdf 等

❌ **不会收录**
- 纯通用 LLM 工具（无电商落点）→ 请投给 [awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills)
- **国内销售平台 skill**：小红书 / 抖音 / 微信公众号 / 视频号 / 淘宝 / 京东 / 拼多多 / 快手 → 本仓库聚焦出海，留给其他 awesome-list
- Hello-world / 教程 demo / blogpost / YouTube 视频（仅收录 GitHub repo 链接）
- **超过 6 个月未更新的项目**（不论 star 数）
- 私有 SaaS（无开源代码且 ≥$99/月）
- 单纯爬虫脚本（未 skillify，缺少 SKILL.md / plugin.json / mcp.json）
- 含未授权数据（cookie / token / 已泄露的 API key）
- 重复造轮子（同平台同功能已有更高星 skill）

## 收录硬门槛

所有候选 skill 必须**同时满足**：

1. **公开 GitHub 仓库**（不收 GitLab/Bitbucket/Gitee 等其他平台，便于读者一键 star）
2. **License 兼容**：CC0 / MIT / Apache-2.0 / BSD（不收 GPL / proprietary / noncommercial-only）
3. 至少含以下文件之一：`SKILL.md` / `plugin.json` / `.mcp.json` / `mcp.json` / `manifest.json`
4. README ≥ 200 字（含安装+用法+示例）
5. **近 6 个月内有 commit 或 release**
6. 能给出至少 1 个跨境电商真实使用场景
7. 与已有条目重复度 < 90%

## 提交流程（5 步）

1. **Fork** 本仓库
2. 在 `README.md` 中找到合适的一级分类（12 选 1）→ 平台子分组（H4）
3. 复制 [`SKILLS_TEMPLATE.md`](./SKILLS_TEMPLATE.md) 的 bullet 模板，按格式填好
4. 按"中文友好优先 → stars 降序"插入到正确位置
5. 提交 PR，勾选模板自检清单

## PR 必填字段

- Skill 名称 / GitHub URL / 作者 GitHub handle
- 拟归入哪个一级分类（12 选 1）
- 适用平台 emoji（≥1）
- **真实电商使用案例**（一段话，例如"我用这个 skill 在 5 分钟内生成了一个日亚母婴类目 listing"）
- 收录前自检清单（全部勾选）

## 时效复检机制

被收录的 skill 若**超过 6 个月未更新**，维护者会自动开 issue @ 原作者。
- 原作者 30 天内回复并承诺维护 → 保留
- 无响应 → 移到 `docs/archive.md` 留档

## 行为准则

请对所有贡献者保持友善与专业。骚扰、人身攻击、广告 spam 行为将被永久封禁。

## 维护者

PR 通常会在 7 天内审核。如 14 天无响应，可在 PR 中 @维护者催办。

## License

本仓库内容（README、CONTRIBUTING 等文档）按 [CC0-1.0](./LICENSE) 释出到公共领域。
被收录的每个 skill 自身 license 以其原仓库声明为准。
