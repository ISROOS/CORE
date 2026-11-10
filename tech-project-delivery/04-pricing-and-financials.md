# 04 — Pricing & Financials for Software Projects in Indonesia (2026)

Agent-facing reference. Covers what people cost, what modules cost, how to estimate, which pricing model to use, payment terms, maintenance, running costs, and Indonesian tax (PPN / PPh 23 / UMKM). Calculator: `estimate_project.py`, in the same folder (section 9).

**Legend:** **[S]** = taken from a named source (see Sources). **[E]** = my own estimate or triangulation; check it against your own project history. All IDR figures exclude PPN unless stated. FX used: **Rp18,100/USD** (BI JISDOR, 6 Nov 2026, Rp18,130), so update this before quoting in USD. jt = juta (million), rb = ribu (thousand), PD = person-day (*manday/mandays*), PM = person-month.

---

## 0. TL;DR decision rules

1. **Price = cost / (1 − margin)**, not cost × (1 + margin). A 30% margin is a 43% markup.
2. **Day-rate shortcut (agency, Jakarta) [E]:** *loaded cost/day ≈ monthly gross salary ÷ 10*. *Sell rate/day ≈ monthly salary ÷ 6.5* (30% margin plus 10% contingency). Example: a mid backend dev on Rp15jt/month costs about Rp1.5jt/day and sells at about Rp2.3jt/day. This matches Badr Interactive's public calculator rate of **Rp2,250,000 per developer-day** [S].
3. **Small Indonesian clients (UMKM)** budget Rp30–150jt for an MVP. Mid-size business apps run Rp150–400jt, and complex apps Rp400jt to Rp1M+ (Crocodic 2026 market tiers [S]). Test the client's budget in the first call and offer to scope down rather than discount.
4. **Default commercial terms:** fixed price per phase, paid in **DP 30–50%** and then milestones, with a **10% retention** at warranty end. Add a 30–90 day warranty, a written change-request process, and a maintenance retainer of **15–20% of build per year**.
5. **Contingency:** 10% for well-specified work, 15–25% for typical work, 30%+ (or switch to T&M) when the client has no spec, legacy integrations are involved, or AI accuracy targets apply.
6. **Tax:** a PKP vendor charges PPN at **12% × DPP Nilai Lain (11/12 × price) = 11% effective**. A corporate client withholds **PPh 23 at 2%** of the price excluding PPN, and the vendor gets a *bukti potong* as a tax credit. Quote "harga belum termasuk PPN".
7. **Never fold third-party running costs into the build price.** That covers cloud, WhatsApp API, SMS, LLM tokens, store fees and domains. Pass them through at cost, or offer a managed bundle with an explicit markup.

---

## 1. People cost: salaries → loaded cost → sell rates

### 1.1 Salary anchors (monthly gross, IDR juta, mostly Jakarta)

| Anchor | What it says | Type |
|---|---|---|
| **Michael Page Indonesia Salary Guide 2025** (average gross monthly, experienced hires) | FE 20, QA 23, BE 25, Mobile 25, Full-stack 30, Tech Lead 40, Solution Architect 55, Eng. Manager 67, Head of Eng 81 · Product Manager 25, Sr Product Mgr 35, Sr Project Mgr 35, UX/UI Designer 43, Head of Product 60 · BI Analyst 27, Lead Data Eng 42, Lead Data Scientist 46 · Sr DevOps 35, Cloud Architect 50 · Sr Security Eng 35 | [S] recruiter data, biased toward mid–senior and MNC/corporate roles |
| **MSBU Tech Salary Guide 2026** (cited by Binar) | Backend mid 7.5–15, senior 12.5–27 · AI developer mid 10–30.5, senior 20–50 | [S] secondary citation |
| Other 2026 ranges cited by Binar | Full-stack 9–12 / 13–17 / 18–25 · Data analyst 7–9 / 10–13 / 13–17 · Data eng 9–11 / 12–16 / 16–22 · DevOps 9–12 / 12–16 / 16–22 (entry/mid/senior) · entry IT 5–8 | [S] secondary |
| Levels.fyi (Nov 2026) | Median SWE total comp **Rp20.5jt/month** (n=289, skewed to tech firms) | [S] |
| Glints listings (2026) | Junior/regular SWE ads at Rp5.5–8.5jt; QA fresh-grad listing Rp4–4.5jt | [S] spot listings, not a survey |
| **INKINDO 2026 billing rates** (minimum consultant *billing* rates, DKI index 1.0, per month, already include overhead) | Sub-professional (≤2 yrs): *Pemrogram Perangkat Lunak* / *Pemrogram Basis Data* **17.6**, *Desain Grafis* 16.9, *Administrator Web* 14.6 · Tenaga Ahli S1 no SKK: 3 yrs **28.85**, 5 yrs **32.3**, 10 yrs ~40.85 | [S] primary. Use it for **government/BUMN HPS** and as a floor for corporate RFPs |

### 1.2 Working rate card (synthesised, 2026, Jakarta agency) [E, built on the anchors above]

Sell/day = midpoint salary × 1.45 overhead ÷ 15 billable days × 1.10 contingency ÷ 0.70 (30% margin). Sell/hour = day ÷ 8.

