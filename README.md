# Global Negotia — Website

Responsive multi-page static website for Cloudflare Pages.

## Public contact details
- Website: https://www.globalnegotia.com
- Email: vjglobalbusiness@gmail.com
- Phone / WhatsApp: +1 786 204 1326
- Website creation offer displayed on the homepage: $285 + $70, with exact scope and any recurring charges to be confirmed directly.

## Pages
- `/` — Home
- `/build-sell.html` — Build & Sell and seven-session class outline
- `/fulfillment.html` — Fulfillment services
- `/about.html` — About
- `/contact.html` — Separate training and fulfillment inquiry forms

## Deploy to GitHub + Cloudflare Pages
1. Create a new GitHub repository (for example, `global-negotia-website`).
2. Upload all files and folders in this project to the repository root. Keep the `functions/api/inquiry.js` path intact.
3. In Cloudflare, go to **Workers & Pages → Create → Pages → Connect to Git** and select the repository.
4. Framework preset: **None**. Build command: leave blank. Build output directory: `/` (repository root).
5. Deploy. Cloudflare Pages detects the `functions/` directory and deploys the `/api/inquiry` function with the site.

## Important: configure email before accepting real inquiries
The forms are implemented and call `/api/inquiry`. To deliver inquiries, configure these environment variables in Cloudflare Pages settings:
- `RESEND_API_KEY` — API key from Resend
- `CONTACT_EMAIL` — approved business inbox that should receive inquiries
- `FROM_EMAIL` — sender address verified in Resend, e.g. `Global Negotia <website@your-verified-domain.com>`

Use a sender domain you control and verify it with Resend. Do not commit keys or passwords to GitHub. After setting variables, redeploy the project and test both forms. If email delivery isn't configured, the form displays a clear message rather than pretending the inquiry was sent.

## Before public launch — business owner confirmation required
The supplied brief explicitly leaves these details open:
- Public contact name and approval of the displayed email/phone
- Whether to display a warehouse address
- Exact service area, accepted shipment types, available fulfillment services, rates, minimums and turnaround times
- Training dates, time zone, session length, tuition, payment method and enrollment details
- Owner/company bio, years of experience, approved testimonials, real business photos
- Privacy policy, terms and applicable service policies
- Final domain and access permissions

Do not publish unconfirmed claims, rates, service promises, private Zoom links, or guarantees of marketplace approval or business results.

## Design notes
- Custom gold/navy SVG logo and favicon included in `assets/`
- Responsive layout and mobile navigation
- Separate inquiry forms with browser-side validation and honeypot field
- Cloudflare Pages Function validates input and sends formatted inquiries through Resend once configured
- No framework or build dependency; no package installation required

## Local preview
You can open `index.html` directly for a visual preview. To test the `/api/inquiry` function locally, use the Cloudflare Pages local development workflow (`wrangler pages dev`) after installing Wrangler and setting local secrets in `.dev.vars`. Never add `.dev.vars` to GitHub.

## Website creation offer
The homepage includes a website creation inquiry route via WhatsApp. The current displayed offer is `$285 + $70` as provided by the owner. Confirm whether these are one-time fees, domain renewal, and/or recurring maintenance before taking payment. A five-star service-standard graphic is used; it is not represented as a verified third-party customer rating.
