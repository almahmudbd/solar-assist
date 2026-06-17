# Solar Power Assistant

Three free, browser-only solar planning tools in one static site. Bilingual (বাংলা / English) with a shared header, footer, and theme.

## Tools

- **Solar Power Calculator** (`calculator.html`) — sizes panels, inverter & battery from your home appliance load.
- **Sunlight Simulator 2D** (`simulator-2d.html`) — panel efficiency by direction & tilt, with a daily performance curve (Chart.js).
- **Sunlight Simulator 3D** (`simulator-3d.html`) — interactive Three.js scene: rotate the view, set azimuth/tilt, and watch the sun track across the sky.
- **Learn Solar** (`resources.html`) — curated articles, video links, and inline SVG diagrams (panel tilt, off-grid flow, series/parallel wiring). Edit the `articles`/`videos` arrays in the page to swap in your own resources.

`index.html` is the landing/hub page that links to all four. Everything runs client-side — no build step, no backend, no data collected.

## Structure

```
index.html            Landing / tool hub
calculator.html       Solar power calculator
simulator-2d.html     2D sunlight simulator
simulator-3d.html     3D sunlight simulator (Three.js)
resources.html        Learn Solar — articles, videos, diagrams
assets/
  site.css            Shared header / footer / language-switch styles
  favicon.svg         Site icon
```

Third-party libraries (Tailwind, Chart.js, Three.js, Lucide) are loaded from CDNs, so the site works straight from the filesystem or any static host. The language choice (`bn`/`en`) is shared across pages via `localStorage`.

## Deploy to Vercel

This is a pure static site (no build needed).

1. Push this folder to its own GitHub repository.
2. In Vercel: **New Project** → import the repo.
3. Framework Preset: **Other**. Leave Build Command empty and Output Directory empty (root is served as-is).
4. Deploy. `index.html` is served at `/`.

### Or via CLI

```bash
npm i -g vercel
vercel        # preview
vercel --prod # production
```
