# IT Project Scoping Template

Template repository that takes an IT project from scoping to code, with an AI assistant and Spec Kit, in one repository. Scoping can be led by a business analyst or a UX designer (or both); implementation follows with Spec Kit.
The conversation can be in any language; all documents are written in English. The assistant's instructions are in `AGENTS.md` (for tools that expect another file, such as `CLAUDE.md`, make it point to `AGENTS.md`).

## Reusing this template
The repository is private and flagged as a template: access must be granted first (Settings > Collaborators and teams, at least Read; or transfer it to an organization).
- **For a specific project**: click **Use this template > Create a new repository**, then follow "Setup" below. The new repository is independent (no history, no link to the template).
- **To build your own template**: create a repository from this one, adapt it (`ui-kit/`, `personas/`, `AGENTS.md`, step documents), then enable Settings > **Template repository**.
- **Getting later template updates**: not automatic. Copy the changed files, or `git remote add template <url>` then `git merge template/main --allow-unrelated-histories`.
- **Fork**: keeps a link to the original but is a poor fit for client projects; prefer "Use this template".
- **Branding**: replace the neutral `ui-kit/` with the client's design system before turning sketches into mockups.

## Repository layout
```
cadrage/          scoping documents (00 to 08, open-points.md)
references/       source documents (briefs, meeting notes, schemas); UX inputs in references/ux/ (sketches/, screenshots/, prototypes/)
ui-kit/           UI kit (base kit included: tokens.css, components.css, showcase.html, catalog) used to turn sketches into mockups
cadrage/mockups/  kit-based mockups generated from sketches (UX-xx)
personas/         challenge personas (sponsor, architect, security, end user, UX/accessibility, project manager, devil's advocate)
AGENTS.md         assistant instructions (method, rules, language)
.github/          PR and issue templates
specs/, .specify/ created later by Spec Kit
```

## Setup (once per project)
1. Click **Use this template** and name the repo `<client>-<project>`. Private, team organization.
2. Give access to the team (Settings > Collaborators and teams).
3. Protect `main` (Settings > Branches): pull request required, at least 1 reviewer.
4. Create a GitHub Project (columns: Scoping, Spec, Plan, Tasks, Implementation, Validated).
5. Create labels `open-point`, `decision`, `risk` and one milestone per step.
6. Clone the repo, open it in your AI assistant, and start a session.

## Roles
- **Scoping lead (BA or UX designer)**: drives the assistant sessions, owns `cadrage/` and functional specs, merges PRs. A UX-led scoping leans on steps 3 to 5; a BA-led one on steps 1, 2 and 4. The other profile contributes and reviews.
- **UX designer / BA (contributor)**: joins workshops, provides profiles, journeys, needs and mockups, reviews PRs for their sections.
- **Tech lead**: validates discovery, scope and estimates; owns plan and architecture.
- **Contributors**: provide input, review PRs, answer open points.
- **Sponsor**: validates business needs, roadmap and the final summary.

## Steps

Each step builds on the information gathered in the previous ones. Ideally, every step is carried out, but depending on the project context some steps can be skipped.

| # | Step | Document | Content | Challenge personas | Validation |
|---|------|----------|---------|--------------------|------------|
| 1 | Business needs | `01-business-needs.md` | Context, objectives and KPIs, needs BN-xx, experience objectives, business constraints | sponsor, devil's advocate | Sponsor |
| 2 | Stakeholders | `02-stakeholders.md` | Stakeholders and RACI, user profiles PR-xx, governance | project manager, end user | Sponsor |
| 3 | Discovery | `03-discovery.md` | Current state, technical and security constraints, integrations and data, non-functional requirements NFR-xx, user research, as-is journeys JR-xx | architect, security, UX | Tech lead |
| 4 | Scope | `04-scope.md` | In/out of scope, work packages WP-xx, to-be journeys, screens/flows UX-xx and mockups, hypotheses HY-xx, traceability table | devil's advocate, architect, end user, UX | Sponsor + tech lead |
| 5 | User testing | `05-user-testing.md` | Test protocol derived from JR-xx, results on UX-xx mockups, findings become open points or decisions | UX, end user, devil's advocate | Sponsor + UX |
| 6 | Risks & assumptions | `06-risks-assumptions.md` | Risks RK-xx (incl. UX), assumptions, rejected or inconclusive HY-xx, dependencies | security, devil's advocate, UX | All |
| 7 | Roadmap & estimation | `07-roadmap-estimation.md` | Estimation ranges per work package, UX activities and tests, high-level plan | project manager, architect | Sponsor |
| 8 | Summary | `08-summary.md` | Synthesis of all steps, experience section, go/no-go criteria | all | Sponsor |

