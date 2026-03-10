# Explore Salesforce CMS and Page Designer
https://trailhead.salesforce.com/content/learn/modules/b2c-page-designer-cms/b2c-explore-cms-page-designer?trail_id=set-up-merchandising-for-your-storefront

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain why it’s important to have **one source of truth** for storefront content.
- Describe how **Salesforce CMS** enables you to deploy content across multiple channels.
- List three steps to take to implement Salesforce CMS with Salesforce B2C Commerce Page Designer.
- List three benefits of Salesforce CMS.

## The pain points (why “one source of truth” matters)
The unit explains Cloud Kicks’ problem:
- They use B2C Commerce built-in content management, but growth makes content development a **bottleneck**.
- Example scenario:
    - Brandon creates a blog post in an external system.
    - Vijay must write HTML and publish it in Business Manager.
    - Result: content is locked to B2C Commerce storefront and can’t be reused across channels.

What “one source of truth” solves (unit meaning):
- Without a connected CMS:
    - content is isolated and not connected to Salesforce platform data,
    - there is no cross-business tracking of **how, when, and where** content is used,
    - developers must reproduce content for each channel,
    - and personalization is hard because content is not connected to data.

The unit lists Brandon’s pain points:
- He can only use content in one place.
- He can’t get new content out fast enough.
- His CMS isn’t connected to data, so he can’t personalize it.
- People keep asking him to create content, which impacts his work production.

## What Salesforce CMS is (technical definition + features)
The unit describes Salesforce CMS as:
- A tool to create, manage, and deliver focused content.
- Users can select a content type or create custom types and draft content quickly (no technical skills required).
- It includes:
    - **Multi-language and translation** support (scaling globally)
    - **Permissions** (collaboration while maintaining brand standards)
    - **Content collections** (like “playlists” of content for reuse)
- Technical core:
    - Salesforce CMS is an **API-first headless content service** with centralized out-of-the-box functionality native to the Salesforce CRM platform.
    - It can deliver content to every channel, including B2C Commerce.

Why “API-first headless” matters (to understand the idea):
- Content is stored as structured content (not tied to storefront templates).
- Any channel can consume it through APIs and channels.

## Benefits of Salesforce CMS (3 benefits stated)
The unit lists:
- Each team can gain experience with easy-to-use tools.
- Each team can deliver content to any experience, whether built with Salesforce CRM or not.
- Content is connected and personalized from any source.

## Create and deliver content to commerce channels (how CMS + Page Designer combine)
The unit describes the cross-channel story:
- Create content in Salesforce CMS (core platform).
- Use **Page Designer for B2C Commerce** to deploy that content as shopping experiences.
- Within Salesforce ecosystem, also use **Experience Builder** to push the same content to B2B clients/retailers.

## Steps to implement CMS with B2C Commerce Page Designer (unit steps)
The unit lists:
1) Vijay installs and connects Salesforce CMS to Page Designer.
2) In Salesforce CMS, Brandon creates and manages options for a new headline banner content.
3) In Page Designer dev environment, Vijay creates a new component type that displays the headline banner.
4) In Page Designer, Brandon adds the component type to a page and selects which CMS content to use from the Salesforce CMS repository.

Interpretation:
- Vijay builds the “pipes” (integration + component type).
- Brandon uses the pipes (select content + publish experience).

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích vì sao cần **one source of truth** cho storefront content.
- Mô tả Salesforce CMS deploy content đa kênh như thế nào.
- Liệt kê các bước triển khai Salesforce CMS với B2C Commerce Page Designer.
- Liệt kê 3 benefits của Salesforce CMS.

## Pain points (vì sao cần “one source of truth”)
Unit mô tả vấn đề của Cloud Kicks:
- Dùng built-in content management của B2C Commerce, nhưng khi scale thì thành **bottleneck**.
- Scenario:
    - Brandon viết blog ở hệ thống ngoài.
    - Vijay phải viết HTML và publish trong Business Manager.
    - Content bị khóa trong storefront B2C Commerce, không reuse đa kênh.

“One source of truth” giải quyết gì:
- Nếu không có CMS kết nối:
    - content bị cô lập, không connected với dữ liệu Salesforce,
    - không track được content “dùng ở đâu/khi nào/như thế nào”,
    - dev phải reproduce content cho từng channel,
    - personalization khó vì content không gắn với data.

Pain points của Brandon (unit):
- Chỉ dùng content ở một nơi.
- Không ra content nhanh.
- CMS không connected data nên không personalize được.
- Bị yêu cầu tạo content liên tục nên giảm năng suất.

## Salesforce CMS là gì (định nghĩa kỹ thuật + features)
Unit mô tả Salesforce CMS:
- Tạo/quản lý/deliver content.
- Chọn content type hoặc tạo custom types; draft nhanh (không cần kỹ năng kỹ thuật).
- Có:
    - **Multi-language/translation**
    - **Permissions**
    - **Content collections** (như playlist)
- Cốt lõi kỹ thuật:
    - **API-first headless content service** trên Salesforce CRM platform.
    - Deliver content tới mọi channel, gồm B2C Commerce.

Vì sao “API-first headless” quan trọng:
- Content tách khỏi templates; kênh khác nhau có thể consume qua API/channels.

## Benefits (3 benefits)
- Tools dễ dùng cho nhiều team.
- Deliver content tới mọi experience (Salesforce hoặc không).
- Content connected và personalize từ mọi nguồn.

## CMS + Page Designer phối hợp (đa kênh)
- Tạo content trong Salesforce CMS.
- Dùng **Page Designer** deploy thành shopping experiences trên B2C Commerce.
- Có thể dùng **Experience Builder** để push cùng content sang B2B clients/retailers.

## Steps implement (unit)
1) Vijay connect CMS ↔ Page Designer.
2) Brandon tạo/manage headline banner options trong CMS.
3) Vijay tạo component type hiển thị banner.
4) Brandon add component type vào page và chọn CMS content từ repository.