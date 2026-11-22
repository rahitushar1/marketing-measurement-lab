# M3 Meridian MMM — fast reproducibility

**Status (2026-11-22): successful clean Colab execution using public GitHub assets; exploratory M3 artifacts merged into main via PR #12.** All three HTML reports were generated, with 12/12 code cells producing outputs and zero recorded errors. The project owner reports a successful final Colab run after the input URL was pinned to the immutable commit; a separate downloaded notebook showing this post-pin execution has not been archived. Independent full Bayesian refitting has not been verified.

## Goal
Reproduce the **existing** Google Meridian synthetic-retailer MMM reports and inspect the model's Bayesian posterior and caveats, using only public repository files. No private Google Drive, laptop uploads, or personal Google authentication to access input files.

## Exact repository paths to publish

- `mmm_geo_weekly.csv` — already exists at repository root (the notebook checks Git blob SHA `7df07a92573810b2c61c43e563102153f55bb14c`).
- `data/mmm/geos.csv` — 48 geographical populations (SHA-256 `b0eba8a59d26995ad9ad7262d5bcbfe6560f607461720634619d42250b4990e9`).
- `artifacts/mmm/MMM_Meridian_Exploratory.nc` — saved prior, posterior and sampling diagnostics, 12,576,270 bytes (SHA-256 `c4419cc22c5f0e3a708cbdbdd684a239873793f7fd3c008f407af81d5e67bbd8`).
- `artifacts/mmm/manifest.json` — checksums and scope.
- `notebooks/02_Meridian_MMM_Portable.ipynb` — portable notebook with saved successful public-input execution outputs; pinned-reference revision reported runnable by the project owner; separately archived outputs for that version pending.
- `reports/mmm/` — three separately verified original HTML reports, clearly labeled original executions, not outputs from the yet-untested portable notebook.

These assets were merged into `main` via [PR #12](https://github.com/rahitushar1/marketing-measurement-lab/pull/12) on 2026-11-22 (merge commit `f31df3e74dbb3dc96099373175364224a6531331`). The notebook uses the immutable input commit `5da3b61c19aeef8a722cc49eb617064ade990507`.

## Reader instructions — after these files are published

1. From the repository open `notebooks/02_Meridian_MMM_Portable.ipynb`; choose **Open in Colab** or open the file through Colab's GitHub tab.
2. In Google Colab select **Runtime → Run all**. Step 1 installs `google-meridian==2.2.0`; Step 2 downloads the 3 files and checks their hashes; Steps 3–10 restore model draws and regenerate the three official HTML reports. **There is no default Bayesian refit**.
3. Locate the generated HTML reports at `/content/mmm_public_outputs/` in the Colab Files sidebar; check that Step 12 prints `PASS` three times.
4. Read the R-hat cell and model limitations. The exploratory budget recommendation is not decision-grade evidence.

**Important:** Input data URLs use `REPO_REF = "5da3b61c19aeef8a722cc49eb617064ade990507"`, an immutable existing Git commit containing all inputs. GitHub commit SHA plus SHA-256 / Git blob checksums protects against mutable branch contents. The project owner reports a completed Colab run after the pinned-ref change (2026-11-22). The repository's saved notebook execution outputs were captured before that one-line input-reference change.

## Full independent refit

The notebook includes an explicitly opt-in `RUN_FULL_REFIT = True` block. It is **not tested in this package**. It re-samples with the originally recorded 2-chain sampling configuration. This can be expensive and does not address the known convergence problems. Never present fast posterior restoration as proof of independent full fitting.

## Scientific caveats

- Synthetic outcomes and estimated paid-media contributions are different from real campaign incrementality.
- National test R² ~0.8803 is predictive fit, not causal identification.
- Highest rank-normalized R-hat ~1.3781 indicates posterior sampling concerns; ROI group max ~1.0218.
- Meridian health score 100/100 uses different automated criteria; compare with strict diagnostics.
- The fixed $396,900 budget optimizer projects ~$68,228 additional *modeled* incremental revenue under ±30% channel spending constraints; this is a scenario, not a demonstrated lift.
- The simulator's `truth_only` data are **not in these files**; MTA, geo-experiment and triangulation are separate workstreams.

## Remaining work for full M3 scientific acceptance

- **Public exploratory case study published:** PR #12 merged into `main`; no additional publication approval needed for that merge.
- A clean Colab run using public assets completed successfully; the owner reports the subsequent immutable-input-ref run also completed. Preserve the distinction from the earlier saved notebook output provenance.
- Maintain the execution evidence, checksums, outputs and limitations already linked in the repository; optionally archive a fresh executed notebook from the post-pin run. Keep [M3 Issue #6](https://github.com/rahitushar1/marketing-measurement-lab/issues/6) open until scientific acceptance criteria are met.
- Verify the full-refit branch later if independent sampling is desired.
