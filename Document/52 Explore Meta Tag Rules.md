# Explore Meta Tag Rules
https://trailhead.salesforce.com/content/learn/modules/b2c-seo-meta-tags/b2c-seo-meta-tag-explore-rules

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain how meta tags can help with SEO.
- Explain the difference between meta title and meta description tags.
- List four types of meta tags that can help with SEO.
- Explain rule inheritance.

## Why meta tags matter (SEO impact)
- **Meta tags** are small snippets of text that describe a page’s content.
- They’re part of the HTML code (not visible on the page itself) and help search engines:
  - rank pages
  - display snippets in search results (SERP)
- Brandon’s goal: optimize meta tags so Cloud Kicks pages stand out and attract clicks.

## What’s in a meta tag (where it goes + examples)
- Meta tags go in the `<head>` section of an HTML document.
  Examples shown:
- `<meta name="title" content="Cloud Kicks specializes in high-end custom sneakers and apparel”>`
- `<meta name="description" content="Mid-top mixed leather sneakers for the empowered, in wide-width, too.">`

## Meta tag types that help SEO (what the unit emphasizes)
The unit lists multiple SEO-related tags and explicitly focuses on the first three (while noting others are important):

### 1) Title
- Describes the content and shows in search results.
- Can be extracted as anchor text and as a title for social shares.
  Best-practice tips given:
- Clear and descriptive, **<= 55 characters**
- Include a keyword only if it adds value (avoid vague keywords)
- Must make sense to both visitors and search engines

### 2) Description
- Appears as a snippet under the title in SERP.
- Doesn’t necessarily affect ranking, but strongly affects click-through rate (CTR).
  Tips given:
- Accurate summary of page content
- Keep **150–165 characters**
- Appealing, concise, relevant

### 3) Robots
- Controls how crawlers index an individual page.
- Difference from robots.txt:
  - `robots.txt` can block crawling an entire site/section
  - robots meta tag controls page-level crawling/indexing
    Examples shown:
- `<meta name="robots" content="noindex" />`
- `noindex, nofollow` can block indexing and also prevent following links on that page
- Note: for product review links, Google requires `rel="nofollow"` on links; robots meta tag can apply nofollow to all links on a page.

### Other SEO-related tags mentioned (not the primary focus in this unit)
- **Alternative text (alt)** tag (images)
- **Canonical** tag (duplicate / near-duplicate pages)
- **hreflang** tag (multi-language / multi-country pages)
- **Headings** (h1/h2/h3) (structure for UX + search engines)

## Rule inheritance (concept introduced here, expanded later)
- Meta tags are managed through rules and can be inherited to reduce repetitive configuration (the unit introduces the concept that rule inheritance matters for large storefront structures).

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích meta tags giúp SEO như thế nào.
- Phân biệt meta title và meta description.
- Liệt kê 4 loại meta tags hỗ trợ SEO.
- Giải thích rule inheritance.

## Vì sao meta tags quan trọng (tác động SEO)
- **Meta tags** là các “snippets” mô tả nội dung trang.
- Nằm trong HTML code (không hiển thị trực tiếp) và giúp search engines:
  - xếp hạng trang
  - hiển thị snippets trên SERP
- Mục tiêu của Brandon: tối ưu meta tags để trang Cloud Kicks nổi bật và tăng lượt click.

## Meta tag nằm ở đâu + ví dụ
- Meta tags đặt trong `<head>`.
  Ví dụ:
- `<meta name="title" content="...">`
- `<meta name="description" content="...">`

## Các meta tags hỗ trợ SEO (những mục unit tập trung)
Unit liệt kê nhiều tags và nói rõ tập trung 3 tags đầu:

### 1) Title
- Mô tả nội dung, hiển thị trên search results.
- Có thể bị trích làm anchor text và title khi share mạng xã hội.
  Tips:
- Rõ ràng, **<= 55 ký tự**
- Có keyword nếu thực sự có giá trị (tránh keyword mơ hồ)
- Có nghĩa với cả visitors và search engines

### 2) Description
- Snippet dưới title trên SERP.
- Không nhất thiết đổi ranking nhưng ảnh hưởng CTR mạnh.
  Tips:
- Accurate theo nội dung trang
- **150–165 ký tự**
- hấp dẫn, concise, relevant

### 3) Robots
- Điều khiển crawler index trang cụ thể.
- Khác robots.txt:
  - `robots.txt` chặn cả site/section
  - robots meta tag điều khiển theo page
    Ví dụ:
- `<meta name="robots" content="noindex" />`
- `noindex, nofollow` chặn index và không follow links
- Ghi chú: link product review cần `rel="nofollow"`; robots tag có thể set nofollow cho toàn trang.

### Các tags khác được nhắc tới (không phải trọng tâm chính của unit)
- **alt**, **canonical**, **hreflang**, **headings (h1/h2/h3)**

## Rule inheritance
- Meta tags quản lý bằng rules và có thể kế thừa (inherit) để giảm cấu hình lặp (unit giới thiệu khái niệm, phần sau sẽ làm rõ hơn).