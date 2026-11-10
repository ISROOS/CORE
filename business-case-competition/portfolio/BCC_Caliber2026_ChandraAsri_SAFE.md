# BCC / Hackathon: CALIBER 2026, Case 1 (Manufacturing Knowledge Hub) x Chandra Asri: "SAFE!"

## Competition & type
- **Type:** BCC-hackathon hybrid. Case 1 asks for an AI-enabled Manufacturing Knowledge Hub for Chandra Asri, a petrochemical company. The deliverable is a **pitch deck plus a working prototype** (the deck mentions a product video and a deployed app).
- **Team:** Wijaya Team, BINUS University: Nicky Gilbert (Project Lead & Data), Michaella Siman (UI/UX & Visual Design), Michael Wijaya (AI & Prototype Engineer). The team slide also names a coach.
- **Result:** the folder tag is **[Preliminary]**, so the team competed in the preliminary round and **did not advance** beyond it (the reading of tags given in the brief).
- **File:** `CALIBER 2026 – SAFE! Chandra Asri Knowledge Hub_compressed.pdf`

## Document type & format
- 54 slides, **16:9 landscape** (960×540 pt).
- The PDF is "compressed": every page is a single raster image with an invisible OCR text layer (fonts report only Helvetica), so typefaces were judged visually. They look like a geometric sans (Poppins-like) for headings and an Inter/Roboto-like sans for body text.
- Structure: cover, then **5 main content slides** (Background, Solution, Impact, Roadmap, Conclusion), a team profile, an Appendix divider, and **46 appendix slides** including references. Slide numbers restart at 1 after the cover.

## Section-by-section outline
- **S1 Cover:** "SAFE! Chandra Asri Knowledge Hub", orange subtitle "From Knowledge Hub to Execution Assurance". The pillar sentence has the first letter of each pillar coloured (**S**tructured Industrial Data Ops, **A**I-Verified Answers…, **F**ailure Memory…, **E**mbedded…). There are 3 framed team photos and a photo of a Chandra Asri refinery with a white fade on the right half.
- **S2 Background & Problem Statement:** action title "Scattered knowledge leads to improper execution, and the plant pays in downtime and cost". It runs Situation → Problem (4 reasons tagged KQ1–KQ3) → concrete example ("pump GA-1201A alarms at 02:00", with the answer spread over five places) → cost (434 h downtime, Rp537.8M maintenance cost, 82% unplanned). A right-hand panel holds the problem statement and the 3 key questions mapped to evidence.
- **S3 Solution:** "SAFE! turns 97 scattered files into approved knowledge that answers, guides execution and learns". It is a four-column pillar grid with Result callouts, then a Strategy row and an Impact row, and a governance banner across all four pillars.
- **S4 Business Impact:** "We measure SAFE! by how well work is executed, and every impact assumption is shown". On the left, a pilot KPI table (baseline → target). On the right, impact calculation cards (≈35 h downtime avoided/yr, ≈Rp21M repeat cost/yr, ≈2,400 engineer hours/yr) each with its formula, plus a note that the percentages are team assumptions.
- **S5 Feasibility & Roadmap:** a Gantt by pillar across Phase 0 Prototype → Phase 1 Pilot (1 unit) → Phase 2 Operations → Phase 3 Plant-wide, with gates, and a readiness grid (technical, cybersecurity, data governance, legal, organizational, etc.).
- **S6 Conclusion:** "SAFE! closes the gap between knowing and doing". It has background stats, the problem statement, a closed-loop knowledge system (Collect → Check → Ask → Answer → Act → Learn), the expected pilot impact and the call to action "a Phase 1 pilot on one unit".
- **S7 Team Profile:** roles, contributions, background, and a "How we work" process strip (audit of 97 files/211 WOs → design 4 pillars → build prototype → validate on 30 questions).
- **S8 Appendix divider:** with a table of contents.
- **Appendix slides 9–54:**
  - Company background and problem scope.
  - Issue tree (objective → KQ → sub-issue evidence → implication).
  - Prototype tour, one screen per slide with numbered callouts 1–4 (Use / Impact): overview dashboard, upload pipeline, review queue, assistant, management overview, execution copilot, Tag 360.
  - "Why S/A/F/E" data proofs: the equipment tag links 7/7 sources; one trip question needs 6 source types; corrective work is 25% of WOs but 56% of cost; 36 trips and 29 permissives.
  - Coverage of CALIBER needs (5 full, 1 partial); generic RAG chatbot vs SAFE!; option scoring (/20).
  - SWOT/TOWS.
  - Bronze/Silver/Gold pipeline; decision flow; 10-step incident walk-through; S0–S11 architecture; deployment stack (Next.js/Vercel, FastAPI on AWS EC2, Supabase pgvector, Ollama Qwen3 embeddings); data model; 9 design decisions.
  - 10 validation rules; tiered approval; Q&A 9 steps; trust layer; security and user limits; ISO/IEC 27001/27002/27005/27701 mapping; 6 roles.
  - Failure-memory timeline for GA-1201A; knowledge loop; copilot loop.
  - **Quality test:** 28/30 passed, 100% on safety checks, with the 30 questions listed, 7 findings plus fixes, and the 2 failures analysed.
  - Financial baseline per asset; low/base/high sensitivity; 2027–2029 forecast; cost drivers and break-even; risk register; FAQ (10 questions); references.

