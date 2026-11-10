# Consulting Problem-Solving: Field Reference

Condensed from 10 open-source "consultant" skill repos (see **Sources**). Each item notes which repo it comes from: [GC]=gcamilo, [YO]=yoichiojima-2, [CG]=ConrayGambit, [CJ]=chefjefff, [SP]=spacemata, [DI]=DogInfantry, [SR]=sruthir28, [AV]=averma416, [AB]=abinauv, [DD]=didixuxu.

---

## 0. Master workflow (the loop)

7-step Bulletproof Problem Solving (Conn & McLean, via [CJ]): **Define → Disaggregate → Prioritize → Workplan → Analyze → Synthesize → Tell the story.** It is a loop, not a straight line. You "porpoise": dive into data, come up, sharpen the hypothesis, dive again. Keep a *one-day answer* ready at every stage.

Working version [GC]: **Clarify → Structure (MECE) → Hypothesize (+ kill test) → Analyze (facts vs. assumptions) → Synthesize (Pyramid) → Challenge your own recommendation.**

**Three questions for every page and every claim** [SP]: *So what?* (the insight) · *Why so?* (the evidence) · *Now what?* (the action).

**Day-1 answer** [SP]: "If I had to recommend right now, what would I say?" That answer becomes the hypothesis you test, and it stops you from boiling the ocean.

---

## 1. Problem definition

### SMART+ problem statement [CJ]
- [ ] Outcome-focused, not activity-focused
- [ ] Specific and measurable
- [ ] Time-bound
- [ ] Aligned with the decision-maker (their values, boundaries and accuracy needs)
- [ ] Scoped wide enough to leave room for creative solutions
- [ ] Solved at the highest sensible level (whole org, not one unit)

**Problem-definition worksheet** [CJ]: problem statement · context (why now) · success criteria · in/out of scope · decision-maker and their values · time frame · accuracy required (rough or precise) · stakeholders.

**Clarify before analysis** [GC]: name the **decision**, the **decision-maker**, the **success metric**, the **constraints** and the **scope**. If any are missing, state *provisional assumptions [A]* and carry on. Don't block on questions.

**Stress-test the statement** [CJ]: write an antithesis, rewrite it from the CEO's view and from a competitor's view. Anti-pattern: "I've seen this before." Newspapers framed their threat as editorial quality, but the real attack was on classified-ad revenue.

