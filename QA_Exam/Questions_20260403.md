## Questions

1. How do you extend a Controller without modifying the base cartridge in SFRA?
    A. Copy the base controller into your cartridge and modify it.
    B. Create a controller with the same name and use server.extend(module.superModule).
    C. Use the `server.replace()` method to overwrite the base route.
    D. Use `require('app_storefront_base/cartridge/controllers/...')` directly.

2. In a middleware chain, what happens if you call res.render() and then next()?
    A. The template renders twice.
    B. An error occurs, and the request fails.
    C. The template renders, and the next middleware executes normally.
    D. The `next()` call is silently ignored.

3. Which middleware functions are required to enable CSRF protection on a specific route pair in SFRA?
    A. `csrfProtection.validateAjaxRequest` on all routes.
    B. `csrfProtection.generateToken` for GET and `csrfProtection.validateRequest` for POST.
    C. `server.middleware.csrf` on both GET and POST routes.
    D. `security.enableCSRF()` on the POST route.


4. How do you prevent a specific Controller route from being cached at the web-tier?
    A. Use `cache.applyDefaultCache`.
    B. Return false from the middleware.
    C. Use `iscacheable` in the controller.
    D. Use `res.cacheExpiration(0)`.

5. If a site's cartridge path is 'plugin_wishlist:app_custom:app_storefront_base', which 'ProductModel.js' is used if it exists in all three?
    A. All three are merged automatically.
    B. The one in app_storefront_base.
    C. The one in plugin_wishlist.
    D. The one in app_custom.

6. How can you pass data from a Controller to an ISML template in SFRA?
    A. Pass a JSON object as the second argument to res.render('templateName', { data: value }).
    B. Return the data from the controller module.
    C. Use the `pdict.set()` method in the controller.
    D. Assign the data to session.custom.

7. What is the primary difference between `server.get()` and `server.append()` in SFRA?
    A. `server.get` defines a new route; `server.append` adds middleware to the end of an existing route.
    B. `server.get` handles data retrieval; `server.append` handles database writes.
    C. `server.get` is for AJAX; `server.append` is for page loads.
    D. `server.append` replaces the original route completely.

8. How do you securely access HTTP Cookies in a B2C Script?
    A. Via `response.cookies`.
    B. Via `session.getCookies()`.
    C. Via `request.httpCookies`.
    D. Using `document.cookie`.

9. Why is it dangerous to store large objects in session.custom?
    A. It exposes the data to cross-site scripting (XSS) attacks.
    B. It automatically disables the page cache.
    C. It increases the session size, degrading performance due to serialization overhead.
    D. It violates the Object.MaxCustomAttributes quota.

10. How do you trigger a 410 (Gone) status code for a discontinued product?
    A. Use  in the ISML.
    B. Throw a new Error(410).
    C. res.setStatusCode(410).
    D. res.redirect('410').

11. What is the primary constraint regarding res.viewData in SFRA?
    A. It is a standard JS object, but it must be kept lean to avoid memory overhead during template rendering.
    B. It is read-only and cannot be modified by middleware.
    C. It can only hold strings and numbers, not objects.
    D. It automatically persists data to the database.

12. How do you handle multi-language support for error messages generated in a Controller?
    A. Use `dw.web.Resource.msg('error.key', 'bundle', null)`.
    B. Create separate controller files for each language.
    C. Use `session.getLocale().translate('error.key')`.
    D. Hardcode the translations in a JSON object in the script.

13. Which SFRA object is typically responsible for generating the 'Breadcrumbs' logic?
    A. The Site Preferences.
    B. The Product or Search model/decorator.
    C. The URLUtils class.
    D. The session.custom object.


14. How can a developer detect if the current request is coming from a 'Search Engine Bot'?
    A. Check `session.isBot`.
    B. Check `request.httpUserAgent`.
    C. Check `request.httpMethod === 'BOT'`.
    D. Use `dw.system.Site.isCrawler()`.

15. How do you execute a redirect to the Home Page from within an SFRA Controller?
    A. `server.route('Home-Show')`.
    B. `res.redirect(URLUtils.url('Home-Show'))`.
    C. `res.render('Home-Show')`.
    D. `window.location.href = '/'`.

16. What is the strict platform limit for Script.MaxCallStackDepth?
    A. 500
    B. 50
    C. 100
    D. Unlimited

17. How should a developer query for Custom Objects to avoid hitting performance bottlenecks?
    A. Use `CustomObjectMgr.queryCustomObjects` with a specific indexed attribute in the query string.
    B. Use `CustomObjectMgr.getAllCustomObjects()` and filter via a JavaScript loop.
    C. Export all Custom Objects to XML and parse them.
    D. Use direct SQL queries.

18. What happens if a developer exceeds the Object.MaxCustomAttributes quota?
    A. The cartridge will fail to upload.
    B. Old attributes are automatically deleted to make room.
    C. The storefront will throw a 500 Error for all users.
    D. They cannot create new attribute definitions in Business Manager for that object type.

19. If a custom requirement dictates storing an Array of complex objects on a Customer Profile, what is the best practice?
    A. Create a 'Set of Objects' custom attribute.
    B. Stringify the array to JSON and store it in a 'Text' or 'Long String' attribute.
    C. Store the data in the `session.custom` object permanently.
    D. Create hundreds of individual custom attributes (e.g., item1, item2).

20. What is the purpose of `dw.system.Transaction.begin()`?
    A. To begin rendering the ISML template.
    B. To start a new HTTP request.
    C. To manually start a database transaction when explicit control is needed.
    D. To initialize a Service Framework call.

21. How many price books can be active for a single site at once?
    A. A maximum of two: one regular and one sale.
    B. Only one active price book is allowed globally.
    C. Multiple, and they are evaluated based on the assigned priority in Business Manager.
    D. Only one per currency.

22. What is the technical difference between a 'System Quota' and a 'Service Limit'?
    A. They are identical terms for the same concept.
    B. Quotas restrict database size; Limits restrict code length.
    C. Quotas apply to Sandbox; Limits apply to Production.
    D. Quotas are hard platform-enforced limits; Service Limits (like API timeouts) can sometimes be configured.

23. How do you retrieve a site preference named 'myConfig' via script?
    A. `session.custom.myConfig`
    B. `request.getPreference('myConfig')`
    C. `Site.preferences.myConfig`
    D. `dw.system.Site.current.getCustomPreferenceValue('myConfig')`

24. What is the maximum length of a standard 'String' attribute in B2C Commerce?
    A. 255 characters.
    B. 100,000 characters.
    C. 4,000 characters.
    D. Unlimited.

25. How do you programmatically delete a persistent cookie from the user's browser?
    A. Use `dw.system.Session.clearCookies()`.
    B. Set the cookie value to null.
    C. Call `request.removeCookie('name')`.
    D. Set its max age to 0 and add it to the response object.

26. Why is it highly recommended to use LocalServiceRegistry over `dw.net.HTTPClient`?
    A. `HTTPClient` is blocked on Production environments.
    B. LocalServiceRegistry provides integrated logging, rate monitoring, and circuit breakers.
    C. `HTTPClient` cannot make HTTPS requests.
    D. `LocalServiceRegistry` executes significantly faster.

27. What behavior does the api.MaxObjectCount quota restrict?
    A. It limits the total number of items a customer can have in their cart.
    B. It limits the number of persistent objects (like products or orders) instantiated in a single request.
    C. It limits the number of products returned in a search result.
    D. It limits how many Custom Object definitions you can create in Business Manager.

28. How can a developer best avoid database 'Deadlocks' in high-volume custom scripts?
    A. Disable the database locking mechanism in Site Preferences.
    B. Wrap the entire Job in a single massive Transaction.
    C. Ensure all scripts access and lock objects in the same order and keep transactions as short as possible.
        -> √ Consistent sorting (e.g., always locking Order A before Order B) prevents circular wait conditions.
    D. Use the transaction.rollback() method after every query.

29. Are native JavaScript 'Map' and 'Set' objects supported in B2C Commerce Script?
    A. Yes, they are fully ES2022 compliant.
        -> The backend engine does not support full modern ES2022 specifications.
    B. Yes, but they are the versions provided by the Rhino engine, which may lack some modern ES6 methods.
        -> √ B2C runs on a customized Rhino JVM engine, meaning some newer native JS features behave differently or are incomplete.
    C. No, Maps and Sets cause memory leaks in the JVM.
    D. No, developers must exclusively use dw.util.Map and dw.util.Set.

30. How do you programmatically trigger a refresh of the Product Search Index from a Controller?
    A. Set the search index status to 'Stale' in `session.custom`.
    B. Use `dw.catalog.SearchIndexMgr.rebuildAll()`.
    C. Call the OCAPI Search API with a POST command.
    D. You cannot trigger a full rebuild directly from a Script; you must use a Job with the Search-Index step.
        -> √ Index rebuilding is extremely resource-intensive and is strictly isolated to the background Job Framework.

