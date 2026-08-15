# Interview Preparation — QA Project Q&A

Based on the completed **Mobile E-Commerce Application — QA Testing Project**.

---

## Q1: Tell me about your QA project.

**Answer:** I built a complete QA portfolio project testing the Sauce Labs My Demo App for Android, which is an e-commerce demo application. I designed 37 manual test cases covering 11 modules — app launch, login, product catalog, product details, sorting, cart management, checkout, navigation, negative testing, UI consistency, and app lifecycle. I also created a 12-case regression smoke suite for critical user flows. Additionally, I performed REST API testing using curl against the JSONPlaceholder API, executing 10 test cases covering GET, POST, PUT, PATCH, and DELETE methods with a 100% pass rate. All QA artifacts are organized in a GitHub-ready repository structure.

**Important clarification:** My testing environment did not have an Android emulator or device, so the mobile test cases were designed but not executed. I documented this limitation honestly. The API tests were actually executed with real responses.

---

## Q2: Why did you choose this application?

**Answer:** I chose the Sauce Labs My Demo App because it is a well-known, open-source Android demo application specifically designed for QA testing purposes. It has a realistic e-commerce workflow — product listing, cart, checkout — which provides comprehensive testing scenarios. Since the target role at Noise involves Android mobile testing, this app directly demonstrates relevant skills. The app is publicly available on GitHub (version 2.2.0) with documented features and known test credentials.

---

## Q3: How did you create test cases?

**Answer:** I followed a structured approach:
1. First, I studied the application by reviewing the official GitHub repository, README, and source code to understand the actual features, screens, and user flows
2. I identified 15 test scenarios covering all major modules
3. I designed individual test cases with detailed preconditions, test data, step-by-step instructions, and expected results
4. I assigned priority (Critical/High/Medium/Low) based on business impact and user flow criticality
5. I used techniques like equivalence partitioning (valid/invalid inputs), boundary value analysis (cart quantities, field lengths), and error guessing (back button behavior, app relaunch)
6. Each test case was given a unique ID and linked to its scenario and module

---

## Q4: What is a test scenario? What is a test case?

**Answer:**
- **Test Scenario:** A high-level description of a functionality to test. Example: "Login/authentication flows" — it describes WHAT to test, not HOW.
- **Test Case:** A detailed, step-by-step instruction for testing a specific condition within a scenario. Example: "TC-003: Log in with valid credentials (bob@example.com / 10203040) and verify successful login" — it describes exactly HOW to test.

In my project, I had 15 test scenarios and 37 test cases. Each scenario typically maps to multiple test cases.

---

## Q5: How did you prioritize tests?

**Answer:** I used a four-level priority system:
- **Critical:** Core functionality that blocks the user if broken — login, add to cart, checkout. These must work for the app to be usable.
- **High:** Important features that significantly impact user experience — product listing, product details, sorting, checkout validation
- **Medium:** Supporting features that affect quality but have workarounds — UI consistency, back navigation, app relaunch
- **Low:** Minor issues that don't significantly impact functionality — cosmetic details

I prioritized based on business impact (what would prevent a sale?) and user frequency (what do users do most?).

---

## Q6: Explain severity vs priority.

**Answer:**
- **Severity** measures the technical impact of a defect on the system — how badly broken it is. A crash is Critical severity; a misaligned button is Low severity.
- **Priority** measures the business urgency of fixing it — how soon it needs to be fixed. A typo on the login page might be Low severity but High priority because it's the first thing users see.

Example: A crash in the QR Code Scanner is Critical severity but might be Medium priority if few users use that feature. Conversely, a wrong price displayed on a product is Medium severity but Critical priority because it directly affects purchases.

They're related but independent — a defect can be high severity but low priority, or vice versa.

---

## Q7: Explain one real bug you found (or what you would do if you found one).

**Answer:** In this project, I did not find any bugs because I could not execute the mobile test cases due to the absence of an Android environment. I want to be honest about that rather than fabricating a bug story.

However, if I had found a bug — say, the cart total not updating when increasing item quantity — I would:
1. Reproduce it multiple times to confirm it's consistent
2. Document the exact steps to reproduce
3. Capture a screenshot showing the incorrect behavior
4. Record the expected result (total should update) vs actual result (total remains unchanged)
5. Assign severity (Medium — functional issue with workaround) and priority (High — affects purchase flow)
6. Create a bug report with all details and link it to the relevant test case
7. Share it with the developer for investigation

