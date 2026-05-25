# SkyFarms website — deployment bundle

## Files
- `index.html`, `investors.html`, `partner.html`, `technology.html`, `farms.html` — page templates
- `styles.css` — shared stylesheet (linked by all 5 pages)
- `_redirects` — clean-URL rewrites for Netlify and Cloudflare Pages

## Deploy
Drop the folder onto any static host:
- **Netlify**: drag-and-drop at app.netlify.com/drop, or `netlify deploy --dir=.`
- **Cloudflare Pages**: `wrangler pages deploy .`
- **Vercel**: `vercel --prod`
- **GitHub Pages / S3 / nginx**: just upload the files

Cross-page links use `.html` extensions and will resolve natively on any
static host. The `_redirects` file enables clean URLs (e.g. `/investors`
instead of `/investors.html`) on Netlify and Cloudflare Pages.

## OG images
Each page references `/og/og-{name}.jpg` for social previews. Create a
1200x630 image for each page and upload to an `/og/` folder at the site root.

## Canonical URLs
All canonical tags currently point to skyfarms.ca with the `.html` extension.
If you switch to clean URLs in production, update the `<link rel="canonical">`
in each page's `<head>` to match.
