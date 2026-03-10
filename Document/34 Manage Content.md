# Manage Content
https://trailhead.salesforce.com/content/learn/modules/b2c-pricebooks-images-content/b2c-manage-content

## English

## Learning Objectives
(As reflected by the unit content retrieved)
- Create and manage **content assets** in Business Manager.
- Understand private vs shared **content libraries** and how they affect storefront search indexing.
- Import content (images/zip and XML) via Content Import & Export.
- Understand the embedded **CDN** option and how content delivery works.

## What content assets are
- Content assets can include text, images, and links (URLs).
- Not all content must be authored inside Business Manager; you can import assets.

## Libraries: private vs shared (key behavior)
- B2C Commerce indexes content in the site library (private or shared).
- Important indexing behavior:
    - If a site uses a **shared library**, content in the private library does **not** appear in the search index.
    - B2C Commerce still considers **site-specific attribute values** for content assets when indexing.

## Create a content asset (unit walkthrough highlights)
- Similar to product records, you **lock** a content asset for editing.
- Lock duration: **60 minutes**.
  Steps shown:
1) Business Manager → Merchant Tools | Site | Content | **Content Assets**
2) New
3) Select language
4) ID: `team-jacket-countdown`
5) Name: `Team Jacket Countdown`
6) Online and searchable: Yes
7) Rendering template (controls where content displays)
8) Custom CSS file (loads for the content)

## Import and export content (files + folder structures)
- You can import image and zip files into your library via:
    - Merchant Tools | Site | Content | **Import & Export**
- You can also import folder structures and content via XML through the same import module.

## Content and storefront search (important connection)
- B2C Commerce search indexes content (not only products).
- Content indexing behavior depends on whether the site is using a private or shared library as described above.

## Content Delivery Network (CDN)
- B2C Commerce includes an embedded **CDN** that serves content near shoppers via proxy servers.
- Enablement: contact Salesforce Support to enable the embedded CDN service.
- You can also use your own CDN in combination with the embedded CDN:
    - put your CDN (or a reverse proxy) in front of B2C Commerce to improve performance/security or add functionality.

## Tiếng Việt

## Learning Objectives
- Tạo và quản lý **content assets** trong Business Manager.
- Hiểu private vs shared **content libraries** và ảnh hưởng tới search indexing.
- Import content (images/zip và XML) qua Content Import & Export.
- Hiểu embedded **CDN** và cách content delivery hoạt động.

## Content assets là gì
- Content assets gồm text, images, và links (URLs).
- Không bắt buộc tạo mọi content trong Business Manager; có thể import.

## Libraries: private vs shared (hành vi quan trọng)
- B2C Commerce index content trong site library (private hoặc shared).
- Hành vi indexing:
    - Nếu site dùng **shared library**, content trong private library sẽ **không** xuất hiện trong search index.
    - Khi index content assets, hệ thống vẫn xét **site-specific attribute values**.

## Tạo content asset (walkthrough)
- Content asset cần **lock** để edit, giống product records.
- Lock tồn tại **60 phút**.
  Steps:
1) Merchant Tools | Site | Content | **Content Assets**
2) New → chọn language
3) ID `team-jacket-countdown`
4) Name `Team Jacket Countdown`
5) Online and searchable: Yes
6) Rendering template (quyết định content hiển thị ở đâu)
7) Custom CSS file (load cho content)

## Import/export content (files + folder structures)
- Import images/zip:
    - Merchant Tools | Site | Content | **Import & Export**
- Import folder structures/content qua XML cũng trong module này.

## Content và storefront search
- Search của B2C Commerce index cả content (không chỉ products).
- Kết quả phụ thuộc vào private/shared library như đã nêu.

## CDN
- Có embedded **CDN** (proxy servers gần shopper); cần Salesforce Support để enable.
- Có thể dùng CDN riêng kết hợp embedded CDN, đặt CDN/reverse proxy trước B2C Commerce để tăng performance/security hoặc thêm chức năng.