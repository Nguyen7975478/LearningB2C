# Salesforce Certified B2C Commerce Developer — Practice Questions (Set 10)
Total: 60 questions, standard difficulty. Each question indicates how many answers to select. An answer key with concise explanations is at the end.

Section A: Setup, Code Versions, Cartridges (12)
1) A new custom controller was uploaded but returns 404. What is the most likely issue? (Select one)
A. Missing reindex
B. Cartridge not added to the site’s cartridge path
C. Missing Page Designer component
D. Wrong locale

2) Where must cartridge code be uploaded for a specific code version? (Select one)
A. /impex/src/
B. /versioned/cartridges/<code-version>/cartridges
C. /static/default/
D. /impex/exports/

3) You need to override app_storefront_base PDP template. Which two conditions are required? (Select two)
A. The override must be placed at the same relative path/name
B. The override must be registered in ocapi.json
C. The custom cartridge must be before app_storefront_base in the path
D. The template must be in /impex/src/templates

4) Which is true about code versions? (Select one)
A. A single global code version is enforced for all sites
B. Each site independently references a code version in Settings
C. Code versions are inferred from ocapi.json
D. The Organization-level setting overrides site-level

5) After switching the referenced code version, the storefront still renders old content. Which two steps help? (Select two)
A. Clear application cache
B. Invalidate iscache fragments for affected templates
C. Rebuild search every request
D. Change the cartridge id

6) Why does cartridge order matter in SFRA? (Select one)
A. Determines which translation files load
B. Determines left-to-right resolution precedence for controllers/templates/scripts
C. Determines OCAPI client throttling
D. Determines CDN header behavior

7) Where is the active code version selected? (Select one)
A. BM > Administration > Site Development > Code Versions
B. BM > Merchant Tools > SEO
C. BM > Content > Assets
D. BM > Services

8) What does dw.json configure? (Select one)
A. OCAPI Shop permissions
B. IDE/WebDAV connection (hostname, username, code version)
C. Page Designer permissions
D. Search synonyms

9) A stakeholder requests different cartridge paths per locale within one site. Correct guidance? (Select one)
A. Supported via site preferences
B. Not supported; use a single site-level path and handle locale in code/templates
C. Supported via ocapi.json
D. Supported via services.json