| Role | Junior (0–2y) | Mid (2–5y) | Senior (5y+) | Mid sell/day | Senior sell/day | Senior sell/hour | Anchor |
|---|---|---|---|---:|---:|---:|---|
| Project / Product Manager | 8–12 | 13–22 | 25–40 | Rp2.66jt | Rp4.94jt | Rp617rb | MP: PM 25, Sr PM 35, Sr Project Mgr 35 |
| Business Analyst | 7–10 | 11–17 | 18–28 | Rp2.13jt | Rp3.49jt | Rp437rb | [E]; MP BI Analyst 27 |
| UI/UX Designer | 6–9 | 10–16 | 17–30 | Rp1.97jt | Rp3.57jt | Rp446rb | [E]; MP UX/UI avg 43 (senior/lead pool) |
| Frontend Dev | 6–10 | 10–16 | 17–25 | Rp1.97jt | Rp3.19jt | Rp399rb | MP FE 20 |
| Backend Dev | 6–10 | 7.5–15 | 12.5–27 | Rp1.71jt | Rp3.00jt | Rp375rb | MSBU via Binar (mid/sr); MP BE 25 |
| Mobile Dev (Flutter/RN/native) | 6–10 | 10–17 | 18–28 | Rp2.05jt | Rp3.49jt | Rp437rb | MP Mobile 25 |
| Full-stack Dev | 9–12 | 13–17 | 18–25 | Rp2.28jt | Rp3.27jt | Rp408rb | 2026 range cited by Binar; MP FS 30 |
| DevOps / Cloud | 9–12 | 12–16 | 16–22 | Rp2.13jt | Rp2.89jt | Rp361rb | 2026 range cited by Binar; MP Sr DevOps 35 |
| QA Engineer | 5–8 | 8–13 | 14–23 | Rp1.59jt | Rp2.81jt | Rp351rb | [E]; MP QA 23; Glints QA fresh-grad 4–4.5 |
| Data Analyst | 7–9 | 10–13 | 13–17 | Rp1.75jt | Rp2.28jt | Rp285rb | 2026 range cited by Binar |
| Data Engineer | 9–11 | 12–16 | 16–22 | Rp2.13jt | Rp2.89jt | Rp361rb | 2026 range cited by Binar; MP Lead DE 42 |
| AI/ML Engineer | 9–14 | 10–30.5 | 20–50 | Rp3.08jt | Rp5.32jt | Rp665rb | MSBU via Binar (mid/sr); jr [E] |
| Tech Lead | — | 30–40 (lead) | 40–50 | Rp5.32jt | Rp6.84jt | Rp854rb | MP Tech Lead 40 [band E] |
| Solution / Cloud Architect | — | 45–55 | 55–70 | Rp7.60jt | Rp9.49jt | Rp1.19jt | MP Sol. Architect 55, Cloud Architect 50 [band E] |

**How to adjust:**
- **Outside Jakarta:** salaries run roughly 15–35% lower [E]. INKINDO publishes an official per-province index (Tabel 6-26) for government work.
- **Freelancer/solo:** the overhead factor is lower (~1.2) and margin is often 0–20%. Teknovidia's rule of thumb puts a freelance monthly rate at **4× the UMR** of your city or the client's city [S]. It also suggests discounting 20–30% for small or individual clients, or declining them.
- **Day vs hour:** per-hour sells at a premium. Teknovidia notes monthly/daily rates usually run 15–25% cheaper than hourly, the "grosir vs eceran" effect [S].

### 1.3 Loaded-cost formula (use this, not raw salary)

```
annual_cost   = salary × 12
              + THR (1 × salary)
              + employer BPJS (Kesehatan 4% + Ketenagakerjaan JKK/JKM/JHT/JP ≈ 6–7%; check caps)
              + laptop/software/AI tools (Rp1–3jt/month)
              + office/co-working + admin/accounting/sales share
              + bench time (unbilled weeks between projects)
billable_days = ~245 working days − leave (12) − sick/training (5–10) − sales/internal (10–20%)
              ≈ 160–190 days/year  (≈ 13–16 per month)
cost/day      = annual_cost / billable_days     →  rule of thumb salary × 1.35–1.6 ÷ 15
```
[E] The BPJS percentages are statutory, but caps and rates change, so check the current BPJS rules before relying on them.

### 1.4 International benchmarks (when selling abroad or to foreign-funded startups)

| Source | Figure |
|---|---|
| Upwork Insights (Nov 2026), web application developers worldwide, $10K+ earners | Median **$30/hr**, middle half $20–45, top 10% ≥$65 [S] |
| Lemon.io rate calculator, Indonesia, Q3 2026 (182 contracts) | Mid **$25/hr**, senior **$35/hr**, strong senior $41/hr [S] |
| Teknovidia sample of 100 Indonesian Upwork devs (older) | 50% charge **$10–20/hr** [S] |
| Toptal | Third-party reviews put it at roughly $60–200+/hr plus platform fees. These are secondary sources, so verify before citing |

At Rp18,100/USD: $25/hr ≈ Rp452rb/hr ≈ **Rp3.6jt/day**, which is at or above a premium local agency rate. Foreign clients therefore support local senior rates or higher.

---

## 2. Per-module price ranges

### 2.1 Local whole-app benchmarks (Indonesia)

| Source | Range |
|---|---|
| Crocodic (2026) | Prototype Rp3–50jt (2–6 wks) · Simple/MVP **Rp30–150jt** (2–3 mo: login, profile, catalog, forms, basic dashboard) · Mid business app **Rp150–400jt** (3–6 mo: payment, booking, multi-role, notifications, API) · Complex **Rp400jt–1M+** (6–12 mo) · Enterprise priced after assessment [S] |
| AppDev (2025), Android | Total Rp20–300jt. Components: UI/UX Rp5–50jt, features Rp10–100jt, backend/API Rp10–80jt, QA Rp5–30jt, external integrations Rp5–50jt, maintenance Rp1–5jt/month. Examples: company profile app 20–50jt, simple marketplace 75–150jt, delivery/transport 150–300jt, booking/event 50–120jt, education 60–150jt [S] |
| Badr Interactive calculator | **Rp2.25jt per developer-day**, with 1 month = 20 mandays. Phase split: requirements/planning ~10%, architecture + UI design ~5–10% [S] |
| Samasitu (template web shop) | "Basic" toko online package **Rp3jt**: 20 products, WA checkout, domain + hosting 1 yr [S]. This is template work, not custom software |
| Marino Technology | B2B order portal "starting from **Rp35jt**" [S] |

### 2.2 Per-module effort & price

