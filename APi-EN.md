# API Technical Documentation

## Introduction

This project is built on the Django framework, primarily designed to interface with the Kernel search system and validate its APIs. After logging in, users can retrieve API keys and endpoints to perform actions such as file uploads and Kernel search functionalities.

## Features

- User registration, login, and account activation.
- Password reset functionality.
- Secure file uploads to the Kernel system.
- API requests for authenticated searches in the Kernel system.
- Daily conversation limits and user storage management.

## User Login

The login page for the project is available at: http://cq.ath.cx:8888/.
After logging in, users can obtain API keys and endpoints on the API page.

## API Documentation

### 1. API Endpoint

**Endpoint**: `GET /api/`
**Description**: Provides a list of all available API paths.

------

### 2. User Registration

**Endpoint**: `POST /api/register/`
**Description**: Registers a new user.

**Request Parameters**:

```
json{
    "username": "example_user",
    "password": "example_password",
    "email": "example@example.com"
}
```

**Example Response**:

```
json{
    "message": "Registration complete. Please check your email for activation."
}
```

------

### 3. User Login

**Endpoint**: `POST /api/token/`
**Description**: Logs in a user and retrieves a JWT token.

**Request Parameters**:

```
json{
    "username": "example_user",
    "password": "example_password"
}
```

**Example Response**:

```
json{
    "access": "your_access_token",
    "refresh": "your_refresh_token"
}
```

------

### 4. Kernel Search API

**Endpoint**: `POST /api/ask`
**Description**: Sends a query to the Kernel system using the user’s API key.

**Request Header**:

```
makefile



Authorization: Bearer <your_access_token>
```

**Request Parameters**:

```
json{
    "question": "Your question"
}
```

**Example Response**:

```
json{
    "answer": "The response"
}
```

------

### 5. File Upload API

**Endpoint**: `POST /api/upload`
**Description**: Uploads a file to the Kernel system. The maximum file size is 10MB.

**Request Header**:

```
makefile



Authorization: Bearer <your_access_token>
```

**Request Parameters**: Upload the file via `form-data` with the field name `file_uploaded`.

**Example Response**:

```
json{
    "message": "Upload successful!",
    "data": {
        "documentId": "abc123",
        "index": "user_1_index"
    }
}
```

------

### 6. File Deletion API

**Endpoint**: `DELETE /api/deleteUploads/`
**Description**: Deletes all files uploaded by the current user.

**Request Header**:

```
makefile



Authorization: Bearer <your_access_token>
```

**Example Response**:

```
json{
    "message": "All uploaded documents have been deleted."
}
```
