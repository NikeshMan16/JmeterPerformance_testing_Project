# 🧪 Performance Testing E-Commerce REST APIs Using Apache JMeter

## 📌 Project Overview

This project focuses on **load testing, validating REST API endpoints and endurance testing** of the [Platzi Fake Store API](https://fakeapi.platzi.com/), simulating typical user actions such as creating, updating, deleting, and retrieving product details . The goal was to evaluate performance under stress and ensure correct functionality using **Apache JMeter**. Currently planning to write a blog about what I learned and how to do it.

---

## 🛠️ Tools & Technologies

* **Apache JMeter** (v5.6+)
* **JMeter Plugins** (Graphs Generator Listener, Assertions, Timers)
* **Postman** (for initial testing)
* **JSON REST API**
* **GitHub** (for source and documentation)

---

## 🎯 Test Scenarios Implemented

### ✅ Scenario 1: Create Product (POST `/products`)

* **Purpose:** Simulate adding new products to the catalog.
* **Assertions:**

  * Response Code = 201
  * Response Data contains expected `title`, `price`, `description`
  * Duration Assertion < 2000ms

### ✅ Scenario 2: Update Product (PUT `/products/{id}`)

* **Purpose:** Test updating an existing product using a dynamic product ID.
* **Dynamic ID:** Captured using `JSON Extractor` after product creation.
* **Assertions:**

  * Response Code = 200
  * Updated values reflected in response

### ✅ Scenario 3: Delete Product (DELETE `/products/{id}`)

* **Purpose:** Simulate deletion of a product and confirm status.
* **Assertions:**

  * Response Code = 200 or 204

### ✅ Scenario 4: View Product (GET `/products` or `/products/{id}`)

* **Purpose:** Simulate users browsing products.
* **Assertions:**

  * Response Code = 200
  * Response contains product list or valid details


### ✅ Scenario 5: View Product by ID through Parametrized CSV(GET `/products` or `/products/{id}`) 

* **Purpose:** Simulating multiple get request for product using parametrized id through csv file.
* **Dynamic ID:** Captured from csv file `products_id.csv`. 
* **Assertions:**

  * Response Code = 200
  * Response contains product list or valid details
* * **Outcome:** Status code 400 for id of products not in the API. 



### ✅ Scenario 6: Login (POST `/auth/login`)

* **Tested for:** Valid credentials
* **Outcome:** Identified API issues (401 Unauthorized) 

### ✅ Scenario 7: Endurance Testing under load for 5 minutes(GET `/products` and `/categories)
* **Purpose:** Simulate multiple users viewing products and categories under load.
* **Assertions:**

  * Response Code = 200
  * Response contains product list or valid details


---

## 📊 Performance Metrics Captured

* **Response Time (ms)**
* **Latency**
* **Throughput**
* **Error %**
* **Assertion Pass/Fail Rate**

---

## 📈 Visual Reports and Documentations

* Explanation document added in the project folder itself(**Process_explanation.docx**)
* Summary Report
* Graph Results
* Duration Assertions
* View Results Tree (with sample responses and debug info)


---

## 🧩 Debugging & Troubleshooting

* **401 Unauthorized** issue was debugged using Postman.
* Dynamic value handling via **JSON Extractor**
* Timeout/Response null handling using **Assertions**
* Parameterization using CSV and Variables planned

---

## 🚀 How to Run This Test

1. Clone the repo
2. Open `FakeStoreLoadTest.jmx` in Apache JMeter
3. Run using GUI or CLI:

   ```bash
   jmeter -n -t FakeStoreLoadTest.jmx -l result.jtl -e -o ./report
   ```
4. Open `./report/index.html` to view HTML report

---

## 📝 Future Improvements

* CI/CD integration using **Jenkins**
* Integration with **Grafana + InfluxDB** for real-time monitoring
* Dockerized JMeter execution

---


## 📄 License

[MIT](LICENSE)

---

## 🙌 Acknowledgements

* [Platzi Fake Store API](https://fakeapi.platzi.com/)
* [Apache JMeter](https://jmeter.apache.org/)
* [JMeter Plugins](https://jmeter-plugins.org/)
* [ChatGPT](https://chatgpt.com/)
