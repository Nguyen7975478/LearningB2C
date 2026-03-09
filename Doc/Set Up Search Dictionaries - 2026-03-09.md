# Set Up Search Dictionaries

## Metadata

| Field        | Value                                                                                                                                                 |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| Source URL   | https://trailhead.salesforce.com/content/learn/modules/cc-einstein-smarter-search/cc-einstein-search-dictionaries?trail_id=set-up-merchandising-for-your-storefront |
| Created Date | 2026-03-09                                                                                                                                            |

---

# 🇬🇧 English (EN)

## Learning Objectives

After completing this unit, you'll be able to:

- List three standard search features in Agentforce Commerce for B2C.
- List the five standard search dictionaries.
- Describe three ways Agentforce Commerce for B2C can sort search results.
- List the three general steps required to configure Search Dictionaries.

---

## Key Concepts: Search Dictionaries

Agentforce Commerce for B2C uses search dictionaries to improve how shoppers find products. The five main dictionary types are:

| Dictionary Type   | Description                                                                                                               |
|-------------------|---------------------------------------------------------------------------------------------------------------------------|
| **Synonyms**      | Words with the same meaning (e.g., "sneaker" = "trainer").                                                                |
| **Hypernyms**     | A broad category term. Searching "top" also returns results for "shirt", "blouse", "tunic".                               |
| **Hyponyms**      | A specific term within a category. Searching "blouse" only returns results for "blouse", not other tops.                  |
| **Common Phrases**| Word combinations that must be found together in search.                                                                   |
| **Compound Words**| Words split into separate terms by a configured rule (e.g., "foot-*" splits "footstool" into "foot" + "stool").           |
| **Stop Words**    | Words the engine ignores (e.g., "an", "the") to keep the index compact and results faster.                                |

---

## Standard B2C Commerce vs. Commerce Cloud Einstein

| Feature                | Standard Agentforce Commerce for B2C                                               | Commerce Cloud Einstein                                                                                         |
|------------------------|-------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| **Search Dictionaries**| Manually created by the merchant from site-specific data.                          | Automatically built from live search data across many merchants; detects term relationships using AI.           |
| **Search Recommendations** | Basic search-as-you-type with spell correction and term completion.           | Algorithms identify recent, popular, and trending phrases; personalized auto-correction and term completion.    |
| **Predictive Sort**    | Configured sorting rules: keyword search, category navigation, dynamic attributes.  | Learns each shopper's behavior and affinity; cookie-based personalization; improves over time with more data.   |

---

## Configuring Search Dictionaries in Business Manager

### Step 1 – Accept the Einstein Data Privacy (Opt-In)

> Must be done by an **administrator** on the **staging instance**.

1. In Business Manager → **App Launcher** → **Administration | Global Preferences | Einstein Search Dictionaries Opt-In**.
2. Select **"I accept these terms and conditions"**.
3. Click **Save**.

### Step 2 – Set Notification Settings

1. **App Launcher** → **Merchant Tools | Site | Site Preferences | Search Preferences**.
2. Select **Notification Settings for Search Dictionary**.
3. Add email addresses of people who will manage synonyms.
4. Click **Apply**.

### Step 3 – Dictionary Locale Fallback *(multi-locale sites)*

1. **App Launcher** → **Merchant Tools | Site | Site Preferences | Search Preferences**.
2. Select **Search Settings**.
3. Enable **Dictionary Locale Fallback** so language-level settings propagate to regional locales.

### Step 4 – Rebuild the Search Index

1. **App Launcher** → **Merchant Tools | Site | Search | Search Indexes**.
2. Check the relevant index(es).
3. Click **Rebuild**.

---

## Using Search Dictionaries

### Create a New Dictionary Entry

1. **App Launcher** → **Merchant Tools | Site | Search Dictionaries**.
2. Click or select a dictionary type (e.g., **Compound Words**).
3. Click **New**.
4. Select the **locale**.
5. Enter the value (e.g., `high-top`).
6. Click **Save**.

### Search and Filter Entries

1. Click **Search Dictionary** to search across all dictionaries.
2. Filter by **type** and/or **locale** as needed.
3. To add a filter: click the **filter icon** → **Add Filter** → select field and value → click **Apply**.
4. To edit existing filters: click **Edit List Filters**.

---

## Stemming Exceptions

**Concept:** Stemming exceptions let you define custom word stems, overriding the default stemming algorithm. This ensures specific words (e.g., "leggings") are not incorrectly reduced to a different stem.

### Steps to Create a Stemming Exception

1. Open **Business Manager**.
2. Go to **Merchant Tools | Search | Search Dictionaries**.
3. Click **Stemming Exceptions**.
4. Click **New**.
5. Enter the word (e.g., `leggings`) as both the **exception** and the **stem**.
6. Click **Save**.

> To push changes live, replicate from development → staging (for testing) → production.

---

## Next Steps

In the next unit of this module, the merchant implements **Einstein Search Recommendations** to further improve the shopper experience on the Agentforce Commerce for B2C storefront.

---

---

# 🇻🇳 Tiếng Việt (VI)

## Mục Tiêu Học Tập

Sau khi hoàn thành bài học này, bạn có thể:

- Liệt kê 3 tính năng tìm kiếm tiêu chuẩn trong Agentforce Commerce for B2C.
- Liệt kê 5 loại từ điển tìm kiếm tiêu chuẩn.
- Mô tả 3 cách sắp xếp kết quả tìm kiếm của hệ thống.
- Nêu 3 bước chính để cấu hình Search Dictionaries.

---

## Các Khái Niệm Chính: Search Dictionaries

Agentforce Commerce for B2C sử dụng từ điển tìm kiếm để cải thiện trải nghiệm tìm kiếm của khách hàng. Có 5 loại từ điển chính:

