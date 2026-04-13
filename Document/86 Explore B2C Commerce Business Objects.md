# Explore B2C Commerce Business Objects
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects

## EN (A-level: detailed; follow Topics)
### Learning Objectives
After completing this unit, you’ll be able to:
- Explain how business objects define the Salesforce Agentforce Commerce for B2C storefront data structure.
- List two reasons why you would customize system objects.
- List two reasons why you would use custom objects.
- List the two business object best practices. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Introduction
- Agentforce Commerce for B2C is an **object-oriented system**; start with objects as basic principle. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- An **object** is a self-contained entity that contains data.
- A single object is organized so the data describes the object (example: Dress with Size, Color, Fabric, Occasion, Sleeves, Neckline, Length). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- The Dress object contains only data about the dress (not about a bracelet, etc.). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Data is stored in fields also known as **attributes**; attributes describe aspects of an object (Dress = object, Color = attribute). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Business objects define the structure of storefront data:
    - **system objects** (come with the system)
    - **custom objects** (add capability; require custom code). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### System Objects
- Agentforce Commerce for B2C provides **63 system object types** (from Appeasement to TrackingRef). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Some are marked read-only in your version of Business Manager.
- You can’t customize the internal system by creating new system objects, but you can create new custom system objects to meet business needs (distinction noted). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- System object types define the attributes contained in system objects; they act like a map. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- SFRA uses system objects to describe parts of its site:
    - helpful as a starting point because it was developed to interact with system objects, reducing the need for custom code. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Benefit stated:
    - system objects cover most data you need (products, content, orders, promotions), speeding implementation by leveraging existing code for those objects. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Extend System Objects
Reasons to extend system objects (two+ are explicit): ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- collect more information from shoppers
- tailor storefront to show additional information
- process orders more efficiently (back-office needs)
  Example:
- Add `addToEmailList` attribute to the basket object to show a “Please Add Me To Your Email List” checkbox on the cart page; you must add code to display and process the data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Group Objects to Collect More Data
- Business Manager manages storefront data (product, content details). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- System objects have a standard set of attributes, but you can add attributes to add more data.
- Example scenario: in-store pickup:
    - add an attribute so shoppers can pick up items in a brick-and-mortar store
    - unit says this attribute group is already added as **InStorePickup** (an attribute group). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Where it shows up:
    - On storefront: feature shows at checkout.
    - In Business Manager: appears on product details page so you can mark products as available for in-store pickup. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Important rule:
    - To show a system attribute within Business Manager, the attribute must belong to a group; otherwise it won’t appear on a Business Manager page (not the same as appearing in the storefront). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Attribute Groups
- Product system object includes attribute group **InStorePickup** with attributes: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
    - `availableForInStorePickup` — Boolean (yes/no): product available for in-store pickup
    - `storeTaxClass` — String: store the tax class
- The group displays in Business Manager on the product details page (new product creation) to specify availability.
- On cart page on storefront, a field asks if shopper wants to pick up one or more items at the store. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Storage scope:
    - System objects can be stored globally (organization-wide/all sites) or local (per site); the system object itself is always available organization-wide. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Custom Objects
- Use custom objects to extend the model to suit business needs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Workflow in Business Manager:
    1) create **custom object types**
    2) define their attributes
    3) create custom objects based on those attributes ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Custom object types are available to all storefront sites in the organization.
- When creating a custom object, you can choose whether it’s site-specific or organization-wide. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Custom Object Types
- Create/manage custom object types for additional business objects required by storefront/business logic. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Example:
    - Custom object type `Sample` with attributes `SKU` and `Date`
    - Create data pairs like:
        - AS-12334 | 06-03-2025
        - AS-44567 | 24-03-2025
        - TT-65443 | 15-02-2025 ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Making a Custom Attribute Editable or Not
- Use a custom attribute fed directly from an external system of record.
- Set the **externally managed** flag on the new attribute.
- Meaning:
    - indicates users shouldn’t edit these attributes directly (values set in an external system). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Fixing incorrect feed value:
    - deselect Externally Managed, manually fix in Business Manager, then reselect Externally Managed. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Best Practices (the two explicitly listed)
