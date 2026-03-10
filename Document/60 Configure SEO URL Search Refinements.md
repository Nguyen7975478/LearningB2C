# Configure SEO URL Search Refinements
https://trailhead.salesforce.com/content/learn/modules/b2c-seo-urls/b2c-seo-url-search-refinements

## English

## Learning Objectives
(From unit content)
- Understand SEO URL refinement rules and uniqueness constraints.
- Configure refinement behavior and delimiters.
- Localize refinement ordering.
- Create and compare URL Search Refinement Snapshots for bulk change management.

## Where refinement definitions are configured (paths)
The unit provides a quick mapping:

| Refinement type | Business Manager path |
|---|---|
| Category search | site > Merchant Tools > Products and Catalogs > Catalogs > catalog > Category |
| Folder search | site > Merchant Tools > Content > Libraries > library > Edit content > Search Refinement Definitions tab |

## Uniqueness rules and limits (important constraints)
- URLs must be unique; conflicts occur if refinement text conflicts after cleansing/character replacement.
- Limits:
    - Max configurable enabled URL search refinements: **30**
    - Max enabled URL search refinements per category or folder: **5**

## Localize refinement ordering (inheritance + override)
- Brandon configures refinement order at the **root category**, and each locale inherits it.
- Locale can be language-only (e.g., `en`) or language_country (e.g., `en_US`).
- You can override order for specific locales that need different ordering.
  Example in unit:
- Root order: `category-color-price`
- Default locale example output: `<shoes-blue-price>`
- German inherits default order: `<schuhe-blaue-preis>`
- Spanish overrides to `category-price-color`: `<zapatos-precio-azules>`

## Configure refinement rules (Settings tab options)
In Business Manager → Merchant Tools → SEO URL Rules → Settings tab, Brandon can configure:

1) **Position**
- Controls whether refinements appear before or after the category/folder mapping.
- Default is after.
- Example:
    - before: `/blue/shoes/`
    - after: `/shoes/blue/`

2) **Refinements segment delimiter**
- Delimiter between refinement segment and category/folder segment:
    - `/` (default), `_`, `-`

3) **Refinements delimiter**
- Delimiter between multiple refinements:
    - `/`, `_` (default), `-`, `.`, `+`

4) **Refinements value delimiter**
- Delimiter between multiple refinement values:
    - `|` (pipe), `_` (default), `-`, `.`, `+`
- Note: pipe `|` is encoded in the URL path.

5) **Conflicting refinements value delimiter**
- Delimiter to separate indices from value mapping when conflicts exist:
    - (None) (default), `_`, `-`

## URL Search Refinement Snapshots (monitor + bulk change)
The unit describes snapshot tooling to track and bulk-manage refinement mapping changes.

### Configure Job (scheduled snapshots)
1) In Business Manager URL Rules, go to the URL Search Refinements area
2) Click **Configure Job**
3) Enable the job
4) Select date/time and interval (hours/days/weeks/months)
5) Apply → Back

### Create Snapshot (immediate)
- Click **Create Snapshot** to capture a snapshot immediately.

### Compare snapshots (find changes)
Comparison filters described:
- Search refinement file
- Storefront URL Type: Any
- LocaleID: Any
- Refinement: Any
- Mode: Changed (and other modes)
  You need at least two snapshots.

### Compare a specific refinement value
- Enter value in **Refinement Value** (example `blue`) → Find → Compare
- Grid shows only mappings containing that value.

Modes described:
- Equal, Added, Removed, Changed

### Existing Redirects indicator
- A green check icon in Existing Redirects column indicates a previously created redirect that was changed or removed.
- Rows with existing redirects are disabled.

## Tiếng Việt

## Learning Objectives
- Hiểu refinement rules cho SEO URLs và yêu cầu unique URLs.
- Cấu hình refinement behavior và delimiters.
- Localize refinement ordering.
- Tạo/so sánh URL Search Refinement Snapshots để bulk change quản lý.

## Cấu hình refinement definitions ở đâu (paths)
| Refinement | Business Manager path |
|---|---|
| Category search | Merchant Tools > Products and Catalogs > Catalogs > catalog > Category |
| Folder search | Merchant Tools > Content > Libraries > library > Search Refinement Definitions |

## Rules về uniqueness và limits
- URLs phải unique; conflicts xảy ra khi refinement values trùng nhau sau cleansing/character replacement.
- Limits:
    - Max enabled refinements: **30**
    - Max enabled refinements per category/folder: **5**

## Localize refinement ordering (inherit + override)
- Cấu hình ở root category; locales inherit.
- Locale có thể `en` hoặc `en_US`.
- Có thể override order theo locale.
  Ví dụ:
- `category-color-price` → `<shoes-blue-price>`
- German inherit → `<schuhe-blaue-preis>`
- Spanish override `category-price-color` → `<zapatos-precio-azules>`

## Settings tab cho refinements
1) **Position** (before/after category segment)
2) **Refinements segment delimiter** (`/`, `_`, `-`)
3) **Refinements delimiter** (`/`, `_`, `-`, `.`, `+`)
4) **Refinements value delimiter** (`|`, `_`, `-`, `.`, `+`) — `|` được encode
5) **Conflicting refinements value delimiter** (None/`_`/`-`)

## URL Search Refinement Snapshots
### Configure Job
- Configure Job → enable → set schedule → Apply.

### Create Snapshot
- Create ngay snapshot.

### Compare snapshots
- Lọc theo file/URL type/LocaleID/Refinement/Mode; cần ≥2 snapshots.

### Compare theo refinement value
- Refinement Value `blue` → Find → Compare.

Modes: Equal/Added/Removed/Changed.  
Existing Redirects: icon check xanh; row disabled nếu redirect đã tồn tại.