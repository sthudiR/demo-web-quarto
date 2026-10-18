# showcase/

One self-contained page that shows what Quarto can host. Everything for it lives in this folder, so it can be removed without touching the rest of the site.

| File | What it is |
|---|---|
| `index.qmd` | The page: three embeds with a sentence each |
| `notebook.ipynb` | A small Jupyter notebook; one figure is embedded in the page |
| `slides.qmd` | A reveal.js slide deck (renders to `slides.html`) |
| `embeds/p5-ripples.html` | p5.js sketch (a grid of dots and ripples) |
| `embeds/three-knot.html` | three.js scene (a torus knot you can spin) |
| `vendor/` | p5.js 1.11.3 and three.js r160, vendored (licences included) |
| `showcase.css` | Styles for the page |
| `_metadata.yml` | Turns off code execution, so the build needs no Python |

## Re-running the notebook
The notebook is saved with its results, so the site build never runs Python. To change it, install Jupyter, matplotlib and numpy, edit the notebook, run `jupyter nbconvert --to notebook --execute --inplace showcase/notebook.ipynb`, and commit it.

## Removing it
Delete `showcase/` and remove the "Showcase" entry from the navbar in `_quarto.yml`.
