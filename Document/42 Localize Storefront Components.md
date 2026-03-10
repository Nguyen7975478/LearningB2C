# Localize Storefront Components
https://trailhead.salesforce.com/content/learn/modules/b2c-localization/b2c-localize-storefront-components

## English

## Learning Objectives
- List the steps of the Salesforce B2C Commerce localization process.
- List the steps of the translation process for text versus source files.
- Explain how **resource files** work.
- Explain how to localize images and **URLs**.

## Localization process (the unit’s 3-step framework)
Step 1 — Identify components that require localization:
- Examples called out: content assets, products, product attributes, currency.
- Also identify any storefront text embedded inside graphics (buttons, banners with text).

Step 2 — Identify supported languages and how they interrelate:
- Example strategy: US and Spanish storefront versions may share the same underlying business objects so storefront selection determines which file set is used.
- Europe strategy can differ: offer unique products by country → unique catalog data per locale.

Step 3 — Structure localized components:
- Decide how to structure localized components using templates and properties files.
- B2C Commerce uses the **cartridge** structure to deliver localized storefront assets and code.

## Identify the components (concrete checklist)
The unit lists activities Brandon and Vijay perform:
1) Create language-specific folders (example: `es_US`)
2) Identify images (for example buttons) that contain locale-specific text
3) Identify only templates used by the storefront (scope what needs translation)
4) Identify JavaScript files where locale-specific text is used
5) Identify other product/category/content images that contain locale-specific text
   Note: The unit also states some situations exist where localization isn’t possible.

## Translation steps: Text (business objects) vs Source files (cartridge assets)
### Translate content, category, and product text
Steps listed:
1) Export content, category, or products
2) Translate the content, category, or products
3) Import the content and use Business Manager for further editing
4) Translate shipping method name and description (these appear during checkout)

### Translate source files (templates/JS/images)
Steps listed:
1) Create language-specific folders (example: `es_US`)
2) Identify images with locale-specific text
3) Identify templates used in the storefront
4) Identify JavaScript files where locale-specific text is used
5) Identify other images needing translation
6) Translate files and store them under the locale folder (images often must be recreated in the original design tool)
7) Run full regression test and QA for localized content
8) Update header/sidebar to include a language selection UI (select box) for the session

## Localize templates and forms
- **Templates** transform data/page info into HTML pages.
- **Form definitions** control validation and rendering of shopper-entered values.
- You can use one template set for all locales or unique template sets per locale (depending on design).

## Resource bundles (resource files) and best practice
- Best practice: separate translatable strings from templates into translated **resource files**.
  Benefits listed:
- Templates don’t need modification when text changes
- Display logic stays in one place (non-language-specific template)
- Externalized strings are in a simple format for translation providers
- Integration is safer: copy translated file into cartridge without breaking logic

### Where resource bundles live + how they’re accessed
- Resource bundles store localized static content (example: error messages).
- Stored under `/templates/resources` (and similarly for forms).
- Templates access messages via `dw.web.Resource` API method `msg()`.

## Localize forms (structure differences by locale)
- Localization can require changing form structure (example: state vs province fields).
- Can change validation/processing logic (example: zip/postal code structure by country).
- The unit shows a folder structure pattern:
    - `forms/default/billingaddress.xml`
    - `forms/it_IT/billingaddress.xml`
    - `forms/ja_JP/billingaddress.xml`

## Localize images and URLs
- Localizing images means translating text/symbols embedded in the images.
- The unit emphasizes knowing where these source files live so they can be sent to translation services.
- The unit also includes localizing URLs as part of storefront localization work.

## Tiếng Việt

## Learning Objectives
- Liệt kê các bước của localization process trong B2C Commerce.
- Liệt kê các bước dịch cho text vs source files.
- Giải thích **resource files** hoạt động thế nào.
- Giải thích cách localize images và **URLs**.

## Localization process (khung 3 bước của unit)
Bước 1 — Xác định components cần localization:
- Ví dụ: content assets, products, product attributes, currency.
- Đồng thời xác định text nằm trong graphics (buttons/banners có chữ).

Bước 2 — Xác định languages hỗ trợ và cách chúng “liên hệ”:
- Ví dụ: US và Spanish share underlying business objects; chọn location/language sẽ chọn đúng file set.
- Europe có thể cần catalog data riêng theo country nếu offer products theo từng nước.

Bước 3 — Structure localized components:
- Quyết định cấu trúc localized components bằng templates và properties files.
- B2C Commerce dùng **cartridge** structure để deploy localized assets/code.

## Identify the components (checklist cụ thể)
Các việc Brandon và Vijay làm:
1) Tạo language-specific folders (ví dụ `es_US`)
2) Xác định images có locale-specific text (buttons…)
3) Chỉ chọn templates thật sự dùng trên storefront để dịch
4) Xác định JavaScript files có locale-specific text
5) Xác định các product/category/content images có text cần dịch
   Ghi chú: có một số trường hợp localization không khả thi.

## Translation steps: Text vs Source files
### Dịch content/category/product text
Steps:
1) Export content/category/products
2) Dịch
3) Import lại và chỉnh tiếp trong Business Manager
4) Dịch shipping method name/description (hiển thị ở checkout)

### Dịch source files (templates/JS/images)
Steps:
1) Tạo folders theo locale (ví dụ `es_US`)
2) Xác định images có text
3) Xác định templates dùng trên storefront
4) Xác định JavaScript files có text theo locale
5) Xác định images khác cần dịch
6) Dịch và lưu vào locale folder (images thường phải recreate bằng tool thiết kế gốc)
7) Regression test + QA
8) Thêm language selection UI (select box) ở header/sidebar cho session

## Localize templates và forms
- **Templates** biến dữ liệu thành HTML pages.
- **Form definitions** kiểm soát validation và rendering input của shopper.
- Có thể dùng một template set cho mọi locale hoặc template set riêng theo locale.

## Resource bundles (resource files) và best practice
- Best practice: tách strings ra khỏi templates và lưu trong translated **resource files**.
  Lợi ích:
- Không cần sửa templates khi text đổi
- Logic hiển thị nằm một nơi (template không phụ thuộc ngôn ngữ)
- Strings dễ gửi cho translation providers
- Tích hợp an toàn: copy file dịch vào cartridge, giảm rủi ro break logic

### Vị trí và cách gọi resource bundles
- Resource bundles chứa localized static content (ví dụ error messages).
- Nằm trong `/templates/resources` (và tương tự cho forms).
- Templates gọi thông qua `dw.web.Resource` method `msg()`.

## Localize forms (khác cấu trúc theo locale)
- Có thể cần đổi form structure (state vs province).
- Có thể đổi validation/processing (zip/postal code).
- Pattern folder:
    - `forms/default/billingaddress.xml`
    - `forms/it_IT/billingaddress.xml`
    - `forms/ja_JP/billingaddress.xml`

## Localize images và URLs
- Localize images = dịch text/symbols trong images.
- Cần biết vị trí source files để gửi dịch.
- Unit cũng xem localizing URLs là một phần của localization storefront.