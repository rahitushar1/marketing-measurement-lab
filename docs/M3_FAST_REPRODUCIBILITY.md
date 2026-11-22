# M3 Meridian MMM — fast reproducibility

**Status: pre-publication candidate.** The notebook has been statically validated and the saved posterior has been inspected, but the portable GitHub-download pathway **has not yet been run from a clean Colab session**. Do not claim it works until that reader-style test passes.

## Goal
Reproduce the **existing** Google Meridian synthetic-retailer MMM reports and inspect the model's Bayesian posterior and caveats, using only public repository files. No private Google Drive, laptop uploads, or personal Google authentication to access input files.

## Exact repository paths to publish

- `mmm_geo_weekly.csv` — already exists at repository root (the notebook checks Git blob SHA `7df07a92573810b2c61c43e563102153f55bb14c`).
- `data/mmm/geos.csv` — 48 geographical populations (SHA-256 `b0eba8a59d26995ad9ad7262d5bcbfe6560f607461720634619d42250b4990e9`).
- `artifacts/mmm/MMM_Meridian_Exploratory.nc` — saved prior, posterior and sampling diagnostics, 12,576,270 bytes (SHA-256 `c4419cc22c5f0e3a708cbdbdd684a239873793f7fd3c008f407af81d5e67bbd8`).
- `artifacts/mmm/manifest.json` — checksums and scope.
- `notebooks/02_Meridian_MMM_Portable.ipynb` — portable notebook with fast restoration (new, **not yet executed**).
- `reports/mmm/` — three separately verified original HTML reports, clearly labeled original executions, not outputs from the yet-untested portable notebook.

These files are prepared under the supplied candidate folder. They **have not been pushed** to GitHub.

## Reader instructions — after these files are published

1. From the repository open `notebooks/02_Meridian_MMM_Portable.ipynb`; choose **Open in Colab** or open the file through Colab's GitHub tab.
2. In Google Colab select **Runtime → Run all**. Step 1 installs `google-meridian==2.2.0`; Step 2 downloads the 3 files and checks their hashes; Steps 3–10 restore model draws and regenerate the three official HTML reports. **There is no default Bayesian refit**.
3. Locate the generated HTML reports at `/content/mmm_public_outputs/` in the Colab Files sidebar; check that Step 12 prints `PASS` three times.
4. Read the R-hat cell and model limitations. The exploratory budget recommendation is not decision-grade evidence.

**Important:** The `main` URLs will not work until the assets are actually published there. For an immutable release, replace `REPO_REF='main'` with the commit SHA after a final approved commit, rerun to verify, and update these instructions. SHA-256 and Git blob checksums already guard against changed content.

## Full independent refit

The notebook includes an explicitly opt-in `RUN_FULL_REFIT = True` block. It is **not tested in this package**. It re-samples with the originally recorded 2-chain sampling configuration. This can be expensive and does not address the known convergence problems. Never present fast posterior restoration as proof of independent full fitting.

## Scientific caveats

- Synthetic outcomes and estimated paid-media contributions are different from real campaign incrementality.
- National test R² ~0.8803 is predictive fit, not causal identification.
- Highest rank-normalized R-hat ~1.3781 indicates posterior sampling concerns; ROI group max ~1.0218.
- Meridian health score 100/100 uses different automated criteria; compare with strict diagnostics.
- The fixed $396,900 budget optimizer projects ~$68,228 additional *modeled* incremental revenue under ±30% channel spending constraints; this is a scenario, not a demonstrated lift.
- The simulator's `truth_only` data are **not in these files**; MTA, geo-experiment and triangulation are separate workstreams.

## What is still required before we mark M3 published/reproducible?

- User reviews and approves file changes and public posterior release.
- Publish files to a review branch (not main) / open a pull request. While testing that branch, change `REPO_REF = "main"` in Step 2 to the review branch name; run a clean Colab session with no Drive mount or manual files. After merge, change the ref to `main` (or ideally to the immutable final commit SHA) and repeat the quick test.
- Record execution evidence, data checks, hashes, expected numerical outputs and limitations; update README, `docs/STATUS.md`, `docs/EVIDENCE.md`, `docs/EXPERIMENT_REGISTER.md`, and issue #6, without claiming closed M3 acceptance criteria.
- Verify the full-refit branch later if independent sampling is desired.
