# writing-research-articles

A portable agent skill for verified web research, fact-based article writing, visual evidence capture, document export, and publishing.

## What it does

Conducts deep web research, builds a visible **Fact Grid** with confidence levels, writes a professional article with inline citations and a hyperlink map, then delivers the result as Markdown, HTML, JSON, DOCX, Google Docs, or a published telegra.ph/Telegraph-style page when the host agent has the required adapters.

## When to use

- Deep research on any topic
- Fact-based article writing (analytical, explanatory, comparative, news)
- Investment analysis and market notes
- Geopolitical longreads
- Telegraph-style HTML publications
- Source verification and fact-checking
- Publication-ready longform content in Markdown, HTML, or JSON
- Browser screenshot capture through `chip-relay` or a host browser adapter
- Host-native image generation for diagrams, editorial visuals, and cover images
- DOCX, Google Docs, and telegra.ph publishing workflows

## Install

Copy or clone this repository into your Codex skills directory:

```powershell
git clone https://github.com/PotapKong/writing-research-articles "$env:USERPROFILE\.codex\skills\writing-research-articles"
```

Then invoke it as `$writing-research-articles` or ask your agent for a verified research article.

For OpenClaw, Hermes, or other agents, install the folder in the runtime's skills directory and map host tools to the capability contract in `references/agent-capabilities.md`.

## Workflow (10 steps)

1. Parse brief and build research question set
2. Search the web across all research tracks
3. Open primary source URLs to confirm key claims
4. Verify freshness and reliability
5. Build Fact Grid
6. Draft article from verified grid only
7. Editorial cleanup pass
8. Pre-publication fact re-check
9. Replace visual placeholders with screenshots, charts, diagrams, or generation notes
10. Export or publish in the requested target

## Output formats

- **HTML Artifact** — for Telegraph, landing pages, dark theme editorial
- **JSON** — for n8n, automation pipelines, structured output
- **DOCX / Google Docs** — for editorial handoff
- **telegra.ph / published page** — when explicitly requested and authenticated tooling is available
- **Markdown** — default

## Optional adapters

- `chip-relay` for persistent CDP browser sessions, screenshots, authenticated capture, and publishing
- The host agent's configured image backend for diagrams, cover visuals, and non-numeric editorial graphics
- Document adapters for DOCX and Google Docs export

## Files

| File | Contents |
|------|----------|
| `SKILL.md` | Main skill definition and workflow |
| `agents/openai.yaml` | Codex UI metadata |
| `references/` | Source hierarchy, style, article structure, citations, formats, visuals, browser capture, publishing, examples |
