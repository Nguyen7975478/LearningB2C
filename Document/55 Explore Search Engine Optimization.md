# Explore Search Engine Optimization
https://trailhead.salesforce.com/content/learn/modules/b2c-hostname-aliases/b2c-hostname-alias-explore-seo

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List five Salesforce B2C Commerce SEO features.
- Explain the benefits of using hostname aliases.
- Define three common hostname alias terms.
- List three tasks you need to accomplish to implement B2C Commerce meta tags.

## SEO and B2C Commerce (what Brandon is optimizing)
- Brandon wants to increase non-paid search results for Cloud Kicks.
- Key SEO note: Google can rank sites lower when URLs are super-long with multiple directory layers and parameters, so short meaningful URLs are preferred.

## Five B2C Commerce SEO features (unit list)
1) **Hostname aliases**
- Configure all variants of a website’s name to lead to the website.
2) **SEO URLs**
- Short, searchable, human-readable URLs.
3) **XML sitemaps**
- Tell search engines what’s on the site.
4) **SEO meta tags**
- Describe page content to improve SEO ranking and click-through.
5) **Redirects and mappings**
- Redirect shoppers to the right place (301/302/404 strategy).

## What you do to design/configure/deploy/maintain (table summary)
### Hostnames
- Create short meaningful URLs by assigning short aliases to long hostnames.
- Define device/request/language mappings to domain + locale.

### SEO URLs
- Identify inbound links and update them.
- Create custom default URLs, page-specific URLs, and optionally page meta tags.
- Remove duplicate content (avoid multiple URLs for same content).
- Use Business Manager URL Rules module to change URLs and add SEO-improving info.

### XML sitemaps
- Register site and submit sitemaps to search engines.
- Use Business Manager to generate sitemaps for freshness/completeness.

### Redirects and mappings
- Create permanent **301 redirects** for obsolete URLs to new URLs.
- Design storefront-specific **404** pages with alternative paths.
- Use static or dynamic mapping rules for legacy URLs.
- Create temporary **302** redirects for merchandising scenarios like out-of-stock.
- Configure 301 HTTP redirects from legacy URLs.

### Meta tags (3 tasks to implement)
The unit’s meta tag task list includes:
- Design meta tags.
- Create body text, intra-site links, anchor text, and image `<alt>` tags.
- Use Business Manager to create/manage page meta tags for product/content detail and list pages.
- Add titles/descriptions/open graph attributes for new categories/products.
- Build robots.txt using external tooling to exclude parts of the site.
- Validate HTML to ensure there are no errors blocking indexing.

## Hostname aliases (what they are + why they matter)
- Hostname aliases generate **301 redirects** for host-only URLs and can redirect to locale- or device-specific sites.
- Aliases can redirect to other aliases.
- The alias file defines:
    - which hostnames/domains B2C Commerce supports
    - which **pipelines** or **controllers** run for a specific URL
- Pipelines predate controllers; both manage flow and actions in the storefront application.
- Host-only URLs can open pipelines (example: `www.your.host.com` opens `Home-Show`).

## Key hostname alias terms (3)
- **Entered URL**: URL typed by shopper.
- **Host name**: host portion of URL (example `www.cloudkicks.com`).
- **Site path**: optional URL segment appended to host name used to distinguish multiple sites on same hostname:
    - `http://www.cloudkicks.com/uk`
    - `http://www.cloudkicks.com/us`
    - Can contain multiple slashes.
- **Locale** (also defined): optional locale identifier in mapping rules; if no mapping rule matches, site default locale is used.
- **Path**: path appended after locale/site path/host (example `/womens/accessories/promopage.html`).

## Scenarios (what aliases enable)
- One domain for multiple sites (example: `/us`, `/uk`, `/de`).
- Keep old domains active during migration to preserve traffic.
- Handle common misspellings.
- Map alias to a locale (example `.de` triggers de_DE).
- Map alias to locale-specific landing page.
- Map alias to device-specific pages (example `m.cloudkicks.com`).
  Tip: best practice is responsive design for device-specific pages.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê 5 SEO features của B2C Commerce.
- Giải thích lợi ích của hostname aliases.
- Định nghĩa 3 thuật ngữ phổ biến của hostname aliases.
- Liệt kê 3 tasks cần làm để implement meta tags.

## SEO và B2C Commerce
- Brandon muốn tăng non-paid search results cho Cloud Kicks.
- Google có thể giảm rank nếu URL quá dài, nhiều layers/parameters → cần URL ngắn, meaningful.

## 5 SEO features (unit list)
1) **Hostname aliases**
2) **SEO URLs**
3) **XML sitemaps**
4) **SEO meta tags**
5) **Redirects and mappings**

## Bảng công việc theo feature (tóm tắt)
- Hostnames: alias ngắn cho hostname dài; map device/request/language → domain/locale.
- SEO URLs: update inbound links; tạo default/page-specific URLs; remove duplicate content; dùng URL Rules.
- XML sitemaps: submit cho search engines; generate trong Business Manager.
- Redirects/mappings: 301/302/404 + static/dynamic mapping cho legacy URLs.
- Meta tags: design meta tags; body text/links/anchor text/alt tags; quản lý page meta tags trong Business Manager; titles/descriptions/open graph; robots.txt; validate HTML.

## Hostname aliases là gì
- Tạo **301 redirects** cho host-only URLs; redirect theo locale/device; redirect sang aliases khác.
- Alias file định nghĩa hostnames/domains được hỗ trợ và pipeline/controller chạy cho URL.
- Host-only URLs có thể mở pipeline (ví dụ `Home-Show`).

## Thuật ngữ hostname aliases
- Entered URL, Host name, Site path (phân biệt sites trên cùng hostname), Locale (mapping rule), Path.

## Scenarios
- 1 domain cho nhiều sites; giữ domain cũ khi migrate; xử lý misspellings; map theo locale/landing page/device pages; best practice dùng responsive design.