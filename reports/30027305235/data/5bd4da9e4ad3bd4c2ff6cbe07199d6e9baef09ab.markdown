# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: src/app/api/docs/test.ts >> /api/docs 页面 >> 桌面端保留完整固定导航
- Location: tests/e2e/src/app/api/docs/test.ts:127:3

# Error details

```
Test timeout of 30000ms exceeded.
```

```
Error: expect(locator).toContainText(expected) failed

Locator: locator('#api-reference')
- Expected substring  - 1
+ Received string     + 7

- List sections
+ v1.0.0OpenAPI 3.0.0catalog.bus
+ OpenAPI document generated from SvelteKit route handlers
+  Server Server:http://localhost:3000
+ Current origin
+ AuthenticationSelect Auth Type  No authentication selected catalog.bus  (Collapsed)​Copy link
+ catalog.bus operations
+ catalog.bus Operations get/api/catalog/bus get/api/catalog/bus/next get/api/catalog/bus/routesShow sidebarSearchcatalog.bus catalog.busClose Group Query shuttle busesHTTP Method:  GETGet next shuttle bus departures for an origin and destination campusHTTP Method:  GETSearch shuttle bus route variantsHTTP Method:  GETGETServer: http://localhost:3000/api/catalog/busCopy URLSend Send get request to http://localhost:3000//api/catalog/busGETCopy URLSend Send get request to http://localhost:3000//api/catalog/busClose ClientQuery shuttle busesAllAuthCookiesHeadersQueryAllAuthentication (Collapsed) Select Auth Type Variables Enabled Key ValueCookies Enabled Key ValueKeyValueHeaders Enabled Key Valueacceptapplication/jsonKeyValueQuery Parameters Enabled Key ValueversionKeyValueKeyValueRequest BodyNoneNo BodyCode Snippet (Collapsed)   Response AllCookiesHeadersBodyAll Powered By Scalar.com                          .,,uod8B8bou,,.                ..,uod8BBBBBBBBBBBBBBBBRPFT?l!i:.           ||||||||||||||!?TFPRBBBBBBBBBBBBBBB8m=,           ||||   '""^^!!||||||||||TFPRBBBVT!:...!           ||||            '""^^!!|||||?!:.......!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||,                    ||||.........`           |||||!!-._               ||||.......;.           ':!|||||||||!!-._        ||||.....bBBBBWdou,.         bBBBBB86foi!|||||||!!-..:|||!..bBBBBBBBBBBBBBBY!         ::!?TFPRBBBBBB86foi!||||||||!!bBBBBBBBBBBBBBBY..!         :::::::::!?TFPRBBBBBB86ftiaabBBBBBBBBBBBBBBY....!         :::;`"^!:;::::::!?TFPRBBBBBBBBBBBBBBBBBBBY......!         ;::::::...''^::::::::::!?TFPRBBBBBBBBBBY........!     .ob86foi;::::::::::::::::::::::::!?TFPRBY..........`    .b888888888886foi;:::::::::::::::::::::::..........` .b888888888888888888886foi;::::::::::::::::...........b888888888888888888888888888886foi;:::::::::......`!Tf998888888888888888888888888888888886foi;:::....`  '"^!|Tf9988888888888888888888888888888888!::..`       '"^!|Tf998888888888888888888888889!! '`             '"^!|Tf9988888888888888888!!`            iBBbo.                  '"^!|Tf998888888889!`             WBBBBbo.                        '"^!|Tf9989!`              YBBBP^'                              '"^!`               ` Send Request ctrlControl↵Enter

Call log:
  - Expect "toContainText" with timeout 30000ms
  - waiting for locator('#api-reference')
    - locator resolved to <div id="api-reference" class="api-reference min-h-[42rem] overflow-hidden rounded-lg border border-border bg-background"></div>
    - unexpected value ""
    - locator resolved to <div data-v-app="" id="api-reference" class="api-reference min-h-[42rem] overflow-hidden rounded-lg border border-border bg-background">…</div>
    - unexpected value "v1.0.0OpenAPI 3.0.0catalog.bus
OpenAPI document generated from SvelteKit route handlers
 Server Server:http://localhost:3000
