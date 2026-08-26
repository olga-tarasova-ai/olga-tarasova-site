# Olga Tarasova — Portfolio Site

Static site, no build step. Open `index.html` directly or deploy the whole
folder as-is to any static host (Netlify, Vercel, GitHub Pages).

## Structure

- `index.html` — the whole site (one page, UA/EN toggle)
- `images/` — photos used on the site; `images/uploads/` is where the
  admin panel saves new photos you upload
- `content/site.json` — editable text (hero, about, services, contact,
  portfolio category labels, process steps) and the 6 Portfolio direction
  background photos + 7 Services card photos (editable via the admin panel;
  hero/about/process photos are final and stay in the code).
- `favicon.ico` + `images/favicon-*.png`, `apple-touch-icon.png`,
  `android-chrome-*.png` — browser tab icon (OT monogram); linked from
  `index.html`, not editable via the admin panel.
- `content/legacy-cases.json` — the 21 original portfolio cases (photos,
  videos, text, captions, block order). Each case keeps its own bespoke
  layout (image/video grid or before-after slider) — only the content
  inside that layout is edited through the admin panel, not the layout
  itself.
- `content/cases.json` — brand new portfolio cases added through the
  admin panel, on top of the 21 original ones; these use a single simple
  gallery template.
- `admin/` — the CMS admin panel (Decap CMS). Open `/admin` on the live
  site to log in and edit `content/site.json`, `content/legacy-cases.json`
  and `content/cases.json` through a form, without touching code.

## Before the admin panel works

Edit `admin/config.yml`:

- `backend.repo` — set to `your-github-username/your-repo-name`
- `site_url` / `display_url` — set to your live Netlify URL

Then in Netlify: **Project configuration → Access & security → OAuth →
Install provider → GitHub** (see the full setup guide you were given
alongside this file).

## Editing text/photos without the admin panel

`content/site.json`, `content/legacy-cases.json` and `content/cases.json`
are plain JSON — safe to open and edit directly (in GitHub's web editor,
or any text editor), commit, and Netlify redeploys automatically in under
a minute.
