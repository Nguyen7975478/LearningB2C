# Salesforce Certified B2C Commerce Developer — Hard Practice Set (Set 3)
Total: 60 advanced questions. Each question specifies the number of correct options. Answers with detailed explanations are provided after each section.

Set H1: Code Versioning, Cartridge Resolution, and SFRA Internals (12)
1) You deploy two custom cartridges that both define the same controller route path. Cartridge order is: app_custom_extA, app_custom_extB, app_storefront_base. Which route executes when the storefront requests that path? (Select one)
A. The route from app_storefront_base
B. The route from app_custom_extB
C. The route from app_custom_extA
D. The platform throws an ambiguity error

2) A site references code version “23.10.1” in Settings. You deploy new code to “23.12.0” and change the site’s referenced version, but overrides don’t appear. Which two actions are most likely required? (Select two)
A. Clear application cache and any relevant template caches
B. Rebuild search indexes
C. Update cartridge path under the site to include new cartridges
D. Restart the application servers

3) You need to validate which cartridge in the path is resolving a given ISML template. What’s the most precise approach? (Select one)
A. Inspect server logs for a template load line
B. Temporarily add a unique comment/string to each candidate template and reload the page
C. Change the template name in the base to force an error
D. Enable global DEBUG and check BM Profiler

4) In SFRA, which statement about middleware ordering is most accurate? (Select one)
A. Middleware order doesn’t matter; all are parallelized
B. Middleware executes in the order registered on the route; earlier middleware can short-circuit
C. All middleware executes after the main route function
D. Middleware is defined only in server.js, not per-route

5) You added a decorator that sets product.custom.badge = 'VIP' during model build. On PDP, some products render the badge, others don’t, though all have the attribute value. Which two causes are likely? (Select two)
A. Route-level cache not varying by product ID
B. iscache fragment without vary keys including product ID
C. Product attributes not persisted yet
D. Missing CSRF token

6) You extend app_storefront_base Product model via a factory that chains base and custom decorators. A teammate moves the custom decorator to run before the base builder. What subtle issue might occur? (Select one)
A. Decorator not executed due to hook conflicts
B. Decorator operates on incomplete base model, missing fields it expects
C. Infinite recursion in factory
D. No impact; decorator order is irrelevant

7) A controller uses a remote include to render a cart mini-summary. Occasionally, users see stale totals after promotions change. Which two misconfigurations can cause this? (Select two)
A. Remote include cached without vary-by-promotion state
B. Response cache on parent route not varying by basket UUID
C. Missing ocapi.json Shop settings
D. Logger mis-level (INFO vs DEBUG)

8) A site defines a cartridge path at the Organization level and another at the Site level. Which statement is correct? (Select one)
A. Only Organization-level path is used
B. The two are merged; Site-level entries take precedence order-wise
C. The platform alternates between them per request
D. Site-level path is ignored if Organization-level exists

9) You introduce a new code version and keep the same cartridge path. A single custom script resolves differently than before. Which is the best first step? (Select one)
A. Clear logs
B. Compare directory structures and ensure the script exists in the same cartridge location
C. Rebuild caches
D. Change code version label

10) In SFRA, which is the most accurate description of the role of controllers vs. helpers/decorators? (Select one)
A. Controllers should hold all business logic; helpers handle I/O only
B. Helpers/decorators encapsulate business rules; controllers orchestrate request handling and rendering
C. Decorators are for CSS; helpers are for translations
D. Controllers must return JSON only; helpers render ISML

11) Your custom storefront experience adds a controller that returns JSON for client-side rendering. It is cached at the CDN with no vary keys. Which two risks are introduced? (Select two)
A. Leaking shopper-specific data across users
B. Increased server CPU per request
C. Serving outdated or mismatched personalization
D. Breaking OCAPI rate-limits

12) After adding a cartridge with a higher path priority, a few Page Designer components stop rendering. What is the MOST likely reason? (Select one)
A. The new cartridge shadows template or script names expected by PD components
B. CDN disabled
C. Missing ocapi.data write permission
D. Log level is too low

Set H2: Search, Indexing, and Data Model Nuances (12)
13) A new searchable product attribute is defined and populated. The attribute is still not searchable after a reindex. Which two issues are likely? (Select two)
A. The attribute type is non-indexable (e.g., binary)
B. The attribute wasn’t added to the product type assigned to the SKUs
C. The attribute is localized, but values were uploaded only for the default locale while search uses another
D. Log appenders weren’t configured