---

## Q8: How did you reproduce a bug? / What is bug reproduction?

**Answer:** Bug reproduction means following the exact same steps that caused the bug to occur, to verify that it happens consistently rather than being a one-time occurrence. This is essential because:
1. It confirms the bug is genuine, not caused by a temporary network issue or test error
2. It helps the developer understand exactly when/how it occurs
3. It establishes reproducibility — whether it happens always, sometimes, or rarely

In my project's bug report format, I included a "Reproducibility" field with values like "Always," "Intermittent," or "Once" to categorize this.

---

## Q9: What is regression testing?

**Answer:** Regression testing verifies that previously working features still work correctly after a code change, bug fix, or new feature addition. The goal is to catch unintended side effects.

In my project, I created a regression suite of 12 critical test cases covering the highest-risk user flows: login, product browsing, product details, add to cart, cart management (quantity, removal, totals), checkout, navigation, and app relaunch. This suite would be run before each release to ensure core functionality remains intact.

---

## Q10: What is retesting?

**Answer:** Retesting is re-executing a specific test case that previously failed, after the developer has fixed the reported defect. The purpose is to verify that the fix actually resolves the issue.

**Key difference from regression:**
- **Retesting** = Testing the same defect again to verify the fix
- **Regression** = Testing other areas to ensure the fix didn't break anything else

In a real workflow: I find a bug → report it → developer fixes it → I retest that specific bug → if it passes, I also run the regression suite to check for side effects.

---

## Q11: How did you test Android behavior?

**Answer:** My test cases were designed to cover Android-specific behaviors:
- **Back button navigation:** Testing that the Android back button returns to the expected previous screen
- **App relaunch:** Testing that closing and reopening the app works correctly
- **Screen rotation:** Testing that the UI remains usable after device rotation
- **App state persistence:** Testing whether cart contents persist across app relaunch
- **Hamburger menu navigation:** Testing Android-style drawer/menu navigation

However, I need to be transparent that I was unable to execute these tests because no Android emulator or device was available in my testing environment. The test cases are designed and ready for execution.

---

## Q12: What negative testing did you perform?

**Answer:** I designed several negative test cases:
- **Invalid login:** Attempting login with wrong credentials (invalid@test.com / wrongpassword)
- **Empty login:** Submitting the login form with blank username and password
- **Empty checkout fields:** Submitting checkout with required fields left empty
- **Invalid checkout data:** Entering invalid data in checkout forms
- **Repeated actions:** Rapidly tapping the add-to-cart button multiple times
- **Cart boundary:** Attempting to decrease quantity below 1 or to 0
- **No-result search:** Searching for a nonexistent product term

These test cases verify that the app handles error conditions gracefully and provides appropriate feedback to the user.

---

## Q13: How did you use Postman / test APIs?

**Answer:** I performed REST API testing against the JSONPlaceholder API (a free, public testing API) to demonstrate API testing skills. I executed 10 test cases covering all major HTTP methods:

- **GET** — Retrieving existing resources (/posts/1, /users, /users/1, /comments)
- **POST** — Creating new resources with valid and invalid payloads
- **PUT** — Updating an entire resource
- **PATCH** — Partially updating a resource
- **DELETE** — Deleting a resource

For each test, I validated:
- HTTP status code (200, 201, 404)
- Response body (correct properties like id, title, body)
- Response time (within acceptable range)

I also created a Postman Collection (v2.1 format) with pm.test() assertions that can be imported and run in Postman. I used curl for actual execution since the Postman GUI was not available.

---

## Q14: What are GET, POST, PUT, PATCH, DELETE?

**Answer:** These are HTTP methods used in REST APIs:

| Method | Purpose | Example |
|--------|---------|---------|
| **GET** | Retrieve data (read-only) | GET /posts/1 — fetch post with ID 1 |
| **POST** | Create a new resource | POST /posts — create a new blog post |
| **PUT** | Update an entire resource (replace) | PUT /posts/1 — replace all fields of post 1 |
| **PATCH** | Partially update a resource | PATCH /posts/1 — update only the title |
| **DELETE** | Remove a resource | DELETE /posts/1 — delete post 1 |

Key difference: PUT replaces the entire resource (all fields), while PATCH updates only specific fields.

---

## Q15: What is HTTP 200? What is HTTP 400?

