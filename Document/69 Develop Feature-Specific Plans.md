# Develop Feature-Specific Plans
https://trailhead.salesforce.com/content/learn/modules/cc-einstein-plan-and-implement/cc-develop-featurespecific-plans

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe the tasks a developer must take to implement **Predictive Sort** and **Product Recommendations**.
- List the features that you can implement with minimal effort.
- List the pre-launch steps you must take to implement **Product Recommendations** and **Predictive Sort**.
- List the post-launch steps a developer must take to implement **Product Recommendations**.

## Purpose of this unit (what you should understand)
This unit is not just a “feature list”. It explains:
- Why some Einstein features are “turn on + configure” while others require storefront engineering.
- How to plan feature rollout so you get value early (low-effort wins first) without blocking go-live.
- The specific *technical prerequisites* that developers must validate (especially **caching** behavior) so personalization is actually correct.

## Feature effort overview (what is minimal vs what needs work)
### Minimal effort: Commerce Insights
- **Commerce Insights** requires only:
  - data feeds, and
  - a login to **Configurator**.

Interpretation (to understand the “why”):
- Insights are primarily a *reporting/analysis surface*. You’re not changing storefront pages yet; you’re looking at data correlations.

### Requires more configuration (worth the effort)
These require more steps (configuration, rollout planning, and sometimes code):
- **Search Dictionaries**
- **Search Recommendations**
- **Predictive Sort**
- **Product Recommendations**

## Search Dictionaries (how Einstein generates suggestions)
Einstein generates search dictionaries based on:
- **Existing synonym groups** for a site.
  - Important implication: *If there are no synonym groups, there are no Einstein Search Dictionaries synonym suggestions.*
- **Traffic patterns**, especially:
  - the amount of traffic that reaches the **no search results page**.

Why these inputs matter (explain the idea):
- Einstein needs a “starting vocabulary” (synonym groups) and real shopper search data.
- “No results” traffic is an indicator of missing synonyms/keywords—so Einstein uses it to prioritize suggestions.

## Einstein Data Privacy Agreement (shared vs site-only suggestions)
The unit explains you can **accept the Einstein Data Privacy Agreement** to:
- *anonymously share and receive synonym suggestions* based on the **Agentforce Commerce for B2C network** search and synonym group data.
- Salesforce ensures contributed data is not disclosed in an identifiable form to other merchants.
- Salesforce may also access contributed data to train and improve the Einstein Search Dictionary and related features/services.
- If you do **not** accept the agreement:
  - Einstein uses **site data only**.

Practical meaning:
- Opting in can increase suggestion quality because the model has more aggregated examples across merchants.

## Search Preferences notifications (operational workflow for merchandisers)
- You can add email addresses to **Business Manager Search Preferences** (unit note: *on the staging instance only*) so merchandising teams are notified when they need to approve/decline search terms.

Why this matters:
- Search dictionaries are not “set and forget”.
- This creates a repeatable operations loop: Einstein suggests → merchandiser reviews → site search improves over time.

## Search Recommendations (why the unit recommends incremental rollout)
The unit warns: don’t try to implement all Search Recommendations at once.

### Typical implementation plan (4 steps)
1) **Enable Einstein Search Recommendations**
  - The machine learning algorithm starts consuming search queries.
  - Einstein begins showing search suggestions based on actual shopper searches.

2) Decide where to place Search Recommendations (needs developer help for richer UI)
  - Extend the **type-ahead search flyout** (expanding search box) to render **multiple** search suggestions (vs the default **single** suggestion).
  - This requires customization (not out-of-the-box).

3) Once design is ready, add optional Search Recommendation options:
  - **recent search phrases** (personalized list of phrases entered by the shopper)
  - **popular search phrases** (added to the recent-search customization)
  - **popular storefront searches**
  - **recent personal searches**

4) Replicate **Search Preferences** to production when ready to go live.

### Flyout design decisions (what you must define up front)
When developing the flyout, decide:
- what appears on the flyout, and
- the maximum number of results for each element, such as:
  - Business view
  - Search for / Did You Mean
  - Popular searches
  - Brands
  - Category
  - Content
  - Recently viewed

How to interpret this (to understand the intent):
- The flyout is a combined UX surface: suggestions aren’t only text; you may show brands/categories/content.
- You must limit counts to avoid slow UX or overwhelming the shopper.

## Predictive Sort (the critical developer prerequisite: caching)
- **Predictive Sort** personalizes the order in which products are displayed.
- The unit states: to implement Predictive Sort, your developer validates that caching correctly **invalidates** when Predictive Sort is applied as a sorting rule.
- This is described as a *critical prerequisite* to ensure personalization works correctly.
- After caching is validated:
  - a merchandiser can use Business Manager to copy an existing sorting rule and blend Predictive Sort into a dynamic or static sorting rule that fits the business.

