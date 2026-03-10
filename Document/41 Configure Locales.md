# Configure Locales
https://trailhead.salesforce.com/content/learn/modules/b2c-localization/b2c-configure-locales

## English

## Learning Objectives
- List the settings you need to configure to localize a Salesforce B2C Commerce implementation.
- Explain how to configure **time zones**.
- Explain how to configure a **regional currency format**.
- Describe how to access **geolocation data**.

## What a locale is (unit definition)
- A **locale** represents a specific geographic, political, or cultural region.
- B2C Commerce supports country-specific and language-specific locales in Business Manager UI and storefront data.
- Locale settings can be configured at both **organization** level and **site** level.

## What you configure: Organization (Global) vs Site (Storefront)
The unit provides this mapping:

### Organization (Global)
- Business Manager default user interface language
- The default data language
- Activate/deactivate locales
- Instance time zones
- Store locator data (geolocation)
- Regional settings

### Site (Storefront)
- Storefront currencies
- Locales
- Default country codes
- Store lookup units (miles versus kilometers)

Additionally, you can configure:
- Preferred locales for underlying B2C Commerce data (Products, Content, Orders, Customers, Taxation jurisdiction and rates, System objects)
- Locale-specific URLs
- Preferred locales by user for the Business Manager user interface

## Configure organization settings (global) first
- The unit emphasizes: configure organization-level default + activate locales so they can be used at site level.

### Configure the Default Locale (mandatory)
- The organization-level `default` locale is mandatory and cannot be deactivated.
  Steps shown:
1. Business Manager → App Launcher → **Administration | Organization | Organization Profile**
2. Select default UI language (example: English)
3. Select default data language (example: English)
4. Click **Apply**

### Add a New Locale (example: zh_CN)
Steps shown:
1. Business Manager → App Launcher → **Administration | Global Preferences | Locales**
2. Click **New**
3. Enter ISO 639 alpha-2 language code: `zh`
4. Enter ISO 3166 alpha-2 country code: `CN`
5. Click **Apply**
6. Click Locale ID: `zh_CN`
7. Select a **fallback locale** (example shown: Chinese (zh))
    - This is used if the assigned country locale isn’t available.

Note: The unit references **CLDR** (Unicode Consortium locale data project) as the source of locale data conventions.

## Configure site settings (after org settings)
Once org locales are configured/activated, configure site locales:

### 1) Add currencies to the site
- Business Manager → App Launcher → **Merchant Tools | Site | Site Preferences | Currencies**
- Click **Add** to add currencies.

### 2) Configure locales for the site
- Business Manager → App Launcher → **Merchant Tools | Site | Site Preferences | Locales**
- Select which active locales are allowed
- Mark one locale as default
- Click **Add** to add a new locale

### 3) Add custom site preferences
- Business Manager → App Launcher → **Merchant Tools | Site | Site Preferences | Custom Preferences**
- Configure **default country code**
- Configure **store lookup unit** (kilometers (km) or miles (mi))

## Configure time zones
### Per-site time zone
- Mandatory when creating a site.
- When creating via site import/export without specifying time zone, it defaults to `UTC`.
  Steps shown:
1. Business Manager → App Launcher → **Administration | Sites | Manage Sites > site**
2. Select site time zone (example: `Etc/UTC`)
3. Click **Apply**

### Per-instance time zone
- Used for tasks not site-specific (scheduled/automated jobs).
  Steps shown:
1. Business Manager → App Launcher → **Administration | Global Preferences | Instance Time Zone**
2. Select continent/ocean group (example: US)
3. Select time zone (example: `US/Eastern`)
4. Click **Apply**

## Configure currency + regional settings (format patterns)
- B2C Commerce includes world currency data; you typically don’t add/edit/remove currencies globally, but you configure allowed currencies for a site and configure how currency appears per locale.
- The currency assigned to the organization `default` locale is the primary B2C Commerce locale currency.
- Example: USD uses `$`; other currencies may use letter prefixes (example: A$ for Australian dollar).

### Allowed currencies (site)
1. Business Manager → App Launcher → **Merchant Tools | Site Preferences | Currencies**
2. Select currencies and sort with arrows
3. Click **Add** (you can’t delete default currency)

### Regional Settings (global, not site-specific)
- Regional settings define patterns for:
    1) Date/time
    2) Number format
    3) Currency format
- Formatting conventions:
    - Numbers: **Java DecimalFormat**
    - Date/time: **Java SimpleDateFormat**
- Pattern tips:
    - Use characters `(# , . *)`
    - `*` indicates where the currency symbol is placed
    - Use `_` to represent a space in grouping characters
    - **Fallback Locale** does not affect regional settings (if not defined, system default applies)

Steps shown to edit:
1. Business Manager → **Administration | Global Preferences | Locales**
2. Select a Locale ID
3. Regional Settings tab → specify currency formats

### Copy regional settings (Prefill)
- You can copy settings from one locale to another:
    - Locales → select Locale → Regional Settings → **Prefill** → **Apply**
- Example: reverse separators for Euro format (`#.##0,00`)

## Access geolocation data (Store Locator Data)
- B2C Commerce comes with US and German geolocation data preloaded for testing only.
- For real implementations, purchase/upload your own geolocation database and regularly update it (Salesforce recommends regular imports because accuracy degrades over time).
  Steps shown:
