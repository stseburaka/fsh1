# FSH1 static website

This project contains a plain HTML/CSS reproduction of the FSH1 site for later GitHub Pages hosting.

## Pages

- `public/index.html` — Belarusian version
- `public/en/index.html` — English version
- `public/assets/styles.css` — shared responsive layout
- `public/assets/fonts.css` — local font-face declarations
- `docs/assets-manifest.json` — production image slots and source proportions

The team photo and 16 gallery photos are sourced from `inbox/photos/`, converted to JPEG web assets, and referenced by both pages. The source-to-slot mapping is recorded in [`docs/assets-manifest.json`](docs/assets-manifest.json).

## Local preview

Serve the `public/` directory with any simple static file server and open the root page. No build step or package installation is required.

The included GitHub Actions workflow publishes only `public/` to GitHub Pages after a push to `main`. Custom domains and DNS changes remain separate manual steps.
