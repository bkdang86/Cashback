# Card Cashback v5.5 Production Deployment

## Required platform
Deploy through Cloudflare Pages because the app needs both static PWA files and Pages Functions under `functions/api`.

## Required configuration
Create the Pages project `card-cashback-v55` and configure production environment variables:

- `PLACES_RESOLVER_URL`: HTTPS endpoint of the selected place/category provider.
- `PLACES_API_KEY`: provider credential, if required. Save as a secret.

The provider response must expose one of `type`, `category`, or `results[0].type`, plus an optional confidence value. The current MCC mapper supports: cafe, coffee_shop, restaurant, supermarket, grocery_store, electronics_store, lodging, airline, department_store.

## Deploy from GitHub
1. Upload every file in this package to the repository root, including `functions`, `_headers`, `_redirects`, and `wrangler.toml`.
2. In Cloudflare Pages, connect the repository.
3. Use no framework preset.
4. Build command: `exit 0`.
5. Build output directory: `.`.
6. Add the required environment variables under the production environment.
7. Deploy.

## Deploy with Wrangler
After authenticating Wrangler:

```bash
npm install
npm run check
npm run deploy
```

## Production smoke checks
- Open `/` and confirm the title shows Card Cashback v5.5.
- POST to `/api/merchant-resolve` with a merchant and confirm a valid JSON result.
- Add a card with an official policy URL and confirm Draft review appears.
- Confirm a foreign transaction enters Pending FX status.
- Enter final FX within seven days and confirm cashback and net benefit are shown in K VND.
- Export a backup and import it on a clean browser profile.

## Security boundary
Do not store PAN, CVV, PIN, OTP, or online-banking credentials. The app only needs user-defined card product labels and cashback policy data.