14) Which approach yields the best recall for misspellings on popular search terms without over-matching? (Select one)
A. Add broad wildcard rules on all keywords
B. Use Dictionaries for synonyms and tune fuzzy matching thresholds
C. Disable stemming and rely on exact match
D. Rebuild the catalog nightly

15) You add a refinement definition but it does not appear on category pages. Which two steps are commonly missed? (Select two)
A. Assigning the refinement to the relevant search refinement menu
B. Rebuilding the search index to include the attribute
C. Adding the component to Page Designer
D. Creating a custom object

16) A merchandiser wants “color family” refinements grouped from granular colors (e.g., “navy,” “sky”) without changing source attributes. Which is the best approach? (Select one)
A. Create a classification catalog
B. Use search mapping rules to bucket attribute values into refinement groups
C. Add a new product attribute and backfill data manually
D. Use URL rules

17) Delta indexing is configured but new products aren’t appearing promptly. Which two misconfigurations commonly cause this? (Select two)
A. Missing trigger for delta indexing job step post-import
B. Attribute not marked searchable
C. CDN not purged
D. Remote include disabled

18) You need to expose a variant-level custom attribute in search facets. Which statement is accurate? (Select one)
A. Variant attributes cannot be used in refinements
B. Use search configuration that indexes variant attributes and map to refinements appropriately
C. Only master-level attributes are indexable
D. Requires OCAPI Data POST per product

19) A guided search page needs a custom sort by “margin” (computed server-side). Which two are best practices? (Select two)
A. Precompute and store margin in an indexable attribute updated by jobs
B. Compute margin in-template during render for each product in results
C. Implement a custom sort definition using the precomputed field
D. Use client-side JavaScript to reorder results after page load

20) A site has multi-locale catalogs. Searches in one locale return far fewer results than another. What are two likely causes? (Select two)
A. Missing localized attribute values for that locale
B. The site runs older SFRA
C. The tokenizer for that locale differs, resulting in stricter matching
D. Too many Page Designer components

21) Your relevance degraded after turning on aggressive stemming. What is the safest rollback? (Select one)
A. Disable stemming entirely and push to production immediately
B. Reduce stemming to a moderate level and re-evaluate with A/B testing and logs
C. Switch to wildcard-only search
D. Rebuild the catalog every hour

22) You introduced a “brand” synonym expansion that maps many unrelated terms. Which remediation is best? (Select one)
A. Convert the synonym set to one-way synonyms limited to high-precision expansions
B. Increase fuzzy distance
C. Delete all synonyms
D. Add redirect rules

23) You must make a new attribute searchable, sortable, and refinable. Which two steps are essential? (Select two)
A. Enable both searchable and sortable flags on the attribute definition
B. Add the attribute to “refinements” and to the sort definition
C. Add it to ocapi.json write_attributes
D. Replace the catalog

24) A custom index field inflates index size, slowing queries. Which optimizations help most? (Select two)
A. Reduce precision (e.g., truncate decimals) if exact precision is unnecessary
B. Store normalized values, not verbose text, if text is not required
C. Duplicate fields for safety
D. Increase log levels

Set H3: Controllers, Forms, Hooks, Services — Edge Cases (12)
25) A POST endpoint accepts JSON payloads and updates a custom object. Which two platform precautions are mandatory? (Select two)
A. CSRF protection on POST routes when relevant
B. Input validation and size limits; reject overly large or malformed payloads
C. Disable HTTPS to reduce latency
D. Write directly to logs for auditing PII

26) Your service call must fail fast during peak traffic to protect storefront performance. Which three configurations should you tune? (Select three)
A. Connection timeout and socket timeout
B. Circuit breaker thresholds and open-state duration
C. Retry count with exponential backoff
D. Disable all logging globally

27) You add a new Shop API OCAPI GET that is personalized. Which two requirements are critical for caching correctness? (Select two)
A. Do not cache or include vary keys (customer, locale, currency) where needed
B. If caching, include appropriate vary keys (customer group, locale, currency) or disable cache
C. Always set max-age=86400
D. Force CDN to ignore all headers

28) A teammate added pricing logic directly in the PDP controller that also returns JSON for headless clients. What’s the MAIN maintainability risk? (Select one)
A. JSON cannot carry prices
B. Duplication and divergence from the platform pricing hooks/decorators
C. Increased log size
D. Page Designer breaks

