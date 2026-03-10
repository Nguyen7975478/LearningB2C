# Configure URL Redirects
https://trailhead.salesforce.com/content/learn/modules/b2c-seo-urls/b2c-seo-url-configure-url-redirects

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain when to use URL redirects.
- List the choices you have to redirect from source to target URLs.
- Explain when to use static or dynamic mappings.
- Explain sources and targets within URL Redirect mappings.
- Describe when B2C Commerce automatically processes redirects.

## When to use redirects (two main scenarios)
Brandon needs redirects in two situations:
1) **Migration / acquisition**: redirect legacy platform URLs to new B2C Commerce URLs to preserve SEO value.
2) **Change within B2C Commerce**: rename categories or change URL rules; redirect old B2C Commerce URLs to new ones to avoid broken links and ranking loss.

## Source URL → feature choice (unit table)
| Source URL | Mapping feature |
|---|---|
| Salesforce B2C Commerce | URL Redirect module, **URL archive** (automatic), **search refinement redirects** (automatic) |
| Legacy platform (not B2C Commerce) | Hostname aliases + static mappings + dynamic mappings |

## Static vs dynamic mappings (how to choose)
- **Static mappings**:
    - Best for unique or unusual pages (often content pages).
- **Dynamic mappings**:
    - Best for URLs that follow patterns (product/category pages).
    - Can extract content from wildcards in the source URL and insert it into the destination URL template.
- Quotas/limits mentioned:
    - **25,000** URL redirects
    - Around **18K static** and **18K dynamic** mappings per site (as described in unit)

## URL Redirects module (B2C → B2C redirects) — example walkthrough
Brandon redirects an old category landing page to a renamed category.

Steps:
1) Business Manager → Merchant Tools | SEO | **URL Rules Redirects**
2) Click **New**
3) Configure mapping:
    - Source Type: Category
    - Category ID: `sports-equipment`
    - Destination Type: Category
    - Category ID: `ck-sports-equipment`
    - Copy Source URL Parameters: Default (No)
    - Redirect Type: Permanent (**301**)
    - Enabled: select
      Result:
- Incoming source URL like `www.cloudkicks.com/sports-equipment` is redirected.

Best practice emphasized:
- Use IDs (catalog/product/category IDs) and let B2C Commerce generate the redirect URLs.
- Avoid hardcoding target as raw URL string because mappings can change.

## Bulk redirects after a comparison (Search Refinement Redirects)
- After comparing URL Search Refinement Snapshots, you can create redirects for:
    - value changes (example `Blue` → `blue`)
    - removal
      Steps described:
1) Merchant Tools | SEO | URL Rules
2) URL Search Refinements tab
3) Enter refinement value (example `blue`) → Compare
4) Select changed items
5) Click **Create Redirects**
6) OK
- Redirects appear in Search Refinement Redirects section.

## URL Archive (automatic redirects for changed category/folder mappings)
- URL archive automatically redirects outdated category and folder URL mappings.
- Enabled on staging and production.
- B2C Commerce saves category/folder mappings when they become outdated and can redirect to new mappings.

Manage archive entries:
1) Use a staging instance (archive tab appears only on staging)
2) Merchant Tools | SEO | URL Rules
3) URL Archive tab
4) View or delete outdated mappings

## Dynamic mappings (legacy → B2C pattern redirects)
- Dynamic mapping rules redirect URLs from a legacy site to B2C Commerce using patterns.
- Not allowed use cases:
    - You can’t map from one B2C Commerce URL to another using dynamic mappings.
    - You can’t create redirects for static resources like images.

## Mapping rule syntax (pattern + template + options)
- Each rule = URL pattern + (optional) options + B2C Commerce URL template, separated by whitespace.
- Wildcards:
    - `*` and `**` match text between slashes (not query string)
- You can reference wildcard matches by position using `{0}`, `{1}`, etc.
  Example table structure in unit:
- Pattern: `/index.asp?ID=576416&Cat=hockey.html`
- Option: `ie=iso-8859-1`
- Template: `/sports-equipment/576416,default,pd.html?cgid=Hockey`

## When redirects are automatically processed
- **URL archive**: when category/folder mappings change.
- **Search refinement redirects**: when refinement values change/are removed (created via compare + Create Redirects).

## Tiếng Việt

## Learning Objectives
- Giải thích khi nào dùng URL redirects.
- Liệt kê các lựa chọn để redirect source → target.
- Giải thích khi nào dùng static vs dynamic mappings.
- Giải thích sources/targets trong URL Redirect mappings.
- Mô tả khi nào B2C Commerce tự xử lý redirects.

## Khi nào cần redirects
1) Migration/acquisition: redirect legacy URLs → B2C URLs để giữ SEO value.
2) Thay đổi trong B2C: rename categories/changing URL rules → redirect URL cũ → URL mới.

## Source URL → feature
- B2C → dùng URL Redirect module, **URL archive**, **search refinement redirects**
- Legacy → hostname aliases + static/dynamic mappings

## Static vs dynamic mappings
- Static: trang lẻ/đặc biệt (content pages)
- Dynamic: theo pattern (product/category), dùng wildcard để map hàng loạt
- Limits: 25,000 redirects; ~18K static và ~18K dynamic mappings/site.

## URL Rules Redirects (B2C → B2C) ví dụ
- URL Rules Redirects → New:
    - Source Type Category + ID
    - Destination Type Category + ID
    - Permanent 301 + Enabled
      Best practice: dùng IDs để hệ thống generate URL; tránh hardcode URL.

## Bulk redirects (search refinement)
- URL Search Refinements tab → Compare → chọn changed items → Create Redirects → OK.

## URL Archive (automatic)
- Tự redirect category/folder mappings cũ khi mappings đổi.
- Có trên staging và production; tab chỉ hiện ở staging để view/delete.

## Dynamic mappings (legacy → B2C)
- Dùng pattern + template + options; wildcard `{0}`...
- Không dùng để map B2C → B2C hoặc static resources (images).

## Redirects tự động
- URL archive khi category/folder mapping thay đổi.
- Search refinement redirects khi refinement values đổi/remove (tạo từ compare).