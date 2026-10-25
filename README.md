# Conduit API Testing

**Postman · JavaScript · Black-box API Testing · Defect Investigation**

API testing of [Conduit](https://conduit.mate.academy/), a RealWorld-style blogging platform. This project focuses on independent, repeatable requests, reusable test helpers, and investigating gaps between frontend validation and backend behavior.

## Navigation

- [Overview](#overview)
- [Test Coverage](#test-coverage)
- [Testing Approach](#testing-approach)
- [Defect Reports](#defect-reports)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Tools](#tools)

## Overview

The collection contains **51 requests** across five API areas: Users, Articles, Profiles, Tags, and Comments.

Key characteristics:

- **Independent requests:** each request prepares its own required test data, so requests can be run individually and in different orders.
- **Runtime-generated data:** JavaScript pre-request helpers generate unique users, articles, and comments rather than relying on hardcoded records.
- **Reusable logic:** shared helpers reduce duplicated setup and assertion code.
- **Cleanup:** articles created during tests are deleted afterward to reduce test-data pollution.
- **Evidence-based investigation:** defects are documented with reproduction steps and supporting evidence.

## Test Coverage

| Area | What is covered |
|---|---|
| Users | User-related API behavior and validation |
| Articles | Article creation and related validation |
| Profiles | Profile behavior, including follow relationships |
| Tags | Tag-related API behavior |
| Comments | Comment creation and related behavior |

The collection includes both normal flows and invalid or boundary inputs. See the [defect reports](#defect-reports) for examples of issues uncovered during testing.

## Testing Approach

Testing was primarily **black-box**, with **grey-box investigation** when observed behavior required further analysis.

- Compared raw API responses with frontend behavior using the browser DevTools Network tab.
- Investigated validation inconsistencies between the frontend and backend.
- Generated test data at runtime to make requests repeatable and reduce collisions.
- Designed requests to run independently, without depending on a specific execution order.
- Captured reproducible defects and supporting evidence in separate reports.

## Defect Reports

Selected reports:

- [CPP-2 — Silent conversion to lowercase](bug-reports/CPP-2-silect-convert-to-lowercase.md)
- [CPP-3 — Contradictory validation messages](bug-reports/CPP-3-contradict-valid-messages.md)
- [CPP-4 — Invalid username length accepted](bug-reports/CPP-4-invalid-username-length-accept.md)
- [CPP-5 — Username is not updated](bug-reports/CPP-5-username-is-not-updated.md)
- [CPP-6 — Whitespace-only input accepted](bug-reports/CPP-6-empty-spaceonly-pass-updated.md)
- [CPP-7 — Invalid image URL accepted](bug-reports/CPP-7-invalid-img-url-accept.md)
- [CPP-8 — Article created with an empty title](bug-reports/CPP-8-empty-title-article-creat.md)
- [CPP-9 — Article created with an empty description](bug-reports/CPP-9-empty-descr-article-creat.md)
- [CPP-10 — User can follow their own profile](bug-reports/CPP-10-user-follows-own-profile.md)

Each report includes details of the observed behavior and investigation evidence where available. Browse the full [bug-reports directory](bug-reports/).

## Project Structure

```text
.
├── postman/
│   └── conduit-collection.json
├── bug-reports/
│   ├── CPP-2 ... CPP-10 reports
│   └── screenshots/
└── README.md
```

- [Postman collection](postman/conduit-collection.json)
- [Bug reports and evidence](bug-reports/)
- [Supporting screenshots](bug-reports/screenshots/)

## Getting Started

1. Clone or download this repository.
2. Open Postman.
3. Import the [Conduit collection](postman/conduit-collection.json).
4. Review the requests and their pre-request and test scripts.
5. Run individual requests or the collection, and inspect the response and test results.

> The collection targets the Conduit practice application. Use it only where you have permission to test, and be aware that requests may create or delete test data.

## Tools

- **API testing:** Postman
- **Scripting:** JavaScript (pre-request and test scripts)
- **Investigation:** Chrome / Edge DevTools
- **Test and defect management:** Jira, TestRail

---

[Back to top](#conduit-api-testing)