31. In the Service Framework registry, what is the exact purpose of the 'createRequest' callback?
    A. It is where you define the URL path, headers, and request body for the outgoing call.
        -> √ This callback formats the data from the B2C application into the strict HTTP request expected by the external API.
    B. It bypasses the Circuit Breaker for testing.
        -> Bypassing is done via Mock Mode, not the request creation logic.
    C. It handles the retry logic if the API returns a 500 error.
    D. It maps the raw JSON response back into a script object.

32. How do you enable 'Mock Mode' for a specific Service to bypass external calls?
    A. Delete the Service Credentials.
    B. Add a mock:true property to the `package.json`.
    C. Use `service.setMock(true)` in the createRequest method.
        -> Service initialization configurations cannot be overridden dynamically at runtime in the request callback.
    D. Administration > Operations > Services > Select Service > Check the 'Mocked' box.
        -> √ Mocking is a configuration toggle in Business Manager, allowing quick testing without code changes.

33. When designing an OCAPI integration, what dictates the use of POST over GET?
    A. POST is faster than GET for large product catalogs.
    B. GET is strictly for retrieving data safely; POST creates resources or performs complex actions like authentication.
        -> √ OCAPI follows RESTful principles, where GET is idempotent and POST causes state changes on the server.
    C. POST allows bypassing the allowed_origins CORS settings.
    D. GET cannot handle JSON responses.

34. How do you securely authorize an OCAPI call coming from a custom Mobile App?
    A. Use a hidden input field on the mobile screen.
    B. Pass the Business Manager admin password in the request header.
    C. Disable the `client_id` requirement in OCAPI settings.
    D. Use a JWT (JSON Web Token) via the Auth API and verify the Client ID.
        -> √ Mobile apps must authenticate users securely using tokens rather than passing raw passwords on every request.

35. What is the technical definition of a 'Hook' in the context of OCAPI?
    A. A mechanism to intercept and steal user passwords.
    B. A custom script execution point that fires before or after a standard OCAPI resource call.
        -> √ Hooks allow developers to inject custom logic (like validation or custom calculations) into the out-of-the-box API flow.
    C. A tool to convert XML to JSON.
    D. A way to connect two different Business Manager instances.

36. What is the most secure way to pass an API Key to an external Service?
    A. Hardcode it as a constant at the top of the Service script.
    B. Save it in a Custom Object named 'Secrets'.
    C. Store it in the 'Service Credentials' password field in Business Manager.
        -> √ This abstracts the key from the code, encrypts it in the database, and prevents it from appearing in source control.
    D. Pass it as a URL parameter generated by ISML.

37. If a storefront Service is timing out and blocking checkout, what is the best immediate architectural fix?
    A. Change the service from POST to GET.
    B. Wrap the service call in a Job.
        -> X Checkout requires real-time synchronous responses (e.g., for payment processing), so background jobs won't work.
    C. Increase the timeout to 60 seconds to guarantee it finishes.
    D. Ensure the Service timeout is configured lower (e.g., 2 seconds) to fail fast.
        -> √ Long timeouts (like the default 10s) tie up application threads. Failing fast allows the circuit breaker to trip and the site to recover.

38. How should a Service Framework script handle a '429 Too Many Requests' response?
    A. Implement a retry logic with an exponential backoff strategy.
        -> √ 429 indicates rate limiting; waiting a few seconds and trying again safely is the standard recovery pattern.
    B. Trip the circuit breaker permanently.
        -> X Rate limits are temporary; permanent trips require manual intervention.
    C. Ignore the error and return an empty object.
    D. Send an email to the customer.

39. Can OCAPI be used to read or modify Site Preferences?
    A. No, OCAPI only handles catalog and order data.
    B. Yes, they are available in the Shop API under /site.
        -> X Exposing site preferences to the public Shop API poses a security risk.
    C. No, preferences can only be changed via WebDAV.
    D. Yes, but strictly through the Data API, as preferences are administrative configurations.
        -> √ The Shop API is for storefront shoppers; the Data API is for system management and configuration.

40. In the Service Framework, what is the critical role of the 'parseResponse' callback?
    A. To write the response to the service log file.
    B. To determine if the Circuit Breaker should trip.
    C. To convert the raw HTTP string or JSON payload into a clean Data Transfer Object (DTO) for the script.
        -> √ It abstracts the parsing logic away from the controller, ensuring the application receives a formatted object regardless of the raw API structure.
    D. To serialize the outgoing request payload.

41. If a custom Service is failing on Staging, where is the best place to find the raw request/response payload for debugging?
    A. Check the WebDAV IMPEX folder.
    B. Check the service-*.log files in the Log Center, assuming 'Communication Log' is enabled.
        -> √ Service logs are specifically designed to capture the exact headers and bodies of framework calls.
    C. Use the Code Profiler.
        -> X The profiler shows execution time, not raw data payloads.
    D. Look in the custom-error.log file.

42. What is the operational implication of using a 'Local Include' () in ISML?
    A. It executes asynchronously after the page loads.
    B. It bypasses the controller and accesses the database directly.
    C. It requires a separate HTTP request to the application server.
    D. It executes in the same thread and shares the cache policy of the parent template.
        -> √ Local includes are compiled together with the parent, meaning they cannot be cached dynamically or independently.

