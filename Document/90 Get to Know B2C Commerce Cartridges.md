
# Get to Know B2C Commerce Cartridges
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- List three ways you can use a cartridge.
- Explain why you need at least one custom cartridge to implement a storefront.
- Describe where you can find the code version number.
- Explain the purpose of the cartridge path. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

---

## Introduction (story setup)
- Vijay Lahiri (Cloud Kicks) wants to develop a new Salesforce B2C Commerce storefront and wants cartridges to be the easiest part of his job. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Storefront applications combine client and server code and are based on a reference architecture such as SFRA (SFRA provides a framework for site design). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

---

## What’s a Cartridge?
- A cartridge is a container for packaging and deploying program code and data; structured in folders/subfolders for efficiency. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- A storefront needs at least one cartridge, but typically has multiple cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Uses:
    - extend business functionality
    - integrate with external systems ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Cartridge types:
    - generic cartridges: reusable business functionality for many sites
    - application-specific cartridges: merchant-specific and site-specific functionality
    - third-party cartridges: e.g., tax calculation or credit card processing; found on the AppExchange ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

### What cartridges can contain (list in unit)
- Controllers
- Form definitions
- Scripts
- Static content (text, images, CSS files, client-side JavaScript files)
- Templates
- Web Services Description Language (WSDL) files
- Page Designer experiences (SFRA only) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

### Steps when working with cartridges (process list)
1) Configure the development environment.
2) Download reference architecture cartridges.
3) Review/structure cartridge files on local drive.
4) Define and test a cartridge-upload process.
5) Customize, extend, or overwrite cartridges.
6) Upload changes to the server.
7) Register cartridges in Business Manager.
8) Run the storefront application to test changes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Best practice note stated: extend or override base cartridges to streamline development and ongoing maintenance. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

---

## Configure the Development Environment
- Vijay needs:
    - an IDE (examples: Visual Studio Code, IntelliJ IDEA, Eclipse)
    - a connection to a B2C Commerce sandbox instance (on-demand sandbox or POD-based sandbox in the realm’s SIG). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Realm/instance model explained:
    - A B2C Commerce instance is like a Salesforce org.
    - Multiple instances form a realm with PIG (primary instance group) and SIG (secondary instance group).
    - There are nine instances per realm: three on the PIG (staging/testing/deployment), five sandbox instances on the SIG (code development), and one demo instance. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Deployment collaboration:
    - Vijay works with Linda Rosenberg (administrator) to push changes to the realm’s PIG. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

---

## Cartridge Stack
- B2C Commerce loads cartridges in a specific order from basic functionality to increasingly customized functionality; this order is the **cartridge stack**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Typical SFRA-based stack described:
    - base cartridges loaded first (foundation, maintained by Salesforce; community can submit suggestions)
    - plugin cartridges loaded next (example: Apple Pay)
    - custom cartridges loaded last (merchant branding and custom functionality) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Why custom cartridges are required:
    - Vijay needs at least one custom cartridge; otherwise there’s no individual branding (generic site won’t pique interest).
    - Each site may need a custom cartridge for a specific language/look/functionality.
    - Country-specific third-party cartridges may be needed for payment methods.
    - Having separate functionality-specific cartridges per brand/locale helps reuse most of the stack and roll out shared vs site-specific changes more easily. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

---

## Cartridge Path (purpose and override rules)
- Cartridge stack is a concept from bottom-up customization, but the **cartridge path** determines the order B2C Commerce identifies an element (controller/template/script) to run. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Override rule:
    - Cartridges earlier on the path (to the left) override functionality of cartridges later on the path. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Example from unit:
    - Create cartridge `app-custom-cart-cloudkicks`
    - Add `cartridge/controllers/Cart.js`
    - Extend your version to meet requirements without copy/paste of the base code
    - Place the custom cartridge before the base cartridge in the cartridge path so the custom version runs first, possibly using base code too. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Example cartridge path string (as shown):
    - `app-custom-cart-cloudkicks:app_custom_cloudkicks-us:plugin_applepay:plugin_comparison:app_storefront_base` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

---

## Code Version (where to find it + why it matters)
- Unit assumptions:
    - If you’re not a B2C Commerce Cloud Developer, read along; don’t try in a Trailhead Playground (B2C Commerce isn’t available there).
    - You need site administrator rights in your sandbox; if not, ask your administrator for login credentials. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- How to check code version in Business Manager:
    1) App Launcher → Administration → Site Development → Code Deployment
    2) Click the version you want (only one active at a time). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Explanation:
    - B2C Commerce uses the code version to execute cartridge code for a storefront.
    - You can upload many cartridges to a code version.
    - The cartridge path configured for each site determines which cartridge runs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

---

## VI (A-level: chi tiết, bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Liệt kê 3 cách dùng cartridge.
- Giải thích vì sao cần ít nhất 1 custom cartridge để implement storefront.
- Nêu nơi tìm code version number.
- Giải thích mục đích cartridge path. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

### What’s a Cartridge?
- Cartridge là “container” để package & deploy program code và data; có cấu trúc folders/subfolders. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Storefront cần ít nhất 1 cartridge, thường là nhiều cartridge. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Dùng để extend business functionality hoặc integrate external systems. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Types:
    - generic (reusable)
    - application-specific (merchant/site-specific)
    - third-party (tax, credit card processing…) trên AppExchange ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

### Cartridge chứa gì (list đúng theo unit)
- Controllers, Form definitions, Scripts, Static content (text/images/CSS/client-side JS), Templates, WSDL files, Page Designer experiences (SFRA only). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

### Quy trình làm việc với cartridges (8 bước)
1) Configure development environment
2) Download reference architecture cartridges
3) Review/structure files local
4) Define & test upload process
5) Customize/extend/overwrite
6) Upload changes
7) Register cartridges trong Business Manager
8) Run storefront để test ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Best practice: extend/override base cartridges để dễ maintenance. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

### Configure the Development Environment
- Cần IDE (VS Code/IntelliJ/Eclipse) + kết nối sandbox instance (on-demand hoặc POD-based trong SIG). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Realm model:
    - Instance ~ Salesforce org
    - Realm gồm PIG và SIG
    - 9 instances/realm: 3 PIG (staging/testing/deployment), 5 SIG sandboxes (dev), 1 demo ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Khi deploy, dev phối hợp admin (Linda Rosenberg) để push lên PIG. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

### Cartridge Stack
- Cartridge stack là thứ tự load từ base → plugin → custom. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Base maintained by Salesforce; plugin (vd Apple Pay); custom là branding & custom features. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Cần custom cartridge để có branding; mỗi site có thể cần custom theo language/look/functionality; có thể cần third-party cartridges theo quốc gia (payment). Tách cartridge theo brand/locale giúp reuse stack và rollout changes dễ hơn. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

### Cartridge Path
- Cartridge path quyết định B2C Commerce chọn element nào (controller/template/script) để chạy; cartridge bên trái override bên phải. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Ví dụ: tạo `app-custom-cart-cloudkicks`, thêm `cartridge/controllers/Cart.js`, extend logic (không copy/paste base), đặt custom cartridge trước base trong cartridge path. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Ví dụ chuỗi path:
    - `app-custom-cart-cloudkicks:app_custom_cloudkicks-us:plugin_applepay:plugin_comparison:app_storefront_base` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))

### Code Version
- Không làm trong Trailhead Playground; cần site admin rights trong sandbox. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Xem code version: App Launcher → Administration → Site Development → Code Deployment; chỉ 1 code version active. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))
- Code version dùng để execute cartridge code; upload nhiều cartridges vào 1 code version, còn cartridge path theo site quyết định cái nào chạy. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-explore))