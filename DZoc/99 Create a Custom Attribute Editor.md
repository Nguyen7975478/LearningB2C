# Create a Custom Attribute Editor
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-custom-attribute-editor

## EN (A-level: detailed; faithful to the unit’s intent + aligned with official Page Designer guidance; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Explain when you should use a custom attribute editor.
- Identify the core files required to build a custom attribute editor.
- Describe how a component type attribute is wired to a custom attribute editor.
- Explain (at a high level) how the editor runs in Page Designer and communicates with the host. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 1) Why Custom Attribute Editors Exist
- In Page Designer, the `type` value you assign to a component attribute determines which **UI control** the merchandiser uses in the Visual Editor (for example, checkbox/file picker/list). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
- If none of the preconfigured controls match your need (for example: choose store locations on a map, choose a color, place a special icon, choose which “Shop Now” button), you create a **custom attribute editor**. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
- A custom attribute editor:
    - does not conflict with Page Designer platform code, and
    - you can create more than one custom attribute editor for a single component type. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 2) Core Concept: Wiring a Component Attribute to a Custom Editor
### 2.1 In the component type meta definition
- For the attribute that should use your custom UI, set:
    - `"type": "custom"`
- Then add an `editor_definition` element that identifies:
    - the custom attribute editor **ID**
    - optional configuration payload (passed into the editor). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 2.2 What configuration is for
- Configuration in `editor_definition` is how you pass editor options (for example, a list of allowed values or display options) into the editor. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 3) Files and Locations You Need (Server side + Client side)
A custom attribute editor uses:
- a meta definition file (JSON),
- a server-side script file (JS),
- and client-side JavaScript and CSS resources that run in the Visual Editor. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 3.1 Where the editor meta definition JSON goes
- Put the editor JSON under:
    - `{your_bm_cartridge}/cartridge/experience/editors`
    - (or a subdirectory under it). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
- Naming rule:
    - file name must be only alphanumeric or underscore characters,
    - subdirectory names must also be only alphanumeric or underscore characters. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 3.2 Where the cartridge must be configured
- The cartridge that contains:
    - editor meta definition JSON,
    - editor script (.js),
    - client-side JS/CSS
      must be added to the **cartridge path for the Business Manager site**. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 3.3 Script file rule (server-side)
- Each custom attribute editor requires a script file with:
    - the same base name as the meta definition JSON,
    - but with `.js` extension.
      (Example: `magical.json` → `magical.js`). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 3.4 Referencing client resources (JS/CSS)
- The editor meta definition lists the JS/CSS resources required by the editor.
- You can use fully-qualified URLs or relative URLs.
- Relative URLs are resolved to the `/static/default` directory of the cartridge. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 4) Runtime Model: How the Editor Runs in the Visual Editor
### 4.1 Sandbox isolation via iframe
- Each custom attribute editor runs inside a host component that contains an HTML `<iframe>`.
- The iframe isolates the editor code and style so different editors don’t interfere with each other. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 4.2 Messaging channel: host ↔ editor
- Page Designer provides management code in the iframe that supports:
    - `subscribe`
    - `emit`
- The host and editor communicate by sending predefined events with serializable payloads. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 4.3 Common event pattern (high-level)
- The editor subscribes to a “ready” event (example mentioned: `sfcc:ready`).
- After initialization, when the user changes a value, the editor emits a value event (example mentioned: `sfcc:value`) to inform the host. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 5) (Optional capability) Breakout / Modal Editor for More Space
- The right pane of the Visual Editor can be constrained.
- You can implement a trigger editor that opens a breakout editor in a modal window to provide more space (example narrative: select an image set, then Apply). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 6) Summary Checklist (A-level, practical)
To build a custom attribute editor you typically do:
1) In component type JSON: set attribute `type` to `custom`, add `editor_definition` with editor ID (+ optional configuration). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
2) Create editor meta definition JSON under `{bm_cartridge}/cartridge/experience/editors`. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
3) Create matching editor script file (`sameName.js`). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
4) Add client JS/CSS resources and reference them from the editor meta definition (relative URLs resolve to `/static/default`). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
5) Ensure the cartridge is on the Business Manager site cartridge path. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
6) Validate the editor runs isolated (iframe) and communicates via subscribe/emit events. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## VI (A-level: chi tiết; bám sát ý của unit + đúng thuật ngữ)

