# Set Up a Page Designer Development Environment
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Identify three steps you must take to configure your environment.
- Explain why compatibility mode is important.
- List three environmental dependencies for the local machine.
- Describe the basic steps you must take to import sample data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## Introduction
Vijay Lahiri (Cloud Kicks developer) sets up his Page Designer dev environment using local tools (git, IDE) and a browser to access GitHub and Business Manager. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### End-to-end steps (the unit’s checklist)
1) Check the compatibility mode in Business Manager.
2) Check the dependencies for the local machine.
3) Download or clone repos from GitHub to your local machine (Page Designer elements are included in the base SFRA repository).
4) Upload the cartridges to the server with Business Manager.
5) Configure the cartridge path in Business Manager.
6) Import the storefront content data into the server with Business Manager.
7) Review the pages and components in Page Designer in Business Manager.
8) Customize or create files. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Assumptions / prerequisites (explicit warnings)
- This module assumes you are a B2C Commerce Cloud Developer with the proper permissions in a sandbox instance.
- Don’t try these steps in a Trailhead Playground (B2C Commerce isn’t available there).
- You need site administrator rights in your sandbox; if not, ask your administrator which login credentials to use.
- Page Designer is automatically enabled for each instance type. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## Check the Compatibility Mode
### What compatibility mode is (as defined)
- Compatibility mode refers to a specific Salesforce B2C Commerce API version where changes impacted backward compatibility with the previous API version.
- Not every API version impacts backward compatibility, so only some API versions have a compatibility mode.
- API versioning allows selecting from multiple compatibility modes, accepting incompatible changes with full knowledge. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Why it matters for Page Designer
- To use Page Designer without side effects from Page Designer components, ensure compatibility mode is set to **17.7 or higher**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Steps to check
1) Open Business Manager.
2) Select **Administration > Site Development > Code Deployment**.
3) Verify the compatibility mode is sufficient. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## Check Dependencies
### Dependencies (example shown in the unit)
The unit shows a `dependencies` snippet (example packages) such as:
- `bootstrap`
- `jquery`
- `popper.js`
- `font-awesome`
- `cleave.js`
- `flag-icon-css` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Verify Node.js and npm
1) Open a command prompt.
2) Run:
- `node -v`
- `npm -v`
3) Ensure version **6.x or later**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))  
   Node.js includes npm. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## Download Data and Files from GitHub
- Many developers create page/component types themselves, but Vijay uses the Page Designer examples included in the SFRA repository in GitHub.
- The unit points you to the “Tools & Resources for Salesforce B2C Developers” Trailhead module for how to download SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## Install Page Designer Cartridges
### Install npm packages
1) In command prompt, navigate to the top level of the repository (example: `storefront-reference-architecture`).
2) Run: `npm install`
3) Repeat for each repository. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Compile JavaScript and Style Sheets
From the repository top level:
- `npm run compile:js`
- `npm run compile:scss`
- `npm run compile:fonts` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## Upload Cartridges
### Create `dw.json` (location + required fields)
- Create a `dw.json` file using a text editor.
- Place it at the top level of the `storefront-reference-architecture` repository, as a sibling of the cartridge directory.
- It must be valid JSON and include: `hostname`, `username`, `password`, `code-version`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

Example shown:
```json
{
  "hostname": "dev01-web-company5.cloudkicks.com",
  "username": "admin",
  "password": "passwordjkl",
  "code-version": "version1"
}
``` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Field meanings (as explained)
- `hostname`: FQDN of the sandbox (example given like `dev04-web-company5.cloudkicks.com`)
- `username`: a user with Site Development rights (example: `admin`)
- `password`: that user’s password
- `code-version`: `version1` for a new sandbox ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Upload command + verify in Code Deployment
1) Navigate to the top level of `storefront-reference-architecture`.  
2) Run: `npm run uploadCartridge` (uploads `app_storefront_base` and `modules` to the sandbox specified in `dw.json`).  
3) Open Business Manager.  
4) Go to **Administration > Site Development > Code Deployment**.  
5) Click the code version you specified (for a new sandbox, `version1`) and confirm `app_storefront_base` and `modules` appear in the Version Summary list. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## Configure the Cartridge Path
Vijay updates the cartridge path so the server adds/uses the new code. Steps:
1) Open Business Manager.  
2) Select **Administration > Site > Manage Sites**.  
3) In Business Manager Site section, click the **RefArch** link (you select your own application).  
4) Click **Settings** tab.  
5) Enter cartridge names. For SFRA:
- RefArch cartridge path: `app_storefront_base`
- Business Manager cartridge path: `bm_app_storefront_base` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## Import sample data + rebuild indexes
- Vijay uses SFRA sample data (graphics used on test pages). Import is done via Business Manager Site Import & Export using the `site-template` directory.
- For SFRA sites: zip up `site_template_sfra` or use `site_template_sfra.zip`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

