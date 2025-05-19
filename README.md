# 🚀 NestJS Microservices Suite

A collection of three scalable microservices built with **NestJS**, supporting user management, real-time communication, and internal socket support. Each service is containerized with Docker and managed through Docker Compose.

---

## 📁 Project Structure
.
├── user-service/               # App 1 - User Management (HTTP + MongoDB)
├── socket-server/             # App 2 - Realtime Socket.IO Server (HA with Redis)
├── socket-support-service/    # App 3 - Internal HTTP Support Service
├── docker-compose.yml         # Multi-service container orchestration
└── README.md

---

## 1️⃣ User Management Service (`user-service`)

RESTful HTTP service for user registration, authentication, and user CRUD operations.

### ✨ Features
- Signup with JWT token generation
- Login & protected routes
- CRUD operations: list, get, update, delete user
- Swagger documentation (`/api`)
- MongoDB with Mongoose
- Unit tests with Jest

### 🔗 Endpoints

| Method | Route             | Description            |
|--------|-------------------|------------------------|
| POST   | `/auth/signup`    | Register new user      |
| POST   | `/auth/login`     | Authenticate user      |
| GET    | `/users`          | List all users         |
| GET    | `/users/:id`      | Get user by ID         |
| PUT    | `/users/:id`      | Update user            |
| DELETE | `/users/:id`      | Delete user            |

---

## 2️⃣ Realtime Socket.IO Server (`socket-server`)

High-availability real-time server using **Socket.IO** and **Redis Adapter**.

### ✨ Features
- JWT authentication on socket connection
- Redis pub/sub for HA
- Track user online/offline presence
- Send/receive friend requests
- Share user status with friends
- Unit tests with Jest

---

## 3️⃣ Private Support HTTP Service (`socket-support-service`)

Internal backend service for updating user status and friend request handling.

### ✨ Features
- POST APIs for updating online/offline status
- Manage friend requests (send/accept)
- Sync Redis and MongoDB
- Return list of online friends
- Unit tests with Jest

### 🔗 Endpoints

| Method | Route                  | Description                      |
|--------|------------------------|----------------------------------|
| POST   | `/status/update`       | Update user status               |
| POST   | `/friend/request`      | Send a friend request            |
| POST   | `/friend/accept`       | Accept a friend request          |

---

## ⚙️ Tech Stack

- [NestJS](https://nestjs.com/)
- MongoDB + Mongoose
- Redis
- Socket.IO with Redis Adapter
- JWT Auth with Passport
- Jest for Unit Testing
- Swagger for API Docs
- Docker + Docker Compose

---

## 🐳 Docker & Docker Compose

### 🛠 Prerequisites
- Docker
- Docker Compose

### ▶️ Start All Services

```bash
docker-compose up --build
