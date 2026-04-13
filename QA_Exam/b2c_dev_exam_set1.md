intent=type | best_matched_skill=none | skill_selection=complete

Here are 5 sets of practice questions for the Salesforce Certified B2C Commerce Developer exam. Each set contains 12 questions (total 60). Each question indicates whether you should select one, two, or three answers. An answer key with concise explanations is included at the end of each set.

Set 1: B2C Commerce Setup and SFRA Fundamentals
1) In a sandbox, where should you deploy a custom cartridge via WebDAV so it becomes available to add to a site’s cartridge path? (Select one)
A. /cartridges/current
B. /versioned/cartridges/<code-version>/cartridges
C. /static/default/cartridges
D. /on-demand/<code-version>/cartridges

Answer: B
Explanation: Code is deployed under the active code version folder. Business Manager exposes code versions from /versioned/cartridges/<code-version>.

2) After uploading a cartridge to the active code version, what must happen before storefront requests can execute controllers in that cartridge? (Select one)
A. Restart the application server
B. Add the cartridge to the site’s cartridge path and clear caches
C. Rebuild ISML to HTML artifacts manually
D. Assign the cartridge to a replication target

Answer: B
Explanation: Controllers resolve by traversing the cartridge path. Clearing cache ensures fresh resolution.

3) When installing SFRA locally, which statement is accurate about its structure? (Select one)
A. SFRA stores all server-side logic in ISML templates
B. SFRA separates controllers, models, and views with routing via server.js
C. SFRA requires no middleware for CSRF protection
D. SFRA disallows decorators on product models

Answer: B
Explanation: SFRA is MVC-like with controllers, models/decorators, and ISML templates; routing is in server code.

4) A business requires a new country-specific taxation setting for a new site. Where do you configure the taxation and currency defaults? (Select one)
A. Merchant Tools > Ordering > Taxation
B. Administration > Sites > Manage Sites > [Site] > Settings
C. Administration > Global Preferences > Currency
D. Merchant Tools > Site Preferences > Localization

Answer: B
Explanation: Site-level settings define taxation and default currency.

5) You need to expose a new cartridge’s JavaScript controllers. Which is the correct order in the site cartridge path? (Select one)
A. app_storefront_base before custom cartridges
B. Custom cartridges first; app_storefront_base last
C. app_storefront_base only; custom cartridges added in BM modules
D. The order doesn’t matter

Answer: B
Explanation: Put custom cartridges before app_storefront_base so overrides and extensions resolve first.

6) When adding a new site to an instance, which two tasks are required for storefront availability? (Select two)
A. Configure hostname aliases/DNS mapping
B. Assign a code version to the site
C. Create a dedicated replication process
D. Add a valid cartridge path

Answer: B, D
Explanation: The site must reference a code version and cartridge path; DNS/aliases occur outside initial BM steps.

7) What is the recommended approach to extending the product model in SFRA? (Select one)
A. Modify the base Product model directly
B. Use decorators to add computed properties to the product object
C. Add properties in the ISML layer
D. Add custom fields to the product price book

Answer: B
Explanation: SFRA promotes decorators to extend models in a maintainable way.

8) Which two tools are typically used together to upload and version code to a B2C sandbox? (Select two)
A. WebDAV client
B. OCAPI Shop API
C. Git
D. Page Designer

Answer: A, C
Explanation: You typically manage source with Git and deploy to sandboxes via WebDAV.

9) What is the purpose of the dw.json file when using UX Studio or compatible IDEs? (Select one)
A. Configure OCAPI permissions
B. Define Business Manager locales
C. Define server connection (hostname, code version) for upload
D. Toggle log levels

Answer: C
Explanation: dw.json tells the IDE where and how to upload to the sandbox.

10) Which statement about SFRA updates is correct? (Select one)
A. Updates are auto-merged into custom cartridges
B. Updates can affect templates and controllers; maintain extensions through composition/decorators
C. Updates never change CSS structure
D. Updates are backward compatible for all hooks

Answer: B
Explanation: Maintain customizations via extension points and decorators to tolerate updates.

