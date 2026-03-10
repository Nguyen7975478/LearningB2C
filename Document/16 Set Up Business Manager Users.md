# Set Up Business Manager Users
https://trailhead.salesforce.com/content/learn/modules/b2c-configure-users-roles-permissions/b2c-admin-configure-business-manager-users

## English

### Purpose / key outcomes
- Explain how a Salesforce B2C Commerce administrator creates and manages **Business Manager users**.
- Connect user setup to **roles and permissions**, **unified authentication**, and security policy controls for login/password behavior.

### Business Manager, Account Manager, and authentication model
- **Business Manager** is the administrative application used to configure and operate storefronts.
- **Account Manager** is used to manage account-level access and roles; it is also the place where **multi-factor authentication (MFA)** is enforced for administrative access.
- The unit describes **unified authentication** options:
    - **Local accounts**: users authenticate as local users; Account Manager access uses MFA for eligible roles.
    - **Salesforce Identity**: users link their access by logging in to Account Manager with MFA, enabling centralized identity and app/user management through Salesforce Identity.

### What admins do when setting up Business Manager users
- Create Business Manager user records for individuals based on job function (for example, administrator vs merchandiser).
- Maintain the user lifecycle: update user information, support password resets, and remove/disable access when no longer needed.
- Ensure access matches responsibilities (least privilege): merchandisers get access to merchandising functions (for example campaigns/promotions), while administrators get broader operational access (for example import/export).

### User Login Settings (security policy) in Business Manager
Under **Administration > Global Preferences > Security**, the unit highlights configuring **User Login Settings** such as:
- **Maximum invalid login attempts**
- **Lockout effective period**
- **Password expiration**
- **Accounts will be deactivated if not active**
- Require **security question** for password change (when configured)
- **Enforce password history**
- **Minimum password length**
- Minimum number of **special characters**
- **Minimum login length**

### Storefront password / development protection
- The unit emphasizes that storefronts under development commonly require storefront password controls, and that administrators are responsible for ensuring appropriate password/security configuration during development.

## Tiếng Việt

### Mục đích / kết quả chính
- Giải thích cách Salesforce B2C Commerce administrator tạo và quản lý **Business Manager users**.
- Liên hệ việc set up users với **roles and permissions**, **unified authentication**, và các thiết lập security policy cho login/password.

### Business Manager, Account Manager, và mô hình authentication
- **Business Manager** là ứng dụng quản trị dùng để cấu hình và vận hành storefront.
- **Account Manager** dùng để quản lý access/roles ở cấp account; đồng thời là nơi áp dụng **multi-factor authentication (MFA)** cho truy cập quản trị.
- Unit mô tả các lựa chọn **unified authentication**:
    - **Local accounts**: user xác thực bằng local user; truy cập Account Manager dùng MFA cho các roles phù hợp.
    - **Salesforce Identity**: user đăng nhập Account Manager bằng MFA để link sang Salesforce Identity, cho phép quản lý identity và app/user tập trung.

### Admin làm gì khi set up Business Manager users
- Tạo user theo từng cá nhân và theo job function (ví dụ administrator vs merchandiser).
- Quản lý vòng đời user: cập nhật thông tin, hỗ trợ password reset, và disable/remove access khi không còn nhu cầu.
- Đảm bảo quyền đúng nhiệm vụ (least privilege): merchandiser có quyền các chức năng merchandising (ví dụ campaigns/promotions), còn administrator có quyền vận hành rộng hơn (ví dụ import/export).

### User Login Settings (security policy) trong Business Manager
Tại **Administration > Global Preferences > Security**, unit nhấn mạnh cấu hình **User Login Settings** gồm:
- **Maximum invalid login attempts**
- **Lockout effective period**
- **Password expiration**
- **Accounts will be deactivated if not active**
- Yêu cầu **security question** khi đổi password (nếu cấu hình)
- **Enforce password history**
- **Minimum password length**
- Số lượng tối thiểu **special characters**
- **Minimum login length**

### Storefront password / bảo vệ khi development
- Unit nhấn mạnh storefront đang development thường cần storefront password controls, và administrator chịu trách nhiệm đảm bảo cấu hình password/security phù hợp trong giai đoạn development.