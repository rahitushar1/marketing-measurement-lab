# Project Charter — Marketing Measurement Lab

**Status:** Initial working charter (2026-11-13). Scope and priorities can evolve through documented decisions.

## Mission
Build a rigorous, reproducible portfolio and learning lab that independently implements Marketing Mix Modeling (MMM), Multi-Touch Attribution (MTA), and incrementality experiment design/analysis on a coherent synthetic business simulation, then triangulates the evidence to make marketing decisions.

## Four equally important outcomes
1. **Technical proficiency:** demonstrate practical skills in data engineering, modeling, statistical and causal fundamentals, existing industry tools, diagnostics, experiments, and interpretation. Learn Git and GitHub by doing.
2. **Measurement judgment:** distinguish attribution credit from causal lift; align estimands, compare uncertainty, diagnose disagreement, and recommend a defensible decision.
3. **Portfolio credibility:** publish reproducible code, test evidence, documented assumptions and limitations, accessible visual explanations, and interview-ready technical case studies.
4. **Professional visibility and opportunities:** cultivate a useful open-source resource; publish updates and a substantive technical article; build warm practitioner relationships and convert qualified interest into conversations, collaborations, referrals, and interviews.

## Audience
Recruiters and hiring managers for marketing science, measurement, analytics, experimentation, and MMM roles; practicing measurement researchers; technically curious marketers and students.

## Intended evidence
- A single plausible, documented causal data-generating process (DGP) with shared underlying simulated outcomes.
- MMM implementations exploring baseline/non-media factors, adstock, saturation, diagnostics, and response curves, using established tools where appropriate (e.g., Meridian or PyMC-Marketing; evaluate Robyn fit/feasibility).
- MTA implementations including journey construction, model comparison, and explanation of bias (e.g., last touch, Markov, Shapley).
- Designed and analyzed simulated randomized experiments; quantify lift, uncertainty, design limits, and comparisons with model estimates. Explore real-world/open data or a genuine live pilot only if feasible and accurately labeled.
- An explicit triangulation case study with aligned targets, ground-truth comparison, uncertainty/sensitivity analyses, business recommendations, and limitations.
- Well-structured GitHub documentation, reproducible environment, automated checks, clear public README, and a sequence of educational releases.

## Working approach
- **Project coordination:** ChatGPT Project / Project HQ; project instructions explain every meaningful action and why it matters.
- **Durable source of truth:** this GitHub repository; decisions and status in `docs/`, work tracked in issues and a GitHub Project board.
- **Learning:** separate ChatGPT conversations for engineering, methods, and networking; capture durable methodological decisions in the repository.
- **Execution:** small, reviewable changes with specific acceptance criteria; use commits, branches, tests, and pull requests as GitHub skills develop.
- **Promotion:** share useful, substantiated insights during the build; seek practitioner feedback respectfully; maintain a separate *private* relationship tracker.

## Non-negotiable quality standards
- Do not claim historical data generator / QA artifacts are verified before independently retrieving and testing them.
- Keep synthetic and real-world experiments clearly distinct; simulated experiments do not establish production experiment execution.
- Disclose assumptions, known causal truth, limitations, biases and uncertainties.
- Avoid publishing confidential employer information, private contacts, passwords, tokens, or proprietary data.
- Every major public technical claim must point to an artifact or reproducible result.
- Optimize for a few deep, defensible implementations rather than superficial tool coverage.

## Success criteria
**Evidence first:** a reviewer can reproduce work and understand why each method was selected, what it estimates, when it fails, and how it changes decisions.
**Attention with quality:** observe relevant repository stars/forks/visits, meaningful reader engagement, credible technical feedback, and warm conversations.
**Career outcomes:** track relevant introductions, recruiter conversations, interviews, referrals, and collaborations separately from vanity metrics.
**Learning:** the owner can independently explain and defend methods and GitHub workflows.

## Scope control
The MVP is three credible case studies plus an honest triangulation capstone. Dashboards, an interactive demo, extra modeling frameworks, additional datasets, and automation are optional extensions evaluated after the MVP.
