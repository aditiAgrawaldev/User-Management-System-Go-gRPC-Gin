
🚀 User Management System — Go + gRPC + Gin

A simple User Management microservice built in Go, demonstrating how to build a service with:

📦 gRPC API (Protocol Buffers)
🌐 REST API using Gin
🧠 Shared service logic between gRPC and HTTP
🧪 Extendable architecture (ready for DB, Swagger, etc.)

---

## 📂 Project Structure

```
user_management/
├── api/
│   └── proto/              # Protocol buffer definitions
├── cmd/
│   └── server/             # Application entry point (main.go)
├── pkg/
│   ├── handler/            # gRPC and HTTP handlers
│   └── service/            # Business logic (Create, Get, List, Update, Delete)
└── README.md               # Project documentation
```

---

## 🧰 Technologies Used

* [Go](https://golang.org/)
* [gRPC](https://grpc.io/)
* [Protocol Buffers](https://protobuf.dev/)
* [Gin Web Framework](https://github.com/gin-gonic/gin)

---

## 🚀 Features

* 🆕 Create a new user
* 📄 Get user by ID
* 📋 List all users
* ✏️ Update user details
* ❌ Delete user
* ⚡ Supports both gRPC and REST (Gin) APIs
* 🧠 Shared service logic between both APIs
* 🧪 Thread-safe in-memory store using mutex

---

## ⚙️ Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/user-management.git
cd user-management
```

### 2. Generate gRPC code

> Make sure you have `protoc`, `protoc-gen-go`, and `protoc-gen-go-grpc` installed.

```bash
protoc --go_out=. --go-grpc_out=. api/proto/service.proto
```

### 3. Run the servers (HTTP + gRPC)

```bash
go run cmd/server/main.go
```

* gRPC server: `localhost:8080`
* REST server (Gin): `localhost:8000`

---

## 📬 Sample API Usage (HTTP via Curl)

### ➕ Create User

```bash
curl -X POST http://localhost:8000/users \
  -H "Content-Type: application/json" \
  -d '{"name":"John Doe","email":"john@example.com"}'
```

### 🔍 Get User by ID

```bash
curl http://localhost:8000/users/1
```

### 📋 List All Users

```bash
curl http://localhost:8000/users
```

### ✏️ Update User

```bash
curl -X PUT http://localhost:8000/users/1 \
  -H "Content-Type: application/json" \
  -d '{"name":"John Updated","email":"john_updated@example.com"}'
```

### ❌ Delete User

```bash
curl -X DELETE http://localhost:8000/users/1
```

---

## 🧱 gRPC Services (Defined in `.proto`)

```proto
service UserService {
  rpc CreateUser(CreateUserRequest) returns (UserResponse);
  rpc GetUser(GetUserRequest) returns (UserResponse);
  rpc ListUsers(Empty) returns (ListUserResponse);
  rpc UpdateUser(UpdateUserRequest) returns (UserResponse);
  rpc DeleteUser(DeleteUserRequest) returns (Empty);
}
```

---

## 💡 Future Improvements

* 🗄️ Use a real database (PostgreSQL, MongoDB)
* 🧪 Add unit & integration tests
* 📦 Docker support
* 📜 Swagger / gRPC-Gateway for auto-generated REST docs
* 🔐 Add JWT-based authentication
* 📈 Monitoring & health checks

---

## 🙋‍♀️ Author

Made with ❤️ by **Aditi Agrawal**
This project was built for learning purposes — feel free to fork and use it for your own projects!




Let me know if you want this turned into an actual `README.md` file or uploaded to GitHub with proper formatting, badges, or CI setup!
