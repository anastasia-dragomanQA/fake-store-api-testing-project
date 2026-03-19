# API Test Cases – DummyJSON API

## TC-API-001 Verify user can retrieve all products

**Endpoint:**  
GET https://dummyjson.com/products

**Description:**  
Verify API returns all products.

**Steps:**
1. Send GET request to /products

**Expected Result:**
- Status code is 200 OK
- Response is JSON
- Response contains product list

## TC-API-002 Verify user can retrieve product by ID

**Endpoint:**  
GET  https://dummyjson.com/products/1

**Description:**  
Verify API returns product details for a valid ID.

**Steps:**
1. Send GET request to /products/1

**Expected Result:**
- Status code is 200 OK
- Response contains product details
- Response format is JSON
- Product object contains required fields (id, title, price, category)
- Product ID in responce matches requested ID

## TC-API-003 Verify response when product ID does not exist

**Endpoint:**
GET https://dummyjson.com/products/9999

**Description:**
Verify API response for non-existing product ID.

**Precondition:**
API is available

**Steps:**
1. Send GET request to /products/9999

**Expected Result:**
- Status code is 404 Not Found
- No product data is returned
- Response format is JSON
- No valid product data is returned

## TC-API-004 Verify product categories can be retrieved

**Endpoint:**
GET https://dummyjson.com/products/categories

**Description:**
Verify API returns product categories.

**Precondition:**
API is available

**Steps:**
1. Send GET request to /products/categories

**Expected Result:**
- Status code is 200 OK
- Response contains category list
- Response format is JSON
- Response is a non-empty array
- Each item in the array is a valid category (string)

## TC-API-005 Verify products can be retrieved by category

**Endpoint:**
GET  https://dummyjson.com/products/category/electronics

**Description:**
Verify API returns products filtered by category.

**Precondition:**
API is available

**Steps:**
1. Send GET request to /products/category/electronics

**Expected Result:**
- Status code is 200 OK
- Response body contains products for selected category
- Response format is JSON
- Each product belongs to the selected category
- Each product contain required fields (id, title, price, category)

## TC-API-006 Verify login with valid credentials

**Endpoint:**  
POST  https://dummyjson.com/auth/login

**Description:**  
Verify login succeeds with valid credentials.

**Request Body:**
```json
{
  "username": "mor_2314",
  "password": "83r5^_"
}
```

**Steps:**
1. Send POST request with valid credentials

**Expected Result:**
- Status code is 200 OK
- Response contains authentication token
- Token is not empty
- Token is returned in response body

## TC-API-007 Verify login fails with invalid credentials

**Endpoint:**
POST  https://dummyjson.com/auth/login

**Description:**
Verify login fails with invalid credentials.

**Precondition:**
API is available

**Request Body:**
```json
{
  "username": "wrong_user",
  "password": "wrong_pass"
}
```
**Steps:**
1. Send POST request with invalid credentials

**Expected Result:**
- Status code is 401 Unauthorized
- Error response is returned
- No authentication token is returned

## TC-API-008 Verify login fails when username is missing

**Endpoint:**
POST https://dummyjson.com/auth/login

**Description:**
Verify login fails when username is missing.

**Precondition:**
API is available

**Request Body:**
```json
{
  "password": "83r5^_"
}
```
**Steps:**
1. Send POST request without username

**Expected Result:**
- Status code is 400 Bad Request
- Validation error message is displayed
- Response format in JSON
- No authentication token is returned

## TC-API-009 Verify login fails when password is missing

**Endpoint:**
POST  https://dummyjson.com/auth/login

**Description:**
Verify login fails when password is missing.

**Precondition:**
API is available

**Request Body:**
```json
{
  "username": "mor_2314"
}
```
**Steps:**
1. Send POST request without password

**Expected Result:**
- Status code is 400 Bad Request
- Validation error message is displayed
- Response format in JSON
- No authentication token is returned

## TC-API-010 Verify API returns status code 200 for successful requests

**Endpoint:**
GET  https://dummyjson.com/products

**Description:**
Verify API returns status code 200 for successful requests.

**Precondition:**
API is available

**Steps:**
1. Send GET request to /products

**Expected Result:**
- Status code is 200 OK
- Response body contains a list of products
- Response format is JSON
- Each product contains valid fields (id, title, price, category)

## Author
Anastasia Dragoman - QA Engineer
