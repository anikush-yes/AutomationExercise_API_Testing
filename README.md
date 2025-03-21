# 🚀 API Testing using Postman and Newman
[![Postman](https://img.shields.io/badge/Tested%20with-Postman-orange.svg)](https://www.postman.com/)
[![API Tests](https://img.shields.io/badge/API%20Tests-14%20passing-brightgreen.svg)]()
______________________________________________________________________________________________________________________________________________
## 👓 Overview

This project focuses on **testing the API** of https://automationexercise.com/, an online platform for practicing API testing. Created a **Postman test collection**, tested it manually in **Postman**, and integrated **Newman** with **GitHub Actions** to execute the tests in **CI pipeline**, ensuring continuous API quality and reliability.
***

## 🏁 Getting Started

### 🔤 Prerequisites

[![Node.js](https://img.shields.io/badge/Node.js-14.x-green)](https://nodejs.org/en)
[![Postman](https://img.shields.io/badge/Tested%20with-Postman-orange)](https://www.postman.com)
[![Newman](https://img.shields.io/badge/Newman-6.2.1-blue)](https://github.com/postmanlabs/newman)
***

### 🪛 Installation

* Clone this repository:

``git clone https://github.com/anikush-yes/AutomationExercise_API_Testing.git``

* Navigate to the project folder:

``cd AutomationExercise_API_Testing`` (Or the name You gave)

* Install dependencies (if required for Newman execution):

``npm install -g newman``

***

## 🏃‍♀️‍➡️ Running API Tests
  

 ### 1.Using Postman

* **Import** the AutomationExercise_API_Testing.postman_collection.json into Postman

* **Set** API base URL **https://automationexercise.com/api/** in Postman environment variables

* **Run** the collection manually

### 2.Using Newman 

* To run the tests from the command line, use the following command:

``npm test``

### 3.Using GitHub Actions

* Manually trigger workflow "Postman Newman Tests" from the **GitHub Actions** tab via **"Run workflow"**

***
##  💞 Expected Results

* All valid requests should return 200 OK.

* Invalid requests should return proper error messages (400/404/405).

* API response times should be under 1000ms.
 
***
## 📥📤 API Endpoints Tested


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

***
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
***
# 📝 Notes


* Ensure the API base URL is correctly set before running the tests.

* Some tests rely on valid user credentials, update them as needed.
  
***
# 🪪 License

This project is licensed under the MIT License.
***

***⭐ If you like this project, don't forget to give it a star! ⭐***

