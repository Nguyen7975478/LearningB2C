# Create and Use Salesforce CMS Content
https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-cms/b2c-create-cms-content?trail_id=set-up-merchandising-for-your-storefront

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List three channels that can use Salesforce CMS content.
- Detail the steps you must take to use Salesforce CMS content in Salesforce B2C Commerce Page Designer.
- Describe two ways you can organize a workspace.
- List three types of content you can create and manage in Salesforce CMS.

## What this unit is really teaching (to understand the “idea”)
This unit explains the operational workflow once the integration is done:
- Salesforce CMS is where content is authored and governed.
- Page Designer is where that content becomes commerce experiences.
  It also teaches an important technical behavior:
- Selecting CMS content in Page Designer **copies** content onto the page (it is not a live link), so updates require re-selection.

## Channels that can use Salesforce CMS content (unit examples)
The unit lists example channels:
- **B2C Commerce**
- **Marketing Cloud Engagement**
- **Heroku**
- **LEX apps**

Meaning:
- CMS content is designed for reuse across different front-ends/touchpoints.

## Two-part process (create in Salesforce, use in Business Manager)
Because Vijay completed the technical setup, Brandon’s process is “two-part”:

### Part A — In Salesforce (author content)
1) Launch the **Salesforce CMS app**.
2) Create and organize content.

### Part B — In Business Manager (use content in Page Designer)
1) Open **Page Designer**.
2) Add a content component to a page.
3) Map the component to the specific CMS content item.

## CMS Workspace (what it is, why it exists, and how to organize)
### What is a CMS workspace?
- A **CMS workspace** is how you **organize and secure** content in the Salesforce CMS app.
- Each workspace has:
    - one or more **channels** that share content,
    - created by one or more contributors.

### Why workspaces matter (understanding)
- Workspaces allow you to separate:
    - audiences,
    - security boundaries,
    - content ownership,
    - and publishing governance.

### Two ways to organize a workspace (unit examples)
The unit states Brandon uses workspaces to differentiate:
- **internal vs external information**
- **geographies**
- **different campaigns**

Operational detail:
- Workspace **name** and **description** help organize/share content appropriately.

## Types of content you can create/manage (unit list)
The unit lists content examples:
- **Video** (YouTube, Vimeo, Vidyard)
- **Graphics**
- **Text**
- **Audio**

## Create content in Salesforce CMS (step-by-step)
The unit provides steps:

1) Open Salesforce.
2) Click the **app icon** (App Launcher).
3) In the Salesforce CMS app, open the workspace you want to add content to.
4) Click **Add Content**.
5) Click **Create Content** and fill in fields:
    - `title`
    - `body`
    - `image`
    - `excerpt`
6) Click **Save Draft** when finished.
    - Draft saves content for approval/editing but does not make it available to channels.
7) Click **Publish** to make it available.

How to interpret Draft vs Publish:
- **Draft** = editable + not distributed.
- **Publish** = available to channels (so Page Designer can select it).

## Use CMS content in Page Designer (configure component) (step-by-step)
This is the “bridge” workflow:

1) In Business Manager, open **Page Designer**.
2) Select the page (example: **Cloud Kicks Homepage**).
3) Click **Page Structure** icon.
4) Click the plus sign next to the **Main Region**.
5) Select **CMS Headline Banner** in **Commerce Layouts** (or drag from Components).
6) In the attribute editor window, click **Select CMS Content**.
7) Select the CMS content → click **Select**.
    - B2C Commerce **copies the content to the page**.
8) Click **Save**.
9) Click **Publish** on the page when satisfied.

## Critical behavior: updates are not automatic (copy vs live link)
The unit states:
- If Brandon updates the original CMS content:
    - changes do **not** automatically appear in the Page Designer component.
- To update the storefront page:
    - he must reconfigure the component attribute and select the content again.

Why this matters:
- You must plan an operational process for updates:
    - update CMS → re-select in Page Designer → republish page.

