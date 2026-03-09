# Set Up Search Recommendations

## Metadata

| Field        | Value                                                                                                                                                        |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Source URL   | https://trailhead.salesforce.com/content/learn/modules/cc-einstein-smarter-search/cc-einstein-search-recommendations?trail_id=set-up-merchandising-for-your-storefront |
| Created Date | 2026-03-09                                                                                                                                                   |

---

# 🇬🇧 English (EN)

## Learning Objectives

After completing this unit, you'll be able to:

- Explain what Einstein Search Recommendations are and how they benefit shoppers.
- Describe the types of search recommendations available in Agentforce Commerce for B2C.
- Identify the prerequisites and opt-in steps needed to enable Einstein Search Recommendations.
- Configure and test Search Recommendations in Business Manager.
- Apply best practices and avoid common pitfalls.

---

## Key Concepts: Search Recommendations & Einstein's Role

**Search Recommendations** is an AI-powered feature of Commerce Cloud Einstein that enhances the storefront search experience by suggesting relevant queries, products, and content as shoppers type in the search bar.

| Aspect | Description |
|---|---|
| **What it is** | A real-time, predictive feature that surfaces query completions and curated results while shoppers are still typing. |
| **Einstein's role** | Einstein analyzes aggregated, anonymized search behavior data across many merchants and uses machine learning models to rank and surface the most relevant suggestions for each site. |
| **Benefit** | Reduces the number of keystrokes required to find products, lowers zero-result searches, and increases conversion by guiding shoppers to popular or trending queries. |
| **Data source** | Live search event data collected from the merchant's storefront (with shopper consent); Einstein continuously refines its model as more data is gathered. |

---

## Types of Search Recommendations

Einstein Search Recommendations provides several flavors of assistance, each surfacing at a different stage of the shopping journey:

| Recommendation Type | Description | Storefront Appearance |
|---|---|---|
| **Search Phrase Suggestions** | Auto-completes partial search terms with popular or trending phrases based on historical site searches. | Dropdown list beneath the search input field as the shopper types. |
| **Trending Searches** | Highlights keywords that are gaining search volume on the site right now. | Displayed in the typeahead panel before the shopper starts typing (empty-state). |
| **Recent Searches** | Surfaces query terms the same shopper has previously entered (cookie/session based). | Listed below "Trending Searches" in the typeahead panel. |
| **Product Recommendations** | Suggests individual products matching the partial query. | Shown alongside phrase suggestions in the typeahead panel (product name + image + price). |
| **Content Recommendations** | Returns relevant content pages or articles matching the partial query. | Included in the typeahead panel when content search is enabled for the site. |

> **Note:** The exact combination of recommendation types that appear depends on the storefront implementation (cartridge or headless), the page controller/component configuration, and which Einstein features are enabled in Business Manager.

---

## Prerequisites & Business Manager Setup

### 1 – Einstein Opt-In (Privacy Agreement)

> Must be completed by an **administrator** on the **staging (or production) instance**.

1. In Business Manager, go to **Administration → Global Preferences → Einstein Recommendations Opt-In** (or **Einstein Commerce Insights Opt-In** depending on your version).
2. Review and accept the **Einstein Data Privacy Agreement**.
3. Click **Save**.

> Without opt-in, the Einstein APIs return empty results and no recommendations will be displayed.

### 2 – Enable Search Recommendations for the Site

1. Navigate to **Merchant Tools → Site → Site Preferences → Search Preferences**.
2. Locate the **Einstein Search Recommendations** section.
3. Set the toggle to **Enabled**.
4. Click **Save**.

### 3 – Locale Configuration

1. In the same **Search Preferences** page, confirm the correct **default locale** is set.
2. If the site supports multiple locales, verify that Einstein is enabled for each active locale.
3. Recommendations are locale-aware — the model matches the shopper's active locale.

### 4 – Rebuild the Search Index

After enabling Einstein Search Recommendations, a full search index rebuild is recommended to ensure all product and content data is properly indexed.

