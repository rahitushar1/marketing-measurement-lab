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
