# Create Promotions
https://trailhead.salesforce.com/content/learn/modules/b2c-campaigns-and-promotions/b2c-create-promotions

## English

## Learning Objectives
- Explain why it’s important to select qualifying and discounted products carefully.
- Explain how exclusivity works.
- Describe what you must do for an Alert on Approaching setting.
- Explain the difference between promotion types.

## Promotion plan (what Brandon will configure)
The unit shows Brandon’s plan by class, discount type, discount, and exclusivity:
- Product: 20% off Brand‑X SuperSpeed running shoes — Without qualifying products — Percent off — Exclusivity **CLASS**
- Product: Free baseball with baseball shoes — With qualifying products — Bonus — Exclusivity **CLASS**
- Product: Buy one get one half‑off Brand‑Y Xcel shorts & t‑shirts — Buy X/Get Y — (Buy 1 / Get 1 discounted 50% off) — Exclusivity **CLASS**
- Order: 15% off orders over $50 — Without qualifying products — Percent off — Exclusivity **NO**
- Shipping: Free shipping orders over $100 — With amount of shipment qualifying products — Free Shipping — Exclusivity **NO**

## Product promotions (core concepts)
- Brandon uses **CLASS exclusivity** for all product promotions so shoppers can’t use more than one promotion in the same class.
- Selecting qualifying/discounted products carefully matters because discounts can apply across product structures:
    - Even though shoppers can’t order a base product, you can discount a base product so the discount applies to all its variations.
- Product types you can select (as discounted/qualifying products) in the unit:
    - Standard product
    - Variation product
    - Product set
    - Product bundle

## Create Product Promotion: 20% Off Brand‑X SuperSpeed Running Shoes (step-by-step)
1) Merchant Tools → Online Marketing → **Promotions** → New
2) General info:
    - ID: `20off-brandxsuperspeed`
    - Name: `20% Off Brand-X SuperSpeed`
    - Enable + make searchable
    - Callout message: `Great News! 20% off Brand-X SuperSpeed sneakers!`
    - Promotion details: `20% Off Brand-X SuperSpeed`
    - Select an image
    - Exclusivity: **CLASS**
    - Apply
3) Rules section:
    - Class: Product
    - Type: Without Qualifying Products
    - Enter `20` (applies to each applicable line item)
    - Discount: Percent off
    - Discounted Products: Edit → Brand equals Brand‑X → Save
    - Maximum Applications: leave empty (applies to every qualifying product in cart)
4) Test on storefront

## Create Product Promotion: Free Baseball with a Pair of Baseball Shoes (step-by-step)
General + Rules highlights shown in the unit:
- ID, name, enable + searchable, callout message that includes limitation wording.
- Class: Product
- Type: With Number of Qualifying Products
- Qualifying quantity: `1`
- Discount: Bonus Product
- Select bonus product (baseball)
- Qualifying Products: select all baseball shoes by ID
- Maximum application: `1` (one baseball per order)
- Apply + test

## Create Product Promotion: Buy One Get One Half Off Brand‑Y Xcel (step-by-step)
- ID: `buyonegetonehalfoff-brand-y`
- Enable + searchable, callout message, image, exclusivity **CLASS**
- Rules:
    - Class: Product
    - Type: Buy X / Get Y
    - Configure: “Buy 1 or more and get 1 discounted product for 50 Percent Off”
    - Qualifying products: Brand equals Brand‑Y Xcel (as specified in unit text)
    - Discounted Products: Same as qualifying products
    - Maximum application: `1`
    - Apply + test

## Order promotions (Alert on Approaching + SFRA/SiteGenesis note)
- Order promotion target: orders over $50 get 15% off.
- The unit calls out **Alert on Approaching**: Brandon wants to alert when the order value is within $10 of the threshold.
- The code for this feature is included in **SFRA** and **SiteGenesis**.

## Shipping promotions (class difference)
- Shipping promotions discount shipping costs (example: free shipping over $100).
- The unit distinguishes shipping promotions from product and order promotions by class and how they’re calculated.

## Best practices: test plan, messaging, workflow (unit topics)
- The unit includes sections on:
    - Best Practices
    - Create a Test Plan
    - Messaging in the Storefront (callout messages/communication)
    - Promotion Workflow (how promotions move from configuration to active usage)
      These emphasize validating promotions in a controlled environment and ensuring shopper-facing messaging is accurate.

## Tiếng Việt

## Learning Objectives
- Giải thích vì sao phải chọn qualifying/discounted products cẩn thận.
- Giải thích exclusivity hoạt động thế nào.
- Mô tả cần làm gì cho setting **Alert on Approaching**.
- Giải thích khác nhau giữa promotion types.

## Promotion plan (bảng cấu hình trong unit)
Unit đưa plan theo class/discount type/discount/exclusivity:
- Product: 20% off Brand‑X SuperSpeed — Without qualifying products — Percent off — **CLASS**
- Product: Free baseball với baseball shoes — With qualifying products — Bonus — **CLASS**
- Product: Buy 1 get 1 half off Brand‑Y Xcel — Buy X/Get Y — 50% off — **CLASS**
- Order: 15% off orders over $50 — Without qualifying products — Percent off — **NO**
- Shipping: Free shipping orders over $100 — With amount of shipment qualifying products — Free Shipping — **NO**

## Product promotions (ý chính)
- Dùng **CLASS exclusivity** để không cho shopper dùng >1 promotion trong cùng class.
- Chọn qualifying/discounted products cẩn thận vì discount có thể áp qua cấu trúc variations:
    - Có thể discount base product để áp cho tất cả variations.
- Product types có thể chọn trong unit:
    - Standard product
    - Variation product
    - Product set
    - Product bundle

## Tạo promotion 20% off Brand‑X (step-by-step)
- Promotions → New → ID `20off-brandxsuperspeed`, enable + searchable, callout message, details, image, exclusivity CLASS → Apply
- Rules: Product → Without Qualifying Products → nhập 20 → Percent off → Discounted Products: Brand = Brand‑X → Save
- Maximum Applications để trống → Apply mọi line item phù hợp
- Test storefront

## Tạo promotion Free baseball (step-by-step tóm)
- Product + With Number of Qualifying Products, quantity 1
- Discount: Bonus Product, chọn bonus product
- Qualifying products: chọn baseball shoes theo ID
- Maximum application 1 (1 baseball/order)
- Apply + test

## Tạo promotion Buy 1 Get 1 half off Brand‑Y Xcel (step-by-step tóm)
- ID `buyonegetonehalfoff-brand-y`, exclusivity CLASS
- Rules: Buy X/Get Y → Buy 1+ get 1 discounted 50% off
- Qualifying products: Brand = Brand‑Y Xcel
- Discounted Products: same as qualifying
- Maximum application 1 → Apply + test

## Order promotions (Alert on Approaching + SFRA/SiteGenesis)
- Order > $50 được 15% off.
- **Alert on Approaching**: cảnh báo khi còn thiếu $10 để đạt ngưỡng.
- Feature code có sẵn trong **SFRA** và **SiteGenesis**.

## Shipping promotions
- Shipping promotions discount shipping cost (ví dụ free shipping > $100) và khác class với product/order.

## Best practices: test plan, messaging, workflow
- Unit có các phần Best Practices, Test Plan, Messaging in the Storefront, Promotion Workflow — nhấn mạnh test/validate và thông điệp hiển thị cho shopper phải đúng.