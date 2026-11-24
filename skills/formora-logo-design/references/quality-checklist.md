# Quality Checklist

Load this when scoring concepts, reviewing a generated image, or approving a finished SVG.

## 1. Scoring model (100 points)

The score is a **decision aid, not an objective measurement** of artistic quality. Every score comes with a short explanation and the single most important improvement.

| Criterion | Weight | High marks | Low marks |
|---|---|---|---|
| Conceptual intelligence | 20 | The idea is surprising, logical and explainable in one sentence | Obvious or arbitrary pairing; no reason these two things meet |
| Visual integration | 20 | Elements share one contour or structure and cannot be pulled apart | Elements sit side by side or merely overlap |
| Brand relevance | 15 | Tied to the name, industry or values; could not serve a random business | Generic; fits almost any brand |
| Clarity and recognition | 15 | Primary subject reads instantly; second meaning is discoverable | Hidden meaning unrecognisable, or the mark is confusing |
| Memorability | 10 | Simple, distinctive silhouette; one idea worth remembering | Forgettable, stock-logo feel, or too busy to recall |
| Typography quality | 10 | Letters well spaced, proportioned and readable where required | Misspelt, unreadable without reason, clumsy spacing |
| Scalability and reproduction | 10 | Holds up small, in one colour, on light and dark | Collapses at small size or depends on colour and effects |

### Score bands

| Score | Meaning |
|---|---|
| 90-100 | Strong candidate for refinement and production |
| 80-89 | Promising; refine execution |
| 70-79 | Viable direction with meaningful weaknesses |
| Below 70 | Reconsider or substantially redesign |

### Table format for presenting five concepts

Copy this. Keep each explanation to one line.

| # | Concept | Int. /20 | Integ. /20 | Brand /15 | Clarity /15 | Memory /10 | Type /10 | Scale /10 | Total | Why | Top improvement |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 01 | | | | | | | | | | | |
| 02 | | | | | | | | | | | |
| 03 | | | | | | | | | | | |
| 04 | | | | | | | | | | | |
| 05 | | | | | | | | | | | |

Int. = conceptual intelligence, Integ. = visual integration, Memory = memorability, Type = typography quality, Scale = scalability.

Score concepts honestly and spread them; five near-identical scores means the concepts were not differentiated or the scoring was not real.

## 2. Rejection criteria

Reject or revise a concept when:

- [ ] The two visual elements are merely placed next to each other.
- [ ] The hidden meaning is impossible to recognise.
- [ ] The brand name becomes unreadable without a deliberate reason.
- [ ] The silhouette collapses at small sizes.
- [ ] The mark relies on colour or effects to communicate its meaning.
- [ ] The concept is generic and could represent almost any business.
- [ ] The visual construction has no clear relationship to the brand.

## 3. Mandatory practical checks before approval

- [ ] Does the design communicate the intended idea?
- [ ] Are the elements genuinely integrated?
- [ ] Can the symbol be recognised without colour?
- [ ] Does it remain clear at small sizes?
- [ ] Is the wordmark readable where required?
- [ ] Does it work on light and dark backgrounds?
- [ ] Can the approved artwork be reproduced as vector paths?
- [ ] Does it have a distinctive relationship to the brand?

Any "no" blocks approval until fixed or consciously accepted by the user.

## 4. Generated image review

A generated image is exploration, not production artwork. Never call it vector or production-ready.

- [ ] **Spelling:** read the brand name letter by letter against the exact spelling. Image models often get this wrong; for Arabic also check joining and contextual forms.
- [ ] **Letter recognition:** every letter the concept depends on is still identifiable.
- [ ] **Silhouette:** fill the mark solid black; the subject still reads and the shape is coherent.
- [ ] **Spacing:** even rhythm between letters and between symbol and wordmark; no collisions or accidental gaps.
- [ ] **Optical balance:** visual weight is centred; no side feels heavier without intent.
- [ ] **Negative space:** hidden shapes are discoverable and do not confuse the primary read.
- [ ] **Small size:** shrink to about 32 px; the idea survives.
- [ ] **No stray effects:** no gradients, shadows, bevels, 3D, mockup scene, random symbols or extra text.
- [ ] **Concept fidelity:** the fusion matches the approved construction brief.

Rule: **do not change the concept when only execution needs improvement.** List specific fixes (shape, spacing, proportion, letter shape) and regenerate with the same concept. Change the concept only if it fails a rejection criterion, and say so.

## 5. Finished SVG review

Use `templates/preview.html` for the visual checks below (renders the SVG at several sizes, in one colour, and reversed).

- [ ] **Renders:** displays correctly in the browser preview with no missing parts.
- [ ] **Valid:** well-formed XML, proper `viewBox` proportional to the design, no errors on load.
- [ ] **No embedded raster:** no `<image>`, base64 or linked bitmaps; custom shapes are paths.
- [ ] **Intentional fills and strokes:** nothing left at default black by accident.
- [ ] **Reads at 16 px:** the symbol is still recognisable.
- [ ] **Works in one colour:** a single flat colour keeps the idea intact.
- [ ] **Works reversed:** light mark on a dark background keeps the idea, including negative-space details.
- [ ] **Source preserved:** the editable file is saved so the artwork can be revised.

Only claim an SVG, PNG or export exists after the file was actually written and checked.
