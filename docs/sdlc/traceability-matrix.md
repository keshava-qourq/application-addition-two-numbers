# Traceability Matrix

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start legend -->
Built from recorded links, not written by a model: requirement key → plan item (`source_stable_key`) → development ticket (`stable_key`) → the ticket's test steps → the last live deployment that started after the work finished. **AC tests** counts the story's acceptance criteria that have a test case, and those whose test cases all passed in the latest finished E2E run.
<!-- sdlc:auto:end legend -->

<!-- sdlc:auto:start matrix -->
| Requirement | Epic | Title | Plan items | Sprint | Design | Code | Commits | Ticket | Tests | AC tests | Deployed |
|---|---|---|---|---|---|---|---|---|---|---|---|
| US-001 | EPIC-001 | Add two numbers and display the result | US-001, US-001-T1, US-001-T2, US-001-T3, US-001-T4 | 1 | GET /health, POST /add, backend, frontend | — | — | not started | not run | 2/2 tested · 0/2 passing | — |
| US-002 | EPIC-001 | Support decimal and negative number entry | US-002 | 1 | POST /add, backend, frontend | — | — | not started | not run | 2/2 tested · 0/2 passing | — |
| US-003 | EPIC-001 | Reject non-numeric input with inline validation | US-003 | 1 | frontend | — | — | not started | not run | 3/3 tested · 0/3 passing | — |
| US-004 | EPIC-001 | Perform calculation without persisting data | US-004 | 1 | POST /add, backend, database | — | — | not started | not run | 2/2 tested · 0/2 passing | — |
| US-005 | EPIC-002 | Access the calculator without logging in | US-005 | 1 | frontend | — | — | not started | not run | 2/2 tested · 0/2 passing | — |
| US-006 | EPIC-002 | View basic usage instructions | US-006 | 1 | frontend | — | — | not started | not run | 1/1 tested · 0/1 passing | — |
<!-- sdlc:auto:end matrix -->
