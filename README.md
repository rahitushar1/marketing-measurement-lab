# Marketing Measurement Lab

**MMM · Multi-touch Attribution · Incrementality · Triangulation**

An open, reproducible research and portfolio project exploring how multiple marketing measurement methods can be implemented, validated, compared and used for business decisions.

**Current status (November 22, 2026):** Exploratory Google Meridian MMM executed and independently reproduced using public inputs and a saved posterior. Full model refitting, convergence remediation, and causal-truth validation remain pending.

## M3 — Google Meridian marketing mix modeling (exploratory; fast reproduction verified)

This synthetic DTC retailer case study models **48 markets × 120 pre-experiment weeks** (5,760 geo-weeks), Search, Social and Display, in **Google Meridian 2.2.0**. The notebook restores a saved Bayesian posterior of **2 chains × 1,000 draws**, then regenerates Google's model results, model-health and fixed-budget optimization reports from publicly downloadable, checksum-verified assets. A fresh Colab run using the public review branch completed successfully on November 22, 2026. An independent **full Bayesian refit** is not yet verified.

- [Read the MMM case study](docs/MMM_CASE_STUDY.md)
- [Open the portable notebook](notebooks/02_Meridian_MMM_Portable.ipynb)
- [Reproduction instructions](docs/M3_FAST_REPRODUCIBILITY.md)
- [Results report](reports/mmm/MMM_Meridian_Model_Results.html) · [Health report](reports/mmm/MMM_Meridian_Model_Health.html) · [Optimization report](reports/mmm/MMM_Meridian_Budget_Optimization.html)

**Headline:** Meridian estimates Social mean modeled ROI at **6.43×** and suggests reallocating a historical **$396,900** fixed budget toward Social. Under default ±30% channel constraints, the modeled scenario estimates **+$68,228 (+3.74%) incremental revenue**. These are **simulated observational model estimates**, not experimentally verified lift. Independent strict convergence diagnostics show maximum rank-normalized R-hat ≈ **1.378**, so parameter inference and optimization remain provisional. MTA, geo incrementality, truth comparison and triangulation are separate upcoming milestones.

## What the lab will deliver
- A unified, documented **synthetic causal data-generating process**, including observable marketing data and separately stored simulation ground truth.
- Reproducible **MMM**, **MTA**, and **incrementality experiment simulations** with code, diagnostics, uncertainty, caveats and decision implications.
- A practical **triangulation framework** for investigating agreement or disagreement among measurement methods.
- Educational notes, method comparisons and practitioner-facing findings as evidence accumulates.

## Project navigation
- [Project charter](docs/PROJECT_CHARTER.md) — purpose, scope, audiences and collaboration model
- [Roadmap](docs/ROADMAP.md) — milestones, exit criteria and workstreams
- [Current status](docs/STATUS.md) — verified progress, priorities and blockers
- [Decisions](docs/DECISIONS.md) — methodology and scope choices
- [Evidence register](docs/EVIDENCE.md) — independently verified claims vs unverified work
- [Synthetic V2 recovery audit](docs/SYNTHETIC_V2_AUDIT.md) — verified tests and remaining research gaps
- [Acceptance criteria](docs/ACCEPTANCE_CRITERIA.md) — technical milestone completion gates
- [Experiment/model register](docs/EXPERIMENT_REGISTER.md) — executed vs planned research
- [Methods and public claims](docs/METHODS_AND_CLAIMS.md) — evidence guardrails
- [Publication and career plan](docs/RELEASE_PLAN.md) — stage-gated releases
- [Issue workflow / GitHub Projects setup](docs/WORKFLOW.md) — board not yet created
- [Collaboration instructions](chatgpt/PROJECT_INSTRUCTIONS.md) — teaching-first and evidence-first workflow
- [Foundation issue](https://github.com/rahitushar1/marketing-measurement-lab/issues/1) — active M0 checklist

## Rigor and disclosure
Synthetic experiments are simulations, not real deployed campaigns. Simulation ground truth is not automatically observable in real-world measurement. Public artifacts will not include private professional contacts, credentials or proprietary employer data.
