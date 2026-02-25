# 📚 Tuần 4: Forms + Hooks

## 🎯 Mục tiêu tuần

- ✅ Nắm vững Forms Framework
- ✅ Hiểu và sử dụng Hooks System
- ✅ Làm việc với Page Designer
- ✅ Sử dụng Service Framework
- ✅ Tích hợp OCAPI nâng cao

---

## 📅 Lịch trình chi tiết 7 ngày

### 📌 Thứ 2 (T2): Forms + CSRF

**Nội dung học:**
- 📝 Forms Framework overview
- 🗂️ Form XML definitions
- ✔️ Form validation
- 🔒 CSRF protection
- 📨 Handling form submission
- ⚠️ Error handling
- ✅ Best practices

**Form XML mẫu:**
```xml
<?xml version="1.0"?>
<form xmlns="http://www.demandware.com/xml/form/2008-04-19">
    <field formid="firstname" label="First Name" type="string" mandatory="true" max-length="50"/>
    <field formid="lastname" label="Last Name" type="string" mandatory="true" max-length="50"/>
    <field formid="email" label="Email" type="string" mandatory="true" parse-error="forms.email.invalid">
        <regexp>^[\w.%+-]+@[\w.-]+\.[\w]{2,6}$</regexp>
    </field>
    <action formid="submit" valid-form="true"/>
</form>
```

**Controller xử lý form:**
```javascript
var server = require('server');

server.post('Submit', function (req, res, next) {
    var formName = 'myForm';
    var form = server.forms.getForm(formName);
    
    if (form.valid) {
        var firstname = form.firstname.value;
        var lastname = form.lastname.value;
        var email = form.email.value;
        
        // Process form data
        res.json({ success: true });
    } else {
        res.json({ 
            success: false, 
            error: form.error 
        });
    }
    
    next();
});
```

---

### 📌 Thứ 3 (T3): Forms Bindings

**Nội dung học:**
- 🔄 Dynamic forms
- 🔗 Form binding với objects
- ✔️ Custom validation
- 🏷️ Form field types
- 📋 Lists và options
- 🔀 Conditional fields

---

### 📌 Thứ 4 (T4): Page Designer

**Nội dung học:**
- 🎨 Page Designer Components
- 🧩 Component Types: Layout, Content, Commerce
- 🗺️ Regions và component slots
- 💻 Component scripts
- 🖥️ Component rendering
- ⚙️ Component attributes
- ✅ Best practices

**Component definition mẫu:**
```json
{
    "name": "Custom Banner",
    "description": "A custom banner component",
    "group": "content",
    "attribute_definition_groups": [
        {
            "id": "content",
            "name": "Content",
            "description": "Banner content",
            "attribute_definitions": [
                {
                    "id": "heading",
                    "name": "Heading",
                    "type": "string",
                    "required": true
                },
                {
                    "id": "image",
                    "name": "Image",
                    "type": "image",
                    "required": false
                }
            ]
        }
    ]
}
```

**Component script mẫu:**
```javascript
'use strict';

var Template = require('dw/util/Template');
var HashMap = require('dw/util/HashMap');

module.exports.render = function (context) {
    var model = new HashMap();
    var component = context.component;
    
    model.heading = component.heading;
    model.image = component.image;
    
    return new Template('experience/components/custom/banner').render(model).text;
};
```

---

### 📌 Thứ 5 (T5): Hooks System

**Nội dung học:**
- 🪝 Hook types: script hooks, object hooks
- ✏️ Creating custom hooks
- 📄 hooks.json configuration
- 🔑 Common hooks: `dw.ocapi.*`, `app.*`, `dw.order.*`
- ✅ Hook best practices
- 📊 Hook execution order

**hooks.json mẫu:**
```json
{
    "hooks": [
        {
            "name": "app.payment.processor.basic_credit",
            "script": "./cartridge/scripts/hooks/payment.js"
        },
        {
            "name": "dw.ocapi.shop.basket.afterPOST",
            "script": "./cartridge/scripts/hooks/ocapi.js"
        },
        {
            "name": "dw.order.validateOrder",
            "script": "./cartridge/scripts/hooks/order.js"
        }
    ]
}
```

**Hook script mẫu:**
```javascript
'use strict';

exports.afterBasketCreate = function (basket) {
    var Logger = require('dw/system/Logger');
    Logger.info('Basket created: ' + basket.UUID);
    
    // Custom logic after basket creation
    basket.custom.source = 'mobile';
};

exports.validateOrder = function (order, status) {
    var Status = require('dw/system/Status');
    
    if (!order.billingAddress) {
        return new Status(Status.ERROR, 'MISSING_BILLING_ADDRESS');
    }
    
    return new Status(Status.OK);
};
```

---

### 📌 Thứ 6 (T6): Service Framework

