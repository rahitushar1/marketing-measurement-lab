# Marketing Measurement Lab — Project Status

Last verified: 2026-11-13
**Current milestone:** M0 — Foundation and existing-work recovery. **Status: IN PROGRESS.**

## Verified completed / evidence
- Public repository, canonical project charter, roadmap, collaboration instructions, GitHub Issues.
- Decision and evidence logs; experiment/model register, methods/claims ledger, publication plan, technical acceptance criteria, workflow/board instructions, issue/PR templates.
- Recovered 2026-11-05 **V2 synthetic retailer archive** from personal file Library; verified **45/45 manifest hashes**.
- Ran source archive `qa.py` against saved release: **PASS 40/40**, exit code 0.
- Generated a new pilot with saved seed `62027`; QA rerun **PASS 40/40**, exactly matching archived QA report.
- Ran mechanism tests: zero-delivery sales survive, three zero-effect world comparisons match, 17/17 mini replay files hash-identical, 4/4 adversarial corruptions detected.
- Independently checked ledger/daily/weekly revenue equality (1,089,355,666 cents), 164,196 orders, 48 markets and 24 randomized pairs.
- Created and seeded actionable issues [#2–#10](https://github.com/rahitushar1/marketing-measurement-lab/issues), one per next technical or visibility deliverable.

## Remaining / boundaries
- **M0 native GitHub Projects board:** NOT CREATED. Current GitHub connection supports GitHub files/issues but does not expose Projects creation. [Issue #3](https://github.com/rahitushar1/marketing-measurement-lab/issues/3) describes the required owner UI step and target five statuses.
- **M0 V2 audit:** Partly verified, **not complete**. Archive's full multi-world power study was not rerun; full 156-week release not regenerated. Source has not been reviewed/imported into GitHub. [Issue #2](https://github.com/rahitushar1/marketing-measurement-lab/issues/2).
- **Scientific limitations:** tests establish internal synthetic invariants, not real-market realism, model parameter recovery, lack of interference, or production deployment.
- **ChatGPT UI Project instructions:** collaboration file read; UI application was not independently verified.
- **MMM/MTA/experiment model results:** no model pipeline has been fitted and verified in this repository.

## Milestone table
| Milestone | State | Next gate |
|---|---|---|
| M0 Foundation + recovery | **In progress** | Finish V2 source audit; owner creates Projects board |
| M1 Unified synthetic DGP | **Candidate code recovered, not yet imported** | Commit source, tests, environment and reproducibility |
| M2 QA automation | **Prior V2 QA verified, CI not implemented** | Review independent tests and establish CI |
| M3 MMM | Planned | Reproducible model + diagnostics |
| M4 MTA | Planned | Reproducible attribution/bias study |
| M5 Incrementality | Planned | Simulated geo inference and uncertainty |
| M6 Triangulation | Planned | Aligned estimands and decision case |
| M7 Publication + practitioner feedback | Plan complete, execution pending | First grounded publication after public source release |

## Priority queue
1. **P0 Technical:** complete [V2 recovery audit #2](https://github.com/rahitushar1/marketing-measurement-lab/issues/2); preserve useful V2 code, rerun remaining power tests, and prepare source import.
2. **P1 Project management:** owner creates [native Projects board #3](https://github.com/rahitushar1/marketing-measurement-lab/issues/3); link verified board URL and import issues.
3. **P0/P1 Technical:** use V2 as candidate for [M1 integration #4](https://github.com/rahitushar1/marketing-measurement-lab/issues/4), not a blind rewrite.
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
