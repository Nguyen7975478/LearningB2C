# Generate a robots.txt File
https://trailhead.salesforce.com/content/learn/modules/b2c-xml-sitemaps/b2c-xml-sitemaps-generate-robots

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe an external search engine’s primary functions.
- List what’s contained in a robots.txt file.
- Describe two ways to generate a robots.txt file.
- Explain how to verify a robots.txt file.
- Describe how to configure caching when you generate a robots.txt file.

## External search engines: primary functions (3)
External search engines primarily:
1) **Crawl**: search the internet for content and inspect each URL’s code/content.
2) **Index**: store and organize content for retrieval.
3) **Rank**: order results by relevance to search queries.

## robots.txt (what it is + how crawlers use it)
- A crawler looks for the `/robots.txt` URI on your site (host + port defines the “site”).
- There can be only **one** `/robots.txt` file per site.
- `robots.txt` controls what crawlers can access/index using directives such as `Disallow`.
  Business reasons:
- limit indexing to important content
- prevent unnecessary crawler requests from overloading the site

## What’s contained in a robots.txt file (core directives)
Basic structure:
- `User-agent: <robot name or *>`
- `Disallow: <path prefix>`
  The unit also mentions examples that can include:
- bot-specific blocks (for example Googlebot)
- `Crawl-delay`
- multiple `Disallow` rules

### Disallow prefix behavior (important detail)
- `Disallow: /help` blocks both:
    - `/help.html`
    - `/help/index.html`
- `Disallow: /help/` blocks:
    - `/help/index.html`
      but allows:
    - `/help.html`

## Block everything example (prevent crawling)
To prevent indexing of all pages:
- `User-agent: *`
- `Disallow: /`

## Storefront Password Protection (staging/dev safeguard)
- **Storefront Password Protection** limits access to project team members.
- It also prevents crawlers from indexing:
    - dynamic content (pages)
    - static content (images)

## Two ways to generate robots.txt (unit list)
### 1) Create with a text editor (and serve via Business Manager)
- Use a plain text editor: Notepad, TextEdit, vi, emacs.
- Don’t use word processors (they can add unexpected characters like curly quotes).
- Save as UTF‑8 if prompted.

### 2) Upload as a file in a storefront cartridge
- If you generate it externally, upload to:
    - `cartridge/static/default/robots.txt`
- Because it’s cartridge-specific (not site-specific), replicate it between instances via **code replication**.

## Prerequisite: hostname aliases
- For robots.txt to be used by B2C Commerce, Brandon must first set up **hostname aliases**.

## Caching behavior (how to ensure changes take effect)
- When caching is enabled on an instance:
    - you must invalidate the **static content cache** for a new robots.txt to be generated or served.
- When caching is disabled on a staging instance:
    - B2C Commerce detects changes immediately.
- In Business Manager, robots.txt is stored as a **site preference** and can be replicated from one instance to another.

## Verify robots.txt (step-by-step)
To verify it’s served:
1) Invalidate static content page cache (if needed).
2) In a browser, open:
    - `http://<hostname>/robots.txt`
3) If you see a blank page, the file isn’t there (not generated/served).

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả các chức năng chính của external search engines.
- Liệt kê robots.txt chứa gì.
- Mô tả 2 cách tạo robots.txt.
- Giải thích cách verify robots.txt.
- Mô tả caching khi generate robots.txt.

## External search engines: 3 chức năng chính
1) **Crawl**: thu thập nội dung và đọc code/content theo URL.
2) **Index**: lưu và tổ chức nội dung để trả kết quả.
3) **Rank**: xếp hạng theo relevance.

## robots.txt là gì và crawler dùng thế nào
- Crawler tìm `/robots.txt` theo host+port.
- Mỗi site chỉ có **một** `/robots.txt`.
- `robots.txt` điều khiển crawler bằng directives như `Disallow`.
  Mục tiêu:
- chỉ index nội dung quan trọng
- tránh crawler requests không cần thiết gây tải

## robots.txt chứa gì (core directives)
- `User-agent:` và `Disallow:`
  Unit cũng nhắc ví dụ có thể có:
- block theo bot (Googlebot)
- `Crawl-delay`
- nhiều `Disallow`

### Hành vi prefix của Disallow
- `Disallow: /help` chặn `/help.html` và `/help/index.html`
- `Disallow: /help/` chặn `/help/index.html` nhưng cho phép `/help.html`

## Ví dụ chặn toàn bộ site
- `User-agent: *`
- `Disallow: /`

## Storefront Password Protection
- Giới hạn access cho team và ngăn crawlers index:
    - dynamic pages
    - static images

## 2 cách tạo robots.txt
### 1) Text editor + Business Manager
- Dùng Notepad/TextEdit/vi/emacs.
- Không dùng word processor (dễ thêm ký tự lạ).
- Lưu UTF‑8 nếu được hỏi.

### 2) Upload vào storefront cartridge
- Upload vào `cartridge/static/default/robots.txt`
- Replicate qua instances bằng **code replication**.

## Prerequisite: hostname aliases
- Muốn robots.txt dùng được trong B2C Commerce, cần setup **hostname aliases** trước.

## Caching (để thay đổi có hiệu lực)
- Cache enabled: phải invalidate **static content cache** để robots.txt mới được generate/serve.
- Cache disabled (staging): thay đổi được detect ngay.
- Business Manager lưu robots.txt như **site preference** và replicate được.

## Verify robots.txt (các bước)
1) Invalidate static content page cache (nếu cần)
2) Mở `http://<hostname>/robots.txt`
3) Trang trắng → file chưa có/không được serve