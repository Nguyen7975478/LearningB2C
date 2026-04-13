1.   A developer needs to deploy a new cartridge to a sandbox. Which protocol is primarily used by the IDE to upload files to the version directory?

     -   A. `SFTP`

     -   <u>**B. `WebDAV`**</u>

         -> √ WebDAV is the standard protocol used for deploying cartridges and managing files on Salesforce B2C Commerce instances.

     -   C. `Git Push`

     -   D. `HTTPS POST`

2.   If a site's cartridge path is set to 'plugin_wishlist:app_custom:app_storefront_base', and a file named 'ProductModel.js' exists in all three, which one will the platform use?

     -   <u>**A. `plugin_wishlist`**</u>

         -> √ The platform searches the cartridge path from left to right and uses the first occurrence it finds.

     -   B. `app_storefront_base`

     -   C. The platform will throw a conflict error.

     -   D. `app_custom`

3.   Which Business Manager module is used to import initial catalog data provided in an XML format?

     -   A. Metadata Import

     -   B. Data Replication

     -   C. Site Import & Export

         -> X Site Import is for full site configurations. Catalog-specific XMLs are handled in the Catalog Import/Export module.

     -   <u>**D. Catalog Import & Export**</u>

         -> √ Right answer

4.   When creating a new site in Business Manager, which two configurations are mandatory to define during the initial site creation process?

     -   A. Cartridge Path and Payment Processor

     -   <u>**B. Default Currency and Taxation Type**</u>

         -> √ As per the exam guide, setting currency and taxation (Net vs Gross) is a primary requirement for new site setup.

     -   C. Customer Groups and Promotions

     -   D. Price Books and Inventory Lists

5.   A developer wants to ensure that a custom attribute 'isEcoFriendly' is available for all Product objects. Where should this be configured?

     -   A. In the ISML template using a script block

     -   B. Product Search Model

     -   C. <u>**System Object Types > Product > Attribute Definitions**</u>

         -> √ Extending existing platform objects is done by adding attribute definitions to the System Object Type.

     -   D. Custom Object Types > Product

6.   What is the primary difference between a Master Catalog and a Storefront Catalog?

     -   A. Only Master catalogs can have prices.

     -   <u>**B. Master catalogs hold the product definitions, while Storefront catalogs define the navigation structure.**</u>

         -> √ That's right!

     -   C. Master catalogs cannot be replicated.

     -   D. Master catalogs are for staging, Storefront catalogs are for production.

7.   A merchant wants to allow shoppers to filter search results by 'Material'. Which configuration is required in Business Manager?

     -   <u>**A. Search Refinement Definitions**</u>

         -> √ Refinement definitions allow attributes to be used as filters on the storefront PLP.

     -   B. Search Sorting Definitions

     -   C. Search Suggestions

     -   D. Category Assignments

8.   Which tool in Business Manager allows a developer to see which specific script or template is causing performance latency on a page?

     -   A. Log Center

     -   B. Pipeline Profiler

     -   <u>**C. Code Profiler**</u>

         -> √ The Code Profiler provides a breakdown of execution time for templates and scripts.

     -   D. Request Log

9.   A developer needs to create a persistent storage for 'User Favorites' that are not part of the standard Profile. When is it appropriate to use a Custom Object?

     -   A. Only for temporary session data.

     -   <u>**B. When the data model is complex and doesn't fit standard system objects.**</u>

         -> √ Custom Objects should be used when system objects (like Profile, Order) cannot accommodate the business data requirement.

     -   C. Always, to keep system objects clean.

     -   D. To replace standard Product attributes.

10.   In OCAPI Settings, which JSON key defines the specific API resources (e.g., /products, /baskets) an application can access?

      -   A. client_id

      -   B. methods

      -   <u>**C. resources**</u>

          That's right!

      -   D. permissions





# Salesforce Certified B2C Commerce Cloud Developer - Practice Exam (60 Questions)

## Section 1: B2C Commerce Setup (11%)

