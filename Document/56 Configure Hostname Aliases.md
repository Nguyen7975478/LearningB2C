# Configure Hostname Aliases
https://trailhead.salesforce.com/content/learn/modules/b2c-hostname-aliases/b2c-hostname-alias-configure-aliases

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe the hostname alias file structure and syntax.
- List three steps to take to set up and register the DNS and domain names.
- Explain why you must configure a hostname alias for the current instance hostname.

## Meaningful URLs (why aliases help SEO)
- A hostname alias defines alternative names for an existing website URL so external search engines can index short meaningful URLs.
- Without aliases, shoppers might have to use the long technical URL (and may get a 404 if they don’t).
  Example long URL shown:
- `http://www.cloudkicks.com/on/demandware.store/Sites-MY-Site/default/Home-Show`
  Example SEO mapping idea:
- `https://www.cloudkicks.com/homepage`

## Static vs dynamic mappings (what alias files can do)
- Alias files tell B2C Commerce how to process URL redirects:
    - **Static mappings**: handle individual URLs
    - **Dynamic mappings**: handle a set of URLs matching a pattern (example: a set of product pages)
- Dynamic mappings require an identifier (example: product ID) in the legacy URL; otherwise you would need many static mappings.

## DNS and domain setup (3-step list expanded in unit)
The unit lists steps Vijay follows:
1) Purchase a domain.
2) Configure DNS to define a hostname.
3) Obtain a **TLS certificate** (transport layer security) from a certificate authority containing the hostname(s).
   Then:
4) Add hostname to alias file as part of a rule.
5) Include hostname alias settings parameters.

Important operational notes:
- DNS/domain names are strict; each installed certificate requires a unique IP address.
- The first certificate shares the IP with the B2C Commerce instance hostname; additional certificates require additional IPs.
- Ensure DNS is updated with the corresponding hostname IP addresses.

Tip:
- If your host is listed in Business Manager (Merchant Tools > SEO > Aliases) and the site has only one locale, you can create search-friendly home page links without more info to determine locale.

## Embedded CDN consideration
- If using embedded CDN, don’t configure a fixed IP in DNS.
- Use a **CNAME** record when pointing DNS record to embedded CDN.

## What’s in a hostname alias file? (required for production launch)
- The alias file contains:
    - hostnames/domains supported by storefront
    - pipelines triggered for specific URLs
- Alias file is required for production instance launch.
- A production instance can have multiple IP addresses, enabling different storefront content for multiple domains per site or multiple sites per realm.
- Alias file format is **JSON** (`__version`, `settings`, and hostName blocks).
  Example settings snippet shown:
- `{ "__version": "1", "settings": { "http-host": "www.cloudkicks.com", "https-host": "www.cloudkicks.com" } }`

## Instance-specific behavior (not replicated)
- Each instance has its own alias file, and alias files are **not included in data replication**.
- This prevents replication from overwriting production hostname settings with staging settings.

Important warning:
- If you configure hostnames in aliases file, do not configure the deprecated HTTP/HTTPS setting in:
    - Administration > Sites > site > Settings
      Because it’s replicated and can override production hostname.

## Production instance hostname requirement
- Production instance hostname is a fully qualified domain name (FQDN), like `production-realm-<name>.demandware.net`.
- It supports `/s/siteID/` site-path feature so you can browse sites without aliases (example: `/s/CKSite/mens`).
- Developers use this hostname for Business Manager access and development tools (VS Code, WebDAV).
- Shoppers should not use it (not good for SEO/brand marketing).
- Production alias file must include:
    - production instance hostname entry
    - DNS hostname entry
      Example production alias file snippet shown:
- `"www.cloudkicks.com" : [{"pipeline": "Home-Show" }],`
- `"production-realm-cloudkicks.demandware.net" : [{"pipeline": "Home-Show" }],`
- `"cloudkicks.com": [{"host": "www.cloudkicks.com", "path":"/"}]`

## Alias file format (structure)
Structure shown includes:
- `__version` (must be `"1"`)
- `settings` includes:
    - `http-host`, `https-host`
    - optional `job-hostnames` (default/de/en etc.)
    - `site-path`, `site-path-trailing-slash`, and other settings
