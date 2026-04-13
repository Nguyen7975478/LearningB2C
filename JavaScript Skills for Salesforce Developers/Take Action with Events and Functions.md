# Take Action with Events and Functions
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level; faithful to unit; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Define functions
- Distinguish between function declaration and function expressions
- Invoke functions
- Pass and assign functions
- Describe uses of functions and events in Lightning Web Components ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

---

## Runtime tie-in: events → queue → stack frames
- In the browser, events are everywhere: click/change/mouse events, window device events.
- DOM events are not core JavaScript language; they are browser APIs.
- When an event is emitted, a message is created and placed into the event queue.
- When the stack is free, the handler is invoked (a frame is pushed). Nested calls add frames; frames pop as calls complete. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

---

## Defining and Assigning Functions
- Functions are special objects; first-class: can be assigned to variables, passed as parameters, returned from functions. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))
- Two phases: definition and invocation. When declared, definition is loaded into memory and a pointer is assigned (variable/parameter/object property). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

### Function declaration (unit example)
```js
// declare function
function calculateGearRatio(driverGear, drivenGear){
  return (driverGear / drivenGear);
}

// call function
let gearRatio = calculateGearRatio(42, 30);
console.log(gearRatio); // 1.4
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

### Function expression assigned to prototype (unit reminder)
```js
Bike.prototype.changeGear = function(direction, changeBy) {
  if (direction === 'up') {
    this.currentGear += changeBy;
  } else {
    this.currentGear -= changeBy;
  }
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

### Returning a function (factory function pattern)
```js
function gearFactory(){
  return function(driverGear, drivenGear){
    return (driverGear / drivenGear);
  }
}
const calculateGearRatio = gearFactory();
// calculateGearRatio can now be invoked as a function
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

### Anonymous functions (example via Array.map)
```js
let myArray = [1, 5, 11, 17];
let newArray = myArray.map( function(item){ return item / 2 } );
console.log(newArray); // [0.5, 2.5, 5.5, 8.5]
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

---

## Function Invocation (what happens conceptually)
When invoked:
- A new frame is pushed onto the stack.
- An object containing variables/arguments is created in memory.
- `this` is bound (plus other special objects).
- Arguments values are assigned, then the runtime executes the function body. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

### Invocation vs assignment (the parentheses rule)
- Whether you use `()` determines if you *invoke* a function vs pass/assign the function reference. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

---

## Functions as Event Handlers
### Event object parameter (unit example)
```js
var handleClick = function(event) {
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

### Inspecting event properties (unit example)
```js
var handleClick = function(event) {
  console.log(event.type);  // click
  console.log(event.currentTarget); // the thing you clicked
  console.log(event.screenX); // screen X coordinate
  console.log(event.screenY); // screen Y coordinate
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

### Assigning handlers: HTML attribute vs DOM API
Inline HTML example shown:
```html
<button onclick="handleClick(event)">
  Click to Go
</button>
```
Modern approach (preferred): `addEventListener`
```js
let button = document.getElementById("clicker");
button.addEventListener("click", handleClick);
```
- You can also remove it:
```js
button.removeEventListener("click", handleClick);
```
- Anonymous listeners can’t be removed easily because you have no pointer to pass. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

---

## Events and Functions in Lightning Web Components (LWC)
- Key code artifacts: JavaScript module, HTML template, CSS file (JS module required; XML metadata also required but not code).
- LWC functions are typically methods on the exported class; they serve as event handlers or helpers.
- Template handler binding looks like HTML, but because the template compiles to JS, it’s a framework convention that ultimately wires `addEventListener` during component lifecycle. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))

**Template binding example**
```html
<lightning-input onchange={handleChange} label="Input Text" value={text}>
</lightning-input>
```

**Handler example**
```js
handleChange(event){
    this.text = event.target.value;
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/take-action-events-functions?utm_source=openai))