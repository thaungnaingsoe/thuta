# Property Portal API

Express + TypeScript REST API backed by Prisma and SQLite. The OpenAPI contract is in [openapi.yaml](../../api/openapi.yaml).

## Run locally

```sh
cd api
npm install
cp .env.example .env
npm run db:generate
npm run db:migrate
npm run db:seed
npm run dev
```

The service listens on port 4000 by default. Set a strong random `JWT_SECRET` before using the API outside local development.

## Routes

- `GET /health`
- `POST /auth/register`, `POST /auth/login`
- `GET /listings` — public filters: `q`, `intent`, `city`, `township`, `type`, `minPrice`, `maxPrice`, `bedrooms`, `sort`, `page`, `limit`
- `GET /listings/:id` — published listings
- `POST /listings`, `PATCH /listings/:id`, `DELETE /listings/:id` — authenticated owner operations
- `GET /account/listings` — authenticated account listings

The demo account and phone numbers are fictional. Photo URLs are external; image uploading and production object storage are not implemented. See [SPEC.md](SPEC.md) for the feature scope.
