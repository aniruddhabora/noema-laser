# Noema-Laser — Landing page

A single-page marketing site for Noema-Laser, designed to be hosted on GitHub Pages.

## Quick deploy (10 minutes)

1. Create a new public repo on GitHub: `noema-laser` (or whatever name you prefer).
2. Drop these files into the repo root:
   ```
   index.html
   README.md
   images/        ← create this folder (see below)
   CNAME          ← only if using a custom domain (see below)
   ```
3. Push to `main` branch.
4. GitHub repo → **Settings → Pages → Source:** `Deploy from a branch` → branch `main`, folder `/ (root)` → **Save**.
5. Wait ~2 minutes. The URL `https://YOUR-USERNAME.github.io/noema-laser/` will be live.

The site works without any images — it'll show clean placeholder blocks until you add the real photos.

## Images (when you have them)

Create an `images/` folder in the repo with these four files. The HTML already references them by these exact names — no code changes needed.

| Filename | Source | Description |
|---|---|---|
| `images/hero-clinician.jpg` | Slide 1 of your deck | Wide photo of clinician treating patient with the Noema device |
| `images/skin-diagram.png` | Slide 6 of your deck | Skin tissue cross-section with laser beam |
| `images/device.png` | Slide 1 of your deck (crop the device portion) | Product shot of the Noema-Laser device on its cart |
| `images/clinician-closeup.jpg` | Slide 1 (or any clinical photo) | Close-up of clinician working on patient |
| `images/clinic-exterior.jpg` | optional | Modern dermatology clinic exterior |

**To extract images from your PowerPoint deck:**
- Save the .pptx → open in PowerPoint → right-click each image → "Save as Picture"
- Or: rename `.pptx` to `.zip`, unzip, images live in `ppt/media/`

**Image sizing recommendations:**
- Hero image: 1600×1200px minimum, JPEG, ~250KB after compression
- Diagrams: 800×800px, PNG with transparent or solid background
- Product shot: 1000×1000px, PNG with white background works best
- Use [tinypng.com](https://tinypng.com) to compress before committing

## Custom domain (optional, +30 minutes)

1. Buy `noemalaser.com` from Namecheap or Porkbun ($12/yr).
2. Add a file named `CNAME` (no extension) to the repo root with just one line:
   ```
   noemalaser.com
   ```
3. In your registrar's DNS panel, add these four A records pointing to GitHub's IPs:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
   Plus a CNAME record: `www` → `YOUR-USERNAME.github.io`
4. Wait ~30 minutes for DNS to propagate.
5. GitHub repo → Settings → Pages → enter `noemalaser.com` in **Custom domain** → check **Enforce HTTPS** once available (5–15 min after domain verification).

## Editing content

Open `index.html` in any editor. The file is self-documenting — section comments are HTML structure, and every editable text string is in plain text (no React, no Vue, no build step).

Common edits:

- **Email:** search for `aniruddha.bora@txstate.edu` and replace.
- **Tagline:** line beginning `Real-time intelligence`.
- **Headline:** line beginning `AI-Guided Precision`.
- **Stats at bottom:** the three numbers (2 patents, 2 publications, 1 NMI submission).
- **Patent number in footer:** `63/996,145`.

## Tech notes

- **Framework:** none. Plain HTML + Tailwind CSS via CDN.
- **No build step.** Edit, commit, push, live.
- **Performance:** ~1 HTTP request for HTML, 1 for Tailwind CDN, 1 for Google Fonts. ~50KB total before images.
- **Mobile responsive.** Grid layouts collapse to single column on small screens.
- **SEO basics:** title, description, OG tags included. Add structured data later if needed.
- **Analytics:** add Plausible or Google Analytics via a script tag in `<head>` if you want traffic data.

## Pre-pitch checklist

- [ ] Site is live at the chosen URL.
- [ ] Email link works (clicking it opens an email client).
- [ ] All five images are loaded (or placeholders are gracefully visible).
- [ ] Site renders correctly on mobile (test from your phone before the pitch).
- [ ] QR code (generated separately) points to the live URL, not a localhost or staging link.
- [ ] Test scan a printed QR card from across a room before Friday.

## License

Content © 2026 Aniruddha Bora / Noema-Laser. Code MIT-licensed if you want to share the template.
