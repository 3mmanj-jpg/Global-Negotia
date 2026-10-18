# Global Negotia — Cloudflare Workers + Static Assets

This package is arranged for Cloudflare Workers Builds (GitHub-connected) and includes the complete responsive website plus a Worker handler for `/api/inquiry`.

## GitHub upload
1. Extract this ZIP on your computer.
2. Upload the **contents of the extracted `global-negotia-cloudflare` folder** to the root of your GitHub repository, preserving folders exactly: `public/` and `src/` must remain folders, and `wrangler.jsonc` must be at repository root.
3. Commit the changes to the `main` branch.

Expected structure:
- `wrangler.jsonc`
- `src/worker.js`
- `public/index.html`
- `public/build-sell.html`
- `public/fulfillment.html`
- `public/about.html`
- `public/contact.html`
- `public/assets/` (CSS, JavaScript, logo and favicon)

## Cloudflare Workers Builds settings
- Build command: leave as `None` / blank if the UI permits.
- Deploy command: `npx wrangler deploy`
- Preview command: `npx wrangler dev`
- Root directory: `.` (repository root)
- Version command: leave blank / `None` if optional.

The deployment is a Worker with Static Assets, not a Pages project. `wrangler.jsonc` tells Wrangler to publish the `public/` directory and route `/api/*` requests through `src/worker.js`.

## Inquiry email setup
The inquiry form returns a clear setup message until these Worker secrets/variables are configured in Cloudflare:
- `RESEND_API_KEY` (secret)
- `CONTACT_EMAIL` (for example, `vjglobalbusiness@gmail.com`)
- `FROM_EMAIL` (a sender address verified in Resend on a domain you control)

Add them in the Worker settings under Variables and Secrets, then redeploy. Never commit API keys to GitHub. Phone/WhatsApp contact remains available on the site even before email delivery is configured.

## Website details
- Public email: `vjglobalbusiness@gmail.com`
- Phone / WhatsApp: `+1 786 204 1326`
- Domain intended for connection: `www.globalnegotia.com`
- Website creation offer: `$285 + $70`; confirm any recurring domain or maintenance fees directly before payment.
- Class dates/pricing and operational details remain unconfirmed; the site avoids inventing those details.
