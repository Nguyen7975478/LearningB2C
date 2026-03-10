# Learn About B2C Commerce Search
https://trailhead.salesforce.com/content/learn/modules/cc-digital-merchandising/digital-search

## English

### Learning Objectives
- Describe how you can increase search hits from external search engines.
- Give an example of how **search redirects** benefit shoppers.
- List what you can include in a **search index**.
- Describe how the search index is updated.
- Explain the difference between merchant-directed and shopper-directed search sorting.
- Explain what **Einstein search dictionaries** can do.

### Search features covered (unit scope)
- **Type-Ahead Search**
- **Search Redirects**
- **Search Index** (searchable attributes + configuration)
- **SEO** (for external search engine traffic)
- Sorting and refinement after search
- **Einstein search dictionaries** (conceptually)

### Type-Ahead Search
- Search starts processing after shoppers type a few characters.
- While typing, B2C Commerce checks spelling and word completion and shows suggestions (such as a category).

### Search Redirects (example and purpose)
- A search redirect maps a predefined term (example: “wedding dress”) to a specific page/URL instead of a generic results page.
- Benefits: tailored content, registry/guide info, pricing; improves the buying experience and likelihood of purchase.

### Search Index + searchable attributes
- Query text is passed to the **search index**.
- Data isn’t searchable by default; merchants configure what’s searchable in Business Manager.
- Examples: brand, ID, name, description.
- Tradeoff: too much searchable data increases index size and reduces speed.

### What you can include in the search index (core concepts shown)
- The index supports multiple concerns: spelling, content, synonyms, suggestions, product availability.
- Configurable dictionary-like concepts called out:
  - **Synonyms**
  - **Hypernyms**
  - **Hyponyms**
- Examples:
  - Hypernym/hyponym: “top” → “tunic/shirt/blouse” (blouse is a hyponym of top).
  - Synonyms: bag/purse/pocketbook/tote (including plural forms).

### SEO (increase external search hits)
- SEO capabilities are described as relevant when traffic comes from search engines like Google.
- Examples called out:
  - Avoid dead ends (avoid 404s) by providing alternative paths.
  - Preserve rankings using canonical/preferred URL signals in page headers for duplicate-like URLs.

### Sorting and refinement after search
- Refinement example path: shirts → brand → size → color.
- Sorting supports both:
  - Shopper-directed sorting (storefront dropdown, e.g., price low-to-high).
  - Merchant-directed sorting (rules applied behind the scenes, e.g., show new merchandise first).
- Sorting types referenced:
  - Default sorting for keyword searches
  - Category sorting (can vary per site when categories are shared)
  - Dynamic attributes (e.g., profit margin, availability)

## Tiếng Việt

### Learning Objectives
- Mô tả cách tăng search hits từ external search engines.
- Nêu ví dụ **search redirects** giúp shoppers.
- Liệt kê những thứ có thể đưa vào **search index**.
- Mô tả search index update thế nào.
- Giải thích merchant-directed vs shopper-directed sorting.
- Giải thích **Einstein search dictionaries** làm được gì.

### Search features trong unit
- **Type-Ahead Search**
- **Search Redirects**
- **Search Index** (searchable attributes + config)
- **SEO**
- Sorting/refinement sau search
- **Einstein search dictionaries**

### Type-Ahead Search
- Search bắt đầu xử lý khi shopper gõ vài ký tự.
- Hệ thống kiểm tra spelling, word completion và đưa suggestions (ví dụ category).

### Search Redirects
- Map term định nghĩa trước (ví dụ “wedding dress”) sang trang/URL cụ thể thay vì results page.
- Lợi ích: nội dung tailored, registry/guide, pricing; tăng trải nghiệm mua và khả năng mua.

### Search Index + searchable attributes
- Query được đưa vào **search index**.
- Data không searchable mặc định; merchant phải cấu hình trong Business Manager.
- Ví dụ: brand, ID, name, description.
- Tradeoff: searchable quá nhiều làm index lớn và search chậm.

### Search index gồm gì (core concepts)
- Index hỗ trợ spelling, content, synonyms, suggestions, product availability.
- Các concept cấu hình:
  - **Synonyms**
  - **Hypernyms**
  - **Hyponyms**
- Ví dụ:
  - “top” → “tunic/shirt/blouse”.
  - Synonyms bag/purse/pocketbook/tote (kể cả plural).

### SEO
- Dùng khi traffic đến từ Google/external search engines.
- Ví dụ:
  - Tránh 404 bằng alternative paths.
  - Dùng canonical/preferred URL trong headers để giữ rankings khi URLs tương tự.

### Sorting/refinement sau search
- Refine: shirts → brand → size → color.
- Sorting:
  - Shopper-directed sorting: dropdown (price low-to-high).
  - Merchant-directed sorting: rule “behind the scenes” (đưa hàng mới lên đầu).
- Các kiểu sorting:
  - Default sorting for keyword searches
  - Category sorting (khác theo site khi categories shared)
  - Dynamic attributes (profit margin, availability)