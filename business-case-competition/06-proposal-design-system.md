# Design Playbook for Competition Proposals and Pitch Decks (Wijaya Team)

Researched 8 Nov 2026. Star counts come from the GitHub REST API on that date (`/repos/{owner}/{repo}` and `/search/repositories?sort=stars`). Every file listed under "Read" was fetched from raw.githubusercontent.com. Raw copies are in `analysis/gh_raw/`, and the search and metadata dumps are in `analysis/gh_search.json` and `analysis/gh_meta.json`.

Use this file as the design layer that sits on top of the `business-case-competition` skill. That skill covers content, frameworks and storyline. This file covers how the pages look.

---

## (a) Best repos: what to borrow from each

### Tier 1: directly usable for consulting-grade proposals and decks

| Repo | Stars | License | Read | What to borrow |
|---|---|---|---|---|
| [alchaincyf/huashu-report](https://github.com/alchaincyf/huashu-report) | 489 | MIT | README, `references/视觉系统.md`, `assets/base.css`, `references/生产流水线.md` | **The best A4 report reference found.** Its rules were reverse-engineered from 41 real 2026 institutional PDFs (McKinsey, BCG, PwC, Stanford HAI, World Bank). Key findings: body text is near-black in 40 of 41 reports, and the brand colour makes up a median 2.8% of body characters. Chart titles state the conclusion. A4 portrait is the default (35 of 41). Adjacent type levels should differ by at least 1.3x. Tables need anti-collision rules. It also includes a production `base.css` with print rules and a list of 11 pitfalls from Chromium HTML-to-PDF work. |
| [kgraph57/mckinsey-style-visualization-skill](https://github.com/kgraph57/mckinsey-style-visualization-skill) | 172 | MIT | README, `references/style-system.md` | A complete token system for 16:9 consulting slides: 1280×720 canvas, 8px grid, 80px margins, fixed headline, chart and source baselines, and a type scale defined by ratios (headline/body ≥ 1.5, body/chrome ≥ 1.6, readable text ≥ 22px). Also the **emphasis ladder** (fill > outline > coloured text > bold) and chart rules: honest zero baseline, direct labels, blue for the argument, grey for context, red only for risk, and a greyscale-survival test. |
| [likaku/Mck-ppt-design-skill](https://github.com/likaku/Mck-ppt-design-skill) | 335 | Apache-2.0 | README, SKILL.md, `color-palette.md`, `brand-guide.md`, `guard-rails.md` | Consulting grammar for native, editable PPTX built with python-pptx: navy #051C2C plus a grey ramp, Georgia titles with Arial body, and a fixed type ladder (44/28/22/18/14/9 pt). Its "10 guard rails" include dynamic widths `(CW - gap*(n-1))/n`, a minimum gap above the bottom bar, legend swatches that match chart colours, and no connectors or shadows (they trigger PowerPoint's repair prompt). It also has a code-checked QA gate (`gate_check.py`). Use it when the team needs an editable .pptx. |
| [appautomaton/presentation](https://github.com/appautomaton/presentation) | 66 | MIT (badge) | README, `brand-system/references/typography-guide.md`, `palette-guide.md`, `deck-design-pdf/SKILL.md` | A four-skill pipeline: consultant (storyboard) → brand-system (identity) → deck-design-pdf (HTML + Playwright `page.pdf()`) or deck-design-ppt. Borrow the **8-role palette** (surface-dark, accent, accent-light, surface-muted, surface, positive, warning, negative), the Google-Fonts pairing table, the **space audit** (1280×720 leaves a body of about 1168×600 after the header and footer, so compute each chart's height before building) and the L1/L2/L3 density classes. |
| [anthropics/skills](https://github.com/anthropics/skills) | 189,243 | per-skill (LICENSE.txt) | `skills/frontend-design`, `pptx`, `theme-factory`, `canvas-design`, `brand-guidelines` SKILL.md | `frontend-design` lists the five current "AI-generated look" clusters to avoid: a cream background with a serif and a terracotta accent, near-black with an acid accent, broadsheet hairlines, the SaaS card kit, and ALL-CAPS eyebrows with `A · B · C` meta strings. It also says to use numbered markers only for real sequences. `pptx` adds an "Avoid" list (no accent lines under titles, no decorative edge stripes, no centred body text, no cream backgrounds by default), a 60-70% dominant-colour rule, dark title and closing slides around light content slides, Office-safe fonts for overflow QA, and 10 palettes. `theme-factory` provides 10 colour and font themes. |
| [analystacademy/flight-check](https://github.com/analystacademy/flight-check) | 25 | MIT | README | A final-pass deck QA skill with six checks: AI writing tells, fabricated sources, topic-label headlines, vague claims, numbers that don't match across slides, and polish problems (mixed `$4B`/`$4b`, leftover [TBD], 3D charts, truncated axes). Run it on every submission. |
| [sharptoolbox/consulting-html-ppt](https://github.com/sharptoolbox/consulting-html-ppt) | 34 | none stated | README (Chinese) | HTML 1920×1080 consulting decks with three page types chosen automatically: numbers → ECharts, structure → SVG model, parallel categories → line-and-box layout. Fixed skeleton (20px margin, 5px black rule at y=170, 48px bold title), flat design, at most one red element per page. It ships 22 SVG structure templates and 28 ECharts templates. **No license file, so take the ideas but don't copy code.** |

### Tier 2: design systems, taste and tokens

| Repo | Stars | License | Use |
|---|---|---|---|
| [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) | 126,109 | MIT | DESIGN.md files for brand design systems. The local `popular-web-designs` skill is built from it. |
| [VoltAgent/awesome-claude-design](https://github.com/VoltAgent/awesome-claude-design) | 4,391 | MIT | 68 more DESIGN.md design-system inspirations. |
| [google-labs-code/design.md](https://github.com/google-labs-code/design.md) | 28,777 | Apache-2.0 | The DESIGN.md spec and CLI (lint, WCAG contrast check, export). The local `design-md` skill wraps it. |
| [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | 146,779 | MIT | UI/UX design-intelligence skill (styles, palettes, font pairings). Most useful for UI/UX competitions. |
| [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) | 111,899 | MIT | "Taste" skills for agents: art direction, reference images, browser checks. |
| [alchaincyf/huashu-design](https://github.com/alchaincyf/huashu-design) | 28,969 | MIT | Web, prototype, editable PPTX and infographic design skill with 84 sample styles (Chinese). |
| [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) | 74,824 | MIT | Turns documents or topics into native PowerPoint with native shapes. `software-ai-life/Awesome-PPT-Design-Skills` (135 stars, no license) supplies style packs for it. |
| [wilwaldon/Claude-Code-Frontend-Design-Toolkit](https://github.com/wilwaldon/Claude-Code-Frontend-Design-Toolkit) | 1,283 | none stated | A curated index of design skills, token tools and visual-QA MCPs. |
| [alexpate/awesome-design-systems](https://github.com/alexpate/awesome-design-systems) | 26,312 | Unlicense | Index of public design systems for studying spacing and type ramps. |
| [Jolg42/awesome-typography](https://github.com/Jolg42/awesome-typography) | 1,551 | CC0 | Typography resource list. |

### Tier 3: rendering engines and templates (print, Typst, slides, charts)

| Repo | Stars | License | Use |
|---|---|---|---|
| [pagedjs/pagedjs](https://github.com/pagedjs/pagedjs) | 1,564 | MIT | A polyfill for CSS Paged Media and Generated Content: running headers via `string-set` and `position: running()`, `target-counter` for TOC page numbers, and footnotes. Add `<script src="https://unpkg.com/pagedjs/dist/paged.polyfill.js">` and the page paginates in the browser. Use it when Chrome alone can't produce TOC page numbers or running headers taken from the content. Read: README. |
| [ashok-khanna/pdf](https://github.com/ashok-khanna/pdf) | 326 | MIT | paged.js tutorial (the README only links to the site). |
| [electricbookworks/paged-design](https://github.com/electricbookworks/paged-design) | 43 | CC0 | Customisable book designs for paged.js. |
| [Kozea/WeasyPrint](https://github.com/Kozea/WeasyPrint) | 9,763 | BSD-3 | Python HTML-to-PDF with strong `@page` support. It doesn't run JS, so charts must be inline SVG. |
| [vivliostyle/vivliostyle.js](https://github.com/vivliostyle/vivliostyle.js) | 800 | AGPL-3.0 | CSS typesetting engine. Note the AGPL license. |
| [typst/typst](https://github.com/typst/typst) | 57,045 | Apache-2.0 | Markup typesetting. Fast and gives precise layout for A4 reports. |
| [talal/ilm](https://github.com/talal/ilm) | 245 | MIT-0 | Clean Typst report template: cover, TOC, figure indices, and a running footer that shows the chapter. Start with `typst init @preview/ilm`. Read: README. |
| [touying-typ/touying](https://github.com/touying-typ/touying) | 2,426 | MIT | Typst slide package. Also [polylux](https://github.com/polylux-typ/polylux) (1,613, MIT). |
| [slidevjs/slidev](https://github.com/slidevjs/slidev) | 49,399 | MIT | Markdown slide decks. The [zcag/tahta](https://github.com/zcag/tahta) theme (145, MIT) is a themeable design system for Slidev. |
| [hakimel/reveal.js](https://github.com/hakimel/reveal.js) | 72,535 | MIT | HTML slide framework. The minimalist [grantmcdermott/quarto-revealjs-clean](https://github.com/grantmcdermott/quarto-revealjs-clean) theme (419, MIT) also has a Typst PDF variant. |
| [marp-team/marp](https://github.com/marp-team/marp) | 12,730 | MIT | Markdown → PDF/PPTX slides. |
| [garrettj403/SciencePlots](https://github.com/garrettj403/SciencePlots) | 9,388 | MIT | Matplotlib style sheets for clean charts. Use as a base, then apply the palette below. |
| [Financial-Times/chart-doctor](https://github.com/Financial-Times/chart-doctor) | 3,388 | MIT | Home of the FT "Visual Vocabulary" chart-chooser (choose a chart by relationship: deviation, correlation, ranking, distribution, change over time, part-to-whole, magnitude, spatial, flow). |
| [scanny/python-pptx](https://github.com/scanny/python-pptx) | 3,583 | MIT | The engine behind the local `powerpoint` skill and Mck-ppt. |

Searched with no useful results: "consulting slides template mckinsey" (zero results), "weasyprint template report", "print css a4 report template", "font pairings google fonts" (only spam and toy repos) and "data visualization style guide" (only tiny repos). Use the Tier 1 sources above instead.

---

## Local Hermes skills: what each offers and how to call it

| Skill | Path | Offers for proposals and decks | How to invoke |
|---|---|---|---|
| **business-case-competition** | `skills/productivity/business-case-competition` | Content layer: SCQA, action titles, a 14-slide template, rubric weights, and `references/figure-to-html.md` (rebuild PDF figures and covers as editable HTML/CSS and export back with printToPDF). | `skill_view("business-case-competition")`, then load the reference you need. |
| **claude-design** | `skills/creative/claude-design` | Process and taste: commit to a "surface" before choosing tokens, three variants (conservative, strong-fit, divergent), a 10-tell slop diagnostic (tech gradient, indigo default, feature-tile grid, accent rail, glass, monument stat, icon topper, centre stack, default Inter, wrong surface) and deck rules (1920×1080, ≥24px text, ≤2 background colours). Print text ≥ 12pt. | `skill_view("claude-design")`. Name the surface: a proposal is **Decide/Learn**; a financial or KPI page is **Compare/Monitor**. |
| **popular-web-designs** | `skills/creative/popular-web-designs` | 54 brand systems with exact tokens and Google Fonts substitutes. The most useful for documents are `ibm.md` (IBM Plex, consulting-grade), `stripe.md`, `notion.md`, `apple.md`, `linear.app.md`, `vercel.md`, `mongodb.md` and `wise.md`. | `skill_view("popular-web-designs", file_path="templates/ibm.md")` |
| **design-md** | `skills/creative/design-md` | Write the team's DESIGN.md token file once (colours, type, spacing, components). `npx @google/design.md` lints WCAG contrast and exports DTCG/Tailwind. | `skill_view("design-md")`. Keep one DESIGN.md per competition so the proposal, deck and Instagram assets match. |
| **baoyu-infographic** | `skills/creative/baoyu-infographic` | 21 layouts (linear-progression, binary-comparison, comparison-matrix, hierarchical-layers, funnel, hub-spoke, bridge, iceberg, dashboard, winding-roadmap, circular-flow, dense-modules…) × 21 styles (corporate-memphis, technical-schematic, ikea-manual, subway-map, ui-wireframe…). Output comes from `image_generate`, so it is a **raster image**. Use it for cover art, concept visuals and social posts, **not** for data charts, where numbers must stay exact and editable. | `skill_view("baoyu-infographic")`. For consulting tone, use the `ikea-manual`, `technical-schematic` or `subway-map` styles. |
| **powerpoint** | `skills/productivity/powerpoint` | python-pptx scripts: `pptx_create.py` (JSON spec → deck with native bar, bar_h, line and pie charts, tables, footers, slide numbers, 16:9 default), `pptx_edit.py`, `pptx_from_template.py` (fill a brand .pptx), `pptx_read.py`, and `pptx_render.py` (LibreOffice → PNG for visual QA). | `skill_view("powerpoint")`, then `python scripts/pptx_create.py deck.json out.pptx`. |
| **pdf** | `skills/productivity/pdf` | reportlab and pypdf: merge (cover + body + appendix), stamp, watermark, page images (`pdf_page_image.py` for page-by-page QA), metadata. The skill itself says **not** to use it for pixel-perfect HTML→PDF; use headless Chrome for that. | `skill_view("pdf")`, then `pdf_merge.py`, `pdf_page_image.py` or `pdf_meta.py`. |
| docx | `skills/productivity/docx` | Use only when the rulebook demands a Word file. It supports styles, TOC and Page X of Y fields. | `skill_view("docx")` |

**Recommended stack:** write the HTML/CSS proposal using the tokens below → export with Chrome `printToPDF` or Playwright `page.pdf()` → run `pdf_page_image.py` and inspect every page → run a flight-check-style review → merge with `pdf_merge.py` if the cover or appendix is built separately. For the deck, use either HTML at 1280×720 → PDF, or `powerpoint` with Mck-ppt rules when an editable .pptx is required.

---

## (b) Proposal design system (A4 portrait)

### Page geometry and grid
- **Page:** A4, 210 × 297 mm.
- **Margins:** top 20 mm, bottom 22 mm (the footer sits inside this), inside/left 22 mm, outside/right 18 mm. If the PDF is only read on screen, use symmetric 20 mm.
- **Text block:** 170 × 255 mm. Use a **12-column grid** with 4 mm gutters, so each column is ≈ 10.5 mm.
  - Full-width body runs over 12 columns, but cap reading paragraphs at about 75-80 characters (frontend-design: < 80 chars). The classic consulting layout is a **4-column side rail plus 8 columns of body**: key takeaways, figure notes and the source go in the rail.
  - Charts span 8 or 12 columns, KPI cards 3 or 4 columns each, and a 2x2 matrix spans 6 or 8.
- **Baseline:** 10.5 pt body at 1.5 leading gives a 15.75 pt (≈ 5.5 mm) baseline. Make every vertical gap a multiple of 4 mm (4/8/12/16/24).
- huashu-report measured three column modes: a single narrow column (about 65% of page width; academic style), two columns (survey style), and fixed text-left/figure-right with the text at about 1/3 (Deloitte, deck-like). For competition proposals, use the **side rail plus body** layout.

### Type scale (A4 print; at least 1.3x between adjacent levels, per huashu-report)
| Role | Size / leading | Weight | Notes |
|---|---|---|---|
| Cover title | 36-44 pt / 1.1 | 700 | At most 2 lines. |
| Section divider number and title | 28-32 pt / 1.15 | 700 | |
| Page action title (H2) | 16-18 pt / 1.25 | 700 | **A full-sentence conclusion, up to 2 lines.** |
| H3 / figure title | 12-13 pt / 1.3 | 600-700 | The figure title also states the conclusion. |
| Body | 10-11 pt / 1.45-1.55 | 400 | English body. The claude-design floor is 12pt for print; 10.5-11pt is acceptable when the judges read on screen. If Bahasa Indonesia makes lines long, use 11 pt. |
| Table text | 8.5-9.5 pt / 1.4 | 400 | Use `tabular-nums`. |
| KPI number | 24-32 pt | 700 | `white-space: nowrap`. |
| Caption, source, footnote | 7.5-8 pt / 1.45 | 400 | Muted grey, never below 7 pt. |
| Running header and footer | 7-8 pt | 400-600 | |

### Free font pairings (all on Google Fonts)
Use one family or two at most, and load only weights 400/600/700 (appautomaton typography guide). **Keep numbers in a sans with tabular figures,** and keep serif type in headings only (huashu-report: "serif stops at the title").

| Mood | Heading | Body/data | When to use |
|---|---|---|---|
| Consulting classic (MBB) | **Source Serif 4** or **Newsreader** | **Source Sans 3** or **Inter** | Strategy, finance, BCC. A free stand-in for the Georgia + Arial/Helvetica pairing used by both Mck repos. |
| Corporate neutral | **IBM Plex Sans** | IBM Plex Sans (+ Plex Mono for data) | Tech, fintech, operations. Matches `popular-web-designs/templates/ibm.md`. |
| Indonesian-modern | **Plus Jakarta Sans** | Plus Jakarta Sans or **Inter** | MPC, consumer and startup topics. The typeface was designed in Indonesia (Tokotype), which gives the team a story to tell. |
| Editorial premium | **Instrument Serif** or **Fraunces** | **DM Sans** | Brand and marketing plans, ESG, culture topics. |
| Data-dense | **Inter** or **Public Sans** | same, + **JetBrains Mono** for KPI numbers | Financial appendix, dashboards. |

Avoid: 3 or more families, a serif body with a sans heading, display fonts in body text, and Inter used by default rather than chosen (claude-design tell #9). For editable .pptx files, use Office-safe fonts (Arial or Calibri body, Cambria or Georgia headings); otherwise the deck re-flows on the judges' PCs (anthropics `pptx`).

### Colour rules
- **Structure:** 1 primary, 1 accent, neutrals, and semantic colours only for data. The dominant colour carries 60-70% of the visual weight (anthropics `pptx`).
- **Body text is near-black** (#1F2328, #231F20 or #30353A), never the brand colour. Brand colour belongs in charts, section markers and key numbers only, at about 3-8% of the page (huashu-report).
- **8 roles** (appautomaton palette guide): surface-dark (covers and dividers; ≥ 4.5:1 against white text), accent, accent-light (gridlines), surface-muted (accent at 90-95% lightness for callout fills), surface (white), positive (muted green such as #2E9E5A), warning (amber #E6A800, never pure yellow), and negative (#B91C1C or #A43C35).
- Charts: **accent for the series being argued, grey (#9AA0A6) for context, red only for loss or risk.** Use at most 6 categorical colours; if you need more, change the chart type (huashu-report).
- **Emphasis ladder:** solid fill > tinted fill > outline > accent text > bold. Use at most one or two strong emphases per page and never stack them (mckviz style-system).
- **Contrast:** body text ≥ 4.5:1 and large text ≥ 3:1. Test with `npx @google/design.md lint` or WebAIM. Print one page in greyscale: the accent and dark grey must still be distinguishable.
- **Starter palettes** (verified hex values from the sources):
  - MBB navy: #051C2C primary, #333333 text, #666666 muted, #CCCCCC lines, #F2F2F2 panels, accents #006BA6 / #007A53 / #D46A00 / #C62828 only when there are 3 or more parallel items (Mck-ppt brand-guide).
  - Strategy blue: #15296B primary, #2563EB secondary, #374151 / #6B7280 / #D1D5DB / #F3F4F6 neutrals, #EFF3FB tint, #B91C1C risk (mckviz).
  - Teal institutional: #14505E brand, #A4551F second accent, #231F20 ink, #6B6B6B muted, #D8D8D8 rules (huashu `base.css`).
  - Topic-led palettes such as Forest & Moss #2C5F2D/#97BC62, Teal Trust #028090/#00A896 and Cherry Bold #990011/#2F3C7E (anthropics `pptx`). If the case brand has its own colour, mute it 10-15% for print (appautomaton).

### Component library (build each once as a CSS class)
1. **Cover:** title (the value proposition, not just "Proposal"), subtitle (one sentence saying what this is), competition name, team and university logos, and the month and year. huashu-report observed that cover design intensity tracks "who pays to read": a pitch wants a designed cover, a research paper wants a metadata cover. A full-bleed surface-dark or a single strong photo with a duotone overlay works well. No cliché gradient and no gold on navy (mckviz).
2. **Section divider:** full-bleed surface-dark, a large section number, the section title, and a one-line "what this section proves". Use 3-5 dividers, which match the pillar structure.
3. **Page header / progress tracker:** a breadcrumb in the top margin (`02 Market Analysis · Customer Pain`) or a row of chapter tabs with the current one in the accent colour. It helps judges navigate a 40-page document. On the cover and dividers, omit it.
4. **Executive summary box:** SCQA in 4 blocks, or 3 numbered key recommendations with impact numbers, plus a 3-4 KPI strip at the bottom. Exactly one page.
5. **KPI stat cards:** a big number (nowrap, tabular) + a label + a delta or source line. Use 3-4 per row, a flat fill **or** an outline, never both (mckviz "flat fill, never fill-plus-border"). Don't use "monument stats" as decoration (claude-design tell #6); every number needs a source.
6. **Callout / key-takeaway box:** surface-muted fill with an accent-coloured label ("So what"). **Don't** use a coloured left-border rail (anthropics `pptx` and claude-design tell #4). Use one per page at most.
7. **Numbered insight cards:** numbers only when the items really are a sequence or ranked (frontend-design). Otherwise use a bold lead-in phrase.
8. **Tables:** a header row with a 0.7 pt dark rule, 0.4 pt light row rules, no outer box, and no bottom rule. Text cells left-aligned, numeric columns right-aligned (or only the last column right-aligned in mixed tables), `tabular-nums`, 3 mm horizontal padding, and a 0.5 px light vertical divider when columns hold long text. Repeat `thead` across pages (huashu `base.css`).
9. **Charts:** see the chart rules below.
10. **Roadmap / Gantt:** quarters or months on the x-axis, 3-5 workstream rows, bars in accent with milestones as diamonds, and one "decision gate" marker (Mck-ppt showcase). Label phases inside the bars and put the date range under the axis.
11. **Issue tree / driver tree:** left to right, MECE, with the root question on the left and the boxes for prioritised branches in the accent fill and the rest in grey outline. Draw it in inline SVG or CSS grid with 1 pt connectors.
12. **2x2 matrix** (impact/effort, BCG, attractiveness/ability): hairline axes with axis labels centred on the axis span (Mck guard-rail 6), quadrant names in muted text, and items as labelled dots. Tint only the "do first" quadrant.
13. **Process chevrons:** n steps with width `(W - gap*(n-1))/n`, built with CSS `clip-path: polygon(...)`. Put the step title inside and the detail below. Use them only for real sequences.
14. **Source footnotes:** every chart, number and table gets a `Source:` line in 7.5-8 pt muted grey under the figure, and the full reference goes in the bibliography. Number figures and tables (`Figure 3.2`).
15. **Appendix index:** a table of contents for the appendix (A1 Financial Model, A2 Survey Instrument, …) with page numbers, and a small "↗ See Appendix A2" cross-reference in the body.
16. Optional: **Team page** (photo circles, roles, one credibility line each) and **Risk matrix** (likelihood × impact heatmap plus mitigation table).

### Chart styling rules
- **The title is the conclusion** ("GenZ churn doubled after the price hike"), and the subtitle gives the metric, unit and period.
- Use a zero baseline for bars, mark the "0" explicitly, and never truncate the axis without disclosing it (mckviz). Never use 3D or pie charts with more than 4 slices; prefer horizontal bars for ranking.
- Label values directly and drop legends where possible. If a legend is needed, its swatches must match the chart colours exactly (Mck guard-rail 4).
- Use no gridlines or very light ones (#E5E7EB). Remove chart borders and keep the axis lines thin.
- Accent for the focus series, grey for comparators, and a diverging palette anchored at 0 for variance data.
- Before drawing, pick the chart type by relationship (FT Visual Vocabulary): change over time → line or column; ranking → sorted horizontal bar; part-to-whole → stacked bar or waterfall; deviation → diverging bar; correlation → scatter.
- Make charts with inline SVG, ECharts in SVG render mode, or matplotlib exported to SVG (SciencePlots base + the team palette), so they stay vector and sharp in the PDF. Check axis tick formatting on narrow ranges: huashu pitfall #9 shows a `{:.0f}` format printing "1, 1, 1, 2, 2" on a 0.9-1.7 axis.

---

## (c) Print-CSS techniques

### HTML → A4 PDF (Chrome / Playwright)
```css
@page { size: A4; margin: 20mm 18mm 22mm 22mm; }
@page :first { margin: 0; }                 /* full-bleed cover */
@page divider { margin: 0; }                /* named page for section dividers */
.divider { page: divider; break-before: page; }

/* Chrome 131+ supports margin boxes and page counters natively */
@page {
  @bottom-right { content: counter(page) " / " counter(pages); font: 600 7.5pt 'Inter'; color:#6B7280; }
  @bottom-left  { content: "Wijaya Team · Binus University"; font: 7.5pt 'Inter'; color:#6B7280; }
  @top-right    { content: "Proposal — <Competition> 2026"; font: 7pt 'Inter'; color:#9AA0A6; }
}
@page :first { @bottom-right { content: none; } @bottom-left { content: none; } @top-right { content: none; } }

html { -webkit-print-color-adjust: exact; print-color-adjust: exact; }  /* keep fills and backgrounds */
h1, h2, h3 { break-after: avoid; }                      /* no heading stranded at the page bottom */
p { orphans: 2; widows: 2; }
figure, .kpi-row, .callout, .card, tr { break-inside: avoid; }
section.chapter { break-before: page; }
thead { display: table-header-group; }                  /* repeat table header across pages */
body, p, li, td, .src { overflow-wrap: anywhere; }      /* a long URL can shrink the whole PDF */
.kpi .n { white-space: nowrap; font-variant-numeric: tabular-nums; }
```
Sources: Chrome 131 release notes and the Chrome "print-margins" blog (margin boxes, `page` and `pages` counters); huashu `base.css` (break rules, header repeat, overflow-wrap, nowrap KPIs).

Key techniques and pitfalls:
- **Chrome limits:** margin boxes and counters work, but `string-set`/`running()` (headers taken from the chapter content) and `target-counter()` (TOC page numbers) **do not**. You have three ways around this:
  1. paged.js polyfill (`paged.polyfill.js`, which supports all of these), then print.
  2. A **named `@page` per chapter**, with that chapter's title in the margin box: `@page ch2 { @top-left { content: "02 Market"; } }` and `.ch2 { page: ch2; }`.
  3. A two-pass build that renders the PDF, finds each heading's page with PyMuPDF and writes the numbers back into the TOC. huashu's `render.py` does this; loop until the page count stops changing and skip the TOC pages when locating headings.
- Export with Playwright `page.pdf({format:'A4', printBackground:true, preferCSSPageSize:true})`, or CDP `Page.printToPDF` with `preferCSSPageSize:true, printBackground:true`. **Turn off the browser's default header and footer** (`displayHeaderFooter:false`).
- **Full-bleed elements:** never hard-code `width:210mm` inside a margined page. One overflowing element (for example, a 93-character URL) makes Chromium scale the whole document to about 66% (huashu pitfall). A body background doesn't cover the page margins, so use `@page{margin:0}` with padded `.page` containers for coloured pages.
- **Fixed-page mode** (best control, used by most designed proposals): every page is a `<section class="page">` with `width:210mm; height:297mm; overflow:hidden; padding:20mm 18mm 22mm 22mm; break-after:page`, and `@page{size:A4; margin:0}`. Write page numbers yourself. Content cannot flow, so check for overflow programmatically: run `el.scrollHeight > el.clientHeight` for every `.page` in the browser.
- **Fonts:** self-host the WOFF2 files or wait for `document.fonts.ready` before calling `pdf()`. Otherwise the fallback font gets embedded.
- **Orphan figures:** keep a figure together with its title and source using `break-inside: avoid` on the `<figure>`, and put `break-after: avoid` on the lead-in paragraph. If a figure still leaves more than 40% of a page empty, move the paragraph instead of shrinking the figure.
- **QA:** render every page to PNG (`pdf_page_image.py` or PyMuPDF), make contact sheets (12 pages per image at about 430 px per page), and look at **every** page. Spot checks miss layout bugs because they cluster on complex pages (huashu). Mechanical checks: grep the HTML for un-interpolated `{fig(`, leftover `TBD`, `lorem` and `NaN`.

### 16:9 decks
- **Canvas:** 1280×720 px (mckviz and appautomaton) or 1920×1080 (claude-design, consulting-html-ppt). For PDF output use `@page { size: 338.67mm 190.5mm; margin: 0 }`, which is 13.333 × 7.5 in (PowerPoint widescreen), with one `.slide{width:338.67mm;height:190.5mm;overflow:hidden;break-after:page}` per slide (huashu `base.css` mode B).
- **Zones at 1280×720:** 56-80 px side margins, action title at y ≈ 96 (up to 2 lines, 32-40 px bold), body band y ≈ 208-560 (or about 1168×600 after a 76 px header and 44 px footer), takeaway line y ≈ 630, and source plus page number y ≈ 692 at 13 px (mckviz).
- **Type:** readable text ≥ 22 px at 1280 (≥ 24 px at 1920). Headline/body ≥ 1.5x. Source text is the smallest on the slide by design.
- **Space audit:** before building, write `body 600 − other content = chart height` for every chart slide (appautomaton).
- Use dark covers and dividers around light content slides. Keep one message per slide (L1) for a pitch and multi-panel slides (L2) for a working deck. Vary layouts; use no accent line under titles and no edge stripes (anthropics `pptx`).
- For an editable deck, use python-pptx: the local `powerpoint` skill, or Mck-ppt rules such as dynamic widths, no connectors or shadows, and `gate_check`. Render through LibreOffice to PNG and inspect before submitting.

---

## (d) Design mistakes judges notice: pre-submission checklist

**Story and headlines**
- [ ] Every page or slide title is a full-sentence conclusion, not a topic label like "Market Overview" (flight-check #3). Reading only the titles should give the whole argument.
- [ ] Numbers match everywhere: executive summary = body = financial appendix = deck (flight-check #5).
- [ ] Every number and chart has a named source line. No "research shows" without a source, and no invented sources (flight-check #2).
- [ ] No vague words without numbers ("significant", "optimize", "leverage") and no AI-style triplets (flight-check #1, #4).

**Visual hierarchy**
- [ ] There is one clear focal point per page and at most one or two strong emphases (emphasis ladder).
- [ ] Type levels differ by at least 1.3x. Body text 10pt with headings at 11pt looks amateur (huashu-report).
- [ ] Body text is left-aligned, never centred or justified with rivers (anthropics `pptx`).
- [ ] At most 2 font families. Numbers use tabular figures. There are no Office fallback fonts in the PDF (check embedded fonts in Acrobat's document properties or with `pdffonts`).
- [ ] Body text is near-black. The brand colour is not spread across paragraphs. There are no rainbow palettes and at most 6 categorical colours.

**AI-template tells** (claude-design slop diagnostic; anthropics frontend-design and pptx)
- [ ] No indigo/violet gradient, glassmorphism, emoji bullets or a centred stack on every page.
- [ ] No identical icon + heading + sentence × 3 card grids on every page, and the same layout isn't repeated slide after slide.
- [ ] No coloured left-border callouts, accent underlines under titles or decorative colour bars.
- [ ] No ALL-CAPS eyebrow above every heading, `A · B · C` meta strings or 01/02/03 markers on things that aren't sequences.
- [ ] No cream-and-terracotta default look unless it was chosen deliberately.

**Charts and tables**
- [ ] No 3D, no pie charts with more than 4 slices, a zero baseline on bars, and honest axes with readable tick labels.
- [ ] Direct labels are used, and legend colours exactly match the series.
- [ ] Tables have no heavy gridlines, numbers are aligned, the header repeats across pages, and adjacent columns don't run into each other.
- [ ] Charts are vector (SVG/PDF) and not blurry screenshots. Exported images are at least 200 dpi.

**Print and production**
- [ ] No text overflow or clipping, nothing touches the margins, and every `.page` passes the overflow check.
- [ ] No headings stranded at the bottom of a page, no one-line orphan pages and no half-empty pages caused by an oversized figure.
- [ ] Page numbers are correct, the TOC page numbers match the PDF, and appendix references resolve.
- [ ] The cover has the title, subtitle, competition, team, university and date. Logos are not stretched (keep their aspect ratio).
- [ ] Consistent formatting: currency (Rp 1,2 M vs IDR 1.2B; pick one), dates, decimal separators (Indonesian comma vs English point) and capitalisation.
- [ ] No leftover `[TBD]`, `lorem`, placeholder images or un-interpolated template code.
- [ ] Page count and file size are within the rulebook limits. The PDF metadata title is set and the filename follows the rulebook format.
- [ ] Greyscale print test: the meaning survives without colour (mckviz).
- [ ] Every page has been reviewed as an image (contact sheets), not just spot-checked.

---

## Sources (all fetched 8 Nov 2026)
- huashu-report: README, `references/视觉系统.md`, `assets/base.css`, `references/生产流水线.md` (github.com/alchaincyf/huashu-report)
- mckinsey-style-visualization-skill: README, `references/style-system.md` (github.com/kgraph57/mckinsey-style-visualization-skill)
- Mck-ppt-design-skill: README, SKILL.md, `references/color-palette.md`, `references/team/brand-guide.md`, `references/framework/guard-rails.md`
- appautomaton/presentation: README, `brand-system/references/typography-guide.md`, `palette-guide.md`, `deck-design-pdf/SKILL.md`
- anthropics/skills: `skills/frontend-design/SKILL.md`, `skills/pptx/SKILL.md`, `skills/theme-factory/SKILL.md`
- analystacademy/flight-check README; sharptoolbox/consulting-html-ppt README; pagedjs README; talal/ilm README; grantmcdermott/quarto-revealjs-clean README; wilwaldon toolkit README; SciencePlots README
- Chrome 131 `@page` margin boxes: https://developer.chrome.com/blog/print-margins, https://developer.chrome.com/release-notes/131
- Local Hermes skills: claude-design, popular-web-designs, design-md, baoyu-infographic, powerpoint, pdf, docx, business-case-competition (`C:/Users/USER/AppData/Local/hermes/skills/...`)
