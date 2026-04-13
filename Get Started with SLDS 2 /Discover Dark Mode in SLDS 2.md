# Discover Dark Mode in SLDS 2
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/dark-mode-in-slds-2-quick-look/discover-dark-mode?trail_id=get-started-with-slds-2

## EN (A-level: detailed, aligned to unit headings)

### Time Estimate / Topics
- Learning Objectives
- What’s New in SLDS 2 Dark Mode
- How Dark Mode Works for Users
- Considerations for Admins and Devs
- Resources

---

## Learning Objectives
After completing this unit, you’ll be able to:
- Identify design changes and user benefits of dark mode in SLDS 2.
- Explain how dark mode is enabled for users and which parts of the UI it affects.
- Outline admin/developer considerations for supporting dark mode. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/dark-mode-in-slds-2-quick-look/discover-dark-mode?trail_id=get-started-with-slds-2))

---

## What’s New in SLDS 2 Dark Mode
- SLDS 2 introduces true dark mode for the Cosmos theme and supported Lightning UIs.
- The dark theme reworks all color tokens, contrast, and iconography for a modern, low-light-optimized experience.
- Not just color inversion: backgrounds, borders, buttons, inputs, popovers, and states are all tuned for dark backgrounds, proper legibility, and accessibility.
- Supported across core Salesforce UI and Lightning components; custom components using styling hooks/tokenized CSS “just work.”

---

## How Dark Mode Works for Users
- Users activate dark mode via their profile menu or browser/system settings (if Salesforce is configured to respect OS appearance).
- The change is immediate and persists for the user.
- Dark mode applies to Home, app pages, navigation, records, and Lightning Apps using SLDS 2/Cosmos; non-converted custom UIs may not fully comply.
- Users can toggle between dark and light at any time.

---

## Considerations for Admins and Devs
- Verify custom branding, CSS overrides, and images for dark mode legibility (use styling hooks whenever possible).
- Avoid hardcoded light colors and overlays.
- Use Salesforce-provided hooks and tokens so app components adapt instantly to dark mode updates.
- Document how to return feedback or report dark mode issues.

---

## Resources
- Salesforce Help: Enable Dark Mode for Your Org
- SLDS 2 Documentation: Styling Hooks & Tokens
- Trailblazer Community: Dark Mode Questions

---

## VI (A-level: đúng Topics, rõ admin/dev)

### Thời lượng / Topics
- Learning Objectives
- SLDS 2 Dark Mode mới có gì
- Người dùng bật dark mode như thế nào
- Lưu ý cho admin/dev
- Resources

---

### Mục tiêu học
- Nhận diện thay đổi thiết kế và lợi ích user khi dùng dark mode SLDS 2.
- Giải thích cách user bật dark mode và phạm vi tác động.
- Đưa checklist cho admin/dev để hỗ trợ dark mode tốt nhất. ([trailhead.salesforce.com](https://trailhead.salesforce.com/content/learn/modules/dark-mode-in-slds-2-quick-look/discover-dark-mode?trail_id=get-started-with-slds-2))

---

### Dark mode mới
- SLDS 2 có dark mode đúng chuẩn cho theme Cosmos; cập nhật lại toàn bộ token màu/icon/contrast để tối ưu cho mắt và phù hợp khi làm việc ban đêm.
- Không đơn giản đảo màu: mọi chi tiết visual được điều chỉnh để rõ trên nền tối, từ border, button, input đến transition state.
- Custom component dùng styling hooks/token CSS sẽ tự động update khi sang dark mode.

---

### User bật dark mode ra sao
- User chọn option dark mode trong profile hoặc theo setting OS/browsers (nếu org bật đủ).
- Apply ngay, nhớ setting cho user.
- Áp dụng cho Home/app/navigation/record/Lightning App dùng Cosmos/SLDS 2; custom UI legacy có thể không đồng bộ hoàn toàn.

---

### Admin/Dev cần làm gì?
- Check custom branding/CSS/image xem đã chuẩn cho dark mode chưa (ưu tiên styling hooks).
- Tránh hardcode màu sáng.
- Dùng hooks/tokens để custom component tự update khi org chuyển theme.
- Hướng dẫn user feedback khi gặp lỗi dark mode.

---

### Resources
- Salesforce Help: Enable Dark Mode
- SLDS 2 Docs
- Trailblazer: Dark Mode