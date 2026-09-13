<p align="center"><a href="README.md">English</a> · <strong>简体中文</strong></p>

<p align="center">
  <a href="https://langsearch.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.png">
      <img src="assets/logo-light.png" alt="LangSearch" width="288">
    </picture>
  </a>
</p>

<h1 align="center">面向 AI Agent 的免费 Web Search API</h1>

<p align="center"><strong>The World Engine for AGI.</strong></p>

<p align="center">
  让你的 Agent 连接互联网。<br>
  查找来源、获取网页正文，为 AI 工作流提供最新信息。
</p>

<p align="center">
  <a href="https://langsearch.com/dashboard"><strong>获取免费 API Key →</strong></a>
  &nbsp;·&nbsp;
  <a href="https://docs.langsearch.com/reference/search-api-guide">文档</a>
  &nbsp;·&nbsp;
  <a href="https://langsearch.com/pricing">免费计划</a>
  &nbsp;·&nbsp;
  <a href="https://docs.langsearch.com/integrations/mcp">MCP</a>
  &nbsp;·&nbsp;
  <a href="https://langsearch.com/install/skill.md">Agent Skill</a>
</p>

<table>
<tr><td>

**✦ AGENT QUICK START**

### 让你的 Agent 连接互联网。

一句提示词，安装 LangSearch Skill。

```text
Read https://langsearch.com/install/skill.md and follow the instructions to install the LangSearch skill for my agent.
```