### Measuring Predictive Sort
- The unit explicitly recommends **A/B Testing** as the best way to measure predictive sorting.

Why (interpretation):
- Sorting changes can feel “better” subjectively but must be validated against conversion metrics.

## Product Recommendations (what components each role owns)
The unit states Product Recommendations requires a team effort:

| Component | What it covers | Role |
|---|---|---|
| Content slots and templates | Design the content slot look and feel | Developer |
| Order history feed | Feed setup / data availability | Administrator |
| SFTP credentials | Secure file transfer capability | Administrator |
| Recommenders | Decide where recommenders live on the storefront | Merchandiser |

### Implementation steps (unit list)
- Add Product Recommendations to the **product detail page (PDP)** via a content slot associated with a recommender.
- Create recommenders in **Configurator**.
- Configure content slots in **Business Manager** to select the specific recommender to display product recommendations.

### Recommended starting point: default PDP recommender
- Start with the default **PDP recommender** (automatically available in Business Manager content slot configuration after Einstein deployment).
- The unit lists algorithm components used:
  - **View to view correlations**
  - **Product affinities**
  - **Natural language processing**

### QA guidance
- Use **preview** and the **validator tool** to ensure there are no issues.

## Basic Schedule (step-by-step responsibilities by environment)
### Development & Staging
- Test static content slot rendering.
- Prepare slot for dynamic rendering.

How to understand this:
- You first prove the slot can render “something” correctly (layout, tile component).
- Then you switch to dynamic Einstein-driven content once data and recommenders are ready.

### Production with Catalog and Inventory Assigned (Administrator + Developer tasks)
Administrator:
- Configure the host URL and region.
- Schedule the catalog and order feeds in the **Einstein Status Dashboard**.
- Wait at least **24–48 hours** for data deployment.
- Log a ticket with Salesforce Support and request initial access to Configurator.
- Provide **2 years of order history data** in the required Einstein format if not imported into Business Manager.
- **SFTP** credentials and location are automatically created after Einstein is deployed.

Developer:
- Develop static product type content slots and populate with static products or recently viewed products.
- Use **global context syntax** if possible to reduce manual slot population effort.
- After tile rendering validates:
  - update **ISML** syntax (type and context),
  - push the code,
  - enable recommendations.

### Parallel go-live note for Search Recommendations
- The unit notes merchants can go live with Search Recommendations in parallel with site go-live because of Einstein’s use of **natural language processing**.

## Multi-Product Implementation (Product Recommendations + Predictive Sort together)
The unit provides a combined plan.

### Development & Staging
Administrator:
- Configure host URL and region.
- Schedule catalog and order feeds in Einstein Status Dashboard.
- Wait **24–48 hours**.
- Support ticket for Configurator access.
- Provide 2 years of order history if needed.
- SFTP credentials and location auto-created after deployment.

Developer:
- Test static content slot rendering.

### Production with Catalog and Inventory Assigned
Administrator:
- Turn on the order and product feeds.
- Provide 2 years of order history if needed.
- SFTP credentials and location auto-created.

Developer:
- Modify code to apply **conditional page caching** and validate caching invalidates when Predictive Sort is applied.
- Develop static product type content slots and populate with static products or recently viewed products.
- Use global context syntax if possible.
- After rendering validates, update ISML type/context, push code, enable recommendations.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả các tasks của developer để implement **Predictive Sort** và **Product Recommendations**.
- Liệt kê các features implement minimal effort.
- Liệt kê các bước pre-launch cho **Product Recommendations** và **Predictive Sort**.
- Liệt kê các bước post-launch của developer cho **Product Recommendations**.

## Mục tiêu của unit (cần hiểu “ý”)
Unit này giải thích:
- Vì sao có feature chỉ “bật + cấu hình” còn có feature phải sửa storefront.
- Cách rollout theo thứ tự để có value sớm (low‑effort wins) mà không chặn go-live.
- Các prerequisite kỹ thuật (đặc biệt **caching**) phải đúng thì personalization mới “đúng thật”.

## Tổng quan effort theo feature
### Minimal effort: Commerce Insights
- **Commerce Insights** chỉ cần:
  - data feeds,
  - login **Configurator**.

Ý nghĩa:
- Insights là bề mặt phân tích/báo cáo; chưa cần thay đổi storefront.

### Cần cấu hình nhiều hơn (đáng làm)
- **Search Dictionaries**
- **Search Recommendations**
- **Predictive Sort**
- **Product Recommendations**

## Search Dictionaries (Einstein tạo suggestions dựa trên gì)
Einstein tạo search dictionaries dựa trên:
- **Synonym groups** hiện có của site.
  - Nếu không có synonym groups ⇒ không có Einstein Search Dictionaries synonym suggestions.
