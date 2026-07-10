# Obstacle Race Panamá

Static, single-page **coming-soon teaser** site for **Obstacle Race Panamá** — the obstacle
race that moves Panama, with a **collection drive for sneakers and sportswear**.

Brutalist tabbed layout (Inicio · Movimiento · Recursos · Patrocinadores). No build step —
pure static files served from the repo root.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire landing page (inline CSS + JS, Google Fonts). |
| `logo.jpg` | The emblem logo (header, hero, footer, and OG image). |
| `favicon.svg` | Site icon. |
| `og.png` | 1200×630 social share image (`og.svg` is its source). |
| `_headers` | Cloudflare Pages security headers (HSTS, CSP, X-Frame-Options, etc.). |
| `robots.txt` | Allows all crawlers, points to the sitemap. |
| `sitemap.xml` | Single-URL sitemap for the homepage. |

## ⚠️ One placeholder left: the registration link

Every "Regístrate / Recibir recursos" button reads one constant near the bottom of `index.html`:

```js
var REGISTER_URL = "https://forms.gle/REEMPLAZAR-CON-FORM-REAL";
```

Paste the real Google Form URL there. Until it's a valid `http(s)://` link (and no longer
contains `REEMPLAZAR`), the buttons fall back to `mailto:info@obstacleracepanama.com` so leads
are still captured.

Sponsorship / brand contact goes to **info@obstacleracepanama.com** (wired into the
"Patrocinadores" tab). This mailbox needs email routing on the domain once it's live.

## Regenerating the OG image

If you replace `logo.jpg`, re-render the share image:

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new --disable-gpu \
  --window-size=1200,630 --default-background-color=00000000 --screenshot=og.png og.svg
```

## Deploy (Cloudflare Pages)

```bash
wrangler pages deploy . --project-name=obstacleracepanama
```

DNS / custom domain (`obstacleracepanama.com`, Namecheap) is handled manually.
