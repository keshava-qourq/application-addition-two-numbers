# Deployment Guide

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start how-it-deploys -->
Pushes to `main` run `.github/workflows/deploy.yml`, which builds the API image (if there is a backend) and deploys the SPA to AWS Amplify. Commits touching only `docs/sdlc/**` don't deploy. Deployments can also be started from the platform's Deployment tab.
<!-- sdlc:auto:end how-it-deploys -->

<!-- sdlc:auto:start environments -->
| Name | Service | Runtime | Scaling | Environment |
|---|---|---|---|---|
| Frontend Static Hosting | AWS S3 + CloudFront | Static React 19 build | CDN edge, auto | dev |
| Addition Service | AWS container compute (e.g. ECS Fargate) | FastAPI 0.115 on Python 3.12 (uvicorn) | Single small task | dev |
| PostgreSQL | AWS RDS PostgreSQL 16 | PostgreSQL 16 | Single small instance (unused) | dev |
<!-- sdlc:auto:end environments -->

<!-- sdlc:auto:start live -->
_Not deployed yet._
<!-- sdlc:auto:end live -->

<!-- sdlc:auto:start topology -->
```mermaid
graph LR
  n_Frontend_Static_Hosting["Frontend Static Hosting<br/>AWS S3 + CloudFront"]
  n_Addition_Service["Addition Service<br/>AWS container compute (e.g. ECS Fargate)"]
  n_PostgreSQL["PostgreSQL<br/>AWS RDS PostgreSQL 16"]
  n_Frontend_Static_Hosting -->|"HTTPS"| n_Addition_Service
  n_Addition_Service -->|"TCP (provisioned, unused)"| n_PostgreSQL
```
<!-- sdlc:auto:end topology -->
