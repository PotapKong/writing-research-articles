# Example Invocations

## Example 1: Investment article

**User:** Research the latest state of uranium supply and write a professional investment-style article with source links and chart placeholders.

**Expected behavior:**
1. research question set: supply-demand balance, production by country, company disclosures, recent policy
2. run 8–12 English web searches; open primary source URLs
3. build Fact Grid and show to user
4. draft market-literate article with sharp headline and clear thesis
5. attach Hyperlink Map with exact anchor phrases
6. insert chart and table placeholders with exact source references and acquisition notes
7. exclude any unverified claim even if widely repeated elsewhere

---

## Example 2: AI agentic-systems source discovery

**User:** Find strong Western English-language articles and authors about agentic systems, coding agents, and multi-agent workflows. Give me links first so I can choose what we turn into a Russian article.

**Expected behavior:**
1. switch to discovery-first mode
2. search across AI labs, respected technical publications, newsletters, product/engineering blogs, and credible expert writers
3. open promising URLs and exclude weak snippet-only leads
4. return a Source Shortlist with 8-15 options
5. include "Best angle for our audience" for every source
6. stop and ask which source or angle the user wants to develop
7. do not draft the article until the user chooses

---

## Example 3: AI article from a chosen source

**User:** Take option 4 from the shortlist and write a new article for our audience about what it means for AI-agent teams in business workflows.

**Expected behavior:**
1. reopen the chosen source
2. extract its core thesis and evidence without copying structure
3. search for primary confirmations, counterarguments, and newer related sources
4. build a Fact Grid from the wider evidence base
5. write a new article in the target language and house style
6. credit the chosen source through inline citation and Hyperlink Map
7. include practical implications, limits, and what to watch next

---

## Example 4: Sparse brief with reference material

**User:** Use this reel as the base angle. Topic: crisis indicators for 2026–2027. Mention the Buffett indicator briefly — it was already covered before.

**Expected behavior:**
1. extract hook from reference material — do not copy its structure
2. identify side angle to mention briefly (Buffett indicator — do not redevelop at full length)
3. run searches to verify and enrich the main thesis
4. show Fact Grid before drafting
5. rebuild article on stronger verified source base
6. avoid repeating already-covered material at full length
7. deliver sharper longread with clean section logic and source-linked evidence

---

## Example 5: n8n pipeline output

**User:** Research [topic] and return structured JSON for my n8n workflow.

**Expected behavior:**
1. research and verify as normal
2. skip the Markdown Fact Grid display; include `fact_grid` array inside the JSON output
3. return complete JSON object per schema in [output-formats.md](output-formats.md)
4. plain text only in `article_sections[].body` — no HTML or Markdown

---

## Example 6: Article with screenshots and generated diagram

**User:** Research the latest AI chip export controls, capture key source screenshots through chip-relay, generate one clean explanatory diagram with the configured image backend, and deliver a DOCX.

**Expected behavior:**
1. research and verify as normal
2. use `chip-relay` or the host browser adapter for source screenshots
3. render exact charts from verified data if charts are needed
4. use the agent's configured image backend only for the explanatory diagram or cover visual
5. replace placeholders with embedded assets and captions
6. export a DOCX with source notes and hyperlink map

---

## Example 7: Codex/Claude/Hermes visual article package

**User:** Research AI-agent observability, capture screenshots of the best source tables or charts, generate one GPT Image 2 diagram if no suitable chart exists, and deliver DOCX plus PDF.

**Expected behavior:**
1. detect runtime capabilities: browser screenshots, image backend, DOCX/PDF export
2. research and verify as normal
3. capture source screenshots for tables, charts, news pages, docs, or benchmark panels that support the article
4. if no source chart exists, build a verified data table and render a deterministic chart; use GPT Image 2 only for a checked publication graphic or diagram based on that verified data
5. record every visual in the asset manifest with source URL, provenance, caption, and verification notes
6. export DOCX and PDF when the runtime supports it; otherwise return the closest durable artifact and say which adapter is missing
7. verify files exist and, when practical, render/inspect them before final delivery

---

## Example 8: telegra.ph publishing

**User:** Prepare this as a Telegraph-style article, publish it to telegra.ph from my authenticated browser profile, and give me the link.

**Expected behavior:**
1. prepare and return the article file first
2. ask the user to authorize the publishing step and browser login if needed
3. use `chip-relay` or available browser tooling with the existing authenticated profile after authorization
4. do not ask for passwords, cookies, or tokens in chat
5. insert article body, images, captions, and links
6. visually verify the published page
7. return the telegra.ph URL and keep the local fallback artifact path

---

## Common client feedback patterns

| Feedback | Response |
|----------|----------|
| "this block is too superficial" | run additional web searches for that specific claim |
| "mention this, but briefly" | reduce section to 1–2 sentences, do not expand |
| "use this reel as a base" | extract angle only, rebuild from verified sources |
| "more trigger-based" | sharpen lede and H2s within same evidence base |
| "reupload the images" | regenerate placeholder notes with updated source URLs |
| "remove this geography/actor" | cut section, rebalance transitions and conclusion |
| "make it a docx" | export the verified article and assets through the document adapter |
| "publish it" | use the requested publisher only after explicit publish authorization |
