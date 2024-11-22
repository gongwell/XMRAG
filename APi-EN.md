# API Technical Documentation

## Introduction

This project is based on the Django framework and is designed to interface with the Kernel search system for validation and interaction. After logging in, users can obtain API keys and endpoints to enable file uploads and Kernel search functionalities.

## Features

- User registration, login, and account activation.
- Password reset functionality.
- Secure file uploads to the Kernel system.
- API requests to perform authenticated searches on the Kernel system.
- User-specific daily query limits and storage management.

## User Login

The login portal is located at: http://cq.ath.cx:8888/.
After logging in, users can retrieve their API keys and endpoint details from the API page.

## API Documentation

### 1. API Overview

**Endpoint**: `GET /api/`
**Description**: Lists all available API endpoints.

------

### 2. User Registration

**Endpoint**: `POST /api/register/`
**Description**: Register a new user account.

**Request Example**:

```
bashcurl -X POST http://cq.ath.cx:8881/api/register \
-H "Content-Type: application/json" \
-d '{
    "username": "example_user",
    "password": "example_password",
    "email": "example@example.com"
}'
```

**Sample Response**:

```
json{
    "message": "Registration complete. Please activate your account via email."
}
```

------

### 3. User Login

**Endpoint**: `POST /api/token/`
**Description**: Log in to obtain a JWT token.

**Request Example**:

```
bashcurl -X POST http://cq.ath.cx:8881/api/token/ \
-H "Content-Type: application/json" \
-d '{
    "username": "example_user",
    "password": "example_password"
}'
```

**Sample Response**:

```
json{
    "access": "your_access_token",
    "refresh": "your_refresh_token"
}
```

------

### 4. Kernel Search API

**Endpoint**: `POST /api/ask`
**Description**: Send a query to the Kernel system using your API key.

**Request Headers**:

```
bashAuthorization: Bearer <your_access_token>
```

**Request Example**:

```
bashcurl -X POST http://cq.ath.cx:8881/api/ask \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json" \
-d '{
    "question": "Your query"
}'
```

**Sample Response**:

```
json{
    "answer": "The search result"
}
```

------

### 5. File Upload API

**Endpoint**: `POST /api/upload`
**Description**: Upload files to the Kernel system (maximum file size: 10MB).

**Request Example**:

```
bashcurl -X POST http://cq.ath.cx:8881/api/upload \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: multipart/form-data" \
-F "file_uploaded=@path/to/your/file"
```

**Sample Response**:

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
**Description**: Delete all files uploaded by the current user.

**Request Example**:

```
bashcurl -X DELETE http://cq.ath.cx:8881/api/deleteUploads/ \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json"
```

**Sample Response**:

```
json{
    "message": "All uploaded documents have been deleted."
}
```