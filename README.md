
# Restaurant & Dishes API

This is a RESTful API built with **Node.js**, **Express.js**, and **SQLite3**. It provides endpoints to manage and retrieve data about restaurants and their dishes.

## Features

- Get all restaurants or filter by ID, cuisine, rating, veg status, etc.
- Get all dishes or filter by veg/non-veg and sort by price.
- Uses SQLite3 for data storage.
- Supports CORS and JSON body parsing.

## Technologies Used

- Node.js
- Express.js
- SQLite3
- CORS

---

## Getting Started

### Prerequisites

- Node.js
- npm (comes with Node.js)

### Installation

1. Clone the repository or copy the project files.
2. Run:

   npm install

3. Run the server:

   node index.js

The server will start on **port 3000** (or the value of \`PORT\` in the environment).

---

## API Endpoints

### 🏨 Restaurants

| Method | Endpoint                        | Description                                      |
|--------|---------------------------------|--------------------------------------------------|
| GET    | /restaurants                    | Get all restaurants                              |
| GET    | /restaurants/details/:id        | Get restaurant by ID                             |
| GET    | /restaurants/cuisine/:cuisine   | Get restaurants by cuisine                       |
| GET    | /restaurants/filter             | Filter by isVeg, hasOutdoorSeating, isLuxury     |
| GET    | /restaurants/sort-by-rating     | Get restaurants with rating >= 4.0 (sorted DESC) |

Example:
GET /restaurants/filter?isVeg=true&hasOutdoorSeating=true&isLuxury=false

---

### 🍽️ Dishes

| Method | Endpoint                  | Description                          |
|--------|---------------------------|--------------------------------------|
| GET    | /dishes                   | Get all dishes                       |
| GET    | /dishes/details/:id       | Get dish by ID                       |
| GET    | /dishes/filter?isVeg=true | Filter dishes by veg/non-veg         |
| GET    | /dishes/sort-by-price     | Get dishes priced >= 250 sorted ASC  |

---

## Database

The database file is located at:

./BD4.5A/database.sqlite

### Tables

- restaurants
  - id, name, cuisine, isVeg, rating, priceForTwo, location, hasOutdoorSeating, isLuxury

- dishes
  - id, name, isVeg, rating, price

Initial data is automatically inserted when the app is run for the first time.

---

## Notes

- The isVeg, hasOutdoorSeating, and isLuxury fields are stored as strings ("true"/"false"), not booleans.
- Error messages are returned with appropriate HTTP status codes (e.g., 404, 500).

---

## License

This project is open-source and free to use.
