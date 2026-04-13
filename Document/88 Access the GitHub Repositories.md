# Access the GitHub Repositories
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Access the Salesforce B2C repositories on GitHub.
- Describe the benefits of the Commerce Cloud Storefront Reference Architecture (SFRA).
- Download or clone the SFRA repositories. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

---

## Get Ready For SFRA
- Story context: Cloud Kicks uses SFRA for all development; leveraging the latest ecommerce tech helps Cloud Kicks compete. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- SFRA is a real working storefront already set up using best practices in:
    - site design
    - storefront architecture ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- Benefit emphasized: saves time/resources because you don’t start from scratch; you modify SFRA to match your needs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

---

## Set Up GitHub Account (required access path)
- Vijay learns he must use **Commerce Cloud Account Manager** to access the Commerce Cloud repository on GitHub. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
    - Purpose: simplifies user access management and provides a seamless SSO experience to members in that GitHub org. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- Steps listed in the unit:
    1) Create a GitHub account.
    2) Enable two-factor authentication (2FA).
    3) Navigate to the SalesforceCommerceCloud GitHub org SSO URL.
    4) Log in via Commerce Cloud Account Manager credentials.
    5) Access the Commerce Cloud GitHub repositories (login required). ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- Access prerequisite:
    - Each user must have active/valid Account Manager credentials; check with your administrator if you don’t. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

---

## Which Repositories? (table in unit)
The unit identifies repositories Vijay needs.

**Required**
- `storefront-reference-architecture`
    - Foundation of SFRA.
    - Contains:
        - `app_storefront_base` cartridge
        - a `modules` cartridge that includes the server module. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- `storefrontdata`
    - Includes the data for SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- `sgmf-scripts`
    - Command-line tools to compile the project and upload cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

**Optional**
- `sfra-jsdoc`
    - Builds JSDoc for the project; can be extended for custom cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- `plugin-applepay`
    - Apple Pay. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

### Version awareness
- The unit notes `storefront-reference-architecture` is the latest version of SFRA and there are other branches as Salesforce develops features; SFRA Versions and Releases page helps you find the right version. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

---

## Feature cartridges + All-in-One install note (plugin_cartridge_merge)
- The unit notes you can install feature cartridges at once using the All-in-One cartridge `plugin_cartridge_merge` in Business Manager Site Import/Export, listing examples:
    - `plugin-applepay` (Apple Pay)
    - `plugin_datadownload` (GDPR-related)
    - `plugin_instorepickup` (buy-online-pick-up-in-store)
    - `plugin_giftregistry` (gift registry)
    - `plugin_productcompare` (compare products)
    - `plugin_sitemap` (sitemap)
    - `plugin_wishlist` (wishlist) ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- But: you must clone each cartridge individually into your environment, and update the full cartridge path in Business Manager. The unit shows an example cartridge path string. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

---

## Download or Clone the SFRA Repositories (procedure)
1) In GitHub, search for `storefront-reference-architecture`.
2) Click Clone or download and clone/download to local system.
3) If downloading zip files:
    - Create a new local folder
    - Move zip files to that folder
    - Open each zip file
4) Download/unzip other required repositories into the same folder. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

### Folder placement (important)
- Repositories should be placed as siblings next to each other, like the unit’s example structure (showing `storefront-reference-architecture`, `cartridges/app_storefront_base`, `cartridges/modules`, plus `sfra-jsdoc`, `storefrontdata`, `plugin-applepay`). ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

---

## Next Steps
- Next unit: install and configure SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

---

## VI (A-level: chi tiết, bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Access Salesforce B2C repositories trên GitHub.
- Mô tả benefits của SFRA.
- Download/clone các SFRA repositories. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

### Get Ready For SFRA
- Cloud Kicks dùng SFRA cho development; SFRA là storefront “thực” có sẵn best practices về site design & storefront architecture. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- Lợi ích: không cần build từ đầu; sửa/điều chỉnh SFRA để hợp nhu cầu. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

### Set Up GitHub Account (lối vào bắt buộc)
- Phải dùng **Commerce Cloud Account Manager** để access repo GitHub → giúp quản lý access và SSO mượt cho GitHub org. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- Steps theo unit: tạo GitHub account → bật 2FA → vào URL SSO của org → login bằng Account Manager creds → access repos.
- Mỗi user cần Account Manager creds hợp lệ; nếu không có thì hỏi admin. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

### Which Repositories? (đúng bảng)
- Required:
    - `storefront-reference-architecture` (nền tảng; có `app_storefront_base` + `modules` cartridge gồm server module)
    - `storefrontdata` (data)
    - `sgmf-scripts` (CLI tools để compile & upload cartridges)
- Optional:
    - `sfra-jsdoc` (build JSDoc, extend cho custom cartridges)
    - `plugin-applepay` (Apple Pay) ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- Note: có nhiều branches; xem SFRA Versions and Releases để chọn đúng version. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

### Feature cartridges + plugin_cartridge_merge
- Có thể “install at once” qua `plugin_cartridge_merge` trong Site Import/Export; danh sách ví dụ plugins như unit nêu (GDPR, instorepickup, giftregistry, productcompare, sitemap, wishlist…). ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))
- Nhưng vẫn phải clone từng plugin riêng và cập nhật cartridge path đầy đủ trong Business Manager (unit có chuỗi ví dụ). ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

### Download/Clone
- Tìm repo → Clone or download → nếu zip thì tạo folder, move zip, unzip → tải các repo required còn lại vào cùng folder.
- Cần đặt repos “sibling” cạnh nhau theo layout ví dụ của unit. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))

### Next Steps
- Unit kế tiếp: Install and Configure SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-access-repositories))