43. What is the primary benefit of using a 'Remote Include' ()?
    A. It allows ISML to call third-party APIs directly.
        -> X The 'url' attribute points to an internal Controller route, not an external API.
    B. It initiates a new internal request, allowing the specific component to have an independent cache policy.
        -> √ This allows a highly cached page (like a PDP) to securely include dynamic, non-cached data (like a user's mini-cart).
    C. It prevents XSS attacks.
    D. It reduces the load on the application server.

44. How do you implement a Webhook listener in B2C Commerce to receive updates from an external ERP?
    A. Register a new Hook in hooks.json pointing to an external URL.
    B. Create a public Controller route that parses the incoming JSON payload and trigger logic based on the data.
        -> √ A Webhook is just an HTTP endpoint. A standard Controller handles the POST request and processes the incoming payload.
    C. Configure a Webhook URL in Site Preferences.
    D. Use the dw.net.Webhook class.

45. When debugging performance, what is the primary benefit of 'Service Profiling' in Business Manager?
    A. It helps identify which external API integrations are introducing latency and slowing down the site flow.
        -> √ Service Profiling measures the specific duration of external network calls, pinpointing slow third-party providers.
    B. It tracks how fast the ISML templates compile.
    C. It prevents the MaxCallStackDepth error.
    D. It analyzes the memory usage of Custom Objects.
        -> X Service profiling focuses on network services, not database object sizes.

46. How do you properly configure a Job Step to execute a custom JavaScript function?
    A. Use the 'EvaluateString' step and type the code in the UI.
    B. Select the 'ExecuteScriptModule' step type and provide the module path and exported function name.
        -> √ This is the modern framework standard for executing reusable script logic in background tasks.
    C. Select the 'LegacyPipelet' step.
    D. Select the 'RunController' step and point to a route.

47. In the Job ChunkProcessing model, what is the purpose of the 'beforeStep' or 'onOpen' callback?
    A. It clears the database cache.
    B. It is called exactly once before any chunks are processed to initialize resources like file streams or iterators.
        -> √ Setting up the heavy data streams before iteration ensures memory is managed correctly and not duplicated per chunk.
    C. It is called before every single item is processed.
        -> X The 'process' callback handles individual items; 'onOpen' is a one-time setup.
    D. It forces the job to wait for another job to finish.

48. How do you define custom parameters (like a file path) that can be passed from the Business Manager UI into a Job Script?
    A. Define them in the package.json file.
    B. Define the parameters in the steptypes.json file of the cartridge.
        -> √ The steptypes.json file instructs Business Manager to render input fields in the Job configuration UI and maps them to script arguments.
    C. Hardcode them as constants in the script.
    D. Pass them via the query string in the job execution URL.

49. Why must a developer use dw.io.XMLStreamWriter instead of building a massive XML string for large catalog exports?
    A. Because standard strings cannot contain XML tags.
    B. To ensure the XML is minified.
    C. To automatically encrypt the data.
    D. To stream the data directly to the file system, avoiding memory quotas that string concatenation would trigger.
        -> √ Holding massive strings in RAM will crash the JVM; streaming writes tiny chunks directly to the disk.

50. What is the most common cause of a 'Catalog Replication' task failing between Staging and Production?
    A. A developer forgot to clear the cache.
    B. The Production instance ran out of disk space.
    C. Locked objects or invalid category assignments disrupting the data integrity constraints.
    √ If an object is currently locked by a job, or if a product references a missing category, the database transaction will abort to prevent corruption.
    D. The OCAPI client ID was incorrect.

51. What is the functional purpose of 'A/B Testing' natively built into B2C Commerce?
    A. To test API endpoint performance.
    B. To automatically fix JavaScript bugs on the frontend.
    C. To test different content, layouts, or promotions simultaneously on segmented traffic to measure conversion rates.
        -> √ A/B testing allows merchants to scientifically determine which configuration drives the most revenue.
    D. To compare Sandbox code with Production code.

52. How can a developer programmatically determine which specific promotion triggered a discount on a product?
    A. Query the `PromotionMgr` for the lowest price.
    B. Use `product.getPromotions()`.
    C. Check the session.custom.promo object.
    D. Iterate through lineItem.priceAdjustments and inspect the applied promotion ID.
        -> √ Price Adjustments represent the actual monetary change applied by the promotion engine to a specific line item.

53. How is an XML 'Sitemap' generated for search engines in B2C Commerce?
    A. A developer must write a custom script using XMLStreamWriter.
    B. It is generated automatically on a schedule via the Sitemap Job configuration in Merchant Tools.
        -> √ The platform provides a native, highly optimized job to build sitemaps based on catalog and content visibility.
    C. It is uploaded manually by the merchant via WebDAV.
    D. It is generated dynamically via a Controller every time a bot requests it.

54. What is the standard architectural pattern for implementing 'Infinite Scroll' on a Product Listing Page (PLP)?
    A. Fetch all products on the first load and hide them using CSS.
    B. Redirect the user to page 2, page 3, etc., automatically via JavaScript.
    C. Use an OCAPI call to fetch JSON and render the tiles using React.
    D. Use an AJAX call to a Controller that renders only the HTML for the new product tiles and appends them to the DOM.
        -> √ Returning pre-rendered HTML snippets (instead of JSON) keeps the display logic isolated in the ISML template and is highly cacheable.

55. What is the purpose of the 'Profile Wrapper' often seen in SFRA Unit Tests?
    A. It encrypts the customer's password before saving.
    B. It connects to the Staging instance to download test data.
    C. It acts as a mock object to simulate a user profile without hitting the database.
        -> √ Unit tests must execute without relying on live database connections or actual user data to remain fast and isolated.
    D. It generates a temporary session for testing.

56. How do you ensure 'Thread Safety' when writing a complex background Job?
    A. Wrap all code in a single transaction.
    B. Avoid using globally scoped variables that might be read or modified unpredictably by parallel executing threads.
        -> √ In parallel chunk processing, shared global state leads to race conditions and corrupted data logic.
    C. Use the session object to store variables instead.
    D. Always use single-thread execution in Job Framework 2.0.

57. Which B2C Script API class is the primary engine for executing queries and facet filtering on the storefront?
    A. `dw.system.IndexMgr`
    B. `dw.catalog.ProductMgr`
    C. `dw.util.SearchCriteria`
        -> X This is not a primary class used for storefront product searches.
    D. `dw.catalog.ProductSearchModel`
        -> √ This class provides the interface to the underlying SOLR index, handling search terms, refinements, and sorting.

58. How do you reliably retrieve the URL of a product image formatted for a 'large' view using the B2C API?
    A. `product.getImage('large', 0).getURL()`
        -> √ This uses the Image API to fetch the first image assigned to the 'large' view type defined in Business Manager.
    B. `URLUtils.staticURL('/images/large/' + product.ID + '.jpg')`
    C. `product.custom.largeImageURL`
    D. `product.getLargeImage()`

59. What is the function of a 'Custom Cache Key' when dealing with Remote Includes?
    A. It forces the browser to ignore the local cache.
    B. It encrypts the cache file on the server.
    C. It is a URL parameter added to ensure different contextual versions of a component are cached separately (e.g., ?currency=EUR).
        -> √ Cache keys force the server to generate and store a unique HTML fragment for specific user contexts.
    D. It links the remote include to a specific Custom Object.

60. How should a developer handle 'Global Errors' (e.g., unhandled 500 exceptions) in an SFRA project?
    A. Redirect all errors to the Homepage via Business Manager.
    B. Wrap every single line of code in try/catch blocks.
    C. Customize the `Error.js` controller to catch exceptions and safely render a friendly maintenance or 'Oops' template.
        -> √ SFRA centralizes fatal error handling in the Error controller to prevent raw stack traces from exposing system architecture.
    D. Disable error logging to prevent the server from crashing.

61. A developer needs to implement a custom 'Inventory Reservation' system using Custom Objects. To prevent race conditions where two customers claim the last item simultaneously, which approach is mandatory?
    A. Wrap the update in a Transaction and use the 'locking' parameter in the query.
        -> √ Explicitly locking the record during the transaction ensures that other threads cannot modify it until the current process completes.
    B. Perform the update within a Job instead of a Storefront Controller.
        -> X Jobs offer background processing but do not inherently solve real-time concurrency issues on the storefront.
    C. Use session.custom to track the reservation temporarily.
    D. Use a try-catch block to handle the 'OptimisticLockingException'.

62. In a Job using the 'Chunk' processing model, the 'process' function returns 'null' for a specific item. What is the impact on the 'write' function?
    A. The entire Job fails with a 'NullPointerException'.
    B. The Job stops immediately and moves to the 'afterStep' phase.
    C. The item is passed to 'write' as an empty object.
    D. The item is filtered out and will not be passed to the 'write' function.
        -> √ The process step acts as a filter; returning null signals the framework to skip this item for the current chunk.

63. When configuring an OCAPI 'before' hook for a 'POST' request, how can the developer modify the incoming request body before it reaches the standard resource logic?
    A. Use a 'Remote Include' to transform the data.
    B. It is impossible to modify the body; you can only validate it and return an error.
    C. Use request.setHttpBody() within the hook script.
    D. Modify the script argument object passed to the hook function.
        -> √ OCAPI hooks receive a mutable argument object that allows developers to intercept and alter data before processing.

64. An enterprise site has 500,000 active Products. A developer uses 'ProductMgr.queryAllSiteProducts()' and converts it to a List. Why will this fail on a Production instance?
    A. It violates the 'Script.MaxMemory' quota by loading all objects into the JVM heap.
        -> √ Loading half a million complex objects into an array consumes massive RAM, triggering an immediate quota violation.
    B. It violates the 'api.MaxObjectCount' quota for persistent objects.
        -> X While related, the immediate failure is usually memory exhaustion when attempting the conversion to a List.
    C. The 'queryAllSiteProducts' method is deprecated and returns an empty list.
    D. Product queries are restricted to 10,000 results by the database layer.

65. To implement a complex SEO requirement where the URL must include the parent category name for products, which SFRA file should be primarily extended?
    A. The 'Search.js' controller.
    B. The 'Product.isml' template.
        -> X ISML templates display content but do not define the routing logic of the URL itself.
    C. The 'UrlUtils.js' or the URL request mapping configuration in Business Manager.
        -> √ URL construction logic is governed by system mappings and utility classes that generate SEO-friendly paths.
    D. The 'sitemap.xml' generator.


66. What is the specific risk of using 'Transaction.wrap()' inside a loop that iterates over thousands of items?
    A. It automatically triggers a Site Maintenance mode.
    B. It results in an 'IllegalStateException' because nested transactions are required.
    C. It causes a 'Script.MaxCallStackDepth' violation.
        -> X Transaction wrapping is not a recursive operation and does not affect the call stack depth.
    D. It creates significant overhead due to constant database 'commit' and 'begin' operations.
        -> √ Frequent small transactions slow down processing; it is more efficient to wrap the entire loop or chunks of it.

67. A developer needs to share a 'Wishlist' across two different sites (SiteA and SiteB) within the same Realm. What is the most efficient architectural approach?
    A. It is impossible as sites have strictly isolated databases.
    -> X Sites within a Realm share a database; isolation is logical, not physical, and can be bypassed for certain objects.
    B. Use a Custom Object with the 'site-wide' scope instead of the 'site' scope.
        -> √ While Wishlists are usually site-specific, Custom Objects can be defined as 'organization' or 'realm' level to be visible across sites.
    C. Store the Wishlist in the Customer Profile custom attributes.
    D. Copy the data via a Job that runs every 5 minutes.

68. In the Service Framework, if 'mockMode' is enabled, which function is executed instead of 'createRequest' and 'parseResponse'?
    A. `mockFull`
        -> √ The mockFull callback is specifically designed to return a simulated response object when the service is in mocked status.
    B. `bypassCall`
    C. `getMockData`
    D. `createMockRequest`
        -> X The framework uses a single 'mockFull' callback to represent the entire mock lifecycle.

69. Why would a developer use 'dw.system.Logger.getRootLogger()' instead of 'dw.system.Logger.getLogger('name')'?
    A. To ensure logs are sent to an external syslog server automatically.
    B. To capture all log statements across the entire system regardless of the category.
        -> √ The root logger intercepts all messages, which is useful for global debugging but can lead to very noisy log files.
    C. To bypass the log file size limits.
    D. Because categorized loggers are deprecated.

70. What is the impact of setting 'pdict.cacheTag = true' in an SFRA controller?
    A. It invalidates the cache for all users globally.
    B. It automatically adds the product ID to the cache key.
    C. It is not a standard SFRA feature; caching is controlled via the 'res' object.
        -> √ SFRA moved away from pdict-based cache control to a more structured middleware-based response object approach.
    D. It enables page-level caching for the next 24 hours.

71. When developing a 'Scripted' Job Step, what is the purpose of the 'steptypes.json' file?
    A. To compile the JavaScript code into optimized machine code.
    B. To define the sequence in which different jobs are executed.
    C. To register the custom step and define its input/output parameters for Business Manager.
    -> √ The steptypes.json file acts as the manifest that tells the platform how to display and configure the step in the Job UI.
    D. To store the database credentials for the job's external integrations.

72. If a developer uses 'URLUtils.staticURL()' to link to an image, when will that link be updated in the user's browser?
    A. Every time the user clears their browser cookies.
    B. When the Search Index is rebuilt.
    C. Only when the cartridge containing the asset is uploaded with a new version string.
        -> √ Static URLs are versioned based on the cartridge upload; this ensures aggressive browser caching while still allowing for updates.
    D. Automatically every 60 minutes.

73.   A developer needs to implement a custom 'Sort Order' for a Search Results page. Which object should they modify?

-   A. PagingModel

-   B. SearchSuggestModel

-   C. CategoryModel

-   D. ProductSearchModel

    -> √ The ProductSearchModel provides the 'setSortingCondition' method to control how results are ordered before display.

74.   What is the outcome of attempting to call 'dw.system.Transaction.commit()' when no transaction was actually started?

-   A. A new transaction is started and immediately closed.

-   B. The script execution is paused for 30 seconds.

-   C. An 'IllegalStateException' is thrown.

    -> √ The platform requires a balanced 'begin' and 'commit'; attempting to commit without an active transaction is a lifecycle error.

-   D. The call is silently ignored.

75.   In OCAPI, what is the purpose of the 'x-dw-client-id' header?

-   A. To identify which application is making the request for permission and quota tracking.

    -> √ Every OCAPI request must be associated with a Client ID defined in Account Manager to enforce security policies.

-   B. To specify which cartridge path to use for the request.

-   C. To store the encrypted password of the customer.

-   D. To bypass the Web Tier cache.

    -> X Bypassing cache is usually handled via specific headers like 'Cache-Control' or OCAPI settings, not the Client ID.

76.   Which method should be used to securely compare a user-provided password against the 'Password' attribute of a Custom Object (assuming it was hashed)?

-   A. `customObject.password.equals(userInput)`

-   B. There is no way to secure Custom Object attributes.

-   C. Standard string comparison is unsafe; you should use a hashing utility to compare hashes.

    -> √ Security best practices dictate comparing cryptographic hashes rather than raw text to prevent exposure.

-   D. `dw.crypto.WeakHash.compare(userInput, storedHash)`

    -> X The 'WeakHash' class does not exist in the API; you should use MessageDigest or modern utilities.

77.   In SFRA, how can a developer ensure that a specific variable in 'res.viewData' is available to all templates rendered in a single request, including nested ones?

-   A. Declare a global variable in the controller file.

-   B. Use the  tag in every template.

-   C. Use the 'session.custom' object.

-   D. Add the variable to 'res.viewData' in a 'base' middleware that runs at the start of the chain.

    -> √ The viewData object is passed through the entire chain; adding it early makes it available to all subsequent logic and templates.

78.   What is the primary technical limitation of 'dw.util.SortedMap' when compared to a standard JavaScript 'Object'?

-   A. It automatically deletes its contents every 5 minutes.

-   B. It is a Java-backed collection that requires specific API methods (.put, .get) and cannot use dot notation.

    -> √ SortedMap is a native B2C API class (based on Java); it doesn't behave like a standard JS object literal.

-   C. It cannot store more than 10 items.

-   D. It is significantly slower than an Array.



79.   A developer wants to use 'ISML expressions' inside a JavaScript file. Why is this not possible?

-   A. It is possible if you change the file extension to .js.isml.

-   B. JavaScript already has its own ${} syntax which conflicts.

-   C. ISML is a server-side templating language that is compiled before JavaScript is executed.

    -> √ ISML and JS are separate layers; the ISML engine doesn't parse .js files in the cartridge.

-   D. It was deprecated in SFRA 6.0.

80.   When using 'dw.svc.LocalServiceRegistry', which status code indicates that the 'Circuit Breaker' has tripped and blocked the request?

-   A. INTERNAL_SERVER_ERROR

-   B. SERVICE_UNAVAILABLE

    -> √ The framework returns this specific status when it prevents a call to a service that has exceeded its failure threshold.

-   C. GATEWAY_TIMEOUT

-   D. UNAUTHORIZED

81.   An SFRA controller needs to render a different template based on the user's 'Device Type' (Mobile vs Desktop). What is the best practice?

-   A. The platform automatically handles this if you use the 'mobile' folder.

-   B. Create two separate controllers: Product-ShowMobile and Product-ShowDesktop.

-   C. Use CSS Media Queries to hide half of the page.

-   D. Check 'request.httpUserAgent' or use the 'session.custom.device' detection logic in a middleware.

    -> √ Detecting the device early in the middleware allows you to set a flag in viewData to choose the correct template.

82.   What is the purpose of 'dw.system.System.getPreferences()'?

-   A. To see the Business Manager password policies.

-   B. To check the current cartridge path.

-   C. It is not a valid API call; site preferences are accessed via dw.system.Site.current.

    -> √ System preferences do not exist in the way Site Preferences do; administrative settings are not exposed this way.

-   D. To retrieve the current server's time zone settings.

    -> X Time zone and locale info are found in the 'System' and 'Site' classes but not through a 'getPreferences' method.

83.   How can a developer effectively debug a Job that only fails on the 'Production' instance due to data-specific issues?

-   A. Production doesn't have logs for security reasons.

-   B. Add 'alert()' statements to the code.

-   C. Connect the UX Studio debugger to the Production instance.

-   D. Download the Job logs from the Log Center and check for the specific 'Error' entries and stack traces.

    That's right!

    -> √ Log files are the primary diagnostic tool for production, as interactive debugging is not allowed on live instances.

84.   When defining a Custom Object, what does the 'Key Attribute' represent?

-   A. The name of the cartridge where the object is defined.

-   B. A list of keywords used for storefront search indexing.

-   C. The unique identifier used to retrieve a specific instance of that object.

    -> √ Just like a Primary Key in SQL, the Key Attribute is what you pass to 'getCustomObject' to find the record.

-   D. The attribute that is automatically encrypted.

85.   Which B2C Commerce tool allows a developer to see a 'live' breakdown of which pipeline steps or scripts are consuming the most execution time?

-   A. Code Profiler

    -> √ The Code Profiler provides a detailed, real-time look at script performance and execution hot-spots.

-   B. Request Log Analyzer

-   C. Pipeline Profiler

-   D. UX Studio Resource Watcher

    -> X This tool monitors file changes in your workspace, not server execution performance.

86.   What is the maximum number of 'Price Books' that can be assigned to a single Site?

-   A. 1,000.

-   B. Exactly 10.

-   C. There is no hard limit, but performance degrades as more are evaluated per request.

    -> √ While you can assign many, the system must evaluate them in order of priority, adding latency to every price lookup.

-   D. 2 (One for List, one for Sale).

87.   If an ISML template uses , why might it fail to render correctly if 'myValue' contains HTML tags?

-   A. The pdict object is read-only for templates.

-   B. The  tag encodes HTML by default to prevent XSS attacks.

    -> √ To render raw HTML, you must explicitly set 'encoding="off"' in the  tag.

-   C. HTML tags must be passed in an Array.

-   D. ISML cannot render HTML tags at all.

88.   When implementing 'Apple Pay' for a B2C storefront, where is the 'Merchant ID' primarily configured?

-   A. Hardcoded in the 'checkout.js' file.

-   B. In the Site Preferences within Business Manager under the Apple Pay settings.

    -> √ Apple Pay integration requires specific merchant identifiers to be registered and assigned at the site level.

-   C. In the Customer Profile custom attribute.

-   D. In the Account Manager under 'Organization Settings'.

89.   Why would a developer use 'dw.util.UUIDUtils.createUUID()' instead of a standard counter for a unique transaction ID?

-   A. Because integers are not supported in B2C Commerce.

-   B. To prevent predictable IDs and ensure uniqueness across multiple parallel threads and application servers.

    -> √ UUIDs are universally unique and don't require a central database counter, making them safer for high-scale distributed systems.

-   C. Counters automatically reset every midnight.

-   D. UUIDs take up less storage space.

90.   What is the primary architectural benefit of 'Page Designer' for a developer?

-   A. It automatically writes the CSS for the site.

-   B. It allows developers to create reusable components that merchants can manage without further code changes.

    -> √ Page Designer bridges the gap by letting developers build the 'bricks' and merchants build the 'house'.

-   C. It speeds up the server's response time.

-   D. It replaces the need for controllers.



91.   An ISML template needs to format a currency value correctly for the current locale. Which tag is most appropriate?

-   A. `${pdict.price}`

-   B.

-   C.

    -> √ StringUtils.formatMoney is the standard API way to ensure currency symbols and decimal places match the user's region.

-   D.

92.   In Account Manager, what does the 'API Client' record define?

-   A. The permissions, scopes, and redirect URIs allowed for a specific OCAPI or Headless application.

    -> √ The API Client is the 'identity' of an external app, controlling what data it can access via the REST APIs.

-   B. A list of developers allowed to log into Business Manager.

-   C. The IP address whitelist for the entire realm.

-   D. The password for the SFTP server.



93.   What happens if a developer tries to access 'request.geolocation' on a Sandbox instance?

-   A. It throws a 'SecurityException'.

-   B. The sandbox crashes and needs to be restarted.

-   C. It always returns 'null'.

-   D. It returns a default geolocation object, as sandboxes often lack precise IP-to-location mapping.

    -> √ While the API works, the results on a sandbox are often mocked or less accurate than on Production instances.

94.   Which of the following describes the 'OCAPI Data API' primarily?

-   A. An API for building dynamic product carousels using JavaScript.

-   B. A legacy SOAP interface for inventory updates.

-   C. A set of RESTful resources for administrative tasks like managing catalogs, customers, and orders.

    -> √ The Data API is for 'backend' or 'office' tasks, while the Shop API is for 'storefront' shopper experiences.

-   D. A tool for importing CSV files into the database.



95.   In a 'Remote Include' call, which variables from the parent request are automatically available in the included controller?

-   A. Everything stored in the parent's 'res.viewData'.

    -> X viewData is request-specific; since the include is a 'new' request, it does not share the parent's memory.

-   B. Only the 'session.custom' variables.

-   C. All 'local' variables defined in the parent ISML template.

-   D. None; a Remote Include is a fresh internal request with its own empty pdict.

    -> √ Because it's a new request, you must explicitly pass parameters via the URL (e.g., ?pid=123) if the include needs data.

96.   How do you implement 'Rate Limiting' for a custom Service integration to prevent overwhelming a third-party API?

-   A. You cannot rate limit on the B2C side; the external API must handle it.

-   B. Configure the 'Rate Limit' and 'Interval' settings in the Service definition in Business Manager.

    -> √ The Service Framework has built-in support to cap the number of calls per second/minute at the configuration level.

-   C. Store the last call time in a Custom Object and manually check it.

-   D. Use 'setTimeout()' in your JavaScript code.

    -> X The B2C Rhino engine does not support 'setTimeout' as it is a non-blocking browser function, and scripts must be blocking.

97.   What is the primary risk of using 'dw.system.Transaction.rollback()' in a catch block?

-   A. It only works on Custom Objects, not System Objects like Orders.

-   B. It deletes the current user's session.

-   C. It requires the developer to manually restart the Job.

-   D. It reverts all database changes since the last Transaction.begin(), which might include unintended side effects.

    -> √ Rollback is a 'nuclear' option that clears all pending changes in that thread's transaction buffer.

98.   A developer needs to fetch a list of all Orders placed in the last 24 hours. Which class is best suited for this?

-   A. `ProductMgr`

-   B. `CustomerMgr`

-   C. `SystemMgr`

-   D. `OrderMgr`

    -> √ OrderMgr provides the 'searchOrders' method, which is the most efficient way to query the order database with filters.

99.   Why is 'dw.crypto.MessageDigest' preferred over simple string manipulation for generating a hash?

-   A. It automatically compresses the data to save space.

-   B. It allows you to 'un-hash' the data back to its original form.

-   C. It is the only way to capitalize a string in B2C script.

-   D. It provides standardized, mathematically secure algorithms like SHA-256 for consistent hashing.

    -> √ Cryptographic utilities ensure that the generated strings are collision-resistant and follow industry standards.

100.   In Business Manager, what does the 'Replication' feature do between Staging and Production?

-   A. It creates a backup of the site on an external hard drive.

-   B. It only updates the images on the site.

-   C. It syncs database data (catalogs, prices) and code versions to the live instance.

    -> √ Replication is the controlled process of 'publishing' your work from the preview/edit environment to the live storefront.

-   D. It allows developers to write code directly on the Production server.

101.   What is the purpose of the 'dw.catalog.CatalogMgr.getSiteCatalog()' method?

-   A. To delete all categories in the system.

-   B. To see the list of all external vendors.

-   C. To retrieve the 'Storefront' catalog assigned to the current site for navigation and search.

    -> √ Sites have one primary 'site' catalog used for hierarchy, though they can have many 'standard' catalogs for data source.

-   D. To download a PDF of the current products.



102.   A developer needs to check if a specific 'Promotion' is currently active for the current shopper. Which object should they use?

-   A. `CampaignMgr`

    -> X Campaigns group promotions, but the individual logic for active status is in the PromotionMgr.

-   B. `PromotionMgr`

    -> √ PromotionMgr allows you to check active promotions based on the current session and customer context.

-   C. `BasketMgr`

-   D. `PriceBookMgr`

103.   In ISML, what is the impact of using ?

-   A. The page will be cached until the next Job runs.

    -> X Cache is invalidated by time or manual clearance, not by the execution of arbitrary Jobs.

-   B. The page will be cached until the user logs out.

-   C. The page is never cached, as 'relative' is a deprecated keyword.

-   D. The page will be cached for 2 hours from the time it was first requested.

    -> √ Relative caching sets a fixed duration (TTL) for the page cache starting from the generation moment.

104.   Which of the following is a 'Hard Quota' that cannot be increased even by Salesforce Support?

-   A. `Script.MaxCallStackDepth`

    -> √ Platform-wide safety limits like recursion depth and memory quotas are hardcoded for multi-tenant stability.

-   B. The number of products in a catalog.

-   C. Number of custom attributes on a Product.

-   D. The timeout of a Service call.

105.   Why is it important to use 'dw.web.URLUtils.continueURL()' inside an ISML form action?

-   A. To add a CSRF token automatically.

    -> X CSRF tokens must be added as a hidden input field or via middleware, not via the URL utility.

-   B. To encrypt the data before it is sent to the server.

-   C. To prevent the user from clicking the 'Back' button.

-   D. To ensure the form submits back to the correct controller and maintains the current pipeline context.

    -> √ `continueURL()` dynamically resolves the correct return path for a multi-step form or page logic.



106.   What is the primary purpose of 'dw.util.Locale.getLocale(request.locale)'?

-   A. To translate the site into 50 languages automatically.

-   B. To redirect the user to a different domain.

-   C. To check if the user is a VIP customer.

-   D. To get a detailed object containing currency, language, and country info for the current user.

    -> √ The Locale object provides all the regional context needed to format data for the shopper's country.

107.   How do you define a 'Shared' cartridge that can be used by all sites in a Realm?

-   A. Shared cartridges are not supported; you must duplicate the code.

-   B. Include the cartridge in the Cartridge Path of every individual site in Business Manager.

    -> √ Cartridges are shared by being added to the path of multiple sites; there is no single 'realm-wide' auto-include setting.

-   C. Upload it to the 'Shared' folder on the SFTP.

-   D. Name the cartridge starting with 'shared_'.



108.   In the Job Framework, what happens if the 'read' function returns 'null'?

-   A. The Job step finishes, assuming there is no more data to process.

    -> √ Returning null from the reader is the standard signal to the framework that the end of the data stream has been reached.

-   B. The writer is called with a 'null' object.

-   C. The Job crashes with a 'ReadError'.

-   D. The framework waits 5 seconds and tries again.



109.   What is the specific purpose of the 'dw.catalog.SearchModel.setSearchPhrase()' method?

-   A. To set the keyword or text string that the engine will use to filter product results.

    -> √ This method passes the user's search query (e.g., 'blue shoes') into the search engine's query logic.

-   B. To change the language of the entire site.

-   C. To define which attributes (like Name or ID) are searchable.

-   D. To block certain words from the search engine.



110.   A developer needs to check if a Customer has already 'Used' a specific one-time-use coupon. Which class should they inspect?

-   A. `dw.campaign.CouponLineItem`

    -> √ You can check the redemption history of a coupon by inspecting its line items in previous orders or via the CouponMgr.

-   B. `dw.system.Site`

-   C. `dw.util.Set`

-   D. `dw.catalog.Product`

## Answers

1. How do you extend a Controller without modifying the base cartridge in SFRA?
    B. Create a controller with the same name and use server.extend(module.superModule).
        -> √ This initiates the middleware inheritance chain, preserving the base logic while allowing extensions.


2. In a middleware chain, what happens if you call res.render() and then next()?
    B. An error occurs, and the request fails.
        -> √ Once a response is rendered or sent, the request lifecycle is closed; calling next() afterward throws an exception.
    D. The `next()` call is silently ignored.
        -> SFRA enforces strict lifecycle management and will explicitly throw an error rather than failing silently.


3. Which middleware functions are required to enable CSRF protection on a specific route pair in SFRA?
    B. `csrfProtection.generateToken` for GET and `csrfProtection.validateRequest` for POST.
        -> √ The GET route needs to generate the token for the view, and the POST route needs to validate the submitted token.
    D. `security.enableCSRF()` on the POST route.
        -> There is no such method in the standard SFRA security middleware

4. How do you prevent a specific Controller route from being cached at the web-tier?
    D. Use `res.cacheExpiration(0)`.
        -> √ Setting the expiration to zero explicitly tells the platform's page cache not to store this response.

5. If a site's cartridge path is 'plugin_wishlist:app_custom:app_storefront_base', which 'ProductModel.js' is used if it exists in all three?
    A. All three are merged automatically.
        -> Scripts are not automatically merged; developers must explicitly use superModule to chain logic.
    C. The one in plugin_wishlist.
        -> √ The platform resolves file lookups from left to right; the leftmost cartridge always has the highest priority.

6. How can you pass data from a Controller to an ISML template in SFRA?
    A. Pass a JSON object as the second argument to res.render('templateName', { data: value }).
        -> √ The properties of this object become accessible via the pdict variable in the ISML template.
    C. Use the `pdict.set()` method in the controller.
        -> Controllers in SFRA use the res.render or res.setViewData methods, not direct pdict manipulation.

7. What is the primary difference between `server.get()` and `server.append()` in SFRA?
    A. `server.get` defines a new route; `server.append` adds middleware to the end of an existing route.
        -> √ Get initializes the endpoint, while append modifies a route inherited via superModule.

8. How do you securely access HTTP Cookies in a B2C Script?
    C. Via `request.httpCookies`.
        -> √ The request object provides a dedicated property to access incoming client cookies safely.

9. Why is it dangerous to store large objects in session.custom?
    C. It increases the session size, degrading performance due to serialization overhead.
        -> √ The entire session object must be saved and loaded across the application servers for every single request.

10. How do you trigger a 410 (Gone) status code for a discontinued product?
    C. res.setStatusCode(410).
        -> √ Setting the status code explicitly on the response object informs search engines the product is permanently removed.
    D. res.redirect('410').
        -> Redirects issue 301 or 302 status codes, not 410.

11. What is the primary constraint regarding res.viewData in SFRA?
    A. It is a standard JS object, but it must be kept lean to avoid memory overhead during template rendering.
        -> √ Passing massive datasets (like full API responses) to the template engine consumes significant CPU and memory quotas.

12. How do you handle multi-language support for error messages generated in a Controller?
    A. Use `dw.web.Resource.msg('error.key', 'bundle', null)`.
        -> √ The Resource class safely fetches the correct localized string based on the user's current session locale.

13. Which SFRA object is typically responsible for generating the 'Breadcrumbs' logic?
    B. The Product or Search model/decorator.
        -> √ Models analyze the category hierarchy of the current product or search term to build the breadcrumb data structure.
    C. The URLUtils class.
        -> URLUtils builds links but doesn't inherently understand category hierarchy structures.

14. How can a developer detect if the current request is coming from a 'Search Engine Bot'?
    B. Check `request.httpUserAgent`.
        -> √ The User-Agent string identifies the browser or crawler making the request (e.g., Googlebot).
    D. Use `dw.system.Site.isCrawler()`.
        -> The Site configuration does not evaluate individual incoming requests.

15. How do you execute a redirect to the Home Page from within an SFRA Controller?
    B. `res.redirect(URLUtils.url('Home-Show'))`.
        -> √ This uses the URL utility to safely construct the path and issues a 302 redirect via the response object.

16. What is the strict platform limit for Script.MaxCallStackDepth?
    A. 500
        -> A stack this deep would pose a significant stability risk to the shared JVM.
    B. 50
        -> √ Salesforce restricts the call stack depth to 50 to prevent infinite recursion from crashing application threads.

17. How should a developer query for Custom Objects to avoid hitting performance bottlenecks?
    A. Use `CustomObjectMgr.queryCustomObjects` with a specific indexed attribute in the query string.
        -> √ Using indexed attributes allows the database to filter results efficiently without loading all objects into memory.
    D. Use direct SQL queries.
        -> Direct SQL access is strictly prohibited and impossible within B2C Script.

18. What happens if a developer exceeds the Object.MaxCustomAttributes quota?
    D. They cannot create new attribute definitions in Business Manager for that object type.
        -> √ This is a hard schema limit imposed by Salesforce to protect database performance.

19. If a custom requirement dictates storing an Array of complex objects on a Customer Profile, what is the best practice?
    B. Stringify the array to JSON and store it in a 'Text' or 'Long String' attribute.
        -> √ B2C Commerce does not support 'Arrays of Objects' natively, so JSON serialization into a text field is the standard workaround.

20. What is the purpose of `dw.system.Transaction.begin()`?
    C. To manually start a database transaction when explicit control is needed.
        -> √ While Transaction.wrap() is preferred for safety, begin() allows manual start of atomic database operations.

21. How many price books can be active for a single site at once?
    C. Multiple, and they are evaluated based on the assigned priority in Business Manager.
        -> √ Sites often use multiple active price books (e.g., standard, sale, clearance) stacked via priority.

22. What is the technical difference between a 'System Quota' and a 'Service Limit'?
    D. Quotas are hard platform-enforced limits; Service Limits (like API timeouts) can sometimes be configured.
        -> √ Quotas protect the shared JVM and cannot be overridden, whereas service limits manage integration rules.


23. How do you retrieve a site preference named 'myConfig' via script?
    A. `session.custom.myConfig`
    B. `request.getPreference('myConfig')`
    C. `Site.preferences.myConfig`
    D. `dw.system.Site.current.getCustomPreferenceValue('myConfig')`
        -> √ This is the secure, standard API method to access developer-defined custom preferences.

24. What is the maximum length of a standard 'String' attribute in B2C Commerce?
    A. 255 characters.
        -> 255 is common in standard SQL, but Salesforce allows up to 4,000 for standard strings.
    C. 4,000 characters.
        -> √ This is the database column limit for standard String types; longer data requires the 'Text' type.

25. How do you programmatically delete a persistent cookie from the user's browser?
    D. Set its max age to 0 and add it to the response object.
        -> √ Browsers delete cookies when they receive an update instructing them that the cookie has expired (age 0).

26. Why is it highly recommended to use LocalServiceRegistry over `dw.net.HTTPClient`?
    B. LocalServiceRegistry provides integrated logging, rate monitoring, and circuit breakers.
        -> √ The Service Framework adds enterprise-grade resilience and analytics that raw HTTP clients lack.
    D. `LocalServiceRegistry` executes significantly faster.
        -> The network speed is the same; the advantage is in safety and tracking.

27. What behavior does the api.MaxObjectCount quota restrict?
    B. It limits the number of persistent objects (like products or orders) instantiated in a single request.
        -> √ Creating massive amounts of persistent objects in memory threatens the heap space of the JVM.





## Key Points



**Title:** Advanced SFRA Development and B2C Platform Architecture

**Subject:** Salesforce B2C Commerce (Demandware)

**Topics:**

-   SFRA Controller & Middleware Lifecycle
-   Platform Quotas and Performance Limits
-   Integration Framework (OCAPI & Service Registry)
-   Jobs, Data Processing, and ISML

**Summary:** This guide covers the architectural patterns of the Storefront Reference Architecture (SFRA), focusing on how to extend functionality without modifying the base, managing the request-response lifecycle through middleware, and adhering to strict platform constraints to ensure scalability and performance.

**Key Concepts:**

-   **Controller Extension:** Use `server.extend(module.superModule)` to inherit from a base controller. `server.append` adds logic to the end of a middleware chain, while `server.replace` overwrites it.
-   **The Middleware Chain:** Middleware functions execute sequentially. **Critical Rule:** Never call `next()` after `res.render()` or `res.json()`, as these methods finalize the response.
-   **CSRF Protection:** In SFRA, CSRF is handled via a route-pair strategy. The `GET` route uses `csrfProtection.generateToken` and the `POST` route uses `csrfProtection.validateRequest`.
-   **Platform Quotas:** * `Script.MaxCallStackDepth`: Limited to **50**.
    -   `String Attribute Length`: Standard attributes are limited to **4,000 characters**.
    -   `api.MaxObjectCount`: Limits the number of persistent objects (Products, Orders) instantiated in a single request.
-   **Service Framework:** Use `LocalServiceRegistry` for external calls. It provides built-in circuit breakers (to prevent "hanging" checkouts), rate limiting, and centralized logging.
-   **Cache Management:**
    -   `Local Include`: Shares the parent's cache.
    -   `Remote Include`: Generates a new request with its own independent cache policy (crucial for dynamic components like baskets).

**Vocabulary List:**

-   **module.superModule:** A reserved keyword used to reference the next version of a module in the cartridge path.
-   **res.viewData:** A standard JavaScript object used to pass data from the controller to the ISML template.
-   **Circuit Breaker:** A state in the Service Framework that automatically fails a service call if a threshold of errors is met, preventing system-wide latency.
-   **OCAPI Hook:** Custom script execution points (before/after) for standard Open Commerce API resources.
-   **Chunk Processing:** A job model involving an ItemReader, ItemProcessor, and ItemWriter to handle large datasets efficiently.

**Key Questions:**

-   Why is it preferred to use `XMLStreamWriter` over string concatenation for large file exports? (Answer: To avoid memory overhead and string length limits).
-   What is the difference between `server.get` and `server.append`? (Answer: `get` creates a new route; `append` adds middleware to an existing one).
-   How does the platform handle multiple active Price Books? (Answer: They are evaluated based on the priority assigned in Business Manager).
-   Which class is used for executing storefront product searches and filtering? (Answer: `dw.catalog.ProductSearchModel`).
-   How do you trigger a 410 status code in SFRA? (Answer: `res.setStatusCode(410)`).



# Advanced Study Guide: Salesforce B2C Commerce Developer (Hard)

**Subject:** Advanced Architecture, Performance, and Integration **Topics:**

-   Multi-cartridge Overlay Logic
-   Advanced Service Framework (Mocking, Circuit Breakers)
-   High-Volume Job Processing & Quota Avoidance
-   OCAPI Hooks & Custom Resource Implementation
-   Search & SEO Architecture
-   Security (CSRF, XSS, and OCAPI Permissions)

## Summary

This document serves as a "deep dive" into the most challenging aspects of the Salesforce B2C Commerce platform. It covers the technical nuances required to build scalable, high-performance global e-commerce sites, specifically focusing on the "Cartridge Path" logic, complex data structures, and the strict governance of the B2C Commerce Quotas.

## Key Concepts

### 1. Cartridge Overlay & `superModule`

-   **Priority:** The leftmost cartridge in the path always takes precedence.
-   **Inheritance:** Use `module.superModule` to call original logic. If you have three cartridges (A, B, Base) and A/B both override a model, `superModule` in A points to B.
-   **Static Assets:** Unlike scripts, static assets (CSS/JS) do not support `superModule`. The first one found in the path is used, and the rest are ignored.

### 2. High-Performance Job Framework

-   **Chunking:** Use `ChunkProcessing` steps for massive datasets to handle transactions automatically.
-   **Memory Safety:** Never use `.toArray()` on a `SeekableIterator` with more than 1,000 items.
-   **Resource Management:** Always wrap file and database operations in `try/finally` blocks to ensure `.close()` is called on writers and iterators.

### 3. Advanced Service Framework

-   **Circuit Breaker:** Protects the application server threads. If a service times out X times in Y minutes, it "trips" and fails instantly for Z minutes.
-   **Rate Limiting:** Distinct from Circuit Breakers; ensures you don't overwhelm the third-party API provider.
-   **Filtering:** Use the `filterLogMessage` callback to mask sensitive PII or PCI data from the communication logs.

## Vocabulary List

-   **Idempotency:** The ability for a Job or Service call to be executed multiple times without changing the result beyond the initial application (crucial for Order processing).
-   **Pipelet:** (Legacy) Pre-packaged logic units used in Pipelines. Modern SFRA uses **Script Modules**.
-   **External Inventory:** A configuration where inventory levels are NOT stored in B2C Commerce but fetched via real-time Service calls during checkout.
-   **Search Sharding:** The process of splitting the search index across multiple servers to improve performance.
-   **Cache Partitioning:** Ensuring that user-specific data (like a mini-cart) is excluded from page caching via Remote Includes or AJAX.



# SFRA Developer Study Guide

**Subject:** Salesforce B2C Commerce Cloud (SFRA) Development

**Topics:**

-   Controller Middleware & Route Logic
-   OCAPI (Open Commerce API) Architecture
-   Job Framework & Chunk Processing
-   Platform Quotas & Performance Optimization
-   Service Framework & Circuit Breakers

**Summary:** This study guide covers the core architectural components of Salesforce B2C Commerce Cloud, focusing on the Storefront Reference Architecture (SFRA). It details how to extend functionality without modifying base code, the lifecycle of middleware chains, secure service integrations, and the limitations imposed by platform quotas to ensure high-performance e-commerce experiences.

**Key Concepts:**

-   **The Middleware Chain:** SFRA uses a stacked middleware approach. Crucially, calling `res.render()` effectively ends the response preparation; calling `next()` after a render will cause an error because the response headers and body have already been initiated.
-   **Cartridge Path Resolution:** When a resource (like a Model or Script) exists in multiple cartridges, the platform picks the first occurrence based on the **left-to-right** order of the cartridge path.
-   **Remote vs. Local Includes:** A **Local Include** (`isinclude template`) runs in the same request thread and shares the parent's memory/cache. A **Remote Include** (`isinclude url`) triggers a completely new internal request, which is essential for components that need independent caching (like a personalized header on a cached PLP).
-   **Job Chunk Processing:** This model is designed for large data sets. The `read` function fetches items; if it returns `null`, the step ends. The `process` function can filter items by returning `null`, preventing them from reaching the `write` function.
-   **Circuit Breakers:** A feature of the Service Framework that "trips" (sets status to `SERVICE_UNAVAILABLE`) when an external service fails repeatedly, preventing the storefront from hanging while waiting for timed-out responses.

**Vocabulary List:**

-   **SFRA:** Storefront Reference Architecture; the modern development model for B2C Commerce.
-   **module.superModule:** A reserved keyword used in `server.extend()` to reference the next cartridge in the path that contains the same controller name.
-   **OCAPI:** Open Commerce API; a RESTful interface for interacting with the platform externally (Shop, Data, and Meta APIs).
-   **pdict:** The "Pipeline Dictionary"; a legacy term still used in ISML to access data passed from the controller's `res.viewData`.
-   **CSRF:** Cross-Site Request Forgery; protection in SFRA requires `csrfProtection.generateToken` (GET) and `csrfProtection.validateRequest` (POST).
-   **Rhino Engine:** The specific JavaScript engine used by B2C Commerce, which supports ES5 and some specific ES6 features (like Map/Set) but with limitations.

**Key Questions:**

-   **Why does `server.append` differ from `server.get`?** `server.get` defines a brand-new route, while `server.append` adds new middleware logic to the *end* of an existing route defined earlier in the cartridge path.
-   **What is the "Hard Quota" for call stack depth?** The limit is strictly **50**. Exceeding this via deep recursion will cause the script to terminate.
-   **How do you handle a 429 "Too Many Requests" error in a Service?** The best practice is to implement **exponential backoff** within the script logic to retry the call at increasing intervals.
-   **What is the purpose of `steptypes.json`?** It is the configuration file required to register custom Job steps and define the parameters that will appear for merchants in Business Manager.
-   **How do you share data across sites in a single Realm?** Use **Custom Objects** with the **Site-wide** (Global) scope rather than Site-specific scope.



## 60 Mastery Questions (Active Recall)

### Section 1: SFRA & Controller Logic (1-15)

1.  **Q:** How do you extend a Controller without modifying the base cartridge?
    -   **A:** Create a controller with the same name in your custom cartridge and use `server.extend(module.superModule)`.
    -   **Rationale:** This initiates the middleware inheritance chain.
2.  **Q:** In a middleware chain, what happens if you call `res.render()` and then `next()`?
    -   **A:** An error occurs. Once a response is rendered/sent, the chain cannot continue to the next step.
3.  **Q:** Which middleware is required to enable CSRF protection on a specific route?
    -   **A:** `csrfProtection.generateToken` for the GET route and `csrfProtection.validateRequest` for the POST route.
4.  **Q:** How do you prevent a specific Controller route from being cached at the web-tier?
    -   **A:** Use `res.cacheExpiration(0)`.
5.  **Q:** If a cartridge path is `plugin_wishlist:app_custom:app_storefront_base`, which `cartridge/scripts/models/ProductModel.js` is used?
    -   **A:** The one in `plugin_wishlist`.
6.  **Q:** How can you pass data from a Controller to an ISML template?
    -   **A:** Pass a JSON object as the second argument to `res.render('templateName', { data: value })`.
7.  **Q:** What is the difference between `server.get` and `server.append`?
    -   **A:** `get` defines a new route; `append` adds middleware to the end of an existing route defined in a `superModule`.
8.  **Q:** How do you access HTTP Cookies in a B2C Script?
    -   **A:** Via `request.httpCookies`.
9.  **Q:** Why is it dangerous to store large objects in `session.custom`?
    -   **A:** It increases the session size, which can degrade performance as the session is serialized/deserialized on every request.
10.  **Q:** How do you trigger a 410 (Gone) status code for a discontinued product?
     -   **A:** `res.setStatusCode(410)`.
11.  **Q:** What is the limit of `res.viewData`?
     -   **A:** It is a standard JS object, but keep it lean to avoid memory overhead during template rendering.
12.  **Q:** How do you handle multi-language support for error messages in a Controller?
     -   **A:** Use `dw.web.Resource.msg('error.key', 'bundle', null)`.
13.  **Q:** Which object handles the "Breadcrumbs" logic in SFRA?
     -   **A:** Usually the `Product` or `Search` model/decorator.
14.  **Q:** How do you detect a "Search Engine Bot" in a script?
     -   **A:** Check `request.httpUserAgent`.
15.  **Q:** How do you redirect a user to the Home Page from a Controller?
     -   **A:** `res.redirect(URLUtils.url('Home-Show'))`.

### Section 2: Data & Quotas (16-30)

1.  **Q:** What is the strict limit for `Script.MaxCallStackDepth`?
    -   **A:** 50. Deep recursion is forbidden.
2.  **Q:** How do you query for Custom Objects without hitting a performance bottleneck?
    -   **A:** Use `CustomObjectMgr.queryCustomObjects` with a specific indexed attribute in the query string.
3.  **Q:** What happens if you exceed `Object.MaxCustomAttributes`?
    -   **A:** You cannot create new attribute definitions in Business Manager for that object type.
4.  **Q:** How do you store an Array of objects in a Custom Attribute?
    -   **A:** Stringify the array to JSON and store it in a "Text" or "Long String" attribute.
5.  **Q:** What is the purpose of `dw.system.Transaction.begin()`?
    -   **A:** To manually start a database transaction (though `Transaction.wrap` is preferred).
6.  **Q:** How many price books can be active for a single site at once?
    -   **A:** Multiple, but they are evaluated based on the assigned priority in Business Manager.
7.  **Q:** What is a "System Quota" vs. a "Service Limit"?
    -   **A:** Quotas are platform-enforced (cannot be changed); Service Limits (like API timeouts) can sometimes be configured.
8.  **Q:** How do you retrieve a site preference named `myConfig`?
    -   **A:** `dw.system.Site.current.getCustomPreferenceValue('myConfig')`.
9.  **Q:** What is the max length of a `String` attribute in B2C Commerce?
    -   **A:** 4,000 characters for standard Strings; significantly more for "Text" types.
10.  **Q:** How do you delete a persistent cookie?
     -   **A:** Set its max age to 0 and add it to the response.
11.  **Q:** Why use `LocalServiceRegistry` over `dw.net.HTTPClient`?
     -   **A:** `LocalServiceRegistry` provides integrated logging, monitoring, and circuit breakers.
12.  **Q:** What is the `api.MaxObjectCount` quota?
     -   **A:** It limits the number of persistent objects (like products) created in a single request.
13.  **Q:** How do you handle "Deadlocks" in B2C Commerce?
     -   **A:** Ensure all scripts access objects in the same order and keep transactions as short as possible.
14.  **Q:** Can you use `Map` and `Set` in B2C Script?
     -   **A:** Yes, but they are the versions provided by the Rhino engine (ES5/partial ES6).
15.  **Q:** How do you refresh the Search Index via code?
     -   **A:** You cannot trigger a full rebuild from Script; you must use a Job with the `Search-Index` step.

### Section 3: Integration & Services (31-45)

1.  **Q:** What is the `createRequest` callback in the Service Framework?
    -   **A:** It's where you define the URL, headers, and request body for the outgoing call.
2.  **Q:** How do you enable "Mock Mode" for a service in Business Manager?
    -   **A:** Administration > Operations > Services > [Service] > Enable "Mocked".
3.  **Q:** What is the difference between `GET` and `POST` in OCAPI?
    -   **A:** `GET` retrieves data; `POST` creates resources or performs complex actions like login.
4.  **Q:** How do you secure an OCAPI call from a mobile app?
    -   **A:** Use a JWT (JSON Web Token) and verify the Client ID.
5.  **Q:** What is a "Hook" in OCAPI?
    -   **A:** A script that executes before or after a standard OCAPI resource call (e.g., `dw.ocapi.shop.basket.calculate`).
6.  **Q:** How do you pass an API Key securely to a service?
    -   **A:** Store it in the `Service Credentials` password field in Business Manager.
7.  **Q:** What is the default timeout for a Service call?
    -   **A:** Usually 10 seconds, but it should be configured lower for storefront performance.
8.  **Q:** How do you handle a `429 Too Many Requests` response from an external API?
    -   **A:** Implement a retry logic with exponential backoff within the service callback.
9.  **Q:** Can OCAPI be used to manage Site Preferences?
    -   **A:** Yes, using the **Data API**, but not the Shop API.
10.  **Q:** What is the purpose of the `parseResponse` callback?
     -   **A:** To convert the raw string/JSON response from a service into a DTO (Data Transfer Object).
11.  **Q:** How do you debug a failed Service call?
     -   **A:** Check the `service-*.log` files in the Log Center.
12.  **Q:** What is a "Local Include" in ISML?
     -   **A:** `<isinclude template="..." />` which executes in the same thread/session as the parent.
13.  **Q:** What is a "Remote Include"?
     -   **A:** `<isinclude url="..." />` which initiates a new request, allowing for independent caching.
14.  **Q:** How do you implement a Webhook in B2C Commerce?
     -   **A:** Create a public Controller route and provide that URL to the external system.
15.  **Q:** What is the benefit of "Service Profiling"?
     -   **A:** It helps identify which external integrations are slowing down the checkout flow.

### Section 4: Advanced Storefront & Jobs (46-60)

1.  **Q:** How do you create a "Job Step" that runs a custom script?
    -   **A:** Use the `ExecuteScriptModule` step type and provide the module path and function name.
2.  **Q:** What is the `onOpen` hook in a Job Step?
    -   **A:** It's called once before any items are processed to initialize resources.
3.  **Q:** How do you pass parameters to a Job Step?
    -   **A:** Define them in the `steptypes.json` file.
4.  **Q:** Why use `dw.io.XMLStreamWriter` instead of building a string for large exports?
    -   **A:** To stream the data directly to the file system and avoid memory overflows.
5.  **Q:** How do you handle "Catalog Replication" failures?
    -   **A:** Check the replication logs; usually caused by locked objects or invalid category assignments.
6.  **Q:** What is "A/B Testing" in B2C Commerce?
    -   **A:** A tool to test different content, layouts, or promotions on segments of traffic.
7.  **Q:** How do you retrieve the "Current Promotion" applied to a line item?
    -   **A:** Iterate through `lineItem.priceAdjustments`.
8.  **Q:** What is a "Sitemap" and how is it generated?
    -   **A:** A file for search engines; generated via the Sitemap Job in Merchant Tools.
9.  **Q:** How do you implement "Infinite Scroll" on a PLP (Product Listing Page)?
    -   **A:** Use an AJAX call to a Controller that renders only the product tiles and appends them to the DOM.
10.  **Q:** What is the "Profile Wrapper" in SFRA unit tests?
     -   **A:** A mock object used to simulate a user profile without hitting the database.
11.  **Q:** How do you ensure "Thread Safety" in a Job?
     -   **A:** Avoid using global variables that might be modified by parallel threads if using parallel execution.
12.  **Q:** What is the `dw.catalog.ProductSearchModel`?
     -   **A:** The primary API class for executing searches and facet filtering.
13.  **Q:** How do you get the URL of a product image with a specific transformation?
     -   **A:** `product.getImage('large', 0).getURL()`.
14.  **Q:** What is a "Custom Cache Key"?
     -   **A:** A parameter added to a Remote Include URL to ensure different versions of a component are cached (e.g., `?isLoggedIn=true`).
15.  **Q:** How do you handle "Global Errors" (500 errors) in SFRA?
     -   **A:** Customize the `Error.js` controller to render a friendly maintenance page.
