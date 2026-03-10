# Explore B2C Commerce Catalogs
https://trailhead.salesforce.com/content/learn/modules/b2c-catalog-category-product/b2c-explore-catalogs

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain how catalogs relate to sites.
- Explain how search differs from navigation.
- Describe how you can configure catalogs for multiple geographic markets.
- List the steps to deploy a catalog to a production instance.
- Explain the difference between catalog and inventory.

## What’s in a B2C Commerce Product Catalog?
- A Salesforce B2C Commerce **catalog** is a database containing details about products and services (descriptions, specifications, warranties, and so on).
- A catalog can also provide the basis for storefront navigation when products are organized into categories that shoppers browse.
- Many merchants maintain product data in a separate system of record: a **product information system (PIM)**.
    - PIMs support multiple geographic locations and multilingual data.
    - In B2C Commerce implementations, PIM data is typically **imported** into B2C Commerce.
    - Some merchants configure products manually in Business Manager or use a hybrid approach (import + manual changes).
- Operational workflow in the story:
    - Admin (Linda Rosenberg) imports data.
    - Merchandiser (Brandon Wilson) creates and updates category structure so products are assigned properly.

## Key terminology: storefront vs site
- **Storefront** refers to the application.
- **Site** refers to the part of a B2C Commerce instance on which the storefront runs.

## Search versus navigation (how shoppers find products)
- **Search**: shopper enters a search term to find products.
- **Navigation**: shopper clicks a predefined category and subcategories to reach products.
- They are configured and optimized differently (this unit is catalog/navigation focused; search is covered in the storefront search module).

## Catalog Design (core building blocks)
Product data in a catalog is organized by categories. The unit summarizes the catalog structure like this:
- **Catalog** = product repository
- **Categories** = catalog and storefront structure (navigation)
- **Products** = data about what the merchant wants to sell

### Two catalog types (best practice)
B2C Commerce uses two types of catalogs, and the unit recommends creating both (even for new merchants):
1) **Product catalog**
- Contains product data imported from an external PIM system.
- Retains the structure of the PIM (often used for internal classification).
- **Is not assigned to a site.**

2) **Storefront catalog**
- Where you create categories that define storefront navigation.
- A storefront uses **one** storefront catalog.
- A product must be assigned to a category to appear on the storefront.

## Catalog Scenarios (how to support different business needs)
Brandon considers three scenarios:

### Scenario 1: Two basic catalogs
- Configure two catalogs per best practice:
    - Product catalog mirrors the inventory/PIM classification structure.
    - Storefront catalog reflects how the merchant wants to sell products (shopper-oriented navigation).

### Scenario 2: New geographic area (USA + Colombia)
Cloud Kicks sells the same product base across two markets, each with its own site and language.
- Catalog A: **Product** catalog (not assigned to a site)
- Catalog B: **Storefront** catalog assigned to **Cloud Kicks USA**
- Catalog C: **Storefront** catalog assigned to **Cloud Kicks Colombia**
  Configuration approach described:
- Create category structure in Catalog A and do not assign it to a site.
- Create Catalog B, assign it to USA site, create shopper-friendly categories, and assign products owned by Catalog A into Catalog B categories.
- Create Catalog C, assign it to Colombia site, retain structure from Catalog B, and assign products owned by Catalog A into Catalog C categories.
  Key rule emphasized:
- Only products included in the storefront catalog and assigned to a category are visible on that site.
- A product can appear in multiple categories (example: a product appears in both Footwear and Sale).

### Scenario 3: Virtual Sidewalk sale (separate event site)
- Create a separate site for brand-specific sales events accessible via a special code.
  Catalog structure described:
- Catalog A: Product catalog (PIM structure; not assigned)
- Catalog B: USA storefront catalog (assigned to USA site; shopper-friendly structure)
- Catalog D: Event storefront catalog (assigned to Virtual Sidewalk Sale site; focused category structure; products from Catalog A assigned into Catalog D)

## Create a Catalog (Business Manager walkthrough)
Key rules:
- A catalog can be assigned to as many sites as you want, but each site can only have **one** catalog.
  Steps to create a storefront catalog:
1) Business Manager → App Launcher → Merchant Tools | Site | Products and Catalogs | Catalogs
2) Click **New**
3) Select language: Default
4) Enter catalog ID: `cloud-kicks-usa-prod`
    - Must be unique; cannot be changed
    - Don’t use the same name as the storefront (avoids confusion)
5) Enter catalog name: `USA Catalog`
6) Click **Apply**
7) Site Assignments tab → select site(s) → **Apply**

After creating a storefront catalog, Brandon:
1) Creates categories
2) Configures category attributes
3) Defines site settings:
    - Search settings
    - Sorting rules
    - Page meta tag rules

## Maintain and Deploy Catalogs (staging → dev/prod replication)
- Brandon creates/maintains catalogs on **staging**.
- Admin replicates catalogs staging → **development** for testing.
- After testing is complete, admin replicates catalogs staging → **production** (and often development as well).

