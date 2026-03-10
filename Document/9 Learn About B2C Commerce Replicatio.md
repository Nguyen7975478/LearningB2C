# cc-digital-replication — Learn About B2C Commerce Replication
https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication

---

## English (Detailed summary — keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Describe the **process flow between instances**.
- List three types of data you can replicate.
- List two differences between the **import and export** and **replication** processes.
- Describe two ways to control replication.
- Explain the benefit of **replication tasks**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Introduction: what replication is (and where it runs)
- Salesforce B2C Commerce uses **replication** to move **data and code** from a **staging instance** to a **development** or **production** instance.
- This is a controlled process that reduces errors during transfer.
- Replication only happens on instances in the **Primary Instance Group (PIG)**, not on **SIG** / **sandboxes**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Source and Target (process flow)
- Replication pushes changes from a **replication source** to a **replication target**.
- The **source is always the staging instance**.
- The target can be **development** or **production**.
- Main goal: **staging → production**; recommended preliminary step: replicate the same changes to **development** first to verify success. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Replication Control (replication process + replication tasks)
- In **Business Manager**, you create a **replication process**.
- A replication process is a collection of **replication tasks** that specify changes since the last replication.
- Changes can include **data** (for example, product data, content, image files) or **code**.
- You can define multiple replication processes and choose tasks to control **granularity** (entire site vs a subset such as **custom objects**). Organization-level changes have similar flexibility.
- Schedule start/end during low-traffic periods to avoid impacting storefront performance. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Two-Step Publishing (Transfer → Publish)
- **Two-step publishing** helps avoid running the whole process only to fail at the end:
    1) **Transfer**: create replication and select **Transfer** as the replication type; if it fails, fix and retry.
    2) **Publish**: after transfer succeeds, create a second task (**Data Publish**) to publish the data.
- For **data replication**, the transferred data must match the published tasks data (you can’t transfer catalog/index/promotion and then publish only catalog). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Data Replication behavior (replace, not merge) + granularity
- Replication is a **replace** operation, not a **merge**.
- It first copies source data to a new location on the target, preserving original data; then switches the target to the new data set (effectively replacing the data).
- Later replications can be more granular (for example, replicate individual sites and associated catalogs: all catalogs, one catalog, or product catalog). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Selecting Data to Replicate (organization scope vs site scope) + limitations
- B2C Commerce data can be **organization scope** (shared across all sites) or **site scope** (used only by one site).
- Within each scope, you can replicate different datasets (for example, organization catalogs; site promotions/coupons). This is the lowest granularity supported at the dataset level.
- You cannot replicate a single product or a single promotion inside a dataset.
- Data replication does **not** copy from staging:
    - **Orders**
    - **Inventory lists**
    - **Business Manager user profiles and login credentials** ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Schedule Data Replication (4 ways) + cautions
You can schedule replication four ways:
- **Automatic** (at a specified date/time, by default, or immediately after defining the process)
- **Manual** (started by a user with permissions in Business Manager)
- **Recurring** (daily/weekly/monthly)
- **Job Step** (triggered by a job)

Cautions:
- If a recurring data replication fails, subsequent repetitions don’t run.
- Replication usually clears the **page cache**, which can dramatically impact storefront performance. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Best Practices
- Test replication **staging → development** first, then test resulting config on development.
- Always run **transfer** followed by **publish** to verify transfer results.
- Identify dependencies between replication groups.
- Always replicate **search indexes** with **catalogs**.
- Transfer to production during minimal activity.
- Turn off incremental/scheduled indexing and stop other jobs while replicating (turn them off before publish); you can replicate the search index or manually build it on the target.
- Avoid major replications during standard maintenance windows.
- Use Business Manager permissions to limit who can replicate. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Code Replication (code version concepts)
- **Code replication** replicates a **code version** (a folder containing custom cartridges) between source and target.
- An instance can have multiple code versions, but only one is **active**.
- After developing in sandbox, upload code to staging (secure connection).
- On production, the system creates a new version named using the original name + timestamp; you can replicate code without activating, or activate during replication; rollback reactivates the previously active version.
- Recommended production flow:
    1) Deploy code version on staging
    2) Replicate code (and data) to development to test
    3) Replicate code to production ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Replication Types (code)
- **Code transfer**: transfers the currently activated code version; always creates a new code version on target; does not synchronize like data replication.
- **Code transfer and publishing**: transfer then immediate activation.
- **Code publishing**: no transfer; activates the previously transferred version (only available if the previous type was code transfer).
- **Code undo**: rolls back depending on prior process; fails if no rollback target exists. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Email Notification
- Configure email notifications for code replications via a comma-delimited recipient list.
- Email is sent after finish/failure; if the process hangs, email isn’t sent. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Replication Groups (tasks)
- Replication groups (tasks) organize replicated data/processes; you can replicate at **site level**, **organization level**, or both (for example, custom objects at both levels).
- Business Manager groups replicated objects—review object relationships to understand complexity. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Replication vs Import/Export
- Use both to populate instance databases:
    - After code/data is in B2C Commerce, **replication** moves it between instances.
    - **Import and export** moves data to/from external systems and a B2C Commerce database. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

