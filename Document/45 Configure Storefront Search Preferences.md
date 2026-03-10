# Configure Storefront Search Preferences
https://trailhead.salesforce.com/content/learn/modules/b2c-storefront-search/b2c-configure-storefront-search-preferences

## English

## Learning Objectives
- Explain the **match type** settings.
- Describe the **product availability** settings.
- List the six **search settings**.
- List the three **email settings**.

## What Search Preferences control (unit overview)
- Search preferences control how B2C Commerce search:
    - shows only available/orderable products (availability filtering),
    - makes query autocorrections,
    - integrates with Commerce Cloud Einstein features,
    - applies rules for search redirects,
    - and sends automatic email notifications for key search/indexing events.
- All configuration is done in **Business Manager**.

## Product availability settings
- The unit focuses on preventing shopper frustration by ensuring search results reflect what can actually be purchased.
- Key setting used in the walkthrough:
    - **Show Orderable Products Only** (so search results exclude products that can’t be ordered).

## Match type settings (Search Redirect Keyword Rules)
- Used when keywords are configured in **Search Driven Redirects**.
- Purpose: control how shopper input matches redirect keywords so results are not overly strict.
  Settings described:
- **Exact**: shopper must enter the exact phrase.
- **Phrase**: for 2–5 word terms that are next to each other in the same order; reduces noise and produces more targeted results for multiword searches.
- **Broad**: for multiple unquoted words, B2C Commerce finds products/content with one or more terms in any order (example: “running shoes” returns results containing running and shoes in any order).  
  Warning in the unit: after a new product import, new refinement attributes can be unaccounted for in existing bucketing rules, causing a poor storefront experience — **don’t enable this setting on a production instance**.

## The six search settings (checkboxes in the walkthrough)
The unit lists these search settings under Search Preferences:
1) **Dictionary Locale Fallback**
2) **Ignore Leading Zeros** (requires **Rebuild index** to activate)
3) **Search Autocorrections**
4) **Einstein Search Recommendations** (personalized query correction; requires development work and search bar dropdown configuration)
5) **Search Redirect Keyword Rules**
6) **Include Promotion IDs in the Product Index**

## Email/notification settings (3 types)
The unit describes three notification areas where you can select Notification Email and enter recipients:
1) Notification Settings for **Unbucketed Refinement Values**
2) Notification Settings for **Search Indexer**
    - notify selected users when indexing errors exceed a threshold after indexing
3) Notification Settings for **Search Dictionary**
    - **Einstein Dictionaries**: notify selected users when new search dictionaries are available

## Step-by-step: configure search preferences (unit walkthrough)
1. Business Manager → App Launcher → **Merchant Tools | Search | Search Preferences**
2. Availability Settings → select **Show Orderable Products Only**
3. Search Settings → select the six settings listed above
4. Unbucketed Refinement Values → Notification Email + enter email address
5. Search Indexer → Notification Email + enter email address
6. Search Dictionary → Notification Email + enter email address
7. Click **Apply**

## Tiếng Việt

## Learning Objectives
- Giải thích **match type** settings.
- Mô tả **product availability** settings.
- Liệt kê 6 **search settings**.
- Liệt kê 3 **email settings**.

## Search Preferences kiểm soát gì (tổng quan)
- Search preferences quyết định search sẽ:
    - chỉ hiển thị sản phẩm orderable (lọc availability),
    - autocorrect query,
    - tích hợp Commerce Cloud Einstein,
    - áp rules cho search redirects,
    - gửi email notifications cho các sự kiện search/indexing.
- Cấu hình trong **Business Manager**.

## Product availability settings
- Mục tiêu: tránh shopper bực khi thấy sản phẩm không mua được.
- Setting chính trong walkthrough:
    - **Show Orderable Products Only**.

## Match type settings (Search Redirect Keyword Rules)
- Dùng khi bạn cấu hình keywords trong **Search Driven Redirects**.
- Mục tiêu: kiểm soát cách match keyword.
  Các setting:
- **Exact**: match đúng cụm từ.
- **Phrase**: cụm 2–5 từ đứng cạnh nhau đúng thứ tự; giảm noise, targeted hơn.
- **Broad**: nhiều từ không có dấu ngoặc kép → match một hoặc nhiều term theo mọi thứ tự (ví dụ “running shoes”).  
  Cảnh báo trong unit: sau product import, refinement attributes mới có thể không nằm trong bucketing rules → trải nghiệm kém; **không bật trên production**.

## 6 search settings (checkbox)
1) **Dictionary Locale Fallback**
2) **Ignore Leading Zeros** (cần **Rebuild index**)
3) **Search Autocorrections**
4) **Einstein Search Recommendations** (cần development + cấu hình dropdown search bar)
5) **Search Redirect Keyword Rules**
6) **Include Promotion IDs in the Product Index**

## 3 email/notification settings
1) Unbucketed Refinement Values
2) Search Indexer (indexing errors vượt threshold)
3) Search Dictionary (**Einstein Dictionaries**: có dictionaries mới)

## Các bước cấu hình (walkthrough)
1. **Merchant Tools | Search | Search Preferences**
2. Availability → **Show Orderable Products Only**
3. Search Settings → chọn 6 setting
4. Unbucketed Refinement Values → Notification Email + email
5. Search Indexer → Notification Email + email
6. Search Dictionary → Notification Email + email
7. **Apply**