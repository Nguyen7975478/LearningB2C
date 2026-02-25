# 📚 Tuần 6: Thi thử và Thi chính thức

## 🎯 Mục tiêu tuần

- ✅ Hoàn thành 3 bài thi thử với điểm cao
- ✅ Củng cố kiến thức còn yếu
- ✅ Chuẩn bị tâm lý và kỹ thuật cho thi chính thức
- 🎯 **ĐẬU CHỨNG CHỈ** 🎯

---

## 📅 Lịch trình chi tiết 7 ngày

### 📌 Thứ 2 (T2): THI THỬ LẦN 2 🎯

### Mục tiêu: 80%+

### Trước khi thi:
- [ ] Ôn lại các điểm yếu từ lần thi thử 1
- [ ] Review flashcards
- [ ] Đọc lại notes quan trọng
- [ ] Ngủ đủ giấc đêm trước
- [ ] Chuẩn bị môi trường thi yên tĩnh

### Trong khi thi:
- Áp dụng chiến thuật 3-pass
- Quản lý thời gian tốt hơn
- Đọc kỹ đề, chú ý keywords
- Mark câu chưa chắc để review

### Sau khi thi:
- Ghi lại các câu khó
- Note các topic còn yếu
- Tính điểm theo domain
- Cập nhật tracking sheet

### Mock Exam 2 Results:

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Overall Score | 80%+ | ____% | ⬜ |
| Digital Applications (27%) | 80%+ | ____% | ⬜ |
| Customization (36%) | 85%+ | ____% | ⬜ |
| System & Data (30%) | 80%+ | ____% | ⬜ |
| Maintenance (7%) | 75%+ | ____% | ⬜ |

---

### 📌 Thứ 3 (T3): Ôn điểm yếu

### Phân tích kết quả Mock 2:

**Weak areas từ Mock 2:**
1. ________________________________
2. ________________________________
3. ________________________________
4. ________________________________
5. ________________________________

### Kế hoạch ôn tập targeted:

#### Nếu yếu Digital Applications:
- [ ] Review ISML tags và syntax
- [ ] Practice controller patterns
- [ ] Review Page Designer components
- [ ] Content Assets và Slots
- [ ] SEO best practices

**Key Topics:**
```javascript
// ISML Caching
<iscache type="relative" hour="24" varyby="price_promotion"/>

// Controller Middleware
server.get('Show', 
    middleware1, 
    middleware2, 
    function (req, res, next) {
        // logic
        next();
    }
);

// Page Designer Component
module.exports.render = function (context) {
    var model = new HashMap();
    model.data = context.component.data;
    return new Template('component').render(model).text;
};
```

#### Nếu yếu Customization:
- [ ] Review Forms Framework
- [ ] Practice Hooks implementation
- [ ] Service Framework patterns
- [ ] Resource Bundles
- [ ] Custom objects CRUD

**Key Topics:**
```javascript
// Hooks
{
    "hooks": [
        {
            "name": "dw.ocapi.shop.basket.afterPOST",
            "script": "./cartridge/scripts/hooks/basket.js"
        }
    ]
}

// Service with mock
var service = LocalServiceRegistry.createService('myService', {
    createRequest: function(svc, params) {
        return JSON.stringify(params);
    },
    parseResponse: function(svc, client) {
        return JSON.parse(client.text);
    },
    mockCall: function(svc, params) {
        return { statusCode: 200, text: '{"success":true}' };
    }
});
```

#### Nếu yếu System & Data:
- [ ] Review Product data model
- [ ] Order lifecycle
- [ ] Caching strategies
- [ ] Search configuration
- [ ] OCAPI endpoints

**Key Topics:**
```javascript
// Product Model
var product = ProductMgr.getProduct(pid);
var master = product.getMasterProduct();
var variants = product.getVariants();
var availability = product.getAvailabilityModel();

// Order Management
var order = OrderMgr.createOrder(basket);
order.setPaymentStatus(Order.PAYMENT_STATUS_PAID);
OrderMgr.placeOrder(order);

// OCAPI
GET /s/SiteGenesis/dw/shop/v21_3/products/{id}
POST /s/SiteGenesis/dw/shop/v21_3/baskets
```

#### Nếu yếu Maintenance:
- [ ] Logging best practices
- [ ] Performance optimization
- [ ] Debugging techniques
- [ ] Security practices

---

