# 🧾 Sales Order & Product Management (SOPM)

A robust Spring Boot backend REST API for end-to-end sales operations management. SOPM handles core business entities including clients, products, salespersons, cities, and geographic data — secured with JWT authentication and structured with clean controller-service-DTO layering.

---

## 🚀 Features

- **Client Management** – Add, update, retrieve single or all clients with validation
- **Product Management** – Full CRUD: create, get, update, deactivate products
- **Salesperson Management** – Manage salesperson profiles and assignments
- **City & Geography** – Add/update cities; manage country-state hierarchies
- **JWT Security** – Token-based auth with per-request token extraction and propagation
- **Request Validation** – Centralized `CustomValidation` layer before service execution
- **Structured Logging** – Before/after execution logs for every endpoint via `LogUtil`
- **Endpoint Discovery** – `/all/unmapped/endpoints` utility to list all registered routes
- **Swagger UI** – API documentation via `@ApiOperation` annotations

---

## 🗂️ Project Structure
```
src/main/java/com/rst/sopm/
├── controller/
│   ├── CityController.java
│   ├── ClientController.java
│   ├── CountryStateController.java
│   ├── EndpointController.java
│   ├── ProductController.java
│   └── SalesPersonController.java
├── service/          # Business logic layer
├── dto/              # Data Transfer Objects
├── jwt/              # JWT token handling & CustomResponse
├── setter/           # Request token extraction utilities
└── util/             # LogUtil, CustomValidation
```

---

## 📡 API Endpoints

### Client
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/add/client` | Add new client |
| POST | `/api/update/client` | Update client |
| POST | `/api/get/all/client` | Get all clients |
| POST | `/api/get/client` | Get single client |

### Product
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/products/create` | Create product |
| POST | `/api/products/get` | Get product by ID |
| POST | `/api/products/get/all` | Get all products |
| POST | `/api/products/update` | Update product |
| POST | `/api/products/deactivate` | Deactivate product |

### Salesperson
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/add/sales/person` | Add salesperson |
| POST | `/api/update/sales/person` | Update salesperson |
| POST | `/api/get/all/sales/person` | Get all salespersons |
| POST | `/api/get/sales/person` | Get single salesperson |

### City
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/add/city` | Add city |
| POST | `/api/update/city` | Update city |
| POST | `/api/get/all/cities` | Get all cities |

### Country & State
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/country-states/create` | Create country/state |
| POST | `/api/country-states/search` | Search country/states |

### Utility
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/all/unmapped/endpoints` | List all registered API routes |

---

## 🛠️ Tech Stack

- **Java 11+**
- **Spring Boot**
- **Spring Security + JWT**
- **Swagger / Springfox**
- **SLF4J / Logback**
- **Maven**

---

## ⚙️ Getting Started
```bash
# Clone the repository
git clone https://github.com/your-username/sopm-backend.git
cd sopm-backend

# Build the project
mvn clean install

# Run the application
mvn spring-boot:run
```

Configure your `application.properties` with your DB credentials and JWT secret before running.

---

## 🔐 Authentication

All endpoints expect a JWT token in the `Authorization` header. The token is extracted and parsed into a `TokenData` object that is propagated through the DTO to the service layer for audit and access control.

---

## 📬 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

---

## 📄 License

[MIT](LICENSE)
