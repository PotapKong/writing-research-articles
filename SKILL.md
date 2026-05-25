---
name: writing-research-articles
description: Conduct verified web research, build a source-traceable Fact Grid, and write professional fact-based articles with citations, hyperlink maps, and visual placeholders. Use when Codex is asked for deep research, source verification, current or time-sensitive information, investment or market analysis, geopolitical or business longreads, Telegraph-style editorial HTML, n8n/JSON article pipelines, or publication-ready longform content in Markdown, HTML, or JSON.
---

# Writing Research Articles

## Core workflow

Use this skill to keep research writing evidence-led. Do not draft factual longform from memory when claims depend on dates, statistics, prices, rankings, filings, market data, policy changes, or current roles.

Track progress with this checklist:

```markdown
Research Progress:
- [ ] Step 1: Parse brief and build research question set
- [ ] Step 2: Search the web across all research tracks
- [ ] Step 3: Open primary or top-tier URLs to confirm key claims
- [ ] Step 4: Verify freshness and reliability of each source
- [ ] Step 5: Build Fact Grid
- [ ] Step 6: Draft article from verified grid only
- [ ] Step 7: Editorial cleanup pass
- [ ] Step 8: Pre-publication fact re-check
- [ ] Step 9: Attach Hyperlink Map and Visual Placeholders
- [ ] Step 10: Output in the requested format
```

In interactive writing sessions, show the Fact Grid before drafting when the user asks for approval gates or the topic is high-stakes. If the user asks for a complete article in one pass, include the Fact Grid in the final output and draft from it without stopping. In automation/n8n mode, put the Fact Grid inside JSON and proceed directly.

## Output format

Detect from context. Apply in order:

1. **HTML Artifact** — user mentions Telegraph, landing page, dark theme, editorial HTML
2. **JSON** — user mentions n8n, automation, pipeline, structured output. See [output-formats.md](references/output-formats.md)
3. **Markdown** — default for all other cases

### Step 1: Parse the brief

Extract internally:
- exact topic, target angle, geography/market scope, time horizon
- intended audience, article type (analytical / explanatory / persuasive / comparative / news)
- publication date sensitivity

If the brief is sparse, convert to a working assignment with: topic, core thesis candidate, target emotional temperature, audience sophistication, publishing format, mandatory reference inputs, optional side angles, likely weak sections requiring deeper verification.

If the client gives a reference reel, thread, article, or Telegram post — extract the hook or angle only. Rebuild the piece on a stronger verified evidence base. Do not copy the structure blindly.

### Step 2: Build research question set

Break assignment into tracks:
- core thesis, market size/growth, policy/regulatory, company-specific, counterargument/risk, recent developments, valuation/financial performance

### Step 3: Search the web

**When to search:** Always browse before drafting when the task involves any date, price, statistic, ranking, market figure from the last 24 months, company filings or official statements, policy changes, news, recommendations, or persons currently holding a role.

**Codex tool mapping:**
- Use available web search tools for discovery, such as `web.run` `search_query`.
- Open URLs for confirmation, such as `web.run` `open`.
- Use official documentation, filings, regulator pages, investor relations pages, and primary datasets whenever available.
- Use browser tools only when a page must be visually inspected, interacted with, or verified.

**Query construction:**
- 2–6 words per query. Short specific queries outperform natural-language ones.
- Always search in English, even when the article will be in Russian.
- For each research track, run at least 2 independent queries from different angles.
- Never repeat a query verbatim — rephrase with different nouns or add year/institution.

### Step 4: Open primary sources

Open a URL when:
- a search snippet is too short to confirm or deny a claim
- a Tier 1 or Tier 2 source URL appears in results (annual report, central bank release, IR page, regulatory filing)
- you need an exact figure or quote, not a paraphrase

Always open at least one primary or top-tier source per major claim.

For source trust hierarchy, see [source-hierarchy.md](references/source-hierarchy.md).

### Step 5: Build and show Fact Grid

Output as Markdown table:

| # | Claim | Exact figure / statement | Source name | URL | Date | Confidence | Primary? | Anchor text |
|---|-------|--------------------------|-------------|-----|------|------------|----------|-------------|

