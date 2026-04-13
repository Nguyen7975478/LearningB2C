# Install and Configure Salesforce Data Mask
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask

## EN (A-level: detailed; follows unit Topics)

### Time Estimate / Topics
Topics on the page:
- Install the Data Mask Managed Package
- Configure Data Mask
- Select the Data to Mask
- Run the Data Mask in Your Sandbox
- Conclusion
- Resources ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

---

## Learning Objectives
After completing this unit, you’ll understand:
- How to install Data Mask.
- How the Data Mask configuration options impact the sandbox data.
- How to run a masking job in your sandbox. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

---

## Install the Data Mask Managed Package
- To install and use Data Mask in production, you must enable certain features and specify user permissions (the unit points to Salesforce Help for details).
- Then install via the standard managed package installation process.
- After installation, Salesforce automatically upgrades the package with new features and bug fixes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

---

## Configure Data Mask
- After installing in production, launch Data Mask.
- You can select a saved masking configuration or start from scratch.
- Two configuration approaches:
    1) Configure in **production** → when a sandbox is created/refreshed, the configuration appears in the sandbox.
    2) Configure directly in an **existing sandbox**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))
- General setup fields:
    - mask name
    - API name
    - description
- Optional actions in general config:
    - mask case comments
    - delete all emails and Chatter feeds ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

---

## Select the Data to Mask
- After general options, choose which data to mask.
- From the list of standard/custom objects in production, select all objects containing sensitive data.
- For each selected object, configure rules for each field. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

### Masking rules available (as listed)
1) **Replace with Random Characters or Numbers**
- Replaces with random characters/numbers that are readable but not recognizable.
- If using random numbers, specify min/max for the field. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

2) **Replace from Library**
- Replaces with random but recognizable values chosen from libraries:
    - First Name, Last Name, Company Name, Email, Street, City, Country, Country (Abbr.), State, Postal Code, Phone Number, Social Security Number. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

3) **Delete**
- Deletes sensitive data entirely (empty data set). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

**Important limitation**
- Checkbox, lookup, and picklist field types aren’t supported. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

---

## Run the Data Mask in Your Sandbox
- When configuration is complete, you can mask sandbox data.
- Run the mask whenever you want to replace or delete sandbox data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

Steps (as listed):
1) In the sandbox, from the **Data Mask Home** tab, open the dropdown for the masking configuration and select **Run**.
2) Monitor progress by checking the status message in the list view for the running job.
3) Verify masking by manually spot-checking sandbox data; then you can grant more users access to the sandbox. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

Logs:
- Use the **Masking Execution Logs** tab to see more information about each job. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

---

## Conclusion
- With Data Mask installed and configured, you can meet security requirements by masking sensitive sandbox data.
- Result: users testing/developing in sandboxes don’t have access to sensitive data and the org better supports privacy compliance. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

---

## Resources
- Install the Data Mask Managed Package (Salesforce Help link from unit). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

---

## VI (A-level: chi tiết; bám sát Topics)

### Topics
- Install the Data Mask Managed Package
- Configure Data Mask
- Select the Data to Mask
- Run the Data Mask in Your Sandbox
- Conclusion
- Resources ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

### Learning Objectives
Sau khi hoàn thành unit, bạn hiểu:
- Cách cài Data Mask.
- Cách các tùy chọn cấu hình ảnh hưởng dữ liệu sandbox.
- Cách chạy masking job trong sandbox. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

### Install managed package
- Trước khi cài trên production cần enable features + set user permissions (tham chiếu Salesforce Help).
- Cài theo quy trình cài managed package.
- Salesforce tự động upgrade package (features/bug fixes). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

### Configure Data Mask
- Launch Data Mask → chọn config đã lưu hoặc tạo mới.
- 2 cách: config ở production (sandbox mới/refresh sẽ có), hoặc config trực tiếp trong sandbox.
- Cần name/API name/description; có option mask case comments hoặc xóa toàn bộ emails và Chatter feeds. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

### Select data + rules
- Chọn objects nhạy cảm; set rule theo field:
    - Random characters/numbers (number có min/max)
    - Replace from Library (First/Last/Company/Email/Address/Phone/SSN…)
    - Delete
- Limitation: không support checkbox/lookup/picklist. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))

### Run in sandbox
- Data Mask Home tab → dropdown config → Run; theo dõi status; spot-check để verify; xem thêm log ở Masking Execution Logs tab. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/install-and-configure-salesforce-data-mask))