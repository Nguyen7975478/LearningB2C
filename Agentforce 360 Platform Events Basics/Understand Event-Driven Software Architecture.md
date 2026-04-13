# Understand Event-Driven Software Architecture
https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_architecture?trailmix_creator_id=strailhead&trailmix_slug=prepare-for-your-salesforce-platform-developer-i-credential

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- List the components of event-based software architecture.
- Explain the benefits of an event-driven software architecture.
- Describe use cases for the **Platform Events** feature.
- Describe the characteristics of a platform event.

## Prerequisites (what Trailhead expects you to already know)
The unit suggests you be familiar with at least one of:
- **Apex**
- **REST API**
- **Flow**
- **Process**
  For the hands-on challenge in this module, you should also understand **Apex triggers**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

## Event-driven software architecture (EDA) (the “big idea”)
### Event-driven vs request-response (how the integration style changes)
- **Request-response**: a system calls another system and waits (or repeatedly polls) for a response.
- **Event-driven**: a system **publishes** an event when something happens; other systems **subscribe** and react when they receive it.

How to understand the “why”:
- With EDA, the producer does not need to know who will react.
- The consumer does not need to be called directly.
- This reduces tight coupling between services/apps.

### The publish-subscribe model (why “Pub/Sub” is central)
- EDA typically uses a **publish-subscribe (Pub/Sub)** model:
  - **Publishers** emit messages (“events”).
  - **Subscribers** receive those messages when they’re interested.
  - Many subscribers can consume the same event stream independently.

## Components of event-based architecture (what pieces exist)
To understand EDA, internalize these components:

### 1) Event (message)
- A statement that “something happened” (for example, “OrderShipped”, “ProductReturned”).
- In Platform Events, the event has a **predefined schema** (fields).

### 2) Producer / Publisher
- The system that creates and sends an event.
- In Salesforce, a publisher can be Apex or Flow; outside Salesforce it can be an external app using APIs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

### 3) Consumer / Subscriber
- The system that listens for and processes events.
- In Salesforce, subscribers can be triggers/flows/processes or UI via `empApi`. External apps typically use Pub/Sub API. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### 4) Event bus / Event channel
- Salesforce provides an event delivery infrastructure (often referred to as an **event bus**) that stores and delivers events.
- Key mental model:
  - publishers send events “to the bus”,
  - subscribers “read from the bus” (directly or indirectly via triggers/flows/empApi/PubSub).

## Benefits of EDA (why architects choose it)
The unit’s key benefit theme is flexibility:
- **Decoupling**: publishers and subscribers evolve independently.
- **Extensibility**: you can add new subscribers without changing the publisher.
- **Near real-time integration**: events flow quickly without polling.
- **Multiple consumers**: one event can drive many downstream actions.

## Platform Events (what they enable)
Platform Events are used when you want:
- Custom event data with a **predefined schema**
- Pub/Sub integration on and off the Salesforce Platform
- Flexibility in publishing and processing events both in Salesforce and externally ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

### Use cases (examples from the unit)
- Salesforce notifies external **order fulfillment** apps about shipment orders.
- External product systems notify Salesforce about **merchandise returns**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

### Important note: other streaming event types
- The unit notes **Change Data Capture** (CDC) is another type of streaming event for record create/update/delete/undelete changes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

## Using Platform Events in native vs external apps (how you choose the mechanism)
### Apps on the Salesforce Platform
- Publish using:
  - Apex
  - Flow Builder
- Subscribe using:
  - Apex trigger
  - `empApi` Lightning component ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

### External apps
- Publish using:
  - **Pub/Sub API** or **data APIs**
- Subscribe using:
  - **Pub/Sub API** ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

## Characteristics of a Platform Event (how to “think” about it)
A Platform Event is:
- A custom message type with a **schema** (fields).
- Used for notifying systems that something occurred.

How it differs from “records” (important conceptual distinction):
- You **publish** an event (a message), rather than “store and update” a record for UI use.
- Consumers react to the event message; they shouldn’t assume the producer is waiting for them.

---

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Liệt kê thành phần của kiến trúc event-based.
- Giải thích lợi ích của event-driven architecture.
- Mô tả use cases của **Platform Events**.
- Mô tả characteristics của platform event.

## Prerequisites (Trailhead mong bạn biết gì)
Unit gợi ý bạn nên biết ít nhất một trong:
- **Apex**, **REST API**, **Flow**, **Process**
  Và để làm hands-on trong module này, bạn nên biết **Apex triggers**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

## Event-driven software architecture (EDA) (ý chính cần nắm)
### Event-driven khác request-response thế nào
- **Request-response**: hệ thống gọi hệ thống khác và chờ (hoặc polling).
- **Event-driven**: hệ thống **publish** event khi có sự kiện; hệ thống khác **subscribe** để phản ứng.

Ý nghĩa (để hiểu “ý”):
- Publisher không cần biết ai sẽ phản ứng.
- Subscriber không cần bị gọi trực tiếp.
- Giảm coupling giữa systems.

### Pub/Sub model (vì sao quan trọng)
- **Publish-subscribe (Pub/Sub)**:
  - Publisher phát event message,
  - Subscriber nhận event message,
  - nhiều subscriber có thể nhận cùng một event stream.

## Các thành phần của kiến trúc event-based
### 1) Event (message)
- Thông điệp “đã xảy ra việc gì đó” (ví dụ OrderShipped, ProductReturned).
- Với Platform Events, event có **schema** (fields) rõ ràng.

### 2) Producer / Publisher
- Hệ thống tạo và publish event.
- Trong Salesforce: Apex hoặc Flow; ngoài Salesforce: external app qua APIs. ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

### 3) Consumer / Subscriber
- Hệ thống nhận và xử lý event.
- Trong Salesforce: triggers/flows/processes hoặc UI `empApi`; ngoài Salesforce: Pub/Sub API. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/platform_events_basics/platform_events_subscribe?utm_source=openai))

### 4) Event bus / channel
- Salesforce cung cấp hạ tầng phân phối event (event bus).
- Mental model:
  - publisher gửi “lên bus”,
  - subscriber đọc “từ bus”.

## Lợi ích của EDA
- **Decoupling**: publisher/subscriber độc lập.
- **Extensibility**: thêm subscriber không cần đổi publisher.
- **Near real-time**: giảm polling.
- **Một event, nhiều consumer**: nhiều hệ thống phản ứng độc lập.

## Platform Events dùng để làm gì
Dùng Platform Events khi bạn cần:
- custom event data với **predefined schema**
- Pub/Sub integration trong và ngoài Salesforce
- publish/process linh hoạt on-platform và off-platform ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

### Use cases (unit)
- Salesforce notify external **order fulfillment** apps.
- External systems notify Salesforce về **merchandise returns**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

### Note
- Unit nhắc **Change Data Capture** là streaming event cho record changes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

## Native vs external apps (chọn cơ chế)
- On-platform: publish bằng Apex/Flow; subscribe bằng Apex trigger hoặc `empApi`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))
- External: publish/subscribe bằng **Pub/Sub API** (publish cũng có thể qua data APIs). ([trailhead.salesforce.com](https://trailhead.salesforce.com/en/content/learn/modules/platform_events_basics/platform_events_architecture?utm_source=openai))

## Characteristics của Platform Event (cách hiểu)
- Platform Event là message type có **schema**.
- Bạn “publish message” để notify, không phải “lưu record rồi update” cho UI.
- Subscriber phản ứng theo message; publisher không chờ subscriber.