## Storyline / argument pattern
- **Hook:** a concrete 2 a.m. incident ("pump GA-1201A alarms at 02:00") showing that the knowledge needed sits in 5 places. This is followed by quantified pain from the baseline dataset (434 h downtime, Rp537.8M, 82% unplanned, 13 problems with no OPL).
- **Reframe:** this is not a search problem but an *execution* problem. "From Knowledge Hub to Execution Assurance"; "measure by how well work is executed, not search".
- **Solution naming:** **SAFE!** = Structured Industrial Data Ops / AI-Verified Answers / Failure Memory & Recommendation / Embedded in Operations. The acronym is a safety word that fits a petrochemical client, and the "!" matches the house style used in FLOW!.
- **Proof over promise:** a built prototype run on the actual case dataset (97 files, 211 WOs) and an evaluation set of 30 known-answer questions. The two failures are disclosed with root cause and fix.
- **Coverage mapping:** an explicit table showing how SAFE! meets each of the 6 CALIBER expected solutions (5 full, 1 partial, honestly flagged), with deck page references.
- **Close:** "closes the gap between knowing and doing", with a single concrete ask (a Phase 1 pilot on one unit).

## Frameworks & analyses used
SCQ-style situation/problem; key questions (KQ1–3) from the case; issue tree; option scoring matrix (Trust/Safety/Speed/Feasibility /20); SWOT → TOWS; competitive comparison vs a generic RAG chatbot; medallion data architecture (Bronze/Silver/Gold); RACI-like role and access matrix; ISO/IEC 27000 mapping; phased gated roadmap; readiness assessment; KPI baseline→target; low/base/high sensitivity; 3-year forecast by rollout coverage; risk-mitigation register; FAQ / pre-emptive Q&A; model evaluation (accuracy, citation correctness, refusal rate, latency p50/p90).

## How numbers are handled
- **Baseline numbers come from the case dataset, computed by the team** (per-asset WOs, breakdowns, downtime hours, cost; 75.5% of cost is corrective plus overhaul; data completeness 88% = 185/211).
- **Impact formulas are shown on the slide:** e.g., 289 h/yr × 30% × 40% ≈ 35 h; Rp358M/yr × 20% × 30% ≈ Rp21M; 30 engineers × 5 searches/wk × 20 min × 48 wk ≈ 2,400 h. Percentages are labelled "team assumptions, validated in the pilot".
- **Safety value is explicitly "not monetized".**
- Low/base/high cases and a forecast scaled by assets covered (40 → 120 → 400 assets).
- **The financial magnitude is small** (tens of millions of rupiah on 8 sample assets). There is no NPV headline; cost is described by drivers rather than a full rupiah budget.
- Source footers on every slide use bracketed source codes ([T1] team prototype, [T2] team analysis, [T5] test results) plus case documents.