### SCQ / SCQA / SCR / SCPR
- **SCQA** [GC]: **S**ituation (1–3 sentences of shared, non-controversial context) → **C**omplication (what changed, with numbers, creating urgency) → **Q**uestion (follows from C, answerable, same scale as C) → **A**nswer (becomes the Pyramid's governing thought).
  - Good: S "Dell led PCs for 20 years via direct-model cost advantage" / C "Lenovo and Huawei undercut by 15–20%" / Q "How can Dell compete when hardware cost is no longer its edge?" / A "Double down on services…"
  - Bad: "Tech is changing / Dell has challenges / What should Dell do? / Innovate."
  - Mistakes: vague or grandiose complication; scale mismatch ($500M problem, $2M answer); a Situation that teaches new information. If there is no real complication, use **SQA**.
- **SCPR** [SR]: Situation → Complication → **Problem** (one crisp, answerable question) → **Recommendation** (MECE, specific, time-bound actions).
- **SCR one-day answer** [CJ]: Situation / Complication / Resolution. Use it as a strawman to attack and as your elevator answer.

---

## 2. Structuring: MECE and issue trees

### MECE
- **ME**: no item belongs in two branches. **CE**: every relevant item fits somewhere [CG][CJ].
- Test [SR]: can every element of the answer be placed in exactly one branch?
- Typical size [CG]: 3–6 top-level categories with 2–5 sub-factors each. Generic People/Process/Technology buckets are a smell.
- Common violation [CJ]: a cross-cutting factor (e.g. "government policy") drawn as its own branch when it touches every branch.
- Don't treat MECE as the goal in itself [GC]: relevance beats structural purity.

### Tree types [CJ]
| Tree | Use when |
|---|---|
| Component/factor | Early on, when you know little |
| Deductive | The logical or math structure is known (e.g. profit = P×V − C) |
| Inductive | You have specific cases and are generalizing |
| Hypothesis | You can state testable hypotheses (grows out of a component tree) |
| Decision | Choosing between options with yes/no gates |
| Profit lever / ROIC | Business-performance problems |

**ROIC tree** [CJ]: ROIC = Profit margin × Capital turnover. Margin breaks into Revenue (Price × Volume × Share) minus Costs (COGS, SG&A, overhead). Turnover = Revenue / Invested capital (working capital + fixed assets).

### Issue-tree checklist [SR][GC]
- [ ] Governing question is specific and answerable ("Should EuroSaaS enter the US by Q1 2027?", not "Should we enter the US?")
- [ ] Roughly 3 (3–5) Level-1 branches; 2–4 levels deep [CJ]
- [ ] Branches are fundamentals, not actions. Revenue: P × Q × funnel. Profit: Rev − Cost. Growth: new customers / expand existing / new products. Market entry: attractiveness / competitive position / capability to win [SR]
- [ ] Every leaf is a testable hypothesis with obvious data ("checkout abandonment 68% vs. 58% benchmark")
- [ ] Leaves evidence-coded **[F] fact / [I] inference / [A] assumption (with confidence %) / [E] estimate** [GC]
- [ ] No "Risks" or "Other" catch-all branch (it overlaps everything) [GC]
- [ ] Kill-test branches flagged and analyzed first [GC]
- [ ] Try 2–3 alternative cuts and keep the one that gives the most insight [CJ]

---

## 3. Hypothesis-driven approach
- Form the view first, then gather data to test it [SP]. Steps: hypothesis → *killer analyses* ("if true, COGS/unit rose faster than price") → run them → confirm or pivot.
- For each branch [GC]: **hypothesis** (what must be true) · **kill test** (the single data point that would disprove it) · **priority**. Lead with the hypothesis that would change the recommendation most if true.
- Test table [CG]: one-sentence falsifiable hypothesis, then `Variable | Expected if true | Actual / data needed` with 4–7 measurable variables. **At least one control row** (something that should *not* match if the hypothesis is true). Mark ✅/❌ against actuals.
- Pitfall [GC]: in a new domain, a bad hypothesis tree wastes more time than open exploration. Start with an issue tree there.

---

## 4. Prioritization and the 80/20 rule

**Pareto** [CG][CJ]: name the vital 1–4 drivers specifically (named accounts, SKUs, causes). **Write the deprioritized list down explicitly.** The test of a real cut: something important ends up on it ("Yes, X matters. We are not doing X this quarter.").

**Impact × ability-to-move matrix** (pruning a tree) [CJ]:
| | Low impact | High impact |
|---|---|---|
| **Can move it** | Easy win only if cheap | **FOCUS: the critical path** |
| **Can't move it** | Ignore | Acknowledge, don't invest |

Revisit the pruning when constraints relax, when estimates change, or when you're stuck.

**Other matrices** [SR]:
- **Impact/Effort 2×2**: Quick Wins (do first) / Big Bets (plan and resource) / Fill-ins / Money Pit (avoid). Fast, works with little data.
- **RICE** = (Reach × Impact × Confidence) / Effort. Impact scale 0.25/0.5/1/2/3; confidence 50/80/100%; effort in person-months. Use when you have quantitative data.
- **Value vs. Complexity**: technical or tech-debt decisions.
- **Weighted scoring**: custom criteria with weights summing to 100% (e.g. strategic 30, customer 25, revenue 20, effort 15, risk 10).

**Workplan rules** [CJ]: no analysis without a hypothesis · *dummy the chart* first · **knock-out order** (analyses that eliminate work go first) · one named owner · due date *and time*. Columns: Issue | Hypothesis | Analysis | Source | Owner | Output | Due. Keep the detailed plan to 2–3 weeks; use a lean Gantt for milestones.

**Analysis heuristics before "big guns"** [CJ]: Occam's razor, order of magnitude (what's 10% on price vs. cost vs. volume worth?), 80/20, Rule of 72 (72 / growth% = years to double), S-curve adoption, expected value.

---

## 5. Case frameworks (when to use + checklist)

