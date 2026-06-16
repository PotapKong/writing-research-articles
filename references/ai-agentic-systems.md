# AI and Agentic-Systems Research

## Use when

Use this reference when the user asks for:

- artificial intelligence articles;
- agentic systems, autonomous agents, coding agents, multi-agent teams, MCP,
  tool use, workflows, evals, observability, or AI product architecture;
- Western English-language source discovery;
- links to authoritative publications, researchers, builders, or bloggers before
  choosing an article topic.

## Discovery-first workflow

When the user wants topic options or links to study first:

1. Search broadly across respected English-language sources.
2. Open the most promising URLs; do not rely on snippets.
3. Build a Source Shortlist with 8-15 options, or 15-25 for deep discovery.
4. Rank each option by authority, novelty, relevance to the user's audience, and
   how well it can support a new derivative article.
5. Stop and ask which source or angle the user wants to develop.

Do not draft the final article until the user chooses a source/angle unless the
brief explicitly says to choose and proceed.

## Source types to prioritize

### Tier A: primary and technical sources

- AI lab posts and research pages: OpenAI, Anthropic, DeepMind, Google Research,
  Meta AI, Microsoft Research, Mistral, Cohere, Stanford HAI, Berkeley AI
  Research, MIT CSAIL, CMU, Princeton NLP, Oxford, Cambridge, and comparable
  institutions.
- Official product or engineering blogs for AI tooling companies and platforms.
- Original papers and technical reports: arXiv, conference proceedings,
  institutional PDFs, benchmark/eval documentation.
- Standards and protocol docs: MCP, model context protocols, tool-use specs,
  agent framework docs, safety/evaluation docs.

### Tier B: respected publications and analysts

- MIT Technology Review
- IEEE Spectrum
- The Gradient
- Communications of the ACM
- ACM Queue
- Quanta Magazine when relevant to AI research
- Wired, The Verge, Ars Technica, and similar outlets when the article is
  reported and source-rich
- The Information, Stratechery, Platformer, SemiAnalysis, Interconnects,
  Latent Space, Import AI, One Useful Thing, and comparable specialist writing
  when directly relevant and well sourced

### Tier C: expert practitioners and builders

Use expert blogs, newsletters, GitHub repos, talks, and long-form posts when:

- the author is identifiable and has domain credibility;
- the post contains concrete implementation detail, examples, evals, or
  architectural tradeoffs;
- claims can be checked against primary docs, papers, repo code, or independent
  evidence.

Treat social posts as leads, not final evidence, unless they come from an
official account or are the original announcement being discussed.

## Query patterns

Use short English queries. Mix broad discovery with focused queries.

General discovery:

```text
agentic systems architecture
AI agents evaluation
LLM tool use agents
coding agents workflows
multi agent systems LLM
AI agents reliability
```

Primary-source discovery:

```text
site:openai.com agents
site:anthropic.com agents tool use
site:deepmind.google agents
site:microsoft.com research agents
site:arxiv.org agentic workflows
site:modelcontextprotocol.io
```

Expert/publication discovery:

```text
AI agents Latent Space
AI agents Interconnects
agentic systems SemiAnalysis
AI agents MIT Technology Review
coding agents The Information
AI agents Stratechery
AI agents Simon Willison
```

Implementation and product patterns:

```text
AI agent observability
agent memory architecture
MCP agent tools
LLM agents evals
AI agent browser automation
agent workflow orchestration
```

## Source Shortlist scoring

Score internally before presenting:

- **Authority:** primary source, respected publication, credible builder, or
  weak lead.
- **Freshness:** publication date and whether newer developments supersede it.
- **Specificity:** concrete evidence, mechanisms, architecture, evals, or data.
- **Originality:** whether it adds a useful angle beyond repeated AI hype.
- **Audience fit:** can be translated into a useful article for the user's
  audience without copying the source.
- **Verification path:** whether key claims can be checked through primary docs,
  papers, code, or independent reporting.

## Source Shortlist format

Use this table:

| # | Source / author | URL | Type | Why it matters | Freshness | Best angle for our audience | Confidence |
|---|-----------------|-----|------|----------------|-----------|-----------------------------|------------|

Guidance:

- `Type` examples: lab post, research paper, technical blog, newsletter,
  reported article, product docs, repo, talk.
- `Why it matters` should summarize the evidence or idea, not praise the author.
- `Best angle for our audience` should be a publishable premise, for example:
  "why agent memory is becoming an operations problem, not a chat feature."
- `Confidence` reflects source quality and verification path, not whether the
  agent agrees with the argument.

## Turning a chosen source into a new article

After the user chooses:

1. Extract the source's core thesis, evidence, and assumptions.
2. Search for primary confirmations, counterarguments, newer updates, and
   concrete examples.
3. Build a Fact Grid from the wider evidence base.
4. Write a new article for the target audience. Do not summarize or translate
   the chosen source mechanically.
5. Credit the chosen source in the Hyperlink Map and, when editorially useful,
   in the article body.

## Avoid

- Hype-cycle articles with no primary evidence.
- Unverified benchmark claims.
- Posts that only repeat vendor announcements.
- Anonymous or low-accountability social threads.
- Treating a famous author as automatically correct.
- Copying the source structure, headline, or examples too closely.