11) To test that a cartridge was added correctly to the cartridge path, which is the most direct method? (Select one)
A. Trigger a BM cache warmup
B. Hit a controller route unique to that cartridge and observe response
C. Recompile ISML files
D. Re-index the product catalog

Answer: B
Explanation: Exercise a known route exposed solely by the cartridge to validate path precedence.

12) Which three items are typical in an SFRA cartridge’s folder structure? (Select three)
A. cartridge/scripts
B. cartridge/controllers
C. cartridge/models (or decorators/factories)
D. cartridge/sfcc-logs

Answer: A, B, C
Explanation: Scripts, controllers, and models/decorators are common; there’s no sfcc-logs folder in cartridges.

Set 2: Working with Business Manager and Data Management
1) Where do you import site data such as catalogs or inventory lists? (Select one)
A. Administration > Code Versions
B. Merchant Tools > Site Import & Export
C. Merchant Tools > SEO
D. Administration > Roles & Permissions

Answer: B
Explanation: BM provides Site Import & Export for data XML/CSV.

2) A business wants to enable a new payment processor. Where is this configured? (Select one)
A. Merchant Tools > Ordering > Payment Methods/Processors
B. Administration > Global Preferences > Payment
C. Merchant Tools > Services > Payment
D. Merchant Tools > Site Preferences > Payments

Answer: A
Explanation: Payment methods and processors are configured under Ordering.

3) To make a new attribute searchable, you must do which two actions? (Select two)
A. Add it to searchable fields in site search preferences
B. Mark the attribute as searchable in attribute settings
C. Rebuild the search index
D. Update the Page Designer component

Answer: B, C
Explanation: Mark attribute searchable and rebuild indexes to include it.

4) Where do you create a search refinement definition for the storefront? (Select one)
A. Merchant Tools > SEO > URL Rules
B. Merchant Tools > Search > Refine Settings
C. Merchant Tools > Search > Search Refinements
D. Merchant Tools > Products and Catalogs > Catalogs

Answer: C
Explanation: Search refinements are configured under Search.

5) A performance issue is suspected around a custom controller. Which two tools help diagnose this? (Select two)
A. Request Logs and custom log categories
B. Profilers in BM
C. OCAPI Data API
D. URL Rules

Answer: A, B
Explanation: Use log categories and profilers to measure controller performance.

6) To log only non-sensitive data at INFO level to a custom log file, what must be configured? (Select one)
A. Log rotation in WebDAV
B. Log categories and appenders in BM
C. CSRF token in server middleware
D. Cache inheritance

Answer: B
Explanation: BM log settings control categories, levels, and custom appenders.

7) A new custom object is needed to store external mapping IDs. What two steps are necessary? (Select two)
A. Create the custom object type and its attributes in BM
B. Add the object to the cartridge path
C. Configure permissions and ensure OCAPI/Data API access if needed
D. Add the object to the search index refinements

Answer: A, C
Explanation: Define the type/attributes, and if accessed externally, configure permissions.

8) To expose a new attribute on Product in the storefront, which locations are typically touched? (Select two)
A. ISML templates rendering product details
B. Model decorators/factories
C. The replication configuration
D. Code version folder name

Answer: A, B
Explanation: Extend the model and update templates to display values.

9) When adjusting site search synonyms for better recall of terms, where do you configure this? (Select one)
A. Merchant Tools > Search > Dictionaries
B. Merchant Tools > SEO > Redirects
C. Administration > Site Preferences
D. Merchant Tools > Content > Assets

Answer: A
Explanation: Dictionaries manage synonyms, stop words, etc.

10) A data import is failing due to a malformed XML. What is the first best step? (Select one)
A. Clear site caches
B. Validate the XML against the schema expected by BM Import
C. Re-upload to a different directory
D. Trigger replication

Answer: B
Explanation: Validate input file structure against the expected XSD.

11) You need to allow an external integration to access a custom object via OCAPI Data. What two actions are required? (Select two)
A. Update ocapi.json to permit read/write on the custom object
B. Add the integration host to cspTrustedSites
C. Configure client ID with appropriate API settings in BM
D. Add a custom URL rule

