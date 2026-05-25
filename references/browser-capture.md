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
2. Prefer source-document charts, regulator tables, investor relations pages, product pages, or live platform states over decorative screenshots.
3. Store screenshots as files and reference their paths in Source Notes or the article asset manifest.
4. Caption every screenshot with source, URL, capture date, and what the reader should notice.
5. If a page is authenticated or user-specific, say so in the caption and avoid exposing private data.
6. Crop or mask personal data, account IDs, tokens, cookies, internal URLs, or email addresses before embedding.

## Replacing placeholders

For each placeholder:

1. Identify whether it needs a screenshot, deterministic chart, generated visual, or manual source asset.
2. Capture or generate the asset.
3. Replace the placeholder with an embedded image, figure block, DOCX image, Google Docs image, or telegra.ph image upload.
4. Add a caption and provenance note.
5. Keep the original source URL in the Hyperlink Map or Source Notes.

If capture fails, leave the placeholder but add exact acquisition notes:

```text
[Screenshot placeholder: capture the revenue chart from Company FY2025 annual report, page 42, URL: ...]
```

## Publishing browser safety

- Do not request passwords, cookies, session tokens, or 2FA codes in chat.
- Use a persistent browser profile only after the user completes login interactively.
- Do not commit browser profiles, logs, or screenshots containing secrets.
- For telegra.ph or Google Docs, verify the final rendered page before returning the link.
