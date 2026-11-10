---
name: tech-project-delivery
description: Use when planning, pricing or documenting tech builds.
version: 1.0.0
author: Hermes (for Nicky)
license: MIT
metadata:
  hermes:
    tags: [project-management, product-management, system-architecture, PRD, ERD, pricing, RACI, client-documents]
    related_skills: [business-case-competition, docx, pdf, xlsx, powerpoint]
---

# Tech Project Delivery: PM, Architecture, Client Docs, Pricing

End-to-end playbook for running and selling software projects (Indonesian clients, Rupiah). Built 8 Nov 2026 from top GitHub repos (system-design-primer 377k★, system-design-101 91k★, mermaid 91k★, google/eng-practices 23k★, ADR 17k★, engineeringladders 8.5k★), company handbooks (GitLab, Basecamp Shape Up, Amazon PR/FAQ, Google design docs, Atlassian), Scrum Guide 2020, DORA 2024, Michael Page 2025 salaries, INKINDO 2026, and local agency pricing. Reply to the user in Indonesian, beginner-friendly.

## When to Use
- A client wants to buy or build a system: discovery, proposal/quote, PRD, SRS, ERD, architecture, SOW/contract, UAT/BAST, SLA.
- Planning or running a tech project: method choice, sprint/rituals, RACI, risk, status reports, launch.
- Designing system architecture, or estimating cost and price per module/role.

## References (load the one you need)
- `references/01-pm-methods-and-company-workflows.md`: method chooser; PMBOK 7, Scrum, Kanban, Shape Up, Lean, OKRs; how Amazon, Google, GitLab, Atlassian and Basecamp work; metrics (DORA, flow); estimation; RAID, status report and change control templates; **11-phase lifecycle with gates and owners** (pre-sales to closure, incl. BAST, termin and Lebaran freeze).
- `references/02-system-architecture.md`: 10-step architecture process, NFR scenarios, C4/Mermaid/PlantUML/Structurizr diagrams as text, ADRs, modular monolith first, data modeling (DBML + Mermaid ERD), REST/OpenAPI, Midtrans/Xendit webhooks, OWASP Top 10:2025 + UU PDP, **6 reference architectures** (company profile, e-commerce, ERP/POS, multi-tenant SaaS, RAG assistant like Lumii, mobile + backend), stacks by budget, scaling, cost.
- `references/03-client-document-templates.md`: **15 fill-in templates** in Indonesian: proposal, discovery questionnaire, PRD (Gherkin), SRS, tech design (arc42-lite), ERD + data dictionary, OpenAPI, UI/UX sign-off, WBS/Gantt/RACI, SOW/contract (17 articles: IP per UU 28/2014 Ps 36, UU PDP, bahasa, meterai, PPN/PPh 23), change request, test plan/UAT/BAST, SLA, handover, status report/minutes.
- `references/04-pricing-and-financials.md`: rates for 14 roles × seniority, salary to day-rate formulas, **26 module price ranges**, estimation methods (WBS, PERT, story points, FP, COCOMO), pricing models, payment terms, maintenance, third-party running costs, tax (PPN 12% × 11/12, PPh 23 2%), quote template.
- `references/05-roles-raci-team.md`: 30 role cards (mission, deliverables per phase, KPIs, seniority L1–L7, failure modes, AI assist), master RACI, team setups for 2–3, 5–8, 10–20 and 30+ people, sprint calendar, DoR/DoD, quality gates G0–G8.

## Calculator
`scripts/estimate_project.py` (stdlib Python). Input is JSON with modules, roles, days, rates and options; see `scripts/sample_project.json`. Output covers cost per role/module, contingency, margin, discount, PPN, PPh 23 withholding, payment schedule and maintenance, in Rupiah, as markdown or `--json`. Always price with it; never do the math mentally.
```
python scripts/estimate_project.py scripts/sample_project.json
```

## Workflow for a client project
1. **Discovery**: send the discovery questionnaire (ref 03 §2). Capture goals, users, scope in/out, NFRs, budget, deadline and data sensitivity (UU PDP).
2. **Shape and estimate**: build the WBS per module (ref 04), use PERT for uncertain items, add contingency, then run the calculator. Pick a pricing model (fixed vs T&M vs retainer).
3. **Proposal and quote**: use ref 03 §1 with the calculator output. Use payment termin tied to gates.
4. **PRD + architecture**: write the PRD, then the tech design with C4 diagrams, ADRs, ERD (DBML/Mermaid) and the OpenAPI skeleton (ref 02 and 03).
5. **Contract/SOW**: use ref 03 §10. Make IP transfer, warranty, change requests and data protection explicit. Have it checked by a lawyer and a tax consultant (the `pajak` profile can help).
6. **Delivery**: choose the method (ref 01), assign RACI (ref 05), set the sprint cadence, use RAID and weekly status reports, and route change requests through the form.
7. **QA → UAT → BAST → launch → hypercare → SLA/maintenance** with gate checklists (ref 01 lifecycle, ref 05 gates).
8. **Deliverables**: produce the documents as DOCX/PDF via the docx/pdf skills. Render diagrams from Mermaid and show them in the preview pane.

## Pitfalls
- Items marked [E] in ref 04 are estimates, not sourced figures. Present them as ranges and update the USD rate (JISDOR) before quoting in USD.
- Commissioned software IP stays with the maker unless the contract transfers it (UU 28/2014 Ps 36). Always write the transfer in.
- PPN applies only if the vendor is PKP. The client withholds PPh 23 at 2% (4% without NPWP). Confirm with a tax consultant.
- Stripe/Shopify/Meta practice notes in ref 01 were not live-verified, so check them before quoting.
- Default to a modular monolith. Split services only when at least 2 of the 5 conditions in ref 02 hold.
