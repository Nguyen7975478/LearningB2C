# Discover Commerce PWA Kit and Commerce Managed Runtime
https://trailhead.salesforce.com/content/learn/modules/commerce-pwa-kit-and-managed-runtime/discover-commerce-pwa-kit-and-commerce-managed-runtime

## English (summary — keep technical terms)

- **Headless commerce** decouples the storefront **front end** (“the head”) from the commerce **back end** so teams can evolve experiences faster; **APIs** bridge the gap between the two layers. The unit positions this as a way to innovate across many devices/touchpoints without being constrained by a tightly-coupled storefront stack.
- **Commerce PWA Kit** and **Commerce Managed Runtime** are presented as a packaged approach to build and operate a headless storefront for **Salesforce B2C Commerce**:
    - **PWA Kit**: the front-end framework/tooling for building the shopper experience.
    - **Managed Runtime**: the hosting/operations layer required to run a decoupled storefront reliably at scale (deploy/host/monitor), instead of relying on the commerce platform to operate the storefront front end.
- **Commerce PWA Kit (PWA Kit)**:
    - Described as a **React**-based framework for creating storefronts.
    - Includes **project templates** (a customizable reference storefront implementing core ecommerce flows, from home page through checkout), so teams can start from a working baseline rather than building from scratch.
    - Provides a rendering approach that supports **server-side rendering** and **client-side rendering**, including **hydration** (so pages can be rendered fast and then become interactive).
    - Provides a routing system that enables injecting data from the **Commerce API** into components.
    - Includes utility functions and scripts to automate common development tasks.
    - Integrates with **B2C Commerce API** and **Open Commerce API (OCAPI)**.
    - Supports essential **progressive web app** capabilities (PWA features).
- **What a PWA is (as framed in the unit)**:
    - A **progressive web app (PWA)** is a website that progressively adds native-app-like capabilities depending on browser/device support.
    - The unit highlights benefits such as fast page loads, smooth rendering/transitions, **offline support**, and **home screen installation**. PWAs work on desktop and mobile through standards-compliant browsers.
- **Commerce Managed Runtime**:
    - Positioned as the operational foundation for a headless storefront: provides infrastructure to **deploy, host, and monitor** the storefront front end.
    - Emphasizes “time to market” and operational offload, and highlights reliability/scale (the unit cites historical **99.99% uptime**).
    - Helps teams evolve customer experiences independently of the back-end commerce engine while still maintaining trust, scalability, and operational control.
- **How the pieces connect**:
    - **B2C Commerce** continues to provide core commerce services (for example: pricing, promotions, search, and capabilities such as **Einstein**).
    - **PWA Kit** renders the shopper experience, calling the **Commerce API** / related APIs to fetch commerce data and execute commerce actions.
    - **Managed Runtime** runs that storefront application in production, handling the operational lifecycle.
- **Practical next step**:
    - The unit points learners to a **Quick Start** path to try PWA Kit with demo settings and get hands-on experience.

## Tiếng Việt (tóm tắt — giữ nguyên thuật ngữ chuyên ngành)

- **Headless commerce** tách rời storefront **front end** (“the head”) khỏi commerce **back end**, giúp team phát triển trải nghiệm nhanh hơn; **APIs** là cầu nối giữa hai lớp. Unit định hướng đây là cách để innovate trên nhiều devices/touchpoints mà không bị ràng buộc bởi storefront stack tightly-coupled.
- **Commerce PWA Kit** và **Commerce Managed Runtime** được trình bày như một bộ giải pháp để xây và vận hành headless storefront cho **Salesforce B2C Commerce**:
    - **PWA Kit**: framework/tooling để xây shopper experience.
    - **Managed Runtime**: lớp hosting/operations bắt buộc cho storefront decoupled (deploy/host/monitor), thay vì trông chờ commerce platform vận hành front end.
- **Commerce PWA Kit (PWA Kit)**:
    - Là framework dựa trên **React** để tạo storefront.
    - Có **project templates** (reference storefront có thể tùy biến, implement core ecommerce flows từ home page đến checkout) giúp khởi đầu nhanh, không phải build từ đầu.
    - Có cơ chế rendering hỗ trợ **server-side rendering** và **client-side rendering**, kèm **hydration** để vừa nhanh hiển thị vừa tương tác được.
    - Có routing system cho phép inject data từ **Commerce API** vào components.
    - Có utility functions/scripts để tự động hóa tác vụ phát triển thường gặp.
    - Tích hợp **B2C Commerce API** và **Open Commerce API (OCAPI)**.
    - Hỗ trợ các tính năng cốt lõi của **progressive web app** (PWA features).
- **PWA là gì (theo cách unit mô tả)**:
    - **progressive web app (PWA)** là website “tiến hóa” dần, bổ sung native-app-like capabilities tùy browser/device hỗ trợ.
    - Unit nhấn mạnh: tải trang nhanh, render/transition mượt, **offline support**, và **home screen installation**; chạy được trên desktop và mobile qua browser tuân chuẩn.
- **Commerce Managed Runtime**:
    - Là nền tảng vận hành cho headless storefront: cung cấp hạ tầng để **deploy, host, monitor** storefront front end.
    - Nhấn mạnh giảm gánh vận hành và tăng “time to market”; nêu độ tin cậy/scale (unit đề cập historical **99.99% uptime**).
    - Cho phép phát triển customer experience độc lập với back-end commerce engine nhưng vẫn đảm bảo trust/scalability/operational control.
- **Cách các thành phần kết nối**:
    - **B2C Commerce** vẫn cung cấp core commerce services (ví dụ: pricing, promotions, search, và các khả năng như **Einstein**).
    - **PWA Kit** render shopper experience và gọi **Commerce API**/các APIs liên quan để lấy dữ liệu và thực thi hành động commerce.
    - **Managed Runtime** chạy storefront app khi lên production và quản lý vòng đời vận hành.
- **Bước tiếp theo để thực hành**:
    - Unit dẫn tới **Quick Start** để thử PWA Kit với demo settings và làm hands-on.