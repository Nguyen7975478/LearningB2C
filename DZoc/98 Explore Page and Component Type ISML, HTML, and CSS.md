# Explore Page and Component Type ISML, HTML, and CSS
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Explain what a page type’s render function does.
- List four Page Designer CSS development standards.
- Explain how you can vary a component’s style based on the region it’s in. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

---

## Introduction (visual-oriented code)
- ISML templates render HTML in the browser; CSS defines styling.
- Script files kick off and facilitate this chain of events. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

---

## ISML and HTML
### What the render function does
- A page type’s render function creates the page’s HTML markup.
- Typically it calls an ISML template that uses `PageRenderHelper.getRegionModelRegistry()` to render each region of the page. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

### storePage.isml example (how regions render)
The unit shows an ISML example where `storePage.isml` renders regions `main` and `legalnotice`, and adds a CSS file via `assets.addCss(...)`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

Key excerpt (structure shown):
- `isdecorate template="common/layout/pdStorePage"`
- `assets.addCss('/css/experience/storePage.css')`
- `pdict.regions.main...render()`
- `pdict.regions.legalnotice...render()` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

### Component rendering chain (mainBanner.isml example)
- Each `PageRenderHelper.getRegionModelRegistry()` finds assigned + visible components in each region and calls each component’s render function.
- That render function calls the component’s ISML template (example shown for `mainBanner.isml`), including:
    - adding a component CSS file via assets
    - rendering responsive images via `<picture>` sources
    - using localized strings via `Resource.msg(...)` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

### Wrapper settings APIs
- Page Designer uses:
    - `dw.experience.RegionRenderSettings`
    - `dw.experience.ComponentRenderSettings`
      to create the HTML wrapper element and wrapper attributes for region/component output. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

---

## CSS (development standards you can rely on)
The unit states these defaults/standards: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))
1) Default HTML wrapper for Page Designer CSS regions/components is `div`.
2) Default CSS class for regions: `experience-region experience-<region_definition_id>`.
3) Default CSS class for components: `experience-component experience-<componenttype_id>`.
4) Component type IDs can include dots (example `assets.productile`); in CSS class names, dots are replaced with hyphens (example: `experience-component experience-assets-productile`).

### Default HTML wrapper example (as shown)
For region `top_region` and 3 components (2 of `component_type_1`, 1 of `component_type_2`), the wrapper structure is shown as nested divs with those default classes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

---

## Vary the Look (style by region context)
- Vijay wants components to use different styles depending on the region they are in.
- The unit uses an example: product tile component vs carousel component (carousel is a one-region component that scrolls through other components).
- When product tile is rendered inside carousel, Vijay wants carousel-specific styling.
- The unit shows setting custom render settings for a carousel by getting the region in the render function:
    - `var carousel = component.getRegion('carousel');` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code?utm_source=openai))

---

## Next Steps
- Next unit continues beyond this visual code topic (the badge later includes custom attribute editor). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

---

## VI (A-level: chi tiết; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Giải thích render function của page type làm gì.
- Liệt kê 4 CSS development standards của Page Designer.
- Giải thích cách thay đổi style component theo region chứa nó. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

### Introduction
- ISML render HTML lên browser; CSS định nghĩa style; script files “khởi động” và điều phối chuỗi render. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

### ISML và HTML (render chain)
- Render function tạo HTML markup của page; thường gọi ISML template và dùng `PageRenderHelper.getRegionModelRegistry()` để render từng region. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))
- `storePage.isml` ví dụ: add CSS `storePage.css`, render `main` và `legalnotice` regions thông qua `pdict.regions.<region>.render()`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))
- Mỗi region tìm components được gán + visible và gọi render function của component; component render lại gọi ISML template của component (vd `mainBanner.isml`) và có assets.addCss + Resource.msg. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))
- Wrapper dùng `dw.experience.RegionRenderSettings` / `dw.experience.ComponentRenderSettings` để tạo wrapper element + attributes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

### CSS standards (4 ý đúng như unit)
1) Wrapper mặc định là `div`
2) Region class: `experience-region experience-<region_definition_id>`
3) Component class: `experience-component experience-<componenttype_id>`
4) Nếu component type ID có dấu chấm, khi sang CSS class thì đổi `.` thành `-` (vd `assets.productile` → `experience-assets-productile`). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code))

### Vary the Look (style theo region)
- Muốn style khác nhau tùy region: ví dụ product tile khi nằm trong carousel cần style carousel-specific.
- Unit minh họa dùng render settings với:
    - `var carousel = component.getRegion('carousel');` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-developers/b2c-page-designer-explore-visual-code?utm_source=openai))