1. Go to **Merchant Tools → Site → Search → Search Indexes**.
2. Select the relevant index type(s) (Product, Content).
3. Click **Rebuild**.
4. Wait for the rebuild to complete before testing.

---

## Configuration & Testing

### Enable / Disable Recommendations

- Recommendations can be toggled on or off per site at any time from **Merchant Tools → Site → Site Preferences → Search Preferences → Einstein Search Recommendations**.
- Changes take effect immediately without a reindex.

### Placement & Slots

- For **SiteGenesis / SFRA cartridge-based** storefronts: the search typeahead component in the cartridge renders recommendations automatically once the feature is enabled and the cartridge is up to date.
- For **headless / PWA** implementations: recommendations are fetched via the **Einstein API** (`/recommendations` endpoint) and rendered by the frontend component. Confirm the API integration is wired to the search bar component.
- **Content slots** are not typically used for typeahead recommendations. However, product recommendation carousels on the search results page (e.g., "Customers also viewed") may use Einstein Recommendation slots configured under **Merchant Tools → Site → Online Marketing → Einstein Recommendations**.

### Verifying Recommendations Work

1. Open the storefront in an **incognito/private browser** window (to avoid cached data).
2. Begin typing a common search term (e.g., "dress", "shoe") in the search bar.
3. Verify that a dropdown panel appears with suggested phrases and/or product tiles.
4. Check that suggestions are relevant to the typed characters and not generic.
5. In Business Manager, check **Merchant Tools → Site → Search → Search Recommendations** to review logged suggestion data (if available in your version).
6. Use browser developer tools → **Network tab** to confirm calls to the Einstein API are returning `200 OK` with populated suggestion data.

---

## Best Practices & Common Issues

### Best Practices

| Practice | Reason |
|---|---|
| Accept the privacy opt-in on **staging first**, then promote to production. | Prevents data collection issues in production before setup is verified. |
| Allow **2–4 weeks** of data collection before evaluating recommendation quality. | Einstein needs sufficient traffic data to build reliable suggestion models. |
| Run a **full reindex** after making significant catalog changes. | Ensures new/updated products are eligible to surface in product recommendations. |
| Test in **multiple locales** if the site is multilingual. | Locale mismatches can cause empty or incorrect recommendations. |
| Monitor **zero-result search rates** before and after enabling recommendations. | A decrease in zero-result searches is a strong indicator that recommendations are working. |
| Keep the **SFRA/cartridge** up to date. | Older versions may lack support for newer Einstein recommendation types. |

### Common Issues

| Issue | Likely Cause | Resolution |
|---|---|---|
| No recommendations appear in the typeahead | Einstein opt-in not accepted, feature disabled, or insufficient data. | Verify opt-in, enable in Site Preferences, allow time for data collection. |
| Recommendations are irrelevant or generic | Model hasn't been trained on enough site-specific data yet. | Wait for more traffic; check that the correct site ID is configured. |
| Recommendations appear in one locale but not another | Einstein not enabled for the additional locale(s). | Enable recommendations for each locale in Search Preferences. |
| API calls return 401/403 errors | Incorrect or missing Einstein API credentials/configuration. | Verify that the Einstein API client ID is correctly set in Business Manager. |
| Product tiles in typeahead show broken images | Product image path misconfiguration in the cartridge settings. | Check the image view type configured in the cartridge metadata. |
| Recommendations don't update after catalog changes | Search index is stale. | Trigger a full search index rebuild. |

---

## Next Steps

- Proceed to the next unit: **Set Up Einstein Predictive Sort** to further personalize the search results ranking for each individual shopper.
- Explore **Einstein Commerce Insights** to analyze which search terms and recommendations are driving the most revenue.
- Review the **Commerce Cloud Einstein Activity Dashboard** in Business Manager to monitor recommendation click-through rates and engagement metrics.

---

---

# 🇻🇳 Tiếng Việt (VI)

## Mục Tiêu Học Tập

