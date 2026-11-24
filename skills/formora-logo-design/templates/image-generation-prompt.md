# Image Generation Prompt

Use only the image tools available in the active environment. Do not assume a provider.

## Template

```text
Create a professional conceptual logo for [BRAND NAME], a brand in [INDUSTRY].

CORE CONCEPT:
Combine [PRIMARY ELEMENT] and [SECONDARY ELEMENT] into one unified visual mark.

VISUAL FUSION:
[Explain exactly how the elements connect, overlap, transform, or share geometry.]

TYPOGRAPHY:
[Describe the letterforms, wordmark, readability, and typographic integration.]

CONSTRUCTION:
[Describe silhouette, proportions, negative space, geometry, and composition.]

STYLE:
[Describe the intended visual language.]

COLOR:
[Specify monochrome exploration or the selected palette.]

BACKGROUND:
Clean, plain background.

RESTRICTIONS:
No generic icon placed beside text.
No unnecessary decorative elements.
No mockup presentation.
No random symbols.
No unnecessary gradients, shadows, or 3D effects.
Prioritize conceptual clarity and a recognizable silhouette.

OUTPUT:
A clean, centered logo concept suitable for professional brand identity development.
```

## Filling rules

- **Fusion precision.** Never write "make a modern animal logo". In VISUAL FUSION, state the exact subjects, how each is represented, the construction relationship (which stroke becomes which body part), composition and silhouette, line weight and shape language.
- **Letters.** Name the letters that must stay recognisable and the one that carries the construction.
- **Monochrome first.** COLOR is "single flat black on white" until the concept works; add palette later.
- **Minimal text.** Generators misspell. Ask for the symbol alone, or at most the brand name; check spelling letter by letter and plan to set type yourself.
- **No mockups.** Keep the RESTRICTIONS block; no business cards, signage or scenes.
- **Do not claim vector.** Output is raster exploration; vector reconstruction is a separate step.

## Generation sequence

1. Generate monochrome concept explorations.
2. Compare the visual logic of the outputs.
3. Select the strongest construction.
4. Refine the shape and typography.
5. Explore color only after the concept works in monochrome.
6. Reconstruct or trace the approved mark as vector artwork when required.

## Filled example (fictional brand)

Brand: NORVA, a ceramics studio.
- CORE CONCEPT: Combine the letter N and a heron standing in water into one unified mark.
- VISUAL FUSION: The N's diagonal is the heron's long neck; the left stem is one leg, the right stem the other, the beak formed by the diagonal's upper terminal.
- TYPOGRAPHY: Only the N is shown; it must stay readable as an N. No other text.
- CONSTRUCTION: Solid silhouette, uniform stroke, a small circular counter as the eye, centered, generous margin.
- STYLE: Minimal geometric, flat, confident, hand-made warmth in the curves. COLOR: black on white only.
