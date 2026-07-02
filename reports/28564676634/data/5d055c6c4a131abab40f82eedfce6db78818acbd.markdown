# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: src/app/dashboard/test.ts >> 仪表盘 >> 仪表盘路径别名渲染匹配的标签
- Location: tests/e2e/src/app/dashboard/test.ts:109:3

# Error details

```
Error: expect(locator).toBeVisible() failed

Locator: getByRole('link', { name: /网站|Websites/i }).first()
Expected: visible
Timeout: 5000ms
Error: element(s) not found

Call log:
  - Expect "toBeVisible" with timeout 5000ms
  - waiting for getByRole('link', { name: /网站|Websites/i }).first()

```

```yaml
- complementary:
  - link "Life@USTC":
    - /url: /
  - navigation "Primary navigation":
    - region "Workspace":
      - paragraph: Workspace
      - link "Overview":
        - /url: /dashboard/overview
      - link "Calendar":
        - /url: /dashboard/calendar
      - link "Homework":
        - /url: /dashboard/homeworks
      - link "Todos":
        - /url: /dashboard/todos
      - link "Exams":
        - /url: /dashboard/exams
      - link "Section Management":
        - /url: /dashboard/subscriptions
    - region "Public tools":
      - paragraph: Public tools
      - link "Dashboard transit":
        - /url: /dashboard/bus
        - text: Shuttle Bus
      - link "Dashboard links":
        - /url: /dashboard/links
        - text: Websites
    - region "Catalog":
      - paragraph: Catalog
      - link "Courses":
        - /url: /courses
      - link "Sections":
        - /url: /sections
      - link "Teachers":
        - /url: /teachers
    - region "Campus":
      - paragraph: Campus
      - link "Transit Map":
        - /url: /bus-map
      - link "Mobile App":
        - /url: /mobile-app
- banner:
  - paragraph: Websites
  - button "Language selector"
  - button "Switch to light mode"
  - button "Profile menu":
    - img "Dev User"
    - text: D
- main:
  - group "Website view":
    - button "Card" [pressed]
    - button "List"
  - searchbox "Search by name or description…"
  - heading "Most clicked" [level=3]
  - button "Academic Affairs System Course selection, grades, and teaching affairs.":
    - text: Academic Affairs System
    - paragraph: Course selection, grades, and teaching affairs.
  - button "Unpin"
  - button "iCourse Review Community Course reviews and study experience sharing.":
    - text: iCourse Review Community
    - paragraph: Course reviews and study experience sharing.
  - button "Pin"
  - button "USTC Email USTC email service.":
    - text: USTC Email
    - paragraph: USTC email service.
  - button "Unpin"
  - button "Library Library catalog search and database resources.":
    - text: Library
    - paragraph: Library catalog search and database resources.
  - button "Pin"
  - button "USTC Official Site University news and announcements.":
    - text: USTC Official Site
    - paragraph: University news and announcements.
  - button "Unpin"
  - button "Online Teaching Platform Course materials and online learning.":
    - text: Online Teaching Platform
    - paragraph: Course materials and online learning.
  - button "Pin"
  - button "Academic Affairs Office Teaching administration and notices.":
    - text: Academic Affairs Office
    - paragraph: Teaching administration and notices.
  - button "Pin"
  - button "Nanqi Market Campus community information platform.":
    - text: Nanqi Market
    - paragraph: Campus community information platform.
  - button "Pin"
  - button "Network Portal Network services and plan management.":
    - text: Network Portal
    - paragraph: Network services and plan management.
  - button "Pin"
  - heading "Study" [level=3]
  - button "Faculty FTP Homepages Faculty homepage and related entry points.":
    - text: Faculty FTP Homepages
    - paragraph: Faculty homepage and related entry points.
  - button "Pin"
  - button "Legacy Academic Affairs System Entry point for the legacy academic affairs system.":
    - text: Legacy Academic Affairs System
    - paragraph: Entry point for the legacy academic affairs system.
  - button "Pin"
  - button "College Physics Lab 1 College physics experiment platform entry.":
    - text: College Physics Lab 1
    - paragraph: College physics experiment platform entry.
  - button "Pin"
  - button "Public Information Query Campus public information lookup.":
    - text: Public Information Query
    - paragraph: Campus public information lookup.
  - button "Pin"
  - button "Teaching Assistant Management Teaching assistant tasks and workflow management.":
    - text: Teaching Assistant Management
    - paragraph: Teaching assistant tasks and workflow management.
  - button "Pin"
  - button "College Physics Lab 2 College physics experiment platform entry.":
    - text: College Physics Lab 2
    - paragraph: College physics experiment platform entry.
  - button "Pin"
  - button "Student Services Hub Unified entry for student affairs services.":
    - text: Student Services Hub
    - paragraph: Unified entry for student affairs services.
  - button "Pin"
  - button "OT Club Campus communities and discussion.":
    - text: OT Club
    - paragraph: Campus communities and discussion.
  - button "Pin"
  - button "Study Space Booking Book library study spaces.":
    - text: Study Space Booking
    - paragraph: Book library study spaces.
  - button "Pin"
  - button "Central Campus Study Room Booking Study room booking system for Central Campus.":
    - text: Central Campus Study Room Booking
    - paragraph: Study room booking system for Central Campus.
  - button "Pin"
  - button "Dawu Lab Tools Assistant tools for lab work.":
    - text: Dawu Lab Tools
    - paragraph: Assistant tools for lab work.
  - button "Pin"
  - button "College Physics Lab 3 College physics experiment platform entry.":
    - text: College Physics Lab 3
    - paragraph: College physics experiment platform entry.
  - button "Pin"
  - heading "Life" [level=3]
  - button "History and Culture Campus history and culture resources.":
    - text: History and Culture
    - paragraph: Campus history and culture resources.
  - button "Pin"
  - button "Han Hai Xing Yun BBS Campus forum community.":
    - text: Han Hai Xing Yun BBS
    - paragraph: Campus forum community.
  - button "Pin"
  - button "Confession Wall Anonymous campus discussion platform.":
    - text: Confession Wall
    - paragraph: Anonymous campus discussion platform.
  - button "Unpin"
  - button "Campus Information Portal Unified campus information portal.":
    - text: Campus Information Portal
    - paragraph: Unified campus information portal.
  - button "Pin"
  - button "Personal FTP Homepages Personal homepage service entry.":
    - text: Personal FTP Homepages
    - paragraph: Personal homepage service entry.
  - button "Pin"
  - button "REC Portal Campus resources and services entry.":
    - text: REC Portal
    - paragraph: Campus resources and services entry.
  - button "Pin"
  - button "Campus Card Management Campus card services.":
    - text: Campus Card Management
    - paragraph: Campus card services.
  - button "Pin"
  - button "Admission Rain Admission information aggregator.":
    - text: Admission Rain
    - paragraph: Admission information aggregator.
  - button "Pin"
  - button "Licensed Software Campus licensed software service.":
    - text: Licensed Software
    - paragraph: Campus licensed software service.
  - button "Pin"
  - button "Self-Service Printing Self-service printing and copying.":
    - text: Self-Service Printing
    - paragraph: Self-service printing and copying.
  - button "Pin"
  - button "Second Classroom Second Classroom activity platform.":
    - text: Second Classroom
    - paragraph: Second Classroom activity platform.
  - button "Pin"
  - button "Nanqi Teahouse Campus forum and discussion community.":
    - text: Nanqi Teahouse
    - paragraph: Campus forum and discussion community.
  - button "Pin"
  - button "USTC Flyer Study and overseas application information community.":
    - text: USTC Flyer
    - paragraph: Study and overseas application information community.
  - button "Pin"
  - button "QQ Account Proof USTC identity association proof.":
    - text: QQ Account Proof
    - paragraph: USTC identity association proof.
  - button "Pin"
  - button "USTC Cloud Drive Campus cloud drive and file sharing.":
    - text: USTC Cloud Drive
    - paragraph: Campus cloud drive and file sharing.
  - button "Pin"
  - heading "Tech" [level=3]
  - button "Web VPN Access campus resources from off campus.":
    - text: Web VPN
    - paragraph: Access campus resources from off campus.
  - button "Pin"
  - button "Open Source Mirrors Open source software mirror downloads.":
    - text: Open Source Mirrors
    - paragraph: Open source software mirror downloads.
  - button "Pin"
  - button "SCC GitLab Campus code hosting service.":
    - text: SCC GitLab
    - paragraph: Campus code hosting service.
  - button "Pin"
  - button "LUG GitLab LUG community code hosting.":
    - text: LUG GitLab
    - paragraph: LUG community code hosting.
  - button "Pin"
  - button "USTC LaTeX Online LaTeX editor and templates.":
    - text: USTC LaTeX
    - paragraph: Online LaTeX editor and templates.
  - button "Pin"
  - button "Vlab Virtual lab teaching platform.":
    - text: Vlab
    - paragraph: Virtual lab teaching platform.
  - button "Pin"
  - heading "Classroom lookup" [level=3]
  - button "Second Teaching Building Classroom information display for Building 2.":
    - text: Second Teaching Building
    - paragraph: Classroom information display for Building 2.
  - button "Pin"
  - button "Third Teaching Building Classroom information display for Building 3.":
    - text: Third Teaching Building
    - paragraph: Classroom information display for Building 3.
  - button "Pin"
  - button "Fifth Teaching Building Classroom information display for Building 5.":
    - text: Fifth Teaching Building
    - paragraph: Classroom information display for Building 5.
  - button "Pin"
  - heading "External websites" [level=3]
  - button "Zhihu Question-answering and knowledge community.":
    - text: Zhihu
    - paragraph: Question-answering and knowledge community.
  - button "Pin"
  - button "bilibili Video and learning content platform.":
    - text: bilibili
    - paragraph: Video and learning content platform.
  - button "Pin"
  - button "Weibo Social media and news platform.":
    - text: Weibo
    - paragraph: Social media and news platform.
  - button "Pin"
  - heading "Graduate" [level=3]
  - button "Graduate Service Platform Comprehensive graduate affairs platform.":
    - text: Graduate Service Platform
    - paragraph: Comprehensive graduate affairs platform.
  - button "Pin"
  - button "EPC Platform Graduate training process platform.":
    - text: EPC Platform
    - paragraph: Graduate training process platform.
  - button "Pin"
  - button "Graduate School Official Graduate School website.":
    - text: Graduate School
    - paragraph: Official Graduate School website.
  - button "Pin"
  - heading "Least clicked" [level=3]
  - button "Academic Guidance Center Academic advising and support services.":
    - text: Academic Guidance Center
    - paragraph: Academic advising and support services.
  - button "Pin"
  - button "Campus Wiki Campus knowledge wiki.":
    - text: Campus Wiki
    - paragraph: Campus knowledge wiki.
  - button "Pin"
  - button "Supercomputing Center High-performance computing resources entry.":
    - text: Supercomputing Center
    - paragraph: High-performance computing resources entry.
  - button "Pin"
  - button "Online Payment System Campus payment service platform.":
    - text: Online Payment System
    - paragraph: Campus payment service platform.
  - button "Pin"
  - button "Campus Hospital Campus hospital and medical services.":
    - text: Campus Hospital
    - paragraph: Campus hospital and medical services.
  - button "Pin"
  - button "Transcript Printing Transcript printing and verification.":
    - text: Transcript Printing
    - paragraph: Transcript printing and verification.
  - button "Pin"
  - button "Welcome Site New student registration and welcome information.":
    - text: Welcome Site
    - paragraph: New student registration and welcome information.
  - button "Pin"
  - button "Admissions Office Admissions policies and notices.":
    - text: Admissions Office
    - paragraph: Admissions policies and notices.
  - button "Pin"
  - button "Teaching Equipment Repair Teaching equipment repair requests.":
    - text: Teaching Equipment Repair
    - paragraph: Teaching equipment repair requests.
  - button "Pin"
  - paragraph:
    - text: Some links are consolidated from
    - link "SmartHypercube/ustclife":
      - /url: https://github.com/SmartHypercube/ustclife
    - text: ", with thanks."
- contentinfo:
  - navigation "Primary navigation":
    - link "Terms of Service":
      - /url: /terms
    - link "Privacy Policy":
      - /url: /privacy
    - link "GitHub":
      - /url: https://github.com/Life-USTC/server
    - link "Mobile App":
      - /url: /mobile-app
  - paragraph: Life@USTC
```

