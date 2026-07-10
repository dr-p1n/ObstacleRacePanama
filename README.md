# Obstacle Race Panamá 2026

Static, single-page landing site for **Obstacle Race Panamá 2026** — the obstacle race
event powered by **Ecofit × Panama Sports Magazine**.

No build step. Pure static files served from the repo root.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire landing page (inline CSS + JS, Google Fonts). |
| `favicon.svg` | Site icon / logo mark. |
| `og.png` | 1200×630 social share image (`og.svg` is its source). |
| `_headers` | Cloudflare Pages security headers (HSTS, CSP, X-Frame-Options, etc.). |
| `robots.txt` | Allows all crawlers, points to the sitemap. |
| `sitemap.xml` | Single-URL sitemap for the homepage. |

## Editing the countdown date

The race countdown reads a single constant near the bottom of `index.html`:

```js
var RACE_DATE = new Date("2026-11-14T06:00:00-05:00").getTime();
```

⚠️ **This date is a placeholder.** Replace it with the confirmed start date/time
(Panama is UTC−05:00, no daylight saving). Also update `startDate` in the JSON-LD
block and `<lastmod>` in `sitemap.xml` when the date is finalized.

## Deploy (Cloudflare Pages)

```bash
wrangler pages deploy . --project-name=obstacleracepanama
```

DNS / custom domain (`obstacleracepanama.com`) is managed manually in the Cloudflare dashboard.