**Q1: A developer needs to deploy a new cartridge to a sandbox. Which protocol is primarily used by the IDE to upload files to the version directory?**

A. SFTP

B. WebDAV (Correct)

C. HTTPS POST

D. Git Push

*Rationale: WebDAV is the standard protocol for managing files and cartridges on B2C Commerce instances.*

**Q2: If a site's cartridge path is set to `plugin_wishlist:app_custom:app_storefront_base`, and a file named `ProductModel.js` exists in all three, which one will the platform use?**

A. app_storefront_base

B. app_custom

C. plugin_wishlist (Correct)

D. The platform will throw a conflict error.

*Rationale: The platform searches the cartridge path from left to right and uses the first occurrence it finds.*

**Q3: Which Business Manager module is used to import initial catalog data provided in an XML format?**

A. Site Import & Export

B. Catalog Import & Export (Correct)

C. Metadata Import

D. Data Replication

**Q4: When creating a new site in Business Manager, which two configurations are mandatory to define during the initial site creation process?**

A. Default Currency and Taxation Type (Correct)

B. Cartridge Path and Payment Processor

C. Price Books and Inventory Lists

D. Customer Groups and Promotions

**Q5: A developer wants to add the correct sequence of cartridge names to a newly created site. Where is this configured in Business Manager?**

A. Administration > Sites > Manage Sites > [Site Name] > Settings (Correct)

B. Administration > Site Development > Cartridges

C. Merchant Tools > Site Preferences

D. Administration > Global Preferences

**Q6: Given a sandbox environment, what is the best practice for deploying a new code version without affecting the currently active version?**

A. Overwrite the files in the current version directory.

B. Create a new version directory via WebDAV and upload files there. (Correct)

C. Use Data Replication.

D. Delete the old version before uploading.

------

## Section 2: Working with a B2C Site (12%)

**Q7: What is the primary difference between a Master Catalog and a Storefront Catalog?**

A. Master catalogs hold product definitions; Storefront catalogs define navigation structure. (Correct)

B. Master catalogs are for staging; Storefront catalogs are for production.

C. Only Master catalogs can have prices.

D. Master catalogs cannot be replicated.

**Q8: A merchant wants to allow shoppers to filter search results by 'Material'. Which configuration is required in Business Manager?**

A. Search Refinement Definitions (Correct)

B. Search Sorting Definitions

C. Search Suggestions

D. Category Assignments

**Q9: Which tool allows a merchant to manage the layout and content of a page without developer intervention using a drag-and-drop interface?**

A. Content Slots

B. Page Designer (Correct)

C. Business Manager Import/Export

D. ISML Templates

**Q10: A developer needs to enable "In-Store Pickup" for a site. Which Business Manager module handles the availability of products per store?**

A. Price Books

B. Inventory Lists (Correct)

C. Product Search Model

D. Shipping Methods

**Q11: To enable shoppers to complete storefront orders, which two configurations must be associated with the site?**

A. Shipping Methods and Payment Processors (Correct)

/B. Content Assets and Folders

C. Search Refinements and Sorting

D. Custom Objects and Services

**Q12: Which module is used to manage non-product content like "About Us" or "Privacy Policy" pages?**

A. Product Data Model

B. Content Assets (Correct)

C. Custom Objects

D. Page Designer Components

------

## Section 3: Data Management (24%)

**Q13: A developer wants to ensure that a custom attribute `isEcoFriendly` is available for all Product objects. Where should this be configured?**

A. System Object Types > Product > Attribute Definitions (Correct)

B. Custom Object Types > Product

C. Product Search Model

D. ISML Template script block

**Q14: Which tool in Business Manager allows a developer to see which specific script or template is causing performance latency on a page?**

A. Log Center

B. Code Profiler (Correct)

C. Request Log

D. Pipeline Profiler

**Q15: A developer needs to create persistent storage for 'User Favorites' that are not part of the standard Profile. When is it appropriate to use a Custom Object?**

A. When the data doesn't fit standard system objects and requires persistence. (Correct)

B. Always, to keep system objects clean.

C. Only for temporary session data.

