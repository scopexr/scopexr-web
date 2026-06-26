# Staging → Production launch checklist

Note to self. The `staging/` pages are intentionally hidden from search
engines while in development. When promoting them to the live site, the
crawl/index protections must be removed AND the URLs corrected, or the
launched pages will either stay invisible to Google or point search
engines at the wrong (staging) location.

This file is excluded from the published site via `_config.yml` (`exclude`).

## Remove the crawl/index blocks

- [ ] `staging/index.html` line ~6: remove `<meta name="robots" content="noindex, nofollow, noarchive, nosnippet, noimageindex">` (or change to `index, follow`).
- [ ] `staging/contact.html` line ~6: remove `<meta name="robots" content="noindex, nofollow, noarchive, nosnippet">`.
- [ ] `robots.txt`: remove `Disallow: /staging/` (and confirm nothing else blocks the new live paths).

## Fix the URLs (currently point at `/staging/`)

These were set for the staging location and must move to the final production paths.

- [ ] `staging/index.html`: `<link rel="canonical">` and `og:url` → final URL (e.g. `https://scopexr.com/`).
- [ ] `staging/contact.html`: `<link rel="canonical">` and `og:url` → final URL (e.g. `https://scopexr.com/contact.html`).
- [ ] If the pages move out of `staging/`, update relative asset/links and the `og:image` paths accordingly.

## Analytics

- [ ] TelemetryDeck script in both pages has `data-is-test-mode="true"` — set to `false` (or remove the attribute) for production traffic.

## Verify after launch

- [ ] Confirm pages return `index, follow` and are reachable (not Disallowed).
- [ ] Re-test Open Graph / Twitter cards and JSON-LD (e.g. Google Rich Results Test) on the live URLs.
- [ ] Submit/refresh sitemap if one exists.
