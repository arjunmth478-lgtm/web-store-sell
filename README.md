# Shopnix — Cloudflare Pages + D1 starter

Includes storefront, password-protected admin panel, product CRUD, categories via product category names, and WhatsApp/Telegram contact settings. Product records persist in Cloudflare D1.

## Deploy steps
1. Back up your current GitHub `sell-web` repository before replacing files. Upload the CONTENTS of this folder to the repo.
2. Cloudflare Dashboard → Workers & Pages → D1 SQL Database → Create database named `shopnix-db`.
3. Open D1 Console and run all SQL from `schema.sql`.
4. For a Cloudflare **Pages** project connected to this repo, Settings → Functions → D1 database bindings: binding variable `DB` → select `shopnix-db`.
5. Pages project → Settings → Variables and Secrets (Functions): add `ADMIN_EMAIL` = `arjunmth2007@gmail.com`; add secret `ADMIN_PASSWORD` = choose a strong unique password; add secret `SESSION_SECRET` = long random string at least 32 characters.
6. Framework preset None, build command blank, output directory `/` (or `.` if required). Deploy/redeploy.
7. Store at your site URL. Admin at `/admin.html`.

Important: these are Cloudflare **Pages Functions** files. If your current `sell-web` is a Worker project, these Pages Functions won't run as-is; create a Pages project or ask for a Worker-specific conversion. Images are added using public HTTPS image URLs in this starter; direct file uploads need Cloudflare R2 setup. No online payments are included.
