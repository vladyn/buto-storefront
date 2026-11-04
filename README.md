# Buto Storefront

Next.js starter storefront for the Medusa backend.

## Prerequisites

- Node.js 22.22+
- Medusa backend running at `http://localhost:9000`

## Environment variables

Copy `.env.template` to `.env.local` and fill in the values:

```bash
cp .env.template .env.local
```

Required variables:

- `NEXT_PUBLIC_MEDUSA_BACKEND_URL` — URL of the Medusa backend API
- `NEXT_PUBLIC_MEDUSA_PUBLISHABLE_KEY` — publishable API key from the Medusa admin

## Development

```bash
npm install
npm run dev
```

The storefront will be available at `http://localhost:8000`.

## Build

```bash
npm run build
npm run start
```