| Question | Framework |
|---|---|
| Why are profits down? | Profitability tree |
| How big is the market? | Market sizing |
| Should we enter market Y? | Market entry |
| Should we acquire X? | M&A |
| What price? | Pricing |
| How do we grow? | Ansoff |
| What's our position? | 3C, Porter, SWOT |
| Improve operations? | Value chain, Lean |
(Selection table from [YO].)

### Profitability [YO][SP]
Profit = Revenue − Costs. Revenue = Price × Volume, where Volume = customers × frequency × units per purchase. Costs = Fixed + Variable.
- [ ] Price or volume problem? All products/regions, or specific ones? When did it start, and what changed? What are competitors doing?
- [ ] Costs rising in absolute terms or as % of revenue? Which category is fastest? Benchmarked against peers?
- [ ] Go one level deeper than feels necessary. Revenue isn't the answer, P × V is, and price means mix-adjusted price [SP].
- Table: last year / this year / change / benchmark for each line.
- **DuPont** [SP]: ROE = margin × asset turnover × leverage. It shows *how* returns are made (luxury = margin, grocery = turns, banks = leverage).

### Market entry [YO][GC][AV]
Tree: **Market attractiveness** (size, growth, profitability, intensity, barriers) · **Company fit** (capabilities, leverageable assets, strategy, risk appetite) · **Entry mode** · **Implementation** (investment, timeline, success factors, exit criteria).
- Entry modes: organic (high investment, full control, slow) · acquisition (very high investment, full control, fast) · JV (medium, shared control) · licensing/franchising (low investment, low/medium control, fast) [YO].
- Go/No-Go thresholds (illustrative values from [YO]): size >$500M, growth >5%, margin >15%, achievable share >10%, payback <5 yrs, NPV >$50M.
- Barriers: scale, capital, switching costs, distribution access, regulation, brand loyalty.
- Must-have frameworks [AV]: Five Forces, PESTLE, industry life cycle, plus CAGE if international.

### Growth: Ansoff [GC][YO]
Penetration (existing product × existing market) → market development → product development → diversification, in order of rising risk.
- Use when "we need to grow" and options compete.
- Mistakes: chasing all four quadrants; under-exploiting penetration (usually the highest ROI, so exhaust it first); treating related and unrelated diversification as equally risky.
- Breaks down: platforms, blurry new/existing boundaries, brand-elasticity risk.
- Sequence: Ansoff → Three Horizons → BCG [GC].

### M&A [YO][AB]
Tree: **strategic rationale** (why buy vs. build vs. partner) · **target attractiveness** · **synergies** (revenue: harder, 2–3 yrs; cost: easier, 1–2 yrs) · **risks** (integration, culture, key people, hidden liabilities) · **valuation**.
- **Value created = Synergies − Premium paid − Integration costs.** Example: $30M − $20M − $5M = $5M [YO].
- Due diligence areas: financial, commercial (customer concentration, contracts), operational, legal, HR, tax.
- Valuation: trading comps, precedent transactions, DCF, LBO.
- Thesis types [AB]: market entry, capability, customers, scale, vertical integration, acqui-hire, defensive. Always test against build, partner/JV and license.

### Pricing [YO]
Three anchors: **cost-plus** (commodities/contracts) · **value-based** (differentiated) · **competitive** (undifferentiated).
- Value-based: Customer value = reference value (best alternative) + differentiation value; Price = value × capture %.
- Elasticity = %ΔQ / %ΔP. If >1, demand is elastic (a price cut raises revenue); if <1, a price rise raises revenue.
- Low price sensitivity when: the product is unique, switching costs are high, it's a small share of total cost, someone else pays, prestige matters, or prices are hard to compare.

---

## 6. Strategy frameworks: when to use, and when they break [GC unless noted]

