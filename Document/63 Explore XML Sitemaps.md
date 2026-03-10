# Explore XML Sitemaps
https://trailhead.salesforce.com/content/learn/modules/b2c-xml-sitemaps/b2c-xml-explore-sitemaps

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe what sitemaps are.
- List four elements contained in a sitemap.
- List three sitemap attributes.
- Explain how the Salesforce B2C Commerce APIs process a sitemap request.

## What sitemaps are (definition + why they matter)
- **Sitemaps** are XML files that provide search engines (Google, Bing, Baidu, Yahoo) with information about a website so their crawlers can index the site more efficiently.
- A sitemap contains details that help search engines construct links to a site and influence how links are treated in search results.

## Four elements contained in a sitemap (unit list)
A sitemap can include:
- A list of URLs available for indexing
- When a page was last updated
- Page update frequency
- Page relevance

Additional elements mentioned as optional in the unit:
- Page language (**hreflang**, optional)
- Related objects of a page (images, optional)

## What you can improve with sitemaps (practical outcomes)
- **New page awareness**: make bots aware of new pages as you update your storefront.
- **Site crawler coverage**: expose dynamic content that isn’t referenced by static content and may not be discovered by standard crawling.
- **Search results freshness**: tell search engines when to reindex a page to keep results fresh.
- **Site planning**: examine Google reports about page visibility, search traffic, and crawler behavior to improve SEO.

## What’s in a sitemap set (files + splitting rules)
### Index file + sitemap files
- A sitemap set contains:
    - one index file: `sitemap_index.xml`
    - one or more sitemap files: `sitemap_0.xml`, `sitemap_1.xml`, ...
- You register the **index file** with the search engine; its purpose is to point to the actual sitemap files.

### Limits: links and file size
- Each sitemap file can contain from **0 to 50,000 links**.
- The number of sitemap files is determined by:
    - configurable **URLs per sitemap file** (up to 50,000), or
    - a maximum size of **10 MB** per sitemap file,
      whichever condition is reached first.
- Example behavior:
    - 25,000 links with 5,000 per file → 5 sitemap files
    - 25,000 links with 25,000 per file → 1 sitemap file

## Locales and alternate links (hreflang)
- B2C Commerce sitemap files include an entry for each URL asset for supported site locales.
- For each entry, locales can be listed as alternate links (hreflang optional).
- URL assets can include URLs for products, categories, content, folders, controllers, home pages, and product images.

## Three sitemap attributes (and what they map to in Business Manager)
The unit shows how feed attributes relate to Business Manager settings:

1) `sitemap-included-flag` → Sitemap inclusion mode:
- Included in a joint sitemap (asset type included in a joint sitemap file)
- Included in a separate sitemap (create a separate XML file for this asset type)
- Not included

2) `sitemap-changefrequency` → Change frequency:
- Always (default), hourly, or never

3) `sitemap-priority` → Priority:
- Used to determine what pages to crawl first
- `1` is the highest priority

## Included products (filter options and defaults)
- You can specify if you want to include:
    - available products only, or
    - available and orderable products only, or
    - all products
- You can choose to include or exclude **non-searchable products**.
- By default, products must be **online**, **available**, and **searchable** to be included in a sitemap.

## Image view types (including product images in the sitemap)
- You can select the **image view type** to include (per catalog), for example: large, medium, small, swatch.
- When you include a view type, B2C Commerce adds:
    - image location
    - image title
    - alternative text
      for the image to the sitemap.
- Note: product image and video sitemaps have their own schema.

## Multiple sites (when you need multiple sitemaps)
- Whether you need multiple sitemap sets depends on:
    - how you use catalogs, and
    - how you configure hostname aliases.
- If sites share the same product catalog:
    - different locales don’t necessarily require separate sitemaps,
    - but you can create a sitemap set per hostname (domain).
- If sites don’t share the same product catalog:
    - they need different sitemaps and must be registered/generated separately.

## Sitemap topology (how B2C Commerce processes sitemap requests)
B2C Commerce synchronizes Business Manager configuration with what crawlers receive by:
1) Checking whether a URL asset can be added to the generated sitemap:
    - URL is included via sitemap settings
    - URL asset is online
    - For products: `sitemapIncluded` flag is `yes` OR product is assigned to a category with sitemapIncluded flag set to `yes` (or parent categories)
    - For content assets: the content asset sitemapIncluded flag is `yes`
