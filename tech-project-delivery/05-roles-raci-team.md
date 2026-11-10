# 05 — Roles, RACI, Team Composition, Rituals, DoR/DoD, Quality Gates

> Agent-facing reference. Use it to (a) staff a tech project, (b) tell a client who does what and what they pay for, (c) assign RACI per phase, (d) run the rituals, and (e) enforce quality gates. Indonesian terms appear where they help in client conversations (e.g., *PIC* = person in charge, *BAST* = Berita Acara Serah Terima / handover certificate, *UAT* sign-off, *termin* = payment milestone).

---

## 0. Shared vocabulary

**Lifecycle phases used throughout this file**

| # | Phase | Main question | Typical exit artifact |
|---|---|---|---|
| P0 | Discover | Is this problem worth solving? For whom? | Opportunity brief, research synthesis, go/no-go |
| P1 | Define | What exactly will we build, by when, for how much? | PRD/SRS, scope + estimate, SOW/contract, backlog v1 |
| P2 | Design | How will it look and work (UX + architecture)? | Prototype, design system, architecture doc + ADRs, test plan |
| P3 | Build | Build it in increments | Working increments, code reviewed, CI green |
| P4 | Verify | Does it work, is it safe, is it accepted? | Test report, security review, UAT sign-off |
| P5 | Launch | Ship to users safely | Release notes, runbook, go-live checklist, BAST |
| P6 | Operate & Grow | Keep it up, learn, improve, sell | SLO reports, analytics, retros, roadmap v2 |

**Product vs project.** A *project* has a fixed end (typical agency/client work: scope, deadline, budget). A *product* lives on (Lumii, TukaKu): outcomes, metrics, roadmap. Marty Cagan (SVPG) distinguishes three models: *product-owner/backlog-admin*, *feature team* (stakeholders hand over roadmaps of features), and *empowered product team* (team is given problems/OKRs and owns value + viability). Client projects usually run as feature teams; your own products should aim for empowered teams.

**Four product risks (Cagan):** value (will they use/buy it?) → PM; usability → Designer; feasibility → Tech Lead; business viability (legal, sales, finance, compliance) → PM. Use this to decide which role must sign off what.

**RACI letters:** R = Responsible (does the work), A = Accountable (one person, final say/sign-off), C = Consulted (two-way, before), I = Informed (one-way, after). Rule: exactly one A per row; avoid rows with no R; too many C's = slow decisions.

---

## 1. Seniority model (use for hiring, pricing day-rates, and expectations)

Synthesised from public ladders: jorgef/engineeringladders (5 axes: Technology, System, People, Process, Influence; levels D1–D7, TL4–7, TPM4–7, EM5–7), Dropbox Engineering Career Framework (IC1–IC7 for SWE/SRE; ladders also for QE, SDET, MLE, Data Eng, Security, TPM, EM M3–M7), Basecamp "Titles for Programmers" (L1 Junior → L5 Principal), Rent the Runway ladder (Camille Fournier), GitLab Engineering Career Framework.

| Level | Common titles | Scope (what they can own) | Autonomy | Influence |
|---|---|---|---|---|
| L1 | Junior / Associate / Intern | Tightly scoped, routine tasks | Needs daily guidance | Own tasks |
| L2 | Mid / Engineer II | Clearly defined features | Asks for help at right time | Feature |
| L3 | Senior | Substantial feature concept→ship alone; designs medium-large features, reduces tech debt | Self-directed; unblocks others | Team |
| L4 | Staff / Lead / Tech Lead | Owns subsystems, production ops, SLAs; strategic decisions on major components | Sets direction for team | Multiple teams |
| L5 | Principal | Sets direction of a discipline (security, web, mobile) | Defines standards | Company |
| L6–7 | Distinguished / Fellow | Invents new systems/technology used widely | — | Industry |

jorgef axes (each level includes the previous): Technology *Adopts→Specializes→Evangelizes→Masters→Creates*; System *Enhances→Designs→Owns→Evolves→Leads*; People *Learns→Supports→Mentors→Coordinates→Manages*; Process *Follows→Enforces→Challenges→Adjusts→Defines*; Influence *Subsystem→Team→Multiple teams→Company→Community*. Promotion rule of thumb from the same repo: perform at the next level consistently for several months before formalising.

**Tech Lead vs Engineering Manager (jorgef):** TL owns the *System* (architecture, code review, spikes, SLAs, production escalation, 30–70% hands-on coding). EM owns the *People* (hiring, 1:1s, career, performance, delivery, 0–30% coding). Shared: roadmap, process, team visibility. In teams <6, one person often does both — make it explicit.

**Rent the Runway lesson (Fournier):** a vague, short ladder caused more level-negotiation and anxiety, not less; a more specific ladder helped reviews and hiring. → When you write role expectations for a client team or your own hires, be concrete.

**Pricing hint:** client quotes should map each role to a level (e.g., "1× Senior Backend (L3), 0.5× Tech Lead (L4)") and an allocation (FTE %). Rates live in the pricing file; never mix junior output with senior rates.

---

## 2. Role cards

Format per role: **Mission · Responsibilities · Deliverables by phase · Inputs → Outputs (handoffs) · Tools · KPIs · Seniority signals · Failure modes · AI-agent assist.**

### A. Product & delivery leadership

#### A1. Product Manager / Product Owner (PM/PO)
- **Mission:** Maximise value delivered; own the "why" and "what" and the value/viability risks. (Scrum Guide: PO is *one person, not a committee*, accountable for Product Goal, creating/ordering backlog items, keeping backlog transparent.)
- **Responsibilities:** problem framing, discovery, prioritisation (RICE/WSJF/MoSCoW), roadmap, PRD, acceptance criteria, stakeholder alignment, release decisions, metrics.
- **Deliverables:** P0 opportunity brief, competitive scan, success metrics · P1 PRD, user stories + AC, roadmap, release plan · P2 approve prototypes, prioritise scope cuts · P3 backlog refinement, answer questions within 24h · P4 accept stories, UAT plan with client · P5 go/no-go, launch brief · P6 metric review, experiment backlog, roadmap v2.
- **Inputs → outputs:** research, data, client goals, sales feedback → prioritised backlog, PRD, decisions log. Handoff to Designer (problem + constraints), to TL (scope + NFRs), to PMM (positioning).
- **Tools:** Linear/Jira, Notion/Confluence, Figma (comment), Amplitude/Mixpanel/PostHog, Productboard, Google Sheets.
- **KPIs:** outcome metrics (activation, retention, revenue, NPS), % roadmap items that moved a metric, cycle time from idea→live, stakeholder satisfaction.
- **Seniority:** Jr: writes stories for a feature area. Sr: owns a product area's outcomes and discovery. Lead/Group PM: strategy across products, coaches PMs.
- **Failure modes:** "feature factory" (output not outcome); PO as backlog clerk; saying yes to every stakeholder; vague AC; skipping discovery; no kill criteria.
- **AI assist:** draft PRDs/stories/AC from interview notes; cluster feedback; RICE scoring sheet; competitor tables; generate release notes; summarise analytics weekly.

