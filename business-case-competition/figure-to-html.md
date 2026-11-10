# Recreate proposal/deck figures and covers as editable HTML/CSS (and back to PDF)

Use this when the user wants pages from their competition PDF (infographics, exec summary, pillar tables, roadmaps, the cover) turned into editable HTML/CSS. Figures and covers in these PDFs are usually raster images, so there is no text layer to extract.

## Procedure
1. **Clarify the target form first.** "Ubah jadi HTML/CSS" can mean three things: editable figures, the whole proposal as a website, or HTML slides. Ask with the clarify tool, offering editable figures first. If they don't name a figure, start with the Executive Summary (the highest-value figure), then offer the rest.
2. **Inventory the PDF** with PyMuPDF (`import fitz`, Pillow for crops): page count, `get_text()` per page, and the count from `get_images()`. A page whose text holds only the caption means the figure is an image. `get_text('dict')` gives the real fonts, sizes and colours of headings and captions. Use the python that has these packages installed, and install them with that same interpreter's pip.
3. **Render crops at 200 dpi** (`page.get_pixmap(dpi=200, clip=fitz.Rect(...))`), splitting a full-page figure into 2 crops so small text stays legible. Then use vision_analyze to transcribe ALL text verbatim and estimate colours.
   - Pass vision_analyze a native Windows path. In git-bash `$TMPDIR` can resolve to `/tmp`, which is AppData\Local\Temp, not the Hermes scratch dir. Convert with `cygpath -w` instead of guessing the path.
   - Sample exact colours from the extracted image with `PIL.Image.getpixel` instead of eyeballing them.
4. **Write one standalone HTML file per figure** into `<pdf folder>/<PROJECT>-HTML/figure-<id>-<slug>.html`. Conventions:
   - Put all colours and radius/shadow tokens in `:root` CSS variables at the top, with Indonesian comments. That way the user can recolour by editing one line.
   - Give each card/pillar its own colour via `style="--c:var(--blue)"` and keep one shared class.
   - Lay it out with CSS grid: section header (numbered circle, uppercase title, fading rule) and stat cards with a coloured top border. Build chevron phase arrows with `clip-path: polygon(...)`.
   - Copy the original caption exactly (`Figure X.` in bold plus an italic title).
   - Add `@media (max-width:760px)` (stack grids, drop the chevrons) and `@media print`.
   - Use plain Arial, no external assets, and no JS.
5. **Covers (one full-page raster image).** Rebuild every piece of text as HTML. Crop only the illustration, logos and team photos into `assets/`.
   - Get the real image xref from `page.get_image_info(xrefs=True)`. The first entry of `get_images()` can be a different, smaller image, and crop coordinates computed against it fall outside the picture.
   - Make photos clean circles: crop tightly inside the original ring, then apply a PIL ellipse alpha mask, saved as PNG. A loose crop keeps the original ring as an inner arc.
   - Fade the illustration's edges into the background with a CSS `mask-image` linear-gradient. Set `z-index` on the title block so the illustration never covers the text.
   - Size the page as fixed A4 (794x1123px plus `@page{size:A4;margin:0}`). Google Fonts are fine, but give a system fallback.
   - Tell the user the folder must be moved together with `assets/`.
6. **Verify in the browser**: open it via `file:///` and set the viewport to about 1080 wide (860 for A4). Take a full-page screenshot (`cdp('Page.captureScreenshot', captureBeyondViewport=True)`) and compare it with the original crop.
   - Check overflow with `js("[...document.querySelectorAll('.card')].map(e=>[e.scrollWidth,e.clientWidth])")`. Wide numbers such as "+Rp44 billion" wrap or overflow in narrow grid cells; fix them with a smaller font plus `white-space:nowrap`.
7. **Make the PDF yourself when asked**: `cdp('Page.printToPDF', printBackground=True, preferCSSPageSize=True, margin*=0)`, after clearing the body padding and background. Re-open the PDF with PyMuPDF to confirm the page count and size (A4 is about 595x842 pt), and render it once to check for white margins.
8. **Show it artifact-style**: `desktop_preview(action=open, url=<file path>, label=...)`, one tab per HTML/PDF file, plus `MEDIA:<path>` in the reply.
9. **Reply in Indonesian, beginner-level**: how to open it (double-click), how to edit text (find and replace in VS Code or Notepad), how to edit colours (the `:root` vars), and how to put it back into the proposal (Ctrl+P, margin None, Background graphics on; or take a screenshot).
