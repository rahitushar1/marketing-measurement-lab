# Delivery workflow and GitHub Projects setup

Updated: 2026-11-13
Native GitHub Projects board status: **PENDING OWNER UI STEP**. The connected GitHub integration can edit files/issues but has no Projects create/modify action. Do not mark the board complete merely because this document or its issues exist.

## Intended board
- Name: **Marketing Measurement Lab**
- Type: **Board**; primary grouping field: **Status**
- Columns: **Backlog → Ready → In Progress → Review → Done**
- Default repository: `rahitushar1/marketing-measurement-lab`.
- Useful extra fields (optional): Priority (P0/P1/P2), Workstream (Technical/Learning/Visibility), Milestone (M0–M7).

## One-time UI setup
1. GitHub profile → **Projects** → **New project** → **Board**.
2. Enter `Marketing Measurement Lab`, create. If available, choose **Import items from repository** to import the current issues; otherwise add the repository issues afterwards.
3. Edit the Status single-select options to the five names above. Arrange columns in workflow order.
4. Make **Issue #1** In Progress, completed **Issue #2** Done, source-integration **Issue #4** Ready, and remaining planned tasks Backlog/Ready as appropriate.
5. Save the resulting Project URL in this file and `docs/STATUS.md`, then check the board box in Issue #1.

## Issue-driven work
- One issue per verifiable outcome, with problem, why, scope, dependencies, exit criteria and evidence.
- **Backlog:** idea or dependency; **Ready:** scoped and not blocked; **In Progress:** actively being executed; **Review:** evidence exists, independent check pending; **Done:** exit criteria verified and documentation current.
- Prefer small branches/PRs for code; append relevant test/reproduction output. Do not merge untested code as working.
- Update `STATUS.md`, experiments register, decisions and claims when a conclusion changes.
- Do not expose personal contacts, job applications, confidential source materials or raw personal data in the public repository.

## Handoff format
**Completed:** verified deliverables.
**Evidence:** commit, issue, tests and relevant outputs.
**Blockers:** reasons and owner action if needed.
**Next:** a single verifiable task with scope.
