# writing-research-articles

A Codex skill for verified web research and fact-based article writing.

## What it does

Conducts deep web research, builds a visible **Fact Grid** with confidence levels, then writes a professional article with inline citations, a hyperlink map, and visual placeholders.

## When to use

- Deep research on any topic
- Fact-based article writing (analytical, explanatory, comparative, news)
- Investment analysis and market notes
- Geopolitical longreads
- Telegraph-style HTML publications
- Source verification and fact-checking
- Publication-ready longform content in Markdown, HTML, or JSON

## Install

Copy or clone this repository into your Codex skills directory:

```powershell
git clone https://github.com/PotapKong/writing-research-articles "$env:USERPROFILE\.codex\skills\writing-research-articles"
```

Then invoke it as `$writing-research-articles` or ask Codex for a verified research article.

## Workflow (10 steps)

1. Parse brief and build research question set
2. Search the web across all research tracks
3. Open primary source URLs to confirm key claims
4. Verify freshness and reliability
5. Build Fact Grid
6. Draft article from verified grid only
7. Editorial cleanup pass
8. Pre-publication fact re-check
9. Attach Hyperlink Map and Visual Placeholders
10. Output in correct format

## Output formats

- **HTML Artifact** — for Telegraph, landing pages, dark theme editorial
- **JSON** — for n8n, automation pipelines, structured output
- **Markdown** — default

## Files

| File | Contents |
|------|----------|
| `SKILL.md` | Main skill definition and workflow |
| `agents/openai.yaml` | Codex UI metadata |
| `references/` | Source hierarchy, style, article structure, citations, formats, visuals, examples |
