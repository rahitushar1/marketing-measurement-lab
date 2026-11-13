# Verification and Evidence Register

Last reviewed: 2026-11-13

This register links claims to artifacts that can independently support them. A statement in chat is not verification.

| ID | Claim / deliverable | Evidence | Verification status |
|---|---|---|---|
| E-001 | Public repository, README and collaboration instructions exist | GitHub repository and main-branch file history | Verified repository foundation only |
| E-002 | Previous synthetic DGP generator works | No recovered code or run output currently in this repository | **Not verified** |
| E-003 | Previous synthetic QA suite passes | No recovered tests or test logs currently in this repository | **Not verified** |
| E-004 | MMM/MTA/experiment pipelines run | No implementation in repository yet | **Not verified** |

## Required evidence for technical completion
- Exact commit/reference, environment or lockfile, seed, and reproduction command.
- Test output, diagnostics, tables/figures with source code and relevant assumptions.
- Expected vs observed behavior, limitations, and failure conditions.
- Links to any issue/PR and run artifacts. Mark simulated experiments clearly.

## Process
When new evidence is obtained, update this table and `docs/STATUS.md`. Keep unsupported claims as pending or unverified.

## E-005 through E-009 — Recovery verification (2026-11-13)

| Evidence ID | Action | Verified result | Remaining boundary |
|---|---|---|---|
| E-005 | Recovered V2 archive and independently inspected `MANIFEST.json` | **45/45** file hashes and lengths match; archive SHA `e1326894d9a2987055f7bf7cbf1b4843cbb5c4aa46f909ff2650f483d622f70c` | Archive not yet committed publicly |
| E-006 | Ran original `qa.py release` | Exit 0, **40/40** passing, zero failed checks | Internal QA rules, not all scientific threats |
| E-007 | Generated pilot afresh and ran `qa.py rerun_pilot` | Exit 0, **40/40**, report exactly equals archived pilot QA JSON | Full release regeneration and full power rerun pending |
| E-008 | Ran original `mechanism_tests` | **17/17** deterministic files equal, **4/4** adversarial corruptions rejected, null-effect tests true for three seeds | Does not prove external fidelity |
| E-009 | Independently summed release ledger, daily and weekly MMM tables | All three revenue aggregates **1,089,355,666 cents**; 164,196 orders, 48 geos, 24 pairs | Model estimation not performed |

Full commands, environment and detailed qualifications: [Synthetic V2 audit](SYNTHETIC_V2_AUDIT.md).

**Status correction to initial E-002/E-003:** The earlier table described the pre-recovery state. As of 2026-11-13, the generator has been recovered and fresh pilot execution verified; the released QA script has been rerun successfully. The complete multi-world power study remains unrerun, and no MMM/MTA fit has been verified.