#### A2. Project Manager (PjM) / Delivery Manager / TPM
- **Mission:** Deliver agreed scope on time, budget and quality; own the "when" and "how much". TPM variant (jorgef, Dropbox): coordinates initiatives spanning multiple teams.
- **Responsibilities:** plan, schedule, budget, RAID log (Risks, Assumptions, Issues, Dependencies), change control, status reporting, vendor/client communication, invoicing milestones (*termin*), resource allocation.
- **Deliverables:** P0 rough order of magnitude (ROM) estimate · P1 project charter, WBS, timeline/Gantt, budget, communication plan, SOW with client, RACI · P2–P4 weekly status report, burn-up, change requests (CR), risk register · P5 cutover plan, BAST, lessons learned · P6 warranty/support handover, SLA reports.
- **Inputs → outputs:** contract, estimates from TL, capacity → plan, status, CR decisions; handoff to Support (warranty), Finance (invoices).
- **Tools:** Jira/Linear, MS Project/ClickUp/Asana, Google Sheets, Notion, Slack/WhatsApp groups (common with Indonesian clients — keep decisions in writing).
- **KPIs:** schedule variance, budget variance (EVM: SPI/CPI), # unapproved scope changes (target 0), on-time milestone %, client satisfaction, margin.
- **Seniority:** Jr: tracks tasks. Sr: owns a whole project incl. client & budget. Program/Portfolio: multiple projects, PMO standards.
- **Failure modes:** status "green" until it's red; accepting verbal scope changes; Gantt fiction; meeting overload; protecting schedule by cutting testing.
- **AI assist:** generate WBS from PRD; status report from Jira data; risk register suggestions; meeting minutes → action items; draft CR documents and client emails (Bahasa Indonesia formal register).

