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

## Example 2: Sparse brief with reference material

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

## Example 3: n8n pipeline output

**User:** Research [topic] and return structured JSON for my n8n workflow.

**Expected behavior:**
1. research and verify as normal
2. skip the Markdown Fact Grid display; include `fact_grid` array inside the JSON output
3. return complete JSON object per schema in [output-formats.md](output-formats.md)
4. plain text only in `article_sections[].body` — no HTML or Markdown

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
