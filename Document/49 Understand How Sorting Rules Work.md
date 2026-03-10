# Understand How Sorting Rules Work
https://trailhead.salesforce.com/content/learn/modules/b2c-storefront-sorting-rules/b2c-how-sorting-rules-work

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain the Salesforce B2C Commerce inheritance model for process sorting rules.
- State the importance of the default sorting rule.
- Explain how B2C Commerce breaks sorting rule ties.
- List the sorting rules best practice sort order.

## The foundation: the `default` sorting rule
- Sorting rule processing is grounded in the **`default` sorting rule**.
- The default sorting rule uses the storefront’s catalog/category structure (navigation structure).
- Navigation is category-driven browsing; keyword search is query-driven.

## Inheritance model (how rules are picked)
- Sorting rules can be assigned at different levels (root category vs subcategory).
- Categories inherit from the navigational catalog’s root sorting rule unless overwritten at a subcategory level.
- This inheritance is key to managing large catalogs without manually assigning rules everywhere.

## How sorting rules evaluate and break ties (layered evaluation)
- During result sorting, B2C Commerce evaluates products by the **first attribute** in the sorting rule.
- If there’s a tie, it uses the **second attribute** to break ties among products tied on the first.
- Then it uses the **third attribute** to break ties among products tied on the first and second, and so on until it reaches the end of the attribute list.

## What happens if products still tie (or have null values)
- After evaluating all attributes, if products:
    - match exactly on all attributes, or
    - have null values for the rule’s attributes,
      then B2C Commerce falls back to the **default sorting rules**.
- In that case, products are returned based on the order in which they are stored in the **search index**.

## Best practice sort order (guidance concept)
- The unit frames a best-practice idea: start with manual/intent-driven attributes where needed, then break ties with strong business signals, and finally rely on stable default/index ordering.
- This is important because a poorly designed rule can create unpredictable ties and inconsistent shopper experiences.

## Example-driven learning (unit scenario)
- The unit states Brandon creates multiple sorting rules to test sorting five products, including using:
    - `product.searchPlacement` (manual placement first, then product name ascending)
    - an active data attribute such as `activeData.returnRate` (lowest return rate ascending)
- This demonstrates how tie-breaking and layered attributes produce deterministic sequences.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích inheritance model của sorting rules trong B2C Commerce.
- Nêu tầm quan trọng của default sorting rule.
- Giải thích B2C Commerce break ties như thế nào.
- Liệt kê best practice sort order (khuyến nghị).

## Nền tảng: `default` sorting rule
- Xử lý sorting dựa trên **`default` sorting rule**.
- Default rule dựa vào cấu trúc catalog/category (navigation).
- Navigation là browse theo category; keyword search là tìm theo query.

## Inheritance model (chọn rule như thế nào)
- Sorting rules có thể gán ở nhiều cấp (root category, subcategory).
- Subcategories inherit rule từ root nếu không override.
- Inheritance giúp quản lý catalog lớn mà không phải gán rule từng nơi.

## Cách evaluate + break ties (xếp theo lớp)
- B2C Commerce dùng **attribute đầu tiên** để rank.
- Tie → dùng **attribute thứ hai** để break tie.
- Tie tiếp → dùng attribute thứ ba… cho đến hết danh sách attributes.

## Nếu vẫn tie hoặc null
- Nếu tie trên tất cả attributes hoặc có null values, hệ thống fallback về **default sorting rules**.
- Khi đó, thứ tự dựa trên cách products được lưu trong **search index**.

## Best practice sort order (ý nghĩa)
- Khuyến nghị tổng quát: dùng manual/intent-driven attributes khi cần, rồi break ties bằng business signals mạnh, cuối cùng fallback ổn định theo default/index.
- Nếu thiết kế rule kém, sẽ tạo nhiều ties và làm trải nghiệm không nhất quán.

## Ví dụ trong unit
- Unit nói Brandon tạo nhiều rules để test 5 products, gồm:
    - `product.searchPlacement` (placement trước, sau đó product name ascending)
    - `activeData.returnRate` (return rate thấp nhất lên trước, ascending)
- Ví dụ này minh họa cơ chế tie-breaking và layering.