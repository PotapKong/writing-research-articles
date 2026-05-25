# writing-research-articles

A Claude Code skill for verified web research and fact-based article writing.

## What it does

Conducts deep web research using `web_search` and `web_fetch`, builds a visible **Fact Grid** with confidence levels, then writes a professional article with inline citations, hyperlink map, and visual placeholders.

## When to use

- Deep research on any topic
- Fact-based article writing (analytical, explanatory, comparative, news)
- Investment analysis and market notes
- Geopolitical longreads
- Telegraph-style HTML publications
- Source verification and fact-checking
- Publication-ready longform content in Markdown, HTML, or JSON

## How to invoke

In Claude Code:

```
/writing-research-articles
```

Then describe your article brief.

## Workflow (10 steps)

1. Parse brief and build research question set
2. Run `web_search` queries (6–12 standard, up to 20 for longreads)
3. `web_fetch` primary source URLs to confirm key claims
4. Verify freshness and reliability of each source
5. Build Fact Grid and show to user — wait for confirmation
6. Draft article from verified grid only
7. Editorial cleanup pass — remove AI patterns
8. Pre-publication re-check — all numbers and names
9. Attach Hyperlink Map and Visual Placeholders
10. Output in correct format

## Output formats

- **HTML Artifact** — for Telegraph, landing pages, dark theme editorial
- **JSON** — for n8n, automation pipelines, structured output
- **Markdown** — default

## Model routing

- **Claude Opus** — ambiguous briefs, multi-angle analysis, conflicting sources, 8+ source reconciliation
- **Claude Sonnet** — clearly scoped briefs, single-topic notes, rewrites, revision loops

## Files

| File | Contents |
|------|----------|
| `SKILL.md` | Main skill definition and full workflow |
