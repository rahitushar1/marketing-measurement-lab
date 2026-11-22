# Verification and Evidence Register

Last reviewed: 2026-11-22

This register links claims to artifacts that can independently support them. A statement in chat is not verification.

| ID | Claim / deliverable | Evidence | Verification status |
|---|---|---|---|
| E-001 | Public repository, README and collaboration instructions exist | GitHub repository and main-branch file history | Verified repository foundation only |
| E-002 | Historical synthetic generator can run | Recovered V2 archive, fresh pilot generation; see E-005/E-007 | **Pilot and complete release regeneration verified; 21/21 files identical** |
| E-003 | Historical V2 QA suite runs and passes its defined rules | New release/pilot QA runs; see E-006/E-008 | **40/40 each verified; broader scientific validation outstanding** |
| E-004 | MMM, MTA and experiment pipelines | See E-012 for executed Meridian fast restoration; MTA and independent geo-experiment analysis not yet implemented | **MMM partially verified; remaining studies unverified** |

## Required evidence for technical completion
- Exact commit/reference, environment or lockfile, seed, and reproduction command.
- Test output, diagnostics, tables/figures with source code and relevant assumptions.
- Expected vs observed behavior, limitations, and failure conditions.
- Links to any issue/PR and run artifacts. Mark simulated experiments clearly.

## Process
When new evidence is obtained, update this table and `docs/STATUS.md`. Keep unsupported claims as pending or unverified.

## E-005 through E-009 — Recovery verification (2026-11-13)

| Evidence ID | Action | Verified result | Remaining boundary |
|---|---|---|---|
| E-005 | Recovered V2 archive and independently inspected `MANIFEST.json` | **45/45** file hashes and lengths match; archive SHA `e1326894d9a2987055f7bf7cbf1b4843cbb5c4aa46f909ff2650f483d622f70c` | Archive not yet committed publicly |
| E-006 | Ran original `qa.py release` | Exit 0, **40/40** passing, zero failed checks | Internal QA rules, not all scientific threats |
| E-007 | Generated pilot afresh and ran `qa.py rerun_pilot` | Exit 0, **40/40**, report exactly equals archived pilot QA JSON | Both now independently reproduced; external scientific validation remains |
| E-008 | Ran original `mechanism_tests` | **17/17** deterministic files equal, **4/4** adversarial corruptions rejected, null-effect tests true for three seeds | Does not prove external fidelity |
| E-009 | Independently summed release ledger, daily and weekly MMM tables | All three revenue aggregates **1,089,355,666 cents**; 164,196 orders, 48 geos, 24 pairs | Model estimation not performed |

Full commands, environment and detailed qualifications: [Synthetic V2 audit](SYNTHETIC_V2_AUDIT.md).

**Status correction to initial E-002/E-003:** The earlier table described the pre-recovery state. As of 2026-11-13, the generator has been recovered and fresh pilot execution verified; the released QA script has been rerun successfully. The complete multi-world power study and release regeneration have now been rerun; that historical statement is superseded for the exploratory MMM by E-012 below. No MTA fit is yet verified.


## E-010 and E-011 — Full reproducibility closeout
| ID | Execution | Observed evidence | Limits |
|---|---|---|---|
| E-010 | Re-ran entire `python validate.py rerun_pilot` multi-world power/coverage study | **PASS**; new `validation.json` exactly equals archived report: 979/1024 positive detections, 46/1024 A/A false positives, 988/1024 interval coverage; weaker-effect 259/384 detections | Conditional on synthetic world, randomized assignments within repeated worlds and no-interference assumptions |
| E-011 | Regenerated full 156-week release from seed 62189 and rebuilt QA/diagnostics/geo probe | **21/21 files byte-identical** to archived release; fresh QA **PASS 40/40** | Exact results in audited environment (Python 3.13.5 with pinned packages); code not yet imported to public repository |

## E-012 — Meridian exploratory MMM public fast reproduction (2026-11-22)

- **Source:** [PR #12](https://github.com/rahitushar1/marketing-measurement-lab/pull/12), [portable notebook](../notebooks/02_Meridian_MMM_Portable.ipynb), [manifest](../artifacts/mmm/manifest.json) and [case study](MMM_CASE_STUDY.md).
- **Observed:** A clean Google Colab session downloaded and checksum-verified public repository inputs with no private Google Drive or laptop uploads; assembled 48 × 120 = 5,760 geo-weeks; restored existing 2 × 1,000 posterior draws; all 12 code cells had saved outputs with zero recorded errors; all three Google Meridian HTML reports were generated and passed file-existence checks.
- **Reproducibility detail:** The post-test change pins public inputs to immutable GitHub commit `5da3b61c19aeef8a722cc49eb617064ade990507`, which contains the same verified assets. A new end-to-end Colab run after this URL change has **not** been recorded.
- **Limit:** Saved-posterior restoration is **not** independent full fitting; the maximum independently calculated rank-normalized R-hat ≈ 1.3781 indicates unresolved convergence issues. Model ROIs, national predictive fit, and optimization cannot be claimed as established causal effects. Full sampling and counterfactual-truth validation remain outstanding.
- **Acceptance:** M3 exploratory execution and fast-restoration QA verified; full M3 scientific gate remains open.
