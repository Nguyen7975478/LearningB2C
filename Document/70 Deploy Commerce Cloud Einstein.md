# Deploy Commerce Cloud Einstein
https://trailhead.salesforce.com/content/learn/modules/cc-einstein-plan-and-implement/cc-einstein-deploy-site

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List the type of data that Einstein tracks.
- Explain the importance of the Einstein Data Privacy Agreement.
- List four actions the Agentforce Commerce Recommendations Validator tracks.
- List the two ways you can activate feeds during deployment.
- Explain how Einstein uses the data feeds.

## What “deploy” means here (deployment = data + activation pipeline)
This unit defines deployment in a practical way:
- “Deploying Einstein” is not just turning on a checkbox.
- It is the controlled process where:
    - catalog and order data feeds are transferred to Einstein,
    - predictive machine-learning models use feeds to generate outputs,
    - and results become available to the storefront and to **Configurator**.

## Where’s the data? (3 sources Einstein uses)
The unit stresses: ML needs large datasets; **2 years of data is ideal**, but Einstein works with what you have.

Einstein uses:

### 1) Catalog
- Product information stored in the catalog.
- Collected by running a **catalog feed** against the **production** instance.

### 2) Orders
- Order information generated on the storefront.
- Collected by running an **order feed** against the **production** instance.

### 3) Clickstream
- Collected automatically in real time using **pixel tracking**.
- It is live data; no extra manual step is required to collect it.

## How Einstein uses the data (what the models produce)
Einstein uses machine-learning models to:
- Analyze catalog + order + clickstream data.
- Identify products frequently purchased together:
    - to power more effective product sets, bundles, and promotions.
- Identify terms to add to search dictionaries:
    - to improve search results.
- Use **content slots** to show recommended products.
- Use a **search flyout** + **Business Manager settings** to personalize type-ahead search guidance.
- Sort search results.

How to interpret this (to understand “why feeds matter”):
- Feeds are not “reporting only”; they directly affect what the storefront surfaces (recommendations and sorting).
- Clickstream provides real-time intent signals, while orders provide conversion truth.

## Enable Activity Tracking for Storefront (clickstream enablement)
Einstein uses browser-based activity tracking to respond to shopper actions in real time.
To ensure activities are enabled in production:

1) Business Manager → Apps Launcher
2) Merchant Tools | Site | Site Preferences | **Privacy Settings**
3) Select **Enabled for Tracking** (default for new storefront sessions)
4) Click **Apply**

Important meaning:
- If tracking is not enabled, you may see missing/invalid events and weaker model learning.

## Agentforce Commerce Recommendation Validator (Chrome extension)
### What it is used for
- The **Recommendation Validator** Chrome extension is used by merchandisers to validate and debug:
    - Einstein product recommendations
    - sorting rules (including Predictive Sort)
- It provides a dashboard to:
    - analyze baskets,
    - view site activity,
    - view site recommendations,
    - view email recommendations data.

Constraint:
- The extension is only available for **Google Chrome**.

### How to load/install it (unit steps)
1) In Chrome, open the extension page in the **Chrome Web Store**.
2) Click **Add To Chrome**.
3) Click **Add Extension** to confirm.

### When it runs + what you see
- The Validator begins running once installed.
- When you visit a storefront using Einstein:
    - it instantly validates recommendation activities and sorting rules.
- When it recognizes events:
    - a numbered footnote appears on the extension icon showing how many events it caught.

### How to use it (unit steps)
1) Open the storefront.
2) Trigger activities by navigating (category → product → recommendations → cart → checkout, etc.).
3) Click the Validator icon when footnotes appear to view status.
4) Review recognized events (example mentioned: `clickCategory` activity).
5) Once recommendations are enabled, the Recommendation tab populates with recommender details.

## Validator Events (action → trigger → result)
The unit provides a mapping of:
- what the shopper does,
- what the code trigger is,
- and what the Validator shows if implementation is correct.

