# Agent guidance

## Project boundary

This repository is reserved for the future mobile client. It must remain separate from the `app` web client and `api` service. The mobile app consumes the REST/JSON API; it does not own listing persistence or authorization rules.

## Stable technology and architecture

- TypeScript, React Native, and Expo.
- Use the sibling API's `openapi.yaml` as the source of truth for network behavior.
- Keep credentials in platform-appropriate secure storage and send authenticated requests to the API. Do not duplicate account or listing data rules in the client.
- Share the API contract rather than importing web-only components or browser dependencies.
- Mobile implementation is deferred until the web/API contract is stable.

## Context files

Use [`SPEC.md`](SPEC.md) for planned mobile scope and phase status. [`README.md`](README.md) is user-facing setup and release documentation. [`CLAUDE.md`](CLAUDE.md) points Claude-compatible tools back to this file.