### 📌 Thứ 4 (T4): THI THỬ LẦN 3 🎯

### Mục tiêu: 85%+

### Pre-exam checklist:
- [ ] Reviewed all weak areas
- [ ] Completed flashcards
- [ ] Good sleep (7-8 hours)
- [ ] Quiet environment prepared
- [ ] Internet connection stable
- [ ] Backup device ready

### Advanced Test Strategies:

**Strategy 1: Time Boxing**
- First 20 questions: 30 minutes (1.5 min each)
- Next 20 questions: 30 minutes (1.5 min each)
- Last 20 questions: 30 minutes (1.5 min each)
- Review: 15 minutes

**Strategy 2: Confidence Levels**
Mark questions as:
- ✅ Confident - Don't review unless time left
- ⚠️ Moderate - Review in Pass 2
- ❓ Unsure - Review in Pass 2 & 3

**Strategy 3: Elimination Method**
1. Read question carefully
2. Eliminate obviously wrong answers
3. If down to 2 options, look for keywords
4. Choose the MOST correct answer

### Common Trap Patterns to Avoid:

❌ **Trap 1: Absolute statements**
- "ALWAYS requires Transaction.wrap()"
- "NEVER use custom objects for..."
- Usually these are FALSE

❌ **Trap 2: Partial truths**
- Answer is mostly correct but has one wrong detail
- Read ALL parts of the answer

❌ **Trap 3: Reverse logic**
- Question asks "Which is NOT..."
- Question asks "All EXCEPT..."

✅ **Good Practice:**
- Underline keywords: NOT, EXCEPT, ALWAYS, BEST
- Double-check negative questions
- Don't overthink - first instinct often correct

### Mock Exam 3 Results:

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Overall Score | 85%+ | ____% | ⬜ |
| Digital Applications (27%) | 85%+ | ____% | ⬜ |
| Customization (36%) | 90%+ | ____% | ⬜ |
| System & Data (30%) | 85%+ | ____% | ⬜ |
| Maintenance (7%) | 80%+ | ____% | ⬜ |

---

### 📌 Thứ 5 (T5): Flashcards + Ôn nhẹ

### Flashcard Topics:

#### ISML Tags
```
Q: What does <iscache> do?
A: Controls page caching with type (relative/daily), duration, and varyby parameters

Q: Difference between isset and var in ISML?
A: isset creates variable in specified scope, var is ECMA standard for local scope

Q: When to use isprint vs ${expression}?
A: isprint for encoding control (htmlcontent, htmlsinglequote), ${} for simple output
```

#### Controllers
```
Q: What is server.extend()?
A: Extends base controller, adds new endpoints without modifying original

Q: What is server.append()?
A: Adds middleware before/after existing route handler

Q: What is server.replace()?
A: Completely replaces existing route handler with new implementation
```

#### Forms
```
Q: How to validate form in controller?
A: form.valid property checks all field validations defined in XML

Q: What is CSRF protection?
A: Cross-Site Request Forgery protection, enabled with csrf-protection="true"
```

#### Hooks
```
Q: Where is hooks.json located?
A: In cartridge root directory, defines hook script mappings

Q: Common hook types?
A: dw.ocapi.*, app.*, dw.order.*, dw.customer.*
```

#### Services
```
Q: Service callback functions?
A: createRequest, parseResponse, mockCall, filterLogMessage, getRequestLogMessage, getResponseLogMessage

Q: How to handle service errors?
A: Check result.ok, result.error, result.status
```

#### Caching
```
Q: Types of caching?
A: Page cache, content slot cache, remote include, pipeline cache

Q: Cache invalidation?
A: Automatic by TTL or manual via cache clear in BM
```

#### Transactions
```
Q: When to use Transaction.wrap()?
A: For ANY write operation to system objects (order, basket, customer, etc.)

Q: Transaction.begin() vs wrap()?
A: begin() requires manual commit/rollback, wrap() handles automatically
```

### Ôn nhẹ - Không học quá sâu:
- [ ] Skim through Week 1-4 notes
- [ ] Review BAD vs GOOD code examples
- [ ] Quick check Domain weightings
- [ ] Practice deep breathing exercises
- [ ] Light exercise for stress relief

---

### 📌 Thứ 6 (T6): Nghỉ ngơi + Chuẩn bị

### ⚠️ KHÔNG HỌC QUÁ NHIỀU HÔM NAY!

