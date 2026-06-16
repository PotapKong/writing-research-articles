# Agent Capability Routing

## Purpose

Use this reference when running the skill in Codex, Claude Code, Hermes,
OpenClaw, or another agent runtime. Keep the article workflow stable while
swapping implementation tools. For runtime-specific mappings, see
[runtime-adapters.md](runtime-adapters.md).

## Capability map

| Capability | Preferred adapter | Fallback |
|------------|-------------------|----------|
| Web discovery | host search tool | browser search |
| Source confirmation | URL open/fetch tool | browser page inspection |
| Authenticated browsing | `chip-relay` persistent CDP profile | host browser tool |
| Screenshots | `chip-relay` + Playwright/Puppeteer/CDP | host browser screenshot tool |
| Source table/chart extraction | source PDF/HTML table parser, spreadsheet, or manual verified extraction | screenshot plus table placeholder |
| Deterministic charts | local chart renderer, notebook, spreadsheet, or HTML canvas | table plus chart placeholder |
| GPT Image 2 visuals | configured GPT Image 2 adapter | other host-configured image backend |
| Editorial visuals | host-configured image backend | ask owner preference or use text placeholder |
| DOCX export | host document adapter | local HTML/Markdown handoff |
| PDF export | host PDF/document adapter or DOCX-to-PDF export | print-ready HTML |
| Google Docs | host Google Docs connector or browser upload | DOCX file |
| telegra.ph publishing | authenticated browser profile through `chip-relay` | HTML file plus manual publishing notes |

## Runtime rules

1. Detect available capabilities before promising a delivery target.
2. Prefer adapters that preserve source provenance and artifact paths.
3. Never require secrets in the skill repository or chat transcript.
4. Use existing authenticated browser profiles only when the user has already set them up or explicitly completes login in the browser.
5. If a capability is unavailable, finish with the closest durable artifact and explain the missing adapter.
6. For image generation, use the runtime's configured backend. Prefer GPT Image
   2 when the owner has configured it and the task needs polished diagrams,
   covers, or verified-data publication graphics.
7. For exact numeric charts, prefer deterministic rendering. Use GPT Image 2
   only when exact values are supplied in the prompt and the output is checked
   against the source data before embedding.

## Adapter contract

Any host agent can implement this skill if it can provide these operations:

```text
search(query) -> results
open(url) -> page text or page handle
browser.open(url) -> tab handle
browser.screenshot(tab, selector_or_viewport) -> image file
data.extract(source) -> structured table or values
chart.render(data, chart_spec) -> image file
image.generate(prompt, optional_inputs) -> image file
document.export(article, assets, target: markdown|html|docx|pdf) -> file or URL
publish(target, article, assets) -> public or private URL
```

When these operations have different names in the host, translate the operation rather than changing the article workflow.
