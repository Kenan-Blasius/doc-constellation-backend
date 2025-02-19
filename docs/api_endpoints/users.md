# Users API

This document provides detailed information about the user-related API endpoints available in the Constellation project.

## Check Token and Constellation Access

### POST `/check_token/{constellation_uuid}`
Check JWT token and constellation access.

**Request Parameters:**
- `constellation_uuid` (path): The unique identifier of the constellation.

**Request Body:**
```json
{
  "token": "string"
}
```

**Response:**
- `200 OK`: Token is valid and user has access.
- `401 Unauthorized`: Token is invalid or user does not have access.

**Response Example**
```json
{
  "rights": "admin"
}
```

## Register a New User

### POST `/register`
Register a new user.

**Request Body:**
```json
{
  "name": "string",
  "password": "string",
  "email": "string"
}
```

**Response:**
- `201 Created`: User successfully registered.
- `400 Bad Request`: Invalid input data.

**Response Example**
```json
{
    "user_uuid": "0000-000000...",
    "access_token": "this_is_a_token",
    "token_type": "bearer"
}
```

## Login a User

### POST `/login`
Login a user.

**Request Body:**
```json
{
  "name": "string",
  "password": "string"
}
```

**Response:**
- `200 OK`: Login successful, returns JWT token.
- `401 Unauthorized`: Invalid name or password.

**Response Example**
```json
{
    "access_token": "this_is_a_token",
    "token_type": "bearer"
}
```

## Get a User by ID

### GET `/users/{user_uuid}`
Retrieve a user by their ID.

**Request Parameters:**
- `user_uuid` (path): The unique identifier of the user.

**Response:**
- `200 OK`: Returns user details.
- `404 Not Found`: User not found.

**Response Example**
```json
{
    "user_uuid": "0000-000000...",
    "name": "string",
    "email": "string"
}
```

## Delete a User

### DELETE `/users`
Delete a user.

**Request Body:**
```json
{
  "user_uuid": "string"
}
```

**Response:**
- `200 OK`: User successfully deleted.
- `404 Not Found`: User not found.

**Response Example**
```json
{
    "message": "User deleted"
}
```

## Update a User

### PATCH `/users`
Update a user. You can update the name, email, password, or all of them, depending on the request body.

**Request Body:**
```json
{
  "uuid": "string",
  "name": "string",
  "email": "string"
}
```

**Response:**
- `200 OK`: User successfully updated.
- `400 Bad Request`: Invalid input data.
- `404 Not Found`: User not found.

**Response Example**
```json
{
    "user_uuid": "0000-000000...",
    "access_token": "this_is_a_token",
}
```
