# Configure Hostname Mapping Rules
https://trailhead.salesforce.com/content/learn/modules/b2c-hostname-aliases/b2c-hostname-alias-configure-mapping-rules

## English

## Learning Objectives
After completing this unit, you’ll be able to:
- Explain the purpose of mapping rules in the alias file.
- Give two reasons for adding mapping rules to a host alias file.
- Explain how B2C Commerce handles duplicate URL mappings.
- List three areas to check in your alias file to ensure it’s valid JSON.

## Why mapping rules (purpose)
- Mapping rules let you map and redirect shoppers to:
    - a proper hostname
    - a specific pipeline
    - a landing page
- Real-world configuration can mix mappings and redirects per event/site.
- You need at least one mapping rule per hostname/domain for which you have storefront content.
- DNS must contain IP addresses corresponding to IP addresses on the production instance.

Sample mapping rule shown:
- `"www.cloudkicks.com" : [{"pipeline": "Home-Show" }],`

## Redirect common hostname to proper hostname
Example shown:
- `"cloudkicks.com": [ { "host": "www.cloudkicks.com", "path":"/home" }]`
  Behavior explained:
- Host-only request `cloudkicks.com` redirects to `www.cloudkicks.com/home`
- Requests like `cloudkicks.com/mens` redirect to `www.cloudkicks.com/mens` (path preserved)

## Mapping rule syntax (elements and meanings)
The unit presents an example mapping rule containing attributes and explains each:

- `"apply-to-host-only-request-with-params":"true"`
    - Default: B2C Commerce processes redirect functionality on host-only requests with parameters.
    - When true: disables default handling; forwards requests to defined pipeline; parameters populated in memory.

- `"name": "mobile"`
    - Documentation only; not interpreted by the system.

- `"if-agent-contains": ["iphone","ipod"]`
    - Applies rule to matching user agents.
    - JSON has no ELSE inside one block; create another block for regular browsers.

- `"if-site-path": "DE"`
    - Important: B2C Commerce recognizes only `name`, `locale`, `pipeline`, `params` and ignores `host`, `path`, `if-agent-contains` when using this property for URL generation.
    - During URL generation, system uses first mapping rule that matches hostname and locale.
    - If matching rule specifies `if-site-path`, B2C Commerce adds the site path to generated URL.

- `"host": "m.cloudkicks.com"`
    - Redirect destination host.
    - Caution: specifying both `host` and `pipeline` can be unclear; prefer `pipeline` when you must choose.

- `"path": "index.html"`
    - Used for permanent 301 redirect; requires `host`.
    - For host-only request: host + path is used.
    - For requests with a path already: old request path is appended to new host (and `path` behaves as described for host-only only).

- `"pipeline": "Summer-Start"`
    - Pipeline mapping when no host redirect is provided; can be combined with locale/params to control context.

- `"locale": "de"`
    - Sets locale for mapped requests (example `/us/mens` pattern).

- `"params": {...}`
    - Adds parameters only when rule matches exactly as requested (example: `/us/` yes, `/us/mens` no).

Note: unit references Infocenter for complete list of mapping rule attributes.

## Debug the alias file (JSON linting advice)
- Hostname alias syntax is inspired by JSON but not strictly JSON.
  To debug as valid JSON, temporarily:
- Use colons `:` instead of equals `=` (equals supported by hostname syntax but invalid JSON).
- Remove comments (invalid JSON).
- Remove trailing commas after host entries (invalid JSON).
  Important: commas may be required by the B2C Commerce hostname file syntax, so put them back after debugging.
- Validate with a tool like **JSONlint** (do not rely on trial-and-error in Business Manager).
- If alias file contains JSON errors, B2C Commerce keeps using the previous good configuration and won’t save invalid configuration.

## Test time (local hosts file approach)
When you can’t register DNS for test environments quickly:
1) Determine IP address of test system.
2) Open command line.
3) Run `nslookup cloudkicks.domain.demandware.net`.
4) Add hostname mapping to local hosts file (typically `/etc/hosts`).
5) Verify by browsing hostnames pointing locally to the instance.
   Best practice: test on a development instance.

