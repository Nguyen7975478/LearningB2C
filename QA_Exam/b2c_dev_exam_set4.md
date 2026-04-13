# Salesforce Certified B2C Commerce Developer — Practice Questions (Set 4)
Total: 60 questions. Each question indicates the number of correct choices. An answer key with concise explanations is provided at the end.

Section S1: Setup, Code Versions, Cartridges, and Environments (12)
1) A developer uploads a new custom cartridge via WebDAV to the active code version, but controllers are not being resolved. What two steps are most likely missing? (Select two)
A. Adding the cartridge to the site’s cartridge path ahead of app_storefront_base
B. Rebuilding search indexes
C. Clearing application/template caches as needed
D. Assigning the cartridge to the Organization cartridge path only

2) Which statement about site code version configuration is accurate? (Select one)
A. All sites must share a single code version
B. Each site references a specific code version in its Settings independently
C. Only Organization settings control the code version
D. The code version is inferred from the cartridge path

3) Where should you place a new ISML template to override a template from app_storefront_base? (Select one)
A. In the same relative path under your higher-priority custom cartridge
B. In /impex/src/templates/
C. In ocapi.json
D. In Business Manager > SEO

4) What is the recommended cartridge order for standard SFRA customization? (Select one)
A. app_storefront_base first, then all custom cartridges
B. custom cartridges first, then app_storefront_base
C. Alphabetical order
D. app_storefront_base only

5) After switching a site to a new code version, templates show stale content. What is the most appropriate first action? (Select one)
A. Run a full reindex
B. Clear application cache and invalidate any relevant iscache fragments
C. Change the code version name again
D. Re-import catalogs

6) Which two items are set at the site level in Business Manager for a newly added site? (Select two)
A. Default currency and taxation type
B. Cartridge path
C. OCAPI credentials
D. Service credential passwords

