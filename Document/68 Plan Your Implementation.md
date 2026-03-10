# Plan Your Implementation
https://trailhead.salesforce.com/content/learn/modules/cc-einstein-plan-and-implement/cc-einstein-plan-implementation

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List the general steps you take to implement Commerce Cloud Einstein.
- List three features that you can test after data enablement.
- Describe the methodology that makes the best use of data.

## Why implementation requires planning (unit core message)
- Einstein implementation is cross-functional and touches:
  - data enablement (feeds + clickstream),
  - storefront rendering (templates/slots),
  - merchandiser configuration (Configurator + Business Manager),
  - and measurement (A/B testing).
- Therefore, a plan is required so each role knows:
  - what must happen first,
  - what can be tested early,
  - what needs waiting time (24–48 hours),
  - and what must be validated (caching).

## Who is on the implementation team (roles)
The unit explicitly states the implementation team includes:
- a Agentforce Commerce for B2C **administrator**
- a **developer**
- a **merchandiser**

How to interpret roles:
- Admin = data + platform enablement
- Developer = storefront experience + technical validation
- Merchandiser = recommender strategy + configuration + optimization

## General steps to implement Einstein (unit step list, with meaning)
1) **Enable the data** in **Einstein Status Dashboard** in Business Manager (admin).
  - Meaning: turn on and schedule the data flows Einstein needs.

2) **Modify the templates** (developer).
  - Meaning: add or update storefront templates so Einstein-powered content can render.

3) **Create custom recommenders** in the **Configurator** (merchandisers).
  - Meaning: define the recommender strategies Einstein will use for Product Recommendations.

4) **Configure content slots** in Business Manager (merchandisers).
  - Meaning: connect a slot location + rendering template + specific recommender.

5) **Go live** (all).
  - Meaning: production is where data is collected; live usage strengthens model output.

6) **A/B test and add recommenders throughout the site** (merchandisers).
  - Meaning: optimize placements using test-and-learn rather than assumptions.

## Enable the Data (where Einstein runs, collects, and what feeds exist)
### Primary instance group (where Einstein runs for activation/testing)
- Einstein only runs on the **primary instance group**:
  - development
  - staging
  - production

### Production-only collection
- Einstein only **collects data on production** (where shoppers look and buy).
- A sandbox instance is **not involved**.

### Einstein data feeds (unit list)
- One-time historical order feed
- Daily order feed
- Daily product feed
- Commerce Insights
- Einstein Search Dictionaries

## Commerce Insights waiting period + Configurator access (key operational sequence)
- **Commerce Insights** requires a mandatory **24–48 hour** waiting period after feed configuration before reports are available.
- After that waiting period:
  - log a ticket with Salesforce Support
  - request initial **Site Admin** access to the Configurator tool

Why this is important:
- Teams must schedule “waiting time” into the plan; otherwise they assume something is broken.

## Administrator tasks during enablement (what exactly they do)
The unit states the administrator uses the production instance of Business Manager to:
- collect credentials
- schedule the catalog and order feed from the Einstein Status Dashboard

Interpretation:
- The admin’s work is the “foundation”—without feeds, merchandisers won’t see meaningful insights/recommender performance.

## Clickstream Data (how to enable it and why)
- Einstein captures real-time clickstream data for its algorithms.
- Setup steps in unit:
  1) Business Manager → App Launcher
  2) Merchant Tools | Site | Site Preferences | **Privacy Settings**
  3) Enable clickstream data

Why clickstream is critical (interpretation):
- Clickstream provides high-volume behavioral signals (views/search) that appear long before enough orders accumulate.

## After data enablement: what is ready to test without development effort
The unit explicitly states:
- After data enablement, some features are ready to test without development effort or quality assurance.

Based on the unit’s flow and feature descriptions, the “ready quickly” items include:
- **Commerce Insights** (after the mandatory waiting period)
- **Einstein Search Dictionaries**
- (and generally “data availability” itself, via dashboard status)

## Develop Templates (developer responsibilities, with “why”)
- Developer gathers requirements and comp designs to create or modify storefront templates.
- When finished, **Product Recommendations** template is ready to test.

### Predictive Sort: cache invalidation validation (unit requirement)
- For Predictive Sort, the developer validates cache invalidation on:
  - category grid pages
  - search grid pages
    if Predictive Sort is activated.
- The unit points to the Infocenter “iscache” guidance: “If Attribute Example section”.

Meaning:
- Personalization changes ordering per shopper/context; cached pages can break personalization if not invalidated correctly.

### Einstein Search Recommendations: developer scope is optional
- Merchandiser can enable personalized auto-correction and term completion instantly in Business Manager.
- Developer effort is needed only for optional enhancements, such as:
  - configuring the search flyout to present available options specific to popular searches and recent searches,
  - extending search flyout functionality.
- The unit references the “Feature versus Effort” concept in the Set Up Search Recommendations module.

## Configure Recommenders (what it means)
- Merchandisers use **Configurator** to create recommenders:
  - a set of rules and strategies used by **Product Recommendations**.
- Recommenders tell the storefront what to display based on Einstein data.

Support tool:
- The unit names the **Commerce Cloud Recommendation Validator (Chrome Extension)** as the tool that validates recommendation activities on the storefront.

## Review Einstein Revenue (post-go-live KPI monitoring)
- Merchandisers monitor the Einstein Dashboard in Commerce Cloud Reports and Dashboards software.
- They compare:
  - Einstein attributed revenue
  - relative to overall site revenue
- Then they share results with managers.

Why this matters:
- It creates an ongoing business feedback loop: “did Einstein impact revenue?”

## Put the Data to Work (test-and-learn methodology)
- After Einstein Recommendations are live in production:
  - develop a **test-and-learn** methodology.
