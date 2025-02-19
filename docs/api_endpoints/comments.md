# Comments API

This document provides detailed information about the comment-related API endpoints available in the Constellation project.

## Create a New Comment

### POST `/files/{file_uuid}/comments`
Create a new comment.

**Request Parameters:**
- `file_uuid` (path): The unique identifier of the file.

**Request Body:**
```json
{
  "content": "string"
}
```

**Response:**
- `201 Created`: Comment successfully created.
- `400 Bad Request`: Invalid input data.

**Response Example**
```json
{
  "comment_uuid": "0000-000000...",
  "content": "string",
  "file_uuid": "string"
}
```

## Get All Comments

### GET `/files/{file_uuid}/comments`
Retrieve all comments for a file.

**Request Parameters:**
- `file_uuid` (path): The unique identifier of the file.

**Response:**
- `200 OK`: Returns a list of comments.
- `404 Not Found`: File not found.

**Response Example**
```json
{
  "comments": [
    {
      "comment_uuid": "0000-000000...",
      "content": "string",
      "file_uuid": "string"
    }
  ]
}
```

## Create a Reply

### POST `/files/{file_uuid}/comments/{comment_uuid}`
Create a reply to a comment.

**Request Parameters:**
- `file_uuid` (path): The unique identifier of the file.
- `comment_uuid` (path): The unique identifier of the comment.

**Request Body:**
```json
{
  "content": "string"
}
```

**Response:**
- `201 Created`: Reply successfully created.
- `400 Bad Request`: Invalid input data.
- `404 Not Found`: Comment not found.

**Response Example**
```json
{
  "reply_uuid": "0000-000000...",
  "content": "string",
  "comment_uuid": "string"
}
```

## Delete a Comment

### DELETE `/files/{file_uuid}/comments/{comment_uuid}`
Delete a comment.

**Request Parameters:**
- `file_uuid` (path): The unique identifier of the file.
- `comment_uuid` (path): The unique identifier of the comment.

**Response:**
- `200 OK`: Comment successfully deleted.
- `404 Not Found`: Comment not found.

**Response Example**
```json
{
  "message": "Comment deleted"
}
```

## Update a Comment

### PUT `/files/{file_uuid}/comments/{comment_uuid}`
Update a comment.

**Request Parameters:**
- `file_uuid` (path): The unique identifier of the file.
- `comment_uuid` (path): The unique identifier of the comment.

**Request Body:**
```json
{
  "content": "string"
}
```

**Response:**
- `200 OK`: Comment successfully updated.
- `400 Bad Request`: Invalid input data.
- `404 Not Found`: Comment not found.

**Response Example**
```json
{
  "comment_uuid": "0000-000000...",
  "content": "string",
  "file_uuid": "string"
}
```