### Four actions (Learning Objective focus) — plus more events listed
The Learning Objective asks for four actions; the unit’s event table includes at least these (and more):

1) Click a category
- Trigger: `viewCategory`
- Result: “viewCategory is Okay” (if clickstream tracking is configured correctly)

2) Click a product
- Trigger: `viewProduct`
- Result: “viewProduct is Okay” (if tracking is configured correctly)

3) View recommendations content slot
- Trigger: `viewReco`
- Result: “viewReco is Okay” (if recommendations enabled and working); recommender details are available in the Recommendation tab

4) Click a recommended product
- Trigger: `clickReco`
- Result: “clickReco is Okay” (if tracking is configured correctly)

Additional events in the table (important for full understanding):
- Add an item to the cart → `addToCart` → “addToCart is Okay”
- Click to begin checkout → `beginCheckout` → “beginCheckout is Okay”
- Finish checkout → `finishCheckout` → “finishCheckout is Okay”
- Perform a search and results display → `viewSearch` → “viewSearch is Okay”

Why this is important:
- These events are the “health signals” proving:
    - clickstream is captured,
    - recommendations are rendered,
    - and the storefront is sending the right signals for Einstein learning and measurement.

## Deploy Einstein (Einstein Status Dashboard workflow)
### What deployment service does (unit concept)
- The **Einstein Deployment service** transfers data from product catalog and order feeds to Einstein.
- Predictive ML models use these feeds to generate recommendations.
- Deployment also feeds data into **Configurator**, where merchandisers fine-tune business rules.

### Frequency trade-offs (why scheduling matters)
- An administrator controls how often data deploys.
- Deploy often enough to keep data fresh.
- Because deployment can impact storefront performance:
    - choose frequency based on catalog change frequency,
    - and expect to adjust after a few tries.

### Steps to initiate deployment feeds (unit steps)
1) Business Manager → Apps Launcher → Administration | Operations | **Einstein Status Dashboard**
2) In the Site column, click the site to configure.
3) Select **Region** corresponding to your primary business geography.
    - This determines where predictive data is physically stored and processed (example: The Americas).
4) For Einstein search dictionary suggestions:
    - configure the Region setting in **production and staging** instances.
5) Modify **Host** if needed (example: `www.northerntrailoutfitters.com`, exclude `https://`).
6) Select one or more features to include:
    - **Out-of-Stock Products**
    - **Variation Products** (variation groups level, e.g., color level)
    - **Multi-Locale**
7) Select/enter the date after export orders were created.
8) Enter maximum orders per run (example: `10,000`).
9) Select the **On** switch.
    - If inactive, catalog and order feeds are not scheduled.
10) Schedule:
- run immediately (one-time), or
- set a recurring schedule.
11) Click **Save**.

### Activation delay after initial feed setup
- The unit states: the system takes **24–48 hours** to process the data before Einstein features become active.

## Two ways to activate feeds (explicit in unit)
- Run feeds **immediately** for a one-time capture.
- Configure a **recurring schedule**.

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê loại dữ liệu Einstein theo dõi.
- Giải thích tầm quan trọng của Einstein Data Privacy Agreement.
- Liệt kê 4 actions mà Agentforce Commerce Recommendations Validator track.
- Liệt kê 2 cách activate feeds khi deploy.
- Giải thích Einstein dùng data feeds như thế nào.

## “Deploy” nghĩa là gì (deploy = pipeline dữ liệu + activation)
Unit mô tả deploy theo cách thực tế:
- Deploy Einstein không chỉ là bật checkbox.
- Đây là quá trình có kiểm soát, trong đó:
    - feeds catalog/order được chuyển sang Einstein,
    - ML models dùng feeds để tạo outputs,
    - kết quả có thể dùng trên storefront và trong **Configurator**.

## Dữ liệu ở đâu? (3 nguồn)
Unit nhấn mạnh ML cần dataset lớn; **2 years** là lý tưởng nhưng vẫn chạy được.

Einstein dùng:

### 1) Catalog
- Product information trong catalog.
- Thu bằng **catalog feed** chạy trên **production**.

### 2) Orders
- Order information tạo từ storefront.
- Thu bằng **order feed** chạy trên **production**.

### 3) Clickstream
- Thu tự động real time qua **pixel tracking**.
- Là live data; không cần thao tác thủ công để “bắt đầu thu”.

## Einstein dùng data để làm gì (đầu ra của models)
- Analyze data.
- Tìm products thường mua cùng → sets/bundles/promotions tốt hơn.
- Tìm terms để thêm vào search dictionaries → search tốt hơn.
- Dùng **content slots** để show recommended products.
- Dùng **search flyout** + **Business Manager settings** để personalize type-ahead guidance.
- Sort search results.

Ý nghĩa:
- Feeds ảnh hưởng trực tiếp những gì storefront hiển thị, không chỉ report.
- Clickstream = intent signals; Orders = conversion truth.

## Enable Activity Tracking (Privacy Settings)
Steps (production):
1) Business Manager → Apps Launcher
2) Merchant Tools | Site | Site Preferences | **Privacy Settings**
3) **Enabled for Tracking**
4) **Apply**

Ý nghĩa:
- Không enable tracking → events thiếu/invalid → model yếu và khó validate.

## Agentforce Commerce Recommendation Validator (Chrome Extension)
### Dùng để làm gì
- Tool cho merchandiser validate/debug:
    - Einstein product recommendations
    - sorting rules (Predictive Sort)
- Có dashboard để:
    - basket analysis
    - xem site activity
    - xem site recommendations
    - xem email recommendations data
- Chỉ có trên **Google Chrome**.

### Cách cài (unit)
- Chrome Web Store → Add To Chrome → Add Extension.

### Khi chạy + dấu hiệu nhận biết
- Cài xong là chạy.
- Vào site có Einstein → validate ngay.
- Nhận event → icon có số (footnote) thể hiện số events bắt được.

### Cách dùng (unit)
- Mở storefront → trigger activities → bấm icon Validator → xem status → xem list events (ví dụ `clickCategory`) → Recommendation tab có details khi đã enable.

## Validator Events (action → trigger → result)
### 4 actions chính (theo Learning Objective) và các event khác
1) Click category → `viewCategory` → “viewCategory is Okay”
2) Click product → `viewProduct` → “viewProduct is Okay”
3) View recommendations content slot → `viewReco` → “viewReco is Okay”
4) Click recommended product → `clickReco` → “clickReco is Okay”

Các events khác cũng có trong bảng:
- addToCart, beginCheckout, finishCheckout, viewSearch → đều hiển thị “is Okay” nếu tracking đúng.

Ý nghĩa:
- Đây là “health checks” chứng minh clickstream + recommendations + sorting đã được instrument đúng.

## Deploy Einstein (Einstein Status Dashboard)
### Deployment service làm gì
- **Einstein Deployment service** chuyển data từ feeds sang Einstein.
- ML models dùng feeds để generate recommendations.
- Đồng thời feed data vào **Configurator** để merchandiser fine-tune business rules.

### Tần suất deploy (trade-off)
- Deploy đủ thường xuyên để data fresh.
- Nhưng deploy có thể ảnh hưởng performance → chọn frequency theo catalog change frequency và chỉnh vài lần để tối ưu.

### Steps initiate feeds (unit)
- Administration | Operations | **Einstein Status Dashboard** → chọn site → chọn **Region** (nơi lưu/xử lý predictive data) → (Search Dictionaries: set region trên prod + staging) → set **Host** (không `https://`) → chọn features (Out-of-Stock, Variation Products, Multi-Locale) → date → max orders/run (ví dụ 10,000) → On → schedule (one-time hoặc recurring) → Save.

### Chờ activate
- Cần **24–48 hours** để process trước khi Einstein active.

## 2 cách activate feeds
- Run ngay (one-time)
- Schedule định kỳ (recurring)