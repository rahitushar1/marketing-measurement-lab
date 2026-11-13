# Synthetic-data V2 recovery and audit

Audit date: 2026-11-13
Status: **Historical V2 generator and data reproduction verified.** Archived multi-world experimental validation and every release file reproduced exactly; external scientific realism and downstream model validation remain outstanding.

## Source artifact
- Original archive recovered from the owner's personal ChatGPT Library: `triangulation_synthetic_v2 (1)(3).zip` (77,924,719 bytes).
- Archive SHA-256: `e1326894d9a2987055f7bf7cbf1b4843cbb5c4aa46f909ff2650f483d622f70c`.
- V2 package release date: 2026-11-05. Internal `MANIFEST.json` and `QA_REPORT.md` supplied.
- Exact generator SHA-256: `402e9131ac463754bfa1e73d9b7faa36db58750f0c056c9473415977523ba1eb`.
- QA script SHA-256: `3ab7a12dd0a112bfb671632a733a9f8fc4c622a1b5a3cfb0abc439b4f93e7195`.
- Validation script SHA-256: `f1c04983aaaed879083f9551ca66d8bef58d882adb8ba170450cd545f08f4b08`.
- Archive is not yet committed publicly. Hashes identify the audited version; reproducible code still needs a controlled import/PR and license/privacy review.

## What was inspected
- 46 ZIP entries, ~90.9 MB uncompressed, including `generate.py`, `qa.py`, `validate.py`, `diagnostics.py`, research/design documentation, parameter registry and configurations.
- Saved pilot/release reports, analyst tables, truth-only counterfactuals, experiment assignments, evaluation scenarios, manifest.
- Declared V2 design: fictional US DTC replenishment retailer; search/social/display; organic demand, competition, promotions, price, latent shopper intent, incomplete identity observation.
- **Fixed-policy contrast design:** channel removal, +20% pressure, all-paid-off, and 14-week social holdout with two-week follow-up. Simulated truth stored separately.

## Independently executed on 2026-11-13
| Check | Observed result | Evidence / command |
|---|---|---|
| Manifest SHA-256 | **45/45 files match** recorded byte lengths and hashes | Independent Python hashlib over extracted archive |
| Environment | Installed numpy 2.3.5, pandas 2.2.3, scipy 1.17.0, matplotlib 3.10.8 match pinned versions; Python is **3.13.5**, not archive's 3.12.14 | Version inspection |
| Saved release structural/causal read-side QA | **PASS 40/40, exit code 0**, zero failures | `python qa.py release --report release_rerun_qa.json` |
| Fresh pilot generation | **PASS, exit code 0**, generated all historical scenario replays | `python generate.py --config config/pilot.json --output rerun_pilot` |
| Fresh pilot read-side QA | **PASS 40/40, exit code 0**; entire QA JSON equals bundled `pilot/qa_report.json`, including row counts | `python qa.py rerun_pilot --report rerun_pilot_qa.json` |
| Mechanism / adversarial QA | All mechanism assertions true: zero-delivery baseline, three zero-effect seeds with identical outcomes, alternative assignment seed retains prehistory, **17/17 byte-identical mini replay files**, **4/4 corrupted fixtures rejected** | `mechanism_tests(load_config(Path('config/pilot.json')))` from `validate.py` |
| Independent revenue cross-check | `transactions` = `mmm_geo_daily` = `mmm_geo_weekly` = **1,089,355,666 cents** over **164,196 transactions** | Independent pandas sum |
| Release geo design | **48 geos**, **24 paired normal** and **24 paired holdout**; **156 full weeks** | Independent CSV inspection |\n| Full multi-world power / coverage validation | **PASS, exit 0**, full newly produced `validation.json` exactly equals archived pilot report | `python validate.py rerun_pilot`; 979/1024 positive detections; 46/1024 A/A false positives; 988/1024 interval coverage; 259/384 weaker-effect detections |\n| Fresh 156-week release regeneration | **PASS, exit 0**, all **21/21 release files byte-identical**, including diagnostic images and truth-only files | `python generate.py --config config/release.json --output rerun_release`; `python qa.py rerun_release`; `python diagnostics.py rerun_release`; regenerate `geo_probe.json` with `validate.observed_geo_probe` |\n| Fresh full release QA | **PASS 40/40**, `qa_report.json` exactly equals original | `python qa.py rerun_release --report rerun_release/qa_report.json` |

## Full validation reproduced this session
- Fresh `python validate.py rerun_pilot` passed; the regenerated validation JSON was **exactly identical** to archived `pilot/validation.json`.
- The archived power estimate was reproduced: **979/1024 = 95.6%** positive detections, **46/1024 = 4.5%** A/A false positives, **988/1024 = 96.5%** approximate t-interval coverage. Lower-efficacy sensitivity: **259/384 = 67.4%** detections.
- Fresh 156-week `generate.py` release regenerated successfully, then QA/diagnostics/geo probe were rebuilt. **All 21/21 regenerated release files match the archived release byte-for-byte.**
- This is reproducibility **under the currently installed pinned packages on Python 3.13.5**; original bundle specified Python 3.12.14. Cross-platform replication and real-advertiser fidelity are separate questions.

## What this does and does not establish
**Established:** The recovered archive has integrity-verified files; original QA and mechanism gates rerun; seeded pilot validation exactly reproduces; all **21/21** full-release outputs reproduce byte-for-byte; independent revenue cross-checks reconcile.

**Not established:** real retailer realism/calibration; identification of every channel effect by a practical MMM or MTA model; cross-geo interference robustness; production deployment or actual holdout experiment; performance in non-synthetic datasets.

**Important:** V2 is a valuable existing baseline. **Do not restart the generator from scratch** without a documented deficiency. M1 should review and integrate this verified candidate with source code and tests, then assess necessary model-specific extensions.

## Next audit actions
1. Import the audited V2 source files, docs and small sample/config into GitHub using a reviewable branch/PR. Preserve the archive SHA, package version and simulation-truth separation; do not commit large generated CSVs or personal library links.
2. Preserve the 2026-11-13 rerun logs, hashes, and report bundle; ensure new source-import CI covers a smaller deterministic subset.
3. Review design assumptions and possible endogeneity/identifiability concerns with meaningful model recovery tests. Separate data integrity from scientific validation.
4. Draft release/licensing/privacy/data-size policy before a public source import.

## Reproduction contract (once source is committed)
- Use the exact V2 configuration and pinned dependencies; original bundle specifies Python 3.12.14.
- Set seeds: pilot `62027`/`62028`; release `62189`/`62190`.
- Keep `truth_only` out of analyst-facing outputs and benchmark/model development until scoring.
- Scripts: `python qa.py release`; `python generate.py --config config/pilot.json --output rerun_pilot`; `python qa.py rerun_pilot`; `python validate.py rerun_pilot`; `python generate.py --config config/release.json --output rerun_release`; `python qa.py rerun_release`; `python diagnostics.py rerun_release`.
