# 05 · Wijaya Team portfolio patterns (13 entries, analysed Nov 2026)

Source: user's own past entries (Wijaya Team / Bravie / BunTeam / Trio Kesasar, Binus: Nicky Gilbert, Michael Wijaya, Michaella Siman, Justin Bun, Richie Leo). Per-entry detail is in `portfolio/*.md`, and the design playbook is in `06-proposal-design-system.md`. Use this file first when starting a new competition. It records what this team already does well, what won, and what lost points.

## Results map
| Result | Entry | Type | Format |
|---|---|---|---|
| 🥇 1st | ITECHNO CUP 2026 – TukaKu (SIAP) | UI/UX | 22p proposal + 21-slide final |
| 🥈 2nd | UGM Career Insight × Blibli – TRUST! | MCC | 45-slide 16:9 (3 main + 41 appendix) |
| 🥉 3rd | UBM UAP IBPC 2026 – JELANTARA | BPC | 19-slide deck + 24p proposal |
| Final Top 4 | UNAIR IDSC × Tempat Tumbuh – FIT | MBCC | 32 slides (15 + 17 appx) |
| SF Top 7 | Genexpo × BI – JELANTRA | BPC | 28p proposal |
| Semifinal | M3C MTI × Toyota – FLOW! | BCC | prelim 43p → SF 64p A4 |
| Semifinal (#9/39 prelim) | DWDG IPB SEA BCC × Levner – PLAY! (team Budi Ayahku) | BCC | 4p exec summary + 22 appendix figures → SF 15p + infographic; judge analytics in `portfolio/BCC_DWDG-IPB-SEA-BCC2026_Levner_PLAY.md` |
| Semifinal | AIESEC Binus – Sleep4win | BPC (BMC round) | 6 slides |
| Semifinal | Dreamcareer – CAP with DEL | Mini case | 13 slides |
| Prelim only / unknown | IBSC (LOOP), Unilever (TRUE), Caliber (SAFE!), Telkom (RALLY), Study2Challenge (RISE) | — | — |

## House style (keep doing this, because it is what works)
1. **Branded acronym solution**, often ending in "!" (FLOW!, TRUST!, SAFE!, SIAP, FIT, LOOP, TRUE). Each letter is one pillar, and each pillar maps to one root cause, one KPI and one budget line.
2. **Issue chain on one page**: key question (SMART), then 3–6 problems, then 2–6 root causes, then pillars, with a priority strip. Dreamcareer's best page was this one.
3. **Human hook**: open with a persona or story that recurs throughout the document. Examples: Raka the Semarang student (Blibli), the 8-panel comic (ITECHNO 🥇, UBM 🥉), the timestamped incident at 02:00 (Caliber), the single missed sealer bead (Toyota).
4. **Thin main body, heavy appendix**: main slides or pages cite appendix numbers (A1–A41). Every appendix page opens with a bold "Takeaway:" line.
5. **Numbers with formulas**: every saving or revenue line shows its formula, a source and a "proposed/assumption" tag. Include downside/base/upside cases, a break-even point, sensitivity analysis and an assumption register.
6. **Pilot + stage gates + capital-at-risk**: release budget per gate and close with an explicit ask ("approve Rp30B, release Rp6B").
7. **Sponsor tie-in**: build in a feature that uses the sponsor's own asset (QRIS for BI, AI camera for Toyota, Blibli creators).
8. **Guardrails / "what we will NOT do"** slide, plus "what competitors can't copy".
9. **One-page infographic exec summary** in 5–6 numbered blocks.

## What separated podium from non-podium
- **Podium entries have internally consistent numbers.** UBM 🥉 reconciled capex/COGS/opex, ROI 38.7%, payback 4.28 years and NPV, where Genexpo (the same idea) had broken tables and only reached SF. Blibli 🥈 had unit economics, a 4×4 sensitivity grid and gated release.
- **Podium entries carry proof.** ITECHNO 🥇 showed usability metrics across two test rounds (SUS 62.5→85.8, misclicks 21.4%→9.5%) and repeated them everywhere.
- **Iteration works.** Re-entering an idea with fixed financials and a clearer story turned an SF into 3rd place (JELANTRA → JELANTARA). Toyota's SF version kept the same numbers but added reasoning, stress tests, feasibility, ADKAR and KPIs.

## Recurring mistakes (check before EVERY submission)
- **Draft leftovers**: "[lengkapi URL]", "KEY INSIGHTNYA LOH YAA", "ISII---", outline-only exec summaries. Run a text search over the export for `[`, `TODO`, `lengkapi`, `cek` and `---`.
- **Typos and inconsistent naming**: Backgroung, Statment, Monsterrat; JELANTRA vs JELANTARA; ton vs liter.
- **Numbers that don't reconcile**: ROI computed on revenue instead of profit; "65% CAGR" that is really 6.5%; NPV without units; a market share larger than capacity; COGS missing; chart labels that don't match the data; ROI 22% vs ≥23% in different places. Recompute everything in Python/Excel and cross-check every figure that appears more than once.
- **Market sizing stated but not derived**: always show TAM/SAM/SOM math.
- **Fake-partner logos** (BCA/Nike/GoPay shown as partners). Label them "target partners".
- **Decoration-only slides** in short formats (2 of 5 slides at Telkom).
- **Tiny samples** stated without caveat (n=3–6). Report n and state the limitation.
- **Dense, technical decks with a thin business case** (Caliber stopped at prelim).

## Visual signatures used so far (vary per sponsor brand)
- Toyota: navy #1E2E89 with periwinkle, one sans font, navy header band, chevron phases, pillar cards with target chips.
- Blibli 🥈: maroon #7C0F1F → red/orange gradient, one shade per letter badge, black full-sentence titles, bottom section tabs, a source line on every slide.
- ITECHNO 🥇: full-bleed red #C21F26, white rounded cards, 3D mascot, phone mockups, fixed bottom section bar, Plus Jakarta Sans.
- UBM 🥉: forest green #144824 + orange #ED8E01 accent word in each title, cream #FFFBF2, Garet, rounded outlined cards.
- UNAIR FIT: royal blue #1C5DB6 + amber accent, row of 4 big KPI numbers repeated.
- IBSC/Unilever: teal/navy or indigo/magenta, Poppins/Bricolage display with a serif body.
- **Rule**: take the palette from the sponsor's brand, use 1 primary + 1 accent + neutrals, and keep one bottom tracker/tab bar plus full-sentence action titles.

## Lessons from OTHER teams' winners (14 files, `portfolio/others_*.md`)
Benchmarks: Triplets GMBCC (prelim→SF), Ascendio B-Startion, IBCC BRAND UI 2025 (NIVEA) and 2026 (Summit Oto), ITTODAY 2025 ×3 (Plogee, HiBU, TBCare), RECURSION LockIN, MetaMind (Gandeng × TBS), RightHand (BEFound BMC), Triplecheese YLS 2025. Also includes the official **Gandeng BCC 2025 case brief**, which publishes its rubric: problem breakdown 25%, solution 30%, data 20%, storyline 15%, design 5%, English 5%. Judges there want expert interviews, each idea scored on ease/impact/risk, no padded surveys, and a hook title plus a one-page summary.

**Adopt these (Wijaya doesn't do them yet):**
- **Hook page BEFORE the cover**: a shock statistic (Triplecheese, Triplets) or an 8-panel comic (RightHand).
- **Persona bookend**: introduce the persona early and bring them back at the end ("Meet Sophia again… but now").
- **Initiative scoring table**: 5 candidate ideas × 4 criteria to justify the chosen pillars (MetaMind). Also an impact×effort matrix (Plogee).
- **Gap analysis slide**: ideal / current / gap (Triplecheese). Frame the problem as actual vs target (TBCare 58% vs 80%).
- **FMEA risk scoring** (severity × occurrence), or a 26-item risk register (The Incredibles).
- **Survey hypotheses mapped to root causes**, tested with z-tests (The Incredibles). Narrow scope with data, e.g. biggest brand and biggest waste stage (Triplets prelim).
- **Sponsor/regulation fit**: design around the client's regulations and group assets (Jenius, the 30% instalment cap), plus a "Group synergy" strip per pillar.
- **One phone mockup per acronym letter** (RightHand). Product page placed right after the abstract with a demo-video QR and Figma QR (Plogee).
- **Pillar pages**: a giant initial header plus a 4-chip Impact bar (IBCC 2025 and 2026). Alliterative "X to Y" pillar names (Triplecheese).
- **Ask slide** with a use-of-funds pie.
- **UI/UX extras**: WCAG contrast plus a typography token table, Hook Model Canvas, verbatim-quote empathy map, admitting a failed heuristic and then showing the fix, companion devices (smartwatch, IoT).
- **Cheap branding for Word/Docs papers**: corner logo tab, tagline footer pill, watermark (LockIN).
- **Reuse the previous winner's skeleton** when a competition repeats. IBCC 2026 copied 2025's chapter structure, and the bar rose to full rigour (hypothesis tests, risk register, ~60 sources).

**Wijaya is already stronger here, so keep it:** scenario/sensitivity grids, stage-gated asks, formula-backed numbers, the assumption register, larger research samples (n=112 vs 10–68), and the one-page visual exec summary. None of the 13 benchmark winners had sensitivity analysis.

**Winners still lose points on the same things Wijaya does:** numbers that don't reconcile (MetaMind net income, Ascendio table vs chart, ROI on revenue, client budget booked as income, NPV ~93% terminal value), tiny test samples, and KPIs without baselines. Doing better here is the clearest way to beat other teams.

## Lessons from PUBLIC international winners (`public-winners/*.md`; files in C:\Users\USER\Documents\Lomba-Benchmark\public-winners)
Sources: CBS Case Competition library (official 1st/2nd/3rd decks 2010–2026, plus case briefs), HBS New Venture Competition (official plans and decks), MOOT CORP world champions, DECA ICDC winning written IMC projects, Micron BACC, and Brandstorm/Unilever FLL slides. No Indonesian podium decks were found publicly; Indonesian winners are known only from news text.
- **Restate the client's target and beat it**, in the client's metric and currency (e.g. "54% growth vs the 50% asked").
- **4-row exec summary** (Question / Situation / Strategy / Impact), repeated as the closing slide. The question carries a numeric target.
- **Brief playback**: turn the ask into 3 verbs and reuse them as section names. **Rubric mirroring**: use the judges' section headings, in the same order.
- **Pillar tracker slide**: re-show the 3 pillar cards before each pillar, with the current one highlighted. Titles should read as one continuing sentence.
- **Appendix with its own contents page** (Analysis / Finance). **Sensitivity per pillar**, and a Monte Carlo when stakes are high. Build revenue per country × channel.
- **Scored choice tables** (markets/tactics: impact × feasibility, ~10 candidates, chosen ones highlighted). Include "why not X" Q&A backups, precedent proof from other firms, and a compliance check.
- **Prototype on a real API** with cost per call when the idea is tech.
- **Business plan specifics**: team is the largest criterion (HBS NVC 30%), so prove team-founder fit early. Show external traction (LOIs, pilots, pre-orders on a timeline, HBS 15%). Put the deal terms first, with tranches released on milestones (MOOT CORP champions). Use a "proven model from another country" (Barakat adapted Finland's baby box). Add a country/regulatory risk slide. Break the cost advantage into parts with $ per source. Put a money value on social impact. Q&A is heavily weighted.
- **Marketing specifics**: persona journey with a pain point per stage mapped to pillars; tactic tables phased by lifecycle; a consumer-facing campaign name/hashtag per pillar; a results strip (cost / revenue / ROI with formula and baseline); product, shelf and media renders; survey stats tests plus a working Figma demo.
- Benchmark winners are often weak on financials (naive ROI, no P&L, no sensitivity). Wijaya's rigour remains the differentiator.

## Default plan for the next competition
1. Read the rulebook and rubric, then pick a format based on the closest podium analogue: case → Toyota SF + Blibli; BPC → UBM 🥉; marketing → Blibli 🥈 / FIT; UI/UX → ITECHNO 🥇.
2. Build the issue chain → acronym → pillar×root-cause×KPI×budget matrix before any design work.
3. Build the financial model in code, with a scenario/sensitivity/assumption register.
4. Design with `06-proposal-design-system.md` (HTML/CSS → PDF), using the sponsor palette.
5. QA pass: the leftover-text search, number cross-check, typo check, and the judge checklist in 06.
