# Connect Salesforce CMS to Page Designer
https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-cms/b2c-connect-cms-to-page-designer?trail_id=set-up-merchandising-for-your-storefront

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List three tasks a developer must take to connect Salesforce CMS to Salesforce B2C Commerce Page Designer.
- Explain the purpose of the CMS workspace.
- Describe how to work with content types in Salesforce CMS and Page Designer.
- Explain how to create a Page Designer component type that accesses Salesforce CMS content.

## What this unit is really teaching (to understand the “idea”)
This unit explains the “plumbing” required so that:
- Salesforce CMS becomes the **content system of record** (authoring + governance),
- and Page Designer becomes the **experience assembly** layer (where content is placed into commerce pages).
  The merchandiser can’t do anything until the developer wires these systems together.

## Implementation Plan (dependency chain)
Brandon’s work (create/manage/use CMS content) can only happen after Vijay does:

1) Get a connection to a Salesforce org.
2) Open Salesforce CMS.
3) Install and configure Salesforce CMS.
4) Create new Page Designer components for Brandon.

Interpretation:
- CMS integration is a developer-led enablement project.
- Merchandisers consume the result through Page Designer component types.

## Prerequisites: Salesforce org and CMS app
### Salesforce org
- Cloud Kicks doesn’t have a Salesforce org, so Vijay asks the Salesforce account manager for a free administrator org.

Why this matters:
- Salesforce CMS runs in Salesforce core; it is not hosted inside Business Manager.

### Salesforce CMS app availability
- Vijay ensures the Salesforce org includes the **Salesforce CMS app**.
- For pricing/packaging, management contacts:
    - Salesforce account executive, or
    - Salesforce B2C Commerce success manager.

## Connect B2C Commerce and CMS (channel + workspace concepts)
The unit uses an analogy:
- A B2C Commerce **instance** is similar to a Salesforce org.

### CMS Workspace (purpose)
- A **Salesforce CMS workspace** is used to:
    - organize content,
    - secure content,
    - control contributor access.
- It is the container that hosts content intended for Page Designer usage.

### Channel (purpose)
- A **Commerce Cloud channel** is the delivery connection that allows CMS content to flow into a consumer (here: B2C Commerce).

## Step-by-step: connect a B2C Commerce instance to a CMS channel (unit steps)
1) Open a Salesforce Support ticket and request a **trust relationship** between your Salesforce org and your B2C Commerce instance.
2) Open a Salesforce org.
3) Add the Salesforce CMS app.
4) In Salesforce CMS, click **Add Workspace** (or use existing workspace).
5) Create a Commerce Cloud channel:
    - CMS Home → **Channels**
    - **Create Channel**
    - Name: `Cloud2Cloud_1`
    - Connection type: **Commerce Cloud**
    - Click **Create**
6) In the CMS workspace:
    - Click **Add Channel**
    - Select the Commerce Cloud channel created above
    - Click **Add**

Tip (unit):
- Page Designer is automatically enabled for each instance type.
- To follow steps in a sandbox, you need site administrator rights.

## Connect Business Manager (assign channel to a site library)
After the channel exists, Vijay assigns it inside Business Manager:

1) Open **Business Manager**
2) Go to **Administration > Sites > Libraries > site > General**
3) Scroll to the bottom
4) Assign the **CMS channel** to the **site library**

Interpretation:
- The site library becomes the “bridge point” where Page Designer can see CMS content via the assigned channel.

## Content types: the “must match” technical rule
This is the most important technical constraint in the unit:

- The **content type** is key.
- You must use the **same content type** in **Salesforce CMS** and **Page Designer**.

Example in the unit:
- Brandon wants text + graphics for a headline banner.
- Vijay chooses the existing CMS content type **news**.
- If the needed content type doesn’t exist:
    - Vijay creates a custom content type in Salesforce CMS.

Why this matters:
- Component attributes (fields) are resolved based on content type schema; mismatch means the component can’t reliably bind to fields.

## Create a Page Designer component type that accesses CMS content (cms_record)
To make CMS content selectable in Page Designer, Vijay builds a component type with an attribute bound to CMS.

### Component type requires BOTH JSON and JS
- For Page Designer components, developers create:
    - a JSON “meta definition” file, and
    - a JavaScript render script.

### Core attribute type used for CMS binding: `cms_record`
- Vijay creates an attribute:
    - `type: "cms_record"`
    - with `editor_definition.content_type` specifying which CMS content type is selectable.

### JSON meta definition (cmsheadlinebanner.json) — what it defines
The unit’s example defines:
- Component:
    - `name`: CMS Headline Banner
    - `description`
    - `group`: assets
