# 🏨 Restful Booker API Testing

## 🔎 Overview

This repository contains a **Postman collection** and **environment** for testing the Restful Booker API, a public sample RESTful API for managing hotel bookings.

🌍 API Base URL: `https://restful-booker.herokuapp.com`

The collection includes both **positive** and **negative** test cases to validate API functionality, authentication, and error handling.

---

## ✨ Features

 **Authentication**: Login to generate an auth token.
 * **Booking Management**:

    *  Retrieve all booking IDs.
    *  Create a new booking.
    *  Retrieve a booking by ID.
    *  Update a booking (full and partial updates).
    *  Delete a booking.
*  **Positive Tests**: Validate successful operations (status codes, response time, content type, response data).
*  **Negative Tests**: Invalid credentials, unauthorized access, missing fields, invalid/long values.
*  **Automated Assertions**: Check status codes, response times, headers, and body content.

---

## 🛠️ Prerequisites

* 📮 **Postman**: Version 10.x or higher.

---

## 🚀 Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/restful-booker-api-testing.git
   cd restful-booker-api-testing
   ```
2. Import:

   * `Booker-collection.json` 
   * `Booker-environment.json` 

---

## ⚙️ Setup

In the Postman environment:

* Set the `url` variable to:
  👉 `https://restful-booker.herokuapp.com`
* `TokenBooker` and `BookingId` variables are auto-set during runs (via login and booking creation).

---

## 📡 API Endpoints Tested

* **POST /auth** 🔑 → Get token.

  ```json
  { "username": "admin", "password": "password123" }
  ```
* **GET /booking** → All booking IDs.
* **POST /booking**  → Create booking.

  ```json
  {
    "firstname": "John",
    "lastname": "Smith",
    "totalprice": 111,
    "depositpaid": true,
    "bookingdates": {
      "checkin": "2018-01-01",
      "checkout": "2019-01-01"
    },
    "additionalneeds": "Breakfast"
  }
  ```
* **GET /booking/:id**  → Get booking by ID.
* **PUT /booking/:id**  → Full update.
* **PATCH /booking/:id**  → Partial update.
* **DELETE /booking/:id**  → Delete booking.

---

## 🧪 Running Tests

1. Open the collection in Postman.
2. Select the **Booker environment**.
3. Run:

   *  **Positive Tests** → login → create → retrieve/update/delete booking.
   *  **Negative Tests** → invalid login, unauthorized GET, missing fields, long values.
4. Use **Collection Runner** for automation and results.

---

## 📂 Project Structure

*  `Booker-collection.json` – all requests & tests.
*  `Booker-environment.json` – environment variables.
