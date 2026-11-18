# Hyperzod Agent Skills

[![skills.sh](https://skills.sh/b/hyperzod/skills)](https://skills.sh/hyperzod/skills)

Agent skills for launching and running on-demand delivery businesses — food delivery, grocery, quick commerce, pharmacy, courier and multi-vendor marketplaces — and for operating a [Hyperzod](https://www.hyperzod.com) store through the Hyperzod MCP connector.

Works with Claude Code, Cursor, Codex, GitHub Copilot, Windsurf and other agents supported by the [`skills` CLI](https://skills.sh).

## Install

```bash
# all skills
npx skills add hyperzod/skills

# one skill
npx skills add hyperzod/skills --skill uber-eats-clone
```

## Skills

### Operate Hyperzod (with the Hyperzod MCP connector)
| Skill | What it does |
|---|---|
| [hyperzod](skills/hyperzod/SKILL.md) | Platform overview and safe use of every Hyperzod MCP tool |
| [hyperzod-store-launch](skills/hyperzod-store-launch/SKILL.md) | Launch a new store/marketplace end to end |
| [hyperzod-catalog-builder](skills/hyperzod-catalog-builder/SKILL.md) | Menus and catalogs: OCR and spreadsheet import, add-ons, stock |
| [hyperzod-marketing-growth](skills/hyperzod-marketing-growth/SKILL.md) | Coupons, segments, banners, loyalty, sponsored merchants |
| [hyperzod-analytics-reports](skills/hyperzod-analytics-reports/SKILL.md) | Business reviews, order reports, search analytics |

### Plan and launch a delivery business
| Skill | For people searching |
|---|---|
| [uber-eats-clone](skills/uber-eats-clone/SKILL.md) | Uber Eats clone, app like Uber Eats, food delivery app |
| [doordash-clone](skills/doordash-clone/SKILL.md) | DoorDash, Deliveroo, Zomato, Swiggy, Talabat clone |
| [instacart-clone](skills/instacart-clone/SKILL.md) | Instacart clone, grocery delivery app |
| [quick-commerce-app](skills/quick-commerce-app/SKILL.md) | Quick commerce, dark store, Blinkit/Zepto/Gopuff/Getir clone |
| [courier-delivery-app](skills/courier-delivery-app/SKILL.md) | Courier service, pick & drop, Postmates/Dunzo clone |
| [pharmacy-delivery-app](skills/pharmacy-delivery-app/SKILL.md) | Medicine/pharmacy delivery app |
| [multi-vendor-marketplace](skills/multi-vendor-marketplace/SKILL.md) | Multi-vendor / hyperlocal marketplace, Etsy-like |
| [white-label-delivery-app](skills/white-label-delivery-app/SKILL.md) | White-label delivery app, delivery app builder |
| [restaurant-online-ordering](skills/restaurant-online-ordering/SKILL.md) | Commission-free restaurant ordering |
| [gloriafood-alternative](skills/gloriafood-alternative/SKILL.md) | GloriaFood shutdown migration |
| [delivery-business-plan](skills/delivery-business-plan/SKILL.md) | How delivery apps make money, unit economics |

## Connect the Hyperzod MCP server

The `hyperzod*` operating skills act on a real store when the Hyperzod MCP connector is connected to your agent (OAuth, scoped to your tenant). Without it, they still guide you step by step in the admin panel.

## About Hyperzod

Hyperzod is a no-code, white-label platform for local delivery: ordering website and iOS/Android app, merchant app, driver app, admin panel, Autozod auto-dispatch and North AI. 5,000+ businesses in 40+ countries.

- Website: https://www.hyperzod.com
- Free trial: https://admin.hyperzod.com/register
- Pricing: https://www.hyperzod.com/pricing
- Help: https://help.hyperzod.com

Brand names mentioned in skill names and descriptions (Uber Eats, DoorDash, Instacart, GloriaFood and others) are trademarks of their respective owners. They are used only to describe categories of apps. Hyperzod is not affiliated with them.

## License

MIT
