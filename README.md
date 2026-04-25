# User API

A RESTful API for user management built with **Node.js**, **Express**, **Prisma ORM**, and **MongoDB Atlas**.

This project was developed to practice backend development concepts, including database integration, REST API design, HTTP methods, and cloud database management.

---

## 🚀 Tech Stack

- Node.js
- Express
- Prisma ORM
- MongoDB Atlas

---

## 📌 Features

- Create a new user
- List all users
- Filter users by name, email, or age via query parameters
- Update an existing user
- Delete a user
- Full CRUD implementation with HTTP methods (GET, POST, PUT, DELETE)
- MongoDB Atlas cloud database integration

---

## 📂 User Data Structure

```json
{
  "name": "lua",
  "age": "25",
  "email": "example@gmail.com"
}
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone git@github.com:IngridGd/Api.git
cd Api
```

Install dependencies:

```bash
npm install
```

---

## 🔐 Environment Variables

Create a `.env` file in the root directory:

```env
DATABASE_URL="mongodb+srv://<USER>:<PASSWORD>@<CLUSTER>.mongodb.net/<DATABASE>?retryWrites=true&w=majority"
```

> ⚠️ Never commit your `.env` file to GitHub.

---

## 🧠 Prisma Setup

```bash
# Install Prisma CLI
npm install prisma --save-dev

# Initialize Prisma
npx prisma init

# Install Prisma Client
npm install @prisma/client

# Push schema to database
npx prisma db push

# Generate Prisma Client
npx prisma generate
```

---

## 👀 Visualizing the Database

You can use **Prisma Studio** to browse your data:

```bash
npx prisma studio
```

> ⚠️ Prisma Studio may not work correctly with MongoDB Atlas via `mongodb+srv`. As an alternative, use the **MongoDB Atlas Data Explorer** directly in the cloud dashboard.

---

## 🗄️ MongoDB Concepts

This project uses **MongoDB Atlas** (cloud-hosted database).

| MongoDB Term | Equivalent |
|---|---|
| Database | database |
| Collection | similar to a table |
| Document | JSON record |

> The collection is created automatically when you run `npx prisma db push` or when the first document is inserted.

---

## ▶️ Running the Project

```bash
node --watch server.js
```

The API will be available at: `http://localhost:3000`

---

## 📡 API Routes

| Method | Endpoint | Description |
|---|---|---|
| POST | `/usuarios` | Create a new user |
| GET | `/usuarios` | List all users (supports filters) |
| PUT | `/usuarios/:id` | Update a user by ID |
| DELETE | `/usuarios/:id` | Delete a user by ID |

### Filtering users (GET)

You can filter results using query parameters:

```
GET /usuarios?name=lua
GET /usuarios?email=example@gmail.com
GET /usuarios?age=25
```

---

## 🧪 Testing with Postman

**POST** — Create a user

`POST http://localhost:3000/usuarios`

```json
{
  "name": "lua",
  "age": "25",
  "email": "example@gmail.com"
}
```

---

**GET** — List all users

`GET http://localhost:3000/usuarios`

---

**GET** — Filter users

`GET http://localhost:3000/usuarios?name=lua`

---

**PUT** — Update a user

`PUT http://localhost:3000/usuarios/:id`

```json
{
  "name": "lua updated",
  "age": "26",
  "email": "updated@gmail.com"
}
```

---

**DELETE** — Delete a user

`DELETE http://localhost:3000/usuarios/:id`

---

## 📈 Roadmap

- [x] Create user (POST)
- [x] List users (GET)
- [x] Filter users by query params
- [x] Update user (PUT)
- [x] Delete user (DELETE)
- [ ] Add input validation (e.g. with Zod or Joi)
- [ ] Improve project folder structure
- [ ] Add authentication (e.g. JWT)
