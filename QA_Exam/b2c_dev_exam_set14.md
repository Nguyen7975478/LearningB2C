# Salesforce Certified B2C Commerce Developer — Practice Questions (Set 14)
Total: 60 questions, standard difficulty. Each question indicates how many answers to select. An answer key with concise explanations is at the end.

Section A: Setup, Code Versions, Cartridges (12)
1) New controllers in a custom cartridge don’t resolve after upload. What should you check first? (Select one)
A. Search index state
B. Site cartridge path includes the cartridge and ordering before app_storefront_base
C. Page Designer components installed
D. ocapi.json

2) Correct WebDAV path for deploying a cartridge to a code version is: (Select one)
A. /impex/src/
B. /versioned/cartridges/<code-version>/cartridges
C. /static/default/
D. /impex/exports/

3) An override ISML file is ignored. Which two are typical causes? (Select two)
A. File path/name doesn’t match the base template
B. Custom cartridge ordered after app_storefront_base
C. ocapi.json missing the template
D. Code version alias missing

4) Which statement about code versions is correct? (Select one)
A. One global code version for all sites
B. Each site references a code version in its own settings
C. Determined only by Organization settings
D. Determined by cartridge path automatically

5) After switching to a new code version, stale templates still render. Which two actions are appropriate? (Select two)
A. Clear application cache
B. Invalidate affected iscache fragments
C. Rebuild search for each request
D. Change the site ID

6) Why does cartridge path order matter? (Select one)
A. It enables CSRF
B. Left-to-right precedence resolves controllers/templates/scripts
C. It configures OCAPI quotas
D. It picks the active locale

7) Where is the active code version selected? (Select one)
A. BM > Administration > Site Development > Code Versions
B. BM > Merchant Tools > Search
C. BM > Content > Assets
D. BM > SEO

8) dw.json primarily configures: (Select one)
A. OCAPI Shop permissions
B. IDE/WebDAV connection details and target code version
C. Page Designer policy
D. Search ranking

9) A site needs different cartridge paths per locale. What is correct? (Select one)
A. Configure per-locale cartridge paths
B. Not supported; use one site-level path and handle locale in code/templates
C. Use ocapi.json per locale
D. Use services.json per locale

