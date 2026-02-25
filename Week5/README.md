# 📚 Tuần 5: Ôn tập tổng hợp

## 🎯 Mục tiêu tuần

- ✅ Ôn tập và củng cố toàn bộ kiến thức
- ✅ Nắm vững Performance Best Practices
- ✅ Hiểu rõ Transactions và Logging patterns
- ✅ Thực hành Code Review
- ✅ Chuẩn bị cho thi thử lần 1

---

## 📅 Lịch trình chi tiết 7 ngày

### 📌 Thứ 2 (T2): Performance Best Practices

**Nội dung học:**
- ⚡ Code optimization techniques
- 💾 Caching strategies
- 🗄️ Database query optimization
- 📊 Script performance profiling
- ⚠️ Common performance pitfalls
- 🧠 Memory management
- 🖼️ Asset optimization

**BAD vs GOOD Code Examples:**

❌ **BAD - Inefficient loop:**
```javascript
var products = productSearch.getProducts();
while (products.hasNext()) {
    var product = products.next();
    var price = product.getPriceModel().getPrice().getValue(); // Multiple API calls
    // Process product
}
```

✅ **GOOD - Optimized:**
```javascript
var products = productSearch.getProducts();
var productsList = products.toArray(); // Convert to array once
for (var i = 0; i < productsList.length; i++) {
    var product = productsList[i];
    var priceModel = product.getPriceModel(); // Cache the model
    var price = priceModel.getPrice().getValue();
    // Process product
}
```

❌ **BAD - No caching:**
```javascript
var ProductMgr = require('dw/catalog/ProductMgr');
function getProductName(pid) {
    return ProductMgr.getProduct(pid).getName(); // API call every time
}
```

✅ **GOOD - With caching:**
```javascript
var ProductMgr = require('dw/catalog/ProductMgr');
var cache = {};
function getProductName(pid) {
    if (!cache[pid]) {
        cache[pid] = ProductMgr.getProduct(pid).getName();
    }
    return cache[pid];
}
```

❌ **BAD - Multiple transactions:**
```javascript
var Transaction = require('dw/system/Transaction');
for (var i = 0; i < items.length; i++) {
    Transaction.wrap(function() {
        basket.createProductLineItem(items[i].pid, items[i].qty);
    });
}
```

✅ **GOOD - Single transaction:**
```javascript
var Transaction = require('dw/system/Transaction');
Transaction.wrap(function() {
    for (var i = 0; i < items.length; i++) {
        basket.createProductLineItem(items[i].pid, items[i].qty);
    }
});
```

**Performance Best Practices:**
1. Minimize API calls - cache results when possible
2. Use transactions efficiently - wrap multiple operations
3. Avoid nested loops with API calls
4. Use pipeline cache for expensive operations
5. Optimize database queries with proper indexing
6. Lazy load data when possible
7. Use content slots caching
8. Minimize custom object reads/writes

---

### 📌 Thứ 3 (T3): Transactions + Logging

**Nội dung học:**
- 🔄 Transaction patterns
- ⚠️ Error handling best practices
- ↩️ Transaction rollback
- 📝 Logging strategies
- 🏷️ Log levels and usage
- 🔍 Monitoring and debugging
- 📊 Performance logging

**Transaction Patterns:**

**Pattern 1: Simple Transaction**
```javascript
var Transaction = require('dw/system/Transaction');
var BasketMgr = require('dw/order/BasketMgr');

try {
    Transaction.wrap(function() {
        var basket = BasketMgr.getCurrentOrNewBasket();
        basket.createProductLineItem(pid, quantity);
    });
} catch (e) {
    Logger.error('Error adding product: ' + e.message);
    throw e;
}
```

**Pattern 2: Nested Operations**
```javascript
var Transaction = require('dw/system/Transaction');
var OrderMgr = require('dw/order/OrderMgr');

Transaction.wrap(function() {
    var order = OrderMgr.createOrder(basket);
    order.setPaymentInstrument(paymentInstrument);
    order.setShippingMethod(shippingMethod);
    OrderMgr.placeOrder(order);
});
```

**Pattern 3: Error Handling with Rollback**
```javascript
var Transaction = require('dw/system/Transaction');
var Status = require('dw/system/Status');

function processOrder(order) {
    try {
        Transaction.begin();
        
        // Step 1: Update order
        order.setStatus(Order.ORDER_STATUS_NEW);
        
        // Step 2: Process payment
        var paymentResult = processPayment(order);
        if (!paymentResult.success) {
            Transaction.rollback();
            return new Status(Status.ERROR, 'PAYMENT_FAILED');
        }
        
        // Step 3: Update inventory
        updateInventory(order);
        
        Transaction.commit();
        return new Status(Status.OK);
    } catch (e) {
        Transaction.rollback();
        Logger.error('Order processing failed: ' + e.message);
        return new Status(Status.ERROR, 'ORDER_PROCESSING_FAILED');
    }
}
```

