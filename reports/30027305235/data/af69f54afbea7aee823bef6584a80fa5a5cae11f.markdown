# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: src/app/dashboard/[tab]/test.ts >> 登录工作台各分支提供唯一页面身份（en-us）
- Location: tests/e2e/src/app/dashboard/[tab]/test.ts:103:3

# Error details

```
Error: expect(locator).toHaveCount(expected) failed

Locator:  getByRole('main', { name: 'Shuttle Bus', exact: true })
Expected: 1
Received: 0
Timeout:  5000ms

Call log:
  - Expect "toHaveCount" with timeout 5000ms
  - waiting for getByRole('main', { name: 'Shuttle Bus', exact: true })
    14 × locator resolved to 0 elements
       - unexpected value "0"

```

# Page snapshot

```yaml
- generic [ref=e3]:
  - link "Skip to main content" [ref=e4] [cursor=pointer]:
    - /url: "#main-content"
  - generic [ref=e7]:
    - navigation "Primary navigation" [ref=e8]:
      - list [ref=e10]:
        - listitem [ref=e11]:
          - link "Life@USTC" [ref=e12] [cursor=pointer]:
            - /url: /
            - img [ref=e13]
            - generic [ref=e14]: Life@USTC
      - generic [ref=e15]:
        - generic [ref=e17]:
          - button "Workspace" [expanded] [ref=e18]:
            - text: Workspace
            - img [ref=e19]
          - list [ref=e23]:
            - listitem [ref=e24]:
              - link "Today" [ref=e25] [cursor=pointer]:
                - /url: /workspace/overview
                - img [ref=e26]
                - generic [ref=e29]: Today
            - listitem [ref=e30]:
              - link "Calendar" [ref=e31] [cursor=pointer]:
                - /url: /workspace/calendar
                - img [ref=e32]
                - generic [ref=e34]: Calendar
            - listitem [ref=e35]:
              - link "Homework" [ref=e36] [cursor=pointer]:
                - /url: /workspace/homeworks
                - img [ref=e37]
                - generic [ref=e39]: Homework
            - listitem [ref=e40]:
              - link "Todos" [ref=e41] [cursor=pointer]:
                - /url: /workspace/todos
                - img [ref=e42]
                - generic [ref=e45]: Todos
            - listitem [ref=e46]:
              - link "Exams" [ref=e47] [cursor=pointer]:
                - /url: /workspace/exams
                - img [ref=e48]
                - generic [ref=e51]: Exams
            - listitem [ref=e52]:
              - link "Section Subscriptions" [ref=e53] [cursor=pointer]:
                - /url: /workspace/subscriptions
                - img [ref=e54]
                - generic [ref=e58]: Section Subscriptions
        - generic [ref=e60]:
          - button "Explore" [expanded] [ref=e61]:
            - text: Explore
            - img [ref=e62]
          - list [ref=e66]:
            - listitem [ref=e67]:
              - link "Courses" [ref=e68] [cursor=pointer]:
                - /url: /catalog/courses
                - img [ref=e69]
                - generic [ref=e71]: Courses
            - listitem [ref=e72]:
              - link "Sections" [ref=e73] [cursor=pointer]:
                - /url: /catalog/sections
                - img [ref=e74]
                - generic [ref=e78]: Sections
            - listitem [ref=e79]:
              - link "Teachers" [ref=e80] [cursor=pointer]:
                - /url: /catalog/teachers
                - img [ref=e81]
                - generic [ref=e86]: Teachers
            - listitem [ref=e87]:
              - link "Shuttle Bus" [ref=e88] [cursor=pointer]:
                - /url: /catalog/bus
                - img [ref=e89]
                - generic [ref=e93]: Shuttle Bus
              - list [ref=e94]:
                - listitem [ref=e95]:
                  - link "Transit Map" [ref=e96] [cursor=pointer]:
                    - /url: /catalog/bus/map
                    - generic [ref=e97]: Transit Map
            - listitem [ref=e98]:
              - link "Websites" [ref=e99] [cursor=pointer]:
                - /url: /catalog/links
                - img [ref=e100]
                - generic [ref=e103]: Websites
            - listitem [ref=e104]:
              - link "Mobile App" [ref=e105] [cursor=pointer]:
                - /url: /mobile-app
                - img [ref=e106]
                - generic [ref=e108]: Mobile App
    - button "Toggle Sidebar" [ref=e109]
    - list [ref=e111]:
      - listitem [ref=e112]:
        - button "Profile menu" [ref=e113]:
          - img "Dev User" [ref=e115]
          - generic [ref=e116]:
            - generic [ref=e117]: Dev User
            - generic [ref=e118]: "@dev-user"
          - img [ref=e119]
  - main [ref=e122]:
    - generic [ref=e124]:
      - button "Menu" [expanded] [ref=e125]:
        - img
        - generic [ref=e126]: Toggle Sidebar
      - generic [ref=e128]:
        - button "Language selector" [ref=e129]:
          - img
        - button "Theme selector" [ref=e130]:
          - img
    - generic [ref=e131]:
      - generic [ref=e133]:
        - generic [ref=e134]:
          - paragraph [ref=e135]: Start with public campus tools
          - heading "Shuttle Bus" [level=1] [ref=e136]
          - paragraph [ref=e137]: See the next shuttle and route changes across campuses.
        - generic [ref=e139]:
          - generic [ref=e140]:
            - generic [ref=e141]:
              - paragraph [ref=e142]: Next departure
              - generic [ref=e143]: 06:50
              - generic [ref=e145]:
                - generic [ref=e146]: Arrive at
                - generic [ref=e147]: 07:00
            - generic [ref=e149]:
              - generic [ref=e150]:
                - paragraph [ref=e151]:
                  - generic [ref=e152]:
                    - generic [ref=e153]: 东区
                    - generic [ref=e154]: →西区
                    - generic [ref=e155]: →先研院
                    - generic [ref=e156]: →高新
                - paragraph [ref=e157]: 东区 → 西区
              - generic [ref=e158]:
                - paragraph [ref=e159]: Upcoming trips
                - list [ref=e160]:
                  - generic [ref=e162]:
                    - generic [ref=e163]: 07:30 → 07:40
                    - paragraph [ref=e164]:
                      - generic [ref=e165]:
                        - generic [ref=e166]: 东区
                        - generic [ref=e167]: →北区
                        - generic [ref=e168]: →西区
                  - generic [ref=e170]:
                    - generic [ref=e171]: 09:20 → 09:30
                    - paragraph [ref=e172]:
                      - generic [ref=e173]:
                        - generic [ref=e174]: 东区
                        - generic [ref=e175]: →北区
                        - generic [ref=e176]: →西区
            - generic [ref=e177]:
              - button "Reverse" [ref=e178]:
                - img
                - text: Reverse
              - link "Transit map" [ref=e179] [cursor=pointer]:
                - /url: /catalog/bus/map
          - button "Change route" [ref=e181]:
            - text: Change route
            - img
          - button "Full timetable" [ref=e183]:
            - text: Full timetable
            - img
      - generic [ref=e185]:
        - navigation "Footer navigation" [ref=e186]:
          - link "Terms of Service" [ref=e187] [cursor=pointer]:
            - /url: /terms
          - link "Privacy Policy" [ref=e188] [cursor=pointer]:
            - /url: /privacy
          - link "GitHub" [ref=e189] [cursor=pointer]:
            - /url: https://github.com/Life-USTC/server
          - link "Mobile App" [ref=e190] [cursor=pointer]:
            - /url: /mobile-app
        - paragraph [ref=e191]: Life@USTC
```

