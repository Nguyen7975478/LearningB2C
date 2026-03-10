# Use Configurator to Review Data
https://trailhead.salesforce.com/content/learn/modules/cc-einstein-plan-and-implement/cc-ai-work-better

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List two tools available in Configurator.
- Explain how to use the Commerce Insights tool.
- List two benefits of using Commerce Insights.

## What Configurator is (clear mental model)
The unit defines Configurator as:
- the online tool used to build **Einstein Product Recommenders**,
- which helps merchandisers configure and manage:
  - **Commerce Insights**
  - **Einstein Product Recommendations**

Important scope note (unit):
- This unit focuses on **Commerce Insights**.
- Product Recommendations configuration is taught in another module.

Prerequisite:
- Before a merchandiser can use Configurator, an administrator must install it (directions are in the **Infocenter**).

## Two tools available in Configurator (unit list)
1) **Commerce Insights**
- Purpose: discover which products are most often purchased together.

2) **Einstein Product Recommendations**
- Purpose: predict the most relevant products to promote to shoppers based on recommendation specifications.

How to interpret “two tools”:
- Insights = “learn what shoppers do”
- Recommendations = “use what you learned to change what shoppers see”

## Commerce Insights (what it does and what questions it answers)
The unit explains:
- **Einstein Commerce Insights** captures shopper **order** and **product** data.
- It identifies products that shoppers purchase together.
- The dashboard helps merchandisers find:
  - which products are most often purchased with a specific product,
  - and lets them drill down by **date range**.
- You can explore metrics such as:
  - product-specific **sales**
  - top **co‑purchase categories**

Main benefit statement (unit):
- “This takes the guesswork out of merchandising.”

## Review a Product (step-by-step, plus “what you’re seeing”)
### Steps (unit)
Each row shows:
- a single product (key item) and the **top 50** products purchased in the same basket.

To review:
1) Open Configurator.
2) On the dashboard, select a product.
3) Use **Product Drilldown** to see details about baskets in which the product was purchased.
4) View the **Commonly Bought With** table.

### Data you see (unit table) — and how to read it
The unit explicitly lists the fields; below is the meaning so you can understand the “idea”.

#### Key Item
- **Product ID**: unique identifier of the item being analyzed (used to map back to catalog/SKU logic).
- **Product Display Name**: human-friendly name for quick validation.
- **Baskets / Sales / Units**: performance of the key item during the selected time range.

Interpretation:
- This section sets the “baseline”: how frequently and how strongly the key item sells.

#### Purchased in Same Basket
For each of the top 50 co-purchased items:
- **Product ID**
- **Product Display Name**
- **Baskets**: number of times shoppers purchased the item in the same basket as the key item (for the selected date range).
- **Basket %**: percent of all key-item baskets that contained that item.

Interpretation:
- “Baskets” shows absolute co-occurrence volume.
- “Basket %” normalizes by key-item basket count, helping you see the *strength of association*.

## Configure a Report (how to scope insights to the right part of the catalog)
The unit explains how the report is structured and constrained.

### Catalog hierarchy drives navigation
- An Insight report uses the **catalog hierarchy** defined in Business Manager.
- Category/subcategory navigation focuses the report on a subset of products.
- A breadcrumb trail at the top lets you jump back to a higher level.

Why this matters:
- You can avoid noisy cross-category patterns when you’re planning a specific area like “Men’s Jackets”.

### Default time range and limits (unit)
- Default: **previous week’s data** (Sunday → Saturday of the previous calendar week).
- You can pick a different date range.
- You can go back **30 days**.
- The unit notes: data **can’t be exported**.

Interpretation:
- Insights are for decisions and pattern recognition inside the tool (not for finance-grade exports).

### Sorting (what you can sort on)
The unit says you can sort ascending by:
- baskets
- sales
- units
- and other options

## Plan with Commerce Insights (how to turn metrics into merchandising actions)
The unit provides examples and intent:

