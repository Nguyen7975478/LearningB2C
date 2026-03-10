# Explore Sorting Rule Strategies
https://trailhead.salesforce.com/content/learn/modules/b2c-storefront-sorting-rules/b2c-sorting-rule-strategies

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe common sorting rule strategies you can use for sale, new arrivals, and top sellers sorting results.
- Explain how dynamic attributes work.
- Explain how to use manual sorting rules to optimize the sort order on the catalog and search results pages.
- Explain how product attributes can help you customize your search results.
- State how the Storefront Toolkit helps with dynamic sorting.

## Strategy planning (what Brandon optimizes for)
The unit groups strategies around four result types:
- **New Arrivals**: sell exciting new products
- **Top Sellers**: highlight what other shoppers like most
- **Search**: show shoppers what they want to see
- **Items On Sale**: drive end-of-season clearance interest

## Manual sorting rules (manual attributes must be activated first)
Manual attributes:
- `category position`
- `search placement`
- `search rank`
  Important: These attributes can only be used in a sorting rule **after** they are activated manually in Business Manager.

### Category Position strategy (exact ordering within a category)
To use category position in a sorting rule, you must:
1) Assign category positions to products within a category.
2) Create a sorting rule that includes the `category position` attribute.

Walkthrough start (as shown in unit):
1) Business Manager → App Launcher → Merchant Tools | Products and Catalogs | Catalogs
2) Select catalog and a category: `mens`
3) Select subcategories: `mens-clothing` and `mens-clothing-shorts`
   (Then assign ordering positions so the rule can sort exactly as desired.)

## Dynamic attributes (what they are)
- **Dynamic attributes** are custom combinations/expressions built from underlying attributes.
- They enable more advanced strategies (for example blending performance signals with catalog attributes).
- Dynamic attributes can be used to power storefront sorting options and personalization strategies.

## Product attributes (customize relevance)
- Product system object attributes can be used in sorting rules to shape results (brand, price, flags like new/on sale, margin signals, etc.).
- Strategy idea: use product attributes early to emphasize merchandising intent, then break ties with performance signals (active data).

## Storefront Toolkit (why it’s useful)
- Storefront Toolkit helps with dynamic sorting by letting you inspect search results:
    - see which sorting rule was applied,
    - see the criteria in the rule,
    - see per-product criteria values.
- This is critical when tuning dynamic attributes and validating that the storefront experience matches the intended strategy.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả các sorting rule strategies phổ biến cho sale/new arrivals/top sellers/search.
- Giải thích dynamic attributes hoạt động thế nào.
- Giải thích cách dùng manual sorting rules tối ưu thứ tự trên catalog/search results.
- Giải thích product attributes giúp customize search results thế nào.
- Nêu Storefront Toolkit hỗ trợ dynamic sorting ra sao.

## Lập chiến lược (4 nhóm kết quả)
- **New Arrivals**: đẩy sản phẩm mới
- **Top Sellers**: nổi bật sản phẩm được nhiều người mua/thích
- **Search**: đúng intent của shopper
- **Items On Sale**: thúc đẩy clearance/end-of-season

## Manual sorting rules (phải activate trước)
Manual attributes:
- `category position`
- `search placement`
- `search rank`
  Quan trọng: chỉ dùng được trong sorting rule **sau khi** activate thủ công trong Business Manager.

### Category Position (đặt thứ tự chính xác theo category)
Để dùng category position:
1) Gán category position cho products trong category.
2) Tạo sorting rule có `category position`.

Walkthrough phần đầu (trong unit):
- Merchant Tools | Products and Catalogs | Catalogs → chọn category `mens` → subcategories `mens-clothing`, `mens-clothing-shorts` → gán positions.

## Dynamic attributes
- **Dynamic attributes** là tổ hợp/biểu thức custom dựa trên các attributes khác.
- Dùng cho chiến lược nâng cao (kết hợp tín hiệu performance với catalog data).
- Thường dùng để tạo storefront sorting options và hỗ trợ personalization.

## Product attributes (customize relevance)
- Dùng product system object attributes trong rules (brand, price, new/on sale flags, margin…).
- Chiến lược: dùng product attributes để phản ánh merchandising intent, rồi break ties bằng active data.

## Storefront Toolkit
- Toolkit giúp inspect search results:
    - sorting rule nào được dùng,
    - criteria trong rule,
    - giá trị criteria của từng product.
- Rất cần khi tuning dynamic attributes.