# art.vaked.dev — entheai Visual Quantum Gallery

Static single-page gallery showcasing the 42 curated visual artifacts of the
entheai ecosystem (singularity checkpoints, brain constellations, fan-out
swarm orbits, ambient themes). Scaffolded from `entheai/public/gallery.html`.

## Layout

```
index.html          # the gallery (adapted from entheai gallery.html; canonical art.vaked.dev)
generative.html     # preserved previous art.vaked.dev canvas piece (flow/attractor/diffusion/mycelium/orbit)
assets/css/tokens.css
assets/js/          # landing helpers (landing.js, reveal.js, shader-field.js, docs.js, easter-eggs.js)
docs/images/        # the 12 gallery artifact images (mirror of entheai/docs/images)
favicon.* / icon-*.png / apple-touch-icon.png / site.webmanifest
_headers robots.txt 404.html
```

## Deploy (Cloudflare Pages)

The `art-vaked-dev` project already exists with `art.vaked.dev` bound:

```bash
wrangler pages deploy . --project-name art-vaked-dev --branch main
```

## Refresh from upstream

New artifacts get added to `entheai/docs/images` and `entheai/public/gallery.html`:

```bash
S=../entheai
cp "$S/public/gallery.html" index.html
cp "$S/docs/images/"*.png "$S/docs/images/"*.jpg docs/images/
cp "$S/public/assets/css/tokens.css" assets/css/
cp "$S/public/assets/js/"*.js assets/js/
```

Then re-apply the `art.vaked.dev` URL tweaks in `index.html` (og:url, canonical,
footer span) and redeploy.
