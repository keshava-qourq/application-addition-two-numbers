# Product Requirements

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start narrative -->
## Summary

### REQ-001 · draft · source: requirements:US-001

Core feature: a visitor enters two numbers and sees their sum instantly, with results updating live on input change and no history retained.

US-001 (critical): As a visitor, I want to enter two numbers and see their sum, so I can quickly perform an addition calculation. AC-001: with two empty numeric fields, entering valid numbers and triggering calculation (button or live) computes and displays the sum. AC-002: changing either input and recalculating updates the displayed result, with no previous results stored or shown.

**Related:** EPIC-001, AC-001, AC-002

- ⚠ Approval status of this story is not explicitly stated in the input (only the technology stack was explicitly marked approved).

### REQ-002 · draft · source: requirements:US-002

Calculator must correctly support decimal and negative number entry in either field, preserving precision and sign.

US-002 (high): As a visitor, I want to enter decimal and negative numbers, so I can add beyond simple positive integers. AC-003: entering a decimal (e.g. 3.14) and an integer computes the sum with decimal precision preserved. AC-004: entering a negative number (e.g. -5) in one or both fields produces an accurate sum.

**Related:** EPIC-001, AC-003, AC-004

### REQ-003 · draft · source: requirements:US-003

Non-numeric or empty input must produce a clear inline validation message near the offending field, and must block calculation until corrected.

US-003 (high): As a visitor, I want a clear inline message for invalid input, so I understand why calculation can't proceed. AC-005: non-numeric text in either field on attempted calculation shows an inline message near that field and no sum is computed. AC-006: correcting the input clears the message and allows calculation. AC-007: leaving one or both fields empty and attempting calculation shows a 'number required' inline message and no sum is computed.

**Related:** EPIC-001, AC-005, AC-006, AC-007

### REQ-004 · draft · source: requirements:US-004

The app must be fully stateless: no inputs or results are persisted anywhere, whether calculation happens client-side or via a stateless backend call.

US-004 (medium): As a visitor, I want my calculation not saved anywhere, so I trust no record is retained. AC-008: refreshing or returning to the page shows no previous inputs/results, since no database or history store is used. AC-009: whether calculation runs client-side or via a simple stateless backend call, no data is written to a database or persistent store.

**Related:** EPIC-001, AC-008, AC-009

### REQ-005 · draft · source: requirements:US-005

The calculator must be reachable via a direct public link with zero authentication, and must contain no login/sign-up UI anywhere.

US-005 (critical): As a member of the public, I want to open the calculator via a direct link with no sign-up/login, so I can use it immediately. AC-010: navigating to the link loads a fully usable calculator with no login/sign-up/auth prompt. AC-011: no account-related screens or controls exist anywhere in the app.

**Related:** EPIC-002, AC-010, AC-011

### REQ-006 · draft · source: requirements:US-006

First-time visitors must see brief, visible instructions explaining how to enter two numbers and obtain a sum.

US-006 (medium): As a first-time visitor, I want brief usage instructions, so I understand how to use the calculator without confusion. AC-012: the page displays short, visible instructional text explaining how to enter two numbers and get the sum.

**Related:** EPIC-002, AC-012
<!-- sdlc:auto:end narrative -->

<!-- sdlc:auto:start summary -->
**Requirements version:** v1  
**Delivery scope:** lightweight  
**Approved:** 2026-10-16

**Capabilities in scope:** Two-number addition calculator with instant result display, Inline validation message for non-numeric input, Support for decimal and negative number entry, Public, link-based access with no login required, Basic usage instructions for the calculator page, Calculation done client-side or via simple stateless backend call, No database used to store inputs or results, No sign-up or login screen of any kind

**Approved technology stack:**

| Layer | Choice | Rationale |
|---|---|---|
| backend | FastAPI | You confirmed the math itself can happen entirely in the browser — there's no real need for a server to add two numbers. A thin FastAPI service is included only to keep the project consistent with the platform's standard deployment shape (health checks, a predictable place to add logic later if you ever add server-side validation or logging). |
| cloud | AWS | A public, stateless, single-page tool like this needs very little from a cloud provider — static hosting plus a lightweight container for the optional backend. AWS covers that (S3/CloudFront for the frontend, a small compute service for FastAPI) without locking you into anything exotic. |
| database | PostgreSQL | You explicitly said no history or persistence is needed — the app is stateless by design. PostgreSQL is listed here only because a database decision is required for every project template; this app has no data to store, so nothing will actually be written to it. |
| frontend | React | This is a single page with two inputs and a sum display — no routing, no SEO needs, no server-rendered pages. Next.js would add a routing/server layer you'll never use. Plain React gives you the UI and nothing more, which matches an app this small. |
<!-- sdlc:auto:end summary -->

