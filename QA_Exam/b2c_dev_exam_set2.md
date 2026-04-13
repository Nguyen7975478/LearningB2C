# Salesforce Certified B2C Commerce Developer — Practice Questions (Set 2)
Total: 60 questions. Each question specifies the number of correct options to select. An answer key with concise explanations follows each section.

Set A: B2C Commerce Setup and SFRA Architecture (12)
1) Which statement best describes the relationship between code versions and sites? (Select one)
A. Each site can only run the “active” global code version
B. Each site references a code version independently in its Settings
C. Each site must share the same code version to enable replication
D. Sites ignore code versions; cartridge path alone determines behavior

2) Which directory is used by WebDAV to upload a cartridge for the active code version? (Select one)
A. /versioned/cartridges/<code-version>/cartridges
B. /impex/src/
C. /cartridge/static/default/
D. /dw/core/cartridges/

3) In SFRA, where are HTTP routes for controllers typically defined? (Select one)
A. In ISML using isroute
B. In server-side JavaScript files using server.get/server.post
C. In Business Manager under URL Rules
D. In ocapi.json under shop.routes

4) When extending app_storefront_base with custom functionality, which path ordering is recommended? (Select one)
A. app_storefront_base first, then custom cartridges
B. Custom cartridges first, then app_storefront_base
C. Alphabetical ordering of all cartridges
D. System cartridges, then app_storefront_base, then custom, then base again

5) What is the purpose of “decorators” in SFRA? (Select one)
A. To add CSS classes to ISML
B. To add properties/behavior to models without modifying base implementations
C. To convert JSON to ISML
D. To bundle cartridges for deployment

6) What is the primary benefit of the model-factory pattern in SFRA? (Select one)
A. Speeds up CDN invalidation
B. Centralizes object construction and applies decorators consistently
C. Removes the need for ISML templates
D. Eliminates the need for caching

7) Which two files commonly appear in an SFRA controller module? (Select two)
A. controller.js using server middleware
B. .isml template for rendering
C. ocapi.json with controller routes
D. services.json with route priorities

8) What is the impact of placing a custom cartridge after app_storefront_base in the site path? (Select one)
A. Custom overrides take precedence
B. app_storefront_base overrides custom definitions
C. Both cartridges are ignored
D. Only ISML templates from custom are used

9) Which action is required after uploading new controllers to the code version? (Select one)
A. Restart the JVM
B. Add/ensure cartridge path includes the cartridge and clear caches if necessary
C. Rebuild the search index
D. Run a job to recompile scripts

10) Which statement best describes SFRA’s separation of concerns? (Select one)
A. Controllers hold business logic; templates hold minimal display logic; decorators/models add computed data
B. All logic should live in ISML for speed
C. Decorators are only for CSS
D. Templates must directly query services

11) How do you verify that a new controller route is resolvable? (Select one)
A. Check Page Designer
B. Trigger replication
C. Access the route URL in the storefront and validate the response
D. Review ocapi.json

12) What is the effect of clearing application cache in Business Manager? (Select one)
A. Removes all code from /versioned
B. Forces template and response caches to refresh so changes appear
C. Deletes log files
D. Resets site preferences

Set B: Business Manager, Product/Search, Content, and Data (12)
13) Where are product search synonyms configured? (Select one)
A. Merchant Tools > Search > Dictionaries
B. Merchant Tools > Products and Catalogs > Catalogs
C. Administration > Code Versions
D. Merchant Tools > SEO

14) To make a custom product attribute searchable, which two actions are required? (Select two)
A. Mark the attribute as searchable in attribute definitions
B. Add the attribute to ocapi.json
C. Rebuild the search index after change
D. Restart the application server

15) Where do you configure payment processors and methods for a site? (Select one)
A. Administration > Global Preferences > Payments
B. Merchant Tools > Ordering > Payment Methods/Processors
C. Merchant Tools > Services > Payment
D. Merchant Tools > Site Preferences > Payment Settings

16) Which tool is used to import a catalog XML into a sandbox? (Select one)
A. Merchant Tools > Site Import & Export
B. Administration > Code Versions
C. OCAPI Shop
D. URL Rules

