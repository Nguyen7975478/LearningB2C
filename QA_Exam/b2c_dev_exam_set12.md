# Salesforce Certified B2C Commerce Developer — Practice Questions (Set 12)
Total: 60 questions, standard difficulty. Each question indicates how many answers to select. An answer key with concise explanations is at the end.

Section A: Setup, Code Versions, Cartridges (12)
1) A cartridge was uploaded under the correct code version, but new routes still 404. What should you verify first? (Select one)
A. Page Designer page is published
B. Site cartridge path includes the cartridge before app_storefront_base
C. The ocapi.json file includes the route
D. A full search reindex ran

2) Where are cartridges deployed for a specific code version via WebDAV? (Select one)
A. /impex/src/
B. /versioned/cartridges/<code-version>/cartridges
C. /static/default/
D. /impex/exports/

3) An ISML override isn’t taking effect. Which two are likely causes? (Select two)
A. The override isn’t at the same relative path/name as base
B. The custom cartridge is after app_storefront_base in the path
C. The override must be registered in ocapi.json
D. The override must be uploaded to /impex/src/templates

4) Which statement about the site’s code version is correct? (Select one)
A. It’s global for the instance
B. It’s selected per site in Site Settings
C. It’s inferred from cartridge path
D. It’s only configurable at Organization level

5) After switching code versions, old templates still render. Which two actions help? (Select two)
A. Clear application cache
B. Invalidate affected iscache fragments
C. Rebuild search indexes per request
D. Rename the code version

6) Why does cartridge order matter? (Select one)
A. It determines left-to-right resolution precedence for controllers/templates/scripts
B. It controls OCAPI rate limits
C. It controls CSRF enablement
D. It determines log levels

7) Where do you select the active code version? (Select one)
A. BM > Administration > Site Development > Code Versions
B. BM > Merchant Tools > Search
C. BM > Content > Assets
D. BM > SEO

8) What does dw.json primarily configure? (Select one)
A. OCAPI Data permissions
B. IDE/WebDAV host/credentials and target code version
C. Page Designer components
D. Search dictionaries

9) A business requests different cartridge paths per locale on one site. What’s the guidance? (Select one)
A. Supported per locale in Site Settings
B. Not supported; use one site-level path, handle locale in code/templates
C. Supported via ocapi.json
D. Supported via services.json