## Scenarios
### Scenario 1: Control site path trailing slash
- Configure preferred host settings:
    - `"site-path-trailing-slash": "yes"`
- Example rules for locales:
    - `en` redirects to `/en/`
    - `de` redirects to `/de` (no trailing slash)
      Example redirect outcomes:
- `www.cloudkicks.com/en` → `www.cloudkicks.com/en/`
- `www.cloudkicks.com/de/` → `www.cloudkicks.com/de`

### Scenario 2: Redirect alternate URL to preferred domain
- Redirect `cloudkicks.com/*` → `www.cloudkicks.com/*` via 301.

## Duplicates (SEO risk + platform handling)
- Duplicate content across multiple URLs reduces search ranking.
- B2C Commerce automatically handles most duplicate URL mappings.
- For alias file host-only rules and site paths, you can add mappings for automatic redirects by:
    - using duplicate resource rules via B2C Commerce Script API
    - defining pipelines with duplicate entry points/contextual equals
    - defining the preferred destination
- B2C Commerce generates URLs using the first applicable mapping.

## Create URL rules to avoid duplicate content (entry-point settings)
- Mark a pipeline (example: `StartNode`) to be checked for duplicate URLs.
- Redirect happens automatically if URL is not the preferred destination.
- Destination types:
    - host
    - site-path
    - pipeline
      (host and site-path require corresponding rules)
      Example config shown includes:
- `"entry-point-pipeline": [ "Home-Show" ]`
- `"entry-point-destination": [ "host", "site-path", "pipeline" ]`
  Result described:
- Requests identifying `StartNode` are redirected to the host-only destination, and the host-only URL invokes the pipeline.

## Tiếng Việt

## Learning Objectives
Sau khi hoàn thành unit, bạn có thể:
- Giải thích mục đích mapping rules trong alias file.
- Nêu 2 lý do cần mapping rules.
- Giải thích B2C Commerce xử lý duplicate URL mappings thế nào.
- Liệt kê 3 điểm cần check để alias file là valid JSON.

## Vì sao cần mapping rules
- Mapping rules cho phép map/redirect shoppers tới:
    - proper hostname
    - pipeline cụ thể
    - landing page
- Cần ít nhất 1 mapping rule cho mỗi hostname/domain có storefront content.
- DNS phải có IP trùng với IP trên production instance.

Ví dụ:
- `"www.cloudkicks.com" : [{"pipeline": "Home-Show" }],`

## Redirect hostname thường dùng sang proper hostname
Ví dụ:
- `"cloudkicks.com": [ { "host": "www.cloudkicks.com", "path":"/home" }]`
- `cloudkicks.com` → `www.cloudkicks.com/home`
- `cloudkicks.com/mens` → `www.cloudkicks.com/mens`

## Syntax mapping rule (các thuộc tính và ý nghĩa)
- `apply-to-host-only-request-with-params`
- `name` (documentation only)
- `if-agent-contains`
- `if-site-path` (ảnh hưởng URL generation; chỉ recognize name/locale/pipeline/params trong ngữ cảnh đó)
- `host`, `path` (301 redirect behavior)
- `pipeline`, `locale`, `params`

## Debug alias file (JSONlint)
- Syntax “inspired by JSON” nhưng không strict JSON.
  Debug JSON:
- dùng `:` thay `=`
- remove comments
- remove trailing commas (rồi thêm lại nếu hostname syntax cần)
- validate bằng **JSONlint**
- Nếu lỗi JSON: hệ thống giữ cấu hình cũ, không save cấu hình lỗi.

## Test time (local hosts)
- nslookup + map `/etc/hosts` để test hostnames trỏ vào instance; best practice test trên development.

## Scenarios
- Control trailing slash theo site-path/locale.
- Redirect alternate domain sang preferred domain.

## Duplicates
- Duplicate URLs giảm ranking.
- B2C Commerce tự xử lý phần lớn duplicates; với host-only/site-path có thể cấu hình redirect thêm.
- Generate URL theo rule đầu tiên match.

## Create URL rules (entry-point)
- Mark pipeline (StartNode) để check duplicates; redirect về preferred destination (host/site-path/pipeline).