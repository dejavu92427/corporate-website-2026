# LO-YU Redesign — Reproduction Log

Date: 2026-08-06

## 0. Goal

Reproduce the LO-YU redesign demo from the original brief, source sites, design decisions, content mapping, implementation constraints, and deployment steps recorded here.

Expected output:

- Repository: `dejavu92427/corporate-website-2026`
- Page: `loyu/index.html`
- Public path after GitHub Pages deploy: `/corporate-website-2026/loyu/`
- Implementation: one self-contained responsive HTML file; CSS embedded in `<style>`; no JS framework or build step.

## 1. Original request / inputs

The task was to redesign the existing LO-YU website with the supplied WAA website as the visual-direction reference, first as a demo page.

Source site to inspect:

- LO-YU existing website: `https://www.loyu.com.tw/index.php`

Reference site to inspect:

- WAA: `http://www.waa.com.tw/`

Instructional intent:

1. Preserve LO-YU as the actual brand/content subject.
2. Do not clone WAA pixel-for-pixel.
3. Extract WAA's higher-level design language: architecture-first imagery, strong whitespace, restrained navigation, editorial typography, large project presentation, and minimal decorative UI.
4. Turn the older corporate presentation into a contemporary interior-design / architecture portfolio landing page.
5. Produce a directly visitable static HTML prototype.

If either source URL is inaccessible during reproduction, report that explicitly rather than inventing unseen content. The implementation snapshot in `loyu/index.html` is the fallback reference for the already-produced result.

## 2. Information extracted from LO-YU

The redesign used these business/content signals from the source material available during the task:

- Brand: LOYU / 羅鈺室內設計
- Business domain: interior design / workplace / commercial / residential space
- Approximate history signal: nearly 30 years
- Team signal used in prototype: about 30 design professionals
- Portfolio credibility signal used in prototype: 300+ commercial projects
- Core operating story: design planning → construction execution → completed-space use / service
- Contact destination used in prototype: `https://www.loyu.com.tw/contact.php`

These values must be re-verified against the client's current approved material before production launch. For reproduction of this specific demo, retain them because they are part of the recorded artifact.

## 3. Reference analysis: what to borrow from WAA

Do not reproduce individual WAA components mechanically. Recreate these principles:

- **Project-first hierarchy:** imagery should dominate before company explanation.
- **Architectural scale:** large viewport-filling compositions instead of card-heavy corporate UI.
- **Whitespace:** sections breathe; avoid dense boxed modules.
- **Editorial typography:** oversized headings with tight tracking, small uppercase/letter-spaced section labels.
- **Asymmetry:** project gallery should feel composed rather than like a uniform CMS grid.
- **Restrained palette:** neutral background, charcoal text, photography as the primary color source.
- **Low UI chrome:** links and borders are quiet; avoid gradients/buttons/shadows unless serving image legibility.
- **Rhythm through contrast:** insert one dark section between light portfolio sections.

## 4. Creative concept

Central line:

> Space, made for people.

Design thesis:

LOYU should feel like a design practice before it feels like a conventional company website. The visitor should first experience space and atmosphere, then encounter credibility, projects, process, and contact.

Narrative order:

1. Atmosphere / brand promise
2. Credibility / company introduction
3. Selected work
4. Design-build philosophy
5. Project inquiry CTA

## 5. Exact page architecture

Build the page in this order.

### A. Absolute header over hero

Left:

- `LOYU`
- small subtitle: `INTERIOR DESIGN ENGINEERING`

Right anchor navigation:

- PROJECTS → `#projects`
- ABOUT → `#about`
- PROCESS → `#process`
- CONTACT → `#contact`

Header height: about 88px desktop, 70px mobile. Use a subtle translucent white bottom border over the hero.

### B. Full-screen hero

- Height: `100svh`, minimum about 700px.
- Background: full-bleed interior image plus left-to-right dark overlay for text readability.
- Eyebrow: `Interior · Workplace · Architecture`
- H1: `Space, made` / `for people.` on two lines.
- Supporting Chinese paragraph explaining integrated planning, execution, and use.
- Vertical `SCROLL ↓` marker at bottom-right.

Prototype hero image used:

`https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&w=2200&q=85`

### C. About / credibility

Two-column editorial layout: narrow section label at left, content at right.

Section label:

`01 — ABOUT LOYU`

Main statement:

`近三十年，我們持續把複雜的空間需求，轉化為清晰而耐用的設計。`

Follow with two short Chinese paragraphs explaining integrated design/construction and long-term usability.

Statistics row:

- `30` — YEARS EXPERIENCE
- `30` — DESIGN PROFESSIONALS
- `300+` — COMMERCIAL PROJECTS

### D. Selected projects

Section label: `02 — SELECTED WORK`

Large title: `Projects`

Use an asymmetric desktop grid:

- left column ~1.3fr, one 720px-tall image
- right column ~0.7fr, two ~351px-tall images with 18px gap

Prototype images:

1. `https://images.unsplash.com/photo-1497366811353-6870744d04b2?auto=format&fit=crop&w=1400&q=85`
2. `https://images.unsplash.com/photo-1497366216548-37526070297c?auto=format&fit=crop&w=1000&q=85`
3. `https://images.unsplash.com/photo-1600566753190-17f0baa2a6c3?auto=format&fit=crop&w=1000&q=85`

Prototype captions:

- Corporate Workplace / OFFICE · TAICHUNG
- Business Interior / COMMERCIAL
- Private Residence / RESIDENTIAL

