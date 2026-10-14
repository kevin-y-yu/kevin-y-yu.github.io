# Editing conventions

Plain static HTML (`index.html`) + one CSS file (`style.css`); no build step. Colours are CSS variables at the top of `style.css`; dark mode is the `prefers-color-scheme: dark` block.

- **Add a publication:** copy an existing `<article class="item">` block in `index.html`, paste it at the right place (newest first), and edit the title, authors (wrap own name in `<strong>`), venue and links.
- **Thumbnails:** always use the paper's own Figure 1 (from the published version), not a teaser, project-page or code-repo image. Do not crop or pad it: the CSS shows every thumbnail in a square white box and letterboxes it. Save it in `images/` as a 360 px-wide image (e.g. `sips --resampleWidth 360 in.png --out images/name.png`; for a PDF figure, `pdftoppm -png -r 300 -singlefile fig.pdf images/name` then resample). With no figure, use `<div class="thumb-placeholder" aria-hidden="true">VENUE YEAR</div>` instead of the `<img>`.
- **External links:** give every external link `target="_blank" rel="noopener"`; leave `mailto:` links alone.
- **CV link:** see the `CV placeholder` comment in the contact line of `index.html`.
- **Last updated:** edit the date in the footer when content changes.
- `.nojekyll` must stay: it makes GitHub Pages serve files as-is.
