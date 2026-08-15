# 📱 Mobile E-Commerce Application — Manual QA & API Testing

A complete, professional QA portfolio project demonstrating manual mobile application testing, test case design, bug reporting, regression testing, and REST API testing.

---

## 📋 Overview

This project contains end-to-end QA testing artifacts for the **Sauce Labs My Demo App** for Android — a demo e-commerce mobile application. The project is structured as a practical QA portfolio demonstrating industry-standard testing practices for a **QA Intern** application.

---

## 🎯 Application Under Test

| Detail | Value |
|--------|-------|
| **Application** | Sauce Labs My Demo App — Android |
| **Version** | 2.2.0 (Build 25) |
| **APK** | mda-2.2.0-25.apk |
| **Package Name** | com.saucelabs.mydemoapp.android |
| **Type** | E-commerce Demo Application |
| **Official Repository** | [saucelabs/my-demo-app-android](https://github.com/saucelabs/my-demo-app-android) |
| **Release Used** | [v2.2.0](https://github.com/saucelabs/my-demo-app-android/releases/tag/2.2.0) |
| **Official Documentation** | [Sauce Labs Mobile Apps](https://docs.saucelabs.com/mobile-apps/) |

---

## 🎯 Objective

Demonstrate competence in manual QA testing practices aligned with the requirements of a **QA Intern** position, specifically:

- Android mobile application testing
- Test case design and execution
- Bug identification and reporting
- Regression testing
- REST API testing with Postman
- Professional QA documentation

---

## 🔍 Testing Scope

### In Scope
- ✅ Application launch and stability
- ✅ Login/authentication (valid, invalid, empty credentials)
- ✅ Product catalog and listing
- ✅ Product details and color selection
- ✅ Product sorting (name, price)
- ✅ Add to cart, cart management, quantity changes
- ✅ Checkout flow and form validation
- ✅ Navigation (menu, back button)
- ✅ Negative and boundary testing
- ✅ UI consistency
- ✅ App relaunch behavior
- ✅ Regression smoke suite
- ✅ REST API testing (JSONPlaceholder)

### Out of Scope
- ❌ SQL/database testing
- ❌ Test automation (Selenium/Appium)
- ❌ Performance/load testing
- ❌ Security/penetration testing
- ❌ iOS testing
- ❌ Real payment transactions

---

## 🧪 Testing Types

| Type | Description |
|------|-------------|
| **Functional Testing** | Verify core features work as expected |
| **Negative Testing** | Invalid inputs, empty fields, boundary values |
| **UI Testing** | Visual elements, layout, text readability |
| **Navigation Testing** | Screen transitions, back button, menu |
| **Regression Testing** | Critical-path smoke suite |
| **API Testing** | REST API validation with Postman/curl |

---

## 🛠️ Tools

| Tool | Purpose |
|------|---------|
| Git | Version control |
| Markdown | Documentation |
| Python / openpyxl | Excel spreadsheet creation |
| curl | API testing execution |
| Newman | Postman collection CLI runner |
| Postman Collection | API test export format |

---

## 🖥️ Test Environment

| Parameter | Value |
|-----------|-------|
| Tester | Bhaskar Danu |
| OS | Windows |
| Android Device | **Not available** (no emulator or physical device) |
| App Version | 2.2.0 (Build 25) |
| API Testing | curl (command line) |
| Testing Date | 2026-08-15 |

---

## 📊 Test Case Summary

| Category | Count |
|----------|-------|
| **Total Mobile Test Cases** | 37 |
| **Regression Test Cases** | 12 |
| **API Test Cases** | 10 |
| **Total** | **59** |

---

## 📈 Execution Summary

### Mobile Application Testing

| Metric | Count |
|--------|-------|
| Designed | 37 |
| Executed | 0 |
| Passed | 0 |
| Failed | 0 |
| Not Executed | 37 |

> ⚠️ **Note:** Mobile test cases were not executed due to the absence of an Android emulator or physical device in the testing environment. All test cases are fully designed and ready for execution.

### API Testing

| Metric | Count |
|--------|-------|
| Designed | 10 |
| Executed | 10 |
| Passed | 10 |
| Failed | 0 |
| **Pass Rate** | **100%** |

---

## 🐛 Bug Summary

| Severity | Count |
|----------|-------|
| Critical | 0 |
| High | 0 |
| Medium | 0 |
| Low | 0 |
| **Total** | **0** |

> No defects were reported because mobile test cases were not executed. No fabricated bugs were created.

---

## 🔄 Regression Summary

- **Regression Cases Designed:** 12 critical user flows
- **Execution Status:** NOT EXECUTED (no Android environment)
- **Coverage:** Login, product browsing, cart operations, checkout, navigation, app relaunch

---

## 🌐 API Testing Summary

- **API Used:** [JSONPlaceholder](https://jsonplaceholder.typicode.com) (public testing API)
- **Purpose:** Supporting REST API testing practice
- **Methods Tested:** GET, POST, PUT, PATCH, DELETE
- **Tests Executed:** 10
- **All Passed:** ✅
- **Postman Collection:** Exported as JSON with test assertions

---

## 📸 Screenshots / Evidence

| Type | Status |
|------|--------|
| Application Screenshots | Not captured (no Android environment) |
| Bug Screenshots | Not captured (no bugs — no execution) |
| API Test Evidence | Documented in API-Test-Report.md |

---

## 📁 Repository Structure

```
mobile-ecommerce-qa-testing/
│
├── README.md                              ← Project overview
│
├── 01-Test-Plan/
│   └── Test-Plan.md                       ← Test plan with scope, strategy, environment
│
├── 02-Test-Cases/
│   └── Mobile-App-Test-Cases.xlsx         ← 37 manual test cases
│
├── 03-Test-Execution/
│   └── Test-Execution-Report.xlsx         ← Test execution tracking
│
├── 04-Bug-Reports/
│   └── Bug-Reports.xlsx                   ← Bug report template (no bugs found)
│
├── 05-Regression/
│   └── Regression-Test-Suite.xlsx         ← 12 regression test cases
│
├── 06-API-Testing/
│   ├── Postman-Collection.json            ← Exported Postman collection
│   ├── API-Test-Cases.xlsx                ← 10 API test cases
│   └── API-Test-Report.md                 ← Detailed API test results
│
├── 07-Screenshots/
│   ├── application/                       ← App screenshots (pending execution)
│   ├── bugs/                              ← Bug evidence (pending execution)
│   └── api/                               ← API test evidence
│
├── 08-Test-Summary/
│   └── Final-Test-Summary.md              ← Final metrics and summary
│
├── 09-Project-Report/
│   └── QA-Project-Report.md              ← Complete project report
│
├── resume-project-entry.md                ← Resume-ready project description
└── interview-preparation.md               ← Interview Q&A based on project
```

---

## ⚠️ Limitations

1. **No Android Execution Environment:** The testing setup did not include Android Studio, Android SDK, an emulator, a physical device, or Sauce Labs cloud access. All mobile test cases are designed but not executed.
2. **No Application Screenshots:** Cannot capture real app screenshots without an Android device.
3. **No Bug Discovery:** Cannot identify genuine defects without test execution.
4. **No Jira:** Bug reports use Jira-style format in spreadsheets, not an actual Jira instance.
5. **No iOS Testing:** iOS environment not available.

---

## ✅ Conclusion

This project demonstrates the complete QA testing lifecycle — from test planning and test case design through regression suite creation and API testing. While the Android execution environment was unavailable, the project showcases:

- **Systematic test design** with 37 well-structured test cases
- **Comprehensive coverage** across 11 application modules
- **Real API testing** with 10 executed tests and 100% pass rate
- **Professional documentation** following industry QA standards
- **Honest reporting** with clear distinction between designed and executed

The test cases and documentation are ready for immediate use when an Android testing environment becomes available.

---

## 📚 References

- [Sauce Labs My Demo App — Android (GitHub)](https://github.com/saucelabs/my-demo-app-android)
- [Sauce Labs Mobile Apps Documentation](https://docs.saucelabs.com/mobile-apps/)
- [JSONPlaceholder — Free Testing API](https://jsonplaceholder.typicode.com)
- [Sauce Labs Official Website](https://saucelabs.com)

---

*Built as a QA portfolio project for a QA Intern application.*
