# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: src/app/sections/test.ts >> /catalog/sections 班级搜索页 >> 280 至 375 像素窄屏筛选与帮助不溢出
- Location: tests/e2e/src/app/sections/test.ts:194:3

# Error details

```
Error: Expected page scrollWidth (298) not to exceed clientWidth (280) by more than 1px. Possible offenders: [{"element":"div","left":104,"right":298},{"element":"a","left":248,"right":298}]

expect(received).toBeLessThanOrEqual(expected)

Expected: <= 281
Received:    298
```

# Page snapshot

```yaml
- generic [ref=e2]:
  - link "跳转到主要内容" [ref=e3] [cursor=pointer]:
    - /url: "#main-content"
  - generic [ref=e4]:
    - main [ref=e6]:
      - generic [ref=e8]:
        - button "菜单" [ref=e9]:
          - generic [ref=e10]: Toggle Sidebar
        - link "Life@USTC" [ref=e11] [cursor=pointer]:
          - /url: /
        - generic [ref=e14]:
          - button "打开搜索" [ref=e16]
          - generic [ref=e17]:
            - button "语言选择" [ref=e18]
            - button "主题选择" [ref=e19]
          - link "登录" [ref=e20] [cursor=pointer]:
            - /url: /account/sign-in
      - region "主要内容滚动区域" [ref=e21]:
        - generic [ref=e24]:
          - generic [ref=e27]:
            - heading "所有班级" [level=1] [ref=e28]
            - paragraph [ref=e29]: 浏览和筛选所有可用的课程班级
          - generic [ref=e30]:
            - generic [ref=e32]:
              - generic [ref=e33]:
                - generic [ref=e34]: 搜索
                - group [ref=e35]:
                  - group [ref=e36]
                  - searchbox "搜索" [ref=e40]: IS3003.01
                  - group [ref=e41]:
                    - generic [ref=e42]:
                      - generic: Ctrl
                      - generic: Shift
                      - generic: K
                - button "搜索" [ref=e43]
                - button "筛选 (1)" [ref=e44]:
                  - generic [ref=e45]: 筛选
                  - generic [ref=e46]: "1"
              - group "筛选" [ref=e47]:
                - 'link "清除: 搜索: IS3003.01" [ref=e48] [cursor=pointer]':
                  - /url: /catalog/sections
                  - generic [ref=e49]: "搜索: IS3003.01"
            - generic [ref=e51]:
              - generic [ref=e52]:
                - paragraph [ref=e53]: 显示 1 个班级中的 1 个 关于 "IS3003.01"
                - generic [ref=e54]: 1 / 1
              - list [ref=e58]:
                - listitem [ref=e59] [cursor=pointer]:
                  - generic [ref=e60]:
                    - generic [ref=e61]: 密码工程原理与实践
                    - paragraph [ref=e62]: 2026年春季学期 · 林璟锵, 王伟
                  - generic "IS3003.01" [ref=e64]
                  - generic [ref=e65]:
                    - generic [ref=e66]: "学分: 2.5"
                    - generic [ref=e67]: "容量: 58 / 80"
                    - generic [ref=e68]: 东校区
    - contentinfo [ref=e69]:
      - generic [ref=e70]:
        - navigation "页脚导航" [ref=e71]:
          - link "服务条款" [ref=e72] [cursor=pointer]:
            - /url: /terms
          - link "隐私政策" [ref=e73] [cursor=pointer]:
            - /url: /privacy
          - link "GitHub" [ref=e74] [cursor=pointer]:
            - /url: https://github.com/Life-USTC/server
          - link "移动应用" [ref=e75] [cursor=pointer]:
            - /url: /usage/mobile
        - paragraph [ref=e76]: Life@USTC
  - region "Notifications alt+T"
```

# Test source

