# Explore Pages, Components, and Development Elements
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Explain the benefits of using Page Designer over content slots.
- List three steps of a typical Page Designer implementation plan.
- Describe how the Page Designer pages and component type JSON and script files relate to each other.
- Explain how Page Designer data differs from content asset data in the content database. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

---

## Introduction
- Vijay Lahiri (Cloud Kicks developer) works with marketing and merchandising to customize the storefront.
- Marketing wants him to use **Page Designer** (instead of content slots) to create reusable page elements.
- Up-front dev work enables merchandisers to customize pages on their own; Page Designer provides drag-and-drop design, scheduling, and publishing.
- Page Designer pages load faster than comparable pages built using content slots.
- You build pages/components using open web standards, framework components, and a reference solution kit.
- You can use **SFRA** as a base (reduces dependencies and QA time, improves speed to market).
- SFRA includes built-in Page Designer pages and prebuilt components (headers, carousels, product tiles).
- You can skin/customize components and can create your own page/component types. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

---

## Pages, Components, and Regions (implementation plan)
In their first meeting, they decide on a typical plan: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))
1) **Plan pages** (Marketing director and Vijay)
    - Create a requirements document detailing required pages, components, layouts, assets.
2) **Get ready** (Vijay)
    - Build the development environment (systems and tools).
3) **Explore** (Vijay)
    - Use sample pages/components to understand Page Designer and review requirements.
4) **Develop** (Vijay)
    - Adapt sample component and page types.
5) **Create** (Brandon Wilson, merchandiser)
    - Use Page Designer in Business Manager to design, schedule, publish custom pages by dragging page and component types.

---

## Pages, Components, and Regions (key terms)
- **Pages**: outermost container of structured content; contain regions.
- **Regions**: contain components; can be hierarchical; can contain other regions.
- **Components**: contain attributes that define the content asset.
- **Components as layouts**: components can also be layouts, containing multiple regions where merchants add more components.
- **Attributes + UI controls**: attributes reference UI controls used by merchandisers to set component attribute values (drop-down list, text field, true/false checkbox). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))
- Vijay creates page types and component types in a **cartridge** (packaging/deploy mechanism).
- Merchandiser (Brandon) uses those types to build pages in Page Designer; pages/components are instances of the types Vijay creates. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

---

## What Are the Development Elements (developer-focused)
The unit lists key elements Vijay focuses on: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### Controllers
- Server-side scripts that handle storefront requests.
- Example: clicking a category menu item or entering a search term triggers a controller that renders a page.
- Written in JavaScript and Salesforce B2C Commerce script. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### JSON files (meta definition files)
- JSON meta definition files describe page types and component types.
- Each page type / component type requires one `.json` meta definition file.
    - Page type meta definition file: describes regions where components can be placed.
    - Component type meta definition file: describes the component type’s attributes; can also define regions. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### Script files
- Include business and view logic.
- Each page and component type requires a script file.
- Script file name must match the meta definition file name (same base name) but with `.js` extension.
- Typically, a script file calls an ISML template. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### ISML templates
- Define how data/page information transforms into HTML-based web pages.
- Rendered in browser using CSS for layout/styling and B2C Commerce form definitions for data display/verification.
- Templates are coded in ISML, which dynamically generates HTML. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### Properties files
- Store storefront text strings (button names, error messages).
- For localization of page/component types or to show thumbnail images in the visual editor:
    - Vijay creates a custom cartridge containing resource bundles for localization and thumbnail image files,
    - then uploads the cartridge to the Business Manager site.
- When adding new types or modifying files, he updates properties files accordingly. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

---

## Page Designer and Content Assets
- Content assets highlight products and discounts as part of the shopper experience.
- Pages and components are persisted in the B2C Commerce database as content assets.
- But:
    - the content asset list in Business Manager does not show pages and components,
    - and you can’t edit them directly from that list.
- Generally, replication and indexing processes work the same for pages/components as for content assets, and they are all stored in the content library (database). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

---

## Searchable Pages
- Page Designer pages/components are content assets, but they aren’t assigned to folders.
- To make them searchable, extend the `ContentSearchModel` to remove the folder filter. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

---

## Next Steps
- Next unit: set up an environment to build and customize Page Designer pages and components. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

---

## VI (A-level: chi tiết; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Giải thích lợi ích của Page Designer so với content slots.
- Liệt kê 3 bước (thực tế là plan 5 bước trong bảng) của một kế hoạch triển khai Page Designer.
- Mô tả quan hệ giữa JSON và script files của page/component types.
- Giải thích Page Designer data khác content asset data trong content database thế nào. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### Introduction
- Vijay làm việc với marketing/merchandising để customize storefront.
- Marketing muốn dùng **Page Designer** thay vì content slots để tạo reusable page elements.
- Dev làm upfront để merchandiser tự kéo-thả thiết kế, schedule và publish.
- Page Designer load nhanh hơn content slots.
- Có thể build theo open web standards + framework components + reference solution kit.
- Dùng **SFRA** làm base để giảm dependencies/QA time và tăng speed to market.
- SFRA có sẵn Page Designer pages và prebuilt components (headers, carousels, product tiles); có thể skin/customize hoặc tự tạo page/component types. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### Pages, Components, and Regions (implementation plan)
Bảng kế hoạch triển khai: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))
1) Plan pages (Marketing director + Vijay): viết requirements document (pages/components/layouts/assets).
2) Get ready (Vijay): build development environment (systems/tools).
3) Explore (Vijay): dùng sample pages/components để hiểu Page Designer và review requirements.
4) Develop (Vijay): adapt sample component/page types.
5) Create (Brandon Wilson – merchandiser): dùng Page Designer trong Business Manager để design/schedule/publish bằng cách drag page & component types.

### Thuật ngữ cốt lõi (Pages/Regions/Components)
- **Pages**: container ngoài cùng, chứa regions.
- **Regions**: chứa components; có thể lồng nhau.
- **Components**: có attributes define content asset.
- Components có thể là **layouts** chứa nhiều regions để merchant add thêm components.
- Attributes gắn với **UI controls** (drop-down/text field/true-false checkbox) để merchandiser cấu hình. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))
- Vijay tạo page types/component types trong **cartridge**; Brandon dùng các types để tạo pages trong Page Designer; pages/components là instances của types. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### Development Elements (Controllers/JSON/Script/ISML/Properties)
- **Controllers**: server-side scripts xử lý request (category click/search term → render page), viết bằng JavaScript + B2C Commerce script. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))
- **JSON meta definition files** (`.json`):
    - page type: mô tả regions đặt components
    - component type: mô tả attributes, có thể define regions ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))
- **Script files** (`.js`):
    - business + view logic
    - tên file trùng với meta definition (chỉ khác extension)
    - thường gọi ISML template ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))
- **ISML templates**:
    - biến data/page info thành HTML pages; render với CSS + form definitions; ISML dynamic HTML ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))
- **Properties files**:
    - lưu text strings (button names/error messages)
    - localization + thumbnails: tạo custom cartridge chứa resource bundles + thumbnail image files rồi upload lên site
    - thay đổi types/files thì update properties ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### Page Designer và Content Assets
- Pages/components được persist như content assets trong database.
- Nhưng list content assets trong Business Manager không hiển thị pages/components và không edit trực tiếp từ đó.
- Replication/indexing nhìn chung hoạt động tương tự và đều lưu trong content library (database). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### Searchable Pages
- Pages/components không nằm trong folders → muốn searchable thì extend `ContentSearchModel` để bỏ folder filter. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))

### Next Steps
- Unit sau: setup environment để build/customize Page Designer pages/components. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-pages-components-dev-elements))