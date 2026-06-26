# CompraYa — Backend

**REST API for the CompraYa e-commerce platform**

> Handles authentication, user management, product catalog, and category organization for the CompraYa online store.

---

## Related Repository

**Frontend:** [CompraYa Frontend](https://github.com/arteagagarcia7) — React + Bootstrap

---

## Tech Stack

JavaScript · Node.js · Express.js · MongoDB · Mongoose · JWT · CORS

---

## API Endpoints

| Module | Base Route | Description |
|--------|-----------|-------------|
| Auth | `/api/auth` | Login and session management |
| Users | `/api/usuarios` | User registration and management |
| Categories | `/api/categoria` | Product category CRUD |
| Products | `/api/producto` | Product catalog CRUD |

---

## How to Run

Prerequisites: Node.js 18+, MongoDB

**1. Clone and install dependencies**
```bash
git clone https://github.com/arteagagarcia7/<repo-name>.git
cd <repo-name>
npm install
```

**2. Configure environment variables**

Create a `.env` file in the root directory:
```env
MONGO_URI=mongodb://localhost:27017/compraya
JWT_SECRET=your-secret-key
PORT=4000
```

**3. Start the server**
```bash
node index.js
```

API available at `http://localhost:4000/api/`

---

## Data Model

**Users** — Registration, login and role management (admin / customer)

**Auth** — JWT-based authentication. Admins access inventory management; customers access the store and cart.

**Categories** — Product classification to organize the store catalog.

**Products** — Full product catalog with stock management, available to admins for CRUD operations and to customers for browsing and adding to cart.

---

## Architecture Decisions

**Express.js with modular routing**
Each resource (users, auth, categories, products) has its own router file, keeping the codebase organized and each module independently maintainable. The main `index.js` only handles server configuration and route registration.

**MongoDB with Mongoose**
MongoDB was chosen for its flexible document schema, which fits the variable nature of product data (different attributes per category). Mongoose adds schema validation and relationship management on top of the native driver.

**JWT Authentication**
JSON Web Tokens handle session management without server-side state. Admin and customer roles are encoded in the token payload, controlling access to protected routes like inventory management.

**CORS enabled**
Configured to allow cross-origin requests from the React frontend running on a different port during development.

---

## Author

**Carlos Andrés Arteaga**
[LinkedIn](https://www.linkedin.com/in/carlos-andres-arteaga) · [GitHub](https://github.com/arteagagarcia7)