10) Which file stores cartridge metadata such as id/description? (Select one)
A. templates/resources/*.properties
B. app_*.properties
C. ocapi.json
D. services.json

11) To enforce HTTPS on a controller route, use: (Select one)
A. server.middleware.https
B. ocapi.json
C. Page Designer policy
D. services.json

12) A valid cartridge is uploaded but not selectable in the site path picker. Likely reason? (Select one)
A. Missing cartridge/ subfolder (invalid cartridge structure)
B. Missing ocapi.shop client
C. Missing cspTrustedSite
D. Wrong locale

Section B: Business Manager, Search, Content, Logging (12)
13) Where do you import catalogs and inventory? (Select one)
A. BM > Merchant Tools > Site Import & Export
B. BM > Administration > Logs
C. BM > SEO
D. BM > Services

14) Which two steps make a product attribute searchable? (Select two)
A. Mark attribute as searchable
B. Add attribute to Page Designer
C. Rebuild the search index
D. Add attribute to ocapi.json read_attributes

15) Where are storefront search refinements (facets) configured? (Select one)
A. Merchant Tools > Search > Search Refinements
B. Merchant Tools > SEO > URL Rules
C. Administration > Sites
D. Content > Assets

16) Define a one-way synonym “sneaker → running shoe.” Where and how? (Select one)
A. SEO Redirect
B. Search > Dictionaries; one-way synonym
C. Search > Search Refinements; two-way synonym
D. Site Preference

17) To display a new PDP attribute, which two areas are typically updated? (Select two)
A. Product model decorators/factory
B. PDP ISML template
C. ocapi.json
D. services.json

18) Configure log categories and appenders at: (Select one)
A. BM > Administration > Operations > Logging
B. ocapi.json
C. services.json
D. templates/resources

19) A marketer wants to compose landing pages from components. Use: (Select one)
A. Page Designer
B. Content Assets only
C. URL Rules
D. OCAPI Shop

20) After enabling a locale, search recall drops. What two items are typical causes? (Select two)
A. Missing localized values for searchable attributes
B. Forgot to run reindex
C. Missing dw.json
D. Wrong code version selected

21) To expose a custom object via Data API, which two steps are required? (Select two)
A. Update ocapi.json read/write with attribute lists
B. Create and map OCAPI client credentials
C. Create a new cartridge
D. Rebuild search

22) What is production logging best practice? (Select one)
A. Use Logger categories INFO/WARN/ERROR; DEBUG targeted
B. System.out.println
C. Everything at DEBUG
D. Disable logs

23) Where do you set default currency and taxation? (Select one)
A. Administration > Sites > Manage Sites > [Site] > Settings
B. Merchant Tools > Search
C. Merchant Tools > SEO
D. Services > Profiles

24) Which two places commonly hold availability label copy? (Select two)
A. templates/resources/*.properties
B. ISML templates
C. ocapi.json
D. Code Versions page

Section C: Controllers, ISML, Forms, Hooks, Services (12)
25) Maintainable controller design means: (Select one)
A. Thin controllers; domain logic in helpers/decorators/factories
B. Put logic in ISML
C. Put all logic in controllers
D. Avoid services

26) Directive to cache template fragments: (Select one)
A. iscache
B. isif
C. isloop
D. isdecorate

27) Proper CSRF for forms requires: (Select one)
A. Generate token on GET; validate on POST via csrfProtection
B. HTTPS only
C. Not needed in SFRA
D. Site preference only

28) For a JSON route, which two are correct? (Select two)
A. Set Content-Type to application/json
B. Use res.json or write JSON to response
C. Render ISML, then convert to JSON
D. Disable caching globally

29) You must change pricing logic without editing base controllers. Use: (Select one)
A. Pricing/tax hook extension points
B. Page Designer
C. URL Rules
D. Site preference only

30) A PLP performs a blocking service call per item. Which two help? (Select two)
A. Use Service Framework with timeouts and circuit breaker
B. Batch/caching to avoid N+1
C. Move calls to ISML
D. Use System.out.println

31) To localize strings, use: (Select two)
A. templates/resources/*.properties
B. Resource.msg/Resource.msgf
C. ocapi.json
D. services.json

32) A remote include shows stale promo state. Likely fix: (Select one)
A. Add appropriate vary keys (basket/promo/customer) or disable include caching
B. Disable all caching globally
C. Change code version
D. Switch to GET

33) Safe caching for a personalized Shop API response: (Select one)
A. No cache, or cache with vary (customer group/locale/currency)
B. Global cache with no vary
C. CDN cache only
D. Response cache only

34) A service returns 200 but error in body. Correct handling: (Select one)
A. Treat as success
B. Parse domain-level status and handle errors
C. Timeout instead
D. Retry forever

35) PII submissions must: (Select two)
A. Minimize/encrypt sensitive fields
B. Restrict OCAPI Data access to least privilege
C. Log raw payload for support
D. Use GET to avoid CSRF

36) A controller must output a large CSV. Best approach: (Select one)
A. Stream incrementally with appropriate headers
B. Build all in memory
C. Render via ISML
D. Print to System.out

Section D: OCAPI, Jobs, Integrations, Data (12)
37) To allow baskets via OCAPI Shop, do which two? (Select two)
A. Configure ocapi.json Shop permissions with allowed attributes
B. Map client credentials to that setting
C. Create a new code version
D. Add a PD component

38) A nightly job imports inventory and reindexes search. Typical steps: (Select two)
A. Script step to import inventory
B. System step to trigger delta/full index
C. Disable CSRF
D. Restart instances

39) Which inbound folders are common for imports? (Select two)
A. /impex/src/
B. /impex/src/instance/
C. /versioned/cartridges/
D. /static/default/

40) Import job collisions occur. Which two mitigations help? (Select two)
A. Retry with exponential backoff
B. Coordinate schedules/locks (serialize)
C. Add TRACE logs only
D. Run as a controller route

41) Least-privilege Data API on orders requires: (Select two)
A. Restrict read_attributes to required fields
B. Dedicated client credentials per integration
C. One shared client for all partners
D. Expose all fields

42) Zero-downtime credential rotation should: (Select two)
A. Introduce new credential/profile and cut over
B. Hardcode secret in code
C. Support overlapping keys if upstream allows
D. Stop traffic

43) Robust synchronous integration includes: (Select two)
A. Short timeouts and circuit breaker
B. Retries with exponential backoff
C. Always log full payloads
D. Never cache

44) Frequent product deltas. Best indexing policy: (Select one)
A. Delta index after each import
B. Full index hourly
C. Weekly index
D. No index

45) To write to a custom object via Data API, you need: (Select two)
A. ocapi.json write with write_attributes
B. Client credentials mapped to that ocapi.json setting
C. A new code version
D. Search refinements

46) Two job steps conflict updating same records. Remedy: (Select one)
A. Locking/serialization or mutually exclusive windows
B. Disable logs
C. Remote includes
D. Global cache

47) Prevent token leakage from service logs by: (Select one)
A. Redact/mask in parser; avoid logging bodies unless masked
B. Use System.out.println
C. Always DEBUG
D. Disable services

48) Shop API varies by price group and locale. Safe caching: (Select one)
A. No cache or cache with appropriate vary keys
B. Global cache
C. CDN with no vary
D. Response cache only

Section E: Performance, Caching, Troubleshooting (12)
49) Reduce PDP TTFB by: (Select two)
A. Precompute heavy fields in decorators
B. Cache static fragments with iscache and proper vary
C. Disable caching
D. Use OCAPI only

50) Profiler shows heavy per-item service calls. Improve by: (Select two)
A. Batch/cache calls
B. Compute offline via jobs; decorate from storage
C. TRACE logs globally
D. Remote includes per tile

51) Stale content persists post-deploy. Likely actions: (Select two)
A. Clear application cache
B. Invalidate iscache fragments
C. Rebuild search per request
D. Rename code version

52) Large JSON export OOMs. Correct pattern: (Select one)
A. Stream JSON chunks
B. Build the entire object in memory
C. Use ISML
D. Disable HTTPS

53) Cache correctness issues often come from: (Select two)
A. Missing vary-by-locale/currency
B. Global cache with no vary
C. Using decorators
D. Using Resource.msg

54) New locale shows English strings. Fix: (Select two)
A. Add locale properties under templates/resources
B. Use Resource.msg/Resource.msgf
C. Update ocapi.json
D. Switch code version

55) A route times out on a downstream service. Best practices: (Select three)
A. Short timeouts (fail fast)
B. Retries with backoff
C. Circuit breaker
D. Increase synchronous calls

56) PDP slowed after release. Which three diagnostics help? (Select three)
A. Compare profiler traces before/after
B. Add targeted timing logs
C. Diff changed services/decorators/hooks
D. Disable logs permanently

57) Lower ISML CPU by: (Select two)
A. Precompute in helpers/decorators
B. Cache static fragments
C. Add HTTP calls in templates
D. Heavy loops in ISML

58) A PD component shows wrong currency when cached. Fix: (Select one)
A. Add vary-by-currency
B. Use ocapi.json
C. Disable CSRF
D. Rebuild catalog

59) Prevent duplicate POST submissions: (Select two)
A. Idempotency keys with server-side dedupe
B. Disable submit button after click
C. Use GET
D. Disable CSRF

60) Catalog import and delta index conflict. Remedy: (Select one)
A. Coordinate schedules/locks and add retries/backoff
B. Disable indexing
C. Add DEBUG logs
D. Change code version

Answer Key and Explanations
1) B — Ensure cartridge path precedence before base.
2) B — Deployed code lives at /versioned/.../cartridges.
3) A, B — Same path/name and higher path priority are required.
4) B — Sites independently select a code version.
5) A, B — Clear application cache and invalidate template fragments.
6) A — Left-to-right precedence controls resolution.
7) A — Code Versions UI sets active version.
8) B — dw.json configures IDE/WebDAV target and version.
9) B — Single site-level path; implement locale in code/templates.
10) B — app_*.properties contains cartridge metadata.
11) A — Use server.middleware.https.
12) A — Invalid structure prevents selection.
13) A — Site Import & Export handles inbound data.
14) A, C — Mark searchable and reindex.
15) A — Configure facets in Search Refinements.
16) B — Dictionaries support one-way synonyms.
17) A, B — Extend model and render in templates.
18) A — Logging configured under Admin > Operations.
19) A — Page Designer enables component-based pages.
20) A, B — Missing localized values or reindex cause drop.
21) A, B — ocapi.json permissions and client mapping.
22) A — Use Logger with appropriate levels; DEBUG sparingly.
23) A — Site Settings manage currency/tax.
24) A, B — Properties and ISML control copy.
25) A — Keep controllers thin; push logic to helpers/decorators/factories.
26) A — iscache caches fragments.
27) A — CSRF token generate/validate pattern.
28) A, B — JSON content type and response handling.
29) A — Use pricing/tax hooks to modify behavior.
30) A, B — Service Framework and batching/caching avoid N+1.
31) A, B — Use properties bundles and Resource helpers.
32) A — Add vary for context-dependent includes or disable cache.
33) A — No cache or vary keys for personalization.
34) B — Parse domain status and handle errors.
35) A, B — Minimize/encrypt PII and enforce least privilege.
36) A — Stream CSV with headers.
37) A, B — OCAPI Shop + client credentials mapping.
38) A, B — Import via script and trigger indexing via system step.
39) A, B — impex src and src/instance are common inbound folders.
40) A, B — Retries/backoff and serialization avoid collisions.
41) A, B — Limit attributes; dedicated credentials.
42) A, C — New credential and overlap keys if supported.
43) A, B — Fail fast, retry transients, and use circuit breaker.
44) A — Delta indexing is efficient for frequent deltas.
45) A, B — Write permissions/attributes and mapped client.
46) A — Serialize or separate windows for shared resources.
47) A — Redact before logging; avoid body logs unless masked.
48) A — No cache or vary by price group/locale.
49) A, B — Precompute heavy data and cache static parts.
50) A, B — Batch/cache or precompute via jobs.
51) A, B — Clear app and iscache template caches.
52) A — Stream JSON to avoid OOM.
53) A, B — Missing varies or global cache cause leakage.
54) A, B — Add locale bundles and use Resource helpers.
55) A, B, C — Short timeouts, backoff retries, and circuit breaker.
56) A, B, C — Profiling, timing, and diffs isolate regressions.
57) A, B — Move logic out of templates and cache fragments.
58) A — Vary-by-currency to ensure correctness.
59) A, B — Idempotency and UI prevention stop duplicates.
60) A — Coordinate schedules, lock, and backoff.