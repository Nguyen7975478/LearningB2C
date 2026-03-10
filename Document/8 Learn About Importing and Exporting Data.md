# cc-digital-import-export — Import Export Data Basics
https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export

---

## English (Summary — keep technical terms)

### Learning objectives (what you should be able to do)
- Explain why **import/export schema files (XSD)** matter.
- Identify data commonly imported from a **system of record** into B2C Commerce.
- Describe **import modes** and **export modes**.
- Describe the **export process**.
- Explain why a **delta feed** is important. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Why import/export exists
- Most merchants maintain back-end **systems of record** (PIM/ERP/OMS, etc.). **Salesforce B2C Commerce** has its own databases/servers for the storefront.
- **Import/Export** bridges the gap:
    - **Import**: load external-file data into the B2C Commerce database.
    - **Export**: extract B2C Commerce data to external systems as **feeds** (often XML). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### What is *not* “import/export” in this context
- **Data replication** (copying code/data between instances) is separate.
- **Business Manager catalog feed** for third-party files (example mentioned: Certona) is separate.
- **Site import/export** (moving site configuration/settings between instances) is separate from the broader import/export definition here. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Schemas (XSD) and file formats
- **Schema files (XSD)** define the required XML structure and attributes.
- B2C Commerce accepts **XML import files** that match these schemas.
- Exports are usually **XML**; **coupon codes** export as **CSV** (Salesforce recommends using a third-party tool to transform CSV to the required XML when needed). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))
- Example schemas mentioned: `sort.xsd`, `coupon.xsd`, `couponredemption.xsd`, `order.xsd`, `promotion.xsd`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Import modes (global mode per feed) + element-level override
Import mode controls how B2C Commerce interprets objects in an import feed:
- **Merge**: create if missing + update if exists.
- **Update**: update only existing objects; does not create missing objects; leaves unspecified attributes unchanged.
- **Replace**: delete + recreate (removes attributes not provided); effectively “delete then merge”.
- **Delete**: remove an object (typically only the object ID is required; other attributes ignored). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

Notes:
- **Replace** and **Delete** can be risky (you can delete more than intended if you use them broadly).
- Some schemas allow **element-level attribute mode** (notably `delete`) to override the process mode for specific elements—useful when one feed needs to create/update/delete selectively. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Production feeds and delta feeds
- Salesforce recommends **delta feeds** in production (only changes since the previous feed):
    - Smaller to archive, faster to import, easier to troubleshoot.
- However, some schema elements always use **replace** and therefore require full object sets, which conflicts with delta feeds. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### List-type elements behavior
- XML **list-type elements** typically replace the entire list regardless of mode.
- If a list element is omitted:
    - **Merge** keeps the list.
    - **Replace** deletes the list. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Typical import/export process steps
**Import (typical):**
1) Transfer XML to the instance via **WebDAV, SFTP, or HTTPS**.
2) For **staging/production**, set up secure transfer (sandboxes don’t require it).
3) Run import via **Business Manager** or a **custom controller**; use standard **import pipelets** for performance and reliability where possible. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

**Export (typical):**
1) Export via **Business Manager** (schemas) or a **custom controller** (can use **export pipelets** for finer control).
2) Transfer exported files from the instance to the back-end system.
3) Configure secure transfer as needed (example: **PCI-DSS** requirements). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Instance-specific guidance (how usage differs by environment)
- **Sandbox**: often used per developer; set up a “template” sandbox; use **Site Export/Site Import** to share certain configuration/contents across sandboxes (with cautions about which objects can be imported and overwrite risks). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))
- **Staging & Production (PIG)**:
    - Prefer secure, automated movement from system of record using **custom controllers**.
    - For **infrequent feeds**, import into **staging** then replicate to **production** to protect production.
    - For **frequent feeds** (e.g., pricing/inventory every few minutes), import directly to **production** (and often also to staging to keep environments aligned). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))
- **Development**: set up via initial site import/export from staging; then keep updated using **data replication**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

---

## Tiếng Việt (Tóm tắt — giữ nguyên thuật ngữ)

