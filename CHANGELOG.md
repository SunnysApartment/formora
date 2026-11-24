# Changelog

All notable changes to FORMORA are recorded here. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and the project uses
[Semantic Versioning](https://semver.org/).

## [1.4.0] — 2026-11-24

### Added
- `templates/mockup.html`: places the real logo file on a photo by perspective, with paper grain, light and four
  finishes (print, letterpress, stamped ink, raised lettering). Includes a grid view for reading a surface's
  corners and an outline view for checking the fit.
- `templates/export-png.html`: transparent PNG copies of an SVG using only a browser screenshot.
- PNG copies of every example logo and of the FORMORA mark, at 1024 and 256 px wide.

### Changed
- The Saqr mockups are now built with the skill's own mockup tool; the pictures are unchanged.
- PNG export guidance uses the new tool first and falls back to installed converters.
- Readme badges are stored in the repository.

## [1.3.0] — 2026-11-24

First public release. Covers roadmap versions 1.0 to 1.3 of the specification in `docs/SPEC.md`.

### Added
- **Concept engine (1.0):** nine-step workflow, seven fusion techniques, five scored concepts before any image,
  100-point scoring model and rejection criteria.
- **Vector construction (1.1):** rules for hand-built SVG marks, and `preview.html` to check a mark at
  16 to 256 px, in one colour, on light and dark.
- **Identity system (1.2):** palette with computed contrast, type pairing, clear space, minimum sizes, misuse rules.
- **Mockups and presentation (1.3):** a brand book template (A4 landscape, prints to PDF), with photo pages or
  flat layouts.
- Arabic and bilingual rules: letter forms, dots, joining, script styles and a mandatory native-reader test.
- Right-to-left support in the brand book template, tested with an Arabic page.
- Two worked examples: WOLF (Latin symbol) and صقر / Saqr (Arabic wordmark with palette, mockups and brand book).
- Mockup method that never redraws the logo: the real vector file is placed on a photo by geometry only.

### Known limits
- The Saqr lettering has not been read by a native Arabic reader.
- Every test was run in the session that built the skill, not in a fresh one.
- The brand book template is untested with a light primary colour.
