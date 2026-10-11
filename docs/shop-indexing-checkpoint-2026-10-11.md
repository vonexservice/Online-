# Shop indexing checkpoint — 2026-10-11

## Purpose
Record the latest Google Search Console Page indexing report supplied on 2026-10-11 and continue the existing indexing-recovery plan. This is a checkpoint, not a new audit or authorization to make broad site changes.

## Report context
- GSC Page indexing report last updated: 2026-10-03.
- Indexed pages report: approximately 15.8K affected/indexed pages (as shown in the user's report).
- Examples include both `www.shop.vonex.ca` and `shop.vonex.ca`, English and French product/collection URLs, and a collection pagination URL with `?page=9&grid_list=grid-view`.
- The report shows 1–10 of 12 exclusion reasons, so this is not the complete list of reasons.

## Exclusion counts shown
| Reason | Pages | Initial interpretation |
|---|---:|---|
| Excluded by noindex tag | 286,954 | Segment by URL pattern and intended indexability; do not remove noindex globally. |
| Alternate page with proper canonical tag | 42,916 | Often expected; sample canonical targets and duplicate URL patterns. |
| Blocked by robots.txt | 17,666 | Verify whether any priority products/collections are blocked. |
| Page with redirect | 7,004 | Usually expected; inspect chains and internal links to redirects. |
| Not found (404) | 1,488 | Recover only URLs that should exist; otherwise preserve valid removals or redirect to a genuinely relevant replacement. |
| Blocked due to other 4xx issue | 132 | Inspect examples and response cause. |
| Server error (5xx) | 30 | Investigate promptly if recurring or affecting priority URLs. |
| Soft 404 | 7 | Review whether content is empty/thin or incorrectly returning a success response. |
| Duplicate without user-selected canonical | 1 | Low volume; inspect the example. |
| Discovered — currently not indexed | 2,682 | Prioritize valuable products/collections; check links, sitemap inclusion, canonical, content and availability. |

## Indexed appearance warning
- Indexed, though blocked by robots.txt: 8,456 URLs.
- Check representative URL patterns. If these are important product/collection pages, allow crawling; if they are low-value filter/utility URLs, do not indiscriminately unblock them.

## Important comparison caveat
The prior working baseline in the October recovery plan cited approximately 344K “Crawled — currently not indexed,” 8.7K 404s, and 7.4K noindex URLs. These values must not be compared as a simple before/after trend against this report until the exact GSC property, report date, complete reason list, and URL scope are confirmed. The current screenshot has examples on both the www and non-www shop hosts, and the reason table only shows 10 of 12 rows.

## Existing implementation context
- The repository's current strategy is selective indexation: prioritize valuable collections, high-value in-stock products, and useful model/cartridge pages; do not try to index every supplier-imported URL.
- A previous Shopify theme fix was prepared in the unpublished theme “Vonex SEO - Clean Product URLs” to remove Shopify `pr_*`/tracking parameters from product-card links while preserving legitimate `variant=` parameters. Confirm deployment status before treating this fix as live or duplicating the work.
- The current repository is a planning/SEO operating repo. No live Shopify theme, robots.txt, canonical, noindex, or redirect changes were made as part of this checkpoint.

## Next actions
1. In GSC, confirm the exact selected property and export all 12 exclusion reasons, including the missing rows.
2. Inspect a small representative sample from the highest-impact categories: noindex, robots.txt, canonical, discovered-not-indexed, and 404.
3. Separate intended exclusions from accidental exclusions before changing anything.
4. Verify whether the “Vonex SEO - Clean Product URLs” theme fix was published; if published, validate representative product-card links and GSC URL inspection. If not, review and test before publishing.
5. Reconcile current counts with the previous baseline only after property and date scopes match.
6. Validate priority product/collection URLs, sitemap membership, canonical targets, HTTP status, and internal links.
7. Track wanted-URL indexation, clicks/impressions, and conversion value—not total indexed URL count.

## Guardrails
- Do not remove `noindex` sitewide.
- Do not unblock all robots.txt paths indiscriminately.
- Do not mass-create redirects for supplier URLs.
- Do not change canonical or URL patterns without sampling and validating the intended target.
- Do not treat sitemap “0 indexed” fields as the site's total indexed-page count.


## Live verification added on 2026-10-11

### Search Console performance snapshot
For `https://www.shop.vonex.ca/`, the latest 28-day Search Console summary returned:
- 74 clicks (up 12 versus the preceding 28-day period)
- 25,773 impressions (down 11,331)
- CTR approximately 0.287% (up about 0.120 percentage points)
- Average position approximately 12.78 (worse by about 0.88 positions)

Treat this as a short-term signal, not a conclusion about the effect of the recent theme changes. The property `https://shop.vonex.ca/` is listed in the connected account but Google denied data access for that exact URL-prefix property. The accessible `www.shop.vonex.ca` property was used for these inspections.

### URL Inspection samples
1. `https://www.shop.vonex.ca/products/hp-659a-black-laserjet-toner`
   - PASS; submitted and indexed
   - Crawl allowed and fetch successful
   - Google-selected canonical matches the user-declared canonical
   - Google lists a product-card URL with `pr_prod_strat`, `pr_rec_id`, `pr_rec_pid`, `pr_ref_pid`, and `pr_seq` as a referring URL. This proves Google has encountered the tracking-parameter path, but does not by itself prove it remains linked from every current live page.

2. HP 659A tracking-parameter URL
   - `Alternate page with proper canonical tag`
   - Google-selected canonical is the clean `/products/hp-659a-black-laserjet-toner` URL.
   - Last crawl for the parameter URL was 2026-06-09, so this is historical evidence, not proof of a newly generated live link.

3. `https://www.shop.vonex.ca/collections/canon-ink-cartridges-canada?page=9&grid_list=grid-view`
   - PASS; submitted and indexed; crawl allowed and fetch successful
   - User-declared canonical omits `grid_list=grid-view`, but Google-selected canonical includes it.
   - This is a specific pagination/canonical mismatch to investigate. Do not mass-canonicalize or block all pagination based on this single sample; compare other pages and the intended pagination strategy first.

### Live Shopify theme status
A read-only Shopify Admin API query confirmed:
- Current live theme: **Vonex - Link & Pagination Fix 2026-10-07** (`MAIN`).
- **Vonex SEO - Clean Product URLs** remains `UNPUBLISHED`.
- In the live theme's `snippets/product-grid-item.liquid`, `product_link` is assigned directly from `product.url`.
- In the unpublished Clean Product URLs theme, `product_link` uses `product.url | within: collection` and then preserves only a legitimate `variant=` parameter when rebuilding the URL.

Do not publish the unpublished theme as-is without review: using `within: collection` can create collection-scoped product paths, which may introduce additional URL variants. The safe next step is a targeted code review and a minimal patch that emits the preferred clean product URL, preserves legitimate variant selection, and removes tracking parameters without creating collection-scoped duplicates. Test the affected product-card and recommendation paths before deployment.

### Sitemap report caveat
The accessible `www.shop.vonex.ca` property currently shows two sitemap indexes, with 4,364 and 8,535 submitted web URLs respectively; both sitemap reports show zero indexed in their per-content-type summary. This is not the site's total indexed-page count and must not be interpreted as such, especially because GSC separately reports approximately 15.8K indexed pages. The app sitemap was submitted on 2026-10-11 and is pending; the standard sitemap was last downloaded on 2026-10-10.

### Immediate next step
Review the live theme's product-card and recommendation URL-generation code, then prepare the smallest safe correction in a draft/preview theme. Keep the existing live theme intact until the canonical URL behavior is verified on representative product cards, product recommendations, variant links, and collection pagination.
