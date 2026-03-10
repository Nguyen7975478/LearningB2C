# Preview and Resolve Conflicts
https://trailhead.salesforce.com/content/learn/modules/b2c-seo-urls/b2c-seo-url-preview-resolve-conflicts

## English

## Learning Objectives
- List three things you can do in Business Manager to resolve SEO URL conflicts.
- Explain how Salesforce B2C Commerce tracks category, folder, and search refinement SEO URLs.
- Describe how B2C Commerce regenerates the category and folder URLs.
- List three changes that initiate a category and folder URL regeneration.
- List two reasons for search refinement SEO URL conflicts.

## Why conflicts happen (uniqueness requirement)
- URLs must be unique; conflicts occur when generated endpoints collide.
- Business Manager helps you:
    - preview URLs
    - see status instantly
    - view conflict information and resolve it
- B2C Commerce automatically resolves many conflicts (but you still must validate and decide if auto-resolution is acceptable).

## How B2C Commerce tracks URLs (directory structure)
- B2C Commerce maintains a database directory of:
    - **category** URLs
    - **folder** URLs
    - **search refinement** URLs
- It does **not** store product/content URLs in the directory because those are built dynamically.
- Directory entries are per:
    - category in the site catalog
    - folder in the site library
    - per site locale
- A system job generates these URLs.

## Automatic uniqueness handling (index suffix)
- When generating URLs, B2C Commerce ensures unique URLs within categories/folders per locale.
- If duplicates are found, B2C Commerce appends an integer index to make them unique.
  Example:
- Two categories with display name `shoes`:
    - first becomes `shoes-1`
    - second becomes `shoes-2`

## When URL regeneration happens (change detection)
B2C Commerce regenerates category/folder URL mappings when changes occur, including:
- Added category/folder
- Removed category/folder
- Changed site assignment
- Changed category/folder name or ID
- Changed category/folder page URL, page description, or page keywords
- Changed category hierarchy (anything affecting `category-path` or `category-parent`)
- Changed attribute value
- Changed locale
- Changed URL settings that control URL mappings

Operational note:
- Job runs on any instance **but production**.
- Performance estimate: ~3 minutes for ~25,000 categories/folders.

## Preview SEO URLs (step-by-step)
1) Business Manager → Merchant Tools | SEO | **URL Rules**
2) Catalog (Content) URLs tab
3) Select a category in Category/Product/Locale field
4) Browse and select a product
5) Language: Default
6) Encoding: Text Encoded
7) Click **Preview**
- Results appear under Rule Preview.

## Validate and resolve Catalog/Content/Global conflicts
- After preview, click **Validate** to surface conflicts.
- General tab shows conflicts; you can expand:
    - Catalog URLs conflicts
    - Content URLs conflicts
    - Global Conflicts
- B2C Commerce auto-resolves by adding an integer at the end of the endpoint:
    - If acceptable: you can save.
    - If not acceptable: change rule syntax or use Page URL override to break ties.

Resolution steps:
1) Click Validate
2) Click a conflict value to open details
3) Expand conflict sections
4) Choose:
    - **Cancel**: manually resolve by changing rule syntax
    - **Save**: accept auto-resolution or use Page URL overrides
5) General tab → click **Run Update Now** to run regeneration and see updated status report

## Search refinement URL conflicts (2 causes)
Conflicts happen especially after URL cleansing/character replacement, for example:
1) Same value appears in different refinements (example: `red` used in both color and brand).
2) Refinement values contain delimiters used in the URL mapping:
    - `-` (hyphen)
    - `_` (underscore)
      B2C Commerce resolves many of these by appending an integer delimited with the configured delimiter.

## Three things you can do to resolve conflicts (unit theme)
- Change rule syntax (make patterns more specific/unique).
- Use the **Page URL** field override for one of the conflicting endpoints.
- Accept B2C Commerce auto-resolution and run update/validate again to confirm.

## Tiếng Việt

## Learning Objectives
- Liệt kê 3 việc có thể làm để resolve SEO URL conflicts.
- Giải thích B2C Commerce track category/folder/search refinement URLs như thế nào.
- Mô tả cơ chế regenerate category/folder URLs.
- Liệt kê 3 thay đổi kích hoạt regeneration.
- Liệt kê 2 nguyên nhân refinement URL conflicts.

## Vì sao có conflicts
- URL phải unique; conflicts xảy ra khi endpoints trùng nhau.
- Business Manager hỗ trợ preview/status/conflict details.
- Nhiều conflicts được auto-resolve nhưng vẫn cần Validate và quyết định.

## Directory structure (track URLs)
- B2C Commerce lưu directory cho category/folder/search refinement URLs trong DB.
- Không lưu product/content URLs vì build động.
- Directory theo category/folder và theo từng site locale; system job generate.

## Auto uniqueness (suffix index)
- Nếu trùng: tự append số.
- Ví dụ `shoes` → `shoes-1`, `shoes-2`.

## Khi nào regenerate URL mappings
Các triggers:
- add/remove category/folder
- đổi site assignment
- đổi name/ID
- đổi page URL/description/keywords
- đổi hierarchy (category-path/parent)
- đổi attribute value
- đổi locale
- đổi URL settings

Note: job chạy mọi instance trừ production; ~3 phút cho ~25k categories/folders.

## Preview SEO URLs (steps)
- URL Rules → Catalog/Content URLs → chọn category + product + locale + encoding → Preview.

## Validate và resolve conflicts
- Validate → xem Catalog/Content/Global conflicts.
- Auto-resolve bằng thêm integer:
    - OK thì Save
    - Không OK thì đổi syntax hoặc dùng Page URL override
- Run Update Now để regenerate và xem status.

## Refinement URL conflicts (2 nguyên nhân)
1) Trùng refinement value giữa refinements (red vừa color vừa brand).
2) Value chứa delimiters `-` hoặc `_`.
   Hệ thống thường resolve bằng append index.

## 3 cách resolve (tổng kết)
- Đổi rule syntax
- Dùng Page URL override
- Chấp nhận auto-resolution + Run Update/Validate lại