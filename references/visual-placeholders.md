# Visual Placeholders

## Placeholder formats

Insert directly into the article body using square brackets:

- `[Screenshot placeholder: describe what should be shown and why it matters]`
- `[Chart placeholder: metric, time range, units, chart type, intended takeaway]`
- `[Graph placeholder: variables, analytical takeaway]`
- `[Diagram placeholder: entities, flows, or process to visualize]`
- `[Table placeholder: columns, rows, comparison purpose]`
- `[Cover image placeholder: editorial or branded lead visual — only if needed]`
- `[Asset manifest placeholder: list produced screenshots, generated visuals, deterministic charts, source URLs, captions, and provenance]`

## Placement rules

1. Place at the exact point where the visual helps the reader most — after a setup paragraph, before cognitive load spikes.
2. Each placeholder must be specific enough that a designer or analyst could build it without guessing.
3. Only add placeholders that materially improve clarity. Use visuals to prove or compress, not to decorate.
4. If a visual depends on source data, mention the source in the placeholder note.
5. Replace placeholders with real assets when the runtime has browser, chart, image-generation, or document tools.

## Content rules by type

**Screenshot placeholders:** specify source document, chart title, quote, page, or section.

**Chart placeholders:** specify the intended takeaway, not just the metric. Include the source URL.

**Table placeholders:** specify the comparison logic and exact fields to include.

**Telegraph-style source lines:** accompany important placeholders with a source line directly beneath:
`Source: [Publisher], [document name if relevant]`

## Acquisition notes

For every placeholder, include a usable acquisition note: the exact source URL and either the page number, section title, chart name, quote block, or a precise instruction for what to assemble manually.

Do not suggest abstract conceptual collages unless you also provide a real source asset for each element.

## Asset replacement rules

- Source screenshots: capture through browser tooling. See [browser-capture.md](browser-capture.md).
- Exact charts: render from verified data, not from a generative image model.
- Conceptual diagrams and cover visuals: use the host agent's configured image-generation backend when available. See [generated-visuals.md](generated-visuals.md).
- DOCX, Google Docs, or telegra.ph embedding: preserve the caption and source/provenance line near the asset. See [document-publishing.md](document-publishing.md).
- PDF embedding: use the same verified asset package as DOCX, then inspect page breaks and legibility.
