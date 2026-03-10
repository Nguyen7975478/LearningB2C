# Configure Variation Groups and Slicing
https://trailhead.salesforce.com/content/learn/modules/b2c-catalog-category-product/b2c-configure-variation-groups-slicing

## English

## Learning Objectives
- Explain the difference between variation display via **variation groups** and **slicing**.
- Describe how variation groups work with base and variation products.
- Explain how variation groups work with categories.
- Explain how B2C Commerce handles attribute property inheritance for variation groups.
- Explain how search results appear when slicing is enabled.

## The shopper experience problem (display together vs separate)
- Variation products can be displayed:
    - As one item with swatches that represent variations (default style).
    - Or as multiple items (each variation) in search/category results.
- The image representing a product result is the **swatch** (small color/texture selection image).

## Variation groups vs slicing (capability comparison)
- **Variation groups**
    - Let you define multiple groups within a base product.
    - Each group represents a specific combination subset of variation attributes (color/size/width/length).
    - More accurate control of search results.
- **Slicing**
    - Controls whether variation products appear as separate products or as one product with swatches.
    - You can slice on any variation attribute, but only one attribute at a time (color or size or width).

## Interaction rule
- If variation groups exist for a base product, B2C Commerce disables slicing for that product (including slicing defined for variation attributes or overridden via category assignments).
- Slicing can still be used for other products that don’t have variation groups.

## Variation groups: facts and constraints
- Each variant in a variation group must be an **orderable** product.
- A variation group belongs to exactly one base product, but a base product can have multiple variation groups.
- Variation groups have:
    - One product image (with swatches representing products in the group)
    - Inventory derived from SKUs in the group, yet can have their own SKU
- They are mutually exclusive from other product types (product set, bundle, base product, standard product), but can participate in a set/bundled product.
- You can assign them to categories and promotions; they can have price adjustments via promotions.
- You cannot assign prices to variation groups in Business Manager (similar to product sets).
- A variation group can include only one value per variation attribute (e.g., `color: green` only, not green+red), but can include multiple attributes (e.g., `color: green` and `size: small`).

## Example variation set (unit table)
The unit provides a base product with variations (HealthFit sweatshirt) across color and size, then defines example variation groups:
- All green sweatshirts of any size (`color: green`)
- All small sweatshirts of any color (`size: small`)

## Create a variation group (unit workflow highlights)
1) Merchant Tools | Site | Products and Catalogs | **Products**
2) Search and open base product (example: `healthfit-sweatshirt`)
3) Click **Lock**
4) Variations tab:
    - Add variation products and set values for all variation attributes (color, size)
    - Then create variation group entries based on chosen attribute-value subsets

## Slicing configuration (two scenarios in unit)
### Scenario A: slice by color globally (all categories/search)
1) Merchant Tools | Site | Products and Catalogs | **Variation Attributes**
2) Select catalog (example: `cloud-kicks-usa`)
3) Open attribute `color / color`
4) Select **Slicing Attribute**
5) Apply
6) **Rebuild the product index**
   Result: searching/navigating shows each variation as a separate slice with its own swatch.

### Scenario B: mixed behavior via category override
- Keep single item (base with swatches) for search/one category, but slice in another category.
  Steps:
1) Products → open base product `healthfit-sweatshirt` → Lock
2) Categories tab → for a category (example Sportswear) click Details
3) Variation Values tab → for color:
    - Deselect Use Default
    - Set Slicing Attribute to Yes
4) Apply
5) Rebuild product index
   Result:
- Search or Sales category shows one result (base product swatch).
- Sportswear/Kids category shows sliced variations.

## Tiếng Việt

## Learning Objectives
- Giải thích khác nhau giữa hiển thị variations bằng **variation groups** và **slicing**.
- Mô tả variation groups làm việc với base/variation products.
- Giải thích variation groups liên quan categories.
- Giải thích inheritance của attribute properties cho variation groups.
- Giải thích search results hiển thị thế nào khi bật slicing.

## Vấn đề trải nghiệm (gộp hay tách)
- Variations có thể hiển thị:
    - 1 item + swatches cho variations
    - hoặc mỗi variation là 1 item riêng trong search/category results
- Ảnh nhỏ đại diện selection là **swatch**.

## Variation groups vs slicing
- **Variation groups**: tạo nhiều nhóm trong base product, mỗi nhóm đại diện một subset tổ hợp attributes (color/size/width/length), kiểm soát search chính xác hơn.
- **Slicing**: quyết định variations hiển thị tách hay gộp; slice theo 1 variation attribute tại 1 thời điểm.

## Quy tắc tương tác
- Nếu base product có variation groups, B2C Commerce disable slicing cho product đó.
- Các product khác vẫn có thể dùng slicing.

## Facts/constraints của variation groups
- Variants trong variation group phải **orderable**.
- Variation group thuộc đúng 1 base product; base product có nhiều variation groups.
- Có 1 product image + swatches; inventory lấy từ SKUs trong group, có thể có SKU riêng.
- Mutually exclusive với product set/bundle/base/standard, nhưng có thể nằm trong set/bundle.
- Assign được vào categories và promotions; có price adjustments qua promotions.
- Không assign prices cho variation groups trong Business Manager.
- Mỗi attribute chỉ 1 value trong group (color: green), nhưng có thể nhiều attributes (color+size).

## Ví dụ variation groups
- `color: green` (mọi size)
- `size: small` (mọi color)

## Tạo variation group (workflow)
- Products → mở base product → Lock → Variations tab → tạo variation products + values → tạo variation groups theo subset.

## Configure slicing (2 scenario)
### A: slice global theo color
- Variation Attributes → mở color → chọn Slicing Attribute → Apply → Rebuild product index.

### B: override theo category
- Products → base product → Categories → Details → Variation Values → set slicing cho color → Apply → Rebuild index.
  Kết quả: một category gộp, một category tách.