# Configure Roles and Permissions
https://trailhead.salesforce.com/content/learn/modules/b2c-configure-users-roles-permissions/b2c-admin-configure-roles-permissions

## English

### Purpose / key outcomes
- Explain how **roles and permissions** control access in Business Manager.
- Understand permission types (module, functional, WebDAV), locale requirements, and how to configure and assign roles.

### Role model and relationship to Account Manager
- A **Business Manager role** is a named grouping of permissions; a user can have **multiple roles**.
- Permissions are **additive**: effective access is the union of permissions across assigned roles.
- Business Manager roles are distinct from **Account Manager roles**:
    - Account Manager roles govern access at the account/instance level.
    - Business Manager roles govern what users can do inside Business Manager.

### Core permission types (3)
1) **Module permissions**
- Grant access to Business Manager modules (UI areas).
- Often depend on scope: **site** vs **organization** context.

2) **Functional permissions**
- Grant the ability to perform specific operations (task-level rights), such as asset/library tasks, order deletion, or price adjustment actions.
- Some functional permissions are site-level only; others are organization-level only.
- Real work usually requires both module + functional permissions (for example, access to a module plus the functional permission to manage objects within it).

3) **WebDAV permissions**
- Control access to WebDAV folders used for files/code/data, including examples like:
    - `/cartridges`
    - `/realmdata`
    - `/securitylogs`

### Locales / languages requirement
- Roles must specify allowed **languages/locales**, ensuring Business Manager access aligns to localization needs.

### Where and how admins configure roles
- Configuration is done in Business Manager under **Administration > Organization > Roles & Permissions**.
- The unit walks through creating a role (example: `merchandiser`) and assigning:
    - Module permissions across major areas (Products and Catalogs, Content, Search, Online Marketing, Ordering, Analytics).
    - Functional permissions (examples shown in the unit include `Manage_Site_Catalog`, `Manage_Site_PriceBooks`, `Manage_Site_Inventory`).
- Admins then assign the role to users so their Business Manager access matches job responsibilities.

## Tiếng Việt

### Mục đích / kết quả chính
- Giải thích cách **roles and permissions** kiểm soát truy cập trong Business Manager.
- Hiểu các loại permissions (module, functional, WebDAV), yêu cầu locale, và cách cấu hình/gán roles.

### Mô hình role và mối quan hệ với Account Manager
- **Business Manager role** là nhóm permissions được đặt tên; một user có thể có **nhiều roles**.
- Permissions là **additive**: quyền thực tế là tổng hợp từ tất cả roles đã gán.
- Business Manager roles khác **Account Manager roles**:
    - Account Manager roles quản lý access cấp account/instance.
    - Business Manager roles quản lý user làm được gì trong Business Manager.

### 3 loại permissions chính
1) **Module permissions**
- Cấp quyền vào các Business Manager modules (khu vực UI).
- Thường phụ thuộc scope: theo **site** hoặc theo **organization**.

2) **Functional permissions**
- Cấp quyền thao tác cụ thể ở mức task (ví dụ asset/library, xóa order, thao tác price adjustment).
- Có functional permissions chỉ site-level hoặc chỉ organization-level.
- Nhiều tác vụ cần cả module + functional permissions (vào module và có quyền quản lý đối tượng bên trong).

3) **WebDAV permissions**
- Cấp quyền vào WebDAV folders chứa files/code/data, ví dụ:
    - `/cartridges`
    - `/realmdata`
    - `/securitylogs`

### Yêu cầu Locales / languages
- Role phải chỉ định **languages/locales** được phép, để truy cập Business Manager phù hợp theo ngôn ngữ/địa phương.

### Cấu hình roles ở đâu và như thế nào
- Cấu hình tại **Administration > Organization > Roles & Permissions** trong Business Manager.
- Unit minh họa tạo role (ví dụ `merchandiser`) và gán:
    - Module permissions cho các khu vực chính (Products and Catalogs, Content, Search, Online Marketing, Ordering, Analytics).
    - Functional permissions (ví dụ trong unit: `Manage_Site_Catalog`, `Manage_Site_PriceBooks`, `Manage_Site_Inventory`).
- Sau đó admin gán role cho users để quyền truy cập khớp job responsibilities.