# Silent Logos 1882 — Online Store

Storefront for **Silent Logos 1882** (Omeplant Nutrition LLC) — home goods, lighting, décor and more,
also sold on TikTok Shop and Facebook Marketplace.

🌐 **Live site:** https://silentlogos1882.wareplatform.com
🔐 **Admin panel:** https://silentlogos1882.wareplatform.com/?edit (or footer → *Admin Panel*)
🔗 **TikTok:** [@silentlogos1882](https://www.tiktok.com/@silentlogos1882)

---

## How it works

```
Admin panel (browser) ──► silentlogos-api.wareplatform.com ──► this GitHub repo ──► GitHub Pages (live site)
                           (Cloudflare Worker)                  products.json + images/
```

- The website is a static page (`index.html`) that loads the catalog from `products.json`.
- The **admin panel** edits products as a private draft. **Publish to website** sends the draft to the
  Cloudflare Worker, which commits `products.json` and the photos to this repo in one commit.
  GitHub Pages updates the live site about a minute later.
- The Worker lives in a separate folder/repo, **`silentlogos1882-worker`** — setup steps are in its `SETUP.md`.

## Files

| Path | What it is |
|------|------------|
| `index.html` | The website — layout, styles and scripts |
| `products.json` | Product catalog — **written by the admin panel** |
| `images/` | Product photos — **written by the admin panel** |
| `fb-import-template.csv` | Spreadsheet template for importing Facebook listings |
| `CNAME` | Custom domain for GitHub Pages |

> Don't edit `products.json` or `images/` by hand while also publishing from the admin panel —
> the two will conflict. If you must edit them in Git, run `git pull` first.

---

## Managing products (admin panel)

**Add or edit** — fill in name, price, category, tag (HOT / NEW / SALE), status, Facebook listing URL
and description, then **Save Product**.

**Photos** — up to 20 per product. *Choose photos* (hold **Ctrl** to pick several), drag & drop, or paste.
Click a thumbnail to make it the **MAIN** photo. Photos are resized in the browser (max 1400 px)
and never enlarged on the storefront. iPhone **HEIC** photos must be saved as JPG first.

**Sold items** — *Mark sold* in the product list (or set Status). The card shows SOLD and Buy Now is disabled.

**Publish** — changes stay private until you press **Publish to website** (top bar turns orange when
there are unpublished changes). **Discard changes** reverts to what's live.

### Import from Facebook (CSV)

Admin panel → **Import from Facebook** → download `fb-import-template.csv`, one row per listing:

`title, price, category, description, facebook_url, photos, status`

- `photos`: photo links separated by `|` — they're downloaded into `images/` when you publish.
  Facebook photo links expire, so publish soon after importing.
- Re-importing is safe: rows with the same Facebook URL (or title) update the existing product.
- A Meta Commerce Manager catalog export (`title, price, image_link, availability, …`) also works.

---

## Safety features

- Publishing that **removes 3+ products** asks for confirmation and lists them.
- Publishing an **empty catalog** requires typing `DELETE ALL` — and the Worker refuses it anyway.
- The Worker rejects publishes from an **outdated tab or another device** instead of overwriting newer changes.
- The admin password is checked by the Worker (Cloudflare secret) — it is **not** in this repo.

### Undoing a bad publish

Every publish is a Git commit, so nothing is ever truly lost:

```bash
git pull
git log --oneline -- products.json          # find the last good "Publish … products" commit
git checkout <good-commit> -- products.json images
git commit -m "Restore catalog" && git push
```

---

## Storefront features

- Category filter (categories from imports are added automatically)
- Product albums: arrows, photo counter, thumbnails; click a photo for full-screen view
  (arrow keys / swipe, Esc to close)
- Sold items shown last with a SOLD badge
- Buy Now → the product's Facebook listing (Stripe checkout coming next)

## Tech

HTML / CSS / vanilla JavaScript · Google Fonts (Orbitron, Share Tech Mono, Rajdhani) ·
Canvas star background · GitHub Pages hosting · Cloudflare Worker for admin login & publishing

---

© 2026 Silent Logos 1882 · Omeplant Nutrition LLC. All rights reserved.
