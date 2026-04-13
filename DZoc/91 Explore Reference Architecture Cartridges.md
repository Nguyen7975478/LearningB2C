# Explore Reference Architecture Cartridges
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- List what’s typically in a Storefront Reference Architecture (SFRA) cartridge stack.
- Explain why it’s important to keep the SFRA base cartridges edit-free.
- Classify the types of files in each base cartridge.
- List what’s typically in the cartridges folder. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

---

## Introduction
- Vijay wants to take a closer look at the SFRA cartridges.
- Important note from the unit: their contents can change as Salesforce updates software over time. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

---

## Explore SFRA Cartridges (typical stack layers)
The unit describes a fully developed SFRA cartridge stack as typically including: base cartridge, overlay plugin, and custom cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

**Layer: Custom**
- Description: customize multiple layers (including base and product cartridges) for easy feature adoption or to highlight brand/organization.
- Tip: rename custom cartridges with `app_custom_*` so they’re easy to find. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

**Layer: Plugin**
- Description: enhance standard B2C Commerce or third-party functionality by integrating optional products/features (examples: product compare, gift registry, Apple Pay, middleware).
- Tip: plugins can create custom objects or data specific to a product/feature. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

**Layer: Base**
- Description: core functionality supported by the B2C Commerce team (or contributions to GitHub), including best-practice code for common features.
- Note: base cartridge contains features you can configure in Business Manager.
- Tip: some base features are configured in Business Manager (example given: pick up in store). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

---

## Base Cartridges
The unit lists base SFRA cartridges that come with the product: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))
- `app_storefront_base`
- `bm_app_storefront_base`
- `Modules`

Why keep base cartridges edit-free:
- Base cartridges contain common functionality for most storefronts.
- If Vijay doesn’t edit them, his code is more likely to work from one major B2C Commerce release to the next.
- It helps him adopt new features and maintain a clear distinction between base and custom code.
- This practice helps with troubleshooting and adopting bug fixes faster. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

Release cadence note:
- Salesforce releases B2C Commerce multiple times per year, with major and incremental releases. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

---

## The app_storefront_base Cartridge (MVC + what it contains)
The unit restates MVC as used by B2C Commerce: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))
- **Model**: processes business logic, data, and rules.
- **View**: displays on the storefront.
- **Controller**: converts shopper input into actions or data consumed by the model or view.

What app_storefront_base provides:
- Foundational B2C Commerce code with multiple models.
- Models use the B2C Commerce script API to retrieve data for functional areas (example: order data and processing).
- Models construct a JSON object that you can use to create a template. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

Templates (View layer) in SFRA:
- Templates define how data and page information transform into dynamic, HTML-based web pages displayed in the browser.
- Templates are created using **ISML (Internet Store Markup Language)**, a proprietary extension to HTML. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

Localization-friendly folder structures:
- Within the cartridge folder, some subfolders are easily localizable.
- Example: `client` folder has a default folder and language-specific folders.
- Other folders like `forms`, `templates`, and `static` have a similar structure. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

---

## The bm_app_storefront_base Cartridge
- Page Designer functionality is baked into SFRA.
- It helps developers create customized page templates that merchandisers use to showcase products.
- Page Designer starter files are located in `bm_app_storefront_base`, along with code for customizing Business Manager and Einstein functionality. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

---

## The server/module Folder (Modules folder)
- The `modules` folder is as important as the two cartridge folders.
- It contains objects that move data from client to server and back, including data from HTTP requests, responses, and session objects.
- It registers routes that map a URL to code that B2C Commerce executes when it detects the URL.
- It uses a modern JavaScript approach similar to NodeJS’s **Express**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))
- Even though `modules` doesn’t follow a typical cartridge structure, you must upload it to the server together with the cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

---

## Cartridge Folder (SiteGenesis folders you might see)
The unit explains that in Navigation view you might see SiteGenesis folders with core storefront functionality accessed using controllers or legacy pipelines code. It lists: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

