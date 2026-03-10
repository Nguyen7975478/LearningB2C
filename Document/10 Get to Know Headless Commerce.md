# b2c-explore-headless-commerce — Get to Know Headless Commerce
https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce

---

## English (Detailed summary — keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Define **headless commerce**.
- Discuss the difference between a **headless** and **traditional** approach.
- List three advantages of using a headless approach. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Introduction (story context)
- Vijay Lahiri (Cloud Kicks) explores **headless commerce** to help deliver more personalized experiences faster across a wider set of touchpoints. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Traditional Commerce Approach (tightly coupled / monolithic)
- Traditional approach often means complex, tightly coupled software on **monolithic systems**.
- A single customization can require editing multiple layers from front end to back end; testing/troubleshooting increases.
- Some changes can void support warranties or block future upgrades.
- Innovation slows due to day-to-day work; traditional storefronts often deliver content mainly as websites or mobile apps, while marketing wants more devices/touchpoints. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Salesforce B2C Commerce (SaaS baseline)
- Cloud Kicks already uses **B2C Commerce** (fully cloud-hosted **SaaS**).
- Salesforce manages database maintenance, security patching, infrastructure/operations.
- Salesforce updates B2C Commerce multiple times a year, making innovations available such as **Einstein artificial intelligence (AI)** and **Page Designer** (drag-and-drop declarative editor).
- Even with reference architectures, changes can still impact both front end and back end; moving to headless increases flexibility.
- B2C Commerce provides developer tools including **RESTful APIs** to build experiences using headless architecture. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### What is Headless Commerce? (definition + front end vs back end)
- **Headless commerce**: content (product, prices, text, graphics) is stored and delivered without a front-end layer; the “head” is decoupled from the back end and **APIs** bridge the gap to deliver content to any screen/device.
- **Front end** = shopper experience layer (what appears on storefront).
- **Back end** = business processes/commerce services/data (search, promotions, pricing, inventory, checkout).
- Front end and back end operate independently; changes to one don’t require changes to the other. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Why Headless? (reasons/advantages)
Headless uses APIs + a back-end data model + cloud infrastructure so developers can use any front-end tool. It enables:
- **Increase feature rollout velocity** by separating front- and back-end change requirements.
- **Widen technology scope** via independent tech choices, industry standard tools/components, wide spectrum of code-based tools/connectors/APIs, combining best-of-breed tools for ecommerce + CMS, and commerce-friendly APIs/tools for heavy customization/personalization.
- **Integrate more** using certified pre-integrated back-end connectors (tax → payments, etc.), mixing and matching commerce services for the right touchpoint/channel/device.
- **Expect improvement on key metrics** including website performance and **SEO**, and increased front-end portability (mobile, smartwatches, kiosk screens, IoT). ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Faster Impact
- Headless can significantly speed delivery of front-end changes (look/feel, checkout, account management).
- Front-end pushes can reflect almost instantly; innovations are independent of back end.
- Compared with traditional publishing processes where changes propagate more slowly; multiple iterations of replication/testing can slow down releases. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Seamless Viewing
- Headless makes it easier to control shopper-facing elements; marketing can be more creative.
- Universal compatibility helps sites work across devices/viewing formats; traditional approaches rely on responsive design and add testing effort. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Personalize the Shopper Experience
- Headless helps capture data and unify the customer journey; the back end recognizes shoppers across channels.
- With a complete view, storefront apps can personalize at scale using **AI** from storefront to third-party front-end apps; enables presenting data on many touchpoints. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### What are RESTful APIs?
- **RESTful API** uses **HTTP** requests/responses with methods like GET/POST.
- Any programming language can use HTTP; REST typically uses less bandwidth than **SOAP** and is internet-suitable.
- RESTful APIs are **stateless**; client and server must be independent, and either can be coded in any language.
- RESTful APIs let you build custom flows (for example, checkout) across devices using the same APIs; moving to headless can be gradual (keep integrated approach in production while building new headless capability). ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

