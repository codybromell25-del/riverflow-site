# Riverflow Pilates — Website

Live static site for Riverflow Pilates, Kilsharvan. Two self-contained pages:

- `index.html` — homepage
- `book.html` — booking page (embeds The Current scheduler)

Every image and font is inlined, so there is **no build step** — Vercel just serves these files as-is.

---

## One-time setup (host on Vercel via GitHub)

1. Create a new empty repo on GitHub, e.g. `riverflow-site`.
2. In this folder, run:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/riverflow-site.git
   git push -u origin main
   ```
3. Go to https://vercel.com → **Add New → Project → Import Git Repository** → pick `riverflow-site`.
   - Framework Preset: **Other**
   - Build Command: *(leave empty)*
   - Output Directory: *(leave empty / `.`)*
   - Click **Deploy**.
4. You get a permanent URL like `https://riverflow-site.vercel.app`. (Add your own domain later under Project → Settings → Domains.)

---

## Making edits (the URL never changes)

Every push to `main` auto-deploys to the **same** URL.

```bash
# make your edits to index.html / book.html
git add .
git commit -m "Update prices"
git push
```

Vercel redeploys in a few seconds.

### Editing tips
- Small text changes (prices, phone numbers, copy) are easy: search the file for the current text and replace it.
- These files are large because images are embedded — that's expected and fine.
- For big structural/design changes, edit the source design file and re-bundle (see below), rather than hand-editing the bundled HTML.

---

## Source of truth

The editable source lives in the parent project as `Riverflow - Soft Studio.dc.html`
(homepage) and `Riverflow - Soft Studio - Book.dc.html` (booking). The `index.html`
and `book.html` here are *bundled outputs* of those. For major changes, edit the
source and regenerate these two files.
