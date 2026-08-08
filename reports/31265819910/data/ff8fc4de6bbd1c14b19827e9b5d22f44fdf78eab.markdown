# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: src/app/oauth/authorize/test.ts >> /oauth/authorize 允许授权时带 code 回跳
- Location: tests/e2e/src/app/oauth/authorize/test.ts:180:1

# Error details

```
Error: expect(received).toBe(expected) // Object.is equality

Expected: 201
Received: 400
```

# Test source

```ts
  1   | import {
  2   |   type APIRequestContext,
  3   |   expect,
  4   |   type Page,
  5   |   test,
  6   | } from "@playwright/test";
  7   | import { sha256Base64Url } from "../../../../../shared/crypto";
  8   | import { signInAsDebugUser } from "../../../../utils/auth";
  9   | import { PLAYWRIGHT_BASE_URL } from "../../../../utils/e2e-db";
  10  | import { gotoAndWaitForReady } from "../../../../utils/page-ready";
  11  | import { captureStepScreenshot } from "../../../../utils/screenshot";
  12  | import { assertPageContract } from "../../_shared/page-contract";
  13  | 
  14  | async function generateCodeChallenge(codeVerifier: string) {
  15  |   return sha256Base64Url(codeVerifier);
  16  | }
  17  | 
  18  | const OAUTH_E2E_CODE_VERIFIER =
  19  |   "oauth-e2e-browser-verifier-0123456789012345678901234567890123456789";
  20  | const OAUTH_E2E_PKCE = {
  21  |   code_challenge: await generateCodeChallenge(OAUTH_E2E_CODE_VERIFIER),
  22  |   code_challenge_method: "S256",
  23  | } as const;
  24  | 
  25  | const REDIRECT_URI = `${PLAYWRIGHT_BASE_URL}/e2e/oauth/callback`;
  26  | 
  27  | async function registerPublicClient(request: APIRequestContext) {
  28  |   const response = await request.post("/api/auth/oauth2/register", {
  29  |     data: {
  30  |       client_name: `oauth-authorize-e2e-${Date.now()}`,
  31  |       redirect_uris: [REDIRECT_URI],
  32  |       token_endpoint_auth_method: "none",
  33  |       grant_types: ["authorization_code"],
  34  |       response_types: ["code"],
  35  |       scope: "openid profile",
  36  |     },
  37  |   });
> 38  |   expect(response.status()).toBe(201);
      |                             ^ Error: expect(received).toBe(expected) // Object.is equality
  39  |   const body = (await response.json()) as { client_id?: string };
  40  |   expect(typeof body.client_id).toBe("string");
  41  |   return body.client_id as string;
  42  | }
  43  | 
  44  | function buildAuthorizeApiUrl(params: Record<string, string>) {
  45  |   return `/api/auth/oauth2/authorize?${new URLSearchParams(params).toString()}`;
  46  | }
  47  | 
  48  | async function resumeConsentIfSignInPage(page: Page) {
  49  |   const allowButton = page.getByRole("button", { name: /允许|Allow/i });
  50  |   const debugSignInButton = page
  51  |     .getByRole("button", {
  52  |       name: /Sign in with Debug User \(Dev\)|调试用户（开发）/i,
  53  |     })
  54  |     .first();
  55  | 
  56  |   for (let attempt = 0; attempt < 3; attempt += 1) {
  57  |     const visibleTarget = await Promise.race([
  58  |       allowButton
  59  |         .waitFor({ state: "visible", timeout: attempt === 0 ? 5_000 : 1_500 })
  60  |         .then(() => "allow" as const)
  61  |         .catch(() => null),
  62  |       debugSignInButton
  63  |         .waitFor({ state: "visible", timeout: attempt === 0 ? 5_000 : 1_500 })
  64  |         .then(() => "signin" as const)
  65  |         .catch(() => null),
  66  |     ]);
  67  | 
  68  |     if (visibleTarget === "allow") {
  69  |       return;
  70  |     }
  71  |     if (visibleTarget === "signin") {
  72  |       await debugSignInButton.click();
  73  |       await page.waitForURL(/\/oauth\/authorize\?/);
  74  |     }
  75  |   }
  76  | 
  77  |   await allowButton.waitFor({ state: "visible" });
  78  | }
  79  | 
  80  | test("/oauth/authorize 未登录时重定向到登录页", async ({ page }, testInfo) => {
  81  |   const clientId = await registerPublicClient(page.request);
  82  | 
  83  |   await gotoAndWaitForReady(
  84  |     page,
  85  |     buildAuthorizeApiUrl({
  86  |       ...OAUTH_E2E_PKCE,
  87  |       client_id: clientId,
  88  |       redirect_uri: REDIRECT_URI,
  89  |       response_type: "code",
  90  |       scope: "openid profile",
  91  |       state: "redirect-state",
  92  |       prompt: "consent",
  93  |     }),
  94  |     { expectMainContent: false },
  95  |   );
  96  | 
  97  |   await expect(page).toHaveURL(/\/account\/sign-in\?/);
  98  |   await captureStepScreenshot(page, testInfo, "oauth-authorize-redirect");
  99  | });
  100 | 
  101 | test("/oauth/authorize 登录后恢复原授权请求", async ({ page }, testInfo) => {
  102 |   const clientId = await registerPublicClient(page.request);
  103 | 
  104 |   await gotoAndWaitForReady(
  105 |     page,
  106 |     buildAuthorizeApiUrl({
  107 |       ...OAUTH_E2E_PKCE,
  108 |       client_id: clientId,
  109 |       redirect_uri: REDIRECT_URI,
  110 |       response_type: "code",
  111 |       scope: "openid profile",
  112 |       state: "resume-state",
  113 |       prompt: "consent",
  114 |     }),
  115 |     { expectMainContent: false },
  116 |   );
  117 | 
  118 |   await expect(page).toHaveURL(/\/account\/sign-in\?/);
  119 |   await page
  120 |     .getByRole("button", { name: /Debug User \(Dev\)|调试用户（开发）/i })
  121 |     .first()
  122 |     .click();
  123 |   await expect(page).toHaveURL(/\/oauth\/authorize\?/);
  124 |   await expect(page.getByRole("button", { name: /允许|Allow/i })).toBeVisible();
  125 |   await captureStepScreenshot(page, testInfo, "oauth-authorize-resumed");
  126 | });
  127 | 
  128 | test("/oauth/authorize 无效客户端展示错误", async ({ page }, testInfo) => {
  129 |   await signInAsDebugUser(page, "/");
  130 | 
  131 |   const response = await page.request.get(
  132 |     buildAuthorizeApiUrl({
  133 |       ...OAUTH_E2E_PKCE,
  134 |       client_id: "missing-client",
  135 |       redirect_uri: REDIRECT_URI,
  136 |       response_type: "code",
  137 |       scope: "openid profile",
  138 |       state: "invalid-client-state",
```