## Visual design system
- **Palette (sampled + visual):** royal/navy blue `#2F4A8D` (header bars, pillar badges, primary), pale blue fills `#EAF0F9` / `#F5F7FE`, near-white background `#F9FDFF`, grey-blue `#B5BECB` for lines and the inactive nav. **Orange** (~`#E8892B`) accents the "!" in SAFE!, the subtitle and callout borders. Green and red are used for pass/fail and severity.
- **Typography:** bold geometric sans for action titles (2 lines, left-aligned, dark navy); a small all-caps blue section kicker above the title ("SAFE! SOLUTION FOR CASE 1"); clean sans body at fairly small size.
- **Slide chrome:** kicker plus action title at top left; the "SAFE! / Chandra Asri Knowledge Hub" logo lockup at top right; a bottom **navigation bar** (BACKGROUND · SOLUTION · IMPACT · ROADMAP · CONCLUSION · APPENDIX) with the current section highlighted; slide number in a blue square bottom right; a source line above the nav.
- **Layout:** dense consulting-grade grids with two-panel splits (problem | statement, KPIs | impact calc), four-column pillar grids with row labels rotated vertically ("Strategy", "Impact"), and a dashed vertical divider with an arrow connector between panels.
- **Components:** letter badges (S/A/F/E in navy circles); lightbulb "Result:" callouts; big-number impact cards (navy block with white number + formula on white); orange-left-border assumption notes; status pills (Built/Planned, Pass/Fail, High/Medium); numbered screenshot callouts (1–4) with "Use / Impact" lines; per-category square-grid test results; timeline cards; system architecture boxes.
- **Imagery:** a real refinery photo on the cover only; everything else is UI screenshots, tables and diagrams. Icons are minimal outline icons.
- **Density:** very high. Many slides are full tables or text grids that read like a document rather than a presentation.

## Strengths
- A real, working prototype on the case dataset, with an evaluation harness (28/30, 100% on safety). This is rare and highly credible in a hackathon.
- Excellent domain specificity (equipment tags, SIL, 1oo2 voting, OPLs, hold points, MOC) and a single recurring incident (GA-1201A).
- Honest disclosure: failures, partial coverage, "not monetized", and assumptions labelled.
- Strong governance and trust story (citations with document number, revision and approval status; refusal of unsafe requests; RLS; ISO mapping) for a safety-critical client.
- A good navigation system and action titles make a 54-slide deck navigable.

## Weaknesses / what a judge would criticize (did not advance)
- **The business case is thin:** quantified value is about Rp21M/yr and 35 h downtime on 8 assets, with no headline NPV/ROI. That is weak against the effort and cost of an enterprise AI platform, and judges may see a tech demo rather than a business case.
- **Too technical and too dense for a pitch:** the appendix reads as an engineering spec (pipeline stages, rerank weights, embedding models). The 5 main slides are crammed with small text.
- Raster-compressed PDF: text is not selectable or crisp, and readability suffers at small sizes.
- The impact percentages (30%, 40%, 20%…) are pure team assumptions without external benchmarks, unlike the Toyota and IBSC entries, which cited published results.
- Limited market/strategic framing (why now, value to Chandra Asri's P&L at plant scale). The scale-up value only appears in the forecast appendix.
- 46 appendix slides against 5 main slides shows heavy effort, but judges score the core.

## Reusable patterns
- Open with a timestamped real incident ("pump GA-1201A alarms at 02:00") that shows the problem physically.
- Use an action-title deck with a small caps section kicker plus a 2-line headline, and keep a bottom section navigator with the current section highlighted.
- Build a four-column pillar grid: badge + name, then bullets, then a "Result:" callout, then rotated-label rows for "Strategy" and "Impact".
- Use impact cards that show the number and its formula side by side, plus a visible "All percentages are team assumptions" note.
- Add a "Coverage of the case's expected solutions" table (Full/Partial + page refs), which helps judges tick rubric boxes.
- For tech or AI solutions, include a proof slide: a known-answer test set, pass rate, safety checks, failures analysed and fixes. Disclose failures.
- Compare the solution against the obvious generic alternative ("Generic RAG chatbot vs SAFE!").
- Do a prototype tour, one screen per slide, with numbered callouts each giving "Use" and "Impact".
- Add an FAQ slide that pre-empts judges' questions.
- **Lesson from not advancing:** pair technical proof with a rupiah business case at plant scale (NPV/payback, benchmarked rates), and keep the main deck readable.
