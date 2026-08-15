# QA Project Report — Mobile E-Commerce Application

**Project Title:** Mobile E-Commerce Application — Manual QA & API Testing  
**Application:** Sauce Labs My Demo App — Android v2.2.0 (Build 25)  
**Author:** Bhaskar Danu  
**Date:** 2026-08-15  
**Version:** 1.0  

---

## 1. Executive Summary

This QA portfolio project demonstrates end-to-end manual quality assurance testing practices applied to the **Sauce Labs My Demo App** for Android — a demo e-commerce mobile application. The project was designed to align with the requirements of a **QA Intern** position at **Noise**, covering manual mobile testing, test case design, bug reporting, regression testing, and basic REST API testing.

**Key Outcomes:**
- 37 manual test cases designed covering 11 modules
- 12 regression test cases for critical user flows
- 10 API test cases designed and executed (100% pass rate)
- Complete professional QA documentation portfolio

**Limitation:** No Android execution environment was available in the testing setup. Mobile test cases were designed but not executed. This is documented transparently.

---

## 2. Application Under Test

| Detail | Value |
|--------|-------|
| **Application Name** | Sauce Labs My Demo App — Android |
| **Version** | 2.2.0 (Build 25) |
| **APK File** | mda-2.2.0-25.apk |
| **Package Name** | com.saucelabs.mydemoapp.android |
| **Developer** | Sauce Labs |
| **Repository** | [saucelabs/my-demo-app-android](https://github.com/saucelabs/my-demo-app-android) |
| **Release** | [v2.2.0](https://github.com/saucelabs/my-demo-app-android/releases/tag/2.2.0) |
| **App Type** | E-commerce demo application |
| **Platform** | Android |

### Application Features (from official repository and source analysis)

| Feature | Description |
|---------|-------------|
| Product Catalog | Grid display of products with images, names, and prices |
| Product Details | Detailed view with description, color selector, add to cart |
| Cart | View items, change quantities, remove items |
| Checkout | Multi-step: shipping → payment → review → confirmation |
| Login | Username/password authentication with test credentials |
| Sorting | Sort by name (A-Z, Z-A) and price (Low-High, High-Low) |
| Navigation | Hamburger menu, bottom navigation, Android back button |
| QR Code Scanner | In-app QR code scanning capability |
| Biometric Login | Fingerprint/biometric authentication option |
| Drawing | In-app drawing feature |
| Geo Location | Location-based feature |
| Webview | Embedded web content viewer |

### Known Test Credentials

| Username | Password |
|----------|----------|
| bob@example.com | 10203040 |

---

## 3. Project Objective

The primary objective of this project is to create a **complete, professional, evidence-based QA portfolio** that demonstrates:

1. **Test Planning** — Structured approach to defining scope, strategy, and resources
2. **Test Case Design** — Comprehensive test cases covering functional, negative, UI, and navigation scenarios
3. **Test Execution** — Systematic test execution with evidence capture (where environment permits)
4. **Defect Reporting** — Jira-style bug reports with severity, priority, and reproduction steps
5. **Regression Testing** — Critical-path smoke suite for ongoing quality verification
6. **API Testing** — REST API testing with Postman/curl demonstrating HTTP methods and assertions
7. **Documentation** — Professional QA artifacts organized for GitHub portfolio

---

## 4. Target Job Alignment

This project is specifically designed to demonstrate skills relevant to the **QA Intern — Noise** position:

| Job Requirement | Project Demonstration |
|----------------|----------------------|
| Android/iOS mobile application testing | Test cases designed for Android app (Sauce Labs My Demo App) |
| Test case execution | 37 test cases with preconditions, steps, expected results |
| Bug reporting | Jira-style bug report format with severity/priority |
| Bug-fix verification | Retesting workflow documented in regression suite |
| Regression testing | 12-case regression smoke suite |
| Test case and test report creation | Excel-based test cases + execution reports |
| Working with developers/product managers | Agile workflow simulation section |
| Agile workflow awareness | Sprint-mapped QA activities |
| Android basics | App structure, navigation, lifecycle testing |
| Jira/bug-tracking tools | Jira-style defect documentation format |
| Postman | Postman collection with test assertions |
| API testing | 10 REST API tests with real execution |

---

## 5. Scope

### In Scope

- Application launch and basic stability
- Login/authentication (valid, invalid, empty credentials)
- Product catalog and listing
- Product details view
- Product sorting (name, price)
- Add to cart functionality
- Cart management (quantities, removal, totals)
- Checkout flow and form validation
- Navigation (menu, back button, screen transitions)
- Negative testing (invalid data, boundary values)
- UI consistency checks
- App relaunch behavior
- Regression smoke testing
- REST API testing (JSONPlaceholder)

### Out of Scope

- SQL/database testing
- Automation (Selenium, Appium)
- Performance/load testing
- Security/penetration testing
- iOS testing
- Real payment transactions
- Source code review

---

## 6. Test Environment

| Parameter | Value |
|-----------|-------|
| **Tester** | Bhaskar Danu |
| **Operating System** | Windows |
| **Android Device** | Not available |
| **Android Version** | Not available |
| **App Version** | 2.2.0 (Build 25) |
| **APK** | mda-2.2.0-25.apk |
| **Package Name** | com.saucelabs.mydemoapp.android |
| **Installation Source** | GitHub Releases (https://github.com/saucelabs/my-demo-app-android/releases/tag/2.2.0) |
| **Network** | Not applicable |
| **Screen Resolution** | Not available |
| **Testing Date** | 2026-08-15 |
| **QA Tools** | Git, Markdown, Python/openpyxl, curl, Newman |
| **API Testing Tool** | curl (command line) |
| **Version Control** | Git v2.55.0 |
| **Known Limitation** | No Android emulator, SDK, physical device, or Sauce Labs cloud access |

---

## 7. Test Strategy

### 7.1 Testing Types Applied

| Type | Description | Execution Status |
|------|-------------|-----------------|
| Functional Testing | Verify features work correctly | NOT EXECUTED (designed) |
| Negative Testing | Invalid inputs and error handling | NOT EXECUTED (designed) |
| UI Testing | Visual elements and layout | NOT EXECUTED (designed) |
| Navigation Testing | Screen transitions and back button | NOT EXECUTED (designed) |
| Boundary Testing | Edge cases and limits | NOT EXECUTED (designed) |
| Regression Testing | Critical-path smoke suite | NOT EXECUTED (designed) |
| API Testing | REST API validation | ✅ EXECUTED |

### 7.2 Test Design Techniques

- **Equivalence Partitioning:** Valid/invalid input classes for login and checkout
- **Boundary Value Analysis:** Cart quantity limits, form field lengths
- **Error Guessing:** Common mobile app issues (back button, relaunch)
- **User Flow Coverage:** End-to-end critical paths (browse → cart → checkout)

---

## 8. Test Scenarios

15 test scenarios were identified covering the complete application:

| ID | Scenario | Priority |
|----|----------|----------|
| TS-01 | Installation and application launch | Critical |
| TS-02 | Login/authentication flows | Critical |
| TS-03 | Home screen and navigation | High |
| TS-04 | Product listing and catalog | High |
| TS-05 | Product details view | High |
| TS-06 | Sort/filter products | Medium |
| TS-07 | Add product to cart | Critical |
| TS-08 | Cart management | Critical |
| TS-09 | Checkout flow | Critical |
| TS-10 | Form validation and negative scenarios | High |
| TS-11 | Android back navigation and state | Medium |
| TS-12 | Network/error handling | Medium |
| TS-13 | UI/usability consistency | Medium |
| TS-14 | App relaunch/state persistence | Medium |
| TS-15 | Regression smoke suite | Critical |

---

## 9. Test Cases

**Total Test Cases Designed:** 37

Test cases are documented in `02-Test-Cases/Mobile-App-Test-Cases.xlsx` with the following coverage:

| Module | Test Cases | Priority Breakdown |
|--------|-----------|-------------------|
| App Launch | 2 | 1 Critical, 1 High |
| Authentication | 4 | 2 Critical, 1 High, 1 Medium |
| Product Catalog | 4 | 1 High, 2 Medium, 1 High |
| Product Details | 3 | 1 High, 1 Medium, 1 Medium |
| Sorting | 3 | 1 High, 1 Medium, 1 Medium |
| Cart | 6 | 2 Critical, 2 High, 2 Medium |
| Checkout | 4 | 2 Critical, 2 High |
| Navigation | 3 | 1 High, 1 Medium, 1 Medium |
| Negative/Boundary | 4 | 1 High, 2 Medium, 1 Low |
| App Lifecycle | 2 | 1 High, 1 Medium |
| UI Consistency | 2 | 2 Medium |

Each test case includes: ID, Module, Scenario, Preconditions, Test Data, Steps, Expected Result, Priority, Actual Result, Status, Defect ID, and Evidence reference.

---

## 10. Test Execution

### 10.1 Mobile Application Testing

**Execution Status: NOT EXECUTED**

All 37 mobile test cases have Status = NOT EXECUTED due to the absence of an Android execution environment. The test execution report is available in `03-Test-Execution/Test-Execution-Report.xlsx`.

| Metric | Count |
|--------|-------|
| Total Designed | 37 |
| Executed | 0 |
| Passed | 0 |
| Failed | 0 |
| Blocked | 0 |
| Not Executed | 37 |

### 10.2 API Testing

**Execution Status: COMPLETED**

All 10 API test cases were executed using curl commands against the JSONPlaceholder API. Results are documented with actual response data.

| Metric | Count |
|--------|-------|
| Total Designed | 10 |
| Executed | 10 |
| Passed | 10 |
| Failed | 0 |
| Pass Rate | 100% |

---

## 11. Defect Reports

**Total Defects Found: 0**

No defects were reported because mobile test cases were not executed. The bug report template is available in `04-Bug-Reports/Bug-Reports.xlsx` with proper column structure, ready for use when testing is performed.

> **Honesty Note:** No fabricated bugs were created. Defects would only be reported based on actual observed behavior during test execution.

---

## 12. Screenshots/Evidence

### 12.1 Mobile Application Screenshots

**Status:** Not captured — no Android environment available.

The `07-Screenshots/application/` and `07-Screenshots/bugs/` directories are created and ready for evidence when Android testing is performed.

### 12.2 API Testing Evidence

API test evidence (curl command outputs) is documented in `06-API-Testing/API-Test-Report.md` with actual response data from real API calls.

---

## 13. Regression Testing

**Regression Suite:** 12 critical test cases covering the highest-risk user flows.

| Reg ID | Area | Test Cases Covered |
|--------|------|--------------------|
| REG-001 | Login | TC-003, TC-004 |
| REG-002 | Product Catalog | TC-007, TC-008 |
| REG-003 | Product Details | TC-009, TC-011 |
| REG-004 | Sorting | TC-012 |
| REG-005 | Add to Cart | TC-015, TC-016 |
| REG-006 | Cart - Quantity | TC-018, TC-019 |
| REG-007 | Cart - Remove | TC-020 |
| REG-008 | Cart - Total | TC-021 |
| REG-009 | Checkout Navigation | TC-022 |
| REG-010 | Checkout Validation | TC-023 |
| REG-011 | Back Navigation | TC-025 |
| REG-012 | App Relaunch | TC-029 |

**Regression Status:** NOT EXECUTED (no Android environment).

The regression suite is documented in `05-Regression/Regression-Test-Suite.xlsx` and is ready for execution.

---

## 14. API Testing

### 14.1 Overview

API testing is included as a **supporting component** to demonstrate REST API testing skills, as required by the Noise QA Intern job description.

**API Used:** JSONPlaceholder (https://jsonplaceholder.typicode.com)  
**Label:** Supporting REST API Testing Practice

> **Note:** This API is separate from the mobile app's internal API. It is used to demonstrate Postman/API testing competency.

### 14.2 Tests Performed

| ID | Method | Endpoint | Expected Status | Result |
|----|--------|----------|----------------|--------|
| API-001 | GET | /posts/1 | 200 | PASS |
| API-002 | GET | /posts/99999 | 404 | PASS |
| API-003 | POST | /posts | 201 | PASS |
| API-004 | POST | /posts (invalid) | 201 | PASS |
| API-005 | PUT | /posts/1 | 200 | PASS |
| API-006 | PATCH | /posts/1 | 200 | PASS |
| API-007 | DELETE | /posts/1 | 200 | PASS |
| API-008 | GET | /users | 200 | PASS |
| API-009 | GET | /users/1 | 200 | PASS |
| API-010 | GET | /comments?postId=1 | 200 | PASS |

### 14.3 Postman Collection

A Postman Collection (v2.1 format) has been exported as `06-API-Testing/Postman-Collection.json`. The collection includes:
- All 10 API requests
- Test assertions (status code, response body, response time)
- Can be imported into Postman for interactive execution

### 14.4 Key Validations

- **Status Code Validation:** All responses matched expected HTTP status codes
- **Response Body Validation:** JSON response properties verified (id, title, body, userId)
- **Response Time:** All responses returned within acceptable timeframes
- **Negative Scenario:** Invalid resource (404) and missing-field POST handled correctly

---

## 15. Test Summary / Metrics

### Overall Metrics

| Category | Designed | Executed | Passed | Failed | Not Executed |
|----------|----------|----------|--------|--------|-------------|
| Mobile Test Cases | 37 | 0 | 0 | 0 | 37 |
| Regression Cases | 12 | 0 | 0 | 0 | 12 |
| API Test Cases | 10 | 10 | 10 | 0 | 0 |
| **Total** | **59** | **10** | **10** | **0** | **49** |

### Defect Metrics

| Severity | Count |
|----------|-------|
| Critical | 0 |
| High | 0 |
| Medium | 0 |
| Low | 0 |
| **Total** | **0** |

---

## 16. Risks and Limitations

### 16.1 Risks

| Risk | Impact | Status |
|------|--------|--------|
| No Android environment | Cannot verify actual app behavior | Materialized |
| Demo app limitations | Some features may behave differently than production apps | Acknowledged |
| App version changes | Test cases may need updates for newer versions | Documented version |

### 16.2 Limitations

1. **No Android Execution:** The primary limitation — all mobile test cases are designed but unexecuted
2. **No Screenshots:** Cannot capture real application screenshots without an Android device
3. **No Bug Discovery:** Cannot identify genuine defects without execution
4. **No Jira:** Bug reports use Jira-style format in spreadsheets, not actual Jira
5. **No iOS Testing:** iOS environment not available
6. **No Sauce Labs Cloud:** No access to Sauce Labs device cloud for remote testing

---

## 17. Lessons Learned

1. **Environment Setup is Critical:** The biggest blocker was the absence of an Android runtime environment. In a real QA role, ensuring the test environment is available before sprint testing begins is essential.

2. **Test Design is Valuable Independently:** Even without execution, designing comprehensive test cases demonstrates systematic thinking and coverage analysis.

3. **API Testing is Portable:** Unlike mobile testing, API testing can be performed from any environment with HTTP access, making it a valuable skill.

4. **Honest Documentation Matters:** Transparently documenting what was and wasn't executed builds credibility over fabricating results.

5. **Tool Flexibility:** When one tool isn't available (e.g., Postman GUI), alternatives (curl, Newman) can achieve the same goals.

---

## 18. Conclusion

This project demonstrates the ability to plan, design, and document a complete QA testing effort for a mobile e-commerce application. While Android test execution was not possible due to environment constraints, the project showcases:

- **Thorough test case design** (37 cases across 11 modules)
- **Structured QA documentation** (test plan, execution reports, bug report templates)
- **Real API testing** (10 tests, 100% pass rate)
- **Professional project organization** (GitHub-ready structure)
- **Honest reporting** (clear distinction between designed and executed)

The test cases, regression suite, and documentation are ready for immediate use when an Android testing environment becomes available.

---

## 19. GitHub Structure

```
mobile-ecommerce-qa-testing/
├── README.md
├── 01-Test-Plan/
│   └── Test-Plan.md
├── 02-Test-Cases/
│   └── Mobile-App-Test-Cases.xlsx
├── 03-Test-Execution/
│   └── Test-Execution-Report.xlsx
├── 04-Bug-Reports/
│   └── Bug-Reports.xlsx
├── 05-Regression/
│   └── Regression-Test-Suite.xlsx
├── 06-API-Testing/
│   ├── Postman-Collection.json
│   ├── API-Test-Cases.xlsx
│   └── API-Test-Report.md
├── 07-Screenshots/
│   ├── application/
│   ├── bugs/
│   └── api/
├── 08-Test-Summary/
│   └── Final-Test-Summary.md
├── 09-Project-Report/
│   └── QA-Project-Report.md
├── resume-project-entry.md
└── interview-preparation.md
```

---

*End of QA Project Report*
