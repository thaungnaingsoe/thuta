# Property Portal Web App

Responsive React web app for discovering and managing property listings in Myanmar. It uses the shadcn preset `b7ClNFsdu` and supports light and dark themes.

## Run locally

Run these commands from the workspace root:

```sh
cd app
npm install
cp .env.example .env.local
npm run dev
```

Set `VITE_API_URL` in `.env.local` if the API is not at `http://localhost:4000`. When the API is unavailable, public browsing falls back to built-in demo listings. Sign-in, publishing, and account management require the API.

## Build

```sh
npm run build
```

See [SPEC.md](SPEC.md) for the web feature scope. The shadcn config is in [`../app/components.json`](../../app/components.json).
