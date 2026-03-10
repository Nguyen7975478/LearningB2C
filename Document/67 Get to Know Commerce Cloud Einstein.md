# Get to Know Commerce Cloud Einstein
https://trailhead.salesforce.com/content/learn/modules/cc-einstein-plan-and-implement/cc-einstein-implementation-basics

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List three types of data that Agentforce Commerce Einstein tracks.
- List three ways that Einstein improves a shopper’s experience.
- Describe the two Einstein search features.
- Explain the differences between Einstein Search and Product Recommendations.

## What Commerce Cloud Einstein is (and what it is not)
- **Commerce Cloud Einstein** (also referenced as **Agentforce Commerce Einstein**) is an embedded **AI** capability in Salesforce **B2C Commerce**.
- “Embedded” means the platform is designed to capture and use commerce signals without requiring:
  - a third‑party recommendations provider,
  - a custom ML pipeline run by your team,
  - or a dedicated data scientist to build the baseline capability.
- It is **not** “auto-on with perfect results”:
  - You still must do **enablement** (turn on data + tools) and **implementation** (UI + configuration + testing).
  - Your site’s **catalog quality**, **search configuration**, and **slot strategy** influence the results shoppers see.

## Enablement vs Implementation (how to think about the work)
### Enablement (platform + data readiness)
Enablement is primarily about ensuring Einstein can “see” enough signals to learn:
- Enable Einstein features in **Business Manager** (especially via **Einstein Status Dashboard**).
- Enable clickstream collection (via **Privacy Settings**).
- Ensure product and order feeds are scheduled (so Einstein can learn from catalog and purchase history).
- Ensure **Configurator** is enabled and accessible.

### Implementation (storefront experience + control plane)
Implementation is about what shoppers actually experience:
- **Templates / ISML**: create places to render recommended products (content slots) and show recommendation tiles.
- **Configurator**: define recommenders (what algorithm, what context, what strategy).
- **Business Manager**: connect a content slot → template → recommender, and enable/disable supporting search features.
- Testing: validate rendering, page caching behavior, and verify that recommendations/sorting behave as intended.

## Data is key (3 data types Einstein uses)
The unit emphasizes that **data volume and quality** determine how useful Einstein is.
- **Two years of data is ideal**, but Einstein can still start learning with less (results may stabilize over time).

### 1) Clickstream (behavioral signals)
- **Clickstream** is anonymous, real-time shopper behavior data collected as the shopper navigates.
- Browser events are captured when a shopper:
  - views a product or page,
  - sees or clicks a recommendation,
  - performs a search or refines search,
  - adds an item to cart,
  - completes checkout.
- The unit references activity types such as:
  - `viewProduct` (product view)
  - `addToCart` (add to basket)
  - `finishCheckout` (purchase completed)
  - `viewReco` (recommendation viewed)

Why clickstream matters (interpretation):
- It allows Einstein to learn *intent* and *affinity signals* even when a shopper doesn’t purchase.
- It supports “people who viewed X also viewed/bought Y” style learning and predictive sorting.

### 2) Products (catalog signals)
- Product data provides the “universe” of items Einstein can recommend or sort.
- Product attributes help algorithms understand similarity and relevance (for example category, product type, variation groups, and merchandising attributes).

Why product data quality matters (interpretation):
- Poor product categorization, inconsistent attributes, or missing images can reduce recommendation quality and shopper trust.

### 3) Orders (transaction signals)
- Order history provides the strongest signal of what shoppers truly buy together and what converts.
- Order data enables insights like “commonly bought together” and supports tuning for conversion-oriented recommenders.

## What Einstein helps merchants do with aggregated data (main outcomes)
The unit describes what you can do once Einstein aggregates clickstream + product + order data:

- **Personalize Product Recommendations**: show different products to different shoppers based on behavior.
- **Personalize Search and Sorting**:
  - improve search suggestions,
  - improve ranking of results,
  - and improve product grid ordering (for both search results and category pages).
- **Improve Findability**:
  - identify new synonyms and terms (Search Dictionaries),
  - reduce “no results” searches by suggesting better terms.
- **Basket analysis**:
  - determine products frequently purchased together,
  - support merchandising strategies like bundles, deals, “complete the look”.

## Einstein feature map (what each feature does + where it’s controlled)
### 1) Commerce Insights
What it does:
- Uses product + order + behavioral signals to identify what products are purchased together.

What you use it for:
- Create bundles, cross-sell placements, and “complete the look” strategies.
- Find category-level trends (seasonal pairing patterns).

Where you work:
- Review in **Configurator** (Insights dashboards).
  Timing:
