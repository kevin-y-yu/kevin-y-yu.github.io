# kevin-y-yu.github.io

Personal academic homepage of Kevin Yu (né Qu). Plain static HTML + one CSS file; no build step.

## Files

- `index.html` — the whole page (header/bio, publications, teaching, footer).
- `style.css` — all styling. Colours are CSS variables at the top; dark mode is the `prefers-color-scheme: dark` block.
- `images/` — photo and publication thumbnails.
- `.nojekyll` — tells GitHub Pages to serve files as-is (no Jekyll processing).

## Editing

- **Add a publication:** copy an existing `<article class="item">` block in `index.html`, paste it at the right place (newest first), and edit the title, authors (wrap your own name in `<strong>`), venue and links.
- **Thumbnails:** always use the paper's own Figure 1 (from the published version), not a teaser, project-page or code-repo image. Do not crop or pad it: the CSS shows every thumbnail in a square white box and letterboxes it. Put it in `images/` as a 360 px-wide image in `images/` (e.g. `sips --resampleWidth 360 in.png --out images/name.png`; for a PDF figure, `pdftoppm -png -r 300 -singlefile fig.pdf images/name` then resample). With no figure, use `<div class="thumb-placeholder" aria-hidden="true">VENUE YEAR</div>` instead of the `<img>`.
- **Add a CV link:** see the `CV placeholder` comment in the contact line of `index.html`.
- **Update the date:** edit the "Last updated" line in the footer.

## Preview locally

```bash
python3 -m http.server 8000 --bind 127.0.0.1
# open http://127.0.0.1:8000/
```

## Deploy (GitHub Pages)

1. On GitHub, create a **public** repository named exactly `kevin-y-yu.github.io` under the `kevin-y-yu` account (no README/licence, so the first push is clean).
2. In this folder:
   ```bash
   git add -A
   git commit -m "Initial homepage"
   git remote add origin git@github.com:kevin-y-yu/kevin-y-yu.github.io.git
   git push -u origin main
   ```
3. In the repo on GitHub: Settings → Pages → Build and deployment → Source: "Deploy from a branch", Branch: `main`, folder `/ (root)`. The site appears at https://kevin-y-yu.github.io/ within a few minutes.
4. Later updates: edit, commit, `git push`.

Design inspired by [Jon Barron's website](https://jonbarron.info/).
