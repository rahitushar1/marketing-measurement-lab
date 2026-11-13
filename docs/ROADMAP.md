# Marketing Measurement Lab — Milestone Roadmap

Last reviewed: 2026-11-13
Status convention: **Verified complete** requires committed deliverables and reproducible evidence; **In progress**, **Planned**, and **Blocked** are separate.

## North star
Demonstrate hands-on implementation and defensible evaluation of marketing mix modeling (MMM), multi-touch attribution (MTA), and incrementality experiments, then triangulate their estimates into business decisions. Explain the underlying statistical and causal reasoning. Build a credible public portfolio and practitioner network along the way.

## Workstreams
- **Technical:** synthetic data, reproducibility, MMM, MTA, experiments, triangulation.
- **Educational:** theory notes, method comparisons, annotated code, explain-what/why/how/learning handoffs.
- **Visibility and career:** public GitHub, LinkedIn learning posts, technical articles, practitioner feedback, relevant relationships and opportunities. No private contact data in the public repository.

## Milestones and completion gates

### M0 — Foundation and recovery audit — IN PROGRESS
- Repository structure, project charter and roadmap, decision/evidence logs, issue-driven work.
- Inventory previous synthetic data generator/QA work; locate usable artifacts.
- Re-run any recovered scripts or tests and document results, assumptions, and known gaps.
- **Exit gate:** clear reproducible baseline, scoped tasks and acceptance criteria. Do not mark historical technical work done from chat descriptions alone.

### M1 — Synthetic causal data generator — PLANNED
- Document a causal data-generating process (DGP): media exposure, seasonality, promotions, demand, pricing/other confounders, conversions and revenue.
- Produce consistent aggregate MMM inputs, event/path-level MTA inputs, and experiment-assignment data from one versioned latent system.
- Seeded reproducibility and known simulation truth (e.g., counterfactual incremental effects); distinguish observable data from oracle-only fields.
- **Exit gate:** executable generator, schema/data dictionary, documented parameters, smoke test and example output.

### M2 — Automated data and causal QA — PLANNED
- Validate schema, integrity, reproducibility, distributions, path/aggregate reconciliations, leakage, interventions/randomization and causal effects against DGP ground truth.
- Test failure cases and report what tests can and cannot establish.
- **Exit gate:** versioned test suite, passing baseline, negative tests, QA report.

### M3 — MMM case study — PLANNED
- Fit baseline and industry-relevant MMM approaches (tool choice to be decided after data requirements).
- Teach adstock, saturation, identification, priors/regularization, uncertainty and calibration.
- **Exit gate:** reproducible fits, diagnostics, holdout checks, counterfactual estimates, decision memo and limitations.

### M4 — MTA case study — PLANNED
- Implement transparent baselines and suitable statistical/attribution approach(es) on path-level simulated observations.
- Distinguish predictive allocation / Shapley-style credit from causal incrementality.
- **Exit gate:** tested pipeline, evaluation against defensible benchmarks, sensitivity/selection-bias analysis, decision memo.

### M5 — Incrementality experimentation — PLANNED
- Simulate a randomized holdout or geo-experiment with documented treatment assignment, estimand, power and analysis.
- No claim of a deployed real-world experiment.
- **Exit gate:** assignment checks, treatment-effect estimate with uncertainty, diagnostics, interpretation and reproducible notebook/scripts.

### M6 — Triangulation and action framework — PLANNED
- Compare MMM, MTA and experimental estimates on explicitly aligned questions, populations, outcome definitions and time frames.
- Explain disagreements (estimand differences, confounding, observation granularity, uncertainty, measurement bias); propose when to trust, investigate, calibrate or run another experiment.
- **Exit gate:** comparison matrix, sensitivity scenarios, reproducible business decision case, limitations.

### M7 — Portfolio and practitioner validation — PLANNED (runs in parallel)
- Clean README, documented case studies, diagrams, clear replication instructions, periodic LinkedIn/technical writing, practitioner review and career-targeted evidence.
- **Exit gate:** publicly understandable project walkthrough, reproducible results and feedback log. Never publish proprietary or private source materials.

## Immediate priorities
1. P0: complete the recovered V2 audit (fresh 40/40 QA and pilot reproduction already verified; multi-world power and full-release replay pending).
2. P0: use V2 as candidate DGP; review source/assumptions and [acceptance criteria](ACCEPTANCE_CRITERIA.md) before integration.
3. P1: owner creates native GitHub Projects board; GitHub issues and PR template now prepared.
4. P1: choose first public educational update only after a verified substantive result.

## Scope and rigor guards
- Known truth exists **only because we construct the simulation**, not because real marketing data has accessible causal truth.
- Channel paths and aggregate outcomes must be generated consistently, not stitched from unrelated fictitious datasets.
- Holdout simulations demonstrate experimental methodology, not execution of a live campaign.
- Each implementation requires runnable instructions, fixed random seeds where appropriate, diagnostics, uncertainty, and caveats.
- No one model is assumed to be the universal ground truth in an observational setting.
