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
