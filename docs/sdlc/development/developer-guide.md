# Developer Guide

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start status -->
_Up to date._
<!-- sdlc:auto:end status -->

<!-- sdlc:auto:start source -->
Generated from commit `9814452` · model `claude-sonnet-5`
<!-- sdlc:auto:end source -->

<!-- sdlc:auto:start overview -->
This repository is a Quorq AI SDLC generated scaffold for a two-number addition app. It contains two separate applications: a Vite + React 19 single-page frontend whose screens were approved and currently run on seeded sample data, and a FastAPI 0.115 backend that currently only exposes a health-check endpoint, since no backend architecture had been approved yet. The backend uses SQLAlchemy with a SQLite database by default (switchable to Postgres via DATABASE_URL), and docker-compose provides a local Postgres 16 container for later use.
<!-- sdlc:auto:end overview -->

<!-- sdlc:auto:start prerequisites -->
- Node.js (for npm, Vite 6, TypeScript 5.6, React 19 tooling)
- Python 3.12
- pip
- Docker and Docker Compose (optional, for the Postgres container)
<!-- sdlc:auto:end prerequisites -->

<!-- sdlc:auto:start setup -->
1. Clone the repository
2. cd backend && pip install -r requirements.txt
3. uvicorn app.main:app --reload   # starts the FastAPI backend on http://localhost:8000
4. cd ../frontend && npm install
5. npm run dev   # starts the Vite dev server (default http://localhost:5173)
6. (optional) docker compose up -d   # starts a local Postgres 16 instance on port 5432 if you want to point DATABASE_URL at it
<!-- sdlc:auto:end setup -->

<!-- sdlc:auto:start run -->
| Name | Command | Description |
|---|---|---|
| backend dev | `uvicorn app.main:app --reload` | Runs the FastAPI backend locally with auto-reload (from backend/) |
| frontend dev | `npm run dev` | Runs the Vite dev server for the React SPA (from frontend/) |
| frontend build | `npm run build` | Bundles the frontend with Vite (does not typecheck) |
| frontend preview | `npm run preview` | Serves the built frontend bundle locally |
| db up | `docker compose up -d` | Starts the local Postgres 16 container defined in docker-compose.yml |
<!-- sdlc:auto:end run -->

<!-- sdlc:auto:start structure -->
| Path | Purpose |
|---|---|
| `backend` | FastAPI service: app entrypoint, SQLAlchemy models/database, Pydantic schemas, routers, and tests |
| `backend/app` | Application source: main.py (entrypoint & CORS), database.py (engine/session), models.py, schemas.py, routers/ |
| `backend/tests` | Pytest tests, e.g. test_health.py |
| `frontend` | Vite + React 19 SPA: approved screens, source, config, and Playwright e2e tests |
| `frontend/src` | App source: main.tsx entrypoint, lib/ (api client, UI/icon vocabulary, navigation), index.css |
| `frontend/e2e` | Playwright acceptance test specs |
| `.quorq` | Platform metadata (handoff.json) used by the Quorq AI SDLC platform |
<!-- sdlc:auto:end structure -->

<!-- sdlc:auto:start conventions -->
- Backend follows one router per architecture component, one route per API-spec endpoint; unimplemented routes return a typed StubResponse rather than raising, so the service stays startable
- SQLAlchemy models all inherit from the shared Base in app/database.py; main.py imports models before calling Base.metadata.create_all
- Backend config (DATABASE_URL, ALLOWED_ORIGINS) is read from environment variables with sane local defaults (SQLite, localhost CORS origins)
- Frontend screens are written to run on seeded sample data first; frontend/src/lib/api.ts is the designated seam for wiring real API calls via apiFetch, using VITE_API_BASE_URL and VITE_API_SECRET_KEY env vars
- Frontend component tests live beside the components they cover and are picked up by Vitest's src/**/*.{test,spec}.{ts,tsx} pattern; Playwright specs live separately in e2e/
<!-- sdlc:auto:end conventions -->

<!-- sdlc:auto:start testing -->
| Name | Command | Description |
|---|---|---|
| backend test | `pytest` | Runs backend tests from backend/ (pytest.ini sets pythonpath=. and testpaths=tests) |
| backend lint | `ruff check .` | Lints the backend Python code per backend/ruff.toml |
| backend format | `ruff format .` | Formats backend Python code |
| frontend test | `npm test` | Runs Vitest component tests |
| frontend lint | `npm run lint` | Runs ESLint over the frontend app |
| frontend typecheck | `npm run typecheck` | Runs tsc --noEmit |
| frontend format | `npm run format` | Formats frontend code with Prettier |
| e2e install | `npm run test:e2e:install` | Installs the Chromium browser needed by Playwright |
| e2e test | `npm run test:e2e` | Runs Playwright acceptance tests from e2e/; without E2E_BASE_URL it builds/serves the frontend and boots the backend locally |
<!-- sdlc:auto:end testing -->

<!-- sdlc:auto:start troubleshooting -->
| Problem | Solution |
|---|---|
| Frontend requests to the backend are blocked by CORS | Ensure the backend's ALLOWED_ORIGINS env var includes the frontend's origin, or run both on the default dev ports (5173 frontend, 8000 backend) which are allowed by default in app/main.py |
| `pytest` fails with ImportError for `app` | Run pytest from the backend/ directory so pytest.ini's pythonpath=. setting applies |
| Playwright e2e tests fail to start | Run `npm run test:e2e:install` first to fetch the Chromium browser; without E2E_BASE_URL set, Playwright will install backend deps and boot both backend (port 8000) and built frontend (port 4173) itself |
| `npm run build` succeeds but the app is actually broken | Run `npm run typecheck` (tsc --noEmit) since build does not typecheck and generated screens may not satisfy tsc |
| Backend has no persistent/shared database | Backend defaults to a local SQLite file (app.db) via DATABASE_URL; set DATABASE_URL to point at the Postgres container started by `docker compose up -d` if shared data is needed |
<!-- sdlc:auto:end troubleshooting -->
