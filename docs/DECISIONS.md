# Decisions and Open Questions

Last reviewed: 2026-11-13

A **decision** is a scope or methodological commitment; an **open question** remains unresolved. Add date, rationale, alternatives, and consequences when resolving material technical choices.

## Decisions

### D-001 — Demonstrate all three measurement methods, not only triangulation
- **Date:** 2026-11-13 (documented from agreed project mission)
- **Decision:** Deliver standalone reproducible MMM, MTA, and incrementality case studies and then triangulate them.
- **Why:** Practical implementation plus conceptual defense is required for a credible portfolio.
- **Consequence:** Each method gets its own verification gate before the combined comparison.

### D-002 — Start with a unified synthetic causal system
- **Date:** 2026-11-13 (documented from agreed project direction)
- **Decision:** Build and validate synthetic data before applying modeling methods.
- **Why:** Allows known simulation truth, controlled bias tests, and compatible aggregate, path, and experiment views.
- **Caveat:** Synthetic realism is limited; model performance on synthetic data is not proof of production performance.

### D-003 — Versioned evidence and teaching-first collaboration
- **Date:** 2026-11-13
- **Decision:** GitHub files/issues/tests hold the durable record. At each meaningful action explain what, why, how, what was learned, what changed, and what is next.
- **Why:** Reproducibility, auditability, and transferable learning.

### D-004 — Visibility is parallel to technical work
- **Date:** 2026-11-13
- **Decision:** Plan GitHub, LinkedIn, writing and practitioner engagement throughout development; publish only verifiable claims and avoid private information.
- **Why:** Professional credibility and opportunities are primary outcomes.

## Open decisions — not yet made
- Q-001: Scope/granularity of synthetic system (users, channels, geo, days/weeks, horizons, confounders).
- Q-002: Selection of initial MMM package(s) / baselines (e.g. Meridian, Robyn, PyMC) after requirements/installation checks.
- Q-003: Selection of MTA baselines and comparison estimand(s).
- Q-004: Exact experimental design (user/geo holdout, randomization and interference controls).
- Q-005: Publication cadence and public datasets/figures once a verified pilot exists.
- Q-006: GitHub Projects board configuration and workflow automation.

## Decision template
- ID/date:
- Problem and options:
- Choice:
- Reason, assumptions, tradeoffs:
- Evidence:
- Impact on roadmap and next review:

### D-005 — Reuse audited V2 as the starting candidate; do not rebuild blindly
- **Date:** 2026-11-13
- **Decision:** Preserve the recovered V2 generator and validation code as the *candidate* M1 foundation rather than replacing it without a documented deficiency.
- **Evidence:** Exact archive/hash verified, fresh pilot generated and passed all 40 bundled QA checks, 17/17 deterministic mini replay matches and 4/4 adversarial checks.
- **Limitations:** Full power-study rerun and full-release regeneration remain pending; code has not yet been publicly imported. A synthetic QA pass is not model identification.
- **Alternatives considered:** Restart entire simulation, or trust historical descriptions alone. Both would forfeit existing verified work or evidence rigor.

### D-006 — Native Projects creation requires an owner interface step
- **Date:** 2026-11-13
- **Decision:** Seed issues with defined acceptance gates, document the desired five-column GitHub Projects board, and leave board creation explicitly open until the owner performs and verifies the UI setup.
- **Why:** The connected GitHub actions support issue and file writes, not user Projects creation. A documentation-only board is not a native Projects board.
- **Evidence:** [Workflow](WORKFLOW.md) and [board setup issue](https://github.com/rahitushar1/marketing-measurement-lab/issues/3).
