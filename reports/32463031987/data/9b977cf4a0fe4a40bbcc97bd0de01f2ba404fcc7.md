# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: src/app/dashboard/test.ts >> 仪表盘 >> /workspace 默认永久重定向到 overview 语义路径
- Location: tests/e2e/src/app/dashboard/test.ts:63:3

# Error details

```
Error: apiRequestContext.fetch: connect ECONNREFUSED ::1:3000
Call log:
  - → GET http://localhost:3000/workspace?overviewWeek=next
    - user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.7922.34 Safari/537.36
    - accept: */*
    - accept-encoding: gzip,deflate,br

```