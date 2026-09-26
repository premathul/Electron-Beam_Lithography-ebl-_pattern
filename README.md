# EBL Pattern Checker

A lightweight, local-first browser tool for checking **1D electron-beam lithography (EBL) hole-array geometry** before fabrication.

It accepts hole center positions, diameters, and optional region labels; calculates adjacent center-to-center spacing and edge-to-edge gaps; flags geometry that violates user-defined thresholds; visualizes the array; and exports the analyzed table as CSV.

## Why this exists

Tapered phononic/nanobeam patterns are easy to mis-enter by hand. A single center coordinate or diameter error can produce an unintended local gap or discontinuity. This tool provides a fast numerical sanity check before the pattern is transferred into the final CAD/EBL workflow.

## Features

- Paste CSV or tab-separated geometry directly into the browser.
- Automatic sorting by center position.
- Adjacent center-to-center spacing calculation.
- Edge-gap calculation:

  `gap_i = |x_i - x_(i-1)| - (d_i + d_(i-1))/2`

- Configurable minimum-gap threshold.
- Configurable maximum adjacent diameter-step threshold.
- Duplicate-center and overlap detection.
- Schematic array visualization with region labels.
- CSV export of calculated geometry and flags.
- No backend and no external data upload.

## Input format

```csv
position_nm,diameter_nm,region
-6700,250,Mirror
-6150,250,Mirror
-5600,250,Mirror
-2310,255,Taper
-1780,260,Taper
-1260,265,Taper
-750,270,Taper
-250,275,Central cavity
```

The header is optional. The first two columns must be numeric and are interpreted in nanometers. The third column is an optional region label.

## Run locally

No installation is required. Clone/download the repository and open `index.html` in a modern browser.

For a local HTTP server:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Repository structure

```text
ebl-pattern-checker/
├── index.html
├── styles.css
├── app.js
├── README.md
├── SCIENTIFIC_NOTES.md
├── SECURITY.md
├── CONTRIBUTING.md
├── LICENSE
└── .gitignore
```

## Scope and limitations

This is a **pre-fabrication geometry checker**, not an EBL process simulator. It does not perform proximity-effect correction (PEC), resist/exposure modeling, charging analysis, stitching-error prediction, dose optimization, or process-bias compensation. Final designs should still be validated in the CAD/EBL software used by the facility and against process-specific calibration data.

## Privacy

All calculations run in the browser. The current version has no server, analytics, account system, or telemetry.

## Deployment

Because this is a static application, it can be hosted on GitHub Pages or any static web host. If the design or fabrication geometry is confidential, keep the repository private and verify the visibility/access controls of the hosting method before deployment. Running it locally is the safest default for unpublished device geometry.

## License

MIT License. See `LICENSE`.
