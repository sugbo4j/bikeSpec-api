# BikeSpec API

A RESTful API service built with Java and Spring Boot that serves as the backend for the BikeSpec Pro mobile application, providing access to the comprehensive bike component database and compatibility engine.

## 🔌 About BikeSpec API

BikeSpec API is the central hub that connects the BikeSpec Scraper's data collection with the BikeSpec Pro mobile application. It provides a secure, efficient, and well-documented set of endpoints that enable all the functionality required by the mobile app, from component browsing to complex compatibility checks.

## 🚀 Key Features

### Authentication & Security
- OAuth 2.0 implementation for secure API access
- Role-based access control for different API consumers
- Rate limiting to prevent abuse
- API key management for third-party integrations

### Component Data Endpoints
- Comprehensive CRUD operations for bike components
- Advanced filtering and search capabilities
- Pagination for efficient data retrieval
- Rich metadata and relationship information

### Compatibility Engine
- RESTful endpoints for compatibility checking
- Detailed compatibility reports with explanation
- Alternatives suggestion when incompatibilities are found
- Compatibility rule management system

### User Management
- User profiles and preferences
- Saved bike builds and components
- Sharing capabilities
- Usage analytics

### Performance Features
- Response caching for frequently accessed data
- Asynchronous processing for complex operations
- Batch operations for multiple components
- Database query optimization

## 🛠️ Technical Stack

- **Framework**: Spring Boot 2.6+
- **Language**: Java 11+
- **Database**: MongoDB (for component data)
- **Security**: Spring Security with OAuth 2.0
- **Documentation**: Swagger/OpenAPI 3.0
- **Testing**: JUnit 5, Mockito, TestContainers
- **CI/CD**: GitHub Actions
- **Containerization**: Docker

## 📚 API Documentation

The API is fully documented using OpenAPI 3.0 (Swagger). When running locally, documentation is available at:

```
http://localhost:8080/swagger-ui.html
```

Key endpoint categories include:

- `/api/v1/components` - Component management
- `/api/v1/frames` - Bike frame information
- `/api/v1/compatibility` - Compatibility checking
- `/api/v1/users` - User management
- `/api/v1/builds` - Saved bike builds

## 🔄 Integration Points

- **BikeSpec Scraper**: Consumes scraped data via secure endpoints
- **BikeSpec Pro Mobile App**: Provides all backend functionality
- **Third-party applications**: Optional API access via developer program

## 📊 Project Status

1. Core API architecture - Implemented
2. Authentication system - Implemented
3. Basic CRUD endpoints - Implemented
4. Compatibility engine API - In Progress
5. User management - In Progress
6. Performance optimization - Planned
7. Third-party developer access - Future Enhancement

## 🚦 Getting Started

### Prerequisites
- Java 11 or higher
- Maven 3.6+
- MongoDB 4.4+
- Docker (optional)

### Installation

#### Standard Setup
```bash
git clone https://github.com/yourusername/bikespec-api.git
cd bikespec-api
mvn clean install
```

#### Docker Setup
```bash
docker-compose up -d
```

### Configuration
Create an `application.properties` file in `src/main/resources` with the following settings:
```
# Server Configuration
server.port=8080

# MongoDB Configuration
spring.data.mongodb.uri=mongodb://localhost:27017/bikecomponents

# OAuth Configuration
spring.security.oauth2.client.registration.client-id=bikespec-client
spring.security.oauth2.client.registration.client-secret=your-secret-key
spring.security.oauth2.client.registration.scope=read,write

# API Configuration
api.version=v1
api.rate-limit=100
```

### Running the API
```bash
java -jar target/bikespec-api-1.0.0.jar
```

## 🧪 Testing

```bash
# Run unit tests
mvn test

# Run integration tests
mvn verify
```

## 🔐 Security Considerations

- All endpoints are secured using OAuth 2.0
- Sensitive operations require elevated permissions
- Personal data is encrypted at rest
- All API calls are logged for audit purposes

## 🤝 Contributing

Contributions are welcome! Please check out our contribution guidelines in CONTRIBUTING.md.

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🔗 Related Projects

- [BikeSpec app](https://github.com/sugbo4j/bikespec-app) - Mobile application that consumes this API
- [BikeSpec Scraper](https://github.com/sugbo4j/bike-components-scraper) - Data collection tool that feeds this API