Current origin
AuthenticationSelect Auth Type  No authentication selected "
    - locator resolved to <div data-v-app="" id="api-reference" class="api-reference min-h-[42rem] overflow-hidden rounded-lg border border-border bg-background">…</div>
    - unexpected value "v1.0.0OpenAPI 3.0.0catalog.bus
OpenAPI document generated from SvelteKit route handlers
 Server Server:http://localhost:3000
Current origin
AuthenticationSelect Auth Type  No authentication selected Show sidebarSearchcatalog.bus catalog.busClose Group Query shuttle busesHTTP Method:  GETGet next shuttle bus departures for an origin and destination campusHTTP Method:  GETSearch shuttle bus route variantsHTTP Method:  GETGETServer: http://localhost:3000/api/catalog/busCopy URLSend Send get request to http://localhost:3000//api/catalog/busGETCopy URLSend Send get request to http://localhost:3000//api/catalog/busClose ClientQuery shuttle busesAllAuthCookiesHeadersQueryAllAuthentication (Collapsed) Select Auth Type Variables Enabled Key ValueCookies Enabled Key ValueKeyValueHeaders Enabled Key Valueacceptapplication/jsonKeyValueQuery Parameters Enabled Key ValueversionKeyValueKeyValueRequest BodyNoneNo BodyCode Snippet (Collapsed)   Response AllCookiesHeadersBodyAll Powered By Scalar.com                          .,,uod8B8bou,,.                ..,uod8BBBBBBBBBBBBBBBBRPFT?l!i:.           ||||||||||||||!?TFPRBBBBBBBBBBBBBBB8m=,           ||||   '""^^!!||||||||||TFPRBBBVT!:...!           ||||            '""^^!!|||||?!:.......!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||,                    ||||.........`           |||||!!-._               ||||.......;.           ':!|||||||||!!-._        ||||.....bBBBBWdou,.         bBBBBB86foi!|||||||!!-..:|||!..bBBBBBBBBBBBBBBY!         ::!?TFPRBBBBBB86foi!||||||||!!bBBBBBBBBBBBBBBY..!         :::::::::!?TFPRBBBBBB86ftiaabBBBBBBBBBBBBBBY....!         :::;`"^!:;::::::!?TFPRBBBBBBBBBBBBBBBBBBBY......!         ;::::::...''^::::::::::!?TFPRBBBBBBBBBBY........!     .ob86foi;::::::::::::::::::::::::!?TFPRBY..........`    .b888888888886foi;:::::::::::::::::::::::..........` .b888888888888888888886foi;::::::::::::::::...........b888888888888888888888888888886foi;:::::::::......`!Tf998888888888888888888888888888888886foi;:::....`  '"^!|Tf9988888888888888888888888888888888!::..`       '"^!|Tf998888888888888888888888889!! '`             '"^!|Tf9988888888888888888!!`            iBBbo.                  '"^!|Tf998888888889!`             WBBBBbo.                        '"^!|Tf9989!`              YBBBP^'                              '"^!`               ` Send Request ctrlControl↵Enter"
    57 × locator resolved to <div data-v-app="" id="api-reference" class="api-reference min-h-[42rem] overflow-hidden rounded-lg border border-border bg-background">…</div>
       - unexpected value "v1.0.0OpenAPI 3.0.0catalog.bus
OpenAPI document generated from SvelteKit route handlers
 Server Server:http://localhost:3000
