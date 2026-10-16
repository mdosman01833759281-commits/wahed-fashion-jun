# Wahed Fashion Jun — Full-stack starter shop

A responsive fashion storefront with an Express backend, SQLite database, customer registration/login, shopping cart, order placement, and a basic admin panel.

## Requirements
- Node.js 20 LTS or newer recommended
- npm (included with Node.js)

## Run locally
1. Extract this project folder.
2. Open a terminal in the project folder.
3. Install dependencies:
   ```bash
   npm install
   ```
4. Copy `.env.example` to `.env`.
5. Change `SESSION_SECRET`, `ADMIN_EMAIL`, and `ADMIN_PASSWORD` in `.env` before running.
6. Start:
   ```bash
   npm start
   ```
7. Visit http://localhost:3000

The SQLite database (`shop.db`) is created automatically and starter products are inserted on first run.

## Admin
Use the email and password configured in `.env`. The default values are only for local setup; change them before starting. If you change the admin email after the database has already been created, the existing admin account will remain unchanged. For a clean test database, stop the server and delete `shop.db` (this deletes local users/orders/products too), then restart.

Admin users can review orders, update order status, add products, and hide products.

## Payments
This starter supports cash on delivery and a manual-payment placeholder. **It does not collect online payments.** To enable bKash, Nagad, SSLCommerz, Stripe, or another gateway, register a merchant account and implement the provider's server-side checkout and verified webhook/callback flow. Never collect card numbers, wallet PINs, or OTPs directly in this website. Do not mark an order paid based only on a browser response.

## Before publishing online
This is a starter, not a production-audited store. Before deployment:
- Use HTTPS and a strong random `SESSION_SECRET`.
- Use a persistent database and persistent session store suitable for your hosting provider.
- Add rate limiting, CSRF protection where appropriate, email verification/password reset, input validation, backups, logging, and privacy/terms pages.
- Set secure cookie options correctly behind your HTTPS reverse proxy.
- Review inventory, refunds, shipping, and payment workflows.
- Do not commit `.env` or `shop.db` to source control.
- Use a supported hosting service and test the deployment configuration.

## Main files
- `server.js` — API, authentication, database, orders, admin endpoints
- `public/index.html` — storefront structure
- `public/styles.css` — responsive visual design
- `public/app.js` — storefront, cart, auth, checkout, admin UI
- `.env.example` — environment variable template