1. Business Manager → **Administration | Global Preferences | Store Locator Data**
2. Select a country
3. Enter ZIP/postal code (example: `02134`)
4. View City, State/Province, Postal Code, Latitude, Longitude

Note: Geolocation module visibility depends on roles (module must be assigned to appropriate roles).

## Tiếng Việt

## Learning Objectives
- Liệt kê các settings cần cấu hình để localize một triển khai B2C Commerce.
- Giải thích cách cấu hình **time zones**.
- Giải thích cách cấu hình **regional currency format**.
- Mô tả cách truy cập **geolocation data**.

## Locale là gì (định nghĩa trong unit)
- **Locale** đại diện cho một vùng địa lý/chính trị/văn hóa cụ thể.
- B2C Commerce hỗ trợ locale theo quốc gia và theo ngôn ngữ trong Business Manager UI và storefront data.
- Locale settings có thể cấu hình ở cấp **organization** và **site**.

## Cấu hình theo cấp: Organization (Global) vs Site (Storefront)
Mapping trong unit:

### Organization (Global)
- Business Manager default user interface language
- Default data language
- Activate/deactivate locales
- Instance time zones
- Store locator data (geolocation)
- Regional settings

### Site (Storefront)
- Storefront currencies
- Locales
- Default country codes
- Store lookup units (miles vs kilometers)

Ngoài ra có thể cấu hình:
- Preferred locales cho underlying data (Products, Content, Orders, Customers, Taxation jurisdiction and rates, System objects)
- Locale-specific URLs
- Preferred locales theo user cho Business Manager UI

## Cấu hình organization settings trước
- Unit nhấn mạnh: phải cấu hình org-level default + activate locales trước để site dùng được.

### Configure the Default Locale (bắt buộc)
- `default` locale ở cấp organization là bắt buộc và không thể deactivate.
  Steps:
1. Business Manager → **Administration | Organization | Organization Profile**
2. Chọn default UI language
3. Chọn default data language
4. **Apply**

### Add a New Locale (ví dụ zh_CN)
Steps:
1. **Administration | Global Preferences | Locales**
2. **New**
3. ISO 639 alpha-2 language code: `zh`
4. ISO 3166 alpha-2 country code: `CN`
5. **Apply**
6. Chọn Locale ID `zh_CN`
7. Chọn **fallback locale** (ví dụ Chinese (zh)) dùng khi country locale không có.

Unit có nhắc **CLDR** (Unicode Consortium) liên quan dữ liệu locale.

## Configure site settings (sau khi org settings xong)
### 1) Add currencies to the site
- **Merchant Tools | Site | Site Preferences | Currencies** → **Add**

### 2) Configure locales for the site
- **Merchant Tools | Site | Site Preferences | Locales**
- Chọn allowed locales, đặt default, **Add** locale mới

### 3) Add custom site preferences
- **Merchant Tools | Site | Site Preferences | Custom Preferences**
- Cấu hình default country code
- Cấu hình store lookup unit (km/mi)

## Configure time zones
### Per-site time zone
- Bắt buộc khi tạo site; nếu tạo qua site import/export mà không chỉ định thì mặc định `UTC`.
  Steps: **Administration | Sites | Manage Sites > site** → chọn time zone (ví dụ `Etc/UTC`) → **Apply**

### Per-instance time zone
- Dùng cho các tác vụ không site-specific (jobs).
  Steps: **Administration | Global Preferences | Instance Time Zone** → chọn vùng (ví dụ US) → chọn `US/Eastern` → **Apply**

## Configure currency + regional settings (format patterns)
- B2C Commerce có sẵn world currency data; bạn cấu hình allowed currencies cho site và cách hiển thị currency theo locale.
- Currency gán cho org `default` locale là primary locale currency.
- Ví dụ ký hiệu: USD dùng `$`, một số currency dùng prefix (A$).

### Allowed currencies (site)
- **Merchant Tools | Site Preferences | Currencies**
- Chọn currency, sắp xếp, **Add** (không xóa được default currency)

### Regional Settings (global, không theo site)
- Regional settings định nghĩa pattern cho date/time, number, currency.
- Conventions:
    - Number: **Java DecimalFormat**
    - Date/time: **Java SimpleDateFormat**
- Tips:
    - Dùng `(# , . *)`
    - `*` chỉ vị trí currency symbol
    - `_` đại diện space
    - **Fallback Locale** không ảnh hưởng regional settings (không cấu hình thì dùng system default)

Edit steps: **Administration | Global Preferences | Locales** → Locale ID → Regional Settings tab.

### Copy regional settings (Prefill)
- Locales → Locale → Regional Settings → **Prefill** → **Apply**
- Ví dụ Euro: đảo dấu phân tách `#.##0,00`

## Access geolocation data (Store Locator Data)
- Có sẵn US/DE geolocation data chỉ để test; production cần mua/upload DB riêng và update định kỳ.
  Steps:
1. **Administration | Global Preferences | Store Locator Data**
2. Chọn country
3. Nhập ZIP/postal code (ví dụ `02134`)
4. Xem City/State/Province/Postal Code/Latitude/Longitude

Note: module geolocation chỉ hiện nếu role được gán module phù hợp.