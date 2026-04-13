# Get Started with Agentforce Commerce Business Manager
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager

## EN (A-level: detailed, follows unit Topics; keep technical terms)
### Learning Objectives
After completing this unit, you’ll be able to:
- List three tasks a merchandiser performs in Business Manager.
- List three tasks a developer performs in Business Manager.
- List four settings configured in the Merchant Tools tab.
- List four tasks you can perform on the Administration tab.
- Describe two features of the localization settings. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Introducing Business Manager
- **Business Manager** is the command center for your Salesforce **Agentforce Commerce for B2C** merchandising, administration, and site development capabilities. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Requirement to use it:
    - You must have access to an Agentforce Commerce for B2C **instance**.
    - Agentforce Commerce for B2C is **not available** in a Trailhead Playground; if you don’t have access, ask your manager. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Naming note:
    - Commerce Cloud → **Agentforce Commerce**
    - B2C Commerce → **Agentforce Commerce for B2C**
      (You may still see older names in apps/docs.) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Get Started with the Business Manager User Interface
- When you open Business Manager, you first **select a site**.
- A company can have a few or many sites depending on size and coverage.
- After selecting a site, you can access the **data, code, and permissions** configured for it—if you have access rights. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Definitions used in the unit:
    - In Agentforce Commerce for B2C, a **site** + its associated **code** combine to create a **storefront**.
    - A **storefront** is the user’s online experience.
    - A site can have multiple storefronts. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- UI shortcut:
    - Click **Storefront** to open the selected site in another window.
- Developer convenience:
    - You might see the **Storefront Toolkit** icon; it’s a development tool to troubleshoot and is automatically linked back to the Business Manager site you came from. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Personas
Business Manager supports three personas (job roles): ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- **Merchandisers** configure site data such as products, images, campaigns, promotions, and search settings.
- **Administrators** configure site settings, import/export site data, and roll out code and data changes.
- **Developers** use Business Manager to access the storefront application to debug/troubleshoot and configure development-specific settings.
  Terminology note:
- “customer” can mean different things; the unit suggests calling the Salesforce customer the **merchant**, and the merchant’s customer the **shopper**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
  Org size note:
- Large merchants often separate personas into multiple people/teams (sometimes with partners).
- Small/medium merchants may blur personas (fewer people do multiple roles). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Where Personas Work in Business Manager
- Business Manager has two tabs:
    - **Merchant Tools**
    - **Administration**
- The unit explores Merchant Tools first (used most by merchandisers). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Merchant Tools
- **Merchant Tools** is where merchandisers manage:
    - site-specific configuration settings
    - storefront data: products, catalogs, content, search, campaigns, promotions ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Also includes merchandising capabilities to bring shoppers to the site:
    - **SEO (search engine optimization)** settings. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Data integration note:
    - Customer data is typically stored in an external database.
    - Order details can come from storefront shoppers or add-on systems (such as order management). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Cross-Functional Tools
Some Merchant Tools functionality crosses persona boundaries: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- **Reports & Dashboards**: gathers/analyzes/synthesizes realm data and configures logical datasets into dashboards that show trusted analytics over time.
- **Page Designer**: visual editor to create/manage personalized landing pages (Homepage, Lifestyle pages, Category landing pages).
- **Content slots**: code embedded in storefront to show products/categories/content assets/static HTML by schedule; a content asset can be a flash graphic, product carousel, product search result set, or marketing graphic.
  Developer–merchandiser collaboration:
- Content slots require both:
    1) Developer adds code to HTML pages, creates rendering templates, uploads code to server.
    2) Merchandiser creates and schedules the slot configuration in Business Manager. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Administration
- **Administration** tab is used by administrator and developer personas.
- Administrator tasks include:
    - import/export site data
    - move data/code to and from site instances
    - manage customer lists and content libraries ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Admin configures **global settings (preferences)** for the organization (applies to all sites). Examples listed: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
    - locales and regional settings (multi-language)
    - password restrictions and login lockout policies for Business Manager users
    - time zones
    - order and customer sequence numbers

### The Developer Persona
A typical developer workflow windows: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- IDE (write/test)
- Business Manager (open storefront site)
- Storefront application (see real-time results of code/data changes)
  Developer actions in Business Manager include: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- create new sites
- troubleshoot problems
- configure code versions
- register **cartridges** (containing code or data) with the server
- manage page cache settings
- set site to online
- manage site taxation
- create custom error and maintenance pages
  Operational tasks also performed by developers:
- configure credentials and security
- track quota status (quotas are internal limits that keep systems running nicely). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Permissions
- Access to Business Manager modules is based on job tasks (**roles**).
- The most important role is the **administrator (admin)** who manages users and permissions.
- Admin responsibilities described:
    - define the organization and all storefronts
    - set default languages
    - create additional roles ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
      Permission types in the unit: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- **Module permissions** (example: Products and Catalogs module) → restrict write access to data by role.
- **Functional permissions** (example: `Manage_Site_Catalog`) → grant ability to perform specific functions.
  Examples table (conceptual outcomes):
- Admin can access everything.
- Merchandiser can edit catalog/pricing/inventory but only for their site.
- Web Operations can transfer/replicate data and run jobs but cannot view catalog/pricing/inventory.
- Developer needs broader access across sites plus permission to transfer data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Localization
- Business Manager supports multiple languages in:
    - the UI
    - the underlying data created/edited/shown (for storefront use) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- You can configure locales separately for:
    - viewing the application
    - managing the data