Sau khi hoàn thành bài học này, bạn có thể:

- Giải thích Einstein Search Recommendations là gì và lợi ích mang lại cho khách hàng mua sắm.
- Mô tả các loại gợi ý tìm kiếm có trong Agentforce Commerce for B2C.
- Xác định các điều kiện tiên quyết và bước opt-in cần thiết để bật Einstein Search Recommendations.
- Cấu hình và kiểm tra Search Recommendations trong Business Manager.
- Áp dụng các thực hành tốt và tránh các lỗi thường gặp.

---

## Khái Niệm Chính: Search Recommendations & Vai Trò Của Einstein

**Search Recommendations** là tính năng được hỗ trợ bởi AI của Commerce Cloud Einstein, giúp nâng cao trải nghiệm tìm kiếm trên storefront bằng cách gợi ý các truy vấn, sản phẩm và nội dung liên quan khi khách hàng đang nhập từ khóa vào ô tìm kiếm.

| Khía Cạnh | Mô Tả |
|---|---|
| **Định nghĩa** | Tính năng dự đoán theo thời gian thực, hiển thị các gợi ý hoàn thiện truy vấn và kết quả được tuyển chọn trong khi khách hàng vẫn đang gõ. |
| **Vai trò của Einstein** | Einstein phân tích dữ liệu hành vi tìm kiếm tổng hợp, ẩn danh từ nhiều merchant và sử dụng các mô hình học máy để xếp hạng và hiển thị gợi ý phù hợp nhất cho từng site. |
| **Lợi ích** | Giảm số lần gõ phím cần thiết để tìm thấy sản phẩm, giảm tỷ lệ tìm kiếm không có kết quả, tăng tỷ lệ chuyển đổi bằng cách hướng khách hàng đến các truy vấn phổ biến hoặc đang thịnh hành. |
| **Nguồn dữ liệu** | Dữ liệu sự kiện tìm kiếm trực tiếp được thu thập từ storefront của merchant (với sự đồng ý của người mua); Einstein liên tục tinh chỉnh mô hình khi có thêm dữ liệu. |

---

## Các Loại Search Recommendations

Einstein Search Recommendations cung cấp nhiều dạng hỗ trợ khác nhau, mỗi dạng xuất hiện ở một giai đoạn khác nhau trong hành trình mua sắm:

| Loại Gợi Ý | Mô Tả | Hiển Thị Trên Storefront |
|---|---|---|
| **Gợi Ý Cụm Từ Tìm Kiếm** | Tự động hoàn thiện từ khóa đang nhập với các cụm từ phổ biến hoặc đang thịnh hành dựa trên lịch sử tìm kiếm của site. | Danh sách thả xuống bên dưới ô nhập tìm kiếm khi khách hàng đang gõ. |
| **Tìm Kiếm Đang Thịnh Hành** | Nổi bật các từ khóa đang tăng lượng tìm kiếm trên site ngay lúc đó. | Hiển thị trong bảng typeahead trước khi khách hàng bắt đầu gõ (trạng thái trống). |
| **Tìm Kiếm Gần Đây** | Hiển thị các từ khóa mà chính khách hàng đó đã nhập trước đây (dựa trên cookie/phiên). | Liệt kê bên dưới "Trending Searches" trong bảng typeahead. |
| **Gợi Ý Sản Phẩm** | Gợi ý các sản phẩm cụ thể phù hợp với từ khóa đang nhập một phần. | Hiển thị cùng với gợi ý cụm từ trong bảng typeahead (tên sản phẩm + hình ảnh + giá). |
| **Gợi Ý Nội Dung** | Trả về các trang nội dung hoặc bài viết liên quan phù hợp với từ khóa đang nhập. | Được bao gồm trong bảng typeahead khi tính năng tìm kiếm nội dung được bật cho site. |

> **Lưu ý:** Sự kết hợp chính xác của các loại gợi ý xuất hiện phụ thuộc vào cách triển khai storefront (cartridge hoặc headless), cấu hình controller/component trang, và những tính năng Einstein nào được bật trong Business Manager.

