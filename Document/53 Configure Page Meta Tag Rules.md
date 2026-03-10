# Configure Page Meta Tag Rules
https://trailhead.salesforce.com/content/learn/modules/b2c-seo-meta-tags/b2c-seo-meta-tag-configure-page-rules

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List the six Salesforce B2C Commerce meta tag scopes.
- List the three basic meta tag settings.
- Explain the benefits of using static and dynamic text.
- Describe how you preview meta tags.

## Basic concepts (what you configure)
B2C Commerce uses a meta tag rules syntax to generate page meta tag content. Brandon configures three basic settings:
1) **Scope**: what page context is being evaluated?
2) **Rule**: the rule text (static/dynamic expressions)
3) **Assignment**: where the rule applies (for example, which category)

## Scope (contexts you can target)
Scopes listed:
- Home page (**HP**)
- Product detail page (**PDP**)
- Content detail page (**CDP**)
- Product list page (**PLP**)
- Content list page (**CLP**)

### Operators and objects available by scope (table)
**All scopes** can use:
- Script operators: `or`, `and`, `else`, `if-then`, `equals`
- Site context
- Host context
- Print a static constant value
- Original request URL

**List pages** can use:
- Search refinements data
- Search phrase data

**Product list and detail pages** can use:
- Category object data

**Content list and detail pages** can use:
- Folder object data

**Product detail pages** can use:
- Product object data
- Product price data
- Product image URL

**Content detail pages** can use:
- Content object data

## Elements (static + dynamic) and why they matter
This part is “writing code” (If statements + dynamic expressions).

### Static text with a dynamic element
Pattern shown:
- `'Some static text with dynamic part ${expression} here.'`
  Behavior shown:
- If `expression` is empty → static sentence still prints (dynamic part disappears).
- If `expression` evaluates to a value → it’s inserted.

Concrete PDP example:
- `${expression} - Available at Cloud Kicks today! Shop high-end custom sneakers and sports apparel.`
  Where `expression` is the product title (changes per product).

### Static text inside a dynamic expression (robots example)
- `${IF SearchRefinement.color OR SearchRefinement.size THEN Constant('noindex,nofollow,noarchive') ELSE Constant('index,follow,archive')},noydir,noodp`
  If size or color refinement is present:
- `noindex,nofollow,noarchive,noydir,noodp`
  Otherwise:
- `index,follow,archive,noydir,noodp`
  Note explained:
- `noodp` = no open directory project
- `noydir` = no Yahoo directory

### Dynamic text (supported vs unsupported attribute types)
Dynamic text can access object values from:
- product, category, folder, content, site
  But some values are not supported (examples given):
- `Product.onlineFrom` (Date+Time)
- `Product.longDescription` (HTML)
- `Category.image` (Image)

Supported attribute types:
- String, Text, Integer, Number, Boolean
- Set of strings/integers/numbers
- Enum of strings (only if multiple is not marked)
- Enum of integers (only if multiple is not marked)

Not supported:
- HTML, Date, Date+time, Image, Password

Example script shown:
- `Find ${Product.name} in ${Category.displayName} today | ${Site.displayName}`
  Example output shown:
- `Find Happy Racers in Footwear today | Cloud Kicks for the latest running shoe technologies.`

## Configure meta tag rules (Business Manager walkthrough)
1) Open Business Manager.
2) Select site → Merchant Tools → SEO → **Page Meta Tag Rules**.
3) Click a scope tile (example: Product Detail Page) to filter.
4) Click **New** in the Product Detail Page tile.
5) Configure:
    - Name: `ProductDetail01`
    - Scope: `Product Detail Page`
    - Meta Tag ID: `description`
    - Locale: Default
    - Rule:
        - `${Product.pageDescription} | ${Site.displayName} - Available at Cloud Kicks today! Shop high-end custom sneakers and sports apparel.`
        - Note: each rule can contain up to **4000 characters**.
    - Description: `Description meta tag for Cloud Kicks product detail page`
    - Save