### Checklist chuẩn bị thi:

#### Technical Setup:
- [ ] **Computer/Laptop** fully charged or plugged in
- [ ] **Internet connection** stable (test speed > 5 Mbps)
- [ ] **Backup device** ready (tablet/phone)
- [ ] **Backup internet** (mobile hotspot if needed)
- [ ] **Webcam** working (for proctored exam)
- [ ] **Microphone** working
- [ ] **Browser** updated (Chrome recommended)
- [ ] **Pop-up blocker** disabled for exam site
- [ ] **Test exam platform** (take practice test if available)

#### Workspace:
- [ ] **Quiet room** reserved
- [ ] **Door sign** "Do Not Disturb - Taking Exam"
- [ ] **Desk cleared** (only allowed materials)
- [ ] **Good lighting** for webcam
- [ ] **Comfortable chair**
- [ ] **Water bottle** nearby (if allowed)
- [ ] **Timer/Clock** visible

#### Documentation:
- [ ] **Valid government ID** ready
- [ ] **Confirmation email** printed/saved
- [ ] **Exam date/time** confirmed (check timezone!)
- [ ] **Webassessor login** tested

#### Personal:
- [ ] **Good night sleep** planned (8+ hours)
- [ ] **Healthy meal** before exam
- [ ] **Bathroom break** before starting
- [ ] **No caffeine** 2 hours before (avoid jitters)
- [ ] **Relaxation technique** practiced

### Evening Before Exam:
✅ DO:
- Light review of flashcards (15-20 min)
- Organize exam materials
- Set multiple alarms
- Relax with favorite activity
- Early bedtime (8+ hours sleep)

❌ DON'T:
- Study new material
- Stay up late cramming
- Drink too much coffee/energy drinks
- Stress about what you don't know
- Take practice tests

---

### 📌 Thứ 7 (T7): NGÀY THI CHÍNH THỨC 🎯🏆

# 🎓 EXAM DAY - YOU GOT THIS!

## Morning Routine:

### 3 hours before exam:
- [ ] Wake up naturally (no snooze!)
- [ ] Healthy breakfast
- [ ] Light review (15 min max)
- [ ] Positive affirmations

### 2 hours before:
- [ ] Final workspace check
- [ ] Technology test
- [ ] Bathroom break
- [ ] Breathing exercises

### 1 hour before:
- [ ] Log into exam platform
- [ ] Complete check-in process
- [ ] Final desk clear
- [ ] Deep breaths, relax

### 30 minutes before:
- [ ] Light stretching
- [ ] Visualization of success
- [ ] Review quick notes (5 min)
- [ ] Clear your mind

## During Exam - Reminders:

### ⏰ Time Management:
- **105 minutes total**
- **60 questions**
- **1.75 minutes per question average**
- **Mark questions for review**
- **Save 15 min for final review**

### 🧠 Mental Strategy:
- Read EVERY word carefully
- Underline keywords: NOT, EXCEPT, BEST, ALWAYS
- Eliminate wrong answers first
- Trust your preparation
- Don't overthink
- Stay calm if stuck - mark and move on

### ✅ Three-Pass Approach:

**Pass 1 (50 min):**
- Answer confident questions
- Mark unsure questions
- Keep moving forward

**Pass 2 (35 min):**
- Review marked questions
- Apply elimination method
- Make educated guesses

**Pass 3 (20 min):**
- Final review ALL questions
- Double-check marked answers
- Verify no skipped questions
- Submit with confidence!

## After Submitting:

### Immediate Results (usually):
- Pass/Fail status shown immediately
- Detailed score report available later
- Domain breakdown percentages

### If You Pass: 🎉
- **CONGRATULATIONS!**
- Certificate available in 2-5 business days
- Update LinkedIn/Resume
- Share achievement
- Plan celebration!

### If You Don't Pass: 💪
- Don't be discouraged!
- Review score report carefully
- Identify weak domains
- Wait required retake period
- Schedule retake with confidence

---

### 📌 Chủ Nhật (CN): Dự phòng / Celebration

### Nếu đã thi T7:
- 🎉 Celebrate your success!
- 📋 Plan next certification
- 📱 Update professional profiles
- 💼 Apply knowledge to projects

### Nếu chưa thi (rescheduled):
- Follow T7 preparation guide
- Stay calm and confident
- Review flashcards lightly
- Trust your preparation