17) To display a new attribute on PDP, where might developers typically add code? (Select two)
A. Product model decorators/factory
B. PDP ISML templates
C. Services Framework credentials
D. Log appenders

18) Which is the correct location to configure logs and custom categories? (Select one)
A. Merchant Tools > Search
B. Business Manager > Administration > Operations > Logs Settings
C. ocapi.json
D. services.json

19) A merchandiser needs to curate content for the homepage. Which two features are most relevant? (Select two)
A. Content Assets and Folders
B. Page Designer pages and components
C. OCAPI Data permissions
D. Service Profiles

20) A data import fails with “invalid XML structure.” First step? (Select one)
A. Retry import
B. Validate XML against the expected schema and correct the file
C. Reindex search
D. Switch code version

21) To expose a custom object externally via OCAPI Data, which two are needed? (Select two)
A. ocapi.json read/write attributes for the object
B. Client ID/secret mapped to the OCAPI settings
C. A new code version
D. Page Designer page type

22) What is a common sign that you should introduce a custom object type? (Select one)
A. To store transient session data
B. To persist domain data not fitting existing system objects (e.g., external mappings)
C. To hold image binaries rendered by templates
D. To replace product attributes

23) Where do you configure search refinements (facets)? (Select one)
A. Merchant Tools > Search > Search Refinements
B. Merchant Tools > SEO > Redirects
C. Administration > Sites
D. Merchant Tools > Content > Slots

24) After creating a new searchable attribute, the storefront still doesn’t return results. Which two steps are likely missing? (Select two)
A. Rebuild the search index
B. Add the attribute to ReadAttributes in ocapi.json
C. Ensure the attribute is assigned to the product type and populated
D. Restart the sandbox

Set C: Controllers, ISML, Forms, Hooks, and Logging (12)
25) What middleware should wrap POST form routes to protect against CSRF? (Select one)
A. server.middleware.https only
B. csrfProtection.validateRequest with generateToken pattern
C. cache.applyCache
D. consentTracking.consent

26) How do you send data from a controller to a template? (Select one)
A. res.json(data)
B. res.render('path/to/template', dataObject)
C. URLUtils.redirect(data)
D. Using properties files

27) A controller must return JSON. Which two steps are correct? (Select two)
A. Set Content-Type to application/json
B. Use res.json or write JSON string to response
C. Render an ISML template that outputs JSON
D. Enable “JSON Mode” in site preferences

28) Where should complex pricing logic be implemented for maintainability? (Select one)
A. Inside the PDP controller directly
B. Within pricing-related hooks and/or decorators used by the model layer
C. In ISML templates
D. In ocapi.json

29) Which ISML tag enables a separately cachable component rendering? (Select one)
A. isinclude
B. iscomponent
C. isdecorate
D. isif

30) Which three artifacts are typical when implementing a custom form? (Select three)
A. forms XML definition for fields/validation
B. server.post route with CSRF validation
C. Client-side only validation; server validation optional
D. Form binding/validation via SFCC Form API

31) Which hook type allows you to modify basket or price calculation without editing controllers? (Select one)
A. app_*.properties
B. Service profile parser
C. Documented pricing/tax calculation hook extension points
D. Request Logs

32) Best practice for logging messages from controllers/models? (Select one)
A. System.out.println
B. dw.system.Logger.getLogger(category, file).info/debug/error
C. console.log
D. Write a file under /versioned/logs

