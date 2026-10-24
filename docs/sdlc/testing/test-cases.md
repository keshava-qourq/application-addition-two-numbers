# Test Cases

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start summary -->
26 test cases · 26 approved · 0 draft · Passed 0 · Failed 0 · Skipped 0 · Not automated 0 · Not run 26

Acceptance criteria covered: 12/12 · passing: 0/12 · No E2E run yet
<!-- sdlc:auto:end summary -->

<!-- sdlc:auto:start cases -->
## Sprint 1

### US-001: Add two numbers and display the result

| ID | Criterion | Level | Title | Status | Result |
|---|---|---|---|---|---|
| TC-001 | AC-001 | e2e | Calculate sum of two valid numbers | approved | not run |
| TC-002 | AC-001 | e2e | Calculate sum with decimal and negative numbers | approved | not run |
| TC-003 | AC-001 | e2e | Attempt calculation with invalid or missing input | approved | not run |
| TC-004 | AC-002 | e2e | Result updates when input values are changed | approved | not run |
| TC-005 | AC-002 | e2e | No previous results are stored or shown after recalculation | approved | not run |

#### TC-001: Calculate sum of two valid numbers

**Criterion:** AC-001 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with two empty numeric input fields

**Steps:**

1. Open the calculator page
2. Enter a valid number (e.g. 5) in the first input field
3. Enter a valid number (e.g. 7) in the second input field
4. Trigger the calculation (click the calculate button or allow live update)

**Expected result:** The sum (12) is computed and displayed on the page

#### TC-002: Calculate sum with decimal and negative numbers

**Criterion:** AC-001 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with two empty numeric input fields

**Steps:**

1. Open the calculator page
2. Enter a decimal number (e.g. -3.5) in the first input field
3. Enter a decimal number (e.g. 2.5) in the second input field
4. Trigger the calculation

**Expected result:** The correct sum (-1) is computed and displayed on the page

#### TC-003: Attempt calculation with invalid or missing input

**Criterion:** AC-001 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with two empty numeric input fields

**Steps:**

1. Open the calculator page
2. Enter a non-numeric value (e.g. 'abc') in the first input field
3. Leave the second input field empty
4. Trigger the calculation

**Expected result:** No sum is displayed, or an indication is shown that the inputs are invalid/incomplete, and no incorrect result appears

#### TC-004: Result updates when input values are changed

**Criterion:** AC-002 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** A sum has already been calculated and is displayed on the page

**Steps:**

1. Open the calculator page
2. Enter 5 and 7 in the input fields and trigger calculation to get a displayed sum of 12
3. Change the first input field value to 10
4. Trigger the calculation again

**Expected result:** The displayed result updates to the new sum (17), replacing the previous result

#### TC-005: No previous results are stored or shown after recalculation

**Criterion:** AC-002 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** A sum has already been calculated and is displayed on the page

**Steps:**

1. Open the calculator page
2. Enter 2 and 3 in the input fields and trigger calculation to get a displayed sum of 5
3. Change the second input field value to 8
4. Trigger the calculation again
5. Observe the page for any history or list of past results

**Expected result:** Only the latest sum (10) is visible on the page; no previous result (5) is stored, listed, or displayed anywhere

### US-002: Support decimal and negative number entry

| ID | Criterion | Level | Title | Status | Result |
|---|---|---|---|---|---|
| TC-006 | AC-003 | e2e | Sum of a decimal number and an integer preserves decimal precision | approved | not run |
| TC-007 | AC-003 | e2e | Sum of two decimal numbers with multiple decimal places | approved | not run |
| TC-008 | AC-004 | e2e | Sum with one negative number is calculated correctly | approved | not run |
| TC-009 | AC-004 | e2e | Sum with both fields negative produces a negative result | approved | not run |

#### TC-006: Sum of a decimal number and an integer preserves decimal precision

**Criterion:** AC-003 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with both input fields empty

**Steps:**

1. Open the calculator page
2. Enter '3.14' into the first input field
3. Enter '2' into the second input field
4. Click the calculate button

**Expected result:** The result displayed is '5.14', with the decimal precision from the input preserved

#### TC-007: Sum of two decimal numbers with multiple decimal places

**Criterion:** AC-003 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with both input fields empty

**Steps:**

1. Open the calculator page
2. Enter '1.25' into the first input field
3. Enter '2.5' into the second input field
4. Click the calculate button

**Expected result:** The result displayed is '3.75', accurately reflecting the decimal values entered

#### TC-008: Sum with one negative number is calculated correctly

**Criterion:** AC-004 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with both input fields empty

**Steps:**

1. Open the calculator page
2. Enter '-5' into the first input field
3. Enter '10' into the second input field
4. Click the calculate button

