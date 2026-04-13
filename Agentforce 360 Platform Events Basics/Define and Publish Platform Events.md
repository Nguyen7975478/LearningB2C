# Define and Publish Platform Events
https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_define_publish?trailmix_creator_id=strailhead&trailmix_slug=prepare-for-your-salesforce-platform-developer-i-credential

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Define a platform event.
- Add custom fields to the event definition.
- Publish platform event messages from Salesforce and from external apps.

## What you’re defining (platform event = schema + message instances)
- A **platform event** is a message type with a predefined schema.
- You define:
  - the event name (Label/API Name),
  - and fields (payload shape).
- An **event message** is a published instance of that event schema.

## Example used in the unit: Cloud News (why this example matters)
Trailhead uses a “Cloud News agency” story so you understand:
- events are “news updates” that many subscribers can consume,
- urgency matters (`Urgent__c`),
- and payload fields can carry human text (`News_Content__c`) and metadata (`Location__c`). ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

## Define a platform event (Setup steps)
The unit’s step sequence for defining **Cloud News**:

1) Setup → Quick Find: **Platform Events** → Platform Events
2) Click **New Platform Event**
3) Label: `Cloud News`
4) Plural Label: `Cloud News`
5) Description: `Cloud news events deliver news at your fingertips`
6) **Publish Behavior**: keep default **Publish Immediately**
7) Click **Save**
8) In **Custom Fields & Relationships**, click **New**
9) Add fields:
  - `Location` (Text, length `100`)
  - `Urgent` (Checkbox)
  - `News Content` (Text Area (Long)) ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

## Supported field types (important constraint)
The unit lists supported field types including:
- Text
- Checkbox
- Text Area (Long)
- Date
- Date/Time
- Number ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

Why this matters:
- Event payload design must fit within supported types.

## Publish Behavior and transactions (the “when will subscribers see it?” idea)
The unit explains there are two publish behaviors:

### Publish Immediately
- Default and recommended for most implementations.
- Event is published when the publish call runs, **regardless of whether the transaction succeeds**.
- Risk/behavior to understand:
  - a subscriber can receive the event before related data is committed. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

Use this when:
- publisher and subscribers are independent, or
- the event is used for logging/auditing-like scenarios. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

### Publish After Commit
- Publish only after the transaction commits successfully.
- If the transaction fails, the event is not published. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

Use this when:
- subscribers require committed transaction data to exist when they react (example: subscriber expects a Task record created in the same transaction). ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

## Publish platform event messages (3 publishing paths)
### 1) Publish with Apex (Salesforce)
- Create an instance of the platform event (example: `Cloud_News__e`) and call:
  - `EventBus.publish()`
- `EventBus.publish()` returns `Database.SaveResult`:
  - If `isSuccess()` is `true`, the publish request is queued and the event is published asynchronously.
  - If `isSuccess()` is `false`, errors are returned in `Database.Error`.
  - Publish failure does **not** throw an exception by default; you must inspect the result. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

### 2) Publish with clicks (Flow Builder)
- Publish without code by using **Flow Builder** record-create capability:
  - create an instance of the platform event object (for example `Cloud_News__e`)
- Example detail in unit:
  - to set a boolean field like `Urgent__c`, use `{!$GlobalConstant.True}`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

### 3) Publish from external apps (APIs)
- External apps can publish using Salesforce APIs, including:
  - **Pub/Sub API**
  - data APIs (examples mentioned: **REST API**, **SOAP API**, **Bulk API**) ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

## “How to think about reliability” (practical checklist)
To avoid silent failures:
- Always check `Database.SaveResult.isSuccess()`.
- If false, log/handle `Database.Error`.
- Choose Publish Behavior based on whether subscribers require committed data.

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Định nghĩa platform event.
- Thêm custom fields vào event definition.
- Publish platform event messages từ Salesforce và external apps.

## Bạn đang “define” gì (platform event = schema + message instances)
- **Platform event** là message type có schema.
- Bạn define:
  - event name (Label/API Name),
  - fields (payload).
- **Event message** là 1 instance được publish theo schema đó.

## Ví dụ Cloud News (vì sao dùng ví dụ này)
Ví dụ “Cloud News agency” giúp hiểu:
- event giống như “bản tin” nhiều subscriber nhận,
- có urgency (`Urgent__c`),
- và payload có text (`News_Content__c`) + metadata (`Location__c`). ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

## Define platform event (Setup steps)
Theo unit (Cloud News):
1) Setup → Platform Events
2) New Platform Event
3) Label/Plural Label: `Cloud News`
4) Description: `Cloud news events deliver news at your fingertips`
5) **Publish Behavior**: mặc định **Publish Immediately**
6) Save
7) Custom Fields & Relationships → New:
  - `Location` (Text, length 100)
  - `Urgent` (Checkbox)
  - `News Content` (Text Area (Long)) ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

## Supported field types (constraint quan trọng)
- Text, Checkbox, Text Area (Long), Date, Date/Time, Number. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

## Publish Behavior và transactions (hiểu “khi nào subscriber thấy event”)
### Publish Immediately
- Default, thường khuyến nghị.
- Publish ngay khi gọi, **bất kể transaction commit hay fail**.
- Có thể subscriber nhận event trước khi data commit. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

### Publish After Commit
- Chỉ publish sau khi commit thành công; fail thì không publish. ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))
- Dùng khi subscriber cần data đã commit (ví dụ cần Task record tồn tại). ([trailhead.salesforce.com](https://trailhead.salesforce.com/pt-BR/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

## Publish event messages (3 đường)
### 1) Apex (Salesforce)
- Tạo `Cloud_News__e` và gọi `EventBus.publish()`.
- Trả `Database.SaveResult`:
  - `isSuccess()` true: queued và publish async
  - false: lỗi trong `Database.Error`
  - không tự throw exception → phải kiểm tra kết quả ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

### 2) Clicks (Flow Builder)
- Dùng Flow tạo record event (`Cloud_News__e`).
- Set boolean `Urgent__c` bằng `{!$GlobalConstant.True}`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

### 3) External apps (APIs)
- Publish bằng **Pub/Sub API** hoặc data APIs như **REST API**, **SOAP API**, **Bulk API**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/fr/content/learn/modules/platform_events_basics/platform_events_define_publish?utm_source=openai))

## Checklist thực hành
- Luôn check `SaveResult.isSuccess()`.
- Chọn Publish Behavior theo nhu cầu commit-data của subscriber.