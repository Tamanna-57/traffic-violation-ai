# SignalWatch — Frontend

A single-file landing and demo page for the Traffic Violation Detection project.
It presents the five detection models, explains the pipeline, and includes an
in-browser preview of how detections are drawn and logged.

It is a flat, illustrated "traffic-poster" design: plain HTML, CSS and vanilla
JavaScript with no build step and no dependencies to install.

## View it locally

Open the file directly:

```bash
# macOS
open frontend/index.html
# Windows
start frontend/index.html
# Linux
xdg-open frontend/index.html
```

Or serve it (closer to how it behaves when hosted):

```bash
cd frontend
python -m http.server 8000
# then open http://localhost:8000
```

## Connect the live model backend

The in-page demo is **illustrative** — the detection boxes are a layout preview,
not real model output. The real models run in the Gradio Space (see the main
[`README.md`](../README.md)).

To wire the **Live demo** / **Open live Space** buttons to your Space, set
`SPACE_URL` near the bottom of `index.html`:

```js
var SPACE_URL = "https://huggingface.co/spaces/<user>/traffic-violation";
```

When it is set, the buttons open the Space in a new tab.

## Deploy

Because it is a static file, it can be hosted anywhere:

- **GitHub Pages** — enable Pages for the repo and serve from the `/frontend`
  folder (or move `index.html` to the repo root / a `docs/` folder).
- **Netlify / Vercel / Cloudflare Pages** — point the project at the `frontend`
  directory, no build command needed.

## What's inside

- **Hero** — a CCTV-watched street scene with AI detection callouts.
- **What it catches** — the five models as illustrated vignettes
  (helmet, driver monitoring, illegal parking, signal & sign, vehicle type),
  plus a "bring your own model" card.
- **Pipeline** — upload → detect → annotate → export.
- **Try it** — upload an image (or load the sample scene) to preview the
  detection overlay and the CSV detection log.

## Fonts & theme

Type is loaded from Google Fonts (Fredoka + IBM Plex) with system fallbacks, so
the page still renders fine offline. The design defaults to a light theme, with
an optional dark toggle in the top-right.