Effort covers backend, web frontend or one cross-platform mobile client, and unit/feature testing for that module. It excludes per-screen UI design, PM and project-level QA (add those in 2.3). Prices = person-days × rate tier: Budget Rp1.2jt/PD (freelancer or small studio), Standard **Rp2.25jt/PD** (Badr-level agency), Premium Rp3.5jt/PD (senior or foreign-client rate).

Source keys: **CS** = Control Shift (UAE) feature estimator, in dev-days, cross-platform, including design, FE, BE and test [S]. **SP** = SquadPrime 2026 hours per feature, senior team [S]. **KX** = Kultrix hours per module [S]. **ADCC** = appdevelopmentcostcalculator.com, app + backend hours, one platform [S].

| Module | Person-days | Budget @Rp1,2jt/PD | Standard @Rp2,25jt/PD | Premium @Rp3,5jt/PD | Basis (sources) |
|---|---:|---:|---:|---:|---|
| Project foundation (repo, CI/CD, envs, base layout, deploy) | 5–15 | 6–18 jt | 11–34 jt | 18–52 jt | SP 30–60h; KX web base 100–200h; CS ~11 PD |
| Auth: email/password + reset + OTP/social | 3–6 | 3.6–7.2 jt | 6.8–14 jt | 10–21 jt | CS 4 PD (+OTP 4, social 3); SP 12–20h; ADCC 80h app+BE |
| RBAC (roles & permissions, 3–5 roles) | 4–8 | 4.8–9.6 jt | 9–18 jt | 14–28 jt | CS 7 PD; SP 12–24h add-on |
| User management (CRUD, invite, profile, audit log) | 3–6 | 3.6–7.2 jt | 6.8–14 jt | 10–21 jt | SP profile 8–16h + CRUD 24–50h |
| Admin dashboard (KPIs, tables, filters) | 8–20 | 9.6–24 jt | 18–45 jt | 28–70 jt | CS 12 PD; ADCC 120h; KX admin+analytics 80–160h |
| CMS (pages, banners, articles, media) | 5–12 | 6–14 jt | 11–27 jt | 18–42 jt | KX content mgmt 40–100h |
| Catalog (categories, variants, search/filter) | 6–12 | 7.2–14 jt | 14–27 jt | 21–42 jt | CS 10 PD; ADCC search 56h |
| Cart & checkout (address, shipping fee, order flow) | 6–12 | 7.2–14 jt | 14–27 jt | 21–42 jt | CS 9 PD; ADCC 80h |
| Payment gateway Midtrans/Xendit (Snap/VA/QRIS, webhook, recon) | 4–10 | 4.8–12 jt | 9–22 jt | 14–35 jt | CS 6 PD; SP 10–16h; KX 30–70h |
| Subscription/recurring billing | 8–14 | 9.6–17 jt | 18–32 jt | 28–49 jt | CS 10 PD; SP 20–40h |
| Invoicing (PDF, numbering, tax fields, e-mail) | 4–8 | 4.8–9.6 jt | 9–18 jt | 14–28 jt | [E] |
| Notifications: email (templates) | 2–4 | 2.4–4.8 jt | 4.5–9 jt | 7–14 jt | SP 6–12h |
| Notifications: WhatsApp via BSP/Cloud API templates | 3–6 | 3.6–7.2 jt | 6.8–14 jt | 10–21 jt | [E]; template approval adds calendar time |
| Notifications: push (FCM/APNs, preferences) | 3–5 | 3.6–6 jt | 6.8–11 jt | 10–18 jt | CS 3 PD; SP 12–24h; ADCC 40h |
| Reporting & export (charts, Excel/PDF) | 5–10 | 6–12 jt | 11–22 jt | 18–35 jt | CS 7 PD; SP 20–40h |
| Inventory (stock, mutations, multi-warehouse, opname) | 10–20 | 12–24 jt | 22–45 jt | 35–70 jt | [E] |
| POS (cashier UI, shifts, receipt printer, offline) | 15–30 | 18–36 jt | 34–68 jt | 52–105 jt | [E]; offline sync alone CS 8 PD, KX 40–90h |
| Booking & scheduling (slots, reschedule, reminders) | 6–12 | 7.2–14 jt | 14–27 jt | 21–42 jt | CS 8 PD; SP 30–60h; ADCC 112h |
| Chat 1:1 realtime (history, read state, attachments) | 8–14 | 9.6–17 jt | 18–32 jt | 28–49 jt | CS 10 PD; SP 30–60h; ADCC 176h (group chat: SP 60–100h) |
| Maps & geolocation (places, radius search) | 4–8 | 4.8–9.6 jt | 9–18 jt | 14–28 jt | CS 6 PD; SP 12–30h; ADCC 56h |
| Live tracking (driver location, ETA) | 8–12 | 9.6–14 jt | 18–27 jt | 28–42 jt | CS 9 PD |
| Multi-tenant SaaS layer (isolation, plans, onboarding) | 15–30 | 18–36 jt | 34–68 jt | 52–105 jt | [E] |
| AI chatbot / RAG (ingest, retrieval, guardrails, evals) | 10–25 | 12–30 jt | 22–56 jt | 35–88 jt | CS 14 PD; KX 80–180h; ADCC 112h |
| Third-party integration / API (each) | 3–9 | 3.6–11 jt | 6.8–20 jt | 10–32 jt | ADCC 48h; KX 25–70h; CS CRM/ERP 9 PD |
| Data migration (map, clean, import, verify) | 4–12 | 4.8–14 jt | 9–27 jt | 14–42 jt | KX 30–90h |
| Store release & publishing (both stores) | 2–4 | 2.4–4.8 jt | 4.5–9 jt | 7–14 jt | [E]; Apple review adds calendar time |

### 2.3 Multipliers and add-ons (apply after summing modules)

