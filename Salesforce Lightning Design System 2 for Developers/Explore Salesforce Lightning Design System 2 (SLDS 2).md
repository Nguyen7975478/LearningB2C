# Explore Salesforce Lightning Design System 2 (SLDS 2)
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2?trail_id=get-started-with-slds-2

## EN (A-level: rewritten better; matches Trailhead unit Topics + includes the key technical details)

### Time Estimate / Topics
**~10 mins**  
Topics on the page:
- Learning Objectives
- Before You Start
- What Is Salesforce Lightning Design System 2?
- Benefits for Developers
- Architecture and Capabilities
- Resources ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

---

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe what SLDS 2 is.
- Define two key benefits for developers.
- Explain what styling hooks and components are. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

---

## Before You Start
- This module is specifically for **developers** working with SLDS 2. If you’re an admin, Trailhead points you to the “Salesforce Lightning Design System 2 for Admins” module.
- Trailhead recommends completing **The Salesforce Cosmos Theme: Quick Look** first. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

---

## What Is Salesforce Lightning Design System 2?
- **SLDS 2** is the latest design system for Lightning Platform products and is described as the foundation of Salesforce’s **agentic design system**.
- Its purpose: help you create **consistent, accessible, scalable** UIs that align with Salesforce design principles and visual language.
- Key features called out:
    - **Components** (building blocks of UI)
    - **Global styling hooks** + a semantic styling hook framework
    - The built-in **Salesforce Cosmos** theme
    - A tooling suite (including **SLDS Validator**) ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

---

## Benefits for Developers (the “why should I care?”)
SLDS 2 is positioned as giving developers **more pro-code, granular control** of an org’s UI:
- **Assess code quality** more easily using updated tools like **SLDS Validator** (rule sets + bulk reporting).
- **Code faster** with a more flexible, “agentic-forward” architecture—especially via **global styling hooks**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

---

## Architecture and Capabilities
### A) New CSS architecture: structure decoupled from theme
- SLDS 2 is built with a new CSS framework that **separates structure from theme** using styling hooks. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

### B) What the architecture explicitly includes
- **Lightning Base Components (LBC)** are called out as the *preferred* out-of-the-box solution.
- **Backward compatibility with SLDS 1**: both SLDS 1 and SLDS 2 share common CSS + styling hooks so component blueprints keep working, but Salesforce recommends upgrading toward LBC where possible.
- Compatibility with **next-generation components** for agent-first experiences (Agentforce) that can be enhanced with descriptive metadata; SLDS 2 helps you customize the style and performance of agent UIs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

### C) Global Styling Hooks (what they are + how to use them)
- Styling hooks control styling like **color, spacing, fonts, borders**.
- They’re an evolution of SLDS 1 design tokens and are implemented with **CSS custom properties** (CSS variables).
- Namespace: `--slds`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

**Refactor example shown in the unit (hard-coded → styling hooks with fallback):**
```css
/* Hard-coded CSS */
.my-custom-card {
  background-color:#ffffff;
  border-radius: 1rem;
}
/*  ----- Refactor to -----  */
/* Updated CSS */
.my-custom-card {
  background-color: var(--slds-g-color-surface-container-1, #ffffff);
  border-radius: var(--slds-g-radius-border-4, 1rem);
}
``` ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

**Naming structure (how to “read” a hook)**
The unit provides the pattern:
- `--[namespace]-g–[category]-[property]-[pairing]-[role]-[attribute]-[state]-[range]` ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

### D) Components (what “component” means in SLDS 2 context)
The unit distinguishes component-related concepts you’ll touch as a developer:
- **Lightning Web Component**: modern standards-based framework (HTML/CSS/JS).
- **Lightning Base Component**: the programmatic components built to SLDS blueprints; provides baseline functionality.
- **Custom Lightning Component**: customer-built reusable components (with or without base components).
- **Component Blueprint**: framework-agnostic HTML/CSS representing the visual design part of a component. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

---

## VI (A-level: viết lại tốt hơn; đúng Topics + có phần kỹ thuật cốt lõi)

### Thời lượng / Topics
**~10 phút**  
- Learning Objectives
- Before You Start
- What Is SLDS 2?
- Benefits for Developers
- Architecture and Capabilities
- Resources ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

### Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả SLDS 2 là gì.
- Nêu 2 lợi ích chính cho developer.
- Giải thích styling hooks và components là gì. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

### Before You Start
- Module này dành cho **developer**; nếu là admin thì Trailhead hướng sang module SLDS 2 for Admins.
- Nên hoàn thành **The Salesforce Cosmos Theme: Quick Look** trước. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

### SLDS 2 là gì?
- SLDS 2 là design system mới nhất cho Lightning Platform products và là nền tảng cho “agentic design system”.
- Mục tiêu: UI **consistent + accessible + scalable**, đúng design principles/visual language của Salesforce.
- Key features:
  - components
  - global styling hooks + semantic framework
  - theme mặc định **Salesforce Cosmos**
  - tooling suite (ví dụ **SLDS Validator**) ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

### Lợi ích cho developer
- Nhiều **pro-code control** và chi tiết hơn cho UI.
- Dễ audit chất lượng code bằng tool mới (SLDS Validator + bulk reporting).
- Code nhanh hơn nhờ kiến trúc linh hoạt + global styling hooks. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

### Architecture & Capabilities
- Kiến trúc CSS mới tách **structure** khỏi **theme** bằng styling hooks. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))  
- Bao gồm:
  - Lightning Base Components (khuyến nghị dùng)
  - backward compatibility SLDS 1 (blueprints vẫn chạy, nhưng nên nâng cấp dần)
  - hỗ trợ next-gen components cho agent-first UI (Agentforce) ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

**Styling hooks**
- Là CSS variables (custom properties), namespace `--slds`, kiểm soát color/spacing/fonts/borders. ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))  
- Ví dụ refactor (giữ fallback) đúng như unit:
```css
.my-custom-card {
  background-color: var(--slds-g-color-surface-container-1, #ffffff);
  border-radius: var(--slds-g-radius-border-4, 1rem);
}
``` ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))

**Components**
- LWC (framework), LBC (base components theo blueprint), custom component, component blueprint (HTML/CSS agnostic) ([trailhead.salesforce.com](https://trailhead.salesforce.com/it/content/learn/modules/salesforce-lightning-design-system-2-for-developers/explore-salesforce-lightning-design-system-2))