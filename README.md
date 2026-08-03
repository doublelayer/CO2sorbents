# An Open Data Approach for Comparing CO2 Sorbents

This repository contains a multidimensional visualization tool for comparing CO₂ sorbent performance using parameters relevant to CO₂ capture processes. The interactive tool connects sorbent properties and operating conditions in a configurable three-dimensional plot, making it possible to explore performance trade-offs across the open dataset developed in this work.

## Authors

Margarita Burunova, Iuliia Vetik, Anna Stepanova, Timmo-Hendrik Pukk, Karolina Kudelina-Zhang, Nadezda Kongi, and Vladislav Ivanistsev.

## Publication and data

- **Preprint:** [An Open Data Approach for Comparing CO2 Sorbents](https://chemrxiv.org/doi/full/10.26434/chemrxiv-2026-g3zqr/v2)
- **Machine-readable dataset:** [Zenodo record](https://zenodo.org/records/20052533)
- **Dataset DOI:** [10.5281/zenodo.20052533](https://www.doi.org/10.5281/zenodo.20052533)

## Visualization tool

The visualization tool is available online at:

<https://doublelayer.github.io/CO2sorbents/>

Its source code is available at:

<https://github.com/doublelayer/CO2sorbents>

The tool provides:

- Interactive three-dimensional comparison of CO₂ sorbents
- User-defined equations and titles for all three axes
- Formula-driven marker size and color
- Linear and logarithmic scaling for axes, marker size, and marker color
- Configurable ranges, color palettes, and reusable numeric variables, including default values for electricity price (`ep`), sorbent mass (`mS`), and CO₂ mass (`mCO2`)
- Full-text search across the source data
- Filters for sorbent category and capture method
- A sortable, paginated table with complete record details
- Transparent SVG plot export

Records without all values required by the selected visualization remain accessible in the data table.

## Run locally

The page loads data from a published Google Sheet and must be served over HTTP because browsers restrict requests made from `file://` pages.

```bash
python3 -m http.server 8000 --bind 127.0.0.1
```

Open <http://localhost:8000/> in a browser. Press `Ctrl+C` in the terminal to stop the server.
