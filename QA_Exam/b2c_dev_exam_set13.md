# Salesforce Certified B2C Commerce Developer — Practice Questions (Set 13)
Total: 60 questions, standard difficulty. Each question indicates how many answers to select. An answer key with concise explanations is at the end.

Section A: Setup, Code Versions, Cartridges (12)
1) A cartridge was uploaded to the correct code version, but custom routes still return 404. What’s the most likely root cause? (Select one)
A. Synonyms not configured
B. Cartridge missing from the Site’s cartridge path or ordered after app_storefront_base
C. Missing Page Designer template
D. Wrong log category

2) What is the correct directory to upload code for the active code version? (Select one)
A. /impex/src/
B. /versioned/cartridges/<code-version>/cartridges
C. /static/default/
D. /impex/exports/

3) An override template is ignored by the storefront. Which two issues are common? (Select two)
A. The override file path/name doesn’t match the base template
B. The custom cartridge appears after app_storefront_base
C. The override wasn’t added to ocapi.json
D. The code version label doesn’t equal the site ID

4) Which statement about code versions is accurate? (Select one)
A. A single global code version controls all sites
B. Each site references a specific code version in its Settings
C. Code versions are defined only in dw.json
D. Code version is inferred from the cartridge path

5) After changing the site’s referenced code version, you still see old templates. Which two actions are recommended first? (Select two)
A. Clear application cache
B. Invalidate relevant template caches (iscache)
C. Rebuild full search index nightly
D. Rename the cartridge root folder

6) Why does cartridge order matter? (Select one)
A. It toggles CSRF on/off
B. Left-to-right precedence decides which controller/template/script resolves
C. It sets OCAPI Data permissions
D. It controls profiler availability

7) Where is the active code version set? (Select one)
A. BM > Administration > Site Development > Code Versions
B. BM > Merchant Tools > Search
C. BM > SEO
D. BM > Content > Assets

8) What does dw.json define? (Select one)
A. OCAPI Shop permissions
B. IDE/WebDAV connection and target code version
C. Synonym lists
D. Page Designer component mappings

9) The business asks for different cartridge paths per locale. Correct guidance is: (Select one)
A. Supported per locale
B. Not supported; one site-level path; handle locale in code/templates
C. Use ocapi.json per locale
D. Use services.json per locale

