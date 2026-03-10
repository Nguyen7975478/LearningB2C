# Configuration of Commerce Cloud Digital (B2C Commerce) — Bilingual Summary
Link: https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-configuration

---

## English

### 1. Module Goal
- Explain how B2C Commerce organizes environments using **realm** and **instances**.
- Clarify the purpose of each instance type and how data/code move between them.
- Introduce the core infrastructure components inside an instance (traffic handling, caching, app logic, storage).

### 2. Realm
- A **realm** is a logically isolated environment used to separate data, code, and configuration.
- A realm contains multiple instances used for different phases of building and operating storefronts.

### 3. Four types of instances (Sandbox / Staging / Development / Production)

#### Sandbox
- Used to **create and update storefront code** and perform quick customization/testing.
- Typically **turns off most system jobs**.

#### Staging
- Used to **configure campaigns, promotions, products, catalogs, and content**.
- Supports **uploading data and code** to staging and then **replicating** to production or development.

#### Development
- Used to **simulate the production environment** and as a final testing step for content + code.
- Uses the **CDN**, but **doesn’t cache content**.
- Supports **replicating data and code from staging** and **exporting data** from the instance.

#### Production
- The **live instance** used for storefront transactions.
- Connected to the B2C Commerce **CDN**.
- Typically receives **replicated data and code from staging**.
- For frequently changing data (e.g., price/inventory), **automation** is important to import feeds and keep staging/production synchronized.

### 4. Instance Groups in a realm

#### Primary Instance Group (PIG)
- Consists of **Production (PRD), Staging (STG), Development (DEV)**.
- Intended as the standard set of environments for operating, preparing, and testing a storefront.

#### Secondary Instance Group (SIG)
- Consists of multiple **sandbox instances (On-Demand Sandboxes)**.
- Used for:
  - Customize storefronts
  - Test web shops (CI environment)
  - Demos

### 5. Instance architecture components
A B2C Commerce instance is built from components that handle traffic, caching, application processing, and persistence:

- **Firewall load balancer:** Manages incoming/outgoing requests and distributes traffic to one or more web servers.
- **Web server:** Handles HTTP requests/responses; production includes **at least two web servers**.
- **Web adapter:** Proprietary B2C Commerce plug-in that manages **page caching**, **page assembly**, and **load distribution** to app servers.
- **Local page cache:** Stores frequently accessed data for faster responses, reducing recomputation and app server calls.
- **App servers:** Run **business logic and presentation**; production includes **at least two app servers**.
- **Shared database schema:** Common schema accessed by all app servers within the instance; each instance uses a distinct schema.
- **Shared file system:** Shared storage accessible by all app servers, containing **cartridges, images, and log files**.

### 6. Operational flow (how it’s typically used)
- Build/customize in sandbox and/or development.
- Configure and prepare content/data on staging.
- Replicate tested changes to production.
- Use automation for high-frequency data feeds to keep environments aligned.

### 7. Key takeaways
- Realms and instance groups (PIG/SIG) provide environment separation and operational control.
- The four instance types have distinct roles in the lifecycle from build → test → live.
- The instance component architecture explains how the platform achieves scalability, performance, and high availability.

---

## Tiếng Việt (giữ nguyên thuật ngữ chuyên ngành)

### 1. Mục tiêu module
- Giải thích cách B2C Commerce tổ chức môi trường theo **realm** và **instances**.
- Làm rõ mục đích từng loại instance và cách data/code di chuyển giữa các môi trường.
- Giới thiệu các thành phần hạ tầng trong một instance (xử lý traffic, caching, xử lý application, lưu trữ).

### 2. Realm
- **Realm** là một môi trường logic tách biệt, giúp tách data, code và configuration.
- Một realm chứa nhiều instance để phục vụ các giai đoạn khác nhau của việc xây dựng và vận hành storefront.

### 3. 4 loại instance (Sandbox / Staging / Development / Production)

#### Sandbox
- Dùng để **create và update storefront code**, phù hợp cho customization/testing nhanh.
- Thường **turn off most system jobs**.

#### Staging
- Dùng để **configure campaigns, promotions, products, catalogs, content**.
- Cho phép **upload data và code** lên staging rồi **replicate** sang production hoặc development.

#### Development
- Dùng để **simulate the production environment**, và là bước “final test” cho content + code.
- Có dùng **CDN** nhưng **doesn’t cache content**.
- Có thể **replicate data/code từ staging** và **export data** từ instance.

#### Production
- Môi trường **live** phục vụ **storefront transactions**.
- Connected tới **CDN** của B2C Commerce.
- Thường nhận **replicate data/code từ staging**.
- Với dữ liệu thay đổi thường xuyên (ví dụ price/inventory), cần **automation** để import feeds và giữ staging/production synchronized.

### 4. Instance Groups trong realm

#### Primary Instance Group (PIG)
- Gồm **Production (PRD), Staging (STG), Development (DEV)**.
- Đây là bộ môi trường chuẩn cho vận hành + chuẩn bị + kiểm thử trước khi go-live.

#### Secondary Instance Group (SIG)
- Gồm nhiều **sandbox instances (On-Demand Sandboxes)**.
- Dùng để:
  - Customize storefronts
  - Test web shops (CI environment)
  - Demos

### 5. Thành phần kiến trúc một instance
Một instance được cấu thành bởi các thành phần xử lý traffic, caching, xử lý app, và lưu trữ:

- **Firewall load balancer:** Quản lý request vào/ra và phân phối traffic đến web servers.
- **Web server:** Xử lý HTTP request/response; production có **at least two web servers**.
- **Web adapter:** Plug-in riêng của B2C Commerce, quản lý **page caching**, **page assembly**, và phân phối load đến app servers.
- **Local page cache:** Lưu dữ liệu truy cập thường xuyên để phản hồi nhanh hơn, giảm recomputation và giảm gọi app server.
- **App servers:** Chạy **business logic và presentation**; production có **at least two app servers**.
- **Shared database schema:** Schema dùng chung cho tất cả app servers trong instance; mỗi instance có schema riêng.
- **Shared file system:** Kho shared cho app servers, chứa **cartridges, images, log files**.

### 6. Luồng vận hành thường gặp
- Develop/customize ở sandbox và/hoặc development.
- Chuẩn bị cấu hình và data/content trên staging.
- Replicate các thay đổi đã test lên production.
- Dùng automation cho các feed dữ liệu thay đổi liên tục để đồng bộ môi trường.

### 7. Ý chính cần nhớ
- Realm và PIG/SIG giúp phân tách môi trường rõ ràng và kiểm soát vận hành tốt.
- 4 loại instance có vai trò khác nhau trong vòng đời build → test → live.
- Kiến trúc instance giải thích cách hệ thống đạt scalability, performance và high availability.