[获取免费 API Key →](https://langsearch.com/dashboard) · [安装指南 ↗](https://langsearch.com/install/skill.md)

</td></tr>
</table>

---

[核心能力](#为-agent-准备好的网页搜索) · [Benchmark](#benchmark--关键指标) · [免费计划](#每一项-web-search-功能全部免费) · [快速开始](#开始使用) · [参与集成](#为你的项目接入-langsearch)

## 为 Agent 准备好的网页搜索

[LangSearch](https://langsearch.com) 为 AI Agent、编程助手、研究工作流和 RAG 应用提供 Web Search API。发送查询，即可获得包含来源 URL 和搜索片段的结构化结果；也可以请求网页正文，作为模型的上下文。

通过 **API** 直接调用，连接官方 **MCP 服务**，或为你的 Agent 安装 **LangSearch Skill**。直接调用 API 无需安装 LangSearch 专用 SDK。

| 你的需求 | LangSearch 提供的能力 |
| --- | --- |
| 为回答提供来源 | 包含标题和 URL 的搜索结果，便于 Agent 引用 |
| 获取更多上下文 | 网页正文，支持设置每条结果的字符上限 |
| 查找近期信息 | 相对时间窗口、指定日期或日期范围 |
| 控制信息来源 | 包含或排除指定域名 |
| 少量链接或更广泛的搜索 | 每次请求最多 50 条结果 |
| 在现有工具中使用搜索 | 基于 Streamable HTTP 的托管 MCP 服务和可安装的 Agent Skill |

## Benchmark — 关键指标

**免费构建，更相关的上下文，更少的等待。**

![LangSearch、Exa、Tavily 和 Brave 的价格、SimpleQA 准确率与延迟对比](assets/benchmarks.zh-CN.svg)

| 指标 | **LangSearch** | Exa | Tavily | Brave |
| --- | ---: | ---: | ---: | ---: |
| **价格** · 美元 / 每千次请求 ↓ | **$0** | $7 | $8 | $5 |
| **准确率** · SimpleQA 分数 ↑ | **95.37%** | 90.04% | 83.26% | 87.42% |
| **延迟** · 毫秒 ↓ | **100 ms** | 178 ms | 260 ms | 559 ms |

<details>
<summary>数据来源与对比口径 · 2026 年 9 月 13 日</summary>

- **价格：** 使用公开计费单价，不计免费赠送额度、税费或批量折扣。分别为 Exa 标准 Search（最多 10 条结果）、Tavily Basic PAYG（每次搜索 1 credit）和 Brave Search。LangSearch 设有每日额度，$0 不代表无限量。来源：[Exa](https://exa.ai/pricing)、[Tavily](https://docs.tavily.com/documentation/api-credits)、[Brave](https://brave.com/search/api/)。
- **准确率：** SimpleQA 分数由 LangSearch 提供并确认。图表采用完整的 0–100% 刻度。
- **延迟：** LangSearch 的 100 ms 为团队提供，未指定分位数和测试条件。竞对数据来自 [Exa 公布的 P50 对比](https://exa.ai/enterprise)，对应 Exa Instant、Tavily Ultra-Fast 和 Brave Search。这里汇总的是已报告数据，并非统一条件下的对照测试；价格与性能对比采用的产品模式也有所不同。

</details>

## 每一项 Web Search 功能，全部免费

[![Free Plan：$0，全部功能免费，无需信用卡，每日额度于 00:00 UTC 重置](assets/free-plan.zh-CN.svg)](https://langsearch.com/dashboard)

<p align="center"><a href="https://langsearch.com/dashboard"><strong>获取免费 API Key →</strong></a> &nbsp;·&nbsp; <a href="https://langsearch.com/pricing">了解免费计划</a></p>

**$0 · 全部已支持的 Web Search 功能 · 无需信用卡。**

账号设有每日额度，**每天 00:00 UTC 自动重置**。同一账号下的 API Key 共享额度，MCP 使用你的 LangSearch API Key。在 [Dashboard](https://langsearch.com/dashboard) 中可以查看当前用量和下次重置时间。

<details>
<summary><strong>查看 Free Plan 的完整功能</strong></summary>

| 功能 | Free Plan |
| --- | --- |
| 网页搜索 | 免费 |
| 搜索片段 | 免费 |
| 网页正文 | 免费 |
| 正文长度控制 | 免费 |
| 日期与域名过滤 | 免费 |
| 每次请求最多 50 条结果 | 免费 |
| 官方 MCP 接入 | 免费 |
| Agent Skill | 免费 |

</details>

## 开始使用

在 [Dashboard → API keys](https://langsearch.com/dashboard) 中创建 API Key，然后选择接入方式。

### API — 发起第一次搜索

替换 `YOUR_LANGSEARCH_API_KEY`，在终端或服务端执行：

```bash
curl --request POST 'https://api.langsearch.com/v1/web-search' \
  --header 'Authorization: Bearer YOUR_LANGSEARCH_API_KEY' \
  --header 'Content-Type: application/json' \
  --data '{
    "query": "AI Agent 如何使用网页搜索？",
    "count": 5,
    "contents": {
      "text": true
    }
  }'
```

从 **`data.webPages.value`** 读取搜索结果：

| 字段 | 含义 |
| --- | --- |
| `name` | 网页标题 |
| `url` | 来源 URL |
| `text` | 启用正文模式时返回的网页正文 |
| `snippet` | 未启用正文模式时返回的搜索片段 |
| `datePublished` | 发布日期，可能缺失 |

设置 `contents.text: true` 后，返回的 `text` 会替代 `snippet`，默认每条结果最多 **5,000 个字符**。实际正文可能更短或缺失，搜索也可能返回空列表。请保留正文对应的 URL，便于引用来源。

<details>
<summary><strong>Python</strong></summary>

使用 `pip install requests` 安装 HTTP 客户端。

```python
import requests

response = requests.post(
    "https://api.langsearch.com/v1/web-search",
    headers={"Authorization": "Bearer YOUR_LANGSEARCH_API_KEY"},
    json={
        "query": "AI Agent 如何使用网页搜索？",
        "count": 5,
        "contents": {"text": True},
    },
    timeout=30,
)
response.raise_for_status()
payload = response.json()
if str(payload.get("code")) != "200":
    raise RuntimeError(f"Search failed: {payload.get('message', 'Unknown error')}")

for page in payload["data"]["webPages"]["value"]:
    print(page.get("name", ""), page["url"])
    print(page.get("text", ""))
```

</details>

<details>
<summary><strong>JavaScript（Node.js 18+）</strong></summary>

```javascript
const response = await fetch("https://api.langsearch.com/v1/web-search", {
  method: "POST",
  headers: {
    Authorization: "Bearer YOUR_LANGSEARCH_API_KEY",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    query: "AI Agent 如何使用网页搜索？",
    count: 5,
    contents: { text: true },
  }),
  signal: AbortSignal.timeout(30_000),
});

if (!response.ok) throw new Error(`Search failed: HTTP ${response.status}`);
const payload = await response.json();
if (String(payload.code) !== "200") {
  throw new Error(`Search failed: ${payload.message ?? "Unknown error"}`);
}

for (const page of payload.data.webPages.value) {
  console.log(page.name ?? "", page.url);
  console.log(page.text ?? "");
}
```

以 ES 模块（`.mjs` 文件）运行，或放入 async 函数中。

</details>

在可信的本地环境或服务端保存和使用 API Key。不要将真实密钥提交到仓库或放入浏览器端代码。

### MCP — 连接现有工具

在兼容的 MCP 客户端中连接官方托管服务：

| 配置项 | 配置值 |
| --- | --- |
| URL | `https://mcp.langsearch.com/mcp` |
| 传输协议 | Streamable HTTP |
| 鉴权 | `Authorization: Bearer YOUR_LANGSEARCH_API_KEY` |
| 工具名称 | `web_search` |

以 **Cursor** 为例，将以下配置合并到 `.cursor/mcp.json`：

```json
{
  "mcpServers": {
    "langsearch": {
      "url": "https://mcp.langsearch.com/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_LANGSEARCH_API_KEY"
      }
    }
  }
}
```

替换密钥占位符，重新加载连接，然后向 Agent 提问：

> 搜索 AI 编程助手的近期进展，并附上来源链接。

不同客户端的配置格式有所区别。**Codex、Claude Code、Cursor、VS Code、Gemini CLI、OpenCode、Windsurf、Cline、Roo Code 和 Zed** 的接入方法见 [MCP 指南](https://docs.langsearch.com/integrations/mcp)。

### Skill — 让 Agent 帮你完成安装

将以下提示词发送给你的 Agent：

```text
Read https://langsearch.com/install/skill.md and follow the instructions to install the LangSearch skill for my agent.
```

Skill 提供安装和使用说明，Agent 仍然需要你的 LangSearch API Key。[阅读 Skill 指南 →](https://docs.langsearch.com/integrations/skill)

## 控制来源和上下文

在同一个 API 请求中设置日期、域名和正文长度：

```json
{
  "query": "AI Agent 与网页搜索",
  "count": 10,
  "freshness": "oneMonth",
  "includeDomains": ["langsearch.com", "openai.com"],
  "excludeDomains": ["reddit.com"],
  "contents": {
    "text": {
      "max_characters": 3000
    }
  }
}
```

- **结果数量：** `count` 默认为 10，最多为 50。
- **相对时间：** `noLimit`（默认）、`oneDay`、`oneWeek`、`oneMonth` 或 `oneYear`。
- **指定日期：** `2026-09-12`，或包含首尾日期的 UTC 区间，例如 `2026-09-01..2026-09-13`。
- **域名过滤：** 使用 `langsearch.com`、`openai.com` 这样的域名字符串。不设置过滤可扩大搜索范围。
- **正文长度：** `contents.text.max_characters` 必须为正整数。使用对象形式即启用正文模式，无需另设 `true`。
- **仅返回搜索片段：** 不传 `contents`，或将 `contents.text` 设置为 `false`。

[API 参考 →](https://docs.langsearch.com/api/web-search-api) · [搜索最佳实践 →](https://docs.langsearch.com/reference/search-best-practices)

## 用搜索构建你的应用

- **编程助手：** 查找最新文档、迁移指南和技术解释。
- **研究 Agent：** 收集来源、比较证据，并逐步细化后续搜索。
- **RAG 应用：** 将网页上下文与自己的知识库结合。
- **信息监测：** 发现某个主题的近期网页，保留链接供进一步查看。
- **AI 聊天应用：** 基于检索到的来源为用户提供回答。

正在使用编程 Agent 开发？可以将 [Agent 集成指南](https://docs.langsearch.com/reference/search-api-guide-for-coding-agents) 或 [文档索引](https://docs.langsearch.com/llms.txt) 提供给它。

## 为你的项目接入 LangSearch

如果你正在维护 Agent 框架、聊天界面或研究工具，我们希望帮助你的用户更方便地使用网页搜索。

可以开发原生搜索适配器、连接托管 MCP 服务，或加入基于 Skill 的工作流。欢迎提供包含可运行示例、测试和清晰安装说明的贡献。

[提交集成需求](https://github.com/langsearch-ai/langsearch/issues/new)，附上项目链接、目标工作流和扩展接口要求。如果向其他项目贡献代码，请先阅读其贡献规则，并检查是否已有相关工作。

## 文档与支持

- [Web Search 指南](https://docs.langsearch.com/reference/search-api-guide)
- [API 参考](https://docs.langsearch.com/api/web-search-api)
- [MCP 配置](https://docs.langsearch.com/integrations/mcp)
- [Agent Skill](https://docs.langsearch.com/integrations/skill)
- [计划与用量](https://docs.langsearch.com/limits/api-limits)
- [错误与排查](https://docs.langsearch.com/api/errors)
- [反馈问题](https://github.com/langsearch-ai/langsearch/issues)

反馈 API 问题时，请提供请求参数、HTTP 状态码以及可用的 `log_id`，并在发布前移除 API Key 和私密数据。

---

<p align="center"><strong>LangSearch — The World Engine for AGI.</strong></p>
