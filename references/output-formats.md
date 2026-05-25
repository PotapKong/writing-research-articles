# Output Formats

## Contents
- Format selection rules
- Markdown (default)
- HTML Artifact
- JSON for n8n

## Format selection rules

Apply in this order:

1. **HTML Artifact** → user mentions Telegraph, landing page, dark theme, editorial HTML, or prior conversation established HTML as default
2. **JSON** → user mentions n8n, automation, pipeline, or structured output
3. **Markdown** → default for all other cases

If no signal, default to Markdown.

## Markdown (default)

Standard output with:
- `##` H2 section heads
- `**bold**` for key terms, figures, institutions
- `> blockquote` for standout claims or direct quotes
- Fact Grid as Markdown table before the article
- Hyperlink Map as Markdown table after the article

## HTML Artifact

Output as a complete HTML file with:
- embedded CSS (dark theme if not specified otherwise)
- semantic tags: `<article>`, `<section>`, `<h2>`, `<blockquote>`, `<figure>`
- source lines as `<cite>` or styled caption beneath visuals
- Fact Grid rendered as an HTML table before the article body
- Hyperlink Map in a collapsible `<details>` section at the end

## JSON for n8n

Output a JSON object with this exact schema:

```json
{
  "title": "string",
  "subhead": "string or null",
  "fact_grid": [
    {
      "id": 1,
      "claim": "string",
      "figure": "string",
      "source_name": "string",
      "url": "string",
      "date": "YYYY-MM-DD",
      "confidence": "high | medium | low",
      "is_primary": true,
      "anchor_text": "string"
    }
  ],
  "article_sections": [
    {
      "heading": "string",
      "body": "string (plain text only — no HTML, no Markdown)"
    }
  ],
  "hyperlink_map": [
    {
      "anchor_text": "string",
      "url": "string",
      "source_type": "primary | secondary",
      "rationale": "string"
    }
  ],
  "visual_placeholders": [
    {
      "type": "chart | table | screenshot | diagram",
      "description": "string",
      "position": "after section heading (string)",
      "source_url": "string or null"
    }
  ],
  "source_notes": {
    "current_as_of": "YYYY-MM-DD",
    "excluded_claims": ["string"],
    "conflicts_resolved": ["string"]
  },
  "disclaimer": "string or null"
}
```

**JSON rules:**
- plain text only in `article_sections[].body` — strip all HTML and Markdown
- ensure all JSON strings are properly escaped
- `visual_placeholders` must include `source_url` wherever a downstream node must fetch the image
- skip the Markdown Fact Grid display; include `fact_grid` array inside the JSON output
