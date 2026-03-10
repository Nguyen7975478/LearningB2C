# Create Campaigns
https://trailhead.salesforce.com/content/learn/modules/b2c-campaigns-and-promotions/b2c-create-campaigns

## English

## Learning Objectives
- Describe how to apply qualifiers to a campaign.
- Explain how you can manage campaigns to save time.
- List four troubleshooting questions.
- Explain how to deactivate qualifiers.

## Inputs used in this unit (what you already created)
Qualifiers:
- Coupon: `spring-code`
- Customer group: `loyalty-shoppers`, `lapsed-shoppers`
- Source Code group: `sourcecode-spring`

Promotions:
- Product promotions:
    - `20off-brandxsuperspeed`
    - `freebaseballwithbaseballshoes`
    - `buyonegetonehalfoff-brand-y`
- Order promotion: `15%off-ordersover$50`
- Shipping promotion: `freeship-ordersover100`

## Create a campaign and attach qualifiers + promotions (step-by-step)
1) Merchant Tools → Online Marketing → **Campaigns**
2) New
3) Enter:
    - ID: `spring-campaign`
    - Description
    - Activate: Yes
    - Schedule: January 15 to April 15
    - Date format note: `mm/dd/yyyy`
4) Campaign start/end date and time are optional:
    - No start date → enabled immediately
    - No end date → runs indefinitely

### Add qualifiers to the campaign
- Customer groups:
    - Edit → select `lapsed-shoppers` and `loyalty-shoppers`
    - Do **not** select “Qualifying Customers Must Belong to All Selected Customer Groups” (so either group can qualify)
    - Apply
- Source codes:
    - Edit → select `sourcecode-spring` → Apply
- Coupons:
    - Edit → select `spring-codes` → Apply

### Add experiences (promotions) to the campaign
1) Add Experience → Add Promotion
2) Use Enabled sort/filter (Enabled tab twice) to bring enabled promotions to the top
3) Select the promotions you created
4) Apply

## Fine-tune which qualifiers apply to which promotions
- Initially, all qualifiers apply to all promotions.
- Unit provides a mapping table showing which promotion should use which qualifier type (coupon/customer group/source code) and whether qualifier is static/dynamic/multiple codes, etc.
- To deselect qualifiers that don’t apply to a promotion:
    1) Open campaign
    2) Expand Promotions experiences
    3) Click (…) next to a qualifier to deselect
    4) Deselect settings such as “Use Customer Groups as promotion qualifiers?”
    5) Apply (and apply again on Campaign page)

### Any vs All qualifiers (Required Qualifiers per promotion experience)
- **Any**: shopper qualifies if they meet at least one qualifier
- **All**: shopper must meet all qualifiers
- Example in unit: shopper clicks a source code link, logs in as Loyalty Program member, and uses a coupon code.

### Rank per promotion within a campaign
- You can apply **rank** per promotion experience using the Rank field next to Any/All, to control precedence within the campaign.

## Create other experiences (after testing promotions)
- Slot configuration experience:
    - Can modify overall campaign schedule
    - Assign more customer groups and a rank
    - Select which slot configurations to use
- Sorting rule experience:
    - Select one or more sorting rules (example: brand sorting rule)
    - Specify categories/subcategories per sorting rule experience

## Manage campaigns (save time)
- Use an existing campaign as a “default campaign”:
    - Copy the campaign and make minor changes for a new campaign.

## Test experiences (storefront verification)
Example test described: order promotion `15%off-ordersover$50`
1) Open Business Manager
2) Select site: CloudKicks
3) Storefront tab → opens storefront in new window
4) Search products, add to cart
5) Open cart
6) Verify discount callout message appears beneath product list and above coupon entry fields

## Troubleshoot (4 checks)
When experiences don’t work, verify:
- The promotion exists in a campaign.
- The campaign is active/enabled and valid for the current date, and promotion belongs to the campaign.
- The promotion is enabled and valid for the current date (and dates align).
- Shoppers qualify correctly (customer group OR coupon OR source code, as configured).

## Storefront Toolkit (staging)
- Use **Storefront Toolkit** on a staging instance to preview and troubleshoot:
    - Merchant Tools → SitePreferences → Toolkit
    - In storefront, open Toolkit icon → Preview Settings
    - Set preview date/time to verify scheduling
    - Specify customer group or source code to preview qualification scenarios

## Deactivate qualifiers (how it fits)
- Deactivating qualifiers is part of “Which Qualifiers?”—you remove qualifier usage from promotions where it should not apply (deselect/disinherit at promotion experience level).

## Tiếng Việt

## Learning Objectives
- Mô tả cách apply qualifiers vào campaign.
- Giải thích cách manage campaigns để tiết kiệm thời gian.
- Liệt kê 4 câu hỏi troubleshoot.
- Giải thích cách deactivate qualifiers.

## Inputs dùng trong unit
Qualifiers:
- Coupon: `spring-code`
- Customer groups: `loyalty-shoppers`, `lapsed-shoppers`
- Source Code group: `sourcecode-spring`

Promotions:
- Product: `20off-brandxsuperspeed`, `freebaseballwithbaseballshoes`, `buyonegetonehalfoff-brand-y`
- Order: `15%off-ordersover$50`
- Shipping: `freeship-ordersover100`

## Tạo campaign + gắn qualifiers/promotions (step-by-step)
- Campaigns → New → ID `spring-campaign` → Activate Yes → schedule Jan 15–Apr 15
- Note format: `mm/dd/yyyy`
- Start/end time optional: không start date → enable ngay; không end date → chạy vô hạn

### Add qualifiers
- Customer groups: chọn `lapsed-shoppers` + `loyalty-shoppers`, không chọn “must belong to all…”, Apply
- Source codes: chọn `sourcecode-spring`, Apply
- Coupons: chọn `spring-codes`, Apply

### Add experiences (promotions)
- Add Experience → Add Promotion → lọc enabled → chọn promotions đã tạo → Apply

## Fine-tune qualifiers theo từng promotion
- Mặc định mọi qualifiers áp cho mọi promotions.
- Unit có bảng mapping “promotion ↔ qualifier type”.
- Deselect qualifiers không áp dụng: mở campaign → expand promotions → (…) → bỏ chọn “Use Customer Groups as promotion qualifiers?” → Apply + Apply trên campaign.

### Any vs All
- **Any**: chỉ cần đạt 1 qualifier
- **All**: phải đạt tất cả qualifiers
- Ví dụ: click source code + login loyalty + dùng coupon.

### Rank theo promotion trong campaign
- Có thể set **rank** cho từng promotion experience (field cạnh Any/All).

## Create other experiences (sau khi test promotions)
- Slot configuration experience: chỉnh schedule, gán customer groups, rank, chọn slot configs.
- Sorting rule experience: chọn sorting rules (ví dụ brand sorting rule), set categories/subcategories.

## Manage campaigns (tiết kiệm thời gian)
- Copy campaign cũ làm default rồi chỉnh nhỏ cho campaign mới.

## Test experiences (verify trên storefront)
- Test order promotion `15%off-ordersover$50`: mở storefront → add cart → check callout message.

## Troubleshoot (4 checks)
- Promotion có nằm trong campaign không?
- Campaign active/valid date và promotion thuộc campaign?
- Promotion enabled/valid date?
- Shopper có qualify đúng (customer group OR coupon OR source code)?

## Storefront Toolkit (staging)
- Dùng **Storefront Toolkit** trên staging: Preview Settings đặt date/time, set customer group/source code để test qualification.

## Deactivate qualifiers
- Thực tế là “deselect/disinherit” qualifiers không áp dụng cho promotion experience cụ thể trong campaign.