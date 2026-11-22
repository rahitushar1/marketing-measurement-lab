# Marketing Measurement Lab — Project Status

Last verified: 2026-11-22
**Portfolio technical focus:** M3 exploratory MMM publicly reproducible by saved-posterior restoration; M3 scientific acceptance remains **IN PROGRESS**.
**Foundation track:** M0 continues in progress; native Projects board and V2 source integration are not complete.

## 2026-11-22 — M3 exploratory MMM published to main

- **Executed:** A regression benchmark and Google Meridian 2.2.0 exploratory MMM were run in Colab on 48 simulated markets × 120 pre-experiment weeks (5,760 geo-weeks), using Search, Social and Display. Two MCMC chains × 1,000 posterior draws were saved in NetCDF.
- **Verified fast reproduction:** A clean Colab run fetched checksummed **public GitHub inputs**, restored the saved posterior without resampling, and regenerated the three Google Meridian HTML reports. All 12 code cells contained outputs and no execution errors were recorded. Evidence: [merged PR #12](https://github.com/rahitushar1/marketing-measurement-lab/pull/12), [portable notebook](../notebooks/02_Meridian_MMM_Portable.ipynb), and [M3 reproduction guide](M3_FAST_REPRODUCIBILITY.md).
- **After-run change:** The notebook's input reference was pinned from a mutable branch name to immutable GitHub commit `5da3b61c19aeef8a722cc49eb617064ade990507`; hashes and the same input asset blobs can be checked independently, but **the owner reports a subsequent successful Colab run with the pinned URL; no separate post-pin executed notebook has been archived**.
- **Findings (exploratory):** National test R² ≈ 0.8803, test wMAPE ≈ 6.14%; Social mean modeled ROI ≈ 6.43×. The $396,900 historical fixed-budget scenario projects +$68,228 (+3.74%) modeled incremental revenue under Meridian's original default ±30% channel constraints.
- **Scientific blockers:** Strict rank-normalized R-hat reaches ≈ 1.3781; full independent Bayesian refit, aligned synthetic counterfactual-truth comparison, and causal calibration are not complete. Prediction quality or official health score does **not** establish true channel incrementality. No simulated model output should be described as a live campaign result.
- **Milestone state:** M3 **IN PROGRESS** (execution and fast restoration verified; all formal exit gates not met). M4 MTA, M5 independent geo-incrementality analysis, M6 triangulation remain separate planned efforts; M7 visibility may proceed on correctly labeled exploratory evidence.

## Earlier foundation and synthetic-V2 audit (verified 2026-11-13)


## Verified completed / evidence
- Public repository, canonical project charter, roadmap, collaboration instructions, GitHub Issues.
- Decision and evidence logs; experiment/model register, methods/claims ledger, publication plan, technical acceptance criteria, workflow/board instructions, issue/PR templates.
- Recovered 2026-11-05 **V2 synthetic retailer archive** from personal file Library; verified **45/45 manifest hashes**.
- Ran source archive `qa.py` against saved release: **PASS 40/40**, exit code 0.
- Generated a new pilot with saved seed `62027`; QA rerun **PASS 40/40**, exactly matching archived QA report.
- Reran full experiment-power validation: **PASS**; validation JSON exactly matches archived report (95.6% detection, 4.5% A/A false positives, 96.5% coverage; weak-effects detection 67.4%).
- Regenerated complete 156-week release with seed `62189`; QA **PASS 40/40** and **21/21 files byte-identical** after diagnostics and geo-probe generation.
- Ran mechanism tests: zero-delivery sales survive, three zero-effect world comparisons match, 17/17 mini replay files hash-identical, 4/4 adversarial corruptions detected.
- Independently checked ledger/daily/weekly revenue equality (1,089,355,666 cents), 164,196 orders, 48 markets and 24 randomized pairs.
- Created and seeded actionable issues [#2–#10](https://github.com/rahitushar1/marketing-measurement-lab/issues), one per next technical or visibility deliverable.

## Remaining / boundaries
- **M0 native GitHub Projects board:** NOT CREATED. Current GitHub connection supports GitHub files/issues but does not expose Projects creation. [Issue #3](https://github.com/rahitushar1/marketing-measurement-lab/issues/3) describes the required owner UI step and target five statuses.
- **M0 historical V2 audit:** **COMPLETED** for archive recovery, saved and regenerated pilot QA, full multi-world validation, full-release byte reproduction. **Source integration into GitHub remains a separate M1 task** under [Issue #4](https://github.com/rahitushar1/marketing-measurement-lab/issues/4).
- **Scientific limitations:** tests establish internal synthetic invariants, not real-market realism, model parameter recovery, lack of interference, or production deployment.
- **ChatGPT UI Project instructions:** collaboration file read; UI application was not independently verified.
- **MMM:** Exploratory fit and public-input fast restoration verified 2026-11-22 (see current update above). **MTA and independent geo-experiment estimates:** not yet verified.

## Milestone table
| Milestone | State | Next gate |
|---|---|---|
| M0 Foundation + recovery | **In progress** | Historical audit complete; owner creates Projects board |
| M1 Unified synthetic DGP | **Verified source candidate, not yet imported** | Commit source, tests, environment and reproducibility |
| M2 QA automation | **Prior V2 QA verified, CI not implemented** | Review independent tests and establish CI |
| M3 MMM | **In progress — public fast restoration verified** | Resolve convergence, independent full refit, aligned synthetic truth evaluation |
| M4 MTA | Planned | Reproducible attribution/bias study |
| M5 Incrementality | Planned | Simulated geo inference and uncertainty |
| M6 Triangulation | Planned | Aligned estimands and decision case |
| M7 Publication + practitioner feedback | **In progress** | Merge reviewed M3 case study; publish evidence-based outreach; gather feedback |

## Priority queue
0. **M3 published exploratory case study:** [PR #12](https://github.com/rahitushar1/marketing-measurement-lab/pull/12) merged to `main` on 2026-11-22 (merge commit `f31df3e74dbb3dc96099373175364224a6531331`). Continue scientific follow-up in [Issue #6](https://github.com/rahitushar1/marketing-measurement-lab/issues/6): posterior mixing, independent refit, synthetic ground truth comparison.
1. **P0 Technical:** prepare reviewed [M1 V2 source import #4](https://github.com/rahitushar1/marketing-measurement-lab/issues/4); historical reproduction verified, do not rebuild blindly.
2. **P1 Project management:** owner creates [native Projects board #3](https://github.com/rahitushar1/marketing-measurement-lab/issues/3); link verified board URL and import issues.
3. **P1 Technical:** establish [M2 independent QA/CI #5](https://github.com/rahitushar1/marketing-measurement-lab/issues/5) after source import.
4. **P1 Visibility:** deliver initial technically accurate publication through [M7 #10](https://github.com/rahitushar1/marketing-measurement-lab/issues/10) after a reproducible source release.

## Durable documents
- [Charter](PROJECT_CHARTER.md), [roadmap](ROADMAP.md), [acceptance criteria](ACCEPTANCE_CRITERIA.md)
- [V2 recovery audit](SYNTHETIC_V2_AUDIT.md), [evidence](EVIDENCE.md), [experiment register](EXPERIMENT_REGISTER.md)
- [Decision log](DECISIONS.md), [methods & claims](METHODS_AND_CLAIMS.md)
- [Publication plan](RELEASE_PLAN.md), [workflow / board instructions](WORKFLOW.md)

## Operating rules
- Distinguish **completed / planned / blocked** with exact evidence.
- Record tests and scientific caveats; simulations are not deployed real-world experiments.
- Never publish private contacts, secrets or proprietary employer data.
- Update status and linked issue at meaningful handoffs.
