---
name: hyperzod-catalog-builder
description: Build and maintain menus and product catalogs on Hyperzod — import from a menu photo/PDF (OCR) or spreadsheet, create categories, products, variants and multi-level add-ons, set stock, labels, tags and AI descriptions, and bulk-update prices or availability. Use for restaurant menu setup, grocery catalog upload, product import, out-of-stock updates, or catalog cleanup on Hyperzod.
---

# Hyperzod catalog builder

## Pick the fastest input path

| User has | Path | Tools |
|---|---|---|
| Photo or PDF of a menu/price list | OCR import | `start-product-ocr-import` → poll `get-product-ocr-import-status` → `get-product-ocr-import-result` → fix rows with `save-product-ocr-import-rows` → ⚠️ `confirm-product-ocr-import` |
| Spreadsheet / CSV / POS export | Product import | `start-product-import` → `get-product-import-result` → `save-product-import-rows` → ⚠️ `confirm-product-import` |
| A handful of items | Manual | `create-product-category` / `create-multiple-product-categories`, then `create-product` |

Always resolve the target merchant first (`search-merchants-tool`). Before confirming an import, show the user a short summary: number of categories, products, items with missing price/image, suspected duplicates. If the result is wrong, `discard-*-import` rather than confirming and cleaning up later.

## Structure guidelines
- 5–15 categories per menu; order them by what sells (use `get-popular-products` on existing stores).
- Use options/add-ons for size, crust, extras; multi-level add-ons for "choose a base → then toppings".
- Labels for badges (Vegan, Spicy, New, Bestseller); tags for search/filter.
- Every product needs a price, a clear name, and ideally an image. Generate missing descriptions with `generate-product-description`, show them to the user, then save with `update-product`.
- Product Scheduler / category timing for breakfast-only or happy-hour items.

## Ongoing maintenance
- Out of stock: `update-product-stock-status` (quick), `update-product-stock-counts` (quick commerce with counts), `update-product-variant-status` for a single size.
- Bulk on/off: ⚠️ `update-multiple-product-statuses` — list the affected items and confirm.
- Price changes: fetch with `get-product`, change only the price fields, `update-product`. For many items, export (`export-products`), edit, re-import.
- Copy a menu to another branch: `duplicate-product-merchant`.
- After big changes: `flush-merchant-catalog-cache` so the storefront updates.

## Quality checklist before go-live
- No product priced 0 unless intended; no empty categories; images present for top 20 items.
- Add-on prices correct and required/optional flags set.
- Tax and allergen info where the market requires it.
