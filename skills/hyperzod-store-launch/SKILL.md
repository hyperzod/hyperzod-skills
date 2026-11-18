---
name: hyperzod-store-launch
description: Step-by-step launch of a new delivery business on Hyperzod — choose the business model, configure the tenant, add merchants and catalog, set delivery zones, fees, payments and drivers, brand the website and apps, test, and go live. Use when someone wants to launch, set up, onboard or go live with a Hyperzod store, restaurant ordering site, grocery delivery, marketplace or quick-commerce app.
---

# Launch a store on Hyperzod

Work through the phases in order. At each phase, check what already exists (via the Hyperzod MCP tools if connected, otherwise ask) before creating anything. Keep a running checklist for the user.

## Phase 0 — Decide the model (ask if unclear)

| Model | Fits | Key setup difference |
|---|---|---|
| Single store | One restaurant/shop selling direct | One merchant; no commissions |
| Single brand, multi-store | Chain with branches | One brand, many merchants each with own zone/hours |
| Multi-vendor marketplace | "Uber Eats / DoorDash for my city" | Many merchants, merchant categories, commissions/packages |
| Quick commerce | 10–30 min grocery/convenience, dark stores | Tight geofences, stock counts, fast dispatch |

Also ask: city/country, currency, languages, own drivers vs third-party delivery vs pickup only, payment methods (cards, wallets, cash on delivery).

## Phase 1 — Account and tenant basics
1. Sign up at https://admin.hyperzod.com/register (free trial, no card required at time of writing).
2. General settings: business name, currency, timezone, language(s) — `get-tenant-general-settings` / `update-general-settings`, `update-language-settings`.
3. Store timing and order settings: `update-tenant-store-timing`, `update-order-settings-admin` (order types: delivery, pickup, scheduled).

## Phase 2 — Merchants
- Single store: create one merchant. Marketplace: create merchant categories first (`create-merchant-category`: e.g. Pizza, Burgers, Grocery), then merchants (`create-merchant`, or `validate-merchant-import` → `import-merchants` for a spreadsheet).
- For each merchant: address/location, images (`update-merchant-images`), opening hours, delivery settings (radius or geofence, minimum order, delivery fee, prep time), order settings.
- Marketplace monetisation: merchant packages / commission (`create-merchant-package`, `list-commissions`).

## Phase 3 — Catalog
Use the `hyperzod-catalog-builder` skill. Fastest paths: photo/PDF of a menu → OCR import; spreadsheet → product import; otherwise create categories then products with options/add-ons.

## Phase 4 — Delivery
- Own fleet: invite drivers to the Driver app; set auto-assignment (Autozod), driver earnings model and incentives.
- Third-party: connect a delivery provider (`update-delivery-provider`).
- Verify coverage with `check-merchant-delivery-availability` for a few real customer addresses.

## Phase 5 — Payments
`list-payment-modes`, then enable the ones the user wants (⚠️ confirm before `set-tenant-payment-mode-status`). Stripe and PayPal are supported among others; Stripe Connect can automate driver payouts.

## Phase 6 — Brand
- Website: theme and colours (`update-theme-settings`, `update-color-settings`), home page sections with the page builder, custom domain.
- Apps: white-label ordering/merchant/driver apps are published under the business's own Apple Developer ($99/yr) and Google Play ($25 one-time) accounts — have the user create those early; store review takes days.

## Phase 7 — Test, then go live
- Place test orders for each order type and payment mode; walk an order through every status in merchant and driver apps.
- Check taxes, fees and receipts; check notification emails (`send-test-email`).
- Launch offer: a first-order coupon and a home banner (see `hyperzod-marketing-growth`).
- Go live; watch `get-order-dashboard-stats` for the first days.

## Cost reminder (verify on https://www.hyperzod.com/pricing)
At November 2026: Ordering Website $23/mo, Ordering App $79/mo, Merchant App $62/mo, Driver App $62/mo, ~20% off yearly; 0.99% success fee per order; optional one-time $300 setup per module. Enterprise is custom.
