# Design system — EosBot profile

## 0. Research log

- **Source of truth:** `EosBot/astroaxe@develop`, especially `docs/design-references.md`, `src/components/site/astroaxe-logo.tsx`, `README.md`, and `docs/IMPLEMENTATION_STATUS.md`.
- **Existing profile audit:** the previous README relied on generic badges, dense marketing tables, unsupported business claims, and no owned visual assets.
- **Rendered QA:** the first revision exposed 300px SVG intrinsic sizing on desktop and a horizontally clipped monospace block on mobile. Both were removed in the second revision.
- **Renderer constraints:** GitHub profile Markdown sanitizes CSS and JavaScript. The design uses static SVG plates, semantic Markdown, and native links instead of simulated interactions.

## 1. Direction

The profile should feel like a **celestial field instrument**, not a generic AI portfolio: tinted darkness, aged copper, smoked glass, ephemeris marks, and precise coordinate labels. The signature is an asymmetric natal instrument whose geometry connects the engineering portfolio to AstroAxé without presenting the product as released.

## 2. Audience and jobs

- **Technical peer:** understand the engineering range and reach source repositories quickly.
- **Hiring or project lead:** identify concrete, inspectable work without unsupported résumé claims.
- **Potential collaborator:** see which projects are public, which product is private, and the exact development state.

## 3. Tokens

| Role | Token | Value |
| :--- | :--- | :--- |
| Background | `pitch` | `#070A10` |
| Depth | `atlantic-blue` | `#123047` |
| Primary text | `mist` | `#D8D3C7` |
| Primary focus | `instrument-copper` | `#C47A4A` |
| Technical data | `technical-aqua` | `#68A8A4` |
| Display | `display` | Anybody Variable; Arial Narrow fallback in SVG |
| Narrative | `reading` | Literata; Georgia fallback in SVG |
| Data | `mono` | IBM Plex Mono; ui-monospace fallback in SVG |

The color mapping is derived from AstroAxé's own `docs/design-references.md`; English token names are used here because the profile's language is English.

## 4. Layout and material

- Full-width 1200-unit visual plates with explicit intrinsic dimensions, safe at narrow GitHub widths.
- Asymmetric copy/instrument split; avoid centered badge walls and equal three-card grids.
- Depth comes from multi-stop navy gradients, radial optical light, copper focus, low-opacity grids, and restrained grain.
- Every visual plate has an SVG `<title>` and `<desc>`; essential facts are repeated as real Markdown.

## 5. Primitives

- **Hero instrument:** identity, discipline, technical field, and location.
- **Status plate:** AstroAxé identity plus an explicit development/release boundary.
- **Field note:** short prose section with one factual job.
- **Project coordinate:** numbered public project entry with repository link, problem, and verified scope.
- **Contact rail:** plain native links; no fake buttons or unavailable product CTA.

## 6. Responsive behavior

SVG viewboxes scale proportionally from 1200px intrinsic width. Copy uses GitHub's native responsive flow. Capability labels are short wrapped lines rather than a fixed-width code block. Project entries use headings and paragraphs rather than card grids.

## 7. Accessibility

- Text contrast targets WCAG AA against `pitch` and `atlantic-blue`.
- Meaning is not encoded by color alone; AstroAxé status is explicit in text.
- No animation, flashing, or motion dependency.
- No meaningful information exists only inside an image.

## 8. Accepted debt

- GitHub controls typography outside SVG and may substitute fonts inside SVG when local families are unavailable.
- The profile cannot provide true interaction or motion without leaving GitHub; immersion is achieved through composition and material depth.
- Browser QA uses direct static captures because the environment's Playwright Chrome installation requires unavailable sudo authentication.
