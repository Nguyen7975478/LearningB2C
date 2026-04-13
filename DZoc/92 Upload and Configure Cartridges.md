# Upload and Configure Cartridges
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Explain which tools you can use to upload Storefront Reference Architecture (SFRA).
- Explain the benefit of disabling page caching.
- List three ways to view cartridges on the server.
- Explain why rule-based storefront URLs should be disabled. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

---

## Introduction
- Vijay starts by uploading standard reference architecture cartridges to the server (manual upload with the SFRA upload tool).
- Now he wants to upload modified cartridges, register them so the server recognizes stacking order, and disable page caching + site URLs to troubleshoot. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- Access note: to access the SFRA repo in GitHub, you need credentials for GitHub and Account Manager. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

---

## Upload SFRA Cartridges (dwupload + npm + dw.json)
- Vijay uses **dwupload**, a command-line upload tool available in GitHub, to upload code. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- dwupload is installed as an npm library:
    - **npm** is the default package manager for **Node.js**.
    - npm includes a CLI client and an online registry. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- The upload tool uses a `dw.json` file that contains:
    - server connection info
    - the code version to upload cartridges to
- In the SFRA repo, you create `dw.json` at the root of your project. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**dw.json example in the unit**
```json
{
    "hostname": "sandbox-01-inside-the-realm.cloudkicks.net",
    "username": "vlahiri",
    "password": "yourpwd",
    "code-version": "version1"
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**How to configure + run from the top-level directory**
1) Open a command line.
2) Navigate to the cartridge you want to upload.
3) Locate or create `dw.json` in the top-level folder of the repository (as a sibling of the `cartridges` directory). ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

---

## Use sgmf-scripts (createCartridge + CLI)
- Vijay can use **sgmf-scripts** `createCartridge` build tool command to automatically create a `dw.json` file. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- sgmf-scripts repository contains scripts to create SFRA overlay cartridges and can be executed through the CLI. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

---

## Add Cartridges to the Cartridge Path
- After upload, Vijay must tell B2C Commerce how to stack cartridges so they load/run in the correct order:
    - register cartridges in Business Manager
- He also needs to load Cloud Kicks storefront data (images, product data, pricing), then run the storefront to test. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- Next step in the unit: disable page caching. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

---

## Disable Page Caching (benefit + steps)
**What automatic page caching means**
- Some page data stays on the page and doesn’t reload from the server, so shoppers see results faster.
- Web server automatically caches HTML pages generated from ISML templates configured for caching.
- Example: product details page structure is cached (same for all products), but product-specific data is not cached (changes per product). ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**Why disable in development**
- TTL (time to live) for page data is the same as TTL for static content.
- If TTL exists, Vijay must wait to see changes; good for production, bad for development → he disables page caching to see changes immediately. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**Steps to disable page caching**
1) Business Manager → App Launcher → Administration | Sites | Manage Sites
    - (If developing a Business Manager extension instead of a new site: Administration | Sites | Manage Sites | Business Manager.)
2) Select a site.
3) Click the Cache tab.
4) Select Sandbox/Development on the General tab.
5) Specify TTL of static content: `0`
6) Deselect Enable page caching.
7) Click Apply. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

---

## Disable Site URLs (rule-based storefront URLs)
- Vijay wants to test a new controller by entering a URL directly in the browser, such as:
    - `https://localhost/on/cloudkicks.store/Sites-app-Site/default/New-Controller` ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- This conflicts with automatically generated **rule-based storefront URLs** intended to improve SEO and drive shoppers to the storefront.
- In this situation, he’s not considering SEO; he wants to test the controller, so he disables rule-based URLs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**Steps to disable rule-based storefront URLs**
1) Business Manager → App Launcher → Merchant Tools | Site | Site Preferences | Storefront URL
2) Disable **Enable Storefront URLs**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

---

## View Cartridges on the Server (3 ways)
Vijay can access cartridges on the server using:
- Business Manager
- a URL in the browser
- WebDAV ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**Business Manager steps**
1) App Launcher → Administration | Sites | Manage Sites
2) Select site (cloudkicks)
3) Click Settings tab
4) Drill down into your cartridge path ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**WebDAV notes**
- Login with Business Manager username/password.
- Cartridge directory name must be ≤ 50 characters (WebDAV restriction).
- WebDAV can have issues with disabled server connections and inability to access a cartridge. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- Typical location for currently selected code version:
    - `https://<hostname>/on/demandware.servlet/webdav/<organization>/Cartridges/.version` ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

---

## Next Steps
- You learned how to upload cartridges, create new cartridges for each reference architecture, disable page caching and site URLs, and view cartridges on server.
- Next: customize cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

---

## VI (A-level: chi tiết; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Giải thích tools dùng để upload SFRA.
- Giải thích lợi ích tắt page caching.
- Liệt kê 3 cách xem cartridges trên server.
- Giải thích vì sao cần tắt rule-based storefront URLs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

### Introduction
- Vijay upload reference architecture cartridges lên server; sau đó upload các cartridges đã sửa, register để server biết stacking order, và tắt page caching + site URLs để troubleshoot. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- Note: muốn access SFRA repo GitHub cần GitHub + Account Manager credentials. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

### Upload SFRA Cartridges (dwupload + npm + dw.json)
- Dùng **dwupload** (CLI upload tool). ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- dwupload là npm library; **npm** là package manager của **Node.js**, có CLI và registry. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- `dw.json` chứa thông tin kết nối + code version; tạo ở root project SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**dw.json example đúng như unit**
```json
{
    "hostname": "sandbox-01-inside-the-realm.cloudkicks.net",
    "username": "vlahiri",
    "password": "yourpwd",
    "code-version": "version1"
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**Cách cấu hình/chạy**
1) mở command line
2) vào cartridge muốn upload
3) tạo/tìm `dw.json` ở top-level repo (cùng cấp với thư mục `cartridges`) ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

### Use sgmf-scripts
- Dùng **sgmf-scripts** lệnh `createCartridge` để tự tạo `dw.json`; scripts chạy được qua CLI và hỗ trợ tạo overlay cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

### Add Cartridges to the Cartridge Path
- Upload xong phải register trong Business Manager để đúng thứ tự stack.
- Cần load Cloud Kicks storefront data (images/product data/pricing) và chạy storefront để test. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

### Disable Page Caching
- Page caching giúp nhanh vì giữ một phần dữ liệu; web server cache HTML pages từ ISML templates (vd structure product details page cache, data per product thì không). ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- Trong dev, TTL khiến phải chờ thấy thay đổi → set TTL=0 và tắt caching để thấy ngay. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

**Steps**
- Administration | Sites | Manage Sites → chọn site → Cache tab → Sandbox/Development → TTL static content = 0 → bỏ chọn Enable page caching → Apply. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

### Disable Site URLs
- Tắt rule-based URLs (SEO-friendly) để test controller bằng URL trực tiếp; ví dụ URL test trong unit. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- Steps: Merchant Tools | Site | Site Preferences | Storefront URL → disable Enable Storefront URLs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

### View Cartridges on the Server (3 ways)
- Business Manager / URL browser / WebDAV. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))
- WebDAV: login bằng BM creds; folder name ≤ 50 chars; có thể lỗi do connections; URL `.version` như unit nêu. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))

### Next Steps
- Next: Customize Cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/b2c-cartridges/b2c-cartridges-upload-configure))