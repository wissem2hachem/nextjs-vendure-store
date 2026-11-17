# Next.js Vendure Storefront

A web storefront built with Next.js, React, and the Vendure Shop API. It includes product discovery, a shopping cart, checkout, customer accounts, and English and German translations.

## What you need

- Node.js and npm
- A running Vendure server with its Shop API available to this application

## Run locally

1. Copy the example environment file:

   ```bash
   cp .env.example .env.local
   ```

2. Set `VENDURE_SHOP_API_URL` in `.env.local` to the URL of your Vendure Shop API. The example uses `http://localhost:3000/shop-api`.
3. Install packages and start the development server:

   ```bash
   npm install
   npm run dev
   ```

4. Open [http://localhost:3001](http://localhost:3001).

Keep `.env.local` private; it is intended for local configuration and should not be committed.

## Configuration

| Variable | Purpose |
| --- | --- |
| `VENDURE_SHOP_API_URL` | Vendure Shop API URL. Set this for server-side requests. |
| `NEXT_PUBLIC_VENDURE_SHOP_API_URL` | Optional public API URL for integrations that need browser-side access. |
| `VENDURE_CHANNEL_TOKEN` | Optional Vendure channel token; defaults to `__default_channel__`. |
| `NEXT_PUBLIC_VENDURE_CHANNEL_TOKEN` | Optional public channel token for browser-side access. |
| `NEXT_PUBLIC_SITE_URL` | Public URL used for site metadata; defaults to `https://example.com`. |
| `NEXT_PUBLIC_SITE_NAME` | Site name used in metadata; defaults to `Vendure Store`. |
| `REVALIDATION_SECRET` | Secret required when using the `/api/revalidate` endpoint. |
| `VENDURE_AUTH_TOKEN_COOKIE` | Optional authentication cookie name; defaults to `vendure-auth-token`. |
| `VENDURE_AUTH_TOKEN_HEADER` | Optional authentication header name; defaults to `vendure-auth-token`. |
| `VENDURE_CHANNEL_TOKEN_HEADER` | Optional channel header name; defaults to `vendure-token`. |

Use the server-only variables wherever possible. Values prefixed with `NEXT_PUBLIC_` are exposed to the browser and should not contain secrets.

## Store capabilities

- Browse collections and products, including product variants
- Search the catalog, filter results, and paginate through products
- Add products to a cart, apply promotion codes, and proceed through checkout
- Create and manage a customer account, addresses, and orders
- Use English or German storefront translations and localized currency formatting

Some capabilities depend on how your Vendure server, channels, shipping, and payment methods are configured.

## Project layout

- `src/app` — Next.js routes and page entry points
- `src/features` — storefront functionality grouped by feature
- `src/platform` — Vendure and framework integrations
- `src/site` — storefront composition, content, and translations
- `src/config` — application configuration
- `src/components/ui` — shared interface components

## Useful commands

| Command | Description |
| --- | --- |
| `npm run dev` | Start the local development server on port 3001. |
| `npm run build` | Create a production build. |
| `npm start` | Run the production server. |
| `npm run lint` | Run ESLint. |
| `npm run check-types` | Generate Next.js types and run TypeScript checks. |
| `npm test` | Run the project's Node.js tests. |

## Further reading

- [Architecture notes](./docs/architecture.md)
- [Upgrade guide](./docs/upgrades.md)
- [Contribution guide](./CONTRIBUTING.md)