- Requires feeds and then a **24–48 hour** delay before insights populate.

### 2) Einstein Search Dictionaries (Search feature #1)
What it does:
- Observes onsite searches and recommends dictionary terms/synonyms that you should add.

What you use it for:
- Expand the site’s synonym coverage so shoppers find products even when wording differs.

Where you work:
- **Business Manager** (Search Dictionaries + notifications in Search Preferences).
  Effort:
- Low dev effort; primarily merchandiser review/approval workflow.

### 3) Einstein Search Recommendations (Search feature #2)
What it does:
- Provides personalized term completion and query correction suggestions.

What you use it for:
- Improve type-ahead search and reduce failed searches (better suggestions before submitting).

Where you work:
- Enable via **Search Preferences** in Business Manager; optional richer UX requires developer work.

### 4) Einstein Predictive Sort
What it does:
- Predictively sorts product results (search results page or category grid) using learned signals.

What you use it for:
- Show the “most likely to matter” products first for a given shopper/context.

Where you work:
- **Business Manager** sorting rules (often by copying an existing sorting rule and applying Predictive Sort).
  How to validate:
- Use **A/B Testing** to prove lift versus a control sort.

### 5) Einstein Product Recommendations
What it does:
- Generates personalized product lists from a specific **recommender** (algorithm + context) and returns them to content slots.

What you use it for:
- PDP cross-sell (“You may also like”), cart upsell, home page personalization, category support, etc.

Where you work:
- **Configurator**: create recommenders.
- **Business Manager**: assign recommenders to content slots.
- **Developer / ISML templates**: render the slot output in the storefront.

## Einstein Search vs Product Recommendations (clear difference)
### Einstein Search (search-first)
- Primary surface: **search box**, search suggestions, search results, category/search sorting.
- Controls: Search Preferences, Search Dictionaries, Sorting Rules.
- Objective: help shoppers *find* what they want quickly.

### Product Recommendations (slot-first)
- Primary surface: **content slots** across pages (PDP/cart/home).
- Controls: Configurator recommenders + slot configuration + templates.
- Objective: help shoppers *discover* additional items they didn’t explicitly search for.

## Roles and responsibilities (what each role must understand)
### Administrator
Must understand:
- Production-only data collection reality (orders/clickstream).
- Scheduling feeds in **Einstein Status Dashboard**.
- Region/host configuration and prerequisites for enabling Configurator access.

### Developer
Must understand:
- Where and how to render slots (ISML, templates).
- Page caching concerns (especially for Predictive Sort and personalization).
- How to test “empty state” (when not enough data exists yet).

### Merchandiser
Must understand:
- How to create recommenders (which algorithm for which page intent).
- How to interpret Commerce Insights to choose placements.
- How to manage search dictionary suggestions and search recommendation behavior.

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê 3 loại dữ liệu Agentforce Commerce Einstein theo dõi.
- Liệt kê 3 cách Einstein cải thiện trải nghiệm shopper.
- Mô tả 2 Einstein search features.
- Giải thích sự khác nhau giữa Einstein Search và Product Recommendations.

## Commerce Cloud Einstein là gì (và không phải là gì)
- **Commerce Cloud Einstein** (cũng gọi **Agentforce Commerce Einstein**) là **AI** được embed trong Salesforce **B2C Commerce**.
- “Embedded” nghĩa là nền tảng được thiết kế để thu thập và dùng commerce signals mà bạn không cần:
  - provider recommendations bên thứ ba,
  - tự build ML pipeline,
  - hay có data scientist để build từ đầu.
- Nhưng Einstein **không phải** kiểu “bật là xong”:
  - Bạn vẫn phải làm **enablement** (bật data + tools) và **implementation** (UI + cấu hình + test).
  - Chất lượng **catalog**, **search configuration**, và **slot strategy** ảnh hưởng trực tiếp chất lượng kết quả.

## Enablement vs Implementation (cách hiểu để làm đúng)
### Enablement (platform + data readiness)
- Bật Einstein trong **Business Manager** (đặc biệt qua **Einstein Status Dashboard**).
- Bật clickstream collection trong **Privacy Settings**.
- Schedule product/order feeds để Einstein học từ catalog + purchase history.
- Bật và xin quyền dùng **Configurator**.

### Implementation (trải nghiệm trên storefront)
- **Templates / ISML**: tạo chỗ để render recommendations (content slots + tiles).
- **Configurator**: tạo recommenders (algorithm + context + strategy).
- **Business Manager**: nối content slot → template → recommender và bật các search features.
- Testing: kiểm tra rendering, page caching, và hành vi recommendations/sorting.

