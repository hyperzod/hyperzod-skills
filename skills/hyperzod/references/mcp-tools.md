# Hyperzod MCP tools by job

Tool names as exposed by the Hyperzod MCP connector. ⚠️ = destructive or customer-visible; confirm with the user first and pass `confirmed: true` only after approval.

## Tenant settings and storefront
- Read: `get-tenant-settings`, `get-tenant-general-settings`, `get-tenant-theme-settings`, `get-tenant-color-settings`, `get-tenant-language-settings`, `get-tenant-order-settings`, `get-tenant-store-timing`, `get-url-settings`, `get-serviceability-settings`, `get-public-mobile-settings`, `search-tenant-settings`
- Write: `update-general-settings`, `update-theme-settings`, `update-color-settings`, `update-language-settings`, `update-order-settings-admin`, `update-tenant-store-settings`, `update-tenant-store-timing`
- Payments: `list-payment-modes`, ⚠️ `set-tenant-payment-mode-status`
- Cache: ⚠️ `clear-tenant-cache`

## Pages and page builder
`list-custom-pages`, `list-admin-pages`, `list-pages-by-ids`, `get-page`, `get-builder-page`, `get-page-blueprint`, `get-page-editor-configuration`, `get-new-page-section(-admin)`, `create-page`, `update-page`, `update-global-page-section`, `update-page-builder-assets`, ⚠️ `delete-page`, ⚠️ `delete-section`, `get-assets`, `upload-file`, ⚠️ `delete-asset`

## Merchants (stores, restaurants, vendors)
- Find: `list-merchants`, `search-merchants-tool`, `search-all-merchants`, `list-merchants-by-ids`, `get-merchant`, `count-merchants`, `list-deleted-merchants`, `list-nearby-merchant-locations`
- Create/update: `create-merchant`, `update-merchant`, `update-merchant-images`, `update-merchant-opening-hours`, `update-merchant-store-timing`, `update-merchant-delivery-settings`, `update-merchant-order-settings`, `update-merchant-pos-management`
- Status: ⚠️ `update-merchant-active-status`, ⚠️ `set-merchant-order-accepting`, ⚠️ `delete-merchant`
- Settings reads: `get-merchant-settings`, `get-merchant-delivery-settings`, `get-merchant-order-settings`, `get-merchant-opening-hours`, `get-merchant-store-timing`, `get-merchant-location`, `get-merchant-notification-settings`, `check-merchant-delivery-availability`
- Merchant categories: `list-merchant-categories`, `create-merchant-category`, `update-merchant-category`, ⚠️ `delete-merchant-category`
- Featured / sponsored: `list-featured-merchants`, `create-featured-merchant`, ⚠️ `delete-featured-merchant`, `list-sponsored-merchants`, `create-sponsored-merchant`, ⚠️ `delete-sponsored-merchant`
- Packages / commissions: `list-merchant-packages`, `create-merchant-package`, `update-merchant-package`, ⚠️ `delete-merchant-package`, `list-commissions`
- Bulk: `validate-merchant-import`, `import-merchants`, `export-merchants`, `list-merchant-imports`, `list-merchant-exports`

## Catalog
- Products: `list-products`, `search-products`, `get-product`, `count-products`, `create-product`, `validate-product`, `update-product`, `duplicate-product`, `add-product-image`, `set-product-3d-model`, `generate-product-description`, ⚠️ `set-product-status`, ⚠️ `update-multiple-product-statuses`, ⚠️ `delete-product`
- Stock: `update-product-stock-status`, `update-product-stock-counts`, `update-product-variant-status`
- Options / add-ons: `list-product-options`, `get-product-option`, `duplicate-product-option`, `update-product-option-status`, ⚠️ `delete-product-option`
- Categories: `list-product-categories`, `search-product-categories`, `create-product-category`, `create-multiple-product-categories`, `update-product-category`, `update-multiple-product-categories`, `update-product-category-status`, `reorder-product-in-category`, ⚠️ `delete-product-category`
- Labels / tags: `list-product-labels`, `create-product-label`, `update-product-label`, `list-product-tags`, `create-product-tag`, `update-product-tag` (+ ⚠️ deletes)
- Spreadsheet import: `start-product-import` → `get-product-import-result` → `save-product-import-rows` → ⚠️ `confirm-product-import` / `discard-product-import`
- Photo/PDF menu (OCR) import: `start-product-ocr-import` → `get-product-ocr-import-status` → `get-product-ocr-import-result` → `save-product-ocr-import-rows` → ⚠️ `confirm-product-ocr-import` / `discard-product-ocr-import`
- Export: `export-products`, `list-product-exports`; cache: `flush-merchant-catalog-cache`