## Locale warning (default locale mismatch)
Tip from the unit:
- Make sure the Page Designer **default locale** is what you want.
- The Page Designer page default locale is not necessarily the same as the default locale for Salesforce CMS content.

Interpretation:
- Locale mismatch can cause “wrong language” content to appear if you select CMS content while Page Designer is set to a different locale variant than expected.

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê 3 channels có thể dùng Salesforce CMS content.
- Trình bày các bước để dùng CMS content trong B2C Commerce Page Designer.
- Mô tả 2 cách tổ chức workspace.
- Liệt kê 3 loại content có thể tạo/quản lý trong Salesforce CMS.

## Unit này dạy gì (để hiểu “ý”)
Unit này dạy workflow vận hành sau khi đã connect xong:
- CMS là nơi tạo/quản trị content.
- Page Designer là nơi biến content thành trải nghiệm commerce.
  Và 1 hành vi kỹ thuật quan trọng:
- Chọn CMS content trong Page Designer sẽ **copy** content vào page (không phải live link), nên update phải chọn lại.

## Channels dùng được Salesforce CMS content (unit ví dụ)
- **B2C Commerce**
- **Marketing Cloud Engagement**
- **Heroku**
- **LEX apps**

Ý nghĩa:
- Content có thể reuse đa kênh/touchpoints.

## Quy trình 2 phần (Salesforce + Business Manager)
Vì Vijay đã setup kỹ thuật, Brandon làm 2 phần:

### Phần A — Trong Salesforce
1) Mở **Salesforce CMS app**
2) Tạo và organize content

### Phần B — Trong Business Manager
1) Mở **Page Designer**
2) Add content component vào page
3) Map component tới content item trong CMS

## CMS Workspace (là gì, vì sao cần, tổ chức thế nào)
### CMS workspace là gì?
- **CMS workspace** dùng để **organize và secure** content trong CMS.
- Mỗi workspace có:
    - ≥1 **channels** chia sẻ content,
    - content do ≥1 contributors tạo.

### Vì sao quan trọng
- Giúp tách theo audience/bảo mật/quyền sở hữu/quy trình publish.

### 2 cách organize (unit)
- **internal vs external information**
- **geographies**
- **campaigns**

Chi tiết vận hành:
- Name/description giúp organize/share đúng.

## Types of content (unit)
- **Video** (YouTube/Vimeo/Vidyard)
- **Graphics**
- **Text**
- **Audio**

## Tạo content trong Salesforce CMS (steps)
1) Open Salesforce
2) App Launcher
3) CMS app → mở workspace
4) **Add Content**
5) **Create Content** → điền `title`, `body`, `image`, `excerpt`
6) **Save Draft**: lưu để approve/edit, chưa available cho channels
7) **Publish**: content available

Cách hiểu:
- Draft = chưa phân phối; Publish = sẵn sàng cho channels.

## Dùng CMS content trong Page Designer (steps)
1) Business Manager → Page Designer
2) Chọn page (Cloud Kicks Homepage)
3) **Page Structure**
4) Dấu + cạnh **Main Region**
5) Chọn **CMS Headline Banner** trong **Commerce Layouts**
6) Attribute editor → **Select CMS Content**
7) Chọn content → **Select** (B2C Commerce **copy** content vào page)
8) **Save**
9) **Publish** page

## Hành vi quan trọng: update không tự động (copy vs live link)
- Update CMS content **không tự** cập nhật lên Page Designer component.
- Muốn cập nhật:
    - reconfigure attribute → select content lại → publish lại.

Ý nghĩa:
- Phải có quy trình update: CMS update → Page Designer re-select → republish.

## Cảnh báo locale (default locale mismatch)
Tip:
- Đảm bảo Page Designer **default locale** đúng.
- Default locale của Page Designer page có thể khác default locale của CMS content.

Ý nghĩa:
- Locale lệch dễ dẫn tới chọn/hiển thị content sai ngôn ngữ.