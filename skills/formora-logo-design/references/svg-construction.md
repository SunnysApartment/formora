# SVG Construction

How to hand-build the approved mark as a real, editable SVG. Load this at
workflow step 6 (Build the vector) or when the user asks for vector artwork.

## 1. When to build

- Build only after the user has approved a concept and it works in
  monochrome. Do not vectorise an unapproved direction.
- A generated image is a sketch to rebuild from, never the deliverable. Do
  not trace it, embed it, or describe it as vector artwork.
- Write every coordinate yourself. A file that wraps or auto-traces a raster
  is not an SVG logo.

## 2. Method

1. **Grid and viewBox.** Draw the symbol on a square working grid such as
   `0 0 512 512`. Snap key points to whole numbers or a simple module (for
   example 8 or 16 units). When the art is done, trim the viewBox to the
   artwork bounds plus clear space (for example 1/8 of the mark's height on
   each side).
2. **Few primitives.** Build from circles, rectangles, arcs and short
   paths. Every node must have a reason to exist. Fewer nodes make cleaner
   curves, smaller files and easier edits.
3. **Fills, not strokes.** Final art uses filled shapes. If a stroke is the
   simplest way to draft a shape, say that it must be outlined (converted to
   a filled path) before production, or redraw it as a filled path.
4. **Negative space.** Cut holes with `fill-rule="evenodd"` on one compound
   path, or draw the cut-out as its own shape. Never fake a hole by painting
   a white shape on top: it breaks on any coloured or dark background.
   Merge shapes that touch into one outline path. Separate shapes placed
   edge to edge show hairline seams when rendered, even though the
   coordinates meet exactly.
5. **`currentColor`.** Set `fill="currentColor"` so one file serves
   positive, reversed and one-colour use; the surrounding CSS or `color`
   attribute sets the ink.
6. **Structure.** Group and id the parts: `<g id="symbol">`,
   `<g id="wordmark">`. Add a `<title>` with the brand name for
   accessibility. Strip editor metadata, comments and unused `<defs>`.

### Example: negative-space cut-out

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="32 32 448 448">
  <title>Example mark</title>
  <g id="symbol" fill="currentColor">
    <!-- disc with a triangular counter; evenodd turns the inner subpath into a hole -->
    <path fill-rule="evenodd"
          d="M56 256a200 200 0 1 0 400 0a200 200 0 1 0 -400 0Z
             M216 176L336 256L216 336Z"/>
  </g>
</svg>
```

The triangle is centred on its centroid (x = 256), not its bounding box, so
it looks centred in the disc. The viewBox keeps 24 units of clear space
around the 400-unit disc.

## 3. Text

- A `<text>` element depends on the font installed on the viewer's machine.
  It is not production-safe. Say so plainly whenever you use it.
- Option A: build the letters as paths by hand. This is practical for
  geometric letterforms, monograms and short custom wordmarks.
- Option B: deliver the wordmark as live text with the font named in
  `font-family`, and label the file and your message: "Wordmark is live
  text. Needs outlining in a vector editor with the licensed font."
- Never claim live text is final artwork.
- Arabic wordmarks: use live text with a named font and the same
  "needs outlining" label, unless you have hand-built the letters as
  paths. Hand-built Arabic must keep correct joining forms, baseline and
  dot placement; if you cannot guarantee that, use live text.

## 4. Optical alignment

- **Overshoot.** Round and pointed shapes extend past flat edges to look
  the same size: about 1 to 3% of the letter or shape height for curves
  (for example 8 to 12 units on a 512 grid), more for sharp points.
- **Visual vs mathematical centring.** Centre by visual mass, not by
  bounding box. Triangles, arrows and play shapes sit on their centroid;
  top-heavy shapes sit slightly above the mathematical centre.
- **Consistent weight.** Keep one stroke weight (or a deliberate, small set
  of weights). Horizontals can be slightly thinner than verticals so they
  look equal.
- **Even counters and gaps.** Counters, cut-outs and gaps between elements
  should look equal in area and rhythm, not just in measured width.
- **Small-size floor.** At 16 px, a 512-unit grid gives 32 units per pixel.
  Keep gaps and strokes at or above about 1.5 px at the smallest intended
  size (roughly 48 units at 16 px on a 512 grid). Anything thinner fills in
  or vanishes; move it to the small-size symbol or drop it.

## 5. Responsive variants

| Variant | Contents | Use |
|---|---|---|
| Horizontal lockup | Symbol + wordmark side by side | Website headers, documents, wide placements |
| Stacked lockup | Symbol above wordmark | Square or tall spaces, packaging, social covers |
| Symbol | Symbol alone | Avatars, app icons, stamps, where the brand is already known |
| Small symbol | Symbol with detail removed, gaps widened | Favicons, 16 to 32 px, embroidery, low-quality print |
| Wordmark | Name alone | Where the symbol would be too small or repeated |

Derive each variant from the same source geometry. The small symbol may
drop inner detail and thicken parts, but it must still read as the same
mark.

## 6. Files and naming

Keep sources in a `logo/` folder in the user's project:

```text
logo/
├── logo-primary.svg        horizontal lockup
├── logo-stacked.svg        stacked lockup
├── symbol.svg
├── symbol-small.svg
├── wordmark.svg
├── logo-primary-black.svg  explicit #000000 fill
├── logo-primary-white.svg  explicit #FFFFFF fill
└── png/                    raster exports, if a converter exists
```

- The main files use `currentColor`. Also export explicit `-black` and
  `-white` copies of each file for users whose tools ignore
  `currentColor` (many editors and upload forms render it as black).
- Add brand-colour copies (`-color`) only after the palette is approved.

## 7. Validation

Do every step before saying the file works:

1. Well-formed XML: `xmllint --noout logo/symbol.svg` when `xmllint` is
   available (check with `command -v xmllint`). If it is not, say the XML
   check was not run.
2. No raster: confirm the file contains no `<image>` element
   (`grep -c '<image' file.svg` returns 0).
3. Render: open `templates/preview.html?svg=<path>` in a browser. Look at
   the mark at 16, 32, 64 and 256 px, in one colour, on a light and a dark
   background.
4. Look at the actual render (screenshot it) and check: holes are real
   holes on dark backgrounds, nothing fills in at 16 px, curves are smooth,
   alignment looks right.
5. Report what you checked and what you could not check.

## 8. PNG export

- Check which converter is installed before claiming any export:
  `command -v rsvg-convert magick inkscape`.
- Examples:
  - `rsvg-convert -w 1024 logo/symbol-black.svg -o logo/png/symbol-1024.png`
  - `magick -background none -density 384 logo/symbol-black.svg logo/png/symbol-1024.png`
  - `inkscape logo/symbol-black.svg --export-type=png --export-width=1024 --export-filename=logo/png/symbol-1024.png`
  - macOS fallback: `qlmanage -t -s 1024 -o logo/png logo/symbol-black.svg`
    (output may have a white background). `sips` may convert SVG on some
    macOS versions; check the result.
- Export from the `-black` and `-white` files: converters may not resolve
  `currentColor`.
- Open at least one PNG to confirm it rendered. If no converter is
  available, say so and leave the export to the user; do not claim it.

## 9. Honest limits

- Hand-written SVG suits geometric, bold marks: monograms, symbolic
  geometry, negative-space cuts, simple silhouettes.
- Complex organic illustration (detailed animals, hair, feathers, freeform
  calligraphy) may need a human designer working in a vector editor. When
  that applies, tell the user, deliver the best simplified version you can
  build, and provide a written reconstruction plan.
- Never call a raster, a traced image or an unvalidated file
  production-ready vector artwork.