### Mục tiêu học
Sau khi hoàn thành unit, bạn có thể:
- Giải thích khi nào nên dùng custom attribute editor.
- Nhận diện các file bắt buộc để xây custom attribute editor.
- Mô tả cách “wire” (gắn) một component attribute vào custom attribute editor.
- Giải thích tổng quan editor chạy trong Page Designer thế nào và giao tiếp với host ra sao. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 1) Khi nào cần Custom Attribute Editor?
- Trong Page Designer, giá trị `type` của attribute quyết định UI control mà merchandiser dùng trong Visual Editor (checkbox, file picker, list…). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
- Nếu các UI controls có sẵn không phù hợp (ví dụ: chọn store locations trên map, chọn màu, đặt icon đặc biệt, chọn kiểu nút “Shop Now”), thì tạo **custom attribute editor**. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
- Custom attribute editor:
    - không xung đột với platform code,
    - có thể tạo nhiều editor cho một component type. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 2) Nguyên tắc “wire” từ component attribute → custom editor
### 2.1 Trong component type meta definition
- Attribute cần editor custom phải đặt:
    - `"type": "custom"`
- Thêm `editor_definition` để chỉ định:
    - **editor ID**
    - cấu hình tùy chọn (optional) truyền vào editor. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 2.2 Cấu hình dùng để làm gì?
- `editor_definition.configuration` là nơi truyền options vào editor (ví dụ danh sách lựa chọn/nhóm lựa chọn/cách hiển thị). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 3) File & vị trí cần có
Custom attribute editor gồm:
- meta definition JSON,
- script JS (server-side),
- client-side JS/CSS chạy trong Visual Editor. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 3.1 Vị trí editor JSON
- Đặt dưới:
    - `{your_bm_cartridge}/cartridge/experience/editors` (hoặc subdirectory). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
- Quy tắc đặt tên:
    - file name + thư mục con chỉ dùng alphanumeric hoặc underscore. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 3.2 Cartridge path (Business Manager site)
- Cartridge chứa editor JSON + editor script + client JS/CSS phải nằm trong **cartridge path của Business Manager site**. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 3.3 Script file bắt buộc
- Tên script trùng JSON (khác extension `.js`):
    - `magical.json` → `magical.js`. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 3.4 Trỏ resource JS/CSS
- Editor JSON liệt kê JS/CSS cần dùng.
- Có thể dùng URL tuyệt đối hoặc tương đối.
- URL tương đối sẽ được resolve về `/static/default` của cartridge. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 4) Cách editor chạy trong Visual Editor
### 4.1 Iframe isolation
- Mỗi custom attribute editor được bọc bởi host có `<iframe>`.
- Iframe giúp cô lập code/style của editor để nhiều editor không ảnh hưởng nhau. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 4.2 Giao tiếp host ↔ editor (messaging channel)
- Trong iframe có management code cung cấp:
    - `subscribe`
    - `emit`
- Host và editor gửi event qua lại với payload (serializable). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

### 4.3 Mẫu event thường gặp
- Editor subscribe `sfcc:ready` để khởi tạo.
- Khi user thay đổi giá trị, editor emit `sfcc:value` để báo cho host. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 5) Breakout/Modal editor (khi cần nhiều không gian)
- Pane bên phải của Visual Editor có thể hẹp.
- Có thể tạo trigger editor mở breakout editor trong modal để thao tác chọn/lọc/preview dễ hơn. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))

---

## 6) Checklist tóm tắt (thực hành)
1) Component type JSON: attribute `type=custom`, thêm `editor_definition` (editor ID + configuration). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
2) Tạo editor JSON trong `{bm_cartridge}/cartridge/experience/editors`. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
3) Tạo editor script `.js` cùng tên. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
4) Tạo client JS/CSS và khai báo trong editor JSON (relative URL → `/static/default`). ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
5) Đảm bảo cartridge có editor được thêm vào cartridge path của Business Manager site. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))
6) Kiểm tra editor chạy trong iframe và trao đổi event subscribe/emit đúng luồng. ([developer.salesforce.com](https://developer.salesforce.com/docs/commerce/commerce-solutions/guide/b2c-dev-for-page-designer.html?utm_source=openai))  