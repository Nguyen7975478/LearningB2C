# Configure Price Books
https://trailhead.salesforce.com/content/learn/modules/b2c-pricebooks-images-content/b2c-configure-price-books

## English

## Learning Objectives
- Explain how Salesforce B2C Commerce determines which price book to use.
- List the permissions required to create, modify, and delete price books.
- Describe how **Read-Only Price Books** help merchants.
- Explain how **site assignment** works with price books.
- Explain why you would use **price tables**.

## What a price book is (core definition)
- A **price book** contains price data for products based on a **currency**.
- You can create price books manually in Business Manager or import price data from an **ERP** or another financial system.
- Prices are “not generally considered product data per se” (they’re managed separately from product definition).
- You must have products defined before creating price books.
- Each product must have a price for quantity **1** in an active price book; **computed prices** are derived from that base.

## How B2C Commerce determines which price book to use (priority rules)
- Multiple price books can be active.
- If two assigned price books overlap in valid periods:
    - The price book with the most recent **Valid From** date wins.
- A price book with a specific active/valid period wins over a continuous price book.

## Operational best practice (performance)
- Maintain a stable set of fixed price books with fixed names.
- Use **merge** or **replace** import mode to update prices quickly as they change.
- Avoid deleting/recreating price books frequently because it slows the system and can affect shopper experience.

## Permissions required
- The unit shows that a merchandiser may be able to view/search price books but cannot create/modify/delete until granted write access and functional permissions:
    - `Manage_PriceBooks` (all price books globally)
    - `Manage_Site_PriceBooks`
- Note: if permissions are mixed across roles for a module, the higher-level access is granted.

## Site assignment (how price books become active on a site)
- Price books are defined for the organization, then assigned to one or more sites to be active for those sites.
- A site can have one or more assigned price books; a price book can be assigned to one or more sites.
- Currency rules:
    - You can assign multiple price books to a site if they share the same currency.
    - If **multi-currency** is enabled, you can assign multiple price books as long as each currency is enabled on the site.
    - If you assign a price book with a currency that isn’t enabled on the site, B2C Commerce ignores it for price determination.

## Create price books (unit walkthrough)
Brandon creates two price books:

### 1) Main list price book
- Business Manager → Merchant Tools | Site | Products and Catalogs | **Price Books** → New
- ID: `main-list-price-cc`
- Name: `Main List Price - Cloud Kicks`
- Activated: Yes
- Currency: US Dollar
- Apply
- (Optional) Attributes tab: custom attributes for the PriceBook system object

### 2) Sale price book “based on” the main price book
- Create second price book:
    - ID: `accessory-sale-price-list`
    - Name: `Accessory Sale Price - Cloud Kicks`
    - Activated: Yes
    - Currency: US Dollar
    - “based on” price book: `main-list-price-cc`
- Pricing lookup behavior described:
    - B2C Commerce checks sale price book first, then falls back to main list price book.

### Site assignments
- For each price book: Site Assignments tab → select site(s) → Apply.

## Read-Only Price Books (what they are + why they’re faster)
- **Read-Only Price Books** are intended for frequent, high-scale price imports from ERP or other sources:
    - XML-based
    - Import at least **60% faster** than a standard price book
    - Prices take effect in the search index without requiring product indexing
    - Can hold up to **300 million** prices
- After switching, price data becomes read-only (stored using separate storage technology).
- Workflow:
    - Edit prices in ERP → reimport to Business Manager
- Emergency option:
    - Create an editable price book and rebuild search indexes (but you lose performance benefits); reimport read-only data and remove editable data as soon as practical.

### How to enable/import Read-Only Price Books (unit steps)
1) Turn on feature:
- Administration | Global Preferences | Feature Switches
- HighScale Price Books Feature → Read and agree to legal requirements → I Agree → Apply

2) Enable import behavior:
- Administration | Global Preferences | Import and Export
- Enable “Import All Prices Books as Read-Only” → Apply

3) Reimport price books to staging, then replicate to production (best practice).

