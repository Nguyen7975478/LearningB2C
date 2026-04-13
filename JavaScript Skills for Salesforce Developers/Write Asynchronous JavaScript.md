# Write Asynchronous JavaScript
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/async-js?trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level; faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Identify important asynchronous features in JavaScript.
- Invoke functions asynchronously using `setTimeout`.
- Write and invoke callback functions.
- Write and invoke promise-based functions. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/async-js?utm_source=openai))

---

## Why async matters: don’t block the single thread
- The engine has a single thread; blocking it is a bad user experience.
- Unit example shows that `alert()` blocks rendering until dismissed: ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/async-js?utm_source=openai))
```html
<html>
  <script>
    alert("Does JavaScript show first?");
  </script>
  <body>
    <p>
      Does HTML show first?
    </p>
  </body>
</html>
```

- Apart from a few legacy bits like `alert()`, JavaScript is an asynchronous language. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/async-js?utm_source=openai))

---

## Asynchronous JavaScript is everywhere (events already async)
- Adding an event handler is already asynchronous:
    - when event fires, a message is added to the queue
    - no event can take over the thread; it waits its turn in the queue ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/async-js?utm_source=openai))

Example reminder shown:
```html
<!-- HTML -->
<button id="clicker">
```
```js
//JavaScript
let button = document.getElementById("clicker");
button.addEventListener("click", handleClick);
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/async-js?utm_source=openai))

---

## setTimeout (asynchronous invocation)
- The unit introduces `setTimeout(handler, milliseconds)` as a way to illustrate how work is queued and executed later. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/async-js?utm_source=openai))

---

## Callbacks
- The unit objective includes writing and invoking callback functions (functions passed into other functions to be invoked later). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/async-js?utm_source=openai))

---

## Promises
- The unit objective includes writing and invoking promise-based functions (promise-based async patterns). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/async-js?utm_source=openai))