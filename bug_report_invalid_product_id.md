# Bug Report: Invalid Product ID Returns Incorrect Status Code

**Bug ID:** BUG-API-001
**Title:** API returns 200 OK instead of 404 Not Found for non-existing product ID
**Reported By:** Anastasia Dragoman
**Date:** March 18, 2026

## Environment
- **API:** DummyJSON
- **Endpoint:** GET /products/{id}
- **Tested URL:** https://dummyjson.com/products/9999
- **Tool:** Postman
- **Method:** GET

## Description
When requesting a product with a non-existing ID, the API returns **200 OK** instead of the expected **404 Not Found**, which is not compliant with REST standards

## Steps to Reproduce
1. Open Postman
2. Send GET request to: https://dummyjson.com/products/9999
3. Observe the response

## Expected Result
- Status code: 404 Not Found
- Response indicates that the product does not exist

## Actual Result
- Status code: 200 OK
- Response contains error message or empty data

## Impact
- Breaks standard REST API behavior
- May mislead clients into thinking the request was successful
- Affects error handling and validation logic

## Severity
 Medium

 ## Status
 Open

📌 Status

Open
