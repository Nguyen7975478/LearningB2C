# Explore Page and Component Type Controllers, JSON, and Scripts
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- List three development elements you can use to create Page Designer page and component types.
- List the JSON file naming convention.
- Explain how controllers are used for Page Designer pages and components.
- Describe the difference between how B2C Commerce uses JSON and JavaScript files for page and component types. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))

---

## Introduction (what matters beneath the surface)
- Page Designer development requires only a few essential elements.
- Controllers, JSON, and script files are most important beneath the surface (visual elements like ISML/HTML/CSS are covered later).
- Controllers “run the show”; JSON/script files work the details:
    - Page type JSON describes regions where components can be placed.
    - Component type JSON describes attributes (and possibly regions).
- Each JSON file has a comparable script file:
    - includes a `render` function to return markup
    - result must be a **string**
- Always give the JSON and script files the same name (except extension) and put them in the same folder. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))

---

## Controllers
- Controllers are server-side scripts that handle storefront requests and manage flow of control; they create instances of models and views to generate responses.
- Example: category menu click or search term triggers a controller that renders a page.
- For Page Designer rendering, a storefront controller calls `dw.experience.PageMgr` to render pages, components, and regions.
- Controllers also help create URLs to Page Designer pages (use cases):
    - link from a marketing email
    - link from global header/footer/main navigation ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))

---

## JSON
### Where to place JSON meta definition files (required directories)
- Page types: `<your_cartridge>/cartridge/experience/pages`
- Component types: `<your_cartridge>/cartridge/experience/components` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))

### Naming convention constraints
- JSON file name can include only alphanumeric or underscore characters.
- If placed in subdirectories under `/experience/pages` or `/experience/components`, each subdirectory level name must also use only alphanumeric or underscore characters. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

### Schema guidance
- The unit points to “B2C Commerce Page Designer JSON schemas” for schema files describing JSON formatting. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

---

## Page: storePage.json (key points described)
- The unit includes a store page meta definition example where:
    - it has three regions: `headerbanner`, `main`, `legalnotice`
    - `headerbanner` and `legalnotice` use `max_components = 1` (only one component rendered at a time)
    - `headerbanner` uses component type exclusion (some component types are not allowed there)
    - `main` has no max_components value → can display multiple components
    - `legalnotice` uses component type inclusion so only `commerce_assets.editorialRichTxt` is allowed in that region ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

**Meaning of max_components**
- Restricts number of components rendered at a time, but the region can contain multiple components overall (for scheduling/targeting).
- Example: banner region can show different components in different seasons. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

---

## Component: mainBanner.json (key points + example excerpt)
- The unit’s `mainBanner.json` defines attributes that the merchandiser can set, including:
    - banner image file
    - text overlay
    - shop now link
- Attributes appear in groups in the visual editor (example group name: “Banner Image Configuration”). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

---

## Script Files (JSON ↔ JS relationship)
- Each JSON meta definition file has a comparable script file with a `render` function returning markup as a string.
- The JSON and script file names must match (same base name) and be in the same folder. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))

---

## User Decorators
- Vijay considers strategies for decorators:
    - script file can accept a decorator parameter when rendering or fall back to default
    - controller can render page with different decorators based on conditions ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

---

## Page: storePage.js (what the unit highlights)
- The unit shows that the primary page type parts are in:
    - template `storePage.isml`
    - stylesheet `storePage.css` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

---

## Component: mainBanner.js (what the unit shows it doing)
- The unit shows `mainBanner.js` render logic that:
    - reads `context.content`
    - sets model properties such as heading/image/categoryLink
    - uses URL building for category link (example uses `URLUtils.url(...)`)
    - sets expires headers (relative page cache instruction)
    - returns the rendered template text (Template render to string) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

### “Good JavaScript” checks (lint)
- Vijay runs repository guideline checks before committing:
    - `npm install`
    - `npm run lint` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

---

## Next Steps
- Next unit covers the visual elements: ISML, HTML, and CSS. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

---

## VI (A-level: chi tiết; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Liệt kê 3 development elements để tạo page/component types.
- Nêu naming convention của JSON.
- Giải thích controllers dùng thế nào cho Page Designer pages/components.
- Mô tả khác biệt cách B2C Commerce dùng JSON và JS files. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))

### Introduction
- Page Designer dev landscape “ít phần tử cốt lõi”; dưới bề mặt quan trọng nhất là controllers, JSON, script files (phần ISML/HTML/CSS học sau). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))
- Controllers “run the show”; JSON/script định nghĩa chi tiết:
    - Page type JSON mô tả regions đặt components
    - Component type JSON mô tả attributes (và có thể regions) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))
- Mỗi JSON có script file tương ứng với `render()` trả markup dạng **string**; JSON và JS cùng tên (khác extension) và cùng folder. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))

### Controllers
- Controller là server-side script xử lý request; tạo model/view để trả response.
- Page Designer: controller gọi `dw.experience.PageMgr` để render pages/components/regions.
- Controller tạo URL tới Page Designer page (link email marketing, header/footer/nav). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))

### JSON
- Vị trí JSON:
    - page types: `<cartridge>/cartridge/experience/pages`
    - component types: `<cartridge>/cartridge/experience/components` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))
- Naming constraint: chỉ alphanumeric hoặc underscore; subdirectory levels cũng vậy. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))
- Có JSON schemas để bám format. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

### storePage.json
- Có 3 regions: `headerbanner`, `main`, `legalnotice`.
- `headerbanner`/`legalnotice`: `max_components=1`.
- `headerbanner`: exclusion (một số component types không cho phép).
- `main`: không có max_components → nhiều components.
- `legalnotice`: inclusion chỉ cho `commerce_assets.editorialRichTxt`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))
- `max_components` giới hạn render “tại một thời điểm” nhưng region vẫn chứa nhiều components để schedule/target (vd banner mùa xuân vs mùa hè). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

### mainBanner.json
- Định nghĩa attributes: image/text overlay/shop now link; hiển thị theo attribute groups trong visual editor. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

### Script files + decorators + lint
- JS script phải có render trả string; tên trùng JSON; cùng folder. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js))
- Decorators có thể truyền qua script/controller hoặc dùng default. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))
- “Good JS”: `npm install`, `npm run lint` trước commit. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))

### Next Steps
- Unit sau: ISML/HTML/CSS. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-json-js?utm_source=openai))