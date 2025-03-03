# 🚀 AutomationExercise API Testing
[![Postman](https://img.shields.io/badge/tested%20with-Postman-orange.svg)](https://www.postman.com/)  

## 👓 Overview

This project contains a Postman collection for testing the API endpoints provided by [Automation Exercise](https://automationexercise.com/) using Postman and Newman. The tests cover various functionalities such as retrieving product lists, searching for products, handling user authentication, and managing user accounts.

### 🏁 Getting Started

#### 🔤 Prerequisites

* Install Postman

 * Install Newman for CLI testing

* Ensure API base URL is set correctly in Postman environment variables

### 🪛 Installation

* Clone this repository:

``git clone https://github.com/anikush-yes/AutomationExercise_API_Testing.git``

* Navigate to the project folder:

``cd AutomationExercise_API_Testing``

* Install dependencies (if required for Newman execution):

``npm install -g newman``

### 📂 Folder Structure

- **AutomationExercise_API_Testing/**
  - 📂 **collections/**
    - 📄 `AutomationExercise_API_Testing.postman_collection.json` *(Postman collection file)*
  - 📂 **tests/**
    - 📂 **test_results/** *(Folder to store test execution reports)*
  - 📄 `README.md` *(Project documentation)*
  - 📄 `package.json` *(Newman dependencies, if applicable)*

# 📥📤 API Endpoints Tested

### 1. Products

``GET /productsList`` - Retrieve all products

``POST /productsList`` - Verify invalid request handling

### 2. Brands

``GET /brandsList`` - Retrieve all brands

``PUT /brandsList`` - Verify method not supported

### 3. Search

``POST /searchProduct`` - Search for products

``POST /searchProduct`` (without parameter) - Verify bad request handling

### 4. User Authentication

``POST /verifyLogin`` - Verify login with valid credentials

``POST /verifyLogin`` (without email) - Verify error handling

``POST /verifyLogin`` (invalid details) - Check invalid login attempt

``DELETE /verifyLogin`` - Verify unsupported method handling

### 5. User Account Management

``POST /createAccount`` - Create a new user

``PUT /updateAccount`` - Update user details

``GET /getUserDetailByEmail`` - Retrieve user details

``DELETE /deleteAccount`` - Delete user account

### 6. Negative Path Testing

1. Invalid product search

2. Account creation without required fields

3. Retrieving non-existent user account

# 🧪 Tests Included

* Status Code Validation: Ensures correct HTTP response codes are returned.

* Response Time Check: Confirms API responses are within acceptable time limits.

* JSON Schema Validation: Verifies API responses match expected structures.

* Functional Testing: Ensures API operations work as expected.

* Error Handling Tests: Tests invalid requests and verifies proper error messages.

# 📥📤 Example Request & Response

## GET /productsList

### 📥Request:

``GET /productsList HTTP/1.1
Host: {{base_url}}``

### 📤Response:

``{
  "responseCode": 200,
  "products": [
    {
      "id": 1,
      "name": "T-shirt",
      "price": "15.99",
      "brand": "Nike",
      "category": {
        "usertype": {
          "usertype": "Men"
        },
        "category": "Clothing"
      }
    }
  ]
}``

## POST /searchProduct

### 📥 Request:

``POST /searchProduct HTTP/1.1
Host: {{base_url}}
Content-Type: application/x-www-form-urlencoded
search_product=jeans``

### 📤 Response:

``{
  "responseCode": 200,
  "products": [
    {
      "id": 5,
      "name": "Blue Jeans",
      "price": "49.99",
      "brand": "Levi's",
      "category": {
        "usertype": {
          "usertype": "Men"
        },
        "category": "Clothing"
      }
    }
  ]
}``

# 🏃‍♀️‍➡️ Running the Tests

* Using Postman

* Import the AutomationExercise_API_Testing.postman_collection.json into Postman.

* Set the base_url environment variable.

* Run the collection manually.

* Using Newman (CLI)

* To run the tests from the command line:

newman run AutomationExercise_API_Testing.postman_collection.json --reporters cli

#  💞 Expected Results

* All valid requests should return 200 OK.

* Invalid requests should return proper error messages (400/404/405).

* API response times should be under 1000ms.

# 📝 Notes

* Ensure the API base URL is correctly set before running the tests.

* Some tests rely on valid user credentials, update them as needed.

# 🪪 License

This project is licensed under the MIT License.

⭐ If you like this project, don't forget to give it a star! ⭐

