# Generate Sitemaps
https://trailhead.salesforce.com/content/learn/modules/b2c-xml-sitemaps/b2c-xml-generate-sitemaps

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List three steps you take to configure Salesforce B2C Commerce sitemaps.
- List the three sitemap attributes that a feed uses.
- Describe how to run a sitemap job.
- Explain how sitemap generation works on instances.
- Explain how links per sitemap work.

## Prerequisites and assumptions (unit context)
- The module assumes you’re a B2C Commerce merchandiser with the proper permissions.
- You can’t follow these steps in a Trailhead Playground because B2C Commerce isn’t available there.
- If you have a sandbox instance, you can practice there.

## 3-step sitemap configuration approach
The unit’s high-level process:
1) Configure sitemap attributes in the data (via a **feed** or manually in Business Manager).
2) Generate sitemaps in Business Manager.
3) Create a search engine account and verify site ownership.

## Links per sitemap (0–50,000) and file generation behavior
- Links per sitemap setting ranges from **0 to 50,000**.
- When a sitemap file (for example `sitemap-1.xml`) reaches the configured number, B2C Commerce creates the next file (`sitemap-2.xml`).
- Example:
    - 25,000 links and setting 5,000 → 5 sitemap files
    - 25,000 links and setting 25,000 → 1 sitemap file

## Instance best practices (where to configure vs where “live” must be)
- Brandon configures sitemaps in **staging** and replicates them into **development** and **production** (best practice).
- Warning: importing a catalog directly into production can cause issues (for example, SEO URLs not being generated correctly).
- Important warning: generate the “live” sitemaps on the **production** instance; otherwise bots might index staging URLs if storefront password protection isn’t enabled.

## Generate sitemaps in Business Manager (step-by-step)
1) Business Manager → App Launcher → **Merchant Tools | site | SEO | Sitemaps**
    - If sitemap files already exist, you see a list including sitemap index files and custom sitemaps.
    - B2C Commerce keeps a sitemap until it generates a new one.
2) Select the **hostname** (example: `www.cloudkicks.com`)
    - All hostnames defined for a site appear here (and they won’t redirect to another).
    - Each hostname has its own sitemap files.
    - If you don’t have a hostname listed, you must configure it in the hostname alias file.
3) Use **Download** (if active) to download sitemap files for the selected host.
4) Open the **Settings** tab (this is where you create/regenerate sitemaps and configure key options).

## Settings tab details (what you configure)
### Includes & Updates
The unit’s example values:
- Sitemap Included: enabled
- Asset change frequency: **daily**
- Asset priority: **0.5**

### Configuration
The unit’s example values:
- Links per Sitemap File: `5000`
- Image View Type: `swatch`
- Include Products: **Available and Orderable Products Only**

### Alternate URLs
The unit’s example values:
- ISO code for the default locale: `en`
- Mobile screen width: `640`

### Included Locales
- Select the locales to include in the sitemap set.
- Click **Apply** to save the sitemap settings.

## Custom sitemaps (upload additional sitemap files)
- Brandon creates a custom sitemap file (for a subset of products) to test URL look/behavior.
- B2C Commerce automatically adds uploaded custom sitemap files to the index file without overriding system-generated sitemaps.

Steps:
1) Merchant Tools | site | SEO | Sitemaps
2) Custom Sitemaps tab
3) Select host
4) Upload one or more valid sitemap XML files

## Feeds: the three sitemap attributes
- The feed uses:
    - `sitemap-included-flag`
    - `sitemap-changefrequency`
    - `sitemap-priority`
- The unit states these attributes are defined in import/export XML schema:
    - `catalog.xsd`
    - `library.xsd`

## Run a sitemap job (manual vs scheduled + what logs tell you)
- Running the sitemap job provides details such as:
    - counts of products/images/categories/folders/content assets assigned, skipped, and added
    - errors that occurred during generation
- You can run the job manually or schedule it.
- Unit guidance:
    - Infrequent updates or major URL changes → run **manually**
    - Frequent updates → run **scheduled** at low-traffic time (early morning); daily or every other day is sufficient

