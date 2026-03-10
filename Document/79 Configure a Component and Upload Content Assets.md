# Configure a Component and Upload Content Assets
https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-merchandiser/b2c-page-designer-configure-component?trail_id=set-up-merchandising-for-your-storefront

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe how **page visibility** works with components.
- List three attributes that Brandon uses in his component.
- Explain why renaming a folder in the **Media Manager** can cause problems.
- Explain how to upload content asset files.

## Context (what Brandon is trying to achieve)
- Brandon already created a Page Designer page and configured who can see it and when.
- Now he wants to:
    - add a more complex component (**Carousel**),
    - understand how B2C Commerce decides **which components display** (so there are no surprises),
    - and upload new **content assets** for use in components.

## Add another component: Carousel (step-by-step)
Brandon adds a **Carousel** component and then adds individual slide components under it.

1) In Business Manager, go to **Merchant Tools | Content | Page Designer**.
2) Select the page: `Cloud Kicks Homepage`.
3) Click the **Page Structure** icon.
4) Click the plus sign beside **Main Region**.
5) Select **Carousel** in the **Commerce Layouts** section (or drag from Components pane).
6) Configure Carousel attributes:
    - Enter the **carousel title** (shown on storefront page).
    - Select **indicators** and **controls**.
    - Select the number of **slides** to show for each device size:
        - phone
        - tablet
        - desktop
          (example shown in the unit: 1/2/3 slides for phone/tablet/desktop).
7) Add slides:
    - Click Page Structure icon again.
    - Click the plus sign beside **Slides**.
    - Select **Image With Text** component as the slide type.

### Image With Text slide: what it can do (capability list)
The unit describes that this slide component lets you showcase multiple products and navigate shoppers to what you want them to see (product/category/search term/external site). For each slide you can:
- Select an **image**.
- Add a **text overlay**.
- Create a **link** to:
    - a **product**
    - a **category**
    - a **search term**
    - an **external site**
- Enter **text below the image**.

### Important configuration instruction (to avoid confusion later)
- The unit explicitly says:
    - Always add the **largest number of slides** that you configured for the Carousel.
    - Reason: each slide for each view (phone/tablet/desktop) can be different, and having the max slide count prevents missing content for a device size.

## Publish and delete pages (operational controls)
### Publish
- When Brandon is satisfied, he clicks **Publish** to make the page available online.

### Delete
If early pages aren’t what he wants, he can delete them:
1) Merchant Tools | Content | Page Designer
2) Use the dropdown arrow on a page → **Delete**

## How visibility works (how B2C Commerce picks which component displays)
This section is the key “understand the idea” part of the unit.

### Visibility evaluation order (top-down in Page Structure)
- Page Designer starts at the **top** of the component list in **Page Structure**.
- It checks component visibility rules **in order** (customer group, date, time).
- It displays the **first component** that matches the rules.

### “Fallback component” behavior (when nothing matches)
- If Page Designer checks all components and finds **no match**, it displays the component at the **bottom** of the list (the unit’s example: the third *Image With Text* component).

### The “no rules means always match” rule (critical)
- If a component has **no rules applied**, it is **always a match**.
- Therefore:
    - any components **below** an “always match” component will **never appear** (because Page Designer stops at the first match above them).

Why this matters in practice:
- You must order components intentionally.
- A “default” component with no rules should typically be placed last, so it acts as a true fallback.

## Three attributes Brandon uses (from the unit’s Carousel slide scenario)
The unit’s slide instructions imply Brandon uses attributes that map to:
1) **Image** (select an image for the slide)
2) **Text overlay** (overlay headline/text)
3) **Link / Destination** (product/category/search term/external URL)
   (Plus additional optional text below the image.)

## Manage content assets (Media Manager concepts)
### Why renaming a folder can cause problems
- Page Designer components reference assets by their stored paths/locations.
- If you **rename** a folder in **Media Manager**, existing references can break because the path changes.
  Practical implication:
- Treat Media Manager folder naming as stable; plan folder taxonomy early.

