# User Account Service - Spring Boot

A robust and scalable User Account Management Service built with Spring Boot, providing RESTful APIs for user registration, authentication, and account management.

## 📋 Overview

This microservice handles all user account-related operations including user registration, authentication, profile management, and authorization. It's designed to be easily integrated into larger Spring Boot applications or used as a standalone service.

## ✨ Features

- **User Registration**: Create new user accounts with validation
- **User Authentication**: Secure login and session management
- **Profile Management**: Update and retrieve user profile information
- **Password Management**: Secure password reset and update functionality
- **Account Verification**: Email/SMS verification support
- **Role-Based Access Control**: Manage user roles and permissions
- **RESTful APIs**: Well-documented REST endpoints
- **Security**: Implements Spring Security best practices
- **Database Integration**: JPA/Hibernate for data persistence

## 🛠️ Technology Stack

- **Java**: 11 or higher
- **Spring Boot**: 2.x/3.x
- **Spring Security**: For authentication and authorization
- **Spring Data JPA**: For database operations
- **MySQL/PostgreSQL**: Relational database (configurable)
- **Maven**: Dependency management and build tool
- **JWT**: JSON Web Tokens for stateless authentication
- **Lombok**: Reduce boilerplate code
- **Swagger/OpenAPI**: API documentation

## 📦 Prerequisites

Before running this application, ensure you have:

- Java Development Kit (JDK) 11 or higher
- Maven 3.6 or higher
- MySQL or PostgreSQL database
- Git (for cloning the repository)

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/YatharthKumarSaxena/User-Account-Service-SpringBoot.git
cd User-Account-Service-SpringBoot
```

### 2. Configure Database

Create a database and update the `application.properties` or `application.yml` file:

```properties
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/user_account_db
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

### 3. Build the Project

```bash
mvn clean install
```

### 4. Run the Application

```bash
mvn spring-boot:run
```

Or run the JAR file:

```bash
java -jar target/user-account-service-0.0.1-SNAPSHOT.jar
```

The application will start on `http://localhost:8080` by default.

## 📖 API Documentation

Once the application is running, access the API documentation at:

- **Swagger UI**: `http://localhost:8080/swagger-ui.html`
- **OpenAPI JSON**: `http://localhost:8080/v3/api-docs`

### Key Endpoints

#### User Registration
```
POST /api/users/register
Content-Type: application/json
{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "securePassword123"
}
```

#### User Login
```
POST /api/users/login
Content-Type: application/json
{
  "username": "john_doe",
  "password": "securePassword123"
}
```

#### Get User Profile
```
GET /api/users/{userId}
Authorization: Bearer {token}
```

#### Update User Profile
```
PUT /api/users/{userId}
Authorization: Bearer {token}
Content-Type: application/json
{
  "email": "newemail@example.com",
  "firstName": "John",
  "lastName": "Doe"
}
```

## ⚙️ Configuration

### Application Properties

Key configuration properties in `application.properties`:

```properties
# Server Configuration
server.port=8080

# JWT Configuration
jwt.secret=your_secret_key
jwt.expiration=86400000

# Email Configuration (if using email verification)
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your_email@gmail.com
spring.mail.password=your_password
```

## 🧪 Testing

Run the test suite:

```bash
mvn test
```

Run with coverage:

```bash
mvn test jacoco:report
```

## 📁 Project Structure

```
src/
├── main/
│   ├── java/
│   │   └── com/
│   │       └── userservice/
│   │           ├── controller/     # REST Controllers
│   │           ├── service/        # Business Logic
│   │           ├── repository/     # Data Access Layer
│   │           ├── model/          # Entity Classes
│   │           ├── dto/            # Data Transfer Objects
│   │           ├── security/       # Security Configuration
│   │           └── exception/      # Custom Exceptions
│   └── resources/
│       ├── application.properties
│       └── application.yml
└── test/
    └── java/                       # Test Cases
```

## 🔒 Security

- Passwords are encrypted using BCrypt
- JWT tokens for stateless authentication
- CORS configuration for cross-origin requests
- Input validation and sanitization
- SQL injection prevention through JPA
- XSS protection headers

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Yatharth Kumar Saxena**

- GitHub: [@YatharthKumarSaxena](https://github.com/YatharthKumarSaxena)

## 📧 Contact

For any queries or support, please open an issue on GitHub.

## 🙏 Acknowledgments

- Spring Boot Framework Team
- Spring Security Team
- All contributors who have helped shape this project

---

**Note**: This is a template README. Please update the configuration details, endpoints, and project-specific information according to your actual implementation.