10) Which file holds cartridge metadata such as id/description? (Select one)
A. templates/resources/*.properties
B. app_*.properties
C. ocapi.json
D. services.json

11) How to enforce HTTPS on specific routes? (Select one)
A. Add server.middleware.https on those routes
B. Configure ocapi.json
C. Update Page Designer policies
D. Change code version

12) A cartridge is uploaded but doesn’t appear in the site-path picker. Most likely why? (Select one)
A. templates/resources missing
B. Not a valid cartridge structure (missing cartridge/ folder)
C. Missing cspTrustedSite entry
D. Wrong locale

Section B: Business Manager, Search, Content, Logging (12)
13) Where do you import catalogs/inventory files? (Select one)
A. BM > Merchant Tools > Site Import & Export
B. BM > SEO
C. BM > Code Versions
D. BM > Services

14) To make a new attribute searchable, which two steps are necessary? (Select two)
A. Set the attribute as searchable
B. Add attribute to Page Designer
C. Rebuild the search index
D. Add attribute to ocapi.json write_attributes

15) Where are search refinements (facets) configured? (Select one)
A. Merchant Tools > Search > Search Refinements
B. Merchant Tools > SEO
C. Administration > Sites
D. Content > Assets

16) A one-way synonym “joggers → sweatpants” is needed. Where do you set it? (Select one)
A. SEO Redirects
B. Search > Dictionaries (one-way)
C. Search Refinements
D. Site Preferences

17) To display a new PDP field, which two layers are updated? (Select two)
A. Product model decorators/factory to expose value
B. PDP ISML template to render it
C. ocapi.json
D. services.json

18) Where do you configure log categories and appenders? (Select one)
A. BM > Administration > Operations > Logging
B. ocapi.json
C. services.json
D. dw.json

19) A marketer wants to build a landing page using reusable pieces. Which tool fits? (Select one)
A. Page Designer
B. OCAPI Shop
C. Site Preferences
D. URL Rules

20) After enabling another locale, search returns fewer results. Likely causes? (Select two)
A. Missing localized attribute values
B. Forgot to reindex
C. Wrong synonyms list
D. Code version not active

21) To expose a custom object via Data API, which two actions are required? (Select two)
A. Configure ocapi.json with read/write and attribute lists
B. Create and map client credentials
C. Create a new cartridge
D. Rebuild search indexes

22) Production logging best practice is: (Select one)
A. Logger categories at INFO/WARN/ERROR; DEBUG used sparingly
B. System.out.println only
C. Everything at DEBUG
D. Disable logging in prod

23) Where do you configure default currency/taxation? (Select one)
A. Administration > Sites > Manage Sites > [Site] > Settings
B. Merchant Tools > SEO
C. Merchant Tools > Services
D. Code Versions

24) To update availability label text, which two areas are typical? (Select two)
A. templates/resources/*.properties
B. ISML templates where displayed
C. ocapi.json
D. logs

Section C: Controllers, ISML, Forms, Hooks, Services (12)
25) Maintainable controller design recommends: (Select one)
A. Thin controllers; business logic in helpers/decorators/factories
B. Place business logic in ISML for visibility
C. Use controllers exclusively for all logic
D. Avoid services entirely

26) Which directive enables fragment caching? (Select one)
A. iscache
B. isif
C. isloop
D. isdecorate

27) Proper CSRF handling requires: (Select one)
A. Generate token on GET; validate on POST (csrfProtection)
B. HTTPS alone is sufficient
C. Not required for SFRA
D. Site preference toggle only

28) For a JSON response, which two are correct? (Select two)
A. Set response Content-Type to application/json
B. Use res.json or write JSON
C. Render ISML first
D. Disable caching globally

29) To modify pricing without editing core controllers, use: (Select one)
A. Pricing/tax hook extension points
B. Page Designer
C. URL Rules
D. Site preference only

30) A list page does a synchronous per-item HTTP call. Which two remedies help? (Select two)
A. Use Service Framework with timeouts and circuit breaker
B. Batch/cache to avoid N+1
C. Move calls into ISML
D. System.out.println timers

31) Localize UI strings using: (Select two)
A. templates/resources/*.properties
B. Resource.msg/Resource.msgf
C. ocapi.json
D. services.json

32) A remote include shows stale promo content. What’s the best fix? (Select one)
A. Add vary keys for promo/basket/customer or disable the include cache
B. Disable all caching
C. Change code version
D. Add TRACE logs

33) For a personalized Shop API, safe caching is: (Select one)
A. No cache or cache with vary (customer group/locale/currency)
B. Global cache
C. CDN cache only
D. Response cache only

34) A service returns HTTP 200 but an error object in body. What should you do? (Select one)
A. Treat as success
B. Parse domain-level status; handle error case
C. Only rely on timeouts
D. Retry unbounded

35) When collecting PII via forms, which two are correct? (Select two)
A. Minimize/encrypt sensitive fields where possible
B. Restrict OCAPI Data permissions by least privilege
C. Log raw PII at DEBUG for support
D. Use GET instead of POST

36) A controller must stream a large CSV file. Best approach: (Select one)
A. Stream incrementally with headers
B. Build all rows in memory first
C. Render via ISML
D. Print to System.out

Section D: OCAPI, Jobs, Integrations, Data (12)
37) To allow baskets via OCAPI Shop, which two are needed? (Select two)
A. ocapi.json Shop permissions with allowed attributes
B. Client credentials mapped to that setting
C. A new code version
D. A PD component

38) A job imports inventory then updates search. Which two steps are typical? (Select two)
A. Script step: import inventory
B. System step: delta/full indexing
C. Disable all logs
D. Restart the sandbox

39) Common inbound file folders: (Select two)
A. /impex/src/
B. /impex/src/instance/
C. /versioned/cartridges/
D. /static/default/

40) Two jobs sometimes collide on same records. Which two mitigations help? (Select two)
A. Retry with exponential backoff
B. Coordinate schedules and locks (serialize)
C. Add TRACE logs only
D. Run imports from controllers

41) Least-privilege Data API for orders should: (Select two)
A. Limit read_attributes to required fields
B. Use dedicated client credentials per integration
C. Share one global client across partners
D. Expose all attributes for simplicity

42) Rotate a service credential without downtime by: (Select two)
A. Adding a new credential/profile and cutting over
B. Hardcoding secrets in code
C. Supporting overlapping keys if allowed
D. Stopping traffic

43) Robust synchronous integration typically includes: (Select two)
A. Short timeouts and circuit breaker
B. Retries with backoff for transient errors
C. Always log full payloads
D. Avoid any caching

44) Frequent product deltas should use: (Select one)
A. Delta reindex after each import
B. Full reindex hourly
C. Weekly reindex
D. No reindex

45) To write to a custom object via Data API, you need: (Select two)
A. ocapi.json write with write_attributes
B. Client credentials mapped
C. A new code version
D. Search refinements

46) Two job steps update the same object set. Best approach is: (Select one)
A. Lock/serialize or schedule exclusive windows
B. Disable logs
C. Use remote include
D. Rely on global cache

47) Prevent sensitive token leakage by: (Select one)
A. Redacting/masking tokens in parser; avoid logging bodies unless masked
B. Printing to System.out
C. Logging everything at DEBUG
D. Disabling services

48) Shop API varies by price group and locale. Safe caching: (Select one)
A. No cache or cache with appropriate vary keys
B. Global cache only
C. CDN no-vary
D. Response cache blindly

Section E: Performance, Caching, Troubleshooting (12)
49) Reduce PDP TTFB by: (Select two)
A. Precompute heavy fields in decorators
B. Cache static fragments (iscache) with relevant vary keys
C. Disable all cache
D. Force OCAPI on all pages

50) Profiler shows heavy per-tile service calls. Which two improvements help most? (Select two)
A. Batch/cache calls
B. Precompute via jobs and decorate from storage
C. Add TRACE logs globally
D. Use remote includes per tile

51) Stale content persists after deploy. Which two actions help? (Select two)
A. Clear application cache
B. Invalidate iscache fragments
C. Rebuild search every request
D. Change code version label

52) A large JSON export OOMs. Correct remediation: (Select one)
A. Stream chunks to response
B. Build JSON fully in memory
C. Render via ISML
D. Disable HTTPS

53) Cache correctness issues are often due to: (Select two)
A. Missing vary-by-locale/currency
B. Using global cache with no vary
C. Using decorators
D. Using properties bundles

54) New locale shows English strings. Which fixes apply? (Select two)
A. Add locale-specific templates/resources/*.properties
B. Use Resource.msg/Resource.msgf
C. Update ocapi.json
D. Switch code versions

55) A route times out downstream. Best practices include: (Select three)
A. Short timeouts (fail fast)
B. Retries with backoff
C. Circuit breaker
D. Increase synchronous calls

56) After release, PDP slower by ~200ms. Which three diagnostics help? (Select three)
A. Compare profiler traces before vs after
B. Add targeted timing logs
C. Diff changes in services/decorators/hooks
D. Disable logs permanently

57) Reduce ISML CPU by: (Select two)
A. Move logic to helpers/decorators
B. Cache static fragments with iscache
C. Add HTTP calls in templates
D. Use heavy loops in ISML

58) A PD component shows wrong currency on cache hits. What should you do? (Select one)
A. Add vary-by-currency on that cached fragment
B. Use ocapi.json
C. Disable CSRF
D. Rebuild catalog

59) Prevent duplicate POST submissions: (Select two)
A. Idempotency keys and server-side dedupe
B. Disable submit button after first click
C. Use GET
D. Disable CSRF

60) Catalog import and delta reindex overlap and fail. What’s the remedy? (Select one)
A. Coordinate schedules, lock shared resources, and add retries/backoff
B. Disable indexing
C. Add DEBUG logs
D. Change code version

Answer Key and Explanations
1) B — Path inclusion/ordering controls controller resolution.
2) B — Code is deployed to /versioned/.../cartridges for a code version.
3) A, B — Match relative path and ensure higher priority than base.
4) B — Sites independently reference a code version.
5) A, B — Clear application cache and invalidate iscache.
6) B — Left-to-right precedence resolves artifacts.
7) A — Active version is selected in Code Versions UI.
8) B — dw.json configures IDE/WebDAV upload target.
9) B — Single site-level path; handle locale in code/templates.
10) B — app_*.properties stores cartridge metadata.
11) A — server.middleware.https enforces HTTPS per route.
12) B — Invalid cartridge structure prevents selection.
13) A — Site Import & Export handles inbound data.
14) A, C — Mark searchable and reindex.
15) A — Refinements configured under Search.
16) B — Dictionaries support one-way synonyms.
17) A, B — Extend model and update templates.
18) A — Configure logging under Admin > Operations.
19) A — Page Designer supports modular landing pages.
20) A, B — Missing localized values or index refresh cause drops.
21) A, B — ocapi.json + client credentials required.
22) A — Structured logging with correct levels.
23) A — Site Settings define currency/taxation.
24) A, B — Properties/ISML define label text.
25) A — Keep controllers thin; move logic to helpers/decorators/factories.
26) A — iscache caches fragments.
27) A — CSRF generate on GET; validate on POST.
28) A, B — Proper content type and JSON body handling.
29) A — Use pricing/tax hooks to adjust behavior.
30) A, B — Service Framework + batching/caching avoid N+1.
31) A, B — Properties and Resource helpers provide i18n.
32) A — Add vary keys or disable include cache.
33) A — No cache or appropriate vary keys for personalization.
34) B — Parse application-level status and handle errors.
35) A, B — Minimize/encrypt PII; enforce least privilege.
36) A — Stream CSV incrementally.
37) A, B — OCAPI Shop permissions + client mapping.
38) A, B — Import via script then trigger indexing.
39) A, B — impex src and src/instance are typical.
40) A, B — Backoff and schedule/lock coordination.
41) A, B — Restrict attributes; dedicated credentials.
42) A, C — Blue/green or overlapping keys if supported.
43) A, B — Fail fast, retry transients, circuit breaker.
44) A — Delta indexing for frequent updates.
45) A, B — Write permissions/attributes and client mapping.
46) A — Serialize or exclusive windows.
47) A — Redact/mask tokens; avoid logging bodies.
48) A — No cache or vary keys (price group/locale).
49) A, B — Precompute and cache static fragments.
50) A, B — Batch/cache or precompute via jobs.
51) A, B — Clear app cache and iscache.
52) A — Stream JSON to avoid OOM.
53) A, B — Missing vary or global cache causes leakage.
54) A, B — Add locale bundles; use Resource helpers.
55) A, B, C — Timeouts, retries with backoff, circuit breaker.
56) A, B, C — Profiling/timing/diffs isolate regressions.
57) A, B — Move logic out of ISML; cache fragments.
58) A — Vary by currency where cached.
59) A, B — Idempotency and UI prevention.
60) A — Coordinate schedules, lock, and backoff for robustness.