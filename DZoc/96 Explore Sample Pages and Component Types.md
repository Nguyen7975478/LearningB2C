# Explore Sample Pages and Component Types
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Identify the page type and component type ID naming convention.
- Explain how page types relate to component types.
- Describe the purpose of mock attributes.
- Explain how resolved values relate to the B2C Commerce API.
- Describe how Page Designer elements are updated in cache. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## Introduction
- Vijay has installed, configured, and downloaded what he needs to work with Page Designer.
- He uploaded code/data to the server and is ready to create a custom cartridge for Page Designer.
- Before starting, he explores the sample Page Designer page and component types that come with SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### SFRA sample cartridges (what they contain)
Names can change per release. The unit highlights:
- `app_storefront_base`: runtime files for page/component types (templates, JSON, scripts)
- `bm_app_storefront_base`: design-time files (names, descriptions, icons, custom attribute editors) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## It’s All in the Name (ID naming convention)
- It’s easy to access page types, component types, and UI controls in code because the **ID** is the key.
- The ID is:
    - the subdirectory path (if any) where the meta definition file and script file are located
    - plus the file name (without extension)
- Use periods (`.`) to separate subdirectory levels. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

**Examples from the unit**
- Page type ID `homepage` when files are directly under `cartridge/experience/pages`.
- If the files are under `cartridge/experience/pages/storefront/campaigns`, the page type ID becomes `storefront.campaigns.homepage`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## Page Types
- Page types define the overall structure of a Page Designer page.
- Vijay starts with the sample page type from SFRA: **Storefront Homepage**.
- It’s described as a simple layout/structure where he can add as many components as he wants. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## Component Types
- Component types contain attributes that merchandisers configure to bring the page to life.
- Example: the **Carousel** component type lets a merchandiser specify the number of slides for each device type (phone/tablet/desktop).
- Each slide contains a component type where attributes like a graphic, text, and a link can be set. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### Sample component types listed
- Main Banner
- Carousel
- Image and Text
- Header
- Shop Category
- Campaign banner
- Product Tile
- Product Carousel - Einstein ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### Where components live in the SFRA repository (as stated)
- `./cartridges/app_storefront_base/cartridge`: css, js, json, isml
- `./cartridges/bm_app_storefront_base/cartridge`: css and properties ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### The three components Vijay focuses on (definitions)
- **Main Banner**: hero image with text overlay and a category picker to create the link. (Hero image = large banner image, typically first thing a shopper sees.)
- **Carousel**: shows product tiles or other components with configurable display attributes per device.
- **Image and Text**: graphic, overlay text, text beneath the graphic, and a link. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## Component Attributes
- Each attribute in a component type’s meta definition file has a **type**.
- The attribute type determines how the merchandiser sets the value in Page Designer.
- Examples:
    - type `file` → file selection modal to browse library files
    - type `enum` → single select box with allowed values
- Attributes call **UI controls** that can display data entry fields or perform actions when a shopper clicks a button.
- If standard types aren’t enough, Vijay can create a **custom attribute editor** (example: selecting store locations on a map). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## Resolved Values
- Page Designer defines content attributes available from the context object (content dictionary) in a map:
    - keys = attribute IDs
    - values = resolved values
- A **resolved value** is converted to a B2C Commerce API object.
    - Example: attribute type `product` → product SKU converted to a `dw.catalog.Product` object instance.
- Some attributes don’t need conversion (strings can be stored as-is). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## Mock Attributes
- Page Designer creates **mock attributes** during authoring.
- When a merchandiser drags a component onto a page (edit mode), a mock component placeholder appears until attributes are configured.
- Mock placeholders are also used:
    - when creating a localized page based on another page
    - when a page doesn’t render because it’s missing attributes ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## Page and Component Type Caching
- B2C Commerce caches page types, component types, and custom UI controls in memory.
- Cache duration depends on environment: sandbox, development, staging, production.
- To refresh in production (or refresh immediately in other instances), perform a **code version switch**.
- Best practice: after replicating new or existing Page Designer elements to production, issue an event for a code version switch to refresh immediately. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## Next Steps
- Next unit explores the underlying code files behind Page Designer page/component types. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

---

## VI (A-level: chi tiết; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Xác định quy ước đặt ID cho page type và component type.
- Giải thích quan hệ page types ↔ component types.
- Mô tả mục đích mock attributes.
- Giải thích resolved values liên quan B2C Commerce API thế nào.
- Mô tả cách Page Designer elements được cập nhật trong cache. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### Introduction
- Vijay đã cài/ cấu hình/ tải files cần cho Page Designer, upload code/data lên server, chuẩn bị tạo custom cartridge; trước đó xem các sample page/component types của SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### SFRA sample cartridges
- `app_storefront_base`: runtime files (templates/JSON/scripts)
- `bm_app_storefront_base`: design-time files (names/descriptions/icons/custom attribute editors) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### It’s All in the Name (ID convention)
- ID là chìa khóa để truy cập page types/component types/UI controls trong code.
- ID = (subdirectory nếu có) + (file name không extension); các level subdirectory nối bằng dấu chấm `.` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))  
  Ví dụ:
- `homepage` nếu nằm trực tiếp dưới `cartridge/experience/pages`
- `storefront.campaigns.homepage` nếu nằm trong `.../storefront/campaigns` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### Page Types
- Page type định nghĩa cấu trúc tổng thể của Page Designer page.
- Vijay bắt đầu từ sample **Storefront Homepage** (layout đơn giản, add nhiều components). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### Component Types
- Component type có attributes để merchandiser cấu hình nội dung.
- Ví dụ Carousel cấu hình số slides theo device (phone/tablet/desktop); mỗi slide lại chứa component type có graphic/text/link. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))  
  Danh sách sample components: Main Banner, Carousel, Image and Text, Header, Shop Category, Campaign banner, Product Tile, Product Carousel - Einstein. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))  
  Nơi chứa:
- `app_storefront_base`: css/js/json/isml
- `bm_app_storefront_base`: css/properties ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### Component Attributes
- Mỗi attribute có type; type quyết định UI nhập liệu trong Page Designer.
- file → modal chọn file; enum → select box.
- Attributes gọi UI controls; nếu thiếu chuẩn có thể tạo custom attribute editor (vd chọn store trên map). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### Resolved Values
- Context/content dictionary map: key=attribute ID, value=resolved value.
- Resolved value là giá trị được convert thành B2C Commerce API object (vd SKU → `dw.catalog.Product`); string có thể giữ nguyên. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### Mock Attributes
- Kéo component vào page → placeholder (mock) cho tới khi cấu hình attributes.
- Mock cũng dùng khi tạo localized page dựa trên page khác hoặc page không render do thiếu attributes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))

### Caching
- Page types/component types/custom UI controls được cache theo environment.
- Refresh production hoặc refresh ngay ở môi trường khác: **code version switch**.
- Best practice: replicate lên production xong thì issue event code version switch để refresh ngay. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-sample-pages-components))