## Data là nền tảng (3 loại data)
Unit nhấn mạnh “data đủ và sạch” mới tạo ra Einstein hữu ích.
- **2 years of data** là lý tưởng, nhưng có thể chạy với ít hơn (kết quả sẽ ổn định dần).

### 1) Clickstream (hành vi)
- **Clickstream** là dữ liệu anonymous, real-time về hành vi shopper.
- Browser events được ghi khi shopper:
  - view product/page,
  - view/click recommendation,
  - search/refine search,
  - add to cart,
  - finish checkout.
- Activity types unit nhắc:
  - `viewProduct`, `addToCart`, `finishCheckout`, `viewReco`

Vì sao clickstream quan trọng (giải thích ý):
- Einstein học được *intent* và *affinity signals* kể cả khi shopper chưa mua.
- Hỗ trợ dạng học “view X → view/buy Y” và predictive sorting.

### 2) Products (catalog signals)
- Product data là “vũ trụ sản phẩm” để Einstein recommend/sort.
- Attributes giúp thuật toán hiểu similarity/relevance (category, product type, variation groups…).

Vì sao chất lượng product data quan trọng:
- Category sai, attributes thiếu/không nhất quán, ảnh thiếu → recommendation kém và giảm trust.

### 3) Orders (transaction signals)
- Order history là signal mạnh nhất về “mua thật”.
- Dùng để tìm “commonly bought together” và phục vụ recommenders hướng conversion.

## Einstein giúp merchant làm gì với data aggregated
- **Personalize Product Recommendations** theo hành vi.
- **Personalize Search and Sorting**:
  - cải thiện suggestions,
  - cải thiện ranking,
  - cải thiện ordering trên grid (search + category).
- **Improve Findability**:
  - đề xuất synonyms/terms (Search Dictionaries),
  - giảm “no results” bằng term gợi ý tốt hơn.
- **Basket analysis**:
  - tìm products thường mua cùng,
  - hỗ trợ bundles/deals/complete-the-look.

## Bản đồ Einstein features (mỗi feature làm gì + cấu hình ở đâu)
### 1) Commerce Insights
- Làm gì: tìm “mua cùng nhau” dựa trên order/product/behavior signals.
- Dùng để: bundles/cross-sell/complete-the-look.
- Làm ở đâu: **Configurator**.
- Timing: cần feeds + chờ **24–48h**.

### 2) Einstein Search Dictionaries (Search feature #1)
- Làm gì: quan sát onsite searches và đề xuất terms/synonyms.
- Dùng để: mở rộng synonym coverage để tìm đúng sản phẩm khi wording khác.
- Làm ở đâu: **Business Manager** (Search Dictionaries + notifications).

### 3) Einstein Search Recommendations (Search feature #2)
- Làm gì: personalized term completion + query correction.
- Dùng để: type-ahead search tốt hơn, giảm failed searches.
- Làm ở đâu: bật trong **Search Preferences**; UX nâng cao cần dev.

### 4) Einstein Predictive Sort
- Làm gì: sort kết quả search/category grid theo predictive intelligence.
- Dùng để: đưa sản phẩm “khả năng phù hợp/có ích nhất” lên trước.
- Làm ở đâu: **Sorting Rules** trong Business Manager.
- Validate: **A/B Testing**.

### 5) Einstein Product Recommendations
- Làm gì: trả về list recommended products theo **recommender** và render vào content slots.
- Dùng để: cross-sell/upsell/personalization (PDP/cart/home…).
- Làm ở đâu:
  - **Configurator** tạo recommenders,
  - **Business Manager** assign slot,
  - **ISML/templates** render.

## Einstein Search vs Product Recommendations (hiểu đúng ý)
### Einstein Search
- Bề mặt chính: search box, suggestions, search results, category/search sorting.
- Control: Search Preferences, Search Dictionaries, Sorting Rules.
- Mục tiêu: giúp shopper *tìm* nhanh.

### Product Recommendations
- Bề mặt chính: content slots trên các trang.
- Control: recommenders (Configurator) + slot config + templates.
- Mục tiêu: giúp shopper *khám phá thêm*.

## Roles (ai cần hiểu gì)
### Administrator
- Hiểu production-only data collection, schedule feeds trong Einstein Status Dashboard, cấu hình region/host và xin Configurator access.

### Developer
- Hiểu slot rendering (ISML), page caching khi personalization/predictive sort, test empty state khi data chưa đủ.

### Merchandiser
- Hiểu tạo recommender theo intent trang, đọc Commerce Insights để chọn placements, quản lý search dictionary suggestions.