- **Platforms (ADCC [S]):** one cross-platform codebase (Flutter/RN) multiplies the *app-side* hours by **×1.25**. Two native apps multiply them by **×1.9**. A managed backend (Supabase/Firebase) cuts backend hours to ~60%, and connecting to an existing API cuts them to ~50%.
- **Glue/integration:** modules never add up cleanly. Control Shift adds **12% + 1 point per feature** for integration and QA [S]. Kultrix calibrates a glue factor against delivered projects [S].
- **UI/UX design:** ADCC adds 8 / 20 / 30% of app-side hours for light, custom or deep design [S]. Per screen [E]: **0.5–1.5 PD per unique hi-fi screen** including states, plus a design system/kit of 5–10 PD. A design-only engagement runs 80–180h (KX [S]). Local per-screen price at Rp1.2–2.5jt/PD comes to roughly **Rp0.6–3.5jt per screen** [E].
- **PM:** 10–15% (ADCC uses 10% [S]). **QA:** 15–25% of build. **Requirements/BA:** ~10% (Badr [S]).
- **Compliance/security** (PII, health, finance, UU PDP): 40–100h (KX [S]), plus a pentest if the client requires one.
- **Rush premium:** +20–50% when the timeline is compressed more than 25% [E].

---

## 3. Estimation methods

### 3.1 Which method when

| Situation | Method | Output |
|---|---|---|
| Pre-sales, 1-page brief | **Analogy / module table** (section 2) ± 50% | Range for "budgetary quote" (*penawaran indikatif*) |
| After discovery, feature list known | **WBS bottom-up** + **PERT 3-point** per task | Fixed price with contingency |
| Agile product, ongoing team | **Story points → velocity → sprints** | Retainer or T&M sprint budget |
| Government/BUMN tender | **Personnel months × INKINDO billing rate** + direct costs | RAB/HPS-style breakdown |
| Large or legacy system, sanity check | **Function points** or **COCOMO II** | Order-of-magnitude cross-check |

**Cone of uncertainty:** at the idea stage, actual effort can be 0.25×–4× the estimate. Narrow it with a *paid discovery* (Rp10–50jt or 5–10% of expected build [E]) before committing to fixed price. Steve McConnell's talks (Construx, SE Radio 273) explain why a single-point estimate is really a commitment, not an estimate.

### 3.2 WBS bottom-up
1. Break each module into tasks of **≤ 3 person-days** (bigger tasks hide unknowns), per role: BA, UI/UX, FE, BE, mobile, DevOps, AI.
2. Add the cross-cutting rows people forget:
   - project setup and CI/CD
   - environments (dev/staging/prod)
   - seed data
   - error/empty/loading states
   - responsive design
   - i18n (ID/EN)
   - audit log
   - backups and monitoring
   - store submission
   - UAT support and bug-fix rounds
   - training
   - handover docs
   - go-live hypercare
3. Add PM % and QA %, then contingency and margin.

### 3.3 PERT 3-point
`E = (O + 4M + P) / 6`, `σ = (P − O) / 6`. Project σ = √Σσ² if tasks are independent. They are not (same team, same client), so blend toward Σσ, as the calculator does with `pert_correlation = 0.5`.
- Example task "Midtrans integration": O = 4, M = 6, P = 12 PD → E = 6.67 PD, σ = 1.33.
- Confidence: P50 = E; **P80 = E + 0.84σ**; P90 = E + 1.28σ. Quote fixed price at P80–P90.

### 3.4 Story points → hours
- Calibrate with history: hours per point = (team hours in the last 3 sprints) ÷ (points completed). A typical starting assumption is 1 SP ≈ 4–8 focused hours [E].
- Budget = backlog points ÷ velocity (points/sprint) × sprint cost.
- Example: 240 SP, velocity 30 → 8 sprints × 2 weeks. A team of 4 at a blended Rp2.25jt/PD costs 4 × 10 days × 2.25jt = **Rp90jt/sprint**, so the total is **Rp720jt** + 15% buffer.

### 3.5 Function points (IFPUG, quick count)
- Weights (average complexity): External Input 4, External Output 5, External Inquiry 4, Internal Logical File 10, External Interface File 7. Unadjusted FP = Σ count × weight.
- Effort = FP × hours/FP, using your **own historical** productivity. Published benchmarks vary widely by stack and team, so do not borrow a number blindly.
- This is useful for government RFPs and for comparing vendors' quotes objectively.

### 3.6 COCOMO II basics (cross-check only)
- Effort (PM) = **2.94 × EAF × KSLOC^E**, with E = 0.91 + 0.01 × ΣSF. Nominal scale factors give ΣSF ≈ 18.97, so E ≈ 1.10.
- Schedule (months) = **3.67 × PM^(0.28 + 0.2 × (E − 0.91))**.
- Example: 20 KSLOC, nominal EAF = 1 → **79.3 PM**, **14.7 months**, about 5.4 people. Modern frameworks and AI-assisted coding make LOC-based models overestimate CRUD apps, so use this only as an upper sanity bound.
- To get COCOMO from an existing codebase (e.g., to value a legacy system you are taking over), run `scc` (boyter/scc, ★8.9k). It prints a COCOMO estimate with tunable `--avg-wage`, `--overhead` (default 2.4) and `--eaf` [S].

### 3.7 Contingency & risk buffer rules
| Risk driver | Add |
|---|---|
| Clear spec + known stack + known client | 10% |
| Typical SME client, spec from discovery | 15–20% |
| Legacy/3rd-party integration, unknown APIs (bank, ERP, government) | +10% per major integration |
| AI/LLM features with accuracy expectations | +20–30% on that module (or time-box it) |
| Client with many decision makers / slow feedback | +10% or charge for waiting time |
| New tech for the team | +15–25% on affected modules |

Keep **contingency** (known unknowns, inside the price) separate from **management reserve** (handled through change requests). Never show contingency as a line item to price-sensitive clients. Bake it into module prices instead.

