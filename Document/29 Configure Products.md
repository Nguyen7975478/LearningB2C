# Configure Products
https://trailhead.salesforce.com/content/learn/modules/b2c-catalog-category-product/b2c-configure-products

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe the Salesforce B2C Commerce product types.
- Explain how product attributes relate to products and appear on the storefront.
- Describe how base and variation products relate.
- Explain how products relate to categories.

## Products (what a “product” can be)
- A product is what merchandisers sell.
- Products can be:
    - physical objects
    - services (example: assembly)
    - options (example: service contracts)

## Salesforce B2C Commerce product types (7)
The unit lists:
1) **Standard**: a one-off product or service
2) **Main**: all the variations of a product (base product representing all variations)
3) **Variation group**: a group of products/services that share at least one attribute (such as color) and are assigned to a base product
4) **Variation**: a specific instance of a base product
5) **Set**: multiple products/services that display together and can be ordered together or separately
6) **Bundle**: multiple products/services that sell only as a group
7) **Option**: add-on item (upgrades) with separate price and display name; **not orderable or searchable**

## Create a base product (unit walkthrough: Healthfit Sweatshirt)
Context:
- Cloud Kicks usually imports product data, but sometimes a merchandiser creates products manually in the **product catalog**.

Steps:
1) Business Manager → App Launcher → Merchant Tools | Site | Products and Catalogs | **Products**
2) Click **New**
3) Enter:
    - ID: `healthfit-sweatshirt`
    - Catalog: `cloud-kicks-usa-prod`
    - Online: Yes
    - Searchable: Yes
    - Name: `Healthfit Sweatshirt`
4) Click **Apply**
5) Categories tab:
    - Select category: Sportswear
    - Click **Apply**

## Product Grid View (manage storefront display order visually)
- Grid view shows how product display order appears on the storefront.
- You can drag product tiles to change order or enter a position number.
- Each tile links to the base product/variant-level information associated with that product.

Steps:
1) Merchant Tools | Site | Products and Catalogs | **Catalogs**
2) Select the catalog category you want to edit
3) In product list, click **grid view** icon
4) Drag tiles (or set position field)

## Assign products to categories (required for storefront visibility)
- A product must be assigned to a category to appear on the storefront.
- You can assign products to more than one category within and across catalogs.
- Breadcrumb on PDP shows the category path B2C Commerce used (example: `Cloud Kicks | Sportswear`).

### Two assignment types: classification vs primary
- **Classification category**: based on the product catalog and its attributes
- **Primary category**: based on the storefront catalog and its attributes
  Important rule:
- B2C Commerce uses the **primary category** for breadcrumbs only if you select it.
- If you don’t select a primary category, B2C Commerce uses the classification category.
- This setting is product-focused and does not depend on which category the shopper used to reach the PDP.

Walkthrough: assign Sales category to the base product:
1) Merchant Tools | Site | Products and Catalogs | Products
2) Open base product `healthfit-sweatshirt`
3) Categories tab → **Edit Categories**
4) Select:
    - Catalog: `cloud-kicks-usa-prod`
    - Expand Cloud Kicks Category
    - Select **Sales**
5) **Apply**

## Product attributes (system object + variation attributes)
- Product attributes are data (description, size, color, etc.) stored in the `product` **system object**.
- Product ID identifies a distinct item for sale and relates to SKU in inventory management.
- Product system object location in Business Manager:
    - Administration | Site Development | System Object Types | **Product**

Examples of attribute sets mentioned:
- Apparel attributes: highlights, description, care, details, complete the look, how to style, available sizes
- Footwear attributes: highlights, description, details, how to style, available sizes

### Variation attributes
- Attributes like color values `red/green/blue` define variation products; these are “variation attributes.”
- B2C Commerce uses page-specific templates to display variation attributes consistently on:
    - product details pages
    - search results pages
    - product compare pages

### Create variation attributes and assign to a base product (unit flow)
1) Create the variation attribute:
    - Merchant Tools | Site | Products and Catalogs | **Variation Attributes** | Catalog
    - Create a variation attribute using color attribute definition + at least one color value
    - Create a size attribute with values: `small`, `medium`, `large`
2) Use the variation attribute on the base product:
    - Products → open `healthfit-sweatshirt`
    - Click **Lock** (locks base product and associated variation products)
    - Variations tab → select shared attribute you created → **Apply**
    - Note: if you can’t lock, contact your admin.

## Attribute groups (group attribute assignments by category)
- Attribute group is a grouping of attribute assignments attached to a category.
- An attribute can belong to more than one attribute group.
- Attribute assignments display on PDP and for some product comparisons.

Walkthrough: create an attribute group for Sportswear
1) Catalogs → select product catalog `cloud-kicks-usa-prod`
2) Select category Cloud Kicks → Edit Sportswear
3) Product Attribute Definitions tab:
    - ID: `personalization`
    - Name: `Personalization`
    - Add
4) Edit Attributes column:
    - (…) → locate **brand** and **UPC** → Add
    - Back
5) Apply
6) Rebuild product index:
    - Merchant Tools | Search | Search Indexes → select product index → **Rebuild**
7) Result: brand/style number appears on PDP for products categorized by Sportswear.

## Variation products (create the actual variant SKUs)
- Brandon adds variations for Healthfit Sweatshirt in three colors:
    - `healthfit-ss-90887` = green
    - `healthfit-ss-90888` = red
    - `healthfit-ss-90889` = blue

