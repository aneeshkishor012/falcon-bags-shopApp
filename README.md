# Falcon Bags — HTML/CSS/JavaScript Shopping App Prototype

## Start
Open `index.html` in Chrome/Edge or run a local server:

```bash
npx serve .
```

No npm dependencies, build step, or environment variables required. All three files must stay together.

## Features that work in this browser prototype
- Responsive homepage with lightweight CSS animated bag hero and category navigation
- Catalog search, category/price filters, sorting, product detail pages
- Wishlist, quantity-aware cart, coupon, shipping threshold, address entry, COD and online **demo** checkout
- Local demo order history and order-status updates
- Admin demo: products, SKUs, stock edits, orders, coupons, shipping settings, staff/suppliers record lists, enquiries, reviews moderation, summary reports
- CSV product import + template download (CSV only)
- Data persists in the same browser's `localStorage`; use a separate browser profile to start clean

## Critical limitations — NOT a production release
- No Node/Express API or Supabase connection; there is no server-side database, authorization, concurrency control, or persistent multi-user sharing.
- **No actual Razorpay payment**: the online payment option makes a demo order marked *Demo (not paid)*. Do not collect real payments.
- Login is a display-only profile: no email/password or phone OTP, session verification or staff RBAC.
- Stock checks are browser-local and cannot protect against overselling across devices.
- PIN-code check validates only 6 digits, not area serviceability; supplier records do not implement purchases.
- Product imagery is illustrated using emoji, not uploaded photographs; hero uses CSS simulated depth, not a real 3D model.
- Legal pages contain unapproved placeholder text. No real shipping, returns, refund, courier, messaging, invoices or backup infrastructure.
- CSV import is a simple demo parser; a production importer needs file-size caps, robust parsing, transaction boundaries, image handling and server validation.
- Reviews are not verified against purchases. Admin dashboard is publicly accessible in this demo, so never host it as a live store.

## Production implementation required to satisfy Falcon Bags SRS v1.0
Use React or vanilla JS UI + Node.js/Express REST APIs + Supabase PostgreSQL/Auth/Storage. Implement server-side authorization and validation, Supabase migrations and RLS, stock reservation within database transactions, payment intent creation and Razorpay signature/webhook verification + idempotency, rate limiting, audit logs, proper mail/SMS OTP provider, per-PIN shipping tables, product media upload and optimization, approved legal copy, QA and deployments.

The ₹1,00,000 development budget described in the SRS excludes third-party operating costs, per the SRS. This prototype is an implementation starting point, **not** a claim that all SRS acceptance criteria have been completed.
"# falcon-bags-shopApp" 
