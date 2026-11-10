# API feature specification

Status: phase 1 API MVP.

## Domain features

- Account registration and login using email and password.
- Property listings with owner, status, intent (`BUY`, `SELL`, `RENT`), type, headline, description, MMK price, city, township, optional property attributes, contact details, and ordered photos.
- Initial cities: Yangon, Mandalay, and Bago. Initial property types: apartment/condo, house, land, and commercial.
- Public search for published listings by keyword, intent, city, township, property type, price range, bedroom count, sort order, and pagination.
- Authenticated account listing management. Only the owner can edit, pause, publish, or soft-remove a listing.
- Seeded, fictional demo listings with sample property photos across all three cities.

## HTTP surface

- `GET /health`
- `POST /auth/register`, `POST /auth/login`
- `GET /listings`, `GET /listings/:id`
- `POST /listings`, `PATCH /listings/:id`, `DELETE /listings/:id`
- `GET /account/listings`

See [`openapi.yaml`](../../api/openapi.yaml) for the shared contract.

## Acceptance criteria

- Public search returns only published listings and includes pagination metadata.
- Account credentials are never exposed; passwords are stored as hashes.
- Every listing mutation verifies bearer authentication and ownership.
- Sample seed data is repeatable and covers Yangon, Mandalay, and Bago with multiple intents and photos.
- Prisma migrations can create the SQLite schema from a fresh database.
