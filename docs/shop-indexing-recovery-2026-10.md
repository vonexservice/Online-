# Shop indexing recovery plan — October 2026

## Objective

Improve useful indexation for shop.vonex.ca while reducing crawl/indexation waste. The objective is not to make Google index every supplier URL.

## Current baseline

- ~4.4K products in catalog/Merchant Center scope
- ~2.2K approved and ~2.2K limited in Merchant Center
- ~3.1K URLs/products in the current sitemap
- ~344K GSC “Crawled — currently not indexed”
- ~8.7K GSC 404 URLs
- ~7.4K GSC noindex URLs

## Phase 1 — classify before changing

Create a representative sample from each GSC/Shopify population:
- indexed
- crawled/not indexed
- discovered/not indexed
- noindex
- 404
- redirect
- duplicate/canonical
- product
- collection
- filter/search URL

Do not mass-edit URLs until the reason for exclusion is understood.

## Phase 2 — protect the index

### Index
- primary collections
- important brand collections
- high-value model/cartridge pages
- strong in-stock products
- useful buying guides/finder pages

### Do not index
- internal search
- low-value filters/facets
- duplicate supplier URLs
- thin/placeholder pages
- cart/checkout/account/utility pages
- discontinued products with no independent value

## Phase 3 — fix URL signals

For each unwanted URL type, choose exactly one appropriate treatment:
- canonicalize duplicate content
- noindex a page that may remain accessible
- redirect a retired/duplicate URL
- return a real 404/410 when the resource is genuinely gone

Do not use robots.txt as the primary index-removal mechanism.

## Phase 4 — sitemap discipline

The sitemap should contain only URLs intended to be indexable.

Weekly checks:
- every sitemap URL returns 200
- every sitemap URL is self-canonical or intentionally canonicalized
- no sitemap URL is noindex
- no sitemap URL is a redirect
- no sitemap URL is a thin/duplicate page
- sitemap product/collection coverage matches the intended index set

## Phase 5 — product SEO

Priority sequence:
1. compatible/remanufactured toner
2. major brands: HP, Brother, Canon, Lexmark, Xerox, Kyocera
3. high-demand cartridge numbers
4. high-value ink
5. other product categories

Product pages should use:
- clear brand/model/colour/cartridge title
- genuine vs compatible distinction
- page yield
- exact compatible printer models
- useful specifications
- unique meta description
- useful image alt text
- links back to the relevant collection/brand

The current compatible/remanufactured toner standardization is already underway; continue by category without changing genuine Return Program products into compatible products.

## Phase 6 — collection architecture

Prioritize:
- Toner Cartridges Canada
- Printer Ink Canada
- HP Toner
- Brother Toner
- Brother Compatible Toner
- Canon Toner
- Lexmark Toner
- Xerox Toner
- Kyocera Toner/Supplies
- other brand/category collections only where inventory and search demand justify them

Evaluate a dedicated Kyocera supplies collection so old Kyocera URLs have a relevant destination instead of a generic toner collection.

## Phase 7 — validation

After deployment:
1. run the build/site audit where applicable
2. inspect representative URLs in GSC
3. submit the sitemap
4. request indexing for a small number of high-priority corrected URLs
5. monitor index coverage weekly
6. compare clicks/impressions for the affected collections/products

## Success criteria

Within each review period, look for:
- fewer accidental 404/redirect/indexation errors
- fewer low-value URLs competing for crawl/indexation
- more priority collection/product URLs indexed
- growth in impressions for model/cartridge searches
- growth in organic clicks and ecommerce conversions

**Do not use total indexed URL count as the primary KPI.**