2) Including custom sitemap files using `getCustomSitemapFiles()`
3) Using `SendGoogleSiteMap` to copy the generated sitemap set into the request output stream (so crawlers can access it)

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả sitemap là gì.
- Liệt kê 4 elements có trong sitemap.
- Liệt kê 3 sitemap attributes.
- Giải thích Salesforce B2C Commerce APIs xử lý sitemap request như thế nào.

## Sitemap là gì (định nghĩa + vì sao quan trọng)
- **Sitemaps** là XML files cung cấp thông tin về website cho search engines (Google, Bing, Baidu, Yahoo) để crawlers index site hiệu quả hơn.
- Sitemap chứa các chi tiết giúp search engines xây link và xử lý link trong search results.

## 4 elements trong sitemap (theo unit)
Sitemap có thể gồm:
- Danh sách URLs có thể index
- Trang được cập nhật lần cuối khi nào
- Tần suất cập nhật
- Độ liên quan (relevance)

Các elements optional unit cũng nhắc:
- Ngôn ngữ trang (**hreflang**, optional)
- Related objects (images, optional)

## Lợi ích thực tế của sitemaps
- **New page awareness**: bot biết trang mới khi bạn update storefront.
- **Crawler coverage**: expose dynamic content không được static content trỏ tới.
- **Freshness**: báo khi nào cần reindex để kết quả tìm kiếm mới.
- **Site planning**: xem Google reports về visibility/traffic/crawler behavior để cải thiện SEO.

## Sitemap set gồm gì (files + tách file)
### Index file + sitemap files
- Một sitemap set gồm:
    - `sitemap_index.xml` (index)
    - `sitemap_0.xml`, `sitemap_1.xml`, ...
- Search engine đăng ký **index file**; index file chỉ trỏ tới các sitemap files.

### Giới hạn links và file size
- Mỗi sitemap file chứa **0–50,000 links**.
- Số file phụ thuộc:
    - URLs per sitemap file (tối đa 50,000), hoặc
    - giới hạn **10 MB**/file,
      điều kiện nào đạt trước thì tách.
- Ví dụ:
    - 25,000 links, setting 5,000 → 5 files
    - setting 25,000 → 1 file

## Locales và alternate links (hreflang)
- Sitemap của B2C Commerce có entry cho từng URL asset theo các locales hỗ trợ.
- Mỗi entry có thể liệt kê alternate links theo locale (hreflang optional).
- URL assets có thể gồm: products, categories, content, folders, controllers, home pages, product images.

## 3 sitemap attributes (mapping sang Business Manager)
1) `sitemap-included-flag`:
- Included in a joint sitemap
- Included in a separate sitemap
- Not included

2) `sitemap-changefrequency`:
- Always (default), hourly, never

3) `sitemap-priority`:
- ưu tiên crawl; `1` là cao nhất

## Included products (các lựa chọn + default)
- Có thể chọn include:
    - available only
    - available + orderable only
    - all products
- Có thể include/exclude **non-searchable products**.
- Default: product phải **online**, **available**, **searchable** để vào sitemap.

## Image view types (đưa product images vào sitemap)
- Chọn **image view type** (large/medium/small/swatch theo catalog).
- Khi include, sitemap có image location/title/alt text.
- Note: product image/video sitemaps có schema riêng.

## Multiple sites (khi nào cần nhiều sitemaps)
- Tùy catalogs và hostname aliases.
- Share product catalog: khác locale không nhất thiết cần sitemap riêng, nhưng có thể tạo sitemap set theo hostname/domain.
- Không share product catalog: cần sitemaps riêng, register/generate riêng.

## Sitemap topology (B2C Commerce xử lý request ra sao)
B2C Commerce:
1) Check điều kiện thêm URL asset vào sitemap:
    - URL được include qua settings
    - URL asset online
    - Products: `sitemapIncluded=yes` hoặc thuộc category có sitemapIncluded=yes (hoặc parent)
    - Content assets: sitemapIncluded=yes
2) Include custom sitemap files bằng `getCustomSitemapFiles()`
3) `SendGoogleSiteMap` copy sitemap set vào request output stream để crawlers truy cập