**Nội dung học:**
- 🔧 Service definitions
- 📋 Service profiles
- 🔑 Service credentials
- 🌐 HTTP và SOAP services
- 📨 Request/Response callbacks
- ⚠️ Error handling
- 🧪 Mock services
- ✅ Best practices

**Service definition XML:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<services xmlns="http://www.demandware.com/xml/services/2013-09-15">
    <service service-id="myservice.http" service-type="HTTPService">
        <service-config>
            <service-type>HTTP</service-type>
            <communication-log-enabled>true</communication-log-enabled>
            <timeout-millis>10000</timeout-millis>
        </service-config>
    </service>
</services>
```

**Service script mẫu:**
```javascript
'use strict';

var LocalServiceRegistry = require('dw/svc/LocalServiceRegistry');

var myService = LocalServiceRegistry.createService('myservice.http', {
    createRequest: function (svc, params) {
        svc.setRequestMethod('POST');
        svc.addHeader('Content-Type', 'application/json');
        return JSON.stringify(params);
    },
    
    parseResponse: function (svc, client) {
        return JSON.parse(client.text);
    },
    
    mockCall: function (svc, params) {
        return {
            statusCode: 200,
            statusMessage: 'Success',
            text: JSON.stringify({ success: true })
        };
    },
    
    filterLogMessage: function (msg) {
        // Remove sensitive data from logs
        return msg.replace(/password/gi, '***');
    }
});

// Call the service
var result = myService.call({
    username: 'test',
    action: 'getData'
});

if (result.ok) {
    var data = result.object;
}
```

---

### 📌 Thứ 7 (T7): OCAPI + Tích hợp

**Nội dung học:**
- 🌐 OCAPI advanced topics
- 🔌 Custom endpoints
- 🔔 Webhooks
- 🔗 Third-party integrations
- 🔒 Security best practices
- ⏱️ Rate limiting

---

### 📌 Chủ Nhật (CN): Ôn tổng + 40 câu hỏi

**Nội dung:**
- 📖 Ôn tập toàn bộ kiến thức tuần 4
- ❓ Làm 40 câu hỏi trắc nghiệm
- 💻 Review code examples
- 🏋️ Practice exercises

---

## ✅ Checklist Tuần 4

- [ ] Nắm vững Forms Framework
- [ ] Hiểu CSRF protection
- [ ] Tạo được Page Designer Components
- [ ] Sử dụng được Hooks System
- [ ] Implement được Services
- [ ] Hiểu OCAPI nâng cao
- [ ] Làm 40 câu hỏi ôn tập

---

## 🔗 Tài liệu tham khảo

### Official Documentation
- **[Forms Framework](https://documentation.b2c.commercecloud.salesforce.com/DOC1/topic/com.demandware.dochelp/Forms/FormsFramework.html)**
- **[Hooks Documentation](https://documentation.b2c.commercecloud.salesforce.com/DOC1/topic/com.demandware.dochelp/Hooks/Hooks.html)**
- **[Hook Types](https://documentation.b2c.commercecloud.salesforce.com/DOC1/topic/com.demandware.dochelp/Hooks/HookTypes.html)**
- **[Service Framework](https://documentation.b2c.commercecloud.salesforce.com/DOC1/topic/com.demandware.dochelp/Services/ServicesFramework.html)**
- **[LocalServiceRegistry](https://documentation.b2c.commercecloud.salesforce.com/DOC2/topic/com.demandware.dochelp/DWAPI/scriptapi/html/api/class_dw_svc_LocalServiceRegistry.html)**

### Video Tutorials
- **[B2C Commerce Fast Path Videos](https://help.salesforce.com/s/articleView?id=cc.b2c_fast_path_training.htm)**
- **[Hooks Tutorial](https://www.youtube.com/results?search_query=salesforce+b2c+hooks)**

### Practice
- **[Week 4 Exercises](../Practice/Week4/)**
- **[SFRA Plugin Examples](https://github.com/SalesforceCommerceCloud?q=plugin&type=all)**

---

## 📋 Checklist tuần 4

- [ ] Nắm vững Forms Framework
- [ ] Tạo được Form XML với validation
- [ ] Hiểu CSRF protection
- [ ] Xử lý form submission trong Controller
- [ ] Tạo được Page Designer Components
- [ ] Setup hooks.json và viết Hook scripts
- [ ] Implement được Service Framework với mock
- [ ] Hiểu OCAPI advanced topics
- [ ] Làm 40 câu hỏi ôn tập trong Practice/Week4/
- [ ] Review lại notes và code examples

---

## 🔗 Navigation

- ⬅️ [Tuần 3 - ISML+Ctil](../Week3/)
- ➡️ [Tuần 5 - Ôn tập](../Week5/)