- Use **system objects** instead of custom objects whenever possible to make it easier to upgrade to the latest reference architecture and eliminate unnecessary customization.
- Use **system attributes** instead of custom attributes whenever possible. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Next Steps
- The unit summarizes exploring Business Manager, development environment, SFRA, and business objects; then directs you to the knowledge check/badge. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

---

## VI (A-level: chi tiết; theo Topics; giữ thuật ngữ)
### Mục tiêu học
- Giải thích business objects định nghĩa cấu trúc dữ liệu storefront như thế nào.
- Liệt kê 2 lý do customize system objects.
- Liệt kê 2 lý do dùng custom objects.
- Liệt kê 2 best practices cho business objects. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Introduction
- Agentforce Commerce for B2C là hệ thống **object-oriented**, nên cần nắm object fundamentals. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- **Object** là một thực thể tự chứa (self-contained) có data.
- Ví dụ Dress object gồm Size/Color/Fabric/Occasion/Sleeves/Neckline/Length; chỉ chứa data mô tả “dress”, không chứa data mô tả thứ khác. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Field còn gọi là **attribute**; attribute mô tả một khía cạnh của object (Dress = object; Color = attribute). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Business objects định nghĩa cấu trúc dữ liệu storefront:
    - **system objects** (có sẵn)
    - **custom objects** (mở rộng thêm capability; cần custom code). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### System Objects
- Có **63 system object types** (Appeasement → TrackingRef); một số read-only trong Business Manager. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Không tạo system objects mới để customize “internal system”, nhưng có thể tạo custom system objects mới theo nhu cầu (distinction quan trọng). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- System object types định nghĩa các attributes trong system objects; “act like a map”. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- SFRA tương tác với system objects, nên dùng SFRA làm starting point giúp giảm nhu cầu custom code. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- System objects cover phần lớn data cần (products/content/orders/promotions) → tăng tốc implementation nhờ tận dụng code có sẵn. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Extend System Objects (lý do + ví dụ)
- Extend để:
    - collect thêm thông tin từ shopper
    - tailor storefront để hiển thị thêm thông tin
    - xử lý orders hiệu quả hơn theo back-office needs ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Ví dụ `addToEmailList` cho basket → hiện checkbox “Please Add Me To Your Email List” ở cart; cần code hiển thị và xử lý. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Group Objects to Collect More Data
- Business Manager quản lý storefront data (product/content details).
- Có thể thêm attributes cho system objects để có thêm data.
- Ví dụ feature pick up tại cửa hàng: tạo attribute group **InStorePickup**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Hiển thị:
    - storefront: xuất hiện ở checkout
    - Business Manager: nằm ở product details page để set product available for in-store pick-up ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Quy tắc quan trọng:
    - Muốn attribute hiện trong Business Manager thì attribute phải thuộc một group; nếu không, không hiện trên trang Business Manager (khác với chuyện hiện trên storefront). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Attribute Groups
- Product system object có group **InStorePickup** gồm: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
    - `availableForInStorePickup` — Boolean (yes/no)
    - `storeTaxClass` — String
- Group này xuất hiện ở Business Manager (product details page) để chọn yes/no.
- Ở storefront cart page có field hỏi shopper muốn pick up ở store không. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Scope lưu trữ:
    - system objects có thể global hoặc local (per site); bản thân system object luôn available toàn organization. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Custom Objects / Custom Object Types
- Custom objects dùng để mở rộng model theo nhu cầu business. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Trong Business Manager:
    - tạo custom object types + định nghĩa attributes → tạo custom objects dựa trên đó. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Custom object types dùng được cho tất cả sites; khi tạo custom object có thể chọn site-specific hay organization-wide. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))
- Ví dụ type `Sample` với `SKU`, `Date` và các cặp dữ liệu minh họa. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Making a Custom Attribute Editable or Not
- Attribute được feed từ external system → set flag **Externally Managed**.
- Ý nghĩa: BM users không nên edit trực tiếp.
- Nếu feed sai: bỏ chọn Externally Managed → sửa tay → chọn lại. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))

### Best Practices (2 ý)
- Ưu tiên **system objects** thay vì custom objects để dễ upgrade SFRA/reference architecture và tránh customization không cần thiết.
- Ưu tiên **system attributes** thay vì custom attributes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital-for-developers/digital-business-objects))