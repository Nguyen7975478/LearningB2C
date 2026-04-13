# Salesforce Certified B2C Commerce Developer — Practice Questions (Set 11)
Total: 60 questions, standard difficulty. Each question indicates how many answers to select. An answer key with concise explanations is at the end.

Section A: Setup, Code Versions, Cartridges (12)
1) A custom cartridge was uploaded but its controllers still don’t resolve. What should be checked first? (Select one)
A. Page Designer page types
B. Site cartridge path includes the cartridge and ordering
C. Search refinement menus
D. Service profiles

2) The correct WebDAV path for uploading a cartridge to a specific code version is: (Select one)
A. /impex/src/
B. /versioned/cartridges/<code-version>/cartridges
C. /static/default/
D. /on-demand/tmp/

3) An ISML override is not taking effect. Which two conditions are likely missing? (Select two)
A. Override placed at same relative path/name as base
B. Custom cartridge has higher priority (before app_storefront_base)
C. ocapi.json includes the template path
D. A dedicated code version alias is required

4) Which statement about site code version is accurate? (Select one)
A. One global code version per instance
B. Each site references its own code version under Site Settings
C. Code version is set only at Organization level
D. Code version is inferred from cartridge path

5) After switching code versions, old templates still display. Which two steps help? (Select two)
A. Clear application cache
B. Invalidate iscache fragments
C. Rebuild catalogs
D. Reset synonyms

6) Cartridge order matters primarily because: (Select one)
A. It controls OCAPI quotas
B. It determines left-to-right resolution precedence for controllers/templates/scripts
C. It enables CSRF middleware
D. It changes CDN TTLs

7) Where do you select the active code version? (Select one)
A. BM > Administration > Site Development > Code Versions
B. BM > Merchant Tools > Search
C. BM > Page Designer
D. BM > SEO

8) What does dw.json configure? (Select one)
A. OCAPI Data permissions
B. IDE/WebDAV connection info and target code version
C. Page Designer policies
D. Search ranking

9) A business asks for different cartridge paths per locale. Proper guidance is: (Select one)
A. Supported per-locale
B. Not supported; implement via code/templates with one site-level path
C. Use ocapi.json per-locale
D. Use services.json per-locale

