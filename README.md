User Authentication API
A Spring Boot REST API for User Registration, Login (JWT Authentication), and Fetching Logged-in User Information using Bearer Token authentication.

Features
User registration with BCrypt password hashing

User login with JWT token generation

Secure /me endpoint to get logged-in user details

MySQL support (configurable in application.yml)

Tech Stack
Java 17 • Spring Boot 3 • Spring Security • Spring Data JPA • JWT • Lombok • MySQL

API Endpoints
1. Register User
POST /api/auth/register
Body:
{
  "username": "akash",
  "email": "akash@example.com",
  "password": "akash123"
}

Expected Response:
{
  "id": 1,
  "username": "akash",
  "email": "akash@example.com",
  "password": "$2a$10$..."
}

2. Login
POST /api/auth/login
Body:
{
  "username": "akash",
  "password": "akash123"
}

Expected Response:
{
  "accessToken": "eyJhbGciOiJIUzI1NiIs..."
}

3. Get Current User Info
GET /api/auth/me
Headers:
Authorization: Bearer <JWT_TOKEN>

Expected Response:
{
  "id": 1,
  "username": "akash",
  "email": "akash@example.com"
}

How to Test in Postman
Register a User → POST /api/auth/register with username, email, and password

Login → POST /api/auth/login → copy accessToken

Fetch User Info → GET /api/auth/me → add header:

Authorization: Bearer <accessToken>

git clone https://github.com/arsalansadar/user-registration-api.git

cd user-registration-api

mvn spring-boot:run


Author

Arsalan Sadar

Java Backend Developer | Spring Boot | REST APIs | JWT | MySQL
