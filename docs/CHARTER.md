# Marketing Measurement Lab — Project Charter

Effective: 2026-11-13
Status: Working charter — revise through recorded decisions.

## Purpose
Build and publicly explain reproducible marketing measurement case studies that demonstrate the ability to **implement**, **interpret**, **critique**, and **act on** MMM, MTA, and incrementality measurement, including what to do when evidence disagrees.

## Intended audiences
1. Marketing measurement practitioners who care about causal validity, statistical rigor and limitations.
2. Recruiters and hiring managers evaluating applied marketing analytics skills.
3. Learners seeking clear, executable explanations of common industry methods.

## Core deliverables
- One versioned causal synthetic-data generator with documented simulation truth and realistic limitations.
- Automated QA tests across data integrity, statistical plausibility, causal and experimental consistency.
- Independently executable MMM, MTA and incrementality studies using appropriate open-source methods and baselines.
- Triangulation framework: comparable estimands, disagreements, uncertainty, investigation and business decisions.
- Public educational narrative, reproducible GitHub portfolio, and practitioner feedback/publication workstream.

## Working agreement
- **Project HQ (ChatGPT conversation):** cross-workstream priorities, decisions, risks, blockers, and session handoff. Avoid deep implementation here.
- **Implementation conversations/issues:** one scoped technical problem with its tests and documentation.
- **Learning conversations:** derivations, concepts, code reading and method comparisons.
- **Visibility conversations:** writing, publication and practitioner engagement.
- **GitHub:** durable source of truth; issues track deliverables, code and tests demonstrate completion, `docs/STATUS.md` tracks current state, `docs/DECISIONS.md` tracks rationale.

## Success criteria
- A new person can clone, configure and rerun every showcased workflow.
- Each measurement method's assumptions, outputs and limitations can be explained mathematically and in business language.
- Results are tested against known simulation ground truth where applicable, with uncertainty and caveats.
- Triangulation changes an explicitly defined business decision or identifies what additional evidence to collect.
- The public repository and writing are useful to practitioners and support substantive professional engagement.

## Scope guardrails
- Synthetic experiments are never represented as actual deployed campaigns.
- Use public or permitted source material; never publish employer-proprietary inputs or private outreach/contact records.
- No model or metric is declared causally valid solely because it fits simulated observational data.
- Career/visibility outcomes depend on external response and cannot be guaranteed.

## Near-term objective
Finish M0: recover and audit prior work, scope the DGP/QA pilot, and establish an issue-driven delivery workflow. Then begin verified M1/M2 implementation.

See `docs/ROADMAP.md`, `docs/DECISIONS.md`, `docs/EVIDENCE.md`, and `docs/STATUS.md`.
