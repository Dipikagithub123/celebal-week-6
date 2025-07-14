# RESTful API Demo

This is a simple RESTful API built with Node.js and Express that supports basic CRUD operations on a `users` resource.

## Features
- Create, Read, Update, and Delete users
- In-memory data storage (no database required)
- All code in a single folder for simplicity

## Setup
1. Install dependencies:
   ```bash
   npm install
   ```
2. Start the server:
   ```bash
   npm start
   ```
   Or, for auto-reload on changes (if you have nodemon):
   ```bash
   npx nodemon index.js
   ```

The server will run at [http://localhost:3000](http://localhost:3000)

## API Endpoints

### Create a User
- **POST** `/users`
- **Body:** `{ "name": "John Doe", "email": "john@example.com" }`
- **Response:** `201 Created` with the created user object

### Get All Users
- **GET** `/users`
- **Response:** `200 OK` with an array of users

### Get a User by ID
- **GET** `/users/:id`
- **Response:** `200 OK` with the user object, or `404 Not Found`

### Update a User
- **PUT** `/users/:id`
- **Body:** `{ "name": "New Name", "email": "new@example.com" }` (either or both fields)
- **Response:** `200 OK` with the updated user, or `404 Not Found`

### Delete a User
- **DELETE** `/users/:id`
- **Response:** `204 No Content` on success, or `404 Not Found`

## Example Usage (with curl)

Create a user:
```bash
curl -X POST http://localhost:3000/users -H "Content-Type: application/json" -d '{"name":"Alice","email":"alice@example.com"}'
```

Get all users:
```bash
curl http://localhost:3000/users
```

Get a user by ID:
```bash
curl http://localhost:3000/users/1
```

Update a user:
```bash
curl -X PUT http://localhost:3000/users/1 -H "Content-Type: application/json" -d '{"name":"Alice Smith"}'
```

Delete a user:
```bash
curl -X DELETE http://localhost:3000/users/1
```

---
