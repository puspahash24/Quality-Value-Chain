# Quality Value Chain — Noamundi & Katamati · v1.21.0

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
- 1.9.1 — Pasting ROM quality in Plant summary (or editing it there) now also sets the ROM inputs on each plant's Predict page, marked “from Plant summary”.
- 1.21.0 — Plant summary (QVC code paste): Wet Plant and IOPP now train on the last 4 months of shifts (editable; 0 = use the plant settings), run the band-width finder on that window and predict with the best band widths; outlier filter fixed at 4σ. The window and chosen widths are shown under Models.
- 1.20.0 — Retractable side panel: the ▢ button at the top left hides or shows the left panel (period, focus, inputs, report library); the choice is remembered.
- 1.19.1 — Fix: OPRs from April–September 2026 were mistaken for the multi-year Wet Plant sheet (they carry a similar shift-wise tonnage sheet) and skipped with “no new months”. A file with OPR / C&S plant sheets is now always read as a monthly report.
- 1.19.0 — Light blue is the default theme, with 8 light themes (Blue, Navy, Sky, Teal, Green, Orange, Rose, Lavender) and 7 dark ones. ⚙ Settings: product specification limits (min / max for Fe, SiO2, Al2O3, P) for every plant product, plus Plant summary fines limit and t / trip; out-of-spec values turn red on flowsheets, the assay ledger, Plant summary and insights. Plant summary Visualise gets Summary / Trend / Daily / Shifts tabs; trends on every page pick one or many streams and switch Daily ↔ Shift-wise. Equipment flowsheets for the C&S plants (hopper, scalping screen, jaw and cone crushers, product screen). Full screen opens filling the screen width (Fit shows the whole sheet). Longer ROM feed arrows. “online” label removed.
- 1.18.0 — Linked folder: a file that cannot be opened (OneDrive “online-only” file not yet downloaded) no longer stops the whole folder check. Every readable report still loads; the unreadable ones are listed in the Report library and retried automatically at the next check. Permission problems and file problems are now reported separately.
- 1.17.0 — Wet / IOPP / NDCMP Predict card renamed “Predicted flowsheet” (was “Grade flow”); folder button reads “📁 Link folder” (also when the browser needs access again).
- 1.16.0 — Full-screen flowsheets in Visualise mode (Wet, IOPP, NDCMP, C&S plants and Plant summary) get a Period bar: Last day / 7 days / 30 days / Month / All and From–To dates, without leaving full screen.
- 1.15.0 — Link a OneDrive folder (Edge / Chrome on a computer): keep every OPR and Noa C&S report in one synced OneDrive folder (sub-folders included), link it once with “📁 Link OneDrive folder”, and the app loads new or changed reports each time it opens or comes back to the screen; Check now / Reload all / Unlink in the Report library. “Waste” wording replaced by “by-products”.
- 1.14.0 — Zoom in full screen: − / + / Fit buttons (also + − 0 keys and Ctrl + mouse wheel), drag to pan when zoomed, 125 % to 400 %. All quantities shown in kt (kilotonnes) — flowsheets, KPIs, product cards, tables, band analysis, backtest and Plant summary; typed inputs (ROM tonnes, t / trip) stay in tonnes.
- 1.13.0 — Plant summary gets Predict | Visualise: Visualise shows the actual ROM processed and products made by every plant over the chosen period (Last day / 7 / 30 days / Month / All / dates), as the same flowsheet plus plant-wise and combined tables; click a plant to open its Visualise page. Focus selector (Fe · SiO2 · Al2O3 · P · Tonnes) in every plant page rail, in each flowsheet header (Predict and Visualise) and on the Plant summary. Tonnes focus shows tonnes as the main value on the equipment flowsheets, mass-flow view and summary flowsheet; tables and charts keep the last chosen element.
- 1.12.0 — Outlier screening in every calculation (training, band analysis, backtest, band finder, Plant summary, Visualise averages) for all plants: physically impossible assays are always dropped (Fe 30–70, SiO2 ≤35, Al2O3 ≤25, P ≤0.6 %); shifts with an extreme ROM grade and product assays with an extreme product−ROM delta (beyond 4 robust σ = median ± 4×1.48·MAD) are ignored. Model settings: Outlier filter Off / Strict 3σ / Normal 4σ (default) / Loose 6σ, with the count of ignored shifts and assays.
- 1.11.0 — Full-screen button on every flowsheet (Wet, IOPP, NDCMP grade flow / equipment and mass flow, Plant summary); Esc or the button exits. Plant summary flowsheet: flowing-dot animation on all lines, and CLO / fines / slime-reject lines into the site and all-plant totals now run in separate lanes so fines and losses no longer merge. Default t / trip = 100 for both sites (old 35 defaults are moved to 100).
- 1.10.0 — Plant summary shows a flowsheet (default): ROM feed → plant (equipment icon) → predicted products → Noamundi / Katamati site totals → all fines, all CLO, slime & reject. Line width = tonnes, value colour = focus element, ✓/✕ against the fines Al₂O₃ limit; click a plant to open its Predict page. Flowsheet | Cards toggle keeps the old card view.
- 1.9.0 — Wet Fines = calculated (CF bypass + Jig Conc + HC Conc), W-6 sample shown as a check; import of the multi-year Wet Plant shift sheet (HIST); best band widths as Wet Plant defaults (Fe 1.0 · SiO2 0.1 · Al2O3 0.5 · P 0.01, from a 30-month backtest), editable per plant; band-width finder for any training window; training window as last N calendar days or a date range; report data stored in IndexedDB (room for many years).
- 1.8.0 — Plant summary page (ROM Monitoring App code / Excel paste); Material flow marked "under construction"; version shown in the header.
- 1.7.x — Equipment flowsheet view (Wet, IOPP, NDCMP) with toggle; IOPP mass flow fix; larger text.
- 1.6.0 — IOPP hydrocyclone circuit streams.
- 1.5.0 — NDCMP + 4 C&S plants, Predict/Visualise, single upload, Material flow draft.
