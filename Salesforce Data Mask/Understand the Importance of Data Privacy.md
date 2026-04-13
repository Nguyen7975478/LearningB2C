# Understand the Importance of Data Privacy
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy

## EN (A-level: detailed; follows the unit Topics)

### Time Estimate / Topics
Topics on the page:
- Learning Objectives
- Why Secure Sandbox Data?
- The Challenge of Securing Sandbox Data
- Secure Sandbox Data with Salesforce Data Mask ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

---

## Learning Objectives
After completing this unit, you’ll be able to:
- Identify the different types of sensitive data.
- Understand the importance of securing sandbox data.
- Explain the options available to admins for securing sandbox data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

---

## Why Secure Sandbox Data?
- Salesforce’s stated priority: **Trust** is the number one value, and data security has been prioritized from the start to meet changing regulatory and customer requirements. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))
- Regulations highlighted that require strong privacy and security practices:
    - **GDPR** (EU General Data Protection Regulation)
    - **CCPA** (California Consumer Privacy Act)
    - plus industry-specific regulations like:
        - **PCI DSS**
        - **HIPAA (1996)** ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))
- Consequences of noncompliance/data breaches (as the unit states):
    - loss of customer trust
    - severe financial/legal consequences
    - example fines mentioned: **$5,000–$100,000 per month** until compliance
    - GDPR can be up to **4% of annual global revenues** or **$20M**, whichever is greater. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

### Why sandboxes are a risk (core point)
- Production is usually scrutinized continuously, but sandboxes may be lower priority because they’re “only” for dev/test.
- However, developers/contractors working in sandboxes could access data that would normally be restricted in production. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

### Scenario in the unit (healthcare contractor)
- A healthcare developer hires a contractor to build a custom object in a sandbox (tracking patient satisfaction survey results).
- The developer choices described:
    - manually remove sensitive data, or
    - tightly monitor/control access to sensitive fields
- The unit concludes: neither approach is efficient nor likely to guarantee data security. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

**Tip: masking vs encryption**
- Data masking: prevents users from viewing sensitive data in UI or exporting it as plain text.
- Data encryption: prevents malicious attackers from accessing/interacting with sensitive data **at rest** in the data center. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

---

## The Challenge of Securing Sandbox Data
- Sandboxes can contain **PI (personal information)** and **PII (personally identifiable information)**.
- Examples listed include: names, phone numbers, emails, addresses, Social Security numbers, credit card/banking details, compensation info, “general secrets,” and more. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))
- Because sandboxes are used for dev/test, a larger group of people (developers, employees, contractors) might need access compared to production.
- Sandbox data privacy is often an afterthought; implementing controls can be time-consuming and difficult. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))
- Without dedicated tooling:
    - admins and developers spend significant time/resources securing full and partial sandboxes,
    - to ensure sensitive production data stays controlled as it’s replicated into sandboxes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

---

## Secure Sandbox Data with Salesforce Data Mask
- Salesforce **Data Mask** is introduced as a resource for admins and developers to mask sensitive data in sandboxes.
- The unit defers “how it works” details to the next unit. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

---

## VI (A-level: chi tiết; bám sát Topics)

### Thời lượng / Topics
- Learning Objectives
- Why Secure Sandbox Data?
- The Challenge of Securing Sandbox Data
- Secure Sandbox Data with Salesforce Data Mask ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

### Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Nhận diện các loại dữ liệu nhạy cảm.
- Hiểu vì sao cần bảo mật dữ liệu trong sandbox.
- Giải thích các lựa chọn mà admin có để bảo mật dữ liệu sandbox. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

### Why Secure Sandbox Data?
- Salesforce nhấn mạnh **Trust** là giá trị số 1; data security được ưu tiên để đáp ứng yêu cầu regulatory + khách hàng. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))
- Các regulation được nêu:
    - **GDPR**, **CCPA**
    - theo ngành: **PCI DSS**, **HIPAA (1996)** ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))
- Hậu quả không tuân thủ / bị breach:
    - mất trust, rủi ro pháp lý/tài chính
    - ví dụ fines: **$5,000–$100,000/tháng** đến khi compliance
    - GDPR có thể tới **4% doanh thu toàn cầu** hoặc **$20M** (lấy mức lớn hơn). ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

**Vì sao sandbox rủi ro**
- Production thường bị kiểm tra liên tục; sandbox đôi khi bị xem nhẹ vì chỉ phục vụ dev/test.
- Nhưng dev/contractor làm trong sandbox có thể truy cập dữ liệu vốn bị hạn chế ở production. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

**Scenario healthcare**
- Dev thuê contractor build custom object trong sandbox (patient satisfaction survey results).
- Hai lựa chọn: xóa data nhạy cảm thủ công hoặc kiểm soát quyền truy cập cực chặt.
- Unit kết luận: không hiệu quả và khó đảm bảo an toàn dữ liệu. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

**Tip: masking vs encryption**
- Masking: ngăn user xem/extract plain text trong UI/export.
- Encryption: bảo vệ dữ liệu **at rest** khỏi attacker. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

### The Challenge of Securing Sandbox Data
- Sandbox có thể chứa **PI/PII**: names/phone/email/address/SSN/credit card/banking/compensation/general secrets…
- Sandbox cần nhiều người truy cập hơn production → privacy quản lý khó, hay bị xem là “afterthought”.
- Không có tooling chuyên biệt → admin/dev tốn nhiều time/cost để bảo vệ full/partial sandboxes khi dữ liệu được replicate từ production. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))

### Secure Sandbox Data with Salesforce Data Mask
- Giới thiệu **Salesforce Data Mask** là công cụ giúp mask data nhạy cảm trong sandbox; chi tiết cách làm nằm ở unit tiếp theo. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/salesforce-data-mask/understand-the-importance-of-data-privacy))