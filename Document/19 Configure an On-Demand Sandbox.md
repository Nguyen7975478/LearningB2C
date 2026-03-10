# Configure an On-Demand Sandbox
https://trailhead.salesforce.com/content/learn/modules/b2c-on-demand-sandbox/b2c-configure-on-demand-sandbox

## English

### Purpose / key outcomes
- Learn what must be configured (primarily in **Account Manager**) so a team can use **on-demand sandboxes** safely and effectively, including roles, permissions, and API access foundations.

### Prerequisites: credits and realm enablement
- After purchasing credits, the realm must be enabled for on-demand sandboxes (the unit frames this as an initial provisioning/activation step before creation is possible).

### Account Manager access and MFA
- Access to Account Manager is protected with **MFA** (the unit describes authorization using **Salesforce Authenticator**).

### User and role setup in Account Manager (key governance)
- Admins create user accounts and assign roles that determine what users can do with on-demand sandboxes.
- The key cost/governance role is **Sandbox API User**:
    - Users with this role can create on-demand sandboxes and therefore **consume credits**.
    - Admins should assign it sparingly to designated sandbox administrators.
- Developers who should use sandboxes but not create them are assigned other roles (examples referenced in the unit include **Business Manager Administrator** and **LogCenter User**) with appropriate scope (for example **All Sandboxes**).

### OCAPI and WebDAV considerations
- The unit highlights enabling access to **Open Commerce API (OCAPI)** and **WebDAV** as part of preparing users and environments for on-demand sandbox operations.

### TTL and lifecycle hygiene
- Configure **time to live (TTL)** where appropriate so sandboxes are automatically deleted after a defined interval, supporting ephemeral environments and CI/CD patterns.

### Accessing Business Manager on an on-demand sandbox
- The unit provides an on-demand sandbox URL pattern under `*.sandbox.dx.commercecloud.salesforce.com/...` to access Business Manager for a specific sandbox instance.

## Tiếng Việt

### Mục đích / kết quả chính
- Nắm các cấu hình cần thiết (chủ yếu trong **Account Manager**) để team dùng **on-demand sandboxes** an toàn và hiệu quả, gồm roles/permissions và nền tảng API access.

### Điều kiện trước: credits và realm enablement
- Sau khi mua credits, realm cần được enable cho on-demand sandboxes (bước activation trước khi có thể tạo sandbox).

### Truy cập Account Manager và MFA
- Truy cập Account Manager được bảo vệ bằng **MFA** (unit mô tả authorize bằng **Salesforce Authenticator**).

### Thiết lập user và roles trong Account Manager (governance quan trọng)
- Admin tạo user accounts và gán roles quyết định user làm được gì với on-demand sandboxes.
- Role quan trọng nhất về cost/governance là **Sandbox API User**:
    - User có role này có thể tạo on-demand sandbox và **consume credits**.
    - Cần gán hạn chế cho nhóm sandbox administrators.
- Developers cần dùng sandbox nhưng không tạo sandbox sẽ được gán roles khác (unit có ví dụ **Business Manager Administrator** và **LogCenter User**) với scope phù hợp (ví dụ **All Sandboxes**).

### OCAPI và WebDAV
- Unit nhấn mạnh việc enable quyền dùng **Open Commerce API (OCAPI)** và **WebDAV** khi chuẩn bị users/environments cho on-demand sandbox operations.

### TTL và hygiene vòng đời
- Cấu hình **time to live (TTL)** khi phù hợp để sandbox tự động bị delete theo thời hạn, hỗ trợ mô hình ephemeral/CI/CD.

### Truy cập Business Manager trên on-demand sandbox
- Unit đưa mẫu URL dạng `*.sandbox.dx.commercecloud.salesforce.com/...` để vào Business Manager của một sandbox cụ thể.