**Expected result:** The result displayed is '5', correctly accounting for the negative value

#### TC-009: Sum with both fields negative produces a negative result

**Criterion:** AC-004 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with both input fields empty

**Steps:**

1. Open the calculator page
2. Enter '-5' into the first input field
3. Enter '-3' into the second input field
4. Click the calculate button

**Expected result:** The result displayed is '-8', correctly computed as the sum of two negative values

### US-003: Reject non-numeric input with inline validation

| ID | Criterion | Level | Title | Status | Result |
|---|---|---|---|---|---|
| TC-010 | AC-005 | e2e | Non-numeric text in first field triggers inline validation | approved | not run |
| TC-011 | AC-005 | e2e | Non-numeric symbols in second field triggers inline validation | approved | not run |
| TC-012 | AC-005 | e2e | Non-numeric text in both fields triggers validation on both | approved | not run |
| TC-013 | AC-006 | e2e | Correcting invalid input clears the validation message and allows calculation | approved | not run |
| TC-014 | AC-007 | e2e | Leaving both fields empty triggers required-number validation | approved | not run |
| TC-015 | AC-007 | e2e | Leaving one field empty triggers required-number validation on that field | approved | not run |

#### TC-010: Non-numeric text in first field triggers inline validation

**Criterion:** AC-005 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with both input fields empty

**Steps:**

1. Enter 'abc' into the first number input field
2. Enter '5' into the second number input field
3. Click the Calculate button

**Expected result:** An inline validation message is displayed next to the first input field, and no sum result is shown

#### TC-011: Non-numeric symbols in second field triggers inline validation

**Criterion:** AC-005 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with both input fields empty

**Steps:**

1. Enter '10' into the first number input field
2. Enter '#@!' into the second number input field
3. Click the Calculate button

**Expected result:** An inline validation message is displayed next to the second input field, and no sum result is shown

#### TC-012: Non-numeric text in both fields triggers validation on both

**Criterion:** AC-005 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with both input fields empty

**Steps:**

1. Enter 'xyz' into the first number input field
2. Enter '???' into the second number input field
3. Click the Calculate button

**Expected result:** An inline validation message is displayed near each offending field, and no sum result is shown

#### TC-013: Correcting invalid input clears the validation message and allows calculation

**Criterion:** AC-006 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded and an inline validation message is currently displayed because the first field contains 'abc' and the second field contains '5'

**Steps:**

1. Clear the first input field
2. Enter '7' into the first input field
3. Click the Calculate button

**Expected result:** The inline validation message is no longer displayed and the correct sum (12) is shown

#### TC-014: Leaving both fields empty triggers required-number validation

**Criterion:** AC-007 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with both input fields empty

**Steps:**

1. Leave both input fields empty
2. Click the Calculate button

**Expected result:** An inline validation message indicating a number is required is displayed near the empty fields, and no sum result is shown

#### TC-015: Leaving one field empty triggers required-number validation on that field

**Criterion:** AC-007 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded with both input fields empty

**Steps:**

1. Enter '8' into the first input field
2. Leave the second input field empty
3. Click the Calculate button

**Expected result:** An inline validation message indicating a number is required is displayed near the second input field, and no sum result is shown

### US-004: Perform calculation without persisting data

| ID | Criterion | Level | Title | Status | Result |
|---|---|---|---|---|---|
| TC-016 | AC-008 | e2e | No previous inputs or results shown after page refresh | approved | not run |
| TC-017 | AC-008 | e2e | No previous inputs or results retrievable after leaving and returning to the page | approved | not run |
| TC-018 | AC-009 | e2e | Calculation result returned without writing data to persistent storage | approved | not run |
| TC-019 | AC-009 | e2e | Repeated calculations do not accumulate any visible history | approved | not run |

#### TC-016: No previous inputs or results shown after page refresh

**Criterion:** AC-008 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** User is on the calculation page

**Steps:**

1. Enter two numbers into the input fields
2. Click the calculate button
3. Observe the displayed result
4. Refresh the page

**Expected result:** The page loads with empty input fields and no result displayed; no previous inputs or results are shown

#### TC-017: No previous inputs or results retrievable after leaving and returning to the page

**Criterion:** AC-008 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** User is on the calculation page

**Steps:**

1. Enter two numbers into the input fields
2. Click the calculate button
3. Observe the displayed result
4. Navigate away from the page to another URL
5. Return to the calculation page

**Expected result:** The page shows empty input fields and no result; no history or record of the previous calculation is visible or accessible

#### TC-018: Calculation result returned without writing data to persistent storage

**Criterion:** AC-009 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** User is on the calculation page

**Steps:**

1. Enter two valid numbers into the input fields
2. Click the calculate button
3. Observe the result displayed on the page
4. Refresh the page or open the page in a new browser session

