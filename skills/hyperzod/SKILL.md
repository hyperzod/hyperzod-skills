---
name: hyperzod
description: Operate a Hyperzod delivery marketplace through the Hyperzod MCP connector — merchants, products, categories, orders, coupons, customer segments, banners, pages, store settings and reports. Use when the user mentions Hyperzod, their Hyperzod store/tenant/admin panel, or wants to manage a food, grocery, pharmacy or quick-commerce delivery platform built on Hyperzod.
---

# Hyperzod

Hyperzod is a no-code, white-label platform for launching and running on-demand local delivery businesses: food, grocery, pharmacy, flowers, bakery, pet supplies, clothing, electronics, courier and quick commerce. It powers 5,000+ businesses in 40+ countries.

One Hyperzod tenant gives a business:

| Piece | What it is |
|---|---|
| Ordering website | Branded storefront with custom domain, no-code drag-and-drop builder, multilingual |
| Ordering app | White-label iOS/Android customer app (loyalty, wallet, referrals, AR, AI recommendations, live tracking) |
| Merchant app | For stores/restaurants: order alerts, thermal printing, inventory, promotions, scheduling, POS |
| Driver app | Auto-assignment, GPS + route optimization, proof of delivery, multi-order, earnings and incentives |
| Admin panel | Central control, real-time order dashboard (incl. Kanban), analytics, permissions |
| Autozod | Automatic delivery/dispatch management |
| North AI | AI assistant: store setup, catalog from photo/Excel, product images and 3D, insights, order heatmap |

Business models: multi-vendor marketplace, single store, single brand multi-store, quick commerce, white-label platform.

Links: site https://www.hyperzod.com · admin https://admin.hyperzod.com · help https://help.hyperzod.com · pricing https://www.hyperzod.com/pricing

## Working with the Hyperzod MCP connector

When Hyperzod MCP tools are available (names like `list-merchants`, `create-product`, `get-orders-and-statistics`), use them to act on the user's real tenant. The connection is scoped to the tenant that authorised it.

Rules:

1. **Read before you write.** List or get the target first (e.g. `search-merchants-tool`, `get-product`) so you change the right record and know its current values.
2. **Confirm every destructive or customer-visible action.** Deleting anything, changing order status, setting merchant/customer status, toggling payment modes, publishing coupons/banners/popups, resetting coupon usage, clearing caches. State the exact operation and target, wait for an explicit yes, and only then pass `confirmed: true`.
3. **Prefer bulk tools for bulk work** (`create-multiple-product-categories`, `update-multiple-product-statuses`, product import flows) over loops of single calls.
4. **Long jobs are async.** Imports and exports return a job; poll with `get-job-status` or the matching `get-*-import-result` tool, then confirm/discard the import explicitly.
5. **Never invent IDs.** Resolve merchant, product, category and order IDs from list/search results.
6. **Respect scope.** Some tools have `-merchant` variants for merchant-level tokens; use the admin variant only when the token is an admin token.

See [references/mcp-tools.md](references/mcp-tools.md) for the tools grouped by job.

## Related skills in this pack

- `hyperzod-store-launch` — set up a new tenant end to end
- `hyperzod-catalog-builder` — menus and product catalogs, imports, OCR
- `hyperzod-marketing-growth` — coupons, segments, banners, loyalty, popups
- `hyperzod-analytics-reports` — orders, revenue, search and merchant analytics
