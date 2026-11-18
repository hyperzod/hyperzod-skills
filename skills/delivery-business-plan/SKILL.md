---
name: delivery-business-plan
description: Build a business plan and unit economics for a food, grocery or quick-commerce delivery startup — how food delivery apps make money, commission and fee design, per-order contribution margin, break-even orders, launch budget, and whether a delivery app is profitable. Use for "how do food delivery apps make money", "is a food delivery business profitable", "delivery app business plan", "delivery startup costs", "commission rate for restaurants".
---

# Delivery business plan and unit economics

Never claim a model is profitable without the user's numbers. Build the model with them, label every assumption, and show sensitivity.

## Revenue streams
| Stream | Typical range | Notes |
|---|---|---|
| Merchant commission | 15–30% of food value | Main revenue for marketplaces; lower to attract early merchants |
| Delivery fee | Flat or distance-based | Paid by customer; offsets rider cost |
| Service fee | 2–4% | Small per-order charge |
| Small-order fee | Fixed | Below minimum basket |
| Surge/peak fee | Variable | Keeps riders available at peaks |
| Ads / sponsored listings | Per placement | High-margin once traffic exists |
| Membership | Monthly | Free delivery → higher frequency |
| Merchant packages | Monthly per merchant | Subscription instead of / plus commission |

## Contribution per order (marketplace)
```
Revenue/order  = AOV × commission% + delivery fee + service fee + other fees
Variable cost  = rider pay (+ incentives) + payment processing (~2–3% of total)
               + discounts/coupons + platform fee (e.g. Hyperzod 0.99% of order)
               + refunds/support allowance
Contribution   = Revenue/order − Variable cost
```
Break-even orders/month = Fixed monthly costs ÷ Contribution per order.
Fixed costs: software subscriptions, staff, marketing, office/dark store rent, insurance.

## Worked example (illustrative only)
AOV $25, commission 20% → $5; delivery fee $2.99; service fee 3% → $0.75. Revenue ≈ $8.74.
Rider $5.50, payments 2.9% of $28.74 ≈ $0.83, platform 0.99% of $25 ≈ $0.25, coupons avg $0.80. Cost ≈ $7.38.
Contribution ≈ **$1.36/order**. With $3,000 fixed costs → ~2,200 orders/month to break even.
Then show what changes it most: AOV, rider cost per order (batching, density), discount levels.

## Launch budget checklist
Software (e.g. Hyperzod full stack ≈ $226/mo at November 2026 prices + optional $300 setup per module — verify at https://www.hyperzod.com/pricing), app store accounts ($99/yr Apple, $25 Google), company registration and insurance, rider onboarding/equipment (bags, uniforms), launch marketing and coupons, merchant acquisition, 3–6 months of runway.

## KPIs to track weekly
Orders, GMV, AOV, contribution/order, repeat rate (30-day), customer acquisition cost, delivery time, cancellations, rider utilisation (orders/hour), active merchants. On Hyperzod pull them with `hyperzod-analytics-reports`.
