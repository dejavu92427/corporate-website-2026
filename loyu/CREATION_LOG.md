# LO-YU Redesign — Creation Log

Date: 2026-08-06

## Brief

Reimagine the existing LO-YU Interior Design website as a contemporary architectural / interior-design portfolio experience. The supplied WAA site was used as a directional reference for pacing, visual hierarchy, large-format imagery, whitespace, and project-first storytelling rather than as a layout to copy.

## Creative direction

The central idea is **“Space, made for people.”** The page shifts LO-YU away from a conventional corporate-information presentation and toward an editorial portfolio that lets spatial work carry the brand.

Key decisions:

- Use a full-viewport photographic hero to establish atmosphere immediately.
- Keep typography restrained, oversized, and architectural, with generous negative space.
- Introduce LO-YU through experience and outcomes rather than a dense company-history block.
- Surface the existing credibility signals — roughly 30 years of experience, a multidisciplinary design team, and 300+ commercial projects — as quiet editorial statistics.
- Make selected projects the visual center of the page with an asymmetric image grid.
- Use a dark interlude for the design / build / use philosophy to create rhythm and contrast.
- Reduce the service process to three understandable stages: design planning, construction, and completed-space use.
- End with a direct project-start CTA instead of a generic corporate footer experience.

## Visual system

The palette is intentionally muted: warm off-white, charcoal, soft gray, and natural photographic tones. The intent is to avoid decorative UI competing with interior photography.

The page uses no framework and keeps the prototype as a single responsive HTML document so it can be reviewed directly through GitHub Pages. Desktop composition is deliberately spacious; mobile collapses the editorial grids into a straightforward vertical narrative.

## Prototype content

The current imagery is presentation imagery sourced through Unsplash URLs and is not intended to represent completed LO-YU projects. Production should replace these with approved LO-YU photography and verify all company facts, project labels, contact destinations, and brand assets before launch.

## Iteration notes

This is a first-pass concept demo, not a finished production site. The next useful iteration would focus on real project photography, actual project taxonomy, LO-YU's logo / type system, richer project-detail transitions, and final bilingual content if required.

## Deployment

Prototype: `loyu/index.html`

The repository includes a GitHub Pages deployment workflow. Pages enablement was added to the workflow so deployment can enable Pages automatically when the workflow runs.
