# 📚 Tuần 2: Dữ liệu và Business Manager

## 🎯 Mục tiêu tuần

- ✅ Nắm vững cơ chế Search trong SFCC
- ✅ Hiểu về System Objects và Custom Objects
- ✅ Làm việc với Caching
- ✅ Sử dụng OCAPI với Postman

---

## 📅 Lịch trình chi tiết 7 ngày

### 📌 Thứ 2 (T2): Cấu hình Search

**Nội dung học:**
- 🔍 Search Index và Reindex
- 🗂️ Search Refinements
- 📊 Sorting Rules
- 💡 Search Suggestions
- 🏆 Search Ranking

**🛠️ Bài tập:**
1. Cấu hình search refinements
2. Tạo sorting rule
3. Test suggestions

---

### 📌 Thứ 3 (T3): Cấu hình Logging

**Nội dung học:**
- 📋 Log Center trong Business Manager
- 📂 Các loại log: system, custom, error, warning
- 💻 Sử dụng Logger trong code
- ✅ Best practices cho logging
- 🐛 Debug và troubleshooting

**Code mẫu:**
```javascript
var Logger = require('dw/system/Logger');
var log = Logger.getLogger('custom', 'myCartridge');

log.info('This is info message');
log.error('This is error message');
log.debug('This is debug message');
```

---

### 📌 Thứ 4 (T4): System & Custom Objects

**Nội dung học:**
- 🗃️ Các System Objects: Customer, Order, Basket, Product, Category, Session, Request
- 🛠️ Custom Objects
- 📝 Custom Object Definition
- 🔄 CRUD operations với Custom Objects

**Code mẫu:**
```javascript
var CustomObjectMgr = require('dw/object/CustomObjectMgr');

// Create
var customObj = CustomObjectMgr.createCustomObject('MyObject', 'key123');
customObj.custom.field1 = 'value1';

// Read
var obj = CustomObjectMgr.getCustomObject('MyObject', 'key123');

// Delete
CustomObjectMgr.remove(obj);
```

---

### 📌 Thứ 5 (T5): Caching chuyên sâu

**Nội dung học:**
- 🗄️ Page Caching
- 🔗 Remote Include
- 📦 Content Slots caching
- ♻️ Cache invalidation
- ✅ Best practices

**🛠️ Bài tập:**
1. Cấu hình page cache
2. Sử dụng remote include
3. Test cache invalidation

---

### 📌 Thứ 6 (T6): OCAPI + Postman

**Nội dung học:**
- 🛒 OCAPI Shop API
- 📊 OCAPI Data API
- 🔐 Authentication và permissions
- 📬 Sử dụng Postman để test API
- 🔗 Common OCAPI endpoints

**🛠️ Bài tập:**
1. Cấu hình OCAPI settings
2. Get product data
3. Create basket
4. Search products

---

### 📌 Thứ 7 (T7): Thực hành tổng hợp

**Nội dung:**
- 🔗 Kết hợp các kiến thức đã học
- 💪 Bài tập thực hành lớn
- 👀 Code review

---

### 📌 Chủ Nhật (CN): Ôn tập + 30 câu hỏi

**Nội dung:**
- 📝 Ôn tập toàn bộ kiến thức tuần 2
- ❓ Làm 30 câu hỏi trắc nghiệm
- 🔍 Review lại các phần chưa rõ

---

## ✅ Checklist Tuần 2

- [ ] Biết cấu hình Search
- [ ] Sử dụng được Logging
- [ ] Hiểu System & Custom Objects
- [ ] Nắm vững Caching
- [ ] Sử dụng được OCAPI
- [ ] Hoàn thành bài tập thực hành
- [ ] Làm 30 câu hỏi ôn tập

---

## 🔗 Tài liệu tham khảo

### Official Documentation
- **[Salesforce Help Center](https://help.salesforce.com/)** ✅
- **[Search OCAPI Documentation](https://help.salesforce.com/s/global-search/OCAPI)** ✅ - Open Commerce API
- **[Salesforce Developers Documentation](https://developer.salesforce.com/docs)** ✅ - Script API Reference
- **[B2C Commerce Search Trailhead](https://trailhead.salesforce.com/content/learn/modules/b2c-commerce-search)** ✅
- **[B2C Commerce Order Management Trailhead](https://trailhead.salesforce.com/content/learn/modules/b2c-commerce-order-management)** ✅

### Video Tutorials
- **[Salesforce Developers YouTube](https://www.youtube.com/@salesforcedevelopers)** ✅ - Official channel
- **[OCAPI Tutorials](https://www.youtube.com/results?search_query=salesforce+b2c+ocapi)**

### Practice
- **[Week 2 Exercises](../Practice/Week2/)**
- **[OCAPI Postman Collection](https://github.com/SalesforceCommerceCloud/ocapi-postman)**

---

## 📋 Checklist tuần 2

- [ ] Biết cấu hình Search refinements và sorting
- [ ] Sử dụng được Logging trong code
- [ ] Hiểu System Objects (Customer, Order, Basket, Product)
- [ ] Thực hiện được CRUD với Custom Objects
- [ ] Nắm vững Caching strategies
- [ ] Sử dụng được OCAPI với Postman
- [ ] Hoàn thành bài tập thực hành
- [ ] Làm 30 câu hỏi ôn tập trong Practice/Week2/
- [ ] Review lại notes và code examples

---

## 🔗 Navigation

- ⬅️ [Tuần 1 - Cài đặt + KT](../Week1/)
- ➡️ [Tuần 3 - ISML+Ctil](../Week3/)
