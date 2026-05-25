# Generated Visuals, Charts, and Diagrams

## Use when

Use this reference when the article needs charts, diagrams, editorial illustrations, cover images, or replacement assets for visual placeholders.

## Backend selection

Use the image-generation method configured in the current agent runtime. Do not assume one universal backend.

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
| Exact data chart | deterministic chart renderer, not image generation |
| Style consistency across a series | the backend already used for the series |

Do not hard-code an unavailable model name. Check the runtime, environment config, or owner preference when implementation details matter.

## Evidence boundary

Generated visuals are not evidence. They explain or illustrate evidence already captured in the Fact Grid.

Use this rule:

- **Exact numbers, time series, rankings, prices, market share:** render deterministically from verified data.
- **Processes, mechanisms, architecture, causal chains:** use diagrams, Mermaid, vector drawing, or the configured image backend.
- **Editorial cover images and atmosphere:** use the configured image backend only when the article benefits from a lead visual.
- **Screenshots of source material:** capture through browser tools, not image generation.

## Chart workflow

1. Extract the data from the verified source.
2. Record source URL, date, metric, units, and transformation.
3. Render the chart using a deterministic tool when available.
4. Check labels, axes, units, legend, and date range.
5. Embed with a caption and source line.

If no chart renderer is available, provide a table and leave a chart placeholder with exact data instructions.

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
