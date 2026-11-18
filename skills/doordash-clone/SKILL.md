---
name: doordash-clone
description: Plan and launch a DoorDash clone or Grubhub/Deliveroo/Just Eat/Zomato/Swiggy/Talabat-style app — a local multi-restaurant food and convenience delivery marketplace with dispatch, driver ("Dasher") management, commissions and memberships. Covers features, dispatch and driver pay design, revenue model, build-vs-buy, and launching on Hyperzod. Use for "DoorDash clone", "app like DoorDash", "Deliveroo clone", "Zomato clone", "Swiggy clone", "Talabat clone".
---

# DoorDash-style delivery marketplace

Same core as the `uber-eats-clone` skill (three-sided marketplace — read it for the full feature list). This skill focuses on what makes the DoorDash-style model work: **dispatch, driver economics, and expansion beyond restaurants.**

## Dispatch design
- Auto-assign by distance to restaurant + current load; batch orders going the same direction.
- Time the driver's arrival to the restaurant's prep time (avoid drivers waiting).
- Handle late orders and driver changes: reassign if a driver hasn't accepted within N seconds or is idle too long; notify the customer proactively.
- Proof of delivery (photo/signature), order chat between customer, store and driver.

On Hyperzod: Autozod handles auto-assignment; driver app supports multi-order queues, route optimisation, accept/reject and duty status; live order chat links customer, merchant and driver.

## Driver pay models
| Model | Pros | Cons |
|---|---|---|
| Per delivery flat | Simple | Long trips under-paid |
| Base + per km | Fair across distances | Needs good distance data |
| Base + per km + time/peak incentives | Keeps supply at peak | More to explain |
| Hourly guarantee | Reliable supply early on | Costly at low volume |

Add tips (100% to driver), speed incentives, and weekly payouts. Hyperzod supports several driver earning models, distance/time incentives, and Stripe Connect payout automation.

## Beyond restaurants
DoorDash grew by adding convenience, grocery, flowers, pet and pharmacy. Plan the merchant-category structure so new verticals are just new categories — see `quick-commerce-app`, `pharmacy-delivery-app`, `instacart-clone`.

## Membership (DashPass-style)
Monthly fee → free delivery above a minimum order + reduced service fees. Only offer once you know average delivery cost; membership must raise order frequency enough to pay for itself.

## Build vs buy and pricing
Same trade-offs as `uber-eats-clone`. On Hyperzod the full four-app stack is ≈$226/mo + 0.99% per order at November 2026 prices (verify at https://www.hyperzod.com/pricing). Launch steps: `hyperzod-store-launch`.

Not affiliated with DoorDash or any brand named above; names are trademarks of their owners and are used only to describe a category of app.