Steps:
1) Open Business Manager.  
2) **Administration > Site Development > Site Import & Export**.  
3) Choose file (zip).  
4) For SFRA, select `site-template-sfra.zip`.  
5) Upload.  
6) When Status is Successful, select file and Import.  
7) Select site: `RefArch`.  
8) Rebuild indexes: **Merchant Tools > Search > Search Indexes**.  
9) Select indexes.  
10) Click Rebuild. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## Next Steps
- Next unit: look more closely at the files in the SFRA repository. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

---

## VI (A-level: chi tiết; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
Sau khi hoàn thành unit, bạn có thể:
- Nêu 3 bước cần làm để cấu hình environment.
- Giải thích vì sao compatibility mode quan trọng.
- Liệt kê 3 dependencies môi trường cho máy local.
- Mô tả các bước cơ bản để import sample data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Introduction
Vijay (Cloud Kicks developer) setup môi trường dev Page Designer bằng local tools (git, IDE) và dùng trình duyệt để vào GitHub và Business Manager. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

**Checklist bước đi end-to-end (đúng theo unit)**
1) Check compatibility mode (Business Manager)  
2) Check dependencies local  
3) Download/clone repos từ GitHub (Page Designer elements nằm trong base SFRA repo)  
4) Upload cartridges lên server (Business Manager)  
5) Configure cartridge path (Business Manager)  
6) Import storefront content data (Business Manager)  
7) Review pages/components (Page Designer trong Business Manager)  
8) Customize hoặc tạo files ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

**Prerequisites/warnings**
- Không làm trong Trailhead Playground (không có B2C Commerce).
- Cần site administrator rights trong sandbox; nếu không thì hỏi admin để lấy credentials.
- Page Designer tự động enable cho mỗi instance type. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Check the Compatibility Mode
- Compatibility mode = một B2C Commerce API version mà thay đổi gây ảnh hưởng backward compatibility; không phải version nào cũng có. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))  
- Để dùng Page Designer không bị side effects từ Page Designer components: compatibility mode phải **17.7+**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))  
- Cách check:
  - Business Manager → **Administration > Site Development > Code Deployment** → xác nhận mode đủ. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Check Dependencies
- Unit đưa ví dụ `dependencies` gồm các packages như bootstrap/jquery/popper.js/font-awesome… ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))  
- Check Node.js + npm:
  - `node -v`, `npm -v`
  - cần version **6.x+**; Node.js bao gồm npm. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Download Data and Files from GitHub
- Vijay dùng các ví dụ Page Designer có sẵn trong SFRA repo. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Install Page Designer Cartridges
- `npm install` ở top-level repo, lặp lại cho từng repo. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))  
- Compile:
  - `npm run compile:js`
  - `npm run compile:scss`
  - `npm run compile:fonts` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Upload Cartridges
- Tạo `dw.json` ở top-level `storefront-reference-architecture` (cùng cấp thư mục cartridge), gồm hostname/username/password/code-version. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))  
- Upload: `npm run uploadCartridge`, rồi kiểm tra ở Code Deployment xem `app_storefront_base` và `modules`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Configure the Cartridge Path
- **Administration > Site > Manage Sites** → chọn site RefArch → Settings:
  - RefArch cartridge path: `app_storefront_base`
  - Business Manager cartridge path: `bm_app_storefront_base` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Import sample data + rebuild indexes
- Import `site_template_sfra` / `site_template_sfra.zip` bằng Site Import & Export, rồi rebuild Search Indexes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))

### Next Steps
- Unit sau: xem kỹ các files trong SFRA repo. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-set-up-dev-environment))