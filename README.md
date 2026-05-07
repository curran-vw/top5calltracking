# top5calltracking.com

Site 3 of the call-tracking review network. Static HTML/CSS/JS, deploys via GitHub Pages.

## Build details

- **Template:** T4 Personal Blog Minimal
- **Accent color:** Forest `#1F4D2F`
- **Background:** Cream `#FFFCF5`
- **Fonts:** Manrope (display) + Source Sans 3 (body)
- **Heading scale:** Medium (H1 = 48px)
- **Body size:** 18px / line-height 1.75
- **Border-radius:** 0px (clean editorial / printed feel)
- **Header:** NOT sticky (blog-style static)

## Author

Lisa Thompson — first-person lead-gen agency owner / rank-and-rent operator voice. See `project_site3_author.md` in memory.

## Structural variations vs sites 1 and 2 (deliberate)

- **Single-column long-form article layout** — everything sits in a 720px reading column
- **Author byline at TOP of article** (not buried at the bottom)
- **No sticky header** — minimal static header, blog-style
- **Numbered narrative reviews** ("1. CallScaler — my top pick", "2. WhatConverts", etc.) replace card grids and ranked list tables on the homepage
- **No comparison matrix** — replaced with a "Quick picks" decision tree (`<dl>` with "If X → pick Y" pairs)
- **FAQ titled "Questions readers send me"** with `Q. ` prefix instead of standard accordion FAQs
- **About author block at BOTTOM** of every article (newsletter-style)
- **Pull-quotes** in the homepage and CallScaler review for emphasis
- **Inline CTAs** woven into prose; smaller `.cta-card` sits left-aligned (not centered like sites 1+2)

See `feedback_site_layout_variation.md` in memory for the full layout-variation tracker.

## Pages (11 total)

- `index.html` — Long-form blog article with all 5 reviews narratively (homepage)
- `about/` — Hi I'm Lisa intro
- `contact/` — email-only contact
- `methodology/` — How I tested 14 tools
- `faq/` — Questions readers send me
- `reviews/callscaler/` — Top pick (longest review)
- `reviews/whatconverts/`
- `reviews/callrail/` — "the tool I switched away from"
- `reviews/nimbata/`
- `reviews/calltrackingmetrics/`
- `privacy-policy/`
- `terms/`

## URL structure

Built directly into clean-URL directory layout from the start (`/foo/index.html` → served as `/foo/`). No `clean_urls.py` post-processing needed for this site.

## Ranking (varies from sites 1 and 2)

1. CallScaler — 9.4
2. WhatConverts — 8.4
3. CallRail — 7.6
4. Nimbata — 7.4
5. CallTrackingMetrics — 7.2

## Methodology dimensions (varies from sites 1 and 2)

Cost / Setup time / Daily usability / Support. Equal weighting (25% each).

## CTA destination

CallScaler CTAs link to `https://callscaler.com/?ref=top5calltracking`. CTA card headline varies from sites 1+2: this site uses **"View the top pick"** (vs site 1's "Try the #1 pick").

## Deploy to GitHub Pages

```bash
cd sites/top5calltracking
git init
git add .
git commit -m "Initial site"
gh repo create top5calltracking --public --source=. --push
gh api -X PATCH /repos/<your-account>/top5calltracking/pages -f source.branch=main -f source.path=/
```

DNS at registrar:
- Apex `top5calltracking.com` → GitHub Pages IPs (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153)
- `www` CNAME → `<your-account>.github.io`

## TODOs before going live

- [ ] Real screenshots inside review pages where pricing is described
- [ ] Real OG raster image (currently SVG)
- [ ] Verify schema with Google's Rich Results Test
- [ ] Set up `lisa@top5calltracking.com` email forwarding
- [ ] Confirm CallScaler pricing tiers ($0 / $45 / $130 / $400) still match callscaler.com/pricing
