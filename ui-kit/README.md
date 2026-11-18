# UI Kit

Put here everything Copilot needs to turn hand-drawn sketches into mockups that respect the project's UI kit.

## Included base kit
A generic starter kit is provided (`tokens.css`, `components.css`, `showcase.html` to preview in a browser, catalog and tokens documentation). Replace or adapt it if the client has its own design system.

## How to provide the UI kit
Fill in `ui-kit/kit-reference.md` and add files to this folder:
- Kit name, version and source (Figma library, Storybook URL, npm package, design system website).
- `design-tokens.md`: colors, typography, spacing, radius, breakpoints (or a tokens JSON/CSS file).
- `components-catalog.md`: components available (name, purpose, variants, states, usage rules).
- Optional: exported component screenshots in `ui-kit/assets/`, and the kit code/CSS if it can be used for HTML mockups.

Copilot cannot open Figma or Storybook links: whatever must be used has to be described in Markdown or provided as files.

## Rules
- Mockups must only use components listed in `components-catalog.md`. A needed component that is missing is flagged as a gap in `cadrage/open-points.md`, never invented.
- The kit also feeds `/speckit.constitution` (design system and accessibility constraints).