- Example in unit:
    - A shopper could view English products/content while Business Manager is in Japanese. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Admin sets preferred locale for:
    - Business Manager display language
    - creating/editing a user profile
- A Business Manager user can select a different display language in their user profile. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Customize Business Manager
You can customize parts of the Business Manager UI: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- menu items
- menu actions
- dialog actions
- forms
  Unit note:
- Out-of-the-box menus use menu item actions; changes integrate well with standard UI actions → customization is comparatively easy for those areas. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Next Steps
- Summary: you learned who uses Business Manager and why, UI specifics, localization management, and customization.
- Next unit: learn about the Agentforce Commerce for B2C development environment. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

---

## VI (A-level: chi tiết theo đúng Topics; giữ thuật ngữ)
### Mục tiêu học
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê 3 nhiệm vụ của **merchandiser** trong Business Manager.
- Liệt kê 3 nhiệm vụ của **developer** trong Business Manager.
- Liệt kê 4 thiết lập được cấu hình trong tab **Merchant Tools**.
- Liệt kê 4 việc có thể làm ở tab **Administration**.
- Mô tả 2 tính năng của thiết lập **localization**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Introducing Business Manager
- **Business Manager** là “command center” cho Agentforce Commerce for B2C: merchandising, administration, site development. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Điều kiện sử dụng:
    - Phải có quyền truy cập một **instance** Agentforce Commerce for B2C.
    - Không có sẵn trong Trailhead Playground; nếu không có, hỏi quản lý. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Ghi chú đổi tên:
    - Commerce Cloud → Agentforce Commerce; B2C Commerce → Agentforce Commerce for B2C (có thể vẫn gặp tên cũ). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Get Started with the Business Manager User Interface
- Mở Business Manager → phải **select a site** trước.
- Sau khi chọn site, bạn truy cập data/code/permissions của site đó nếu có quyền. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Khái niệm:
    - **site + code** → tạo **storefront**
    - **storefront** = trải nghiệm online của user
    - 1 site có thể có nhiều storefronts ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Click **Storefront** để mở site ở cửa sổ khác.
- Có thể thấy icon **Storefront Toolkit** (tool dev để troubleshoot), tự link với Business Manager site vừa mở. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Personas
- **Merchandisers**: cấu hình dữ liệu site (products, images, campaigns, promotions, search settings).
- **Administrators**: cấu hình site settings, import/export data, rollout code & data changes.
- **Developers**: dùng Business Manager để truy cập storefront app debug/troubleshoot và cấu hình dev-specific settings. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Note thuật ngữ:
    - “customer” có nhiều nghĩa; gọi khách của Salesforce là **merchant**, khách của merchant là **shopper**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Doanh nghiệp lớn/nhỏ:
    - Large merchants thường tách persona rõ; có thể làm với partners.
    - SMB thường “blur personas” (ít người làm nhiều việc). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Where Personas Work in Business Manager
- Có 2 tab chính:
    - **Merchant Tools**
    - **Administration** ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Merchant Tools
- Khu vực merchandiser quản trị config theo site và dữ liệu storefront: products/catalogs/content/search/campaigns/promotions. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Có cấu hình **SEO** để thu hút shoppers.
- Customer data thường nằm ở external DB; order details có thể đến từ storefront hoặc hệ thống add-on (order management). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Cross-Functional Tools
- **Reports & Dashboards**: phân tích dữ liệu realm, tạo dashboards theo datasets.
- **Page Designer**: tạo landing pages (Homepage, Lifestyle, Category landing pages).
- **Content slots**: code embed để hiển thị content theo lịch (products/categories/content assets/static HTML...). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Content slots cần phối hợp:
    - Dev viết code + templates + upload server
    - Merchandiser tạo & schedule slot config trong Business Manager ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Administration
- Admin tab: import/export, move data/code giữa instances, manage customer lists & content libraries. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Global settings (preferences) áp cho toàn organization, ví dụ:
    - locales & regional settings, password/login lockout policies, time zones, order/customer sequence numbers ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### The Developer Persona
- Dev thường mở 3 cửa sổ: IDE, Business Manager, storefront app (xem kết quả realtime). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Các việc dev làm trong Business Manager:
    - create sites, troubleshoot, config code versions, register **cartridges**, manage cache, set online, taxation, custom error/maintenance pages ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Việc vận hành:
    - config credentials/security, theo dõi quotas (limits nội bộ). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Permissions
- Phân quyền theo **roles**; quan trọng nhất là **admin** (quản users/permissions).
- Permission types:
    - module permissions
    - functional permissions (vd `Manage_Site_Catalog`) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))
- Ví dụ:
    - Admin full access; Merchandiser edit trong phạm vi site; Web Ops không xem catalog/pricing/inventory nhưng được transfer/replicate/import/export/run jobs; Developer cần access rộng + transfer permission. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Localization
- Hỗ trợ đa ngôn ngữ cho UI và dữ liệu nền.
- Locale cho “view application” và “manage data” có thể cấu hình riêng.
- Admin set preferred locale; user có thể đổi display language trong profile. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Customize Business Manager
- Customize: menu items, menu actions, dialog actions, forms.
- Out-of-the-box menu dùng menu item actions nên thay đổi tích hợp tốt với UI chuẩn. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))

### Next Steps
- Chuyển sang học development environment. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/cc-business-manager))