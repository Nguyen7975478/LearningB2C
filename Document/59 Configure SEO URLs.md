# Configure SEO URLs
https://trailhead.salesforce.com/content/learn/modules/b2c-seo-urls/b2c-configure-seo-urls

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain the order in which SEO URL configurations move from one instance to another.
- Describe how to create a product or category URL rule.
- List three things you need to consider when configuring SEO URL rules.
- Explain why it’s important to localize URLs.

## Instance flow (where you configure first)
- Brandon configures and tests URL rules in a **sandbox**.
- Then he **exports** them to **staging**.
- His administrator replicates to **production**.
- Practical principle: validate endpoints and conflicts before production.

## Configure general SEO URL settings (Settings tab)
Brandon configures settings to avoid duplicate-content signals and improve readability:

### Lowercase normalization
- Enable **Lower Case** so search engines don’t treat URLs with different capitalization as different pages (duplicate content).
- Note: this does not affect product IDs (`abc123` vs `ABC123`).

### Whitespace replacement
- Configure how whitespace is replaced:
    - default: `%20` (URL encoding)
    - alternatives include plus, underscore, minus, period
- Important warning:
    - Avoid using `-` as whitespace delimiter if `-` is also used as a delimiter inside **SEO Search Refinement URLs**.
    - This can cause duplicate URLs and show up as conflicts on the General tab.

Steps:
1) Business Manager → Merchant Tools | SEO | **URL Rules**
2) Settings tab
3) Select Lower Case
4) Choose whitespace replacement
5) Apply

## Configure rules (Catalog URLs / Content URLs)
- A rule defines the pattern for how endpoints are constructed.
- Brandon uses his catalog structure knowledge to avoid conflicts and keep URLs concise.

### Key design considerations (3+)
1) Category depth:
    - If category depth is more than 2–3, use `category` instead of `category-path` to keep URLs short.
2) Duplicate category names under different parents:
    - Use `category-path` instead of `category` to avoid conflicts (example: `womens > shoes` vs `mens > shoes`).
3) Delimiters for `category-path`:
    - If using `category-path`, use a delimiter other than `/` so product names/IDs aren’t confused as path segments by search engines.
4) Don’t add the product/content asset ID:
    - The ID is required and B2C Commerce always appends it automatically.

### Rule syntax constraints (unit list)
- Mapping can be empty.
- Mapping segments can contain: `a-z`, `A-Z`, `-`, `_`
- Mapping can contain one `/`, with restriction that both segments can’t be empty.

### Create a category URL rule (example rule syntax)
- Category URL Rule field example:
    - `[[ constant, const ], /, [ category-path, [ attribute, ID ], - ]]`
      Key reminder:
- Products display only if assigned to a category.

## Optional rule settings (important toggles)
The unit lists several critical toggles:
- **Enable override with the pageURL product|content attribute**
    - Use Page URL attribute to override endpoints to resolve conflicts or customize specific URLs.
- **Append a trailing slash to category|folder URLs**
    - Prevent search engines from treating slash vs no-slash as duplicates.
- **Generate URL mappings for offline categories|folders**
    - If enabled, you can see possible conflicts; if disabled, you can prevent conflicts from hidden categories/folders.
- **Enable Category|Folder Search Refinement URLs**
    - Put refinement info into the path instead of query string.
- **Use - as the Product ID Separator Instead of /**
    - Adds hyphen between product name and ID instead of `/`.
    - Note: set this to `/` when product SKUs or content IDs contain hyphens and Chrome is used (conflict considerations).

## Attribute value types you can use in rules
The unit lists supported attribute value types for category/product/folder/content asset data:
- Integer
- Set-of-Int
- Enum-of-Int
- String
- Set-of-String
- Enum-of-String

## Localize URLs (why + how)
Brandon localizes URLs so locale appears in the URL in a way that meets country/language customs.

### Locale mapping option: Path (example)
- Set locale mapping to **Path** so locale becomes part of the URL path.
- One value:
    - `http://cloudkicks.com/en/mens`
- Two values (one slash allowed), example `de/DE`:
    - `http://cloudkicks.com/de/DE/mens`

### Other locale mapping options
- **None**: locale doesn’t appear in URL.
- **Hostname**: locale is part of the hostname (configured via alias file hostnames + locale).
- **URL Parameter**: locale appears as a parameter, e.g. `...?lang=en_US` and you map `en` → `default`.

Note: alias file can also be used as an alternative locale mapping strategy.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích thứ tự cấu hình SEO URL di chuyển giữa instances.
- Mô tả cách tạo product/category URL rule.
- Liệt kê 3 điều cần cân nhắc khi cấu hình rules.
- Giải thích vì sao cần localize URLs.

## Flow giữa instances
- Configure/test ở **sandbox** → export sang **staging** → admin replicate sang **production**.
- Nguyên tắc: preview/validate/conflicts trước khi lên production.

## General settings (Settings tab)
### Lower Case
- Bật **Lower Case** để tránh duplicate content do URL khác capitalization.
- Không ảnh hưởng product IDs.

### Whitespace replacement
- Chọn `%20` hoặc delimiter khác.
- Cảnh báo: tránh dùng `-` nếu cũng dùng `-` trong SEO Search Refinement URLs → dễ tạo conflicts.

Steps: Merchant Tools | SEO | URL Rules → Settings → Lower Case + whitespace → Apply.

## Configure rules (Catalog/Content URLs)
### 3+ điểm cần cân nhắc
1) Category depth > 2–3 → dùng `category` để URL ngắn.
2) Trùng category names ở nhánh khác → dùng `category-path`.
3) Dùng delimiter khác `/` cho `category-path`.
4) Không cần add product/content ID vì hệ thống tự thêm.

### Rule syntax constraints
- Mapping có thể empty
- Segments: a-z, A-Z, -, _
- Tối đa 1 `/` và không để cả hai segment rỗng

### Ví dụ category URL rule
- `[[ constant, const ], /, [ category-path, [ attribute, ID ], - ]]`

## Các toggles quan trọng
- Override bằng **pageURL** attribute
- Append trailing slash
- Generate mappings cho offline categories/folders
- Enable Category/Folder Search Refinement URLs
- Dùng `-` làm Product ID separator thay `/` (lưu ý SKU có hyphen)

## Attribute value types dùng trong rules
- Integer, Set-of-Int, Enum-of-Int, String, Set-of-String, Enum-of-String

## Localize URLs
- Locale mapping **Path**: `/en/...` hoặc `de/DE/...` (1 slash).
- Các options: None / Hostname / URL Parameter.
- Có thể dùng aliases file như chiến lược thay thế.