# Test source

```ts
  18  |  * ## Edge Cases
  19  |  * - `?tab=homeworks` for unauthenticated users falls back to public bus tab
  20  |  * - Invalid `?tab=` values default to "overview" (auth) or "bus" (public)
  21  |  */
  22  | import { expect, test } from "@playwright/test";
  23  | import { signInAsDebugUser } from "../../../utils/auth";
  24  | import { DEV_SEED } from "../../../utils/dev-seed";
  25  | import { gotoAndWaitForReady } from "../../../utils/page-ready";
  26  | import { captureStepScreenshot } from "../../../utils/screenshot";
  27  | import { ensureSeedSectionSubscription } from "../../../utils/subscriptions";
  28  | 
  29  | test.describe("仪表盘", () => {
  30  |   test("未登录 ?tab=homeworks 显示公共校车视图", async ({ page }, testInfo) => {
  31  |     await gotoAndWaitForReady(page, "/?tab=homeworks", {
  32  |       testInfo,
  33  |       screenshotLabel: "dashboard",
  34  |     });
  35  | 
  36  |     await expect(page).toHaveURL(/\/\?tab=homeworks$/);
  37  |     await expect(page.locator("#app-logo")).toBeVisible();
  38  | 
  39  |     // Public view shows bus + links tabs and sign-in CTA
  40  |     await expect(
  41  |       page.getByRole("link", { name: /^(校车|Shuttle Bus)$/i }),
  42  |     ).toBeVisible();
  43  |     await expect(
  44  |       page.getByRole("link", { name: /^(登录|Sign in)$/i }).first(),
  45  |     ).toBeVisible();
  46  | 
  47  |     // Auth-only tabs should not be present
  48  |     await expect(
  49  |       page.getByRole("link", { name: /^(总览|Overview)$/i }),
  50  |     ).toHaveCount(0);
  51  | 
  52  |     await captureStepScreenshot(page, testInfo, "home-public-with-tab");
  53  |   });
  54  | 
  55  |   test("登录后首页显示总览、所有标签和种子数据", async ({ page }, testInfo) => {
  56  |     await signInAsDebugUser(page, "/");
  57  |     await ensureSeedSectionSubscription(page);
  58  |     await gotoAndWaitForReady(page, "/", {
  59  |       testInfo,
  60  |       screenshotLabel: "dashboard",
  61  |     });
  62  | 
  63  |     await expect(page).toHaveURL(/\/(?:\?.*)?$/);
  64  |     await expect(page.locator("#main-content")).toBeVisible();
  65  |     await expect(page.locator("#app-user-menu")).toBeVisible();
  66  | 
  67  |     // All 8 tabs should be present in the nav bar
  68  |     const nav = page.getByLabel(/Dashboard section switcher/i);
  69  |     for (const label of [
  70  |       /^(总览|Overview)$/i,
  71  |       /日历|Calendar/i,
  72  |       /网站|Websites/i,
  73  |     ]) {
  74  |       await expect(nav.getByRole("link", { name: label })).toBeVisible();
  75  |     }
  76  | 
  77  |     // Seed homework title visible on overview. Retry the subscription+reload
  78  |     // because other E2E slices exercise subscription replacement for the
  79  |     // shared debug user. The initial sign-in goto stays outside the retry.
  80  |     await expect(async () => {
  81  |       await ensureSeedSectionSubscription(page);
  82  |       await page.reload({ waitUntil: "domcontentloaded" });
  83  |       await expect(
  84  |         page.getByText(DEV_SEED.homeworks.title).first(),
  85  |       ).toBeVisible({
  86  |         timeout: 2_000,
  87  |       });
  88  |     }).toPass({ timeout: 15_000 });
  89  |     await expect(
  90  |       page.locator('form[action="/api/dashboard-links/visit"]'),
  91  |     ).toHaveCount(DEV_SEED.dashboardLinks.overviewLimit);
  92  | 
  93  |     await captureStepScreenshot(page, testInfo, "dashboard-home");
  94  |   });
  95  | 
  96  |   test("可通过标签栏导航到作业标签", async ({ page }, testInfo) => {
  97  |     await signInAsDebugUser(page, "/");
  98  | 
  99  |     const homeworksTab = page
  100 |       .getByRole("link", { name: /作业|Homework/i })
  101 |       .first();
  102 |     await expect(homeworksTab).toBeVisible();
  103 |     await homeworksTab.click();
  104 | 
  105 |     await expect(page).toHaveURL(/\/dashboard\/homeworks(?:\?.*)?$/);
  106 |     await captureStepScreenshot(page, testInfo, "dashboard-navigate-homeworks");
  107 |   });
  108 | 
  109 |   test("仪表盘路径别名渲染匹配的标签", async ({ page }, testInfo) => {
  110 |     await signInAsDebugUser(page, "/dashboard/links");
  111 |     await gotoAndWaitForReady(page, "/dashboard/links", {
  112 |       testInfo,
  113 |       screenshotLabel: "dashboard-links-path",
  114 |     });
  115 |     const linksDashboardTab = page
  116 |       .getByRole("link", { name: /网站|Websites/i })
  117 |       .first();
> 118 |     await expect(linksDashboardTab).toBeVisible();
      |                                     ^ Error: expect(locator).toBeVisible() failed
  119 |     await expect(linksDashboardTab).toHaveAttribute("aria-current", "page");
  120 |     await expect(
  121 |       page.getByRole("searchbox", {
  122 |         name: /搜索网站名称或描述|Search by name or description/i,
  123 |       }),
  124 |     ).toBeVisible();
  125 | 
  126 |     await signInAsDebugUser(page, "/dashboard/homeworks");
  127 |     const homeworksDashboardTab = page
  128 |       .getByRole("link", { name: /作业|Homework/i })
  129 |       .first();
  130 |     await expect(homeworksDashboardTab).toBeVisible();
  131 |     await expect(homeworksDashboardTab).toHaveAttribute("aria-current", "page");
  132 | 
  133 |     await gotoAndWaitForReady(page, "/dashboard/subscriptions");
  134 |     await expect(page).toHaveURL(/\/dashboard\/subscriptions(?:\?.*)?$/);
  135 |     await expect(
  136 |       page.getByRole("link", {
  137 |         name: /Subscriptions|Section Management|订阅/i,
  138 |       }),
  139 |     ).toBeVisible();
  140 |     await expect(page.getByText(DEV_SEED.semesterNameCn).first()).toBeVisible();
  141 |     await captureStepScreenshot(page, testInfo, "dashboard-subscriptions-path");
  142 |   });
  143 | });
  144 | 
```