# Create and Monitor an On-Demand Sandbox
https://trailhead.salesforce.com/content/learn/modules/b2c-on-demand-sandbox/b2c-create-monitor-on-demand-sandbox

## English

### Purpose / key outcomes
- Learn how to create, manage, and monitor **on-demand sandboxes** using both **REST API (Swagger UI)** and a community-based **CLI**, and understand monitoring and credit-usage concepts.

### Tooling overview
- **REST API** accessed through **Swagger UI** (admin endpoint) supports realm-level and sandbox-level operations.
- A community-based **CLI** (Commerce Cloud Community Suite / **SFCC-CI**) is positioned for automation and integration into CI pipelines.

### CI/CD-oriented sandbox lifecycle (example flow)
- Acquire sandbox → deploy code → deploy test data → run automated tests → delete sandbox.
- This pattern demonstrates ephemeral environments that reduce environmental drift and speed up feedback loops.

### REST API prerequisites and authorization
- Prerequisites include:
    - Realm enabled for on-demand sandboxes
    - Required roles such as **Sandbox API User** and **Business Manager Administrator**
    - A configured **API Client ID**
- The unit shows authorizing in Swagger UI via **Authorize** using the API Client ID (lock icon indicates authorization state).

### API action model (what you can do)
- The unit differentiates between general endpoints, **realm-level actions**, and **sandbox-level actions**:
    - Realm-level actions focus on realm information/management.
    - Sandbox-level actions focus on creating and controlling individual sandboxes (create/start/stop/remove).

### Creating a sandbox + TTL semantics
- The unit illustrates creating a sandbox with `POST /sandboxes`.
- **time-to-live (TTL)** is specified in hours (example TTL=24); if TTL ≤ 0, the sandbox persists (“forever”) unless removed.

### Monitoring and logging
- Monitoring is supported via **Log Center** (LogCenter) where log messages are collected for troubleshooting and operational visibility.

### Credit usage, thresholds, and reporting
- The unit describes credit-consumption governance:
    - Notification at a usage threshold (example: **85%** consumption triggers notification to the Salesforce account team).
    - Overages: sandboxes continue running but incur **overage charges** if usage exceeds purchased credits.
- Usage reporting can be queried via REST API endpoints, with fields such as:
    - `sandboxSeconds`
    - `minutesUp`
    - `minutesDown`

### CLI capabilities and integration points
- The CLI supports automation features (as listed in the unit), including:
    - OAuth2 interactive/headless authentication
    - create/start/stop/remove sandboxes
    - instance aliasing / multi-instance configuration
    - code/data deployment with code version handling
    - job execution/monitoring
    - WebDAV connectivity
- The unit notes use in build systems (examples: Jenkins, Travis CI, Bitbucket Pipelines, Heroku CI) and a JavaScript API for Node.js use cases.

### Business Manager configuration for API client access (OCAPI Settings)
- To allow some API/CLI operations against instances, admins grant client access in Business Manager under:
    - **Administration > Site Development > Open Commerce API Settings**
    - Configure **Data API** and **Global** access by adding the client ID’s authorization set.

## Tiếng Việt

### Mục đích / kết quả chính
- Học cách tạo, quản lý và monitor **on-demand sandboxes** bằng **REST API (Swagger UI)** và community-based **CLI**, đồng thời hiểu monitoring và credit-usage concepts.

### Tổng quan tooling
- **REST API** truy cập qua **Swagger UI** (admin endpoint) hỗ trợ thao tác realm-level và sandbox-level.
- Community-based **CLI** (Commerce Cloud Community Suite / **SFCC-CI**) phù hợp automation và tích hợp CI pipelines.

### Sandbox lifecycle theo hướng CI/CD (ví dụ)
- Acquire sandbox → deploy code → deploy test data → chạy automated tests → delete sandbox.
- Mô hình ephemeral giúp giảm environmental drift và tăng tốc feedback loops.

### Điều kiện trước và authorize REST API
- Prerequisites:
    - Realm đã enable on-demand sandboxes
    - Có roles như **Sandbox API User** và **Business Manager Administrator**
    - Có **API Client ID** đã cấu hình
- Unit mô tả authorize trong Swagger UI bằng **Authorize** với API Client ID (lock icon thể hiện trạng thái authorize).

### Mô hình actions của API
- Unit phân biệt general endpoints, **realm-level actions**, **sandbox-level actions**:
    - Realm-level: thông tin/quản lý realm.
    - Sandbox-level: tạo và điều khiển sandbox (create/start/stop/remove).

### Tạo sandbox + ý nghĩa TTL
- Unit minh họa tạo sandbox bằng `POST /sandboxes`.
- **time-to-live (TTL)** tính theo giờ (ví dụ TTL=24); TTL ≤ 0 nghĩa là sandbox tồn tại “forever” cho đến khi bị remove.

### Monitoring và logging
- Monitoring thông qua **Log Center (LogCenter)**, nơi tập trung log messages để troubleshoot và theo dõi vận hành.

### Credit usage, threshold, và reporting
- Unit mô tả governance cho credit consumption:
    - Có thông báo khi đạt ngưỡng (ví dụ **85%** consumption sẽ báo cho Salesforce account team).
    - Nếu vượt credits đã mua, sandbox vẫn chạy nhưng có **overage charges**.
- Usage reporting có thể query qua REST API với các fields:
    - `sandboxSeconds`
    - `minutesUp`
    - `minutesDown`

### CLI capabilities và tích hợp
- CLI hỗ trợ automation (theo danh sách trong unit), gồm:
    - OAuth2 interactive/headless authentication
    - create/start/stop/remove sandboxes
    - aliasing / multi-instance configuration
    - deploy code/data + code version handling
    - execute/monitor jobs
    - WebDAV connectivity
- Unit nêu CLI có thể chạy trong build systems (Jenkins, Travis CI, Bitbucket Pipelines, Heroku CI) và có JavaScript API cho Node.js.

### Cấu hình Business Manager cho API client access (OCAPI Settings)
- Để một số API/CLI operations gọi được vào instances, admin cần grant client access tại:
    - **Administration > Site Development > Open Commerce API Settings**
    - Cấu hình **Data API** và **Global** bằng cách thêm authorization set của client ID.