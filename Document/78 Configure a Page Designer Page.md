# Configure a Page Designer Page
https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-merchandiser/b2c-page-designer-configure-page?trail_id=set-up-merchandising-for-your-storefront

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain the difference between the **Page Structure** and **Components** views.
- List three important Page Designer configuration settings.
- Note two ways you can control how you display or hide a component.

## What this unit is really teaching (so you understand the “why”)
This unit is about turning “a page shell” into a controlled merchandising experience by configuring:
- **Structure** (where components go)
- **Visibility** (who sees what, and when)
- **Localization** (what shoppers see in each locale, including fallback)
- **SEO settings** (how the page is found)
  It also teaches how to understand Page Designer’s UI: **Page Structure** vs **Components**.

## Page Designer UI: Page Structure vs Components (clear mental model)
### Page Structure view (layout + hierarchy)
- Shows the page’s **regions** and the **component tree** (what is placed where).
- You use it to:
    - insert components into a region,
    - re-order components (top-down order matters later for visibility),
    - create nested structures (for example a carousel containing slides).

Think of it as: **“page blueprint + placement order”**.

### Components view (palette of building blocks)
- Shows the **available component types**.
- You use it to:
    - drag components into regions,
    - discover what types exist (Banner, Carousel, Image With Text, etc.).

Think of it as: **“toolbox / component catalog”**.

Why this matters:
- If you’re trying to change “where something appears” you must be in **Page Structure**.
- If you’re trying to “find something to add” you must be in **Components**.

## Create a Page Designer page (step-by-step workflow from the unit)
Brandon creates a new page using the Visual Editor.

1) In **Business Manager**, select **App Launcher** → **Merchant Tools | Content | Page Designer**
2) Click **New**
3) Select a **page type**
4) Click **Next**
5) Assign **categories** (one or more) → **Next**
6) Assign **products** (one or more) → **Next**
7) Select language (**default**)
8) Enter page name (Business Manager creates the **ID** as you type the name)
9) (Optional) enter description
10) Review settings
11) Click **Save & Create**

Important meaning of category/product assignment:
- It ties the page to a merchandising context (for example: “this layout applies to these products”).
- It also supports reuse: the same page type can be applied to many products/categories.

## Three important Page Designer configuration settings (Page Settings)
After saving, Brandon configures page settings via the **Page Settings** icon.

### 1) Localization (per-locale visibility and content variants)
- Brandon “toggles **Visible**” for the selected locale to set the page:
    - **visible** or
    - **hidden**
- This controls whether the page variant is available to shoppers for that locale.

Why it matters (understanding):
- You can build the page in default locale first, then progressively localize.
- You can keep a locale variant hidden until translation and images are ready.

### 2) Targeting / Scheduling (who sees it and when)
Brandon controls visibility by:
- **Customer Group** (for example a VIP-like segment such as “Big Spenders”)
- **Schedule / date range** (display from/to dates)

Critical technical detail (from the unit):
- Display times correspond to the **shopper’s browser time**, not the storefront instance time.

Why that detail matters:
- A “midnight launch” is not one global moment—different shoppers’ browsers can be in different time zones.
- For global campaigns, you must plan schedules carefully (or coordinate by region/locale and test).

### 3) SEO settings (how the page is discoverable)
Brandon configures SEO-related fields:
- **Page Address (URL)**
- **page title**
- **page description**
- up to **10 metadata keywords**

Why it matters:
- These fields help external search engines understand and index the page.
- Without SEO configuration, a landing page might exist but be hard to find organically.

## Locale fallback hierarchy (how Page Designer decides what content to show)
This is the key “understand the idea” part of the unit.

### Example fallback hierarchy in the unit
- `fr_CA (French Canadian) > fr (French) > default`

Best practice stated:
- Create base-language content and name it **default**.

### What happens when the page is created
- When you create a page in the **default locale**, Page Designer automatically creates page **variants** for each locale in the fallback hierarchy.
- For each component on the page, you can either:
    - localize content at the component level for that locale, or
    - allow the component to inherit content via fallback.

### What shoppers see if localized content is missing
- If `fr_CA` doesn’t have localized content:
    - Page Designer displays `fr` content.
- If `fr` also doesn’t have localized content:
    - Page Designer displays **default** content.

### How to visually identify fallback vs localized components (UI cues)
Steps from the unit:
1) Open Page Designer → open the page
2) Select the `fr-CA` locale
3) Move the mouse over each component:
    - **Pink box** + label **Fallback**:
        - component is not localized for the selected locale, so it displays fallback content
    - **Blue box**:
        - component is localized for that locale
