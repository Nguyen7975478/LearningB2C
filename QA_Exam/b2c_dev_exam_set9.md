# Salesforce Certified B2C Commerce Developer — Practice Questions (Set 9)
Total: 60 questions, standard difficulty. Each question indicates how many answers to select. An answer key with concise explanations is at the end.

Section A: Setup, Code Versions, Cartridges (12)
1) A custom cartridge was uploaded to the correct code version but not appearing in the site’s cartridge path selector. What’s the likely cause? (Select one)
A. Missing ocapi.shop client
B. The uploaded folder is not a valid cartridge structure (missing cartridge/ subfolder)
C. Missing cspTrustedSite entry
D. The site is using the wrong timezone

2) You need to override the base PDP template. Which two conditions must be true? (Select two)
A. The override sits in the same relative path/name in a higher‑priority custom cartridge
B. The override must be registered in ocapi.json
C. The override must be uploaded to /impex/src/templates
D. The custom cartridge appears before app_storefront_base in the site path

3) Which path is used to deploy code via WebDAV for a specific code version? (Select one)
A. /impex/src/instance/
B. /versioned/cartridges/<code-version>/cartridges
C. /static/default/
D. /impex/exports/

4) Why does cartridge order matter? (Select one)
A. It controls ISML syntax
B. It determines resolution precedence for controllers/templates/scripts (left‑to‑right)
C. It sets OCAPI quotas
D. It changes Business Manager roles

5) After changing the site’s referenced code version, you still observe old templates. Which two actions are recommended first? (Select two)
A. Clear application cache
B. Invalidate affected template fragment caches (iscache)
C. Rebuild the entire search index hourly
D. Rename the code version

6) Where do you assign the site’s code version? (Select one)
A. BM > Administration > Site Development > Code Versions
B. BM > Administration > Operations > Logging
C. BM > Merchant Tools > Search
D. BM > Content > Assets

7) What is dw.json primarily used for? (Select one)
A. Configuring OCAPI permissions
B. Configuring IDE/WebDAV upload target and code version for deployment
C. Setting up Page Designer components
D. Creating search refinements

8) A team asks for different cartridge paths by locale on the same site. What is the proper guidance? (Select one)
A. Supported; configure per locale under Site Settings
B. Not supported; cartridge path is site‑level; handle locale in code/templates
C. Supported via ocapi.json
D. Supported via services.json

9) You uploaded a valid cartridge but routes still 404. What’s the first thing to check? (Select one)
A. Code version label
B. Site cartridge path ordering includes the cartridge
C. Search dictionaries
D. Log appenders

