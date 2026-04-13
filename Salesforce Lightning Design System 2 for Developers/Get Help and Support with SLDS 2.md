# Get Help and Support with SLDS 2
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2?trail_id=get-started-with-slds-2

## EN (A-level: rewritten better; includes FAQs + lifecycle support loop)

### Time Estimate / Topics
**~5 mins**  
Topics on the page:
- Learning Objectives
- Got Questions?
- How to Get Help with SLDS 2
- Next Steps to Support Your Org in SLDS 2
- Resources ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

---

## Learning Objectives
After completing this unit, you’ll be able to:
- Answer some of the most frequently asked questions about SLDS 2.
- Describe how to get support if you need it.
- Explain how to support your org through its lifecycle in SLDS 2. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

---

## Got Questions? (FAQ-style: what Salesforce expects you to know)
### Will SLDS 2 affect my existing customizations?
- Most customizations transition smoothly due to reliance on styling hooks, but you should test thoroughly in sandbox.
- Expected behaviors by usage pattern: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))
    - **Uses Lightning Base Components (LBC):** typically no action required; exception if you added custom CSS overrides.
    - **Uses supported styling hooks/classes correctly:** automatically receives updates when SLDS 2 is active; align markup with SLDS blueprints.
    - **Uses CSS overrides:** move hard-coded values to styling hooks; remove as many class overrides as possible.
    - **Uses deprecated syntax:** update old BEM syntax (example given: `.slds-button--neutral` → `.slds-button_neutral`).
    - **Doesn’t use hooks/classes correctly:** won’t automatically adopt the new design; fix usage to align.

### Can I switch back to SLDS 1 if needed?
- Yes: Setup → Themes and Branding → activate an SLDS 1 theme (org-wide). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))
- Trailhead recommends transitioning fully to SLDS 2. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

### Will SLDS 2 be available for Experience Cloud sites?
- Not currently available on Experience Cloud (as stated on the page). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

### How will SLDS 2 affect AppExchange solutions?
- Most work, but you should test each in sandbox.
- Timing/compatibility depends on the ISV partner; contact the ISV for issues. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

### Will I need to retrain my users?
- It’s intuitive, but Trailhead recommends familiarizing users with changes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

### What’s supported vs not supported? / known gaps
- Availability rolls out incrementally; check “Salesforce Cosmos Theme and SLDS 2 Availability” for the latest. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))
- Known gaps/issues listed include:
    - Cozy/Compact density not supported
    - some AppExchange incompatibilities
    - custom Lightning components may need more adjustments
    - some tokens/hooks aren’t supported (deprecated classes and component-level styling hooks aren’t supported)
    - some SLDS Validator features (token→hook mapping) are subject to change ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

---

## How to Get Help with SLDS 2
- Join the **Design Trailblazers** group (login required) for community support and discussions. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

---

## Next Steps to Support Your Org in SLDS 2 (lifecycle loop)
Trailhead’s recommended ongoing behavior:
- Keep using **SLDS Validator** and SLDS 2 developer tools as you build and deploy new code (continuous validation).
- Read release notes.
- Participate in the Trailblazer community and share designs/wins. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

---

## Resources (as listed)
- Help: Salesforce Cosmos and SLDS 2 Availability
- Salesforce Lightning Design System 2 website
- Trailblazer Group: Design Trailblazers (login required)
- Salesforce Developer Documentation: Get Started with SLDS Linter
- SLDS Validator Developer Guide: Get Started ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

---

## VI (A-level: viết lại tốt hơn; có FAQ + hướng hỗ trợ theo “vòng đời”)
### Topics
- Learning Objectives
- Got Questions?
- How to Get Help with SLDS 2
- Next Steps to Support Your Org in SLDS 2
- Resources ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

### Learning Objectives
- Trả lời các câu hỏi FAQ thường gặp về SLDS 2.
- Biết cách nhận support.
- Biết cách “vận hành lâu dài” org trong SLDS 2. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

### FAQ quan trọng
- Customizations đa số chuyển mượt nhờ styling hooks, nhưng phải test trong sandbox. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))
- LBC thường không cần làm gì (trừ khi override CSS).
- Có CSS overrides → nên chuyển hard-coded values sang styling hooks và giảm overrides.
- Deprecated syntax → update BEM cũ (ví dụ `.slds-button--neutral` → `.slds-button_neutral`).
- Experience Cloud: hiện **chưa** hỗ trợ SLDS 2. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))
- AppExchange: phần lớn chạy được nhưng phụ thuộc ISV, cần test và liên hệ ISV khi có issue. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))
- Known gaps: chưa hỗ trợ Cozy/Compact density; một số tokens/hooks không support; một số tính năng SLDS Validator có thể thay đổi. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

### Cách lấy help
- Tham gia **Design Trailblazers** group để hỏi/trao đổi. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))

### Ongoing support (lifecycle)
- Tiếp tục dùng SLDS Validator + developer tools khi deploy code mới; theo dõi release notes; tham gia cộng đồng và chia sẻ “wins”. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/get-help-and-support-with-slds-2))