### 3.8 Worked example (calculator output, sample project)
"KlinikKu": web admin + Flutter app covering booking, Midtrans, WA/email/push notifications, invoices, reports, an AI FAQ bot (RAG), store release and data import. 14 WBS modules with 3-point estimates; team of PM, BA, UI/UX, FE, 2 BE, mobile, QA, DevOps and AI.
- Most-likely build = 132 PD. The PERT mean plus PM 12% and QA 20% gives **171.5 PD**.
- Labour cost (loaded): **Rp251.8jt**, at an average Rp1.47jt/PD.
- Contingency: PERT P80 came out at about 8%, so it was floored to **10%** → Rp25.2jt.
- Margin 30% on price → **services price Rp396.0jt** (effective Rp2.31jt/PD, in line with Badr's Rp2.25jt).
- Taxes: DPP Nilai Lain Rp363.0jt → **PPN Rp43.56jt**. Pass-through costs (domain, Apple/Google fees) Rp2.59jt. **Invoice total Rp442.15jt**.
- The client withholds PPh 23 of Rp7.92jt, so **cash received is Rp434.23jt**.
- Termin: DP 40% (Rp175.8jt incl. PPN), UI sign-off 20%, UAT 30%, retention 10%.
- Duration ≈ 8 weeks of build plus client waits. Maintenance at 18%/yr = **Rp5.94jt/month**.
- Sanity check against market: this sits inside Crocodic's "mid business app Rp150–400jt" tier [S].

---

## 4. Pricing models — when to use

| Model | Use when | Risk sits with | Protect yourself by |
|---|---|---|---|
| **Fixed price** (*borongan*) | Scope is clear after discovery; UMKM and government want certainty | Vendor | Detailed SOW + acceptance criteria, exclusions list, CR process, P80 estimate, limited revision rounds |
| **Time & Materials** (*per manday/jam*) | Unclear scope, R&D, AI experiments, legacy rescue | Client | Weekly timesheets (e.g., Kimai), budget cap/alerts, monthly invoicing |
| **Dedicated team / retainer** (*sewa tim bulanan*) | Ongoing product development, startups | Shared | Minimum 3-month term, 30-day notice, rate review every 12 months |
| **Milestone-based fixed** | Default for SME custom builds | Vendor (per milestone) | Pay-per-milestone, re-estimate later phases |
| **Fixed-price discovery → fixed/T&M build** | Any project over ~Rp100jt with a vague brief | Shared | Discovery deliverables (BRD, wireframes, estimate) are the client's to keep. Credit the fee against the build if signed within 30 days |
| **Value-based** | You can quantify the client's gain (e.g., saves 3 admins = Rp15jt/month) | Vendor upside | Price at 10–30% of first-year value. Chris Do / The Futur: use time-, project- and value-based models as fits, and "price the client, not the job" |
| **Subscription / SaaS license** (Lumii-style) | Same product for many clients; low upfront budgets | Vendor (CAPEX) | Setup fee + monthly per outlet/user. Annual prepay discount 10–20%. Price tiers by usage (messages, AI tokens) |
| **Revenue share** | Client is a startup with no cash; you believe in it | Vendor (heavily) | Only with a floor fee covering cost, audit rights, a cap/term and an exit buy-out price. Prefer a small equity stake plus a reduced fee |
| **License + customization** | You own a base system (POS, booking) | Mixed | Retain IP; client gets a non-exclusive license. Customization billed per manday |

**IP note:** custom work usually transfers source code/IP after full payment. A reusable core licensed to the client is the norm for product companies; state it explicitly. It also changes the tax character (section 7.3).

---

## 5. Payment terms (termin) & contracts

**Standard SME schedule [E, common market practice]:**
- **DP 30–50%** at signing. Do not start without it; 50% for new or small clients.
- Milestones: design sign-off 20%, staging/UAT 20–30%, go-live/BAST.
- **Retention 5–10%** paid at warranty end (30–90 days).

**Example schedules:**
- *Small project < Rp50jt:* 50% DP / 50% at handover.
- *Rp50–300jt:* 40 / 20 / 30 / 10, as in the worked example.
- *Large or corporate:* 30% DP / 4–5 milestones / 10% retention. Corporates may insist on payment only after BAST (*Berita Acara Serah Terima*) with Net-30/45 terms. Price in the financing cost (+2–3%), or ask for a bank guarantee or a larger DP.
- *Government (LKPP):* payment follows contract termin after BAST, often with a 5% performance bond. Price per INKINDO billing rates.

**Contract must-haves:**
- **SOW** with a feature list and acceptance criteria per feature.
- **Exclusions**, e.g. content entry, store account fees, third-party fees, data cleansing, hardware.
- Revision rounds: e.g. 2 rounds per design screen.
- Client obligations: timely feedback within **3 working days**, after which the timeline shifts.
- **Change Request (CR) procedure:** written CR → impact estimate (cost + days) → signed before work.
- Warranty: bug = deviation from the agreed spec; it is not new behaviour.
- IP transfer on full payment.
- Late payment: work pauses after X days, plus a penalty or interest.
- Termination: paid for work done plus a kill fee.
- Hosting/third-party accounts held in the client's name.
- Governing law and dispute resolution (BANI or court).
- e-Meterai Rp10,000 on contracts and receipts above Rp5jt (Bea Meterai law).
- Open templates: the-plain-contract (★311), zkrige/freelancer_contract (★105).

**Scope-creep protection checklist:**
- [ ] Discovery phase produced a signed BRD/SRS + wireframes (Badr publishes a BRD guideline).
- [ ] Every feature has acceptance criteria ("done = …").
- [ ] Change budget: suggest 10–15% of contract as a pre-approved CR pool.
- [ ] CR rate card in the contract (e.g., Rp2.25jt/PD or Rp350rb/hour).
- [ ] "Out of scope" log shared weekly. Small items get bundled into a phase 2 quote.
- [ ] UAT window fixed (e.g., 10 working days). Silence counts as acceptance.
- [ ] Freeze the scope for each milestone. New ideas go to the backlog.

**Discount rules [E]:** never discount the day rate; cut scope instead (MVP first). Acceptable levers:
- 3–5% for full upfront payment
- 5–10% for a portfolio/case-study right or a multi-phase commitment
- 10–20% annual-prepay discount for SaaS
- an NGO/education rate

Always show the discount as a separate line, so the list price stays anchored.

---

## 6. Maintenance, support & running costs

### 6.1 Maintenance pricing
| Basis | Figure |
|---|---|
| International norm | **15–25% of original build per year** (Adevs [S]). Small apps often need less; the 15–20% convention comes from large systems (Pincler [S]) |
| Indonesian vendors | Rp1–5jt/month for business apps holding customer or transaction data; Rp5–10jt+/month for core systems with guaranteed response times (Xetup via CiptaDusa [S]). Odoo implementer: **5% of project value/yr** (Nextgen [S]). Remote maintenance from **Rp1.5jt/month** (projects.co.id listing [S]) |
| After warranty, ad hoc | Bug fixes Rp200rb–1jt/hour (Majapahit Teknologi via CiptaDusa [S]) |

**Tiered retainer template [E]:**
- **Basic (~1% of build/month, min Rp1.5jt):** monitoring, backups, security patches, 4 h/month of fixes, response 2 working days.
- **Standard (~1.5%/month):** 10 h/month, response 1 working day, monthly report.
- **Priority (2%+/month):** 20+ h, 4-hour response for P1 issues, 24/7 on-call surcharge.

Unused hours do not roll over, or roll over for at most one month. New features are billed by CR. ISO/IEC/IEEE 14764 maintenance types are corrective, adaptive, perfective and preventive. Backups and sysadmin work fall outside that standard, so list them explicitly.

### 6.2 Third-party & infrastructure costs (pass-through; verify before quoting)
| Item | Price (as found) |
|---|---|
| **Midtrans** (per successful transaction, ex-VAT except QRIS/GoPay/ShopeePay) | Bank transfer/VA **Rp4,000** · Card **2.9% + Rp2,000** · QRIS **0.7%** · e-wallets ~1.5–2% · over-the-counter Rp5,000 · cardless credit 1.7–2%. No setup or monthly fee [S] |
| **Xendit** (help-centre rate card) | VA (Mandiri/BNI/BRI/Permata) **Rp4,500** · BCA VA = BCA fee + Rp2,000 · cards 2.9% + Rp2,000 [S] |
| QRIS MDR policy | Bank Indonesia set 0% MDR for QRIS payments ≤ Rp100,000 for all merchants from 1 Oct 2026 (PaymentReview [S]). Check current BI rules |
| **WhatsApp Business Platform** (Meta, Indonesia, from 1 Oct 2026, per delivered message) | Marketing **Rp586.33** ($0.0411) · Utility / Authentication / Service **Rp356.65** ($0.025). Utility gets tier discounts above 750k msgs/month. Replies inside the 24-hour window: check Meta's current free-service rules. A BSP (WATI, Qontak, 360dialog, etc.) adds its own platform fee [S] |
| **LLM APIs** (OpenAI standard tier, per 1M tokens, input/output) | gpt-5-mini $0.25 / $2.00 · gpt-5.4-mini $0.75 / $4.50 · gpt-6-luna $0.10 / $0.50 · gpt-6-sol $2 / $10 · text-embedding-3-small $0.02 [S, developers.openai.com Nov 2026]. Cost per chat ≈ (in_tok × in_price + out_tok × out_price) / 1e6. Example: 3k in + 500 out on gpt-5-mini ≈ $0.00175 ≈ **Rp32 per answer** |
| App stores | Apple Developer **$99/yr**; Google Play **$25 one-time** [S] |
| Domain | `.id` ~Rp215–300rb/yr; `.co.id` ~Rp270–400rb/yr, varying by registrar (get.id, Hoster [S]) |
| Cloud/VPS | Local VPS from ~$6/month (Valebyte Nov 2026 [S]). Small production stacks typically run Rp0.5–3jt/month; managed Odoo/ERP-class hosting Rp1.5–5jt/month (Cherp [S]) |
| SMS OTP | Varies by provider. Prefer WhatsApp authentication or email OTP to save cost [E] |

**Rule:** bill these monthly at cost with the invoice attached, so they stay outside the PPh 23 base (section 7.2). Or sell a "managed hosting" bundle at cost +20–30% and treat it as a taxable service. For AI features, quote a **monthly token allowance**: estimated messages × cost per answer × 1.5 safety factor. Bill any overage.

---

## 7. Indonesian tax notes (not legal advice; confirm with a *konsultan pajak*)

### 7.1 PPN (VAT)
- The statutory rate has been **12%** since 1 Jan 2025. For non-luxury goods/services, PMK-131/2024 sets **DPP Nilai Lain = 11/12 × selling price**, so PPN = 12% × 11/12 × price = **11% effective**. PMK-11/2025 (in force 4 Feb 2025) consolidates DPP Nilai Lain and besaran tertentu PPN schemes [S, DJP].
- Only a **PKP** (VAT-registered entrepreneur) charges PPN. Registration is mandatory above **Rp4.8 miliar** annual turnover and voluntary below it. Many corporate clients prefer PKP vendors because they can credit input VAT.
- **Faktur pajak** is issued via **Coretax**. A **DP creates a faktur pajak uang muka** at receipt. Later termin are also uang muka fakturs referencing the first one, with the final pelunasan faktur at the end (DJP Coretaxpedia [S]). Issue fakturs at each payment or invoice date, not only at the end.
- Invoice layout:
  - Harga Jual: Rp100.000.000
  - DPP Nilai Lain (11/12): Rp91.666.667
  - PPN 12%: Rp11.000.000
  - Total: Rp111.000.000

### 7.2 PPh 23 (withholding on services)
- **2% of gross excluding PPN** for "jasa lain" under PMK-141/2015. That list includes software/website development, IT consulting, hosting/data processing and maintenance of computers and software. The rate is **4% if the vendor has no NPWP/valid NIK** [S, BukpotRekap; Kring Pajak].
- The client (badan / PKP / appointed withholder) deducts it and issues an **e-Bupot**. The vendor credits it against annual PPh. Plan for cash of 98% of DPP plus PPN.
- Genuine **reimbursements** (cloud, domain) invoiced at cost with the principal's invoice in the client's name can be excluded from the PPh 23 base. A marked-up "managed" bundle is fully subject to PPh 23 [S].
- **Off-the-shelf licenses are not PPh 23 jasa objects** (PPN only). **Royalties** for exploitation rights are PPh 23 at 15% (or PPh 26 for foreigners). Contract wording decides the classification, so describe custom builds as *jasa pembuatan perangkat lunak* [S].

### 7.3 Small-vendor regimes (relevant if you operate as an individual/UMKM or a new PT)
- **PP 55/2022 PPh Final 0.5%** of gross turnover for turnover ≤ Rp4.8 miliar/yr, for a limited number of years depending on entity type. DJP notes individuals who started in 2018 used it until 2024 [S]. Rules on time limits and extensions have been changing, so verify current status.
- A UMKM vendor holding a valid **Surat Keterangan PP 55** can ask the client not to withhold PPh 23 at 2% and instead apply the final 0.5% treatment. Attach the Suket to the invoice.
- A PT with turnover ≤ Rp4.8 miliar that is outside the final regime gets the Pasal 31E facility (50% rate cut on the relevant portion) [S, DJP].
- Pricing implication: quote the same **pre-tax price** either way. Show PPN only if PKP. Never quote "net after tax" unless you gross up deliberately: net = price × (1 − 2%) → gross-up price = net / 0.98.

### 7.4 Foreign clients
Export of services can qualify for 0% PPN only for specific service types under the regulations (PMK on export of JKP). Check whether software development qualifies before relying on it. Payments from abroad are usually not subject to Indonesian PPh 23 withholding by the payer; the vendor declares the income.

---

## 8. Quote/proposal financial section — template

```
RINGKASAN BIAYA (harga dalam Rupiah, belum termasuk PPN)
1. Discovery & Desain UI/UX ............................ Rp  xx.xxx.xxx
2. Pengembangan Modul (lihat lampiran rincian per modul)  Rp xxx.xxx.xxx
3. QA, UAT, Deployment & Training ...................... Rp  xx.xxx.xxx
   Subtotal Jasa (DPP) ................................. Rp xxx.xxx.xxx
   Diskon (jika ada) ................................... (Rp  x.xxx.xxx)
   PPN 12% x DPP Nilai Lain 11/12 ...................... Rp  xx.xxx.xxx   ← hanya jika PKP
   TOTAL ............................................... Rp xxx.xxx.xxx
Biaya pihak ketiga (ditagihkan sesuai tagihan aktual): cloud, domain, WhatsApp API, LLM API, akun Apple/Google.
Termin: DP 40% | Sign-off desain 20% | UAT 30% | Retensi 10% (30 hari setelah go-live)
Garansi bug 60 hari. Maintenance opsional: Rp x.xxx.xxx/bulan (paket Standard).
Perubahan scope melalui Change Request; tarif Rp2.250.000/manday.
Penawaran berlaku 30 hari. PPh 23 dipotong sesuai ketentuan.
```

Present **three options** (good / better / best): MVP, Standard, Full. Clients anchor on the middle option, and the cheaper one stops the "can you discount?" conversation.

---

## 9. Calculator — `estimate_project.py`

Path: `C:/Users/USER/AppData/Local/hermes/cache/scratch/pm-research/estimate_project.py`. Standard library only, Python 3.8+.

```
python estimate_project.py --sample > sample_project.json   # editable template
python estimate_project.py sample_project.json              # text report
python estimate_project.py sample_project.json --md out.md  # markdown for proposals
python estimate_project.py sample_project.json --json       # for further automation
```

**Inputs (JSON):**
- `roles`: a day rate, or `{salary, overhead_factor, billable_days}`.
- `team`: headcount per role.
- `modules[].effort`: role → days or `[O, M, P]`.
- `overheads`: e.g. `pm_pct`, `qa_pct`, as a % of build-role days.
- `contingency_pct`: a number, or `pert_p80` / `pert_p90`, with `pert_correlation` and `min_contingency_pct`.
- `margin_pct` (on price), `discount_pct`, `rounding`, `pass_through_costs`.
- `tax`: `pkp`, `ppn_rate`, `dpp_factor` (11/12), `client_withholds_pph23`, `pph23_rate`.
- `payment_schedule` (must sum to 100%), `maintenance_pct_per_year`.

**Outputs:**
- module and role breakdown
- labour cost, contingency, margin, discount, services price, effective sell rate
- DPP Nilai Lain, PPN, invoice total, PPh 23 withheld, cash received
- per-term schedule (price / PPN / invoice / PPh 23 / transfer)
- calendar weeks, and maintenance per year and per month

Tested on the sample (results in section 3.8). Input validation rejects unknown roles, an O ≤ M ≤ P violation, or a schedule that doesn't sum to 100%. Sample output: `sample_estimate.md`.

---

## Sources

**Salary / rates**
- Michael Page, *Indonesia Salary Guide 2025*, Technology pp. 33–34 (PDF mirror): https://jakartasatu.com/wp-content/uploads/2025/03/Indonesia-Salary-Guide-2025.pdf. Read Nov 2026.
- INKINDO, *Pedoman Standar Minimal 2026 – Billing Rate* (Tabel 3-26, 4-26): https://inkindo.org/documents/ikdweb-billing-rate-2026.pdf
- Binar, *Benchmark Gaji IT di Indonesia* (cites MSBU Tech Salary Guide 2026 and other 2026 ranges): https://www.binar.co.id/blog/benchmark-gaji-it-di-indonesia
- Levels.fyi, SWE Indonesia (updated Nov 2026): https://levels.fyi/t/software-engineer/locations/indonesia
- Glints listings: https://glints.com/id/explore/gaji-software-engineer-indonesia
- Upwork Insights, web application developer rates (Nov 1, 2026): https://www.upworkinsights.com/rates/web-application-freelancers
- Lemon.io, Indonesia rate calculator (Q3 2026): https://lemon.io/rate-calculator/indonesia
- Teknovidia, *Menentukan Rate Mandays Freelance Programmer*: https://www.teknovidia.com/rate-mandays-freelance-programmer
- Robert Walters Indonesia salary survey page (gated; numbers not extracted): https://www.robertwalters.co.id/our-services/salary-survey.html

**Project / module pricing**
- Badr Interactive project calculator (RATE = Rp2,250,000/day in page script; phase %): https://badr.co.id/project-calculator
- Crocodic, *Biaya Pembuatan Aplikasi 2026*: https://crocodic.com/biaya-pembuatan-aplikasi
- AppDev, *Biaya Bikin Aplikasi Android 2025*: https://appdev.co.id/biaya-bikin-aplikasi-android-di-2025-estimasi-panduan-lengkap
- Control Shift, App Feature Estimator (AED, dev-days): https://www.controlshift.ae/app-feature-estimator
- SquadPrime, *MVP development cost by feature (2026)*: https://squadprime.com/blog/mvp-development-cost-breakdown-by-feature
- Kultrix, *App development cost: hours by module*: https://kultrix.com/blog/app-development-cost-hours-by-module
- App Development Cost Calculator, *Cost by feature*: https://appdevelopmentcostcalculator.com/cost-by-feature/
- Samasitu toko online packages: https://samasitu.id/jasa-pembuatan-website/website-toko-online/
- Marino Technology B2B portal: https://marinotechnology.com/layanan/portal-pesanan-klien-b2b-authenticated-enterprise-workspace

**Maintenance**
- CiptaDusa, *Biaya maintenance aplikasi* (cites Xetup, Majapahit Teknologi, ISO/IEC/IEEE 14764): https://ciptadusa.com/en/blog/biaya-maintenance-aplikasi
- Nextgen, Odoo implementation pricing (maintenance 5%/yr): https://nextgen.co.id/harga-implementasi-odoo
- Adevs, *Software maintenance costs 2026*: http://adevs.com/blog/software-maintenance-costs
- Pincler, *Software maintenance cost*: https://www.pincler.com/blog/software-maintenance-cost

**Third-party costs**
- Midtrans pricing: https://stg-v2.midtrans.com/en/pricing and https://docs.midtrans.com/docs/how-much-does-midtrans-charge-for-its-payment-service
- Xendit pricing: https://help.xendit.co/hc/en-us/articles/360025424912-What-are-the-pricings-for-Xendit-products
- QRIS MDR 2026: https://paymentreview.com/blog/indonesia-qris-merchant-fees-2026
- WhatsApp API pricing Indonesia (Meta rate card, Oct 2026): https://calypso.so/whatsapp-api-pricing/indonesia ; Meta docs: https://developers.facebook.com/documentation/business-messaging/whatsapp/pricing
- OpenAI API pricing: https://developers.openai.com/api/docs/pricing
- BI JISDOR exchange rate: https://bi.go.id/id/statistik/informasi-kurs/jisdor
- Store fees: https://appdevelopmentcostcalculator.com/app-store-fees
- Domain prices: https://get.id/ ; https://www.hoster.co.id/

**Tax**
- DJP press release, PMK-11/2025 DPP Nilai Lain: https://www.pajak.go.id/index.php/id/siaran-pers/pemerintah-terbitkan-aturan-dpp-nilai-lain-dan-besaran-tertentu-ppn
- FAQ PMK-131/2024 (12% × 11/12): https://ptpsi.com/wp-content/uploads/2025/01/FAQ-PMK-131.pdf
- DJP Coretaxpedia, faktur pajak uang muka & pelunasan: https://www.pajak.go.id/coretaxpedia/faktur-pajak-uang-muka-dan-pelunasan
- BukpotRekap, PPh 23 jasa TI/software (PMK-141/2015): https://www.bukpotrekap.id/blog/pph-23-jasa-teknologi-informasi-software-website-coretax
- Kring Pajak on X (software/website services = PPh 23 at 2%): https://x.com/kring_pajak/status/1748165691721887787
- DJP, PPh Final UMKM 0.5%: https://www.pajak.go.id/id/artikel/gunakan-tarif-pph-final-05-sejak-2018-umkm-perlu-tahu-ini ; PPh Badan Pasal 31E: https://www.pajak.go.id/id/artikel/lima-jenis-tarif-pph-badan-yang-wajib-diperhatikan

**GitHub (stars via GitHub API, 8 Nov 2026)**
- boyter/scc ★8,863: code counter with a COCOMO estimate (`--avg-wage`, `--overhead`, `--eaf`). https://github.com/boyter/scc
- kimai/kimai ★5,146: open-source time tracking for T&M billing. https://github.com/kimai/kimai
- InvoicePlane/InvoicePlane ★3,280: self-hosted invoicing. https://github.com/InvoicePlane/InvoicePlane
- jackmorgan/the-plain-contract ★311: plain-language freelance contract template. https://github.com/jackmorgan/the-plain-contract
- zkrige/freelancer_contract ★105: freelance developer contract template. https://github.com/zkrige/freelancer_contract

**Talks / video**
- The Futur (Chris Do), *How to Charge for Creative Work* (three pricing models): https://thefutur.com/watch/how-to-charge-for-creative-work-sales-masterclass ; *Price the client, not the job*: https://thefutur.com/watch/price-the-client-not-the-job
- Steve McConnell, *10 Deadly Sins of Agile Software Estimation*: https://www.youtube.com/watch?v=DG-_KAXaQvY ; SE Radio 273: https://se-radio.net/2016/11/se-radio-episode-273-steve-mcconnell-on-software-estimation/
