# B2C Commerce Ordering
https://help.salesforce.com/s/articleView?id=cc.b2c_ordering.htm&type=5

## English

## What “Ordering” means in B2C Commerce (conceptual model)
- In Salesforce **B2C Commerce**, **Ordering** is the collection of storefront + back-office capabilities that manage the lifecycle from:
    - **basket/cart** creation,
    - to **checkout**,
    - to **order** creation,
    - to **order status** progression,
    - to customer service operations (search, view, edit, cancel where allowed).
- Ordering also connects to the broader operational ecosystem:
    - payment authorization/processing,
    - taxation and shipping calculation,
    - promotions and coupons,
    - inventory availability,
    - fulfillment/export integrations (depending on your architecture).

## Core entities and why they matter (to understand the ideas)
### Basket (Cart)
- A **basket** is the pre-order container that holds:
    - products/line items,
    - quantities,
    - promotions/coupons,
    - shipping method selections,
    - payment instruments (in-progress),
    - addresses (in-progress).
- Why it matters:
    - everything during checkout is being calculated and validated on the basket before it becomes an order.

### Order
- An **order** is the persisted record created after checkout conditions are satisfied and submission occurs.
- Why it matters:
    - once created, order processing (export/fulfillment, customer service changes, payment capture/settlement) is governed by order status rules and integration flows.

### Customer (Registered vs Guest)
- Ordering supports both:
    - registered customers (profile + order history),
    - guest checkout (order exists, but customer isn’t a full registered profile).
- Why it matters:
    - impacts customer service flows, lookup, and what data is retained.

## Typical order flow (high-level lifecycle you should internalize)
Even though implementations differ by cartridge/architecture, the ordering logic usually follows:

1) Shopper builds basket
- add items, select variations/options, apply promotions/coupons.

2) Checkout validations
- shipping address, shipping method, taxes, payment setup.
- order totals are calculated repeatedly during changes.

3) Order creation + payment authorization/handling
- order is created, payment is authorized/processed depending on payment method.
- some payment methods are synchronous (on-site) while others can be asynchronous (redirect and return).

4) Order placement and post-processing
- after placement, the system proceeds to:
    - export/fulfillment integration,
    - inventory updates,
    - confirmation communications,
    - downstream OMS processes (if integrated).

Why this matters:
- Understanding where an order is “created” vs “placed” helps when troubleshooting payment issues, abandoned redirects, and customer service edits.

## Order statuses and state transitions (how to think about them)
- B2C Commerce uses defined **order statuses** to manage where an order is in its lifecycle.
- Why it matters:
    - integrations (export jobs, OMS connectors) often trigger based on specific status changes.
    - customer service actions (edit/cancel) are usually constrained by status.

Practical understanding:
- Ordering is not a single state; it is a controlled workflow.

## Ordering configuration surface (where merchants/admins control behavior)
B2C Commerce ordering behavior is influenced by configuration such as **Order Preferences** and other site-level settings in Business Manager.

Key idea:
- Many ordering behaviors are “configuration + hooks”, not hard-coded:
    - configuration defines what is allowed,
    - hooks/scripts define how your business rules and integrations run.

## Ordering and customer service operations (why CSR tooling matters)
- Ordering isn’t only “storefront checkout”.
- Merchants also need back-office operations to:
    - find orders,
    - view details,
    - support customers (address correction, order lookup, notes),
    - and sometimes create orders on behalf of customers (depending on your tools like Customer Service Center).

## Tiếng Việt

## “Ordering” trong B2C Commerce là gì (mô hình khái niệm)
- Trong Salesforce **B2C Commerce**, **Ordering** là tập hợp khả năng storefront + back-office để quản lý vòng đời:
    - tạo **basket/cart**,
    - **checkout**,
    - tạo **order**,
    - tiến trình **order status**,
    - và nghiệp vụ customer service (search/view/edit/cancel theo quyền).
- Ordering còn gắn với hệ thống vận hành:
    - payment authorization/processing,
    - tax/shipping calculation,
    - promotions/coupons,
    - inventory availability,
    - fulfillment/export/OMS integrations (tùy kiến trúc).

## Các thực thể lõi và “ý nghĩa” (để hiểu đúng ý)
### Basket (Cart)
- **Basket** là container trước khi thành order, gồm:
    - line items, quantity,
    - promotions/coupons,
    - shipping selections,
    - payment instruments (đang cấu hình),
    - addresses (đang cấu hình).
- Ý nghĩa:
    - checkout thực chất là liên tục validate/calculate trên basket trước khi “chốt” thành order.

### Order
- **Order** là bản ghi persisted sau khi thỏa điều kiện checkout và submit.
- Ý nghĩa:
    - từ đây các xử lý export/fulfillment/payment capture/customer service edits… bị chi phối bởi trạng thái và quy trình.

### Customer (Registered vs Guest)
- Hỗ trợ registered và guest.
- Ý nghĩa:
    - ảnh hưởng luồng customer service, lookup và dữ liệu lưu trữ.

## Order flow điển hình (vòng đời bạn cần nắm)
1) Shopper build basket (add items/variations, apply promo/coupon)
2) Checkout validations (address, shipping method, taxes, payment setup; totals được recalc liên tục)
3) Order creation + payment authorization/handling (có synchronous hoặc asynchronous redirect)
4) Order placement + post-processing (export/fulfillment, inventory update, confirmation, OMS processes)

Ý nghĩa:
- Phân biệt “created” và “placed” giúp debug payment/redirect/CSR edits.

## Order statuses (cách hiểu)
- B2C Commerce dùng **order statuses** để quản lý trạng thái trong lifecycle.
- Ý nghĩa:
    - integration thường trigger theo status,
    - CSR actions thường bị giới hạn theo status.

## Cấu hình Ordering (nơi điều khiển hành vi)
- Ordering bị ảnh hưởng bởi **Order Preferences** và site settings trong Business Manager.
- Ý nghĩa:
    - nhiều hành vi là “configuration + hooks”, không phải code cứng.

## Ordering và nghiệp vụ customer service
- Ordering không chỉ checkout; còn cần back-office để find/view/support customer, và đôi khi tạo order thay khách (tùy tool như Customer Service Center).