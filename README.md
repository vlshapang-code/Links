# Links

Shapang Business Links

A single self-contained `index.html`: no build step, no frameworks, no external
JavaScript, no tracking. Designed mobile-first for an NFC business-card tap.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire site — markup, CSS and inline SVG icons |
| `og-image.png` | Link-preview image (1200×630) used by the OG/Twitter tags |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is (skip Jekyll) |

## Edit your details

Everything personal lives in `index.html`. See the `EDIT ME` comment block at
the very top of the file for the full map; the short version:

| What | Where |
| --- | --- |
| Name / tagline | `<h1 class="name">` and `<p class="tagline">` in `<header>` |
| Phone / emails | the `.contact` section, just above the link list |
| The six platform URLs | the `href` attributes inside `<nav>`, all in one block |
| Booking form endpoint | `YOUR_FORMSPREE_ENDPOINT` — see **Booking requests** below |
| Title / description | `<title>` and `<meta name="description">` in `<head>` |
| Link-preview (OG) tags | the `og:` / `twitter:` block in `<head>` |

Optional: swap `og-image.png` for your own 1200×630 image to change the link-preview picture.

## Booking requests ("Book Now")

The first item in the link list opens a popout form (name, phone, a Music/Science
dropdown, and a message) instead of navigating away. It's pure CSS/HTML — no JS —
but since GitHub Pages can't run server code, delivering the email needs a
third-party form backend: it POSTs to [Formspree](https://formspree.io)
(`<form action="...">` near the end of `index.html`, just before `</body>`).
Both Science and Music requests land in the same Formspree inbox — the Interest
field on each submission says which. Formspree required confirming the very
first submission by email before later ones go through; if requests ever stop
arriving, check that confirmation didn't get missed. To point the form at a
different Formspree form later, swap the `action=` URL there.

## Enable GitHub Pages

1. This repo already lives at [github.com/vlshapang-code/Links](https://github.com/vlshapang-code/Links).
2. On GitHub, open the repo → **Settings** → **Pages** (left sidebar).
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Set **Branch** to `main` and folder to `/ (root)`, then click **Save**.
5. Wait ~1 minute. The site goes live at:

```
https://vlshapang-code.github.io/Links/
```

## Custom domain

The site is set up to serve from **https://shapangg.com/** (root, not a subpath).
The `CNAME` file in the repo root holds that domain — GitHub Pages reads it
directly, so don't delete or rename it, and keep it as one line with no protocol
(`shapangg.com`, not `https://shapangg.com`).

Two things must both be true for the domain to work:

1. **Repo side** — `CNAME` present (done), and the domain entered under
   **Settings → Pages → Custom domain**.
2. **DNS side** — at whoever registered `shapangg.com`, four `A` records on the
   apex pointing at GitHub's Pages IPs (`185.199.108.153`, `185.199.109.153`,
   `185.199.110.153`, `185.199.111.153`), plus optionally a `CNAME` record for
   `www` pointing at `vlshapang-code.github.io`.

Once DNS resolves, tick **Enforce HTTPS** on the Pages screen. The absolute URLs
in `index.html` (og:image, og:url, and the form's `_next` redirect) already point
at `shapangg.com`. The NFC tag should point at the custom domain too.

## Local preview

```bash
open index.html
```

No server needed — it is one static file.
