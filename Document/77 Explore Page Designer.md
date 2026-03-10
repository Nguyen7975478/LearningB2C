# Explore Page Designer
https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-merchandiser/b2c-page-designer-explore?trail_id=set-up-merchandising-for-your-storefront

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain how developer involvement differs with **Page Designer** versus **Content Slots**.
- Describe three things you can do with Page Designer.
- List three basic steps of a Page Designer page development workflow.
- List three ways you can control the view of a Page Designer page.
- Explain how pages relate to components.

## What Page Designer is (concept + why it exists)
- **Commerce Cloud Page Designer** is a **visual editor** in **Business Manager** that lets merchandisers create and manage **personalized landing pages** using reusable building blocks.
- Example page types in the unit:
    - **Homepage**
    - **Lifestyle pages**
    - **Category landing pages**
- Example personalization intent in the unit:
    - target **female shoppers** interested in **hiking footwear and apparel**, then reuse the same page/component types to target other sports (baseball, running).

### Page Designer vs Content Slots (developer involvement)
- **Content Slots**: merchandiser can fill preconfigured areas (products, categories, content assets, static HTML, product recommendations), but changing page structure often requires a developer.
- **Page Designer**: developer creates reusable **page types** and **component types**; merchandiser assembles and updates pages without asking the developer for each change.

## What you can do with Page Designer (capabilities)
The unit lists these capabilities:
- Configure when a **page** is visible and who can see it.
- Configure when a **component** is visible in a region and who can see it.
- Provide different content for components **per locale**.
- Upload **content assets**.
- Configure **SEO settings**.
- Enable **search** for Page Designer pages.
- Include a page in the **sitemap**.

How to interpret (so you understand the idea):
- These map to merchandising control pillars:
    - **Targeting** (who),
    - **Scheduling** (when),
    - **Localization** (locale),
    - **Discoverability** (SEO/search/sitemap).

## Workflow (page development lifecycle)
The unit gives general steps:
1) **Design**: Determine how shoppers access the pages (email, category landing, marketing content).
2) **Configure**: Build pages with components, populate content, and assign products.
3) **Preview in Page Designer**: Preview by device types, customer groups, and dates.
4) **Preview on the storefront**: Use the **Storefront Toolkit** to publish, preview by date/customer group/locale/device type, and view URL structure.
5) **Schedule and publish**: Schedule when pages appear and to whom; also make them visible immediately for testing.

## Pages, Components, and Regions (relationship)
The unit defines:
- A Page Designer **page** is an **HTML page** loaded by the browser (desktop/tablet/phone).
- You create a page based on a prebuilt **page type**.
- You use components based on prebuilt **component types**.
- When a developer creates a page type, they define the **page structure**, including **regions**.

Rules for structure:
- A page contains **one or more regions** with sections.
- A **region** contains one or more subcomponents.
- Regions can contain other regions.
- A component uses the layout defined by the component type.

Why this matters:
- Page Type and Component Type are the “contract” between developer and merchandiser:
    - dev defines structure + allowed components,
    - merch builds experiences within that structure.

## UI Tools (how you control “view”)
The unit highlights common tools:

### Locale selector (data locale alignment)
- Brandon changes locale via dropdown.
- **Default** means it uses the preferred data locale in his user profile.
- The unit notes this can differ from the storefront’s default locale.
- Important rule: when working in Page Designer, the **user and site data locale must be the same**.

### Visible toggle (per-locale visibility)
- Toggle **Visible** to set the page visible/hidden for the selected locale.

### Preview (targeted preview)
- Use **Preview** to view how the page looks for:
    - specific device types,
    - customer groups,
    - and dates.

### Device preview sizes + rotate
- Desktop: **1280 × 1024**
- Tablet: **768 × 1024**
- Phone: **375 × 667**
- Use **Rotate** to switch portrait/landscape.

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích developer involvement khác nhau giữa **Page Designer** và **Content Slots**.
- Mô tả 3 việc có thể làm với Page Designer.
- Liệt kê 3 bước workflow cơ bản để phát triển Page Designer page.
- Liệt kê 3 cách control view của Page Designer page.
- Giải thích pages liên quan components như thế nào.

## Page Designer là gì (khái niệm + vì sao có)
- **Commerce Cloud Page Designer** là **visual editor** trong **Business Manager**, giúp merchandiser tạo và quản lý **personalized landing pages** bằng các building blocks tái sử dụng.
- Ví dụ trang trong unit:
    - **Homepage**
    - **Lifestyle pages**
    - **Category landing pages**
- Ví dụ “ý” personalization:
    - target **female shoppers** quan tâm **hiking footwear and apparel**, rồi reuse page/component types cho sports khác (baseball, running).

### Page Designer vs Content Slots (developer involvement)
- **Content Slots**: merchandiser fill nội dung trong slot có sẵn (products/categories/content assets/static HTML/product recommendations) nhưng muốn đổi cấu trúc trang thường cần dev.
- **Page Designer**: dev tạo **page types** + **component types**; merch lắp ghép và update trải nghiệm mà không cần dev mỗi lần.

## Làm được gì với Page Designer (capabilities)
Unit liệt kê:
- Configure khi nào **page** visible và ai thấy.
- Configure khi nào **component** visible trong region và ai thấy.
- Nội dung khác nhau theo **locale**.
- Upload **content assets**.
- Configure **SEO settings**.
- Enable **search** cho Page Designer pages.
- Include page vào **sitemap**.

Cách hiểu (để hiểu ý):
- Đây là 4 trụ:
    - **Targeting** (who),
    - **Scheduling** (when),
    - **Localization** (locale),
    - **Discoverability** (SEO/search/sitemap).

## Workflow (vòng đời tạo page)
1) **Design**: xác định đường vào trang (email/category landing/marketing content).
2) **Configure**: build page bằng components, populate content, assign products.
3) **Preview trong Page Designer**: preview theo device/customer group/dates.
4) **Preview trên storefront**: dùng **Storefront Toolkit** để publish/preview và xem URL structure.
5) **Schedule & publish**: schedule ai thấy/khi nào; có thể bật visible ngay để test.

## Pages, Components, Regions (mối quan hệ)
- Page = **HTML page** load trên browser.
- Page tạo từ **page type**.
- Component dùng theo **component types**.
- Dev tạo page type thì định nghĩa **regions**.

Quy tắc:
- Page có ≥1 regions.
- Region chứa subcomponents.
- Region có thể chứa region khác.
- Component dùng layout do component type định nghĩa.

Ý nghĩa:
- Page Type/Component Type là “hợp đồng” dev–merch.

## UI Tools (control “view”)
### Locale selector (đồng bộ data locale)
- Default locale dùng preferred data locale trong user profile; có thể khác storefront default.
- Rule: user và site data locale phải giống nhau khi làm trong Page Designer.

### Visible toggle
- Toggle **Visible** để visible/hidden theo locale.

### Preview
- Preview theo device/customer group/dates.

### Device sizes + rotate
- Desktop **1280×1024**, Tablet **768×1024**, Phone **375×667**, có **Rotate**.