**Answer:**
- **200 (OK):** The request was successful. The server processed it and returned the requested data. Most GET requests return 200.
- **201 (Created):** A new resource was successfully created. Typically returned after a successful POST request.
- **400 (Bad Request):** The server couldn't process the request because the client sent malformed or invalid data. Example: sending a POST request with missing required fields.
- **404 (Not Found):** The requested resource doesn't exist. Example: GET /posts/99999 when that post doesn't exist.
- **500 (Internal Server Error):** Something went wrong on the server side.

In my API tests, I validated that each endpoint returned the correct status code — 200 for successful GET/PUT/PATCH/DELETE, 201 for successful POST, and 404 for non-existent resources.

---

## Q16: What would you do if a developer says a bug is not reproducible?

**Answer:** I would:
1. **Revisit my steps:** Carefully re-read my documented reproduction steps to ensure they are accurate and complete
2. **Try reproducing again:** Execute the exact steps on my end to verify the bug still occurs
3. **Check the environment:** Confirm that the developer and I are using the same app version, device/emulator, OS version, and test data
4. **Add more detail:** If I can still reproduce it, I would add more detailed steps, screen recordings, or logs
5. **Pair with the developer:** Offer to reproduce it together in a screen-sharing session so we can identify any environmental differences
6. **Document intermittent behavior:** If the bug is intermittent, note how many times I tried and how many times it occurred
7. **Escalate if needed:** If we truly can't align, I would involve the QA lead to help mediate

The key is to approach it collaboratively, not adversarially. The goal is to fix the bug, not prove who is right.

---

## Q17: What is a test case vs a bug report?

**Answer:**
- **Test Case:** A pre-defined set of steps to verify expected behavior BEFORE testing. It describes what to test, how to test it, and what the expected result should be. It's proactive.
- **Bug Report:** A document created AFTER testing when the actual result doesn't match the expected result. It describes what went wrong, how to reproduce it, and its impact. It's reactive.

A test case leads to a bug report — when I execute test case TC-018 (increase cart quantity) and the total doesn't update, I create bug report BUG-001 linked to TC-018.

---

## Q18: What was your biggest challenge?

**Answer:** The biggest challenge was not having an Android execution environment. I couldn't install the app, interact with it, or capture real screenshots. This meant I had to design test cases based on studying the source code, README, and official documentation rather than hands-on exploration.

I overcame this by:
- Thoroughly studying the app's GitHub repository to understand features and UI
- Analyzing the app's source code structure to identify screens and user flows
- Using the documented test credentials and app behavior
- Being completely transparent about the limitation in all project artifacts
- Focusing on what I could do — comprehensive test design, API testing, and documentation

This taught me an important lesson: in a real QA role, ensuring the test environment is ready before sprint testing begins is critical.

---

## Q19: What would you improve with more time?

**Answer:**
1. **Execute all test cases** with a real Android emulator or physical device
2. **Capture real screenshots** of each screen and any bugs found
3. **Expand test cases** to cover QR Code Scanner, Biometric Login, Drawing, and Geo Location features
4. **Add more negative scenarios** — SQL injection strings, XSS inputs, extremely long inputs
5. **Test accessibility** — screen reader compatibility, contrast ratios, touch target sizes
6. **Add exploratory testing** — unscripted exploration to find issues that structured tests miss
7. **Set up a CI pipeline** — run Newman/API tests automatically on each commit
8. **Test on multiple Android versions** — verify compatibility across Android 10, 11, 12, 13, 14

---

## Q20: How does this project relate to Agile?

**Answer:** Although this was a solo portfolio project and not part of a real Agile team, I designed the workflow to map to Agile practices:

- **Sprint Planning** → I reviewed the app features and created the test plan (like reviewing user stories)
- **Test Preparation** → I designed test cases based on requirements (during sprint)
- **Testing Phase** → I executed API tests and would execute mobile tests (during sprint)
- **Daily Status** → Tracking which tests are executed, passed, failed (daily standup input)
- **Bug Reporting** → Creating Jira-style bug reports for developer handoff
- **Retesting** → Re-executing fixed bugs to verify the fix
- **Regression** → Running the smoke suite before the sprint release
- **Sprint Review** → The Final Test Summary serves as the sprint QA summary

In a real Noise QA Intern role, I would participate in daily standups, sprint planning, sprint reviews, and retrospectives, communicating testing progress and defects to the development team.

---

*These answers are based entirely on the actual completed project. No fabricated experiences or results are claimed.*
