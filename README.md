**Go-A-Simple-API - A Clean Architecture REST API in Go**

📋 Overvie

A simple, well-structured REST API built with Go (Golang) that follows clean architecture principles. This project demonstrates a product management API with a clear separation of concerns, making it an excellent learning resource and foundation for building scalable Go applications.

✨ Features
Clean Architecture: Clear separation into layers (Controller, Use Case, Repository, Domain)

RESTful Design: Standard HTTP methods and response formats

PostgreSQL Integration: Persistent data storage with relational database

Docker Support: Easy containerization and deployment

Structured Logging: Organized logging for debugging and monitoring

Error Handling: Consistent error responses and status codes

🏗️ Architecture
This project follows a layered architecture pattern:

📦 go-a-simple-api
├── 📄 main.go                 # Application entry point
├── 📄 conn.go                 # Database connection setup
├── 📄 response.go             # Standardized HTTP responses
├── 📄 product.go              # Domain model/entity
├── 📄 product_controller.go   # HTTP handlers
├── 📄 product_usecase.go      # Business logic
└── 📄 product_repository.go   # Data access layer

🚀 Getting Started
Prerequisites
Go 1.19+ (or version specified in go.mod)

Docker and Docker Compose (for containerized setup)

PostgreSQL (if running locally without Docker)

Installation
Option 1: Using Docker (Recommended)
bash
# Clone the repository
git clone https://github.com/Fernvndez/go-a-simple-api.git
cd go-a-simple-api

# Start the application with Docker Compose
docker-compose up
Option 2: Local Development
bash
# Clone the repository
git clone https://github.com/Fernvndez/go-a-simple-api.git
cd go-a-simple-api

# Install dependencies
go mod download

# Set up environment variables
export DB_HOST=localhost
export DB_PORT=5432
export DB_USER=your_username
export DB_PASSWORD=your_password
export DB_NAME=your_database

# Run the application
go run main.go
📖 API Endpoints
Product Management
Method	Endpoint	Description
GET	/products	Retrieve all products
GET	/products/{id}	Retrieve a specific product
POST	/products	Create a new product
PUT	/products/{id}	Update an existing product
DELETE	/products/{id}	Delete a product
Example Requests
Create a Product:

curl -X POST http://localhost:8080/products \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Sample Product",
    "price": 29.99,
    "description": "A sample product description"
  }'
Get All Products:

curl http://localhost:8080/products
🐳 Docker Deployment
The project includes Docker configuration for easy deployment:

Dockerfile.txt: Container build instructions

docker-compose.yml: Multi-container orchestration (API + PostgreSQL)

To build and run with Docker Compose:

docker-compose up --build
The API will be available at http://localhost:8080

🧪 Development
Project Structure
Domain Layer (product.go): Business entities and interfaces

Repository Layer (product_repository.go): Data access and persistence

Use Case Layer (product_usecase.go): Business logic and rules

Controller Layer (product_controller.go): HTTP handlers and request/response management

Infrastructure Layer (conn.go, main.go): External concerns like DB connections and server setup

Running Tests
(Note: Test files would typically be added with _test.go suffix)

Dependencies
Key dependencies are managed in go.mod and go.sum files. The project uses standard Go modules for dependency management.

🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

Fork the repository

Create your feature branch (git checkout -b feature/amazing-feature)

Commit your changes (git commit -m 'Add some amazing feature')

Push to the branch (git push origin feature/amazing-feature)

Open a Pull Request

📄 License
This project is open source and available for use and modification.
