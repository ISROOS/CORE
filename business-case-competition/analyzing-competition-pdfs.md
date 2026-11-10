# Analyzing competition PDFs (own entries, other teams' winners, public winners)

Use this when the user drops a ZIP or folder of proposals or decks to "learn the pattern". The output is one analysis file per entry, merged into `05-wijaya-team-patterns.md`.

## Procedure
1. **Unzip and inventory** with the Python that has pymupdf+pillow (`C:/Users/USER/AppData/Local/Programs/Python/Python312/python.exe`). Use `zipfile.extractall` into `$LOCALAPPDATA/hermes/cache/scratch/<batch>/`, then print size and path per file. Folder tags carry the result: 🥇/🥈/🥉, `[SemiFinal]`, `[Final Top 4]`, `[Preliminary]`. Report empty folders to the user.
2. **Fan out** 4–5 subagents grouped by competition type (BCC / BPC / MCC / UI-UX / design research), so each one compares like with like. Every subagent gets the same shared setup block:
   - the Python path above, and an instruction to keep its scripts in its OWN `renders/<name>/` subfolder, because siblings overwrite shared helper scripts;
   - list paths with `os.listdir` from the parent dir, because emoji folder names fail when passed as literal path strings;
   - per PDF: page count and size, `page.get_fonts()`, `get_text()` (image-only PDFs have no text, so rely on vision), 3×3 or 4×3 contact sheets at about 55 dpi viewed with vision_analyze, about 110 dpi zooms of the cover, exec summary, financials and roadmap pages, and a PIL quantize palette (hex values are approximate);
   - recompute financial KPIs in Python and flag anything that does not reconcile;
   - read `05-wijaya-team-patterns.md` first, so the analysis can say what differs from the house style;
   - summarize only and never copy long passages, because third-party entries are copyrighted.
3. **Analysis template** (one md per entry). Sections: Competition/type/round/placement (otherwise "winner per user, placement unknown"); Format; Section outline with page ranges; Storyline pattern (hook, problem→root cause→solution→impact, solution naming); Frameworks; Numbers (sizing, financials, KPIs, sample sizes, sources); Visual design system (palette, fonts, grid, components, charts, illustration, density); Why it won / Strengths; Weaknesses; Differences vs Wijaya house style; Reusable techniques.
4. **Merge.** Copy files to `references/portfolio/` (prefix other teams' entries with `others_`). Then update `05` in place: results map, "adopt these" techniques, "Wijaya already stronger" list, and recurring mistakes. Fold a lesson that is already listed into the existing bullet; do not add a second copy.
5. **Report** in Indonesian: what was learned, what to adopt, what to keep, and caveats (missing placements, approximate colours, empty folders).

## Searching for public winning entries
- Tag each find as `verified (source says won)`, `claimed by uploader` or `unverified`, and keep a manifest JSON (title, competition, year, placement, team, url, file, verification).
- Download only freely accessible files. Skip anything behind a login, a paywall, or a piracy mirror.
- A file in a batch can be the organiser's case brief rather than an entry. Treat it as a rubric source: it often publishes weights and what the judges want.
