**Performance Testing E-Commerce REST APIs Using Apache JMeter**

 Project Overview

 This project focuses on load testing and validating REST API endpoints of the Platzi Fake Store API, simulating typical user actions such as creating, updating, deleting, and retrieving product details. The goal was to evaluate performance under stress and ensure correct functionality using Apache JMeter.

Tools & Technologies
1. Apache JMeter (v5.6+)
2. JMeter Plugins (Graphs Generator Listener, Assertions, Timers)
3. Postman (for initial testing)
4. JSON REST API
5. GitHub (for source and documentation)

Test Scenarios Implemented

Scenario 1: Create Product (POST /products)
_Purpose: Simulate adding new products to the catalog._

Assertions:
Response Code = 201
Response Data contains expected title, price, description
Duration Assertion < 2000ms

Scenario 2: Update Product (PUT /products/{id})
_Purpose: Test updating an existing product using a dynamic product ID._

Dynamic ID: Captured using JSON Extractor after product creation.

Assertions:
Response Code = 200
Updated values reflected in response

Scenario 3: Delete Product (DELETE /products/{id})
_Purpose: Simulate deletion of a product and confirm status._

Assertions:
Response Code = 200 or 204

Scenario 4: View Product (GET /products or /products/{id})
_Purpose: Simulate users browsing products._

Assertions:
Response Code = 200
Response contains product list or valid details

Scenario 5: Login (POST /auth/login)

Tested for: Valid credentials

Outcome: Identified API issues (401 Unauthorized)

Performance Metrics Captured

Response Time (ms)

Latency

Throughput

Error %

Assertion Pass/Fail Rate

📈 Visual Reports

Summary Report

Graph Results

Duration Assertions

View Results Tree (with sample responses and debug info)

🧩 Debugging & Troubleshooting

401 Unauthorized issue was debugged using Postman.

Dynamic value handling via JSON Extractor

Timeout/Response null handling using Assertions

Parameterization using CSV and Variables planned

🚀 How to Run This Test

Clone the repo

Open product_test_plan.jmx in Apache JMeter

Run using GUI or CLI:

jmeter -n -t product_test_plan.jmx -l result.jtl -e -o ./report

Open ./report/index.html to view HTML report

📝 Future Improvements

CI/CD integration using Jenkins

Integration with Grafana + InfluxDB for real-time monitoring

Use of CSV Data Set Config for user input simulation

Dockerized JMeter execution

🤝 Contributions

Pull requests are welcome! For any major changes, please open an issue first.

📄 License

MIT

🙌 Acknowledgements

Platzi Fake Store API

Apache JMeter

JMeter Plugins

