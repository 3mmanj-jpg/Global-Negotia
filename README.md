# Global Negotia — Cloudflare Worker, flat upload package

This package is intentionally FLAT so you can select and upload all files together in GitHub without needing to preserve folders.

## Upload to GitHub
1. Extract this ZIP.
2. Open the extracted folder and select all files inside it. Upload them together to the ROOT of the Global-Negotia repository.
3. Commit changes. Do not upload the ZIP itself.

## Cloudflare Workers Builds
Build command: `echo "Preparing Global Negotia"`
Deploy command: `npx wrangler deploy`
Preview command: `npx wrangler dev`
Root directory: `.`

`wrangler.jsonc` serves static files from the repository root and routes `/api/*` through `worker.js`. The `.assetsignore` excludes worker/config files from public static assets.

## Inquiry email
For email delivery, set `RESEND_API_KEY` (secret), `CONTACT_EMAIL`, and `FROM_EMAIL` in Worker Variables and Secrets. Use a verified sender in Resend.

Public contact: vjglobalbusiness@gmail.com | +1 786 204 1326
Domain intended: www.globalnegotia.com
