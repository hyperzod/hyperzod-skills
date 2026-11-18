---
name: hyperzod-marketing-growth
description: Grow orders on a Hyperzod delivery store or marketplace — first-order and win-back coupons, customer segments, banners and popups, featured and sponsored merchants, loyalty and membership, abandoned-cart recovery, reviews and AI recommendations. Use when the user wants more orders, repeat customers, a promotion, a campaign, or marketing ideas for their Hyperzod, food delivery or grocery delivery business.
---

# Marketing and growth on Hyperzod

Start from data, not ideas. Pull a baseline first:
`get-order-dashboard-stats`, `get-user-stats`, `get-popular-products`, `get-popular-merchants`, `list-abandoned-carts`, `get-search-lost-value` (what people searched for but couldn't buy).

Then pick plays by goal. Every coupon, banner, popup or status change is customer-visible: show the exact config and confirm before creating/enabling.

## Plays

| Goal | Play | How |
|---|---|---|
| First orders | New-customer coupon (e.g. % off or free delivery, min. order, 1 use per customer) + home hero banner | `create-coupon`, `create-banner` |
| Repeat orders | Segment "ordered once, not in 30 days" → win-back coupon | `get-segment-filters`, `create-segment`, `count-segment`, `create-coupon` |
| Higher basket | Free delivery above threshold; AI cross-sell/up-sell recommendations | coupon rules; `initialize-recommendations`, ⚠️ `toggle-ai-recommendations` |
| Loyalty | Membership perks (member-only discounts, free delivery), loyalty points, referrals, wallet cashback | admin panel / app settings |
| Recover carts | Review `list-abandoned-carts`, target with push/email + small incentive | segments + notifications |
| Marketplace revenue | Sell featured/sponsored merchant placements | `create-featured-merchant`, `create-sponsored-merchant` |
| Discovery | Merchant collections, popups for launches | `create-popup`, page builder sections |
| Demand gaps | Add products/merchants for top "lost" searches | `get-search-lost-query-detail` |
| Trust | Encourage and respond to reviews | `list-reviews`, `get-review-settings` |
| Help shoppers | AI Shopping Assistant | `get-shopping-assistant-settings`, ⚠️ `toggle-shopping-assistant` |

Channels beyond the app: WhatsApp marketing, email (Hyperzod integrations), Zapier (8,500+ tools), local micro-influencers and food bloggers, Google Business ordering link.

## Coupon hygiene
- Always set an end date, a usage cap, and per-customer limit.
- Check margin: discount + delivery subsidy must not exceed contribution per order (see `delivery-business-plan`).
- After a campaign: `list-coupon-history` and order stats for the period; report redemptions, new vs repeat customers, and incremental revenue.