**Logging Best Practices:**

```javascript
var Logger = require('dw/system/Logger');
var logger = Logger.getLogger('custom', 'OrderProcessing');

// DEBUG - Detailed information for debugging
logger.debug('Processing order: ' + orderNo + ', items: ' + itemCount);

// INFO - General informational messages
logger.info('Order ' + orderNo + ' placed successfully');

// WARN - Warning messages for potential issues
logger.warn('Low inventory for product: ' + productID + ', remaining: ' + qty);

// ERROR - Error messages for failures
logger.error('Payment failed for order: ' + orderNo + ', error: ' + error.message);

// With error object
try {
    // risky operation
} catch (e) {
    logger.error('Error processing order: {0}', e.message);
    logger.error('Stack trace: {0}', e.stack);
}
```

---

### 📌 Thứ 4 (T4): Bài tập Code Review

**Nội dung học:**
- 🔍 Review code samples
- 🐛 Identify bugs and issues
- 🔒 Security vulnerabilities
- ⚡ Performance improvements
- 📋 Best practices violations
- 🔨 Refactoring exercises

**Code Review Exercise 1: Find the issues**

```javascript
// PROBLEMATIC CODE
var server = require('server');

server.get('Show', function (req, res, next) {
    var productID = req.querystring.pid; // Issue 1: No validation
    var ProductMgr = require('dw/catalog/ProductMgr');
    var product = ProductMgr.getProduct(productID); // Issue 2: No null check
    
    var Transaction = require('dw/system/Transaction');
    Transaction.wrap(function() { // Issue 3: Unnecessary transaction for read
        var name = product.getName();
        var price = product.getPrice();
    });
    
    res.render('product', { product: product }); // Issue 4: Missing next()
});
```

**FIXED CODE:**

```javascript
var server = require('server');

server.get('Show', function (req, res, next) {
    var productID = req.querystring.pid;
    
    // Validate input
    if (!productID) {
        res.setStatusCode(400);
        res.json({ error: 'Product ID is required' });
        return next();
    }
    
    var ProductMgr = require('dw/catalog/ProductMgr');
    var product = ProductMgr.getProduct(productID);
    
    // Check if product exists
    if (!product) {
        res.setStatusCode(404);
        res.json({ error: 'Product not found' });
        return next();
    }
    
    // No transaction needed for read operations
    res.render('product', { product: product });
    next();
});
```

---

### 📌 Thứ 5 (T5): Fast Path Videos

**Nội dung học:**
- 🏗️ B2C Commerce Architecture
- 📝 Forms and validation
- 🪝 Hooks system deep dive
- 🔧 Service Framework
- 🎨 Page Designer advanced topics
- ✅ SFRA best practices

---

### 📌 Thứ 6 (T6): Ôn lại Domain 1-3

### Domain 1: Digital Applications (27%)
**Key Topics:**
- Storefront architecture
- Cartridge structure and path
- Controllers and routes
- ISML templates
- Page Designer components
- Content Assets and Slots
- SEO best practices

**Sample Questions:**
1. What is the correct cartridge path order?
2. How does controller inheritance work in SFRA?
3. What is the purpose of iscache tag?
4. How to create a custom Page Designer component?

### Domain 2: Customization (36%)
**Key Topics:**
- Forms Framework
- Resource Bundles
- Hooks system
- Service Framework
- Custom objects and attributes
- Business Manager extensions
- Script debugging

**Sample Questions:**
1. How to implement a custom hook?
2. What is the purpose of hooks.json?
3. How to create a service with mock data?
4. When should you use Transaction.wrap()?

### Domain 3: System & Data (30%)
**Key Topics:**
- Product data model
- Order management
- Customer data
- Inventory management
- Pricing and promotions
- Search and indexing
- Caching strategies
- OCAPI (Shop and Data)

**Sample Questions:**
1. What is the difference between Product and Variant?
2. How does page caching work?
3. What are OCAPI best practices?
4. How to optimize search performance?

### Domain 4: Maintenance (7%)
**Key Topics:**
- Logging and monitoring
- Performance optimization
- Debugging techniques
- Code profiling
- Error handling
- Security best practices

**Bảng đánh giá mục tiêu:**

| Domain | Weight | Target Score | Topics to Focus |
|--------|--------|--------------|-----------------|
| Digital Applications | 27% | 80%+ | ISML, Controllers, Page Designer |
| Customization | 36% | 85%+ | Forms, Hooks, Services |
| System & Data | 30% | 80%+ | Data Model, OCAPI, Caching |
| Maintenance | 7% | 75%+ | Logging, Performance |
| **Overall** | **100%** | **80%+** | - |

