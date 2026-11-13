# Experiment and Model Register

Updated 2026-11-13. Distinguish **not started**, **executed**, **QA passed**, and **scientifically validated**. These labels are not interchangeable.

| ID | Purpose | Version | Estimand/check | Execution evidence | Current status |
|---|---|---|---|---|---|
| SIM-001 | Synthetic V2 release QA | V2 / SHA e1326894… | Structural, financial, paths, experiment and truth consistency | 40/40 read-side checks rerun and pass | **Executed; internal QA passed** |
| SIM-002 | Seeded V2 pilot reproducibility | V2 pilot 62027 | Byte reproducibility, structural validity, null effect, adversarial negative tests | Fresh pilot generated; 40/40 QA exact report match; 17/17 small replay hashes; 4/4 corruptions caught | **Executed; targeted reproducibility passed** |
| SIM-003 | Multi-world paired geo experimental power | V2 archived validation | Positive-lift detection, A/A false positives, interval coverage | Bundled report claims 95.6%/4.5%/96.5%; **full multi-world test not rerun in this session** | **Reported, pending independent rerun** |
| MMM-001 | Aggregate MMM baseline | V2 candidate | Media incremental revenue under specified policy | No fitted model verified | **Not started** |
| MTA-001 | Compare attribution allocations | V2 candidate | Allocated credit vs simulated causal effects | No fitted model verified | **Not started** |
| INC-001 | Paired randomized social holdout analysis | V2 candidate | Social-on vs social-off, 14-week pulse plus 2-week outcome follow-up | Geo design and read-side QA checked; full inference study pending | **Partially audited, analysis pending** |
| TRI-001 | Align MMM, MTA and experimental evidence | V2 candidate | Comparison on aligned population, policy and outcome windows | No cross-method comparison verified | **Not started** |

For each future study record hypothesis, unit, eligible population, treatment, comparator, time window, outcome, uncertainty, power assumptions, randomization/interference, environment, seed, file hashes, QA evidence, failures and limitations. See [V2 audit](SYNTHETIC_V2_AUDIT.md).
