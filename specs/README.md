# Property Portal

Three separate projects live in this workspace:

- [`app/`](../app/) — React + TypeScript + Vite web app, shadcn preset `b7ClNFsdu`.
- [`api/`](../api/) — Express + TypeScript API with Prisma and SQLite.
- [`mobile/`](../mobile/) — Expo repository reserved for phase 2.

Each project has one standard set of docs in its folder below: `AGENTS.md` for stable architecture and constraints, `CLAUDE.md` pointing to it, `SPEC.md` for feature scope, and `README.md` for user-facing setup and usage.

- [Web app docs](app/README.md)
- [API docs](api/README.md)
- [Mobile docs](mobile/README.md)

Start the web app and API in separate terminals by following their setup instructions. The web app expects the API at `http://localhost:4000` by default.
