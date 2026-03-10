# Configure Product Sets, Bundles, and Options
https://trailhead.salesforce.com/content/learn/modules/b2c-catalog-category-product/b2c-product-sets-bundles-options

## English

## Learning Objectives
- List strategies for using product sets and bundles.
- Explain the difference between a bundle and a product set.
- Describe how the searchable and online attributes work with product sets.
- Explain how bundles work with Salesforce B2C Commerce.
- Explain how options work with B2C Commerce.

## Why sets/bundles/options exist (merchandising strategy)
- Packaging products can increase average order value by presenting products together (often with a reduced effective price or convenience).
- B2C Commerce supports:
    - **product sets** (order separately or together)
    - **bundles** (single orderable product; included items not purchasable individually)
    - **options** (add-ons like warranty/setup/sharpening; not searchable/orderable alone)

## Product sets
- A product set can contain zero/one/many products and other product sets.
- A product set is owned by a specific catalog.
- You can assign it to multiple categories, with:
    - a primary category
    - classification category assignments
- You can position product sets alongside standard products in categories.
- Product sets can have recommendations.

### Searchable and Online behavior (important rule)
- A product set appears in search results only if it is `searchable` and `online`.
- A product set is considered online if:
    - the product set itself is online, and
    - at least one product in the set is online.
- Online/offline takes precedence over searchable.
- Search results return a product set regardless of included products’ searchable settings.
- If product set searchable is off, the set won’t be searchable.
- Searchable product set attributes are included in the search index.

### Create a product set (unit walkthrough)
1) Merchant Tools | Site | Products and Catalogs | **Product Sets**
2) New → General:
    - ID: `outfit-01`
    - Catalog: `cloud-kicks-usa-prod`
    - Online: Yes
    - Searchable: Yes
    - Name: `Running Outfit`
3) Apply
4) Categories tab:
    - Edit Categories → select categories (Sportswear and Sales) → Apply
    - Set primary category: Sportswear
5) Products tab:
    - Add base products (so shoppers can choose variation values)
    - Example: add `healthfit` and `plain-blue-shorts` and mark Online/Searchable

## Bundles
- A **bundle** is a separate product with:
    - its own SKU and price
    - specified included products in specified quantities
- Bundles are unaffected by the prices of the included products.
- Shoppers cannot purchase the included products individually.
- You can create a bundle within a bundle.
- Bundles are a single orderable product (unlike sets).

### Bundle example in unit
- Create component products first (example IDs in unit):
    - `pair-of-tennis-rackets-101`
    - `tennis-net-poles-lines`
- Make them online and searchable.
- Then create a bundle product (“Tennis for Beginners”) that includes those products.

## Options
- Product options:
    - have their own price and display name
    - do not have their own thumbnail images
    - are not searchable and cannot be ordered separately
    - appear on the product detail page as add-ons/selections
- You can:
    - Create `product` system object attributes to define options.
    - Create shared (global) product options.
    - Assign global options to products.
    - Create local options for products.

### Options example scenario
- Ice skates with a sharpening option (fee-based), where the selection depends on skater weight.
- Unit describes creating a base product (example `double-runner`) with variation products (sizes like 9, 11, 13), then offering an option for sharpening.

## Tiếng Việt

## Learning Objectives
- Liệt kê strategies dùng product sets và bundles.
- Giải thích khác nhau giữa bundle và product set.
- Mô tả searchable/online hoạt động thế nào với product sets.
- Giải thích bundles hoạt động thế nào trong B2C Commerce.
- Giải thích options hoạt động thế nào.

## Vì sao cần sets/bundles/options (merchandising)
- Gom sản phẩm thành gói giúp tăng AOV bằng cách trình bày sản phẩm cùng nhau (giảm giá/tiện lợi).
- B2C Commerce hỗ trợ:
    - **product sets** (có thể mua lẻ hoặc mua cùng)
    - **bundles** (1 sản phẩm orderable; items bên trong không mua lẻ)
    - **options** (add-ons như warranty/setup/sharpening; không order/search riêng)

## Product sets
- Có thể chứa products và product sets khác.
- Thuộc ownership của một catalog.
- Assign nhiều categories với primary category + classification categories.
- Position trong category cùng standard products; có recommendations.

### Rule searchable + online
- Product set chỉ lên search results khi `searchable` và `online`.
- Considered online khi:
    - set online, và
    - ít nhất 1 product trong set online.
- Online/offline ưu tiên hơn searchable.
- Search results trả về product set không phụ thuộc included products searchable.
- Tắt product set searchable → set không searchable.
- Searchable product set attributes nằm trong search index.

### Tạo product set (walkthrough)
- Product Sets → New → ID `outfit-01` → catalog `cloud-kicks-usa-prod` → Online/Searchable Yes → name `Running Outfit` → Apply
- Categories tab: chọn Sportswear + Sales, primary Sportswear
- Products tab: add base products `healthfit`, `plain-blue-shorts` và set Online/Searchable.

## Bundles
- **Bundle** là sản phẩm riêng có SKU + price riêng.
- Giá bundle không phụ thuộc giá items bên trong.
- Items trong bundle không mua lẻ.
- Có thể bundle trong bundle.
- Bundle là single orderable product.

### Ví dụ bundle
- Tạo products `pair-of-tennis-rackets-101`, `tennis-net-poles-lines` online/searchable, rồi tạo bundle “Tennis for Beginners” chứa chúng.

## Options
- Options có price + display name riêng, không có thumbnail riêng.
- Không searchable, không order riêng; hiển thị ở PDP như add-on.
- Có thể tạo options bằng:
    - product system object attributes
    - shared (global) options + assign cho products
    - local options theo product

### Ví dụ options
- Ice skates + tùy chọn sharpening theo phí; unit mô tả tạo base product `double-runner` với variation products (size 9/11/13) và cung cấp option.