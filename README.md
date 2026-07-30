# Links

Shapang Business Links

A single self-contained `index.html`: no build step, no frameworks, no JavaScript,
no tracking. Designed mobile-first for an NFC business-card tap.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire site — markup, CSS and inline SVG icons |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is (skip Jekyll) |

## Edit your details

Everything personal lives in `index.html`:

| What | Where |
| --- | --- |
| Name | `<h1 class="name">` — the line marked `EDIT: your name` |
| Tagline | `<p class="tagline">` — the line marked `EDIT: your one-line tagline` |
| The five URLs | the `href="YOUR_*_URL"` attributes inside `<nav>`, all in one block |
| Title / description | `<title>` and `<meta name="description">` in `<head>` |
| Link-preview (OG) tags | the `og:` / `twitter:` block in `<head>` — replace `YOUR_SITE_URL` |

The five URL placeholders are unique strings, so one find-and-replace each does it:

```
YOUR_GITHUB_URL
YOUR_LINKEDIN_URL
YOUR_SOUNDCLOUD_URL
YOUR_YOUTUBE_URL
YOUR_TWITCH_URL
```

Optional: drop a 1200×630 `og-image.png` in the repo root so shared links show a
preview image (the meta tags already point at that path).

## Enable GitHub Pages

1. This repo already lives at [github.com/vlshapang-code/Links](https://github.com/vlshapang-code/Links).
2. On GitHub, open the repo → **Settings** → **Pages** (left sidebar).
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Set **Branch** to `main` and folder to `/ (root)`, then click **Save**.
5. Wait ~1 minute. The site goes live at:

```
https://vlshapang-code.github.io/Links/
```

That URL is what the NFC tag should point to. If you later add a custom domain,
set it under the same Pages screen and point the tag at the domain instead.

## Local preview

```bash
open index.html
```

No server needed — it is one static file.