```ts
  1   | import type { TestInfo } from "@playwright/test";
  2   | import { expect, type Page } from "@playwright/test";
  3   | import {
  4   |   type BrowserHealthAllowlist,
  5   |   expectNoFrameworkErrorOverlay,
  6   |   observeBrowserHealth,
  7   |   unexpectedBrowserIssues,
  8   | } from "./browser-health";
  9   | import { expectRenderedUiQuality, type UiQualityAllowlist } from "./ui-quality";
  10  | 
  11  | type GotoOptions = {
  12  |   expectMainContent?: boolean;
  13  |   waitUntil?: "load" | "domcontentloaded" | "networkidle" | "commit";
  14  |   testInfo?: TestInfo;
  15  |   screenshotLabel?: string;
  16  |   /** Assert console errors, uncaught page errors, and framework overlays during navigation. */
  17  |   browserHealth?: false | BrowserHealthAllowlist;
  18  |   /** Assert the main region contains rendered, meaningful UI rather than an empty shell. */
  19  |   expectMeaningfulContent?: boolean;
  20  |   /** Assert the document itself does not scroll horizontally. */
  21  |   expectNoHorizontalOverflow?: boolean;
  22  |   /** Assert shared document, asset, link, heading, and control integrity. */
  23  |   uiQuality?: false | UiQualityAllowlist;
  24  | };
  25  | 
  26  | const GOTO_RETRY_ATTEMPTS = 3;
  27  | 
  28  | export async function expectNoPageHorizontalOverflow(page: Page) {
  29  |   const geometry = await page.evaluate(() => {
  30  |     const root = document.documentElement;
  31  |     const offenders = Array.from(document.body.querySelectorAll("*"))
  32  |       .map((element) => {
  33  |         const rect = element.getBoundingClientRect();
  34  |         return {
  35  |           element:
  36  |             element.id.length > 0
  37  |               ? `${element.tagName.toLowerCase()}#${element.id}`
  38  |               : element.tagName.toLowerCase(),
  39  |           left: Math.round(rect.left),
  40  |           right: Math.round(rect.right),
  41  |         };
  42  |       })
  43  |       .filter(({ left, right }) => right > root.clientWidth + 1 || left < -1)
  44  |       .slice(0, 5);
  45  | 
  46  |     return {
  47  |       clientWidth: root.clientWidth,
  48  |       scrollWidth: root.scrollWidth,
  49  |       offenders,
  50  |     };
  51  |   });
  52  | 
  53  |   expect(
  54  |     geometry.scrollWidth,
  55  |     `Expected page scrollWidth (${geometry.scrollWidth}) not to exceed clientWidth (${geometry.clientWidth}) by more than 1px. Possible offenders: ${JSON.stringify(geometry.offenders)}`,
> 56  |   ).toBeLessThanOrEqual(geometry.clientWidth + 1);
      |     ^ Error: Expected page scrollWidth (298) not to exceed clientWidth (280) by more than 1px. Possible offenders: [{"element":"div","left":104,"right":298},{"element":"a","left":248,"right":298}]
  57  | }
  58  | 
  59  | export async function expectMeaningfulMainContent(page: Page) {
  60  |   const main = page.locator("#main-content");
  61  |   await expect(main).toBeVisible();
  62  |   await expect(
  63  |     main
  64  |       .locator(
  65  |         "h1, h2, p, a, button, input, textarea, select, img, svg, canvas, table, pre, article, section",
  66  |       )
  67  |       .filter({ visible: true })
  68  |       .first(),
  69  |     "Expected #main-content to contain at least one visible content element",
  70  |   ).toBeVisible();
  71  | }
  72  | 
  73  | export async function waitForUiSettled(
  74  |   page: Page,
  75  |   options: {
  76  |     waitUntil?: "load" | "domcontentloaded" | "networkidle";
  77  |   } = {},
  78  | ) {
  79  |   await page.waitForLoadState(options.waitUntil ?? "domcontentloaded");
  80  |   await page.waitForFunction(
  81  |     () => document.documentElement.dataset.lifeUstcHydrated === "true",
  82  |     null,
  83  |     { timeout: 10_000 },
  84  |   );
  85  |   await page.waitForFunction(() => !/^Loading\b/i.test(document.title), null, {
  86  |     timeout: 10_000,
  87  |   });
  88  |   await expect(page.locator('[data-slot="page-loading"]:visible')).toHaveCount(
  89  |     0,
  90  |     {
  91  |       timeout: 10_000,
  92  |     },
  93  |   );
  94  |   await expect(page.locator('[data-slot="skeleton"]:visible')).toHaveCount(0, {
  95  |     timeout: 10_000,
  96  |   });
  97  | }
  98  | 
  99  | export async function gotoAndWaitForReady(
  100 |   page: Page,
  101 |   url: string,
  102 |   options: GotoOptions = {},
  103 | ) {
  104 |   const {
  105 |     browserHealth = false,
  106 |     expectMainContent = true,
  107 |     expectMeaningfulContent = false,
  108 |     expectNoHorizontalOverflow = false,
  109 |     uiQuality = false,
  110 |     waitUntil,
  111 |   } = options;
  112 |   const healthObserver =
  113 |     browserHealth === false ? null : observeBrowserHealth(page);
  114 | 
  115 |   try {
  116 |     const loadStateWaitUntil =
  117 |       waitUntil === "commit" ? "domcontentloaded" : waitUntil;
  118 |     let response: Awaited<ReturnType<Page["goto"]>> | undefined;
  119 |     for (let attempt = 1; attempt <= GOTO_RETRY_ATTEMPTS; attempt += 1) {
  120 |       try {
  121 |         response = await page.goto(url, {
  122 |           waitUntil: waitUntil ?? "domcontentloaded",
  123 |         });
  124 |         break;
  125 |       } catch (error) {
  126 |         if (
  127 |           !(error instanceof Error) ||
  128 |           !error.message.includes("net::ERR_ABORTED") ||
  129 |           attempt === GOTO_RETRY_ATTEMPTS
  130 |         ) {
  131 |           throw error;
  132 |         }
  133 |       }
  134 |     }
  135 | 
  136 |     await waitForUiSettled(page, { waitUntil: loadStateWaitUntil });
  137 | 
  138 |     if (expectMeaningfulContent) {
  139 |       await expectMeaningfulMainContent(page);
  140 |     } else if (expectMainContent) {
  141 |       await expect(page.locator("#main-content")).toBeVisible();
  142 |     }
  143 | 
  144 |     if (browserHealth !== false) {
  145 |       await expectNoFrameworkErrorOverlay(page);
  146 |       expect(
  147 |         unexpectedBrowserIssues(healthObserver?.issues ?? [], browserHealth),
  148 |         "Unexpected browser errors occurred while loading the page",
  149 |       ).toEqual([]);
  150 |     }
  151 | 
  152 |     if (expectNoHorizontalOverflow) {
  153 |       await expectNoPageHorizontalOverflow(page);
  154 |     }
  155 | 
  156 |     if (uiQuality !== false) {
```