D. To replace standard Product attributes.

**Q16: In OCAPI Settings, which JSON key defines the specific API resources (e.g., `/products`, `/baskets`) an application can access?**

A. client_id

B. resources (Correct)

C. methods

D. permissions

**Q17: A developer wants to modify site search preferences to enable searching for a product attribute that is currently not searchable. What must be done?**

A. Set the attribute to 'Searchable' in the Product System Object Type. (Correct)

B. Update the ISML template.

C. Create a Search Refinement.

D. Re-index the catalog.

**Q18: Given a business requirement to create a new sorting definition (e.g., "Sort by Discount Percent"), where is this managed?**

A. Merchant Tools > Search > Sorting Definitions (Correct)

B. Merchant Tools > Search > Search Refinements

C. Administration > Sites > Search

D. System Object Types > Product

**Q19: How can a developer access the specific error logs generated by a custom script?**

A. Administration > Operations > Site Development > Development Setup > Log Files (Correct)

B. Administration > Site Development > Error Logs

C. Merchant Tools > Online Marketing > Logs

D. They are only available via the IDE debugger.

**Q20: When configuring OCAPI permissions, what is the difference between 'Data' and 'Shop' APIs?**

A. Shop API is for storefront interactions; Data API is for backend/admin operations. (Correct)

B. Shop API is for read-only; Data API is for read-write.

C. There is no difference.

D. Data API is deprecated.

**Q21: A developer sees a 'Quota Violation' in the logs. Which tool should be used to investigate which specific quota was exceeded?**

A. Quota Status module in Business Manager (Correct)

B. Code Profiler

C. Pipeline Profiler

D. Log Center

**Q22: Which Service configuration setting defines the maximum time the platform waits for an external system to respond?**

A. Connection Timeout (Correct)

B. Circuit Breaker Threshold

C. Retry Interval

D. Rate Limit

**Q23: A developer needs to clear the cache for a specific set of products. Which action in Business Manager is most appropriate?**

A. Invalidate the Site Cache. (Correct)

/B. Re-index the Catalog.

C. Restart the Instance.

D. Upload a new code version.

**Q24: What is the mandatory step after modifying Search Refinements or Search Searchable Attributes?**

A. Run a Search Re-index. (Correct)

B. Clear the browser cache.

C. Replicate to Production.

D. Perform a Site Import.

------

## Section 4: Application Development (53%)

**Q25: What is the outcome of using `<isinclude url="..." />` in an ISML template?**

A. The content is included at compile time.

B. A new internal request is triggered, allowing for independent caching. (Correct)

C. It shares the pdict with the parent template.

D. It is faster than a local include.

**Q26: To protect a storefront form from CSRF attacks, which middleware should be added to the POST route in SFRA?**

A. `csrfProtection.validateRequest` (Correct)

B. `csrfProtection.generateToken`

C. `server.post`

D. `security.csrfCheck`

**Q27: A developer needs to access a localized string from a resource bundle named `myBundle.properties`. Which syntax is correct in ISML?**

A. `${Resource.msg('key', 'myBundle', null)}` (Correct)

B. `${dw.web.Resource.key}`

C. `<isprint value="myBundle.key" />`

D. `${pdict.resources.key}`

**Q28: How should non-sensitive debugging information be logged in a custom B2C script?**

A. `dw.system.Logger.debug('message')` (Correct)

B. `console.log('message')`

C. `dw.system.Logger.error('message')`

D. `response.log('message')`

**Q29: In SFRA, which file is responsible for mapping a URL like 'Product-Show' to the corresponding controller function?**

A. The controller file itself using `server.get` or `server.post` (Correct)

B. route-mapping.json

C. site-path.xml

D. The cartridge path

**Q30: A developer is extending a controller and wants to add data to the viewData object before the template renders. Which approach is correct?**

A. Use `res.getViewData()` and modify the object. (Correct)

B. Use `res.append()`.

C. Use `res.setViewData()`.

D. Modify `pdict` directly in the script.

**Q31: To implement Page Designer components, which two files must a developer create at minimum?**

