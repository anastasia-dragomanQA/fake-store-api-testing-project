 ## API Test Execution Report

**Tester:** Anastasia Dragoman  
**Date:** 2026-03-16  
**Environment:** DummyJSON API  

| Test Case ID | Test Case Name | Expected Result | Actual Result | Status |
|--------------|----------------|-----------------|---------------|--------|
| TC-API-001 | Verify user can retrieve all products | Status 200 OK, response contains product list | Status 200 OK, "products" array returned and not empty | PASS |
| TC-API-002 | Verify user can retrieve product by ID | Status 200 OK, valid product details returned | Status 200 OK, correct product details returned | PASS |
| TC-API-003 | Verify response when product ID does not exist | Status 404 Not Found | Status 200 OK, error message returned | FAIL |
| TC-API-004 | Verify product categories can be retrieved | Status 200 OK, categories list returned | Status 200 OK, categories list returned | PASS |
| TC-API-005 | Verify products can be retrieved by category | Status 200 OK, filtered products returned | Status 200 OK, filtered products returned | PASS |
| TC-API-006 | Verify login with valid credentials | Status 200 OK, authentication token returned | Status 200 OK, token returned | PASS |
| TC-API-007 | Verify login fails with invalid credentials | Status 401 Unauthorized | Error response returned, authentication failed | PASS |
| TC-API-008 | Verify login fails when username is missing | Status 400 Bad Request | Validation error returned for missing username | PASS |
| TC-API-009 | Verify login fails when password is missing | Status 400 Bad Request | Validation error returned for missing password | PASS |
| TC-API-010 | Verify API returns status code 200 for successful requests | Status 200 OK | Status 200 OK confirmed | PASS |
