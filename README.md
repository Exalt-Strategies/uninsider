# UN Insider

Independent coverage of UN affairs — Security Council decisions, humanitarian crises, peacekeeping, and global governance.

A single-file static site, paraphrasing and attributing reporting from primary sources (UN Press, Security Council Report, UN News, OHCHR, PassBlue, and others).

## Structure

- `index.html` — public reader (deployed to Vercel)
- `un_insider_editor.html` — internal editor (kept local, not deployed)
- `vercel.json` — security headers and routing for Vercel
- `.vercelignore` — keeps the editor out of every deployment

## Security

- Content Security Policy via `<meta>` tag plus Vercel response headers
- HTML sanitiser with tag/attribute allowlist for user-authored body content
- URL allowlist (`https:`, `mailto:`, anchors only)
- `Strict-Transport-Security`, `X-Frame-Options: DENY`, `Referrer-Policy: strict-origin-when-cross-origin`, locked-down `Permissions-Policy`
- All external links open with `rel="noopener noreferrer"`

## Editing

The editor lives only on the local machine. Open `un_insider_editor.html` in a browser to write or edit. Articles persist to your browser's `localStorage`. Each save sanitises the body HTML before storing it.

## Attribution

UN Insider paraphrases and attributes; it does not claim authorship of source reporting. Each article links to its primary source.
