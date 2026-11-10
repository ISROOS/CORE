---
name: business-case-competition
description: Use when doing case or marketing plan contests. Win.
version: 1.1.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [business-case, marketing-plan, competition, consulting, pitch-deck]
    related_skills: [powerpoint, docx, pdf, xlsx, claude-design]
---

# Business Case & Marketing Plan Competition

## When to Use
Use this for business case or marketing plan competitions: analysing a case, researching, writing the proposal/paper, building the deck, preparing for Q&A, or reworking the team's existing competition deliverables (including turning figures into HTML/CSS).

Workflow for helping a team (often Indonesian university students) win a business case competition (BCC) or marketing plan competition (MPC). Reply in Indonesian, plain language. Researched Nov 2026 from GitHub repos + official rulebooks. Details live in references/, so load the one you need instead of guessing.

## References (load on demand)
- `references/01-consulting-frameworks.md`: 7-step loop, SCQA, MECE/issue trees, hypothesis tests, prioritization, case frameworks (profitability, entry, Ansoff, M&A, pricing), strategy frameworks table, market sizing worked examples, NPV/IRR/break-even/unit economics, synthesis.
- `references/02-case-competition-playbook.md`: formats (JMSB ICC, HKUST ICC, UGM/ITS/HSBC ID), published rubric weights, winning deck spine, 3h/24h/48h time plans, team roles, mistakes, Q&A defence, Indonesia notes, final checklist.
- `references/03-marketing-plan-playbook.md`: MPC rubrics (DECA, Brandstorm, BINUS IMCB, FEB UI), SOSTAC/STP/AARRR/See-Think-Do-Care/PESO, 15-section proposal outline mapped to rubric, Indonesian digital data + KOL/KOC tiers, funnel metrics, ~18-slide deck, judge criticisms.
- `references/04-deck-storytelling-pitch.md`: Pyramid Principle, action titles, ghost deck, exec summary checklist, chart cheat-sheet, 14-slide template, delivery, 30 likely judge questions.
- `references/05-wijaya-team-patterns.md`: **read first for any new competition.** The user's own 13 past entries (results map with 1st/2nd/3rd/SF), house style (acronym pillars, issue chain, human hook, appendix-heavy, formulas + gates), what separated podium entries, recurring mistakes QA list, and visual signatures. Per-entry detail is in `references/portfolio/*.md`.
- `references/06-proposal-design-system.md`: design playbook from GitHub repos (huashu-report, mckinsey-style-visualization, Mck-ppt-design, anthropics/skills, flight-check) + local skills. Covers A4 grid, type scale, font pairings, palettes, 16 components, chart rules, print CSS for HTML->PDF and 16:9, judge-visible design mistakes.
- When the user sends OTHER teams' winning entries: analyze them with the same template as portfolio/*.md, save to `references/portfolio/others_<comp>.md`, and update 05 with the patterns that differ from the house style. Check first whether a file is an entry at all: organiser case briefs and rubric PDFs show up in such ZIPs, and they are even more valuable as a statement of what judges want.

