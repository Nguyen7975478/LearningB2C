# Customize Cartridges
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- List three things you can do with sgmf scripts.
- Describe how you can override the app_storefront_base cartridge.
- Explain how the global .scss file inherits styles.
- Describe how to include JavaScript modules from other cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

---

## Introduction
- Vijay uploaded SFRA cartridges and registered them.
- He configured page caching and site URLs to speed development.
- Now he’s ready to customize storefront apps with SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

---

## Create an SFRA Overlay Cartridge (edit-free policy)
- Vijay adopts an **edit-free policy** so he won’t need to find SFRA code changes from new releases and port them into his customized code. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
- He plans to customize SFRA without editing:
    - `app_storefront_base`
    - plugins such as `plugin_applepay`
- He doesn’t need to rename base/plugin cartridges to keep receiving security updates, bug fixes, and new features from Salesforce.
- He’s happy SFRA will still work after a major release. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### What sgmf-scripts can do (list in unit)
- Upload a file to a sandbox.
- Upload a cartridge.
- Run tests on certain files or directories.
- Compile css or js files.
- Lint scss or js files.
- Create a new cartridge structure. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

---

## Add Custom Cartridges to Your Application (sgmf-scripts + npx)
- Vijay uses **sgmf-scripts** and **npx** (bundled with npm; requires npm 5.3.0+). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
- If using sgmf-scripts in multiple projects, install globally:
    - `npm install --global sgmf-scripts`
    - Benefit stated: install once instead of per project. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

**Steps to create an overlay cartridge (as listed)**
1) Open command line.
2) `mkdir cloudkicks`
3) `cd cloudkicks`
4) `npx sgmf-scripts --createCartridge app_custom_cloudkicks`
5) `npm install` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

**Resulting structure (as shown)**
- `cartridges/app_custom_cloudkicks/cartridge/...`
- plus: `dw.json`, `node_modules`, `package.json` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

---

## Customize CSS and JavaScript (selective overrides via package.json paths)
- You can’t modify SFRA base cartridges directly, but you can selectively override CSS styles and client-side JavaScript. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
- In `package.json`, the `paths` property lists every cartridge with CSS and client-side JS customized in the site.
- `paths` lets you import CSS/JS functionality from other cartridges and selectively override.
- The compile tool compiles JS and CSS across cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

**Steps in unit**
1) Open command prompt.
2) Navigate to top level of your custom cartridge.
3) Open `package.json` and modify `paths`:
    - `paths.base` points to local directory containing `app_storefront_base`.
4) Add properties for cartridges you want to import from (example: plugin_ratings, plugin_reviews, app_storefront_base). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

**paths example in unit**
```json
"paths": {
  "base": "../storefront-reference-architecture/cartridges/app_storefront_base/",
  "ratings": "../plugin_ratings/cartridges/plugin_ratings/",
  "reviews": "../plugin_reviews/cartridges/plugin_reviews/",
  "applepay": "../plugin-applepay/cartridges/plugin_applepay/"
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### Global .scss inheritance (example shown)
- Example import path for custom scss:
    - `my_repository/cartridges/my_cartridge/cartridge/client/default/myfile.scss` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
- The sample global `.scss` inherits most styles from the base cartridge.
- It uses the `base` property (from `package.json`) to import style sheets.
- Sample shown includes imports like:
    - `@import "base/variables";`
    - `@import "bootstrap/scss/bootstrap";`
    - plus other base/component imports
    - and a small override (example `.modal-background { display: none !important; }`). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### Include/override client-side JavaScript using require()
- You can include functionality from one SFRA script module in another.
- Vijay uses the `paths` object in `require()` to override client-side JS.
- Example shown:
```js
'use strict'; var base = require('../base/product/base');
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### What you can customize via overlay cartridges (table in unit)
- **Hooks**: configure functionality called at a point in application flow or an event.
- **Modules**: access JS/B2C Commerce script modules conforming to **CommonJS Modules 1.1.1**.
- **Templates**: override by creating a new template with same name and relative path.
- **Models**: JSON object layer converting proprietary script API objects to pure JSON objects for storefront + applies business logic.
- **Controllers and Nodes**: replace a base controller to inherit/extend, replace/add route, override middleware chain step, change route access, add web service/third-party call.
- **Forms**: persist form data during session; store in system objects or custom objects.
- **Plugin cartridges**: include plugin cartridges on the cartridge path and base path like any cartridge. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

