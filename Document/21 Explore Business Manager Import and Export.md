# Explore Business Manager Import and Export
https://trailhead.salesforce.com/content/learn/modules/b2c-import-export/b2c-business-manager-import-export

## English

### Learning Objectives
- List three data objects you can transfer via the import/export process.
- Explain the purpose of Salesforce B2C Commerce **XSD files**.
- Explain one benefit of using **Read-Only Price Books**.
- Explain two benefits of **object-specific schema files**.
- Explain how you use instances to roll out storefront data.

### What admins are responsible for (unit context)
- The administrator’s core responsibility is **data management**: transferring storefront data between external systems (system of record) and B2C Commerce.
- Admins also help move **site configuration and settings data** between instances to bring new developer instances online.

### What typically moves via import/export
- Typical **Import** objects called out:
  - **Active data**
  - **Catalog**
  - **Coupons**
  - **Price Books**
- Typical **Export** objects called out:
  - **Coupon redemptions**
  - **Customer records**
  - **Orders**
  - **Order updates** (cancels, returns, shipping)

### XSD files and object-specific schema files
- **XSD schema files** define the required XML structure and validation rules for each import/export file type.
- B2C Commerce uses **object-specific schema files** so each domain object (catalog, customer, order, etc.) has a dedicated schema:
  - `catalog.xsd`
  - `coupon.xsd`
  - `couponredemption.xsd`
  - `customer.xsd`
  - `customeractivedata.xsd`
  - `order.xsd`
  - `pricebook.xsd`
- Key operational point:
  - Business Manager **validates** manually imported files against the XSD.
  - Programmatic imports require programmatic validation by developers.
- Export format note: exports are usually XML, except **coupon codes** export as **CSV**.

### Read-Only Price Books (why it’s a benefit)
- When price data is large and updated frequently in an external **PIM**, **Read-Only Price Books** provide an efficient way to transfer price book data at scale (compared to manual imports).

### Using instances to roll out storefront data
- The unit references the typical safe lifecycle using instance types:
  - **sandbox** for build/test,
  - **staging** for validation,
  - **development** as an additional verification environment,
  - **production** for live shoppers.
- The emphasis is that you don’t push directly to production without validation.

### File and log hygiene
- Archive prior XML, remove older files regularly to avoid accumulation.
- Deleting an import record in Business Manager also removes the related log file.

## Tiếng Việt

### Learning Objectives
- Liệt kê ba data objects có thể transfer bằng import/export.
- Giải thích mục đích của **XSD files** trong B2C Commerce.
- Nêu một lợi ích của **Read-Only Price Books**.
- Nêu hai lợi ích của **object-specific schema files**.
- Giải thích cách dùng instances để roll out storefront data.

### Trách nhiệm của admin (bối cảnh unit)
- Trọng tâm là **data management**: chuyển dữ liệu storefront giữa external systems (system of record) và B2C Commerce.
- Admin cũng hỗ trợ chuyển **site configuration và settings data** giữa instances để bring up developer instances.

### Dữ liệu thường import/export
- **Import** thường gồm:
  - **Active data**
  - **Catalog**
  - **Coupons**
  - **Price Books**
- **Export** thường gồm:
  - **Coupon redemptions**
  - **Customer records**
  - **Orders**
  - **Order updates** (cancels, returns, shipping)

### XSD files và object-specific schema files
- **XSD schema files** định nghĩa cấu trúc XML và rules để validate import/export.
- B2C Commerce dùng **object-specific schema files** theo từng loại dữ liệu:
  - `catalog.xsd`, `coupon.xsd`, `couponredemption.xsd`, `customer.xsd`,
    `customeractivedata.xsd`, `order.xsd`, `pricebook.xsd`
- Điểm vận hành:
  - Import thủ công trong Business Manager được **validate** theo XSD.
  - Import programmatic cần developer validate programmatic.
- Lưu ý export: phần lớn XML, riêng **coupon codes** export ra **CSV**.

### Read-Only Price Books (lợi ích)
- Với dữ liệu giá lớn và cập nhật thường xuyên từ external **PIM**, **Read-Only Price Books** giúp transfer price books hiệu quả hơn so với import thủ công.

### Dùng instances để roll out data
- Unit nhấn mạnh quy trình an toàn theo instance types:
  - **sandbox** build/test,
  - **staging** validate,
  - **development** verify thêm,
  - **production** cho live.
- Tránh đẩy thẳng production khi chưa validate.

### Hygiene cho files/logs
- Archive XML cũ, dọn file cũ định kỳ.
- Xóa import record trong Business Manager sẽ xóa luôn log file liên quan.