- Attribute group “Headline Content”
    - attribute `cmsItem`:
        - `type`: `cms_record`
        - `required`: true
        - `editor_definition.content_type`: `news`
- Attribute group “Call to Action Button”
    - `ctaTitle` (string, required)
    - `ctaLink` (url, required)
- `region_definitions`: empty array (component has no regions)

Interpretation:
- `cmsItem` is the “handle” that lets merchandisers pick an item from CMS.
- CTA fields remain Page Designer-owned attributes (merchandisers can set per page/slot).

### JS render script (cmsheadlinebanner.js) — what it does
The unit’s script:
- Creates a model and reads `context.content`.
- If `content.cmsItem` exists:
    - reads CMS fields:
        - `title`
        - `body`
        - `bannerImage`
        - `excerpt` (used as `alt` text)
    - transforms image URLs for:
        - `device: mobile`
        - `device: desktop`
    - assigns call-to-action:
        - `ctaTitle`, `ctaLink`
- Renders:
    - `Template('experience/components/assets/headlinebanner').render(model).text`

Why this matters:
- It demonstrates the full integration path:
    - CMS structured fields → Page Designer attribute → render model → ISML template output.

## Good JavaScript (linting before commit)
Vijay runs:
- `npm install`
- `npm run lint`

Interpretation:
- This is a quality gate to enforce code standards before deploying cartridges.

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê 3 tasks developer cần làm để connect Salesforce CMS ↔ Page Designer.
- Giải thích mục đích của CMS workspace.
- Mô tả cách làm việc với content types giữa CMS và Page Designer.
- Giải thích cách tạo Page Designer component type truy cập CMS content.

## Unit này dạy gì (để hiểu “ý”)
Unit này nói về phần “plumbing” để:
- Salesforce CMS thành **content system of record** (tạo + quản trị),
- Page Designer thành lớp **lắp ghép trải nghiệm**.
  Merchandiser chỉ dùng được khi developer nối hệ thống xong.

## Implementation Plan (chuỗi phụ thuộc)
Brandon chỉ làm được sau khi Vijay:
1) Có kết nối tới Salesforce org.
2) Mở Salesforce CMS.
3) Install/configure CMS.
4) Tạo Page Designer components mới.

Ý nghĩa:
- CMS integration là enablement do developer dẫn dắt.

## Prerequisites: Salesforce org + CMS app
- Xin Salesforce org admin miễn phí.
- Đảm bảo org có **Salesforce CMS app**; pricing/packaging hỏi account executive/success manager.

## Connect B2C Commerce và CMS (workspace + channel)
- Instance B2C Commerce tương tự org (analogy).
- **Workspace**: tổ chức/bảo mật/kiểm soát contributor access.
- **Channel**: kết nối deliver CMS content sang consumer (B2C Commerce).

## Steps connect instance → channel (theo unit)
1) Support ticket xin **trust relationship**.
2) Mở Salesforce org.
3) Add CMS app.
4) CMS: **Add Workspace**.
5) CMS: Channels → Create Channel:
    - Name `Cloud2Cloud_1`
    - Connection type **Commerce Cloud**
6) Workspace: Add Channel → chọn channel → Add.

Tip:
- Page Designer auto-enabled mỗi instance type; làm trên sandbox cần site admin rights.

## Assign channel trong Business Manager (site library)
- Business Manager → Administration > Sites > Libraries > site > General → assign CMS channel vào **site library**.

Ý nghĩa:
- Site library là điểm “bridge” để Page Designer thấy CMS content.

## Quy tắc bắt buộc: content type phải match
- **Content type** là chìa khóa.
- CMS và Page Designer phải dùng **cùng content type**.
- Ví dụ: dùng content type **news**; thiếu thì tạo custom content type.

Ý nghĩa:
- Bind fields dựa theo schema; mismatch là hỏng mapping.

## Tạo component type đọc CMS content (cms_record)
- Component cần **JSON + JS**.

### Attribute type: `cms_record`
- Trong JSON, tạo attribute `cmsItem`:
    - type `cms_record`
    - required
    - `editor_definition.content_type: news`

### JSON meta (cmsheadlinebanner.json)
- Định nghĩa component + groups:
    - Headline Content group (`cmsItem`)
    - Call to Action group (`ctaTitle`, `ctaLink`)
    - `region_definitions: []`

### JS render (cmsheadlinebanner.js)
- Đọc `context.content.cmsItem.attributes.*`:
    - title, body, bannerImage, excerpt
- Transform image URL theo `device: mobile/desktop`
- Render template `experience/components/assets/headlinebanner`

Ý nghĩa:
- Đây là đường đi đầy đủ: CMS fields → model → template output.

## Good JavaScript
- `npm install`, `npm run lint` để đảm bảo code theo guidelines.