---

## Cartridge Path Substitution (require() patterns)
- Cartridge path controls file lookup and defines what code runs.
- B2C Commerce searches cartridges left-to-right when a controller/script/model/ISML template is called via URL or code. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
- You can substitute cartridge-path file lookup using `require()` in these situations: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
    - Relative to current file: `require('./shipping')`, `require('../../util')`
    - Relative to current cartridge: `require('~/cartridge/scripts/cart')`
    - From beginning of cartridge path: `require('*/cartridge/scripts/util/array')`
    - Specific B2C Commerce API: `require('dw/catalog/CatalogMgr')`
    - Specific module or cartridge: `require('server')`

---

## Troubleshoot
When changes don’t appear:
1) Business Manager → App Launcher → Administration | Site Development | Code Deployment
2) Click Add and enter the name of a new (empty) code version
3) Then reactivate the original code version (unit describes this flow as the fix). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

---

## Let’s Wrap It Up
- You learned about sgmf scripts, how global `.scss` inherits styles, and how to include JS modules from other cartridges.
- You also learned how to create a storefront cartridge.
- Next: take the final quiz and earn the badge. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

---

## VI (A-level: chi tiết; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Liệt kê 3 việc làm được với sgmf scripts.
- Mô tả cách override `app_storefront_base`.
- Giải thích global `.scss` inherit styles thế nào.
- Mô tả cách include JavaScript modules từ cartridges khác. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### Introduction
- Vijay đã upload và register SFRA cartridges; cấu hình page caching và site URLs để dev nhanh hơn; giờ bắt đầu customize. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### Create an SFRA Overlay Cartridge (edit-free policy)
- Áp dụng **edit-free policy** để không phải port SFRA changes từ release mới vào code custom. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
- Customize mà không sửa trực tiếp `app_storefront_base` và plugins như `plugin_applepay`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

**sgmf-scripts làm được (đúng list)**
- Upload file, upload cartridge, run tests, compile css/js, lint scss/js, create cartridge structure. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### Add Custom Cartridges (npx + sgmf-scripts)
- Dùng **npx** (npm 5.3.0+) và sgmf-scripts; có thể cài global `npm install --global sgmf-scripts`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
- Steps tạo overlay cartridge:
    - `mkdir cloudkicks`
    - `cd cloudkicks`
    - `npx sgmf-scripts --createCartridge app_custom_cloudkicks`
    - `npm install` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
- Có cấu trúc thư mục + `dw.json`, `node_modules`, `package.json`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### Customize CSS & JavaScript (paths trong package.json)
- Không sửa base trực tiếp, nhưng override chọn lọc CSS và client-side JS. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))
- `package.json` → `paths` khai báo đường dẫn các cartridges cần import/override; compile tool compile CSS/JS across cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

**paths example**
```json
"paths": {
  "base": "../storefront-reference-architecture/cartridges/app_storefront_base/",
  "ratings": "../plugin_ratings/cartridges/plugin_ratings/",
  "reviews": "../plugin_reviews/cartridges/plugin_reviews/",
  "applepay": "../plugin-applepay/cartridges/plugin_applepay/"
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

**global .scss inherit**
- File scss custom nằm dưới `cartridge/client/default/...`.
- Dùng `@import "base/..."` để inherit từ base; có thể thêm overrides nhỏ (vd `.modal-background { display: none !important; }`). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

**require() để include/override JS**
```js
'use strict'; var base = require('../base/product/base');
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

**Customize được gì qua overlay cartridge (đúng bảng)**
- Hooks, Modules (CommonJS 1.1.1), Templates, Models, Controllers and Nodes (routes/middleware/access/web service), Forms, Plugin cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### Cartridge Path Substitution
- Cartridge path quyết định lookup và code chạy; search left-to-right.
- Có thể thay cơ chế lookup bằng `require()` theo các pattern: `./`, `~/`, `*/`, `dw/...`, `server`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### Troubleshoot
- Không thấy changes: tạo code version rỗng rồi kích hoạt lại code version cũ trong Code Deployment. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))

### Wrap-up
- Tổng kết + làm quiz để nhận badge. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-customize))