10) Which file holds cartridge metadata like id/description? (Select one)
A. templates/resources/*.properties
B. app_*.properties
C. ocapi.json
D. services.json

11) Enforce HTTPS on select routes using: (Select one)
A. server.middleware.https
B. ocapi.json
C. Page Designer
D. services.json

12) Two cartridges define the same route; which one runs? (Select one)
A. The one with newest timestamp
B. The first (leftmost) in site path
C. The rightmost in site path
D. Neither; platform errors

Section B: Business Manager, Search, Content, Logging (12)
13) Where do you import site data (catalogs/inventory)? (Select one)
A. BM > Merchant Tools > Site Import & Export
B. BM > Administration > Site Development > Code Versions
C. BM > SEO
D. BM > Logs

14) To make an attribute searchable, which two are required? (Select two)
A. Mark the attribute searchable
B. Add it to Page Designer
C. Rebuild the search index
D. Add to ocapi.json read_attributes

15) Where are search refinements configured? (Select one)
A. Merchant Tools > Search > Search Refinements
B. Merchant Tools > SEO
C. Administration > Sites
D. Content > Assets

16) Define a one-way synonym “parka → winter coat” here: (Select one)
A. SEO > Redirects
B. Search > Dictionaries (one-way)
C. Search > Refinements
D. Site Preferences

17) To render a new PDP attribute, which two places are updated? (Select two)
A. Product decorators/factory
B. PDP ISML template
C. ocapi.json
D. services.json

18) Configure log categories/appenders at: (Select one)
A. BM > Administration > Operations > Logging
B. ocapi.json
C. services.json
D. dw.json

19) To let marketers build pages from components, use: (Select one)
A. Page Designer
B. URL Rules
C. OCAPI Shop
D. Synonyms

20) After enabling a locale, search results dropped. Likely two causes: (Select two)
A. Missing localized values for searchable attributes
B. Forgot to reindex
C. Missing cspTrustedSite
D. Wrong code version

21) To expose a custom object via Data API, do which two? (Select two)
A. Update ocapi.json with read/write and attributes
B. Create and map OCAPI client credentials
C. Create a new code version
D. Add a Page Designer type

22) Production logging best practice is: (Select one)
A. Logger with categories at INFO/WARN/ERROR; DEBUG for targeted troubleshooting
B. System.out.println everywhere
C. Always DEBUG
D. Disable logging

23) Site default currency/taxation is configured at: (Select one)
A. Administration > Sites > Manage Sites > [Site] > Settings
B. Search > Dictionaries
C. SEO > URL Rules
D. Services > Profiles

24) To change text on availability messages, typically update: (Select two)
A. templates/resources/*.properties
B. ISML templates
C. ocapi.json
D. dw.json

Section C: Controllers, ISML, Forms, Hooks, Services (12)
25) Maintainable controller design: (Select one)
A. Thin controllers; push domain logic to helpers/decorators/factories
B. Put logic in ISML
C. All logic in controllers
D. Avoid services

26) Directive to cache template fragments: (Select one)
A. iscache
B. isif
C. isloop
D. isdecorate

27) CSRF handling requires: (Select one)
A. Generate token on GET and validate on POST with csrfProtection
B. HTTPS only
C. None in SFRA
D. ocapi.json

28) For a JSON route, which two steps are correct? (Select two)
A. Set Content-Type to application/json
B. Use res.json or write JSON string
C. Render ISML then convert to JSON
D. Disable caching globally

29) Modify pricing behavior without editing base controllers using: (Select one)
A. Pricing/tax hook extension points
B. Page Designer
C. URL Rules
D. Site preference only

30) A list page performs per-item HTTP calls. Two improvements: (Select two)
A. Use Service Framework with timeouts and circuit breaker
B. Batch/cache to avoid N+1
C. Use ISML for calls
D. System.out.println timing

31) Localize UI text using: (Select two)
A. templates/resources/*.properties
B. Resource.msg/Resource.msgf
C. ocapi.json
D. services.json

32) A remote include shows stale promo state. Fix: (Select one)
A. Add vary keys (basket/promo/customer) or disable include cache
B. Disable all caching
C. Change code version
D. Switch to GET

33) For personalized Shop API responses, safe caching is: (Select one)
A. No cache or cache with vary (customer group/locale/currency)
B. Global cache with no vary
C. CDN-only cache
D. Response cache only

34) Service returns 200 with error in body. Correct handling: (Select one)
A. Treat 200 as success
B. Parse body for domain status/error and handle accordingly
C. Timeout instead
D. Retry forever

35) Storing PII requires which two? (Select two)
A. Minimize/encrypt sensitive fields
B. Restrict OCAPI Data access (least privilege)
C. Log raw PII at DEBUG
D. Use GET to avoid CSRF

36) Large CSV export route should: (Select one)
A. Stream incrementally with appropriate headers
B. Build full CSV in memory
C. Use ISML
D. Print to System.out

Section D: OCAPI, Jobs, Integrations, Data (12)
37) To allow baskets via OCAPI Shop, do which two? (Select two)
A. ocapi.json Shop permissions with attributes
B. Map client ID/secret to that setting
C. Create new code version
D. Add PD component

38) Nightly job imports inventory and reindexes search. Typical steps: (Select two)
A. Script step for import
B. System step to trigger delta/full index
C. Disable logs
D. Restart code version

39) Inbound import folders include: (Select two)
A. /impex/src/
B. /impex/src/instance/
C. /versioned/cartridges/
D. /static/default/

40) Import job intermittently hits file locks. Mitigation: (Select two)
A. Retry with exponential backoff
B. Coordinate schedules and locks
C. Add TRACE logs only
D. Run via controller

41) Least-privilege OCAPI Data on orders requires: (Select two)
A. Restrict read_attributes to required fields
B. Dedicated credentials per integration
C. One shared client for all partners
D. Expose all fields

42) Rotate a service credential without downtime by: (Select two)
A. Adding new credential/profile and cutting over
B. Hardcoding secret
C. Supporting overlapping keys if allowed
D. Stopping traffic

43) Robust synchronous integration includes: (Select two)
A. Short timeouts and circuit breaker
B. Retries with backoff for transients
C. Always log full payloads
D. Never cache

44) Product deltas hourly. Best indexing policy: (Select one)
A. Delta index after each import
B. Full index hourly
C. Weekly index
D. No index

45) Write to a custom object via Data API requires: (Select two)
A. ocapi.json write with write_attributes
B. Client credentials mapped
C. A new code version
D. Search refinements

46) Two job steps collide updating same records. Remedy: (Select one)
A. Locking/serialization or exclusive windows
B. Disable logs
C. Remote includes
D. Global cache

47) Prevent token leakage from logs by: (Select one)
A. Redacting/masking tokens in parser; avoid logging bodies unless masked
B. System.out.println
C. DEBUG everywhere
D. Disable service

48) Shop API varies by price group and locale. Safe caching: (Select one)
A. No cache or cache with proper vary keys
B. Global cache
C. CDN no-vary
D. Response cache only

Section E: Performance, Caching, Troubleshooting (12)
49) Reduce PDP TTFB via: (Select two)
A. Precompute heavy fields in decorators
B. Cache static fragments with iscache and proper vary
C. Disable cache
D. Use OCAPI only

50) Profiler shows per-item service calls are heavy. Improve by: (Select two)
A. Batch/cache calls
B. Compute offline via jobs and decorate from storage
C. TRACE logging globally
D. Remote includes per tile

51) Stale content persists post-deploy. Likely actions: (Select two)
A. Clear application cache
B. Invalidate iscache fragments
C. Rebuild all indexes per request
D. Rename code version

52) Large JSON export OOMs. Correct pattern: (Select one)
A. Stream JSON chunks
B. Build full JSON in memory
C. Use ISML
D. Disable HTTPS

53) Cache correctness issues often stem from: (Select two)
A. Missing vary-by-locale/currency
B. Global cache with no vary
C. Using decorators
D. Using Resource.msg

54) New locale shows English strings. Fixes include: (Select two)
A. Add locale properties under templates/resources
B. Use Resource.msg/Resource.msgf
C. Update ocapi.json
D. Switch code version

55) Route timeouts to downstream service. Best practices: (Select three)
A. Short timeouts (fail fast)
B. Retries with backoff
C. Circuit breaker
D. Increase synchronous calls

56) PDP slowed after release. Which three diagnostics help? (Select three)
A. Compare profiler traces before/after
B. Add targeted timing logs
C. Diff services/decorators/hooks changes
D. Disable logs permanently

57) Lower ISML CPU by: (Select two)
A. Precompute in helpers/decorators
B. Cache static fragments
C. Add HTTP calls in templates
D. Heavy loops in ISML

58) PD component shows wrong currency when cached. Fix: (Select one)
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
A. Coordinate schedules with locks and retries/backoff
B. Disable indexing
C. Add DEBUG logs
D. Change code version

Answer Key and Explanations
1) B — Check site cartridge path and ordering.
2) B — Deployed code resides under /versioned/.../cartridges.
3) A, B — Match relative path and ensure higher priority than base.
4) B — Each site independently references a code version.
5) A, B — Clear app cache; invalidate template cache.
6) B — Left-to-right path precedence controls resolution.
7) A — Active version is managed in Code Versions.
8) B — dw.json configures IDE/WebDAV deployment target.
9) B — Single site-level path; handle locale within code/templates.
10) B — app_*.properties holds cartridge metadata.
11) A — server.middleware.https enforces HTTPS.
12) B — The leftmost cartridge wins.
13) A — Use Site Import & Export for inbound data.
14) A, C — Mark searchable and reindex.
15) A — Refinements are configured under Search.
16) B — Use one-way synonyms in Dictionaries.
17) A, B — Extend model and update templates.
18) A — Configure logging in Admin > Operations.
19) A — Page Designer enables marketer-driven pages.
20) A, B — Missing localized values or reindex issues.
21) A, B — ocapi.json + mapped client credentials.
22) A — Use Logger with appropriate levels; DEBUG sparingly.
23) A — Site Settings define currency/taxation.
24) A, B — Properties and templates control copy.
25) A — Keep controllers thin; push logic down.
26) A — iscache supports fragment caching.
27) A — CSRF: generate token on GET, validate on POST.
28) A, B — Use JSON content type and res.json/write.
29) A — Use pricing/tax hooks.
30) A, B — Service Framework + batch/cache to avoid N+1.
31) A, B — Properties + Resource helpers for i18n.
32) A — Add vary or disable include cache.
33) A — No cache or proper vary for personalization.
34) B — Parse application status and handle errors.
35) A, B — Minimize/encrypt PII; enforce least privilege.
36) A — Stream CSV with proper headers.
37) A, B — OCAPI Shop + client mapping.
38) A, B — Import via script; trigger indexing via system step.
39) A, B — impex src and src/instance are typical.
40) A, B — Backoff and schedule/lock coordination.
41) A, B — Restrict attributes; dedicated credentials.
42) A, C — New credential and overlap keys if allowed.
43) A, B — Fail fast, retry transients, protect with CB.
44) A — Delta indexing for frequent imports.
45) A, B — Write permissions/attributes and client mapping.
46) A — Serialize access or separate windows.
47) A — Redact/mask and avoid logging bodies.
48) A — No cache or vary with price group/locale.
49) A, B — Precompute and cache static parts.
50) A, B — Batch/cache or precompute offline.
51) A, B — Clear app cache and invalidate iscache.
52) A — Stream JSON to avoid OOM.
53) A, B — Missing vary or global cache cause issues.
54) A, B — Add locale bundles; use Resource helpers.
55) A, B, C — Short timeouts, backoff retries, and CB.
56) A, B, C — Profiling + timing + diffs isolate regressions.
57) A, B — Precompute and cache fragments.
58) A — Add vary-by-currency where cached.
59) A, B — Idempotency and UI disable.
60) A — Coordinate schedules, locks, and backoff.