- Use:
  - Business Manager **A/B testing**, or
  - third‑party platform tools.
- For in-depth A/B test review, consult a Commerce Cloud Customer representative.

## Sample Einstein Implementation Timeline (step table, summarized clearly)
The unit includes a step-by-step timeline for sites going live. Key steps include:

**Plan**
1) Review Site Readiness Assessment (**SRA**), define feature scope, agree on development steps.
2) Define content slots and assets for Product Recommendations.
3) Clarify technical questions around recommendations styling and search functionality.

**Develop**
4) Update/create search flyout, storefront template code, slot rendering; follow Einstein best practices.

**Deploy**
5) Begin Einstein activation after site is on production Business Manager, with catalog assigned and products with inventory.
6) Ensure merchandiser email addresses are set up in B2C Commerce Account Manager.
7) Request Configurator access (and optionally SFTP external/store order feed credentials) from Support.
8) Wait 24–48 hours for initial data deployment.
9) Request Support to add initial Site Admin user to Configurator.
10) (Optional) Send external order data via SFTP so Einstein can use external store data.
11) After Site Admin is provisioned, access Configurator and add merchandiser email with user access.

**Test**
12) Validate in staging:
- Product Recommendations
- Predictive Sort
- Search Recommendations

**Run**
13) Einstein goes live.
14) Review best practices with merchandising team.
15) Create A/B tests to measure success.

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê các bước tổng quát triển khai Commerce Cloud Einstein.
- Liệt kê 3 features có thể test sau data enablement.
- Mô tả methodology tận dụng data hiệu quả nhất.

## Vì sao cần plan (thông điệp chính của unit)
- Triển khai Einstein là cross‑functional, chạm vào:
  - enable data (feeds + clickstream),
  - storefront rendering (templates/slots),
  - cấu hình merchandiser (Configurator + Business Manager),
  - đo lường (A/B testing).
- Vì vậy cần plan để:
  - biết việc nào làm trước,
  - việc nào test sớm được,
  - chỗ nào phải chờ (24–48h),
  - và cái gì cần validate (caching).

## Team triển khai gồm ai (roles)
Unit nêu team gồm:
- Agentforce Commerce for B2C **administrator**
- **developer**
- **merchandiser**

Cách hiểu:
- Admin = nền tảng dữ liệu + enablement
- Dev = trải nghiệm storefront + validate kỹ thuật
- Merch = chiến lược recommender + cấu hình + tối ưu

## Các bước triển khai Einstein (kèm ý nghĩa)
1) Enable data trong **Einstein Status Dashboard** (admin).
2) Modify templates (dev).
3) Create custom recommenders trong **Configurator** (merch).
4) Configure content slots trong Business Manager (merch).
5) Go live (team).
6) A/B test + mở rộng recommenders (merch).

## Enable the Data
### Einstein chạy ở đâu
- Chỉ chạy trên primary instance group: dev/staging/prod.

### Data collect ở đâu
- Chỉ collect data ở **production**; sandbox không tham gia.

### Data feeds (unit)
- One-time historical order feed; Daily order feed; Daily product feed; Commerce Insights; Einstein Search Dictionaries.

## Commerce Insights: chờ 24–48h + xin Configurator access
- Chờ **24–48 hours** sau feed mới có report.
- Sau đó log ticket Support xin **Site Admin** access cho Configurator.
- Ý nghĩa: phải đưa “waiting time” vào plan.

## Admin làm gì khi enablement
- Dùng production Business Manager để:
  - collect credentials
  - schedule catalog + order feed trong Einstein Status Dashboard

## Clickstream Data (Privacy Settings)
- Bật clickstream:
  - Merchant Tools | Site | Site Preferences | **Privacy Settings** → enable.

Ý nghĩa:
- Clickstream cho tín hiệu hành vi số lượng lớn, đến sớm hơn orders.

## Sau data enablement: test sớm được gì
- Unit nói có features test được mà không cần dev/QA.
- Thực tế:
  - Commerce Insights (sau khi chờ)
  - Einstein Search Dictionaries
  - kiểm tra data availability trên dashboard

## Develop Templates (dev làm gì và vì sao)
- Dev lấy requirements + comp designs để sửa templates.
- Xong thì template Product Recommendations sẵn sàng test.

### Predictive Sort: validate cache invalidation (yêu cầu unit)
- Dev phải validate cache invalidation trên category/search grid pages khi Predictive Sort activated.
- Unit trỏ tới hướng dẫn Infocenter về `iscache`.

Ý nghĩa:
- Personalization mà cache sai → hiển thị sai thứ tự.

### Search Recommendations: dev scope optional
- Merch có thể bật auto-correction/term completion ngay.
- Dev cần nếu muốn mở rộng search flyout (popular/recent options).

## Configure Recommenders
- Merch tạo recommenders trong Configurator (rules + strategies cho Product Recommendations).
- Tool hỗ trợ validate: **Commerce Cloud Recommendation Validator (Chrome Extension)**.

## Review Einstein Revenue
- Merch theo dõi Einstein Dashboard trong Reports & Dashboards để so Einstein attributed revenue với overall revenue.

## Put the Data to Work (test-and-learn)
- Live rồi: dùng test-and-learn bằng A/B testing hoặc tool khác; phân tích sâu có thể nhờ Customer representative.

## Sample timeline (tóm rõ các mốc)
- Plan (SRA, scope, slots/assets, technical alignment)
- Develop (search flyout + templates + slot rendering)
- Deploy (activate trên production; set merch emails; request Configurator access; chờ 24–48h; Support cấp Site Admin; optional external orders via SFTP; add merch access)
- Test (staging: Recommendations, Predictive Sort, Search Recommendations)
- Run (go-live + best practices + A/B tests)