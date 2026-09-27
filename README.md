# An Open Data Approach for Comparing CO2 Sorbents

This repository contains a multidimensional visualization tool for comparing CO₂ sorbent performance using parameters relevant to CO₂ capture processes. The interactive tool connects sorbent properties and operating conditions in configurable 3D and 2D plots, making it possible to explore performance trade-offs across the open dataset developed in this work.

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

- Interactive 3D comparison of CO₂ sorbents by default, with an optional publication-oriented 2D view
- User-defined equations and titles for the plot axes; changing mode preserves the Z settings for the next 3D view
- Formula-driven marker size and color
- Linear and logarithmic scaling for axes, marker size, and marker color
- Configurable ranges, color palettes, and reusable numeric variables, including default values for electricity price (`ep`), sorbent mass (`mS`), and CO₂ mass (`mCO2`)
- Full-text search across the source data
- Filters for sorbent category and capture method
- A sortable, paginated table with complete record details
- Local, browser-only experimental records that appear in the table and active plot without changing the curated source dataset
- A structured workflow for preparing local records for curator review by email
- PNG, SVG, filtered CSV, and standalone Python exports

Records without all values required by the selected visualization remain accessible in the data table.

## Plot modes

The application opens in **3D** mode. Use the **Plot type** selector in the Plot mappings panel to switch to **2D**. The 2D plot uses the current X and Y equations and retains filtering, marker size, marker color, logarithmic scales, ranges, and hover information. Z controls are temporarily hidden and disabled in 2D mode; their values are retained when returning to 3D.

## Add and share experimental data

Use **Add record locally** for a browser-only record, or **Share data with curators** for the guided sharing workflow. Both buttons open the same structured scientific form. Numerical properties have separate value and uncertainty inputs, and each property explicitly distinguishes a supplied value (including zero), missing information, and a not-applicable value. Reaction kinetics can be entered either as solid-sorbent `t90` in minutes or liquid-sorbent `k_app` in s⁻¹.

After selecting **Add to local table and plot**, the record is mapped to the existing database schema and immediately included in the current browser session. Local records have a green table row, a **Local** badge, and diamond plot markers. They are not written to the published Google Sheet, Zenodo dataset, repository, or any other permanent database.

For curator review, first add the record locally and then select **Send data to curators** in the form. After closing the form to inspect the plot, the same email action is available as **Send to curators** on the local table row. The application opens the user's default email client using a `mailto:` link addressed to `anna.stepanova@gmail.com`, with the subject and all form values, units, missing/not-applicable states, and uncertainties already prepared. The application does not send email automatically. The researcher must review and send it, and the curators verify submitted data before permanent inclusion in the curated dataset.

## Export formats

Choose a format next to **Export**:

- **PNG** exports the currently displayed 2D or 3D Plotly figure at high resolution for presentations and publications.
- **SVG** exports the currently displayed figure as vector graphics.
- **CSV** contains records represented in the active filtered plot, including the relevant raw source fields, local records, record provenance, and computed X/Y/Z, marker-size, and marker-color values.
- **Python script** embeds the same exported CSV data directly as base64 text, records the active mappings, ranges, scales, color palette, and plot mode, and contains pandas/matplotlib code that reproduces the figure without downloading the online database. Run it in an environment with `pandas`, `numpy`, and `matplotlib` installed.

Image exports reflect the current plot. CSV and Python exports include only points represented after active table filters and plot-value validation; this behavior is also stated beside the export control.

## Run locally

The page loads data from a published Google Sheet and must be served over HTTP because browsers restrict requests made from `file://` pages.

```bash
python3 -m http.server 8000 --bind 127.0.0.1
```

Open <http://localhost:8000/> in a browser. Press `Ctrl+C` in the terminal to stop the server.

## Deployment

The application is deployed directly from `index.html` on GitHub Pages. All project-owned CSS and JavaScript are embedded in that file; the existing Plotly and Papa Parse libraries load from their CDNs. No build step or package installation is required.
