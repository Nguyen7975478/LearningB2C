# Check Your B2C Commerce Status
https://trailhead.salesforce.com/content/learn/modules/b2c-commerce-trust-site/check-your-b2c-commerce-status

## English (summary — keep technical terms)

- This unit is a hands-on guide for checking Salesforce B2C Commerce availability by **POD (Point of Deployment/Delivery)** using the Salesforce status experience (Trust/Status).
- **How health is measured for B2C Commerce**:
    - Different Salesforce products track status differently (the unit contrasts examples such as org/node-based vs database-instance-based tracking).
    - For B2C Commerce, **sandbox**, **development**, and **production** instance health is tracked at the **POD** level (instances share the POD’s underlying hardware/software resources but maintain customer data isolation).
- **Find B2C Commerce PODs in Status** (high-level navigation):
    - Go to the Salesforce Trust site, then access **Status** (the unit describes using “Go to Status”).
    - Use the product navigation to select **B2C Commerce Cloud** and view the list of PODs.
- **POD list color meanings**:
    - **Green**: available and fully functional
    - **Orange**: performance degradation
    - **Red**: service disruption
    - **Purple**: undergoing maintenance
- **Drill into a specific POD**:
    - Locate your POD (search/quick find) and open it.
    - Review **Current Status By Service** to see health per service category for that POD.
    - The unit explains that **Purple (maintenance)** can imply different runtime states depending on maintenance type (for example: available, not available, or **read-only**).
- **History and maintenance visibility**:
    - Use **History** to view past status over a selected time range for POD components/services (the unit gives examples such as core services and capabilities like Cart-related services and **eCDN**).
    - Use **Maintenance** to see scheduled/active maintenance sessions and open a maintenance ID for details and business impact assessment.
- **Subscribe to POD notifications**:
    - The unit describes subscribing via email and confirming via a verification link so you receive POD alerts.
- **Status API**:
    - The unit notes you can use the **Status API for Salesforce Trust** (Swagger REST reference) to programmatically consume status data and embed it into other pages/tools.

## Tiếng Việt (tóm tắt — giữ nguyên thuật ngữ chuyên ngành)

- Unit này hướng dẫn thực hành kiểm tra availability của Salesforce B2C Commerce theo **POD (Point of Deployment/Delivery)** trên trải nghiệm Salesforce Trust/Status.
- **Cách B2C Commerce đo health**:
    - Mỗi sản phẩm Salesforce có cách track status khác nhau (unit nêu đối chiếu kiểu org/node vs database instance).
    - Với B2C Commerce, health của **sandbox**, **development**, **production** được track theo **POD** (cùng chia sẻ hạ tầng POD nhưng dữ liệu khách hàng được cô lập).
- **Cách tìm danh sách POD trên Status**:
    - Vào Salesforce Trust site rồi mở **Status** (unit mô tả dùng “Go to Status”).
    - Chọn **B2C Commerce Cloud** để xem danh sách PODs.
- **Ý nghĩa màu trạng thái POD list**:
    - **Green**: available và fully functional
    - **Orange**: performance degradation
    - **Red**: service disruption
    - **Purple**: đang maintenance
- **Xem chi tiết một POD**:
    - Tìm đúng POD (search/quick find) và mở POD.
    - Xem **Current Status By Service** để biết health theo từng service.
    - Unit giải thích **Purple (maintenance)** có thể dẫn tới nhiều trạng thái tùy maintenance type (ví dụ: available, not available, hoặc **read-only**).
- **Xem lịch sử và maintenance**:
    - Tab **History**: xem status trong quá khứ theo time range cho các components/services (unit nêu ví dụ như core services, Cart services, **eCDN**).
    - Tab **Maintenance**: xem các maintenance sessions; mở maintenance ID để xem chi tiết và đánh giá business impact.
- **Subscribe notifications**:
    - Subscribe bằng email và xác nhận qua link để nhận POD alerts.
- **Status API**:
    - Có thể dùng **Status API for Salesforce Trust** (Swagger REST) để lấy status data theo cách programmatic và nhúng vào công cụ/trang khác.