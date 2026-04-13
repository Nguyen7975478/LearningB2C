# Work with Objects, Classes, and Prototypical Inheritance
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level; faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Create objects using object literal notation and constructors.
- Assign properties and functions to objects.
- Identify the role of prototypes in JavaScript object inheritance.
- Describe JavaScript class syntax.
- Describe the role of inheritance and object literal notation in Lightning Web Components. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

---

## Notes on JavaScript objects (unit list)
- Objects don’t have classes the way an Apex/Java/C# developer might think.
- Each object inherits from another object.
- Objects are mutable.
- Objects get their own variable context when created. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

---

## Assigning Properties and Functions to Objects
- Objects have members of two types:
    - properties
    - functions
- Property shapes listed:
    - primitives
    - objects
    - arrays ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

### Primitive types (unit list + note)
- At the time of writing, JavaScript has seven primitive types:
    - string, number, Boolean, `null`, `undefined`, symbol, bigint
- Primitive types are immutable.
- Primitive variables are passed by value when assigned (a copy is assigned). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

---

## Objects and Inheritance (Prototypal inheritance)
- JavaScript inheritance model is **prototype inheritance**.
- A prototype is another object in memory that defines properties/functions that other objects inherit if they share the same prototype.
- Traditionally, objects share the same prototype by sharing the same constructor function.
- Example given: `Bike` constructor + `Bike.prototype.changeGear = function(...) { ... }` so every object created from `Bike` inherits `changeGear`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

**Constructor + prototype method snippet (as shown)**
```js
function Bike(gears, startGear) {
  this.gears = gears;
  this.currentGear = startGear;
}
Bike.prototype.changeGear = function(direction, changeBy) {
  if (direction === 'up') {
    this.currentGear += changeBy;
  } else {
    this.currentGear -= changeBy;
  }
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

### Prototype chains + the `class` keyword
- You can implement multilevel inheritance (prototype chain).
- Doing it with constructor functions is complex and requires boilerplate; beyond the module’s scope.
- To address complexity, ECMAScript introduced `class` syntax.
- Important: JavaScript `class` is syntactic sugar; under the covers it’s still prototypes / `Object.create`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

---

## VI (A-level; bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Tạo objects bằng object literal notation và constructors.
- Gán properties và functions vào objects.
- Nhận biết vai trò của prototypes trong inheritance.
- Mô tả JavaScript class syntax.
- Mô tả vai trò của inheritance và object literal notation trong LWC. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

### Ghi chú về objects (đúng list trong unit)
- JS objects không có “classes” theo nghĩa Apex/Java/C#.
- Mỗi object inherit từ object khác.
- Objects mutable.
- Mỗi object có variable context riêng khi tạo. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

### Properties và functions
- Member có 2 loại: property và function.
- Properties có thể là primitives/objects/arrays. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))
- Primitive types (7 loại theo unit): string, number, Boolean, null, undefined, symbol, bigint; immutable; assignment là by value (copy). ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

### Prototypal inheritance
- JS dùng prototype inheritance; prototype là object trong memory chứa props/functions để objects khác inherit.
- Thường objects share prototype bằng cách share constructor.
- Ví dụ `Bike` + `Bike.prototype.changeGear` để mọi instance từ `Bike` dùng được `changeGear`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

**Snippet đúng như unit**
```js
function Bike(gears, startGear) {
  this.gears = gears;
  this.currentGear = startGear;
}
Bike.prototype.changeGear = function(direction, changeBy) {
  if (direction === 'up') {
    this.currentGear += changeBy;
  } else {
    this.currentGear -= changeBy;
  }
}
```
([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))

### Class syntax
- Prototype chain phức tạp nếu viết bằng constructor functions.
- `class` là syntactic sugar; engine vẫn dùng prototype / `Object.create`, không phải class-based inheritance “thật” như Java/C#. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/javascript-essentials-salesforce-developers/work-with-obj-class-prototype?utm_source=openai))