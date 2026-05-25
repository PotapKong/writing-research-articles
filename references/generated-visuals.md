# Generated Visuals, Charts, and Diagrams

## Use when

Use this reference when the article needs charts, diagrams, editorial illustrations, cover images, or replacement assets for visual placeholders.

## Model preference

Prefer GPT Image 2 when the host exposes it. If GPT Image 2 is unavailable, use the host's current best OpenAI image model or image-generation adapter. Do not hard-code an unavailable model name; check the runtime or official docs when implementation details matter.

## Evidence boundary

Generated visuals are not evidence. They explain or illustrate evidence already captured in the Fact Grid.

Use this rule:

- **Exact numbers, time series, rankings, prices, market share:** render deterministically from verified data.
- **Processes, mechanisms, architecture, causal chains:** use diagrams, Mermaid, vector drawing, or GPT Image 2.
- **Editorial cover images and atmosphere:** use GPT Image 2 only when the article benefits from a lead visual.
- **Screenshots of source material:** capture through browser tools, not image generation.

## Chart workflow

1. Extract the data from the verified source.
2. Record source URL, date, metric, units, and transformation.
3. Render the chart using a deterministic tool when available.
4. Check labels, axes, units, legend, and date range.
5. Embed with a caption and source line.

If no chart renderer is available, provide a table and leave a chart placeholder with exact data instructions.

## GPT Image 2 prompt pattern

Use concise, specific prompts:

```text
Create a clean editorial diagram for a business longread.
Subject: [specific mechanism].
Show: [3-5 entities or stages].
Style: restrained publication graphic, legible labels, neutral background.
Do not include numeric claims unless provided below.
Required labels: [exact labels].
Source basis: [short summary of verified claim].
Output: [aspect ratio / transparent background if supported].
```

For cover images:

```text
Create a sophisticated editorial cover image for an analytical article about [topic].
Mood: [controlled, serious, market-literate].
Visual metaphor: [specific, non-generic].
Avoid: stock-photo look, fake logos, unreadable text, invented charts, exaggerated drama.
```

## Visual QA checklist

- No invented company logos, UI, charts, prices, labels, or screenshots.
- Text is legible if the visual contains labels.
- The asset matches the article's evidence and tone.
- The caption distinguishes generated illustration from source screenshot.
- The file path or URL is recorded in the delivery notes.
