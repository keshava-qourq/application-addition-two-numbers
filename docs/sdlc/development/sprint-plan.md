# Sprint Plan

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start sprints -->
## Sprint 1: Sprint 1

Ship a fully working, publicly accessible addition calculator with validation and no data persistence.

Capacity: 20 points · Committed: 20

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-001 | Story | Add two numbers and display the result | 8 | frontend-agent | — |
| ↳ US-001-T1 | Task | Implement POST /add endpoint | — | backend-agent | — |
| ↳ US-001-T2 | Task | Implement GET /health endpoint | — | backend-agent | — |
| ↳ US-001-T3 | Task | Build Calculator SPA input and result UI | — | frontend-agent | — |
| ↳ US-001-T4 | Task | Wire frontend to the /add endpoint | — | integration-agent | — |
| US-002 | Story | Support decimal and negative number entry | 3 | frontend-agent | US-001 |
| US-003 | Story | Reject non-numeric input with inline validation | 5 | frontend-agent | US-001 |
| US-004 | Story | Perform calculation without persisting data | 2 | backend-agent | US-001 |
| US-005 | Story | Access the calculator without logging in | 1 | frontend-agent | — |
| US-006 | Story | View basic usage instructions | 1 | frontend-agent | — |

## Unscheduled

_Nothing unscheduled._
<!-- sdlc:auto:end sprints -->
