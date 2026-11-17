# Quality Value Chain — Noamundi & Katamati · v1.8.0

Installable web app (PWA). Trains ROM → product quality (Fe, SiO2, Al2O3, P) from the monthly
Ore Processing Report (Wet Plant, IOPP, NDCMP) and the Noa C&S Plant Report (ISS, Metso (NIM),
Sandvik, Metso (KTM)), and predicts every product from ROM quality.
Runs fully in the browser — report data never leaves the computer. Works offline after first open.

## Pages
- **Wet Plant · IOPP · NDCMP · C&S** — Predict (model) or Visualise (actuals for a date range);
  Equipment flowsheet or Mass flow diagram.
- **Plant summary** (new in 1.8) — paste the *Plant quality* message from the ROM Quality Monitoring
  App (Shift end report → "Share plant quality code"), or a table copied from Excel
  (Plant, Trips or ROM t, Fe, SiO2, Al2O3, P). Every plant's products are predicted at once, plus
  Noamundi / Katamati / all fines, CLO and losses as tonnage-weighted blends. Copy to Excel or CSV.
- **Material flow** — draft only, under construction; not used in any prediction.

## Publish / update (GitHub Pages)
Upload ALL files in this folder to the repo root (replace the old ones):
`index.html`, `sw.js`, `manifest.webmanifest`, `README.md` and the icon files.
Installed copies pick up the update on the next launch (the version in `sw.js` changes with each release).

## Version history
- 1.8.0 — Plant summary page (ROM Monitoring App code / Excel paste); Material flow marked "under construction"; version shown in the header.
- 1.7.x — Equipment flowsheet view (Wet, IOPP, NDCMP) with toggle; IOPP mass flow fix; larger text.
- 1.6.0 — IOPP hydrocyclone circuit streams.
- 1.5.0 — NDCMP + 4 C&S plants, Predict/Visualise, single upload, Material flow draft.
