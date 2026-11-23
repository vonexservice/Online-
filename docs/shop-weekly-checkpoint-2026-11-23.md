# Vonex Shop SEO checkpoint — 2026-11-23

**Scope:** shop.vonex.ca ecommerce orders, organic visibility, technical SEO and acquisition tracking.  
**Review type:** Read-only Shopify Admin GraphQL, ShopifyQL analytics, current theme file inspection, public crawl comparison and GitHub repository review.  
**Production changes:** None. No Shopify theme/settings/page changes, publishing, outreach, listings or backlink placements.

## Executive summary

1. GSC Wizard access is blocked by an inactive subscription. The last available shop Search Console snapshot is historical through 2026-10-11.
2. Shopify records 2 orders and $272.87 total sales in the latest complete 30 days (2026-10-24 to 2026-11-22), compared with 8 orders and $997.66 in the previous 30 days. Net sales were $242.64 versus $859.36.
3. Shopify reports 27,780 sessions, 785 sessions reaching checkout and 1 completed-checkout session in the same 30-day window. Two paid orders were recorded. Checkout events exceed cart-add sessions (785 versus 235); treat session conversion and traffic quality as unreliable until pixels/events are reconciled.
4. The published Saskatoon landing page body was updated 2026-11-03 and currently states $10 shipping below $100 and free shipping at $100+. This matches the general Canadian delivery profile. The older public crawl still shows no-minimum/free-next-day/24-7 copy and is labelled “Crawled: last month”; it may be stale and should not trigger a copy change without a fresh storefront render.
5. The current MAIN theme is “Vonex - toner finder fix (draft)”, updated 2026-11-18. Product-grid code strips all query parameters from product URLs, which may discard legitimate variant selection. Product breadcrumb JSON-LD uses collection-scoped URLs; validate before patching.
6. No new backlinks or citations are verified. Four shop directory candidates remain research-only.

## 1. Search Console and organic performance

GSC Wizard returned `payment_required` on 2026-11-23. No fresh property, query, page, sitemap or indexing report could be retrieved.

Restore access: https://tool.gscwizard.com/settings/subscription

Historical snapshot for `https://www.shop.vonex.ca/` through 2026-10-11:
- 74 clicks
- 25,773 impressions
- About 0.287% CTR
- Average position about 12.78

Historical collection samples:
- HP toner Canada: 2,702 impressions, 1 click, average position 31.93
- Brother supplies Canada: 855 impressions, 0 clicks, average position 36.90
- Canon supplies: 396 impressions, 0 clicks, average position 40.94

These are not current figures. The GSC property used historically was the www host; Shopify's connected store domain is www.shop.vonex.ca. Confirm the selected property after GSC access returns.

## 2. Shopify sales and orders

### Latest complete 30 days: 2026-10-24 to 2026-11-22

| Metric | Current 30 days | Previous 30 days |
|---|---:|---:|
| Orders | 2 | 8 |
| Gross sales | $242.64 | $1,357.67 |
| Sales reversals | $0.00 | -$488.31 |
| Net sales | $242.64 | $859.36 |
| Total sales | $272.87 | $997.66 |

### Latest complete 90 days: 2026-08-25 to 2026-11-22

| Metric | Current 90 days | Previous 90 days |
|---|---:|---:|
| Orders | 16 | 16 |
| Gross sales | $2,432.90 | $4,355.64 |
| Sales reversals | -$488.31 | -$1,867.06 |
| Net sales | $1,914.59 | $2,468.58 |
| Total sales | $2,236.86 | $2,926.66 |

Order count is unchanged over 90 days, but total and net sales are lower. Do not claim sales growth. These are store-wide Shopify sales, not organic-search-attributed revenue.

### Order-referrer evidence

For 2026-10-24 to 2026-11-22:
- Blank referrer: 2 orders, $272.87 total sales, $242.64 net sales.
- Search referrer: 0 orders; previous period had 3 orders and $326.16 total sales.
- Social referrer: 0 orders; previous period had 1 order and negative net sales.

Shopify's “search” referrer is not a clean organic SEO attribution report. Reconcile it with GSC and GA4 before attributing orders to SEO.

## 3. Sessions and conversion tracking

ShopifyQL, 2026-10-24 to 2026-11-22:
- Sessions: 27,780 versus 60,777 in the preceding period.
- Sessions with cart additions: 235 versus 399.
- Sessions reaching checkout: 785 versus 453.
- Sessions completing checkout: 1 versus 6.
- Two paid orders were recorded in the same period.

Referrer source:
- Direct: 26,344 sessions.
- Search: 147.
- Bing: 5.
- Social: 1,198.
- Blank: 81.
- Unknown: 10.