| Framework | Use when | Watch out / breaks down |
|---|---|---|
| **Porter's Five Forces** | Is the industry structurally attractive? First move for entry or positioning. Score each force 1–5, where higher = worse for profitability [YO] | Wrong industry definition; using it for *internal* strengths; ratings that don't lead to moves. Breaks for platforms, hyper-dynamic or co-opetition industries, and where regulation/macro forces dominate |
| **3C** (Ohmae) [YO] | Positioning: Customer (needs, buying process), Competitor (strategy, likely response), Company (competences, cost position) | The goal is where company capability meets customer need better than competitors, sustainably |
| **4P / 7P** [YO] | Tactical marketing mix: Product, Price, Place, Promotion (+ People, Process, Physical evidence for services) | Tactical, not strategy |
| **Value chain** (Porter) | Where value is created and cost piles up; invest / outsource / redesign. Use after Five Forces | Useless without activity-level cost data; ignores linkages; not the same as a customer journey. Weak for platforms, asset-light and service businesses |
| **McKinsey 7S** | Strategy is set but execution won't align (transformation, PMI). Hard: Strategy, Structure, Systems. Soft: Shared values, Style, Staff, Skills | Listing the S's without finding misalignments; ignoring the soft S's. Breaks if the strategy itself is wrong, at startups under 50 people, or in a crisis |
| **BCG growth-share** | Capital allocation across 4+ business units (Stars invest / Cows harvest / ? pick and fund / Dogs divest) | The vertical axis is *market* growth, not your growth; don't spread money thinly across question marks. Breaks where share doesn't drive profit (luxury, software, network effects) |
| **GE-McKinsey 9-box** | Portfolio decisions needing multi-factor attractiveness × strength | Arbitrary weights (run sensitivity), self-scoring inflation, politics |
| **PESTEL** [YO] | Macro scan: Political, Economic, Social, Technological, Environmental, Legal. Rate impact H/M/L and tag each item O or T | Feeds the O/T side of SWOT |
| **SWOT → TOWS** [YO] | Pull together internal (S/W) and external (O/T) | SWOT alone isn't strategy. Convert via TOWS: **SO** use strengths to capture opportunities · **WO** fix weaknesses by pursuing opportunities · **ST** use strengths to blunt threats · **WT** minimize weaknesses and avoid threats |
| **VRIO** | Which resources are real sustainable advantages (Valuable, Rare, Inimitable, Organized) | Rating everything "yes"; ignoring the O; static view (ask how long the advantage lasts) |
| **Three Horizons** | Balance today's earnings against future bets | H1 starves H2/H3 (ring-fence the budget); define horizons by business-model maturity, not calendar time |
| **Blue Ocean (ERRC)** | Price wars or converged differentiation; unlock non-customers | ERRC must move budget (cuts in Eliminate/Reduce fund Raise/Create); don't only raise and create; premium pricing defeats the purpose |
| **Scenario planning** | Irreversible, high-capital decisions on a 5–15 yr horizon | Scenarios built around the preferred future; low/mid/high variants instead of genuinely different worlds; no actions coming out of it |

**Chains** [GC]: attractiveness = Five Forces → Value chain → VRIO · growth = Ansoff → 3 Horizons → BCG · execution = Value chain → 7S → 9-box · repositioning = Five Forces → Blue Ocean → Value chain.

**Framework hygiene** [SP]: choose by problem, not by familiarity; always customize; hypothesis first; synthesize rather than describe ("barriers are collapsing, so the 22% margin isn't defensible", not "the five forces suggest…"); scrap a framework that isn't working. The client sees the building, not the scaffolding.

---

## 7. Market sizing

**TAM** (100% share) → **SAM** (what your product, geography and segment can serve) → **SOM** (realistic 3–5 yr capture, often 2–5% of SAM for a new entrant) [DD].

| Method | Formula | Best for |
|---|---|---|
| Top-down | Total category × geo % × segment % | Mature markets with research reports |
| Bottom-up | Σ(segment count × annual revenue per customer) × penetration | B2B, niche; most credible to investors |
| Value theory | Problem cost × % solved × willingness-to-pay (10–30% of value) × customers | New categories [DD] |

Structures [YO]: consumer = population × usage × price · B2B = number of companies × adoption × spend · physical = locations × items per location · services = users × frequency × price.

**Guesstimate process** [DI]: (1) fix scope (geo, period, segment); (2) decompose; (3) estimate each piece from anchors (US ~330–340M people, ~130M households, 2.5 per household; ~250 working days; ~2,000 work hours per year); (4) sanity-check with a second decomposition. Give a range ("~$200M, $150–300M"), not false precision.

