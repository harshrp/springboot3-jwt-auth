# Spring Boot JWT Authentication Example

This is a simple Spring Boot application that demonstrates how to implement JWT (JSON Web Token) authentication for securing RESTful APIs. It provides endpoints for user registration, user authentication, retrieving user details, and dynamic logging level adjustment using Spring Boot Actuator(without any security).

## Features

- User registration: Allows users to register by providing a username and password.
- User authentication: Validates user credentials and generates a JWT token for subsequent API requests.
- JWT token-based authentication: Secures API endpoints using JWT tokens.
- Retrieving user details: Provides an endpoint to retrieve user details based on the authenticated JWT token.
- Dynamic logging level adjustment: Enables changing the logging level at runtime using Spring Boot Actuator.

## Technologies Used

- Java
- Spring Boot
- Spring Security
- Spring Data JPA
- H2 Database
- JWT (JSON Web Tokens)
- Spring Boot Actuator

## Prerequisites

- Java 17 or higher installed on your machine
- Maven installed on your machine

## Getting Started

1. Clone this repository to your local machine:

```
git clone https://github.com/harshrp/springboot3-jwt-auth.git
```

2. Navigate to the project directory:

```
cd springboot3-jwt-auth
```

3. Build the project using Maven:

```
mvn clean package
```

4. Run the application:

  - **Using maven** <br/>``` mvn spring-boot:run```

  - **From jar file**
    Create a jar file using '**mvn clean install**' command and then execute
    <br/>```java -jar target/<jar_filename>.jar```
  - **Directly from IDE**
    <br/>```Right click on Springboot3JwtAuthApplication.java and click on 'Run' option```
    <br/><br/>

5. Once the application is running, you can access the endpoints using a REST client or any HTTP client library.

## API Endpoints

### User Registration

- **URL:** `/api/register`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
    "username": "example_user",
    "password": "example_password"
  }
  ```
- **Response:** `"Registration successful"`

### User Authentication

- **URL:** `/api/authenticate`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
    "username": "example_user",
    "password": "example_password"
  }
  ```
- **Response:** JWT token

### Retrieve User Details

- **URL:** `/api/user`
- **Method:** `GET`
- **Headers:** `Authorization: Bearer <JWT Token>`
- **Response:** User details JSON object

### Dynamic Logging Level Adjustment

- **URL:** `/actuator/loggers`
- **Method:** `GET`
- **Description:** Endpoint provided by Spring Boot Actuator to adjust logging levels at runtime.

## Configuration

- The JWT secret key and token expiration time can be configured in the `application.properties` file.
- The H2 in-memory database is used for demonstration purposes. You can switch to another database by configuring the `application.properties` file accordingly.
- Logging levels can be adjusted dynamically at runtime using Spring Boot Actuator.

## Security

- Passwords are hashed using the BCrypt hashing algorithm before storing them in the database.
- Endpoints are secured using Spring Security and JWT tokens.
- JWT tokens are validated before granting access to protected endpoints.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