### Mục tiêu bài học
- Nêu lý do vì sao **import/export schema files (XSD)** quan trọng.
- Kể các loại dữ liệu thường import từ **system of record** vào B2C Commerce.
- Mô tả các **import modes** và **export modes**.
- Mô tả **export process**.
- Giải thích vì sao **delta feed** quan trọng. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Import/Export dùng để làm gì
- Doanh nghiệp thường có back-end **systems of record**. **Salesforce B2C Commerce** có DB/servers riêng cho storefront.
- **Import/Export** là cầu nối dữ liệu 2 chiều:
    - **Import**: lấy dữ liệu từ file bên ngoài vào DB của B2C Commerce.
    - **Export**: trích dữ liệu từ B2C Commerce ra thành **feeds** cho hệ thống ngoài (thường XML). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Những thứ KHÔNG phải import/export theo ngữ cảnh unit này
- **Data replication** (copy code/data giữa instances) là chủ đề khác.
- **Business Manager catalog feed** cho third-party files (ví dụ: Certona) là luồng khác.
- **Site import/export** (di chuyển cấu hình/setting của site giữa instances) là loại thao tác riêng. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Schemas (XSD) và định dạng file
- **Schema files (XSD)** định nghĩa cấu trúc XML và các attributes bắt buộc.
- B2C Commerce chỉ nhận **XML import** đúng schema.
- Export thường là **XML**; riêng **coupon codes** export ra **CSV** (Salesforce khuyến nghị dùng công cụ ngoài để transform CSV sang XML khi cần). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))
- Ví dụ schema: `sort.xsd`, `coupon.xsd`, `couponredemption.xsd`, `order.xsd`, `promotion.xsd`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Import modes (mode áp cho cả feed) + override theo element
Các **import modes** quy định cách xử lý objects trong feed:
- **Merge**: object chưa có thì tạo; có rồi thì update.
- **Update**: chỉ update object đã tồn tại; không tạo object mới; attributes không có trong feed thì giữ nguyên.
- **Replace**: xoá rồi tạo lại (mất các attributes không được cung cấp); tương đương “delete rồi merge”.
- **Delete**: xoá object khỏi DB (thường chỉ cần object ID; attributes khác bị ignore). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

Lưu ý:
- **Replace/Delete** dễ gây xoá ngoài ý muốn nếu dùng sai phạm vi.
- Một số schema hỗ trợ **attribute mode** ở mức element (đặc biệt `delete`) để override mode chung cho một phần tử cụ thể, giúp 1 quy trình vừa create/update vừa delete có chọn lọc. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Production feeds và delta feeds
- Khuyến nghị dùng **delta feeds** cho production (chỉ chứa thay đổi so với feed trước):
    - Nhỏ hơn để lưu trữ, import nhanh hơn, dễ troubleshoot hơn.
- Nhưng có schema elements luôn chạy theo **replace** nên cần full dataset mỗi lần → không phù hợp delta feed. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### List-type elements trong XML
- **List-type elements** thường sẽ thay thế cả danh sách, bất kể mode.
- Nếu list element không có trong file:
    - **Merge**: giữ list hiện có.
    - **Replace**: xoá list. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Quy trình Import/Export (tóm tắt bước)
**Import:**
1) Transfer XML lên instance bằng **WebDAV / SFTP / HTTPS**.
2) Với **staging/production**, cấu hình secure transfer (sandbox không bắt buộc).
3) Ch��y import bằng **Business Manager** hoặc **custom controller**; ưu tiên dùng **import pipelets** cho dữ liệu lớn (nhanh, ổn định, tiết kiệm tài nguyên). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

**Export:**
1) Export bằng **Business Manager** (schemas) hoặc **custom controller**; có thể dùng **export pipelets** để điều khiển chi tiết hơn.
2) Transfer file export về hệ thống back-end.
3) Thiết lập secure transfer nếu cần (ví dụ yêu cầu **PCI-DSS**). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))

### Lưu ý theo từng instance type
- **Sandbox**: thường mỗi dev có 1 sandbox; tạo sandbox “mẫu”; dùng **Site Export/Site Import** để chia sẻ một số cấu hình/contents (cần lưu ý các object hỗ trợ và rủi ro overwrite). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))
- **Staging & Production (PIG)**:
    - Dùng **custom controllers** + secure connection để trao đổi với system of record.
    - Feed ít thay đổi: import vào **staging** rồi replicate sang **production** để giảm rủi ro cho production.
    - Feed thay đổi liên tục (pricing/inventory): import trực tiếp vào **production** (thường đồng thời import vào staging để sync). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))
- **Development**: khởi tạo từ site import/export staging → dev; sau đó cập nhật bằng **data replication**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-import-export?utm_source=openai))