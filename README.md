# HeatTreatPro — Heat Treat Service Directory

Niche directory of commercial heat treat shops, split into two buyer categories:

- **Small Batch / Custom** — knife makers, tool & die, one-offs, small machine shops
- **Large Scale / Industrial** — aerospace, automotive, heavy industry (incl. NADCAP-certified)

## Structure

```
index.html      # The whole site (single file for now)
shops/          # Will hold per-shop data/pages as the directory grows
```

## Deploying to Cloudflare Pages (free, unlimited bandwidth)

1. Push this repo to GitHub:
   ```
   gh repo create heattreapro --public --source=. --push
   ```
2. At https://dash.cloudflare.com → Workers & Pages → Create application → Pages → Connect to Git → pick the repo
3. Build settings: **leave all blank** (no build step — it's static HTML)
4. Deploy. Site goes live at `heattreapro.pages.dev` in ~1 minute

## Custom domain

1. Buy a domain (~$12/yr — Namecheap, Porkbun, or Cloudflare Registrar)
2. Cloudflare Pages → Custom domains → add it (Cloudflare auto-creates the DNS records)
3. Google Search Console: submit the sitemap once live

## Adding shops

Edit `index.html` directly — each shop is a `<div class="shop-card">` block inside its category section. Copy an existing card and change:

- Shop name, location line (city, state + street address), services line
- Tags (`<span class="tag">`) for processes/materials/certs
- NADCAP tag: add `<span class="tag nadcap">NADCAP</span>` if certified
- Link the "View Site" button to their real website (never leave a dead `#` link)

Keep the two sections separate — small-batch and large-scale are different buyers. When we hit ~50+ shops, split into per-shop pages under `shops/` for SEO.

## What's still TODO before launch

- [ ] Verify every shop is still in business (phone check or site check)
- [ ] Fill remaining gaps: phone numbers, batch-size minimums, turnaround times
- [ ] Get The Monty's Top 50 list (themonty.com blocks bots — grab it manually)
- [ ] Replace "HeatTreatPro" name + logo with final branding
- [ ] Add a "Submit Your Shop" form (or start with a contact email)
- [ ] Basic analytics (Cloudflare has free built-in analytics)