6) Assign the meta tag:
    - Return to scope list → find rule → Assign dropdown → Categories → Save
    - Note: children inherit assigned rules; for large catalogs, you may create multiple rules and override at subcategory level.
    - If assignment errors occur, it may be because meta tags were already configured.

## Preview Page Meta Tag Rules (where to look)
The unit lists navigation paths for previewing rules in Business Manager:

- Home page rules for sites:
    - Administration > Sites > Manage Sites > SiteID
- Detail and list page rules for products:
    - site > Merchant Tools > Products and Catalogs > Catalogs > catalogID
- Detail and list page rules for content:
    - site > Merchant Tools > Content > Libraries > libraryID > folderID
- Detail page rules for product:
    - site > Merchant Tools > Products and Catalogs > Products > productID
- Detail page rules for content:
    - site > Merchant Tools > Content > Libraries > libraryID > folder > contentID

Example preview flow (PDP):
1) site > Merchant Tools > Products and Catalogs > Products
2) Search for a product → open product
3) Page Meta Tag Rules tab
4) Select locale: Default
5) Select scope: Product Detail Page
6) Review Page Meta Tag IDs, Rules, Content

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê meta tag scopes của B2C Commerce.
- Liệt kê 3 meta tag settings cơ bản.
- Giải thích lợi ích static vs dynamic text.
- Mô tả cách preview meta tags.

## Basic concepts (3 settings)
B2C Commerce dùng rules syntax để generate meta tags. 3 settings:
1) **Scope**: context của page
2) **Rule**: nội dung rule (static/dynamic)
3) **Assignment**: rule áp cho đâu (ví dụ category nào)

## Scope (các context)
- **HP**, **PDP**, **CDP**, **PLP**, **CLP**

### Operators/objects theo scope (bảng)
**All**: `or/and/else/if-then/equals`, site context, host context, static constant, original request URL  
**List pages**: search refinements, search phrase  
**Product list/detail**: category object data  
**Content list/detail**: folder object data  
**PDP**: product object + price + image URL  
**CDP**: content object data

## Elements: static + dynamic (và vì sao quan trọng)
### Static + dynamic element
- `'Some static text ... ${expression} ...'`
- `expression` trống thì chỉ còn static text; có giá trị thì được chèn vào.
  Ví dụ PDP:
- `${expression} - Available at Cloud Kicks today! ...` (expression = product title)

### Static text trong dynamic expression (robots)
- `${IF SearchRefinement.color OR SearchRefinement.size THEN Constant('noindex,nofollow,noarchive') ELSE Constant('index,follow,archive')},noydir,noodp`
- Có refinement → noindex...
- Không có → index...
- `noodp`/`noydir` là chỉ thị robots.

### Dynamic text: supported/unsupported types
- Truy cập objects: product/category/folder/content/site.
- Không support: HTML/Date/Date+time/Image/Password.
- Supported: String/Text/Integer/Number/Boolean, sets, enum (single).

Ví dụ script:
- `Find ${Product.name} in ${Category.displayName} today | ${Site.displayName}`

## Configure rules trong Business Manager (walkthrough)
- Merchant Tools → SEO → Page Meta Tag Rules → chọn scope tile → New
- Tạo rule:
    - Name `ProductDetail01`, Meta Tag ID `description`, Locale Default
    - Rule `${Product.pageDescription} | ${Site.displayName} - ...`
    - Mỗi rule tối đa **4000 chars**
- Assign: Assign dropdown → Categories → Save
- Child categories inherit; có thể override ở subcategory level.

## Preview rules (đường dẫn)
- Site rules: Administration > Sites > Manage Sites > SiteID
- Product catalog rules: Merchant Tools > Products and Catalogs > Catalogs > catalogID
- Content library rules: Merchant Tools > Content > Libraries > libraryID > folderID
- PDP rules: Merchant Tools > Products and Catalogs > Products > productID
- CDP rules: Merchant Tools > Content > Libraries > ... > contentID

Ví dụ preview PDP:
- Products → mở product → Page Meta Tag Rules tab → chọn locale/scope → xem IDs/Rules/Content.