# Integrate and Check Your Meta Tags
https://trailhead.salesforce.com/content/learn/modules/b2c-seo-meta-tags/b2c-seo-meta-tag-integrate-check

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List the API classes you can use to generate meta tags.
- Describe where on a page you add meta tags.
- List the property and container you use to handle meta tags.
- List three things you should do to check your final meta tags.

## Why integrate meta tags in code (automation)
- Brandon wants to automate meta tag generation by adding it to storefront application code.
- Automation reduces manual errors and provides consistent metadata generation as storefront data changes.
- Workflow: developer makes changes in a sandbox, uploads code to staging, then replicates to development and production.

## B2C Commerce APIs used for meta tags (scope mapping)
The unit provides this mapping:

Use this class… | For a…
---|---
`dw.system.Site` | Home page
`dw.catalog.Product` | Product detail page
`dw.catalog.ProductSearchModel` | Product list page (based on search results)
`dw.content.Content` | Content detail page
`dw.content.ContentSearchModel` | Content list page (based on search results)

## Where meta tags go (HTML head)
- Meta tags are populated within the HTML `<head>` section.

## Property + container used to handle meta tags
- Use the `pageMetaTags` property on the page context object to populate meta tags.
- B2C Commerce exposes the results through the `dw.web.PageMetaData` container during page generation.
- The platform generates meta tag content from meta tag rules using the current scope context or inherited parent context.

## Reference implementation points (SFRA)
- Vijay reviews SFRA base cartridge patterns:
    - Page.js controller
    - `htmlHead.isml` (common/layout) template
      This provides the standard place to populate and render meta tags.

## Example controller code (what it does)
- The controller checks the class of an object and, if it’s one of the supported page contexts (Site, Product, ProductSearchModel, Content, ContentSearchModel), it:
    - gets `request.pageMetaData`
    - calls `pageMetaData.addPageMetaTags(object.pageMetaTags)`

## Example template rendering pattern (loop)
- In ISML, iterate `pdict.CurrentPageMetaData.getPageMetaTags()` and print:
    - `<title>` when tag is a title
    - `<meta name="...">` when tag uses `name`
    - `<meta property="...">` when tag uses `property`

## Check and fallback code (defensive SEO)
- Template check example:
    - If description is not set (`!isPageMetaTagSet('description')`), print a fallback meta description:
        - `<meta name="description" content="Add your fallback description here!">`

## Check your final meta tags (quality checklist)
The unit recommends reviewing:
- Ensure all pages and content have title tags and meta descriptions.
- Pay attention to headings (h1/h2/h3) structure.
- Ensure all images have alt text.
- Use robots meta tags to guide search engines.
- Find duplicates and use canonical tags to avoid cannibalizing your own SEO with duplicate/similar pages.
- Create an operational checklist: when new content is created, add meta tags as part of the routine.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê API classes dùng để generate meta tags.
- Mô tả meta tags được add ở đâu trên page.
- Liệt kê property và container dùng để xử lý meta tags.
- Liệt kê 3 việc cần làm để kiểm tra meta tags cuối cùng.

## Vì sao cần integrate meta tags bằng code (automation)
- Brandon muốn tự động hóa meta tag generation bằng cách đưa vào storefront application code.
- Automation giảm lỗi thủ công và tạo metadata nhất quán khi storefront data thay đổi.
- Workflow: dev làm ở sandbox → upload code lên staging → replicate sang development và production.

## B2C Commerce APIs dùng cho meta tags (mapping theo page type)
Use this class… | For a…
---|---
`dw.system.Site` | Home page
`dw.catalog.Product` | Product detail page
`dw.catalog.ProductSearchModel` | Product list page
`dw.content.Content` | Content detail page
`dw.content.ContentSearchModel` | Content list page

## Meta tags đặt ở đâu
- Meta tags được populate trong HTML `<head>`.

## Property + container xử lý meta tags
- Dùng property `pageMetaTags` trên object theo scope.
- Platform đưa kết quả qua container `dw.web.PageMetaData` trong quá trình generate page.
- Meta tag content được tạo theo rules, lấy từ current scope hoặc inherited parent context.

## Điểm tham chiếu SFRA
- Vijay xem SFRA base cartridge:
    - Page.js controller
    - `htmlHead.isml` (common/layout)
      Đây là nơi thường xử lý/render meta tags.

## Controller code (ý nghĩa)
- Check object.class thuộc Site/Product/ProductSearchModel/Content/ContentSearchModel
- Lấy `request.pageMetaData`
- `addPageMetaTags(object.pageMetaTags)`

## ISML template render (loop)
- Loop `pdict.CurrentPageMetaData.getPageMetaTags()` để in:
    - `<title>` nếu tag là title
    - `<meta name="...">` nếu dùng name
    - `<meta property="...">` nếu dùng property

## Check + fallback code
- Nếu chưa set description (`!isPageMetaTagSet('description')`) thì in fallback meta description.

## Checklist kiểm tra meta tags
- Đảm bảo mọi pages/content có title + meta description.
- Kiểm tra heading structure (h1/h2/h3).
- Ảnh phải có alt text.
- Dùng robots meta tags đúng.
- Tìm duplicate pages và dùng canonical tags.
- Lập checklist vận hành: tạo content mới thì thêm meta tags vào routine.