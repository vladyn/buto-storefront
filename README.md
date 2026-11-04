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

## Deploy on Render

Use the `render-deploy` branch for Render deployments.

### One-click deploy

1. Push this branch to `git@github.com:vladyn/buto-storefront.git`.
2. In the Render dashboard, create a new **Blueprint** and select the `buto-storefront` repository.
3. Render will read `render.yaml` and create the web service.
4. When prompted, set the secret environment variables:
   - `NEXT_PUBLIC_MEDUSA_BACKEND_URL` — URL of the production Medusa backend
   - `NEXT_PUBLIC_MEDUSA_PUBLISHABLE_KEY` — publishable API key from the Medusa admin
   - `NEXT_PUBLIC_BASE_URL` — public URL of the storefront on Render

### Manual deploy

If you prefer not to use the Blueprint:

1. Create a new **Web Service** in Render.
2. Connect `git@github.com:vladyn/buto-storefront.git` and select the `render-deploy` branch.
3. Set:
   - **Runtime:** Node
   - **Build Command:** `npm install --legacy-peer-deps && npm run build`
   - **Start Command:** `npm run start`
4. Add the environment variables listed above.

The `render.yaml` file in this branch already sets `PORT=8000` so the service listens on the correct port.
