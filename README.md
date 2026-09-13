<p align="center"><strong>English</strong> · <a href="README.zh-CN.md">简体中文</a></p>

<p align="center">
  <a href="https://langsearch.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.png">
      <img src="assets/logo-light.png" alt="LangSearch" width="288">
    </picture>
  </a>
</p>

<h1 align="center">Free Web Search API for AI Agents</h1>

<p align="center"><strong>The World Engine for AGI.</strong></p>

<p align="center">
  Give your agents access to the web.<br>
  Find sources, retrieve webpage text, and bring current information into your AI workflows.
</p>

<p align="center">
  <a href="https://langsearch.com/dashboard"><strong>Get your free API key →</strong></a>
  &nbsp;·&nbsp;
  <a href="https://docs.langsearch.com/reference/search-api-guide">Documentation</a>
  &nbsp;·&nbsp;
  <a href="https://langsearch.com/pricing">Free Plan</a>
  &nbsp;·&nbsp;
  <a href="https://docs.langsearch.com/integrations/mcp">MCP</a>
  &nbsp;·&nbsp;
  <a href="https://langsearch.com/install/skill.md">Agent Skill</a>
</p>

<table>
<tr><td>

**✦ AGENT QUICK START**

### Give your agent the web.

One prompt to install the LangSearch Skill.

```text
Read https://langsearch.com/install/skill.md and follow the instructions to install the LangSearch skill for my agent.
```

