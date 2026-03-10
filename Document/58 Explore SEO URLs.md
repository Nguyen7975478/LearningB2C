
# Explore SEO URLs
https://trailhead.salesforce.com/content/learn/modules/b2c-seo-urls/b2c-explore-seo-urls

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain why SEO URLs are important.
- List three SEO URL best practices.
- Explain why you retain the URL text that follows the hostname.
- List four steps in the SEO URL configuration process.

## Why SEO URLs (business + shopper impact)
- SEO URLs improve:
    - shopper experience (readable, predictable URLs)
    - external search engine rankings
    - linking functionality (clean links shared in email/social)
    - site traffic
- Brandon already configured **hostname aliases** (so shoppers and search engines land on the right host). Now he wants:
    - custom/default/page-specific SEO URLs (the “endpoint” part after the host).

## The problem SEO URLs solve (encoded characters and readability)
- Some category names contain characters that must be encoded in URLs (example: ampersand `&` becomes `%26`).
- Example before cleanup (encoded `&` and blank replacement):
    - `.../on-the-go-%26-gear/hiking/`
- Brandon wants readable output (treat `&` like a hyphen) using character replacement:
    - Mapping rule example: `&` → `-`
- Result after replacement:
    - `.../on-the-go-gear/hiking/`

## Pattern and structure (what B2C Commerce generates)
- SEO URLs are a shortened/condensed form of the standard B2C Commerce URL.
- Max storefront URL length is **1800 characters**.
    - If longer, B2C Commerce shortens but keeps URLs valid/unique by retaining required product/content IDs in product/content-specific URLs.
- URL structure differs by host type:

| Host type | URL pattern | Example idea |
|---|---|---|
| Non-`.demandware.net` host | `<hostname>/<endpoint>` | `cloudkicks.com/mens` |
| `.demandware.net` or localhost | `<hostname>.demandware.net/s/<site-name>/<endpoint>` | `...demandware.net/s/cloudkicks/men` |

### Instance differences (why sandbox/staging URLs look “internal”)
- Production uses brand hostnames (aliases) like `www.cloudkicks.com/...`
- Sandbox/staging/dev typically show `*.demandware.net/s/<site-name>/...` unless aliases are configured.
- Key point: the **endpoint** (the part after host) is identical across instances, so teams can validate endpoints before production.

## Rule patterns (what a “rule” is)
- SEO URL rules define the endpoint pattern.
- If you don’t configure a pattern, B2C Commerce uses defaults.
- Example pattern shown:
    - `[ category-path, [ attribute, displayName ], - ]`
    - Meaning: use category path + display name, with `-` as delimiter for blanks.

## SEO URL best practices (3)
The unit’s best-practice theme is:
1) Use clearly named URLs that aren’t too long (readable endpoints).
2) Remove/replace characters that must be encoded (avoid `%26`, etc.).
3) Normalize/clean endpoints (remove extra spaces/characters/words; handle leading/trailing blanks; handle umlauts).

## SEO URL configuration process (4 steps, unit flow)
At a high level, Brandon follows this process:
1) Ensure SEO URLs are enabled (storefront URL preferences).
2) Configure hostname aliases (required so modified URLs show correctly on the storefront).
3) If multiple locales: configure locale mapping (locale from hostname alias, URL path, or URL parameter).
4) Configure URL rules + character replacements + search refinement URL handling; then review status and handle conflicts.

## Redirecting older URLs (migration + change management)
The unit introduces two redirect-related capabilities:
- **Static and dynamic mapping**: redirect old mappings to new mappings (legacy platform → B2C Commerce).
- **URL archive functionality**: automatically redirect old mappings to new mappings when mappings change on a live site (especially when configuration changes change endpoints).
- Search refinement URL redirects can redirect outdated search refinement URL mappings.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích vì sao SEO URLs quan trọng.
- Liệt kê 3 best practices cho SEO URLs.
- Giải thích vì sao giữ lại URL text sau hostname.
- Liệt kê 4 bước trong quy trình cấu hình SEO URL.

## Vì sao SEO URLs quan trọng
- SEO URLs giúp:
    - trải nghiệm shopper (URL dễ đọc/dễ hiểu)
    - tăng ranking trên external search engines
    - link/share dễ hơn
    - tăng traffic
- Brandon đã làm **hostname aliases** (đúng host). Bây giờ anh cần:
    - custom/default/page-specific URLs (endpoint sau hostname).

## Vấn đề SEO URLs giải quyết (ký tự encode)
- Category names có ký tự phải encode, ví dụ `&` → `%26`.
- URL trước cleanup: `.../on-the-go-%26-gear/hiking/`
- Brandon muốn `&` hiển thị như `-`:
    - mapping `&` → `-`
- Kết quả: `.../on-the-go-gear/hiking/`

## Pattern/structure (B2C Commerce generate thế nào)
- SEO URL là dạng rút gọn của URL chuẩn.
- Max storefront URL **1800 chars**; dài hơn sẽ được rút gọn nhưng vẫn unique bằng cách giữ product/content IDs bắt buộc.
- 2 cấu trúc URL:

| Host type | Pattern | Ý nghĩa |
|---|---|---|
| Non-`.demandware.net` | `<hostname>/<endpoint>` | `cloudkicks.com/mens` |
| `.demandware.net`/localhost | `<hostname>.demandware.net/s/<site-name>/<endpoint>` | `.../s/cloudkicks/men` |

### Khác nhau giữa instances
- Production dùng brand hostnames.
- Sandbox/staging/dev thường `*.demandware.net/s/<site-name>/...` nếu chưa cấu hình aliases.
- **Endpoint** giống nhau giữa instances → dễ test trước production.

## Rule patterns (rule là gì)
- SEO URL rules định nghĩa pattern cho endpoint.
- Không cấu hình thì dùng default.
- Ví dụ pattern:
    - `[ category-path, [ attribute, displayName ], - ]`

## SEO URL best practices (3)
1) URL rõ ràng, không quá dài.
2) Remove/replace ký tự cần encode (tránh `%26`…).
3) Normalize/clean endpoints: xử lý spaces, leading/trailing blanks, umlauts.

## Quy trình cấu hình (4 bước)
1) Bật SEO URLs.
2) Cấu hình hostname aliases.
3) Nếu multi-locale: cấu hình locale mapping (hostname alias / path / parameter).
4) Cấu hình URL rules + character replacements + search refinement URLs, rồi xem status và xử lý conflicts.

## Redirect URLs cũ (migration + thay đổi)
- **Static/dynamic mapping**: redirect từ legacy platform sang B2C Commerce.
- **URL archive**: tự redirect mapping cũ sang mapping mới khi mappings thay đổi trên live site.
- Search refinement redirects: redirect các refinement URL mappings cũ.