- `Storefront_sg_controllers`  
  Contains controllers, scripts, and basic templates that provide business processing (example: determine promotions based on cart products).

- `Storefront_sg_core`  
  Contains templates and forms that provide storefront UI code (examples: account creation form, product details page).

- `Storefront_sg_pipelines`  
  Contains legacy pipelines and scripts that provide business processing (example: take shopper input for shipping and payment methods).

Additional note:
- Each cartridge comes with project, properties, and settings files for easier handling in an IDE. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

---

## Next Steps
- Next unit: upload these cartridges to the server. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

---

## VI (A-level: chi tiết; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê thành phần “thường có” trong SFRA cartridge stack.
- Giải thích vì sao cần giữ base cartridges “edit-free”.
- Phân loại các lo��i file trong mỗi base cartridge.
- Liệt kê những gì “thường có” trong cartridges folder. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

### Giới thiệu
- Vijay muốn xem kỹ cấu trúc SFRA cartridges.
- Nội dung cartridges có thể thay đổi theo từng lần Salesforce cập nhật phần mềm. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

### Explore SFRA Cartridges (3 lớp stack)
- SFRA stack “đầy đủ” thường có: **Base** + **overlay Plugin** + **Custom**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

**Custom**
- Customize nhiều lớp (kể cả base và product cartridges) để dễ adopt feature hoặc thể hiện brand/organization.
- Tip: đổi tên custom cartridges theo `app_custom_*` để dễ tìm. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

**Plugin**
- Tích hợp optional products/features (product compare, gift registry, Apple Pay, middleware).
- Plugins có thể tạo custom objects hoặc data riêng theo feature. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

**Base**
- Core functionality do B2C Commerce team hỗ trợ (hoặc cộng đồng GitHub), theo best practices.
- Base có những features có thể cấu hình trong Business Manager.
- Ví dụ feature base config trong Business Manager: pick up in store. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

### Base Cartridges (3 “base” được nêu)
- `app_storefront_base`
- `bm_app_storefront_base`
- `Modules` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

**Vì sao giữ edit-free**
- Không edit base giúp code ổn định hơn qua các major releases.
- Dễ adopt feature mới, dễ phân tách base vs custom, troubleshoot nhanh và nhận bug fixes nhanh hơn. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

**Release cadence**
- B2C Commerce release nhiều lần mỗi năm: major và incremental. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

### app_storefront_base (MVC + models/templates/ISML)
- MVC:
    - Model (business logic/data/rules)
    - View (hiển thị storefront)
    - Controller (biến input thành actions/data cho model/view) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))
- Models dùng B2C Commerce script API để lấy data theo functional area (vd orders), build JSON object để dùng cho template. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))
- Templates dùng **ISML** (proprietary extension to HTML) để render web pages dynamic. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))
- Một số folder localizable (vd `client` có default + language-specific; `forms/templates/static` tương tự). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

### bm_app_storefront_base
- Page Designer baked into SFRA; starter files nằm trong `bm_app_storefront_base` cùng code customize Business Manager và Einstein. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

### server/module (Modules)
- `modules` quan trọng như cartridge folders:
    - chứa objects chuyển data client↔server, HTTP request/response/session
    - register routes map URL → code execute
    - approach giống NodeJS **Express**
    - phải upload cùng cartridges dù không theo structure cartridge chuẩn ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

### Cartridge Folder (SiteGenesis folders)
- `Storefront_sg_controllers`: controllers/scripts/basic templates cho business processing (vd promotions).
- `Storefront_sg_core`: templates/forms cho UI (vd account creation form, product details page).
- `Storefront_sg_pipelines`: legacy pipelines/scripts cho business processing (vd shipping/payment input). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))
- Mỗi cartridge có project/properties/settings files để IDE xử lý dễ. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))

### Next Steps
- Unit kế tiếp: upload cartridges lên server. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-ref-architecture))