# Test source

```ts
  1   | /**
  2   |  * E2E tests for dashboard route variants (`/workspace/<tab>`).
  3   |  */
  4   | import { expect, type Page, test } from "@playwright/test";
  5   | import {
  6   |   type SignedTabId,
  7   |   signedTabIds,
  8   | } from "@/features/dashboard/lib/dashboard-nav";
  9   | import {
  10  |   expectRequiresSignIn,
  11  |   signInAsDebugUser,
  12  | } from "../../../../utils/auth";
  13  | import { sidebarNavigationLink } from "../../../../utils/locators";
  14  | import { gotoAndWaitForReady } from "../../../../utils/page-ready";
  15  | import { captureStepScreenshot } from "../../../../utils/screenshot";
  16  | 
  17  | const dashboardTabRoutes = {
  18  |   overview: "/workspace/overview",
  19  |   calendar: "/workspace/calendar",
  20  |   homeworks: "/workspace/homeworks",
  21  |   todos: "/workspace/todos",
  22  |   exams: "/workspace/exams",
  23  |   subscriptions: "/workspace/subscriptions",
  24  |   bus: "/catalog/bus",
  25  |   links: "/catalog/links",
  26  | } satisfies Record<SignedTabId, string>;
  27  | 
  28  | const dashboardTabTitles = {
  29  |   "en-us": {
  30  |     overview: "Overview",
  31  |     calendar: "Calendar",
  32  |     homeworks: "Homework",
  33  |     todos: "Todos",
  34  |     exams: "Exams",
  35  |     subscriptions: "Section Subscriptions",
  36  |     bus: "Shuttle Bus",
  37  |     links: "Websites",
  38  |   },
  39  |   "zh-cn": {
  40  |     overview: "总览",
  41  |     calendar: "日历",
  42  |     homeworks: "作业",
  43  |     todos: "待办",
  44  |     exams: "考试",
  45  |     subscriptions: "教学班订阅",
  46  |     bus: "校车",
  47  |     links: "网站",
  48  |   },
  49  | } satisfies Record<"en-us" | "zh-cn", Record<SignedTabId, string>>;
  50  | 
  51  | async function setLocale(page: Page, locale: "en-us" | "zh-cn") {
  52  |   const response = await page.request.post("/api/account/preferences", {
  53  |     data: { locale },
  54  |   });
  55  |   expect(response.status()).toBe(200);
  56  | }
  57  | 
  58  | async function expectDashboardPageIdentity(
  59  |   page: Page,
  60  |   locale: "en-us" | "zh-cn",
  61  |   title: string,
  62  | ) {
  63  |   await expect(page.locator("html")).toHaveAttribute("lang", locale);
  64  |   await expect(page).toHaveTitle(`${title} - Life@USTC`);
  65  |   await expect(page.getByRole("heading", { level: 1 })).toHaveCount(1);
  66  |   await expect(
  67  |     page.getByRole("heading", { level: 1, name: title, exact: true }),
  68  |   ).toHaveCount(1);
  69  |   await expect(page.getByRole("main")).toHaveCount(1);
  70  |   await expect(
  71  |     page.getByRole("main", { name: title, exact: true }),
> 72  |   ).toHaveCount(1);
      |     ^ Error: expect(locator).toHaveCount(expected) failed
  73  | }
  74  | 
  75  | test("/workspace 别名需要登录", async ({ page }, testInfo) => {
  76  |   await expectRequiresSignIn(page, "/workspace/homeworks");
  77  |   await captureStepScreenshot(page, testInfo, "dashboard-homeworks-unauth");
  78  | });
  79  | 
  80  | test("/workspace/homeworks 加载登录标签", async ({ page }, testInfo) => {
  81  |   await signInAsDebugUser(page, "/workspace/homeworks");
  82  |   await gotoAndWaitForReady(page, "/workspace/homeworks", {
  83  |     testInfo,
  84  |     screenshotLabel: "dashboard-homeworks",
  85  |   });
  86  | 
  87  |   await expect(page).toHaveURL(/\/workspace\/homeworks(?:[/?#].*)?$/);
  88  |   await expect(
  89  |     sidebarNavigationLink(page, /^(作业|Homework)$/i),
  90  |   ).toHaveAttribute("aria-current", "page");
  91  |   await captureStepScreenshot(page, testInfo, "dashboard-homeworks");
  92  | });
  93  | 
  94  | test("登录工作区隐藏公共页脚但公共内容页保留", async ({ page }) => {
  95  |   await signInAsDebugUser(page, "/workspace/overview");
  96  |   await expect(page.locator("footer")).toHaveCount(0);
  97  | 
  98  |   await gotoAndWaitForReady(page, "/catalog/courses");
  99  |   await expect(page.locator("footer")).toBeVisible();
  100 | });
  101 | 
  102 | for (const locale of ["zh-cn", "en-us"] as const) {
  103 |   test(`登录工作台各分支提供唯一页面身份（${locale}）`, async ({
  104 |     page,
  105 |   }, testInfo) => {
  106 |     test.setTimeout(60_000);
  107 |     if (locale === "zh-cn") {
  108 |       await page.setViewportSize({ width: 390, height: 844 });
  109 |     }
  110 |     await signInAsDebugUser(page, dashboardTabRoutes.overview);
  111 |     await setLocale(page, locale);
  112 | 
  113 |     for (const tab of signedTabIds) {
  114 |       await gotoAndWaitForReady(page, dashboardTabRoutes[tab]);
  115 |       await expectDashboardPageIdentity(
  116 |         page,
  117 |         locale,
  118 |         dashboardTabTitles[locale][tab],
  119 |       );
  120 | 
  121 |       if (
  122 |         (locale === "zh-cn" && tab === "todos") ||
  123 |         (locale === "en-us" && tab === "calendar")
  124 |       ) {
  125 |         await captureStepScreenshot(
  126 |           page,
  127 |           testInfo,
  128 |           `dashboard-page-identity-${locale}-${tab}`,
  129 |         );
  130 |       }
  131 |     }
  132 |   });
  133 | }
  134 | 
  135 | test("查询参数别名永久跳转后使用规范化的工作台页面身份", async ({ page }) => {
  136 |   await setLocale(page, "zh-cn");
  137 |   await signInAsDebugUser(page, "/workspace/todos");
  138 |   await gotoAndWaitForReady(page, "/workspace?tab=todos");
  139 | 
  140 |   await expect(page).toHaveURL(/\/workspace\/todos$/);
  141 |   await expectDashboardPageIdentity(page, "zh-cn", "待办");
  142 | });
  143 | 
```