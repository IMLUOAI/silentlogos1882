# Silent Logos 1882 — Official Store Website

> Cyberpunk-themed landing page for the **Silent Logos 1882** TikTok Shop.
> Built as a single-file static site — no frameworks, no dependencies, just HTML/CSS/JS.

🔗 **TikTok Store:** [@silentlogos1882](https://www.tiktok.com/@silentlogos1882)
🌐 **Live Site:** *(add your GitHub Pages URL here once deployed)*

---

## What's in the Box

| File | Description |
|------|-------------|
| `index.html` | The entire website — styles, scripts, and content all in one file |
| `README.md` | This file |

---

## Products Featured

- 🚽 **Topseat Magnetic Toilet Seats** — quick-release, slow-close bathroom upgrade
- 🏮 **Solar Lanterns & Garden Lamps** — auto on/off, no wiring needed
- 🐾 **Hollow Projection Night Lamp** — casts paw print patterns on walls & ceilings
- 🌿 **doTERRA PastTense Stick** — natural essential oil tension relief
- 🔔 **4pcs Vintage Gold Cowbells** — rustic farmhouse & holiday décor
- 🍴 **Stainless Cutlery Set** — mirror-polished, dishwasher safe

---

## How to Edit

Everything lives in `index.html`. Open it in any text editor (VS Code recommended).

**To update a product card**, search for the product name and edit:
- The emoji icon in `prod-img-wrap`
- The category label in `prod-cat`
- The product name in `prod-name`
- The description in `prod-desc`
- The price in `prod-price`
- The link `href` in `prod-btn`

**To update the TikTok link**, search for `silentlogos1882` and replace with your new handle if it ever changes.

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

---

## License

© 2026 Silent Logos 1882. All rights reserved.
