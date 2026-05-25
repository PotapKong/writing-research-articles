# Document Export and Publishing

## Use when

Use this reference when the user asks for DOCX, Word, Google Docs, HTML, telegra.ph, Telegraph-style output, or a live published article link.

## Delivery target selection

| User asks for | Deliver |
|---------------|---------|
| "file", "Word", "docx", "editorial handoff" | DOCX |
| "Google Docs" | Google Docs link if connector/browser upload is available; otherwise DOCX |
| "Telegraph style" | HTML or telegra.ph page depending on whether publishing is requested |
| "publish", "post to telegra.ph", "give me a link" | Article file first, then authorization request, then published page |
| "n8n", "pipeline", "structured" | JSON schema from output formats |

## DOCX export

When a document adapter is available:

1. Convert the final article into document structure: title, subhead, H2 sections, paragraphs, blockquotes, images, captions, hyperlink map, source notes, disclaimer.
2. Embed images from screenshots or generated visuals at their article positions.
3. Preserve clickable links when supported.
4. Render or inspect the file before final delivery when practical.
5. Return the file path and any unsupported formatting notes.

If no document adapter is available, produce Markdown or HTML and state that DOCX export requires a document-capable runtime.

## Google Docs

Use a Google Docs connector when available. If not, use browser upload only when the user has an authenticated browser profile.

Minimum requirements:

- final article text
- images as local files or accessible URLs
- captions and source notes
- hyperlink map
- verified sharing setting requested by the user

Do not ask for Google passwords, cookies, or tokens in chat. Let the user authenticate interactively in the browser if needed.

## telegra.ph publishing

Use telegra.ph only when explicitly requested.

Workflow:

1. Prepare the final article as a local file first, preferably DOCX or HTML with embedded/linked assets.
2. Return the file path or artifact to the user for review.
3. Ask the user to authorize the publishing step and, if needed, complete browser login interactively.
4. Use `chip-relay` or the host browser to open telegra.ph with an authenticated profile after authorization.
5. Insert title, author if requested, article body, images, captions, and links.
6. Preview and visually verify the page.
7. Publish only after authorization is confirmed.
8. Return the public URL and keep the local article file as fallback.

If authentication is unavailable, publish only if the target supports anonymous posting and the user accepts that limitation.

## Publishing notes

Final response should include:

- target and status: DOCX created, Google Docs created, telegra.ph published, or fallback produced
- file path or URL
- visual assets included
- sources current as of date
- any manual step still required