7) A team needs a custom site preference that toggles a feature flag. What is the correct approach? (Select one)
A. Add a new property to ocapi.json
B. Add a custom site preference group and preference, then reference it in code
C. Add it to templates/resources/*.properties
D. Add a new setting in dw.json

8) Which two directories are used for code deployment and data import respectively? (Select two)
A. /versioned/cartridges/<code-version>/cartridges for code
B. /impex/src/ for data import
C. /static/default/ for controllers
D. /impex/exports/ for cartridge upload

9) A merchant requests two different cartridge paths for two locales on the same site. What is the correct guidance? (Select one)
A. Cartridge paths can vary per locale
B. Cartridge path is site-level; implement locale differences in code/templates
C. Cartridge path is global for the instance
D. Use ocapi.json per locale

10) What is the purpose of app_*.properties inside a cartridge? (Select one)
A. To configure route definitions
B. To define cartridge metadata such as id and version
C. To manage OCAPI access
D. To set default catalog IDs

11) How do Organization-level and Site-level cartridge paths interact? (Select one)
A. Only Organization-level applies
B. They are merged; Site-level ordering is applied after Organization-level
C. Site-level is ignored if Organization-level exists
D. They alternate per request

12) You observe that a newly uploaded cartridge is not visible under “Code Versions.” What is the likely cause? (Select one)
A. Uploaded to the wrong path (not under /versioned/cartridges/<code-version>/cartridges)
B. Missing Page Designer components
C. Missing ocapi.shop permissions
D. Not added to search refinements

Section S2: Business Manager, Catalog/Search, Content, Logging (12)
13) Where do you configure a new search refinement definition (facet)? (Select one)
A. Merchant Tools > Search > Search Refinements
B. Administration > Sites
C. Merchant Tools > SEO > Redirects
D. Merchant Tools > Products and Catalogs > Catalogs

14) Which two steps are required to make a product attribute searchable? (Select two)
A. Mark attribute as searchable in attribute definition
B. Add to ocapi.json read_attributes
C. Rebuild search indexes
D. Add the attribute to Page Designer

15) To display a new attribute on PDP, which two areas are typically involved? (Select two)
A. Extend product model via decorator/factory
B. Modify PDP ISML template to render the attribute
C. Create a new code version
D. Create a new OCAPI client

16) A merchandiser wants synonyms to map “hoodie” to “hooded sweatshirt” without mapping the reverse. Where is this configured and what pattern is used? (Select one)
A. Merchant Tools > SEO; redirect rule
B. Merchant Tools > Search > Dictionaries; one-way synonym
C. Merchant Tools > Search > Search Refinements; two-way synonym
D. Administration > Sites; locale setting

17) You must expose a custom object via OCAPI Data for an integration. Which two actions are required? (Select two)
A. Create/update ocapi.json with read/write permissions and attribute lists
B. Create client ID/secret and map to ocapi.json settings
C. Add the object to the cartridge path
D. Rebuild search indexes

18) Where are log categories and appenders configured? (Select one)
A. Business Manager > Administration > Operations > Logging
B. Business Manager > Search > Dictionaries
C. In dw.json
D. In ocapi.json

19) A merchandiser wants to assemble a landing page with reusable components. Which feature is most appropriate? (Select one)
A. Page Designer
B. Content Assets only
C. URL Rules
D. OCAPI Shop

20) Search results return fewer products after enabling a new locale. What two issues are typical? (Select two)
A. Missing localized values for searchable attributes
B. Failure to rebuild search indexes
C. Missing services.json
D. Misconfigured cartridge path

21) You added a new searchable and refinable attribute, but it doesn’t appear in the storefront facet menu. Which two steps might be missing? (Select two)
A. Assigning the attribute to a refinement menu
B. Rebuilding the index so values are available
C. Adding the attribute to ocapi.shop read_attributes
D. Creating a new site preference

22) What is the best practice for logging? (Select one)
A. Use Logger with dedicated category/file and appropriate levels (INFO/WARN/ERROR)
B. Use System.out.println for simplicity
C. Log everything at DEBUG in production
D. Avoid logs in production

23) Where is site import/export managed? (Select one)
A. Merchant Tools > Site Import & Export
B. Administration > Code Versions
C. Merchant Tools > SEO
D. Merchant Tools > Services

24) Which two Business Manager areas are primarily used by merchandisers vs. developers? (Select two)
A. Content and Page Designer (merchandisers)
B. Search and Dictionaries (merchandisers)
C. Services Framework (merchandisers)
D. Code Versions (merchandisers)

Section S3: Controllers, Templates, Forms, Hooks, Services, APIs (12)
25) A route returns JSON for a headless client. Which two are correct? (Select two)
A. Set Content-Type to application/json
B. Use res.json or write JSON string; avoid rendering ISML
C. Always reuse PDP ISML to ensure consistency
D. Disable HTTPS

26) Which middleware should be used around POST form handlers? (Select one)
A. csrfProtection.validateRequest (with generateToken in GET render)
B. cache.applyCache only
C. consentTracking.consent only
D. None; SFRA auto-adds CSRF

27) A new decorator adds computed fields to the product model. Where should this logic live? (Select one)
A. ISML with script blocks
B. Product decorators and/or factory
C. ocapi.json
D. Services configuration

28) You need to capture basket pricing adjustments without changing core controllers. What mechanism is intended? (Select one)
A. Page Designer
B. Documented hooks (e.g., pricing/tax calculation hooks)
C. ocapi.json read_attributes
D. Cartridge app.properties

29) A controller is doing blocking HTTP per product on a listing page. Which two improvements help? (Select two)
A. Use the Service Framework with timeouts and circuit breaker
B. Aggregate/batch calls or cache responses to avoid N+1 patterns
C. Move the calls into ISML
D. Use System.out.println for timing

30) In an ISML template, which directive allows separately cachable fragments? (Select one)
A. iscache
B. isinclude only
C. isif
D. isloop

31) A controller must render cached content that varies by locale and currency. What should be used? (Select one)
A. res.cachePeriod with varyBy keys or iscache vary attributes
B. Disable caching for correctness
C. Only CDN cache
D. Global cache without vary

32) A POST endpoint ingests JSON into a custom object. Which two precautions are mandatory? (Select two)
A. Validate input, enforce size limits, and reject malformed payloads
B. Add CSRF protection where relevant
C. Log full payloads at DEBUG for later inspection
D. Disable HTTPS for performance

33) A service responds with HTTP 200 but an application-level error. How should failure be detected? (Select one)
A. The 200 means success; return OK
B. Parse response body and check domain status codes/fields per contract
C. Rely exclusively on timeouts
D. Switch to SOAP

34) The Shop API response is personalized. Which two caching strategies are safe? (Select two)
A. No caching
B. Cache with vary keys including customer group, locale, currency
C. Cache globally for all users
D. CDN cache with no vary

35) Which pattern helps keep controllers thin and maintainable? (Select one)
A. Move complex rules to helpers/decorators/factories
B. Put heavy loops in ISML
C. Return JSON only
D. Avoid using services

36) When must you use remote includes over local includes? (Select one)
A. When the included content must execute in a separate pipeline with its own cache behavior
B. Always; they are faster
C. Never
D. Only for JSON routes

Section S4: OCAPI, Jobs, Integration, and Data Flows (12)
37) To expose baskets via OCAPI Shop, which two steps are required? (Select two)
A. ocapi.json Shop permissions for basket resources with allowed attributes
B. Create and map client credentials to that ocapi.json setting
C. Add the Shop resource in Page Designer
D. Add a new code version

38) A nightly job imports inventory and reindexes search. Which two steps are typical? (Select two)
A. Script step to perform inventory import
B. System step to trigger delta or full indexing
C. Disable CSRF
D. Repackage cartridges

39) Which import folders are typically used for inbound data files? (Select two)
A. /impex/src/
B. /impex/src/instance/
C. /versioned/cartridges/
D. /on-demand/tmp/

40) A job intermittently fails due to file locks on import. What two mitigations help? (Select two)
A. Add retry with exponential backoff
B. Coordinate schedules/locks to avoid overlap
C. Disable logging
D. Run the job from controllers

41) An integration requires least-privilege OCAPI Data access to orders. Which two are correct? (Select two)
A. Restrict read_attributes to required fields only
B. Use a shared client for all partners
C. Issue dedicated credentials per integration
D. Expose all fields for convenience

42) A service credential must be rotated with zero downtime. What two steps help? (Select two)
A. Introduce a new credential/profile, cut over in config, then remove old
B. Change password in code constants
C. Support overlapping key validity if upstream allows
D. Stop traffic during rotation

43) Which two steps improve robustness of a synchronous integration? (Select two)
A. Configure short timeouts and a circuit breaker
B. Implement retries with exponential backoff for transient failures
C. Always log entire request/response bodies
D. Remove caching

44) A PIM sends product deltas hourly. What indexing policy is most efficient? (Select one)
A. Delta reindex after each import
B. Full reindex every hour
C. Reindex weekly
D. No reindex needed

45) A partner needs to call a Data API that writes to a custom object. What two items are mandatory? (Select two)
A. ocapi.json write_permissions with write_attributes listed
B. Client credentials with that ocapi.json setting
C. Change code version
D. Add to search refinement menus

46) A job must run two steps that update the same objects and occasionally collide. What should you implement? (Select one)
A. Cache busting
B. Locking/serialization or mutually exclusive windows
C. More logging
D. A remote include

47) An upstream service returns sensitive tokens. How do you prevent leakage to logs? (Select one)
A. Redact tokens in the Service parser before logging; avoid logging bodies unless masked
B. Rely on DEBUG logs only
C. Disable all logs globally
D. Print to System.out

48) A shop API endpoint needs to be personalized by pricelist and locale. Which is safest? (Select one)
A. Cache globally
B. Add vary-by customer group/pricelist and locale or disable cache
C. CDN cache with no vary
D. Only Application cache

Section S5: Performance, Caching, Troubleshooting, Localization (12)
49) Which two techniques reduce controller TTFB for a PDP? (Select two)
A. Precompute heavy fields in decorators; avoid blocking calls per request
B. Use iscache for static fragments and proper vary keys
C. Always disable caching
D. Render via OCAPI only

50) The profiler shows 35% of time is spent in a service call per product on PLP tiles. Which two mitigations help most? (Select two)
A. Batch/aggregate calls and cache responses
B. Move computation offline via jobs; fetch precomputed attributes
C. Increase logging to TRACE
D. Render JSON in ISML

51) You see stale promotion details in a remote include. What is the likely cause? (Select one)
A. Missing vary key for promo/basket state on the include
B. Missing ocapi.json read permissions
C. Missing controller import
D. Incorrect code version

52) A large JSON export endpoint exhausts memory. Which is the correct approach? (Select one)
A. Stream JSON chunks to response; avoid building huge objects in memory
B. Convert to ISML then to JSON
C. Disable HTTPS
D. Use console.log to flush buffers

53) Which two cause cache correctness issues in localized sites? (Select two)
A. Missing vary-by-locale/currency
B. Using global cache with no vary
C. Using decorators
D. Using Logger at INFO

54) A new locale was added, but many UI strings show in English. Which two are typical fixes? (Select two)
A. Add templates/resources/*.properties files for the new locale
B. Use Resource.msg/Resource.msgf to fetch localized strings
C. Add the locale to ocapi.json
D. Change the code version

55) A controller experiences timeouts downstream. Which three resiliency steps are best practice? (Select three)
A. Fail fast (short timeouts)
B. Retries with exponential backoff and circuit breaker
C. Graceful degradation (cached/placeholder content)
D. Increase synchronous calls

56) After release, PDP render time increased by 250ms. Which three diagnostics help? (Select three)
A. Compare profiler traces for the route before vs. after
B. Add targeted timing logs to isolate hotspots
C. Diff changes in services/decorators/hooks
D. Clear all caches permanently

57) Which two strategies lower ISML template CPU time? (Select two)
A. Move complex logic to helpers/decorators; pass view-ready data
B. Cache static fragments with iscache
C. Add blocking HTTP calls in template
D. Add loops with heavy computation in ISML

58) A Page Designer component shows incorrect currency on cache hits. What is the fix? (Select one)
A. Add vary-by-currency on the cached fragment
B. Mark component as uncacheable always
C. Use ocapi.json
D. Switch to a different code version

59) You must ensure that duplicate POST submissions don’t create duplicate orders. Which two mitigations help? (Select two)
A. Idempotency keys with server-side deduplication
B. Client-side submit button disable to prevent double-click
C. Switch POST to GET
D. Disable CSRF

60) A catalog import job and a delta indexing job conflict occasionally. What’s the best solution? (Select one)
A. Coordinate schedules with locking and order; add retries/backoff
B. Disable indexing
C. Increase log verbosity
D. Remove cache

Answer Key with Explanations
1) A, C — Add cartridge to path; clear caches for resolution
2) B — Site references code version independently
3) A — Override by matching relative path/name in a higher-priority custom cartridge
4) B — Custom first, base last for overrides
5) B — Clear app/template caches after switching code versions
6) A, B — Currency/taxation and cartridge path are site-level
7) B — Use custom site preference and read in code
8) A, B — /versioned/... for code; /impex/src for import
9) B — Path is site-scoped; handle locale in code/templates
10) B — Cartridge metadata file (id/version/etc.)
11) B — Merged; site-level ordering applied after org-level
12) A — Uploaded to wrong path
13) A — Search > Search Refinements
14) A, C — Mark searchable and reindex
15) A, B — Extend model and update template
16) B — Dictionaries; one-way synonym
17) A, B — ocapi.json + client credentials
18) A — Configure logs in BM
19) A — Page Designer enables marketer-built pages
20) A, B — Missing localized values and indexing issues
21) A, B — Assign to menu and reindex
22) A — Use Logger categories and levels appropriately
23) A — Site Import & Export
24) A, B — Content/PD and Search are merch areas
25) A, B — Set JSON content type; respond with JSON
26) A — CSRF protection for POSTs
27) B — Decorators/factory hold computed model logic
28) B — Use hooks to intercept calculations
29) A, B — Use Service Framework; batch/cache calls
30) A — iscache caches fragments
31) A — Response cache or iscache with proper vary
32) A, B — Validate, size-limit, CSRF where relevant
33) B — Parse body for domain success/failure
34) A, B — No cache or cache with vary for personalization
35) A — Keep controllers thin; use helpers/decorators
36) A — Remote includes have separate pipelines/caches
37) A, B — ocapi.json Shop + client credentials
38) A, B — Import via script; trigger indexing
39) A, B — impex src paths for inbound
40) A, B — Retries and schedule/lock coordination
41) A, C — Restrict fields; dedicated creds
42) A, C — Blue/green/overlap key rotation
43) A, B — Short timeouts + CB; retry transient failures
44) A — Delta reindex after import
45) A, B — ocapi.json write + credentials
46) B — Lock/serialize conflicting updates
47) A — Redact/mask; avoid logging bodies
48) B — Vary keys for personalization or disable cache
49) A, B — Precompute and cache static parts
50) A, B — Batch/cache or precompute in jobs
51) A — Add vary for promo/basket on include
52) A — Stream JSON
53) A, B — Missing vary or global cache causes issues
54) A, B — Properties + Resource helpers
55) A, B, C — Fail fast, retry with CB, degrade gracefully
56) A, B, C — Profiler, timing logs, diff changed layers
57) A, B — Precompute and cache static fragments
58) A — Vary by currency to partition cache
59) A, B — Idempotency and client disable
60) A — Coordinate schedules and locking; add backoff