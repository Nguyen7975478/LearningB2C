# Manage Product Images
https://trailhead.salesforce.com/content/learn/modules/b2c-pricebooks-images-content/b2c-manage-product-images

## English

## Learning Objectives
(As reflected by the unit content)
- Understand the **Image Management System** and how it assigns images (including variation-driven mapping).
- Configure catalog **Image Settings** (image location, view types, variation attribute).
- Build an image **matrix** and understand consistency requirements.
- Understand **Dynamic Imaging Service (DIS)** and what it enables.

## Two ways B2C Commerce manages images
1) **Image Management System**
- Matrix-based image assignment (supports internal or external images).

2) **Dynamic Imaging Service (DIS)**
- On-the-fly image transformation service.

## Image Management System (capabilities)
Supports:
- Multiple images per product.
- Multidimensional access to images and image subsets for variation products and variation attributes.
- Image annotation with **alt text** and **image titles** (localizable).
- Images stored internally in B2C Commerce or referenced externally.

### Image locations (internal vs external)
- Images are addressed by URL reference.
- The image location is set relative to a catalog.
- Default location (if not specified) points to the internal catalog base directory.

## View types (what they are + rules)
- View types represent how an image is used (thumbnail/small/medium/large, swatch, etc.).
- The unit notes:
    - View types must be unique per catalog.
    - You must have at least one view type to assign images.
    - You don’t have to use every view type for every product.
    - You can assign multiple view types to one image.

### Stacking behavior (virtual index)
- When multiple view types are assigned to an image, they act like a stack:
    - First view type = virtual index 0, second = index 1, etc.
    - You can’t explicitly set index numbers or create gaps.
- Best practice: keep related images aligned at the same index positions across view types (for example small index 0 aligns with large index 1 for the same underlying picture concept).

### Swatches
- Swatches are special:
    - Typically one swatch per view type and variant combination.
    - Stacked swatch images are not allowed.
    - Swatches may represent fabric/texture (not only color).

## Variation mapping rule (main product only)
- You can assign images to the **main product** (base/main), not directly to its variations.
- The Image Management System retrieves variation images based on variation attribute value mapping (example: base product uses `color`; the system maps “red” value to identify red variation images).

## Configure catalog image settings (unit walkthrough)
1) Business Manager → Merchant Tools | Site | Products and Catalogs | **Catalogs**
2) Select product catalog: `storefront-catalog-m-en`
3) Edit → **Image Settings** tab
4) Image location: Internal
5) Configure:
    - Variation attribute ID: `color`
    - Default image alt text: `${productname}, ${variationvalue}, ${viewtype}`
    - Default image title: `${productname}, ${variationvalue}`
6) Apply

## Create an image matrix (unit concept)
- Matrix is built per product based on selected variation attributes (example: color, size, length).
- No limit to number of attributes, but structure must be consistent:
    - If one branch is color+fabric+size, another branch cannot be color+size+fabric (ordering must be consistent).
- The unit begins a walkthrough of creating a matrix by opening a base product ID (example shown: `25148430M`) and assigning images through the matrix UI.

## Dynamic Imaging Service (DIS)
- DIS dynamically scales/resizes/crops/overlays/changes format and quality for storefront images.
- Benefit: you can provide one high-resolution source image and let DIS generate needed variants for:
    - product detail page
    - catalog pages
    - recommendations
    - search results
    - and more
- You configure parameters such as size, crop, overlay, background color, quality; DIS serves the appropriate representation per context, reducing pre-generated image workload.

## Tiếng Việt

## Learning Objectives
- Hiểu **Image Management System** và cách gán ảnh (bao gồm mapping theo variation).
- Cấu hình **Image Settings** ở catalog (image location, view types, variation attribute).
- Tạo **image matrix** và hiểu yêu cầu consistency.
- Hiểu **Dynamic Imaging Service (DIS)** và lợi ích.

## 2 cách B2C Commerce quản lý images
1) **Image Management System** (matrix-based, internal/external)
2) **Dynamic Imaging Service (DIS)** (transform ảnh on-the-fly)

## Image Management System (khả năng)
- Nhiều ảnh trên một product.
- Truy cập đa chiều ảnh/nhánh ảnh theo variation products và variation attributes.
- Annotation bằng **alt text** và **image titles** (localizable).
- Ảnh có thể lưu nội bộ hoặc tham chiếu external.

### Image locations
- Tham chiếu bằng URL; location cấu hình theo catalog.
- Default location trỏ về internal catalog base directory.

## View types (khái niệm + rules)
- View types thể hiện cách dùng ảnh (thumbnail/small/medium/large, swatch…).
- Rules:
    - Unique theo catalog
    - Phải có ít nhất 1 view type
    - Không bắt buộc dùng tất cả view types cho mọi product
    - 1 ảnh có thể gán nhiều view types

### Stacking (virtual index)
- Multiple view types trên 1 ảnh hoạt động như stack:
    - view type đầu = index 0, tiếp theo = 1…
    - Không đặt index thủ công, không tạo “khoảng trống”
- Best practice: canh ảnh liên quan cùng vị trí index giữa các view types.

### Swatches
- Swatch đặc biệt:
    - Thường 1 swatch cho mỗi view type + variant combination
    - Không cho phép stacked swatches
    - Có thể dùng cho texture/fabric, không chỉ màu.

## Mapping theo variation (chỉ assign trên main product)
- Chỉ assign images cho **main product**, không assign trực tiếp cho variations.
- System lấy ảnh variation theo mapping variation attribute values (ví dụ attribute `color`: “red” → ảnh của red variation).

## Cấu hình image settings cho catalog (walkthrough)
- Catalogs → chọn `storefront-catalog-m-en` → Edit → Image Settings
- Internal, Variation attribute ID `color`
- Default alt `${productname}, ${variationvalue}, ${viewtype}`
- Default title `${productname}, ${variationvalue}`
- Apply

## Image matrix (khái niệm)
- Tạo matrix theo variation attributes (ví dụ color/size/length).
- Không giới hạn số attributes, nhưng cấu trúc phải consistent (không đảo thứ tự thuộc tính giữa các nhánh).
- Unit bắt đầu hướng dẫn bằng cách mở base product ID (ví dụ `25148430M`) và assign ảnh qua UI matrix.

## Dynamic Imaging Service (DIS)
- DIS scale/resize/crop/overlay/đổi format/quality theo ngữ cảnh.
- Lợi ích: dùng 1 ảnh source độ phân giải cao, DIS tạo các biến thể cho PDP, catalog, recommendations, search results…
- Cấu hình size/crop/overlay/background/quality; DIS serve đúng ảnh theo context, giảm effort tạo nhiều ảnh thủ công.