29) Your basket calculation relies on a hook that sometimes runs after totals are displayed. Which is the best fix? (Select one)
A. Move logic into ISML
B. Ensure hook is invoked in the calculation pipeline before totals are read; add deterministic ordering
C. Switch to remote include
D. Disable CSRF

30) A form persists PII to a custom object. Which two practices are mandatory? (Select two)
A. Log the raw PII payload for support
B. Validate and minimize PII storage; encrypt or avoid storing sensitive fields
C. Restrict OCAPI Data read/write to least privilege
D. Use GET for submissions to ease caching

31) Your service occasionally returns a 200 with an error payload. How do you robustly detect failure? (Select one)
A. Assume 200 is always success
B. Implement a response parser that reads application-level status codes and validates schema
C. Rely only on timeouts
D. Switch to SOAP

32) An OCAPI Data POST intermittently fails with 403 for a client. Which two root causes are likely? (Select two)
A. Missing or expired client credentials
B. Incorrect ocapi.json write_attributes for the payload fields
C. CDN cache is stale
D. Log category disabled

33) A hook implementation requires sharing context between pre- and post-steps. Which technique is appropriate? (Select one)
A. Write to a global variable in the cartridge
B. Attach needed metadata to the request object or a scoped object the framework passes
C. Use ISML to pass hidden fields
D. Save to a custom object on each call

34) Your checkout has a custom POST that sometimes receives duplicate submissions (e.g., double-click). Which two mitigations help? (Select two)
A. Idempotency key in payload and server-side dedupe
B. Client-side JS to disable the submit button after click
C. Increase cache time
D. Replace POST with GET

35) A controller needs to stream a large JSON export to the browser without exhausting memory. Which approach is best? (Select one)
A. Build a giant object and stringify at end
B. Stream chunks to the response writer incrementally and set appropriate headers
C. Write to ISML then convert to JSON
D. Use Logger to buffer chunks

36) Your custom object update job fails when running concurrently with another job that touches the same records. Best practice? (Select one)
A. Ignore; failures are fine
B. Introduce locking strategy or run jobs in mutually exclusive windows; add retries/backoff
C. Increase log verbosity
D. Use templates/resources to coordinate

Set H4: OCAPI, Security, Compliance, and Operations (12)
37) Which two statements reflect least-privilege OCAPI configuration? (Select two)
A. Expose only required resources and attributes in read/write sections
B. Grant global read/write to speed development
C. Separate client credentials for distinct integrations
D. Put secrets in cartridge constants.js

38) A new external client requires access to order data via OCAPI Data. Which three steps are essential? (Select three)
A. Create client ID/secret in BM and map to OCAPI settings
B. Allow order resources with explicit read_attributes in ocapi.json
C. Enable Shop API basket read/write
D. Restrict fields to non-PII where possible

39) Which two practices help avoid sensitive data in logs? (Select two)
A. Redact tokens and PII in service response parser before logging
B. Log entire payloads at DEBUG only
C. Disable logs entirely
D. Avoid logging request/response bodies unless masked or essential

40) Your hardening review flags that CSRF tokens sometimes aren’t validated on POST. What is the correct remediation? (Select one)
A. Switch POST to GET
B. Ensure csrfProtection.generateToken on GET render and csrfProtection.validateRequest on POST handlers
C. Add HTTPS and keep POSTs as-is
D. Disable caching

41) An auditor asks how you segregate duties between environments (dev/test/prod). Which two controls are relevant? (Select two)
A. Different OCAPI credentials and permissions per environment
B. Shared code versions across all environments
C. Restricted BM roles per environment and replication controls
D. Merge all logs into one bucket

42) You must rotate a service credential without downtime. Which two steps help? (Select two)
A. Create a new credential/profile, deploy code to reference it, cut over, then remove the old one
B. Change the password in code and redeploy
C. Schedule a maintenance window to stop traffic
D. Support both old and new keys for a transition period if the upstream allows it

43) A Shop API endpoint exposes personalized recommendations. What’s the safest caching strategy? (Select one)
A. Global cache with no vary
B. No cache or vary by customer (and locale/currency)
C. Cache at CDN for one day
D. Only rely on application cache

44) A partner integration requests broad OCAPI write on system objects. What is the recommended response? (Select one)
A. Approve to accelerate go-live
B. Grant least privilege with scoped resources/attributes and time-bound credentials
C. Deny all OCAPI
D. Ask them to use Page Designer