Confidence levels:
- **High** — Tier 1 primary, or two independent Tier 2 confirmations
- **Medium** — single Tier 2 source, no primary available
- **Low** — single Tier 3 or older date; include only with explicit caveat
- **Excluded** — found but not verifiable; note reason

After the table, add a short paragraph: total sources checked, excluded claims, any conflict and how resolved, effective "current as of" date.

### Step 6: Draft from the verified grid only

Use verified material to produce a coherent narrative. Separate what is known, what is inferred, what remains uncertain.

If one section is weakly supported: remove it, reduce to one cautious sentence, reframe as an open question, or move to a brief mention. A tighter article beats a broader weaker one.

For article structure and construction rules, see [article-construction.md](references/article-construction.md).

For house style, voice, and forbidden AI patterns, see [house-style.md](references/house-style.md).

### Step 7: Editorial cleanup pass

Before finalizing, rewrite any sentence that:
- could fit almost any topic
- sounds like a template or pads rather than informs
- uses obvious AI contrast formulas
- relies on vague praise instead of specifics

### Step 8: Pre-publication re-check

Run a second-pass fact-check on the finished text:
- headline thesis vs body support
- every date, percentage, price, count, hard number
- proper nouns: company names, institutions, people, regions, laws, reports
- causal wording: "caused", "triggered", "led to", "forced", "signaled"
- comparative framing: "worse than", "largest since", "first time since"

If a sentence cannot be re-confirmed from the verified grid — soften it, narrow it, or cut it.

### Step 9: Attach Hyperlink Map and Visual Placeholders

For citation rules and Hyperlink Map format, see [citations.md](references/citations.md).

For visual placeholder rules, see [visual-placeholders.md](references/visual-placeholders.md).

### Step 10: Final output

Return in this order:
1. Fact Grid (Markdown table + verification summary)
2. Title + Optional Subhead
3. Full article with inline citations
4. Hyperlink Map
5. Source Notes
6. Optional Disclaimer (required for articles touching markets, investing, tokens, macro, or public securities)

For HTML and JSON output formats, see [output-formats.md](references/output-formats.md).

## Non-negotiable standards

1. Research first. Never draft from memory alone when facts, dates, figures, market data, or current events matter.
2. Only include claims supportable by a trustworthy source.
3. Prioritize information current on the assignment date. Verify outdated sources against newer ones.
4. If sources conflict, state the conflict explicitly — reconcile or exclude the disputed claim.
5. Do not invent citations, URLs, source names, publication names, data points, quotes, or publication dates.
6. Every factual sentence in the final article must be source-traceable.
7. No lazy AI patterns, inflated filler, robotic transitions, or stock framing devices.
8. Repeat fact-check before delivery.
9. Respect the host environment's citation, quotation, and copyright rules.

## Failure conditions

If search returns no relevant results, or a page cannot be opened because of a paywall or access failure:
- note it in the Fact Grid with confidence = **Excluded**
- narrow the claim, use cautious wording, explain what could not be verified
- prefer omission over fabrication

If a major tool call fails: note the failure in Source Notes and proceed with available verified sources only. Do not substitute unverified memory for failed tool results.

## Revision loop

When client reacts after review, handle feedback in this order:
1. factual weakness — run additional searches for the specific claim
2. structural weakness — cut or reorder sections
3. tonal mismatch — adjust voice within the same evidence base
4. visual or image-hosting issue — update placeholder notes with new source URLs
5. headline or hook adjustment

Response to feedback must be surgical. Do not rewrite the whole article if one paragraph is the real issue. When a section is cut, rebalance transitions and conclusion.

## Reference files

| File | Contents |
|------|----------|
| [source-hierarchy.md](references/source-hierarchy.md) | Source trust hierarchy, freshness rules |
| [house-style.md](references/house-style.md) | Voice, structural patterns, forbidden AI patterns |
| [article-construction.md](references/article-construction.md) | Article construction, sections, templates |
| [output-formats.md](references/output-formats.md) | HTML, JSON schema, Markdown rules |
| [citations.md](references/citations.md) | Citation rules, Hyperlink Map format |
| [visual-placeholders.md](references/visual-placeholders.md) | Visual placeholder rules |
| [examples.md](references/examples.md) | Example invocations and expected behavior |