| Loại Từ Điển       | Mô Tả                                                                                                                               |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| **Synonyms**       | Các từ đồng nghĩa (ví dụ: "sneaker" = "trainer").                                                                                  |
| **Hypernyms**      | Từ chỉ nhóm sản phẩm. Khi tìm "top", hệ thống trả về cả "shirt", "blouse", "tunic".                                               |
| **Hyponyms**       | Từ chỉ một mặt hàng cụ thể trong nhóm. Tìm "blouse" chỉ trả về kết quả chứa "blouse".                                             |
| **Common Phrases** | Cụm từ cần được tìm kiếm kết hợp với nhau.                                                                                         |
| **Compound Words** | Từ ghép được tách ra theo quy tắc cấu hình (ví dụ: "foot-*" tách "footstool" thành "foot" + "stool").                             |
| **Stop Words**     | Các từ bị bỏ qua trong quá trình lập chỉ mục (ví dụ: "an", "the") giúp chỉ mục gọn hơn và tìm kiếm nhanh hơn.                   |

---

## So Sánh B2C Commerce Tiêu Chuẩn vs. Commerce Cloud Einstein

| Tính Năng              | Agentforce Commerce for B2C Tiêu Chuẩn                                             | Commerce Cloud Einstein                                                                                                 |
|------------------------|-------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| **Search Dictionaries**| Tạo thủ công bởi merchant dựa trên dữ liệu của site.                               | Tự động xây dựng từ dữ liệu tìm kiếm thực tế của nhiều merchant; AI phát hiện mối quan hệ giữa các thuật ngữ.          |
| **Search Recommendations** | Gợi ý khi nhập từ cơ bản: sửa lỗi chính tả và hoàn thiện từ khóa.            | Thuật toán xác định cụm từ phổ biến, xu hướng, cá nhân hóa gợi ý và sửa lỗi cho từng khách hàng.                      |
| **Predictive Sort**    | Quy tắc sắp xếp cấu hình sẵn: tìm kiếm từ khóa, điều hướng danh mục, thuộc tính.  | Học hành vi và sở thích của từng khách hàng qua cookie; cải thiện cá nhân hóa kết quả theo thời gian.                  |

---

## Các Bước Cấu Hình Search Dictionaries Trong Business Manager

### Bước 1 – Chấp Nhận Thỏa Thuận Quyền Riêng Tư Einstein (Opt-In)

> Phải được thực hiện bởi **quản trị viên** trên **môi trường staging**.

1. Trong Business Manager → **App Launcher** → **Administration | Global Preferences | Einstein Search Dictionaries Opt-In**.
2. Chọn **"I accept these terms and conditions"**.
3. Nhấp **Save**.

### Bước 2 – Cài Đặt Thông Báo (Notification Settings)

1. **App Launcher** → **Merchant Tools | Site | Site Preferences | Search Preferences**.
2. Chọn **Notification Settings for Search Dictionary**.
3. Thêm địa chỉ email của những người quản lý từ điển đồng nghĩa.
4. Nhấp **Apply**.

### Bước 3 – Cài Đặt Dự Phòng Ngôn Ngữ *(cho site nhiều locale)*

1. **App Launcher** → **Merchant Tools | Site | Site Preferences | Search Preferences**.
2. Chọn **Search Settings**.
3. Bật **Dictionary Locale Fallback** để cài đặt ở cấp ngôn ngữ lan rộng sang các vùng khu vực.

### Bước 4 – Xây Dựng Lại Chỉ Mục Tìm Kiếm

1. **App Launcher** → **Merchant Tools | Site | Search | Search Indexes**.
2. Chọn (tick) các chỉ mục liên quan.
3. Nhấp **Rebuild**.

---

## Cách Sử Dụng Search Dictionaries

### Tạo Mục Từ Điển Mới

1. **App Launcher** → **Merchant Tools | Site | Search Dictionaries**.
2. Chọn loại từ điển (ví dụ: **Compound Words**).
3. Nhấp **New**.
4. Chọn **locale**.
5. Nhập giá trị (ví dụ: `high-top`).
6. Nhấp **Save**.

### Tìm Kiếm và Lọc Mục Từ Điển

1. Nhấp **Search Dictionary** để tìm kiếm trên tất cả từ điển.
2. Có thể lọc theo **loại** và/hoặc **locale**.
3. Để thêm bộ lọc: nhấp biểu tượng **filter** → **Add Filter** → chọn trường và giá trị → nhấp **Apply**.
4. Để chỉnh sửa bộ lọc hiện có: nhấp **Edit List Filters**.

---

## Stemming Exceptions (Ngoại Lệ Gốc Từ)

**Khái Niệm:** Stemming exceptions cho phép bạn định nghĩa gốc từ tùy chỉnh, ghi đè thuật toán stemming mặc định. Điều này đảm bảo các từ cụ thể (ví dụ: "leggings") không bị rút gọn sai sang một gốc từ khác.

### Các Bước Tạo Stemming Exception Mới

1. Mở **Business Manager**.
2. Vào **Merchant Tools | Search | Search Dictionaries**.
3. Nhấp **Stemming Exceptions**.
4. Nhấp **New**.
5. Nhập từ (ví dụ: `leggings`) vào cả trường **exception** và **stem**.
6. Nhấp **Save**.

> Để áp dụng thay đổi lên production: replicate từ development → staging (kiểm thử) → production.

---

## Các Bước Tiếp Theo

Trong bài tiếp theo của module này, merchant sẽ triển khai **Einstein Search Recommendations** để tiếp tục nâng cao trải nghiệm tìm kiếm của khách hàng trên storefront Agentforce Commerce for B2C.