**Worked example: NYC coffee (both methods)** [YO]
- *Top-down:* 8M people × 75% adults × 60% coffee drinkers × 40% buy out = 1.44M buyers × 3 cups/wk × $4 = $17.3M/wk, about **$0.9B/yr**.
- *Bottom-up:* ~3,000 shops × 200 customers/day × $5 × 350 days, about **$1.05B/yr**.
- The two are ~15% apart, so the answer is ~$0.9–1.05B. Per [SP], the gap tells you which assumptions to challenge.

**Worked example: AI email SaaS, North America** [DD]
- Bottom-up TAM: 85k small × $3.6k + 18k mid × $9.6k + 2.5k enterprise × $24k = **$539M**.
- SAM = 539 × 45% AI-ready × 70% switchable = **$169M**.
- SOM = 2.5% (yr 3) → $4.2M ARR; 5% (yr 5) → $8.5M ARR (~888 customers).
- Top-down check: $7.5B global × 40% NA × 25% e-commerce × 65% $1M+ = $488M TAM; × 35% AI = $171M SAM. The TAM variance is ~10% and SAM ~1%, so confidence is high.
- Further checks: public comps (Klaviyo revenue ~$700M) and customer-count plausibility.

---

## 8. Financial checks [YO unless noted]

- **NPV** = Σ CF_t/(1+r)^t − I₀. Accept if >0. Example: −100k, then 30/35/40/45k at 10% gives **NPV ≈ +$17k**. NPV is the gold standard and the right tool for mutually exclusive projects.
- **IRR**: the rate at which NPV = 0. Accept if above the hurdle (e.g. 15% vs. 10% WACC). Caveats: assumes reinvestment at the IRR, can have multiple values with odd cash flows, ignores scale.
- **Payback** = investment / annual CF (100k/25k = 4 yrs). With uneven flows, interpolate (e.g. 3.2 yrs). Ignores everything after payback; use discounted payback for rigor.
- **ROI** = net benefit / cost. Simple, but no time value. Use as a supplement only.
- **Break-even units** = Fixed / (P − VC). Break-even revenue = Fixed / CM ratio. Example: $50k / ($100 − $60) = **1,250 units/month = $125k/month**.
- **Unit economics**: CAC = fully loaded S&M / new customers. LTV = ARPU × GM% / churn. Lifetime = 1/churn. CAC payback = CAC / (ARPU × GM%). Example: $50 ARPU, 70% GM, 4% churn, CAC $200 gives LTV $875, **LTV:CAC 4.4×, payback 5.7 months**. Cutting churn to 3% lifts LTV ~33%.
  - Rules of thumb: LTV:CAC ≥3× (well above 3× may mean under-investment); payback <12 months [YO] or <18 months [SP][AV]; monthly SaaS churn <2%, with >5% a warning. Segment by channel or cohort before averaging. **Rule of 40**: growth % + EBITDA % > 40 [SP].
- **DCF** [SP][AV]: FCF = EBIT(1−t) + D&A − CapEx − ΔNWC. TV = FCF_n(1+g)/(WACC−g) or an exit multiple. WACC = E/V·Ke + D/V·Kd(1−t), with Ke via CAPM. Always build a WACC × g sensitivity grid.
- **Sensitivity**: one-way ±10/20% tables, a tornado chart, and scenarios weighted to an expected NPV (e.g. 20% × 2.5 + 60% × 1.0 + 20% × −0.5 = $1.0M).
- **Model by case type** [AV]: valuation = DCF + comps · entry/business case = 5-yr P&L + break-even · SaaS = LTV/CAC + ARR · M&A = DCF + synergies + accretion/dilution · capex = NPV/IRR + payback · turnaround = P&L bridge + working capital.

---

## 9. Synthesis and storytelling

**Summary vs. synthesis** [SR]: summary compresses; synthesis names the pattern and forces an implication. Test: *does it change what the reader does?*
1. Cluster inductively, letting themes emerge.
2. Force-rank to **3 insights** by frequency × severity × surprise.
3. Write each as a **claim**, not a topic ("Mid-market buyers cap at $50K, their no-approval threshold", not "Pricing concerns").
4. Add 2–3 specific evidence bullets (quotes, numbers, sources).
5. Write the so-what: "Because this is true, the reader should ___."
6. Anti-summary check. Expect to throw away ~80% of the raw input.

