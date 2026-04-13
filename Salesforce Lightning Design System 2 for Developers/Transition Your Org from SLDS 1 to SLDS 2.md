# Transition Your Org from SLDS 1 to SLDS 2 (Developer Path)
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2

## EN (A-level: rewritten better; practical steps + exact tooling commands)

### Time Estimate / Topics
**~5 mins**  
Topics on the page:
- Learning Objectives
- Your SLDS 2 Transition
- Transition Tasks for You: Assess Your Code and Uplift to SLDS 2
- Onward and Upward
- Resources ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

---

## Learning Objectives
After completing this unit, you’ll be able to:
- List the SLDS 2 transition tasks for developers.
- List your admin’s and designer’s SLDS 2 transition tasks.
- Discuss how to set up a test org, SLDS Linter, SLDS Validator, and SARIF Viewer to audit your design code. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

---

## Your SLDS 2 Transition (big picture)
- The uplift from SLDS 1 → SLDS 2 is presented as “straightforward,” but effort depends on how many custom components you have.
- Trailhead notes this is a significantly lighter transition than Classic → Lightning. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Team roles (who does what)
**Designer tasks**
- Validate visual consistency across the UI.
- Use Figma kits to update designs.
- Support testing custom components for unexpected visual behavior. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

**Admin tasks**
- Coordinate the overall uplift project (go-live coordination is referenced as an admin-led activity). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

---

## Transition Tasks for You: Assess Your Code and Uplift to SLDS 2
Trailhead gives this high-level process:
1) Set up a dev environment and assess org readiness.
2) Analyze code using SLDS Linter or SLDS Validator + Figma kits.
3) Update components to comply with SLDS 2.
4) Test in your dev environment.
5) Redeploy and launch the new org version. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

---

## Step 1: Set Up Your Development Environment (test org requirements + enablement)
### Minimum requirements for the test org
- Minimum Salesforce version: **Winter ’25**
- Supported browsers: latest Chrome, Firefox, Safari, Edge ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Enable SLDS 2 (Salesforce Cosmos) if needed
Trailhead steps:
1) Setup → Setup
2) (Starter orgs) Open Advanced Setup
3) Quick Find → Themes and Branding
4) On Salesforce Cosmos theme dropdown → Activate ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

---

## Step 2A: Analyze Your Code Using SLDS Linter (recommended)
Trailhead recommends SLDS Linter due to automation and robust rule sets. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Prereqs
- Install VS Code
- (Optional) install SARIF Viewer VS Code extension
- Install Node.js (minimum supported **v18.4.0**, recommended latest Active LTS) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Run SLDS Linter (exact commands shown)
From your project root in VS Code terminal:

**Lint**
```bash
npx @salesforce-ux/slds-linter@latest lint
```

**Generate a SARIF report**
```bash
npx @salesforce-ux/slds-linter report
```
Output: `slds-linter-report.sarif`

**Auto-fix in bulk**
```bash
npx @salesforce-ux/slds-linter@latest lint --fix
```

**Revalidate**
```bash
npx @salesforce-ux/slds-linter@latest lint
``` ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

---

## Step 2B: Analyze Your Code Using SLDS Validator (alternative)
Trailhead still recommends SLDS Linter, but provides Validator steps. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Setup
- VS Code v1.26+
- Salesforce Extension Pack (includes SLDS Validator)
- JDK setup (via referenced instructions)
- SARIF Viewer extension (needed for bulk reporting output) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Generate a SARIF report (flow)
In VS Code:
- Command Palette → **SLDS: Generate Sarif Report**
- Select folders + output directory
- Open SARIF file in viewer ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

Validator report includes:
- component-level issues
- CSS class violations
- token → styling hook guidance (subject to change)
- accessibility concerns
- location + description + recommended fixes + severity ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

---

## Step 3: Update + Test (iterative uplift loop)
Trailhead’s iterative guidance:
1) Use Linter/Validator recommendations.
2) Use the “Get Started: Developers” guide for CSS update guidance.
3) Use Figma kits (Components for Web + Style Guide kits).
4) Test via functional validation + visual regression + (if applicable) cross-environment testing. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

---

## Go Live (developer checklist)
Trailhead’s go-live steps:
1) Revalidate updated code with SLDS Linter/Validator.
2) Visual regression test (designer can help).
3) Update docs/training (admin can help).
4) Communicate to customers (release notes/blog posts); coordinate with admin.
- Share post-release feedback in the Design Trailblazers community. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

---

## VI (A-level: viết lại tốt hơn; theo đúng Topics + có “how-to” rõ ràng)

### Thời lượng / Topics
~5 phút:
- Learning Objectives
- Your SLDS 2 Transition
- Transition Tasks for You
- Onward and Upward
- Resources ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Learning Objectives
- Liệt kê tasks chuyển SLDS 1 → SLDS 2 cho developer.
- Liệt kê tasks của admin và designer.
- Biết cách set up test org + SLDS Linter/Validator + SARIF Viewer để audit code. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Vai trò team
- Designer: validate visual consistency, dùng Figma kits, hỗ trợ test visual behavior. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))  
- Admin: điều phối uplift project. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Quy trình uplift (developer)
1) Setup env + assess readiness  
2) Audit bằng SLDS Linter/Validator + Figma kits  
3) Update code theo SLDS 2  
4) Test  
5) Redeploy + go live ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Setup test org + bật Cosmos nếu cần
- Yêu cầu: Salesforce Winter ’25+, browsers mới nhất. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))  
- Bật SLDS 2 qua Themes and Branding → Activate Salesforce Cosmos. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### SLDS Linter (khuyến nghị) — commands
- `npx @salesforce-ux/slds-linter@latest lint`
- `npx @salesforce-ux/slds-linter report` → `slds-linter-report.sarif`
- `npx @salesforce-ux/slds-linter@latest lint --fix`
- chạy lại `lint` để xác nhận hết violations ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### SLDS Validator (tuỳ chọn)
- VS Code + Salesforce Extension Pack + JDK + SARIF Viewer.
- Command Palette → SLDS: Generate Sarif Report; xem issues + recommended fixes + severity. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))

### Go live
- revalidate + visual regression + update tài liệu + truyền thông; share feedback trong Design Trailblazers. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-lightning-design-system-2-for-developers/transition-your-org-from-slds-1-to-slds-2?trail_id=get-started-with-slds-2))