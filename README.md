# Conduit API Testing — Postman Collection

API testing project for [Conduit](https://conduit.mate.academy/), a RealWorld-style blogging platform. Built as part of my QA Flex academy practice — covers the full API surface with independent, self-contained requests, reusable pre-request helpers, and documented bugs found through investigation rather than checkbox testing.

## What's in here

- **51 requests** across User, Articles, Profile, Tags, and Comments
- Every request is **independent** — pre-request scripts create their own test data (users, articles, comments) using `Date.now()`-based uniqueness
- Reusable helper functions for user creation, article creation, comment creation, and common assertions — no copy-pasted test logic
- Automatic cleanup — articles created during tests are deleted afterward to keep the database tidy
- Bugs found and documented, ranging from silent data transformation to broken validation and a self-follow exploit

## Approach

Black-box API testing with grey-box investigation when something looked off — DevTools Network tab to compare frontend behavior against raw API responses, especially for the bugs where the frontend validates correctly but the API doesn't.

Test data is generated at runtime, never hardcoded — every request can be run on its own, in any order, any number of times, without colliding with previous runs.

## Structure

- `postman/conduit-collection.json` — import into Postman to run everything
- `bug-reports/` — one file per bug, with evidence
- `bug-reports/screenshots/` — supporting screenshots


## Tools

Postman, JavaScript (pre-request & test scripts), Chrome/Edge DevTools, Jira, TestRail

---
