# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: src/app/workspace/homeworks/list-state.test.ts >> 仪表盘作业 >> 已完成作业隐藏截止提醒：桌面列表 / 逾期
- Location: tests/e2e/src/app/workspace/homeworks/list-state.test.ts:42:7

# Error details

```
Error: expect(locator).toBeVisible() failed

Locator: getByRole('dialog').getByTestId('homework-deadline-summary').getByText(/^(已完成|Completed)$/i)
Expected: visible
Timeout: 5000ms
Error: element(s) not found

Call log:
  - Expect "toBeVisible" with timeout 5000ms
  - waiting for getByRole('dialog').getByTestId('homework-deadline-summary').getByText(/^(已完成|Completed)$/i)

```

```yaml
- link "Skip to main content":
  - /url: "#main-content"
- navigation "Primary navigation":
  - list:
    - listitem:
      - link "Life@USTC":
        - /url: /
  - button "Workspace" [expanded]
  - list:
    - listitem:
      - link "Today":
        - /url: /workspace/overview
    - listitem:
      - link "Calendar":
        - /url: /workspace/calendar
      - text: "19"
    - listitem:
      - link "Homework":
        - /url: /workspace/homeworks
      - text: "8"
    - listitem:
      - link "Todos":
        - /url: /workspace/todos
      - text: "5"
    - listitem:
      - link "Exams":
        - /url: /workspace/exams
    - listitem:
      - link "Section Subscriptions":
        - /url: /workspace/subscriptions
      - text: "4"
  - button "Catalog" [expanded]
  - list:
    - listitem:
      - link "Courses":
        - /url: /catalog/courses
    - listitem:
      - link "Sections":
        - /url: /catalog/sections
    - listitem:
      - link "Teachers":
        - /url: /catalog/teachers
    - listitem:
      - link "Room maps":
        - /url: /catalog/rooms
    - listitem:
      - link "Shuttle Bus":
        - /url: /catalog/bus
    - listitem:
      - link "Websites":
        - /url: /catalog/links
    - listitem:
      - link "Second Classroom":
        - /url: /catalog/young-events
    - listitem:
      - link "Campus Weather":
        - /url: /catalog/weather
    - listitem:
      - link "News & Notices":
        - /url: /news
  - button "Usage" [expanded]
  - list:
    - listitem:
      - link "Mobile App":
        - /url: /usage/mobile
    - listitem:
      - link "Presto Bot":
        - /url: /usage/bot
    - listitem:
      - link "MCP":
        - /url: /usage/mcp
    - listitem:
      - link "CLI":
        - /url: /usage/cli
- button "Toggle Sidebar"
- list:
  - listitem:
    - button "Profile menu":
      - img "Dev User"
      - text: Dev User @dev-user
- main "Homework":
  - button "Open search": Search sections, teachers, courses, homework, todos… Ctrl K
  - button "Language selector"
  - button "Theme selector"
  - region "Main content scroll region":
    - heading "Homework" [level=1]
    - group "Homework":
      - radio "Incomplete"
      - radio "Completed"
      - radio "All" [checked]
    - button "Add homework"
    - table:
      - rowgroup:
        - row "Section Title Submission due Status Mark as complete":
          - columnheader "Section"
          - columnheader "Title"
          - columnheader "Submission due"
          - columnheader "Status"
          - columnheader "Mark as complete"
      - rowgroup:
        - 'row "Cryptographic Engineering: Principles and Practice e2e-completed-deadline-false-true Jan 1, 2020, 12:00 PM Completed Major assignment Team required Mark as incomplete View details"':
          - 'cell "Cryptographic Engineering: Principles and Practice"':
            - 'link "Cryptographic Engineering: Principles and Practice"':
              - /url: /catalog/sections/9902001
          - cell "e2e-completed-deadline-false-true":
            - button "e2e-completed-deadline-false-true"
          - cell "Jan 1, 2020, 12:00 PM"
          - cell "Completed Major assignment Team required"
          - cell "Mark as incomplete View details":
            - button "Mark as incomplete"
            - button "View details"
        - row "Advanced Linear Algebra 历史学期复盘作业 Mar 20, 8:00 PM Overdue by 6 months Mark as complete View details":
          - cell "Advanced Linear Algebra":
            - link "Advanced Linear Algebra":
              - /url: /catalog/sections/9902004
          - cell "历史学期复盘作业":
            - button "历史学期复盘作业"
          - cell "Mar 20, 8:00 PM"
          - cell "Overdue by 6 months"
          - cell "Mark as complete View details":
            - button "Mark as complete"
            - button "View details"
        - 'row "Cryptographic Engineering: Principles and Practice 迭代一需求拆解 Apr 27, 8:00 PM Completed Mark as incomplete View details"':
          - 'cell "Cryptographic Engineering: Principles and Practice"':
            - 'link "Cryptographic Engineering: Principles and Practice"':
              - /url: /catalog/sections/9902001
          - cell "迭代一需求拆解":
            - button "迭代一需求拆解"
          - cell "Apr 27, 8:00 PM"
          - cell "Completed"
          - cell "Mark as incomplete View details":
            - button "Mark as incomplete"
            - button "View details"
        - 'row "Cryptographic Engineering: Principles and Practice 逾期实验数据补交 Apr 28, 10:00 PM Overdue by 5 months Major assignment Mark as complete View details"':
          - 'cell "Cryptographic Engineering: Principles and Practice"':
            - 'link "Cryptographic Engineering: Principles and Practice"':
              - /url: /catalog/sections/9902001
          - cell "逾期实验数据补交":
            - button "逾期实验数据补交"
          - cell "Apr 28, 10:00 PM"
          - cell "Overdue by 5 months Major assignment"
          - cell "Mark as complete View details":
            - button "Mark as complete"
            - button "View details"
        - 'row "Cryptographic Engineering: Principles and Practice 今日课堂反馈整理 Apr 29, 11:00 PM Overdue by 5 months Mark as complete View details"':
          - 'cell "Cryptographic Engineering: Principles and Practice"':
            - 'link "Cryptographic Engineering: Principles and Practice"':
              - /url: /catalog/sections/9902001
          - cell "今日课堂反馈整理":
            - button "今日课堂反馈整理"
          - cell "Apr 29, 11:00 PM"
          - cell "Overdue by 5 months"
          - cell "Mark as complete View details":
            - button "Mark as complete"
            - button "View details"
        - row "Introduction to Astrophysics 线性变换证明题 May 1, 10:00 PM Completed Mark as incomplete View details":
          - cell "Introduction to Astrophysics":
            - link "Introduction to Astrophysics":
              - /url: /catalog/sections/9902002
          - cell "线性变换证明题":
            - button "线性变换证明题"
          - cell "May 1, 10:00 PM"
          - cell "Completed"
          - cell "Mark as incomplete View details":
            - button "Mark as incomplete"
            - button "View details"
        - row "Environmental Microbiology 实验报告与误差分析 May 2, 9:00 PM Overdue by 5 months Major assignment Team required Mark as complete View details":
          - cell "Environmental Microbiology":
            - link "Environmental Microbiology":
              - /url: /catalog/sections/9902003
          - cell "实验报告与误差分析":
            - button "实验报告与误差分析"
          - cell "May 2, 9:00 PM"
          - cell "Overdue by 5 months Major assignment Team required"
          - cell "Mark as complete View details":
            - button "Mark as complete"
            - button "View details"
        - 'row "Cryptographic Engineering: Principles and Practice 迭代二系统设计评审 May 3, 11:00 PM Overdue by 5 months Major assignment Team required Mark as complete View details"':
          - 'cell "Cryptographic Engineering: Principles and Practice"':
            - 'link "Cryptographic Engineering: Principles and Practice"':
              - /url: /catalog/sections/9902001
          - cell "迭代二系统设计评审":
            - button "迭代二系统设计评审"
          - cell "May 3, 11:00 PM"
          - cell "Overdue by 5 months Major assignment Team required"
          - cell "Mark as complete View details":
            - button "Mark as complete"
            - button "View details"
        - row "Introduction to Astrophysics 特征值综合练习 May 5, 10:00 PM Overdue by 5 months Mark as complete View details":
          - cell "Introduction to Astrophysics":
            - link "Introduction to Astrophysics":
              - /url: /catalog/sections/9902002
          - cell "特征值综合练习":
            - button "特征值综合练习"
          - cell "May 5, 10:00 PM"
          - cell "Overdue by 5 months"
          - cell "Mark as complete View details":
            - button "Mark as complete"
            - button "View details"
        - row "Introduction to Astrophysics e2e-workspace-homework-1789837614455 Date TBD Date TBD Mark as complete View details":
          - cell "Introduction to Astrophysics":
            - link "Introduction to Astrophysics":
              - /url: /catalog/sections/9902002
          - cell "e2e-workspace-homework-1789837614455":
            - button "e2e-workspace-homework-1789837614455"
          - cell "Date TBD"
          - cell "Date TBD"
          - cell "Mark as complete View details":
            - button "Mark as complete"
            - button "View details"
- region "Notifications alt+T"
- dialog "e2e-completed-deadline-false-true":
  - heading "e2e-completed-deadline-false-true" [level=2]
  - 'link "Cryptographic Engineering: Principles and Practice · IS3003.01 · 2026年春季学期"':
    - /url: /catalog/sections/9902001
  - paragraph: Submission due
  - paragraph: 1/1/20, 12:00 PM
  - table:
    - rowgroup:
      - row "Status Completed · Major assignment · Team required":
        - rowheader "Status"
        - cell "Completed · Major assignment · Team required"
      - row "Submission opens TBD":
        - rowheader "Submission opens"
        - cell "TBD"
      - row "Published TBD":
        - rowheader "Published"
        - cell "TBD"
  - heading "Details" [level=2]
  - paragraph: No homework details yet
  - heading "Homework discussion" [level=2]
  - button "Post comment"
  - text: No comments yet
  - button "Mark as incomplete"
  - button "Close"
```

