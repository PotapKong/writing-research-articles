# Browser Capture and chip-relay

## Use when

Use browser capture when the article needs screenshots, authenticated pages, chart images, web app states, telegra.ph publishing, or visual verification that cannot be captured from text search alone.

Prefer `chip-relay` when installed because it provides a persistent local Chrome DevTools Protocol rail with switchable browser backends and stable profiles.

## chip-relay workflow

Use the local `chip-relay` skill or repository instructions when available.

Typical operator sequence:

```bash
scripts/chip-relay doctor
scripts/chip-relay launch --backend auto
scripts/chip-relay health
scripts/chip-relay open https://example.com
scripts/chip-relay status
```

Expected CDP endpoint:

```text
http://127.0.0.1:18800
```

Use Playwright, Puppeteer, or the host browser adapter to connect to the endpoint and capture screenshots.

## Screenshot rules

1. Capture only what supports a specific claim, visual explanation, or publishing step.
2. Prefer source-document charts, regulator tables, investor relations pages, news pages, product pages, technical docs, benchmark pages, or live platform states over decorative screenshots.
3. Store screenshots as files and reference their paths in Source Notes or the article asset manifest.
4. Caption every screenshot with source, URL, capture date, and what the reader should notice.
5. If a page is authenticated or user-specific, say so in the caption and avoid exposing private data.
6. Crop or mask personal data, account IDs, tokens, cookies, internal URLs, or email addresses before embedding.
7. Capture the smallest useful region: table, chart, quote block, headline,
   benchmark panel, or product state. Avoid full-page screenshots unless layout
   context is the point.
8. After capture, verify that text is legible, the crop contains the cited
   evidence, and no private information is visible.

## Screenshot target priority

1. Existing source chart or table that directly supports a claim.
2. Official statement, model card, docs page, benchmark page, filing, or policy
   page.
3. Reported news page when the article needs the headline, quote, or context.
4. Product UI, workflow, or live page state when the article is about user-facing
   behavior.
5. Context screenshot only when the visual setting itself is important.

## Replacing placeholders

For each placeholder:

1. Identify whether it needs a screenshot, deterministic chart, generated visual, or manual source asset.
2. Capture or generate the asset.
3. Replace the placeholder with an embedded image, figure block, DOCX image, Google Docs image, or telegra.ph image upload.
4. Add a caption and provenance note.
5. Keep the original source URL in the Hyperlink Map or Source Notes.
6. Record the asset in the manifest described in
   [runtime-adapters.md](runtime-adapters.md).

If capture fails, leave the placeholder but add exact acquisition notes:

```text
[Screenshot placeholder: capture the revenue chart from Company FY2025 annual report, page 42, URL: ...]
```

## Publishing browser safety

- Do not request passwords, cookies, session tokens, or 2FA codes in chat.
- Use a persistent browser profile only after the user completes login interactively.
- Do not commit browser profiles, logs, or screenshots containing secrets.
- For telegra.ph or Google Docs, verify the final rendered page before returning the link.
