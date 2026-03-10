# Notify Search Engines About Your Sitemaps
https://trailhead.salesforce.com/content/learn/modules/b2c-xml-sitemaps/b2c-xml-sitemaps-notify-search-engines

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain how to submit sitemaps to Google.
- Explain how to add the `google-site-verification` meta tag for Google site verification.
- List the development elements that handle sitemaps in a B2C Commerce storefront application.
- Find the template you need for Google site verification within the storefront.

## Why Google + protocol compatibility
- Google has almost half the market share of all search engines.
- Most search engines (including Google) use the **sitemap.org protocol** (Sitemap Protocol 0.9).
- Once Brandon generates sitemaps for Google, he can also register and use them with other search engines (Yahoo! and Bing).

## How to submit a sitemap to Google (3 methods)
After creating a sitemap, you can submit it by:
1) Adding it to the search console (manual submission)
2) Adding it to the `robots.txt` file
3) Using Google ping functionality
- Google checks for updates regularly, so you typically submit once.

## What Google Search Console helps you do (unit list)
- Confirm Google can find and crawl your site.
- Fix indexing problems and request re-indexing.
- View Google Search traffic data (appearance frequency, queries, click-through, etc.).
- Receive alerts when Google encounters indexing, spam, or other issues.
- Show which sites link to your website.
- Troubleshoot AMP, mobile usability, and other search features.

## Sitemap output recap (what gets indexed)
- Each generation job creates:
    - one index file `sitemap_index.xml`
    - one or more sitemap files `sitemap_0.xml`, `sitemap_1.xml`, ...
- The **index file** is what you register; its purpose is to point to sitemap files.
- In B2C Commerce sitemaps:
    - variations, base products, product sets, and unsearchable products are indexed
    - offline and unassigned products are not included

## Where the live sitemap index must be (production) + how to view it
- You can configure/import sitemaps on any instance type, but your **live** sitemap must be on the **production** instance for Google to index the site.
- To view the index file:
    - `http://<hostname>/sitemap_index.xml`
      Troubleshooting note:
- Use a hostname configured in **hostname aliases** (include the full hostname, not the storefront name).

## Verify site ownership (google-site-verification)
- Google requires verifying site ownership by either:
    - adding a specific meta tag, or
    - deploying a file with a specific name to the web server’s root directory.
- Google’s meta-tag name for verification is `google-site-verification`.
- In SFRA, the `htmlhead.isml` template uses this name for Google site verification.
- Unit recommendation: create a **custom site preference** for the Google tag and include the tag in the storefront application.

## Development elements that handle sitemaps (SFRA plugin_sitemap)
- SFRA includes `plugin_sitemap`, which implements sitemap functionality:
    - serves requests for search provider (Google, Yahoo) XML sitemaps
    - reads a given sitemap and copies it into the request output stream
    - renders an `http_200` template on success or `http_404` on failure
- The plugin calls the Script API `SiteMap` class to generate/manage the sitemap.
- It uses the `SendGoogleSiteMap` pipelet to read the sitemap and copy it into the request output stream.
- The pipelet directly serves site requests from crawlers (including Google).

## Recommendation reminder (robots.txt)
- The unit recommends placing the location of your `sitemap_index.xml` file in your `robots.txt` file.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích cách submit sitemaps cho Google.
- Giải thích cách add meta tag `google-site-verification`.
- Liệt kê các development elements xử lý sitemaps trong storefront app.
- Tìm template dùng cho Google site verification trong storefront.

## Vì sao Google + protocol
- Google chiếm gần một nửa thị phần.
- Đa số search engines dùng **sitemap.org protocol** (Sitemap Protocol 0.9).
- Generate cho Google xong có thể dùng cho Yahoo!/Bing.

## 3 cách submit sitemap cho Google
1) Submit qua Search Console
2) Thêm vào `robots.txt`
3) Dùng Google ping
- Google tự kiểm tra updates nên thường submit 1 lần.

## Google Search Console giúp gì (theo unit)
- Xác nhận crawl/index.
- Fix indexing và request re-index.
- Xem search traffic (impressions/queries/CTR…).
- Nhận alerts (indexing/spam/issues).
- Xem backlinks.
- Troubleshoot AMP/mobile usability…

## Sitemap output (nhắc lại include/exclude)
- Job tạo `sitemap_index.xml` + các `sitemap_0.xml`, `sitemap_1.xml`…
- Register **index file**.
- Bao gồm: variations, base products, product sets, unsearchable products.
- Không bao gồm: offline và unassigned products.

## Live sitemap phải ở production + cách xem
- Có thể cấu hình ở nhiều instance, nhưng **live** sitemap phải nằm trên **production** để Google index.
- Xem tại: `http://<hostname>/sitemap_index.xml`
- Troubleshooting: dùng hostname đã cấu hình trong **hostname aliases** (full hostname, không dùng storefront name).

## Verify ownership (google-site-verification)
- Google verify bằng meta tag hoặc file ở web server root.
- Meta tag name: `google-site-verification`.
- SFRA template `htmlhead.isml` dùng name này.
- Khuyến nghị: tạo **custom site preference** cho tag và include vào storefront app.

## Development elements xử lý sitemaps (SFRA plugin_sitemap)
- SFRA có `plugin_sitemap`:
    - serve XML sitemaps (Google/Yahoo)
    - stream sitemap vào response output stream
    - success → `http_200`, fail → `http_404`
- Plugin gọi Script API `SiteMap` class.
- Dùng `SendGoogleSiteMap` pipelet để đọc sitemap và stream cho crawler.

## Reminder
- Nên đặt location của `sitemap_index.xml` trong `robots.txt`.