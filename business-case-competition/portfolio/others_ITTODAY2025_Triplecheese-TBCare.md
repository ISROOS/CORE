# IT Today 2025 · UX Today — "TBCare" (Tim Triplecheese, BINUS)

## Competition / type / round / placement
- **Competition:** IT Today 2025 (UX Today), UI/UX design proposal. The cover reads "IT TODAY 2025 – UI/UX Design Proposal".
- **Round:** written proposal. **Placement:** winner per user; placement unknown.
- **Team:** Devi J.S, Livenia K, Thaniesya S (BINUS University). The same team name appears on "Triplecheese_YLS 2025" in the user's folder.
- **Product:** TBCare, an app helping tuberculosis patients finish long treatment.
  - Medication scheduling, with proof-of-intake via **pill image recognition**.
  - **Virtual-pet gamification** (points buy accessories).
  - **AirCare IoT** room sensor (CO₂, PM2.5/PM10, temp, humidity) with ventilation tips.
  - Mask reminders via geofence, Sehatpedia education, widgets.
  - Theme: "Industry in Humanity", SDG 3.

## Format
- 30 pages, A4 portrait (596×842), Bahasa Indonesia.
- **Google Docs export** (Poppins + Arial embedded) with designed figures pasted in. The cover, solution and STP pages are designed; most pages are text + figure.
- Footer: TBCare logo bottom-left, page number bottom-right. No header.

## Section outline (PDF pages)
| PDF p. | Section |
|---|---|
| 1 | Cover: photo of a coughing man raising a hand ("stop TB"), huge black "UI/UX Design Proposal" title, green accent bar, team headshots |
| 2 | Abstrak + 5-phone mockup strip |
| 3–5 | Latar Belakang: Indonesia #2 TB globally, 885k cases (2024) bar chart, +22.4%/yr stat card, 125k deaths ≈14/hour, treatment gaps (SO initiation 81% vs 90%, RO success 58% vs 80%), reasons for non-adherence by gender (male/female % cards), air quality as a risk factor, KAP survey 43.6% low knowledge |
| 6 | Tujuan (3 icon cards) + Hasil (6 numbered outcome pills) + SDG 3 tile |
| 7 | Metodologi DT (5 green icon tiles) → Empathize |
| 8 | Survey **n=10** (horizontal bar charts + "Key Insight" box) + interviews **n=2** (photo quote cards) |
| 9–10 | Define: 2 personas (Michael Trionto, Viona Zaneta) with illustrated header, empathy map (Say/Think/Do/Feel) |
| 11 | Affinity map + "Competitive Benchmarking" dark-green ✓ table (4 apps) |
| 12 | Ideate: solution mapping (Problem → HMW → Solution rows, green side labels) |
| 13 | **"Jaminan Sehat"**: illustrated wordmark + 6 feature cards on a full-width green band |
| 14 | User flow (green diamond flowchart) + design system (colour circles, typography **table** with Quicksand style/size/letter-spacing/line-height) |
| 15 | Logo/favicon set, colour contrast checks (**Aa with WCAG ratings**), Crazy 8 |
| 16 | Wireframes + Hi-fi intro with QR |
| 17–20 | Hi-fi walkthrough in 8 numbered flows (register → IoT pairing with device photo → home/virtual pet → points & schedule → scan pill → AirCare analytics → Sehatpedia → notifications & widgets) |
| 20–21 | Testing: heuristic evaluation table (green ✓ rows, **one heuristic honestly marked as failing**: error recovery) |
| 22–23 | Usability testing: tester-criteria table, phase 1 vs phase 2 KPI strips, SEQ + SUS bar charts with "Key Insight" boxes |
| 24 | Iterasi: (1) fix for the failed heuristic (error message + auto-check after scan), (2) Sehatpedia category layout |
| 25 | Analisis Desain: STP (segmenting/targeting table with icons), positioning map (gamification × IoT axes) |
| 26–27 | Platform, rich picture, three-tier constraints + spec table |
| 28 | Navigation tree |
| 29 | Kesimpulan + Jaminan Sehat recap cards + phones |
| 30 | Daftar pustaka + Lampiran (logo, prototype QR) |

## Storyline pattern
- **Hook:** a stark statistic-driven opening. Indonesia is #2 in the world for TB, there are 885k cases, and "~14 deaths every hour". It is urgent and morbid rather than emotional storytelling.
- **Problem → root cause → solution → impact:** the problem is TB burden. The root causes, each backed by a national figure, are:
  - **non-adherence**: patients "feel healthy", drugs unavailable, boredom;
  - **low knowledge**: KAP 43.6%;
  - **poor home air/ventilation**.

  Each cause is matched to a feature: schedule + scan + gamification → adherence; Sehatpedia → knowledge; AirCare → air. This is the tightest cause → feature mapping of the three ITTODAY entries.
- **Solution naming:** product TBCare + a **hidden-letter acronym "Jaminan Sehat"** ("health guarantee"). Letters are pulled from the feature names: penJAdwalan, gaMIfikasi, image recognitioN, AirCare, Notifikasi, SEHATpedia. It is a clever, meaningful local phrase, the same move as SIAP and LENTERA.

## Frameworks & analyses
Design Thinking (d.school) · survey (n=10) · interviews (n=2) · 2 personas · empathy map · affinity map · competitive benchmarking · solution mapping (HMW-based) · user flow · design system with **typography spec table** and **colour-contrast (WCAG) check** · Crazy 8 · wireframe · hi-fi · Nielsen heuristic evaluation (with a failing item) · tester criteria (demographic / geographic / motivation / behaviour) · 2-phase usability test · SEQ · SUS · iteration tied to heuristic failure · STP + **positioning map** · rich picture · three-tier architecture · navigation map · IoT device concept.