**Expected result:** The correct sum is returned and displayed immediately after calculation, and no trace of the calculation (inputs or result) is visible or retrievable in the new session, confirming no persistent store was written to

#### TC-019: Repeated calculations do not accumulate any visible history

**Criterion:** AC-009 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** User is on the calculation page

**Steps:**

1. Enter a first pair of numbers and click calculate
2. Observe the result
3. Enter a second, different pair of numbers and click calculate
4. Observe the result

**Expected result:** Only the most recent result is displayed each time; no list, log, or history of prior calculations appears anywhere on the page

### US-005: Access the calculator without logging in

| ID | Criterion | Level | Title | Status | Result |
|---|---|---|---|---|---|
| TC-020 | AC-010 | e2e | Calculator loads and is usable via direct link without login | approved | not run |
| TC-021 | AC-010 | e2e | Calculator page accessible without any prior navigation or session | approved | not run |
| TC-022 | AC-011 | e2e | No login or sign-up screens exist anywhere in the application | approved | not run |
| TC-023 | AC-011 | e2e | No hidden account-related UI elements are present on the page | approved | not run |

#### TC-020: Calculator loads and is usable via direct link without login

**Criterion:** AC-010 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** Tester has the direct URL to the calculator page and no active session or credentials

**Steps:**

1. Open a new browser session with no stored cookies or session data
2. Enter the direct link to the calculator page in the address bar
3. Press Enter to navigate to the page
4. Observe the page that loads
5. Enter two numbers into the calculator input fields
6. Click the button to perform the addition

**Expected result:** The calculator page loads fully with no login, sign-up, or authentication prompt displayed, and the addition operation completes successfully showing the correct result

#### TC-021: Calculator page accessible without any prior navigation or session

**Criterion:** AC-010 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** Tester has never visited the application before and has no account

**Steps:**

1. Open a fresh incognito/private browser window
2. Paste the calculator page link directly into the address bar
3. Navigate to the link

**Expected result:** The calculator page loads immediately and all calculator controls are interactive, with no redirect to a login or sign-up page and no authentication barrier of any kind

#### TC-022: No login or sign-up screens exist anywhere in the application

**Criterion:** AC-011 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** Tester is on the calculator page

**Steps:**

1. Visually inspect the full calculator page layout
2. Check the page header, footer, and any menus or navigation elements for account-related links
3. Attempt to navigate to common login/sign-up URL paths if known (e.g., /login, /signup) via the address bar
4. Observe the result of each navigation attempt

**Expected result:** No login, sign-up, or any account-related controls, links, or screens are found anywhere on the calculator page or via direct URL navigation; attempts to reach login/sign-up paths do not reveal any such screens

#### TC-023: No hidden account-related UI elements are present on the page

**Criterion:** AC-011 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** Tester is on the calculator page

**Steps:**

1. Scroll through the entire calculator page from top to bottom
2. Inspect all visible buttons, icons, and menu items on the page
3. Check for any user profile icon, account settings, or 'sign in' text anywhere on the page

**Expected result:** No account-related UI elements, icons, or text (such as 'Login', 'Sign up', 'Sign in', or profile icons) are present anywhere on the page

### US-006: View basic usage instructions

| ID | Criterion | Level | Title | Status | Result |
|---|---|---|---|---|---|
| TC-024 | AC-012 | e2e | Instructional text is visible when calculator page loads | approved | not run |
| TC-025 | AC-012 | e2e | Instructional text content describes entering two numbers and getting the sum | approved | not run |
| TC-026 | AC-012 | e2e | Instructions remain visible without requiring user interaction | approved | not run |

#### TC-024: Instructional text is visible when calculator page loads

**Criterion:** AC-012 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator application is accessible via browser

**Steps:**

1. Open the calculator page in a browser
2. Observe the page without scrolling or clicking anything

**Expected result:** A short block of instructional text is visible on the page explaining how to enter two numbers and obtain their sum

#### TC-025: Instructional text content describes entering two numbers and getting the sum

**Criterion:** AC-012 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded

**Steps:**

1. Open the calculator page in a browser
2. Read the instructional text displayed on the page

**Expected result:** The instructional text clearly mentions entering two numbers and how to obtain the resulting sum, in brief, understandable language

#### TC-026: Instructions remain visible without requiring user interaction

**Criterion:** AC-012 · **Level:** e2e · **Status:** approved · **Result:** not run

**Preconditions:** The calculator page is loaded for the first time, no prior interaction

**Steps:**

1. Open the calculator page as a first-time visitor
2. Do not click, type, or scroll
3. Check whether the instructional text is already displayed

**Expected result:** The instructional text is displayed by default without needing any click, hover, or scroll action
<!-- sdlc:auto:end cases -->
