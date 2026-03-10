# Learn About Sorting Rules
https://trailhead.salesforce.com/content/learn/modules/b2c-storefront-sorting-rules/b2c-learn-about-sorting-rules

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe the benefits of using sorting rules.
- List the three types of sorting rules you can configure.
- Describe four types of attributes you can use when building sorting rules.
- Explain the difference between **search placement** and **search rank**.

## Why sorting rules (what they help you achieve)
Sorting rules let merchandisers curate product sequencing to improve discovery and conversion. The unit highlights goals such as:
- Help shoppers find products (present better sequences, and show assortments based on what a shopper has already viewed).
- Feature best-selling/new/most popular products using **active data** and category-based rules.
- Vary product sequencing for repeat customers (avoid showing the same list every visit; use active merchandising data to personalize).
- Increase add-to-basket and conversion rates by presenting more relevant items first.

## Sorting rule types (3)
The unit describes three places/uses where sorting rules are configured for storefront behavior:
1) **Keyword search results**
- When a shopper enters a query, a sorting rule orders the search results.
- A sorting rule is layered: top attribute ranks all products; the next attribute breaks ties; continue until ties are resolved.
- You set direction (ascending/descending) per attribute layer.

2) **Explicit category placement**
- Category sorting starts from the sorting rule assigned to the navigational catalog’s **root category**.
- All subcategories inherit the root sorting rule unless overridden at a subcategory.
- The `category position` attribute can place products in a specific order within a category (but only if `category position` is included in the sorting rule).

3) **Storefront sorting options**
- These are the shopper-facing dropdown options (for example price “Low to High”).
- Shoppers see choices, but not the underlying logic. Example: they might see “Top sellers” without knowing the metric used (units sold vs revenue).

## Where else you can use sorting rules (beyond search/category)
The unit notes sorting rules can also be used in:
- **Campaigns**
- **A/B testing**
- **Predictive sort** (Commerce Cloud Einstein)

### Global vs site-scoped sorting rules
- When creating a sorting rule, you can choose **site** scope or **global** scope.
- Global sorting rules can only use **global dynamic attributes**, but scoring still remains site-specific (based on site data).
- You can change scope (site ↔ global) in Business Manager or via import/export.

## Commerce Cloud Einstein (Predictive Sort)
- **Commerce Cloud Predictive Sort** personalizes sorting for each shopper using catalog/product data, order history, and live clickstream signals.

## Settings and attributes you can use (4 attribute families)
Sorting rules are built from attributes; the unit groups them:

### 1) Category or product settings (manual control)
Goal: maximum control over ordering.
Attributes:
- `category position`
- `search placement`
- `search rank`

### 2) Text relevance settings
Goal: sort by how closely products match the search query.
Attribute:
- `text relevance`
  Important constraint: works only in a search-specific sorting rule.

### 3) Product attributes (product system object)
Goal: sort based on merchant-defined product attributes.
Examples listed include:
- Brand, Price, Online From
- New In*, On Sale*, Material*, Collection*, Delivered From Supplier*, Rating*
- Profit Margin**  
  (*Requires custom attribute. **Requires import of cost data.)

### 4) Active data attributes
Goal: sort based on data captured/calculated by B2C Commerce.
Examples listed:
- Revenue, Orders, Units Ordered, Conversion Rate
- Impressions, Views
- ATS (Available to Sell), SKU Coverage
- Availability, Availability Ranking, Days Available

## Data attribute types (what you can pull into rules)
The unit lists attribute source categories:
- **Product**: any single-value (non-set) attribute of the product system object, except Password/Image/Text/HTML/Email types. Attributes don’t need to be flagged online/searchable to be used in sorting rules.
- **Active data**: requires active merchandising feature; includes production order data and storefront behavior signals.
- **Availability model**: requires availability feature and/or active merchandising.
- **Dynamic**: custom combinations of attributes you create.

## Search placement vs search rank (difference)
- Both are manual attributes used to influence ordering, but they represent different controls:
    - **search placement** is used to place specific products earlier (explicit placement).
    - **search rank** influences ranking order as a scoring factor (used to move products up/down relative to others).

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả lợi ích của sorting rules.
- Liệt kê 3 loại sorting rules có thể cấu hình.
- Mô tả 4 nhóm attributes có thể dùng để build sorting rules.
- Giải thích khác nhau giữa **search placement** và **search rank**.

## Vì sao cần sorting rules (lợi ích)
Sorting rules giúp merchandiser “curate” thứ tự hiển thị sản phẩm để tăng discovery và conversion. Unit nêu các mục tiêu:
- Giúp shopper tìm sản phẩm dễ hơn (trình bày sequence tốt hơn; hiển thị assortment tối ưu dựa trên hành vi đã xem).
- Feature best-selling/new/most popular bằng **active data** và rules theo category.
- Thay đổi sequence cho khách quay lại (không thấy list giống nhau; dùng active merchandising data để cá nhân hóa).
- Tăng add-to-basket và conversion bằng cách đưa sản phẩm phù hợp lên trước.

## 3 loại sorting rules
1) **Keyword search results**
- Khi shopper search, sorting rule quyết định thứ tự kết quả.
- Rule có nhiều “layer”: attribute đầu rank tất cả; attribute sau break ties; tiếp tục cho đến khi hết tie.
- Set ascending/descending cho từng layer.

2) **Explicit category placement**
- Category sorting dựa vào sorting rule gán cho **root category** của navigational catalog.
- Subcategories inherit nếu không override.
- Attribute `category position` cho phép đặt thứ tự cụ thể trong category (chỉ khi rule có include `category position`).

3) **Storefront sorting options**
- Dropdown cho shopper (ví dụ price “Low to High”).
- Shopper thấy option nhưng không thấy logic phía sau (Top sellers dùng units sold hay revenue…).

## Sorting rules còn dùng ở đâu
- **Campaigns**
- **A/B testing**
- **Predictive sort** (Commerce Cloud Einstein)

### Global vs site scope
- Khi tạo rule chọn scope theo **site** hoặc **global**.
- Global rules chỉ dùng **global dynamic attributes** nhưng scoring vẫn site-specific.
- Có thể đổi scope site ↔ global trong Business Manager hoặc import/export.

## Commerce Cloud Einstein (Predictive Sort)
- **Predictive Sort** cá nhân hóa sorting theo catalog/product data, order history và clickstreams.

## Settings/attributes (4 nhóm)
### 1) Category/product settings (manual)
- `category position`, `search placement`, `search rank`

### 2) Text relevance
- `text relevance` (chỉ dùng cho search-specific sorting rule)

### 3) Product attributes
- Ví dụ: Brand, Price, Online From, New In*, On Sale*, Material*, Collection*, Delivered From Supplier*, Rating*, Profit Margin**
  (*custom attribute; **import cost data)

### 4) Active data attributes
- Revenue, Orders, Units Ordered, Conversion Rate, Impressions, Views
- ATS (Available to Sell), SKU Coverage, Availability, Availability Ranking, Days Available

## Attribute source types
- **Product** (single-value product system object; trừ Password/Image/Text/HTML/Email; không cần online/searchable).
- **Active data** (cần active merchandising feature).
- **Availability model** (availability feature và/hoặc active merchandising).
- **Dynamic** (custom combinations).

## Search placement vs search rank
- **search placement**: đặt/đẩy một số products lên trước theo placement rõ ràng.
- **search rank**: điều chỉnh ranking theo “điểm/xếp hạng” so với products khác.