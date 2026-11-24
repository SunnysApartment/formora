# FORMORA: Conceptual Logo Design

FORMORA is a Claude Code skill that designs conceptual logos. It fuses letters, animals, objects and negative space into one mark, instead of putting an icon next to a word. It first works out the idea, then draws the mark, then packages it for real use.

The central principle: **One concept → Two visual elements → One unified symbol.**

## What you get

1. Brand questions, only if your brief leaves out something essential.
2. Five concept directions, each scored out of 100, with the reasoning behind them.
3. You pick one, combine two, or ask for more.
4. Image prompts, or images if an image tool is connected.
5. Hand-built SVG logo files, with a check at small sizes.
6. Colours, type recommendations and usage rules.
7. Mockups and a one-page brand presentation.

## How to use it

Type `/formora-logo-design` followed by your brief. Examples:

```text
/formora-logo-design
Create a conceptual logo for a premium coffee brand.
Explore typography and bird symbolism.
```

```text
/formora-logo-design
Transform the letter S into a snake.
The snake should be the letter itself.
```

```text
/formora-logo-design
Combine a lion and a crown into one minimal geometric symbol.
Avoid placing two separate icons together.
```

```text
/formora-logo-design
Create an Arabic wordmark where the Arabic letters form a falcon.
Preserve Arabic readability.
```

```text
/formora-logo-design
Explore five ways to merge a leaf and the letter A
for a sustainable architecture company.
```

At any point you can ask it to:

- Give you more concepts.
- Reject a concept.
- Combine two concepts.
- Change the visual style.
- Keep the concept and only refine the drawing.
- Show black-and-white alternatives.
- Make an Arabic or bilingual version.
- Explain how to rebuild the mark as a vector.
- Produce a complete identity presentation.

## What is in the folder

- `SKILL.md`: the instructions Claude follows.
- `references/`
  - `design-principles.md`: the design rules the work must follow.
  - `conceptual-techniques.md`: the ways to fuse two ideas into one mark.
  - `typography-guide.md`: letters, wordmarks, Arabic and bilingual type.
  - `quality-checklist.md`: scoring and rejection checks.
  - `svg-construction.md`: how marks are built as SVG.
  - `identity-system.md`: colours, type and usage rules.
  - `reel-observations.md`: notes from the reference reels.
- `templates/`
  - `concept-brief.md`: the brand and concept brief.
  - `image-generation-prompt.md`: the structure for image prompts.
  - `logo-specification.md`: the final logo specification.
  - `preview.html`: a page to preview the logo files.
  - `export-png.html`: makes PNG copies of an SVG with a browser screenshot.
  - `mockup.html`: places the real logo file on a photo (perspective, grain, shadow).
  - `brand-presentation.html`: the brand book (A4 landscape pages, printed to PDF).

## Installation

The skill lives in a project's `.claude/skills/formora-logo-design/` folder, or in `~/.claude/skills/formora-logo-design/` to use it in every project. To install or update, copy the whole folder there:

```bash
mkdir -p ~/.claude/skills
cp -R formora-logo-design ~/.claude/skills/
```

## Honest limits

- Generated images are sketches. They can misspell words, and they are not vectors.
- Hand-built SVG suits bold, geometric marks. Complex illustration, or final outlining of a custom wordmark, may need a designer with a vector editor.
- The reference reels are inspiration, not rules. Their contents have not been verified, and the skill extracts techniques from them without copying their logos.
- The skill only claims what it has done. It will not say it made an image or file unless that worked.

## Not included yet

Planned for version 2.0:

- A larger concept exploration space.
- More systematic discovery of visual relationships.
- Concept similarity detection.
- Iterative visual critique.
- Better Arabic and multilingual typography support.
- Brand-specific design memory within a project.