Answer: A, C
Explanation: OCAPI permissions are defined in ocapi.json and tied to client credentials.

12) Which three Business Manager areas are most relevant to merchandising teams rather than developers? (Select three)
A. Products and Catalogs
B. Search and Search Refinements
C. Services Framework
D. Content (Assets, Slots, Page Designer)

Answer: A, B, D
Explanation: Merchandisers work with products, content, and search tools.

Set 3: Application Development — Controllers, ISML, Forms, Hooks
1) In SFRA, which middleware should wrap routes that accept form submissions? (Select one)
A. server.middleware.https only
B. csrfProtection.validateRequest paired with csrfProtection.generateToken
C. consentTracking.consent
D. cache.applyCache

Answer: B
Explanation: CSRF protection is required for POSTs and form handling in SFRA.

2) Which ISML tag is used to include a component that can render in a separate pipeline and cache independently? (Select one)
A. isinclude
B. isdecorate
C. iscomponent
D. iscache

Answer: C
Explanation: iscomponent supports modular, independently cachable render units.

3) To pass server-side data to an ISML template from a controller, what method is typically used? (Select one)
A. res.redirect(URLUtils.url(…))
B. res.render(template, viewDataObject)
C. next()
D. res.json(viewDataObject)

Answer: B
Explanation: res.render accepts a template path and a view-data hash.

4) A route should return JSON instead of rendering a template. Which two steps are correct? (Select two)
A. Set response content type to application/json
B. Call res.render with a JSON template
C. Use res.json or write JSON string and set status
D. Override site preference DisableJSON to false

Answer: A, C
Explanation: Return JSON via res.json (preferred) and ensure proper content type.

5) You must decorate the product with a computed boolean flag “isClearance” based on price book. Where should this logic live? (Select one)
A. In the ISML template using script tags
B. In a product decorator module applied by the model factory
C. In the OCAPI configuration
D. In Page Designer component JSON

Answer: B
Explanation: Use decorators/factories to keep business logic out of templates.

6) Given a requirement to validate and persist a custom form, which three pieces are typical? (Select three)
A. forms XML definition under forms/
B. Controller route using server.post with CSRF middleware
C. Client-side JS only, no server validation
D. Form handler that binds and validates fields via Form API

Answer: A, B, D
Explanation: Define forms XML, secure POST route, and use SFCC Form bindings/validation server-side.

7) Which hook would you use to intercept basket calculation logic without modifying core controller behavior? (Select one)
A. dw.web.HttpParameterMap
B. app_*.properties
C. Hook dw.ocapi.shop.basket.beforeGET
D. Hook implementations such as app.calculateLineItem or similar extension points

Answer: D
Explanation: Use documented hook extension points for pricing, taxes, or calculations.

8) For a new marketing landing page in Page Designer, what two artifacts must you create? (Select two)
A. A page type definition
B. A job to publish the page nightly
C. Components (and placements) used within that page type
D. ocapi.json entry to authorize render

Answer: A, C
Explanation: Page types and components define marketer-editable structures.

