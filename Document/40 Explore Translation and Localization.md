# Explore Translation and Localization
https://trailhead.salesforce.com/content/learn/modules/b2c-localization/b2c-explore-translation-localization

## English

## Learning Objectives
- Explain the difference between **translation** and **localization**.
- List the general steps you need to take to localize a Salesforce B2C Commerce storefront.
- List why you’d use **country codes**.
- Explain how **localization fallback** works.

## Translation vs Localization
- **Translation**: change content from one language to another (for example English → Spanish).
- **Localization**: adapt a storefront experience for a market/region, beyond text—language, currency, time zones, taxation, and other region-specific expectations.

## Example: configure a user’s preferred locale (Business Manager)
The unit shows how an administrator configures preferred locale per user:
1. Business Manager → App Launcher → **Administration | Organization | Users**
2. Search/open a user record
3. Set **Preferred UI Locale** (example: Organization Default (English (Default)))
4. Set **Preferred Data Locale** (example: Organization Default (Default))
5. Click **Apply**

## Important note (UTF right-to-left limitation)
- The unit notes B2C Commerce does not handle certain **Unicode Transformation Format (UTF)** right-to-left characters in some contexts (example given: gift certificates purchased under **United Arab Emirates Dirham (AED)** currency may not display amounts in list view).
- Suggested workaround: prefix the amount with the currency abbreviation, for example **(AED) 250**, configured in **Merchant Tools > Online Marketing > Gift Certificates**.

## General localization plan (the unit’s initial steps)
The unit provides a simple plan Brandon uses to start localization:
1) Identify storefront components that require localization (examples: **content assets**, **products**, **product attributes**, **currency**).
2) Determine how to architect localization for the business (localized templates vs properties files depending on approach).
3) Identify which languages to support and how they interrelate.

## “How languages interrelate” (architecture choice examples)
- You can use the same underlying business objects for multiple language experiences (example: USA/English and Latin America/Spanish) and let shoppers select location/language so B2C Commerce selects the correct file set.
- If selling by country in Europe, you may need unique catalog data per locale (country-specific product offerings).

## Country codes (why they matter)
- The unit highlights that locales can be language-specific and country-specific, and **country codes** are used to target country-level locale behavior (for example `zh_CN`) rather than only language-level behavior.

## Localization fallback (what it means)
- Localization fallback is the mechanism B2C Commerce uses when a requested locale’s localized data is missing—B2C Commerce falls back to another locale based on configured fallback rules so the storefront can still render meaningful content.

## Tiếng Việt

## Learning Objectives
- Giải thích khác nhau giữa **translation** và **localization**.
- Liệt kê các bước tổng quát để localize storefront Salesforce B2C Commerce.
- Nêu lý do dùng **country codes**.
- Giải thích **localization fallback** hoạt động như thế nào.

## Translation vs Localization
- **Translation**: dịch nội dung từ ngôn ngữ này sang ngôn ngữ khác (ví dụ English → Spanish).
- **Localization**: bản địa hóa trải nghiệm storefront theo thị trường/vùng, không chỉ text mà còn currency, time zones, taxation và các kỳ vọng theo khu vực.

## Ví dụ: cấu hình preferred locale cho user (Business Manager)
Unit hướng dẫn admin cấu hình preferred locale theo user:
1. Business Manager → App Launcher → **Administration | Organization | Users**
2. Tìm/mở user record
3. Set **Preferred UI Locale**
4. Set **Preferred Data Locale**
5. Click **Apply**

## Lưu ý quan trọng (giới hạn UTF right-to-left)
- Unit nêu B2C Commerce không xử lý tốt một số ký tự **UTF** dạng right-to-left trong một số ngữ cảnh (ví dụ gift certificates với currency **AED** có thể không hiển thị amount ở list view).
- Workaround: prefix amount với currency abbreviation, ví dụ **(AED) 250**, cấu hình tại **Merchant Tools > Online Marketing > Gift Certificates**.

## Kế hoạch localization tổng quát (các bước khởi đầu)
Kế hoạch Brandon dùng:
1) Xác định các components cần localization (ví dụ **content assets**, **products**, **product attributes**, **currency**).
2) Quyết định kiến trúc localization (localized templates hoặc properties files tùy approach).
3) Xác định các languages hỗ trợ và cách chúng “liên hệ” với nhau.

## “Liên hệ giữa languages” (ví dụ quyết định kiến trúc)
- Có thể dùng chung underlying business objects cho nhiều trải nghiệm ngôn ngữ (ví dụ USA/English và Latin America/Spanish) và cho shopper chọn location/language để B2C Commerce chọn đúng file set.
- Nếu bán theo từng country ở Europe, có thể cần catalog data riêng theo locale (offerings khác nhau theo quốc gia).

## Country codes (vì sao cần)
- Unit nhấn mạnh locales có thể language-specific và country-specific, và **country codes** giúp target locale theo quốc gia (ví dụ `zh_CN`) thay vì chỉ theo language.

## Localization fallback (ý nghĩa)
- **Localization fallback** là cơ chế B2C Commerce dùng khi thiếu localized data cho locale đang yêu cầu—hệ thống sẽ fallback sang locale khác theo cấu hình để storefront vẫn hiển thị được nội dung.