---

## Điều Kiện Tiên Quyết & Thiết Lập Trong Business Manager

### Bước 1 – Chấp Nhận Thỏa Thuận Quyền Riêng Tư Einstein (Opt-In)

> Phải được thực hiện bởi **quản trị viên** trên **môi trường staging (hoặc production)**.

1. Trong Business Manager, vào **Administration → Global Preferences → Einstein Recommendations Opt-In** (hoặc **Einstein Commerce Insights Opt-In** tùy phiên bản).
2. Đọc và chấp nhận **Einstein Data Privacy Agreement**.
3. Nhấp **Save**.

> Nếu chưa opt-in, các API Einstein sẽ trả về kết quả trống và không có gợi ý nào được hiển thị.

### Bước 2 – Bật Search Recommendations Cho Site

1. Điều hướng đến **Merchant Tools → Site → Site Preferences → Search Preferences**.
2. Tìm phần **Einstein Search Recommendations**.
3. Đặt toggle sang **Enabled**.
4. Nhấp **Save**.

### Bước 3 – Cấu Hình Locale

1. Trong cùng trang **Search Preferences**, xác nhận **locale mặc định** được đặt đúng.
2. Nếu site hỗ trợ nhiều locale, hãy xác minh Einstein được bật cho từng locale đang hoạt động.
3. Gợi ý tìm kiếm có nhận thức về locale — mô hình sẽ khớp với locale đang hoạt động của khách hàng.

### Bước 4 – Xây Dựng Lại Chỉ Mục Tìm Kiếm

Sau khi bật Einstein Search Recommendations, nên thực hiện rebuild chỉ mục tìm kiếm đầy đủ để đảm bảo toàn bộ dữ liệu sản phẩm và nội dung được lập chỉ mục đúng cách.

1. Vào **Merchant Tools → Site → Search → Search Indexes**.
2. Chọn loại chỉ mục liên quan (Sản phẩm, Nội dung).
3. Nhấp **Rebuild**.
4. Chờ quá trình rebuild hoàn tất trước khi kiểm tra.

---

## Cách Cấu Hình & Kiểm Tra

### Bật / Tắt Gợi Ý

- Gợi ý có thể bật hoặc tắt theo từng site bất kỳ lúc nào từ **Merchant Tools → Site → Site Preferences → Search Preferences → Einstein Search Recommendations**.
- Thay đổi có hiệu lực ngay lập tức mà không cần reindex.

### Vị Trí Hiển Thị & Slots

- Với storefront dựa trên **SiteGenesis / SFRA cartridge**: component typeahead tìm kiếm trong cartridge tự động hiển thị gợi ý khi tính năng được bật và cartridge đã được cập nhật.
- Với triển khai **headless / PWA**: gợi ý được lấy qua **Einstein API** (endpoint `/recommendations`) và được hiển thị bởi frontend component. Xác nhận tích hợp API đã được kết nối với component thanh tìm kiếm.
- **Content slots** thường không được dùng cho gợi ý typeahead. Tuy nhiên, các carousel gợi ý sản phẩm trên trang kết quả tìm kiếm (ví dụ: "Khách hàng cũng xem") có thể sử dụng Einstein Recommendation slots được cấu hình tại **Merchant Tools → Site → Online Marketing → Einstein Recommendations**.

### Xác Nhận Gợi Ý Hoạt Động

1. Mở storefront trong cửa sổ trình duyệt **ẩn danh/riêng tư** (để tránh dữ liệu được cache).
2. Bắt đầu nhập một từ khóa tìm kiếm phổ biến (ví dụ: "dress", "shoe") vào thanh tìm kiếm.
3. Xác nhận rằng một bảng thả xuống xuất hiện với các cụm từ gợi ý và/hoặc tile sản phẩm.
4. Kiểm tra rằng các gợi ý phù hợp với các ký tự đã gõ và không chỉ là gợi ý chung chung.
5. Trong Business Manager, kiểm tra **Merchant Tools → Site → Search → Search Recommendations** để xem lại dữ liệu gợi ý đã được ghi lại (nếu có trong phiên bản của bạn).
6. Sử dụng công cụ developer của trình duyệt → **tab Network** để xác nhận các lần gọi đến Einstein API đang trả về `200 OK` với dữ liệu gợi ý được điền đầy đủ.

