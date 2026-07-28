# CO2 sorbents comparison tool

An interactive tool for comparing and exploring sorbents for emerging CO2 capture technologies. Data is loaded live from the project's published Google Sheet.

## Features

- Interactive 3D comparison with user-defined equations and titles for all three axes
- Formula-driven marker size and marker color
- Three distinct marker color palettes, including a reversed green–yellow–red scale
- Collapsible extra settings for plot ranges, marker scales, logarithmic axes, and color palettes
- Transparent SVG plot export
- Reusable user-defined numeric variables, with electricity price (`EP`) provided by default
- Formula-driven material and energy cost
- Always-visible table of source symbols, supported operators, and functions
- Linear or logarithmic scaling for each calculated axis; X is logarithmic by default
- Full-text search across every field in the source data
- Filters for sorbent category and capture method
- Sortable, paginated results table
- Complete record details, including fields that are not used by the 3D model
- Shared filters between the table and plot

Records that are missing values required by the model remain available in the table. The status beside the plot reports how many filtered records can currently be plotted.

## Run locally

The page must be served over HTTP because browsers restrict Google Sheet requests made from `file://` pages.

```bash
python3 -m http.server 8000 --bind 127.0.0.1
```

Then open <http://localhost:8000/>. Press `Ctrl+C` in the terminal to stop the server.