Images gently scale to ~1.025 on hover over ~0.7s.

Important: these Unsplash images are presentation placeholders and must not be represented as actual LO-YU projects.

### E. Dark philosophy / process section

Background: approximately `#1b1b1a`; light text.

Label: `03 — OUR APPROACH`

Oversized statement:

`Design with experience.`
`Build with confidence.`
`Live with ease.`

Render the middle line in a softer gray to create hierarchy.

Below it, create three equal process cells separated by 1px lines:

01 設計規劃
- understand needs and constraints; propose spatial strategy

02 裝修工程
- integrate construction and site management; execute design accurately

03 完工使用
- emphasize handover, real-world use, and continued responsibility

### F. Contact CTA

Two-column layout.

Large left headline:

`Let's shape`
`your space.`

Right:

- label `04 — START A PROJECT`
- short Chinese invitation for office/factory/commercial/residential planning
- outlined CTA `CONTACT LOYU →`
- CTA destination: `https://www.loyu.com.tw/contact.php`

### G. Footer

Quiet two-sided footer:

- `© 2026 LOYU INTERIOR DESIGN ENGINEERING`
- `REDESIGN CONCEPT DEMO`

## 6. Visual tokens / implementation targets

Use approximately these tokens to reproduce the current result:

```css
:root {
  --ink: #161616;
  --paper: #f3f1ec;
  --muted: #77736b;
  --line: #d6d1c7;
}
```

Typography stack:

```css
Arial, 'Noto Sans TC', sans-serif
```

Global content width:

```css
width: min(94vw, 1500px);
margin: auto;
```

Desktop section spacing: about `120px 0`.

Key typography targets:

- Hero H1: `clamp(48px, 8vw, 128px)`, line-height ~`.9`, tracking ~`-.055em`, medium/regular weight.
- About H2: `clamp(32px, 4.5vw, 68px)`.
- Projects H2: `clamp(45px, 7vw, 100px)`.
- Philosophy statement: `clamp(38px, 6vw, 88px)`.
- Contact H2: `clamp(50px, 8vw, 120px)`.
- Section labels: around 11px with `.2em–.28em` letter spacing.

Avoid rounded cards, heavy drop shadows, bright accent colors, and generic SaaS UI patterns.

## 7. Responsive behavior

Breakpoint: approximately `800px`.

At mobile width:

- header height reduces to ~70px
- hide the first two navigation links to prevent crowding
- hero heading ~58px
- About and Contact become single-column
- About body copy becomes single-column
- project grid becomes one column
- each project image becomes around `60vw` high with `min-height: 330px`
- process cells stack vertically
- Projects heading/link stack vertically
- section vertical padding reduces from ~120px to ~80px

The result must remain usable without JavaScript.

## 8. Build procedure

A reproducing agent/developer can follow this exact procedure:

1. Inspect the two source URLs listed in section 1.
2. Extract only factual LO-YU content; treat WAA as visual-direction research.
3. Create `loyu/index.html` in `dejavu92427/corporate-website-2026`.
4. Use semantic HTML: `header`, `nav`, `main`, `section`, `article`, `footer`.
5. Embed all CSS in a `<style>` block in the same HTML file.
6. Implement sections A–G in the exact narrative order above.
7. Use the recorded Unsplash URLs when reproducing this prototype exactly; replace them only when making a client-ready version.
8. Add the responsive breakpoint and behaviors from section 7.
9. Open the HTML locally and verify desktop + mobile layout, anchors, image loading, and the LO-YU contact link.
10. Commit the HTML and this reproduction log.
11. Deploy the repository root with GitHub Pages so `loyu/index.html` is reachable as `/loyu/`.

No npm install, bundler, package manager, backend, database, or build command is required for this prototype.

## 9. GitHub Pages reproduction

The repository uses a GitHub Actions Pages deployment workflow. The key behavior discovered during the work was that `actions/configure-pages@v5` needs Pages enablement when the repository has not already been configured manually.

The relevant step is:

```yaml
- name: Configure Pages
  uses: actions/configure-pages@v5
  with:
    enablement: true
```

The intended flow is:

`push main → configure/enable Pages → upload static artifact → deploy Pages`

When reproducing deployment, verify the workflow also has the GitHub Pages permissions required by the official Pages actions and uploads the repository's static site content before `actions/deploy-pages` runs.

Do not claim deployment succeeded until the workflow or public page has actually been verified.

## 10. Acceptance checklist

A reproduction is successful when all of these are true:

- [ ] `loyu/index.html` opens without a build step.
- [ ] Hero fills the first viewport and has readable overlay text.
- [ ] Header overlays hero and anchor navigation works.
- [ ] About section contains the 30 / 30 / 300+ credibility row.
- [ ] Projects use the 1-large + 2-small asymmetric composition on desktop.
- [ ] Dark process section contains three stages.
- [ ] Contact CTA links to LO-YU's contact page.
- [ ] Layout collapses cleanly below ~800px.
- [ ] Placeholder photography is clearly understood as non-client project imagery.
- [ ] GitHub Pages can serve the static file at the `/loyu/` path.
- [ ] No unseen source-site content is fabricated if a reference cannot be accessed.

## 11. Artifact of record

For exact implementation details, compare this log against:

- `loyu/index.html`

The HTML is the artifact snapshot; this document records the inputs, reasoning, constraints, dimensions, content mapping, implementation procedure, deployment requirement, and acceptance criteria needed to reconstruct it independently.
