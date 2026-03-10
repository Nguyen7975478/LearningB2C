# Configure Import and Export
https://trailhead.salesforce.com/content/learn/modules/b2c-import-export/b2c-configure-import-export

## English

### Learning Objectives
- List three types of permissions an administrator needs to perform import/export.
- List three basic steps of the import process.
- List three basic steps of the export process.
- Explain the purpose of site import/export.
- Describe two ways to deal with transfer limitations.

### Permissions (3 required areas)
- Access to **Site import/export** (all site information).
- Access to **Import/export** (storefront information such as products/content).
- **WebDAV** access to log files and import/export directories.
- Note: requesting an FTP port from Support may be needed for developer-provided **FTPClient** scripts.

### Import process (3 basic steps)
- Transfer the import file to the instance (Business Manager upload / file transfer mechanism).
- Run the import job/process in Business Manager (choose file + mode + execute).
- Validate results via logs and data verification.

### Export process (3 basic steps)
- Run export in Business Manager (select export type/criteria, generate file).
- Transfer the export file out (to external **OMS** or other system) using WebDAV/FTP/HTTPS.
- Validate exported data and archive as needed.

### Catalog import (what the unit walks through)
- Prepare catalog XML from external **PIM** following `catalog.xsd`.
- In Business Manager (Import & Export for Products and Catalogs):
  - Upload (optionally compress)
  - Validate/analyze
  - Execute import using the selected mode (example: **merge**)

### Order export (what the unit walks through)
- In Business Manager (Ordering Import & Export):
  - Select orders + file naming
  - Export options include “Update Order Export Status and Inventory”
  - Download/compress and transfer to **OMS**
- Emphasis: secure transfer is best practice due to **PCI-DSS** and OMS requirements.

### Site import/export (purpose + steps)
- Purpose: snapshot and restore site configuration/data across instances (commonly to bring new developer environments online).
- Export: provide archive name, select data, export, download zip.
- Import: choose local file and import on receiving instance.

### Transfer limitations + mitigation
- Size limits called out in the unit include:
  - Standard import processing limit: **1,000 business objects**
  - WebDAV push upload limit: **100 MB**
  - FTP/WebDAV download into a file: **200 MB**
  - Export upload limit mentioned: **500 MB**
- Mitigations:
  - Use compression (**gzip** / **zip**)
  - Use **delta feeds** (where applicable)

### Compression formats
- **gzip** (`.gz`): supported for standard imports and import pipelets (`catalog.xml.gz`).
- **zip** (`.zip`): single-file zip/unzip supported; Business Manager auto-unzips on upload.

### Delta feeds
- Recommended for imports other than catalog data: only differences between current and previous XML.
- Limitation: delta catalog feed can’t include elements that override global mode with element-specific mode (example: bundled-products using replace).

### Static files (images) and WebDAV
- XML contains persistent database objects + references.
- Static assets (product images) live in the instance file system; use **WebDAV** to upload/download.

### Why archive
- XML imports can’t be rolled back; archive previous XML before importing.
- If new XML fails validation, re-import archived prior version.
- Delete old files periodically (keep the last file) to prevent accumulation.

## Tiếng Việt

### Learning Objectives
- Liệt kê 3 loại permissions admin cần cho import/export.
- Liệt kê 3 bước cơ bản của import process.
- Liệt kê 3 bước cơ bản của export process.
- Giải thích mục đích của site import/export.
- Mô tả 2 cách xử lý transfer limitations.

### Permissions (3 nhóm)
- Quyền **Site import/export** (all site information).
- Quyền **Import/export** (products/content).
- Quyền **WebDAV** truy cập logs và import/export directories.
- Có thể cần xin FTP port từ Support nếu dùng **FTPClient** scripts.

### Import process (3 bước cơ bản)
- Transfer import file lên instance (upload/transfer).
- Chạy import trong Business Manager (chọn file + mode + execute).
- Validate kết quả bằng logs và kiểm tra dữ liệu.

### Export process (3 bước cơ bản)
- Chạy export trong Business Manager (chọn loại/tiêu chí, generate file).
- Transfer file export ra ngoài (ví dụ sang **OMS**) bằng WebDAV/FTP/HTTPS.
- Validate dữ liệu export và archive khi cần.

### Catalog import (unit hướng dẫn)
- Chuẩn bị catalog XML từ **PIM** theo `catalog.xsd`.
- Trong Business Manager:
  - Upload (có thể compress)
  - Validate/analyze
  - Import theo mode (ví dụ **merge**)

### Order export (unit hướng dẫn)
- Trong Business Manager:
  - Chọn orders + đặt tên file
  - Option “Update Order Export Status and Inventory”
  - Download/compress và transfer sang **OMS**
- Nhấn mạnh secure transfer vì **PCI-DSS** và OMS requirements.

### Site import/export (mục đích + steps)
- Mục đích: snapshot/restore site config + data giữa instances (thường để bring up dev env).
- Export: archive name → chọn data → export → download zip.
- Import: chọn local file → import ở receiving instance.

### Transfer limitations + cách xử lý
- Các limits trong unit:
  - Standard import limit: **1,000 business objects**
  - WebDAV push upload: **100 MB**
  - FTP/WebDAV download into a file: **200 MB**
  - Export upload limit: **500 MB**
- Cách xử lý:
  - Dùng compression (**gzip** / **zip**)
  - Dùng **delta feeds** khi phù hợp

### Compression
- **gzip** (`.gz`): hỗ trợ standard imports và import pipelets (`catalog.xml.gz`).
- **zip** (`.zip`): zip/unzip theo từng file; Business Manager auto-unzip khi upload.

### Delta feeds
- Khuyến nghị cho imports không phải catalog data: chỉ phần khác biệt so với XML trước.
- Hạn chế: delta catalog feed không dùng được nếu có elements override global mode bằng element-specific mode (ví dụ bundled-products dùng replace).

### Static files và WebDAV
- XML chứa database objects + references.
- Static assets (product images) nằm trong instance file system; dùng **WebDAV** upload/download.

### Why archive
- XML imports không rollback được; archive XML cũ trước khi import.
- Nếu XML mới fail validation thì import lại bản archived.
- Dọn file cũ định kỳ (giữ file gần nhất).