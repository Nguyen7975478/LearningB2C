# Explore Discount Types and Promotion Controls
https://trailhead.salesforce.com/content/learn/modules/b2c-campaigns-and-promotions/b2c-explore-discount-types-promotion-controls

## English

## Learning Objectives
- List three discount types.
- Explain where you can go to learn about discount types and available discounts.
- List three ways you can control who gets the deal.
- Explain the compatibility rules.
- List three steps in the order of promotion processing.

## What promotions are (and where they run)
- B2C Commerce promotions specify discounts/offers.
- Promotions run within a **campaign** or an **A/B test**.
- Promotion configuration defines promotion type, conditions, and discounts.
- Promotions can be extended with custom attributes.
- Promotions can be time-sensitive, targeted, or perpetual (example: free shipping to build loyalty).
- The same promotion can be assigned to multiple campaigns.

## How to think about defining a promotion (unit’s 4 questions)
For each promotion, ask:
1) Who gets the deal?
2) What’s the discount?
3) How do shoppers get the deal?
4) Are there exclusions?

## Discount types (examples shown)
The unit shows a sampling (and points to “Campaigns and Promotions” in the Infocenter/Help for the complete list).

### Buy X for Total
- Shopper buys a minimum number of qualifying products for a total fixed price (example: buy 3 discounted products for US$30).

### Buy X/Get Y
- Shopper buys minimum qualifying products to qualify for a discount on specified extra products (example: buy 2 jeans, get a 3rd pair 50% off).
- Discount options listed for this discount type include:
    - Percent off, Amount off, Fixed price, Price from price book, Free

### Without qualifying products
- Shopper does not need a qualifying product to get the discount (discount applies directly to discounted products).
- Discount options listed include:
    - Percent off, Amount off, Fixed price, Price from price book,
    - Percent off product options, Bonus products, Choice of bonus products,
    - Fixed price shipping, Free shipping

Note: Some discount types (example: choice of bonus products) require additional storefront application code.

## Ways to control promotions (“Control Those Promotions”)
The unit lists the main control mechanisms:
- Tiered discounts
- Compatibility rules
- Maximum application
- Qualifiers
- Globally excluded products
- Qualifying and discounted products

### Tiered discounts
- Discount increases as shopper buys more/spends more (example: 10% off $50, 15% off $100, 20% off $150+).

### Compatibility rules (Exclusivity + Rank)
#### Exclusivity
- **NO**: can combine with any promotion (default)
- **CLASS**: can’t combine with another promotion of the same class
- **GLOBAL**: can’t combine with any promotion
  Example: if registered shoppers should get 20% off instead of stacking with a 10% off promotion, use exclusivity to prevent double discounts.

#### Rank
- Rank determines precedence; promotions are applied from highest to lowest rank.
- Rank range described: 10 highest, 100 lowest.
- By default, promotions have no rank (optional).

### Maximum application
- Limits how many times a promotion can be used in a single order (example: limit bonus baseball count even if shopper buys multiple qualifying shoes).

### Globally excluded products
- Exclude products within a promotion, or exclude products globally from all promotions to protect low-margin items.

### Qualifying vs discounted products
- You can define a set of **qualifying products** and a (same or different) set of **discounted products**.
- Example: buy Brand‑Y T‑shirt (qualifying) and get matching shorts discounted.

## Which discounts apply? (promotion processing order)
B2C Commerce applies priority rules; some are customizable (exclusivity, rank), most are fixed.

### Discount processing by class (cart calculation steps)
- Calculate product promotions
- Calculate order promotions based on merchandise total
- Prorate order-level discounts across all products
- Calculate shipping promotions

### When multiple promotions apply (overall order)
1) External API-generated promotions
2) Class (product, order, shipping)
3) Exclusivity (customizable)
4) Rank (customizable)
5) Discount type and value (best value precedence), in this order:
    1. Fixed price
    2. Total fixed price
    3. Free
    4. Price book price
    5. Amount-off
    6. Percent-off
    7. Bonus-product
    8. Choice of bonus products
    9. Free product-shipping
    10. Fixed price product-shipping
6) Maximum application

## Tiếng Việt

## Learning Objectives
- Liệt kê 3 discount types.
- Nêu nơi xem đầy đủ discount types và available discounts.
- Liệt kê 3 cách control “ai nhận deal”.
- Giải thích compatibility rules.
- Liệt kê 3 bước trong order của promotion processing.

## Promotions là gì (và chạy ở đâu)
- Promotions là discounts/offers trong B2C Commerce.
- Promotions chạy trong **campaign** hoặc **A/B test**.
- Promotion configuration định nghĩa type/conditions/discounts; có thể extend bằng custom attributes.
- Promotion có thể time-sensitive, targeted, hoặc perpetual (ví dụ free shipping).
- Một promotion có thể gán cho nhiều campaigns.

## 4 câu hỏi để định nghĩa promotion (unit)
1) Ai nhận deal?
2) Discount là gì?
3) Shopper làm gì để nhận deal?
4) Có exclusions không?

## Discount types (ví dụ trong unit)
(Unit chỉ đưa sampling và chỉ tới Help/Infocenter để xem full list)

### Buy X for Total
- Mua tối thiểu N qualifying products với tổng giá cố định (ví dụ mua 3 món tổng US$30).

### Buy X/Get Y
- Mua tối thiểu qualifying products để được discount cho extra products (ví dụ mua 2 jeans, cái thứ 3 50% off).
- Discounts có thể: Percent off, Amount off, Fixed price, Price from price book, Free

### Without qualifying products
- Không cần qualifying product; discount áp trực tiếp lên discounted products.
- Discounts: Percent off, Amount off, Fixed price, Price from price book,
  Percent off product options, Bonus products, Choice of bonus products,
  Fixed price shipping, Free shipping

Note: một số discount types (choice of bonus products) cần thêm code trong storefront app.

## Control promotions (các cơ chế)
- Tiered discounts
- Compatibility rules
- Maximum application
- Qualifiers
- Globally excluded products
- Qualifying and discounted products

### Tiered discounts
- Discount tăng theo số lượng/chi tiêu (ví dụ 10% ở $50, 15% ở $100, 20% ở $150+).

### Compatibility rules (Exclusivity + Rank)
#### Exclusivity
- **NO**: combine được với mọi promotion (default)
- **CLASS**: không combine với promotion cùng class
- **GLOBAL**: không combine với bất kỳ promotion nào

#### Rank
- Xác định ưu tiên; apply từ rank cao xuống thấp.
- Range: 10 cao nhất, 100 thấp nhất.
- Default: không có rank (optional).

### Maximum application
- Giới hạn số lần apply trong một order (ví dụ bonus baseball chỉ 1 cái dù mua nhiều shoes).

### Globally excluded products
- Exclude product trong từng promotion hoặc exclude globally khỏi tất cả promotions.

### Qualifying vs discounted products
- Tách **qualifying products** và **discounted products** (có thể giống hoặc khác).
- Ví dụ: mua T‑shirt (qualifying) thì shorts được discount.

## Promotion processing order (khi nhiều promotions áp dụng)
### Theo class (cart calculation)
- Tính product promotions
- Tính order promotions theo merchandise total
- Prorate order-level discounts
- Tính shipping promotions

### Overall order khi nhiều promotions áp dụng
1) External API-generated promotions
2) Class (product, order, shipping)
3) Exclusivity
4) Rank
5) Discount type/value theo thứ tự ưu tiên:
   Fixed price → Total fixed price → Free → Price book price → Amount-off → Percent-off →
   Bonus-product → Choice of bonus products → Free product-shipping → Fixed price product-shipping
6) Maximum application