The 785 checkout sessions exceed 235 cart-addition sessions, and the one completed-checkout session does not reconcile with two paid orders. This is a measurement inconsistency, not proof that orders were lost. Direct-labelled traffic dominates. The wide international traffic pattern may include noisy/automated traffic or attribution problems, but bots are not proven.

Top landing paths by sessions:
- `/fr/collections/office-workplace`: 4,458
- `/collections/all`: 4,240
- `/search`: 3,318
- `/fr/collections/office-workplace-supplies`: 2,945
- `/`: 791

None of these top landing paths recorded a completed-checkout session in this report. Investigate tracking and landing-page quality before changing SEO copy based on sessions alone.

Fulfillment report, 2026-08-25 to 2026-11-22:
- 12 orders fulfilled
- 7 orders shipped
- 7 orders delivered
- Median days from order to fulfillment: 0.0

The sample is small. It does not establish that every order ships within 24 hours; validate fulfillment timing before relying on the homepage “Ships within 24 hrs” claim.

## 4. Shipping page and active delivery profiles

Shopify Admin confirms the published page:
- Title: Printer Supplies Saskatoon | Toner, Ink & Office Supplies
- Handle: `saskatoon-sk-printer-supplies`
- Published: yes
- Template: `page`
- Last updated: 2026-11-03
- Current body: $10 flat shipping under $100; free shipping at $100+; orders are usually processed within one business day.

Active delivery profiles:
- General profile, Canada zone: $10 CAD for $0–$99.99; free at $100+.
- Saskatchewan zone: $10 Standard rate with no price condition plus a free rate at $100+.
- Zebra Printers profile: $25 CAD flat rate; one location reports no rates.

The public crawl of the Saskatoon page is labelled “Crawled: last month” and still displays older claims such as free shipping with no minimum, free next-day delivery and 24/7 support. The newer published Shopify Admin page body is different and matches the general delivery rates. Do not edit based on the stale crawl alone; obtain a fresh rendered-page/checkout check. Verify the Zebra location exception separately.

The current page body also states a one-year warranty for compatible/remanufactured cartridges. Confirm that statement against the current supplier/return policy before promoting it.

## 5. Published theme and technical SEO

Shopify Admin confirms:
- MAIN theme: **Vonex - toner finder fix (draft)**, theme ID `gid://shopify/OnlineStoreTheme/191330877745`, updated 2026-11-18.
- “Vonex - clean card links rebuild (2026-11-02)” and “Vonex SEO fixes 2026-11-05 (preview)” remain unpublished.

Read-only inspection of the MAIN theme:
- `layout/theme.liquid` outputs the title, meta description when present and canonical URL.
- Collection tag pages receive noindex and canonical to the base collection.
- `content_for_header` is present and may inject app/customer-event scripts.
- No hard-coded GA4/GTM ID was found in the inspected theme layout/snippets/config. The available Admin GraphQL query can read a web pixel by ID but cannot enumerate all configured pixels; GA4/web-pixel setup remains unverified.
- `snippets/product-grid-item.liquid` assigns `product.url | split: '?'` to `product_link`, stripping every query parameter. This may discard legitimate `variant=` selection; validate product cards and variant handling before any code change.
- `snippets/structured-data.liquid` builds the product breadcrumb item with `product.url | within: collection`. Compare rendered BreadcrumbList URLs with product canonicals before changing it.
- Complementary-product snippets use `product.url`.
- The Booster SEO snippet remains in the theme files but the current layout renders native title/description/canonical and the structured-data snippet.
- `templates/llms.txt.liquid` and `templates/llms-full.txt.liquid` are present; public endpoint delivery and freshness remain unverified.

No theme files, settings, page content or shipping profiles were changed.

## 6. GitHub and acquisition status

- `Online-` repository latest commit: 2026-10-12. No open PRs.
- `data/backlink-opportunities.csv` contains four research-only prospects (PrintCan, GlobalSpec, Canadian Exports and CTI Directory). Retailer eligibility, fees and outbound-link attributes remain unverified.
- The verified acquisition ledger is header-only.
- No outreach, citation creation or live backlink placement is recorded or verified.

Do not count a prospect as an acquisition until its exact public URL, target URL, link context/attribute and verification date are checked.

## 7. Priority actions

1. Reconcile Shopify orders against completed-checkout events and inspect configured GA4/web pixels; investigate why checkout sessions exceed cart-add sessions.
2. Test the current published product-grid links with products that have multiple variants; prepare a minimal preview-only correction if variant selection is lost.
3. Obtain a fresh rendered storefront check for the Saskatoon shipping page and test checkout totals below $100, at $100+, and for Zebra printers.
4. Restore GSC access; refresh collection/page/query performance, Merchant Listings, sitemap and indexing reports.
5. Verify the four backlink prospects for actual retailer eligibility and reader value; only then start outreach and record confirmed live placements separately.

No production changes were made in this review.
