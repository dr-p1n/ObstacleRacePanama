# Obstacle Race Panamá

Static, single-page **coming-soon / teaser** site for **Obstacle Race Panamá** — the
obstacle race that moves Panama, powered by **Ecofit × Panama Sports Magazine**.

No build step. Pure static files served from the repo root.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire landing page (inline CSS + JS, Google Fonts). |
| `logo.png` | The emblem logo (used in header, hero, footer, and OG image). |
| `favicon.svg` | Site icon. |
| `og.png` | 1200×630 social share image (`og.svg` is its source). |
| `_headers` | Cloudflare Pages security headers (HSTS, CSP, X-Frame-Options, etc.). |
| `robots.txt` | Allows all crawlers, points to the sitemap. |
| `sitemap.xml` | Single-URL sitemap for the homepage. |

## ⚠️ Two placeholders to replace before/after go-live

1. **Logo** — `logo.png` is currently a **stand-in emblem**. Overwrite it with the real
   Obstacle Race Panamá artwork (square PNG, transparent or dark background works best),
   then regenerate `og.png` from `og.svg` so the share image matches.

2. **Registration link** — every "Regístrate" button reads one constant near the bottom
   of `index.html`:

   ```js
   var REGISTER_URL = "https://forms.gle/REEMPLAZAR-CON-FORM-REAL";
   ```

   Paste the real Google Form URL there. Until it's a valid `http(s)://` link (and no longer
   contains `REEMPLAZAR`), the buttons safely fall back to scrolling to the sign-up section.

Sponsorship / brand contact goes to **gladysgiselle@gmail.com** (already wired into the
"Patrocinios" links).

## Deploy (Cloudflare Pages)

```bash
wrangler pages deploy . --project-name=obstacleracepanama
```

DNS / custom domain (`obstacleracepanama.com`, Namecheap) is handled manually.