---

## Tiếng Việt (Tóm tắt chi tiết — giữ nguyên thuật ngữ)

### Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả **process flow between instances**.
- Liệt kê 3 loại dữ liệu có thể replicate.
- Nêu 2 điểm khác nhau giữa **import and export** và **replication**.
- Mô tả 2 cách control replication.
- Giải thích lợi ích của **replication tasks**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Replication là gì (và chạy ở đâu)
- Salesforce B2C Commerce dùng **replication** để chuyển **data và code** từ **staging instance** sang **development** hoặc **production** instance.
- Đây là quy trình có kiểm soát để giảm lỗi khi transfer.
- Replication chỉ diễn ra trên **PIG (Primary Instance Group)**, không chạy trên **SIG** / **sandboxes**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Source và Target
- Replication đẩy thay đổi từ **replication source** sang **replication target**.
- **Source luôn là staging instance**.
- Target có thể là **development** hoặc **production**.
- Mục tiêu chính: **staging → production**; bước khuyến nghị trước: replicate sang **development** để verify. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Replication Control (replication process + replication tasks)
- Tạo **replication process** trong **Business Manager**.
- Replication process là tập các **replication tasks** mô tả thay đổi kể từ lần replicate trước.
- Thay đổi có thể là **data** (product data, content, image files) hoặc **code**.
- Có thể tạo nhiều replication processes và chọn tasks để điều khiển **granularity** (đẩy cả site hoặc subset như **custom objects**). Tương tự cho organization-level changes.
- Nên schedule vào giờ ít traffic để tránh ảnh hưởng performance/shopper experience. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Two-Step Publishing (Transfer → Publish)
- **Two-step publishing** giúp tránh chạy toàn bộ rồi fail:
    1) **Transfer**: tạo replication, chọn Transfer; fail thì sửa rồi chạy lại.
    2) **Publish**: transfer OK thì tạo task **Data Publish** để publish data.
- Với **data replication**, dữ liệu transfer phải khớp với dữ liệu publish (không thể transfer catalog/index/promotion rồi publish chỉ catalog). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Data Replication (replace, not merge) + granularity
- Replication là **replace operation**, không phải **merge**.
- Copy data sang vị trí mới trên target (giữ dữ liệu cũ), rồi switch sang data mới (thực chất replace).
- Các lần sau có thể replicate granular hơn (theo site và catalogs: all catalogs / one catalog / product catalog). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Selecting Data to Replicate (organization scope vs site scope) + limitations
- Data có thể thuộc **organization scope** (shared) hoặc **site scope** (chỉ 1 site dùng).
- Trong mỗi scope, có thể chọn dataset để replicate (organization catalogs; site promotions/coupons…)—đây là mức granularity thấp nhất.
- Không replicate được “một product” hay “một promotion” riêng lẻ trong dataset.
- Data replication **không copy** các object sau từ staging:
    - **Orders**
    - **Inventory lists**
    - **Business Manager user profiles and login credentials** ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Schedule Data Replication (4 cách) + cảnh báo
- **Automatic**, **Manual**, **Recurring**, **Job Step**.
- Lưu ý: recurring fail thì các lần chạy sau không chạy; replication thường clear **page cache** và có thể ảnh hưởng mạnh đến performance storefront. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Best Practices
- Test staging → development trước; test config trên development.
- Luôn chạy **transfer** rồi **publish**.
- Xác định dependencies giữa replication groups.
- Replicate **search indexes** cùng **catalogs**.
- Transfer lên production khi ít hoạt động.
- Tắt incremental/scheduled indexing và dừng jobs khác khi replicate; tắt trước publish; có thể replicate search index hoặc build thủ công.
- Tránh major replication trong maintenance windows.
- Giới hạn quyền replication bằng Business Manager permissions. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Code Replication (code version)
- Code replication replicate **code version** (folder chứa custom cartridges).
- Một instance có nhiều code versions nhưng chỉ một version **active**.
- Upload code lên staging (secure connection) trước khi replicate.
- Production tự tạo version mới (kèm timestamp); có thể replicate không activate hoặc activate ngay; rollback sẽ re-activate version trước đó.
- Flow khuyến nghị:
    1) Deploy code version on staging
    2) Replicate code (and data) to development để test
    3) Replicate code to production ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Replication Types (code)
- **Code transfer**, **Code transfer and publishing**, **Code publishing**, **Code undo**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))

### Email Notification + Replication Groups + Replication vs Import/Export
- Email notification cho code replication cấu hình bằng list email; gửi sau finish/fail; nếu hang thì không gửi.
- **Replication groups/tasks** dùng để tổ chức data/process; có thể replicate site level / organization level / cả hai.
- Replication dùng để chuyển code/data giữa instances; **import/export** dùng để chuyển data giữa external systems và B2C Commerce database. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/architecture-of-commerce-cloud-digital/cc-digital-replication))