- **Traffic** (đặc biệt lượng traffic đi tới trang **no search results page**).

Ý nghĩa:
- Einstein cần “vốn từ ban đầu” + dữ liệu search thực tế.
- No-results traffic là tín hiệu mạnh về việc thiếu synonyms/keywords.

## Einstein Data Privacy Agreement (shared vs site-only)
- Bạn có thể **accept Einstein Data Privacy Agreement** để:
  - chia sẻ và nhận synonym suggestions ẩn danh dựa trên dữ liệu mạng **Agentforce Commerce for B2C**.
- Salesforce đảm bảo dữ liệu không bị lộ dạng identifiable cho merchants khác.
- Salesforce có thể dùng dữ liệu đóng góp để train và cải thiện Search Dictionary và features liên quan.
- Nếu không accept:
  - Einstein dùng **site data only**.

Ý nghĩa:
- Opt-in thường giúp suggestions “tốt hơn” vì có nhiều ví dụ tổng hợp hơn.

## Email notifications trong Search Preferences (workflow vận hành)
- Có thể thêm email trong **Business Manager Search Preferences** (unit note: *chỉ trên staging*) để notify merchandising team approve/decline terms.

Ý nghĩa:
- Dictionaries cần vận hành liên tục: Einstein gợi ý → merchandiser duyệt → search tốt dần.

## Search Recommendations (vì sao nên rollout theo increments)
### Kế hoạch 4 bước (unit)
1) Enable Einstein Search Recommendations:
- ML consume search queries và tìm phrases để recommend → bắt đầu có suggestions từ actual searches.

2) Quyết định vị trí hiển thị (cần dev nếu muốn “xịn” hơn):
- Extend **type-ahead search flyout** để hiển thị **nhiều** suggestions (thay vì default 1).
- Cần customization (không out-of-the-box).

3) Khi design sẵn sàng, thêm options:
- **recent search phrases**
- **popular search phrases**
- **popular storefront searches**
- **recent personal searches**

4) Replicate Search Preferences sang production khi ready go-live.

### Flyout cần thống nhất gì
- Nội dung hiển thị và số lượng tối đa mỗi phần:
  - Business view; Search for/Did You Mean; Popular searches; Brands; Category; Content; Recently viewed.

Ý nghĩa:
- Flyout là UX tổng hợp (không chỉ text).
- Phải giới hạn số lượng để UX nhanh và không overwhelm.

## Predictive Sort (prerequisite quan trọng nhất: caching)
- Predictive Sort cá nhân hóa thứ tự hiển thị sản phẩm.
- Developer phải validate caching **invalidate đúng** khi áp Predictive Sort như một sorting rule (critical prerequisite).
- Xong phần caching thì merchandiser copy sorting rule và blend Predictive Sort vào dynamic/static sorting rule phù hợp.

### Đo hiệu quả
- Unit khuyến nghị **A/B Testing** là cách tốt nhất đo impact.

## Product Recommendations (role-based components)
| Component | Nội dung | Role |
|---|---|---|
| Content slots + templates | thiết kế UI slot | Developer |
| Order history feed | feed/data | Administrator |
| SFTP credentials | file transfer | Administrator |
| Recommenders | quyết định vị trí recommenders | Merchandiser |

### Steps (unit)
- Add reco vào **PDP** qua content slot + recommender.
- Tạo recommenders trong **Configurator**.
- Business Manager: slot chọn đúng recommender.

### Bắt đầu với default PDP recommender
- Có sẵn sau deploy; algorithms:
  - **View to view correlations**
  - **Product affinities**
  - **Natural language processing**

### QA
- Dùng **preview** và **validator tool**.

## Basic Schedule (theo environment)
### Development & Staging
- Test static slot rendering.
- Prepare slot for dynamic rendering.

Ý nghĩa:
- Chứng minh layout/tile render đúng trước, rồi mới chuyển sang dynamic.

### Production (Catalog + Inventory assigned)
Administrator:
- Configure host URL + region; schedule feeds; chờ **24–48h**; ticket Support xin Configurator access; cung cấp **2 years** order history nếu cần; SFTP auto-created.

Developer:
- Build static product slots; dùng **global context syntax** nếu có; validate tiles; update **ISML** type/context; push code; enable recommendations.

### Note
- Search Recommendations có thể go live song song site go-live nhờ **natural language processing**.

## Multi-Product Implementation (Recommendations + Predictive Sort)
- Dev/Staging: admin làm host/region/feeds/wait/support/order history; dev test static slot rendering.
- Production: admin bật feeds; dev làm **conditional page caching** + validate invalidate; tiếp tục slot work; update ISML; enable recommendations.