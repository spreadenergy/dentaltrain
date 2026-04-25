# Dental Train — Investor Landing Page

A single-file static site. No build step. Drop it on any static host.

```
.
├── index.html
├── assets/
│   ├── logo.png
│   └── journey-infographic.png
└── README.md
```

---

## Before you share the link

Open `index.html` in your editor and find these two items (both marked with `FOUNDER:` comments — use Cmd+F):

1. **Email address.** Currently `invest@dentaltrain.app`. Change it to the inbox you actually monitor. It appears in three places: the two "Request the Deck" buttons (hero and footer) and the footer band.
2. **Calendar link.** The "Book a Call" buttons currently point to `#`. Replace `href="#"` with your Calendly, SavvyCal, or Google Calendar appointment URL. Both buttons are tagged `data-calendar-link` so they are easy to find.

---

## Preview locally

Just double-click `index.html` — it opens in your browser with no server required.

If you want a local server (some browsers restrict features over `file://`):

```bash
# Python 3
python3 -m http.server 8000
# then open http://localhost:8000
```

---

## Deploy to Vercel (fastest path)

**Option A — drag and drop (no CLI):**

1. Go to [vercel.com](https://vercel.com) and sign in (free).
2. Click **Add New → Project**.
3. Drag this whole folder onto the import area.
4. Click **Deploy**. You'll get a `*.vercel.app` URL in ~10 seconds.

**Option B — CLI (one command):**

```bash
cd dentaltrain-site
npx vercel
```

Follow the prompts. Accept defaults. The first deploy gives you a preview URL; run `npx vercel --prod` to promote it.

### Point `dentaltrain.app` to it

1. In the Vercel project dashboard, go to **Settings → Domains**.
2. Add `dentaltrain.app` (and `www.dentaltrain.app`).
3. Vercel shows you the DNS records to set at your registrar. Set them. Done.

---

## Deploy to Netlify

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop).
2. Drag this folder onto the drop zone.
3. You get a URL instantly. Add `dentaltrain.app` under **Domain management**.

---

## Deploy to Cloudflare Pages

1. Go to [pages.cloudflare.com](https://pages.cloudflare.com) → **Create a project** → **Direct Upload**.
2. Upload this folder. No build command, no build output directory needed.
3. Add `dentaltrain.app` under **Custom domains** (DNS is automatic if the domain is on Cloudflare).

---

## When you want to edit later

Everything is in `index.html`. Open the file, change the words, save, re-deploy. There is no framework, no build step, no node_modules.

- **Colors** are defined once in the `tailwind.config` block at the top of the file.
- **Copy** is inline in each `<section>`.
- **Images** live in `assets/`. Swap in new ones with the same filenames if you want.

---

## Optional — add a social preview image

When this link is shared on LinkedIn, iMessage, or Slack, it will show a preview. For a proper preview, add a **1200×630 PNG** at `assets/og-image.png`. The Open Graph meta tags in `<head>` already reference it — no code change needed.

---

## Optional — add analytics later

Paste one of these just before `</body>` in `index.html`:

- [Plausible](https://plausible.io) — privacy-friendly, no cookie banner needed
- [Fathom](https://usefathom.com) — same idea
- [Vercel Analytics](https://vercel.com/docs/analytics) — one line if hosted on Vercel

Avoid Google Analytics; it triggers a cookie banner requirement in many jurisdictions and you don't need session-level data for an investor page.