33) ISML localization uses which mechanism? (Select one)
A. services.json
B. templates/resources/*.properties per locale
C. ocapi.json
D. controller-localization.json

34) A controller uses multiple synchronous service calls per request leading to timeouts. Which two fixes help? (Select two)
A. Cache service responses prudently
B. Use Service Framework with timeouts/retries/circuit breakers
C. Log all payloads at DEBUG always
D. Move logic to ISML

35) A page fragment must vary by locale and currency. What is recommended? (Select one)
A. Disable cache
B. Use iscache with vary keys or res.cachePeriod with varyBy parameters
C. Only CDN cache
D. Rebuild search per request

36) After deploying a new template, changes don’t appear. What are two likely remedies? (Select two)
A. Clear application cache
B. Rebuild all indexes
C. Invalidate template cache (iscache)
D. Change code version name

Set D: Services, OCAPI, Integrations, Jobs (12)
37) Which three Service Framework settings are essential for resilient integrations? (Select three)
A. Connection/socket timeouts
B. Retry/circuit breaker strategy
C. Full payload logging at all times
D. Response parser and optional caching

38) Where do you securely store API credentials for services? (Select one)
A. In Business Manager service credentials
B. In server-side templates
C. In dw.json
D. In cartridge scripts

39) To allow access to baskets via OCAPI Shop API, which two are required? (Select two)
A. ocapi.json Shop permissions for baskets
B. Client credential configured for OCAPI
C. A new cartridge path entry
D. Page Designer registration

40) A nightly job must import inventory and refresh search. Which two steps are typical? (Select two)
A. Script step to import inventory
B. Disable cache globally
C. System step to trigger delta search index
D. Change site ID

41) Which WebDAV directories are typically used for import sources? (Select two)
A. /impex/src/
B. /impex/src/instance/
C. /versioned/cartridges/
D. /services/ocapi/

42) A job intermittently fails due to locked resources. Which two mitigations help? (Select two)
A. Retry with exponential backoff
B. Execute job inside storefront requests
C. Pre-check locks and conditionally skip/wait
D. Run ISML to free locks

43) When should an integration be asynchronous? (Select two)
A. When long-running and not required for immediate shopper response
B. When work can be queued and retried without blocking the request path
C. When needed to show real-time prices at checkout
D. Never; synchronous is always better

44) To prevent sensitive data from appearing in logs, what is recommended? (Select one)
A. Disable logs entirely
B. Redact/mask sensitive fields in response parser before logging
C. Log only at ERROR
D. Print to console instead of Logger

45) OCAPI customization logic (hooks) lives where? (Select one)
A. ocapi.json
B. A cartridge implementing documented hook scripts, registered in path
C. Page Designer component JSON
D. Log settings

46) A PIM pushes product deltas hourly. Efficient indexing strategy? (Select one)
A. Full reindex hourly
B. Delta reindex after each import
C. No indexing
D. Weekly reindex

47) A service endpoint begins timing out. Which three actions improve resiliency? (Select three)
A. Reduce timeouts to fail fast
B. Add retries with backoff and circuit breakers
C. Cache responses where feasible
D. Increase synchronous calls per page

48) Which two job step types are common in B2C Commerce? (Select two)
A. Script step (custom JS)
B. System step (built-in function)
C. SQL step
D. ISML step

Set E: Performance, Caching, Security, and Best Practices (12)
49) Which two platform-level caches are commonly used for storefront performance? (Select two)
A. iscache in templates
B. Response cache (res.cachePeriod/varyBy)
C. Database cache per table
D. CDN-only caching

50) Which two patterns reduce controller complexity? (Select two)
A. Move domain logic to helpers/decorators/factories
B. Inline business logic in ISML
C. Keep controllers thin; leverage services for integrations
D. Put everything in a single controller file

51) For localization of UI text, which two practices are correct? (Select two)
A. Use templates/resources/*.properties by locale
B. Hardcode English and translate later
C. Use Resource.msg/Resource.msgf to fetch strings
D. Store localized strings in ocapi.json

52) Which two anti-patterns hurt scalability? (Select two)
A. Repeated synchronous service calls without caching
B. Excessive logic in templates
C. Using decorators for computed properties
D. Returning JSON for APIs

53) A template snippet is static and identical for all users. Best caching approach? (Select one)
A. No caching
B. iscache without vary keys
C. res.cachePeriod(0)
D. Only CDN cache

54) Which two steps help diagnose a slow route? (Select two)
A. Enable targeted log categories and inspect request logs
B. Use BM profiler to measure controller time
C. Rebuild search indexes
D. Disable all caches permanently

55) Which practice best protects against CSRF on forms? (Select one)
A. Use GET for all forms
B. Use csrfProtection middleware on POST, generate and validate tokens
C. Rely on HTTPS alone
D. Put token in cookies only

56) Where should secrets and API keys live? (Select one)
A. Business Manager service credentials
B. In cartridge constants.js
C. In templates/resources/*.properties
D. In code version name

57) After deployment, part of the site still shows stale content. Which two actions are appropriate? (Select two)
A. Clear application cache
B. Invalidate iscache entries for affected templates
C. Recreate code version
D. Switch to a different sandbox

58) When should remote includes be preferred over local includes? (Select one)
A. When the included content must run in a separate pipeline with its own cache behavior
B. Always; remote includes are faster for everything
C. Only for JSON API responses
D. Never use remote includes

59) Which two strategies reduce rendering time? (Select two)
A. Precompute view data in models/decorators instead of templates
B. Cache static fragments with iscache
C. Put heavy loops in ISML to keep controllers thin
D. Avoid all caching for correctness

60) Which log-level policy is recommended for production? (Select one)
A. Log all payloads at DEBUG
B. Use INFO for routine checkpoints, WARN/ERROR for issues, DEBUG only for targeted troubleshooting
C. Only use ERROR logs
D. Use TRACE always for maximum detail

Answer Key and Explanations
1) B — Sites independently reference a code version in Settings.
2) A — Code deploys under /versioned/cartridges/<code-version>/cartridges.
3) B — Routes are registered in server-side JS via server.get/post.
4) B — Custom first, base last to allow overrides.
5) B — Decorators extend models cleanly.
6) B — Factories centralize construction and apply decorators.
7) A, B — Controllers and ISML are paired; ocapi/services files aren’t for routes.
8) B — Base after custom means base can override later-resolved artifacts.
9) B — Ensure cartridge path and clear caches when needed.
10) A — Controllers thin; business logic in models/decorators; templates minimal.
11) C — Call the route directly to validate.
12) B — Cache clear refreshes rendered output.
13) A — Synonyms live in Dictionaries.
14) A, C — Mark searchable and reindex.
15) B — Payment config under Ordering.
16) A — Site Import & Export handles data loads.
17) A, B — Extend model and update templates to render.
18) B — Logs configured in BM log settings.
19) A, B — Content Assets/PD are merch tools.
20) B — Validate the input XML against schema.
21) A, B — OCAPI permissions and client credentials.
22) B — Use custom objects for domain data that doesn’t fit system objects.
23) A — Refinements (facets) configured under Search.
24) A, C — Reindex; ensure data is populated and assigned.
25) B — CSRF token generate/validate for POSTs.
26) B — res.render(template, data).
27) A, B — Set JSON content-type and respond with JSON.
28) B — Centralize in hooks/decorators for reuse.
29) B — iscomponent supports separate caching units.
30) A, B, D — Form XML, CSRF-protected POST, and binding/validation.
31) C — Use pricing/tax calculation hooks.
32) B — Use platform Logger with categories.
33) B — Properties files per locale.
34) A, B — Cache responses and add resiliency via Service Framework.
35) B — Use iscache/res.cachePeriod with vary keys.
36) A, C — Clear app cache or invalidate template cache.
37) A, B, D — Timeouts, resiliency, and parsing/caching.
38) A — Store secrets in BM service credentials.
39) A, B — OCAPI permissions and client config.
40) A, C — Import via script; delta search step.
41) A, B — /impex/src[/instance] are import folders.
42) A, C — Retries/backoff and pre-checks mitigate locks.
43) A, B — Async when not needed synchronously; allows queuing/retry.
44) B — Redact before logging.
45) B — Implement OCAPI hooks in a cartridge.
46) B — Delta indexing for frequent updates.
47) A, B, C — Fail fast, add retries/circuit break, and cache.
48) A, B — Script and System steps are standard.
49) A, B — iscache and response cache.
50) A, C — Keep controllers thin; push logic down; use services.
51) A, C — Properties + Resource helpers.
52) A, B — Repeated sync calls and heavy template logic are anti-patterns.
53) B — iscache (no vary) for static identical snippets.
54) A, B — Logs and profiler reveal hotspots.
55) B — CSRF middleware + tokens.
56) A — Store secrets in BM, not code.
57) A, B — Clear app/template caches.
58) A — Remote includes provide separate pipelines and cache behavior.
59) A, B — Precompute and cache static parts.
60) B — Use INFO for normal ops; escalate when needed; DEBUG sparingly.

End of File