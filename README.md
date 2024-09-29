# User Authentication API Documentation

![API Documentation](https://i.ibb.co/1nfBGHQ/Docs-API.png)

## Overview This API handles user authentication, including registration, login, and profile management. It is built using Laravel with JWT (JSON Web Token) for secure authentication.

## Endpoints

### 1. Registration Endpoint (regis) - **Method:** `POST` - **URL:** `http://127.0.0.1:8000/api/auth/register` - **Description:** This endpoint handles user registration by accepting a JSON payload with user information. - **Request Example:** ```json { "name": "John Doe", "email": "john@example.com", "password": "password123", "password_confirmation": "password123" } ``` - **Response:** On success, returns a 201 Created status: ```json { "message": "berhasil melakukan pendaftaran akun", "user": { "name": "John Doe", "email": "john@example.com", "id": 1, "created_at": "2024-09-28T12:34:56.000000Z", "updated_at": "2024-09-28T12:34:56.000000Z" } } ``` - **Error Response:** If registration fails due to validation errors (e.g., duplicate email), returns a 400 Bad Request: ```json { "message": "email sudah ada" } ```

### 2. Login Endpoint (loginkan) - **Method:** `POST` - **URL:** `http://127.0.0.1:8000/api/auth/login` - **Description:** This endpoint handles user login by accepting login credentials (email and password). - **Request Example:** ```json { "email": "john@example.com", "password": "password123" } ``` - **Response:** On successful login, returns a 200 OK status with a JWT token and user details: ```json { "access_token": "{{your_token}}...", "token_type": "bearer", "expires_in": 3600, "user": { "id": 1, "name": "John Doe", "email": "john@example.com" } } ``` - **Error Response:** If login fails (e.g., incorrect credentials), returns a 401 Unauthorized: ```json { "error": "Unauthorized" } ```

### 3. Profile Endpoint (profile-abangnya) - **Method:** `GET` - **URL:** `http://127.0.0.1:8000/api/auth/user-profile` - **Description:** This endpoint retrieves the authenticated user's profile information. - **Authentication:** Requires a valid Bearer token in the request header. - **Response:** On success, returns a 200 OK status with user profile details: ```json { "id": 1, "name": "John Doe", "email": "john@example.com" } ```

### 4. Logout Endpoint (logout) - **Method:** `POST` - **URL:** `http://127.0.0.1:8000/api/auth/logout` - **Description:** Logs out the user by invalidating the JWT token. - **Response:** On success, returns a 201 OK status with a confirmation message: ```json { "message": "berhasil keluar bang jangan lupa login lagi" } ```

### 5. Token Refresh Endpoint (refresh) - **Method:** `POST` - **URL:** `http://127.0.0.1:8000/api/auth/refresh` - **Description:** Refreshes the JWT token to extend the session. - **Response:** On success, returns a new JWT token: ```json { "access_token": "new_jwt_token", "token_type": "bearer", "expires_in": 3600 } ```

## Recommendations - **Login Request Method:** Ensure that the login request method is `POST` for better security practices. - **Bearer Token Handling:** When accessing protected endpoints, pass the Bearer token from the login response in the request headers.
