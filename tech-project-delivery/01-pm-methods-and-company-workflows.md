# 01 — Project & Product Management Methods + How Tech Companies Actually Work

> Agent-facing reference. Use it to pick a delivery method, run ceremonies, write artifacts, estimate, manage risk/stakeholders, and run a gated end-to-end lifecycle for products (Lumii, TukaKu) and client systems (Indonesian clients: BAST, termin, PPN, masa garansi).
> Rule of thumb: **Method follows uncertainty.** High uncertainty in *what* to build → discovery/Lean/Shape Up. Known scope + fixed contract → phased/gated (PMBOK-style) with agile build inside. Continuous ops/support flow → Kanban.

---

## 0. Quick decision table — which method when

| Situation | Use | Why |
|---|---|---|
| New product, unknown demand (Lumii new feature, TukaKu MVP) | Lean Startup + dual-track agile (discovery + delivery), Shape Up cycles | Cheapest learning per Rupiah; fixed time, variable scope |
| Small product team (2–8), founder-led | Shape Up (6+2 weeks) or Linear-style 2-week cycles | Low ceremony, protects maker time |
| Client project, fixed price, fixed deadline | Hybrid: gated phases (discovery → UAT → BAST) + 1–2-week sprints inside build | Contract needs gates/sign-off; build needs feedback |
| Client project, time & materials / retainer | Scrum or Kanban with monthly review & invoice | Scope evolves; bill by capacity |
| Support / maintenance / ops tickets | Kanban with WIP limits + SLAs | Work arrives randomly; flow beats sprints |
| Many teams, one product (later stage) | Squads/teams with OKRs + quarterly planning (don't copy "Spotify model" literally) | Alignment with autonomy |
| Big decision, many stakeholders | Amazon PR-FAQ / narrative memo, Google-style design doc | Writing forces clarity; async review |

---

## 1. PMBOK 7 (PMI, 2021) — summary

PMBOK 7 moved from process groups/knowledge areas (PMBOK 6) to **principles + performance domains** and is method-agnostic (predictive, adaptive, hybrid). (PMI has since published an 8th edition; treat the 7th's principles/domains as the stable core.)

**12 principles (Standard for Project Management):**
1. Be a diligent, respectful, caring **steward**
2. Create a collaborative **team** environment
3. Effectively engage with **stakeholders**
4. Focus on **value**
5. Recognize, evaluate, respond to **system interactions** (systems thinking)
6. Demonstrate **leadership** behaviors
7. **Tailor** based on context
8. Build **quality** into processes and deliverables
9. Navigate **complexity**
10. Optimize **risk** responses
11. Embrace **adaptability and resiliency**
12. Enable **change** to achieve the envisioned future state

**8 performance domains:** Stakeholders · Team · Development approach & life cycle · Planning · Project work · Delivery · Measurement · Uncertainty.

**Practical use:** For a client project, run a 10-minute "domain check" at each gate: Who's affected and engaged? Is the team clear on roles? Is the approach (predictive/agile/hybrid) right? Is the plan current? Is work flowing? Are we delivering accepted value? Which metrics show it? What are the top risks/assumptions?

---

## 2. Scrum Guide 2020 (Schwaber & Sutherland) — exact essentials

- **Pillars:** transparency, inspection, adaptation. **Values:** commitment, focus, openness, respect, courage.
- **Scrum Team** (typically ≤10 people), no sub-teams/hierarchy; 3 **accountabilities**: **Product Owner** (maximizes value, owns Product Backlog), **Scrum Master** (effectiveness of team, coaches Scrum), **Developers** (create the Increment; own Sprint Backlog). 2020 removed "Development Team" as a separate team and added "self-managing".
- **Events (timeboxes for a 1-month Sprint; shorter Sprints → proportionally shorter):**
  | Event | Timebox | Output |
  |---|---|---|
  | Sprint | ≤1 month, fixed length | ≥1 usable Increment |
  | Sprint Planning | ≤8h | Sprint Goal (Why), selected items (What), plan (How) |
  | Daily Scrum | 15 min | Adapted plan toward Sprint Goal (not a status meeting) |
  | Sprint Review | ≤4h | Inspect outcome with stakeholders, adapt Product Backlog |
  | Sprint Retrospective | ≤3h | Improvements (can go into next Sprint Backlog) |
- **Artifacts + commitments:** Product Backlog → **Product Goal**; Sprint Backlog → **Sprint Goal**; Increment → **Definition of Done**.
- Backlog refinement is an ongoing activity (not an event); common guidance ≤10% of capacity.

**Definition of Done template (adapt):** code reviewed · automated tests pass (unit + key integration) · acceptance criteria met · no new critical/high bugs · deployed to staging · docs/changelog updated · analytics events added · feature flag/rollback ready · PO accepted.

**Definition of Ready (optional, don't weaponize):** clear problem + acceptance criteria · designs attached if UI · dependencies known · small enough to finish in ≤ half a sprint.

---

## 3. Kanban

Core practices (Kanban Method): **visualize work**, **limit WIP**, **manage flow**, **make policies explicit**, **implement feedback loops**, **improve collaboratively/evolve experimentally**. Start with what you do now; evolve.

- Board: `Backlog → Ready → In Progress (WIP 3) → Review (WIP 2) → QA → Done`. Add swimlanes: Expedite (max 1), Fixed-date, Standard, Intangible (tech debt).
- **Little's Law:** avg cycle time = avg WIP ÷ avg throughput. Halve WIP → roughly halve cycle time.
- Metrics: cycle time (start→done), lead time (request→done), throughput (items/week), WIP age, cumulative flow diagram (CFD; widening bands = bottleneck).
- SLA forecast: "85% of items finish within N days" (from cycle-time scatterplot percentile). Use this instead of estimates for support work.
- Cadences: daily standup at the board (walk right-to-left, "what's blocked/aging?"), weekly replenishment, monthly service delivery review.

---

## 4. Shape Up (Basecamp, Ryan Singer — free at basecamp.com/shapeup)

- **Six-week cycles + two-week cool-down** (bugs, exploration, cleanup). Small-batch projects 1–2 weeks; big-batch = full cycle.
- **Shaping** (senior people, before the cycle): set the **appetite** (how much time it's *worth*, not an estimate) → rough solution via **breadboards** (places, affordances, connections) and **fat-marker sketches** → find **rabbit holes** → declare **no-gos** → write a **pitch**.
- **Pitch template:** Problem · Appetite · Solution (sketches) · Rabbit holes · No-gos.
- **Betting table:** leadership bets on pitches for the next cycle; **no backlog** (unbet pitches aren't kept in a growing queue; good ideas come back).
- **Circuit breaker:** if a project isn't done at the end of the cycle, it does *not* automatically get extended (by default it's cancelled/reshaped). Forces scope hammering.
- Team gets the whole project, not tasks; they discover tasks, organize into **scopes**, and report progress on **hill charts** (uphill = figuring out, downhill = executing).
- Lesson: "Fixed time, variable scope." Great for founder-led product teams; poor fit for client contracts with fixed itemized scope unless you sell it as "appetite-based phases."

---

## 5. Lean / Lean Startup / Dual-track agile

- **Lean (Toyota → software, Poppendieck):** eliminate waste (partially done work, extra features, relearning, handoffs, delays, task switching, defects), build quality in, defer commitment, deliver fast, optimize the whole.
- **Lean Startup (Eric Ries):** Build–Measure–Learn; **MVP** = smallest thing that tests the riskiest assumption; **validated learning**; **innovation accounting**; **pivot or persevere** decision at fixed intervals.
- **Riskiest-assumption order (Cagan's 4 risks):** value (will they buy/use?), usability (can they figure it out?), feasibility (can we build it?), business viability (does it work for legal, sales, finance?).
- **Dual-track agile (Cagan, Patton):** discovery track (PM+designer+tech lead: interviews, prototypes, tests) runs 1–2 cycles ahead of the delivery track (engineers ship validated items). Not two teams—one team, two kinds of work.
- **Discovery techniques:** customer interviews (Mom Test style: past behavior, not opinions), opportunity-solution tree (Teresa Torres), story mapping (Jeff Patton: backbone of user activities → walking skeleton → release slices), fake-door test, concierge/Wizard-of-Oz MVP, clickable prototype test with 5 users.
- **Experiment card:** We believe [segment] has [problem]. If we [change], then [metric] will move from X to Y within [time]. We'll know we're wrong if [kill criterion].

**Indonesian context example (TukaKu):** Before building payments, run a WhatsApp concierge MVP for 2 weeks with 20 users; kill criterion: <30% repeat usage in week 2.

---

## 6. Linear Method (linear.app/method)

Principles: build for the creators; purpose-built; **create momentum — don't sprint**; meaningful direction; aim for clarity (don't invent terms); say no to busy work; simple first, then powerful; **decide and move on**.
Practices: set strategic initiatives (leave room for unplanned work) → connect daily work via **projects** → work in **n-week cycles** (2 weeks most common) → **write issues, not user stories** (short, concrete task descriptions; user stories seen as an anti-pattern) → scope projects down → build with users/feedback → write project updates → measure progress in completed scope, not effort.
**Use it when:** small product teams that want low ceremony and fast shipping (good default for Lumii).

---

## 7. OKRs (Grove → Doerr → Google)

- **Objective** = qualitative, inspiring, time-bound. **Key Results** = 2–5 measurable outcomes (not tasks) per objective.
- Google's guide: **committed** OKRs (must hit 1.0) vs **aspirational** OKRs (expected avg ~0.7); graded 0.0–1.0; 0.6–0.7 on aspirational is healthy; consistently 1.0 = sandbagging.
- Cadence: annual objectives, quarterly KRs; weekly confidence check (red/yellow/green); end-of-quarter grade + retro.
- Anti-patterns: KRs that are outputs ("launch feature X"), 10 objectives, tying OKRs to bonuses (kills ambition), cascading top-down only (good orgs mix ~50% bottom-up).
- **Example (Lumii, Q1):** O: Make Lumii indispensable for small Indonesian shops. KR1: weekly active merchants 120 → 400. KR2: % merchants using AI invoice reply ≥3×/week 15% → 40%. KR3: churn month-2 from 35% → 20%.
- Initiatives (projects/pitches) sit *under* KRs; that's where Shape Up/Scrum work attaches.

---

## 8. How top tech companies actually work (public sources)

### Amazon — Working Backwards, PR/FAQ, 6-pager
- **PR/FAQ:** write the launch press release *before* building: headline, sub-head, date/city, problem, solution, leader quote, how it works, customer quote, call to action. Then **External FAQ** (customer questions, plain language) and **Internal FAQ** (stakeholder questions: cost, P&L, risks, dependencies, why now, what must be true). Commonly: PR ≤1 page, FAQ up to ~5 pages.
- **Narrative memo ("6-pager"):** no slides; meeting starts with silent reading (~20 min in a 60-min meeting), then discussion; authors take notes. Forces complete thinking.
- Also: single-threaded leaders (one person 100% owning an initiative), input metrics over output metrics, Weekly Business Review (WBR), Correction of Errors (COE) post-mortems.
- **Use:** before committing ≥1 cycle to a big feature or before a client proposal, write a 1-page PR + FAQ.

### Google — design docs, OKRs, code review
- Design doc sections (Malte Ubl, "Design Docs at Google"): **Context & scope · Goals & non-goals · The actual design (overview → details, focus on trade-offs) · System-context diagram · APIs · Data storage · Code/pseudo-code (sparingly) · Degree of constraint · Alternatives considered · Cross-cutting concerns (security, privacy, observability)**. Typical 10–20 pages for big projects; "mini design docs" 1–3 pages for incremental work. Skip a design doc when the solution is obvious and has no real trade-offs.
- Lifecycle: create & iterate → review (small group or formal) → implement & update → maintain/learn.
- Code review standard (google/eng-practices): approve once a CL *improves overall code health*, even if not perfect; small CLs; reply within a business day.

### GitLab — public handbook, product development flow, async
- **Product Development Flow** = **Validation track** (validation backlog → problem validation → ready for design → design → solution validation) + **Build track** (plan → develop & test → launch → improve). Issue description is the **single source of truth**. Release stages: experiment → beta → generally available, with exit criteria.
- **Handbook-first / async:** decisions documented in the handbook/issues before or instead of meetings; meetings have agendas in a doc, are recorded, and notes are the deliverable. "Minimal viable change" (MVC): ship the smallest valuable change, iterate.
- Values (CREDIT): Collaboration, Results, Efficiency, Diversity/inclusion/belonging, Iteration, Transparency.

### Atlassian Team Playbook (free, ~95 "plays")
Most-used plays: **Retrospective, OKRs, Roles & responsibilities, Health Monitor, DACI (Driver, Approver, Contributors, Informed) decision-making, User manual, Working agreements**, project kickoff, premortem, stakeholder communications, project poster, 5 whys, sparring. Use as ready-made workshop scripts for client kickoffs.

### Spotify "model" — and its critique
- 2012 whitepaper + Henrik Kniberg's 2014 videos: **Squads** (autonomous cross-functional team, ~like Scrum team), **Tribes** (collection of squads in a related area), **Chapters** (same-skill people across squads, line management), **Guilds** (voluntary communities of interest). Culture: "loosely coupled, tightly aligned", autonomy, failure-friendly, limited blast radius.
- **Critique:** Jeremiah Lee ("Spotify's Failed #SquadGoals", 2020) — the model was aspirational and never fully implemented; matrix management left chapter leads managing people without product responsibility; autonomy without coordination mechanisms; Kniberg himself warned not to copy it ("part ambition, part approximation").
- **Lesson:** copy the *principles* (autonomy + alignment, small teams, clear missions), not the *names*. Solve coordination explicitly (OKRs, shared roadmap, architecture ownership).

### Stripe / Shopify / Meta (public descriptions; verify before quoting)
- **Stripe:** strong writing culture (long-form docs, emails shared widely), API design reviews, high bar for craft/docs; "operating principles" published publicly.
- **Shopify:** GSD ("Get Shit Done") internal project system with phases (think → explore/prototype → build → release) and regular project updates; in 2023 publicly cancelled recurring meetings with 3+ people to protect maker time.
- **Meta:** small-diff culture, internal code review (Phabricator lineage), continuous deployment with feature flags/gatekeepers and staged rollouts, heavy A/B testing; engineering "bootcamp" onboarding.
- **Basecamp:** Shape Up + public employee handbook (github.com/basecamp/handbook); calm-company, async-first communication.

---

## 9. Ceremonies & communication cadence (default operating rhythm)

| Cadence | Ceremony | Who | Output |
|---|---|---|---|
| Daily (15m) or async in Slack/WA | Standup: progress vs goal, blockers | Team | Unblocked work |
| Weekly (30m) | Client/stakeholder sync | PM, client PIC, tech lead | Decisions, RAID updates |
| Weekly (written) | Status report (template §12) | PM → stakeholders | Single source of truth |
| Every 1–2 weeks | Planning / replenishment | Team + PO | Cycle goal + committed items |
| Every 1–2 weeks | Demo / review | Team + stakeholders | Feedback, accepted items |
| Every 1–2 weeks | Retrospective | Team only | 1–3 improvement actions with owners |
| Ongoing (≤10%) | Backlog refinement | PO + tech lead + designer | Ready items |
| Monthly | Steering committee / business review | Sponsor, PM, leads | Budget, scope, risk decisions |
| Quarterly | OKR planning & grading, roadmap review | Leadership + leads | Next quarter bets |
| Per incident | Post-mortem (blameless) | Responders | Root cause + action items |

**Communication plan matrix:** for each stakeholder → info needed · format · frequency · channel (email / WhatsApp group / Notion / meeting) · owner. Indonesian clients often expect a WhatsApp group; still send a weekly written report by email/Notion so decisions are auditable.

**Meeting hygiene:** agenda in doc 24h before; decision owner named (DACI/RAPID); notes + action items (owner, due date) posted within 2h; cancel if no agenda.

---

## 10. Metrics

**Delivery (team-level, use for self-improvement, never to compare teams):**
- **Velocity:** story points completed per sprint; planning aid only; unstable for first 3 sprints; never a productivity KPI.
- **Burn-down** (remaining work vs time in sprint) / **burn-up** (completed vs total scope — better, because scope changes are visible).
- **Cycle time / lead time / throughput / WIP / flow efficiency** (active time ÷ total time; typical teams 15–40%).
- **Sprint goal success rate**, **predictability** (planned vs done, healthy 80–100%).

**DORA (DevOps Research & Assessment, Google Cloud):**
| Metric | Elite (2024 report clusters) |
|---|---|
| Deployment frequency | On demand (multiple/day) |
| Change lead time (commit → prod) | < 1 day |
| Change failure rate | ~5% |
| Failed deployment recovery time | < 1 hour |
(Low cluster: lead time 1–6 months, deploy monthly–biannually, ~40% failure, recovery 1 week–1 month. 2024 report: elite ≈ 19% of respondents. DORA also tracks *rework rate*.) Tools: middlewarehq/middleware (open-source DORA platform), dora-metrics/pelorus.

**Product/outcome:** activation rate, retention (D1/D7/D30 or month-N cohort), WAU/MAU, NPS/CSAT, task success, revenue/MRR, churn, support tickets per active user. Pick one **North Star metric** + 3–5 input metrics (Amazon-style controllable inputs).

**Project (client):** schedule variance, budget burn vs % complete (simple EVM: CPI = EV/AC, SPI = EV/PV; <0.9 = red), open defects by severity, change requests count/value, UAT pass rate, client satisfaction per milestone.

---

## 11. Estimation

| Technique | How | Use when |
|---|---|---|
| **Story points** (Fibonacci 1,2,3,5,8,13) | Relative size = effort+complexity+risk; Planning Poker | Stable Scrum team; sprint planning |
| **T-shirt sizes** (XS–XL) | Quick bucket; map to ranges (S ≤ 3 days, M ≤ 2 wks, L ≤ 6 wks, XL = split it) | Roadmap, early proposals |
| **PERT (three-point)** | E = (O + 4M + P) / 6; σ = (P − O)/6 | Client quotes, fixed price; sum E per task, add buffer from √Σσ² |
| **Ideal days / hours** | Direct effort estimate | Small agencies billing by man-day |
| **Appetite** (Shape Up) | Decide time budget first, shape scope to fit | Product work; fixed-budget client phases |
| **#NoEstimates / throughput forecasting** | Slice items to similar small size; count items; forecast with historical throughput (Monte Carlo) | Mature teams with steady flow |
| **Wideband Delphi** | Anonymous rounds of expert estimates until convergence | Big unknowns, multiple experts |

**PERT worked example (client login + OTP module):** O = 3 days, M = 5, P = 11 → E = (3 + 20 + 11)/6 = 5.67 days; σ = 1.33. For 10 such tasks with similar σ: total E ≈ 56.7 days, σ_total ≈ √(10×1.78) ≈ 4.2 → quote at ~P85 ≈ E + 1σ ≈ 61 days, plus 10–20% PM/QA overhead if not already in tasks.

**Rules:** estimate by the people doing the work; give ranges, not points ("4–6 weeks, 80% confidence"); re-estimate at each gate (cone of uncertainty: early estimates can be off by 4× either way); split anything >13 points / >5 days; separate estimate (truth) from commitment (business decision) from target (wish).

---

## 12. Artifacts & templates (copy-paste)

### 12.1 One-page project charter / brief
```
Project: ____  Sponsor: ____  PM: ____  Date: ____
Problem / opportunity (1–3 sentences, evidence):
Goals (measurable) & non-goals:
Success metrics (baseline → target, by when):
Scope in / out:
Key deliverables & milestones (with gate dates):
Budget & resources (Rp, people, tools):
Assumptions & constraints:
Top 5 risks (see RAID):
Stakeholders & decision rights (DACI/RACI):
Approval: ____ (sign + date)
```

### 12.2 RAID log (Risks, Assumptions, Issues, Dependencies)
| ID | Type | Description | Prob (1–5) | Impact (1–5) | Score | Owner | Response (avoid/mitigate/transfer/accept) | Trigger | Due | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| R1 | Risk | Payment gateway (Midtrans/Xendit) approval delays | 3 | 4 | 12 | PM | Submit KYB docs in week 1; sandbox-first | No approval by wk 4 | wk 1 | Open |
| A1 | Assumption | Client supplies product data in Excel by wk 2 | – | – | – | Client PIC | Confirm in kickoff; template provided | – | wk 2 | Open |
| I1 | Issue | Staging server down | – | 3 | – | Tech lead | Restore; add monitoring | – | today | Open |
| D1 | Dependency | WhatsApp Business API approval | – | 4 | – | PM | Apply early; fallback SMS OTP | – | wk 3 | Open |
Rules: score ≥12 = red, reviewed weekly in sync; every risk has one owner and a trigger; run a **premortem** at kickoff ("It's 3 months later and the project failed—why?").

### 12.3 Stakeholder management
- **Power/interest grid:** High power + high interest → manage closely (sponsor, owner); high power + low interest → keep satisfied (finance, director); low power + high interest → keep informed (end users, admin staff); low/low → monitor.
- **RACI** per deliverable (exactly one A). **DACI** per decision.
- Stakeholder register: name · role · interest · influence · current vs desired attitude (resistant/neutral/supportive/leading) · engagement strategy · owner.
- Indonesian context: identify the real decision maker (often owner/"Bapak/Ibu pimpinan") vs day-to-day PIC; get decisions confirmed in writing (email/notulen rapat) even if agreed verbally or by WhatsApp.

### 12.4 Weekly status report (≤1 page)
```
Project ____ | Week of ____ | Overall: 🟢/🟡/🔴 (Scope 🟢 Schedule 🟡 Budget 🟢 Quality 🟢)
Summary (3 lines): what changed, what's at risk, what we need from you.
Done this week: • ... 
Next week: • ...
Milestones: [Design sign-off ✅ 12 Mar] [UAT start ⏳ 2 Apr, forecast 5 Apr]
Top risks/issues (from RAID): R1 ... (owner, action, date)
Decisions needed (by whom, by when): 1) Approve CR-03 (+Rp 8.5jt, +4 days) — Pak Budi, by Fri
Metrics: burn-up X/Y items, budget used 46% vs 50% complete, open bugs P1:0 P2:3
```
Color rules: 🟢 on track; 🟡 at risk but recoverable within plan; 🔴 needs sponsor decision. Never let something go 🟢 → 🔴 without a 🟡 week.

### 12.5 Change control (Change Request / CR)
1. Anyone submits CR: description, reason, requester.
2. PM + tech lead assess impact: effort, cost (Rp), schedule, risk, affected deliverables (within 2–3 business days).
3. Decision by authority defined in contract (e.g., client sponsor; CRs < Rp X may be approved by PM). Options: approve / reject / defer to phase 2 / swap (trade scope of equal size).
4. Update scope baseline, plan, RAID, invoice/addendum (adendum kontrak if large).
5. Log in CR register: ID · date · description · impact (days, Rp) · decision · approver · date.
Rule: **no verbal scope changes**; "small" requests go to the register too (they add up). In agile contracts, allow free swaps of equal-sized unstarted items.

### 12.6 Decision record (ADR-lite)
`Title · Status (proposed/accepted/superseded) · Context · Decision · Consequences · Alternatives`. See joelparkerhenderson/architecture-decision-record for templates.

### 12.7 Retrospective formats
Start/Stop/Continue · 4Ls (Liked, Learned, Lacked, Longed for) · Sailboat (wind, anchors, rocks, island). Always end with ≤3 actions, each with owner + date; review last retro's actions first.

---

## 13. The end-to-end lifecycle with gates (client system or internal product)

Owners: **PM** (project/delivery manager), **PO/Product Manager**, **TL** (tech lead/architect), **UX** (designer), **QA**, **DevOps**, **Client Sponsor** (decision maker), **Client PIC** (day-to-day), **Support**.

| # | Phase | Key activities | Deliverables | Gate criteria (exit) | Accountable / sign-off |
|---|---|---|---|---|---|
| 0 | **Pre-sales / Initiation** | Qualify lead, rough scope, ROM estimate (±50%), proposal | Proposal, ROM quote, SOW draft | Signed contract/SPK, DP (down payment) received, sponsor named | Sales/PM; Client Sponsor signs |
| 1 | **Discovery** | Stakeholder interviews, current-process mapping (as-is/to-be), user research, competitive scan, tech constraints, risks | Discovery report, personas/jobs, story map, prioritized feature list (MoSCoW), RAID v1, refined estimate (±25%) | Problem + success metrics agreed; MVP scope (Must haves) agreed; top risks have owners | PO/PM; Client Sponsor approves |
| 2 | **Requirements** | User stories / issues with acceptance criteria (Given-When-Then), NFRs (performance, security, availability, data/PDP law compliance), integrations list, data migration needs | PRD/SRS, acceptance criteria, NFR list, traceability matrix (req → test), scope baseline | Requirements reviewed & signed; Must-haves testable; open questions ≤ agreed limit | PO; Client PIC reviews, Sponsor signs |
| 3 | **Design** (UX + technical) | Wireframes → hi-fi prototype, usability test (5 users), architecture/design doc, data model, API contracts, ADRs, infra & cost plan, security review, test strategy | Figma prototype, design doc, ERD, API spec (OpenAPI), test plan, release plan | Prototype approved by client; design doc reviewed by TL/peer; estimates within ±10–15% or CR raised | UX + TL; Client signs UI approval |
| 4 | **Build** | Sprints/cycles; CI/CD, code review, unit/integration tests, feature flags, demo every 1–2 weeks | Working increments on staging, sprint reports, updated docs | All Must-have stories meet DoD; code freeze; no P1/P2 open; staging deploy reproducible | TL (quality), PM (schedule) |
| 5 | **QA / System test** | Functional, regression, integration, performance/load, security (OWASP top 10, pen test if needed), cross-device, data migration dry run | Test report, bug list by severity, performance results | 100% critical test cases executed; ≥95% pass; 0 P1, 0 P2 (or accepted workaround); perf meets NFR | QA lead; TL |
| 6 | **UAT** (User Acceptance Test) | Client users test real scenarios on UAT env with realistic data; training for key users | UAT scripts, UAT results, signed acceptance — Indonesia: **BAST (Berita Acara Serah Terima)** / Berita Acara UAT | All UAT scenarios passed or deferred with sign-off; client signs BAST/UAT acceptance (triggers termin payment) | Client Sponsor/PIC sign; PM facilitates |
| 7 | **Launch / Go-live** | Go/no-go meeting, release checklist, data migration, DNS/app-store release, staged rollout (internal → 10% → 100%), monitoring, comms | Release notes, runbook, rollback plan, go-live announcement | Go/no-go checklist all ✅ (backups, rollback tested, monitoring/alerts on, support roster, client comms sent) | PM runs; Sponsor + TL decide go/no-go |
| 8 | **Hypercare** (typically 2–4 weeks) | Elevated support, daily triage, fast hotfixes, usage monitoring, user coaching | Daily issue log, hypercare report, KPIs vs baseline | Incident volume back to normal for ≥1 week; no open P1/P2; handover docs complete; support team trained | PM + TL; Support accepts handover |
| 9 | **Maintenance / Operate** (masa garansi + SLA/retainer) | Bug fixes (warranty period, e.g., 3 months free for defects), SLA support, security patching, minor enhancements via CR, monthly report | SLA report, release log, roadmap for phase 2 | Contract renewal / phase-2 decision; periodic review (monthly/quarterly) | Support lead / account manager; Client |
| 10 | **Closure / Retrospective** | Lessons learned, final invoice, archive docs, case study/testimonial | Closure report, lessons learned | Final payment received; documentation & credentials handed over; retention-money (if any) released | PM; Sponsor |

**Go/No-Go checklist (launch):** ☐ UAT signed ☐ 0 open P1/P2 ☐ backups + restore tested ☐ rollback plan rehearsed ☐ monitoring/alerts/log dashboards live ☐ on-call roster + escalation contacts ☐ secrets rotated, prod credentials owned by client ☐ legal: privacy policy/T&C, UU PDP (Indonesia's Personal Data Protection Law) considerations ☐ app store/Play review approved ☐ support scripts/FAQ ☐ stakeholder comms scheduled ☐ launch window avoids peak business hours/holidays (e.g., Lebaran, Harbolnas for e-commerce).

**Bug severity (use in contract):** P1 Critical — system down/data loss/payments broken, response 1h, fix/workaround 4–24h · P2 High — major feature broken, no workaround, 1 business day · P3 Medium — workaround exists, next release · P4 Low — cosmetic, backlog.

**Payment-milestone mapping (common in Indonesian client projects; adapt):** DP 30–50% at contract → 20–30% at design sign-off → 20–30% at UAT/BAST → 10% after hypercare/warranty. Tie every invoice to a *gate artifact the client signs*.

**Internal product variant (Lumii/TukaKu):** collapse phases 1–3 into discovery track (opportunity → validated problem → prototype tested), 4–7 into delivery cycles with feature flags and staged rollout; "UAT" = beta cohort; gates = experiment metrics (e.g., activation ≥ X%) instead of signatures.

---

## 14. Roles quick map
- **Product Manager / PO:** why & what; outcomes, backlog priority, discovery. (Cagan: owns value + viability risk.)
- **Project/Delivery Manager:** when & how much; plan, RAID, budget, stakeholders, gates, status.
- **Scrum Master / Agile coach:** process health, impediments (often merged with PM in small teams).
- **Tech Lead / Architect:** how; design, quality, feasibility risk, code review standards.
- **Designer (UX/UI):** usability risk, research, prototypes.
- **QA:** test strategy, automation, release quality.
- **DevOps/SRE:** CI/CD, infra, monitoring, reliability, DORA metrics.
- **Client Sponsor vs PIC:** sponsor decides money/scope; PIC coordinates daily.
Small team (2–4) rule: founder = PM+PO, one senior dev = TL+DevOps, designer part-time, QA = peer-testing + client UAT. Still keep separate *hats* in gates (the person who built it shouldn't be the only one who tests it).

---

## 15. Anti-patterns to avoid
- Sprint as mini-waterfall (design → dev → test inside one sprint with handoffs) → swarm on fewer items.
- Velocity as KPI / comparing teams → point inflation.
- Roadmap with dates for everything → use Now/Next/Later; commit dates only for externally-bound items.
- Feature factory (output over outcome) → every initiative linked to a KR/metric.
- "Spotify model" cargo cult → design coordination explicitly.
- Status reports that are always green → define color rules and escalate early.
- Verbal scope changes from client WhatsApp → CR register.
- Launch Friday evening / before Lebaran → freeze windows.
- No hypercare budget in quote → include 2–4 weeks explicitly.

---

## 16. YouTube talks — key lessons

1. **Henrik Kniberg — "Spotify Engineering Culture" Part 1 & 2** (https://www.youtube.com/watch?v=Yvfz4HGtoPc, https://www.youtube.com/watch?v=0tpCmSnEoKo). Lessons: autonomy + alignment ("loosely coupled, tightly aligned"); small autonomous squads with a clear mission; limit blast radius so failure is cheap; culture matters more than structure. Pair with Jeremiah Lee's critique: it was aspirational.
2. **Ryan Singer — "Shaping in a Nutshell"** (https://www.youtube.com/watch?v=h_8M23wVjXk, 2022, ~73k views) and "Fixed Time, Variable Scope" (https://youtube.com/watch?v=K1jRu4v0SMI). Lessons: shape at the right altitude (not wireframes, not words); set appetite before solution; de-risk rabbit holes before betting; give teams whole projects.
3. **Marty Cagan — "EMPOWERED: Extraordinary Results with Ordinary People"** (https://youtu.be/bsA8Gw_1KAg). Lessons: empowered product teams get *problems to solve*, not features to build; leaders provide product strategy & context; feature teams/roadmaps of output are the failure mode; discovery tackles value, usability, feasibility, viability risks up front.
4. **Jeff Patton — "Why We Build the Wrong Things"** (https://www.youtube.com/watch?v=sg7xGxEjNCw) & "User Story Mapping" (https://www.youtube.com/watch?v=AorAgSrHjKM). Lessons: shared understanding beats shared documents; stories are for conversations; map the user journey and slice releases by outcome; minimize output, maximize outcome.
5. **Allen Holub — "Why You Should Get Rid of Estimates"** (https://www.youtube.com/watch?v=RrlarrIzbgQ). Lessons: estimates are often used as commitments and are low-value; slice work small, measure throughput, forecast from data; deliver value continuously so "when will it be done" matters less.
6. **Jeff Gothelf — "Outcomes Over Output"** (https://youtube.com/watch?v=nZz23vG59Zs). Lessons: define success as changes in customer behavior (outcomes); write KRs as behavior metrics; activity ≠ progress.

---

## 17. Top GitHub repos (stars verified via GitHub API, Nov 2026)

| Repo | Stars | Use |
|---|---|---|
| google/eng-practices | 23,274 | Google code review guide (reviewer & author) |
| joelparkerhenderson/architecture-decision-record | 17,425 | ADR templates/examples |
| deanpeters/Product-Manager-Skills | 7,927 | PM frameworks packaged as AI-agent skills (PRDs, discovery, etc.) |
| basecamp/handbook | 6,664 | Basecamp's public employee handbook (calm, async culture) |
| engineering-management/awesome-engineering-management | 2,793 | EM learning & day-to-day practice |
| kdeldycke/awesome-engineering-team-management | 2,632 | Dev → engineering manager transition |
| dend/awesome-product-management | 2,452 | Curated PM/program-manager resources |
| domenicosolazzo/awesome-okr | 1,812 | OKR articles, books, examples |
| middlewarehq/middleware | 1,633 | Open-source DORA metrics platform |
| lorabv/awesome-agile | 1,497 | Agile/Scrum/Kanban resources |
| shahedbd/awesome-project-management | 816 | Project-management topics list |
| eugeneyan/ml-design-docs | 721 | Design doc template for ML systems |
| bmoeskau/engineering-ladders | 610 | Career ladders (roles/levels) |
| joelparkerhenderson/objectives-and-key-results | 421 | OKR guide with examples |
| thoughtworks/metrik | 364 | Four key metrics from CD pipelines |
| timbray/a-cloud-prfaq | 119 | Real example PR/FAQ (Tim Bray, ex-AWS) |

Note: no high-star "Shape Up" or "Scrum template" repo exists; the primary sources (Basecamp book, scrumguides.org) are the canonical references.

---

## Sources
- Scrum Guide 2020 — https://scrumguides.org/scrum-guide.html
- PMI, PMBOK Guide 7th ed. (2021) — https://www.pmi.org/standards/pmbok
- Basecamp, *Shape Up* (Ryan Singer, free) — https://basecamp.com/shapeup ; Ryan Singer videos above
- Linear Method — https://linear.app/method/introduction ; https://linear.app/method/write-issues-not-user-stories
- GitLab Product Development Flow — https://handbook.gitlab.com/handbook/product-development/how-we-work/product-development-flow/
- Atlassian Team Playbook — https://www.atlassian.com/team-playbook/plays
- Working Backwards PR/FAQ (Bryar & Carr) — https://www.workingbackwards.com/concepts/working-backwards-pr-faq-process
- Malte Ubl, "Design Docs at Google" — https://www.industrialempathy.com/posts/design-docs-at-google/
- Google re:Work OKR guide — https://rework.withgoogle.com/guides/set-goals-with-okrs/
- Spotify Engineering Culture part 1 (2014) — https://engineering.atspotify.com/2014/03/spotify-engineering-culture-part-1
- Jeremiah Lee, "Spotify's Failed #SquadGoals" (2020) — https://www.jeremiahlee.com/posts/failed-squad-goals/
- DORA 2024 Accelerate State of DevOps report — https://services.google.com/fh/files/misc/2024_final_dora_report.pdf ; cluster summary: https://octopus.com/blog/2024-devops-performance-clusters
- Kanban Guide — https://kanbanguides.org ; Eric Ries, *The Lean Startup*; Marty Cagan, *Inspired/Empowered* (svpg.com); Jeff Patton, *User Story Mapping*; Teresa Torres, *Continuous Discovery Habits*
- GitHub repos with stars in §17 (GitHub REST API, retrieved 2026-11-08)
- YouTube talks listed in §16
