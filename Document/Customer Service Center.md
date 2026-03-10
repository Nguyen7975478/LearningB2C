# Customer Service Center
https://developer.salesforce.com/docs/commerce/b2c-commerce/guide/b2c-customer-service-center.html

## English

## What Customer Service Center (CSC) is
- **Customer Service Center (CSC)** is a B2C Commerce module that enables customer service agents to:
    - create and search for **orders**,
    - create and search for **customers**,
    - view order data and (some) customer data,
    - and modify customer/order information depending on permissions and customization.
- CSC is designed to support “assisted service” workflows (agents helping shoppers).

## Access model and prerequisites (critical operational points)
### Turned off by default
- CSC is **turned off by default**.

### Permissions required for all users
- All users (including administrators) must have **permissions configured in Business Manager** to use CSC.

Why this matters:
- Most “CSC doesn’t show up” issues are permission/setup issues, not code issues.

## What an agent can do in CSC (capabilities list)
Depending on permissions, CSC lets an agent:

### Orders
- **Search for orders**
- **Create orders**, including:
    - adjust prices on individual items, shipping cost, or entire orders
    - enter coupon code for a new order
    - specify shipping and billing addresses
    - search for products and refine quantities

### Customers
- **Search for customers**
- **Create customers**
- **Create an order for a customer**
- **View a customer’s orders**
- **View and modify customer data**

## CSC customization (business logic + UI) — what is customizable
CSC can be customized to meet business needs in two main dimensions:

### 1) Business logic customization (Shop API hooks)
- Customize business logic using **Shop API hooks**.
  Examples (from the guide’s intent):
- payment processing variations
- hosted payment page behavior

### 2) UI customization (JSON-based CSC UI configuration)
- Customize areas of the CSC user interface by modifying **JSON configuration** in Business Manager.

Why this matters:
- CSC is a productized UI, but you still have controlled customization points.

## Reuse existing B2C Commerce integrations (Soap APIs + OCAPI hooks)
CSC can reuse existing platform capabilities and integrations, including:
- **B2C Commerce SOAP APIs**
- **Open Commerce API (OCAPI) hooks**
  Examples of integration reuse:
- Payment Service Providers (PSPs)
- Order Calculation logic

Interpretation:
- CSC isn’t an isolated system; it participates in your existing commerce integration landscape.

## Key concept: “same calculation routines” (pricing/taxes/shipping/promotions)
- CSC uses the same calculation routines used by B2C Commerce for:
    - pricing
    - taxes
    - shipping charges
    - promotions

Why this matters:
- It reduces mismatch risk between agent-created orders and storefront-created orders (totals should align if hooks/config are consistent).

## Typical navigation path (where agents start CSC)
- Agents access CSC via Business Manager navigation (the broader documentation set commonly references):
    - Merchant Tools > site > Ordering > Customer Service Center
      (Your exact menu availability depends on permissions.)

## Practical usage patterns (how CSC fits Ordering)
CSC supports operational use-cases such as:
- locating an order by multiple identifiers (order number, customer data)
- editing customer information (as permitted)
- placing an order on behalf of a customer
- adding internal notes (agent-only context) and tracking assisted-sales activity

## Tiếng Việt

## Customer Service Center (CSC) là gì
- **Customer Service Center (CSC)** là một module của B2C Commerce giúp customer service agents:
    - tạo và tìm **orders**,
    - tạo và tìm **customers**,
    - xem order data và một phần customer data,
    - chỉnh sửa dữ liệu tùy theo permissions và customization.
- CSC phục vụ workflow “assisted service” (agent hỗ trợ shopper).

## Điều kiện truy cập (các điểm vận hành quan trọng)
### Mặc định tắt
- CSC **turned off by default**.

### Bắt buộc có permissions
- Mọi user (kể cả admin) phải được set **permissions trong Business Manager** mới dùng được CSC.

Ý nghĩa:
- Lỗi “không thấy CSC” thường do permissions/setup, không phải do code.

## Agent làm được gì trong CSC (capabilities)
Tùy permission, agent có thể:

### Orders
- **Search orders**
- **Create orders**, gồm:
    - adjust giá item/shipping/toàn đơn
    - nhập coupon code
    - nhập shipping/billing addresses
    - search products và chỉnh quantity

### Customers
- **Search customers**
- **Create customers**
- **Create an order for a customer**
- **View customer’s orders**
- **View/modify customer data**

## Customization (business logic + UI)
CSC tùy biến theo 2 hướng:

### 1) Business logic (Shop API hooks)
- Tùy biến logic qua **Shop API hooks** (payment, hosted payment pages…).

### 2) UI (JSON config trong Business Manager)
- Tùy biến UI bằng **JSON configuration** trong Business Manager.

Ý nghĩa:
- CSC là UI có sẵn nhưng có điểm mở rộng/kiểm soát rõ ràng.

## Tái sử dụng integrations (SOAP APIs + OCAPI hooks)
CSC có thể dùng lại integrations:
- **SOAP APIs**
- **OCAPI hooks**
  Ví dụ: PSPs, Order Calculation.

## CSC dùng cùng calculation routines
- CSC dùng cùng routine cho pricing/taxes/shipping/promotions như storefront.
  Ý nghĩa:
- Giảm lệch totals giữa order agent tạo và order storefront tạo (nếu hooks/config nhất quán).

## Path truy cập CSC (thực tế vận hành)
- Thường truy cập: Merchant Tools > site > Ordering > Customer Service Center (tùy permission).

## CSC nằm ở đâu trong bức tranh Ordering
- CSC hỗ trợ: tìm order theo nhiều tiêu chí, chỉnh customer data (theo quyền), đặt order thay khách, ghi chú nội bộ, tracking assisted sales.