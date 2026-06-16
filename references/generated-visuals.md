# Generated Visuals, Charts, and Diagrams

## Use when

Use this reference when the article needs charts, diagrams, editorial illustrations, cover images, or replacement assets for visual placeholders.

## Backend selection

Use the image-generation method configured in the current agent runtime. Do not
assume one universal backend. If GPT Image 2 is configured, prefer it for
polished editorial diagrams, cover images, and verified-data publication
graphics that need strong visual quality.

Examples of valid host-native backends:

- GPT Image 2
- Nano Banana
- the host's built-in image tool
- an OpenAI, Google, local, or custom image adapter exposed by the agent
- a deterministic diagram renderer for vector or Mermaid-style diagrams

If exactly one suitable backend is configured, use it. If several are available, choose the most efficient option for the visual task or ask the agent owner for a priority preference when cost, quality, latency, brand consistency, or privacy matters.

Selection heuristic:

| Need | Prefer |
|------|--------|
| Editorial cover or polished illustration | highest-quality configured image model |
| Fast draft concept | lowest-latency configured image model |
| Private or sensitive source material | local/private backend if available |
| Diagram with labels | deterministic diagram tool first, image model only if visual polish matters |
| Exact data chart | deterministic chart renderer first; GPT Image 2 only with exact supplied values and QA |
| Style consistency across a series | the backend already used for the series |

Do not hard-code an unavailable model name. Check the runtime, environment config, or owner preference when implementation details matter.

## Evidence boundary

Generated visuals are not evidence. They explain or illustrate evidence already captured in the Fact Grid.

Use this rule:

- **Exact numbers, time series, rankings, prices, market share:** render deterministically from verified data.
- **Processes, mechanisms, architecture, causal chains:** use diagrams, Mermaid, vector drawing, or the configured image backend.
- **Verified-data publication graphics:** may use GPT Image 2 when no source
  screenshot or deterministic renderer is available, but the prompt must include
  the exact data table and the output must be checked against it.
- **Editorial cover images and atmosphere:** use the configured image backend only when the article benefits from a lead visual.
- **Screenshots of source material:** capture through browser tools, not image generation.

## Chart workflow

1. Extract the data from the verified source.
2. Record source URL, date, metric, units, and transformation.
3. Render the chart using a deterministic tool when available.
4. Check labels, axes, units, legend, and date range.
5. Embed with a caption and source line.

If no chart renderer is available, provide a table and leave a chart placeholder with exact data instructions.

## GPT Image 2 verified-data workflow

Use this only when a visual is useful and no suitable source screenshot or local
deterministic renderer is available.

1. Build a small verified data table from the Fact Grid.
2. Include the source URL, date, metric, units, and all values in the image
   prompt.
3. Ask for a simple publication graphic with legible labels.
4. Forbid invented labels, extra data points, fake logos, and decorative
   benchmark values.
5. Inspect the result: every label and number must match the verified data.
6. If the generated image alters values or labels, discard it and use a table or
   placeholder instead.
7. Caption it as "Generated publication graphic based on verified source data",
   not as a source screenshot.

Prompt pattern:

```text
Create a clean publication chart based only on the verified data below.
Chart type: [bar/line/comparison/flow].
Title: [plain factual title].
Data:
- [Label]: [value] [unit], source date [date]
- [Label]: [value] [unit], source date [date]
Required labels: [exact labels].
Style: editorial, legible, restrained, no fake logos, no extra numbers.
Do not add data points, forecasts, rankings, or annotations not listed here.
Caption/provenance: generated from verified data, source URL [url].
```

## Image prompt pattern

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
- Generated data visuals match every value and label in the verified data table.
- The asset manifest records whether the image is evidence, derived from
  evidence, or illustrative.