#### A3. Scrum Master / Agile Coach
- **Mission:** Team effectiveness (Scrum Guide: accountable for establishing Scrum and the team's effectiveness; serves team, PO and organisation).
- **Responsibilities:** facilitate events within timeboxes, remove impediments, coach self-management, help PO with backlog techniques, track flow metrics, run retros.
- **Deliverables:** working agreements, DoR/DoD drafts, sprint calendar, impediment log, retro actions, flow dashboards (cycle time, WIP).
- **Inputs → outputs:** team signals, metrics → improvement actions; handoff: impediments to EM/PjM.
- **Tools:** Jira/Linear boards, Miro/FigJam (retros), Parabol/EasyRetro, Slack.
- **KPIs:** sprint goal hit rate, predictability (planned vs done), cycle time trend, retro action completion %, team health survey.
- **Seniority:** Jr: one team facilitator. Sr: multiple teams, org-level impediments. Agile coach: org transformation.
- **Failure modes:** "Scrum police"/meeting secretary; velocity as productivity target; retros with no follow-through. In teams <8, usually a hat worn by PjM or TL, not a full-time role.
- **AI assist:** retro theme clustering, agenda prep, impediment trend analysis, timebox reminders, auto-summaries of standups.

#### A4. Business Analyst (BA)
- **Mission:** Translate business needs into precise, testable requirements; bridge client domain ↔ team.
- **Responsibilities:** elicitation workshops, as-is/to-be process maps (BPMN), use cases, business rules, data dictionaries, gap analysis, traceability matrix, UAT scenarios.
- **Deliverables:** P0 stakeholder map, as-is process · P1 BRD/SRS (*dokumen kebutuhan*), use cases, business rules catalog, data requirements · P2 validate wireframes against rules · P4 UAT scripts, requirement traceability matrix (RTM) · P5 training material input.
- **Inputs → outputs:** interviews, existing forms/Excel, regulations → requirements; handoff to PM/PO (backlog), QA (test basis), Designer (flows).
- **Tools:** Confluence/Notion, draw.io/Lucidchart, BPMN tools, Excel, Jira.
- **KPIs:** requirement defects found after build (lower is better), rework %, # change requests caused by missed requirements, UAT pass rate first round.
- **Failure modes:** documentation without validation; specifying solutions instead of needs; requirements frozen too early on uncertain products.
- **AI assist:** transcribe & structure workshop notes, generate use-case/AC drafts, detect contradictions/ambiguity ("fast", "user-friendly"), build RTM, convert Excel processes to BPMN text.

#### A5. Stakeholder / Client Sponsor (and client PIC)
- **Mission:** Provide business goals, budget, domain knowledge, timely decisions and acceptance.
- **Responsibilities:** approve scope/budget, nominate a single decision-maker (*PIC*), provide data/access/content, attend reviews, perform UAT, sign BAST, pay *termin*.
- **Deliverables:** business objectives, signed SOW/PO, content & test data, review feedback within agreed SLA (e.g., 3 working days), UAT sign-off.
- **KPIs (that you track about them):** decision latency, feedback turnaround, attendance at reviews. Write these into the contract as client dependencies.
- **Failure modes:** many voices/no single PIC; feedback via WhatsApp voice notes not logged; disappearing until UAT then requesting redesign; unpaid termin used as leverage.
- **AI assist:** convert scattered chat feedback into a logged decision/CR list; prepare executive one-pagers; translate tech status into business language.

### B. Research & design

#### B1. UX Researcher
- **Mission:** Reduce value/usability risk with evidence about users.
- **Responsibilities:** research plans, recruiting, interviews, usability tests, surveys, journey maps, personas/JTBD, synthesis, insight repository.
- **Deliverables:** P0 research plan, interview guide, synthesis (affinity map), opportunity areas · P2 usability test results with severity · P6 post-launch studies, satisfaction surveys.
- **Handoffs:** insights → PM (prioritisation), Designer (design principles), PMM (messaging).
- **Tools:** Dovetail, Maze, Lookback, UserTesting, Google Forms/Typeform, Miro.
- **KPIs:** % roadmap decisions backed by research, # critical usability issues found pre-launch, time from question→insight.
- **Failure modes:** research theatre (reports nobody reads); leading questions; testing only with friends; only quant or only qual.
- **AI assist:** interview guides, transcript tagging & clustering (verify quotes), survey design, synthetic "pre-test" of copy (never a substitute for real users).

#### B2. UX / UI / Product Designer
- **Mission:** Own usability & desirability; turn problems into flows and interfaces that ship.
- **Responsibilities:** IA, user flows, wireframes, high-fidelity UI, prototypes, design system/tokens, accessibility (WCAG 2.2 AA), design QA of built screens.
- **Deliverables:** P1 flows & low-fi · P2 hi-fi Figma, clickable prototype, design system components, spec/redlines, empty/error/loading states · P3 dev handoff (Dev Mode), answer questions · P4 design QA checklist · P6 iteration from analytics.
- **Inputs → outputs:** PRD, research, brand → Figma files + specs; handoff to FE/Mobile (components, tokens, assets), UX Writer (copy slots).
- **Tools:** Figma, FigJam, Framer, Storybook (review), Zeplin, Lottie.
- **KPIs:** task success rate, SUS score, design-to-dev rework, accessibility issues, consistency (% screens using system components).
- **Failure modes:** pixel-perfect mockups without states; designing for desktop only (Indonesia is mobile-first, low-end Android); no handoff conversation; ignoring feasibility.
- **AI assist:** generate UI variants and copy placeholders, accessibility contrast checks, convert Figma to component code drafts, heuristic evaluation (Nielsen's 10).

#### B3. UX Writer / Content Designer
- **Mission:** Clear, consistent product language that helps users act.
- **Responsibilities:** microcopy, error messages, onboarding, voice & tone guide, terminology glossary, localisation (Bahasa Indonesia / English), notification & email copy.
- **Deliverables:** content guidelines, copy deck per screen, glossary, string files review.
- **Tools:** Figma, Ditto/Frontitude, Lokalise/Crowdin, Google Docs.
- **KPIs:** task completion on copy-heavy flows, support tickets about confusion, translation consistency.
- **Failure modes:** copy added last; inconsistent terms ("saldo/balance/dompet"); literal translations.
- **AI assist:** draft copy variants, enforce glossary, translate ID↔EN with tone rules (human review), find inconsistent strings in code.

### C. Engineering leadership & architecture

#### C1. Tech Lead (TL) / Engineering Manager (EM)
- **Mission:** TL: technical quality and feasibility of the *system*. EM: delivery and health of the *people* (see §1 table).
- **Responsibilities (TL):** architecture within team, estimates, code review standards, spikes, tech-debt plan, production escalation, SLAs/monitoring. **(EM):** hiring, 1:1s, career growth, performance, capacity planning, process, cross-team alignment.
- **Deliverables:** P1 estimates, feasibility notes, tech risks · P2 technical design doc, ADRs, repo/CI scaffold, coding standards · P3 code reviews, unblocking, tech-debt tickets · P4 release readiness review · P5 deploy plan, rollback plan · P6 incident postmortems, debt roadmap. EM: hiring plan, onboarding plan, team health, performance reviews.
- **Tools:** GitHub/GitLab, IDE, CI, observability, ADR templates, Lattice/Notion (EM).
- **KPIs:** DORA metrics (deployment frequency, lead time for changes, change failure rate, time to restore), escaped defects, PR review latency; EM: retention, hiring time, eNPS/team health.
- **Seniority:** TL ≈ L4+ (jorgef TL4–TL7); EM M3+ (Dropbox) / EM5+ (jorgef).
- **Failure modes:** TL who codes everything (bus factor 1); EM who cancels 1:1s; hero culture; no written decisions.
- **AI assist:** first-pass code review, ADR drafting, estimate sanity checks against history, onboarding docs, 1:1 note templates, DORA metric extraction from Git/CI.

#### C2. Software Architect / Solution Architect
- **Mission:** Make the right structural decisions early (and reversible ones cheaply); own NFRs across systems.
- **Responsibilities:** solution architecture, technology selection, integration design, NFRs (performance, availability, security, scalability, cost), architecture reviews, governance.
- **Deliverables:** P1 NFR list, solution options with cost, build-vs-buy · P2 C4 diagrams (context/container/component), ADRs, data model, API contracts, threat model with Security, capacity & cost estimate · P3 architecture fitness checks · P6 evolution roadmap.
- **Handoffs:** to TL/devs (contracts, patterns), DevOps (deployment topology), DBA (data model), Security (threat model).
- **Tools:** draw.io, Structurizr/C4, Excalidraw, OpenAPI, cloud calculators.
- **KPIs:** % NFRs met at launch, architecture-caused incidents, infra cost vs estimate, time to onboard new service.
- **Failure modes:** ivory-tower diagrams; microservices for a 3-person team; resume-driven tech choices; undocumented decisions.
- **AI assist:** generate options matrix, draft ADRs (joelparkerhenderson/architecture-decision-record templates), C4 in Mermaid/PlantUML, cost estimates (verify with official calculators).

### D. Engineering ICs

#### D1. Frontend Engineer
- **Mission:** Fast, accessible, correct web UI.
- **Responsibilities:** components, state, API integration, performance (Core Web Vitals), accessibility, responsive design, frontend tests, SEO where relevant.
- **Deliverables:** component library/Storybook, pages/features, unit & e2e tests, performance budget report.
- **Inputs → outputs:** Figma + API contract → UI code; handoff to QA (testable build + test IDs).
- **Tools:** React/Next.js/Vue, TypeScript, Tailwind, Vite, Playwright/Cypress, Vitest/Jest, Lighthouse.
- **KPIs:** LCP/INP/CLS, JS bundle size, UI defect rate, a11y violations.
- **Failure modes:** building before API contract exists; no loading/error states; giant bundles on low-end phones.
- **AI assist:** component scaffolding from Figma, test generation, a11y/perf audit fixes, refactors.

#### D2. Mobile Engineer (Android/iOS/cross-platform)
- **Mission:** Reliable native-quality apps across devices and networks.
- **Responsibilities:** app architecture, offline/poor-network handling, push notifications, store releases, crash monitoring, device matrix testing, deep links.
- **Deliverables:** builds per sprint (TestFlight / Play internal track), store listing assets with PMM, release checklist, crash reports.
- **Tools:** Kotlin/Jetpack Compose, Swift/SwiftUI, Flutter/React Native, Firebase (Crashlytics, FCM), Fastlane, Codemagic/Bitrise.
- **KPIs:** crash-free sessions (target ≥99.5%), app start time, APK size, store rating, release cadence.
- **Failure modes:** testing only on flagship devices; forgetting store review lead time; hard-coded config without remote flags.
- **AI assist:** boilerplate, platform API lookup, crash log triage, store listing drafts, localisation strings.

#### D3. Backend Engineer
- **Mission:** Correct, secure, scalable business logic and APIs.
- **Responsibilities:** API design, domain logic, data access, integrations (payment gateways e.g., Midtrans/Xendit, WhatsApp Business API), auth, background jobs, tests, observability hooks.
- **Deliverables:** OpenAPI spec, services, migrations, unit/integration tests, runbook entries.
- **Tools:** Node/NestJS, Python/FastAPI/Django, Go, Laravel (common in ID), PostgreSQL, Redis, queues, Docker.
- **KPIs:** p95 latency, error rate, test coverage of critical paths, defects escaped, PR cycle time.
- **Failure modes:** no idempotency on payment webhooks; N+1 queries; secrets in repo; breaking API changes without versioning.
- **AI assist:** API scaffolding, test generation, SQL review, log analysis, migration scripts (review carefully).

#### D4. Full-stack Engineer
- **Mission:** Ship complete vertical slices end-to-end — the default hire for 2–8-person teams.
- **Responsibilities:** FE + BE + basic infra for a feature; generalist judgement on where to put logic.
- **KPIs:** features shipped to production with low rework; lead time.
- **Failure modes:** shallow in both; neglecting security/DB design; becoming de-facto DevOps without time budget.
- **AI assist:** strongest leverage role — agent pairs on everything; keep human ownership of architecture and security.

#### D5. DevOps / Platform Engineer
- **Mission:** Make shipping fast and safe; give developers a paved road (platform as a product).
- **Responsibilities:** CI/CD, IaC, environments (dev/staging/prod), containerisation, secrets, cost management, backups, developer tooling.
- **Deliverables:** P2 environment plan, IaC repo, CI pipeline · P3 preview environments, deploy automation · P5 production setup, backup/restore test, rollback mechanism · P6 cost report, platform roadmap.
- **Tools:** GitHub Actions/GitLab CI, Terraform/OpenTofu, Docker, Kubernetes (only when justified), Argo CD, cloud (AWS/GCP; GCP and AWS have Jakarta regions), Vault/SOPS.
- **KPIs:** DORA metrics, pipeline duration, environment provisioning time, infra cost/month vs budget.
- **Failure modes:** Kubernetes for one app; snowflake servers; untested backups; prod access for everyone.
- **AI assist:** generate pipelines/Terraform modules, explain failing builds, cost anomaly summaries.

#### D6. Site Reliability Engineer (SRE)
- **Mission:** Reliability as a feature, managed with SLOs and error budgets.
- **Responsibilities:** SLIs/SLOs, monitoring & alerting, on-call, incident management, postmortems, capacity planning, toil reduction. Google SRE book: keep toil below 50% of each SRE's time; the rest is engineering that reduces future toil.
- **Deliverables:** SLO document, alert rules, runbooks/playbooks, incident process, blameless postmortems, launch checklist (cf. Google SRE Appendix E "Launch Coordination Checklist").
- **Tools:** Prometheus/Grafana, Datadog/New Relic, Sentry, OpenTelemetry, PagerDuty/Opsgenie, status page.
- **KPIs:** SLO attainment, error budget burn, MTTR/time to restore, alerts per on-call shift, toil %.
- **Failure modes:** alerting on causes not symptoms (pager fatigue); 100% availability targets; postmortems that blame people.
- **AI assist:** incident timeline drafting, log/trace summarisation, runbook generation, postmortem first drafts.

#### D7. Database Administrator (DBA) / Database Reliability Engineer
- **Mission:** Data integrity, performance and recoverability.
- **Responsibilities:** schema review, indexing, query tuning, backups/PITR, replication, migrations safety, access control, retention policies.
- **Deliverables:** data model review, backup & restore runbook (tested), migration review checklist, performance reports.
- **Tools:** PostgreSQL/MySQL tooling, pg_stat_statements, managed DB consoles (RDS/Cloud SQL), Flyway/Prisma/Alembic.
- **KPIs:** RPO/RTO met in drills, slow-query count, storage growth vs forecast, migration incidents.
- **Failure modes:** never-tested restores; locking migrations at peak hours; shared admin credentials. Small teams: use managed DB + Backend/DevOps covers DBA duties.
- **AI assist:** EXPLAIN plan analysis, index suggestions, migration risk review.

### E. Quality & security

#### E1. QA Engineer / SDET
- **Mission:** Build confidence that the product works as specified and catch defects as early (cheaply) as possible. Dropbox has separate QE and SDET ladders.
- **Responsibilities:** test strategy & plan, test cases from AC, exploratory testing, automation (API/e2e), regression suites, bug triage, release sign-off input, UAT support.
- **Deliverables:** P1 review AC for testability · P2 test plan & strategy (test pyramid) · P3 automated tests in CI, test data · P4 test execution report, defect log, regression pass · P5 smoke test in prod · P6 escaped-defect analysis.
- **Tools:** Playwright/Cypress, Appium/Maestro, Postman/Newman, k6/JMeter, TestRail/Qase, BrowserStack.
- **KPIs:** escaped defects (prod bugs per release), defect detection %, automation coverage of critical flows, regression run time.
- **Failure modes:** QA as a phase at the end; flaky test suites ignored; "QA approves" replacing developer ownership of quality.
- **AI assist:** generate test cases from AC (incl. edge cases), write automation scripts, triage duplicates, test data generation.

#### E2. Security Engineer / AppSec
- **Mission:** Reduce the likelihood and impact of breaches; keep compliance evidence.
- **Responsibilities:** threat modelling (STRIDE), secure SDLC, SAST/DAST/SCA, secrets management, pen-test coordination, IAM, incident response, security requirements (OWASP ASVS levels).
- **Deliverables:** P1 security requirements (ASVS L1/L2) · P2 threat model · P3 scanning in CI · P4 pen-test/vuln report & remediation · P5 security go-live checklist · P6 vulnerability management, access reviews.
- **Tools:** OWASP ZAP, Semgrep, Dependabot/Renovate, Trivy, gitleaks, Snyk, cloud security posture tools.
- **KPIs:** critical vulns open > SLA (target 0), mean time to remediate, % repos with scanning, secrets leaked.
- **Failure modes:** security review only before launch; checkbox compliance; blocking without offering fixes.
- **AI assist:** threat-model drafts, triage scanner output, explain CVEs, secure code review hints (verify).

### F. Data & AI

#### F1. Data Analyst
- **Mission:** Turn data into decisions.
- **Responsibilities:** metric definitions, tracking plan, dashboards, ad-hoc analysis, A/B test analysis, reporting to stakeholders.
- **Deliverables:** P1 KPI tree & tracking plan (events + properties) · P3 event QA · P5 launch dashboard · P6 weekly metrics review, experiment readouts.
- **Tools:** SQL, Metabase/Looker Studio/Power BI, PostHog/Amplitude/Mixpanel, Google Sheets, Python.
- **KPIs:** decisions influenced, dashboard adoption, metric trust (no conflicting numbers).
- **Failure modes:** vanity metrics; tracking added after launch; definitions differ across dashboards.
- **AI assist:** SQL drafting, chart narration, anomaly explanation, tracking-plan generation from PRD.

#### F2. Data Engineer
- **Mission:** Reliable, timely, documented data pipelines.
- **Responsibilities:** ingestion (ELT), warehouse modelling, orchestration, data quality tests, lineage, privacy controls (PII masking).
- **Tools:** dbt, Airflow/Dagster, BigQuery/Snowflake/Postgres, Airbyte/Fivetran, Great Expectations.
- **KPIs:** pipeline freshness SLA, failed runs, data-quality test pass %, cost per query/TB.
- **Failure modes:** building a warehouse before there are questions; no tests; PII copied everywhere.
- **AI assist:** dbt model scaffolding, SQL optimisation, documentation generation.

#### F3. Data Scientist / ML Engineer
- **Mission:** Models and statistical insight that measurably improve product outcomes. Dropbox has a separate MLE ladder.
- **Responsibilities:** problem framing as ML, feature engineering, training/evaluation, experiment design, model deployment & monitoring (with MLE/MLOps), drift detection.
- **Deliverables:** baseline (heuristic first), model card, offline eval report, online A/B plan, monitoring dashboard.
- **Tools:** Python, pandas/polars, scikit-learn, PyTorch, MLflow/W&B, notebooks, feature stores.
- **KPIs:** business metric lift, model quality metrics, inference latency/cost, drift alerts.
- **Failure modes:** model with no baseline; notebook never productionised; leakage; no monitoring.
- **AI assist:** EDA code, experiment tracking summaries, documentation.

#### F4. AI / LLM Engineer (key role for Lumii-type products)
- **Mission:** Ship LLM features that are useful, grounded, safe and affordable.
- **Responsibilities:** model/provider selection, prompt & tool design, RAG (chunking, embeddings, retrieval), agents/tool calling, evaluation sets & regression evals, guardrails (PII, prompt injection, jailbreaks), latency/cost optimisation, observability (traces), fallback strategy.
- **Deliverables:** P0 feasibility spike + eval baseline · P1 AI behaviour spec (what it must/never do), eval dataset (golden Q&A) · P2 architecture (RAG/agent), cost model per request/user · P3 prompts as versioned code, eval CI · P4 red-team report, eval pass thresholds · P5 rate limits, kill switch · P6 online feedback loop, eval drift, cost reports.
- **Tools:** OpenAI/Anthropic/Gemini APIs, open models (vLLM/Ollama), LangChain/LlamaIndex or plain SDKs, pgvector/Qdrant, Langfuse/LangSmith/Helicone, promptfoo/Ragas evals (see tensorchord/Awesome-LLMOps, EthicalML/awesome-production-machine-learning).
- **KPIs:** eval pass rate, hallucination/groundedness rate, task success, p95 latency, cost per conversation, user thumbs-up %, escalation-to-human rate.
- **Failure modes:** "vibe-checked" prompts with no eval set; no cost cap; sending PII to third-party models without consent/DPA (UU PDP risk); no fallback when provider is down.
- **AI assist:** generate eval cases, adversarial prompts, compare model outputs, summarise traces.

### G. Go-to-market, customers & governance

#### G1. Product Marketing Manager (PMM)
- **Mission:** Positioning, messaging and launch so the right customers understand why to buy.
- **Responsibilities:** ICP & personas, positioning, pricing/packaging input, launch plans, sales enablement, website & store copy, competitive battlecards.
- **Deliverables:** P0 market sizing, competitor matrix · P1 positioning doc · P5 launch plan, landing page, app store listing, pitch deck, demo script · P6 win/loss analysis.
- **Tools:** Notion, Figma/Canva, HubSpot, Webflow/Framer, Google Analytics.
- **KPIs:** launch adoption, conversion on landing pages, sales cycle length, win rate.
- **Failure modes:** joining after the product is built; feature-list messaging.
- **AI assist:** positioning drafts, landing copy variants, battlecards, translations, demo scripts.

#### G2. Growth (Growth PM / Growth Marketer / Growth Engineer)
- **Mission:** Grow acquisition, activation, retention, referral, revenue (AARRR) via experiments.
- **Responsibilities:** funnel analysis, experiment backlog (ICE), onboarding optimisation, referral/lifecycle (email/WA/push), paid & SEO channels.
- **Deliverables:** growth model, experiment docs (hypothesis, metric, sample size, result), lifecycle campaigns.
- **Tools:** PostHog/Amplitude, GrowthBook/Statsig (flags & A/B), Customer.io/Braze/OneSignal, Google/Meta Ads, SEO tools.
- **KPIs:** north-star metric, activation %, D7/D30 retention, CAC, LTV/CAC, experiment velocity & win rate.
- **Failure modes:** dark patterns; underpowered tests; growth on a leaky bucket (poor retention).
- **AI assist:** hypothesis generation, sample-size calculation, ad/email variants, cohort analysis.

#### G3. Customer Support / Customer Success (CS)
- **Mission:** Support: resolve issues fast. Success: ensure customers reach outcomes, renew and expand (B2B).
- **Responsibilities:** ticket handling (L1/L2), knowledge base, escalation to engineering (L3), onboarding & training clients, health scoring, renewals, feedback loop to PM.
- **Deliverables:** support playbook & macros, FAQ/help centre, escalation matrix with severities, onboarding plan, QBR deck, monthly feedback digest.
- **Tools:** Zendesk/Freshdesk/Intercom/Crisp, WhatsApp Business (dominant channel in Indonesia), Qontak/Mekari, Notion help centre.
- **KPIs:** first response time, resolution time, CSAT, ticket deflection %, churn/NRR (B2B), time-to-value.
- **Failure modes:** engineers doing L1 support; bugs reported without repro; feedback never reaching roadmap.
- **AI assist:** AI first-line responder with handoff, ticket summarisation & tagging, KB article drafting, sentiment trend.

#### G4. Technical Writer
- **Mission:** Docs that let users, developers and operators succeed without asking.
- **Responsibilities:** user guides (*buku panduan*), API docs, admin manuals, release notes, runbooks review, docs-as-code.
- **Deliverables:** P2 docs plan & IA · P3–P4 API reference (from OpenAPI), user manual · P5 release notes, training material, handover docs (part of BAST package) · P6 doc updates per release.
- **Tools:** Docusaurus/MkDocs/Mintlify, Markdown, Swagger/Redoc, Loom/Scribe.
- **KPIs:** support tickets deflected by docs, docs freshness, time-to-first-API-call.
- **Failure modes:** docs written once and rotting; no owner; screenshots out of date.
- **AI assist:** generate docs from code/OpenAPI, keep release notes from commits, translate ID/EN, detect stale pages.

#### G5. Legal & Compliance (in-house counsel, DPO, external lawyer)
- **Mission:** Make the product legally shippable and contracts enforceable.
- **Responsibilities:** contracts (SOW/MSA, NDA, SLA, IP ownership & source-code handover clauses), Terms of Service, Privacy Policy, data processing agreements, regulatory checks. Indonesia: UU No. 27/2022 on Personal Data Protection (UU PDP) — consent, data-subject rights, breach notification, DPO where required; registration as electronic system operator (PSE) under PP 71/2019 and ministry regulations; sector rules (e.g., OJK for financial services, BI for payments); tax invoicing (e-Faktur) for services — verify current rules with a qualified professional.
- **Deliverables:** P1 contract & SOW review, data inventory/DPIA trigger check · P2 privacy-by-design review · P5 ToS, privacy policy, consent flows approved · P6 incident/breach procedure, contract renewals.
- **KPIs:** contract turnaround, compliance findings open, zero regulatory incidents.
- **Failure modes:** engaged after launch; copying foreign ToS templates; unclear IP ownership with clients (major dispute source for agencies).
- **AI assist:** first-draft clauses and checklists, compare contract versions, map data flows for DPIA — always final review by a qualified lawyer.

---

## 3. Master RACI matrix (by lifecycle activity)

Roles (columns): **PM** = PM/PO · **PjM** = Project/Delivery Mgr · **SM** = Scrum Master · **BA** · **SH** = Client Sponsor/Stakeholder · **UXR** · **DES** = Designer (+UX Writer) · **TL** = Tech Lead/EM · **ARC** = Architect · **DEV** = FE/Mobile/BE/Full-stack · **OPS** = DevOps/SRE/DBA · **QA** · **SEC** · **DATA** = Analyst/DE/DS · **AI** = AI/LLM Eng · **GTM** = PMM/Growth · **CS** = Support/Success · **TW** = Tech Writer · **LEG** = Legal.

| Phase | Activity | PM | PjM | SM | BA | SH | UXR | DES | TL | ARC | DEV | OPS | QA | SEC | DATA | AI | GTM | CS | TW | LEG |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| P0 | Business goal & budget | C | C | | C | **A/R** | | | I | | | | | | C | | C | C | | I |
| P0 | User/market research | A | I | | C | C | **R** | C | I | | | | | | C | | C | C | | |
| P0 | Feasibility spike (incl. AI) | C | I | | | I | | | **A** | C | R | C | | C | C | R | | | | |
| P0 | Go / no-go | R | C | | C | **A** | C | C | C | C | | | | C | C | C | C | | | C |
| P1 | Requirements / PRD / SRS | **A** | C | | R | C | C | C | C | C | I | I | C | C | C | C | C | C | I | C |
| P1 | Estimate & plan | C | **A/R** | C | C | I | | C | R | C | C | C | C | C | | C | | | | |
| P1 | SOW / contract / pricing | C | R | | C | **A** (client) | | | C | C | | | | | | | | | | R |
| P1 | Backlog ordering | **A/R** | C | C | C | C | | C | C | | C | | C | | | | | | | |
| P2 | UX design & prototype | C | I | | C | C | C | **A/R** | C | | C | | C | | | C | C | | | |
| P2 | Architecture & ADRs | I | I | | | | | C | **A** | R | C | C | C | C | C | C | | | | |
| P2 | Threat model & privacy review | I | I | | | I | | | C | C | C | C | | **A/R** | C | C | | | | C |
| P2 | Test strategy | C | I | | C | | | | C | | C | C | **A/R** | C | | C | | | | |
| P2 | Tracking plan / KPIs | A | | | C | C | | C | C | | C | | | | **R** | C | C | | | |
| P3 | Sprint planning | A (what) | C | R (facilitate) | C | | | C | C | | **R** (how) | C | C | | | C | | | | |
| P3 | Implementation & code review | I | I | | | | | C | **A** | C | **R** | C | C | C | C | R | | | | |
| P3 | CI/CD & environments | | I | | | | | | A | C | C | **R** | C | C | | | | | | |
| P3 | AI evals & guardrails | C | | | | | | | A | | C | | C | C | C | **R** | | | | C |
| P3 | Sprint review / demo | **A** | R | R (facilitate) | C | C | | R | R | | R | | R | | | | I | I | | |
| P3 | Change requests | C | **A/R** | | C | **A** (approve $) | | C | C | C | | | | | | | | | | C |
| P4 | System & regression testing | I | I | | | | | C | C | | R | C | **A/R** | | | R | | | | |
| P4 | Security testing / pen-test | I | I | | | I | | | C | C | R (fix) | C | C | **A/R** | | | | | | |
| P4 | Performance / load test | I | I | | | | | | A | C | R | **R** | R | | | | | | | |
| P4 | UAT & acceptance | R | R | | R | **A** | | C | C | | C | | R | | | | | C | C | |
| P5 | Go-live decision | R | R | | | **A** | | | R | C | | R | R | R | | C | C | C | | C |
| P5 | Deployment & rollback plan | I | C | | | | | | **A** | C | R | **R** | C | C | | | | | | |
| P5 | Docs, training, release notes | C | C | | C | I | | C | C | | C | C | C | | | | C | C | **A/R** | |
| P5 | Launch / marketing | C | I | | | C | | C | I | | | | | | C | | **A/R** | C | C | C |
| P5 | Handover (BAST, source code, credentials) | C | **A/R** | | C | R (sign) | | | R | C | | R | | C | | | | C | R | C |
| P5 | ToS / privacy / consent | C | I | | | C | | C | | | C | | | C | C | C | C | | | **A/R** |
| P6 | Monitoring, on-call, incidents | I | I | | | I | | | A | | R | **R** | | C | | C | | C | | |
| P6 | Postmortems | I | I | C | | I | | | **A** | C | R | R | C | C | | C | | C | | |
| P6 | Support & success | C | I | | | I | | | C (L3) | | C | C | | | | | | **A/R** | C | |
| P6 | Metrics review & roadmap v2 | **A/R** | C | | C | C | C | C | C | | | | | | R | C | R | C | | |

**How to adapt:** for small teams collapse columns (one person can hold several letters), but keep **one A per row**. For client projects the client sponsor is A for money/scope/acceptance; your PjM is A for delivery; your TL is A for technical quality. Put this table into the SOW appendix so acceptance authority is contractual.

---

## 4. Team composition by project size

Principles: Scrum Guide — teams "typically 10 or fewer people", split into multiple teams sharing one Product Goal, backlog and PO when larger. Team Topologies (Skelton & Pais) — stream-aligned teams for product flows, a platform team providing self-service infra, enabling teams that coach, complicated-subsystem teams (e.g., ML/AI core) for deep specialties. Cagan's core trio: PM + Product Designer + Tech Lead, with access to data and research.

### 4.1 Micro (2–3 people) — MVP, prototype, small client app (≈1–3 months)
| Seat | Hats worn |
|---|---|
| Founder / PM-PjM (e.g., Nicky) | PM, PjM, BA, client PIC contact, PMM, CS L1, Scrum-lite facilitator |
| Senior full-stack (TL) | TL, Architect, BE, DevOps (managed platforms: Vercel/Render/Supabase/Firebase), DBA, Security basics |
| Full-stack / Mobile or Designer-dev | FE/Mobile, UI design (from UI kit), QA by peer testing |
**Freelance/outsourced on demand:** UI designer (2–3 weeks), lawyer (contract/privacy), pen-test before launch if handling money/PII. **Process:** Kanban + weekly demo; DoD includes self-QA checklist; AI agent covers tests, docs, release notes.

### 4.2 Small (5–8) — production product or mid-size client system (≈3–6 months)
PM/PO (1) · PjM/Delivery (0.5, often combined with PM for internal products; separate for client work) · Product Designer (1, also UX writing) · Tech Lead (1, hands-on) · Engineers 3–4 (FE, BE, Mobile/Full-stack mix) · QA (1, manual + automation) · DevOps (0.25–0.5 shared or TL) · AI/LLM Eng (1 if AI-core product, else embedded in BE) · Data analyst (0.25) · Fractional: security review, lawyer, PMM. **Process:** 2-week Scrum; SM hat on PjM/TL.

### 4.3 Medium (10–20) — 2–3 teams
Product: Head of Product or Lead PM + 1 PM/PO per team · 1–2 Designers + 0.5 UX researcher · EM (1–2) + TL per team · Architect (0.5–1) · 2–3 stream-aligned teams of 4–6 engineers each (one per domain, e.g., Customer App / Merchant Dashboard / AI Core) · Platform/DevOps team of 1–2 (+ SRE practices) · QA 2–3 (or SDET embedded per team) · Security engineer (0.5–1) · Data: 1 analyst + 1 data engineer · PMM 1, Growth 1, CS 1–3, Tech Writer 0.5. **Process:** Scrum per team + cross-team sync (Scrum of Scrums), quarterly planning, shared DoD.

### 4.4 Large (30+) — multiple products / enterprise client programme
Program/portfolio management (PMO, TPMs) · Product org with Group PMs · Design org with design system team, research ops · Engineering org: EMs (≈1 per 5–8 engineers), Staff/Principal engineers, Architecture review board · Platform team(s), SRE team with on-call rotations, DBA/data platform · QA/SDET guild · Security team (AppSec + GRC) · Data team (analytics, DE, DS/ML) · AI platform team (shared LLM gateway, evals, guardrails) · GTM: PMM, Growth, Sales engineering · Support L1–L3, Customer Success managers · Docs team · Legal & compliance/DPO. **Process:** quarterly/PI planning, OKRs, RFC/ADR process, incident management with severity levels, release trains or continuous delivery with feature flags.

### 4.5 Ratio heuristics (sanity checks, not rules)
- 1 PM per 1 stream-aligned team (≈4–8 engineers).
- 1 Product Designer per 1–2 teams; designers <1:10 to engineers → expect UX debt.
- 1 QA per 3–6 engineers when automation is immature; fewer when devs own tests.
- 1 EM per 5–8 direct reports; above 8, 1:1 quality drops.
- SRE: Google advises ≤50% toil; if on-call pages more than ~2 incidents/shift, fix reliability before adding features.
- Every role with bus factor 1 (typically DevOps, TL, the only mobile dev) needs written runbooks and a documented backup.

### 4.6 Indonesian client-project staffing notes
- Clients expect a named **PIC** on both sides and frequent WhatsApp contact: assign PjM as the single channel; log decisions in a shared doc/Jira weekly.
- Government/enterprise tenders often require named CVs and certifications for roles (PM, analyst, programmer, tester) — keep standard CVs ready per role/level.
- Budget proposals (*RAB*) commonly list man-months per role × rate; the role list in §2 maps directly to RAB line items.

---

## 5. Rituals & meeting calendar

Scrum Guide 2020 timeboxes (for a one-month sprint; shorter sprints → proportionally shorter): Sprint ≤ 1 month · Sprint Planning ≤ 8h · Daily Scrum 15 min · Sprint Review ≤ 4h · Sprint Retrospective ≤ 3h. Backlog refinement is ongoing (rule of thumb ≤10% of capacity).

### 5.1 Two-week sprint calendar (team of 5–8)
| When | Ritual | Who | Length | Output |
|---|---|---|---|---|
| Day 1 (Mon) AM | Sprint Planning | PO, devs, QA, designer; SM facilitates | 2–4h | Sprint goal, sprint backlog, capacity |
| Daily | Daily Scrum / standup | Devs (+PO optional) | 15 min | Plan for next 24h, blockers |
| Weekly (Wed) | Backlog refinement | PO, TL, 2–3 devs, QA, designer | 1h | Stories meeting DoR for next sprint |
| Weekly | Design review / critique | Designer, PM, TL | 45 min | Approved designs |
| Weekly | Client status (client work) | PjM, client PIC, PM | 30–45 min | Status, decisions, CRs, risks |
| Weekly | Tech sync / architecture | TL, architect, senior devs | 45 min | ADRs, tech-debt decisions |
| Bi-weekly | 1:1s | EM ↔ each report | 30 min | Growth, feedback, blockers |
| Day 10 (Fri) | Sprint Review / demo | Team + stakeholders/client | 1–2h | Feedback, backlog updates |
| Day 10 (Fri) | Retrospective | Scrum team only | 1–1.5h | 1–3 owned improvement actions |
| Monthly | Metrics review | PM, data, GTM, TL | 1h | Insights → roadmap |
| Monthly | Steering committee (client) | Sponsor, PjM, PM, TL | 1h | Budget, scope, timeline decisions |
| Quarterly | OKR / roadmap planning | Leads, PMs | ½–1 day | Quarterly objectives |
| Per incident | Postmortem | TL, OPS, involved devs | 1h within 5 working days | Blameless report + actions |
| Per release | Go/no-go | PM, PjM, TL, QA, OPS, SEC, client | 30 min | Signed release decision |

### 5.2 Kanban variant (2–3 people / support mode)
Daily async check-in (Slack/WA thread), weekly 45-min planning+demo combined, monthly retro, WIP limit ≈ 1–2 per person, replenish on demand.

### 5.3 Meeting hygiene rules
Agenda + desired decision in invite; notes and action items (owner + date) posted within 24h; cancel if no agenda; prefer async written updates for status (GitLab handbook-first approach); demos show working software, not slides.

---

## 6. Definition of Ready (DoR) & Definition of Done (DoD)

### 6.1 DoR — a backlog item may enter a sprint when:
- [ ] User story in "As a / I want / so that" or job story form, with clear user value and linked goal/metric
- [ ] Acceptance criteria written (Given/When/Then), incl. negative/edge cases
- [ ] Designs attached (all states: empty, loading, error, success; mobile + desktop where relevant) and copy final or placeholder agreed
- [ ] API contract / data changes identified; dependencies (other teams, client data, third-party credentials such as payment sandbox keys) available
- [ ] NFRs noted (performance, security, privacy/PII, accessibility, analytics events)
- [ ] Estimated by the team and small enough to finish within one sprint (split if > ~3 days)
- [ ] Testability confirmed by QA; test data known
- [ ] For AI features: expected behaviours, refusal cases and eval examples defined
- [ ] PO has prioritised it; no open questions blocking start
(DoR is a guide, not a gate that prevents learning — Scrum Guide itself does not mandate DoR.)

### 6.2 DoD — an increment is Done when (Scrum Guide: DoD is a formal description of the quality required; if not met, it cannot be released or presented at Sprint Review):
**Code**
- [ ] Meets all acceptance criteria; PO accepted
- [ ] Code reviewed and approved (≥1 reviewer; 2 for security-sensitive or payment code)
- [ ] Follows coding standards; linters/formatters pass; no new critical static-analysis/secret-scan findings
- [ ] Unit + integration tests written; critical paths covered; CI green
**Quality**
- [ ] QA tested on target browsers/devices (incl. low-end Android if mobile-first audience)
- [ ] No open Critical/High bugs on the story; regressions pass
- [ ] Accessibility basics checked (contrast, labels, keyboard)
- [ ] Performance within budget (e.g., API p95 < agreed ms; LCP < 2.5s)
**Ops & data**
- [ ] DB migrations reversible / backward compatible; feature flag where risky
- [ ] Logging, metrics, alerts added for new critical flows; analytics events firing per tracking plan
- [ ] Deployed to staging (and prod, if continuous delivery)
**Docs & compliance**
- [ ] API docs/README/runbook/release notes updated
- [ ] PII handling reviewed (consent, retention, masking)
- [ ] For AI features: eval suite passes threshold; guardrail tests pass; cost per call within budget

### 6.3 Release-level DoD ("Done-Done" for client delivery)
UAT signed · security checklist passed · backups & restore tested · monitoring/on-call in place · user manual & admin guide delivered · source code, credentials, and infrastructure ownership transferred per contract · BAST signed · warranty period start date recorded.

---

## 7. Quality gates (stage-gate checkpoints)

Each gate: **owner (A)**, **evidence required**, **pass rule**. Don't proceed (or don't invoice the next *termin*) until passed or explicitly waived in writing by the A.

| Gate | When | A | Evidence | Pass rule |
|---|---|---|---|---|
| G0 Problem/Opportunity | End P0 | Sponsor / PM | Opportunity brief, research summary, rough ROI, top risks | Clear problem, target user, success metric; budget range agreed |
| G1 Scope & Commercials | End P1 | Sponsor (client) + PjM | PRD/SRS, estimate, timeline, SOW, RACI, payment terms, assumptions & exclusions | Signed SOW; acceptance criteria and change-request process defined |
| G2 Design & Architecture | End P2 | TL (tech) + PM (UX) | Approved prototype, usability test (≥5 users for key flow), architecture doc + ADRs, threat model, test strategy, environment plan, cost model | No unresolved high risks; NFRs mapped to design; client signed design approval |
| G3 Per-increment (CI) | Every merge | TL | CI: build, lint, tests, SAST/SCA, secret scan, coverage threshold | All green; no critical findings |
| G4 Feature complete / code freeze | End P3 | TL + PM | All in-scope stories meet DoD; known-issues list | Scope complete or deferral approved via CR |
| G5 Release readiness | End P4 | QA (quality) + SEC + Sponsor (UAT) | Test report (pass %, open defects by severity), perf/load test, security scan/pen-test, UAT sign-off, AI eval report | 0 Critical, 0 High open (or waived in writing); SLO-capable monitoring live |
| G6 Go-live | P5 | Sponsor + TL | Go-live checklist, rollback plan tested, runbook, on-call roster, comms plan, legal docs live | All checklist items done; go/no-go meeting recorded |
| G7 Hypercare exit | P5 + 2–4 weeks | PjM + Sponsor | Incident log, SLO report, support volume trend | Stable for agreed period → BAST/warranty start, handover to support |
| G8 Periodic health | P6 monthly/quarterly | TL / PM | DORA metrics, SLO/error budget, security patch status, cost, product metrics | Error budget not exhausted (else freeze features); patches within SLA |

**Defect severity (use in contracts):** Critical = system down/data loss/security breach/payments broken, no workaround · High = major function broken, workaround painful · Medium = function impaired, workaround exists · Low = cosmetic. Typical warranty SLAs: response Critical ≤ 4h, High ≤ 1 business day (set your own; price support separately).

---

## 8. Handoff checklists (where projects actually break)

- **PM → Design:** problem statement, target users, success metric, constraints (budget, timeline, tech, brand), must-have vs nice-to-have.
- **Design → Engineering:** Figma link with final frames, component mapping to design system, all states, responsive rules, motion specs, assets exported, copy final, open questions list; 30-min walkthrough meeting.
- **Architecture → Dev/OPS:** C4 diagrams, ADRs, API contracts (OpenAPI), data model, env variables list, NFR budget.
- **Dev → QA:** build on staging, feature flags state, test accounts/data, known limitations, what changed (PR links).
- **QA → PM/Client (UAT):** test summary, open defects, UAT scripts in client language, UAT environment & accounts.
- **Engineering → Support/Ops:** runbook, dashboards, alert meanings, escalation matrix, FAQ for known issues, admin manual.
- **Agency → Client (BAST package):** source code repo transfer, infra & domain credentials (via password manager, never chat), documentation, training recording, warranty terms, signed BAST.

---

## 9. AI agent as a team member — operating rules

1. **Assign the agent a role card**, not "help": e.g., "QA assistant: generate test cases from AC in Jira tickets labelled `ready-for-qa`, output to TestRail format."
2. **Human stays A** for anything touching money, security, legal, production data, client commitments.
3. **Agent-friendly artefacts:** keep PRDs, ADRs, DoR/DoD, runbooks as Markdown in repo — agents read them as context.
4. **High-leverage uses by phase:** P0 research synthesis & competitor scans · P1 PRD/story/AC drafts, estimates cross-check, SOW drafts · P2 design variants, ADR/C4 drafts, threat model drafts · P3 code, tests, reviews · P4 test generation, log triage · P5 release notes, docs, training material, translations · P6 incident summaries, analytics narration, support deflection.
5. **Verification rule:** every agent output that becomes a commitment (estimate, legal clause, price, security claim) needs a named human reviewer recorded in the RACI.

---

## 10. Quick decision rules

- Team < 6 and one product → combine PM+PjM (internal) or PjM+SM (client); TL = EM; no dedicated Architect, DBA, SRE — use managed services.
- Handling payments or personal data (KTP/NIK, phone, location) → security review and privacy/legal review are mandatory gates, regardless of team size.
- AI is the core value proposition → dedicated AI/LLM engineer + eval set before building UI.
- Client demands fixed price → BA + PjM time up-front (P1) is non-negotiable; write assumptions/exclusions and the CR process into the SOW.
- More than ~8 engineers on one backlog → split into stream-aligned teams by user journey/domain, keep one PO/Product Goal per product.
- On-call pages frequently or error budget exhausted → freeze features, fix reliability (SRE practice).

---

## Sources

Star counts read from GitHub repository pages on 2026-11-08 (API rate-limited; counts taken from page `stargazerCount`).

**GitHub repositories**
- jorgef/engineeringladders — ★8,555 — https://github.com/jorgef/engineeringladders (Developer/TL/TPM/EM ladders, 5 axes, TL vs EM table)
- charlax/engineering-management — ★8,396 — https://github.com/charlax/engineering-management
- kdeldycke/awesome-engineering-team-management — ★2,632 — https://github.com/kdeldycke/awesome-engineering-team-management
- dend/awesome-product-management — ★2,452 — https://github.com/dend/awesome-product-management
- bmoeskau/engineering-ladders — ★610 — https://github.com/bmoeskau/engineering-ladders (index of 35+ public ladders incl. Dropbox, GitLab, CircleCI, Rent the Runway)
- sdras/career-ladders — ★828 — https://github.com/sdras/career-ladders
- basecamp/handbook — ★6,664 — https://github.com/basecamp/handbook/blob/master/titles-for-programmers.md (L1–L5 IC expectations, tech-lead duties)
- ttt30ga/awesome-product-design — ★2,759 — https://github.com/ttt30ga/awesome-product-design
- goabstract/Awesome-Design-Tools — ★41,812 — https://github.com/goabstract/Awesome-Design-Tools
- dastergon/awesome-sre — ★13,761 — https://github.com/dastergon/awesome-sre
- wmariuss/awesome-devops — ★4,448 — https://github.com/wmariuss/awesome-devops
- google/eng-practices (code review guide) — ★23,274 — https://github.com/google/eng-practices
- joelparkerhenderson/architecture-decision-record — ★17,425 — https://github.com/joelparkerhenderson/architecture-decision-record
- kamranahmedse/developer-roadmap (role roadmaps) — ★371,550 — https://github.com/kamranahmedse/developer-roadmap
- fityanos/awesome-quality-assurance-roadmap — ★2,210 — https://github.com/fityanos/awesome-quality-assurance-roadmap
- sbilly/awesome-security — ★15,079 — https://github.com/sbilly/awesome-security
- OWASP/ASVS — ★3,769 — https://github.com/OWASP/ASVS
- igorbarinov/awesome-data-engineering — ★9,243 — https://github.com/igorbarinov/awesome-data-engineering
- EthicalML/awesome-production-machine-learning — ★21,081 — https://github.com/EthicalML/awesome-production-machine-learning
- tensorchord/Awesome-LLMOps — ★5,971 — https://github.com/tensorchord/Awesome-LLMOps
- PagerDuty/incident-response-docs — ★1,052 — https://github.com/PagerDuty/incident-response-docs

**Handbooks, frameworks, books**
- The 2020 Scrum Guide (Schwaber & Sutherland) — https://scrumguides.org/scrum-guide.html (accountabilities, team ≤10, timeboxes, DoD)
- Dropbox Engineering Career Framework — https://dropbox.github.io/dbx-career-framework/ (IC1–IC7 SWE/SRE; QE, SDET, MLE, DE, Security, TPM, EM ladders)
- GitLab Engineering Career Framework — https://handbook.gitlab.com/handbook/engineering/careers/matrix/
- Rent the Runway engineering ladder (Camille Fournier, 2015) — https://dresscode.renttherunway.com/blog/ladder
- CircleCI career paths — https://circleci.com/blog/why-we-re-designed-our-engineering-career-paths-at-circleci/
- Google SRE Book, ch. 5 "Eliminating Toil" (≤50% toil) and Appendix E Launch Checklist — https://sre.google/sre-book/eliminating-toil/
- Team Topologies (Skelton & Pais) — team types (stream-aligned, platform, enabling, complicated-subsystem)
- DORA four key metrics — https://dora.dev
- Indonesia: UU No. 27 Tahun 2022 (Pelindungan Data Pribadi); PP 71/2019 (PSTE) — verify current implementing rules with counsel.

**Talks (YouTube)**
- Marty Cagan, "EMPOWERED" keynote — https://youtu.be/bsA8Gw_1KAg (four risks; feature teams vs empowered teams; managers' staffing/coaching duty)
- Marty Cagan interview on three PM models (product owner / feature team / empowered) — https://youtu.be/QxbbXl5NfFw
- Camille Fournier on Lenny's Podcast, "The things engineers are desperate for PMs to understand" — https://youtube.com/watch?v=hZSh0rs20uI
- Lenny's Newsletter, "Product management theater" (Cagan) — https://lennysnewsletter.com/p/product-management-theater-marty