---

## Thực Hành Tốt & Lỗi Thường Gặp

### Thực Hành Tốt

| Thực Hành | Lý Do |
|---|---|
| Chấp nhận privacy opt-in trên **staging trước**, sau đó mới đưa lên production. | Ngăn ngừa các vấn đề thu thập dữ liệu trong production trước khi thiết lập được xác minh. |
| Chờ **2–4 tuần** thu thập dữ liệu trước khi đánh giá chất lượng gợi ý. | Einstein cần đủ dữ liệu lưu lượng truy cập để xây dựng mô hình gợi ý đáng tin cậy. |
| Chạy **reindex đầy đủ** sau khi thực hiện thay đổi đáng kể trong catalog. | Đảm bảo sản phẩm mới/được cập nhật đủ điều kiện xuất hiện trong gợi ý sản phẩm. |
| Kiểm tra **nhiều locale** nếu site đa ngôn ngữ. | Không khớp locale có thể gây ra gợi ý trống hoặc không chính xác. |
| Theo dõi **tỷ lệ tìm kiếm không có kết quả** trước và sau khi bật gợi ý. | Tỷ lệ giảm là chỉ số mạnh cho thấy gợi ý đang hoạt động hiệu quả. |
| Giữ **SFRA/cartridge** được cập nhật. | Các phiên bản cũ hơn có thể thiếu hỗ trợ cho các loại gợi ý Einstein mới hơn. |

### Lỗi Thường Gặp

| Lỗi | Nguyên Nhân Có Thể | Cách Giải Quyết |
|---|---|---|
| Không có gợi ý nào xuất hiện trong typeahead | Chưa chấp nhận Einstein opt-in, tính năng bị tắt, hoặc không đủ dữ liệu. | Xác minh opt-in, bật trong Site Preferences, chờ đủ thời gian thu thập dữ liệu. |
| Gợi ý không liên quan hoặc quá chung chung | Mô hình chưa được đào tạo với đủ dữ liệu đặc thù của site. | Chờ thêm lưu lượng truy cập; kiểm tra site ID được cấu hình đúng chưa. |
| Gợi ý xuất hiện ở một locale nhưng không ở locale khác | Einstein chưa được bật cho các locale bổ sung. | Bật gợi ý cho từng locale trong Search Preferences. |
| Lỗi 401/403 khi gọi API | Thiếu hoặc sai thông tin xác thực Einstein API. | Xác minh Einstein API client ID được cấu hình đúng trong Business Manager. |
| Tile sản phẩm trong typeahead hiển thị hình ảnh bị lỗi | Cấu hình đường dẫn hình ảnh sai trong cài đặt cartridge. | Kiểm tra loại view hình ảnh được cấu hình trong metadata của cartridge. |
| Gợi ý không cập nhật sau khi thay đổi catalog | Chỉ mục tìm kiếm bị cũ. | Kích hoạt rebuild chỉ mục tìm kiếm đầy đủ. |

---

## Các Bước Tiếp Theo

- Tiến hành bài tiếp theo: **Set Up Einstein Predictive Sort** để cá nhân hóa thêm thứ hạng kết quả tìm kiếm cho từng khách hàng riêng lẻ.
- Khám phá **Einstein Commerce Insights** để phân tích các từ khóa tìm kiếm và gợi ý nào đang tạo ra doanh thu nhiều nhất.
- Xem lại **Commerce Cloud Einstein Activity Dashboard** trong Business Manager để theo dõi tỷ lệ nhấp qua gợi ý và các chỉ số tương tác.
