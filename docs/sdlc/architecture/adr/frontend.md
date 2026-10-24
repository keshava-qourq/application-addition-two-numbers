<!-- sdlc:auto:start adr -->
# ADR-0001: Use React 19 for Frontend

Status: Accepted  
Date: 2026-10-16

## Context and Problem Statement

Which Frontend technology does the project use? Decided in architecture v1.

## Considered Options

- React 19
- Next.js
- Vue

## Decision Outcome

Chosen option: React 19, because A single page with two inputs and a sum display needs only client-side UI. React 19 renders the inputs, runs validation, and computes the sum in-browser for instant results.

## Consequences

No routing or SSR layer, which this app never needs; served as a static build via CloudFront.
<!-- sdlc:auto:end adr -->