# Understand JavaScript in the Browser
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level; faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you'll be able to:
- Describe the interaction between JavaScript and the browser.
- Explain the role of web APIs.
- Use basic Document Object Model APIs.
- Describe ways Lightning components abstract the DOM. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

---

## How JavaScript Works in the Browser
- The unit focuses on the relationship between JavaScript and the browser, with emphasis on how your web page looks in JavaScript. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

---

## The JavaScript Runtime Is Not the Browser, Nor Is the Browser JavaScript
- A browser’s primary job: act as a client for a web server, request resources over protocols like HTTP/HTTPS, then render them (HTML/CSS into a page).
- When JavaScript is encountered, the browser uses the JavaScript runtime engine to parse/evaluate/execute it.
- While scripts run, they can call back to browser capabilities (modify page, interact with local environment, interact with other resources). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

---

## Web APIs
### Standards + why they matter
- Because there are multiple browsers, web API standards matter so JavaScript can be written once and run anywhere. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

### Adding web APIs to the runtime model
- The unit extends the earlier runtime model:
    - single-thread stack execution
    - queue of requests
    - event loop scheduling
- Web APIs extend core JavaScript and surface interfaces critical to UX. Examples listed include:
    - DOM API (interact with page structure)
    - Fetch API (async server requests without leaving page)
    - Audio/video/graphics
    - Device features (geolocation, device orientation, client-side data storage) ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

### Simple end-to-end example (unit example)
A basic app flow might use:
- Fetch API to save data
- DOM API to update the page
- Client-data storage to cache locally ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

---

## DOM API (what “the page” looks like in JS)
- The unit then “dives into the DOM API” as the representation of what the user sees inside JavaScript. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

---

## Lightning components and the DOM
- The unit’s goal includes describing how Lightning components abstract the DOM (how framework code handles DOM interactions so you rarely manipulate DOM directly). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

---

## VI (A-level; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Mô tả tương tác giữa JavaScript và browser.
- Giải thích vai trò web APIs.
- Dùng các DOM APIs cơ bản.
- Mô tả cách Lightning components abstract DOM. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

### JavaScript trong browser hoạt động ra sao
- Unit tập trung mối quan hệ JS ↔ browser, đặc biệt “web page nhìn như thế nào trong JS”. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

### Runtime không phải browser, và browser không phải JavaScript
- Browser là client của web server, request resources qua HTTP/HTTPS, render HTML/CSS.
- Khi gặp JS, browser gọi JS runtime engine để parse/evaluate/execute.
- Script đang chạy có thể gọi lại APIs của browser để sửa page, tương tác môi trường local, và tài nguyên khác. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

### Web APIs
- Có nhiều browsers → standards quan trọng để “write once run anywhere”. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))
- Web APIs mở rộng core JS và cung cấp interfaces quan trọng cho UX, ví dụ:
    - DOM API, Fetch API, media/graphics, device features (geolocation/orientation/storage). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))
- Ví dụ flow: Fetch lưu record, DOM thêm item vào list, client storage cache data. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))

### DOM API
- DOM là mô hình biểu diễn cấu trúc page để JS thao tác; unit chuyển sang “dive into the DOM API”. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/understand-js-in-browser?utm_source=openai))