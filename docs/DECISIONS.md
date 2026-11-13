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
