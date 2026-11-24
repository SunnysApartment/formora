# Identity System (after the logo is approved)

Load this file only when the logo is approved and works in black and white at small size. If it does not, go back to refinement; do not build an identity on an unfinished mark. Never claim a file, mockup or export exists unless the operation succeeded.

## 1. Colour palette

Start only after the mark works in black and white.

- Structure: one primary brand colour, one or two supporting colours, plus neutrals (a near-black and an off-white). No more.
- Derive colour from the brand's meaning (industry, values, audience, culture, the concept of the mark), not from trends. Write one sentence per colour saying why it was chosen.
- Check the colour does not rely on effects: no gradients unless the concept requires them.
- Give every colour as HEX and RGB. Give CMYK only as: `CMYK (approximate — confirm with the printer)`. Never present a computed CMYK as exact; screen colours and printed inks differ by stock and press. Recommend a Pantone/spot match only if the printer confirms it.
- Check contrast with the WCAG formula and state each ratio in the specification: 4.5:1 minimum for normal text, 3:1 minimum for large text (about 24 px regular or 19 px bold and up) and for UI/graphic elements. Compute, do not estimate:

```python
def lum(h):
    c=[int(h.lstrip('#')[i:i+2],16)/255 for i in (0,2,4)]
    c=[v/12.92 if v<=.03928 else ((v+.055)/1.055)**2.4 for v in c]
    return .2126*c[0]+.7152*c[1]+.0722*c[2]
def ratio(a,b):
    x,y=sorted((lum(a),lum(b)),reverse=True); return (x+.05)/(y+.05)
```

- Report a table: text colour, background colour, ratio, pass/fail for normal and large text. If the primary colour fails as text on off-white, say so and restrict it to large text, shapes and the logo; provide a darker text variant.
- Test the palette beside the logo on white, off-white, near-black and the primary colour.

## 2. Typography pairing

- One typeface for headings, one for body text. Describe each by classification (geometric sans, humanist sans, transitional serif, slab, etc.) and character (open, condensed, warm, technical, formal).
- Pair for contrast in character with harmony in proportion (x-height, width); avoid two similar faces.
- Name a specific typeface only when confident it exists and its style fits. Prefer faces with open licences (for example from Google Fonts) and always add: "Check the licence for your use (print, web, app, logo use) before adopting it."
- Arabic or bilingual brands: choose an Arabic face that matches the Latin one in weight, x-height/proportion and tone; check pairs at the same size and weight (regular with regular, bold with bold). Set both scripts, check line height (Arabic usually needs more) and mixed-direction alignment. Follow `typography-guide.md`.
- State sizes and weights for H1, H2, body and caption. Check body text readability at the smallest size.
- If the wordmark uses custom letterforms, state that the body/heading faces support it and are not a substitute for it.

## 3. Logo usage rules

- **Clear space:** define in units of an element of the logo itself, for example `x` = the height of the main letter (or the symbol's counter, or the stroke width). Required clear space = 1x on all sides (state the actual multiple that fits the mark). Include a diagram or a plain description in the specification.
- **Minimum sizes:** give a value for each version (full logo, symbol, wordmark) for print (mm) and screen (px). Derive them by testing; do not invent. Test by reducing the artwork until the fused element or the second meaning is lost, then set the minimum above that. Below the minimum, switch to the simplified or symbol-only version if one exists (see responsive variations).
- **Version per background:** list which file goes on which background: full colour on white/off-white; reversed (light mark) on near-black and on the primary colour when contrast passes; one-colour black or white on photos, textures or single-ink print. Check each pairing for contrast.
- **Misuses (show or list):** stretching or squashing; changing the proportions of symbol and wordmark; recolouring outside the palette; adding shadows, glows, outlines, gradients or 3D effects; placing on busy images or low-contrast backgrounds; rotating or skewing; rearranging or resizing elements; replacing the typeface; cropping; adding or removing parts of the mark.

## 4. Light and dark variations

- Produce at least: positive (dark mark on light), reversed (light mark on dark), full colour, one-colour black, one-colour white.
- A reversed version is not an automatic inversion. Check that negative space still reads, that thin parts do not vanish, and that the primary colour keeps adequate contrast on dark; adjust the tint if needed and record it.
- List every variation with file name, intended background and its contrast ratio.
- Vector artwork requirement: if only raster artwork exists, say variations are raster previews and a vector reconstruction is still required for production.

## 5. Mockups and applications

Applications to show: business card, packaging, signage/storefront, social media profile and post. Mockups are illustrations, not production files. Say so wherever they are presented.

**If an image-generation tool is available in the session:**
- Use the approved logo file as the reference image. Brief each mockup separately: object and format, materials and finish, camera angle and lighting, background, where the logo sits and at what relative size, palette (HEX values), and exclusions (no extra text, no redrawn logo, no invented slogans, no watermarks).
- Always add: "Place the supplied logo exactly as is. Do not redraw, restyle, recolour, crop, mirror or distort it."
- Check each result: compare the logo in the mockup with the approved artwork (shape, proportions, letterforms, spelling, negative space, colours). If the tool altered the mark, say so and discard that result; try again with a simpler brief. Do not present an altered logo as the approved one. Also check for garbled text, wrong colours and unrealistic physical details.
- Keep the prompts used, so the user can reproduce them.

**If no image tool is available, or it redraws the logo:** take free-licence blank photos (business card, box, sign, phone), and place the real logo file on them by geometry only (perspective, blend, grain, shadow), never by regenerating it. Record each photo's source and licence. Failing that, keep the "flat layouts" page in `templates/brand-presentation.html` (card faces, label, sign, profile and post tiles) and state that these are flat layouts, not photographic mockups.

## 6. The identity presentation

1. Copy `templates/brand-presentation.html` into the user's project (do not edit the template in the skill folder).
2. Replace every `{{PLACEHOLDER}}` token with real content: brand name, headline and concept, brand line, logo files, palette (HEX/RGB/approximate CMYK, one reason per colour, contrast table), typography, usage rules, applications, files and status notes. The template is a brand book of fixed A4 landscape pages. It assumes the dark colour is a near-black and the light colour an off-white; set the three `--on-…` text colours so every colour band passes contrast. The brand line is written from the brief: if it rests on assumed values, tell the user it is your wording.
3. Search the finished file for any remaining `{{`; none may be left. Delete whole pages you cannot fill rather than leaving filler (page and section numbers renumber themselves). Keep either the photo pages or the flat-layouts page, never both.
4. Print it to PDF with no page margins (the command is in the template's header comment), then look at every page: logo is not distorted, images load, no text overflows a page or a colour band, light/dark versions sit on the right backgrounds.
5. Fill `templates/logo-specification.md` as the written specification (concept, construction notes, deliverables and their status, colour, type, clear space, minimum sizes, misuse, variations, contrast ratios). Mark any deliverable that is only raster or still needs vector reconstruction.
6. Tell the user exactly which files were created and which items remain unconfirmed (CMYK with the printer, font licences, vector reconstruction).