**So-What test** [CG]: Process → Result → **Insight**, ending in an action specific enough to assign to a person with a deadline.

**Pyramid Principle** (Minto) [CG][GC][AB]: answer first, then 3–5 supporting arguments that are MECE under the answer, then 2–4 pieces of evidence each, also MECE.
- [ ] Top line is one sentence, specific and actionable, with no hedging
- [ ] Arguments are full thoughts ("CS activity dropped, causing 30% of the cycle increase"), not topics
- [ ] Evidence is numbers or named instances, not "the team thinks"
- [ ] Grouping is either *deductive* (premise → premise → therefore) or *inductive* (parallel reasons) [AB]
- Think bottom-up, present top-down. Using the pyramid *during* analysis invites confirmation bias [GC].

**Output contract for a recommendation** [GC]: **Bottom line** · ≤3 supporting arguments with [F/I/A/E] evidence · **Risks** (≥2, each with likelihood/impact/mitigation) · **Kill conditions** (≥2: "if X is observed, the recommendation flips to Y") · **Next actions** (owner, deadline, metric) · Open questions. Then argue against yourself: the strongest counter-case, and the assumption that would reverse the answer.

**Logic hygiene** [DI]: check logic and evidence separately; never present inductive findings as deductive certainty; don't mistake a *necessary* condition (customer interest) for a *sufficient* one (interest + differentiation + model + execution); watch for post-hoc causation and false dichotomies (there's often a $20M option between $0 and $50M).

---

## Sources
Star counts are from the GitHub API at fetch time (Nov 2026). All files were read via raw.githubusercontent.com.

1. **gcamilo/management-consulting** ★119: https://github.com/gcamilo/management-consulting (SKILL.md; references/frameworks-problem-solving, -strategy, -financial, -pricing; variants/market-entry; examples/issue-tree-good-vs-bad)
2. **yoichiojima-2/consultant** ★60: https://github.com/yoichiojima-2/consultant (skills/consulting/problem-solving, strategy, finance, cases)
3. **ConrayGambit/Strategy-Consultant-5-Consulting-Frameworks** ★32: https://github.com/ConrayGambit/Strategy-Consultant-5-Consulting-Frameworks (README; prompts/mece-framework, issue-trees, hypothesis-driven, pareto-principle, pyramid-principle)
4. **chefjefff/mckinsey-problem-solving** ★20: https://github.com/chefjefff/mckinsey-problem-solving (skills/problem-solving/SKILL.md, based on Conn & McLean, *Bulletproof Problem Solving*)
5. **spacemata/-mbb-management-consultant-claude-skill** ★9: https://github.com/spacemata/-mbb-management-consultant-claude-skill (FRAMEWORKS.md; skill/references/guesstimation, case-types)
6. **DogInfantry/claude-skill-management-consultant-B1** ★160: https://github.com/DogInfantry/claude-skill-management-consultant-B1 (skill/references/frameworks, issue-hypothesis-trees, logic-and-synthesis, guesstimation). Note: its guesstimation file is byte-identical in size to spacemata's and the frameworks files are near-identical, so one likely derives from the other.
7. **sruthir28/enterprise-ai-skills** ★159: https://github.com/sruthir28/enterprise-ai-skills (issue-tree-builder, hypothesis-tree, prioritization, scpr-framework, synthesis)
8. **averma416/consulting-gauntlet** ★35: https://github.com/averma416/consulting-gauntlet (SKILL.md; references/frameworks, financial-models)
9. **abinauv/business-consulting** ★34: https://github.com/abinauv/business-consulting (README; skills/financial-analysis; deliverable-creation/references/pyramid-principle-deep-dive; commands/market-entry, ma-assessment)
10. **didixuxu/didi-skills** ★86: https://github.com/didixuxu/didi-skills (market-sizing-analysis/SKILL.md; examples/saas-market-sizing.md)

Caveat: thresholds such as Go/No-Go cut-offs, LTV:CAC ≥3× and payback limits are rules of thumb taken from these repos, not universal standards. Where repos disagree (e.g. payback <12 vs. <18 months), both are shown.
