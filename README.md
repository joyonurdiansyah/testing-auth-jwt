# User Authentication API Documentation

![API Documentation](https://i.ibb.co/1nfBGHQ/Docs-API.png)

## Overview
This API handles user authentication, including registration, login, and profile management. It is built using Laravel with JWT (JSON Web Token) for secure authentication.

## Endpoints

### 1. Registration Endpoint (regis)
- **Method:** `POST`
- **URL:** `http://127.0.0.1:8000/api/auth/register`
- **Description:** This endpoint handles user registration by accepting a JSON payload with user information.
- **Request Example:**
  ```json
  {
    "name": "John Doe",
    "email": "john@example.com",
    "password": "password123",
    "password_confirmation": "password123"
  }
  
- **Response: On success, returns a 201 Created status:**
  ```json
  "message": "berhasil melakukan pendaftaran akun",
  "user": {
    "name": "John Doe",
    "email": "john@example.com",
    "id": 1,
    "created_at": "2024-09-28T12:34:56.000000Z",
    "updated_at": "2024-09-28T12:34:56.000000Z"
  }

- **Error Response: If registration fails due to validation errors (e.g., duplicate email), returns a 400 Bad Request:**
  ```json
  {
  "message": "email sudah ada"
    }
  



