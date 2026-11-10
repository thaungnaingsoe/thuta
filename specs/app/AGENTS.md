# Agent guidance

## Project boundary

This repository contains only the public web client and browser-side account/listing flows. The Express service lives in the sibling `api` repository; call it through its REST/JSON contract. The Expo client belongs in the sibling `mobile` repository. Do not add API persistence, secrets, or mobile-specific runtime code here.

## Stable technology and architecture

- TypeScript, React, and Vite.
- shadcn/ui initialized with preset `b7ClNFsdu` (Luma style, Mist base, Emerald theme, Inter, Phosphor icons).
- Keep the web app as a browser client. Read API shapes from the sibling `api/openapi.yaml` and avoid drifting request/response types.
- Keep presentation, browser interactions, and remote data access in the web client; authorization and validation are enforced by the API.
- Use accessible semantic HTML, keyboard-operable controls, and responsive layouts.
- Theme preference belongs to the browser client and must respect and persist the user's selection.

## Context files

Use [`SPEC.md`](SPEC.md) for web features and acceptance criteria. [`README.md`](README.md) is user-facing setup and usage documentation. [`CLAUDE.md`](CLAUDE.md) points Claude-compatible tools back to this file.