## Manage Inventory (catalog vs inventory)
- A catalog represents a set of products; **inventory** tracks how many are available to sell.
- Inventory affects shopper experience (avoid “out of stock” surprises in cart or after ordering).
- Inventory systems track preorder/backorder handling and allocation.
- Inventory management options mentioned:
    - **B2C Commerce inventory** (manual): basic availability tracking in the platform.
    - **Salesforce Omnichannel Inventory** (external system): more full-featured interface connected to an external inventory management system.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích catalogs liên quan sites như thế nào.
- Giải thích search khác navigation như thế nào.
- Mô tả cách cấu hình catalogs cho nhiều geographic markets.
- Liệt kê các bước deploy catalog lên production instance.
- Giải thích sự khác nhau giữa catalog và inventory.

## B2C Commerce Product Catalog gồm những gì?
- **Catalog** trong Salesforce B2C Commerce là database chứa chi tiết về products/services (descriptions, specifications, warranties…).
- Catalog cũng là nền tảng cho storefront navigation khi products được tổ chức theo categories để shopper browse.
- Nhiều merchants quản lý product data ở system of record là **PIM (product information system)**:
    - PIM hỗ trợ nhiều geographic locations và multilingual data.
    - PIM data thường được **import** vào B2C Commerce.
    - Một số merchants cấu hình thủ công trong Business Manager hoặc hybrid (import + manual).
- Workflow trong câu chuyện:
    - Admin (Linda) import data.
    - Merchandiser (Brandon) tạo/cập nhật category structure để assign products đúng.

## Thuật ngữ: storefront vs site
- **Storefront** là ứng dụng.
- **Site** là phần của một B2C Commerce instance nơi storefront chạy.

## Search vs navigation
- **Search**: shopper gõ search term.
- **Navigation**: shopper click categories/subcategories.
- Hai phần này tối ưu/cấu hình khác nhau (unit này tập trung catalog/navigation; search xem ở module storefront search).

## Catalog Design (các building blocks)
Unit tóm tắt:
- **Catalog** = product repository
- **Categories** = cấu trúc catalog + storefront (navigation)
- **Products** = dữ liệu hàng hóa merchant bán

### 2 loại catalog (best practice)
Unit khuyến nghị tạo cả hai:
1) **Product catalog**
- Chứa product data import từ external PIM.
- Giữ structure của PIM (internal classification).
- **Không assign cho site.**

2) **Storefront catalog**
- Nơi tạo categories để định nghĩa storefront navigation.
- Một storefront dùng **một** storefront catalog.
- Product phải được assign vào category thì mới xuất hiện trên storefront.

## Catalog Scenarios (các kịch bản)
### Scenario 1: Two basic catalogs
- Product catalog mirror PIM/inventory classification.
- Storefront catalog tổ chức theo cách bán hàng (shopper-oriented).

### Scenario 2: New geographic area (USA + Colombia)
- Catalog A: Product catalog (không assign)
- Catalog B: Storefront catalog cho USA site
- Catalog C: Storefront catalog cho Colombia site
  Cách làm:
- Catalog A giữ category structure của PIM, không assign.
- Tạo Catalog B, assign USA site, tạo categories theo trải nghiệm mua sắm, assign products owned by Catalog A vào categories của B.
- Tạo Catalog C, assign Colombia site, giữ structure từ B, assign products owned by A vào categories của C.
  Quy tắc quan trọng:
- Chỉ products nằm trong storefront catalog và được assign category mới visible trên site.
- Product có thể nằm nhiều categories (ví dụ Footwear và Sale).

### Scenario 3: Virtual Sidewalk sale
- Tạo site riêng cho sales event qua special code.
- Catalog A: product catalog (PIM structure; không assign)
- Catalog B: USA storefront catalog (assign USA)
- Catalog D: event storefront catalog (assign event site; focused categories; assign products owned by A vào D)

## Create a Catalog (walkthrough)
- Catalog assign được nhiều sites, nhưng mỗi site chỉ có **một** catalog.
  Steps tạo storefront catalog:
1) Merchant Tools | Site | Products and Catalogs | Catalogs
2) **New**
3) language: Default
4) catalog ID: `cloud-kicks-usa-prod` (unique, không đổi; không nên trùng tên storefront)
5) catalog name: `USA Catalog`
6) **Apply**
7) Site Assignments → chọn sites → **Apply**

Sau khi tạo storefront catalog, Brandon:
1) Creates categories
2) Configures category attributes
3) Defines site settings: Search settings, Sorting rules, Page meta tag rules

## Maintain & Deploy Catalogs (replication)
- Brandon làm catalog trên **staging**.
- Admin replicate staging → **development** để test.
- Xong test, replicate staging → **production** (và development).

## Manage Inventory (catalog vs inventory)
- Catalog = tập sản phẩm; **inventory** = số lượng có thể bán.
- Inventory giúp tránh trải nghiệm xấu (đến cart mới biết hết hàng).
- Inventory track preorder/backorder và allocation.
- Options:
    - **B2C Commerce inventory** (manual): basic availability tracking.
    - **Salesforce Omnichannel Inventory** (external): giao diện mạnh hơn kết nối inventory management system.