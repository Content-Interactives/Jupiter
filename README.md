# Jupiter Interactive

Client-only WebGL lesson for the Jupiter system: single `index.html` with an inline ES module (no bundler). Curriculum, NGSS alignment, and product links are in [`Standards.md`](Standards.md).

**Production:** [https://content-interactives.github.io/Jupiter](https://content-interactives.github.io/Jupiter)

---

## Architecture

| Layer | Implementation |
|--------|----------------|
| Rendering | `THREE.WebGLRenderer`, scene/camera/lights |
| Modules | Native `importmap` → Three.js **r162** on unpkg (`three`, `three/addons/`) |
| UI | DOM overlays (menus, Flexi bubble), Font Awesome 6.5 (CDN) |

---

## Repository layout

| Path | Role |
|------|------|
| `index.html` | Document, styles, `<script type="module">`, import map |
| `package.json` | Optional `http-server` on port **8085** for local static hosting |
| `Flexi_Telescope.svg` | Static mascot asset |

---

## Local development

Serve over HTTP (ES modules and textures expect a real origin):

```bash
npm install
npm run dev
```

Opens `http-server` on port **8085**. Do not rely on `file://`.

---

## Deployment

Static hosting (e.g. GitHub Pages): publish files so `index.html` is the default document.

---

## Maintenance note

`<title>` in `index.html` currently reads **“Venus Orbit with Three.js”** while the repo is Jupiter-focused—update if that is unintentional.
