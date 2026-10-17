# demo-web-quarto

**Window Garden**: a small multi-page guide written in [Quarto](https://quarto.org) (`.qmd` plain-text pages). Charts and sliders use Quarto's built-in Observable JS, so they run in the browser and the build needs no Python or R. Hosted on GitHub Pages at https://sthudir.github.io/demo-web-quarto/.

## Files
- `_quarto.yml`: site settings: navbar (with the Back to Hub link and GitHub icon), light/dark themes, output folder.
- `index.qmd`, `light.qmd`, `calendar.qmd`, `watch.qmd`: the pages. `light.qmd` has the interactive chart; `watch.qmd` has the video.
- `tokens.css`, `tokens.scss`: shared demo-web design tokens and theme tweaks.
- `site.json`, `thumbnail.svg`: what the hub reads; listed under `resources` in `_quarto.yml` so Quarto copies them to the output root.

## Run locally
Install [Quarto](https://quarto.org/docs/get-started/) (1.10.x), then:
```
quarto preview     # live-reloading dev server
quarto render      # production build into _site/
```

## Deploy
Push to `main`. `.github/workflows/deploy.yml` installs Quarto, runs `quarto render`, and publishes `_site/` to GitHub Pages. If the `HUB_DISPATCH_TOKEN` secret exists, it also tells the hub to refresh.

## Video
Edit the `<iframe>` in `watch.qmd` (YouTube privacy-enhanced `youtube-nocookie.com/embed/<id>`).

## Base path
Quarto writes relative links, so the site works under `/demo-web-quarto/` without extra settings. `site-url` in `_quarto.yml` is only used for metadata.

## Adding Python
For real Python cells, add `jupyter: python3` and a `requirements.txt`, and add `setup-python` + `pip install` steps to the workflow before `quarto render`.
