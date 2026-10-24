<!-- sdlc:auto:start adr -->
# ADR-0002: Use FastAPI 0.115 for Backend

Status: Accepted  
Date: 2026-10-16

## Context and Problem Statement

Which Backend technology does the project use? Decided in architecture v1.

## Considered Options

- FastAPI 0.115
- Flask
- Express

## Decision Outcome

Chosen option: FastAPI 0.115, because Included as a thin, optional stateless service exposing /add and /health to match the platform's standard deployment shape and give a predictable place for future server-side logic.

## Consequences

Not on the critical path since addition runs client-side; adds a small container to operate.
<!-- sdlc:auto:end adr -->