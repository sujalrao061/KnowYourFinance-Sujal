# KnowYourFinance

COMP 425 team project. This repository is Sujal Rao's working copy of the shared KnowYourFinance project. The existing project history is preserved.

## What the app does

KnowYourFinance helps users review income, expenses, and savings without linking a bank account. Users can import a CSV statement, enter a transaction manually, correct records, and view reports. Sensitive number patterns in transaction descriptions are redacted before later processing.

## Project folders

- `backend/`: Spring Boot API using Java 21.
- `frontend/`: React interface built with Vite.
- `docs/`: requirements, design diagrams, and development notes.
- `.github/workflows/`: automated build workflows.

## Backend tests

With Java 21 and Maven installed, run:

```sh
cd backend
mvn -B verify
```

The existing backend suite was run on November 4, 2026 at revision `f89fd4722035a571622e002588c64f0726168144`: **52 tests passed, 0 failures, 0 errors, 0 skipped**. The build also completed successfully. These results cover the existing automated tests; browser workflows, Docker startup, and the hosted database still need separate checks.

## Running the app

The backend uses Supabase PostgreSQL. Set `SPRING_DATASOURCE_URL`, `SPRING_DATASOURCE_USERNAME`, and `SPRING_DATASOURCE_PASSWORD` in your local environment using the team's approved development database settings. Keep passwords and API keys out of Git.

Start the backend:

```sh
cd backend
mvn spring-boot:run
```

Start the frontend in a second terminal:

```sh
cd frontend
npm ci
npm run dev
```

The default development addresses are `http://localhost:8080` for the API and `http://localhost:5173` for the frontend.

## Current milestone

Milestone 4 covers the Core MVP and Docker setup, due November 13, 2026. Remaining verification includes the exact CSV scenarios through the running app, container connectivity, persistence after restart, and report checks. Task assignments in workday documents are plans until backed by completed work and evidence.

## Project notes

The current MVP focuses on CSV imports, manual transactions, transaction corrections, categorization, and reports. Authentication, budgets, recurring-charge detection, bank linking, report export, and multiple currencies remain outside the approved MVP scope. Hosted categorization provider adapters are described in the design and should not be assumed complete from that description alone.

See `docs/requirements/`, `docs/design/`, `docs/diagrams/`, and `docs/build-log/` for the shared project documentation.