- `references/figure-to-html.md`: recreate figures and covers from the team's proposal/deck PDF as editable HTML/CSS, export them back to PDF, and show them in the preview pane (render crops, transcribe, CSS-variable template, cover asset cropping, browser verification, printToPDF).
- `references/analyzing-competition-pdfs.md`: procedure when the user sends a ZIP of proposals (own, other teams' winners, or public winners) to learn from: subagent fan-out by competition type, shared setup block, per-entry analysis template, merging into 05/portfolio, verification tags for public finds.

`assets/sources/`: raw text of rulebooks/rubrics fetched (BACC-2022 winning report + rubric, HKUST ICC, Brandstorm, HSBC ID, etc.); use it to verify a claim.

## Workflow
1. **Read the rulebook first.** Get format, page/slide caps, deadline, rubric weights, AI-use rules. Breaking format rules loses points (HKUST scores over-limit decks "1"). If AI is restricted, act as sparring partner only.
2. **Profile the judges** (once the judges or sponsor reps are announced; earlier, use the sponsor's executives and past juries). Use public sources only: LinkedIn headline and posts, interviews, talks, articles, the company's annual report and CEO letter, past winning entries of the same competition, and the guidebook's emphasis. For each judge write a card: background (consulting/finance/marketing/tech/ops/academic), current priorities and the words they use, pet frameworks, likely Q&A angle, and what would bore or annoy them. Then adapt framing, vocabulary, the depth of each section, which numbers to lead with, and assign Q&A owners per judge. Never contact or lobby judges, and never invent facts to please them. The rubric still wins over preferences.
3. **Define the problem.** One SMART question plus SCQ. Find the root cause, not just the symptoms.
4. **Structure.** Use a MECE issue tree, form a hypothesis on day 1, then test it with data. Use frameworks as tools, never as slide filler.
5. **Research.** Use real cited data (BPS, DataReportal, company reports). State every assumption explicitly.
6. **Quantify.** Size the market (top-down plus bottom-up cross-check), then run financials (cost, revenue, NPV/payback/ROI) and a sensitivity analysis. Compute in Python/Excel, never mentally.
7. **Recommend + implement.** Most rubric weight goes here (JMSB: Implementation x3, Recommendation x2.5). Include a roadmap with phases, owners and budget, KPIs, and risks with mitigation and kill conditions.
8. **Storyline.** Answer first (Pyramid). Write a ghost deck of action titles, which must read as a story on their own, then build the exhibits.
9. **Deliverables.** Paper/proposal via docx/pdf skills, deck via powerpoint skill. One message per slide, a source line on every chart, and backup slides in the appendix.
10. **Q&A drill.** Rehearse with the 30 judge questions in ref 04 plus the per-judge angles from step 2. Answer with Answer, then Evidence, then Implication for the recommendation, then stop.
11. **Pre-submit QA gate (always).** Run the recurring-mistakes list in ref 05 against the exported file. Text-search the export for draft leftovers (`[`, `TODO`, `lengkapi`, `cek`, `---`). Check name and unit consistency. Recompute every KPI that appears more than once and confirm ROI uses profit, not revenue. Show the TAM/SAM/SOM derivation. Benchmark winners routinely lose points on numbers that don't reconcile, so getting these right is the clearest edge.

## Deliverable rules (always)
- Produce real files on disk (HTML/PDF/DOCX/PPTX/XLSX) in a per-competition folder next to the user's source file. Verify each one by rendering it before you report.
- Show every produced file in the side preview pane (`desktop_preview` open) and link it with `MEDIA:`. This user expects an artifact-panel experience.
- When PDF output is requested, generate it yourself (HTML then CDP `Page.printToPDF`). Don't tell the user to print it manually. For anything converted from the team's PDF, follow `references/figure-to-html.md`.
- One chat session per competition is the user's habit. When a new one starts, ask for the guidebook and the working folder, and use chat history search for earlier competitions only on request.

## Pitfalls
- Framework dumping (SWOT/PESTEL with no "so what") is the most common criticism.
- Ideas with no numbers, budget or timeline. Feasibility is scored everywhere.
- MPC: KPIs not tied to funnel/budget (CAC, ROAS, LTV:CAC >= 3:1); personas without data.
- Rules of thumb in refs (go/no-go thresholds, CAC payback) are heuristics. Label them as such.
- For deep research, fan out parallel subagents, one per topic, each writing a cited markdown file. Then merge their files into references/ instead of re-reading everything yourself.
- GitHub repo discovery: the unauthenticated search API allows about 10 searches/min, so sleep about 6s between queries. Keyword searches like "case competition" return spam repos (Bee Movie scripts, FTC robotics), so filter by description. When page extraction fails, fetch READMEs via raw.githubusercontent.com or curl.
