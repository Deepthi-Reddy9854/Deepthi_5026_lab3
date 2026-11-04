# Lab 3 – REST API, Query Parameters, Validation and Debugging

## Project Details

- **Name:** Bolla Deepthi
- **Registration Number:** 252U1R5026
- **Section:** S-10
- **Course:** Backend Development Fundamentals
- **Lab:** Lab 3 – REST API, Query Parameters, Validation and Debugging
- **Institution:** Aurora Deemed to be University
- **Faculty:** Shiva Sai Teja

## Deployment URL

**Render URL:** Add your Lab 3 Render deployment URL here after deployment.

## Project Description

This project implements RESTful API operations using Node.js, Express.js, and SQLite. It provides endpoints to create, retrieve, update, and delete book records.

It also supports searching, sorting, pagination, price filtering, input validation, and proper HTTP status codes.

## Technologies Used

- Node.js
- Express.js
- SQLite
- SQLite3
- JavaScript
- Postman
- Visual Studio Code

## Project Structure

```text
Deepthi_5026_lab3/
│
├── .gitignore
├── README.md
└── lab3/
    ├── app.js
    ├── database.db
    ├── package.json
    ├── package-lock.json
    ├── README.md
    └── screenshot/
        ├── DELETE Request.png
        ├── GET All Books.png
        ├── Multiple Query.png
        ├── Pagination.png
        ├── POST Successful Request.png
        ├── POST Validation Error.png
        ├── Price Filtering.png
        ├── PUT Update Request.png
        ├── Search Books.png
        └── Sorting.png
```

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/Deepthi-Reddy9854/Deepthi_5026_lab3.git
```

### 2. Open the project folder

```bash
cd Deepthi_5026_lab3/lab3
```

### 3. Install dependencies

```bash
npm install
```

### 4. Start the development server

```bash
npm run dev
```

To start the server without the development watcher, use `npm start`.
The server runs at:

```text
http://localhost:3000
```

## API Endpoints

| HTTP Method | Endpoint | Description |
|---|---|---|
| GET | `/books` | Retrieve all books |
| GET | `/books/:bookId` | Retrieve a specific book |
| POST | `/books` | Add a new book |
| PUT | `/books/:bookId` | Update a book |
| DELETE | `/books/:bookId` | Delete a book |

## Query Parameters

### 1. Search Books

```text
GET /books?search_q=clean
```

Searches for books using a partial title. The default search is empty.

### 2. Sorting

```text
GET /books?order_by=price&order=ASC
```

Sorts books by price in ascending order.

The `order_by` value can be `id`, `title`, `author`, `price`, or `pages`.
Use `DESC` for descending order; the default sort is by `id` in ascending order.

### 3. Pagination

```text
GET /books?limit=5&offset=0
```

Returns five records starting from the first record. The defaults are
`limit=10` and `offset=0`.

### 4. Price Filtering

```text
GET /books?min_price=100&max_price=500
```

Retrieves books within the specified price range.

### 5. Combined Query

```text
GET /books?search_q=clean&order_by=price&order=DESC&limit=5&offset=0&min_price=100&max_price=1000
```

Combines searching, sorting, pagination, and price filtering.

## Request Body for POST and PUT

Select **Body → raw → JSON** in Postman.

```json
{
  "title": "Python Programming",
  "author": "John Smith",
  "price": 450,
  "pages": 320
}
```

## HTTP Status Codes

| Status Code | Description |
|---|---|
| 200 | Request successful |
| 201 | Book created successfully |
| 400 | Invalid input or query parameters |
| 404 | Book or route not found |
| 500 | Internal server error |

## Input Validation

The application validates:

- Book title must not be empty.
- Author name must not be empty.
- Price must be a valid non-negative integer.
- Pages must be a positive integer.
- Book ID must be a valid positive integer.
- Sorting order must be ASC or DESC.
- Pagination values must be valid.

## Postman Testing

All API endpoints are tested using Postman.

The tests include:

1. Retrieve all books.
2. Search books by title.
3. Sort books by price.
4. Test pagination.
5. Filter books by price.
6. Add a book using POST.
7. Test invalid input validation.
8. Update a book using PUT.
9. Delete a book using DELETE.
10. Test invalid IDs and missing records.

## Screenshots

### 1. GET All Books

![GET All Books](lab3/screenshot/GET%20All%20Books.png)

### 2. Search Books

![Search Books](lab3/screenshot/Search%20Books.png)

### 3. Sorting

![Sorting](lab3/screenshot/Sorting.png)

### 4. Pagination

![Pagination](lab3/screenshot/Pagination.png)

### 5. Price Filtering

![Price Filtering](lab3/screenshot/Price%20Filtering.png)

### 6. Multiple Query Parameters

![Multiple Query Parameters](lab3/screenshot/Multiple%20Query.png)

### 7. POST Successful Request

![POST Success](lab3/screenshot/POST%20Successful%20Request.png)

### 8. POST Validation Error

![POST Validation](lab3/screenshot/POST%20Validation%20Error.png)

### 9. PUT Update Request

![PUT Update](lab3/screenshot/PUT%20Update%20Request.png)

### 10. DELETE Request

![DELETE Book](lab3/screenshot/DELETE%20Request.png)

## Conclusion

This lab helped me understand REST API development using Node.js, Express.js, and SQLite. I implemented CRUD operations and learned how to use query parameters for searching, sorting, pagination, and price filtering. I also understood input validation, HTTP status codes, database integration, and debugging techniques. Postman helped me test the API endpoints and verify their responses.

---

**End of Lab 3**