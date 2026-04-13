# Subscribe to Platform Events
https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?trailmix_creator_id=strailhead&trailmix_slug=prepare-for-your-salesforce-platform-developer-i-credential

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Describe how to subscribe to platform event messages.
- Subscribe to an event on the platform and in external apps.
- Test platform events in an Apex test method.

## Subscription options (what “subscribe” can mean on Salesforce)
The unit lists subscription mechanisms:

### On the Salesforce Platform
- **Apex triggers**
- **processes**
- **flows**
- `empApi` Lightning component ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### In external apps
- **Pub/Sub API** ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

How to choose:
- If your consumer logic runs in Salesforce server-side → triggers/flows/processes.
- If your consumer logic runs in a UI → `empApi`.
- If your consumer runs outside Salesforce → Pub/Sub API.

## Subscribe with Apex triggers (the most common server-side pattern)
### Only “after insert” triggers are supported
- Platform events support **only after insert triggers**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))
  Meaning:
- Your trigger runs after the event message is published.

### Autosubscription (why triggers feel simple)
- Triggers provide an **autosubscription mechanism**:
  - you don’t create a channel listener manually.
  - triggers receive event notifications whether events were published through Apex or APIs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### Create a platform event trigger (unit steps)
1) Developer Console → File | New | Apex Trigger
2) Provide a name and choose the platform event sObject
3) Submit (template includes `after insert`) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

Alternative noted:
- Create trigger from the platform event definition page (Setup → Triggers related list), but you still must specify `after insert`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Debug logging (the “why don’t I see logs?” issue)
### Triggers run in a separate process
- Platform event triggers do **not** execute in the same Apex transaction as the publisher.
- They run asynchronously in their own process under the **Automated Process** system user. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### How to capture logs (unit steps)
To debug, you add a Debug Log trace flag for **Automated Process**:
1) Setup → Debug Logs
2) New
3) Traced Entity Type: **Automated Process**
4) Set start/expiration dates
5) Choose Debug Level (or create one)
6) Save ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

Important note:
- Debug logs for **Apex tests** are an exception: they include logging for event triggers in the same test execution log. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Things to note about platform event triggers (behavior you must internalize)
### 1) Order of event processing (replay ID)
- Triggers process events sequentially in the order received.
- Ordering is based on the **event replay ID**.
- A trigger can receive a **batch** of events at once:
  - order preserved within the batch,
  - batch can include events from multiple publishers. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### 2) Asynchronous execution (no immediate side effects)
- Because trigger runs asynchronously:
  - there can be a delay between publish and processing,
  - don’t expect results immediately after publishing. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### 3) Running user context (Automated Process)
- Trigger runs as **Automated Process**, not the publishing user.
- Therefore, if your downstream records need user context, set fields explicitly (the unit mentions setting an owner ID explicitly in its example). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Testing Platform Events (Apex test pattern)
- When testing platform event publishing and trigger side effects:
  - wrap publish calls in `Test.startTest()` and `Test.stopTest()`.
- `Test.stopTest()` causes asynchronous publish/trigger processing to occur in test context. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Subscribe using clicks (Flow patterns)
### Platform event–triggered flow
- Start a flow when a platform event message is received.
- In the Start element, choose the platform event object.
- Access event fields via `$Record`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### Pause element (resume a paused flow)
- A platform event can resume a paused flow interview (Pause element).
- You can resume only when event fields match a condition. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Subscribe with Pub/Sub API (external clients) (how it behaves)
The unit highlights Pub/Sub API characteristics:
- Single interface for publishing, subscribing, and schema retrieval.
- Based on gRPC and HTTP/2; high-performance streaming with compression.
- Uses a **pull subscription model**:
  - the client requests N events based on processing capacity (flow control),
  - avoids overwhelming the client during spikes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))
- Event payload uses **Apache Avro** format. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Mô tả cách subscribe platform event messages.
- Subscribe event trên platform và trong external apps.
- Test platform events trong Apex test method.

## Subscription options (subscribe bằng gì)
### Trên Salesforce Platform
- **Apex triggers**
- **processes**
- **flows**
- `empApi` Lightning component ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### External apps
- **Pub/Sub API** ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

Cách chọn:
- Logic server-side trong Salesforce → triggers/flows/processes.
- UI subscribe → `empApi`.
- External consumer → Pub/Sub API.

## Subscribe bằng Apex triggers (pattern server-side phổ biến)
### Chỉ hỗ trợ after insert
- Platform events chỉ hỗ trợ **after insert triggers**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))
  Ý nghĩa:
- Trigger chạy sau khi event message được publish.

### Autosubscription
- Trigger là cơ chế **autosubscription**:
  - không cần tự tạo channel listener,
  - nhận events dù publish từ Apex hay APIs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### Tạo trigger (unit)
- Developer Console → New Apex Trigger → chọn event sObject → template có `after insert`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))
- Có thể tạo từ Setup event definition → Triggers related list nhưng vẫn phải `after insert`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Debug logging (vì sao khó thấy log)
- Trigger chạy async, không nằm trong transaction publish, chạy dưới user **Automated Process**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))
- Muốn log: Setup → Debug Logs → trace flag cho **Automated Process**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))
- Note: Apex tests là ngoại lệ (log nằm chung test execution log). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Trigger behavior cần nắm
- Thứ tự xử lý dựa trên **event replay ID**, có thể nhận **batch**, giữ thứ tự trong batch. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))
- Async: có delay, không mong kết quả có ngay. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))
- Running user: **Automated Process**, không phải user publish → cần set fields rõ ràng nếu cần context. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Test Platform Events (Apex)
- Publish trong test phải bọc `Test.startTest()` / `Test.stopTest()`.
- `Test.stopTest()` mới làm phần async publish/trigger chạy trong test. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Subscribe bằng clicks (Flow)
- Platform event–triggered flow: Start element chọn event object; dùng `$Record`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))
- Pause element: event đến thì resume flow nếu match điều kiện. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

## Pub/Sub API (external) (cách hoạt động)
- Một API cho publish/subscribe/schema.
- gRPC + HTTP/2 + compression; payload **Apache Avro**.
- **Pull subscription model**: client chủ động request N events theo khả năng xử lý (flow control), tránh bị overwhelm khi spike. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))