4) To localize a component:
    - select the component
    - change text/images in the right pane
    - click **Save**
    - the component becomes **blue** (localized)

Why this matters:
- It prevents “translation gaps” from breaking pages—fallback provides safe defaults.
- It gives merchandisers immediate visual confirmation of localization coverage.

## Two ways to control how you display or hide a component (unit objective)
This unit emphasizes two levers that directly control display/hide outcomes:

1) **Targeting/Scheduling** rules
- Show component/page to specific **Customer Groups** and/or within a schedule window.

2) **Localization visibility + fallback**
- Locale variants can be visible/hidden, and component content can be:
    - localized (blue), or
    - inherited via fallback (pink + Fallback).

(Visibility ordering logic and “first match wins” behavior is covered in the next unit about configuring components.)

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích khác nhau giữa **Page Structure** và **Components** views.
- Liệt kê 3 configuration settings quan trọng của Page Designer.
- Nêu 2 cách control hiển thị/ẩn component.

## Unit này đang dạy gì (để hiểu “ý”)
Unit này hướng dẫn cách biến “một trang mới tạo” thành trải nghiệm merchandising có kiểm soát bằng:
- **Structure** (đặt component ở đâu)
- **Visibility** (ai thấy, khi nào thấy)
- **Localization** (mỗi locale thấy gì, có fallback)
- **SEO settings** (trang được tìm thấy như thế nào)
  Đồng thời giúp bạn hiểu UI: **Page Structure** vs **Components**.

## UI: Page Structure vs Components (mental model)
### Page Structure (layout + hierarchy)
- Hiển thị **regions** và cây **component** (đặt ở đâu, thứ tự, lồng nhau).
- Dùng để: chèn component vào region, đổi thứ tự, tạo nested structures.

Hiểu đơn giản: **“bản thiết kế + thứ tự hiển thị”**.

### Components (palette)
- Danh sách **component types** có thể dùng.
- Dùng để: kéo thả component vào regions.

Hiểu đơn giản: **“toolbox / kho component”**.

## Tạo page (workflow theo unit)
1) Business Manager → Merchant Tools | Content | Page Designer
2) **New**
3) Chọn **page type**
4) Next
5) Assign **categories** → Next
6) Assign **products** → Next
7) Language **default**
8) Nhập name (ID tự tạo theo name)
9) (Optional) description
10) Review
11) **Save & Create**

Ý nghĩa assignments:
- Gắn page với context products/categories để tái sử dụng và target đúng nơi.

## 3 settings quan trọng (Page Settings)
### 1) Localization
- Toggle **Visible** để set page visible/hidden theo locale.

Ý nghĩa:
- Làm default trước, rồi localize dần; locale chưa sẵn sàng có thể để hidden.

### 2) Targeting / Scheduling
- Control bằng **Customer Group** + **Display from/to**.

Chi tiết kỹ thuật quan trọng:
- Thời gian hiển thị theo **shopper’s browser time**.

Ý nghĩa:
- Launch theo nhiều time zones cần plan kỹ.

### 3) SEO
- **Page Address (URL)**, **page title**, **page description**, tối đa **10 metadata keywords**.

Ý nghĩa:
- Tăng khả năng discover/index trên search engines.

## Fallback hierarchy (cách Page Designer quyết định nội dung theo locale)
### Ví dụ hierarchy
- `fr_CA > fr > default`

Best practice:
- Nội dung base đặt tên **default**.

### Page variants
- Tạo page ở default → hệ thống tạo **variants** cho các locale trong hierarchy.
- Mỗi component có thể localize theo locale hoặc dùng fallback.

### Shopper thấy gì nếu thiếu localized content
- Thiếu `fr_CA` → dùng `fr`
- Thiếu `fr` → dùng `default`

### Nhận biết fallback vs localized trong UI
- Locale `fr-CA` → hover component:
    - **Pink** + **Fallback** = dùng fallback
    - **Blue** = đã localize
- Localize: chọn component → sửa text/images → Save → chuyển blue

Ý nghĩa:
- Fallback giúp trang “không gãy” khi thiếu bản dịch; UI cues giúp kiểm soát nhanh.

## 2 cách control hiển thị/ẩn component (theo objective của unit)
1) **Targeting/Scheduling** (Customer Groups + thời gian)
2) **Localization visibility + fallback** (Visible per locale + localized vs fallback content)

(Cơ chế “first match wins” theo thứ tự component sẽ học ở unit cấu hình component.)