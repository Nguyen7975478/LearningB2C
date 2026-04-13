# Explore the B2C Commerce Development Environment
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment

## EN (A-level: detailed; keep technical terms; follow Topics)
### Learning Objectives
After completing this unit, you’ll be able to:
- List two tools used for the client portion of a Salesforce Agentforce Commerce for B2C storefront.
- List the three key Agentforce Commerce for B2C software development tools.
- Describe the elements of the MVC architecture.
- List three tasks you can perform with scripts and controllers. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Look at the Tools
- Start by looking at the tools in the storefront developer landscape. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- The **three key software development tools** are: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
    - **Business Manager**
    - **Microsoft Visual Studio Code**
    - **Agentforce Commerce Storefront Reference Architecture (SFRA)**
- Other development tools called out: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
    - Templates
    - Form definitions
    - Resource bundles
    - Scripts
    - Controllers

### The MVC Architecture
- Agentforce Commerce for B2C uses **Model–View–Controller (MVC)**, dividing an application into three parts: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
    - **Model**: business logic, data, rules underlying the application.
        - Traditionally, models store data used to populate the view.
        - In Agentforce Commerce for B2C, data is represented by **APIs**, which provide helper classes instead of storing data.
    - **View**: what the shopper sees on the storefront (landing page, product details page, QuickView, cart page).
    - **Controller**: takes shopper input (fields, clicks) and converts it into actions/data consumed by the model or view.
- The unit notes that while MVC maps how things work together, code still needs a deployment mechanism → cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Agentforce Commerce for B2C Cartridges
- A **cartridge** packages and deploys program code and data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- It can deliver:
    - generic functionality (shared processes)
    - application-specific functionality (brand-specific code/data)
- Example framing:
    - merchant sells multiple brands, each with its own site; processes similar but look/feel differ → generic cartridges for standard processes, app-specific cartridges for brand customization. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Let’s Start With What We’re Building (top-down view)
#### Storefront pages (client)
- Standard storefront pages: Home, Category, Product details, Search results. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- These pages are in proprietary **ISML** (based on HTML) and use **CSS** for formatting.
- Shoppers interact via clicking buttons/tabs and entering text into fields.
- Client-side tools used here:
    - **templates**
    - **form definitions** ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
      With these tools you can: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Validate shopper input
- Prompt shoppers for confirmation
- Show error or informational boxes
- Conditionalize HTML

#### Application processing (client + server)
- There’s a processing component on both client and server: takes clicks/data entry and does something with it. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Tools used here:
    - **scripts**
    - **controllers**
      With these tools you can: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Add calculations and logic to business processes
- Call web services
- Integrate back-end systems
- Share information across users

### Coding Storefront Pages
- Storefront pages are the visuals (products, ads, discounts).
- For visuals you use:
    - templates, form definitions, resource bundles (client-based only). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Templates
- Templates transform data and page information into HTML-based web pages.
- Rendered in the browser using CSS for styling and form definitions for data display/verification. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Templates are coded in **ISML** (Internet Store Markup Language):
    - dynamically generates HTML
    - provides predefined tags (example: `<isif>`, `<isloop>`)
    - uses script blocks and expressions ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- One template can display thousands of products (example: search results page tiles). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Form Definitions
- Form definitions control how customer-entered values are validated and rendered in the browser. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Example constraints:
    - ZIP codes must be a precise series of integers
    - name/address as strings
- Form definitions are proprietary (distinct language like ISML). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Storage:
    - forms folder of a cartridge: `cartridge/forms/default`
    - a form schema file identifies allowed elements and attributes
- Form definitions interact with both display and processing parts. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Resource Bundles
- Avoid hard-coding shopper-visible text in code.
- Store titles/labels/messages/button & field names in resource bundles (`.properties` files).
- Benefits:
    - separate text from layout
    - easier changes, especially for different locales ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Process the Storefront Application
- Processing handles what happens from arrival to checkout at shopper initiative (displays/sends/calculates/retrieves the right details). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Uses scripts and controllers.
- Uploading code:
    - SFRA Upload Tool or upload utilities such as **webdav**
    - utilities available from community repositories in GitHub
    - can also use standard JavaScript tools (linters, static code analysis). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Scripts
