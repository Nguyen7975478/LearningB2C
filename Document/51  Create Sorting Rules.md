# Create Sorting Rules
https://trailhead.salesforce.com/content/learn/modules/b2c-storefront-sorting-rules/b2c-create-sorting-rules

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Configure a sorting rule using single attributes.
- Preview a category sorting rule.
- Configure a hybrid sorting rule.
- Configure a storefront sorting option using a dynamic attribute.

## Business Manager UI (3 sections)
The Sorting Rules page has three sections:
- **Sorting Rules**
- **Attributes**
- **Preview**

## Create a sorting rule (example: inventory-first sorting)
Brandon wants to boost high-inventory items in the Sale category. He evaluates availability ranking but chooses **ATS (Available to Sell)**.

### Rule design used
- Primary attribute: `ATS` (highest to lowest)
- Tie-breaker: `Revenue (30 Days)` (`activeData.revenueMonth`) (highest to lowest)
- Direction: Descending for both
- Text Relevancy: No (for both attributes)

### Step-by-step: create the rule
1) Business Manager → App Launcher → Merchant Tools | Site | Search | **Sorting Rules**
2) Click **New**
3) Enter Rule ID + description: `cloudkicks-01`
4) In Attributes section, click **Add**
5) Select attributes:
    - `ATS`
    - `Revenue (30 Days) (activeData.revenueMonth)`
6) Click **Apply**
7) Keep **Text Relevancy** = No for both attributes
    - If Yes: B2C Commerce multiplies attribute score by text relevance score (0–1), effectively creating a blended weighting (the unit describes this as equivalent to 50%/50% weighting).
    - Use when multiple items may have the same sorting-attribute score (recommendations sort) or when sorting for best sellers.
8) Direction: keep **Descending** for both

## Preview sorting rules (validate outcomes before storefront changes)
1) Merchant Tools | Site | Search | Sorting Rules
2) Select rule `cloudkicks-01`
3) Preview section:
    - Category: Sale
    - Search term: `shorts`
4) Click **Preview**
   Notes:
- Preview shows products based on the search term; if no products meet attribute requirements, you still see products in the preview category that contain the search term in the product name.

## Storefront Toolkit: examine search results
- You can examine search results using the Storefront Toolkit search information tool:
    - shows the sorting rule used,
    - shows criteria in the rule,
    - shows criteria values for each search result.

## Create a hybrid sorting rule (manual + attribute)
- The unit states Brandon creates a hybrid rule combining:
    - `category position` (manual attribute) and
    - a custom product attribute `isSale`
      to push sales items to the bottom of the search results.
      (Implementation details continue beyond the snippet returned, but the key concept is mixing manual placement with product-attribute logic.)

## Storefront sorting option using a dynamic attribute
- The unit’s objective includes creating a storefront sorting option that uses a **dynamic attribute** (dynamic attributes are the reusable computed signals you can expose as sorting options).
- The idea: shopper selects an option in a dropdown; the option is powered by a rule using a dynamic attribute.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Cấu hình sorting rule bằng single attributes.
- Preview category sorting rule.
- Cấu hình hybrid sorting rule.
- Cấu hình storefront sorting option dùng dynamic attribute.

## Business Manager UI (3 phần)
Trang Sorting Rules có 3 phần:
- **Sorting Rules**
- **Attributes**
- **Preview**

## Tạo sorting rule (ví dụ: ưu tiên tồn kho)
Brandon muốn đưa sản phẩm tồn kho cao lên trước ở Sale category. Anh cân nhắc availability ranking nhưng chọn **ATS (Available to Sell)**.

### Thiết kế rule
- Attribute chính: `ATS` (cao → thấp)
- Tie-breaker: `Revenue (30 Days)` (`activeData.revenueMonth`) (cao → thấp)
- Direction: Descending
- Text Relevancy: No

### Steps tạo rule
1) Merchant Tools | Site | Search | **Sorting Rules**
2) **New**
3) Rule ID/description: `cloudkicks-01`
4) Attributes → **Add**
5) Chọn:
    - `ATS`
    - `Revenue (30 Days) (activeData.revenueMonth)`
6) **Apply**
7) **Text Relevancy** = No
    - Nếu Yes: nhân attribute score với text relevance (0–1) để tạo blended weighting (unit mô tả tương đương 50/50).
    - Dùng khi nhiều items có cùng score hoặc cho best-sellers/recommendations.
8) Direction: Descending cho cả hai

## Preview sorting rules
- Chọn rule `cloudkicks-01` → Preview:
    - Category Sale
    - Search term `shorts`
    - **Preview**
- Nếu không có product thỏa attribute requirement, vẫn thấy products trong category có search term trong product name.

## Storefront Toolkit
- Toolkit cho biết sorting rule nào dùng, criteria và criteria values của từng result.

## Hybrid sorting rule
- Unit nêu hybrid rule kết hợp:
    - `category position` + custom attribute `isSale`
      để đẩy sales items xuống cuối kết quả.

## Storefront sorting option + dynamic attribute
- Unit yêu cầu cấu hình storefront sorting option dùng **dynamic attribute** để shopper chọn trong dropdown.