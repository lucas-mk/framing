# User Testing

Purpose: remove doubts about the scoped journeys and mockups (UX-xx) before risks, estimation and specification. Run on the project's own mockups when possible; otherwise on comparable products or the as-is process (state it below).

## Test context
| Item | Value |
|------|-------|
| Tested object | _Mockups UX-xx / HTML prototype / as-is product (to be confirmed)_ |
| Feasible on the project? | _Yes / No, with reason. If No, fallback used_ |
| Test type | _Moderated / unmoderated, remote / on site_ |
| Planned dates | _To be completed_ |

## Doubts to clear
Each doubt comes from an open point, an HY-xx hypothesis or a scope assumption.

| ID | Doubt / question | Origin (OP / HY-xx / BN-xx) | Journey (JR-xx) | Screens (UX-xx) |
|----|------------------|------------------------------|-----------------|-----------------|

## Test protocol
### Participants
Guideline: about 5 participants per profile (PR-xx) is enough to expose most major usability problems; fewer is acceptable for a first round if stated. Real users of the target profile are preferred over colleagues. If real users cannot be reached, say so, state the substitute, and treat the results as weaker evidence. Get informed consent, collect no more personal data than needed, and anonymize participants (P1, P2...) in this document.
| Profile (PR-xx) | Number | Recruitment criteria | Participant IDs |
|-----------------|--------|----------------------|-----------------|

### Tasks
Tasks are derived from the target journeys (JR-xx), not invented. Written as realistic scenarios without hints about the interface.

| Task | Scenario given to the participant | Journey (JR-xx) | Screens (UX-xx) | Doubt cleared | Success criteria | Metrics (success, time, errors, satisfaction) |
|------|-----------------------------------|-----------------|-----------------|---------------|------------------|-----------------------------------------------|

### Script and materials
_Introduction, consent, task order, debrief questions, observation grid, recording policy (To be completed)_

## Results
| Participant | Task | Result (success / partial / failure) | Observation | Severity (blocker / major / minor) | Doubt (ID) |
|-------------|------|---------------------------------------|-------------|-------------------------------------|------------|

## Findings and follow-up
Each problem becomes an open point (to resolve) or a decision (already resolved), logged in `open-points.md` or `00-decision-log.md`.

| Finding | Severity | Doubt cleared? | Outcome | Reference (OP-xx / decision) | Impacted (BN / JR / UX / HY) |
|---------|----------|----------------|---------|-------------------------------|------------------------------|

## Hypotheses status
Update the status of each HY-xx tested (confirmed / rejected / inconclusive) in `04-scope.md` and feed `06-risks-assumptions.md`.

## Loop back rule
After the findings are logged, decide for each blocker or major finding:
- **Reopen step 4** (scope, journeys or mockups change): record a DEC-xx, update the affected documents, set the mockup status back to Draft, and retest if the change is significant.
- **Accept and mitigate**: record a DEC-xx and a risk RK-xx in step 6.
- **Defer**: keep an OP-xx with owner and date.
Minor findings go to open points or the backlog for Spec Kit.

## Definition of done (exit criteria)
- [ ] Every doubt has an outcome (cleared, still open, or not testable) with a reference
- [ ] Every blocker/major finding has a DEC-xx or OP-xx and a loop back decision
- [ ] HY-xx statuses are updated
- [ ] Mockup statuses in `04-scope.md` are updated
- [ ] If no test could be run, the reason and the risk are recorded (RK-xx)
- [ ] Sponsor and UX validation recorded in the decision log
