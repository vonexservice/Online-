# Vonex SEO Operating Model

## Two-domain strategy

### Domain A: www.vonex.ca

Primary intent: local and commercial B2B services.

Topic clusters:
- printer repair
- copier repair
- copier service
- managed print
- copier/printer leasing
- office equipment
- printer sales
- authorized brand support
- Saskatchewan service areas

Geographic focus:
- Saskatoon
- Regina
- nearby Saskatchewan communities where service is actually offered

Do not expand location pages simply to create URLs. Each location page must have a distinct service/search purpose and accurate local information.

### Domain B: shop.vonex.ca

Primary intent: ecommerce/product research and transactions.

Topic clusters:
- toner
- ink
- printer supplies
- Brother
- HP
- Canon
- Lexmark
- Xerox
- Kyocera
- Zebra
- model/part-number searches
- compatible vs OEM
- Canadian shipping/product availability

## 1. Indexing-first strategy

The shop has a large supplier-driven catalog. The goal is controlled indexation, not indexing every product URL.

### Tier A — index and actively improve
- primary collections with meaningful demand
- brand collections
- important model/cartridge landing pages
- high-value in-stock products with unique content
- useful evergreen buying guides and cartridge-finder pages

### Tier B — index selectively

Products should be indexed when they have:
- a real search demand or strong long-tail value
- a clear product identity
- unique/adequate title and description
- verified compatibility or specifications
- useful image/alt text
- availability or a sensible replacement path
- a canonical URL that is not duplicated elsewhere

### Tier C — keep out of the index

Normally noindex/canonicalize/redirect:
- internal search pages
- filter/facet combinations without standalone search demand
- duplicate supplier/import URLs
- thin placeholder pages
- cart, checkout, account and utility URLs
- expired/discontinued products with no independent search value
- duplicate variants that do not need separate search landing pages

### Important distinction

Do not confuse crawl control, index eligibility, and index selection. A canonical tag does not guarantee indexation. A noindex directive is different from robots.txt blocking. For URLs already known to Google, use the appropriate canonical/noindex/redirect strategy rather than assuming robots.txt will remove them.

## 2. Current indexing baseline

Use this as the October 2026 working baseline and refresh it during each weekly review:
- ~4.4K products in the current catalog/Merchant Center scope
- ~2.2K approved and ~2.2K limited in Merchant Center
- ~3.1K URLs/products represented in the current sitemap
- GSC: roughly 344K Crawled — currently not indexed
- GSC: roughly 8.7K 404 URLs
- GSC: roughly 7.4K noindex URLs

These numbers are signals, not targets. The 344K figure especially should be segmented before any attempt to “fix” it, because a large ecommerce site can contain many low-value discovered URLs that should never become indexable.

## 3. URL/indexing audit

Every weekly audit should classify URL populations into:
1. wanted + indexable
2. wanted + currently not indexed
3. duplicate/canonicalized
4. intentional noindex
5. redirect
6. real 404
7. accidental/unknown URL

For each class, measure count, trend and representative examples.

### P0 checks
- sitemap contains only URLs we want indexed
- canonical points to the preferred URL
- noindex is used only intentionally
- internal links do not point to noindex/redirect/404 URLs
- old URLs redirect once to the closest relevant replacement
- product URLs do not create uncontrolled parameter/facet variants
- primary domain is consistent
- important pages return 200 and contain crawlable content
- important products have unique SEO title/meta/description content

## 4. Product SEO program

Product titles follow the agreed structure:

[Brand] [Model] [Colour] [Toner/Ink Cartridge] ([Genuine/Compatible]) – [Yield]

Rules:
- no store name in the product title
- clearly distinguish Genuine/OEM, Compatible and Remanufactured Compatible
- do not label genuine Return Program products as compatible
- use real printer models in “Will it work with my device?”
- do not invent compatibility
- do not repeat generic shipping copy that the Shopify theme already provides

The current compatible/remanufactured toner work is being completed brand/category by brand/category. Lexmark-compliant / Static Control compatible products identified in the catalog have been standardized; genuine Lexmark Return Program products are excluded.

## 5. Collection architecture

Broad commercial intent should land on strong collections rather than thousands of thin product URLs.

Priority architecture:
- Toner Cartridges Canada
- Printer Ink Canada
- brand collections
- compatible toner collections
- model/cartridge-number product pages

Where a brand has meaningful inventory and search demand, give it a real collection/landing page. Do not create a collection solely for SEO if there is not enough useful inventory/content.

Known opportunity: a dedicated Kyocera toner/supplies collection should be evaluated because the shop currently lacks a strong Kyocera supplies landing page while Kyocera is strategically important to Vonex.

## 6. Internal linking

Use a deliberate hierarchy:

Home → Collections → Brand → Model/Cartridge → Product

Also:
- product → relevant brand collection
- product → relevant toner/ink collection
- compatible product → compatible collection
- buying guide → collection/product
- service site → shop collection when the user is ready to buy supplies
- shop → vonex.ca service pages when the user needs local repair/service

Avoid sitewide keyword-stuffed links and links to noindex/redirect pages.

## 7. Content and AEO/GEO

Answer real buying questions:
- Which toner fits my printer?
- Is this genuine or compatible?
- What is the page yield?
- What printers use this cartridge?
- What is the difference between OEM and compatible toner?
- How do I find my cartridge number?

Use visible answers on the page. Structured data should describe content that is actually visible.

## 8. Competitor intelligence

For every important competitor:
- domain
- ranking URL
- target keyword
- current position
- search intent
- estimated demand
- referring domains
- page type
- title/H1 structure
- content coverage
- missing information
- product/category/service advantage
- Vonex target URL
- action required

## 9. Opportunity scoring

Score 0–100 using:
- Commercial intent: 25
- Current Vonex position / proximity to page 1: 20
- Search demand: 20
- Competitive difficulty: 15
- Business value: 15
- Content/link feasibility: 5

For ecommerce, add an Indexability Gate before scoring a URL as a ranking opportunity:
- Is this the canonical URL?
- Should this URL exist in search?
- Is the page materially different/useful?
- Is there enough inventory/content to satisfy the query?

## 10. Link strategy

Do not use automated link creation or mass low-quality Google properties.

Preferred authority sources:
- real local/business directories
- manufacturer/dealer references
- supplier/manufacturer profiles
- industry organizations
- chambers and business associations
- local news/community publications
- legitimate partner/customer references
- useful editorial/resource mentions
- genuinely useful Google/YouTube resources

The objective is authority and relevance, not a fixed backlink count.

## 11. Weekly operating cadence

### Monday — Indexing
Review GSC indexing categories, sitemap coverage, 404s, redirects, noindex and representative product/collection URLs.

### Tuesday — Product SEO
Improve a focused batch of high-value products: titles, meta descriptions, compatibility, specifications and internal links.

### Wednesday — Collections
Improve one or more commercial collection/brand pages and their internal-link structure.

### Thursday — Search demand
Use GSC/Semrush/Ahrefs to identify queries close to page 1 and map each to one canonical URL.

### Friday — Authority/content
Create one useful supporting asset or pursue a legitimate relevant mention/citation.

## 12. Definition of done

A URL is not “done” merely because its title was changed.

For priority pages/products, done means:
- correct canonical URL
- correct index/noindex state
- useful crawlable content
- unique title and meta description
- correct H1
- relevant internal links
- no broken/redirected internal links
- appropriate structured data where applicable
- included in sitemap only if intended for indexation
- verified in GSC after deployment when appropriate
