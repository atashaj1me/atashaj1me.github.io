# atashaj1me.github.io

Personal site for Thang Nguyen. Hand-written HTML + CSS, no build step.
Hosted on GitHub Pages from the `main` branch root.

## Local preview

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

1. Create repo `atashaj1me.github.io` on GitHub (must match the username exactly).
2. Push the contents of this folder to `main`:
   ```sh
   git init && git add . && git commit -m "init"
   git branch -M main
   git remote add origin git@github.com:atashaj1me/atashaj1me.github.io.git
   git push -u origin main
   ```
3. In repo Settings → Pages: Source = `Deploy from a branch`, Branch = `main` / `/ (root)`.
4. Site lives at <https://atashaj1me.github.io> after ~1 minute.

The `.nojekyll` file disables GitHub's Jekyll preprocessing so files are served as-is.

## File map

```
index.html        bio + featured paper + reading list
research.html     working papers + coursework
wip.html          drafts in progress
notes.html        investment memos (titles + mailto)
blog/index.html   blog post index
blog/YYYY-MM-DD-slug.html  individual posts
cv.html           HTML CV (+ link to assets/pdf/cv.pdf)
404.html          custom not-found page
assets/css/site.css  the only stylesheet
assets/img/       headshot + figures
assets/pdf/       cv.pdf, paper PDFs, slide decks
```

## Adding content (copy-paste templates)

### A new working paper — paste into `research.html`, under `Working papers`

```html
<div class="paper">
  <span class="title">Title here</span>
  <span class="meta">Working paper · 2026 · with Coauthor</span>
  <p class="abstract">Three to five line abstract.</p>
  <span class="links">
    <a href="assets/pdf/paper-slug.pdf">[PDF]</a>
    <a href="#">[BibTeX]</a>
    <a href="#">[SSRN]</a>
  </span>
</div>
```

### A coursework entry — paste into `research.html`, under `Coursework`

```html
<div class="paper">
  <span class="title">Title here</span>
  <span class="meta">Coursework — ECON 301, Fulbright University Vietnam · 2025</span>
  <p class="abstract">Short abstract.</p>
  <span class="links"><a href="assets/pdf/coursework-slug.pdf">[PDF]</a></span>
</div>
```

### A WIP entry — paste into `wip.html`

```html
<div class="paper">
  <span class="title">Project title</span>
  <p class="status">Draft — last updated 2026-MM.</p>
  <p class="abstract">Short description.</p>
  <span class="links">
    <a href="mailto:thang.c.ngn@gmail.com?subject=Draft%20request">[request draft]</a>
  </span>
</div>
```

### An investment memo — paste into `notes.html`, under the right category

```html
<div class="note">
  <span class="meta">2026-MM</span>
  <div><span class="title">Memo title</span> — <span class="blurb">one-line summary</span>
    <a href="mailto:thang.nguyen@ochnaresearch.work?subject=Memo%20request%20%E2%80%94%20Title">[request]</a>
  </div>
</div>
```

### A blog post

1. Duplicate `blog/2026-04-30-hello.html`, rename to `blog/YYYY-MM-DD-slug.html`.
2. Edit the date `<p class="meta">`, `<title>`, and `<h1>`.
3. Add a line to the `<ol class="post-list">` in `blog/index.html`.

## Customization

- Colors and fonts live in `:root` at the top of `assets/css/site.css`.
- The body font chain starts with Latin Modern Roman; if you ever want to self-host
  LMR, drop the woff2 files into `assets/fonts/` and add an `@font-face` rule
  pointing to them — the chain already names `Latin Modern Roman` first, so
  it'll be picked up automatically.
- Headshot: place a square JPEG at `assets/img/headshot.jpg` (≥400×400). It
  appears only on the home page; if missing, the page hides the image gracefully.