45) Your logs show frequent 401s on a service call from production only. Which two root causes are most likely? (Select two)
A. Wrong credentials or environment-specific key
B. Sandbox IP allow-lists applied to prod
C. Missing locale files
D. Incorrect HTTP method

46) A new security policy mandates masking card PANs end-to-end. Which two platform strategies are applicable? (Select two)
A. Do not store PANs; rely on tokenization via the PSP
B. Redact PANs in all logs and prevent them from being written by parsers
C. Save the last 8 digits in custom objects for analytics
D. Include full PAN in DEBUG for reconciliation

47) Your SiteGenesis legacy code uses XML pipelines and you must migrate a critical flow to SFRA. What’s the safest path? (Select one)
A. Rewrite entire site at once
B. Incrementally port flows to SFRA controllers/templates; keep legacy isolated; maintain feature parity with tests
C. Mix pipeline calls inside SFRA controllers
D. Use ISML to call pipelines

48) An OCAPI customization must run validation before writing to a system object. Where does the logic live? (Select one)
A. ocapi.json
B. A cartridge hook implementation registered in the path (e.g., beforePOST/validate)
C. services.json
D. Page Designer component

Set H5: Performance, Caching Patterns, Troubleshooting, and Ops (12)
49) A route renders a product grid and is slow under load. Which three improvements are typical? (Select three)
A. Introduce response cache with vary keys (locale, currency, page, filters)
B. Precompute expensive fields in decorators and avoid per-item service calls
C. Move all logic into ISML
D. Use batched lookups or cached services to avoid N+1 patterns

50) You discover double JSON serialization (stringified strings). What is the clean fix? (Select one)
A. Keep as-is; browsers parse twice
B. Ensure the controller passes a JS object to res.json once; avoid pre-stringifying
C. Render ISML instead
D. Cache longer

51) Profiler shows 40% of time in a synchronous service call on each tile of a product list. Which two remedies help? (Select two)
A. Aggregate calls: one request for many items or cache results
B. Increase log level to TRACE
C. Remove the call or precompute data offline via jobs and decorate from storage
D. Use more remote includes

52) Stale template content persists despite cache clears. Which two lesser-known causes exist? (Select two)
A. A remote include has its own cache not invalidated
B. CDN edge cache still serving old variant
C. Wrong ocapi.json client name
D. Logger buffering

53) A job fails only when catalog import and search delta reindex overlap. What’s the best mitigation? (Select one)
A. Disable delta indexing
B. Introduce job schedule coordination and lock mechanism; ensure order of operations
C. Increase retries to 100
D. Turn off logs

54) You need to diagnose a memory spike during peak hours. Which two tools/approaches are relevant? (Select two)
A. Analyze BM Profiler data and request logs for allocation hotspots
B. Add heap dumps via platform APIs
C. Add targeted logging and correlate with service latencies
D. Use ISML to render diagnostics to shoppers

55) The site occasionally returns 503 from a downstream service chain. Which three resilience techniques are most effective? (Select three)
A. Circuit breaker to shed failing dependency
B. Exponential backoff retries with jitter for transient failures
C. Graceful degradation (serve cached/placeholder content)
D. Add synchronous retries inside ISML

56) A controller endpoint must stream a CSV export of orders for one tenant while preventing cross-tenant leaks. Which two safeguards are required? (Select two)
A. Tenant scoping on queries and authorization checks
B. Caching without vary to increase speed
C. Content-Disposition and CSV headers; stream output
D. Use GET to skip CSRF

57) A Page Designer component shows wrong currency on cache hits. Which root cause is most likely? (Select one)
A. Missing vary-by-currency on the cached fragment
B. Wrong ocapi.data permissions
C. Controller name collision
D. No CDN

58) An integration needs at-least-once delivery semantics for outbound events. Which approach is best? (Select one)
A. Fire-and-forget synchronous POSTs
B. Queue events with IDs, retry on failure with dedupe on consumer side
C. Log-only and reprocess manually
D. Use templates/resources

59) The storefront performs excessive DDoS-like traffic to your service due to a client bug. Which two mitigations help quickly? (Select two)
A. Rate-limit/throttle at the Service Framework or edge
B. Increase timeouts
C. Cache negative responses appropriately (with short TTL)
D. Disable logs

