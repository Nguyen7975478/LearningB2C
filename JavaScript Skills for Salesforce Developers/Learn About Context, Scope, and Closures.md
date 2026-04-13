# Learn About Context, Scope, and Closures
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level; faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Describe execution context and lexical scope in JavaScript.
- Explain how `this` is bound.
- Describe how closures work and why they’re useful.
- Recognize common pitfalls around context, scope, and closures in modern JavaScript (especially framework code). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

---

## 1) Context vs Scope (why Salesforce devs get tripped up)
- In classical languages, “context” and “scope” often feel aligned.
- In JavaScript, **context** (what `this` is) and **scope** (which variables you can access) are different concepts.
- The unit positions this as a common source of confusion when moving from Apex to JavaScript. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

---

## 2) Execution Context (runtime view)
- JavaScript executes code inside an **execution context**.
- The unit ties this to the earlier runtime model (stack frames, event loop): each function invocation creates a new stack frame and a new execution context with its own variables/arguments bindings. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

---

## 3) Lexical Scope (compile-time view)
- JavaScript uses **lexical scoping**:
    - what variables a function can “see” is determined by where the function is written in the code, not where it’s called from.
- Functions create scope boundaries; blocks can also create scope boundaries with `let` and `const`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

### Function scope vs block scope (reinforcement)
- `var` is function-scoped (not block-scoped).
- `let` / `const` are block-scoped. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

---

## 4) `this` Binding (the practical definition)
- The value of `this` is determined at **call time** by *how a function is invoked*, not where it’s defined.
- This differs from Apex, where `this` is consistently the current instance. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

### Common patterns that change `this`
- Method call: `obj.method()` typically binds `this` to `obj`.
- Standalone call: `func()` binds `this` differently depending on strict mode / environment.
- Event handlers / callbacks can lose the original `this` unless explicitly bound. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

---

## 5) Closures (what they are)
- A **closure** is created when a function “remembers” the variables from the lexical scope where it was created, even after that outer function has returned.
- This is fundamental to JavaScript patterns such as:
    - factory functions (returning functions),
    - encapsulation of private state,
    - callbacks that need access to outer variables. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

### Why closures are useful
- They let you keep state without global variables.
- They let you parameterize behavior (make a specialized function once, reuse later). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

---

## 6) Common pitfalls (as framed by the unit)
- Confusing context (`this`) with scope (variable visibility).
- Accidentally using `var` in loops and expecting per-iteration bindings (use `let`).
- Losing `this` when passing methods as callbacks (bind or use arrow functions where appropriate).
- Overusing closures in a way that retains memory longer than intended (be mindful of what a callback captures). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

---

## VI (A-level; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
Sau khi hoàn thành unit, bạn có thể:
- Mô tả execution context và lexical scope trong JavaScript.
- Giải thích cách `this` được bind.
- Mô tả closures hoạt động thế nào và vì sao hữu ích.
- Nhận ra các pitfalls thường gặp về context/scope/closures trong JS hiện đại (đặc biệt khi viết code trong framework). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

### 1) Context vs Scope (vì sao dễ nhầm)
- Trong các ngôn ngữ “classical”, context và scope thường “có vẻ” trùng nhau.
- Trong JS:
    - **context** = `this` là gì
    - **scope** = biến nào truy cập được
- Unit nhấn mạnh đây là nguồn nhầm lẫn phổ biến khi chuyển từ Apex sang JS. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

### 2) Execution Context (góc nhìn runtime)
- JS thực thi trong **execution context**.
- Mỗi lần gọi function tạo stack frame + execution context mới với bindings riêng (variables/arguments). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

### 3) Lexical Scope (góc nhìn compile-time)
- JS dùng **lexical scoping**:
    - function “nhìn thấy” biến dựa trên nơi function được viết (định nghĩa), không phải nơi nó được gọi.
- Function tạo boundary cho scope; block cũng tạo boundary nếu dùng `let/const`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))
- Nhắc lại:
    - `var` function-scope
    - `let/const` block-scope ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

### 4) `this` binding
- `this` phụ thuộc *cách gọi* function (call-site), không phụ thuộc nơi định nghĩa.
- Khác Apex: `this` thường luôn là instance hiện tại. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

### 5) Closures
- Closure xảy ra khi function “ghi nhớ” biến từ lexical scope nơi nó được tạo, kể cả khi outer function đã return.
- Là nền tảng cho factory functions, “private state”, và callback cần dùng biến bên ngoài. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))

### 6) Pitfalls
- Nhầm `this` (context) với scope.
- Dùng `var` trong loop và kỳ vọng binding theo iteration (nên dùng `let`).
- Mất `this` khi truyền method làm callback (cần bind hoặc arrow function khi phù hợp).
- Closure giữ reference làm giữ memory lâu hơn nếu capture nhiều thứ không cần. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/context-scope-closures?utm_source=openai))