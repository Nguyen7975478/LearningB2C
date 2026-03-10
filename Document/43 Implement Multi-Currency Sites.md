# Implement Multi-Currency Sites
https://trailhead.salesforce.com/content/learn/modules/b2c-localization/b2c-implement-multi-currency-sites

## English

## Learning Objectives
- Explain why you would want to implement a multi-currency site.
- Explain how Salesforce B2C Commerce uses **session currency** for multi-currency sites.
- List the reports and analytics that support the multi-currency site feature.
- Explain how to show prices in multiple currencies on the product details page.

## Why multi-currency (what it enables)
- Multi-currency goes beyond localization: sell to multiple countries/regions from a single site using up to **150 currencies**.
- Shoppers can select currency, browse, and checkout using that currency (“flip a switch” model).

## When multi-currency is a good fit (unit reasoning)
Brandon considers multi-currency when multiple storefronts differ *only by currency* for:
- product prices
- shipping methods / shipping costs
- payment methods
- promotions

…and storefronts are otherwise the same in:
- logic and design
- catalog and content
- search and merchandising rules
- customers
- inventory
- third-party integrations
- order management

Note: The unit states support is limited to certain areas of B2C Commerce.

## Session currency (core mechanism)
- B2C Commerce uses the browser’s **session currency**.
- When a shopper first arrives, session currency is initialized to the site’s default currency.
- Session currency remains until the shopper selects a preferred currency.
- B2C Commerce remembers/restores session currency when the shopper returns.
- If the session currency becomes invalid (for example admin removes an allowed currency), B2C Commerce resets it to the default site currency the next time the shopper accesses the storefront.
- Shopper can’t checkout/create an order with an invalid currency (session currency must be allowed on the site).

## Reports and analytics (how revenue is handled)
The unit lists features that report revenue amounts for multi-currency sites:
- **A/B Testing**: statistics reflect converted monetary value for orders placed during a test.
- **Active Data**: customer and product active data reflect converted monetary values.
- **Reports & Dashboards**: realm currency setting can be changed so aggregated realm data for all sites shows in a selected currency.

Revenue conversion behavior:
- When B2C Commerce records a revenue event, monetary values are converted to the site’s default currency using that day’s exchange rate.
- B2C Commerce does not provide separate reporting per currency.
- Exchange rate service is internal and not viewable in Business Manager or via the B2C Commerce API.

## Implement multi-currency (step-by-step with roles)
The unit provides this implementation checklist:

1) Configure allowed currencies for the site — **Admin**
- Site is created with a single default currency; after creation, add allowed currencies.

2) Create price books for each currency — **Merchandiser**
- B2C Commerce looks up prices using session currency.
- Each price book is specific to one currency.
- For 3 currencies, create at least 3 price books.

3) Configure promotions to account for currency — **Merchandiser**
- Promotion can optionally specify a currency.
- If it applies to all currencies (example: 10% off), select a specific currency or **All**.
- Promotion applies only when shopper’s session currency matches.

4) Configure payment methods to specify a currency — **Merchandiser**
- Payment method can specify one or more allowed currencies.
- If no currency specified, all allowed currencies accepted by default.
- Payment method applies only for selected session currencies.
- You can specify min/max payment ranges per allowed currency.

5) Configure shipping methods to specify a currency — **Merchandiser**
- Shipping method can optionally specify an allowed currency.
- If not specified, B2C Commerce uses default site currency.
- Shipping method applies only when shopper selects that currency as session currency.

6) Customize storefront to let shopper select preferred currency — **Developer**
- Storefront must show allowed currencies and set session currency.
- Use `dw.system.Session` B2C Commerce Script API object to set session currency.

7) Modify import process for multi-currency changes — **Developer**
- Review documentation; adjust import logic for multi-currency requirements.

## Show prices in multiple currencies on PDP (API option)
- Separate from multi-currency checkout feature: you can display an additional price from another currency on the product details page using API methods:
    - `ProductPriceModel.getPriceBookPrice(String priceBookID)`
    - `ProductPriceModel.getPriceBookPrice(String priceBookID, Quantity quantity)`