10) What file holds cartridge metadata like id/description? (Select one)
A. templates/resources/*.properties
B. app_*.properties
C. ocapi.json
D. services.json

11) Enforce HTTPS on selected routes by: (Select one)
A. server.middleware.https
B. ocapi.json
C. Page Designer
D. services.json

12) A valid cartridge doesn’t appear in the site path picker. Likely reason? (Select one)
A. No synonyms configured
B. Missing cartridge/ subfolder (invalid structure)
C. Wrong code version alias
D. Log categories not set

Section B: Business Manager, Search, Content, Logging (12)
13) Where is catalog/inventory import executed? (Select one)
A. BM > Administration > Logs
B. BM > Merchant Tools > Site Import & Export
C. BM > SEO
D. BM > Services

14) Making a product attribute searchable requires: (Select two)
A. Mark attribute searchable
B. Add attribute to Page Designer
C. Rebuild search index
D. Add to ocapi.json read_attributes

15) Where are storefront refinements configured? (Select one)
A. Merchant Tools > Search > Search Refinements
B. Merchant Tools > SEO > URL Rules
C. Administration > Sites
D. Content > Assets

16) You need a one-way synonym “beanie → knit cap”. Where and how? (Select one)
A. SEO Redirect
B. Search > Dictionaries; one-way synonym
C. Search > Search Refinements
D. Site Preference

17) To render a new PDP attribute, typically update: (Select two)
A. Product model decorators/factory
B. PDP ISML template
C. ocapi.json
D. services.json

18) Where are log categories and appenders configured? (Select one)
A. BM > Administration > Operations > Logging
B. ocapi.json
C. services.json
D. templates/resources

19) A merchandiser wants component-based pages. Use: (Select one)
A. Page Designer
B. Content Assets only
C. URL Rules
D. OCAPI Data

20) After enabling a new locale, search recall drops. Likely two causes: (Select two)
A. Missing localized values for searchable attributes
B. Forgot to reindex
C. Missing dw.json
D. Missing cspTrustedSite

21) To expose a custom object via Data API, you must: (Select two)
A. Update ocapi.json with read/write and attribute lists
B. Create and map OCAPI client credentials
C. Create a new code version
D. Create a new cartridge

22) Production logging best practice: (Select one)
A. Use Logger categories with INFO/WARN/ERROR; DEBUG only for targeted troubleshooting
B. Use System.out.println
C. Log everything at DEBUG
D. Disable logs

23) Configure default currency/taxation at: (Select one)
A. Administration > Sites > Manage Sites > [Site] > Settings
B. Merchant Tools > Search
C. Merchant Tools > SEO
D. Services > Profiles

24) To change availability label text, edit: (Select two)
A. templates/resources/*.properties
B. ISML templates
C. ocapi.json
D. Code Versions page

Section C: Controllers, ISML, Forms, Hooks, Services (12)
25) Maintainable controller pattern: (Select one)
A. Thin controllers; logic in helpers/decorators/factories
B. Put core logic in ISML
C. Keep all logic in controllers
D. Avoid services

26) Directive for cacheable fragments: (Select one)
A. iscache
B. isif
C. isloop
D. isdecorate

27) Proper CSRF for forms requires: (Select one)
A. Generate token on GET; validate on POST using csrfProtection
B. HTTPS only
C. Not needed in SFRA
D. Site preference only

28) For a JSON route, which two are correct? (Select two)
A. Set Content-Type to application/json
B. Use res.json or write JSON to response
C. Render ISML then convert to JSON
D. Disable caching globally

29) Change pricing behavior without editing base controllers by: (Select one)
A. Pricing/tax hook extension points
B. Page Designer
C. URL Rules
D. Site Preference

30) A PLP makes synchronous HTTP calls per item. Which two actions help? (Select two)
A. Use Service Framework with timeouts and circuit breaker
B. Batch/cache to avoid N+1
C. Move calls to ISML
D. Use System.out.println for timing

31) To localize UI text, use: (Select two)
A. templates/resources/*.properties
B. Resource.msg/Resource.msgf
C. ocapi.json
D. services.json

32) A remote include shows stale promotion data. Correct fix: (Select one)
A. Add vary keys (basket/promo/customer) or disable include cache
B. Disable all caching
C. Change code version
D. Rebuild search

33) For personalized Shop API responses, safe caching is: (Select one)
A. No cache, or cache with vary (customer group/locale/currency)
B. Global cache only
C. CDN cache with no vary
D. Response cache blindly

34) HTTP 200 with error in body from a service should be handled by: (Select one)
A. Treating as success
B. Parsing domain status fields and failing appropriately
C. Timing out
D. Retrying forever

35) PII form submissions should: (Select two)
A. Minimize/encrypt sensitive fields
B. Restrict OCAPI Data access with least privilege
C. Log raw payloads for support
D. Use GET instead of POST

36) A controller streams a large CSV. Correct approach: (Select one)
A. Stream incrementally with proper headers
B. Build fully in memory then send
C. Use ISML to render CSV
D. Print to System.out

Section D: OCAPI, Jobs, Integrations, Data (12)
37) To allow baskets via OCAPI Shop, do which two? (Select two)
A. Configure ocapi.json Shop permissions with allowed attributes
B. Map client ID/secret to that setting
C. Create new code version
D. Add PD component

38) Nightly job: import inventory then reindex. Typical steps: (Select two)
A. Script step for import
B. System step for delta/full index
C. Disable CSRF
D. Restart code version

39) Common inbound file locations: (Select two)
A. /impex/src/
B. /impex/src/instance/
C. /versioned/cartridges/
D. /static/default/

40) Jobs intermittently collide on same records. Which two mitigations help? (Select two)
A. Retry with exponential backoff
B. Coordinate schedules/locks to serialize
C. Add TRACE logs only
D. Run imports from controllers

41) Least-privilege Data API for orders should: (Select two)
A. Restrict read_attributes to necessary fields
B. Use dedicated client credentials per integration
C. Share one global client
D. Expose all attributes

42) Zero-downtime credential rotation should: (Select two)
A. Introduce a new credential/profile and cut over
B. Hardcode the secret in code
C. Support overlapping keys if upstream allows
D. Stop traffic

43) Robust synchronous integration includes: (Select two)
A. Short timeouts and circuit breaker
B. Retries with backoff for transient errors
C. Always log full payloads
D. Never cache

44) Frequent product delta imports. Best indexing: (Select one)
A. Delta index after each import
B. Full index each hour
C. Weekly index
D. No index

45) To write to a custom object via Data API, you need: (Select two)
A. ocapi.json write with write_attributes
B. Client credentials mapped to that ocapi.json setting
C. A new code version
D. Search refinements

46) Two job steps update the same set; remedy is: (Select one)
A. Locking/serialization or exclusive windows
B. Disable logs
C. Use remote includes
D. Global cache

47) Prevent token leakage in logs by: (Select one)
A. Redacting/masking tokens in parser; avoid logging bodies unless masked
B. Printing to System.out
C. Logging all bodies at DEBUG
D. Disabling services

48) Shop API varies by price group and locale. Safe caching: (Select one)
A. No cache or cache with appropriate vary keys
B. Global cache only
C. CDN no-vary
D. Response cache blindly

Section E: Performance, Caching, Troubleshooting (12)
49) Reduce PDP TTFB: (Select two)
A. Precompute heavy fields in decorators
B. Cache static fragments (iscache) with proper vary
C. Disable cache
D. Use OCAPI only

50) Profiler shows heavy per-tile service calls. Improve by: (Select two)
A. Batch/cache calls
B. Precompute via jobs and decorate from storage
C. Add TRACE logs globally
D. Use remote includes per tile

51) Stale content persists after deploy. Which two are typical fixes? (Select two)
A. Clear application cache
B. Invalidate iscache fragments
C. Rebuild search on every request
D. Rename code version

52) Large JSON export OOMs. Appropriate fix: (Select one)
A. Stream JSON chunks to response
B. Build JSON fully in memory
C. Render via ISML
D. Disable HTTPS

53) Cache correctness issues usually stem from: (Select two)
A. Missing vary-by-locale/currency
B. Using global cache with no vary
C. Using decorators
D. Using properties bundles

54) New locale shows English strings. Fix: (Select two)
A. Add locale-specific templates/resources/*.properties
B. Use Resource.msg/Resource.msgf
C. Update ocapi.json
D. Switch code version

55) A route times out on a downstream dependency. Best practices: (Select three)
A. Short timeouts (fail fast)
B. Retries with exponential backoff
C. Circuit breaker
D. Increase synchronous calls

56) After release, PDP is slower by ~220ms. Which three diagnostics help? (Select three)
A. Compare profiler traces before/after
B. Add targeted timing logs
C. Diff changes in services/decorators/hooks
D. Disable logs permanently

57) Reduce ISML CPU cost by: (Select two)
A. Move logic to helpers/decorators
B. Cache static fragments with iscache
C. Add blocking HTTP calls in templates
D. Heavy loops in ISML

58) A PD component shows wrong currency under cache. Fix: (Select one)
A. Add vary-by-currency
B. Use ocapi.json
C. Disable CSRF
D. Rebuild catalog

59) Prevent duplicate POST effects: (Select two)
A. Idempotency keys with server-side dedupe
B. Disable submit button after click on client
C. Use GET
D. Disable CSRF

60) Catalog import conflicts with delta indexing occasionally. Best remedy: (Select one)
A. Coordinate schedules, lock shared resources, and add retries/backoff
B. Disable indexing
C. Add DEBUG logs
D. Change code version

Answer Key and Explanations
1) B — Cartridge must be in path and ordered before base.
2) B — Deployed code lives under /versioned/.../cartridges.
3) A, B — Match relative path and ensure priority over base.
4) B — Each site selects its own code version.
5) A, B — Clear app cache and invalidate template cache.
6) B — Left-to-right precedence controls resolution.
7) A — Code Versions UI sets the active version.
8) B — dw.json configures IDE/WebDAV target and version.
9) B — One site-level path; implement locale in code/templates.
10) B — app_*.properties holds cartridge metadata.
11) A — Use server.middleware.https for secure routes.
12) B — Invalid cartridge structure prevents selection.
13) B — Site Import & Export handles inbound data loads.
14) A, C — Mark searchable and reindex.
15) A — Refinements configured under Search.
16) B — Dictionaries support one-way synonyms.
17) A, B — Extend model and update templates.
18) A — Logging configured under Admin > Operations.
19) A — Page Designer supports componentized pages.
20) A, B — Missing localized values or reindexing lowers recall.
21) A, B — ocapi.json permissions and client mapping required.
22) A — Use Logger with proper levels; DEBUG sparingly.
23) A — Site Settings store currency/taxation.
24) A, B — Properties and ISML define labels.
25) A — Keep controllers thin and move logic to helpers/decorators/factories.
26) A — iscache caches fragments for performance.
27) A — Generate on GET; validate on POST.
28) A, B — Proper content type and JSON response.
29) A — Use pricing/tax hooks for extensibility.
30) A, B — Service framework + batching/caching avoid N+1.
31) A, B — Properties bundles and Resource helpers for i18n.
32) A — Add appropriate vary keys or disable include cache.
33) A — No cache or use vary for personalization.
34) B — Parse business-level status to detect failures.
35) A, B — Minimize/encrypt PII and lock down access.
36) A — Stream CSV with headers.
37) A, B — OCAPI Shop and client mapping.
38) A, B — Import then index via system step.
39) A, B — impex src and src/instance are standard inbound folders.
40) A, B — Backoff and serialized scheduling/locking.
41) A, B — Restrict attributes; dedicated credentials.
42) A, C — New credential; overlap keys if allowed.
43) A, B — Fail fast, retry transients, and circuit-break failures.
44) A — Delta indexing fits frequent updates.
45) A, B — Write permissions/attributes + mapped client.
46) A — Serialize or exclusive windows prevent collisions.
47) A — Redact tokens and avoid logging bodies.
48) A — No cache or vary by price group/locale.
49) A, B — Precompute and cache static fragments.
50) A, B — Batch/cache or precompute with jobs.
51) A, B — Clear app and template caches.
52) A — Stream JSON to avoid memory spikes.
53) A, B — Missing vary or global cache often causes leakage.
54) A, B — Add locale bundles and use Resource helpers.
55) A, B, C — Short timeouts, backoff retries, circuit breaker.
56) A, B, C — Profiling, timers, and diffs isolate regressions.
57) A, B — Move logic out of ISML; cache fragments.
58) A — Vary by currency to ensure correctness.
59) A, B — Idempotency and UI prevention stop duplicates.
60) A — Orchestrate schedules, lock, and backoff for robustness.