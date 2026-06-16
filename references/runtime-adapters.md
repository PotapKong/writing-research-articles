# Runtime Adapters: Codex, Claude Code, Hermes

## Purpose

Use this reference to run the same article workflow across different coding
agents without changing the editorial standard. The agent should detect
capabilities first, then choose the best available adapter.

## Required capability contract

At minimum, a complete production article workflow needs:

```text
search(query) -> result list
open(url) -> page text, source metadata, or page handle
browser.open(url) -> tab/page handle
browser.screenshot(target) -> image file path
data.extract(source) -> table or structured values
chart.render(data, spec) -> image file path
image.generate(prompt, inputs) -> image file path
document.export(article, assets, "docx" | "pdf" | "html") -> file path
```

If one operation is unavailable, use the closest durable fallback and state the
gap in Source Notes.

## Codex

Typical mapping:

| Need | Prefer | Fallback |
|------|--------|----------|
| Web discovery | built-in web search/open tools | browser search |
| Local/browser screenshots | Browser plugin, Playwright, or available browser tool | screenshot placeholder with exact URL/selector |
| Image generation | configured image generation tool, GPT Image 2 if exposed | deterministic diagram/table placeholder |
| DOCX | Documents skill/tooling when available | HTML/Markdown handoff |
| PDF | PDF skill/tooling or DOCX-to-PDF export when available | HTML print-ready file |

Codex-specific rule: after editing or generating a local artifact, verify it
with real file checks and visual rendering when practical.

## Claude Code

Typical mapping:

| Need | Prefer | Fallback |
|------|--------|----------|
| Web discovery | Claude Code web/search tools if enabled | browser/manual source list |
| Screenshots | Playwright/Puppeteer through local browser or MCP browser tools | browser-capture placeholder |
| Image generation | configured image MCP/tool or GPT Image 2 adapter if installed | deterministic chart/diagram renderer |
| DOCX/PDF | local scripts, document tools, or repository export pipeline | HTML/Markdown handoff |

Claude Code-specific rule: use named agents only when they exist. A writer
agent can own the article, a researcher can own Fact Grid/source discovery, and
a verifier can own final source and artifact checks.

## Hermes / OpenClaw / long-running agents

Typical mapping:

| Need | Prefer | Fallback |
|------|--------|----------|
| Web discovery | host search/open adapters | browser search |
| Authenticated browser | `chip-relay` persistent CDP profile | host browser profile |
| Screenshots | `chip-relay` + Playwright/Puppeteer/CDP | host screenshot tool |
| GPT Image 2 | configured OpenAI image backend | other configured image backend |
| DOCX/PDF | host document/export adapter | local HTML/Markdown artifact |

Hermes-specific rule: keep paths and artifact names explicit because outputs may
be consumed by other automation, Telegram bots, n8n flows, or publication jobs.

## Asset manifest

For every non-text asset, record:

| Field | Meaning |
|-------|---------|
| `asset_id` | stable ID, e.g. `fig-01` |
| `type` | screenshot, chart, diagram, generated cover, table, source image |
| `path_or_url` | local file path or public URL |
| `source_url` | original evidence URL, if any |
| `source_date` | publication or document date |
| `created_at` | capture/render/generation date |
| `provenance` | evidence screenshot, deterministic rendering, generated from verified data, or illustrative |
| `caption` | publication-ready caption |
| `verification` | what was checked: labels, values, crop, privacy, source match |

## Hard rules

1. Do not promise DOCX, PDF, Google Docs, screenshots, or image generation until
   the runtime capability is confirmed.
2. Prefer source screenshots for existing tables, charts, and news evidence.
3. Prefer deterministic chart rendering for exact numeric charts.
4. Use GPT Image 2 or another image model for diagrams, covers, and polished
   publication graphics only with verified data and explicit labels.
5. Never let a generated image introduce a new fact.
6. Final delivery should include the article file path, asset manifest, source
   recency note, and any unverified or unavailable step.
