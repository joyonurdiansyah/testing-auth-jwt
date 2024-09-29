# User Authentication API Documentation

![API Documentation](https://i.ibb.co/1nfBGHQ/Docs-API.png)

## Overview
This API handles user authentication, including registration, login, and profile management. It is built using Laravel with JWT (JSON Web Token) for secure authentication.

## Endpoints

### 1. Registration Endpoint (regis)
- **Method:** POST
- **URL:** `http://127.0.0.1:8000/api/auth/register`
- **Description:** This endpoint handles user registration by accepting a JSON payload with user information.

#### Request Example:
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123",
  "password_confirmation": "password123"
} 

### 2.  Login Endpoint (loginkan)
- **Method:** POST
- **URL:** `http://127.0.0.1:8000/api/auth/register`
- **Description:** This endpoint handles user login by accepting login credentials (email and password).

#### Request Example:
```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "token_type": "bearer",
  "expires_in": 3600,
  "user": {
    "id": 1,
    "name": "John Doe",
    "email": "john@example.com"
  }
}

### 3. Profile Endpoint (profile-abangnya)
- **Method:** POST
- **URL:** `http://127.0.0.1:8000/api/auth/user-profile`
- **Description:** This endpoint retrieves the authenticated user's profile information..
- **Authentication:** Requires a valid Bearer token in the request header...

#### Request Example:
```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john@example.com"
}

### 4. Logout Endpoint (logout)
- **Method:** POST
- **URL:** `http://127.0.0.1:8000/api/auth/logout`
- **Description:** Logs out the user by invalidating the JWT token..

#### Request Example:
```json
{
  "message": "berhasil keluar bang jangan lupa login lagi"
}




