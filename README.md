# Silent Logos 1882 — Official Store Website

> Cyberpunk-themed landing page for the **Silent Logos 1882** TikTok Shop.
> Built as a single-file static site — no frameworks, no dependencies, just HTML/CSS/JS.

🔗 **TikTok Store:** [@silentlogos1882](https://www.tiktok.com/@silentlogos1882)
🌐 **Live Site:** *(add your GitHub Pages URL here once deployed)*

---

## What's in the Box

| File | Description |
|------|-------------|
| `index.html` | The website — styles, scripts, and layout |
| `products.json` | Product catalog |
| `README.md` | This file |

---

## How Products Work

Products are stored in **`products.json`** and photos in **`images/`**. Don't edit them by hand —
use the **Admin Panel** (footer → Admin Panel):

1. Add/edit products, upload photos, or **Import from Facebook** (CSV).
2. Press **Publish to website** — the admin Worker commits the changes to this repo and
   GitHub Pages updates the site in about a minute.

Setup of the admin Worker (`silentlogos1882-worker`) is in its `SETUP.md`.

| File | Purpose |
|------|---------|
| `index.html` | The website — layout, styles, scripts |
| `products.json` | Product catalog (written by the admin panel) |
| `images/` | Product photos (written by the admin panel) |
| `fb-import-template.csv` | Template for importing Facebook listings |

---

## Deploy to GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set **Source** to `main` branch, `/ (root)` folder
4. Click **Save** — your site will be live at:
   ```
   https://<your-username>.github.io/<repo-name>/
   ```
5. Paste that URL into the Live Site link above

### Optional: Custom Domain
- Buy a domain (e.g. `silentlogos1882.com`) from Namecheap or Google Domains
- In GitHub Pages settings, add it under **Custom domain**
- Add a `CNAME` record pointing to `<your-username>.github.io` with your domain registrar

---

## Tech Stack

- **HTML5 / CSS3 / Vanilla JS** — zero dependencies
- **Google Fonts** — Orbitron, Share Tech Mono, Rajdhani
- **Canvas API** — animated digital rain effect
- **IntersectionObserver API** — scroll-reveal animations
- **Cloudflare Worker** (`silentlogos1882-worker`) — admin login + publishing to GitHub

---

## License

© 2026 Silent Logos 1882 · Omeplant Nutrition LLC. All rights reserved.
