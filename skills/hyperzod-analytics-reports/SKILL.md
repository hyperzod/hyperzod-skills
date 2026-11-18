---
name: hyperzod-analytics-reports
description: Analyse and report on a Hyperzod delivery business — order volume, revenue, AOV, top merchants and products, payment modes, devices, order heatmap, search demand and lost searches, merchant performance, and exportable order reports. Use for weekly/monthly business reviews, merchant payouts reconciliation, "how is my store doing", or finding growth opportunities on Hyperzod.
---

# Hyperzod analytics and reports

## Standard business review
Ask for the period (default: last 30 days vs previous 30). Gather:

1. Headline: `get-order-dashboard-stats`, `get-orders-and-statistics` → orders, GMV, AOV, cancellations.
2. Customers: `get-user-stats` → new vs returning; `count-customers`.
3. Mix: `get-payment-mode-stats`, `get-device-stats`, order types.
4. Leaders: `get-popular-merchants`, `get-popular-products`; per merchant `get-merchant-analytics`.
5. Geography: `get-order-map` (where demand is) vs `get-search-map` (where searches happen) — gaps suggest new merchants or delivery zones.
6. Search: `get-search-summary`, `get-search-funnel`, `get-search-lost-value`, `get-search-queries` → what customers want but can't find.

Present: a short summary (3–5 bullets with numbers and % change), then a table, then 2–3 concrete actions. Chart trends over time when a chart tool is available.

## Exportable order reports
- Tenant: `get-tenant-report-columns` → `get-tenant-order-report` or `export-tenant-order-report` (async; poll `get-job-status`).
- Per merchant (payout reconciliation): `get-merchant-report-columns` → `get-merchant-order-report` / `export-merchant-order-report`; compare with `list-commissions`.

## Interpreting
- Falling AOV + rising orders usually means discount-driven growth — check coupon history.
- High search volume with low conversion for a term = catalog gap or wrong naming.
- Merchant with high cancellations: check opening hours, `set-merchant-order-accepting` behaviour, prep time.
- Don't infer causes the data can't show; label assumptions.