## Numbers
- **Context (Kemenkes / national reports):** #2 globally; 885k cases (2024); +22.4%/yr; 125k deaths/yr (~14/hr). SO initiation 81% vs 90% target; RO success 58% vs 80%. Non-adherence reasons (male 33.5% feel healthy, 31.9% unavailable at facility, 13% bored; female 30.4% feel healthy…). KAP 2023: 43.6% low knowledge. Targeting: 293,323 cases (2020) → 885,000 (2024).
- **Usability:**
  - Completion time: phase 1 11m17s, phase 2 9m45s (target 9m30s–12m54s).
  - Success rate: 100% in both phases.
  - Misclick: 15% (12/80) in phase 1, 6.25% (5/80) in phase 2.
  - SEQ: 3.58 → 4.67 (5-pt).
  - SUS: **45 → 81.25**.
  - Tester count not explicit (80 predicted clicks).
- **Research sample is very small** (survey n=10, interviews n=2).
- No market sizing (beyond case counts), business model, device cost or financials.
- Sources: Kemenkes, TB Indonesia program report, SKI 2023, peer-reviewed KAP study.

## Visual design system
- **Palette:**
  - Document: deep teal-green ~#2A615A / #007661 (headers, bands, tables), sage #7D978C, mint #86BB9C / #D8E5DB tints, white.
  - App primary: green #5ED473 → #12A631 gradient.
  - Text: #007661, #686767.
  - Health/medical green throughout.
- **Type:** Poppins (doc headings + body, Arial fallback); Quicksand in the app. The cover uses a giant black bold Poppins title (an editorial "poster" cover).
- **Grid/frame:** mostly plain document, one column, wide line spacing (Google Docs 1.5). The designed moments are the cover, the full-bleed green feature band (p13), the STP tables and the KPI strips. The footer has a small logo.
- **Components:** big-number stat cards with icons, bar charts (green), % cards by gender, numbered outcome pills, persona cards with illustrated banners, dark-green benchmarking table, ✓ heuristic table with one red row, colour-contrast "Aa" badges, KPI strips per test phase, bar charts with "Key Insight 💡" callout boxes, positioning map, flowchart with green diamonds.
- **Illustration style:** stock photos (cover, personas), flat health illustrations (lungs, pills, doctors), a cute 3D yellow virtual-pet mascot in the app, a **real product photo of the AirCare device**.
- **Density:** medium. There is a lot of white space and line-spacing; it reads as a report with designed inserts.

## Why it likely won
- **The clearest problem → root cause → feature logic.** Each official statistic of failure (adherence, knowledge, air) gets one feature.
- **Distinctive tech mix** fits the medical problem: proof-of-intake scan (directly observed therapy, digitised), IoT air sensor, virtual-pet motivation.
- **The biggest measured improvement:** SUS 45 → 81.25 and misclick 15% → 6.25%. A low phase-1 score made the iteration story credible.
- **Honest heuristic evaluation** (admits one failing heuristic, then fixes it) reads as genuine process.
- **Accessibility craft:** a typography spec table and WCAG contrast checks. These are rare in student entries.

## Weaknesses
- **Research base is very thin** (n=10 survey, 2 interviews), stated without caveat.
- Google-Docs layout makes many pages look plain next to Plogee/HiBU. Inconsistent figure styling.
- The design-system palette (#5ED473 / #12A631 bright green) differs from the document's deep teal brand.
- Typos ("Emphatize", "Recovers"). The Hasil section is generic.
- No business model, cost of the IoT device, distribution via puskesmas/Kemenkes, or privacy handling for health data.
- Tester count isn't stated. SEQ scale is 5-pt here vs 7-pt in Plogee, so comparisons across entries aren't meaningful.

## Differences vs Wijaya Team house style (ITECHNO 🥇 TukaKu)
**They do, Wijaya doesn't:**
- **WCAG colour-contrast check** and a full **typography token table** (style/size/weight/letter-spacing/line-height).
- **Heuristic evaluation that reports a failure**, then iterates on it.
- **Tester-criteria table**.
- A **hidden-letter acronym** built from feature names.
- **Positioning map**.
- A **hardware/IoT device** shown with a product photo.
- A **national-target-gap** framing (actual vs target %) as the problem statement.

**Wijaya does, they don't:**
- Large two-sided research (n=112) and SUS benchmarks.
- A designed abstract with a KPI strip.
- A brand world (mascot, section nav).
- TOWS and a revenue model.
- English.
- A comic/story hook. TBCare's hook is purely statistical.

**Shared:** the same template, two-phase SEQ/SUS/misclick measurement, the spec table and the navigation map.

## Reusable techniques
- **Frame the problem as "actual vs national target"** (81% vs 90%, 58% vs 80%). It creates an instant, quantified gap the solution must close.
- Make the acronym **from letters hidden inside feature names**, spelling a meaningful local phrase (bold the letters in the explanation sentence).
- Add a **typography spec table + WCAG contrast badges** to the design system. Cheap, and it signals professional craft.
- In the heuristic evaluation, **admit one failing heuristic**, then show the iteration that fixes it. That turns testing into a story.
- Add a **tester-criteria table** (demographic, geographic, motivation, behaviour) before the usability results.
- Use **"Key Insight 💡" callout boxes** beside every chart.
- For health/IoT ideas, show a **physical device photo** plus the pairing flow, which makes the concept feel buildable.
- A low phase-1 SUS isn't a weakness. Report it honestly, because the jump is the proof.
