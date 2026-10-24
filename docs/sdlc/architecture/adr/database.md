<!-- sdlc:auto:start adr -->
# ADR-0003: Use PostgreSQL 16 for Database

Status: Accepted  
Date: 2026-10-16

## Context and Problem Statement

Which Database technology does the project use? Decided in architecture v1.

## Considered Options

- PostgreSQL 16
- SQLite
- None

## Decision Outcome

Chosen option: PostgreSQL 16, because Required by the project template. The app is stateless by design and defines no schema, so nothing is written to it.

## Consequences

Provisioned but unused, which is intentional for this stateless tool.
<!-- sdlc:auto:end adr -->