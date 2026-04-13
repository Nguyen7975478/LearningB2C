# Install and Configure SFRA
Tham khảo: https://trailhead.salesforce.com/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra?trail_id=develop-for-commerce-cloud&trailmix_creator_id=xijo6a8wrw0ssnzmy8&trailmix_slug=salesforce-developer

## EN (A-level: detailed, faithful to unit Topics; keep technical terms)

### Learning Objectives
After completing this unit, you’ll be able to:
- Use Node Package Manager (npm) to install packages.
- Compile the JavaScript, style sheets, and fonts for SFRA.
- Upload the SFRA cartridges.
- Add data to SFRA.
- Index SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

---

## Install and Configure (initial setup steps)
- Vijay wants to configure his local machine to test/prototype SFRA customizations; he starts with Node.js and SFRA command-line tools, then Visual Studio Code and other tools/processes. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))
  Steps:
1) Open a command prompt and navigate to the `storefront-reference-architecture` directory.
2) Install latest Node.js **12.x** from the unit’s link.
    - Test: `node -v`
3) On Windows, install VS 2015 build tools:
    - `npm install --global --production windows-build-tools --vs2015`
4) Install SFRA modules:
    - `npm install`
    - Important notes:
        - SFRA depends on npm-managed modules.
        - Always run `npm install` after downloading a new SFRA version because dependencies can change. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

---

## SFRA Command-Line Tools (sgmf-scripts)
### Global installation (recommended on *nix or Windows)
- Install globally:
    - `npm install -g sgmf-scripts`
- Then you can run:
    - `sgmf-scripts --help` ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))
- Windows build tools must be global so npm can compile native Windows binaries.
- Mac note: if you get `EACCES`, the unit points to fixing permissions; global install is not required but avoids install steps for new cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### Local installation
- Install locally:
    - `npm install sgmf-scripts`
- Run via:
    - `node node_modules/sgmf-scripts --help` ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

---

## Visual Studio Code
- VS Code is a free editor for Windows/Linux/macOS; features mentioned include debugging, syntax highlighting, intelligent code completion, snippets, refactoring, and embedded Git. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))
  Steps:
1) Download and install VS Code.
2) In Extensions, install **ESLint**.
3) Open a folder containing your cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### Set Up and Enable Code Upload (dw.json + Prophet setting)
- Create `dw.json` in the directory containing cartridges (config structure shown):
```json
{
  "hostname": "<*.demandware.net (without https/http)>",
  "username": "<username>",
  "password": "<password>",
  "cartridge": ["cartridge A", "cartridge B"], //optional
  "code-version": "<code-version>"
}
```
- Enable upload:
    1) VS Code → Preferences → Settings
    2) Search `extension.prophet.upload.enabled`
    3) Set to `true`
    4) Restart VS Code ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### Set Up Code Debugging (launch.json)
- Create `vscode/launch.json` (create `vscode` folder if needed). Structure shown includes:
    - `"type": "prophet"`
    - `"request": "launch"`
    - `"hostname"`, `"username"`, `"password"`, `"codeversion"`
    - `"cartridgeroot"` absolute path to directory containing all cartridges
    - `"workspaceroot": "${workspaceFolder}" ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

---

## JavaScript and Style Sheets (compile commands)
From repository top level, run:
- `npm run compile:js`
- `npm run compile:scss`
- `npm run compile:fonts` ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

---

## Cartridges (upload flow)
- The unit shows a more concrete `dw.json` example (hostname/username/password/code-version) and explains each field:
    - hostname = sandbox FQDN
    - username = user with Site Development rights
    - password = password
    - code-version = e.g., version1 for a new sandbox ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))
- Upload cartridges:
    1) Navigate to top level of `storefront-reference-architecture`
    2) Run `npm run uploadCartridge` (uploads `app_storefront_base` and `modules` cartridges using the dw.json settings)
    3) Open Business Manager
    4) Administration → Site Development → Code Deployment ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

*(Further steps continue in the unit after Code Deployment; this file captures all content visible in the fetched section and keeps the same order.)* ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

---

## VI (A-level: chi tiết, bám sát Topics; giữ thuật ngữ)

### Mục tiêu học
- Dùng npm để cài packages.
- Compile JavaScript, style sheets, fonts cho SFRA.
- Upload SFRA cartridges.
- Add data vào SFRA.
- Index SFRA. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### Install and Configure
- Vijay set up máy local để test/prototype SFRA customizations: cài Node.js + SFRA CLI tools → VS Code và các process khác. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))
- Steps:
    1) Vào thư mục `storefront-reference-architecture`
    2) Cài Node.js 12.x, test `node -v`
    3) Windows: `npm install --global --production windows-build-tools --vs2015`
    4) `npm install` để cài dependencies; luôn chạy lại khi tải SFRA version mới. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### SFRA Command-Line Tools (sgmf-scripts)
- Global (*nix/Windows): `npm install -g sgmf-scripts` → chạy `sgmf-scripts --help`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))
- Mac có thể gặp `EACCES` → fix permissions; global không bắt buộc nhưng tiện hơn cho cartridge mới. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))
- Local: `npm install sgmf-scripts` → chạy `node node_modules/sgmf-scripts --help`. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### Visual Studio Code
- VS Code có debugging, syntax highlighting, intelligent completion, snippets, refactoring, embedded Git. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))
- Steps: cài VS Code → cài ESLint extension → mở folder chứa cartridges. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### Enable upload (dw.json + Prophet)
- Tạo `dw.json` theo cấu trúc unit cung cấp. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))
- Bật setting `extension.prophet.upload.enabled = true`, restart VS Code. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### Debugging (launch.json)
- Tạo `vscode/launch.json` cấu hình `"type": "prophet"` và các field hostname/user/pass/codeversion + cartridgeroot/workspaceroot. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### Compile assets
- Chạy:
    - `npm run compile:js`
    - `npm run compile:scss`
    - `npm run compile:fonts` ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))

### Upload cartridges
- Giải thích các field trong `dw.json` (hostname=FQDN, user có Site Development rights, code-version...).
- Upload: `npm run uploadCartridge` rồi vào Business Manager → Administration → Site Development → Code Deployment. ([trailhead.salesforce.com](https://trailhead.salesforce.com/ja/content/learn/modules/b2c-developer-resources-and-tools/b2c-developer-install-config-sfra))