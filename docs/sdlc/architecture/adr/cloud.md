<!-- sdlc:auto:start adr -->
# ADR-0004: Use AWS for Cloud

Status: Accepted  
Date: 2026-10-16

## Context and Problem Statement

Which Cloud technology does the project use? Decided in architecture v1.

## Considered Options

- AWS
- Vercel
- Azure

## Decision Outcome

Chosen option: AWS, because S3/CloudFront host the static frontend and a small container runs the optional FastAPI service, covering a public stateless SPA without exotic dependencies.

## Consequences

Minimal cloud footprint; no serverless/data services needed for this scope.
<!-- sdlc:auto:end adr -->