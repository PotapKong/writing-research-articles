# Agent Capability Routing

## Purpose

Use this reference when running the skill outside Codex, especially in OpenClaw, Hermes, or other long-running agents. Keep the article workflow stable while swapping implementation tools.

## Capability map

| Capability | Preferred adapter | Fallback |
|------------|-------------------|----------|
| Web discovery | host search tool | browser search |
| Source confirmation | URL open/fetch tool | browser page inspection |
| Authenticated browsing | `chip-relay` persistent CDP profile | host browser tool |
| Screenshots | `chip-relay` + Playwright/Puppeteer/CDP | host browser screenshot tool |
| Deterministic charts | local chart renderer, notebook, spreadsheet, or HTML canvas | table plus chart placeholder |
| Editorial visuals | GPT Image 2 or current OpenAI image model | host image tool |
| DOCX export | host document adapter | local HTML/Markdown handoff |
| Google Docs | host Google Docs connector or browser upload | DOCX file |
| telegra.ph publishing | authenticated browser profile through `chip-relay` | HTML file plus manual publishing notes |

## Runtime rules

1. Detect available capabilities before promising a delivery target.
2. Prefer adapters that preserve source provenance and artifact paths.
3. Never require secrets in the skill repository or chat transcript.
4. Use existing authenticated browser profiles only when the user has already set them up or explicitly completes login in the browser.
5. If a capability is unavailable, finish with the closest durable artifact and explain the missing adapter.

## Adapter contract

Any host agent can implement this skill if it can provide these operations:

```text
search(query) -> results
open(url) -> page text or page handle
browser.open(url) -> tab handle
browser.screenshot(tab, selector_or_viewport) -> image file
image.generate(prompt, optional_inputs) -> image file
document.export(article, assets, target) -> file or URL
publish(target, article, assets) -> public or private URL
```

When these operations have different names in the host, translate the operation rather than changing the article workflow.
