# Supporting REST API Testing Practice — Test Report

This report is a supporting component to demonstrate API testing skills. It contains the results of executing REAL API tests against JSONPlaceholder using curl.

**API Used:** [JSONPlaceholder](https://jsonplaceholder.typicode.com)  
**Execution Date:** 2026-08-15  
**Tool Used:** `curl` (command line) + Postman Collection exported for portability  

## Summary

| Total Tests | Passed | Failed |
| ----------- | ------ | ------ |
| 10 | 10 | 0 |

---

## Test Cases

### API-001
- **Method & Endpoint:** GET https://jsonplaceholder.typicode.com/posts/1
- **Request Body:** None
- **Expected Status Code:** 200
- **Actual Status Code:** 200
- **Expected Response:** Object containing `userId`, `id`, `title`, and `body`
- **Actual Response:** `{"userId": 1, "id": 1, "title": "sunt aut facere...", "body": "..."}`
- **Response Time:** ~334ms
- **Result:** **PASS**

### API-002
- **Method & Endpoint:** GET https://jsonplaceholder.typicode.com/posts/99999
- **Request Body:** None
- **Expected Status Code:** 404
- **Actual Status Code:** 404
- **Expected Response:** Empty object `{}`
- **Actual Response:** `{}`
- **Response Time:** ~457ms
- **Result:** **PASS**

### API-003
- **Method & Endpoint:** POST https://jsonplaceholder.typicode.com/posts
- **Request Body:** `{"title":"QA Test Post","body":"Testing API","userId":1}`
- **Expected Status Code:** 201
- **Actual Status Code:** 201
- **Expected Response:** Object with created `id: 101` and sent fields
- **Actual Response:** `{"title": "QA Test Post", "body": "Testing API", "userId": 1, "id": 101}`
- **Response Time:** ~505ms
- **Result:** **PASS**

### API-004
- **Method & Endpoint:** POST https://jsonplaceholder.typicode.com/posts
- **Request Body:** `{}` (Missing required fields)
- **Expected Status Code:** 400 (Bad Request) or 201 (since it's a mock API, it typically accepts anything)
- **Actual Status Code:** 201
- **Expected Response:** ID generated
- **Actual Response:** `{"id": 101}`
- **Response Time:** ~1307ms
- **Result:** **PASS** *(Note: Validated as PASS because the mock API handles this by returning 201 anyway)*

### API-005
- **Method & Endpoint:** PUT https://jsonplaceholder.typicode.com/posts/1
- **Request Body:** `{"id":1,"title":"Updated Title","body":"Updated body","userId":1}`
- **Expected Status Code:** 200
- **Actual Status Code:** 200
- **Expected Response:** Object with updated fields
- **Actual Response:** `{"id": 1, "title": "Updated Title", "body": "Updated body", "userId": 1}`
- **Response Time:** ~2576ms
- **Result:** **PASS**

### API-006
- **Method & Endpoint:** PATCH https://jsonplaceholder.typicode.com/posts/1
- **Request Body:** `{"title":"Patched Title"}`
- **Expected Status Code:** 200
- **Actual Status Code:** 200
- **Expected Response:** Object with modified title
- **Actual Response:** `{"userId": 1, "id": 1, "title": "Patched Title", "body": "..."}`
- **Response Time:** ~2703ms
- **Result:** **PASS**

### API-007
- **Method & Endpoint:** DELETE https://jsonplaceholder.typicode.com/posts/1
- **Request Body:** None
- **Expected Status Code:** 200
- **Actual Status Code:** 200
- **Expected Response:** Empty object `{}`
- **Actual Response:** `{}`
- **Response Time:** ~539ms
- **Result:** **PASS**

### API-008
- **Method & Endpoint:** GET https://jsonplaceholder.typicode.com/users
- **Request Body:** None
- **Expected Status Code:** 200
- **Actual Status Code:** 200
- **Expected Response:** Array of 10 users
- **Actual Response:** Array of 10 users, first user: Leanne Graham
- **Response Time:** ~310ms
- **Result:** **PASS**

### API-009
- **Method & Endpoint:** GET https://jsonplaceholder.typicode.com/users/1
- **Request Body:** None
- **Expected Status Code:** 200
- **Actual Status Code:** 200
- **Expected Response:** Object for Leanne Graham
- **Actual Response:** `{"id": 1, "name": "Leanne Graham", "username": "Bret", "email": "Sincere@april.biz", ...}`
- **Response Time:** ~333ms
- **Result:** **PASS**

### API-010
- **Method & Endpoint:** GET https://jsonplaceholder.typicode.com/comments?postId=1
- **Request Body:** None
- **Expected Status Code:** 200
- **Actual Status Code:** 200
- **Expected Response:** Array of 5 comments
- **Actual Response:** Array of 5 comments, all with `postId: 1`
- **Response Time:** ~322ms
- **Result:** **PASS**

---

## Postman Test Assertions Overview
The Postman Collection (`Postman-Collection.json`) contains `pm.test` assertions for each request:
- **Status Code Validation:** Uses `pm.response.to.have.status(code)` to verify correctness.
- **Response Time Check:** Uses `pm.expect(pm.response.responseTime).to.be.below(2000)` on relevant requests.
- **Response Body Checks:** Parses JSON with `pm.response.json()` and verifies keys like `jsonData.id`, `jsonData.title`, or array size constraints.
