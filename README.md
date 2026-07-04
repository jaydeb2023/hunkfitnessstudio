# Hunk Fitness Studio — Website Files

This folder has three files that work together:

| File | What it's for |
|---|---|
| `index.html` | The actual website (design, content, booking form, chatbot, map, everything). |
| `robots.txt` | Tells search engine crawlers (Google, Bing, etc.) which pages they're allowed to crawl, and points them to your sitemap. |
| `sitemap.xml` | A list of every page on your site, so search engines find and index it faster. Right now it lists just the one homepage — add more `<url>` entries here if you ever split the site into separate pages (e.g. a blog or a dedicated pricing page). |

## Where these three files go

All three must sit in the **root** of your domain — not in a subfolder — so they're reachable at exactly these addresses:

```
https://www.hunkfitnessstudio.in/index.html   (or just /)
https://www.hunkfitnessstudio.in/robots.txt
https://www.hunkfitnessstudio.in/sitemap.xml
```

If your hosting is cPanel / Hostinger / GoDaddy-style: upload all three into `public_html/`.
If it's Netlify/Vercel: drop them in the project's root/`public` folder.

## One-time setup after uploading

1. **Google Search Console** → Add your property (`hunkfitnessstudio.in`) → Sitemaps → submit `sitemap.xml`.
2. **Bing Webmaster Tools** → same idea, submit the sitemap there too.
3. Double check `https://www.hunkfitnessstudio.in/robots.txt` loads in a browser and shows plain text (not a 404).
4. Update the `<lastmod>` date in `sitemap.xml` whenever you make a meaningful content change (new photos, new pricing, etc.) — it's a small nudge that tells crawlers "come re-check this."

## About the logo file reference

`sitemap.xml` and the schema in `index.html` reference `https://www.hunkfitnessstudio.in/logo.png`. Right now your logo is embedded directly inside `index.html` (so the page works standalone), but for the cleanest SEO setup:

1. Save your bull-mascot logo as `logo.png` in the same root folder.
2. That way `logo.png` is a real, independently-loadable file at that URL, which Google's Business/Local Search and rich-result previews prefer over a data-embedded image.

## If you add more pages later

Only if you split things up (e.g. `/pricing.html`, `/blog/`) — add a matching `<url>` block to `sitemap.xml` for each new page, and make sure `robots.txt` still says `Allow: /` (it already covers everything under the root).
