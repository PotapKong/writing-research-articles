# writing-research-articles

A portable agent skill for verified web research, source discovery, fact-based article writing, visual evidence capture, generated visuals, document export, and publishing.

## What it does

Conducts web research, builds a visible **Fact Grid** with confidence levels, discovers authoritative source links when the user wants to choose a topic first, captures evidence screenshots, generates diagrams or verified-data publication graphics through GPT Image 2 or another configured image backend, writes a professional article with inline citations and a hyperlink map, then delivers the result as Markdown, HTML, JSON, DOCX, PDF, Google Docs, or a published telegra.ph/Telegraph-style page when the host agent has the required adapters.

## When to use

- Deep research on any topic
- Fact-based article writing (analytical, explanatory, comparative, news)
- AI, agentic systems, coding agents, automation, and technical explainers
- Western English-language source discovery: authoritative articles, blogs, authors, lab posts, papers, and technical case studies
- Investment analysis and market notes
- Geopolitical longreads
- Telegraph-style HTML publications
- Source verification and fact-checking
- Publication-ready longform content in Markdown, HTML, or JSON
- Browser screenshot capture through `chip-relay` or a host browser adapter
- Host-native image generation, including GPT Image 2 when configured, for diagrams, editorial visuals, verified-data graphics, and cover images
- DOCX, PDF, Google Docs, and telegra.ph publishing workflows
- Codex, Claude Code, Hermes, OpenClaw, or other agents that can map the required capabilities

## Install

Copy or clone this repository into your Codex skills directory:

```powershell
git clone https://github.com/PotapKong/writing-research-articles "$env:USERPROFILE\.codex\skills\writing-research-articles"
```

Then invoke it as `$writing-research-articles` or ask your agent for a verified research article.

For OpenClaw, Hermes, or other agents, install the folder in the runtime's skills directory and map host tools to the capability contract in `references/agent-capabilities.md`.

## Modes

- **quick** — compact article or narrow explainer
- **standard** — default verified article with Fact Grid and Hyperlink Map
- **deep** — high-stakes or longform work with expanded verification
- **discovery-first** — source/topic shortlist first, user chooses, article comes after

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
- **DOCX / PDF / Google Docs** — for editorial handoff
- **telegra.ph / published page** — when explicitly requested and authenticated tooling is available
- **Markdown** — default

## Optional adapters

- `chip-relay` for persistent CDP browser sessions, screenshots, authenticated capture, and publishing
- GPT Image 2 or the host agent's configured image backend for diagrams, cover visuals, and verified-data publication graphics
- Document adapters for DOCX, PDF, and Google Docs export

## Files

| File | Contents |
|------|----------|
| `SKILL.md` | Main skill definition and workflow |
| `agents/openai.yaml` | Codex UI metadata |
| `references/ai-agentic-systems.md` | AI/agentic source discovery and topic-shortlist workflow |
| `references/runtime-adapters.md` | Codex, Claude Code, Hermes runtime mapping |
| `references/` | Source hierarchy, style, article structure, citations, formats, visuals, browser capture, publishing, examples |
