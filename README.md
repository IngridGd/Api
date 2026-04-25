# User API

A RESTful API for user management built with **Node.js**, **Express**, **Prisma ORM**, and **MongoDB Atlas**.

This project was developed to practice backend development concepts, including database integration, REST API design, and cloud database management.

---

## 🚀 Tech Stack

- Node.js
- Express
- Prisma ORM
- MongoDB Atlas

---

## 📌 Features

- Create users
- List all users
- MongoDB Atlas cloud database integration
- API testing with Postman

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
| GET | `/usuarios` | List all users |

---

## 🧪 Testing with Postman

**POST** `http://localhost:3000/usuarios`

Body (JSON):

```json
{
  "name": "lua",
  "age": "25",
  "email": "example@gmail.com"
}
```

**GET** `http://localhost:3000/usuarios`

---

## 📈 Roadmap

- [ ] Add `PUT /usuarios/:id` — Update user
- [ ] Add `DELETE /usuarios/:id` — Delete user
- [ ] Add input validation (e.g. with Zod or Joi)
- [ ] Improve project folder structure