9) Where do you define localized resources used in templates? (Select one)
A. cartridge/templates/resources/*.properties per locale
B. cartridge/scripts/i18n.js
C. Global BM preferences
D. services.json

Answer: A
Explanation: ISML uses properties files under templates/resources for i18n.

10) What is the best practice for logging from a controller? (Select one)
A. Use System.out.println
B. Use dw.system.Logger.getLogger(category, file).info/debug/error
C. Write to a custom text file via WebDAV
D. Log only in production

Answer: B
Explanation: Use Logger with configured categories and levels.

11) A controller violates best practices by doing synchronous HTTP calls on every product detail view. Which two changes improve scalability? (Select two)
A. Cache results where possible via response or application cache
B. Move calls into decorators executed for each request
C. Use Service Framework with proper timeouts and circuit breakers and cache at model layer
D. Increase Business Manager log levels to FATAL

Answer: A, C
Explanation: Use the Service Framework with caching and resiliency patterns; avoid per-request blocking calls when possible.

12) For a route that renders cached content varying by locale and currency, which approach is recommended? (Select one)
A. Disable cache
B. Use res.cachePeriod with varyBy parameters, or use iscache with vary attributes
C. Use only CDN-level caching
D. Use OCAPI caching only

Answer: B
Explanation: Use platform cache directives (iscache or res.cachePeriod) to vary content by keys.

Set 4: Services, OCAPI, Jobs, and Integrations
1) To create a robust integration to an external REST API, which three Service Framework configurations are key? (Select three)
A. Connection and socket timeouts
B. Circuit breaker/retry policies and error handling
C. OCAPI Data credential reuse
D. Caching policy/response parsing

Answer: A, B, D
Explanation: Timeouts, resiliency, and parsing/caching are core Service Framework concerns.

2) Where are service credentials (username/password/API keys) securely stored for services? (Select one)
A. In cartridge scripts
B. In dw.json
C. In BM service profiles/credentials
D. In site preferences resources.properties

Answer: C
Explanation: Store secrets in BM service credentials, not code.

3) You must expose baskets to an external OMS via OCAPI Shop. Which two actions are required? (Select two)
A. Update OCAPI Shop permissions in ocapi.json to allow basket read/write
B. Create a custom cartridge to simulate OCAPI
C. Configure client ID/secret and assign to the OCAPI setting
D. Enable cartridge-level setting shop.ocapi.enabled=true

Answer: A, C
Explanation: OCAPI access requires client credentials and appropriate permissions.

4) A nightly job must import inventory and reindex search. What two job steps are typical? (Select two)
A. A script step to call import API for inventory list
B. Disable all caches for the duration
C. A system step to trigger search index rebuild
D. A replication immediately after

Answer: A, C
Explanation: A script/system step pair often imports data then rebuilds search indexes.

5) Which two directories are commonly used for job import files? (Select two)
A. /on/demand/tmp/
B. /impex/src/
C. /versioned/imports/
D. /impex/src/instance/

Answer: B, D
Explanation: impex is the import/export directory; instance or org-level subfolders are typical.

6) To process large catalogs efficiently, which two techniques help? (Select two)
A. Streamed CSV/XML parsing in scripts
B. Break imports into chunks and use delta updates
C. Increase log level to DEBUG globally
D. Run imports through ISML templates

Answer: A, B
Explanation: Streaming and delta/chunked imports scale better.

7) For OCAPI Data permissions, the “read_attributes” and “write_attributes” sections should include which kinds of fields? (Select one)
A. Only system attributes
B. Only custom attributes
C. Both system and custom attributes you intend to expose
D. No attributes; OCAPI infers them

Answer: C
Explanation: Explicitly list fields to read/write—principle of least privilege.

8) Which three are strong indicators an integration should be asynchronous? (Select three)
A. Non-blocking to storefront request path
B. Long-running processing or batch-oriented data
C. Requires immediate shopper feedback at checkout
D. Can be queued and retried independently

Answer: A, B, D
Explanation: Async improves UX and resilience when work is long-running or not needed immediately.

9) To mask sensitive tokens in logs from a service response, which approach is best? (Select one)
A. Disable logs
B. Use a response parser that removes/redacts sensitive fields before logging
C. Print full payloads but store logs only for one day
D. Rely on DEBUG-only logs

Answer: B
Explanation: Redact at parse/log time to prevent sensitive data leakage.

10) When building an OCAPI customization involving hooks, where is hook code implemented? (Select one)
A. In ocapi.json directly
B. In a cartridge implementing the documented hook scripts and registered in cartridge path
C. In Business Manager’s Log Settings
D. In Page Designer page types

Answer: B
Explanation: OCAPI hooks are implemented in cartridges on the server side.

11) A job fails intermittently due to a locked resource. What two steps improve robustness? (Select two)
A. Introduce retry with backoff in the job script
B. Switch job to run synchronously on storefront requests
C. Add job parameterization and pre-checks for locks
D. Increase code version

Answer: A, C
Explanation: Retries/backoff and pre-checks mitigate contention issues.

12) An external PIM pushes product updates every hour. What is the most efficient search indexing strategy? (Select one)
A. Full reindex every hour
B. Delta indexing after each import
C. No indexing; search auto-detects
D. Reindex once daily

Answer: B
Explanation: Delta reindexing is efficient for frequent updates.

Set 5: Performance, Caching, Best Practices, Localization
1) Which two caching layers are commonly used for storefront rendering in B2C Commerce? (Select two)
A. iscache directive at template level
B. CDN edge cache only
C. Application response cache (res.cachePeriod/varyBy)
D. Database row cache

Answer: A, C
Explanation: Platform supports template caching and response cache; CDN is external; DB row cache is not a storefront concept.

2) A template fragment must vary by currency and promotions. Which approach is best? (Select one)
A. No cache; always dynamic
B. iscache with vary-by-currency and a custom vary key for promo state
C. Cache globally for all users
D. Use OCAPI cache exclusively

Answer: B
Explanation: Use iscache with appropriate vary keys to maintain correctness.

3) Which two coding issues most often cause scalability problems? (Select two)
A. Duplicated service calls per request without caching
B. Excessive synchronous I/O inside the request thread
C. Moving logic to decorators
D. Using Logger at INFO for checkpoints

Answer: A, B
Explanation: Avoid redundant service calls and blocking I/O paths.

4) To localize UI strings, what are two best practices? (Select two)
A. Place strings in properties files under templates/resources
B. Hardcode English in ISML and translate later
C. Use Resource.msg/Resource.msgf helpers
D. Store strings in services.json

Answer: A, C
Explanation: Use properties and Resource helpers for localization.

5) A page still shows stale data after code deploy. Which two actions help? (Select two)
A. Clear application cache
B. Force re-index of search every time
C. Invalidate iscache entries if template cache was used
D. Change code version name

Answer: A, C
Explanation: Clear app cache and template cache as appropriate.

6) Which is a correct approach for logging performance metrics? (Select one)
A. Use Logger with a dedicated category, log timings, and analyze in BM logs
B. Print timings in templates to the page footer
C. Log all data at ERROR level
D. Rely only on Request Logs default

Answer: A
Explanation: Structured logging with categories and levels aids analysis.

7) To minimize controller complexity, where should most business logic live? (Select one)
A. Controllers only
B. Decorators, helpers, factories, and services
C. ISML templates
D. ocapi.json

Answer: B
Explanation: Keep controllers thin; move logic to reusable layers.

8) When adding a new language, which two areas are typically updated? (Select two)
A. templates/resources/*.properties for the new locale
B. Page Designer components JSON only
C. Static assets localized per locale where needed
D. dw.json locales

Answer: A, C
Explanation: Provide localized properties and assets for the new locale.

9) A site experiences timeouts calling an external API. Which three mitigations are best practice? (Select three)
A. Reduce timeouts to fail fast
B. Add caching of responses where feasible
C. Add retries with exponential backoff and circuit breakers
D. Increase the number of synchronous calls per page

Answer: A, B, C
Explanation: Fail fast, cache, and add resiliency patterns. Avoid multiplying calls.

10) A developer adds custom pricing within the PDP controller and skips the pricing hook. What is the issue? (Select one)
A. None; controller is the best place for pricing
B. Violates extensibility; use pricing hooks/decorators to centralize logic
C. Pricing must live in ISML
D. OCAPI enforces this automatically

Answer: B
Explanation: Centralize domain logic in hooks/decorators for reuse and consistency.

11) Which two strategies reduce template render time? (Select two)
A. Minimize logic in ISML; precompute in models
B. Use remote includes for every snippet
C. Cache static fragments with iscache
D. Render JSON then transform client-side

Answer: A, C
Explanation: Precompute data and cache static fragments to accelerate rendering.

12) When should you use remote includes over local includes? (Select one)
A. When the included content must execute in a separate pipeline and be independently cached
B. Always, because remote includes are faster
C. Only for JSON responses
D. Never; they are deprecated

Answer: A
Explanation: Remote includes are used for separate pipeline execution and caching behavior.

End of 5 Sets