- Limitation: this PDP “show another currency price” is not the same as multi-currency checkout; search price ranges/refinements/sorting and other price-related features are limited to the site currency only.

## Tiếng Việt

## Learning Objectives
- Giải thích vì sao triển khai multi-currency site.
- Giải thích cơ chế **session currency** của B2C Commerce.
- Liệt kê reports/analytics hỗ trợ multi-currency.
- Giải thích cách hiển thị giá nhiều currency trên product details page.

## Multi-currency giúp gì
- Multi-currency vượt ra ngoài localization: bán đa quốc gia/vùng trong cùng một site với tối đa **150 currencies**.
- Shopper chọn currency rồi browse/checkout theo currency đó.

## Khi nào multi-currency phù hợp (lý do trong unit)
Brandon cân nhắc multi-currency khi nhiều storefronts chỉ khác *currency* ở:
- product prices
- shipping methods / shipping costs
- payment methods
- promotions

…còn lại giống nhau ở:
- logic and design
- catalog and content
- search and merchandising rules
- customers
- inventory
- third-party integrations
- order management

Note: Unit nói hỗ trợ multi-currency bị giới hạn ở một số area.

## Session currency (cơ chế chính)
- B2C Commerce dùng **session currency** của browser.
- Lần đầu vào site: session currency = default currency của site.
- Giữ nguyên cho đến khi shopper chọn preferred currency.
- B2C Commerce nhớ/restore session currency khi shopper quay lại.
- Nếu session currency không còn hợp lệ (admin remove allowed currency), B2C Commerce reset về default currency ở lần truy cập tiếp theo.
- Không checkout/không tạo order với invalid currency (session currency phải là allowed currency của site).

## Reports và analytics (doanh thu được xử lý thế nào)
Các features trong unit:
- **A/B Testing**: thống kê phản ánh converted monetary value.
- **Active Data**: active data của customer/product phản ánh converted money values.
- **Reports & Dashboards**: có thể đổi realm currency setting để aggregated realm data hiển thị theo currency chọn.

Revenue conversion:
- Khi ghi nhận revenue event, B2C Commerce convert mọi monetary values về default currency của site theo exchange rate của ngày đó.
- Không có reporting riêng theo từng currency.
- Exchange rate service là internal, không xem được trong Business Manager hoặc API.

## Implement multi-currency (các bước + roles)
Checklist trong unit:

1) Configure allowed currencies — **Admin**
- Site tạo ra có 1 default currency; sau đó add allowed currencies.

2) Create price books per currency — **Merchandiser**
- Lookup giá theo session currency.
- Mỗi price book thuộc 1 currency.
- 3 currencies → ít nhất 3 price books.

3) Configure promotions per currency — **Merchandiser**
- Promotion có thể chỉ định currency.
- Nếu áp cho mọi currency (ví dụ 10% off) chọn currency cụ thể hoặc **All**.
- Promotion chỉ áp khi session currency match.

4) Configure payment methods per currency — **Merchandiser**
- Payment method có thể giới hạn currencies.
- Không chỉ định currency → mặc định accept mọi allowed currencies.
- Chỉ áp cho session currencies được chọn; có th�� cấu hình min/max ranges theo currency.

5) Configure shipping methods per currency — **Merchandiser**
- Shipping method có thể chỉ định allowed currency.
- Không chỉ định → dùng default currency.
- Chỉ áp khi session currency match.

6) Customize storefront chọn currency — **Developer**
- UI cho shopper chọn preferred currency.
- Dùng `dw.system.Session` API để set session currency.

7) Modify import process — **Developer**
- Điều chỉnh import logic theo yêu cầu multi-currency; tham chiếu documentation.

## Hiển thị giá nhiều currency trên PDP (API)
- Khác với multi-currency checkout: có thể show thêm giá theo currency khác trên PDP bằng:
    - `ProductPriceModel.getPriceBookPrice(String priceBookID)`
    - `ProductPriceModel.getPriceBookPrice(String priceBookID, Quantity quantity)`
- Hạn chế: tính năng này chỉ cho PDP; search sorting/refinements/price ranges và các price-related features khác vẫn giới hạn theo site currency.