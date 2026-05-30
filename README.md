# Joli — Lingerie Atelier · Landing Concept

A studio-grade landing page concept for a handmade-lingerie brand. Built from scratch as a
**self-contained single file** — no framework, no build step, no dependencies. Open `index.html`
and it runs.

🔗 **Live demo:** https://YOUR-USERNAME.github.io/joli-concept/
🎨 **Other directions:** [`concepts.html`](concepts.html) — three alternate art directions (Editorial / Boudoir / Quiet Luxury)

> Concept / spec work. Created as a design-and-build exercise for a boutique lingerie label.
> Brand name and imagery are used for portfolio demonstration only; contact details in the page are placeholders.

---

## Highlights

- **Live style switcher** — a floating *“✦ Стиль”* panel lets the viewer change the font pairing
  (Cormorant · Playfair · Prata · Unbounded) and the colour palette (Espresso / Noir / Bordeaux / Slate)
  on the fly. Choices persist in `localStorage`. Built so the client could pick their direction *during the pitch*.
- **3D coverflow collection** — a scroll-driven, GPU-transformed product gallery (`perspective` +
  `rotateY`/`translateZ`/`scale`), with edge mask-fade and a scroll-position “active” card that flips to its reverse angle.
- **Cinematic scroll** — hero depth parallax, kinetic split-text, clip-path reveals, a word-fill manifesto,
  film grain, and an intro loader. All on native scroll via a single `requestAnimationFrame` loop.
- **Real mobile experience** — the desktop coverflow degrades into a native scroll-snap **swipe carousel**
  with a centre-detecting active card; dedicated tablet (`≤1024`) and phone (`≤600`) breakpoints.
- **Brand watermark grid** — the logo tiled as a subtle bone-tinted texture across dark sections via
  multiple-background CSS.
- **Cyrillic-first typography** — every font chosen for proper Ukrainian/Cyrillic coverage.
- **Social-ready** — OpenGraph / Twitter card with a custom 1200×630 share image for clean Telegram unfurls.

## Tech

Plain **HTML + CSS + vanilla JS**. No bundler, no libraries. The whole landing is one `index.html`.

| Area | Approach |
|------|----------|
| Animation | IntersectionObserver reveals + a single rAF scroll loop (parallax, zoom, word-fill) |
| 3D gallery | CSS `transform-style: preserve-3d`, `perspective`, per-card transform from scroll offset |
| Mobile | CSS scroll-snap carousel + JS active-card detection |
| Theming | CSS custom properties (`--fd`/`--fs`/`--fm` + palette vars) toggled live, saved to `localStorage` |
| Type | Google Fonts (Cormorant, Playfair, Prata, Unbounded, Manrope, Inter, Golos Text, JetBrains Mono) |

## Run locally

```bash
# just open it
open index.html          # macOS
start index.html         # Windows

# or serve (so relative assets + fonts behave exactly like production)
python -m http.server 8000
# → http://localhost:8000
```

## Structure

```
index.html      → the flagship landing (this is the portfolio piece)
concepts.html   → showcase of the flagship + 3 alternate art directions
v1-editorial.html / v2-boudoir.html / v3-minimal.html   → the alternate concepts
img/editorial/  → editorial / campaign imagery
img/products/   → product catalogue imagery
img/og-card.jpg → social share card (1200×630)
```

## Deploy (GitHub Pages)

Settings → Pages → Source: **Deploy from a branch** → `main` / root. Live at
`https://YOUR-USERNAME.github.io/joli-concept/` within a minute.

---

*Designed & built by [YOUR-USERNAME](https://github.com/YOUR-USERNAME).*