A. A JSON configuration file and an ISML template. (Correct)

B. A JavaScript controller and an ISML template.

C. A custom object and a content slot.

D. A CSS file and a JSON file.

**Q32: Which method is used to manually start a database transaction when updating a Custom Object via script?**

A. `dw.system.Transaction.begin()` (Correct)

B. `dw.system.Transaction.wrap()`

C. `dw.system.Transaction.start()`

D. `dw.object.CustomObject.save()`

**Q33: Which ISML tag is used to prevent the caching of a specific part of a page?**

A. Use a remote include (`<isinclude url="..." />`) pointing to an uncached controller. (Correct)

B. `<iscache type="none" />`

C. `<isnocache />`

D. `<isprint encoding="off" />`

**Q34: A developer is writing a Job step using Chunk Processing. What is the role of the 'process' function?**

A. To transform a single item and return it for writing. (Correct)

B. To fetch data from the database.

C. To commit the transaction.

D. To initialize the file writer.

**Q35: How can a developer retrieve the current shopper's IP address in a B2C script?**

A. `request.httpRemoteAddress` (Correct)

B. `request.remoteAddress`

C. `session.userHost`

D. `dw.system.System.getIP()`

**Q36: What is the mandatory method to use in an ISML form action to ensure proper navigation in SFRA?**

A. `URLUtils.continueURL()` (Correct)

B. `URLUtils.url()`

C. `res.render()`

D. `URLUtils.https()`

**Q37: Which class is used to search for orders programmatically?**

A. `dw.order.OrderMgr` (Correct)

B. `dw.order.OrderSearchModel`

C. `dw.customer.CustomerMgr`

D. `dw.catalog.SearchModel`

**Q38: A developer wants to intercept the standard OCAPI Product retrieval to add a custom attribute. What should they use?**

A. An OCAPI Hook (Correct)

B. A JavaScript Controller

C. A Custom Object

D. ISML expressions

**Q39: Which B2C API class represents the shopper's cart during checkout?**

A. `dw.order.Basket` (Correct)

B. `dw.order.Order`

C. `dw.customer.Profile`

D. `dw.util.Collection`

**Q40: What is the purpose of the `dw.system.HookMgr` class?**

A. To trigger logic at specific extension points. (Correct)

B. To register OCAPI clients.

C. To manage WebDAV.

D. To hash passwords.

**Q41: A developer needs to render a template but only if a certain condition is met. Which ISML tag is correct?**

A. `<isif condition="${pdict.show}">` (Correct)

B. `<iswhen pdict.show>`

C. `<ischeck value="${pdict.show}">`

D. `<isinclude if="${pdict.show}">`

**Q42: Which method is used to bind a B2C Script object to an ISML form definition?**

A. `form.copyFrom()` (Correct)

B. `form.bind()`

C. `form.populate()`

D. `res.viewData.form = form`

**Q43: Which B2C API should be used to format a price in ISML using the current locale's currency symbol?**

A. `dw.util.StringUtils.formatMoney()` (Correct)

B. `dw.system.Site.format()`

C. `dw.web.Resource.msg()`

D. `pdict.Price.toString()`

**Q44: In SFRA, what is the role of `res.cacheExpiration()`?**

A. To set the time a page is cached on the web tier. (Correct)

B. To clear database cache.

C. To invalidate sessions.

D. To set cookie expiration.

**Q45: A developer wants to create a URL to a static image asset in a cartridge. Which class should be used?**

A. `URLUtils.staticURL()` (Correct)

B. `URLUtils.url()`

C. `URLUtils.imageURL()`

D. `URLUtils.httpsStatic()`

**Q46: Which ISML tag is used to loop through a collection of products?**

A. `<isloop items="${pdict.products}" var="product">` (Correct)

B. `<isforeach items="${pdict.products}">`

C. `<isrepeat collection="${pdict.products}">`

D. `<isiterate products>`

**Q47: A developer needs to return a JSON response from a controller. How is this done in SFRA?**

A. `res.json({ success: true });` (Correct)

