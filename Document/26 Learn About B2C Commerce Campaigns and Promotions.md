# Learn About B2C Commerce Campaigns and Promotions
https://trailhead.salesforce.com/content/learn/modules/cc-digital-merchandising/digital-campaigns-and-promotions

## English

### Learning Objectives
- Describe how campaigns relate to promotions.
- List the main types of promotions you can configure.
- List the Salesforce B2C Commerce promotion qualifiers.
- List the ways you can control promotions.

### Core relationship: campaigns, promotions, qualifiers
- Discounts are configured as **promotions** in Business Manager.
- Multiple promotions are grouped into **campaigns**.
- Promotions are triggered by **qualifiers** (example: a coupon emailed to shoppers).

### Campaigns (what they are + scheduling)
- A **campaign** is a collection of scheduled experiences.
- Experience types the unit lists:
  - **Promotion**
  - **Slot configuration** (content placements that can trigger actions; example banner linking to search results)
  - **Sorting rule**
- Scheduling controls:
  - Campaigns can have start/end dates or run continually.
  - Enable/disable with one setting.
  - Promotions can share the campaign schedule or have independent schedules within the campaign period (series of promotions).

### Promotions (rule model)
- A promotion is defined by answering:
  1) Promotion class
  2) Discount type
  3) Discount
- **Promotion classes**:
  - **Product**
  - **Order**
  - **Shipping**

### Discount types (product promotion matrix)
Product promotion discount types listed:
- Without qualifying products
- With an amount of qualifying products
- With a number of qualifying products
- With a combination of qualifying products
- **Buy X/Get Y**
- **Buy X and Y/Get Z**
- **Buy X for Total**
  Order promotion configuration:
- Qualify by amount spent, number of products, or combination of products.
- Discounts: percent off, amount off, bonus products, choice of bonus products (list or rule).
  Shipping promotion configuration:
- Based on the order or on individual products/product combinations.

### Discounts you can give (list)
- Percent off
- Amount off
- Fixed price
- Price from a certain price book
- Percent off product options
- Bonus products
- Choice of bonus products
- Fixed price shipping
- Free shipping

### Qualifiers (3 types)
- **Coupons**
  - Single-use or multiple-use coupons.
  - Multi-use “while supplies last.”
  - System-generated coupons that generate coupon codes.
- **Customer Groups**
  - Predefined: Everyone, Registered customers, Unregistered customers.
  - Custom groups: list-based or criteria-based (visit data, order value, address).
- **Source Codes**
  - Direct shoppers to landing pages/featured pages/category lists/URLs.
  - Can be distributed via print catalogs (manual entry) or affiliate redirect links (cookie qualifier code).

### Other ways to control promotions (prevent stacking)
- **Tiered discounts**: discount increases as shoppers buy more/spend more (quantity pricing example table).
- **Rank and Exclusivity**:
  - Rank controls precedence (smaller number = higher rank).
  - **Exclusivity**: **NO**, **CLASS**, **GLOBAL**.
  - Global exclusive prevents combining with any other promotions.
- Exclusions:
  - Exclude products from specific promotions or from all promotions.
  - Define qualifying products vs discounted products separately.

### What happens when multiple promotions apply (application order)
B2C Commerce applies promotions in a defined order:
1) Class (product → order → shipping)
2) Exclusivity Type
3) Rank
4) Discount Type and Value
5) Maximum Application

## Tiếng Việt

### Learning Objectives
- Mô tả campaigns liên quan promotions thế nào.
- Liệt kê các promotion types chính có thể cấu hình.
- Liệt kê Salesforce B2C Commerce promotion qualifiers.
- Liệt kê các cách kiểm soát promotions.

### Quan hệ cốt lõi: campaigns, promotions, qualifiers
- Discount được cấu hình thành **promotions** trong Business Manager.
- Nhiều promotions được nhóm vào **campaigns**.
- Promotions được trigger bởi **qualifiers** (ví dụ coupon gửi qua email).

### Campaigns (khái niệm + scheduling)
- **Campaign** là tập các scheduled experiences.
- Experience types trong unit:
  - **Promotion**
  - **Slot configuration** (content placements có thể trigger action; ví dụ banner dẫn tới search results)
  - **Sorting rule**
- Scheduling:
  - Có start/end dates hoặc chạy liên tục.
  - Enable/disable bằng một setting.
  - Promotions có thể dùng lịch campaign hoặc có lịch riêng trong campaign period (chuỗi promotions).

### Promotions (mô hình rule)
- Promotion được xác định bằng 3 câu hỏi:
  1) Promotion class
  2) Discount type
  3) Discount
- **Promotion classes**:
  - **Product**
  - **Order**
  - **Shipping**

### Discount types (product promotion matrix)
Product promotion discount types:
- Without qualifying products
- With an amount of qualifying products
- With a number of qualifying products
- With a combination of qualifying products
- **Buy X/Get Y**
- **Buy X and Y/Get Z**
- **Buy X for Total**
  Order promotions:
- Qualify theo amount spent / number / combination.
- Discounts: percent off, amount off, bonus products, choice of bonus products (list/rule).
  Shipping promotions:
- Dựa trên order hoặc products/product combinations.

### Discounts có thể cấu hình (list)
- Percent off
- Amount off
- Fixed price
- Price from a certain price book
- Percent off product options
- Bonus products
- Choice of bonus products
- Fixed price shipping
- Free shipping

### Qualifiers (3 loại)
- **Coupons**
  - Single-use hoặc multiple-use.
  - Multi-use “while supplies last”.
  - System-generated coupons tạo coupon codes tự động.
- **Customer Groups**
  - Predefined: Everyone, Registered customers, Unregistered customers.
  - Custom groups: theo list hoặc theo criteria (visit data, order value, address).
- **Source Codes**
  - Điều hướng shoppers đến landing page/featured page/category list/URL.
  - Có thể phát qua print catalog (nhập tay) hoặc affiliate redirect link (cookie qualifier code).

### Các cách khác để control promotions (tránh stacking)
- **Tiered discounts**: discount tăng khi mua nhiều/spend nhiều (ví dụ bảng quantity/unit price).
- **Rank and Exclusivity**:
  - Rank: số nhỏ hơn = rank cao hơn.
  - **Exclusivity**: **NO**, **CLASS**, **GLOBAL**.
  - Global exclusive ngăn combine với promotions khác.
- Exclusions:
  - Exclude products khỏi promotions cụ thể hoặc khỏi tất cả promotions.
  - Tách qualifying products và discounted products.

### Khi nhiều promotions áp dụng (application order)
Thứ tự apply trong B2C Commerce:
1) Class (product → order → shipping)
2) Exclusivity Type
3) Rank
4) Discount Type and Value
5) Maximum Application