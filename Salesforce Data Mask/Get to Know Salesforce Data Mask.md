# Get to Know Salesforce Data Mask
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask

## EN (A-level: detailed; follows the unit Topics)

### Time Estimate / Topics
Topics on the page:
- Learning Objectives
- How Does Data Mask Work?
- Make Your Data Random
- Replace Your Data with Familiar Values
- Delete Your Data
- Summary ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

---

## Learning Objectives
After completing this unit, you’ll be able to:
- Understand the definition of data obfuscation.
- Know the business cases for when to replace or delete data.
- Understand the risks of data deletion. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

---

## How Does Data Mask Work?
- Data Mask uses **platform-native obfuscation** to mask sensitive data in **full or partial** sandboxes.
- You can configure different masking levels depending on sensitivity. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

**Tip: what “data obfuscation” means (examples in unit)**
- Make it unreadable by replacing characters (example: `Blake` → `gB1ff95-$`).
- Or replace it with readable but unrelated values (example: `Kelsey` → `Amber`). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

**Packaging/licensing context**
- Data Mask is a **managed package** installed and configured in an **Unlimited or Enterprise** production org, along with purchase of Data Mask **User permission set licenses**.
- You run masking from any sandbox created from that production org. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

**Security property (important)**
- Uses **nondeterministic obfuscation** to prevent reverse engineering / statistical inference attacks from de-obfuscating masked data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

**Irreversibility + operational behavior**
- Once sandbox data is masked, you can’t unmask it.
- This does not affect production; if you need original data again, refresh from production and create a new sandbox.
- You can mask data sets as often as needed after configuration. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

---

## Make Your Data Random
- If you mark fields to replace with random characters, Data Mask transforms readable sensitive sandbox data into random data.
- Example transformation (Contact):
    - `Susan Badger, me@thebadger.com` → `vqiz olmmt, saljohnson@example.com`
- This lets business processes function while preserving confidentiality of production values. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

---

## Replace Your Data with Familiar Values
- Replacing using **library values** uses proprietary libraries embedded in the managed package to generate random but recognizable data.
- Example transformation:
    - `Nancy Simon, nan@see.com` → `Gregory Fitzpatrick, liza.perez@acmeautorepairandpaintz.com`
- Field types remain the same, so business processes depending on those types still work.
- You can recognize the type of data and make informed decisions using the random data, while sensitive production info remains confidential. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

---

## Delete Your Data
- If you mark fields for deletion, Data Mask transforms readable sensitive data into **empty sets**.
- Example: deleting a free-form text field “Manager Feedback” removes the sensitive text and leaves it blank.
- This is described as the most compute-efficient way to eliminate private data from a sandbox. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

**Warning (risk)**
- Deletion can reduce ability to test business processes.
- Deleted data can’t be restored in the sandbox.
- Production is unaffected; to restore, refresh from production and create a new sandbox. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

---

## Summary
- Data Mask supports different levels of masking:
    - replace with random characters
    - replace with similarly mapped words (library)
    - delete (eliminate)
- Goal: keep sensitive production data private when replicated in sandboxes, without conceding privacy/confidentiality. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

---

## VI (A-level: chi tiết; bám sát Topics)

### Thời lượng / Topics
- Learning Objectives
- How Does Data Mask Work?
- Make Your Data Random
- Replace Your Data with Familiar Values
- Delete Your Data
- Summary ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

### Learning Objectives
- Hiểu định nghĩa data obfuscation.
- Biết business case khi nào “replace” vs “delete” data.
- Hiểu rủi ro khi xóa dữ liệu. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

### How Does Data Mask Work?
- Data Mask dùng **platform-native obfuscation** để mask data nhạy cảm trong full/partial sandboxes; có thể cấu hình level theo độ nhạy. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))
- Data obfuscation:
    - thay ký tự thành không đọc được (`Blake` → `gB1ff95-$`),
    - hoặc thay bằng giá trị “đọc được nhưng không liên quan” (`Kelsey` → `Amber`). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))
- Data Mask là **managed package** cài trên production Unlimited/Enterprise + mua licenses; chạy mask từ sandbox tạo từ production đó. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))
- Dùng **nondeterministic obfuscation** để chống reverse engineering / statistical inference. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))
- Mask rồi **không unmask** được; production không bị ảnh hưởng; muốn data gốc thì refresh từ production và tạo sandbox mới; có thể chạy mask nhiều lần khi cần. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

### Make Your Data Random
- Replace random characters: biến data nhạy cảm thành random; ví dụ Contact `Susan Badger, me@thebadger.com` → `vqiz olmmt, saljohnson@example.com`.
- Giữ business process chạy được nhưng không lộ dữ liệu thật. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

### Replace Your Data with Familiar Values
- Replace từ library (proprietary) tạo random nhưng “recognizable”; ví dụ `Nancy Simon, nan@see.com` → `Gregory Fitzpatrick, ...@acme...`.
- Field types giữ nguyên nên process không hỏng; vẫn nhận ra loại dữ liệu để test/đánh giá. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

### Delete Your Data
- Delete: biến thành empty set; compute-efficient để bỏ dữ liệu private.
- Risk: có thể làm mất khả năng test một số process; đã delete thì không restore trong sandbox; production không ảnh hưởng (muốn restore thì refresh sandbox). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))

### Summary
- 3 mức: random / library / delete, mục tiêu bảo vệ dữ liệu production khi replicate sang sandbox. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/salesforce-data-mask/get-to-know-salesforce-data-mask))