10) Which artifact inside a cartridge defines cartridge metadata like id/description? (Select one)
A. templates/resources/*.properties
B. app_*.properties
C. ocapi.json
D. services.json

11) You must enforce HTTPS on sensitive routes. What should you use? (Select one)
A. server.middleware.https
B. ocapi.json
C. Page Designer policy
D. services.json

12) Two cartridges define the same controller route. Which implementation runs? (Select one)
A. The newer file by timestamp
B. The implementation in the leftmost cartridge in the site path
C. The rightmost cartridge in the site path
D. The platform throws an error

Section B: Business Manager, Search, Content, Logging (12)
13) Where can you import catalogs and inventory? (Select one)
A. BM > Administration > Logs
B. BM > Merchant Tools > Site Import & Export
C. BM > SEO
D. BM > Services

14) To make a product attribute searchable, which two are required? (Select two)
A. Mark the attribute as searchable
B. Add the attribute to Page Designer
C. Rebuild the search index
D. Add it to ocapi.json read_attributes

15) Where are storefront search refinements configured? (Select one)
A. Merchant Tools > Search > Search Refinements
B. Merchant Tools > SEO > URL Rules
C. Administration > Sites
D. Content > Assets

16) A one-way synonym “parka → winter coat” is required. Where is it configured? (Select one)
A. SEO > Redirects
B. Search > Dictionaries (one-way)
C. Search > Search Refinements
D. Site Preferences

17) To show a new PDP attribute value, which two updates are typical? (Select two)
A. Product model decorators/factory to expose data
B. PDP ISML template to render
C. ocapi.json
D. services.json

18) Where are Logger categories and appenders configured? (Select one)
A. BM > Administration > Operations > Logging
B. ocapi.json
C. services.json
D. dw.json

19) A marketer wants to assemble new landing pages with components. Which feature should be used? (Select one)
A. Page Designer
B. URL Rules
C. OCAPI Shop
D. Services

20) After enabling a new locale, search returns fewer results. Which two are likely? (Select two)
A. Missing localized values for searchable attributes
B. Forgot to reindex after data change
C. Missing cspTrustedSite
D. Wrong code version active

21) To allow an integration to access a custom object via OCAPI Data, which two steps are required? (Select two)
A. ocapi.json with read/write and attribute lists
B. OCAPI client credentials mapped to that setting
C. New code version
D. New Page Designer page type

22) Production logging best practice: (Select one)
A. Logger with categories at INFO/WARN/ERROR; DEBUG sparingly for targeted troubleshooting
B. System.out.println
C. Everything at DEBUG
D. Disable logs

23) Where do you configure the site default currency and taxation type? (Select one)
A. Administration > Sites > Manage Sites > [Site] > Settings
B. Merchant Tools > Search
C. Merchant Tools > SEO
D. Administration > Roles

24) To change availability label copy, which two places are typical? (Select two)
A. templates/resources/*.properties
B. ISML templates rendering the label
C. ocapi.json
D. dw.json

Section C: Controllers, ISML, Forms, Hooks, Services (12)
25) Maintainable controller design includes: (Select one)
A. Thin controllers; business logic in helpers/decorators/factories
B. ISML templates contain business logic
C. Controllers contain all logic
D. Avoid services entirely

26) Which directive enables cacheable template fragments? (Select one)
A. iscache
B. isif
C. isloop
D. isdecorate

27) Proper CSRF handling for forms requires: (Select one)
A. Generate token on GET and validate on POST via csrfProtection
B. HTTPS alone
C. No CSRF in SFRA
D. Site preference only

28) A route returns JSON. What two actions are correct? (Select two)
A. Set Content-Type to application/json
B. Use res.json or write JSON
C. Render ISML then parse to JSON
D. Disable caching globally

29) Customize pricing behavior without editing base controllers using: (Select one)
A. Hook extension points (pricing/tax)
B. Page Designer
C. URL Rules
D. Site preference only

30) A PLP performs synchronous HTTP per product tile. Which two help? (Select two)
A. Use Service Framework with timeouts and circuit breaker
B. Batch/cache to avoid N+1 calls
C. Move calls into ISML
D. Use System.out.println for timing

31) Localize UI strings using: (Select two)
A. templates/resources/*.properties
B. Resource.msg/Resource.msgf
C. ocapi.json
D. services.json

32) A remote include shows stale promotion data. How to fix? (Select one)
A. Add vary keys for basket/promo/customer context or disable cache for the include
B. Disable all caching
C. Change code version
D. Switch to GET

33) Caching a personalized Shop API response safely requires: (Select one)
A. No cache, or cache with vary on customer group/locale/currency
B. Global cache with no vary
C. CDN cache only
D. Response cache only

34) A service returns HTTP 200 with an error payload. Correct handling is: (Select one)
A. Treat as success and continue
B. Parse application-level status and fail appropriately
C. Rely only on timeout
D. Retry forever

35) Storing PII from a form requires which two? (Select two)
A. Minimize/encrypt sensitive fields where possible
B. Restrict OCAPI Data access to least privilege
C. Log raw PII for troubleshooting
D. Use GET to avoid CSRF

36) A controller must stream a large CSV. Best approach: (Select one)
A. Stream incrementally with appropriate headers
B. Build entire CSV in memory then send
C. Use ISML to render CSV
D. Print to System.out

Section D: OCAPI, Jobs, Integrations, Data (12)
37) To allow baskets via OCAPI Shop, which two are required? (Select two)
A. ocapi.json Shop permissions with allowed attributes
B. Map a client ID/secret to that setting
C. Create a new code version
D. Add a Page Designer component

38) A nightly job imports inventory and reindexes search. Which two steps are typical? (Select two)
A. Script step: import inventory
B. System step: trigger delta/full index
C. Disable logs
D. Rename code version

39) Which inbound folders are commonly used for imports? (Select two)
A. /impex/src/
B. /impex/src/instance/
C. /versioned/cartridges/
D. /static/default/

40) When an import job intermittently fails due to file locks, what two mitigations help? (Select two)
A. Retry with exponential backoff
B. Coordinate schedules/locks to avoid overlap
C. Add TRACE logs only
D. Run the job from controllers

41) Least-privilege OCAPI Data access for orders should include: (Select two)
A. Restrict read_attributes to only required fields
B. Dedicated client credentials per integration
C. One client shared by all partners
D. Expose all fields to simplify mapping

42) To rotate a service credential without downtime, which two steps help? (Select two)
A. Add a new credential/profile and cut over
B. Hardcode the secret in code
C. Support overlapping keys if upstream allows
D. Stop traffic

43) A robust synchronous integration should include: (Select two)
A. Short timeouts and circuit breaker
B. Retries with exponential backoff for transient failures
C. Always log full payloads
D. Never cache anything

44) Product deltas arrive hourly. Which indexing policy is most efficient? (Select one)
A. Delta index after each import
B. Full index hourly
C. Weekly index
D. No index needed

45) To write to a custom object via Data API you need: (Select two)
A. ocapi.json write permissions and write_attributes for fields
B. Client credentials mapped to that ocapi.json setting
C. A new code version
D. Search refinements

46) Two job steps update the same records and collide. The best remedy is: (Select one)
A. Locking/serialization or mutually exclusive windows
B. Disable logs
C. Remote includes
D. Global cache

47) Prevent sensitive token leakage from services logs by: (Select one)
A. Redacting/masking in parsers; avoid logging bodies unless masked
B. Printing to System.out
C. Keep logs at DEBUG
D. Disable the service

48) A Shop API endpoint varies by pricebook and locale. Safe caching strategy: (Select one)
A. No cache, or cache with appropriate vary keys
B. Global cache
C. CDN cache with no vary
D. Application cache only

Section E: Performance, Caching, Troubleshooting (12)
49) To reduce PDP TTFB, which two help? (Select two)
A. Precompute heavy fields in decorators; avoid per-request blocking calls
B. Cache static fragments with iscache and proper vary
C. Always disable caching
D. Force OCAPI

50) Profiler shows heavy per-tile service calls. Which two help? (Select two)
A. Batch/cache calls to avoid N+1
B. Move computation offline to jobs; decorate from stored values
C. Add TRACE logs everywhere
D. Use remote includes for each tile

51) Stale content persists after deployment. Which two are typical fixes? (Select two)
A. Clear application cache
B. Invalidate template caches (iscache) for affected templates
C. Rebuild search every request
D. Change code version name

52) A large JSON export OOMs. Correct fix is: (Select one)
A. Stream chunks to the response
B. Build entire JSON in memory
C. Use ISML
D. Disable HTTPS

53) Cache correctness issues on multi-locale/multi-currency sites often arise from: (Select two)
A. Missing vary-by-locale/currency
B. Using global cache with no vary
C. Using decorators
D. Using Resource.msg

54) New locale shows English strings. Which two fixes apply? (Select two)
A. Add locale-specific properties under templates/resources
B. Use Resource.msg/Resource.msgf helpers
C. Update ocapi.json
D. Switch code version

55) A route frequently times out on a downstream service. Which three techniques are best practice? (Select three)
A. Short timeouts (fail fast)
B. Retries with backoff
C. Circuit breaker
D. Increase synchronous calls

56) After a release, PDP TTFB increased by 250ms. Which three diagnostics help? (Select three)
A. Compare profiler traces before/after
B. Add targeted timing logs around suspect blocks
C. Diff services/decorators/hooks changes
D. Disable logs permanently

57) To reduce ISML template CPU time, which two help? (Select two)
A. Precompute data in helpers/decorators; pass view-ready data
B. Cache static fragments with iscache
C. Add HTTP calls in templates
D. Heavy loops in ISML

58) A PD component shows wrong currency when cached. Fix by: (Select one)
A. Adding vary-by-currency on the cached fragment
B. Using ocapi.json
C. Disabling CSRF
D. Rebuilding catalog

59) Prevent duplicate POST submissions: (Select two)
A. Idempotency keys and server-side dedupe
B. Disable submit button client-side after click
C. Use GET to avoid CSRF
D. Disable CSRF

60) Catalog import and delta reindex sometimes overlap and fail. Best remedy: (Select one)
A. Coordinate schedules with locking and add retries/backoff
B. Disable indexing
C. Add DEBUG logs
D. Change code version

Answer Key and Explanations
1) B — Cartridge must be in the site path to resolve controllers.
2) B — Deployed code for a specific version resides at /versioned/.../cartridges.
3) A, C — Same relative path/name and higher path precedence.
4) B — Sites independently reference a code version.
5) A, B — Clear application cache and invalidate template fragments.
6) B — Left-to-right precedence controls resolution.
7) A — Code Versions page manages the active version.
8) B — dw.json configures IDE/WebDAV connection and target version.
9) B — Path is site-level; handle locale differences in code/templates.
10) B — app_*.properties holds cartridge metadata.
11) A — Use server.middleware.https.
12) B — The leftmost (earliest) cartridge in the path wins.
13) B — Site Import & Export handles inbound data loads.
14) A, C — Mark searchable and rebuild index.
15) A — Refinements are configured under Search.
16) B — One-way synonyms live in Dictionaries.
17) A, B — Extend model and update templates.
18) A — Configure logging under Admin > Operations.
19) A — Page Designer supports componentized pages.
20) A, B — Missing localized values or not reindexing reduces recall.
21) A, B — ocapi.json permissions and client credentials are required.
22) A — Use Logger with appropriate levels; limit DEBUG in prod.
23) A — Site Settings specify currency/taxation.
24) A, B — Properties + ISML typically control user-facing copy.
25) A — Keep controllers thin; push domain logic to helpers/decorators/factories.
26) A — iscache caches template fragments.
27) A — CSRF token generate/validate pattern.
28) A, B — Correct content type and JSON body handling.
29) A — Use hooks to modify pricing/tax behavior.
30) A, B — Service Framework + batching/caching reduces per-item calls.
31) A, B — Use properties bundles and Resource helpers for i18n.
32) A — Add vary keys for basket/promo/customer or disable include cache.
33) A — No cache or appropriate vary keys for personalization.
34) B — Parse application-level status and respond accordingly.
35) A, B — Minimize/encrypt PII; enforce least-privilege access.
36) A — Stream CSV; avoid building large responses in memory.
37) A, B — OCAPI Shop configuration + client mapping.
38) A, B — Import via script, then trigger indexing.
39) A, B — impex src and src/instance are common inbound folders.
40) A, B — Retries with backoff and schedule/lock coordination.
41) A, B — Restrict attributes and use dedicated credentials.
42) A, C — Blue/green credentials or overlapping windows.
43) A, B — Short timeouts, retries, and circuit breaker.
44) A — Use delta indexing for frequent updates.
45) A, B — Write permissions/attributes and mapped client.
46) A — Serialize or isolate windows to avoid conflicts.
47) A — Redact tokens and avoid logging bodies unless masked.
48) A — No cache or vary keys (pricebook/locale).
49) A, B — Precompute and cache static fragments.
50) A, B — Batch/cache and precompute via jobs.
51) A, B — Clear app cache and invalidate iscache.
52) A — Stream JSON to avoid OOM.
53) A, B — Missing vary keys/global cache leads to leakage/incorrectness.
54) A, B — Add locale bundles and use Resource helpers.
55) A, B, C — Fail fast, retry, circuit breaker.
56) A, B, C — Profiling, targeted timers, and diffs isolate regressions.
57) A, B — Move logic out of templates and cache static parts.
58) A — Vary by currency for correctness.
59) A, B — Idempotency and client-side prevention.
60) A — Coordinate schedules, lock, and backoff for robustness.