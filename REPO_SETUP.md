# GitHub Repository Setup

Suggested repository name: `ebl-pattern-checker`

Suggested description:

> Local-first EBL hole-array geometry checker for nanofabrication pattern validation, taper inspection, spacing/gap calculations, visualization, and CSV export.

Suggested topics:

`electron-beam-lithography`, `nanofabrication`, `ebl`, `nanophotonics`, `phononic-crystal`, `geometry-validation`, `research-tools`

## First push

```bash
git init
git add .
git commit -m "Initial EBL Pattern Checker"
git branch -M main
git remote add origin <YOUR-REPOSITORY-URL>
git push -u origin main
```

## Recommended repository settings

For unpublished lab geometry, start with a **private repository**. Enable branch protection later if collaborators will contribute. Do not enable a public deployment until you have confirmed that no confidential device geometry or lab-specific process information is embedded in the repository.
