# Configure Storefront Search Redirects
https://trailhead.salesforce.com/content/learn/modules/b2c-storefront-search/b2c-configure-storefront-search-redirects

## English

## Learning Objectives
- Explain how guided search gives you control over what the shopper sees.
- Explain how search redirects work behind the scenes.
- Explain how matching works for search redirects.
- Describe how the locale fallback mechanism works for search redirects.

## What search redirects are (guided search)
- **Search redirects** give merchandisers guided control over the shopper experience. Instead of always showing a generic search results page, you can send shoppers to a specific page or URL.
- Example in the unit: if shoppers search for `sneakers`, the redirect can return a dedicated page (Special High-End Jazzy Sneaker page) that better matches intent and improves conversion.
- A redirect can be triggered by **multiple, comma-separated keywords** (more control, fewer missed matches).

## How search redirects work behind the scenes (SearchRedirectURL pipelet + ISML)
- B2C Commerce integrates redirects into the search flow using the `SearchRedirectURL` **pipelet** (a code snippet performing a business function).
- Developer places `SearchRedirectURL` **before** the **Search** pipelet so redirect evaluation happens first:
    - If shopper input matches a redirect keyword, standard search is bypassed.
- When a match occurs:
    - `SearchRedirectURL` calculates the fully qualified target URL based on the redirect action.
    - An **ISML template** uses that URL to issue the HTTP redirect to the shopper’s browser.
- For URL redirects, you can configure destination protocol (HTTP/HTTPS).

## Matching types (how keywords trigger redirects)
The unit explains 4 matching types (available when Search Redirect Keyword Rules are enabled in Search Preferences):

### 1) Exact Match (brackets)
- Syntax: `[mens shoes]`
- Triggers only when shopper enters the exact phrase in the same order, with no extra words and no variations.
- Example: `mens shoes` triggers; `mens shoe` does not.

### 2) Phrase Match (quotation marks)
- Syntax: `"mens shoes"`
- Triggers when shopper enters the phrase in that exact word order.
- Can trigger even if shopper enters additional text, as long as the exact phrase is included.

### 3) Broad Match (no quotes)
- Syntax: `mens shoes`
- Triggers when shopper enters text containing the words in any order.
- Triggers for singular/plural forms based on **stemming** for the language.
- Does not consider synonyms or other variations.

### 4) Negative Match (hyphen)
- Syntax: `mens shoes, -used, -"running shoes"`
- A redirect does not trigger for searches containing negative terms.
- Negative keywords must be used with at least one positive keyword.
- A redirect containing only negative keywords will never trigger.

## Configure a search redirect in Business Manager (step-by-step)
1. Business Manager → App Launcher → **Merchant Tools | Search | Search Driven Redirects**
2. Click **New**
3. Default language is selected (or select a language and click **Apply**)
4. Enter keywords (comma-separated), example: `womens shoes, -used`
5. Select **Online** (to enable for storefront)
6. Select **Secure** to use https (otherwise http; if **Enforce HTTPS** is enabled, HTTPS is used anyway)
7. Choose redirect action, example: **Show Category Page**
8. Select **Category ID**, example: `womens-shoes`
9. Click **Apply**

## Localization (keywords per locale + fallback behavior)
- You can define different keywords **by locale** for a redirect.
- If a locale does not have keywords defined, B2C Commerce uses keywords via the **fallback mechanism**.
- Important constraint called out:
    - Locale fallback works **from country locale to language locale**, such as `en_GB` → `en`.
    - **Search Dictionaries** does **not** support fallback from language to the default locale.
- Examples in the unit:
    - If shopper uses `de_AT`, B2C Commerce uses `de` keywords (because `de_AT` defaults to `de`).
    - If shopper uses `es_ES`, B2C Commerce uses the `es_ES` keywords (no fallback needed in that case).

## Tiếng Việt

## Learning Objectives
- Giải thích guided search giúp merchandiser kiểm soát shopper thấy gì.
- Giải thích search redirects hoạt động behind the scenes.
- Giải thích matching hoạt động thế nào cho search redirects.
- Mô tả locale fallback mechanism cho search redirects.

## Search redirects là gì (guided search)
- **Search redirects** cho phép merchandiser điều hướng shoppers tới một trang/URL cụ thể thay vì luôn hiển thị trang search results chung.
- Ví dụ unit: search `sneakers` có thể đưa tới trang “Special High-End Jazzy Sneaker” để tăng đúng intent và tăng khả năng mua.
- Một redirect có thể được kích hoạt bởi **nhiều keywords**, ngăn cách bằng dấu phẩy (**comma-separated keywords**).

## Behind the scenes (SearchRedirectURL pipelet + ISML)
- B2C Commerce dùng `SearchRedirectURL` **pipelet** để đánh giá redirect trong search flow.
- Developer đặt `SearchRedirectURL` **trước** **Search** pipelet:
    - Nếu match redirect keyword thì bypass standard search.
- Khi match:
    - `SearchRedirectURL` tính fully qualified target URL theo redirect action.
    - **ISML template** dùng URL đó để thực hiện HTTP redirect về browser.
- Redirect URL có thể cấu hình protocol (HTTP/HTTPS).

## Matching types (cách keywords kích hoạt redirect)
Unit mô tả 4 match types (khi bật Search Redirect Keyword Rules trong Search Preferences):

### 1) Exact Match (brackets)
- Cú pháp: `[mens shoes]`
- Chỉ trigger khi shopper gõ đúng cụm từ, đúng thứ tự, không thêm từ và không biến thể.
- Ví dụ: `mens shoes` trigger; `mens shoe` không trigger.

### 2) Phrase Match (quotation marks)
- Cú pháp: `"mens shoes"`
- Trigger khi có cụm từ đúng thứ tự từ.
- Có thể trigger dù shopper gõ thêm từ khác, miễn có chứa đúng phrase.

### 3) Broad Match (không có quotes)
- Cú pháp: `mens shoes`
- Trigger khi shopper nhập có chứa các từ theo bất kỳ thứ tự.
- Trigger cả singular/plural dựa trên **stemming** theo ngôn ngữ.
- Không xét synonyms hay biến thể khác.

### 4) Negative Match (hyphen)
- Cú pháp: `mens shoes, -used, -"running shoes"`
- Redirect không trigger nếu search có chứa negative terms.
- Negative keywords phải đi kèm ít nhất một positive keyword.
- Redirect chỉ có negative keywords sẽ không bao giờ trigger.

## Cấu hình redirect trong Business Manager (step-by-step)
1. App Launcher → **Merchant Tools | Search | Search Driven Redirects**
2. **New**
3. Chọn language (mặc định) và **Apply** nếu đổi
4. Nhập keywords (comma-separated), ví dụ: `womens shoes, -used`
5. Chọn **Online**
6. Chọn **Secure** để dùng https (nếu bật **Enforce HTTPS** thì luôn HTTPS)
7. Chọn action, ví dụ **Show Category Page**
8. Chọn **Category ID**, ví dụ `womens-shoes`
9. **Apply**

## Localization (keywords theo locale + fallback)
- Có thể đặt keywords theo từng **locale**.
- Nếu locale không có keywords, hệ thống dùng **fallback mechanism**.
- Ràng buộc quan trọng:
    - Fallback chỉ chạy **từ country locale về language locale**, ví dụ `en_GB` → `en`.
    - **Search Dictionaries** không hỗ trợ fallback từ language về default locale.
- Ví dụ unit:
    - `de_AT` dùng keywords của `de` (vì `de_AT` default về `de`).
    - `es_ES` dùng keywords `es_ES` (không fallback).