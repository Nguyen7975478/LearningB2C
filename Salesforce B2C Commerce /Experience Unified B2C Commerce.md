# Experience Unified B2C Commerce
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce

## EN (A-level: detailed; follows the unit Topics)

### Learning Objectives
After completing this unit, you’ll be able to:
- Explain how merchandising tools, such as **Geolocation** and **Dynamic Customer Groups**, personalize the storefront experience for first-time visitors based on location data.
- Explain how **Einstein Recommendations** and **predictive sort** optimize product discovery by prioritizing relevant items and resolving terminology differences.
- Describe the role of **Agentforce Guided Shopping** in answering specific customer inquiries regarding product details and store policies by using generative AI.
- Explain how a **unified commerce strategy** connects Order Management, Point of Sale, and Data 360 to create a consistent, cross-channel shopper profile. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

---

## Make Agentforce Commerce for B2C a Unified Commerce Experience
- Ecommerce businesses adopt **unified commerce** to meet expectations, grow, and reduce cost of ownership.
- Unified commerce = all channels, touchpoints, and backend systems work as one.
- Agentforce Commerce combines:
    - Agentforce Commerce for B2C
    - Order Management (OM)
    - Retail Cloud POS
      on a single platform, centralizing ecommerce and inventory/operations. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))
- Benefit: consistent experiences online/in-store/mobile through centralized real-time visibility of products, orders, and customer interactions. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

---

## Add Agentforce Guided Shopping
- Guided Shopping provides a 24/7 conversational shopping assistant, secured by the Salesforce trust layer.
- It helps shoppers find products and purchase faster with natural language on storefront or messaging apps.
- It uses SCAPI to retrieve product info and combines NLP with Data 360 + B2C store data for a personalized “in-store shopping” feel online.
- Outcomes: convenience, personalized attention, product search/help/recommendations/promotions/FAQs/secure checkout; business sees increased conversion and lower service costs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

---

## Integrate Agentforce Commerce with Data 360, Agentforce Marketing, and Agentforce Service
### Data 360 + Commerce
- Data 360 for Agentforce Commerce for B2C provides a unified, activated 360-degree customer view.
- Integrating Data 360 enables real-time data usage (orders, engagement events, profiles), near real-time segmentation, and personalization. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Marketing + Commerce
- Unifying commerce + marketing data improves the customer view and supports consistent, relevant engagement across touchpoints, increasing efficiency and satisfaction. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Service + Commerce
- Integration gives service reps real-time view across commerce + service:
    - view catalog + inventory
    - access recommendations
    - place orders on behalf of shoppers
    - co-browse, view cart, add products, complete transactions
- Result: customer service becomes a shopping channel with cross-sell/upsell opportunities. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

---

## Experience Unified Commerce (Gabby scenario)
### Setup
- Gabby is a first-time visitor to Northern Trail Outfitters (NTO) from northern US, shopping for winter hiking boots.
- NTO uses:
    - ecommerce: Agentforce Commerce for B2C
    - unified apps: B2C + OM + POS
    - integrations: Data 360, Agentforce Marketing, Agentforce Service. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Personalization on first visit (Geolocation + Dynamic Customer Groups)
- Geolocation detects IP region; dynamic customer groups segment by location.
- Homepage content slot shows winter hero imagery/gear for her region rather than warm-weather assets.
- Merchandisers/designers build this layout using Page Designer (drag-and-drop components, no dev code needed). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Search + discovery (Einstein + predictive sort + refinements)
- Einstein search recommendations provide term completion.
- Merchandiser configures dictionaries/synonyms (e.g., “snow boots” vs “insulated footwear”) to resolve terminology differences.
- Predictive sort ranks the most relevant/high-quality items first.
- Refinement filters (Waterproof/Insulated) appear because merchandisers configured refinement definitions based on product attributes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Real-time recommendations
- Einstein recommendations analyze real-time browsing behavior and dynamically refine recommendations during the session.
- Site shows similar products, add-to-cart options, and recently viewed products to guide the shopper. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Guided Shopping Q&A + checkout assistance
- Gabby asks about warmth rating, sizing, and return policy.
- Guided Shopping (generative AI) answers and recommends local store try-on / in-store pickup.
- “Complete the Set” suggestions are powered by Einstein recommendations (complementary items like socks/traction cleats). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Promotions at checkout
- Promotion engine shows personalized promotional offers for seasonal gear.
- Campaign is targeted at new visitors to drive first purchase and brand loyalty. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

---

## In-Store Pickup with Unified Commerce
- With B2C + OM + POS, NTO delivers consistent experiences across online/in-store/mobile.
- Gabby selects in-store pickup; associate uses POS to access her unified profile (order + purchase history + preferences).
- OM tracks the order in real time, increasing transparency for shoppers and service reps. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

---

## Connect the Entire Shopper Journey
- Data 360 segmentation adds Gabby to “new customer” segment.
- Marketing sends a personalized follow-up offer (e.g., discount on winter gloves) relevant to her purchase.
- Months later, Service integration helps a rep see her order history to resolve boot-care questions quickly, reinforcing loyalty. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

---

## Wrap Up
- The unit ties together: B2C Commerce features + tools for engaging shoppers, plus unified commerce integrations (B2C + OM + POS + Data 360/Marketing/Service) to create consistent cross-channel experiences and a comprehensive customer view. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

---

## VI (A-level: chi tiết; bám sát Topics của unit)

### Mục tiêu học
- Giải thích Geolocation + Dynamic Customer Groups cá nhân hóa trải nghiệm cho first-time visitor.
- Giải thích Einstein Recommendations + predictive sort tối ưu discovery và xử lý khác biệt thuật ngữ.
- Mô tả vai trò Agentforce Guided Shopping (gen AI) trả lời câu hỏi chi tiết.
- Giải thích unified commerce kết nối OM + POS + Data 360 để tạo shopper profile nhất quán đa kênh. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Unified commerce là gì?
- Unified commerce = mọi kênh/touchpoint/backend systems hoạt động như một.
- Agentforce Commerce gom B2C + OM + Retail Cloud POS trên một platform → real-time view sản phẩm/đơn hàng/tương tác. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Agentforce Guided Shopping
- Trợ lý mua sắm hội thoại 24/7 (trust layer), dùng SCAPI + NLP + Data 360 + store data để cá nhân hóa.
- Giúp search/recommend/promotions/FAQs/checkout → tăng conversion, giảm service cost. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Integrations (Data 360 / Marketing / Service)
- Data 360 + Commerce: unified 360 view, near real-time segmentation, personalization dựa trên orders/events/profiles.
- Marketing + Commerce: thống nhất data để messaging nhất quán, nâng hiệu quả.
- Service + Commerce: reps thấy real-time view, co-browse/cart/order placement → service trở thành shopping channel. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Gabby scenario (trải nghiệm thực tế)
- First visit, geolocation + dynamic customer groups đổi hero content sang winter theme; build bằng Page Designer (drag-drop, không cần code).
- Einstein search term completion + dictionary synonyms + predictive sort + refinements theo product attributes.
- Einstein recommendations dựa trên hành vi realtime, hiển thị similar/recently viewed/complete-the-set.
- Guided Shopping trả lời warmth/sizing/returns và gợi ý in-store pickup.
- Promotions cá nhân hóa, campaign target new visitors. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### In-store pickup
- B2C + OM + POS: associate dùng POS xem unified profile; OM track realtime. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))

### Connect entire journey
- Data 360 segmentation → new customer segment; Marketing gửi ưu đãi phù hợp; Service xem order history để hỗ trợ nhanh → tăng loyalty. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/cc-digital/experience-unified-b2c-commerce))