## Orders
`list-orders-tool`, `list-store-orders`, `search-store-orders`, `get-store-order`, `list-scheduled-orders`, `list-order-statuses`, `list-order-types`, `get-order-scheduling-slots`, `add-order-note`, ⚠️ `update-order-status-tool`, `update-order-type`, `get-order-settings`, `update-order-settings`

## Customers and segments
- Customers: `list-customers-tool`, `search-customers-tool`, `get-customer-tool`, `count-customers`, `create-customer-tool`, `update-customer-tool`, ⚠️ `set-customer-status-tool`, ⚠️ `delete-customer-tool`, `list-customer-orders`, addresses (`get/create/update/delete-customer-address`), `import-customers`, `export-customers`
- Segments: `get-segment-filters`, `create-segment`, `update-segment`, `list-segments`, `get-segment`, `count-segment`, `count-segment-by-country`, `execute-segment`, `list-segment-customers`, `check-user-in-segment`, ⚠️ `delete-segment`

## Marketing
- Coupons: `list-coupons`, `create-coupon`, `update-coupon`, ⚠️ `set-coupon-status`, ⚠️ `reset-coupon-usage`, `list-coupon-history`, ⚠️ `delete-coupon`
- Banners / popups: `list-banners`, `create-banner`, `update-banner`, `list-popups`, `create-popup`, `update-popup` (+ ⚠️ deletes)
- Campaigns: `get-campaign`, ⚠️ `delete-campaign`; notifications: `list-notification-channels`, `list-notification-events`, `list-notification-logs`, `send-test-email`
- Reviews: `list-reviews`, `create-review`, `update-review`, `get-review-settings`, ⚠️ `delete-review`
- Abandoned carts: `list-abandoned-carts`

## AI features
`get-ai-recommendation-status`, `get-recommendation-settings`, `initialize-recommendations`, ⚠️ `toggle-ai-recommendations`, `get-shopping-assistant-settings`, `update-shopping-assistant-settings`, ⚠️ `toggle-shopping-assistant`, `list-shopping-assistant-conversations`, `get-shopping-assistant-conversation`

## Analytics and reports
- Dashboards: `get-order-dashboard-stats`, `get-orders-and-statistics`, `get-order-statistics`, `get-order-analytics`, `get-tenant-stats`, `get-user-stats`, `get-device-stats`, `get-payment-mode-stats`, `get-weather-stats`, `get-order-map`
- Merchants/products: `get-merchant-analytics`, `get-merchant-order-stats`, `get-merchant-orders-and-statistics`, `get-popular-merchants`, `get-popular-products`, `get-product-analytics`
- Reports: `get-tenant-report-columns`, `get-tenant-order-report`, `export-tenant-order-report`, `get-merchant-report-columns`, `get-merchant-order-report`, `export-merchant-order-report`
- Search analytics: `get-search-summary`, `get-search-volume`, `get-search-queries`, `get-search-keywords`, `get-search-funnel`, `get-search-lost-value`, `get-search-lost-query-detail`, `get-search-map`, `get-search-merchants`, `get-search-taps`, `get-search-locales`, `get-search-guest-split`
- Jobs: `get-job-status`, `list-tenant-exports`
