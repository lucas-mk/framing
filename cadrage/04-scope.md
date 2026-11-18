# Scope

## In scope
_To be completed_

## Out of scope
_To be completed_

## Work packages
A work package (WP) is a coherent, independently deliverable slice of value that can become one `/speckit.specify` input: it covers one or a few BN-xx, serves identified profiles (PR-xx), and has a testable outcome. Rule of thumb: if it cannot be estimated in a range of a few weeks or has several unrelated outcomes, split it. Each WP gets an ID (WP-01...), a short description, an acceptance outline and its dependencies.

## Work packages traceability
| Work package | BN-xx | PR-xx | JR-xx | UX-xx | NFR-xx | Priority (MoSCoW) | Dependencies |
|--------------|-------|-------|-------|-------|--------|-------------------|--------------|

## Target journeys (to-be, JR-xx)
_To be completed_

## Key screens and flows (UX-xx)
Accepted inputs per screen (named `UX-xx-<name>`), all optional: pencil/paper sketch in `references/ux/sketches/` (photo or scan), screenshot or export (e.g. Figma) in `references/ux/screenshots/`, or HTML prototype in `references/ux/prototypes/UX-xx-<name>/`. Without any input, the assistant designs the mockup directly in HTML from the to-be journeys and the UI kit (input type "AI-generated", to be validated). In every case it produces a mockup in `cadrage/mockups/`.

| ID | Screen / flow | Journey (JR-xx) | Work package | Input type (sketch / screenshot / HTML prototype / AI-generated) | Input file | Components used (UI kit) | Kit mockup | Mockup status (Draft / Tested / Validated) |
|----|---------------|-----------------|--------------|---------------------------------------------------|------------|--------------------------|------------|--------------------------------------------|

An AI-generated or untested mockup stays "Draft". It becomes "Tested" after step 5 and "Validated" only after the scoping lead's explicit validation.

## Usage hypotheses (HY-xx)
Created here, from the to-be journeys and mockups, whenever a usage assumption is uncertain. Step 5 tests them; step 6 reports the outcome as risks or assumptions.

| ID | Usage hypothesis | How to test | Linked JR / PR / UX | Status (Untested / Confirmed / Rejected / Inconclusive) |
|----|------------------|-------------|---------------------|---------------------------------------------------------|

## Deliverables
_To be completed_

## Definition of done (exit criteria)
- [ ] In scope / out of scope are explicit
- [ ] Every Must/Should BN-xx is covered by at least one work package
- [ ] Every work package has JR-xx, UX-xx (or a reason), NFR-xx and dependencies
- [ ] To-be journeys and key screens exist; each screen has a mockup status
- [ ] Uncertain usages are listed as HY-xx
- [ ] Sponsor and tech lead validation recorded in the decision log