- Develop locally in Visual Studio Code, but run on the server.
- A JavaScript interpreter on the application server processes each JavaScript class/method.
- Source of the script call is irrelevant to the interpreter → tool flexibility. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- APIs mentioned: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
    - Agentforce Commerce for B2C **Script APIs**
    - **SCAPI** (Agentforce Commerce for B2C API): RESTful APIs to build storefront UX
    - **OCAPI** (Open Commerce APIs): RESTful API for third-party integrations and unified journeys beyond hosted experience
- With SCAPI/OCAPI: request construction and response consumption is up to you. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Controllers
- Controllers are server-side scripts that handle storefront requests. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- They orchestrate back-end processing and create instances of models/views per request.
- Example triggers: clicking category menu item or entering search term triggers a controller that renders a page.
- Written in JavaScript and Agentforce Commerce for B2C script.
- File extension: `.ds` or `.js`.
- Location requirement: controllers must be in the `controllers` folder at the top level of the cartridge.
- You can use any IDE with a JavaScript editor to develop controllers. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Getting Started (the unit’s condensed steps)
The unit reduces setup to: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
1) Review the Developers Center for Commerce Cloud.
2) Get a sandbox from Support (or LINK partner manager if applicable).
3) Install an IDE (for example Visual Studio Code).
4) Open Business Manager and:
    - register cartridges
    - import SFRA data into sandbox
    - disable page caching (see changes immediately)
    - generate search indexes
    - view the storefront

### LINK Partners
- LINK marketplace: extend sites with third-party software.
- Providers certify cartridges via the LINK Technology Partner Program.
- LINK cartridges reduce implementation time (ready-to-go).
- Categories include payment providers, ratings & reviews, tax address verification, social personalization. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Next Steps
- Next unit: learn about SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

---

## VI (A-level: chi tiết; giữ thuật ngữ; theo Topics)
### Mục tiêu học
- Liệt kê 2 tools dùng cho “client portion” của storefront.
- Liệt kê 3 key software development tools.
- Mô tả các phần của MVC architecture.
- Liệt kê 3 việc có thể làm với scripts và controllers. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Look at the Tools
- 3 key tools: **Business Manager**, **Microsoft Visual Studio Code**, **SFRA**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Các tool khác: templates, form definitions, resource bundles, scripts, controllers. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### MVC Architecture
- **Model**: business logic/data/rules; trong Agentforce Commerce for B2C, data được đại diện bằng **APIs** cung cấp helper classes thay vì lưu data kiểu truyền thống. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- **View**: những gì shopper thấy (landing, product details, QuickView, cart). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- **Controller**: nhận input (fields/clicks) chuyển thành actions/data cho model/view. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- MVC chỉ là “map”; vẫn cần cơ chế deploy → cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Cartridges
- **cartridge** là cách package & deploy code + data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Có generic cartridges (process chuẩn) và application-specific cartridges (brand-specific code/data). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Storefront pages (client) + processing
- Pages chuẩn: Home, Category, Product details, Search results. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Dùng proprietary **ISML** (based on HTML) + **CSS**.
- Tool phía client: templates + form definitions.
- Làm được: validate input, confirm, hiển thị error/info, conditionalize HTML. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Processing component (client+server) dùng scripts+controllers:
    - calculations/logic, call web services, integrate back-end systems, share info across users. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Templates / Form Definitions / Resource Bundles
- Templates: ISML, predefined tags `<isif>/<isloop>`, dynamic HTML; 1 template hiển thị hàng ngàn sản phẩm (search results tiles). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Form definitions: validate/render input; lưu ở `cartridge/forms/default`; có schema file; tương tác cả display lẫn processing. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Resource bundles (`.properties`): tách text khỏi layout, dễ đổi theo locale; tránh hard-code. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Scripts / Controllers
- Scripts: code viết local (VS Code) chạy trên server; JS interpreter xử lý class/method; linh hoạt tool. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- APIs: Script APIs, **SCAPI**, **OCAPI**; request/response do bạn xây. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))
- Controllers: server-side scripts; orchestrate processing; `.ds`/`.js`; nằm trong folder `controllers` ở top-level cartridge. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### Getting Started
- Xem Developers Center → lấy sandbox → cài IDE → Business Manager: register cartridges, import SFRA data, disable caching, generate search indexes, view storefront. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))

### LINK Partners
- LINK marketplace cung cấp cartridges đã certify, triển khai nhanh; categories: payments, ratings/reviews, tax verification, social personalization. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-dev-environment))