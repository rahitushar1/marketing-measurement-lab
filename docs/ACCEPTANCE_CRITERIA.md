# Acceptance Criteria — technical milestone gates

Updated: 2026-11-13. Completion means versioned outputs, commands and evidence—not a chat assertion.

## M1 — Coherent synthetic DGP
- [ ] Version-controlled generator with dependency lock/pinned environment, config and deterministic seed.
- [ ] One documented causal source produces ledger, media events, MMM panels, MTA observation and experiment assignment.
- [ ] Record full table keys, units, time windows, missingness, currency and reconciliation conventions.
- [ ] Separate latent/researcher truth from analyst tables and prohibit leakage.
- [ ] Fresh pilot regeneration and at least one full-release reproduction method demonstrated.
- [ ] Baseline and intervention contrasts defined with coherent spend denominators.
- [ ] Document scientific limits, particularly no geo interference, realism assumptions and potentially unidentifiable parameters.

## M2 — Automated QA
- [ ] Positive QA tests for schema/keys, ledger cents, media billing, path chronology, assignments, and cross-grain reconciliation.
- [ ] Negative tests intentionally corrupt ledger, media, truth metrics and leak a hidden column; each fails the appropriate gate.
- [ ] Zero-delivery, zero-effect, paired replay and separate analyst/truth checks documented.
- [ ] CI reruns bounded automated checks on every relevant pull request; larger stochastic validation can run manually.
- [ ] Machine-readable report, thresholds, failure messages and known unsupported threats committed.

## M3 — MMM
- [ ] Explicit outcome, media variables, controls, units, horizon, priors/regularization and response formulation.
- [ ] Runnable baseline and chosen industry-relevant approach; environment and seed recorded.
- [ ] Diagnostics: residuals, fit, temporal/geo holdout, posterior or estimator uncertainty and response realism.
- [ ] Compare **defined causal counterfactuals** with truth on an aligned policy/window/population, with calibration/identification limitations.
- [ ] Business recommendation and explanation of disagreement/uncertainty.

## M4 — MTA
- [ ] Construct paths with documented attribution lookback, identity loss and consent/visibility.
- [ ] Reproduce transparent heuristic baselines and an appropriate comparative statistical approach.
- [ ] Detect and explain selection bias, credited vs causal effects and differences in observation.
- [ ] Compare methods on predeclared target and uncertainty or sensitivity criteria; retain nonconverting journeys.
- [ ] Reproducible results and interpretation.

## M5 — Incrementality
- [ ] Predeclare estimand, unit of randomization, treatment comparator, eligible population, pulse and follow-up.
- [ ] Check randomization, pair balance, pre-period, delivery integrity and cross-market interference assumptions.
- [ ] Estimate effect, uncertainty and a relevant randomization/power sensitivity analysis.
- [ ] Compare to full simulated counterfactual truth without pretending it was a deployed campaign.
- [ ] Explain operational feasibility and caveats.

## M6 — Triangulation
- [ ] Align metrics, populations, geographic/time windows, counterfactuals and spend denominators.
- [ ] Distinguish assignment of credit from causal lift and account for common-mode errors.
- [ ] Include stable/unstable and agreeing/disagreeing scenarios, diagnostic actions and a decision threshold.
- [ ] Demonstrate a defensible business recommendation or justified need for more evidence, with sensitivity and caveats.

## M7 — Public quality
- [ ] New reviewer can clone, install, reproduce and distinguish observed/simulated/truth-only data.
- [ ] Published posts link exact code/release and disclose assumptions and synthetic status.
- [ ] At least one substantive technical feedback cycle recorded without private contact details.
- [ ] Portfolio summary translates technical findings into decision context.

See [V2 audit](SYNTHETIC_V2_AUDIT.md) and [evidence register](EVIDENCE.md).