---

## Tiếng Việt (Tóm tắt chi tiết — giữ nguyên thuật ngữ)

### Learning Objectives
Sau khi học xong unit, bạn có thể:
- Định nghĩa **headless commerce**.
- Nêu khác biệt giữa **headless** và **traditional approach**.
- Liệt kê 3 advantages của headless. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Traditional Commerce Approach (tightly coupled / monolithic)
- Nhiều nền tảng truyền thống dùng phần mềm phức tạp, tightly coupled trên **monolithic systems**.
- Một customization có thể phải sửa nhiều layer từ front end đến back end → tăng effort test/troubleshoot.
- Một số thay đổi có thể ảnh hưởng support warranty hoặc cản trở upgrades.
- Innovation dễ bị chậm; thường chỉ nhắm website/mobile app, trong khi marketing muốn mở rộng touchpoints/devices. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Salesforce B2C Commerce (SaaS)
- **B2C Commerce** là nền tảng **SaaS** cloud-hosted; Salesforce quản lý DB maintenance, security patching, và hạ tầng/vận hành.
- B2C Commerce được cập nhật nhiều lần/năm; innovation như **Einstein artificial intelligence (AI)** và **Page Designer** được cung cấp thường xuyên.
- Dù có reference architectures, thay đổi vẫn có thể ảnh hưởng cả front end và back end; headless giúp linh hoạt hơn.
- Có developer tools gồm **RESTful APIs** để build trải nghiệm theo headless architecture. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Headless commerce là gì (định nghĩa + front end/back end)
- **Headless commerce**: lưu trữ nội dung (product, prices, text, graphics) và deliver không cần front-end layer; “head” tách khỏi back end; **APIs** làm cầu nối deliver đến mọi screen/device.
- **Front end** = lớp trải nghiệm shopper.
- **Back end** = business processes/commerce services/data (search, promotions, pricing, inventory, checkout).
- Front end và back end hoạt động độc lập; thay đổi một bên không bắt buộc đổi bên kia. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Vì sao headless (advantages)
Headless dùng APIs + back-end data model + cloud infrastructure để:
- Tăng **feature rollout velocity** (tách y��u cầu thay đổi front/back).
- Mở rộng **technology scope** (chọn tech độc lập; dùng industry standard tools; dùng connectors/APIs; kết hợp best-of-breed ecommerce + CMS; commerce-friendly APIs cho customization/personalization).
- **Integrate more** (certified pre-integrated connectors, tax → payments; mix & match commerce services theo touchpoint/channel/device).
- Kỳ vọng cải thiện metrics: performance, **SEO**, và portability lên mobile/smartwatch/kiosk/IoT. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### Faster Impact / Seamless Viewing / Personalize
- Faster impact: front-end changes phản ánh nhanh; ít phụ thuộc back end; truyền thống chậm do publishing + replication/testing.
- Seamless viewing: tương thích tốt đa thiết bị; giảm rủi ro hiển thị sai và giảm gánh test so với cách truyền thống.
- Personalize: unify customer journey; back end nhận diện shopper xuyên kênh; dùng **AI** để personalize ở quy mô lớn, kể cả third-party front-end apps. ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))

### RESTful APIs là gì
- **RESTful API** dùng **HTTP**, methods như GET/POST; language-agnostic.
- REST thường ít bandwidth hơn **SOAP**; phù hợp internet.
- RESTful APIs **stateless**; client/server độc lập; dễ maintain/evolve.
- Có thể dùng cùng APIs để build custom flows đa thiết bị; transition sang headless không cần “all at once” (có thể vừa giữ integrated approach vừa phát triển headless). ([trailhead.salesforce.com](https://trailhead.salesforce.com/de/content/learn/modules/b2c-headless-commerce-basics/b2c-explore-headless-commerce))