Cross-cutting: `00-decision-log.md`, `open-points.md`.

Each step document ends with a **Definition of done** checklist; a step is closed when it is met or each gap is an accepted open point.

**Loop back**: step 5 findings can reopen step 4. The assistant proposes the change, you validate, a DEC-xx is logged, the affected documents are updated and mockup statuses return to Draft. Mockup statuses: Draft (always for AI-generated), Tested (after step 5), Validated (after your validation).

**Light mode** (small projects): steps 1, 2, 4, 7 and 8 are mandatory, steps 3 and 5 are optional (skipped or reduced to a short note), step 6 is merged into the summary. Log the choice as a DEC-xx and note the resulting risk.

## Cycle for each step
1. **Prepare**: `git pull`, create branch `scoping/step-N`, drop sources in `references/`.
2. **Clarify**: "Let's start step N: <name>. Ask me your questions." Answer, or paste meeting notes/emails.
3. **Draft**: the assistant updates the document, the decision log and the open points.
4. **Challenge**: "Challenge the document as architect and security." Keep, reject, or turn remarks into open points.
5. **Validate**: open a PR; the team reviews the diff; merge after approval.
6. **Close**: turn open points into issues (template "Open point") with an owner and a due date.

## Rituals
- **Business workshop** before steps 1, 2 and 4: collect notes, then let the assistant structure them.
- **Weekly review**: open points and GitHub Project.
- **End-of-scoping review**: go/no-go, tag `scoping-v1.0`.

## UX inputs to kit-based mockups (step 4)
An input is optional. Without any sketch, screenshot or prototype, ask the assistant to design the mockups directly in HTML from the journeys and the UI kit (see below).

1. Drop your input, named `UX-xx-<name>`, in one of:
   - `references/ux/sketches/` : pencil/paper sketch (photo or scan, `.png`)
   - `references/ux/screenshots/` : screenshot or export, e.g. from Figma (`.png`; add the Figma link in a `UX-xx-<name>.md` note)
   - `references/ux/prototypes/UX-xx-<name>/` : HTML prototype (`index.html` + assets)
2. Make sure `ui-kit/` is filled in (kit reference, tokens, components catalog).
3. Ask the assistant: "Turn the UX inputs into mockups using the UI kit." It transcribes each input (image or HTML source), asks about unclear parts, maps elements to kit components and writes `cadrage/mockups/UX-xx-<name>.html` and `.md`.
4. Review in the PR, adjust, then validate. Missing components become open points.

**No input available**: ask the assistant "Propose HTML mockups from the journeys." It proposes the screens (UX-xx) from the to-be journeys, asks you to confirm the list, then generates `cadrage/mockups/UX-xx-<name>.html` and `.md` with the UI kit only. These mockups are AI proposals, flagged as such in the `.md`, and must be validated (ideally in user testing).

## User testing (step 5)
Run on the project mockups when possible (otherwise on a comparable product or the as-is process, stated in the document).
1. Ask the assistant: "Let's start step 5: user testing." It lists the doubts to clear (open points, HY-xx, assumptions) and writes the protocol in `cadrage/05-user-testing.md`: participants (PR-xx), tasks taken from the journeys (JR-xx), success criteria, script.
2. Run the sessions, then paste the notes or observation grid.
3. The assistant fills the results and turns each problem into an open point or a decision (decision log), updates the HY-xx status and the impacted documents. Nothing is changed in earlier steps without your validation.

## Handover to Spec Kit
1. Run `specify init .` (with your AI agent) once scoping is validated.
2. `/speckit.constitution` from the NFR-xx (accessibility level, security, data) and the design system.
3. Per work package (WP-xx; the scoping lead decides the split): give the assistant a short brief (goal, BN/PR/JR/UX/NFR references, in/out of scope, acceptance outline, dependencies, relevant DEC/OP), then `/speckit.specify` (what and why; PR-xx are the actors, JR/UX feed scenarios and a "UX references" section), `/speckit.clarify` (open points and untested or inconclusive HY-xx), PR review.
4. `/speckit.plan`, `/speckit.tasks`, `/speckit.analyze` (tech lead; the scoping lead checks every need is covered), then implementation.
5. When a need changes: update `cadrage/` and the spec first (PR), then regenerate plan and tasks.

## Rules
- Personas propose, the scoping lead decides. Anything unsourced goes to `open-points.md`.
- Every decision is logged with date and decision maker.
- One person drives the assistant on a given step at a time.
- No sensitive data in the repo unless company policy allows it.
- Optional: set up a shared knowledge base on this repo so the team can query the scoping.