## Upload content asset files (what you do conceptually)
- Brandon can upload new content assets (images/files) so they can be selected inside component attributes.
- This upload is performed through **Media Manager** (where content assets are stored and managed).
  (Exact click-by-click upload UI details are not fully visible in the retrieved excerpt, but the unit’s objective confirms uploading content assets is part of the workflow.)

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả **page visibility** hoạt động thế nào với components.
- Liệt kê 3 attributes Brandon dùng trong component.
- Giải thích vì sao rename folder trong **Media Manager** có thể gây vấn đề.
- Giải thích cách upload content asset files.

## Bối cảnh (Brandon muốn làm gì)
- Brandon đã tạo page và cấu hình ai thấy/khi nào thấy.
- Bây giờ anh muốn:
    - thêm component phức tạp hơn (**Carousel**),
    - hiểu cơ chế hệ thống chọn **component nào được hiển thị** (tránh “bất ngờ”),
    - và upload **content assets** để d��ng trong components.

## Thêm component: Carousel (step-by-step)
1) Business Manager → **Merchant Tools | Content | Page Designer**
2) Chọn page `Cloud Kicks Homepage`
3) Bấm **Page Structure** icon
4) Bấm dấu **+** cạnh **Main Region**
5) Chọn **Carousel** trong **Commerce Layouts** (hoặc drag từ Components)
6) Cấu hình Carousel:
    - **carousel title**
    - **indicators** + **controls**
    - số **slides** cho từng device size: phone/tablet/desktop (ví dụ 1/2/3)
7) Thêm slides:
    - Page Structure icon → dấu + cạnh **Slides**
    - chọn **Image With Text** component

### Image With Text slide làm được gì (unit)
Slide này cho phép showcase nhiều products và dẫn shopper tới:
- product / category / search term / external site
  Và cho mỗi slide có thể:
- chọn **image**
- thêm **text overlay**
- tạo **link**
- nhập **text dưới ảnh**

### Lưu ý quan trọng (để không “thiếu slide” theo device)
- Luôn thêm số slides bằng **lớn nhất** bạn đã cấu hình cho Carousel.
- Ý nghĩa: mỗi view (phone/tablet/desktop) có thể cần slide khác nhau; nếu không đủ slides sẽ bị thiếu nội dung cho một số device.

## Publish và delete pages
### Publish
- **Publish** để page available online.

### Delete
- Page Designer list → dropdown → **Delete**.

## Visibility hoạt động thế nào (hiểu ý quan trọng nhất)
### Thứ tự kiểm tra visibility (top-down)
- Page Designer duyệt từ **trên xuống** trong danh sách **Page Structure**.
- Check rules theo thứ tự (customer group, date, time).
- Hiển thị **component đầu tiên** match.

### Khi không có component nào match
- Nếu không có match, hệ thống hiển thị component ở **dưới cùng** (unit ví dụ: Image With Text thứ 3).

### Quy tắc “không có rules = luôn match” (cực quan trọng)
- Component **không có rules** ⇒ **luôn match**.
- Vì vậy:
    - mọi component **bên dưới** một component “luôn match” sẽ **không bao giờ hiển thị**.

Ý nghĩa vận hành:
- Cần sắp xếp thứ tự component có chủ đích.
- Component “default/no rules” nên đặt cuối để làm fallback đúng nghĩa.

## 3 attributes Brandon dùng (theo scenario slide)
1) **Image**
2) **Text overlay**
3) **Link/Destination** (product/category/search term/external URL)
   (+ text dưới ảnh là phần bổ sung)

## Content assets (Media Manager)
### Vì sao rename folder gây vấn đề
- Components tham chiếu assets theo đường dẫn.
- Rename folder trong **Media Manager** làm đổi path → các tham chiếu cũ có thể “gãy”.
  Ý nghĩa:
- Folder taxonomy/naming nên ổn định, lên kế hoạch từ sớm.

## Upload content asset files
- Upload assets (images/files) để chọn được trong component attributes.
- Thao tác upload nằm trong **Media Manager** (nơi quản lý content assets).
  (Chi tiết UI upload không hiển thị đầy đủ trong đoạn trích lấy được, nhưng objective xác nhận đây là phần của workflow.)