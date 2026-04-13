# Learn JavaScript Core Concepts
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts?trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level; faithful to unit Topics; keep technical terms)

### A Quick Disclaimer (unit note)
- This module assumes you already know JavaScript fundamentals (keywords, operators, basic syntax) but are still relatively new to the language.
- If you’re coming from a classical programming language (such as Apex) to JavaScript, the purpose is to understand the *what* and *why* of certain JavaScript features so you can write better code in **Lightning Web Components** or any JavaScript framework. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### Learning Objectives
After completing this unit, you'll be able to:
- Describe the nature of the JavaScript runtime environment.
- Distinguish between the JavaScript engine and the language.
- Avoid key pitfalls when learning JavaScript.
- Describe some important JavaScript best practices. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

---

## The What, Why, and How of JavaScript
- Early 2000s web apps: browsers were simple HTML renderers and standards were fragmented, often forcing use of a single browser (commonly Internet Explorer).
- Server-side UI frameworks evolved so complex logic ran on the server and rendered HTML was sent to the browser (JavaScript mainly did simple interactivity).
- Example Salesforce server-side framework: **Visualforce**; the unit notes millions of Visualforce pages exist.
- Modern web: browsers are powerful; JavaScript is standardized around **ECMAScript**; modern apps are often client-side rendered.
- On Salesforce, client-side rendering is done with the **Lightning Component Framework**—but many Salesforce developers need help “getting” JavaScript deeply. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

---

## The JavaScript Runtime
- The JavaScript runtime is an engine that interprets JavaScript code; it can be inside a browser or another environment (like a server).
- The defining feature: a **single-threaded** runtime.
- Work executes on the **stack**; new work waits in a **queue**.
- When the stack is empty, the **event loop** moves queued work into the stack.
- The unit notes this is a simplification but it explains the model that influences how JavaScript behaves. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

---

## JavaScript the Language
### JavaScript is changing
- JavaScript is built on the ECMAScript standard.
- The standard updates annually; engine vendors implement new features.
- Some features are “syntactic sugar” for existing behavior. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### Adoption of APIs is not universal
- Most APIs work broadly, but not every browser adopts every feature at the same rate.
- To use newer features, check compatibility (example resource: caniuse.com).
- When features aren’t available, developers may use **polyfills**.
- The Lightning Component Framework uses a curated list of polyfills applied before other code to improve compatibility. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

---

## Indispensable Things to Know
### Remember: JavaScript is case sensitive
- This is tricky for Salesforce developers used to Apex and SOQL being case insensitive. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### Declaring variables: `var`, `let`, `const`
The unit summarizes: ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))
- `var`: function scope, mutable assignment
- `let`: block scope, mutable assignment
- `const`: block scope, **immutable assignment**

**Primitive reassignment example (as shown)**
```js
//primitive assignments
var myBike = "Mountain Bike";
let currentGear = 5;
const numberOfGears = 12;

//reassignment
myBike = "Penny Farthing"; // this works
currentGear = 1; // so does this
numberOfGears = 1; // error
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### “All variables are pointers” + const with objects
- Assignment points the variable to something in memory.
- `const` prevents reassigning the variable to a different object, but does **not** prevent mutating the object itself (properties/functions can still be changed). ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### Implicit type coercion (pitfall)
- Operators may implicitly convert types.
- Example behavior shown by the unit:
    - `9 * "3"` becomes a number result
    - `9 + "3"` becomes string concatenation behavior ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### Don’t use implicit Boolean coercion with `==` / `!=`
- `==` and `!=` can coerce types in confusing ways.
- Best practice: use `===` and `!==` (type + value must match for primitives; for objects, pointers must match). ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### Truthy and Falsy (exception you must know)
Falsy values listed:
- `false`, `0`, `""` / `''`, `null`, `undefined`, `NaN`
- Everything else is truthy.
- The unit calls out the useful pattern: `if (myRecord) { ... }` to handle multiple invalid cases. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### `this` is tricky
- In Apex, `this` reliably points to the current instance.
- In JavaScript, what `this` points to depends on **where the function is called**, not where it’s defined. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### Functions are values
- Functions are objects and first-class: they can be assigned to variables, passed as parameters, and used like other objects. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

---

## VI (A-level; bám sát Topics; giữ thuật ngữ chuyên ngành)

### A Quick Disclaimer
- Module giả định bạn biết JS cơ bản (keywords/operators/syntax) nhưng còn mới.
- Nếu bạn chuyển từ ngôn ngữ “classical” như Apex sang JavaScript, mục tiêu là hiểu *what* và *why* của c��c feature JS để viết tốt hơn trong **Lightning Web Components** hoặc framework JS khác. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### Mục tiêu học
- Mô tả bản chất JavaScript runtime environment.
- Phân biệt JavaScript engine và JavaScript (ngôn ngữ).
- Tránh các pitfalls khi học JS.
- Mô tả các best practices quan trọng. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### The What, Why, and How of JavaScript
- Thời kỳ đầu web apps: browser đơn giản, chuẩn phân mảnh → đôi khi buộc dùng 1 browser.
- Nhiều framework server-side UI ra đời để logic chạy trên server, HTML render gửi về browser; JS chủ yếu làm interactivity đơn giản.
- Ví dụ framework Salesforce: **Visualforce** (unit nhắc có hàng triệu VF pages).
- Hiện tại: JS chuẩn hóa theo **ECMAScript**, browser mạnh, web apps nhiều cái client-side rendered.
- Trên Salesforce, client-side rendering qua **Lightning Component Framework**. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### JavaScript Runtime
- Runtime là engine chạy JS; đặc trưng là **single-threaded**.
- Stack chạy synchronous work; queue chứa requests; **event loop** đưa queue → stack khi stack rỗng. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### JavaScript the Language
- JS thay đổi theo năm vì ECMAScript update hằng năm; có “syntactic sugar”. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))
- API adoption không đồng đều → cần check compatibility; có **polyfills**; Lightning Component Framework dùng polyfills curated để tăng tương thích. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

### Indispensable Things to Know
- JS **case sensitive** (khác Apex/SOQL). ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))
- Khai báo biến `var`/`let`/`const`:
    - `var`: function scope, mutable assignment
    - `let`: block scope, mutable assignment
    - `const`: block scope, immutable assignment ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

**Snippet đúng như unit**
```js
var myBike = "Mountain Bike";
let currentGear = 5;
const numberOfGears = 12;

myBike = "Penny Farthing";
currentGear = 1;
numberOfGears = 1; // error
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))

- “All variables are pointers”; `const` không cho reassignment nhưng object vẫn mutate được. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))
- Tránh implicit type coercion; best practice dùng `===` / `!==`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))
- Truthy/Falsy: falsy gồm `false`, `0`, `""`, `null`, `undefined`, `NaN`; còn lại truthy; pattern `if (myRecord)` hữu ích. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))
- `this` “tricky”: phụ thuộc nơi function được gọi. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))
- Functions là values/first-class. ([trailhead.salesforce.com](https://trailhead.salesforce.com/es/content/learn/modules/javascript-essentials-salesforce-developers/learn-js-core-concepts))