# Test source

```ts
  31  |       page
  32  |         .getByRole("row")
  33  |         .filter({ hasText: DEV_SEED.homeworks.title })
  34  |         .first(),
  35  |     ).toBeVisible();
  36  | 
  37  |     await captureStepScreenshot(page, testInfo, "homeworks/list-view");
  38  |   });
  39  | 
  40  |   for (const mobile of [false, true]) {
  41  |     for (const overdue of [true, false]) {
  42  |       test(`已完成作业隐藏截止提醒：${mobile ? "移动卡片" : "桌面列表"} / ${overdue ? "逾期" : "未到期"}`, async ({
  43  |         page,
  44  |       }, testInfo) => {
  45  |         test.setTimeout(90_000);
  46  |         await page.setViewportSize(
  47  |           mobile ? { width: 390, height: 844 } : { width: 1280, height: 900 },
  48  |         );
  49  |         await signInAsDebugUser(page, "/workspace/homeworks");
  50  |         await ensureSeedSectionSubscription(page);
  51  |         const title = `e2e-completed-deadline-${mobile}-${overdue}`;
  52  |         let homeworkId: string | undefined;
  53  |         try {
  54  |           const response = await page.request.post(
  55  |             "/api/community/section-homeworks",
  56  |             {
  57  |               data: {
  58  |                 sectionJwId: DEV_SEED.section.jwId,
  59  |                 title,
  60  |                 submissionDueAt: overdue
  61  |                   ? "2020-01-01T12:00:00+08:00"
  62  |                   : "2099-01-01T12:00:00+08:00",
  63  |                 isMajor: true,
  64  |                 requiresTeam: true,
  65  |               },
  66  |             },
  67  |           );
  68  |           expect(response.ok()).toBe(true);
  69  |           const created = await response.json();
  70  |           homeworkId = created.id;
  71  |           expect(homeworkId).toBeTruthy();
  72  |           await gotoAndWaitForReady(page, "/workspace/homeworks");
  73  |           await page
  74  |             .getByRole("radio", { name: /全部|All/i })
  75  |             .first()
  76  |             .click();
  77  |           const surface = mobile
  78  |             ? page
  79  |                 .getByTestId("workspace-homeworks-cards")
  80  |                 .locator('[data-slot="item"]')
  81  |                 .filter({ hasText: title })
  82  |             : page.getByRole("row").filter({ hasText: title });
  83  |           const reminder = /已逾期|还剩|Overdue by|left/i;
  84  |           const reminderText = surface.getByText(reminder);
  85  |           await expect(reminderText).toBeVisible();
  86  |           const dueText = await surface
  87  |             .getByText(/\d{1,2}:\d{2}/)
  88  |             .first()
  89  |             .textContent();
  90  |           const complete = surface.getByRole("button", {
  91  |             name: /标记为完成|Mark as complete/i,
  92  |           });
  93  |           await complete.click();
  94  |           await expect(
  95  |             surface.getByRole("button", {
  96  |               name: /取消完成|Mark as incomplete/i,
  97  |             }),
  98  |           ).toBeEnabled();
  99  |           await expect(reminderText).toHaveCount(0);
  100 |           await expect(
  101 |             surface.getByText(/^(已完成|Completed)$/i),
  102 |           ).toBeVisible();
  103 |           await expect(
  104 |             surface.getByText(/大作业|Major/i, { exact: true }),
  105 |           ).toBeVisible();
  106 |           await expect(
  107 |             surface.getByText(/需要组队|Team required|Requires team/i, {
  108 |               exact: true,
  109 |             }),
  110 |           ).toBeVisible();
  111 |           expect(
  112 |             await surface
  113 |               .getByText(/\d{1,2}:\d{2}/)
  114 |               .first()
  115 |               .textContent(),
  116 |           ).toBe(dueText);
  117 |           await captureStepScreenshot(
  118 |             page,
  119 |             testInfo,
  120 |             `homeworks/completed-deadline-${mobile}-${overdue}`,
  121 |           );
  122 | 
  123 |           await surface
  124 |             .getByRole("button", { name: title, exact: true })
  125 |             .click();
  126 |           const dialog = page.getByRole("dialog");
  127 |           const summary = dialog.getByTestId("homework-deadline-summary");
  128 |           await expect(summary.getByText(reminder)).toHaveCount(0);
  129 |           await expect(
  130 |             summary.getByText(/^(已完成|Completed)$/i),
> 131 |           ).toBeVisible();
      |             ^ Error: expect(locator).toBeVisible() failed
  132 |           await expect(summary.getByText(/\d{1,2}:\d{2}/)).toBeVisible();
  133 |           await dialog
  134 |             .getByRole("button", { name: /取消完成|Mark as incomplete/i })
  135 |             .click();
  136 |           await expect(summary.getByText(reminder)).toBeVisible();
  137 |           await page.keyboard.press("Escape");
  138 |           await expect(reminderText).toBeVisible();
  139 |         } finally {
  140 |           await cleanupHomeworksForE2e([homeworkId]);
  141 |         }
  142 |       });
  143 |     }
  144 |   }
  145 | });
  146 | 
```