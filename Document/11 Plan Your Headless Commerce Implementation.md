# b2c-plan-your-headless-implementation — Plan Your Headless Commerce Implementation
https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation

---

## English (Detailed summary — keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Describe a typical **headless commerce use case**.
- List three benefits of converting to **headless**.
- List three potential headless tools.
- Explain when you’d choose a headless approach. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### Introduction: suitability + costs
- The story uses Cloud Kicks and Vijay Lahiri considering inspiration from headless early adopters.
- Headless adoption is associated with **technical maturity** and can increase **short-term costs** (more IT/development investment).
- Best candidates often have a strong IT department and do-it-yourself mindset, long development queues, and ambitious creative/marketing teams wanting faster front-end changes.
- Headless provides flexibility for large merchants with many developers and for Salesforce partners doing extensive implementations; ROI can offset added costs.
- The merchant typically owns the **front end** in headless; the team must also plan for security, developer operations, hosting, and compliance. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### Start with SFRA-style development, then move to headless (hybrid path)
- Vijay compares headless to **SFRA-style development**, where Salesforce provides base storefront cartridges and merchants layer **LINK**, third-party, and custom cartridges.
- **LINK cartridges** (LINK Technology Partner Program) are pre-integrated solutions compatible with B2C Commerce storefront apps (examples given: PayPal payments, Bazaarvoice ratings).
- **SFRA** includes both front-end and back-end functionality; some storefront apps may keep SFRA.
- Strategy: start with SFRA for fastest time to market, then **mix and match** between SFRA and headless as needs dictate—quick time to value now + flexibility for future innovation. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### Build headless with PWA Kit and Managed Runtime
- Alternative path: use **Progressive Web App (PWA) Kit** + **Managed Runtime** to go headless without starting from scratch.
- **PWA Kit** (React framework) includes:
    - Project templates (customizable storefront implementing core ecommerce flows home → checkout)
    - Rendering system (server-side + client-side) and **hydration**
    - Routing system that injects Commerce API data into components
    - Utility functions/scripts for automating routine dev tasks
    - Integration with **B2C Commerce API** and **Open Commerce API (OCAPI)**
    - Support for essential progressive web app features
- PWA Kit + Managed Runtime: use templates + **Salesforce Commerce API** to go live sooner; customize prebuilt React components; offload runtime management; code in JavaScript or TypeScript; provides infrastructure to host/deploy/secure/scale/monitor (unit cites historical 99.99% uptime). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### Benefits of moving to a headless approach (as listed)
- Better employee adoption (team can access/update front end more easily).
- Fewer steps to front-end deployment (changes not routed through IT).
- Time savings across IT (non-developers can commit changes without tickets; developers focus on critical work).
- Faster time to market (launch new front-end experiences quickly; react to market with minimal costly back-end development).
- Many merchants investing in headless already have mature engineering practices like **CI/CD**; headless supports and extends those practices. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### Use Case: Artificial Intelligence (AI) + APIs/Heroku
- Vijay is interested in a platform that can handle digital experiences across touchpoints using **AI**.
- He wants to build a custom mobile app that scales using **Heroku** to reach shoppers anywhere.
- He’s evaluating **APIs** and Heroku for rapid, scalable app development in any language.
- Key planning questions: how tools work together with the new architecture and what to do to prepare for the change. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation?utm_source=openai))

### Define Roles (specialization)
- Recognize specialization: storefront development vs design are different jobs.
- With headless, creative teams focus on shopper experience (engagement/conversion); developers focus on back-end enhancements to make processes faster/richer and data more varied. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation?utm_source=openai))

### Wrap-up
- Headless is positioned as a long-term trend; the unit concludes you explored reasons, tools, and role differentiation. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation?utm_source=openai))

---

## Tiếng Việt (Tóm tắt chi tiết — giữ nguyên thuật ngữ)

### Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả một use case điển hình của **headless commerce**.
- Liệt kê 3 benefits khi chuyển sang **headless**.
- Liệt kê 3 potential headless tools.
- Giải thích khi nào nên chọn headless approach. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### Suitability + short-term costs
- Headless phù hợp với doanh nghiệp có **technical maturity**; có thể tăng **short-term costs** do mở rộng IT/development.
- Best candidate: IT mạnh, do-it-yourself, backlog phát triển dài, creative/marketing muốn rollout front-end nhanh.
- Merchant thường chịu trách nhiệm **front end**; cần thêm nguồn lực cho security, developer operations, hosting, compliance. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### Start with SFRA-style development, then move to headless
- **SFRA-style development**: Salesforce cung cấp base storefront cartridges; merchant stack **LINK**, third-party, custom cartridges.
- **LINK cartridges**: giải pháp pre-integrated từ LINK Technology Partner Program (ví dụ PayPal, Bazaarvoice).
- **SFRA** có cả front-end và back-end; có storefront vẫn nên giữ SFRA.
- Lộ trình: start SFRA để time to market nhanh, sau đó **mix and match** SFRA và headless theo nhu cầu—vừa nhanh go-live, vừa sẵn sàng kiến trúc headless cho innovation dài hạn. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### PWA Kit + Managed Runtime (headless path)
- Dùng **PWA Kit** + **Managed Runtime** để enable headless.
- **PWA Kit** (React framework) có templates, rendering (server/client) + **hydration**, routing inject Commerce API data, utilities/scripts, tích hợp **B2C Commerce API** + **OCAPI**, và các PWA features.
- Managed Runtime hỗ trợ host/deploy/secure/scale/monitor; dev có thể dùng JavaScript/TypeScript; giúp go live sớm với **Salesforce Commerce API**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### Benefits (liệt kê theo unit)
- Better employee adoption.
- Fewer steps to front-end deployment.
- Time savings across IT.
- Faster time to market.
- Nhiều merchant chọn headless đã có **CI/CD**; headless giúp nâng mức engineering practices. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation))

### Use Case: AI + APIs + Heroku
- Mục tiêu: trải nghiệm đa touchpoints với **AI**.
- Xây custom mobile app scale bằng **Heroku**; đánh giá **APIs** và Heroku để phát triển nhanh, scale, đa ngôn ngữ.
- Cần xác định cách các tools hoạt động cùng kiến trúc mới và chuẩn bị cho thay đổi. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation?utm_source=openai))

### Define Roles
- Tách vai trò: development vs design.
- Headless giúp creative teams tối ưu shopper experience; developers tập trung back-end enhancements. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation?utm_source=openai))

### Wrap-up
- Unit kết thúc: headless là xu hướng; bạn đã xem lý do, tools, và role differentiation. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/b2c-headless-commerce-basics/b2c-plan-your-headless-implementation?utm_source=openai))