60) A regression reduced PDP TTFB by 300ms. You must isolate the cause. Which three steps are effective? (Select three)
A. Compare profiler traces before/after by route
B. Diff code between versions and examine changed services/decorators
C. Clear all caches and assume it’s fixed
D. Add targeted timers/logs around suspect blocks to measure deltas

Answers and Explanations
1) C — Cartridge path is resolved left-to-right; first match wins (custom extA).
2) A, C — Clear caches; ensure the new version’s cartridges are referenced in the site path.
3) B — Tag each template candidate with a unique marker to observe which renders.
4) B — Middleware runs in registered order; earlier middleware can short-circuit.
5) A, B — Caching without proper vary keys can surface stale/other-product data.
6) B — Running custom decorator before base can access missing fields; order matters.
7) A, B — Missing vary on remote include or parent response cache causes stale totals.
8) B — Paths merge; Site-level ordering takes precedence.
9) B — Verify identical structure and presence of the script in the target version.
10) B — Keep controllers thin; push business logic to helpers/decorators.
11) A, C — Cached JSON without vary risks data leakage and stale personalization.
12) A — Higher-priority cartridge may shadow PD component templates/scripts.
13) A, B — Non-indexable type or attribute not attached to product type block search.
14) B — Use curated synonyms + tuned fuzzy thresholds to balance recall/precision.
15) A, B — Assign to menu and reindex so values are available.
16) B — Use mapping rules to bucket values into a refinement dimension.
17) A, B — Missing delta trigger or attribute not searchable prevents prompt appearance.
18) B — Variant attributes can be indexed and mapped to facets with proper config.
19) A, C — Precompute margin and define a sort using that field.
20) A, C — Missing localized values or tokenizer differences reduce results.
21) B — Taper stemming and validate via A/B and logs.
22) A — One-way, precise expansions prevent over-broad matching.
23) A, B — Enable attribute flags and include it in refinements/sort config.
24) A, B — Reduce precision and store normalized tokens to shrink the index.
25) A, B — Protect POSTs and validate inputs/size to prevent abuse.
26) A, B, C — Timeouts, CB, and backoff retries protect storefront under stress.
27) B — For personalized endpoints, either avoid caching or vary appropriately.
28) B — Logic diverges from hooks; duplication across outputs becomes fragile.
29) B — Ensure hook order executes before totals; deterministic placement.
30) B, C — Minimize/secure PII; lock down OCAPI permissions.
31) B — Parse payload-level status and schema to detect logical failures.
32) A, B — 403 often indicates auth or ocapi.json attribute permission issues.
33) B — Use request-scoped context; avoid globals and persistent writes.
34) A, B — Idempotency and UI disable prevent duplicate effects.
35) B — Stream chunks to the response; avoid building huge in-memory JSON.
36) B — Coordinate schedules/locks and implement backoff.
37) A, C — Least privilege and separate credentials are core; never hardcode secrets.
38) A, B, D — Credentials, ocapi.json, and PII minimization.
39) A, D — Redact/mask and avoid logging bodies unless essential.
40) B — Generate token on GET, validate on POST for CSRF protection.
41) A, C — Distinct creds/roles per environment; controlled replication.
42) A, D — Blue/green credentials or dual-key transition when supported.
43) B — No cache or vary by customer/locale/currency for personalization.
44) B — Grant only what’s needed, scoped and time-bound.
45) A, B — Wrong creds or IP allow-lists often cause 401 in prod.
46) A, B — Tokenize; redact/mask; never store full PANs.
47) B — Incremental migration with isolation and tests is safest.
48) B — OCAPI validation logic is in hook implementations in a cartridge.
49) A, B, D — Response caching, precompute, and batched/cached lookups help.
50) B — Avoid double-stringify; let res.json serialize once.
51) A, C — Batch/cache or precompute via jobs; remove per-item calls.
52) A, B — Remote include cache and CDN can serve stale content independently.
53) B — Coordinate schedules and locking to avoid overlaps.
54) A, C — Use profiler/log correlation; platform doesn’t provide heap dumps.
55) A, B, C — CB, retries with backoff, and graceful fallbacks; never retry in ISML.
56) A, C — Scope/authorize per tenant and stream CSV with correct headers.
57) A — Add vary-by-currency for correct cache partitioning.
58) B — Queue with IDs and dedupe for at-least-once semantics.
59) A, C — Rate-limit and cache negatives to absorb bursts.
60) A, B, D — Profiling deltas, code diff, and targeted timings isolate regressions.