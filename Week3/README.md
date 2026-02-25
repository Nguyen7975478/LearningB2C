# 📚 Tuần 3: ISML + Controllers

## 🎯 Mục tiêu tuần

- ✅ Nắm vững ISML template
- ✅ Hiểu SFRA Controllers
- ✅ Sử dụng Resource Bundles
- ✅ Đọc và hiểu SFRA source code

---

## 📅 Lịch trình chi tiết 7 ngày

### 📌 Thứ 2 (T2): ISML Cơ bản

**Nội dung học:**
- 📝 ISML syntax cơ bản
- 🔤 Variables và expressions
- 🔀 Conditionals: `<isif>`, `<iselseif>`, `<iselse>`
- 🔁 Loops: `<isloop>`, `<isbreak>`, `<isnext>`
- 📥 Include templates: `<isinclude>`
- 💬 Comments: `<iscomment>`

**Code mẫu:**
```isml
<isif condition="${product.available}">
    <div class="product-available">
        <span>${product.name}</span>
    </div>
<iselse/>
    <div class="product-unavailable">Out of Stock</div>
</isif>

<isloop items="${products}" var="product">
    <div>${product.name}</div>
</isloop>
```

---

### 📌 Thứ 3 (T3): ISML Nâng cao

**Nội dung học:**
- 📌 `isset` - Set variables
- 📄 `iscontent` - Set content type
- ⚡ `iscache` - Caching
- 🔲 `isslot` - Content slots
- 🖨️ `isprint` - Print with encoding
- 🎨 `isdecorate` - Template decoration
- 🔄 `isreplace` - Content replacement

**Code mẫu:**
```isml
<iscontent type="text/html" charset="UTF-8"/>
<iscache type="relative" hour="24"/>
<isset name="total" value="${basket.totalGrossPrice}" scope="page"/>
<isprint value="${product.name}" encoding="htmlcontent"/>
```

---

### 📌 Thứ 4 (T4): Resource Bundles

**Nội dung học:**
- 📂 Tạo và quản lý properties files
- 🌐 Multi-language support
- 📝 Using `Resource.msg()` trong ISML
- 💻 Using `Resource.msg()` trong JavaScript
- ✅ Best practices

**Properties file mẫu (`forms.properties`):**
```properties
button.submit=Submit
button.cancel=Cancel
error.required=This field is required
```

**Sử dụng trong ISML:**
```isml
${Resource.msg('button.submit','forms',null)}
```

**Sử dụng trong JavaScript:**
```javascript
var Resource = require('dw/web/Resource');
var submitText = Resource.msg('button.submit', 'forms', null);
```

---

### 📌 Thứ 5 (T5): SFRA Controllers Cơ bản

**Nội dung học:**
- 🏗️ Controller structure
- 🛣️ Routes và endpoints
- 📨 Request/Response
- 🔧 `server.get()`, `server.post()`
- 🔗 Middleware
- 🖥️ Render templates

**Code mẫu:**
```javascript
var server = require('server');

server.get('Show', function (req, res, next) {
    var ProductMgr = require('dw/catalog/ProductMgr');
    var product = ProductMgr.getProduct(req.querystring.pid);

    res.render('product/productDetail', {
        product: product
    });

    next();
});

module.exports = server.exports();
```

---

### 📌 Thứ 6 (T6): SFRA Controllers Nâng cao

**Nội dung học:**
- 📋 Form handling
- ✔️ Validation
- 💾 Transaction management
- ⚠️ Error handling
- 🔗 Chaining controllers
- 🔧 `server.extend()`, `server.append()`, `server.replace()`

**Code mẫu:**
```javascript
var server = require('server');
var BasketMgr = require('dw/order/BasketMgr');
var Transaction = require('dw/system/Transaction');

server.post('AddProduct', function (req, res, next) {
    var basket = BasketMgr.getCurrentBasket();

    try {
        Transaction.wrap(function () {
            basket.createProductLineItem(req.form.pid, req.form.quantity);
        });

        res.json({
            success: true,
            basket: basket
        });
    } catch (e) {
        res.json({
            success: false,
            error: e.message
        });
    }

    next();
});
```

---

### 📌 Thứ 7 (T7): Đọc SFRA Source Code

**Nội dung học:**
- 📦 Clone SFRA repository
- 🗂️ Hiểu cấu trúc SFRA
- 📖 Đọc các controller chính:
  - `Product.js`
  - `Cart.js`
  - `Checkout.js`
  - `Search.js`
- ✅ Best practices từ SFRA

---

### 📌 Chủ Nhật (CN): Models + 20 câu hỏi

**Nội dung:**
- 🏛️ Tìm hiểu Models trong SFRA
- 🛍️ Product Model, Cart Model, Order Model
- ❓ Làm 20 câu hỏi ôn tập

---

## ✅ Checklist Tuần 3

- [ ] Nắm vững ISML cơ bản và nâng cao
- [ ] Sử dụng được Resource Bundles
- [ ] Viết được SFRA Controllers
- [ ] Hiểu cấu trúc SFRA
- [ ] Đọc được SFRA source code
- [ ] Hiểu Models trong SFRA
- [ ] Làm 20 câu hỏi ôn tập

---

## 🔗 Navigation

- ⬅️ [Tuần 2 - Dữ liệu và Business Manager](../Week2/)
- ➡️ [Tuần 4](../Week4/)
