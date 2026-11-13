# Methods, Estimands and Public Claims Ledger

Updated: 2026-11-13. Do not conflate a pass in generator QA with reliable causal identification by a statistical model.

## Estimand registry
| Method | Target | Interpretation / caveat | Status |
|---|---|---|---|
| Synthetic DGP replay | Incremental gross revenue and billed spend under a defined intervention | Known only in the synthetic world; fixed-policy causal contrast | Counterfactual artifacts found; read-side QA passed |
| MMM | Aggregate incremental revenue under a proposed budget or media policy | Requires model fit, controls, diagnostics, out-of-sample and counterfactual comparison | No fitted model |
| MTA | Conversion / revenue **credit** assigned to observed touches | Credit rules do not make an effect causal; identity loss and exposure selection matter | No fitted model |
| Geo experiment | Social-on vs paused-social effect over pulse + follow-up, paired geography design | Within-world randomization and no-interference assumptions; simulated not live | Design QA and full multi-world power/coverage simulation reproduced; separate study write-up pending |
| Triangulation | Diagnose agreement/disagreement across compatible populations and estimands | Alignment and shared bias must be investigated, not blindly averaged | Not implemented |

## Public-claim register
| Claim | Evidence | Caveat | Publishable? |
|---|---|---|---|
| A V2 synthetic dataset and source package exist | Recovered original archive with 45/45 matching manifest hashes | Source not yet imported into public repository | Yes, with provenance/disclosure |
| V2 release passed its own 40 QA checks in a fresh run | `python qa.py release` exit 0, 40/40 passing | Only against authored internal checks; not independent scientific validation | Yes, precisely worded |
| V2 pilot can be regenerated deterministically | Fresh seeded generation and exact QA report match; mini 17/17 replay hash matches | All 21/21 release files additionally reproduced byte-for-byte | Yes, narrowly |
| Paid-social design has 95.6% power | Fresh rerun reproduced 979/1024, with exact JSON match | **Conditional simulated power** for selected effect sizes, assumptions, randomization and no interference; not universal campaign power | **Yes, with explicit simulation caveat** |
| MMM/MTA/triangulation results are accurate | No model implementation or evaluation yet | Not tested | **No** |

## Guardrails
- A 40/40 QA result checks defined invariants; it does not verify external market realism or identify causal effects from observational data.
- Keep `truth_only` sealed until the model specification and evaluation protocol are frozen.
- Disclose fictional retailer, simulated geo test, gross revenue vs margin, modeled identity loss and no market interference.
- Every future public figure must state the outcome, unit, source commit, date, uncertainty and limitations.