<!-- sdlc:auto:start epics -->
## EPIC-001: Addition Calculator

Core functionality allowing a user to enter two numbers and instantly see their sum, with support for decimals and negative numbers.

### US-001: Add two numbers and display the result

**Priority:** critical

> As a visitor to the page, I want to enter two numbers and see their sum, so that I can quickly perform an addition calculation.

| ID | Given | When | Then |
|---|---|---|---|
| AC-001 | the calculator page is loaded with two empty numeric input fields | I enter a valid number in each field and trigger the calculation (via button click or live update) | the sum of the two numbers is computed and displayed on the page |
| AC-002 | I have already calculated a sum | I change either input value and trigger calculation again | the displayed result updates to reflect the new sum, with no previous results stored or shown |

### US-002: Support decimal and negative number entry

**Priority:** high

> As a visitor to the page, I want to enter decimal and negative numbers into the input fields, so that I can add numbers beyond simple positive integers.

| ID | Given | When | Then |
|---|---|---|---|
| AC-003 | the calculator page is loaded | I enter a decimal number (e.g. 3.14) in one field and an integer in the other and calculate | the sum is correctly computed and displayed with decimal precision preserved |
| AC-004 | the calculator page is loaded | I enter a negative number (e.g. -5) in one or both fields and calculate | the sum correctly accounts for the negative value and is displayed accurately |

### US-003: Reject non-numeric input with inline validation

**Priority:** high

> As a visitor to the page, I want to see a clear inline message when I enter something that isn't a valid number, so that I understand why a calculation cannot be performed and how to fix it.

| ID | Given | When | Then |
|---|---|---|---|
| AC-005 | the calculator page is loaded | I enter non-numeric text (e.g. letters or symbols) into either input field and attempt to calculate | an inline validation message is displayed near the offending field and no sum is calculated |
| AC-006 | an inline validation message is currently displayed due to invalid input | I correct the input to a valid number | the validation message is cleared and I am able to calculate the sum |
| AC-007 | the calculator page is loaded | I leave one or both input fields empty and attempt to calculate | an inline validation message is displayed indicating a number is required, and no sum is calculated |

### US-004: Perform calculation without persisting data

**Priority:** medium

> As a visitor to the page, I want my calculation to be performed without being saved anywhere, so that I can trust no record of my inputs or results is retained.

| ID | Given | When | Then |
|---|---|---|---|
| AC-008 | I have performed one or more calculations on the page | I refresh or leave and return to the page | no previous inputs or results are displayed or retrievable, since no database or history store is used |
| AC-009 | the calculation logic runs client-side or via a simple stateless backend call | a calculation is requested | the result is returned without any data being written to a database or persistent store |

## EPIC-002: Public Access & Usability

Ensures the calculator is freely accessible without authentication and that first-time visitors understand how to use it.

### US-005: Access the calculator without logging in

**Priority:** critical

> As a member of the public, I want to open the calculator page via a direct link without signing up or logging in, so that I can use the tool immediately without any barriers.

| ID | Given | When | Then |
|---|---|---|---|
| AC-010 | I have the link to the calculator page | I navigate to it in a browser | the calculator loads and is fully usable without any login, sign-up, or authentication prompt |
| AC-011 | the application | I look for account-related features such as login or sign-up screens | no such screens or controls exist anywhere in the application |

### US-006: View basic usage instructions

**Priority:** medium

> As a first-time visitor, I want to see brief instructions on how to use the calculator, so that I understand how to enter numbers and get a result without confusion.

| ID | Given | When | Then |
|---|---|---|---|
| AC-012 | the calculator page is loaded | I view the page | a short, visible instructional text explains how to enter two numbers and obtain the sum |
<!-- sdlc:auto:end epics -->