Current origin
AuthenticationSelect Auth Type  No authentication selected catalog.bus  (Collapsed)​Copy link
catalog.bus operations
catalog.bus Operations get/api/catalog/bus get/api/catalog/bus/next get/api/catalog/bus/routesShow sidebarSearchcatalog.bus catalog.busClose Group Query shuttle busesHTTP Method:  GETGet next shuttle bus departures for an origin and destination campusHTTP Method:  GETSearch shuttle bus route variantsHTTP Method:  GETGETServer: http://localhost:3000/api/catalog/busCopy URLSend Send get request to http://localhost:3000//api/catalog/busGETCopy URLSend Send get request to http://localhost:3000//api/catalog/busClose ClientQuery shuttle busesAllAuthCookiesHeadersQueryAllAuthentication (Collapsed) Select Auth Type Variables Enabled Key ValueCookies Enabled Key ValueKeyValueHeaders Enabled Key Valueacceptapplication/jsonKeyValueQuery Parameters Enabled Key ValueversionKeyValueKeyValueRequest BodyNoneNo BodyCode Snippet (Collapsed)   Response AllCookiesHeadersBodyAll Powered By Scalar.com                          .,,uod8B8bou,,.                ..,uod8BBBBBBBBBBBBBBBBRPFT?l!i:.           ||||||||||||||!?TFPRBBBBBBBBBBBBBBB8m=,           ||||   '""^^!!||||||||||TFPRBBBVT!:...!           ||||            '""^^!!|||||?!:.......!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||                     ||||.........!           ||||,                    ||||.........`           |||||!!-._               ||||.......;.           ':!|||||||||!!-._        ||||.....bBBBBWdou,.         bBBBBB86foi!|||||||!!-..:|||!..bBBBBBBBBBBBBBBY!         ::!?TFPRBBBBBB86foi!||||||||!!bBBBBBBBBBBBBBBY..!         :::::::::!?TFPRBBBBBB86ftiaabBBBBBBBBBBBBBBY....!         :::;`"^!:;::::::!?TFPRBBBBBBBBBBBBBBBBBBBY......!         ;::::::...''^::::::::::!?TFPRBBBBBBBBBBY........!     .ob86foi;::::::::::::::::::::::::!?TFPRBY..........`    .b888888888886foi;:::::::::::::::::::::::..........` .b888888888888888888886foi;::::::::::::::::...........b888888888888888888888888888886foi;:::::::::......`!Tf998888888888888888888888888888888886foi;:::....`  '"^!|Tf9988888888888888888888888888888888!::..`       '"^!|Tf998888888888888888888888889!! '`             '"^!|Tf9988888888888888888!!`            iBBbo.                  '"^!|Tf998888888889!`             WBBBBbo.                        '"^!|Tf9989!`              YBBBP^'                              '"^!`               ` Send Request ctrlControl↵Enter"

```

```yaml
- main "Open API Documentation for catalog.bus":
  - region "Introduction":
    - text: v1.0.0 OpenAPI 3.0.0
    - heading "catalog.bus" [level=1]
    - paragraph: OpenAPI document generated from SvelteKit route handlers
    - text: "Server Server: http://localhost:3000"
    - paragraph: Current origin
    - region "Authentication":
      - button "Authentication" [disabled] [expanded]:
        - heading "Authentication" [level=2]
      - button "Select Auth Type"
      - text: No authentication selected
  - region "catalog.bus (Collapsed)":
    - heading "catalog.bus (Collapsed)" [level=2]
    - button "Copy link"
    - paragraph: catalog.bus operations
    - group "catalog.bus Operations":
      - text: catalog.bus Operations
      - list "catalog.bus endpoints":
        - listitem: get /api/catalog/bus
        - listitem: get /api/catalog/bus/next
        - listitem: get /api/catalog/bus/routes
- region "Notifications alt+T":
  - list