Steps:
1) Products → open base product `healthfit-sweatshirt`
2) Lock the product
3) Variations tab → select variation attribute(s) (color) via ellipses (…) → Apply
4) Variation Products section:
    - Enter product ID `healthfit-ss-90887` → Add → select color green
    - Enter product ID `healthfit-ss-90888` → Add → select color red
    - Enter product ID `healthfit-ss-90889` → Add → select color blue → Apply
    - Note: if you don’t provide an ID, the variation uses base product ID + suffix.
5) Select green as the default variation → Apply (this displays as default on storefront)
6) The unit notes Brandon then adds size (small/medium/large) and assigns size to variations.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả các Salesforce B2C Commerce product types.
- Giải thích product attributes liên quan sản phẩm và hiển thị trên storefront thế nào.
- Mô tả quan hệ base product và variation products.
- Giải thích products liên quan categories thế nào.

## Products (product có thể là gì)
- Product là thứ merchandiser bán.
- Product có thể là:
    - vật lý (physical objects)
    - dịch vụ (ví dụ assembly)
    - options (ví dụ service contracts)

## 7 product types trong B2C Commerce
1) **Standard**: sản phẩm/dịch vụ một-off
2) **Main**: đại diện tất cả variations của một sản phẩm (base product)
3) **Variation group**: nhóm sản phẩm/dịch vụ chia sẻ ít nhất một attribute (ví dụ color) và gán vào base product
4) **Variation**: một biến thể cụ thể của base product
5) **Set**: nhiều sản phẩm/dịch vụ hiển thị cùng nhau, mua cùng hoặc mua riêng
6) **Bundle**: nhiều sản phẩm/dịch vụ chỉ bán theo nhóm
7) **Option**: add-on có price + display name riêng; **không orderable, không searchable**

## Tạo base product (walkthrough: Healthfit Sweatshirt)
Bối cảnh: Cloud Kicks thường import data, nhưng đôi khi merchandiser tạo thủ công trong **product catalog**.

Steps:
1) Merchant Tools | Site | Products and Catalogs | **Products**
2) **New**
3) Nhập:
    - ID `healthfit-sweatshirt`
    - Catalog `cloud-kicks-usa-prod`
    - Online Yes
    - Searchable Yes
    - Name `Healthfit Sweatshirt`
4) **Apply**
5) Categories tab:
    - Chọn Sportswear
    - **Apply**

## Product Grid View (điều chỉnh display order)
- Grid view hiển thị thứ tự sản phẩm như trên storefront.
- Kéo thả tiles hoặc nhập position number.
  Steps:
1) Merchant Tools | Site | Products and Catalogs | **Catalogs**
2) Chọn catalog category
3) Bấm grid view icon
4) Drag/đặt position

## Assign products to categories (bắt buộc để hiển thị)
- Product phải assign vào category mới xuất hiện trên storefront.
- Có thể assign nhiều categories trong/giữa catalogs.
- Breadcrumb trên PDP là category path B2C Commerce dùng (ví dụ `Cloud Kicks | Sportswear`).

### Classification vs primary category
- **Classification category**: dựa trên product catalog và attributes
- **Primary category**: dựa trên storefront catalog và attributes
  Rule:
- Breadcrumb dùng **primary category** nếu bạn chọn.
- Nếu không chọn primary, hệ thống dùng classification category.
- Đây là product-focused, không phụ thuộc shopper click category nào.

Walkthrough assign Sales:
- Products → mở `healthfit-sweatshirt` → Categories → Edit Categories
- Catalog `cloud-kicks-usa-prod` → expand Cloud Kicks Category → chọn **Sales** → Apply

## Product attributes (system object + variation attributes)
- Product attributes là dữ liệu (description/size/color…) trong `product` **system object**.
- Product ID liên hệ SKU trong inventory management.
- Vị trí system object:
    - Administration | Site Development | System Object Types | **Product**

Ví dụ attribute sets:
- Apparel: highlights/description/care/details/complete the look/how to style/available sizes
- Footwear: highlights/description/details/how to style/available sizes

### Variation attributes
- Values như red/green/blue định nghĩa variation products → gọi là variation attributes.
- Templates hiển thị variation attributes trên PDP, search results, compare pages.

### Tạo variation attributes và gán vào base product
1) Variation Attributes | Catalog: tạo color attribute + values; tạo size attribute small/medium/large
2) Products → mở base product → Lock → Variations tab → chọn shared attribute → Apply

## Attribute groups (gán theo category)
- Attribute group = nhóm attribute assignments gắn vào category.
- Attribute có thể thuộc nhiều groups.
- Hiển thị trên PDP và một số compare.

Walkthrough:
- Catalogs → `cloud-kicks-usa-prod` → category Cloud Kicks → Edit Sportswear
- Product Attribute Definitions: ID `personalization`, name `Personalization` → Add
- Edit Attributes: thêm brand + UPC → Apply
- Rebuild product index: Search Indexes → product index → Rebuild
- Kết quả: brand/style number hiển thị trên PDP cho products trong Sportswear.

## Variation products (tạo SKU biến thể)
Ví dụ 3 colors:
- `healthfit-ss-90887` green
- `healthfit-ss-90888` red
- `healthfit-ss-90889` blue

Steps:
- Mở base product → Lock → Variations tab chọn color → Apply
- Variation Products section: nhập ID → Add → chọn color → Apply
- Nếu không nhập ID, system dùng base ID + suffix
- Chọn default variation green → Apply
- Unit nói tiếp sẽ thêm size và assign size cho variations.