# API Test Cases – Fake Store API

## TC-API-001 Verify user can retrieve all products

**Endpoint:**  
GET https://fakestoreapi.com/products

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
GET https://fakestoreapi.com/products/1

**Description:**  
Verify API returns product details for a valid ID.

**Steps:**
1. Send GET request to /products/1

**Expected Result:**
- Status code is 200 OK
- Response contains product details

## TC-API-003 Verify response when product ID does not exist

**Endpoint:**
GET https://fakestoreapi.com/products/9999

**Description:**
Verify API response for non-existing product ID.

**Precondition:**
API is available

**Steps:**
1. Send GET request to /products/9999

**Expected Result:**
- Status code is 404 OR empty response
- No product data is returned

## TC-API-004 Verify product categories can be retrieved

**Endpoint:**
GET https://fakestoreapi.com/products/categories

**Description:**
Verify API returns product categories.

**Precondition:**
API is available

**Steps:**
1. Send GET request to /products/categories

**Expected Result:**
- Status code is 200 OK
- Response contains category list

## TC-API-005 Verify products can be retrieved by category

**Endpoint:**
GET https://fakestoreapi.com/products/category/electronics

**Description:**
Verify API returns products filtered by category.

**Precondition:**
API is available

**Steps:**
1. Send GET request to /products/category/electronics

**Expected Result:**
- Status code is 200 OK
- Response contains products for selected category

## TC-API-006 Verify login with valid credentials

**Endpoint:**  
POST https://fakestoreapi.com/auth/login

**Description:**  
Verify login succeeds with valid credentials.

**Request Body:**
'''json
{
  "username": "mor_2314",
  "password": "83r5^_"
}
'''

**Steps:**
1. Send POST request with valid credentials

**Expected Result:**
- Status code is 200 OK
- Response contains token

## TC-API-007 Verify login fails with invalid credentials

**Endpoint:**
POST https://fakestoreapi.com/auth/login

**Description:**
Verify login fails with invalid credentials.

**Precondition:**
API is available

**Request Body:**
{
  "username": "wrong_user",
  "password": "wrong_pass"
}

**Steps:**
1. Send POST request with invalid credentials

**Expected Result:**
- Error response is returned
- Authentication fails

## TC-API-008 Verify login fails when username is missing

**Endpoint:**
POST https://fakestoreapi.com/auth/login

**Description:**
Verify login fails when username is missing.

**Precondition:**
API is available

**Request Body:**

{
  "password": "83r5^_"
}

**Steps:**
1. Send POST request without username

**Expected Result:**
- Error response is returned
- Validation message is displayed

## TC-API-009 Verify login fails when password is missing

**Endpoint:**
POST https://fakestoreapi.com/auth/login

**Description:**
Verify login fails when password is missing.

**Precondition:**
API is available

**Request Body:**

{
  "username": "mor_2314"
}

**Steps:**
1. Send POST request without password

**Expected Result:**
- Error response is returned
- Validation message is displayed

## TC-API-010 Verify API returns status code 200 for successful requests

**Endpoint:**
GET https://fakestoreapi.com/products

**Description:**
Verify API returns status code 200 for successful requests.

**Precondition:**
API is available

**Steps:**
1. Send GET request to /products

**Expected Result:**
- Status code is 200 OK


