# Launch notes & follow-ups

This file is excluded from the published site via `_config.yml` (`exclude`).

## Launched (staging → production)

On 2026-06-26 the `staging/` redesign was promoted to the site root:

- [x] Moved `index.html`, `contact.html`, `styles.css` to root; removed the old
      placeholder `index.md`.
- [x] Consolidated images into `assets/images/` (was `provisional/` + `rights-review/`).
- [x] Removed `noindex, nofollow` robots metas from `index.html` / `contact.html`.
- [x] Repointed canonical + `og:url` from `/staging/` to live paths (`/`, `/contact.html`).
- [x] `robots.txt`: removed `Disallow: /staging/` (site open to crawlers).
- [x] TelemetryDeck `data-is-test-mode` set to `false` on both pages.

## Open follow-ups

- [x] **Restyle the legal pages.** `privacy.md` / `terms.md` converted to standalone
      `privacy.html` / `terms.html` that share the site header/footer and a frosted
      "document card" matching the new design. Legal text preserved verbatim.
- [ ] Confirm `404.html` (self-styled) still feels on-brand against the new design.
- [ ] Consider a `sitemap.xml` + reference it from `robots.txt`.
- [ ] Consider pretty URLs (e.g. `/contact` instead of `/contact.html`).