- hostName entries mapping to arrays of mapping rules:
    - `"hostName1": [ { mappingRule1 }, { mappingRuleN } ]`

Key setting guidance:
- Use hostname in either the `settings` section or the rules section, **not both**.
- `job-hostnames` is used within job context so jobs on staging can generate production-style URLs.

## Configure hostname aliases in Business Manager (walkthrough)
Business Manager path:
- Merchant Tools | Site | SEO > Site URLs > **Aliases**

Example alias JSON shown:
- `cloudkicks.com` maps locale `fr_FR` with `if-site-path: ck-fr`
- `eu.cloudkicks.com` maps locale `fr_FR` with `if-site-path: fr` and then redirects host to `cloudkicks.com`

Steps listed:
1) Open Business Manager.
2) Click App Selector.
3) Go to Merchant Tools | Site | SEO > Site URLs > Aliases.
4) Enter alias JSON.
5) Validate JSON in a tool like **JSONlint**.
6) Paste into editor and Save.

Result example:
- Visiting `eu.cloudkicks.com/fr/` routes to `cloudkicks.com/ck-fr/`.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả cấu trúc/syntax hostname alias file.
- Liệt kê 3 bước để setup/register DNS và domain names.
- Giải thích vì sao phải cấu hình alias cho current instance hostname.

## Vì sao aliases tạo URL “meaningful”
- Hostname alias tạo tên thay thế cho URL hiện có để search engines index URL ngắn, meaningful.
- Không có aliases, shopper phải dùng URL kỹ thuật rất dài và dễ gặp 404.
  Ví dụ URL dài:
- `http://www.cloudkicks.com/on/demandware.store/Sites-MY-Site/default/Home-Show`
  Ví dụ SEO mapping:
- `https://www.cloudkicks.com/homepage`

## Static vs dynamic mappings
- Alias file điều khiển redirects:
    - **Static mappings**: từng URL cụ thể
    - **Dynamic mappings**: pattern cho nhiều URLs (ví dụ product pages)
- Dynamic cần identifier (ví dụ product ID) trong legacy URL.

## DNS và domain setup
Steps Vijay:
1) Purchase domain
2) Configure DNS hostname
3) Lấy **TLS certificate**
   (then) 4) add hostname vào alias file, 5) include settings.
   Notes:
- Mỗi certificate cần IP riêng; certificate đầu share IP với instance hostname; thêm certificate cần thêm IP.
- DNS phải update IP tương ứng.

Tip:
- Nếu host có trong Business Manager Aliases và site chỉ 1 locale, có thể tạo home page links dễ SEO mà không cần thêm thông tin locale.

## Embedded CDN
- Nếu dùng embedded CDN: không dùng fixed IP; dùng **CNAME**.

## Hostname alias file gồm gì (bắt buộc khi launch production)
- Chứa hostnames/domains hỗ trợ + pipelines trigger cho URLs.
- Bắt buộc cho production launch; production có thể có nhiều IP cho nhiều domains/sites.
- Format **JSON**; ví dụ `__version` + `settings`.

## Instance-specific (không replicate)
- Mỗi instance có alias file riêng; không nằm trong data replication.
- Cảnh báo: không dùng deprecated HTTP/HTTPS setting trong Administration > Sites > Settings vì có thể override production.

## Yêu cầu cho production instance hostname
- Production hostname dạng FQDN `production-realm-...demandware.net`, hỗ trợ `/s/siteID/`.
- Dev dùng cho Business Manager/VS Code/WebDAV; shopper không nên dùng vì SEO/brand.
- Production alias file phải có entry cho production instance hostname và DNS hostname.

## Configure trong Business Manager (walkthrough)
- Merchant Tools | Site | SEO > Site URLs > Aliases
- Paste JSON (validate bằng **JSONlint**) rồi Save.
- Ví dụ: `eu.cloudkicks.com/fr/` route sang `cloudkicks.com/ck-fr/`.