- Use Insights to find correlations and patterns (example: seasonal trends).
- Examples from the unit:
  - winter hat often purchased with winter coat/vest
  - winter socks often purchased with gloves and winter boots
- Commerce Insights is an **analysis tool**, not a financial reporting tool.
- The purpose is to map co-purchase correlations so merchandisers can build:
  - product **bundles**
  - **deals**
  - “**complete the look**” suggestions

Practical interpretation:
- If two products have high Basket % together, test:
  - PDP “You may also like”
  - cart cross-sell
  - bundle/set merchandising (if your catalog strategy supports it)

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê 2 tools trong Configurator.
- Giải thích cách dùng Commerce Insights tool.
- Liệt kê 2 benefits của Commerce Insights.

## Configurator là gì (mental model rõ ràng)
Unit định nghĩa Configurator là:
- online tool để build **Einstein Product Recommenders**,
- giúp merchandiser configure/manage:
  - **Commerce Insights**
  - **Einstein Product Recommendations**

Note về phạm vi:
- Unit này tập trung **Commerce Insights**.
- Product Recommendations học ở module khác.

Prerequisite:
- Trước khi merchandiser dùng, admin phải install Configurator (trong **Infocenter**).

## 2 tools trong Configurator (theo unit)
1) **Commerce Insights**
- Discover products thường mua cùng.

2) **Einstein Product Recommendations**
- Predict products phù hợp để promote theo recommendation specifications.

Cách hiểu:
- Insights = “hiểu hành vi”
- Recommendations = “đưa hành vi vào trải nghiệm”

## Commerce Insights làm gì (và trả lời câu hỏi gì)
- Capture **order** + **product** data.
- Identify items shoppers mua cùng.
- Dashboard cho biết:
  - product nào hay mua kèm với 1 product cụ thể,
  - drilldown theo **date range**,
  - xem metrics như **sales** và top **co‑purchase categories**.
- Lợi ích chính: giảm guesswork.

## Review a Product (các bước + hiểu ý nghĩa dữ liệu)
### Steps (unit)
- Mỗi row: 1 product và **top 50** products mua cùng basket.
1) Open Configurator
2) Chọn product
3) **Product Drilldown** xem baskets
4) Xem **Commonly Bought With**

### Data bạn sẽ thấy (unit) và cách hiểu
#### Key Item
- Product ID: định danh
- Product Display Name: tên dễ đọc
- Baskets / Sales / Units: hiệu suất key item trong time range

Ý nghĩa:
- Baseline: key item bán thế nào trong khoảng thời gian đó.

#### Purchased in Same Basket
- Product ID / Display Name
- Baskets: số lần item đó xuất hiện cùng basket với key item
- Basket %: % baskets của key item có chứa item đó

Ý nghĩa:
- Baskets = volume tuyệt đối.
- Basket % = độ “gắn kết” (association strength) đã normalize.

## Configure a Report (scope theo catalog)
### Dựa trên catalog hierarchy
- Report dùng **catalog hierarchy** trong Business Manager.
- Category/subcategory để focus subset products.
- Breadcrumb để quay lại level cao hơn.

Ý nghĩa:
- Giảm noise; tập trung đúng khu vực merchandising.

### Default time range và limits
- Default: **previous week** (Sun–Sat tuần trước).
- Chọn date range khác được.
- Look back tối đa **30 days**.
- Data **không export** được.

Ý nghĩa:
- Dùng để ra quyết định/nhận pattern trong tool, không phải báo cáo tài chính.

### Sorting
- Sort theo baskets/sales/units/other options.

## Plan với Commerce Insights (biến insight thành action)
- Dùng để tìm correlations (seasonal trends).
- Ví dụ unit:
  - winter hat ↔ winter coat/vest
  - winter socks ↔ gloves + winter boots
- Commerce Insights là **analysis tool**, không phải financial reporting tool.
- Mục tiêu: map co‑purchase correlations để build:
  - **bundles**
  - **deals**
  - “**complete the look**”

Gợi ý áp dụng:
- Basket % cao → test PDP reco / cart cross-sell / bundles/sets.