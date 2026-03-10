# Understand Import Modes
https://trailhead.salesforce.com/content/learn/modules/b2c-import-export/b2c-explore-import-modes

## English

### Learning Objectives
- Explain the purpose of the import modes.
- List two modes that add new objects via import.
- Describe how you can delete data using import.
- Explain the two general ways you can import or export data.
- Describe how Salesforce B2C Commerce is designed to handle storefront data.

### Schemas vs modes
- **Schemas** define XML structure rules.
- **Modes** define what happens to the data at import.

### The four import modes (global mode)
- **Merge**: add new objects if they don’t exist + update existing objects.
- **Update**: update existing objects only; does not add new objects; only updates attributes present in XML.
- **Replace**: re-create objects based on XML; removes existing attributes not present in XML; effectively delete + merge.
- **Delete**: deletes objects included in the XML, even if the object’s data is unchanged.

### The unit’s database outcome concept (what changes and what doesn’t)
- Objects not in the XML file are unaffected (example in unit: object E remains because it wasn’t in the XML file in those scenarios).
- “Mode alone” doesn’t remove a specific attribute value unless the file expresses the change:
    - Example given: to remove a “Facebook flag” attribute, set the value to none/blank in XML, then import with **merge** or **update**.

### Deleting data using import (two methods)
1) Create an XML containing only objects you want to remove and import in **delete** mode.
2) Use element-level delete: set `mode="delete"` on specific elements inside a feed.

### Modes for elements (element-level override)
- Element-level mode overrides global mode.
- The unit’s example: one XML file contains new `<product>` elements (no explicit mode) plus `<product ... mode="delete">` elements; run global **merge** to add new products and delete selected products in one pass.

### Catalog Import/Export (storefront data design)
- B2C Commerce import/export is designed for storefront data intricacies.
- Best practice: two catalogs:
    - **storefront catalog** (display/navigation)
    - **product catalog** (imported structure from external **PIM**)
- Catalog import semantics highlighted:
    - Import a storefront catalog independent of the product catalog.
    - Storefront catalog categories can reference products in that category.
    - Imports of other storefront catalogs don’t affect existing product/category assignments.
    - Product catalog updates don’t affect category assignments in storefront catalogs.
    - Storefront and product catalogs are treated as self-contained data units so you can import one without deleting the other’s structure.

## Tiếng Việt

### Learning Objectives
- Giải thích mục đích của import modes.
- Liệt kê hai modes có thể add objects qua import.
- Mô tả cách delete data bằng import.
- Giải thích hai cách tổng quát để import/export.
- Mô tả B2C Commerce được thiết kế để xử lý storefront data thế nào.

### Schemas vs modes
- **Schemas** định nghĩa rules cấu trúc XML.
- **Modes** quyết định dữ liệu được xử lý thế nào khi import.

### 4 import modes (global mode)
- **Merge**: add objects mới nếu chưa có + update objects hiện có.
- **Update**: chỉ update objects đã tồn tại; không add objects mới; chỉ update attributes có trong XML.
- **Replace**: re-create objects theo XML; xóa attributes hiện có nhưng không có trong XML; tương đương delete + merge.
- **Delete**: xóa objects có trong XML, kể cả khi object không thay đổi nội dung.

### Ý nghĩa “kết quả trong database”
- Objects không nằm trong XML sẽ không bị ảnh hưởng.
- Chỉ chọn mode chưa đủ để gỡ một attribute value nếu file không biểu diễn thay đổi:
    - Ví dụ unit: muốn remove “Facebook flag” attribute thì set value none/blank trong XML rồi import bằng **merge** hoặc **update**.

### Xóa data bằng import (2 cách)
1) Tạo XML chỉ chứa objects cần xóa rồi import bằng **delete** mode.
2) Dùng element-level delete bằng cách đặt `mode="delete"` trên element cần xóa.

### Modes for elements (override theo element)
- Mode ở element-level override global mode.
- Ví dụ unit: 1 XML có products mới + products cần xóa (`mode="delete"`); chạy global **merge** để vừa add vừa delete.

### Catalog Import/Export (thiết kế cho storefront data)
- Import/export được thiết kế để xử lý storefront data intricacies.
- Best practice: dùng 2 catalogs:
    - **storefront catalog** (display/navigation)
    - **product catalog** (mirror external **PIM**)
- Catalog import semantics:
    - Import storefront catalog độc lập với product catalog.
    - Category storefront có thể reference products.
    - Import storefront catalog khác không ảnh hưởng assignments hiện có.
    - Update product catalog không ảnh hưởng category assignments của storefront catalogs.
    - Storefront/product catalogs được xem là self-contained units nên import một cái không làm mất cấu trúc cái còn lại.