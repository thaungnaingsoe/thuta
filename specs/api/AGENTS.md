# Agent guidance

## Project boundary

This repository owns the REST API, authentication, validation, data access, database migrations, and seed data. The React browser client and future Expo client are separate sibling repositories and consume this service. Do not put UI or client-specific flows here.

## Stable technology and architecture

- TypeScript on Node.js with Express.
- Prisma ORM with SQLite for the initial database.
- REST/JSON contract documented in `openapi.yaml`; keep web and mobile clients aligned to it.
- Validate external input at the API boundary. Use Prisma's parameterized data operations; do not construct SQL from request strings.
- Hash passwords with bcrypt. Sign authenticated requests with configured JWT secret. Enforce listing ownership on every mutation in the API.
- Public endpoints expose published listings only. Preserve soft removal and the draft/published/paused/removed listing lifecycle.
- Schema changes must be expressed through Prisma schema and committed migrations. Seed content must remain repeatable and clearly fictional.
- Uploaded media storage is not part of the current architecture; listings currently reference external photo URLs. Keep production storage as a separate future decision.

## Context files

Use [`SPEC.md`](SPEC.md) for current API behavior and feature requirements. [`README.md`](README.md) is user-facing setup/API documentation. [`CLAUDE.md`](CLAUDE.md) points Claude-compatible tools back to this file.