---

## 📊 Complete Study Tracking:

| Week | Topic | Status | Mock Score | Notes |
|------|-------|--------|------------|-------|
| Week 1 | Setup + Basics | ⬜ | - | _____________ |
| Week 2 | Data + BM | ⬜ | - | _____________ |
| Week 3 | ISML + Controllers | ⬜ | - | _____________ |
| Week 4 | Forms + Hooks | ⬜ | - | _____________ |
| Week 5 | Review + Mock 1 | ⬜ | ___% | _____________ |
| Week 6 | Mock 2 | ⬜ | ___% | _____________ |
| Week 6 | Mock 3 | ⬜ | ___% | _____________ |
| Week 6 | **REAL EXAM** | ⬜ | ___% | _____________ |

## 🎯 Final Exam Stats:

- **Exam Date:** ___/___/______
- **Start Time:** _____:_____
- **End Time:** _____:_____
- **Final Score:** ______%
- **Result:** ⬜ PASS ⬜ FAIL

### Domain Breakdown:
- Digital Applications (27%): ______%
- Customization (36%): ______%
- System & Data (30%): ______%
- Maintenance (7%): ______%

---

## 📚 After Certification:

### Next Steps:
- [ ] Download certificate
- [ ] Add to LinkedIn (Certifications section)
- [ ] Update resume
- [ ] Share on social media
- [ ] Request verification badge (if available)
- [ ] Join Salesforce B2C community
- [ ] Mentor others preparing for exam

### Future Certifications:
- [ ] B2C Commerce Architect
- [ ] Salesforce Administrator
- [ ] Platform Developer I
- [ ] JavaScript Developer I

---

## 💪 Motivational Reminders:

> "Success is not final, failure is not fatal: it is the courage to continue that counts."

> "You've got 6 weeks of solid preparation. Trust yourself!"

> "The expert in anything was once a beginner."

**YOU ARE READY! GO GET THAT CERTIFICATION! 🚀🏆**

---

## ✅ Checklist tuần 6:

- [ ] Thi thử lần 2 (target 80%+)
- [ ] Ôn tập điểm yếu
- [ ] Thi thử lần 3 (target 85%+)
- [ ] Review flashcards
- [ ] Chuẩn bị kỹ thuật và tâm lý
- [ ] THI CHÍNH THỨC
- [ ] ĐẬU CHỨNG CHỈ! 🎉

---

## 🔗 Tài liệu tham khảo

### Official Documentation
- **[Exam Guide](https://trailhead.salesforce.com/credentials/b2ccommercedeveloper)**
- **[Schedule Exam](https://www.webassessor.com/salesforce)**
- **[B2C Commerce InfoCenter](https://documentation.b2c.commercecloud.salesforce.com/DOC1/)**

### Practice Resources
- **[Focus on Force](https://focusonforce.com/)** - Practice exams (paid)
- **[Udemy Practice Tests](https://www.udemy.com/topic/salesforce-b2c-commerce/)** - Various practice tests
- **[Quizlet Flashcards](https://quizlet.com/search?query=salesforce%20b2c%20commerce)** - Community flashcards
- **[Mock Exams](../Practice/MockExams/)**

### Community
- **[Trailblazer Community](https://trailblazers.salesforce.com/)** - Ask questions
- **[Salesforce Stack Exchange](https://salesforce.stackexchange.com/questions/tagged/commerce-cloud)**

---

## 📋 Checklist tuần 6

- [ ] Thi thử lần 2 (target 80%+)
- [ ] Phân tích kết quả Mock 2 và ôn điểm yếu
- [ ] Thi thử lần 3 (target 85%+)
- [ ] Review flashcards toàn bộ
- [ ] Chuẩn bị kỹ thuật (máy tính, internet, webcam)
- [ ] Chuẩn bị tâm lý và ngủ đủ giấc
- [ ] THI CHÍNH THỨC
- [ ] ĐẬU CHỨNG CHỈ! 🎉

---

## 🔗 Navigation

- ⬅️ [Tuần 5 - Ôn tập](../Week5/)
- ➡️ [Practice Exercises](../Practice/)
- 📚 [Resources](../Resources/)

---

## 🎓 GOOD LUCK! YOU'VE GOT THIS! 💪

Remember: **You've prepared well, trust yourself, stay calm, and let your knowledge shine!**
