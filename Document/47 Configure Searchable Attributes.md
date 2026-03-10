# Configure Searchable Attributes
https://trailhead.salesforce.com/content/learn/modules/b2c-storefront-search/b2c-configure-searchable-attributes

## English

## Learning Objectives
- Explain the importance of using searchable attributes.
- List the five general **boost factor** rules.
- Describe when to avoid using **autocorrect** with searchable attributes.
- Explain how **system objects** relate to searchable attributes.

## What searchable attributes are (core definition)
- When a shopper searches, B2C Commerce only looks at product/catalog/content attributes configured as **searchable**.
- Search results return only when the search term appears in a searchable attribute.
- If a term exists only in a non-searchable attribute, the product/content will not be returned.

## Example attribute strategy (unit table)
The unit provides example focus areas:
- Product searchable attributes: brand, boot type, outerwear, sandal type, shoe type, sneaker type, top type
- Category searchable attributes: size chart
- Content searchable attributes: holiday special

## Boost factor (how relevance weighting works)
- Boost factor increases/decreases the importance of an attribute in search results (example: sneaker type boost 2.00 vs color 1.00).
- General boost factor rules listed:
    1) You can use decimals as boost factors.
    2) `.01–.99` reduces impact.
    3) `1.00` is default (no change).
    4) `1.01–100.00` increases importance (recommendation: don’t go higher than 5).
    5) Use boost factors `<= 5.00`.
- Boost factor only works in search when text relevance is part of a sorting rule.

## Autocorrect / autocompletion caveat
- Searchable attribute values use autocorrection and autocompletion by default.
- Avoid autocorrect for attributes like product ID because product ID should route to a specific PDP; autocorrect could incorrectly steer to another product with similar ID.

## Caveats and performance guidance
- Searchable attributes are independent from refinement attributes and sorting-rule attributes, but:
    - Boost factor affects sort order if sorting rule uses text relevance.
- Too many searchable attributes increases index size and can slow search speed.
- Best practice: keep searchable attributes to the minimum necessary.

## Configure searchable attributes (Business Manager walkthrough)
1. Business Manager → App Launcher → **Merchant Tools | Search | Searchable Attributes**
2. Click **New** in the Product Index Attribute section
3. Expand the field list (only appropriate data types appear)
4. Select an attribute (example: Sandal Type (custom-sandalType)) — red triangles indicate unapplied changes
5. Enter **Boost Factor** (example: `2.00`)
6. Set **Autocorrection** (example: Yes)
7. Click **Apply** (red triangles disappear)
8. **Rebuild the product (or content) Index** (required)

## Create attributes first (system objects dependency)
- To configure a field as searchable, the attribute must already exist as an attribute definition on a **system object**:
    - product, catalog/category, or content system object.
- The unit shows how to create a missing content attribute first:

Create a Content system object attribute:
1. Business Manager → **Administration | Sites | Site Development | System Object Types**
2. Select **Content**
3. Attribute Definitions tab → **New**
4. Enter ID: `holiday-special`
5. Enter display name: `Holiday Special`
6. Set Localizable/Site-Specific to **Localizable**
7. Click **Apply**

Then set it as searchable:
8. Merchant Tools → Search → Searchable Attributes
9. Content Index Attributes → **New**
10. Select Holiday Special (custom.holiday-special)
11. Click **Apply**

## Troubleshoot search results (unit tips table)
- Queries/results: use Storefront toolkit **Search Information** tool to inspect how a query is constructed.
- Index: if an index feature doesn’t work, verify the feature is enabled in **Site Preferences | Search Preferences**.
- Stemming: if stemming fails in a non-English locale, change stemmer language in **Search | Search Indexes | Language Options**.

## Tiếng Việt

## Learning Objectives
- Giải thích tầm quan trọng của searchable attributes.
- Liệt kê 5 rules tổng quát cho **boost factor**.
- Mô tả khi nào nên tránh **autocorrect** với searchable attributes.
- Giải thích **system objects** liên quan searchable attributes thế nào.

## Searchable attributes là gì (định nghĩa)
- Khi shopper search, B2C Commerce chỉ tìm trên các attributes đã cấu hình **searchable**.
- Kết quả chỉ trả về nếu search term nằm trong searchable attribute.
- Nếu term nằm ở attribute không searchable thì sản phẩm/content không lên kết quả.

## Ví dụ chiến lược attributes (bảng trong unit)
- Product searchable attributes: brand, boot type, outerwear, sandal type, shoe type, sneaker type, top type
- Category searchable attributes: size chart
- Content searchable attributes: holiday special

## Boost factor (weighting relevance)
- Boost factor tăng/giảm “tầm quan trọng” của attribute trong search results (ví dụ sneaker type 2.00 quan trọng gấp đôi color 1.00).
- 5 rules:
    1) Có thể dùng số thập phân.
    2) `.01–.99` giảm tác động.
    3) `1.00` là default.
    4) `1.01–100.00` tăng tầm quan trọng (khuyến nghị không quá 5).
    5) Dùng boost factor `<= 5.00`.
- Boost factor chỉ có tác dụng khi sorting rule có dùng text relevance.

## Autocorrect/autocompletion (caveat)
- Searchable attribute values dùng autocorrection/autocompletion mặc định.
- Tránh autocorrect cho product ID vì cần dẫn đúng PDP; autocorrect có thể dẫn sai sang sản phẩm ID tương tự.

## Caveats và performance
- Searchable attributes không ảnh hưởng trực tiếp refinement/sorting attributes, nhưng:
    - Boost factor có thể ảnh hưởng sort order nếu sorting rule dùng text relevance.
- Quá nhiều searchable attributes làm index lớn và search chậm.
- Best practice: chỉ chọn số lượng searchable attributes tối thiểu cần thiết.

## Cấu hình searchable attributes (walkthrough)
1. **Merchant Tools | Search | Searchable Attributes**
2. **New** ở Product Index Attribute
3. Mở list fields (chỉ hiện data types phù hợp)
4. Chọn attribute (ví dụ Sandal Type (custom-sandalType)) — tam giác đỏ = chưa Apply
5. Nhập **Boost Factor** (ví dụ `2.00`)
6. Set **Autocorrection** (ví dụ Yes)
7. **Apply**
8. **Rebuild product/content Index**

## Phải tạo attributes trước (phụ thuộc system objects)
- Muốn set searchable, attribute phải tồn tại như attribute definition trên **system object**: product, catalog/category, hoặc content.
- Unit minh họa tạo content attribute:

Tạo Content system object attribute:
1. **Administration | Sites | Site Development | System Object Types**
2. Chọn **Content**
3. Attribute Definitions → **New**
4. ID: `holiday-special`
5. display name: `Holiday Special`
6. Localizable/Site-Specific: **Localizable**
7. **Apply**

Sau đó set searchable:
8. Merchant Tools → Search → Searchable Attributes
9. Content Index Attributes → **New**
10. Chọn Holiday Special (custom.holiday-special)
11. **Apply**

## Troubleshoot search results (tips)
- Queries/results: dùng Storefront toolkit **Search Information** tool.
- Index: kiểm tra feature có bật trong **Site Preferences | Search Preferences**.
- Stemming: nếu không hoạt động ở non-English locale, đổi stemmer language ở **Search | Search Indexes | Language Options**.