10) Which file inside a cartridge typically contains cartridge metadata like id/description? (Select one)
A. app_*.properties
B. templates/resources/*.properties
C. ocapi.json
D. services.json

11) To require HTTPS on certain routes, use: (Select one)
A. server.middleware.https
B. ocapi.json
C. Page Designer rule
D. services.json

12) If two custom cartridges define the same controller route, which executes? (Select one)
A. The route from the rightmost cartridge
B. The route from the first (leftmost) cartridge in the site path
C. The route with the newest timestamp
D. The platform throws an error

Section B: Business Manager, Search, Content, Logging (12)
13) Where do you import product/catalog/inventory data? (Select one)
A. BM > Merchant Tools > Site Import & Export
B. BM > Administration > Site Development > Code Versions
C. BM > SEO
D. BM > Operations > Logging

14) To make a new product attribute searchable, which two steps are required? (Select two)
A. Mark the attribute as searchable
B. Add the attribute to Page Designer
C. Rebuild the search index
D. Add the attribute to ocapi.json write_attributes

15) Where are storefront search refinements (facets) configured? (Select one)
A. Merchant Tools > Search > Search Refinements
B. Merchant Tools > SEO > URL Rules
C. Administration > Sites
D. Content > Assets

16) A one‑way synonym is needed (“sneakers” → “running shoes,” but not vice versa). Where do you configure it? (Select one)
A. Merchant Tools > Search > Dictionaries
B. Merchant Tools > Search > Search Refinements
C. Administration > Sites
D. Page Designer

17) You need to show a new PDP attribute value. Which two layers are commonly updated? (Select two)
A. Product model decorators/factory (to expose data)
B. PDP ISML template (to render)
C. services.json
D. ocapi.json

18) Where do you configure log categories and appenders? (Select one)
A. BM > Administration > Operations > Logging
B. Code Versions
C. Page Designer
D. ocapi.json

19) A marketer wants to assemble landing pages from reusable components. Which feature is most appropriate? (Select one)
A. Page Designer
B. URL Rules
C. OCAPI Shop
D. Site Preferences

20) Search results decreased after enabling a new locale. Which two are likely causes? (Select two)
A. Missing localized values for searchable attributes
B. Search index not rebuilt after data change
C. Missing services.json
D. Cartridge path missing the base cartridge

21) You must expose a custom object through OCAPI Data. Which two steps are required? (Select two)
A. Update ocapi.json with read/write permissions and attribute lists
B. Create client credentials and map to that ocapi.json setting
C. Create a new cartridge
D. Rebuild the search index

22) Logging best practice in production is: (Select one)
A. Use Logger categories with INFO/WARN/ERROR; use DEBUG selectively
B. Use System.out.println for simplicity
C. Log everything at DEBUG to be safe
D. Disable logs to reduce overhead

23) Where do you change the site’s default currency and taxation settings? (Select one)
A. Administration > Sites > Manage Sites > [Site] > Settings
B. Merchant Tools > Search
C. Merchant Tools > SEO
D. Administration > Roles

24) To change copy for availability labels on PLP/PDP, which two places are typical? (Select two)
A. templates/resources/*.properties
B. ISML templates
C. ocapi.json
D. dw.json

Section C: Controllers, ISML, Forms, Hooks, Services (12)
25) Which approach keeps controllers maintainable? (Select one)
A. Keep controllers thin; move domain logic into helpers/decorators/factories
B. Put most logic in ISML
C. Put all logic in controllers
D. Use only JSON responses

26) Which directive enables cacheable template fragments? (Select one)
A. iscache
B. isif
C. isloop
D. isdecorate

27) Proper CSRF handling for forms is: (Select one)
A. Generate token on GET; validate on POST via csrfProtection
B. Only rely on HTTPS
C. Not necessary in SFRA
D. Configure in ocapi.json

28) A route returns JSON. Which two are correct? (Select two)
A. Set Content‑Type to application/json
B. Respond using res.json or by writing a JSON string
C. Render ISML then convert to JSON
D. Must disable caching globally

29) You need to customize pricing without editing base controllers. What should you use? (Select one)
A. Hook extension points (pricing/tax)
B. Page Designer
C. URL Rules
D. Site preference only

30) A PLP calls a synchronous service per item. Which two improvements help? (Select two)
A. Use Service Framework with timeouts and a circuit breaker
B. Batch/caching results to avoid N+1 calls
C. Move service calls into ISML
D. Use System.out.println for timing

31) To localize text, use: (Select two)
A. templates/resources/*.properties
B. Resource.msg/Resource.msgf helpers
C. ocapi.json
D. services.json

32) A remote include shows stale promo content. What is the likely fix? (Select one)
A. Add vary keys (basket/promo/customer) or disable caching for that include
B. Disable all template caching
C. Change code version name
D. Increase log level to DEBUG

33) Caching a personalized Shop API response safely requires: (Select one)
A. No cache, or cache with vary on customer group/locale/currency
B. Global cache with no vary
C. CDN cache only
D. Response cache only

34) Your service sometimes returns HTTP 200 with an application error in the body. Proper handling is: (Select one)
A. Treat 200 as success; ignore body
B. Parse the body and evaluate domain status fields
C. Retry for one hour
D. Switch to SOAP

35) For handling PII in form submissions, which two are correct? (Select two)
A. Minimize and encrypt sensitive fields where possible
B. Restrict OCAPI Data access to least privilege
C. Log raw PII payloads for debugging
D. Use GET to avoid CSRF

36) A controller must output a large CSV. Best approach is: (Select one)
A. Stream incrementally to the response with appropriate headers
B. Build the entire CSV in memory first
C. Use ISML to render CSV
D. Print to System.out

Section D: OCAPI, Jobs, Integrations, Data (12)
37) To allow baskets via OCAPI Shop, you must: (Select two)
A. Configure ocapi.json Shop permissions for baskets with allowed attributes
B. Map a client ID/secret to that ocapi.json setting
C. Create a new code version
D. Add a Page Designer component

38) A nightly job imports inventory and reindexes search. Which two steps are typical? (Select two)
A. Script step to import inventory
B. System step to trigger delta/full indexing
C. Disable CSRF
D. Rename the code version

39) Which inbound folders are commonly used for imports? (Select two)
A. /impex/src/
B. /impex/src/instance/
C. /versioned/cartridges/
D. /static/default/

40) Two jobs sometimes collide updating the same records. Which approach helps? (Select two)
A. Introduce locking/serialization or mutually exclusive schedules
B. Add retries with exponential backoff
C. Disable all logs
D. Use ISML for synchronization

41) Least‑privilege OCAPI Data access for orders should include: (Select two)
A. Restrict read_attributes to just required fields
B. Dedicated client credentials per integration
C. One client shared by all partners
D. Expose all fields for flexibility

42) To rotate a service credential without downtime, which two steps help? (Select two)
A. Add a new credential/profile, cut over, then retire old
B. Hardcode the new secret into code constants
C. Support overlapping keys if the upstream allows
D. Stop traffic entirely during rotation

43) A robust synchronous integration should include: (Select two)
A. Short timeouts and a circuit breaker
B. Retries with exponential backoff for transient failures
C. Always log full request/response payloads
D. Never use caching

44) Product deltas arrive hourly. Which indexing policy is most efficient? (Select one)
A. Delta reindex after each import
B. Full reindex every hour
C. Weekly reindex
D. No reindex required

45) To write to a custom object via Data API, you need: (Select two)
A. ocapi.json write permissions and write_attributes for those fields
B. Client credentials mapped to that ocapi.json setting
C. A new code version
D. Search refinements

46) Two job steps update the same object set and collide. What’s the remedy? (Select one)
A. Locking/serialization or mutually exclusive windows
B. Disable loggers
C. Add more remote includes
D. Global response cache

47) Prevent sensitive token leakage from service logs by: (Select one)
A. Redacting/masking in the response parser; avoid logging bodies unless masked
B. Printing to System.out
C. Using DEBUG always
D. Disabling the service

48) A Shop API endpoint varies by pricebook and locale. Safe caching strategy is: (Select one)
A. No cache or cache with appropriate vary keys (price group/locale)
B. Global cache
C. CDN cache with no vary
D. App cache only

Section E: Performance, Caching, Troubleshooting (12)
49) To reduce PDP time‑to‑first‑byte, which two are recommended? (Select two)
A. Precompute heavy fields in decorators; avoid per‑request blocking calls
B. Cache static fragments with iscache and proper vary
C. Disable all caching
D. Force OCAPI for all pages

50) Profiler shows heavy spend on per‑tile service calls. Which two mitigations help most? (Select two)
A. Batch/cache calls to avoid N+1 patterns
B. Move computation offline into jobs; decorate from stored values
C. Add TRACE logs globally
D. Use remote includes for each tile

51) After deploy, a page remains stale. Which two actions are typical? (Select two)
A. Clear application cache
B. Invalidate iscache fragments for affected templates
C. Rebuild the whole index on every request
D. Change code version label

52) A large JSON export endpoint OOMs. Proper approach is: (Select one)
A. Stream JSON chunks to the response
B. Build the full JSON in memory
C. Use ISML
D. Print objects to logs

53) Cache correctness issues on multilingual/multicurrency sites often stem from: (Select two)
A. Missing vary‑by‑locale/currency
B. Using global cache with no vary
C. Using decorators
D. Using Resource.msg

54) New locale shows English strings. Which two fixes are standard? (Select two)
A. Add locale‑specific properties under templates/resources
B. Use Resource.msg/Resource.msgf to fetch strings
C. Update ocapi.json
D. Switch code versions

55) A route frequently times out on a downstream service. Which three resilience techniques are best practice? (Select three)
A. Short timeouts (fail fast)
B. Retries with exponential backoff
C. Circuit breaker
D. Add more synchronous calls

56) After a release, PDP TTFB increased by 220ms. Which three diagnostics help? (Select three)
A. Compare profiler traces for that route before/after
B. Add targeted timing logs around suspect code
C. Diff changes in services/decorators/hooks
D. Disable all logs permanently

57) To reduce ISML template CPU time, which two are recommended? (Select two)
A. Precompute data in helpers/decorators; pass view‑ready data
B. Cache static fragments with iscache
C. Add blocking HTTP calls in templates
D. Expand loops in templates for compute

58) A Page Designer component shows wrong currency when cached. What should you do? (Select one)
A. Add vary‑by‑currency to the cached fragment
B. Use ocapi.json
C. Disable CSRF
D. Rebuild the catalog

59) To prevent duplicate POST effects (e.g., double‑click), which two mitigations help? (Select two)
A. Idempotency keys with server‑side deduplication
B. Disable the submit button after first click on the client
C. Use GET instead of POST
D. Disable CSRF

60) Catalog import and delta reindex sometimes overlap and fail. What’s the best remedy? (Select one)
A. Coordinate schedules and implement locking; add retries/backoff
B. Disable indexing permanently
C. Increase logs to DEBUG always
D. Change code version

Answer Key and Explanations
1) B — A valid cartridge folder must contain a cartridge/ subfolder to be selectable.
2) A, D — Match relative path/name and ensure custom cartridge precedes base.
3) B — Deployed code lives at /versioned/cartridges/<code-version>/cartridges.
4) B — Path precedence is left‑to‑right; first match wins.
5) A, B — Clear app cache and invalidate iscache to surface new templates.
6) A — Code Versions UI controls active version selection.
7) B — dw.json configures IDE target and version for uploads.
8) B — Path is site‑level; handle locale variance in templates/models.
9) B — Ensure the cartridge is in the site path with correct ordering.
10) A — app_*.properties contains cartridge metadata.
11) A — Use server.middleware.https on routes that require HTTPS.
12) B — The leftmost cartridge with that route handles it.
13) A — Use Site Import & Export for inbound data files.
14) A, C — Mark searchable and rebuild index to take effect.
15) A — Refinements are configured under Search > Search Refinements.
16) A — Dictionaries support one‑way synonyms.
17) A, B — Extend model and update templates.
18) A — Logging config is managed under Admin > Operations.
19) A — Page Designer enables componentized page assembly.
20) A, B — Missing locale attributes or not reindexing reduces results.
21) A, B — ocapi.json permissions and client credentials are both required.
22) A — Use Logger with proper levels; keep DEBUG targeted.
23) A — Site Settings manage currency/taxation.
24) A, B — Properties and ISML typically drive label text.
25) A — Thin controllers; logic in helpers/decorators/factories.
26) A — iscache supports fragment caching in ISML.
27) A — CSRF token pattern (generate on GET; validate on POST).
28) A, B — Serve JSON with proper content type and JSON body.
29) A — Use hooks to introduce/override calculation logic.
30) A, B — Service Framework and batching/caching remove N+1 patterns.
31) A, B — Properties bundles and Resource helpers provide i18n.
32) A — Add vary for basket/promo/customer context or disable caching.
33) A — No cache or include appropriate vary keys for personalization.
34) B — Inspect application‑level status in the response to detect errors.
35) A, B — Limit and secure PII; least‑privilege OCAPI access.
36) A — Streaming avoids excessive memory usage.
37) A, B — Configure ocapi.json Shop + map client credentials.
38) A, B — Import via script; trigger indexing via system step.
39) A, B — impex src and src/instance are used for inbound files.
40) A, B — Locking/serialization and retries mitigate collisions.
41) A, B — Limit attributes, and use dedicated credentials.
42) A, C — Blue/green credentials or overlapping key windows.
43) A, B — Fail fast, retry transients, and protect with a circuit breaker.
44) A — Delta reindexing after imports is efficient.
45) A, B — Write permissions and client mapping are required.
46) A — Serialize access or separate windows to avoid conflicts.
47) A — Redact before logging; avoid logging sensitive bodies.
48) A — No cache or use vary by price group/locale.
49) A, B — Precompute and cache static fragments.
50) A, B — Batch/cache or precompute via jobs.
51) A, B — Clear application cache and template cache.
52) A — Stream JSON to avoid OOMs.
53) A, B — Missing varies or global cache lead to leakage/incorrectness.
54) A, B — Add locale bundles and use Resource helpers.
55) A, B, C — Short timeouts, retries with backoff, and circuit breaker.
56) A, B, C — Profiling, targeted timers, and code diffs isolate regressions.
57) A, B — Move logic out of templates and cache fragments.
58) A — Add vary‑by‑currency where cached.
59) A, B — Idempotency and UI prevention stop duplicates.
60) A — Coordinate and lock; use retries/backoff for robustness.