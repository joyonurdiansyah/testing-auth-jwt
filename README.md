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