### Job tab walkthrough (schedule + run now)
1) Merchant Tools | site | SEO | Sitemaps → **Job** tab
2) Configure schedule:
    - Job Enabled
    - Start date/time
    - Interval (hours/days/weeks/months; unit shows an example like every 60 minutes + every day)
    - Apply
3) Run manually:
    - Click **Run Now**
    - Click **Refresh** to see status
4) Review logs:
    - Success / Error status
    - Logfile details while it builds

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê 3 bước cấu hình B2C Commerce sitemaps.
- Liệt kê 3 sitemap attributes feed dùng.
- Mô tả cách chạy sitemap job.
- Giải thích sitemap generation theo instances.
- Giải thích links per sitemap hoạt động thế nào.

## Prerequisites (bối cảnh unit)
- Unit giả định bạn là merchandiser có đủ permissions.
- Không làm được trong Trailhead Playground vì B2C Commerce không có ở đó.
- Nếu có sandbox instance, bạn có thể luyện tập.

## Quy trình 3 bước cấu hình sitemap
1) Cấu hình sitemap attributes trong data (qua **feed** hoặc thủ công trong Business Manager).
2) Generate sitemaps trong Business Manager.
3) Tạo account ở search engine và verify site ownership.

## Links per sitemap (0–50,000) và cách tạo nhiều files
- Setting links per sitemap từ **0–50,000**.
- File đạt ngưỡng thì B2C Commerce tạo file kế tiếp.
- Ví dụ:
    - 25,000 links, setting 5,000 → 5 files
    - setting 25,000 → 1 file

## Best practices theo instance
- Brandon cấu hình ở **staging** rồi replicate sang **development** và **production**.
- Cảnh báo: import catalog trực tiếp vào production có thể gây issues (ví dụ SEO URLs không generate đúng).
- Cảnh báo quan trọng: “live” sitemaps phải generate trên **production**, nếu không bots có thể index staging nếu chưa bật storefront password protection.

## Generate sitemaps trong Business Manager (step-by-step)
1) **Merchant Tools | site | SEO | Sitemaps**
    - Nếu đã có, sẽ thấy sitemap index files và custom sitemaps.
    - B2C Commerce giữ sitemap cũ cho đến khi tạo sitemap mới.
2) Chọn **hostname** (ví dụ `www.cloudkicks.com`)
    - Mỗi hostname có sitemap files riêng.
    - Nếu không thấy hostname, cần cấu hình trong hostname alias file.
3) **Download** (nếu có) để tải sitemaps của host đã chọn.
4) Vào **Settings** tab để create/regenerate và cấu hình.

## Settings tab (các cấu hình chính)
### Includes & Updates
- Sitemap Included
- Asset change frequency: **daily**
- Asset priority: **0.5**

### Configuration
- Links per Sitemap File: `5000`
- Image View Type: `swatch`
- Include Products: **Available and Orderable Products Only**

### Alternate URLs
- ISO code default locale: `en`
- Mobile screen width: `640`

### Included Locales
- Chọn locales cần include → **Apply**

## Custom sitemaps (upload thêm sitemap XML)
- Brandon tạo custom sitemap để test URL look/behavior.
- File upload tự được thêm vào index, không override system-generated sitemaps.

Steps:
- Sitemaps → Custom Sitemaps tab → chọn host → upload XML hợp lệ.

## Feed: 3 sitemap attributes
- `sitemap-included-flag`, `sitemap-changefrequency`, `sitemap-priority`
- Nằm trong schema `catalog.xsd` và `library.xsd`

## Chạy sitemap job (manual/scheduled + logs)
- Job cho counts assets assigned/skipped/added và errors.
- Guidance:
    - ít update / thay đổi lớn → chạy **manual**
    - update thường xuyên → **schedule** low-traffic; daily hoặc every other day

### Job tab walkthrough
- Sitemaps → Job tab → enable + schedule → Apply → Run Now → Refresh → xem Success/Error + logfile.