## Price tables (volume-based pricing)
- **Price tables** let merchants set lower prices for higher quantities (volume pricing).
- You can create multiple price tables per product ID (SKU) in a price book:
    - Each table has a unique start date and a different valid time period.
    - Null time period = continuous price.
- The unit provides a volume pricing example table and shows how to:
    - Set base price per product
    - Add volume limits (for example 6, 11) and corresponding prices
    - Define activation From/To dates and revert to continuous by clearing dates
    - Create multiple price tables for the same product using “Add Price Table”

## Tiếng Việt

## Learning Objectives
- Giải thích B2C Commerce chọn price book nào.
- Liệt kê permissions cần để tạo/sửa/xóa price books.
- Mô tả **Read-Only Price Books** giúp merchant như thế nào.
- Giải thích **site assignment** cho price books.
- Giải thích vì sao cần **price tables**.

## Price book là gì (định nghĩa)
- **Price book** chứa dữ liệu giá theo **currency**.
- Có thể tạo thủ công trong Business Manager hoặc import từ **ERP**/financial system.
- Giá thường không được xem là product data “thuần” (quản lý riêng).
- Phải có products trước khi tạo price books.
- Mỗi product phải có giá cho quantity **1** trong một price book active trên site; **computed prices** được suy ra từ giá này.

## B2C Commerce chọn price book như thế nào (priority)
- Có thể active nhiều price books.
- Nếu hai price books assigned có thời gian hiệu lực overlap:
    - Price book có **Valid From** gần nhất sẽ thắng.
- Price book có thời gian hiệu lực cụ thể sẽ thắng continuous price book.

## Best practice vận hành (performance)
- Giữ bộ price books ổn định với tên cố định.
- Dùng import mode **merge** hoặc **replace** để update giá nhanh.
- Tránh xóa/tạo lại price books theo chu kỳ vì làm chậm hệ thống và ảnh hưởng shopper experience.

## Permissions cần có
- Unit nêu 2 functional permissions:
    - `Manage_PriceBooks`
    - `Manage_Site_PriceBooks`
- Note: nếu permissions “mix” từ nhiều roles, hệ thống cấp quyền cao hơn.

## Site assignment (để price book có hiệu lực trên site)
- Price books định nghĩa ở cấp organization, sau đó assign cho site(s).
- Một site có thể có nhiều price books; một price book có thể assign nhiều sites.
- Currency rules:
    - Multiple price books trên site nếu cùng currency.
    - Nếu bật **multi-currency**, có thể assign nhiều price books theo từng currency đã enable trên site.
    - Price book có currency không enable trên site sẽ bị B2C Commerce bỏ qua khi lookup giá.

## Tạo price books (walkthrough)
### 1) Main list price book
- Price Books → New
- ID `main-list-price-cc`, Name `Main List Price - Cloud Kicks`, Activated Yes, Currency USD → Apply

### 2) Sale price book “based on”
- ID `accessory-sale-price-list`, Name `Accessory Sale Price - Cloud Kicks`, Activated Yes, Currency USD
- based on `main-list-price-cc`
- Lookup: sale price book trước, fallback về main list price book.

### Site Assignments
- Site Assignments tab → chọn site(s) → Apply.

## Read-Only Price Books
- XML-based, nhanh hơn tối thiểu **60%**, không cần product indexing để giá có hiệu lực trong search index, chứa tới **300 million** prices.
- Sau khi chuyển sang read-only: sửa giá ở ERP rồi reimport.
- Emergency: tạo editable price book + rebuild indexes (mất performance), sau đó reimport read-only và xóa editable càng sớm càng tốt.

### Enable/import (steps)
1) Feature Switches: HighScale Price Books Feature → đồng ý legal → Apply
2) Import and Export: bật “Import All Prices Books as Read-Only” → Apply
3) Reimport vào staging rồi replicate sang production (best practice).

## Price tables (volume pricing)
- **Price tables** để set giá thấp hơn khi mua số lượng cao.
- Có thể tạo nhiều price tables cho một SKU:
    - Unique start date + valid time period
    - Null time period = continuous
- Unit hướng dẫn set base price, thêm volume limits, set From/To, clear để về continuous, và “Add Price Table” để có multiple tables.