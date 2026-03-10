# Learn About B2C Commerce Product Data
https://trailhead.salesforce.com/content/learn/modules/cc-digital-merchandising/digital-product-data

## English

### Learning Objectives (unit outcomes)
- Explain what makes a product display on a Salesforce B2C Commerce storefront.
- Describe the difference between a **storefront catalog** and a **product catalog**.
- List the types of products you can display in a B2C Commerce storefront.
- List the types of libraries you can configure in B2C Commerce.

### What “product data” includes
- Product data includes pictures, videos, and specifications.
- It also includes product exploration content: tabs, product concepts, and how-to content.

### Where product data lives and how it’s configured
- All product information is stored in the B2C Commerce database.
- You configure product data in **Business Manager**, where you can create, manage, and import product details in one or more catalogs.
- You can import product details, inventory, prices, content, images, and video from another system.

### Catalogs (storefront catalog vs product catalog)
- A **catalog** is a collection of categories, products, and images.
- You can assign only one catalog—the **storefront catalog**—to your site.
- **Storefront catalog**:
    - Category structure determines storefront navigation and category groupings.
    - Determines products available in each category.
    - Determines product attributes displayed to the shopper.
    - Defines search feature configuration, search refinement, and **SEO**.
- **Product catalog**:
    - Used when you want a catalog structure that mirrors an external system/system of record.
    - Not assigned to a site.
    - **Owns the products** (you edit products in the product catalog).
    - Mirrors the organization of inventory, fulfillment, or product management systems.
- A product can be included in multiple catalogs/categories, but it is edited only in the catalog that owns it; edits propagate where the product is included.

### Categories
- Categories define the catalog structure.
- The top-level category is the root category (it doesn’t have a name); all created categories are children of the root category.

### Products: requirements to display + product types
- To display in a storefront, a product must be:
    - Assigned to a storefront category
    - Searchable
    - Online
    - Available
- Product types you can create in Business Manager:
    - **Standard**
    - **Main**
    - **Variation Group**
    - **Variation**
    - **Set**
    - **Bundle**
    - **Option** (not separately orderable or searchable)

### Inventory (inventory lists)
- B2C Commerce provides built-in inventory via **inventory lists** mapping product IDs to inventory details (allocation, preorder/backorder, in-stock dates).
- A site can have only one inventory list; an inventory list can be shared across sites.
- B2C Commerce isn’t the system of record for inventory; it tracks levels and integrates with back-end inventory systems so shoppers see near real-time availability.

### Price Books
- Prices are defined in **price books** (currency-based) with **price tables** for quantity tiers.
- Multiple price tables per product are possible, but only one price table can be active at a time.
- Price books are defined for the organization, then assigned to one or more storefronts; a site must have a price book assigned before it can be used.

### Content Assets and libraries
- B2C Commerce supports content assets such as HTML text, graphics, videos (videos via third-party application), customer support pages, sales content, size charts, tips, etc.
- Content assets are stored in libraries and folders; you can use a private library created with the site or libraries shared by multiple sites.
- Business Manager can manage image matrices (by color/fabric/size range; large/medium/small; swatches).
- Content can be B2C Commerce-managed or delivered via an external **CDN**.

## Tiếng Việt

### Learning Objectives (kết quả của unit)
- Giải thích điều gì khiến product hiển thị trên storefront Salesforce B2C Commerce.
- Mô tả khác nhau giữa **storefront catalog** và **product catalog**.
- Liệt kê các product types có thể hiển thị trên storefront.
- Liệt kê các types of libraries có thể cấu hình trong B2C Commerce.

### “Product data” gồm gì
- Product data gồm pictures, videos, specifications.
- Ngoài ra gồm nội dung khám phá sản phẩm: tabs, product concepts, how-to content.

### Product data lưu ở đâu và cấu hình thế nào
- Tất cả product information nằm trong B2C Commerce database.
- Cấu hình product data bằng **Business Manager** (create/manage/import product details trong một hoặc nhiều catalogs).
- Có thể import product details, inventory, prices, content, images, video từ hệ thống khác.

### Catalogs (storefront catalog vs product catalog)
- **Catalog** là tập hợp categories, products, images.
- Một site chỉ assign được một catalog: **storefront catalog**.
- **Storefront catalog**:
    - Category structure quyết định navigation và nhóm category.
    - Quy định products trong từng category.
    - Quy định product attributes hiển thị cho shopper.
    - Định nghĩa search feature configuration, search refinement, và **SEO**.
- **Product catalog**:
    - Dùng khi muốn cấu trúc catalog mirror external system/system of record.
    - Không assign cho site.
    - **Owns the products** (edit products trong product catalog).
    - Mirror organization của inventory/fulfillment/product management systems.
- Product có thể được include trong nhiều catalogs/categories, nhưng chỉ edit tại catalog “owns” product; thay đổi sẽ tự phản ánh ở các nơi product được include.

### Categories
- Categories định nghĩa cấu trúc catalog.
- Category cấp cao nhất là root category (không có tên); mọi category tạo ra đều là con của root category.

### Products: điều kiện hiển thị + product types
- Để hiển thị trên storefront, product phải:
    - Assigned to a storefront category
    - Searchable
    - Online
    - Available
- Product types trong Business Manager:
    - **Standard**
    - **Main**
    - **Variation Group**
    - **Variation**
    - **Set**
    - **Bundle**
    - **Option** (không separately orderable hoặc searchable)

### Inventory (inventory lists)
- B2C Commerce có inventory built-in qua **inventory lists** mapping product IDs tới inventory details (allocation, preorder/backorder, in-stock dates).
- Một site chỉ có 1 inventory list; 1 inventory list có thể share cho nhiều sites.
- B2C Commerce không phải system of record của inventory; nó track levels và integrate với back-end inventory systems để hiển thị availability gần real time.

### Price Books
- Giá được định nghĩa trong **price books** theo currency với **price tables** cho quantity tiers.
- Có thể có nhiều price tables mỗi product nhưng chỉ 1 price table active tại một thời điểm.
- Price books định nghĩa ở cấp organization rồi assign cho storefronts; site phải assign price book trước khi dùng.

### Content Assets và libraries
- B2C Commerce hỗ trợ content assets như HTML text, graphics, videos (video qua third-party application), support pages, sales content, size charts, tips…
- Content assets lưu trong libraries/folders; có private library theo site hoặc libraries share giữa nhiều sites.
- Business Manager có thể quản lý image matrices (theo color/fabric/size range; large/medium/small; swatches).
- Content có thể do B2C Commerce quản lý hoặc phân phối qua external **CDN**.