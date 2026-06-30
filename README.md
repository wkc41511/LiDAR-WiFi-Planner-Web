# LiDAR WiFi Planner — Website

Public website for the iOS and macOS app *LiDAR WiFi Planner*: the landing page, product guide, and the support, privacy, and terms pages linked from its App Store listing.

It is a small static site hosted on GitHub Pages, with no build step. Page text and translations live in `site.js` (and `product.js` for the guide), which render the active language at runtime and remember the visitor's choice. Five languages are supported — Traditional Chinese, English, Japanese, Korean, and Simplified Chinese — with browser-language detection and a manual selector.

## Files

- `index.html` — landing page
- `product.html` / `product.js` — product guide and its generated interface mockups
- `support.html` — support and contact
- `privacy.html` — privacy policy
- `terms.html` — terms of use
- `site.js` — localized content and language routing for the support and legal pages
- `styles.css` — shared styling (light/dark, glass cards, layout)
- `assets/` — background artwork

Each page is a thin shell whose header, language and theme selectors, and `#content` article are populated from `site.js` at runtime. The support, privacy, and terms pages also carry a static English copy of their content inline, so they remain readable for clients and crawlers that do not run JavaScript.

## Editing content

Text is organized by language and page in the `translations` object in `site.js` (`meta` rows and `sections` per page). Update each supported language and commit — there is nothing to compile. When changing the support, privacy, or terms copy, update the matching static block in that page's HTML so the no-JavaScript version stays in sync.

## Local preview

```bash
python3 -m http.server
```

Then open http://localhost:8000.

## Deployment

GitHub Pages serves the `main` branch as-is; `.nojekyll` keeps files unprocessed. A push to `main` goes live within about a minute.
