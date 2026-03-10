# Learn About the Salesforce B2C Commerce Administrator
https://trailhead.salesforce.com/content/learn/modules/b2c-configure-users-roles-permissions/b2c-learn-about-administrator

## English (summary — keep technical terms)

- This unit defines what a Salesforce B2C Commerce **administrator** does and how that role fits into operating a B2C Commerce storefront across environments and tools.
- **Primary responsibilities** highlighted:
    - Manage **users**, **roles**, and **permissions** for **Business Manager** so people have the access they need (and no more).
    - Manage storefront **data** and **code** using platform mechanisms such as **import/export**, **jobs**, and **replication**.
    - Configure site and organization settings via **preferences** (including **custom preferences**).
    - Monitor and control instances (operational oversight) and perform standard system **backups**.
- **Business Manager vs Account Manager**:
    - **Business Manager** is the administration UI for configuring and managing storefront sites; a single instance can host multiple sites.
    - **Account Manager** is the portal for managing the B2C Commerce account, users, and roles at the account level.
    - The unit emphasizes that **Account Manager roles** are different from **Business Manager roles**: each governs permissions within its own tool.
- **Users and roles model in Business Manager**:
    - Typical Business Manager users include developers, merchandisers, and administrators.
    - The admin assigns one or more Business Manager roles; each role grants a specific permission set.
    - The unit reinforces least-privilege thinking via predefined roles to improve both efficiency and security.
    - It notes a built-in `admin` user account with an administrator role that cannot be deleted; administrative recovery rules apply (for example, password reset constraints around the `admin` user).
- **Key admin functions for moving/managing data and code** (as grouped in the unit):
    - **Import/export** (manual or batch) for moving storefront data in/out.
    - **Jobs** for scheduled/batch processing.
    - **Read-only price books** as a high-speed mechanism to bring price books from an external **PIM**.
    - **Data replication** and **code replication**.
    - **Site import/export** for copying site configuration/setting data between instances (commonly to bring a new developer sandbox online).
    - **Catalog feeds** for processing third-party files (the unit references integrations such as Certona-style feeds).
- **Certificates management**:
    - Admin manages client certificates used for secure/authenticated communication: secure interactions with third parties over HTTPS, uploading code to staging, and encryption/decryption for SOAP web services. Certificates are stored/managed in Business Manager with expiration tracking.
- **Multi-Factor Authentication (MFA)**:
    - The unit explains **MFA** (and that two-factor authentication is a form of MFA) and frames it as a control against threats such as phishing, malicious code injection, account takeovers, Magecart-style attacks, and data loss.
- **Control Center** and operational controls:
    - The unit references **Control Center** for monitoring instance state and performing actions such as initialize/start/stop/restart, viewing usage information, and viewing audit logs.
    - It also notes using Account Manager to manage credentials for Business Manager and Control Center.
- **Architecture context reminder**:
    - The unit ties administrative responsibility back to the platform architecture: realm-level separation (with **PIG** and **SIG**), multiple instances, and multiple sites within an instance as an organization—because roles/permissions and preferences can apply at different scopes.

## Tiếng Việt (tóm tắt — giữ nguyên thuật ngữ chuyên ngành)

- Unit này mô tả vai trò Salesforce B2C Commerce **administrator** và cách vai trò đó vận hành storefront B2C Commerce xuyên suốt các environments và các công cụ quản trị.
- **Trách nhiệm chính**:
    - Quản lý **users**, **roles**, **permissions** trong **Business Manager** để đảm bảo đúng quyền truy cập (least privilege).
    - Quản lý storefront **data** và **code** bằng các cơ chế như **import/export**, **jobs**, **replication**.
    - Cấu hình thiết lập site/organization bằng **preferences** (bao gồm **custom preferences**).
    - Giám sát vận hành instances và thực hiện system **backups** tiêu chuẩn.
- **Business Manager vs Account Manager**:
    - **Business Manager** là UI để cấu hình và quản trị storefront sites; một instance có thể có nhiều sites.
    - **Account Manager** là portal quản lý account/users/roles ở cấp tài khoản B2C Commerce.
    - Unit nhấn mạnh **Account Manager roles** khác **Business Manager roles** (mỗi loại chỉ có hiệu lực trong công cụ tương ứng).
- **Mô hình users và roles trong Business Manager**:
    - Users thường gồm developers, merchandisers, administrators.
    - Admin gán một hoặc nhiều Business Manager roles; mỗi role là một permission set cụ thể.
    - Khuyến nghị dùng predefined roles để vừa hiệu quả vừa tăng security theo least privilege.
    - Unit nhắc tới user `admin` built-in với administrator role không thể xóa, kèm các quy tắc recovery/reset liên quan đến `admin`.
- **Các chức năng admin để quản lý/di chuyển data và code**:
    - **Import/export** (manual hoặc batch) để đưa dữ liệu vào/ra.
    - **Jobs** để chạy theo lịch/batch processing.
    - **Read-only price books** để import price books tốc độ cao từ external **PIM**.
    - **Data replication** và **code replication**.
    - **Site import/export** để copy site configuration/setting data giữa instances (thường dùng để bring up developer sandbox mới).
    - **Catalog feeds** để xử lý third-party files (unit nhắc tới kiểu feeds như Certona).
- **Certificates**:
    - Admin quản lý client certificates cho secure/authenticated communication: tương tác third parties qua HTTPS, upload code lên staging, và SOAP web service encryption/decryption; certificates được lưu trong Business Manager để theo dõi expiration.
- **Multi-Factor Authentication (MFA)**:
    - Unit giải thích **MFA** (two-factor authentication là một dạng MFA) và xem đây là kiểm soát quan trọng chống phishing, malicious code injection, account takeovers, Magecart-style attacks, và data loss.
- **Control Center** và vận hành:
    - Unit đề cập **Control Center** để theo dõi trạng thái instance và thao tác initialize/start/stop/restart, xem usage, xem audit logs.
    - Đồng thời dùng Account Manager để quản lý credentials cho Business Manager và Control Center.
- **Nhắc lại bối cảnh kiến trúc**:
    - Unit liên hệ tới kiến trúc: realm (với **PIG** và **SIG**), nhiều instances, và nhiều sites trong một instance (organization), vì roles/permissions và preferences có thể áp theo scope khác nhau.