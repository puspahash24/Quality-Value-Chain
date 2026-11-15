# Quality Value Chain — Noamundi (Wet Plant; IOPP & NDCMP to follow)

Installable PWA: trains Wet ROM → product quality deltas (Fe, SiO2, Al2O3, P) from the monthly
Ore Processing Report and predicts every Wet Plant stream from shift ROM Al2O3.
Runs fully in the browser — OPR data never leaves the computer. Works offline after first open.

## Publish (GitHub Pages)
1. Create a repo (e.g. `wet-plant-grade-flow`) and upload ALL files keeping the folder structure:
   `index.html`, `manifest.webmanifest`, `sw.js` and the 6 icon PNGs (all in the repo root)
2. Settings → Pages → Source: *Deploy from a branch* → `main` / root → Save.
3. Open `https://<your-user>.github.io/wet-plant-grade-flow/`

## Install (no admin rights needed)
- **Chrome / Edge (laptop):** click **Install app** in the top bar, or the install icon at the right end of the address bar.
  The app gets its own window, Start-menu/desktop icon, and can open .xlsx OPR files via *Open with → Quality Value Chain*.
- **Android (Chrome):** ⋮ → *Add to Home screen / Install app*.
- **iPhone (Safari):** Share → *Add to Home Screen*.

## Updating
Upload the new `index.html` to the repo and bump `VERSION` in `sw.js` (e.g. `gf-v1.1.0`).
Installed copies pick up the update automatically on the next launch.

## Deep link from ROM Monitoring App
`…/?al=4.35&jig=1&t=7200` pre-fills shift ROM Al2O3, jig state and tonnes.