[Get your free API key →](https://langsearch.com/dashboard) · [Installation guide ↗](https://langsearch.com/install/skill.md)

</td></tr>
</table>

---

[Features](#the-web-ready-for-your-agent) · [Benchmarks](#benchmarks--compare-the-essentials) · [Free Plan](#every-web-search-feature-free) · [Quick start](#get-started) · [Integrations](#bring-langsearch-to-your-project)

## The web, ready for your agent

[LangSearch](https://langsearch.com) is a Web Search API for AI agents, coding assistants, research workflows, and RAG applications. Send a query and receive structured results with source URLs and snippets—or request full webpage text for your model's context.

Connect through the **API**, use the official **MCP server**, or give your agent the **LangSearch Skill**. No LangSearch-specific SDK is required for direct API access.

| What you need | What LangSearch provides |
| --- | --- |
| Sources for an answer | Search results with titles and URLs your agent can cite |
| More context | Full webpage text with a configurable character limit per result |
| Recent information | Relative time windows, a specific date, or a date range |
| Control over sources | Include or exclude domains |
| A few links or a broader search | Up to 50 results per request |
| Search in your existing tools | Hosted MCP over Streamable HTTP and an installable Agent Skill |

## Benchmarks — compare the essentials

**Free to build. Relevant context. Less waiting.**

![Price, SimpleQA accuracy, and latency comparison for LangSearch, Exa, Tavily, and Brave](assets/benchmarks.svg)

| Metric | **LangSearch** | Exa | Tavily | Brave |
| --- | ---: | ---: | ---: | ---: |
| **Price** · USD / 1,000 requests ↓ | **$0** | $7 | $8 | $5 |
| **Accuracy** · SimpleQA score ↑ | **95.37%** | 90.04% | 83.26% | 87.42% |
| **Latency** · milliseconds ↓ | **100 ms** | 178 ms | 260 ms | 559 ms |

<details>
<summary>Sources and comparison conditions · September 13, 2026</summary>

- **Price:** published usage rates before free credits, taxes, or volume discounts. Exa standard Search (up to 10 results), Tavily Basic PAYG (one credit per search), and Brave Search. LangSearch has a daily allowance; $0 does not mean unlimited usage. Sources: [Exa](https://exa.ai/pricing), [Tavily](https://docs.tavily.com/documentation/api-credits), [Brave](https://brave.com/search/api/).
- **Accuracy:** SimpleQA scores supplied and confirmed by LangSearch. The chart uses the full 0–100% scale.
- **Latency:** LangSearch's 100 ms is team-reported; percentile and test conditions are not specified. Competitor figures are [Exa-reported P50](https://exa.ai/enterprise) for Exa Instant, Tavily Ultra-Fast, and Brave Search. These reported figures are not a controlled, like-for-like measurement; pricing modes differ from performance modes.

</details>

## Every Web Search feature. Free.

[![Free Plan: $0, all features included, no credit card required. Daily allowance resets at 00:00 UTC.](assets/free-plan.svg)](https://langsearch.com/dashboard)

<p align="center"><a href="https://langsearch.com/dashboard"><strong>Get your free API key →</strong></a> &nbsp;·&nbsp; <a href="https://langsearch.com/pricing">Explore the Free Plan</a></p>

**$0 · Every supported Web Search feature · No credit card required.**

Your account has a daily allowance that **automatically resets at 00:00 UTC**. API keys on the same account share that allowance; MCP uses your LangSearch API key. View current usage and the next reset in your [Dashboard](https://langsearch.com/dashboard).

<details>
<summary><strong>See everything included in the Free Plan</strong></summary>

| Feature | Free Plan |
| --- | --- |
| Web search | Free |
| Search snippets | Free |
| Full webpage text | Free |
| Text length control | Free |
| Date and domain filters | Free |
| Up to 50 results per request | Free |
| Official MCP access | Free |
| Agent Skill | Free |

</details>

## Get started

Create a key in [Dashboard → API keys](https://langsearch.com/dashboard), then choose how you want to connect.

### API — make your first search

Replace `YOUR_LANGSEARCH_API_KEY` and run this from your terminal or server:

```bash
curl --request POST 'https://api.langsearch.com/v1/web-search' \
  --header 'Authorization: Bearer YOUR_LANGSEARCH_API_KEY' \
  --header 'Content-Type: application/json' \
  --data '{
    "query": "How do AI agents use web search?",
    "count": 5,
    "contents": {
      "text": true
    }
  }'
```

Read results from **`data.webPages.value`**:

| Field | Meaning |
| --- | --- |
| `name` | Page title |
| `url` | Source URL |
| `text` | Webpage text when text mode is enabled |
| `snippet` | Search snippet when text mode is not enabled |
| `datePublished` | Publication date, when available |

With `contents.text: true`, `text` replaces `snippet` and is limited to **5,000 characters per result** by default. Available text may be shorter or missing, and a search can return an empty result list. Keep source URLs alongside the text for citations.

<details>
<summary><strong>Python</strong></summary>

Install the HTTP client with `pip install requests`.

```python
import requests

response = requests.post(
    "https://api.langsearch.com/v1/web-search",
    headers={"Authorization": "Bearer YOUR_LANGSEARCH_API_KEY"},
    json={
        "query": "How do AI agents use web search?",
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
<summary><strong>JavaScript (Node.js 18+)</strong></summary>

```javascript
const response = await fetch("https://api.langsearch.com/v1/web-search", {
  method: "POST",
  headers: {
    Authorization: "Bearer YOUR_LANGSEARCH_API_KEY",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    query: "How do AI agents use web search?",
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

Run as an ES module (`.mjs`) or inside an async function.

</details>

Keep your API key in a trusted local or server environment. Do not commit real keys or include them in browser code.

### MCP — connect your tools

Use the official hosted server with compatible MCP clients:

| Setting | Value |
| --- | --- |
| URL | `https://mcp.langsearch.com/mcp` |
| Transport | Streamable HTTP |
| Authentication | `Authorization: Bearer YOUR_LANGSEARCH_API_KEY` |
| Tool | `web_search` |

For **Cursor**, merge this into `.cursor/mcp.json`:

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

Replace the placeholder, reload the connection, and ask your agent:

> Search the web for recent developments in AI coding agents and include source links.

Client configuration formats differ. Find setup instructions for **Codex, Claude Code, Cursor, VS Code, Gemini CLI, OpenCode, Windsurf, Cline, Roo Code, and Zed** in the [MCP guide](https://docs.langsearch.com/integrations/mcp).

### Skill — let your agent handle setup

Paste this prompt into your agent:

```text
Read https://langsearch.com/install/skill.md and follow the instructions to install the LangSearch skill for my agent.
```

The Skill supplies installation and usage instructions; your agent still needs a LangSearch API key. [Read the Skill guide →](https://docs.langsearch.com/integrations/skill)

## Choose your sources and context

Use the same API endpoint with date filters, domain filters, and a text budget:

```json
{
  "query": "AI agents and web search",
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

- **Result count:** `count` defaults to 10; the maximum is 50.
- **Relative dates:** `noLimit` (default), `oneDay`, `oneWeek`, `oneMonth`, or `oneYear`.
- **Exact dates:** `2026-09-12`, or an inclusive UTC range such as `2026-09-01..2026-09-13`.
- **Domains:** use domain strings, such as `langsearch.com` and `openai.com`. Omit the filters for a broader search.
- **Text budget:** `contents.text.max_characters` must be a positive integer. The object enables text mode itself; no separate `true` flag is needed.
- **Snippets only:** omit `contents`, or set `contents.text` to `false`.

[API reference →](https://docs.langsearch.com/api/web-search-api) · [Search best practices →](https://docs.langsearch.com/reference/search-best-practices)

## Build with search

- **Coding assistants:** find current documentation, migration guides, and technical explanations.
- **Research agents:** gather sources, compare evidence, and refine follow-up searches.
- **RAG applications:** add web context alongside your own knowledge base.
- **Monitoring workflows:** discover recent pages about a topic and retain links for review.
- **AI chat applications:** give users answers informed by retrieved sources.

Building with a coding agent? Share our [agent integration guide](https://docs.langsearch.com/reference/search-api-guide-for-coding-agents) or [documentation index](https://docs.langsearch.com/llms.txt).

## Bring LangSearch to your project

Maintaining an agent framework, chat interface, or research tool? We'd love to help make Web Search easier for your users.

You can build a native search provider, connect the hosted MCP server, or add a Skill-based workflow. Contributions that include working examples, tests, and clear setup instructions are welcome.

[Open an integration request](https://github.com/langsearch-ai/langsearch/issues/new) with your project link, the intended workflow, and its extension requirements. If you're contributing to another project, follow its contribution process and check for existing work first.

## Documentation and support

- [Web Search guide](https://docs.langsearch.com/reference/search-api-guide)
- [API reference](https://docs.langsearch.com/api/web-search-api)
- [MCP setup](https://docs.langsearch.com/integrations/mcp)
- [Agent Skill](https://docs.langsearch.com/integrations/skill)
- [Plan and usage](https://docs.langsearch.com/limits/api-limits)
- [Errors and troubleshooting](https://docs.langsearch.com/api/errors)
- [Report an issue](https://github.com/langsearch-ai/langsearch/issues)

For API issues, include the request parameters, HTTP status, and `log_id` when available. Remove API keys and private data before posting.

---

<p align="center"><strong>LangSearch — The World Engine for AGI.</strong></p>
