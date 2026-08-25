# RF Strategic Ltd. — website

Static one-page site. No build step — plain HTML/CSS, deployable as-is on GitHub Pages.

## Structure

```
├── index.html              ← homepage (hero, approach, services, results, about, contact)
├── 404.html
├── privacy-policy/index.html
├── robots.txt
├── sitemap.xml
├── llms.txt
├── assets/
│   ├── rf-icon.png         ← real logo mark, background removed
│   ├── rf-banner.jpg       ← real brand banner (used as a full-width strip under the hero)
│   └── rf-headshot.jpg     ← real photo of Robert, founder
└── README.md
```

## What's real vs. placeholder

**Real:** logo, banner, and Robert's headshot in `assets/`.

**Still placeholder — replace before launch:**
- Hero, approach-section, and results-section backdrop photos are hotlinked from Pexels (free stock, no attribution required, but not self-hosted). Swap for real office/team photography and move the files into `assets/` when available.
- Results/testimonial quote is written copy, not a real client quote.
- Robert's bio paragraph in the About section is a placeholder line.
- Contact details (email, phone, WhatsApp) are marked "TBC" in the CTA band and footer.
- `privacy-policy/index.html` is a minimal honest draft (states no tracking is active) — needs proper legal review before go-live, and an update if analytics/a pixel gets added later.
- Domain (`rfstrategic.co.uk`) is already owned, so `robots.txt`, `sitemap.xml`, and the meta tags in `index.html` all reference it, and a `CNAME` file is included at repo root. None of this takes effect until DNS is pointed and the custom domain is switched on in GitHub Pages settings — see Deploy step 3.

## Deploy (GitHub Pages)

1. Push this repo to GitHub (public repo). The site will build immediately from `index.html`, but stays reachable only at the default `github.io` URL until step 3.
2. Repo Settings → Pages → deploy from the `main` branch, root folder.
3. When ready to go live: point DNS for `rfstrategic.co.uk` (already owned) at GitHub Pages, then enable the custom domain in Pages settings — the `CNAME` file is already in the repo, so GitHub should pick it up automatically:
   ```
   A     @    185.199.108.153
   A     @    185.199.109.153
   A     @    185.199.110.153
   A     @    185.199.111.153
   CNAME www  <github-username>.github.io
   ```
4. Submit `sitemap.xml` to Google Search Console.
5. Swap remaining placeholder photography and copy per the list above.

## Notes

- Single page, anchor-linked nav (`#approach`, `#services`, `#about`, `#contact`) — no separate get-started/intake flow has been built yet; add one if RF wants a form instead of a direct booking CTA.
- No analytics/tracking pixel installed yet. Add one (and update the privacy policy accordingly) only once it's actually implemented.
