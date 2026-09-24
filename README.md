# Canvas & Co

A small, static homepage for Canvas & Co, a two-person art-print studio in Portland, Oregon. We design original artwork in-house, print it on premium canvas, and ship it ready to hang.

**Live site:** https://majicwilson.github.io/canvas-co/

## What's on the page

- A hero and a "Why Canvas & Co" section with our most-loved prints
- Our three collections: Landscape, Botanical, and Abstract
- The full catalog, with every print and its price
- About the studio and contact details

## Running it locally

There's no build step. Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8000
```

Then visit http://localhost:8000.

## Project layout

- `index.html`: the whole page
- `styles.css`: all styling (warm cream palette, terracotta accent, system sans-serif)
- `images/`: the artwork for each print
- `products.csv`: name, category, price, and image for every print
- `company.md`: a short description of the studio and its voice

## Updating the site

Product cards are written by hand in `index.html`, so when a print changes, update `products.csv` and the matching cards. Pushing to `main` republishes the site through GitHub Pages in about a minute.