B. `res.renderJSON({ success: true });`

C. `response.getWriter().println(JSON.stringify({ success: true }));`

D. `res.printJSON();`

**Q48: In ISML, what does `encoding="off"` in `<isprint />` do?**

A. It prints the value without HTML escaping. (Correct)

B. It encrypts the value.

C. It prevents caching.

D. It formats as currency.

**Q49: Which B2C Script object contains information about the shopper's user agent?**

A. `request.httpUserAgent` (Correct)

B. `session.device`

C. `request.deviceType`

D. `dw.system.System.getIP()`

**Q50: What happens if a developer exceeds the `api.MaxObjectCount` quota?**

A. The request is terminated immediately with an error. (Correct)

B. The request is delayed.

C. A warning is logged.

D. Support is notified to increase the limit.

**Q51: When using the Service Framework, what does the 'Circuit Breaker' do?**

A. Stops requests to a failing external system to prevent bottlenecks. (Correct)

B. Encrypts data.

C. Load balances sandboxes.

D. Bypasses auth.

**Q52: What is the correct way to handle a transaction rollback?**

A. `dw.system.Transaction.rollback()` (Correct)

B. `Transaction.undo()`

C. The platform rolls back automatically on any error.

D. `dw.system.Transaction.cancel()`

**Q53: How does a developer provide localized values for a custom product attribute in Business Manager?**

A. By selecting 'Localized' in the attribute definition and entering values per locale. (Correct)

B. By creating multiple attributes (e.g., name_en, name_fr).

C. By using properties files only.

D. This is not supported.

**Q54: Which tool is used to troubleshoot server-side JavaScript issues by pausing execution?**

A. Script Debugger (Correct)

B. Code Profiler

C. Log Center

D. Request Log

**Q55: What is the recommended way to perform a heavy batch process (e.g., updating 1 million products)?**

A. Use a Job with a Script Step. (Correct)

B. Use a Controller with a long timeout.

C. Use an OCAPI Data API call.

D. Use a local ISML script block.

**Q56: In SFRA, what is the primary benefit of 'Models'?**

A. They encapsulate business logic and data transformation for the view. (Correct)

/B. They replace the database.

C. They are used for styling.

D. They manage cartridge paths.

**Q57: A developer needs to add a new step to an existing job. Where is this done?**

A. Administration > Operations > Jobs (Correct)

B. Administration > Site Development > Jobs

C. Merchant Tools > Jobs

D. Administration > Operations > Services

**Q58: Which file defines the parameters for a custom job step?**

A. steptypes.json (Correct)

B. jobs.xml

C. package.json

D. config.json

**Q59: Which B2C API retrieves a specific Content Asset by its ID?**

A. `dw.content.ContentMgr.getContent('id')` (Correct)

B. `dw.content.ContentMgr.getAsset('id')`

C. `dw.catalog.CatalogMgr.getContent('id')`

D. `pdict.content.id`

**Q60: What is the result of `URLUtils.https('Home-Show')`?**

A. A fully qualified HTTPS URL for the Home-Show route. (Correct)

B. A relative URL.

C. An error if the site is not in HTTPS mode.

D. A redirect to the home page.

Tôi đã cập nhật lại định dạng cho toàn bộ 60 câu hỏi. Các syntax như `${}` đã được đặt trong định dạng văn bản thô để tránh bị lỗi hiển thị.

**Tóm tắt các điểm quan trọng trong bộ câu hỏi:**

1.  **Cấu trúc (Setup):** Tập trung vào WebDAV, Cartridge Path và Site Import.
2.  **Quản lý dữ liệu:** Nhấn mạnh vào System Objects, Search Refinements và OCAPI permissions.
3.  **Phát triển ứng dụng (Trọng tâm 53%):** Bao gồm SFRA Controllers, ISML tags, Middleware (CSRF), Transaction handling, và Job steps (Chunk processing).

Bạn có thể sử dụng bộ câu hỏi này để kiểm tra kiến thức trước khi đi thi. Chúc bạn ôn tập tốt!