```

# Test source

```ts
  1   | /**
  2   |  * E2E tests for /api/docs
  3   |  */
  4   | import { expect, type Page, test } from "@playwright/test";
  5   | import { gotoAndWaitForReady } from "../../../../utils/page-ready";
  6   | import { capturePageScreenshot } from "../../../../utils/screenshot";
  7   | import { assertPageContract } from "../../_shared/page-contract";
  8   | 
  9   | async function setLocale(page: Page, locale: "en-us" | "zh-cn") {
  10  |   const response = await page.request.post("/api/account/preferences", {
  11  |     data: { locale },
  12  |   });
  13  |   expect(response.ok()).toBe(true);
  14  | }
  15  | 
  16  | async function waitForSectionsReference(page: Page) {
  17  |   const reference = page.locator("#api-reference");
> 18  |   await expect(reference).toContainText("List sections", { timeout: 30_000 });
      |                           ^ Error: expect(locator).toContainText(expected) failed
  19  |   return reference;
  20  | }
  21  | 
  22  | test.describe("/api/docs 页面", () => {
  23  |   test("接口契约", async ({ page }, testInfo) => {
  24  |     await assertPageContract(page, {
  25  |       routePath: "/api/docs/tag/sections",
  26  |       testInfo,
  27  |     });
  28  |   });
  29  | 
  30  |   test("渲染 API 参考容器", async ({ page }) => {
  31  |     await gotoAndWaitForReady(page, "/api/docs/tag/sections", {
  32  |       waitUntil: "load",
  33  |     });
  34  |     await expect(page.locator("#api-reference")).toBeVisible();
  35  |   });
  36  | 
  37  |   test("移动端优先展示参考内容并用抽屉浏览完整导航", async ({
  38  |     page,
  39  |   }, testInfo) => {
  40  |     await page.setViewportSize({ width: 390, height: 844 });
  41  |     await setLocale(page, "zh-cn");
  42  |     await gotoAndWaitForReady(page, "/api/docs/tag/sections", {
  43  |       waitUntil: "load",
  44  |     });
  45  |     const reference = await waitForSectionsReference(page);
  46  |     const mobileTrigger = page.getByTestId(
  47  |       "api-docs-mobile-navigation-trigger",
  48  |     );
  49  | 
  50  |     await expect(mobileTrigger).toHaveAccessibleName("浏览 API 接口");
  51  |     await expect(mobileTrigger).toBeVisible();
  52  |     await expect(page.getByTestId("api-docs-desktop-navigation")).toBeHidden();
  53  | 
  54  |     const initialMetrics = await reference.evaluate((element) => ({
  55  |       documentY: element.getBoundingClientRect().top + window.scrollY,
  56  |       scrollY: window.scrollY,
  57  |       viewportHeight: window.innerHeight,
  58  |       hasBodyOverflow:
  59  |         document.documentElement.scrollWidth >
  60  |         document.documentElement.clientWidth,
  61  |     }));
  62  |     expect(initialMetrics.scrollY).toBe(0);
  63  |     expect(initialMetrics.documentY).toBeLessThan(
  64  |       initialMetrics.viewportHeight,
  65  |     );
  66  |     expect(initialMetrics.viewportHeight).toBe(844);
  67  |     expect(initialMetrics.hasBodyOverflow).toBe(false);
  68  |     await capturePageScreenshot(page, testInfo, {
  69  |       url: "api-docs/mobile-reference",
  70  |     });
  71  | 
  72  |     await mobileTrigger.click();
  73  |     const panel = page.getByTestId("api-docs-mobile-navigation-panel");
  74  |     await expect(panel).toBeVisible();
  75  |     await expect(panel).toHaveRole("dialog");
  76  |     await expect(panel).toHaveAccessibleName("API 导航");
  77  |     await expect(
  78  |       panel.getByRole("heading", { name: "API 导航" }),
  79  |     ).toBeVisible();
  80  |     await expect(
  81  |       panel.getByRole("link", { name: "Sections", exact: true }),
  82  |     ).toHaveAttribute("aria-current", "page");
  83  |     const desktopNavigation = page.getByTestId("api-docs-desktop-navigation");
  84  |     expect(await panel.getByRole("link").count()).toBe(
  85  |       await desktopNavigation
  86  |         .getByRole("link", { includeHidden: true })
  87  |         .count(),
  88  |     );
  89  |     await expect
  90  |       .poll(() =>
  91  |         panel.evaluate((element) => getComputedStyle(element).overflowY),
  92  |       )
  93  |       .toBe("auto");
  94  |     await capturePageScreenshot(page, testInfo, {
  95  |       url: "api-docs/mobile-navigation",
  96  |     });
  97  | 
  98  |     await page.keyboard.press("Escape");
  99  |     await expect(panel).toBeHidden();
  100 |     await expect(mobileTrigger).toBeFocused();
  101 | 
  102 |     await mobileTrigger.click();
  103 |     await panel
  104 |       .getByRole("link", { name: "GET List sections", exact: true })
  105 |       .click();
  106 |     await expect(page).toHaveURL(
  107 |       /\/api\/docs\/tag\/sections\/GET\/api\/catalog\/sections$/,
  108 |     );
  109 |     await expect(panel).toBeHidden();
  110 |     await expect(reference).toContainText("List sections");
  111 |     await expect.poll(() => page.evaluate(() => window.scrollY)).toBe(0);
  112 |     const operationDocumentY = await reference.evaluate(
  113 |       (element) => element.getBoundingClientRect().top + window.scrollY,
  114 |     );
  115 |     expect(operationDocumentY).toBeLessThan(844);
  116 |     await mobileTrigger.click();
  117 |     await expect(
  118 |       panel.getByRole("link", { name: "GET List sections", exact: true }),
```