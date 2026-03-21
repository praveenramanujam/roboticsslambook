# Estimation, Mapping & Localization

A hands-on interactive textbook covering the mathematics and algorithms behind robot localization, mapping, and SLAM. Built for students who want to understand estimation from the ground up.

## Structure

| Part | Topic | Chapters |
|------|-------|----------|
| I | The Estimation Mindset | 1 |
| II | Linear Algebra and Geometry | 2 to4 |
| III | Uncertainty and Identifiability | 5 to8 |
| IV | Estimation Frameworks | 9 to10 |
| V | Modeling the Real World | 11 to14 |
| VI | Core Estimation Algorithms | 15 to18 |
| VII toVIII | SLAM and Optimization | 19 to26 |
| IX toXI | System Architecture and Visual SLAM | 27 to38 |
| XII toXIV | Sensor Fusion, LiDAR, Large-Scale Mapping | 39 to52 |

## How it works

- Each chapter combines written explanations with live, editable Python code
- Notebooks run entirely in the browser via JupyterLite (Pyodide) with no installation required
- Built with [Jupyter Book](https://jupyterbook.org/)

## Local development

```bash
pip install "jupyter-book<1.0" jupyterlite-sphinx jupyterlite-pyodide-kernel matplotlib numpy scipy
jupyter-book build book/
# Open book/_build/html/index.html
```

## Deploy

Push to `main` and GitHub Actions automatically builds and deploys to GitHub Pages.
