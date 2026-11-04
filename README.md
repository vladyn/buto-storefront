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

## Deploy on Vercel

Use the `vercel-deploy` branch for Vercel deployments.

### Required environment variables

In the Vercel dashboard, add these environment variables for the project:

- `NEXT_PUBLIC_MEDUSA_BACKEND_URL` — URL of the production Medusa backend (e.g. `https://your-backend.example.com`)
- `NEXT_PUBLIC_MEDUSA_PUBLISHABLE_KEY` — publishable API key from the Medusa admin
- `NEXT_PUBLIC_DEFAULT_REGION` — default region code (e.g. `dk`)
- `NEXT_PUBLIC_BASE_URL` — public URL of the storefront (e.g. `https://your-storefront.vercel.app`)

### Vercel project settings

- **Framework Preset:** Next.js
- **Build Command:** `npm run build`
- **Install Command:** `npm install --legacy-peer-deps`
- **Output Directory:** `.next`

The `vercel.json` file in this branch already sets these values.