---

### 📌 Thứ 7 (T7): THI THỬ LẦN 1 🎯

### Chuẩn bị thi:
- 60 câu hỏi
- 105 phút (1 giờ 45 phút)
- Passing score: 65%
- Target score: 80%+

### Chiến thuật làm bài:

**Pass 1 (45-50 phút):**
- Làm tất cả câu dễ và chắc chắn
- Skip câu khó hoặc chưa chắc
- Mark để review sau

**Pass 2 (30-35 phút):**
- Review các câu đã mark
- Áp dụng elimination method
- Suy luận dựa trên kiến thức

**Pass 3 (15-20 phút):**
- Final review tất cả câu
- Double check câu dễ sai
- Đảm bảo không bỏ sót

### Trong khi thi:
✅ Đọc kỹ đề trước khi chọn
✅ Chú ý từ khóa: NOT, EXCEPT, ALWAYS, NEVER
✅ Eliminate wrong answers trước
✅ Trust your first instinct nếu không chắc
✅ Time management - không dành quá 2 phút/câu
❌ Không thay đổi answer quá nhiều
❌ Không panic nếu gặp câu khó

---

### 📌 Chủ Nhật (CN): Phân tích lỗ hổng

**Nội dung:**
- 📊 Review kết quả thi thử
- 🔍 Phân tích các câu sai
- 🎯 Xác định điểm yếu
- 📋 Lập kế hoạch ôn tập bổ sung
- 🃏 Tạo flashcards cho kiến thức còn yếu

### Bảng tracking tiến độ:

| Mock Exam | Date | Score | Domain 1 | Domain 2 | Domain 3 | Domain 4 | Notes |
|-----------|------|-------|----------|----------|----------|----------|-------|
| Mock 1 | ___/___/___ | ___% | ___% | ___% | ___% | ___% | ________________ |
| Mock 2 | ___/___/___ | ___% | ___% | ___% | ___% | ___% | ________________ |
| Mock 3 | ___/___/___ | ___% | ___% | ___% | ___% | ___% | ________________ |

### Weak Areas Analysis:

**Areas to improve:**
- [ ] ________________________________
- [ ] ________________________________
- [ ] ________________________________
- [ ] ________________________________

**Action items:**
1. ________________________________
2. ________________________________
3. ________________________________

---

## ✅ Checklist Tuần 5

- [ ] Học Performance Best Practices
- [ ] Hiểu Transaction patterns
- [ ] Hoàn thành Code Review exercises
- [ ] Xem Fast Path Videos
- [ ] Ôn tập Domain 1-3
- [ ] Thi thử lần 1
- [ ] Phân tích kết quả và lỗ hổng

---

## 🔗 Tài liệu tham khảo

### Official Documentation
- **[B2C Commerce InfoCenter](https://documentation.b2c.commercecloud.salesforce.com/DOC1/)**
- **[Script API Documentation](https://documentation.b2c.commercecloud.salesforce.com/DOC2/topic/com.demandware.dochelp/DWAPI/scriptapi/html/api/index.html)**
- **[OCAPI Shop API](https://documentation.b2c.commercecloud.salesforce.com/DOC2/topic/com.demandware.dochelp/OCAPI/current/shop/Resources/index.html)**
- **[OCAPI Data API](https://documentation.b2c.commercecloud.salesforce.com/DOC2/topic/com.demandware.dochelp/OCAPI/current/data/Resources/index.html)**

### Practice Resources
- **[Focus on Force](https://focusonforce.com/)** - Practice exams (paid)
- **[Quizlet Flashcards](https://quizlet.com/search?query=salesforce%20b2c%20commerce)** - Community flashcards
- **[Week 5 Exercises](../Practice/Week5/)**

### Video Tutorials
- **[B2C Commerce Fast Path Videos](https://help.salesforce.com/s/articleView?id=cc.b2c_fast_path_training.htm)**

---

## 📋 Checklist tuần 5

- [ ] Học Performance Best Practices
- [ ] Hiểu Transaction patterns (begin/commit/rollback)
- [ ] Hoàn thành Code Review exercises
- [ ] Xem Fast Path Videos
- [ ] Ôn tập Domain 1 - Digital Applications (27%)
- [ ] Ôn tập Domain 2 - Customization (36%)
- [ ] Ôn tập Domain 3 - System & Data (30%)
- [ ] Ôn tập Domain 4 - Maintenance (7%)
- [ ] Thi thử lần 1 (target 80%+)
- [ ] Phân tích kết quả và xác định lỗ hổng

---

## 🔗 Navigation

- ⬅️ [Tuần 4 - Forms+Hooks](../Week4/)
- ➡️ [Tuần 6 - Thi chính thức](../Week6/)
