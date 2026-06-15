# DOMINIO — Flipbook

Interactive HTML5 flipbook of the **DOMINIO – FLC x Berdez x Sineva Review** magazine.
Drag, swipe, or use the arrows to turn pages — works on desktop, tablet, and mobile.

## ▶ Live

Once GitHub Pages is enabled, the flipbook is published at:

`https://developersineva.github.io/<repo-name>/`

## Run locally

```bash
# from this folder
python -m http.server 8777
# then open http://localhost:8777
```

(Serving over HTTP is required — opening `index.html` directly via `file://`
blocks the page images in most browsers.)

## What's inside

| Path | Description |
|------|-------------|
| `index.html` | The flipbook UI and logic |
| `pages/` | 36 rendered magazine pages (JPEG) |
| `lib/page-flip.browser.js` | [StPageFlip](https://github.com/Nodlik/StPageFlip) — the page-turn engine (bundled, no CDN needed) |
| `sound/page-flip.mp3` | Page-turn sound effect — "Turned Page" from [BigSoundBank](https://bigsoundbank.com/turned-page-s0164.html), **CC0 / public domain** (free for commercial use, no attribution required) |

## How it works

1. Each PDF page was rendered to an image with **PyMuPDF**.
2. **StPageFlip** maps swipe/drag distance to a 3D page-rotation angle in real
   time using CSS 3D transforms, with shadows and gradients for a paper-fold look.
3. Pages lazy-load for fast performance on mobile.
